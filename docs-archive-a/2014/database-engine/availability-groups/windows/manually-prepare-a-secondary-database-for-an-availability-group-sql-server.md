---
title: Preparar um banco de dados secundário manualmente para um grupo de disponibilidade (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.configsecondarydbs.f1
- sql12.swb.availabilitygroup.preparedbs.f1
helpviewer_keywords:
- secondary databases [SQL Server], in availability group
- secondary databases [SQL Server]
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], databases
ms.assetid: 9f2feb3c-ea9b-4992-8202-2aeed4f9a6dd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3da3f7332bdabce65785b2844157dd4639389254
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572192"
---
# <a name="manually-prepare-a-secondary-database-for-an-availability-group-sql-server"></a><span data-ttu-id="77c54-102">Preparar um banco de dados secundário manualmente para um grupo de disponibilidade (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="77c54-102">Manually Prepare a Secondary Database for an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="77c54-103">Este tópico descreve como preparar um banco de dados secundário para um grupo de disponibilidade AlwaysOn no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], o [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77c54-103">This topic describes how to prepare a secondary database for an AlwaysOn availability group in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span> <span data-ttu-id="77c54-104">A preparação de um banco de dados secundário exige duas etapas: (1) restaurar um backup recente do banco de dados primário e os backups de log subsequentes em cada instância do servidor que hospede a réplica secundária, usando RESTORE WITH NORECOVERY e (2) unir o banco de dados restaurado ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="77c54-104">Preparing a secondary database requires two steps: (1) restoring a recent database backup of the primary database and subsequent log backups onto each server instance that hosts the secondary replica, using RESTORE WITH NORECOVERY, and (2) joining the restored database to the availability group.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="77c54-105">Se você tiver uma configuração de envio de logs existente, poderá ser capaz de converter o banco de dados primários de envio de logs junto com um ou mais de seus bancos de dados secundários em um banco de dados primário AlwaysOn e um ou mais bancos de dados secundários AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="77c54-105">If you have an existing log shipping configuration, you might be able to convert the log shipping primary database along with one or more of its secondary databases to an AlwaysOn primary database and one or more AlwaysOn secondary databases.</span></span> <span data-ttu-id="77c54-106">Para obter mais informações, consulte [pré-requisitos para migrar do envio de logs para Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](prereqs-migrating-log-shipping-to-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="77c54-106">For more information, see [Prerequisites for Migrating from Log Shipping to AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-migrating-log-shipping-to-always-on-availability-groups.md).</span></span>  
  
-   <span data-ttu-id="77c54-107">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="77c54-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="77c54-108">Pré-requisitos e restrições</span><span class="sxs-lookup"><span data-stu-id="77c54-108">Prerequisites and Restrictions</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="77c54-109">Recomendações</span><span class="sxs-lookup"><span data-stu-id="77c54-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="77c54-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="77c54-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="77c54-111">**Para preparar um banco de dados secundário, usando:**</span><span class="sxs-lookup"><span data-stu-id="77c54-111">**To prepare a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="77c54-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="77c54-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="77c54-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="77c54-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="77c54-114">PowerShell</span><span class="sxs-lookup"><span data-stu-id="77c54-114">PowerShell</span></span>](#PowerShellProcedure)  
  
-   [<span data-ttu-id="77c54-115">Tarefas relacionadas a backup e restauração</span><span class="sxs-lookup"><span data-stu-id="77c54-115">Related Backup and Restore Tasks</span></span>](#RelatedTasks)  
  
-   <span data-ttu-id="77c54-116">**Acompanhamento** [depois de preparar um banco de dados secundário](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="77c54-116">**Follow Up:** [After Preparing a Secondary Database](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="77c54-117">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="77c54-117">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="77c54-118">Pré-requisitos e restrições</span><span class="sxs-lookup"><span data-stu-id="77c54-118">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="77c54-119">Verifique se o sistema onde você planeja colocar o banco de dados possui um disco com espaço suficiente para os bancos de dados secundários.</span><span class="sxs-lookup"><span data-stu-id="77c54-119">Make sure that the system where you plan to place database possesses a disk drive with sufficient space for the secondary databases.</span></span>  
  
-   <span data-ttu-id="77c54-120">O nome do banco de dados secundário deve ser igual ao nome do banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="77c54-120">The name of the secondary database must be the same as the name of the primary database.</span></span>  
  
-   <span data-ttu-id="77c54-121">Use RESTORE WITH NORECOVERY para cada operação de restauração.</span><span class="sxs-lookup"><span data-stu-id="77c54-121">Use RESTORE WITH NORECOVERY for every restore operation.</span></span>  
  
-   <span data-ttu-id="77c54-122">Se o banco de dados secundário precisar residir em um caminho de arquivo diferente (inclusive a letra da unidade) do banco de dados primário, o comando de restauração também deve usar a opção WITH MOVE para cada um dos arquivos de banco de dados para especificar o caminho do banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="77c54-122">If the secondary database needs to reside on a different file path (including the drive letter) than the primary database, the restore command must also use the WITH MOVE option for each of the database files to specify them to the path of the secondary database.</span></span>  
  
-   <span data-ttu-id="77c54-123">Se restaurar o grupo de arquivos de banco de dados pelo grupo de arquivos, restaure todo o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="77c54-123">If you restore the database filegroup by filegroup, be sure to restore the whole database.</span></span>  
  
-   <span data-ttu-id="77c54-124">Depois de restaurar o banco de dados, você deve restaurar (WITH NORECOVERY) cada backup de log criado desde o último backup de dados restaurado.</span><span class="sxs-lookup"><span data-stu-id="77c54-124">After restoring the database, you must restore (WITH NORECOVERY) every log backup created since the last restored data backup.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="77c54-125">Recomendações</span><span class="sxs-lookup"><span data-stu-id="77c54-125">Recommendations</span></span>  
  
-   <span data-ttu-id="77c54-126">Em instâncias autônomas do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], é recomendável que, se possível, o caminho do arquivo (incluindo a letra da unidade) de um determinado banco de dados secundário seja idêntico ao caminho do banco de dados primário correspondente.</span><span class="sxs-lookup"><span data-stu-id="77c54-126">On stand-alone instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], we recommend that, if possible, the file path (including the drive letter) of a given secondary database be identical to the path of the corresponding primary database.</span></span> <span data-ttu-id="77c54-127">Isso ocorre porque, se você mover os arquivos de banco de dados ao criar um banco de dados secundário, uma operação de adição de arquivo posterior poderá apresentar falha no banco de dados secundário e fazer com que o banco de dados secundário seja suspenso.</span><span class="sxs-lookup"><span data-stu-id="77c54-127">This is because if you move the database files when creating a secondary database, a later add-file operation might fail on the secondary database and cause the secondary database to be suspended.</span></span>  
  
-   <span data-ttu-id="77c54-128">Antes de preparar seus bancos de dados secundários, é altamente recomendável suspender os backups de log agendados nos bancos de dados no grupo de disponibilidade até que a inicialização das réplicas secundárias seja concluída.</span><span class="sxs-lookup"><span data-stu-id="77c54-128">Before preparing your secondary databases, we strongly recommend that you suspend scheduled log backups on the databases in the availability group until the initialization of secondary replicas has completed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="77c54-129">Segurança</span><span class="sxs-lookup"><span data-stu-id="77c54-129">Security</span></span>  
 <span data-ttu-id="77c54-130">Quando é feito backup de um banco de dados, a [propriedade TRUSTWORTHY do banco de dados](../../../relational-databases/security/trustworthy-database-property.md) é definida como off.</span><span class="sxs-lookup"><span data-stu-id="77c54-130">When a database is backed up, the [TRUSTWORTHY database property](../../../relational-databases/security/trustworthy-database-property.md) is set to OFF.</span></span> <span data-ttu-id="77c54-131">Portanto, em um banco de dados recém-restaurado, TRUSTWORTHY sempre será OFF.</span><span class="sxs-lookup"><span data-stu-id="77c54-131">Therefore, TRUSTWORTHY is always OFF on a newly restored database.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="77c54-132">Permissões</span><span class="sxs-lookup"><span data-stu-id="77c54-132">Permissions</span></span>  
 <span data-ttu-id="77c54-133">As permissões BACKUP DATABASE e BACKUP LOG usam como padrão os membros da função de servidor fixa **sysadmin** e as funções de banco de dados fixas **db_owner** e **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="77c54-133">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span> <span data-ttu-id="77c54-134">Para obter mais informações, veja [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="77c54-134">For more information, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
 <span data-ttu-id="77c54-135">Quando o banco de dados que está sendo restaurado não existir na instância do servidor, a instrução RESTORE exigirá as permissões CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="77c54-135">When the database being restored does not exist on the server instance, the RESTORE statement requires CREATE DATABASE permissions.</span></span> <span data-ttu-id="77c54-136">Para obter mais informações, veja [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="77c54-136">For more information, see [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="77c54-137">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="77c54-137">Using SQL Server Management Studio</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="77c54-138"> Os caminhos de arquivos de backup e restauração forem idênticos entre a instância do servidor que hospeda a réplica primária e todas as instâncias que hospedam uma réplica secundária, você deverá ser capaz de criar bancos de dados secundários usando [Assistente de Novo Grupo de Disponibilidade](use-the-availability-group-wizard-sql-server-management-studio.md), [Assistente para Adicionar Réplica a Grupo de Disponibilidade](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)ou [Assistente para Adicionar Banco de Dados ao Grupo de Disponibilidade](availability-group-add-database-to-group-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="77c54-138">If the backup and restore file paths are identical between the server instance that hosts the primary replica and every instance that hosts a secondary replica, you should be able create secondary databases by using [New Availability Group Wizard](use-the-availability-group-wizard-sql-server-management-studio.md), [Add Replica to Availability Group Wizard](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md), or [Add Database to Availability Group Wizard](availability-group-add-database-to-group-wizard.md).</span></span>  
  
 <span data-ttu-id="77c54-139">**Para preparar um banco de dados secundário**</span><span class="sxs-lookup"><span data-stu-id="77c54-139">**To prepare a secondary database**</span></span>  
  
1.  <span data-ttu-id="77c54-140">A menos que você já tenha um backup recente do banco de dados primário, crie um novo backup completo ou diferencial do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="77c54-140">Unless you already have a recent database backup of the primary database, create a new full or differential database backup.</span></span> <span data-ttu-id="77c54-141">Como prática recomendada, coloque esse backup e qualquer backup de log subsequente no compartilhamento de rede recomendado.</span><span class="sxs-lookup"><span data-stu-id="77c54-141">As a best practice, place this backup and any subsequent log backups onto the recommended network share.</span></span>  
  
2.  <span data-ttu-id="77c54-142">Crie pelo menos um novo backup de log do banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="77c54-142">Create at least one new log backup of the primary database.</span></span>  
  
3.  <span data-ttu-id="77c54-143">Na instância do servidor que hospeda a réplica secundária, restaure o backup completo do banco de dados primário (e opcionalmente um backup diferencial) seguido por quaisquer backups de log subsequentes.</span><span class="sxs-lookup"><span data-stu-id="77c54-143">On the server instance that hosts the secondary replica, restore the full database backup of the primary database (and optionally a differential backup) followed by any subsequent log backups.</span></span>  
  
     <span data-ttu-id="77c54-144">Na página **Opções de RESTORE DATABASE** , selecione **Deixar o banco de dados não operacional e não reverter as transações não confirmadas. Os logs de transações adicionais podem ser restaurados. (RESTAURAR COM NORECOVERY)**.</span><span class="sxs-lookup"><span data-stu-id="77c54-144">On the **RESTORE DATABASEOptions** page, select **Leave the database non-operational, and do not roll back the uncommitted transactions. Additional transaction logs can be restored. (RESTORE WITH NORECOVERY)**.</span></span>  
  
     <span data-ttu-id="77c54-145">Se os caminhos de arquivo dos bancos de dados primário e secundário forem diferentes, por exemplo, se o banco de dados primário estiver na unidade 'F:', mas a instância do servidor que hospeda a réplica secundária não tiver uma unidade F:, inclua a opção MOVE na cláusula WITH.</span><span class="sxs-lookup"><span data-stu-id="77c54-145">If the file paths of the primary database and the secondary database differ, for example, if the primary database is on drive 'F:' but the server instance that hosts the secondary replica lacks an F: drive, include the MOVE option in your WITH clause.</span></span>  
  
4.  <span data-ttu-id="77c54-146">Para concluir a configuração do banco de dados secundário, você precisa unir o banco de dados secundário ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="77c54-146">To complete configuration of the secondary database, you need to join the secondary database to the availability group.</span></span> <span data-ttu-id="77c54-147">Para obter mais informações, veja [Unir um banco de dados secundário a um grupo de disponibilidade &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="77c54-147">For more information, [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="77c54-148"> Para obter informações sobre como executar estas operações de backup e restauração, consulte [Tarefas relacionadas a backup e restauração](#RelatedTasks), posteriormente nesta seção.</span><span class="sxs-lookup"><span data-stu-id="77c54-148">For information about how to perform these backup and restore operations, see [Related Backup and Restore Tasks](#RelatedTasks), later in this section.</span></span>  
  
###  <a name="related-backup-and-restore-tasks"></a><a name="RelatedTasks"></a><span data-ttu-id="77c54-149">Tarefas de backup e restauração relacionadas</span><span class="sxs-lookup"><span data-stu-id="77c54-149">Related Backup and Restore Tasks</span></span>  
 <span data-ttu-id="77c54-150">**Para criar um backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="77c54-150">**To create a database backup**</span></span>  
  
-   [<span data-ttu-id="77c54-151">Criar um backup completo de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="77c54-151">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="77c54-152">Criar um backup diferencial de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="77c54-152">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/create-a-differential-database-backup-sql-server.md)  
  
 <span data-ttu-id="77c54-153">**Para criar um backup do log**</span><span class="sxs-lookup"><span data-stu-id="77c54-153">**To create a log backup**</span></span>  
  
-   [<span data-ttu-id="77c54-154">Fazer backup de um log de transações &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="77c54-154">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/back-up-a-transaction-log-sql-server.md)  
  
 <span data-ttu-id="77c54-155">**Para restaurar backups**</span><span class="sxs-lookup"><span data-stu-id="77c54-155">**To restore backups**</span></span>  
  
-   [<span data-ttu-id="77c54-156">Restaurar um backup de banco de dados &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="77c54-156">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](../../../relational-databases/backup-restore/restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="77c54-157">Restaurar um backup de banco de dados diferencial &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="77c54-157">Restore a Differential Database Backup &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/restore-a-differential-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="77c54-158">Restaurar um backup de log de transações &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="77c54-158">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md)  
  
-   [<span data-ttu-id="77c54-159">Restaurar um banco de dados em um novo local &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="77c54-159">Restore a Database to a New Location &#40;SQL Server&#41;</span></span>](../../../relational-databases/backup-restore/restore-a-database-to-a-new-location-sql-server.md)  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="77c54-160">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="77c54-160">Using Transact-SQL</span></span>  
 <span data-ttu-id="77c54-161">**Para preparar um banco de dados secundário**</span><span class="sxs-lookup"><span data-stu-id="77c54-161">**To prepare a secondary database**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="77c54-162">Para obter um exemplo desse procedimento, veja [Exemplo (Transact-SQL)](#ExampleTsql), acima neste tópico.</span><span class="sxs-lookup"><span data-stu-id="77c54-162">For an example of this procedure, see [Example (Transact-SQL)](#ExampleTsql), earlier in this topic.</span></span>  
  
1.  <span data-ttu-id="77c54-163">A menos que você tenha um backup completo recente do banco de dados primário, conecte-se à instância do servidor que hospeda a réplica primária e crie um backup completo do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="77c54-163">Unless you have a recent full backup of the primary database, connect to the server instance that hosts the primary replica and create a full database backup.</span></span> <span data-ttu-id="77c54-164">Como prática recomendada, coloque esse backup e qualquer backup de log subsequente no compartilhamento de rede recomendado.</span><span class="sxs-lookup"><span data-stu-id="77c54-164">As a best practice, place this backup and any subsequent log backups onto the recommended network share.</span></span>  
  
2.  <span data-ttu-id="77c54-165">Na instância do servidor que hospeda a réplica secundária, restaure o backup completo do banco de dados primário (e opcionalmente um backup diferencial) seguido por todos os backups de log subsequentes.</span><span class="sxs-lookup"><span data-stu-id="77c54-165">On the server instance that hosts the secondary replica, restore the full database backup of the primary database (and optionally a differential backup) followed by all subsequent log backups.</span></span> <span data-ttu-id="77c54-166">Use WITH NORECOVERY para cada operação de restauração.</span><span class="sxs-lookup"><span data-stu-id="77c54-166">Use WITH NORECOVERY for every restore operation.</span></span>  
  
     <span data-ttu-id="77c54-167">Se os caminhos de arquivo dos bancos de dados primário e secundário forem diferentes, por exemplo, se o banco de dados primário estiver na unidade 'F:', mas a instância do servidor que hospeda a réplica secundária não tiver uma unidade F:, inclua a opção MOVE na cláusula WITH.</span><span class="sxs-lookup"><span data-stu-id="77c54-167">If the file paths of the primary database and the secondary database differ, for example, if the primary database is on drive 'F:' but the server instance that hosts the secondary replica lacks an F: drive, include the MOVE option in your WITH clause.</span></span>  
  
3.  <span data-ttu-id="77c54-168">Se quaisquer backups de log tiverem sido executados no banco de dados primário desde o backup de log necessário, será necessário copiá-los na instância do servidor que hospeda a réplica secundária e aplicar cada um desses backups de log ao banco de dados secundário, começando com o mais recente e sempre usando RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="77c54-168">If any log backups have been taken on the primary database since the required log backup, you must also copy these to the server instance that hosts the secondary replica and apply each of those log backups to the secondary database, starting with the earliest and always using RESTORE WITH NORECOVERY.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="77c54-169">Um backup de log não existirá se o banco de dados primário tiver acabado de ser criado, e nenhum backup de log tiver sido executado ainda, ou se o modelo de recuperação tiver acabado de ser alterado de simples para completo.</span><span class="sxs-lookup"><span data-stu-id="77c54-169">A log backup would not exist if the primary database has just been created and no log backup has been taken yet or if the recovery model has just been changed from simple to full.</span></span>  
  
4.  <span data-ttu-id="77c54-170">Para concluir a configuração do banco de dados secundário, você precisa unir o banco de dados secundário ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="77c54-170">To complete configuration of the secondary database, you need to join the secondary database to the availability group.</span></span> <span data-ttu-id="77c54-171">Para obter mais informações, veja [Unir um banco de dados secundário a um grupo de disponibilidade &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="77c54-171">For more information, [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="77c54-172"> Para obter informações sobre como executar estas operações de backup e restauração, consulte [Tarefas relacionadas a backup e restauração](#RelatedTasks), posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="77c54-172">For information about how to perform these backup and restore operations, see [Related Backup and Restore Tasks](#RelatedTasks), later in this topic.</span></span>  
  
###  <a name="transact-sql-example"></a><a name="ExampleTsql"></a><span data-ttu-id="77c54-173">Exemplo de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="77c54-173">Transact-SQL Example</span></span>  
 <span data-ttu-id="77c54-174">O exemplo a seguir prepara um banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="77c54-174">The following example prepares a secondary database.</span></span> <span data-ttu-id="77c54-175">Esse exemplo usa o banco de dados de exemplo do [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] que, por padrão, usa o modelo de recuperação simples.</span><span class="sxs-lookup"><span data-stu-id="77c54-175">This example uses the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] sample database, which uses the simple recovery model by default.</span></span>  
  
1.  <span data-ttu-id="77c54-176">Para usar o banco de dados [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] , modifique-o para usar o modelo de recuperação completa:</span><span class="sxs-lookup"><span data-stu-id="77c54-176">To use the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database, modify it to use the full recovery model:</span></span>  
  
    ```sql
    USE master;  
    GO  
    ALTER DATABASE MyDB1   
    SET RECOVERY FULL;  
    GO  
    ```  
  
2.  <span data-ttu-id="77c54-177">Depois de modificar o modelo de recuperação do banco de dados de SIMPLE para FULL, crie um backup completo, que pode ser usado para criar o banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="77c54-177">After modifying the recovery model of the database from SIMPLE to FULL, create a full backup, which can be used to create the secondary database.</span></span> <span data-ttu-id="77c54-178">Como o modelo de recuperação acabou de ser alterado, a opção WITH FORMAT estará especificada para criar um novo conjunto de mídias.</span><span class="sxs-lookup"><span data-stu-id="77c54-178">Because the recovery model has just been changed, the WITH FORMAT option is specified to create a new media set.</span></span> <span data-ttu-id="77c54-179">Isso é útil para separar os backups sob o modelo de recuperação completa de qualquer backup anterior feito sob o modelo de recuperação simples.</span><span class="sxs-lookup"><span data-stu-id="77c54-179">This is useful to separate the backups under the full recovery model from any previous backups made under the simple recovery model.</span></span> <span data-ttu-id="77c54-180">Para a finalidade deste exemplo, o arquivo de backup (C:\\[!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)].bak) será criado na mesma unidade que o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="77c54-180">For the purpose of this example, the backup file (C:\\[!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)].bak) is created on the same drive as the database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="77c54-181">Em um banco de dados de produção, você deve sempre fazer backup em um dispositivo separado.</span><span class="sxs-lookup"><span data-stu-id="77c54-181">For a production database, you should always back up to a separate device.</span></span>  
  
     <span data-ttu-id="77c54-182">Na instância do servidor que hospeda a réplica primária (`INSTANCE01`), crie um backup completo do banco de dados primário da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="77c54-182">On the server instance that hosts the primary replica (`INSTANCE01`), create a full backup of the primary database as follows:</span></span>  
  
    ```sql
    BACKUP DATABASE MyDB1   
        TO DISK = 'C:\MyDB1.bak'   
        WITH FORMAT  
    GO  
    ```  
  
3.  <span data-ttu-id="77c54-183">Copie o backup completo na instância do servidor que hospeda a réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="77c54-183">Copy the full backup to the server instance that hosts the secondary replica.</span></span>  
  
4.  <span data-ttu-id="77c54-184">Restaure o backup completo usando RESTORE WITH NORECOVERY na instância do servidor que hospeda a réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="77c54-184">Restore the full backup, using RESTORE WITH NORECOVERY, onto the server instance that hosts the secondary replica.</span></span> <span data-ttu-id="77c54-185">O comando de restauração depende de se os caminhos dos bancos de dados primário e secundário são idênticos.</span><span class="sxs-lookup"><span data-stu-id="77c54-185">The restore command depends on whether the paths of primary and secondary databases are identical.</span></span>  
  
    -   <span data-ttu-id="77c54-186">**Se os caminhos forem idênticos:**</span><span class="sxs-lookup"><span data-stu-id="77c54-186">**If the paths are identical:**</span></span>  
  
         <span data-ttu-id="77c54-187">No computador que hospeda a réplica secundária, restaure o backup completo da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="77c54-187">On the computer that hosts the secondary replica, restore the full backup as follows:</span></span>  
  
        ```sql
        RESTORE DATABASE MyDB1   
            FROM DISK = 'C:\MyDB1.bak'   
            WITH NORECOVERY  
        GO  
        ```  
  
    -   <span data-ttu-id="77c54-188">**Se os caminhos forem diferentes:**</span><span class="sxs-lookup"><span data-stu-id="77c54-188">**If the paths differ:**</span></span>  
  
         <span data-ttu-id="77c54-189">Se o caminho do banco de dados secundário for diferente do caminho do banco de dados primário (por exemplo, se as letras das unidades forem diferentes), a criação do banco de dados secundário exigirá que a operação de restauração inclua uma cláusula MOVE.</span><span class="sxs-lookup"><span data-stu-id="77c54-189">If the path of the secondary database differs from the path of the primary database (for instance, their drive letters differ), creating the secondary database requires that the restore operation include a MOVE clause.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="77c54-190">Se os nomes dos caminhos dos bancos de dados primário e secundário forem diferentes, não será possível adicionar um arquivo.</span><span class="sxs-lookup"><span data-stu-id="77c54-190">If the path names of the primary and secondary databases differ, you cannot add a file.</span></span> <span data-ttu-id="77c54-191">Isso acontece porque, ao receber o log para a operação de adição de arquivo, a instância do servidor da réplica secundária tenta colocar o novo arquivo no mesmo caminho usado pelo banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="77c54-191">This is because on receiving the log for the add file operation, the server instance of the secondary replica attempts to place the new file in the same path as used by the primary database.</span></span>  
  
         <span data-ttu-id="77c54-192">Por exemplo, o comando a seguir restaura um backup de um banco de dados primário que reside no diretório de dados da instância padrão do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], C:\Arquivos de Programas\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA.</span><span class="sxs-lookup"><span data-stu-id="77c54-192">For example, the following command restores a backup of a primary database that resides in the data directory of the default instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA.</span></span> <span data-ttu-id="77c54-193">A operação Restore Database deve mover o banco de dados para o diretório data de uma instância remota de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] named (*AlwaysOn1*), que hospeda a réplica secundária em outro nó de cluster.</span><span class="sxs-lookup"><span data-stu-id="77c54-193">The restore database operation must move the database to the data directory of a remote instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] named  (*AlwaysOn1*), which hosts the secondary replica on another cluster node.</span></span> <span data-ttu-id="77c54-194">Lá, os arquivos de dados e de log são restaurados para *c:\Arquivos de PROGRAMAS\MICROSOFT SQL Server\MSSQL12. Diretório ALWAYSON1\MSSQL\DATA*</span><span class="sxs-lookup"><span data-stu-id="77c54-194">There, the data and log files are restored to the *C:\Program Files\Microsoft SQL Server\MSSQL12.ALWAYSON1\MSSQL\DATA* directory .</span></span> <span data-ttu-id="77c54-195">O operação de restauração usa WITH NORECOVERY, para deixar o banco de dados secundário no banco de dados de restauração.</span><span class="sxs-lookup"><span data-stu-id="77c54-195">The restore operation uses WITH NORECOVERY, to leave the secondary database in the restoring database.</span></span>  
  
        ```sql
        RESTORE DATABASE MyDB1  
          FROM DISK='C:\MyDB1.bak'  
         WITH NORECOVERY,   
            MOVE 'MyDB1_Data' TO   
             'C:\Program Files\Microsoft SQL Server\MSSQL12.ALWAYSON1\MSSQL\DATA\MyDB1_Data.mdf',   
            MOVE 'MyDB1_Log' TO  
             'C:\Program Files\Microsoft SQL Server\MSSQL12.ALWAYSON1\MSSQL\DATA\MyDB1_Data.ldf';  
        GO  
        ```  
  
5.  <span data-ttu-id="77c54-196">Depois que você restaura o backup completo, será necessário criar um backup de log no banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="77c54-196">After you restore the full backup, you must create a log backup on the primary database.</span></span> <span data-ttu-id="77c54-197">Por exemplo, a seguinte instrução [!INCLUDE[tsql](../../../includes/tsql-md.md)] faz backup do log em um arquivo de backup chamado *E:\MyDB1_log.bak*:</span><span class="sxs-lookup"><span data-stu-id="77c54-197">For example, the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement backs up the log to the a backup file named *E:\MyDB1_log.bak*:</span></span>  
  
    ```sql
    BACKUP LOG MyDB1   
      TO DISK = 'E:\MyDB1_log.bak'   
    GO  
    ```  
  
6.  <span data-ttu-id="77c54-198">Para poder unir o banco de dados com a réplica secundária, é necessário aplicar o backup de log exigido (e qualquer backup de log subsequente).</span><span class="sxs-lookup"><span data-stu-id="77c54-198">Before you can join the database to the secondary replica, you must apply the required log backup (and any subsequent log backups).</span></span>  
  
     <span data-ttu-id="77c54-199">Por exemplo, a seguinte instrução [!INCLUDE[tsql](../../../includes/tsql-md.md)] restaura o primeiro log de *C:\MyDB1.bak*:</span><span class="sxs-lookup"><span data-stu-id="77c54-199">For example, the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement restores the first log from *C:\MyDB1.bak*:</span></span>  
  
    ```sql
    RESTORE LOG MyDB1   
      FROM DISK = 'E:\MyDB1_log.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    ```  
  
7.  <span data-ttu-id="77c54-200">Se qualquer backup de log adicional ocorrer antes da junção do banco de dados com a réplica secundária, você também deverá restaurar todos esses backups de log, em sequência, na instância do servidor que hospeda a réplica secundária usando RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="77c54-200">If any additional log backups occur before the database joins the secondary replica, you must also restore all of those log backups, in sequence, to the server instance that hosts the secondary replica using RESTORE WITH NORECOVERY.</span></span>  
  
     <span data-ttu-id="77c54-201">Por exemplo, a seguinte instrução [!INCLUDE[tsql](../../../includes/tsql-md.md)] restaura dois logs adicionais de *E:\MyDB1_log.bak*:</span><span class="sxs-lookup"><span data-stu-id="77c54-201">For example, the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement restores two additional logs from *E:\MyDB1_log.bak*:</span></span>  
  
    ```sql
    RESTORE LOG MyDB1   
      FROM DISK = 'E:\MyDB1_log.bak'   
        WITH FILE=2, NORECOVERY  
    GO  
    RESTORE LOG MyDB1   
      FROM DISK = 'E:\MyDB1_log.bak'   
        WITH FILE=3, NORECOVERY  
    GO  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="77c54-202">Uso do PowerShell</span><span class="sxs-lookup"><span data-stu-id="77c54-202">Using PowerShell</span></span>  
 <span data-ttu-id="77c54-203">**Para preparar um banco de dados secundário**</span><span class="sxs-lookup"><span data-stu-id="77c54-203">**To prepare a secondary database**</span></span>  
  
1.  <span data-ttu-id="77c54-204">Se você precisar criar um backup recente do banco de dados primário, altere o diretório (`cd`) para a instância do servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="77c54-204">If you need to create a recent backup of the primary database, change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="77c54-205">Use o cmdlet `Backup-SqlDatabase` para criar cada um dos backups.</span><span class="sxs-lookup"><span data-stu-id="77c54-205">Use the `Backup-SqlDatabase` cmdlet to create each of the backups.</span></span>  
  
3.  <span data-ttu-id="77c54-206">Altere o diretório (`cd`) para a instância de servidor que hospeda a réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="77c54-206">Change directory (`cd`) to the server instance that hosts the secondary replica.</span></span>  
  
4.  <span data-ttu-id="77c54-207">Para restaurar os backups do banco de dados e de log de cada banco de dados primário, use o cmdlet `restore-SqlDatabase`, especificando o parâmetro de restauração `NoRecovery`.</span><span class="sxs-lookup"><span data-stu-id="77c54-207">To restore the database and log backups of each primary database, use the `restore-SqlDatabase` cmdlet, specifying the `NoRecovery` restore parameter.</span></span> <span data-ttu-id="77c54-208">Se os caminhos dos arquivos forem diferentes nos computadores que hospedam a réplica primária e a réplica secundária de destino, use também o parâmetro de restauração `RelocateFile`.</span><span class="sxs-lookup"><span data-stu-id="77c54-208">If the file paths differ between the computers that host the primary replica and the target secondary replica, also use the `RelocateFile` restore parameter.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="77c54-209">Para exibir a sintaxe de um cmdlet, use o cmdlet `Get-Help` no ambiente do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77c54-209">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="77c54-210">Para obter mais informações, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="77c54-210">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
5.  <span data-ttu-id="77c54-211">Para concluir a configuração do banco de dados secundário, você precisa uni-lo ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="77c54-211">To complete configuration of the secondary database, you need to join it to the availability group.</span></span> <span data-ttu-id="77c54-212">Para obter mais informações, veja [Unir um banco de dados secundário a um grupo de disponibilidade &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="77c54-212">For more information, [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
 <span data-ttu-id="77c54-213">**Para configurar e usar o provedor do SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="77c54-213">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="77c54-214">Provedor do SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="77c54-214">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
###  <a name="sample-backup-and-restore-script-and-command"></a><a name="ExamplePSscript"></a><span data-ttu-id="77c54-215">Exemplo de script e comando de backup e restauração</span><span class="sxs-lookup"><span data-stu-id="77c54-215">Sample Backup and Restore Script and Command</span></span>  
 <span data-ttu-id="77c54-216">Os comandos PowerShell a seguir fazem backup de um backup de banco de dados completo e do log de transações em um compartilhamento de rede e restaura esses backups a partir desse compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="77c54-216">The following PowerShell commands back up a full database backup and transaction log to a network share and restore those backups from that share.</span></span> <span data-ttu-id="77c54-217">Este exemplo supõe que o caminho do arquivo para o qual o banco de dados é restaurado é igual ao caminho do arquivo no qual foi feito o backup do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="77c54-217">This example assumes that the file path to which the database is restored is the same as the file path on which the database was backed up.</span></span>  
  
```powershell
# Create database backup  
Backup-SqlDatabase -Database "MyDB1" -BackupFile "\\share\backups\MyDB1.bak" -ServerInstance "SourceMachine\Instance"  
# Create log backup  
Backup-SqlDatabase -Database "MyDB1" -BackupAction "Log" -BackupFile "\\share\backups\MyDB1.trn" -ServerInstance "SourceMachine\Instance"  
# Restore database backup
Restore-SqlDatabase -Database "MyDB1" -BackupFile "\\share\backups\MyDB1.bak" -NoRecovery -ServerInstance "DestinationMachine\Instance"  
# Restore log backup
Restore-SqlDatabase -Database "MyDB1" -BackupFile "\\share\backups\MyDB1.trn" -RestoreAction "Log" -NoRecovery -ServerInstance "DestinationMachine\Instance"
```  
  
##  <a name="follow-up-after-preparing-a-secondary-database"></a><a name="FollowUp"></a><span data-ttu-id="77c54-218">Acompanhamento: depois de preparar um banco de dados secundário</span><span class="sxs-lookup"><span data-stu-id="77c54-218">Follow Up: After Preparing a Secondary Database</span></span>  
 <span data-ttu-id="77c54-219">Para concluir a configuração do banco de dados secundário, una o banco de dados recém-restaurado ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="77c54-219">To complete configuration of the secondary database, join the newly restored database to the availability group.</span></span> <span data-ttu-id="77c54-220">Para obter mais informações, consulte [Unir um banco de dados secundário a um grupo de disponibilidade &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="77c54-220">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77c54-221">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="77c54-221">See Also</span></span>  
 <span data-ttu-id="77c54-222">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="77c54-222">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="77c54-223">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="77c54-223">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="77c54-224">[Argumentos de RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="77c54-224">[RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span></span>  
 <span data-ttu-id="77c54-225">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="77c54-225">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="77c54-226">Solucionar problemas de uma operação de adição de arquivo com falha &#40;Grupos de Disponibilidade AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="77c54-226">Troubleshoot a Failed Add-File Operation &#40;AlwaysOn Availability Groups&#41;</span></span>](troubleshoot-a-failed-add-file-operation-always-on-availability-groups.md)  
