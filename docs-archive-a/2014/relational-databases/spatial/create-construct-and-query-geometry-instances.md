---
title: Criar, construir e consultar instâncias de geometria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- planar spatial data [SQL Server], getting started
- geometry data type [SQL Server], getting started
ms.assetid: c6b5c852-37d2-48d0-a8ad-e43bb80d6514
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 539f3f8bb1d9a1c277d6317cc571cf8bcb281833
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569861"
---
# <a name="create-construct-and-query-geometry-instances"></a><span data-ttu-id="495a0-102">Criar, construir e consultar instâncias de geometria</span><span class="sxs-lookup"><span data-stu-id="495a0-102">Create, Construct, and Query geometry Instances</span></span>
  <span data-ttu-id="495a0-103">O tipo de dados espaciais planares, `geometry`, representa dados em um sistema de coordenadas euclidiano (plano).</span><span class="sxs-lookup"><span data-stu-id="495a0-103">The planar spatial data type, `geometry`, represents data in a Euclidean (flat) coordinate system.</span></span> <span data-ttu-id="495a0-104">Este tipo é implementado como um tipo de dados CLR (Common Language Runtime) no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="495a0-104">This type is implemented as a common language runtime (CLR) data type in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="495a0-105">O tipo `geometry` é predefinido e está disponível em cada banco de dados.</span><span class="sxs-lookup"><span data-stu-id="495a0-105">The `geometry` type is predefined and available in each database.</span></span> <span data-ttu-id="495a0-106">É possível criar colunas de tabelas do tipo `geometry` e operar com dados `geometry` da mesma maneira como outros tipos CLR são usados.</span><span class="sxs-lookup"><span data-stu-id="495a0-106">You can create table columns of type `geometry` and operate on `geometry` data in the same manner as you would use other CLR types.</span></span>  
  
 <span data-ttu-id="495a0-107">O tipo de dados de `geometry` (planar) que tem suporte do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está de acordo com os Recursos Simples do Open Geospatial Consortium (OGC) para o SQL Specification versão 1.1.0.</span><span class="sxs-lookup"><span data-stu-id="495a0-107">The `geometry` data type (planar) supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conforms to the Open Geospatial Consortium (OGC) Simple Features for SQL Specification version 1.1.0.</span></span>  
  
 <span data-ttu-id="495a0-108">Para obter mais informações sobre especificações do OCG, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="495a0-108">For more information on OGC specifications, see the following:</span></span>  
  
-   [<span data-ttu-id="495a0-109">OGC Specifications, Simple Feature Access Part 1 - Common Architecture</span><span class="sxs-lookup"><span data-stu-id="495a0-109">OGC Specifications, Simple Feature Access Part 1 - Common Architecture</span></span>](https://go.microsoft.com/fwlink/?LinkId=93628)  
  
-   <span data-ttu-id="495a0-110">[Especificações do OGC, Simple Feature Access Part 2 – SQL Options](https://go.microsoft.com/fwlink/?LinkId=93629) (Acesso de recurso simples Parte 2 – opções de SQL)</span><span class="sxs-lookup"><span data-stu-id="495a0-110">[OGC Specifications, Simple Feature Access Part 2 - SQL Options](https://go.microsoft.com/fwlink/?LinkId=93629)</span></span>  
  
 <span data-ttu-id="495a0-111">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dá suporte a um subconjunto do padrão GML 3.1 existente que é definido no seguinte esquema: [https://schemas.microsoft.com/sqlserver/profiles/gml/SpatialGML.xsd](https://go.microsoft.com/fwlink/?LinkId=230959).</span><span class="sxs-lookup"><span data-stu-id="495a0-111">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supports a subset of the existing GML 3.1 standard which is defined in the following schema: [https://schemas.microsoft.com/sqlserver/profiles/gml/SpatialGML.xsd](https://go.microsoft.com/fwlink/?LinkId=230959).</span></span>  
  
##  <a name="creating-or-constructing-a-new-geometry-instance"></a><a name="creating"></a> <span data-ttu-id="495a0-112">Criando ou construindo uma nova instância de geometria</span><span class="sxs-lookup"><span data-stu-id="495a0-112">Creating or constructing a new geometry instance</span></span>  
  
###  <a name="creating-a-new-geometry-instance-from-an-existing-instance"></a><a name="existing"></a> <span data-ttu-id="495a0-113">Criando uma nova instância de geometria de uma instância existente</span><span class="sxs-lookup"><span data-stu-id="495a0-113">Creating a New geometry Instance from an Existing Instance</span></span>  
 <span data-ttu-id="495a0-114">O tipo de dados `geometry` fornece vários métodos internos que podem ser usados para criar novas instâncias de `geometry` baseadas em instâncias existentes.</span><span class="sxs-lookup"><span data-stu-id="495a0-114">The `geometry` data type provides numerous built-in methods you can use to create new `geometry` instances based on existing instances.</span></span>  
  
 <span data-ttu-id="495a0-115">**Para criar um buffer em torno de uma geometria**</span><span class="sxs-lookup"><span data-stu-id="495a0-115">**To create a buffer around a geometry**</span></span>  
 [<span data-ttu-id="495a0-116">STBuffer &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-116">STBuffer &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stbuffer-geometry-data-type)  
  
 [<span data-ttu-id="495a0-117">BufferWithTolerance &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-117">BufferWithTolerance &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/bufferwithtolerance-geometry-data-type)  
  
 <span data-ttu-id="495a0-118">**Para criar uma versão simplificada de uma geometria**</span><span class="sxs-lookup"><span data-stu-id="495a0-118">**To create a simplified version of a geometry**</span></span>  
 [<span data-ttu-id="495a0-119">Reduce &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-119">Reduce &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/reduce-geometry-data-type)  
  
 <span data-ttu-id="495a0-120">**Para cria o casco convexo de uma geometria**</span><span class="sxs-lookup"><span data-stu-id="495a0-120">**To create the convex hull of a geometry**</span></span>  
 [<span data-ttu-id="495a0-121">STConvexHull &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-121">STConvexHull &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stconvexhull-geometry-data-type)  
  
 <span data-ttu-id="495a0-122">**Para criar uma geometria da interseção de duas geometrias**</span><span class="sxs-lookup"><span data-stu-id="495a0-122">**To create a geometry from the intersection of two geometries**</span></span>  
 [<span data-ttu-id="495a0-123">STIntersection &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-123">STIntersection &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stintersection-geometry-data-type)  
  
 <span data-ttu-id="495a0-124">**Para criar uma geometria da união de duas geometrias**</span><span class="sxs-lookup"><span data-stu-id="495a0-124">**To create a geometry from the union of two geometries**</span></span>  
 [<span data-ttu-id="495a0-125">STUnion &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-125">STUnion &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stunion-geometry-data-type)  
  
 <span data-ttu-id="495a0-126">**Para criar uma geometria dos pontos onde uma geometria não sobrepõe outra**</span><span class="sxs-lookup"><span data-stu-id="495a0-126">**To create a geometry from the points where one geometry does not overlap another**</span></span>  
 [<span data-ttu-id="495a0-127">STDifference &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-127">STDifference &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stdifference-geometry-data-type)  
  
 <span data-ttu-id="495a0-128">**Para criar uma geometria dos pontos onde duas geometrias não se sobrepõem**</span><span class="sxs-lookup"><span data-stu-id="495a0-128">**To create a geometry from the points where two geometries do not overlap**</span></span>  
 [<span data-ttu-id="495a0-129">STSymDifference &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-129">STSymDifference &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stsymdifference-geometry-data-type)  
  
 <span data-ttu-id="495a0-130">**Para criar uma instância de Point arbitrária que está em uma geometria existente**</span><span class="sxs-lookup"><span data-stu-id="495a0-130">**To create an arbitrary Point instance that lies on an existing geometry**</span></span>  
 [<span data-ttu-id="495a0-131">STPointOnSurface &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-131">STPointOnSurface &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type)  
  
  
  
###  <a name="constructing-a-geometry-instance-from-well-known-text-input"></a><a name="wkt"></a> <span data-ttu-id="495a0-132">Construindo uma instância de geometria da entrada de texto conhecida</span><span class="sxs-lookup"><span data-stu-id="495a0-132">Constructing a geometry Instance from Well-Known Text Input</span></span>  
 <span data-ttu-id="495a0-133">O tipo de dados de `geometry` fornece vários métodos internos que geram uma geometria da representação WKT do Open Geospatial Consortium (OGC).</span><span class="sxs-lookup"><span data-stu-id="495a0-133">The `geometry` data type provides several built-in methods that generate a geometry from the Open Geospatial Consortium (OGC) WKT representation.</span></span> <span data-ttu-id="495a0-134">O padrão WKT é uma cadeia de caracteres de texto que permite que dados de geometria sejam trocados em formulário textual.</span><span class="sxs-lookup"><span data-stu-id="495a0-134">The WKT standard is a text string that allows geometry data to be exchanged in textual form.</span></span>  
  
 <span data-ttu-id="495a0-135">**Para construir qualquer tipo de instância de geometria de entrada WKT**</span><span class="sxs-lookup"><span data-stu-id="495a0-135">**To construct any type of geometry instance from WKT input**</span></span>  
 [<span data-ttu-id="495a0-136">STGeomFromText &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-136">STGeomFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeomfromtext-geometry-data-type)  
  
 [<span data-ttu-id="495a0-137">Parse &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-137">Parse &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/parse-geometry-data-type)  
  
 <span data-ttu-id="495a0-138">**Para construir uma instância de Point de geometria de entrada WKT**</span><span class="sxs-lookup"><span data-stu-id="495a0-138">**To construct a geometry Point instance from WKT input**</span></span>  
 [<span data-ttu-id="495a0-139">STPointFromText &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-139">STPointFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpointfromtext-geometry-data-type)  
  
 <span data-ttu-id="495a0-140">**Para construir uma instância de MultiPoint de geometria de entrada WKT**</span><span class="sxs-lookup"><span data-stu-id="495a0-140">**To construct a geometry MultiPoint instance from WKT input**</span></span>  
 [<span data-ttu-id="495a0-141">STMPointFromText &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-141">STMPointFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmpointfromtext-geometry-data-type)  
  
 <span data-ttu-id="495a0-142">**Para construir uma instância de LineString de geometria de entrada WKT**</span><span class="sxs-lookup"><span data-stu-id="495a0-142">**To construct a geometry LineString instance from WKT input**</span></span>  
 [<span data-ttu-id="495a0-143">STLineFromText &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-143">STLineFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stlinefromtext-geometry-data-type)  
  
 <span data-ttu-id="495a0-144">**Para construir uma instância de MultiLineString de geometria de entrada WKT**</span><span class="sxs-lookup"><span data-stu-id="495a0-144">**To construct a geometry MultiLineString instance from WKT input**</span></span>  
 [<span data-ttu-id="495a0-145">STMLineFromText &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-145">STMLineFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmlinefromtext-geometry-data-type)  
  
 <span data-ttu-id="495a0-146">**Para construir uma instância de Polygon de geometria de entrada WKT**</span><span class="sxs-lookup"><span data-stu-id="495a0-146">**To construct a geometry Polygon instance from WKT input**</span></span>  
 [<span data-ttu-id="495a0-147">STPolyFromText &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-147">STPolyFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpolyfromtext-geometry-data-type)  
  
 <span data-ttu-id="495a0-148">**Para construir uma instância de MultiPolygon de geometria de entrada WKT**</span><span class="sxs-lookup"><span data-stu-id="495a0-148">**To construct a geometry MultiPolygon instance from WKT input**</span></span>  
 [<span data-ttu-id="495a0-149">STMPolyFromText &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-149">STMPolyFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmpolyfromtext-geometry-data-type)  
  
 <span data-ttu-id="495a0-150">**Para construir uma instância de GeometryCollection de geometria de entrada WKT**</span><span class="sxs-lookup"><span data-stu-id="495a0-150">**To construct a geometry GeometryCollection instance from WKT input**</span></span>  
 [<span data-ttu-id="495a0-151">STGeomCollFromText &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-151">STGeomCollFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeomcollfromtext-geometry-data-type)  
  
  
  
###  <a name="constructing-a-geometry-instance-from-well-known-binary-input"></a><a name="wkb"></a> <span data-ttu-id="495a0-152">Construindo uma instância de geometria da entrada binária conhecida</span><span class="sxs-lookup"><span data-stu-id="495a0-152">Constructing a geometry Instance from Well-Known Binary Input</span></span>  
 <span data-ttu-id="495a0-153">WKB é um formato binário especificado pelo Open Geospatial Consortium (OGC) que permite que dados de `geometry` sejam trocados entre um aplicativo cliente e um banco de dados SQL.</span><span class="sxs-lookup"><span data-stu-id="495a0-153">WKB is a binary format specified by the Open Geospatial Consortium (OGC) that permits `geometry` data to be exchanged between a client application and an SQL database.</span></span> <span data-ttu-id="495a0-154">As seguintes funções aceitam entrada WKB para construir geometrias:</span><span class="sxs-lookup"><span data-stu-id="495a0-154">The following functions accept WKB input to construct geometries:</span></span>  
  
 <span data-ttu-id="495a0-155">**Para construir qualquer tipo de instância de geometria de entrada WKB**</span><span class="sxs-lookup"><span data-stu-id="495a0-155">**To construct any type of geometry instance from WKB input**</span></span>  
 [<span data-ttu-id="495a0-156">STGeomFromWKB &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-156">STGeomFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeomfromwkb-geometry-data-type)  
  
 <span data-ttu-id="495a0-157">**Para construir uma instância de Point de geometria de entrada WKB**</span><span class="sxs-lookup"><span data-stu-id="495a0-157">**To construct a geometry Point instance from WKB input**</span></span>  
 [<span data-ttu-id="495a0-158">STPointFromWKB &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-158">STPointFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpointfromwkb-geometry-data-type)  
  
 <span data-ttu-id="495a0-159">**Para construir uma instância de MultiPoint de geometria de entrada WKB**</span><span class="sxs-lookup"><span data-stu-id="495a0-159">**To construct a geometry MultiPoint instance from WKB input**</span></span>  
 [<span data-ttu-id="495a0-160">STMPointFromWKB &#40;tipo de dados de geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-160">STMPointFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmpointfromwkb-geometry-data-type)  
  
 <span data-ttu-id="495a0-161">**Para construir uma instância de LineString de geometria de entrada WKB**</span><span class="sxs-lookup"><span data-stu-id="495a0-161">**To construct a geometry LineString instance from WKB input**</span></span>  
 [<span data-ttu-id="495a0-162">STLineFromWKB &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-162">STLineFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stlinefromwkb-geometry-data-type)  
  
 <span data-ttu-id="495a0-163">**Para construir uma instância de MultiLineString de geometria de entrada WKB**</span><span class="sxs-lookup"><span data-stu-id="495a0-163">**To construct a geometry MultiLineString instance from WKB input**</span></span>  
 [<span data-ttu-id="495a0-164">STMLineFromWKB &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-164">STMLineFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmlinefromwkb-geometry-data-type)  
  
 <span data-ttu-id="495a0-165">**Para construir uma instância de Polygon de geometria de entrada WKB**</span><span class="sxs-lookup"><span data-stu-id="495a0-165">**To construct a geometry Polygon instance from WKB input**</span></span>  
 [<span data-ttu-id="495a0-166">STPolyFromWKB &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-166">STPolyFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpolyfromwkb-geometry-data-type)  
  
 <span data-ttu-id="495a0-167">**Para construir uma instância de MultiPolygon de geometria de entrada WKB**</span><span class="sxs-lookup"><span data-stu-id="495a0-167">**To construct a geometry MultiPolygon instance from WKB input**</span></span>  
 [<span data-ttu-id="495a0-168">STMPolyFromWKB &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-168">STMPolyFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmpolyfromwkb-geometry-data-type)  
  
 <span data-ttu-id="495a0-169">**Para construir uma instância de GeometryCollection de geometria de entrada WKB**</span><span class="sxs-lookup"><span data-stu-id="495a0-169">**To construct a geometry GeometryCollection instance from WKB input**</span></span>  
 [<span data-ttu-id="495a0-170">STGeomCollFromWKB &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-170">STGeomCollFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeomcollfromwkb-geometry-data-type)  
  
  
  
###  <a name="constructing-a-geometry-instance-from-gml-text-input"></a><a name="gml"></a> <span data-ttu-id="495a0-171">Construindo uma instância de geometria de entrada de texto GML</span><span class="sxs-lookup"><span data-stu-id="495a0-171">Constructing a geometry Instance from GML Text Input</span></span>  
 <span data-ttu-id="495a0-172">O `geometry` tipo de dados fornece um método que gera uma `geometry` instância de GML, uma representação XML de objetos geométricos.</span><span class="sxs-lookup"><span data-stu-id="495a0-172">The `geometry` data type provides a method that generates a `geometry` instance from GML, an XML representation of geometric objects.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="495a0-173">oferece suporte a um subconjunto de GML.</span><span class="sxs-lookup"><span data-stu-id="495a0-173">supports a subset of GML.</span></span>  
  
 <span data-ttu-id="495a0-174">**Para construir qualquer tipo de instância de geometria de entrada GML**</span><span class="sxs-lookup"><span data-stu-id="495a0-174">**To construct any type of geometry instance from GML input**</span></span>  
 [<span data-ttu-id="495a0-175">GeomFromGml &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-175">GeomFromGml &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/geomfromgml-geometry-data-type)  
  
  
  
##  <a name="returning-well-known-text-and-well-known-binary-from-a-geometry-instance"></a><a name="returning"></a> <span data-ttu-id="495a0-176">Retornando texto conhecido e binário conhecido de uma instância de geometria</span><span class="sxs-lookup"><span data-stu-id="495a0-176">Returning Well-Known Text and Well-Known Binary from a geometry Instance</span></span>  
 <span data-ttu-id="495a0-177">É possível usar os seguintes métodos para retornar o formato WKT ou WKB de uma instância de `geometry`:</span><span class="sxs-lookup"><span data-stu-id="495a0-177">You can use the following methods to return either the WKT or WKB format of a `geometry` instance:</span></span>  
  
 <span data-ttu-id="495a0-178">**Para retornar a representação WKT de uma instância de geometria**</span><span class="sxs-lookup"><span data-stu-id="495a0-178">**To return the WKT representation of a geometry instance**</span></span>  
 [<span data-ttu-id="495a0-179">STAsText &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-179">STAsText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stastext-geometry-data-type)  
  
 [<span data-ttu-id="495a0-180">ToString &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-180">ToString &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/tostring-geometry-data-type)  
  
 <span data-ttu-id="495a0-181">**Para retornar a representação WKT de uma instância de geometria incluindo qualquer valor Z e M**</span><span class="sxs-lookup"><span data-stu-id="495a0-181">**To return the WKT representation of a geometry instance including any Z and M values**</span></span>  
 [<span data-ttu-id="495a0-182">AsTextZM &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-182">AsTextZM &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/astextzm-geometry-data-type)  
  
 <span data-ttu-id="495a0-183">**Para retornar a representação WKB de uma instância de geometria**</span><span class="sxs-lookup"><span data-stu-id="495a0-183">**To return the WKB representation of a geometry instance**</span></span>  
 [<span data-ttu-id="495a0-184">STAsBinary &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-184">STAsBinary &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stasbinary-geometry-data-type)  
  
 <span data-ttu-id="495a0-185">**Para retornar uma representação GML de uma instância de geometria**</span><span class="sxs-lookup"><span data-stu-id="495a0-185">**To return a GML representation of a geometry instance**</span></span>  
 [<span data-ttu-id="495a0-186">AsGml &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-186">AsGml &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/asgml-geometry-data-type)  
  
  
  
##  <a name="querying-the-properties-and-behaviors-of-geometry-instances"></a><a name="querying"></a> <span data-ttu-id="495a0-187">Consultando as propriedades e comportamentos de instâncias de geometria</span><span class="sxs-lookup"><span data-stu-id="495a0-187">Querying the Properties and Behaviors of geometry Instances</span></span>  
 <span data-ttu-id="495a0-188">Todas as `geometry` instâncias têm várias propriedades que podem ser recuperadas por meio de métodos que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fornece.</span><span class="sxs-lookup"><span data-stu-id="495a0-188">All `geometry` instances have a number of properties that can be retrieved through methods that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides.</span></span> <span data-ttu-id="495a0-189">Os tópicos a seguir definem propriedades e comportamentos de tipos de geometria e os métodos de consulta de cada um.</span><span class="sxs-lookup"><span data-stu-id="495a0-189">The following topics define the properties and behaviors of geometry types, and the methods for querying each one.</span></span>  
  
###  <a name="validity-instance-type-and-geometrycollection-information"></a><a name="valid"></a> <span data-ttu-id="495a0-190">Informações de validade, tipo de instância e GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="495a0-190">Validity, Instance Type, and GeometryCollection Information</span></span>  
 <span data-ttu-id="495a0-191">Quando uma instância de `geometry` é construída, é possível usar os seguintes métodos para determinar se ela está bem formada, para retornar o tipo da instância ou, se ela for uma instância de coleção, retornar uma instância de `geometry` específica.</span><span class="sxs-lookup"><span data-stu-id="495a0-191">Once a `geometry` instance is constructed, you can use the following methods to determine if it is well-formed, return the instance type, or, if it is a collection instance, return a specific `geometry` instance.</span></span>  
  
 <span data-ttu-id="495a0-192">**Para retornar o tipo de instância de uma geometria**</span><span class="sxs-lookup"><span data-stu-id="495a0-192">**To return the instance type of a geometry**</span></span>  
 [<span data-ttu-id="495a0-193">STGeometryType &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-193">STGeometryType &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeometrytype-geometry-data-type)  
  
 <span data-ttu-id="495a0-194">**Para determinar se uma geometria é um determinado tipo de instância**</span><span class="sxs-lookup"><span data-stu-id="495a0-194">**To determine if a geometry is a given instance type**</span></span>  
 [<span data-ttu-id="495a0-195">InstanceOf &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-195">InstanceOf &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/instanceof-geometry-data-type)  
  
 <span data-ttu-id="495a0-196">**Para determinar se uma instância de geometria está bem formada para seu tipo de instância**</span><span class="sxs-lookup"><span data-stu-id="495a0-196">**To determine if a geometry instance is well-formed for its instance type**</span></span>  
 [<span data-ttu-id="495a0-197">STIsValid &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-197">STIsValid &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type)  
  
 <span data-ttu-id="495a0-198">**Para converter uma instância de geometria em uma instância de geometria bem formada com um tipo de instância**</span><span class="sxs-lookup"><span data-stu-id="495a0-198">**To convert a geometry instance to a well-formed geometry instance with an instance type**</span></span>  
 [<span data-ttu-id="495a0-199">MakeValid &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-199">MakeValid &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/makevalid-geometry-data-type)  
  
 <span data-ttu-id="495a0-200">**Para retornar o número de geometrias em uma instância de coleção de geometrias**</span><span class="sxs-lookup"><span data-stu-id="495a0-200">**To return the number of geometries in a geometry collection instance**</span></span>  
 [<span data-ttu-id="495a0-201">STNumGeometries &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-201">STNumGeometries &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stnumgeometries-geometry-data-type)  
  
 <span data-ttu-id="495a0-202">Para retornar uma geometria específica em uma instância coleção de geometrias</span><span class="sxs-lookup"><span data-stu-id="495a0-202">To return a specific geometry in a geometry collection instance</span></span>  
 <span data-ttu-id="495a0-203">[STGeometryN &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/stgeometryn-geometry-data-type)STGeometryN (tipo de dados geometry)</span><span class="sxs-lookup"><span data-stu-id="495a0-203">[STGeometryN &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stgeometryn-geometry-data-type)STGeometryN (geometry Data type)</span></span>  
  
  
  
###  <a name="number-of-points"></a><a name="number"></a> <span data-ttu-id="495a0-204">Número de pontos</span><span class="sxs-lookup"><span data-stu-id="495a0-204">Number of Points</span></span>  
 <span data-ttu-id="495a0-205">Todas as instâncias não vazias `geometry` são compostas de *pontos*.</span><span class="sxs-lookup"><span data-stu-id="495a0-205">All nonempty `geometry` instances are comprised of *points*.</span></span> <span data-ttu-id="495a0-206">Esses pontos representam as coordenadas X e Y do plano no qual as geometrias são obtidas.</span><span class="sxs-lookup"><span data-stu-id="495a0-206">These points represent the X- and Y-coordinates of the plane on which the geometries are drawn.</span></span> <span data-ttu-id="495a0-207">`geometry` fornece vários métodos internos de consulta de pontos de uma instância.</span><span class="sxs-lookup"><span data-stu-id="495a0-207">`geometry` provides numerous built-in methods for querying the points of an instance.</span></span>  
  
 <span data-ttu-id="495a0-208">**Para retornar o número de pontos que compõem uma instância**</span><span class="sxs-lookup"><span data-stu-id="495a0-208">**To return the number of points that comprise an instance**</span></span>  
 [<span data-ttu-id="495a0-209">STNumPoints &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-209">STNumPoints &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stnumpoints-geometry-data-type)  
  
 <span data-ttu-id="495a0-210">**Para retornar um ponto específico em uma instância**</span><span class="sxs-lookup"><span data-stu-id="495a0-210">**To return a specific point in an instance**</span></span>  
 [<span data-ttu-id="495a0-211">STPointN</span><span class="sxs-lookup"><span data-stu-id="495a0-211">STPointN</span></span>](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type)  
  
 <span data-ttu-id="495a0-212">**Para retornar um ponto arbitrário que está em uma instância**</span><span class="sxs-lookup"><span data-stu-id="495a0-212">**To return an arbitrary point that lies on an instance**</span></span>  
 [<span data-ttu-id="495a0-213">STPointOnSurface</span><span class="sxs-lookup"><span data-stu-id="495a0-213">STPointOnSurface</span></span>](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type)  
  
 <span data-ttu-id="495a0-214">**Para retornar o ponto inicial de uma instância**</span><span class="sxs-lookup"><span data-stu-id="495a0-214">**To return the start point of an instance**</span></span>  
 [<span data-ttu-id="495a0-215">STStartPoint</span><span class="sxs-lookup"><span data-stu-id="495a0-215">STStartPoint</span></span>](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type)  
  
 <span data-ttu-id="495a0-216">**Para retornar o ponto de extremidade de uma instância**</span><span class="sxs-lookup"><span data-stu-id="495a0-216">**To return the end point of an instance**</span></span>  
 [<span data-ttu-id="495a0-217">STEndpoint</span><span class="sxs-lookup"><span data-stu-id="495a0-217">STEndpoint</span></span>](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type)  
  
 <span data-ttu-id="495a0-218">**Para retornar a coordenada X de uma instância de Point**</span><span class="sxs-lookup"><span data-stu-id="495a0-218">**To return the X-coordinate of a Point instance**</span></span>  
 [<span data-ttu-id="495a0-219">STX &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-219">STX &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stx-geometry-data-type)  
  
 <span data-ttu-id="495a0-220">**Para retornar a coordenada Y de uma instância de Point**</span><span class="sxs-lookup"><span data-stu-id="495a0-220">**To return the Y-coordinate of a Point instance**</span></span>  
 [<span data-ttu-id="495a0-221">STY</span><span class="sxs-lookup"><span data-stu-id="495a0-221">STY</span></span>](/sql/t-sql/spatial-geometry/sty-geometry-data-type)  
  
 <span data-ttu-id="495a0-222">**Para retornar o ponto do centro geométrico de uma instância de Polygon, CurvePolygon ou MultiPolygon**</span><span class="sxs-lookup"><span data-stu-id="495a0-222">**To return the geometric center point of a Polygon, CurvePolygon, or MultiPolygon instance**</span></span>  
 [<span data-ttu-id="495a0-223">STCentroid</span><span class="sxs-lookup"><span data-stu-id="495a0-223">STCentroid</span></span>](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type)  
  
  
  
###  <a name="dimension"></a><a name="dimension"></a> <span data-ttu-id="495a0-224">Dimensão</span><span class="sxs-lookup"><span data-stu-id="495a0-224">Dimension</span></span>  
 <span data-ttu-id="495a0-225">Uma instância `geometry` não vazia pode ser zero, uni ou bidimensional.</span><span class="sxs-lookup"><span data-stu-id="495a0-225">A nonempty `geometry` instance can be 0-, 1-, or 2-dimensional.</span></span> <span data-ttu-id="495a0-226">`geometries` de dimensão zero, como `Point` e `MultiPoint`, não têm nenhum comprimento ou área.</span><span class="sxs-lookup"><span data-stu-id="495a0-226">Zero-dimensional `geometries`, such as `Point` and `MultiPoint`, have no length or area.</span></span> <span data-ttu-id="495a0-227">Objetos unidimensionais, como `LineString, CircularString, CompoundCurve` e `MultiLineString`, têm comprimento.</span><span class="sxs-lookup"><span data-stu-id="495a0-227">One-dimensional objects, such as `LineString, CircularString, CompoundCurve`, and `MultiLineString`, have length.</span></span> <span data-ttu-id="495a0-228">Instâncias bidimensionais, como `Polygon`, `CurvePolygon` e `MultiPolygon`, têm área e comprimento.</span><span class="sxs-lookup"><span data-stu-id="495a0-228">Two-dimensional instances, such as `Polygon`, `CurvePolygon`, and `MultiPolygon`, have area and length.</span></span> <span data-ttu-id="495a0-229">Instâncias vazias relatarão uma dimensão de -1 e uma `GeometryCollection` relatará uma área dependente dos tipos de seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="495a0-229">Empty instances will report a dimension of -1, and a `GeometryCollection` will report an area dependent on the types of its contents.</span></span>  
  
 <span data-ttu-id="495a0-230">**Para retornar a dimensão de uma instância**</span><span class="sxs-lookup"><span data-stu-id="495a0-230">**To return the dimension of an instance**</span></span>  
 [<span data-ttu-id="495a0-231">STDimension</span><span class="sxs-lookup"><span data-stu-id="495a0-231">STDimension</span></span>](/sql/t-sql/spatial-geometry/stdimension-geometry-data-type)  
  
 <span data-ttu-id="495a0-232">**Para retornar o comprimento de uma instância**</span><span class="sxs-lookup"><span data-stu-id="495a0-232">**To return the length of an instance**</span></span>  
 [<span data-ttu-id="495a0-233">STLength</span><span class="sxs-lookup"><span data-stu-id="495a0-233">STLength</span></span>](/sql/t-sql/spatial-geometry/stlength-geometry-data-type)  
  
 <span data-ttu-id="495a0-234">**Para retornar a área de uma instância**</span><span class="sxs-lookup"><span data-stu-id="495a0-234">**To return the area of an instance**</span></span>  
 [<span data-ttu-id="495a0-235">STArea</span><span class="sxs-lookup"><span data-stu-id="495a0-235">STArea</span></span>](/sql/t-sql/spatial-geometry/starea-geometry-data-type)  
  
  
  
###  <a name="empty"></a><a name="empty"></a> <span data-ttu-id="495a0-236">Empty (vazio)</span><span class="sxs-lookup"><span data-stu-id="495a0-236">Empty</span></span>  
 <span data-ttu-id="495a0-237">Uma instância *vazia* `geometry` não tem nenhum ponto.</span><span class="sxs-lookup"><span data-stu-id="495a0-237">An *empty*`geometry` instance does not have any points.</span></span> <span data-ttu-id="495a0-238">O comprimento de instâncias `LineString, CircularString`, `CompoundCurve` e `MultiLineString` é zero.</span><span class="sxs-lookup"><span data-stu-id="495a0-238">The length of empty `LineString, CircularString`, `CompoundCurve`, and `MultiLineString` instances is zero.</span></span> <span data-ttu-id="495a0-239">A área de instâncias de `Polygon`, `CurvePolygon` e `MultiPolygon` vazias é 0.</span><span class="sxs-lookup"><span data-stu-id="495a0-239">The area of empty `Polygon`, `CurvePolygon`, and `MultiPolygon` instances is 0.</span></span>  
  
 <span data-ttu-id="495a0-240">**Para determinar se uma instância está vazia**</span><span class="sxs-lookup"><span data-stu-id="495a0-240">**To determine if an instance is empty**</span></span>  
 <span data-ttu-id="495a0-241">[STIsEmpty](/sql/t-sql/spatial-geometry/stisempty-geometry-data-type).</span><span class="sxs-lookup"><span data-stu-id="495a0-241">[STIsEmpty](/sql/t-sql/spatial-geometry/stisempty-geometry-data-type).</span></span>  
  
  
  
###  <a name="simple"></a><a name="simple"></a> <span data-ttu-id="495a0-242">Simple (simples)</span><span class="sxs-lookup"><span data-stu-id="495a0-242">Simple</span></span>  
 <span data-ttu-id="495a0-243">Para que uma `geometry` das instâncias seja *simples*, ela deve atender a esses dois requisitos:</span><span class="sxs-lookup"><span data-stu-id="495a0-243">For a `geometry` of the instance to be *simple*, it must meet both of these requirements:</span></span>  
  
-   <span data-ttu-id="495a0-244">Não deve haver interseção de nenhuma figura da instância consigo mesma, exceto em seus pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="495a0-244">Each figure of the instance must not intersect itself, except at its endpoints.</span></span>  
  
-   <span data-ttu-id="495a0-245">Não pode haver nenhuma interseção entre duas figuras da instância em nenhum ponto que não esteja nos seus dois limites.</span><span class="sxs-lookup"><span data-stu-id="495a0-245">No two figures of the instance can intersect each other at a point that is not in both of their boundaries.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="495a0-246">Geometrias vazias são sempre simples.</span><span class="sxs-lookup"><span data-stu-id="495a0-246">Empty geometries are always simple.</span></span>  
  
 <span data-ttu-id="495a0-247">**Para determinar se uma instância é simples**</span><span class="sxs-lookup"><span data-stu-id="495a0-247">**To determine if an instance is simple**</span></span>  
 <span data-ttu-id="495a0-248">[STIsSimple](/sql/t-sql/spatial-geometry/stissimple-geometry-data-type).</span><span class="sxs-lookup"><span data-stu-id="495a0-248">[STIsSimple](/sql/t-sql/spatial-geometry/stissimple-geometry-data-type).</span></span>  
  
  
  
###  <a name="boundary-interior-and-exterior"></a><a name="boundary"></a> <span data-ttu-id="495a0-249">Limite, interior e exterior</span><span class="sxs-lookup"><span data-stu-id="495a0-249">Boundary, Interior, and Exterior</span></span>  
 <span data-ttu-id="495a0-250">O *interior* de uma `geometry` instância é o espaço ocupado pela instância e o *exterior* é o espaço que não o ocupa.</span><span class="sxs-lookup"><span data-stu-id="495a0-250">The *interior* of a `geometry` instance is the space occupied by the instance, and the *exterior* is the space not occupied it.</span></span>  
  
 <span data-ttu-id="495a0-251">O*Limite* é definido pelo OGC da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="495a0-251">*Boundary* is defined by the OGC as follows:</span></span>  
  
-   <span data-ttu-id="495a0-252">Instâncias de `Point` e `MultiPoint` não têm um limite.</span><span class="sxs-lookup"><span data-stu-id="495a0-252">`Point` and `MultiPoint` instances do not have a boundary.</span></span>  
  
-   <span data-ttu-id="495a0-253">Limites de `LineString` e `MultiLineString` são formados pelos pontos iniciais e de extremidade removendo os que ocorrem um número par de vezes.</span><span class="sxs-lookup"><span data-stu-id="495a0-253">`LineString` and `MultiLineString` boundaries are formed by the start points and end points, removing those that occur an even number of times.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('MULTILINESTRING((0 1, 0 0, 1 0, 0 1), (1 1, 1 0))');  
SELECT @g.STBoundary().ToString();  
```  
  
 <span data-ttu-id="495a0-254">O limite de uma instância de `Polygon` ou `MultiPolygon` é o conjunto de seus anéis.</span><span class="sxs-lookup"><span data-stu-id="495a0-254">The boundary of a `Polygon` or `MultiPolygon` instance is the set of its rings.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('POLYGON((0 0, 3 0, 3 3, 0 3, 0 0), (1 1, 1 2, 2 2, 2 1, 1 1))');  
SELECT @g.STBoundary().ToString();  
```  
  
 <span data-ttu-id="495a0-255">**Para retornar o limite de uma instância**</span><span class="sxs-lookup"><span data-stu-id="495a0-255">**To return the boundary of an instance**</span></span>  
 [<span data-ttu-id="495a0-256">STBoundary</span><span class="sxs-lookup"><span data-stu-id="495a0-256">STBoundary</span></span>](/sql/t-sql/spatial-geometry/stboundary-geometry-data-type)  
  
  
  
###  <a name="envelope"></a><a name="envelope"></a> <span data-ttu-id="495a0-257">Envelope</span><span class="sxs-lookup"><span data-stu-id="495a0-257">Envelope</span></span>  
 <span data-ttu-id="495a0-258">O *envelope* de uma `geometry` instância, também conhecido como a *caixa delimitadora*, é o retângulo alinhado ao eixo formado pelas coordenadas mínima e máxima (X, Y) da instância.</span><span class="sxs-lookup"><span data-stu-id="495a0-258">The *envelope* of a `geometry` instance, also known as the *bounding box*, is the axis-aligned rectangle formed by the minimum and maximum (X,Y) coordinates of the instance.</span></span>  
  
 <span data-ttu-id="495a0-259">**Para retornar o envelope de uma instância**</span><span class="sxs-lookup"><span data-stu-id="495a0-259">**To return the envelope of an instance**</span></span>  
 [<span data-ttu-id="495a0-260">STEnvelope</span><span class="sxs-lookup"><span data-stu-id="495a0-260">STEnvelope</span></span>](/sql/t-sql/spatial-geometry/stenvelope-geometry-data-type)  
  
  
  
###  <a name="closure"></a><a name="closure"></a> <span data-ttu-id="495a0-261">Fechamento</span><span class="sxs-lookup"><span data-stu-id="495a0-261">Closure</span></span>  
 <span data-ttu-id="495a0-262">Uma instância *fechada* `geometry` é uma figura cujos pontos inicial e final são os mesmos.</span><span class="sxs-lookup"><span data-stu-id="495a0-262">A *closed*`geometry` instance is a figure whose start points and end points are the same.</span></span> <span data-ttu-id="495a0-263">As instâncias `Polygon` são consideradas fechadas.</span><span class="sxs-lookup"><span data-stu-id="495a0-263">`Polygon` instances are considered closed.</span></span> <span data-ttu-id="495a0-264">As instâncias `Point` não estão fechadas.</span><span class="sxs-lookup"><span data-stu-id="495a0-264">`Point` instances are not closed.</span></span>  
  
 <span data-ttu-id="495a0-265">Um anel é uma instância de `LineString` simples e fechada.</span><span class="sxs-lookup"><span data-stu-id="495a0-265">A ring is a simple, closed `LineString` instance.</span></span>  
  
 <span data-ttu-id="495a0-266">**Para determinar se uma instância está fechada**</span><span class="sxs-lookup"><span data-stu-id="495a0-266">**To determine if an instance is closed**</span></span>  
 [<span data-ttu-id="495a0-267">STIsClosed</span><span class="sxs-lookup"><span data-stu-id="495a0-267">STIsClosed</span></span>](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type)  
  
 <span data-ttu-id="495a0-268">**Para determinar se uma instância é um anel**</span><span class="sxs-lookup"><span data-stu-id="495a0-268">**To determine if an instance is a ring**</span></span>  
 [<span data-ttu-id="495a0-269">STIsRing</span><span class="sxs-lookup"><span data-stu-id="495a0-269">STIsRing</span></span>](/sql/t-sql/spatial-geometry/stisring-geometry-data-type)  
  
 <span data-ttu-id="495a0-270">**Para retornar o anel exterior de uma instância de Polygon**</span><span class="sxs-lookup"><span data-stu-id="495a0-270">**To return the exterior ring of a Polygon instance**</span></span>  
 [<span data-ttu-id="495a0-271">STExteriorRing</span><span class="sxs-lookup"><span data-stu-id="495a0-271">STExteriorRing</span></span>](/sql/t-sql/spatial-geometry/stexteriorring-geometry-data-type)  
  
 <span data-ttu-id="495a0-272">**Para retornar o número de anéis interiores em um Polígono**</span><span class="sxs-lookup"><span data-stu-id="495a0-272">**To return the number of interior rings in a Polygon**</span></span>  
 [<span data-ttu-id="495a0-273">STNumInteriorRing</span><span class="sxs-lookup"><span data-stu-id="495a0-273">STNumInteriorRing</span></span>](/sql/t-sql/spatial-geometry/stnuminteriorring-geometry-data-type)  
  
 <span data-ttu-id="495a0-274">**Para retornar um anel interior especificado de um Polígono**</span><span class="sxs-lookup"><span data-stu-id="495a0-274">**To return a specified interior ring of a Polygon**</span></span>  
 [<span data-ttu-id="495a0-275">STInteriorRingN</span><span class="sxs-lookup"><span data-stu-id="495a0-275">STInteriorRingN</span></span>](/sql/t-sql/spatial-geometry/stinteriorringn-geometry-data-type)  
  
  
  
###  <a name="spatial-reference-id-srid"></a><a name="srid"></a> <span data-ttu-id="495a0-276">SRID (Spatial Reference ID)</span><span class="sxs-lookup"><span data-stu-id="495a0-276">Spatial Reference ID (SRID)</span></span>  
 <span data-ttu-id="495a0-277">A ID de referência espacial (SRID) é um identificador que especifica o sistema de coordenadas no qual a instância `geometry` é representada.</span><span class="sxs-lookup"><span data-stu-id="495a0-277">The spatial reference ID (SRID) is an identifier specifying which coordinate system the `geometry` instance is represented in.</span></span> <span data-ttu-id="495a0-278">Duas instâncias com SRIDs diferentes são incomparáveis.</span><span class="sxs-lookup"><span data-stu-id="495a0-278">Two instances with different SRIDs are incomparable.</span></span>  
  
 <span data-ttu-id="495a0-279">**Para definir ou retornar o SRID de uma instância**</span><span class="sxs-lookup"><span data-stu-id="495a0-279">**To set or return the SRID of an instance**</span></span>  
 [<span data-ttu-id="495a0-280">STSrid</span><span class="sxs-lookup"><span data-stu-id="495a0-280">STSrid</span></span>](/sql/t-sql/spatial-geometry/stsrid-geometry-data-type)  
  
 <span data-ttu-id="495a0-281">Essa propriedade pode ser modificada.</span><span class="sxs-lookup"><span data-stu-id="495a0-281">This property can be modified.</span></span>  
  
  
  
##  <a name="determining-relationships-between-geometry-instances"></a><a name="rel"></a> <span data-ttu-id="495a0-282">Determinando relações entre instâncias de geometria</span><span class="sxs-lookup"><span data-stu-id="495a0-282">Determining Relationships between geometry Instances</span></span>  
 <span data-ttu-id="495a0-283">O tipo de dados `geometry` fornece vários métodos internos que podem ser usados para determinar relações entre duas instâncias de `geometry`.</span><span class="sxs-lookup"><span data-stu-id="495a0-283">The `geometry` data type provides many built-in methods you can use to determine relationships between two `geometry` instances.</span></span>  
  
 <span data-ttu-id="495a0-284">**Para determinar se duas instâncias abrangem o mesmo conjunto de pontos**</span><span class="sxs-lookup"><span data-stu-id="495a0-284">**To determine if two instances comprise the same point set**</span></span>  
 [<span data-ttu-id="495a0-285">STEquals</span><span class="sxs-lookup"><span data-stu-id="495a0-285">STEquals</span></span>](/sql/t-sql/spatial-geometry/stequals-geometry-data-type)  
  
 <span data-ttu-id="495a0-286">**Para determinar se duas instâncias são não contíguas**</span><span class="sxs-lookup"><span data-stu-id="495a0-286">**To determine if two instances are disjoint**</span></span>  
 [<span data-ttu-id="495a0-287">STDisjoint</span><span class="sxs-lookup"><span data-stu-id="495a0-287">STDisjoint</span></span>](/sql/t-sql/spatial-geometry/stdisjoint-geometry-data-type)  
  
 <span data-ttu-id="495a0-288">**Para determinar se há interseção entre duas instâncias**</span><span class="sxs-lookup"><span data-stu-id="495a0-288">**To determine if two instances intersect**</span></span>  
 [<span data-ttu-id="495a0-289">STIntersects</span><span class="sxs-lookup"><span data-stu-id="495a0-289">STIntersects</span></span>](/sql/t-sql/spatial-geometry/stintersects-geometry-data-type)  
  
 <span data-ttu-id="495a0-290">**Para determinar se duas instâncias se tocam**</span><span class="sxs-lookup"><span data-stu-id="495a0-290">**To determine if two instances touch**</span></span>  
 [<span data-ttu-id="495a0-291">STTouches</span><span class="sxs-lookup"><span data-stu-id="495a0-291">STTouches</span></span>](/sql/t-sql/spatial-geometry/sttouches-geometry-data-type)  
  
 <span data-ttu-id="495a0-292">**Para determinar se duas instâncias se sobrepõem**</span><span class="sxs-lookup"><span data-stu-id="495a0-292">**To determine if two instances overlap**</span></span>  
 [<span data-ttu-id="495a0-293">STOverlaps</span><span class="sxs-lookup"><span data-stu-id="495a0-293">STOverlaps</span></span>](/sql/t-sql/spatial-geometry/stoverlaps-geometry-data-type)  
  
 <span data-ttu-id="495a0-294">**Para determinar se duas instâncias se cruzam**</span><span class="sxs-lookup"><span data-stu-id="495a0-294">**To determine if two instances cross**</span></span>  
 [<span data-ttu-id="495a0-295">STCrosses</span><span class="sxs-lookup"><span data-stu-id="495a0-295">STCrosses</span></span>](/sql/t-sql/spatial-geometry/stcrosses-geometry-data-type)  
  
 <span data-ttu-id="495a0-296">**Para determinar se uma instância está dentro de outra**</span><span class="sxs-lookup"><span data-stu-id="495a0-296">**To determine if one instance is within another**</span></span>  
 [<span data-ttu-id="495a0-297">STWithin</span><span class="sxs-lookup"><span data-stu-id="495a0-297">STWithin</span></span>](/sql/t-sql/spatial-geometry/stwithin-geometry-data-type)  
  
 <span data-ttu-id="495a0-298">**Para determinar se uma instância contém outra**</span><span class="sxs-lookup"><span data-stu-id="495a0-298">**To determine if one instance contains another**</span></span>  
 [<span data-ttu-id="495a0-299">STContains</span><span class="sxs-lookup"><span data-stu-id="495a0-299">STContains</span></span>](/sql/t-sql/spatial-geometry/stcontains-geometry-data-type)  
  
 <span data-ttu-id="495a0-300">**Para determinar se uma instância sobrepõe outra**</span><span class="sxs-lookup"><span data-stu-id="495a0-300">**To determine if one instance overlaps another**</span></span>  
 [<span data-ttu-id="495a0-301">STOverlaps</span><span class="sxs-lookup"><span data-stu-id="495a0-301">STOverlaps</span></span>](/sql/t-sql/spatial-geometry/stoverlaps-geometry-data-type)  
  
 <span data-ttu-id="495a0-302">**Para determinar se duas instâncias estão espacialmente relacionadas**</span><span class="sxs-lookup"><span data-stu-id="495a0-302">**To determine if two instances are spatially related**</span></span>  
 [<span data-ttu-id="495a0-303">STRelate</span><span class="sxs-lookup"><span data-stu-id="495a0-303">STRelate</span></span>](/sql/t-sql/spatial-geometry/strelate-geometry-data-type)  
  
 <span data-ttu-id="495a0-304">**Para determinar a distância mais curta entre pontos em duas instâncias de geometria**</span><span class="sxs-lookup"><span data-stu-id="495a0-304">**To determine the shortest distance between points in two geometries**</span></span>  
 [<span data-ttu-id="495a0-305">STDistance</span><span class="sxs-lookup"><span data-stu-id="495a0-305">STDistance</span></span>](/sql/t-sql/spatial-geometry/stdistance-geometry-data-type)  
  
  
  
##  <a name="geometry-instances-default-to-zero-srid"></a><a name="defaultsrid"></a> <span data-ttu-id="495a0-306">Padrão de instâncias de geometria para SRID zero</span><span class="sxs-lookup"><span data-stu-id="495a0-306">geometry Instances Default to Zero SRID</span></span>  
 <span data-ttu-id="495a0-307">O padrão de SRID para instâncias de `geometry` no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é 0.</span><span class="sxs-lookup"><span data-stu-id="495a0-307">The default SRID for `geometry` instances in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is 0.</span></span> <span data-ttu-id="495a0-308">Com dados espaciais de `geometry`, o SRID da instância espacial não é necessário para executar cálculos. Portanto as instâncias podem residir em espaço planar não definido.</span><span class="sxs-lookup"><span data-stu-id="495a0-308">With `geometry` spatial data, the specific SRID of the spatial instance is not required to perform calculations; thus, instances can reside in undefined planar space.</span></span> <span data-ttu-id="495a0-309">Para indicar espaço planar não definido nos cálculos de métodos de tipo de dados de `geometry`, o [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] usa SRID 0.</span><span class="sxs-lookup"><span data-stu-id="495a0-309">To indicate undefined planar space in the calculations of `geometry` data type methods, the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] uses SRID 0.</span></span>  
  
##  <a name="examples"></a><a name="examples"></a> <span data-ttu-id="495a0-310">Exemplos</span><span class="sxs-lookup"><span data-stu-id="495a0-310">Examples</span></span>  
 <span data-ttu-id="495a0-311">Os dois exemplos a seguir mostram como adicionar e consultar dados geométricos.</span><span class="sxs-lookup"><span data-stu-id="495a0-311">The following two examples show how to add and query geometry data.</span></span>  
  
-   <span data-ttu-id="495a0-312">O primeiro exemplo cria uma tabela com uma coluna de identidade e uma coluna de `geometry``GeomCol1`.</span><span class="sxs-lookup"><span data-stu-id="495a0-312">The first example creates a table with an identity column and a `geometry` column `GeomCol1`.</span></span> <span data-ttu-id="495a0-313">Uma terceira coluna renderiza a coluna de `geometry` em sua representação WKT (Well-Known Text) do Open Geospatial Consortium (OGC) e usa o método `STAsText()` .</span><span class="sxs-lookup"><span data-stu-id="495a0-313">A third column renders the `geometry` column into its Open Geospatial Consortium (OGC) Well-Known Text (WKT) representation, and uses the `STAsText()` method.</span></span> <span data-ttu-id="495a0-314">Em seguida, duas linhas são inseridas: uma linha que contém uma instância `LineString` de `geometry`e uma linha que contém uma instância de `Polygon` .</span><span class="sxs-lookup"><span data-stu-id="495a0-314">Two rows are then inserted: one row contains a `LineString` instance of `geometry`, and one row contains a `Polygon` instance.</span></span>  
  
    ```  
    IF OBJECT_ID ( 'dbo.SpatialTable', 'U' ) IS NOT NULL   
        DROP TABLE dbo.SpatialTable;  
    GO  
  
    CREATE TABLE SpatialTable   
        ( id int IDENTITY (1,1),  
        GeomCol1 geometry,   
        GeomCol2 AS GeomCol1.STAsText() );  
    GO  
  
    INSERT INTO SpatialTable (GeomCol1)  
    VALUES (geometry::STGeomFromText('LINESTRING (100 100, 20 180, 180 180)', 0));  
  
    INSERT INTO SpatialTable (GeomCol1)  
    VALUES (geometry::STGeomFromText('POLYGON ((0 0, 150 0, 150 150, 0 150, 0 0))', 0));  
    GO  
    ```  
  
-   <span data-ttu-id="495a0-315">O segundo exemplo usa o método `STIntersection()` para retornar os pontos onde as duas instâncias de `geometry` inseridas anteriormente se cruzam.</span><span class="sxs-lookup"><span data-stu-id="495a0-315">The second example uses the `STIntersection()` method to return the points where the two previously inserted `geometry` instances intersect.</span></span>  
  
    ```  
    DECLARE @geom1 geometry;  
    DECLARE @geom2 geometry;  
    DECLARE @result geometry;  
  
    SELECT @geom1 = GeomCol1 FROM SpatialTable WHERE id = 1;  
    SELECT @geom2 = GeomCol1 FROM SpatialTable WHERE id = 2;  
    SELECT @result = @geom1.STIntersection(@geom2);  
    SELECT @result.STAsText();  
    ```  
  
  
  
## <a name="see-also"></a><span data-ttu-id="495a0-316">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="495a0-316">See Also</span></span>  
 [<span data-ttu-id="495a0-317">Dados espaciais &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="495a0-317">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
