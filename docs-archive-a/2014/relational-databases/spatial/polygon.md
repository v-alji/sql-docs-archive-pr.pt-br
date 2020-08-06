---
title: Polígono | Microsoft Docs
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- geometry subtypes [SQL Server]
- Polygon geometry subtype [SQL Server]
ms.assetid: b6a21c3c-fdb8-4187-8229-1c488454fdfb
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 040bb8a2558cc57b1b99a3ce984bec3c8925bc0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582904"
---
# <a name="polygon"></a><span data-ttu-id="d17f6-102">Polygon</span><span class="sxs-lookup"><span data-stu-id="d17f6-102">Polygon</span></span>
  <span data-ttu-id="d17f6-103">Um `Polygon` é uma superfície bidimensional armazenada como uma sequência de pontos que define um anel delimitador exterior e zero ou mais anéis interiores.</span><span class="sxs-lookup"><span data-stu-id="d17f6-103">A `Polygon` is a two-dimensional surface stored as a sequence of points defining an exterior bounding ring and zero or more interior rings.</span></span>

## <a name="polygon-instances"></a><span data-ttu-id="d17f6-104">Instâncias de polígono</span><span class="sxs-lookup"><span data-stu-id="d17f6-104">Polygon instances</span></span>
 <span data-ttu-id="d17f6-105">Uma instância `Polygon` pode ser formada de um anel que tem pelo menos três pontos distintos.</span><span class="sxs-lookup"><span data-stu-id="d17f6-105">A `Polygon` instance can be formed from a ring that has at least three distinct points.</span></span> <span data-ttu-id="d17f6-106">Uma instância `Polygon` também pode estar vazia.</span><span class="sxs-lookup"><span data-stu-id="d17f6-106">A `Polygon` instance can also be empty.</span></span>

 <span data-ttu-id="d17f6-107">Os anéis exteriores e todos os anéis interiores de um `Polygon` definem seu limite.</span><span class="sxs-lookup"><span data-stu-id="d17f6-107">The exterior and any interior rings of a `Polygon` define its boundary.</span></span> <span data-ttu-id="d17f6-108">O espaço dentro dos anéis define o interior do `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="d17f6-108">The space within the rings defines the interior of the `Polygon`.</span></span>

 <span data-ttu-id="d17f6-109">A ilustração a seguir mostra exemplos de instâncias `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="d17f6-109">The illustration below shows examples of `Polygon` instances.</span></span>

 <span data-ttu-id="d17f6-110">![Exemplos das instâncias geométricas Polygon](../../database-engine/media/polygon.gif "Exemplos das instâncias geométricas Polygon")</span><span class="sxs-lookup"><span data-stu-id="d17f6-110">![Examples of geometry Polygon instances](../../database-engine/media/polygon.gif "Examples of geometry Polygon instances")</span></span>

 <span data-ttu-id="d17f6-111">Conforme mostrado na ilustração:</span><span class="sxs-lookup"><span data-stu-id="d17f6-111">As shown in the illustration:</span></span>

1.  <span data-ttu-id="d17f6-112">A Figura 1 é uma instância `Polygon` cujo limite está definido por um anel exterior.</span><span class="sxs-lookup"><span data-stu-id="d17f6-112">Figure 1 is a `Polygon` instance whose boundary is defined by an exterior ring.</span></span>

2.  <span data-ttu-id="d17f6-113">A Figura 2 é uma instância `Polygon` cujo limite está definido por um anel exterior e dois anéis interiores.</span><span class="sxs-lookup"><span data-stu-id="d17f6-113">Figure 2 is a `Polygon` instance whose boundary is defined by an exterior ring and two interior rings.</span></span> <span data-ttu-id="d17f6-114">A área dentro dos anéis interiores faz parte do exterior da instância `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="d17f6-114">The area inside the interior rings is part of the exterior of the `Polygon` instance.</span></span>

3.  <span data-ttu-id="d17f6-115">A Figura 3 é uma instância `Polygon` válida porque seus anéis interiores cruzam em um único ponto tangente.</span><span class="sxs-lookup"><span data-stu-id="d17f6-115">Figure 3 is a valid `Polygon` instance because its interior rings intersect at a single tangent point.</span></span>

### <a name="accepted-instances"></a><span data-ttu-id="d17f6-116">Instâncias aceitas</span><span class="sxs-lookup"><span data-stu-id="d17f6-116">Accepted instances</span></span>
 <span data-ttu-id="d17f6-117">Instâncias `Polygon` aceitas são instâncias que podem ser armazenadas em uma variável `geometry` ou `geography` sem lançar uma exceção.</span><span class="sxs-lookup"><span data-stu-id="d17f6-117">Accepted `Polygon` instances are instances that can be stored in a `geometry` or `geography` variable without throwing an exception.</span></span> <span data-ttu-id="d17f6-118">As seguintes instâncias `Polygon` são aceitas:</span><span class="sxs-lookup"><span data-stu-id="d17f6-118">The following are accepted `Polygon` instances:</span></span>

-   <span data-ttu-id="d17f6-119">Uma instância `Polygon` vazia</span><span class="sxs-lookup"><span data-stu-id="d17f6-119">An Empty `Polygon` instance</span></span>

-   <span data-ttu-id="d17f6-120">Uma instância `Polygon` que tem um anel exterior aceitável e zero ou mais anéis interiores aceitáveis</span><span class="sxs-lookup"><span data-stu-id="d17f6-120">A `Polygon` instance that has an acceptable exterior ring and zero or more acceptable interior rings</span></span>

 <span data-ttu-id="d17f6-121">Os critérios a seguir são necessários para que um anel seja aceitável.</span><span class="sxs-lookup"><span data-stu-id="d17f6-121">The following criteria are needed for a ring to be acceptable.</span></span>

-   <span data-ttu-id="d17f6-122">A instância `LineString` deve ser aceita.</span><span class="sxs-lookup"><span data-stu-id="d17f6-122">The `LineString` instance must be accepted.</span></span>

-   <span data-ttu-id="d17f6-123">A instância `LineString` deve ter pelo menos quatro pontos.</span><span class="sxs-lookup"><span data-stu-id="d17f6-123">The `LineString` instance must have at least four points.</span></span>

-   <span data-ttu-id="d17f6-124">Os pontos inicial e final da instância `LineString` devem ser iguais.</span><span class="sxs-lookup"><span data-stu-id="d17f6-124">The starting and ending points of the `LineString` instance must be the same.</span></span>

 <span data-ttu-id="d17f6-125">O exemplo a seguir mostra instâncias `Polygon` aceitas.</span><span class="sxs-lookup"><span data-stu-id="d17f6-125">The following example shows accepted `Polygon` instances.</span></span>

```
DECLARE @g1 geometry = 'POLYGON EMPTY';
DECLARE @g2 geometry = 'POLYGON((1 1, 3 3, 3 1, 1 1))';
DECLARE @g3 geometry = 'POLYGON((-5 -5, -5 5, 5 5, 5 -5, -5 -5),(0 0, 3 0, 3 3, 0 3, 0 0))';
DECLARE @g4 geometry = 'POLYGON((-5 -5, -5 5, 5 5, 5 -5, -5 -5),(3 0, 6 0, 6 3, 3 3, 3 0))';
DECLARE @g5 geometry = 'POLYGON((1 1, 1 1, 1 1, 1 1))';
```

 <span data-ttu-id="d17f6-126">Conforme mostrado por `@g4` e `@g5` uma instância aceita de `Polygon` talvez não seja uma instância válida de `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="d17f6-126">As `@g4` and `@g5` show an accepted `Polygon` instance may not be a valid `Polygon` instance.</span></span> <span data-ttu-id="d17f6-127">`@g5` também mostra que uma instância do Polygon precisa conter apenas um anel com quatro pontos para ser aceita.</span><span class="sxs-lookup"><span data-stu-id="d17f6-127">`@g5` also shows that a Polygon instance needs to only contain a ring with any four points to be accepted.</span></span>

 <span data-ttu-id="d17f6-128">Os exemplos a seguir lançam uma `System.FormatException` porque as instâncias `Polygon` não são aceitas.</span><span class="sxs-lookup"><span data-stu-id="d17f6-128">The following examples throw a `System.FormatException` because the `Polygon` instances are not accepted.</span></span>

```
DECLARE @g1 geometry = 'POLYGON((1 1, 3 3, 1 1))';
DECLARE @g2 geometry = 'POLYGON((1 1, 3 3, 3 1, 1 5))';
```

 <span data-ttu-id="d17f6-129">`@g1` não é aceito porque a instância de `LineString` para o anel exterior não contém pontos suficientes.</span><span class="sxs-lookup"><span data-stu-id="d17f6-129">`@g1` is not accepted because the `LineString` instance for the exterior ring does not contain enough points.</span></span> <span data-ttu-id="d17f6-130">`@g2` não é aceito porque o ponto de início da instância `LineString` do anel exterior não é igual ao ponto de término.</span><span class="sxs-lookup"><span data-stu-id="d17f6-130">`@g2` is not accepted because the starting point of the exterior ring `LineString` instance is not the same as the ending point.</span></span> <span data-ttu-id="d17f6-131">O exemplo a seguir tem um anel exterior aceitável, mas o anel interior não é aceitável.</span><span class="sxs-lookup"><span data-stu-id="d17f6-131">The following example has an acceptable exterior ring, but the interior ring is not acceptable.</span></span> <span data-ttu-id="d17f6-132">Isso também lança uma `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="d17f6-132">This also throws a `System.FormatException`.</span></span>

```
DECLARE @g geometry = 'POLYGON((-5 -5, -5 5, 5 5, 5 -5, -5 -5),(0 0, 3 0, 0 0))';
```

### <a name="valid-instances"></a><span data-ttu-id="d17f6-133">Instâncias válidas</span><span class="sxs-lookup"><span data-stu-id="d17f6-133">Valid instances</span></span>
 <span data-ttu-id="d17f6-134">Os anéis interiores de um `Polygon` podem tocar em si mesmos e um no outro em pontos tangentes únicos, mas se os anéis interiores de um `Polygon` se cruzarem, a instância não será válida.</span><span class="sxs-lookup"><span data-stu-id="d17f6-134">The interior rings of a `Polygon` can touch both themselves and each other at single tangent points, but if the interior rings of a `Polygon` cross, the instance is not valid.</span></span>

 <span data-ttu-id="d17f6-135">O exemplo a seguir mostra instâncias `Polygon` válidas.</span><span class="sxs-lookup"><span data-stu-id="d17f6-135">The following example shows valid `Polygon` instances.</span></span>

```
DECLARE @g1 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20))';
DECLARE @g2 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0))';
DECLARE @g3 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0), (-10 0, 0 10, -5 -10, -10 0))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid();
```

 <span data-ttu-id="d17f6-136">`@g3` é válido porque os dois anéis interiores se tocam em um único ponto e não se cruzam.</span><span class="sxs-lookup"><span data-stu-id="d17f6-136">`@g3` is valid because the two interior rings touch at a single point and do not cross each other.</span></span> <span data-ttu-id="d17f6-137">O exemplo a seguir mostra instâncias `Polygon` que não são válidas.</span><span class="sxs-lookup"><span data-stu-id="d17f6-137">The following example shows `Polygon` instances that are not valid.</span></span>

```
DECLARE @g1 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (20 0, 0 10, 0 -20, 20 0))';
DECLARE @g2 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0), (5 0, 1 5, 1 -5, 5 0))';
DECLARE @g3 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0), (-10 0, 0 10, 0 -10, -10 0))';
DECLARE @g4 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0), (-10 0, 1 5, 0 -10, -10 0))';
DECLARE @g5 geometry = 'POLYGON((10 0, 0 10, 0 -10, 10 0), (-20 -20, -20 20, 20 20, 20 -20, -20 -20) )';
DECLARE @g6 geometry = 'POLYGON((1 1, 1 1, 1 1, 1 1))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(), @g4.STIsValid(), @g5.STIsValid(), @g6.STIsValid();
```

 <span data-ttu-id="d17f6-138">`@g1` não é válido porque o anel interno toca o anel exterior em dois locais.</span><span class="sxs-lookup"><span data-stu-id="d17f6-138">`@g1` is not valid because the inner ring touches the exterior ring in two places.</span></span> <span data-ttu-id="d17f6-139">`@g2` não é válido porque o segundo anel interno está no interior do primeiro anel interno.</span><span class="sxs-lookup"><span data-stu-id="d17f6-139">`@g2` is not valid because the second inner ring in within the interior of the first inner ring.</span></span> <span data-ttu-id="d17f6-140">`@g3` não é válido porque os dois anéis internos tocam-se em vários pontos sucessivos.</span><span class="sxs-lookup"><span data-stu-id="d17f6-140">`@g3` is not valid because the two inner rings touch at multiple consecutive points.</span></span> <span data-ttu-id="d17f6-141">`@g4` não é válido porque os interiores dos dois anéis internos estão sobrepostos.</span><span class="sxs-lookup"><span data-stu-id="d17f6-141">`@g4` is not valid because the interiors of the two inner rings overlap.</span></span> <span data-ttu-id="d17f6-142">`@g5` não é válido porque o anel exterior não é o primeiro anel.</span><span class="sxs-lookup"><span data-stu-id="d17f6-142">`@g5` is not valid because the exterior ring is not the first ring.</span></span> <span data-ttu-id="d17f6-143">`@g6` não é válido porque o anel não tem três pontos distintos pelo menos.</span><span class="sxs-lookup"><span data-stu-id="d17f6-143">`@g6` is not valid because the ring does not have at least three distinct points.</span></span>

## <a name="examples"></a><span data-ttu-id="d17f6-144">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d17f6-144">Examples</span></span>
 <span data-ttu-id="d17f6-145">O exemplo a seguir cria uma instância de `geometry``Polygon` simples com um espaço e SRID 10.</span><span class="sxs-lookup"><span data-stu-id="d17f6-145">The following example creates a simple `geometry``Polygon` instance with a hole and SRID 10.</span></span>

```
DECLARE @g geometry;
SET @g = geometry::STPolyFromText('POLYGON((0 0, 0 3, 3 3, 3 0, 0 0), (1 1, 1 2, 2 1, 1 1))', 10);
```

 <span data-ttu-id="d17f6-146">Uma instância que não é válida pode ser inserida e convertida em uma instância `geometry` válida.</span><span class="sxs-lookup"><span data-stu-id="d17f6-146">Aninstance that is not valid may be entered and converted to a valid `geometry` instance.</span></span> <span data-ttu-id="d17f6-147">No exemplo seguinte de um `Polygon`, os anéis interiores e exteriores se sobrepõem e a instância não é válida.</span><span class="sxs-lookup"><span data-stu-id="d17f6-147">In the following example of a `Polygon`, the interior and exterior rings overlap and the instance is not valid.</span></span>

```
DECLARE @g geometry;
SET @g = geometry::Parse('POLYGON((1 0, 0 1, 1 2, 2 1, 1 0), (2 0, 1 1, 2 2, 3 1, 2 0))');
```

 <span data-ttu-id="d17f6-148">No exemplo a seguir, a instância inválida é tornada válida com `MakeValid()`.</span><span class="sxs-lookup"><span data-stu-id="d17f6-148">In the following example, the invalid instance is made valid with `MakeValid()`.</span></span>

```
SET @g = @g.MakeValid();
SELECT @g.ToString();
```

 <span data-ttu-id="d17f6-149">A instância de `geometry` retornada do exemplo acima é um `MultiPolygon`.</span><span class="sxs-lookup"><span data-stu-id="d17f6-149">The `geometry` instance returned from the above example is a `MultiPolygon`.</span></span>

```
MULTIPOLYGON (((2 0, 3 1, 2 2, 1.5 1.5, 2 1, 1.5 0.5, 2 0)), ((1 0, 1.5 0.5, 1 1, 1.5 1.5, 1 2, 0 1, 1 0)))
```

 <span data-ttu-id="d17f6-150">Este é outro exemplo de conversão de uma instância inválida em uma instância de geometry válida.</span><span class="sxs-lookup"><span data-stu-id="d17f6-150">Here is another example of converting an invalid instance to a valid geometry instance.</span></span> <span data-ttu-id="d17f6-151">No exemplo a seguir, a instância `Polygon` foi criada usando três pontos que são exatamente iguais:</span><span class="sxs-lookup"><span data-stu-id="d17f6-151">In the following example the `Polygon` instance has been created using three points that are exactly the same:</span></span>

```sql
DECLARE @g geometry
SET @g = geometry::Parse('POLYGON((1 3, 1 3, 1 3, 1 3))');
SET @g = @g.MakeValid();
SELECT @g.ToString()
```

 <span data-ttu-id="d17f6-152">A instância de geometry retornada acima é um `Point(1 3)`.</span><span class="sxs-lookup"><span data-stu-id="d17f6-152">The geometry instance returned above is a `Point(1 3)`.</span></span>  <span data-ttu-id="d17f6-153">Se o `Polygon` fornecido for `POLYGON((1 3, 1 5, 1 3, 1 3))` , `MakeValid()` retornaria `LINESTRING(1 3, 1 5)`.</span><span class="sxs-lookup"><span data-stu-id="d17f6-153">If the `Polygon` given is `POLYGON((1 3, 1 5, 1 3, 1 3))` then `MakeValid()` would return `LINESTRING(1 3, 1 5)`.</span></span>

## <a name="see-also"></a><span data-ttu-id="d17f6-154">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d17f6-154">See Also</span></span>
 <span data-ttu-id="d17f6-155">[A área de &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/starea-geometry-data-type) [STExteriorRing &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/stexteriorring-geometry-data-type) [STNumInteriorRing &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/stnuminteriorring-geometry-data-type) [STInteriorRingN &#40;](/sql/t-sql/spatial-geometry/stinteriorringn-geometry-data-type) tipo de dados geometry&#41;o &#40;[do tipo de](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type) dados geometry&#41;o tipo de dados geometry &#40;[STPointOnSurface](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type)&#41;[o tipo de](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type) dados [espaciaI](../spatial/spatial-data-sql-server.md) &#40;[MultiPolygon](../spatial/polygon.md) SQL Server o tipo de [dados geography](/sql/t-sql/spatial-geography/stisvalid-geography-data-type)&#41;</span><span class="sxs-lookup"><span data-stu-id="d17f6-155">[STArea &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/starea-geometry-data-type) [STExteriorRing &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stexteriorring-geometry-data-type) [STNumInteriorRing &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stnuminteriorring-geometry-data-type) [STInteriorRingN &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stinteriorringn-geometry-data-type) [STCentroid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type) [STPointOnSurface &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [MultiPolygon](../spatial/polygon.md) [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) [STIsValid &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stisvalid-geography-data-type) [STIsValid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type)</span></span>


