---
title: Restaurar um banco de dados do SQL Server até um ponto determinado (modelo de recuperação completa) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- STOPAT clause [RESTORE LOG statement]
- point in time recovery [SQL Server]
- restoring databases [SQL Server], point in time
ms.assetid: 3a5daefd-08a8-4565-b54f-28ad01a47d32
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0c71ff6e75cbbf27042c1eac70b1f97076290865
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581410"
---
# <a name="restore-a-sql-server-database-to-a-point-in-time-full-recovery-model"></a><span data-ttu-id="6ce35-102">Restaurar um banco de dados do SQL Server até um ponto determinado (modelo de recuperação completa)</span><span class="sxs-lookup"><span data-stu-id="6ce35-102">Restore a SQL Server Database to a Point in Time (Full Recovery Model)</span></span>
  <span data-ttu-id="6ce35-103">Este tópico descreve como restaurar um banco de dados em um determinado ponto no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6ce35-103">This topic describes how to restore a database to a point in time in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="6ce35-104">Este tópico é relevante apenas para os bancos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que usam o modelo de recuperação completa ou bulk-logged.</span><span class="sxs-lookup"><span data-stu-id="6ce35-104">This topic is relevant only for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases that use the full or bulk-logged recovery models.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6ce35-105">No modelo de recuperação bulk-logged, se um backup de log contiver alterações bulk-logged, a recuperação pontual não será possível para um ponto dentro desse backup.</span><span class="sxs-lookup"><span data-stu-id="6ce35-105">Under the bulk-logged recovery model, if a log backup contains bulk-logged changes, point-in-time recovery is not possible to a point within that backup.</span></span> <span data-ttu-id="6ce35-106">O banco de dados deve ser recuperado até o fim do backup do log de transações.</span><span class="sxs-lookup"><span data-stu-id="6ce35-106">The database must be recovered to the end of the transaction log backup.</span></span>  
  
-   <span data-ttu-id="6ce35-107">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="6ce35-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6ce35-108">Recomendações</span><span class="sxs-lookup"><span data-stu-id="6ce35-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="6ce35-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="6ce35-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6ce35-110">**Para restaurar um banco de dados do SQL Server em um momento determinado usando:**</span><span class="sxs-lookup"><span data-stu-id="6ce35-110">**To restore a SQL Server database to a point in time, using:**</span></span>  
  
     [<span data-ttu-id="6ce35-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6ce35-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6ce35-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6ce35-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6ce35-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="6ce35-113">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="6ce35-114">Recomendações</span><span class="sxs-lookup"><span data-stu-id="6ce35-114">Recommendations</span></span>  
  
-   <span data-ttu-id="6ce35-115">Use STANDBY para localizar um momento determinado desconhecido.</span><span class="sxs-lookup"><span data-stu-id="6ce35-115">Use STANDBY to find unknown point in time.</span></span>  
  
-   <span data-ttu-id="6ce35-116">Especificar com antecedência o momento determinado em uma sequência de restauração</span><span class="sxs-lookup"><span data-stu-id="6ce35-116">Specify the point in time early in a restore sequence</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6ce35-117">Segurança</span><span class="sxs-lookup"><span data-stu-id="6ce35-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6ce35-118">Permissões</span><span class="sxs-lookup"><span data-stu-id="6ce35-118">Permissions</span></span>  
 <span data-ttu-id="6ce35-119">Se o banco de dados que está sendo restaurado não existir, o usuário deverá ter permissões CREATE DATABASE para poder executar o comando RESTORE.</span><span class="sxs-lookup"><span data-stu-id="6ce35-119">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="6ce35-120">Se o banco de dados existir, as permissões RESTORE usarão como padrão os membros das funções de servidor fixas **sysadmin** e **dbcreator** e o proprietário (**dbo**) do banco de dados (para a opção FROM DATABASE_SNAPSHOT, o banco de dados sempre existe).</span><span class="sxs-lookup"><span data-stu-id="6ce35-120">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="6ce35-121">As permissões RESTORE são concedidas a funções nas quais as informações de associação estão sempre disponíveis para o servidor.</span><span class="sxs-lookup"><span data-stu-id="6ce35-121">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="6ce35-122">Como a associação da função de banco de dados fixa pode ser verificada apenas quando o banco de dados está acessível e não danificado, o que nem sempre é o caso quando RESTORE é executado, os membros da função de banco de dados fixa **db_owner** não têm permissões RESTORE.</span><span class="sxs-lookup"><span data-stu-id="6ce35-122">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6ce35-123">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6ce35-123">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="6ce35-124">**Para restaurar um banco de dados para um momento determinado**</span><span class="sxs-lookup"><span data-stu-id="6ce35-124">**To restore a database to a point in time**</span></span>  
  
1.  <span data-ttu-id="6ce35-125">No Pesquisador de Objetos, conecte-se à instância adequada do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]e expanda a árvore de servidores.</span><span class="sxs-lookup"><span data-stu-id="6ce35-125">In Object Explorer, connect to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="6ce35-126">Expanda os **Bancos de dados**.</span><span class="sxs-lookup"><span data-stu-id="6ce35-126">Expand **Databases**.</span></span> <span data-ttu-id="6ce35-127">Dependendo do banco de dados, selecione um banco de dados de usuário ou expanda os **Bancos de dados do sistema**e selecione um banco de dados do sistema.</span><span class="sxs-lookup"><span data-stu-id="6ce35-127">Depending on the database, either select a user database or expand **System Databases**, and then select a system database.</span></span>  
  
3.  <span data-ttu-id="6ce35-128">Clique com o botão direito do mouse no banco de dados, aponte para **Tarefas**, aponte para **Restaurar**e clique em **Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="6ce35-128">Right-click the database, point to **Tasks**, point to **Restore**, and then click **Database**.</span></span>  
  
4.  <span data-ttu-id="6ce35-129">Na página **Geral** , use a seção **Origem** para especificar a origem e o local dos conjuntos de backup a serem restaurados.</span><span class="sxs-lookup"><span data-stu-id="6ce35-129">On the **General** page, use the **Source** section to specify the source and location of the backup sets to restore.</span></span> <span data-ttu-id="6ce35-130">Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="6ce35-130">Select one of the following options:</span></span>  
  
    -   <span data-ttu-id="6ce35-131">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="6ce35-131">**Database**</span></span>  
  
         <span data-ttu-id="6ce35-132">Selecione o banco de dados a ser restaurado na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="6ce35-132">Select the database to restore from the drop-down list.</span></span> <span data-ttu-id="6ce35-133">A lista contém apenas os bancos de dados dos quais foi feito um backup de acordo com o histórico de backup do **msdb** .</span><span class="sxs-lookup"><span data-stu-id="6ce35-133">The list contains only databases that have been backed up according to the **msdb** backup history.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6ce35-134">Se o backup foi obtido de um servidor diferente, o servidor de destino não terá informações de histórico de backup para o banco de dados especificado.</span><span class="sxs-lookup"><span data-stu-id="6ce35-134">If the backup is taken from a different server, the destination server will not have the backup history information for the specified database.</span></span> <span data-ttu-id="6ce35-135">Nesse caso, selecione **Dispositivo** para especificar manualmente o arquivo ou o dispositivo a ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="6ce35-135">In this case, select **Device** to manually specify the file or device to restore.</span></span>  
  
    -   <span data-ttu-id="6ce35-136">**Dispositivo**</span><span class="sxs-lookup"><span data-stu-id="6ce35-136">**Device**</span></span>  
  
         <span data-ttu-id="6ce35-137">Clique no botão Procurar ( **...** ) para abrir a caixa de diálogo **Selecione dispositivos de backup** .</span><span class="sxs-lookup"><span data-stu-id="6ce35-137">Click the browse (**...**) button to open the **Select backup devices** dialog box.</span></span> <span data-ttu-id="6ce35-138">Na caixa **Tipo de mídia de backup** , selecione um dos tipos de dispositivo listados.</span><span class="sxs-lookup"><span data-stu-id="6ce35-138">In the **Backup media type** box, select one of the listed device types.</span></span> <span data-ttu-id="6ce35-139">Para selecionar um ou mais dispositivos da caixa **Mídia de backup** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="6ce35-139">To select one or more devices for the **Backup media** box, click **Add**.</span></span>  
  
         <span data-ttu-id="6ce35-140">Após adicionar os dispositivos desejados à caixa de listagem **Mídia de backup** , clique em **OK** para voltar à página **Geral** .</span><span class="sxs-lookup"><span data-stu-id="6ce35-140">After you add the devices you want to the **Backup media** list box, click **OK** to return to the **General** page.</span></span>  
  
         <span data-ttu-id="6ce35-141">Na caixa de listagem **Origem: Dispositivo: Banco de Dados** , selecione o nome do banco de dados que deve ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="6ce35-141">In the **Source: Device: Database** list box, select the name of the database which should be restored.</span></span>  
  
         <span data-ttu-id="6ce35-142">**Observação** Essa lista estará disponível apenas quando **Dispositivo** for selecionado.</span><span class="sxs-lookup"><span data-stu-id="6ce35-142">**Note** This list is only available when **Device** is selected.</span></span> <span data-ttu-id="6ce35-143">Apenas os bancos de dados que têm backups no dispositivo selecionado estarão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="6ce35-143">Only databases that have backups on the selected device will be available.</span></span>  
  
5.  <span data-ttu-id="6ce35-144">Na seção **Destino** , a caixa **Banco de Dados** é preenchida automaticamente com o nome do banco de dados a ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="6ce35-144">In the **Destination** section, the **Database** box is automatically populated with the name of the database to be restored.</span></span> <span data-ttu-id="6ce35-145">Para alterar o nome do banco de dados, digite o novo nome na caixa **Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="6ce35-145">To change the name of the database, enter the new name in the **Database** box.</span></span>  
  
6.  <span data-ttu-id="6ce35-146">Clique em **Linha do Tempo** para acessar a caixa de diálogo **Linha do Tempo de Backup** .</span><span class="sxs-lookup"><span data-stu-id="6ce35-146">Click **Timeline** to access the **Backup Timeline** dialog box.</span></span>  
  
7.  <span data-ttu-id="6ce35-147">Na caixa de diálogo **Restaurar para** , clique em **Data e hora específicas**.</span><span class="sxs-lookup"><span data-stu-id="6ce35-147">In the **Restore to** section, click **Specific date and time**.</span></span>  
  
8.  <span data-ttu-id="6ce35-148">Use as caixas **Data** e **Hora** ou a barra de controle deslizante para especificar uma data específica e hora em que a restauração deve parar.</span><span class="sxs-lookup"><span data-stu-id="6ce35-148">Use either the **Date** and **Time** boxes or the slider bar to specify a specific date and time to where the restore should stop.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="6ce35-149">Use a caixa **Intervalo da Linha do Tempo** para alterar a quantidade de tempo exibida na linha do tempo.</span><span class="sxs-lookup"><span data-stu-id="6ce35-149">Use the **Timeline Interval** box to change the amount of time displayed on the timeline.</span></span>  
  
9. <span data-ttu-id="6ce35-150">Depois que você especificar um momento determinado, o orientador de recuperação de banco de dados garantirá que apenas os backups necessários para restaurar até esse momento determinado sejam selecionados na coluna **Restaurar** da grade **Conjuntos de backup a serem restaurados** .</span><span class="sxs-lookup"><span data-stu-id="6ce35-150">After you have specified a specific point in time, the Database Recovery Advisor ensures that only backups that are required for restoring to that point in time are selected in the **Restore** column of the **Backup sets to restore** grid.</span></span> <span data-ttu-id="6ce35-151">Esses backups selecionados compõem o plano de restauração recomendado para a sua restauração pontual.</span><span class="sxs-lookup"><span data-stu-id="6ce35-151">These selected backups make up the recommended restore plan for your point-in-time restore.</span></span> <span data-ttu-id="6ce35-152">Você deve usar apenas os backups selecionados para sua operação de restauração pontual.</span><span class="sxs-lookup"><span data-stu-id="6ce35-152">You should use only the selected backups for your point-in-time restore operation.</span></span>  
  
     <span data-ttu-id="6ce35-153">Para obter informações sobre as colunas da grade **Conjuntos de backup a serem restaurados** , veja [Restaurar banco de dados &#40;página Geral&#41;](../../integration-services/general-page-of-integration-services-designers-options.md)).</span><span class="sxs-lookup"><span data-stu-id="6ce35-153">For information about the columns in the **Backup sets to restore** grid, see [Restore Database &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span></span> <span data-ttu-id="6ce35-154">Para obter informações sobre o Orientador de Recuperação de Banco de Dados, confira [Visão geral da restauração e recuperação &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6ce35-154">For information about the Database Recovery Advisor, see [Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md).</span></span>  
  
10. <span data-ttu-id="6ce35-155">Na página **Opções** , no painel **Opções de restauração** , você pode selecionar qualquer uma das seguintes opções, de acordo com sua situação:</span><span class="sxs-lookup"><span data-stu-id="6ce35-155">On the **Options** page, in the **Restore options** panel, you can select any of the following options, if appropriate for your situation:</span></span>  
  
    -   <span data-ttu-id="6ce35-156">**Substituir o banco de dados existente (WITH REPLACE)**</span><span class="sxs-lookup"><span data-stu-id="6ce35-156">**Overwrite the existing database (WITH REPLACE)**</span></span>  
  
    -   <span data-ttu-id="6ce35-157">**Preservar as configurações de replicação (WITH KEEP_REPLICATION)**</span><span class="sxs-lookup"><span data-stu-id="6ce35-157">**Preserve the replication settings (WITH KEEP_REPLICATION)**</span></span>  
  
    -   <span data-ttu-id="6ce35-158">**Acesso restrito ao banco de dados restaurado (WITH RESTRICTED_USER)**</span><span class="sxs-lookup"><span data-stu-id="6ce35-158">**Restrict access to the restored database (WITH RESTRICTED_USER)**</span></span>  
  
     <span data-ttu-id="6ce35-159">Para obter mais informações sobre essas opções, veja [Restaurar banco de dados &#40;Página Opções&#41;](restore-database-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="6ce35-159">For more information about these options, see [Restore Database &#40;Options Page&#41;](restore-database-options-page.md).</span></span>  
  
11. <span data-ttu-id="6ce35-160">Selecione uma opção para a caixa **Estado de recuperação** .</span><span class="sxs-lookup"><span data-stu-id="6ce35-160">Select an option for the **Recovery state** box.</span></span> <span data-ttu-id="6ce35-161">Essa caixa determina o estado do banco de dados após a operação de restauração.</span><span class="sxs-lookup"><span data-stu-id="6ce35-161">This box determines the state of the database after the restore operation.</span></span>  
  
    -   <span data-ttu-id="6ce35-162">**RESTORE WITH RECOVERY** é o comportamento padrão que deixa o banco de dados pronto para uso revertendo as transações não confirmadas.</span><span class="sxs-lookup"><span data-stu-id="6ce35-162">**RESTORE WITH RECOVERY** is the default behavior which leaves the database ready for use by rolling back the uncommitted transactions.</span></span> <span data-ttu-id="6ce35-163">Os logs de transações adicionais não podem ser restaurados.</span><span class="sxs-lookup"><span data-stu-id="6ce35-163">Additional transaction logs cannot be restored.</span></span> <span data-ttu-id="6ce35-164">Selecione essa opção se você estiver restaurando todos os backups necessários agora.</span><span class="sxs-lookup"><span data-stu-id="6ce35-164">Select this option if you are restoring all of the necessary backups now.</span></span>  
  
    -   <span data-ttu-id="6ce35-165">**RESTORE WITH NORECOVERY** deixa o banco de dados não operacional e não reverte as transações não confirmadas.</span><span class="sxs-lookup"><span data-stu-id="6ce35-165">**RESTORE WITH NORECOVERY** which leaves the database non-operational, and does not roll back the uncommitted transactions.</span></span> <span data-ttu-id="6ce35-166">Os logs de transações adicionais podem ser restaurados.</span><span class="sxs-lookup"><span data-stu-id="6ce35-166">Additional transaction logs can be restored.</span></span> <span data-ttu-id="6ce35-167">Só é possível usar o banco de dados depois que ele é recuperado.</span><span class="sxs-lookup"><span data-stu-id="6ce35-167">The database cannot be used until it is recovered.</span></span>  
  
    -   <span data-ttu-id="6ce35-168">**RESTORE WITH STANDBY** deixa o banco de dados no modo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="6ce35-168">**RESTORE WITH STANDBY** which leaves the database in read-only mode.</span></span> <span data-ttu-id="6ce35-169">Ele desfaz as transações não confirmadas, mas salva as ações de desfazer em um arquivo em espera para que os efeitos da recuperação possam ser revertidos.</span><span class="sxs-lookup"><span data-stu-id="6ce35-169">It undoes uncommitted transactions, but saves the undo actions in a standby file so that recovery effects can be reverted.</span></span>  
  
     <span data-ttu-id="6ce35-170">Para ver as descrições das opções, consulte [Restaurar banco de dados &#40;Página Opções&#41;](restore-database-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="6ce35-170">For descriptions of the options, see [Restore Database &#40;Options Page&#41;](restore-database-options-page.md).</span></span>  
  
12. <span data-ttu-id="6ce35-171">**Fazer backup da parte final do log antes da restauração** será selecionada se for necessário para o momento determinado que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="6ce35-171">**Take tail-log backup before restore** will be selected if it is necessary for the point in time that you have selected.</span></span> <span data-ttu-id="6ce35-172">Você não precisa modificar essa configuração, mas poderá escolher o backup da parte final do log até mesmo se não for necessário.</span><span class="sxs-lookup"><span data-stu-id="6ce35-172">You do not need to modify this setting, but you can choose to backup the tail of the log even if it is not required.</span></span>  
  
13. <span data-ttu-id="6ce35-173">As operações de restauração poderão falhar se houver conexões ativas com o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6ce35-173">Restore operations may fail if there are active connections to the database.</span></span> <span data-ttu-id="6ce35-174">Marque a opção **Fechar conexões existentes** para assegurar que todas as conexões ativas entre o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] e o banco de dados sejam fechadas.</span><span class="sxs-lookup"><span data-stu-id="6ce35-174">Check the **Close existing connections option** to ensure that all active connections between [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and the database are closed.</span></span> <span data-ttu-id="6ce35-175">Essa caixa de seleção define o banco de dados no modo de usuário único antes de executar as operações de restauração e define o banco de dados no modo de vários usuários ao concluir.</span><span class="sxs-lookup"><span data-stu-id="6ce35-175">This check box sets the database to single user mode before performing the restore operations, and sets the database to multi-user mode when complete.</span></span>  
  
14. <span data-ttu-id="6ce35-176">Selecione **Perguntar antes de restaurar cada backup** para que você seja solicitado entre cada operação de restauração.</span><span class="sxs-lookup"><span data-stu-id="6ce35-176">Select **Prompt before restoring each backup** if you wish to be prompted between each restore operation.</span></span> <span data-ttu-id="6ce35-177">Isso normalmente só é necessário quando o banco de dados é grande e você deseja monitorar o status da operação de restauração.</span><span class="sxs-lookup"><span data-stu-id="6ce35-177">This is not usually necessary unless the database is large and you wish to monitor the status of the restore operation.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6ce35-178">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6ce35-178">Using Transact-SQL</span></span>  
 <span data-ttu-id="6ce35-179">**Antes de começar**</span><span class="sxs-lookup"><span data-stu-id="6ce35-179">**Before you begin**</span></span>  
  
 <span data-ttu-id="6ce35-180">Um momento especificado sempre é restaurado a partir de um backup de log.</span><span class="sxs-lookup"><span data-stu-id="6ce35-180">A specified time is always restored from a log backup.</span></span> <span data-ttu-id="6ce35-181">Em cada instrução RESTORE LOG da sequência de restauração, especifique a transação ou o tempo de destino em uma cláusula STOPAT idêntica.</span><span class="sxs-lookup"><span data-stu-id="6ce35-181">In every RESTORE LOG statement of the restore sequence, you must specify your target time or transaction in an identical STOPAT clause.</span></span> <span data-ttu-id="6ce35-182">Como um pré-requisito para uma restauração pontual, você deve restaurar primeiro um backup de banco de dados completo cujo ponto de extremidade seja anterior ao tempo de recuperação designado.</span><span class="sxs-lookup"><span data-stu-id="6ce35-182">As a prerequisite to a point-in-time restore, you must first restore a full database backup whose end point is earlier than your target restore time.</span></span> <span data-ttu-id="6ce35-183">Esse backup de banco de dados completo pode ser anterior ao backup de banco de dados completo mais recente desde que você depois restaure todos os backups de log subsequentes, até o backup de log que contém o tempo determinado.</span><span class="sxs-lookup"><span data-stu-id="6ce35-183">That full database backup can be older than the most recent full database backup as long as you then restore every subsequent log backup, up to and including the log backup that contains your target point in time.</span></span>  
  
 <span data-ttu-id="6ce35-184">Para ajudar a identificar qual backup de banco de dados restaurar, uma alternativa é especificar a cláusula WITH STOPAT em uma instrução RESTORE DATABASE para gerar um erro se um backup de dados for muito recente para o tempo designado especificado.</span><span class="sxs-lookup"><span data-stu-id="6ce35-184">To help you identify which database backup to restore, you can optionally specify your WITH STOPAT clause in your RESTORE DATABASE statement to raise an error if a data backup is too recent for the specified target time.</span></span> <span data-ttu-id="6ce35-185">O backup de dados completo será sempre restaurado, mesmo que ele contenha o tempo de destino.</span><span class="sxs-lookup"><span data-stu-id="6ce35-185">The complete data backup is always restored, even if it contains the target time.</span></span>  
  
 <span data-ttu-id="6ce35-186">**Sintaxe [!INCLUDE[tsql](../../includes/tsql-md.md)] básica**</span><span class="sxs-lookup"><span data-stu-id="6ce35-186">**Basic [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax**</span></span>  
  
 <span data-ttu-id="6ce35-187">Restaurar *database_name* de log de <backup_device> com STOPAT \*\* = *`time`* ,\*\* Recovery...</span><span class="sxs-lookup"><span data-stu-id="6ce35-187">RESTORE LOG *database_name* FROM <backup_device> WITH STOPAT **=*`time`*,** RECOVERY...</span></span>  
  
 <span data-ttu-id="6ce35-188">O ponto de recuperação é a última confirmação de transação que ocorreu em ou antes do `datetime` valor especificado por *tempo*.</span><span class="sxs-lookup"><span data-stu-id="6ce35-188">The recovery point is the latest transaction commit that occurred at or before the `datetime` value that is specified by *time*.</span></span>  
  
 <span data-ttu-id="6ce35-189">Para restaurar apenas as modificações feitas antes de um momento determinado, especifique WITH STOPAT **=** *hora* para cada backup restaurado.</span><span class="sxs-lookup"><span data-stu-id="6ce35-189">To restore only the modifications that were made before a specific point in time, specify WITH STOPAT **=** *time* for each backup you restore.</span></span> <span data-ttu-id="6ce35-190">Isso garante que você não ultrapassará o tempo de destino.</span><span class="sxs-lookup"><span data-stu-id="6ce35-190">This makes sure that you do not go past the target time.</span></span>  
  
 <span data-ttu-id="6ce35-191">**Para restaurar um banco de dados para um momento determinado**</span><span class="sxs-lookup"><span data-stu-id="6ce35-191">**To restore a database to a point in time**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6ce35-192">Para obter um exemplo desse procedimento, veja [Exemplo (Transact-SQL)](#TsqlExample), mais adiante nesta seção.</span><span class="sxs-lookup"><span data-stu-id="6ce35-192">For an example of this procedure, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="6ce35-193">Conecte-se à instância de servidor na qual você deseja restaurar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6ce35-193">Connect to server instance on which you want to restore the database.</span></span>  
  
2.  <span data-ttu-id="6ce35-194">Execute a instrução RESTORE DATABASE usando a opção NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="6ce35-194">Execute the RESTORE DATABASE statement using the NORECOVERY option.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6ce35-195">Se uma sequência de restauração parcial excluir qualquer grupo de arquivos [FILESTREAM](../blob/filestream-sql-server.md) , não haverá suporte para a restauração pontual.</span><span class="sxs-lookup"><span data-stu-id="6ce35-195">If a partial restore sequence excludes any [FILESTREAM](../blob/filestream-sql-server.md) filegroup, point-in-time restore is not supported.</span></span> <span data-ttu-id="6ce35-196">Você pode forçar a sequência de restauração a continuar.</span><span class="sxs-lookup"><span data-stu-id="6ce35-196">You can force the restore sequence to continue.</span></span> <span data-ttu-id="6ce35-197">Contudo, os grupos de arquivos FILESTREAM omitidos de sua instrução RESTORE nunca poderão ser restaurados.</span><span class="sxs-lookup"><span data-stu-id="6ce35-197">However the FILESTREAM filegroups that are omitted from your RESTORE statement can never be restored.</span></span> <span data-ttu-id="6ce35-198">Para forçar uma restauração pontual, especifique a opção CONTINUE_AFTER_ERROR juntamente com a opção STOPAT, STOPATMARK ou STOPBEFOREMARK, que você também deve especificar nas instruções RESTORE LOG subsequentes.</span><span class="sxs-lookup"><span data-stu-id="6ce35-198">To force a point-in-time restore, specify the CONTINUE_AFTER_ERROR option together with the STOPAT, STOPATMARK, or STOPBEFOREMARK option, which you must also specify in your subsequent RESTORE LOG statements.</span></span> <span data-ttu-id="6ce35-199">Se você especificar CONTINUE_AFTER_ERROR, a sequência de restauração parcial terá êxito e o grupo de arquivos FILESTREAM se tornará irrecuperável.</span><span class="sxs-lookup"><span data-stu-id="6ce35-199">If you specify CONTINUE_AFTER_ERROR, the partial restore sequence succeeds and the FILESTREAM filegroup becomes unrecoverable.</span></span>  
  
3.  <span data-ttu-id="6ce35-200">Restaurar o último backup de banco de dados diferencial e, se houver, sem recuperar o banco de dados (RESTORE DATABASE *database_name* FROM *backup_device* WITH NORECOVERY).</span><span class="sxs-lookup"><span data-stu-id="6ce35-200">Restore the last differential database backup, if any,  without recovering the database (RESTORE DATABASE *database_name* FROM *backup_device* WITH NORECOVERY).</span></span>  
  
4.  <span data-ttu-id="6ce35-201">Aplique cada backup de log de transações na mesma sequência em que eles foram criados, especificando a hora em que você pretende interromper a restauração do log (Restore Database *database_name* de <backup_device> com STOPAT\*\* = *`time`* ,\*\* Recovery).</span><span class="sxs-lookup"><span data-stu-id="6ce35-201">Apply each transaction log backup in the same sequence in which they were created, specifying the time at which you intend to stop restoring log (RESTORE DATABASE *database_name* FROM <backup_device> WITH STOPAT**=*`time`*,** RECOVERY).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6ce35-202">As opções RECOVERY e STOPAT.</span><span class="sxs-lookup"><span data-stu-id="6ce35-202">The RECOVERY and STOPAT options.</span></span> <span data-ttu-id="6ce35-203">Se o backup de log de transações não contiver o tempo solicitado (por exemplo, se o tempo especificado estiver além do tempo coberto pelo log de transações), um aviso será gerado e o banco de dados permanecerá sem-recuperação.</span><span class="sxs-lookup"><span data-stu-id="6ce35-203">If the transaction log backup does not contain the requested time (for example, if the time specified is beyond the end of the time covered by the transaction log), a warning is generated and the database remains unrecovered.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="6ce35-204">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6ce35-204">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="6ce35-205">O exemplo a seguir restaura um banco de dados para seu estado de `12:00 AM` em `April 15, 2020` e mostra uma operação de restauração que envolve vários backups de log.</span><span class="sxs-lookup"><span data-stu-id="6ce35-205">The following example restores a database to its state as of `12:00 AM` on `April 15, 2020` and shows a restore operation that involves multiple log backups.</span></span> <span data-ttu-id="6ce35-206">No dispositivo de backup, `AdventureWorksBackups`, o backup de banco de dados completo a ser restaurado é o terceiro conjunto de backup no dispositivo (`FILE = 3`), o primeiro backup de log é o quarto conjunto de backup (`FILE = 4`), e o segundo backup de log é o quinto conjunto de backup (`FILE = 5`).</span><span class="sxs-lookup"><span data-stu-id="6ce35-206">On the backup device, `AdventureWorksBackups`, the full database backup to be restored is the third backup set on the device (`FILE = 3`), the first log backup is the fourth backup set (`FILE = 4`), and the second log backup is the fifth backup set (`FILE = 5`).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6ce35-207">O banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] usa o modelo de recuperação simples.</span><span class="sxs-lookup"><span data-stu-id="6ce35-207">The [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database uses the simple recovery model.</span></span> <span data-ttu-id="6ce35-208">Para permitir backups de log, antes de fazer um backup de banco de dados completo, o banco de dados foi definido para usar o modelo de recuperação completa, usando `ALTER DATABASE AdventureWorks SET RECOVERY FULL`.</span><span class="sxs-lookup"><span data-stu-id="6ce35-208">To permit log backups, before taking a full database backup, the database was set to use the full recovery model, using `ALTER DATABASE AdventureWorks SET RECOVERY FULL`.</span></span>  
  
```  
RESTORE DATABASE AdventureWorks  
   FROM AdventureWorksBackups  
   WITH FILE=3, NORECOVERY;  
  
RESTORE LOG AdventureWorks  
   FROM AdventureWorksBackups  
   WITH FILE=4, NORECOVERY, STOPAT = 'Apr 15, 2020 12:00 AM';  
  
RESTORE LOG AdventureWorks  
   FROM AdventureWorksBackups  
   WITH FILE=5, NORECOVERY, STOPAT = 'Apr 15, 2020 12:00 AM';  
RESTORE DATABASE AdventureWorks WITH RECOVERY;   
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="6ce35-209">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="6ce35-209">Related Tasks</span></span>  
  
-   [<span data-ttu-id="6ce35-210">Restaurar um backup de banco de dados &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6ce35-210">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="6ce35-211">Fazer backup de um log de transações &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6ce35-211">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
-   [<span data-ttu-id="6ce35-212">Restaurar um banco de dados até o ponto de falha no modelo de recuperação completa &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6ce35-212">Restore a Database to the Point of Failure Under the Full Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-database-to-point-of-failure-full-recovery.md)  
  
-   [<span data-ttu-id="6ce35-213">Restaurar um banco de dados para uma transação marcada &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6ce35-213">Restore a Database to a Marked Transaction &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-to-a-marked-transaction-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="6ce35-214">Recuperar para um número de sequência de log &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6ce35-214">Recover to a Log Sequence Number &#40;SQL Server&#41;</span></span>](recover-to-a-log-sequence-number-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="6ce35-215">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6ce35-215">See Also</span></span>  
 <span data-ttu-id="6ce35-216">[conjunto de backup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6ce35-216">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="6ce35-217">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6ce35-217">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="6ce35-218">RESTORE HEADERONLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6ce35-218">RESTORE HEADERONLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-headeronly-transact-sql)  
  
  
