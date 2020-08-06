---
title: Adicionar pontos vazios ao gráfico (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2b056119-439f-494f-83cf-ee0c05dc6487
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 53d891c58210bcd51cd4e49f2f9a691a7729c884
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684074"
---
# <a name="add-empty-points-to-the-chart-report-builder-and-ssrs"></a><span data-ttu-id="a0cc2-102">Adicionar pontos vazios ao gráfico (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="a0cc2-102">Add Empty Points to the Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a0cc2-103">Valores nulos são mostrados no gráfico como espaços vazios ou lacunas entre os pontos de dados em uma série.</span><span class="sxs-lookup"><span data-stu-id="a0cc2-103">Null values are shown on the chart as empty spaces or gaps between data points in a series.</span></span> <span data-ttu-id="a0cc2-104">Pontos vazios são pontos de dados que podem ser inseridos em um espaço vazio criado por valores nulos.</span><span class="sxs-lookup"><span data-stu-id="a0cc2-104">Empty points are data points that can be inserted in the empty space created by null values.</span></span>  
  
 <span data-ttu-id="a0cc2-105">Por padrão, pontos vazios são calculados pela média dos pontos de dados anteriores e seguintes que contêm um valor.</span><span class="sxs-lookup"><span data-stu-id="a0cc2-105">By default, empty points are calculated by taking the average of the previous and next data points that contain a value.</span></span> <span data-ttu-id="a0cc2-106">Você pode alterar isso para que todos os pontos vazios sejam inseridos como zero.</span><span class="sxs-lookup"><span data-stu-id="a0cc2-106">You can change this so that all empty points are inserted at zero.</span></span>  
  
 <span data-ttu-id="a0cc2-107">Para obter mais informações, consulte [Pontos de dados vazios e nulos em gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a0cc2-107">For more information, see [Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-empty-points-on-a-chart"></a><span data-ttu-id="a0cc2-108">Para especificar pontos vazios em um gráfico</span><span class="sxs-lookup"><span data-stu-id="a0cc2-108">To specify empty points on a chart</span></span>  
  
1.  <span data-ttu-id="a0cc2-109">Abra o painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="a0cc2-109">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="a0cc2-110">Na superfície de design, clique com o botão direito do mouse na série que contém valores nulos.</span><span class="sxs-lookup"><span data-stu-id="a0cc2-110">On the design surface, right-click the series that contains null values.</span></span> <span data-ttu-id="a0cc2-111">As propriedades da série são exibidas no painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="a0cc2-111">The properties for the series are displayed in the Properties pane.</span></span>  
  
3.  <span data-ttu-id="a0cc2-112">Expanda o nó **EmptyPoint** .</span><span class="sxs-lookup"><span data-stu-id="a0cc2-112">Expand the **EmptyPoint** node.</span></span>  
  
4.  <span data-ttu-id="a0cc2-113">Selecione um valor de cor para a propriedade Color.</span><span class="sxs-lookup"><span data-stu-id="a0cc2-113">Select a color value for the Color property.</span></span>  
  
5.  <span data-ttu-id="a0cc2-114">No nó **EmptyPoint** , expanda o nó Marker.</span><span class="sxs-lookup"><span data-stu-id="a0cc2-114">In the **EmptyPoint** node, expand the Marker node.</span></span>  
  
6.  <span data-ttu-id="a0cc2-115">Selecione um tipo de marcador para a propriedade MarkerType.</span><span class="sxs-lookup"><span data-stu-id="a0cc2-115">Select a marker type for the MarkerType property.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a0cc2-116">Você deve selecionar um tipo de marcador para adicionar pontos vazios a um gráfico de barras, colunas ou de dispersão.</span><span class="sxs-lookup"><span data-stu-id="a0cc2-116">You must select a marker type to add empty points to a bar, column or scatter chart.</span></span> <span data-ttu-id="a0cc2-117">No entanto, para gráficos de área, linha e radar, a seleção de um tipo de marcador é opcional porque o gráfico preenche o espaço vazio ou a lacuna sem precisar da especificação de um marcador.</span><span class="sxs-lookup"><span data-stu-id="a0cc2-117">However, for area, line and radar charts, selecting a marker type is optional because the chart fills in the empty space or gap without requiring a marker to be specified.</span></span>  
  
7.  <span data-ttu-id="a0cc2-118">Defina o valor do ponto vazio.</span><span class="sxs-lookup"><span data-stu-id="a0cc2-118">Set the value of the empty point.</span></span>  
  
    1.  <span data-ttu-id="a0cc2-119">No painel Propriedades, expanda o nó **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="a0cc2-119">In the Properties pane, expand the **CustomAttributes** node.</span></span>  
  
    2.  <span data-ttu-id="a0cc2-120">Defina a propriedade EmptyPointValue.</span><span class="sxs-lookup"><span data-stu-id="a0cc2-120">Set the EmptyPointValue property.</span></span> <span data-ttu-id="a0cc2-121">Para inserir pontos vazios em uma média dos pontos de dados anteriores e seguintes, selecione **Média**.</span><span class="sxs-lookup"><span data-stu-id="a0cc2-121">To insert empty points at an average of the previous and next data points, select **Average**.</span></span> <span data-ttu-id="a0cc2-122">Para inserir pontos vazios em zero, selecione **Zero**.</span><span class="sxs-lookup"><span data-stu-id="a0cc2-122">To insert empty points at zero, select **Zero**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0cc2-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a0cc2-123">See Also</span></span>  
 <span data-ttu-id="a0cc2-124">[Adicionar filtros de conjunto de dados, de região de dados e de grupo &#40;Construtor de Relatórios e SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="a0cc2-124">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="a0cc2-125">[Tipos de gráficos &#40;Construtor de Relatórios e SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a0cc2-125">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a0cc2-126">[Adicionar quebras de escala a um gráfico &#40;Construtor de Relatórios e SSRS&#41;](add-scale-breaks-to-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a0cc2-126">[Add Scale Breaks to a Chart &#40;Report Builder and SSRS&#41;](add-scale-breaks-to-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="a0cc2-127">Gráficos &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a0cc2-127">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
