---
title: Gráficos de intervalos (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 48e351d3-ac5b-4eda-a4bd-32a0de206a30
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 76a9723bc55030da59d22c945a40ce4418b84ab3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681425"
---
# <a name="range-charts-report-builder-and-ssrs"></a><span data-ttu-id="8ebac-102">Gráficos de intervalos (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="8ebac-102">Range Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="8ebac-103">Um tipo de gráfico de intervalos exibe um conjunto de pontos de dados que são definidos por diversos valores para a mesma categoria.</span><span class="sxs-lookup"><span data-stu-id="8ebac-103">A range chart type displays a set of data points that are each defined by multiple values for the same category.</span></span> <span data-ttu-id="8ebac-104">Os valores são representados pela altura do marcador, de acordo com a medição feita pelo eixo y.</span><span class="sxs-lookup"><span data-stu-id="8ebac-104">Values are represented by the height of the marker as measured by the value axis.</span></span> <span data-ttu-id="8ebac-105">Os rótulos de categoria são exibidos no eixo de categoria.</span><span class="sxs-lookup"><span data-stu-id="8ebac-105">Category labels are displayed on the category axis.</span></span> <span data-ttu-id="8ebac-106">O gráfico de intervalos comum preenche a área entre os valores superior e inferior de cada ponto de dados.</span><span class="sxs-lookup"><span data-stu-id="8ebac-106">The plain range chart fills in the area between the top and bottom value for each data point.</span></span>  
  
 <span data-ttu-id="8ebac-107">A ilustração a seguir mostra um gráfico de intervalos comum com três séries.</span><span class="sxs-lookup"><span data-stu-id="8ebac-107">The following illustration shows a plain range chart with three series.</span></span>  
  
 <span data-ttu-id="8ebac-108">![Gráfico de intervalo](../media/rs-rangechart.gif "Gráfico de intervalo")</span><span class="sxs-lookup"><span data-stu-id="8ebac-108">![Range chart](../media/rs-rangechart.gif "Range chart")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="8ebac-109">Variações</span><span class="sxs-lookup"><span data-stu-id="8ebac-109">Variations</span></span>  
  
-   <span data-ttu-id="8ebac-110">**Intervalo suave**.</span><span class="sxs-lookup"><span data-stu-id="8ebac-110">**Smooth range**.</span></span> <span data-ttu-id="8ebac-111">Um intervalo suave exibe linhas curvas em vez de linhas retas.</span><span class="sxs-lookup"><span data-stu-id="8ebac-111">A smooth range chart displays curved lines rather than straight.</span></span>  
  
-   <span data-ttu-id="8ebac-112">**Intervalo de colunas**.</span><span class="sxs-lookup"><span data-stu-id="8ebac-112">**Column range**.</span></span> <span data-ttu-id="8ebac-113">Um intervalo de colunas usa colunas em vez de áreas para exibir os intervalos.</span><span class="sxs-lookup"><span data-stu-id="8ebac-113">A column range chart uses columns instead of areas to display the ranges.</span></span>  
  
-   <span data-ttu-id="8ebac-114">**Intervalo de barras**.</span><span class="sxs-lookup"><span data-stu-id="8ebac-114">**Bar range**.</span></span> <span data-ttu-id="8ebac-115">Um intervalo de barras usa barras em vez de áreas para exibir os intervalos.</span><span class="sxs-lookup"><span data-stu-id="8ebac-115">A bar range chart uses bars instead of areas to display the ranges.</span></span>  
  
## <a name="data-considerations-for-range-charts"></a><span data-ttu-id="8ebac-116">Considerações de dados para gráficos de intervalos</span><span class="sxs-lookup"><span data-stu-id="8ebac-116">Data Considerations for Range Charts</span></span>  
  
-   <span data-ttu-id="8ebac-117">Os tipos de gráfico de intervalos exigem dois valores por ponto de dados.</span><span class="sxs-lookup"><span data-stu-id="8ebac-117">Range chart types require two values per data point.</span></span> <span data-ttu-id="8ebac-118">Esses valores correspondem com um valor alto e um baixo que definem o intervalo para cada ponto de dados.</span><span class="sxs-lookup"><span data-stu-id="8ebac-118">These values correspond with a high value and a low value that defines the range for each data point.</span></span>  
  
-   <span data-ttu-id="8ebac-119">Os gráficos de intervalos só serão úteis para análise se os valores superiores sempre forem mais altos que os valores inferiores.</span><span class="sxs-lookup"><span data-stu-id="8ebac-119">Range charts are useful for analysis only if the top values are always higher than the bottom values.</span></span> <span data-ttu-id="8ebac-120">Caso contrário, considere o uso de um gráfico de linhas.</span><span class="sxs-lookup"><span data-stu-id="8ebac-120">If this is not the case, consider using a line chart.</span></span> <span data-ttu-id="8ebac-121">Se o valor alto for menor que o valor baixo, o gráfico de intervalos exibirá o valor absoluto da diferença entre esses valores.</span><span class="sxs-lookup"><span data-stu-id="8ebac-121">If the high value is lower the low value, the range chart will display the absolute value of the difference between these values.</span></span>  
  
-   <span data-ttu-id="8ebac-122">Se apenas um dos valores for especificado, o gráfico de intervalos será exibido como se ele fosse um gráfico de áreas comum, com um valor por ponto de dados.</span><span class="sxs-lookup"><span data-stu-id="8ebac-122">If only one value is specified, the range chart will display as if it were a regular area chart, with one value per data point.</span></span>  
  
-   <span data-ttu-id="8ebac-123">Os gráficos de intervalos geralmente são usados para grafar dados que contêm valores máximo e mínimo para cada grupo de categorias no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8ebac-123">Range charts are often used to graph data that contains minimum and maximum values for each category group in the dataset.</span></span>  
  
-   <span data-ttu-id="8ebac-124">O gráfico de intervalos não oferece suporte à exibição de marcadores em cada ponto de dados.</span><span class="sxs-lookup"><span data-stu-id="8ebac-124">Displaying markers on each data point is not supported on the range chart.</span></span>  
  
-   <span data-ttu-id="8ebac-125">Assim como no gráfico de áreas, em um gráfico de intervalos comum, se os valores em diversas séries forem semelhantes, as séries serão sobrepostas.</span><span class="sxs-lookup"><span data-stu-id="8ebac-125">Like the area chart, in a plain range chart, if the values in multiple series are similar, the series will overlap.</span></span> <span data-ttu-id="8ebac-126">Neste cenário, você pode usar um gráfico de intervalos de colunas ou de barras em vez de um gráfico de intervalos comum.</span><span class="sxs-lookup"><span data-stu-id="8ebac-126">In this scenario, you may want to use a column range or bar range chart instead of a plain range chart.</span></span>  
  
-   <span data-ttu-id="8ebac-127">Os gráficos de Gantt podem ser criados usando um gráfico de intervalos de barras.</span><span class="sxs-lookup"><span data-stu-id="8ebac-127">Gantt charts can be created using a range bar chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ebac-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8ebac-128">See Also</span></span>  
 <span data-ttu-id="8ebac-129">[Gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8ebac-129">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8ebac-130">[Tipos de gráficos &#40;Construtor de Relatórios e SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8ebac-130">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="8ebac-131">Formatar um gráfico &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8ebac-131">Formatting a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-a-chart-report-builder-and-ssrs.md)  
  
  
