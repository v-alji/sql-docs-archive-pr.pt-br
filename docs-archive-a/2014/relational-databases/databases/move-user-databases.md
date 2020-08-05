---
title: Mover bancos de dados de usuário | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- disaster recovery [SQL Server], moving database files
- database files [SQL Server], moving
- data files [SQL Server], moving
- editions [SQL Server], moving databases between
- moving full-text catalogs
- scheduled disk maintenace [SQL Server]
- moving databases
- full-text catalogs [SQL Server], moving
- moving database files
- moving user databases
- relocating database files
- planned database relocations [SQL Server]
- databases [SQL Server], moving
ms.assetid: ad9a4e92-13fb-457d-996a-66ffc2d55b79
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6c2b82c3bec13c82aa30aebd175ef78f8136ee04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573103"
---
# <a name="move-user-databases"></a><span data-ttu-id="aa718-102">Mover bancos de dados de usuário</span><span class="sxs-lookup"><span data-stu-id="aa718-102">Move User Databases</span></span>
  <span data-ttu-id="aa718-103">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], é possível mover os dados, o log e os arquivos de catálogo de texto completo de um banco de dados de usuário para um novo local, especificando o novo local do arquivo na cláusula FILENAME da instrução [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="aa718-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can move the data, log, and full-text catalog files of a user database to a new location by specifying the new file location in the FILENAME clause of the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement.</span></span> <span data-ttu-id="aa718-104">Esse método é aplicado para mover arquivos do banco de dados dentro da mesma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa718-104">This method applies to moving database files within the same instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="aa718-105">Para mover um banco de dados para uma outra instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou para um outro servidor, use as operações de [backup e restauração](../backup-restore/back-up-and-restore-of-sql-server-databases.md) ou [anexar e desanexar](move-a-database-using-detach-and-attach-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="aa718-105">To move a database to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or to another server, use [backup and restore](../backup-restore/back-up-and-restore-of-sql-server-databases.md) or [detach and attach operations](move-a-database-using-detach-and-attach-transact-sql.md).</span></span>  
  
## <a name="considerations"></a><span data-ttu-id="aa718-106">Considerações</span><span class="sxs-lookup"><span data-stu-id="aa718-106">Considerations</span></span>  
 <span data-ttu-id="aa718-107">Ao mover um banco de dados para outra instância do servidor, para oferecer uma experiência consistente aos usuários e aplicativos, talvez seja necessário recriar alguns ou todos os metadados do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="aa718-107">When you move a database onto another server instance, to provide a consistent experience to users and applications, you might have to re-create some or all the metadata for the database.</span></span> <span data-ttu-id="aa718-108">Para obter mais informações, consulte [Gerenciar metadados ao disponibilizar um banco de dados em outra instância do servidor &#40;SQL Server&#41;](manage-metadata-when-making-a-database-available-on-another-server.md).</span><span class="sxs-lookup"><span data-stu-id="aa718-108">For more information, see [Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](manage-metadata-when-making-a-database-available-on-another-server.md).</span></span>  
  
 <span data-ttu-id="aa718-109">Alguns recursos do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] alteram a maneira como o [!INCLUDE[ssDE](../../includes/ssde-md.md)] armazena as informações nos arquivos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="aa718-109">Some features of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] change the way that the [!INCLUDE[ssDE](../../includes/ssde-md.md)] stores information in the database files.</span></span> <span data-ttu-id="aa718-110">Esses recursos são restritos a edições específicas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa718-110">These features are restricted to specific editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="aa718-111">Um banco de dados que contém esses recursos não pode ser movido para uma edição do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que não dê suporte a eles.</span><span class="sxs-lookup"><span data-stu-id="aa718-111">A database that contains these features cannot be moved to an edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that does not support them.</span></span> <span data-ttu-id="aa718-112">Use a exibição de gerenciamento dinâmico sys.dm_db_persisted_sku_features para listar todos os recursos específicos de edição habilitados no banco de dados atual.</span><span class="sxs-lookup"><span data-stu-id="aa718-112">Use the sys.dm_db_persisted_sku_features dynamic management view to list all edition-specific features that are enabled in the current database.</span></span>  
  
 <span data-ttu-id="aa718-113">Os procedimentos neste tópico exigem o nome lógico dos arquivos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="aa718-113">The procedures in this topic require the logical name of the database files.</span></span> <span data-ttu-id="aa718-114">Para obter o nome, consulte a coluna de nome na exibição de catálogo [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="aa718-114">To obtain the name, query the name column in the [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) catalog view.</span></span>  
  
 <span data-ttu-id="aa718-115">A partir do [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], os catálogos de texto completo são integrados no banco de dados em vez de serem armazenados no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="aa718-115">Starting with [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], full-text catalogs are integrated into the database rather than being stored in the file system.</span></span> <span data-ttu-id="aa718-116">Os catálogos de texto completo agora são movidos automaticamente quando você move um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="aa718-116">The full-text catalogs now move automatically when you move a database.</span></span>  
  
## <a name="planned-relocation-procedure"></a><span data-ttu-id="aa718-117">Procedimento de realocação planejada</span><span class="sxs-lookup"><span data-stu-id="aa718-117">Planned Relocation Procedure</span></span>  
 <span data-ttu-id="aa718-118">Para mover um arquivo de dados ou de log como parte de uma realocação planejada, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="aa718-118">To move a data or log file as part of a planned relocation, follow these steps:</span></span>  
  
1.  <span data-ttu-id="aa718-119">Execute a seguinte instrução.</span><span class="sxs-lookup"><span data-stu-id="aa718-119">Run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name SET OFFLINE;  
    ```  
  
2.  <span data-ttu-id="aa718-120">Mova o arquivo ou os arquivos para o novo local.</span><span class="sxs-lookup"><span data-stu-id="aa718-120">Move the file or files to the new location.</span></span>  
  
3.  <span data-ttu-id="aa718-121">Para cada arquivo movido, execute a seguinte instrução.</span><span class="sxs-lookup"><span data-stu-id="aa718-121">For each file moved, run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE ( NAME = logical_name, FILENAME = 'new_path\os_file_name' );  
    ```  
  
4.  <span data-ttu-id="aa718-122">Execute a seguinte instrução.</span><span class="sxs-lookup"><span data-stu-id="aa718-122">Run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name SET ONLINE;  
    ```  
  
5.  <span data-ttu-id="aa718-123">Execute a consulta a seguir para verificar se houve alteração no arquivo.</span><span class="sxs-lookup"><span data-stu-id="aa718-123">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
## <a name="relocation-for-scheduled-disk-maintenance"></a><span data-ttu-id="aa718-124">Realocação para manutenção de disco programada</span><span class="sxs-lookup"><span data-stu-id="aa718-124">Relocation for Scheduled Disk Maintenance</span></span>  
 <span data-ttu-id="aa718-125">Para realocar um arquivo como parte de um processo de manutenção de disco programada, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="aa718-125">To relocate a file as part of a scheduled disk maintenance process, follow these steps:</span></span>  
  
1.  <span data-ttu-id="aa718-126">Para cada arquivo a ser movido, execute a seguinte instrução.</span><span class="sxs-lookup"><span data-stu-id="aa718-126">For each file to be moved, run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE ( NAME = logical_name , FILENAME = 'new_path\os_file_name' );  
    ```  
  
2.  <span data-ttu-id="aa718-127">Pare a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou desligue o sistema para realizar a manutenção.</span><span class="sxs-lookup"><span data-stu-id="aa718-127">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or shut down the system to perform maintenance.</span></span> <span data-ttu-id="aa718-128">Para obter mais informações, consulte [Iniciar, parar, pausar, retomar e reiniciar os serviços SQL Server](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="aa718-128">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
3.  <span data-ttu-id="aa718-129">Mova o arquivo ou os arquivos para o novo local.</span><span class="sxs-lookup"><span data-stu-id="aa718-129">Move the file or files to the new location.</span></span>  
  
4.  <span data-ttu-id="aa718-130">Reinicialize a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou o servidor.</span><span class="sxs-lookup"><span data-stu-id="aa718-130">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or the server.</span></span> <span data-ttu-id="aa718-131">Para obter mais informações, veja [Iniciar, parar, pausar, retomar, reiniciar o mecanismo de banco de dados, o SQL Server Agent ou o serviço SQL Server Browser](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md)</span><span class="sxs-lookup"><span data-stu-id="aa718-131">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md)</span></span>  
  
5.  <span data-ttu-id="aa718-132">Execute a consulta a seguir para verificar se houve alteração no arquivo.</span><span class="sxs-lookup"><span data-stu-id="aa718-132">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
## <a name="failure-recovery-procedure"></a><span data-ttu-id="aa718-133">Falha no procedimento de recuperação</span><span class="sxs-lookup"><span data-stu-id="aa718-133">Failure Recovery Procedure</span></span>  
 <span data-ttu-id="aa718-134">Se um arquivo tiver que ser movido devido à uma falha de hardware, execute as seguintes etapas para realocar o arquivo no novo local.</span><span class="sxs-lookup"><span data-stu-id="aa718-134">If a file must be moved because of a hardware failure, use the following steps to relocate the file to a new location.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="aa718-135">Se o banco de dados não puder ser inicializado, significa que ele está em modo de suspeição ou em estado não recuperado, e apenas os membros de função fixa sysadmin podem mover o arquivo.</span><span class="sxs-lookup"><span data-stu-id="aa718-135">If the database cannot be started, that is it is in suspect mode or in an unrecovered state, only members of the sysadmin fixed role can move the file.</span></span>  
  
1.  <span data-ttu-id="aa718-136">Interrompa a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , se tiver sido iniciado.</span><span class="sxs-lookup"><span data-stu-id="aa718-136">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if it is started.</span></span>  
  
2.  <span data-ttu-id="aa718-137">Inicie a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no modo somente recuperação mestre, inserindo um dos seguintes comandos no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="aa718-137">Start the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in master-only recovery mode by entering one of the following commands at the command prompt.</span></span>  
  
    -   <span data-ttu-id="aa718-138">Para a instância padrão (MSSQLSERVER), execute o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="aa718-138">For the default (MSSQLSERVER) instance, run the following command.</span></span>  
  
        ```  
        NET START MSSQLSERVER /f /T3608  
        ```  
  
    -   <span data-ttu-id="aa718-139">Para uma instância nomeada, execute o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="aa718-139">For a named instance, run the following command.</span></span>  
  
        ```  
        NET START MSSQL$instancename /f /T3608  
        ```  
  
     <span data-ttu-id="aa718-140">Para obter mais informações, consulte [Iniciar, parar, pausar, retomar e reiniciar os serviços SQL Server](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="aa718-140">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
3.  <span data-ttu-id="aa718-141">Para cada arquivo a ser movido, use comandos **sqlcmd** ou [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] para executar a instrução a seguir.</span><span class="sxs-lookup"><span data-stu-id="aa718-141">For each file to be moved, use **sqlcmd** commands or [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] to run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE( NAME = logical_name , FILENAME = 'new_path\os_file_name' );  
    ```  
  
     <span data-ttu-id="aa718-142">Para obter mais informações sobre como usar o utilitário **sqlcmd** , veja [Usar o Utilitário sqlcmd](../scripting/sqlcmd-use-the-utility.md).</span><span class="sxs-lookup"><span data-stu-id="aa718-142">For more information about how to use the **sqlcmd** utility, see [Use the sqlcmd Utility](../scripting/sqlcmd-use-the-utility.md).</span></span>  
  
4.  <span data-ttu-id="aa718-143">Saia do utilitário **sqlcmd** ou [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa718-143">Exit the **sqlcmd** utility or [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
5.  <span data-ttu-id="aa718-144">Pare a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa718-144">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
6.  <span data-ttu-id="aa718-145">Mova o arquivo ou os arquivos para o novo local.</span><span class="sxs-lookup"><span data-stu-id="aa718-145">Move the file or files to the new location.</span></span>  
  
7.  <span data-ttu-id="aa718-146">Inicie a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa718-146">Start the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="aa718-147">Por exemplo, execute `NET START MSSQLSERVER`.</span><span class="sxs-lookup"><span data-stu-id="aa718-147">For example, run: `NET START MSSQLSERVER`.</span></span>  
  
8.  <span data-ttu-id="aa718-148">Execute a consulta a seguir para verificar se houve alteração no arquivo.</span><span class="sxs-lookup"><span data-stu-id="aa718-148">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
## <a name="examples"></a><span data-ttu-id="aa718-149">Exemplos</span><span class="sxs-lookup"><span data-stu-id="aa718-149">Examples</span></span>  
 <span data-ttu-id="aa718-150">O exemplo seguinte move o arquivo de log [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] para um novo local como parte de uma realocação planejada.</span><span class="sxs-lookup"><span data-stu-id="aa718-150">The following example moves the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] log file to a new location as part of a planned relocation.</span></span>  
  
```  
USE master;  
GO  
-- Return the logical file name.  
SELECT name, physical_name AS CurrentLocation, state_desc  
FROM sys.master_files  
WHERE database_id = DB_ID(N'AdventureWorks2012')  
    AND type_desc = N'LOG';  
GO  
ALTER DATABASE AdventureWorks2012 SET OFFLINE;  
GO  
-- Physically move the file to a new location.  
-- In the following statement, modify the path specified in FILENAME to  
-- the new location of the file on your server.  
ALTER DATABASE AdventureWorks2012   
    MODIFY FILE ( NAME = AdventureWorks2012_Log,   
                  FILENAME = 'C:\NewLoc\AdventureWorks2012_Log.ldf');  
GO  
ALTER DATABASE AdventureWorks2012 SET ONLINE;  
GO  
--Verify the new location.  
SELECT name, physical_name AS CurrentLocation, state_desc  
FROM sys.master_files  
WHERE database_id = DB_ID(N'AdventureWorks2012')  
    AND type_desc = N'LOG';  
```  
  
## <a name="see-also"></a><span data-ttu-id="aa718-151">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aa718-151">See Also</span></span>  
 <span data-ttu-id="aa718-152">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aa718-152">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="aa718-153">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aa718-153">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="aa718-154">[Anexar e desanexar bancos de dados &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="aa718-154">[Database Detach and Attach &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span></span>  
 <span data-ttu-id="aa718-155">[Mover bancos de dados do sistema](system-databases.md) </span><span class="sxs-lookup"><span data-stu-id="aa718-155">[Move System Databases](system-databases.md) </span></span>  
 <span data-ttu-id="aa718-156">[Mover arquivos de banco de dados](move-database-files.md) </span><span class="sxs-lookup"><span data-stu-id="aa718-156">[Move Database Files](move-database-files.md) </span></span>  
 <span data-ttu-id="aa718-157">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aa718-157">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="aa718-158">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aa718-158">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="aa718-159">Iniciar, parar, pausar, retomar, reiniciar o mecanismo de banco de dados, o SQL Server Agent ou o serviço SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="aa718-159">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md)  
  
  
