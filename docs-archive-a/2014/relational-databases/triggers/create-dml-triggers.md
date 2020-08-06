---
title: Criar gatilhos DML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- encryption [SQL Server], DML triggers
- deferred name resolution, DML triggers
- WITH ENCRYPTION clause
- IF UPDATE
- SET statement, DML triggers
- DML triggers, programming
- testing column changes
- results [SQL Server], DML triggers
ms.assetid: b2b52258-642b-462e-8e0f-18c09d2eccf4
author: rothja
ms.author: jroth
ms.openlocfilehash: f843513ba634bcb3479e373eb9ac978ab584588d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582883"
---
# <a name="create-dml-triggers"></a><span data-ttu-id="12483-102">Criar gatilhos DML</span><span class="sxs-lookup"><span data-stu-id="12483-102">Create DML Triggers</span></span>
  <span data-ttu-id="12483-103">Este tópico descreve como criar um gatilho DML [!INCLUDE[tsql](../../includes/tsql-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TRIGGER.</span><span class="sxs-lookup"><span data-stu-id="12483-103">This topic describes how to create a [!INCLUDE[tsql](../../includes/tsql-md.md)] DML trigger by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TRIGGER statement.</span></span>  
  
##  <a name="before-you-begin"></a><a name="Top"></a> <span data-ttu-id="12483-104">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="12483-104">Before You Begin</span></span>  
  
### <a name="limitations-and-restrictions"></a><span data-ttu-id="12483-105">Limitações e Restrições</span><span class="sxs-lookup"><span data-stu-id="12483-105">Limitations and Restrictions</span></span>  
 <span data-ttu-id="12483-106">Para obter uma lista de limitações e restrições relacionadas à criação de gatilhos DML, veja [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="12483-106">For a list of limitations and restrictions related to creating DML triggers, see [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql).</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="12483-107">Permissões</span><span class="sxs-lookup"><span data-stu-id="12483-107">Permissions</span></span>  
 <span data-ttu-id="12483-108">Exige a permissão ALTER na tabela ou exibição na qual o gatilho é criado.</span><span class="sxs-lookup"><span data-stu-id="12483-108">Requires ALTER permission on the table or view on which the trigger is being created.</span></span>  
  
##  <a name="how-to-create-a-dml-trigger"></a><a name="Procedures"></a> <span data-ttu-id="12483-109">Como criar um gatilho DML</span><span class="sxs-lookup"><span data-stu-id="12483-109">How to Create a DML Trigger</span></span>  
 <span data-ttu-id="12483-110">Você pode usar uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="12483-110">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="12483-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="12483-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="12483-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="12483-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="12483-113">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="12483-113">Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="12483-114">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="12483-114">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="12483-115">Expanda **Bancos de Dados**, expanda o banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , expanda **Tabelas** e expanda a tabela **Purchasing.PurchaseOrderHeader**.</span><span class="sxs-lookup"><span data-stu-id="12483-115">Expand **Databases**, expand the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, expand **Tables** and then expand the table **Purchasing.PurchaseOrderHeader**.</span></span>  
  
3.  <span data-ttu-id="12483-116">Clique com o botão direito do mouse em **Gatilhos**e selecione **Novo Gatilho**.</span><span class="sxs-lookup"><span data-stu-id="12483-116">Right-click **Triggers**, and then select **New Trigger**.</span></span>  
  
4.  <span data-ttu-id="12483-117">No menu **Consulta** , clique em **Especificar Valores para Parâmetros de Modelo**.</span><span class="sxs-lookup"><span data-stu-id="12483-117">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span> <span data-ttu-id="12483-118">Como alternativa, pressione (Ctrl-Shift-M) para abrir caixa de diálogo **Especificar Valores para Parâmetros de Modelo** .</span><span class="sxs-lookup"><span data-stu-id="12483-118">Alternatively, you can press (Ctrl-Shift-M) to open the **Specify Values for Template Parameters** dialog box.</span></span>  
  
5.  <span data-ttu-id="12483-119">Na caixa de diálogo **Especificar Valores para Parâmetros de Modelo** , digite os seguintes valores para os parâmetros mostrados.</span><span class="sxs-lookup"><span data-stu-id="12483-119">In the **Specify Values for Template Parameters** dialog box, enter the following values for the parameters shown.</span></span>  
  
    |<span data-ttu-id="12483-120">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="12483-120">Parameter</span></span>|<span data-ttu-id="12483-121">Valor</span><span class="sxs-lookup"><span data-stu-id="12483-121">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="12483-122">Autor</span><span class="sxs-lookup"><span data-stu-id="12483-122">Author</span></span>|<span data-ttu-id="12483-123">*Seu nome*</span><span class="sxs-lookup"><span data-stu-id="12483-123">*Your name*</span></span>|  
    |<span data-ttu-id="12483-124">Data de criação</span><span class="sxs-lookup"><span data-stu-id="12483-124">Create Date</span></span>|<span data-ttu-id="12483-125">*A data de hoje*</span><span class="sxs-lookup"><span data-stu-id="12483-125">*Today's date*</span></span>|  
    |<span data-ttu-id="12483-126">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="12483-126">Description</span></span>|<span data-ttu-id="12483-127">Verifica a avaliação de crédito de fornecedor antes de permitir uma nova ordem de compra com o fornecedor a ser inserido.</span><span class="sxs-lookup"><span data-stu-id="12483-127">Checks the vendor credit rating before allowing a new purchase order with the vendor to be inserted.</span></span>|  
    |<span data-ttu-id="12483-128">Schema_Name</span><span class="sxs-lookup"><span data-stu-id="12483-128">Schema_Name</span></span>|<span data-ttu-id="12483-129">Compra</span><span class="sxs-lookup"><span data-stu-id="12483-129">Purchasing</span></span>|  
    |<span data-ttu-id="12483-130">Trigger_Name</span><span class="sxs-lookup"><span data-stu-id="12483-130">Trigger_Name</span></span>|<span data-ttu-id="12483-131">NewPODetail2</span><span class="sxs-lookup"><span data-stu-id="12483-131">NewPODetail2</span></span>|  
    |<span data-ttu-id="12483-132">Table_Name</span><span class="sxs-lookup"><span data-stu-id="12483-132">Table_Name</span></span>|<span data-ttu-id="12483-133">PurchaseOrderDetail</span><span class="sxs-lookup"><span data-stu-id="12483-133">PurchaseOrderDetail</span></span>|  
    |<span data-ttu-id="12483-134">Data_Modification_Statement</span><span class="sxs-lookup"><span data-stu-id="12483-134">Data_Modification_Statement</span></span>|<span data-ttu-id="12483-135">Remova UPDATE e DELETE da lista.</span><span class="sxs-lookup"><span data-stu-id="12483-135">Remove UPDATE and DELETE from the list.</span></span>|  
  
6.  <span data-ttu-id="12483-136">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="12483-136">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="12483-137">No **Editor de Consultas**, substitua o comentário `-- Insert statements for trigger here` pela seguinte instrução:</span><span class="sxs-lookup"><span data-stu-id="12483-137">In the **Query Editor**, replace the comment `-- Insert statements for trigger here` with the following statement:</span></span>  
  
    ```sql  
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
  
8.  <span data-ttu-id="12483-138">Para verificar se a sintaxe é válida, no menu **Consulta** , clique em **Analisar**.</span><span class="sxs-lookup"><span data-stu-id="12483-138">To verify the syntax is valid, on the **Query** menu, click **Parse**.</span></span> <span data-ttu-id="12483-139">Se uma mensagem de erro for retornada, compare a instrução com as informações acima e corrija conforme necessário. Repita esta etapa.</span><span class="sxs-lookup"><span data-stu-id="12483-139">If an error message is returned, compare the statement with the information above and correct as needed and repeat this step.</span></span>  
  
9. <span data-ttu-id="12483-140">Para criar o gatilho DML, no menu **Consulta** , clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="12483-140">To create the DML trigger, from the **Query** menu, click **Execute**.</span></span> <span data-ttu-id="12483-141">O gatilho DML é criado como um objeto no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="12483-141">The DML trigger is created as an object in the database.</span></span>  
  
10. <span data-ttu-id="12483-142">Para ver o gatilho DML listado no Pesquisador de Objetos, clique com o botão direito do mouse em **Gatilhos** e selecione **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="12483-142">To see the DML trigger listed in Object Explorer, right-click **Triggers** and select **Refresh**.</span></span>  
  
 [<span data-ttu-id="12483-143">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="12483-143">Before You Begin</span></span>](#Top)  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="12483-144">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="12483-144">Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="12483-145">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="12483-145">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="12483-146">No menu **Arquivo** , clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="12483-146">From the **File** menu, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="12483-147">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="12483-147">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="12483-148">Este exemplo cria o mesmo gatilho DML armazenado como anteriormente.</span><span class="sxs-lookup"><span data-stu-id="12483-148">This example creates the same stored DML trigger as above.</span></span>  
  
    ```sql
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
