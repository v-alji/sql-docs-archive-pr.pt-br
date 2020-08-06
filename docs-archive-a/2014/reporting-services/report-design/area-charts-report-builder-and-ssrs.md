---
title: Gráficos de áreas (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 245b236d-1d55-4744-b752-80bd133502aa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f401efa0abd5eac8ab39e511bc6b16a4f381ebdf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681437"
---
# <a name="area-charts-report-builder-and-ssrs"></a><span data-ttu-id="4a9c3-102">Gráficos de área (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="4a9c3-102">Area Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="4a9c3-103">Um gráfico de área exibe uma série como um conjunto de pontos conectados por uma linha, com toda a área preenchida abaixo da linha.</span><span class="sxs-lookup"><span data-stu-id="4a9c3-103">An area chart displays a series as a set of points connected by a line, with all the area filled in below the line.</span></span> <span data-ttu-id="4a9c3-104">Para obter mais informações sobre como adicionar dados a um gráfico de área, consulte [Gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4a9c3-104">For more information on how to add data to an area chart, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="4a9c3-105">A ilustração a seguir mostra um exemplo de um gráfico de áreas empilhadas.</span><span class="sxs-lookup"><span data-stu-id="4a9c3-105">The following illustration shows an example of a stacked area chart.</span></span> <span data-ttu-id="4a9c3-106">Os dados são bem-adequados para serem exibidos em um gráfico de áreas empilhadas porque o gráfico pode exibir os totais de todas as séries, bem como a proporção com que cada série contribui no total.</span><span class="sxs-lookup"><span data-stu-id="4a9c3-106">The data is well suited for display on a stacked area chart because the chart can display totals for all series as well as the proportion that each series contributes to the total.</span></span>  
  
 <span data-ttu-id="4a9c3-107">![Gráfico de área](../media/areachart.gif "Gráfico de área")</span><span class="sxs-lookup"><span data-stu-id="4a9c3-107">![Area chart](../media/areachart.gif "Area chart")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="4a9c3-108">Variações</span><span class="sxs-lookup"><span data-stu-id="4a9c3-108">Variations</span></span>  
  
-   <span data-ttu-id="4a9c3-109">**Área empilhada**.</span><span class="sxs-lookup"><span data-stu-id="4a9c3-109">**Stacked area**.</span></span> <span data-ttu-id="4a9c3-110">Um gráfico de áreas no qual várias séries são empilhadas verticalmente.</span><span class="sxs-lookup"><span data-stu-id="4a9c3-110">An area chart where multiple series are stacked vertically.</span></span> <span data-ttu-id="4a9c3-111">Se houver apenas uma série em seu gráfico, o gráfico de áreas empilhadas exibirá o mesmo que o gráfico de áreas.</span><span class="sxs-lookup"><span data-stu-id="4a9c3-111">If there is only one series in your chart, the stacked area chart will display the same as an area chart.</span></span>  
  
-   <span data-ttu-id="4a9c3-112">**Porcentual de área empilhada**.</span><span class="sxs-lookup"><span data-stu-id="4a9c3-112">**Percent stacked area**.</span></span> <span data-ttu-id="4a9c3-113">Um gráfico de áreas no qual várias séries são empilhadas verticalmente para ajustar toda a área de gráfico.</span><span class="sxs-lookup"><span data-stu-id="4a9c3-113">An area chart where multiple series are stacked vertically to fit the entire chart area.</span></span> <span data-ttu-id="4a9c3-114">Se houver apenas uma série em seu gráfico, o gráfico de áreas empilhadas exibirá o mesmo que o gráfico de áreas.</span><span class="sxs-lookup"><span data-stu-id="4a9c3-114">If there is only one series in your chart, the stacked area chart will display the same as an area chart.</span></span>  
  
-   <span data-ttu-id="4a9c3-115">**Área suave**.</span><span class="sxs-lookup"><span data-stu-id="4a9c3-115">**Smooth area**.</span></span> <span data-ttu-id="4a9c3-116">Um gráfico de áreas onde os pontos de dados são conectados por uma linha suave em vez de uma linha regular.</span><span class="sxs-lookup"><span data-stu-id="4a9c3-116">An area chart where the data points are connected by a smooth line instead of a regular line.</span></span> <span data-ttu-id="4a9c3-117">Use um gráfico de áreas suaves em vez de um gráfico de áreas quando você estiver mais preocupado com as tendências de exibição do que com a exibição dos valores dos pontos de dados individuais.</span><span class="sxs-lookup"><span data-stu-id="4a9c3-117">Use a smooth area chart instead of an area chart when you are more concerned with displaying trends than with displaying the values of individual data points.</span></span>  
  
## <a name="data-considerations-for-area-charts"></a><span data-ttu-id="4a9c3-118">Considerações de dados para gráficos de área</span><span class="sxs-lookup"><span data-stu-id="4a9c3-118">Data Considerations for Area Charts</span></span>  
  
-   <span data-ttu-id="4a9c3-119">Junto com o gráfico de linhas, o gráfico de áreas é o único tipo de gráfico que exibe dados contiguamente.</span><span class="sxs-lookup"><span data-stu-id="4a9c3-119">Along with the line chart, the area chart is the only chart type that displays data contiguously.</span></span> <span data-ttu-id="4a9c3-120">Por esta razão, normalmente um gráfico de áreas é usado para representar dados que ocorrem em um período de tempo contínuo.</span><span class="sxs-lookup"><span data-stu-id="4a9c3-120">For this reason, an area chart is commonly used to represent data that occurs over a continuous period of time.</span></span>  
  
-   <span data-ttu-id="4a9c3-121">O porcentual de um gráfico de áreas empilhadas é útil para mostrar dados proporcionais que ocorrem com o passar do tempo.</span><span class="sxs-lookup"><span data-stu-id="4a9c3-121">A percent stacked area chart is useful for showing proportional data that occurs over time.</span></span>  
  
-   <span data-ttu-id="4a9c3-122">Se houver apenas uma série, um gráfico de áreas empilhadas será desenhado em um gráfico de áreas.</span><span class="sxs-lookup"><span data-stu-id="4a9c3-122">If there is only one series, a stacked area chart will be drawn as an area chart.</span></span>  
  
-   <span data-ttu-id="4a9c3-123">Em um gráfico de áreas comum, se os valores em várias séries forem semelhantes, as séries serão sobrepostas, impedindo a exibição de valores de pontos de dados importantes.</span><span class="sxs-lookup"><span data-stu-id="4a9c3-123">In a plain area chart, if the values in multiple series are similar, the areas may overlap, obscuring important data point values.</span></span> <span data-ttu-id="4a9c3-124">Esse problema pode ser solucionado alterando o tipo de gráfico para um gráfico de área empilhada, que foi desenvolvido para mostrar várias séries em um gráfico de áreas.</span><span class="sxs-lookup"><span data-stu-id="4a9c3-124">You can resolve this issue by changing the chart type to a stacked area chart, which is designed to show multiple series on an area chart.</span></span>  
  
-   <span data-ttu-id="4a9c3-125">Caso o gráfico de áreas empilhadas contenha lacunas, pode ser que seu conjunto de dados tenha valores vazios, que serão exibidos como uma seção vaga nesse tipo de gráfico.</span><span class="sxs-lookup"><span data-stu-id="4a9c3-125">If your stacked area chart contains gaps, it is possible that your dataset includes empty values, which will be shown as a vacant section on a stacked area chart.</span></span> <span data-ttu-id="4a9c3-126">Se o seu conjunto de dados tiver valores vazios, insira pontos vazios no gráfico.</span><span class="sxs-lookup"><span data-stu-id="4a9c3-126">If your dataset includes empty values, consider inserting empty points on the chart.</span></span> <span data-ttu-id="4a9c3-127">Ao adicionar pontos vazios, as áreas vazias no gráfico serão preenchidas com uma cor diferente para indicar valores nulos ou zero.</span><span class="sxs-lookup"><span data-stu-id="4a9c3-127">Adding empty points will fill in the empty areas on the chart with a different color to indicate null or zero values.</span></span> <span data-ttu-id="4a9c3-128">Para obter mais informações, consulte [Adicionar pontos vazios ao gráfico &#40;Construtor de relatórios e SSRS&#41;](add-empty-points-to-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4a9c3-128">For more information, see [Add Empty Points to the Chart &#40;Report Builder and SSRS&#41;](add-empty-points-to-a-chart-report-builder-and-ssrs.md).</span></span>  
  
-   <span data-ttu-id="4a9c3-129">O comportamento do gráfico de áreas é bem semelhante ao comportamento dos gráficos de colunas e linhas.</span><span class="sxs-lookup"><span data-stu-id="4a9c3-129">Area chart types are very similar to column and line charts in behavior.</span></span> <span data-ttu-id="4a9c3-130">Se você estiver fazendo uma comparação entre várias séries, use um gráfico de colunas.</span><span class="sxs-lookup"><span data-stu-id="4a9c3-130">If you are making a comparison between multiple series, consider using a column chart instead.</span></span> <span data-ttu-id="4a9c3-131">Se estiver analisando tendências durante um determinado período de tempo, use um gráfico de linhas.</span><span class="sxs-lookup"><span data-stu-id="4a9c3-131">If you are analyzing trends over a period of time, consider using a line chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a9c3-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4a9c3-132">See Also</span></span>  
 <span data-ttu-id="4a9c3-133">[Gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4a9c3-133">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="4a9c3-134">[Tipos de gráficos &#40;Construtor de Relatórios e SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4a9c3-134">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="4a9c3-135">[Gráficos de linhas &#40;Construtor de Relatórios e SSRS&#41;](line-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4a9c3-135">[Line Charts &#40;Report Builder and SSRS&#41;](line-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="4a9c3-136">[Alterar um tipo de gráfico &#40;Construtor de Relatórios e SSRS&#41;](change-a-chart-type-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4a9c3-136">[Change a Chart Type &#40;Report Builder and SSRS&#41;](change-a-chart-type-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="4a9c3-137">Pontos de dados vazios e nulos em gráficos &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="4a9c3-137">Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;</span></span>](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md)  
  
  
