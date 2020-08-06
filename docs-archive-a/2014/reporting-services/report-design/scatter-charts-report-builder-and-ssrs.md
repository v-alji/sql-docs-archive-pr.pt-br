---
title: Gráficos de dispersão (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2520ae24-0609-4890-807d-3267018aba8e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 93f9b31089eb8399c7fdfd201d3c799608f2e91e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681426"
---
# <a name="scatter-charts-report-builder-and-ssrs"></a><span data-ttu-id="84a85-102">Gráficos de dispersão (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="84a85-102">Scatter Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="84a85-103">Um gráfico de dispersão exibe uma série como um conjunto de pontos.</span><span class="sxs-lookup"><span data-stu-id="84a85-103">A scatter chart displays a series as a set of points.</span></span> <span data-ttu-id="84a85-104">Os valores são representados pela posição dos pontos no gráfico.</span><span class="sxs-lookup"><span data-stu-id="84a85-104">Values are represented by the position of the points on the chart.</span></span> <span data-ttu-id="84a85-105">As categorias são representadas por diferentes marcadores no gráfico.</span><span class="sxs-lookup"><span data-stu-id="84a85-105">Categories are represented by different markers on the chart.</span></span> <span data-ttu-id="84a85-106">Normalmente, os gráficos de dispersão são usados para comparar dados agregados por categorias.</span><span class="sxs-lookup"><span data-stu-id="84a85-106">Scatter charts are typically used to compare aggregated data across categories.</span></span> <span data-ttu-id="84a85-107">Para obter mais informações sobre como adicionar dados a um gráfico de dispersão, consulte [Gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="84a85-107">For more information on how to add data to a scatter chart, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md)</span></span>  
  
 <span data-ttu-id="84a85-108">A ilustração a seguir mostra um exemplo de gráfico de dispersão.</span><span class="sxs-lookup"><span data-stu-id="84a85-108">The following illustration shows an example of a scatter chart.</span></span>  
  
 <span data-ttu-id="84a85-109">![Gráfico de dispersão](../media/rs-scatterchart.gif "Gráfico de dispersão")</span><span class="sxs-lookup"><span data-stu-id="84a85-109">![Scatter chart](../media/rs-scatterchart.gif "Scatter chart")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="84a85-110">Variações</span><span class="sxs-lookup"><span data-stu-id="84a85-110">Variations</span></span>  
  
-   <span data-ttu-id="84a85-111">**Bolha.**</span><span class="sxs-lookup"><span data-stu-id="84a85-111">**Bubble.**</span></span> <span data-ttu-id="84a85-112">Os gráficos de bolhas exibem a diferença entre dois valores de um ponto de dados baseado no tamanho da bolha.</span><span class="sxs-lookup"><span data-stu-id="84a85-112">Bubble charts display the difference between two values of a data point based on the size of the bubble.</span></span> <span data-ttu-id="84a85-113">Quanto maior a bolha, maior a diferença entre os dois valores.</span><span class="sxs-lookup"><span data-stu-id="84a85-113">The larger the bubble, the larger the difference between the two values.</span></span>  
  
-   <span data-ttu-id="84a85-114">**Bolha em 3D**.</span><span class="sxs-lookup"><span data-stu-id="84a85-114">**3-D Bubble**.</span></span> <span data-ttu-id="84a85-115">Um gráfico de bolhas exibido em 3D.</span><span class="sxs-lookup"><span data-stu-id="84a85-115">A bubble chart displayed in 3-D.</span></span>  
  
## <a name="data-considerations-for-a-scatter-chart"></a><span data-ttu-id="84a85-116">Considerações de dados para um gráfico de dispersão</span><span class="sxs-lookup"><span data-stu-id="84a85-116">Data Considerations for a Scatter Chart</span></span>  
  
-   <span data-ttu-id="84a85-117">Normalmente, os gráficos de dispersão são usados para exibir e comparar valores numéricos, como dados científicos, estatísticos e de engenharia.</span><span class="sxs-lookup"><span data-stu-id="84a85-117">Scatter charts are commonly used for displaying and comparing numeric values, such as scientific, statistical, and engineering data.</span></span>  
  
-   <span data-ttu-id="84a85-118">Use o gráfico de dispersão quando quiser comparar grandes números de pontos de dados sem considerar o tempo.</span><span class="sxs-lookup"><span data-stu-id="84a85-118">Use the scatter chart when you want to compare large numbers of data points without regard to time.</span></span> <span data-ttu-id="84a85-119">Quanto mais dados você inserir em um gráfico de dispersão, melhor serão as comparações que você pode criar.</span><span class="sxs-lookup"><span data-stu-id="84a85-119">The more data that you include in a scatter chart, the better the comparisons that you can make.</span></span>  
  
-   <span data-ttu-id="84a85-120">O gráfico de bolhas requer dois valores (superior e inferior) por ponto de dados.</span><span class="sxs-lookup"><span data-stu-id="84a85-120">The bubble chart requires two values (top and bottom) per data point.</span></span>  
  
-   <span data-ttu-id="84a85-121">Os gráficos de dispersão são ideais para controlar a distribuição de valores e clusters de pontos de dados.</span><span class="sxs-lookup"><span data-stu-id="84a85-121">Scatter charts are ideal for handling the distribution of values and clusters of data points.</span></span> <span data-ttu-id="84a85-122">Este será o melhor tipo de gráfico se o seu conjunto de dados contiver muitos pontos (por exemplo, milhares de pontos).</span><span class="sxs-lookup"><span data-stu-id="84a85-122">This is the best chart type if your dataset contains many points (for example, several thousand points).</span></span> <span data-ttu-id="84a85-123">Exibir várias séries em um gráfico de pontos causa uma distração visual e deve ser evitado.</span><span class="sxs-lookup"><span data-stu-id="84a85-123">Displaying multiple series on a point chart is visually distracting and should be avoided.</span></span> <span data-ttu-id="84a85-124">Neste cenário, considere o uso de um gráfico de linha.</span><span class="sxs-lookup"><span data-stu-id="84a85-124">In this scenario, consider using a line chart.</span></span>  
  
-   <span data-ttu-id="84a85-125">Por padrão, os gráficos de dispersão exibem pontos de dados como círculos.</span><span class="sxs-lookup"><span data-stu-id="84a85-125">By default, scatter charts display data points as circles.</span></span> <span data-ttu-id="84a85-126">Se você tiver várias séries em um gráfico de dispersão, considere a possibilidade de alterar o marcador de cada ponto para outras formas, como quadrado, triângulo, losango, etc.</span><span class="sxs-lookup"><span data-stu-id="84a85-126">If you have multiple series on a scatter chart, consider changing the marker shape of each point to be square, triangle, diamond, or another shape.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84a85-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="84a85-127">See Also</span></span>  
 <span data-ttu-id="84a85-128">[Gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="84a85-128">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="84a85-129">[Tipos de gráficos &#40;Construtor de Relatórios e SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="84a85-129">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="84a85-130">[Formatando um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="84a85-130">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="84a85-131">Gráficos de linhas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="84a85-131">Line Charts &#40;Report Builder and SSRS&#41;</span></span>](line-charts-report-builder-and-ssrs.md)  
  
  
