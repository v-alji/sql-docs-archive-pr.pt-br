---
title: 'Tutorial: Adicionar um gráfico de pizza ao relatório (Construtor de Relatórios) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eaadf7bf-c312-428a-b214-0a1fbf959c3f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 318370b185dcd75a8c3c54be49c47756bad5f3c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683357"
---
# <a name="tutorial-add-a-pie-chart-to-your-report-report-builder"></a><span data-ttu-id="e5f4c-102">Tutorial: Adicionar um gráfico de pizza ao relatório (Construtor de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="e5f4c-102">Tutorial: Add a Pie Chart to Your Report (Report Builder)</span></span>
  <span data-ttu-id="e5f4c-103">Gráficos de pizza e gráficos de rosca exibem dados como uma proporção do todo.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-103">Pie charts and doughnut charts display data as a proportion of the whole.</span></span> <span data-ttu-id="e5f4c-104">Os gráficos de pizza são os mais usados para fazer comparações entre grupos.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-104">Pie charts are most commonly used to make comparisons between groups.</span></span> <span data-ttu-id="e5f4c-105">Gráficos de pizza e de rosca, além dos gráficos de pirâmide e funil, constituem um grupo de gráficos conhecidos como gráficos de forma.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-105">Pie and doughnut charts, along with pyramid and funnel charts, constitute a group of charts known as shape charts.</span></span> <span data-ttu-id="e5f4c-106">Os gráficos de forma não têm nenhum eixo.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-106">Shape charts have no axes.</span></span> <span data-ttu-id="e5f4c-107">Quando um campo numérico é solto em um gráfico de forma, o gráfico calcula a porcentagem de cada valor com relação ao total.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-107">When a numeric field is dropped on a shape chart, the chart calculates the percentage of each value to the total.</span></span>  
  
 <span data-ttu-id="e5f4c-108">Se houver muitos pontos de dados em um gráfico de pizza, os rótulos dos pontos de dados podem ficar muito cheios para serem lidos.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-108">If there are too many data points on a pie chart, your data point labels might be too crowded to read.</span></span> <span data-ttu-id="e5f4c-109">Nesse caso, use um gráfico de linha.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-109">In that case, consider using a line chart.</span></span> <span data-ttu-id="e5f4c-110">Use gráficos de pizza somente depois de ter agregado seus dados em alguns pontos de dados.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-110">Consider using pie charts only after you have aggregated your data into a few data points.</span></span>  
  
 <span data-ttu-id="e5f4c-111">A ilustração a seguir mostra o gráfico de pizza que você criará.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-111">The following illustration shows the pie chart you will create.</span></span>  
  
 <span data-ttu-id="e5f4c-112">![rs_TutorialPieChartConcave](../../2014/tutorials/media/rs-tutorialpiechartconcave.gif "rs_TutorialPieChartConcave")</span><span class="sxs-lookup"><span data-stu-id="e5f4c-112">![rs_TutorialPieChartConcave](../../2014/tutorials/media/rs-tutorialpiechartconcave.gif "rs_TutorialPieChartConcave")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="e5f4c-113">O que você aprenderá</span><span class="sxs-lookup"><span data-stu-id="e5f4c-113">What You Will Learn</span></span>  
 <span data-ttu-id="e5f4c-114">Neste tutorial, você aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="e5f4c-114">In this tutorial, you will learn how to:</span></span>  
  
1.  [<span data-ttu-id="e5f4c-115">Criar um gráfico de pizza no Assistente de gráfico</span><span class="sxs-lookup"><span data-stu-id="e5f4c-115">Create a Pie Chart from the Chart Wizard</span></span>](#Chart)  
  
2.  [<span data-ttu-id="e5f4c-116">Escolher o tipo de gráfico</span><span class="sxs-lookup"><span data-stu-id="e5f4c-116">Choose the Chart Type</span></span>](#ChartType)  
  
3.  [<span data-ttu-id="e5f4c-117">Exibir as porcentagens em cada fatia do gráfico</span><span class="sxs-lookup"><span data-stu-id="e5f4c-117">Display Percentages in Each Slice</span></span>](#Percentages)  
  
4.  [<span data-ttu-id="e5f4c-118">Combinar pequenas fatias em uma fatia</span><span class="sxs-lookup"><span data-stu-id="e5f4c-118">Combine Small Slices into One Slice</span></span>](#CombineSlices)  
  
5.  [<span data-ttu-id="e5f4c-119">Personalizar o efeito de desenho</span><span class="sxs-lookup"><span data-stu-id="e5f4c-119">Customize the Drawing Effect</span></span>](#DrawingEffect)  
  
6.  [<span data-ttu-id="e5f4c-120">Adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="e5f4c-120">Add a Report Title</span></span>](#Title)  
  
7.  [<span data-ttu-id="e5f4c-121">Salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="e5f4c-121">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="e5f4c-122">Neste tutorial, as etapas do assistente são consolidadas em dois procedimentos.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-122">In this tutorial, the steps for the wizard are consolidated into two procedures.</span></span> <span data-ttu-id="e5f4c-123">Para obter instruções passo a passo sobre como procurar um servidor de relatório, adicionar uma fonte de dados e um conjunto de dados, consulte o primeiro tutorial desta série: [Tutorial: Criando um relatório de tabela básico &#40;Construtor de Relatórios&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="e5f4c-123">For step-by-step instructions about how to browse to a report server, add a data source, and add a dataset, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="e5f4c-124">Tempo estimado para concluir este tutorial: 10 minutos</span><span class="sxs-lookup"><span data-stu-id="e5f4c-124">Estimated time to complete this tutorial: 10 minutes</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5f4c-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e5f4c-125">Requirements</span></span>  
 <span data-ttu-id="e5f4c-126">Para obter mais informações sobre os requisitos, consulte [Pré-requisitos para tutoriais &#40;Construtor de Relatórios&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="e5f4c-126">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-pie-chart-from-the-chart-wizard"></a><a name="Chart"></a><span data-ttu-id="e5f4c-127">1. criar um gráfico de pizza no assistente de gráfico</span><span class="sxs-lookup"><span data-stu-id="e5f4c-127">1. Create a Pie Chart from the Chart Wizard</span></span>  
 <span data-ttu-id="e5f4c-128">Na caixa de diálogo Guia de Introdução, use o Assistente de Gráfico para criar um conjunto de dados inserido, escolha uma fonte de dados compartilhada e crie um gráfico de pizza.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-128">From the Getting Started dialog box, use the Chart Wizard to create an embedded dataset, choose a shared data source, and create a pie chart.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e5f4c-129">Neste tutorial, a consulta contém os valores de dados para que não precise de uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-129">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="e5f4c-130">Isso torna a consulta bastante longa.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-130">This makes the query quite long.</span></span> <span data-ttu-id="e5f4c-131">Em um ambiente empresarial, uma consulta não conteria os dados.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-131">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="e5f4c-132">Isso é apenas para fins de aprendizado.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-132">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-chart-report"></a><span data-ttu-id="e5f4c-133">Para criar um novo relatório de gráfico</span><span class="sxs-lookup"><span data-stu-id="e5f4c-133">To create a new chart report</span></span>  
  
1.  <span data-ttu-id="e5f4c-134">Clique em **Iniciar**, aponte para **Programas**, para **Construtor de Relatórios do Microsoft SQL Server 2012**e clique em **Construtor de Relatórios**.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-134">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="e5f4c-135">A caixa de diálogo Guia de Introdução é exibida.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-135">The Getting Started dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e5f4c-136"> Se a caixa de diálogo Guia de Introdução não for exibida, no botão Construtor de Relatórios, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-136">If the Getting Started dialog box does not appear, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="e5f4c-137">No painel esquerdo, verifique se **Novo Relatório** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-137">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="e5f4c-138">No painel direito, clique em **Assistente de Gráfico**.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-138">In the right pane, click **Chart Wizard**.</span></span>  
  
4.  <span data-ttu-id="e5f4c-139">Na página **Escolher um conjunto de dados** , clique em **Criar um conjunto de dados**e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-139">On the **Choose a dataset** page, click **Create a dataset**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="e5f4c-140">Na página **Escolher uma conexão com uma fonte de dados** , selecione uma fonte de dados existente ou procure o servidor de relatório, selecione uma fonte de dados e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-140">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source, and then click **Next**.</span></span> <span data-ttu-id="e5f4c-141">Talvez seja necessário inserir um nome de usuário e uma senha.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-141">You may need to enter a user name and password.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e5f4c-142">A fonte de dados escolhida não tem importância, contanto que você tenha permissões suficientes.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-142">The data source you choose is unimportant, as long as you have adequate permissions.</span></span> <span data-ttu-id="e5f4c-143">Você não obterá dados da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-143">You will not be getting data from the data source.</span></span> <span data-ttu-id="e5f4c-144">Para obter mais informações, consulte [Formas alternativas de obter uma conexão de dados &#40;Construtor de Relatórios&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="e5f4c-144">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
6.  <span data-ttu-id="e5f4c-145">Na página **criar uma consulta** , clique em **Editar como texto**.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-145">On the **Design a Query** page, click **Edit as Text**.</span></span>  
  
7.  <span data-ttu-id="e5f4c-146">Cole a seguinte consulta no painel de consulta:</span><span class="sxs-lookup"><span data-stu-id="e5f4c-146">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT 'Advanced Digital Camera' AS Product, CAST(254995.21 AS money) AS Sales  
    UNION SELECT 'Slim Digital Camera' AS Product, CAST(164499.04 AS money) AS Sales  
    UNION SELECT 'SLR Digital Camera' AS Product, CAST(782176.79 AS money) AS Sales  
    UNION SELECT 'Lens Adapter' AS Product, CAST(36333.08 AS money) AS Sales  
    UNION SELECT 'Macro Zoom Lens' AS Product, CAST(40199.3 AS money) AS Sales  
    UNION SELECT 'USB Cable' AS Product, CAST(53245.5 AS money) AS Sales  
    UNION SELECT 'Independent Filmmaker Camcorder' AS Product, CAST(452288.0 AS money) AS Sales  
    UNION SELECT 'Full Frame Digital Camera' AS Product, CAST(247250.85 AS money) AS Sales  
    ```  
  
8.  <span data-ttu-id="e5f4c-147">(Opcional) Clique no botão Executar (**!**) para ver os dados em que o gráfico se baseará.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-147">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>  
  
9. <span data-ttu-id="e5f4c-148">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-148">Click **Next**.</span></span>  
  
##  <a name="2-choose-the-chart-type"></a><a name="ChartType"></a><span data-ttu-id="e5f4c-149">2. escolher o tipo de gráfico</span><span class="sxs-lookup"><span data-stu-id="e5f4c-149">2. Choose the Chart Type</span></span>  
 <span data-ttu-id="e5f4c-150">Você pode escolher um dos diversos tipos de gráfico predefinidos.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-150">You can choose from a variety of predefined chart types.</span></span>  
  
#### <a name="to-add-a-pie-chart"></a><span data-ttu-id="e5f4c-151">Para adicionar um gráfico de pizza</span><span class="sxs-lookup"><span data-stu-id="e5f4c-151">To add a pie chart</span></span>  
  
1.  <span data-ttu-id="e5f4c-152">Na página **escolher um tipo de gráfico** , clique em **pizza**e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-152">On the **Choose a chart type** page, click **Pie**, and then click **Next**.</span></span> <span data-ttu-id="e5f4c-153">A página **Organizar campos de gráfico** será aberta.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-153">The **Arrange chart fields** page opens.</span></span>  
  
     <span data-ttu-id="e5f4c-154">Na página **Organizar campos de gráfico** , arraste o campo Produto até o painel **Categorias** .</span><span class="sxs-lookup"><span data-stu-id="e5f4c-154">On the **Arrange chart fields** page, drag the Product field to the **Categories** pane.</span></span> <span data-ttu-id="e5f4c-155">Esse painel define o número de fatias do gráfico de pizza.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-155">Categories define the number of slices in the pie chart.</span></span> <span data-ttu-id="e5f4c-156">Neste exemplo, haverá oito fatias, uma para cada produto.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-156">In this example, there will be eight slices, one for each product.</span></span>  
  
2.  <span data-ttu-id="e5f4c-157">Arraste o campo Vendas até o painel **Valores** .</span><span class="sxs-lookup"><span data-stu-id="e5f4c-157">Drag the Sales field to the **Values** pane.</span></span> <span data-ttu-id="e5f4c-158">Sales representa a quantidade de vendas da subcategoria.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-158">Sales represents the sales amount for the subcategory.</span></span> <span data-ttu-id="e5f4c-159">O painel **valores** é exibido `[Sum(Sales)]` porque o gráfico exibe a agregação de cada produto.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-159">The **Values** pane displays `[Sum(Sales)]` because the chart displays the aggregate for each product.</span></span>  
  
3.  <span data-ttu-id="e5f4c-160">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-160">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="e5f4c-161">Na página **escolher um estilo** , no painel estilos, selecione um estilo.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-161">On the **Choose a style** page, in the Styles pane, select a style.</span></span>  
  
     <span data-ttu-id="e5f4c-162">Um estilo especifica um estilo de fonte, um conjunto de cores e um estilo de borda.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-162">A style specifies a font style, a set of colors, and a border style.</span></span> <span data-ttu-id="e5f4c-163">Quando você selecionar um estilo, o painel Visualizar exibirá um exemplo do gráfico com esse estilo.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-163">When you select a style, the Preview pane displays a sample of the chart with that style.</span></span>  
  
5.  <span data-ttu-id="e5f4c-164">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-164">Click **Finish**.</span></span>  
  
     <span data-ttu-id="e5f4c-165">O gráfico é adicionado à superfície de design.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-165">The chart is added to the design surface.</span></span>  
  
6.  <span data-ttu-id="e5f4c-166">Clique no gráfico para exibir suas alças.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-166">Click the chart to display the chart handles.</span></span> <span data-ttu-id="e5f4c-167">Arraste o canto inferior direito do gráfico para aumentar o tamanho do gráfico.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-167">Drag the bottom-right corner of the chart to increase the size of the chart.</span></span> <span data-ttu-id="e5f4c-168">Observe que o tamanho da superfície de design de relatório aumenta para acomodar o tamanho do gráfico.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-168">Note that the report design surface increases in size to accommodate the chart size.</span></span>  
  
7.  <span data-ttu-id="e5f4c-169">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-169">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="e5f4c-170">O relatório exibe o gráfico de pizza com oito fatias, uma para cada produto.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-170">The report displays the pie chart with eight slices, one for each product.</span></span> <span data-ttu-id="e5f4c-171">O tamanho de cada fatia representa as vendas desse produto.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-171">The size of each slice represents the sales for that product.</span></span> <span data-ttu-id="e5f4c-172">Três das fatias são bastante finas.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-172">Three of the slices are quite thin.</span></span>  
  
##  <a name="3-display-percentages-in-each-slice"></a><a name="Percentages"></a><span data-ttu-id="e5f4c-173">3. exibir porcentagens em cada fatia</span><span class="sxs-lookup"><span data-stu-id="e5f4c-173">3. Display Percentages in Each Slice</span></span>  
 <span data-ttu-id="e5f4c-174">Em cada fatia da pizza, é possível exibir uma porcentagem dessa fatia comparada à pizza inteira.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-174">On each slice of the pie, you can display a percentage for this slice compared to the whole pie.</span></span>  
  
#### <a name="to-display-percentages-in-each-slice-of-the-pie-chart"></a><span data-ttu-id="e5f4c-175">Para exibir as porcentagens em cada fatia do gráfico de pizza</span><span class="sxs-lookup"><span data-stu-id="e5f4c-175">To display percentages in each slice of the pie chart</span></span>  
  
1.  <span data-ttu-id="e5f4c-176">Alterne para a exibição de design de relatório.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-176">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="e5f4c-177">Clique com o botão direito do mouse no gráfico de pizza e clique em **Mostrar Rótulos de Dados**.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-177">Right-click the pie chart and click **Show Data Labels**.</span></span> <span data-ttu-id="e5f4c-178">Os rótulos de dados são exibidos no gráfico.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-178">The data labels appear on the chart.</span></span>  
  
3.  <span data-ttu-id="e5f4c-179">Clique com o botão direito do mouse em um rótulo e clique em **Propriedades do rótulo da série**.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-179">Right-click a label, and then click **Series Label Properties**.</span></span>  
  
4.  <span data-ttu-id="e5f4c-180">Em dados do rótulo, na caixa suspensa, selecione **#PERCENT**.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-180">In Label data, from the drop-down box, select **#PERCENT**.</span></span>  
  
     <span data-ttu-id="e5f4c-181">Para exibir valores como porcentagens, a propriedade UseValueAsLabel deve ser falsa.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-181">To display values as percentages, the UseValueAsLabel property must be false.</span></span> <span data-ttu-id="e5f4c-182">Se for solicitado que você defina esse valor na caixa de diálogo **Confirmar Ação** , clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-182">If you are prompted to set this value in the **Confirm Action** dialog, click **Yes**.</span></span>  
  
5.  <span data-ttu-id="e5f4c-183">Adicional Para especificar quantas casas decimais o rótulo deve mostrar, digite `#PERCENT{Pn}` onde *n* é o número de casas decimais a serem exibidas.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-183">(Optional) To specify how many decimal places the label shows, type `#PERCENT{Pn}` where *n* is the number of decimal places to display.</span></span> <span data-ttu-id="e5f4c-184">Por exemplo, para não exibir casas decimais, digite `#PERCENT{P0}` .</span><span class="sxs-lookup"><span data-stu-id="e5f4c-184">For example, to display no decimal places, type `#PERCENT{P0}`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e5f4c-185">O**Formato de Número** na caixa de diálogo **Propriedades do Rótulo de Série** não tem nenhum efeito quando você formata percentuais.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-185">**Number Format** in the **Series Label Properties** dialog box has no effect when you format percentages.</span></span> <span data-ttu-id="e5f4c-186">Isso formata os rótulos como porcentagens, mas não calcula qual porcentagem do gráfico de pizza cada fatia representa.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-186">This formats the labels as percentages, but does not calculate the percentage of the pie that each slice represents.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="e5f4c-187">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-187">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="e5f4c-188">O relatório exibe a porcentagem do todo para cada fatia da pizza.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-188">The report displays the percentage of the whole for each pie slice.</span></span>  
  
##  <a name="4-combine-small-slices-into-one-slice"></a><a name="CombineSlices"></a><span data-ttu-id="e5f4c-189">4. combinar fatias pequenas em uma fatia</span><span class="sxs-lookup"><span data-stu-id="e5f4c-189">4. Combine Small Slices into One Slice</span></span>  
 <span data-ttu-id="e5f4c-190">Três das fatias do gráfico são bastante pequenas.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-190">Three of the slices in the pie are quite small.</span></span> <span data-ttu-id="e5f4c-191">É possível combinar várias fatias pequenas em uma fatia maior que representa todas elas.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-191">You can combine multiple small slices into one larger slice that represents all of them.</span></span>  
  
#### <a name="to-combine-any-slices-on-the-pie-chart-smaller-than-5-percent-into-one-slice"></a><span data-ttu-id="e5f4c-192">Para combinar fatias no gráfico de pizza menores do que 5% em uma fatia</span><span class="sxs-lookup"><span data-stu-id="e5f4c-192">To combine any slices on the pie chart smaller than 5 percent into one slice</span></span>  
  
1.  <span data-ttu-id="e5f4c-193">Alterne para a exibição de design de relatório.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-193">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="e5f4c-194">Na guia **Exibir** , no grupo **Mostrar/ocultar** , selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-194">On the **View** tab, in the **Show/Hide** group, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="e5f4c-195">Na superfície de design, clique em qualquer fatia do gráfico de pizza.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-195">On the design surface, click on any slice of the pie chart.</span></span> <span data-ttu-id="e5f4c-196">As propriedades da série são exibidas no painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-196">The properties for the series are displayed in the Properties pane.</span></span>  
  
4.  <span data-ttu-id="e5f4c-197">Na seção **Geral** , expanda o nó **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="e5f4c-197">In the **General** section, expand the **CustomAttributes** node.</span></span>  
  
5.  <span data-ttu-id="e5f4c-198">Defina a propriedade **CollectedStyle** como **SingleSlice**.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-198">Set the **CollectedStyle** property to **SingleSlice**.</span></span>  
  
6.  <span data-ttu-id="e5f4c-199">Verifique se a propriedade **CollectedThreshold** está definida como 5.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-199">Verify that the **CollectedThreshold** property is set to 5.</span></span>  
  
7.  <span data-ttu-id="e5f4c-200">Verifique se a propriedade **CollectedThresholdUsePercent** está definida como **True**.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-200">Verify that the **CollectedThresholdUsePercent** property is set to **True**.</span></span>  
  
8.  <span data-ttu-id="e5f4c-201">Na faixa de faixas, na guia **início** , clique em **executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-201">On the Ribbon, on the **Home** tab, click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="e5f4c-202">Na legenda, a categoria "Outro" agora existe.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-202">In the legend, the category "Other" now exists.</span></span> <span data-ttu-id="e5f4c-203">A nova fatia da pizza combina todas as fatias que estavam abaixo de 5% em uma fatia que representa 6% da pizza inteira.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-203">The new pie slice combines all the slices that were under 5% into one slice that is 6% of the whole pie.</span></span>  
  
##  <a name="5-customize-the-drawing-effect"></a><a name="DrawingEffect"></a><span data-ttu-id="e5f4c-204">5. personalizar o efeito de desenho</span><span class="sxs-lookup"><span data-stu-id="e5f4c-204">5. Customize the Drawing Effect</span></span>  
 <span data-ttu-id="e5f4c-205">No Assistente de Gráfico, o estilo padrão de um gráfico de pizza é Ocean, que apresenta um efeito de desenho Côncavo.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-205">In the Chart Wizard, the default style for a pie chart is Ocean, which features a Concave drawing effect.</span></span> <span data-ttu-id="e5f4c-206">Você poderá alterá-lo depois de executar o assistente.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-206">You can change that after you run the wizard.</span></span>  
  
#### <a name="to-add-a-drawing-effect-to-the-pie-chart"></a><span data-ttu-id="e5f4c-207">Para adicionar um efeito de desenho ao gráfico de pizza</span><span class="sxs-lookup"><span data-stu-id="e5f4c-207">To add a drawing effect to the pie chart</span></span>  
  
1.  <span data-ttu-id="e5f4c-208">Alterne para a exibição de design de relatório.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-208">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="e5f4c-209">Se o painel Propriedades ainda não estiver aberto, na guia **Exibir** , selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-209">If the Properties pane is not already opened, on the **View** tab, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="e5f4c-210">Clique duas vezes no próprio gráfico de pizza.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-210">Double-click the pie chart itself.</span></span> <span data-ttu-id="e5f4c-211">As propriedades da série do gráfico de pizza são mostradas no painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-211">The series properties for the pie chart are shown in the Properties pane.</span></span>  
  
4.  <span data-ttu-id="e5f4c-212">No painel Propriedades, expanda o nó **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="e5f4c-212">In the Properties pane, expand the **CustomAttributes** node.</span></span>  
  
5.  <span data-ttu-id="e5f4c-213">Defina **PieDrawingStyle** como **SoftEdge**.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-213">Set the **PieDrawingStyle** to **SoftEdge**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e5f4c-214">Efeitos de desenho e efeitos tridimensionais são opções exclusivas.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-214">Drawing effects and three-dimensional effects are exclusive options.</span></span> <span data-ttu-id="e5f4c-215">Se um gráfico tiver efeitos tridimensionais aplicados, **PieDrawingStyle** não estará disponível no painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-215">If a chart has three-dimensional effects applied, **PieDrawingStyle** is not available on the Properties pane.</span></span>  
  
6.  <span data-ttu-id="e5f4c-216">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-216">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="e5f4c-217">A ilustração a seguir mostra o gráfico de pizza com o efeito de borda suave.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-217">The following illustration shows the pie chart with the soft edge effect.</span></span>  
  
 <span data-ttu-id="e5f4c-218">![rs_TutorialPieChartSoftEdge](../../2014/tutorials/media/rs-tutorialpiechartsoftedge.gif "rs_TutorialPieChartSoftEdge")</span><span class="sxs-lookup"><span data-stu-id="e5f4c-218">![rs_TutorialPieChartSoftEdge](../../2014/tutorials/media/rs-tutorialpiechartsoftedge.gif "rs_TutorialPieChartSoftEdge")</span></span>  
  
##  <a name="6-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="e5f4c-219">6. adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="e5f4c-219">6. Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="e5f4c-220">Para adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="e5f4c-220">To add a report title</span></span>  
  
1.  <span data-ttu-id="e5f4c-221">Na superfície de design, clique em **Clique para adicionar título**.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-221">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="e5f4c-222">Digite **Vendas de Câmeras e Filmadoras**, pressione ENTER e digite **Como um Percentual do Total de Vendas**para que fique assim:</span><span class="sxs-lookup"><span data-stu-id="e5f4c-222">Type **Camera and Camcorder Sales**, press ENTER, and then type **As a Percentage of Total Sales**, so it looks like this:</span></span>  
  
     <span data-ttu-id="e5f4c-223">**Vendas de Câmeras e Filmadoras**</span><span class="sxs-lookup"><span data-stu-id="e5f4c-223">**Camera and Camcorder Sales**</span></span>  
  
     <span data-ttu-id="e5f4c-224">**Como um Percentual do Total de Vendas**</span><span class="sxs-lookup"><span data-stu-id="e5f4c-224">**As a Percentage of Total Sales**</span></span>  
  
3.  <span data-ttu-id="e5f4c-225">Selecione **vendas de câmera e camcorder**e clique no botão **negrito** na seção **fonte** da guia **página inicial** da faixa de opções.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-225">Select **Camera and Camcorder Sales**, and click the **Bold** button from the **Font** section of the **Home** tab of the ribbon.</span></span>  
  
4.  <span data-ttu-id="e5f4c-226">Selecione **como uma porcentagem do total de vendas**e, na seção **fonte** , na guia **início** , defina o tamanho da fonte como **10**.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-226">Select **As a Percentage of Total Sales**, and in the **Font** section on the **Home** tab, set the font size to **10**.</span></span>  
  
5.  <span data-ttu-id="e5f4c-227">(Opcional) Talvez seja necessário aumentar a altura da caixa de texto Título para acomodar as duas linhas de texto.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-227">(Optional) You may need to make the Title text box taller to accommodate the two lines of text.</span></span>  
  
     <span data-ttu-id="e5f4c-228">Esse título aparecerá na parte superior do relatório.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-228">This title will appear at the top of the report.</span></span> <span data-ttu-id="e5f4c-229">Quando não houver nenhum cabeçalho de página definido, os itens na parte superior do corpo do relatório serão equivalentes a um cabeçalho de relatório.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-229">When there is no page header defined, items at the top of the report body are the equivalent of a report header.</span></span>  
  
6.  <span data-ttu-id="e5f4c-230">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-230">Click **Run** to preview the report.</span></span>  
  
##  <a name="7-save-the-report"></a><a name="Save"></a><span data-ttu-id="e5f4c-231">7. salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="e5f4c-231">7. Save the Report</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="e5f4c-232">Para salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="e5f4c-232">To save the report</span></span>  
  
1.  <span data-ttu-id="e5f4c-233">Alterne para a exibição de design de relatório.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-233">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="e5f4c-234">No botão Construtor de Relatórios , clique em **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-234">From the Report Builder button, click **Save As**.</span></span>  
  
3.  <span data-ttu-id="e5f4c-235">Em **Nome**, digite **Gráfico de Pizza de Vendas**.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-235">In **Name**, type **Sales Pie Chart**.</span></span>  
  
4.  <span data-ttu-id="e5f4c-236">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-236">Click **Save**.</span></span>  
  
 <span data-ttu-id="e5f4c-237">O relatório é salvo no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-237">Your report is saved on the report server.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e5f4c-238">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="e5f4c-238">Next Steps</span></span>  
 <span data-ttu-id="e5f4c-239">Você concluiu com êxito o tutorial Adicionando um Gráfico de Pizza ao seu Relatório.</span><span class="sxs-lookup"><span data-stu-id="e5f4c-239">You have successfully completed the Adding a Pie Chart to Your Report tutorial.</span></span> <span data-ttu-id="e5f4c-240">Para saber mais sobre gráficos, consulte [Gráficos &#40;Construtor de Relatórios e SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) e [Minigráficos e barras de dados &#40;Construtor de Relatórios e SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e5f4c-240">To learn more about charts, see [Charts &#40;Report Builder and SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) and [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5f4c-241">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e5f4c-241">See Also</span></span>  
 <span data-ttu-id="e5f4c-242">[TUTORIAIS &#40;Construtor de Relatórios&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="e5f4c-242">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="e5f4c-243">Construtor de Relatórios no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="e5f4c-243">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
