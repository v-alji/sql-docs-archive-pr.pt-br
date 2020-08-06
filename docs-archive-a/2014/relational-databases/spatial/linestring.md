---
title: LineString | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- LineString geometry subtype [SQL Server]
- geometry subtypes [SQL Server]
ms.assetid: e50d0b86-8b31-4285-be71-ad05c7712cbd
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 5a0f77959cfe4492eca6c38951ba2868452d41ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582920"
---
# <a name="linestring"></a><span data-ttu-id="6b318-102">LineString</span><span class="sxs-lookup"><span data-stu-id="6b318-102">LineString</span></span>
  <span data-ttu-id="6b318-103">Um `LineString` é um objeto unidimensional que representa uma sequência de pontos e os segmentos de linha que os conectam.</span><span class="sxs-lookup"><span data-stu-id="6b318-103">A `LineString` is a one-dimensional object representing a sequence of points and the line segments connecting them.</span></span>

## <a name="linestring-instances"></a><span data-ttu-id="6b318-104">Instâncias LineString</span><span class="sxs-lookup"><span data-stu-id="6b318-104">LineString Instances</span></span>
 <span data-ttu-id="6b318-105">A ilustração a seguir mostra exemplos de instâncias `LineString`.</span><span class="sxs-lookup"><span data-stu-id="6b318-105">The illustration below shows examples of `LineString` instances.</span></span>

 <span data-ttu-id="6b318-106">![Exemplos de instâncias LineString de geometria](../../database-engine/media/linestring.gif "Exemplos de instâncias LineString de geometria")</span><span class="sxs-lookup"><span data-stu-id="6b318-106">![Examples of geometry LineString instances](../../database-engine/media/linestring.gif "Examples of geometry LineString instances")</span></span>

 <span data-ttu-id="6b318-107">Conforme mostrado na ilustração:</span><span class="sxs-lookup"><span data-stu-id="6b318-107">As shown in the illustration:</span></span>

-   <span data-ttu-id="6b318-108">A Figura 1 é uma instância `LineString` simples, não fechada.</span><span class="sxs-lookup"><span data-stu-id="6b318-108">Figure 1 is a simple, nonclosed `LineString` instance.</span></span>

-   <span data-ttu-id="6b318-109">A Figura 2 é uma instância `LineString` não simples, não fechada.</span><span class="sxs-lookup"><span data-stu-id="6b318-109">Figure 2 is a nonsimple, nonclosed `LineString` instance.</span></span>

-   <span data-ttu-id="6b318-110">A Figura 3 é uma instância `LineString` fechada, simples e portanto é um anel.</span><span class="sxs-lookup"><span data-stu-id="6b318-110">Figure 3 is a closed, simple `LineString` instance, and therefore is a ring.</span></span>

-   <span data-ttu-id="6b318-111">A Figura 4 é uma instância `LineString` fechada, não simples e, por isso, não é um anel.</span><span class="sxs-lookup"><span data-stu-id="6b318-111">Figure 4 is a closed, nonsimple `LineString` instance, and therefore is not a ring.</span></span>

### <a name="accepted-instances"></a><span data-ttu-id="6b318-112">Instâncias aceitas</span><span class="sxs-lookup"><span data-stu-id="6b318-112">Accepted Instances</span></span>
 <span data-ttu-id="6b318-113">As instâncias `LineString` aceitas podem ser inseridas em uma variável geometry, mas talvez não sejam instâncias `LineString` válidas.</span><span class="sxs-lookup"><span data-stu-id="6b318-113">Accepted `LineString` instances can be input into a geometry variable, but they may not be valid `LineString` instances.</span></span> <span data-ttu-id="6b318-114">Os seguintes critérios devem ser atendidos para que uma instância `LineString` seja aceita.</span><span class="sxs-lookup"><span data-stu-id="6b318-114">The following criteria must be met for a `LineString` instance to be accepted.</span></span> <span data-ttu-id="6b318-115">A instância deve ser formada por pelo menos dois pontos ou deve estar vazia.</span><span class="sxs-lookup"><span data-stu-id="6b318-115">The instance must be formed of at least two points or it must be empty.</span></span> <span data-ttu-id="6b318-116">As instâncias LineString a seguir são aceitas.</span><span class="sxs-lookup"><span data-stu-id="6b318-116">The following LineString instances are accepted.</span></span>

```
DECLARE @g1 geometry = 'LINESTRING EMPTY';
DECLARE @g2 geometry = 'LINESTRING(1 1,2 3,4 8, -6 3)';
DECLARE @g3 geometry = 'LINESTRING(1 1, 1 1)';
```

 <span data-ttu-id="6b318-117">`@g3` mostra que uma instância `LineString` pode ser aceita, mas não válida.</span><span class="sxs-lookup"><span data-stu-id="6b318-117">`@g3` shows that a `LineString` instance can be accepted, but not valid.</span></span>

 <span data-ttu-id="6b318-118">A instância `LineString` a seguir não é aceita.</span><span class="sxs-lookup"><span data-stu-id="6b318-118">The following `LineString` instance is not accepted.</span></span> <span data-ttu-id="6b318-119">Ela irá gerar um `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="6b318-119">It will throw a `System.FormatException`.</span></span>

```
DECLARE @g geometry = 'LINESTRING(1 1)';
```

### <a name="valid-instances"></a><span data-ttu-id="6b318-120">Instâncias válidas</span><span class="sxs-lookup"><span data-stu-id="6b318-120">Valid Instances</span></span>
 <span data-ttu-id="6b318-121">Para que uma instância `LineString` seja válida, ela deve atender aos seguintes critérios.</span><span class="sxs-lookup"><span data-stu-id="6b318-121">For a `LineString` instance to be valid it must meet the following criteria.</span></span>

1.  <span data-ttu-id="6b318-122">A instância `LineString` deve ser aceita.</span><span class="sxs-lookup"><span data-stu-id="6b318-122">The `LineString` instance must be accepted.</span></span>

2.  <span data-ttu-id="6b318-123">Se uma instância `LineString` não for vazia, ela deverá conter pelo menos dois pontos distintos.</span><span class="sxs-lookup"><span data-stu-id="6b318-123">If a `LineString` instance is not empty then it must contain at least two distinct points.</span></span>

3.  <span data-ttu-id="6b318-124">A instância `LineString` não pode se sobrepor sobre um intervalo de dois ou mais pontos consecutivos.</span><span class="sxs-lookup"><span data-stu-id="6b318-124">The `LineString` instance cannot overlap itself over an interval of two or more consecutive points.</span></span>

 <span data-ttu-id="6b318-125">As instâncias `LineString` a seguir são válidas.</span><span class="sxs-lookup"><span data-stu-id="6b318-125">The following `LineString` instances are valid.</span></span>

```
DECLARE @g1 geometry= 'LINESTRING EMPTY';
DECLARE @g2 geometry= 'LINESTRING(1 1, 3 3)';
DECLARE @g3 geometry= 'LINESTRING(1 1, 3 3, 2 4, 2 0)';
DECLARE @g4 geometry= 'LINESTRING(1 1, 3 3, 2 4, 2 0, 1 1)';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(), @g4.STIsValid();

```

 <span data-ttu-id="6b318-126">As instâncias `LineString` a seguir não são válidas.</span><span class="sxs-lookup"><span data-stu-id="6b318-126">The following `LineString` instances are not valid.</span></span>

```
DECLARE @g1 geometry = 'LINESTRING(1 4, 3 4, 2 4, 2 0)';
DECLARE @g2 geometry = 'LINESTRING(1 1, 1 1)';
SELECT @g1.STIsValid(), @g2.STIsValid();
```

> [!WARNING]
>  <span data-ttu-id="6b318-127">A detecção de sobreposições de `LineString` baseia-se em cálculos de pontos flutuantes, os quais não são exatos.</span><span class="sxs-lookup"><span data-stu-id="6b318-127">The detection of `LineString` overlaps is based on floating-point calculations, which are not exact.</span></span>

## <a name="examples"></a><span data-ttu-id="6b318-128">Exemplos</span><span class="sxs-lookup"><span data-stu-id="6b318-128">Examples</span></span>
 <span data-ttu-id="6b318-129">O exemplo a seguir mostra como criar uma instância `geometry``LineString` com três pontos e uma SRID de 0:</span><span class="sxs-lookup"><span data-stu-id="6b318-129">The following example shows how to create a `geometry``LineString` instance with three points and an SRID of 0:</span></span>

```
DECLARE @g geometry;
SET @g = geometry::STGeomFromText('LINESTRING(1 1, 2 4, 3 9)', 0);
```

 <span data-ttu-id="6b318-130">Cada ponto na instância `LineString` pode conter valores Z (elevação) e M (medida).</span><span class="sxs-lookup"><span data-stu-id="6b318-130">Each point in the `LineString` instance may contain Z (elevation) and M (measure) values.</span></span> <span data-ttu-id="6b318-131">Esse exemplo adiciona valores de M à instância `LineString` criada no exemplo acima.</span><span class="sxs-lookup"><span data-stu-id="6b318-131">This example adds M values to the `LineString` instance created in the example above.</span></span> <span data-ttu-id="6b318-132">M e Z podem ser valores nulos.</span><span class="sxs-lookup"><span data-stu-id="6b318-132">M and Z can be null values.</span></span>

```
DECLARE @g geometry;
SET @g = geometry::STGeomFromText('LINESTRING(1 1 NULL 0, 2 4 NULL 12.3, 3 9 NULL 24.5)', 0);
```

 <span data-ttu-id="6b318-133">O exemplo a seguir mostra como criar uma instância `geometry LineString` com dois pontos iguais.</span><span class="sxs-lookup"><span data-stu-id="6b318-133">The following example shows how to create a `geometry LineString` instance with two points that are the same.</span></span> <span data-ttu-id="6b318-134">Uma chamada para `IsValid` indica que a instância `LineString` não é válida e uma chamada para `MakeValid` converterá a instância `LineString` em um `Point`.</span><span class="sxs-lookup"><span data-stu-id="6b318-134">A call to `IsValid` indicates that the `LineString` instance is not valid and a call to `MakeValid` will convert the `LineString` instance into a `Point`.</span></span>

```sql
DECLARE @g geometry
SET @g = geometry::STGeomFromText('LINESTRING(1 3, 1 3)',0);
IF @g.STIsValid() = 1
  BEGIN
     SELECT @g.ToString() + ' is a valid LineString.';  
  END
ELSE
  BEGIN
     SELECT @g.ToString() + ' is not a valid LineString.';
     SET @g = @g.MakeValid();
     SELECT @g.ToString() + ' is a valid Point.';  
  END

```

 <span data-ttu-id="6b318-135">Os snippets de código acima irão retornar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6b318-135">The above code snippet will return the following:</span></span>

```
LINESTRING(1 3, 1 3) is not a valid LineString
POINT(1 3) is a valid Point.
```

## <a name="see-also"></a><span data-ttu-id="6b318-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6b318-136">See Also</span></span>
 <span data-ttu-id="6b318-137">[O &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) o &#40;tipo de dados [Geometry&#41;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) [ponto de extremidade &#40;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) tipo de dados de geometria&#41;o tipo de [dados geometry &#40;](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type)&#41;[STNumPoints](/sql/t-sql/spatial-geometry/stnumpoints-geometry-data-type) &#40;tipo de dados geometry&#41;[STIsRing &#40;tipo de dados geometry](/sql/t-sql/spatial-geometry/stisring-geometry-data-type)&#41;[STIsClosed &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) [STPointOnSurface &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [dados espaciais &#40;SQL Server](../spatial/spatial-data-sql-server.md)&#41;</span><span class="sxs-lookup"><span data-stu-id="6b318-137">[STLength &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) [STStartPoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) [STEndpoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) [STPointN &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type) [STNumPoints &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stnumpoints-geometry-data-type) [STIsRing &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisring-geometry-data-type) [STIsClosed &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) [STPointOnSurface &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md)</span></span>


