---
title: Caixas de diálogo Criar Nova Política ou Abrir política, Página geral | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.newgroup.f1
- sql12.swb.dmf.policy.f1
- sql12.swb.dmf.policy.filter.f1
ms.assetid: c00bebd0-d04b-4c64-840e-8b7a2c603436
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4b67cb8faf18001b841824b806e7befc0683d457
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572022"
---
# <a name="create-new-policy-or-open-policy-dialog-box-general-page"></a><span data-ttu-id="6dd2b-102">Caixas de diálogo Criar Nova Política ou Abrir política, Página geral</span><span class="sxs-lookup"><span data-stu-id="6dd2b-102">Create New Policy or Open Policy Dialog Box, General Page</span></span>
  <span data-ttu-id="6dd2b-103">Use esta caixa de diálogo para criar uma nova política ou modificar uma política existente do Gerenciamento Baseado em Políticas.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-103">Use this dialog box to create a new Policy-Based Management policy or modify an existing policy.</span></span> <span data-ttu-id="6dd2b-104">Use as áreas **Em relação aos destinos** e **Restrição de servidor** como um filtro para limitar as políticas a um subconjunto de todos os destinos possíveis.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-104">Use the **Against targets** and **Server restriction** areas as a filter to limit policies to a subset of all possible targets.</span></span> <span data-ttu-id="6dd2b-105">Com relação às condições a serem usadas como filtros de destino, elas devem ser definidas em uma faceta física e não devem conter funções e nem operador LIKE.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-105">For conditions to be used as target filters, they must be defined on a physical facet, must not contain functions, and must not contain the LIKE operator.</span></span> <span data-ttu-id="6dd2b-106">Quando o sistema computar o objeto definido para uma política, por padrão os objetos do sistema serão excluídos.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-106">When the system computes the object set for a policy, by default the system objects are excluded.</span></span>  <span data-ttu-id="6dd2b-107">Por exemplo, se o conjunto de objetos da política referenciar todas as tabelas, a política não se aplicará a tabelas do sistema.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-107">For example, if the object set of the policy refers to all tables, the policy will not apply to system tables.</span></span> <span data-ttu-id="6dd2b-108">Se os usuários desejarem avaliar uma política em relação a objetos do sistema, eles poderão explicitamente adicionar objetos do sistema ao conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-108">If users want to evaluate a policy against system objects, they can explicitly add system objects to the object set.</span></span> <span data-ttu-id="6dd2b-109">Entretanto, embora todas as políticas tenham suporte para o modo de avaliação **verificação de agenda** , por questões de desempenho, nem todas as políticas com conjuntos de objetos arbitrários têm suporte para o modo de avaliação **verificação de alterações** .</span><span class="sxs-lookup"><span data-stu-id="6dd2b-109">However, though all policies are supported for **check on schedule** evaluation mode, for performance reason, not all policies with arbitrary object sets are supported for **check on change** evaluation mode.</span></span> <span data-ttu-id="6dd2b-110">Para obter mais informações, consulte [https://blogs.msdn.com/b/sqlpbm/archive/2009/04/13/policy-evaluation-modes.aspx](https://blogs.msdn.com/b/sqlpbm/archive/2009/04/13/policy-evaluation-modes.aspx)</span><span class="sxs-lookup"><span data-stu-id="6dd2b-110">For more information, see [https://blogs.msdn.com/b/sqlpbm/archive/2009/04/13/policy-evaluation-modes.aspx](https://blogs.msdn.com/b/sqlpbm/archive/2009/04/13/policy-evaluation-modes.aspx)</span></span>  
  
## <a name="options"></a><span data-ttu-id="6dd2b-111">Opções</span><span class="sxs-lookup"><span data-stu-id="6dd2b-111">Options</span></span>  
 <span data-ttu-id="6dd2b-112">**Nome**</span><span class="sxs-lookup"><span data-stu-id="6dd2b-112">**Name**</span></span>  
 <span data-ttu-id="6dd2b-113">No caso de uma nova política, digite o nome da nova política.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-113">For a new policy, type the new policy name.</span></span> <span data-ttu-id="6dd2b-114">No caso de uma política existente, o nome será exibido.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-114">For an existing policy, the name is displayed.</span></span>  
  
 <span data-ttu-id="6dd2b-115">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="6dd2b-115">**Enabled**</span></span>  
 <span data-ttu-id="6dd2b-116">Selecione a caixa de seleção **Habilitado** para habilitar a política.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-116">Select the **Enabled** check box to enable the policy.</span></span> <span data-ttu-id="6dd2b-117">Desmarque a caixa de seleção **Habilitado** para desabilitar a política.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-117">Clear the **Enabled** check box to disable the policy.</span></span> <span data-ttu-id="6dd2b-118">A caixa **Habilitado** se aplica à automação da política.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-118">The **Enabled** box applies to policy automation.</span></span> <span data-ttu-id="6dd2b-119">Ela cria ou remove o sistema de automação da política.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-119">It creates or removes the automation system for the policy.</span></span> <span data-ttu-id="6dd2b-120">A automação usa os seguintes mecanismos:</span><span class="sxs-lookup"><span data-stu-id="6dd2b-120">Automation uses the following mechanisms:</span></span>  
  
 <span data-ttu-id="6dd2b-121">**Ao alterar: impedir**</span><span class="sxs-lookup"><span data-stu-id="6dd2b-121">**On change: prevent**</span></span>  
 <span data-ttu-id="6dd2b-122">Um gatilho de banco de dados garante conformidade.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-122">A database trigger enforces compliance.</span></span>  
  
 <span data-ttu-id="6dd2b-123">**Ao alterar: log apenas**</span><span class="sxs-lookup"><span data-stu-id="6dd2b-123">**On change: log only**</span></span>  
 <span data-ttu-id="6dd2b-124">Um evento dos serviços de notificação verifica a conformidade.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-124">A notification services event checks for compliance.</span></span>  
  
 <span data-ttu-id="6dd2b-125">**Ao agendar**</span><span class="sxs-lookup"><span data-stu-id="6dd2b-125">**On schedule**</span></span>  
 <span data-ttu-id="6dd2b-126">Um trabalho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent é criado para verificar a conformidade em uma agenda.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-126">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job is created to check for compliance on a schedule.</span></span>  
  
 <span data-ttu-id="6dd2b-127">Políticas executadas usando o modo de avaliação **Sob Demanda** não usam esta caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-127">Policies that are run using **On demand** evaluation mode do not use this check box.</span></span>  
  
 <span data-ttu-id="6dd2b-128">**Verificar condição**</span><span class="sxs-lookup"><span data-stu-id="6dd2b-128">**Check condition**</span></span>  
 <span data-ttu-id="6dd2b-129">Selecione a condição de Gerenciamento Baseado em Política que esta política usa.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-129">Select the Policy-Based Management condition that this policy uses.</span></span> <span data-ttu-id="6dd2b-130">Todas as condições no servidor para a faceta de Gerenciamento Baseado em Política associada são listadas.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-130">All conditions on the server for the associated Policy-Based Management facet are listed.</span></span> <span data-ttu-id="6dd2b-131">Clique em **Nova condição** para criar uma condição nova.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-131">Click **New condition** to create a new condition.</span></span> <span data-ttu-id="6dd2b-132">Clique no botão de reticências ( **…** ) para modificar a condição.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-132">Click the ellipsis (**...**) button to modify the condition.</span></span>  
  
 <span data-ttu-id="6dd2b-133">**Em relação aos destinos**</span><span class="sxs-lookup"><span data-stu-id="6dd2b-133">**Against targets**</span></span>  
 <span data-ttu-id="6dd2b-134">Selecione os tipos de destinos que estão disponíveis para essa faceta para completar uma expressão de filtro.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-134">Select the target types that are available for this facet to complete a filter expression.</span></span>  
  
 <span data-ttu-id="6dd2b-135">**Modo de avaliação**</span><span class="sxs-lookup"><span data-stu-id="6dd2b-135">**Evaluation Mode**</span></span>  
 <span data-ttu-id="6dd2b-136">Selecione o modo de avaliação para a política.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-136">Select the evaluation mode for the policy.</span></span> <span data-ttu-id="6dd2b-137">Algumas políticas podem ser marcadas, mas não impostas.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-137">Some policies can be checked but not enforced.</span></span> <span data-ttu-id="6dd2b-138">Os modos de avaliação são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="6dd2b-138">The evaluation modes are as follows:</span></span>  
  
 <span data-ttu-id="6dd2b-139">**Sob Demanda**</span><span class="sxs-lookup"><span data-stu-id="6dd2b-139">**On demand**</span></span>  
 <span data-ttu-id="6dd2b-140">A política só será executada quando você executá-la na caixa de diálogo **Avaliar** .</span><span class="sxs-lookup"><span data-stu-id="6dd2b-140">Policy will only be run when you run it from the **Evaluate** dialog box.</span></span>  
  
 <span data-ttu-id="6dd2b-141">**Ao agendar**</span><span class="sxs-lookup"><span data-stu-id="6dd2b-141">**On schedule**</span></span>  
 <span data-ttu-id="6dd2b-142">Avalia periodicamente a política, registra uma entrada de log para políticas sem-conformidade e cria um relatório.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-142">Periodically evaluates the policy, records a log entry for policies that have out-of-compliance, and creates a report.</span></span> <span data-ttu-id="6dd2b-143">Habilita a caixa **Agenda** .</span><span class="sxs-lookup"><span data-stu-id="6dd2b-143">Enables the **Schedule** box.</span></span>  
  
 <span data-ttu-id="6dd2b-144">**Ao alterar: log apenas**</span><span class="sxs-lookup"><span data-stu-id="6dd2b-144">**On change: log only**</span></span>  
 <span data-ttu-id="6dd2b-145">Quando se tenta fazer alterações, esta opção não evita alterações sem-conformidade, mas registra violações de política.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-145">When changes are tried, this option does not prevent out-of-compliance changes, but logs policy violations.</span></span>  
  
 <span data-ttu-id="6dd2b-146">**Ao alterar: impedir**</span><span class="sxs-lookup"><span data-stu-id="6dd2b-146">**On change: prevent**</span></span>  
 <span data-ttu-id="6dd2b-147">Quando se tenta fazer alterações, esta opção evita alterações que possam violar a política.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-147">When changes are tried, this option prevents changes that would violate the policy.</span></span>  
  
 <span data-ttu-id="6dd2b-148">**Agenda**</span><span class="sxs-lookup"><span data-stu-id="6dd2b-148">**Schedule**</span></span>  
 <span data-ttu-id="6dd2b-149">Esta opção aparece quando o modo de avaliação **Ao agendar** é selecionado.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-149">This option appears when **On schedule** evaluation mode is selected.</span></span> <span data-ttu-id="6dd2b-150">Digite o nome da agenda, clique em **Escolher** para selecionar uma agenda de uma lista ou clique em **Novo** para criar uma nova agenda.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-150">Type the name of the schedule, click **Pick** to select a schedule from a list, or click **New** to create a new schedule.</span></span> <span data-ttu-id="6dd2b-151">Para habilitar a área da agenda, **Na agenda** deve ser selecionado.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-151">To enable the schedule area, **On schedule** must be selected.</span></span>  
  
 <span data-ttu-id="6dd2b-152">**Restrição de servidor**</span><span class="sxs-lookup"><span data-stu-id="6dd2b-152">**Server restriction**</span></span>  
 <span data-ttu-id="6dd2b-153">Selecione os tipos de servidores que são apropriados para esta política.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-153">Select the types of servers that are appropriate for this policy.</span></span> <span data-ttu-id="6dd2b-154">As opções são **Nenhum** ou selecione uma condição que filtra os possíveis servidores.</span><span class="sxs-lookup"><span data-stu-id="6dd2b-154">Options are **None** or select a condition that filters the possible servers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dd2b-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6dd2b-155">See Also</span></span>  
 [<span data-ttu-id="6dd2b-156">Administrar servidores com Gerenciamento Baseado em Políticas</span><span class="sxs-lookup"><span data-stu-id="6dd2b-156">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
