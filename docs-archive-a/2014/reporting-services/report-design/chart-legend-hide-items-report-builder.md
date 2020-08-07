---
title: Ocultar itens de legenda no gráfico (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 92256240-0cd5-4be4-8904-d1e3b93cb6b3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 20444432f580ffaf1c5f4de1320b06319f973a01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582305"
---
# <a name="hide-legend-items-on-the-chart-report-builder-and-ssrs"></a><span data-ttu-id="de510-102">Ocultar itens de legenda no gráfico (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="de510-102">Hide Legend Items on the Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="de510-103">Por padrão, qualquer série adicionada a um gráfico que não seja de forma é adicionada como um item na legenda.</span><span class="sxs-lookup"><span data-stu-id="de510-103">By default, any series added to a non-Shape chart will be added as an item in the legend.</span></span> <span data-ttu-id="de510-104">Para gráficos de pizza, de rosca, de funil e de pirâmide, qualquer série adicionada ao gráfico adicionará pontos de dados individuais na legenda.</span><span class="sxs-lookup"><span data-stu-id="de510-104">For pie, doughnut, funnel, and pyramid charts, any series added to the chart will add individual data points in the legend.</span></span>  
  
 <span data-ttu-id="de510-105">É possível ocultar qualquer item na legenda.</span><span class="sxs-lookup"><span data-stu-id="de510-105">You can hide any item on the legend.</span></span> <span data-ttu-id="de510-106">Quando você oculta um item de legenda, ele ainda é exibido no gráfico.</span><span class="sxs-lookup"><span data-stu-id="de510-106">When you hide a legend item, it will still appear in the chart.</span></span> <span data-ttu-id="de510-107">Isso é útil em situações em que você não deseja mostrar mais informações para uma série adicionada ao gráfico.</span><span class="sxs-lookup"><span data-stu-id="de510-107">This is useful in situations where you do not want to show more information for a series that is added to the chart.</span></span> <span data-ttu-id="de510-108">Por exemplo, ao adicionar uma série calculada, como uma média móvel, ao gráfico, talvez você queira ocultar essa entrada na legenda para que apenas mais informações da série original sejam mostradas.</span><span class="sxs-lookup"><span data-stu-id="de510-108">For example, if you have added a calculated series like a moving average to the chart, you may want to hide this entry in the legend so that more information is only shown for the original series.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-hide-an-item-from-display-in-the-legend"></a><span data-ttu-id="de510-109">Para ocultar um item da exibição na legenda</span><span class="sxs-lookup"><span data-stu-id="de510-109">To hide an item from display in the legend</span></span>  
  
1.  <span data-ttu-id="de510-110">Clique com o botão direito do mouse na série que deseja ocultar e selecione **Propriedades da Série**.</span><span class="sxs-lookup"><span data-stu-id="de510-110">Right-click on the series you want to hide and select **Series Properties**.</span></span>  
  
2.  <span data-ttu-id="de510-111">Clique em **Legenda**.</span><span class="sxs-lookup"><span data-stu-id="de510-111">Click **Legend**.</span></span> <span data-ttu-id="de510-112">Selecione a opção **Não mostrar esta série em uma legenda** .</span><span class="sxs-lookup"><span data-stu-id="de510-112">Select the **Do not show this series in a legend** option.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="de510-113">Não é possível ocultar uma série apenas de um grupo e não de outros.</span><span class="sxs-lookup"><span data-stu-id="de510-113">You cannot hide a series for one group and not for the others.</span></span> <span data-ttu-id="de510-114">Se você adicionou um campo à área **Grupos de Séries** , todas as séries pertencentes a esse grupo serão ocultadas.</span><span class="sxs-lookup"><span data-stu-id="de510-114">If you have added a field to the **Series Groups** area, all series belonging to this group will be hidden.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de510-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="de510-115">See Also</span></span>  
 <span data-ttu-id="de510-116">[Formatando a legenda em um gráfico &#40;Construtor de Relatórios e SSRS&#41;](chart-legend-formatting-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="de510-116">[Formatting the Legend on a Chart &#40;Report Builder and SSRS&#41;](chart-legend-formatting-report-builder.md) </span></span>  
 <span data-ttu-id="de510-117">[Formatando pontos de dados em um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="de510-117">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="de510-118">[Alterar o texto de um item de legenda &#40;Construtor de Relatórios e SSRS&#41;](chart-legend-change-item-text-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="de510-118">[Change the Text of a Legend Item &#40;Report Builder and SSRS&#41;](chart-legend-change-item-text-report-builder.md) </span></span>  
 <span data-ttu-id="de510-119">[Adicionar uma média móvel a um gráfico &#40;Construtor de Relatórios e SSRS&#41;](add-a-moving-average-to-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="de510-119">[Add a Moving Average to a Chart &#40;Report Builder and SSRS&#41;](add-a-moving-average-to-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="de510-120">Caixa de diálogo Propriedades da Legenda, Geral &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="de510-120">Legend Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../legend-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
