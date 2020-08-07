---
title: Exibir as dependências de uma tabela | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table dependencies [SQL Server]
- dependencies [SQL Server], tables
- displaying dependences
- viewing dependencies
ms.assetid: c4351ef5-e7d0-46e7-8367-88695e9974f8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 20f54b913124cdaa8a7dfeebac01ba070cc37d88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584070"
---
# <a name="view-the-dependencies-of-a-table"></a><span data-ttu-id="68657-102">Exibir as dependências de uma tabela</span><span class="sxs-lookup"><span data-stu-id="68657-102">View the Dependencies of a Table</span></span>
  <span data-ttu-id="68657-103">Você pode exibir as dependências de uma tabela no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="68657-103">You can view a table's dependencies in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="68657-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="68657-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="68657-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="68657-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="68657-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="68657-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="68657-107">**Para exibir as dependências de uma tabela usando:**</span><span class="sxs-lookup"><span data-stu-id="68657-107">**To view a table's dependencies, using:**</span></span>  
  
     [<span data-ttu-id="68657-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="68657-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="68657-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="68657-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="68657-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="68657-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="68657-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="68657-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="68657-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="68657-112">Permissions</span></span>  
 <span data-ttu-id="68657-113">Requer permissão VIEW DEFINITION no banco de dados e permissão SELECT em sys.sql_expression_dependencies para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="68657-113">Requires VIEW DEFINITION permission on the database and SELECT permission on sys.sql_expression_dependencies for the database.</span></span> <span data-ttu-id="68657-114">Por padrão, a permissão SELECT é concedida somente a membros da função de banco de dados fixa db_owner.</span><span class="sxs-lookup"><span data-stu-id="68657-114">By default, SELECT permission is granted only to members of the db_owner fixed database role.</span></span> <span data-ttu-id="68657-115">Quando são concedidas permissões SELECT e VIEW DEFINITION a outro usuário, o usuário autorizado pode exibir todas as dependências no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="68657-115">When SELECT and VIEW DEFINITION permissions are granted to another user, the grantee can view all dependencies in the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="68657-116">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="68657-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-dependencies-of-a-table"></a><span data-ttu-id="68657-117">Para visualizar as dependências de uma tabela</span><span class="sxs-lookup"><span data-stu-id="68657-117">To view the dependencies of a table</span></span>  
  
1.  <span data-ttu-id="68657-118">No **Pesquisador de Objetos**, expanda **Bancos de Dados**, expanda um banco de dados e, em seguida, expanda **Tabelas**.</span><span class="sxs-lookup"><span data-stu-id="68657-118">In **Object Explorer**, expand **Databases**, expand a database, and then expand **Tables**.</span></span>  
  
2.  <span data-ttu-id="68657-119">Clique com o botão direito do mouse em uma tabela e clique em **Exibir Dependências**.</span><span class="sxs-lookup"><span data-stu-id="68657-119">Right-click a table, and then click **View Dependencies**.</span></span>  
  
3.  <span data-ttu-id="68657-120">Na caixa de diálogo **Dependências do Objeto** _\<object name>_ , selecione **Objetos que dependem de** _\<object name>_ ou **Objetos dos quais** _\<object name>_ **depende**.</span><span class="sxs-lookup"><span data-stu-id="68657-120">In the **Object Dependencies**_\<object name>_ dialog box, select either **Objects that depend on** _\<object name>_, or **Objects on which**_\<object name>_**depends**.</span></span>  
  
4.  <span data-ttu-id="68657-121">Selecione um objeto na grade **Dependências** .</span><span class="sxs-lookup"><span data-stu-id="68657-121">Select an object in the **Dependencies** grid.</span></span> <span data-ttu-id="68657-122">O tipo de objeto (como “Gatilho” ou “Procedimento Armazenado”) aparece na caixa **Tipo** .</span><span class="sxs-lookup"><span data-stu-id="68657-122">The type of object (such as "Trigger" or "Stored Procedure"), appears in the **Type** box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="68657-123">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="68657-123">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-objects-that-depend-on-a-table"></a><span data-ttu-id="68657-124">Para exibir os objetos que dependem de uma tabela</span><span class="sxs-lookup"><span data-stu-id="68657-124">To view the objects that depend on a table</span></span>  
  
1.  <span data-ttu-id="68657-125">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="68657-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="68657-126">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="68657-126">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="68657-127">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="68657-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT * FROM sys.sql_expression_dependencies  
    WHERE referencing_id = OBJECT_ID(N'Production.vProductAndDescription');   
    GO  
  
    ```  
  
#### <a name="to-view-the-objects-on-which-a-table-depends"></a><span data-ttu-id="68657-128">Para exibir os objetos dos quais uma tabela depende</span><span class="sxs-lookup"><span data-stu-id="68657-128">To view the objects on which a table depends</span></span>  
  
1.  <span data-ttu-id="68657-129">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="68657-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="68657-130">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="68657-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="68657-131">O exemplo a seguir retorna os objetos que dependem da tabela `Production.Product`.</span><span class="sxs-lookup"><span data-stu-id="68657-131">The following example returns the objects that depend on the table `Production.Product`.</span></span> <span data-ttu-id="68657-132">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="68657-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    SELECT * FROM sys.sql_expression_dependencies  
    WHERE referenced_id = OBJECT_ID(N'Production.Product');   
    GO  
  
    ```  
  
 <span data-ttu-id="68657-133">Para obter mais informações, veja [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="68657-133">For additional information, see [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)</span></span>  
  
  
