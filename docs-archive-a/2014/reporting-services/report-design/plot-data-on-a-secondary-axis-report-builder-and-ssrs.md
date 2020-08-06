---
title: Plotar dados em um eixo secundário (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 094f39bf-3634-4852-9fc3-3adec4b266e5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cec58820e0373bb1e9ef2d50d022e5b4ef7e962b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678582"
---
# <a name="plot-data-on-a-secondary-axis-report-builder-and-ssrs"></a><span data-ttu-id="3f8c3-102">Plotar dados em um eixo secundário (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="3f8c3-102">Plot Data on a Secondary Axis (Report Builder and SSRS)</span></span>
  <span data-ttu-id="3f8c3-103">O gráfico possui dois tipos de eixo: primário e secundário.</span><span class="sxs-lookup"><span data-stu-id="3f8c3-103">The chart has two axis types: primary and secondary.</span></span> <span data-ttu-id="3f8c3-104">O eixo secundário é útil ao comparar dois conjuntos de valores com dois intervalos de dados distintos que compartilham uma categoria em comum.</span><span class="sxs-lookup"><span data-stu-id="3f8c3-104">The secondary axis is useful when comparing two value sets with two distinct data ranges that share a common category.</span></span>  
  
 <span data-ttu-id="3f8c3-105">Por exemplo, suponha que você tenha um gráfico que calcula Receita versus Imposto referente ao ano de 2008.</span><span class="sxs-lookup"><span data-stu-id="3f8c3-105">For example, suppose you have a chart that calculates Revenue vs. Tax for the year 2008.</span></span> <span data-ttu-id="3f8c3-106">Nesse caso, o período de 2008 é comum para os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="3f8c3-106">In this case, the 2008 time period is common to both value sets.</span></span> <span data-ttu-id="3f8c3-107">No entanto, quando as duas séries são plotadas no mesmo eixo y, não podemos fazer uma comparação útil porque a escala do eixo y é otimizada para os valores maiores no conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="3f8c3-107">However, when both series are plotted on the same y-axis, we cannot make a useful comparison because the scale of the y-axis is optimized for the largest values in the dataset.</span></span> <span data-ttu-id="3f8c3-108">Se mostrarmos Receita no eixo primário, e Imposto no eixo secundário, poderemos exibir cada série em seu próprio eixo y com sua própria escala de valores.</span><span class="sxs-lookup"><span data-stu-id="3f8c3-108">If we show Revenue on the primary axis, and Tax on the secondary axis, we can display each series on its own y-axis with its own scale of values.</span></span> <span data-ttu-id="3f8c3-109">A série ainda compartilha um eixo x comum.</span><span class="sxs-lookup"><span data-stu-id="3f8c3-109">The series still share a common x-axis.</span></span>  
  
 <span data-ttu-id="3f8c3-110">Em situações em que existam mais de duas séries a serem comparadas, considere uma abordagem diferente para comparação e exibição de várias séries em um gráfico.</span><span class="sxs-lookup"><span data-stu-id="3f8c3-110">In situations where there are more than two series to be compared, consider a different approach for comparing and displaying multiple series in a chart.</span></span> <span data-ttu-id="3f8c3-111">Para obter mais informações, consulte [Várias séries em um gráfico &#40;Construtor de Relatórios e SSRS&#41;](multiple-series-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3f8c3-111">For more information, see [Multiple Series on a Chart &#40;Report Builder and SSRS&#41;](multiple-series-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="3f8c3-112">Um exemplo deste gráfico está disponível como um relatório de exemplo.</span><span class="sxs-lookup"><span data-stu-id="3f8c3-112">An example of this chart is available as a sample report.</span></span> <span data-ttu-id="3f8c3-113">Para obter mais informações sobre como baixar este relatório de exemplo e outros, consulte [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [Construtor de Relatórios e Report Designer relatórios de exemplo](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="3f8c3-113">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-plot-a-series-on-the-secondary-axis"></a><span data-ttu-id="3f8c3-114">Para plotar uma série no eixo secundário</span><span class="sxs-lookup"><span data-stu-id="3f8c3-114">To plot a series on the secondary axis</span></span>  
  
1.  <span data-ttu-id="3f8c3-115">Clique com o botão direito do mouse na série no gráfico ou em um campo na área **Valores** que você deseja exibir no eixo secundário e clique em **Propriedades da Série**.</span><span class="sxs-lookup"><span data-stu-id="3f8c3-115">Right-click the series in the chart or right-click on a field in the **Values** area that you want to display on the secondary axis and click **Series Properties**.</span></span> <span data-ttu-id="3f8c3-116">A caixa de diálogo **Propriedades da Série** é exibida.</span><span class="sxs-lookup"><span data-stu-id="3f8c3-116">The **Series Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="3f8c3-117">Clique em **Eixo e Área do Gráfico**e selecione qual dos eixos secundários você deseja habilitar, o eixo de valor ou o eixo de categoria.</span><span class="sxs-lookup"><span data-stu-id="3f8c3-117">Click **Axes and Chart Area**, and select which of the secondary axes you want to enable, the value axis or the category axis.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f8c3-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3f8c3-118">See Also</span></span>  
 <span data-ttu-id="3f8c3-119">[Formatando rótulos de eixo em um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3f8c3-119">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="3f8c3-120">Especificar um intervalo do eixo &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3f8c3-120">Specify an Axis Interval &#40;Report Builder and SSRS&#41;</span></span>](specify-an-axis-interval-report-builder-and-ssrs.md)  
  
  
