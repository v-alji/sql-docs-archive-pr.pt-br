---
title: Realçar dados do gráfico adicionando faixas (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: addd6137-4b6e-4e88-a7e8-9600fcd1ccce
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 01b0bb41a71daf9ac558ce8d8bb84480426870c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570443"
---
# <a name="highlight-chart-data-by-adding-strip-lines-report-builder-and-ssrs"></a><span data-ttu-id="58768-102">Realçar dados do gráfico adicionando faixas (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="58768-102">Highlight Chart Data by Adding Strip Lines (Report Builder and SSRS)</span></span>
  <span data-ttu-id="58768-103">As faixas são intervalos horizontais ou verticais que sombreiam o plano de fundo do gráfico em intervalos regulares ou personalizados.</span><span class="sxs-lookup"><span data-stu-id="58768-103">Strip lines, or strips, are horizontal or vertical ranges that shade the background of the chart in regular or custom intervals.</span></span> <span data-ttu-id="58768-104">É possível usar faixas para:</span><span class="sxs-lookup"><span data-stu-id="58768-104">You can use strip lines to:</span></span>  
  
-   <span data-ttu-id="58768-105">Melhorar a legibilidade para pesquisar valores individuais no gráfico.</span><span class="sxs-lookup"><span data-stu-id="58768-105">Improve readability for looking up individual values on the chart.</span></span> <span data-ttu-id="58768-106">Especificar faixas em intervalos regulares para ajudar a separar pontos de dados ao ler o gráfico.</span><span class="sxs-lookup"><span data-stu-id="58768-106">Specify strip lines at regular intervals to help separate data points when reading the chart.</span></span>  
  
-   <span data-ttu-id="58768-107">Realçar datas que ocorrem em intervalos regulares.</span><span class="sxs-lookup"><span data-stu-id="58768-107">Highlight dates that occur at regular intervals.</span></span> <span data-ttu-id="58768-108">Por exemplo, em um relatório de vendas você pode usar faixas para identificar pontos de dados de fins de semana.</span><span class="sxs-lookup"><span data-stu-id="58768-108">For example, in a sales report you might use strip lines to identify weekend data points.</span></span>  
  
-   <span data-ttu-id="58768-109">Realçar um intervalo de chaves específico.</span><span class="sxs-lookup"><span data-stu-id="58768-109">Highlight a specific key range.</span></span> <span data-ttu-id="58768-110">Usando o exemplo anterior, é possível usar uma faixa para realçar o intervalo mais alto de vendas que esteja entre $80 e 100.</span><span class="sxs-lookup"><span data-stu-id="58768-110">Using the previous example, you can use one strip line to highlight the highest range of sales that is between $80-100.</span></span>  
  
 <span data-ttu-id="58768-111">As faixas não são aplicáveis aos tipos de gráficos de Formas ou Polares.</span><span class="sxs-lookup"><span data-stu-id="58768-111">Strip lines are not applicable to Shape or Polar chart types.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-display-interlaced-strip-lines-at-regular-intervals-on-a-chart"></a><span data-ttu-id="58768-112">Para exibir faixas entrelaçadas em intervalos regulares de um gráfico</span><span class="sxs-lookup"><span data-stu-id="58768-112">To display interlaced strip lines at regular intervals on a chart</span></span>  
  
1.  <span data-ttu-id="58768-113">Para mostrar faixas horizontais, clique com o botão direito do mouse em o eixo de gráfico vertical e clique em **Propriedades VerticalAxis**.</span><span class="sxs-lookup"><span data-stu-id="58768-113">To show horizontal strip lines, right-click the vertical chart axis and click **VerticalAxis Properties**.</span></span>  
  
     <span data-ttu-id="58768-114">Para mostrar faixas verticais, clique com o botão direito do mouse em o eixo de gráfico horizontal e clique em **Propriedades do Eixo Vertical**.</span><span class="sxs-lookup"><span data-stu-id="58768-114">To show vertical strip lines, right-click the horizontal chart axis and click **Horizontal Axis Properties**.</span></span>  
  
2.  <span data-ttu-id="58768-115">Selecione a opção **Usar entrelaçamento** .</span><span class="sxs-lookup"><span data-stu-id="58768-115">Select the **Use interlacing** option.</span></span> <span data-ttu-id="58768-116">Faixas cinza são exibidas no gráfico.</span><span class="sxs-lookup"><span data-stu-id="58768-116">Grey strip lines will appear on your chart.</span></span>  
  
3.  <span data-ttu-id="58768-117">(Opcional) Especifique uma cor para as faixas usando a lista suspensa **Cor** adjacente.</span><span class="sxs-lookup"><span data-stu-id="58768-117">(Optional) Specify a color for the strip lines using the adjacent **Color** drop-down list.</span></span>  
  
### <a name="to-display-interlaced-strip-lines-at-custom-intervals-on-a-chart"></a><span data-ttu-id="58768-118">Para exibir faixas entrelaçadas em intervalos personalizados em um gráfico</span><span class="sxs-lookup"><span data-stu-id="58768-118">To display interlaced strip lines at custom intervals on a chart</span></span>  
  
1.  <span data-ttu-id="58768-119">Para mostrar faixas horizontais, clique com o botão direito do mouse em o eixo de gráfico vertical e clique em **Propriedades VerticalAxis**.</span><span class="sxs-lookup"><span data-stu-id="58768-119">To show horizontal strip lines, right-click the vertical chart axis and click **VerticalAxis Properties**.</span></span>  
  
     <span data-ttu-id="58768-120">Para mostrar faixas verticais, clique com o botão direito do mouse em o eixo de gráfico horizontal e clique em **Propriedades do Eixo Vertical**.</span><span class="sxs-lookup"><span data-stu-id="58768-120">To show vertical strip lines, right-click the horizontal chart axis and click **Horizontal Axis Properties**.</span></span>  
  
     <span data-ttu-id="58768-121">As propriedades do eixo são exibidas na janela Propriedades.</span><span class="sxs-lookup"><span data-stu-id="58768-121">The axis properties are displayed in the Properties window.</span></span>  
  
2.  <span data-ttu-id="58768-122">Na seção **Aparência** do painel Propriedades da propriedade StripLines, clique no botão Editar Coleção (…) para abrir o **Editor de Coleções ChartStripLine**.</span><span class="sxs-lookup"><span data-stu-id="58768-122">In the **Appearance** section of the Properties pane, for the StripLines property, click the Edit Collection (...) button to open the **ChartStripLine Collection Editor**.</span></span>  
  
3.  <span data-ttu-id="58768-123">Clique em **Adicionar** para adicionar uma nova faixa à coleção.</span><span class="sxs-lookup"><span data-stu-id="58768-123">Click **Add** to add a new strip line to the collection.</span></span>  
  
4.  <span data-ttu-id="58768-124">Clique em StripWidth para especificar a largura da faixa, medida em polegadas no relatório.</span><span class="sxs-lookup"><span data-stu-id="58768-124">Click StripWidth to specify the width of the strip line, measured in inches on the report.</span></span> <span data-ttu-id="58768-125">Se você estiver realçando datas ou horas, clique em StripWidthType e selecione um intervalo de tempo.</span><span class="sxs-lookup"><span data-stu-id="58768-125">If you are highlighting dates or times, click StripWidthType and select a time interval.</span></span>  
  
5.  <span data-ttu-id="58768-126">Digite um valor ou expressão para o Intervalo para especificar a frequência com que a faixa se repete.</span><span class="sxs-lookup"><span data-stu-id="58768-126">Type a value or expression for the Interval to specify how often the strip line will repeat.</span></span>  <span data-ttu-id="58768-127">Por exemplo, se você especificar um intervalo de 10, e a largura da faixa for 5, as faixas serão exibidas em valores de 0 a 5, 15 a 20, 30 a 35 e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="58768-127">For example, if you specify an interval of 10, and your strip line width is 5, strip lines will display at values of 0 to 5, 15 to 20, 30 to 35, and so on.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="58768-128">Por padrão, o Intervalo é definido como Automático, o que significa que o gráfico não calcula um intervalo para faixas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="58768-128">By default, Interval is set to Auto, which means the chart will not calculate an interval for custom strip lines.</span></span> <span data-ttu-id="58768-129">O gráfico calculará intervalos para faixas apenas se o valor de um intervalo estiver definido.</span><span class="sxs-lookup"><span data-stu-id="58768-129">The chart only calculates intervals for strip lines if an interval value is set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58768-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="58768-130">See Also</span></span>  
 <span data-ttu-id="58768-131">[Formatando rótulos dos eixos de um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="58768-131">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="58768-132">[Formatando um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="58768-132">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="58768-133">Adicionar uma média móvel a um gráfico &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="58768-133">Add a Moving Average to a Chart &#40;Report Builder and SSRS&#41;</span></span>](add-a-moving-average-to-a-chart-report-builder-and-ssrs.md)  
  
  
