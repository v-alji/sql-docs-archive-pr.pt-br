---
title: 'Tutorial: Adicionar um gráfico de barras ao relatório (Construtor de Relatórios) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6956ebd6-0217-4087-a4fa-5cc1c3804691
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 01708ca548c40118daa03fac34d8a323d628b012
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572365"
---
# <a name="tutorial-add-a-bar-chart-to-your-report-report-builder"></a><span data-ttu-id="34268-102">Tutorial: Adicionar um gráfico de barras ao relatório (Construtor de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="34268-102">Tutorial: Add a Bar Chart to Your Report (Report Builder)</span></span>
  <span data-ttu-id="34268-103">Um gráfico de barras exibe os dados de categoria horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="34268-103">A bar chart displays category data horizontally.</span></span> <span data-ttu-id="34268-104">Ele pode ajudar a:</span><span class="sxs-lookup"><span data-stu-id="34268-104">This can help to:</span></span>  
  
-   <span data-ttu-id="34268-105">Melhorar a legibilidade de nomes de categorias longos.</span><span class="sxs-lookup"><span data-stu-id="34268-105">Improve readability of long category names.</span></span>  
  
-   <span data-ttu-id="34268-106">Melhorar a capacidade de compreensão de tempos plotados como valores.</span><span class="sxs-lookup"><span data-stu-id="34268-106">Improve understandability of times plotted as values.</span></span>  
  
-   <span data-ttu-id="34268-107">Comparar o valor relativo de várias séries.</span><span class="sxs-lookup"><span data-stu-id="34268-107">Compare the relative value of multiple series.</span></span>  
  
 <span data-ttu-id="34268-108">A ilustração a seguir mostra o gráfico de barras que você criará, com as vendas em 2008 e 2009 dos cinco principais vendedores, em ordem alfabética.</span><span class="sxs-lookup"><span data-stu-id="34268-108">The following illustration shows the bar chart that you will create, with sales for 2008 and 2009 for the top five salespeople, in alphabetical order.</span></span>  
  
 <span data-ttu-id="34268-109">![rs_BarChartTutorial](../../2014/tutorials/media/rs-barcharttutorial.gif "rs_BarChartTutorial")</span><span class="sxs-lookup"><span data-stu-id="34268-109">![rs_BarChartTutorial](../../2014/tutorials/media/rs-barcharttutorial.gif "rs_BarChartTutorial")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="34268-110">O que você aprenderá</span><span class="sxs-lookup"><span data-stu-id="34268-110">What You Will Learn</span></span>  
 <span data-ttu-id="34268-111">Neste tutorial, você aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="34268-111">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="34268-112">Criar um gráfico no Assistente de Gráfico</span><span class="sxs-lookup"><span data-stu-id="34268-112">Create a Chart from the Chart Wizard</span></span>](#Chart)  
  
2.  [<span data-ttu-id="34268-113">Escolher o tipo de gráfico</span><span class="sxs-lookup"><span data-stu-id="34268-113">Choose the Chart Type</span></span>](#ChartType)  
  
3.  [<span data-ttu-id="34268-114">Exibir todos os valores de categoria no eixo vertical.</span><span class="sxs-lookup"><span data-stu-id="34268-114">Display all Category Values on the Vertical Axis</span></span>](#AllValues)  
  
4.  [<span data-ttu-id="34268-115">Modificar a exibição de nomes no eixo vertical</span><span class="sxs-lookup"><span data-stu-id="34268-115">Modify the Display of Names on the Vertical Axis</span></span>](#Sort)  
  
5.  [<span data-ttu-id="34268-116">Mover a legenda</span><span class="sxs-lookup"><span data-stu-id="34268-116">Move the Legend</span></span>](#Legend)  
  
6.  [<span data-ttu-id="34268-117">Mover o título do gráfico</span><span class="sxs-lookup"><span data-stu-id="34268-117">Move the Chart Title</span></span>](#ChartTitle)  
  
7.  [<span data-ttu-id="34268-118">Formatar e rotular o eixo horizontal</span><span class="sxs-lookup"><span data-stu-id="34268-118">Format and Label the Horizontal Axis</span></span>](#Horizontal)  
  
8.  [<span data-ttu-id="34268-119">Adicionar um filtro para exibir os cinco valores principais</span><span class="sxs-lookup"><span data-stu-id="34268-119">Add a Filter to Display the Top Five Values</span></span>](#Filter)  
  
9. [<span data-ttu-id="34268-120">Adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="34268-120">Add a Report Title</span></span>](#Title)  
  
10. [<span data-ttu-id="34268-121">Salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="34268-121">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="34268-122">Neste tutorial, as etapas do assistente são consolidadas em um procedimento.</span><span class="sxs-lookup"><span data-stu-id="34268-122">In this tutorial, the steps for the wizard are consolidated into one procedure.</span></span> <span data-ttu-id="34268-123">Para obter instruções passo a passo sobre como procurar um servidor de relatório, criar um conjunto de dados e escolher uma fonte de dados, consulte o primeiro tutorial desta série: [Tutorial: Criando um relatório de tabela básico &#40;Construtor de Relatórios&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="34268-123">For step-by-step instructions about how to browse to a report server, create a dataset, and choose a data source, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="34268-124">Tempo estimado para concluir este tutorial: 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="34268-124">Estimated time to complete this tutorial: 15 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34268-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="34268-125">Requirements</span></span>  
 <span data-ttu-id="34268-126">Para obter mais informações sobre os requisitos, consulte [Pré-requisitos para tutoriais &#40;Construtor de Relatórios&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="34268-126">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-chart-report-from-the-chart-wizard"></a><a name="Chart"></a><span data-ttu-id="34268-127">1. criar um relatório de gráfico do assistente de gráfico</span><span class="sxs-lookup"><span data-stu-id="34268-127">1. Create a Chart Report from the Chart Wizard</span></span>  
 <span data-ttu-id="34268-128">Na caixa de diálogo **introdução** , crie um conjunto de dados inserido, escolha uma fonte de dados compartilhada e crie um gráfico de barras usando o assistente de gráfico.</span><span class="sxs-lookup"><span data-stu-id="34268-128">From the **Getting Started** dialog box, create an embedded dataset, choose a shared data source, and create a bar chart by using the Chart Wizard.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="34268-129">Neste tutorial, como contém os valores de dados, a consulta não precisa de uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="34268-129">In this tutorial, the query contains the data values so that it does not need an external data source.</span></span> <span data-ttu-id="34268-130">Isso torna a consulta bastante longa.</span><span class="sxs-lookup"><span data-stu-id="34268-130">This makes the query quite long.</span></span> <span data-ttu-id="34268-131">Em um ambiente empresarial, uma consulta não conteria os dados.</span><span class="sxs-lookup"><span data-stu-id="34268-131">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="34268-132">Isso é apenas para fins de aprendizado.</span><span class="sxs-lookup"><span data-stu-id="34268-132">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-chart-report"></a><span data-ttu-id="34268-133">Para criar um novo relatório de gráfico</span><span class="sxs-lookup"><span data-stu-id="34268-133">To create a new chart report</span></span>  
  
1.  <span data-ttu-id="34268-134">Clique em **Iniciar**, aponte para **Programas**, para **Construtor de Relatórios do Microsoft SQL Server 2012**e clique em **Construtor de Relatórios**.</span><span class="sxs-lookup"><span data-stu-id="34268-134">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="34268-135">A caixa de diálogo **introdução** é exibida.</span><span class="sxs-lookup"><span data-stu-id="34268-135">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="34268-136">Se a caixa de diálogo **introdução** não for exibida, clique no botão Construtor de relatórios e, em seguida, clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="34268-136">If the **Getting Started** dialog box does not appear, click the Report Builder button, and then click **New**.</span></span>  
  
2.  <span data-ttu-id="34268-137">No painel esquerdo, verifique se **Novo Relatório** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="34268-137">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="34268-138">No painel direito, clique em **Assistente de Gráfico**.</span><span class="sxs-lookup"><span data-stu-id="34268-138">In the right pane, click **Chart Wizard**.</span></span>  
  
4.  <span data-ttu-id="34268-139">Na página **Escolher um conjunto de dados** , clique em **Criar um conjunto de dados**e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="34268-139">On the **Choose a dataset** page, click **Create a dataset**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="34268-140">Na página **Escolher uma conexão com uma fonte de dados** , selecione uma fonte de dados existente ou procure o servidor de relatório, selecione uma fonte de dados e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="34268-140">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source, and then click **Next**.</span></span> <span data-ttu-id="34268-141">Talvez seja necessário inserir um nome de usuário e uma senha.</span><span class="sxs-lookup"><span data-stu-id="34268-141">You may need to enter a user name and password.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="34268-142">A fonte de dados escolhida não tem importância, contanto que você tenha permissões suficientes.</span><span class="sxs-lookup"><span data-stu-id="34268-142">The data source you choose is unimportant, as long as you have adequate permissions.</span></span> <span data-ttu-id="34268-143">Você não obterá dados da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="34268-143">You will not be getting data from the data source.</span></span> <span data-ttu-id="34268-144">Para obter mais informações, consulte [Formas alternativas de obter uma conexão de dados &#40;Construtor de Relatórios&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="34268-144">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
6.  <span data-ttu-id="34268-145">Na página **Crie uma consulta** , clique em **Editar como Texto**.</span><span class="sxs-lookup"><span data-stu-id="34268-145">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
7.  <span data-ttu-id="34268-146">Cole a seguinte consulta no painel de consulta:</span><span class="sxs-lookup"><span data-stu-id="34268-146">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT 'Luis' as FirstName, 'Alverca' as LastName, CAST(170000.00 AS money) AS SalesYear2009, CAST(150000. AS money) AS SalesYear2008  
    UNION SELECT 'Jeffrey' as FirstName, 'Zeng' as LastName, CAST(210000. AS money) AS SalesYear2009, CAST(190000. AS money) AS SalesYear2008  
    UNION SELECT 'Houman' as FirstName, 'Pournasseh' as LastName, CAST(150000. AS money) AS SalesYear2009, CAST(180000. AS money) AS SalesYear2008  
    UNION SELECT 'Robin' as FirstName, 'Wood' as LastName, CAST(75000. AS money) AS SalesYear2009, CAST(175000. AS money) AS SalesYear2008  
    UNION SELECT 'Daniela' as FirstName, 'Guaita' as LastName,  CAST(170000. AS money) AS SalesYear2009, CAST(175000. AS money) AS SalesYear2008  
    UNION SELECT 'John' as FirstName, 'Yokim' as LastName, CAST(160000. AS money) AS SalesYear2009, CAST(195000. AS money) AS SalesYear2008  
    UNION SELECT 'Delphine' as FirstName, 'Ribaute' as LastName, CAST(180000. AS money) AS SalesYear2009, CAST(205000. AS money) AS SalesYear2008  
    UNION SELECT 'Robert' as FirstName, 'Hernady' as LastName, CAST(140000. AS money) AS SalesYear2009, CAST(180000. AS money) AS SalesYear2008  
    UNION SELECT 'Tanja' as FirstName, 'Plate' as LastName, CAST(150000. AS money) AS SalesYear2009, CAST(160000. AS money) AS SalesYear2008  
    UNION SELECT 'David' as FirstName, 'Bradley' as LastName, CAST(210000. AS money) AS SalesYear2009, CAST(180000. AS money) AS SalesYear2008  
    UNION SELECT 'Michal' as FirstName, 'Jaworski' as LastName, CAST(175000. AS money) AS SalesYear2009, CAST(220000. AS money) AS SalesYear2008  
    UNION SELECT 'Chris' as FirstName, 'Ashton' as LastName, CAST(195000. AS money) AS SalesYear2009, CAST(205000. AS money) AS SalesYear2008  
    UNION SELECT 'Pongsiri' as FirstName, 'Hirunyanitiwatna' as LastName, CAST(175000. AS money) AS SalesYear2009, CAST(215000. AS money) AS SalesYear2008  
    UNION SELECT 'Brian' as FirstName, 'Burke' as LastName, CAST(187000. AS money) AS SalesYear2009, CAST(207000. AS money) AS SalesYear2008  
    ```  
  
8.  <span data-ttu-id="34268-147">(Opcional) Clique no botão Executar (**!**) para ver os dados em que o gráfico se baseará.</span><span class="sxs-lookup"><span data-stu-id="34268-147">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>  
  
9. <span data-ttu-id="34268-148">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="34268-148">Click **Next**.</span></span>  
  
##  <a name="2-choose-the-chart-type"></a><a name="ChartType"></a><span data-ttu-id="34268-149">2. escolher o tipo de gráfico</span><span class="sxs-lookup"><span data-stu-id="34268-149">2. Choose the Chart Type</span></span>  
 <span data-ttu-id="34268-150">Você pode escolher um dos diversos tipos de gráfico predefinidos.</span><span class="sxs-lookup"><span data-stu-id="34268-150">You can choose from a variety of predefined chart types.</span></span>  
  
#### <a name="to-add-a-column-chart"></a><span data-ttu-id="34268-151">Para adicionar um gráfico de colunas</span><span class="sxs-lookup"><span data-stu-id="34268-151">To add a column chart</span></span>  
  
1.  <span data-ttu-id="34268-152">Na página **Escolher um tipo de gráfico** , o gráfico de colunas é o tipo de gráfico padrão.</span><span class="sxs-lookup"><span data-stu-id="34268-152">On the **Choose a chart type** page, the column chart is the default chart type.</span></span>  
  
2.  <span data-ttu-id="34268-153">Clique em **Barra**e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="34268-153">Click **Bar**, and then click **Next**.</span></span>  
  
     <span data-ttu-id="34268-154">Na página **organizar campos de gráfico** , há quatro campos no painel **campos disponíveis** : FirstName, LastName, SalesYear2009 e SalesYear2008.</span><span class="sxs-lookup"><span data-stu-id="34268-154">On the **Arrange chart fields** page, there are four fields in the **Available fields** pane: FirstName, LastName, SalesYear2009, and SalesYear2008.</span></span>  
  
3.  <span data-ttu-id="34268-155">Arraste LastName para o painel Categorias.</span><span class="sxs-lookup"><span data-stu-id="34268-155">Drag LastName to the Categories pane.</span></span>  
  
4.  <span data-ttu-id="34268-156">Arraste SalesYear2009 para o painel Valores.</span><span class="sxs-lookup"><span data-stu-id="34268-156">Drag SalesYear2009 to the Values pane.</span></span> <span data-ttu-id="34268-157">SalesYear2009 representa o valor das vendas daquele vendedor no ano de 2009.</span><span class="sxs-lookup"><span data-stu-id="34268-157">SalesYear2009 represents the sales amount for each salesperson for the year 2009.</span></span> <span data-ttu-id="34268-158">O painel Valores exibe `[Sum(SalesYear2009)]` porque o gráfico exibe a agregação de cada produto.</span><span class="sxs-lookup"><span data-stu-id="34268-158">The Values pane displays `[Sum(SalesYear2009)]` because the chart displays the aggregate for each product.</span></span>  
  
5.  <span data-ttu-id="34268-159">Arraste SalesYear2008 para o painel Valores em SalesYear2009.</span><span class="sxs-lookup"><span data-stu-id="34268-159">Drag SalesYear2008 to the Values pane under SalesYear2009.</span></span> <span data-ttu-id="34268-160">SalesYear2008 representa o valor das vendas daquele vendedor no ano de 2008.</span><span class="sxs-lookup"><span data-stu-id="34268-160">SalesYear2008 represents the sales amount for each salesperson for the year 2008.</span></span>  
  
6.  <span data-ttu-id="34268-161">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="34268-161">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="34268-162">Na página **escolher um estilo** , no painel estilos, selecione um estilo.</span><span class="sxs-lookup"><span data-stu-id="34268-162">On the **Choose a style** page, in the Styles pane, select a style.</span></span>  
  
     <span data-ttu-id="34268-163">Um estilo especifica um estilo de fonte, um conjunto de cores e um estilo de borda.</span><span class="sxs-lookup"><span data-stu-id="34268-163">A style specifies a font style, a set of colors, and a border style.</span></span> <span data-ttu-id="34268-164">Quando você selecionar um estilo, o painel Visualizar exibirá um exemplo do gráfico com esse estilo.</span><span class="sxs-lookup"><span data-stu-id="34268-164">When you select a style, the Preview pane displays a sample of the chart with that style.</span></span>  
  
8.  <span data-ttu-id="34268-165">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="34268-165">Click **Finish**.</span></span>  
  
     <span data-ttu-id="34268-166">O gráfico é adicionado à superfície de design.</span><span class="sxs-lookup"><span data-stu-id="34268-166">The chart is added to the design surface.</span></span>  
  
9. <span data-ttu-id="34268-167">Clique no gráfico para exibir suas alças.</span><span class="sxs-lookup"><span data-stu-id="34268-167">Click the chart to display the chart handles.</span></span> <span data-ttu-id="34268-168">Arraste o canto inferior direito do gráfico para aumentar o tamanho do gráfico.</span><span class="sxs-lookup"><span data-stu-id="34268-168">Drag the bottom-right corner of the chart to increase the size of the chart.</span></span>  
  
10. <span data-ttu-id="34268-169">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="34268-169">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="34268-170">O relatório exibe o gráfico de barras para as vendas de cada vendedor nos anos de 2008 e 2009.</span><span class="sxs-lookup"><span data-stu-id="34268-170">The report displays the bar chart for sales for each sales person for the years 2008 and 2009.</span></span> <span data-ttu-id="34268-171">O comprimento da barra corresponde ao total de vendas.</span><span class="sxs-lookup"><span data-stu-id="34268-171">The length of the bar corresponds to the sales total.</span></span>  
  
##  <a name="3-modify-the-display-of-names-on-the-vertical-axis"></a><a name="AllValues"></a><span data-ttu-id="34268-172">3. modificar a exibição de nomes no eixo vertical</span><span class="sxs-lookup"><span data-stu-id="34268-172">3. Modify the Display of Names on the Vertical Axis</span></span>  
 <span data-ttu-id="34268-173">Por padrão, apenas alguns valores no eixo vertical são exibidos.</span><span class="sxs-lookup"><span data-stu-id="34268-173">By default, only some of the values on the vertical axis appear.</span></span> <span data-ttu-id="34268-174">É possível alterar o gráfico para exibir todas as categorias.</span><span class="sxs-lookup"><span data-stu-id="34268-174">You can change the chart to display all categories.</span></span>  
  
#### <a name="to-display-all-sales-persons-along-the-category-axis-of-a-bar-chart"></a><span data-ttu-id="34268-175">Para exibir todas as pessoas de vendas junto com o eixo da categoria de um gráfico de barras</span><span class="sxs-lookup"><span data-stu-id="34268-175">To display all sales persons along the category axis of a bar chart</span></span>  
  
1.  <span data-ttu-id="34268-176">Alterne para a exibição de design de relatório.</span><span class="sxs-lookup"><span data-stu-id="34268-176">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="34268-177">Clique com o botão direito do mouse no eixo vertical e clique em **Propriedades do eixo vertical**.</span><span class="sxs-lookup"><span data-stu-id="34268-177">Right-click the vertical axis, and then click **Vertical Axis Properties**.</span></span>  
  
3.  <span data-ttu-id="34268-178">Em **Alcance e intervalo do eixo**, na caixa **Intervalo** , digite **1**.</span><span class="sxs-lookup"><span data-stu-id="34268-178">Under **Axis range and interval**, in the **Interval** box, type **1**.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="34268-179">Clique com o botão direito do mouse no **título do eixo** vertical e desmarque a caixa de seleção **Mostrar título do eixo** .</span><span class="sxs-lookup"><span data-stu-id="34268-179">Right-click the vertical **Axis Title** and clear the **Show Axis Title** check box.</span></span>  
  
6.  <span data-ttu-id="34268-180">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="34268-180">Click **Run** to preview the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="34268-181">Se você não conseguir ler os nomes dos vendedores no eixo vertical, poderá aumentar o tamanho do gráfico ou alterar as opções de formatação dos rótulos do eixo.</span><span class="sxs-lookup"><span data-stu-id="34268-181">If you cannot read the salesperson names on the vertical axis, you can make your chart taller or change the formatting options for the axis labels.</span></span>  
  
###  <a name="display-last-name-and-first-name-on-vertical-axis"></a><a name="CategoryExpression"></a><span data-ttu-id="34268-182">Exibir sobrenome e nome no eixo vertical</span><span class="sxs-lookup"><span data-stu-id="34268-182">Display Last Name and First Name on Vertical Axis</span></span>  
 <span data-ttu-id="34268-183">Você pode alterar a expressão de categoria para incluir o sobrenome seguido do nome de cada vendedor.</span><span class="sxs-lookup"><span data-stu-id="34268-183">You can change the category expression to include last name followed by first name of each sales person.</span></span>  
  
##### <a name="to-change-the-category-expression"></a><span data-ttu-id="34268-184">Para alterar a expressão de categoria</span><span class="sxs-lookup"><span data-stu-id="34268-184">To change the category expression</span></span>  
  
1.  <span data-ttu-id="34268-185">Alterne para a exibição de design de relatório.</span><span class="sxs-lookup"><span data-stu-id="34268-185">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="34268-186">Clique duas vezes no gráfico para exibir o painel **Dados do Gráfico** .</span><span class="sxs-lookup"><span data-stu-id="34268-186">Double-click the chart to display the **Chart Data** pane.</span></span>  
  
3.  <span data-ttu-id="34268-187">Na área **Grupos de Categorias** , clique com o botão direito do mouse em [LastName] e clique em **Propriedades do Grupo de Categorias**.</span><span class="sxs-lookup"><span data-stu-id="34268-187">In the **Category Groups** area, right-click [LastName], and then click **Category Group Properties**.</span></span>  
  
4.  <span data-ttu-id="34268-188">Em Rótulo, clique no botão de expressão (Fx).</span><span class="sxs-lookup"><span data-stu-id="34268-188">In Label, click the expression (Fx) button.</span></span>  
  
5.  <span data-ttu-id="34268-189">Digite a seguinte expressão: `=Fields!LastName.Value & ", " & Fields!FirstName.Value`</span><span class="sxs-lookup"><span data-stu-id="34268-189">Type the following expression: `=Fields!LastName.Value & ", " & Fields!FirstName.Value`</span></span>  
  
     <span data-ttu-id="34268-190">Essa expressão concatena o sobrenome, uma vírgula e o nome.</span><span class="sxs-lookup"><span data-stu-id="34268-190">This expression concatenates the last name, a comma, and the first name.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="34268-191">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="34268-191">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="34268-192">Se os nomes não aparecerem ao executar o relatório, você poderá atualizar os dados manualmente.</span><span class="sxs-lookup"><span data-stu-id="34268-192">If the first names do not appear when you run the report, you can refresh the data manually.</span></span> <span data-ttu-id="34268-193">Enquanto estiver no modo de visualização, na guia **Executar** , no grupo **Navegação** , clique em **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="34268-193">While still in preview mode, on the **Run** tab in the **Navigation** group, click **Refresh**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="34268-194">Se você não conseguir ler os nomes dos vendedores no eixo vertical, poderá aumentar o tamanho do gráfico ou alterar as opções de formatação dos rótulos do eixo.</span><span class="sxs-lookup"><span data-stu-id="34268-194">If you cannot read the salesperson names on the vertical axis, you can make your chart taller or change the formatting options for the axis labels.</span></span>  
  
##  <a name="4-change-the-sort-order-for-names-on-the-vertical-axis"></a><a name="Sort"></a><span data-ttu-id="34268-195">4. alterar a ordem de classificação dos nomes no eixo vertical</span><span class="sxs-lookup"><span data-stu-id="34268-195">4. Change the Sort Order for Names on the Vertical Axis</span></span>  
 <span data-ttu-id="34268-196">Quando você classifica dados em um gráfico, está alterando a ordem de valores no eixo de categoria.</span><span class="sxs-lookup"><span data-stu-id="34268-196">When you sort the data on a chart, you are changing the order of values on the category axis.</span></span>  
  
#### <a name="to-sort-the-names-in-alphabetical-order-on-the-bar-chart"></a><span data-ttu-id="34268-197">Para classificar os nomes em ordem alfabética no gráfico de barras</span><span class="sxs-lookup"><span data-stu-id="34268-197">To sort the names in alphabetical order on the bar chart</span></span>  
  
1.  <span data-ttu-id="34268-198">Alterne para a exibição de design de relatório.</span><span class="sxs-lookup"><span data-stu-id="34268-198">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="34268-199">Clique duas vezes no gráfico para exibir o painel **Dados do Gráfico** .</span><span class="sxs-lookup"><span data-stu-id="34268-199">Double-click the chart to display the **Chart Data** pane.</span></span>  
  
3.  <span data-ttu-id="34268-200">Na área **Grupos de Categorias** , clique com o botão direito do mouse em [LastName] e clique em **Propriedades do Grupo de Categorias**.</span><span class="sxs-lookup"><span data-stu-id="34268-200">In the **Category Groups** area, right-click [LastName], and then click **Category Group Properties**.</span></span>  
  
4.  <span data-ttu-id="34268-201">Clique em **Classificar**.</span><span class="sxs-lookup"><span data-stu-id="34268-201">Click **Sorting**.</span></span> <span data-ttu-id="34268-202">A página **Alterar opções de classificação** exibe uma lista de expressões de classificação.</span><span class="sxs-lookup"><span data-stu-id="34268-202">The **Change sorting options** page displays a list of sort expressions.</span></span> <span data-ttu-id="34268-203">Por padrão, essa lista contém uma expressão de classificação que é igual à expressão do grupo de categorias original.</span><span class="sxs-lookup"><span data-stu-id="34268-203">By default, this list has one sort expression that is the same as the original category group expression.</span></span>  
  
5.  <span data-ttu-id="34268-204">Em classificar por, clique no botão expressão (**FX**).</span><span class="sxs-lookup"><span data-stu-id="34268-204">In Sort by, click the expression (**Fx**) button.</span></span>  
  
6.  <span data-ttu-id="34268-205">Digite a seguinte expressão: `=Fields!LastName.Value & ", " & Fields!FirstName.Value`</span><span class="sxs-lookup"><span data-stu-id="34268-205">Type the following expression: `=Fields!LastName.Value & ", " & Fields!FirstName.Value`</span></span>  
  
7.  <span data-ttu-id="34268-206">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="34268-206">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="34268-207">De volta à página **Propriedades do grupo de categorias** , na lista suspensa **ordem** , selecione **Z a a**. Isso seleciona ordem alfabética inversa para que os nomes apareçam na ordem de cima para baixo.</span><span class="sxs-lookup"><span data-stu-id="34268-207">Back on the **Category Group Properties** page, in the **Order** drop-down list, select **Z to A**. This selects reverse alphabetical order so that the names appear in order from top to bottom.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="34268-208">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="34268-208">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="34268-209">Os nomes no eixo horizontal são classificados em ordem inversa, com **Alerca** na parte superior e **Zeng** na parte inferior.</span><span class="sxs-lookup"><span data-stu-id="34268-209">The names on the horizontal axis are sorted in reverse order, with **Alerca** at the top and **Zeng** at the bottom.</span></span>  
  
##  <a name="5-move-the-legend"></a><a name="Legend"></a><span data-ttu-id="34268-210">5. mover a legenda</span><span class="sxs-lookup"><span data-stu-id="34268-210">5. Move the Legend</span></span>  
 <span data-ttu-id="34268-211">Para melhorar a capacidade de leitura dos valores do gráfico, mova a legenda do gráfico.</span><span class="sxs-lookup"><span data-stu-id="34268-211">To improve the readability of the chart values, you might want to move the chart legend.</span></span> <span data-ttu-id="34268-212">Por exemplo, em um gráfico de barras no qual as barras são mostradas na horizontal, você pode alterar a posição da legenda para que ela fique acima ou abaixo da área do gráfico.</span><span class="sxs-lookup"><span data-stu-id="34268-212">For example, in a bar chart where bars are shown horizontally, you can change the position of the legend so that it is above or below the chart area.</span></span> <span data-ttu-id="34268-213">Isso dá mais espaço na horizontal às barras.</span><span class="sxs-lookup"><span data-stu-id="34268-213">This gives more horizontal space to the bars.</span></span>  
  
#### <a name="to-display-the-legend-below-the-chart-area-of-a-bar-chart"></a><span data-ttu-id="34268-214">Para exibir a legenda abaixo da área de gráfico de um gráfico de barras</span><span class="sxs-lookup"><span data-stu-id="34268-214">To display the legend below the chart area of a bar chart</span></span>  
  
1.  <span data-ttu-id="34268-215">Alterne para a exibição de design de relatório.</span><span class="sxs-lookup"><span data-stu-id="34268-215">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="34268-216">Clique com o botão direito do mouse na legenda no gráfico.</span><span class="sxs-lookup"><span data-stu-id="34268-216">Right-click the legend on the chart.</span></span>  
  
3.  <span data-ttu-id="34268-217">Selecione **Propriedades da Legenda**.</span><span class="sxs-lookup"><span data-stu-id="34268-217">Select **Legend Properties**.</span></span>  
  
4.  <span data-ttu-id="34268-218">Em **Posição da legenda**, selecione uma posição diferente.</span><span class="sxs-lookup"><span data-stu-id="34268-218">For **Legend position**, select a different position.</span></span> <span data-ttu-id="34268-219">Por exemplo, defina a posição para a opção da metade inferior.</span><span class="sxs-lookup"><span data-stu-id="34268-219">For example, set the position to the middle bottom option.</span></span>  
  
     <span data-ttu-id="34268-220">Quando a legenda estiver posicionada na parte superior ou inferior de um gráfico, o layout da legenda será alterado de vertical para horizontal.</span><span class="sxs-lookup"><span data-stu-id="34268-220">When the legend is placed at the top or bottom of a chart, the layout of the legend changes from vertical to horizontal.</span></span> <span data-ttu-id="34268-221">Você pode selecionar um layout diferente na lista suspensa **Layout** .</span><span class="sxs-lookup"><span data-stu-id="34268-221">You can select a different layout from the **Layout** drop-down list.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="34268-222">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="34268-222">Click **Run** to preview the report.</span></span>  
  
##  <a name="6-title-the-chart"></a><a name="ChartTitle"></a><span data-ttu-id="34268-223">6. título do gráfico</span><span class="sxs-lookup"><span data-stu-id="34268-223">6. Title the Chart</span></span>  
  
#### <a name="to-change-the-chart-title-above-the-chart-area-of-a-bar-chart"></a><span data-ttu-id="34268-224">Para alterar o título do gráfico acima da área de gráfico de um gráfico de barras</span><span class="sxs-lookup"><span data-stu-id="34268-224">To change the chart title above the chart area of a bar chart</span></span>  
  
1.  <span data-ttu-id="34268-225">Alterne para a exibição de design de relatório.</span><span class="sxs-lookup"><span data-stu-id="34268-225">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="34268-226">Selecione as palavras **título do gráfico** na parte superior do gráfico e digite o seguinte texto: **vendas para 2008 e 2009**.</span><span class="sxs-lookup"><span data-stu-id="34268-226">Select the words **Chart Title** at the top of the chart, and then type the following text: **Sales for 2008 and 2009**.</span></span>  
  
3.  <span data-ttu-id="34268-227">Clique em qualquer ponto fora do texto.</span><span class="sxs-lookup"><span data-stu-id="34268-227">Click anywhere outside the text.</span></span>  
  
4.  <span data-ttu-id="34268-228">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="34268-228">Click **Run** to preview the report.</span></span>  
  
##  <a name="7-format-and-label-the-horizontal-axis"></a><a name="Horizontal"></a><span data-ttu-id="34268-229">7. Formatar e rotular o eixo horizontal</span><span class="sxs-lookup"><span data-stu-id="34268-229">7. Format and Label the Horizontal Axis</span></span>  
 <span data-ttu-id="34268-230">Por padrão, o eixo horizontal exibe valores em um formato geral que é dimensionado para ajustar o tamanho do gráfico automaticamente.</span><span class="sxs-lookup"><span data-stu-id="34268-230">By default, the horizontal axis displays values in a general format that is automatically scaled to fit the size of the chart.</span></span>  
  
#### <a name="to-format-the-numbers-on-the-horizontal-axis"></a><span data-ttu-id="34268-231">Para formatar os números no eixo horizontal</span><span class="sxs-lookup"><span data-stu-id="34268-231">To format the numbers on the horizontal axis</span></span>  
  
1.  <span data-ttu-id="34268-232">Alterne para a exibição de design de relatório.</span><span class="sxs-lookup"><span data-stu-id="34268-232">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="34268-233">Clique no eixo horizontal ao longo da parte inferior do gráfico para selecioná-lo.</span><span class="sxs-lookup"><span data-stu-id="34268-233">Click the horizontal axis along the bottom of the chart to select it.</span></span>  
  
     <span data-ttu-id="34268-234">Na faixa de faixas, na guia **início** , no grupo **número** , clique no botão **moeda** .</span><span class="sxs-lookup"><span data-stu-id="34268-234">On the ribbon, on the **Home** tab, in the **Number** group, click the **Currency** button.</span></span> <span data-ttu-id="34268-235">Os rótulos do eixo horizontal são alterados para moeda.</span><span class="sxs-lookup"><span data-stu-id="34268-235">The horizontal axis labels change to currency.</span></span>  
  
3.  <span data-ttu-id="34268-236">(Opcional) Remova os dígitos decimais.</span><span class="sxs-lookup"><span data-stu-id="34268-236">(Optional) Remove the decimal digits.</span></span> <span data-ttu-id="34268-237">Próximo ao botão **Moeda** , clique no botão **Diminuir Decimal** duas vezes.</span><span class="sxs-lookup"><span data-stu-id="34268-237">Near the **Currency** button, click the **Decrease Decimal** button twice.</span></span>  
  
4.  <span data-ttu-id="34268-238">Clique com o botão direito do mouse no eixo horizontal e clique em **Propriedades do Eixo Horizontal**.</span><span class="sxs-lookup"><span data-stu-id="34268-238">Right-click the horizontal axis, and click **Horizontal Axis Properties**.</span></span>  
  
5.  <span data-ttu-id="34268-239">Na guia **número** , selecione **Mostrar valores em milhares.**</span><span class="sxs-lookup"><span data-stu-id="34268-239">On the **Number** tab, select **Show values in Thousands.**</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="34268-240">Clique com botão direito do mouse em **título do eixo** e clique em Propriedades do **título do eixo**.</span><span class="sxs-lookup"><span data-stu-id="34268-240">Right-click **Axis Title** and click **Axis Title Properties**.</span></span>  
  
8.  <span data-ttu-id="34268-241">Na caixa de **texto título** , digite **vendas em milhares** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="34268-241">In the **Title text** box, type **Sales in thousands** and click **OK**.</span></span>  
  
9. <span data-ttu-id="34268-242">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="34268-242">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="34268-243">O relatório exibe a quantidade de vendas no eixo horizontal como moeda em milhares, sem dígitos decimais.</span><span class="sxs-lookup"><span data-stu-id="34268-243">The report displays the sales amount on the horizontal axis as currency in thousands, and has no decimal digits.</span></span>  
  
##  <a name="8-add-a-filter-to-display-the-top-five-values"></a><a name="Filter"></a><span data-ttu-id="34268-244">8. adicionar um filtro para exibir os cinco valores principais</span><span class="sxs-lookup"><span data-stu-id="34268-244">8. Add a Filter to Display the Top Five Values</span></span>  
 <span data-ttu-id="34268-245">Você pode adicionar um filtro ao gráfico para especificar os dados do conjunto de dados a serem incluídos ou excluídos no gráfico.</span><span class="sxs-lookup"><span data-stu-id="34268-245">You can add a filter to the chart to specify which data from the dataset to include or exclude in the chart.</span></span>  
  
#### <a name="to-add-a-filter-and-display-the-top-five-values"></a><span data-ttu-id="34268-246">Para adicionar um filtro e exibir os cinco valores principais</span><span class="sxs-lookup"><span data-stu-id="34268-246">To add a filter and display the top five values</span></span>  
  
1.  <span data-ttu-id="34268-247">Alterne para a exibição de design de relatório.</span><span class="sxs-lookup"><span data-stu-id="34268-247">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="34268-248">Clique duas vezes no gráfico para exibir o painel **Dados do Gráfico** .</span><span class="sxs-lookup"><span data-stu-id="34268-248">Double-click the chart to display the **Chart Data** pane.</span></span>  
  
3.  <span data-ttu-id="34268-249">Na área **Grupos de Categorias** , clique com o botão direito do mouse no campo [LastName] e clique em **Propriedades do Grupo de Categorias**.</span><span class="sxs-lookup"><span data-stu-id="34268-249">In the **Category Groups** area, right-click the [LastName] field, and then click **Category Group Properties**.</span></span>  
  
4.  <span data-ttu-id="34268-250">Clique em **Filtros**.</span><span class="sxs-lookup"><span data-stu-id="34268-250">Click **Filters**.</span></span> <span data-ttu-id="34268-251">A página **Alterar filtros** pode exibir uma lista de expressões de filtro.</span><span class="sxs-lookup"><span data-stu-id="34268-251">The **Change filters** page can display a list of filter expressions.</span></span> <span data-ttu-id="34268-252">Por padrão, essa lista está vazia.</span><span class="sxs-lookup"><span data-stu-id="34268-252">By default, this list is empty.</span></span>  
  
5.  <span data-ttu-id="34268-253">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="34268-253">Click **Add**.</span></span> <span data-ttu-id="34268-254">Um novo filtro em branco é exibido.</span><span class="sxs-lookup"><span data-stu-id="34268-254">A new blank filter appears.</span></span>  
  
6.  <span data-ttu-id="34268-255">Em **expressão**, digite **[Sum (SalesYear2009)]**.</span><span class="sxs-lookup"><span data-stu-id="34268-255">In **Expression**, type **[Sum(SalesYear2009)]**.</span></span> <span data-ttu-id="34268-256">Esse procedimento cria a expressão subjacente `=Sum(Fields!SalesYear2009.Value)`, que poderá ser vista se você clicar no botão **fx** .</span><span class="sxs-lookup"><span data-stu-id="34268-256">This creates the underlying expression `=Sum(Fields!SalesYear2009.Value)`, which you can see if you click the **fx** button.</span></span>  
  
7.  <span data-ttu-id="34268-257">Verifique se o tipo de dados é **Text**.</span><span class="sxs-lookup"><span data-stu-id="34268-257">Verify that the data type is **Text**.</span></span>  
  
8.  <span data-ttu-id="34268-258">Em **Operador**, selecione **N Superior** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="34268-258">In **Operator**, select **Top N** from the drop-down list.</span></span>  
  
9. <span data-ttu-id="34268-259">Em **Valor**, digite a seguinte expressão: **=5**</span><span class="sxs-lookup"><span data-stu-id="34268-259">In **Value**, type the following expression: **=5**</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
11. <span data-ttu-id="34268-260">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="34268-260">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="34268-261">Se os resultados não forem filtrados ao executar o relatório, você poderá atualizar os dados manualmente.</span><span class="sxs-lookup"><span data-stu-id="34268-261">If the results are not filtered when you run the report, you can refresh the data manually.</span></span> <span data-ttu-id="34268-262">Na guia **Executar** do grupo **Navegação** , clique em **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="34268-262">On the **Run** tab in the **Navigation** group, click **Refresh**.</span></span>  
  
 <span data-ttu-id="34268-263">O gráfico exibe os cinco nomes de vendedores principais dos dados de vendas de 2009.</span><span class="sxs-lookup"><span data-stu-id="34268-263">The chart shows the top five salesperson names from the 2009 sales data.</span></span>  
  
##  <a name="9-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="34268-264">9. adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="34268-264">9. Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="34268-265">Para adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="34268-265">To add a report title</span></span>  
  
1.  <span data-ttu-id="34268-266">Na superfície de design, clique em **Clique para adicionar título**.</span><span class="sxs-lookup"><span data-stu-id="34268-266">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="34268-267">Digite **gráfico de barras de vendas**, pressione Enter e digite os **cinco principais vendedores para 2009**, portanto, tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="34268-267">Type **Sales Bar Chart**, press ENTER, and then type **Top Five Sellers for 2009**, so it looks like this:</span></span>  
  
     <span data-ttu-id="34268-268">**Gráfico de Barras de Vendas**</span><span class="sxs-lookup"><span data-stu-id="34268-268">**Sales Bar Chart**</span></span>  
  
     <span data-ttu-id="34268-269">**Cinco Principais Vendedores de 2009**</span><span class="sxs-lookup"><span data-stu-id="34268-269">**Top Five Sellers for 2009**</span></span>  
  
3.  <span data-ttu-id="34268-270">Selecione **Gráfico de Barras de Vendas**e clique no botão **Negrito** .</span><span class="sxs-lookup"><span data-stu-id="34268-270">Select **Sales Bar Chart**, and click the **Bold** button.</span></span>  
  
4.  <span data-ttu-id="34268-271">Selecione **cinco principais vendedores para 2009**e, na seção **fonte** , na guia **início** , defina o tamanho da fonte como **10**.</span><span class="sxs-lookup"><span data-stu-id="34268-271">Select **Top Five Sellers for 2009**, and in the **Font** section on the **Home** tab, set the font size to **10**.</span></span>  
  
5.  <span data-ttu-id="34268-272">(Opcional) Talvez seja necessário aumentar a altura da caixa de texto Título para acomodar as duas linhas de texto.</span><span class="sxs-lookup"><span data-stu-id="34268-272">(Optional) You may need to make the Title text box taller to accommodate the two lines of text.</span></span>  
  
     <span data-ttu-id="34268-273">Esse título aparecerá na parte superior do relatório.</span><span class="sxs-lookup"><span data-stu-id="34268-273">This title will appear at the top of the report.</span></span> <span data-ttu-id="34268-274">Quando não houver nenhum cabeçalho de página definido, os itens na parte superior do corpo do relatório serão equivalentes a um cabeçalho de relatório.</span><span class="sxs-lookup"><span data-stu-id="34268-274">When there is no page header defined, items at the top of the report body are the equivalent of a report header.</span></span>  
  
6.  <span data-ttu-id="34268-275">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="34268-275">Click **Run** to preview the report.</span></span>  
  
##  <a name="10-save-the-report"></a><a name="Save"></a><span data-ttu-id="34268-276">10. salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="34268-276">10. Save the Report</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="34268-277">Para salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="34268-277">To save the report</span></span>  
  
1.  <span data-ttu-id="34268-278">Alterne para a exibição de design de relatório.</span><span class="sxs-lookup"><span data-stu-id="34268-278">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="34268-279">No botão **Construtor de Relatórios** , clique em **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="34268-279">From the **Report Builder** button, click **Save As**.</span></span>  
  
3.  <span data-ttu-id="34268-280">Em **Nome**, digite **Gráfico de Barras de Vendas**.</span><span class="sxs-lookup"><span data-stu-id="34268-280">In **Name**, type **Sales Bar Chart**.</span></span>  
  
4.  <span data-ttu-id="34268-281">Clique em **Save** (Salvar).</span><span class="sxs-lookup"><span data-stu-id="34268-281">Click **Save**.</span></span>  
  
 <span data-ttu-id="34268-282">O relatório é salvo no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="34268-282">Your report is saved on the report server.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="34268-283">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="34268-283">Next Steps</span></span>  
 <span data-ttu-id="34268-284">Você concluiu com êxito o tutorial Adicionando um gráfico de barras seu relatório.</span><span class="sxs-lookup"><span data-stu-id="34268-284">You have successfully completed the Adding a Bar Chart to Your Report tutorial.</span></span> <span data-ttu-id="34268-285">Para saber mais sobre gráficos, consulte [Gráficos &#40;Construtor de Relatórios e SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) e [Minigráficos e barras de dados &#40;Construtor de Relatórios e SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="34268-285">To learn more about charts, see [Charts &#40;Report Builder and SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) and [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34268-286">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="34268-286">See Also</span></span>  
 <span data-ttu-id="34268-287">[TUTORIAIS &#40;Construtor de Relatórios&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="34268-287">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="34268-288">Construtor de Relatórios no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="34268-288">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
