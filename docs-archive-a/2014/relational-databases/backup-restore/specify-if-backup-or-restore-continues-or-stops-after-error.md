---
title: Especificar se uma operação de backup ou restauração continua ou pára depois de encontrar um erro (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- errors [SQL Server], backups
- backing up databases [SQL Server], errors
- backups [SQL Server], errors
- database backups [SQL Server], errors
ms.assetid: 042be17a-b9b0-4629-b6bb-b87a8bc6c316
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 87cccec6f7eea18f2750d3b0be81b577b0eb170a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582466"
---
# <a name="specify-whether-a-backup-or-restore-operation-continues-or-stops-after-encountering-an-error-sql-server"></a><span data-ttu-id="fa401-102">Especificar se uma operação de backup ou restauração para ou continua depois de encontrar um erro (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fa401-102">Specify Whether a Backup or Restore Operation Continues or Stops After Encountering an Error (SQL Server)</span></span>
  <span data-ttu-id="fa401-103">Este tópico descreve como especificar se uma operação de backup ou restauração continuará ou será interrompida após encontrar um erro no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa401-103">This topic describes how to specify whether a backup or restore operation continues or stops after encountering an error in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="fa401-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="fa401-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="fa401-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="fa401-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="fa401-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="fa401-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="fa401-107">**Para especificar se uma operação de backup ou restauração continua depois de encontrar um erro usando:**</span><span class="sxs-lookup"><span data-stu-id="fa401-107">**To specify whether a backup or restore operation continues after encountering an error, using:**</span></span>  
  
     [<span data-ttu-id="fa401-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fa401-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="fa401-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fa401-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fa401-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="fa401-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fa401-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="fa401-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fa401-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="fa401-112">Permissions</span></span>  
 <span data-ttu-id="fa401-113">BACKUP</span><span class="sxs-lookup"><span data-stu-id="fa401-113">BACKUP</span></span>  
 <span data-ttu-id="fa401-114">As permissões BACKUP DATABASE e BACKUP LOG usam como padrão os membros da função de servidor fixa **sysadmin** e as funções de banco de dados fixas **db_owner** e **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="fa401-114">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="fa401-115">Os problemas de propriedade e permissão no arquivo físico do dispositivo de backup podem interferir em uma operação de backup.</span><span class="sxs-lookup"><span data-stu-id="fa401-115">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="fa401-116">deve ser capaz de ler e gravar no dispositivo; a conta sob a qual o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executa deve ter permissões de gravação.</span><span class="sxs-lookup"><span data-stu-id="fa401-116">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="fa401-117">No entanto, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), que adiciona uma entrada para um dispositivo de backup nas tabelas do sistema, não verifica permissões de acesso a arquivos.</span><span class="sxs-lookup"><span data-stu-id="fa401-117">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="fa401-118">Esses problemas no arquivo físico do dispositivo de backup podem não aparecer até que o recurso físico seja acessado quando o backup ou restauração é tentado.</span><span class="sxs-lookup"><span data-stu-id="fa401-118">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
 <span data-ttu-id="fa401-119">RESTORE</span><span class="sxs-lookup"><span data-stu-id="fa401-119">RESTORE</span></span>  
 <span data-ttu-id="fa401-120">Se o banco de dados que está sendo restaurado não existir, o usuário deverá ter permissões CREATE DATABASE para poder executar o comando RESTORE.</span><span class="sxs-lookup"><span data-stu-id="fa401-120">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="fa401-121">Se o banco de dados existir, as permissões RESTORE usarão como padrão os membros das funções de servidor fixas **sysadmin** e **dbcreator** e o proprietário (**dbo**) do banco de dados (para a opção FROM DATABASE_SNAPSHOT, o banco de dados sempre existe).</span><span class="sxs-lookup"><span data-stu-id="fa401-121">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="fa401-122">As permissões RESTORE são concedidas a funções nas quais as informações de associação estão sempre disponíveis para o servidor.</span><span class="sxs-lookup"><span data-stu-id="fa401-122">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="fa401-123">Como a associação da função de banco de dados fixa pode ser verificada apenas quando o banco de dados está acessível e não danificado, o que nem sempre é o caso quando RESTORE é executado, os membros da função de banco de dados fixa **db_owner** não têm permissões RESTORE.</span><span class="sxs-lookup"><span data-stu-id="fa401-123">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="fa401-124">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fa401-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-specify-whether-backup-continues-or-stops-after-an-error-is-encountered"></a><span data-ttu-id="fa401-125">Para especificar se o backup para ou continua depois de encontrar um erro</span><span class="sxs-lookup"><span data-stu-id="fa401-125">To specify whether backup continues or stops after an error is encountered</span></span>  
  
1.  <span data-ttu-id="fa401-126">Siga as etapas para [criar um backup de banco de dados](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="fa401-126">Follow the steps to [create a database backup](create-a-full-database-backup-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="fa401-127">Na página **Opções** , na seção **Confiabilidade** , clique em **Executar soma de verificação antes de gravar na mídia** e em **Continuar se houver erro**.</span><span class="sxs-lookup"><span data-stu-id="fa401-127">On the **Options** page, in the **Reliability** section, click **Perform checksum before writing to media** and **Continue on error**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fa401-128">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fa401-128">Using Transact-SQL</span></span>  
  
#### <a name="to-specify-whether-a-backup-operation-continues-or-stops-after-encountering-an-error"></a><span data-ttu-id="fa401-129">Para especificar se uma operação de backup para ou continua depois de encontrar um erro</span><span class="sxs-lookup"><span data-stu-id="fa401-129">To specify whether a backup operation continues or stops after encountering an error</span></span>  
  
1.  <span data-ttu-id="fa401-130">Conecte-se ao [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa401-130">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="fa401-131">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="fa401-131">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="fa401-132">Na instrução [BACKUP](/sql/t-sql/statements/backup-transact-sql) , especifique a opção CONTINUE_AFTER ERROR para continuar ou a opção STOP_ON_ERROR para parar.</span><span class="sxs-lookup"><span data-stu-id="fa401-132">In the [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement, specify the CONTINUE_AFTER ERROR option to continue or the STOP_ON_ERROR option to stop.</span></span> <span data-ttu-id="fa401-133">O comportamento padrão é parar depois de encontrar um erro.</span><span class="sxs-lookup"><span data-stu-id="fa401-133">The default behavior is to stop after encountering an error.</span></span> <span data-ttu-id="fa401-134">Este exemplo instrui a operação de backup a continuar apesar de encontrar um erro.</span><span class="sxs-lookup"><span data-stu-id="fa401-134">This example instructs the backup operation to continue despite encountering an error.</span></span>  
  
```sql  
BACKUP DATABASE AdventureWorks2012   
 TO DISK = 'Z:\SQLServerBackups\AdvWorksData.bak'  
   WITH CHECKSUM, CONTINUE_AFTER_ERROR;  
GO  
```  
  
#### <a name="to-specify-whether-a-restore-operation-continues-or-stops-after-encountering-an-error"></a><span data-ttu-id="fa401-135">Para especificar se uma operação de restauração para ou continua depois de encontrar um erro</span><span class="sxs-lookup"><span data-stu-id="fa401-135">To specify whether a restore operation continues or stops after encountering an error</span></span>  
  
1.  <span data-ttu-id="fa401-136">Conecte-se ao [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa401-136">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="fa401-137">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="fa401-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="fa401-138">Na instrução [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) , especifique a opção CONTINUE_AFTER ERROR para continuar ou a opção STOP_ON_ERROR para parar.</span><span class="sxs-lookup"><span data-stu-id="fa401-138">In the [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statement, specify the CONTINUE_AFTER ERROR option to continue or the STOP_ON_ERROR option to stop.</span></span> <span data-ttu-id="fa401-139">O comportamento padrão é parar depois de encontrar um erro.</span><span class="sxs-lookup"><span data-stu-id="fa401-139">The default behavior is to stop after encountering an error.</span></span> <span data-ttu-id="fa401-140">Este exemplo instrui a operação de restauração a continuar apesar de encontrar um erro.</span><span class="sxs-lookup"><span data-stu-id="fa401-140">This example instructs the restore operation to continue despite encountering an error.</span></span>  
  
```sql  
RESTORE DATABASE AdventureWorks2012   
 FROM DISK = 'Z:\SQLServerBackups\AdvWorksData.bak'   
   WITH CHECKSUM, CONTINUE_AFTER_ERROR;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="fa401-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fa401-141">See Also</span></span>  
 <span data-ttu-id="fa401-142">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fa401-142">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span></span>  
 <span data-ttu-id="fa401-143">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fa401-143">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span></span>  
 <span data-ttu-id="fa401-144">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fa401-144">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span></span>  
 <span data-ttu-id="fa401-145">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fa401-145">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span></span>  
 <span data-ttu-id="fa401-146">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fa401-146">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="fa401-147">[conjunto de backup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fa401-147">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="fa401-148">[Argumentos de RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fa401-148">[RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span></span>  
 <span data-ttu-id="fa401-149">[Erros de mídia possíveis durante backup e restauração &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fa401-149">[Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md) </span></span>  
 [<span data-ttu-id="fa401-150">Habilitar ou desabilitar as somas de verificação de backup durante backup ou restauração &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fa401-150">Enable or Disable Backup Checksums During Backup or Restore &#40;SQL Server&#41;</span></span>](enable-or-disable-backup-checksums-during-backup-or-restore-sql-server.md)  
  
  
