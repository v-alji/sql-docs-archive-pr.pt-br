---
title: MSSQLSERVER_8649 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8649 (Database Engine error)
ms.assetid: 992dbc74-7c3a-498b-9f1b-b28387640677
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b39ed0d8ffe5f7f601b6cb1393596d0d6546e557
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575857"
---
# <a name="mssqlserver_8649"></a><span data-ttu-id="bb2be-102">MSSQLSERVER_8649</span><span class="sxs-lookup"><span data-stu-id="bb2be-102">MSSQLSERVER_8649</span></span>
    
## <a name="details"></a><span data-ttu-id="bb2be-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="bb2be-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bb2be-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="bb2be-104">Product Name</span></span>|<span data-ttu-id="bb2be-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bb2be-105">SQL Server</span></span>|  
|<span data-ttu-id="bb2be-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="bb2be-106">Event ID</span></span>|<span data-ttu-id="bb2be-107">8649</span><span class="sxs-lookup"><span data-stu-id="bb2be-107">8649</span></span>|  
|<span data-ttu-id="bb2be-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="bb2be-108">Event Source</span></span>|<span data-ttu-id="bb2be-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bb2be-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bb2be-110">Componente</span><span class="sxs-lookup"><span data-stu-id="bb2be-110">Component</span></span>|<span data-ttu-id="bb2be-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bb2be-111">SQLEngine</span></span>|  
|<span data-ttu-id="bb2be-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="bb2be-112">Symbolic Name</span></span>|<span data-ttu-id="bb2be-113">COST_TOO_HIGH</span><span class="sxs-lookup"><span data-stu-id="bb2be-113">COST_TOO_HIGH</span></span>|  
|<span data-ttu-id="bb2be-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="bb2be-114">Message Text</span></span>|<span data-ttu-id="bb2be-115">A consulta foi cancelada porque seu custo estimado (%d) excede o limite configurado de %d.</span><span class="sxs-lookup"><span data-stu-id="bb2be-115">The query has been canceled because the estimated cost of this query (%d) exceeds the configured threshold of %d.</span></span> <span data-ttu-id="bb2be-116">Contate o administrador do sistema.</span><span class="sxs-lookup"><span data-stu-id="bb2be-116">Contact the system administrator.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bb2be-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="bb2be-117">Explanation</span></span>  
 <span data-ttu-id="bb2be-118">A consulta foi cancelada porque seu custo estimado excede o limite configurado para QUERY_GOVERNOR_COST_LIMIT.</span><span class="sxs-lookup"><span data-stu-id="bb2be-118">The query was canceled because the estimated cost of this query exceeds the configured threshold set for the QUERY_GOVERNOR_COST_LIMIT.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bb2be-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="bb2be-119">User Action</span></span>  
 <span data-ttu-id="bb2be-120">Defina a opção QUERY_GOVERNOR_COST_LIMIT com um valor mais alto.</span><span class="sxs-lookup"><span data-stu-id="bb2be-120">Set the QUERY_GOVERNOR_COST_LIMIT option to a higher value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb2be-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bb2be-121">See Also</span></span>  
 [<span data-ttu-id="bb2be-122">SET QUERY_GOVERNOR_COST_LIMIT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bb2be-122">SET QUERY_GOVERNOR_COST_LIMIT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql)  
  
  
