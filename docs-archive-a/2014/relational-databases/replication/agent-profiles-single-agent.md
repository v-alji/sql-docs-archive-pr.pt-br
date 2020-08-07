---
title: Perfis de agente (agente único) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.profiles.perfprofileagentname.f1
helpviewer_keywords:
- Agent Profile dialog box
ms.assetid: 22713555-c496-4ce1-8ec7-4ae75cfadca8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7def9a6fef4e7e66076ee18552705c6071dab134
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571965"
---
# <a name="agent-profiles-single-agent"></a><span data-ttu-id="55b6d-102">Perfis de Agente (agente único)</span><span class="sxs-lookup"><span data-stu-id="55b6d-102">Agent Profiles (single agent)</span></span>
  <span data-ttu-id="55b6d-103">Use a caixa de diálogo **Perfis de Agente** para gerenciar perfis para um agente.</span><span class="sxs-lookup"><span data-stu-id="55b6d-103">Use the **Agent Profiles** dialog box to manage profiles for an agent.</span></span> <span data-ttu-id="55b6d-104">Perfis de agente fornecem um modo conveniente para gerenciar parâmetros em runtime para cada agente.</span><span class="sxs-lookup"><span data-stu-id="55b6d-104">Agent profiles provide a convenient way to manage the runtime parameters for each agent.</span></span> <span data-ttu-id="55b6d-105">Cada agente tem um perfil padrão e alguns agentes têm perfis adicionais predefinidos.</span><span class="sxs-lookup"><span data-stu-id="55b6d-105">Each agent has a default profile, and some agents have additional predefined profiles.</span></span> <span data-ttu-id="55b6d-106">Por exemplo, o Merge Agent tem um perfil de "vínculo lento" projetado para baixas conexões de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="55b6d-106">For example, the Merge Agent has a "slow link" profile designed for low bandwidth connections.</span></span> <span data-ttu-id="55b6d-107">Perfis predefinidos são suficientes para a maioria dos aplicativos, mas você também pode criar perfis definidos pelo usuário, que permite personalizar o comportamento do agente.</span><span class="sxs-lookup"><span data-stu-id="55b6d-107">Predefined profiles are sufficient for most applications, but you can also create user-defined profiles, allowing you to customize agent behavior.</span></span>  
  
## <a name="options"></a><span data-ttu-id="55b6d-108">Opções</span><span class="sxs-lookup"><span data-stu-id="55b6d-108">Options</span></span>  
 <span data-ttu-id="55b6d-109">**Padrão para Novo**</span><span class="sxs-lookup"><span data-stu-id="55b6d-109">**Default for New**</span></span>  
 <span data-ttu-id="55b6d-110">Selecione o perfil que será usado quando são criados trabalhos para um agente de um determinado tipo.</span><span class="sxs-lookup"><span data-stu-id="55b6d-110">Select the profile that will be used when jobs are created for an agent of a given type.</span></span> <span data-ttu-id="55b6d-111">Por exemplo, se você criar um número de assinaturas para uma publicação de mesclagem, o trabalho do Merge Agent usará o perfil selecionado para cada assinatura.</span><span class="sxs-lookup"><span data-stu-id="55b6d-111">For example, if you create a number of subscriptions to a merge publication, the Merge Agent job for each subscription will use the profile selected.</span></span> <span data-ttu-id="55b6d-112">Se você quiser alterar o perfil dos trabalhos existentes, selecione um perfil e clique em **Alterar Agentes Existentes**.</span><span class="sxs-lookup"><span data-stu-id="55b6d-112">If you want to change the profile for existing jobs, select a profile, and then click **Change Existing Agents**.</span></span>  
  
 <span data-ttu-id="55b6d-113">**Nome**</span><span class="sxs-lookup"><span data-stu-id="55b6d-113">**Name**</span></span>  
 <span data-ttu-id="55b6d-114">O nome do perfil.</span><span class="sxs-lookup"><span data-stu-id="55b6d-114">The name of the profile.</span></span>  
  
 <span data-ttu-id="55b6d-115">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="55b6d-115">**Type**</span></span>  
 <span data-ttu-id="55b6d-116">O tipo de perfil: **Usuário** (definido pelo usuário) ou **Sistema** (predefinido).</span><span class="sxs-lookup"><span data-stu-id="55b6d-116">The type of profile: **User** (user-defined) or **System** (predefined).</span></span>  
  
 <span data-ttu-id="55b6d-117">**Propriedades (...)**</span><span class="sxs-lookup"><span data-stu-id="55b6d-117">**Properties (...)**</span></span>  
 <span data-ttu-id="55b6d-118">Clique para exibir os valores usados para cada parâmetro no perfil do agente.</span><span class="sxs-lookup"><span data-stu-id="55b6d-118">Click to view the values used for each parameter in the agent profile.</span></span>  
  
 <span data-ttu-id="55b6d-119">**Novo**</span><span class="sxs-lookup"><span data-stu-id="55b6d-119">**New**</span></span>  
 <span data-ttu-id="55b6d-120">Clique para criar um novo perfil.</span><span class="sxs-lookup"><span data-stu-id="55b6d-120">Click to create a new profile.</span></span>  
  
 <span data-ttu-id="55b6d-121">**Delete (excluir)**</span><span class="sxs-lookup"><span data-stu-id="55b6d-121">**Delete**</span></span>  
 <span data-ttu-id="55b6d-122">Selecione um perfil definido pelo usuário e então clique em **Excluir** para excluir aquele perfil.</span><span class="sxs-lookup"><span data-stu-id="55b6d-122">Select a user-defined profile, and then click **Delete** to delete that profile.</span></span> <span data-ttu-id="55b6d-123">Perfis predefinidos não podem ser excluídos.</span><span class="sxs-lookup"><span data-stu-id="55b6d-123">Predefined profiles cannot be deleted.</span></span>  
  
 <span data-ttu-id="55b6d-124">**Alterar Agentes Existentes**</span><span class="sxs-lookup"><span data-stu-id="55b6d-124">**Change Existing Agents**</span></span>  
 <span data-ttu-id="55b6d-125">Selecione um perfil e clique em **Alterar Agentes Existentes** para especificar que todos os trabalhos existentes, para um agente de um tipo específico, devem usar o perfil selecionado.</span><span class="sxs-lookup"><span data-stu-id="55b6d-125">Select a profile, and then click **Change Existing Agents** to specify that all existing jobs for an agent of a given type should use the selected profile.</span></span> <span data-ttu-id="55b6d-126">Por exemplo, se você criou um número de assinaturas para uma publicação de mesclagem e quer alterar o perfil para especificar que um trabalho do Merge Agent para cada uma dessas assinaturas deve usar **Perfil do agente de vínculo lento**, selecione o perfil e clique em **Alterar Agentes Existentes**.</span><span class="sxs-lookup"><span data-stu-id="55b6d-126">For example, if you have created a number of subscriptions to a merge publication, and you want to change the profile to specify that the Merge Agent job for each of these subscriptions should use the **Slow link agent profile**, select that profile, and then click **Change Existing Agents**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55b6d-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="55b6d-127">See Also</span></span>  
 <span data-ttu-id="55b6d-128">[Trabalhar com perfis do Agente de Replicação](agents/work-with-replication-agent-profiles.md) </span><span class="sxs-lookup"><span data-stu-id="55b6d-128">[Work with Replication Agent Profiles](agents/work-with-replication-agent-profiles.md) </span></span>  
 <span data-ttu-id="55b6d-129">[Visão geral dos agentes de replicação](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="55b6d-129">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="55b6d-130">Perfis do agente de replicação</span><span class="sxs-lookup"><span data-stu-id="55b6d-130">Replication Agent Profiles</span></span>](agents/replication-agent-profiles.md)  
  
  
