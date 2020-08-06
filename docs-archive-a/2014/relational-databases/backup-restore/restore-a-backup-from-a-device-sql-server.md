---
title: Restaurar um backup de um dispositivo (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restoring databases [SQL Server], device restores
- backup devices [SQL Server], restoring from
- database restores [SQL Server], device restores
- devices [SQL Server]
ms.assetid: 6e139de7-7de2-4d18-9df0-beac31ba7ff1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 50d7f7b8e255aea470a1065df669c0cc3169a8dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679995"
---
# <a name="restore-a-backup-from-a-device-sql-server"></a><span data-ttu-id="85694-102">Restaurar um backup de um dispositivo (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="85694-102">Restore a Backup from a Device (SQL Server)</span></span>
  <span data-ttu-id="85694-103">Este tópico descreve como restaurar um backup de um dispositivo no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85694-103">This topic describes how to restore a backup from a device in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="85694-104">Para obter informações sobre SQL Server Backup para o serviço de armazenamento de BLOBs do Azure, consulte [SQL Server Backup e restauração com o serviço de armazenamento de BLOBs do Azure](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="85694-104">For information on SQL Server backup to the Azure Blob storage service, see, [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span></span>  
  
 <span data-ttu-id="85694-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="85694-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="85694-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="85694-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="85694-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="85694-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="85694-108">**Para restaurar um backup de um dispositivo usando:**</span><span class="sxs-lookup"><span data-stu-id="85694-108">**To restore a backup from a device, using:**</span></span>  
  
     [<span data-ttu-id="85694-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="85694-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="85694-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="85694-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="85694-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="85694-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="85694-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="85694-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="85694-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="85694-113">Permissions</span></span>  
 <span data-ttu-id="85694-114">Se o banco de dados que está sendo restaurado não existir, o usuário deverá ter permissões CREATE DATABASE para poder executar o comando RESTORE.</span><span class="sxs-lookup"><span data-stu-id="85694-114">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="85694-115">Se o banco de dados existir, as permissões RESTORE usarão como padrão os membros das funções de servidor fixas **sysadmin** e **dbcreator** e o proprietário (**dbo**) do banco de dados (para a opção FROM DATABASE_SNAPSHOT, o banco de dados sempre existe).</span><span class="sxs-lookup"><span data-stu-id="85694-115">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="85694-116">As permissões RESTORE são concedidas a funções nas quais as informações de associação estão sempre disponíveis para o servidor.</span><span class="sxs-lookup"><span data-stu-id="85694-116">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="85694-117">Como a associação da função de banco de dados fixa pode ser verificada apenas quando o banco de dados está acessível e não danificado, o que nem sempre é o caso quando RESTORE é executado, os membros da função de banco de dados fixa **db_owner** não têm permissões RESTORE.</span><span class="sxs-lookup"><span data-stu-id="85694-117">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="85694-118">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="85694-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-restore-a-backup-from-a-device"></a><span data-ttu-id="85694-119">Para restaurar um backup de um dispositivo</span><span class="sxs-lookup"><span data-stu-id="85694-119">To restore a backup from a device</span></span>  
  
1.  <span data-ttu-id="85694-120">Depois de se conectar à instância apropriada do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], em Pesquisador de Objetos, clique no nome do servidor para expandir a árvore do servidor.</span><span class="sxs-lookup"><span data-stu-id="85694-120">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="85694-121">Expanda **Bancos de Dados**e, dependendo do banco de dados, selecione um banco de dados de usuário ou expanda **Bancos de Dados do Sistema** e selecione um banco de dados do sistema.</span><span class="sxs-lookup"><span data-stu-id="85694-121">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="85694-122">Clique com o botão direito do mouse no banco de dados, aponte para **Tarefas**e clique em **Restaurar**.</span><span class="sxs-lookup"><span data-stu-id="85694-122">Right-click the database, point to **Tasks**, and then click **Restore**.</span></span>  
  
4.  <span data-ttu-id="85694-123">Clique no tipo da operação de restauração desejada (**Banco de Dados**, **Arquivos e Grupos de Arquivos**ou **Log de Transações**).</span><span class="sxs-lookup"><span data-stu-id="85694-123">Click the type of restore operation you want (**Database**, **Files and Filegroups**, or **Transaction Log**).</span></span> <span data-ttu-id="85694-124">Essa ação abre a caixa de diálogo de restauração correspondente.</span><span class="sxs-lookup"><span data-stu-id="85694-124">This opens the corresponding restore dialog box.</span></span>  
  
5.  <span data-ttu-id="85694-125">Na página **Geral** , na seção **Restaurar Origem** , clique em **Dispositivo de Origem**.</span><span class="sxs-lookup"><span data-stu-id="85694-125">On the **General** page, in the **Restore source** section, click **From device**.</span></span>  
  
6.  <span data-ttu-id="85694-126">Clique no botão de procura da caixa de texto **Dispositivo de Origem** , que abre a caixa de diálogo **Especificar Backup** .</span><span class="sxs-lookup"><span data-stu-id="85694-126">Click the browse button for the **From device** text box, which opens the **Specify Backup** dialog box.</span></span>  
  
7.  <span data-ttu-id="85694-127">Na caixa de texto **Mídia de Backup** , selecione **Dispositivo de Backup**e clique no botão **Adicionar** para abrir a caixa de diálogo **Selecionar Dispositivo de Backup** .</span><span class="sxs-lookup"><span data-stu-id="85694-127">In the **Backup media** text box, select **Backup Device**, and click the **Add** button to open the **Select Backup Device** dialog box.</span></span>  
  
8.  <span data-ttu-id="85694-128">Na caixa de texto **Dispositivo de backup** , selecione o dispositivo a ser usado para restaurar a operação.</span><span class="sxs-lookup"><span data-stu-id="85694-128">In the **Backup device** text box, select the device you want to use for the restore operation.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="85694-129">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="85694-129">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-a-backup-from-a-device"></a><span data-ttu-id="85694-130">Para restaurar um backup de um dispositivo</span><span class="sxs-lookup"><span data-stu-id="85694-130">To restore a backup from a device</span></span>  
  
1.  <span data-ttu-id="85694-131">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85694-131">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="85694-132">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="85694-132">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="85694-133">Na instrução [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) , especifique um dispositivo de backup lógico ou físico a ser usado na operação de backup.</span><span class="sxs-lookup"><span data-stu-id="85694-133">In the [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statement, specify a logical or physical backup device to use for the backup operation.</span></span> <span data-ttu-id="85694-134">Este exemplo restaura de um arquivo em disco que tem o nome físico `Z:\SQLServerBackups\AdventureWorks2012.bak`.</span><span class="sxs-lookup"><span data-stu-id="85694-134">This example restores from a disk file that has the physical name `Z:\SQLServerBackups\AdventureWorks2012.bak`.</span></span>  
  
```sql  
RESTORE DATABASE AdventureWorks2012  
   FROM DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak' ;  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="85694-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="85694-135">See Also</span></span>  
 <span data-ttu-id="85694-136">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="85694-136">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span></span>  
 <span data-ttu-id="85694-137">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="85694-137">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span></span>  
 <span data-ttu-id="85694-138">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="85694-138">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span></span>  
 <span data-ttu-id="85694-139">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="85694-139">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span></span>  
 <span data-ttu-id="85694-140">[Restaurar um backup de banco de dados no modelo de recuperação simples &#40;Transact-SQL&#41;](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="85694-140">[Restore a Database Backup Under the Simple Recovery Model &#40;Transact-SQL&#41;](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md) </span></span>  
 <span data-ttu-id="85694-141">[Restaurar um backup de banco de dados &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="85694-141">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span></span>  
 <span data-ttu-id="85694-142">[Restaurar um backup de banco de dados diferencial &#40;SQL Server&#41;](restore-a-differential-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="85694-142">[Restore a Differential Database Backup &#40;SQL Server&#41;](restore-a-differential-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="85694-143">[Restaurar um banco de dados em um novo local &#40;SQL Server&#41;](restore-a-database-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="85694-143">[Restore a Database to a New Location &#40;SQL Server&#41;](restore-a-database-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="85694-144">[Fazer backup de arquivos e de grupos de arquivos &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="85694-144">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="85694-145">[Fazer backup de um log de transações &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="85694-145">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 [<span data-ttu-id="85694-146">Criar um backup diferencial de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="85694-146">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
  
