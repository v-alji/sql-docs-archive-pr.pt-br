---
title: MSSQLSERVER_41396 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41396 (Database Engine error)
ms.assetid: 4ff04042-8367-46f3-8a16-c94682d6eedb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2386c805b61631c9b843753d74ba6616e7344223
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680426"
---
# <a name="mssqlserver_41396"></a><span data-ttu-id="560e0-102">MSSQLSERVER_41396</span><span class="sxs-lookup"><span data-stu-id="560e0-102">MSSQLSERVER_41396</span></span>
    
## <a name="details"></a><span data-ttu-id="560e0-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="560e0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="560e0-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="560e0-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="560e0-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="560e0-105">Event ID</span></span>|<span data-ttu-id="560e0-106">41396</span><span class="sxs-lookup"><span data-stu-id="560e0-106">41396</span></span>|  
|<span data-ttu-id="560e0-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="560e0-107">Event Source</span></span>|<span data-ttu-id="560e0-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="560e0-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="560e0-109">Componente</span><span class="sxs-lookup"><span data-stu-id="560e0-109">Component</span></span>|<span data-ttu-id="560e0-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="560e0-110">SQLEngine</span></span>|  
|<span data-ttu-id="560e0-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="560e0-111">Symbolic Name</span></span>|<span data-ttu-id="560e0-112">MAX_SORT_ROWS_EXCEEDED</span><span class="sxs-lookup"><span data-stu-id="560e0-112">MAX_SORT_ROWS_EXCEEDED</span></span>|  
|<span data-ttu-id="560e0-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="560e0-113">Message Text</span></span>|<span data-ttu-id="560e0-114">A operação de classificação excedeu o limite de buffer.</span><span class="sxs-lookup"><span data-stu-id="560e0-114">The sort operation exceeded the buffer limit.</span></span> <span data-ttu-id="560e0-115">A execução do procedimento armazenado foi anulada.</span><span class="sxs-lookup"><span data-stu-id="560e0-115">The stored procedure execution was aborted.</span></span> <span data-ttu-id="560e0-116">Consulte os manuais online do SQL Server para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="560e0-116">Consult SQL Server Books Online for more information.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="560e0-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="560e0-117">Explanation</span></span>  
 <span data-ttu-id="560e0-118">Os procedimentos armazenados compilados de modo nativo executam operações de classificação na memória.</span><span class="sxs-lookup"><span data-stu-id="560e0-118">Natively compiled stored procedures perform sort operations in memory.</span></span> <span data-ttu-id="560e0-119">Há um limite para o tamanho do buffer de classificação.</span><span class="sxs-lookup"><span data-stu-id="560e0-119">There is a limit on the size of the sort buffer.</span></span> <span data-ttu-id="560e0-120">Esse erro significa que o tamanho do buffer de classificação excedeu esse limite.</span><span class="sxs-lookup"><span data-stu-id="560e0-120">This error means that the size of the sort buffer exceeds this limit.</span></span> <span data-ttu-id="560e0-121">A operação de classificação e a execução do procedimento armazenado anuladas.</span><span class="sxs-lookup"><span data-stu-id="560e0-121">The sort operation and the stored procedure execution aborted.</span></span>  
  
 <span data-ttu-id="560e0-122">O tamanho de cada linha ou entrada no buffer de classificação é determinado pelo número de linhas classificadas assim como o número de junções e o número e o tipo de funções de agregação na consulta.</span><span class="sxs-lookup"><span data-stu-id="560e0-122">The size of each row or entry in the sort buffer is determined by the number of rows sorted as well as the number of joins and the number and type of aggregate functions in the query.</span></span> <span data-ttu-id="560e0-123">Ao simplificando a consulta, você poderá reduzir o tamanho de cada linha, ajustando, assim, mais linhas no buffer de classificação.</span><span class="sxs-lookup"><span data-stu-id="560e0-123">By simplifying the query, you can reduce the size of each row thereby fitting more rows in the sort buffer.</span></span> <span data-ttu-id="560e0-124">O tamanho das linhas nas tabelas base não afeta o tamanho de cada linha ou entrada no buffer de classificação.</span><span class="sxs-lookup"><span data-stu-id="560e0-124">The size of the rows in the base tables does not affect the size of each row or entry in the sort buffer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="560e0-125">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="560e0-125">User Action</span></span>  
 <span data-ttu-id="560e0-126">Selecione menos linhas ou reduza a complexidade da consulta removendo junções ou funções de agregação.</span><span class="sxs-lookup"><span data-stu-id="560e0-126">Select fewer rows or decrease the complexity of the query by removing joins or aggregate functions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="560e0-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="560e0-127">See Also</span></span>  
 [<span data-ttu-id="560e0-128">OLTP in-memory &#40;Otimização na memória&#41;</span><span class="sxs-lookup"><span data-stu-id="560e0-128">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
