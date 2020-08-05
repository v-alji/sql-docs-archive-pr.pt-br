---
title: Gráficos de ações (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f75ca11e-b7f5-4ac0-ba17-fe6f82742dad
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a0f8c9c7dbc750bdb477f2ea1d96aa03f7ad022f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569064"
---
# <a name="stock-charts-report-builder-and-ssrs"></a><span data-ttu-id="5c467-102">Gráficos de ações (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="5c467-102">Stock Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="5c467-103">Um gráfico de estoque é especificamente projetado para dados financeiros ou científicos que usam até quatro valores por ponto de dados.</span><span class="sxs-lookup"><span data-stu-id="5c467-103">A stock chart is specifically designed for financial or scientific data that uses up to four values per data point.</span></span> <span data-ttu-id="5c467-104">Esses valores se alinham com os valores alto, baixo, aberto e fechado usados para plotar dados de estoque financeiro.</span><span class="sxs-lookup"><span data-stu-id="5c467-104">These values align with the high, low, open and close values that are used to plot financial stock data.</span></span> <span data-ttu-id="5c467-105">Esse tipo de gráfico exibe valores de abertura e fechamento usando marcadores, que geralmente são linhas ou triângulos.</span><span class="sxs-lookup"><span data-stu-id="5c467-105">This chart type displays opening and closing values by using markers, which are typically lines or triangles.</span></span> <span data-ttu-id="5c467-106">No exemplo a seguir, os valores de abertura são mostrados pelos marcados à esquerda e os valores de fechamento são mostrados pelos marcadores à direita.</span><span class="sxs-lookup"><span data-stu-id="5c467-106">In the following example, the opening values are shown by the markers on the left, and the closing values are shown by the markers on the right.</span></span>  
  
 <span data-ttu-id="5c467-107">![Gráfico de ações](../media/rs-stockchart.gif "Gráfico de ações")</span><span class="sxs-lookup"><span data-stu-id="5c467-107">![Stock chart](../media/rs-stockchart.gif "Stock chart")</span></span>  
  
 <span data-ttu-id="5c467-108">Um exemplo de um gráfico de ações está disponível como um relatório de exemplo do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] Report Builder.</span><span class="sxs-lookup"><span data-stu-id="5c467-108">An example of a stock chart is available as a sample [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] Report Builder report.</span></span> <span data-ttu-id="5c467-109">Para obter mais informações sobre como baixar este relatório de exemplo e outros, consulte [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] [Construtor de Relatórios e Report Designer relatórios de exemplo](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="5c467-109">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="5c467-110">Variações</span><span class="sxs-lookup"><span data-stu-id="5c467-110">Variations</span></span>  
  
-   <span data-ttu-id="5c467-111">**Velas**.</span><span class="sxs-lookup"><span data-stu-id="5c467-111">**Candlestick**.</span></span> <span data-ttu-id="5c467-112">O gráfico de velas é uma forma especializada do gráfico de estoque, na qual as caixas são usadas para mostrar a faixa entre os valores de abertura e fechamento.</span><span class="sxs-lookup"><span data-stu-id="5c467-112">The candlestick chart is a specialized form of the stock chart, wherein boxes are used to show the range between the open and close values.</span></span> <span data-ttu-id="5c467-113">Da mesma forma que o gráfico de estoque, o gráfico de velas pode exibir até quatro valores por ponto de dados.</span><span class="sxs-lookup"><span data-stu-id="5c467-113">Like the stock chart, the candlestick chart can display up to four values per data point.</span></span>  
  
## <a name="data-considerations-for-stock-charts"></a><span data-ttu-id="5c467-114">Considerações de dados para gráficos de estoque</span><span class="sxs-lookup"><span data-stu-id="5c467-114">Data Considerations for Stock Charts</span></span>  
  
-   <span data-ttu-id="5c467-115">Ao apresentar muitos pontos de dados de estoque, como tendências de preço de estoque anual, é difícil distinguir entre os valores aberto, fechado, alto e baixo de cada ponto de dados.</span><span class="sxs-lookup"><span data-stu-id="5c467-115">When presenting many stock data points, such as annual stock price trend, it is difficult to distinguish each open, close, high and low value of each data point.</span></span> <span data-ttu-id="5c467-116">Nesse cenário, considere usar um gráfico de linhas em vez de um gráfico de estoque.</span><span class="sxs-lookup"><span data-stu-id="5c467-116">In this scenario, consider using a line chart instead of a stock chart.</span></span>  
  
-   <span data-ttu-id="5c467-117">Quando os rótulos de eixos são gerados, a rotulação geralmente começa em zero.</span><span class="sxs-lookup"><span data-stu-id="5c467-117">When axis labels are generated, labeling usually begins at zero.</span></span>  <span data-ttu-id="5c467-118">Em geral, os preços de estoque não flutuam no mesmo grau que os outros conjuntos de dados.</span><span class="sxs-lookup"><span data-stu-id="5c467-118">In general, stock prices do not fluctuate to the same degree as other data sets.</span></span> <span data-ttu-id="5c467-119">Por esse motivo, talvez você queira desativar os rótulos de eixos de iniciar em zero para obter uma melhor exibição de seus dados.</span><span class="sxs-lookup"><span data-stu-id="5c467-119">For this reason, you may want to disable the axis labels from starting at zero, in order to get a better view of your data.</span></span> <span data-ttu-id="5c467-120">Para fazer isso, defina **IncludeZero** como **false** na caixa de diálogo **Propriedades do Eixo** ou na janela Propriedades.</span><span class="sxs-lookup"><span data-stu-id="5c467-120">To do this, set **IncludeZero** to **false** in the **Axis Properties** dialog box or the Properties window.</span></span> <span data-ttu-id="5c467-121">Para obter mais informações sobre como o gráfico gera rótulos de eixo, consulte [Formatação de rótulos de eixo de um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5c467-121">For more information about how the chart generates axis labels, see [Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="5c467-122">fornece muitas fórmulas calculadas para uso com gráficos de estoque, inclusive Indicador de Preços, Índice de Força Relativa, MACD e outros.</span><span class="sxs-lookup"><span data-stu-id="5c467-122">provides many calculated formulas for use with stock charts, including Price Indicator, Relative Strength Index, MACD and more.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c467-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5c467-123">See Also</span></span>  
 <span data-ttu-id="5c467-124">[Gráficos de intervalo &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5c467-124">[Range Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5c467-125">[Gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5c467-125">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5c467-126">[Formatando um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5c467-126">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="5c467-127">Caixa de diálogo Propriedades do Eixo, Opções do Eixo &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5c467-127">Axis Properties Dialog Box, Axis Options &#40;Report Builder and SSRS&#41;</span></span>](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md)  
  
  
