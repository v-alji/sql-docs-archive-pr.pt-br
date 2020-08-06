---
title: Habilitar ou desabilitar as somas de verificação de backup durante backup ou restauração (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup checksums [SQL Server]
- disabling checksums
- checksums [SQL Server]
ms.assetid: 6786bd1e-ad97-430a-8dfb-d4ba952d6c4d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a239dcdfca689be8555117104264d66a2ac037f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685812"
---
# <a name="enable-or-disable-backup-checksums-during-backup-or-restore-sql-server"></a><span data-ttu-id="5d310-102">Habilitar ou desabilitar as somas de verificação de backup durante backup ou restauração (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5d310-102">Enable or Disable Backup Checksums During Backup or Restore (SQL Server)</span></span>
  <span data-ttu-id="5d310-103">Este tópico descreve como habilitar ou desabilitar somas de verificação de backup durante processos de backup ou restauração de bancos de dados no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d310-103">This topic describes how to enable or disable backup checksums when you are backing up or restoring a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="5d310-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="5d310-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5d310-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="5d310-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5d310-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="5d310-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5d310-107">**Para habilitar ou desabilitar as somas de verificação de backup usando:**</span><span class="sxs-lookup"><span data-stu-id="5d310-107">**To enable or disable backup checksums, using:**</span></span>  
  
     [<span data-ttu-id="5d310-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5d310-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5d310-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5d310-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5d310-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="5d310-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5d310-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="5d310-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5d310-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="5d310-112">Permissions</span></span>  
 <span data-ttu-id="5d310-113">BACKUP</span><span class="sxs-lookup"><span data-stu-id="5d310-113">BACKUP</span></span>  
 <span data-ttu-id="5d310-114">As permissões BACKUP DATABASE e BACKUP LOG usam como padrão os membros da função de servidor fixa **sysadmin** e as funções de banco de dados fixas **db_owner** e **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="5d310-114">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="5d310-115">Os problemas de propriedade e permissão no arquivo físico do dispositivo de backup podem interferir em uma operação de backup.</span><span class="sxs-lookup"><span data-stu-id="5d310-115">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5d310-116">deve ser capaz de ler e gravar no dispositivo; a conta sob a qual o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executa deve ter permissões de gravação.</span><span class="sxs-lookup"><span data-stu-id="5d310-116">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="5d310-117">No entanto, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), que adiciona uma entrada para um dispositivo de backup nas tabelas do sistema, não verifica permissões de acesso a arquivos.</span><span class="sxs-lookup"><span data-stu-id="5d310-117">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="5d310-118">Esses problemas no arquivo físico do dispositivo de backup podem não aparecer até que o recurso físico seja acessado quando o backup ou restauração é tentado.</span><span class="sxs-lookup"><span data-stu-id="5d310-118">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
 <span data-ttu-id="5d310-119">RESTORE</span><span class="sxs-lookup"><span data-stu-id="5d310-119">RESTORE</span></span>  
 <span data-ttu-id="5d310-120">Se o banco de dados que está sendo restaurado não existir, o usuário deverá ter permissões CREATE DATABASE para poder executar o comando RESTORE.</span><span class="sxs-lookup"><span data-stu-id="5d310-120">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="5d310-121">Se o banco de dados existir, as permissões RESTORE usarão como padrão os membros das funções de servidor fixas **sysadmin** e **dbcreator** e o proprietário (**dbo**) do banco de dados (para a opção FROM DATABASE_SNAPSHOT, o banco de dados sempre existe).</span><span class="sxs-lookup"><span data-stu-id="5d310-121">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="5d310-122">As permissões RESTORE são concedidas a funções nas quais as informações de associação estão sempre disponíveis para o servidor.</span><span class="sxs-lookup"><span data-stu-id="5d310-122">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="5d310-123">Como a associação da função de banco de dados fixa pode ser verificada apenas quando o banco de dados está acessível e não danificado, o que nem sempre é o caso quando RESTORE é executado, os membros da função de banco de dados fixa **db_owner** não têm permissões RESTORE.</span><span class="sxs-lookup"><span data-stu-id="5d310-123">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5d310-124">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5d310-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-enable-or-disable-checksums-during-a-backup-operation"></a><span data-ttu-id="5d310-125">Para habilitar ou desabilitar as somas de verificação durante operações de backup</span><span class="sxs-lookup"><span data-stu-id="5d310-125">To enable or disable checksums during a backup operation</span></span>  
  
1.  <span data-ttu-id="5d310-126">Siga as etapas para [criar um backup de banco de dados](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5d310-126">Follow the steps to [create a database backup](create-a-full-database-backup-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="5d310-127">Na página **Opções** , na seção **Confiabilidade** , clique em **Executar soma de verificação antes de gravar na mídia**.</span><span class="sxs-lookup"><span data-stu-id="5d310-127">On the **Options** page, in the **Reliability** section, click **Perform checksum before writing to media**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5d310-128">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5d310-128">Using Transact-SQL</span></span>  
  
#### <a name="to-enable-or-disable-backup-checksum-for-a-backup-operation"></a><span data-ttu-id="5d310-129">Para habilitar ou desabilitar a soma de verificação de backup durante operações de backup</span><span class="sxs-lookup"><span data-stu-id="5d310-129">To enable or disable backup checksum for a backup operation</span></span>  
  
1.  <span data-ttu-id="5d310-130">Conecte-se ao [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d310-130">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5d310-131">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="5d310-131">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5d310-132">Para habilitar somas de verificação de backup em uma instrução [BACKUP](/sql/t-sql/statements/backup-transact-sql) , especifique a opção WITH CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="5d310-132">To enable backup checksums in a [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement, specify the WITH CHECKSUM option.</span></span> <span data-ttu-id="5d310-133">Para desabilitar somas de verificação de backup, especifique a opção WITH NO_CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="5d310-133">To disable backup checksums, specify the WITH NO_CHECKSUM option.</span></span> <span data-ttu-id="5d310-134">Esse é o comportamento padrão, com exceção de um backup compactado.</span><span class="sxs-lookup"><span data-stu-id="5d310-134">This is the default behavior, except for a compressed backup.</span></span> <span data-ttu-id="5d310-135">O exemplo a seguir especifica que somas de verificação serão executadas.</span><span class="sxs-lookup"><span data-stu-id="5d310-135">The following example specifies that checksums be performed.</span></span>  
  
```sql  
BACKUP DATABASE AdventureWorks2012   
 TO DISK = 'Z:\SQLServerBackups\AdvWorksData.bak'  
   WITH CHECKSUM;  
GO  
```  
  
#### <a name="to-enable-or-disable-backup-checksum-for-a-restore-operation"></a><span data-ttu-id="5d310-136">Para habilitar ou desabilitar a soma de verificação de backup durante operações de restauração</span><span class="sxs-lookup"><span data-stu-id="5d310-136">To enable or disable backup checksum for a restore operation</span></span>  
  
1.  <span data-ttu-id="5d310-137">Conecte-se ao [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d310-137">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5d310-138">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="5d310-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5d310-139">Para habilitar somas de verificação de backup em uma instrução [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) , especifique a opção WITH CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="5d310-139">To enable backup checksums in a [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statement, specify the WITH CHECKSUM option.</span></span> <span data-ttu-id="5d310-140">Esse é o comportamento padrão de um backup compactado.</span><span class="sxs-lookup"><span data-stu-id="5d310-140">This is the default behavior for a compressed backup.</span></span> <span data-ttu-id="5d310-141">Para desabilitar somas de verificação de backup, especifique a opção WITH NO_CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="5d310-141">To disable backup checksums, specify the WITH NO_CHECKSUM option.</span></span> <span data-ttu-id="5d310-142">Esse é o comportamento padrão, com exceção de um backup compactado.</span><span class="sxs-lookup"><span data-stu-id="5d310-142">This is the default behavior, except for a compressed backup.</span></span> <span data-ttu-id="5d310-143">O exemplo a seguir especifica que somas de verificação de backup serão executadas.</span><span class="sxs-lookup"><span data-stu-id="5d310-143">The following example specifies that backup checksums be performed.</span></span>  
  
```sql  
RESTORE DATABASE AdventureWorks2012   
 FROM DISK = 'Z:\SQLServerBackups\AdvWorksData.bak'  
   WITH CHECKSUM;  
GO  
```  
  
> [!WARNING]  
>  <span data-ttu-id="5d310-144">Se você solicitar CHECKSUM explicitamente para uma operação de restauração e se o backup contiver somas de verificação de backup, as somas de verificação de backup e as somas de verificação de página serão ambas verificadas, como no caso padrão.</span><span class="sxs-lookup"><span data-stu-id="5d310-144">If you explicitly request CHECKSUM for a restore operation and if the backup contains backup checksums, backup checksums and page checksums are both verified, as in the default case.</span></span> <span data-ttu-id="5d310-145">Porém, se o conjunto de backup não tiver as somas de verificação de backup, a operação de restauração falha com uma mensagem indicando que as somas de verificação não estão presentes.</span><span class="sxs-lookup"><span data-stu-id="5d310-145">However, if the backup set lacks backup checksums, the restore operation fails with a message indicating that checksums are not present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d310-146">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5d310-146">See Also</span></span>  
 <span data-ttu-id="5d310-147">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5d310-147">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span></span>  
 <span data-ttu-id="5d310-148">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5d310-148">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span></span>  
 <span data-ttu-id="5d310-149">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5d310-149">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span></span>  
 <span data-ttu-id="5d310-150">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5d310-150">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span></span>  
 <span data-ttu-id="5d310-151">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5d310-151">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="5d310-152">[conjunto de backup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5d310-152">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="5d310-153">[Argumentos de RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5d310-153">[RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span></span>  
 <span data-ttu-id="5d310-154">[Erros de mídia possíveis durante backup e restauração &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5d310-154">[Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md) </span></span>  
 [<span data-ttu-id="5d310-155">Especificar se uma operação de backup ou restauração continua ou é interrompida após um erro &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5d310-155">Specify Whether a Backup or Restore Operation Continues or Stops After Encountering an Error &#40;SQL Server&#41;</span></span>](specify-if-backup-or-restore-continues-or-stops-after-error.md)  
  
  
