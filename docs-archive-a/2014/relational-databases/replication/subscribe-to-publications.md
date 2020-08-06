---
title: Assinar publicações | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.conc.subtopubs.f1
helpviewer_keywords:
- subscriptions [SQL Server replication], about subscriptions
- pull subscriptions [SQL Server replication]
- subscriptions [SQL Server replication]
- push subscriptions [SQL Server replication], about push subscriptions
- merge replication subscribing [SQL Server replication]
- merge replication subscribing [SQL Server replication], about subscribing
- publications [SQL Server replication], subscribing
- push subscriptions [SQL Server replication]
- pull subscriptions [SQL Server replication], about pull subscriptions
- snapshot replication [SQL Server], subscribing
- transactional replication, subscribing
ms.assetid: 088ee30a-05ab-47c4-92ed-316b93e12445
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c565aae26c6d549eb67043168797d5fb059c8e2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569313"
---
# <a name="subscribe-to-publications"></a><span data-ttu-id="2f011-102">Assinar publicações</span><span class="sxs-lookup"><span data-stu-id="2f011-102">Subscribe to Publications</span></span>
  <span data-ttu-id="2f011-103">Uma assinatura é uma solicitação para se obter uma cópia dos dados e objetos do banco de dados em uma publicação.</span><span class="sxs-lookup"><span data-stu-id="2f011-103">A subscription is a request for a copy of the data and database objects in a publication.</span></span> <span data-ttu-id="2f011-104">Uma assinatura define qual publicação será recebida, e onde e quando será recebida.</span><span class="sxs-lookup"><span data-stu-id="2f011-104">A subscription defines which publication will be received, and where and when it will be received.</span></span> <span data-ttu-id="2f011-105">Ao planejar assinaturas, considere onde o processamento de agente deverá acontecer.</span><span class="sxs-lookup"><span data-stu-id="2f011-105">When planning for subscriptions, consider where you want agent processing to occur.</span></span> <span data-ttu-id="2f011-106">O tipo de assinatura selecionado controla onde o agente é executado.</span><span class="sxs-lookup"><span data-stu-id="2f011-106">The type of subscription you choose controls where the agent runs.</span></span> <span data-ttu-id="2f011-107">Com uma assinatura push, o Agente de Mesclagem ou o Agente de Distribuição são executados no Distribuidor, enquanto que, com uma assinatura pull, os agentes são executados nos Assinantes.</span><span class="sxs-lookup"><span data-stu-id="2f011-107">With a push subscription, the Merge Agent or Distribution Agent runs at the Distributor, whereas with a pull subscription, agents run at the Subscribers.</span></span> <span data-ttu-id="2f011-108">Após a criação de uma assinatura, ela não pode ser alterada de um tipo para outro.</span><span class="sxs-lookup"><span data-stu-id="2f011-108">After a subscription is created, it cannot be changed from one type to another.</span></span>  
  
|<span data-ttu-id="2f011-109">Subscription</span><span class="sxs-lookup"><span data-stu-id="2f011-109">Subscription</span></span>|<span data-ttu-id="2f011-110">Características</span><span class="sxs-lookup"><span data-stu-id="2f011-110">Characteristics</span></span>|<span data-ttu-id="2f011-111">Use quando</span><span class="sxs-lookup"><span data-stu-id="2f011-111">Use When</span></span>|  
|------------------|---------------------|--------------|  
|<span data-ttu-id="2f011-112">Assinatura push</span><span class="sxs-lookup"><span data-stu-id="2f011-112">Push Subscription</span></span>|<span data-ttu-id="2f011-113">Em uma assinatura push, o Publicador propaga alterações para o Assinante sem solicitação do Assinante.</span><span class="sxs-lookup"><span data-stu-id="2f011-113">With a push subscription, the Publisher propagates changes to a Subscriber without a request from the Subscriber.</span></span> <span data-ttu-id="2f011-114">As alterações podem ser empurradas para os Assinantes sob demanda continuamente ou com base em agendamento.</span><span class="sxs-lookup"><span data-stu-id="2f011-114">Changes can be pushed to Subscribers on demand, continuously, or on a scheduled basis.</span></span> <span data-ttu-id="2f011-115">O Agente de Distribuição ou o Agente de Mesclagem são executados no Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="2f011-115">The Distribution Agent or Merge Agent runs at the Distributor.</span></span>|<span data-ttu-id="2f011-116">Os dados são sincronizados de forma contínua ou com base em uma agenda que recorre com frequência.</span><span class="sxs-lookup"><span data-stu-id="2f011-116">Data will typically be synchronized continuously or on a frequently recurring schedule.</span></span><br /><br /> <span data-ttu-id="2f011-117">As publicações requerem movimentação de dados tempo quase real.</span><span class="sxs-lookup"><span data-stu-id="2f011-117">Publications require near real-time movement of data.</span></span><br /><br /> <span data-ttu-id="2f011-118">A sobrecarga do processador superior no Distribuidor não afeta o desempenho.</span><span class="sxs-lookup"><span data-stu-id="2f011-118">The higher processor overhead at the Distributor does not affect performance.</span></span><br /><br /> <span data-ttu-id="2f011-119">É usado com mais frequência com replicação transacional e de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="2f011-119">Most often used with snapshot and transactional replication.</span></span>|  
|<span data-ttu-id="2f011-120">Assinatura pull</span><span class="sxs-lookup"><span data-stu-id="2f011-120">Pull Subscription</span></span>|<span data-ttu-id="2f011-121">Em uma assinatura pull, o Assinante solicita que alterações sejam feitas no Publicador.</span><span class="sxs-lookup"><span data-stu-id="2f011-121">With a pull subscription, the Subscriber requests changes made at the Publisher.</span></span> <span data-ttu-id="2f011-122">As assinaturas pull permitem que o usuário, no Assinante, determine quando as alterações de dados serão sincronizadas.</span><span class="sxs-lookup"><span data-stu-id="2f011-122">Pull subscriptions allow the user at the Subscriber to determine when the data changes are synchronized.</span></span> <span data-ttu-id="2f011-123">O Agente de Distribuição ou o Agente de Mesclagem são executados no Assinante.</span><span class="sxs-lookup"><span data-stu-id="2f011-123">The Distribution Agent or the Merge Agent runs at the Subscriber.</span></span>|<span data-ttu-id="2f011-124">Em geral, os dados são sincronizados sob demanda ou com base em uma agenda, em vez de continuamente.</span><span class="sxs-lookup"><span data-stu-id="2f011-124">Data will typically be synchronized on demand or on a schedule rather than continuously.</span></span><br /><br /> <span data-ttu-id="2f011-125">A publicação tem um grande número de Assinantes, e/ou demandaria muitos recursos para executar todos os agentes no Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="2f011-125">The publication has a large number of Subscribers, and/or it would be too resource-intensive to run all the agents at the Distributor.</span></span><br /><br /> <span data-ttu-id="2f011-126">Os assinantes são autônomos, desconectados, e/ou móveis.</span><span class="sxs-lookup"><span data-stu-id="2f011-126">Subscribers are autonomous, disconnected, and/or mobile.</span></span> <span data-ttu-id="2f011-127">Os assinantes determinam quando as alterações são conectadas e sincronizadas.</span><span class="sxs-lookup"><span data-stu-id="2f011-127">Subscribers will determine when they will connect and synchronize changes.</span></span><br /><br /> <span data-ttu-id="2f011-128">Usado com mais frequência com replicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="2f011-128">Most often used with merge replication.</span></span>|  
  
## <a name="merge-replication-subscription-types"></a><span data-ttu-id="2f011-129">Tipos de assinatura de replication de mesclagem</span><span class="sxs-lookup"><span data-stu-id="2f011-129">Merge Replication Subscription Types</span></span>  
 <span data-ttu-id="2f011-130">Todos os tipos de replicação permitem assinaturas push e pull.</span><span class="sxs-lookup"><span data-stu-id="2f011-130">All replication types allow push and pull subscriptions.</span></span> <span data-ttu-id="2f011-131">A replicação de mesclagem usa duas condições a mais para distinguir assinaturas: assinatura de cliente e assinatura de servidor.</span><span class="sxs-lookup"><span data-stu-id="2f011-131">Merge replication uses two additional terms to distinguish subscriptions: client subscriptions and server subscriptions.</span></span> <span data-ttu-id="2f011-132">Os tipos de assinatura de cliente e de servidor podem ser usados com assinaturas push e pull.</span><span class="sxs-lookup"><span data-stu-id="2f011-132">Both client and server subscription types can be used with push and pull subscriptions.</span></span> <span data-ttu-id="2f011-133">As assinaturas de cliente são apropriadas para a maioria dos Assinantes, enquanto que as assinaturas de servidor são usadas, em geral, para Assinantes que republicam dados em outros Assinantes.</span><span class="sxs-lookup"><span data-stu-id="2f011-133">Client subscriptions are appropriate for most Subscribers, whereas server subscriptions are typically used for Subscribers that republish data to other Subscribers.</span></span> <span data-ttu-id="2f011-134">A opção de assinatura também afeta a resolução de conflitos.</span><span class="sxs-lookup"><span data-stu-id="2f011-134">Subscription choice also affects conflict resolution.</span></span>  
  
## <a name="non-sql-server-subscribers"></a><span data-ttu-id="2f011-135">Non-SQL Server Subscribers</span><span class="sxs-lookup"><span data-stu-id="2f011-135">Non-SQL Server Subscribers</span></span>  
 <span data-ttu-id="2f011-136">O Oracle e o IBM DB2 podem assinar as publicações de instantâneo e transacionais usando assinaturas push.</span><span class="sxs-lookup"><span data-stu-id="2f011-136">Oracle and IBM DB2 can subscribe to snapshot and transactional publications using push subscriptions.</span></span> <span data-ttu-id="2f011-137">Para obter mais informações, consulte [Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md).</span><span class="sxs-lookup"><span data-stu-id="2f011-137">For more information, see [Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md).</span></span>  
  
## <a name="creating-subscriptions"></a><span data-ttu-id="2f011-138">Criando assinaturas</span><span class="sxs-lookup"><span data-stu-id="2f011-138">Creating Subscriptions</span></span>  
 <span data-ttu-id="2f011-139">Para criar uma assinatura, forneça as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="2f011-139">To create a subscription, you supply the following information:</span></span>  
  
-   <span data-ttu-id="2f011-140">O nome da publicação.</span><span class="sxs-lookup"><span data-stu-id="2f011-140">The name of the publication.</span></span>  
  
-   <span data-ttu-id="2f011-141">Nome do Assinante e o banco de dados de assinatura.</span><span class="sxs-lookup"><span data-stu-id="2f011-141">The name of the Subscriber and the subscription database.</span></span>  
  
-   <span data-ttu-id="2f011-142">Se o Agente de Distribuição ou o Agente de Mesclagem forem executados no Distribuidor ou no Assinante.</span><span class="sxs-lookup"><span data-stu-id="2f011-142">Whether the Distribution Agent or Merge Agent runs at the Distributor or at the Subscriber.</span></span>  
  
-   <span data-ttu-id="2f011-143">Se o Agente de Distribuição ou Agente de Mesclagem forem executados de forma contínua, com base em uma agenda ou somente sob demanda.</span><span class="sxs-lookup"><span data-stu-id="2f011-143">Whether the Distribution Agent or Merge Agent runs continuously, on a scheduled basis, or on demand only.</span></span>  
  
-   <span data-ttu-id="2f011-144">Se o Agente de Instantâneo precisar criar um instantâneo inicial para a assinatura e se o Agente de Distribuição ou Agente de Mesclagem devem aplicar esse instantâneo no Assinante.</span><span class="sxs-lookup"><span data-stu-id="2f011-144">Whether the Snapshot Agent should create an initial snapshot for the subscription and whether the Distribution Agent or Merge Agent should apply that snapshot at the Subscriber.</span></span>  
  
-   <span data-ttu-id="2f011-145">As contas nas quais o Agente de Distribuição ou Agente de Mesclagem serão executados.</span><span class="sxs-lookup"><span data-stu-id="2f011-145">Accounts under which the Distribution Agent or Merge Agent will run.</span></span>  
  
-   <span data-ttu-id="2f011-146">Com relação à replicação de mesclagem, o tipo de assinatura: de servidor ou cliente.</span><span class="sxs-lookup"><span data-stu-id="2f011-146">For merge replication, the type of subscription: server or client.</span></span>  
  
 <span data-ttu-id="2f011-147">**Para criar uma assinatura push**</span><span class="sxs-lookup"><span data-stu-id="2f011-147">**To create a push subscription**</span></span>  
  
 [<span data-ttu-id="2f011-148">Criar uma Assinatura Push</span><span class="sxs-lookup"><span data-stu-id="2f011-148">Create a Push Subscription</span></span>](create-a-push-subscription.md)  
  
 <span data-ttu-id="2f011-149">**Para exibir ou modificar propriedades de assinatura push**</span><span class="sxs-lookup"><span data-stu-id="2f011-149">**To view or modify push subscription properties**</span></span>  
  
 [<span data-ttu-id="2f011-150">Exibir e modificar propriedades de assinatura push</span><span class="sxs-lookup"><span data-stu-id="2f011-150">View and Modify Push Subscription Properties</span></span>](view-and-modify-push-subscription-properties.md)  
  
 <span data-ttu-id="2f011-151">**Para excluir uma assinatura push**</span><span class="sxs-lookup"><span data-stu-id="2f011-151">**To delete a push subscription**</span></span>  
  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="2f011-152">: [Excluir uma assinatura push](delete-a-push-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="2f011-152">: [Delete a Push Subscription](delete-a-push-subscription.md)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f011-153">Excluir uma assinatura não remove objetos publicados no Assinante.</span><span class="sxs-lookup"><span data-stu-id="2f011-153">Deleting a subscription does not remove published objects from the Subscriber.</span></span>  
  
 <span data-ttu-id="2f011-154">**Para criar uma assinatura pull**</span><span class="sxs-lookup"><span data-stu-id="2f011-154">**To create a pull subscription**</span></span>  
  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="2f011-155">: [Criar uma assinatura pull](create-a-pull-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="2f011-155">: [Create a Pull Subscription](create-a-pull-subscription.md)</span></span>  
  
 <span data-ttu-id="2f011-156">**Para exibir ou modificar propriedades de assinatura pull**</span><span class="sxs-lookup"><span data-stu-id="2f011-156">**To view or modify pull subscription properties**</span></span>  
  
 [<span data-ttu-id="2f011-157">Exibir e modificar propriedades de assinatura pull</span><span class="sxs-lookup"><span data-stu-id="2f011-157">View and Modify Pull Subscription Properties</span></span>](view-and-modify-pull-subscription-properties.md)  
  
 <span data-ttu-id="2f011-158">**Para excluir uma assinatura pull**</span><span class="sxs-lookup"><span data-stu-id="2f011-158">**To delete a pull subscription**</span></span>  
  
 [<span data-ttu-id="2f011-159">Excluir uma assinatura pull</span><span class="sxs-lookup"><span data-stu-id="2f011-159">Delete a Pull Subscription</span></span>](delete-a-pull-subscription.md)  
  
## <a name="see-also"></a><span data-ttu-id="2f011-160">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2f011-160">See Also</span></span>  
 <span data-ttu-id="2f011-161">[Proteger o Assinante](security/secure-the-subscriber.md) </span><span class="sxs-lookup"><span data-stu-id="2f011-161">[Secure the Subscriber](security/secure-the-subscriber.md) </span></span>  
 [<span data-ttu-id="2f011-162">Desativação e expiração de assinatura</span><span class="sxs-lookup"><span data-stu-id="2f011-162">Subscription Expiration and Deactivation</span></span>](subscription-expiration-and-deactivation.md)  
  
  
