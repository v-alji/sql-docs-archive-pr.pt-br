---
title: Exibir informações de ordenação | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- collations [SQL Server], view
ms.assetid: 1338b4ea-7142-44bc-a3b9-44e54431405f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 995e559cfd7ca871f5abd90751f2f79167bdf76f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583636"
---
# <a name="view-collation-information"></a><span data-ttu-id="c0ed5-102">Exibir informações de ordenação</span><span class="sxs-lookup"><span data-stu-id="c0ed5-102">View Collation Information</span></span>
    
##  <a name="you-can-view-the-collation-of-a-server-database-or-column-in-ssmanstudiofull-using-object-explorer-menu-options-or-by-using-tsql"></a><a name="Top"></a> <span data-ttu-id="c0ed5-103">Você pode exibir a ordenação de um servidor, banco de dados ou coluna no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] usando as opções de menu do Pesquisador de Objetos ou usando o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0ed5-103">You can view the collation of a server, database, or column in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] using Object Explorer menu options or by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
##  <a name="how-to-view-a-collation-setting"></a><a name="Procedures"></a> <span data-ttu-id="c0ed5-104">Como exibir uma configuração de ordenação</span><span class="sxs-lookup"><span data-stu-id="c0ed5-104">How to View a Collation Setting</span></span>  
 <span data-ttu-id="c0ed5-105">Você pode usar uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="c0ed5-105">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="c0ed5-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c0ed5-106">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="c0ed5-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c0ed5-107">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c0ed5-108">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c0ed5-108">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="c0ed5-109">**Para exibir uma configuração de ordenação para um servidor (instância do SQL Server) no Pesquisador de Objetos**</span><span class="sxs-lookup"><span data-stu-id="c0ed5-109">**To view a collation setting for a server (instance of SQL Server) in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="c0ed5-110">No Pesquisador de Objetos, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0ed5-110">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c0ed5-111">Clique com o botão direito do mouse na instância e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="c0ed5-111">Right-click the instance and select **Properties**.</span></span>  
  
 <span data-ttu-id="c0ed5-112">**Para exibir uma configuração de ordenação para um banco de dados no Pesquisador de Objetos**</span><span class="sxs-lookup"><span data-stu-id="c0ed5-112">**To view a collation setting for a database in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="c0ed5-113">No Pesquisador de Objetos, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="c0ed5-113">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="c0ed5-114">Expanda **Banco de Dados**, clique com o botão direito do mouse no banco de dados e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="c0ed5-114">Expand **Databases**, right-click the database and select **Properties**.</span></span>  
  
 <span data-ttu-id="c0ed5-115">**Para exibir uma configuração de ordenação para uma coluna no Pesquisador de Objetos**</span><span class="sxs-lookup"><span data-stu-id="c0ed5-115">**To view a collation setting for a column in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="c0ed5-116">No Pesquisador de Objetos, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="c0ed5-116">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="c0ed5-117">Expanda **Bancos de Dados**, expanda o banco de dados e, por fim, expanda **Tabelas**.</span><span class="sxs-lookup"><span data-stu-id="c0ed5-117">Expand **Databases**, expand the database and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="c0ed5-118">Expanda a tabela que contém a coluna e expanda **Colunas**.</span><span class="sxs-lookup"><span data-stu-id="c0ed5-118">Expand the table that contains the column and then expand **Columns**.</span></span>  
  
4.  <span data-ttu-id="c0ed5-119">Clique com o botão direito do mouse na coluna e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="c0ed5-119">Right-click the column and select **Properties**.</span></span> <span data-ttu-id="c0ed5-120">Se a propriedade de ordenação estiver vazia, a coluna não será um tipo de dados de caractere.</span><span class="sxs-lookup"><span data-stu-id="c0ed5-120">If the collation property is empty, the column is not a character data type.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c0ed5-121">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c0ed5-121">Using Transact-SQL</span></span>  
 <span data-ttu-id="c0ed5-122">**Para exibir a configuração de ordenação de um servidor**</span><span class="sxs-lookup"><span data-stu-id="c0ed5-122">**To view the collation setting of a server**</span></span>  
  
1.  <span data-ttu-id="c0ed5-123">No Pesquisador de Objetos, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] e, na barra de ferramentas, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="c0ed5-123">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and on the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="c0ed5-124">Na janela de consulta, insira a instrução a seguir que usa a função de sistema SERVERPROPERTY.</span><span class="sxs-lookup"><span data-stu-id="c0ed5-124">In the query window, enter the following statement that uses the SERVERPROPERTY system function.</span></span>  
  
    ```  
    SELECT CONVERT (varchar, SERVERPROPERTY('collation'));  
    ```  
  
3.  <span data-ttu-id="c0ed5-125">Se desejar, você pode usar o procedimento armazenado de sistema sp_helpsort.</span><span class="sxs-lookup"><span data-stu-id="c0ed5-125">Alternatively, you can use the sp_helpsort system stored procedure.</span></span>  
  
    ```  
    EXECUTE sp_helpsort;  
    ```  
  
 <span data-ttu-id="c0ed5-126">**Para exibir todas as ordenações com suporte no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="c0ed5-126">**To view all collations supported by [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]**</span></span>  
  
1.  <span data-ttu-id="c0ed5-127">No Pesquisador de Objetos, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] e, na barra de ferramentas, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="c0ed5-127">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and on the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="c0ed5-128">Na janela de consulta, insira a instrução a seguir que usa a função de sistema SERVERPROPERTY.</span><span class="sxs-lookup"><span data-stu-id="c0ed5-128">In the query window, enter the following statement that uses the SERVERPROPERTY system function.</span></span>  
  
    ```  
    SELECT name, description FROM sys.fn_helpcollations();  
    ```  
  
 <span data-ttu-id="c0ed5-129">**Para exibir a configuração de ordenação de um banco de dados.**</span><span class="sxs-lookup"><span data-stu-id="c0ed5-129">**To view the collation setting of a database**</span></span>  
  
1.  <span data-ttu-id="c0ed5-130">No Pesquisador de Objetos, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] e, na barra de ferramentas, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="c0ed5-130">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and on the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="c0ed5-131">Na janela de consulta, insira a instrução a seguir que usa a exibição de catálogo de sistema do sys.databases.</span><span class="sxs-lookup"><span data-stu-id="c0ed5-131">In the query window, enter the following statement that uses the sys.databases system catalog view.</span></span>  
  
    ```  
    SELECT name, collation_name FROM sys.databases;  
    ```  
  
3.  <span data-ttu-id="c0ed5-132">Se desejar, você pode usar a função de sistema DATABASEPROPERTYEX.</span><span class="sxs-lookup"><span data-stu-id="c0ed5-132">Alternatively, you can use the DATABASEPROPERTYEX system function.</span></span>  
  
    ```  
    SELECT CONVERT (varchar, DATABASEPROPERTYEX('database_name','collation'));  
    ```  
  
 <span data-ttu-id="c0ed5-133">**Para exibir a configuração de ordenação de uma coluna**</span><span class="sxs-lookup"><span data-stu-id="c0ed5-133">**To view the collation setting of a column**</span></span>  
  
1.  <span data-ttu-id="c0ed5-134">No Pesquisador de Objetos, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] e, na barra de ferramentas, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="c0ed5-134">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and on the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="c0ed5-135">Na janela de consulta, insira a instrução a seguir que usa a exibição de catálogo de sistema sys.columns.</span><span class="sxs-lookup"><span data-stu-id="c0ed5-135">In the query window, enter the following statement that uses the sys.columns system catalog view.</span></span>  
  
    ```  
    SELECT name, collation_name FROM sys.columns WHERE name = N'<insert character data type column name>';  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c0ed5-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c0ed5-136">See Also</span></span>  
 <span data-ttu-id="c0ed5-137">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c0ed5-137">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span></span>  
 <span data-ttu-id="c0ed5-138">[sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c0ed5-138">[sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) </span></span>  
 <span data-ttu-id="c0ed5-139">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c0ed5-139">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 <span data-ttu-id="c0ed5-140">[sys.columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-columns-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c0ed5-140">[sys.columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-columns-transact-sql) </span></span>  
 <span data-ttu-id="c0ed5-141">[Precedência de ordenação &#40;Transact-SQL&#41;](/sql/t-sql/statements/collation-precedence-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c0ed5-141">[Collation Precedence &#40;Transact-SQL&#41;](/sql/t-sql/statements/collation-precedence-transact-sql) </span></span>  
 [<span data-ttu-id="c0ed5-142">sp_helpsort &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c0ed5-142">sp_helpsort &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-helpsort-transact-sql)  
  
  
