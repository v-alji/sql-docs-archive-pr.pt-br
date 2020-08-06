---
title: Assinaturas atualizáveis | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.updatablesubscriptions.f1
ms.assetid: 8e9a13a0-6b24-47c6-9d83-3cbaf08f673d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 447114152365e098420f46d4b7e880e8f2907864
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679848"
---
# <a name="updatable-subscriptions"></a><span data-ttu-id="bbf68-102">Assinaturas Atualizáveis</span><span class="sxs-lookup"><span data-stu-id="bbf68-102">Updatable Subscriptions</span></span>
  <span data-ttu-id="bbf68-103">Com a replicação transacional, os dados replicados devem ser tratados como somente leitura; no entanto, você pode modificá-los em um Assinante do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando assinaturas atualizáveis.</span><span class="sxs-lookup"><span data-stu-id="bbf68-103">With transactional replication, replicated data should be treated as read-only; however, you can modify replicated data at a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscriber by using updatable subscriptions.</span></span> <span data-ttu-id="bbf68-104">Se for necessário modificar dados no Assinante, escolha um das opções a seguir, dependendo de seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="bbf68-104">If you need to modify data at the Subscriber, choose one of the following options depending on your requirements.</span></span>  
  
|<span data-ttu-id="bbf68-105">Tipo de assinatura atualizável</span><span class="sxs-lookup"><span data-stu-id="bbf68-105">Updatable Subscription Type</span></span>|<span data-ttu-id="bbf68-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bbf68-106">Requirements</span></span>|  
|---------------------------------|------------------|  
|<span data-ttu-id="bbf68-107">Atualização imediata</span><span class="sxs-lookup"><span data-stu-id="bbf68-107">Immediate Updating</span></span>|<span data-ttu-id="bbf68-108">O Publicador e o Assinante devem estar conectados para atualizar dados no Assinante.</span><span class="sxs-lookup"><span data-stu-id="bbf68-108">Publisher and Subscriber must be connected to update data at the Subscriber.</span></span>|  
|<span data-ttu-id="bbf68-109">Atualização enfileirada</span><span class="sxs-lookup"><span data-stu-id="bbf68-109">Queued Updating</span></span>|<span data-ttu-id="bbf68-110">O Publicador e o Assinante não precisam estar conectados para atualizar dados no Assinante.</span><span class="sxs-lookup"><span data-stu-id="bbf68-110">Publisher and Subscriber do not have to be connected to update data at the Subscriber.</span></span> <span data-ttu-id="bbf68-111">As atualizações podem ser feitas offline e, depois, sincronizadas entre o Publicador e o Assinante.</span><span class="sxs-lookup"><span data-stu-id="bbf68-111">Updates can be made while offline, and later synchronized between the Publisher and Subscriber.</span></span>|  
  
## <a name="options"></a><span data-ttu-id="bbf68-112">Opções</span><span class="sxs-lookup"><span data-stu-id="bbf68-112">Options</span></span>  
 <span data-ttu-id="bbf68-113">**Replicar alterações do Assinante**</span><span class="sxs-lookup"><span data-stu-id="bbf68-113">**Replicate Subscriber changes**</span></span>  
 <span data-ttu-id="bbf68-114">Marque a caixa de seleção na coluna **Replicar** para cada Assinante que possa fazer atualizações.</span><span class="sxs-lookup"><span data-stu-id="bbf68-114">Select the check box in the **Replicate** column for each Subscriber that should be able to make updates.</span></span> <span data-ttu-id="bbf68-115">Para esses assinantes que podem fazer atualizações, selecione a opção apropriada na caixa de listagem suspensa, na coluna **Confirmar no Publicador** :</span><span class="sxs-lookup"><span data-stu-id="bbf68-115">For those Subscribers that can make updates, select the appropriate option from the drop-down list box in the **Commit at Publisher** column:</span></span>  
  
-   <span data-ttu-id="bbf68-116">Selecione **Confirmar as alterações simultaneamente** para uma assinatura de atualização imediata.</span><span class="sxs-lookup"><span data-stu-id="bbf68-116">Select **Simultaneously commit changes** for an immediate updating subscription.</span></span>  
  
-   <span data-ttu-id="bbf68-117">Selecione **Enfileirar alterações e confirmar quando possível** para uma assinatura de atualização em fila.</span><span class="sxs-lookup"><span data-stu-id="bbf68-117">Select **Queue changes and commit when possible** for a queued updating subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbf68-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bbf68-118">See Also</span></span>  
 <span data-ttu-id="bbf68-119">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="bbf68-119">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="bbf68-120">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="bbf68-120">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 <span data-ttu-id="bbf68-121">[Subscribe to Publications](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="bbf68-121">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 [<span data-ttu-id="bbf68-122">Updatable Subscriptions for Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="bbf68-122">Updatable Subscriptions for Transactional Replication</span></span>](transactional/updatable-subscriptions-for-transactional-replication.md)  
  
  
