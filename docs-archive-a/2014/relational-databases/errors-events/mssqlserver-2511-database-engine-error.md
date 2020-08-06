---
title: MSSQLSERVER_2511 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2511 (Database Engine error)
ms.assetid: 9a00c0ed-eb4b-4fae-8016-192396006c37
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 23e91b0d64140329639cf57f3a336cd2eab8e4e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680432"
---
# <a name="mssqlserver_2511"></a><span data-ttu-id="46b08-102">MSSQLSERVER_2511</span><span class="sxs-lookup"><span data-stu-id="46b08-102">MSSQLSERVER_2511</span></span>
    
## <a name="details"></a><span data-ttu-id="46b08-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="46b08-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="46b08-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="46b08-104">Product Name</span></span>|<span data-ttu-id="46b08-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="46b08-105">SQL Server</span></span>|  
|<span data-ttu-id="46b08-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="46b08-106">Event ID</span></span>|<span data-ttu-id="46b08-107">2511</span><span class="sxs-lookup"><span data-stu-id="46b08-107">2511</span></span>|  
|<span data-ttu-id="46b08-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="46b08-108">Event Source</span></span>|<span data-ttu-id="46b08-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="46b08-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="46b08-110">Componente</span><span class="sxs-lookup"><span data-stu-id="46b08-110">Component</span></span>|<span data-ttu-id="46b08-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="46b08-111">SQLEngine</span></span>|  
|<span data-ttu-id="46b08-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="46b08-112">Symbolic Name</span></span>|<span data-ttu-id="46b08-113">DBCC_KEYS_OUT_OF_ORDER</span><span class="sxs-lookup"><span data-stu-id="46b08-113">DBCC_KEYS_OUT_OF_ORDER</span></span>|  
|<span data-ttu-id="46b08-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="46b08-114">Message Text</span></span>|<span data-ttu-id="46b08-115">Erro de tabela: ID de objeto %d, ID de índice %d, ID de partição %I64d, ID de unidade de alocação %I64d (tipo %.\*ls).</span><span class="sxs-lookup"><span data-stu-id="46b08-115">Table error: Object ID %d, index ID %d, partition ID %I64d, alloc unit ID %I64d (type %.\*ls).</span></span> <span data-ttu-id="46b08-116">As chaves estão fora da ordem na página %S_PGID, slots %d e %d.</span><span class="sxs-lookup"><span data-stu-id="46b08-116">Keys out of order on page %S_PGID, slots %d and %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="46b08-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="46b08-117">Explanation</span></span>  
 <span data-ttu-id="46b08-118">Chaves fora de ordem foram detectadas no índice especificado.</span><span class="sxs-lookup"><span data-stu-id="46b08-118">Out-of-order keys were detected in the specified index.</span></span> <span data-ttu-id="46b08-119">A página em que as chaves estão contidas pode estar corrompida.</span><span class="sxs-lookup"><span data-stu-id="46b08-119">The page in which the keys are contained may be corrupted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="46b08-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="46b08-120">User Action</span></span>  
 <span data-ttu-id="46b08-121">Reconstrua o índice especificado usando a instrução ALTER INDEX REBUILD.</span><span class="sxs-lookup"><span data-stu-id="46b08-121">Rebuild the specified index by using the ALTER INDEX REBUILD statement.</span></span>  
  
  
