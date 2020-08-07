---
title: SRIDs (Identificadores de Referência Espacial) | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Spatial Reference Identifiers (SRIDs)
- geodetic spatial data [SQL Server], identifiers
- SRID
ms.assetid: 0612658a-7d1b-4178-bdc2-42b914ea31a7
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 15db59b43731b9a39ff4bef78e3a6cb6929e9b47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575059"
---
# <a name="spatial-reference-identifiers-srids"></a><span data-ttu-id="49148-102">SRIDs (Spatial Reference Identifiers)</span><span class="sxs-lookup"><span data-stu-id="49148-102">Spatial Reference Identifiers (SRIDs)</span></span>
  <span data-ttu-id="49148-103">Cada instância espacial tem um SRID (spatial reference identifier).</span><span class="sxs-lookup"><span data-stu-id="49148-103">Each spatial instance has a spatial reference identifier (SRID).</span></span> <span data-ttu-id="49148-104">O SRID corresponde a um sistema de referência espacial baseado no elipsoide específico usado para mapeamento de terra plana ou de terra redonda.</span><span class="sxs-lookup"><span data-stu-id="49148-104">The SRID corresponds to a spatial reference system based on the specific ellipsoid used for either flat-earth mapping or round-earth mapping.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="49148-105">Para obter uma descrição detalhada e exemplos de recursos espaciais introduzidos no [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], incluindo um novo SRID, baixe o white paper [Novos recursos espaciais no SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span><span class="sxs-lookup"><span data-stu-id="49148-105">For a detailed description and examples of spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], including a new SRID, download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>  
  
 <span data-ttu-id="49148-106">Uma coluna espacial pode conter objetos com SRIDs diferentes.</span><span class="sxs-lookup"><span data-stu-id="49148-106">A spatial column can contain objects with different SRIDs.</span></span> <span data-ttu-id="49148-107">No entanto apenas instâncias espaciais com o mesmo SRID podem ser usadas ao executar operações com métodos de dados espaciais do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em seus dados.</span><span class="sxs-lookup"><span data-stu-id="49148-107">However, only spatial instances with the same SRID can be used when performing operations with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] spatial data methods on your data.</span></span> <span data-ttu-id="49148-108">O resultado de qualquer método espacial derivado de duas instâncias de dados espaciais será válido apenas se essas instâncias tiverem o mesmo SRID que é baseado na mesma unidade de medida, datum, e projeção usada para determinar as coordenadas das instâncias.</span><span class="sxs-lookup"><span data-stu-id="49148-108">The result of any spatial method derived from two spatial data instances is valid only if those instances have the same SRID that is based on the same unit of measurement, datum, and projection used to determine the coordinates of the instances.</span></span> <span data-ttu-id="49148-109">As unidades mais comuns de medida de um SRID são metros ou metros quadrados.</span><span class="sxs-lookup"><span data-stu-id="49148-109">The most common units of measurement of a SRID are meters or square meters.</span></span>  
  
 <span data-ttu-id="49148-110">Se duas instâncias espaciais não tiverem o mesmo SRID, os resultados de um método de Tipo de Dados `geometry` ou `geography` usado nas instâncias retornará NULL.</span><span class="sxs-lookup"><span data-stu-id="49148-110">If two spatial instances do not have the same SRID, the results from a `geometry` or `geography` Data Type method used on the instances will return NULL.</span></span> <span data-ttu-id="49148-111">Por exemplo, para que o seguinte termo de predicado retorne um resultado não NULL, as duas instâncias de `geometry`, `geometry1` e `geometry2`, devem ter o mesmo SRID:</span><span class="sxs-lookup"><span data-stu-id="49148-111">For example, for the following predicate term to return a non-NULL result, the two `geometry` instances, `geometry1` and `geometry2`, must have the same SRID:</span></span>  
  
 `geometry1.STIntersects(geometry2) = 1`  
  
> [!NOTE]  
>  <span data-ttu-id="49148-112">O sistema de identificação de referência espacial é definido pelo [padrão do EPSG (European Petroleum Survey Group)](https://go.microsoft.com/fwlink/?LinkId=99349) , que é um conjunto de padrões desenvolvido para armazenamento de dados geodésicos, de cartografia e de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="49148-112">The spatial reference identification system is defined by the [European Petroleum Survey Group (EPSG)](https://go.microsoft.com/fwlink/?LinkId=99349) standard, which is a set of standards developed for cartography, surveying, and geodetic data storage.</span></span> <span data-ttu-id="49148-113">Esse padrão é de propriedade do Comitê de Pesquisa e Posicionamento da OGP (Oil and Gas Producers).</span><span class="sxs-lookup"><span data-stu-id="49148-113">This standard is owned by the Oil and Gas Producers (OGP) Surveying and Positioning Committee.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49148-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="49148-114">See Also</span></span>  
 [<span data-ttu-id="49148-115">Visão geral de tipos de dados espaciais</span><span class="sxs-lookup"><span data-stu-id="49148-115">Spatial Data Types Overview</span></span>](spatial-data-types-overview.md)  
  
  
