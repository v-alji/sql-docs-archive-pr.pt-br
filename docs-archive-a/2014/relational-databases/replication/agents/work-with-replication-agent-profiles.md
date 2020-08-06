---
title: Trabalhar com perfis do agente de replicação | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], agents and profiles
- replication agent profiles [SQL Server]
- agents [SQL Server replication], profiles
- profiles [SQL Server], replication agents
ms.assetid: 9c290a88-4e9f-4a7e-aab5-4442137a9918
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fc20451edfb1096fca7e468effb14df78b51f758
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569947"
---
# <a name="work-with-replication-agent-profiles"></a><span data-ttu-id="78354-102">Trabalhar com perfis do agente de replicação</span><span class="sxs-lookup"><span data-stu-id="78354-102">Work with Replication Agent Profiles</span></span>
  <span data-ttu-id="78354-103">Este tópico descreve como trabalhar com perfis do Agente de Replicação no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], o [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou o RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="78354-103">This topic describes how to work with Replication Agent Profiles in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span> <span data-ttu-id="78354-104">O comportamento de cada agente de replicação é controlado por um conjunto de parâmetros que podem ser definidos através dos perfis de agente.</span><span class="sxs-lookup"><span data-stu-id="78354-104">The behavior of each replication agent is controlled by a set of parameters that can be set through agent profiles.</span></span> <span data-ttu-id="78354-105">Cada agente tem um perfil padrão, e alguns têm perfis adicionais predefinidos; em um determinado momento, apenas um perfil está ativo para um agente.</span><span class="sxs-lookup"><span data-stu-id="78354-105">Each agent has a default profile, and some have additional predefined profiles; at a given time, only one profile is active for an agent.</span></span>  
  
 <span data-ttu-id="78354-106">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="78354-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="78354-107">**Para trabalhar com perfis do Agente de Replicação, usando:**</span><span class="sxs-lookup"><span data-stu-id="78354-107">**To work with Replication Agent Profiles, using:**</span></span>  
  
     [<span data-ttu-id="78354-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="78354-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
    -   <span data-ttu-id="78354-109">Acesse a caixa de diálogo Perfis de Agente</span><span class="sxs-lookup"><span data-stu-id="78354-109">Access the Agent Profiles dialog box</span></span>  
  
    -   <span data-ttu-id="78354-110">Especifique um perfil para um agente</span><span class="sxs-lookup"><span data-stu-id="78354-110">Specify a profile for an agent</span></span>  
  
    -   <span data-ttu-id="78354-111">Crie um perfil</span><span class="sxs-lookup"><span data-stu-id="78354-111">Create a profile</span></span>  
  
    -   <span data-ttu-id="78354-112">Modifique um perfil</span><span class="sxs-lookup"><span data-stu-id="78354-112">Modify a profile</span></span>  
  
    -   <span data-ttu-id="78354-113">Exclua um perfil</span><span class="sxs-lookup"><span data-stu-id="78354-113">Delete a profile</span></span>  
  
     [<span data-ttu-id="78354-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="78354-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
    -   <span data-ttu-id="78354-115">Crie um perfil</span><span class="sxs-lookup"><span data-stu-id="78354-115">Create a profile</span></span>  
  
    -   <span data-ttu-id="78354-116">Modifique um perfil</span><span class="sxs-lookup"><span data-stu-id="78354-116">Modify a profile</span></span>  
  
    -   <span data-ttu-id="78354-117">Exclua um perfil</span><span class="sxs-lookup"><span data-stu-id="78354-117">Delete a profile</span></span>  
  
    -   <span data-ttu-id="78354-118">Use perfis de agente durante a sincronização</span><span class="sxs-lookup"><span data-stu-id="78354-118">Use agent profiles during synchronization</span></span>  
  
    -   <span data-ttu-id="78354-119">Exemplo de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="78354-119">Transact-SQL example</span></span>  
  
     [<span data-ttu-id="78354-120">Replication Management Objects</span><span class="sxs-lookup"><span data-stu-id="78354-120">Replication Management Objects</span></span>](#RMOProcedure)  
  
    -   <span data-ttu-id="78354-121">Crie um perfil</span><span class="sxs-lookup"><span data-stu-id="78354-121">Create a profile</span></span>  
  
    -   <span data-ttu-id="78354-122">Modifique um perfil</span><span class="sxs-lookup"><span data-stu-id="78354-122">Modify a profile</span></span>  
  
    -   <span data-ttu-id="78354-123">Exclua um perfil</span><span class="sxs-lookup"><span data-stu-id="78354-123">Delete a profile</span></span>  
  
-   <span data-ttu-id="78354-124">**Acompanhamento:**  [depois de alterar parâmetros de agente](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="78354-124">**Follow Up:**  [After Changing Agent Parameters](#FollowUp)</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="78354-125">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="78354-125">Using SQL Server Management Studio</span></span>  
  
###  <a name="to-access-the-agent-profiles-dialog-box-from-sql-server-management-studio"></a><a name="Access_SSMS"></a> <span data-ttu-id="78354-126">Para acessar a caixa de diálogo Perfis do Agente a partir do SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="78354-126">To access the Agent Profiles dialog box from SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="78354-127">Na página **Geral** da caixa de diálogo **Propriedades do Distribuidor – \<Distributor>** , clique em **Padrões de Perfil**.</span><span class="sxs-lookup"><span data-stu-id="78354-127">On the **General** page of the **Distributor Properties - \<Distributor>** dialog box, click **Profile Defaults**.</span></span>  
  
#### <a name="to-access-the-agent-profiles-dialog-box-from-replication-monitor"></a><span data-ttu-id="78354-128">Para acessar a caixa de diálogo Perfis do Agente a partir do Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="78354-128">To access the Agent Profiles dialog box from Replication Monitor</span></span>  
  
-   <span data-ttu-id="78354-129">Para abrir a caixa de diálogo para todos os agentes, clique com o botão direito em um Publicador e, em seguida, clique em **Perfis do Agente**.</span><span class="sxs-lookup"><span data-stu-id="78354-129">To open the dialog box for all agents, right-click a Publisher, and then click **Agent Profiles**.</span></span>  
  
-   <span data-ttu-id="78354-130">Para abrir a caixa de diálogo para um único agente:</span><span class="sxs-lookup"><span data-stu-id="78354-130">To open the dialog box for a single agent:</span></span>  
  
    1.  <span data-ttu-id="78354-131">Expanda um Grupo do publicador no painel esquerdo do Replication Monitor, expanda um Publicador e, em seguida, clique em uma publicação.</span><span class="sxs-lookup"><span data-stu-id="78354-131">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
    2.  <span data-ttu-id="78354-132">Para os perfis de Distribution Agent ou Merge Agent, clique em uma assinatura com o botão direito na guia **Todas as Assinaturas** e então clique em **Perfil do Agente**.</span><span class="sxs-lookup"><span data-stu-id="78354-132">For Distribution Agent and Merge Agent profiles, right-click a subscription on the **All Subscriptions** tab, and then click **Agent Profile**.</span></span> <span data-ttu-id="78354-133">Para outros agentes, clique com o botão direito do mouse no agente na guia **Agentes** e, em seguida, clique em **Perfil do Agente**.</span><span class="sxs-lookup"><span data-stu-id="78354-133">For other agents, right-click the agent on the **Agents** tab, and then click **Agent Profile**.</span></span>  
  
###  <a name="to-specify-a-profile-for-an-agent"></a><a name="Specify_SSMS"></a> <span data-ttu-id="78354-134">Para especificar o perfil para um agente</span><span class="sxs-lookup"><span data-stu-id="78354-134">To specify a profile for an agent</span></span>  
  
1.  <span data-ttu-id="78354-135">Se a caixa de diálogo **Perfis do Agente** exibir perfis para mais de um agente, selecione um agente.</span><span class="sxs-lookup"><span data-stu-id="78354-135">If the **Agent Profiles** dialog box displays profiles for more than one agent, select an agent.</span></span>  
  
2.  <span data-ttu-id="78354-136">Selecione um perfil na coluna **Padrão para Novo** da grade **Perfis do Agente** .</span><span class="sxs-lookup"><span data-stu-id="78354-136">Select a profile in the **Default for new** column of the **Agent profiles** grid.</span></span> <span data-ttu-id="78354-137">Por padrão, o perfil só é aplicado aos agentes para publicações e assinaturas novas.</span><span class="sxs-lookup"><span data-stu-id="78354-137">By default, the profile is only applied to agents for new publications and subscriptions.</span></span>  
  
3.  <span data-ttu-id="78354-138">Para especificar que todos os agentes de um tipo selecionado para publicações ou assinaturas existentes usem esse perfil, clique em **Alterar agentes existentes**.</span><span class="sxs-lookup"><span data-stu-id="78354-138">To specify that all agents of the selected type for existing publications or subscriptions should use this profile, click **Change existing agents**.</span></span>  
  
###  <a name="to-view-and-edit-the-parameters-associated-with-a-profile"></a><a name="Modify_SSMS"></a> <span data-ttu-id="78354-139">Para exibir e editar os parâmetros associados a um perfil</span><span class="sxs-lookup"><span data-stu-id="78354-139">To view and edit the parameters associated with a profile</span></span>  
  
1.  <span data-ttu-id="78354-140">Se a caixa de diálogo **Perfis do Agente** exibir perfis para mais de um agente, selecione um agente.</span><span class="sxs-lookup"><span data-stu-id="78354-140">If the **Agent Profiles** dialog box displays profiles for more than one agent, select an agent.</span></span>  
  
2.  <span data-ttu-id="78354-141">Clique no botão de propriedades ( **…** ) ao lado de um perfil.</span><span class="sxs-lookup"><span data-stu-id="78354-141">Click the properties button (**...**) next to a profile.</span></span>  
  
3.  <span data-ttu-id="78354-142">Exiba os parâmetros e valores na caixa de diálogo **Propriedades do Perfil \<ProfileName>** .</span><span class="sxs-lookup"><span data-stu-id="78354-142">View the parameters and values in the **\<ProfileName> Profile Properties** dialog box.</span></span>  
  
    -   <span data-ttu-id="78354-143">Os parâmetros em perfis definidos pelo usuário podem ser editados; os parâmetros em perfis de sistema predefinidos não podem.</span><span class="sxs-lookup"><span data-stu-id="78354-143">Parameters in user-defined profiles can be edited; parameters in predefined system profiles cannot.</span></span>  
  
    -   <span data-ttu-id="78354-144">Para exibir todos os parâmetros de um agente, desmarque a caixa de seleção **Mostrar apenas os parâmetros usados neste perfil** .</span><span class="sxs-lookup"><span data-stu-id="78354-144">To view all parameters for an agent, clear the **Show only parameters used in this profile** check box.</span></span> <span data-ttu-id="78354-145">Para obter informações sobre parâmetros de agente, consulte os links no final deste tópico.</span><span class="sxs-lookup"><span data-stu-id="78354-145">For information about agent parameters, see the links at the end of this topic.</span></span>  
  
4.  <span data-ttu-id="78354-146">Clique em **fechar**</span><span class="sxs-lookup"><span data-stu-id="78354-146">Click **Close**.</span></span>  
  
###  <a name="to-create-a-user-defined-profile"></a><a name="Create_SSMS"></a> <span data-ttu-id="78354-147">Para criar um perfil definido pelo usuário</span><span class="sxs-lookup"><span data-stu-id="78354-147">To create a user-defined profile</span></span>  
  
1.  <span data-ttu-id="78354-148">Se a caixa de diálogo **Perfis do Agente** exibir perfis para mais de um agente, selecione um agente.</span><span class="sxs-lookup"><span data-stu-id="78354-148">If the **Agent Profiles** dialog box displays profiles for more than one agent, select an agent.</span></span>  
  
2.  <span data-ttu-id="78354-149">Clique em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="78354-149">Click **New**.</span></span>  
  
3.  <span data-ttu-id="78354-150">Na caixa de diálogo de inicialização **Novo Perfil do Agente** , selecione um perfil existente no qual o novo perfil será baseado.</span><span class="sxs-lookup"><span data-stu-id="78354-150">In the **New Agent Profile** initialization dialog box, select an existing profile on which to base the new profile.</span></span>  
  
4.  <span data-ttu-id="78354-151">Na caixa de diálogo **Novo Perfil do Agente** , digite os valores nas caixas de texto **Nome** e **Descrição** .</span><span class="sxs-lookup"><span data-stu-id="78354-151">In the **New Agent Profile** dialog box, enter values in the **Name** and **Description** text boxes.</span></span>  
  
5.  <span data-ttu-id="78354-152">Modificar parâmetros para personalizar o perfil.</span><span class="sxs-lookup"><span data-stu-id="78354-152">Modify parameters to tailor the profile.</span></span> <span data-ttu-id="78354-153">Para exibir todos os parâmetros de um agente, desmarque a caixa de seleção **Mostrar apenas os parâmetros usados neste perfil** .</span><span class="sxs-lookup"><span data-stu-id="78354-153">To view all parameters for an agent, clear the **Show only parameters used in this profile** check box.</span></span> <span data-ttu-id="78354-154">Para obter informações sobre parâmetros de agente, consulte os links no final deste tópico.</span><span class="sxs-lookup"><span data-stu-id="78354-154">For information about agent parameters, see the links at the end of this topic.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
###  <a name="to-delete-a-user-defined-profile"></a><a name="Delete_SSMS"></a> <span data-ttu-id="78354-155">Para excluir um perfil definido pelo usuário</span><span class="sxs-lookup"><span data-stu-id="78354-155">To delete a user-defined profile</span></span>  
  
1.  <span data-ttu-id="78354-156">Se a caixa de diálogo **Perfis do Agente** exibir perfis para mais de um agente, selecione um agente.</span><span class="sxs-lookup"><span data-stu-id="78354-156">If the **Agent Profiles** dialog box displays profiles for more than one agent, select an agent.</span></span>  
  
2.  <span data-ttu-id="78354-157">Se um perfil for associado a um ou mais agentes, altere o perfil para esses agentes:</span><span class="sxs-lookup"><span data-stu-id="78354-157">If a profile is associated with one or more agents, change the profile for those agents:</span></span>  
  
    1.  <span data-ttu-id="78354-158">Selecione um perfil diferente na grade **Perfis do Agente** .</span><span class="sxs-lookup"><span data-stu-id="78354-158">Select a different profile in the **Agent profiles** grid.</span></span>  
  
    2.  <span data-ttu-id="78354-159">Clique em **Alterar Agentes Existentes**.</span><span class="sxs-lookup"><span data-stu-id="78354-159">Click **Change existing agents**.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="78354-160">Isso alterará o perfil para todos os agentes do tipo selecionado para publicações ou assinaturas existentes, não apenas para os que usam o perfil que se deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="78354-160">This will change the profile for all agents of the selected type for existing publications or subscriptions, not only the ones using the profile you want to delete.</span></span>  
  
3.  <span data-ttu-id="78354-161">Selecione o perfil a ser excluído e, em seguida, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="78354-161">Select the profile you want to delete, and then click **Delete**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="78354-162">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="78354-162">Using Transact-SQL</span></span>  
  
###  <a name="to-create-a-new-agent-profile"></a><a name="Create_tsql"></a> <span data-ttu-id="78354-163">Para criar um perfil novo de agente</span><span class="sxs-lookup"><span data-stu-id="78354-163">To create a new agent profile</span></span>  
  
1.  <span data-ttu-id="78354-164">No Distribuidor, execute [sp_add_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="78354-164">At the Distributor, execute [sp_add_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-agent-profile-transact-sql).</span></span> <span data-ttu-id="78354-165">Especifique **@name** , um valor de **1** para **@profile_type** e um dos seguintes valores para **@agent_type** :</span><span class="sxs-lookup"><span data-stu-id="78354-165">Specify **@name**, a value of **1** for **@profile_type**, and one of the following values for **@agent_type**:</span></span>  
  
    -   <span data-ttu-id="78354-166">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span><span class="sxs-lookup"><span data-stu-id="78354-166">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span></span>  
  
    -   <span data-ttu-id="78354-167">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="78354-167">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span></span>  
  
    -   <span data-ttu-id="78354-168">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span><span class="sxs-lookup"><span data-stu-id="78354-168">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span></span>  
  
    -   <span data-ttu-id="78354-169">**4** - [Replication Merge Agent](replication-merge-agent.md)</span><span class="sxs-lookup"><span data-stu-id="78354-169">**4** - [Replication Merge Agent](replication-merge-agent.md)</span></span>  
  
    -   <span data-ttu-id="78354-170">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="78354-170">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span></span>  
  
     <span data-ttu-id="78354-171">Se esse perfil se tornar o novo perfil padrão para seu tipo de agente de replicação, especifique o valor **1** para **@default**.</span><span class="sxs-lookup"><span data-stu-id="78354-171">If this profile will become the new default profile for its type of replication agent, specify a value of **1** for **@default**.</span></span> <span data-ttu-id="78354-172">O identificador para o novo perfil é retornado usando o **@profile_id** parâmetro de saída.</span><span class="sxs-lookup"><span data-stu-id="78354-172">The identifier for the new profile is returned using the **@profile_id** output parameter.</span></span> <span data-ttu-id="78354-173">Isso cria um perfil novo com um conjunto de parâmetros de perfis baseado no perfil padrão para o tipo de agente especificado.</span><span class="sxs-lookup"><span data-stu-id="78354-173">This creates a new profile with a set of profile parameters based on the default profile for the given agent type.</span></span>  
  
2.  <span data-ttu-id="78354-174">Depois que o perfil novo for criado, adicione, remova ou modifique os parâmetros padrão para personalizar o perfil.</span><span class="sxs-lookup"><span data-stu-id="78354-174">After the new profile has been created, add, remove, or modify the default parameters to customize the profile.</span></span>  
  
###  <a name="to-modify-an-existing-agent-profile"></a><a name="Modify_tsql"></a> <span data-ttu-id="78354-175">Para modificar um perfil de agente existente</span><span class="sxs-lookup"><span data-stu-id="78354-175">To modify an existing agent profile</span></span>  
  
1.  <span data-ttu-id="78354-176">No Distribuidor, execute [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="78354-176">At the Distributor, execute [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span></span> <span data-ttu-id="78354-177">Especifique um dos seguintes valores para **@agent_type** :</span><span class="sxs-lookup"><span data-stu-id="78354-177">Specify one of the following values for **@agent_type**:</span></span>  
  
    -   <span data-ttu-id="78354-178">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span><span class="sxs-lookup"><span data-stu-id="78354-178">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span></span>  
  
    -   <span data-ttu-id="78354-179">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="78354-179">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span></span>  
  
    -   <span data-ttu-id="78354-180">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span><span class="sxs-lookup"><span data-stu-id="78354-180">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span></span>  
  
    -   <span data-ttu-id="78354-181">**4** - [Replication Merge Agent](replication-merge-agent.md)</span><span class="sxs-lookup"><span data-stu-id="78354-181">**4** - [Replication Merge Agent](replication-merge-agent.md)</span></span>  
  
    -   <span data-ttu-id="78354-182">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="78354-182">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span></span>  
  
     <span data-ttu-id="78354-183">Isso retorna todos os perfis para o tipo especificado de agente.</span><span class="sxs-lookup"><span data-stu-id="78354-183">This returns all profiles for the specified type of agent.</span></span> <span data-ttu-id="78354-184">Observe o valor de **profile_id** no conjunto de resultados para o perfil a ser alterado.</span><span class="sxs-lookup"><span data-stu-id="78354-184">Note the value of **profile_id** in the result set for the profile to change.</span></span>  
  
2.  <span data-ttu-id="78354-185">No Distribuidor, execute [sp_help_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-parameter-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="78354-185">At the Distributor, execute [sp_help_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-parameter-transact-sql).</span></span> <span data-ttu-id="78354-186">Especifique o identificador de perfil da etapa 1 para **@profile_id** .</span><span class="sxs-lookup"><span data-stu-id="78354-186">Specify the profile identifier from step 1 for **@profile_id**.</span></span> <span data-ttu-id="78354-187">Isso retorna todos os parâmetros para o perfil.</span><span class="sxs-lookup"><span data-stu-id="78354-187">This returns all parameters for the profile.</span></span> <span data-ttu-id="78354-188">Observe o nome de qualquer parâmetro a modificar ou remover do perfil.</span><span class="sxs-lookup"><span data-stu-id="78354-188">Note the name of any parameters to modify or remove from the profile.</span></span>  
  
3.  <span data-ttu-id="78354-189">Para alterar o valor de um parâmetro em um perfil, execute [sp_change_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="78354-189">To change the value of a parameter in a profile, execute [sp_change_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-agent-profile-transact-sql).</span></span> <span data-ttu-id="78354-190">Especifique o identificador de perfil da etapa 1 para **@profile_id** , o nome do parâmetro a ser alterado **@property** e um novo valor para o parâmetro para **@value** .</span><span class="sxs-lookup"><span data-stu-id="78354-190">Specify the profile identifier from step 1 for **@profile_id**, the name of the parameter to change for **@property**, and a new value for the parameter for **@value**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="78354-191">Você não pode alterar um perfil de agente existente para se tornar o perfil padrão para um agente.</span><span class="sxs-lookup"><span data-stu-id="78354-191">You cannot change an existing agent profile to become the default profile for an agent.</span></span> <span data-ttu-id="78354-192">Em vez disso, você deve criar um perfil novo como perfil padrão, como mostrado no procedimento anterior.</span><span class="sxs-lookup"><span data-stu-id="78354-192">You must instead create a new profile as the default profile, as shown in the previous procedure.</span></span>  
  
4.  <span data-ttu-id="78354-193">Para remover um parâmetro de um perfil, execute [sp_drop_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-drop-agent-parameter-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="78354-193">To remove a parameter from a profile, execute [sp_drop_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-drop-agent-parameter-transact-sql).</span></span> <span data-ttu-id="78354-194">Especifique o identificador de perfil da etapa 1 para **@profile_id** e o nome do parâmetro a ser removido **@parameter_name** .</span><span class="sxs-lookup"><span data-stu-id="78354-194">Specify the profile identifier from step 1 for **@profile_id** and the name of the parameter to remove for **@parameter_name**.</span></span>  
  
5.  <span data-ttu-id="78354-195">Para adicionar um parâmetro novo a um perfil, você deve fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="78354-195">To add a new parameter to a profile, you must do the following:</span></span>  
  
    -   <span data-ttu-id="78354-196">Examine a tabela do [MSagentparameterlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/msagentparameterlist-transact-sql) no Distribuidor para determinar quais parâmetros de perfil podem ser definidos para cada tipo de agente.</span><span class="sxs-lookup"><span data-stu-id="78354-196">Query the [MSagentparameterlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/msagentparameterlist-transact-sql) table at the Distributor to determine which profile parameters can be set for each agent type.</span></span>  
  
    -   <span data-ttu-id="78354-197">No Distribuidor, execute [sp_add_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-agent-parameter-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="78354-197">At the Distributor, execute [sp_add_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-agent-parameter-transact-sql).</span></span> <span data-ttu-id="78354-198">Especifique o identificador de perfil da etapa 1 para **@profile_id** , o nome de um parâmetro válido para o qual adicionar **@parameter_name** e o valor do parâmetro para **@parameter_value** .</span><span class="sxs-lookup"><span data-stu-id="78354-198">Specify the profile identifier from step 1 for **@profile_id**, the name of a valid parameter to add for **@parameter_name**, and the value of the parameter for **@parameter_value**.</span></span>  
  
###  <a name="to-delete-an-agent-profile"></a><a name="Delete_tsql"></a> <span data-ttu-id="78354-199">Para excluir um perfil de agente</span><span class="sxs-lookup"><span data-stu-id="78354-199">To delete an agent profile</span></span>  
  
1.  <span data-ttu-id="78354-200">No Distribuidor, execute [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="78354-200">At the Distributor, execute [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span></span> <span data-ttu-id="78354-201">Especifique um dos seguintes valores para **@agent_type** :</span><span class="sxs-lookup"><span data-stu-id="78354-201">Specify one of the following values for **@agent_type**:</span></span>  
  
    -   <span data-ttu-id="78354-202">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span><span class="sxs-lookup"><span data-stu-id="78354-202">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span></span>  
  
    -   <span data-ttu-id="78354-203">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="78354-203">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span></span>  
  
    -   <span data-ttu-id="78354-204">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span><span class="sxs-lookup"><span data-stu-id="78354-204">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span></span>  
  
    -   <span data-ttu-id="78354-205">**4** - [Replication Merge Agent](replication-merge-agent.md)</span><span class="sxs-lookup"><span data-stu-id="78354-205">**4** - [Replication Merge Agent](replication-merge-agent.md)</span></span>  
  
    -   <span data-ttu-id="78354-206">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="78354-206">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span></span>  
  
     <span data-ttu-id="78354-207">Isso retorna todos os perfis para o tipo especificado de agente.</span><span class="sxs-lookup"><span data-stu-id="78354-207">This returns all profiles for the specified type of agent.</span></span> <span data-ttu-id="78354-208">Observe o valor de **profile_id** no conjunto de resultados para o perfil a remover.</span><span class="sxs-lookup"><span data-stu-id="78354-208">Note the value of **profile_id** in the result set for the profile to remove.</span></span>  
  
2.  <span data-ttu-id="78354-209">No Distribuidor, execute [sp_drop_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-drop-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="78354-209">At the Distributor, execute [sp_drop_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-drop-agent-profile-transact-sql).</span></span> <span data-ttu-id="78354-210">Especifique o identificador de perfil da etapa 1 para **@profile_id** .</span><span class="sxs-lookup"><span data-stu-id="78354-210">Specify the profile identifier from step 1 for **@profile_id**.</span></span>  
  
###  <a name="to-use-agent-profiles-during-synchronization"></a><a name="Synch_tsql"></a> <span data-ttu-id="78354-211">Para usar perfis de agente durante sincronização</span><span class="sxs-lookup"><span data-stu-id="78354-211">To use agent profiles during synchronization</span></span>  
  
1.  <span data-ttu-id="78354-212">No Distribuidor, execute [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="78354-212">At the Distributor, execute [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span></span> <span data-ttu-id="78354-213">Especifique um dos seguintes valores para **@agent_type** :</span><span class="sxs-lookup"><span data-stu-id="78354-213">Specify one of the following values for **@agent_type**:</span></span>  
  
    -   <span data-ttu-id="78354-214">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span><span class="sxs-lookup"><span data-stu-id="78354-214">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span></span>  
  
    -   <span data-ttu-id="78354-215">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="78354-215">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span></span>  
  
    -   <span data-ttu-id="78354-216">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span><span class="sxs-lookup"><span data-stu-id="78354-216">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span></span>  
  
    -   <span data-ttu-id="78354-217">**4** - [Replication Merge Agent](replication-merge-agent.md)</span><span class="sxs-lookup"><span data-stu-id="78354-217">**4** - [Replication Merge Agent](replication-merge-agent.md)</span></span>  
  
    -   <span data-ttu-id="78354-218">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="78354-218">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span></span>  
  
     <span data-ttu-id="78354-219">Isso retorna todos os perfis para o tipo especificado de agente.</span><span class="sxs-lookup"><span data-stu-id="78354-219">This returns all profiles for the specified type of agent.</span></span> <span data-ttu-id="78354-220">Observe o valor de `profile_name` no conjunto de resultados para o perfil a ser usado.</span><span class="sxs-lookup"><span data-stu-id="78354-220">Note the value of `profile_name` in the result set for the profile to use.</span></span>  
  
2.  <span data-ttu-id="78354-221">Se o agente for iniciado a partir de um trabalho do Agent, edite a etapa de trabalho que inicia o agente para especificar o valor `profile_name` obtido na etapa 1 após o parâmetro de linha de comando **-ProfileName** .</span><span class="sxs-lookup"><span data-stu-id="78354-221">If the agent is started from an agent job, edit the job step that starts the agent to specify the value of `profile_name` obtained in step 1 after the **-ProfileName** command-line parameter.</span></span> <span data-ttu-id="78354-222">Para obter mais informações, consulte [Exibir e modificar parâmetros do prompt de comando do agente de replicação &#40;SQL Server Management Studio&#41;](view-and-modify-replication-agent-command-prompt-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="78354-222">For more information, see [View and Modify Replication Agent Command Prompt Parameters &#40;SQL Server Management Studio&#41;](view-and-modify-replication-agent-command-prompt-parameters.md).</span></span>  
  
3.  <span data-ttu-id="78354-223">Ao iniciar o agente no prompt de comando, especifique o valor `profile_name` obtido na etapa 1 após o parâmetro de linha de comando **-ProfileName** .</span><span class="sxs-lookup"><span data-stu-id="78354-223">When starting the agent from the command prompt, specify the value of `profile_name` obtained in step 1 after the **-ProfileName** command-line parameter.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="78354-224">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="78354-224">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="78354-225">Este exemplo cria um perfil personalizado para o Agente de Mesclagem nomeado **custom_merge**, altera o valor do parâmetro **-UploadReadChangesPerBatch** , adiciona um novo parâmetro **-ExchangeType** e retorna informações sobre o perfil criado.</span><span class="sxs-lookup"><span data-stu-id="78354-225">This example creates a custom profile for the Merge Agent named **custom_merge**, changes the value of the **-UploadReadChangesPerBatch** parameter, adds a new **-ExchangeType** parameter, and returns information on the profile that is created.</span></span>  
  
 [!code-sql[HowTo#sp_addagentprofileparam](../../../snippets/tsql/SQL15/replication/howto/tsql/createperfparammerge.sql#sp_addagentprofileparam)]  
  
##  <a name="using-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="78354-226">Usando RMO</span><span class="sxs-lookup"><span data-stu-id="78354-226">Using RMO</span></span>  
  
###  <a name="to-create-a-new-agent-profile"></a><a name="Create_RMO"></a> <span data-ttu-id="78354-227">Para criar um perfil novo de agente</span><span class="sxs-lookup"><span data-stu-id="78354-227">To create a new agent profile</span></span>  
  
1.  <span data-ttu-id="78354-228">Crie uma conexão para o Distribuidor usando uma instância da classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="78354-228">Create a connection to the Distributor by using an instance of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="78354-229">Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.AgentProfile>.</span><span class="sxs-lookup"><span data-stu-id="78354-229">Create an instance of the <xref:Microsoft.SqlServer.Replication.AgentProfile> class.</span></span>  
  
3.  <span data-ttu-id="78354-230">Defina as seguintes propriedades no objeto:</span><span class="sxs-lookup"><span data-stu-id="78354-230">Set the following properties on the object:</span></span>  
  
    -   <span data-ttu-id="78354-231"><xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> - o nome para o perfil.</span><span class="sxs-lookup"><span data-stu-id="78354-231"><xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> - the name for the profile.</span></span>  
  
    -   <span data-ttu-id="78354-232"><xref:Microsoft.SqlServer.Replication.AgentProfile.AgentType%2A> - um valor <xref:Microsoft.SqlServer.Replication.AgentType> que especifica o tipo de agente de replicação para o qual está sendo criado o perfil.</span><span class="sxs-lookup"><span data-stu-id="78354-232"><xref:Microsoft.SqlServer.Replication.AgentProfile.AgentType%2A> - an <xref:Microsoft.SqlServer.Replication.AgentType> value that specifies the type of replication agent for which the profile is being created.</span></span>  
  
    -   <span data-ttu-id="78354-233"><xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> - o <xref:Microsoft.SqlServer.Management.Common.ServerConnection> criado na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="78354-233"><xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> - the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> created in step 1.</span></span>  
  
    -   <span data-ttu-id="78354-234">(Opcional) <xref:Microsoft.SqlServer.Replication.AgentProfile.Description%2A> - uma descrição do perfil.</span><span class="sxs-lookup"><span data-stu-id="78354-234">(Optional) <xref:Microsoft.SqlServer.Replication.AgentProfile.Description%2A> - a description of the profile.</span></span>  
  
    -   <span data-ttu-id="78354-235">(Opcional) <xref:Microsoft.SqlServer.Replication.AgentProfile.Default%2A> - defina essa propriedade para `true` se todos os trabalhos de agente novos para essa <xref:Microsoft.SqlServer.Replication.AgentType> utilizarão, por padrão, esse perfil.</span><span class="sxs-lookup"><span data-stu-id="78354-235">(Optional) <xref:Microsoft.SqlServer.Replication.AgentProfile.Default%2A> - set this property to `true` if all new agent jobs for this <xref:Microsoft.SqlServer.Replication.AgentType> will use this profile by default.</span></span>  
  
4.  <span data-ttu-id="78354-236">Chame o método <xref:Microsoft.SqlServer.Replication.AgentProfile.Create%2A> para criar o perfil no servidor.</span><span class="sxs-lookup"><span data-stu-id="78354-236">Call the <xref:Microsoft.SqlServer.Replication.AgentProfile.Create%2A> method to create the profile on the server.</span></span>  
  
5.  <span data-ttu-id="78354-237">Uma vez que o perfil existir no servidor, você poderá personalizá-lo adicionando, removendo ou modificando os valores dos parâmetros do agente de replicação.</span><span class="sxs-lookup"><span data-stu-id="78354-237">Once the profile exists on the server, you can customize it by adding, removing, or changing the values of replication agent parameters.</span></span>  
  
6.  <span data-ttu-id="78354-238">Para atribuir o perfil a um trabalho de agente de replicação existente, chame o método <xref:Microsoft.SqlServer.Replication.AgentProfile.AssignToAgent%2A> .</span><span class="sxs-lookup"><span data-stu-id="78354-238">To assign the profile to an existing replication agent job, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.AssignToAgent%2A> method.</span></span> <span data-ttu-id="78354-239">Passe o nome do banco de dados de distribuição para *distributionDBName* e a ID do trabalho para *agentID*.</span><span class="sxs-lookup"><span data-stu-id="78354-239">Pass the name of the distribution database for *distributionDBName* and the ID of the job for *agentID*.</span></span>  
  
###  <a name="to-modify-an-existing-agent-profile"></a><a name="Modify_RMO"></a> <span data-ttu-id="78354-240">Para modificar um perfil de agente existente</span><span class="sxs-lookup"><span data-stu-id="78354-240">To modify an existing agent profile</span></span>  
  
1.  <span data-ttu-id="78354-241">Crie uma conexão para o Distribuidor usando uma instância da classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="78354-241">Create a connection to the Distributor by using an instance of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="78354-242">Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.ReplicationServer>.</span><span class="sxs-lookup"><span data-stu-id="78354-242">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span> <span data-ttu-id="78354-243">Passe o objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> criado na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="78354-243">Pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object created in step 1.</span></span>  
  
3.  <span data-ttu-id="78354-244">Chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> .</span><span class="sxs-lookup"><span data-stu-id="78354-244">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method.</span></span> <span data-ttu-id="78354-245">Se esse método retornar `false`, verifique se o Distribuidor existe.</span><span class="sxs-lookup"><span data-stu-id="78354-245">If this method returns `false`, verify that the Distributor exists.</span></span>  
  
4.  <span data-ttu-id="78354-246">Chame o método <xref:Microsoft.SqlServer.Replication.ReplicationServer.EnumAgentProfiles%2A> .</span><span class="sxs-lookup"><span data-stu-id="78354-246">Call the <xref:Microsoft.SqlServer.Replication.ReplicationServer.EnumAgentProfiles%2A> method.</span></span> <span data-ttu-id="78354-247">Passe um valor <xref:Microsoft.SqlServer.Replication.AgentType> para reduzir os perfis retornados a um tipo específico de agente de replicação.</span><span class="sxs-lookup"><span data-stu-id="78354-247">Pass an <xref:Microsoft.SqlServer.Replication.AgentType> value to narrow down the returned profiles to a specific type of replication agent.</span></span>  
  
5.  <span data-ttu-id="78354-248">Obtenha o objeto desejado <xref:Microsoft.SqlServer.Replication.AgentProfile> dos <xref:System.Collections.ArrayList>retornados, nos quais a propriedade <xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> do objeto corresponda ao nome do perfil.</span><span class="sxs-lookup"><span data-stu-id="78354-248">Get the desired <xref:Microsoft.SqlServer.Replication.AgentProfile> object from the returned <xref:System.Collections.ArrayList>, where the <xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> property of the object matches the profile name.</span></span>  
  
6.  <span data-ttu-id="78354-249">Chame um dos métodos seguintes de <xref:Microsoft.SqlServer.Replication.AgentProfile> para alterar o perfil:</span><span class="sxs-lookup"><span data-stu-id="78354-249">Call one of the following methods of <xref:Microsoft.SqlServer.Replication.AgentProfile> to change the profile:</span></span>  
  
    -   <span data-ttu-id="78354-250"><xref:Microsoft.SqlServer.Replication.AgentProfile.AddParameter%2A> - adiciona um parâmetro com suporte ao perfil, onde *name* é o nome parâmetro do agente de replicação e *value* é o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="78354-250"><xref:Microsoft.SqlServer.Replication.AgentProfile.AddParameter%2A> - adds a supported parameter to the profile, where *name* is the name of the replication agent parameter and *value* is the specified value.</span></span> <span data-ttu-id="78354-251">Para enumerar todos os parâmetros de agente com suporte para um determinado tipo de agente, chame o método <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameterInfo%2A> .</span><span class="sxs-lookup"><span data-stu-id="78354-251">To enumerate all supported agent parameters for a given agent type, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameterInfo%2A> method.</span></span> <span data-ttu-id="78354-252">Este método retorna um <xref:System.Collections.ArrayList> de objetos <xref:Microsoft.SqlServer.Replication.AgentProfileParameterInfo> que representam todos os parâmetros com suporte.</span><span class="sxs-lookup"><span data-stu-id="78354-252">This method returns an <xref:System.Collections.ArrayList> of <xref:Microsoft.SqlServer.Replication.AgentProfileParameterInfo> objects that represent all supported parameters.</span></span>  
  
    -   <span data-ttu-id="78354-253"><xref:Microsoft.SqlServer.Replication.AgentProfile.RemoveParameter%2A> - remove um parâmetro existente do perfil, onde *name* é o nome do parâmetro do agente de replicação.</span><span class="sxs-lookup"><span data-stu-id="78354-253"><xref:Microsoft.SqlServer.Replication.AgentProfile.RemoveParameter%2A> - removes an existing parameter from the profile, where *name* is the name of the replication agent parameter.</span></span> <span data-ttu-id="78354-254">Para enumerar todos os parâmetros de agente atuais definidos para o perfil, chame o método <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameters%2A> .</span><span class="sxs-lookup"><span data-stu-id="78354-254">To enumerate all current agent parameters defined for the profile, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameters%2A> method.</span></span> <span data-ttu-id="78354-255">Este método retorna um <xref:System.Collections.ArrayList> de objetos <xref:Microsoft.SqlServer.Replication.AgentProfileParameter> que representam o parâmetro existente para este perfil.</span><span class="sxs-lookup"><span data-stu-id="78354-255">This method returns an <xref:System.Collections.ArrayList> of <xref:Microsoft.SqlServer.Replication.AgentProfileParameter> objects that represent the existing parameter for this profile.</span></span>  
  
    -   <span data-ttu-id="78354-256"><xref:Microsoft.SqlServer.Replication.AgentProfile.ChangeParameter%2A> - altera a configuração de um parâmetro existente no perfil, onde *name* é o nome do parâmetro do agente de replicação e *newValue* é o valor para o qual o parâmetro está sendo alterado.</span><span class="sxs-lookup"><span data-stu-id="78354-256"><xref:Microsoft.SqlServer.Replication.AgentProfile.ChangeParameter%2A> - changes the setting of an existing parameter in the profile, where *name* is the name of the agent parameter and *newValue* is the value to which the parameter is being changed.</span></span> <span data-ttu-id="78354-257">Para enumerar todos os parâmetros de agente atuais definidos para o perfil, chame o método <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameters%2A> .</span><span class="sxs-lookup"><span data-stu-id="78354-257">To enumerate all current agent parameters defined for the profile, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameters%2A> method.</span></span> <span data-ttu-id="78354-258">Este método retorna um <xref:System.Collections.ArrayList> de objetos <xref:Microsoft.SqlServer.Replication.AgentProfileParameter> que representam o parâmetro existente para este perfil.</span><span class="sxs-lookup"><span data-stu-id="78354-258">This method returns an <xref:System.Collections.ArrayList> of <xref:Microsoft.SqlServer.Replication.AgentProfileParameter> objects that represent the existing parameter for this profile.</span></span> <span data-ttu-id="78354-259">Para enumerar todas as configurações de parâmetro de agente com suporte, chame o método <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameterInfo%2A> .</span><span class="sxs-lookup"><span data-stu-id="78354-259">To enumerate all supported agent parameter settings, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameterInfo%2A> method.</span></span> <span data-ttu-id="78354-260">Este método retorna um <xref:System.Collections.ArrayList> de objetos <xref:Microsoft.SqlServer.Replication.AgentProfileParameterInfo> que representam os valores com suporte para todos os parâmetros.</span><span class="sxs-lookup"><span data-stu-id="78354-260">This method returns an <xref:System.Collections.ArrayList> of <xref:Microsoft.SqlServer.Replication.AgentProfileParameterInfo> objects that represent the supported values for all parameters.</span></span>  
  
###  <a name="to-delete-an-agent-profile"></a><a name="Delete_RMO"></a> <span data-ttu-id="78354-261">Para excluir um perfil de agente</span><span class="sxs-lookup"><span data-stu-id="78354-261">To delete an agent profile</span></span>  
  
1.  <span data-ttu-id="78354-262">Crie uma conexão para o Distribuidor usando uma instância da classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="78354-262">Create a connection to the Distributor by using an instance of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="78354-263">Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.AgentProfile>.</span><span class="sxs-lookup"><span data-stu-id="78354-263">Create an instance of the <xref:Microsoft.SqlServer.Replication.AgentProfile> class.</span></span> <span data-ttu-id="78354-264">Defina o nome do perfil para <xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> e o <xref:Microsoft.SqlServer.Management.Common.ServerConnection> da etapa 1 para <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="78354-264">Set the name of the profile for <xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> and the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="78354-265">Chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> .</span><span class="sxs-lookup"><span data-stu-id="78354-265">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method.</span></span> <span data-ttu-id="78354-266">Se este método retornar `false`, o banco de dados com o nome especificado estava incorreto ou o perfil não existe no servidor.</span><span class="sxs-lookup"><span data-stu-id="78354-266">If this method returns `false`, either the specified name was incorrect or the profile does not exist on the server.</span></span>  
  
4.  <span data-ttu-id="78354-267">Verifique se a propriedade <xref:Microsoft.SqlServer.Replication.AgentProfile.Type%2A> é definida como <xref:Microsoft.SqlServer.Replication.AgentProfileTypeOption.User>, o que indica um perfil de cliente.</span><span class="sxs-lookup"><span data-stu-id="78354-267">Verify that the <xref:Microsoft.SqlServer.Replication.AgentProfile.Type%2A> property is set to <xref:Microsoft.SqlServer.Replication.AgentProfileTypeOption.User>, which indicates a customer profile.</span></span> <span data-ttu-id="78354-268">Você não deve remover um perfil que possui um valor de <xref:Microsoft.SqlServer.Replication.AgentProfileTypeOption.System> para <xref:Microsoft.SqlServer.Replication.AgentProfile.Type%2A>.</span><span class="sxs-lookup"><span data-stu-id="78354-268">You should not remove a profile that has a value of <xref:Microsoft.SqlServer.Replication.AgentProfileTypeOption.System> for <xref:Microsoft.SqlServer.Replication.AgentProfile.Type%2A>.</span></span>  
  
5.  <span data-ttu-id="78354-269">Chame o método <xref:Microsoft.SqlServer.Replication.AgentProfile.Remove%2A> para remover o perfil definido pelo usuário representado por esse objeto do servidor.</span><span class="sxs-lookup"><span data-stu-id="78354-269">Call the <xref:Microsoft.SqlServer.Replication.AgentProfile.Remove%2A> method to remove the user-defined profile represented by this object from the server.</span></span>  
  
##  <a name="follow-up-after-changing-agent-parameters"></a><a name="FollowUp"></a> <span data-ttu-id="78354-270">Acompanhamento: depois de alterar parâmetros de agente</span><span class="sxs-lookup"><span data-stu-id="78354-270">Follow Up: After Changing Agent Parameters</span></span>  
 <span data-ttu-id="78354-271">As alterações do parâmetro de agente entrarão em vigor na próxima vez o agente for iniciado.</span><span class="sxs-lookup"><span data-stu-id="78354-271">Agent parameter changes take effect the next time the agent is started.</span></span> <span data-ttu-id="78354-272">Se o agente ficar executando continuamente, será necessário parar e reiniciar o agente.</span><span class="sxs-lookup"><span data-stu-id="78354-272">If the agent runs continuously, you must stop and restart the agent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78354-273">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="78354-273">See Also</span></span>  
 <span data-ttu-id="78354-274">[Perfis do agente de replicação](replication-agent-profiles.md) </span><span class="sxs-lookup"><span data-stu-id="78354-274">[Replication Agent Profiles](replication-agent-profiles.md) </span></span>  
 <span data-ttu-id="78354-275">[Replication Snapshot Agent](replication-snapshot-agent.md) </span><span class="sxs-lookup"><span data-stu-id="78354-275">[Replication Snapshot Agent](replication-snapshot-agent.md) </span></span>  
 <span data-ttu-id="78354-276">[Replication Log Reader Agent](replication-log-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="78354-276">[Replication Log Reader Agent](replication-log-reader-agent.md) </span></span>  
 <span data-ttu-id="78354-277">[Replication Distribution Agent](replication-distribution-agent.md) </span><span class="sxs-lookup"><span data-stu-id="78354-277">[Replication Distribution Agent](replication-distribution-agent.md) </span></span>  
 <span data-ttu-id="78354-278">[Replication Merge Agent](replication-merge-agent.md) </span><span class="sxs-lookup"><span data-stu-id="78354-278">[Replication Merge Agent](replication-merge-agent.md) </span></span>  
 [<span data-ttu-id="78354-279">Agente de Leitor de Fila de Replicação</span><span class="sxs-lookup"><span data-stu-id="78354-279">Replication Queue Reader Agent</span></span>](replication-queue-reader-agent.md)  
  
  
