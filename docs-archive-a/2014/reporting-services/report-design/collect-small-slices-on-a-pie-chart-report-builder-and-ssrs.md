---
title: Coletar fatias pequenas em um gráfico de pizza (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 21c2b8cb-b9ca-4bc0-bf49-50ba432562f6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2302217843864115847aeb544d1c64727b8ad3a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574504"
---
# <a name="collect-small-slices-on-a-pie-chart-report-builder-and-ssrs"></a><span data-ttu-id="c275c-102">Coletar fatias pequenas em um gráfico de pizza (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="c275c-102">Collect Small Slices on a Pie Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c275c-103">Quando os gráficos de pizza exibem muitos pontos de dados, eles começam a parecer clusterizados.</span><span class="sxs-lookup"><span data-stu-id="c275c-103">When pie charts display too many points of data, they begin to look cluttered.</span></span> <span data-ttu-id="c275c-104">Para resolver esse problema, você pode mostrar todos os dados sejam inferiores a um determinado valor como uma fatia no gráfico de pizza.</span><span class="sxs-lookup"><span data-stu-id="c275c-104">To resolve this issue, you can show all data that falls beneath a certain value as one slice on the pie chart.</span></span>  
  
 <span data-ttu-id="c275c-105">Para coletar pequenas fatias em uma fatia, primeiro decida se o limite para coleta de pequenas fatias será medido como uma porcentagem do gráfico de pizza ou como um valor fixo.</span><span class="sxs-lookup"><span data-stu-id="c275c-105">To collect small slices into one slice, first decide whether your threshold for collecting small slices is measured as a percentage of the pie chart or as a fixed value.</span></span> <span data-ttu-id="c275c-106">Em seguida, defina as propriedades CollectedThreshold e CollectedThresholdUsePercent. Defina a propriedade CollectedThreshold como a porcentagem do gráfico à qual um valor deve ser inferior para ser coletado ou o valor de dados limite real para coleta.</span><span class="sxs-lookup"><span data-stu-id="c275c-106">Then set the CollectedThreshold and CollectedThresholdUsePercent properties.Set the CollectedThreshold property to either the percentage of the chart that a value must fall below to be collected, or the actual threshold data value for collection.</span></span> <span data-ttu-id="c275c-107">Defina a propriedade CollectedThresholdUsePercent como `True` para usar uma porcentagem ou `False` para usar um valor real.</span><span class="sxs-lookup"><span data-stu-id="c275c-107">Set the CollectedThresholdUsePercent property to `True` to use a percentage or `False` to use an actual value.</span></span>  
  
 <span data-ttu-id="c275c-108">Também é possível coletar pequenas fatias em um segundo gráfico de pizza que é retirado de uma fatia coletada do primeiro gráfico de pizza.</span><span class="sxs-lookup"><span data-stu-id="c275c-108">You can also collect small slices into a second pie chart that is called out from a collected slice of the first pie chart.</span></span> <span data-ttu-id="c275c-109">O segundo gráfico de pizza é desenhado à direita do gráfico de pizza original.</span><span class="sxs-lookup"><span data-stu-id="c275c-109">The second pie chart is drawn to the right of the original pie chart.</span></span>  
  
 <span data-ttu-id="c275c-110">Não é possível combinar fatias de gráficos de funil ou de pirâmide em uma fatia.</span><span class="sxs-lookup"><span data-stu-id="c275c-110">You cannot combine slices of funnel or pyramid charts into one slice.</span></span>  
  
 <span data-ttu-id="c275c-111">Um exemplo deste gráfico está disponível como um relatório de exemplo.</span><span class="sxs-lookup"><span data-stu-id="c275c-111">An example of this chart is available as a sample report.</span></span> <span data-ttu-id="c275c-112">Para obter mais informações sobre como baixar este relatório de exemplo e outros, consulte [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [Construtor de Relatórios e Report Designer relatórios de exemplo](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="c275c-112">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
### <a name="to-collect-small-slices-into-a-single-slice-on-a-pie-chart"></a><span data-ttu-id="c275c-113">Para coletar pequenas fatias em uma única fatia em um gráfico de pizza</span><span class="sxs-lookup"><span data-stu-id="c275c-113">To collect small slices into a single slice on a pie chart</span></span>  
  
1.  <span data-ttu-id="c275c-114">Abra o painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="c275c-114">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="c275c-115">Na superfície de design, clique em qualquer fatia do gráfico de pizza.</span><span class="sxs-lookup"><span data-stu-id="c275c-115">On the design surface, click on any slice of the pie chart.</span></span> <span data-ttu-id="c275c-116">As propriedades da série são exibidas no painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="c275c-116">The properties for the series are displayed in the Properties pane.</span></span>  
  
3.  <span data-ttu-id="c275c-117">Na seção **Geral** , expanda o nó **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="c275c-117">In the **General** section, expand the **CustomAttributes** node.</span></span>  
  
4.  <span data-ttu-id="c275c-118">Defina a propriedade CollectedStyle como **SingleSlice**.</span><span class="sxs-lookup"><span data-stu-id="c275c-118">Set the CollectedStyle property to **SingleSlice**.</span></span>  
  
5.  <span data-ttu-id="c275c-119">Defina o valor do limite coletado e o tipo de limite.</span><span class="sxs-lookup"><span data-stu-id="c275c-119">Set the collected threshold value and type of threshold.</span></span> <span data-ttu-id="c275c-120">Os exemplos a seguir são maneiras comuns de configurar limites coletados.</span><span class="sxs-lookup"><span data-stu-id="c275c-120">The following examples are common ways of setting collected thresholds.</span></span>  
  
    -   <span data-ttu-id="c275c-121">**Por porcentagem.**</span><span class="sxs-lookup"><span data-stu-id="c275c-121">**By percentage.**</span></span> <span data-ttu-id="c275c-122">Por exemplo, para coletar qualquer fatia no gráfico de pizza que seja menor do que 10% em uma única fatia:</span><span class="sxs-lookup"><span data-stu-id="c275c-122">For example, to collect any slice on your pie chart that is less than 10% into a single slice:</span></span>  
  
         <span data-ttu-id="c275c-123">Defina a propriedade CollectedThresholdUsePercent como `True` .</span><span class="sxs-lookup"><span data-stu-id="c275c-123">Set the CollectedThresholdUsePercent property to `True`.</span></span>  
  
         <span data-ttu-id="c275c-124">Defina a propriedade CollectedThreshold como **10**.</span><span class="sxs-lookup"><span data-stu-id="c275c-124">Set the CollectedThreshold property to **10**.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="c275c-125">Se você definir Coletostyle como **SingleSlice**, CollectedThreshold como um valor maior que **100**e CollectedThresholdUsePercent for `True` , o gráfico gerará uma exceção porque não poderá calcular uma porcentagem.</span><span class="sxs-lookup"><span data-stu-id="c275c-125">If you set CollectedStyle to **SingleSlice**, CollectedThreshold to a value greater than **100**, and CollectedThresholdUsePercent is `True`, the chart will throw an exception because it cannot calculate a percentage.</span></span> <span data-ttu-id="c275c-126">Para resolver esse problema, defina CollectedThreshold como um valor menor do que **100**.</span><span class="sxs-lookup"><span data-stu-id="c275c-126">To resolve this issue, set the CollectedThreshold to a value less than **100**.</span></span>  
  
    -   <span data-ttu-id="c275c-127">**Por valor de dados.**</span><span class="sxs-lookup"><span data-stu-id="c275c-127">**By data value.**</span></span> <span data-ttu-id="c275c-128">Por exemplo, para coletar qualquer fatia no gráfico de pizza que seja menor do que 5000 em uma única fatia:</span><span class="sxs-lookup"><span data-stu-id="c275c-128">For example, to collect any slice on your pie chart that is less than 5000 into a single slice:</span></span>  
  
         <span data-ttu-id="c275c-129">Defina a propriedade CollectedThresholdUsePercent como `False` .</span><span class="sxs-lookup"><span data-stu-id="c275c-129">Set the CollectedThresholdUsePercent property to `False`.</span></span>  
  
         <span data-ttu-id="c275c-130">Defina a propriedade CollectedThreshold como **5000**.</span><span class="sxs-lookup"><span data-stu-id="c275c-130">Set the CollectedThreshold property to **5000**.</span></span>  
  
6.  <span data-ttu-id="c275c-131">Defina a propriedade CollectedLabel como uma cadeia de caracteres que represente o rótulo do texto que será mostrado na fatia coletada.</span><span class="sxs-lookup"><span data-stu-id="c275c-131">Set the CollectedLabel property to a string that represents the text label that will be shown on the collected slice.</span></span>  
  
7.  <span data-ttu-id="c275c-132">(Opcional) Defina as propriedades CollectedSliceExploded, CollectedColor, CollectedLegendText e CollectedToolTip.</span><span class="sxs-lookup"><span data-stu-id="c275c-132">(Optional) Set the CollectedSliceExploded, CollectedColor, CollectedLegendText and CollectedToolTip properties.</span></span> <span data-ttu-id="c275c-133">Essas propriedades alteram a aparência, a cor, o texto do rótulo, o texto da legenda e aspectos da dica de ferramenta da única fatia.</span><span class="sxs-lookup"><span data-stu-id="c275c-133">These properties change the appearance, color, label text, legend text and tooltip aspects of the single slice.</span></span>  
  
### <a name="to-collect-small-slices-into-a-secondary-callout-pie-chart"></a><span data-ttu-id="c275c-134">Para coletar pequenas fatias em um gráfico de pizza de texto explicativo secundário</span><span class="sxs-lookup"><span data-stu-id="c275c-134">To collect small slices into a secondary, callout pie chart</span></span>  
  
1.  <span data-ttu-id="c275c-135">Siga as etapas 1 a 3 acima.</span><span class="sxs-lookup"><span data-stu-id="c275c-135">Follow Steps 1-3 from above.</span></span>  
  
2.  <span data-ttu-id="c275c-136">Defina a propriedade CollectedStyle como **CollectedPie**.</span><span class="sxs-lookup"><span data-stu-id="c275c-136">Set the CollectedStyle property to **CollectedPie**.</span></span>  
  
3.  <span data-ttu-id="c275c-137">Defina a propriedade CollectedThreshold como um valor que represente o limite no qual pequenas fatias serão coletadas em uma fatia.</span><span class="sxs-lookup"><span data-stu-id="c275c-137">Set the CollectedThresholdproperty to a value that represents the threshold at which small slices will be collected into one slice.</span></span> <span data-ttu-id="c275c-138">Quando a propriedade recolhidastyle é definida como **CollectedPie**, a CollectedThresholdUsePercentproperty é sempre definida como `True` e o limite coletado é sempre medido em porcentagem.</span><span class="sxs-lookup"><span data-stu-id="c275c-138">When the CollectedStyle property is set to **CollectedPie**, the CollectedThresholdUsePercentproperty is always set to `True`, and the collected threshold is always measured in percent.</span></span>  
  
4.  <span data-ttu-id="c275c-139">(Opcional) Defina as propriedades CollectedColor, CollectedLabel, CollectedLegendText e CollectedToolTip.</span><span class="sxs-lookup"><span data-stu-id="c275c-139">(Optional) Set the CollectedColor, CollectedLabel, CollectedLegendText and CollectedToolTip properties.</span></span> <span data-ttu-id="c275c-140">Todas as outras propriedades denominadas "Coletadas" não se aplicam ao gráfico de pizza coletado.</span><span class="sxs-lookup"><span data-stu-id="c275c-140">All other properties named "Collected" do not apply to the collected pie.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c275c-141">O gráfico de pizza secundário é calculado com base nas pequenas fatias dos dados, portanto, ele só é exibido na Visualização.</span><span class="sxs-lookup"><span data-stu-id="c275c-141">The secondary pie chart is calculated based on the small slices in your data so it will only appear in Preview.</span></span> <span data-ttu-id="c275c-142">Ele não é exibido na superfície de design.</span><span class="sxs-lookup"><span data-stu-id="c275c-142">It does not appear on the design surface.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c275c-143">Não é possível formatar o gráfico de pizza secundário.</span><span class="sxs-lookup"><span data-stu-id="c275c-143">You cannot format the secondary pie chart.</span></span> <span data-ttu-id="c275c-144">Por esse motivo, é altamente recomendável usar a primeira abordagem ao coletar fatias da pizza.</span><span class="sxs-lookup"><span data-stu-id="c275c-144">For this reason, it is strongly recommended to use the first approach when collecting pie slices.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c275c-145">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c275c-145">See Also</span></span>  
 <span data-ttu-id="c275c-146">[Gráficos de pizza &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c275c-146">[Pie Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c275c-147">[Formatando pontos de dados em um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c275c-147">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c275c-148">[Exibir rótulos de ponto de dados fora de um gráfico de pizza &#40;Construtor de Relatórios e SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c275c-148">[Display Data Point Labels Outside a Pie Chart &#40;Report Builder and SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c275c-149">[Exibir valores de porcentagem em um gráfico de pizza &#40;Construtor de Relatórios e SSRS&#41;](display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c275c-149">[Display Percentage Values on a Pie Chart &#40;Report Builder and SSRS&#41;](display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c275c-150">Adicionar efeitos 3D a um gráfico &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c275c-150">Add 3D Effects to a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-effects-add-3d-effects-report-builder.md)  
  
  
