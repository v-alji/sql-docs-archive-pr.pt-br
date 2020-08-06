---
title: Dimensões (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- OLAP objects [Analysis Services], dimensions
- dimensions [Analysis Services]
- Analysis Services objects, dimensions
ms.assetid: 2b114135-2572-4479-8c81-3ccf0cfeb9f7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2e0e15d4f74c2c6cec06edaf692199e48534c7e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684404"
---
# <a name="dimensions-analysis-services---multidimensional-data"></a><span data-ttu-id="b45ae-102">Dimensões (Analysis Services – Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="b45ae-102">Dimensions (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="b45ae-103">No [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , as dimensões são um componente fundamental dos cubos.</span><span class="sxs-lookup"><span data-stu-id="b45ae-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], dimensions are a fundamental component of cubes.</span></span> <span data-ttu-id="b45ae-104">As dimensões organizam dados com relação a uma área de interesse, como clientes, lojas ou funcionários, para usuários.</span><span class="sxs-lookup"><span data-stu-id="b45ae-104">Dimensions organize data with relation to an area of interest, such as customers, stores, or employees, to users.</span></span> <span data-ttu-id="b45ae-105">As dimensões no [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] contêm atributos que correspondem às colunas nas tabelas de dimensões.</span><span class="sxs-lookup"><span data-stu-id="b45ae-105">Dimensions in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] contain attributes that correspond to columns in dimension tables.</span></span> <span data-ttu-id="b45ae-106">Esses atributos aparecem como hierarquias de atributo e podem ser organizados em hierarquias definidas pelo usuário, ou podem ser definidos como hierarquias pai-filho com base em colunas na tabela de dimensões subjacente.</span><span class="sxs-lookup"><span data-stu-id="b45ae-106">These attributes appear as attribute hierarchies and can be organized into user-defined hierarchies, or can be defined as parent-child hierarchies based on columns in the underlying dimension table.</span></span> <span data-ttu-id="b45ae-107">As hierarquias são usadas para organizar medidas contidas em um cubo.</span><span class="sxs-lookup"><span data-stu-id="b45ae-107">Hierarchies are used to organize measures that are contained in a cube.</span></span> <span data-ttu-id="b45ae-108">Os tópicos a seguir fornecem uma visão geral de dimensões, atributos e hierarquias.</span><span class="sxs-lookup"><span data-stu-id="b45ae-108">The following topics provide an overview of dimensions, attributes, and hierarchies.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b45ae-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="b45ae-109">In This Section</span></span>  
  
|<span data-ttu-id="b45ae-110">Tópico</span><span class="sxs-lookup"><span data-stu-id="b45ae-110">Topic</span></span>|<span data-ttu-id="b45ae-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="b45ae-111">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="b45ae-112">Introdução a Dimensões &#40;Analysis Services – Dados Multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="b45ae-112">Introduction to Dimensions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimensions-analysis-services-multidimensional-data.md)|<span data-ttu-id="b45ae-113">Fornece uma visão geral de conceitos de dimensão.</span><span class="sxs-lookup"><span data-stu-id="b45ae-113">Provides an overview of dimension concepts.</span></span>|  
|[<span data-ttu-id="b45ae-114">Atributos e hierarquias de atributos</span><span class="sxs-lookup"><span data-stu-id="b45ae-114">Attributes and Attribute Hierarchies</span></span>](attributes-and-attribute-hierarchies.md)|<span data-ttu-id="b45ae-115">Descreve atributos e hierarquias de atributo.</span><span class="sxs-lookup"><span data-stu-id="b45ae-115">Describes attributes and attribute hierarchies.</span></span>|  
|[<span data-ttu-id="b45ae-116">Hierarquias do usuário</span><span class="sxs-lookup"><span data-stu-id="b45ae-116">User Hierarchies</span></span>](user-hierarchies.md)|<span data-ttu-id="b45ae-117">Descreve hierarquias definidas pelo usuário de atributos.</span><span class="sxs-lookup"><span data-stu-id="b45ae-117">Describes user-defined hierarchies of attributes.</span></span>|  
|[<span data-ttu-id="b45ae-118">Dimensões habilitadas para gravação</span><span class="sxs-lookup"><span data-stu-id="b45ae-118">Write-Enabled Dimensions</span></span>](write-enabled-dimensions.md)|<span data-ttu-id="b45ae-119">Descreve dimensões habilitadas para gravação.</span><span class="sxs-lookup"><span data-stu-id="b45ae-119">Describes write-enabled dimensions.</span></span>|  
|[<span data-ttu-id="b45ae-120">Tradução de dimensões</span><span class="sxs-lookup"><span data-stu-id="b45ae-120">Dimension Translations</span></span>](dimension-translations.md)|<span data-ttu-id="b45ae-121">Descreve conversões de metadados de dimensão.</span><span class="sxs-lookup"><span data-stu-id="b45ae-121">Describes translations of dimension meta data.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b45ae-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b45ae-122">See Also</span></span>  
 <span data-ttu-id="b45ae-123">[Dimensões em modelos multidimensionais](../multidimensional-models/dimensions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="b45ae-123">[Dimensions in Multidimensional Models](../multidimensional-models/dimensions-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="b45ae-124">Objetos de cubo &#40;Analysis Services de dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="b45ae-124">Cube Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md)  
  
  
