---
title: MSSQLSERVER_41399 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41399 (Database Engine error)
ms.assetid: 5e5acb07-16ca-4329-8210-cd2bab0c904f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2e134cbc8b39a3c65d9c515183243f0b4caed434
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572577"
---
# <a name="mssqlserver_41399"></a><span data-ttu-id="a9ea8-102">MSSQLSERVER_41399</span><span class="sxs-lookup"><span data-stu-id="a9ea8-102">MSSQLSERVER_41399</span></span>
    
## <a name="details"></a><span data-ttu-id="a9ea8-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="a9ea8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a9ea8-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="a9ea8-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="a9ea8-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="a9ea8-105">Event ID</span></span>|<span data-ttu-id="a9ea8-106">41399</span><span class="sxs-lookup"><span data-stu-id="a9ea8-106">41399</span></span>|  
|<span data-ttu-id="a9ea8-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="a9ea8-107">Event Source</span></span>|<span data-ttu-id="a9ea8-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a9ea8-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a9ea8-109">Componente</span><span class="sxs-lookup"><span data-stu-id="a9ea8-109">Component</span></span>|<span data-ttu-id="a9ea8-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a9ea8-110">SQLEngine</span></span>|  
|<span data-ttu-id="a9ea8-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="a9ea8-111">Symbolic Name</span></span>|<span data-ttu-id="a9ea8-112">MAX_SORT_ROW_WIDTH_EXCEEDED</span><span class="sxs-lookup"><span data-stu-id="a9ea8-112">MAX_SORT_ROW_WIDTH_EXCEEDED</span></span>|  
|<span data-ttu-id="a9ea8-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="a9ea8-113">Message Text</span></span>|<span data-ttu-id="a9ea8-114">A operação de classificação é muito complexa.</span><span class="sxs-lookup"><span data-stu-id="a9ea8-114">The sort operation is too complex.</span></span> <span data-ttu-id="a9ea8-115">Consulte os manuais online do SQL Server para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a9ea8-115">Consult SQL Server Books Online for more information.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a9ea8-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="a9ea8-116">Explanation</span></span>  
 <span data-ttu-id="a9ea8-117">Classificar o resultado de operações de junção e agregação aumenta a complexidade da operação de classificação aumentando o tamanho da linha no buffer de classificação.</span><span class="sxs-lookup"><span data-stu-id="a9ea8-117">Sorting the result of join and aggregation operations increases the complexity of the sort operation by increasing the size of the row in the sort buffer.</span></span> <span data-ttu-id="a9ea8-118">Esse erro significa que o tamanho da linha é maior que o tamanho máximo suportado pelo operador de classificação em procedimentos armazenados criados de modo nativo.</span><span class="sxs-lookup"><span data-stu-id="a9ea8-118">This error means that the size of the row is larger than the maximum size supported by the sort operator in natively compiled stored procedures.</span></span> <span data-ttu-id="a9ea8-119">Observe que o tamanho de uma linha no buffer de classificação somente é determinado pelo número de junções e o número e o tipo de funções de agregação.</span><span class="sxs-lookup"><span data-stu-id="a9ea8-119">Note that the size of a row in the sort buffer is determined solely by the number of joins and the number and type of aggregate functions.</span></span> <span data-ttu-id="a9ea8-120">O tamanho das linhas nas tabelas base não afeta o tamanho da linha no buffer.</span><span class="sxs-lookup"><span data-stu-id="a9ea8-120">The size of the rows in the base tables does not affect the size of the row in the buffer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a9ea8-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="a9ea8-121">User Action</span></span>  
 <span data-ttu-id="a9ea8-122">Reduza a complexidade da consulta removendo junções ou funções de agregação.</span><span class="sxs-lookup"><span data-stu-id="a9ea8-122">Decrease the complexity of the query by removing joins or aggregate functions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9ea8-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a9ea8-123">See Also</span></span>  
 [<span data-ttu-id="a9ea8-124">OLTP in-memory &#40;Otimização na memória&#41;</span><span class="sxs-lookup"><span data-stu-id="a9ea8-124">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
