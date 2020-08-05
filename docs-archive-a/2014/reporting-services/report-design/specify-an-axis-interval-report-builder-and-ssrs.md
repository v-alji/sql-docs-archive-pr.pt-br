---
title: Especificar um intervalo do eixo (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ae46712d-a5bf-44c0-9929-e30ccc1e7e33
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 70b64b824933753a8482360f193ca4ccf71e8d52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569072"
---
# <a name="specify-an-axis-interval-report-builder-and-ssrs"></a><span data-ttu-id="fdd23-102">Especificar um intervalo do eixo (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="fdd23-102">Specify an Axis Interval (Report Builder and SSRS)</span></span>
  <span data-ttu-id="fdd23-103">O intervalo do eixo define o número de rótulos e as marcas de escala associadas em um eixo.</span><span class="sxs-lookup"><span data-stu-id="fdd23-103">The axis interval defines the number of labels and accompanying tick marks on an axis.</span></span> <span data-ttu-id="fdd23-104">No eixo de valor, os intervalos do eixo fornecem uma medida consistente dos pontos de dados no gráfico.</span><span class="sxs-lookup"><span data-stu-id="fdd23-104">On the value axis, axis intervals provide a consistent measure of the data points on the chart.</span></span> <span data-ttu-id="fdd23-105">No entanto, no eixo de categoria, esta funcionalidade pode fazer com que as categorias sejam exibidas sem os rótulos do eixo.</span><span class="sxs-lookup"><span data-stu-id="fdd23-105">However, on the category axis, this functionality can cause categories to appear without axis labels.</span></span> <span data-ttu-id="fdd23-106">Você pode especificar o número de intervalos que deseja na propriedade Intervalo do eixo.</span><span class="sxs-lookup"><span data-stu-id="fdd23-106">You can specify the number of intervals you want in the axis Interval property.</span></span> [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="fdd23-107">calcula o número de intervalos no tempo de execução, com base nos dados do conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="fdd23-107">calculates the number of intervals at run time, based on the data in the result set.</span></span> <span data-ttu-id="fdd23-108">Para obter mais informações sobre como os intervalos de eixo são calculados, consulte [Formatação de rótulos de eixo de um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="fdd23-108">For more information about how axis intervals are calculated, see [Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="fdd23-109">Este tópico não é aplicável para valores de data ou hora no eixo de categoria.</span><span class="sxs-lookup"><span data-stu-id="fdd23-109">This topic is not applicable for date or time values on the category axis.</span></span> <span data-ttu-id="fdd23-110">Por padrão, os valores de `DateTime` são exibidos como dias.</span><span class="sxs-lookup"><span data-stu-id="fdd23-110">Be default, `DateTime` values appear as days.</span></span> <span data-ttu-id="fdd23-111">Para especificar um intervalo de data ou hora diferente, como um intervalo de mês ou hora, você deve formatar os rótulos dos eixos e definir o eixo para exibir instâncias de tipos `DateTime` em vez de tipos `String`.</span><span class="sxs-lookup"><span data-stu-id="fdd23-111">To specify a different date or time interval, such as a month or time interval, you must format the axis labels and set the axis to display instances of `DateTime` types instead of `String` types.</span></span> <span data-ttu-id="fdd23-112">Além disso, você deve definir a propriedade Intervalo.</span><span class="sxs-lookup"><span data-stu-id="fdd23-112">In addition, you must set the Interval property.</span></span> <span data-ttu-id="fdd23-113">Para obter mais informações, consulte [Formatar rótulos de eixo como datas ou moedas &#40;Construtor de Relatórios e SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="fdd23-113">For more information, see [Format Axis Labels as Dates or Currencies &#40;Report Builder and SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="fdd23-114">Este tópico não se aplica a gráficos de pizza, rosca, funil ou pirâmide que não possuem eixos.</span><span class="sxs-lookup"><span data-stu-id="fdd23-114">This topic does not apply to pie, doughnut, funnel or pyramid charts, which do not have axes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fdd23-115">O eixo de categoria geralmente é o eixo horizontal ou o eixo x.</span><span class="sxs-lookup"><span data-stu-id="fdd23-115">The category axis is usually the horizontal or x-axis.</span></span> <span data-ttu-id="fdd23-116">No entanto, para os gráficos de barras, o eixo de categoria é o vertical ou eixo y.</span><span class="sxs-lookup"><span data-stu-id="fdd23-116">However, for bar charts, the category axis is the vertical or y-axis.</span></span>  
  
 <span data-ttu-id="fdd23-117">Um exemplo de um gráfico que especifica intervalos de eixos diferentes está disponível como um relatório de exemplo.</span><span class="sxs-lookup"><span data-stu-id="fdd23-117">An example of a chart specifying different axis intervals is available as a sample report.</span></span> <span data-ttu-id="fdd23-118">Para obter mais informações sobre como baixar este relatório de exemplo e outros, consulte [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [Construtor de Relatórios e Report Designer relatórios de exemplo](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="fdd23-118">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-show-all-category-labels-on-the-x-axis"></a><span data-ttu-id="fdd23-119">Para mostrar todos os rótulos de categorias no eixo x</span><span class="sxs-lookup"><span data-stu-id="fdd23-119">To show all category labels on the x-axis</span></span>  
  
1.  <span data-ttu-id="fdd23-120">Clique com o botão direito do mouse no eixo da categoria e clique em **Propriedades do Eixo**.</span><span class="sxs-lookup"><span data-stu-id="fdd23-120">Right-click the category axis and click **Axis Properties**.</span></span> <span data-ttu-id="fdd23-121">A caixa de diálogo **Propriedades do Eixo** é aberta.</span><span class="sxs-lookup"><span data-stu-id="fdd23-121">The **Axis Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="fdd23-122">Em **Opções de eixo**, defina `Interval` como **1**.</span><span class="sxs-lookup"><span data-stu-id="fdd23-122">In **Axis Options**, set `Interval` to **1**.</span></span> <span data-ttu-id="fdd23-123">Cada rótulo do grupo de categorias é exibido.</span><span class="sxs-lookup"><span data-stu-id="fdd23-123">Every category group label is displayed.</span></span> <span data-ttu-id="fdd23-124">Para mostrar cada rótulo de outro grupo de categorias no eixo x, digite **2**.</span><span class="sxs-lookup"><span data-stu-id="fdd23-124">If you want to show every other category group label on the x-axis, type **2**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="fdd23-125">Quando um intervalo do eixo é definido, todos os rótulos automáticos são desabilitados.</span><span class="sxs-lookup"><span data-stu-id="fdd23-125">When an axis interval is set, all automatic labeling is disabled.</span></span> <span data-ttu-id="fdd23-126">Se um valor para o intervalo do eixo for especificado, poderá ocorrer um comportamento imprevisível do rótulo, dependendo da quantidade de categorias existentes no eixo de categoria.</span><span class="sxs-lookup"><span data-stu-id="fdd23-126">If you specify a value for the axis interval, you may experience unpredictable labeling behavior depending on how many categories are on the category axis.</span></span>  
  
### <a name="to-enable-a-variable-interval-calculation-on-an-axis"></a><span data-ttu-id="fdd23-127">Para habilitar um cálculo do intervalo de variáveis em um eixo</span><span class="sxs-lookup"><span data-stu-id="fdd23-127">To enable a variable interval calculation on an axis</span></span>  
  
1.  <span data-ttu-id="fdd23-128">Clique com o botão direito do mouse no eixo do gráfico que deseja alterar e clique em **Propriedades do Eixo**.</span><span class="sxs-lookup"><span data-stu-id="fdd23-128">Right-click the chart axis that you want to change, and then click **Axis Properties**.</span></span> <span data-ttu-id="fdd23-129">A caixa de diálogo **Propriedades do Eixo** é aberta.</span><span class="sxs-lookup"><span data-stu-id="fdd23-129">The **Axis Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="fdd23-130">Em **Opções de eixo**, defina `Interval` como **automático**. O gráfico exibirá o número ideal de rótulos de categoria que podem se ajustar ao longo do eixo.</span><span class="sxs-lookup"><span data-stu-id="fdd23-130">In **Axis Options**, set `Interval` to **Auto**. The chart will display the optimal number of category labels that can fit along the axis.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fdd23-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fdd23-131">See Also</span></span>  
 <span data-ttu-id="fdd23-132">[Formatando um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fdd23-132">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="fdd23-133">[Formatando pontos de dados em um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fdd23-133">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="fdd23-134">[Classificar dados em uma região de dados &#40;Construtor de Relatórios e SSRS&#41;](sort-data-in-a-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fdd23-134">[Sort Data in a Data Region &#40;Report Builder and SSRS&#41;](sort-data-in-a-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="fdd23-135">[Caixa de diálogo Propriedades do eixo, opções de eixo &#40;Construtor de Relatórios e SSRS&#41;](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fdd23-135">[Axis Properties Dialog Box, Axis Options &#40;Report Builder and SSRS&#41;](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="fdd23-136">[Especifique uma escala logarítmica &#40;Construtor de Relatórios e SSRS&#41;](specify-a-logarithmic-scale-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fdd23-136">[Specify a Logarithmic Scale &#40;Report Builder and SSRS&#41;](specify-a-logarithmic-scale-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="fdd23-137">Plotar dados em um eixo secundário &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="fdd23-137">Plot Data on a Secondary Axis &#40;Report Builder and SSRS&#41;</span></span>](plot-data-on-a-secondary-axis-report-builder-and-ssrs.md)  
  
  
