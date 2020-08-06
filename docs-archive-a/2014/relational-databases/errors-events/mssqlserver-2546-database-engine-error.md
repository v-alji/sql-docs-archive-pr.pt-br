---
title: MSSQLSERVER_2546 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2546 (Database Engine error)
ms.assetid: c8f0e1b4-c7c4-45f2-9221-746714172313
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5c1c5f64ca0daba413f2b71c05f5b8e57b2d55df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679372"
---
# <a name="mssqlserver_2546"></a><span data-ttu-id="2bc21-102">MSSQLSERVER_2546</span><span class="sxs-lookup"><span data-stu-id="2bc21-102">MSSQLSERVER_2546</span></span>
    
## <a name="details"></a><span data-ttu-id="2bc21-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="2bc21-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2bc21-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="2bc21-104">Product Name</span></span>|<span data-ttu-id="2bc21-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2bc21-105">SQL Server</span></span>|  
|<span data-ttu-id="2bc21-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="2bc21-106">Event ID</span></span>|<span data-ttu-id="2bc21-107">2546</span><span class="sxs-lookup"><span data-stu-id="2bc21-107">2546</span></span>|  
|<span data-ttu-id="2bc21-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="2bc21-108">Event Source</span></span>|<span data-ttu-id="2bc21-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2bc21-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2bc21-110">Componente</span><span class="sxs-lookup"><span data-stu-id="2bc21-110">Component</span></span>|<span data-ttu-id="2bc21-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2bc21-111">SQLEngine</span></span>|  
|<span data-ttu-id="2bc21-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="2bc21-112">Symbolic Name</span></span>|<span data-ttu-id="2bc21-113">DBCC_INDEX_MARKED_DISABLED</span><span class="sxs-lookup"><span data-stu-id="2bc21-113">DBCC_INDEX_MARKED_DISABLED</span></span>|  
|<span data-ttu-id="2bc21-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="2bc21-114">Message Text</span></span>|<span data-ttu-id="2bc21-115">O índice 'INDEX_NAME' na tabela 'OBJECT_NAME' está marcado como desabilitado.</span><span class="sxs-lookup"><span data-stu-id="2bc21-115">Index 'INDEX_NAME' on table 'OBJECT_NAME' is marked as disabled.</span></span> <span data-ttu-id="2bc21-116">Reconstrua o índice para colocá-lo online.</span><span class="sxs-lookup"><span data-stu-id="2bc21-116">Rebuild the index to bring it online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2bc21-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="2bc21-117">Explanation</span></span>  
 <span data-ttu-id="2bc21-118">O índice especificado está marcado como offline ou está desabilitado.</span><span class="sxs-lookup"><span data-stu-id="2bc21-118">The specified index is marked as offline or is disabled.</span></span> <span data-ttu-id="2bc21-119">Por isso, não é possível verificá-lo.</span><span class="sxs-lookup"><span data-stu-id="2bc21-119">Therefore, this index cannot be checked.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2bc21-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="2bc21-120">User Action</span></span>  
 <span data-ttu-id="2bc21-121">Reconstrua o índice usando a instrução ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="2bc21-121">Rebuild the index by using ALTER INDEX.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bc21-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2bc21-122">See Also</span></span>  
 <span data-ttu-id="2bc21-123">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2bc21-123">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 [<span data-ttu-id="2bc21-124">Reorganizar e recompilar índices</span><span class="sxs-lookup"><span data-stu-id="2bc21-124">Reorganize and Rebuild Indexes</span></span>](../indexes/indexes.md)  
  
  
