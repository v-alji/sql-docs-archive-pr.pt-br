---
title: Criar gatilhos DML para tratar várias linhas de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- multiple row DML triggers
- UPDATE statement [SQL Server], DML triggers
- DELETE statement [SQL Server], DML triggers
- multirow DML triggers [SQL Server]
- INSERT statement [SQL Server], DML triggers
- DML triggers, multirow
ms.assetid: d476c124-596b-4b27-a883-812b6b50a735
author: rothja
ms.author: jroth
ms.openlocfilehash: 11ea7aa457a5cdfcafd4a8c4e0ac170ae0e3b9c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582888"
---
# <a name="create-dml-triggers-to-handle-multiple-rows-of-data"></a><span data-ttu-id="81682-102">Crie gatilhos DML para tratar várias linhas de dados</span><span class="sxs-lookup"><span data-stu-id="81682-102">Create DML Triggers to Handle Multiple Rows of Data</span></span>
  <span data-ttu-id="81682-103">Ao gravar o código de um gatilho DML, considere que a instrução que aciona o gatilho pode ser uma única instrução que afeta diversas linhas de dados, em vez de uma única linha.</span><span class="sxs-lookup"><span data-stu-id="81682-103">When you write the code for a DML trigger, consider that the statement that causes the trigger to fire can be a single statement that affects multiple rows of data, instead of a single row.</span></span> <span data-ttu-id="81682-104">Esse comportamento é comum para os gatilhos UPDATE e DELETE, pois essas instruções geralmente afetam várias linhas.</span><span class="sxs-lookup"><span data-stu-id="81682-104">This behavior is common for UPDATE and DELETE triggers because these statements frequently affect multiple rows.</span></span> <span data-ttu-id="81682-105">O comportamento é menos comum para gatilhos INSERT, pois a instrução INSERT básica adiciona apenas uma única linha.</span><span class="sxs-lookup"><span data-stu-id="81682-105">The behavior is less common for INSERT triggers because the basic INSERT statement adds only a single row.</span></span> <span data-ttu-id="81682-106">Entretanto, como o gatilho INSERT pode ser acionado por uma instrução INSERT INTO (*table_name*) SELECT, a inserção de várias linhas pode causar a invocação de um único gatilho.</span><span class="sxs-lookup"><span data-stu-id="81682-106">However, because an INSERT trigger can be fired by an INSERT INTO (*table_name*) SELECT statement, the insertion of many rows may cause a single trigger invocation.</span></span>  
  
 <span data-ttu-id="81682-107">Considerações multilinha são especialmente importantes quando a função de um gatilho DML deve ser recalcular automaticamente valores de resumo de uma tabela e armazenar os resultados em outra para contagens contínuas.</span><span class="sxs-lookup"><span data-stu-id="81682-107">Multirow considerations are especially important when the function of a DML trigger is to automatically recalculate summary values from one table and store the results in another for ongoing tallies.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="81682-108">Não recomendamos usar cursores em gatilhos porque eles potencialmente podem reduzir o desempenho.</span><span class="sxs-lookup"><span data-stu-id="81682-108">We do not recommend using cursors in triggers because they could potentially reduce performance.</span></span> <span data-ttu-id="81682-109">Para projetar um gatilho que afeta várias linhas, use uma lógica baseada em conjunto de linhas em vez de cursores.</span><span class="sxs-lookup"><span data-stu-id="81682-109">To design a trigger that affects multiple rows, use rowset-based logic instead of cursors.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="81682-110">Exemplos</span><span class="sxs-lookup"><span data-stu-id="81682-110">Examples</span></span>  
 <span data-ttu-id="81682-111">Os gatilhos DML nos exemplos a seguir são projetados para armazenar o total de execução de uma coluna em outra tabela do banco de dados de exemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81682-111">The DML triggers in the following examples are designed to store a running total of a column in another table of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
### <a name="a-storing-a-running-total-for-a-single-row-insert"></a><span data-ttu-id="81682-112">a.</span><span class="sxs-lookup"><span data-stu-id="81682-112">A.</span></span> <span data-ttu-id="81682-113">Armazenando um total de execução de uma inserção de única linha</span><span class="sxs-lookup"><span data-stu-id="81682-113">Storing a running total for a single-row insert</span></span>  
 <span data-ttu-id="81682-114">A primeira versão do gatilho DML trabalha bem para uma inserção de única linha quando uma linha de dados é carregada na tabela `PurchaseOrderDetail` .</span><span class="sxs-lookup"><span data-stu-id="81682-114">The first version of the DML trigger works well for a single-row insert when a row of data is loaded into the `PurchaseOrderDetail` table.</span></span> <span data-ttu-id="81682-115">Uma instrução INSERT aciona um gatilho DML e uma nova linha é carregada na tabela **inserida** durante o período de duração da execução do gatilho.</span><span class="sxs-lookup"><span data-stu-id="81682-115">An INSERT statement fires the DML trigger, and the new row is loaded into the **inserted** table for the duration of the trigger execution.</span></span> <span data-ttu-id="81682-116">A instrução `UPDATE` lê o valor da coluna `LineTotal` para a linha e adiciona esse valor ao valor existente na coluna `SubTotal` na tabela `PurchaseOrderHeader` .</span><span class="sxs-lookup"><span data-stu-id="81682-116">The `UPDATE` statement reads the `LineTotal` column value for the row and adds that value to the existing value in the `SubTotal` column in the `PurchaseOrderHeader` table.</span></span> <span data-ttu-id="81682-117">A cláusula `WHERE` certifica que a linha atualizada na tabela `PurchaseOrderDetail` corresponde à `PurchaseOrderID` da linha na tabela **inserida** .</span><span class="sxs-lookup"><span data-stu-id="81682-117">The `WHERE` clause makes sure that the updated row in the `PurchaseOrderDetail` table matches the `PurchaseOrderID` of the row in the **inserted** table.</span></span>  
  
```  
-- Trigger is valid for single-row inserts.  
USE AdventureWorks2012;  
GO  
CREATE TRIGGER NewPODetail  
ON Purchasing.PurchaseOrderDetail  
AFTER INSERT AS  
   UPDATE PurchaseOrderHeader  
   SET SubTotal = SubTotal + LineTotal  
   FROM inserted  
   WHERE PurchaseOrderHeader.PurchaseOrderID = inserted.PurchaseOrderID ;  
```  
  
### <a name="b-storing-a-running-total-for-a-multirow-or-single-row-insert"></a><span data-ttu-id="81682-118">B.</span><span class="sxs-lookup"><span data-stu-id="81682-118">B.</span></span> <span data-ttu-id="81682-119">Armazenando um total de execução para uma inserção multilinha ou de linha única</span><span class="sxs-lookup"><span data-stu-id="81682-119">Storing a running total for a multirow or single-row insert</span></span>  
 <span data-ttu-id="81682-120">Para uma inserção de várias linhas, o gatilho DML no exemplo A pode não funcionar corretamente; a expressão à direita de uma expressão de atribuição em uma instrução UPDATE (`SubTotal` + `LineTotal`) pode ser apenas um único valor, não uma lista de valores.</span><span class="sxs-lookup"><span data-stu-id="81682-120">For a multirow insert, the DML trigger in example A might not operate correctly; the expression to the right of an assignment expression in an UPDATE statement (`SubTotal` + `LineTotal`) can be only a single value, not a list of values.</span></span> <span data-ttu-id="81682-121">Portanto, o efeito do gatilho é para recuperar um valor de qualquer linha única na tabela **inserida** e adicionar esse valor a um valor de `SubTotal` existente na tabela `PurchaseOrderHeader` para um valor específico `PurchaseOrderID` .</span><span class="sxs-lookup"><span data-stu-id="81682-121">Therefore, the effect of the trigger is to retrieve a value from any single row in the **inserted** table and add that value to the existing `SubTotal` value in the `PurchaseOrderHeader` table for a specific `PurchaseOrderID` value.</span></span> <span data-ttu-id="81682-122">Essa operação pode não ter o efeito esperado se um único valor de `PurchaseOrderID` ocorrer mais de uma vez na tabela **inserida** .</span><span class="sxs-lookup"><span data-stu-id="81682-122">This operation might not have the expected effect if a single `PurchaseOrderID` value occurred more than one time in the **inserted** table.</span></span>  
  
 <span data-ttu-id="81682-123">Para atualizar corretamente a tabela `PurchaseOrderHeader` , o gatilho deve permitir várias linhas na tabela **inserida** .</span><span class="sxs-lookup"><span data-stu-id="81682-123">To correctly update the `PurchaseOrderHeader` table, the trigger must allow for the chance of multiple rows in the **inserted** table.</span></span> <span data-ttu-id="81682-124">Você pode fazer isso usando a função `SUM` que calcula o total de um grupo de linhas `LineTotal` na tabela **inserida** de cada `PurchaseOrderID`.</span><span class="sxs-lookup"><span data-stu-id="81682-124">You can do this by using the `SUM` function that calculates the total `LineTotal` for a group of rows in the **inserted** table for each `PurchaseOrderID`.</span></span> <span data-ttu-id="81682-125">A função `SUM` é incluída em uma subconsulta correlacionada (a instrução `SELECT` entre parênteses).</span><span class="sxs-lookup"><span data-stu-id="81682-125">The `SUM` function is included in a correlated subquery (the `SELECT` statement in parentheses).</span></span> <span data-ttu-id="81682-126">Esta subconsulta retorna um único valor para cada `PurchaseOrderID` na tabela **inserida** que corresponde ou está correlacionada a `PurchaseOrderID` na tabela `PurchaseOrderHeader` .</span><span class="sxs-lookup"><span data-stu-id="81682-126">This subquery returns a single value for each `PurchaseOrderID` in the **inserted** table that matches or is correlated with a `PurchaseOrderID` in the `PurchaseOrderHeader` table.</span></span>  
  
```  
-- Trigger is valid for multirow and single-row inserts.  
USE AdventureWorks2012;  
GO  
CREATE TRIGGER NewPODetail2  
ON Purchasing.PurchaseOrderDetail  
AFTER INSERT AS  
   UPDATE Purchasing.PurchaseOrderHeader  
   SET SubTotal = SubTotal +   
      (SELECT SUM(LineTotal)  
      FROM inserted  
      WHERE PurchaseOrderHeader.PurchaseOrderID  
       = inserted.PurchaseOrderID)  
   WHERE PurchaseOrderHeader.PurchaseOrderID IN  
      (SELECT PurchaseOrderID FROM inserted);  
```  
  
 <span data-ttu-id="81682-127">Esse gatilho também funciona corretamente em uma inserção de única linha; a soma da coluna de valor `LineTotal` é a soma de uma única linha.</span><span class="sxs-lookup"><span data-stu-id="81682-127">This trigger also works correctly in a single-row insert; the sum of the `LineTotal` value column is the sum of a single row.</span></span> <span data-ttu-id="81682-128">Entretanto, com esse gatilho a subconsulta correlacionada e o operador `IN` usado na cláusula `WHERE` exigem processamento adicional de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81682-128">However, with this trigger the correlated subquery and the `IN` operator that is used in the `WHERE` clause require additional processing from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="81682-129">Isto é desnecessário para uma inserção da única-linha.</span><span class="sxs-lookup"><span data-stu-id="81682-129">This is unnecessary for a single-row insert.</span></span>  
  
### <a name="c-storing-a-running-total-based-on-the-type-of-insert"></a><span data-ttu-id="81682-130">C.</span><span class="sxs-lookup"><span data-stu-id="81682-130">C.</span></span> <span data-ttu-id="81682-131">Armazenando um total de execução com base no tipo de inserção</span><span class="sxs-lookup"><span data-stu-id="81682-131">Storing a running total based on the type of insert</span></span>  
 <span data-ttu-id="81682-132">Você pode alterar o gatilho para usar o método ideal para o número de linhas.</span><span class="sxs-lookup"><span data-stu-id="81682-132">You can change the trigger to use the method optimal for the number of rows.</span></span> <span data-ttu-id="81682-133">Por exemplo, a função `@@ROWCOUNT` pode ser usada na lógica do gatilho para distinguir entre uma inserção única e multilinha.</span><span class="sxs-lookup"><span data-stu-id="81682-133">For example, the `@@ROWCOUNT` function can be used in the logic of the trigger to distinguish between a single and a multirow insert.</span></span>  
  
```  
-- Trigger valid for multirow and single row inserts  
-- and optimal for single row inserts.  
USE AdventureWorks2012;  
GO  
CREATE TRIGGER NewPODetail3  
ON Purchasing.PurchaseOrderDetail  
FOR INSERT AS  
IF @@ROWCOUNT = 1  
BEGIN  
   UPDATE Purchasing.PurchaseOrderHeader  
   SET SubTotal = SubTotal + LineTotal  
   FROM inserted  
   WHERE PurchaseOrderHeader.PurchaseOrderID = inserted.PurchaseOrderID  
END  
ELSE  
BEGIN  
      UPDATE Purchasing.PurchaseOrderHeader  
   SET SubTotal = SubTotal +   
      (SELECT SUM(LineTotal)  
      FROM inserted  
      WHERE PurchaseOrderHeader.PurchaseOrderID  
       = inserted.PurchaseOrderID)  
   WHERE PurchaseOrderHeader.PurchaseOrderID IN  
      (SELECT PurchaseOrderID FROM inserted)  
END;  
```  
  
## <a name="see-also"></a><span data-ttu-id="81682-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="81682-134">See Also</span></span>  
 [<span data-ttu-id="81682-135">Gatilhos DML</span><span class="sxs-lookup"><span data-stu-id="81682-135">DML Triggers</span></span>](dml-triggers.md)  
  
  
