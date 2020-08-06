---
title: Exibir ou alterar as propriedades de um banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- displaying databases
- database viewing [SQL Server]
- databases [SQL Server], viewing
- viewing databases
ms.assetid: 9e8ac097-84b7-46c7-85e3-c1e79f94d747
author: stevestein
ms.author: sstein
ms.openlocfilehash: d6aee7503ca02d47575be4e8103641f61d9696d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685177"
---
# <a name="view-or-change-the-properties-of-a-database"></a><span data-ttu-id="e3571-102">Exibir ou alterar as propriedades de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="e3571-102">View or Change the Properties of a Database</span></span>
  <span data-ttu-id="e3571-103">Este tópico descreve como exibir ou alterar os propriedades de um banco de dados no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3571-103">This topic describes how to view or change the properties of a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="e3571-104">Depois de alterar uma propriedade de banco de dados, a modificação entra em vigor imediatamente.</span><span class="sxs-lookup"><span data-stu-id="e3571-104">After you change a database property, the modification takes effect immediately.</span></span>  
  
 <span data-ttu-id="e3571-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="e3571-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e3571-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="e3571-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e3571-107">Recomendações</span><span class="sxs-lookup"><span data-stu-id="e3571-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="e3571-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="e3571-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e3571-109">**Para exibir ou alterar as propriedades de um banco de dados usando:**</span><span class="sxs-lookup"><span data-stu-id="e3571-109">**To view or change the properties of a database, using:**</span></span>  
  
     [<span data-ttu-id="e3571-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e3571-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e3571-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e3571-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e3571-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="e3571-112">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="e3571-113">Recomendações</span><span class="sxs-lookup"><span data-stu-id="e3571-113">Recommendations</span></span>  
  
-   <span data-ttu-id="e3571-114">Quando AUTO_CLOSE for ON, algumas colunas da exibição de catálogo [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) e da função DATABASEPROPERTYEX retornarão NULL, pois o banco de dados não está disponível para recuperar os dados.</span><span class="sxs-lookup"><span data-stu-id="e3571-114">When AUTO_CLOSE is ON, some columns in the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view and DATABASEPROPERTYEX function will return NULL because the database is unavailable to retrieve the data.</span></span> <span data-ttu-id="e3571-115">Para resolver isso, execute uma instrução USE para abrir o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e3571-115">To resolve this, execute a USE statement to open the database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e3571-116">Segurança</span><span class="sxs-lookup"><span data-stu-id="e3571-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e3571-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="e3571-117">Permissions</span></span>  
 <span data-ttu-id="e3571-118">Requer a permissão ALTER no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e3571-118">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e3571-119">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e3571-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-the-properties-of-a-database"></a><span data-ttu-id="e3571-120">Para exibir ou alterar as propriedades de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="e3571-120">To view or change the properties of a database</span></span>  
  
1.  <span data-ttu-id="e3571-121">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="e3571-121">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="e3571-122">Expanda **Banco de Dados**, clique com o botão direito do mouse no banco de dados para exibi-lo e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="e3571-122">Expand **Databases**, right-click the database to view, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="e3571-123">Na caixa de diálogo **Propriedades do Banco de Dados** , selecione uma página para exibir as informações correspondentes.</span><span class="sxs-lookup"><span data-stu-id="e3571-123">In the **Database Properties** dialog box, select a page to view the corresponding information.</span></span> <span data-ttu-id="e3571-124">Por exemplo, selecione a página **Arquivos** para exibir os dados e as informações do arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="e3571-124">For example, select the **Files** page to view data and log file information.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e3571-125">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e3571-125">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-property-of-a-database-by-using-databasepropertyex"></a><span data-ttu-id="e3571-126">Para exibir uma propriedade de um banco de dados usando DATABASEPROPERTYEX</span><span class="sxs-lookup"><span data-stu-id="e3571-126">To view a property of a database by using DATABASEPROPERTYEX</span></span>  
  
1.  <span data-ttu-id="e3571-127">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3571-127">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e3571-128">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="e3571-128">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e3571-129">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="e3571-129">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="e3571-130">Este exemplo usa a função do sistema [DATABASEPROPERTYEX](/sql/t-sql/functions/databasepropertyex-transact-sql) para retornar o status da opção de banco de dados AUTO_SHRINK no banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e3571-130">This example uses the [DATABASEPROPERTYEX](/sql/t-sql/functions/databasepropertyex-transact-sql) system function to return the status of the AUTO_SHRINK database option in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="e3571-131">Um valor de retorno 1 significa que a opção está definida como ON e um valor de retorno 0 significa que a opção está definida como OFF.</span><span class="sxs-lookup"><span data-stu-id="e3571-131">A return value of 1 means that the option is set to ON, and a return value of 0 means that the option is set to OFF.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT DATABASEPROPERTYEX('AdventureWorks2012', 'IsAutoShrink');  
GO  
  
```  
  
#### <a name="to-view-the-properties-of-a-database-by-querying-sysdatabases"></a><span data-ttu-id="e3571-132">Para exibir as propriedades de um banco de dados consultando sys.databases</span><span class="sxs-lookup"><span data-stu-id="e3571-132">To view the properties of a database by querying sys.databases</span></span>  
  
1.  <span data-ttu-id="e3571-133">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3571-133">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e3571-134">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="e3571-134">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e3571-135">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="e3571-135">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="e3571-136">Este exemplo consulta a exibição de catálogo [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) para exibir várias propriedades do banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e3571-136">This example queries the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view to view several properties of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="e3571-137">Este exemplo retorna o número de identificação de banco de dados (`database_id`), se o banco de dados for somente leitura ou de leitura/gravação (`is_read_only`), a ordenação do banco de dados (`collation_name`) e o nível de compatibilidade do banco de dados (`compatibility_level`).</span><span class="sxs-lookup"><span data-stu-id="e3571-137">This example returns the database ID number (`database_id`), whether the database is read-only or read-write (`is_read_only`), the collation for the database (`collation_name`), and the database compatibility level (`compatibility_level`).</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT database_id, is_read_only, collation_name, compatibility_level  
FROM sys.databases WHERE name = 'AdventureWorks2012';  
GO  
  
```  
  
#### <a name="to-change-the-properties-of-a-database"></a><span data-ttu-id="e3571-138">Para alterar as propriedades de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="e3571-138">To change the properties of a database</span></span>  
  
1.  <span data-ttu-id="e3571-139">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3571-139">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e3571-140">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="e3571-140">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e3571-141">Copie e cole o exemplo a seguir na janela de consulta.</span><span class="sxs-lookup"><span data-stu-id="e3571-141">Copy and paste the following example into the query window.</span></span> <span data-ttu-id="e3571-142">O exemplo determina o estado de isolamento de instantâneo no banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , altera o estado da propriedade e verifique a alteração.</span><span class="sxs-lookup"><span data-stu-id="e3571-142">The example determines the state of snapshot isolation on the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, changes the state of the property, and then verifies the change.</span></span>  
  
     <span data-ttu-id="e3571-143">Para determinar o estado de isolamento de instantâneo, selecione a primeira instrução `SELECT` e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="e3571-143">To determine the state of snapshot isolation, select the first `SELECT` statement and click **Execute**.</span></span>  
  
     <span data-ttu-id="e3571-144">Para alterar o estado de isolamento de instantâneo, selecione a primeira instrução `ALTER DATABASE` e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="e3571-144">To change the state of snapshot isolation, select the `ALTER DATABASE` statement and click **Execute**.</span></span>  
  
     <span data-ttu-id="e3571-145">Para verificar a alteração, selecione a segunda instrução `SELECT` e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="e3571-145">To verify the change, select the second `SELECT` statement, and click **Execute**.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase9](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase9)]  
  
## <a name="see-also"></a><span data-ttu-id="e3571-146">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e3571-146">See Also</span></span>  
 <span data-ttu-id="e3571-147">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e3571-147">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 <span data-ttu-id="e3571-148">[ALTER DATABASE SET HADR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) </span><span class="sxs-lookup"><span data-stu-id="e3571-148">[ALTER DATABASE SET HADR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) </span></span>  
 <span data-ttu-id="e3571-149">[Opções ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options) </span><span class="sxs-lookup"><span data-stu-id="e3571-149">[ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options) </span></span>  
 <span data-ttu-id="e3571-150">[Espelhamento de banco de dados ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="e3571-150">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="e3571-151">[Nível de compatibilidade de ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) </span><span class="sxs-lookup"><span data-stu-id="e3571-151">[ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) </span></span>  
 [<span data-ttu-id="e3571-152">Opções de arquivo e grupos de arquivos ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e3571-152">ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options)  
  
  
