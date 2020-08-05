---
title: MSSQL_ENG014157 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014157 error
ms.assetid: 1a0890cf-d977-43e0-a2ba-9c5ff1a8f856
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0682d740d82c995d64427f56aabce24b8a48ca65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572500"
---
# <a name="mssql_eng014157"></a><span data-ttu-id="9ac77-102">MSSQL_ENG014157</span><span class="sxs-lookup"><span data-stu-id="9ac77-102">MSSQL_ENG014157</span></span>
    
## <a name="message-details"></a><span data-ttu-id="9ac77-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="9ac77-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9ac77-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="9ac77-104">Product Name</span></span>|<span data-ttu-id="9ac77-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9ac77-105">SQL Server</span></span>|  
|<span data-ttu-id="9ac77-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="9ac77-106">Event ID</span></span>|<span data-ttu-id="9ac77-107">14157</span><span class="sxs-lookup"><span data-stu-id="9ac77-107">14157</span></span>|  
|<span data-ttu-id="9ac77-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="9ac77-108">Event Source</span></span>|<span data-ttu-id="9ac77-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9ac77-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9ac77-110">Componente</span><span class="sxs-lookup"><span data-stu-id="9ac77-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="9ac77-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="9ac77-111">Symbolic Name</span></span>||  
|<span data-ttu-id="9ac77-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="9ac77-112">Message Text</span></span>|<span data-ttu-id="9ac77-113">A assinatura criada pelo Assinante '%s' para a publicação '%s' expirou e foi descartada.</span><span class="sxs-lookup"><span data-stu-id="9ac77-113">The subscription created by Subscriber '%s' to publication '%s' has expired and has been dropped.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9ac77-114">Explicação</span><span class="sxs-lookup"><span data-stu-id="9ac77-114">Explanation</span></span>  
 <span data-ttu-id="9ac77-115">Um Assinante deve fazer a sincronização com o Publicador no momento especificado no período de retenção de publicação.</span><span class="sxs-lookup"><span data-stu-id="9ac77-115">A Subscriber must synchronize with the Publisher within the time specified in the publication retention period.</span></span> <span data-ttu-id="9ac77-116">Se um Assinante não fizer a sincronização nesse período, a assinatura será expirada.</span><span class="sxs-lookup"><span data-stu-id="9ac77-116">If a Subscriber does not synchronize within this period, the subscription expires.</span></span> <span data-ttu-id="9ac77-117">Para obter mais informações, consulte [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="9ac77-117">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9ac77-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="9ac77-118">User Action</span></span>  
 <span data-ttu-id="9ac77-119">É necessário recriar e inicializar a assinatura para que o Assinante comece a receber novamente as alterações de dados:</span><span class="sxs-lookup"><span data-stu-id="9ac77-119">The subscription must be re-created and initialized before the Subscriber can begin receiving data changes again:</span></span>  
  
-   <span data-ttu-id="9ac77-120">Para obter mais informações sobre como criar assinaturas, consulte [Assinar publicações](subscribe-to-publications.md).</span><span class="sxs-lookup"><span data-stu-id="9ac77-120">For information about creating subscriptions, see [Subscribe to Publications](subscribe-to-publications.md).</span></span>  
  
-   <span data-ttu-id="9ac77-121">Para obter informações sobre como inicializar assinaturas, consulte [Inicializar uma assinatura](initialize-a-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="9ac77-121">For information about initializing subscriptions, see [Initialize a Subscription](initialize-a-subscription.md).</span></span>  
  
 <span data-ttu-id="9ac77-122">Se o banco de dados de assinatura contiver alterações que não foram sincronizadas com o Publicador, será possível usar o [tablediff Utility](../../tools/tablediff-utility.md) para determinar quais linhas são diferentes nos bancos de dados de publicação e de assinatura.</span><span class="sxs-lookup"><span data-stu-id="9ac77-122">If the subscription database contains changes that have not been synchronized with the Publisher, you can use the [tablediff Utility](../../tools/tablediff-utility.md) to determine which rows are different in the publication and subscription databases.</span></span>  
  
 <span data-ttu-id="9ac77-123">É possível aumentar o período de retenção de publicação para que a assinatura não expire.</span><span class="sxs-lookup"><span data-stu-id="9ac77-123">You can increase the publication retention period to avoid having subscriptions expire.</span></span> <span data-ttu-id="9ac77-124">Tome cuidado ao definir um valor alto, já que isso pode resultar no armazenamento de mais dados e metadados, o que afeta o desempenho.</span><span class="sxs-lookup"><span data-stu-id="9ac77-124">Use caution in setting a high value, because this can result in more data and metadata being stored, which affects performance.</span></span> <span data-ttu-id="9ac77-125">Para obter mais informações, consulte [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="9ac77-125">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ac77-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9ac77-126">See Also</span></span>  
 [<span data-ttu-id="9ac77-127">Referência de erros e eventos &#40;Replicação&#41;</span><span class="sxs-lookup"><span data-stu-id="9ac77-127">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
