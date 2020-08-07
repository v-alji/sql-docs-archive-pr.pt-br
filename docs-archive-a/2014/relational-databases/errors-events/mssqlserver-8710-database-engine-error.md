---
title: MSSQLSERVER_8710 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8710 (Database Engine error)
ms.assetid: 78b9f9da-5489-4be0-94df-f065d86ed18c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 65fb6b3efb42c282347f560353a2b21edc337859
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584154"
---
# <a name="mssqlserver_8710"></a><span data-ttu-id="c4f3d-102">MSSQLSERVER_8710</span><span class="sxs-lookup"><span data-stu-id="c4f3d-102">MSSQLSERVER_8710</span></span>
    
## <a name="details"></a><span data-ttu-id="c4f3d-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="c4f3d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c4f3d-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="c4f3d-104">Product Name</span></span>|<span data-ttu-id="c4f3d-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c4f3d-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c4f3d-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="c4f3d-106">Event ID</span></span>|<span data-ttu-id="c4f3d-107">8710</span><span class="sxs-lookup"><span data-stu-id="c4f3d-107">8710</span></span>|  
|<span data-ttu-id="c4f3d-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="c4f3d-108">Event Source</span></span>|<span data-ttu-id="c4f3d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c4f3d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c4f3d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="c4f3d-110">Component</span></span>|<span data-ttu-id="c4f3d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c4f3d-111">SQLEngine</span></span>|  
|<span data-ttu-id="c4f3d-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="c4f3d-112">Symbolic Name</span></span>|<span data-ttu-id="c4f3d-113">QUERY2_CUBE_ILLEGAL_AGG_FUNC</span><span class="sxs-lookup"><span data-stu-id="c4f3d-113">QUERY2_CUBE_ILLEGAL_AGG_FUNC</span></span>|  
|<span data-ttu-id="c4f3d-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="c4f3d-114">Message Text</span></span>|<span data-ttu-id="c4f3d-115">As funções de agregação usadas com consultas CUBE, ROLLUP ou GROUPING SET devem ser fornecidas para a mesclagem de subagregações.</span><span class="sxs-lookup"><span data-stu-id="c4f3d-115">Aggregate functions that are used with CUBE, ROLLUP, or GROUPING SET queries must provide for the merging of subaggregates.</span></span> <span data-ttu-id="c4f3d-116">Para corrigir esse problema, remova a função de agregação ou grave a consulta que está usando as cláusulas UNION ALL sobre GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="c4f3d-116">To fix this problem, remove the aggregate function or write the query using UNION ALL over GROUP BY clauses.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c4f3d-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="c4f3d-117">Explanation</span></span>  
 <span data-ttu-id="c4f3d-118">Uma função de agregação foi usada com CUBE, ROLLUP ou GROUPING SET e não forneceu um método para mesclar subagregações.</span><span class="sxs-lookup"><span data-stu-id="c4f3d-118">An aggregate function has been used with CUBE, ROLLUP, or GROUPING SETS that does not provide a method for merging subaggregates.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c4f3d-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="c4f3d-119">User Action</span></span>  
 <span data-ttu-id="c4f3d-120">Para corrigir esse problema, remova a função de agregação ou grave a consulta que está usando as cláusulas UNION ALL sobre GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="c4f3d-120">To fix this problem, remove the aggregate function or write the query using UNION ALL over GROUP BY clauses.</span></span>  
  
  
