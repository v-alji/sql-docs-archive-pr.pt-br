---
title: A atualização modificará as assinaturas de atualização em fila que usam o enfileiramento de mensagens | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [SQL Server replication]
- MSMQ [SQL Server replication]
- queues [SQL Server replication]
- queued updating subscriptions [SQL Server replication]
ms.assetid: 97944de3-fbad-4db1-939a-dcd550bf5893
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d44cbad43d75634cbf8660110cc879522265c54d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686030"
---
# <a name="upgrading-will-modify-queued-updating-subscriptions-that-use-message-queuing"></a><span data-ttu-id="72912-102">A atualização modificará assinaturas de atualização enfileiradas que usam o serviço de enfileiramento de mensagens</span><span class="sxs-lookup"><span data-stu-id="72912-102">Upgrading will modify queued updating subscriptions that use Message Queuing</span></span>
  <span data-ttu-id="72912-103">O Supervisor de Atualização detectou que podem haver uma ou mais assinaturas de atualização na fila que usam o serviço de enfileiramento de mensagens da [!INCLUDE[msCoName](../../includes/msconame-md.md)] (também conhecido como MSMQ).</span><span class="sxs-lookup"><span data-stu-id="72912-103">Upgrade Advisor detected that you might have one or more queued updating subscriptions that use [!INCLUDE[msCoName](../../includes/msconame-md.md)] Message Queuing (also known as MSMQ).</span></span> <span data-ttu-id="72912-104">A replicação não oferece mais suporte para o serviço de enfileiramento de mensagens. Portanto, as assinaturas serão modificadas para usar uma fila do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72912-104">Replication no longer supports Message Queuing; therefore, the subscriptions will be modified to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] queue.</span></span>  
  
 <span data-ttu-id="72912-105">Somente um valor de **SQL** é permitido.</span><span class="sxs-lookup"><span data-stu-id="72912-105">Only a value of **sql** is allowed.</span></span> <span data-ttu-id="72912-106">Publicações existentes que usam o Serviço de Enfileiramento de Mensagens são modificadas durante atualização para usar uma fila [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72912-106">Existing publications that use Message Queuing are modified during upgrade to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] queue.</span></span> <span data-ttu-id="72912-107">Se você tiver aplicativos que dependem de atualização enfileirada usando o enfileiramento de mensagens, esses aplicativos precisarão ser gravados novamente para acomodar uma fila do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72912-107">If you have applications that depend on queued updating using Message Queuing, these applications will have to be rewritten to accommodate a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] queue.</span></span> <span data-ttu-id="72912-108">Para obter mais informações sobre assinaturas de atualização na fila, consulte ‘Assinaturas atualizáveis para replicação transacional’ nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72912-108">For more information about queued updating subscriptions, see "Updatable Subscriptions for Transactional Replication" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="72912-109">A atualização irá remover a assinatura do serviço de enfileiramento de mensagens existente se o serviço de enfileiramento de mensagens for executado durante a atualização de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72912-109">Upgrade will remove the existing Message Queuing subscription queues if the Message Queuing service is running while [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is being upgraded.</span></span>  
  
 <span data-ttu-id="72912-110">Se o serviço de enfileiramento de mensagens não estiver em execução, remova as filas manualmente depois da atualização.</span><span class="sxs-lookup"><span data-stu-id="72912-110">If the Message Queuing service is not running, remove the queues manually after upgrade is complete.</span></span> <span data-ttu-id="72912-111">Para obter mais informações sobre a remoção de filas, consulte a documentação do Windows.</span><span class="sxs-lookup"><span data-stu-id="72912-111">For more information about how to remove queues, see the Windows documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72912-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="72912-112">See Also</span></span>  
 [<span data-ttu-id="72912-113">Problemas na atualização da replicação</span><span class="sxs-lookup"><span data-stu-id="72912-113">Replication Upgrade Issues</span></span>](../../../2014/sql-server/install/replication-upgrade-issues.md)  
  
  
