---
title: Especificar cores consistentes em vários gráficos de forma (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d52f68e9-2ba7-4bff-9053-4089e5164ab4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c2c89f0f8cda3b7d6ef6b2acbd0de66c87170357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569071"
---
# <a name="specify-consistent-colors-across-multiple-shape-charts-report-builder-and-ssrs"></a><span data-ttu-id="423ca-102">Especificar cores consistentes em gráficos com várias formas (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="423ca-102">Specify Consistent Colors across Multiple Shape Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="423ca-103">Em gráficos não forma, uma cor nova é selecionada na paleta com base no índice da série no gráfico.</span><span class="sxs-lookup"><span data-stu-id="423ca-103">On non-shape charts, a new color is selected from the palette based on the index of series in the chart.</span></span> <span data-ttu-id="423ca-104">Por exemplo, a primeira série do gráfico é mapeada para a primeira cor da paleta.</span><span class="sxs-lookup"><span data-stu-id="423ca-104">For example, the first series on your chart will be mapped to the first color in the palette.</span></span> <span data-ttu-id="423ca-105">No entanto, esse comportamento é diferente em gráficos com forma.</span><span class="sxs-lookup"><span data-stu-id="423ca-105">However, this behavior differs for shape charts.</span></span> <span data-ttu-id="423ca-106">Em gráficos com forma, todas as cores da paleta são mapeadas para um ponto de dados no conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="423ca-106">On shape charts, each color in the palette is mapped to a data point in the dataset.</span></span> <span data-ttu-id="423ca-107">Por exemplo, o ponto de dados 1 é mapeado para a primeira cor da paleta, o ponto de dados 2 é mapeado para a segunda paleta de cores e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="423ca-107">For example, data point 1 is mapped to the first color in the palette, data point 2 is mapped to the second color palette and so on.</span></span>  
  
 <span data-ttu-id="423ca-108">Caso não tenha nenhum valor, um ponto de dados é omitido na exibição de um gráfico com forma.</span><span class="sxs-lookup"><span data-stu-id="423ca-108">If a data point has no value, it is omitted from display on a shape chart.</span></span> <span data-ttu-id="423ca-109">Isso significa que o ponto de dados deixa de ser colorido.</span><span class="sxs-lookup"><span data-stu-id="423ca-109">This means that the data point is skipped from being colored.</span></span> <span data-ttu-id="423ca-110">Por exemplo, se o ponto de dados 2 tiver um valor igual a zero, o ponto de dados 1 será mapeado para a primeira cor da paleta e o ponto 3, para a segunda cor da paleta.</span><span class="sxs-lookup"><span data-stu-id="423ca-110">For example, if point 2 has a value of zero, point 1 will be mapped to the first color in the palette, and point 3 will be mapped to the second color in the palette.</span></span> <span data-ttu-id="423ca-111">Essa abordagem é útil porque os pontos vazios no conjunto de dados de um gráfico de pizza não necessariamente usam uma cor da paleta quando o ponto vazio não precisa ser desenhado.</span><span class="sxs-lookup"><span data-stu-id="423ca-111">This approach is useful because the empty points in the dataset of a pie chart do not unnecessarily use a palette color when the empty point does not need to be drawn.</span></span>  
  
 <span data-ttu-id="423ca-112">Como efeito colateral, quando vários gráficos de pizza são exibidos em um relatório, os gráficos de pizza podem exibir cores diferentes dos pontos de dados com o mesmo agrupamento da categoria.</span><span class="sxs-lookup"><span data-stu-id="423ca-112">As a side effect, when multiple pie charts are displayed in a report, the pie charts may display different colors for data points that have the same category grouping.</span></span> <span data-ttu-id="423ca-113">Para resolver isso, você precisa definir cores individuais mapeadas para um grupo de categorias, e não valores de dados individuais.</span><span class="sxs-lookup"><span data-stu-id="423ca-113">To resolve this, you need to define individual colors that map to a category group instead of individual data values.</span></span> <span data-ttu-id="423ca-114">A maneira como você faz isto vai depender se os gráficos de formas são minigráficos em uma tabela ou matriz, ou se eles são gráficos de formas no próprio relatório.</span><span class="sxs-lookup"><span data-stu-id="423ca-114">How you do this depends on if the shape charts are sparklines in a table or matrix, or if they are shape charts in the report itself.</span></span>  
  
 <span data-ttu-id="423ca-115">Como a legenda é conectada à série, todas as cores especificadas para a série serão mostradas automaticamente na legenda.</span><span class="sxs-lookup"><span data-stu-id="423ca-115">The legend is connected to the series, so any color you specify for the series will automatically be shown on the legend.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-consistent-colors-across-multiple-sparkline-shape-charts-in-a-table-or-matrix"></a><span data-ttu-id="423ca-116">Para especificar cores consistentes em minigráficos de várias formas em uma tabela ou matriz</span><span class="sxs-lookup"><span data-stu-id="423ca-116">To specify consistent colors across multiple sparkline shape charts in a table or matrix</span></span>  
  
1.  <span data-ttu-id="423ca-117">Clique no gráfico para exibir o painel Dados do Gráfico.</span><span class="sxs-lookup"><span data-stu-id="423ca-117">Click the chart to display the Chart Data pane.</span></span>  
  
2.  <span data-ttu-id="423ca-118">Na área **Grupos de Categorias** , clique com o botão direito do mouse em uma categoria e clique em **Propriedades de Grupos de Categorias**.</span><span class="sxs-lookup"><span data-stu-id="423ca-118">In the **Category Groups** area, right-click a category and click **Category Group Properties**.</span></span>  
  
3.  <span data-ttu-id="423ca-119">Na guia Geral, na caixa **Sincronizar grupos em** , clique no nome da categoria para a qual você gostaria de sincronizar cores e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="423ca-119">On the General tab, in the **Synchronize groups in** box, click the name of the category for which you would like to synchronize colors, and then click **OK**.</span></span>  
  
### <a name="to-specify-consistent-colors-across-multiple-shape-charts"></a><span data-ttu-id="423ca-120">Para especificar cores consistentes em vários gráficos com forma</span><span class="sxs-lookup"><span data-stu-id="423ca-120">To specify consistent colors across multiple shape charts</span></span>  
  
1.  <span data-ttu-id="423ca-121">Clique com o botão direito do mouse fora do corpo do relatório e selecione **Propriedades do Relatório**.</span><span class="sxs-lookup"><span data-stu-id="423ca-121">Right-click outside the body of the report, and select **Report Properties**.</span></span>  
  
2.  <span data-ttu-id="423ca-122">Em **Código**, digite o seguinte código na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="423ca-122">In **Code**, type the following code into the textbox.</span></span>  
  
    ```  
    Private colorPalette As String() = {"Color1", "Color2", "Color3"}  
    Private count As Integer = 0  
    Private mapping As New System.Collections.Hashtable()  
    Public Function GetColor(ByVal groupingValue As String) As String  
        If mapping.ContainsKey(groupingValue) Then  
            Return mapping(groupingValue)  
        End If  
        Dim c As String = colorPalette(count Mod colorPalette.Length)  
        count = count + 1  
        mapping.Add(groupingValue, c)  
        Return c  
    End Function  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="423ca-123">Você precisará substituir as cadeias de caracteres "Color1" por cores próprias.</span><span class="sxs-lookup"><span data-stu-id="423ca-123">You will need to replace the "Color1" strings with your own colors.</span></span> <span data-ttu-id="423ca-124">É possível usar cores nomeadas, por exemplo "Vermelho" ou usar valor hexadecimal de seis dígitos que representam a cor como "#FFFFFF" para preto.</span><span class="sxs-lookup"><span data-stu-id="423ca-124">You can use named colors, for example "Red", or you can use six-digit hexadecimal value that represent the color, such as "#FFFFFF" for black.</span></span> <span data-ttu-id="423ca-125">Se tiver mais de três cores definidas, você precisará estender a matriz de cores para que o número de cores na matriz corresponda ao número de pontos do gráfico com forma.</span><span class="sxs-lookup"><span data-stu-id="423ca-125">If you have more than three colors defined, you will need to extend the array of colors so that the number of colors in the array matches the number of points in your shape chart.</span></span> <span data-ttu-id="423ca-126">É possível adicionar novas cores à matriz especificando uma lista separada por vírgulas dos valores da cadeia de caracteres que contêm cores nomeadas ou representações hexadecimais das cores.</span><span class="sxs-lookup"><span data-stu-id="423ca-126">You can add new colors to the array by specifying a comma-separated list of string values that contain named colors or hexadecimal representations of colors.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
4.  <span data-ttu-id="423ca-127">Clique com o botão direito do mouse no gráfico com forma e selecione **Propriedades da Série**.</span><span class="sxs-lookup"><span data-stu-id="423ca-127">Right-click on the shape chart and select **Series Properties**.</span></span>  
  
5.  <span data-ttu-id="423ca-128">Em **Preenchimento**, clique no botão **Expressão** (*fx*) para editar a expressão de acordo com a propriedade **Cor** .</span><span class="sxs-lookup"><span data-stu-id="423ca-128">In **Fill**, click the **Expression** (*fx*) button to edit the expression for the **Color** property.</span></span>  
  
6.  <span data-ttu-id="423ca-129">Digite a seguinte expressão em que "MyCategoryField" é o campo exibido na área **Grupos de Categorias** :</span><span class="sxs-lookup"><span data-stu-id="423ca-129">Type the following expression, where "MyCategoryField" is the field that is displayed in the **Category Groups** area:</span></span>  
  
    ```  
    =Code.GetColor(Fields!MyCategoryField)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="423ca-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="423ca-130">See Also</span></span>  
 <span data-ttu-id="423ca-131">[Formatando as cores da série em um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="423ca-131">[Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="423ca-132">[Adicionar estilos de bisel, alto-relevo e textura a um gráfico &#40;Construtor de Relatórios e SSRS&#41;](chart-effects-add-bevel-emboss-or-texture-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="423ca-132">[Add Bevel, Emboss, and Texture Styles to a Chart &#40;Report Builder and SSRS&#41;](chart-effects-add-bevel-emboss-or-texture-report-builder.md) </span></span>  
 <span data-ttu-id="423ca-133">[Definir cores em um gráfico usando uma paleta &#40;Construtor de Relatórios e SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="423ca-133">[Define Colors on a Chart Using a Palette &#40;Report Builder and SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="423ca-134">[Adicionar pontos vazios ao gráfico &#40;Construtor de Relatórios e SSRS&#41;](add-empty-points-to-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="423ca-134">[Add Empty Points to the Chart &#40;Report Builder and SSRS&#41;](add-empty-points-to-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="423ca-135">[Gráficos de forma &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="423ca-135">[Shape Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="423ca-136">[Vinculando várias regiões de dados ao mesmo conjunto de dados &#40;Construtor de Relatórios e SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="423ca-136">[Linking Multiple Data Regions to the Same Dataset &#40;Report Builder and SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="423ca-137">[Regiões de dados aninhadas &#40;Construtor de Relatórios e SSRS&#41;](nested-data-regions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="423ca-137">[Nested Data Regions &#40;Report Builder and SSRS&#41;](nested-data-regions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="423ca-138">Minigráficos e barras de dados &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="423ca-138">Sparklines and Data Bars &#40;Report Builder and SSRS&#41;</span></span>](sparklines-and-data-bars-report-builder-and-ssrs.md)  
  
  
