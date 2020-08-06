---
title: Agendar um trabalho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- scheduling jobs [SQL Server]
- SQL Server Agent jobs, scheduling
- jobs [SQL Server Agent], scheduling
ms.assetid: f626390a-a3df-4970-b7a7-a0529e4a109c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1077766d6853ed7c029b8eefa76515c89ad861fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680278"
---
# <a name="schedule-a-job"></a><span data-ttu-id="5f40f-102">Schedule a Job</span><span class="sxs-lookup"><span data-stu-id="5f40f-102">Schedule a Job</span></span>
  <span data-ttu-id="5f40f-103">Este tópico descreve como agendar um trabalho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="5f40f-103">This topic describes how to schedule a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>  
  
-   <span data-ttu-id="5f40f-104">**Antes de começar:** ,</span><span class="sxs-lookup"><span data-stu-id="5f40f-104">**Before you begin:** ,</span></span>  
  
     [<span data-ttu-id="5f40f-105">Segurança</span><span class="sxs-lookup"><span data-stu-id="5f40f-105">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5f40f-106">**Para agendar um trabalho usando:**</span><span class="sxs-lookup"><span data-stu-id="5f40f-106">**To schedule a job, using:**</span></span>  
  
     [<span data-ttu-id="5f40f-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5f40f-107">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="5f40f-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5f40f-108">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="5f40f-109">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="5f40f-109">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5f40f-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="5f40f-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5f40f-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="5f40f-111">Security</span></span>  
 <span data-ttu-id="5f40f-112">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="5f40f-112">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="5f40f-113">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5f40f-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-and-attach-a-schedule-to-a-job"></a><span data-ttu-id="5f40f-114">Para criar e anexar uma agenda a um trabalho</span><span class="sxs-lookup"><span data-stu-id="5f40f-114">To create and attach a schedule to a job</span></span>  
  
1.  <span data-ttu-id="5f40f-115">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="5f40f-115">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="5f40f-116">Expanda **SQL Server Agent**, expanda **Trabalhos**, clique com o botão direito do mouse no trabalho que deseja agendar e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="5f40f-116">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to schedule, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="5f40f-117">Selecione a página **Agendas** e clique em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="5f40f-117">Select the **Schedules** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="5f40f-118">Na caixa **Nome** , digite um nome para a nova agenda.</span><span class="sxs-lookup"><span data-stu-id="5f40f-118">In the **Name** box, type a name for the new schedule.</span></span>  
  
5.  <span data-ttu-id="5f40f-119">Desmarque a caixa de seleção **Habilitado** se não quiser que a agenda entre em vigor imediatamente após a sua criação.</span><span class="sxs-lookup"><span data-stu-id="5f40f-119">Clear the **Enabled** check box if you do not want the schedule to take effect immediately following its creation.</span></span>  
  
6.  <span data-ttu-id="5f40f-120">Para **Tipo de Agenda**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="5f40f-120">For **Schedule Type**, select one of the following:</span></span>  
  
    -   <span data-ttu-id="5f40f-121">Clique em **Iniciar automaticamente quando o SQL Server Agent for iniciado** para iniciar o trabalho quando o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent for iniciado.</span><span class="sxs-lookup"><span data-stu-id="5f40f-121">Click **Start automatically when SQL Server Agent starts** to start the job when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service is started.</span></span>  
  
    -   <span data-ttu-id="5f40f-122">Clique em **Iniciar quando as CPUs estiverem ociosas** para iniciar o trabalho quando as CPUs atingirem uma condição de ociosidade.</span><span class="sxs-lookup"><span data-stu-id="5f40f-122">Click **Start whenever the CPUs become idle** to start the job when the CPUs reach an idle condition.</span></span>  
  
    -   <span data-ttu-id="5f40f-123">Clique em **Recorrente** se desejar que a agenda seja executada seguidamente.</span><span class="sxs-lookup"><span data-stu-id="5f40f-123">Click **Recurring** if you want a schedule to run repeatedly.</span></span> <span data-ttu-id="5f40f-124">Para definir a agenda recorrente, complete os grupos **Frequência**, **Frequência Diária**e **Duração** na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5f40f-124">To set the recurring schedule, complete the **Frequency**, **Daily Frequency**, and **Duration** groups on the dialog.</span></span>  
  
    -   <span data-ttu-id="5f40f-125">Clique em **Uma vez** se quiser que a agenda seja executada apenas uma vez.</span><span class="sxs-lookup"><span data-stu-id="5f40f-125">Click **One time** if you want the schedule to run only once.</span></span> <span data-ttu-id="5f40f-126">Para definir uma agenda executada apenas **Uma vez** , complete o grupo **Ocorrência única** na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5f40f-126">To set the **One time** schedule, complete the **One-time occurrence** group on the dialog.</span></span>  
  
#### <a name="to-attach-a-schedule-to-a-job"></a><span data-ttu-id="5f40f-127">Para anexar uma agenda a um trabalho</span><span class="sxs-lookup"><span data-stu-id="5f40f-127">To attach a schedule to a job</span></span>  
  
1.  <span data-ttu-id="5f40f-128">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="5f40f-128">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="5f40f-129">Expanda **SQL Server Agent**, expanda **Trabalhos**, clique com o botão direito do mouse no trabalho que deseja agendar e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="5f40f-129">Expand **SQL Server Agent**, expand **Jobs**, right-click the job that you want to schedule, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="5f40f-130">Selecione a página **Agendas** e clique em **Escolher**.</span><span class="sxs-lookup"><span data-stu-id="5f40f-130">Select the **Schedules** page, and then click **Pick**.</span></span>  
  
4.  <span data-ttu-id="5f40f-131">Selecione a agenda que você quer anexar e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5f40f-131">Select the schedule that you want to attach, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="5f40f-132">Na caixa de diálogo **Propriedades do Trabalho** , clique duas vezes na agenda anexada.</span><span class="sxs-lookup"><span data-stu-id="5f40f-132">In the **Job Properties** dialog box, double-click the attached schedule.</span></span>  
  
6.  <span data-ttu-id="5f40f-133">Verifique se a **Data de Início** está definida corretamente.</span><span class="sxs-lookup"><span data-stu-id="5f40f-133">Verify that **Start date** is set correctly.</span></span> <span data-ttu-id="5f40f-134">Se não estiver, estabeleça a data desejada para o início da agenda e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5f40f-134">If it is not, set the date when you want for the schedule to start, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="5f40f-135">Na caixa de diálogo **Propriedades do Trabalho** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5f40f-135">In the **Job Properties** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="5f40f-136">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5f40f-136">Using Transact-SQL</span></span>  
  
#### <a name="to-schedule-a-job"></a><span data-ttu-id="5f40f-137">Para agendar um trabalho</span><span class="sxs-lookup"><span data-stu-id="5f40f-137">To schedule a job</span></span>  
  
1.  <span data-ttu-id="5f40f-138">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f40f-138">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5f40f-139">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="5f40f-139">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5f40f-140">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="5f40f-140">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
    -- creates a schedule named NightlyJobs.   
    -- Jobs that use this schedule execute every day when the time on the server is 01:00.   
    EXEC sp_add_schedule  
        @schedule_name = N'NightlyJobs' ,  
        @freq_type = 4,  
        @freq_interval = 1,  
        @active_start_time = 010000 ;  
    GO  
    -- attaches the schedule to the job BackupDatabase  
    EXEC sp_attach_schedule  
       @job_name = N'BackupDatabase',  
       @schedule_name = N'NightlyJobs' ;  
    GO  
    ```  
  
 <span data-ttu-id="5f40f-141">Para obter mais informações, consulte [sp_add_schedule &#40;Transact-sql&#41;](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql) e [sp_attach_schedule &#40;transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5f40f-141">For more information, see [sp_add_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql) and [sp_attach_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="5f40f-142">Usando SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="5f40f-142">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="5f40f-143">Use a classe `JobSchedule` usando uma linguagem de programação da sua escolha, como o Visual Basic, o Visual C# ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f40f-143">Use the `JobSchedule` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="5f40f-144">Para obter mais informações, consulte[SMO (SQL Server Management Objects)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="5f40f-144">For more information, see[SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
