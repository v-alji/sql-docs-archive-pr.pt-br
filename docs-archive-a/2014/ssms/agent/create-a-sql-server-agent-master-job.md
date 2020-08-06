---
title: Criar um trabalho mestre do SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 04/26/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], master jobs
- jobs [SQL Server Agent], creating
- master SQL Server Agent job [SQL Server]
ms.assetid: c12ab23f-d7ee-43a5-8cd2-0a9121292bcd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8a6503caec3f153878e360ee29ce09a5c099ade5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680741"
---
# <a name="create-a-sql-server-agent-master-job"></a><span data-ttu-id="07337-102">Criar um trabalho mestre do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="07337-102">Create a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="07337-103">Este tópico descreve como criar um [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trabalho do agente mestre no usando o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07337-103">This topic describes how to create a master [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="07337-104">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="07337-104">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="07337-105">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="07337-105">Limitations and Restrictions</span></span>  
 <span data-ttu-id="07337-106">Alterações em trabalhos mestres do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent devem ser propagadas para todos os servidores de destino envolvidos.</span><span class="sxs-lookup"><span data-stu-id="07337-106">Changes to master [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs must be propagated to all involved target servers.</span></span> <span data-ttu-id="07337-107">Como os servidores de destino inicialmente não baixam um trabalho até que os destinos estejam especificados, a [!INCLUDE[msCoName](../../includes/msconame-md.md)] recomenda que você conclua todas as etapas de trabalho e as agendas de um trabalho em particular antes de especificar servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="07337-107">Because target servers do not initially download a job until those targets are specified, [!INCLUDE[msCoName](../../includes/msconame-md.md)] recommends that you complete all job steps and job schedules for a particular job before you specify any target servers.</span></span> <span data-ttu-id="07337-108">Caso contrário, você deve solicitar manualmente que os servidores de destino baixem o trabalho modificado novamente, executando o procedimento armazenado **sp_post_msx_operation** ou modificando o trabalho usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07337-108">Otherwise, you must manual request that the target servers download the modified job again, either by executing the **sp_post_msx_operation** stored procedure or modifying the job using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="07337-109">Para obter mais informações, consulte [sp_post_msx_operation &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql) ou [modificar um trabalho](modify-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="07337-109">For more information, see [sp_post_msx_operation &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql) or [Modify a Job](modify-a-job.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="07337-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="07337-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="07337-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="07337-111">Permissions</span></span>  
 <span data-ttu-id="07337-112">Trabalhos distribuídos que possuem etapas associadas a um proxy são executados no contexto da conta proxy no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="07337-112">Distributed jobs that have steps which are associated with a proxy run under the context of the proxy account on the target server.</span></span> <span data-ttu-id="07337-113">Certifique-se de que as seguintes condições sejam atendidas, ou as etapas de trabalho associadas a um proxy não serão baixadas do servidor mestre para o destino:</span><span class="sxs-lookup"><span data-stu-id="07337-113">Make sure that the following conditions are met or job steps that are associated with a proxy will not be downloaded from the master server to the target:</span></span>  
  
-   <span data-ttu-id="07337-114">A subchave do registro **\ HKEY_LOCAL_MACHINE \software\microsoft\microsoft SQL Server \\ < *instance_name*> \SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) é definida como 1 (true).</span><span class="sxs-lookup"><span data-stu-id="07337-114">The registry subkey **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<*instance_name*>\SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) is set to 1 (true).</span></span> <span data-ttu-id="07337-115">Por padrão, essa subchave encontra-se definida como 0 (falso).</span><span class="sxs-lookup"><span data-stu-id="07337-115">By default, this subkey is set to 0 (false).</span></span>  
  
-   <span data-ttu-id="07337-116">Existe uma conta proxy no servidor de destino com o mesmo nome da conta proxy do servidor mestre sob a qual a etapa de trabalho é executada.</span><span class="sxs-lookup"><span data-stu-id="07337-116">A proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
 <span data-ttu-id="07337-117">Se as etapas de trabalho que usam contas proxy falharem ao serem baixadas do servidor mestre para o servidor de destino, verifique a coluna **error_message** da tabela **sysdownloadlist** no banco de dados **msdb** quanto às seguintes mensagens de erro:</span><span class="sxs-lookup"><span data-stu-id="07337-117">If job steps that use proxy accounts fail when downloading them from the master server to the target server, you can check the **error_message** column in the **sysdownloadlist** table in the **msdb** database for the following error messages:</span></span>  
  
-   <span data-ttu-id="07337-118">"A etapa do trabalho requer uma conta proxy. Entretanto, a verificação de proxy está desabilitada no servidor de destino."</span><span class="sxs-lookup"><span data-stu-id="07337-118">"The job step requires a proxy account, however proxy matching is disabled on the target server."</span></span> <span data-ttu-id="07337-119">Para resolver este erro, defina a subchave **AllowDownloadedJobsToMatchProxyName** do Registro como 1.</span><span class="sxs-lookup"><span data-stu-id="07337-119">To resolve this error, set the **AllowDownloadedJobsToMatchProxyName** registry subkey to 1.</span></span>  
  
-   <span data-ttu-id="07337-120">"Proxy não localizado."</span><span class="sxs-lookup"><span data-stu-id="07337-120">"Proxy not found."</span></span> <span data-ttu-id="07337-121">Para resolver este erro, certifique-se de que existe uma conta proxy no servidor de destino com o mesmo nome da conta proxy do servidor mestre sob a qual a etapa de trabalho é executada.</span><span class="sxs-lookup"><span data-stu-id="07337-121">To resolve this error, make sure a proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="07337-122">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="07337-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-master-sql-server-agent-job"></a><span data-ttu-id="07337-123">Para criar um trabalho mestre do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="07337-123">To create a master SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="07337-124">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor no qual você deseja criar o trabalho do SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="07337-124">In the **Object Explorer**, click the plus sign to expand the server where you want to create a SQL Server Agent job.</span></span>  
  
2.  <span data-ttu-id="07337-125">Clique no sinal de adição para expandir o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="07337-125">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="07337-126">Clique com o botão direito do mouse na pasta **Trabalhos** e selecione **Novo Trabalho...**.</span><span class="sxs-lookup"><span data-stu-id="07337-126">Right-click the **Jobs** folder and select **New Job...**.</span></span>  
  
4.  <span data-ttu-id="07337-127">Na caixa de diálogo **Novo Trabalho** , na página **Geral** , modifique as propriedades gerais do trabalho.</span><span class="sxs-lookup"><span data-stu-id="07337-127">In the **New Job** dialog box, on the **General** page, modify the general properties of the job.</span></span> <span data-ttu-id="07337-128">Para obter mais informações sobre as opções disponíveis nesta página, consulte [Propriedades do trabalho e novo trabalho &#40;página geral&#41;](../../integration-services/general-page-of-integration-services-designers-options.md)</span><span class="sxs-lookup"><span data-stu-id="07337-128">For more information on the available options on this page, see [Job Properties and New Job &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md)</span></span>  
  
5.  <span data-ttu-id="07337-129">Na página **Etapas** , organize as etapas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="07337-129">On the **Steps** page, organize the job steps.</span></span> <span data-ttu-id="07337-130">Para obter mais informações sobre as opções disponíveis nesta página, consulte [Propriedades do trabalho: página de etapas do novo trabalho &#40;&#41;](job-properties-new-job-steps-page.md)</span><span class="sxs-lookup"><span data-stu-id="07337-130">For more information on the available options on this page, see [Job Properties:New Job &#40;Steps Page&#41;](job-properties-new-job-steps-page.md)</span></span>  
  
6.  <span data-ttu-id="07337-131">Na página **Agendas** , organize agendas para o trabalho.</span><span class="sxs-lookup"><span data-stu-id="07337-131">On the **Schedules** page, organize schedules for the job.</span></span> <span data-ttu-id="07337-132">Para obter mais informações sobre as opções disponíveis nesta página, consulte [Propriedades do trabalho: nova página de agendas de &#40;de trabalho&#41;](job-properties-new-job-schedules-page.md)</span><span class="sxs-lookup"><span data-stu-id="07337-132">For more information on the available options on this page, see [Job Properties: New Job &#40;Schedules Page&#41;](job-properties-new-job-schedules-page.md)</span></span>  
  
7.  <span data-ttu-id="07337-133">Na página **Alertas** , organize os alertas para o trabalho.</span><span class="sxs-lookup"><span data-stu-id="07337-133">On the **Alerts** page, organize the alerts for the job.</span></span> <span data-ttu-id="07337-134">Para obter mais informações sobre as opções disponíveis nesta página, consulte [Propriedades do trabalho: nova página de alertas de &#40;de trabalho&#41;](job-properties-new-job-alerts-page.md)</span><span class="sxs-lookup"><span data-stu-id="07337-134">For more information on the available options on this page, see [Job Properties: New Job &#40;Alerts Page&#41;](job-properties-new-job-alerts-page.md)</span></span>  
  
8.  <span data-ttu-id="07337-135">Na página **Notificações**, defina ações para que o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent seja executado quando o trabalho for concluído.</span><span class="sxs-lookup"><span data-stu-id="07337-135">On the **Notifications** page, set actions for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform when the job completes.</span></span> <span data-ttu-id="07337-136">Para obter mais informações sobre as opções disponíveis nesta página, consulte [Propriedades do trabalho: nova página de notificações de &#40;de trabalho&#41;](job-properties-new-job-notifications-page.md).</span><span class="sxs-lookup"><span data-stu-id="07337-136">For more information on the available options on this page, see [Job Properties: New Job &#40;Notifications Page&#41;](job-properties-new-job-notifications-page.md).</span></span>  
  
9. <span data-ttu-id="07337-137">Na página **Destinos** , gerencie os servidores de destino para o trabalho.</span><span class="sxs-lookup"><span data-stu-id="07337-137">On the **Targets** page, manage the target servers for the job.</span></span> <span data-ttu-id="07337-138">Para obter mais informações sobre as opções disponíveis nesta página, consulte [Propriedades do trabalho: nova página de destinos de &#40;de trabalho&#41;](job-properties-new-job-targets-page.md).</span><span class="sxs-lookup"><span data-stu-id="07337-138">For more information on the available options on this page, see [Job Properties: New Job &#40;Targets Page&#41;](job-properties-new-job-targets-page.md).</span></span>  
  
10. <span data-ttu-id="07337-139">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="07337-139">When finished, click **OK**.</span></span>  
  

  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="07337-140">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="07337-140">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-master-sql-server-agent-job"></a><span data-ttu-id="07337-141">Para criar um trabalho mestre do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="07337-141">To create a master SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="07337-142">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07337-142">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="07337-143">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="07337-143">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="07337-144">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="07337-144">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb ;  
    GO  
    -- Adds a new job executed by the SQLServerAgent service called 'Weekly Sales Data Backup'  
    EXEC dbo.sp_add_job  
        @job_name = N'Weekly Sales Data Backup' ;  
    GO  
    -- Adds a step (operation) to the 'Weekly Sales Data Backup' job.  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'TSQL',  
        @command = N'ALTER DATABASE SALES SET READ_ONLY',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    -- Creates a schedule called RunOnce  
    EXEC dbo.sp_add_schedule  
        @schedule_name = N'RunOnce',  
        @freq_type = 1,  
        @active_start_time = 233000 ;  
    USE msdb ;  
    GO  
    -- Sets the 'RunOnce' schedule to the "Weekly Sales Data Backup' Job  
    EXEC sp_attach_schedule  
       @job_name = N'Weekly Sales Data Backup',  
       @schedule_name = N'RunOnce';  
    GO  
    -- assigns the multiserver job Weekly Sales Backups to the server SEATTLE2  
    -- assumes that SEATTLE2 is registered as a target server for the current instance.  
    EXEC dbo.sp_add_jobserver  
        @job_name = N'Weekly Sales Data Backups',  
        @server_name = N'SEATTLE2' ;  
    GO  
    ```  
  
 <span data-ttu-id="07337-145">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="07337-145">For more information, see:</span></span>  
  
-   [<span data-ttu-id="07337-146">sp_add_job &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="07337-146">sp_add_job &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql)  
  
-   [<span data-ttu-id="07337-147">sp_add_jobstep &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="07337-147">sp_add_jobstep &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)  
  
-   [<span data-ttu-id="07337-148">sp_add_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="07337-148">sp_add_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql)  
  
-   [<span data-ttu-id="07337-149">sp_attach_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="07337-149">sp_attach_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql)  
  
-   [<span data-ttu-id="07337-150">&#41;&#40;Transact-SQL de sp_add_jobserver</span><span class="sxs-lookup"><span data-stu-id="07337-150">sp_add_jobserver &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql)  
  

  
  
