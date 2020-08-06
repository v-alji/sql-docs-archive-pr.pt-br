---
title: Ponto | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Point geometry subtype [SQL Server]
- geometry data type [SQL Server], spatial data
ms.assetid: 2a596ec4-8b2f-4962-bcb4-e5c8f77edad5
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 4b12069d84e00738e3ddac8c414f33903f4f0999
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582905"
---
# <a name="point"></a><span data-ttu-id="9d160-102">Point</span><span class="sxs-lookup"><span data-stu-id="9d160-102">Point</span></span>
  <span data-ttu-id="9d160-103">Em dados espaciais do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], um `Point` é um objeto dimensional zero que representa um único local e pode conter valores Z (elevação) e M (medida).</span><span class="sxs-lookup"><span data-stu-id="9d160-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] spatial data, a `Point` is a 0-dimensional object representing a single location and may contain Z (elevation) and M (measure) values.</span></span>  
  
## <a name="geography-data-type"></a><span data-ttu-id="9d160-104">Tipo de dados de geografia</span><span class="sxs-lookup"><span data-stu-id="9d160-104">Geography Data Type</span></span>  
 <span data-ttu-id="9d160-105">O tipo de Ponto para o tipo de dados geography representa um único local em que *Lat* representa latitude e *Long* representa longitude.</span><span class="sxs-lookup"><span data-stu-id="9d160-105">The Point type for the geography data type represents a single location where *Lat* represents latitude and *Long* represents longitude.</span></span> <span data-ttu-id="9d160-106">Os valores de latitude e longitude são medidos em graus.</span><span class="sxs-lookup"><span data-stu-id="9d160-106">The values for latitude and longitude are measured in degrees.</span></span> <span data-ttu-id="9d160-107">Valores para latitude sempre estão no intervalo [-90, 90] e os valores inseridos fora desse intervalo gerarão uma exceção.</span><span class="sxs-lookup"><span data-stu-id="9d160-107">Values for latitude always lie in the interval [-90, 90], and values that are inputted outside this range will throw an exception.</span></span> <span data-ttu-id="9d160-108">Os valores de longitude estão sempre no intervalo (-180, 180]; e os valores inseridos fora desse intervalo são ajustados para caberem nesse intervalo.</span><span class="sxs-lookup"><span data-stu-id="9d160-108">Values for longitude always lie in the interval (-180, 180], and values inputted outside this range are wrapped around to fit in this range.</span></span> <span data-ttu-id="9d160-109">Por exemplo, se 190 for inserido para longitude, ele será ajustado para o valor -170.</span><span class="sxs-lookup"><span data-stu-id="9d160-109">For example, if 190 is inputted for longitude, then it will be wrapped to the value -170.</span></span> <span data-ttu-id="9d160-110">*SRID* representa a ID de referência espacial da instância **geography** que você deseja retornar.</span><span class="sxs-lookup"><span data-stu-id="9d160-110">*SRID* represents the spatial reference ID of the **geography** instance that you wish to return.</span></span>  
  
## <a name="geometry-data-type"></a><span data-ttu-id="9d160-111">Tipo de dados geometry</span><span class="sxs-lookup"><span data-stu-id="9d160-111">Geometry Data Type</span></span>  
 <span data-ttu-id="9d160-112">O tipo de Ponto para o tipo de dados geometry representa um único local onde *X* representa a coordenada X do Ponto que é gerado e *Y* representa a coordenada de Y do Ponto que é gerado.</span><span class="sxs-lookup"><span data-stu-id="9d160-112">The Point type for the geometry data type represents a single location where *X* represents the X-coordinate of the Point being generated and *Y* represents the Y-coordinate of the Point being generated.</span></span> <span data-ttu-id="9d160-113">*SRID* representa a ID de referência espacial da instância **geometry** que você deseja retornar.</span><span class="sxs-lookup"><span data-stu-id="9d160-113">*SRID* represents the spatial reference ID of the **geometry** instance that you wish to return.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="9d160-114">Exemplos</span><span class="sxs-lookup"><span data-stu-id="9d160-114">Examples</span></span>  
 <span data-ttu-id="9d160-115">O exemplo a seguir cria uma instância `geometry Point`que representa o ponto (3, 4) com um SRID de 0.</span><span class="sxs-lookup"><span data-stu-id="9d160-115">The following example creates a `geometry Point`instance representing the point (3, 4) with an SRID of 0.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('POINT (3 4)', 0);  
```  
  
 <span data-ttu-id="9d160-116">O próximo exemplo cria uma instância de `geometry``Point` que representa o ponto (3, 4) com um valor Z (elevação) de 7, um valor M (medida) de 2,5 e o SRID padrão de 0.</span><span class="sxs-lookup"><span data-stu-id="9d160-116">The next example creates a `geometry``Point` instance representing the point (3, 4) with a Z (elevation) value of 7, an M (measure) value of 2.5, and the default SRID of 0.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('POINT(3 4 7 2.5)');  
```  
  
 <span data-ttu-id="9d160-117">O exemplo final retorna os valores X, Y, Z e M para a instância `geometry``Point` .</span><span class="sxs-lookup"><span data-stu-id="9d160-117">The final example returns the X, Y, Z, and M values for the `geometry``Point` instance.</span></span>  
  
```  
SELECT @g.STX;  
SELECT @g.STY;  
SELECT @g.Z;  
SELECT @g.M;  
```  
  
 <span data-ttu-id="9d160-118">Podem ser especificados valores Z e M como NULL, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="9d160-118">Z and M values may be explicitly specified as NULL, as shown in the following example.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('POINT(3 4 NULL NULL)');  
```  
  
## <a name="see-also"></a><span data-ttu-id="9d160-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9d160-119">See Also</span></span>  
 <span data-ttu-id="9d160-120">[MultiPoint](multipoint.md) </span><span class="sxs-lookup"><span data-stu-id="9d160-120">[MultiPoint](multipoint.md) </span></span>  
 <span data-ttu-id="9d160-121">[STX &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/stx-geometry-data-type) </span><span class="sxs-lookup"><span data-stu-id="9d160-121">[STX &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stx-geometry-data-type) </span></span>  
 <span data-ttu-id="9d160-122">[STY &#40;tipo de dados geometry&#41;](/sql/t-sql/spatial-geometry/sty-geometry-data-type) </span><span class="sxs-lookup"><span data-stu-id="9d160-122">[STY &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/sty-geometry-data-type) </span></span>  
 [<span data-ttu-id="9d160-123">Dados espaciais &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9d160-123">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
