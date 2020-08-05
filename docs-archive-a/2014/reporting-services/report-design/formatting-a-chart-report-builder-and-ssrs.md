---
title: Formatando um gráfico (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10214"
- sql12.rtp.rptdesigner.calculatedseriesproperties.fill.f1
- sql12.rtp.rptdesigner.serieslabelproperties.fill.f1
- sql12.rtp.rptdesigner.legendproperties.fill.f1
- "10149"
- sql12.rtp.rptdesigner.seriesproperties.shadow.f1
- sql12.rtp.rptdesigner.seriesproperties.markers.f1
- "10255"
- sql12.rtp.rptdesigner.charttitleproperties.fill.f1
- "10154"
- "10170"
- "10173"
- sql12.rtp.rptdesigner.seriesproperties.fill.f1
- "10169"
- "10158"
- sql12.rtp.rptdesigner.chartareaproperties.fill.f1
- sql12.rtp.rptdesigner.charttitleproperties.shadow.f1
- "10246"
- "10150"
- sql12.rtp.rptdesigner.calculatedseriesproperties.borders.f1
- sql12.rtp.rptdesigner.chartproperties.fill.f1
- "10159"
- sql12.rtp.rptdesigner.majorgridlineproperties.gridlineoptions.f1
- "10160"
- sql12.rtp.rptdesigner.serieslabelproperties.font.f1
- "10182"
- "10163"
- "10164"
- "10253"
- "10216"
- "10171"
- "10257"
- sql12.rtp.rptdesigner.chartareaproperties.border.f1
- sql12.rtp.rptdesigner.calculatedseriesproperties.shadow.f1
- sql12.rtp.rptdesigner.chartproperties.border.f1
- sql12.rtp.rptdesigner.minorgridlineproperties.gridlineoptions.f1
- sql12.rtp.rptdesigner.chartareaproperties.shadow.f1
- sql12.rtp.rptdesigner.charttitleproperties.borders.f1
- sql12.rtp.rptdesigner.charttitleproperties.font.f1
- "10247"
ms.assetid: d3984300-c766-42f8-b7c4-863123d67c99
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: af164d4db9b6439f0634d113652b95939827b0f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572388"
---
# <a name="formatting-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="10860-102">Formatando um gráfico (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="10860-102">Formatting a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="10860-103">Quando você tiver definido os dados do gráfico e estiver satisfeito com a sua aparência, poderá adicionar a formatação para melhorá-lo em geral e realçar os principais pontos de dados.</span><span class="sxs-lookup"><span data-stu-id="10860-103">After you have defined the data for your chart and it is appearing the way you want, you can add formatting to improve the overall appearance and highlight key data points.</span></span> <span data-ttu-id="10860-104">As opções de formatação mais comuns podem ser modificadas na caixa de diálogo Propriedades que são encontradas quando você clica com o botão direito do mouse em um elemento do gráfico para exibir o menu de atalho correspondente.</span><span class="sxs-lookup"><span data-stu-id="10860-104">The most common formatting options can be modified from the Properties dialog box that are found when you right-click a chart element to display its shortcut menu.</span></span> <span data-ttu-id="10860-105">Cada elemento do gráfico possui sua própria caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="10860-105">Each chart element has its own dialog box.</span></span> <span data-ttu-id="10860-106">Para obter mais informações sobre elementos de gráfico, consulte [Gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="10860-106">For more information about chart elements, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="10860-107">Todas as propriedades relacionadas ao gráfico estão localizadas no painel Propriedades, mas muitas dessas propriedades podem também ser definidas em uma caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="10860-107">All properties that relate to the chart are located in the Properties pane, but many of these properties can also be set from a dialog box.</span></span> <span data-ttu-id="10860-108">Se você estiver formatando a série, poderá especificar as propriedades específicas à série usando atributos personalizados que podem ser encontrados somente na categoria de propriedades **CustomAttributes** , localizada no painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="10860-108">If you are formatting the series, you can specify series-specific properties using custom attributes, which can only be found in the **CustomAttributes** category of properties, located in the Properties pane.</span></span>  
  
 <span data-ttu-id="10860-109">Para formatar efetivamente o gráfico usando um número mínimo de etapas, altere o estilo de borda padrão, a paleta e o estilo de desenho.</span><span class="sxs-lookup"><span data-stu-id="10860-109">To effectively format the chart using a minimal number of steps, change the default border style, palette and drawing style.</span></span> <span data-ttu-id="10860-110">Esses três recursos produzem a maior alteração visível no gráfico.</span><span class="sxs-lookup"><span data-stu-id="10860-110">These three features produce the largest visible change on the chart.</span></span> <span data-ttu-id="10860-111">Os estilos de desenho são aplicáveis somente aos gráficos de pizza, de rosca, de barras e de colunas.</span><span class="sxs-lookup"><span data-stu-id="10860-111">Drawing styles are only applicable to pie, doughnut, bar and column charts.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="in-this-section"></a><span data-ttu-id="10860-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="10860-112">In This Section</span></span>  
 [<span data-ttu-id="10860-113">Formatando as cores da série em um gráfico &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="10860-113">Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md)  
 <span data-ttu-id="10860-114">Discute como as cores são definidas usando uma paleta, como é possível definir sua própria paleta de cores e como definir as cores baseado em uma expressão.</span><span class="sxs-lookup"><span data-stu-id="10860-114">Discusses how colors are defined using a palette, how you can define your own color palette, and how to define colors based on an expression.</span></span>  
  
 [<span data-ttu-id="10860-115">Formatando rótulos dos eixos de um gráfico #40;Construtor de Relatórios e SSRS#41;</span><span class="sxs-lookup"><span data-stu-id="10860-115">Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md)  
 <span data-ttu-id="10860-116">Discute como exibir linhas de grade, marcas de escala e títulos e como formatar números e datas na escala do eixo.</span><span class="sxs-lookup"><span data-stu-id="10860-116">Discusses how to display gridlines, tick marks, and titles, and how to format numbers and dates on the axis scale.</span></span>  
  
 [<span data-ttu-id="10860-117">Formatando a legenda em um gráfico &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="10860-117">Formatting the Legend on a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-legend-formatting-report-builder.md)  
 <span data-ttu-id="10860-118">Discute como reordenar e formatar itens na legenda do gráfico.</span><span class="sxs-lookup"><span data-stu-id="10860-118">Discusses how to re-order and format items in the chart legend.</span></span>  
  
 [<span data-ttu-id="10860-119">Formatando pontos de dados em um gráfico &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="10860-119">Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-data-points-on-a-chart-report-builder-and-ssrs.md)  
 <span data-ttu-id="10860-120">Discute como posicionar rótulos de pontos de dados e formatar marcadores de pontos de dados para cada série no gráfico.</span><span class="sxs-lookup"><span data-stu-id="10860-120">Discusses how to position data point labels and format data point markers for every series on the chart.</span></span>  
  
 [<span data-ttu-id="10860-121">Efeitos 3D, bisel e outros efeitos em um gráfico &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="10860-121">3D, Bevel, and Other Effects in a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-effects-3d-bevel-and-other-report-builder.md)  
 <span data-ttu-id="10860-122">Discute vários efeitos 3D que podem ser aplicados a um gráfico.</span><span class="sxs-lookup"><span data-stu-id="10860-122">Discusses various 3D effects that you can apply to a chart.</span></span>  
  
 [<span data-ttu-id="10860-123">Adicionar um quadro de borda a um gráfico &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="10860-123">Add a Border Frame to a Chart &#40;Report Builder and SSRS&#41;</span></span>](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md)  
 <span data-ttu-id="10860-124">Explica como adicionar uma moldura de borda a um gráfico.</span><span class="sxs-lookup"><span data-stu-id="10860-124">Explains how to add a border frame to a chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10860-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="10860-125">See Also</span></span>  
 <span data-ttu-id="10860-126">[Gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="10860-126">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="10860-127">[Adicionar um quadro de borda a um gráfico &#40;Construtor de Relatórios e SSRS&#41;](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="10860-127">[Add a Border Frame to a Chart &#40;Report Builder and SSRS&#41;](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="10860-128">[Definir cores em um gráfico usando uma paleta &#40;Construtor de Relatórios e SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="10860-128">[Define Colors on a Chart Using a Palette &#40;Report Builder and SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="10860-129">Adicionar estilos de bisel, alto-relevo e textura a um gráfico &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="10860-129">Add Bevel, Emboss, and Texture Styles to a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-effects-add-bevel-emboss-or-texture-report-builder.md)  
  
  
