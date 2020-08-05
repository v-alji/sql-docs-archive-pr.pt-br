---
title: Adicionar um gráfico a um relatório (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a6b595dc-f775-4a53-8554-74a0bf9335ec
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 789dd6cce10b0425833ea63f2f7941ea75970a25
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569108"
---
# <a name="add-a-chart-to-a-report-report-builder-and-ssrs"></a><span data-ttu-id="cf5bb-102">Adicionar um gráfico a um relatório (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="cf5bb-102">Add a Chart to a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="cf5bb-103">Para resumir dados em um formato visual, use uma região de dados do gráfico.</span><span class="sxs-lookup"><span data-stu-id="cf5bb-103">When you want to summarize data in a visual format, use a Chart data region.</span></span> <span data-ttu-id="cf5bb-104">É importante escolher um tipo de gráfico apropriado para o tipo de dados que você está apresentando.</span><span class="sxs-lookup"><span data-stu-id="cf5bb-104">It is important to choose an appropriate chart type for the type of data that you are presenting.</span></span> <span data-ttu-id="cf5bb-105">Isso influencia a interpretação dos dados quando colocados em formato de gráfico.</span><span class="sxs-lookup"><span data-stu-id="cf5bb-105">This affects how well the data can be interpreted when put in chart form.</span></span> <span data-ttu-id="cf5bb-106">Para obter mais informações, consulte [Gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="cf5bb-106">For more information, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="cf5bb-107">A maneira mais simples de adicionar uma região de dados de gráfico a seu relatório é executar o Assistente de Novo Gráfico.</span><span class="sxs-lookup"><span data-stu-id="cf5bb-107">The simplest way to add a Chart data region to your report is to run the New Chart Wizard.</span></span> <span data-ttu-id="cf5bb-108">O assistente oferece gráficos de colunas, linhas, pizza, barras e área.</span><span class="sxs-lookup"><span data-stu-id="cf5bb-108">The wizard offers column, line, pie, bar, and area charts.</span></span> <span data-ttu-id="cf5bb-109">Para esses e outros tipos de gráfico, você pode adicionar um gráfico manualmente.</span><span class="sxs-lookup"><span data-stu-id="cf5bb-109">For these and other chart types, you can also add a chart manually.</span></span>  
  
 <span data-ttu-id="cf5bb-110">Depois de adicionar uma região de dados do gráfico à superfície de design, você pode arrastar campos do conjunto de dados do relatório de dados numéricos e não numéricos para o painel do gráfico Dados do Gráfico.</span><span class="sxs-lookup"><span data-stu-id="cf5bb-110">After you add a Chart data region to the design surface, you can drag report dataset fields for numeric and non-numeric data to the Chart Data pane of the chart.</span></span> <span data-ttu-id="cf5bb-111">Clique no gráfico para exibir o painel Dados do Gráfico com suas três áreas: Grupos de Séries, Grupos de Categorias e Valores.</span><span class="sxs-lookup"><span data-stu-id="cf5bb-111">Click the chart to display the Chart Data pane with its three areas: Series Groups, Category Groups, and Values.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-chart-to-a-report-by-using-the-chart-wizard"></a><span data-ttu-id="cf5bb-112">Para adicionar um gráfico a um relatório usando o Assistente de Gráfico</span><span class="sxs-lookup"><span data-stu-id="cf5bb-112">To add a chart to a report by using the Chart Wizard</span></span>  
  
1.  > [!NOTE]  
    >  <span data-ttu-id="cf5bb-113">O Assistente de Gráfico só está disponível no Construtor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="cf5bb-113">The Chart Wizard is only available in Report Builder.</span></span>  
  
     <span data-ttu-id="cf5bb-114">Na guia **Inserir** , clique em **Gráfico**e em **Assistente de Gráfico**.</span><span class="sxs-lookup"><span data-stu-id="cf5bb-114">On the **Insert** tab, click **Chart**, and then click **Chart Wizard**.</span></span>  
  
2.  <span data-ttu-id="cf5bb-115">Siga as etapas no Assistente de **Novo** Gráfico.</span><span class="sxs-lookup"><span data-stu-id="cf5bb-115">Follow the steps in the **New** Chart wizard.</span></span>  
  
3.  <span data-ttu-id="cf5bb-116">Na guia **Página Inicial** , clique em **Executar** para visualizar o relatório renderizado.</span><span class="sxs-lookup"><span data-stu-id="cf5bb-116">On the **Home** tab, click **Run** to see the rendered report.</span></span>  
  
4.  <span data-ttu-id="cf5bb-117">Na guia **Executar** , clique em **Design** para continuar trabalhando no relatório.</span><span class="sxs-lookup"><span data-stu-id="cf5bb-117">On the **Run** tab, click **Design** to continue working on the report.</span></span>  
  
### <a name="to-add-a-chart-to-a-report"></a><span data-ttu-id="cf5bb-118">Para adicionar um gráfico a um relatório</span><span class="sxs-lookup"><span data-stu-id="cf5bb-118">To add a chart to a report</span></span>  
  
1.  <span data-ttu-id="cf5bb-119">Crie um relatório e defina um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="cf5bb-119">Create a report and define a dataset.</span></span> <span data-ttu-id="cf5bb-120">Para obter mais informações, consulte [Adicionar dados a um relatório &#40;Construtor de relatórios e SSRS&#41;](../report-data/report-datasets-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="cf5bb-120">For more information, see [Add Data to a Report &#40;Report Builder and SSRS&#41;](../report-data/report-datasets-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="cf5bb-121">Na guia **Inserir** , clique em **Gráfico**e em **Inserir Gráfico**.</span><span class="sxs-lookup"><span data-stu-id="cf5bb-121">On the **Insert** tab, click **Chart**, and then click **Insert Chart**.</span></span>  
  
3.  <span data-ttu-id="cf5bb-122">Clique na superfície de design em que você deseja o canto superior esquerdo do gráfico e arraste até o local do canto inferior direito do gráfico.</span><span class="sxs-lookup"><span data-stu-id="cf5bb-122">Click on the design surface where you want the upper-left corner of the chart, and then drag to where you want the lower-right corner of the chart.</span></span>  
  
     <span data-ttu-id="cf5bb-123">A caixa de diálogo **Selecionar Tipo de Gráfico** é exibida.</span><span class="sxs-lookup"><span data-stu-id="cf5bb-123">The **Select Chart Type** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="cf5bb-124">Selecione o tipo de gráfico que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="cf5bb-124">Select the type of chart you want to add.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="cf5bb-125">Clique no gráfico para exibir o painel **Dados do Gráfico** .</span><span class="sxs-lookup"><span data-stu-id="cf5bb-125">Click the chart to display the **Chart Data** pane.</span></span>  
  
6.  <span data-ttu-id="cf5bb-126">Adicione um ou mais campos à área **Valores** .</span><span class="sxs-lookup"><span data-stu-id="cf5bb-126">Add one or more fields to the **Values** area.</span></span> <span data-ttu-id="cf5bb-127">Essas informações serão plotadas no eixo de valor.</span><span class="sxs-lookup"><span data-stu-id="cf5bb-127">This information will be plotted on the value axis.</span></span>  
  
7.  <span data-ttu-id="cf5bb-128">Adicione um campo de agrupamento à área **Grupos de Categorias** .</span><span class="sxs-lookup"><span data-stu-id="cf5bb-128">Add a grouping field to the **Category Groups** area.</span></span> <span data-ttu-id="cf5bb-129">Quando você adiciona esse campo à área **Grupos de Categorias** , um campo de agrupamento é criado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="cf5bb-129">When you add this field to the **Category Groups** area, a grouping field is automatically created for you.</span></span> <span data-ttu-id="cf5bb-130">Cada grupo representa um ponto de dados da série.</span><span class="sxs-lookup"><span data-stu-id="cf5bb-130">Each group represents a data point in your series.</span></span>  
  
8.  <span data-ttu-id="cf5bb-131">Para resumir os dados por categoria, clique com o botão direito do mouse no campo de dados e clique em **Propriedades da Série**.</span><span class="sxs-lookup"><span data-stu-id="cf5bb-131">To summarize the data by category, right-click the data field and click **Series Properties**.</span></span> <span data-ttu-id="cf5bb-132">Na caixa **Categoria** , selecione o campo de categoria na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="cf5bb-132">In the **Category** box, select the category field from the drop-down list.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
9. <span data-ttu-id="cf5bb-133">Na guia **Página Inicial** , clique em **Executar** para visualizar o relatório renderizado.</span><span class="sxs-lookup"><span data-stu-id="cf5bb-133">On the **Home** tab, click **Run** to see the rendered report.</span></span>  
  
10. <span data-ttu-id="cf5bb-134">Na guia **Executar** , clique em **Design** para continuar trabalhando no relatório.</span><span class="sxs-lookup"><span data-stu-id="cf5bb-134">On the **Run** tab, click **Design** to continue working on the report.</span></span>  
  
 <span data-ttu-id="cf5bb-135">Em gráficos com eixos, como gráficos de barras e de colunas, o eixo de categoria pode não exibir todos os rótulos de categoria.</span><span class="sxs-lookup"><span data-stu-id="cf5bb-135">On charts with axes, such as bar and column charts, the category axis may not display all the category labels.</span></span> <span data-ttu-id="cf5bb-136">Para obter mais informações sobre como alterar os rótulos do eixo, consulte [Especificar um intervalo do eixo &#40;Construtor de Relatórios e SSRS&#41;](specify-an-axis-interval-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="cf5bb-136">For more information about how to change the axis labels, see [Specify an Axis Interval &#40;Report Builder and SSRS&#41;](specify-an-axis-interval-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf5bb-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cf5bb-137">See Also</span></span>  
 <span data-ttu-id="cf5bb-138">[Gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="cf5bb-138">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="cf5bb-139">[Tipos de gráficos &#40;Construtor de Relatórios e SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="cf5bb-139">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="cf5bb-140">[Pontos de dados vazios e nulos em gráficos &#40;Construtor de Relatórios e SSRS&#41;](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="cf5bb-140">[Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="cf5bb-141">[Tutorial: Adicionando um gráfico de barras ao relatório (Construtor de Relatórios)](https://go.microsoft.com/fwlink/?LinkId=198052) </span><span class="sxs-lookup"><span data-stu-id="cf5bb-141">[Tutorial: Adding a Bar Chart to Your Report (Report Builder)](https://go.microsoft.com/fwlink/?LinkId=198052) </span></span>  
 <span data-ttu-id="cf5bb-142">[Tutorial: Adicionando um gráfico de barras a um relatório (Designer de Relatórios)](https://go.microsoft.com/fwlink/?LinkId=198042) </span><span class="sxs-lookup"><span data-stu-id="cf5bb-142">[Tutorial: Adding a Bar Chart to a Report (Report Designer)](https://go.microsoft.com/fwlink/?LinkId=198042) </span></span>  
 <span data-ttu-id="cf5bb-143">[Tutorial: Adicionando um gráfico de pizza ao relatório (Construtor de Relatórios)](https://go.microsoft.com/fwlink/?LinkId=198051) </span><span class="sxs-lookup"><span data-stu-id="cf5bb-143">[Tutorial: Adding a Pie Chart to Your Report (Report Builder)](https://go.microsoft.com/fwlink/?LinkId=198051) </span></span>  
 [<span data-ttu-id="cf5bb-144">Tutorial: Adicionando um gráfico de pizza ao relatório (Designer de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="cf5bb-144">Tutorial: Adding a Pie Chart to a Report (Report Designer)</span></span>](https://go.microsoft.com/fwlink/?LinkId=198041)  
  
  
