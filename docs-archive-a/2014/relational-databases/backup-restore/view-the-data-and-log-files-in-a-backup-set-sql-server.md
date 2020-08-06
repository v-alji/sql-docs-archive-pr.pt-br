---
title: Exibir os dados e arquivos de log em um conjunto de backup (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- database backups [SQL Server], viewing backup sets
- viewing backup set information
- backup sets [SQL Server], viewing files in
- displaying backup set information
- transaction log backups [SQL Server], viewing backup sets
- backing up [SQL Server], viewing backup sets
ms.assetid: abb6420c-f809-426e-aeb4-d0a74989cf39
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7dbcb14a658b49aba6f5f2ebe3425a2ab5759efa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681704"
---
# <a name="view-the-data-and-log-files-in-a-backup-set-sql-server"></a><span data-ttu-id="d98a1-102">Exibir os dados e arquivos de log em um conjunto de backup (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d98a1-102">View the Data and Log Files in a Backup Set (SQL Server)</span></span>
  <span data-ttu-id="d98a1-103">Este tópico descreve como exibir os arquivos de dados e logs em um conjunto de backup no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d98a1-103">This topic describes how to view the data and log files in a backup set in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="d98a1-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="d98a1-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d98a1-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="d98a1-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d98a1-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="d98a1-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d98a1-107">**Para exibir os dados e arquivos de log em um conjunto de backup, usando:**</span><span class="sxs-lookup"><span data-stu-id="d98a1-107">**To view the data and log files in a backup set, using:**</span></span>  
  
     [<span data-ttu-id="d98a1-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d98a1-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d98a1-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d98a1-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d98a1-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="d98a1-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d98a1-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="d98a1-111">Security</span></span>  
 <span data-ttu-id="d98a1-112">Para obter informações sobre segurança, veja [RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="d98a1-112">For information about security, see [RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql)</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d98a1-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="d98a1-113">Permissions</span></span>  
 <span data-ttu-id="d98a1-114">No [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] e em versões posteriores, a obtenção de informações sobre um conjunto ou dispositivo de backup exige a permissão CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="d98a1-114">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions, obtaining information about a backup set or backup device requires CREATE DATABASE permission.</span></span> <span data-ttu-id="d98a1-115">Para obter mais informações, veja [GRANT Database Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d98a1-115">For more information, see [GRANT Database Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d98a1-116">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d98a1-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-data-and-log-files-in-a-backup-set"></a><span data-ttu-id="d98a1-117">Para exibir os dados e arquivos de log em um conjunto de backup</span><span class="sxs-lookup"><span data-stu-id="d98a1-117">To view the data and log files in a backup set</span></span>  
  
1.  <span data-ttu-id="d98a1-118">Depois de se conectar à instância apropriada do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], em Pesquisador de Objetos, clique no nome do servidor para expandir a árvore do servidor.</span><span class="sxs-lookup"><span data-stu-id="d98a1-118">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="d98a1-119">Expanda **Bancos de Dados**e, dependendo do banco de dados, selecione um banco de dados de usuário ou expanda **Bancos de Dados do Sistema** e selecione um banco de dados do sistema.</span><span class="sxs-lookup"><span data-stu-id="d98a1-119">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="d98a1-120">Clique com o botão direito do mouse no banco de dados e clique em **Propriedades**, o que abrirá a caixa de diálogo **Propriedades do Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="d98a1-120">Right-click the database, and then click **Properties**, which opens the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="d98a1-121">No painel **Selecionar uma Página** , clique em **Arquivos**.</span><span class="sxs-lookup"><span data-stu-id="d98a1-121">In the **Select a Page** pane, click **Files**.</span></span>  
  
5.  <span data-ttu-id="d98a1-122">Procure na grade **Arquivos de banco de dados** para obter uma lista dos dados e arquivos de log e suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="d98a1-122">Look in the **Database files** grid for a list of the data and log files and their properties.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d98a1-123">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d98a1-123">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-data-and-log-files-in-a-backup-set"></a><span data-ttu-id="d98a1-124">Para exibir os dados e arquivos de log em um conjunto de backup</span><span class="sxs-lookup"><span data-stu-id="d98a1-124">To view the data and log files in a backup set</span></span>  
  
1.  <span data-ttu-id="d98a1-125">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d98a1-125">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d98a1-126">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="d98a1-126">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d98a1-127">Use a instrução [RESTORE FILELISTONLY](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="d98a1-127">Use the [RESTORE FILELISTONLY](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) statement.</span></span> <span data-ttu-id="d98a1-128">Este exemplo retorna informações sobre o segundo conjunto de backup (`FILE=2`) no dispositivo de backup do `AdventureWorksBackups` .</span><span class="sxs-lookup"><span data-stu-id="d98a1-128">This example returns information about the second backup set (`FILE=2`) on the `AdventureWorksBackups` backup device.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
RESTORE FILELISTONLY FROM AdventureWorksBackups   
   WITH FILE=2;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="d98a1-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d98a1-129">See Also</span></span>  
 <span data-ttu-id="d98a1-130">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d98a1-130">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span></span>  
 <span data-ttu-id="d98a1-131">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d98a1-131">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span></span>  
 <span data-ttu-id="d98a1-132">[conjunto de backup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d98a1-132">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="d98a1-133">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d98a1-133">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span></span>  
 <span data-ttu-id="d98a1-134">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d98a1-134">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span></span>  
 [<span data-ttu-id="d98a1-135">Dispositivos de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d98a1-135">Backup Devices &#40;SQL Server&#41;</span></span>](backup-devices-sql-server.md)  
  
  
