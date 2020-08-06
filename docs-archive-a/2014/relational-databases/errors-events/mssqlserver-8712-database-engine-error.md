---
title: MSSQLSERVER_8712 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8712 (Database Engine error)
ms.assetid: 292fb3bc-062e-41e4-a566-b5d3d0b21977
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9285d4846cac5af2dd6e87ab55d5fd0610586d07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584150"
---
# <a name="mssqlserver_8712"></a><span data-ttu-id="f3c61-102">MSSQLSERVER_8712</span><span class="sxs-lookup"><span data-stu-id="f3c61-102">MSSQLSERVER_8712</span></span>
    
## <a name="details"></a><span data-ttu-id="f3c61-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="f3c61-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f3c61-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="f3c61-104">Product Name</span></span>|<span data-ttu-id="f3c61-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f3c61-105">SQL Server</span></span>|  
|<span data-ttu-id="f3c61-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="f3c61-106">Event ID</span></span>|<span data-ttu-id="f3c61-107">8712</span><span class="sxs-lookup"><span data-stu-id="f3c61-107">8712</span></span>|  
|<span data-ttu-id="f3c61-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="f3c61-108">Event Source</span></span>|<span data-ttu-id="f3c61-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f3c61-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f3c61-110">Componente</span><span class="sxs-lookup"><span data-stu-id="f3c61-110">Component</span></span>|<span data-ttu-id="f3c61-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f3c61-111">SQLEngine</span></span>|  
|<span data-ttu-id="f3c61-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="f3c61-112">Symbolic Name</span></span>|<span data-ttu-id="f3c61-113">USEPLAN_ERR_NO_INDEX</span><span class="sxs-lookup"><span data-stu-id="f3c61-113">USEPLAN_ERR_NO_INDEX</span></span>|  
|<span data-ttu-id="f3c61-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="f3c61-114">Message Text</span></span>|<span data-ttu-id="f3c61-115">O índice '%.\*ls', especificado na dica USE PLAN, não existe.</span><span class="sxs-lookup"><span data-stu-id="f3c61-115">Index '%.\*ls', specified in the USE PLAN hint, does not exist.</span></span> <span data-ttu-id="f3c61-116">Especifique um índice existente ou crie um índice com o nome especificado.</span><span class="sxs-lookup"><span data-stu-id="f3c61-116">Specify an existing index, or create an index with the specified name.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f3c61-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="f3c61-117">Explanation</span></span>  
 <span data-ttu-id="f3c61-118">Um índice especificado na dica USE PLAN não existe.</span><span class="sxs-lookup"><span data-stu-id="f3c61-118">An index that is specified in the USE PLAN hint does not exist.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f3c61-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="f3c61-119">User Action</span></span>  
 <span data-ttu-id="f3c61-120">Verifique se todos os índices que estão especificados na dica USE PLAN existem.</span><span class="sxs-lookup"><span data-stu-id="f3c61-120">Ensure all indexes that are specified in the USE PLAN hint exist.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3c61-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f3c61-121">See Also</span></span>  
 <span data-ttu-id="f3c61-122">[Dicas de consulta &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="f3c61-122">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 [<span data-ttu-id="f3c61-123">Guias de plano</span><span class="sxs-lookup"><span data-stu-id="f3c61-123">Plan Guides</span></span>](../performance/plan-guides.md)  
  
  
