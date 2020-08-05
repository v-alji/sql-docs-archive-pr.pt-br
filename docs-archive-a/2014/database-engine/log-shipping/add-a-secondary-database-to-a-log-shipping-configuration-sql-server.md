---
title: Adicionar um banco de dados secundário a uma configuração de envio de logs (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- adding secondary databases
- secondary databases [SQL Server], in log shipping
- secondary data files [SQL Server], adding
- log shipping [SQL Server], secondary databases
ms.assetid: b02eba13-f8e6-4684-b7e4-75ea038ea473
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 062df1b53ed74321ba0c75c9df763de79a4802bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574252"
---
# <a name="add-a-secondary-database-to-a-log-shipping-configuration-sql-server"></a><span data-ttu-id="ec374-102">Adicionar um banco de dados secundário a uma configuração de envio de logs (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ec374-102">Add a Secondary Database to a Log Shipping Configuration (SQL Server)</span></span>
  <span data-ttu-id="ec374-103">Este tópico descreve como adicionar um banco de dados secundário a uma configuração de envio de logs existente no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ec374-103">This topic describes how to add a secondary database to an existing log shipping configuration in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="ec374-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="ec374-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ec374-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="ec374-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ec374-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="ec374-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ec374-107">**Para adicionar um banco de dados secundário de envio de logs, usando:**</span><span class="sxs-lookup"><span data-stu-id="ec374-107">**To add a log shipping secondary database, using:**</span></span>  
  
     [<span data-ttu-id="ec374-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ec374-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ec374-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ec374-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="ec374-110">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="ec374-110">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ec374-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="ec374-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ec374-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="ec374-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ec374-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="ec374-113">Permissions</span></span>  
 <span data-ttu-id="ec374-114">Os procedimentos armazenados de envio de logs exigem a associação à função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="ec374-114">The log-shipping stored procedures require membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ec374-115">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ec374-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-add-a-log-shipping-secondary-database"></a><span data-ttu-id="ec374-116">Para adicionar um banco de dados secundário de envio de logs</span><span class="sxs-lookup"><span data-stu-id="ec374-116">To add a log shipping secondary database</span></span>  
  
1.  <span data-ttu-id="ec374-117">Clique com o botão direito do mouse no banco de dados que deve ser usado como banco de dados primário na configuração de envio de logs e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="ec374-117">Right-click the database you want to use as your primary database in the log shipping configuration, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="ec374-118">Em **Selecionar uma página**, clique em **Envio do Log de Transações**.</span><span class="sxs-lookup"><span data-stu-id="ec374-118">Under **Select a page**, click **Transaction Log Shipping**.</span></span>  
  
3.  <span data-ttu-id="ec374-119">Em **Instâncias e bancos de dados do servidor secundário**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="ec374-119">Under **Secondary server instances and databases**, click **Add**.</span></span>  
  
4.  <span data-ttu-id="ec374-120">Clique em **Conectar** e conecte-se à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que deseja usar como servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="ec374-120">Click **Connect** and connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to use as your secondary server.</span></span>  
  
5.  <span data-ttu-id="ec374-121">Na caixa **Banco de dados secundário** , escolha um banco de dados da lista ou digite o nome do banco de dados que você quer criar.</span><span class="sxs-lookup"><span data-stu-id="ec374-121">In the **Secondary database** box, choose a database from the list or type the name of the database you want to create.</span></span>  
  
6.  <span data-ttu-id="ec374-122">Na guia **Inicializar banco de dados secundário** , escolha a opção que deseja usar para inicializar o banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="ec374-122">On the **Initialize Secondary database** tab, choose the option that you want to use to initialize the secondary database.</span></span>  
  
7.  <span data-ttu-id="ec374-123">Na **Guia Copiar Arquivos**, na caixa **Pasta de destino para arquivos copiados** , digite o caminho da pasta para a qual os backups de log de transações devem ser copiados.</span><span class="sxs-lookup"><span data-stu-id="ec374-123">On the **Copy Files tab**, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="ec374-124">Essa pasta fica, frequentemente, alocada no servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="ec374-124">This folder is often located on the secondary server.</span></span>  
  
8.  <span data-ttu-id="ec374-125">Observe a agenda de cópias listada na caixa **Agenda** em **Copiar trabalho**.</span><span class="sxs-lookup"><span data-stu-id="ec374-125">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="ec374-126">Caso queira personalizar a agenda para sua instalação, clique em **Agenda** e, em seguida, ajuste a Agenda do agente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="ec374-126">If you want to customize the schedule for your installation, click **Schedule** and then adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span> <span data-ttu-id="ec374-127">Essa agenda deve aproximar-se da agenda de backup.</span><span class="sxs-lookup"><span data-stu-id="ec374-127">This schedule should approximate the backup schedule.</span></span>  
  
9. <span data-ttu-id="ec374-128">Na guia **Restaurar** em **Estado de banco de dados ao restaurar backups**, escolha a opção **Nenhum modo de recuperação** ou **Modo de espera** .</span><span class="sxs-lookup"><span data-stu-id="ec374-128">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** or **Standby mode** option.</span></span>  
  
10. <span data-ttu-id="ec374-129">Caso tenha escolhido a opção **Modo de espera** , escolha se deseja desconectar os usuários do banco de dados secundário enquanto a operação de restauração está em andamento.</span><span class="sxs-lookup"><span data-stu-id="ec374-129">If you chose the **Standby mode** option, choose if you want to disconnect users from the secondary database while the restore operation is underway.</span></span>  
  
11. <span data-ttu-id="ec374-130">Caso queira adiar o processo de restauração no servidor secundário, escolha um tempo de atraso em **Atrasar restauração de backups pelo menos**.</span><span class="sxs-lookup"><span data-stu-id="ec374-130">If you want to delay the restore process on the secondary server, choose a delay time under **Delay restoring backups at least**.</span></span>  
  
12. <span data-ttu-id="ec374-131">Escolha um limite de alerta em **Alertar se nenhuma restauração ocorrer em**.</span><span class="sxs-lookup"><span data-stu-id="ec374-131">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>  
  
13. <span data-ttu-id="ec374-132">Observe a agenda de restauração listada na caixa **Agenda** em **Restaurar trabalho**.</span><span class="sxs-lookup"><span data-stu-id="ec374-132">Note the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="ec374-133">Caso queira personalizar a agenda para sua instalação, clique em **Agenda** e, em seguida, ajuste a Agenda do agente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="ec374-133">If you want to customize the schedule for your installation, click **Schedule** and then adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span> <span data-ttu-id="ec374-134">Essa agenda deve aproximar-se da agenda de backup.</span><span class="sxs-lookup"><span data-stu-id="ec374-134">This schedule should approximate the backup schedule.</span></span>  
  
14. <span data-ttu-id="ec374-135">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec374-135">Click **OK**.</span></span>  
  
15. <span data-ttu-id="ec374-136">Clique em **OK** na caixa de diálogo Propriedades do Banco de Dados para iniciar o processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="ec374-136">Click **OK** on the Database Properties dialog box to begin the configuration process.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ec374-137">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ec374-137">Using Transact-SQL</span></span>  
  
#### <a name="to-add-a-log-shipping-secondary-database"></a><span data-ttu-id="ec374-138">Para adicionar um banco de dados secundário de envio de logs</span><span class="sxs-lookup"><span data-stu-id="ec374-138">To add a log shipping secondary database</span></span>  
  
1.  <span data-ttu-id="ec374-139">No servidor secundário, execute [sp_add_log_shipping_secondary_primary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-primary-transact-sql) fornecendo os detalhes do servidor primário e banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ec374-139">On the secondary server, execute [sp_add_log_shipping_secondary_primary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-primary-transact-sql) supplying the details of the primary server and database.</span></span> <span data-ttu-id="ec374-140">Esse procedimento armazenado retorna a ID secundária e as ID de tarefa de cópia e restauração.</span><span class="sxs-lookup"><span data-stu-id="ec374-140">This stored procedure returns the secondary ID and the copy and restore job IDs.</span></span>  
  
2.  <span data-ttu-id="ec374-141">No servidor secundário, execute [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) para definir o agendamento das tarefas de cópia e restauração.</span><span class="sxs-lookup"><span data-stu-id="ec374-141">On the secondary server, execute [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) to set the schedule for the copy and restore jobs.</span></span>  
  
3.  <span data-ttu-id="ec374-142">No servidor secundário, execute [sp_add_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-database-transact-sql) para adicionar o banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="ec374-142">On the secondary server, execute [sp_add_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-database-transact-sql) to add a secondary database.</span></span>  
  
4.  <span data-ttu-id="ec374-143">No servidor primário, execute [sp_add_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-secondary-transact-sql) para adicionar as informações necessárias sobre o novo banco de dados secundário ao servidor primário.</span><span class="sxs-lookup"><span data-stu-id="ec374-143">On the primary server, execute [sp_add_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-secondary-transact-sql) to add the required information about the new secondary database to the primary server.</span></span>  
  
5.  <span data-ttu-id="ec374-144">No servidor secundário, habilite as tarefas de cópia e restauração.</span><span class="sxs-lookup"><span data-stu-id="ec374-144">On the secondary server, enable the copy and restore jobs.</span></span> <span data-ttu-id="ec374-145">Para obter mais informações, consulte [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="ec374-145">For more information, see [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="ec374-146">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="ec374-146">Related Tasks</span></span>  
  
-   [<span data-ttu-id="ec374-147">Atualizar o envio de logs para SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec374-147">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="ec374-148">Configurar o envio de logs &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ec374-148">Configure Log Shipping &#40;SQL Server&#41;</span></span>](configure-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="ec374-149">Remover um banco de dados secundário de uma configuração de envio de logs &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ec374-149">Remove a Secondary Database from a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="ec374-150">Remover envio de log &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ec374-150">Remove Log Shipping &#40;SQL Server&#41;</span></span>](remove-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="ec374-151">Exibir o relatório de envio de logs &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="ec374-151">View the Log Shipping Report &#40;SQL Server Management Studio&#41;</span></span>](view-the-log-shipping-report-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="ec374-152">Monitorar o envio de logs &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec374-152">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="ec374-153">Executar failover para um secundário de envio de logs &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ec374-153">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="ec374-154">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ec374-154">See Also</span></span>  
 <span data-ttu-id="ec374-155">[Sobre o envio de logs &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ec374-155">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="ec374-156">Tabelas de envio de log e procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="ec374-156">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
