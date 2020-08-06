---
title: MSSQLSERVER_17883 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17883 (Database Engine error)
ms.assetid: adaf1c04-e397-4a69-90b8-9353a37277ea
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 46488fb6f7adac2c1109871f2aad4c79352829ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679377"
---
# <a name="mssqlserver_17883"></a><span data-ttu-id="ca9a1-102">MSSQLSERVER_17883</span><span class="sxs-lookup"><span data-stu-id="ca9a1-102">MSSQLSERVER_17883</span></span>
    
## <a name="details"></a><span data-ttu-id="ca9a1-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="ca9a1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ca9a1-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="ca9a1-104">Product Name</span></span>|<span data-ttu-id="ca9a1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ca9a1-105">SQL Server</span></span>|  
|<span data-ttu-id="ca9a1-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="ca9a1-106">Event ID</span></span>|<span data-ttu-id="ca9a1-107">17883</span><span class="sxs-lookup"><span data-stu-id="ca9a1-107">17883</span></span>|  
|<span data-ttu-id="ca9a1-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="ca9a1-108">Event Source</span></span>|<span data-ttu-id="ca9a1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ca9a1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ca9a1-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ca9a1-110">Component</span></span>|<span data-ttu-id="ca9a1-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ca9a1-111">SQLEngine</span></span>|  
|<span data-ttu-id="ca9a1-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="ca9a1-112">Symbolic Name</span></span>|<span data-ttu-id="ca9a1-113">SRV_SCHEDULER_NONYIELDING</span><span class="sxs-lookup"><span data-stu-id="ca9a1-113">SRV_SCHEDULER_NONYIELDING</span></span>|  
|<span data-ttu-id="ca9a1-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="ca9a1-114">Message Text</span></span>|<span data-ttu-id="ca9a1-115">Processo %ld:%ld:%ld (0x%lx) Trabalhador 0x%p parece não estar produzindo no Agendador %ld.</span><span class="sxs-lookup"><span data-stu-id="ca9a1-115">Process %ld:%ld:%ld (0x%lx) Worker 0x%p appears to be non-yielding on Scheduler %ld.</span></span> <span data-ttu-id="ca9a1-116">Hora de criação do thread: % I64d.</span><span class="sxs-lookup"><span data-stu-id="ca9a1-116">Thread creation time: %I64d.</span></span> <span data-ttu-id="ca9a1-117">Thread aprox. de uso da CPU: kernel %I64d ms, usuário %I64d ms.</span><span class="sxs-lookup"><span data-stu-id="ca9a1-117">Approx Thread CPU Used: kernel %I64d ms, user %I64d ms.</span></span> <span data-ttu-id="ca9a1-118">Utilização do processo %d%%.</span><span class="sxs-lookup"><span data-stu-id="ca9a1-118">Process Utilization %d%%.</span></span> <span data-ttu-id="ca9a1-119">Sistema inativo %d%%.</span><span class="sxs-lookup"><span data-stu-id="ca9a1-119">System Idle %d%%.</span></span> <span data-ttu-id="ca9a1-120">Intervalo: %I64d ms.</span><span class="sxs-lookup"><span data-stu-id="ca9a1-120">Interval: %I64d ms.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ca9a1-121">Explicação</span><span class="sxs-lookup"><span data-stu-id="ca9a1-121">Explanation</span></span>  
 <span data-ttu-id="ca9a1-122">Indica que há um possível problema com um thread que não está produzindo em um agendador.</span><span class="sxs-lookup"><span data-stu-id="ca9a1-122">Indicates that there is a possible problem with a thread not yielding on a scheduler.</span></span>  <span data-ttu-id="ca9a1-123">Isso pode ocorrer devido a um bug no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não estiver obtendo ciclos necessários para a execução.</span><span class="sxs-lookup"><span data-stu-id="ca9a1-123">This could be caused by a bug in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not getting enough cycles to execute.</span></span>  <span data-ttu-id="ca9a1-124">Esse erro pode deixar de ocorrer caso o thread passe a ter produções eventualmente.</span><span class="sxs-lookup"><span data-stu-id="ca9a1-124">This error could go away if the thread eventually yields.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ca9a1-125">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="ca9a1-125">User Action</span></span>  
 <span data-ttu-id="ca9a1-126">Em caso de carga excessiva no sistema, reduza a carga; caso contrário, entre em contato com os Serviços de Atendimento ao Cliente da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ca9a1-126">If excessive load on system reduce load otherwise contact Microsoft Customer Support Services.</span></span>  
  
  
