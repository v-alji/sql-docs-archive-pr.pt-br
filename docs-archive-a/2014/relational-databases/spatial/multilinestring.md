---
title: MultiLineString | Microsoft Docs
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- MultiLineString geometry subtype [SQL Server]
- geometry subtypes [SQL Server]
ms.assetid: 95deeefe-d6c5-4a11-b347-379e4486e7b7
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: fdd093d99d055df8e15fc22e3e570e6805e35d6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582912"
---
# <a name="multilinestring"></a><span data-ttu-id="b12db-102">MultiLineString</span><span class="sxs-lookup"><span data-stu-id="b12db-102">MultiLineString</span></span>
  <span data-ttu-id="b12db-103">Um `MultiLineString` é uma coleção de zero ou mais `geometry` instâncias ou **geographyLineString** .</span><span class="sxs-lookup"><span data-stu-id="b12db-103">A `MultiLineString` is a collection of zero or more `geometry` or **geographyLineString** instances.</span></span>  
  
## <a name="multilinestring-instances"></a><span data-ttu-id="b12db-104">Instâncias MultiLineString</span><span class="sxs-lookup"><span data-stu-id="b12db-104">MultiLineString instances</span></span>  
 <span data-ttu-id="b12db-105">A ilustração a seguir mostra exemplos de instâncias `MultiLineString`.</span><span class="sxs-lookup"><span data-stu-id="b12db-105">The illustration below shows examples of `MultiLineString` instances.</span></span>  
  
 <span data-ttu-id="b12db-106">![Exemplos das instâncias geométricas MultiLineString](../../database-engine/media/multilinestring.gif "Exemplos das instâncias geométricas MultiLineString")</span><span class="sxs-lookup"><span data-stu-id="b12db-106">![Examples of geometry MultiLineString instances](../../database-engine/media/multilinestring.gif "Examples of geometry MultiLineString instances")</span></span>  
  
 <span data-ttu-id="b12db-107">Conforme mostrado na ilustração:</span><span class="sxs-lookup"><span data-stu-id="b12db-107">As shown in the illustration:</span></span>  
  
-   <span data-ttu-id="b12db-108">A Figura 1 é uma `MultiLineString` instância simples cujo limite é de quatro pontos de extremidade de seus dois `LineString` elementos.</span><span class="sxs-lookup"><span data-stu-id="b12db-108">Figure 1 is a simple `MultiLineString` instance whose boundary is the four endpoints of its two `LineString` elements.</span></span>  
  
-   <span data-ttu-id="b12db-109">A Figura 2 é uma instância `MultiLineString` simples porque apenas os pontos de extremidade da interseção de elementos `LineString` se cruzam.</span><span class="sxs-lookup"><span data-stu-id="b12db-109">Figure 2 is a simple `MultiLineString` instance because only the endpoints of the `LineString` elements intersect.</span></span> <span data-ttu-id="b12db-110">O limite são os dois pontos de extremidade que não se sobrepõem.</span><span class="sxs-lookup"><span data-stu-id="b12db-110">The boundary is the two non-overlapping endpoints.</span></span>  
  
-   <span data-ttu-id="b12db-111">A Figura 3 é uma instância `MultiLineString` não simples porque apenas o interior de um de seus elementos `LineString` se cruzam.</span><span class="sxs-lookup"><span data-stu-id="b12db-111">Figure 3 is a nonsimple `MultiLineString` instance because the interior of one of its `LineString` elements is intersected.</span></span> <span data-ttu-id="b12db-112">O limite dessa instância `MultiLineString` são os quatro pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="b12db-112">The boundary of this `MultiLineString` instance is the four endpoints.</span></span>  
  
-   <span data-ttu-id="b12db-113">A Figura 4 é uma instância `MultiLineString` não simples, não fechada.</span><span class="sxs-lookup"><span data-stu-id="b12db-113">Figure 4 is a nonsimple, nonclosed `MultiLineString` instance.</span></span>  
  
-   <span data-ttu-id="b12db-114">A Figura 5 é uma instância `MultiLineString` simples, não fechada.</span><span class="sxs-lookup"><span data-stu-id="b12db-114">Figure 5 is a simple, nonclosed `MultiLineString`.</span></span> <span data-ttu-id="b12db-115">Ele não está fechado porque seus `LineStrings` elementos não estão fechados.</span><span class="sxs-lookup"><span data-stu-id="b12db-115">It is not closed because its `LineStrings` elements are not closed.</span></span> <span data-ttu-id="b12db-116">Ela é simples porque nenhum dos interiores de qualquer uma das instâncias `LineStrings` se cruzam.</span><span class="sxs-lookup"><span data-stu-id="b12db-116">It is simple because none of the interiors of any of the `LineStrings` instances intersect.</span></span>  
  
-   <span data-ttu-id="b12db-117">A Figura 6 é uma instância `MultiLineString` simples e fechada.</span><span class="sxs-lookup"><span data-stu-id="b12db-117">Figure 6 is a simple, closed `MultiLineString` instance.</span></span> <span data-ttu-id="b12db-118">Ela é fechada porque todos os seus elementos não estão fechados.</span><span class="sxs-lookup"><span data-stu-id="b12db-118">It is closed because all its elements are closed.</span></span> <span data-ttu-id="b12db-119">Ela é simples porque nenhum de seus elementos se cruzam nos interiores.</span><span class="sxs-lookup"><span data-stu-id="b12db-119">It is simple because none of its elements intersect at the interiors.</span></span>  
  
### <a name="accepted-instances"></a><span data-ttu-id="b12db-120">Instâncias aceitas</span><span class="sxs-lookup"><span data-stu-id="b12db-120">Accepted instances</span></span>  
 <span data-ttu-id="b12db-121">Para uma instância `MultiLineString` ser aceita, ela precisa estar vazia ou conter apenas instâncias `LineString` que sejam aceitos.</span><span class="sxs-lookup"><span data-stu-id="b12db-121">For a `MultiLineString` instance to be accepted it must either be empty or comprised of only `LineString` intances that are accepted.</span></span> <span data-ttu-id="b12db-122">Para obter mais informações sobre `LineString` instâncias aceitas, consulte [LineString](../spatial/linestring.md).</span><span class="sxs-lookup"><span data-stu-id="b12db-122">For more information on accepted `LineString` instances, see [LineString](../spatial/linestring.md).</span></span> <span data-ttu-id="b12db-123">Veja a seguir exemplos de instâncias `MultiLineString` aceitas.</span><span class="sxs-lookup"><span data-stu-id="b12db-123">The following are examples of accepted `MultiLineString` instances.</span></span>  
  
```  
DECLARE @g1 geometry = 'MULTILINESTRING EMPTY';  
DECLARE @g2 geometry = 'MULTILINESTRING((1 1, 3 5), (-5 3, -8 -2))';  
DECLARE @g3 geometry = 'MULTILINESTRING((1 1, 5 5), (1 3, 3 1))';  
DECLARE @g4 geometry = 'MULTILINESTRING((1 1, 3 3, 5 5),(3 3, 5 5, 7 7))';  
```  
  
 <span data-ttu-id="b12db-124">O exemplo a seguir gera um `System.FormatException` porque a segunda instância `LineString` não é válida.</span><span class="sxs-lookup"><span data-stu-id="b12db-124">The following example throws a `System.FormatException` because the second `LineString` instance is not valid.</span></span>  
  
```  
DECLARE @g geometry = 'MULTILINESTRING((1 1, 3 5),(-5 3))';  
```  
  
### <a name="valid-instances"></a><span data-ttu-id="b12db-125">Instâncias válidas</span><span class="sxs-lookup"><span data-stu-id="b12db-125">Valid instances</span></span>  
 <span data-ttu-id="b12db-126">Para que uma instância `MultiLineString` seja válida, ela deve atender aos seguintes critérios:</span><span class="sxs-lookup"><span data-stu-id="b12db-126">For a `MultiLineString` instance to be valid it must meet the following criteria:</span></span>  
  
1.  <span data-ttu-id="b12db-127">Todas as instâncias contendo a instância `MultiLineString` devem ser instâncias `LineString` válidas.</span><span class="sxs-lookup"><span data-stu-id="b12db-127">All instances comprising the `MultiLineString` instance must be valid `LineString` instances.</span></span>  
  
2.  <span data-ttu-id="b12db-128">Duas instâncias `LineString` contendo a instância `MultiLineString` não podem se sobrepor em um intervalo.</span><span class="sxs-lookup"><span data-stu-id="b12db-128">No two `LineString` instances comprising the `MultiLineString` instance may overlap over an interval.</span></span> <span data-ttu-id="b12db-129">Apenas em um número finito de pontos, é possível encontrar as instâncias `LineString` se cruzando ou se tocando umas com as outras, ou com outras instâncias `LineString`.</span><span class="sxs-lookup"><span data-stu-id="b12db-129">The `LineString` instances can only intersect or touch themselves or other `LineString` instances at a finite number of points.</span></span>  
  
 <span data-ttu-id="b12db-130">O exemplo a seguir mostra três instâncias `MultiLineString` válidas e uma instância `MultiLineString` que não é válida.</span><span class="sxs-lookup"><span data-stu-id="b12db-130">The following example shows three valid `MultiLineString` instances and one `MultiLineString` instance that is not valid.</span></span>  
  
```  
DECLARE @g1 geometry = 'MULTILINESTRING EMPTY';  
DECLARE @g2 geometry = 'MULTILINESTRING((1 1, 3 5), (-5 3, -8 -2))';  
DECLARE @g3 geometry = 'MULTILINESTRING((1 1, 5 5), (1 3, 3 1))';  
DECLARE @g4 geometry = 'MULTILINESTRING((1 1, 3 3, 5 5),(3 3, 5 5, 7 7))';  
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(), @g4.STIsValid();  
```  
  
 <span data-ttu-id="b12db-131">`@g4` não é válido porque a segunda instância `LineString` sobrepõe a primeira instância `LineString` em um intervalo.</span><span class="sxs-lookup"><span data-stu-id="b12db-131">`@g4` is not valid because the second `LineString` instance overlaps the first `LineString` instance at an interval.</span></span> <span data-ttu-id="b12db-132">Elas se tocam em um número infinito de pontos.</span><span class="sxs-lookup"><span data-stu-id="b12db-132">They touch at an infinite number of points.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b12db-133">Exemplos</span><span class="sxs-lookup"><span data-stu-id="b12db-133">Examples</span></span>  
 <span data-ttu-id="b12db-134">O exemplo a seguir cria uma instância simples do `geometry``MultiLineString` , que contém dois elementos de `LineString` com o SRID 0.</span><span class="sxs-lookup"><span data-stu-id="b12db-134">The following example creates a simple `geometry``MultiLineString` instance containing two `LineString` elements with the SRID 0.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('MULTILINESTRING((0 2, 1 1), (1 0, 1 1))');  
```  
  
 <span data-ttu-id="b12db-135">Para instanciar essa instância com um SRID diferente, use `STGeomFromText()` ou `STMLineStringFromText()`.</span><span class="sxs-lookup"><span data-stu-id="b12db-135">To instantiate this instance with a different SRID, use `STGeomFromText()` or `STMLineStringFromText()`.</span></span> <span data-ttu-id="b12db-136">Também é possível usar `Parse()` e, em seguida, modificar o SRID, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="b12db-136">You can also use `Parse()` and then modify the SRID, as shown in the following example.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('MULTILINESTRING((0 2, 1 1), (1 0, 1 1))');  
SET @g.STSrid = 13;  
```  
  
## <a name="see-also"></a><span data-ttu-id="b12db-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b12db-137">See Also</span></span>  
 <span data-ttu-id="b12db-138">[STLength &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) </span><span class="sxs-lookup"><span data-stu-id="b12db-138">[STLength &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) </span></span>  
 <span data-ttu-id="b12db-139">[STIsClosed &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) </span><span class="sxs-lookup"><span data-stu-id="b12db-139">[STIsClosed &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) </span></span>  
 <span data-ttu-id="b12db-140">[LineString](../spatial/linestring.md) </span><span class="sxs-lookup"><span data-stu-id="b12db-140">[LineString](../spatial/linestring.md) </span></span>  
 [<span data-ttu-id="b12db-141">Dados espaciais &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b12db-141">Spatial Data &#40;SQL Server&#41;</span></span>](../spatial/spatial-data-sql-server.md)  
  
  
