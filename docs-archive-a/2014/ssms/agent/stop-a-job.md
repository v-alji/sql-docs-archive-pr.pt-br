---
title: Parar um trabalho   Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], stopping
- SQL Server Agent jobs, stopping
- stopping jobs
ms.assetid: 4249328a-24d8-4284-9d1d-7d04ed90e3d7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 78986e85dd8ee808f5fb621182d903a94bbc5eb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678559"
---
# <a name="stop-a-job"></a><span data-ttu-id="6648d-102">Stop a Job</span><span class="sxs-lookup"><span data-stu-id="6648d-102">Stop a Job</span></span>
  <span data-ttu-id="6648d-103">Este tópico descreve como interromper um [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trabalho do Agent.</span><span class="sxs-lookup"><span data-stu-id="6648d-103">This topic describes how to stop a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span> <span data-ttu-id="6648d-104">Um trabalho é uma série especificada de ações que o SQL Server Agent executa.</span><span class="sxs-lookup"><span data-stu-id="6648d-104">A job is a specified series of actions that SQL Server Agent performs.</span></span>  
  
-   <span data-ttu-id="6648d-105">**Antes de começar:** ,</span><span class="sxs-lookup"><span data-stu-id="6648d-105">**Before you begin:**  ,</span></span>  
  
     [<span data-ttu-id="6648d-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="6648d-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="6648d-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="6648d-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6648d-108">**Para interromper um trabalho usando:**</span><span class="sxs-lookup"><span data-stu-id="6648d-108">**To stop a job, using:**</span></span>  
  
     [<span data-ttu-id="6648d-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6648d-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="6648d-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6648d-110">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="6648d-111">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="6648d-111">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6648d-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="6648d-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6648d-113">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="6648d-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="6648d-114">Se um trabalho estiver executando no momento uma etapa do tipo **CmdExec** ou **PowerShell**, o processo em execução (por exemplo, MyProgram.exe) será forçado a terminar prematuramente.</span><span class="sxs-lookup"><span data-stu-id="6648d-114">If a job is currently executing a step of type **CmdExec** or **PowerShell**, the process that is being run (for example, MyProgram.exe) is forced to end prematurely.</span></span> <span data-ttu-id="6648d-115">Isso pode causar comportamento imprevisível, como manter abertos os arquivos em uso pelo processo.</span><span class="sxs-lookup"><span data-stu-id="6648d-115">This can cause unpredictable behavior, such as files that are being used by the process being held open.</span></span>  
  
-   <span data-ttu-id="6648d-116">Em caso de trabalho multisservidor, uma instrução STOP para o trabalho é postada em todos os servidores de destino do trabalho.</span><span class="sxs-lookup"><span data-stu-id="6648d-116">For a multiserver job, a STOP instruction for the job is posted to all target servers of the job.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6648d-117">Segurança</span><span class="sxs-lookup"><span data-stu-id="6648d-117">Security</span></span>  
 <span data-ttu-id="6648d-118">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="6648d-118">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="6648d-119">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6648d-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-stop-a-job"></a><span data-ttu-id="6648d-120">Para interromper um trabalho</span><span class="sxs-lookup"><span data-stu-id="6648d-120">To stop a job</span></span>  
  
1.  <span data-ttu-id="6648d-121">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="6648d-121">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="6648d-122">Expanda **SQL Server Agent**, expanda **Trabalhos**, clique com o botão direito do mouse no trabalho que deseja interromper e clique em **Parar Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="6648d-122">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to stop, and then click **Stop Job**.</span></span>  
  
3.  <span data-ttu-id="6648d-123">Se desejar interromper vários trabalhos, clique com o botão direito do mouse em **Monitor de Atividade do Trabalho**e, depois, clique em **Exibir Atividade do Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="6648d-123">If you want to stop multiple jobs, right-click **Job Activity Monitor**, and then click **View Job Activity**.</span></span> <span data-ttu-id="6648d-124">No Monitor de Atividade do Trabalho, selecione os trabalhos que você deseja interromper, clique com o botão direito do mouse em sua seleção e, depois, clique em **Parar Trabalhos**.</span><span class="sxs-lookup"><span data-stu-id="6648d-124">In the Job Activity Monitor, select the jobs you want to stop, right-click your selection, and then click **Stop Jobs**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="6648d-125">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6648d-125">Using Transact-SQL</span></span>  
  
### <a name="to-stop-a-job"></a><span data-ttu-id="6648d-126">Para interromper um trabalho</span><span class="sxs-lookup"><span data-stu-id="6648d-126">To stop a job</span></span>  
  
1.  <span data-ttu-id="6648d-127">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6648d-127">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6648d-128">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="6648d-128">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6648d-129">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="6648d-129">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- stops a job named Weekly Sales Data Backup  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_stop_job  
        N'Weekly Sales Data Backup' ;  
    GO  
    ```  
  
 <span data-ttu-id="6648d-130">Para obter mais informações, consulte [sp_stop_job &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-stop-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6648d-130">For more information, see [sp_stop_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-stop-job-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="6648d-131">Usando SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="6648d-131">Using SQL Server Management Objects</span></span>  

### <a name="to-stop-a-job"></a><span data-ttu-id="6648d-132">Para interromper um trabalho</span><span class="sxs-lookup"><span data-stu-id="6648d-132">To stop a job</span></span>
  
 <span data-ttu-id="6648d-133">Chame o método `Stop` da classe `Job` usando uma linguagem de programação da sua escolha, como o Visual Basic, o Visual C# ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6648d-133">Call the `Stop` method of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="6648d-134">Para obter mais informações, veja [SMO (SQL Server Management Objects)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="6648d-134">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
