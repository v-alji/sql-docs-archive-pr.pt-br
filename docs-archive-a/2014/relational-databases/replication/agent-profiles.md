---
title: Perfis de agente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.profiles.perfprofiles.f1
helpviewer_keywords:
- Agent Profiles dialog box
ms.assetid: 0422e99c-e688-419b-bb4c-c7bebeef1d8d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7584670088da1ac7a9c81f1f8f0cbdce8b040c7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571964"
---
# <a name="agent-profiles"></a><span data-ttu-id="134ab-102">Perfis de Agente</span><span class="sxs-lookup"><span data-stu-id="134ab-102">Agent Profiles</span></span>
  <span data-ttu-id="134ab-103">Use a caixa de diálogo **Perfis de Agente** para gerenciar perfis de agente.</span><span class="sxs-lookup"><span data-stu-id="134ab-103">Use the **Agent Profiles** dialog box to manage agent profiles.</span></span> <span data-ttu-id="134ab-104">Perfis de agente fornecem um modo conveniente para gerenciar parâmetros em runtime para cada agente.</span><span class="sxs-lookup"><span data-stu-id="134ab-104">Agent profiles provide a convenient way to manage the runtime parameters for each agent.</span></span> <span data-ttu-id="134ab-105">Cada agente tem um perfil padrão e alguns agentes têm perfis adicionais predefinidos.</span><span class="sxs-lookup"><span data-stu-id="134ab-105">Each agent has a default profile, and some agents have additional predefined profiles.</span></span> <span data-ttu-id="134ab-106">Por exemplo, o Merge Agent tem um perfil de "vínculo lento" projetado para baixas conexões de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="134ab-106">For example, the Merge Agent has a "slow link" profile designed for low bandwidth connections.</span></span> <span data-ttu-id="134ab-107">Perfis predefinidos são suficientes para a maioria dos aplicativos, mas você também pode criar perfis definidos pelo usuário, que permite personalizar o comportamento do agente.</span><span class="sxs-lookup"><span data-stu-id="134ab-107">Predefined profiles are sufficient for most applications, but you can also create user-defined profiles, allowing you to customize agent behavior.</span></span>  
  
## <a name="options"></a><span data-ttu-id="134ab-108">Opções</span><span class="sxs-lookup"><span data-stu-id="134ab-108">Options</span></span>  
 <span data-ttu-id="134ab-109">**Selecionar uma página**</span><span class="sxs-lookup"><span data-stu-id="134ab-109">**Select a page**</span></span>  
 <span data-ttu-id="134ab-110">Selecione um agente no painel esquerdo e os perfis para o agente são exibidos no painel direito.</span><span class="sxs-lookup"><span data-stu-id="134ab-110">Select an agent in the left pane, and the profiles for the agent are displayed in the right pane.</span></span>  
  
 <span data-ttu-id="134ab-111">**Padrão para Novo**</span><span class="sxs-lookup"><span data-stu-id="134ab-111">**Default for New**</span></span>  
 <span data-ttu-id="134ab-112">Selecione o perfil que será usado quando são criados trabalhos para um agente de um determinado tipo.</span><span class="sxs-lookup"><span data-stu-id="134ab-112">Select the profile that will be used when jobs are created for an agent of a given type.</span></span> <span data-ttu-id="134ab-113">Por exemplo, se você criar um número de assinaturas para uma publicação de mesclagem, o trabalho do Merge Agent usará o perfil selecionado para cada assinatura.</span><span class="sxs-lookup"><span data-stu-id="134ab-113">For example, if you create a number of subscriptions to a merge publication, the Merge Agent job for each subscription will use the profile selected.</span></span> <span data-ttu-id="134ab-114">Se você quiser alterar o perfil dos trabalhos existentes, selecione um perfil e clique em **Alterar Agentes Existentes**.</span><span class="sxs-lookup"><span data-stu-id="134ab-114">If you want to change the profile for existing jobs, select a profile, and then click **Change Existing Agents**.</span></span>  
  
 <span data-ttu-id="134ab-115">**Nome**</span><span class="sxs-lookup"><span data-stu-id="134ab-115">**Name**</span></span>  
 <span data-ttu-id="134ab-116">O nome do perfil.</span><span class="sxs-lookup"><span data-stu-id="134ab-116">The name of the profile.</span></span>  
  
 <span data-ttu-id="134ab-117">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="134ab-117">**Type**</span></span>  
 <span data-ttu-id="134ab-118">O tipo de perfil: **Usuário** (definido pelo usuário) ou **Sistema** (predefinido).</span><span class="sxs-lookup"><span data-stu-id="134ab-118">The type of profile: **User** (user-defined) or **System** (predefined).</span></span>  
  
 <span data-ttu-id="134ab-119">**Propriedades (...)**</span><span class="sxs-lookup"><span data-stu-id="134ab-119">**Properties (...)**</span></span>  
 <span data-ttu-id="134ab-120">Clique para exibir os valores usados para cada parâmetro no perfil do agente.</span><span class="sxs-lookup"><span data-stu-id="134ab-120">Click to view the values used for each parameter in the agent profile.</span></span>  
  
 <span data-ttu-id="134ab-121">**Novo**</span><span class="sxs-lookup"><span data-stu-id="134ab-121">**New**</span></span>  
 <span data-ttu-id="134ab-122">Clique para criar um novo perfil.</span><span class="sxs-lookup"><span data-stu-id="134ab-122">Click to create a new profile.</span></span>  
  
 <span data-ttu-id="134ab-123">**Delete (excluir)**</span><span class="sxs-lookup"><span data-stu-id="134ab-123">**Delete**</span></span>  
 <span data-ttu-id="134ab-124">Selecione um perfil definido pelo usuário e então clique em **Excluir** para excluir aquele perfil.</span><span class="sxs-lookup"><span data-stu-id="134ab-124">Select a user-defined profile, and then click **Delete** to delete that profile.</span></span> <span data-ttu-id="134ab-125">Perfis predefinidos não podem ser excluídos.</span><span class="sxs-lookup"><span data-stu-id="134ab-125">Predefined profiles cannot be deleted.</span></span>  
  
 <span data-ttu-id="134ab-126">**Alterar Agentes Existentes**</span><span class="sxs-lookup"><span data-stu-id="134ab-126">**Change Existing Agents**</span></span>  
 <span data-ttu-id="134ab-127">Selecione um perfil e clique em **Alterar Agentes Existentes** para especificar que todos os trabalhos existentes, para um agente de um tipo específico, devem usar o perfil selecionado.</span><span class="sxs-lookup"><span data-stu-id="134ab-127">Select a profile, and then click **Change Existing Agents** to specify that all existing jobs for an agent of a given type should use the selected profile.</span></span> <span data-ttu-id="134ab-128">Por exemplo, se você criou um número de assinaturas para uma publicação de mesclagem e quer alterar o perfil para especificar que um trabalho do Merge Agent para cada uma dessas assinaturas deve usar **Perfil do agente de vínculo lento**, selecione o perfil e clique em **Alterar Agentes Existentes**.</span><span class="sxs-lookup"><span data-stu-id="134ab-128">For example, if you have created a number of subscriptions to a merge publication, and you want to change the profile to specify that the Merge Agent job for each of these subscriptions should use the **Slow link agent profile**, select that profile, and then click **Change Existing Agents**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="134ab-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="134ab-129">See Also</span></span>  
 <span data-ttu-id="134ab-130">[Trabalhar com perfis do Agente de Replicação](agents/work-with-replication-agent-profiles.md) </span><span class="sxs-lookup"><span data-stu-id="134ab-130">[Work with Replication Agent Profiles](agents/work-with-replication-agent-profiles.md) </span></span>  
 <span data-ttu-id="134ab-131">[Visão geral dos agentes de replicação](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="134ab-131">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="134ab-132">Perfis do agente de replicação</span><span class="sxs-lookup"><span data-stu-id="134ab-132">Replication Agent Profiles</span></span>](agents/replication-agent-profiles.md)  
  
  
