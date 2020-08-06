---
title: Gravar o status do trabalho no log de aplicativos do Windows | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- status information [SQL Server], jobs
- SQL Server Agent jobs, status
- writing job status to log
- jobs [SQL Server Agent], status
- logs [SQL Server], jobs
ms.assetid: 3b813702-8f61-40ec-bf3b-ce9deb7e68be
author: stevestein
ms.author: sstein
ms.openlocfilehash: 67bdd7948d1722e49976d5e48b571c684431cd1c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682057"
---
# <a name="write-the-job-status-to-the-windows-application-log"></a><span data-ttu-id="ca160-102">Write the Job Status to the Windows Application Log</span><span class="sxs-lookup"><span data-stu-id="ca160-102">Write the Job Status to the Windows Application Log</span></span>
  <span data-ttu-id="ca160-103">Este tópico descreve como configurar [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o Agent no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] para gravar o status do trabalho no log de eventos de aplicativos do Windows usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , o [!INCLUDE[tsql](../../includes/tsql-md.md)] ou o SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="ca160-103">This topic describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to write job status to the Windows application event log by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="ca160-104">As respostas de trabalho asseguram que os administradores de banco de dados saibam quando os trabalhos são concluídos e a frequência com que são executados.</span><span class="sxs-lookup"><span data-stu-id="ca160-104">Job responses ensure that database administrators know when jobs complete and how frequently they run.</span></span> <span data-ttu-id="ca160-105">São respostas de trabalho típicas:</span><span class="sxs-lookup"><span data-stu-id="ca160-105">Typical job responses include:</span></span>  
  
-   <span data-ttu-id="ca160-106">Notificar o operador por meio de email, pager eletrônico ou uma mensagem **net send** .</span><span class="sxs-lookup"><span data-stu-id="ca160-106">Notifying the operator by using e-mail, electronic paging, or a **net send** message.</span></span> <span data-ttu-id="ca160-107">Use uma dessas respostas de trabalho se o operador tiver de executar uma ação de acompanhamento.</span><span class="sxs-lookup"><span data-stu-id="ca160-107">Use one of these job responses if the operator must perform a follow-up action.</span></span> <span data-ttu-id="ca160-108">Por exemplo, se um trabalho de backup for concluído com êxito, o operador deverá ser notificado para remover a fita de backup e armazená-la em local seguro.</span><span class="sxs-lookup"><span data-stu-id="ca160-108">For example, if a backup job completes successfully, the operator must be notified to remove the backup tape and store it in a safe location.</span></span>  
  
-   <span data-ttu-id="ca160-109">Gravar uma mensagem de evento no log de aplicativos do Windows.</span><span class="sxs-lookup"><span data-stu-id="ca160-109">Writing an event message to the Windows application log.</span></span> <span data-ttu-id="ca160-110">Essa resposta só pode ser utilizada para trabalhos que falharam.</span><span class="sxs-lookup"><span data-stu-id="ca160-110">You can use this response only for failed jobs.</span></span>  
  
-   <span data-ttu-id="ca160-111">Excluir o trabalho automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ca160-111">Automatically deleting the job.</span></span> <span data-ttu-id="ca160-112">Use essa resposta de trabalho se você tiver certeza de que não precisará reexecutar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="ca160-112">Use this job response if you are certain that you do not need to rerun this job.</span></span>  
  
 <span data-ttu-id="ca160-113">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="ca160-113">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ca160-114">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="ca160-114">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ca160-115">Segurança</span><span class="sxs-lookup"><span data-stu-id="ca160-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ca160-116">**Para gravar o status do trabalho no log de aplicativos do Windows usando:**</span><span class="sxs-lookup"><span data-stu-id="ca160-116">**To write the job status to the Windows application log, using:**</span></span>  
  
     [<span data-ttu-id="ca160-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ca160-117">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="ca160-118">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="ca160-118">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ca160-119">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="ca160-119">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ca160-120">Segurança</span><span class="sxs-lookup"><span data-stu-id="ca160-120">Security</span></span>  
 <span data-ttu-id="ca160-121">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="ca160-121">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="ca160-122">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ca160-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-write-job-status-to-the-windows-application-log"></a><span data-ttu-id="ca160-123">Para gravar o status do trabalho no log de aplicativos do Windows</span><span class="sxs-lookup"><span data-stu-id="ca160-123">To write job status to the Windows application log</span></span>  
  
1.  <span data-ttu-id="ca160-124">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="ca160-124">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="ca160-125">Expanda **SQL Server Agent**, expanda **Trabalhos**, clique com o botão direito do mouse no trabalho que deseja editar e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="ca160-125">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to edit, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="ca160-126">Selecione a página **Notificações** .</span><span class="sxs-lookup"><span data-stu-id="ca160-126">Select the **Notifications** page.</span></span>  
  
4.  <span data-ttu-id="ca160-127">Marque **Gravar no log de eventos de aplicativos do Windows**e siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="ca160-127">Check **Write to Windows application event log**, and choose one of the following:</span></span>  
  
    -   <span data-ttu-id="ca160-128">Clique em**Quando o trabalho for bem-sucedido**para registrar o status do trabalho quando ele for concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="ca160-128">Click**When the job succeeds**to log the job status when the job completes successfully.</span></span>  
  
    -   <span data-ttu-id="ca160-129">Clique em**Quando o trabalho falhar**para registrar o status do trabalho quando ele não for concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="ca160-129">Click**When the job fails**to log the job status when the job completes unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="ca160-130">Clique em**Quando o trabalho for concluído** para registrar o status do trabalho independentemente do status de conclusão.</span><span class="sxs-lookup"><span data-stu-id="ca160-130">Click**When the job completes** to log the job status regardless of completion status.</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="ca160-131">Usando SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="ca160-131">Using SQL Server Management Objects</span></span>  

### <a name="to-write-job-status-to-the-windows-application-log"></a><span data-ttu-id="ca160-132">Para gravar o status do trabalho no log de aplicativos do Windows</span><span class="sxs-lookup"><span data-stu-id="ca160-132">To write job status to the Windows application log</span></span>
  
 <span data-ttu-id="ca160-133">Chame a propriedade `EventLogLevel` da classe `Job` usando uma linguagem de programação que você escolher, como o Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca160-133">Call the `EventLogLevel` property of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
  
 <span data-ttu-id="ca160-134">O código de exemplo a seguir define o trabalho para gerar uma entrada no log de eventos do sistema deve ser gerada quando a execução do trabalho for concluída.</span><span class="sxs-lookup"><span data-stu-id="ca160-134">The following code example sets the job to generate an operating system event log entry when the job execution finishes.</span></span>  
  
```powershell
$srv = new-object Microsoft.SqlServer.Management.Smo.Server("(local)")  
$jb = new-object Microsoft.SqlServer.Management.Smo.Agent.Job($srv.JobServer, "Test Job")  
$jb.EventLogLevel = [Microsoft.SqlServer.Management.Smo.Agent.CompletionAction]::Always  
```  
