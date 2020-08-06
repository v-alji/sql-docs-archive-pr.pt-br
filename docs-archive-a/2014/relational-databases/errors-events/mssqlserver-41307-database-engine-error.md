---
title: MSSQLSERVER_41307 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41307 (Database Engine error)
ms.assetid: 56f56410-b07d-4379-b01c-702c95761070
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 98407a65d5529fd73bccc638df11167131bd9f8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681666"
---
# <a name="mssqlserver_41307"></a><span data-ttu-id="47d36-102">MSSQLSERVER_41307</span><span class="sxs-lookup"><span data-stu-id="47d36-102">MSSQLSERVER_41307</span></span>
    
## <a name="details"></a><span data-ttu-id="47d36-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="47d36-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="47d36-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="47d36-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="47d36-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="47d36-105">Event ID</span></span>|<span data-ttu-id="47d36-106">41307</span><span class="sxs-lookup"><span data-stu-id="47d36-106">41307</span></span>|  
|<span data-ttu-id="47d36-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="47d36-107">Event Source</span></span>|<span data-ttu-id="47d36-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="47d36-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="47d36-109">Componente</span><span class="sxs-lookup"><span data-stu-id="47d36-109">Component</span></span>|<span data-ttu-id="47d36-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="47d36-110">SQLEngine</span></span>|  
|<span data-ttu-id="47d36-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="47d36-111">Symbolic Name</span></span>|<span data-ttu-id="47d36-112">HK_HEKATON_ROW_LIMIT</span><span class="sxs-lookup"><span data-stu-id="47d36-112">HK_HEKATON_ROW_LIMIT</span></span>|  
|<span data-ttu-id="47d36-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="47d36-113">Message Text</span></span>|<span data-ttu-id="47d36-114">O limite de tamanho de linha de *number* bytes para tabelas com otimização de memória foi excedido.</span><span class="sxs-lookup"><span data-stu-id="47d36-114">The row size limit of *number* bytes for memory optimized tables has been exceeded.</span></span> <span data-ttu-id="47d36-115">Simplifique a definição da tabela.</span><span class="sxs-lookup"><span data-stu-id="47d36-115">Please simplify the table definition.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="47d36-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="47d36-116">Explanation</span></span>  
 <span data-ttu-id="47d36-117">O limite de tamanho de linha para tabelas com otimização de memória é 8.060 bytes.</span><span class="sxs-lookup"><span data-stu-id="47d36-117">The row size limit for memory optimized tables is 8,060 bytes.</span></span> <span data-ttu-id="47d36-118">Para obter mais informações, consulte [Tamanho da tabela e da linha em tabelas com otimização de memória](../in-memory-oltp/memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="47d36-118">For more information, see [Table and Row Size in Memory-Optimized Tables](../in-memory-oltp/memory-optimized-tables.md).</span></span> <span data-ttu-id="47d36-119">Para obter mais informações, veja [OLTP in-memory &#40;Otimização na memória&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="47d36-119">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47d36-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="47d36-120">See Also</span></span>  
 [<span data-ttu-id="47d36-121">OLTP in-memory &#40;Otimização na memória&#41;</span><span class="sxs-lookup"><span data-stu-id="47d36-121">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
