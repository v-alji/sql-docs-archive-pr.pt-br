---
title: 'Tutorial: Adicionar um gráfico de colunas ao relatório (Construtor de Relatórios) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 63480059-b7b9-44b5-9d7f-91780db708b6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0ef3b3f2872c2f8181296bb05337ca18975ac2f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684041"
---
# <a name="tutorial-add-a-column-chart-to-your-report-report-builder"></a><span data-ttu-id="93cfb-102">Tutorial: Adicionar um gráfico de colunas ao relatório (Construtor de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="93cfb-102">Tutorial: Add a Column Chart to Your Report (Report Builder)</span></span>
  <span data-ttu-id="93cfb-103">Um gráfico de coluna exibe uma série como um conjunto de barras verticais agrupadas por categoria.</span><span class="sxs-lookup"><span data-stu-id="93cfb-103">A column chart displays a series as a set of vertical bars that are grouped by category.</span></span> <span data-ttu-id="93cfb-104">Um gráfico de coluna pode ser útil para:</span><span class="sxs-lookup"><span data-stu-id="93cfb-104">A column chart can be useful to:</span></span>  
  
-   <span data-ttu-id="93cfb-105">Mostrar alterações de dados em um período de tempo.</span><span class="sxs-lookup"><span data-stu-id="93cfb-105">Show data changes over a period of time.</span></span>  
  
-   <span data-ttu-id="93cfb-106">Comparar o valor relativo de várias séries.</span><span class="sxs-lookup"><span data-stu-id="93cfb-106">Compare the relative value of multiple series.</span></span>  
  
-   <span data-ttu-id="93cfb-107">Exibir uma média móvel para mostrar tendências.</span><span class="sxs-lookup"><span data-stu-id="93cfb-107">Display a moving average to show trends.</span></span>  
  
 <span data-ttu-id="93cfb-108">A ilustração seguinte mostra o gráfico de coluna que você criará, com uma média móvel.</span><span class="sxs-lookup"><span data-stu-id="93cfb-108">The following illustration shows the column chart you will create, with a moving average.</span></span>  
  
 <span data-ttu-id="93cfb-109">![rs_TutorialColChartFinished](../../2014/tutorials/media/rs-tutorialcolchartfinished.gif "rs_TutorialColChartFinished")</span><span class="sxs-lookup"><span data-stu-id="93cfb-109">![rs_TutorialColChartFinished](../../2014/tutorials/media/rs-tutorialcolchartfinished.gif "rs_TutorialColChartFinished")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="93cfb-110">O que você aprenderá</span><span class="sxs-lookup"><span data-stu-id="93cfb-110">What You Will Learn</span></span>  
 <span data-ttu-id="93cfb-111">Neste tutorial, você aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="93cfb-111">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="93cfb-112">Criar um gráfico no Assistente de Gráfico</span><span class="sxs-lookup"><span data-stu-id="93cfb-112">Create a Chart from the Chart Wizard</span></span>](#Chart)  
  
2.  [<span data-ttu-id="93cfb-113">Escolher o tipo de gráfico</span><span class="sxs-lookup"><span data-stu-id="93cfb-113">Choose the Chart Type</span></span>](#ChartType)  
  
3.  [<span data-ttu-id="93cfb-114">Formatar e rotular o eixo horizontal</span><span class="sxs-lookup"><span data-stu-id="93cfb-114">Format and Label the Horizontal Axis</span></span>](#Horizontal)  
  
4.  [<span data-ttu-id="93cfb-115">Mover a legenda</span><span class="sxs-lookup"><span data-stu-id="93cfb-115">Move the Legend</span></span>](#Legend)  
  
5.  [<span data-ttu-id="93cfb-116">Intitular o gráfico</span><span class="sxs-lookup"><span data-stu-id="93cfb-116">Title the Chart</span></span>](#ChartTitle)  
  
6.  [<span data-ttu-id="93cfb-117">Formatar e rotular o eixo vertical</span><span class="sxs-lookup"><span data-stu-id="93cfb-117">Format and Label the Vertical Axis</span></span>](#Vertical)  
  
7.  [<span data-ttu-id="93cfb-118">Adicionar uma média móvel</span><span class="sxs-lookup"><span data-stu-id="93cfb-118">Add a Moving Average</span></span>](#Average)  
  
8.  [<span data-ttu-id="93cfb-119">Adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="93cfb-119">Add a Report Title</span></span>](#Title)  
  
9. [<span data-ttu-id="93cfb-120">Salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="93cfb-120">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="93cfb-121">Neste tutorial, as etapas do assistente são consolidadas em um procedimento.</span><span class="sxs-lookup"><span data-stu-id="93cfb-121">In this tutorial, the steps for the wizard are consolidated into one procedure.</span></span> <span data-ttu-id="93cfb-122">Para obter instruções passo a passo sobre como procurar um servidor de relatório, escolher uma fonte de dados e criar um conjunto de dados, consulte o primeiro tutorial desta série: [Tutorial: Criação de um relatório de tabela básico &#40;Construtor de Relatórios&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="93cfb-122">For step-by-step instructions about how to browse to a report server, choose a data source, and create a dataset, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="93cfb-123">Tempo estimado para concluir este tutorial: 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="93cfb-123">Estimated time to complete this tutorial: 15 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93cfb-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="93cfb-124">Requirements</span></span>  
 <span data-ttu-id="93cfb-125">Para obter informações sobre os requisitos, consulte [Pré-requisitos para tutoriais &#40;Construtor de Relatórios&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="93cfb-125">For information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-chart-report-from-the-chart-wizard"></a><a name="Chart"></a><span data-ttu-id="93cfb-126">1. criar um relatório de gráfico do assistente de gráfico</span><span class="sxs-lookup"><span data-stu-id="93cfb-126">1. Create a Chart Report from the Chart Wizard</span></span>  
 <span data-ttu-id="93cfb-127">Na caixa de diálogo **introdução** , use o assistente de gráfico para criar um conjunto de dados inserido, escolha uma fonte de dados compartilhada e crie um gráfico de colunas.</span><span class="sxs-lookup"><span data-stu-id="93cfb-127">From the **Getting Started** dialog box, use the Chart Wizard to create an embedded dataset, choose a shared data source, and create a column chart.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="93cfb-128">Neste tutorial, a consulta contém os valores de dados para que não precise de uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="93cfb-128">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="93cfb-129">Isso torna a consulta bastante longa.</span><span class="sxs-lookup"><span data-stu-id="93cfb-129">This makes the query quite long.</span></span> <span data-ttu-id="93cfb-130">Em um ambiente empresarial, uma consulta não conteria os dados.</span><span class="sxs-lookup"><span data-stu-id="93cfb-130">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="93cfb-131">Isso é apenas para fins de aprendizado.</span><span class="sxs-lookup"><span data-stu-id="93cfb-131">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-chart-report"></a><span data-ttu-id="93cfb-132">Para criar um novo relatório de gráfico</span><span class="sxs-lookup"><span data-stu-id="93cfb-132">To create a new chart report</span></span>  
  
1.  <span data-ttu-id="93cfb-133">Clique em **Iniciar**, aponte para **Programas**, para **Construtor de Relatórios do Microsoft SQL Server 2012**e clique em **Construtor de Relatórios**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-133">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="93cfb-134">A caixa de diálogo **introdução** é exibida.</span><span class="sxs-lookup"><span data-stu-id="93cfb-134">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="93cfb-135">Se a caixa de diálogo **introdução** não for exibida, no botão **Construtor de relatórios** , clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-135">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="93cfb-136">No painel esquerdo, verifique se **Novo Relatório** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="93cfb-136">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="93cfb-137">No painel direito, clique em **Assistente de Gráfico**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-137">In the right pane, click **Chart Wizard**.</span></span>  
  
4.  <span data-ttu-id="93cfb-138">Na **página escolher um conjunto de uma**, clique em **criar um conjunto de um**e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-138">On the **Choose a dataset page**, click **Create a dataset**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="93cfb-139">Na página **Escolher uma conexão com uma fonte de dados** , selecione uma fonte de dados existente ou procure o servidor de relatório, selecione uma fonte de dados e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-139">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source, and then click **Next**.</span></span> <span data-ttu-id="93cfb-140">Talvez seja necessário inserir um nome de usuário e uma senha.</span><span class="sxs-lookup"><span data-stu-id="93cfb-140">You may need to enter a user name and password.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="93cfb-141">A fonte de dados escolhida não tem importância, contanto que você tenha permissões suficientes.</span><span class="sxs-lookup"><span data-stu-id="93cfb-141">The data source you choose is unimportant, as long as you have adequate permissions.</span></span> <span data-ttu-id="93cfb-142">Você não obterá dados da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="93cfb-142">You will not be getting data from the data source.</span></span> <span data-ttu-id="93cfb-143">Para obter mais informações, consulte [Formas alternativas de obter uma conexão de dados &#40;Construtor de Relatórios&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="93cfb-143">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
6.  <span data-ttu-id="93cfb-144">Na página **Crie uma consulta** , clique em **Editar como Texto**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-144">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
7.  <span data-ttu-id="93cfb-145">Cole a seguinte consulta no painel de consulta:</span><span class="sxs-lookup"><span data-stu-id="93cfb-145">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT CAST('2009-01-01' AS date) AS SalesDate, CAST(54995.21 AS money) AS Sales  
    UNION SELECT CAST('2009-01-05' AS date) AS SalesDate, CAST(64499.04 AS money) AS Sales  
    UNION SELECT CAST('2009-02-11' AS date) AS SalesDate, CAST(37821.79 AS money) AS Sales  
    UNION SELECT CAST('2009-03-18' AS date) AS SalesDate, CAST(53633.08 AS money) AS Sales  
    UNION SELECT CAST('2009-04-23' AS date) AS SalesDate, CAST(24019.3 AS money) AS Sales  
    UNION SELECT CAST('2009-05-01' AS date) AS SalesDate, CAST(93245.5 AS money) AS Sales  
    UNION SELECT CAST('2009-06-06' AS date) AS SalesDate, CAST(55288.0 AS money) AS Sales  
    UNION SELECT CAST('2009-06-16' AS date) AS SalesDate, CAST(68733.5 AS money) AS Sales  
    UNION SELECT CAST('2009-07-16' AS date) AS SalesDate, CAST(24750.85 AS money) AS Sales  
    UNION SELECT CAST('2009-08-23' AS date) AS SalesDate, CAST(43452.3 AS money) AS Sales  
    UNION SELECT CAST('2009-09-24' AS date) AS SalesDate, CAST(58656. AS money) AS Sales  
    UNION SELECT CAST('2009-10-15' AS date) AS SalesDate, CAST(44583. AS money) AS Sales  
    UNION SELECT CAST('2009-11-21' AS date) AS SalesDate, CAST(81568. AS money) AS Sales  
    UNION SELECT CAST('2009-12-15' AS date) AS SalesDate, CAST(45973. AS money) AS Sales  
    UNION SELECT CAST('2009-12-26' AS date) AS SalesDate, CAST(96357. AS money) AS Sales  
    UNION SELECT CAST('2009-12-31' AS date) AS SalesDate, CAST(81946. AS money) AS Sales  
    ```  
  
8.  <span data-ttu-id="93cfb-146">(Opcional) Clique no botão Executar (**!**) para ver os dados em que o gráfico se baseará.</span><span class="sxs-lookup"><span data-stu-id="93cfb-146">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>  
  
9. <span data-ttu-id="93cfb-147">Clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-147">Click **Next**.</span></span>  
  
##  <a name="2-choose-the-chart-type"></a><a name="ChartType"></a><span data-ttu-id="93cfb-148">2. escolher o tipo de gráfico</span><span class="sxs-lookup"><span data-stu-id="93cfb-148">2. Choose the Chart Type</span></span>  
 <span data-ttu-id="93cfb-149">Você pode escolher um dos diversos tipos de gráfico predefinidos.</span><span class="sxs-lookup"><span data-stu-id="93cfb-149">You can choose from a variety of predefined chart types.</span></span>  
  
#### <a name="to-add-a-column-chart"></a><span data-ttu-id="93cfb-150">Para adicionar um gráfico de colunas</span><span class="sxs-lookup"><span data-stu-id="93cfb-150">To add a column chart</span></span>  
  
1.  <span data-ttu-id="93cfb-151">Na página **Escolher um tipo de gráfico** , o gráfico de colunas é o tipo de gráfico padrão.</span><span class="sxs-lookup"><span data-stu-id="93cfb-151">On the **Choose a chart type** page, the column chart is the default chart type.</span></span> <span data-ttu-id="93cfb-152">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-152">Click **Next**.</span></span>  
  
2.  <span data-ttu-id="93cfb-153">Na página **Organizar campos de gráfico** , arraste o campo SalesDate até **Categorias**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-153">On the **Arrange chart fields** page, drag the SalesDate field to **Categories**.</span></span> <span data-ttu-id="93cfb-154">As categorias são exibidas no eixo horizontal.</span><span class="sxs-lookup"><span data-stu-id="93cfb-154">Categories display on the horizontal axis.</span></span>  
  
3.  <span data-ttu-id="93cfb-155">Arraste o campo Sales até **Valores**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-155">Drag the Sales field to **Values**.</span></span> <span data-ttu-id="93cfb-156">A caixa **Valores** exibe Sum(Sales) porque a soma do valor total das vendas é agregada para cada data.</span><span class="sxs-lookup"><span data-stu-id="93cfb-156">The **Values** box displays Sum(Sales) because the sum of the sales total value is aggregated for each date.</span></span> <span data-ttu-id="93cfb-157">Os valores são exibidos no eixo vertical.</span><span class="sxs-lookup"><span data-stu-id="93cfb-157">Values display on the vertical axis.</span></span>  
  
4.  <span data-ttu-id="93cfb-158">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-158">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="93cfb-159">Na página **escolher um estilo** , na caixa estilos, selecione um estilo.</span><span class="sxs-lookup"><span data-stu-id="93cfb-159">On the **Choose a Style** page, in the Styles box, select a style.</span></span>  
  
     <span data-ttu-id="93cfb-160">Um estilo especifica um estilo de fonte, um conjunto de cores e um estilo de borda.</span><span class="sxs-lookup"><span data-stu-id="93cfb-160">A style specifies a font style, a set of colors, and a border style.</span></span> <span data-ttu-id="93cfb-161">Quando você selecionar um estilo, o painel Visualizar exibirá um exemplo do gráfico com esse estilo.</span><span class="sxs-lookup"><span data-stu-id="93cfb-161">When you select a style, the Preview pane displays a sample of the chart with that style.</span></span>  
  
6.  <span data-ttu-id="93cfb-162">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-162">Click **Finish**.</span></span>  
  
     <span data-ttu-id="93cfb-163">O gráfico é adicionado à superfície de design.</span><span class="sxs-lookup"><span data-stu-id="93cfb-163">The chart is added to the design surface.</span></span>  
  
7.  <span data-ttu-id="93cfb-164">Clique no gráfico para exibir suas alças.</span><span class="sxs-lookup"><span data-stu-id="93cfb-164">Click the chart to display the chart handles.</span></span> <span data-ttu-id="93cfb-165">Arraste o canto inferior direito do gráfico para aumentar o tamanho do gráfico.</span><span class="sxs-lookup"><span data-stu-id="93cfb-165">Drag the bottom-right corner of the chart to increase the size of the chart.</span></span> <span data-ttu-id="93cfb-166">Observe que o tamanho da superfície de design de relatório aumenta para acomodar o tamanho do gráfico.</span><span class="sxs-lookup"><span data-stu-id="93cfb-166">Note that the report design surface increases in size to accommodate the chart size.</span></span>  
  
8.  <span data-ttu-id="93cfb-167">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="93cfb-167">Click **Run** to preview the report.</span></span>  
  
##  <a name="3-format-and-label-the-horizontal-axis"></a><a name="Horizontal"></a><span data-ttu-id="93cfb-168">3. Formatar e rotular o eixo horizontal</span><span class="sxs-lookup"><span data-stu-id="93cfb-168">3. Format and Label the Horizontal Axis</span></span>  
 <span data-ttu-id="93cfb-169">Por padrão, o eixo horizontal exibe valores em um formato geral que é dimensionado para ajustar o tamanho do gráfico automaticamente.</span><span class="sxs-lookup"><span data-stu-id="93cfb-169">By default, the horizontal axis displays values in a general format that is automatically scaled to fit the size of the chart.</span></span>  
  
#### <a name="to-format-a-date-on-the-horizontal-axis"></a><span data-ttu-id="93cfb-170">Para formatar uma data no eixo horizontal</span><span class="sxs-lookup"><span data-stu-id="93cfb-170">To format a date on the horizontal axis</span></span>  
  
1.  <span data-ttu-id="93cfb-171">Alterne para a exibição de design de relatório.</span><span class="sxs-lookup"><span data-stu-id="93cfb-171">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="93cfb-172">Clique com o botão direito do mouse no eixo horizontal e clique em **Propriedades do eixo horizontal**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-172">Right-click the horizontal axis, and then click **Horizontal Axis Properties**.</span></span>  
  
3.  <span data-ttu-id="93cfb-173">Clique em **Número**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-173">Click **Number**.</span></span>  
  
4.  <span data-ttu-id="93cfb-174">Em **categoria**, selecione **Data**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-174">In **Category**, select **Date**.</span></span>  
  
5.  <span data-ttu-id="93cfb-175">Na caixa **Tipo** , selecione **31 de janeiro de 2000**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-175">In the **Type** box, select **31 Jan 2000**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="93cfb-176">Na guia Início, clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="93cfb-176">On the Home tab, click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="93cfb-177">A data é exibida no formato selecionado.</span><span class="sxs-lookup"><span data-stu-id="93cfb-177">The date displays in the date format that you selected.</span></span> <span data-ttu-id="93cfb-178">Observe que o gráfico não rotula cada categoria no eixo horizontal.</span><span class="sxs-lookup"><span data-stu-id="93cfb-178">Notice that the chart does not label every category on the horizontal axis.</span></span> <span data-ttu-id="93cfb-179">Por padrão, somente rótulos que se ajustam próximo ao eixo são incluídos.</span><span class="sxs-lookup"><span data-stu-id="93cfb-179">By default, only labels that fit next to the axis are included.</span></span>  
  
 <span data-ttu-id="93cfb-180">É possível personalizar a exibição de rótulo como o giro dos rótulos e a especificação do intervalo.</span><span class="sxs-lookup"><span data-stu-id="93cfb-180">You can customize the label display by rotating the labels and specifying the interval.</span></span>  
  
#### <a name="to-rotate-the-axis-labels-and-change-the-display-interval-along-the-horizontal-axis"></a><span data-ttu-id="93cfb-181">Para girar os rótulos do eixo e alterar o intervalo de exibição ao longo do eixo horizontal</span><span class="sxs-lookup"><span data-stu-id="93cfb-181">To rotate the axis labels and change the display interval along the horizontal axis</span></span>  
  
1.  <span data-ttu-id="93cfb-182">Alterne para a exibição de design de relatório.</span><span class="sxs-lookup"><span data-stu-id="93cfb-182">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="93cfb-183">Clique com o botão direito do mouse no título do eixo horizontal e clique em **Mostrar título do eixo** para remover o título.</span><span class="sxs-lookup"><span data-stu-id="93cfb-183">Right-click the horizontal axis title, and then click **Show Axis Title** to remove the title.</span></span> <span data-ttu-id="93cfb-184">Como o eixo horizontal exibe datas, o título não é necessário.</span><span class="sxs-lookup"><span data-stu-id="93cfb-184">Because the horizontal axis displays dates, the title is not needed.</span></span>  
  
3.  <span data-ttu-id="93cfb-185">Clique com o botão direito do mouse no eixo horizontal e clique em **Propriedades do eixo horizontal**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-185">Right-click the horizontal axis and then click **Horizontal Axis Properties**.</span></span>  
  
4.  <span data-ttu-id="93cfb-186">Na página **Opções do eixo** , em **intervalo e**intervalo do eixo, digite **3** para **intervalo**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-186">In the **Axis Options** page under **Axis range and interval**, type **3** for **Interval**.</span></span> <span data-ttu-id="93cfb-187">O gráfico exibirá a cada três datas.</span><span class="sxs-lookup"><span data-stu-id="93cfb-187">The chart will display every third date.</span></span>  
  
5.  <span data-ttu-id="93cfb-188">Clique em **Rótulos**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-188">Click **Labels**.</span></span>  
  
6.  <span data-ttu-id="93cfb-189">Em **alterar opções de ajuste automático do rótulo do eixo**, selecione **Desabilitar ajuste automático**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-189">In **Change axis label auto-fit options**, select **Disable auto-fit**.</span></span>  
  
7.  <span data-ttu-id="93cfb-190">Em **Ângulo de rotação do rótulo**, selecione **-90**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-190">In **Label rotation angle**, select **-90**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="93cfb-191">O texto de exemplo para o eixo horizontal gira 90 graus.</span><span class="sxs-lookup"><span data-stu-id="93cfb-191">The sample text for the horizontal axis rotates by 90 degrees.</span></span>  
  
9. <span data-ttu-id="93cfb-192">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="93cfb-192">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="93cfb-193">No gráfico, os rótulos são girados e o rótulo a cada três datas é mostrado.</span><span class="sxs-lookup"><span data-stu-id="93cfb-193">On the chart, the labels are rotated and the label for every third date is shown.</span></span>  
  
##  <a name="4-move-the-legend"></a><a name="Legend"></a><span data-ttu-id="93cfb-194">4. mover a legenda</span><span class="sxs-lookup"><span data-stu-id="93cfb-194">4. Move the Legend</span></span>  
 <span data-ttu-id="93cfb-195">A legenda é criada automaticamente de categoria e dados de série.</span><span class="sxs-lookup"><span data-stu-id="93cfb-195">The legend is automatically created from category and series data.</span></span>  
  
#### <a name="to-move-the-legend-below-the-chart-area-of-a-column-chart"></a><span data-ttu-id="93cfb-196">Para mover a legenda abaixo da área de gráfico de um gráfico de colunas</span><span class="sxs-lookup"><span data-stu-id="93cfb-196">To move the legend below the chart area of a column chart</span></span>  
  
1.  <span data-ttu-id="93cfb-197">Alterne para a exibição de design de relatório.</span><span class="sxs-lookup"><span data-stu-id="93cfb-197">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="93cfb-198">Clique com o botão direito do mouse na legenda no gráfico e clique em **Propriedades da legenda**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-198">Right-click the legend on the chart, and then click **Legend Properties**.</span></span>  
  
3.  <span data-ttu-id="93cfb-199">Em **layout e posição**, selecione uma posição diferente.</span><span class="sxs-lookup"><span data-stu-id="93cfb-199">For **Layout and Position**, select a different position.</span></span> <span data-ttu-id="93cfb-200">Por exemplo, defina a posição para a opção da metade inferior.</span><span class="sxs-lookup"><span data-stu-id="93cfb-200">For example, set the position to the middle bottom option.</span></span>  
  
     <span data-ttu-id="93cfb-201">Quando a legenda estiver posicionada na parte superior ou inferior de um gráfico, o layout da legenda será alterado de vertical para horizontal.</span><span class="sxs-lookup"><span data-stu-id="93cfb-201">When the legend is placed at the top or bottom of a chart, the layout of the legend changes from vertical to horizontal.</span></span> <span data-ttu-id="93cfb-202">Você pode selecionar um layout diferente na lista suspensa **Layout** .</span><span class="sxs-lookup"><span data-stu-id="93cfb-202">You can select a different layout from the **Layout** drop-down list.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="93cfb-203">(Opcional) Como há somente uma categoria neste tutorial, a legenda não é necessária.</span><span class="sxs-lookup"><span data-stu-id="93cfb-203">(Optional) Because there is only one category in this tutorial, the legend is not needed.</span></span> <span data-ttu-id="93cfb-204">Para remover a legenda, clique com o botão direito do mouse na legenda e clique em **excluir legenda**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-204">To remove the legend, right-click the legend and then click **Delete Legend**.</span></span>  
  
6.  <span data-ttu-id="93cfb-205">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="93cfb-205">Click **Run** to preview the report.</span></span>  
  
##  <a name="5-title-the-chart"></a><a name="ChartTitle"></a><span data-ttu-id="93cfb-206">5. título do gráfico</span><span class="sxs-lookup"><span data-stu-id="93cfb-206">5. Title the Chart</span></span>  
  
#### <a name="to-change-the-chart-title-above-the-chart-area"></a><span data-ttu-id="93cfb-207">Para alterar o título do gráfico acima da área do gráfico</span><span class="sxs-lookup"><span data-stu-id="93cfb-207">To change the chart title above the chart area</span></span>  
  
1.  <span data-ttu-id="93cfb-208">Alterne para a exibição de design de relatório.</span><span class="sxs-lookup"><span data-stu-id="93cfb-208">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="93cfb-209">Selecione as palavras **título do gráfico** na parte superior do gráfico e digite o seguinte texto: **armazenar totais da ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-209">Select the words **Chart Title** at the top of the chart, and then type the following text: **Store Sales Order Totals**.</span></span>  
  
3.  <span data-ttu-id="93cfb-210">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="93cfb-210">Click **Run** to preview the report.</span></span>  
  
##  <a name="6-format-and-label-the-vertical-axis"></a><a name="Vertical"></a><span data-ttu-id="93cfb-211">6. Formatar e rotular o eixo vertical</span><span class="sxs-lookup"><span data-stu-id="93cfb-211">6. Format and Label the Vertical Axis</span></span>  
 <span data-ttu-id="93cfb-212">Por padrão, o eixo vertical exibe valores em um formato geral que é dimensionado para ajustar o tamanho do gráfico automaticamente.</span><span class="sxs-lookup"><span data-stu-id="93cfb-212">By default, the vertical axis displays values in a general format that is automatically scaled to fit the size of the chart.</span></span>  
  
#### <a name="to-format-as-currency-the-numbers-on-the-vertical-axis"></a><span data-ttu-id="93cfb-213">Para formatar os números no eixo vertical como moeda</span><span class="sxs-lookup"><span data-stu-id="93cfb-213">To format as currency the numbers on the vertical axis</span></span>  
  
1.  <span data-ttu-id="93cfb-214">Alterne para a exibição de design de relatório.</span><span class="sxs-lookup"><span data-stu-id="93cfb-214">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="93cfb-215">Clique duas vezes nos rótulos no eixo vertical ao longo do gráfico para selecioná-los.</span><span class="sxs-lookup"><span data-stu-id="93cfb-215">Double-click the labels on the vertical axis along the side of the chart to select them.</span></span>  
  
3.  <span data-ttu-id="93cfb-216">Na faixa de faixas, na guia **início** , no grupo **número** , clique no botão **moeda** .</span><span class="sxs-lookup"><span data-stu-id="93cfb-216">On the ribbon, on the **Home** tab, in the **Number** group, click the **Currency** button.</span></span> <span data-ttu-id="93cfb-217">Os rótulos do eixo são alterados para mostrar o formato da moeda.</span><span class="sxs-lookup"><span data-stu-id="93cfb-217">The axis labels change to show the currency format.</span></span>  
  
4.  <span data-ttu-id="93cfb-218">Na faixa de faixas, na guia **início** , no grupo **número** , clique no botão **diminuir decimal** duas vezes para mostrar o número arredondado para o dólar mais próximo.</span><span class="sxs-lookup"><span data-stu-id="93cfb-218">On the ribbon, on the **Home** tab, in the **Number** group, click the **Decrease Decimal** button two times, to show the number rounded to the nearest dollar.</span></span>  
  
5.  <span data-ttu-id="93cfb-219">Clique com o botão direito do mouse no eixo vertical e clique em **Propriedades do eixo vertical**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-219">Right-click the vertical axis and click **Vertical Axis Properties**.</span></span>  
  
6.  <span data-ttu-id="93cfb-220">Clique em **Número**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-220">Click **Number**.</span></span> <span data-ttu-id="93cfb-221">Observe que a **moeda** já está selecionada na caixa **categoria** e as **casas decimais** já são **0** (zero).</span><span class="sxs-lookup"><span data-stu-id="93cfb-221">Note that **Currency** is already selected in the **Category** box, and **Decimal places** is already **0** (zero).</span></span>  
  
7.  <span data-ttu-id="93cfb-222">Na caixa **Mostrar valores em** , clique em **milhares**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-222">In the **Show Values in** box, click **Thousands**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="93cfb-223">Clique com o botão direito do mouse no título do eixo vertical ao lado do gráfico e clique em **Propriedades do título do eixo**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-223">Right-click the vertical axis title along the side of the chart and click **Axis Title Properties**.</span></span>  
  
10. <span data-ttu-id="93cfb-224">Substitua o texto no campo de **texto título** pelo seguinte texto: **vendas total (em milhares)**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-224">Replace the text in the **Title text** field with the following text: **Sales Total (in Thousands)**.</span></span> <span data-ttu-id="93cfb-225">Também é possível especificar várias opções relacionadas ao modo como o título é formatado.</span><span class="sxs-lookup"><span data-stu-id="93cfb-225">You can also specify a variety of options related to how the title is formatted.</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
12. <span data-ttu-id="93cfb-226">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="93cfb-226">Click **Run** to preview the report.</span></span>  
  
##  <a name="7-add-a-moving-average"></a><a name="Average"></a><span data-ttu-id="93cfb-227">7. adicionar uma média móvel</span><span class="sxs-lookup"><span data-stu-id="93cfb-227">7. Add a Moving Average</span></span>  
  
#### <a name="to-add-a-moving-average"></a><span data-ttu-id="93cfb-228">Para adicionar uma média móvel</span><span class="sxs-lookup"><span data-stu-id="93cfb-228">To add a moving average</span></span>  
  
1.  <span data-ttu-id="93cfb-229">Alterne para a exibição de design de relatório.</span><span class="sxs-lookup"><span data-stu-id="93cfb-229">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="93cfb-230">Clique duas vezes no gráfico para exibir o painel **Dados do Gráfico** .</span><span class="sxs-lookup"><span data-stu-id="93cfb-230">Double-click the chart to display the **Chart Data** pane.</span></span>  
  
3.  <span data-ttu-id="93cfb-231">Clique com o botão direito do mouse no campo **[Sum (Sales)]** que está na área **valores** e clique em **Adicionar série calculada**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-231">Right-click the **[Sum(Sales)]** field that is in the **Values** area, and then click **Add Calculated Series**.</span></span>  
  
4.  <span data-ttu-id="93cfb-232">Em **Fórmula**, verifique se a opção **Média móvel** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="93cfb-232">In **Formula**, verify that **Moving average** is selected.</span></span>  
  
5.  <span data-ttu-id="93cfb-233">Em **Definir Parâmetros da Fórmula**, em **Período**, selecione **4**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-233">In **Set Formula Parameters**, for **Period**, select **4**.</span></span>  
  
6.  <span data-ttu-id="93cfb-234">Clique em **borda**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-234">Click **Border**.</span></span>  
  
7.  <span data-ttu-id="93cfb-235">Em **largura da linha**, selecione **3PT**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-235">In **Line width**, select **3pt**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="93cfb-236">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="93cfb-236">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="93cfb-237">O gráfico exibe uma linha que mostra a média móvel para o total de vendas por data, a cada quatro datas.</span><span class="sxs-lookup"><span data-stu-id="93cfb-237">The chart displays a line that shows the moving average for total sales by date, averaged over every four dates.</span></span>  
  
##  <a name="8-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="93cfb-238">8. adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="93cfb-238">8. Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="93cfb-239">Para adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="93cfb-239">To add a report title</span></span>  
  
1.  <span data-ttu-id="93cfb-240">Alterne para a exibição de design de relatório.</span><span class="sxs-lookup"><span data-stu-id="93cfb-240">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="93cfb-241">Na superfície de design, clique em **Clique para adicionar título**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-241">On the design surface, click **Click to add title**.</span></span>  
  
3.  <span data-ttu-id="93cfb-242">Digite **gráfico de vendas**, pressione Enter e digite **janeiro a dezembro de 2009**, portanto, tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="93cfb-242">Type **Sales Chart**, press ENTER, and then type **January to December 2009**, so it looks like this:</span></span>  
  
     <span data-ttu-id="93cfb-243">**Gráfico de Vendas**</span><span class="sxs-lookup"><span data-stu-id="93cfb-243">**Sales Chart**</span></span>  
  
     <span data-ttu-id="93cfb-244">**Janeiro a dezembro de 2009**</span><span class="sxs-lookup"><span data-stu-id="93cfb-244">**January to December 2009**</span></span>  
  
4.  <span data-ttu-id="93cfb-245">Selecione **gráfico de vendas**e clique no **botão Negrito** na seção **fonte** na guia **página inicial** da faixa de opções.</span><span class="sxs-lookup"><span data-stu-id="93cfb-245">Select **Sales Chart**, and click the **Bold** button in the **Font** section on the **Home** tab of the ribbon.</span></span>  
  
5.  <span data-ttu-id="93cfb-246">Selecione **janeiro a dezembro de 2009**e, na **seção fonte** , na guia **início** , defina o tamanho da fonte como **10**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-246">Select **January to December 2009**, and in the **Font** section on the **Home** tab, set the font size to **10**.</span></span>  
  
6.  <span data-ttu-id="93cfb-247">Adicional Talvez seja necessário aumentar a altura da caixa de texto **título** para acomodar as duas linhas de texto puxando as setas de duas pontas ao clicar no meio da borda inferior.</span><span class="sxs-lookup"><span data-stu-id="93cfb-247">(Optional) You may need to make the **Title** text box taller to accommodate the two lines of text by pulling down on the double-headed arrows when you click in the middle of the bottom edge.</span></span>  
  
     <span data-ttu-id="93cfb-248">Esse título aparecerá na parte superior do relatório.</span><span class="sxs-lookup"><span data-stu-id="93cfb-248">This title will appear at the top of the report.</span></span> <span data-ttu-id="93cfb-249">Quando não houver nenhum cabeçalho de página definido, os itens na parte superior do corpo do relatório serão equivalentes a um cabeçalho de relatório.</span><span class="sxs-lookup"><span data-stu-id="93cfb-249">When there is no page header defined, items at the top of the report body are the equivalent of a report header.</span></span>  
  
7.  <span data-ttu-id="93cfb-250">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="93cfb-250">Click **Run** to preview the report.</span></span>  
  
##  <a name="9-save-the-report"></a><a name="Save"></a><span data-ttu-id="93cfb-251">9. salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="93cfb-251">9. Save the Report</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="93cfb-252">Para salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="93cfb-252">To save the report</span></span>  
  
1.  <span data-ttu-id="93cfb-253">Alterne para a exibição de design de relatório.</span><span class="sxs-lookup"><span data-stu-id="93cfb-253">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="93cfb-254">No botão Construtor de Relatórios , clique em **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-254">From the Report Builder button, click **Save As**.</span></span>  
  
3.  <span data-ttu-id="93cfb-255">Em **Nome**, digite **Gráfico de Colunas do Pedido de Vendas**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-255">In **Name**, type **Sales Order Column Chart**.</span></span>  
  
4.  <span data-ttu-id="93cfb-256">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="93cfb-256">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="93cfb-257">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="93cfb-257">Next Steps</span></span>  
 <span data-ttu-id="93cfb-258">Você concluiu com êxito o tutorial Adicionando um gráfico de colunas ao seu relatório.</span><span class="sxs-lookup"><span data-stu-id="93cfb-258">You have successfully completed the Adding a Column Chart to Your Report tutorial.</span></span> <span data-ttu-id="93cfb-259">Para saber mais sobre gráficos, consulte [Gráficos &#40;Construtor de Relatórios e SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) e [Minigráficos e barras de dados &#40;Construtor de Relatórios e SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="93cfb-259">To learn more about charts, see [Charts &#40;Report Builder and SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) and [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93cfb-260">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="93cfb-260">See Also</span></span>  
 <span data-ttu-id="93cfb-261">[TUTORIAIS &#40;Construtor de Relatórios&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="93cfb-261">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="93cfb-262">Construtor de Relatórios no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="93cfb-262">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
