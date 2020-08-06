---
title: Posicionar rótulos em um gráfico (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5db74e0b-8be8-4b47-b386-faab56dffa9b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e90cbf04e0282454658e6324f0ba6600a99cb718
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678580"
---
# <a name="position-labels-in-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="2e0ee-102">Posicionar rótulos em um gráfico (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="2e0ee-102">Position Labels in a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="2e0ee-103">Como cada tipo de gráfico tem uma forma diferente, os rótulos de ponto de dados são colocados em um local ideal de forma que não interfiram no gráfico.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-103">Because each chart type has a different shape, data point labels are placed in an optimal location so as not to interfere on the chart.</span></span> <span data-ttu-id="2e0ee-104">A posição padrão dos rótulos varia com o tipo de gráfico:</span><span class="sxs-lookup"><span data-stu-id="2e0ee-104">The default position of the labels depends varies with the chart type:</span></span>  
  
-   <span data-ttu-id="2e0ee-105">Em gráficos empilhados, os rótulos só podem ser posicionados nas séries.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-105">On stacked charts, labels can only be positioned inside the series.</span></span>  
  
-   <span data-ttu-id="2e0ee-106">Nos gráficos de funil ou pirâmide, os rótulos são posicionados fora de uma coluna.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-106">On funnel or pyramid charts, labels are placed on the outside in a column.</span></span>  
  
-   <span data-ttu-id="2e0ee-107">Em gráficos de pizza, os rótulos são posicionados nas fatias individuais em um gráfico de pizza.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-107">On pie charts, labels are placed inside the individual slices on a pie chart.</span></span>  
  
-   <span data-ttu-id="2e0ee-108">Nos gráficos de barras, os rótulos são posicionados fora das barras que representam os pontos de dados.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-108">On bar charts, labels are placed outside of the bars that represent data points.</span></span>  
  
-   <span data-ttu-id="2e0ee-109">Nos gráficos polares, os rótulos são posicionados fora da área circular que representa os pontos de dados.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-109">On polar charts, labels are placed outside of the circular area that represents data points.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-position-of-point-labels-in-a-pie-chart"></a><span data-ttu-id="2e0ee-110">Para alterar a posição dos rótulos de pontos em um gráfico de pizza</span><span class="sxs-lookup"><span data-stu-id="2e0ee-110">To change the position of point labels in a Pie chart</span></span>  
  
1.  <span data-ttu-id="2e0ee-111">Crie um gráfico de pizza.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-111">Create a pie chart.</span></span>  
  
2.  <span data-ttu-id="2e0ee-112">Na superfície de design, clique com o botão direito do mouse no gráfico e selecione **Mostrar Rótulos de Dados**.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-112">On the design surface, right-click the chart and select **Show Data Labels**.</span></span>  
  
3.  <span data-ttu-id="2e0ee-113">Abra o painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-113">Open the Properties pane.</span></span> <span data-ttu-id="2e0ee-114">Na guia **Exibir** , clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-114">On the **View** tab, click **Properties**.</span></span>  
  
4.  <span data-ttu-id="2e0ee-115">Na superfície de design, clique no gráfico.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-115">On the design surface, click the chart.</span></span> <span data-ttu-id="2e0ee-116">As propriedades para o gráfico são exibidas no painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-116">The properties for the chart are displayed in the Properties pane.</span></span>  
  
5.  <span data-ttu-id="2e0ee-117">Na seção **Geral** , expanda o nó **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="2e0ee-117">In the **General** section, expand the **CustomAttributes** node.</span></span> <span data-ttu-id="2e0ee-118">Uma lista de atributos para o gráfico de pizza é exibida.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-118">A list of attributes for the pie chart is displayed.</span></span>  
  
6.  <span data-ttu-id="2e0ee-119">Selecione um valor para a propriedade PieLabelStyle.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-119">Select a value for the PieLabelStyle property.</span></span>  
  
### <a name="to-change-the-position-of-point-labels-in-a-funnel-or-pyramid-chart"></a><span data-ttu-id="2e0ee-120">Para alterar a posição dos rótulos de pontos em um Gráfico de funil ou pirâmide</span><span class="sxs-lookup"><span data-stu-id="2e0ee-120">To change the position of point labels in a Funnel or Pyramid chart</span></span>  
  
1.  <span data-ttu-id="2e0ee-121">Crie um gráfico de funil ou pirâmide.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-121">Create a funnel or pyramid chart.</span></span>  
  
2.  <span data-ttu-id="2e0ee-122">Na superfície de design, clique com o botão direito do mouse no gráfico e selecione **Mostrar Rótulos de Dados**.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-122">On the design surface, right-click the chart and select **Show Data Labels**.</span></span>  
  
3.  <span data-ttu-id="2e0ee-123">Abra o painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-123">Open the Properties pane.</span></span> <span data-ttu-id="2e0ee-124">Na guia **Exibir** , clique em **Propriedades**</span><span class="sxs-lookup"><span data-stu-id="2e0ee-124">On the **View** tab, click **Properties**</span></span>  
  
4.  <span data-ttu-id="2e0ee-125">Na superfície de design, clique no gráfico.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-125">On the design surface, click the chart.</span></span> <span data-ttu-id="2e0ee-126">As propriedades para o gráfico são exibidas no painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-126">The properties for the chart are displayed in the Properties pane.</span></span>  
  
5.  <span data-ttu-id="2e0ee-127">Na seção **Geral** , expanda o nó **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="2e0ee-127">In the **General** section, expand the **CustomAttributes** node.</span></span> <span data-ttu-id="2e0ee-128">Uma lista de atributos para o gráfico de funil é exibida.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-128">A list of attributes for the funnel chart is displayed.</span></span>  
  
6.  <span data-ttu-id="2e0ee-129">Para um gráfico de funil, selecione um valor para a propriedade FunnelLabelStyle.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-129">For a funnel chart, select a value for the FunnelLabelStyle property.</span></span> <span data-ttu-id="2e0ee-130">Para um gráfico de pirâmide, selecione um valor para a propriedade PyramidLabelStyle.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-130">For a pyramid chart, select a value for the PyramidLabelStyle property.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2e0ee-131">Quando essa propriedade é definida com um valor `OutsideInColumn`, os rótulos são desenhados em uma coluna vertical.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-131">When this property is set to a value `OutsideInColumn`, the labels are drawn in a vertical column.</span></span> <span data-ttu-id="2e0ee-132">Não há como alterar a posição da coluna.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-132">There is no way to change the position of the column.</span></span>  
  
### <a name="to-change-the-position-of-point-labels-in-a-bar-chart"></a><span data-ttu-id="2e0ee-133">Para alterar a posição dos rótulos de pontos em um gráfico de barras</span><span class="sxs-lookup"><span data-stu-id="2e0ee-133">To change the position of point labels in a Bar chart</span></span>  
  
1.  <span data-ttu-id="2e0ee-134">Crie um gráfico de barras.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-134">Create a bar chart.</span></span>  
  
2.  <span data-ttu-id="2e0ee-135">Na superfície de design, clique com o botão direito do mouse no gráfico e selecione **Mostrar Rótulos de Dados**.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-135">On the design surface, right-click the chart and select **Show Data Labels**.</span></span>  
  
3.  <span data-ttu-id="2e0ee-136">Abra o painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-136">Open the Properties pane.</span></span> <span data-ttu-id="2e0ee-137">Na guia **Exibir** , clique em **Propriedades**</span><span class="sxs-lookup"><span data-stu-id="2e0ee-137">On the **View** tab, click **Properties**</span></span>  
  
4.  <span data-ttu-id="2e0ee-138">Na superfície de design, clique no gráfico.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-138">On the design surface, click the chart.</span></span> <span data-ttu-id="2e0ee-139">As propriedades para o gráfico são exibidas no painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-139">The properties for the chart are displayed in the Properties pane.</span></span>  
  
5.  <span data-ttu-id="2e0ee-140">Na seção **Geral** , expanda o nó **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="2e0ee-140">In the **General** section, expand the **CustomAttributes** node.</span></span> <span data-ttu-id="2e0ee-141">Uma lista de atributos para o gráfico de barras é exibida.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-141">A list of attributes for the bar chart is displayed.</span></span>  
  
6.  <span data-ttu-id="2e0ee-142">Selecione um valor para a propriedade BarLabelStyle.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-142">Select a value for the BarLabelStyle property.</span></span>  
  
 <span data-ttu-id="2e0ee-143">Se o estilo do rótulo da barra for definido como `Outside`, os rótulos serão colocados fora da barra, contanto que caibam na área do gráfico.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-143">When the bar label style is set to `Outside`, the labels will be placed outside of the bar, as long as it fits in the chart area.</span></span> <span data-ttu-id="2e0ee-144">Se o rótulo não puder ser colocado fora da barra, mas dentro da área de gráfico, o rótulo será colocado dentro da barra na posição mais próxima do final da barra.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-144">If the label cannot be placed outside of the bar but inside of the chart area, the label is placed inside the bar at the position closest to the end of the bar.</span></span>  
  
### <a name="to-change-the-position-of-point-labels-in-an-area-column-line-or-scatter-chart"></a><span data-ttu-id="2e0ee-145">Para alterar a posição dos rótulos de pontos em um gráfico de Área, Coluna, Linha ou Dispersão</span><span class="sxs-lookup"><span data-stu-id="2e0ee-145">To change the position of point labels in an Area, Column, Line or Scatter chart</span></span>  
  
1.  <span data-ttu-id="2e0ee-146">Crie um gráfico de Área, Coluna, Linha ou Dispersão.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-146">Create an Area, Column, Line or Scatter chart.</span></span>  
  
2.  <span data-ttu-id="2e0ee-147">Na superfície de design, clique com o botão direito do mouse no gráfico e selecione **Mostrar Rótulos de Dados**.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-147">On the design surface, right-click the chart and select **Show Data Labels**.</span></span>  
  
3.  <span data-ttu-id="2e0ee-148">Abra o painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-148">Open the Properties pane.</span></span> <span data-ttu-id="2e0ee-149">Na guia **Exibir** , clique em **Propriedades**</span><span class="sxs-lookup"><span data-stu-id="2e0ee-149">On the **View** tab, click **Properties**</span></span>  
  
4.  <span data-ttu-id="2e0ee-150">Na superfície de design, clique na série.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-150">On the design surface, click the series.</span></span> <span data-ttu-id="2e0ee-151">As propriedades da série são exibidas no painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-151">The properties for the series are displayed in the Properties pane.</span></span>  
  
5.  <span data-ttu-id="2e0ee-152">Na seção **Dados** , expanda o nó **DataPoint** e o nó **Rótulo**.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-152">In the **Data** section, expand the **DataPoint** node, then expand the **Label**node.</span></span>  
  
6.  <span data-ttu-id="2e0ee-153">Selecione um valor para a propriedade Position.</span><span class="sxs-lookup"><span data-stu-id="2e0ee-153">Select a value for the Position property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e0ee-154">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2e0ee-154">See Also</span></span>  
 <span data-ttu-id="2e0ee-155">[Gráficos de pizza &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2e0ee-155">[Pie Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2e0ee-156">[Gráficos de barras &#40;Construtor de Relatórios e SSRS&#41;](bar-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2e0ee-156">[Bar Charts &#40;Report Builder and SSRS&#41;](bar-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2e0ee-157">[Formatando rótulos dos eixos de um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2e0ee-157">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2e0ee-158">[Formatar rótulos de eixo como datas ou moedas &#40;Construtor de Relatórios e SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2e0ee-158">[Format Axis Labels as Dates or Currencies &#40;Report Builder and SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2e0ee-159">[Exibir rótulos de pontos de dados fora de um gráfico de pizza &#40;Construtor de Relatórios e SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2e0ee-159">[Display Data Point Labels Outside a Pie Chart &#40;Report Builder and SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="2e0ee-160">Formatando pontos de dados em um gráfico &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2e0ee-160">Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-data-points-on-a-chart-report-builder-and-ssrs.md)  
  
  
