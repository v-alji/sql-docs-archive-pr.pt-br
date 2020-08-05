---
title: Exibir valores de percentual em um gráfico de pizza (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eb905fc1-5235-4773-a27e-b07be9318be5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2dee9017d34f2751b790b2e4928571160b597f1d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573738"
---
# <a name="display-percentage-values-on-a-pie-chart-report-builder-and-ssrs"></a><span data-ttu-id="61351-102">Exibir valores de porcentagem em um gráfico de pizza (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="61351-102">Display Percentage Values on a Pie Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="61351-103">Por padrão, as categorias são mostradas na legenda para identificar cada valor.</span><span class="sxs-lookup"><span data-stu-id="61351-103">By default, categories are shown in the legend to identify each value.</span></span> <span data-ttu-id="61351-104">Se você rotulou o gráfico de pizza usando rótulos de categorias, poderá desejar mostrar porcentagens na legenda.</span><span class="sxs-lookup"><span data-stu-id="61351-104">If you have labeled the pie chart using category labels, you may want show percentages in the legend.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-display-percentage-values-as-labels-on-a-pie-chart"></a><span data-ttu-id="61351-105">Para exibir valores de porcentagem como rótulos em um gráfico de pizza</span><span class="sxs-lookup"><span data-stu-id="61351-105">To display percentage values as labels on a pie chart</span></span>  
  
1.  <span data-ttu-id="61351-106">Adicione um gráfico de pizza ao relatório.</span><span class="sxs-lookup"><span data-stu-id="61351-106">Add a pie chart to your report.</span></span> <span data-ttu-id="61351-107">Para obter mais informações, consulte [Adicionar um gráfico a um relatório &#40;Construtor de Relatórios e SSRS&#41;](add-a-chart-to-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="61351-107">For more information, see [Add a Chart to a Report &#40;Report Builder and SSRS&#41;](add-a-chart-to-a-report-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="61351-108">Na superfície de design, clique com o botão direito do mouse no gráfico de pizza e selecione **Mostrar Rótulos de Dados**.</span><span class="sxs-lookup"><span data-stu-id="61351-108">On the design surface, right-click on the pie and select **Show Data Labels**.</span></span> <span data-ttu-id="61351-109">Os rótulos de dados devem aparecer dentro de cada fatia do gráfico de pizza.</span><span class="sxs-lookup"><span data-stu-id="61351-109">The data labels should appear within each slice on the pie chart.</span></span>  
  
3.  <span data-ttu-id="61351-110">Na superfície de design, clique com o botão direito do mouse nos rótulos e selecione **Propriedades do Rótulo de Série**.</span><span class="sxs-lookup"><span data-stu-id="61351-110">On the design surface, right-click on the labels and select **Series Label Properties**.</span></span> <span data-ttu-id="61351-111">A caixa de diálogo **Propriedades do Rótulo de Série** é exibida.</span><span class="sxs-lookup"><span data-stu-id="61351-111">The **Series Label Properties** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="61351-112">Digite `#PERCENT` para a opção **rotular dados** .</span><span class="sxs-lookup"><span data-stu-id="61351-112">Type `#PERCENT` for the **Label data** option.</span></span>  
  
5.  <span data-ttu-id="61351-113">(Opcional) Para especificar quantas casas decimais o rótulo deve mostrar, digite "#PERCENT{P*n*}" em que *n* é o número de casas decimais a serem exibidas.</span><span class="sxs-lookup"><span data-stu-id="61351-113">(Optional) To specify how many decimal places the label shows, type "#PERCENT{P*n*}" where *n* is the number of decimal places to display.</span></span> <span data-ttu-id="61351-114">Por exemplo, para não exibir nenhuma casa decimal, digite "#PERCENT{P0}".</span><span class="sxs-lookup"><span data-stu-id="61351-114">For example, to display no decimal places, type "#PERCENT{P0}".</span></span>  
  
### <a name="to-display-percentage-values-in-the-legend-of-a-pie-chart"></a><span data-ttu-id="61351-115">Para exibir valores percentuais na legenda de um gráfico de pizza</span><span class="sxs-lookup"><span data-stu-id="61351-115">To display percentage values in the legend of a pie chart</span></span>  
  
1.  <span data-ttu-id="61351-116">Na superfície de design, clique com o botão direito do mouse no gráfico de pizza e selecione **Propriedades da Série**.</span><span class="sxs-lookup"><span data-stu-id="61351-116">On the design surface, right-click on the pie chart and select **Series Properties**.</span></span> <span data-ttu-id="61351-117">A caixa de diálogo **Propriedades da Série** é exibida.</span><span class="sxs-lookup"><span data-stu-id="61351-117">The **Series Properties** dialog box displays.</span></span>  
  
2.  <span data-ttu-id="61351-118">Em **legenda**, digite `#PERCENT` para a propriedade **texto da legenda personalizada** .</span><span class="sxs-lookup"><span data-stu-id="61351-118">In **Legend**, type `#PERCENT` for the **Custom legend text** property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61351-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="61351-119">See Also</span></span>  
 <span data-ttu-id="61351-120">[Gráficos de pizza &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="61351-120">[Pie Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="61351-121">[Formatando a legenda em um gráfico &#40;Construtor de Relatórios e SSRS&#41;](chart-legend-formatting-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="61351-121">[Formatting the Legend on a Chart &#40;Report Builder and SSRS&#41;](chart-legend-formatting-report-builder.md) </span></span>  
 <span data-ttu-id="61351-122">[Exibir rótulos de ponto de dados fora de um gráfico de pizza &#40;Construtor de Relatórios e SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="61351-122">[Display Data Point Labels Outside a Pie Chart &#40;Report Builder and SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="61351-123">Coletar fatias pequenas em um gráfico de pizza &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="61351-123">Collect Small Slices on a Pie Chart &#40;Report Builder and SSRS&#41;</span></span>](collect-small-slices-on-a-pie-chart-report-builder-and-ssrs.md)  
  
  
