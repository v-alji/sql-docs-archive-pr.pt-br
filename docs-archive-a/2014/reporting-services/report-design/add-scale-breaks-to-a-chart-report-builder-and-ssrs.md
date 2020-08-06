---
title: Adicionar quebras de escala a um gráfico (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 84d66436-ed62-4967-bbbd-b457593ee787
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1c081debd1e0a84158615edebdb6b84705c10e5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682128"
---
# <a name="add-scale-breaks-to-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="12193-102">Adicionar quebras de escala a um gráfico (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="12193-102">Add Scale Breaks to a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="12193-103">Uma quebra de escala é uma faixa desenhada em uma área de plotagem de um gráfico para indicar uma quebra de continuidade entre os valores altos e baixos em um eixo de valor (normalmente, o vertical, ou eixo y).</span><span class="sxs-lookup"><span data-stu-id="12193-103">A scale break is a stripe drawn across the plotting area of a chart to denote a break in continuity between the high and low values on a value axis (usually the vertical, or y-axis).</span></span> <span data-ttu-id="12193-104">Use uma quebra de escala para exibir dois intervalos distintos na mesma área do gráfico.</span><span class="sxs-lookup"><span data-stu-id="12193-104">Use a scale break to display two distinct ranges in the same chart area.</span></span>  
  
 <span data-ttu-id="12193-105">![Gráfico com quebra de escala](../media/rs-multipledatarangeschart-scalebreak.gif "Gráfico com quebra de escala")</span><span class="sxs-lookup"><span data-stu-id="12193-105">![Chart with scale break](../media/rs-multipledatarangeschart-scalebreak.gif "Chart with scale break")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12193-106">Não é possível especificar onde posicionar a quebra de escala no gráfico.</span><span class="sxs-lookup"><span data-stu-id="12193-106">You cannot specify where to place a scale break on your chart.</span></span> <span data-ttu-id="12193-107">O gráfico usa seus próprios cálculos com base nos valores do conjunto de dados para determinar se há separação suficiente entre os intervalos de dados para desenhar uma quebra de escala no eixo de valor (eixo y) em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="12193-107">The chart uses its own calculations based on the values in your dataset to determine whether there is sufficient separation between data ranges to draw a scale break on the value axis (y-axis) at run time.</span></span>  
  
 <span data-ttu-id="12193-108">Um exemplo de gráfico com quebras de escala está disponível como um relatório de exemplo.</span><span class="sxs-lookup"><span data-stu-id="12193-108">An example of a chart with scale breaks is available as a sample report.</span></span> <span data-ttu-id="12193-109">Para obter mais informações sobre como baixar este relatório de exemplo e outros, consulte [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [Construtor de Relatórios e Report Designer relatórios de exemplo](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="12193-109">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-enable-scale-breaks-on-the-chart"></a><span data-ttu-id="12193-110">Para habilitar quebras de escala no gráfico</span><span class="sxs-lookup"><span data-stu-id="12193-110">To enable scale breaks on the chart</span></span>  
  
1.  <span data-ttu-id="12193-111">Clique com o botão direito do mouse no eixo vertical e clique em **Propriedades do Eixo**.</span><span class="sxs-lookup"><span data-stu-id="12193-111">Right-click the vertical axis and then click **Axis Properties**.</span></span> <span data-ttu-id="12193-112">A caixa de diálogo **Propriedades VerticalAxis** é aberta.</span><span class="sxs-lookup"><span data-stu-id="12193-112">The **VerticalAxis Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="12193-113">Marque a caixa de seleção **Habilitar quebras de escala** .</span><span class="sxs-lookup"><span data-stu-id="12193-113">Select the **Enable scale breaks** check box.</span></span>  
  
### <a name="to-change-the-style-of-the-scale-break"></a><span data-ttu-id="12193-114">Para alterar o estilo da quebra de escala</span><span class="sxs-lookup"><span data-stu-id="12193-114">To change the style of the scale break</span></span>  
  
1.  <span data-ttu-id="12193-115">Abra o painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="12193-115">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="12193-116">Na superfície de design, clique com o botão direito do mouse no eixo y do gráfico.</span><span class="sxs-lookup"><span data-stu-id="12193-116">On the design surface, right-click on the y-axis of the chart.</span></span> <span data-ttu-id="12193-117">As propriedades do objeto do eixo y (denominado Eixo do Gráfico, por padrão) são exibidas no painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="12193-117">The properties for the y-axis object (named Chart Axis by default) are displayed in the Properties pane.</span></span>  
  
3.  <span data-ttu-id="12193-118">Na seção **Escala** , expanda a propriedade ScaleBreakStyle.</span><span class="sxs-lookup"><span data-stu-id="12193-118">In the **Scale** section, expand the ScaleBreakStyle property.</span></span>  
  
4.  <span data-ttu-id="12193-119">Altere os valores das propriedades ScaleBreakStyle, como BreakLineType e Spacing.</span><span class="sxs-lookup"><span data-stu-id="12193-119">Change the values for ScaleBreakStyle properties, such as BreakLineType and Spacing.</span></span> <span data-ttu-id="12193-120">Para obter mais informações sobre propriedades de quebra de escala, consulte [Exibindo uma série com vários intervalos de dados em um gráfico &#40;Construtor de Relatórios e SSRS&#41;](displaying-a-series-with-multiple-data-ranges-on-a-chart.md).</span><span class="sxs-lookup"><span data-stu-id="12193-120">For more information about scale break properties, see [Displaying a Series with Multiple Data Ranges on a Chart &#40;Report Builder and SSRS&#41;](displaying-a-series-with-multiple-data-ranges-on-a-chart.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12193-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="12193-121">See Also</span></span>  
 <span data-ttu-id="12193-122">[Gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="12193-122">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="12193-123">[Formatando um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="12193-123">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="12193-124">Caixa de diálogo Propriedades do Eixo, Opções do Eixo &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="12193-124">Axis Properties Dialog Box, Axis Options &#40;Report Builder and SSRS&#41;</span></span>](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md)  
  
  
