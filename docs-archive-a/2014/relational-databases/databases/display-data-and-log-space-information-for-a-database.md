---
title: Exibir dados e informações de espaço de log para um banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], space
- status information [SQL Server], space
- displaying space information
- disk space [SQL Server], displaying
- databases [SQL Server], space used
- viewing space information
- space allocation [SQL Server], displaying
- data space [SQL Server]
ms.assetid: c7b99463-4bab-4e9b-9217-fcb0898dc757
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1beb8cdedbc2b72eadeeb350ee1c3b6d16218205
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685743"
---
# <a name="display-data-and-log-space-information-for-a-database"></a><span data-ttu-id="8dc02-102">Exibir dados e informações de espaço de log para um banco de dados</span><span class="sxs-lookup"><span data-stu-id="8dc02-102">Display Data and Log Space Information for a Database</span></span>
  <span data-ttu-id="8dc02-103">Este tópico descreve como exibir os dados e as informações de espaço de log para um banco de dados no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8dc02-103">This topic describes how to display the data and log space information for a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="8dc02-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="8dc02-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8dc02-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="8dc02-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8dc02-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="8dc02-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8dc02-107">**Para exibir dados e informações de espaço de log para um banco de dados, usando:**</span><span class="sxs-lookup"><span data-stu-id="8dc02-107">**To display data and log space information for a database, using:**</span></span>  
  
     [<span data-ttu-id="8dc02-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8dc02-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8dc02-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8dc02-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8dc02-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="8dc02-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8dc02-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="8dc02-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8dc02-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="8dc02-112">Permissions</span></span>  
 <span data-ttu-id="8dc02-113">A permissão para executar **sp_spaceused** é concedida à função **public** .</span><span class="sxs-lookup"><span data-stu-id="8dc02-113">Permission to execute **sp_spaceused** is granted to the **public** role.</span></span> <span data-ttu-id="8dc02-114">Somente os membros da função de banco de dados fixa **db_owner** podem especificar o parâmetro **@updateusage** .</span><span class="sxs-lookup"><span data-stu-id="8dc02-114">Only members of the **db_owner** fixed database role can specify the **@updateusage** parameter.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8dc02-115">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8dc02-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-display-data-and-log-space-information-for-a-database"></a><span data-ttu-id="8dc02-116">Para exibir dados e informações de espaço de log para um banco de dados</span><span class="sxs-lookup"><span data-stu-id="8dc02-116">To display data and log space information for a database</span></span>  
  
1.  <span data-ttu-id="8dc02-117">No Pesquisador de Objetos, conecte-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="8dc02-117">In Object Explorer, connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="8dc02-118">Expanda os **Bancos de dados**.</span><span class="sxs-lookup"><span data-stu-id="8dc02-118">Expand **Databases**.</span></span>  
  
3.  <span data-ttu-id="8dc02-119">Clique com o botão direito do mouse em um banco de dados, aponte para **Relatórios**, aponte para **Relatórios Padrão**e clique em **Uso do Disco**.</span><span class="sxs-lookup"><span data-stu-id="8dc02-119">Right-click a database, point to **Reports**, point to **Standard Reports,**, and then click **Disk Usage**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8dc02-120">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8dc02-120">Using Transact-SQL</span></span>  
  
#### <a name="to-display-data-and-log-space-information-for-a-database-by-using-sp_spaceused"></a><span data-ttu-id="8dc02-121">Para exibir dados e informações de espaço de log para um banco de dados usando sp_spaceused</span><span class="sxs-lookup"><span data-stu-id="8dc02-121">To display data and log space information for a database by using sp_spaceused</span></span>  
  
1.  <span data-ttu-id="8dc02-122">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8dc02-122">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8dc02-123">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="8dc02-123">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8dc02-124">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="8dc02-124">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="8dc02-125">Este exemplo usa o procedimento armazenado de sistema [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) para relatar informações de espaço em disco para a tabela `Vendor` e seus índices.</span><span class="sxs-lookup"><span data-stu-id="8dc02-125">This example uses the [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) system stored procedure to report disk space information for the `Vendor` table and its indexes.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_spaceused N'Purchasing.Vendor';  
GO  
```  
  
#### <a name="to-display-data-and-log-space-information-for-a-database-by-querying-sysdatabase_files"></a><span data-ttu-id="8dc02-126">Para exibir dados e informações de espaço de log para um banco de dados consultando sys.database_files</span><span class="sxs-lookup"><span data-stu-id="8dc02-126">To display data and log space information for a database by querying sys.database_files</span></span>  
  
1.  <span data-ttu-id="8dc02-127">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8dc02-127">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8dc02-128">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="8dc02-128">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8dc02-129">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="8dc02-129">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="8dc02-130">Este exemplo consulta a exibição de catálogo [sys.database_files](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) para retornar informações específicas sobre os dados e arquivos de log no banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8dc02-130">This example queries the [sys.database_files](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) catalog view to return specific information about the data and log files in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT file_id, name, type_desc, physical_name, size, max_size  
FROM sys.database_files ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="8dc02-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8dc02-131">See Also</span></span>  
 <span data-ttu-id="8dc02-132">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8dc02-132">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 <span data-ttu-id="8dc02-133">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8dc02-133">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span></span>  
 <span data-ttu-id="8dc02-134">[sp_spaceused &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8dc02-134">[sp_spaceused &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) </span></span>  
 <span data-ttu-id="8dc02-135">[Adicionar arquivos de dados ou de log a um banco de dados](add-data-or-log-files-to-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="8dc02-135">[Add Data or Log Files to a Database](add-data-or-log-files-to-a-database.md) </span></span>  
 [<span data-ttu-id="8dc02-136">Excluir arquivos de dados ou de log de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="8dc02-136">Delete Data or Log Files from a Database</span></span>](delete-data-or-log-files-from-a-database.md)  
  
  
