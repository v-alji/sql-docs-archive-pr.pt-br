---
title: Alternar entre modos de atualização para uma assinatura transacional atualizável | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- transactional replication, updatable subscriptions
- updatable subscriptions, update modes
- subscriptions [SQL Server replication], updatable
ms.assetid: ab5ebab1-7ee4-41f4-999b-b4f0c420c921
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c31814d1e2ab6fac64ffcde883f3cac2439828a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584123"
---
# <a name="switch-between-update-modes-for-an-updatable-transactional-subscription"></a><span data-ttu-id="83ea0-102">Alternar entre modos de atualização para uma assinatura transacional atualizável</span><span class="sxs-lookup"><span data-stu-id="83ea0-102">Switch Between Update Modes for an Updatable Transactional Subscription</span></span>
  <span data-ttu-id="83ea0-103">Este tópico descreve como alternar entre modos de atualização para uma assinatura de transação atualizável no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83ea0-103">This topic describes how to switch between update modes for an updatable transaction subscription in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="83ea0-104">Especifique o modo para assinaturas atualizáveis usando o Assistente para Nova Assinatura.</span><span class="sxs-lookup"><span data-stu-id="83ea0-104">Specify the mode for updatable subscriptions using the New Subscription Wizard.</span></span> <span data-ttu-id="83ea0-105">Para obter informações sobre como configurar o modo ao usar esse assistente, consulte [Exibir e modificar propriedades de assinatura pull](../view-and-modify-pull-subscription-properties.md).</span><span class="sxs-lookup"><span data-stu-id="83ea0-105">For information about setting the mode when using this wizard, see [View and Modify Pull Subscription Properties](../view-and-modify-pull-subscription-properties.md).</span></span>  
  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="83ea0-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="83ea0-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="83ea0-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="83ea0-107">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="83ea0-108">É possível realizar failover da atualização imediata para a atualização em fila a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="83ea0-108">You can fail over from immediate to queued updating at any time.</span></span> <span data-ttu-id="83ea0-109">Entretanto, após fazê-lo, não será possível retornar para atualização imediata até que o Assinante ou o Publicador esteja conectado e o Queue Reader Agent tenha aplicado todas as mensagens pendentes na fila para o Publicador.</span><span class="sxs-lookup"><span data-stu-id="83ea0-109">After you do, however, you cannot return to immediate updating until the Subscriber and Publisher are connected and the Queue Reader Agent has applied all pending messages in the queue to the Publisher.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="83ea0-110">Recomendações</span><span class="sxs-lookup"><span data-stu-id="83ea0-110">Recommendations</span></span>  
  
-   <span data-ttu-id="83ea0-111">Quando uma assinatura de atualização para uma publicação transacional oferecer suporte para failover de um modo de atualização para outro, você poderá alternar programaticamente os modos de atualização para tratar situações em que a conectividade muda por um curto intervalo de tempo.</span><span class="sxs-lookup"><span data-stu-id="83ea0-111">When an updating subscription to a transactional publication supports failover from one updating mode to another, you can programmatically switch update modes to handle situations when connectivity changes for a short period of time.</span></span> <span data-ttu-id="83ea0-112">O modo de atualização pode ser definido programaticamente e sob demanda usando procedimentos armazenados de replicação.</span><span class="sxs-lookup"><span data-stu-id="83ea0-112">The update mode can be set programmatically and on demand using replication stored procedures.</span></span> <span data-ttu-id="83ea0-113">Para obter mais informações, consulte [Updatable Subscriptions for Transactional Replication](../transactional/updatable-subscriptions-for-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="83ea0-113">For more information, see [Updatable Subscriptions for Transactional Replication](../transactional/updatable-subscriptions-for-transactional-replication.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="83ea0-114">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="83ea0-114">Using SQL Server Management Studio</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="83ea0-115">Para alterar o modo de atualização após a criação da assinatura, a propriedade **update_mode** deve ser definida como **failover** (que permite a troca de atualização imediata para atualização na fila) ou **failover na fila** (que permite a troca de atualização na fila para atualização imediata) quando a assinatura é criada.</span><span class="sxs-lookup"><span data-stu-id="83ea0-115">To change the update mode after the subscription is created, the **update_mode** property must be set to **failover** (which allows a switch from immediate updating to queued updating) or **queued failover** (which allows a switch from queued updating to immediate updating) when the subscription is created.</span></span> <span data-ttu-id="83ea0-116">Essas propriedades são definidas automaticamente no Assistente para Nova Assinatura.</span><span class="sxs-lookup"><span data-stu-id="83ea0-116">These properties are set automatically in the New Subscription Wizard.</span></span>  
  
#### <a name="to-set-the-updating-mode-for-a-push-subscription"></a><span data-ttu-id="83ea0-117">Para definir o modo de atualização para uma assinatura push</span><span class="sxs-lookup"><span data-stu-id="83ea0-117">To set the updating mode for a push subscription</span></span>  
  
1.  <span data-ttu-id="83ea0-118">Conecte-se ao Assinante no [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]e expanda o nó do servidor.</span><span class="sxs-lookup"><span data-stu-id="83ea0-118">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="83ea0-119">Expanda a pasta **Replicação** e, então, expanda a pasta **Assinaturas Locais** .</span><span class="sxs-lookup"><span data-stu-id="83ea0-119">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="83ea0-120">Clique com o botão direito na assinatura para a qual se quer definir o modo de atualização e, então, clique em **Configurar Método de Atualização**.</span><span class="sxs-lookup"><span data-stu-id="83ea0-120">Right-click the subscription for which you want to set the update mode, and then click **Set Update Method**.</span></span>  
  
4.  <span data-ttu-id="83ea0-121">Na caixa de diálogo **Configurar Método de Atualização – \<Subscriber>: \<SubscriptionDatabase>** , selecione **Atualização imediata** ou **Atualização na fila**.</span><span class="sxs-lookup"><span data-stu-id="83ea0-121">In the **Set Update Method - \<Subscriber>: \<SubscriptionDatabase>** dialog box, select **Immediate updating** or **Queued updating**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
#### <a name="to-set-the-updating-mode-for-a-pull-subscription"></a><span data-ttu-id="83ea0-122">Para definir o modo de atualização para uma assinatura pull</span><span class="sxs-lookup"><span data-stu-id="83ea0-122">To set the updating mode for a pull subscription</span></span>  
  
1.  <span data-ttu-id="83ea0-123">Na caixa de diálogo **Propriedades de Assinatura – \<Publisher>: \<PublicationDatabase>** , selecione um valor de **Replicar as atualizações imediatamente** ou **Enfileirar alterações** para a opção **Método de atualização do assinante**.</span><span class="sxs-lookup"><span data-stu-id="83ea0-123">In the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box, select a value of **Immediately replicate changes** or **Queue changes** for the **Subscriber update method** option.</span></span>  
  
2.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
 <span data-ttu-id="83ea0-124">Para obter mais informações sobre como acessar a caixa de diálogo **Propriedades da Assinatura – \<Publisher>: \<PublicationDatabase>** , confira [Exibir e modificar propriedades de assinatura pull](../view-and-modify-pull-subscription-properties.md).</span><span class="sxs-lookup"><span data-stu-id="83ea0-124">For more information about accessing the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box, see [View and Modify Pull Subscription Properties](../view-and-modify-pull-subscription-properties.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="83ea0-125">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="83ea0-125">Using Transact-SQL</span></span>  
  
#### <a name="to-switch-between-update-modes"></a><span data-ttu-id="83ea0-126">Para alternar entre modos de atualização</span><span class="sxs-lookup"><span data-stu-id="83ea0-126">To switch between update modes</span></span>  
  
1.  <span data-ttu-id="83ea0-127">Verifique se a assinatura oferece suporte para failover executando [sp_helppullsubscription](/sql/relational-databases/system-stored-procedures/sp-helppullsubscription-transact-sql) para uma assinatura pull ou [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql) para uma assinatura push.</span><span class="sxs-lookup"><span data-stu-id="83ea0-127">Verify that the subscription supports failover by executing [sp_helppullsubscription](/sql/relational-databases/system-stored-procedures/sp-helppullsubscription-transact-sql) for a pull subscription or [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql) for a push subscription.</span></span> <span data-ttu-id="83ea0-128">Se o valor do **modo de atualização** no conjunto de resultados for **3** ou **4**, há suporte para failover.</span><span class="sxs-lookup"><span data-stu-id="83ea0-128">If the value of **update mode** in the result set is **3** or **4**, failover is supported.</span></span>  
  
2.  <span data-ttu-id="83ea0-129">No Assinante, no banco de dados da assinatura, execute [sp_setreplfailovermode](/sql/relational-databases/system-stored-procedures/sp-setreplfailovermode-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="83ea0-129">At the Subscriber on the subscription database, execute [sp_setreplfailovermode](/sql/relational-databases/system-stored-procedures/sp-setreplfailovermode-transact-sql).</span></span> <span data-ttu-id="83ea0-130">Especifique **@publisher** , **@publisher_db** , **@publication** e um dos seguintes valores para **@failover_mode** :</span><span class="sxs-lookup"><span data-stu-id="83ea0-130">Specify **@publisher**, **@publisher_db**, **@publication**, and one of the following values for **@failover_mode**:</span></span>  
  
    -   <span data-ttu-id="83ea0-131">**em fila** - failover para atualização em fila quando a conectividade for perdida temporariamente.</span><span class="sxs-lookup"><span data-stu-id="83ea0-131">**queued** - fail over to queued updating when connectivity has been temporarily lost.</span></span>  
  
    -   <span data-ttu-id="83ea0-132">**imediato** - failover para a atualização imediata quando conectividade for restaurada.</span><span class="sxs-lookup"><span data-stu-id="83ea0-132">**immediate** - fail over to immediate updating when connectivity has been restored.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83ea0-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="83ea0-133">See Also</span></span>  
 [<span data-ttu-id="83ea0-134">Updatable Subscriptions for Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="83ea0-134">Updatable Subscriptions for Transactional Replication</span></span>](../transactional/updatable-subscriptions-for-transactional-replication.md)  
  
  
