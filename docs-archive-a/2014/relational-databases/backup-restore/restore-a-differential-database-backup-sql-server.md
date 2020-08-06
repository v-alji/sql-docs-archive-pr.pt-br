---
title: Restaurar um backup diferencial do banco de dados (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full differential backups [SQL Server]
- restoring databases [SQL Server], full differential backups
- database backups [SQL Server], full differential backups
- database restores [SQL Server], full differential backups
- backing up databases [SQL Server], full differential backups
ms.assetid: 0dd971a4-ee38-4dd3-9f30-ef77fc58dd11
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a8eab18d84efc1a990715e0d5488085252f93a7e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581411"
---
# <a name="restore-a-differential-database-backup-sql-server"></a><span data-ttu-id="debbd-102">Restaurar um backup diferencial de banco de dados (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="debbd-102">Restore a Differential Database Backup (SQL Server)</span></span>
  <span data-ttu-id="debbd-103">Este tópico descreve como restaurar um backup de banco de dados diferencial no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="debbd-103">This topic describes how to restore a differential database backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="debbd-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="debbd-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="debbd-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="debbd-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="debbd-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="debbd-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="debbd-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="debbd-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="debbd-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="debbd-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="debbd-109">**Para restaurar um backup de banco de dados diferencial usando:**</span><span class="sxs-lookup"><span data-stu-id="debbd-109">**To restore a differential database backup, using:**</span></span>  
  
     [<span data-ttu-id="debbd-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="debbd-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="debbd-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="debbd-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="debbd-112">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="debbd-112">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="debbd-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="debbd-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="debbd-114">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="debbd-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="debbd-115">RESTORE não é permitido em uma transação explícita ou implícita.</span><span class="sxs-lookup"><span data-stu-id="debbd-115">RESTORE is not allowed in an explicit or implicit transaction.</span></span>  
  
-   <span data-ttu-id="debbd-116">Os backups criados por uma versão mais recente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não podem ser restaurados em versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="debbd-116">Backups that are created by more recent version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot be restored in earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="debbd-117">No [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], é possível restaurar um banco de dados de usuário de um backup de banco de dados criado por meio do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ou de uma versão posterior.</span><span class="sxs-lookup"><span data-stu-id="debbd-117">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can restore a user database from a database backup that was created by using [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or a later version.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="debbd-118">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="debbd-118">Prerequisites</span></span>  
  
-   <span data-ttu-id="debbd-119">No modelo de recuperação completa ou bulk-logged, antes de poder restaurar um banco de dados, é necessário fazer backup do log de transações ativas (conhecido como a parte final do log).</span><span class="sxs-lookup"><span data-stu-id="debbd-119">Under the full or bulk-logged recovery model, before you can restore a database, you must back up the active transaction log (known as the tail of the log).</span></span> <span data-ttu-id="debbd-120">Para obter mais informações, veja [Fazer backup de um log de transações &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md)).</span><span class="sxs-lookup"><span data-stu-id="debbd-120">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="debbd-121">Segurança</span><span class="sxs-lookup"><span data-stu-id="debbd-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="debbd-122">Permissões</span><span class="sxs-lookup"><span data-stu-id="debbd-122">Permissions</span></span>  
 <span data-ttu-id="debbd-123">Se o banco de dados que está sendo restaurado não existir, o usuário deverá ter permissões CREATE DATABASE para poder executar o comando RESTORE.</span><span class="sxs-lookup"><span data-stu-id="debbd-123">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="debbd-124">Se o banco de dados existir, as permissões RESTORE usarão como padrão os membros das funções de servidor fixas **sysadmin** e **dbcreator** e o proprietário (**dbo**) do banco de dados (para a opção FROM DATABASE_SNAPSHOT, o banco de dados sempre existe).</span><span class="sxs-lookup"><span data-stu-id="debbd-124">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="debbd-125">As permissões RESTORE são concedidas a funções nas quais as informações de associação estão sempre disponíveis para o servidor.</span><span class="sxs-lookup"><span data-stu-id="debbd-125">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="debbd-126">Como a associação da função de banco de dados fixa pode ser verificada apenas quando o banco de dados está acessível e não danificado, o que nem sempre é o caso quando RESTORE é executado, os membros da função de banco de dados fixa **db_owner** não têm permissões RESTORE.</span><span class="sxs-lookup"><span data-stu-id="debbd-126">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="debbd-127">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="debbd-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-restore-a-differential-database-backup"></a><span data-ttu-id="debbd-128">Para restaurar um backup de banco de dados diferencial</span><span class="sxs-lookup"><span data-stu-id="debbd-128">To restore a differential database backup</span></span>  
  
1.  <span data-ttu-id="debbd-129">Depois de se conectar à instância adequada do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], no Pesquisador de Objetos, clique no nome do servidor para expandir a árvore de servidores.</span><span class="sxs-lookup"><span data-stu-id="debbd-129">After you connect to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="debbd-130">Expanda os **Bancos de dados**.</span><span class="sxs-lookup"><span data-stu-id="debbd-130">Expand **Databases**.</span></span> <span data-ttu-id="debbd-131">Dependendo do banco de dados, selecione um banco de dados de usuário ou expanda os **Bancos de dados do sistema**e selecione um banco de dados do sistema.</span><span class="sxs-lookup"><span data-stu-id="debbd-131">Depending on the database, either select a user database or expand **System Databases**, and then select a system database.</span></span>  
  
3.  <span data-ttu-id="debbd-132">Clique com o botão direito do mouse no banco de dados, aponte para **Tarefas**, aponte para **Restaurar**e clique em **Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="debbd-132">Right-click the database, point to **Tasks**, point to **Restore**, and then click **Database**.</span></span>  
  
4.  <span data-ttu-id="debbd-133">Na página **Geral** , use a seção **Origem** para especificar a origem e o local dos conjuntos de backup a serem restaurados.</span><span class="sxs-lookup"><span data-stu-id="debbd-133">On the **General** page, use the **Source** section to specify the source and location of the backup sets to restore.</span></span> <span data-ttu-id="debbd-134">Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="debbd-134">Select one of the following options:</span></span>  
  
    -   <span data-ttu-id="debbd-135">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="debbd-135">**Database**</span></span>  
  
         <span data-ttu-id="debbd-136">Selecione o banco de dados a ser restaurado na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="debbd-136">Select the database to restore from the drop-down list.</span></span> <span data-ttu-id="debbd-137">A lista contém apenas os bancos de dados dos quais foi feito um backup de acordo com o histórico de backup do **msdb** .</span><span class="sxs-lookup"><span data-stu-id="debbd-137">The list contains only databases that have been backed up according to the **msdb** backup history.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="debbd-138">Se o backup foi obtido de um servidor diferente, o servidor de destino não terá informações de histórico de backup para o banco de dados especificado.</span><span class="sxs-lookup"><span data-stu-id="debbd-138">If the backup is taken from a different server, the destination server will not have the backup history information for the specified database.</span></span> <span data-ttu-id="debbd-139">Nesse caso, selecione **Dispositivo** para especificar manualmente o arquivo ou o dispositivo a ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="debbd-139">In this case, select **Device** to manually specify the file or device to restore.</span></span>  
  
    -   <span data-ttu-id="debbd-140">**Dispositivo**</span><span class="sxs-lookup"><span data-stu-id="debbd-140">**Device**</span></span>  
  
         <span data-ttu-id="debbd-141">Clique no botão Procurar ( **...** ) para abrir a caixa de diálogo **Selecione dispositivos de backup** .</span><span class="sxs-lookup"><span data-stu-id="debbd-141">Click the browse (**...**) button to open the **Select backup devices** dialog box.</span></span> <span data-ttu-id="debbd-142">Na caixa **Tipo de mídia de backup** , selecione um dos tipos de dispositivo listados.</span><span class="sxs-lookup"><span data-stu-id="debbd-142">In the **Backup media type** box, select one of the listed device types.</span></span> <span data-ttu-id="debbd-143">Para selecionar um ou mais dispositivos da caixa **Mídia de backup** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="debbd-143">To select one or more devices for the **Backup media** box, click **Add**.</span></span>  
  
         <span data-ttu-id="debbd-144">Após adicionar os dispositivos desejados à caixa de listagem **Mídia de backup** , clique em **OK** para voltar à página **Geral** .</span><span class="sxs-lookup"><span data-stu-id="debbd-144">After you add the devices you want to the **Backup media** list box, click **OK** to return to the **General** page.</span></span>  
  
         <span data-ttu-id="debbd-145">Na caixa de listagem **Fonte: Dispositivo: Banco de Dados**, selecione o nome do banco de dados que deve ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="debbd-145">In the **Source: Device: Database** list box, select the name of the database which should be restored.</span></span>  
  
         <span data-ttu-id="debbd-146">**Observação** Essa lista estará disponível apenas quando **Dispositivo** for selecionado.</span><span class="sxs-lookup"><span data-stu-id="debbd-146">**Note** This list is only available when **Device** is selected.</span></span> <span data-ttu-id="debbd-147">Apenas os bancos de dados que têm backups no dispositivo selecionado estarão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="debbd-147">Only databases that have backups on the selected device will be available.</span></span>  
  
5.  <span data-ttu-id="debbd-148">Na seção **Destino** , a caixa **Banco de Dados** é preenchida automaticamente com o nome do banco de dados a ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="debbd-148">In the **Destination** section, the **Database** box is automatically populated with the name of the database to be restored.</span></span> <span data-ttu-id="debbd-149">Para alterar o nome do banco de dados, digite o novo nome na caixa **Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="debbd-149">To change the name of the database, enter the new name in the **Database** box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="debbd-150">Para interromper a restauração em um ponto específico, clique em **Linha do Tempo** para acessar a caixa de diálogo **Linha do Tempo de Backup** .</span><span class="sxs-lookup"><span data-stu-id="debbd-150">To stop the restore at a specific point in time, click **Timeline** to access the **Backup Timeline** dialog box.</span></span> <span data-ttu-id="debbd-151">Para obter ajuda na interrupção de uma restauração de banco de dados em um ponto específico, veja [Restaurar um Banco de Dados do SQL Server em um ponto específico &#40;Modelo de recuperação completa&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="debbd-151">For help with stopping a database restore at a specific point in time, see [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
6.  <span data-ttu-id="debbd-152">Na grade **Conjuntos de backup a serem restaurados** , selecione os backups que deseja restaurar através do backup diferencial.</span><span class="sxs-lookup"><span data-stu-id="debbd-152">In the **Backup sets to restore** grid, select the backups through the differential backup that you wish to restore.</span></span>  
  
     <span data-ttu-id="debbd-153">Para obter informações sobre as colunas da grade **Conjuntos de backup a serem restaurados** , veja [Restaurar banco de dados &#40;página Geral&#41;](../../integration-services/general-page-of-integration-services-designers-options.md)).</span><span class="sxs-lookup"><span data-stu-id="debbd-153">For information about the columns in the **Backup sets to restore** grid, see [Restore Database &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span></span>  
  
7.  <span data-ttu-id="debbd-154">Na página **Opções** , no painel **Opções de restauração** , você pode selecionar qualquer uma das seguintes opções, de acordo com sua situação:</span><span class="sxs-lookup"><span data-stu-id="debbd-154">On the **Options** page, in the **Restore options** panel, you can select any of the following options, if appropriate for your situation:</span></span>  
  
    -   <span data-ttu-id="debbd-155">**Substituir o banco de dados existente (WITH REPLACE)**</span><span class="sxs-lookup"><span data-stu-id="debbd-155">**Overwrite the existing database (WITH REPLACE)**</span></span>  
  
    -   <span data-ttu-id="debbd-156">**Preservar as configurações de replicação (WITH KEEP_REPLICATION)**</span><span class="sxs-lookup"><span data-stu-id="debbd-156">**Preserve the replication settings (WITH KEEP_REPLICATION)**</span></span>  
  
    -   <span data-ttu-id="debbd-157">**Perguntar antes de restaurar cada backup**</span><span class="sxs-lookup"><span data-stu-id="debbd-157">**Prompt before restoring each backup**</span></span>  
  
    -   <span data-ttu-id="debbd-158">**Acesso restrito ao banco de dados restaurado (WITH RESTRICTED_USER)**</span><span class="sxs-lookup"><span data-stu-id="debbd-158">**Restrict access to the restored database (WITH RESTRICTED_USER)**</span></span>  
  
     <span data-ttu-id="debbd-159">Para obter mais informações sobre essas opções, veja [Restaurar banco de dados &#40;Página Opções&#41;](restore-database-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="debbd-159">For more information about these options, see [Restore Database &#40;Options Page&#41;](restore-database-options-page.md).</span></span>  
  
8.  <span data-ttu-id="debbd-160">Selecione uma opção para a caixa **Estado de recuperação** .</span><span class="sxs-lookup"><span data-stu-id="debbd-160">Select an option for the **Recovery state** box.</span></span> <span data-ttu-id="debbd-161">Essa caixa determina o estado do banco de dados após a operação de restauração.</span><span class="sxs-lookup"><span data-stu-id="debbd-161">This box determines the state of the database after the restore operation.</span></span>  
  
    -   <span data-ttu-id="debbd-162">**RESTORE WITH RECOVERY** é o comportamento padrão que deixa o banco de dados pronto para uso revertendo as transações não confirmadas.</span><span class="sxs-lookup"><span data-stu-id="debbd-162">**RESTORE WITH RECOVERY** is the default behavior which leaves the database ready for use by rolling back the uncommitted transactions.</span></span> <span data-ttu-id="debbd-163">Os logs de transações adicionais não podem ser restaurados.</span><span class="sxs-lookup"><span data-stu-id="debbd-163">Additional transaction logs cannot be restored.</span></span> <span data-ttu-id="debbd-164">Selecione essa opção se você estiver restaurando todos os backups necessários agora.</span><span class="sxs-lookup"><span data-stu-id="debbd-164">Select this option if you are restoring all of the necessary backups now.</span></span>  
  
    -   <span data-ttu-id="debbd-165">**RESTORE WITH NORECOVERY** deixa o banco de dados não operacional e não reverte as transações não confirmadas.</span><span class="sxs-lookup"><span data-stu-id="debbd-165">**RESTORE WITH NORECOVERY** which leaves the database non-operational, and does not roll back the uncommitted transactions.</span></span> <span data-ttu-id="debbd-166">Os logs de transações adicionais podem ser restaurados.</span><span class="sxs-lookup"><span data-stu-id="debbd-166">Additional transaction logs can be restored.</span></span> <span data-ttu-id="debbd-167">Só é possível usar o banco de dados depois que ele é recuperado.</span><span class="sxs-lookup"><span data-stu-id="debbd-167">The database cannot be used until it is recovered.</span></span>  
  
    -   <span data-ttu-id="debbd-168">**RESTORE WITH STANDBY** deixa o banco de dados no modo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="debbd-168">**RESTORE WITH STANDBY** which leaves the database in read-only mode.</span></span> <span data-ttu-id="debbd-169">Ele desfaz as transações não confirmadas, mas salva as ações de desfazer em um arquivo em espera para que os efeitos da recuperação possam ser revertidos.</span><span class="sxs-lookup"><span data-stu-id="debbd-169">It undoes uncommitted transactions, but saves the undo actions in a standby file so that recovery effects can be reverted.</span></span>  
  
     <span data-ttu-id="debbd-170">Para ver as descrições das opções, consulte [Restaurar banco de dados &#40;Página Opções&#41;](restore-database-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="debbd-170">For descriptions of the options, see [Restore Database &#40;Options Page&#41;](restore-database-options-page.md).</span></span>  
  
9. <span data-ttu-id="debbd-171">As operações de restauração falharão se houver conexões ativas com o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="debbd-171">Restore operations will fail if there are active connections to the database.</span></span> <span data-ttu-id="debbd-172">Marque a opção **Fechar conexões existentes** para assegurar que todas as conexões ativas entre o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] e o banco de dados sejam fechadas.</span><span class="sxs-lookup"><span data-stu-id="debbd-172">Check the **Close existing connections option** to ensure that all active connections between [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and the database are closed.</span></span>  
  
10. <span data-ttu-id="debbd-173">Selecione **Perguntar antes de restaurar cada backup** para que você seja solicitado entre cada operação de restauração.</span><span class="sxs-lookup"><span data-stu-id="debbd-173">Select **Prompt before restoring each backup** if you wish to be prompted between each restore operation.</span></span> <span data-ttu-id="debbd-174">Isso normalmente só é necessário quando o banco de dados é grande e você deseja monitorar o status da operação de restauração.</span><span class="sxs-lookup"><span data-stu-id="debbd-174">This is not usually necessary unless the database is large and you wish to monitor the status of the restore operation.</span></span>  
  
11. <span data-ttu-id="debbd-175">Se desejar, use a página **Arquivos** para restaurar o banco de dados em um novo local.</span><span class="sxs-lookup"><span data-stu-id="debbd-175">Optionally, use the **Files** page to restore the database to a new location.</span></span> <span data-ttu-id="debbd-176">Para obter ajuda para mover um banco de dados, consulte [Restaurar um banco de dados para um novo local &#40;SQL Server&#41;](restore-a-database-to-a-new-location-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="debbd-176">For help with moving a database, see [Restore a Database to a New Location &#40;SQL Server&#41;](restore-a-database-to-a-new-location-sql-server.md).</span></span>  
  
12. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="debbd-177">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="debbd-177">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-a-differential-database-backup"></a><span data-ttu-id="debbd-178">Para restaurar um backup de banco de dados diferencial</span><span class="sxs-lookup"><span data-stu-id="debbd-178">To restore a differential database backup</span></span>  
  
1.  <span data-ttu-id="debbd-179">Execute uma instrução RESTORE DATABASE, especificando a cláusula NORECOVERY, para restaurar o backup de banco de dados completo que vem antes do backup de banco de dados diferencial.</span><span class="sxs-lookup"><span data-stu-id="debbd-179">Execute the RESTORE DATABASE statement, specifying the NORECOVERY clause, to restore the full database backup that comes before the differential database backup.</span></span> <span data-ttu-id="debbd-180">Para obter mais informações, confira [Como restaurar um backup completo](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="debbd-180">For more information, see [How to: Restore a Full Backup](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md).</span></span>  
  
2.  <span data-ttu-id="debbd-181">Execute a instrução RESTORE DATABASE para restaurar o backup de banco de dados diferencial, especificando:</span><span class="sxs-lookup"><span data-stu-id="debbd-181">Execute the RESTORE DATABASE statement to restore the differential database backup, specifying:</span></span>  
  
    -   <span data-ttu-id="debbd-182">O nome do banco de dados para o qual o backup de banco de dados diferencial é aplicado.</span><span class="sxs-lookup"><span data-stu-id="debbd-182">The name of the database to which the differential database backup is applied.</span></span>  
  
    -   <span data-ttu-id="debbd-183">O dispositivo de backup em que o backup de banco de dados diferencial é restaurado.</span><span class="sxs-lookup"><span data-stu-id="debbd-183">The backup device where the differential database backup is restored from.</span></span>  
  
    -   <span data-ttu-id="debbd-184">A cláusula NORECOVERY, se você tiver backups de log de transações para aplicar depois de o backup de banco de dados diferencial ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="debbd-184">The NORECOVERY clause if you have transaction log backups to apply after the differential database backup is restored.</span></span> <span data-ttu-id="debbd-185">Caso contrário, especifique a cláusula RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="debbd-185">Otherwise, specify the RECOVERY clause.</span></span>  
  
3.  <span data-ttu-id="debbd-186">Com o modelo de recuperação completa ou bulk-logged, a restauração de um backup de banco de dados diferencial restaura o banco de dados até o ponto que o backup de banco de dados diferencial foi concluído.</span><span class="sxs-lookup"><span data-stu-id="debbd-186">With the full or bulk-logged recovery model, restoring a differential database backup restores the database to the point at which the differential database backup was completed.</span></span> <span data-ttu-id="debbd-187">Para recuperar até o ponto da falha, você deve aplicar todos os backups de log de transações criados depois de o último backup de banco de dados diferencial ter sido criado.</span><span class="sxs-lookup"><span data-stu-id="debbd-187">To recover to the point of failure, you must apply all transaction log backups created after the last differential database backup was created.</span></span> <span data-ttu-id="debbd-188">Para obter mais informações, veja [Aplicar backups de log de transações &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="debbd-188">For more information, see [Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="debbd-189">Exemplos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="debbd-189">Examples (Transact-SQL)</span></span>  
  
#### <a name="a-restoring-a-differential-database-backup"></a><span data-ttu-id="debbd-190">a.</span><span class="sxs-lookup"><span data-stu-id="debbd-190">A.</span></span> <span data-ttu-id="debbd-191">Restaurando um backup de banco de dados diferencial</span><span class="sxs-lookup"><span data-stu-id="debbd-191">Restoring a differential database backup</span></span>  
 <span data-ttu-id="debbd-192">Este exemplo restaura um banco de dados e um backup de banco de dados diferencial do banco de dados `MyAdvWorks` .</span><span class="sxs-lookup"><span data-stu-id="debbd-192">This example restores a database and differential database backup of the `MyAdvWorks` database.</span></span>  
  
```sql  
-- Assume the database is lost, and restore full database,   
-- specifying the original full database backup and NORECOVERY,   
-- which allows subsequent restore operations to proceed.  
RESTORE DATABASE MyAdvWorks  
   FROM MyAdvWorks_1  
   WITH NORECOVERY;  
GO  
-- Now restore the differential database backup, the second backup on   
-- the MyAdvWorks_1 backup device.  
RESTORE DATABASE MyAdvWorks  
   FROM MyAdvWorks_1  
   WITH FILE = 2,  
   RECOVERY;  
GO  
```  
  
#### <a name="b-restoring-a-database-differential-database-and-transaction-log-backup"></a><span data-ttu-id="debbd-193">B.</span><span class="sxs-lookup"><span data-stu-id="debbd-193">B.</span></span> <span data-ttu-id="debbd-194">Restaurando um backup de banco de dados, de banco de dados diferencial e de log de transações</span><span class="sxs-lookup"><span data-stu-id="debbd-194">Restoring a database, differential database, and transaction log backup</span></span>  
 <span data-ttu-id="debbd-195">Este exemplo restaura um banco de dados, um backup de banco de dados diferencial e um backup de log de transações do banco de dados `MyAdvWorks` .</span><span class="sxs-lookup"><span data-stu-id="debbd-195">This example restores a database, differential database, and transaction log backup of the `MyAdvWorks` database.</span></span>  
  
```sql  
-- Assume the database is lost at this point. Now restore the full   
-- database. Specify the original full database backup and NORECOVERY.  
-- NORECOVERY allows subsequent restore operations to proceed.  
RESTORE DATABASE MyAdvWorks  
   FROM MyAdvWorks_1  
   WITH NORECOVERY;  
GO  
-- Now restore the differential database backup, the second backup on   
-- the MyAdvWorks_1 backup device.  
RESTORE DATABASE MyAdvWorks  
   FROM MyAdvWorks_1  
   WITH FILE = 2,  
   NORECOVERY;  
GO  
-- Now restore each transaction log backup created after  
-- the differential database backup.  
RESTORE LOG MyAdvWorks  
   FROM MyAdvWorks_log1  
   WITH NORECOVERY;  
GO  
RESTORE LOG MyAdvWorks  
   FROM MyAdvWorks_log2  
   WITH RECOVERY;  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="debbd-196">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="debbd-196">Related Tasks</span></span>  
  
-   [<span data-ttu-id="debbd-197">Criar um backup diferencial de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="debbd-197">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="debbd-198">Restaurar um backup de log de transações &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="debbd-198">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="debbd-199">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="debbd-199">See Also</span></span>  
 <span data-ttu-id="debbd-200">[Backups diferenciais &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="debbd-200">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="debbd-201">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="debbd-201">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
