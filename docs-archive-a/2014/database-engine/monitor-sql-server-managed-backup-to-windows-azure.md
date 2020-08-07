---
title: Monitorar SQL Server Backup gerenciado no Azure | Microsoft Docs
description: Este artigo descreve as ferramentas que você pode usar para determinar a integridade geral dos backups usando SQL Server Backup gerenciado para o Azure e identificar erros.
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: cfb9e431-7d4c-457c-b090-6f2528b2f315
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: baec99e63c70befde0cfce76e42dd6202ebc0bad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582616"
---
# <a name="monitor-sql-server-managed-backup-to-azure"></a><span data-ttu-id="db42d-103">Monitorar o backup gerenciado do SQL Server para Azure</span><span class="sxs-lookup"><span data-stu-id="db42d-103">Monitor SQL Server Managed Backup to Azure</span></span>
  <span data-ttu-id="db42d-104">O [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] tem medidas internas para identificar problemas e erros durante processos de backup e adotar uma ação corretiva quando possível.</span><span class="sxs-lookup"><span data-stu-id="db42d-104">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] has built-in measures to identify problems and errors during backup processes and remedy with corrective action when possible.</span></span>  <span data-ttu-id="db42d-105">No entanto, há determinadas situações onde a intervenção do usuário é necessária.</span><span class="sxs-lookup"><span data-stu-id="db42d-105">However there are certain situations where user intervention is required.</span></span> <span data-ttu-id="db42d-106">Este tópico descreve as ferramentas que você pode usar para determinar o estado de integridade geral dos backups e identifica todos os erros que precisam ser resolvidos.</span><span class="sxs-lookup"><span data-stu-id="db42d-106">This topic describes the tools that you can use to determine the overall health status of backups, and identify any errors that need to be addressed.</span></span>  
  
## <a name="overview-of-ss_smartbackup-built-in-debugging"></a><span data-ttu-id="db42d-107">Visão geral de depuração interna do [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db42d-107">Overview of [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Built-in Debugging</span></span>  
 <span data-ttu-id="db42d-108">O [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] examina periodicamente backups agendados e tenta reagendar todos os backups com falha.</span><span class="sxs-lookup"><span data-stu-id="db42d-108">The [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] periodically reviews scheduled backups and attempts to reschedule any failed backups.</span></span> <span data-ttu-id="db42d-109">Ele pesquisa a conta de armazenamento periodicamente para identificar interrupções nas cadeias de logs que afetam a capacidade de recuperação do banco de dados e agenda backups novos apropriadamente.</span><span class="sxs-lookup"><span data-stu-id="db42d-109">It polls the storage account periodically to identify breaks in log chains affecting recoverability of the database, and schedules new backups accordingly.</span></span> <span data-ttu-id="db42d-110">Ele também leva em conta as políticas de limitação do Azure e tem mecanismos em vigor para gerenciar vários backups de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="db42d-110">It also takes into account Azure throttling policies, and has mechanisms in place to manage multiple database backups.</span></span> <span data-ttu-id="db42d-111">O [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] usa eventos estendidos para rastrear toda a atividade.</span><span class="sxs-lookup"><span data-stu-id="db42d-111">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] uses extended events to track all activity.</span></span> <span data-ttu-id="db42d-112">Os canais de Evento Estendido usados pelo agente [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] incluem Administração, Operacional, Analítico e Depuração.</span><span class="sxs-lookup"><span data-stu-id="db42d-112">The Extended Event channels used by [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] agent include, Admin, Operational, Analytical, and Debug.</span></span> <span data-ttu-id="db42d-113">Os eventos que entram na categoria Admin geralmente estão relacionados a erros, requerem intervenção do usuário e são habilitados por padrão.</span><span class="sxs-lookup"><span data-stu-id="db42d-113">Events that fall under the Admin category usually are related to errors and require user intervention and are enabled by default.</span></span> <span data-ttu-id="db42d-114">Os eventos analíticos são ativados também por padrão, mas geralmente não relacionados aos erros que requerem intervenção do usuário.</span><span class="sxs-lookup"><span data-stu-id="db42d-114">Analytical events are also turned on by default, but usually are not related to errors that require user intervention.</span></span> <span data-ttu-id="db42d-115">Os eventos operacionais normalmente são informativos.</span><span class="sxs-lookup"><span data-stu-id="db42d-115">Operation events are typically informational.</span></span> <span data-ttu-id="db42d-116">Por exemplo, os eventos operacionais incluem o agendamento de um backup, uma conclusão bem-sucedida do backup, etc. A depuração é a mais detalhada e é usada internamente pelo [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para determinar problemas e corrigi-los, se necessário.</span><span class="sxs-lookup"><span data-stu-id="db42d-116">For example, operational events include scheduling a backup, a successful completion of backup, etc. The Debug is the most verbose and is used internally by [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] to determine issues and correct them if required.</span></span>  
  
### <a name="configure-monitoring-parameters-for-ss_smartbackup"></a><span data-ttu-id="db42d-117">Configurar parâmetros de monitoramento para o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db42d-117">Configure Monitoring Parameters for [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]</span></span>  
 <span data-ttu-id="db42d-118">O procedimento armazenado do sistema **smart_admin. sp_set_parameter** permite que você especifique as configurações de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="db42d-118">The **smart_admin.sp_set_parameter** system stored procedure allows you to specify monitoring settings.</span></span> <span data-ttu-id="db42d-119">As seções a seguir mostram o processo de habilitar Eventos Estendidos e habilitar a notificação por email sobre erros e avisos.</span><span class="sxs-lookup"><span data-stu-id="db42d-119">The following sections walks through the process of enabling Extended Events,  and enabling email notification for errors and warnings.</span></span>  
  
 <span data-ttu-id="db42d-120">A função **smart_admin. fn_get_parameter** pode ser usada para obter a configuração atual de um parâmetro específico ou de todos os parâmetros configurados.</span><span class="sxs-lookup"><span data-stu-id="db42d-120">The **smart_admin.fn_get_parameter** function can be used to get the current setting for a specific parameter or all configured parameters.</span></span> <span data-ttu-id="db42d-121">Se os parâmetros nunca tiverem sido configurados, a função não retornará nenhum valor.</span><span class="sxs-lookup"><span data-stu-id="db42d-121">If the parameters have never been configured, the function does not return any values.</span></span>  
  
1.  <span data-ttu-id="db42d-122">Conecte-se ao [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db42d-122">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="db42d-123">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="db42d-123">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="db42d-124">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="db42d-124">Copy and paste the following example into the query window and then click **Execute**.</span></span> <span data-ttu-id="db42d-125">Isso retornará a configuração atual de Eventos Estendidos e notificações por email.</span><span class="sxs-lookup"><span data-stu-id="db42d-125">This will return the current configuration for Extended Events, and e-mail notifications.</span></span>  
  
```sql
Use msdb  
Go  
SELECT * FROM smart_admin.fn_get_parameter (NULL)  
GO  
```  
  
 <span data-ttu-id="db42d-126">Para obter mais informações, consulte [smart_admin. fn_get_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/managed-backup-fn-get-parameter-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="db42d-126">For more information, see [smart_admin.fn_get_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/managed-backup-fn-get-parameter-transact-sql)</span></span>  
  
### <a name="extended-events-for-monitoring"></a><span data-ttu-id="db42d-127">Eventos Estendidos para monitoramento</span><span class="sxs-lookup"><span data-stu-id="db42d-127">Extended Events for Monitoring</span></span>  
 <span data-ttu-id="db42d-128">Por padrão, os eventos Admin, Operacional e Analítico estão ativados.</span><span class="sxs-lookup"><span data-stu-id="db42d-128">By default, Admin, Operational and Analytical events are turned on.</span></span> <span data-ttu-id="db42d-129">Os eventos Admin são mais críticos, úteis para identificar erros que requerem intervenção manual para resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="db42d-129">Admin events are most critical, useful when identifying errors that require manual intervention to solve the problem.</span></span> <span data-ttu-id="db42d-130">Talvez seja necessário ativar os eventos operacional e de depuração, mas considere que esses eventos são detalhados e podem requerer filtragem.</span><span class="sxs-lookup"><span data-stu-id="db42d-130">You may want to turn on the operational and debug events but consider that these events are verbose and may require some filtering.</span></span> <span data-ttu-id="db42d-131">Os procedimentos a seguir descrevem como monitorar eventos registrados em log com Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="db42d-131">The following procedures describe how to monitor events logged through Extended Events.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="db42d-132">Diferente dos Eventos Estendidos do SQL engine, o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] não oferece suporte a conceitos de sessão de Evento Estendido.</span><span class="sxs-lookup"><span data-stu-id="db42d-132">Unlike Extended Events for SQL Engine, [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] does not support Extended Event session concepts.</span></span> <span data-ttu-id="db42d-133">As funções e os procedimentos armazenados do sistema são as ferramentas usadas para interagir com eventos estendidos.</span><span class="sxs-lookup"><span data-stu-id="db42d-133">System stored procedures and functions are the tools used to interact with extended events.</span></span> <span data-ttu-id="db42d-134">Você também pode exibir o log de eventos estendidos do diretório de log.</span><span class="sxs-lookup"><span data-stu-id="db42d-134">You can also view the extended event log from the log directory.</span></span>  
  
##### <a name="to-configure-and-view-extended-events"></a><span data-ttu-id="db42d-135">Para configurar e exibir Eventos Estendidos</span><span class="sxs-lookup"><span data-stu-id="db42d-135">To Configure and View Extended Events</span></span>  
  
1.  <span data-ttu-id="db42d-136">Para exibir os canais de Evento Estendido disponíveis e seu status atual executando a seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="db42d-136">To view available Extended Event channels and their current status by running the following query:</span></span>  
  
    ```sql
    SELECT * FROM smart_admin.fn_get_current_xevent_settings()  
    ```  
  
     <span data-ttu-id="db42d-137">A saída desta consulta exibirá o event_name, quer seja configurável ou não, e se estiver habilitado no momento.</span><span class="sxs-lookup"><span data-stu-id="db42d-137">The output from this query will display the event_name, whether it is configurable or not, and whether it is currently enabled.</span></span>  <span data-ttu-id="db42d-138">Para obter mais informações, consulte [smart_admin. fn_get_current_xevent_settings &#40;&#41;do Transact-SQL ](/sql/relational-databases/system-functions/managed-backup-fn-get-current-xevent-settings-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="db42d-138">For more information, see [smart_admin.fn_get_current_xevent_settings &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/managed-backup-fn-get-current-xevent-settings-transact-sql).</span></span>  
  
2.  <span data-ttu-id="db42d-139">Para habilitar eventos de depuração, execute a seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="db42d-139">To enable debug events, run the following query:</span></span>  
  
    ```sql
    --  to enable debug events  
    Use msdb;  
    GO 
    EXEC smart_admin.sp_set_parameter 'FileRetentionDebugXevent', 'True'  
    ```  
  
     <span data-ttu-id="db42d-140">Para obter mais informações sobre o procedimento armazenado, consulte [smart_admin. sp_set_parameter &#40;&#41;do Transact-SQL ](/sql/relational-databases/system-stored-procedures/managed-backup-sp-set-parameter-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="db42d-140">For more information about the stored procedure, see [smart_admin.sp_set_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/managed-backup-sp-set-parameter-transact-sql).</span></span>  
  
3.  <span data-ttu-id="db42d-141">Para exibir os eventos em log, execute esta consulta:</span><span class="sxs-lookup"><span data-stu-id="db42d-141">To view the logged events run the following query:</span></span>  
  
    ```sql
    --  View all events in the current week  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek;
    ```  
  
    ```sql
    --  view all admin events  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)   
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    DECLARE @eventresult TABLE  
    (event_type nvarchar(512),  
    event nvarchar (512),  
    timestamp datetime  
    )  
  
    INSERT INTO @eventresult  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek  
  
    SELECT * from @eventresult  
    WHERE event_type LIKE '%admin%'
    ```  
  
### <a name="aggregated-error-countshealth-status"></a><span data-ttu-id="db42d-142">Contagens de erros agregadas/Status de integridade</span><span class="sxs-lookup"><span data-stu-id="db42d-142">Aggregated Error Counts/Health Status</span></span>  
 <span data-ttu-id="db42d-143">A função **smart_admin. fn_get_health_status** retorna uma tabela de contagens de erros agregados para cada categoria que pode ser usada para monitorar o status de integridade de [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="db42d-143">The **smart_admin.fn_get_health_status** function returns a table of aggregated error counts for each category that can be used to monitor the health status of [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="db42d-144">Essa mesma função também é usada pelo mecanismo de notificação por email configurado pelo sistema descrito mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="db42d-144">This same function is also used by the system configured e-mail notification mechanism described later in this topic.</span></span>   
<span data-ttu-id="db42d-145">Essas contagens agregadas podem ser usadas para monitorar a integridade do sistema.</span><span class="sxs-lookup"><span data-stu-id="db42d-145">These aggregated counts can be used to monitor system health.</span></span> <span data-ttu-id="db42d-146">Por exemplo, se a coluna number_ of_retention_loops for 0 em 30 minutos, pode ser que o gerenciamento de retenção esteja demorando ou talvez nem esteja funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="db42d-146">For example, if the number_ of_retention_loops column is 0 in 30 minutes, it is possible that retention management is taking long time or even not working correctly.</span></span> <span data-ttu-id="db42d-147">As colunas diferentes de zero do erro podem indicar problemas e os logs de Eventos Estendidos devem ser verificados para descobrir o problema.</span><span class="sxs-lookup"><span data-stu-id="db42d-147">Non-zero error columns may indicate problems and Extended Events logs should be checked to discover the problem.</span></span> <span data-ttu-id="db42d-148">Como alternativa, chame **smart_admin. sp_get_backup_diagnostics** procedimento armazenado para encontrar os detalhes do erro.</span><span class="sxs-lookup"><span data-stu-id="db42d-148">Alternatively, call **smart_admin.sp_get_backup_diagnostics** stored procedure to find the details of the error.</span></span>  
  
### <a name="using-agent-notification-for-assessing-backup-status-and-health"></a><span data-ttu-id="db42d-149">Usando a notificação do agente para avaliar o status e a integridade do backup</span><span class="sxs-lookup"><span data-stu-id="db42d-149">Using Agent Notification for Assessing Backup Status and Health</span></span>  
 <span data-ttu-id="db42d-150">O [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] inclui um mecanismo de notificação baseado nas políticas de gerenciamento baseado em políticas do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="db42d-150">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] includes a notification mechanism that is based on SQL Server policy based management policies.</span></span>  
  
 <span data-ttu-id="db42d-151">**Pré-requisitos:**</span><span class="sxs-lookup"><span data-stu-id="db42d-151">**Prerequisites:**</span></span>  
  
-   <span data-ttu-id="db42d-152">O Database Mail é necessário para usar essa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="db42d-152">Database Mail is required to use this functionality.</span></span> <span data-ttu-id="db42d-153">Para obter mais informações, sobre como habilitar o BD mail para a instância do SQL Server, consulte [configurar Database Mail](../relational-databases/database-mail/configure-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="db42d-153">For more information, about how to enable DB Mail for the instance of SQL Server, see [Configure Database Mail](../relational-databases/database-mail/configure-database-mail.md).</span></span>  
  
-   <span data-ttu-id="db42d-154">As propriedades do Sistema de Alerta do SQL Server Agent devem estar definidas para usar o Database Mail.</span><span class="sxs-lookup"><span data-stu-id="db42d-154">SQL Server Agent Alert System properties should be set to use Database Mail.</span></span>  
  
 <span data-ttu-id="db42d-155">**Arquitetura de notificação:**</span><span class="sxs-lookup"><span data-stu-id="db42d-155">**Notification Architecture:**</span></span>  
  
-   <span data-ttu-id="db42d-156">**Gerenciamento baseado em políticas:** Duas políticas são definidas para monitorar a integridade do backup: **política de integridade do sistema de administração inteligente**e **política de integridade da ação do usuário do administrador inteligente**.</span><span class="sxs-lookup"><span data-stu-id="db42d-156">**Policy Based Management:** Two policies are set to monitor backup health: **Smart Admin System Health Policy**, and the **Smart Admin User Action Health Policy**.</span></span> <span data-ttu-id="db42d-157">A Política de Integridade do Sistema do Smart Admin avalia os erros críticos, como a falta de Credenciais do SQL ou credenciais desse tipo inválidas e os erros de conectividade e relata a integridade do sistema.</span><span class="sxs-lookup"><span data-stu-id="db42d-157">The Smart Admin System Health Policy evaluates critical errors like lack of or invalid SQL Credentials, connectivity errors and reports the health of the system.</span></span> <span data-ttu-id="db42d-158">Esses normalmente requerem uma ação manual para corrigir o problema subjacente.</span><span class="sxs-lookup"><span data-stu-id="db42d-158">These typically require a manual action to correct the underlying issue.</span></span> <span data-ttu-id="db42d-159">A Política de Integridade de Ação do Usuário do Smart Admin avalia os avisos, como backups corrompidos e itens semelhantes.</span><span class="sxs-lookup"><span data-stu-id="db42d-159">The Smart Admin User Action Health Policy evaluates warnings such as corrupted backups, and such.</span></span>  <span data-ttu-id="db42d-160">Talvez eles não exijam nenhuma ação, mas apenas um aviso de um evento.</span><span class="sxs-lookup"><span data-stu-id="db42d-160">These may not require any action but just a warning of an event.</span></span> <span data-ttu-id="db42d-161">Espera-se que esses problemas sejam resolvidos automaticamente pelo agente [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db42d-161">It is expected that such issues will be automatically taken care of by [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] agent.</span></span>  
  
-   <span data-ttu-id="db42d-162">**SQL Server Agent** Trabalho: a notificação é executada usando um trabalho SQL Server Agent que tem três etapas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="db42d-162">**SQL Server Agent** Job: The notification is performed using a SQL Server Agent job that has three job steps.</span></span> <span data-ttu-id="db42d-163">Na primeira etapa do trabalho, ele detecta se o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] está configurado para um banco de dados ou instância.</span><span class="sxs-lookup"><span data-stu-id="db42d-163">In the first job step it detects to see whether [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is configured for a database or instance.</span></span> <span data-ttu-id="db42d-164">Se ele encontrar o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] habilitado e configurado, executará a segunda etapa: um cmdlet do PowerShell que avalia o status de integridade examinando as políticas de gerenciamento baseado em políticas do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="db42d-164">If it finds [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] enabled and configured, it executes the second step: executes a PowerShell cmdlet that assess the health status by evaluating the SQL Server policy based management policies.</span></span> <span data-ttu-id="db42d-165">Se ele encontrar um erro ou aviso, ocorrerá uma falha, que disparará a terceira etapa, que é enviar uma notificação por email com o relatório de erro/aviso.</span><span class="sxs-lookup"><span data-stu-id="db42d-165">If it finds either an error or warning, it fails which then triggers the third step: The third step sends out an e-mail notification with the error/warning report.</span></span>  <span data-ttu-id="db42d-166">No entanto, esse trabalho do SQL Server Agent não está habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="db42d-166">However this SQL Server Agent job is not enabled by default.</span></span> <span data-ttu-id="db42d-167">Para habilitar o trabalho de notificação por email, use o procedimento armazenado do sistema **smart_admin. sp_set_backup_parameter** .</span><span class="sxs-lookup"><span data-stu-id="db42d-167">To enable the e-mail notification job, use the **smart_admin.sp_set_backup_parameter** system stored procedure.</span></span>  <span data-ttu-id="db42d-168">O procedimento a seguir descreve as etapas com mais detalhes:</span><span class="sxs-lookup"><span data-stu-id="db42d-168">The following procedure describes the steps in more detail:</span></span>  
  
##### <a name="enabling-email-notification"></a><span data-ttu-id="db42d-169">Habilitando a notificação por email</span><span class="sxs-lookup"><span data-stu-id="db42d-169">Enabling Email Notification</span></span>  
  
1.  <span data-ttu-id="db42d-170">Se Database Mail ainda não estiver configurado, use as etapas descritas em [configurar Database Mail](../relational-databases/database-mail/configure-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="db42d-170">If Database Mail is not already configured, use the steps described in [Configure Database Mail](../relational-databases/database-mail/configure-database-mail.md).</span></span>  
  
2.  <span data-ttu-id="db42d-171">Definir banco de dados como o sistema de email para SQL Server sistema de alertas: clique com o botão direito do mouse em **SQL Server Agent**, selecione **sistema de alerta**, marque a caixa **habilitar perfil de email** , selecione **Database Mail** como o **sistema de email**e selecione um perfil de email criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="db42d-171">Set database as the Mail System for SQL Server Alert System: Right Click on **SQL Server Agent**, select **Alert System**, check the **Enable mail profile** box, Select **Database Mail** as the **Mail System**, and select a previously created Mail profile.</span></span>  
  
3.  <span data-ttu-id="db42d-172">Execute a consulta a seguir em uma janela de consulta e forneça o endereço de email para o qual você deseja que a notificação seja enviada:</span><span class="sxs-lookup"><span data-stu-id="db42d-172">Run the following query in a query window and provide the e-mail address where you want the notification to be sent to:</span></span>  
  
    ```sql
    Use msdb  
    Go  
    EXEC smart_admin.sp_set_parameter @parameter_name = 'SSMBackup2WANotificationEmailIds', @parameter_value = '<email address>'
    ```  
  
     <span data-ttu-id="db42d-173">Isso cria um trabalho do SQL Server Agent que é usado para coletar o status de integridade e enviar notificações quando ocorre um erro ou um problema com os backups.</span><span class="sxs-lookup"><span data-stu-id="db42d-173">This creates a SQL Server Agent job that is used to gather health status and send notifications when there is an error or an issue with backups.</span></span>  
  
 <span data-ttu-id="db42d-174">A seguir é mostrado um exemplo de script para habilitar o DB Mail e para configurar notificação por email através do Trabalho do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="db42d-174">Following is a sample script  to enable DB Mail and set up the e-mail notification through SQL Server Agent Job</span></span>  
  
```sql
-- Prereq: Make sure that SQL Server service runs in a service account that has  
--  access to SMTP Server   
-- set SQL Server service account as domain account   
  
EXEC sp_configure 'show advanced', 1  
RECONFIGURE  
GO  
  
-- Enable DBMail  
EXEC sp_configure 'Database Mail XPs',1  
GO  
RECONFIGURE  
GO  
  
-- Configure DBMail  
DECLARE @emailid NVARCHAR(255)  
-- Note: change this email to your own email id  
SET @emailid = N'emailalias@mycompany.com'  
  
DECLARE @smtpserver NVARCHAR(255)  
SET @smtpserver = N'smtphost.domainname.com'  
  
DECLARE @mailprofile NVARCHAR(255)  
SET @mailprofile = N'my_profile'  
  
EXEC msdb.dbo.sysmail_add_account_sp @account_name=N'myaccount',  
                @email_address = @emailid,  
                @replyto_address = @emailid,  
                @mailserver_name = @smtpserver,  
                @use_default_credentials = 1  
  
EXEC msdb.dbo.sysmail_add_profile_sp @profile_name=@mailprofile  
EXEC msdb.dbo.sysmail_add_profileaccount_sp @profile_name=@mailprofile, @account_name=N'myaccount', @sequence_number=1  
  
-- Set SQL Agent to use DBMail profile  
EXEC msdb.dbo.sp_set_sqlagent_properties @databasemail_profile = @mailprofile  
  
-- Configure Notifications   
EXEC msdb.smart_admin.sp_set_parameter  
@parameter_name = 'SSMBackup2WANotificationEmailIds',  
@parameter_value = @emailid  
  
-- To test is you are receiving notifications  
-- delete few backup files from your storage container, Wait for 15 minutes & see if you get any email notification
```  
  
### <a name="using-powershell-to-setup-custom-health-monitoring"></a><span data-ttu-id="db42d-175">Usando o PowerShell para configurar o monitoramento de integridade personalizado</span><span class="sxs-lookup"><span data-stu-id="db42d-175">Using PowerShell to Setup Custom Health Monitoring</span></span>  
 <span data-ttu-id="db42d-176">O cmdlet **Test-SqlSmartAdmin** pode ser usado para criar o monitoramento de integridade personalizado.</span><span class="sxs-lookup"><span data-stu-id="db42d-176">The **Test-SqlSmartAdmin** cmdlet can be used to create custom health monitoring.</span></span> <span data-ttu-id="db42d-177">Por exemplo, a opção de notificação descrita na seção anterior pode ser configurada no nível da instância.</span><span class="sxs-lookup"><span data-stu-id="db42d-177">For example, the notification option described in the previous section can be configured at the instance level.</span></span>  <span data-ttu-id="db42d-178">Se você tiver várias instâncias do SQL Server configuradas para usar o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)], o cmdlet do PowerShell poderá ser usado para criar scripts ao coletar o status e a integridade dos backups de todas as instâncias.</span><span class="sxs-lookup"><span data-stu-id="db42d-178">If you have several instances of SQL Server configured to use [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)], the PowerShell cmdlet can be used to create scripts in gather the status and health of backups for all the instances.</span></span>  
  
 <span data-ttu-id="db42d-179">O cmdlet **Test-SqlSmartAdmin** avalia os erros e avisos retornados pelo SQL Server políticas de gerenciamento baseado em políticas e relata um status acumulado.</span><span class="sxs-lookup"><span data-stu-id="db42d-179">The **Test-SqlSmartAdmin** cmdlet assesses the errors and warnings returned by the SQL Server Policy Based Management policies and reports out a rolled up status.</span></span>  <span data-ttu-id="db42d-180">Por padrão, esse cmdlet usa as políticas do sistema.</span><span class="sxs-lookup"><span data-stu-id="db42d-180">By default this cmdlet uses the system policies.</span></span> <span data-ttu-id="db42d-181">Para incluir qualquer política personalizada, use o parâmetro `-AllowUserPolicies`.</span><span class="sxs-lookup"><span data-stu-id="db42d-181">To include any custom policy use the `-AllowUserPolicies` parameter.</span></span>  
  
 <span data-ttu-id="db42d-182">A seguir é mostrado um exemplo de script PowerShell que retorna um relatório de erros e avisos com base nas políticas do sistema e qualquer política de usuário criada:</span><span class="sxs-lookup"><span data-stu-id="db42d-182">Following is a sample PowerShell script that returns a report of errors and warnings based on the system policies and any user policies created:</span></span>  
  
```powershell
$policyResults = Get-SqlSmartAdmin | Test-SqlSmartAdmin -AllowUserPolicies  
$policyResults.PolicyEvaluationDetails | Select Name, Category, Expression, Result, Exception | fl
```  
  
 <span data-ttu-id="db42d-183">O script a seguir retorna um relatório detalhado dos erros e avisos para a instância padrão ( `\SQL\COMPUTER\DEFAULT` ):</span><span class="sxs-lookup"><span data-stu-id="db42d-183">The following script returns a detailed report of the errors and warnings for the default instance (`\SQL\COMPUTER\DEFAULT`):</span></span>  
  
```powershell
(Get-SqlSmartAdmin ).EnumHealthStatus()  
```  
  
### <a name="objects-in-msdb-database"></a><span data-ttu-id="db42d-184">Objetos em um banco de dados MSDB</span><span class="sxs-lookup"><span data-stu-id="db42d-184">Objects in MSDB database</span></span>  
 <span data-ttu-id="db42d-185">Há objetos que são instalados para implementar a funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="db42d-185">There are objects that are installed to implement the functionality.</span></span> <span data-ttu-id="db42d-186">Esses objetos são reservados para uso interno.</span><span class="sxs-lookup"><span data-stu-id="db42d-186">These objects are reserved for internal use.</span></span> <span data-ttu-id="db42d-187">Porém, há uma tabela do sistema que pode ser útil para monitorar o status do backup: smart_backup_files.</span><span class="sxs-lookup"><span data-stu-id="db42d-187">However, there is one system table that can be useful in monitoring the backup status: smart_backup_files.</span></span> <span data-ttu-id="db42d-188">A maioria das informações armazenadas nesta tabela é relevante para o monitoramento como o tipo de backup, nome do banco de dados, primeiro e último LSN, as datas de expiração de backup são expostas por meio da função do sistema [smart_admin. fn_available_backups &#40;&#41;do Transact-SQL ](/sql/relational-databases/system-functions/managed-backup-fn-available-backups-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="db42d-188">Most of the Information   stored in this table relevant to monitoring like the type of backup, database name, first and last lsn, backup expiry dates are exposed through the system function [smart_admin.fn_available_backups &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/managed-backup-fn-available-backups-transact-sql).</span></span> <span data-ttu-id="db42d-189">Embora a coluna de status na tabela smart_backup_files que indica o status do arquivo de backup não esteja disponível por meio da função.</span><span class="sxs-lookup"><span data-stu-id="db42d-189">However the status column in the smart_backup_files table which indicates the status of the backup file is not available using the function.</span></span> <span data-ttu-id="db42d-190">O seguinte é um exemplo de consulta que você pode usar para recuperar algumas informações que incluem o status da tabela do sistema:</span><span class="sxs-lookup"><span data-stu-id="db42d-190">Following is a sample query you can use to retrieve the some information including the status from the system table:</span></span>  
  
```sql
USE msdb  
GO  
SELECT  
 database_name AS [Database Name] ,backup_path AS [Backup Destination and File]  
,[Backup Type] =  
CASE backup_type  
WHEN 1 THEN 'FULL'  
WHEN 2 THEN 'LOG'  
END  
,[Backup Status] =  
CASE [status]  
WHEN 'A' THEN 'Available'  
WHEN 'B' THEN 'Copy In Progress'  
WHEN 'C' THEN 'Corrupted'  
WHEN 'D' THEN 'Deleted'  
WHEN 'F' THEN 'Copy Failed'  
WHEN 'U' THEN 'Unknown'  
END  
,first_lsn AS [First LSN]  
,last_lsn AS [Last LSN]  
,backup_start_date AS [Backup Start Time]  
,backup_finish_date AS [Backup Completion Time]  
,expiration_date AS [Backup Expiry Date/Time]  
FROM  
smart_backup_files;
```  
  
 <span data-ttu-id="db42d-191">Veja a seguir uma explicação detalhada do status diferente retornado:</span><span class="sxs-lookup"><span data-stu-id="db42d-191">Following is a detailed explanation of the different status returned:</span></span>  
  
-   <span data-ttu-id="db42d-192">**Disponível-a:** Este é um arquivo de backup normal.</span><span class="sxs-lookup"><span data-stu-id="db42d-192">**Available - A:** This is a normal backup file.</span></span> <span data-ttu-id="db42d-193">O backup foi concluído e também verificou se ele está disponível no armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="db42d-193">The backup has been completed, and also verified that it is available in the Azure storage.</span></span>  
  
-   <span data-ttu-id="db42d-194">**Cópia em andamento-B:** Esse status é especificamente para bancos de dados do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="db42d-194">**Copy in Progress -B:** This status is specifically for Availability Group databases.</span></span> <span data-ttu-id="db42d-195">Se o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] detectar uma interrupção na cadeia de logs de backup, ele primeiro tentará identificar o backup que pode ter causado essa interrupção.</span><span class="sxs-lookup"><span data-stu-id="db42d-195">If [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] detects a break in the backup log chain, it will first attempt identify the  backup that might have caused the break in backup chain.</span></span> <span data-ttu-id="db42d-196">Ao localizar o arquivo de backup, ele tenta copiar o arquivo para o armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="db42d-196">On finding the backup file it attempts to copy the file to Azure storage.</span></span> <span data-ttu-id="db42d-197">Quando o processo de cópia estiver em andamento, ele exibirá esse status.</span><span class="sxs-lookup"><span data-stu-id="db42d-197">When the copying process is in progress it will display this status.</span></span>  
  
-   <span data-ttu-id="db42d-198">**Falha na cópia-F:** Semelhante à cópia em andamento, esses bancos de dados de grupo de disponibilidade t são específicos.</span><span class="sxs-lookup"><span data-stu-id="db42d-198">**Copy Failed - F:** Similar to Copy In Progress, this is specific t Availability Group databases.</span></span> <span data-ttu-id="db42d-199">Se o processo de cópia falhar, o status será marcado como F.</span><span class="sxs-lookup"><span data-stu-id="db42d-199">If the copy process fails, the status is marked as F.</span></span>  
  
-   <span data-ttu-id="db42d-200">**Corrompido-C:** Se [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] o não puder verificar o arquivo de backup no armazenamento executando um comando restore HEADER_ONLY, mesmo após várias tentativas, ele marcará esse arquivo como corrompido.</span><span class="sxs-lookup"><span data-stu-id="db42d-200">**Corrupted - C:** If [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is unable to verify the backup file in the storage by performing a RESTORE HEADER_ONLY command even after multiple attempts, it marks this file as corrupted.</span></span> <span data-ttu-id="db42d-201">O [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] agendará um backup para garantir que o arquivo corrompido não resulte em uma interrupção da cadeia de backup.</span><span class="sxs-lookup"><span data-stu-id="db42d-201">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] will schedule a backup to ensure that the corrupted file does not result in a break of the backup chain.</span></span>  
  
-   <span data-ttu-id="db42d-202">**Excluído-D:** O arquivo correspondente não pode ser encontrado no armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="db42d-202">**Deleted - D:** The corresponding file cannot be found in the Azure storage.</span></span> <span data-ttu-id="db42d-203">O [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] agendará um backup se o arquivo excluído resultar em uma interrupção na cadeia de backup.</span><span class="sxs-lookup"><span data-stu-id="db42d-203">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] will schedule a backup if the deleted file results in a break in the backup chain.</span></span>  
  
-   <span data-ttu-id="db42d-204">**Desconhecido-U:** Esse status indicou que [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] ainda não foi capaz de verificar a existência do arquivo e suas propriedades no armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="db42d-204">**Unknown - U:** This status indicated that [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] has not yet been able to verify file existence and its properties in the Azure storage.</span></span> <span data-ttu-id="db42d-205">Na próxima vez que o processo for executado, que é aproximadamente a cada 15 minutos, esse status será atualizado.</span><span class="sxs-lookup"><span data-stu-id="db42d-205">The next time the process runs, which is approximately every 15 minutes, this status will be updated.</span></span>  
