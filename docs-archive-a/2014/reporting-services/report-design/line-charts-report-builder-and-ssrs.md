---
title: Gráficos de linhas (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 194e6679-890d-4a3e-a756-130d32ef7e29
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 44e7a011186e66e6b8bdc8b5dd31939c883e320b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684510"
---
# <a name="line-charts-report-builder-and-ssrs"></a><span data-ttu-id="14a10-102">Gráficos de linhas (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="14a10-102">Line Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="14a10-103">Um gráfico de linhas exibe uma série como um conjunto de pontos conectado por uma única linha.</span><span class="sxs-lookup"><span data-stu-id="14a10-103">A line chart displays a series as a set of points connected by a single line.</span></span> <span data-ttu-id="14a10-104">As linhas de gráfico são usadas para representar grandes quantidades de dados que ocorrem em um período de tempo contínuo.</span><span class="sxs-lookup"><span data-stu-id="14a10-104">Line charts are used to representing large amounts of data that occur over a continuous period of time.</span></span> <span data-ttu-id="14a10-105">Para obter mais informações sobre como adicionar dados a um gráfico de linhas, consulte [Gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="14a10-105">For more information about how to add data to a line chart, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="14a10-106">A ilustração a seguir mostra um gráfico de linhas que contém três séries.</span><span class="sxs-lookup"><span data-stu-id="14a10-106">The following illustration shows a line chart that contains three series.</span></span>  
  
 <span data-ttu-id="14a10-107">![Gráfico de linhas](../media/rs-linechart.gif "Gráfico de Linhas")</span><span class="sxs-lookup"><span data-stu-id="14a10-107">![Line chart](../media/rs-linechart.gif "Line chart")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="14a10-108">Variações</span><span class="sxs-lookup"><span data-stu-id="14a10-108">Variations</span></span>  
  
-   <span data-ttu-id="14a10-109">**Linha suave**.</span><span class="sxs-lookup"><span data-stu-id="14a10-109">**Smooth line**.</span></span> <span data-ttu-id="14a10-110">Um gráfico de linhas que usa uma linha curva em vez de uma linha regular.</span><span class="sxs-lookup"><span data-stu-id="14a10-110">A line chart that uses a curved line instead of a regular line.</span></span>  
  
-   <span data-ttu-id="14a10-111">**Linha escalonada**.</span><span class="sxs-lookup"><span data-stu-id="14a10-111">**Stepped line**.</span></span> <span data-ttu-id="14a10-112">Um gráfico de linhas que usa uma linha escalonada em vez de uma linha regular.</span><span class="sxs-lookup"><span data-stu-id="14a10-112">A line chart that uses a stepped line instead of a regular line.</span></span> <span data-ttu-id="14a10-113">A linha escalonada conecta os pontos usando uma linha que a deixa com uma aparência semelhante aos degraus de uma escadaria.</span><span class="sxs-lookup"><span data-stu-id="14a10-113">The stepped line connects points by using a line that makes it look like steps on a ladder or staircase.</span></span>  
  
-   <span data-ttu-id="14a10-114">**Minigráficos**.</span><span class="sxs-lookup"><span data-stu-id="14a10-114">**Sparkline charts**.</span></span> <span data-ttu-id="14a10-115">Variações do gráfico de linha que mostram apenas a série de linha na célula de uma tabela ou matriz.</span><span class="sxs-lookup"><span data-stu-id="14a10-115">Variations of the line chart that show only the line series in the cell of a table or matrix.</span></span> <span data-ttu-id="14a10-116">Para obter mais informações, consulte [Minigráficos e barras de dados &#40;Construtor de Relatórios e SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="14a10-116">For more information, see [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="data-considerations-for-line-charts"></a><span data-ttu-id="14a10-117">Considerações de dados para gráficos de linhas</span><span class="sxs-lookup"><span data-stu-id="14a10-117">Data Considerations for Line Charts</span></span>  
  
-   <span data-ttu-id="14a10-118">Para melhorar o impacto visual do gráfico de linhas padrão, altere a largura das bordas para 3 e adicione um deslocamento de sombra de 1.</span><span class="sxs-lookup"><span data-stu-id="14a10-118">To improve the visual impact of the default line chart, consider changing the width of the series border to 3, and adding a shadow offset of 1.</span></span> <span data-ttu-id="14a10-119">Esse processo criará um gráfico de linhas mais espesso.</span><span class="sxs-lookup"><span data-stu-id="14a10-119">This will create a much bolder line chart.</span></span> <span data-ttu-id="14a10-120">Será preciso reverter essas propriedades para os valores originais caso você altere o tipo de gráfico definido como Linha para outro tipo.</span><span class="sxs-lookup"><span data-stu-id="14a10-120">You will need to revert these properties to their original values if you change the chart type from Line to another type.</span></span>  
  
-   <span data-ttu-id="14a10-121">Se o conjunto de dados incluir valores vazios, o gráfico de linhas adicionará pontos vazios, no formulário de linhas como espaços reservados para manter a continuidade no gráfico.</span><span class="sxs-lookup"><span data-stu-id="14a10-121">If your dataset includes empty values, the line chart will add empty points, in the form of placeholder lines, in order to maintain continuity on the chart.</span></span> <span data-ttu-id="14a10-122">Se você optar por não ver essas linhas, exiba o conjunto de dados usando um gráfico não contínuo, como, por exemplo, um gráfico de barras ou colunas.</span><span class="sxs-lookup"><span data-stu-id="14a10-122">If you would rather not see these lines, consider displaying your dataset using a non-contiguous chart type such as a bar or column chart.</span></span>  
  
-   <span data-ttu-id="14a10-123">Um gráfico de linhas requer pelo menos dois pontos para desenhar uma linha.</span><span class="sxs-lookup"><span data-stu-id="14a10-123">A line chart requires at least two points to draw a line.</span></span>  <span data-ttu-id="14a10-124">Se o conjunto de dados tiver apenas um ponto de dados, o gráfico de linhas exibirá apenas um marcador de ponto de dados.</span><span class="sxs-lookup"><span data-stu-id="14a10-124">If your dataset has only one data point, the line chart will display as a single data point marker.</span></span>  
  
-   <span data-ttu-id="14a10-125">Uma série que é desenhada como uma linha não ocupará muito espaço dentro de uma área de gráfico.</span><span class="sxs-lookup"><span data-stu-id="14a10-125">A series that is drawn as a line will not take up much space within a chart area.</span></span>  <span data-ttu-id="14a10-126">Por isso, os gráficos de linhas são frequentemente combinados com outros tipos de gráficos, como gráficos de colunas.</span><span class="sxs-lookup"><span data-stu-id="14a10-126">For this reason, line charts are frequently combined with other chart types such as column charts.</span></span> <span data-ttu-id="14a10-127">Entretanto, não é possível combinar um gráfico de linhas com gráficos do tipo barras, polares, tortas ou formas.</span><span class="sxs-lookup"><span data-stu-id="14a10-127">However, you cannot combine a line chart with bar, polar, pie or shape chart types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14a10-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="14a10-128">See Also</span></span>  
 <span data-ttu-id="14a10-129">[Gráficos de barras &#40;Construtor de Relatórios e SSRS&#41;](bar-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="14a10-129">[Bar Charts &#40;Report Builder and SSRS&#41;](bar-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="14a10-130">[Gráficos de colunas &#40;Construtor de Relatórios e SSRS&#41;](column-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="14a10-130">[Column Charts &#40;Report Builder and SSRS&#41;](column-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="14a10-131">[Gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="14a10-131">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="14a10-132">[Tipos de gráficos &#40;Construtor de Relatórios e SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="14a10-132">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="14a10-133">[Gráficos de áreas &#40;Construtor de Relatórios e SSRS&#41;](area-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="14a10-133">[Area Charts &#40;Report Builder and SSRS&#41;](area-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="14a10-134">[Pontos de dados vazios e nulos em gráficos &#40;Construtor de Relatórios e SSRS&#41;](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="14a10-134">[Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="14a10-135">Gráficos &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="14a10-135">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
