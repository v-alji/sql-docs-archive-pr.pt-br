---
title: Mecanismo de eventos estendidos do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- extended events [SQL Server], engine
ms.assetid: d74642a5-42b9-4a15-aa3d-f98bfe695050
author: rothja
ms.author: jroth
ms.openlocfilehash: ef11ac8e2cfaf39d2bca90f1d5d52439989ee327
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569462"
---
# <a name="sql-server-extended-events-engine"></a><span data-ttu-id="d3377-102">Mecanismo de eventos estendidos do SQL Server</span><span class="sxs-lookup"><span data-stu-id="d3377-102">SQL Server Extended Events Engine</span></span>
  <span data-ttu-id="d3377-103">O mecanismo de Eventos Estendidos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é uma coleção de serviços e objetos que:</span><span class="sxs-lookup"><span data-stu-id="d3377-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Extended Events engine is a collection of services and objects that:</span></span>  
  
-   <span data-ttu-id="d3377-104">Habilita a definição de eventos.</span><span class="sxs-lookup"><span data-stu-id="d3377-104">Enable the definition of events.</span></span>  
  
-   <span data-ttu-id="d3377-105">Habilita dados de evento de processamento.</span><span class="sxs-lookup"><span data-stu-id="d3377-105">Enable processing event data.</span></span>  
  
-   <span data-ttu-id="d3377-106">Gerencia serviços de eventos estendidos e objetos no sistema.</span><span class="sxs-lookup"><span data-stu-id="d3377-106">Manage Extended Events services and objects in the system.</span></span>  
  
-   <span data-ttu-id="d3377-107">Mantenha uma lista de sessões de eventos estendidos e gerencie o acesso àquela lista.</span><span class="sxs-lookup"><span data-stu-id="d3377-107">Maintain a list of Extended Events sessions and manage access to that list.</span></span>  
  
 <span data-ttu-id="d3377-108">O mecanismo de eventos estendidos não fornece qualquer evento ou ações que ocorram quando um evento é disparado.</span><span class="sxs-lookup"><span data-stu-id="d3377-108">The Extended Events engine itself does not provide any events or actions to take when an event fires.</span></span> <span data-ttu-id="d3377-109">Os processos que usam o mecanismo de evento estendido definem interação com o mecanismo.</span><span class="sxs-lookup"><span data-stu-id="d3377-109">The processes that use the Extended Events engine define interaction with the engine.</span></span> <span data-ttu-id="d3377-110">Estes processos adicionam pontos de evento e fornecem ações para que ocorram em resposta ao disparo do evento.</span><span class="sxs-lookup"><span data-stu-id="d3377-110">These processes add event points and supply the actions to take in response to event firing.</span></span>  
  
 <span data-ttu-id="d3377-111">A ilustração seguinte mostra uma exibição simplificada de uma sessão de eventos estendidos.</span><span class="sxs-lookup"><span data-stu-id="d3377-111">The following illustration shows a simplified view of an Extended Events session.</span></span> <span data-ttu-id="d3377-112">Para obter mais informações, consulte [Sessões de eventos estendidos do SQL Server](sql-server-extended-events-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="d3377-112">For more information, see [SQL Server Extended Events Sessions](sql-server-extended-events-sessions.md).</span></span>  
  
 <span data-ttu-id="d3377-113">![Arquitetura de eventos estendidos detalhada](../../database-engine/media/xearchitecturedetailed.gif "Arquitetura de eventos estendidos detalhada")</span><span class="sxs-lookup"><span data-stu-id="d3377-113">![Detailed extended events architecture](../../database-engine/media/xearchitecturedetailed.gif "Detailed extended events architecture")</span></span>  
  
 <span data-ttu-id="d3377-114">Observe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d3377-114">Note the following:</span></span>  
  
-   <span data-ttu-id="d3377-115">Cada processo do Windows pode ter um ou mais módulos (**processo Win32**, **módulo Win32**).</span><span class="sxs-lookup"><span data-stu-id="d3377-115">Each Windows process can have one or more modules (**Win32 process**, **Win32 module**).</span></span> <span data-ttu-id="d3377-116">Estes também são conhecidos como *binários* ou *módulos de executáveis*.</span><span class="sxs-lookup"><span data-stu-id="d3377-116">These are also known as *binaries* or *executable modules*.</span></span>  
  
-   <span data-ttu-id="d3377-117">Cada um dos módulos de processo do Windows pode conter um ou mais pacotes de eventos estendidos (**Pacote**) que contêm um ou mais objetos de eventos estendidos (**Tipo**, **Destino**, **Ação**, **Mapa**, **Predicado**e **Evento**).</span><span class="sxs-lookup"><span data-stu-id="d3377-117">Each of the Windows process modules can contain one or more Extended Events packages (**Package**), which contain one or more Extended Events objects (**Type**, **Target**, **Action**, **Map**, **Predicate**, and **Event**).</span></span>  
  
-   <span data-ttu-id="d3377-118">Dentro de um processo de host pode haver só uma instância do mecanismo de eventos estendidos (**Mecanismo de evento estendido**) que:</span><span class="sxs-lookup"><span data-stu-id="d3377-118">Inside a host process there can only be one instance of the Extended Events engine (**Extended event engine**), which:</span></span>  
  
    -   <span data-ttu-id="d3377-119">Gerencia alguns aspectos da sessão (por exemplo, enumerar sessões).</span><span class="sxs-lookup"><span data-stu-id="d3377-119">Manages some aspects of the session (for example, enumerating sessions).</span></span>  
  
    -   <span data-ttu-id="d3377-120">Gerencia envio (**Dispatcher**).</span><span class="sxs-lookup"><span data-stu-id="d3377-120">Handles dispatching (**Dispatcher**).</span></span> <span data-ttu-id="d3377-121">Isso é semelhante a um pool de thread.</span><span class="sxs-lookup"><span data-stu-id="d3377-121">This is similar to a thread pool.</span></span>  
  
    -   <span data-ttu-id="d3377-122">Gerencia buffers de memória (**Buffer**) para eventos.</span><span class="sxs-lookup"><span data-stu-id="d3377-122">Handles memory buffers (**Buffer**) for events.</span></span> <span data-ttu-id="d3377-123">Quando os buffers estiverem cheios, eles são despachados para os destinos.</span><span class="sxs-lookup"><span data-stu-id="d3377-123">When buffers are filled, the buffers are dispatched to targets.</span></span>  
  
-   <span data-ttu-id="d3377-124">Depois que uma sessão for criada e os eventos associados à sessão opcionalmente (**Contexto de sessão**):</span><span class="sxs-lookup"><span data-stu-id="d3377-124">After a session is created and events are optionally bound to the session (**Session context**):</span></span>  
  
    -   <span data-ttu-id="d3377-125">Instâncias de destinos (**Instância de destino**) podem também ser criadas e adicionadas à sessão.</span><span class="sxs-lookup"><span data-stu-id="d3377-125">Instances of targets (**Target instance**) may be also be created and added to the session.</span></span>  
  
    -   <span data-ttu-id="d3377-126">Quando os buffers estão cheios, aqueles buffers são despachados para os destinos.</span><span class="sxs-lookup"><span data-stu-id="d3377-126">When buffers are filled, those buffers are dispatched to targets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3377-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d3377-127">See Also</span></span>  
 [<span data-ttu-id="d3377-128">Eventos estendidos</span><span class="sxs-lookup"><span data-stu-id="d3377-128">Extended Events</span></span>](extended-events.md)  
  
  
