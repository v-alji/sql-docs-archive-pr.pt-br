---
title: Contêiner do Host da Tarefa | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.taskhostcontainer.f1
helpviewer_keywords:
- containers [Integration Services], Task Host
- Task Host container
ms.assetid: 7394a2c2-1b07-427d-b94a-9792e7783d35
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4429d564cea0f08d5c2408199a8f1837b38389b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582069"
---
# <a name="task-host-container"></a><span data-ttu-id="505e2-102">Contêiner Host da Tarefa</span><span class="sxs-lookup"><span data-stu-id="505e2-102">Task Host Container</span></span>
  <span data-ttu-id="505e2-103">O contêiner do host da tarefa encapsula uma única tarefa.</span><span class="sxs-lookup"><span data-stu-id="505e2-103">The task host container encapsulates a single task.</span></span> <span data-ttu-id="505e2-104">No Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)] , o host da tarefa não é configurado separadamente, ele é configurado quando você define as propriedades da tarefa que ele encapsula.</span><span class="sxs-lookup"><span data-stu-id="505e2-104">In [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, the task host is not configured separately; instead, it is configured when you set the properties of the task it encapsulates.</span></span> <span data-ttu-id="505e2-105">Para obter mais informações sobre as tarefas que os contêineres do host da tarefa encapsulam, consulte [Tarefas do Integration Services](integration-services-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="505e2-105">For more information about the tasks that the task host containers encapsulate, see [Integration Services Tasks](integration-services-tasks.md).</span></span>  
  
 <span data-ttu-id="505e2-106">Esse contêiner estende o uso de variáveis e manipuladores de eventos no nível de tarefa.</span><span class="sxs-lookup"><span data-stu-id="505e2-106">This container extends the use of variables and event handlers to the task level.</span></span> <span data-ttu-id="505e2-107">Para obter informações, consulte [Manipuladores de Eventos do Integration Services &#40;SSIS&#41;](../integration-services-ssis-event-handlers.md) e [Variáveis do Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="505e2-107">For more information, see [Integration Services &#40;SSIS&#41; Event Handlers](../integration-services-ssis-event-handlers.md) and [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md).</span></span>  
  
## <a name="configuration-of-the-task-host"></a><span data-ttu-id="505e2-108">Configuração do host da tarefa</span><span class="sxs-lookup"><span data-stu-id="505e2-108">Configuration of the Task Host</span></span>  
 <span data-ttu-id="505e2-109">Você pode definir as propriedades na janela **Propriedades** do [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="505e2-109">You can set properties in the **Properties** window of [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or programmatically.</span></span>  
  
 <span data-ttu-id="505e2-110">Para obter informações sobre como definir essas propriedades no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], consulte [Definir as propriedades de uma tarefa ou de um contêiner](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="505e2-110">For information about setting these properties in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
 <span data-ttu-id="505e2-111">Para obter informações sobre como definir essas propriedades programaticamente, consulte <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span><span class="sxs-lookup"><span data-stu-id="505e2-111">For information about programmatically setting these properties, see <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="505e2-112">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="505e2-112">Related Tasks</span></span>  
  
-   [<span data-ttu-id="505e2-113">Definir as propriedades de uma tarefa ou contêiner</span><span class="sxs-lookup"><span data-stu-id="505e2-113">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="505e2-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="505e2-114">See Also</span></span>  
 [<span data-ttu-id="505e2-115">Contêineres do Integration Services</span><span class="sxs-lookup"><span data-stu-id="505e2-115">Integration Services Containers</span></span>](integration-services-containers.md)  
  
  
