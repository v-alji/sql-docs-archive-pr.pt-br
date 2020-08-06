---
title: Excluir funções definidas pelo usuário | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: db1d668a-23b7-4757-a9c5-1bd848ba7f6d
author: rothja
ms.author: jroth
ms.openlocfilehash: e5f6b2b306c4fe8db08b088d9607cfb19ab0f25e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582848"
---
# <a name="delete-user-defined-functions"></a><span data-ttu-id="7c900-102">Excluir funções definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="7c900-102">Delete User-defined Functions</span></span>
  <span data-ttu-id="7c900-103">Você pode excluir (remover) funções definidas pelo usuário no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c900-103">You can delete (drop) user-defined functions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
 <span data-ttu-id="7c900-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="7c900-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7c900-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="7c900-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7c900-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="7c900-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="7c900-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="7c900-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7c900-108">**Para excluir uma função definida pelo usuário, usando:**</span><span class="sxs-lookup"><span data-stu-id="7c900-108">**To delete a user-defined function, using:**</span></span>  
  
     [<span data-ttu-id="7c900-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7c900-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7c900-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7c900-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7c900-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="7c900-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="7c900-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="7c900-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="7c900-113">Você não poderá excluir a função se houver funções Transact-SQL ou exibições no banco de dados que referenciem essa função e forem criadas usando SCHEMABINDING, ou se houver colunas computadas, restrições CHECK ou DEFAULT que referenciem a função.</span><span class="sxs-lookup"><span data-stu-id="7c900-113">You will not be able to delete the function if there are Transact-SQL functions or views in the database that reference this function and were created by using SCHEMABINDING, or if there are computed columns, CHECK constraints, or DEFAULT constraints that reference the function.</span></span>  
  
-   <span data-ttu-id="7c900-114">Você não poderá excluir a função se houver colunas computadas que referenciem essa função e tenham sido indexadas.</span><span class="sxs-lookup"><span data-stu-id="7c900-114">You will not be able to delete the function if there are computed columns that reference this function and have been indexed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7c900-115">Segurança</span><span class="sxs-lookup"><span data-stu-id="7c900-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7c900-116">Permissões</span><span class="sxs-lookup"><span data-stu-id="7c900-116">Permissions</span></span>  
 <span data-ttu-id="7c900-117">Requer permissão ALTER no esquema ao qual a função pertence ou permissão CONTROL na função.</span><span class="sxs-lookup"><span data-stu-id="7c900-117">Requires ALTER permission on the schema to which the function belongs, or CONTROL permission on the function.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7c900-118">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7c900-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-user-defined-function"></a><span data-ttu-id="7c900-119">Para excluir uma função definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="7c900-119">To delete a user-defined function</span></span>  
  
1.  <span data-ttu-id="7c900-120">Clique no sinal de mais ao lado do banco de dados que contém a função que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="7c900-120">Click on the plus sign next to the database that contains the function you wish to modify.</span></span>  
  
2.  <span data-ttu-id="7c900-121">Clique no sinal de mais ao lado da pasta **Programação** .</span><span class="sxs-lookup"><span data-stu-id="7c900-121">Click on the plus sign next to the **Programmability** folder.</span></span>  
  
3.  <span data-ttu-id="7c900-122">Clique no sinal de mais ao lado da pasta que contém a função que você deseja modificar:</span><span class="sxs-lookup"><span data-stu-id="7c900-122">Click the plus sign next to the folder that contains the function you wish to modify:</span></span>  
  
    -   <span data-ttu-id="7c900-123">Table-valued Function</span><span class="sxs-lookup"><span data-stu-id="7c900-123">Table-valued Function</span></span>  
  
    -   <span data-ttu-id="7c900-124">Função de valor escalar</span><span class="sxs-lookup"><span data-stu-id="7c900-124">Scalar-valued Function</span></span>  
  
    -   <span data-ttu-id="7c900-125">Função de agregação</span><span class="sxs-lookup"><span data-stu-id="7c900-125">Aggregate Function</span></span>  
  
4.  <span data-ttu-id="7c900-126">Clique com o botão direito do mouse na função a ser excluída e selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="7c900-126">Right-click the function you want to delete and select **Delete**.</span></span>  
  
5.  <span data-ttu-id="7c900-127">Na caixa de diálogo **Excluir Objeto** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7c900-127">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="7c900-128">Clique em **Mostrar dependências** na caixa de diálogo **excluir objeto** para abrir a caixa de diálogo _function_name_**dependências** .</span><span class="sxs-lookup"><span data-stu-id="7c900-128">Click **Show Dependencies** in the **Delete Object** dialog box to open the _function_name_**Dependencies** dialog box.</span></span> <span data-ttu-id="7c900-129">Isso mostrará todos os objetos que dependem da função e todos os objetos dos quais a função depende.</span><span class="sxs-lookup"><span data-stu-id="7c900-129">This will show all of the objects that depend on the function and all of the objects on which the function depends.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7c900-130">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7c900-130">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-user-defined-function"></a><span data-ttu-id="7c900-131">Para excluir uma função definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="7c900-131">To delete a user-defined function</span></span>  
  
1.  <span data-ttu-id="7c900-132">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c900-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7c900-133">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="7c900-133">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7c900-134">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="7c900-134">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- creates function called "Sales.ufn_SalesByStore"  
    USE AdventureWorks2012;  
    GO  
    CREATE FUNCTION Sales.ufn_SalesByStore (@storeid int)  
    RETURNS TABLE  
    AS  
    RETURN   
    (  
        SELECT P.ProductID, P.Name, SUM(SD.LineTotal) AS 'Total'  
        FROM Production.Product AS P   
        JOIN Sales.SalesOrderDetail AS SD ON SD.ProductID = P.ProductID  
        JOIN Sales.SalesOrderHeader AS SH ON SH.SalesOrderID = SD.SalesOrderID  
        JOIN Sales.Customer AS C ON SH.CustomerID = C.CustomerID  
        WHERE C.StoreID = @storeid  
        GROUP BY P.ProductID, P.Name  
    );  
    GO  
    ```  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- determines if function exists in database  
    IF OBJECT_ID (N'Sales.fn_SalesByStore', N'IF') IS NOT NULL  
    -- deletes function  
        DROP FUNCTION Sales.fn_SalesByStore;  
    GO  
    ```  
  
 <span data-ttu-id="7c900-135">Para obter mais informações, consulte [DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7c900-135">For more information, see [DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql).</span></span>  
  
  
