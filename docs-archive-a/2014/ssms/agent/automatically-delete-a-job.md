---
title: Excluir um trabalho automaticamente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- dropping jobs
- SQL Server Agent jobs, removing
- automatic job removal
- jobs [SQL Server Agent], deleting
- deleting jobs
- removing jobs
ms.assetid: 92dbb6da-5919-4bde-9354-d454e9ea3da0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 07a10ec4a31d553a548bfecdcba426e3b46a1782
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575551"
---
# <a name="automatically-delete-a-job"></a><span data-ttu-id="0930d-102">Automatically Delete a Job</span><span class="sxs-lookup"><span data-stu-id="0930d-102">Automatically Delete a Job</span></span>
  <span data-ttu-id="0930d-103">Este tópico descreve como configurar o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] para excluir trabalhos automaticamente quando eles obtiverem êxito, falharem ou forem concluídos usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="0930d-103">This topic describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to automatically delete jobs when they succeed, fail, or complete by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="0930d-104">As respostas de trabalho asseguram que os administradores de banco de dados saibam quando os trabalhos são concluídos e a frequência com que são executados.</span><span class="sxs-lookup"><span data-stu-id="0930d-104">Job responses ensure that database administrators know when jobs complete and how frequently they run.</span></span> <span data-ttu-id="0930d-105">São respostas de trabalho típicas:</span><span class="sxs-lookup"><span data-stu-id="0930d-105">Typical job responses include:</span></span>  
  
-   <span data-ttu-id="0930d-106">Notificar o operador por meio de email, pager eletrônico ou uma mensagem **net send** .</span><span class="sxs-lookup"><span data-stu-id="0930d-106">Notifying the operator by using e-mail, electronic paging, or a **net send** message.</span></span>  
  
     <span data-ttu-id="0930d-107">Use uma dessas respostas de trabalho se o operador tiver de executar uma ação de acompanhamento.</span><span class="sxs-lookup"><span data-stu-id="0930d-107">Use one of these job responses if the operator must perform a follow-up action.</span></span> <span data-ttu-id="0930d-108">Por exemplo, se um trabalho de backup for concluído com êxito, o operador deverá ser notificado para remover a fita de backup e armazená-la em local seguro.</span><span class="sxs-lookup"><span data-stu-id="0930d-108">For example, if a backup job completes successfully, the operator must be notified to remove the backup tape and store it in a safe location.</span></span>  
  
-   <span data-ttu-id="0930d-109">Gravar uma mensagem de evento no log de aplicativos do Windows.</span><span class="sxs-lookup"><span data-stu-id="0930d-109">Writing an event message to the Windows application log.</span></span>  
  
     <span data-ttu-id="0930d-110">Essa resposta só pode ser utilizada para trabalhos que falharam.</span><span class="sxs-lookup"><span data-stu-id="0930d-110">You can use this response only for failed jobs.</span></span>  
  
-   <span data-ttu-id="0930d-111">Excluir o trabalho automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0930d-111">Automatically deleting the job.</span></span>  
  
     <span data-ttu-id="0930d-112">Use essa resposta de trabalho se você tiver certeza de que não precisará reexecutar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="0930d-112">Use this job response if you are certain that you do not need to rerun this job.</span></span>  
  
 <span data-ttu-id="0930d-113">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="0930d-113">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0930d-114">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="0930d-114">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0930d-115">Segurança</span><span class="sxs-lookup"><span data-stu-id="0930d-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0930d-116">**Para especificar respostas de trabalho, usando:**</span><span class="sxs-lookup"><span data-stu-id="0930d-116">**To specify job responses, using:**</span></span>  
  
     [<span data-ttu-id="0930d-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0930d-117">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="0930d-118">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="0930d-118">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0930d-119">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="0930d-119">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0930d-120">Segurança</span><span class="sxs-lookup"><span data-stu-id="0930d-120">Security</span></span>  
 <span data-ttu-id="0930d-121">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="0930d-121">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="0930d-122">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0930d-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-automatically-delete-a-job"></a><span data-ttu-id="0930d-123">Para excluir um trabalho automaticamente</span><span class="sxs-lookup"><span data-stu-id="0930d-123">To automatically delete a job</span></span>  
  
1.  <span data-ttu-id="0930d-124">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="0930d-124">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="0930d-125">Expanda **SQL Server Agent**, expanda **Trabalhos**, clique com o botão direito do mouse no trabalho que deseja editar e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="0930d-125">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to edit, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="0930d-126">Selecione a página **Notificações** .</span><span class="sxs-lookup"><span data-stu-id="0930d-126">Select the **Notifications** page.</span></span>  
  
4.  <span data-ttu-id="0930d-127">Marque **Excluir trabalho automaticamente**e siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="0930d-127">Check **Automatically delete job**, and choose one of the following:</span></span>  
  
    -   <span data-ttu-id="0930d-128">Clique em **Quando o trabalho for bem-sucedido** para excluir o status do trabalho quando ele for concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="0930d-128">Click **When the job succeeds** to delete the job status when it has completed successfully.</span></span>  
  
    -   <span data-ttu-id="0930d-129">Clique em **Quando o trabalho falhar** para excluir o trabalho quando ele não puder ser concluído.</span><span class="sxs-lookup"><span data-stu-id="0930d-129">Click **When the job fails** to delete the job when it has completed unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="0930d-130">Clique em **Quando o trabalho for concluído** para excluir o trabalho independentemente de seu status de conclusão.</span><span class="sxs-lookup"><span data-stu-id="0930d-130">Click **When the job completes** to delete the job regardless of completion status.</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="0930d-131">Usando SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="0930d-131">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="0930d-132">**Para excluir um trabalho automaticamente**</span><span class="sxs-lookup"><span data-stu-id="0930d-132">**To automatically delete a job**</span></span>  
  
 <span data-ttu-id="0930d-133">Use a propriedade `DeleteLevel` da classe `Job` usando uma linguagem de programação da sua escolha, como o Visual Basic, o Visual C# ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0930d-133">Use the `DeleteLevel` property of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="0930d-134">Para obter mais informações, veja [SMO (SQL Server Management Objects)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="0930d-134">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
  
  
