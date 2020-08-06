---
title: Consultar dados espaciais do vizinho mais próximo | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 7af4ad5d-484e-45b4-aa16-83c33b358bb6
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 644b3e5cfdaeff7457639bc2da77260b64011735
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582902"
---
# <a name="query-spatial-data-for-nearest-neighbor"></a><span data-ttu-id="98ea6-102">Consultar dados espaciais de vizinho mais próximo</span><span class="sxs-lookup"><span data-stu-id="98ea6-102">Query Spatial Data for Nearest Neighbor</span></span>
  <span data-ttu-id="98ea6-103">Uma consulta comum usada com dados espaciais é a consulta de Vizinho Mais Próximo.</span><span class="sxs-lookup"><span data-stu-id="98ea6-103">A common query used with spatial data is the Nearest Neighbor query.</span></span> <span data-ttu-id="98ea6-104">As consultas de Vizinho Mais Próximo são usadas para localizar os objetos espaciais mais próximos a um objeto espacial específico.</span><span class="sxs-lookup"><span data-stu-id="98ea6-104">Nearest Neighbor queries are used to find the closest spatial objects to a specific spatial object.</span></span> <span data-ttu-id="98ea6-105">Por exemplo, um localizador de lojas para um site geralmente deve localizar os locais de loja mais próximos ao local de um cliente.</span><span class="sxs-lookup"><span data-stu-id="98ea6-105">For example a store locater for a Web site often must find the closest store locations to a customer location.</span></span>  
  
 <span data-ttu-id="98ea6-106">Uma consulta de Vizinho Mais Próximo pode ser escrita em uma variedade de formatos de consulta válidos, mas, para que a consulta de Vizinho Mais Próximo use um índice espacial, a sintaxe a seguir deve ser usada.</span><span class="sxs-lookup"><span data-stu-id="98ea6-106">A Nearest Neighbor query can be written in a variety of valid query formats, but for the Nearest Neighbor query to use a spatial index the following syntax must be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98ea6-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="98ea6-107">Syntax</span></span>  
  
```vb  
SELECT TOP ( number )  
        [ WITH TIES ]  
        [ * | expression ]   
        [, ...]  
    FROM spatial_table_reference, ...   
        [ WITH   
            (   
                [ INDEX ( index_ref ) ]   
                [ , SPATIAL_WINDOW_MAX_CELLS = <value>]   
                [ ,... ]   
            )   
        ]  
    WHERE   
        column_ref.STDistance ( @spatial_ object )   
            {   
                [ IS NOT NULL ] | [ < const ] | [ > const ]   
                | [ <= const ] | [ >= const ] | [ <> const ] ]   
            }  
            [ AND { other_predicate } ]   
    }  
    ORDER BY column_ref.STDistance ( @spatial_ object ) [ ,...n ]  
[ ; ]  
  
```  
  
## <a name="nearest-neighbor-query-and-spatial-indexes"></a><span data-ttu-id="98ea6-108">Consulta de Vizinho Mais Próximo e índices espaciais</span><span class="sxs-lookup"><span data-stu-id="98ea6-108">Nearest Neighbor Query and Spatial Indexes</span></span>  
 <span data-ttu-id="98ea6-109">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], as cláusulas `TOP` e `ORDER BY` são usadas para realizar uma consulta de Vizinho Mais Próximo em colunas de dados espaciais.</span><span class="sxs-lookup"><span data-stu-id="98ea6-109">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], `TOP` and `ORDER BY` clauses are used to perform a Nearest Neighbor query on spatial data columns.</span></span> <span data-ttu-id="98ea6-110">A cláusula `ORDER BY` contém uma chamada ao método `STDistance()` para o tipo de dados de coluna espacial.</span><span class="sxs-lookup"><span data-stu-id="98ea6-110">The `ORDER BY` clause contains a call to the `STDistance()` method for the spatial column data type.</span></span> <span data-ttu-id="98ea6-111">A cláusula `TOP` indica o número de objetos a ser retornado para a consulta.</span><span class="sxs-lookup"><span data-stu-id="98ea6-111">The `TOP` clause indicates the number of objects to return for the query.</span></span>  
  
 <span data-ttu-id="98ea6-112">Os requisitos a seguir devem ser satisfeitos para uma consulta de Vizinho Mais Próximo para usar um índice espacial:</span><span class="sxs-lookup"><span data-stu-id="98ea6-112">The following requirements must be met for a Nearest Neighbor query to use a spatial index:</span></span>  
  
1.  <span data-ttu-id="98ea6-113">Um índice espacial deve estar presente em uma das colunas espaciais e o método `STDistance()` deve usar essa coluna nas cláusulas `WHERE` e `ORDER BY`.</span><span class="sxs-lookup"><span data-stu-id="98ea6-113">A spatial index must be present on one of the spatial columns and the `STDistance()` method must use that column in the `WHERE` and `ORDER BY` clauses.</span></span>  
  
2.  <span data-ttu-id="98ea6-114">A cláusula `TOP` não pode conter uma instrução `PERCENT`.</span><span class="sxs-lookup"><span data-stu-id="98ea6-114">The `TOP` clause cannot contain a `PERCENT` statement.</span></span>  
  
3.  <span data-ttu-id="98ea6-115">A cláusula `WHERE` deve conter um método `STDistance()`.</span><span class="sxs-lookup"><span data-stu-id="98ea6-115">The `WHERE` clause must contain a `STDistance()` method.</span></span>  
  
4.  <span data-ttu-id="98ea6-116">Se houver vários predicados na cláusula `WHERE`, o predicado que contém o método `STDistance()` deve ser conectado por uma conjunção `AND` aos outros predicados.</span><span class="sxs-lookup"><span data-stu-id="98ea6-116">If there are multiple predicates in the `WHERE` clause then the predicate containing `STDistance()` method must be connected by an `AND` conjunction to the other predicates.</span></span> <span data-ttu-id="98ea6-117">O método `STDistance()` não pode estar em uma parte opcional da cláusula `WHERE`.</span><span class="sxs-lookup"><span data-stu-id="98ea6-117">The `STDistance()` method cannot be in an optional part of the `WHERE` clause.</span></span>  
  
5.  <span data-ttu-id="98ea6-118">A primeira expressão na cláusula `ORDER BY` deve usar o método `STDistance()`.</span><span class="sxs-lookup"><span data-stu-id="98ea6-118">The first expression in the `ORDER BY` clause must use the `STDistance()` method.</span></span>  
  
6.  <span data-ttu-id="98ea6-119">A ordem de classificação para a primeira expressão `STDistance()` na cláusula `ORDER BY` deve ser `ASC`.</span><span class="sxs-lookup"><span data-stu-id="98ea6-119">Sort order for the first `STDistance()` expression in the `ORDER BY` clause must be `ASC`.</span></span>  
  
7.  <span data-ttu-id="98ea6-120">Todas as linhas para as quais `STDistance` retorna `NULL` devem ser filtradas.</span><span class="sxs-lookup"><span data-stu-id="98ea6-120">All the rows for which `STDistance` returns `NULL` must be filtered out.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="98ea6-121">Os métodos que levam `geography` ou tipos de dados `geometry` como argumentos retornarão `NULL` se o SRIDs não forem o mesmo para os tipos.</span><span class="sxs-lookup"><span data-stu-id="98ea6-121">Methods that take `geography` or `geometry` data types as arguments will return `NULL` if the SRIDs are not the same for the types.</span></span>  
  
 <span data-ttu-id="98ea6-122">É recomendado que os novos mosaicos de índice espaciais sejam usados para índices usados em consultas de Vizinhos Mais Próximos.</span><span class="sxs-lookup"><span data-stu-id="98ea6-122">It is recommended that the new spatial index tessellations be used for indexes used in Nearest Neighbor queries.</span></span> <span data-ttu-id="98ea6-123">Para obter mais informações sobre mosaicos de índice espacial, veja [Dados espaciais &#40;SQL Server&#41;](spatial-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="98ea6-123">For more information on spatial index tessellations, see [Spatial Data &#40;SQL Server&#41;](spatial-data-sql-server.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="98ea6-124">Exemplo</span><span class="sxs-lookup"><span data-stu-id="98ea6-124">Example</span></span>  
 <span data-ttu-id="98ea6-125">O exemplo de código a seguir mostra para uma consulta de Vizinho Mais Próximo que pode usar um índice espacial.</span><span class="sxs-lookup"><span data-stu-id="98ea6-125">The following code example shows a Nearest Neighbor query that can use a spatial index.</span></span> <span data-ttu-id="98ea6-126">O exemplo usa a tabela `Person.Address` no banco de dados `AdventureWorks2012` .</span><span class="sxs-lookup"><span data-stu-id="98ea6-126">The example uses the `Person.Address` table in `AdventureWorks2012` database.</span></span>  
  
```  
USE AdventureWorks2012  
GO  
DECLARE @g geography = 'POINT(-121.626 47.8315)';  
SELECT TOP(7) SpatialLocation.ToString(), City FROM Person.Address  
WHERE SpatialLocation.STDistance(@g) IS NOT NULL  
ORDER BY SpatialLocation.STDistance(@g);  
  
```  
  
 <span data-ttu-id="98ea6-127">Crie um índice espacial na coluna SpatialLocation para ver como uma consulta de Vizinho Mais Próximo usa um índice espacial.</span><span class="sxs-lookup"><span data-stu-id="98ea6-127">Create a spatial index on the column SpatialLocation to see how a Nearest Neighbor query uses a spatial index.</span></span> <span data-ttu-id="98ea6-128">Para obter mais informações sobre como criar índices espaciais, consulte [Create, Modify, and Drop Spatial Indexes](create-modify-and-drop-spatial-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="98ea6-128">For more information on creating spatial indexes, see [Create, Modify, and Drop Spatial Indexes](create-modify-and-drop-spatial-indexes.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="98ea6-129">Exemplo</span><span class="sxs-lookup"><span data-stu-id="98ea6-129">Example</span></span>  
 <span data-ttu-id="98ea6-130">O exemplo de código a seguir mostra para uma consulta de Vizinho Mais Próximo que não pode usar um índice espacial.</span><span class="sxs-lookup"><span data-stu-id="98ea6-130">The following code example shows a Nearest Neighbor query that cannot use a spatial index.</span></span>  
  
```  
USE AdventureWorks2012  
GO  
DECLARE @g geography = 'POINT(-121.626 47.8315)';  
SELECT TOP(7) SpatialLocation.ToString(), City FROM Person.Address  
ORDER BY SpatialLocation.STDistance(@g);  
  
```  
  
 <span data-ttu-id="98ea6-131">A consulta não tem uma cláusula `WHERE` que usa `STDistance()` em uma forma especificada na seção de sintaxe; portanto, a consulta não pode usar um índice espacial.</span><span class="sxs-lookup"><span data-stu-id="98ea6-131">The query lacks a `WHERE` clause that uses `STDistance()` in a form specified in the syntax section so the query cannot use a spatial index.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98ea6-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="98ea6-132">See Also</span></span>  
 [<span data-ttu-id="98ea6-133">Dados espaciais &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="98ea6-133">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
