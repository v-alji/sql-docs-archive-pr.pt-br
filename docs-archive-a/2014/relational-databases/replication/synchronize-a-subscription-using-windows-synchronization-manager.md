---
title: Sincronizar uma assinatura usando o Gerenciador de sincronização do Windows (Gerenciador de sincronização do Windows) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- synchronization [SQL Server replication], Windows Synchronization Manager
- Windows Synchronization Manager
ms.assetid: 80f15dd6-e84d-4f96-9866-5b34ea531f1e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bb31c344f91c68b04e03dd218f22b09bec44830b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680894"
---
# <a name="synchronize-a-subscription-using-windows-synchronization-manager-windows-synchronization-manager"></a><span data-ttu-id="bd3e9-102">Sincronizar uma assinatura usando o Gerenciador de Sincronização do Windows (Gerenciador de Sincronização do Windows)</span><span class="sxs-lookup"><span data-stu-id="bd3e9-102">Synchronize a Subscription Using Windows Synchronization Manager (Windows Synchronization Manager)</span></span>
  <span data-ttu-id="bd3e9-103">O Gerenciador de Sincronização[!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows só poderá ser usado para sincronizar assinaturas para publicações do Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estiver em execução no mesmo computador que o Gerenciador de Sincronização (ele também pode ser usado para sincronizar arquivos offline e páginas da Web).</span><span class="sxs-lookup"><span data-stu-id="bd3e9-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Synchronization Manager can only be used to synchronize subscriptions to Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] publications if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running on the same computer as Synchronization Manager (it can also be used to synchronize offline files and Web pages).</span></span> <span data-ttu-id="bd3e9-104">Para usar o Gerenciador de Sincronização:</span><span class="sxs-lookup"><span data-stu-id="bd3e9-104">To use Synchronization Manager:</span></span>  
  
1.  <span data-ttu-id="bd3e9-105">Habilite a sincronização de assinaturas pull com o Gerenciador de Sincronização do Windows na caixa de diálogo **Propriedades de Assinatura – \<Subscriber>\<SubscriptionDatabase>** .</span><span class="sxs-lookup"><span data-stu-id="bd3e9-105">Enable the synchronization of pull subscriptions with Windows Synchronization Manager in the **Subscription Properties - \<Subscriber>: \<SubscriptionDatabase>** dialog box.</span></span> <span data-ttu-id="bd3e9-106">Para obter mais informações sobre como acessar essa caixa de diálogo, consulte [Exibir e modificar propriedades de assinatura pull](view-and-modify-pull-subscription-properties.md).</span><span class="sxs-lookup"><span data-stu-id="bd3e9-106">For more information about accessing this dialog box, see [View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md).</span></span>  
  
2.  <span data-ttu-id="bd3e9-107">Acesse o Gerenciador de Sincronização através do menu **Iniciar** no Windows.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-107">Access Synchronization Manager through the **Start** menu in Windows.</span></span>  
  
 <span data-ttu-id="bd3e9-108">O Gerenciador de Sincronização permite usar o Resolvedor Interativo para mesclar assinaturas.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-108">Synchronization Manager allows you to use the Interactive Resolver for merge subscriptions.</span></span> <span data-ttu-id="bd3e9-109">Normalmente, os conflitos detectados durante a sincronização são resolvidos automaticamente, mas se a resolução interativa estiver habilitada, os conflitos poderão ser resolvidos pelo usuário durante a sincronização.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-109">Typically, conflicts detected during synchronization are resolved automatically, but if interactive resolution is enabled, conflicts can be resolved by a user during synchronization.</span></span> <span data-ttu-id="bd3e9-110">Se a sincronização a ser executada for a do Gerenciador de Sincronização do Windows (como uma sincronização agendada ou sob demanda no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou no Replication Monitor) os conflitos serão resolvidos automaticamente sem a intervenção do usuário, de acordo com o resolvedor especificado para o artigo.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-110">If a synchronization is performed outside of Windows Synchronization Manager (as a scheduled synchronization or an on demand synchronization in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Replication Monitor), conflicts are resolved automatically without user intervention, according to the resolver specified for the article.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bd3e9-111">A partir do [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] e [!INCLUDE[wiprlhlong](../../includes/wiprlhlong-md.md)], as versões de 64 bits do Gerenciador de Sincronização do Windows não podem detectar assinaturas de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-111">Beginning with [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] and [!INCLUDE[wiprlhlong](../../includes/wiprlhlong-md.md)], 64-bit versions of the Windows Synchronization Manager cannot detect 32-bit subscriptions.</span></span>  
  
### <a name="to-enable-the-synchronization-of-pull-subscriptions-with-windows-synchronization-manager"></a><span data-ttu-id="bd3e9-112">Para habilitar a sincronização de assinaturas pull com o Gerenciador de Sincronização do Windows</span><span class="sxs-lookup"><span data-stu-id="bd3e9-112">To enable the synchronization of pull subscriptions with Windows Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="bd3e9-113">Na página **Geral** da caixa de diálogo **Propriedades de Assinatura – \<Subscriber>: \<SubscriptionDatabase>** , selecione um valor de **Habilitar** para a opção **Usar o Gerenciador de Sincronização do Windows**.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-113">On the **General** page of the **Subscription Properties - \<Subscriber>: \<SubscriptionDatabase>** dialog box, select a value of **Enable** for the **Use Windows Synchronization Manager** option.</span></span>  
  
2.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-synchronize-a-pull-subscription-with-synchronization-manager"></a><span data-ttu-id="bd3e9-114">Para sincronizar uma assinatura pull com o Gerenciador de Sincronização</span><span class="sxs-lookup"><span data-stu-id="bd3e9-114">To synchronize a pull subscription with Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="bd3e9-115">Inicie o Gerenciador de Sincronização usando um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="bd3e9-115">Launch Synchronization Manager using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="bd3e9-116">No Internet Explorer, clique em **Ferramentas**e, então, clique em **Sincronizar**.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-116">In Internet Explorer, click **Tools**, and then click **Synchronize**.</span></span>  
  
    -   <span data-ttu-id="bd3e9-117">Clique em **Iniciar**, aponte para **Programas** ou **Todos os Programas**, aponte para **Acessórios**e, então, clique em **Sincronizar**.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-117">Click **Start**, point to **Programs** or **All Programs**, point to **Accessories**, and then click **Synchronize**.</span></span>  
  
    -   <span data-ttu-id="bd3e9-118">Clique em **Iniciar**e, então, clique em **Executar**</span><span class="sxs-lookup"><span data-stu-id="bd3e9-118">Click **Start**, and then click **Run.**</span></span> <span data-ttu-id="bd3e9-119">Na caixa de diálogo **executar** , digite `mobsync.exe` no campo **abrir** e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-119">In the **Run** dialog box, type `mobsync.exe` in the **Open** field, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="bd3e9-120">Na caixa de diálogo **Itens a Serem Sincronizados** , selecione as assinaturas a serem sincronizadas.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-120">In the **Items to Synchronize** dialog box, select the subscriptions to synchronize.</span></span> <span data-ttu-id="bd3e9-121">As assinaturas são listadas sob as instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instaladas no computador.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-121">Subscriptions are listed under the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span>  
  
3.  <span data-ttu-id="bd3e9-122">Clique em **Sincronizar**.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-122">Click **Synchronize**.</span></span>  
  
### <a name="to-reinitialize-a-pull-subscription-with-synchronization-manager"></a><span data-ttu-id="bd3e9-123">Para reinicializar uma assinatura pull com o Gerenciador de Sincronização</span><span class="sxs-lookup"><span data-stu-id="bd3e9-123">To reinitialize a pull subscription with Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="bd3e9-124">Na caixa de diálogo **Itens a Serem Sincronizados** , selecione uma assinatura e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-124">In the **Items to Synchronize** dialog box, select a subscription, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="bd3e9-125">Na caixa de diálogo **Propriedades de Assinatura do SQL Server** , clique em **Reinicializar Assinatura**.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-125">In the **SQL Server Subscription Properties** dialog box, click **Reinitialize Subscription**.</span></span>  
  
3.  <span data-ttu-id="bd3e9-126">Clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-126">Click **Yes**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="bd3e9-127">Por padrão, na próxima vez que a assinatura é sincronizada, um novo instantâneo é aplicado ao banco de dados de assinatura.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-127">The next time the subscription is synchronized, by default a new snapshot is applied to the subscription database.</span></span> <span data-ttu-id="bd3e9-128">Para obter mais informações, consulte [Reinicializar as assinaturas](reinitialize-subscriptions.md).</span><span class="sxs-lookup"><span data-stu-id="bd3e9-128">For more information, see [Reinitialize Subscriptions](reinitialize-subscriptions.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bd3e9-129">A replicação de mesclagem permite que qualquer alteração pendente seja carregada no Publicador antes do instantâneo ser aplicado, mas essa opção não está disponível no Gerenciador de Sincronização.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-129">Merge replication allows any outstanding changes to be uploaded to the Publisher before the snapshot is applied, but this option is not available from Synchronization Manager.</span></span> <span data-ttu-id="bd3e9-130">Para carregar alterações, sincronize a assinatura antes de reiniciá-la.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-130">To upload changes, synchronize the subscription before reinitializing it.</span></span>  
  
### <a name="to-set-properties-for-a-pull-subscription-in-synchronization-manager"></a><span data-ttu-id="bd3e9-131">Para definir propriedades de uma assinatura pull no Gerenciador de Sincronização</span><span class="sxs-lookup"><span data-stu-id="bd3e9-131">To set properties for a pull subscription in Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="bd3e9-132">Na caixa de diálogo **Itens a Serem Sincronizados** , selecione uma assinatura e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-132">In the **Items to Synchronize** dialog box, select a subscription, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="bd3e9-133">Exiba e modifique propriedades nas seguintes guias:</span><span class="sxs-lookup"><span data-stu-id="bd3e9-133">View and modify properties on the following tabs:</span></span>  
  
    -   <span data-ttu-id="bd3e9-134">**Identificação**</span><span class="sxs-lookup"><span data-stu-id="bd3e9-134">**Identification**</span></span>  
  
    -   <span data-ttu-id="bd3e9-135">**Logon do Assinante**, **Logon do Distribuidor**e **Logon do Publicador** (apenas para replicação de mesclagem)</span><span class="sxs-lookup"><span data-stu-id="bd3e9-135">**Subscriber Login**, **Distributor Login**, and **Publisher Login** (for merge replication only)</span></span>  
  
    -   <span data-ttu-id="bd3e9-136">**Informações do Servidor Web** (para assinatura de mesclagem em Assinantes que usam SQL Server 2005 ou posterior)</span><span class="sxs-lookup"><span data-stu-id="bd3e9-136">**Web Server Information** (for merge subscriptions on Subscribers running SQL Server 2005 or later)</span></span>  
  
    -   <span data-ttu-id="bd3e9-137">**Outros**</span><span class="sxs-lookup"><span data-stu-id="bd3e9-137">**Other**</span></span>  
  
     <span data-ttu-id="bd3e9-138">É recomendável usar a Autenticação do Windows para todas as conexões.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-138">It is recommended to use Windows Authentication for all connections.</span></span> <span data-ttu-id="bd3e9-139">Para obter mais informações sobre as permissões que são exigidas pelo Distribution Agent e pelo Merge Agent, consulte [Replication Agent Security Model](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="bd3e9-139">For information about the permissions required by the Distribution Agent and the Merge Agent, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-remove-a-pull-subscription-from-synchronization-manager"></a><span data-ttu-id="bd3e9-140">Para remover uma assinatura pull do Gerenciador de Sincronização</span><span class="sxs-lookup"><span data-stu-id="bd3e9-140">To remove a pull subscription from Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="bd3e9-141">Na caixa de diálogo **Itens a Serem Sincronizados** , selecione uma assinatura e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-141">In the **Items to Synchronize** dialog box, select a subscription, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="bd3e9-142">Na caixa de diálogo **Propriedades de Assinatura do SQL Server** , clique em **Remover Assinatura**.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-142">In the **SQL Server Subscription Properties** dialog box, click **Remove Subscription**.</span></span>  
  
3.  <span data-ttu-id="bd3e9-143">Selecione uma opção na caixa de diálogo **Remover Assinatura** .</span><span class="sxs-lookup"><span data-stu-id="bd3e9-143">Select an option in the **Remove Subscription** dialog box.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-use-the-interactive-resolver"></a><span data-ttu-id="bd3e9-144">Para usar o Resolvedor Interativo</span><span class="sxs-lookup"><span data-stu-id="bd3e9-144">To use the Interactive Resolver</span></span>  
  
1.  <span data-ttu-id="bd3e9-145">Habilite o artigo e assinatura a usarem a resolução interativa.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-145">Enable the article and subscription to use interactive resolution.</span></span> <span data-ttu-id="bd3e9-146">Para obter mais informações, consulte [Especificar a resolução interativa de conflitos para artigos de mesclagem](../../relational-databases/replication/publish/specify-merge-replication-properties.md#interactive-conflict-resolution).</span><span class="sxs-lookup"><span data-stu-id="bd3e9-146">For more information, see [Specify Interactive Conflict Resolution for Merge Articles](../../relational-databases/replication/publish/specify-merge-replication-properties.md#interactive-conflict-resolution).</span></span>
  
2.  <span data-ttu-id="bd3e9-147">Após o início da sincronização da assinatura no Gerenciador de Sincronização, o Resolvedor Interativo será iniciado automaticamente se a resolução interativa de conflitos estiver habilitada e se houver conflitos em um ou mais artigos.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-147">After the subscription begins synchronizing in Synchronization Manager, the Interactive Resolver launches automatically if interactive conflict resolution is enabled and there are conflicts for one or more articles.</span></span> <span data-ttu-id="bd3e9-148">O Resolvedor Interativo exibe um conflito de cada vez, com uma sugestão de resolução para cada conflito (com base no resolvedor especificado quando a publicação e a assinatura foram criadas).</span><span class="sxs-lookup"><span data-stu-id="bd3e9-148">The Interactive Resolver displays conflicts one at a time, with a suggested resolution for each conflict (based on the resolver specified when the publication and subscription were created).</span></span>  
  
3.  <span data-ttu-id="bd3e9-149">Opcionalmente, edite qualquer uma das colunas exibidas no Resolvedor Interativo e clique em um dos seguintes botões para resolver o conflito:</span><span class="sxs-lookup"><span data-stu-id="bd3e9-149">Optionally edit any of the columns displayed in the Interactive Resolver, and then click one of the following buttons to resolve the conflict:</span></span>  
  
    -   <span data-ttu-id="bd3e9-150">**Aceitar Sugestão**</span><span class="sxs-lookup"><span data-stu-id="bd3e9-150">**Accept Suggested**</span></span>  
  
    -   <span data-ttu-id="bd3e9-151">**Aceitar Publicador**</span><span class="sxs-lookup"><span data-stu-id="bd3e9-151">**Accept Publisher**</span></span>  
  
    -   <span data-ttu-id="bd3e9-152">**Aceitar Assinante**</span><span class="sxs-lookup"><span data-stu-id="bd3e9-152">**Accept Subscriber**</span></span>  
  
    -   <span data-ttu-id="bd3e9-153">**Resolver Tudo Automaticamente** (todos os conflitos atuais são resolvidos sem entrada adicional)</span><span class="sxs-lookup"><span data-stu-id="bd3e9-153">**Resolve All Automatically** (all current conflicts are resolved without further input)</span></span>  
  
     <span data-ttu-id="bd3e9-154">Em seguida, a linha selecionada é aplicada ao Publicador e/ou Assinante. Ela é propagada para outros nós na topologia durante sincronizações subsequentes.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-154">The selected row is then applied to the Publisher and/or Subscriber; it is propagated to other nodes in the topology during subsequent synchronizations.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bd3e9-155">As edições serão aplicadas apenas se fizerem parte da linha escolhida para resolução.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-155">Edits are only applied if they are part of the row that is chosen for resolution.</span></span> <span data-ttu-id="bd3e9-156">Por exemplo, se você fizer edições no **Publicador**e, em seguida, clicar em **Aceitar Assinante**, as edições serão descartadas.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-156">For example, if you make edits under **Publisher**, and then click **Accept Subscriber**, the edits are discarded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd3e9-157">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bd3e9-157">See Also</span></span>  
 [<span data-ttu-id="bd3e9-158">Interactive Conflict Resolution</span><span class="sxs-lookup"><span data-stu-id="bd3e9-158">Interactive Conflict Resolution</span></span>](merge/advanced-merge-replication-conflict-interactive-resolution.md)  
  
