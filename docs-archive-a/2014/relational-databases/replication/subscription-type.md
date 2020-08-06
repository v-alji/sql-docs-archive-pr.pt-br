---
title: Tipo de assinatura | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.subscriptiontype.f1
ms.assetid: 9a50f588-ee45-4a87-826f-372ff0798587
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 614ff910b13706485ee9466c884243ff1c9027ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680369"
---
# <a name="subscription-type"></a><span data-ttu-id="11ccb-102">Tipo de Assinatura</span><span class="sxs-lookup"><span data-stu-id="11ccb-102">Subscription Type</span></span>
  <span data-ttu-id="11ccb-103">A replicação de mesclagem oferece dois tipos de assinatura: servidor e cliente (referenciado em versões anteriores do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] como global e local, respectivamente).</span><span class="sxs-lookup"><span data-stu-id="11ccb-103">Merge replication offers two subscription types: server and client (referred to in previous versions of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as global and local, respectively).</span></span> <span data-ttu-id="11ccb-104">Os Assinantes com uma assinatura de servidor podem:</span><span class="sxs-lookup"><span data-stu-id="11ccb-104">Subscribers with a server subscription can:</span></span>  
  
-   <span data-ttu-id="11ccb-105">Republicar dados para outros Assinantes.</span><span class="sxs-lookup"><span data-stu-id="11ccb-105">Republish data to other Subscribers.</span></span>  
  
-   <span data-ttu-id="11ccb-106">Servir como parceiros de sincronização alternativos.</span><span class="sxs-lookup"><span data-stu-id="11ccb-106">Serve as alternate synchronization partners.</span></span>  
  
-   <span data-ttu-id="11ccb-107">Resolver conflitos de acordo com uma prioridade definida.</span><span class="sxs-lookup"><span data-stu-id="11ccb-107">Resolve conflicts according to a priority you set.</span></span>  
  
 <span data-ttu-id="11ccb-108">A maioria dos Assinantes não requer essa funcionalidade e usa uma assinatura de cliente.</span><span class="sxs-lookup"><span data-stu-id="11ccb-108">Most Subscribers do not require this functionality and can use a client subscription.</span></span> <span data-ttu-id="11ccb-109">Assinaturas de cliente ainda permitem detecção e resolução de conflitos, mas não é atribuída uma prioridade aos Assinantes: o primeiro Assinante a enviar uma alteração ao Publicador ganha todos os conflitos que possam surgir daquela alteração.</span><span class="sxs-lookup"><span data-stu-id="11ccb-109">Client subscriptions still allow conflict detection and resolution, but Subscribers are not assigned a priority: the first Subscriber to submit a change to the Publisher wins any conflicts that might arise from that change.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="11ccb-110">O tipo da assinatura não pode ser alterado depois que ela é criada.</span><span class="sxs-lookup"><span data-stu-id="11ccb-110">Subscription type cannot be changed after a subscription is created.</span></span>  
  
## <a name="options"></a><span data-ttu-id="11ccb-111">Opções</span><span class="sxs-lookup"><span data-stu-id="11ccb-111">Options</span></span>  
 <span data-ttu-id="11ccb-112">**Propriedades da assinatura**</span><span class="sxs-lookup"><span data-stu-id="11ccb-112">**Subscription properties**</span></span>  
 <span data-ttu-id="11ccb-113">Para cada Assinante, selecione **Cliente** ou **Servidor** na caixa de listagem suspensa na coluna **Tipo de Assinatura** .</span><span class="sxs-lookup"><span data-stu-id="11ccb-113">For each Subscriber, select **Client** or **Server** from the drop-down list box in the **Subscription Type** column.</span></span> <span data-ttu-id="11ccb-114">Para Assinantes com assinaturas de servidor, insira um número entre 0 e 99.99 na coluna **Prioridade para a Resolução de Conflitos** (quanto mais alto for o número, mais alta será a prioridade para o Assinante).</span><span class="sxs-lookup"><span data-stu-id="11ccb-114">For Subscribers with server subscriptions, enter a number between 0 and 99.99 in the **Priority for Conflict Resolution** column (the higher the number, the higher the priority for the Subscriber).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11ccb-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="11ccb-115">See Also</span></span>  
 <span data-ttu-id="11ccb-116">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="11ccb-116">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="11ccb-117">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="11ccb-117">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 [<span data-ttu-id="11ccb-118">Assinar publicações</span><span class="sxs-lookup"><span data-stu-id="11ccb-118">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
