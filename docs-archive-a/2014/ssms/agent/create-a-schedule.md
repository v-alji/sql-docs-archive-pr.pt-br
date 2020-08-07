---
title: Criar uma agenda | Microsoft Docs
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
- schedules [SQL Server], jobs
ms.assetid: 8c7ef3b3-c06d-4a27-802d-ed329dc86ef3
author: stevestein
ms.author: sstein
ms.openlocfilehash: ac71a61163dceb06697b61ef24fce2117d57cf2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582268"
---
# <a name="create-a-schedule"></a><span data-ttu-id="2da04-102">Create a Schedule</span><span class="sxs-lookup"><span data-stu-id="2da04-102">Create a Schedule</span></span>
  <span data-ttu-id="2da04-103">Você pode criar uma agenda para trabalhos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], ou SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="2da04-103">You can create a schedule for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
-   <span data-ttu-id="2da04-104">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="2da04-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2da04-105">Segurança</span><span class="sxs-lookup"><span data-stu-id="2da04-105">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2da04-106">**Para criar uma agenda, usando:**</span><span class="sxs-lookup"><span data-stu-id="2da04-106">**To create a schedule, using:**</span></span>  
  
     [<span data-ttu-id="2da04-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2da04-107">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="2da04-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2da04-108">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="2da04-109">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="2da04-109">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2da04-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="2da04-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2da04-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="2da04-111">Security</span></span>  
 <span data-ttu-id="2da04-112">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="2da04-112">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="2da04-113">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2da04-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-schedule"></a><span data-ttu-id="2da04-114">Para criar uma agenda</span><span class="sxs-lookup"><span data-stu-id="2da04-114">To create a schedule</span></span>  
  
1.  <span data-ttu-id="2da04-115">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="2da04-115">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="2da04-116">Expanda **SQL Server Agent**, clique com o botão direito do mouse em **Trabalhos**e selecione **Gerenciar Agendas**.</span><span class="sxs-lookup"><span data-stu-id="2da04-116">Expand **SQL Server Agent**, right-click **Jobs**, and select **Manage Schedules**.</span></span>  
  
3.  <span data-ttu-id="2da04-117">Na caixa de diálogo **Gerenciar Agendas** , clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="2da04-117">In the **Manage Schedules** dialog box, click **New**.</span></span>  
  
4.  <span data-ttu-id="2da04-118">Na caixa **Nome** , digite um nome para a nova agenda.</span><span class="sxs-lookup"><span data-stu-id="2da04-118">In the **Name** box, type a name for the new schedule.</span></span>  
  
5.  <span data-ttu-id="2da04-119">Se você não quiser que a agenda tenha efeito imediatamente após a criação, desmarque a caixa de seleção **Habilitado** .</span><span class="sxs-lookup"><span data-stu-id="2da04-119">If you do not want the schedule to take effect immediately after it has been created, clear the **Enabled** check box.</span></span>  
  
6.  <span data-ttu-id="2da04-120">Para **Tipo de Agenda**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="2da04-120">For **Schedule Type**, select one of the following:</span></span>  
  
    -   <span data-ttu-id="2da04-121">Para iniciar o trabalho quando as CPUs atingem uma condição ociosa, clique em **Iniciar quando as CPUs estiverem ociosas**.</span><span class="sxs-lookup"><span data-stu-id="2da04-121">To start the job when the CPUs reach an idle condition, click **Start whenever the CPUs become idle**.</span></span>  
  
    -   <span data-ttu-id="2da04-122">Clique em **Recorrente**se desejar que a agenda seja executada repetidamente.</span><span class="sxs-lookup"><span data-stu-id="2da04-122">If you want a schedule to run repeatedly, click **Recurring**.</span></span> <span data-ttu-id="2da04-123">Para definir a agenda recorrente, complete os grupos **Frequência**, **Frequência Diária**e **Duração** na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2da04-123">To set the recurring schedule, complete the **Frequency**, **Daily Frequency**, and **Duration** groups on the dialog.</span></span>  
  
    -   <span data-ttu-id="2da04-124">Para que a agenda seja executada somente uma vez, clique em **Uma vez**.</span><span class="sxs-lookup"><span data-stu-id="2da04-124">If you want the schedule to run only one time, click **One time**.</span></span> <span data-ttu-id="2da04-125">Para definir a agenda **Uma vez** , conclua o grupo **Ocorrência única** na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2da04-125">To set the **One time** schedule, complete the **One-time occurrence** group on the dialog box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="2da04-126">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2da04-126">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-schedule"></a><span data-ttu-id="2da04-127">Para criar uma agenda</span><span class="sxs-lookup"><span data-stu-id="2da04-127">To create a schedule</span></span>  
  
1.  <span data-ttu-id="2da04-128">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2da04-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2da04-129">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="2da04-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2da04-130">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="2da04-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a schedule named RunOnce.   
    -- The schedule runs one time, at 23:30 on the day that the schedule is created.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_schedule  
        @schedule_name = N'RunOnce',  
        @freq_type = 1,  
        @active_start_time = 233000 ;  
  
    GO  
    ```  
  
 <span data-ttu-id="2da04-131">Para obter mais informações, consulte [sp_add_schedule &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2da04-131">For more information, see [sp_add_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="2da04-132">Usando SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="2da04-132">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="2da04-133">**Para criar uma agenda**</span><span class="sxs-lookup"><span data-stu-id="2da04-133">**To create a schedule**</span></span>  
  
 <span data-ttu-id="2da04-134">Use a classe `JobSchedule` usando uma linguagem de programação da sua escolha, como o Visual Basic, o Visual C# ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2da04-134">Use the `JobSchedule` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="2da04-135">Para obter mais informações, veja [SMO (SQL Server Management Objects)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="2da04-135">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
