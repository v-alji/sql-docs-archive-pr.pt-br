---
title: Criar, construir e consultar instâncias de geografia | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- geography data type [SQL Server]
- geodetic data type [SQL Server]
- geography data type [SQL Server], about geography data type
ms.assetid: b585851e-d15b-411f-adeb-aeabeb777c0b
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: d744457cc517a6172cca96b27eae1f456deca24e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569863"
---
# <a name="create-construct-and-query-geography-instances"></a><span data-ttu-id="d9cef-102">Criar, construir e consultar instâncias de geografia</span><span class="sxs-lookup"><span data-stu-id="d9cef-102">Create, Construct, and Query geography Instances</span></span>
  <span data-ttu-id="d9cef-103">O tipo de dados espacial de geografia, `geography`, representa dados em um sistema de coordenadas de terra redonda.</span><span class="sxs-lookup"><span data-stu-id="d9cef-103">The geography spatial data type, `geography`, represents data in a round-earth coordinate system.</span></span> <span data-ttu-id="d9cef-104">Este tipo é implementado como um tipo de dados CLR (Common Language Runtime) .NET no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9cef-104">This type is implemented as a .NET common language runtime (CLR) data type in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d9cef-105">O tipo de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `geography` armazena dados elipsoidais (globo terrestre), como as coordenadas de latitude e longitude de GPS.</span><span class="sxs-lookup"><span data-stu-id="d9cef-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `geography` data type stores ellipsoidal (round-earth) data, such as GPS latitude and longitude coordinates.</span></span>  
  
 <span data-ttu-id="d9cef-106">O tipo `geography` é predefinido e está disponível em cada banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d9cef-106">The `geography` type is predefined and available in each database.</span></span> <span data-ttu-id="d9cef-107">É possível criar colunas de tabelas do tipo `geography` e operar em dados de `geography` da mesma maneira como outros tipos fornecidos pelo sistema são usados.</span><span class="sxs-lookup"><span data-stu-id="d9cef-107">You can create table columns of type `geography` and operate on `geography` data in the same manner as you would use other system-supplied types.</span></span>  
  
##  <a name="creating-or-constructing-a-new-geography-instance"></a><a name="creating"></a> <span data-ttu-id="d9cef-108">Criando ou construindo uma nova instância de geografia</span><span class="sxs-lookup"><span data-stu-id="d9cef-108">Creating or constructing a new geography instance</span></span>  
  
###  <a name="creating-a-new-geography-instance-from-an-existing-instance"></a><a name="existing"></a> <span data-ttu-id="d9cef-109">Criando uma nova instância de geografia de uma instância existente</span><span class="sxs-lookup"><span data-stu-id="d9cef-109">Creating a New geography Instance from an Existing Instance</span></span>  
 <span data-ttu-id="d9cef-110">O tipo de dados `geography` fornece vários métodos internos que podem ser usados para criar novas instâncias de `geography` baseadas em instâncias existentes.</span><span class="sxs-lookup"><span data-stu-id="d9cef-110">The `geography` data type provides numerous built-in methods you can use to create new `geography` instances based on existing instances.</span></span>  
  
 <span data-ttu-id="d9cef-111">**Para criar um buffer em torno de uma geografia**</span><span class="sxs-lookup"><span data-stu-id="d9cef-111">**To create a buffer around a geography**</span></span>  
 [<span data-ttu-id="d9cef-112">STBuffer &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-112">STBuffer &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stbuffer-geography-data-type)  
  
 <span data-ttu-id="d9cef-113">**Para criar um buffer em torno de uma geografia, permitindo uma tolerância**</span><span class="sxs-lookup"><span data-stu-id="d9cef-113">**To create a buffer around a geography, allowing for a tolerance**</span></span>  
 [<span data-ttu-id="d9cef-114">BufferWithTolerance &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-114">BufferWithTolerance &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/bufferwithtolerance-geography-data-type)  
  
 <span data-ttu-id="d9cef-115">**Para criar uma geografia da interseção de duas instâncias de geografia**</span><span class="sxs-lookup"><span data-stu-id="d9cef-115">**To create a geography from the intersection of two geography instances**</span></span>  
 [<span data-ttu-id="d9cef-116">STIntersection &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-116">STIntersection &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stintersection-geography-data-type)  
  
 <span data-ttu-id="d9cef-117">**Para criar uma geografia da união de duas instâncias de geografia**</span><span class="sxs-lookup"><span data-stu-id="d9cef-117">**To create a geography from the union of two geography instances**</span></span>  
 [<span data-ttu-id="d9cef-118">STUnion &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-118">STUnion &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stunion-geography-data-type)  
  
 <span data-ttu-id="d9cef-119">**Para criar uma geografia dos pontos onde uma geografia não sobrepõe outra**</span><span class="sxs-lookup"><span data-stu-id="d9cef-119">**To create a geography from the points where one geography does not overlap another**</span></span>  
 [<span data-ttu-id="d9cef-120">STDifference &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-120">STDifference &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stdifference-geography-data-type)  
  
###  <a name="constructing-a-geography-instance-from-well-known-text-input"></a><a name="wkt"></a> <span data-ttu-id="d9cef-121">Construindo uma instância de geografia da entrada de texto conhecida</span><span class="sxs-lookup"><span data-stu-id="d9cef-121">Constructing a geography Instance from Well-Known Text Input</span></span>  
 <span data-ttu-id="d9cef-122">O tipo de dados de `geography` fornece vários métodos internos que geram uma geografia da representação WKT do Open Geospatial Consortium (OGC).</span><span class="sxs-lookup"><span data-stu-id="d9cef-122">The `geography` data type provides several built-in methods that generate a geography from the Open Geospatial Consortium (OGC) WKT representation.</span></span> <span data-ttu-id="d9cef-123">O padrão WKT é uma cadeia de caracteres de texto que permite que dados de geografia sejam trocados em formulário textual.</span><span class="sxs-lookup"><span data-stu-id="d9cef-123">The WKT standard is a text string that allows geography data to be exchanged in textual form.</span></span>  
  
 <span data-ttu-id="d9cef-124">**Para construir qualquer tipo de instância de geografia de entrada WKT**</span><span class="sxs-lookup"><span data-stu-id="d9cef-124">**To construct any type of geography instance from WKT input**</span></span>  
 [<span data-ttu-id="d9cef-125">STGeomFromText &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-125">STGeomFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stgeomfromtext-geography-data-type)  
  
 [<span data-ttu-id="d9cef-126">Parse &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-126">Parse &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/parse-geography-data-type)  
  
 <span data-ttu-id="d9cef-127">**Para construir uma instância de Point de geografia de entrada WKT**</span><span class="sxs-lookup"><span data-stu-id="d9cef-127">**To construct a geography Point instance from WKT input**</span></span>  
 [<span data-ttu-id="d9cef-128">STPointFromText &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-128">STPointFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stpointfromtext-geography-data-type)  
  
 <span data-ttu-id="d9cef-129">**Para construir uma instância de MultiPoint de geografia de entrada WKT**</span><span class="sxs-lookup"><span data-stu-id="d9cef-129">**To construct a geography MultiPoint instance from WKT input**</span></span>  
 [<span data-ttu-id="d9cef-130">STMPointFromText &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-130">STMPointFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmpointfromtext-geography-data-type)  
  
 <span data-ttu-id="d9cef-131">**Para construir uma instância de LineString de geografia de entrada WKT**</span><span class="sxs-lookup"><span data-stu-id="d9cef-131">**To construct a geography LineString instance from WKT input**</span></span>  
 <span data-ttu-id="d9cef-132">STLineFromText (tipo de dados de geografia)</span><span class="sxs-lookup"><span data-stu-id="d9cef-132">STLineFromText (geography Data Type)</span></span>  
  
 <span data-ttu-id="d9cef-133">**Para construir uma instância de MultiLineString de geografia de entrada WKT**</span><span class="sxs-lookup"><span data-stu-id="d9cef-133">**To construct a geography MultiLineString instance from WKT input**</span></span>  
 [<span data-ttu-id="d9cef-134">STMLineFromText &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-134">STMLineFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmlinefromtext-geography-data-type)  
  
 <span data-ttu-id="d9cef-135">**Para construir uma instância de Polygon de geografia de entrada WKT**</span><span class="sxs-lookup"><span data-stu-id="d9cef-135">**To construct a geography Polygon instance from WKT input**</span></span>  
 [<span data-ttu-id="d9cef-136">STPolyFromText &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-136">STPolyFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stpolyfromtext-geography-data-type)  
  
 <span data-ttu-id="d9cef-137">**Para construir uma instância de MultiPolygon de geografia de entrada WKT**</span><span class="sxs-lookup"><span data-stu-id="d9cef-137">**To construct a geography MultiPolygon instance from WKT input**</span></span>  
 [<span data-ttu-id="d9cef-138">STMPolyFromText &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-138">STMPolyFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmpolyfromtext-geography-data-type)  
  
 <span data-ttu-id="d9cef-139">**Para construir uma instância de GeometryCollection de geografia de entrada WKT**</span><span class="sxs-lookup"><span data-stu-id="d9cef-139">**To construct a geography GeometryCollection instance from WKT input**</span></span>  
 [<span data-ttu-id="d9cef-140">STGeomCollFromText &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-140">STGeomCollFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stgeomcollfromtext-geography-data-type)  
  
###  <a name="constructing-a-geography-instance-from-well-known-binary-input"></a><a name="wkb"></a> <span data-ttu-id="d9cef-141">Construindo uma instância de geografia da entrada binária conhecida</span><span class="sxs-lookup"><span data-stu-id="d9cef-141">Constructing a geography Instance from Well-Known Binary Input</span></span>  
 <span data-ttu-id="d9cef-142">WKB é um formato binário especificado pelo OGC que permite que dados de `Geography` sejam trocados entre um aplicativo cliente e um banco de dados SQL.</span><span class="sxs-lookup"><span data-stu-id="d9cef-142">WKB is a binary format specified by the OGC that permits `Geography` data to be exchanged between a client application and an SQL database.</span></span> <span data-ttu-id="d9cef-143">As seguintes funções aceitam entrada WKB para construir instâncias de geografia:</span><span class="sxs-lookup"><span data-stu-id="d9cef-143">The following functions accept WKB input to construct geography instances:</span></span>  
  
 <span data-ttu-id="d9cef-144">**Para construir qualquer tipo de instância de geografia de entrada WKB**</span><span class="sxs-lookup"><span data-stu-id="d9cef-144">**To construct any type of geography instance from WKB input**</span></span>  
 [<span data-ttu-id="d9cef-145">STGeomFromWKB &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-145">STGeomFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stgeomfromwkb-geography-data-type)  
  
 <span data-ttu-id="d9cef-146">**Para construir uma instância de Point de geografia de entrada WKB**</span><span class="sxs-lookup"><span data-stu-id="d9cef-146">**To construct a geography Point instance from WKB input**</span></span>  
 [<span data-ttu-id="d9cef-147">STPointFromWKB &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-147">STPointFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stpointfromwkb-geography-data-type)  
  
 <span data-ttu-id="d9cef-148">**Para construir uma instância de MultiPoint de geografia de entrada WKB**</span><span class="sxs-lookup"><span data-stu-id="d9cef-148">**To construct a geography MultiPoint instance from WKB input**</span></span>  
 [<span data-ttu-id="d9cef-149">STMPointFromWKB &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-149">STMPointFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmpointfromwkb-geography-data-type)  
  
 <span data-ttu-id="d9cef-150">**Para construir uma instância de LineString de geografia de entrada WKB**</span><span class="sxs-lookup"><span data-stu-id="d9cef-150">**To construct a geography LineString instance from WKB input**</span></span>  
 [<span data-ttu-id="d9cef-151">STLineFromWKB &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-151">STLineFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stlinefromwkb-geography-data-type)  
  
 <span data-ttu-id="d9cef-152">**Para construir uma instância de MultiLineString de geografia de entrada WKB**</span><span class="sxs-lookup"><span data-stu-id="d9cef-152">**To construct a geography MultiLineString instance from WKB input**</span></span>  
 [<span data-ttu-id="d9cef-153">STMLineFromWKB &#40;Tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-153">STMLineFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmlinefromwkb-geography-data-type)  
  
 <span data-ttu-id="d9cef-154">**Para construir uma instância de Polygon de geografia de entrada WKB**</span><span class="sxs-lookup"><span data-stu-id="d9cef-154">**To construct a geography Polygon instance from WKB input**</span></span>  
 [<span data-ttu-id="d9cef-155">STPolyFromWKB &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-155">STPolyFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stpolyfromwkb-geography-data-type)  
  
 <span data-ttu-id="d9cef-156">**Para construir uma instância de MultiPolygon de geografia de entrada WKB**</span><span class="sxs-lookup"><span data-stu-id="d9cef-156">**To construct a geography MultiPolygon instance from WKB input**</span></span>  
 [<span data-ttu-id="d9cef-157">STMPolyFromWKB &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-157">STMPolyFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmpolyfromwkb-geography-data-type)  
  
 <span data-ttu-id="d9cef-158">**Para construir uma instância de GeometryCollection de geografia de entrada WKB**</span><span class="sxs-lookup"><span data-stu-id="d9cef-158">**To construct a geography GeometryCollection instance from WKB input**</span></span>  
 <span data-ttu-id="d9cef-159">[STGeomCollFromWKB &#40;tipo de dados geography&#41;](/sql/t-sql/spatial-geography/stgeomcollfromwkb-geography-data-type)STGeomCollFromWKB (tipo de dados geography)</span><span class="sxs-lookup"><span data-stu-id="d9cef-159">[STGeomCollFromWKB &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stgeomcollfromwkb-geography-data-type)STGeomCollFromWKB (geography Data Type)</span></span>  
  
###  <a name="constructing-a-geography-instance-from-gml-text-input"></a><a name="gml"></a> <span data-ttu-id="d9cef-160">Construindo uma instância de geografia de entrada de texto GML</span><span class="sxs-lookup"><span data-stu-id="d9cef-160">Constructing a geography Instance from GML Text Input</span></span>  
 <span data-ttu-id="d9cef-161">O `geography` tipo de dados fornece um método que gera uma `geography` instância de GML, uma representação XML de uma `geography` instância.</span><span class="sxs-lookup"><span data-stu-id="d9cef-161">The `geography` data type provides a method that generates a `geography` instance from GML, an XML representation of a `geography` instance.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d9cef-162">oferece suporte a um subconjunto de GML.</span><span class="sxs-lookup"><span data-stu-id="d9cef-162">supports a subset of GML.</span></span>  
  
 <span data-ttu-id="d9cef-163">Para obter mais informações sobre Geography Markup Language, veja a Especificação do OGC: [OGC Specifications, Geography Markup Language.](https://go.microsoft.com/fwlink/?LinkId=93629)</span><span class="sxs-lookup"><span data-stu-id="d9cef-163">For more information on Geography Markup Language, see the OGC Specification: [OGC Specifications, Geography Markup Language.](https://go.microsoft.com/fwlink/?LinkId=93629)</span></span>  
  
 <span data-ttu-id="d9cef-164">**Para construir qualquer tipo de instância de geografia de entrada GML**</span><span class="sxs-lookup"><span data-stu-id="d9cef-164">**To construct any type of geography instance from GML input**</span></span>  
 [<span data-ttu-id="d9cef-165">GeomFromGML &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-165">GeomFromGML &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/geomfromgml-geography-data-type)  
  
##  <a name="returning-well-known-text-and-well-known-binary-from-a-geography-instance"></a><a name="returning"></a> <span data-ttu-id="d9cef-166">Retornando Well-Known Text e Well-Known Binary de uma instância de geografia</span><span class="sxs-lookup"><span data-stu-id="d9cef-166">Returning Well-Known Text and Well-Known Binary from a geography Instance</span></span>  
 <span data-ttu-id="d9cef-167">É possível usar os seguintes métodos para retornar o formato WKT ou WKB de uma instância de `geography`:</span><span class="sxs-lookup"><span data-stu-id="d9cef-167">You can use the following methods to return either the WKT or WKB format of a `geography` instance:</span></span>  
  
 <span data-ttu-id="d9cef-168">**Para retornar a representação WKT de uma instância de geografia**</span><span class="sxs-lookup"><span data-stu-id="d9cef-168">**To return the WKT representation of a geography instance**</span></span>  
 [<span data-ttu-id="d9cef-169">STAsText &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-169">STAsText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stastext-geography-data-type)  
  
 [<span data-ttu-id="d9cef-170">ToString &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-170">ToString &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/tostring-geography-data-type)  
  
 <span data-ttu-id="d9cef-171">**Para retornar a representação WKT de uma instância de geometria incluindo qualquer valor Z e M**</span><span class="sxs-lookup"><span data-stu-id="d9cef-171">**To return the WKT representation of a geography instance including any Z and M values**</span></span>  
 [<span data-ttu-id="d9cef-172">AsTextZM &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-172">AsTextZM &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/astextzm-geography-data-type)  
  
 <span data-ttu-id="d9cef-173">**Para retornar a representação WKB de uma instância de geografia**</span><span class="sxs-lookup"><span data-stu-id="d9cef-173">**To return the WKB representation of a geography instance**</span></span>  
 [<span data-ttu-id="d9cef-174">STAsBinary &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-174">STAsBinary &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stasbinary-geography-data-type)  
  
 <span data-ttu-id="d9cef-175">**Para retornar a representação GML de uma instância de geografia**</span><span class="sxs-lookup"><span data-stu-id="d9cef-175">**To return a GML representation of a geography instance**</span></span>  
 [<span data-ttu-id="d9cef-176">AsGml &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-176">AsGml &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/asgml-geography-data-type)  
  
##  <a name="querying-the-properties-and-behaviors-of-geography-instances"></a><a name="query"></a> <span data-ttu-id="d9cef-177">Consultando as propriedades e comportamentos de instâncias de geografia</span><span class="sxs-lookup"><span data-stu-id="d9cef-177">Querying the Properties and Behaviors of geography Instances</span></span>  
 <span data-ttu-id="d9cef-178">Todas as `geography` instâncias têm várias propriedades que podem ser recuperadas por meio de métodos que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fornece.</span><span class="sxs-lookup"><span data-stu-id="d9cef-178">All `geography` instances have a number of properties that can be retrieved through methods that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides.</span></span> <span data-ttu-id="d9cef-179">Os tópicos a seguir definem as propriedades e comportamentos de tipos de geografia e os métodos de consulta de cada um.</span><span class="sxs-lookup"><span data-stu-id="d9cef-179">The following topics define the properties and behaviors of geography types, and the methods for querying each one.</span></span>  
  
###  <a name="validity-instance-type-and-geometrycollection-information"></a><a name="valid"></a> <span data-ttu-id="d9cef-180">Informações de validade, tipo de instância e GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="d9cef-180">Validity, Instance Type, and GeometryCollection Information</span></span>  
 <span data-ttu-id="d9cef-181">Depois `geography` que uma instância é construída, você pode usar os métodos a seguir para retornar o tipo de instância ou, se for uma `GeometryCollection` instância, retornar uma `geography` instância específica.</span><span class="sxs-lookup"><span data-stu-id="d9cef-181">After a `geography` instance is constructed, you can use the following methods to return the instance type, or if it is a `GeometryCollection` instance, return a specific `geography` instance.</span></span>  
  
 <span data-ttu-id="d9cef-182">**Para retornar o tipo de instância de uma geografia**</span><span class="sxs-lookup"><span data-stu-id="d9cef-182">**To return the instance type of a geography**</span></span>  
 [<span data-ttu-id="d9cef-183">STGeometryType &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-183">STGeometryType &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stgeometrytype-geography-data-type)  
  
 <span data-ttu-id="d9cef-184">**Para determinar se uma geografia é um determinado tipo de instância**</span><span class="sxs-lookup"><span data-stu-id="d9cef-184">**To determine if a geography is a given instance type**</span></span>  
 [<span data-ttu-id="d9cef-185">InstanceOf &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-185">InstanceOf &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/instanceof-geography-data-type)  
  
 <span data-ttu-id="d9cef-186">**Para determinar se uma instância de geografia é bem formada para seu tipo de instância**</span><span class="sxs-lookup"><span data-stu-id="d9cef-186">**To determine if a geography instance is well-formed for its instance type**</span></span>  
 [<span data-ttu-id="d9cef-187">STNumGeometries &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-187">STNumGeometries &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stnumgeometries-geography-data-type)  
  
 <span data-ttu-id="d9cef-188">**Para retornar uma geografia específica em uma instância GeometryCollection**</span><span class="sxs-lookup"><span data-stu-id="d9cef-188">**To return a specific geography in a GeometryCollection instance**</span></span>  
 <span data-ttu-id="d9cef-189">[STGeometryN &#40;tipo de dados geography&#41;](/sql/t-sql/spatial-geography/stgeometryn-geography-data-type)STGeometryN (tipo de dados geography)</span><span class="sxs-lookup"><span data-stu-id="d9cef-189">[STGeometryN &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stgeometryn-geography-data-type)STGeometryN (geography Data Type)</span></span>  
  
###  <a name="number-of-points"></a><a name="number"></a> <span data-ttu-id="d9cef-190">Número de pontos</span><span class="sxs-lookup"><span data-stu-id="d9cef-190">Number of Points</span></span>  
 <span data-ttu-id="d9cef-191">Todas as instâncias não vazias `geography` são compostas de *pontos*.</span><span class="sxs-lookup"><span data-stu-id="d9cef-191">All nonempty `geography` instances are comprised of *points*.</span></span> <span data-ttu-id="d9cef-192">Esses pontos representam as coordenadas de latitude e longitude da terra nas quais as instâncias de `geography` são obtidas.</span><span class="sxs-lookup"><span data-stu-id="d9cef-192">These points represent the latitude and longitude coordinates of the earth on which the `geography` instances are drawn.</span></span> <span data-ttu-id="d9cef-193">O tipo de dados `geography` fornece vários métodos internos de consulta de pontos de uma instância.</span><span class="sxs-lookup"><span data-stu-id="d9cef-193">The data type `geography` provides numerous built-in methods for querying the points of an instance.</span></span>  
  
 <span data-ttu-id="d9cef-194">**Para retornar o número de pontos que compõem uma instância**</span><span class="sxs-lookup"><span data-stu-id="d9cef-194">**To return the number of points that comprise an instance**</span></span>  
 [<span data-ttu-id="d9cef-195">STNumPoints &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-195">STNumPoints &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stnumpoints-geography-data-type)  
  
 <span data-ttu-id="d9cef-196">**Para retornar um ponto específico em uma instância**</span><span class="sxs-lookup"><span data-stu-id="d9cef-196">**To return a specific point in an instance**</span></span>  
 [<span data-ttu-id="d9cef-197">STPointN &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-197">STPointN &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type)  
  
 <span data-ttu-id="d9cef-198">**Para retornar o ponto inicial de uma instância**</span><span class="sxs-lookup"><span data-stu-id="d9cef-198">**To return the start point of an instance**</span></span>  
 [<span data-ttu-id="d9cef-199">STStartPoint &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-199">STStartPoint &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/ststartpoint-geography-data-type)  
  
 <span data-ttu-id="d9cef-200">**Para retornar o ponto de extremidade de uma instância**</span><span class="sxs-lookup"><span data-stu-id="d9cef-200">**To return the end point of an instance**</span></span>  
 [<span data-ttu-id="d9cef-201">STEndpoint &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-201">STEndpoint &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stendpoint-geography-data-type)  
  
###  <a name="dimension"></a><a name="dimension"></a> <span data-ttu-id="d9cef-202">Dimensão</span><span class="sxs-lookup"><span data-stu-id="d9cef-202">Dimension</span></span>  
 <span data-ttu-id="d9cef-203">Uma instância `geography` não vazia pode ser zero, uni ou bidimensional.</span><span class="sxs-lookup"><span data-stu-id="d9cef-203">A nonempty `geography` instance can be 0-, 1-, or 2-dimensional.</span></span> <span data-ttu-id="d9cef-204">Instâncias com dimensões zero `geography` , como `Point` e `MultiPoint` , não têm comprimento ou área.</span><span class="sxs-lookup"><span data-stu-id="d9cef-204">Zero-dimensional `geography` instances, such as `Point` and `MultiPoint`, have no length or area.</span></span> <span data-ttu-id="d9cef-205">Objetos unidimensionais, como `LineString, CircularString`, `CompoundCurve` e `MultiLineString`, têm comprimento.</span><span class="sxs-lookup"><span data-stu-id="d9cef-205">One-dimensional objects, such as `LineString, CircularString`, `CompoundCurve`, and `MultiLineString`, have length.</span></span> <span data-ttu-id="d9cef-206">Instâncias bidimensionais, como `Polygon, CurvePolygon` , e `MultiPolygon` têm área e comprimento.</span><span class="sxs-lookup"><span data-stu-id="d9cef-206">Two-dimensional instances, such as `Polygon, CurvePolygon`, and `MultiPolygon`, have area and length.</span></span> <span data-ttu-id="d9cef-207">Instâncias vazias relatam uma dimensão de -1 e uma `GeometryCollection` relata a dimensão máxima de seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="d9cef-207">Empty instances report a dimension of -1, and a `GeometryCollection` reports the maximum dimension of its contents.</span></span>  
  
 <span data-ttu-id="d9cef-208">**Para retornar a dimensão de uma instância**</span><span class="sxs-lookup"><span data-stu-id="d9cef-208">**To return the dimension of an instance**</span></span>  
 [<span data-ttu-id="d9cef-209">STDimension &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-209">STDimension &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stdimension-geography-data-type)  
  
 <span data-ttu-id="d9cef-210">**Para retornar o comprimento de uma instância**</span><span class="sxs-lookup"><span data-stu-id="d9cef-210">**To return the length of an instance**</span></span>  
 [<span data-ttu-id="d9cef-211">STLength &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-211">STLength &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stlength-geography-data-type)  
  
 <span data-ttu-id="d9cef-212">**Para retornar a área de uma instância**</span><span class="sxs-lookup"><span data-stu-id="d9cef-212">**To return the area of an instance**</span></span>  
 [<span data-ttu-id="d9cef-213">STArea &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-213">STArea &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/starea-geography-data-type)  
  
###  <a name="empty"></a><a name="empty"></a> <span data-ttu-id="d9cef-214">Empty (vazio)</span><span class="sxs-lookup"><span data-stu-id="d9cef-214">Empty</span></span>  
 <span data-ttu-id="d9cef-215">Uma instância *vazia* `geography` não tem nenhum ponto.</span><span class="sxs-lookup"><span data-stu-id="d9cef-215">An *empty*`geography` instance does not have any points.</span></span> <span data-ttu-id="d9cef-216">O comprimento de instâncias de `LineString, CircularString`, `CompoundCurve` e `MultiLineString` vazias é 0.</span><span class="sxs-lookup"><span data-stu-id="d9cef-216">The length of empty `LineString, CircularString`, `CompoundCurve`, and `MultiLineString` instances is 0.</span></span> <span data-ttu-id="d9cef-217">A área de instâncias `Polygon, CurvePolygon` e `MultiPolygon` vazias é 0.</span><span class="sxs-lookup"><span data-stu-id="d9cef-217">The area of empty `Polygon, CurvePolygon` and `MultiPolygon` instances is 0.</span></span>  
  
 <span data-ttu-id="d9cef-218">**Para determinar se uma instância está vazia**</span><span class="sxs-lookup"><span data-stu-id="d9cef-218">**To determine if an instance is empty**</span></span>  
 [<span data-ttu-id="d9cef-219">STIsEmpty &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-219">STIsEmpty &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stisempty-geography-data-type)  
  
###  <a name="closure"></a><a name="closure"></a> <span data-ttu-id="d9cef-220">Fechamento</span><span class="sxs-lookup"><span data-stu-id="d9cef-220">Closure</span></span>  
 <span data-ttu-id="d9cef-221">Uma instância *fechada* `geography` é uma figura cujos pontos inicial e final são os mesmos.</span><span class="sxs-lookup"><span data-stu-id="d9cef-221">A *closed*`geography` instance is a figure whose start points and end points are the same.</span></span> <span data-ttu-id="d9cef-222">As instâncias `Polygon` são consideradas fechadas.</span><span class="sxs-lookup"><span data-stu-id="d9cef-222">`Polygon` instances are considered closed.</span></span> <span data-ttu-id="d9cef-223">As instâncias `Point` não estão fechadas.</span><span class="sxs-lookup"><span data-stu-id="d9cef-223">`Point` instances are not closed.</span></span>  
  
 <span data-ttu-id="d9cef-224">Um anel é uma instância de `LineString` simples e fechada.</span><span class="sxs-lookup"><span data-stu-id="d9cef-224">A ring is a simple, closed `LineString` instance.</span></span>  
  
 <span data-ttu-id="d9cef-225">**Para determinar se uma instância está fechada**</span><span class="sxs-lookup"><span data-stu-id="d9cef-225">**To determine if an instance is closed**</span></span>  
 [<span data-ttu-id="d9cef-226">STIsClosed &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-226">STIsClosed &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stisclosed-geography-data-type)  
  
 <span data-ttu-id="d9cef-227">**Para retornar o número de anéis em uma instância de Polígono**</span><span class="sxs-lookup"><span data-stu-id="d9cef-227">**To return the number of rings in a Polygon instance**</span></span>  
 [<span data-ttu-id="d9cef-228">NumRings &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-228">NumRings &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/numrings-geography-data-type)  
  
 <span data-ttu-id="d9cef-229">**Para retornar um anel especificado de uma instância de geografia**</span><span class="sxs-lookup"><span data-stu-id="d9cef-229">**To return a specified ring of a geography instance**</span></span>  
 [<span data-ttu-id="d9cef-230">RingN &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-230">RingN &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/ringn-geography-data-type)  
  
###  <a name="spatial-reference-id-srid"></a><a name="srid"></a> <span data-ttu-id="d9cef-231">SRID (Spatial Reference ID)</span><span class="sxs-lookup"><span data-stu-id="d9cef-231">Spatial Reference ID (SRID)</span></span>  
 <span data-ttu-id="d9cef-232">A ID de referência espacial (SRID) é um identificador que especifica o sistema de coordenadas elipsoidais no qual a instância `geography` é representada.</span><span class="sxs-lookup"><span data-stu-id="d9cef-232">The spatial reference ID (SRID) is an identifier specifying which ellipsoidal coordinate system the `geography` instance is represented in.</span></span> <span data-ttu-id="d9cef-233">Duas instâncias `geography` com SRIDs diferentes não podem ser comparadas.</span><span class="sxs-lookup"><span data-stu-id="d9cef-233">Two `geography` instances with different SRIDs cannot be compared.</span></span>  
  
 <span data-ttu-id="d9cef-234">**Para definir ou retornar o SRID de uma instância**</span><span class="sxs-lookup"><span data-stu-id="d9cef-234">**To set or return the SRID of an instance**</span></span>  
 [<span data-ttu-id="d9cef-235">STSrid &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-235">STSrid &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stsrid-geography-data-type)  
  
 <span data-ttu-id="d9cef-236">Essa propriedade pode ser modificada.</span><span class="sxs-lookup"><span data-stu-id="d9cef-236">This property can be modified.</span></span>  
  
##  <a name="determining-relationships-between-geography-instances"></a><a name="rel"></a> <span data-ttu-id="d9cef-237">Determinando relações entre instâncias de geografia</span><span class="sxs-lookup"><span data-stu-id="d9cef-237">Determining Relationships between geography Instances</span></span>  
 <span data-ttu-id="d9cef-238">O tipo de dados `geography` fornece vários métodos internos que podem ser usados para determinar relações entre duas instâncias de `geography`.</span><span class="sxs-lookup"><span data-stu-id="d9cef-238">The `geography` data type provides many built-in methods you can use to determine relationships between two `geography` instances.</span></span>  
  
 <span data-ttu-id="d9cef-239">**Para determinar se duas instâncias abrangem o mesmo conjunto de pontos**</span><span class="sxs-lookup"><span data-stu-id="d9cef-239">**To determine if two instances comprise the same point set**</span></span>  
 [<span data-ttu-id="d9cef-240">STEquals &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-240">STEquals &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stequals-geometry-data-type)  
  
 <span data-ttu-id="d9cef-241">**Para determinar se duas instâncias são não contíguas**</span><span class="sxs-lookup"><span data-stu-id="d9cef-241">**To determine if two instances are disjoint**</span></span>  
 [<span data-ttu-id="d9cef-242">STDisjoint &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-242">STDisjoint &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stdisjoint-geometry-data-type)  
  
 <span data-ttu-id="d9cef-243">**Para determinar se há interseção entre duas instâncias**</span><span class="sxs-lookup"><span data-stu-id="d9cef-243">**To determine if two instances intersect**</span></span>  
 [<span data-ttu-id="d9cef-244">STIntersects &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-244">STIntersects &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stintersects-geometry-data-type)  
  
 <span data-ttu-id="d9cef-245">**Para determinar o ponto ou pontos de interseção de duas instâncias**</span><span class="sxs-lookup"><span data-stu-id="d9cef-245">**To determine the point or points where two instances intersect**</span></span>  
 [<span data-ttu-id="d9cef-246">STIntersection &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-246">STIntersection &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stintersection-geography-data-type)  
  
 <span data-ttu-id="d9cef-247">**Para determinar a distância mais curta entre pontos em duas instâncias de geografia**</span><span class="sxs-lookup"><span data-stu-id="d9cef-247">**To determine the shortest distance between points in two geography instances**</span></span>  
 [<span data-ttu-id="d9cef-248">STDistance &#40;tipo de dados geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-248">STDistance &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stdistance-geometry-data-type)  
  
 <span data-ttu-id="d9cef-249">**Para determinar a diferença em pontos entre duas instâncias de geografia**</span><span class="sxs-lookup"><span data-stu-id="d9cef-249">**To determine the difference in points between two geography instances**</span></span>  
 [<span data-ttu-id="d9cef-250">STDifference &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-250">STDifference &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stdifference-geography-data-type)  
  
 <span data-ttu-id="d9cef-251">**Para derivar a diferença simétrica ou pontos exclusivos de uma instância de geografia comparada com outra instância**</span><span class="sxs-lookup"><span data-stu-id="d9cef-251">**To derive the symmetric difference, or unique points, of one geography instance compared with another instance**</span></span>  
 [<span data-ttu-id="d9cef-252">STSymDifference &#40;tipo de dados geography&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-252">STSymDifference &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stsymdifference-geography-data-type)  
  
##  <a name="geography-instances-must-use-supported-srid"></a><a name="supportedsrid"></a> <span data-ttu-id="d9cef-253">Instâncias de geografia devem usar SRID com suporte</span><span class="sxs-lookup"><span data-stu-id="d9cef-253">geography Instances Must Use Supported SRID</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d9cef-254">dá suporte a SRIDs baseadas nos padrões do EPSG.</span><span class="sxs-lookup"><span data-stu-id="d9cef-254">supports SRIDs based on the EPSG standards.</span></span> <span data-ttu-id="d9cef-255">Um SRID com suporte do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para instâncias de `geography` deve ser usado ao executar cálculos ou usar métodos com dados espaciais de geografia.</span><span class="sxs-lookup"><span data-stu-id="d9cef-255">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-supported SRID for `geography` instances must be used when performing calculations or using methods with geography spatial data.</span></span> <span data-ttu-id="d9cef-256">A SRID deve corresponder a uma das SRIDs exibidos na exibição de catálogo **sys.spatial_reference_systems** .</span><span class="sxs-lookup"><span data-stu-id="d9cef-256">The SRID must match one of the SRIDs displayed in the **sys.spatial_reference_systems** catalog view.</span></span> <span data-ttu-id="d9cef-257">Conforme mencionado anteriormente, ao executar cálculos nos dados espaciais usando o tipo de dados de `geography`, os resultados dependerão de qual elipsoide foi usado na criação dos dados, pois cada elipsoide recebe um SRID ( spatial reference identifier) específico.</span><span class="sxs-lookup"><span data-stu-id="d9cef-257">As mentioned previously, when you perform calculations on your spatial data using the `geography` data type, your results will depend on which ellipsoid was used in the creation of your data, as each ellipsoid is assigned a specific spatial reference identifier (SRID).</span></span>  
  
 <span data-ttu-id="d9cef-258">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa o SRID padrão de 4326, que é mapeado para o sistema de referência espacial WGS 84 ao usar métodos nas instâncias de `geography`.</span><span class="sxs-lookup"><span data-stu-id="d9cef-258">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses the default SRID of 4326, which maps to the WGS 84 spatial reference system, when using methods on `geography` instances.</span></span> <span data-ttu-id="d9cef-259">Se você usar dados de um sistema de referência espacial diferente de WGS 84 (ou SRID 4326), será necessário determinar o SRID específico de seus dados espaciais de geografia.</span><span class="sxs-lookup"><span data-stu-id="d9cef-259">If you use data from a spatial reference system other than WGS 84 (or SRID 4326), you will need to determine the specific SRID for your geography spatial data.</span></span>  
  
##  <a name="examples"></a><a name="examples"></a> <span data-ttu-id="d9cef-260">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d9cef-260">Examples</span></span>  
 <span data-ttu-id="d9cef-261">Os exemplos a seguir mostram como adicionar e consultar dados de geografia.</span><span class="sxs-lookup"><span data-stu-id="d9cef-261">The following examples show how to add and query geography data.</span></span>  
  
-   <span data-ttu-id="d9cef-262">O primeiro exemplo cria uma tabela com uma coluna de identidade e uma coluna de `geography``GeogCol1`.</span><span class="sxs-lookup"><span data-stu-id="d9cef-262">The first example creates a table with an identity column and a `geography` column `GeogCol1`.</span></span> <span data-ttu-id="d9cef-263">Uma terceira coluna renderiza a coluna de `geography` em sua representação WKT (Well-Known Text) do Open Geospatial Consortium (OGC) e usa o método `STAsText()` .</span><span class="sxs-lookup"><span data-stu-id="d9cef-263">A third column renders the `geography` column into its Open Geospatial Consortium (OGC) Well-Known Text (WKT) representation, and uses the `STAsText()` method.</span></span> <span data-ttu-id="d9cef-264">Em seguida, duas linhas são inseridas: uma linha que contém uma instância `LineString` de `geography`e uma linha que contém uma instância de `Polygon` .</span><span class="sxs-lookup"><span data-stu-id="d9cef-264">Two rows are then inserted: one row contains a `LineString` instance of `geography`, and one row contains a `Polygon` instance.</span></span>  
  
    ```  
    IF OBJECT_ID ( 'dbo.SpatialTable', 'U' ) IS NOT NULL   
        DROP TABLE dbo.SpatialTable;  
    GO  
  
    CREATE TABLE SpatialTable   
        ( id int IDENTITY (1,1),  
        GeogCol1 geography,   
        GeogCol2 AS GeogCol1.STAsText() );  
    GO  
  
    INSERT INTO SpatialTable (GeogCol1)  
    VALUES (geography::STGeomFromText('LINESTRING(-122.360 47.656, -122.343 47.656)', 4326));  
  
    INSERT INTO SpatialTable (GeogCol1)  
    VALUES (geography::STGeomFromText('POLYGON((-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653))', 4326));  
    GO  
    ```  
  
-   <span data-ttu-id="d9cef-265">O segundo exemplo usa o método `STIntersection()` para retornar os pontos onde as duas instâncias de `geography` inseridas anteriormente se cruzam.</span><span class="sxs-lookup"><span data-stu-id="d9cef-265">The second example uses the `STIntersection()` method to return the points where the two previously inserted `geography` instances intersect.</span></span>  
  
    ```  
    DECLARE @geog1 geography;  
    DECLARE @geog2 geography;  
    DECLARE @result geography;  
  
    SELECT @geog1 = GeogCol1 FROM SpatialTable WHERE id = 1;  
    SELECT @geog2 = GeogCol1 FROM SpatialTable WHERE id = 2;  
    SELECT @result = @geog1.STIntersection(@geog2);  
    SELECT @result.STAsText();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d9cef-266">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d9cef-266">See Also</span></span>  
 [<span data-ttu-id="d9cef-267">Dados espaciais &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d9cef-267">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
