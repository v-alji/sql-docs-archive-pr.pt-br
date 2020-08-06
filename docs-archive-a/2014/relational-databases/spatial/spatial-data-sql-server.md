---
title: Dados espaciais (SQL Server) | Microsoft Docs
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- geography data type [SQL Server], spatial storage design
- planar spatial data [SQL Server], designing
- spatial data types [SQL Server]
- geodetic spatial data [SQL Server]
- geometry data type [SQL Server], spatial storage design
- spatial storage [SQL Server]
- geodetic spatial data [SQL Server], designing
ms.assetid: 41a132a1-09e2-4426-b9df-225270cb8e15
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 4d491420a9eca7c35b89b254a03381c6467c834c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582900"
---
# <a name="spatial-data-sql-server"></a><span data-ttu-id="80ca3-102">Dados espaciais (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="80ca3-102">Spatial Data (SQL Server)</span></span>
  <span data-ttu-id="80ca3-103">Os dados espaciais representam informações sobre a localização física e a forma dos objetos geométricos.</span><span class="sxs-lookup"><span data-stu-id="80ca3-103">Spatial data represents information about the physical location and shape of geometric objects.</span></span> <span data-ttu-id="80ca3-104">Esses objetos podem ser localizações de pontos ou objetos mais complexos como países, estradas ou lagos.</span><span class="sxs-lookup"><span data-stu-id="80ca3-104">These objects can be point locations or more complex objects such as countries, roads, or lakes.</span></span>  
  
 <span data-ttu-id="80ca3-105">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oferece suporte a dois tipos de dados espaciais: `geometry` e `geography`.</span><span class="sxs-lookup"><span data-stu-id="80ca3-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supports two spatial data types: the `geometry` data type and the `geography` data type.</span></span>  
  
-   <span data-ttu-id="80ca3-106">O tipo `geometry` representa dados em um sistema de coordenadas euclidiano (plano).</span><span class="sxs-lookup"><span data-stu-id="80ca3-106">The `geometry` type represents data in a Euclidean (flat) coordinate system.</span></span>  
  
-   <span data-ttu-id="80ca3-107">O tipo `geography` representa dados em um sistema de coordenadas de globo terrestre.</span><span class="sxs-lookup"><span data-stu-id="80ca3-107">The `geography` type represents data in a round-earth coordinate system.</span></span>  
  
 <span data-ttu-id="80ca3-108">Os dois tipos de dados são implementados como tipos de dados CLR (Common Language Runtime) do .NET no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="80ca3-108">Both data types are implemented as .NET common language runtime (CLR) data types in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="80ca3-109">Para obter uma descrição detalhada e exemplos de recursos espaciais introduzidos no [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], baixe o white paper [Novos recursos espaciais no SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span><span class="sxs-lookup"><span data-stu-id="80ca3-109">For a detailed description and examples of spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>  
  
##  <a name="related-tasks"></a><a name="reltasks"></a> <span data-ttu-id="80ca3-110">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="80ca3-110">Related Tasks</span></span>  
 [<span data-ttu-id="80ca3-111">Criar, construir e consultar instâncias de geometria</span><span class="sxs-lookup"><span data-stu-id="80ca3-111">Create, Construct, and Query geometry Instances</span></span>](create-construct-and-query-geometry-instances.md)  
 <span data-ttu-id="80ca3-112">Descreve os métodos que você pode usar com instâncias do tipo de dados de geometria.</span><span class="sxs-lookup"><span data-stu-id="80ca3-112">Describes the methods that you can use with instances of the geometry data type.</span></span>  
  
 [<span data-ttu-id="80ca3-113">Criar, construir e consultar instâncias de geografia</span><span class="sxs-lookup"><span data-stu-id="80ca3-113">Create, Construct, and Query geography Instances</span></span>](create-construct-and-query-geography-instances.md)  
 <span data-ttu-id="80ca3-114">Descreve os métodos que você pode usar com instâncias do tipo de dados de geografia.</span><span class="sxs-lookup"><span data-stu-id="80ca3-114">Describes the methods that you can use with instances of the geography data type.</span></span>  
  
 [<span data-ttu-id="80ca3-115">Consultar dados espaciais de vizinho mais próximo</span><span class="sxs-lookup"><span data-stu-id="80ca3-115">Query Spatial Data for Nearest Neighbor</span></span>](query-spatial-data-for-nearest-neighbor.md)  
 <span data-ttu-id="80ca3-116">Descreve o padrão de consulta comum usado para localizar os objetos espaciais mais próximos a um objeto espacial específico.</span><span class="sxs-lookup"><span data-stu-id="80ca3-116">Describes the common query pattern that is used to find the closest spatial objects to a specific spatial object.</span></span>  
  
 [<span data-ttu-id="80ca3-117">Criar, modificar e remover índices espaciais</span><span class="sxs-lookup"><span data-stu-id="80ca3-117">Create, Modify, and Drop Spatial Indexes</span></span>](create-modify-and-drop-spatial-indexes.md)  
 <span data-ttu-id="80ca3-118">Fornece informações sobre como criar, alterar e remover um índice espacial.</span><span class="sxs-lookup"><span data-stu-id="80ca3-118">Provides information about creating, altering, and dropping a spatial index.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="80ca3-119">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="80ca3-119">Related Content</span></span>  
 [<span data-ttu-id="80ca3-120">Visão geral de tipos de dados espaciais</span><span class="sxs-lookup"><span data-stu-id="80ca3-120">Spatial Data Types Overview</span></span>](spatial-data-types-overview.md)  
 <span data-ttu-id="80ca3-121">Introduz os tipos de dados espaciais.</span><span class="sxs-lookup"><span data-stu-id="80ca3-121">Introduces the spatial data types.</span></span>  
  
-   [<span data-ttu-id="80ca3-122">Ponto</span><span class="sxs-lookup"><span data-stu-id="80ca3-122">Point</span></span>](point.md)  
  
-   [<span data-ttu-id="80ca3-123">LineString</span><span class="sxs-lookup"><span data-stu-id="80ca3-123">LineString</span></span>](linestring.md)  
  
-   [<span data-ttu-id="80ca3-124">CircularString</span><span class="sxs-lookup"><span data-stu-id="80ca3-124">CircularString</span></span>](circularstring.md)  
  
-   [<span data-ttu-id="80ca3-125">CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="80ca3-125">CompoundCurve</span></span>](compoundcurve.md)  
  
-   [<span data-ttu-id="80ca3-126">Polygon</span><span class="sxs-lookup"><span data-stu-id="80ca3-126">Polygon</span></span>](polygon.md)  
  
-   [<span data-ttu-id="80ca3-127">CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="80ca3-127">CurvePolygon</span></span>](curvepolygon.md)  
  
-   [<span data-ttu-id="80ca3-128">MultiPoint</span><span class="sxs-lookup"><span data-stu-id="80ca3-128">MultiPoint</span></span>](multipoint.md)  
  
-   [<span data-ttu-id="80ca3-129">MultiLineString</span><span class="sxs-lookup"><span data-stu-id="80ca3-129">MultiLineString</span></span>](multilinestring.md)  
  
-   [<span data-ttu-id="80ca3-130">MultiPolygon</span><span class="sxs-lookup"><span data-stu-id="80ca3-130">MultiPolygon</span></span>](multipolygon.md)  
  
-   [<span data-ttu-id="80ca3-131">GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="80ca3-131">GeometryCollection</span></span>](geometrycollection.md)  
  
 [<span data-ttu-id="80ca3-132">Visão geral de índices espaciais</span><span class="sxs-lookup"><span data-stu-id="80ca3-132">Spatial Indexes Overview</span></span>](spatial-indexes-overview.md)  
 <span data-ttu-id="80ca3-133">Introduz índices espaciais e descreve mosaico e esquemas de mosaico.</span><span class="sxs-lookup"><span data-stu-id="80ca3-133">Introduces spatial indexes and describes tessellation and tessellation schemes.</span></span>  
  
  
