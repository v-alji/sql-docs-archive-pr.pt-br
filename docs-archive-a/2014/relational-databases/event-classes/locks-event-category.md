---
title: Categoria de evento de bloqueios | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Locks event category [SQL Server]
- SQL Server event classes, Locks event category
- event classes [SQL Server], Locks event category
- lock escalation [SQL Server], locks event category
ms.assetid: 27d6afa2-7dab-4fe7-a1ad-064b879dc654
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3a202279021e3e6c7c3c44a167792bb9439567aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570699"
---
# <a name="locks-event-category"></a><span data-ttu-id="5ae6f-102">Categoria de eventos Bloqueios</span><span class="sxs-lookup"><span data-stu-id="5ae6f-102">Locks Event Category</span></span>
  <span data-ttu-id="5ae6f-103">Use as classes de evento na categoria de evento **Bloqueios** para monitorar a atividade de bloqueio em uma instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ae6f-103">Use the event classes in the **Locks** event category to monitor locking activity in an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="5ae6f-104">Essas classes de evento podem ajudar a descobrir problemas de bloqueio causados por vários usuários lendo e modificando dados simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="5ae6f-104">These event classes can help you investigate locking problems caused by multiple users reading and modifying data concurrently.</span></span>  
  
 <span data-ttu-id="5ae6f-105">Como o [!INCLUDE[ssDE](../../includes/ssde-md.md)] frequentemente processa muitos bloqueios, captar as classes de evento **Locks** durante um rastreamento pode incorrer em sobrecarga significativa e resultar em arquivos ou tabelas de rastreamento maiores.</span><span class="sxs-lookup"><span data-stu-id="5ae6f-105">Because the [!INCLUDE[ssDE](../../includes/ssde-md.md)] often processes many locks, capturing the **Locks** event classes during a trace can incur significant overhead and result in large trace files or tables.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5ae6f-106">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="5ae6f-106">In This Section</span></span>  
  
|<span data-ttu-id="5ae6f-107">Tópico</span><span class="sxs-lookup"><span data-stu-id="5ae6f-107">Topic</span></span>|<span data-ttu-id="5ae6f-108">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="5ae6f-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="5ae6f-109">Classe de evento Deadlock Graph</span><span class="sxs-lookup"><span data-stu-id="5ae6f-109">Deadlock Graph Event Class</span></span>](deadlock-graph-event-class.md)|<span data-ttu-id="5ae6f-110">Fornece uma descrição XML de um deadlock.</span><span class="sxs-lookup"><span data-stu-id="5ae6f-110">Provides an XML description of a deadlock.</span></span>|  
|[<span data-ttu-id="5ae6f-111">Classe de evento Lock:Acquired</span><span class="sxs-lookup"><span data-stu-id="5ae6f-111">Lock:Acquired Event Class</span></span>](lock-acquired-event-class.md)|<span data-ttu-id="5ae6f-112">Indica que um bloqueio foi adquirido em um recurso, como uma linha em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="5ae6f-112">Indicates that a lock has been acquired on a resource, such as a row in a table.</span></span>|  
|[<span data-ttu-id="5ae6f-113">Classe de evento Lock:Cancel</span><span class="sxs-lookup"><span data-stu-id="5ae6f-113">Lock:Cancel Event Class</span></span>](lock-cancel-event-class.md)|<span data-ttu-id="5ae6f-114">Rastreia solicitações de bloqueios canceladas antes que o bloqueio fosse adquirido (por exemplo, para impedir um deadlock).</span><span class="sxs-lookup"><span data-stu-id="5ae6f-114">Tracks requests for locks that were canceled before the lock was acquired (for example, to prevent a deadlock).</span></span>|  
|[<span data-ttu-id="5ae6f-115">Classe de evento Lock:Deadlock Chain</span><span class="sxs-lookup"><span data-stu-id="5ae6f-115">Lock:Deadlock Chain Event Class</span></span>](lock-deadlock-chain-event-class.md)|<span data-ttu-id="5ae6f-116">Monitora quando ocorrem condições de deadlock e quais objetos são envolvidos.</span><span class="sxs-lookup"><span data-stu-id="5ae6f-116">Monitors when deadlock conditions occur and which objects are involved.</span></span>|  
|[<span data-ttu-id="5ae6f-117">Classe de evento Lock:Deadlock</span><span class="sxs-lookup"><span data-stu-id="5ae6f-117">Lock:Deadlock Event Class</span></span>](lock-deadlock-event-class.md)|<span data-ttu-id="5ae6f-118">Rastreia quando uma transação solicitou um bloqueio em um recurso já bloqueado por outra transação, resultando em um deadlock.</span><span class="sxs-lookup"><span data-stu-id="5ae6f-118">Tracks when a transaction has requested a lock on a resource already locked by another transaction, resulting in a deadlock.</span></span>|  
|[<span data-ttu-id="5ae6f-119">Classe de evento Lock:Escalation</span><span class="sxs-lookup"><span data-stu-id="5ae6f-119">Lock:Escalation Event Class</span></span>](lock-escalation-event-class.md)|<span data-ttu-id="5ae6f-120">Indica se um bloqueio mais refinado foi convertido em um bloqueio mais rústico.</span><span class="sxs-lookup"><span data-stu-id="5ae6f-120">Indicates that a finer-grained lock has been converted to a coarser-grained lock.</span></span>|  
|[<span data-ttu-id="5ae6f-121">Classe de evento Lock:Released</span><span class="sxs-lookup"><span data-stu-id="5ae6f-121">Lock:Released Event Class</span></span>](lock-released-event-class.md)|<span data-ttu-id="5ae6f-122">Rastreia quando um bloqueio é liberado.</span><span class="sxs-lookup"><span data-stu-id="5ae6f-122">Tracks when a lock is released.</span></span>|  
|[<span data-ttu-id="5ae6f-123">Classe de evento Lock:Timeout &#40;timeout &#62; 0&#41;</span><span class="sxs-lookup"><span data-stu-id="5ae6f-123">Lock:Timeout &#40;timeout &#62; 0&#41; Event Class</span></span>](lock-timeout-timeout-0-event-class.md)|<span data-ttu-id="5ae6f-124">Rastreia quando solicitações de bloqueio não podem ser concluídas porque outra transação tem um bloqueio no recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="5ae6f-124">Tracks when lock requests cannot be completed because another transaction has a blocking lock on the requested resource.</span></span> <span data-ttu-id="5ae6f-125">Esse evento só acontece em situações em que o valor de tempo limite de bloqueio é maior que zero.</span><span class="sxs-lookup"><span data-stu-id="5ae6f-125">This event occurs only in situations where the lock time-out value is greater than zero.</span></span>|  
|[<span data-ttu-id="5ae6f-126">Classe de evento Lock:Timeout</span><span class="sxs-lookup"><span data-stu-id="5ae6f-126">Lock:Timeout Event Class</span></span>](lock-timeout-event-class.md)|<span data-ttu-id="5ae6f-127">Rastreia quando solicitações de bloqueio não podem ser concluídas porque outra transação tem um bloqueio no recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="5ae6f-127">Tracks when lock requests cannot be completed because another transaction has a blocking lock on the requested resource.</span></span>|  
  
  
