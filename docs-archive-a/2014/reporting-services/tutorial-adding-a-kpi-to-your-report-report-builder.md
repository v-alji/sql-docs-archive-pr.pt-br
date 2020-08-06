---
title: 'Tutorial: Adicionando um KPI ao relatório (Construtor de Relatórios) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 1bf77859-0b33-4f40-abaf-ebeeb6ebb1f8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 405978721068583597adf5c4257978a222121078
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683350"
---
# <a name="tutorial-adding-a-kpi-to-your-report-report-builder"></a><span data-ttu-id="31fad-102">Tutorial: adicionando um KPI ao relatório (Construtor de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="31fad-102">Tutorial: Adding a KPI to Your Report (Report Builder)</span></span>
  <span data-ttu-id="31fad-103">O KPI (indicador chave de desempenho) é um valor mensurável que tem importância comercial.</span><span class="sxs-lookup"><span data-stu-id="31fad-103">A key performance indicator (KPI) is a measurable value that has business significance.</span></span> <span data-ttu-id="31fad-104">Este tutorial ensina a incluir um KPI em um relatório.</span><span class="sxs-lookup"><span data-stu-id="31fad-104">This tutorial teaches you how to include a (KPI) in a report.</span></span> <span data-ttu-id="31fad-105">Nesse cenário, o resumo das vendas por subcategorias de produto é o KPI.</span><span class="sxs-lookup"><span data-stu-id="31fad-105">In this scenario, the sales summary by product subcategories is the KPI.</span></span> <span data-ttu-id="31fad-106">O estado atual do KPI é mostrado usando-se cores e indicadores.</span><span class="sxs-lookup"><span data-stu-id="31fad-106">The current state of the KPI is shown by using colors, gauges, and indicators.</span></span>  
  
 <span data-ttu-id="31fad-107">A ilustração a seguir mostra o relatório que você criará.</span><span class="sxs-lookup"><span data-stu-id="31fad-107">The following illustration shows the report that you will create.</span></span>  
  
 <span data-ttu-id="31fad-108">![rs_AddKPITutorial](../../2014/tutorials/media/rs-addkpitutorial.gif "rs_AddKPITutorial")</span><span class="sxs-lookup"><span data-stu-id="31fad-108">![rs_AddKPITutorial](../../2014/tutorials/media/rs-addkpitutorial.gif "rs_AddKPITutorial")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="31fad-109">O que você aprenderá</span><span class="sxs-lookup"><span data-stu-id="31fad-109">What You Will Learn</span></span>  
 <span data-ttu-id="31fad-110">Neste tutorial, você aprenderá a adicionar um KPI definindo a cor do plano de fundo das células da tabela com base no valor da célula, além de adicionar e configurar um indicador.</span><span class="sxs-lookup"><span data-stu-id="31fad-110">In this tutorial, you will learn to add a KPI by setting the background color of table cells based on cell value and add and configure a gauge and an indicator.</span></span> <span data-ttu-id="31fad-111">Você também aprende a escrever a expressão que define a cor do plano de fundo das células da tabela.</span><span class="sxs-lookup"><span data-stu-id="31fad-111">You also learn to write the expression that sets the background color of the table cells.</span></span>  
  
 <span data-ttu-id="31fad-112">Este tutorial contém os seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="31fad-112">This tutorial contains the following procedures:</span></span>  
  
1.  [<span data-ttu-id="31fad-113">Criar um relatório de tabela e conjunto de dados no Assistente de Tabela ou Matriz</span><span class="sxs-lookup"><span data-stu-id="31fad-113">Create a Table Report and Dataset from the Table or Matrix Wizard</span></span>](#Table)  
  
2.  [<span data-ttu-id="31fad-114">Organizar dados, escolher layout e estilo no Assistente de Tabela ou Matriz</span><span class="sxs-lookup"><span data-stu-id="31fad-114">Organize Data, Choose Layout, and Style from the Table or Matrix Wizard</span></span>](#CompleteWizard)  
  
3.  [<span data-ttu-id="31fad-115">Usar cores do plano de fundo para exibir um KPI</span><span class="sxs-lookup"><span data-stu-id="31fad-115">Use Background Colors to Display a KPI</span></span>](#BackgroundColors)  
  
4.  [<span data-ttu-id="31fad-116">Exibir um KPI usando um medidor</span><span class="sxs-lookup"><span data-stu-id="31fad-116">Display a KPI by Using a Gauge</span></span>](#Gauge)  
  
5.  [<span data-ttu-id="31fad-117">Exibir um KPI usando um indicador</span><span class="sxs-lookup"><span data-stu-id="31fad-117">Display a KPI by Using an Indicator</span></span>](#Indicator)  
  
6.  [<span data-ttu-id="31fad-118">Adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="31fad-118">Add a Report Title</span></span>](#Title)  
  
7.  [<span data-ttu-id="31fad-119">Salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="31fad-119">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="31fad-120">Neste tutorial, as etapas do assistente são consolidadas em dois procedimentos: um para criar o conjunto de dados e um para criar uma tabela.</span><span class="sxs-lookup"><span data-stu-id="31fad-120">In this tutorial, the steps for the wizard are consolidated into two procedures: one to create the dataset and one to create a table.</span></span> <span data-ttu-id="31fad-121">Para obter instruções passo a passo sobre como procurar um servidor de relatório, escolher uma fonte de dados, criar um conjunto de dados e executar o assistente, consulte o primeiro tutorial desta série: [Tutorial: Criação de um relatório de tabela básico &#40;Construtor de Relatórios&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="31fad-121">For step-by-step instructions about how to browse to a report server, choose a data source, create a dataset, and run the wizard, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="31fad-122">Tempo estimado para concluir este tutorial: 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="31fad-122">Estimated time to complete this tutorial: 15 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31fad-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="31fad-123">Requirements</span></span>  
 <span data-ttu-id="31fad-124">Para obter mais informações sobre os requisitos, consulte [Pré-requisitos para tutoriais &#40;Construtor de Relatórios&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="31fad-124">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-table-report-and-dataset-from-the-table-or-matrix-wizard"></a><a name="Table"></a><span data-ttu-id="31fad-125">1. criar um relatório de tabela e um conjunto de relatórios do assistente de tabela ou matriz</span><span class="sxs-lookup"><span data-stu-id="31fad-125">1. Create a Table Report and Dataset from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="31fad-126">Na caixa de diálogo **introdução** , escolha uma fonte de dados compartilhada, crie um conjunto de dados inserido e exiba-os em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="31fad-126">From the **Getting Started** dialog box, choose a shared data source, create an embedded dataset, and display the data in a table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="31fad-127">Neste tutorial, a consulta contém os valores de dados para que não precise de uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="31fad-127">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="31fad-128">Isso torna a consulta bastante longa.</span><span class="sxs-lookup"><span data-stu-id="31fad-128">This makes the query quite long.</span></span> <span data-ttu-id="31fad-129">Em um ambiente empresarial, uma consulta não conteria os dados.</span><span class="sxs-lookup"><span data-stu-id="31fad-129">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="31fad-130">Isso é apenas para fins de aprendizado.</span><span class="sxs-lookup"><span data-stu-id="31fad-130">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-table"></a><span data-ttu-id="31fad-131">Para criar uma tabela nova</span><span class="sxs-lookup"><span data-stu-id="31fad-131">To create a new table</span></span>  
  
1.  <span data-ttu-id="31fad-132">Clique em **Iniciar**, aponte para **Programas**, para **Construtor de Relatórios do Microsoft SQL Server 2012**e clique em **Construtor de Relatórios**.</span><span class="sxs-lookup"><span data-stu-id="31fad-132">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="31fad-133">A caixa de diálogo **introdução** é exibida.</span><span class="sxs-lookup"><span data-stu-id="31fad-133">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="31fad-134">Se a caixa de diálogo **introdução** não for exibida, no botão Construtor de relatórios, clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="31fad-134">If the **Getting Started** dialog box does not appear, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="31fad-135">No painel esquerdo, verifique se **Novo Relatório** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="31fad-135">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="31fad-136">No painel direito, clique em **Assistente de Tabela ou Matriz**.</span><span class="sxs-lookup"><span data-stu-id="31fad-136">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="31fad-137">Na página Escolher um conjunto de dados , clique em **Criar um conjunto de dados**.</span><span class="sxs-lookup"><span data-stu-id="31fad-137">On the Choose a dataset page, click **Create a dataset**.</span></span>  
  
5.  <span data-ttu-id="31fad-138">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="31fad-138">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="31fad-139">Na página **escolher uma conexão com uma fonte de dados** , selecione uma fonte de dados existente ou navegue até o servidor de relatório e selecione uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="31fad-139">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source.</span></span> <span data-ttu-id="31fad-140">Se não houver nenhuma fonte de dados disponível ou se você não tiver acesso a um servidor de relatório, será possível usar uma fonte de dados inserida.</span><span class="sxs-lookup"><span data-stu-id="31fad-140">If there no data source is available or you do not have access to a report server, you can use an embedded data source instead.</span></span> <span data-ttu-id="31fad-141">Para obter mais informações, consulte [Tutorial: Criando um relatório de tabela básico &#40;Construtor de Relatórios&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="31fad-141">For more information, see [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
7.  <span data-ttu-id="31fad-142">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="31fad-142">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="31fad-143">Na página **Crie uma consulta** , clique em **Editar como Texto**.</span><span class="sxs-lookup"><span data-stu-id="31fad-143">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
9. <span data-ttu-id="31fad-144">Copie e cole a seguinte consulta no painel de consulta:</span><span class="sxs-lookup"><span data-stu-id="31fad-144">Copy and paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Tripod' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-11' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Lens Adapter' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Mini Battery Charger' as Product, CAST(1056.00 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Accessories' as Subcategory,  
       'Telephoto Conversion Lens' as Product, CAST(1380.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,'Accessories' as Subcategory,    
       'USB Cable' as Product, CAST(780.00 AS money) AS Sales, 26 as Quantity  
    UNION SELECT CAST('2009-01-08' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(3798.00 AS money) AS Sales, 9 as Quantity  
    UNION SELECT CAST('2009-01-09' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Business Videographer' as Product, CAST(10400.00 AS money) AS Sales, 13 as Quantity  
    UNION SELECT CAST('2009-01-10' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Social Videographer' as Product, CAST(3000.00 AS money) AS Sales, 60 as Quantity  
    UNION SELECT CAST('2009-01-11' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Advanced Digital' as Product, CAST(7234.50 AS money) AS Sales, 39 as Quantity  
    UNION SELECT CAST('2009-01-07' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Compact Digital' as Product, CAST(10836.00 AS money) AS Sales, 84 as Quantity  
    UNION SELECT CAST('2009-01-08' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Consumer Digital' as Product, CAST(2550.00 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Digital' as Subcategory,   
       'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2009-01-09' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'SLR Camera 35mm' as Product, CAST(18530.00 AS money) AS Sales, 34 as Quantity  
    UNION SELECT CAST('2009-01-07' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'SLR Camera' as Product, CAST(26576.00 AS money) AS Sales, 88 as Quantity  
    ```  
  
10. <span data-ttu-id="31fad-145">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="31fad-145">Click **Next**.</span></span>  
  
##  <a name="2-organize-data-choose-layout-and-style-from-the-table-or-matrix-wizard"></a><a name="CompleteWizard"></a><span data-ttu-id="31fad-146">2. organizar dados, escolher layout e estilo no assistente de tabela ou matriz</span><span class="sxs-lookup"><span data-stu-id="31fad-146">2. Organize Data, Choose Layout, and Style from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="31fad-147">Use o assistente para fornecer um design inicial no qual exibir dados.</span><span class="sxs-lookup"><span data-stu-id="31fad-147">Use the wizard to provide a starting design on which to display data.</span></span> <span data-ttu-id="31fad-148">O painel de visualização no assistente ajuda a visualizar o resultado do agrupamento de dados antes de concluir o design da tabela ou da matriz.</span><span class="sxs-lookup"><span data-stu-id="31fad-148">The preview pane in the wizard helps you to visualize the result of grouping data before you complete the table or matrix design.</span></span>  
  
#### <a name="to-organize-data-into-groups-choose-a-layout-and-a-style"></a><span data-ttu-id="31fad-149">Para organizar dados em grupos, escolha um layout e um estilo</span><span class="sxs-lookup"><span data-stu-id="31fad-149">To organize data into groups, choose a layout and a style</span></span>  
  
1.  <span data-ttu-id="31fad-150">Na página Organizar campos, arraste Product até **Valores**.</span><span class="sxs-lookup"><span data-stu-id="31fad-150">On the Arrange fields page, drag Product to **Values**.</span></span>  
  
2.  <span data-ttu-id="31fad-151">Arraste Quantity até **Values** e coloque-o abaixo de Product.</span><span class="sxs-lookup"><span data-stu-id="31fad-151">Drag Quantity to **Values** and place below Product.</span></span>  
  
     <span data-ttu-id="31fad-152">O campo Quantity é resumido com a função Sum, a função padrão para resumir campos numéricos.</span><span class="sxs-lookup"><span data-stu-id="31fad-152">Quantity is summarized with the Sum function, the default function to summarize numeric fields.</span></span>  
  
3.  <span data-ttu-id="31fad-153">Arraste Sales até **Valores** e coloque-o abaixo de Quantity.</span><span class="sxs-lookup"><span data-stu-id="31fad-153">Drag Sales to **Values** and place below Quantity.</span></span>  
  
     <span data-ttu-id="31fad-154">As etapas 1, 2 e 3 especificam os dados a serem exibidos na tabela.</span><span class="sxs-lookup"><span data-stu-id="31fad-154">Steps 1, 2, and 3 specify the data to display in the table.</span></span>  
  
4.  <span data-ttu-id="31fad-155">Arraste SalesDate até **Grupos de linhas**.</span><span class="sxs-lookup"><span data-stu-id="31fad-155">Drag SalesDate to **Row groups**.</span></span>  
  
5.  <span data-ttu-id="31fad-156">Arraste Subcategory até **Grupos de linhas** e coloque-o abaixo de SalesDate.</span><span class="sxs-lookup"><span data-stu-id="31fad-156">Drag Subcategory to **Row groups** and place below SalesDate.</span></span>  
  
     <span data-ttu-id="31fad-157">As etapas 4 e 5 organizam os valores dos campos primeiro por data e depois por todas as vendas nessa data.</span><span class="sxs-lookup"><span data-stu-id="31fad-157">Steps 4 and 5 organize the values for the fields first by date, and then by all sales for that date.</span></span>  
  
6.  <span data-ttu-id="31fad-158">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="31fad-158">Click **Next**.</span></span>  
  
     <span data-ttu-id="31fad-159">Quando você executar o relatório, a tabela exibirá cada data, todas as ordens de cada data e todos os produtos, quantidades e totais de vendas de cada pedido.</span><span class="sxs-lookup"><span data-stu-id="31fad-159">When you run the report, the table displays each date, all orders for each date, and all products, quantities, and sales totals for each order.</span></span>  
  
7.  <span data-ttu-id="31fad-160">Na página Escolher o Layout, em **Opções**, verifique se a opção **Mostrar subtotais e totais gerais** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="31fad-160">On the Choose the Layout page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
8.  <span data-ttu-id="31fad-161">Verifique se a opção **Bloqueado, subtotal abaixo** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="31fad-161">Verify that **Blocked, subtotal below** is selected.</span></span>  
  
9. <span data-ttu-id="31fad-162">Desmarque a opção **Expandir/recolher grupos**.</span><span class="sxs-lookup"><span data-stu-id="31fad-162">Clear the option **Expand/collapse groups**.</span></span>  
  
     <span data-ttu-id="31fad-163">Neste tutorial, o relatório criado não usa o recurso de detalhamento que permite a um usuário expandir uma hierarquia de grupo pai para exibir linhas de grupo filho e linhas de detalhes.</span><span class="sxs-lookup"><span data-stu-id="31fad-163">In this tutorial, the report you create does not use the drilldown feature that lets a user expand a parent group hierarchy to display child group rows and detail rows.</span></span>  
  
10. <span data-ttu-id="31fad-164">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="31fad-164">Click **Next**.</span></span>  
  
11. <span data-ttu-id="31fad-165">Na página Escolher um Estilo, no painel Estilos, selecione um estilo.</span><span class="sxs-lookup"><span data-stu-id="31fad-165">On the Choose a Style page, in the Styles pane, select a style.</span></span>  
  
     <span data-ttu-id="31fad-166">A ilustração do relatório concluído mostra o relatório usando o estilo Oceano.</span><span class="sxs-lookup"><span data-stu-id="31fad-166">The illustration of the completed report shows the report using the Ocean style.</span></span>  
  
12. <span data-ttu-id="31fad-167">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="31fad-167">Click **Finish**.</span></span>  
  
     <span data-ttu-id="31fad-168">A tabela é adicionada à superfície de design.</span><span class="sxs-lookup"><span data-stu-id="31fad-168">The table is added to the design surface.</span></span> <span data-ttu-id="31fad-169">A tabela tem cinco colunas e cinco linhas.</span><span class="sxs-lookup"><span data-stu-id="31fad-169">The table has five columns and five rows.</span></span> <span data-ttu-id="31fad-170">O painel Grupos de Linhas mostra três grupos de linhas: SalesDate, Subcategory e Details.</span><span class="sxs-lookup"><span data-stu-id="31fad-170">The Row Groups pane shows three row groups: SalesDate, Subcategory, and Details.</span></span> <span data-ttu-id="31fad-171">Os dados detalhados são todos os dados recuperados pela consulta do conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="31fad-171">Detail data is all the data that is retrieved by the dataset query.</span></span>  
  
13. <span data-ttu-id="31fad-172">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="31fad-172">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="31fad-173">Para cada produto vendido em uma data específica, a tabela exibe o nome do produto, a quantidade vendida e o total da venda.</span><span class="sxs-lookup"><span data-stu-id="31fad-173">For each product that is sold on a specific date, the table displays the product name, the quantity sold, and the sales total.</span></span> <span data-ttu-id="31fad-174">Os dados são organizados primeiro pela data da venda e depois pela subcategoria.</span><span class="sxs-lookup"><span data-stu-id="31fad-174">The data is organized first by sales date and then by subcategory.</span></span>  
  
##  <a name="3-use-background-colors-to-display-a-kpi"></a><a name="BackgroundColors"></a><span data-ttu-id="31fad-175">3. usar cores de plano de fundo para exibir um KPI</span><span class="sxs-lookup"><span data-stu-id="31fad-175">3. Use Background Colors to Display a KPI</span></span>  
 <span data-ttu-id="31fad-176">As cores do plano de fundo podem ser definidas como uma expressão avaliada quando você executa o relatório.</span><span class="sxs-lookup"><span data-stu-id="31fad-176">Background colors can be set to an expression that is evaluated when you run the report.</span></span>  
  
#### <a name="to-display-the-present-state-of-a-kpi-by-using-background-colors"></a><span data-ttu-id="31fad-177">Para exibir o estado atual de um KPI usando cores de plano de fundo</span><span class="sxs-lookup"><span data-stu-id="31fad-177">To display the present state of a KPI by using background colors</span></span>  
  
1.  <span data-ttu-id="31fad-178">Na tabela, clique com o botão direito do mouse em duas células abaixo da `[Sum(Sales)]` célula (a linha de subtotal que exibe as vendas de uma subcategoria) e clique em **Propriedades da caixa de texto**.</span><span class="sxs-lookup"><span data-stu-id="31fad-178">In the table, right-click two cells down from the `[Sum(Sales)]` cell (the subtotal row that displays the sales for a subcategory), and then click **Text Box Properties**.</span></span>  
  
2.  <span data-ttu-id="31fad-179">Em **preenchimento**, clique no botão **FX** ao lado da opção **cor de preenchimento** e insira a seguinte expressão no campo **Definir expressão para: BackgroundColor** :</span><span class="sxs-lookup"><span data-stu-id="31fad-179">In **Fill**, click the **fx** button next to the **Fill color** option and enter the following expression in the **Set expression for: BackgroundColor** field:</span></span>  
  
 `=IIF(Sum(Fields!Sales.Value) >= 5000 ,"Lime", IIF(Sum(Fields!Sales.Value) < 2500, "Red","Yellow"))`  
  
 <span data-ttu-id="31fad-180">Isso altera a cor do plano de fundo para verde, usando a tonalidade de verde denominada "Verde-limão", para cada célula que contém uma soma agregada para `[Sum(Sales)]` maior ou igual a 5000.</span><span class="sxs-lookup"><span data-stu-id="31fad-180">This changes the background color to green, using the shade of green named "Lime", for each cell that contains an aggregated sum for `[Sum(Sales)]` that is greater than or equal to 5000.</span></span> <span data-ttu-id="31fad-181">Os valores de `[Sum(Sales)]` entre 2500 e 5000 são coloridos de amarelo.</span><span class="sxs-lookup"><span data-stu-id="31fad-181">Values of `[Sum(Sales)]` between 2500 and 5000 are colored yellow.</span></span> <span data-ttu-id="31fad-182">Os valores menores que 2500 são coloridos de vermelho.</span><span class="sxs-lookup"><span data-stu-id="31fad-182">Values less than 2500 are colored red.</span></span>  
  
1.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
2.  <span data-ttu-id="31fad-183">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="31fad-183">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="31fad-184">Na linha de subtotal que exibe as vendas de uma subcategoria, a cor do plano de fundo da célula é vermelha, amarela ou verde, dependendo da soma das vendas.</span><span class="sxs-lookup"><span data-stu-id="31fad-184">In the subtotal row that displays the sales for a subcategory, the background color of the cell is red, yellow, or green depending on value of the sales sum.</span></span>  
  
##  <a name="4-display-a-kpi-by-using-a-gauge"></a><a name="Gauge"></a><span data-ttu-id="31fad-185">4. exibir um KPI usando um medidor</span><span class="sxs-lookup"><span data-stu-id="31fad-185">4. Display a KPI by Using a Gauge</span></span>  
 <span data-ttu-id="31fad-186">Um medidor representa um único valor em um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="31fad-186">A gauge depicts a single value in a dataset.</span></span> <span data-ttu-id="31fad-187">Este tutorial usa um medidor linear horizontal porque sua forma e simplicidade facilitam a leitura, mesmo quando menor e usado dentro de uma célula da tabela.</span><span class="sxs-lookup"><span data-stu-id="31fad-187">This tutorial uses a horizontal linear gauge because its shape and simplicity makes it easy to read, even in when it is a small size and used within a table cell.</span></span> <span data-ttu-id="31fad-188">Para obter mais informações, consulte [Medidores &#40;Construtor de Relatórios e SSRS&#41;](report-design/gauges-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="31fad-188">For more information, see [Gauges &#40;Report Builder and SSRS&#41;](report-design/gauges-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-display-the-present-state-of-a-kpi-using-a-gauge"></a><span data-ttu-id="31fad-189">Para exibir o estado presente de um KPI que usa um medidor</span><span class="sxs-lookup"><span data-stu-id="31fad-189">To display the present state of a KPI using a gauge</span></span>  
  
1.  <span data-ttu-id="31fad-190">Alterne para o modo Design.</span><span class="sxs-lookup"><span data-stu-id="31fad-190">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="31fad-191">Na tabela, clique com o botão direito do mouse no manipulador de colunas da célula que você alterou no procedimento anterior, aponte para **Inserir coluna**e clique em **direita**.</span><span class="sxs-lookup"><span data-stu-id="31fad-191">In the table, right-click the column handler for the cell that you changed in the previous procedure, point to **Insert Column**, and then click **Right**.</span></span> <span data-ttu-id="31fad-192">Uma nova coluna é adicionada à tabela.</span><span class="sxs-lookup"><span data-stu-id="31fad-192">A new column is added to the table.</span></span>  
  
3.  <span data-ttu-id="31fad-193">Digite **KPI** no título da coluna.</span><span class="sxs-lookup"><span data-stu-id="31fad-193">Type **KPI** in the column heading.</span></span>  
  
4.  <span data-ttu-id="31fad-194">Na guia **Inserir** , no grupo **regiões de dados** , clique em **medidor**e, em seguida, clique na superfície de design fora da tabela.</span><span class="sxs-lookup"><span data-stu-id="31fad-194">On the **Insert** tab, in the **Data Regions** group, click **Gauge**, and then click the design surface outside the table.</span></span> <span data-ttu-id="31fad-195">A caixa de diálogo **Selecionar Tipo de Medidor** é exibida.</span><span class="sxs-lookup"><span data-stu-id="31fad-195">The **Select Gauge Type** dialog box appears.</span></span>  
  
5.  <span data-ttu-id="31fad-196">Clique em **linear**.</span><span class="sxs-lookup"><span data-stu-id="31fad-196">Click **Linear**.</span></span> <span data-ttu-id="31fad-197">O primeiro tipo de medidor linear, **horizontal**, é selecionado.</span><span class="sxs-lookup"><span data-stu-id="31fad-197">The first linear gauge type, **Horizontal**, is selected.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="31fad-198">Um medidor é adicionado à superfície de design.</span><span class="sxs-lookup"><span data-stu-id="31fad-198">A gauge is added to the design surface.</span></span>  
  
7.  <span data-ttu-id="31fad-199">No painel Dados do Relatório, arraste Sales para o indicador.</span><span class="sxs-lookup"><span data-stu-id="31fad-199">From the Report Data pane, drag Sales to the gauge.</span></span> <span data-ttu-id="31fad-200">Quando você arrasta Sales pelo indicador, o painel Dados do Medidor é aberto.</span><span class="sxs-lookup"><span data-stu-id="31fad-200">When you drag Sales across the gauge, the Gauge Data pane opens.</span></span>  
  
8.  <span data-ttu-id="31fad-201">Descarte vendas na lista **valores** .</span><span class="sxs-lookup"><span data-stu-id="31fad-201">Drop Sales in the **Values** list.</span></span>  
  
     <span data-ttu-id="31fad-202">Quando você solta o campo no medidor, o campo é agregado através da função Sum interna.</span><span class="sxs-lookup"><span data-stu-id="31fad-202">When you drop the field onto the gauge, the field is aggregated by using the built-in Sum function.</span></span>  
  
9. <span data-ttu-id="31fad-203">Clique com o botão direito do mouse no indicador e clique em **Propriedades do ponteiro**.</span><span class="sxs-lookup"><span data-stu-id="31fad-203">Right-click the pointer in the gauge and click **Pointer Properties**.</span></span>  
  
10. <span data-ttu-id="31fad-204">Em **tipo de ponteiro**, selecione **barra**.</span><span class="sxs-lookup"><span data-stu-id="31fad-204">In **Pointer Type**, select **Bar**.</span></span> <span data-ttu-id="31fad-205">Isso altera o ponteiro de um marcador para uma barra que será mais visível quando o medidor for adicionado à tabela.</span><span class="sxs-lookup"><span data-stu-id="31fad-205">This changes the pointer from a marker to a bar that will be more visible when the gauge is added to the table.</span></span>  
  
11. <span data-ttu-id="31fad-206">Clique em **preenchimento do ponteiro**.</span><span class="sxs-lookup"><span data-stu-id="31fad-206">Click **Pointer Fill**.</span></span> <span data-ttu-id="31fad-207">Em **cor secundária,** selecione **amarelo**.</span><span class="sxs-lookup"><span data-stu-id="31fad-207">In **Secondary Color,** pick **Yellow**.</span></span> <span data-ttu-id="31fad-208">O padrão de preenchimento de gradiente mudará de branco para amarelo.</span><span class="sxs-lookup"><span data-stu-id="31fad-208">The gradient fill pattern will change from white to yellow.</span></span>  
  
12. <span data-ttu-id="31fad-209">Clique com o botão direito do mouse na escala do medidor e clique em **Propriedades da Escala**.</span><span class="sxs-lookup"><span data-stu-id="31fad-209">Right-click the scale in the gauge and click **Scale Properties**.</span></span>  
  
13. <span data-ttu-id="31fad-210">Defina a opção **máximo** como 25000.</span><span class="sxs-lookup"><span data-stu-id="31fad-210">Set the **Maximum** option to 25000.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="31fad-211">Em vez de uma constante como 25.000, é possível usar uma expressão para calcular dinamicamente o valor da opção **Máximo** .</span><span class="sxs-lookup"><span data-stu-id="31fad-211">Instead of a constant such as 25000, you can use an expression to dynamically calculate the value of the **Maximum** option.</span></span> <span data-ttu-id="31fad-212">A expressão usaria a agregação do recurso de agregação e semelhante à expressão `=Max(Sum(Fields!Sales.value), "Tablix1")`.</span><span class="sxs-lookup"><span data-stu-id="31fad-212">The expression would use the aggregate of aggregate feature and look similar to the expression `=Max(Sum(Fields!Sales.value), "Tablix1")`.</span></span>  
  
14. <span data-ttu-id="31fad-213">Arraste o medidor dentro da tabela para a terceira célula na linha do subtotal que exibe as vendas de uma subcategoria da coluna que você inseriu.</span><span class="sxs-lookup"><span data-stu-id="31fad-213">Drag the gauge inside the table into the third cell in the subtotal row that displays the sales for a subcategory of the column that you inserted.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="31fad-214">Talvez você precise redimensionar a coluna para que o medidor linear horizontal se ajuste à célula.</span><span class="sxs-lookup"><span data-stu-id="31fad-214">You might have to resize the column so that the horizontal linear gauge fits into the cell.</span></span> <span data-ttu-id="31fad-215">Para redimensionar a coluna, clique em um cabeçalho de coluna e use as alças para redimensionar as células horizontal e verticalmente.</span><span class="sxs-lookup"><span data-stu-id="31fad-215">To resize the column, click a column header and use the handles to resize the cells horizontally and vertically.</span></span>  
  
15. <span data-ttu-id="31fad-216">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="31fad-216">Click **Run** to preview the report.</span></span>  
  
     <span data-ttu-id="31fad-217">O comprimento horizontal da barra no medidor é alterado de acordo com o valor do KPI.</span><span class="sxs-lookup"><span data-stu-id="31fad-217">The horizontal length of the bar in the gauge changes depending on the value of the KPI.</span></span>  
  
16. <span data-ttu-id="31fad-218">(Opcional) Adicione um pin máximo para resolver o estouro de forma que qualquer valor acima do máximo da escala sempre aponte para o pin máximo:</span><span class="sxs-lookup"><span data-stu-id="31fad-218">(Optional) Add a maximum pin to handle overflow so that any value over the scale maximum always points to the maximum pin:</span></span>  
  
    1.  <span data-ttu-id="31fad-219">Abra o painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="31fad-219">Open the Properties pane.</span></span>  
  
    2.  <span data-ttu-id="31fad-220">Clique na escala.</span><span class="sxs-lookup"><span data-stu-id="31fad-220">Click the scale.</span></span> <span data-ttu-id="31fad-221">As propriedades da escala linear são exibidas no painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="31fad-221">The properties for the linear scale are displayed in the Properties pane.</span></span>  
  
    3.  <span data-ttu-id="31fad-222">Na categoria **pins da escala** , expanda o nó **MaximumPin** .</span><span class="sxs-lookup"><span data-stu-id="31fad-222">In the **Scale Pins** category, expand the **MaximumPin** node.</span></span>  
  
    4.  <span data-ttu-id="31fad-223">Defina a propriedade **habilitar** como `True` .</span><span class="sxs-lookup"><span data-stu-id="31fad-223">Set the **Enable** property to `True`.</span></span> <span data-ttu-id="31fad-224">Um pin é exibido depois do valor de máximo na escala.</span><span class="sxs-lookup"><span data-stu-id="31fad-224">A pin appears after the maximum value on the scale.</span></span>  
  
    5.  <span data-ttu-id="31fad-225">Defina **BorderColor** como `Lime` .</span><span class="sxs-lookup"><span data-stu-id="31fad-225">Set **BorderColor** to `Lime`.</span></span>  
  
17. <span data-ttu-id="31fad-226">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="31fad-226">Click **Run** to preview the report.</span></span>  
  
##  <a name="5-display-a-kpi-by-using-an-indicator"></a><a name="Indicator"></a><span data-ttu-id="31fad-227">5. exibir um KPI usando um indicador</span><span class="sxs-lookup"><span data-stu-id="31fad-227">5. Display a KPI by Using an Indicator</span></span>  
 <span data-ttu-id="31fad-228">Indicadores são medidores pequenos e simples que comunicam valores de dados em um relance.</span><span class="sxs-lookup"><span data-stu-id="31fad-228">Indicators are small simple gauges that communicate data values at a glance.</span></span> <span data-ttu-id="31fad-229">Por conta de seu tamanho e simplicidade, os indicadores costumam ser usados em tabelas e matrizes.</span><span class="sxs-lookup"><span data-stu-id="31fad-229">Because of their size and simplicity, indicators are often used in tables and matrices.</span></span> <span data-ttu-id="31fad-230">Para obter mais informações, consulte [Indicadores &#40;Construtor de Relatórios e SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="31fad-230">For more information, see [Indicators &#40;Report Builder and SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-display-the-present-state-of-a-kpi-using-an-indicator"></a><span data-ttu-id="31fad-231">Para exibir o estado atual de um KPI usando um indicador</span><span class="sxs-lookup"><span data-stu-id="31fad-231">To display the present state of a KPI using an indicator</span></span>  
  
1.  <span data-ttu-id="31fad-232">Alterne para o modo Design.</span><span class="sxs-lookup"><span data-stu-id="31fad-232">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="31fad-233">Na tabela, clique com o botão direito do mouse no manipulador de colunas da célula que você alterou no procedimento anterior, aponte para **Inserir coluna**e clique em **direita**.</span><span class="sxs-lookup"><span data-stu-id="31fad-233">In the table, right-click the column handler for the cell that you changed in the previous procedure, point to **Insert Column**, and then click **Right**.</span></span> <span data-ttu-id="31fad-234">Uma nova coluna é adicionada à tabela.</span><span class="sxs-lookup"><span data-stu-id="31fad-234">A new column is added to the table.</span></span>  
  
3.  <span data-ttu-id="31fad-235">Digite **KPI** no título da coluna.</span><span class="sxs-lookup"><span data-stu-id="31fad-235">Type **KPI** in the column heading.</span></span>  
  
4.  <span data-ttu-id="31fad-236">Clique na célula do subtotal da subcategoria.</span><span class="sxs-lookup"><span data-stu-id="31fad-236">Click the cell for the subcategory subtotal.</span></span>  
  
5.  <span data-ttu-id="31fad-237">Na guia **Inserir** , no grupo **regiões de dados** , clique duas vezes em **indicador.**</span><span class="sxs-lookup"><span data-stu-id="31fad-237">On the **Insert** tab, in the **Data Regions** group, double-click **Indicator.**</span></span>  
  
     <span data-ttu-id="31fad-238">A caixa de diálogo **Selecionar Tipo de Indicador** será aberta.</span><span class="sxs-lookup"><span data-stu-id="31fad-238">The **Select Indicator Type** dialog box opens.</span></span>  
  
6.  <span data-ttu-id="31fad-239">Clique em **formas**.</span><span class="sxs-lookup"><span data-stu-id="31fad-239">Click **Shapes**.</span></span> <span data-ttu-id="31fad-240">O primeiro tipo de forma, **3 semáforos (não coroados),** é selecionado.</span><span class="sxs-lookup"><span data-stu-id="31fad-240">The first shape type, **3 Traffic Lights (Unrimmed),** is selected.</span></span>  
  
     <span data-ttu-id="31fad-241">Você usará esse indicador no tutorial.</span><span class="sxs-lookup"><span data-stu-id="31fad-241">You will use this indicator in the tutorial.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="31fad-242">O indicador é adicionado à superfície de design.</span><span class="sxs-lookup"><span data-stu-id="31fad-242">The indicator is added to the design surface.</span></span>  
  
8.  <span data-ttu-id="31fad-243">Clique com o botão direito do mouse no indicador e clique em **Propriedades do Indicador**.</span><span class="sxs-lookup"><span data-stu-id="31fad-243">Right-click the indicator and click **Indicator Properties**.</span></span>  
  
9. <span data-ttu-id="31fad-244">Clique em **valores e Estados**.</span><span class="sxs-lookup"><span data-stu-id="31fad-244">Click **Values and States**.</span></span>  
  
10. <span data-ttu-id="31fad-245">Na lista suspensa valor, selecione **[Sum (Sales)]**, mas não altere nenhuma outra opção.</span><span class="sxs-lookup"><span data-stu-id="31fad-245">In the Value drop-down list, select **[Sum(Sales)]**, but do not change any other options.</span></span>  
  
     <span data-ttu-id="31fad-246">Por padrão, a sincronização de dados ocorre na região de dados e o valor **Tablix1**, o nome da região de dados da tabela no relatório, é exibido na caixa **Escopo de sincronização** .</span><span class="sxs-lookup"><span data-stu-id="31fad-246">By default, data synchronization occurs across the data region and you see the value **Tablix1**, the name of the table data region in the report, in the **Synchronization scope** box.</span></span>  
  
     <span data-ttu-id="31fad-247">Nesse relatório, é possível alterar também o escopo de um indicador colocado na célula do subtotal da subcategoria para sincronização no campo SalesDate.</span><span class="sxs-lookup"><span data-stu-id="31fad-247">In this report, you can also change the scope of an indicator placed in the cell of the subcategory subtotal to synchronize across the SalesDate field.</span></span>  
  
11. <span data-ttu-id="31fad-248">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="31fad-248">Click **Run** to preview the report.</span></span>  
  
##  <a name="6-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="31fad-249">6. adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="31fad-249">6. Add a Report Title</span></span>  
 <span data-ttu-id="31fad-250">Um título é exibido na parte superior do relatório.</span><span class="sxs-lookup"><span data-stu-id="31fad-250">A report title appears at the top of the report.</span></span> <span data-ttu-id="31fad-251">É possível colocar o título em um cabeçalho do relatório. No entanto, se ele não usar um cabeçalho, será possível colocar o título em uma caixa de texto na parte superior do corpo do relatório.</span><span class="sxs-lookup"><span data-stu-id="31fad-251">You can place the report title in a report header or if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="31fad-252">Você usará a caixa de texto colocada automaticamente na parte superior do corpo do relatório.</span><span class="sxs-lookup"><span data-stu-id="31fad-252">You will use the text box that is automatically placed at the top of the report body.</span></span>  
  
 <span data-ttu-id="31fad-253">O texto pode ser aprimorado ainda mais aplicando-se estilos, tamanhos e cores de fontes diferentes a frases e caracteres individuais do texto.</span><span class="sxs-lookup"><span data-stu-id="31fad-253">The text can be further enhanced by applying different font styles, sizes, and colors to phrases and individual characters of the text.</span></span> <span data-ttu-id="31fad-254">Para obter mais informações, consulte [Formatar o texto em uma caixa de texto &#40;Construtor de Relatórios e SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="31fad-254">For more information, see [Format Text in a Text Box &#40;Report Builder and SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="31fad-255">Para adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="31fad-255">To add a report title</span></span>  
  
1.  <span data-ttu-id="31fad-256">Na superfície de design, clique em **Clique para adicionar título**.</span><span class="sxs-lookup"><span data-stu-id="31fad-256">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="31fad-257">Digite **KPI de vendas do produto**e clique fora da caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="31fad-257">Type **Product Sales KPI**, and then click outside the text box.</span></span>  
  
3.  <span data-ttu-id="31fad-258">Opcionalmente, clique com o botão direito do mouse na caixa de texto que contém **KPI vendas do produto**, clique em **Propriedades da caixa de texto**e, na guia fonte, selecione os diferentes estilos de fonte, tamanhos e cores.</span><span class="sxs-lookup"><span data-stu-id="31fad-258">Optionally, right-click the text box that contains **Product Sales KPI**, click **Text Box Properties**, and then on the Font tab select the different font styles, sizes and colors.</span></span>  
  
4.  <span data-ttu-id="31fad-259">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="31fad-259">Click **Run** to preview the report.</span></span>  
  
##  <a name="7-save-the-report"></a><a name="Save"></a><span data-ttu-id="31fad-260">7. salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="31fad-260">7. Save the Report</span></span>  
 <span data-ttu-id="31fad-261">Salve o relatório em um servidor de relatório ou no computador.</span><span class="sxs-lookup"><span data-stu-id="31fad-261">Save the report to a report server or your computer.</span></span> <span data-ttu-id="31fad-262">Se você não salvar o relatório no servidor de relatório, vários recursos do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , como partes do relatório e sub-relatórios, não estarão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="31fad-262">If you do not save the report to the report server, a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features such as report parts and subreports are not available.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="31fad-263">Para salvar o relatório em um servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="31fad-263">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="31fad-264">No botão **Construtor de Relatórios** , clique em **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="31fad-264">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="31fad-265">Clique em **Sites e Servidores Recentes**.</span><span class="sxs-lookup"><span data-stu-id="31fad-265">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="31fad-266">Selecione ou digite o nome do servidor de relatório no qual você tem permissão para salvar relatórios.</span><span class="sxs-lookup"><span data-stu-id="31fad-266">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="31fad-267">A mensagem "Conectando-se a um servidor de relatório" é exibida.</span><span class="sxs-lookup"><span data-stu-id="31fad-267">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="31fad-268">Quando a conexão for concluída, você verá o conteúdo da pasta do relatório que o administrador do servidor de relatório especificou como o local padrão para relatórios.</span><span class="sxs-lookup"><span data-stu-id="31fad-268">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="31fad-269">Em **Nome**, substitua o nome padrão por **KPI de Vendas de Produtos**.</span><span class="sxs-lookup"><span data-stu-id="31fad-269">In **Name**, replace the default name with **Product Sales KPI**.</span></span>  
  
5.  <span data-ttu-id="31fad-270">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="31fad-270">Click **Save**.</span></span>  
  
 <span data-ttu-id="31fad-271">O relatório será salvo no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="31fad-271">The report is saved to the report server.</span></span> <span data-ttu-id="31fad-272">O nome do servidor de relatório ao qual você está conectado é exibido na barra de status da parte inferior da janela.</span><span class="sxs-lookup"><span data-stu-id="31fad-272">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="31fad-273">Para salvar o relatório no computador</span><span class="sxs-lookup"><span data-stu-id="31fad-273">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="31fad-274">No botão **Construtor de Relatórios** , clique em **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="31fad-274">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="31fad-275">Clique em **Área de Trabalho**, **Meus Documentos**ou **Meu computador**e procure a pasta na qual você quer salvar o relatório.</span><span class="sxs-lookup"><span data-stu-id="31fad-275">Click **Desktop**, **My Documents**, or **My computer**, and browse to the folder where you want to save the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="31fad-276">Se você não tiver acesso a um servidor de relatório, clique em **Área de Trabalho**, **Meus Documentos**ou **Meu computador** e salve o relatório no computador.</span><span class="sxs-lookup"><span data-stu-id="31fad-276">If you do not have access to a report server, click **Desktop**, **My Documents**, or **My computer** and save the report to your computer.</span></span>  
  
1.  <span data-ttu-id="31fad-277">Em **Nome**, substitua o nome padrão por **KPI de Vendas de Produtos**.</span><span class="sxs-lookup"><span data-stu-id="31fad-277">In **Name**, replace the default name with **Product Sales KPI**.</span></span>  
  
2.  <span data-ttu-id="31fad-278">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="31fad-278">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="31fad-279">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="31fad-279">Next Steps</span></span>  
 <span data-ttu-id="31fad-280">Você completou com êxito o tutorial Adicionando um KPI ao relatório.</span><span class="sxs-lookup"><span data-stu-id="31fad-280">You have successfully completed the Adding a KPI to Your Report tutorial.</span></span> <span data-ttu-id="31fad-281">Para obter mais informações, consulte indicadores de medidores (Construtor de Relatórios) [&#40;Construtor de relatórios e SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="31fad-281">For more information, see Gauges (Report Builder) [Indicators &#40;Report Builder and SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31fad-282">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="31fad-282">See Also</span></span>  
 <span data-ttu-id="31fad-283">[TUTORIAIS &#40;Construtor de Relatórios&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="31fad-283">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="31fad-284">Construtor de Relatórios no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="31fad-284">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
