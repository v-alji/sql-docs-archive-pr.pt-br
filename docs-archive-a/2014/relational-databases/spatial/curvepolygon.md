---
title: CurvePolygon | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: e000a1d8-a049-4542-bfeb-943fd6ab3969
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: b90fdbd9a0bc80dfc6a82416d0193b2951fe13ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569860"
---
# <a name="curvepolygon"></a><span data-ttu-id="22c32-102">CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="22c32-102">CurvePolygon</span></span>
  <span data-ttu-id="22c32-103">`CurvePolygon` é uma superfície topologicamente fechada definida por um anel delimitador exterior e zero ou mais anéis interiores</span><span class="sxs-lookup"><span data-stu-id="22c32-103">A `CurvePolygon` is a topologically closed surface defined by an exterior bounding ring and zero or more interior rings</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="22c32-104">Para obter uma descrição detalhada e exemplos de recursos espaciais introduzidos no [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , incluindo o `CurvePolygon` subtipo, baixe o White Paper, [novos recursos espaciais no SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span><span class="sxs-lookup"><span data-stu-id="22c32-104">For a detailed description and examples of spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], including the `CurvePolygon` subtype, download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>  
  
 <span data-ttu-id="22c32-105">Os critérios a seguir definem atributos de uma `CurvePolygon` instância do:</span><span class="sxs-lookup"><span data-stu-id="22c32-105">The following criteria define attributes of a `CurvePolygon` instance:</span></span>  
  
-   <span data-ttu-id="22c32-106">O limite da instância `CurvePolygon` é definido pelo anel exterior e por todos os anéis interiores.</span><span class="sxs-lookup"><span data-stu-id="22c32-106">The boundary of the `CurvePolygon` instance is defined by the exterior ring and all interior rings.</span></span>  
  
-   <span data-ttu-id="22c32-107">O interior da instância `CurvePolygon` é o espaço entre o anel exterior e todos os anéis interiores.</span><span class="sxs-lookup"><span data-stu-id="22c32-107">The interior of the `CurvePolygon` instance is the space between the exterior ring and all of the interior rings.</span></span>  
  
 <span data-ttu-id="22c32-108">Uma instância `CurvePolygon` é diferente de uma instância `Polygon` porque uma instância `CurvePolygon` pode conter os seguintes segmentos de arco circular: `CircularString` e `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="22c32-108">A `CurvePolygon` instance differs from a `Polygon` instance in that a `CurvePolygon` instance may contain the following circular arc segments: `CircularString` and `CompoundCurve`.</span></span>  
  
## <a name="compoundcurve-instances"></a><span data-ttu-id="22c32-109">Instâncias CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="22c32-109">CompoundCurve instances</span></span>  
 <span data-ttu-id="22c32-110">A ilustração a seguir mostra figuras de `CurvePolygon` válidas:</span><span class="sxs-lookup"><span data-stu-id="22c32-110">Illustration below shows valid `CurvePolygon` figures:</span></span>  
  
### <a name="accepted-instances"></a><span data-ttu-id="22c32-111">Instâncias aceitas</span><span class="sxs-lookup"><span data-stu-id="22c32-111">Accepted instances</span></span>  
 <span data-ttu-id="22c32-112">Para uma instância `CurvePolygon` ser aceita, ela precisa estar vazia ou conter apenas anéis de arco circular que sejam aceitos.</span><span class="sxs-lookup"><span data-stu-id="22c32-112">For a `CurvePolygon` instance to be accepted, it needs to be either empty or contain only circular arc rings that are accepted.</span></span> <span data-ttu-id="22c32-113">Um anel de arco circular aceito atende aos requisitos a seguir.</span><span class="sxs-lookup"><span data-stu-id="22c32-113">An accepted circular arc ring meets the following requirements.</span></span>  
  
1.  <span data-ttu-id="22c32-114">É uma instância `LineString`, `CircularString` ou `CompoundCurve` aceita.</span><span class="sxs-lookup"><span data-stu-id="22c32-114">Is an accepted `LineString`, `CircularString`, or `CompoundCurve` instance.</span></span> <span data-ttu-id="22c32-115">Para obter mais informações sobre instâncias aceitas, consulte [LineString](linestring.md), [CircularString](circularstring.md)e [CompoundCurve](compoundcurve.md).</span><span class="sxs-lookup"><span data-stu-id="22c32-115">For more information on accepted instances, see [LineString](linestring.md), [CircularString](circularstring.md), and [CompoundCurve](compoundcurve.md).</span></span>  
  
2.  <span data-ttu-id="22c32-116">Tem pelo menos quatro pontos.</span><span class="sxs-lookup"><span data-stu-id="22c32-116">Has at least four points.</span></span>  
  
3.  <span data-ttu-id="22c32-117">O ponto inicial e o ponto de extremidade têm as mesmas coordenadas de X e Y.</span><span class="sxs-lookup"><span data-stu-id="22c32-117">The start and end point have the same X and Y coordinates.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="22c32-118">Os valores de Z e M são ignorados.</span><span class="sxs-lookup"><span data-stu-id="22c32-118">Z and M values are ignored.</span></span>  
  
 <span data-ttu-id="22c32-119">O exemplo a seguir mostra instâncias `CurvePolygon` aceitas.</span><span class="sxs-lookup"><span data-stu-id="22c32-119">The following example shows accepted `CurvePolygon` instances.</span></span>  
  
```  
DECLARE @g1 geometry = 'CURVEPOLYGON EMPTY';  
DECLARE @g2 geometry = 'CURVEPOLYGON((0 0, 0 0, 0 0, 0 0))';  
DECLARE @g3 geometry = 'CURVEPOLYGON((0 0 1, 0 0 2, 0 0 3, 0 0 3))'  
DECLARE @g4 geometry = 'CURVEPOLYGON(CIRCULARSTRING(1 3, 3 5, 4 7, 7 3, 1 3))';  
DECLARE @g5 geography = 'CURVEPOLYGON((-122.3 47, 122.3 -47, 125.7 -49, 121 -38, -122.3 47))';  
```  
  
 <span data-ttu-id="22c32-120">`@g3` é aceito, embora os pontos inicial e de extremidade tenham valores de Z diferentes, pois esses valores são ignorados.</span><span class="sxs-lookup"><span data-stu-id="22c32-120">`@g3` is accepted even though the start and end points have different Z values because Z values are ignored.</span></span> <span data-ttu-id="22c32-121">`@g5` é aceito, embora a instância de tipo `geography` não seja válida.</span><span class="sxs-lookup"><span data-stu-id="22c32-121">`@g5` is accepted even though the `geography` type instance is not valid.</span></span>  
  
 <span data-ttu-id="22c32-122">Os exemplos a seguir geram um `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="22c32-122">The following examples throw `System.FormatException`.</span></span>  
  
```  
DECLARE @g1 geometry = 'CURVEPOLYGON((0 5, 0 0, 0 0, 0 0))';  
DECLARE @g2 geometry = 'CURVEPOLYGON((0 0, 0 0, 0 0))';  
```  
  
 <span data-ttu-id="22c32-123">`@g1` não é aceito porque os pontos inicial e de extremidade não têm o mesmo valor de Y.</span><span class="sxs-lookup"><span data-stu-id="22c32-123">`@g1` is not accepted because the start and end points do not have the same Y value.</span></span> <span data-ttu-id="22c32-124">`@g2` não é aceito porque o anel não contém pontos suficientes.</span><span class="sxs-lookup"><span data-stu-id="22c32-124">`@g2` is not accepted because the ring does not have enough points.</span></span>  
  
### <a name="valid-instances"></a><span data-ttu-id="22c32-125">Instâncias válidas</span><span class="sxs-lookup"><span data-stu-id="22c32-125">Valid instances</span></span>  
 <span data-ttu-id="22c32-126">Para que uma instância `CurvePolygon` seja válida, os anéis exterior e interior devem atender aos seguintes critérios:</span><span class="sxs-lookup"><span data-stu-id="22c32-126">For a `CurvePolygon` instance to be valid both exterior and interior rings must meet the following criteria:</span></span>  
  
1.  <span data-ttu-id="22c32-127">Eles podem tocar apenas em pontos tangentes únicos.</span><span class="sxs-lookup"><span data-stu-id="22c32-127">They may only touch at single tangent points.</span></span>  
  
2.  <span data-ttu-id="22c32-128">Eles não podem se cruzar.</span><span class="sxs-lookup"><span data-stu-id="22c32-128">They cannot cross each other.</span></span>  
  
3.  <span data-ttu-id="22c32-129">Cada anel deve conter pelo menos quatro pontos.</span><span class="sxs-lookup"><span data-stu-id="22c32-129">Each ring must contain at least four points.</span></span>  
  
4.  <span data-ttu-id="22c32-130">Cada anel deve ser um tipo de curva aceitável.</span><span class="sxs-lookup"><span data-stu-id="22c32-130">Each ring must be an acceptable curve type.</span></span>  
  
 <span data-ttu-id="22c32-131">As instâncias `CurvePolygon` também deverão atender a critérios específicos se forem tipos de dados `geometry` ou `geography`.</span><span class="sxs-lookup"><span data-stu-id="22c32-131">`CurvePolygon` instances also need to meet specific criteria depending on whether they are `geometry` or `geography` data types.</span></span>  
  
#### <a name="geometry-data-type"></a><span data-ttu-id="22c32-132">Tipo de dados geometry</span><span class="sxs-lookup"><span data-stu-id="22c32-132">Geometry data type</span></span>  
 <span data-ttu-id="22c32-133">Uma instância **geometryCurvePolygon** válida deve ter os seguintes atributos:</span><span class="sxs-lookup"><span data-stu-id="22c32-133">A valid **geometryCurvePolygon** instance must have the following attributes:</span></span>  
  
1.  <span data-ttu-id="22c32-134">Todos os anéis interiores devem estar dentro do anel exterior.</span><span class="sxs-lookup"><span data-stu-id="22c32-134">All the interior rings must be contained within the exterior ring.</span></span>  
  
2.  <span data-ttu-id="22c32-135">Pode ter vários anéis interiores, mas um anel interior não pode conter outro anel interior.</span><span class="sxs-lookup"><span data-stu-id="22c32-135">May have multiple interior rings, but an interior ring cannot contain another interior ring.</span></span>  
  
3.  <span data-ttu-id="22c32-136">Nenhum anel pode cruzar com outro anel ou com si próprio.</span><span class="sxs-lookup"><span data-stu-id="22c32-136">No ring can cross itself or another ring.</span></span>  
  
4.  <span data-ttu-id="22c32-137">Os anéis podem tocar apenas pontos tangentes únicos (o número de pontos onde os anéis tocam deve ser finito).</span><span class="sxs-lookup"><span data-stu-id="22c32-137">Rings can only touch at single tangent points (number of points where rings touch must be finite).</span></span>  
  
5.  <span data-ttu-id="22c32-138">O interior do polígono deve estar conectado.</span><span class="sxs-lookup"><span data-stu-id="22c32-138">The interior of the polygon must be connected.</span></span>  
  
 <span data-ttu-id="22c32-139">O exemplo a seguir mostra uma instância **geometryCurvePolygon** válida.</span><span class="sxs-lookup"><span data-stu-id="22c32-139">The following example shows valid **geometryCurvePolygon** instances.</span></span>  
  
```  
DECLARE @g1 geometry = 'CURVEPOLYGON EMPTY';  
DECLARE @g2 geometry = 'CURVEPOLYGON(CIRCULARSTRING(1 3, 3 5, 4 7, 7 3, 1 3))';  
SELECT @g1.STIsValid(), @g2.STIsValid();  
```  
  
 <span data-ttu-id="22c32-140">As instâncias CurvePolygon têm as mesmas regras de validade que as instâncias Polygon, com exceção de que as instâncias CurvePolygon podem aceitar os novos tipos de segmento de arco circular.</span><span class="sxs-lookup"><span data-stu-id="22c32-140">CurvePolygon instances have the same validity rules as Polygon instances with the exception that CurvePolygon instances may accept the new circular arc segment types.</span></span> <span data-ttu-id="22c32-141">Para obter mais exemplos de instâncias válidas ou não válidas, consulte [Polygon](polygon.md).</span><span class="sxs-lookup"><span data-stu-id="22c32-141">For more examples of instances that are valid or not valid, see [Polygon](polygon.md).</span></span>  
  
#### <a name="geography-data-type"></a><span data-ttu-id="22c32-142">Tipo de dados geography</span><span class="sxs-lookup"><span data-stu-id="22c32-142">Geography data type</span></span>  
 <span data-ttu-id="22c32-143">Uma instância **geographyCurvePolygon** válida deve ter os seguintes atributos:</span><span class="sxs-lookup"><span data-stu-id="22c32-143">A valid **geographyCurvePolygon** instance must have the following attributes:</span></span>  
  
1.  <span data-ttu-id="22c32-144">O interior do polígono é conectado usando a regra do lado esquerdo.</span><span class="sxs-lookup"><span data-stu-id="22c32-144">The interior of the polygon is connected using the left-hand rule.</span></span>  
  
2.  <span data-ttu-id="22c32-145">Nenhum anel pode cruzar com outro anel ou com si próprio.</span><span class="sxs-lookup"><span data-stu-id="22c32-145">No ring can cross itself or another ring.</span></span>  
  
3.  <span data-ttu-id="22c32-146">Os anéis podem tocar apenas pontos tangentes únicos (o número de pontos onde os anéis tocam deve ser finito).</span><span class="sxs-lookup"><span data-stu-id="22c32-146">Rings can only touch at single tangent points (number of points where rings touch must be finite).</span></span>  
  
4.  <span data-ttu-id="22c32-147">O interior do polígono deve estar conectado.</span><span class="sxs-lookup"><span data-stu-id="22c32-147">The interior of the polygon must be connected.</span></span>  
  
 <span data-ttu-id="22c32-148">O exemplo a seguir mostra uma instância CurvePolygon de geography válida.</span><span class="sxs-lookup"><span data-stu-id="22c32-148">The following example shows a valid geography CurvePolygon instance.</span></span>  
  
```  
DECLARE @g geography = 'CURVEPOLYGON((-122.3 47, 122.3 47, 125.7 49, 121 38, -122.3 47))';  
SELECT @g.STIsValid();  
```  
  
## <a name="examples"></a><span data-ttu-id="22c32-149">Exemplos</span><span class="sxs-lookup"><span data-stu-id="22c32-149">Examples</span></span>  
  
### <a name="a-instantiating-a-geometry-instance-with-an-empty-curvepolygon"></a><span data-ttu-id="22c32-150">a.</span><span class="sxs-lookup"><span data-stu-id="22c32-150">A.</span></span> <span data-ttu-id="22c32-151">Criando uma instância geométrica com um CurvePolygon vazio</span><span class="sxs-lookup"><span data-stu-id="22c32-151">Instantiating a Geometry Instance with an Empty CurvePolygon</span></span>  
 <span data-ttu-id="22c32-152">Esse exemplo mostra como criar uma instância `CurvePolygon` vazia:</span><span class="sxs-lookup"><span data-stu-id="22c32-152">This example shows how to create an empty `CurvePolygon` instance:</span></span>  
  
```sql  
DECLARE @g geometry;  
SET @g = geometry::Parse('CURVEPOLYGON EMPTY');  
```  
  
### <a name="b-declaring-and-instantiating-a-geometry-instance-with-a-curvepolygon-in-the-same-statement"></a><span data-ttu-id="22c32-153">B.</span><span class="sxs-lookup"><span data-stu-id="22c32-153">B.</span></span> <span data-ttu-id="22c32-154">Declarando e criando uma instância geométrica com um CurvePolygon na mesma instrução</span><span class="sxs-lookup"><span data-stu-id="22c32-154">Declaring and Instantiating a Geometry Instance with a CurvePolygon in the Same Statement</span></span>  
 <span data-ttu-id="22c32-155">Este snippet de código mostra como declarar e iniciar uma instância de geometry com um `CurvePolygon` na mesma instrução:</span><span class="sxs-lookup"><span data-stu-id="22c32-155">This code snippet shows how to declare and initialize a geometry instance with a `CurvePolygon` in the same statement:</span></span>  
  
```sql  
DECLARE @g geometry = 'CURVEPOLYGON(CIRCULARSTRING(2 4, 4 2, 6 4, 4 6, 2 4))'  
```  
  
### <a name="c-instantiating-a-geography-instance-with-a-curvepolygon"></a><span data-ttu-id="22c32-156">C.</span><span class="sxs-lookup"><span data-stu-id="22c32-156">C.</span></span> <span data-ttu-id="22c32-157">Criando uma instância geográfica com um CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="22c32-157">Instantiating a Geography Instance with a CurvePolygon</span></span>  
 <span data-ttu-id="22c32-158">Este snippet de código mostra como declarar e iniciar uma instância de `geography` com um `CurvePolygon`:</span><span class="sxs-lookup"><span data-stu-id="22c32-158">This code snippet shows how to declare and initialize a `geography` instance with a `CurvePolygon`:</span></span>  
  
```sql  
DECLARE @g geography = 'CURVEPOLYGON(CIRCULARSTRING(-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653))';  
```  
  
### <a name="d-storing-a-curvepolygon-with-only-an-exterior-bounding-ring"></a><span data-ttu-id="22c32-159">D.</span><span class="sxs-lookup"><span data-stu-id="22c32-159">D.</span></span> <span data-ttu-id="22c32-160">Armazenando um CurvePolygon com apenas um anel delimitador exterior</span><span class="sxs-lookup"><span data-stu-id="22c32-160">Storing a CurvePolygon with Only an Exterior Bounding Ring</span></span>  
 <span data-ttu-id="22c32-161">Este exemplo mostra como armazenar um círculo simples em uma instância `CurvePolygon` (apenas um anel delimitador exterior é usado para definir o círculo):</span><span class="sxs-lookup"><span data-stu-id="22c32-161">This example shows how to store a simple circle in a `CurvePolygon` instance (only an exterior bounding ring is used to define the circle):</span></span>  
  
```sql  
DECLARE @g geometry;  
SET @g = geometry::Parse('CURVEPOLYGON(CIRCULARSTRING(2 4, 4 2, 6 4, 4 6, 2 4))');  
SELECT @g.STArea() AS Area;  
```  
  
### <a name="e-storing-a-curvepolygon-containing-interior-rings"></a><span data-ttu-id="22c32-162">E.</span><span class="sxs-lookup"><span data-stu-id="22c32-162">E.</span></span> <span data-ttu-id="22c32-163">Armazenando um CurvePolygon que contém anéis interiores</span><span class="sxs-lookup"><span data-stu-id="22c32-163">Storing a CurvePolygon Containing Interior Rings</span></span>  
 <span data-ttu-id="22c32-164">Este exemplo cria uma rosca em uma instância `CurvePolygon` (um anel delimitador exterior e um anel interior são usados para definir a rosca):</span><span class="sxs-lookup"><span data-stu-id="22c32-164">This example creates a donut in a `CurvePolygon` instance (both an exterior bounding ring and an interior ring is used to define the donut):</span></span>  
  
```sql  
DECLARE @g geometry;  
SET @g = geometry::Parse('CURVEPOLYGON(CIRCULARSTRING(0 4, 4 0, 8 4, 4 8, 0 4), CIRCULARSTRING(2 4, 4 2, 6 4, 4 6, 2 4))');  
SELECT @g.STArea() AS Area;  
```  
  
 <span data-ttu-id="22c32-165">Este exemplo mostra uma instância `CurvePolygon` válida e uma instância inválida ao usar anéis interiores:</span><span class="sxs-lookup"><span data-stu-id="22c32-165">This example shows both a valid `CurvePolygon` instance and an invalid instance when using interior rings:</span></span>  
  
```sql  
DECLARE @g1 geometry, @g2 geometry;  
SET @g1 = geometry::Parse('CURVEPOLYGON(CIRCULARSTRING(0 5, 5 0, 0 -5, -5 0, 0 5), (-2 2, 2 2, 2 -2, -2 -2, -2 2))');  
IF @g1.STIsValid() = 1  
  BEGIN  
     SELECT @g1.STArea();  
  END  
SET @g2 = geometry::Parse('CURVEPOLYGON(CIRCULARSTRING(0 5, 5 0, 0 -5, -5 0, 0 5), (0 5, 5 0, 0 -5, -5 0, 0 5))');  
IF @g2.STIsValid() = 1  
  BEGIN  
     SELECT @g2.STArea();  
  END  
SELECT @g1.STIsValid() AS G1, @g2.STIsValid() AS G2;  
```  
  
 <span data-ttu-id="22c32-166">Tanto o @g1 quanto o @g2 usam o mesmo anel delimitador exterior: um círculo com um raio de 5 e ambos usam um quadrado para um anel interior.</span><span class="sxs-lookup"><span data-stu-id="22c32-166">Both @g1 and @g2 use the same exterior bounding ring: a circle with a radius of 5 and they both use a square for an interior ring.</span></span>  <span data-ttu-id="22c32-167">Entretanto, a instância @g1 é válida, mas a instância @g2 é inválida.</span><span class="sxs-lookup"><span data-stu-id="22c32-167">However, the instance @g1 is valid, but the instance @g2 is invalid.</span></span>  <span data-ttu-id="22c32-168">A razão pela qual @g2 é inválida é que o anel interior divide o espaço interno limitado pelo anel exterior em quatro regiões separadas.</span><span class="sxs-lookup"><span data-stu-id="22c32-168">The reason that @g2 is invalid is that the interior ring splits the interior space bounded by the exterior ring into four separate regions.</span></span>  <span data-ttu-id="22c32-169">O desenho a seguir mostra o que ocorreu:</span><span class="sxs-lookup"><span data-stu-id="22c32-169">The following drawing shows what occurred:</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22c32-170">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="22c32-170">See Also</span></span>  
 <span data-ttu-id="22c32-171">[Polygon](polygon.md) </span><span class="sxs-lookup"><span data-stu-id="22c32-171">[Polygon](polygon.md) </span></span>  
 <span data-ttu-id="22c32-172">[CircularString](circularstring.md) </span><span class="sxs-lookup"><span data-stu-id="22c32-172">[CircularString](circularstring.md) </span></span>  
 <span data-ttu-id="22c32-173">[CompoundCurve](compoundcurve.md) </span><span class="sxs-lookup"><span data-stu-id="22c32-173">[CompoundCurve](compoundcurve.md) </span></span>  
 <span data-ttu-id="22c32-174">[Referência de método de tipo de dados geometry](/sql/t-sql/spatial-geometry/spatial-types-geometry-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="22c32-174">[geometry Data Type Method Reference](/sql/t-sql/spatial-geometry/spatial-types-geometry-transact-sql) </span></span>  
 <span data-ttu-id="22c32-175">[Referência de método de tipo de dados geography](/sql/t-sql/spatial-geography/spatial-types-geography) </span><span class="sxs-lookup"><span data-stu-id="22c32-175">[geography Data Type Method Reference](/sql/t-sql/spatial-geography/spatial-types-geography) </span></span>  
 [<span data-ttu-id="22c32-176">Visão geral de tipos de dados espaciais</span><span class="sxs-lookup"><span data-stu-id="22c32-176">Spatial Data Types Overview</span></span>](spatial-data-types-overview.md)  
  
  
