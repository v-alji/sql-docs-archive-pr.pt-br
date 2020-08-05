---
title: Especificar uma área do gráfico para uma série (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10157"
- sql12.rtp.rptdesigner.chartareaproperties.alignment.f1
ms.assetid: dc3c365b-c263-402a-bf6f-c2a7081db073
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 483bc6d2fa4aa079c95e9dbd03e18c71d7b13abf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569075"
---
# <a name="specify-a-chart-area-for-a-series-report-builder-and-ssrs"></a><span data-ttu-id="5a610-102">Especificar uma área do gráfico para uma série (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="5a610-102">Specify a Chart Area for a Series (Report Builder and SSRS)</span></span>
  <span data-ttu-id="5a610-103">O gráfico é o contêiner de nível superior que inclui a borda exterior, o título e a legenda do gráfico.</span><span class="sxs-lookup"><span data-stu-id="5a610-103">The chart is the top-level container that includes the outer border, the chart title, and the legend.</span></span> <span data-ttu-id="5a610-104">Por padrão, o gráfico contém uma área de gráfico padrão.</span><span class="sxs-lookup"><span data-stu-id="5a610-104">By default, the chart contains one default chart area.</span></span> <span data-ttu-id="5a610-105">A área do gráfico não é visível na superfície do gráfico, mas você pode imaginá-la como um contêiner que inclui somente os rótulos e o título dos eixos e a área de plotagem de uma ou mais séries.</span><span class="sxs-lookup"><span data-stu-id="5a610-105">The chart area is not visible on the chart surface, but you can think of the chart area as a container that encompasses only the axis labels, the axis title and the plotting area of one or more series.</span></span> <span data-ttu-id="5a610-106">A ilustração a seguir mostra o conceito de áreas de gráfico dentro de um único gráfico.</span><span class="sxs-lookup"><span data-stu-id="5a610-106">The following illustration shows the concept of chart areas within a single chart.</span></span>  
  
 <span data-ttu-id="5a610-107">![Mostra um diagrama de uma área do gráfico](../media/chartareasdiagram.gif "Mostra um diagrama de uma área do gráfico")</span><span class="sxs-lookup"><span data-stu-id="5a610-107">![Shows a diagram of a chart area](../media/chartareasdiagram.gif "Shows a diagram of a chart area")</span></span>  
  
 <span data-ttu-id="5a610-108">Por padrão, todas as séries são adicionadas à área do gráfico padrão.</span><span class="sxs-lookup"><span data-stu-id="5a610-108">By default, all series are added to the default chart area.</span></span> <span data-ttu-id="5a610-109">Ao usar área, coluna, linha e gráficos de dispersão, qualquer combinação dessas séries pode ser exibida na mesma área do gráfico.</span><span class="sxs-lookup"><span data-stu-id="5a610-109">When using area, column, line, and scatter charts, any combination of these series can be displayed on the same chart area.</span></span> <span data-ttu-id="5a610-110">Caso haja várias séries na mesma área de gráfico, a legibilidade do gráfico é reduzida.</span><span class="sxs-lookup"><span data-stu-id="5a610-110">If you have several series in the same chart area, the readability of the chart is reduced.</span></span> <span data-ttu-id="5a610-111">Talvez você queira separar os tipos de gráfico em várias áreas.</span><span class="sxs-lookup"><span data-stu-id="5a610-111">You may want to separate the chart types into multiple chart areas.</span></span> <span data-ttu-id="5a610-112">Usar várias áreas de gráfico aumentará a legibilidade, tendo em vista comparações mais fáceis.</span><span class="sxs-lookup"><span data-stu-id="5a610-112">Using multiple chart areas will increase readability for easier comparisons.</span></span> <span data-ttu-id="5a610-113">Por exemplo, gráficos de ações por volume/preço costumam apresentar intervalos diferentes, mas as comparações podem ser feitas entre os dados de preço e volume no mesmo período.</span><span class="sxs-lookup"><span data-stu-id="5a610-113">For example, price-volume stock charts often have different ranges of values, but comparisons can be made between the price and volume data over the same period of time.</span></span>  
  
 <span data-ttu-id="5a610-114">As séries de barras, polar ou com forma só podem ser combinadas com séries dos mesmos tipos de gráfico na mesma área de gráfico.</span><span class="sxs-lookup"><span data-stu-id="5a610-114">The bar, polar, or shape series can only be combined with series of the same chart types in the same chart area.</span></span> <span data-ttu-id="5a610-115">Caso você esteja usando um gráfico polar ou com forma, considere usar uma região de dados do gráfico separada para cada campo que deseja mostrar.</span><span class="sxs-lookup"><span data-stu-id="5a610-115">If you are using a Polar or Shape chart, consider using a separate chart data region for each field that you wish to show.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-associate-a-series-with-a-new-chart-area"></a><span data-ttu-id="5a610-116">Para associar uma série a uma nova área de gráfico</span><span class="sxs-lookup"><span data-stu-id="5a610-116">To associate a series with a new chart area</span></span>  
  
1.  <span data-ttu-id="5a610-117">Clique com o botão direito do mouse em qualquer lugar do gráfico e selecione **Adicionar Nova Área de Gráfico**.</span><span class="sxs-lookup"><span data-stu-id="5a610-117">Right-click anywhere on the chart and select **Add New Chart Area**.</span></span> <span data-ttu-id="5a610-118">Uma nova área de gráfico, em branco, é exibida no gráfico.</span><span class="sxs-lookup"><span data-stu-id="5a610-118">A new, blank chart area appears on the chart.</span></span>  
  
2.  <span data-ttu-id="5a610-119">Clique com o botão direito do mouse na série do gráfico ou em uma série ou em um campo de dados na área apropriada do painel Dados do Gráfico e clique em **Propriedades da Série**.</span><span class="sxs-lookup"><span data-stu-id="5a610-119">Right-click the series on the chart or right-click a series or data field in the appropriate area in the Chart Data pane, and then click **Series Properties**.</span></span>  
  
3.  <span data-ttu-id="5a610-120">Em **Eixos e Áreas do Gráfico**, selecione a área do gráfico em que você deseja mostrar a série.</span><span class="sxs-lookup"><span data-stu-id="5a610-120">In **Axes and Chart Areas**, select the chart area that you want the series to be shown in.</span></span>  
  
4.  <span data-ttu-id="5a610-121">(Opcional) Alinhe as áreas de gráfico verticalmente.</span><span class="sxs-lookup"><span data-stu-id="5a610-121">(Optional) Align the chart areas vertically.</span></span> <span data-ttu-id="5a610-122">Para isso, clique com o botão direito do mouse no gráfico e selecione **Propriedades da Área do Gráfico**.</span><span class="sxs-lookup"><span data-stu-id="5a610-122">To do this, right-click the chart and select **Chart Area Properties**.</span></span> <span data-ttu-id="5a610-123">Em **Alinhamento**, selecione outra área de gráfico com a qual você deseja alinhar a área de gráfico selecionada.</span><span class="sxs-lookup"><span data-stu-id="5a610-123">In **Alignment**, select another chart area that you want to align the selected chart area with.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a610-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5a610-124">See Also</span></span>  
 <span data-ttu-id="5a610-125">[Várias séries em um gráfico &#40;Construtor de Relatórios e SSRS&#41;](multiple-series-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5a610-125">[Multiple Series on a Chart &#40;Report Builder and SSRS&#41;](multiple-series-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5a610-126">[Formatando pontos de dados em um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5a610-126">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5a610-127">[Definir cores em um gráfico usando uma paleta &#40;Construtor de Relatórios e SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5a610-127">[Define Colors on a Chart Using a Palette &#40;Report Builder and SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5a610-128">[Gráficos polares &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5a610-128">[Polar Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5a610-129">[Gráficos de forma &#40;Construtor de Relatórios e SSRS&#41;](shape-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5a610-129">[Shape Charts &#40;Report Builder and SSRS&#41;](shape-charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="5a610-130">Gráficos de pizza &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5a610-130">Pie Charts &#40;Report Builder and SSRS&#41;</span></span>](pie-charts-report-builder-and-ssrs.md)  
  
  
