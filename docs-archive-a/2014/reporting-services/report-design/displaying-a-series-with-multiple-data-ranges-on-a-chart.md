---
title: Exibindo uma série com vários intervalos de dados em um gráfico (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 45da3d39-278e-4760-a4b3-9932c9547cf2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: dfe378f3fb5aa50ddf02f95b2b4be04dd1ae6ac5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570445"
---
# <a name="displaying-a-series-with-multiple-data-ranges-on-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="2fc11-102">Exibindo uma série com vários intervalos de dados em um gráfico (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="2fc11-102">Displaying a Series with Multiple Data Ranges on a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="2fc11-103">O gráfico usará os valores mínimo e máximo de uma série para calcular a escala do eixo.</span><span class="sxs-lookup"><span data-stu-id="2fc11-103">Chart will use the minimum and maximum values of a series to calculate the axis scale.</span></span> <span data-ttu-id="2fc11-104">Quando uma série do gráfico contiver mais que um intervalo de dados, os pontos de dados poderão ficar obscuros e apenas alguns deles poderão ser visualizados facilmente no gráfico.</span><span class="sxs-lookup"><span data-stu-id="2fc11-104">When a series on your chart contains more than one range of data, the data points can become obscured, and only a few data points to be seen easily on the chart.</span></span> <span data-ttu-id="2fc11-105">Por exemplo, suponha que um relatório exiba informações sobre o total de vendas diário de um período de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="2fc11-105">For example, suppose a report displays daily sales totals over a period of 30 days.</span></span>  
  
 <span data-ttu-id="2fc11-106">![Gráfico com vários intervalos de dados](../media/rs-multipledatarangeschart.gif "Gráfico com vários intervalos de dados")</span><span class="sxs-lookup"><span data-stu-id="2fc11-106">![Chart with multiple data ranges](../media/rs-multipledatarangeschart.gif "Chart with multiple data ranges")</span></span>  
  
 <span data-ttu-id="2fc11-107">Na maior parte do mês, as vendas ficam entre 10 e 40.</span><span class="sxs-lookup"><span data-stu-id="2fc11-107">For most of the month, the sales are between 10 and 40.</span></span> <span data-ttu-id="2fc11-108">No entanto, uma campanha publicitária de uma semana provocou um aumento repentino nas vendas no início de abril.</span><span class="sxs-lookup"><span data-stu-id="2fc11-108">However, a one-week sales marketing campaign has caused a sudden sales increase at the beginning of April.</span></span> <span data-ttu-id="2fc11-109">Essa alteração nos dados de vendas produz uma distribuição irregular dos pontos de dados que reduz a legibilidade geral do gráfico.</span><span class="sxs-lookup"><span data-stu-id="2fc11-109">This change in sales data produces an uneven distribution of data points that reduces the overall readability of the chart.</span></span>  
  
 <span data-ttu-id="2fc11-110">Existem maneiras diferentes de melhorar a legibilidade:</span><span class="sxs-lookup"><span data-stu-id="2fc11-110">There are different ways to improve readability:</span></span>  
  
-   <span data-ttu-id="2fc11-111">**Habilitar quebras de escala**.</span><span class="sxs-lookup"><span data-stu-id="2fc11-111">**Enable scale breaks**.</span></span> <span data-ttu-id="2fc11-112">Se os dados formarem dois ou mais conjuntos de intervalos de dados, use uma quebra de escala para remover a lacuna entre os intervalos.</span><span class="sxs-lookup"><span data-stu-id="2fc11-112">If your data forms two or more sets of data ranges, use a scale break to remove the gap between the ranges.</span></span> <span data-ttu-id="2fc11-113">Uma quebra de escala é uma faixa desenhada em uma área de plotagem para indicar a quebra entre os valores altos e baixos de uma série.</span><span class="sxs-lookup"><span data-stu-id="2fc11-113">A scale break is a stripe drawn across the plotting area to denote a break between the high and low values of a series.</span></span>  
  
-   <span data-ttu-id="2fc11-114">**Filtrar valores desnecessários**.</span><span class="sxs-lookup"><span data-stu-id="2fc11-114">**Filter out unnecessary values**.</span></span> <span data-ttu-id="2fc11-115">Se houver pontos de dados que estão encobrindo um intervalo de dados importante que deve aparecer no gráfico, remova os pontos indesejados usando um filtro de relatório.</span><span class="sxs-lookup"><span data-stu-id="2fc11-115">If you have data points that are obscuring the important data range to be displayed on the chart, remove the unwanted points using a report filter.</span></span> <span data-ttu-id="2fc11-116">Para obter informações sobre como adicionar um filtro ao gráfico no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], consulte [Adicionar filtros de conjunto de dados, de região de dados e de grupo &#40;Construtor de Relatórios e SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md).</span><span class="sxs-lookup"><span data-stu-id="2fc11-116">For information on how to add a filter to the chart in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], see [Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md).</span></span>  
  
-   <span data-ttu-id="2fc11-117">**Plotar cada intervalo de dados como uma série separada para comparar várias séries**.</span><span class="sxs-lookup"><span data-stu-id="2fc11-117">**Plot each data range as a separate series for multiple series comparison**.</span></span> <span data-ttu-id="2fc11-118">Se houver dois ou mais intervalos de dados, considere separá-los em séries distintas.</span><span class="sxs-lookup"><span data-stu-id="2fc11-118">If you have more than two data ranges, consider separating the data ranges into separate series.</span></span> <span data-ttu-id="2fc11-119">Para obter mais informações, consulte [Várias séries em um gráfico &#40;Construtor de Relatórios e SSRS&#41;](multiple-series-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2fc11-119">For more information, see [Multiple Series on a Chart &#40;Report Builder and SSRS&#41;](multiple-series-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="displaying-multiple-data-ranges-using-scale-breaks"></a><span data-ttu-id="2fc11-120">Exibindo vários intervalos de dados usando quebras de escala</span><span class="sxs-lookup"><span data-stu-id="2fc11-120">Displaying Multiple Data Ranges Using Scale Breaks</span></span>  
 <span data-ttu-id="2fc11-121">Quando você habilita uma quebra de escala, o gráfico calcula onde desenhar uma linha no gráfico.</span><span class="sxs-lookup"><span data-stu-id="2fc11-121">When you enable a scale break, the chart calculates where to draw a line across the chart.</span></span> <span data-ttu-id="2fc11-122">Deve haver espaço suficiente entre os intervalos para desenhar uma quebra de escala.</span><span class="sxs-lookup"><span data-stu-id="2fc11-122">You must have sufficient separation between ranges to draw a scale break.</span></span> <span data-ttu-id="2fc11-123">Por padrão, a quebra de escala poderá ser adicionada somente se houver uma separação entre os intervalos de dados de pelo menos 25% do gráfico.</span><span class="sxs-lookup"><span data-stu-id="2fc11-123">By default, a scale break can be added only if there is a separation between the data ranges of at least 25% of the chart.</span></span>  
  
 <span data-ttu-id="2fc11-124">![Gráfico com quebra de escala](../media/rs-multipledatarangeschart-scalebreak.gif "Gráfico com quebra de escala")</span><span class="sxs-lookup"><span data-stu-id="2fc11-124">![Chart with scale break](../media/rs-multipledatarangeschart-scalebreak.gif "Chart with scale break")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2fc11-125">Não é possível especificar onde posicionar a quebra de escala em um gráfico.</span><span class="sxs-lookup"><span data-stu-id="2fc11-125">You cannot specify where to place a scale break on a chart.</span></span> <span data-ttu-id="2fc11-126">No entanto, você pode modificar como ela será calculada, o que será descrito adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="2fc11-126">You can, however, modify how the scale break is calculated, described later in this topic.</span></span>  
  
 <span data-ttu-id="2fc11-127">Se você habilitar uma quebra de escala mas ela não aparecer, mesmo que haja distância suficiente entre os intervalos de dados, será possível definir a propriedade CollapsibleSpaceThreshold com um valor inferior a 25.</span><span class="sxs-lookup"><span data-stu-id="2fc11-127">If you enable a scale break but it does not appear, even though there is sufficient distance between the data ranges, you can set the CollapsibleSpaceThreshold property to a value less than 25.</span></span> <span data-ttu-id="2fc11-128">CollapsibleSpaceThreshold especifica o percentual de espaço recolhível necessário entre os intervalos de dados.</span><span class="sxs-lookup"><span data-stu-id="2fc11-128">The CollapsibleSpaceThreshold specifies the percent of collapsible space required between the data ranges.</span></span> <span data-ttu-id="2fc11-129">Para obter mais informações, consulte [Adicionar quebras de escala a um gráfico &#40;Construtor de Relatórios e SSRS&#41;](add-scale-breaks-to-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2fc11-129">For more information, see [Add Scale Breaks to a Chart &#40;Report Builder and SSRS&#41;](add-scale-breaks-to-a-chart-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="2fc11-130">Os gráficos suportam até cinco quebras de escala por gráfico; no entanto, exibir mais de uma quebra de escala pode deixar o gráfico ilegível.</span><span class="sxs-lookup"><span data-stu-id="2fc11-130">Charts support up to five scale breaks per chart; however, displaying more than one scale break can cause the chart to become unreadable.</span></span> <span data-ttu-id="2fc11-131">Se houver dois ou mais intervalos de dados, considere o uso de outro método para exibir esses dados.</span><span class="sxs-lookup"><span data-stu-id="2fc11-131">If you have more than two data ranges, consider using a different method for displaying this data.</span></span> <span data-ttu-id="2fc11-132">Para obter mais informações, consulte [Várias séries em um gráfico &#40;Construtor de Relatórios e SSRS&#41;](multiple-series-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2fc11-132">For more information, see [Multiple Series on a Chart &#40;Report Builder and SSRS&#41;](multiple-series-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
## <a name="unsupported-scale-break-scenarios"></a><span data-ttu-id="2fc11-133">Cenários de quebra de escala não suportados</span><span class="sxs-lookup"><span data-stu-id="2fc11-133">Unsupported Scale Break Scenarios</span></span>  
 <span data-ttu-id="2fc11-134">As quebras de escala não são suportadas nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="2fc11-134">Scale breaks are not supported in the following chart scenarios:</span></span>  
  
-   <span data-ttu-id="2fc11-135">O gráfico está habilitado para 3D.</span><span class="sxs-lookup"><span data-stu-id="2fc11-135">The chart is 3-D enabled.</span></span>  
  
-   <span data-ttu-id="2fc11-136">Um eixo de valor logarítmico foi especificado.</span><span class="sxs-lookup"><span data-stu-id="2fc11-136">A logarithmic value axis has been specified.</span></span>  
  
-   <span data-ttu-id="2fc11-137">O eixo de valor mínimo ou máximo foi definido explicitamente.</span><span class="sxs-lookup"><span data-stu-id="2fc11-137">The value axis minimum or maximum has been explicitly set.</span></span>  
  
-   <span data-ttu-id="2fc11-138">O tipo de gráfico é polar, radar, pizza, anel, funil, pirâmide ou algum gráfico empilhado.</span><span class="sxs-lookup"><span data-stu-id="2fc11-138">The chart type is polar, radar, pie, doughnut, funnel, pyramid, or any stacked chart.</span></span>  
  
 <span data-ttu-id="2fc11-139">Um exemplo de gráfico com quebras de escala está disponível como um relatório de exemplo.</span><span class="sxs-lookup"><span data-stu-id="2fc11-139">An example of chart with scale breaks is available as a sample report.</span></span> <span data-ttu-id="2fc11-140">Para obter mais informações sobre como baixar este relatório de exemplo e outros, consulte [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [Construtor de Relatórios e Report Designer relatórios de exemplo](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="2fc11-140">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fc11-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2fc11-141">See Also</span></span>  
 <span data-ttu-id="2fc11-142">[Várias séries em um gráfico &#40;Construtor de Relatórios e SSRS&#41;](multiple-series-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2fc11-142">[Multiple Series on a Chart &#40;Report Builder and SSRS&#41;](multiple-series-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2fc11-143">[Formatando um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2fc11-143">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2fc11-144">[3D, bisel e outros efeitos em um gráfico &#40;Construtor de Relatórios e SSRS&#41;](chart-effects-3d-bevel-and-other-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="2fc11-144">[3D, Bevel, and Other Effects in a Chart &#40;Report Builder and SSRS&#41;](chart-effects-3d-bevel-and-other-report-builder.md) </span></span>  
 <span data-ttu-id="2fc11-145">[Gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2fc11-145">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2fc11-146">[Caixa de diálogo Propriedades do eixo, opções de eixo &#40;Construtor de Relatórios e SSRS&#41;](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2fc11-146">[Axis Properties Dialog Box, Axis Options &#40;Report Builder and SSRS&#41;](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="2fc11-147">Coletar fatias pequenas em um gráfico de pizza &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2fc11-147">Collect Small Slices on a Pie Chart &#40;Report Builder and SSRS&#41;</span></span>](collect-small-slices-on-a-pie-chart-report-builder-and-ssrs.md)  
  
  