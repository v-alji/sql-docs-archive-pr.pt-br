---
title: CompoundCurve | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: ae357f9b-e3e2-4cdf-af02-012acda2e466
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 6a899bbe9a17a64083592e1078e8cac93365f02b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569865"
---
# <a name="compoundcurve"></a><span data-ttu-id="07910-102">CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="07910-102">CompoundCurve</span></span>
  <span data-ttu-id="07910-103">Uma `CompoundCurve` é uma coleção de zero ou mais instâncias `CircularString` ou `LineString` contínuas dos tipos geometry ou geography.</span><span class="sxs-lookup"><span data-stu-id="07910-103">A `CompoundCurve` is a collection of zero or more continuous `CircularString` or `LineString` instances of either geometry or geography types.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="07910-104">Para obter uma descrição detalhada e exemplos dos novos recursos espaciais nesta versão, incluindo o `CompoundCurve` subtipo, baixe o White Paper, [novos recursos espaciais no SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span><span class="sxs-lookup"><span data-stu-id="07910-104">For a detailed description and examples of the new spatial features in this release, including the `CompoundCurve` subtype, download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>

 <span data-ttu-id="07910-105">Pode ser criada uma instância `CompoundCurve` vazia, mas para que `CompoundCurve` seja válida, ela deve atender aos seguintes critérios:</span><span class="sxs-lookup"><span data-stu-id="07910-105">An empty `CompoundCurve` instance can be instantiated, but for a `CompoundCurve` to be valid it must meet the following criteria:</span></span>

1.  <span data-ttu-id="07910-106">Deve conter pelo menos uma instância `CircularString` ou `LineString`.</span><span class="sxs-lookup"><span data-stu-id="07910-106">It must contain at least one `CircularString` or `LineString` instance.</span></span>

2.  <span data-ttu-id="07910-107">A sequência de instâncias `CircularString` ou `LineString` deve ser contínua.</span><span class="sxs-lookup"><span data-stu-id="07910-107">The sequence of `CircularString` or `LineString` instances must be continuous.</span></span>

 <span data-ttu-id="07910-108">Se um `CompoundCurve` contiver uma sequência de `CircularString` várias `LineString` instâncias, o ponto de extremidade final para cada instância, exceto para a última instância, deverá ser o ponto de extremidade inicial para a próxima instância na sequência.</span><span class="sxs-lookup"><span data-stu-id="07910-108">If a `CompoundCurve` contains a sequence of multiple `CircularString` and `LineString` instances, the ending endpoint for every instance except for the last instance must be the starting endpoint for the next instance in the sequence.</span></span> <span data-ttu-id="07910-109">Isso significa que, se o ponto final de uma instância anterior na sequência for (4 3 7 2), o ponto inicial da próxima instância na sequência deverá ser (4 3 7 2).</span><span class="sxs-lookup"><span data-stu-id="07910-109">This means that if the ending point of a prior instance in the sequence is (4 3 7 2), the starting point for the next instance in the sequence must be (4 3 7 2).</span></span> <span data-ttu-id="07910-110">Observe que os valores Z (elevação) e M (medida) do ponto também devem ser iguais.</span><span class="sxs-lookup"><span data-stu-id="07910-110">Note that Z(elevation) and M(measure) values for the point must also be the same.</span></span> <span data-ttu-id="07910-111">Se houver uma diferença nos dois pontos, será lançada uma `System.FormatException` .</span><span class="sxs-lookup"><span data-stu-id="07910-111">If there is a difference in the two points, a `System.FormatException` is thrown.</span></span> <span data-ttu-id="07910-112">Os pontos em uma `CircularString` não precisam ter um valor Z ou M.</span><span class="sxs-lookup"><span data-stu-id="07910-112">Points in a `CircularString` do not have to have a Z or M value.</span></span> <span data-ttu-id="07910-113">Se não forem fornecidos valores Z ou M para o ponto final da instância anterior, o ponto inicial da próxima instância não poderá incluir valores Z ou M.</span><span class="sxs-lookup"><span data-stu-id="07910-113">If no Z or M values are given for the ending point of the prior instance, the starting point of the next instance cannot include Z or M values.</span></span> <span data-ttu-id="07910-114">Se o ponto final da sequência anterior for (4 3), o ponto inicial da próxima sequência deverá ser (4 3); ele não poderá ser (4 3 7 2).</span><span class="sxs-lookup"><span data-stu-id="07910-114">If the ending point for the prior sequence is (4 3), the starting point for the next sequence must be (4 3); it cannot be (4 3 7 2).</span></span> <span data-ttu-id="07910-115">Todos os pontos em uma instância `CompoundCurve` não devem ter nenhum valor Z ou devem ter o mesmo valor Z.</span><span class="sxs-lookup"><span data-stu-id="07910-115">All points in a `CompoundCurve` instance must have either no Z value or the same Z value.</span></span>

## <a name="compoundcurve-instances"></a><span data-ttu-id="07910-116">Instâncias CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="07910-116">CompoundCurve instances</span></span>
 <span data-ttu-id="07910-117">A ilustração a seguir mostra tipos de `CompoundCurve` válidos.</span><span class="sxs-lookup"><span data-stu-id="07910-117">The following illustration shows valid `CompoundCurve` types.</span></span>

 ![](../../database-engine/media/f278742e-b861-4555-8b51-3d972b7602bf.png "f278742e-b861-4555-8b51-3d972b7602bf")

### <a name="accepted-instances"></a><span data-ttu-id="07910-118">Instâncias aceitas</span><span class="sxs-lookup"><span data-stu-id="07910-118">Accepted instances</span></span>
 <span data-ttu-id="07910-119">A instância `CompoundCurve` será aceita se for uma instância vazia ou se atender aos critérios a seguir.</span><span class="sxs-lookup"><span data-stu-id="07910-119">`CompoundCurve` instance is accepted if it is an empty instance or meets the following criteria.</span></span>

1.  <span data-ttu-id="07910-120">Todas as instâncias contidas na instância `CompoundCurve` são instâncias de segmento de arco circular aceitas.</span><span class="sxs-lookup"><span data-stu-id="07910-120">All the instances contained by `CompoundCurve` instance are accepted circular arc segment instances.</span></span> <span data-ttu-id="07910-121">Para obter mais informações sobre instâncias de segmento de arco circular aceitas, veja [LineString](linestring.md) e [CircularString](circularstring.md).</span><span class="sxs-lookup"><span data-stu-id="07910-121">For more information on accepted circular arc segment instances, see [LineString](linestring.md) and [CircularString](circularstring.md).</span></span>

2.  <span data-ttu-id="07910-122">Todos os segmentos de arco circular na instância `CompoundCurve` estão conectados.</span><span class="sxs-lookup"><span data-stu-id="07910-122">All of the circular arc segments in the `CompoundCurve` instance are connected.</span></span> <span data-ttu-id="07910-123">O primeiro ponto de cada segmento de arco circular sucessivo é igual ao último ponto no segmento de arco circular anterior.</span><span class="sxs-lookup"><span data-stu-id="07910-123">The first point for each succeeding circular arc segment is the same as the last point on the preceding circular arc segment.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="07910-124">Isso inclui as coordenadas Z e M.</span><span class="sxs-lookup"><span data-stu-id="07910-124">This includes the Z and M coordinates.</span></span> <span data-ttu-id="07910-125">Assim, as quatro coordenadas X, Y, Z e M devem ser iguais.</span><span class="sxs-lookup"><span data-stu-id="07910-125">So, all four coordinates X, Y, Z, and M must be the same.</span></span>

3.  <span data-ttu-id="07910-126">Nenhuma das instâncias contidas é uma instância vazia.</span><span class="sxs-lookup"><span data-stu-id="07910-126">None of the contained instances are empty instances.</span></span>

 <span data-ttu-id="07910-127">O exemplo a seguir mostra instâncias `CompoundCurve` aceitas.</span><span class="sxs-lookup"><span data-stu-id="07910-127">The following example shows accepted `CompoundCurve` instances.</span></span>

```
DECLARE @g1 geometry = 'COMPOUNDCURVE EMPTY';
DECLARE @g2 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 0, 0 1, -1 0), (-1 0, 2 0))';
```

 <span data-ttu-id="07910-128">O exemplo a seguir mostra instâncias `CompoundCurve` que não são aceitas.</span><span class="sxs-lookup"><span data-stu-id="07910-128">The following example shows `CompoundCurve` instances that are not accepted.</span></span> <span data-ttu-id="07910-129">Essas instâncias lançam `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="07910-129">These instances throw `System.FormatException`.</span></span>

```
DECLARE @g1 geometry = 'COMPOUNDCURVE(CIRCULARSTRING EMPTY)';
DECLARE @g2 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 0, 0 1, -1 0), (1 0, 2 0))';
```

### <a name="valid-instances"></a><span data-ttu-id="07910-130">Instâncias válidas</span><span class="sxs-lookup"><span data-stu-id="07910-130">Valid instances</span></span>
 <span data-ttu-id="07910-131">Uma instância `CompoundCurve` será válida se atender aos critérios a seguir.</span><span class="sxs-lookup"><span data-stu-id="07910-131">A `CompoundCurve` instance is valid if it meets the following criteria.</span></span>

1.  <span data-ttu-id="07910-132">A instância `CompoundCurve` é aceita.</span><span class="sxs-lookup"><span data-stu-id="07910-132">The `CompoundCurve` instance is accepted.</span></span>

2.  <span data-ttu-id="07910-133">Todas as instâncias de segmento de arco circular contidas na instância `CompoundCurve` são instâncias válidas.</span><span class="sxs-lookup"><span data-stu-id="07910-133">All circular arc segment instances contained by the `CompoundCurve` instance are valid instances.</span></span>

 <span data-ttu-id="07910-134">O exemplo a seguir mostra instâncias `CompoundCurve` válidas.</span><span class="sxs-lookup"><span data-stu-id="07910-134">The following example shows valid `CompoundCurve` instances.</span></span>

```
DECLARE @g1 geometry = 'COMPOUNDCURVE EMPTY';
DECLARE @g2 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 0, 0 1, -1 0), (-1 0, 2 0))';
DECLARE @g3 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 1, 1 1, 1 1), (1 1, 3 5, 5 4))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid();

```

 <span data-ttu-id="07910-135">`@g3` é válido porque a instância `CircularString` é válida.</span><span class="sxs-lookup"><span data-stu-id="07910-135">`@g3` is valid because the `CircularString` instance is valid.</span></span> <span data-ttu-id="07910-136">Para obter mais informações sobre a validade da `CircularString` instância, consulte [circularstring](circularstring.md).</span><span class="sxs-lookup"><span data-stu-id="07910-136">For more information on the validity of the `CircularString` instance, see [CircularString](circularstring.md).</span></span>

 <span data-ttu-id="07910-137">O exemplo a seguir mostra instâncias `CompoundCurve` que não são válidas.</span><span class="sxs-lookup"><span data-stu-id="07910-137">The following example shows `CompoundCurve` instances that are not valid.</span></span>

```
DECLARE @g1 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 1, 1 1, 1 1), (1 1, 3 5, 5 4, 3 5))';
DECLARE @g2 geometry = 'COMPOUNDCURVE((1 1, 1 1))';
DECLARE @g3 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 1, 2 3, 1 1))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid();
```

 <span data-ttu-id="07910-138">`@g1` não é válido porque a segunda instância não é uma instância de LineString válida.</span><span class="sxs-lookup"><span data-stu-id="07910-138">`@g1` is not valid because the second instance is not a valid LineString instance.</span></span> <span data-ttu-id="07910-139">`@g2` não é válido porque a instância de `LineString` não é válida.</span><span class="sxs-lookup"><span data-stu-id="07910-139">`@g2` is not valid because the `LineString` instance is not valid.</span></span> <span data-ttu-id="07910-140">`@g3` não é válido porque a instância de `CircularString` não é válida.</span><span class="sxs-lookup"><span data-stu-id="07910-140">`@g3` is not valid because the `CircularString` instance is not valid.</span></span> <span data-ttu-id="07910-141">Para obter mais informações sobre as `CircularString` instâncias e válidas `LineString` , consulte [Circularstring](circularstring.md) e [LineString](linestring.md).</span><span class="sxs-lookup"><span data-stu-id="07910-141">For more information on valid `CircularString` and `LineString` instances, see [CircularString](circularstring.md) and [LineString](linestring.md).</span></span>

## <a name="examples"></a><span data-ttu-id="07910-142">Exemplos</span><span class="sxs-lookup"><span data-stu-id="07910-142">Examples</span></span>

### <a name="a-instantiating-a-geometry-instance-with-an-empty-compooundcurve"></a><span data-ttu-id="07910-143">a.</span><span class="sxs-lookup"><span data-stu-id="07910-143">A.</span></span> <span data-ttu-id="07910-144">Criando uma instância de geometry com uma CompoundCurve vazia</span><span class="sxs-lookup"><span data-stu-id="07910-144">Instantiating a geometry instance with an empty CompooundCurve</span></span>
 <span data-ttu-id="07910-145">O exemplo a seguir mostra como criar uma instância `CompoundCurve` vazia:</span><span class="sxs-lookup"><span data-stu-id="07910-145">The following example shows how to create an empty `CompoundCurve` instance:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('COMPOUNDCURVE EMPTY');
```

### <a name="b-declaring-and-instantiating-a-geometry-instance-using-a-compoundcurve-in-the-same-statement"></a><span data-ttu-id="07910-146">B.</span><span class="sxs-lookup"><span data-stu-id="07910-146">B.</span></span> <span data-ttu-id="07910-147">Declarando e criando uma instância de geometry usando uma CompoundCurve na mesma instrução</span><span class="sxs-lookup"><span data-stu-id="07910-147">Declaring and instantiating a geometry instance using a CompoundCurve in the same statement</span></span>
 <span data-ttu-id="07910-148">O seguinte exemplo mostra como declarar e inicializar uma instância `geometry` com um `CompoundCurve`na mesma instrução:</span><span class="sxs-lookup"><span data-stu-id="07910-148">The following example shows how to declare and initialize a `geometry` instance with a `CompoundCurve`in the same statement:</span></span>

```sql
DECLARE @g geometry = 'COMPOUNDCURVE ((2 2, 0 0),CIRCULARSTRING (0 0, 1 2.1082, 3 6.3246, 0 7, -3 6.3246, -1 2.1082, 0 0))';
```

### <a name="c-instantiating-a-geography-instance-with-a-compoundcurve"></a><span data-ttu-id="07910-149">C.</span><span class="sxs-lookup"><span data-stu-id="07910-149">C.</span></span> <span data-ttu-id="07910-150">Criando uma instância de geography com uma CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="07910-150">Instantiating a geography instance with a CompoundCurve</span></span>
 <span data-ttu-id="07910-151">O exemplo a seguir mostra como declarar e inicializar uma instância de `geography` com uma `CompoundCurve`:</span><span class="sxs-lookup"><span data-stu-id="07910-151">The following example shows how to declare and initialize a `geography` instance with a `CompoundCurve`:</span></span>

```sql
DECLARE @g geography = 'COMPOUNDCURVE(CIRCULARSTRING(-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653))';
```

### <a name="d-storing-a-square-in-a-compoundcurve-instance"></a><span data-ttu-id="07910-152">D.</span><span class="sxs-lookup"><span data-stu-id="07910-152">D.</span></span> <span data-ttu-id="07910-153">Armazenando um quadrado em uma instância CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="07910-153">Storing a square in a CompoundCurve instance</span></span>
 <span data-ttu-id="07910-154">O exemplo seguinte usa uma instância `CompoundCurve` de duas maneiras diferentes para armazenar um quadrado.</span><span class="sxs-lookup"><span data-stu-id="07910-154">The following example uses two different ways to use a `CompoundCurve` instance to store a square.</span></span>

```sql
DECLARE @g1 geometry, @g2 geometry;
SET @g1 = geometry::Parse('COMPOUNDCURVE((1 1, 1 3), (1 3, 3 3),(3 3, 3 1), (3 1, 1 1))');
SET @g2 = geometry::Parse('COMPOUNDCURVE((1 1, 1 3, 3 3, 3 1, 1 1))');
SELECT @g1.STLength(), @g2.STLength();
```

 <span data-ttu-id="07910-155">Os comprimentos de `@g1` e `@g2` são iguais.</span><span class="sxs-lookup"><span data-stu-id="07910-155">The lengths for both `@g1` and `@g2` are the same.</span></span> <span data-ttu-id="07910-156">Observe que, no exemplo, uma instância `CompoundCurve` pode armazenar uma ou mais instâncias `LineString`.</span><span class="sxs-lookup"><span data-stu-id="07910-156">Notice from the example that a `CompoundCurve` instance can store one or more instances of `LineString`.</span></span>

### <a name="e-instantiating-a-geometry-instance-using-a-compoundcurve-with-multiple-circularstrings"></a><span data-ttu-id="07910-157">E.</span><span class="sxs-lookup"><span data-stu-id="07910-157">E.</span></span> <span data-ttu-id="07910-158">Criando uma instância de geometry que usa uma CompoundCurve com várias CircularStrings</span><span class="sxs-lookup"><span data-stu-id="07910-158">Instantiating a geometry instance using a CompoundCurve with multiple CircularStrings</span></span>
 <span data-ttu-id="07910-159">O exemplo a seguir mostra como usar duas instâncias `CircularString` diferentes para inicializar uma `CompoundCurve`:</span><span class="sxs-lookup"><span data-stu-id="07910-159">The following example shows how to use two different `CircularString` instances to initialize a `CompoundCurve`.</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(0 2, 2 0, 4 2), CIRCULARSTRING(4 2, 2 4, 0 2))');
SELECT @g.STLength();
```

 <span data-ttu-id="07910-160">Isso produz a seguinte saída: 12,566370... que é o equivalente a 4&#x03c0; (4 \* PI).</span><span class="sxs-lookup"><span data-stu-id="07910-160">This produces the following output: 12.566370... which is the equivalent of 4&#x03c0; (4 \* pi).</span></span> <span data-ttu-id="07910-161">A instância `CompoundCurve` do exemplo armazena um círculo com raio 2.</span><span class="sxs-lookup"><span data-stu-id="07910-161">The `CompoundCurve` instance in the example stores a circle with a radius of 2.</span></span> <span data-ttu-id="07910-162">Os dois exemplos de código anteriores não precisavam usar uma `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="07910-162">Both of the previous code examples did not have to use a `CompoundCurve`.</span></span> <span data-ttu-id="07910-163">Teria sido mais simples usar uma instância `LineString` no primeiro exemplo e uma instância `CircularString` no segundo exemplo.</span><span class="sxs-lookup"><span data-stu-id="07910-163">For the first example a `LineString` instance would have been simpler, and a `CircularString` instance would have been simpler for the second example.</span></span> <span data-ttu-id="07910-164">Porém, o próximo exemplo mostra onde uma `CompoundCurve` oferece uma alternativa melhor.</span><span class="sxs-lookup"><span data-stu-id="07910-164">However, the next example shows where a `CompoundCurve` provides a better alternative.</span></span>

### <a name="f-using-a-compoundcurve-to-store-a-semicircle"></a><span data-ttu-id="07910-165">F.</span><span class="sxs-lookup"><span data-stu-id="07910-165">F.</span></span> <span data-ttu-id="07910-166">Usando uma CompoundCurve para armazenar um semicírculo</span><span class="sxs-lookup"><span data-stu-id="07910-166">Using a CompoundCurve to store a semicircle</span></span>
 <span data-ttu-id="07910-167">O exemplo a seguir usa uma instância `CompoundCurve` para armazenar um semicírculo.</span><span class="sxs-lookup"><span data-stu-id="07910-167">The following example uses a `CompoundCurve` instance to store a semicircle.</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(0 2, 2 0, 4 2), (4 2, 0 2))');
SELECT @g.STLength();
```

### <a name="g-storing-multiple-circularstring-and-linestring-instances-in-a-compoundcurve"></a><span data-ttu-id="07910-168">G.</span><span class="sxs-lookup"><span data-stu-id="07910-168">G.</span></span> <span data-ttu-id="07910-169">Armazenando várias instâncias CircularString e LineString em uma CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="07910-169">Storing multiple CircularString and LineString instances in a CompoundCurve</span></span>
 <span data-ttu-id="07910-170">O exemplo a seguir mostra como várias instâncias `CircularString` e `LineString` podem ser armazenadas usando uma `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="07910-170">The following example shows how multiple `CircularString` and `LineString` instances can be stored by using a `CompoundCurve`.</span></span>

```sql
DECLARE @g geometry
SET @g = geometry::Parse('COMPOUNDCURVE((3 5, 3 3), CIRCULARSTRING(3 3, 5 1, 7 3), (7 3, 7 5), CIRCULARSTRING(7 5, 5 7, 3 5))');
SELECT @g.STLength();
```

### <a name="h-storing-instances-with-z-and-m-values"></a><span data-ttu-id="07910-171">H.</span><span class="sxs-lookup"><span data-stu-id="07910-171">H.</span></span> <span data-ttu-id="07910-172">Armazenando instâncias com valores Z e M</span><span class="sxs-lookup"><span data-stu-id="07910-172">Storing instances with Z and M values</span></span>
 <span data-ttu-id="07910-173">O exemplo a seguir mostra como usar uma instância `CompoundCurve` para armazenar uma sequência de instâncias `CircularString` e `LineString` com valores Z e M.</span><span class="sxs-lookup"><span data-stu-id="07910-173">The following example shows how to use a `CompoundCurve` instance to store a sequence of `CircularString` and `LineString` instances with both Z and M values.</span></span>

```sql
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(7 5 4 2, 5 7 4 2, 3 5 4 2), (3 5 4 2, 8 7 4 2))');
```

### <a name="i-illustrating-why-circularstring-instances-must-be-explicitly-declared"></a><span data-ttu-id="07910-174">I.</span><span class="sxs-lookup"><span data-stu-id="07910-174">I.</span></span> <span data-ttu-id="07910-175">Ilustrando por que as instâncias CircularString devem ser declaradas explicitamente</span><span class="sxs-lookup"><span data-stu-id="07910-175">Illustrating why CircularString instances must be explicitly declared</span></span>
 <span data-ttu-id="07910-176">O exemplo a seguir mostra por que as instâncias `CircularString` devem ser declaradas explicitamente.</span><span class="sxs-lookup"><span data-stu-id="07910-176">The following example shows why `CircularString` instances must be explicitly declared.</span></span> <span data-ttu-id="07910-177">O programador está tentando armazenar um círculo em uma instância `CompoundCurve` .</span><span class="sxs-lookup"><span data-stu-id="07910-177">The programmer is trying to store a circle in a `CompoundCurve` instance.</span></span>

```sql
DECLARE @g1 geometry;  
DECLARE @g2 geometry;
SET @g1 = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(0 2, 2 0, 4 2), (4 2, 2 4, 0 2))');
SELECT 'Circle One', @g1.STLength() AS Perimeter;  -- gives an inaccurate amount
SET @g2 = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(0 2, 2 0, 4 2), CIRCULARSTRING(4 2, 2 4, 0 2))');
SELECT 'Circle Two', @g2.STLength() AS Perimeter;  -- now we get an accurate amount
```

 <span data-ttu-id="07910-178">A saída é da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="07910-178">The output is as follows:</span></span>

```
Circle One11.940039...
Circle Two12.566370...
```

 <span data-ttu-id="07910-179">O perímetro para o círculo dois é de aproximadamente 4&#x03c0; (4 \* PI), que é o valor real para o perímetro.</span><span class="sxs-lookup"><span data-stu-id="07910-179">The perimeter for Circle Two is approximately 4&#x03c0; (4 \* pi), which is the actual value for the perimeter.</span></span> <span data-ttu-id="07910-180">Porém, o perímetro de Circle One é significativamente inexato.</span><span class="sxs-lookup"><span data-stu-id="07910-180">However, the perimeter for Circle One is significantly inaccurate.</span></span> <span data-ttu-id="07910-181">A instância `CompoundCurve` de Circle One armazena um segmento de arco circular (ABC) e dois segmentos de linha (CD, DA).</span><span class="sxs-lookup"><span data-stu-id="07910-181">Circle One's `CompoundCurve` instance stores one circular arc segment (ABC) and two line segments (CD, DA).</span></span> <span data-ttu-id="07910-182">A instância `CompoundCurve` deve armazenar dois segmentos de arco circular (ABC, CDA) para definir um círculo.</span><span class="sxs-lookup"><span data-stu-id="07910-182">The `CompoundCurve` instance has to store two circular arc segments (ABC, CDA) to define a circle.</span></span> <span data-ttu-id="07910-183">Uma instância `LineString` define o segundo conjunto de pontos (4 2, 2 4, 0 2) na instância `CompoundCurve` de Circle One.</span><span class="sxs-lookup"><span data-stu-id="07910-183">A `LineString` instance defines the second set of points (4 2, 2 4, 0 2) in Circle One's `CompoundCurve` instance.</span></span> <span data-ttu-id="07910-184">Você deve declarar uma instância `CircularString` explicitamente dentro de uma `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="07910-184">You have to explicitly declare a `CircularString` instance inside a `CompoundCurve`.</span></span>

## <a name="see-also"></a><span data-ttu-id="07910-185">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="07910-185">See Also</span></span>
 <span data-ttu-id="07910-186">[A Preisvalid &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type) &#40;tipo de dados [Geometry&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) o tipo de dados [Geometry &#40;geometria](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type)&#41;ponto de extremidade &#40;tipo de dados [Geometry](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type)&#41;[LineString](linestring.md) [circularstring](circularstring.md) [tipos de dados espaciais](spatial-data-types-overview.md) [Point](point.md)</span><span class="sxs-lookup"><span data-stu-id="07910-186">[STIsValid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type) [STLength &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) [STStartPoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) [STEndpoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) [LineString](linestring.md) [CircularString](circularstring.md) [Spatial Data Types Overview](spatial-data-types-overview.md) [Point](point.md)</span></span>


