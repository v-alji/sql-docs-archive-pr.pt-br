---
title: Modificar um procedimento armazenado | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- modifying stored procedures
- editing stored procedures
- stored procedures [SQL Server], modifying
ms.assetid: 13396239-6100-48ce-aa34-461358d99c92
author: stevestein
ms.author: sstein
ms.openlocfilehash: 906f0e06650da505094d18774ce86dab53d53f38
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678679"
---
# <a name="modify-a-stored-procedure"></a><span data-ttu-id="fd3e6-102">Modificar um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="fd3e6-102">Modify a Stored Procedure</span></span>
    
##  <a name="this-topic-describes-how-to-modify-a-stored-procedure-in-sscurrent-by-using-ssmanstudiofull-or-tsql"></a><a name="Top"></a> <span data-ttu-id="fd3e6-103">Este tópico descreve como modificar um procedimento armazenado no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd3e6-103">This topic describes how to modify a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="fd3e6-104">**Antes de começar:**  [Limitações e Restrições](#Restrictions), [Segurança](#Security)</span><span class="sxs-lookup"><span data-stu-id="fd3e6-104">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="fd3e6-105">**Para alterar um procedimento usando:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="fd3e6-105">**To alter a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fd3e6-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="fd3e6-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="fd3e6-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="fd3e6-107">Limitations and Restrictions</span></span>  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="fd3e6-108">não podem ser modificados para serem procedimentos armazenados CLR e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="fd3e6-108">stored procedures cannot be modified to be CLR stored procedures and vice versa.</span></span>  
  
 <span data-ttu-id="fd3e6-109">Se a definição de procedimento anterior foi criada com WITH ENCRYPTION ou WITH RECOMPILE, essas opções estarão habilitadas somente se tiverem sido incluídas na instrução ALTER PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="fd3e6-109">If the previous procedure definition was created using WITH ENCRYPTION or WITH RECOMPILE, these options are enabled only if they are included in the ALTER PROCEDURE statement.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fd3e6-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="fd3e6-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fd3e6-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="fd3e6-111">Permissions</span></span>  
 <span data-ttu-id="fd3e6-112">Requer a permissão ALTER PROCEDURE no procedimento.</span><span class="sxs-lookup"><span data-stu-id="fd3e6-112">Requires ALTER PROCEDURE permission on the procedure.</span></span>  
  
##  <a name="how-to-modify-a-stored-procedure"></a><a name="Procedures"></a> <span data-ttu-id="fd3e6-113">Como modificar um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="fd3e6-113">How to Modify a Stored Procedure</span></span>  
 <span data-ttu-id="fd3e6-114">Você pode usar uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="fd3e6-114">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="fd3e6-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fd3e6-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="fd3e6-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fd3e6-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="fd3e6-117">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fd3e6-117">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="fd3e6-118">**Para modificar um procedimento no Management Studio**</span><span class="sxs-lookup"><span data-stu-id="fd3e6-118">**To modify a procedure in Management Studio**</span></span>  
  
1.  <span data-ttu-id="fd3e6-119">No Pesquisador de Objetos, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="fd3e6-119">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="fd3e6-120">Expanda **Bancos de Dados**, expanda o banco de dados ao qual pertence o procedimento e expanda **Programação**.</span><span class="sxs-lookup"><span data-stu-id="fd3e6-120">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="fd3e6-121">Expanda **Procedimentos Armazenados**, clique com o botão direito do mouse no procedimento a modificar e clique em **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="fd3e6-121">Expand **Stored Procedures**, right-click the procedure to modify, and then click **Modify**.</span></span>  
  
4.  <span data-ttu-id="fd3e6-122">Modifique o texto do procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="fd3e6-122">Modify the text of the stored procedure.</span></span>  
  
5.  <span data-ttu-id="fd3e6-123">Para testar a sintaxe, no menu **Consulta** , clique em **Analisar**.</span><span class="sxs-lookup"><span data-stu-id="fd3e6-123">To test the syntax, on the **Query** menu, click **Parse**.</span></span>  
  
6.  <span data-ttu-id="fd3e6-124">Para salvar as modificações na definição do procedimento, no menu **Consulta** , clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="fd3e6-124">To save the modifications to the procedure definition, on the **Query** menu, click **Execute**.</span></span>  
  
7.  <span data-ttu-id="fd3e6-125">Para salvar a definição do procedimento atualizada, como um script [!INCLUDE[tsql](../../includes/tsql-md.md)] , no menu **Arquivo** , clique em **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="fd3e6-125">To save the updated procedure definition as a [!INCLUDE[tsql](../../includes/tsql-md.md)] script, on the **File** menu, click **Save As**.</span></span> <span data-ttu-id="fd3e6-126">Aceite o nome de arquivo ou substitua-o por um nome novo e, então, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fd3e6-126">Accept the file name or replace it with a new name, and then click **Save**.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fd3e6-127">Valide todas as entradas de usuário.</span><span class="sxs-lookup"><span data-stu-id="fd3e6-127">Validate all user input.</span></span> <span data-ttu-id="fd3e6-128">Não concatene a entrada de usuário antes de validá-la.</span><span class="sxs-lookup"><span data-stu-id="fd3e6-128">Do not concatenate user input before you validate it.</span></span> <span data-ttu-id="fd3e6-129">Nunca execute um comando construído por uma entrada de usuário inválida.</span><span class="sxs-lookup"><span data-stu-id="fd3e6-129">Never execute a command constructed from unvalidated user input.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fd3e6-130">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fd3e6-130">Using Transact-SQL</span></span>  
 <span data-ttu-id="fd3e6-131">**Para modificar um procedimento no Editor de Consultas**</span><span class="sxs-lookup"><span data-stu-id="fd3e6-131">**To modify a procedure in Query Editor**</span></span>  
  
1.  <span data-ttu-id="fd3e6-132">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="fd3e6-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="fd3e6-133">Expanda **Bancos de Dados**e o banco de dados ao qual o procedimento pertence.</span><span class="sxs-lookup"><span data-stu-id="fd3e6-133">Expand **Databases**, expand the database in which the procedure belongs.</span></span> <span data-ttu-id="fd3e6-134">Ou, na barra de ferramentas, selecione o banco de dados na lista de bancos de dados disponíveis.</span><span class="sxs-lookup"><span data-stu-id="fd3e6-134">Or, from the tool bar, select the database from the list of available databases.</span></span> <span data-ttu-id="fd3e6-135">Neste exemplo, selecione o banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fd3e6-135">For this example, select the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
3.  <span data-ttu-id="fd3e6-136">No menu **Arquivo** , clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="fd3e6-136">On the **File** menu, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="fd3e6-137">Copie e cole o exemplo a seguir no editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="fd3e6-137">Copy and paste the following example into the query editor.</span></span> <span data-ttu-id="fd3e6-138">O exemplo cria o procedimento `uspVendorAllInfo` , que retorna os nomes de todos os fornecedores no banco de dados [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] , os produtos que eles fornecem, suas classificações de crédito e sua disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="fd3e6-138">The example creates the `uspVendorAllInfo` procedure, which returns the names of all the vendors in the [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] database, the products they supply, their credit ratings, and their availability.</span></span>  
  
    ```  
  
    IF OBJECT_ID ( 'Purchasing.uspVendorAllInfo', 'P' ) IS NOT NULL   
        DROP PROCEDURE Purchasing.uspVendorAllInfo;  
    GO  
    CREATE PROCEDURE Purchasing.uspVendorAllInfo  
    WITH EXECUTE AS CALLER  
    AS  
        SET NOCOUNT ON;  
        SELECT v.Name AS Vendor, p.Name AS 'Product name',   
          v.CreditRating AS 'Rating',   
          v.ActiveFlag AS Availability  
        FROM Purchasing.Vendor v   
        INNER JOIN Purchasing.ProductVendor pv  
          ON v.BusinessEntityID = pv.BusinessEntityID   
        INNER JOIN Production.Product p  
          ON pv.ProductID = p.ProductID   
        ORDER BY v.Name ASC;  
    GO  
  
    ```  
  
5.  <span data-ttu-id="fd3e6-139">No menu **Arquivo** , clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="fd3e6-139">On the **File** menu, click **New Query**.</span></span>  
  
6.  <span data-ttu-id="fd3e6-140">Copie e cole o exemplo a seguir no editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="fd3e6-140">Copy and paste the following example into the query editor.</span></span> <span data-ttu-id="fd3e6-141">O exemplo modifica o procedimento `uspVendorAllInfo` .</span><span class="sxs-lookup"><span data-stu-id="fd3e6-141">The example modifies the `uspVendorAllInfo` procedure.</span></span> <span data-ttu-id="fd3e6-142">A cláusula EXECUTE AS CALLER é removida e o corpo do procedimento é modificado para retornar apenas os fornecedores que fornecem o produto especificado.</span><span class="sxs-lookup"><span data-stu-id="fd3e6-142">The EXECUTE AS CALLER clause is removed and the body of the procedure is modified to return only those vendors that supply the specified product.</span></span> <span data-ttu-id="fd3e6-143">As funções `LEFT` e `CASE` personalizam a aparência do conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="fd3e6-143">The `LEFT` and `CASE` functions customize the appearance of the result set.</span></span>  
  
    ```  
    ALTER PROCEDURE Purchasing.uspVendorAllInfo  
        @Product varchar(25)   
    AS  
        SET NOCOUNT ON;  
        SELECT LEFT(v.Name, 25) AS Vendor, LEFT(p.Name, 25) AS 'Product name',   
        'Rating' = CASE v.CreditRating   
            WHEN 1 THEN 'Superior'  
            WHEN 2 THEN 'Excellent'  
            WHEN 3 THEN 'Above average'  
            WHEN 4 THEN 'Average'  
            WHEN 5 THEN 'Below average'  
            ELSE 'No rating'  
            END  
        , Availability = CASE v.ActiveFlag  
            WHEN 1 THEN 'Yes'  
            ELSE 'No'  
            END  
        FROM Purchasing.Vendor AS v   
        INNER JOIN Purchasing.ProductVendor AS pv  
          ON v.BusinessEntityID = pv.BusinessEntityID   
        INNER JOIN Production.Product AS p   
          ON pv.ProductID = p.ProductID   
        WHERE p.Name LIKE @Product  
        ORDER BY v.Name ASC;  
    GO  
  
    ```  
  
7.  <span data-ttu-id="fd3e6-144">Para salvar as modificações na definição do procedimento, no menu **Consulta** , clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="fd3e6-144">To save the modifications to the procedure definition, on the **Query** menu, click **Execute**.</span></span>  
  
8.  <span data-ttu-id="fd3e6-145">Para salvar a definição do procedimento atualizada, como um script [!INCLUDE[tsql](../../includes/tsql-md.md)] , no menu **Arquivo** , clique em **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="fd3e6-145">To save the updated procedure definition as a [!INCLUDE[tsql](../../includes/tsql-md.md)] script, on the **File** menu, click **Save As**.</span></span> <span data-ttu-id="fd3e6-146">Aceite o nome de arquivo ou substitua-o por um nome novo e, então, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fd3e6-146">Accept the file name or replace it with a new name, and then click **Save**.</span></span>  
  
9. <span data-ttu-id="fd3e6-147">Para executar o procedimento armazenado modificado, execute o exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="fd3e6-147">To run the modified stored procedure, execute the following example.</span></span>  
  
    ```  
    EXEC Purchasing.uspVendorAllInfo N'LL Crankarm';  
    GO  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="fd3e6-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fd3e6-148">See Also</span></span>  
 [<span data-ttu-id="fd3e6-149">ALTER PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fd3e6-149">ALTER PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-procedure-transact-sql)  
  
  
