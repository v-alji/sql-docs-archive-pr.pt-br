---
title: Inicializar assinaturas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.initializesubscriptions.f1
ms.assetid: 7b170e4e-470d-4828-a9ed-7435b0b03514
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f8c9388138ddec275dc1abd2b75e0b0c7fc99de4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569874"
---
# <a name="initialize-subscriptions"></a><span data-ttu-id="1e221-102">Inicializar Assinaturas</span><span class="sxs-lookup"><span data-stu-id="1e221-102">Initialize Subscriptions</span></span>
  <span data-ttu-id="1e221-103">Os Assinantes devem ser inicializados antes que possam começar a receber dados replicados.</span><span class="sxs-lookup"><span data-stu-id="1e221-103">Subscribers must be initialized before they can begin receiving replicated data.</span></span> <span data-ttu-id="1e221-104">Um conjunto de dados inicial não é requerido, mas o Assinante deve ter pelo menos o esquema para cada objeto replicado e todas as tabelas de metadados e procedimentos requeridos pela replicação.</span><span class="sxs-lookup"><span data-stu-id="1e221-104">An initial dataset is not required, but the Subscriber must at least have the schema for each replicated object and any metadata tables and procedures required by replication.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1e221-105">Opções</span><span class="sxs-lookup"><span data-stu-id="1e221-105">Options</span></span>  
 <span data-ttu-id="1e221-106">**Propriedades da assinatura**</span><span class="sxs-lookup"><span data-stu-id="1e221-106">**Subscription properties**</span></span>  
 <span data-ttu-id="1e221-107">Marque a caixa de seleção na coluna **Inicializar** para cada Assinante que requer um conjunto de dados inicial.</span><span class="sxs-lookup"><span data-stu-id="1e221-107">Select the check box in the **Initialize** column for each Subscriber that requires an initial data set.</span></span> <span data-ttu-id="1e221-108">Se a caixa de seleção for desmarcada, somente os metadados de replicação e procedimentos serão inicializados.</span><span class="sxs-lookup"><span data-stu-id="1e221-108">If the check box is cleared, only the replication metadata and procedures will be initialized.</span></span> <span data-ttu-id="1e221-109">Para mais informações sobre a inicialização de uma assinatura sem um instantâneo, consulte [Inicializar uma assinatura transacional sem um instantâneo](initialize-a-transactional-subscription-without-a-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="1e221-109">For more information about initializing a subscription without a snapshot, see [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span></span>  
  
 <span data-ttu-id="1e221-110">Selecione **Imediatamente** na caixa de listagem suspensa na coluna **Inicializar Quando** para que o Agente de Mesclagem ou Agente de Distribuição transfira os arquivos de instantâneo para o Assinante depois que o assistente for concluído.</span><span class="sxs-lookup"><span data-stu-id="1e221-110">Select **Immediately** from the drop-down list box in the **Initialize When** column to have the Merge Agent or Distribution Agent transfer snapshot files to the Subscriber after this wizard is completed.</span></span> <span data-ttu-id="1e221-111">Selecione **Na primeira sincronização** para que o agente transfira os arquivos da próxima vez em que for agendado para executar.</span><span class="sxs-lookup"><span data-stu-id="1e221-111">Select **At first synchronization** to have the agent transfer the files the next time it is scheduled to run.</span></span> <span data-ttu-id="1e221-112">A opção **Imediatamente** não está disponível para assinaturas pull no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e221-112">The **Immediately** option is not available for pull subscriptions to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span> <span data-ttu-id="1e221-113">O Agente de Mesclagem e Agente de Distribuição não executam em instâncias do [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]; portanto a assinatura deve ser reiniciada por outro método.</span><span class="sxs-lookup"><span data-stu-id="1e221-113">The Merge Agent and Distribution Agent do not run on instances of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]; therefore the subscription must be initialized through another method.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1e221-114">O assistente pode solicitar uma conexão com o Distribuidor para iniciar o trabalho apropriado para o Agente de Distribuição ou Agente de Mesclagem.</span><span class="sxs-lookup"><span data-stu-id="1e221-114">The wizard might prompt for a connection to the Distributor in order to start the appropriate job for the Distribution Agent or Merge Agent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e221-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1e221-115">See Also</span></span>  
 <span data-ttu-id="1e221-116">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="1e221-116">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="1e221-117">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="1e221-117">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 <span data-ttu-id="1e221-118">[Inicializar uma assinatura](initialize-a-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="1e221-118">[Initialize a Subscription](initialize-a-subscription.md) </span></span>  
 [<span data-ttu-id="1e221-119">Assinar publicações</span><span class="sxs-lookup"><span data-stu-id="1e221-119">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
