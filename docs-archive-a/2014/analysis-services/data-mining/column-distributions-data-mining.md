---
title: Distribuições de coluna (mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- normal distribution type [data mining]
- uniform distribution type [data mining]
- columns [data mining], distributions
- log normal distribution type [data mining]
- continuous columns
- distributions [data mining]
ms.assetid: 87e700de-32be-4bc8-b01d-ba4ee1ab48de
author: minewiskan
ms.author: owend
ms.openlocfilehash: 29aad33535c4cc4d9baf4c453249ce3b51595e78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583915"
---
# <a name="column-distributions-data-mining"></a><span data-ttu-id="8e8b0-102">Distribuições de colunas (mineração de dados)</span><span class="sxs-lookup"><span data-stu-id="8e8b0-102">Column Distributions (Data Mining)</span></span>
  <span data-ttu-id="8e8b0-103">No [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , você pode definir distribuições de coluna em uma estrutura de mineração para afetar como os algoritmos processam os dados nessas colunas quando você cria modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="8e8b0-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you can define column distributions in a mining structure, to affect how algorithms process the data in those columns when you create mining models.</span></span> <span data-ttu-id="8e8b0-104">Com relação a certos algoritmos, é útil definir a distribuição de colunas contínuas antes de processar o modelo, principalmente quando se sabe que as colunas contêm distribuições comuns de valores.</span><span class="sxs-lookup"><span data-stu-id="8e8b0-104">For some algorithms, it is useful to define the distribution of any continuous columns before you process the model, if the columns are known to contain common distributions of values.</span></span> <span data-ttu-id="8e8b0-105">Se as distribuições não estiverem definidas, os modelos de mineração resultantes poderão produzir previsões menos precisas do que se as distribuições estiverem definidas, uma vez que os algoritmos terão menos informações com as quais interpretar dados.</span><span class="sxs-lookup"><span data-stu-id="8e8b0-105">If you do not define the distributions, the resulting mining models may produce less accurate predictions than if the distributions were defined, because the algorithms will have less information from which to interpret the data.</span></span>

 <span data-ttu-id="8e8b0-106">Os algoritmos que estão disponíveis em [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] fornecem suporte aos seguintes tipos de distribuição:</span><span class="sxs-lookup"><span data-stu-id="8e8b0-106">The algorithms that are available in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] support the following distribution types:</span></span>

 <span data-ttu-id="8e8b0-107">`Normal`Os valores para a coluna contínua formam um histograma com uma distribuição normal.</span><span class="sxs-lookup"><span data-stu-id="8e8b0-107">`Normal` The values for the continuous column form a histogram with a normal distribution.</span></span>

 <span data-ttu-id="8e8b0-108">![Histograma com distribuição normal](../media/normal-distribution.gif "Histograma com distribuição normal")</span><span class="sxs-lookup"><span data-stu-id="8e8b0-108">![Histogram with normal distribution](../media/normal-distribution.gif "Histogram with normal distribution")</span></span>

 <span data-ttu-id="8e8b0-109">`Log Normal`Os valores da coluna contínua formam um histograma, em que a curva é alongada na extremidade superior e é distorcida em direção à extremidade inferior.</span><span class="sxs-lookup"><span data-stu-id="8e8b0-109">`Log Normal` The values for the continuous column form a histogram, where the curve is elongated at the upper end and is skewed toward the lower end.</span></span>

 <span data-ttu-id="8e8b0-110">![Histograma com distribuição normal de log](../media/log-normal-distribution.gif "Histograma com distribuição normal de log")</span><span class="sxs-lookup"><span data-stu-id="8e8b0-110">![Histogram with log normal distribution](../media/log-normal-distribution.gif "Histogram with log normal distribution")</span></span>

 <span data-ttu-id="8e8b0-111">`Uniform`Os valores para a coluna contínua formam uma curva plana, na qual todos os valores são igualmente prováveis.</span><span class="sxs-lookup"><span data-stu-id="8e8b0-111">`Uniform` The values for the continuous column form a flat curve, in which all values are equally likely.</span></span>

 <span data-ttu-id="8e8b0-112">![Histograma com distribuição uniforme](../media/uniform-distribution.gif "Histograma com distribuição uniforme")</span><span class="sxs-lookup"><span data-stu-id="8e8b0-112">![Histogram with uniform distribution](../media/uniform-distribution.gif "Histogram with uniform distribution")</span></span>

 <span data-ttu-id="8e8b0-113">Para obter mais informações sobre os algoritmos fornecidos pelo [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], consulte [Algoritmos de Data Mining &#40;Analysis Services – Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="8e8b0-113">For more information about the algorithms that [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides, see [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8e8b0-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8e8b0-114">See Also</span></span>
 <span data-ttu-id="8e8b0-115">[Tipos de conteúdo &#40;data mining&#41;](content-types-data-mining.md) [estruturas de mineração &#40;Analysis Services-Data Mining&#41;](mining-structures-analysis-services-data-mining.md) [métodos discretização &#40;](discretization-methods-data-mining.md) [distribuições](/sql/dmx/distributions-dmx)&#41;de mineração de dados &#40;[colunas da estrutura de mineração](mining-structure-columns.md) do DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="8e8b0-115">[Content Types &#40;Data Mining&#41;](content-types-data-mining.md) [Mining Structures &#40;Analysis Services - Data Mining&#41;](mining-structures-analysis-services-data-mining.md) [Discretization Methods &#40;Data Mining&#41;](discretization-methods-data-mining.md) [Distributions &#40;DMX&#41;](/sql/dmx/distributions-dmx) [Mining Structure Columns](mining-structure-columns.md)</span></span>


