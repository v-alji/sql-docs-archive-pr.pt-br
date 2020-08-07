---
title: Compreendendo a arquitetura Microsoft OLAP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- multidimensional data [Analysis Services], about multidimensional data
ms.assetid: a2eaaee8-7b06-48af-ba44-e21a3678c4c4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1abbbbd7c2f7caa99407bbcd17ace07deac5dfeb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575413"
---
# <a name="understanding-microsoft-olap-architecture"></a><span data-ttu-id="ea259-102">Entendendo a arquitetura Microsoft OLAP</span><span class="sxs-lookup"><span data-stu-id="ea259-102">Understanding Microsoft OLAP Architecture</span></span>
  <span data-ttu-id="ea259-103">Use estes tópicos para compreender os bancos de dados multidimensionais do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] e como planejar a implementação dos bancos de dados multidimensionais em sua solução de Business Intelligence.</span><span class="sxs-lookup"><span data-stu-id="ea259-103">Use these topics to better understand [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] multidimensional databases and plan how to implement multidimensional databases in your business intelligence solution.</span></span>  
  
 <span data-ttu-id="ea259-104">![Ícone de pasta de arquivo pequeno](../../../integration-services/media/filefolder-small.gif "Pequeno ícone de pasta de arquivos") **arquitetura lógica**</span><span class="sxs-lookup"><span data-stu-id="ea259-104">![Small File Folder Icon](../../../integration-services/media/filefolder-small.gif "Small File Folder Icon") **Logical Architecture**</span></span>  
 [<span data-ttu-id="ea259-105">Objetos de servidor &#40;Analysis Services-dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="ea259-105">Server Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../olap-logical/server-objects-analysis-services-multidimensional-data.md)  
  
 [<span data-ttu-id="ea259-106">Objetos de dimensão &#40;Analysis Services de dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="ea259-106">Dimension Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../../multidimensional-models-olap-logical-dimension-objects/dimension-objects-analysis-services-multidimensional-data.md)  
  
 [<span data-ttu-id="ea259-107">Objetos de cubo &#40;Analysis Services de dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="ea259-107">Cube Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../../multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md)  
  
 [<span data-ttu-id="ea259-108">Mais...</span><span class="sxs-lookup"><span data-stu-id="ea259-108">More...</span></span>](../olap-logical/understanding-microsoft-olap-logical-architecture.md)  
  
 <span data-ttu-id="ea259-109">![Ícone de pasta de arquivos pequena](../../../integration-services/media/filefolder-small.gif "Pequeno ícone de pasta de arquivos") **arquitetura física**</span><span class="sxs-lookup"><span data-stu-id="ea259-109">![Small File Folder Icon](../../../integration-services/media/filefolder-small.gif "Small File Folder Icon") **Physical Architecture**</span></span>  
 [<span data-ttu-id="ea259-110">Componentes do servidor de mecanismo OLAP</span><span class="sxs-lookup"><span data-stu-id="ea259-110">OLAP Engine Server Components</span></span>](olap-engine-server-components.md)  
  
 [<span data-ttu-id="ea259-111">Cubos locais &#40;Analysis Services-dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="ea259-111">Local Cubes &#40;Analysis Services - Multidimensional Data&#41;</span></span>](local-cubes-analysis-services-multidimensional-data.md)  
  
 [<span data-ttu-id="ea259-112">Mais...</span><span class="sxs-lookup"><span data-stu-id="ea259-112">More...</span></span>](understanding-microsoft-olap-physical-architecture.md)  
  
 <span data-ttu-id="ea259-113">![Ícone de pasta de arquivo pequeno](../../../integration-services/media/filefolder-small.gif "Pequeno ícone de pasta de arquivos") **arquitetura de programação**</span><span class="sxs-lookup"><span data-stu-id="ea259-113">![Small File Folder Icon](../../../integration-services/media/filefolder-small.gif "Small File Folder Icon") **Programming Architecture**</span></span>  
 [<span data-ttu-id="ea259-114">Desenvolvendo com AMO &#40;Objetos de Gerenciamento de Análise&#41;</span><span class="sxs-lookup"><span data-stu-id="ea259-114">Developing with Analysis Management Objects &#40;AMO&#41;</span></span>](https://docs.microsoft.com/bi-reference/amo/developing-with-analysis-management-objects-amo)  
  
 [<span data-ttu-id="ea259-115">Desenvolvendo com ASSL &#40;linguagem de script do Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ea259-115">Developing with Analysis Services Scripting Language &#40;ASSL&#41;</span></span>](../scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md)  
  
 [<span data-ttu-id="ea259-116">Desenvolvendo com ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="ea259-116">Developing with ADOMD.NET</span></span>](https://docs.microsoft.com/bi-reference/adomd/developing-with-adomd-net)  
  
 <span data-ttu-id="ea259-117">![Ícone de pasta de arquivo pequeno](../../../integration-services/media/filefolder-small.gif "Pequeno ícone de pasta de arquivos") **Considerações internacionais**</span><span class="sxs-lookup"><span data-stu-id="ea259-117">![Small File Folder Icon](../../../integration-services/media/filefolder-small.gif "Small File Folder Icon") **International Considerations**</span></span>  
 [<span data-ttu-id="ea259-118">Cenários de globalização para Analysis Services Multidimensional</span><span class="sxs-lookup"><span data-stu-id="ea259-118">Globalization scenarios for Analysis Services Multiidimensional</span></span>](../../globalization-scenarios-for-analysis-services-multiidimensional.md)  
  
## <a name="see-also"></a><span data-ttu-id="ea259-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ea259-119">See Also</span></span>  
 [<span data-ttu-id="ea259-120">Referência técnica &#40;SSAS&#41;</span><span class="sxs-lookup"><span data-stu-id="ea259-120">Technical Reference &#40;SSAS&#41;</span></span>](../../powershell/technical-reference-ssas.md)  
  
  
