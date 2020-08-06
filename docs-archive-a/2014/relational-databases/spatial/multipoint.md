---
title: MultiPoint | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- MultiPoint geometry subtype [SQL Server]
ms.assetid: 2aaab211-3aba-4dbd-90b7-095d997b1f62
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: b741071b7986aceea4e49d4fde8293ef2c96fc2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582909"
---
# <a name="multipoint"></a><span data-ttu-id="89457-102">MultiPoint</span><span class="sxs-lookup"><span data-stu-id="89457-102">MultiPoint</span></span>
  <span data-ttu-id="89457-103">Um `MultiPoint` é uma coleção de zero ou mais pontos.</span><span class="sxs-lookup"><span data-stu-id="89457-103">A `MultiPoint` is a collection of zero or more points.</span></span> <span data-ttu-id="89457-104">O limite de uma instância `MultiPoint` é vazio.</span><span class="sxs-lookup"><span data-stu-id="89457-104">The boundary of a `MultiPoint` instance is empty.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="89457-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="89457-105">Examples</span></span>  
 <span data-ttu-id="89457-106">O exemplo a seguir cria uma instância `geometry MultiPoint` com SRID 23 e dois pontos: um ponto com as coordenadas (2, 3), um ponto com as coordenadas (7, 8) e um valor Z de 9,5.</span><span class="sxs-lookup"><span data-stu-id="89457-106">The following example creates a `geometry MultiPoint` instance with SRID 23 and two points: one point with the coordinates (2, 3), one point with the coordinates (7, 8), and a Z value of 9.5.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('MULTIPOINT((2 3), (7 8 9.5))', 23);  
```  
  
 <span data-ttu-id="89457-107">Essa instância `MultiPoint` também pode ser expressada usando `STMPointFromText()` conforme mostrado a seguir.</span><span class="sxs-lookup"><span data-stu-id="89457-107">This `MultiPoint` instance can also be expressed using `STMPointFromText()` as shown below.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STMPointFromText('MULTIPOINT((2 3), (7 8 9.5))', 23);  
```  
  
 <span data-ttu-id="89457-108">O exemplo a seguir usa o método `STGeometryN()` para recuperar uma descrição do primeiro ponto na coleção.</span><span class="sxs-lookup"><span data-stu-id="89457-108">The following example uses the method `STGeometryN()` to retrieve a description of the first point in the collection.</span></span>  
  
```  
SELECT @g.STGeometryN(1).STAsText();  
```  
  
## <a name="see-also"></a><span data-ttu-id="89457-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="89457-109">See Also</span></span>  
 <span data-ttu-id="89457-110">[Empresas](point.md) </span><span class="sxs-lookup"><span data-stu-id="89457-110">[Point](point.md) </span></span>  
 [<span data-ttu-id="89457-111">Dados espaciais &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="89457-111">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
