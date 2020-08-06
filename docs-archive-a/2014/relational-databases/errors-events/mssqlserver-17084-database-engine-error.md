---
title: MSSQLSERVER_17084 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17084 (Database Engine error)
ms.assetid: e579d104-3307-4edd-8587-b14ecbc02ed9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 59b0fc3e0884ddd89809767a068b937b5c145f9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581877"
---
# <a name="mssqlserver_17084"></a><span data-ttu-id="7b219-102">MSSQLSERVER_17084</span><span class="sxs-lookup"><span data-stu-id="7b219-102">MSSQLSERVER_17084</span></span>
    
## <a name="details"></a><span data-ttu-id="7b219-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="7b219-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7b219-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="7b219-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="7b219-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="7b219-105">Event ID</span></span>|<span data-ttu-id="7b219-106">17084</span><span class="sxs-lookup"><span data-stu-id="7b219-106">17084</span></span>|  
|<span data-ttu-id="7b219-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="7b219-107">Event Source</span></span>|<span data-ttu-id="7b219-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7b219-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7b219-109">Componente</span><span class="sxs-lookup"><span data-stu-id="7b219-109">Component</span></span>|<span data-ttu-id="7b219-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7b219-110">SQLEngine</span></span>|  
|<span data-ttu-id="7b219-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="7b219-111">Symbolic Name</span></span>|<span data-ttu-id="7b219-112">P3_ATOMIC_WITH_MISSING_OPTION</span><span class="sxs-lookup"><span data-stu-id="7b219-112">P3_ATOMIC_WITH_MISSING_OPTION</span></span>|  
|<span data-ttu-id="7b219-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="7b219-113">Message Text</span></span>|<span data-ttu-id="7b219-114">A cláusula WITH da instrução BEGIN ATOMIC deve especificar um valor para a opção '%ls'.</span><span class="sxs-lookup"><span data-stu-id="7b219-114">The WITH clause of BEGIN ATOMIC statement must specify a value for the option '%ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7b219-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="7b219-115">Explanation</span></span>  
 <span data-ttu-id="7b219-116">A cláusula WITH da instrução BEGIN ATOMIC não especificou um valor para uma opção.</span><span class="sxs-lookup"><span data-stu-id="7b219-116">The WITH clause of BEGIN ATOMIC statement did not specify a value for an option.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7b219-117">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="7b219-117">User Action</span></span>  
 <span data-ttu-id="7b219-118">Os blocos `ATOMIC` requerem valores para as opções `WITH``TRANSACTION ISOLATION LEVEL` e `LANGUAGE`.</span><span class="sxs-lookup"><span data-stu-id="7b219-118">`ATOMIC` blocks require values for the `WITH` options `TRANSACTION ISOLATION LEVEL` and `LANGUAGE`.</span></span> <span data-ttu-id="7b219-119">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7b219-119">For example::</span></span>  
  
```  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE= N'us_english')  
```  
  
 <span data-ttu-id="7b219-120">Para obter mais informações, veja [OLTP in-memory &#40;Otimização na memória&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="7b219-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b219-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7b219-121">See Also</span></span>  
 [<span data-ttu-id="7b219-122">OLTP in-memory &#40;Otimização na memória&#41;</span><span class="sxs-lookup"><span data-stu-id="7b219-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
