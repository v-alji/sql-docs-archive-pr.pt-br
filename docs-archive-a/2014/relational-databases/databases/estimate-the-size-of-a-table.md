---
title: Estimar o tamanho de uma tabela | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- pages [SQL Server], space
- space [SQL Server], tables
- row size [SQL Server]
- size [SQL Server], tables
- column size [SQL Server]
- predicting table size [SQL Server]
- table size [SQL Server]
- estimating table size
- clustered indexes, table size
- disk space [SQL Server], tables
- space allocation [SQL Server], table size
- designing databases [SQL Server], estimating size
- reserved free rows per page [SQL Server]
- calculating table size
ms.assetid: 15c17c92-616f-402e-894b-907a296efe5f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4a16d439d3b2bc59479866b7bb36295ec4fc8950
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683545"
---
# <a name="estimate-the-size-of-a-table"></a><span data-ttu-id="7fabe-102">Estimar o tamanho de uma tabela</span><span class="sxs-lookup"><span data-stu-id="7fabe-102">Estimate the Size of a Table</span></span>
  <span data-ttu-id="7fabe-103">Você pode usar as seguintes etapas para estimar a quantidade de espaço necessária para armazenar dados em uma tabela:</span><span class="sxs-lookup"><span data-stu-id="7fabe-103">You can use the following steps to estimate the amount of space required to store data in a table:</span></span>  
  
1.  <span data-ttu-id="7fabe-104">Calcular o espaço necessário para o heap ou índice clusterizado seguindo as instruções em [Estimar o tamanho de um heap](estimate-the-size-of-a-heap.md) ou [Estimar o tamanho de um índice clusterizado](estimate-the-size-of-a-clustered-index.md).</span><span class="sxs-lookup"><span data-stu-id="7fabe-104">Calculate the space required for the heap or clustered index following the instructions in [Estimate the Size of a Heap](estimate-the-size-of-a-heap.md) or [Estimate the Size of a Clustered Index](estimate-the-size-of-a-clustered-index.md).</span></span>  
  
2.  <span data-ttu-id="7fabe-105">Calcule o espaço necessário para cada índice não clusterizado, seguindo as instruções em [Estimar o tamanho de um índice não clusterizado](estimate-the-size-of-a-nonclustered-index.md).</span><span class="sxs-lookup"><span data-stu-id="7fabe-105">For each nonclustered index, calculate the space required for it by following the instructions in [Estimate the Size of a Nonclustered Index](estimate-the-size-of-a-nonclustered-index.md).</span></span>  
  
3.  <span data-ttu-id="7fabe-106">Some os valores calculados nas etapas 1 e 2.</span><span class="sxs-lookup"><span data-stu-id="7fabe-106">Add the values calculated in steps 1 and 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fabe-107">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7fabe-107">See Also</span></span>  
 <span data-ttu-id="7fabe-108">[Estimar o tamanho de um banco de dados](estimate-the-size-of-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="7fabe-108">[Estimate the Size of a Database](estimate-the-size-of-a-database.md) </span></span>  
 <span data-ttu-id="7fabe-109">[Estimar o tamanho de um heap](estimate-the-size-of-a-heap.md) </span><span class="sxs-lookup"><span data-stu-id="7fabe-109">[Estimate the Size of a Heap](estimate-the-size-of-a-heap.md) </span></span>  
 <span data-ttu-id="7fabe-110">[Estimar o tamanho de um índice clusterizado](estimate-the-size-of-a-clustered-index.md) </span><span class="sxs-lookup"><span data-stu-id="7fabe-110">[Estimate the Size of a Clustered Index](estimate-the-size-of-a-clustered-index.md) </span></span>  
 [<span data-ttu-id="7fabe-111">Estimar o tamanho de um índice não clusterizado</span><span class="sxs-lookup"><span data-stu-id="7fabe-111">Estimate the Size of a Nonclustered Index</span></span>](estimate-the-size-of-a-nonclustered-index.md)  
  
  
