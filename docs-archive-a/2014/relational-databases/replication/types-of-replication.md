---
title: Tipos de replicação | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], types
ms.assetid: c1655e8d-d14c-455a-a7f9-9d2f43e88ab4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5576331004eca44bc32dbde8f430284f75e6eb70
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681538"
---
# <a name="types-of-replication"></a><span data-ttu-id="cbc43-102">Tipos de replicação</span><span class="sxs-lookup"><span data-stu-id="cbc43-102">Types of Replication</span></span>
  <span data-ttu-id="cbc43-103">O [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fornece os seguintes tipos de replicação para uso em aplicativos distribuídos:</span><span class="sxs-lookup"><span data-stu-id="cbc43-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides the following types of replication for use in distributed applications:</span></span>  
  
-   <span data-ttu-id="cbc43-104">Replicação transacional.</span><span class="sxs-lookup"><span data-stu-id="cbc43-104">Transactional replication.</span></span> <span data-ttu-id="cbc43-105">Para obter mais informações, consulte [Replicação transacional](transactional/transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="cbc43-105">For more information, see [Transactional Replication](transactional/transactional-replication.md).</span></span>  
  
-   <span data-ttu-id="cbc43-106">Replicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="cbc43-106">Merge replication.</span></span> <span data-ttu-id="cbc43-107">Para obter mais informações, consulte [Replicação de mesclagem](merge/merge-replication.md).</span><span class="sxs-lookup"><span data-stu-id="cbc43-107">For more information, see [Merge Replication](merge/merge-replication.md).</span></span>  
  
-   <span data-ttu-id="cbc43-108">Replicação de instantâneo</span><span class="sxs-lookup"><span data-stu-id="cbc43-108">Snapshot replication.</span></span> <span data-ttu-id="cbc43-109">Para obter mais informações, consulte [Replicação de instantâneo](snapshot-replication.md).</span><span class="sxs-lookup"><span data-stu-id="cbc43-109">For more information, see [Snapshot Replication](snapshot-replication.md).</span></span>  
  
 <span data-ttu-id="cbc43-110">O tipo de replicação que você escolhe para um aplicativo, depende de muitos fatores, incluindo o ambiente físico da replicação, o tipo e a quantidade de dados a serem replicados e se os dados serão ou não atualizados no Assinante.</span><span class="sxs-lookup"><span data-stu-id="cbc43-110">The type of replication you choose for an application depends on many factors, including the physical replication environment, the type and quantity of data to be replicated, and whether the data is updated at the Subscriber.</span></span> <span data-ttu-id="cbc43-111">O ambiente físico inclui o número e local dos computadores envolvidos na replicação e se esses computadores são clientes (estações de trabalho, laptops ou dispositivos portáteis) ou servidores.</span><span class="sxs-lookup"><span data-stu-id="cbc43-111">The physical environment includes the number and location of computers involved in replication and whether these computers are clients (workstations, laptops, or handheld devices) or servers.</span></span>  
  
 <span data-ttu-id="cbc43-112">Cada tipo de replicação começa normalmente com uma sincronização inicial dos objetos publicados entre o Publicador e os Assinantes.</span><span class="sxs-lookup"><span data-stu-id="cbc43-112">Each type of replication typically begins with an initial synchronization of the published objects between the Publisher and Subscribers.</span></span> <span data-ttu-id="cbc43-113">Esta sincronização inicial pode ser executada por replicação com um *instantâneo*, que é uma cópia de todos os objetos e dados especificados por uma publicação.</span><span class="sxs-lookup"><span data-stu-id="cbc43-113">This initial synchronization can be performed by replication with a *snapshot*, which is a copy of all of the objects and data specified by a publication.</span></span> <span data-ttu-id="cbc43-114">Depois que o instantâneo é criado, ele é distribuído aos Assinantes.</span><span class="sxs-lookup"><span data-stu-id="cbc43-114">After the snapshot is created, it is delivered to the Subscribers.</span></span> <span data-ttu-id="cbc43-115">Para alguns aplicativos, a replicação de instantâneo é tudo o que é necessário.</span><span class="sxs-lookup"><span data-stu-id="cbc43-115">For some applications, snapshot replication is all that is required.</span></span> <span data-ttu-id="cbc43-116">Para outros tipos de aplicativos, é importante que as alterações de dados subsequentes fluam para o Assinante de forma incremental com o passar do tempo.</span><span class="sxs-lookup"><span data-stu-id="cbc43-116">For other types of applications, it is important that subsequent data changes flow to the Subscriber incrementally over time.</span></span> <span data-ttu-id="cbc43-117">Alguns aplicativos também exigem que as alterações fluam do Assinante de volta para o Publicador.</span><span class="sxs-lookup"><span data-stu-id="cbc43-117">Some applications also require that changes flow from the Subscriber back to the Publisher.</span></span> <span data-ttu-id="cbc43-118">A replicação transacional e a replicação de mesclagem fornecem opções para estes tipos de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="cbc43-118">Transactional replication and merge replication provide options for these types of applications.</span></span>  
  
 <span data-ttu-id="cbc43-119">As alterações de dados não são rastreadas para a replicação de instantâneo. Sempre que um instantâneo é aplicado, ele sobrescreve por completo os dados existentes.</span><span class="sxs-lookup"><span data-stu-id="cbc43-119">Data changes are not tracked for snapshot replication; each time a snapshot is applied, it completely overwrites the existing data.</span></span> <span data-ttu-id="cbc43-120">A replicação transacional rastreia as alterações pelo log de transação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e a replicação de mesclagem rastreia as alterações pelos gatilhos e tabelas de metadados.</span><span class="sxs-lookup"><span data-stu-id="cbc43-120">Transactional replication tracks changes through the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] transaction log, and merge replication tracks changes through triggers and metadata tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbc43-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cbc43-121">See Also</span></span>  
 [<span data-ttu-id="cbc43-122">Visão geral dos agentes de replicação</span><span class="sxs-lookup"><span data-stu-id="cbc43-122">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
