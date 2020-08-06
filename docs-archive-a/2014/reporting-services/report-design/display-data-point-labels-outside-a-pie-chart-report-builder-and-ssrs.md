---
title: Exibir rótulos de pontos de dados fora de um gráfico de pizza (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 959b7574-cf43-470b-b592-4944d8a9948f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: dd4f38f24d2729acacfa3520635b93d8af2e9433
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683430"
---
# <a name="display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs"></a><span data-ttu-id="2cdd2-102">Exibir rótulos de pontos de dados fora de um gráfico de pizza (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="2cdd2-102">Display Data Point Labels Outside a Pie Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="2cdd2-103">No [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], o rótulo do gráfico de pizza é otimizado para exibir rótulos apenas em várias fatias de dados.</span><span class="sxs-lookup"><span data-stu-id="2cdd2-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], pie chart labeling is optimized to display labels on only several slices of data.</span></span> <span data-ttu-id="2cdd2-104">Os rótulos poderão ser sobrepostos, se o gráfico de pizza contiver muitas fatias.</span><span class="sxs-lookup"><span data-stu-id="2cdd2-104">Labels may overlap if the pie chart contains too many slices.</span></span> <span data-ttu-id="2cdd2-105">Uma solução é exibir os rótulos fora do gráfico de pizza, o que pode criar mais espaço para rótulos de dados mais longos.</span><span class="sxs-lookup"><span data-stu-id="2cdd2-105">One solution is to display the labels outside the pie chart, which may create more room for longer data labels.</span></span> <span data-ttu-id="2cdd2-106">Se os rótulos ainda estiverem sobrepostos, você poderá criar mais espaço para eles habilitando 3D.</span><span class="sxs-lookup"><span data-stu-id="2cdd2-106">If you find that your labels still overlap, you can create more space for them by enabling 3D.</span></span> <span data-ttu-id="2cdd2-107">Isso reduz o diâmetro do gráfico de pizza criando mais espaço em torno do gráfico.</span><span class="sxs-lookup"><span data-stu-id="2cdd2-107">This reduces the diameter of the pie chart, creating more space around the chart.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-display-data-point-labels-inside-a-pie-chart"></a><span data-ttu-id="2cdd2-108">Para exibir rótulos de pontos de dados dentro de um gráfico de pizza</span><span class="sxs-lookup"><span data-stu-id="2cdd2-108">To display data point labels inside a pie chart</span></span>  
  
1.  <span data-ttu-id="2cdd2-109">Adicione um gráfico de pizza ao relatório.</span><span class="sxs-lookup"><span data-stu-id="2cdd2-109">Add a pie chart to your report.</span></span> <span data-ttu-id="2cdd2-110">Para obter mais informações, consulte [Adicionar um gráfico a um relatório &#40;Construtor de Relatórios e SSRS&#41;](add-a-chart-to-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2cdd2-110">For more information, see [Add a Chart to a Report &#40;Report Builder and SSRS&#41;](add-a-chart-to-a-report-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="2cdd2-111">Na superfície de design, clique com o botão direito do mouse no gráfico e selecione **Mostrar Rótulos de Dados**.</span><span class="sxs-lookup"><span data-stu-id="2cdd2-111">On the design surface, right-click on the chart and select **Show Data Labels**.</span></span>  
  
### <a name="to-display-data-point-labels-outside-a-pie-chart"></a><span data-ttu-id="2cdd2-112">Para exibir rótulos de pontos de dados fora de um gráfico de pizza</span><span class="sxs-lookup"><span data-stu-id="2cdd2-112">To display data point labels outside a pie chart</span></span>  
  
1.  <span data-ttu-id="2cdd2-113">Crie um gráfico de pizza e exiba os rótulos de dados.</span><span class="sxs-lookup"><span data-stu-id="2cdd2-113">Create a pie chart and display the data labels.</span></span>  
  
2.  <span data-ttu-id="2cdd2-114">Abra o painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="2cdd2-114">Open the Properties pane.</span></span>  
  
3.  <span data-ttu-id="2cdd2-115">Na superfície de design, clique na própria pizza para exibir as propriedades **Categoria** no painel de Propriedades.</span><span class="sxs-lookup"><span data-stu-id="2cdd2-115">On the design surface, click on the pie itself to display the **Category** properties in the Properties pane.</span></span>  
  
4.  <span data-ttu-id="2cdd2-116">Expanda o nó **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="2cdd2-116">Expand the **CustomAttributes** node.</span></span> <span data-ttu-id="2cdd2-117">Uma lista de atributos para o gráfico de pizza é exibida.</span><span class="sxs-lookup"><span data-stu-id="2cdd2-117">A list of attributes for the pie chart is displayed.</span></span>  
  
5.  <span data-ttu-id="2cdd2-118">Defina a propriedade **PieLabelStyle** para **Externo**.</span><span class="sxs-lookup"><span data-stu-id="2cdd2-118">Set the **PieLabelStyle** property to **Outside**.</span></span>  
  
6.  <span data-ttu-id="2cdd2-119">Defina a `PieLineColor` propriedade como **preto**.</span><span class="sxs-lookup"><span data-stu-id="2cdd2-119">Set the `PieLineColor` property to **Black**.</span></span> <span data-ttu-id="2cdd2-120">A propriedade PieLineColor define as linhas do texto explicativo para cada rótulo de ponto de dados.</span><span class="sxs-lookup"><span data-stu-id="2cdd2-120">The PieLineColor property defines callout lines for each data point label.</span></span>  
  
### <a name="to-prevent-overlapping-labels-displayed-outside-a-pie-chart"></a><span data-ttu-id="2cdd2-121">Para evitar rótulos sobrepostos exibidos fora de um gráfico de pizza</span><span class="sxs-lookup"><span data-stu-id="2cdd2-121">To prevent overlapping labels displayed outside a pie chart</span></span>  
  
1.  <span data-ttu-id="2cdd2-122">Crie um gráfico de pizza com rótulos externos.</span><span class="sxs-lookup"><span data-stu-id="2cdd2-122">Create a pie chart with external labels.</span></span>  
  
2.  <span data-ttu-id="2cdd2-123">Na superfície de design, clique com o botão direito do mouse fora do gráfico de pizza, mas dentro das bordas do gráfico e selecione **Propriedades da Área do Gráfico**. A caixa de diálogo **AreaProperties do Gráfico** é exibida.</span><span class="sxs-lookup"><span data-stu-id="2cdd2-123">On the design surface, right-click outside the pie chart but inside the chart borders and select **Chart Area Properties**.The **Chart AreaProperties** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="2cdd2-124">Na guia **Opções 3D** , selecione **Habilitar 3D**.</span><span class="sxs-lookup"><span data-stu-id="2cdd2-124">On the **3D Options** tab, select **Enable 3D**.</span></span>  
  
4.  <span data-ttu-id="2cdd2-125">Se desejar que o gráfico tenha mais espaço para rótulos, mas ainda pareça bidimensional, defina as propriedades **Rotação** e **Inclinação** em **0**.</span><span class="sxs-lookup"><span data-stu-id="2cdd2-125">If you want the chart to have more room for labels but still appear two-dimensional, set the **Rotation** and **Inclination** properties to **0**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cdd2-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2cdd2-126">See Also</span></span>  
 <span data-ttu-id="2cdd2-127">[Gráficos de pizza &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2cdd2-127">[Pie Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2cdd2-128">[Coletar fatias pequenas em um gráfico de pizza &#40;Construtor de Relatórios e SSRS&#41;](collect-small-slices-on-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2cdd2-128">[Collect Small Slices on a Pie Chart &#40;Report Builder and SSRS&#41;](collect-small-slices-on-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="2cdd2-129">Exibir valores percentuais em um gráfico de pizza &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2cdd2-129">Display Percentage Values on a Pie Chart &#40;Report Builder and SSRS&#41;</span></span>](display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md)  
  
  
