---
title: Snapshot Agent (Assistente para Nova Publicação) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.configuresnapshotagent.f1
ms.assetid: 0257d4ee-1f7b-49fd-b4ef-65bfc1ef6951
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c45fa3444fb2f81436a40a2bfb80519aea105c47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583490"
---
# <a name="snapshot-agent-new-publication-wizard"></a><span data-ttu-id="5aed3-102">Agente de Instantâneo (Assistente para Nova Publicação)</span><span class="sxs-lookup"><span data-stu-id="5aed3-102">Snapshot Agent (New Publication Wizard)</span></span>
  <span data-ttu-id="5aed3-103">O Agente de Instantâneo cria arquivos que contêm o esquema de publicação e os dados usados para inicializar novas assinaturas.</span><span class="sxs-lookup"><span data-stu-id="5aed3-103">The Snapshot Agent creates files containing the publication schema and data that are used to initialize new subscriptions.</span></span> <span data-ttu-id="5aed3-104">Por padrão, o Agente de Instantâneo é executado imediatamente depois que a publicação é criada no Assistente para Nova Publicação.</span><span class="sxs-lookup"><span data-stu-id="5aed3-104">By default, the Snapshot Agent runs immediately after the publication is created in the New Publication Wizard.</span></span> <span data-ttu-id="5aed3-105">Subsequentemente, o agente é executado de acordo com uma agenda especificada.</span><span class="sxs-lookup"><span data-stu-id="5aed3-105">Subsequently, the agent runs according to a schedule you specify.</span></span> <span data-ttu-id="5aed3-106">A criação de novos arquivos de instantâneo pelo agente depende do tipo de replicação e das opções escolhidas.</span><span class="sxs-lookup"><span data-stu-id="5aed3-106">Whether the agent creates new snapshot files each time it runs depends on the type of replication and options chosen.</span></span> <span data-ttu-id="5aed3-107">Para obter mais informações, consulte [Create and Apply the Snapshot](create-and-apply-the-snapshot.md) (Criar e aplicar o instantâneo).</span><span class="sxs-lookup"><span data-stu-id="5aed3-107">For more information, see [Create and Apply the Snapshot](create-and-apply-the-snapshot.md).</span></span>  
  
 <span data-ttu-id="5aed3-108">Para publicações de mesclagem que usam filtros com parâmetros, você deve criar um instantâneo para cada partição de dados após a conclusão do instantâneo de publicação.</span><span class="sxs-lookup"><span data-stu-id="5aed3-108">For merge publications that use parameterized filters, you must create a snapshot for each partition of data after the publication snapshot has completed.</span></span> <span data-ttu-id="5aed3-109">Para obter mais informações, consulte [Snapshots for Merge Publications with Parameterized Filters](snapshots-for-merge-publications-with-parameterized-filters.md).</span><span class="sxs-lookup"><span data-stu-id="5aed3-109">For more information, see [Snapshots for Merge Publications with Parameterized Filters](snapshots-for-merge-publications-with-parameterized-filters.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="5aed3-110">Opções</span><span class="sxs-lookup"><span data-stu-id="5aed3-110">Options</span></span>  
 <span data-ttu-id="5aed3-111">**Criar um instantâneo imediatamente** (publicação de mesclagem) ou **Criar um instantâneo imediatamente e mantê-lo disponível para inicializar assinaturas** (replicação transacional)</span><span class="sxs-lookup"><span data-stu-id="5aed3-111">**Create a snapshot immediately** (merge replication) or **Create a snapshot immediately and keep the snapshot available to initialize subscriptions** (transactional replication)</span></span>  
 <span data-ttu-id="5aed3-112">Marque essa caixa de seleção para criar um instantâneo imediatamente depois que o Assistente para Nova Publicação for concluído.</span><span class="sxs-lookup"><span data-stu-id="5aed3-112">Select this check box to create a snapshot immediately after the New Publication Wizard is completed.</span></span> <span data-ttu-id="5aed3-113">Desmarque essa caixa de seleção se você planejar alterar as propriedades do instantâneo na caixa de diálogo **Propriedades de Publicação** antes de gerar um instantâneo ou se inicializar o Assinante sem um instantâneo.</span><span class="sxs-lookup"><span data-stu-id="5aed3-113">Clear this check box if you plan to change snapshot properties in the **Publication Properties** dialog box before generating a snapshot, or if you will initialize the Subscriber without a snapshot.</span></span> <span data-ttu-id="5aed3-114">Para obter mais informações, consulte [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="5aed3-114">For more information, see [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5aed3-115">O assistente pode solicitar uma conexão com o Distribuidor para iniciar o trabalho apropriado para o Agente de Distribuição ou Agente de Mesclagem.</span><span class="sxs-lookup"><span data-stu-id="5aed3-115">The wizard might prompt for a connection to the Distributor in order to start the appropriate job for the Distribution Agent or Merge Agent.</span></span>  
  
 <span data-ttu-id="5aed3-116">**Agendar o Agente de Instantâneo para execução nos seguintes horários**</span><span class="sxs-lookup"><span data-stu-id="5aed3-116">**Schedule the Snapshot Agent to run at the following times**</span></span>  
 <span data-ttu-id="5aed3-117">Aceite a agenda padrão para execução do Agente de Instantâneo ou clique em **Alterar** para especificar uma agenda.</span><span class="sxs-lookup"><span data-stu-id="5aed3-117">Accept the default schedule for running the Snapshot Agent, or click **Change** to specify a schedule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5aed3-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5aed3-118">See Also</span></span>  
 <span data-ttu-id="5aed3-119">[Create a Publication](publish/create-a-publication.md) </span><span class="sxs-lookup"><span data-stu-id="5aed3-119">[Create a Publication](publish/create-a-publication.md) </span></span>  
 <span data-ttu-id="5aed3-120">[Criar e aplicar o instantâneo inicial](create-and-apply-the-initial-snapshot.md) </span><span class="sxs-lookup"><span data-stu-id="5aed3-120">[Create and Apply the Initial Snapshot](create-and-apply-the-initial-snapshot.md) </span></span>  
 <span data-ttu-id="5aed3-121">[Exibir e modificar as propriedades da publicação](publish/view-and-modify-publication-properties.md) </span><span class="sxs-lookup"><span data-stu-id="5aed3-121">[View and Modify Publication Properties](publish/view-and-modify-publication-properties.md) </span></span>  
 <span data-ttu-id="5aed3-122">[Inicializar uma assinatura com um instantâneo](initialize-a-subscription-with-a-snapshot.md) </span><span class="sxs-lookup"><span data-stu-id="5aed3-122">[Initialize a Subscription with a Snapshot](initialize-a-subscription-with-a-snapshot.md) </span></span>  
 <span data-ttu-id="5aed3-123">[Publicar dados e objetos de banco de dados](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="5aed3-123">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 [<span data-ttu-id="5aed3-124">Visão geral dos agentes de replicação</span><span class="sxs-lookup"><span data-stu-id="5aed3-124">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
