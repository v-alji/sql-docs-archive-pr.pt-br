---
title: MSSQLSERVER_41365 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41365 (Database Engine error)
ms.assetid: 4fc7ec15-b722-4e3d-b7f9-3d39d171e96e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1382a6395f1929a5d5552113e07376bcbf80bf35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575145"
---
# <a name="mssqlserver_41365"></a><span data-ttu-id="dc38a-102">MSSQLSERVER_41365</span><span class="sxs-lookup"><span data-stu-id="dc38a-102">MSSQLSERVER_41365</span></span>
    
## <a name="details"></a><span data-ttu-id="dc38a-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="dc38a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dc38a-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="dc38a-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="dc38a-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="dc38a-105">Event ID</span></span>|<span data-ttu-id="dc38a-106">41365</span><span class="sxs-lookup"><span data-stu-id="dc38a-106">41365</span></span>|  
|<span data-ttu-id="dc38a-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="dc38a-107">Event Source</span></span>|<span data-ttu-id="dc38a-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="dc38a-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="dc38a-109">Componente</span><span class="sxs-lookup"><span data-stu-id="dc38a-109">Component</span></span>|<span data-ttu-id="dc38a-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="dc38a-110">SQLEngine</span></span>|  
|<span data-ttu-id="dc38a-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="dc38a-111">Symbolic Name</span></span>|<span data-ttu-id="dc38a-112">HK_MERGE_SCHEDULE_ERROR</span><span class="sxs-lookup"><span data-stu-id="dc38a-112">HK_MERGE_SCHEDULE_ERROR</span></span>|  
|<span data-ttu-id="dc38a-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="dc38a-113">Message Text</span></span>|<span data-ttu-id="dc38a-114">A solicitação de mesclagem para o intervalo de transações [%ld, %ld] no banco de dados %.\*ls não foi agendada.</span><span class="sxs-lookup"><span data-stu-id="dc38a-114">Merge request for transaction range [%ld, %ld] on database %.\*ls was not scheduled.</span></span> <span data-ttu-id="dc38a-115">Os arquivos de ponto de verificação que representam o intervalo não estão disponíveis para mesclagem ou parte de uma mesclagem contínua.</span><span class="sxs-lookup"><span data-stu-id="dc38a-115">The checkpoint files representing the range are either not available for merge or part of an ongoing merge.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="dc38a-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="dc38a-116">Explanation</span></span>  
 <span data-ttu-id="dc38a-117">Os arquivos de ponto de verificação que representam o intervalo não estão disponíveis para mesclagem ou parte de uma mesclagem contínua.</span><span class="sxs-lookup"><span data-stu-id="dc38a-117">The checkpoint files representing the range are either not available for merge or part of an ongoing merge.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dc38a-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="dc38a-118">User Action</span></span>  
 <span data-ttu-id="dc38a-119">Forneça um melhor intervalo de transações para mesclagem/espera antes de emitir a mesma solicitação novamente.</span><span class="sxs-lookup"><span data-stu-id="dc38a-119">Provide a better transaction range for merge/wait before issuing the same request again.</span></span> <span data-ttu-id="dc38a-120">Para obter mais informações, veja [OLTP in-memory &#40;Otimização na memória&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="dc38a-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc38a-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dc38a-121">See Also</span></span>  
 [<span data-ttu-id="dc38a-122">OLTP in-memory &#40;Otimização na memória&#41;</span><span class="sxs-lookup"><span data-stu-id="dc38a-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
