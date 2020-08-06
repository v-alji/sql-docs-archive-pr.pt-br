---
title: GeometryCollection | Microsoft Docs
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- GeomCollection geometry subtype [SQL Server]
- geometry subtypes [SQL Server]
ms.assetid: 4445c0d9-a66b-4d7c-88e4-a66fa6f7d9fd
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 71d2234a9b73b7647554e364fe3864f089a47a0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582922"
---
# <a name="geometrycollection"></a><span data-ttu-id="d5091-102">GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="d5091-102">GeometryCollection</span></span>
  <span data-ttu-id="d5091-103">Uma `GeometryCollection` é uma coleção de zero ou mais instâncias de `geometry` ou de `geography`.</span><span class="sxs-lookup"><span data-stu-id="d5091-103">A `GeometryCollection` is a collection of zero or more `geometry` or `geography` instances.</span></span> <span data-ttu-id="d5091-104">Uma `GeometryCollection` pode estar vazia.</span><span class="sxs-lookup"><span data-stu-id="d5091-104">A `GeometryCollection` can be empty.</span></span>  
  
## <a name="geometrycollection-instances"></a><span data-ttu-id="d5091-105">Instâncias de GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="d5091-105">GeometryCollection Instances</span></span>  
  
### <a name="accepted-instances"></a><span data-ttu-id="d5091-106">Instâncias aceitas</span><span class="sxs-lookup"><span data-stu-id="d5091-106">Accepted Instances</span></span>  
 <span data-ttu-id="d5091-107">Para que uma instância de `GeometryCollection` seja aceita, ela deve ser uma instância de `GeometryCollection` vazia ou todas as instâncias que englobam a instância de `GeometryCollection` devem ser instâncias aceitas.</span><span class="sxs-lookup"><span data-stu-id="d5091-107">For a `GeometryCollection` instance to be accepted, it must either be an empty `GeometryCollection` instance or all the instances comprising the `GeometryCollection` instance must be accepted instances.</span></span> <span data-ttu-id="d5091-108">O exemplo a seguir mostra as instâncias aceitas.</span><span class="sxs-lookup"><span data-stu-id="d5091-108">The following example shows accepted instances.</span></span>  
  
```  
DECLARE @g1 geometry = 'GEOMETRYCOLLECTION EMPTY';  
DECLARE @g2 geometry = 'GEOMETRYCOLLECTION(LINESTRING EMPTY,POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
DECLARE @g3 geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1, 3 5),POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
```  
  
 <span data-ttu-id="d5091-109">O exemplo a seguir emite uma `System.FormatException` porque a instância de `LinesString` na instância de `GeometryCollection` não é aceita.</span><span class="sxs-lookup"><span data-stu-id="d5091-109">The following example throws a `System.FormatException` because the `LinesString` instance in the `GeometryCollection` instance is not accepted.</span></span>  
  
```  
DECLARE @g geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1), POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
```  
  
### <a name="valid-instances"></a><span data-ttu-id="d5091-110">Instâncias válidas</span><span class="sxs-lookup"><span data-stu-id="d5091-110">Valid Instances</span></span>  
 <span data-ttu-id="d5091-111">Uma instância de `GeometryCollection` é válida quando todas as instâncias que englobam a instância de `GeometryCollection` são válidas.</span><span class="sxs-lookup"><span data-stu-id="d5091-111">A `GeometryCollection` instance is valid when all instances that comprise the `GeometryCollection` instance are valid.</span></span> <span data-ttu-id="d5091-112">O exemplo a seguir mostra três instâncias de `GeometryCollection` válidas e uma instância que não é válida.</span><span class="sxs-lookup"><span data-stu-id="d5091-112">The following shows three valid `GeometryCollection` instances and one instance that is not valid.</span></span>  
  
```  
DECLARE @g1 geometry = 'GEOMETRYCOLLECTION EMPTY';  
DECLARE @g2 geometry = 'GEOMETRYCOLLECTION(LINESTRING EMPTY,POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
DECLARE @g3 geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1, 3 5),POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
DECLARE @g4 geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1, 3 5),POLYGON((-1 -1, 1 -5, -5 5, -5 -1, -1 -1)))';  
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(), @g4.STIsValid();  
```  
  
 <span data-ttu-id="d5091-113">`@g4` não é válida porque a instância de `Polygon` na instância de `GeometryCollection` não é válida.</span><span class="sxs-lookup"><span data-stu-id="d5091-113">`@g4` is not valid because the `Polygon` instance in the `GeometryCollection` instance is not valid.</span></span>  
  
 <span data-ttu-id="d5091-114">Para obter mais informações sobre instâncias aceitas e válidas, consulte [Point](point.md), [MultiPoint](multipoint.md), [LineString](linestring.md), [MultiLineString](multilinestring.md), [Polygon](polygon.md)e [MultiPolygon](multipolygon.md).</span><span class="sxs-lookup"><span data-stu-id="d5091-114">For more information on accepted and valid instances, see [Point](point.md), [MultiPoint](multipoint.md), [LineString](linestring.md), [MultiLineString](multilinestring.md), [Polygon](polygon.md), and [MultiPolygon](multipolygon.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d5091-115">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d5091-115">Examples</span></span>  
 <span data-ttu-id="d5091-116">O exemplo a seguir cria uma instância de `geometry``GeometryCollection` com valores Z no SRID 1 contendo uma instância de `Point` e uma instância de `Polygon` .</span><span class="sxs-lookup"><span data-stu-id="d5091-116">The following example instantiates a `geometry``GeometryCollection` with Z values in SRID 1 containing a `Point` instance and a `Polygon` instance.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomCollFromText('GEOMETRYCOLLECTION(POINT(3 3 1), POLYGON((0 0 2, 1 10 3, 1 0 4, 0 0 2)))', 1);  
```  
  
## <a name="see-also"></a><span data-ttu-id="d5091-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d5091-117">See Also</span></span>  
 [<span data-ttu-id="d5091-118">Dados espaciais &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d5091-118">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
