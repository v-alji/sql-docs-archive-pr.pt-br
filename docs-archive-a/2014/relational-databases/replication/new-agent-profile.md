---
title: Novo perfil de agente | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.profiles.newperfprofile.f1
helpviewer_keywords:
- New Agent Profile dialog box
ms.assetid: ebf59330-a421-45a5-9020-0484a96852bc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1d7848e44585fd35a5b5a33cf431e15de96c9375
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683484"
---
# <a name="new-agent-profile"></a><span data-ttu-id="7a205-102">Novo Perfil de Agente</span><span class="sxs-lookup"><span data-stu-id="7a205-102">New Agent Profile</span></span>
  <span data-ttu-id="7a205-103">Use a caixa de diálogo **Novo Perfil de Agente** para criar um novo perfil.</span><span class="sxs-lookup"><span data-stu-id="7a205-103">Use the **New Agent Profile** dialog box to create a new profile.</span></span> <span data-ttu-id="7a205-104">Novos perfis sempre são baseados em perfis existentes, mas eles podem ser modificados para atender aos requisitos do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7a205-104">New profiles are always based on existing profiles, but they can be modified to meet application requirements.</span></span> <span data-ttu-id="7a205-105">Depois que um perfil é criado ele pode ser aplicado a trabalhos de agentes futuros e existentes na caixa de diálogo **Perfis de Agente** .</span><span class="sxs-lookup"><span data-stu-id="7a205-105">After a profile has been created, it can be applied to existing and future agent jobs in the **Agent Profiles** dialog box.</span></span> <span data-ttu-id="7a205-106">Os valores de parâmetro de agente podem ser editados na caixa de diálogo Propriedades do \<**AgentProfileName>\*\*.</span><span class="sxs-lookup"><span data-stu-id="7a205-106">Agent parameter values can be edited in the \<**AgentProfileName> Properties\*\* dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7a205-107">Opções</span><span class="sxs-lookup"><span data-stu-id="7a205-107">Options</span></span>  
 <span data-ttu-id="7a205-108">**Nome**</span><span class="sxs-lookup"><span data-stu-id="7a205-108">**Name**</span></span>  
 <span data-ttu-id="7a205-109">Insira um nome para o perfil.</span><span class="sxs-lookup"><span data-stu-id="7a205-109">Enter a name for the profile.</span></span>  
  
 <span data-ttu-id="7a205-110">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="7a205-110">**Description**</span></span>  
 <span data-ttu-id="7a205-111">Insira uma descrição para o perfil.</span><span class="sxs-lookup"><span data-stu-id="7a205-111">Enter a description for the profile.</span></span>  
  
 <span data-ttu-id="7a205-112">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="7a205-112">**Parameter**</span></span>  
 <span data-ttu-id="7a205-113">Os parâmetros de agente incluídos no perfil.</span><span class="sxs-lookup"><span data-stu-id="7a205-113">The agent parameters included in the profile.</span></span> <span data-ttu-id="7a205-114">O perfil no qual o perfil novo é baseado não especifica necessariamente um valor para cada parâmetro.</span><span class="sxs-lookup"><span data-stu-id="7a205-114">The profile on which the new profile is based does not necessarily specify a value for each parameter.</span></span> <span data-ttu-id="7a205-115">Para consultar todos os parâmetros válidos de um determinado agente, desmarque a caixa de seleção **Mostrar apenas os parâmetros usados neste perfil** .</span><span class="sxs-lookup"><span data-stu-id="7a205-115">To see all parameters that are valid for a given agent, clear the **Show only parameters used in this profile** check box.</span></span> <span data-ttu-id="7a205-116">Para obter descrições de cada parâmetro, consulte.</span><span class="sxs-lookup"><span data-stu-id="7a205-116">For descriptions of each parameter, see:</span></span>  
  
-   [<span data-ttu-id="7a205-117">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="7a205-117">Replication Snapshot Agent</span></span>](agents/replication-snapshot-agent.md)  
  
-   [<span data-ttu-id="7a205-118">Agente do Leitor de Log de Replicação</span><span class="sxs-lookup"><span data-stu-id="7a205-118">Replication Log Reader Agent</span></span>](agents/replication-log-reader-agent.md)  
  
-   [<span data-ttu-id="7a205-119">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="7a205-119">Replication Distribution Agent</span></span>](agents/replication-distribution-agent.md)  
  
-   [<span data-ttu-id="7a205-120">Replication Merge Agent</span><span class="sxs-lookup"><span data-stu-id="7a205-120">Replication Merge Agent</span></span>](agents/replication-merge-agent.md)  
  
-   [<span data-ttu-id="7a205-121">Agente de Leitor de Fila de Replicação</span><span class="sxs-lookup"><span data-stu-id="7a205-121">Replication Queue Reader Agent</span></span>](agents/replication-queue-reader-agent.md)  
  
 <span data-ttu-id="7a205-122">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="7a205-122">**Default Value**</span></span>  
 <span data-ttu-id="7a205-123">O valor padrão para cada parâmetro de agente.</span><span class="sxs-lookup"><span data-stu-id="7a205-123">The default value for each agent parameter.</span></span>  
  
 <span data-ttu-id="7a205-124">**Valor**</span><span class="sxs-lookup"><span data-stu-id="7a205-124">**Value**</span></span>  
 <span data-ttu-id="7a205-125">O valor especificado para o parâmetro no perfil no qual o perfil novo é baseado.</span><span class="sxs-lookup"><span data-stu-id="7a205-125">The value specified for the parameter in the profile on which the new profile is based.</span></span> <span data-ttu-id="7a205-126">Edite esse campo para obter qualquer valor de parâmetro que você queira alterar.</span><span class="sxs-lookup"><span data-stu-id="7a205-126">Edit this field for any parameter values you want to change.</span></span>  
  
 <span data-ttu-id="7a205-127">**Mostrar apenas os parâmetros usados neste perfil**</span><span class="sxs-lookup"><span data-stu-id="7a205-127">**Show only parameters used in this profile**</span></span>  
 <span data-ttu-id="7a205-128">Desmarque para mostrar todos os parâmetros válidos para um determinado agente.</span><span class="sxs-lookup"><span data-stu-id="7a205-128">Clear to show all valid parameters for a given agent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a205-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7a205-129">See Also</span></span>  
 <span data-ttu-id="7a205-130">[Trabalhar com perfis do Agente de Replicação](agents/work-with-replication-agent-profiles.md) </span><span class="sxs-lookup"><span data-stu-id="7a205-130">[Work with Replication Agent Profiles](agents/work-with-replication-agent-profiles.md) </span></span>  
 <span data-ttu-id="7a205-131">[Visão geral dos agentes de replicação](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="7a205-131">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="7a205-132">Perfis do agente de replicação</span><span class="sxs-lookup"><span data-stu-id="7a205-132">Replication Agent Profiles</span></span>](agents/replication-agent-profiles.md)  
  
  
