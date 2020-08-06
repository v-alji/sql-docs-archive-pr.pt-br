---
title: Especificar respostas de trabalho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], responses
- SQL Server Agent jobs, responses
- actions [SQL Server Agent jobs]
- responding to jobs
ms.assetid: 050242e1-9b79-4ade-91a9-580707b9d2d9
author: stevestein
ms.author: sstein
ms.openlocfilehash: d41c5e1552a1ff16343bdb2c4e9feaafb51c5783
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678563"
---
# <a name="specify-job-responses"></a><span data-ttu-id="4d4d8-102">Especificar respostas de trabalho</span><span class="sxs-lookup"><span data-stu-id="4d4d8-102">Specify Job Responses</span></span>
  <span data-ttu-id="4d4d8-103">As respostas de trabalho especificam ações que o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent deve efetuar após a conclusão de um trabalho.</span><span class="sxs-lookup"><span data-stu-id="4d4d8-103">Job responses specify actions that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service will take after a job completes.</span></span> <span data-ttu-id="4d4d8-104">As respostas de trabalho asseguram que os administradores de banco de dados saibam quando os trabalhos são concluídos e a frequência com que são executados.</span><span class="sxs-lookup"><span data-stu-id="4d4d8-104">Job responses ensure that database administrators know when jobs complete and how frequently they run.</span></span> <span data-ttu-id="4d4d8-105">São respostas de trabalho típicas:</span><span class="sxs-lookup"><span data-stu-id="4d4d8-105">Typical job responses include:</span></span>  
  
-   <span data-ttu-id="4d4d8-106">Notificar o operador por meio de email, pager eletrônico ou uma mensagem **net send** .</span><span class="sxs-lookup"><span data-stu-id="4d4d8-106">Notifying the operator by using e-mail, electronic paging, or a **net send** message.</span></span>  
  
     <span data-ttu-id="4d4d8-107">Use uma dessas respostas de trabalho se o operador tiver de executar uma ação de acompanhamento.</span><span class="sxs-lookup"><span data-stu-id="4d4d8-107">Use one of these job responses if the operator must perform a follow-up action.</span></span> <span data-ttu-id="4d4d8-108">Por exemplo, se um trabalho de backup for concluído com êxito, o operador deverá ser notificado para remover a fita de backup e armazená-la em local seguro.</span><span class="sxs-lookup"><span data-stu-id="4d4d8-108">For example, if a backup job completes successfully, the operator must be notified to remove the backup tape and store it in a safe location.</span></span>  
  
-   <span data-ttu-id="4d4d8-109">Gravar uma mensagem de evento no log de aplicativos do Windows.</span><span class="sxs-lookup"><span data-stu-id="4d4d8-109">Writing an event message to the Windows application log.</span></span>  
  
     <span data-ttu-id="4d4d8-110">Essa resposta só pode ser utilizada para trabalhos que falharam.</span><span class="sxs-lookup"><span data-stu-id="4d4d8-110">You can use this response only for failed jobs.</span></span>  
  
-   <span data-ttu-id="4d4d8-111">Excluir o trabalho automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4d4d8-111">Automatically deleting the job.</span></span>  
  
     <span data-ttu-id="4d4d8-112">Use essa resposta de trabalho se você tiver certeza de que não precisará reexecutar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="4d4d8-112">Use this job response if you are certain that you do not need to rerun this job.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="4d4d8-113">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="4d4d8-113">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4d4d8-114">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="4d4d8-114">**Description**</span></span>|<span data-ttu-id="4d4d8-115">**Tópico**</span><span class="sxs-lookup"><span data-stu-id="4d4d8-115">**Topic**</span></span>|  
|<span data-ttu-id="4d4d8-116">Descreve como notificar um operador sobre o status do trabalho.</span><span class="sxs-lookup"><span data-stu-id="4d4d8-116">Describes how to notify an operator of job status.</span></span>|[<span data-ttu-id="4d4d8-117">Notify an Operator of Job Status</span><span class="sxs-lookup"><span data-stu-id="4d4d8-117">Notify an Operator of Job Status</span></span>](notify-an-operator-of-job-status.md)|  
|<span data-ttu-id="4d4d8-118">Descreve como gravar o status do trabalho no log de aplicativos do Windows.</span><span class="sxs-lookup"><span data-stu-id="4d4d8-118">Describes how to write job status to the Windows application log.</span></span>|[<span data-ttu-id="4d4d8-119">Write the Job Status to the Windows Application Log</span><span class="sxs-lookup"><span data-stu-id="4d4d8-119">Write the Job Status to the Windows Application Log</span></span>](../../reporting-services/report-server/windows-application-log.md)|  
  
## <a name="see-also"></a><span data-ttu-id="4d4d8-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4d4d8-120">See Also</span></span>  
 [<span data-ttu-id="4d4d8-121">Monitorar e responder a eventos</span><span class="sxs-lookup"><span data-stu-id="4d4d8-121">Monitor and Respond to Events</span></span>](monitor-and-respond-to-events.md)  
  
  
