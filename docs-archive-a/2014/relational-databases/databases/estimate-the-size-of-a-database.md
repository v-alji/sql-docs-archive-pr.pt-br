---
title: Estimar o tamanho de um banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- space allocation [SQL Server], database size
- calculating database size
- increasing database size
- database size [SQL Server], estimating
- predicting database size
- size [SQL Server], databases
- estimating database size
- designing databases [SQL Server], estimating size
ms.assetid: 5b240161-eba4-44b0-946c-61a8fc00fc8c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6e3a390c4ade2c2dc08f67d2d1461955516e866c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573102"
---
# <a name="estimate-the-size-of-a-database"></a><span data-ttu-id="31448-102">Estimar o tamanho de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="31448-102">Estimate the Size of a Database</span></span>
  <span data-ttu-id="31448-103">Ao projetar um banco de dados, você terá de estimar o quão grande ele ficará quando estiver completo com dados.</span><span class="sxs-lookup"><span data-stu-id="31448-103">When you design a database, you may have to estimate how large the database will be when filled with data.</span></span> <span data-ttu-id="31448-104">A estimativa do tamanho do banco de dados pode ajudá-lo a determinar a configuração de hardware que será necessária para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="31448-104">Estimating the size of the database can help you determine the hardware configuration you will require to do the following:</span></span>  
  
-   <span data-ttu-id="31448-105">Alcançar o desempenho solicitado pelos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="31448-105">Achieve the performance required by your applications.</span></span>  
  
-   <span data-ttu-id="31448-106">Garantir a quantia física apropriada de espaço em disco exigida para armazenar os dados e índices.</span><span class="sxs-lookup"><span data-stu-id="31448-106">Guarantee the appropriate physical amount of disk space required to store the data and indexes.</span></span>  
  
 <span data-ttu-id="31448-107">O cálculo do tamanho de um banco de dados também pode ajudar a determinar se o design de banco de dados precisa ser refinado.</span><span class="sxs-lookup"><span data-stu-id="31448-107">Estimating the size of a database can also help you determine whether the database design needs refining.</span></span> <span data-ttu-id="31448-108">Por exemplo, você pode determinar que o tamanho do banco de dados seja grande demais para implementar em sua empresa e que mais normalização seja necessária.</span><span class="sxs-lookup"><span data-stu-id="31448-108">For example, you may determine that the estimated size of the database is too large to implement in your organization and that more normalization is required.</span></span> <span data-ttu-id="31448-109">Ao contrário, o tamanho calculado pode ser menor que o esperado.</span><span class="sxs-lookup"><span data-stu-id="31448-109">Conversely, the estimated size may be smaller than expected.</span></span> <span data-ttu-id="31448-110">Isto permitiria desnormalizar o banco de dados para melhorar desempenho da consulta.</span><span class="sxs-lookup"><span data-stu-id="31448-110">This would allow you to denormalize the database to improve query performance.</span></span>  
  
 <span data-ttu-id="31448-111">Para estimar o tamanho do banco de dados, estime o tamanho de cada tabela individualmente e adicione os valores obtidos.</span><span class="sxs-lookup"><span data-stu-id="31448-111">To estimate the size of a database, estimate the size of each table individually and then add the values obtained.</span></span> <span data-ttu-id="31448-112">O tamanho da tabela depende se a tabela possui índices e, se possuir, de que tipo de índices.</span><span class="sxs-lookup"><span data-stu-id="31448-112">The size of a table depends on whether the table has indexes and, if they do, what type of indexes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="31448-113">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="31448-113">In This Section</span></span>  
  
|<span data-ttu-id="31448-114">Tópico</span><span class="sxs-lookup"><span data-stu-id="31448-114">Topic</span></span>|<span data-ttu-id="31448-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="31448-115">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="31448-116">Estimar o tamanho de uma tabela</span><span class="sxs-lookup"><span data-stu-id="31448-116">Estimate the Size of a Table</span></span>](estimate-the-size-of-a-table.md)|<span data-ttu-id="31448-117">Define as etapas e cálculos necessários para estimar a quantidade de espaço exigida para armazenar os dados em uma tabela e índices associados.</span><span class="sxs-lookup"><span data-stu-id="31448-117">Defines the steps and calculations needed to estimate the amount of space required to store the data in a table and associated indexes.</span></span>|  
|[<span data-ttu-id="31448-118">Estimar o tamanho de um heap</span><span class="sxs-lookup"><span data-stu-id="31448-118">Estimate the Size of a Heap</span></span>](estimate-the-size-of-a-heap.md)|<span data-ttu-id="31448-119">Define as etapas e cálculos necessários para estimar a quantidade de espaço exigida para armazenar os dados em um heap.</span><span class="sxs-lookup"><span data-stu-id="31448-119">Defines the steps and calculations needed to estimate the amount of space required to store the data in a heap.</span></span> <span data-ttu-id="31448-120">Um heap é uma tabela que não tem um índice clusterizados.</span><span class="sxs-lookup"><span data-stu-id="31448-120">A heap is a table that does not have a clustered index.</span></span>|  
|[<span data-ttu-id="31448-121">Estimar o tamanho de um índice clusterizado</span><span class="sxs-lookup"><span data-stu-id="31448-121">Estimate the Size of a Clustered Index</span></span>](estimate-the-size-of-a-clustered-index.md)|<span data-ttu-id="31448-122">Define as etapas e cálculos necessários para estimar a quantidade de espaço exigida para armazenar os dados em um índice clusterizado.</span><span class="sxs-lookup"><span data-stu-id="31448-122">Defines the steps and calculations needed to estimate the amount of space required to store the data in a clustered index.</span></span>|  
|[<span data-ttu-id="31448-123">Estimar o tamanho de um índice não clusterizado</span><span class="sxs-lookup"><span data-stu-id="31448-123">Estimate the Size of a Nonclustered Index</span></span>](estimate-the-size-of-a-nonclustered-index.md)|<span data-ttu-id="31448-124">Define as etapas e cálculos necessários para estimar a quantidade de espaço exigida para armazenar os dados em um índice não clusterizado.</span><span class="sxs-lookup"><span data-stu-id="31448-124">Defines the steps and calculations needed to estimate the amount of space required to store the data in a nonclustered index.</span></span>|  
  
  
