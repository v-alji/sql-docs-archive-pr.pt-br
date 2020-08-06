---
title: Gráficos polares (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c9402d8f-202a-4cdf-949e-50f5b1d2b885
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b8c4dd9394fab3e076c4a714375954a616e081f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678583"
---
# <a name="polar-charts-report-builder-and-ssrs"></a><span data-ttu-id="b57f3-102">Gráficos polares (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="b57f3-102">Polar Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="b57f3-103">Um gráfico polar exibe uma série como um conjunto de pontos agrupados por categoria em um círculo de 360 graus.</span><span class="sxs-lookup"><span data-stu-id="b57f3-103">A polar chart displays a series as a set of points that are grouped by category on a 360-degree circle.</span></span> <span data-ttu-id="b57f3-104">Os valores são representados pelo comprimento do ponto, conforme medido do centro do círculo.</span><span class="sxs-lookup"><span data-stu-id="b57f3-104">Values are represented by the length of the point as measured from the center of the circle.</span></span> <span data-ttu-id="b57f3-105">Quanto mais distante o ponto está do centro, maior é o seu valor.</span><span class="sxs-lookup"><span data-stu-id="b57f3-105">The farther the point is from the center, the greater its value.</span></span> <span data-ttu-id="b57f3-106">São exibidos rótulos de categoria no perímetro do gráfico.</span><span class="sxs-lookup"><span data-stu-id="b57f3-106">Category labels are displayed on the perimeter of the chart.</span></span> <span data-ttu-id="b57f3-107">Para obter mais informações sobre como adicionar dados a um gráfico polar, consulte [Gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b57f3-107">For more information on how to add data to a polar chart, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="b57f3-108">Variações</span><span class="sxs-lookup"><span data-stu-id="b57f3-108">Variations</span></span>  
  
-   <span data-ttu-id="b57f3-109">**Gráfico de radar**.</span><span class="sxs-lookup"><span data-stu-id="b57f3-109">**Radar chart**.</span></span> <span data-ttu-id="b57f3-110">Um gráfico de radar exibe uma série como uma linha ou área circular.</span><span class="sxs-lookup"><span data-stu-id="b57f3-110">A radar chart displays a series as a circular line or area.</span></span> <span data-ttu-id="b57f3-111">Ao contrário do gráfico polar, o gráfico de radar não exibe dados em termos de coordenadas polares.</span><span class="sxs-lookup"><span data-stu-id="b57f3-111">Unlike the polar chart, the radar chart does not display data in terms of polar coordinates.</span></span>  
  
## <a name="data-considerations-for-polar-charts"></a><span data-ttu-id="b57f3-112">Considerações de dados para gráficos polares</span><span class="sxs-lookup"><span data-stu-id="b57f3-112">Data Considerations for Polar Charts</span></span>  
  
-   <span data-ttu-id="b57f3-113">O gráfico de radar é útil para comparações entre várias séries de dados de categoria.</span><span class="sxs-lookup"><span data-stu-id="b57f3-113">The radar chart is useful for comparisons between multiple series of category data.</span></span>  
  
-   <span data-ttu-id="b57f3-114">Os gráficos polares são usados com mais frequência para fazer gráficos de dados polares, nos quais cada ponto de dados é determinado por um ângulo ou uma distância.</span><span class="sxs-lookup"><span data-stu-id="b57f3-114">Polar charts are most commonly used to graph polar data, where each data point is determined by an angle and a distance.</span></span>  
  
-   <span data-ttu-id="b57f3-115">Os gráficos polares não podem ser combinados com qualquer outro tipo de gráfico na mesma área de gráfico.</span><span class="sxs-lookup"><span data-stu-id="b57f3-115">Polar charts cannot be combined with any other chart type in the same chart area.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b57f3-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b57f3-116">Example</span></span>  
 <span data-ttu-id="b57f3-117">O exemplo a seguir mostra como um gráfico de radar pode ser usado.</span><span class="sxs-lookup"><span data-stu-id="b57f3-117">The following example shows how a radar chart can be used.</span></span> <span data-ttu-id="b57f3-118">A tabela a seguir fornece dados de amostra do gráfico.</span><span class="sxs-lookup"><span data-stu-id="b57f3-118">The table below provides sample data for the chart.</span></span>  
  
|<span data-ttu-id="b57f3-119">Nome</span><span class="sxs-lookup"><span data-stu-id="b57f3-119">Name</span></span>|<span data-ttu-id="b57f3-120">Sales</span><span class="sxs-lookup"><span data-stu-id="b57f3-120">Sales</span></span>|  
|----------|-----------|  
|<span data-ttu-id="b57f3-121">Arbustos</span><span class="sxs-lookup"><span data-stu-id="b57f3-121">Shrubs</span></span>|<span data-ttu-id="b57f3-122">61</span><span class="sxs-lookup"><span data-stu-id="b57f3-122">61</span></span>|  
|<span data-ttu-id="b57f3-123">Sementes</span><span class="sxs-lookup"><span data-stu-id="b57f3-123">Seeds</span></span>|<span data-ttu-id="b57f3-124">78</span><span class="sxs-lookup"><span data-stu-id="b57f3-124">78</span></span>|  
|<span data-ttu-id="b57f3-125">Bulbos</span><span class="sxs-lookup"><span data-stu-id="b57f3-125">Bulbs</span></span>|<span data-ttu-id="b57f3-126">60</span><span class="sxs-lookup"><span data-stu-id="b57f3-126">60</span></span>|  
|<span data-ttu-id="b57f3-127">Árvores</span><span class="sxs-lookup"><span data-stu-id="b57f3-127">Trees</span></span>|<span data-ttu-id="b57f3-128">38</span><span class="sxs-lookup"><span data-stu-id="b57f3-128">38</span></span>|  
|<span data-ttu-id="b57f3-129">Flores</span><span class="sxs-lookup"><span data-stu-id="b57f3-129">Flowers</span></span>|<span data-ttu-id="b57f3-130">81</span><span class="sxs-lookup"><span data-stu-id="b57f3-130">81</span></span>|  
  
 <span data-ttu-id="b57f3-131">Nesse exemplo, o campo Nome é colocado na área Grupos de Categorias.</span><span class="sxs-lookup"><span data-stu-id="b57f3-131">In this example, the Name field is placed in the Category Groups area.</span></span> <span data-ttu-id="b57f3-132">O campo Vendas é colocado na área Valores.</span><span class="sxs-lookup"><span data-stu-id="b57f3-132">The Sales field is placed in the Values area.</span></span> <span data-ttu-id="b57f3-133">O campo Vendas é agregado automaticamente para o gráfico quando você o lança.</span><span class="sxs-lookup"><span data-stu-id="b57f3-133">The Sales field is automatically aggregated for the chart when you drop it.</span></span> <span data-ttu-id="b57f3-134">O gráfico de radar calcula onde colocar os rótulos com base no número de valores no campo Vendas, que contém cinco valores e coloca rótulos em cinco pontos equidistantes em um círculo.</span><span class="sxs-lookup"><span data-stu-id="b57f3-134">The radar chart calculates where to place the labels based on the number of values in the Sales field, which contains five values and places labels at five equidistant points on a circle.</span></span> <span data-ttu-id="b57f3-135">Se o campo Vendas continha três valores, os rótulos seriam colocados em três pontos equidistantes em um círculo.</span><span class="sxs-lookup"><span data-stu-id="b57f3-135">If the Sales field contained three values, the labels would be placed at three equidistant points on a circle.</span></span>  
  
 <span data-ttu-id="b57f3-136">A ilustração a seguir mostra um exemplo de um gráfico de radar baseado nos dados apresentados.</span><span class="sxs-lookup"><span data-stu-id="b57f3-136">The following illustration shows an example of a radar chart based on the data presented.</span></span>  
  
 <span data-ttu-id="b57f3-137">![Gráfico de radar](../media/rs-radarchart.gif "Gráfico de radar")</span><span class="sxs-lookup"><span data-stu-id="b57f3-137">![Radar chart](../media/rs-radarchart.gif "Radar chart")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b57f3-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b57f3-138">See Also</span></span>  
 <span data-ttu-id="b57f3-139">[Gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b57f3-139">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b57f3-140">[Formatando um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b57f3-140">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b57f3-141">[Tipos de gráficos &#40;Construtor de Relatórios e SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b57f3-141">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b57f3-142">[Gráficos de linhas &#40;Construtor de Relatórios e SSRS&#41;](line-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b57f3-142">[Line Charts &#40;Report Builder and SSRS&#41;](line-charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="b57f3-143">Pontos de dados vazios e nulos em gráficos &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b57f3-143">Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;</span></span>](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md)  
  
  
