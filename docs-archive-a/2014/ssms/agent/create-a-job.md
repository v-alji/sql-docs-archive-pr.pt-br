---
title: Criar um trabalho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], creating
- SQL Server Agent jobs, creating
ms.assetid: b35af2b6-6594-40d1-9861-4d5dd906048c
author: stevestein
ms.author: sstein
ms.openlocfilehash: de74f032924fbb0b6643bd8f3d482481ffb1f983
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569024"
---
# <a name="create-a-job"></a><span data-ttu-id="77adf-102">Crie um trabalho</span><span class="sxs-lookup"><span data-stu-id="77adf-102">Create a Job</span></span>
  <span data-ttu-id="77adf-103">Este tópico descreve como criar um trabalho do SQL Server Agent no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] ou SMO (SQL Server Management Objects).</span><span class="sxs-lookup"><span data-stu-id="77adf-103">This topic describes how to create a SQL Server Agent job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects (SMO).</span></span>  
  
 <span data-ttu-id="77adf-104">Para adicionar etapas de trabalho, agendas, alertas e notificações que podem ser enviadas a operadores, consulte os tópicos na seção Consulte também.</span><span class="sxs-lookup"><span data-stu-id="77adf-104">To add job steps, schedules, alerts, and notifications that can be sent to operators, see the links to topics in the See Also section.</span></span>  
  
-   <span data-ttu-id="77adf-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="77adf-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="77adf-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="77adf-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="77adf-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="77adf-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="77adf-108">**Para criar um trabalho, usando:**</span><span class="sxs-lookup"><span data-stu-id="77adf-108">**To create a job, using:**</span></span>  
  
     <span data-ttu-id="77adf-109">[SQL Server Management Studio](#SSMSProcedure),</span><span class="sxs-lookup"><span data-stu-id="77adf-109">[SQL Server Management Studio](#SSMSProcedure),</span></span>  
  
     [<span data-ttu-id="77adf-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="77adf-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="77adf-111">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="77adf-111">SQL Server Management Objects</span></span>](#SMOProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="77adf-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="77adf-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="77adf-113">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="77adf-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="77adf-114">Para criar um trabalho, o usuário deve ser membro de uma das funções de banco de dados fixas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent ou da função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="77adf-114">To create a job, a user must be a member of one of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles or the **sysadmin** fixed server role.</span></span> <span data-ttu-id="77adf-115">Um trabalho só pode ser editado por seu proprietário ou por membros da função **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="77adf-115">A job can be edited only by its owner or members of the **sysadmin** role.</span></span> <span data-ttu-id="77adf-116">Para obter mais informações sobre as funções de banco de dados fixas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, consulte [Funções de banco de dados fixas do SQL Server Agent](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="77adf-116">For more information about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
-   <span data-ttu-id="77adf-117">Atribuir um trabalho a outro logon não garante que o novo proprietário tenha permissões adequadas para executar o trabalho com êxito.</span><span class="sxs-lookup"><span data-stu-id="77adf-117">Assigning a job to another login does not guarantee that the new owner has sufficient permission to run the job successfully.</span></span>  
  
-   <span data-ttu-id="77adf-118">Trabalhos locais são armazenados em cache pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent local.</span><span class="sxs-lookup"><span data-stu-id="77adf-118">Local jobs are cached by the local [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="77adf-119">Portanto, qualquer modificação obriga, implicitamente, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent a rearmazenar em cache o trabalho.</span><span class="sxs-lookup"><span data-stu-id="77adf-119">Therefore, any modifications implicitly force [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to re-cache the job.</span></span> <span data-ttu-id="77adf-120">Como o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent não armazena o trabalho em cache até que **sp_add_jobserver** seja chamado, é mais eficiente chamar **sp_add_jobserver** por último.</span><span class="sxs-lookup"><span data-stu-id="77adf-120">Because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent does not cache the job until **sp_add_jobserver** is called, it is more efficient to call **sp_add_jobserver** last.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="77adf-121">Segurança</span><span class="sxs-lookup"><span data-stu-id="77adf-121">Security</span></span>  
  
-   <span data-ttu-id="77adf-122">Você precisa ser um administrador do sistema para alterar o proprietário de um trabalho.</span><span class="sxs-lookup"><span data-stu-id="77adf-122">You must be a system administrator to change the owner of a job.</span></span>  
  
-   <span data-ttu-id="77adf-123">Por questão de segurança, apenas o proprietário do trabalho ou um membro da função **sysadmin** pode alterar a definição do trabalho.</span><span class="sxs-lookup"><span data-stu-id="77adf-123">For security reasons, only the job owner or a member of the **sysadmin** role can change the definition of the job.</span></span> <span data-ttu-id="77adf-124">Somente os membros da função de servidor fixa **sysadmin** podem atribuir a propriedade do trabalho a outros usuários, bem como executar qualquer trabalho, independentemente de seu proprietário.</span><span class="sxs-lookup"><span data-stu-id="77adf-124">Only members of the **sysadmin** fixed server role can assign job ownership to other users, and they can run any job, regardless of the job owner.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="77adf-125">Se você transmitir a propriedade a um usuário que não seja membro da função de servidor fixa **sysadmin** e o trabalho estiver executando etapas que exijam contas proxy (por exemplo, execução de pacotes [!INCLUDE[ssIS](../../includes/ssis-md.md)] ), verifique se o usuário tem acesso à conta proxy necessária, ou o trabalho falhará.</span><span class="sxs-lookup"><span data-stu-id="77adf-125">If you change job ownership to a user who is not a member of the **sysadmin** fixed server role, and the job is executing job steps that require proxy accounts (for example, [!INCLUDE[ssIS](../../includes/ssis-md.md)] package execution), make sure that the user has access to that proxy account or else the job will fail.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="77adf-126">Permissões</span><span class="sxs-lookup"><span data-stu-id="77adf-126">Permissions</span></span>  
 <span data-ttu-id="77adf-127">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="77adf-127">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="77adf-128">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="77adf-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-sql-server-agent-job"></a><span data-ttu-id="77adf-129">Para criar um trabalho do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="77adf-129">To create a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="77adf-130">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor no qual você deseja criar o trabalho do SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="77adf-130">In the **Object Explorer**, click the plus sign to expand the server where you want to create a SQL Server Agent job.</span></span>  
  
2.  <span data-ttu-id="77adf-131">Clique no sinal de adição para expandir o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="77adf-131">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="77adf-132">Clique com o botão direito do mouse na pasta **Trabalhos** e selecione **Novo Trabalho...**.</span><span class="sxs-lookup"><span data-stu-id="77adf-132">Right-click the **Jobs** folder and select **New Job...**.</span></span>  
  
4.  <span data-ttu-id="77adf-133">Na caixa de diálogo **Novo Trabalho** , na página **Geral** , modifique as propriedades gerais do trabalho.</span><span class="sxs-lookup"><span data-stu-id="77adf-133">In the **New Job** dialog box, on the **General** page, modify the general properties of the job.</span></span> <span data-ttu-id="77adf-134">Para obter mais informações sobre as opções disponíveis nesta página, consulte [Propriedades do trabalho e novo trabalho &#40;página geral&#41;](../../integration-services/general-page-of-integration-services-designers-options.md)</span><span class="sxs-lookup"><span data-stu-id="77adf-134">For more information on the available options on this page, see [Job Properties and New Job &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md)</span></span>  
  
5.  <span data-ttu-id="77adf-135">Na página **Etapas** , organize as etapas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="77adf-135">On the **Steps** page, organize the job steps.</span></span> <span data-ttu-id="77adf-136">Para obter mais informações sobre as opções disponíveis nesta página, consulte [Propriedades do trabalho: página de etapas do novo trabalho &#40;&#41;](job-properties-new-job-steps-page.md)</span><span class="sxs-lookup"><span data-stu-id="77adf-136">For more information on the available options on this page, see [Job Properties:New Job &#40;Steps Page&#41;](job-properties-new-job-steps-page.md)</span></span>  
  
6.  <span data-ttu-id="77adf-137">Na página **Agendas** , organize agendas para o trabalho.</span><span class="sxs-lookup"><span data-stu-id="77adf-137">On the **Schedules** page, organize schedules for the job.</span></span> <span data-ttu-id="77adf-138">Para obter mais informações sobre as opções disponíveis nesta página, consulte [Propriedades do trabalho: nova página de agendas de &#40;de trabalho&#41;](job-properties-new-job-schedules-page.md)</span><span class="sxs-lookup"><span data-stu-id="77adf-138">For more information on the available options on this page, see [Job Properties: New Job &#40;Schedules Page&#41;](job-properties-new-job-schedules-page.md)</span></span>  
  
7.  <span data-ttu-id="77adf-139">Na página **Alertas** , organize os alertas para o trabalho.</span><span class="sxs-lookup"><span data-stu-id="77adf-139">On the **Alerts** page, organize the alerts for the job.</span></span> <span data-ttu-id="77adf-140">Para obter mais informações sobre as opções disponíveis nesta página, consulte [Propriedades do trabalho: nova página de alertas de &#40;de trabalho&#41;](job-properties-new-job-alerts-page.md)</span><span class="sxs-lookup"><span data-stu-id="77adf-140">For more information on the available options on this page, see [Job Properties: New Job &#40;Alerts Page&#41;](job-properties-new-job-alerts-page.md)</span></span>  
  
8.  <span data-ttu-id="77adf-141">Na página **Notificações**, defina ações para que o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent seja executado quando o trabalho for concluído.</span><span class="sxs-lookup"><span data-stu-id="77adf-141">On the **Notifications** page, set actions for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform when the job completes.</span></span> <span data-ttu-id="77adf-142">Para obter mais informações sobre as opções disponíveis nesta página, consulte [Propriedades do trabalho: nova página de notificações de &#40;de trabalho&#41;](job-properties-new-job-notifications-page.md).</span><span class="sxs-lookup"><span data-stu-id="77adf-142">For more information on the available options on this page, see [Job Properties: New Job &#40;Notifications Page&#41;](job-properties-new-job-notifications-page.md).</span></span>  
  
9. <span data-ttu-id="77adf-143">Na página **Destinos** , gerencie os servidores de destino para o trabalho.</span><span class="sxs-lookup"><span data-stu-id="77adf-143">On the **Targets** page, manage the target servers for the job.</span></span> <span data-ttu-id="77adf-144">Para obter mais informações sobre as opções disponíveis nesta página, consulte [Propriedades do trabalho: nova página de destinos de &#40;de trabalho&#41;](job-properties-new-job-targets-page.md).</span><span class="sxs-lookup"><span data-stu-id="77adf-144">For more information on the available options on this page, see [Job Properties: New Job &#40;Targets Page&#41;](job-properties-new-job-targets-page.md).</span></span>  
  
10. <span data-ttu-id="77adf-145">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="77adf-145">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="77adf-146">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="77adf-146">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-sql-server-agent-job"></a><span data-ttu-id="77adf-147">Para criar um trabalho do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="77adf-147">To create a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="77adf-148">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77adf-148">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="77adf-149">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="77adf-149">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="77adf-150">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="77adf-150">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
    EXEC dbo.sp_add_job  
        @job_name = N'Weekly Sales Data Backup' ;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'TSQL',  
        @command = N'ALTER DATABASE SALES SET READ_ONLY',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    EXEC dbo.sp_add_schedule  
        @schedule_name = N'RunOnce',  
        @freq_type = 1,  
        @active_start_time = 233000 ;  
    USE msdb ;  
    GO  
    EXEC sp_attach_schedule  
       @job_name = N'Weekly Sales Data Backup',  
       @schedule_name = N'RunOnce';  
    GO  
    EXEC dbo.sp_add_jobserver  
        @job_name = N'Weekly Sales Data Backup';  
    GO  
    ```  
  
 <span data-ttu-id="77adf-151">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="77adf-151">For more information, see:</span></span>  
  
-   [<span data-ttu-id="77adf-152">sp_add_job &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="77adf-152">sp_add_job &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql)  
  
-   [<span data-ttu-id="77adf-153">sp_add_jobstep &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="77adf-153">sp_add_jobstep &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)  
  
-   [<span data-ttu-id="77adf-154">sp_add_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="77adf-154">sp_add_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql)  
  
-   [<span data-ttu-id="77adf-155">sp_attach_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="77adf-155">sp_attach_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql)  
  
-   [<span data-ttu-id="77adf-156">&#41;&#40;Transact-SQL de sp_add_jobserver</span><span class="sxs-lookup"><span data-stu-id="77adf-156">sp_add_jobserver &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql)  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMOProcedure"></a><span data-ttu-id="77adf-157">Usando SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="77adf-157">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="77adf-158">**Para criar um trabalho do SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="77adf-158">**To create a SQL Server Agent job**</span></span>  
  
 <span data-ttu-id="77adf-159">Chame o método `Create` da classe `Job` usando uma linguagem de programação da sua escolha, como o Visual Basic, o Visual C# ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77adf-159">Call the `Create` method of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="77adf-160">Para obter um código de exemplo, consulte [Agendamento de tarefas administrativas automáticas no SQL Server Agent](sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="77adf-160">For example code, see [Scheduling Automatic Administrative Tasks in SQL Server Agent](sql-server-agent.md).</span></span>  
  
##  <a name="SSMSProc2"></a>  
