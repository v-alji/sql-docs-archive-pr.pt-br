---
title: CircularString | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 9fe06b03-d98c-4337-9f89-54da98f49f9f
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: c701cdc2e8538a5b91093e17714fd9f6508d1c4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569867"
---
# <a name="circularstring"></a><span data-ttu-id="1a6c7-102">CircularString</span><span class="sxs-lookup"><span data-stu-id="1a6c7-102">CircularString</span></span>
  <span data-ttu-id="1a6c7-103">Um `CircularString` é uma coleção de zero ou mais segmentos de arco circulares contínuos.</span><span class="sxs-lookup"><span data-stu-id="1a6c7-103">A `CircularString` is a collection of zero or more continuous circular arc segments.</span></span> <span data-ttu-id="1a6c7-104">Um segmento de arco circular é um segmento curvado definido por três pontos em um plano bidimensional; o primeiro ponto não pode ser igual ao terceiro ponto.</span><span class="sxs-lookup"><span data-stu-id="1a6c7-104">A circular arc segment is a curved segment defined by three points in a two-dimensional plane; the first point cannot be the same as the third point.</span></span> <span data-ttu-id="1a6c7-105">Se todos os três pontos de um segmento de arco circular forem colineares, o segmento de arco será tratado como um segmento de linha.</span><span class="sxs-lookup"><span data-stu-id="1a6c7-105">If all three points of a circular arc segment are collinear, the arc segment is treated as a line segment.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="1a6c7-106">Para obter uma descrição detalhada e exemplos dos novos recursos espaciais introduzidos no [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , incluindo o `CircularString` subtipo, baixe o White Paper, [novos recursos espaciais no SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span><span class="sxs-lookup"><span data-stu-id="1a6c7-106">For a detailed description and examples of the new spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], including the `CircularString` subtype, download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>

## <a name="circularstring-instances"></a><span data-ttu-id="1a6c7-107">Instâncias CircularString</span><span class="sxs-lookup"><span data-stu-id="1a6c7-107">CircularString instances</span></span>
 <span data-ttu-id="1a6c7-108">O desenho seguinte mostra instâncias `CircularString` válidas:</span><span class="sxs-lookup"><span data-stu-id="1a6c7-108">The drawing below shows valid `CircularString` instances:</span></span>

 ![](../../database-engine/media/5ff17e34-b578-4873-9d33-79500940d0bc.png "5ff17e34-b578-4873-9d33-79500940d0bc")

### <a name="accepted-instances"></a><span data-ttu-id="1a6c7-109">Instâncias aceitas</span><span class="sxs-lookup"><span data-stu-id="1a6c7-109">Accepted instances</span></span>
 <span data-ttu-id="1a6c7-110">Uma `CircularString` instância será aceita se estiver vazia ou contiver um número ímpar de pontos, n, em que n > 1.</span><span class="sxs-lookup"><span data-stu-id="1a6c7-110">A `CircularString` instance is accepted if it is either empty or contains an odd number of points, n, where n > 1.</span></span> <span data-ttu-id="1a6c7-111">As instâncias `CircularString` a seguir são aceitas.</span><span class="sxs-lookup"><span data-stu-id="1a6c7-111">The following `CircularString` instances are accepted.</span></span>

```sql
DECLARE @g1 geometry = 'CIRCULARSTRING EMPTY';
DECLARE @g2 geometry = 'CIRCULARSTRING(1 1, 2 0, -1 1)';
DECLARE @g3 geometry = 'CIRCULARSTRING(1 1, 2 0, 2 0, 2 0, 1 1)';
```

 <span data-ttu-id="1a6c7-112">`@g3`mostra que a `CircularString` instância pode ser aceita, mas não válida.</span><span class="sxs-lookup"><span data-stu-id="1a6c7-112">`@g3` shows that `CircularString` instance may be accepted, but not valid.</span></span> <span data-ttu-id="1a6c7-113">A declaração da instância CircularString a seguir não é aceita.</span><span class="sxs-lookup"><span data-stu-id="1a6c7-113">The following CircularString instance declaration is not accepted.</span></span> <span data-ttu-id="1a6c7-114">Esta declaração lança uma `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="1a6c7-114">This declaration throws a `System.FormatException`.</span></span>

```sql
DECLARE @g geometry = 'CIRCULARSTRING(1 1, 2 0, 2 0, 1 1)';
```

### <a name="valid-instances"></a><span data-ttu-id="1a6c7-115">Instâncias válidas</span><span class="sxs-lookup"><span data-stu-id="1a6c7-115">Valid instances</span></span>
 <span data-ttu-id="1a6c7-116">Uma instância `CircularString` válida deve estar vazia ou ter os seguintes atributos:</span><span class="sxs-lookup"><span data-stu-id="1a6c7-116">A valid `CircularString` instance must be empty or have the following attributes:</span></span>

-   <span data-ttu-id="1a6c7-117">Deve conter, pelo menos, um segmento de arco circular (ou seja, que tenha um mínimo de três pontos).</span><span class="sxs-lookup"><span data-stu-id="1a6c7-117">It must contain at least one circular arc segment (that is, have a minimum of three points).</span></span>

-   <span data-ttu-id="1a6c7-118">O último ponto de extremidade para cada segmento de arco circular na sequência, com exceção do último segmento, deve ser o primeiro ponto de extremidade para o próximo segmento na sequência.</span><span class="sxs-lookup"><span data-stu-id="1a6c7-118">The last endpoint for each circular arc segment in the sequence, except for the last segment, must be the first endpoint for the next segment in the sequence.</span></span>

-   <span data-ttu-id="1a6c7-119">Deve ter um número ímpar de pontos.</span><span class="sxs-lookup"><span data-stu-id="1a6c7-119">It must have an odd number of points.</span></span>

-   <span data-ttu-id="1a6c7-120">Não pode se sobrepor a um intervalo.</span><span class="sxs-lookup"><span data-stu-id="1a6c7-120">It cannot overlap itself over an interval.</span></span>

-   <span data-ttu-id="1a6c7-121">Embora instâncias `CircularString` possam conter segmentos de linha, esses segmentos devem ser definidos por três pontos colineares.</span><span class="sxs-lookup"><span data-stu-id="1a6c7-121">Although `CircularString` instances may contain line segments, these line segments must be defined by three collinear points.</span></span>

 <span data-ttu-id="1a6c7-122">O exemplo a seguir mostra instâncias `CircularString` válidas.</span><span class="sxs-lookup"><span data-stu-id="1a6c7-122">The following example shows valid `CircularString` instances.</span></span>

```sql
DECLARE @g1 geometry = 'CIRCULARSTRING EMPTY';
DECLARE @g2 geometry = 'CIRCULARSTRING(1 1, 2 0, -1 1)';
DECLARE @g3 geometry = 'CIRCULARSTRING(1 1, 2 0, 2 0, 1 1, 0 1)';
DECLARE @g4 geometry = 'CIRCULARSTRING(1 1, 2 2, 2 2)';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(),@g4.STIsValid();
```

 <span data-ttu-id="1a6c7-123">Uma instância `CircularString` deve conter, pelo menos, dois segmentos de arco circulares para definir um círculo completo.</span><span class="sxs-lookup"><span data-stu-id="1a6c7-123">A `CircularString` instance must contain at least two circular arc segments to define a complete circle.</span></span> <span data-ttu-id="1a6c7-124">Uma instância `CircularString` não pode usar um único segmento de arco circular (como (1 1, 3 1, 1 1)) para definir um círculo completo.</span><span class="sxs-lookup"><span data-stu-id="1a6c7-124">A `CircularString` instance cannot use a single circular arc segment (such as (1 1, 3 1, 1 1)) to define a complete circle.</span></span> <span data-ttu-id="1a6c7-125">Use (1 1, 2 2, 3 1, 2 0, 1 1) para definir o círculo.</span><span class="sxs-lookup"><span data-stu-id="1a6c7-125">Use (1 1, 2 2, 3 1, 2 0, 1 1) to define the circle.</span></span>

 <span data-ttu-id="1a6c7-126">O exemplo a seguir mostra instâncias CircularString que não são válidas.</span><span class="sxs-lookup"><span data-stu-id="1a6c7-126">The following example shows CircularString instances that are not valid.</span></span>

```sql
DECLARE @g1 geometry = 'CIRCULARSTRING(1 1, 2 0, 1 1)';
DECLARE @g2 geometry = 'CIRCULARSTRING(0 0, 0 0, 0 0)';
SELECT @g1.STIsValid(), @g2.STIsValid();
```

### <a name="instances-with-collinear-points"></a><span data-ttu-id="1a6c7-127">Instâncias com pontos colineares</span><span class="sxs-lookup"><span data-stu-id="1a6c7-127">Instances with collinear points</span></span>
 <span data-ttu-id="1a6c7-128">Nos casos a seguir, um segmento de arco circular será tratado como um segmento de linha:</span><span class="sxs-lookup"><span data-stu-id="1a6c7-128">In the following cases a circular arc segment will be treated as a line segment:</span></span>

-   <span data-ttu-id="1a6c7-129">Quando todos os três pontos são colineares (por exemplo, (1 3, 4 4, 7 5)).</span><span class="sxs-lookup"><span data-stu-id="1a6c7-129">When all three points are collinear (for example, (1 3, 4 4, 7 5)).</span></span>

-   <span data-ttu-id="1a6c7-130">Quando o primeiro ponto e o ponto mediano são os mesmos, mas o terceiro ponto é diferente (por exemplo, (1 3, 1 3, 7 5)).</span><span class="sxs-lookup"><span data-stu-id="1a6c7-130">When the first and middle point are the same, but the third point is different (for example, (1 3, 1 3, 7 5)).</span></span>

-   <span data-ttu-id="1a6c7-131">Quando o primeiro e o último pontos são os mesmos, mas o primeiro ponto é diferente (por exemplo, (1 3, 4 4, 4 4)).</span><span class="sxs-lookup"><span data-stu-id="1a6c7-131">When the middle and last point are the same, but the first point is different (for example, (1 3, 4 4, 4 4)).</span></span>

## <a name="examples"></a><span data-ttu-id="1a6c7-132">Exemplos</span><span class="sxs-lookup"><span data-stu-id="1a6c7-132">Examples</span></span>

### <a name="a-instantiating-a-geometry-instance-with-an-empty-circularstring"></a><span data-ttu-id="1a6c7-133">a.</span><span class="sxs-lookup"><span data-stu-id="1a6c7-133">A.</span></span> <span data-ttu-id="1a6c7-134">Criando uma instância de geometry com uma CircularString vazia</span><span class="sxs-lookup"><span data-stu-id="1a6c7-134">Instantiating a Geometry Instance with an Empty CircularString</span></span>
 <span data-ttu-id="1a6c7-135">Esse exemplo mostra como criar uma instância `CircularString` vazia:</span><span class="sxs-lookup"><span data-stu-id="1a6c7-135">This example shows how to create an empty `CircularString` instance:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('CIRCULARSTRING EMPTY');
```

### <a name="b-instantiating-a-geometry-instance-using-a-circularstring-with-one-circular-arc-segment"></a><span data-ttu-id="1a6c7-136">B.</span><span class="sxs-lookup"><span data-stu-id="1a6c7-136">B.</span></span> <span data-ttu-id="1a6c7-137">Criando uma instância de geometry usando uma CircularString com um segmento de arco circular</span><span class="sxs-lookup"><span data-stu-id="1a6c7-137">Instantiating a Geometry Instance Using a CircularString with One Circular Arc Segment</span></span>
 <span data-ttu-id="1a6c7-138">O exemplo a seguir mostra como criar uma instância `CircularString` com um único segmento de arco circular (meio-círculo):</span><span class="sxs-lookup"><span data-stu-id="1a6c7-138">The following example shows how to create a `CircularString` instance with a single circular arc segment (half-circle):</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry:: STGeomFromText('CIRCULARSTRING(2 0, 1 1, 0 0)', 0);
SELECT @g.ToString();
```

### <a name="c-instantiating-a-geometry-instance-using-a-circularstring-with-multiple-circular-arc-segments"></a><span data-ttu-id="1a6c7-139">C.</span><span class="sxs-lookup"><span data-stu-id="1a6c7-139">C.</span></span> <span data-ttu-id="1a6c7-140">Criando uma instância de geometry usando uma CircularString com vários segmentos de arco circular</span><span class="sxs-lookup"><span data-stu-id="1a6c7-140">Instantiating a Geometry Instance Using a CircularString with Multiple Circular Arc Segments</span></span>
 <span data-ttu-id="1a6c7-141">O exemplo a seguir mostra como criar uma instância `CircularString` com mais de um segmento de arco circular (círculo cheio):</span><span class="sxs-lookup"><span data-stu-id="1a6c7-141">The following example shows how to create a `CircularString` instance with more than one circular arc segment (full circle):</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('CIRCULARSTRING(2 1, 1 2, 0 1, 1 0, 2 1)');
SELECT 'Circumference = ' + CAST(@g.STLength() AS NVARCHAR(10));  
```

 <span data-ttu-id="1a6c7-142">Isso gera a saída a seguir:</span><span class="sxs-lookup"><span data-stu-id="1a6c7-142">This produces the following output:</span></span>

```
Circumference = 6.28319
```

 <span data-ttu-id="1a6c7-143">Compare a saída quando `LineString` é usada em vez de `CircularString`:</span><span class="sxs-lookup"><span data-stu-id="1a6c7-143">Compare the output when `LineString` is used instead of `CircularString`:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::STGeomFromText('LINESTRING(2 1, 1 2, 0 1, 1 0, 2 1)', 0);
SELECT 'Perimeter = ' + CAST(@g.STLength() AS NVARCHAR(10));
```

 <span data-ttu-id="1a6c7-144">Isso gera a saída a seguir:</span><span class="sxs-lookup"><span data-stu-id="1a6c7-144">This produces the following output:</span></span>

```
Perimeter = 5.65685
```

 <span data-ttu-id="1a6c7-145">Observe que o valor do `CircularString` exemplo é próximo a 2&#x03c0; (2 \* PI), que é a circunferência real do círculo.</span><span class="sxs-lookup"><span data-stu-id="1a6c7-145">Notice that the value for the `CircularString` example is close to 2&#x03c0; (2 \* pi), which is the actual circumference of the circle.</span></span>

### <a name="d-declaring-and-instantiating-a-geometry-instance-with-a-circularstring-in-the-same-statement"></a><span data-ttu-id="1a6c7-146">D.</span><span class="sxs-lookup"><span data-stu-id="1a6c7-146">D.</span></span> <span data-ttu-id="1a6c7-147">Declarando e criando uma instância de geometry com uma CircularString na mesma instrução</span><span class="sxs-lookup"><span data-stu-id="1a6c7-147">Declaring and Instantiating a Geometry Instance with a CircularString in the Same Statement</span></span>
 <span data-ttu-id="1a6c7-148">Este snippet mostra como declarar e criar uma instância de `geometry` com uma `CircularString` na mesma instrução:</span><span class="sxs-lookup"><span data-stu-id="1a6c7-148">This snippet shows how to declare and instantiate a `geometry` instance with a `CircularString` in the same statement:</span></span>

```sql
DECLARE @g geometry = 'CIRCULARSTRING(0 0, 1 2.1082, 3 6.3246, 0 7, -3 6.3246, -1 2.1082, 0 0)';
```

### <a name="e-instantiating-a-geography-instance-with-a-circularstring"></a><span data-ttu-id="1a6c7-149">E.</span><span class="sxs-lookup"><span data-stu-id="1a6c7-149">E.</span></span> <span data-ttu-id="1a6c7-150">Criando uma instância de geography com uma CircularString</span><span class="sxs-lookup"><span data-stu-id="1a6c7-150">Instantiating a Geography Instance with a CircularString</span></span>
 <span data-ttu-id="1a6c7-151">O exemplo a seguir mostra como declarar e criar uma instância de `geography` com uma `CircularString`:</span><span class="sxs-lookup"><span data-stu-id="1a6c7-151">The following example shows how to declare and instantiate a `geography` instance with a `CircularString`:</span></span>

```sql
DECLARE @g geography = 'CIRCULARSTRING(-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653)';
```

### <a name="f-instantiating-a-geometry-instance-with-a-circularstring-that-is-a-straight-line"></a><span data-ttu-id="1a6c7-152">F.</span><span class="sxs-lookup"><span data-stu-id="1a6c7-152">F.</span></span> <span data-ttu-id="1a6c7-153">Criando uma instância de geometry com uma CircularString que é uma linha reta</span><span class="sxs-lookup"><span data-stu-id="1a6c7-153">Instantiating a Geometry Instance with a CircularString that is a Straight Line</span></span>
 <span data-ttu-id="1a6c7-154">O exemplo a seguir mostra como criar uma instância `CircularString` que é uma linha reta:</span><span class="sxs-lookup"><span data-stu-id="1a6c7-154">The following example shows how to create a `CircularString` instance that is a straight line:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::STGeomFromText('CIRCULARSTRING(0 0, 1 2, 2 4)', 0);
```

## <a name="see-also"></a><span data-ttu-id="1a6c7-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1a6c7-155">See Also</span></span>
 <span data-ttu-id="1a6c7-156">[Tipos de dados espaciais visão geral](spatial-data-types-overview.md) [CompoundCurve](compoundcurve.md) [MakeValid &#40;tipo de dados geography&#41;](/sql/t-sql/spatial-geography/makevalid-geography-data-type) [MakeValid &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/makevalid-geometry-data-type) [Inisvalid &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type) [inisvalid &#40;tipo de dados geography&#41;](/sql/t-sql/spatial-geography/stisvalid-geography-data-type) tamanho &#40;tipo de [dados geometry](/sql/t-sql/spatial-geometry/stlength-geometry-data-type)&#41;tipo de dados geometry &#40;[&#41;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) [ponto de extremidade &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) o tipo de dados [Geometry &#40;&#41;](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type) [STNumPoints &#40;tipo](/sql/t-sql/spatial-geometry/stnumpoints-geometry-data-type) de dados geometry&#41;[STIsRing &#40;](/sql/t-sql/spatial-geometry/stisring-geometry-data-type) tipo de dados geometry&#41;[STIsClosed &#40;tipo de dados geometry](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type)&#41;[STPointOnSurface &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [LineString](linestring.md)</span><span class="sxs-lookup"><span data-stu-id="1a6c7-156">[Spatial Data Types Overview](spatial-data-types-overview.md) [CompoundCurve](compoundcurve.md) [MakeValid &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/makevalid-geography-data-type) [MakeValid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/makevalid-geometry-data-type) [STIsValid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type) [STIsValid &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stisvalid-geography-data-type) [STLength &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) [STStartPoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) [STEndpoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) [STPointN &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type) [STNumPoints &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stnumpoints-geometry-data-type) [STIsRing &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisring-geometry-data-type) [STIsClosed &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) [STPointOnSurface &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [LineString](linestring.md)</span></span>


