---
title: Criar um plano de manutenção | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- maintenance plans [SQL Server], creating
ms.assetid: a945cb65-ba7a-42f4-bbd9-6ec675745523
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3df0c1cd06427deb051a9c4214d03084b44c6f9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576364"
---
# <a name="create-a-maintenance-plan"></a><span data-ttu-id="e15bc-102">Criar um plano de manutenção</span><span class="sxs-lookup"><span data-stu-id="e15bc-102">Create a Maintenance Plan</span></span>
  <span data-ttu-id="e15bc-103">Este tópico descreve como criar um plano de manutenção de servidor único ou vários servidores no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e15bc-103">This topic describes how to create a single server or multiserver maintenance plan in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="e15bc-104">Usando o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], Há duas formas de criar esses planos de manutenção: por meio do Assistente de Plano de Manutenção ou da superfície de design.</span><span class="sxs-lookup"><span data-stu-id="e15bc-104">Using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], you can create these maintenance plans in one of two ways: by either using the Maintenance Plan Wizard or the design surface.</span></span> <span data-ttu-id="e15bc-105">O Assistente é melhor para criar planos de manutenção básicos, enquanto que criar planos usando a superfície de design permite utilizar fluxo de trabalho aprimorado.</span><span class="sxs-lookup"><span data-stu-id="e15bc-105">The Wizard is best for creating basic maintenance plans, while creating a plan using the design surface allows you to utilize enhanced workflow.</span></span>  
  
 <span data-ttu-id="e15bc-106">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="e15bc-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e15bc-107">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="e15bc-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e15bc-108">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="e15bc-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e15bc-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="e15bc-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e15bc-110">**Para criar um plano de manutenção usando:**</span><span class="sxs-lookup"><span data-stu-id="e15bc-110">**To create a maintenance plan, using:**</span></span>  
  
     [<span data-ttu-id="e15bc-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e15bc-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e15bc-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e15bc-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e15bc-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="e15bc-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e15bc-114">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="e15bc-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="e15bc-115">Para criar um plano de manutenção multisservidor, é necessário configurar um ambiente multisservidor contendo um servidor mestre e um ou mais servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="e15bc-115">To create a multiserver maintenance plan, a multiserver environment containing one master server and one or more target servers must be configured.</span></span> <span data-ttu-id="e15bc-116">Devem ser criados e mantidos planos de manutenção multisservidor no servidor mestre.</span><span class="sxs-lookup"><span data-stu-id="e15bc-116">Multiserver maintenance plans must be created and maintained on the master server.</span></span> <span data-ttu-id="e15bc-117">Os planos podem ser exibidos, mas não mantidos, nos servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="e15bc-117">These plans can be viewed, but not maintained, on target servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e15bc-118">Segurança</span><span class="sxs-lookup"><span data-stu-id="e15bc-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e15bc-119">Permissões</span><span class="sxs-lookup"><span data-stu-id="e15bc-119">Permissions</span></span>  
 <span data-ttu-id="e15bc-120">Para criar ou gerenciar planos de manutenção, é necessário ser membro da função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="e15bc-120">To create or manage Maintenance Plans, you must be a member of the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e15bc-121">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e15bc-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-maintenance-plan-using-the-maintenance-plan-wizard"></a><span data-ttu-id="e15bc-122">Para criar um plano de manutenção usando o Assistente de Plano de Manutenção</span><span class="sxs-lookup"><span data-stu-id="e15bc-122">To create a maintenance plan using the Maintenance Plan Wizard</span></span>  
  
1.  <span data-ttu-id="e15bc-123">No Pesquisador de Objetos, clique no sinal de adição para expandir o servidor em que você deseja criar um plano de manutenção.</span><span class="sxs-lookup"><span data-stu-id="e15bc-123">In Object Explorer, click the plus sign to expand the server where you want to create a maintenance plan.</span></span>  
  
2.  <span data-ttu-id="e15bc-124">Clique no sinal de adição para expandir a pasta **Gerenciamento** .</span><span class="sxs-lookup"><span data-stu-id="e15bc-124">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="e15bc-125">Clique com o botão direito do mouse na pasta **Planos de Manutenção** e selecione **Assistente de Plano de Manutenção**.</span><span class="sxs-lookup"><span data-stu-id="e15bc-125">Right-click the **Maintenance Plans** folder and select **Maintenance Plan Wizard**.</span></span>  
  
4.  <span data-ttu-id="e15bc-126">Siga as etapas do assistente para criar um plano de manutenção.</span><span class="sxs-lookup"><span data-stu-id="e15bc-126">Follow the steps of the wizard to create a maintenance plan.</span></span> <span data-ttu-id="e15bc-127">Para obter mais informações, consulte [Use the Maintenance Plan Wizard](use-the-maintenance-plan-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="e15bc-127">For more information, see [Use the Maintenance Plan Wizard](use-the-maintenance-plan-wizard.md).</span></span>  
  
#### <a name="to-create-a-maintenance-plan-using-the-design-surface"></a><span data-ttu-id="e15bc-128">Para criar um plano de manutenção usando a superfície de design</span><span class="sxs-lookup"><span data-stu-id="e15bc-128">To create a maintenance plan using the design surface</span></span>  
  
1.  <span data-ttu-id="e15bc-129">No Pesquisador de Objetos, clique no sinal de adição para expandir o servidor em que você deseja criar um plano de manutenção.</span><span class="sxs-lookup"><span data-stu-id="e15bc-129">In Object Explorer, click the plus sign to expand the server where you want to create a maintenance plan.</span></span>  
  
2.  <span data-ttu-id="e15bc-130">Clique no sinal de adição para expandir a pasta **Gerenciamento** .</span><span class="sxs-lookup"><span data-stu-id="e15bc-130">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="e15bc-131">Clique com o botão direito do mouse na pasta **Planos de Manutenção** e selecione **Novo Plano de Manutenção**.</span><span class="sxs-lookup"><span data-stu-id="e15bc-131">Right-click the **Maintenance Plans** folder and select **New Maintenance Plan**.</span></span>  
  
4.  <span data-ttu-id="e15bc-132">Crie um plano de manutenção, seguindo as etapas em [Criar um plano de manutenção &#40; Superfície de Design do Plano de Manutenção&#41;](create-a-maintenance-plan-maintenance-plan-design-surface.md).</span><span class="sxs-lookup"><span data-stu-id="e15bc-132">Create a maintenance plan following the steps in [Create a Maintenance Plan &#40;Maintenance Plan Design Surface&#41;](create-a-maintenance-plan-maintenance-plan-design-surface.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e15bc-133">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e15bc-133">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-maintenance-plan"></a><span data-ttu-id="e15bc-134">Para criar um plano de manutenção</span><span class="sxs-lookup"><span data-stu-id="e15bc-134">To create a maintenance plan</span></span>  
  
1.  <span data-ttu-id="e15bc-135">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e15bc-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e15bc-136">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="e15bc-136">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e15bc-137">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="e15bc-137">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb;  
    GO  
    --  Adds a new job, executed by the SQL Server Agent service, called "HistoryCleanupTask_1".  
    EXEC dbo.sp_add_job  
       @job_name = N'HistoryCleanupTask_1',   
       @enabled = 1,   
       @description = N'Clean up old task history' ;   
    GO  
    -- Adds a job step for reorganizing all of the indexes in the HumanResources.Employee table to the HistoryCleanupTask_1 job.   
    EXEC dbo.sp_add_jobstep  
        @job_name = N'HistoryCleanupTask_1',   
        @step_name = N'Reorganize all indexes on HumanResources.Employee table',   
        @subsystem = N'TSQL',   
        @command = N'USE AdventureWorks2012  
    GO  
    ALTER INDEX AK_Employee_LoginID ON HumanResources.Employee REORGANIZE WITH ( LOB_COMPACTION = ON )   
    GO  
    USE AdventureWorks2012  
    GO  
    ALTER INDEX AK_Employee_NationalIDNumber ON HumanResources.Employee REORGANIZE WITH ( LOB_COMPACTION = ON )   
    GO  
    USE AdventureWorks2012  
    GO  
    ALTER INDEX AK_Employee_rowguid ON HumanResources.Employee REORGANIZE WITH ( LOB_COMPACTION = ON )   
    GO  
    USE AdventureWorks2012  
    GO  
    ALTER INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee REORGANIZE WITH ( LOB_COMPACTION = ON )   
    GO  
    USE AdventureWorks2012  
    GO  
    ALTER INDEX IX_Employee_OrganizationNode ON HumanResources.Employee REORGANIZE WITH ( LOB_COMPACTION = ON )   
    GO  
    USE AdventureWorks2012  
    GO  
    ALTER INDEX PK_Employee_BusinessEntityID ON HumanResources.Employee REORGANIZE WITH ( LOB_COMPACTION = ON )   
    GO  
    ',   
        @retry_attempts = 5,   
        @retry_interval = 5 ;   
    GO  
    -- Creates a schedule named RunOnce that executes every day when the time on the server is 23:00.   
    EXEC dbo.sp_add_schedule  
        @schedule_name = N'RunOnce',   
        @freq_type = 4,   
        @freq_interval = 1,   
        @active_start_time = 233000 ;   
    GO  
    -- Attaches the RunOnce schedule to the job HistoryCleanupTask_1.   
    EXEC sp_attach_schedule  
       @job_name = N'HistoryCleanupTask_1'  
       @schedule_name = N'RunOnce' ;   
    GO  
  
    ```  
  
 <span data-ttu-id="e15bc-138">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="e15bc-138">For more information, see:</span></span>  
  
-   [<span data-ttu-id="e15bc-139">sp_add_job &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e15bc-139">sp_add_job &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql)  
  
-   [<span data-ttu-id="e15bc-140">sp_add_jobstep &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e15bc-140">sp_add_jobstep &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)  
  
-   [<span data-ttu-id="e15bc-141">sp_add_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e15bc-141">sp_add_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql)  
  
-   [<span data-ttu-id="e15bc-142">sp_attach_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e15bc-142">sp_attach_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql)  
  
  
