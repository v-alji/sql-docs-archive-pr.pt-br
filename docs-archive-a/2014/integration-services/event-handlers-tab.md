---
title: Guia manipuladores de eventos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.eventhandlerwindow.f1
ms.assetid: 94fc8916-8032-490c-b9d5-ded8b6217e49
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a5f25a9b0d602a3189feab797b7ef9c333decabb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574813"
---
# <a name="event-handlers-tab"></a><span data-ttu-id="74931-102">Guia Manipuladores de Eventos</span><span class="sxs-lookup"><span data-stu-id="74931-102">Event Handlers Tab</span></span>
  <span data-ttu-id="74931-103">Use a guia **Manipuladores de Eventos** do Designer [!INCLUDE[ssIS](../includes/ssis-md.md)] para criar um fluxo de controle em um pacote [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="74931-103">Use the **Event Handlers** tab of [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer to build a control flow in an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package.</span></span> <span data-ttu-id="74931-104">Um manipulador de eventos é executado em resposta a um evento criado pelo pacote ou por uma tarefa ou contêiner no pacote.</span><span class="sxs-lookup"><span data-stu-id="74931-104">An event handler runs in response to an event raised by the package or by a task or container in the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="74931-105">Opções</span><span class="sxs-lookup"><span data-stu-id="74931-105">Options</span></span>  
 <span data-ttu-id="74931-106">**Executável**</span><span class="sxs-lookup"><span data-stu-id="74931-106">**Executable**</span></span>  
 <span data-ttu-id="74931-107">Selecione o executável para o qual deseja criar um manipulador de eventos.</span><span class="sxs-lookup"><span data-stu-id="74931-107">Select the executable for which you want to build an event handler.</span></span> <span data-ttu-id="74931-108">O executável pode ser o pacote ou uma tarefa ou contêineres no pacote.</span><span class="sxs-lookup"><span data-stu-id="74931-108">The executable can be the package, or a task or containers in the package.</span></span>  
  
 <span data-ttu-id="74931-109">**Manipulador de eventos**</span><span class="sxs-lookup"><span data-stu-id="74931-109">**Event handler**</span></span>  
 <span data-ttu-id="74931-110">Selecione um tipo de manipulador de eventos.</span><span class="sxs-lookup"><span data-stu-id="74931-110">Select a type of event handler.</span></span> <span data-ttu-id="74931-111">Crie o manipulador de eventos, arrastando os itens da **Caixa de Ferramentas**.</span><span class="sxs-lookup"><span data-stu-id="74931-111">Create the event handler by dragging items from the **Toolbox**.</span></span>  
  
 <span data-ttu-id="74931-112">**Delete (excluir)**</span><span class="sxs-lookup"><span data-stu-id="74931-112">**Delete**</span></span>  
 <span data-ttu-id="74931-113">Selecione um manipulador de eventos e remova-o do pacote, clicando em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="74931-113">Select an event handler, and remove it from the package by clicking **Delete**.</span></span>  
  
 <span data-ttu-id="74931-114">**Clique aqui para criar um \<event handler name> para o executável \<executable name>**</span><span class="sxs-lookup"><span data-stu-id="74931-114">**Click here to create an \<event handler name> for the executable \<executable name>**</span></span>  
 <span data-ttu-id="74931-115">Clique para criar o manipulador de eventos.</span><span class="sxs-lookup"><span data-stu-id="74931-115">Click to create the event handler.</span></span>  
  
 <span data-ttu-id="74931-116">Crie o fluxo de controle arrastando os objetos gráficos que representam as tarefas e os contêiners [!INCLUDE[ssIS](../includes/ssis-md.md)] da **Caixa de Ferramentas** para a superfície de design da guia **Manipuladores de Eventos** e, em seguida, conectando os objetos usando as restrições de precedência para definir a sequência na qual eles serão executados.</span><span class="sxs-lookup"><span data-stu-id="74931-116">Create the control flow by dragging graphical objects that represent [!INCLUDE[ssIS](../includes/ssis-md.md)] tasks and containers from the **Toolbox** to the design surface of the **Event Handlers** tab, and then connecting the objects by using precedence constraints to define the sequence in which they run.</span></span>  
  
 <span data-ttu-id="74931-117">Além disso, para adicionar anotações, clique com o botão direito do mouse na superfície de design e, em seguida, no menu, clique em **Adicionar Anotação**.</span><span class="sxs-lookup"><span data-stu-id="74931-117">Additionally, to add annotations, right-click the design surface, and then on the menu, click **Add Annotation**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74931-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="74931-118">See Also</span></span>  
 <span data-ttu-id="74931-119">[Manipuladores de eventos do SSIS &#40;Integration Services&#41;](integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="74931-119">[Integration Services &#40;SSIS&#41; Event Handlers](integration-services-ssis-event-handlers.md) </span></span>  
 <span data-ttu-id="74931-120">[Fluxo de Controle](control-flow/control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="74931-120">[Control Flow](control-flow/control-flow.md) </span></span>  
 <span data-ttu-id="74931-121">[Designer SSIS](ssis-designer.md) </span><span class="sxs-lookup"><span data-stu-id="74931-121">[SSIS Designer](ssis-designer.md) </span></span>  
 [<span data-ttu-id="74931-122">Manipuladores de eventos do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="74931-122">Integration Services &#40;SSIS&#41; Event Handlers</span></span>](integration-services-ssis-event-handlers.md)  
  
  
