---
title: Gráficos de barras (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: db0cf6a0-2114-41d0-ab27-0319e52dee76
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 483266607bc021a5c5a0a946aff6e7202248c582
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573758"
---
# <a name="bar-charts-report-builder-and-ssrs"></a><span data-ttu-id="44e77-102">Gráficos de barras (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="44e77-102">Bar Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="44e77-103">Um gráfico de barras exibe as séries como conjuntos de barras horizontais.</span><span class="sxs-lookup"><span data-stu-id="44e77-103">A bar chart displays series as sets of horizontal bars.</span></span> <span data-ttu-id="44e77-104">O gráfico de barras plano está bem relacionado ao gráfico de colunas, que exibe uma série como conjuntos de barras verticais e o gráfico de barras de intervalo, que exibe uma série como conjuntos de barras horizontais com pontos de início e término variáveis.</span><span class="sxs-lookup"><span data-stu-id="44e77-104">The plain bar chart is closely related to the column chart, which displays series as sets of vertical bars, and the range bar chart, which displays series as sets of horizontal bars with varying beginning and end points.</span></span>  
  
 <span data-ttu-id="44e77-105">O gráfico de barras é o único tipo de gráfico que exibe dados horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="44e77-105">The bar chart is the only chart type that displays data horizontally.</span></span> <span data-ttu-id="44e77-106">Por esse motivo, é conhecido por representar dados que ocorrem com o tempo, com uma data inicial e final finita.</span><span class="sxs-lookup"><span data-stu-id="44e77-106">For this reason, it is popular for representing data that occurs over time, with a finite start and end date.</span></span> <span data-ttu-id="44e77-107">Também é conhecido por mostrar informações categóricas uma vez que as categorias podem ser exibidas horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="44e77-107">It is also popular for showing categorical information since the categories can be displayed horizontally.</span></span> <span data-ttu-id="44e77-108">Para obter mais informações sobre como adicionar dados a um gráfico de barras, consulte [Gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="44e77-108">For more information about how to add data to a bar chart, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="44e77-109">A ilustração a seguir mostra um gráfico de barras.</span><span class="sxs-lookup"><span data-stu-id="44e77-109">The following illustration shows a bar chart.</span></span> <span data-ttu-id="44e77-110">O gráfico de barras é o mais adequado para esses dados porque todas as três séries compartilham um período de tempo comum, permitindo que sejam feitas comparações válidas.</span><span class="sxs-lookup"><span data-stu-id="44e77-110">The bar chart is well suited for this data because all three series share a common time period, allowing for valid comparisons to be made.</span></span>  
  
 <span data-ttu-id="44e77-111">![Gráfico de barras](../media/barchart.gif "Gráfico de barras")</span><span class="sxs-lookup"><span data-stu-id="44e77-111">![Bar chart](../media/barchart.gif "Bar chart")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations-of-the-bar-chart"></a><span data-ttu-id="44e77-112">Variações do gráfico de barras</span><span class="sxs-lookup"><span data-stu-id="44e77-112">Variations of the Bar Chart</span></span>  
  
-   <span data-ttu-id="44e77-113">**Empilhado**.</span><span class="sxs-lookup"><span data-stu-id="44e77-113">**Stacked**.</span></span> <span data-ttu-id="44e77-114">Um gráfico de barras no qual várias séries são empilhadas verticalmente.</span><span class="sxs-lookup"><span data-stu-id="44e77-114">A bar chart where multiple series are stacked vertically.</span></span> <span data-ttu-id="44e77-115">Se houver apenas uma série em seu gráfico, o gráfico de barras empilhadas exibirá o mesmo que o gráfico de barras.</span><span class="sxs-lookup"><span data-stu-id="44e77-115">If there is only one series in your chart, the stacked bar chart will display the same as a bar chart.</span></span>  
  
-   <span data-ttu-id="44e77-116">**Por cento empilhado**.</span><span class="sxs-lookup"><span data-stu-id="44e77-116">**Percent stacked**.</span></span> <span data-ttu-id="44e77-117">Um gráfico de barras no qual várias séries são empilhadas verticalmente para se ajustarem a 100% da área do gráfico.</span><span class="sxs-lookup"><span data-stu-id="44e77-117">A bar chart where multiple series are stacked vertically to fit 100% of the chart area.</span></span> <span data-ttu-id="44e77-118">Se houver apenas uma série em seu gráfico, todas as barras serão ajustadas a 100% da área do gráfico.</span><span class="sxs-lookup"><span data-stu-id="44e77-118">If there is only one series in your chart, all the bars will fit to 100% of the chart area.</span></span>  
  
-   <span data-ttu-id="44e77-119">**3D clusterizado**.</span><span class="sxs-lookup"><span data-stu-id="44e77-119">**3D clustered**.</span></span> <span data-ttu-id="44e77-120">Um gráfico de barras que mostra séries individuais em linhas separadas em um gráfico 3D.</span><span class="sxs-lookup"><span data-stu-id="44e77-120">A bar chart that shows individual series in separate rows on a 3D chart.</span></span>  
  
-   <span data-ttu-id="44e77-121">**Cilindro em 3D**.</span><span class="sxs-lookup"><span data-stu-id="44e77-121">**3D cylinder**.</span></span> <span data-ttu-id="44e77-122">Um gráfico de barras que molda as barras como cilindros em um gráfico 3D.</span><span class="sxs-lookup"><span data-stu-id="44e77-122">A bar chart that shapes the bars as cylinders on a 3D chart.</span></span>  
  
## <a name="data-considerations-for-bar-charts"></a><span data-ttu-id="44e77-123">Considerações de dados para gráficos de barras</span><span class="sxs-lookup"><span data-stu-id="44e77-123">Data Considerations for Bar Charts</span></span>  
  
-   <span data-ttu-id="44e77-124">Os gráficos de barras têm os eixos invertidos.</span><span class="sxs-lookup"><span data-stu-id="44e77-124">Bar charts have their axes reversed.</span></span> <span data-ttu-id="44e77-125">O eixo de categoria é o eixo vertical (ou "eixo y") e o eixo de valor é o eixo horizontal (ou "eixo x").</span><span class="sxs-lookup"><span data-stu-id="44e77-125">The category axis is the vertical axis (or "y-axis") and the value axis is the horizontal axis (or "x-axis").</span></span> <span data-ttu-id="44e77-126">Isso significa que em um gráfico de barras, você tem mais espaço para rótulos de categoria a serem exibidos ao longo do eixo y como uma lista que é lida da parte superior para a inferior.</span><span class="sxs-lookup"><span data-stu-id="44e77-126">This means that in a bar chart, you have more space for category labels to be displayed along the y-axis as a list that reads from top to bottom.</span></span>  
  
-   <span data-ttu-id="44e77-127">Gráficos de barras e colunas são usados com mais frequência para mostrar comparações entre grupos.</span><span class="sxs-lookup"><span data-stu-id="44e77-127">Bar and column charts are most commonly used to show comparisons between groups.</span></span> <span data-ttu-id="44e77-128">Se mais de três séries estiverem presentes no gráfico, considere usar um gráfico de colunas ou barras empilhadas.</span><span class="sxs-lookup"><span data-stu-id="44e77-128">If more than three series are present on the chart, consider using a stacked bar or column chart.</span></span> <span data-ttu-id="44e77-129">Você também pode coletar gráficos de barras ou colunas empilhadas em vários grupos se tiver várias séries em seu gráfico.</span><span class="sxs-lookup"><span data-stu-id="44e77-129">You can also collect stacked bar or column charts into multiple groups if you have several series on your chart.</span></span>  
  
-   <span data-ttu-id="44e77-130">Um gráfico de barras exibe valores da esquerda para a direita, que pode ser mais intuitivo ao exibir dados relacionados a durações.</span><span class="sxs-lookup"><span data-stu-id="44e77-130">A bar chart displays values from left to right, which may be more intuitive when displaying data related to durations.</span></span>  
  
-   <span data-ttu-id="44e77-131">Se estiver procurando para adicionar barras a uma tabela ou matriz no relatório, considere usar um medidor linear em vez de um gráfico de barras.</span><span class="sxs-lookup"><span data-stu-id="44e77-131">If you are looking to add bars to a table or matrix within the report, consider using a linear gauge instead of a bar chart.</span></span> <span data-ttu-id="44e77-132">O medidor linear é projetado para mostrar um valor em vez de vários grupos para que seja mais flexível para ser usado em uma lista ou região de dados da tabela.</span><span class="sxs-lookup"><span data-stu-id="44e77-132">The linear gauge is designed to show one value instead of multiple groups, so it is more flexible for use within a list or table data region.</span></span> <span data-ttu-id="44e77-133">Para obter mais informações, consulte [Medidores &#40;Construtor de Relatórios e SSRS&#41;](gauges-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="44e77-133">For more information, see [Gauges &#40;Report Builder and SSRS&#41;](gauges-report-builder-and-ssrs.md).</span></span>  
  
-   <span data-ttu-id="44e77-134">Você pode adicionar estilos de desenho especiais às barras individuais em um gráfico de barras para aumentar seu impacto visual.</span><span class="sxs-lookup"><span data-stu-id="44e77-134">You can add special drawing styles to the individual bars on a bar chart to increase its visual impact.</span></span> <span data-ttu-id="44e77-135">Os estilos de desenho incluem entalhe, relevo, cilindro e claro para escuro.</span><span class="sxs-lookup"><span data-stu-id="44e77-135">Drawing styles include wedge, emboss, cylinder, and light-to-dark.</span></span> <span data-ttu-id="44e77-136">Esses efeitos são projetados para melhorar a aparência de seu gráfico 2D.</span><span class="sxs-lookup"><span data-stu-id="44e77-136">These effects are designed to improve the appearance of your 2D chart.</span></span> <span data-ttu-id="44e77-137">Se estiver usando um gráfico 3D, os estilos de desenho ainda serão aplicados, mas podem não ter o mesmo efeito.</span><span class="sxs-lookup"><span data-stu-id="44e77-137">If you are using a 3D chart, the drawing styles will still be applied, but may not have the same effect.</span></span> <span data-ttu-id="44e77-138">Para obter mais informações sobre como adicionar um estilo de desenho a um gráfico de barras, consulte [Adicionar estilos de bisel, relevo e textura a um gráfico &#40;Construtor de Relatórios e SSRS&#41;](chart-effects-add-bevel-emboss-or-texture-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="44e77-138">For more information about how to add a drawing style to a bar chart, see [Add Bevel, Emboss, and Texture Styles to a Chart &#40;Report Builder and SSRS&#41;](chart-effects-add-bevel-emboss-or-texture-report-builder.md).</span></span>  
  
-   <span data-ttu-id="44e77-139">Os gráficos de barras empilhados sobrepõem séries para criar uma pilha de barras.</span><span class="sxs-lookup"><span data-stu-id="44e77-139">Stacked bar charts place series on top of each other to create one bar stack.</span></span> <span data-ttu-id="44e77-140">Você tem a opção de separar o gráfico de barras empilhado em vários conjuntos de pilhas para cada categoria.</span><span class="sxs-lookup"><span data-stu-id="44e77-140">You have the option of separating the stacked bar chart into multiple sets of stacks for each category.</span></span> <span data-ttu-id="44e77-141">O gráfico empilhado agrupado é exibido lado a lado.</span><span class="sxs-lookup"><span data-stu-id="44e77-141">The grouped stacked chart is displayed side-by-side.</span></span> <span data-ttu-id="44e77-142">É possível haver qualquer número de séries empilhadas agrupadas em um gráfico.</span><span class="sxs-lookup"><span data-stu-id="44e77-142">You can have any number of grouped stacked series in a chart.</span></span>  
  
-   <span data-ttu-id="44e77-143">Quando rótulos de ponto de dados são mostrados em um gráfico de barras, os rótulos são colocados fora de cada barra.</span><span class="sxs-lookup"><span data-stu-id="44e77-143">When data point labels are shown on a bar chart, the labels are placed on the outside of each bar.</span></span> <span data-ttu-id="44e77-144">Isso pode fazer com que os rótulos se sobreponham quando as barras ocuparem todo o espaço dividido dentro da área do gráfico.</span><span class="sxs-lookup"><span data-stu-id="44e77-144">This can cause labels to overlap when the bars take up all of the allotted space within the chart area.</span></span> <span data-ttu-id="44e77-145">É possível alterar a posição dos rótulos de ponto de dados exibida para cada barra definindo a propriedade **BarLabelStyle** no painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="44e77-145">You can change the position of the data point labels displayed for each bar by setting the **BarLabelStyle** property in the Properties pane.</span></span>  
  
-   <span data-ttu-id="44e77-146">Caso haja muitos pontos de dados no conjunto de dados em relação ao tamanho do gráfico, o tamanho das colunas ou das barras e do espaço entre elas é reduzido.</span><span class="sxs-lookup"><span data-stu-id="44e77-146">If there are a lot of data points in your dataset relative to the size of your chart, the size of the columns or bars and the spacing between them are reduced.</span></span> <span data-ttu-id="44e77-147">Para definir manualmente a largura das colunas de um gráfico, modifique a largura, em pixels, alterando a propriedade **PointWidth** .</span><span class="sxs-lookup"><span data-stu-id="44e77-147">To manually set the width of the columns in a chart, modify their width, in pixels, by modifying the **PointWidth** property.</span></span> <span data-ttu-id="44e77-148">Por padrão, o valor dessa propriedade é 0,8.</span><span class="sxs-lookup"><span data-stu-id="44e77-148">By default, this property has a value of 0.8.</span></span> <span data-ttu-id="44e77-149">Quando você aumenta a largura das colunas ou das barras em um gráfico, o espaço entre cada coluna ou barra diminui.</span><span class="sxs-lookup"><span data-stu-id="44e77-149">When you increase the width of the columns or bars in a chart, the space between each column or bar decreases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44e77-150">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="44e77-150">See Also</span></span>  
 <span data-ttu-id="44e77-151">[Gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="44e77-151">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="44e77-152">[Tipos de gráficos &#40;Construtor de Relatórios e SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="44e77-152">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="44e77-153">[Pontos de dados vazios e nulos em gráficos &#40;Construtor de Relatórios e SSRS&#41;](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="44e77-153">[Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="44e77-154">[Gráficos de colunas &#40;Construtor de Relatórios e SSRS&#41;](column-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="44e77-154">[Column Charts &#40;Report Builder and SSRS&#41;](column-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="44e77-155">[Gráficos de intervalo &#40;Construtor de Relatórios e SSRS&#41;](range-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="44e77-155">[Range Charts &#40;Report Builder and SSRS&#41;](range-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="44e77-156">[Formatando as cores da série em um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="44e77-156">[Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="44e77-157">[Formatando rótulos dos eixos de um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="44e77-157">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="44e77-158">[Formatando a legenda em um gráfico &#40;Construtor de Relatórios e SSRS&#41;](chart-legend-formatting-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="44e77-158">[Formatting the Legend on a Chart &#40;Report Builder and SSRS&#41;](chart-legend-formatting-report-builder.md) </span></span>  
 <span data-ttu-id="44e77-159">[Adicionar estilos de bisel, alto-relevo e textura a um gráfico &#40;Construtor de Relatórios e SSRS&#41;](chart-effects-add-bevel-emboss-or-texture-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="44e77-159">[Add Bevel, Emboss, and Texture Styles to a Chart &#40;Report Builder and SSRS&#41;](chart-effects-add-bevel-emboss-or-texture-report-builder.md) </span></span>  
 <span data-ttu-id="44e77-160">[Tutorial: Adicionando um gráfico de barras a um relatório (Construtor de Relatórios)](https://go.microsoft.com/fwlink/?LinkId=198052) </span><span class="sxs-lookup"><span data-stu-id="44e77-160">[Tutorial: Adding a Bar Chart to a Report (Report Builder)](https://go.microsoft.com/fwlink/?LinkId=198052) </span></span>  
 [<span data-ttu-id="44e77-161">Tutorial: Adicionando um gráfico de barras a um relatório</span><span class="sxs-lookup"><span data-stu-id="44e77-161">Tutorial: Adding a Bar Chart to a Report</span></span>](https://go.microsoft.com/fwlink/?LinkId=198042)  
  
  