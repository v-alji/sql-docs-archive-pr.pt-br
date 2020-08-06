---
title: Preparar um banco de dados espelho para espelhamento (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], preparing for mirroring
- logins [SQL Server], database mirroring
- mirror database [SQL Server]
ms.assetid: 8676f9d8-c451-419b-b934-786997d46c2b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cf46b4f6fd8e7af55e1930ef6063c4754673fa79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681168"
---
# <a name="prepare-a-mirror-database-for-mirroring-sql-server"></a><span data-ttu-id="6f5a5-102">Preparar um banco de dados espelho para espelhamento (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6f5a5-102">Prepare a Mirror Database for Mirroring (SQL Server)</span></span>
  <span data-ttu-id="6f5a5-103">Antes de uma sessão de espelhamento do banco de dados poder iniciar, o proprietário do banco de dados ou administrador de sistema devem ter certeza de que o banco de dados espelho foi criado e está pronto para espelhar.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-103">Before a database mirroring session can start, the database owner or system administrator must make sure that the mirror database has been created and is ready for mirroring.</span></span> <span data-ttu-id="6f5a5-104">A criação de um novo banco de dados espelho requer minimamente um backup cheio do banco de dados principal e um backup de log subsequente e a restauração de ambos sobre a instância do servidor espelho, usando WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-104">Creating a new mirror database minimally requires taking a full backup of the principal database and a subsequent log backup and restoring them both onto the mirror server instance, using WITH NORECOVERY.</span></span>  
  
 <span data-ttu-id="6f5a5-105">Este tópico descreve como preparar um banco de dados espelho no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f5a5-105">This topic describes how to prepare a mirror database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6f5a5-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="6f5a5-106">Before You Begin</span></span>  
  
###  <a name="requirements"></a><a name="Requirements"></a> <span data-ttu-id="6f5a5-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6f5a5-107">Requirements</span></span>  
  
-   <span data-ttu-id="6f5a5-108">As instâncias de servidor principal e espelho devem ser executadas na mesma versão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f5a5-108">The principal and mirror server instances must be running on the same version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6f5a5-109">Embora o servidor espelho possa ter uma versão posterior do SQL Server, essa configuração é recomendável somente durante um processo de atualização cuidadosamente planejado.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-109">While it is possible for the mirror server to have a higher version of SQL Server, this configuration is only recommended during a carefully planned upgrade process.</span></span> <span data-ttu-id="6f5a5-110">Nessa configuração, você corre o risco de um failover automático, no qual a movimentação de dados é suspensa automaticamente porque os dados não podem migrar para uma versão anterior do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-110">In such a configuration, you run the risk of an automatic failover, in which data movement is automatically suspended because data cannot move to a lower version of SQL Server.</span></span> <span data-ttu-id="6f5a5-111">Para obter mais informações, consulte [Minimize Downtime for Mirrored Databases When Upgrading Server Instances](upgrading-mirrored-instances.md).</span><span class="sxs-lookup"><span data-stu-id="6f5a5-111">For more information, see [Minimize Downtime for Mirrored Databases When Upgrading Server Instances](upgrading-mirrored-instances.md).</span></span>  
  
-   <span data-ttu-id="6f5a5-112">As instâncias de servidor principal e espelho devem ser executadas na mesma edição do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f5a5-112">The principal and mirror server instances must be running on the same edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6f5a5-113">Para obter mais informações sobre o suporte para espelhamento de banco de dados no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], consulte [Recursos com suporte pelas edições do SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="6f5a5-113">For information about support for database mirroring in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
-   <span data-ttu-id="6f5a5-114">O banco de dados deve usar o modelo de recuperação completa.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-114">The database must use the full recovery model.</span></span>  
  
     <span data-ttu-id="6f5a5-115">Para obter mais informações, veja [Exibir ou alterar o modelo de recuperação de um banco de dados &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server.md) ou [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) e [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6f5a5-115">For more information, see [View or Change the Recovery Model of a Database &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server.md) or [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) and [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
-   <span data-ttu-id="6f5a5-116">O nome do banco de dados espelho deve ser igual ao nome do banco de dados principal.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-116">The name of the mirror database must be the same as the name of the principal database.</span></span>  
  
-   <span data-ttu-id="6f5a5-117">O banco de dados espelho deve estar no estado de RESTORING para espelhar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-117">The mirror database must be in the RESTORING state for mirroring to work.</span></span> <span data-ttu-id="6f5a5-118">Ao preparar um banco de dados espelho, é necessário usar RESTORE WITH NORECOVERY para todas as operações de restauração.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-118">When preparing a mirror database, you must use RESTORE WITH NORECOVERY for every restore operation.</span></span> <span data-ttu-id="6f5a5-119">Minimamente, você precisará restaurar o backup completo WITH NORECOVERY do banco de dados principal, seguido por todos os backups de log subsequentes.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-119">Minimally, you will need to restore WITH NORECOVERY a full backup of the principal database, followed by all subsequent log backups.</span></span>  
  
-   <span data-ttu-id="6f5a5-120">O sistema onde você planeja criar o banco de dados espelho deve ter uma unidade de disco com espaço suficiente para conter o banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-120">The system where you plan to create the mirror database must possesses a disk drive with sufficient space to hold the mirror database.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6f5a5-121">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="6f5a5-121">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="6f5a5-122">Não é possível espelhar os bancos de dados do sistema **mestre**, **msdb**, **temp**ou **modelo** .</span><span class="sxs-lookup"><span data-stu-id="6f5a5-122">You cannot mirror the **master**, **msdb**, **temp**, or **model** system databases.</span></span>  
  
-   <span data-ttu-id="6f5a5-123">Não é possível espelhar um banco de dados que pertence a um [grupos de disponibilidade AlwaysOn (SQL Server)](../availability-groups/windows/always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6f5a5-123">You cannot mirror a database that belongs to an [AlwaysOn Availability Groups (SQL Server)](../availability-groups/windows/always-on-availability-groups-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="6f5a5-124">Recomendações</span><span class="sxs-lookup"><span data-stu-id="6f5a5-124">Recommendations</span></span>  
  
-   <span data-ttu-id="6f5a5-125">Use um backup de banco de dados completo muito recente ou diferencial recente do banco de dados principal.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-125">Use a very recent full database backup or a recent differential database backup of the principal database.</span></span>  
  
-   <span data-ttu-id="6f5a5-126">Se um trabalho de backup de log estiver agendado para ser executado com muita frequência no banco de dados principal, talvez você precise desabilitar o trabalho de backup até o início do espelhamento.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-126">If a log backup job is scheduled to run very frequently on the principal database, you might have to disable the backup job until mirroring has started.</span></span>  
  
-   <span data-ttu-id="6f5a5-127">Se possível, o caminho (inclusive a letra da unidade) do banco de dados espelho deve ser idêntico ao caminho do banco de dados principal.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-127">If possible, the path (including the drive letter) of the mirror database should be identical to the path of the principal database.</span></span>  
  
     <span data-ttu-id="6f5a5-128">Se os caminhos dos arquivos precisarem ser diferentes, por exemplo, se o banco de dados principal estiver na unidade 'F:', mas o sistema espelho não tiver uma unidade F:, será necessário incluir a opção MOVE na instrução RESTORE.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-128">If the file paths must differ, for example, if the principal database is on drive 'F:' but the mirror system lacks an F: drive, you must include the MOVE option in the RESTORE STATEMENT.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="6f5a5-129">Ao adicionar um arquivo durante uma sessão de espelhamento sem afetá-la, é necessário que o caminho do arquivo exista nos dois servidores.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-129">Adding a file during a mirroring session without impacting the session requires that the path of the file exists on both servers.</span></span> <span data-ttu-id="6f5a5-130">Portanto, se você mover os arquivos de banco de dados quando estiver criando o banco de dados espelho, uma operação adicionar arquivo posterior pode não funcionar no banco de dados espelho e causar a suspensão do espelhamento.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-130">Therefore, if you move the database files when creating the mirror database, a later add-file operation might fail on the mirror database and cause mirroring to be suspended.</span></span> <span data-ttu-id="6f5a5-131">Para obter informações sobre como lidar com uma falha na operação de criar arquivo, veja [Solução de problemas de configuração de espelhamento de banco de dados &#40;SQL Server&#41;](troubleshoot-database-mirroring-configuration-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6f5a5-131">For information about dealing with a failed create-file operation, see [Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;](troubleshoot-database-mirroring-configuration-sql-server.md).</span></span>  
  
-   <span data-ttu-id="6f5a5-132">Se o banco de dados principal tiver catálogos de texto completo, é recomendável conferir [Espelhamento de banco de dados e catálogos de texto completo &#40;SQL Server&#41;](database-mirroring-and-full-text-catalogs-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6f5a5-132">If the principal database has any full-text catalogs, we recommend that you see [Database Mirroring and Full-Text Catalogs &#40;SQL Server&#41;](database-mirroring-and-full-text-catalogs-sql-server.md).</span></span>  
  
-   <span data-ttu-id="6f5a5-133">Em um banco de dados de produção, sempre faça backup em um dispositivo separado.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-133">For a production database, always back up to a separate device.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6f5a5-134">Segurança</span><span class="sxs-lookup"><span data-stu-id="6f5a5-134">Security</span></span>  
 <span data-ttu-id="6f5a5-135">TRUSTWORTHY é definido como OFF em um backup de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-135">TRUSTWORTHY is set to OFF when a database is backed up.</span></span> <span data-ttu-id="6f5a5-136">Portanto, em um novo banco de dados espelho, TRUSTWORTHY será sempre OFF.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-136">Therefore, TRUSTWORTHY is always OFF on a new mirror database.</span></span> <span data-ttu-id="6f5a5-137">Se o banco de dados tiver que ser confiável depois de um failover, serão necessárias etapas de instalação adicionais.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-137">If the database needs to be trustworthy after a failover, additional setup steps are necessary.</span></span> <span data-ttu-id="6f5a5-138">Para obter mais informações, veja [Configurar um banco de dados espelho para usar a propriedade confiável &#40;Transact-SQL&#41;](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="6f5a5-138">For more information, see [Set Up a Mirror Database to Use the Trustworthy Property &#40;Transact-SQL&#41;](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md).</span></span>  
  
 <span data-ttu-id="6f5a5-139">Para obter informações sobre como habilitar a decodificação automática da chave mestre de um banco de dados espelho, veja [Configurar um banco de dados espelho criptografado](set-up-an-encrypted-mirror-database.md).</span><span class="sxs-lookup"><span data-stu-id="6f5a5-139">For information about enabling automatic decryption of the database master key of a mirror database, see [Set Up an Encrypted Mirror Database](set-up-an-encrypted-mirror-database.md).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6f5a5-140">Permissões</span><span class="sxs-lookup"><span data-stu-id="6f5a5-140">Permissions</span></span>  
 <span data-ttu-id="6f5a5-141">Proprietário de banco de dados ou administrador do sistema.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-141">Database owner or system administrator.</span></span>  
  
##  <a name="to-prepare-an-existing-mirror-database-to-restart-mirroring"></a><a name="PrepareToRestartMirroring"></a> <span data-ttu-id="6f5a5-142">Para preparar um banco de dados espelho existente para reiniciar o espelhamento</span><span class="sxs-lookup"><span data-stu-id="6f5a5-142">To Prepare an Existing Mirror Database to Restart Mirroring</span></span>  
 <span data-ttu-id="6f5a5-143">Se o espelhamento foi removido e o banco de dados espelho ainda está no estado de RECOVERING, você pode reinicializar o espelhamento.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-143">If mirroring has been removed and the mirror database is still in the RECOVERING state, you can restart mirroring.</span></span>  
  
1.  <span data-ttu-id="6f5a5-144">Faça pelo menos um backup de log no banco de dados principal.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-144">Take at least one log backup on the principal database.</span></span> <span data-ttu-id="6f5a5-145">Para obter mais informações, veja [Fazer backup de um log de transações &#40;SQL Server&#41;](../../relational-databases/backup-restore/back-up-a-transaction-log-sql-server.md)).</span><span class="sxs-lookup"><span data-stu-id="6f5a5-145">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](../../relational-databases/backup-restore/back-up-a-transaction-log-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="6f5a5-146">No banco de dados espelho, use RESTORE WITH NORECOVERY para restaurar todos os backups de logs efetuados no banco de dados principal desde que o espelhamento foi removido.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-146">On the mirror database, use RESTORE WITH NORECOVERY to restore all log backups taken on the principal database since mirroring was removed.</span></span> <span data-ttu-id="6f5a5-147">Para obter mais informações, veja [Restaurar um backup de log de transações &#40;SQL Server&#41;](../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6f5a5-147">For more information, see [Restore a Transaction Log Backup &#40;SQL Server&#41;](../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md).</span></span>  
  
##  <a name="to-prepare-a-new-mirror-database"></a><a name="CombinedProcedure"></a> <span data-ttu-id="6f5a5-148">Para preparar um novo banco de dados espelho</span><span class="sxs-lookup"><span data-stu-id="6f5a5-148">To Prepare a New Mirror Database</span></span>  
 <span data-ttu-id="6f5a5-149">**Para preparar um banco de dados espelho**</span><span class="sxs-lookup"><span data-stu-id="6f5a5-149">**To prepare a mirror database**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6f5a5-150">Para obter um exemplo [!INCLUDE[tsql](../../includes/tsql-md.md)] desse procedimento, veja [Exemplo (Transact-SQL)](#TsqlExample), mais adiante nesta seção.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-150">For a [!INCLUDE[tsql](../../includes/tsql-md.md)] example of this procedure, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="6f5a5-151">Conecte-se à instância de servidor principal.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-151">Connect to principal server instance.</span></span>  
  
2.  <span data-ttu-id="6f5a5-152">Crie um backup de banco de dados completo ou diferencial do banco de dados principal.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-152">Create either a full database backup or a differential database backup of the principal database.</span></span>  
  
    -   [<span data-ttu-id="6f5a5-153">Criar um backup completo de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6f5a5-153">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md)  
  
    -   <span data-ttu-id="6f5a5-154">[Criar um backup de banco de dados diferencial &#40;SQL Server&#41;](../../relational-databases/backup-restore/create-a-differential-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6f5a5-154">[Create a Differential Database Backup &#40;SQL Server&#41;](../../relational-databases/backup-restore/create-a-differential-database-backup-sql-server.md).</span></span>  
  
3.  <span data-ttu-id="6f5a5-155">Geralmente, você precisa efetuar pelo menos um backup de log no banco de dados principal.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-155">Typically, you need to take at least one log backup on the principal database.</span></span> <span data-ttu-id="6f5a5-156">Porém, um backup de log pode ser desnecessário, caso o banco de dados tenha acabado de ser criado e nenhum backup realizado ou se o modelo de recuperação foi alterado de SIMPLE para FULL.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-156">However, a log backup might be unnecessary, if the database has just been created and no log backup has been taken yet, or if the recovery model has just been changed from SIMPLE to FULL.</span></span>  
  
    -   [<span data-ttu-id="6f5a5-157">Fazer backup de um log de transações &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6f5a5-157">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/back-up-a-transaction-log-sql-server.md)  
  
4.  <span data-ttu-id="6f5a5-158">A menos que os backups estejam em uma unidade de rede que esteja acessível de ambos os sistemas, copie o banco de dados e os backups de log para o sistema que hospedará a instância de servidor espelho.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-158">Unless the backups are on a network drive that is accessible from both systems, copy the database and log backups to the system that will host the mirror server instance.</span></span>  
  
5.  <span data-ttu-id="6f5a5-159">Conecte-se à instância de servidor espelho.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-159">Connect to mirror server instance.</span></span>  
  
6.  <span data-ttu-id="6f5a5-160">Usando RESTORE WITH NORECOVERY, crie o banco de dados espelho restaurando o backup completo do banco de dados e, opcionalmente, o backup de banco de dados diferencial mais recente, na instância do servidor espelho.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-160">Using RESTORE WITH NORECOVERY, create the mirror database by restoring the full database backup and, optionally, the most recent differential database backup, onto the mirror server instance.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6f5a5-161">Se restaurar o grupo de arquivos de banco de dados pelo grupo de arquivos, restaure todo o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-161">If you restore the database filegroup by filegroup, be sure to restore the whole database.</span></span>  
  
    -   [<span data-ttu-id="6f5a5-162">Restaurar um backup de banco de dados &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6f5a5-162">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](../../relational-databases/backup-restore/restore-a-database-backup-using-ssms.md)  
  
    -   <span data-ttu-id="6f5a5-163">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) e [RESTORE Arguments &amp;#40;Transact-SQL&amp;#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6f5a5-163">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) and [RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql).</span></span>  
  
7.  <span data-ttu-id="6f5a5-164">Usando RESTORE WITH NORECOVERY, aplique quaisquer backups de log pendentes ou backups ao banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-164">Using RESTORE WITH NORECOVERY, apply any outstanding log backup or backups to the mirror database.</span></span>  
  
    -   [<span data-ttu-id="6f5a5-165">Restaurar um backup de log de transações &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6f5a5-165">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md)  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="6f5a5-166">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6f5a5-166">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="6f5a5-167">Antes de poder iniciar uma sessão de espelhamento de banco de dados, é preciso criar o banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-167">Before you can start a database mirroring session, you must create the mirror database.</span></span> <span data-ttu-id="6f5a5-168">Isso deve ser feito antes de iniciar a sessão de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-168">You should do this just before starting the mirroring session.</span></span>  
  
 <span data-ttu-id="6f5a5-169">Esse exemplo usa o banco de dados de exemplo do [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] que, por padrão, usa o modelo de recuperação simples.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-169">This example uses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database, which uses the simple recovery model by default.</span></span>  
  
1.  <span data-ttu-id="6f5a5-170">Para usar espelhamento de banco de dados com o banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , modifique-o para usar o modelo de recuperação completa:</span><span class="sxs-lookup"><span data-stu-id="6f5a5-170">To use database mirroring with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, modify it to use the full recovery model:</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE AdventureWorks   
    SET RECOVERY FULL;  
    GO  
    ```  
  
2.  <span data-ttu-id="6f5a5-171">Depois de modificar o modelo de recuperação do banco de dados de SIMPLE para FULL, crie um backup completo, que pode ser usado para criar o banco de dados do espelho.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-171">After modifying the recovery model of the database from SIMPLE to FULL, create a full backup, which can be used to create the mirror database.</span></span> <span data-ttu-id="6f5a5-172">Como o modelo de recuperação acabou de ser alterado, a opção WITH FORMAT estará especificada para criar um novo conjunto de mídias.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-172">Because the recovery model has just been changed, the WITH FORMAT option is specified to create a new media set.</span></span> <span data-ttu-id="6f5a5-173">Isso é útil para separar os backups sob o modelo de recuperação completa de qualquer backup anterior feito sob o modelo de recuperação simples.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-173">This is useful to separate the backups under the full recovery model from any previous backups made under the simple recovery model.</span></span> <span data-ttu-id="6f5a5-174">Com a finalidade deste exemplo, o arquivo de backup (`C:\AdventureWorks.bak`) será criado na mesma unidade como o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-174">For the purpose of this example, the backup file (`C:\AdventureWorks.bak`) is created on the same drive as the database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6f5a5-175">Em um banco de dados de produção, você deve sempre fazer backup em um dispositivo separado.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-175">For a production database, you should always back up to a separate device.</span></span>  
  
     <span data-ttu-id="6f5a5-176">Na instância de servidor principal (em `PARTNERHOST1`), crie um backup completo do banco de dados principal conforme segue:</span><span class="sxs-lookup"><span data-stu-id="6f5a5-176">On the principal server instance (on `PARTNERHOST1`), create a full backup of the principal database as follows:</span></span>  
  
    ```  
    BACKUP DATABASE AdventureWorks   
        TO DISK = 'C:\AdventureWorks.bak'   
        WITH FORMAT  
    GO  
    ```  
  
3.  <span data-ttu-id="6f5a5-177">Copiar o backup completo para servidor espelho.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-177">Copy the full backup to the mirror server.</span></span>  
  
4.  <span data-ttu-id="6f5a5-178">Usando RESTORE WITH NORECOVERY, restaure o backup completo na instância do servidor espelho.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-178">Using RESTORE WITH NORECOVERY, restore the full backup onto the mirror server instance.</span></span> <span data-ttu-id="6f5a5-179">O comando para restaurar depende que os caminhos dos bancos de dados principal e espelho sejam idênticos.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-179">The restore command depends on whether the paths of principal and mirror databases are identical.</span></span>  
  
    -   <span data-ttu-id="6f5a5-180">**Se os caminhos forem idênticos:**</span><span class="sxs-lookup"><span data-stu-id="6f5a5-180">**If the paths are identical:**</span></span>  
  
         <span data-ttu-id="6f5a5-181">Na instância de servidor espelho (em `PARTNERHOST5`), restaure o backup completo conforme a seguir:</span><span class="sxs-lookup"><span data-stu-id="6f5a5-181">On the mirror server instance (on `PARTNERHOST5`), restore the full backup as follows:</span></span>  
  
        ```  
        RESTORE DATABASE AdventureWorks   
            FROM DISK = 'C:\AdventureWorks.bak'   
            WITH NORECOVERY  
        GO  
        ```  
  
    -   <span data-ttu-id="6f5a5-182">**Se os caminhos forem diferentes:**</span><span class="sxs-lookup"><span data-stu-id="6f5a5-182">**If the paths differ:**</span></span>  
  
         <span data-ttu-id="6f5a5-183">Se o caminho do banco de dados espelho for diferente do caminho do banco de dados principal (por exemplo, as letras da unidade são diferentes), crie o banco de dados espelho requer que a operação de restauração inclua uma cláusula MOVE.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-183">If the path of the mirror database differs from the path of the principal database (for instance, their drive letters differ), creating the mirror database requires that the restore operation include a MOVE clause.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="6f5a5-184">Se os nomes do caminho dos bancos de dados espelho e principal forem diferentes, não será possível adicionar um arquivo.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-184">If the path names of the principal and mirror databases differ, you cannot add a file.</span></span> <span data-ttu-id="6f5a5-185">Isso acontece porque, ao receber o log para a operação do arquivo adicionado, a instância do servidor espelho tenta colocar o novo arquivo no local usado pelo banco de dados principal.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-185">This is because on receiving the log for the add file operation, the mirror server instance attempts to place the new file in the location used by the principal database.</span></span>  
  
         <span data-ttu-id="6f5a5-186">Por exemplo, o seguinte comando restaura um backup de um banco de dados principal que está em C:\Arquivos de Programas\Microsoft SQL Server\MSSQL.*n*\MSSQL\Data\ para um local diferente, D:\Arquivos de Programas\Microsoft SQL Server\MSSQL.*n*\MSSQL\Dat`a\`, em que o banco de dados espelho reside.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-186">For example, the following command restores a backup of a principal database residing in C:\Program Files\Microsoft SQL Server\MSSQL.*n*\MSSQL\Data\ to a different location, D:\Program Files\Microsoft SQL Server\MSSQL.*n*\MSSQL\Dat`a\`, where the mirror database is to reside.</span></span>  
  
        ```  
        RESTORE DATABASE AdventureWorks  
           FROM DISK='C:\AdventureWorks.bak'  
           WITH NORECOVERY,   
              MOVE 'AdventureWorks_Data' TO   
                 'D:\Program Files\Microsoft SQL Server\MSSQL.n\MSSQL\Data\AdventureWorks_Data.mdf',   
              MOVE 'AdventureWorks_Log' TO  
                 'D:\Program Files\Microsoft SQL Server\MSSQL.n\MSSQL\Data\AdventureWorks_Log.ldf';  
        GO  
        ```  
  
5.  <span data-ttu-id="6f5a5-187">Depois de criar o backup completo, deve-se criar um backup de log no banco de dados principal.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-187">After you create the full backup, you must create a log backup on the principal database.</span></span> <span data-ttu-id="6f5a5-188">Por exemplo, a seguinte instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] faz o backup de log ao mesmo arquivo usado pelo backup completo anterior:</span><span class="sxs-lookup"><span data-stu-id="6f5a5-188">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement backs up the log to the same file used by the preceding full backup:</span></span>  
  
    ```  
    BACKUP LOG AdventureWorks   
        TO DISK = 'C:\AdventureWorks.bak'   
    GO  
    ```  
  
6.  <span data-ttu-id="6f5a5-189">Antes de poder iniciar o espelhamento, é necessário aplicar o backup de log exigido (e qualquer backup de log subsequente).</span><span class="sxs-lookup"><span data-stu-id="6f5a5-189">Before you can start mirroring, you must apply the required log backup (and any subsequent log backups).</span></span>  
  
     <span data-ttu-id="6f5a5-190">Por exemplo, a seguinte instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] restaura o primeiro log do `C:\AdventureWorks.bak`:</span><span class="sxs-lookup"><span data-stu-id="6f5a5-190">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement restores the first log from `C:\AdventureWorks.bak`:</span></span>  
  
    ```  
    RESTORE LOG AdventureWorks   
        FROM DISK = 'C:\AdventureWorks.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    ```  
  
7.  <span data-ttu-id="6f5a5-191">Se qualquer backup de log adicional ocorrer antes de começar o espelhamento, deve-se também restaurar todos os backups de log, em sequência, ao servidor espelho usando WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-191">If any additional log backups occur before you start mirroring, you must also restore all of those log backups, in sequence, to the mirror server using WITH NORECOVERY.</span></span>  
  
     <span data-ttu-id="6f5a5-192">Por exemplo, a instrução seguinte [!INCLUDE[tsql](../../includes/tsql-md.md)] restaura dois logs adicionais de `C:\AdventureWorks.bak`:</span><span class="sxs-lookup"><span data-stu-id="6f5a5-192">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement restores two additional logs from `C:\AdventureWorks.bak`:</span></span>  
  
    ```  
    RESTORE LOG AdventureWorks   
        FROM DISK = 'C:\AdventureWorks.bak'   
        WITH FILE=2, NORECOVERY  
    GO  
    RESTORE LOG AdventureWorks   
        FROM DISK = 'C:\AdventureWorks.bak'   
        WITH FILE=3, NORECOVERY  
    GO  
    ```  
  
 <span data-ttu-id="6f5a5-193">Para obter um exemplo completo de configuração de espelhamento de banco de dados, exibição da configuração de segurança, preparo do banco de dados espelho, configuração de parceiros e adição de uma testemunha, veja [Configurando o espelhamento de banco de dados &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6f5a5-193">For a complete example of setting up database mirroring, showing security setup, preparing the mirror database, setting up the partners, and adding a witness, see [Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-preparing-a-mirror-database"></a><a name="FollowUp"></a> <span data-ttu-id="6f5a5-194">Acompanhamento: depois de preparar um banco de dados espelho</span><span class="sxs-lookup"><span data-stu-id="6f5a5-194">Follow Up: After Preparing a Mirror Database</span></span>  
  
1.  <span data-ttu-id="6f5a5-195">Se algum backup de log adicional tiver sido realizado desde sua operação RESTORE LOG mais recente, você deverá aplicar manualmente todos os backups de log adicionais, usando RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-195">If any additional log backups have been taken since your most recent RESTORE LOG operation, you must manually apply every additional log backup, using RESTORE WITH NORECOVERY.</span></span>  
  
2.  <span data-ttu-id="6f5a5-196">Inicie a sessão de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-196">Start the mirroring session.</span></span> <span data-ttu-id="6f5a5-197">Para obter mais informações, veja [Estabelecer uma sessão de espelhamento de banco de dados usando a Autenticação do Windows &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md) ou o [Estabelecer uma sessão de espelhamento de banco de dados com a Autenticação do Windows &#40;Transact-SQL&#41;](database-mirroring-establish-session-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="6f5a5-197">For more information, see [Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md) or [Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;](database-mirroring-establish-session-windows-authentication.md).</span></span>  
  
3.  <span data-ttu-id="6f5a5-198">Se você desabilitou o trabalho de backup no banco de dados principal, reabilite o trabalho.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-198">If you disabled the backup job on the principal database, reenable the job.</span></span>  
  
4.  <span data-ttu-id="6f5a5-199">Se o banco de dados precisar estar confiável após um failover, serão necessárias etapas adicionais de instalação após o início do espelhamento.</span><span class="sxs-lookup"><span data-stu-id="6f5a5-199">If the database needs to be trustworthy after a failover, extra setup steps are necessary after mirroring begins.</span></span> <span data-ttu-id="6f5a5-200">Para obter mais informações, veja [Configurar um banco de dados espelho para usar a propriedade confiável &#40;Transact-SQL&#41;](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="6f5a5-200">For more information, see [Set Up a Mirror Database to Use the Trustworthy Property &#40;Transact-SQL&#41;](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="6f5a5-201">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="6f5a5-201">Related Tasks</span></span>  
  
-   [<span data-ttu-id="6f5a5-202">Criar um backup completo de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6f5a5-202">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="6f5a5-203">Restaurar um backup de log de transações &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6f5a5-203">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md)  
  
-   [<span data-ttu-id="6f5a5-204">Estabelecer uma sessão de espelhamento de banco de dados usando a Autenticação do Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6f5a5-204">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="6f5a5-205">Estabelecer uma sessão de espelhamento de banco de dados com a Autenticação do Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6f5a5-205">Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](database-mirroring-establish-session-windows-authentication.md)  
  
-   [<span data-ttu-id="6f5a5-206">Configurar um banco de dados espelho criptografado</span><span class="sxs-lookup"><span data-stu-id="6f5a5-206">Set Up an Encrypted Mirror Database</span></span>](set-up-an-encrypted-mirror-database.md)  
  
-   [<span data-ttu-id="6f5a5-207">Configurar um banco de dados espelho para usar a propriedade confiável &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6f5a5-207">Set Up a Mirror Database to Use the Trustworthy Property &#40;Transact-SQL&#41;</span></span>](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="6f5a5-208">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6f5a5-208">See Also</span></span>  
 <span data-ttu-id="6f5a5-209">[Espelhamento de banco de dados &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6f5a5-209">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="6f5a5-210">[Segurança de transporte para espelhamento de banco de dados e Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="6f5a5-210">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="6f5a5-211">[Configurando o espelhamento de banco de dados &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6f5a5-211">[Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="6f5a5-212">[Fazer backup e restaurar índices e catálogos de texto completo](../../relational-databases/indexes/indexes.md) </span><span class="sxs-lookup"><span data-stu-id="6f5a5-212">[Back Up and Restore Full-Text Catalogs and Indexes](../../relational-databases/indexes/indexes.md) </span></span>  
 <span data-ttu-id="6f5a5-213">[Espelhamento de banco de dados e catálogos de texto completo &#40;SQL Server&#41;](database-mirroring-and-full-text-catalogs-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6f5a5-213">[Database Mirroring and Full-Text Catalogs &#40;SQL Server&#41;](database-mirroring-and-full-text-catalogs-sql-server.md) </span></span>  
 <span data-ttu-id="6f5a5-214">[Espelhamento e replicação de banco de dados &#40;SQL Server&#41;](database-mirroring-and-replication-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6f5a5-214">[Database Mirroring and Replication &#40;SQL Server&#41;](database-mirroring-and-replication-sql-server.md) </span></span>  
 <span data-ttu-id="6f5a5-215">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6f5a5-215">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="6f5a5-216">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6f5a5-216">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="6f5a5-217">Argumentos de RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6f5a5-217">RESTORE Arguments &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-arguments-transact-sql)  
  
  
