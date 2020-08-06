---
title: Configurar o envio de logs (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], enabling
- log shipping [SQL Server], configuring
ms.assetid: c42aa04a-4945-4417-b4c7-50589d727e9c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 269b0ae2980435e507128cc87606f7eb702c2b7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679489"
---
# <a name="configure-log-shipping-sql-server"></a><span data-ttu-id="487bb-102">Configurar o envio de logs (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="487bb-102">Configure Log Shipping (SQL Server)</span></span>
  <span data-ttu-id="487bb-103">Este tópico descreve como configurar o envio de logs no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="487bb-103">This topic describes how to configure log shipping in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="487bb-104">O [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] e versões posteriores dão suporte à compactação de backup.</span><span class="sxs-lookup"><span data-stu-id="487bb-104">[!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] and later versions support backup compression.</span></span> <span data-ttu-id="487bb-105">Ao criar uma configuração de envio de logs, é possível controlar o comportamento de compactação de backup dos backups de log.</span><span class="sxs-lookup"><span data-stu-id="487bb-105">When creating a log shipping configuration, you can control the backup compression behavior of log backups.</span></span> <span data-ttu-id="487bb-106">Para obter mais informações, veja [Compactação de backup &#40;SQL Server&#41;](../../relational-databases/backup-restore/backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="487bb-106">For more information, see [Backup Compression &#40;SQL Server&#41;](../../relational-databases/backup-restore/backup-compression-sql-server.md).</span></span>  
  
 <span data-ttu-id="487bb-107">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="487bb-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="487bb-108">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="487bb-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="487bb-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="487bb-109">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="487bb-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="487bb-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="487bb-111">**Para configurar o envio de logs, usando:**</span><span class="sxs-lookup"><span data-stu-id="487bb-111">**To configure log shipping, using:**</span></span>  
  
     [<span data-ttu-id="487bb-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="487bb-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="487bb-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="487bb-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="487bb-114">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="487bb-114">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="487bb-115">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="487bb-115">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="487bb-116">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="487bb-116">Prerequisites</span></span>  
  
-   <span data-ttu-id="487bb-117">O banco de dados primário deve usar o modelo de recuperação completa ou bulk-logged; se o banco de dados for alterado para o modelo de recuperação simples, o envio de logs deixará de funcionar.</span><span class="sxs-lookup"><span data-stu-id="487bb-117">The primary database must use the full or bulk-logged recovery model; switching the database to simple recovery will cause log shipping to stop functioning.</span></span>  
  
-   <span data-ttu-id="487bb-118">Antes de configurar o envio de logs, é necessário criar um compartilhamento para disponibilizar os backups de log de transações no servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="487bb-118">Before you configure log shipping, you must create a share to make the transaction log backups available to the secondary server.</span></span> <span data-ttu-id="487bb-119">Esse é um compartilhamento do diretório onde os backups de log de transação serão gerados.</span><span class="sxs-lookup"><span data-stu-id="487bb-119">This is a share of the directory where the transaction log backups will be generated.</span></span> <span data-ttu-id="487bb-120">Por exemplo, se você fez backup dos logs de transação no diretório c:\data\tlogs\\, será possível criar o compartilhamento \\\\*primaryserver*\tlogs desse diretório.</span><span class="sxs-lookup"><span data-stu-id="487bb-120">For example, if you back up your transaction logs to the directory c:\data\tlogs\\, you could create the \\\\*primaryserver*\tlogs share of that directory.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="487bb-121">Segurança</span><span class="sxs-lookup"><span data-stu-id="487bb-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="487bb-122">Permissões</span><span class="sxs-lookup"><span data-stu-id="487bb-122">Permissions</span></span>  
 <span data-ttu-id="487bb-123">Os procedimentos armazenados de envio de logs exigem a associação à função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="487bb-123">The log-shipping stored procedures require membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="487bb-124">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="487bb-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-log-shipping"></a><span data-ttu-id="487bb-125">Para configurar o envio de logs</span><span class="sxs-lookup"><span data-stu-id="487bb-125">To configure log shipping</span></span>  
  
1.  <span data-ttu-id="487bb-126">Clique com o botão direito do mouse no banco de dados que deve ser usado como banco de dados primário na configuração de envio de logs e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="487bb-126">Right click the database you want to use as your primary database in the log shipping configuration, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="487bb-127">Em **Selecionar uma página**, clique em **Envio do Log de Transações**.</span><span class="sxs-lookup"><span data-stu-id="487bb-127">Under **Select a page**, click **Transaction Log Shipping**.</span></span>  
  
3.  <span data-ttu-id="487bb-128">Selecione a caixa de seleção **Habilitar como banco de dados primário em uma configuração de envio de logs** .</span><span class="sxs-lookup"><span data-stu-id="487bb-128">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>  
  
4.  <span data-ttu-id="487bb-129">Em **Backup de log de transações**, clique em **Configurações de backup**.</span><span class="sxs-lookup"><span data-stu-id="487bb-129">Under **Transaction log backups**, click **Backup Settings**.</span></span>  
  
5.  <span data-ttu-id="487bb-130">Na caixa **Caminho de rede para a pasta de backup** , digite o caminho de rede para o compartilhamento criado para a pasta de backup de log de transações.</span><span class="sxs-lookup"><span data-stu-id="487bb-130">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>  
  
6.  <span data-ttu-id="487bb-131">Se a pasta de backup estiver localizada no servidor primário, digite o caminho local para a pasta de backup na caixa **Se a pasta de backup estiver localizada no servidor primário, digite um caminho local para a pasta** .</span><span class="sxs-lookup"><span data-stu-id="487bb-131">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box.</span></span> <span data-ttu-id="487bb-132">(Se a pasta de backup não estiver localizada no servidor primário, deixe essa caixa em branco.)</span><span class="sxs-lookup"><span data-stu-id="487bb-132">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="487bb-133">Se a conta de serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no servidor primário estiver sendo executada na conta Sistema Local, será necessário criar a pasta de backup no servidor primário e especificar um caminho local para a pasta.</span><span class="sxs-lookup"><span data-stu-id="487bb-133">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>  
  
7.  <span data-ttu-id="487bb-134">Configure os parâmetros **Excluir arquivos com mais de** e **Alertar se nenhum backup ocorrer em** .</span><span class="sxs-lookup"><span data-stu-id="487bb-134">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>  
  
8.  <span data-ttu-id="487bb-135">Observe a agenda de backup listada na caixa **Agenda** em **Trabalho de backup**.</span><span class="sxs-lookup"><span data-stu-id="487bb-135">Note the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="487bb-136">Se quiser personalizar a agenda para sua instalação, clique em **Agenda** e, em seguida, ajuste a Agenda do agente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="487bb-136">If you want to customize the schedule for your installation, then click **Schedule** and adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span>  
  
9. [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="487bb-137">dá suporte à [compactação de backup](../../relational-databases/backup-restore/backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="487bb-137">supports [backup compression](../../relational-databases/backup-restore/backup-compression-sql-server.md).</span></span> <span data-ttu-id="487bb-138">Ao criar uma configuração de envio de logs, é possível controlar o comportamento de compactação de backup dos backups de log escolhendo uma das opções a seguir: **Usar a configuração de servidor padrão**, **Compactar backup** ou **Não compactar o backup**.</span><span class="sxs-lookup"><span data-stu-id="487bb-138">When creating a log shipping configuration, you can control the backup compression behavior of log backups by choosing one of the following options: **Use the default server setting**, **Compress backup**, or **Do not compress backup**.</span></span> <span data-ttu-id="487bb-139">Para obter mais informações, consulte [Log Shipping Transaction Log Backup Settings](../../relational-databases/databases/log-shipping-transaction-log-backup-settings.md).</span><span class="sxs-lookup"><span data-stu-id="487bb-139">For more information, see [Log Shipping Transaction Log Backup Settings](../../relational-databases/databases/log-shipping-transaction-log-backup-settings.md).</span></span>  
  
10. <span data-ttu-id="487bb-140">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="487bb-140">Click **OK**.</span></span>  
  
11. <span data-ttu-id="487bb-141">Em **Instâncias e bancos de dados do servidor secundário**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="487bb-141">Under **Secondary server instances and databases**, click **Add**.</span></span>  
  
12. <span data-ttu-id="487bb-142">Clique em **Conectar** e conecte-se à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que deseja usar como servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="487bb-142">Click **Connect** and connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to use as your secondary server.</span></span>  
  
13. <span data-ttu-id="487bb-143">Na caixa **Banco de Dados Secundário** , escolha um banco de dados da lista ou digite o nome do banco de dados que deve ser criado.</span><span class="sxs-lookup"><span data-stu-id="487bb-143">In the **Secondary Database** box, choose a database from the list or type the name of the database you want to create.</span></span>  
  
14. <span data-ttu-id="487bb-144">Na guia **Inicializar banco de dados secundário** , escolha a opção que deseja usar para inicializar o banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="487bb-144">On the **Initialize Secondary database** tab, choose the option that you want to use to initialize the secondary database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="487bb-145">Se você optar para que o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] inicialize o banco de dados secundário por meio de um backup de banco de dados, os arquivos de dados e de log do banco de dados secundário serão colocados no mesmo local que os arquivos de dados e de log do banco de dados **mestre** .</span><span class="sxs-lookup"><span data-stu-id="487bb-145">If you choose to have [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] initialize the secondary database from a database backup, the data and log files of the secondary database are placed in the same location as the data and log files of the **master** database.</span></span> <span data-ttu-id="487bb-146">É provável que esse local seja diferente do local dos arquivos de dados e de log do banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="487bb-146">This location is likely to be different than the location of the data and log files of the primary database.</span></span>  
  
15. <span data-ttu-id="487bb-147">Na guia **Copiar Arquivos** , na caixa **Pasta de destino dos arquivos copiados** , digite o caminho da pasta onde os backups de log de transações devem ser copiados.</span><span class="sxs-lookup"><span data-stu-id="487bb-147">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="487bb-148">Essa pasta fica, frequentemente, alocada no servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="487bb-148">This folder is often located on the secondary server.</span></span>  
  
16. <span data-ttu-id="487bb-149">Observe a agenda de cópias listada na caixa **Agenda** em **Copiar trabalho**.</span><span class="sxs-lookup"><span data-stu-id="487bb-149">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="487bb-150">Caso queira personalizar a agenda para sua instalação, clique em **Agenda** e, em seguida, ajuste a Agenda do agente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="487bb-150">If you want to customize the schedule for your installation, click **Schedule** and then adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span> <span data-ttu-id="487bb-151">Essa agenda deve aproximar-se da agenda de backup.</span><span class="sxs-lookup"><span data-stu-id="487bb-151">This schedule should approximate the backup schedule.</span></span>  
  
17. <span data-ttu-id="487bb-152">Na guia **Restaurar** em **Estado de banco de dados ao restaurar backups**, escolha a opção **Nenhum modo de recuperação** ou **Modo de espera** .</span><span class="sxs-lookup"><span data-stu-id="487bb-152">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** or **Standby mode** option.</span></span>  
  
18. <span data-ttu-id="487bb-153">Caso tenha escolhido a opção **Modo de espera** , escolha se deseja desconectar os usuários do banco de dados secundário enquanto a operação de restauração está em andamento.</span><span class="sxs-lookup"><span data-stu-id="487bb-153">If you chose the **Standby mode** option, choose if you want to disconnect users from the secondary database while the restore operation is underway.</span></span>  
  
19. <span data-ttu-id="487bb-154">Caso queira adiar o processo de restauração no servidor secundário, escolha um tempo de atraso em **Atrasar restauração de backups pelo menos**.</span><span class="sxs-lookup"><span data-stu-id="487bb-154">If you want to delay the restore process on the secondary server, choose a delay time under **Delay restoring backups at least**.</span></span>  
  
20. <span data-ttu-id="487bb-155">Escolha um limite de alerta em **Alertar se nenhuma restauração ocorrer em**.</span><span class="sxs-lookup"><span data-stu-id="487bb-155">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>  
  
21. <span data-ttu-id="487bb-156">Observe a agenda de restauração listada na caixa **Agenda** em **Restaurar trabalho**.</span><span class="sxs-lookup"><span data-stu-id="487bb-156">Note the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="487bb-157">Caso queira personalizar a agenda para sua instalação, clique em **Agenda** e, em seguida, ajuste a Agenda do agente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="487bb-157">If you want to customize the schedule for your installation, click **Schedule** and then adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span> <span data-ttu-id="487bb-158">Essa agenda deve aproximar-se da agenda de backup.</span><span class="sxs-lookup"><span data-stu-id="487bb-158">This schedule should approximate the backup schedule.</span></span>  
  
22. <span data-ttu-id="487bb-159">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="487bb-159">Click **OK**.</span></span>  
  
23. <span data-ttu-id="487bb-160">Em **Instância do servidor monitor**, selecione a caixa de seleção **Usar uma instância de servidor monitor** e, em seguida, clique em **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="487bb-160">Under **Monitor server instance**, select the **Use a monitor server instance** check box, and then click **Settings**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="487bb-161">Para monitorar essa configuração de envio de logs é necessário adicionar o servidor monitor neste momento.</span><span class="sxs-lookup"><span data-stu-id="487bb-161">To monitor this log shipping configuration, you must add the monitor server now.</span></span> <span data-ttu-id="487bb-162">Para adicionar o servidor monitor posteriormente, é necessário remover essa configuração de envio de logs e, em seguida, substituí-la pela configuração nova que inclui um servidor monitor.</span><span class="sxs-lookup"><span data-stu-id="487bb-162">To add the monitor server later, you would need to remove this log shipping configuration and then replace it with a new configuration that includes a monitor server.</span></span>  
  
24. <span data-ttu-id="487bb-163">Clique em **Conectar** e conecte-se à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que deseja usar como servidor monitor.</span><span class="sxs-lookup"><span data-stu-id="487bb-163">Click **Connect** and connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to use as your monitor server.</span></span>  
  
25. <span data-ttu-id="487bb-164">Em **Conexões de monitor**, escolha o método de conexão para ser usado pelo backup, copie e restaure os trabalhos para fazer a conexão com o servidor monitor.</span><span class="sxs-lookup"><span data-stu-id="487bb-164">Under **Monitor connections**, choose the connection method to be used by the backup, copy, and restore jobs to connect to the monitor server.</span></span>  
  
26. <span data-ttu-id="487bb-165">Em **Retenção de histórico**, escolha o período de tempo em que o registro deve ser retido no histórico de envio de logs.</span><span class="sxs-lookup"><span data-stu-id="487bb-165">Under **History retention**, choose the length of time you want to retain a record of your log shipping history.</span></span>  
  
27. <span data-ttu-id="487bb-166">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="487bb-166">Click **OK**.</span></span>  
  
28. <span data-ttu-id="487bb-167">Na caixa de diálogo **Propriedades do Banco de Dados** , clique em **OK** para iniciar o processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="487bb-167">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="487bb-168">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="487bb-168">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-log-shipping"></a><span data-ttu-id="487bb-169">Para configurar o envio de logs</span><span class="sxs-lookup"><span data-stu-id="487bb-169">To configure log shipping</span></span>  
  
1.  <span data-ttu-id="487bb-170">Inicialize o banco de dados secundário, restaurando um backup completo do banco de dados primário no servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="487bb-170">Initialize the secondary database by restoring a full backup of the primary database on the secondary server.</span></span>  
  
2.  <span data-ttu-id="487bb-171">No servidor primário, execute [sp_add_log_shipping_primary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-database-transact-sql) para adicionar um banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="487bb-171">On the primary server, execute [sp_add_log_shipping_primary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-database-transact-sql) to add a primary database.</span></span> <span data-ttu-id="487bb-172">O procedimento armazenado retorna o ID do trabalho de backup e o ID primário.</span><span class="sxs-lookup"><span data-stu-id="487bb-172">The stored procedure returns the backup job ID and primary ID.</span></span>  
  
3.  <span data-ttu-id="487bb-173">No servidor primário, execute [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) para adicionar um agendamento ao trabalho de backup.</span><span class="sxs-lookup"><span data-stu-id="487bb-173">On the primary server, execute [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) to add a schedule for the backup job.</span></span>  
  
4.  <span data-ttu-id="487bb-174">No servidor monitor, execute [sp_add_log_shipping_alert_job](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-alert-job-transact-sql) para adicionar o trabalho de alerta.</span><span class="sxs-lookup"><span data-stu-id="487bb-174">On the monitor server, execute [sp_add_log_shipping_alert_job](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-alert-job-transact-sql) to add the alert job.</span></span>  
  
5.  <span data-ttu-id="487bb-175">No servidor primário, habilite o trabalho de backup.</span><span class="sxs-lookup"><span data-stu-id="487bb-175">On the primary server, enable the backup job.</span></span>  
  
6.  <span data-ttu-id="487bb-176">No servidor secundário, execute [sp_add_log_shipping_secondary_primary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-primary-transact-sql) fornecendo os detalhes do servidor primário e banco de dados.</span><span class="sxs-lookup"><span data-stu-id="487bb-176">On the secondary server, execute [sp_add_log_shipping_secondary_primary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-primary-transact-sql) supplying the details of the primary server and database.</span></span> <span data-ttu-id="487bb-177">Esse procedimento armazenado retorna a ID secundária e as ID de tarefa de cópia e restauração.</span><span class="sxs-lookup"><span data-stu-id="487bb-177">This stored procedure returns the secondary ID and the copy and restore job IDs.</span></span>  
  
7.  <span data-ttu-id="487bb-178">No servidor secundário, execute [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) para definir o agendamento das tarefas de cópia e restauração.</span><span class="sxs-lookup"><span data-stu-id="487bb-178">On the secondary server, execute [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) to set the schedule for the copy and restore jobs.</span></span>  
  
8.  <span data-ttu-id="487bb-179">No servidor secundário, execute [sp_add_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-database-transact-sql) para adicionar o banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="487bb-179">On the secondary server, execute [sp_add_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-database-transact-sql) to add a secondary database.</span></span>  
  
9. <span data-ttu-id="487bb-180">No servidor primário, execute [sp_add_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-secondary-transact-sql) para adicionar as informações necessárias sobre o novo banco de dados secundário ao servidor primário.</span><span class="sxs-lookup"><span data-stu-id="487bb-180">On the primary server, execute [sp_add_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-secondary-transact-sql) to add the required information about the new secondary database to the primary server.</span></span>  
  
10. <span data-ttu-id="487bb-181">No servidor secundário, habilite as tarefas de cópia e restauração.</span><span class="sxs-lookup"><span data-stu-id="487bb-181">On the secondary server, enable the copy and restore jobs.</span></span> <span data-ttu-id="487bb-182">Para obter mais informações, consulte [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="487bb-182">For more information, see [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="487bb-183">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="487bb-183">Related Tasks</span></span>  
  
-   [<span data-ttu-id="487bb-184">Atualizar o envio de logs para SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="487bb-184">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="487bb-185">Adicionar um banco de dados secundário a uma configuração de envio de logs &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="487bb-185">Add a Secondary Database to a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](add-a-secondary-database-to-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="487bb-186">Remover um banco de dados secundário de uma configuração de envio de logs &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="487bb-186">Remove a Secondary Database from a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="487bb-187">Remover envio de log &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="487bb-187">Remove Log Shipping &#40;SQL Server&#41;</span></span>](remove-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="487bb-188">Exibir o relatório de envio de logs &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="487bb-188">View the Log Shipping Report &#40;SQL Server Management Studio&#41;</span></span>](view-the-log-shipping-report-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="487bb-189">Monitorar o envio de logs &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="487bb-189">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="487bb-190">Executar failover para um secundário de envio de logs &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="487bb-190">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="487bb-191">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="487bb-191">See Also</span></span>  
 <span data-ttu-id="487bb-192">[Sobre o envio de logs &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="487bb-192">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="487bb-193">Tabelas de envio de log e procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="487bb-193">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
