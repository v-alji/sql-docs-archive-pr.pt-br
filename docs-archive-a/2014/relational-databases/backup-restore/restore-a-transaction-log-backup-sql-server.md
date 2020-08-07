---
title: Restaurar um backup de log de transações (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.restoretlog.options.f1
- sql12.swb.restoretlog.general.f1
helpviewer_keywords:
- restore log
- backing up transaction logs [SQL Server], restoring
- transaction log backups [SQL Server], restoring
- restoring transaction logs [SQL Server], restoring backups
- transaction log restores [SQL Server], SQL Server Management Studio
ms.assetid: 1de2b888-78a6-4fb2-a647-ba4bf097caf3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 68fe4bbc199d6555bd490d25f92491100b8bbfcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581408"
---
# <a name="restore-a-transaction-log-backup-sql-server"></a><span data-ttu-id="6e46c-102">Restaurar um backup de log de transações (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6e46c-102">Restore a Transaction Log Backup (SQL Server)</span></span>
  <span data-ttu-id="6e46c-103">Este tópico descreve como restaurar um backup de log de transação no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6e46c-103">This topic describes how to restore a transaction log backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="6e46c-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="6e46c-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6e46c-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="6e46c-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6e46c-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="6e46c-106">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="6e46c-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="6e46c-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6e46c-108">**Para restaurar um backup de log de transações, usando:**</span><span class="sxs-lookup"><span data-stu-id="6e46c-108">**To restore a transaction log backup, using:**</span></span>  
  
     [<span data-ttu-id="6e46c-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6e46c-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6e46c-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6e46c-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="6e46c-111">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="6e46c-111">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6e46c-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="6e46c-112">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="6e46c-113">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="6e46c-113">Prerequisites</span></span>  
  
-   <span data-ttu-id="6e46c-114">Os backups devem ser restaurados na ordem em que foram criados.</span><span class="sxs-lookup"><span data-stu-id="6e46c-114">Backups must be restored in the order in which they were created.</span></span> <span data-ttu-id="6e46c-115">Antes de poder restaurar um backup de log de transações específico, restaure primeiro os backups anteriores seguintes sem reverter as transações não confirmadas, isto é WITH NORECOVERY:</span><span class="sxs-lookup"><span data-stu-id="6e46c-115">Before you can restore a particular transaction log backup, you must first restore the following previous backups without rolling back uncommitted transactions, that is WITH NORECOVERY:</span></span>  
  
    -   <span data-ttu-id="6e46c-116">O backup de banco de dados completo e o último backup diferencial, se houver, realizado antes do backup de log de transações específico.</span><span class="sxs-lookup"><span data-stu-id="6e46c-116">The full database backup and the last differential backup, if any, taken before the particular transaction log backup.</span></span> <span data-ttu-id="6e46c-117">Antes do backup de banco de dados completo ou diferencial mais recente tiver sido criado, o banco de dados deverá usar o modelo de recuperação completa ou o modelo de recuperação bulk-logged.</span><span class="sxs-lookup"><span data-stu-id="6e46c-117">Before the most recent full or differential database backup was created, the database must have been using the full recovery model or bulk-logged recovery model.</span></span>  
  
    -   <span data-ttu-id="6e46c-118">Todos os backups de log de transações efetuados depois do backup de banco de dados completo ou o backup diferencial (se você o restaurar) e antes do backup de log de transações específico.</span><span class="sxs-lookup"><span data-stu-id="6e46c-118">All transaction log backups taken after the full database backup or the differential backup (if you restore one) and before the particular transaction log backup.</span></span> <span data-ttu-id="6e46c-119">Devem ser aplicados backups de log na sequência na qual eles foram criados, sem qualquer intervalo na cadeia de logs.</span><span class="sxs-lookup"><span data-stu-id="6e46c-119">Log backups must be applied in the sequence in which they were created, without any gaps in the log chain.</span></span>  
  
         <span data-ttu-id="6e46c-120">Para obter mais informações sobre backups de log de transações, consulte [Backups de log de transações &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) e [Aplicar backups de log de transações &#40;SQL Server&#41;](apply-transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6e46c-120">For more information about transaction log backups, see [Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) and [Apply Transaction Log Backups &#40;SQL Server&#41;](apply-transaction-log-backups-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6e46c-121">Segurança</span><span class="sxs-lookup"><span data-stu-id="6e46c-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6e46c-122">Permissões</span><span class="sxs-lookup"><span data-stu-id="6e46c-122">Permissions</span></span>  
 <span data-ttu-id="6e46c-123">As permissões RESTORE são concedidas a funções nas quais as informações de associação estão sempre disponíveis para o servidor.</span><span class="sxs-lookup"><span data-stu-id="6e46c-123">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="6e46c-124">Como a associação da função de banco de dados fixa pode ser verificada apenas quando o banco de dados está acessível e não danificado, o que nem sempre é o caso quando RESTORE é executado, os membros da função de banco de dados fixa **db_owner** não têm permissões RESTORE.</span><span class="sxs-lookup"><span data-stu-id="6e46c-124">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6e46c-125">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6e46c-125">Using SQL Server Management Studio</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="6e46c-126">O processo normal de uma restauração é selecionar os backups de log na caixa de diálogo **Restaurar Banco de Dados** junto com os dados e backups diferenciais.</span><span class="sxs-lookup"><span data-stu-id="6e46c-126">The normal process of a restore is to select the log backups in the **Restore Database** dialog box along with the data and differential backups.</span></span>  
  
#### <a name="to-restore-a-transaction-log-backup"></a><span data-ttu-id="6e46c-127">Para restaurar um backup de log de transações</span><span class="sxs-lookup"><span data-stu-id="6e46c-127">To restore a transaction log backup</span></span>  
  
1.  <span data-ttu-id="6e46c-128">Depois de se conectar à instância apropriada do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], em Pesquisador de Objetos, clique no nome do servidor para expandir a árvore do servidor.</span><span class="sxs-lookup"><span data-stu-id="6e46c-128">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="6e46c-129">Expanda **Bancos de Dados**e, dependendo do banco de dados, selecione um banco de dados de usuário ou expanda **Bancos de Dados do Sistema** e selecione um banco de dados do sistema.</span><span class="sxs-lookup"><span data-stu-id="6e46c-129">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="6e46c-130">Clique com o botão direito do mouse no banco de dados, aponte para **Tarefas**, **Restaurar**e clique em **Log de Transações**, o que abre a caixa de diálogo **Restaurar Log de Transações** .</span><span class="sxs-lookup"><span data-stu-id="6e46c-130">Right-click the database, point to **Tasks**, point to **Restore**, and then click **Transaction Log**, which opens the **Restore Transaction Log** dialog box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6e46c-131">Se a opção **Log de Transações** estiver acinzentada, talvez seja necessário restaurar um backup completo ou diferencial primeiro.</span><span class="sxs-lookup"><span data-stu-id="6e46c-131">If **Transaction Log** is grayed out, you may need to restore a full or differential backup first.</span></span> <span data-ttu-id="6e46c-132">Use a caixa de diálogo **Backup de banco de dados** .</span><span class="sxs-lookup"><span data-stu-id="6e46c-132">Use the **Database** backup dialog box.</span></span>  
  
4.  <span data-ttu-id="6e46c-133">Na página **Geral** , na caixa de listagem **Banco de Dados** , selecione o nome de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6e46c-133">On the **General** page, in the **Database** list box, select the name of a database.</span></span> <span data-ttu-id="6e46c-134">Só são listados bancos de dados no estado de restauração.</span><span class="sxs-lookup"><span data-stu-id="6e46c-134">Only databases in the restoring state are listed.</span></span>  
  
5.  <span data-ttu-id="6e46c-135">Para especificar a origem e o local dos conjuntos de backup a serem restaurados, clique em uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="6e46c-135">To specify the source and location of the backup sets to restore, click one of the following options:</span></span>  
  
    -   <span data-ttu-id="6e46c-136">**De backups anteriores do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="6e46c-136">**From previous backups of database**</span></span>  
  
         <span data-ttu-id="6e46c-137">Selecione o banco de dados a ser restaurado na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="6e46c-137">Select the database to restore from the drop-down list.</span></span> <span data-ttu-id="6e46c-138">A lista contém apenas os bancos de dados dos quais foi feito um backup de acordo com o histórico de backup do **msdb** .</span><span class="sxs-lookup"><span data-stu-id="6e46c-138">The list contains only databases that have been backed up according to the **msdb** backup history.</span></span>  
  
    -   <span data-ttu-id="6e46c-139">**Do arquivo ou fita**</span><span class="sxs-lookup"><span data-stu-id="6e46c-139">**From file or tape**</span></span>  
  
         <span data-ttu-id="6e46c-140">Clique no botão Procurar ( **...** ) para abrir a caixa de diálogo **Selecione dispositivos de backup** .</span><span class="sxs-lookup"><span data-stu-id="6e46c-140">Click the browse (**...**) button to open the **Select backup devices** dialog box.</span></span> <span data-ttu-id="6e46c-141">Na caixa **Tipo de mídia de backup** , selecione um dos tipos de dispositivo listados.</span><span class="sxs-lookup"><span data-stu-id="6e46c-141">In the **Backup media type** box, select one of the listed device types.</span></span> <span data-ttu-id="6e46c-142">Para selecionar um ou mais dispositivos da caixa **Mídia de backup** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="6e46c-142">To select one or more devices for the **Backup media** box, click **Add**.</span></span>  
  
         <span data-ttu-id="6e46c-143">Após adicionar os dispositivos desejados à caixa de listagem **Mídia de backup** , clique em **OK** para voltar à página **Geral** .</span><span class="sxs-lookup"><span data-stu-id="6e46c-143">After you add the devices you want to the **Backup media** list box, click **OK** to return to the **General** page.</span></span>  
  
6.  <span data-ttu-id="6e46c-144">Na grade **Selecione os backups de log de transações a serem restaurados** , selecione os backups a serem restaurados.</span><span class="sxs-lookup"><span data-stu-id="6e46c-144">In the **Select the transaction log backups to restore** grid, select the backups to restore.</span></span> <span data-ttu-id="6e46c-145">Essa grade lista os backups de log de transações disponíveis para o banco de dados selecionado.</span><span class="sxs-lookup"><span data-stu-id="6e46c-145">This grid lists the transaction log backups available for the selected database.</span></span> <span data-ttu-id="6e46c-146">Um backup de log só estará disponível se o **Primeiro LSN** for maior do que o **Último LSN** do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6e46c-146">A log backup is available only if its **First LSN** greater than the **Last LSN** of the database.</span></span> <span data-ttu-id="6e46c-147">Os backups de log são listados na ordem dos números de sequência de log (LSN) que eles contêm e devem ser restaurados nessa ordem.</span><span class="sxs-lookup"><span data-stu-id="6e46c-147">Log backups are listed in the order of the log sequence numbers (LSN) they contain, and they must be restored in this order.</span></span>  
  
     <span data-ttu-id="6e46c-148">A tabela a seguir lista os cabeçalhos de coluna da grade e descreve seus valores.</span><span class="sxs-lookup"><span data-stu-id="6e46c-148">The following table lists the column headers of the grid and describes their values.</span></span>  
  
    |<span data-ttu-id="6e46c-149">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="6e46c-149">Header</span></span>|<span data-ttu-id="6e46c-150">Valor</span><span class="sxs-lookup"><span data-stu-id="6e46c-150">Value</span></span>|  
    |------------|-----------|  
    |<span data-ttu-id="6e46c-151">**Restaurar**</span><span class="sxs-lookup"><span data-stu-id="6e46c-151">**Restore**</span></span>|<span data-ttu-id="6e46c-152">Caixas de seleção selecionadas indicam os conjuntos de backup a serem restaurados.</span><span class="sxs-lookup"><span data-stu-id="6e46c-152">Selected check boxes indicate the backup sets to be restored.</span></span>|  
    |<span data-ttu-id="6e46c-153">**Nome**</span><span class="sxs-lookup"><span data-stu-id="6e46c-153">**Name**</span></span>|<span data-ttu-id="6e46c-154">Nome do conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="6e46c-154">Name of the backup set.</span></span>|  
    |<span data-ttu-id="6e46c-155">**Componente**</span><span class="sxs-lookup"><span data-stu-id="6e46c-155">**Component**</span></span>|<span data-ttu-id="6e46c-156">O componente de backup: **Banco de dados**, **Arquivo** ou \<blank> (para logs de transações).</span><span class="sxs-lookup"><span data-stu-id="6e46c-156">Backed-up component: **Database**, **File**, or \<blank> (for transaction logs).</span></span>|  
    |<span data-ttu-id="6e46c-157">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="6e46c-157">**Database**</span></span>|<span data-ttu-id="6e46c-158">Nome do banco de dados envolvido na operação de backup.</span><span class="sxs-lookup"><span data-stu-id="6e46c-158">Name of the database involved in the backup operation.</span></span>|  
    |<span data-ttu-id="6e46c-159">**Data de Início**</span><span class="sxs-lookup"><span data-stu-id="6e46c-159">**Start Date**</span></span>|<span data-ttu-id="6e46c-160">A data e hora do início da operação de backup, apresentadas na configuração regional do cliente.</span><span class="sxs-lookup"><span data-stu-id="6e46c-160">Date and time when the backup operation began, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="6e46c-161">**Data de Conclusão**</span><span class="sxs-lookup"><span data-stu-id="6e46c-161">**Finish Date**</span></span>|<span data-ttu-id="6e46c-162">Data e hora de término da operação de backup, apresentadas na configuração regional do cliente.</span><span class="sxs-lookup"><span data-stu-id="6e46c-162">Date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="6e46c-163">**Primeiro LSN**</span><span class="sxs-lookup"><span data-stu-id="6e46c-163">**First LSN**</span></span>|<span data-ttu-id="6e46c-164">Número de sequência de log da primeira transação no conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="6e46c-164">Log sequence number of the first transaction in the backup set.</span></span> <span data-ttu-id="6e46c-165">Em branco para backups de arquivo.</span><span class="sxs-lookup"><span data-stu-id="6e46c-165">Blank for file backups.</span></span>|  
    |<span data-ttu-id="6e46c-166">**Último LSN**</span><span class="sxs-lookup"><span data-stu-id="6e46c-166">**Last LSN**</span></span>|<span data-ttu-id="6e46c-167">Número de sequência de log da última transação no conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="6e46c-167">Log sequence number of the last transaction in the backup set.</span></span> <span data-ttu-id="6e46c-168">Em branco para backups de arquivo.</span><span class="sxs-lookup"><span data-stu-id="6e46c-168">Blank for file backups.</span></span>|  
    |<span data-ttu-id="6e46c-169">**LSN do Ponto de Verificação**</span><span class="sxs-lookup"><span data-stu-id="6e46c-169">**Checkpoint LSN**</span></span>|<span data-ttu-id="6e46c-170">Número de sequência de log do ponto de verificação mais recente no momento em que o backup foi criado.</span><span class="sxs-lookup"><span data-stu-id="6e46c-170">Log sequence number of the most recent checkpoint at the time the backup was created.</span></span>|  
    |<span data-ttu-id="6e46c-171">**LSN Completo**</span><span class="sxs-lookup"><span data-stu-id="6e46c-171">**Full LSN**</span></span>|<span data-ttu-id="6e46c-172">Número de sequência de log do backup de banco de dados completo mais recente.</span><span class="sxs-lookup"><span data-stu-id="6e46c-172">Log sequence number of the most recent full database backup.</span></span>|  
    |<span data-ttu-id="6e46c-173">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="6e46c-173">**Server**</span></span>|<span data-ttu-id="6e46c-174">Nome da instância do Mecanismo de Banco de Dados que executou a operação de backup.</span><span class="sxs-lookup"><span data-stu-id="6e46c-174">Name of the Database Engine instance that performed the backup operation.</span></span>|  
    |<span data-ttu-id="6e46c-175">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="6e46c-175">**User Name**</span></span>|<span data-ttu-id="6e46c-176">Nome do usuário que realizou a operação de backup.</span><span class="sxs-lookup"><span data-stu-id="6e46c-176">Name of the user who performed the backup operation.</span></span>|  
    |<span data-ttu-id="6e46c-177">**Tamanho**</span><span class="sxs-lookup"><span data-stu-id="6e46c-177">**Size**</span></span>|<span data-ttu-id="6e46c-178">Tamanho do conjunto de backup em bytes.</span><span class="sxs-lookup"><span data-stu-id="6e46c-178">Size of the backup set in bytes.</span></span>|  
    |<span data-ttu-id="6e46c-179">**Posição**</span><span class="sxs-lookup"><span data-stu-id="6e46c-179">**Position**</span></span>|<span data-ttu-id="6e46c-180">Posição do conjunto de backup no volume.</span><span class="sxs-lookup"><span data-stu-id="6e46c-180">Position of the backup set in the volume.</span></span>|  
    |<span data-ttu-id="6e46c-181">**Validade**</span><span class="sxs-lookup"><span data-stu-id="6e46c-181">**Expiration**</span></span>|<span data-ttu-id="6e46c-182">Data e hora de vencimento do conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="6e46c-182">Date and time the backup set expires.</span></span>|  
  
7.  <span data-ttu-id="6e46c-183">Selecione uma das seguintes:</span><span class="sxs-lookup"><span data-stu-id="6e46c-183">Select one of the following:</span></span>  
  
    -   <span data-ttu-id="6e46c-184">**Point-in-time**</span><span class="sxs-lookup"><span data-stu-id="6e46c-184">**Point in time**</span></span>  
  
         <span data-ttu-id="6e46c-185">Retenha o padrão (**Mais recente possível**) ou selecione uma data e hora específicas clicando no botão Procurar, que abre a caixa de diálogo **Recuperação Pontual** .</span><span class="sxs-lookup"><span data-stu-id="6e46c-185">Either retain the default (**Most recent possible**) or select a specific date and time by clicking the browse button, which opens the **Point in Time Restore** dialog box.</span></span>  
  
    -   <span data-ttu-id="6e46c-186">**Transação marcada**</span><span class="sxs-lookup"><span data-stu-id="6e46c-186">**Marked transaction**</span></span>  
  
         <span data-ttu-id="6e46c-187">Restaure o banco de dados a uma transação previamente marcada.</span><span class="sxs-lookup"><span data-stu-id="6e46c-187">Restore the database to a previously marked transaction.</span></span> <span data-ttu-id="6e46c-188">Selecionar esta opção inicia a caixa de diálogo **Selecionar Transação Marcada** que exibe uma grade com uma lista das transações marcadas disponíveis nos backups de log de transações selecionados.</span><span class="sxs-lookup"><span data-stu-id="6e46c-188">Selecting this option launches the **Select Marked Transaction** dialog box, which displays a grid listing the marked transactions available in the selected transaction log backups.</span></span>  
  
         <span data-ttu-id="6e46c-189">Por padrão, a restauração vai até a transação marcada, mas a exclui.</span><span class="sxs-lookup"><span data-stu-id="6e46c-189">By default, the restore is up to, but excluding, the marked transaction.</span></span> <span data-ttu-id="6e46c-190">Para restaurar também a transação marcada, selecione **Incluir transação marcada**.</span><span class="sxs-lookup"><span data-stu-id="6e46c-190">To restore the marked transaction also, select **Include marked transaction**.</span></span>  
  
         <span data-ttu-id="6e46c-191">A tabela a seguir lista os cabeçalhos de coluna da grade e descreve seus valores.</span><span class="sxs-lookup"><span data-stu-id="6e46c-191">The following table lists the column headers of the grid and describes their values.</span></span>  
  
        |<span data-ttu-id="6e46c-192">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="6e46c-192">Header</span></span>|<span data-ttu-id="6e46c-193">Valor</span><span class="sxs-lookup"><span data-stu-id="6e46c-193">Value</span></span>|  
        |------------|-----------|  
        |\<blank>|<span data-ttu-id="6e46c-194">Exibe uma caixa de seleção para selecionar a marca.</span><span class="sxs-lookup"><span data-stu-id="6e46c-194">Displays a checkbox for selecting the mark.</span></span>|  
        |<span data-ttu-id="6e46c-195">**Transaction Mark**</span><span class="sxs-lookup"><span data-stu-id="6e46c-195">**Transaction Mark**</span></span>|<span data-ttu-id="6e46c-196">Nome da transação marcada especificado pelo usuário quando a transação foi confirmada.</span><span class="sxs-lookup"><span data-stu-id="6e46c-196">Name of the marked transaction specified by the user when the transaction was committed.</span></span>|  
        |<span data-ttu-id="6e46c-197">**Data**</span><span class="sxs-lookup"><span data-stu-id="6e46c-197">**Date**</span></span>|<span data-ttu-id="6e46c-198">Data e hora de confirmação da transação.</span><span class="sxs-lookup"><span data-stu-id="6e46c-198">Date and time of the transaction when it was committed.</span></span> <span data-ttu-id="6e46c-199">A data e hora da transação são exibidas como registradas na tabela **msdbgmarkhistory** , não a data e hora do computador cliente.</span><span class="sxs-lookup"><span data-stu-id="6e46c-199">Transaction date and time are displayed as recorded in the **msdbgmarkhistory** table, not in the client computer's date and time.</span></span>|  
        |<span data-ttu-id="6e46c-200">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="6e46c-200">**Description**</span></span>|<span data-ttu-id="6e46c-201">Descrição da transação marcada especificada pelo usuário quando a transação foi confirmada (se houver).</span><span class="sxs-lookup"><span data-stu-id="6e46c-201">Description of marked transaction specified by the user when the transaction was committed (if any).</span></span>|  
        |<span data-ttu-id="6e46c-202">**LSN**</span><span class="sxs-lookup"><span data-stu-id="6e46c-202">**LSN**</span></span>|<span data-ttu-id="6e46c-203">Número de sequência de log da transação marcada.</span><span class="sxs-lookup"><span data-stu-id="6e46c-203">Log sequence number of the marked transaction.</span></span>|  
        |<span data-ttu-id="6e46c-204">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="6e46c-204">**Database**</span></span>|<span data-ttu-id="6e46c-205">Nome do banco de dados em que a transação marcada foi confirmada.</span><span class="sxs-lookup"><span data-stu-id="6e46c-205">Name of the database where the marked transaction was committed.</span></span>|  
        |<span data-ttu-id="6e46c-206">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="6e46c-206">**User Name**</span></span>|<span data-ttu-id="6e46c-207">Nome do usuário do banco de dados que confirmou a transação marcada.</span><span class="sxs-lookup"><span data-stu-id="6e46c-207">Name of the database user who committed the marked transaction.</span></span>|  
  
8.  <span data-ttu-id="6e46c-208">Para exibir ou selecionar as opções avançadas, clique em **Opções** no painel **Selecionar uma página** .</span><span class="sxs-lookup"><span data-stu-id="6e46c-208">To view or select the advanced options, click **Options** in the **Select a page** pane.</span></span>  
  
9. <span data-ttu-id="6e46c-209">Na seção **Opções de restauração** , as opções são:</span><span class="sxs-lookup"><span data-stu-id="6e46c-209">In the **Restore options** section, the choices are:</span></span>  
  
    -   <span data-ttu-id="6e46c-210">**Preservar as configurações de replicação (WITH KEEP_REPLICATION)**</span><span class="sxs-lookup"><span data-stu-id="6e46c-210">**Preserve the replication settings (WITH KEEP_REPLICATION)**</span></span>  
  
         <span data-ttu-id="6e46c-211">Preserva as configurações de replicação ao restaurar um banco de dados publicado em um servidor diferente daquele onde o banco de dados foi criado.</span><span class="sxs-lookup"><span data-stu-id="6e46c-211">Preserves the replication settings when restoring a published database to a server other than the server where the database was created.</span></span>  
  
         <span data-ttu-id="6e46c-212">Essa opção está disponível apenas com a opção **deixar o banco de dados pronto para uso revertendo as transações não confirmadas...** (descrito posteriormente), que é equivalente a restaurar um backup com a `RECOVERY` opção.</span><span class="sxs-lookup"><span data-stu-id="6e46c-212">This option is available only with the **Leave the database ready for use by rolling back the uncommitted transactions...** option (described later), which is equivalent to restoring a backup with the `RECOVERY` option.</span></span>  
  
         <span data-ttu-id="6e46c-213">Marcar essa opção é equivalente a usar a `KEEP_REPLICATION` opção em uma [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` instrução.</span><span class="sxs-lookup"><span data-stu-id="6e46c-213">Checking this option is equivalent to using the `KEEP_REPLICATION` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
    -   <span data-ttu-id="6e46c-214">**Perguntar antes de restaurar cada backup**</span><span class="sxs-lookup"><span data-stu-id="6e46c-214">**Prompt before restoring each backup**</span></span>  
  
         <span data-ttu-id="6e46c-215">Antes de restaurar cada conjunto de backup (depois do primeiro), essa opção traz a caixa de diálogo **Continuar Restauração** que solicita a você que indique se deseja continuar a sequência de restauração.</span><span class="sxs-lookup"><span data-stu-id="6e46c-215">Before restoring each backup set (after the first), this option brings up the **Continue with Restore** dialog box, which asks you to indicate whether you want to continue the restore sequence.</span></span> <span data-ttu-id="6e46c-216">Essa caixa de diálogo exibe o nome do próximo conjunto de mídia (se disponível), o nome do conjunto de backup e a descrição do conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="6e46c-216">This dialog displays the name of the next media set (if available), the backup set name, and backup set description.</span></span>  
  
         <span data-ttu-id="6e46c-217">Essa opção é particularmente útil quando você deve trocar fitas para conjuntos de mídia diferentes.</span><span class="sxs-lookup"><span data-stu-id="6e46c-217">This option is particularly useful when you must swap tapes for different media sets.</span></span> <span data-ttu-id="6e46c-218">Por exemplo, você poderá usá-la quando o servidor tiver só um dispositivo de fita.</span><span class="sxs-lookup"><span data-stu-id="6e46c-218">For example, you can use it when the server has only one tape device.</span></span> <span data-ttu-id="6e46c-219">Espere até estar pronto para continuar antes de clicar em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e46c-219">Wait until you are ready to proceed before clicking **OK**.</span></span>  
  
         <span data-ttu-id="6e46c-220">Clicar em **Não** deixa o banco de dados em estado de restauração.</span><span class="sxs-lookup"><span data-stu-id="6e46c-220">Clicking **No** leaves the database in the restoring state.</span></span> <span data-ttu-id="6e46c-221">Quando for conveniente, você poderá continuar a sequência de restauração depois da última restauração concluída.</span><span class="sxs-lookup"><span data-stu-id="6e46c-221">At your convenience, you can continue the restore sequence after the last restore that completed.</span></span> <span data-ttu-id="6e46c-222">Se o próximo backup for um backup de dados ou diferencial, use a tarefa **Restaurar Banco de Dados** novamente.</span><span class="sxs-lookup"><span data-stu-id="6e46c-222">If the next backup is a data or differential backup, use the **Restore Database** task again.</span></span> <span data-ttu-id="6e46c-223">Se o backup seguinte for um backup de log, use a tarefa **Restaurar Log de Transações** .</span><span class="sxs-lookup"><span data-stu-id="6e46c-223">If the next backup is a log backup, use the **Restore Transaction Log** task.</span></span>  
  
    -   <span data-ttu-id="6e46c-224">**Acesso restrito ao banco de dados restaurado (WITH RESTRICTED_USER)**</span><span class="sxs-lookup"><span data-stu-id="6e46c-224">**Restrict access to the restored database (WITH RESTRICTED_USER)**</span></span>  
  
         <span data-ttu-id="6e46c-225">Disponibiliza o banco de dados restaurado apenas para os membros do **db_owner**, **dbcreator**ou **sysadmin**.</span><span class="sxs-lookup"><span data-stu-id="6e46c-225">Makes the restored database available only to the members of **db_owner**, **dbcreator**, or **sysadmin**.</span></span>  
  
         <span data-ttu-id="6e46c-226">Marcar essa opção é sinônimo de usar a `RESTRICTED_USER` opção em uma [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` instrução.</span><span class="sxs-lookup"><span data-stu-id="6e46c-226">Checking this option is synonymous to using the `RESTRICTED_USER` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
10. <span data-ttu-id="6e46c-227">Para as opções **Estado de recuperação** , especifique o estado do banco de dados após a operação de restauração.</span><span class="sxs-lookup"><span data-stu-id="6e46c-227">For the **Recovery state** options, specify the state of the database after the restore operation.</span></span>  
  
    -   <span data-ttu-id="6e46c-228">**Deixe o banco de dados pronto para uso revertendo as transações não confirmadas. Os logs de transações adicionais não podem ser restaurados. (RESTORE WITH RECOVERY)**</span><span class="sxs-lookup"><span data-stu-id="6e46c-228">**Leave the database ready for use by rolling back uncommitted transactions. Additional transaction logs cannot be restored. (RESTORE WITH RECOVERY)**</span></span>  
  
         <span data-ttu-id="6e46c-229">Recupera o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6e46c-229">Recovers the database.</span></span> <span data-ttu-id="6e46c-230">Essa opção é equivalente à `RECOVERY` opção em uma [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` instrução.</span><span class="sxs-lookup"><span data-stu-id="6e46c-230">This option is equivalent to the `RECOVERY` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
         <span data-ttu-id="6e46c-231">Só escolha essa opção se você não tiver nenhum arquivo de log que queira restaurar.</span><span class="sxs-lookup"><span data-stu-id="6e46c-231">Choose this option only if you have no log files you want to restore.</span></span>  
  
    -   <span data-ttu-id="6e46c-232">**Deixe o banco de dados não operacional e não reverta as transações não confirmadas. Os logs de transações adicionais podem ser restaurados. (RESTORE WITH NORECOVERY)**</span><span class="sxs-lookup"><span data-stu-id="6e46c-232">**Leave the database non-operational, and do not roll back uncommitted transactions. Additional transaction logs can be restored. (RESTORE WITH NORECOVERY)**</span></span>  
  
         <span data-ttu-id="6e46c-233">Deixa o banco de dados não recuperado, no estado `RESTORING`.</span><span class="sxs-lookup"><span data-stu-id="6e46c-233">Leaves the database unrecovered, in the `RESTORING` state.</span></span> <span data-ttu-id="6e46c-234">Essa opção é equivalente a usar a `NORECOVERY` opção em uma [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` instrução.</span><span class="sxs-lookup"><span data-stu-id="6e46c-234">This option is equivalent to using the `NORECOVERY` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
         <span data-ttu-id="6e46c-235">Quando você escolhe essa opção, a opção **Preservar configurações de replicação** fica indisponível.</span><span class="sxs-lookup"><span data-stu-id="6e46c-235">When you choose this option, the **Preserve replication settings** option is unavailable.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="6e46c-236">Para um banco de dados espelho ou secundário, sempre selecione essa opção.</span><span class="sxs-lookup"><span data-stu-id="6e46c-236">For a mirror or secondary database, always select this option.</span></span>  
  
    -   <span data-ttu-id="6e46c-237">**Deixar o banco de dados no modo somente leitura. Desfaça as transações não confirmadas, mas salve as ações de desfazer em um arquivo, para que os efeitos da recuperação possam ser revertidos. (RESTORE WITH STANDBY)**</span><span class="sxs-lookup"><span data-stu-id="6e46c-237">**Leave the database in read-only mode. Undo uncommitted transactions, but save the undo actions in a file so that recovery effects can be reversed. (RESTORE WITH STANDBY)**</span></span>  
  
         <span data-ttu-id="6e46c-238">Deixa o banco de dados no estado de espera.</span><span class="sxs-lookup"><span data-stu-id="6e46c-238">Leaves the database in a standby state.</span></span> <span data-ttu-id="6e46c-239">Essa opção é equivalente a usar a `STANDBY` opção em uma [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` instrução.</span><span class="sxs-lookup"><span data-stu-id="6e46c-239">This option is equivalent to using the `STANDBY` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
         <span data-ttu-id="6e46c-240">A escolha desta opção requer que você especifique um arquivo de espera.</span><span class="sxs-lookup"><span data-stu-id="6e46c-240">Choosing this option requires that you specify a standby file.</span></span>  
  
11. <span data-ttu-id="6e46c-241">Opcionalmente, especifique o nome do arquivo em espera na caixa de texto **Arquivo em espera** .</span><span class="sxs-lookup"><span data-stu-id="6e46c-241">Optionally, specify a standby file name in the **Standby file** text box.</span></span> <span data-ttu-id="6e46c-242">Essa opção será necessária se você deixar o banco de dados no modo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="6e46c-242">This option is required if you leave the database in read-only mode.</span></span> <span data-ttu-id="6e46c-243">Você pode procurar o arquivo em espera ou pode digitar o nome do caminho na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="6e46c-243">You can browse for the standby file or type its pathname in the text box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6e46c-244">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6e46c-244">Using Transact-SQL</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6e46c-245">Nós recomendamos que você sempre especifique explicite WITH NORECOVERY ou WITH RECOVERY em toda instrução RESTORE para eliminar a ambiguidade.</span><span class="sxs-lookup"><span data-stu-id="6e46c-245">We recommend that you always explicitly specify either WITH NORECOVERY or WITH RECOVERY in every RESTORE statement to eliminate ambiguity.</span></span> <span data-ttu-id="6e46c-246">Isso é particularmente importante ao escrever scripts.</span><span class="sxs-lookup"><span data-stu-id="6e46c-246">This is particularly important when writing scripts.</span></span>  
  
#### <a name="to-restore-a-transaction-log-backup"></a><span data-ttu-id="6e46c-247">Para restaurar um backup de log de transações</span><span class="sxs-lookup"><span data-stu-id="6e46c-247">To restore a transaction log backup</span></span>  
  
1.  <span data-ttu-id="6e46c-248">Execute a instrução RESTORE para aplicar o backup de log de transações, especificando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6e46c-248">Execute the RESTORE LOG statement to apply the transaction log backup, specifying:</span></span>  
  
    -   <span data-ttu-id="6e46c-249">O nome do banco de dados ao qual o log de transações será aplicado.</span><span class="sxs-lookup"><span data-stu-id="6e46c-249">The name of the database to which the transaction log will be applied.</span></span>  
  
    -   <span data-ttu-id="6e46c-250">O dispositivo de backup a partir de onde o backup de log de transações será restaurado.</span><span class="sxs-lookup"><span data-stu-id="6e46c-250">The backup device where the transaction log backup will be restored from.</span></span>  
  
    -   <span data-ttu-id="6e46c-251">A cláusula NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="6e46c-251">The NORECOVERY clause.</span></span>  
  
     <span data-ttu-id="6e46c-252">A sintaxe básica desta instrução é:</span><span class="sxs-lookup"><span data-stu-id="6e46c-252">The basic syntax for this statement is as follows:</span></span>  
  
     <span data-ttu-id="6e46c-253">RESTORE LOG *database_name* FROM <backup_device> WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="6e46c-253">RESTORE LOG *database_name* FROM <backup_device> WITH NORECOVERY.</span></span>  
  
     <span data-ttu-id="6e46c-254">Em que *database_name* é o nome do banco de dados e <backup_device> é o nome do dispositivo que contém o backup de log que está sendo restaurado.</span><span class="sxs-lookup"><span data-stu-id="6e46c-254">Where *database_name* is the name of database and <backup_device>is the name of the device that contains the log backup being restored.</span></span>  
  
2.  <span data-ttu-id="6e46c-255">Repita a etapa 1 para cada backup de log de transações você tiver que aplicar.</span><span class="sxs-lookup"><span data-stu-id="6e46c-255">Repeat step 1 for each transaction log backup you have to apply.</span></span>  
  
3.  <span data-ttu-id="6e46c-256">Depois de restaurar o último backup na sua sequência de restauração, para recuperar o uso de banco de dados use uma das seguintes instruções:</span><span class="sxs-lookup"><span data-stu-id="6e46c-256">After restoring the last backup in your restore sequence, to recover the database use one of the following statements:</span></span>  
  
    -   <span data-ttu-id="6e46c-257">Recuperar o banco de dados como parte da última instrução RESTORE LOG:</span><span class="sxs-lookup"><span data-stu-id="6e46c-257">Recover the database as part of the last RESTORE LOG statement:</span></span>  
  
        ```  
        RESTORE LOG <database_name> FROM <backup_device> WITH RECOVERY;  
        GO  
        ```  
  
    -   <span data-ttu-id="6e46c-258">Espere para recuperar o banco de dados usando uma instrução separada RESTORE DATABASE:</span><span class="sxs-lookup"><span data-stu-id="6e46c-258">Wait to recover the database by using a separate RESTORE DATABASE statement:</span></span>  
  
        ```  
        RESTORE LOG <database_name> FROM <backup_device> WITH NORECOVERY;   
        RESTORE DATABASE <database_name> WITH RECOVERY;  
        GO  
        ```  
  
         <span data-ttu-id="6e46c-259">Ao esperar para recuperar o banco de dados você tem a oportunidade de verificar se restaurou todos dos backups de log necessários.</span><span class="sxs-lookup"><span data-stu-id="6e46c-259">Waiting to recover the database gives you the opportunity to verify that you have restored all of the necessary log backups.</span></span> <span data-ttu-id="6e46c-260">Essa abordagem é aconselhável quando você estiver executando uma restauração point-in-time.</span><span class="sxs-lookup"><span data-stu-id="6e46c-260">This approach is often advisable when you are performing a point-in-time restore.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="6e46c-261">Se você estiver criando um banco de dados espelho, omita a etapa de recuperação.</span><span class="sxs-lookup"><span data-stu-id="6e46c-261">If you are creating a mirror database, omit the recovery step.</span></span> <span data-ttu-id="6e46c-262">Um banco de dados espelho deve permanecer no estado RESTORING.</span><span class="sxs-lookup"><span data-stu-id="6e46c-262">A mirror database must remain in the RESTORING state.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="6e46c-263">Exemplos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6e46c-263">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="6e46c-264">Por padrão, o banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] usa o modelo de recuperação simples.</span><span class="sxs-lookup"><span data-stu-id="6e46c-264">By default, the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database uses the simple recovery model.</span></span> <span data-ttu-id="6e46c-265">Os exemplos seguintes requerem a modificação do banco de dados para usar o modelo de recuperação completa, como segue:</span><span class="sxs-lookup"><span data-stu-id="6e46c-265">The following examples require modifying the database to use the full recovery model, as follows:</span></span>  
  
```sql  
ALTER DATABASE AdventureWorks2012 SET RECOVERY FULL;  
```  
  
#### <a name="a-applying-a-single-transaction-log-backup"></a><span data-ttu-id="6e46c-266">a.</span><span class="sxs-lookup"><span data-stu-id="6e46c-266">A.</span></span> <span data-ttu-id="6e46c-267">Aplicando um único backup de log de transações</span><span class="sxs-lookup"><span data-stu-id="6e46c-267">Applying a single transaction log backup</span></span>  
 <span data-ttu-id="6e46c-268">O exemplo seguinte inicia restaurando o banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] usando um backup de banco de dados completo que reside em um dispositivo de backup chamado `AdventureWorks2012_1`.</span><span class="sxs-lookup"><span data-stu-id="6e46c-268">The following example starts by restoring the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database by using a full database backup that resides on a backup device named `AdventureWorks2012_1`.</span></span> <span data-ttu-id="6e46c-269">O exemplo aplica então o primeiro backup de log de transações que reside em um dispositivo de backup chamado `AdventureWorks2012_log`.</span><span class="sxs-lookup"><span data-stu-id="6e46c-269">The example then applies the first transaction log backup that resides on a backup device named `AdventureWorks2012_log`.</span></span> <span data-ttu-id="6e46c-270">Por fim, o exemplo recupera o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6e46c-270">Finally, the example recovers the database.</span></span>  
  
```sql  
RESTORE DATABASE AdventureWorks2012  
   FROM AdventureWorks2012_1  
   WITH NORECOVERY;  
GO  
RESTORE LOG AdventureWorks2012  
   FROM AdventureWorks2012_log  
   WITH FILE = 1,  
   WITH NORECOVERY;  
GO  
RESTORE DATABASE AdventureWorks2012  
   WITH RECOVERY;  
GO  
```  
  
#### <a name="b-applying-multiple-transaction-log-backups"></a><span data-ttu-id="6e46c-271">B.</span><span class="sxs-lookup"><span data-stu-id="6e46c-271">B.</span></span> <span data-ttu-id="6e46c-272">Aplicando múltiplos backups de log de transações</span><span class="sxs-lookup"><span data-stu-id="6e46c-272">Applying multiple transaction log backups</span></span>  
 <span data-ttu-id="6e46c-273">O exemplo seguinte inicia restaurando o banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] usando um backup de banco de dados completo que reside em um dispositivo de backup chamado `AdventureWorks2012_1`.</span><span class="sxs-lookup"><span data-stu-id="6e46c-273">The following example starts by restoring the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database by using a full database backup that resides on a backup device named `AdventureWorks2012_1`.</span></span> <span data-ttu-id="6e46c-274">O exemplo aplica então, um por um, os três primeiros backups de log de transações que residem em um dispositivo de backup chamado `AdventureWorks2012_log`.</span><span class="sxs-lookup"><span data-stu-id="6e46c-274">The example then applies, one by one, the first three transaction log backups that reside on a backup device named `AdventureWorks2012_log`.</span></span> <span data-ttu-id="6e46c-275">Por fim, o exemplo recupera o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6e46c-275">Finally, the example recovers the database.</span></span>  
  
```sql  
RESTORE DATABASE AdventureWorks2012  
   FROM AdventureWorks2012_1  
   WITH NORECOVERY;  
GO  
RESTORE LOG AdventureWorks2012  
   FROM AdventureWorks2012_log  
   WITH FILE = 1,  
   NORECOVERY;  
GO  
RESTORE LOG AdventureWorks2012  
   FROM AdventureWorks2012_log  
   WITH FILE = 2,  
   WITH NORECOVERY;  
GO  
RESTORE LOG AdventureWorks2012  
   FROM AdventureWorks2012_log  
   WITH FILE = 3,  
   WITH NORECOVERY;  
GO  
RESTORE DATABASE AdventureWorks2012  
   WITH RECOVERY;  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="6e46c-276">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="6e46c-276">Related Tasks</span></span>  
  
-   [<span data-ttu-id="6e46c-277">Fazer backup de um log de transações &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6e46c-277">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
-   [<span data-ttu-id="6e46c-278">Restaurar um backup de banco de dados &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6e46c-278">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="6e46c-279">Restaurar um banco de dados até o ponto de falha no modelo de recuperação completa &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6e46c-279">Restore a Database to the Point of Failure Under the Full Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-database-to-point-of-failure-full-recovery.md)  
  
-   [<span data-ttu-id="6e46c-280">Restaurar um banco de dados do SQL Server em um ponto específico &#40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="6e46c-280">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
-   [<span data-ttu-id="6e46c-281">Restaurar um banco de dados para uma transação marcada &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6e46c-281">Restore a Database to a Marked Transaction &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-to-a-marked-transaction-sql-server-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="6e46c-282">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6e46c-282">See Also</span></span>  
 <span data-ttu-id="6e46c-283">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6e46c-283">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="6e46c-284">Aplicar backups de log de transações &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6e46c-284">Apply Transaction Log Backups &#40;SQL Server&#41;</span></span>](apply-transaction-log-backups-sql-server.md)  
  
  
