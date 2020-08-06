---
title: MSSQLSERVER_2530 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
ms.assetid: 5d4be07a-38a5-4b25-819c-4dcb4636cc15
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 30b57aae907d6f0acc4d1c0e6021bf936621c69e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569532"
---
# <a name="mssqlserver_2530"></a><span data-ttu-id="e9afe-102">MSSQLSERVER_2530</span><span class="sxs-lookup"><span data-stu-id="e9afe-102">MSSQLSERVER_2530</span></span>
    
## <a name="details"></a><span data-ttu-id="e9afe-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="e9afe-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e9afe-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="e9afe-104">Product Name</span></span>|<span data-ttu-id="e9afe-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e9afe-105">SQL Server</span></span>|  
|<span data-ttu-id="e9afe-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="e9afe-106">Event ID</span></span>|<span data-ttu-id="e9afe-107">2530</span><span class="sxs-lookup"><span data-stu-id="e9afe-107">2530</span></span>|  
|<span data-ttu-id="e9afe-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="e9afe-108">Event Source</span></span>|<span data-ttu-id="e9afe-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e9afe-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e9afe-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e9afe-110">Component</span></span>|<span data-ttu-id="e9afe-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e9afe-111">SQLEngine</span></span>|  
|<span data-ttu-id="e9afe-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="e9afe-112">Symbolic Name</span></span>|<span data-ttu-id="e9afe-113">DBCC_INDEX_IS_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="e9afe-113">DBCC_INDEX_IS_OFFLINE</span></span>|  
|<span data-ttu-id="e9afe-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="e9afe-114">Message Text</span></span>|<span data-ttu-id="e9afe-115">O índice "%.\*ls" na tabela "%.\*ls" está desabilitado.</span><span class="sxs-lookup"><span data-stu-id="e9afe-115">The index "%.\*ls" on table "%.\*ls" is disabled.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e9afe-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="e9afe-116">Explanation</span></span>  
 <span data-ttu-id="e9afe-117">A instrução DBCC não pode continuar porque o índice especificado está desabilitado.</span><span class="sxs-lookup"><span data-stu-id="e9afe-117">The DBCC statement cannot proceed because the specified index is disabled.</span></span> <span data-ttu-id="e9afe-118">Depois que um índice é desabilitado, ele permanece em estado desabilitado até que seja reconstruído ou descartado e recriado.</span><span class="sxs-lookup"><span data-stu-id="e9afe-118">After an index is disabled, it remains in a disabled state until it is rebuilt or dropped and re-created.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e9afe-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="e9afe-119">User Action</span></span>  
  
1.  <span data-ttu-id="e9afe-120">Habilite o índice desabilitado usando um dos seguinte métodos:</span><span class="sxs-lookup"><span data-stu-id="e9afe-120">Enable the disabled index by using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="e9afe-121">Instrução ALTER INDEX com a cláusula REBUILD</span><span class="sxs-lookup"><span data-stu-id="e9afe-121">ALTER INDEX statement with the REBUILD clause</span></span>  
  
    -   <span data-ttu-id="e9afe-122">CREATE INDEX com a cláusula DROP_EXISTING</span><span class="sxs-lookup"><span data-stu-id="e9afe-122">CREATE INDEX with the DROP_EXISTING clause</span></span>  
  
    -   <span data-ttu-id="e9afe-123">DBCC DBREINDEX</span><span class="sxs-lookup"><span data-stu-id="e9afe-123">DBCC DBREINDEX</span></span>  
  
2.  <span data-ttu-id="e9afe-124">Execute novamente a instrução DBCC.</span><span class="sxs-lookup"><span data-stu-id="e9afe-124">Rerun the DBCC statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9afe-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e9afe-125">See Also</span></span>  
 <span data-ttu-id="e9afe-126">[Habilitar índices e restrições](../indexes/enable-indexes-and-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="e9afe-126">[Enable Indexes and Constraints](../indexes/enable-indexes-and-constraints.md) </span></span>  
 <span data-ttu-id="e9afe-127">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e9afe-127">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="e9afe-128">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e9afe-128">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 [<span data-ttu-id="e9afe-129">DBCC DBREINDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e9afe-129">DBCC DBREINDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql)  
  
  
