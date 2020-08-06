---
title: Visão geral de tipos de dados espaciais | Microsoft Docs
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- geometry data type [SQL Server], understanding
- geography data type [SQL Server], spatial data
- planar spatial data [SQL Server], geometry data type
- spatial data types [SQL Server]
ms.assetid: 1615db50-69de-4778-8be6-4e058c00ccd4
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: c0548d974e83bfe2b1e103d4458b17078fba8014
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682190"
---
# <a name="spatial-data-types-overview"></a><span data-ttu-id="c6b0c-102">Visão geral de tipos de dados espaciais</span><span class="sxs-lookup"><span data-stu-id="c6b0c-102">Spatial Data Types Overview</span></span>
  <span data-ttu-id="c6b0c-103">Há dois tipos de dados espaciais.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-103">There are two types of spatial data.</span></span> <span data-ttu-id="c6b0c-104">O tipo de dados `geometry` oferece suporte a dados planares ou a dados euclidianos (planisfério).</span><span class="sxs-lookup"><span data-stu-id="c6b0c-104">The `geometry` data type supports planar, or Euclidean (flat-earth), data.</span></span> <span data-ttu-id="c6b0c-105">O tipo de dados `geometry` (planar) está de acordo com os Recursos Simples do Open Geospatial Consortium (OGC) para o SQL Specification versão 1.1.0 e compatível com o SQL MM (padrão ISO).</span><span class="sxs-lookup"><span data-stu-id="c6b0c-105">The `geometry` data type both conforms to the Open Geospatial Consortium (OGC) Simple Features for SQL Specification version 1.1.0 and is compliant with SQL MM (ISO standard).</span></span>

 <span data-ttu-id="c6b0c-106">Além disso, o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] oferece suporte ao tipo de dados `geography` que armazena dados elipsoidais (globo), como coordenadas de latitude e longitude de GPS.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-106">In addition, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] supports the `geography` data type, which stores ellipsoidal (round-earth) data, such as GPS latitude and longitude coordinates.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="c6b0c-107">Para obter uma descrição detalhada e exemplos de recursos espaciais introduzidos no [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], incluindo aprimoramentos nos tipos de dados espaciais, baixe o white paper, [New Spatial Features in SQL Server Code-Named "Denali"](https://go.microsoft.com/fwlink/?LinkId=226407)(Novos recursos espaciais no SQL Server codinome "Denali").</span><span class="sxs-lookup"><span data-stu-id="c6b0c-107">For a detailed description and examples of spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], including enhancements to the spatial data types, download the white paper, [New Spatial Features in SQL Server Code-Named "Denali"](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>

##  <a name="spatial-data-objects"></a><a name="objects"></a> <span data-ttu-id="c6b0c-108">Objetos de dados espaciais</span><span class="sxs-lookup"><span data-stu-id="c6b0c-108">Spatial Data Objects</span></span>
 <span data-ttu-id="c6b0c-109">Os tipos de dados `geometry` e `geography` oferecem suporte a dezesseis objetos de dados espaciais, ou tipos de instâncias.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-109">The `geometry` and `geography` data types support sixteen spatial data objects, or instance types.</span></span> <span data-ttu-id="c6b0c-110">No entanto, apenas onze desses tipos de instâncias *podem ser instanciados*. É possível criar e trabalhar com essas instâncias (ou criar uma instância delas) em um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-110">However, only eleven of these instance types are *instantiable*; you can create and work with these instances (or instantiate them) in a database.</span></span> <span data-ttu-id="c6b0c-111">Essas instâncias derivam determinadas propriedades de seus tipos de dados pai que as distinguem como `Points` , **LineStrings, CircularStrings**, `CompoundCurves` , `Polygons` `CurvePolygons` ou como várias `geometry` `geography` instâncias ou em um `GeometryCollection` .</span><span class="sxs-lookup"><span data-stu-id="c6b0c-111">These instances derive certain properties from their parent data types that distinguish them as `Points`, **LineStrings, CircularStrings**, `CompoundCurves`, `Polygons`, `CurvePolygons` or as multiple `geometry` or `geography` instances in a `GeometryCollection`.</span></span> <span data-ttu-id="c6b0c-112">O tipo `Geography` tem um tipo de instância adicional, `FullGlobe`.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-112">`Geography` type has an additional instance type, `FullGlobe`.</span></span>

 <span data-ttu-id="c6b0c-113">A figura a seguir ilustra a hierarquia `geometry` na qual os tipos de dados `geometry` e `geography` se baseiam.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-113">The figure below depicts the `geometry` hierarchy upon which the `geometry` and `geography` data types are based.</span></span> <span data-ttu-id="c6b0c-114">Os tipos instanciáveis de `geometry` e `geography` são indicados em azul.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-114">The instantiable types of `geometry` and `geography` are indicated in blue.</span></span>

 <span data-ttu-id="c6b0c-115">![Hierarquia do tipo geométrico](../../database-engine/media/geom-hierarchy.gif "Hierarquia do tipo geométrico")</span><span class="sxs-lookup"><span data-stu-id="c6b0c-115">![Hierarchy of the geometry type](../../database-engine/media/geom-hierarchy.gif "Hierarchy of the geometry type")</span></span>

 <span data-ttu-id="c6b0c-116">Como a figura indica, os dez tipos de `geometry` dados e instanciáveis `geography` são `Point` ,,,,,, `MultiPoint` ,, `LineString` `CircularString` `MultiLineString` `CompoundCurve` `Polygon` `CurvePolygon` `MultiPolygon` e `GeometryCollection` .</span><span class="sxs-lookup"><span data-stu-id="c6b0c-116">As the figure indicates, the ten instantiable types of the `geometry` and `geography` data types are `Point`, `MultiPoint`, `LineString`, `CircularString`, `MultiLineString`, `CompoundCurve`, `Polygon`, `CurvePolygon`, `MultiPolygon`, and `GeometryCollection`.</span></span> <span data-ttu-id="c6b0c-117">Há um tipo adicional do qual se pode criar uma instância para o tipo de dados de geography: `FullGlobe`.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-117">There is one additional instantiable type for the geography data type: `FullGlobe`.</span></span> <span data-ttu-id="c6b0c-118">Os `geometry` `geography` tipos e podem reconhecer uma instância específica, desde que ela seja uma instância bem formada, mesmo que a instância não esteja definida explicitamente.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-118">The `geometry` and `geography` types can recognize a specific instance as long as it is a well-formed instance, even if the instance is not defined explicitly.</span></span> <span data-ttu-id="c6b0c-119">Por exemplo, se você definir uma `Point` instância explicitamente usando o método STPointFromText () `geometry` e `geography` reconhecer a instância como um `Point` , desde que a entrada do método esteja bem formada.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-119">For example, if you define a `Point` instance explicitly using the STPointFromText() method, `geometry` and `geography` recognize the instance as a `Point`, as long as the method input is well-formed.</span></span> <span data-ttu-id="c6b0c-120">Se você definir a mesma instância usando o método `STGeomFromText()`, os tipos de dados `geometry` e `geography` a reconhecerão como uma instância de `Point`.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-120">If you define the same instance using the `STGeomFromText()` method, both the `geometry` and `geography` data types recognize the instance as a `Point`.</span></span>

 <span data-ttu-id="c6b0c-121">Os subtipos dos tipos geometry e geography são divididos em tipos simples e de coleção.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-121">The subtypes for geometry and geography types are divided into simple and collection types.</span></span>  <span data-ttu-id="c6b0c-122">Alguns métodos como `STNumCurves()` só funcionam com tipos simples.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-122">Some methods like `STNumCurves()` work only with simple types.</span></span>

 <span data-ttu-id="c6b0c-123">Os tipos simples incluem:</span><span class="sxs-lookup"><span data-stu-id="c6b0c-123">Simple types include:</span></span>

-   [<span data-ttu-id="c6b0c-124">Ponto</span><span class="sxs-lookup"><span data-stu-id="c6b0c-124">Point</span></span>](../spatial/point.md)

-   [<span data-ttu-id="c6b0c-125">LineString</span><span class="sxs-lookup"><span data-stu-id="c6b0c-125">LineString</span></span>](../spatial/linestring.md)

-   [<span data-ttu-id="c6b0c-126">CircularString</span><span class="sxs-lookup"><span data-stu-id="c6b0c-126">CircularString</span></span>](../spatial/circularstring.md)

-   [<span data-ttu-id="c6b0c-127">CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="c6b0c-127">CompoundCurve</span></span>](../spatial/compoundcurve.md)

-   [<span data-ttu-id="c6b0c-128">Polygon</span><span class="sxs-lookup"><span data-stu-id="c6b0c-128">Polygon</span></span>](../spatial/polygon.md)

-   [<span data-ttu-id="c6b0c-129">CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="c6b0c-129">CurvePolygon</span></span>](../spatial/curvepolygon.md)

 <span data-ttu-id="c6b0c-130">Os tipos de coleção incluem:</span><span class="sxs-lookup"><span data-stu-id="c6b0c-130">Collection types include:</span></span>

-   [<span data-ttu-id="c6b0c-131">MultiPoint</span><span class="sxs-lookup"><span data-stu-id="c6b0c-131">MultiPoint</span></span>](../spatial/multipoint.md)

-   [<span data-ttu-id="c6b0c-132">MultiLineString</span><span class="sxs-lookup"><span data-stu-id="c6b0c-132">MultiLineString</span></span>](../spatial/multilinestring.md)

-   [<span data-ttu-id="c6b0c-133">MultiPolygon</span><span class="sxs-lookup"><span data-stu-id="c6b0c-133">MultiPolygon</span></span>](../spatial/multipolygon.md)

-   [<span data-ttu-id="c6b0c-134">GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="c6b0c-134">GeometryCollection</span></span>](../spatial/geometrycollection.md)


##  <a name="differences-between-the-geometry-and-geography-data-types"></a><a name="differences"></a> <span data-ttu-id="c6b0c-135">Diferenças entre os tipos de dados de geometria e geografia</span><span class="sxs-lookup"><span data-stu-id="c6b0c-135">Differences Between the geometry and geography Data Types</span></span>
 <span data-ttu-id="c6b0c-136">Os dois tipos de dados espaciais sempre se comportam de maneira muito semelhante, mas há algumas diferenças importantes na maneira como eles são armazenados e manipulados.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-136">The two types of spatial data often behave quite similarly, but there are some key differences in how the data is stored and manipulated.</span></span>

### <a name="how-connecting-edges-are-defined"></a><span data-ttu-id="c6b0c-137">Como bordas de conexão são definidas</span><span class="sxs-lookup"><span data-stu-id="c6b0c-137">How connecting edges are defined</span></span>
 <span data-ttu-id="c6b0c-138">Os dados definidos para os tipos `LineString` e `Polygon` são somente vértices.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-138">The defining data for `LineString` and `Polygon` types are vertices only.</span></span>  <span data-ttu-id="c6b0c-139">A borda de conexão entre dois vértices em um tipo geometry é uma linha reta.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-139">The connecting edge between two vertices in a geometry type is a straight line.</span></span>  <span data-ttu-id="c6b0c-140">No entanto, a borda de conexão entre dois vértices em um tipo de geografia é um amplo arco elíptico curto entre os dois vértices.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-140">However, the connecting edge between two vertices in a geography type is a short great elliptic arc between the two vertices.</span></span>  <span data-ttu-id="c6b0c-141">Uma grande elipse é a interseção do elipsoide com um plano no centro, e um amplo arco elíptico é um segmento de arco na grande elipse.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-141">A great ellipse is the intersection of the ellipsoid with a plane through its center and a great elliptic arc is an arc segment on the great ellipse.</span></span>

### <a name="how-circular-arc-segments-are-defined"></a><span data-ttu-id="c6b0c-142">Como são definidos segmentos de arco circular</span><span class="sxs-lookup"><span data-stu-id="c6b0c-142">How circular arc segments are defined</span></span>
 <span data-ttu-id="c6b0c-143">Os segmentos de arco circular para tipos geometry são definidos no plano de coordenadas cartesianas XY (são ignorados valores Z).</span><span class="sxs-lookup"><span data-stu-id="c6b0c-143">Circular arc segments for geometry types are defined on the XY Cartesian coordinate plane (Z values are ignored).</span></span> <span data-ttu-id="c6b0c-144">Os segmentos de arco circular para tipos geography são definidos por segmentos de curva em uma esfera de referência.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-144">Circular arc segments for geography types are defined by curve segments on a reference sphere.</span></span> <span data-ttu-id="c6b0c-145">Qualquer paralelo na esfera de referência pode ser definido por dois arcos circulares complementares, onde os pontos para ambos os arcos têm um ângulo de latitude constante.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-145">Any parallel on the reference sphere can be defined by two complementary circular arcs where the points for both arcs have a constant latitude angle.</span></span>

### <a name="measurements-in-spatial-data-types"></a><span data-ttu-id="c6b0c-146">Medidas em tipos de dados espaciais</span><span class="sxs-lookup"><span data-stu-id="c6b0c-146">Measurements in spatial data types</span></span>
 <span data-ttu-id="c6b0c-147">No sistema planar ou de terra plana, as medidas de distâncias e de áreas são fornecidas na mesma unidade de medida das coordenadas.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-147">In the planar, or flat-earth, system, measurements of distances and areas are given in the same unit of measurement as coordinates.</span></span> <span data-ttu-id="c6b0c-148">Usando o tipo de dados de `geometry`, a distância entre (2, 2) e (5, 6) é de 5 unidades, independentemente das unidades usadas.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-148">Using the `geometry` data type, the distance between (2, 2) and (5, 6) is 5 units, regardless of the units used.</span></span>

 <span data-ttu-id="c6b0c-149">No sistema elipsoidal ou de terra redonda, as coordenadas são fornecidas em graus de latitude ou de longitude.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-149">In the ellipsoidal, or round-earth system, coordinates are given in degrees of latitude and longitude.</span></span> <span data-ttu-id="c6b0c-150">No entanto os comprimentos e áreas são normalmente medidos em metros e metros quadrados, embora a medida possa depender do SRID (spatial reference identifier) da instância de `geography`.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-150">However, lengths and areas are usually measured in meters and square meters, though the measurement may depend on the spatial reference identifier (SRID) of the `geography` instance.</span></span> <span data-ttu-id="c6b0c-151">A unidade de medida mais comum para o tipo de dados `geography` é em metros.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-151">The most common unit of measurement for the `geography` data type is meters.</span></span>

### <a name="orientation-of-spatial-data"></a><span data-ttu-id="c6b0c-152">Orientação de dados espaciais</span><span class="sxs-lookup"><span data-stu-id="c6b0c-152">Orientation of spatial data</span></span>
 <span data-ttu-id="c6b0c-153">No sistema de planar, a orientação de anel de um polígono não é um fator importante.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-153">In the planar system, the ring orientation of a polygon is not an important factor.</span></span> <span data-ttu-id="c6b0c-154">Por exemplo, um polígono descrito por ((0, 0), (10, 0), (0, 20), (0, 0)) é o mesmo que um polígono descrito por ((0, 0), (0, 20), (10, 0), (0, 0)).</span><span class="sxs-lookup"><span data-stu-id="c6b0c-154">For example, a polygon described by ((0, 0), (10, 0), (0, 20), (0, 0)) is the same as a polygon described by ((0, 0), (0, 20), (10, 0), (0, 0)).</span></span> <span data-ttu-id="c6b0c-155">Os Recursos Simples do OGC para SQL Specification não ditam uma ordenação de anel e o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] não impõe ordenação de anel.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-155">The OGC Simple Features for SQL Specification does not dictate a ring ordering, and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not enforce ring ordering.</span></span>

 <span data-ttu-id="c6b0c-156">Em um sistema elipsoidal, um polígono não tem nenhum significado ou é ambíguo, sem uma orientação.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-156">In an ellipsoidal system, a polygon has no meaning, or is ambiguous, without an orientation.</span></span> <span data-ttu-id="c6b0c-157">Por exemplo, um anel ao redor do equador descreve o hemisfério norte ou o sul?</span><span class="sxs-lookup"><span data-stu-id="c6b0c-157">For example, does a ring around the equator describe the northern or southern hemisphere?</span></span> <span data-ttu-id="c6b0c-158">Se usarmos o tipo de dados `geography` para armazenar a instância espacial, deveremos especificar a orientação do anel e descrever precisamente o local da instância.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-158">If we use the `geography` data type to store the spatial instance, we must specify the orientation of the ring and accurately describe the location of the instance.</span></span> <span data-ttu-id="c6b0c-159">O interior do polígono em um sistema elipsoidal é definido pela regra à esquerda.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-159">The interior of the polygon in an ellipsoidal system is defined by the left-hand rule.</span></span>

 <span data-ttu-id="c6b0c-160">Quando o nível de compatibilidade é 100 ou abaixo no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] , o `geography` tipo de dados tem as seguintes restrições:</span><span class="sxs-lookup"><span data-stu-id="c6b0c-160">When the compatibility level is 100 or below in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] then the `geography` data type has the following restrictions:</span></span>

-   <span data-ttu-id="c6b0c-161">Cada instância de `geography` deve se ajustar dentro de um único hemisfério.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-161">Each `geography` instance must fit inside a single hemisphere.</span></span> <span data-ttu-id="c6b0c-162">Nenhum objeto espacial maior do que um hemisfério pode ser armazenado.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-162">No spatial objects larger than a hemisphere can be stored.</span></span>

-   <span data-ttu-id="c6b0c-163">Qualquer instância de `geography` de uma representação WKT (Well-Known Text) ou WKB (Well-Known Binary) do Open Geospatial Consortium (OGC) que reproduza um objeto maior do que um hemisfério aciona uma `ArgumentException`.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-163">Any `geography` instance from an Open Geospatial Consortium (OGC) Well-Known Text (WKT) or Well-Known Binary (WKB) representation that produces an object larger than a hemisphere throws an `ArgumentException`.</span></span>

-   <span data-ttu-id="c6b0c-164">Os `geography` métodos de tipo de dados que exigem a entrada de duas `geography` instâncias, como a interseção (), a Union (), a adequação () e STSymDifference (), retornarão NULL se os resultados dos métodos não couberem dentro de um único hemisfério.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-164">The `geography` data type methods that require the input of two `geography` instances, such as STIntersection(), STUnion(), STDifference(), and STSymDifference(), will return null if the results from the methods do not fit inside a single hemisphere.</span></span> <span data-ttu-id="c6b0c-165">STBuffer() também retornará nulo se a saída ultrapassar um único hemisfério.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-165">STBuffer() will also return null if the output exceeds a single hemisphere.</span></span>

 <span data-ttu-id="c6b0c-166">No [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], `FullGlobe` é um tipo especial de Polígono que abrange o globo inteiro.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-166">In [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], `FullGlobe` is a special type of Polygon that covers the entire globe.</span></span> <span data-ttu-id="c6b0c-167">`FullGlobe` tem uma área, mas nenhuma borda ou vértices.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-167">`FullGlobe` has an area, but no borders or vertices.</span></span>

### <a name="outer-and-inner-rings-not-important-in-geography-data-type"></a><span data-ttu-id="c6b0c-168">Anéis externos e internos não são importantes no tipo de dados geography</span><span class="sxs-lookup"><span data-stu-id="c6b0c-168">Outer and inner rings not important in geography data type</span></span>
 <span data-ttu-id="c6b0c-169">Os recursos simples do OGC para a especificação do SQL discutem anéis externos e anéis internos, mas essa distinção faz pouco sentido para o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `geography` tipo de dados; qualquer anel de um polígono pode ser levado para ser o anel externo.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-169">The OGC Simple Features for SQL Specification discusses outer rings and inner rings, but this distinction makes little sense for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `geography` data type; any ring of a polygon can be taken to be the outer ring.</span></span>

 <span data-ttu-id="c6b0c-170">Para obter mais informações sobre especificações do OCG, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c6b0c-170">For more information on OGC specifications, see the following:</span></span>

-   [<span data-ttu-id="c6b0c-171">OGC Specifications, Simple Feature Access Part 1 - Common Architecture</span><span class="sxs-lookup"><span data-stu-id="c6b0c-171">OGC Specifications, Simple Feature Access Part 1 - Common Architecture</span></span>](https://go.microsoft.com/fwlink/?LinkId=93627)

-   <span data-ttu-id="c6b0c-172">[Especificações do OGC, Simple Feature Access Part 2 – SQL Options](https://go.microsoft.com/fwlink/?LinkId=93628) (Acesso de recurso simples Parte 2 – opções de SQL)</span><span class="sxs-lookup"><span data-stu-id="c6b0c-172">[OGC Specifications, Simple Feature Access Part 2 - SQL Options](https://go.microsoft.com/fwlink/?LinkId=93628)</span></span>


##  <a name="circular-arc-segments"></a><a name="circular"></a> <span data-ttu-id="c6b0c-173">Segmentos de arco circular</span><span class="sxs-lookup"><span data-stu-id="c6b0c-173">Circular Arc Segments</span></span>
 <span data-ttu-id="c6b0c-174">Três tipos instanciáveis podem adotar segmentos de arco circular: `CircularString`, `CompoundCurve` e `CurvePolygon`.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-174">Three instantiable types can take circular arc segments: `CircularString`, `CompoundCurve`, and `CurvePolygon`.</span></span>  <span data-ttu-id="c6b0c-175">Um segmento de arco circular é definido por três pontos em um plano bidimensional, e o terceiro ponto não pode ser igual ao primeiro.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-175">A circular arc segment is defined by three points in a two dimensional plane and the third point cannot be the same as the first point.</span></span>

 <span data-ttu-id="c6b0c-176">As figuras A e B mostram segmentos de arco circular típicos.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-176">Figures A and B show typical circular arc segments.</span></span> <span data-ttu-id="c6b0c-177">Observe como cada um dos três pontos se situa no perímetro de um círculo.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-177">Note how each of the three points lie on the perimeter of a circle.</span></span>

 <span data-ttu-id="c6b0c-178">As figuras C e D mostram como um segmento de linha pode ser definido como um segmento de arco circular.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-178">Figures C and D show how a line segment can be defined as a circular arc segment.</span></span>  <span data-ttu-id="c6b0c-179">Observe que três pontos ainda são necessários para definir o segmento de arco circular, ao contrário de um segmento de linha normal, que pode ser definido por apenas dois pontos.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-179">Note that three points are still needed to define the circular arc segment unlike a regular line segment which can be defined by just two points.</span></span>

 <span data-ttu-id="c6b0c-180">Os métodos que operam em tipos de segmento de arco circular usam segmentos de linha reta para aproximar o arco circular. O número de segmentos de linha usado para aproximar o arco dependerá do comprimento e da curvatura do arco. Podem ser armazenados valores Z para cada um dos tipos de segmento de arco circular; porém, os métodos não usarão os valores Z em seus cálculos.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-180">Methods operating on circular arc segment types use straight line segments to approximate the circular arc. The number of line segments used to approximate the arc will depend on the length and curvature of the arc. Z values can be stored for each of the circular arc segment types; however, methods will not use the Z values in their calculations.</span></span>

> [!NOTE]
>  <span data-ttu-id="c6b0c-181">Se forem fornecidos valores Z para segmentos de arco circular, eles deverão ser iguais para todos os pontos no segmento de arco circular para que o segmento seja aceito para entrada.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-181">If Z values are given for circular arc segments then they must be the same for all points in the circular arc segment for it to be accepted for input.</span></span> <span data-ttu-id="c6b0c-182">Por exemplo, `CIRCULARSTRING(0 0 1, 2 2 1, 4 0 1)` é aceito, mas `CIRCULARSTRING(0 0 1, 2 2 2, 4 0 1)` não é.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-182">For example: `CIRCULARSTRING(0 0 1, 2 2 1, 4 0 1)` is accepted, but `CIRCULARSTRING(0 0 1, 2 2 2, 4 0 1)` is not accepted.</span></span>

### <a name="linestring-and-circularstring-comparison"></a><span data-ttu-id="c6b0c-183">Comparação de LineString e CircularString</span><span class="sxs-lookup"><span data-stu-id="c6b0c-183">LineString and CircularString comparison</span></span>
 <span data-ttu-id="c6b0c-184">O diagrama a seguir mostra triângulos isósceles idênticos (o triângulo A usa segmentos de linha para definir o triângulo, e o triângulo B usa segmentos de arco circular para definir o triângulo):</span><span class="sxs-lookup"><span data-stu-id="c6b0c-184">The following diagram shows identical isosceles triangles (triangle A uses line segments to define the triangle and triangle B uses circular arc segments to defined the triangle):</span></span>

 ![](../../database-engine/media/7e382f76-59da-4b62-80dc-caf93e637c14.png "7e382f76-59da-4b62-80dc-caf93e637c14")

 <span data-ttu-id="c6b0c-185">Este exemplo mostra como armazenar os triângulos isósceles anteriores que usam uma instância `LineString` e uma `CircularString`:</span><span class="sxs-lookup"><span data-stu-id="c6b0c-185">This example shows how to store the above isosceles triangles using both a `LineString` instance and `CircularString` instance:</span></span>

```sql
DECLARE @g1 geometry;
DECLARE @g2 geometry;
SET @g1 = geometry::STGeomFromText('LINESTRING(1 1, 5 1, 3 5, 1 1)', 0);
SET @g2 = geometry::STGeomFromText('CIRCULARSTRING(1 1, 3 1, 5 1, 4 3, 3 5, 2 3, 1 1)', 0);
IF @g1.STIsValid() = 1 AND @g2.STIsValid() = 1
  BEGIN
      SELECT @g1.ToString(), @g2.ToString()
      SELECT @g1.STLength() AS [LS Length], @g2.STLength() AS [CS Length]
  END
```

 <span data-ttu-id="c6b0c-186">Note que uma instância `CircularString` requer sete pontos para definir o triângulo, mas uma instância `LineString` requer somente quatro pontos para definir o triângulo.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-186">Notice that a `CircularString` instance requires seven points to define the triangle, but a `LineString` instance requires only four points to define the triangle.</span></span> <span data-ttu-id="c6b0c-187">O motivo para isso é que uma instância `CircularString` armazena segmentos de arco circular e não segmentos de linha.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-187">The reason for this is that a `CircularString` instance stores circular arc segments and not line segments.</span></span> <span data-ttu-id="c6b0c-188">Portanto, os lados do triângulo armazenados na instância `CircularString` são ABC, CDE e EFA, ao passo que os lados do triângulo armazenados na instância `LineString` são AC, CE e EA.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-188">So the sides of the triangle stored in the `CircularString` instance are ABC, CDE, and EFA whereas the sides of the triangle stored in the `LineString` instance are AC, CE, and EA.</span></span>

 <span data-ttu-id="c6b0c-189">Considere o seguinte snippet de código:</span><span class="sxs-lookup"><span data-stu-id="c6b0c-189">Consider the following code snippet:</span></span>

```sql
SET @g1 = geometry::STGeomFromText('LINESTRING(0 0, 2 2, 4 0)', 0);
SET @g2 = geometry::STGeomFromText('CIRCULARSTRING(0 0, 2 2, 4 0)', 0);
SELECT @g1.STLength() AS [LS Length], @g2.STLength() AS [CS Length];
```

 <span data-ttu-id="c6b0c-190">Esse snippet produzirá os seguintes resultados:</span><span class="sxs-lookup"><span data-stu-id="c6b0c-190">This snippet will produce the following results:</span></span>

```
LS LengthCS Length
5.65685...6.28318...
```

 <span data-ttu-id="c6b0c-191">A ilustração a seguir mostra como cada tipo é armazenado (mostrado na linha vermelha `LineString``@g1` , mostra a linha azul `CircularString``@g2` ):</span><span class="sxs-lookup"><span data-stu-id="c6b0c-191">The following illustration shows how each type is stored (red line shows `LineString``@g1`, blue line shows `CircularString``@g2`):</span></span>

 ![](../../database-engine/media/e52157b5-5160-4a4b-8560-50cdcf905b76.png "e52157b5-5160-4a4b-8560-50cdcf905b76")

 <span data-ttu-id="c6b0c-192">Como a ilustração acima mostra, as instâncias `CircularString` usam menos pontos para armazenar limites de curva com maior precisão que instâncias `LineString`.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-192">As the illustration above shows, `CircularString` instances use fewer points to store curve boundaries with greater precision than `LineString` instances.</span></span> <span data-ttu-id="c6b0c-193">As instâncias `CircularString` são úteis para armazenar limites circulares como um raio de pesquisa de vinte milhas de um ponto específico.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-193">`CircularString` instances are useful for storing circular boundaries like a twenty-mile search radius from a specific point.</span></span> <span data-ttu-id="c6b0c-194">Instâncias `LineString` são boas para armazenar limites que são lineares como um quarteirão de cidade.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-194">`LineString` instances are good for storing boundaries that are linear like a square city block.</span></span>

### <a name="linestring-and-compoundcurve-comparison"></a><span data-ttu-id="c6b0c-195">Comparação de LineString e CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="c6b0c-195">LineString and CompoundCurve comparison</span></span>
 <span data-ttu-id="c6b0c-196">Os exemplos de código seguintes mostram como armazenar a mesma figura usando instâncias `LineString` e `CompoundCurve`:</span><span class="sxs-lookup"><span data-stu-id="c6b0c-196">The following code examples show how to store the same figure using `LineString` and `CompoundCurve` instances:</span></span>

```sql
SET @g = geometry::Parse('LINESTRING(2 2, 4 2, 4 4, 2 4, 2 2)');
SET @g = geometry::Parse('COMPOUNDCURVE((2 2, 4 2), (4 2, 4 4), (4 4, 2 4), (2 4, 2 2))');
SET @g = geometry::Parse('COMPOUNDCURVE((2 2, 4 2, 4 4, 2 4, 2 2))');
```

 <span data-ttu-id="c6b0c-197">ou o</span><span class="sxs-lookup"><span data-stu-id="c6b0c-197">or</span></span>

 <span data-ttu-id="c6b0c-198">Nos exemplos anteriores, uma instância `LineString` ou uma instância `CompoundCurve` poderiam armazenar a figura.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-198">In the examples above, either a `LineString` instance or a `CompoundCurve` instance could store the figure.</span></span>  <span data-ttu-id="c6b0c-199">Este próximo exemplo usa uma `CompoundCurve` para armazenar uma fatia de pizza:</span><span class="sxs-lookup"><span data-stu-id="c6b0c-199">This next example uses a `CompoundCurve` to store a pie slice:</span></span>

```sql
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(2 2, 1 3, 0 2),(0 2, 1 0, 2 2))');
```

 <span data-ttu-id="c6b0c-200">Uma instância `CompoundCurve` pode armazenar o segmento de arco circular (2 2, 1 3, 0 2) diretamente, ao passo que uma instância `LineString` teria que converter a curva em vários segmentos de linha menores.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-200">A `CompoundCurve` instance can store the circular arc segment (2 2, 1 3, 0 2) directly whereas a `LineString` instance would have to convert the curve into several smaller line segments.</span></span>

### <a name="circularstring-and-compoundcurve-comparison"></a><span data-ttu-id="c6b0c-201">Comparação de CircularString e CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="c6b0c-201">CircularString and CompoundCurve comparison</span></span>
 <span data-ttu-id="c6b0c-202">O exemplo de código a seguir mostra como a fatia de pizza pode ser armazenada em uma instância `CircularString`:</span><span class="sxs-lookup"><span data-stu-id="c6b0c-202">The following code example shows how the pie slice can be stored in a `CircularString` instance:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('CIRCULARSTRING( 0 0, 1 2.1082, 3 6.3246, 0 7, -3 6.3246, -1 2.1082, 0 0)');
SELECT @g.ToString(), @g.STLength();
```

 <span data-ttu-id="c6b0c-203">Para armazenar a fatia de pizza usando uma instância `CircularString`, é necessário que três pontos sejam usados para cada segmento de linha.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-203">To store the pie slice using a `CircularString` instance requires that three points be used for each line segment.</span></span>  <span data-ttu-id="c6b0c-204">Se um ponto intermediário não for conhecido, ele deverá ser calculado ou o ponto de extremidade do segmento de linha deverá ser dobrado como mostra o seguinte snippet:</span><span class="sxs-lookup"><span data-stu-id="c6b0c-204">If an intermediate point is not known, it either has to be calculated or the endpoint of the line segment has to be doubled as the following snippet shows:</span></span>

```sql
SET @g = geometry::Parse('CIRCULARSTRING( 0 0, 3 6.3246, 3 6.3246, 0 7, -3 6.3246, 0 0, 0 0)');
```

 <span data-ttu-id="c6b0c-205">`CompoundCurve`as instâncias permitem ambos os `LineString` `CircularString` componentes e, de forma que apenas dois pontos para os segmentos de linha da fatia da pizza precisem ser conhecidos.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-205">`CompoundCurve` instances allow both `LineString` and `CircularString` components so that only two points to the line segments of the pie slice need to be known.</span></span>  <span data-ttu-id="c6b0c-206">Este exemplo de código mostra como usar uma `CompoundCurve` para armazenar a mesma figura:</span><span class="sxs-lookup"><span data-stu-id="c6b0c-206">This code example shows how to use a `CompoundCurve` to store the same figure:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING( 3 6.3246, 0 7, -3 6.3246), (-3 6.3246, 0 0, 3 6.3246))');
SELECT @g.ToString(), @g.STLength();
```

### <a name="polygon-and-curvepolygon-comparison"></a><span data-ttu-id="c6b0c-207">Comparação de Polygon e CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="c6b0c-207">Polygon and CurvePolygon comparison</span></span>
 <span data-ttu-id="c6b0c-208">Instâncias `CurvePolygon` podem usar instâncias `CircularString` e `CompoundCurve` ao definir os seus anéis exteriores e interiores.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-208">`CurvePolygon` instances can use `CircularString` and `CompoundCurve` instances when defining their exterior and interior rings.</span></span>  <span data-ttu-id="c6b0c-209">Instâncias `Polygon` não podem usar os tipos de segmento de arco circular: `CircularString` e `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="c6b0c-209">`Polygon` instances cannot use the circular arc segment types: `CircularString` and `CompoundCurve`.</span></span>


## <a name="see-also"></a><span data-ttu-id="c6b0c-210">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c6b0c-210">See Also</span></span>
 <span data-ttu-id="c6b0c-211">[Dados espaciais &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) [método de tipo de dados geometry referência](/sql/t-sql/spatial-geometry/spatial-types-geometry-transact-sql) do [método de tipo de dados geography](/sql/t-sql/spatial-geography/spatial-types-geography) [STNumCurves &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/stnumcurves-geometry-data-type) [STNumCurves &#40;tipo de dados geography&#41;](/sql/t-sql/spatial-geography/stnumcurves-geography-data-type) [STGeomFromText &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/stgeomfromtext-geometry-data-type) [STGeomFromText &#40;tipo de dados geography&#41;](/sql/t-sql/spatial-geography/stgeomfromtext-geography-data-type)</span><span class="sxs-lookup"><span data-stu-id="c6b0c-211">[Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) [geometry Data Type Method Reference](/sql/t-sql/spatial-geometry/spatial-types-geometry-transact-sql) [geography Data Type Method Reference](/sql/t-sql/spatial-geography/spatial-types-geography) [STNumCurves &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stnumcurves-geometry-data-type) [STNumCurves &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stnumcurves-geography-data-type) [STGeomFromText &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stgeomfromtext-geometry-data-type) [STGeomFromText &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stgeomfromtext-geography-data-type)</span></span>


