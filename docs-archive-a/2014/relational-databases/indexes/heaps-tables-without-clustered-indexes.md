---
title: Heaps (tabelas sem índices clusterizados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- heaps
ms.assetid: df5c4dfb-d372-4d0f-859a-a2d2533ee0d7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2a39bac2e0352f2adc7749e980d5cc91044f8ab2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583050"
---
# <a name="heaps-tables-without-clustered-indexes"></a><span data-ttu-id="0fbc8-102">Heaps (Tabelas sem índices clusterizados)</span><span class="sxs-lookup"><span data-stu-id="0fbc8-102">Heaps (Tables without Clustered Indexes)</span></span>
  <span data-ttu-id="0fbc8-103">Heap é uma tabela sem índice clusterizado.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-103">A heap is a table without a clustered index.</span></span> <span data-ttu-id="0fbc8-104">Podem ser criados um ou mais índices não clusterizados em tabelas armazenadas como um heap.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-104">One or more nonclustered indexes can be created on tables stored as a heap.</span></span> <span data-ttu-id="0fbc8-105">Dados são armazenados no heap sem especificar uma ordem.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-105">Data is stored in the heap without specifying an order.</span></span> <span data-ttu-id="0fbc8-106">Normalmente, os dados são armazenados inicialmente na ordem em que as linhas são inseridas na tabela, mas o [!INCLUDE[ssDE](../../includes/ssde-md.md)] pode mover os dados no heap para armazenar as linhas de forma eficaz; portanto, a ordem de dados não pode ser prevista.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-106">Usually data is initially stored in the order in which is the rows are inserted into the table, but the [!INCLUDE[ssDE](../../includes/ssde-md.md)] can move data around in the heap to store the rows efficiently; so the data order cannot be predicted.</span></span> <span data-ttu-id="0fbc8-107">Para garantir a ordem de linhas retornadas de um heap, você deve usar a cláusula `ORDER BY`.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-107">To guarantee the order of rows returned from a heap, you must use the `ORDER BY` clause.</span></span> <span data-ttu-id="0fbc8-108">Para especificar a ordem de armazenamento das linhas, crie um índice clusterizado na tabela, de forma que a tabela não seja um heap.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-108">To specify the order for storage of the rows, create a clustered index on the table, so that the table is not a heap.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0fbc8-109">Às vezes, há boas razões para deixar uma tabela como heap em vez de criar um índice clusterizado, mas usar heaps efetivamente é uma habilidade avançada.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-109">There are sometimes good reasons to leave a table as a heap instead of creating a clustered index, but using heaps effectively is an advanced skill.</span></span> <span data-ttu-id="0fbc8-110">A maioria das tabelas deve ter um índice clusterizado cuidadosamente escolhido, a menos que haja uma boa razão boa para deixar a tabela como heap.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-110">Most tables should have a carefully chosen clustered index unless a good reason exists for leaving the table as a heap.</span></span>  
  
## <a name="when-to-use-a-heap"></a><span data-ttu-id="0fbc8-111">Quando usar um heap</span><span class="sxs-lookup"><span data-stu-id="0fbc8-111">When to Use a Heap</span></span>  
 <span data-ttu-id="0fbc8-112">Se uma tabela for um heap e não tiver um índice clusterizado, a tabela inteira deverá ser examinada (análise de tabela) para localizar as linhas.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-112">If a table is a heap and does not have any nonclustered indexes, then the entire table must be examined (a table scan) to find any row.</span></span> <span data-ttu-id="0fbc8-113">Isso pode ser aceitável quando a tabela é pequena, como uma lista dos 12 escritórios regionais de uma empresa.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-113">This can be acceptable when the table is tiny, such as a list of the 12 regional offices of a company.</span></span>  
  
 <span data-ttu-id="0fbc8-114">Quando uma tabela é armazenada como heap, linhas individuais são identificadas por referência a um RID (identificador de linha) que consiste em número do arquivo, número da página de dados e local na página.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-114">When a table is stored as a heap, individual rows are identified by reference to a row identifier (RID) consisting of the file number, data page number, and slot on the page.</span></span> <span data-ttu-id="0fbc8-115">A ID de linha é uma estrutura pequena e eficiente.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-115">The row id is a small and efficient structure.</span></span> <span data-ttu-id="0fbc8-116">Às vezes, os arquitetos de dados usam heaps quando os dados são sempre acessados por índices não clusterizados e o RID é menor que uma chave de índice clusterizado.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-116">Sometimes data architects use heaps when data is always accessed through nonclustered indexes and the RID is smaller than a clustered index key.</span></span>  
  
## <a name="when-not-to-use-a-heap"></a><span data-ttu-id="0fbc8-117">Quando não usar um heap</span><span class="sxs-lookup"><span data-stu-id="0fbc8-117">When Not to Use a Heap</span></span>  
 <span data-ttu-id="0fbc8-118">Não use um heap quando os dados são retornados frequentemente em uma ordem classificada.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-118">Do not use a heap when the data is frequently returned in a sorted order.</span></span> <span data-ttu-id="0fbc8-119">Um índice clusterizado na coluna de classificação pode evitar a operação de classificação.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-119">A clustered index on the sorting column could avoid the sorting operation.</span></span>  
  
 <span data-ttu-id="0fbc8-120">Não use um heap quando os dados forem agrupados com frequência.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-120">Do not use a heap when the data is frequently grouped together.</span></span> <span data-ttu-id="0fbc8-121">Os dados devem ser classificados antes de serem agrupados, e um índice clusterizado na coluna de classificação pode evitar a operação de classificação.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-121">Data must be sorted before it is grouped, and a clustered index on the sorting column could avoid the sorting operation.</span></span>  
  
 <span data-ttu-id="0fbc8-122">Não use um heap quando intervalos de dados são consultados frequentemente na tabela.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-122">Do not use a heap when ranges of data are frequently queried from the table.</span></span>  <span data-ttu-id="0fbc8-123">Um índice clusterizado na coluna de intervalo pode evitar a classificação do heap inteiro.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-123">A clustered index on the range column will avoid sorting the entire heap.</span></span>  
  
 <span data-ttu-id="0fbc8-124">Não use um heap quando não houver índice não clusterizado e a tabela for grande.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-124">Do not use a heap when there are no nonclustered indexes and the table is large.</span></span> <span data-ttu-id="0fbc8-125">Em um heap, todas as linhas do heap devem ser lidas para localizar qualquer linha.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-125">In a heap, all rows of the heap must be read to find any row.</span></span>  
  
## <a name="managing-heaps"></a><span data-ttu-id="0fbc8-126">Gerenciando heaps</span><span class="sxs-lookup"><span data-stu-id="0fbc8-126">Managing Heaps</span></span>  
 <span data-ttu-id="0fbc8-127">Para criar um heap, crie uma tabela sem um índice clusterizado.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-127">To create a heap, create a table without a clustered index.</span></span> <span data-ttu-id="0fbc8-128">Se uma tabela já tiver um índice clusterizado, descarte o índice clusterizado para retornar a tabela a um heap.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-128">If a table already has a clustered index, drop the clustered index to return the table to a heap.</span></span>  
  
 <span data-ttu-id="0fbc8-129">Para remover um heap, crie um índice clusterizado no heap.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-129">To remove a heap, create a clustered index on the heap.</span></span>  
  
 <span data-ttu-id="0fbc8-130">Para recriar um heap para recuperar o espaço desperdiçado, crie um índice clusterizado no heap e descarte esse índice clusterizado.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-130">To rebuild a heap to reclaim wasted space, create a clustered index on the heap, and then drop that clustered index.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="0fbc8-131">Criar ou descartar índices clusterizados requer a regravação da tabela inteira.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-131">Creating or dropping clustered indexes requires rewriting the entire table.</span></span> <span data-ttu-id="0fbc8-132">Se a tabela tiver índices não clusterizados, todos os índices não clusterizados deverão ser recriados sempre que o índice clusterizado for alterado.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-132">If the table has nonclustered indexes, all the nonclustered indexes must all be recreated whenever the clustered index is changed.</span></span> <span data-ttu-id="0fbc8-133">Portanto, mudar de um heap para uma estrutura de índice clusterizado ou vice-versa pode demorar muito e exigir espaço em disco para reorganizar os dados em tempdb.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-133">Therefore, changing from a heap to a clustered index structure or back can take a lot of time and require disk space for reordering data in tempdb.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="0fbc8-134">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="0fbc8-134">Related Content</span></span>  
 [<span data-ttu-id="0fbc8-135">CREATE INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0fbc8-135">CREATE INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-index-transact-sql)  
  
 [<span data-ttu-id="0fbc8-136">DROP INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0fbc8-136">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
 [<span data-ttu-id="0fbc8-137">Índices clusterizados e não clusterizados descritos</span><span class="sxs-lookup"><span data-stu-id="0fbc8-137">Clustered and Nonclustered Indexes Described</span></span>](clustered-and-nonclustered-indexes-described.md)  
  
  
