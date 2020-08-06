---
title: Republicar dados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- republishing data
- publishing [SQL Server replication], Subscribers
- Subscribers [SQL Server replication], republishing data
ms.assetid: a1485cf4-b1c4-49e9-ab06-8ccfaad998f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f1e4213266121b3bf55bf2857e15f71f1e94e301
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569320"
---
# <a name="republish-data"></a><span data-ttu-id="89aae-102">Republicar dados</span><span class="sxs-lookup"><span data-stu-id="89aae-102">Republish Data</span></span>
  <span data-ttu-id="89aae-103">Em um modelo de republicação, o Publicador envia dados a um Assinante, que então republica os dados para qualquer número de outros Assinantes.</span><span class="sxs-lookup"><span data-stu-id="89aae-103">In a republishing model, the Publisher sends data to a Subscriber, which then republishes the data to any number of other Subscribers.</span></span> <span data-ttu-id="89aae-104">Isso é útil quando um Publicador precisa enviar dados a Assinantes por um link de comunicação lento ou caro.</span><span class="sxs-lookup"><span data-stu-id="89aae-104">This is useful when a Publisher must send data to Subscribers over a slow or expensive communications link.</span></span> <span data-ttu-id="89aae-105">Se houver um número de Assinantes na extremidade daquele link, o uso de um republicador alterna a massa da carga de distribuição àquele lado do link.</span><span class="sxs-lookup"><span data-stu-id="89aae-105">If there are a number of Subscribers on the far side of that link, using a republisher shifts the bulk of the distribution load to that side of the link.</span></span>  
  
 <span data-ttu-id="89aae-106">Republicar dados envolve as etapas seguintes:</span><span class="sxs-lookup"><span data-stu-id="89aae-106">Republishing data involves the following steps:</span></span>  
  
1.  <span data-ttu-id="89aae-107">Crie uma publicação no Publicador.</span><span class="sxs-lookup"><span data-stu-id="89aae-107">Create a publication at the Publisher.</span></span>  
  
2.  <span data-ttu-id="89aae-108">Crie uma assinatura à publicação para o Assinante de republicação.</span><span class="sxs-lookup"><span data-stu-id="89aae-108">Create a subscription to the publication for the republishing Subscriber.</span></span>  
  
3.  <span data-ttu-id="89aae-109">Inicialize a assinatura.</span><span class="sxs-lookup"><span data-stu-id="89aae-109">Initialize the subscription.</span></span> <span data-ttu-id="89aae-110">A assinatura deve ser inicializada antes de a publicação ser criada no Assinante de republicação ou a replicação falhará.</span><span class="sxs-lookup"><span data-stu-id="89aae-110">The subscription must be initialized before the publication is created at the republishing Subscriber, or replication will fail.</span></span>  
  
4.  <span data-ttu-id="89aae-111">Crie uma publicação no banco de dados de assinatura do Assinante de republicação.</span><span class="sxs-lookup"><span data-stu-id="89aae-111">Create a publication in the subscription database at the republishing Subscriber.</span></span>  
  
5.  <span data-ttu-id="89aae-112">Crie assinaturas à publicação no Assinante de republicação para os outros Assinantes.</span><span class="sxs-lookup"><span data-stu-id="89aae-112">Create subscriptions to the publication at the republishing Subscriber for the other Subscribers.</span></span>  
  
6.  <span data-ttu-id="89aae-113">Inicialize as assinaturas.</span><span class="sxs-lookup"><span data-stu-id="89aae-113">Initialize the subscriptions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89aae-114">Se você usar replicação de mesclagem em uma topologia de republicação, todos os Assinantes de republicação deverão usar assinatura de servidor.</span><span class="sxs-lookup"><span data-stu-id="89aae-114">If you use merge replication in a republishing topology, all republishing Subscribers must use server subscriptions.</span></span> <span data-ttu-id="89aae-115">Para obter mais informações sobre tipos de assinaturas, veja [Assinar Publicações](subscribe-to-publications.md).</span><span class="sxs-lookup"><span data-stu-id="89aae-115">For more information about subscription types, see [Subscribe to Publications](subscribe-to-publications.md).</span></span>  
  
 <span data-ttu-id="89aae-116">Na ilustração a seguir, o Publicador e o republicador estão agindo como os seus próprios Distribuidores locais.</span><span class="sxs-lookup"><span data-stu-id="89aae-116">In the following illustration, both the Publisher and the republisher are acting as their own local Distributors.</span></span> <span data-ttu-id="89aae-117">Se cada um fosse definido para usar um Distribuidor remoto, cada Distribuidor precisaria estar do mesmo lado do link de comunicações lento ou caro do seu Publicador.</span><span class="sxs-lookup"><span data-stu-id="89aae-117">If each were set up to use a remote Distributor, each Distributor would need to be on the same side of the slow or expensive communications link as its Publisher.</span></span> <span data-ttu-id="89aae-118">Os Publicadores devem ser conectados a Distribuidores remotos por links de comunicação confiáveis, de alta velocidade.</span><span class="sxs-lookup"><span data-stu-id="89aae-118">Publishers must be connected to remote Distributors by reliable, high-speed communications links.</span></span>  
  
 <span data-ttu-id="89aae-119">![Republicar dados](media/repl-06a.gif "Republicar dados")</span><span class="sxs-lookup"><span data-stu-id="89aae-119">![Republishing data](media/repl-06a.gif "Republishing data")</span></span>  
  
 <span data-ttu-id="89aae-120">Qualquer servidor pode agir como um Publicador e Assinante.</span><span class="sxs-lookup"><span data-stu-id="89aae-120">Any server can act as both a Publisher and Subscriber.</span></span> <span data-ttu-id="89aae-121">Por exemplo, considere o diagrama a seguir em que uma publicação de uma tabela existe em Londres e deverá ser distribuída a quatro cidades diferentes nos Estados Unidos: Chicago, Nova Iorque, San Diego e Seattle.</span><span class="sxs-lookup"><span data-stu-id="89aae-121">For example, consider the following diagram in which a publication of a table exists in London and must be distributed to four different cities in the United States: Chicago, New York, San Diego, and Seattle.</span></span> <span data-ttu-id="89aae-122">O servidor em Nova Iorque é escolhido para assinar a tabela publicada originada em Londres, porque o site de Nova Iorque atende às seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="89aae-122">The server in New York is chosen to subscribe to the published table originating in London, because the New York site meets these conditions:</span></span>  
  
-   <span data-ttu-id="89aae-123">O link de retorno da rede para Londres é relativamente confiável.</span><span class="sxs-lookup"><span data-stu-id="89aae-123">The network link back to London is relatively reliable.</span></span>  
  
-   <span data-ttu-id="89aae-124">Os custos de comunicação de Londres para Nova Iorque são aceitáveis.</span><span class="sxs-lookup"><span data-stu-id="89aae-124">The London-to-New York communication costs are acceptable.</span></span>  
  
-   <span data-ttu-id="89aae-125">Existem boas linhas de comunicações de rede de Nova Iorque para todos os outros sites de Assinante nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="89aae-125">There are good network communications lines from New York to all other Subscriber sites in the United States.</span></span>  
  
     <span data-ttu-id="89aae-126">![Republicar dados em locais dispersos](media/repl-06.gif "Republicar dados em locais dispersos")</span><span class="sxs-lookup"><span data-stu-id="89aae-126">![Republishing data to dispersed locations](media/repl-06.gif "Republishing data to dispersed locations")</span></span>  
  
 <span data-ttu-id="89aae-127">A replicação fornece suporte aos cenários de republicação mostrados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="89aae-127">Replication supports the republishing scenarios shown in the following table.</span></span>  
  
|<span data-ttu-id="89aae-128">Publicador</span><span class="sxs-lookup"><span data-stu-id="89aae-128">Publisher</span></span>|<span data-ttu-id="89aae-129">Assinante de publicação</span><span class="sxs-lookup"><span data-stu-id="89aae-129">Publishing Subscriber</span></span>|<span data-ttu-id="89aae-130">Subscriber</span><span class="sxs-lookup"><span data-stu-id="89aae-130">Subscriber</span></span>|  
|---------------|---------------------------|----------------|  
|<span data-ttu-id="89aae-131">Publicação transacional</span><span class="sxs-lookup"><span data-stu-id="89aae-131">Transactional publication</span></span>|<span data-ttu-id="89aae-132">Assinatura transacional/publicação transacional</span><span class="sxs-lookup"><span data-stu-id="89aae-132">Transactional subscription/transactional publication</span></span>|<span data-ttu-id="89aae-133">Assinatura transacional</span><span class="sxs-lookup"><span data-stu-id="89aae-133">Transactional subscription</span></span>|  
|<span data-ttu-id="89aae-134">Publicação transacional</span><span class="sxs-lookup"><span data-stu-id="89aae-134">Transactional publication</span></span>|<span data-ttu-id="89aae-135">Assinatura transacional/publicação de mesclagem<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="89aae-135">Transactional subscription/merge publication<sup>1</sup></span></span>|<span data-ttu-id="89aae-136">Assinatura de mesclagem</span><span class="sxs-lookup"><span data-stu-id="89aae-136">Merge subscription</span></span>|  
|<span data-ttu-id="89aae-137">Publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="89aae-137">Merge publication</span></span>|<span data-ttu-id="89aae-138">Assinatura de mesclagem/publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="89aae-138">Merge subscription/merge publication</span></span>|<span data-ttu-id="89aae-139">Assinatura de mesclagem</span><span class="sxs-lookup"><span data-stu-id="89aae-139">Merge subscription</span></span>|  
|<span data-ttu-id="89aae-140">Publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="89aae-140">Merge publication</span></span>|<span data-ttu-id="89aae-141">Assinatura de mesclagem/publicação transacional</span><span class="sxs-lookup"><span data-stu-id="89aae-141">Merge subscription/transactional publication</span></span>|<span data-ttu-id="89aae-142">Assinatura transacional</span><span class="sxs-lookup"><span data-stu-id="89aae-142">Transactional subscription</span></span>|  
  
 <span data-ttu-id="89aae-143"><sup>1</sup> Você deve definir a `@published_in_tran_pub` Propriedade na publicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="89aae-143"><sup>1</sup>You should set the `@published_in_tran_pub` property on the merge publication.</span></span> <span data-ttu-id="89aae-144">Por padrão, a replicação transacional espera que as tabelas no Assinante sejam tratadas como somente leitura.</span><span class="sxs-lookup"><span data-stu-id="89aae-144">By default, transactional replication expects tables at the Subscriber to be treated as read-only.</span></span> <span data-ttu-id="89aae-145">Se a replicação de mesclagem fizer alterações de dados de uma tabela em uma assinatura transacional, poderá ocorrer não convergência de dados.</span><span class="sxs-lookup"><span data-stu-id="89aae-145">If merge replication makes data changes to a table in a transactional subscription, non-convergence of data can occur.</span></span> <span data-ttu-id="89aae-146">Para evitar esse risco, recomendamos que qualquer tabela desse tipo seja especificada como somente para download na publicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="89aae-146">To avoid this risk, we recommend that any such table be specified as download-only in the merge publication.</span></span> <span data-ttu-id="89aae-147">Isso impede que um Assinante de mesclagem carregue alterações de dados na tabela.</span><span class="sxs-lookup"><span data-stu-id="89aae-147">This prevents a merge Subscriber from uploading data changes to the table.</span></span> <span data-ttu-id="89aae-148">Para obter mais informações, consulte [Otimizar o desempenho da replicação de mesclagem com artigos somente para download](merge/optimize-merge-replication-performance-with-download-only-articles.md).</span><span class="sxs-lookup"><span data-stu-id="89aae-148">For more information, see [Optimize Merge Replication Performance with Download-Only Articles](merge/optimize-merge-replication-performance-with-download-only-articles.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89aae-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="89aae-149">See Also</span></span>  
 <span data-ttu-id="89aae-150">[Configurar Distribuição](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="89aae-150">[Configure Distribution](configure-distribution.md) </span></span>  
 <span data-ttu-id="89aae-151">[Publicar dados e objetos de banco de dados](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="89aae-151">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 <span data-ttu-id="89aae-152">[Subscribe to Publications](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="89aae-152">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 <span data-ttu-id="89aae-153">[Inicializar uma assinatura](initialize-a-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="89aae-153">[Initialize a Subscription](initialize-a-subscription.md) </span></span>  
 [<span data-ttu-id="89aae-154">Sincronizar dados</span><span class="sxs-lookup"><span data-stu-id="89aae-154">Synchronize Data</span></span>](synchronize-data.md)  
  
  
