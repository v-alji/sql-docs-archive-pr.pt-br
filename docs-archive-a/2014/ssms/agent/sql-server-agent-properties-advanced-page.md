---
title: Propriedades do SQL Server Agent (página Avançado) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.advanced.f1
ms.assetid: a4d798ee-4c18-40d4-b6af-63d17503738c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8ec0d9d7fbd51f9350bf692588f90c292e54f4e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582260"
---
# <a name="sql-server-agent-properties-advanced-page"></a><span data-ttu-id="8f86e-102">Propriedades do SQL Server Agent (página Avançado)</span><span class="sxs-lookup"><span data-stu-id="8f86e-102">SQL Server Agent Properties (Advanced Page)</span></span>
  <span data-ttu-id="8f86e-103">Use esta página para exibir e modificar as propriedades avançadas do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] serviço do Agent.</span><span class="sxs-lookup"><span data-stu-id="8f86e-103">Use this page to view and modify advanced properties of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8f86e-104">Opções</span><span class="sxs-lookup"><span data-stu-id="8f86e-104">Options</span></span>  
 <span data-ttu-id="8f86e-105">**Encaminhamento de evento do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="8f86e-105">**SQL Server event forwarding**</span></span>  
 <span data-ttu-id="8f86e-106">As opções nesta categoria ativam e configuram o encaminhamento de evento.</span><span class="sxs-lookup"><span data-stu-id="8f86e-106">The options in this category activate and configure event forwarding.</span></span>  
  
 <span data-ttu-id="8f86e-107">**Encaminhar eventos para um servidor diferente**</span><span class="sxs-lookup"><span data-stu-id="8f86e-107">**Forward events to a different server**</span></span>  
 <span data-ttu-id="8f86e-108">Encaminha eventos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para um servidor diferente.</span><span class="sxs-lookup"><span data-stu-id="8f86e-108">Forwards [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent events to a different server.</span></span>  
  
 <span data-ttu-id="8f86e-109">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="8f86e-109">**Server**</span></span>  
 <span data-ttu-id="8f86e-110">Selecionar o nome do servidor ao qual os eventos serão encaminhados.</span><span class="sxs-lookup"><span data-stu-id="8f86e-110">Select the name of the server to forward events to.</span></span>  
  
 <span data-ttu-id="8f86e-111">**Eventos sem-tratamento**</span><span class="sxs-lookup"><span data-stu-id="8f86e-111">**Unhandled events**</span></span>  
 <span data-ttu-id="8f86e-112">Encaminha apenas os eventos sem-tratamento para o servidor especificado.</span><span class="sxs-lookup"><span data-stu-id="8f86e-112">Forwards only unhandled events to the specified server.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8f86e-113">O Agent só encaminha os eventos aos quais não haja respostas de nenhum alerta.</span><span class="sxs-lookup"><span data-stu-id="8f86e-113">Agent forwards only events that no alert responds to.</span></span>  
  
 <span data-ttu-id="8f86e-114">**Todos os eventos**</span><span class="sxs-lookup"><span data-stu-id="8f86e-114">**All events**</span></span>  
 <span data-ttu-id="8f86e-115">Encaminha todos os eventos.</span><span class="sxs-lookup"><span data-stu-id="8f86e-115">Forwards all events.</span></span> <span data-ttu-id="8f86e-116">Quando um alerta na instância local responde ao evento, o agente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] encaminhará o evento e processará o alerta.</span><span class="sxs-lookup"><span data-stu-id="8f86e-116">When an alert in the local instance responds to the event, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agent will both forward the event and process the alert.</span></span>  
  
 <span data-ttu-id="8f86e-117">**Se a gravidade do evento for esta ou acima**</span><span class="sxs-lookup"><span data-stu-id="8f86e-117">**If event has severity at or above**</span></span>  
 <span data-ttu-id="8f86e-118">Encaminha apenas os eventos com nível de severidade igual ou maior que o nível especificado.</span><span class="sxs-lookup"><span data-stu-id="8f86e-118">Forwards only events with a severity level at or above the level specified.</span></span>  
  
 <span data-ttu-id="8f86e-119">**Condição de CPU ociosa**</span><span class="sxs-lookup"><span data-stu-id="8f86e-119">**Idle CPU Condition**</span></span>  
 <span data-ttu-id="8f86e-120">As opções nesta categoria definem as condições sobre as quais o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent executa trabalhos agendados para serem executados na agenda da CPU ociosa.</span><span class="sxs-lookup"><span data-stu-id="8f86e-120">The options in this category define the conditions under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent runs jobs scheduled to run on the Idle CPU schedule.</span></span>  
  
 <span data-ttu-id="8f86e-121">**Definir condição de CPU ociosa**</span><span class="sxs-lookup"><span data-stu-id="8f86e-121">**Define idle CPU condition**</span></span>  
 <span data-ttu-id="8f86e-122">Define as condições sob as quais o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent considera que a CPU está ociosa.</span><span class="sxs-lookup"><span data-stu-id="8f86e-122">Defines the conditions under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent considers the CPU to be idle.</span></span>  
  
 <span data-ttu-id="8f86e-123">**Uso médio de CPU cai abaixo de**</span><span class="sxs-lookup"><span data-stu-id="8f86e-123">**Average CPU usage falls below**</span></span>  
 <span data-ttu-id="8f86e-124">Porcentagem de uso de CPU abaixo do qual a CPU é considerada ociosa.</span><span class="sxs-lookup"><span data-stu-id="8f86e-124">Percentage of CPU usage below which the CPU is considered to be idle.</span></span>  
  
 <span data-ttu-id="8f86e-125">**E permanece abaixo desse nível por**</span><span class="sxs-lookup"><span data-stu-id="8f86e-125">**And remains below this level for**</span></span>  
 <span data-ttu-id="8f86e-126">Quantidade de tempo em que o uso médio da CPU deve estar abaixo do nível especificado antes que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent execute trabalhos na agenda de CPU ociosa.</span><span class="sxs-lookup"><span data-stu-id="8f86e-126">Amount of time that the average CPU must below the level specified before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent runs jobs on the Idle CPU schedule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f86e-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8f86e-127">See Also</span></span>  
 <span data-ttu-id="8f86e-128">[Criar e anexar agendas a trabalhos](create-and-attach-schedules-to-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="8f86e-128">[Create and Attach Schedules to Jobs](create-and-attach-schedules-to-jobs.md) </span></span>  
 [<span data-ttu-id="8f86e-129">Gerenciar eventos</span><span class="sxs-lookup"><span data-stu-id="8f86e-129">Manage Events</span></span>](manage-events.md)  
  
  
