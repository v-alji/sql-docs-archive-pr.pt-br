---
title: Fazer backup e restaurar índices e catálogos de texto completo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- full-text indexes [SQL Server], backing up
- full-text search [SQL Server], back up and restore
- recovery [full-text search]
- backups [SQL Server], full-text indexes
- full-text indexes [SQL Server], restoring
- restore operations [full-text search]
ms.assetid: 6a4080d9-e43f-4b7b-a1da-bebf654c1194
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6c0df49c03325da375427c6566799f374fcc9dd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582392"
---
# <a name="back-up-and-restore-full-text-catalogs-and-indexes"></a><span data-ttu-id="0624b-102">Fazer backup e restaurar índices e catálogos de texto completo</span><span class="sxs-lookup"><span data-stu-id="0624b-102">Back Up and Restore Full-Text Catalogs and Indexes</span></span>
  <span data-ttu-id="0624b-103">Este tópico explica como fazer backup e restauração de índices de texto completo criados no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0624b-103">This topic explains how to back up and restore full-text indexes created in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0624b-104">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], o catálogo de texto completo é um conceito lógico e não reside em um grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="0624b-104">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the full-text catalog is a logical concept and does not reside in a filegroup.</span></span> <span data-ttu-id="0624b-105">Por isso, para fazer backup de um catálogo de texto completo no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], é necessário identificar cada grupo de arquivos que contém um índice de texto completo do catálogo e fazer backup de cada um deles.</span><span class="sxs-lookup"><span data-stu-id="0624b-105">Therefore, to back up a full-text catalog in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must identify every filegroup that contains a full-text index that belongs to the catalog.</span></span> <span data-ttu-id="0624b-106">Depois, faça backup desses grupos de arquivos, um por um.</span><span class="sxs-lookup"><span data-stu-id="0624b-106">Then you must back up those filegroups, one by one.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0624b-107">É possível importar catálogos de texto completo durante a atualização de um banco de dados do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0624b-107">It is possible to import full-text catalogs when upgrading a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] database.</span></span> <span data-ttu-id="0624b-108">Cada catálogo de texto completo importado é um arquivo de banco de dados em seu próprio grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="0624b-108">Each imported full-text catalog is a database file in its own filegroup.</span></span> <span data-ttu-id="0624b-109">Para fazer backup de um catálogo importado, basta fazer backup do grupo de arquivos correspondente.</span><span class="sxs-lookup"><span data-stu-id="0624b-109">To back up an imported catalog, simply back up its filegroup.</span></span> <span data-ttu-id="0624b-110">Para obter mais informações, veja [Fazendo backup e restaurando catálogos de texto completo](https://go.microsoft.com/fwlink/?LinkID=121052), nos Manuais Online do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0624b-110">For more information, see [Backing Up and Restoring Full-Text Catalogs](https://go.microsoft.com/fwlink/?LinkID=121052), in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Books Online.</span></span>  
  
##  <a name="backing-up-the-full-text-indexes-of-a-full-text-catalog"></a><a name="backingup"></a> <span data-ttu-id="0624b-111">Fazendo backup dos índices de texto completo de um catálogo de texto completo</span><span class="sxs-lookup"><span data-stu-id="0624b-111">Backing Up the Full-Text Indexes of a Full-Text Catalog</span></span>  
  
###  <a name="finding-the-full-text-indexes-of-a-full-text-catalog"></a><a name="Find_FTIs_of_a_Catalog"></a> <span data-ttu-id="0624b-112">Localizando os índices de texto completo de um catálogo de texto completo</span><span class="sxs-lookup"><span data-stu-id="0624b-112">Finding the Full-Text Indexes of a Full-Text Catalog</span></span>  
 <span data-ttu-id="0624b-113">É possível recuperar as propriedades dos índices de texto completo usando a seguinte instrução [SELECT](/sql/t-sql/queries/select-transact-sql) , que seleciona colunas das exibições do catálogo [sys.fulltext_indexes](/sql/relational-databases/system-catalog-views/sys-fulltext-indexes-transact-sql) e [sys.fulltext_catalogs](/sql/relational-databases/system-catalog-views/sys-fulltext-catalogs-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="0624b-113">You can retrieve the properties of the full-text indexes by using the following [SELECT](/sql/t-sql/queries/select-transact-sql) statement, which selects columns from the [sys.fulltext_indexes](/sql/relational-databases/system-catalog-views/sys-fulltext-indexes-transact-sql) and [sys.fulltext_catalogs](/sql/relational-databases/system-catalog-views/sys-fulltext-catalogs-transact-sql) catalog views.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @TableID int;  
SET @TableID = (SELECT OBJECT_ID('AdventureWorks2012.Production.Product'));  
SELECT object_name(@TableID), i.is_enabled, i.change_tracking_state,   
   i.has_crawl_completed, i.crawl_type, c.name as fulltext_catalog_name   
   FROM sys.fulltext_indexes i, sys.fulltext_catalogs c   
   WHERE i.fulltext_catalog_id = c.fulltext_catalog_id;  
GO  
```  
  

  
###  <a name="finding-the-filegroup-or-file-that-contains-a-full-text-index"></a><a name="Find_FG_of_FTI"></a> <span data-ttu-id="0624b-114">Localizando o grupo de arquivos ou o arquivo que contém um índice de texto completo</span><span class="sxs-lookup"><span data-stu-id="0624b-114">Finding the Filegroup or File That Contains a Full-Text Index</span></span>  
 <span data-ttu-id="0624b-115">Quando criado, um índice de texto completo é colocado em um destes locais:</span><span class="sxs-lookup"><span data-stu-id="0624b-115">When a full-text index is created, it is placed in one of the following locations:</span></span>  
  
-   <span data-ttu-id="0624b-116">Um grupo de arquivos especificado pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="0624b-116">A user-specified filegroup.</span></span>  
  
-   <span data-ttu-id="0624b-117">O mesmo grupo de arquivos como tabela base ou exibição, para uma tabela não particionada.</span><span class="sxs-lookup"><span data-stu-id="0624b-117">The same filegroup as base table or view, for a nonpartitioned table.</span></span>  
  
-   <span data-ttu-id="0624b-118">O grupo de arquivos principal, para uma tabela particionada.</span><span class="sxs-lookup"><span data-stu-id="0624b-118">The primary filegroup, for a partitioned table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0624b-119">Para obter informações sobre como criar um índice de texto completo, veja [Criar e gerenciar índices de texto completo](create-and-manage-full-text-indexes.md) e [CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0624b-119">For information about creating a full-text index, see [Create and Manage Full-Text Indexes](create-and-manage-full-text-indexes.md) and [CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql).</span></span>  
  
 <span data-ttu-id="0624b-120">Para localizar o grupo de arquivos do índice de texto completo em uma tabela ou exibição, use a seguinte consulta, em que *object_name* corresponde ao nome da tabela ou exibição:</span><span class="sxs-lookup"><span data-stu-id="0624b-120">To find the filegroup of full-text index on a table or view, use the following query, where *object_name* is the name of the table or view:</span></span>  
  
```  
SELECT name FROM sys.filegroups f, sys.fulltext_indexes i   
   WHERE f.data_space_id = i.data_space_id   
      and i.object_id = object_id('object_name');  
GO  
  
```  
  

  
###  <a name="backing-up-the-filegroups-that-contain-full-text-indexes"></a><a name="Back_up_FTIs_of_FTC"></a> <span data-ttu-id="0624b-121">Fazendo backup dos grupos de arquivos que contêm índices de texto completo</span><span class="sxs-lookup"><span data-stu-id="0624b-121">Backing Up the Filegroups That Contain Full-Text Indexes</span></span>  
 <span data-ttu-id="0624b-122">Depois de localizar os grupos de arquivos que contêm os índices de um catálogo de texto completo, você precisa fazer backup de cada um dos grupos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="0624b-122">After you find the filegroups that contain the indexes of a full-text catalog, you need back up each of the filegroups.</span></span> <span data-ttu-id="0624b-123">Durante o processo de backup, catálogos de texto completo não podem ser descartados ou adicionados.</span><span class="sxs-lookup"><span data-stu-id="0624b-123">During the backup process, full-text catalogs may not be dropped or added.</span></span>  
  
 <span data-ttu-id="0624b-124">O primeiro backup de um grupo de arquivos deve ser um backup de arquivo completo.</span><span class="sxs-lookup"><span data-stu-id="0624b-124">The first backup of a filegroup must be a full file backup.</span></span> <span data-ttu-id="0624b-125">Depois de ter criado um backup de arquivo completo de um grupo de arquivos, você pode fazer backup somente das alterações feitas em um grupo de arquivos; para isso, crie uma série de um ou mais backups de arquivo diferenciais baseados no backup de arquivo completo.</span><span class="sxs-lookup"><span data-stu-id="0624b-125">After you have created a full file backup for a filegroup, you could back up only the changes in a filegroup by creating a series of one or more differential file backups that are based on the full file backup.</span></span>  
  
 <span data-ttu-id="0624b-126">**Para efetuar backup de arquivos e grupos de arquivos**</span><span class="sxs-lookup"><span data-stu-id="0624b-126">**To back up files and filegroups**</span></span>  
  
-   [<span data-ttu-id="0624b-127">Fazer backup de arquivos e de grupos de arquivos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0624b-127">Back Up Files and Filegroups &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-files-and-filegroups-sql-server.md)  
  
-   [<span data-ttu-id="0624b-128">BACKUP &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0624b-128">BACKUP &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/backup-transact-sql)  
  

  
##  <a name="restoring-a-full-text-index"></a><a name="Restore_FTI"></a> <span data-ttu-id="0624b-129">Restaurando um índice de texto completo</span><span class="sxs-lookup"><span data-stu-id="0624b-129">Restoring a Full-Text Index</span></span>  
 <span data-ttu-id="0624b-130">A restauração de um grupo de arquivos submetido a backup restaura os arquivos de índice de texto completo, bem como os demais arquivos do grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="0624b-130">Restoring a backed-up filegroup restores the full-text index files, as well as the other files in the filegroup.</span></span> <span data-ttu-id="0624b-131">Por padrão, o grupo de arquivos é restaurado no local do disco em que foi feito backup do grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="0624b-131">By default, the filegroup is restored to the disk location on which the filegroup was backed up.</span></span>  
  
 <span data-ttu-id="0624b-132">Se uma tabela indexada com texto completo estava online e uma operação de população estava sendo executada quando o backup foi criado, a população será retomada após a restauração.</span><span class="sxs-lookup"><span data-stu-id="0624b-132">If a full-text indexed table was online and a population was running when the backup was created, the population is resumed after the restore.</span></span>  
  
 <span data-ttu-id="0624b-133">**Para restaurar um grupo de arquivos**</span><span class="sxs-lookup"><span data-stu-id="0624b-133">**To restore a filegroup**</span></span>  
  
-   [<span data-ttu-id="0624b-134">Restaurar arquivos e grupos de arquivos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0624b-134">Restore Files and Filegroups &#40;SQL Server&#41;</span></span>](../backup-restore/restore-files-and-filegroups-sql-server.md)  
  
-   [<span data-ttu-id="0624b-135">Restaurar arquivos e grupos de arquivos sobre arquivos existentes &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0624b-135">Restore Files and Filegroups over Existing Files &#40;SQL Server&#41;</span></span>](../backup-restore/restore-files-and-filegroups-over-existing-files-sql-server.md)  
  
-   [<span data-ttu-id="0624b-136">Restaurar arquivos em um novo local &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0624b-136">Restore Files to a New Location &#40;SQL Server&#41;</span></span>](../backup-restore/restore-files-to-a-new-location-sql-server.md)  
  
-   [<span data-ttu-id="0624b-137">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0624b-137">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  

  
## <a name="see-also"></a><span data-ttu-id="0624b-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0624b-138">See Also</span></span>  
 <span data-ttu-id="0624b-139">[Gerenciar e monitorar a pesquisa de texto completo em uma instância do servidor](manage-and-monitor-full-text-search-for-a-server-instance.md) </span><span class="sxs-lookup"><span data-stu-id="0624b-139">[Manage and Monitor Full-Text Search for a Server Instance](manage-and-monitor-full-text-search-for-a-server-instance.md) </span></span>  
 [<span data-ttu-id="0624b-140">Atualizar pesquisa de texto completo</span><span class="sxs-lookup"><span data-stu-id="0624b-140">Upgrade Full-Text Search</span></span>](upgrade-full-text-search.md)  
  
  
