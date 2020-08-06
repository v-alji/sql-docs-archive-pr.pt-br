---
title: MultiPolygon | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- MultiPolygon geometry subtype [SQL Server]
- geometry subtypes [SQL Server]
ms.assetid: 2c5db358-2a16-49d9-aac5-a74e86813932
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: f18fd2485c9b2e62586d9f3e81f76f6cf680dbfc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582908"
---
# <a name="multipolygon"></a><span data-ttu-id="73923-102">MultiPolygon</span><span class="sxs-lookup"><span data-stu-id="73923-102">MultiPolygon</span></span>
  <span data-ttu-id="73923-103">Uma instância `MultiPolygon` é uma coleção de zero ou mais instâncias `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="73923-103">A `MultiPolygon` instance is a collection of zero or more `Polygon` instances.</span></span>

## <a name="polygon-instances"></a><span data-ttu-id="73923-104">Instâncias de polígono</span><span class="sxs-lookup"><span data-stu-id="73923-104">Polygon Instances</span></span>
 <span data-ttu-id="73923-105">A ilustração a seguir mostra exemplos de instâncias `MultiPolygon`.</span><span class="sxs-lookup"><span data-stu-id="73923-105">The illustration below shows examples of `MultiPolygon` instances.</span></span>

 <span data-ttu-id="73923-106">![Exemplos das instâncias geométricas MultiPolygon](../../database-engine/media/multipolygon.gif "Exemplos das instâncias geométricas MultiPolygon")</span><span class="sxs-lookup"><span data-stu-id="73923-106">![Examples of geometry MultiPolygon instances](../../database-engine/media/multipolygon.gif "Examples of geometry MultiPolygon instances")</span></span>

 <span data-ttu-id="73923-107">Conforme mostrado na ilustração:</span><span class="sxs-lookup"><span data-stu-id="73923-107">As shown in the illustration:</span></span>

-   <span data-ttu-id="73923-108">A Figura 1 é uma instância `MultiPolygon` com dois elementos `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="73923-108">Figure 1 is a `MultiPolygon` instance with two `Polygon` elements.</span></span> <span data-ttu-id="73923-109">O limite é definido pelos dois anéis exteriores e os três anéis interiores.</span><span class="sxs-lookup"><span data-stu-id="73923-109">The boundary is defined by the two exterior rings and the three interior rings.</span></span>

-   <span data-ttu-id="73923-110">A Figura 2 é uma instância `MultiPolygon` com dois elementos `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="73923-110">Figure 2 is a `MultiPolygon` instance with two `Polygon` elements.</span></span> <span data-ttu-id="73923-111">O limite é definido pelos dois anéis exteriores e os três anéis interiores.</span><span class="sxs-lookup"><span data-stu-id="73923-111">The boundary is defined by the two exterior rings and the three interior rings.</span></span> <span data-ttu-id="73923-112">Os dois elementos `Polygon` cruzam em um ponto de tangente.</span><span class="sxs-lookup"><span data-stu-id="73923-112">The two `Polygon` elements intersect at a tangent point.</span></span>

### <a name="accepted-instances"></a><span data-ttu-id="73923-113">Instâncias aceitas</span><span class="sxs-lookup"><span data-stu-id="73923-113">Accepted Instances</span></span>
 <span data-ttu-id="73923-114">Uma instância de `MultiPolygon` é aceita quando uma das condições a seguir é atendida.</span><span class="sxs-lookup"><span data-stu-id="73923-114">A `MultiPolygon` instance is accepted one of the following conditions is met.</span></span>

-   <span data-ttu-id="73923-115">É uma instância de `MultiPolygon` vazia.</span><span class="sxs-lookup"><span data-stu-id="73923-115">It is an empty `MultiPolygon` instance.</span></span>

-   <span data-ttu-id="73923-116">Todas as instâncias que englobam a instância de `MultiPolygon` são instâncias de `Polygon` aceitas.</span><span class="sxs-lookup"><span data-stu-id="73923-116">All instances comprising the `MultiPolygon` instance are accepted `Polygon` instances.</span></span> <span data-ttu-id="73923-117">Para obter mais informações sobre `Polygon` instâncias aceitas, consulte [Polygon](../spatial/polygon.md).</span><span class="sxs-lookup"><span data-stu-id="73923-117">For more information on accepted `Polygon` instances, see [Polygon](../spatial/polygon.md).</span></span>

 <span data-ttu-id="73923-118">Os exemplos a seguir mostram as instâncias de `MultiPolygon` aceitas.</span><span class="sxs-lookup"><span data-stu-id="73923-118">The following examples show accepted `MultiPolygon` instances.</span></span>

```
DECLARE @g1 geometry = 'MULTIPOLYGON EMPTY';
DECLARE @g2 geometry = 'MULTIPOLYGON(((1 1, 1 -1, -1 -1, -1 1, 1 1)),((1 1, 3 1, 3 3, 1 3, 1 1)))';
DECLARE @g3 geometry = 'MULTIPOLYGON(((2 2, 2 -2, -2 -2, -2 2, 2 2)),((1 1, 3 1, 3 3, 1 3, 1 1)))';
```

 <span data-ttu-id="73923-119">O exemplo a seguir mostra uma instância de MultiPolygon que emitirá um `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="73923-119">The following example shows a MultiPolygon instance that will throw a `System.FormatException`.</span></span>

```
DECLARE @g geometry = 'MULTIPOLYGON(((1 1, 1 -1, -1 -1, -1 1, 1 1)),((1 1, 3 1, 3 3)))';
```

 <span data-ttu-id="73923-120">A segunda instância no MultiPolygon é uma instância de LineString e não uma instância de Polygon aceita.</span><span class="sxs-lookup"><span data-stu-id="73923-120">The second instance in the MultiPolygon is a LineString instance and not an accepted Polygon instance.</span></span>

### <a name="valid-instances"></a><span data-ttu-id="73923-121">Instâncias válidas</span><span class="sxs-lookup"><span data-stu-id="73923-121">Valid Instances</span></span>
 <span data-ttu-id="73923-122">Uma instância de `MultiPolygon` será válida se for uma instância de `MultiPolygon` vazia ou se atender aos critérios a seguir.</span><span class="sxs-lookup"><span data-stu-id="73923-122">A `MultiPolygon` instance is valid if it is an empty `MultiPolygon` instance or if it meets the following criteria.</span></span>

1.  <span data-ttu-id="73923-123">Todas as instâncias que englobam a instância de `MultiPolygon` são instâncias de `Polygon` válidas.</span><span class="sxs-lookup"><span data-stu-id="73923-123">All of the instances comprising the `MultiPolygon` instance are valid `Polygon` instances.</span></span> <span data-ttu-id="73923-124">Para instâncias válidas `Polygon` , consulte [Polygon](../spatial/polygon.md).</span><span class="sxs-lookup"><span data-stu-id="73923-124">For valid `Polygon` instances, see [Polygon](../spatial/polygon.md).</span></span>

2.  <span data-ttu-id="73923-125">Nenhuma das instâncias de `Polygon` que englobe a instância de `MultiPolygon` se sobreporá.</span><span class="sxs-lookup"><span data-stu-id="73923-125">None of the `Polygon` instances comprising the `MultiPolygon` instance overlap.</span></span>

 <span data-ttu-id="73923-126">O exemplo a seguir mostra duas instâncias de `MultiPolygon` válidas e uma instância de `MultiPolygon` inválida.</span><span class="sxs-lookup"><span data-stu-id="73923-126">The following example shows two valid `MultiPolygon` instances and one invalid `MultiPolygon` instance.</span></span>

```
DECLARE @g1 geometry = 'MULTIPOLYGON EMPTY';
DECLARE @g2 geometry = 'MULTIPOLYGON(((1 1, 1 -1, -1 -1, -1 1, 1 1)),((1 1, 3 1, 3 3, 1 3, 1 1)))';
DECLARE @g3 geometry = 'MULTIPOLYGON(((2 2, 2 -2, -2 -2, -2 2, 2 2)),((1 1, 3 1, 3 3, 1 3, 1 1)))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid();
```

 <span data-ttu-id="73923-127">`@g2` é válido porque as duas instâncias `Polygon` tocam somente um ponto tangente.</span><span class="sxs-lookup"><span data-stu-id="73923-127">`@g2` is valid because the two `Polygon` instances touch only at a tangent point.</span></span> <span data-ttu-id="73923-128">`@g3` não é válido porque os interiores das duas instâncias `Polygon` sobrepõem-se.</span><span class="sxs-lookup"><span data-stu-id="73923-128">`@g3` is not valid because the interiors of the two `Polygon` instances overlap each other.</span></span>

## <a name="examples"></a><span data-ttu-id="73923-129">Exemplos</span><span class="sxs-lookup"><span data-stu-id="73923-129">Examples</span></span>
 <span data-ttu-id="73923-130">O exemplo a seguir mostra a criação de uma instância de `geometry``MultiPolygon` e retorna o WKT (Well-Known Text) do segundo componente.</span><span class="sxs-lookup"><span data-stu-id="73923-130">The following example shows the creation of a `geometry``MultiPolygon` instance and returns the Well-Known Text (WKT) of the second component.</span></span>

```
DECLARE @g geometry;
SET @g = geometry::Parse('MULTIPOLYGON(((0 0, 0 3, 3 3, 3 0, 0 0), (1 1, 1 2, 2 1, 1 1)), ((9 9, 9 10, 10 9, 9 9)))');
SELECT @g.STGeometryN(2).STAsText();
```

 <span data-ttu-id="73923-131">Este exemplo cria uma instância `MultiPolygon` vazia.</span><span class="sxs-lookup"><span data-stu-id="73923-131">This example instantiates an empty `MultiPolygon` instance.</span></span>

```
DECLARE @g geometry;
SET @g = geometry::Parse('MULTIPOLYGON EMPTY');
```

## <a name="see-also"></a><span data-ttu-id="73923-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="73923-132">See Also</span></span>
 <span data-ttu-id="73923-133">Área de &#40;do [polígono](../spatial/polygon.md) [tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/starea-geometry-data-type) o tipo de dados [geometry &#40;geometria&#41;](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type) [STPointOnSurface &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [dados espaciais &#40;SQL Server](../spatial/spatial-data-sql-server.md)&#41;</span><span class="sxs-lookup"><span data-stu-id="73923-133">[Polygon](../spatial/polygon.md) [STArea &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/starea-geometry-data-type) [STCentroid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type) [STPointOnSurface &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md)</span></span>


