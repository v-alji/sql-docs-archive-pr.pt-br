---
title: Iniciar um trabalho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], starting
- SQL Server Agent jobs, starting
- starting jobs
ms.assetid: cec9f7f7-d0a7-4239-9dc5-a69c011ebaa0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4d5af895df518a915dacd953331b9139471933aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683892"
---
# <a name="start-a-job"></a><span data-ttu-id="6280c-102">Iniciar um trabalho</span><span class="sxs-lookup"><span data-stu-id="6280c-102">Start a Job</span></span>
  <span data-ttu-id="6280c-103">Este tópico descreve como iniciar a execução de um [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trabalho do Agent no usando o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] ou SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="6280c-103">This topic describes how to start running a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="6280c-104">Um trabalho é uma série especificada de ações que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent executa.</span><span class="sxs-lookup"><span data-stu-id="6280c-104">A job is a specified series of actions that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent performs.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6280c-105">Agent podem ser executados em um servidor local ou em vários servidores remotos.</span><span class="sxs-lookup"><span data-stu-id="6280c-105">Agent jobs can run on one local server or on multiple remote servers.</span></span>  
  
-   <span data-ttu-id="6280c-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="6280c-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6280c-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="6280c-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6280c-108">**Para iniciar um trabalho, usando:**</span><span class="sxs-lookup"><span data-stu-id="6280c-108">**To start a job, using:**</span></span>  
  
     [<span data-ttu-id="6280c-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6280c-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="6280c-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6280c-110">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="6280c-111">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="6280c-111">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6280c-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="6280c-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6280c-113">Segurança</span><span class="sxs-lookup"><span data-stu-id="6280c-113">Security</span></span>  
 <span data-ttu-id="6280c-114">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="6280c-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="6280c-115">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6280c-115">Using SQL Server Management Studio</span></span>  
  
### <a name="to-start-a-job"></a><span data-ttu-id="6280c-116">Para iniciar um trabalho</span><span class="sxs-lookup"><span data-stu-id="6280c-116">To start a job</span></span>  
  
1.  <span data-ttu-id="6280c-117">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="6280c-117">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="6280c-118">Expanda **SQL Server Agent** e expanda **Trabalhos**.</span><span class="sxs-lookup"><span data-stu-id="6280c-118">Expand **SQL Server Agent,** and expand **Jobs**.</span></span> <span data-ttu-id="6280c-119">Segundo o modo pelo qual você queira que o trabalho seja iniciado, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="6280c-119">Depending on how you want the job to start, do one of the following:</span></span>  
  
    -   <span data-ttu-id="6280c-120">Se estiver trabalhando em um único servidor, em um servidor de destino ou executando um trabalho de servidor local em um servidor mestre, clique com o botão direito do mouse no trabalho que deseja iniciar e, em seguida, clique em **Iniciar Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="6280c-120">If you are working on a single server, or working on a target server, or running a local server job on a master server, right-click the job you want to start, and then click **Start Job**.</span></span>  
  
    -   <span data-ttu-id="6280c-121">Se desejar iniciar vários trabalhos, clique com o botão direito do mouse em **Monitor de Atividade do Trabalho**e clique em **Exibir Atividade do Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="6280c-121">If you want to start multiple jobs, right-click **Job Activity Monitor**, and then click **View Job Activity**.</span></span> <span data-ttu-id="6280c-122">No Monitor de Atividade do Trabalho, você pode selecionar vários trabalhos, clicar com o botão direito do mouse na seleção e clicar em **Iniciar Trabalhos**.</span><span class="sxs-lookup"><span data-stu-id="6280c-122">In the Job Activity Monitor you can select multiple jobs, right-click your selection, and click **Start Jobs**.</span></span>  
  
    -   <span data-ttu-id="6280c-123">Se estiver trabalhando em um servidor mestre e quiser que todos os servidores de destino executem o trabalho simultaneamente, clique com o botão direito do mouse no trabalho que deseja iniciar, clique em **Iniciar Trabalho**e, em seguida, clique em **Iniciar em todos os servidores de destino**.</span><span class="sxs-lookup"><span data-stu-id="6280c-123">If you are working on a master server and want all targeted servers to run the job simultaneously, right-click the job you want to start, click **Start Job**, and then click **Start on all targeted servers**.</span></span>  
  
    -   <span data-ttu-id="6280c-124">Se estiver trabalhando em um servidor mestre e quiser especificar servidores de destino para o trabalho, clique com o botão direito do mouse no trabalho que deseja iniciar, clique em **Iniciar Trabalho**e, em seguida, clique em **Iniciar em servidores de destino específicos**.</span><span class="sxs-lookup"><span data-stu-id="6280c-124">If you are working on a master server and want to specify target servers for the job, right-click the job you want to start, click **Start Job**, and then click **Start on specific target servers**.</span></span> <span data-ttu-id="6280c-125">Na caixa de diálogo **Instruções Pós-Download** , marque a caixa de seleção **Estes servidores de destino** e selecione cada servidor de destino em que o trabalho deve ser executado.</span><span class="sxs-lookup"><span data-stu-id="6280c-125">In the **Post Download Instructions** dialog box, select the **These target servers** check box, and then select each target server on which this job should run.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="6280c-126">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6280c-126">Using Transact-SQL</span></span>  
  
### <a name="to-start-a-job"></a><span data-ttu-id="6280c-127">Para iniciar um trabalho</span><span class="sxs-lookup"><span data-stu-id="6280c-127">To start a job</span></span>  
  
1.  <span data-ttu-id="6280c-128">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6280c-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6280c-129">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="6280c-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6280c-130">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="6280c-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- starts a job named Weekly Sales Data Backup.    
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_start_job N'Weekly Sales Data Backup' ;  
    GO  
    ```  
  
 <span data-ttu-id="6280c-131">Para obter mais informações, consulte [sp_start_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-start-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6280c-131">For more information, see [sp_start_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-start-job-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="6280c-132">Usando SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="6280c-132">Using SQL Server Management Objects</span></span>  

### <a name="to-start-a-job"></a><span data-ttu-id="6280c-133">Para iniciar um trabalho</span><span class="sxs-lookup"><span data-stu-id="6280c-133">To start a job</span></span>
  
 <span data-ttu-id="6280c-134">Chame o método `Start` da classe `Job` usando uma linguagem de programação da sua escolha, como o Visual Basic, o Visual C# ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6280c-134">Call the `Start` method of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="6280c-135">Para obter mais informações, veja [SMO (SQL Server Management Objects)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="6280c-135">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
