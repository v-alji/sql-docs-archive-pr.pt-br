---
title: Alterar o texto de um item de legenda (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9e82fa34-17ed-494f-b25d-03dcc353a21f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0d0bb721aa0ff03a5211065111c98605cd86e971
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582312"
---
# <a name="change-the-text-of-a-legend-item-report-builder-and-ssrs"></a><span data-ttu-id="0a012-102">Alterar o texto de um item de legenda (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="0a012-102">Change the Text of a Legend Item (Report Builder and SSRS)</span></span>
  <span data-ttu-id="0a012-103">Quando um campo é colocado na área Valores do gráfico, um item de legenda é gerado automaticamente contendo o nome desse campo.</span><span class="sxs-lookup"><span data-stu-id="0a012-103">When a field is placed in the Values area of the chart, a legend item is automatically generated that contains the name of this field.</span></span> <span data-ttu-id="0a012-104">Cada item de legenda está conectado a uma série individual no gráfico, exceto para gráficos de forma, nos quais a legenda está conectada a pontos de dados individuais em vez de séries individuais.</span><span class="sxs-lookup"><span data-stu-id="0a012-104">Every legend item is connected to an individual series on the chart, with the exception of shape charts, where the legend is connected to individual data points instead of individual series.</span></span>  
  
 <span data-ttu-id="0a012-105">Em gráficos de forma, você pode alterar o texto de um item de legenda para mostrar mais informações sobre os pontos de dados individuais.</span><span class="sxs-lookup"><span data-stu-id="0a012-105">On shape charts, you can change the text of a legend item to show more information about the individual data points.</span></span> <span data-ttu-id="0a012-106">Por exemplo, para mostrar os valores dos pontos de dados como porcentagens na legenda, você pode usar uma palavra-chave, como `#PERCENT`.</span><span class="sxs-lookup"><span data-stu-id="0a012-106">For example, if you want to show the values of the data points as percentages in the legend, you can use a keyword such as `#PERCENT`.</span></span> <span data-ttu-id="0a012-107">É possível adicionar códigos de formato do .NET Framework em conjunto com palavras-chave para aplicar formatos numéricos e de data.</span><span class="sxs-lookup"><span data-stu-id="0a012-107">You can append .NET Framework format codes in conjunction with keywords to apply numeric and date formats.</span></span> <span data-ttu-id="0a012-108">Para obter mais informações sobre palavras-chave, consulte [Formatação de pontos de dados em um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0a012-108">For more information about keywords, see [Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="0a012-109">![Gráfico nítido](../media/sharpchart.png "Gráfico nítido")</span><span class="sxs-lookup"><span data-stu-id="0a012-109">![Sharp Chart](../media/sharpchart.png "Sharp Chart")</span></span>  
  
 <span data-ttu-id="0a012-110">Em gráficos de não forma, você pode alterar o texto de um item de legenda.</span><span class="sxs-lookup"><span data-stu-id="0a012-110">On non-shape charts, you can change the text of a legend item.</span></span> <span data-ttu-id="0a012-111">Por exemplo, se o nome da série for "Série1", você poderá desejar alterar o texto para algo mais descritivo, como "Vendas de 2008".</span><span class="sxs-lookup"><span data-stu-id="0a012-111">For example, if your series name is "Series1", you may want to change the text to something more descriptive like "Sales for 2008".</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-modify-the-text-that-appears-in-the-legend-on-a-shape-chart"></a><span data-ttu-id="0a012-112">Para modificar o texto que aparece na legenda em um gráfico de forma</span><span class="sxs-lookup"><span data-stu-id="0a012-112">To modify the text that appears in the legend on a Shape chart</span></span>  
  
1.  <span data-ttu-id="0a012-113">Clique com o botão direito do mouse em uma série ou em um campo na área **Valores** e selecione **Propriedades da Série**.</span><span class="sxs-lookup"><span data-stu-id="0a012-113">Right-click on a series, or right-click on a field in the **Values** area, and select **Series Properties**.</span></span>  
  
2.  <span data-ttu-id="0a012-114">Clique em **Legenda** e digite uma palavra-chave na caixa **Texto da legenda personalizada** .</span><span class="sxs-lookup"><span data-stu-id="0a012-114">Click **Legend** and in the **Custom legend text** box, type a keyword.</span></span>  
  
 <span data-ttu-id="0a012-115">A tabela a seguir fornece exemplos de palavras-chave específicas de gráfico para usar para a propriedade **Texto da Legenda Personalizada** .</span><span class="sxs-lookup"><span data-stu-id="0a012-115">The following table provides examples of chart-specific keywords to use for the **Custom Legend Text** property.</span></span> <span data-ttu-id="0a012-116">Para obter mais informações sobre palavras-chave, consulte [Formatação de pontos de dados em um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0a012-116">For more information about keywords, see [Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
|<span data-ttu-id="0a012-117">Palavra-chave</span><span class="sxs-lookup"><span data-stu-id="0a012-117">Keyword</span></span>|<span data-ttu-id="0a012-118">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="0a012-118">Description</span></span>|<span data-ttu-id="0a012-119">Exemplo do que é exibido como texto na legenda</span><span class="sxs-lookup"><span data-stu-id="0a012-119">Example of what appears as text in the legend</span></span>|  
|-------------|-----------------|---------------------------------------------------|  
|`#PERCENT{P1}`|<span data-ttu-id="0a012-120">Exibe a porcentagem do valor total para uma casa decimal.</span><span class="sxs-lookup"><span data-stu-id="0a012-120">Displays the percentage of the total value to one decimal place.</span></span>|<span data-ttu-id="0a012-121">85.0%</span><span class="sxs-lookup"><span data-stu-id="0a012-121">85.0%</span></span>|  
|`#VALY`|<span data-ttu-id="0a012-122">Exibe o valor numérico real do campo de dados.</span><span class="sxs-lookup"><span data-stu-id="0a012-122">Displays the actual numeric value of the data field.</span></span>|<span data-ttu-id="0a012-123">17000</span><span class="sxs-lookup"><span data-stu-id="0a012-123">17000</span></span>|  
|`#VALY{C2}`|<span data-ttu-id="0a012-124">Exibe o valor numérico real do campo de dados como uma moeda para duas casas decimais.</span><span class="sxs-lookup"><span data-stu-id="0a012-124">Displays the actual numeric value of the data field as a currency to two decimal places.</span></span>|<span data-ttu-id="0a012-125">$17000.00</span><span class="sxs-lookup"><span data-stu-id="0a012-125">$17000.00</span></span>|  
|`#AXISLABEL (#PERCENT{P0})`|<span data-ttu-id="0a012-126">Exibe a representação de texto do campo de categoria, seguida pela porcentagem que cada categoria exibe no gráfico.</span><span class="sxs-lookup"><span data-stu-id="0a012-126">Displays the text representation of the category field, followed by the percentage that each category displays on the chart.</span></span>|<span data-ttu-id="0a012-127">Michael Blythe (85%)</span><span class="sxs-lookup"><span data-stu-id="0a012-127">Michael Blythe (85%)</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="0a012-128">A palavra-chave #AXISLABEL pode ser avaliada em tempo de execução quando não há um campo especificado na área **Grupos de Séries** .</span><span class="sxs-lookup"><span data-stu-id="0a012-128">The #AXISLABEL keyword can only be evaluated at run time when there is not a field specified in the **Series Groups** area.</span></span>  
  
### <a name="to-modify-the-text-that-appears-in-the-legend-on-a-non-shape-chart"></a><span data-ttu-id="0a012-129">Para modificar o texto que aparece na legenda em um gráfico de não forma</span><span class="sxs-lookup"><span data-stu-id="0a012-129">To modify the text that appears in the legend on a non-Shape chart</span></span>  
  
1.  <span data-ttu-id="0a012-130">Clique com o botão direito do mouse em uma série ou em um campo na área **Valores** e selecione **Propriedades da Série**.</span><span class="sxs-lookup"><span data-stu-id="0a012-130">Right-click on a series, or right-click on a field in the **Values** area, and select **Series Properties**.</span></span>  
  
2.  <span data-ttu-id="0a012-131">Clique em **Legenda** e, na caixa **Texto da legenda personalizada** , digite um rótulo para a legenda.</span><span class="sxs-lookup"><span data-stu-id="0a012-131">Click **Legend** and in the **Custom legend text** box, type a legend label.</span></span> <span data-ttu-id="0a012-132">A série é atualizada com o texto.</span><span class="sxs-lookup"><span data-stu-id="0a012-132">The series is updated with your text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a012-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0a012-133">See Also</span></span>  
 <span data-ttu-id="0a012-134">[Formatando a legenda em um gráfico &#40;Construtor de Relatórios e SSRS&#41;](chart-legend-formatting-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="0a012-134">[Formatting the Legend on a Chart &#40;Report Builder and SSRS&#41;](chart-legend-formatting-report-builder.md) </span></span>  
 <span data-ttu-id="0a012-135">[Formatando as cores da série em um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0a012-135">[Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="0a012-136">Ocultar itens de legenda no gráfico &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0a012-136">Hide Legend Items on the Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-legend-hide-items-report-builder.md)  
  
  
