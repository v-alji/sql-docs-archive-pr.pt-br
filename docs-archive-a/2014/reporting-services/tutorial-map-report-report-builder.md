---
title: 'Tutorial: Relatório de mapa (Construtor de Relatórios) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8d831356-7efa-40cc-ae95-383b3eecf833
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b737bb3fe74eb3524f2944a7458cb4837b1aeedf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684016"
---
# <a name="tutorial-map-report-report-builder"></a><span data-ttu-id="63c66-102">Tutorial: Relatório de mapa (construtor de relatórios)</span><span class="sxs-lookup"><span data-stu-id="63c66-102">Tutorial: Map Report (Report Builder)</span></span>
  <span data-ttu-id="63c66-103">Este tutorial foi desenvolvido para ajudá-lo a aprender sobre os recursos de mapa que você pode usar para exibir dados de relatório em comparação com um plano de fundo geográfico.</span><span class="sxs-lookup"><span data-stu-id="63c66-103">This tutorial is designed to help you learn about the map features you can use to display report data against a geographic background.</span></span>  
  
 <span data-ttu-id="63c66-104">Os mapas se baseiam em dados espaciais que geralmente consistem em pontos, linhas e polígonos.</span><span class="sxs-lookup"><span data-stu-id="63c66-104">Maps are based on spatial data that typically consists of points, lines, and polygons.</span></span> <span data-ttu-id="63c66-105">Por exemplo, um polígono pode representar a estrutura de tópicos de um município, uma linha pode representar uma estrada e um ponto pode representar o local de uma cidade.</span><span class="sxs-lookup"><span data-stu-id="63c66-105">For example, a polygon can represent the outline of a county, a line can represent a road, and a point can represent the location of a city.</span></span> <span data-ttu-id="63c66-106">Cada tipo de dados espaciais é exibido em uma camada do mapa separada como um conjunto de elementos de mapa.</span><span class="sxs-lookup"><span data-stu-id="63c66-106">Each type of spatial data is displayed on a separate map layer as a set of map elements.</span></span>  
  
 <span data-ttu-id="63c66-107">Para variar a aparência de elementos de mapas, especifique um campo com valores que correspondem aos elementos de mapas com dados analíticos de um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="63c66-107">To vary the appearance of map elements, you specify a field that has values that match the map elements with analytical data from a dataset.</span></span> <span data-ttu-id="63c66-108">Também é possível definir regras que variam em cor, tamanho ou outras propriedades com base em intervalos de dados.</span><span class="sxs-lookup"><span data-stu-id="63c66-108">You can also define rules that vary color, size, or other properties based on ranges of data.</span></span>  
  
 <span data-ttu-id="63c66-109">Neste tutorial, você criará um relatório de mapa que exibe a localização de lojas em municípios estatais de Nova York.</span><span class="sxs-lookup"><span data-stu-id="63c66-109">In this tutorial, you will build a map report that displays store locations in New York state counties.</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="63c66-110">O que você aprenderá</span><span class="sxs-lookup"><span data-stu-id="63c66-110">What You Will Learn</span></span>  
 <span data-ttu-id="63c66-111">Neste tutorial, você aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="63c66-111">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="63c66-112">Criar um mapa com uma camada de polígono usando o Assistente de Mapas</span><span class="sxs-lookup"><span data-stu-id="63c66-112">Create a Map with a Polygon Layer from the Map Wizard</span></span>](#Map)  
  
2.  [<span data-ttu-id="63c66-113">Adicionar uma camada de ponto de mapa para exibir locais de loja</span><span class="sxs-lookup"><span data-stu-id="63c66-113">Add a Map Point Layer to Display Store Locations</span></span>](#PointLayer)  
  
3.  [<span data-ttu-id="63c66-114">Adicionar uma camada de linha de mapa para exibir uma rota</span><span class="sxs-lookup"><span data-stu-id="63c66-114">Add a Map Line Layer to Display a Route</span></span>](#LineLayer)  
  
4.  [<span data-ttu-id="63c66-115">Adicionar um plano de fundo lado a lado do Bing Maps</span><span class="sxs-lookup"><span data-stu-id="63c66-115">Add a Bing Maps Tile Background</span></span>](#TileLayer)  
  
5.  [<span data-ttu-id="63c66-116">Tornar uma camada transparente</span><span class="sxs-lookup"><span data-stu-id="63c66-116">Make a Layer Transparent</span></span>](#Transparent)  
  
6.  [<span data-ttu-id="63c66-117">Variar as cores de municípios com base em vendas</span><span class="sxs-lookup"><span data-stu-id="63c66-117">Vary County Color Based on Sales</span></span>](#Vary)  
  
    1.  [<span data-ttu-id="63c66-118">Criar um relacionamento entre dados espaciais e analíticos</span><span class="sxs-lookup"><span data-stu-id="63c66-118">Build a Relationship between Spatial and Analytical Data</span></span>](#Relationship)  
  
    2.  [<span data-ttu-id="63c66-119">Especificar as regras de cores para polígonos</span><span class="sxs-lookup"><span data-stu-id="63c66-119">Specify Color Rules for Polygons</span></span>](#ColorRules)  
  
    3.  [<span data-ttu-id="63c66-120">Formatar os dados na escala de cores como moeda</span><span class="sxs-lookup"><span data-stu-id="63c66-120">Format the Data in the Color Scale as Currency</span></span>](#ColorScale)  
  
    4.  [<span data-ttu-id="63c66-121">Criar uma nova legenda</span><span class="sxs-lookup"><span data-stu-id="63c66-121">Create a New Legend</span></span>](#NewLegend)  
  
    5.  [<span data-ttu-id="63c66-122">Associar regras de cores e legenda</span><span class="sxs-lookup"><span data-stu-id="63c66-122">Associate Legend and Color Rules</span></span>](#Associate)  
  
    6.  [<span data-ttu-id="63c66-123">Limpar cores dos municípios para os quais não há dados</span><span class="sxs-lookup"><span data-stu-id="63c66-123">Clear Color from Counties with No Data</span></span>](#NoData)  
  
7.  [<span data-ttu-id="63c66-124">Adicionar um ponto personalizado</span><span class="sxs-lookup"><span data-stu-id="63c66-124">Add a Custom Point</span></span>](#CustomPoint)  
  
8.  [<span data-ttu-id="63c66-125">Centralizar o modo de exibição de mapas</span><span class="sxs-lookup"><span data-stu-id="63c66-125">Center the Map View</span></span>](#CenterView)  
  
9. [<span data-ttu-id="63c66-126">Adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="63c66-126">Add a Report Title</span></span>](#Title)  
  
10. [<span data-ttu-id="63c66-127">Salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="63c66-127">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="63c66-128">Neste tutorial, as etapas do assistente são consolidadas em dois procedimentos: um para criar o conjunto de dados e um para criar uma tabela.</span><span class="sxs-lookup"><span data-stu-id="63c66-128">In this tutorial, the steps for the wizard are consolidated into two procedures: one to create the dataset and one to create a table.</span></span> <span data-ttu-id="63c66-129">Para obter instruções passo a passo sobre como procurar um servidor de relatório, escolher uma fonte de dados, criar um conjunto de dados e executar o assistente, consulte o primeiro tutorial desta série: [Tutorial: Criação de um relatório de tabela básico &#40;Construtor de Relatórios&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="63c66-129">For step-by-step instructions about how to browse to a report server, choose a data source, create a dataset, and run the wizard, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="63c66-130">Tempo estimado para concluir este tutorial: 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="63c66-130">Estimated time to complete this tutorial: 30 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63c66-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="63c66-131">Requirements</span></span>  
 <span data-ttu-id="63c66-132">Para obter informações sobre os requisitos, consulte [Pré-requisitos para tutoriais &#40;Construtor de Relatórios&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="63c66-132">For information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-map-with-a-polygon-layer-from-the-map-wizard"></a><a name="Map"></a><span data-ttu-id="63c66-133">1. criar um mapa com uma camada de polígono a partir do assistente de mapa</span><span class="sxs-lookup"><span data-stu-id="63c66-133">1. Create a Map with a Polygon Layer from the Map Wizard</span></span>  
 <span data-ttu-id="63c66-134">Adicionar um mapa em seu relatório a partir da galeria de mapas.</span><span class="sxs-lookup"><span data-stu-id="63c66-134">Add a map to your report from the map gallery.</span></span> <span data-ttu-id="63c66-135">O mapa tem uma camada que exibe os municípios do estado de Nova York.</span><span class="sxs-lookup"><span data-stu-id="63c66-135">The map has one layer that displays the counties in New York state.</span></span> <span data-ttu-id="63c66-136">A forma de cada município é um polígono com base em dados espaciais inseridos no mapa a partir da galeria de mapas.</span><span class="sxs-lookup"><span data-stu-id="63c66-136">The shape of each county is a polygon based on spatial data that is embedded in the map from the map gallery.</span></span>  
  
#### <a name="to-add-a-map-with-the-map-wizard-in-a-new-report"></a><span data-ttu-id="63c66-137">Para adicionar um mapa com o assistente de mapa em um novo relatório</span><span class="sxs-lookup"><span data-stu-id="63c66-137">To add a map with the map wizard in a new report</span></span>  
  
1.  <span data-ttu-id="63c66-138">Clique em **Iniciar**, aponte para **programas**, aponte para [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Construtor de relatórios**e, em seguida, clique em **Construtor de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="63c66-138">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)]**Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="63c66-139">A caixa de diálogo Guia de Introdução é exibida.</span><span class="sxs-lookup"><span data-stu-id="63c66-139">The Getting Started dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="63c66-140"> Se a caixa de diálogo Guia de Introdução não for exibida, no botão Construtor de Relatórios, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="63c66-140">If the Getting Started dialog box does not appear, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="63c66-141">No painel esquerdo, verifique se **Relatório** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="63c66-141">In the left pane, verify that **Report** is selected.</span></span>  
  
3.  <span data-ttu-id="63c66-142">No painel direito, clique em **Assistente de Mapa**.</span><span class="sxs-lookup"><span data-stu-id="63c66-142">In the right pane, click **Map Wizard**.</span></span>  
  
4.  <span data-ttu-id="63c66-143">Clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="63c66-143">Click **Create**.</span></span>  
  
5.  <span data-ttu-id="63c66-144">Na página**Escolher uma fonte de dados espaciais** , verifique se a **Galeria de mapas** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="63c66-144">**Choose a source of spatial data** page, verify that **Map gallery** is selected.</span></span>  
  
6.  <span data-ttu-id="63c66-145">No painel de Galeria de Mapas, expanda **Estados por País** em **EUA**e clique em **Nova York**.</span><span class="sxs-lookup"><span data-stu-id="63c66-145">In the Map Gallery pane, expand **States by County** under **USA**, and click **New York**.</span></span>  
  
     <span data-ttu-id="63c66-146">O painel de Visualização de Mapa exibe o mapa do município de Nova York.</span><span class="sxs-lookup"><span data-stu-id="63c66-146">The Map Preview pane displays the New York county map.</span></span>  
  
7.  <span data-ttu-id="63c66-147">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="63c66-147">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="63c66-148">Na página **Escolher as opções de dados espaciais e de exibição de mapa** , aceite os padrões.</span><span class="sxs-lookup"><span data-stu-id="63c66-148">On the **Choose spatial data and map view options** page, accept the defaults.</span></span> <span data-ttu-id="63c66-149">Por padrão, os elementos do mapa de uma galeria de mapas serão inseridos automaticamente na definição do relatório.</span><span class="sxs-lookup"><span data-stu-id="63c66-149">By default, map elements from a map gallery will automatically be embedded in the report definition.</span></span>  
  
9. <span data-ttu-id="63c66-150">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="63c66-150">Click **Next**.</span></span>  
  
10. <span data-ttu-id="63c66-151">Na página **Escolher visualização do mapa** , verifique se **Mapa Básico** está selecionado e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="63c66-151">On the **Choose map visualization** page, verify **Basic Map** is selected, and click **Next**.</span></span>  
  
11. <span data-ttu-id="63c66-152">Na página **Escolher o tema da cor e a visualização dos dados** , selecione a opção **Exibir rótulos** .</span><span class="sxs-lookup"><span data-stu-id="63c66-152">On the **Choose color theme and data visualization** page, select the **Display labels** option.</span></span>  
  
12. <span data-ttu-id="63c66-153">Se estiver selecionada, desmarque a opção **Mapa de cor única** .</span><span class="sxs-lookup"><span data-stu-id="63c66-153">If it is selected, clear the **Single color map** option.</span></span>  
  
13. <span data-ttu-id="63c66-154">Na lista suspensa **campo de dados** , clique em #COUNTYNAME.</span><span class="sxs-lookup"><span data-stu-id="63c66-154">From the **Data field** drop-down list, click #COUNTYNAME.</span></span> <span data-ttu-id="63c66-155">O painel Visualização de Mapa no assistente exibe os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="63c66-155">The Map Preview pane in the wizard displays the following items:</span></span>  
  
    -   <span data-ttu-id="63c66-156">Um título com o texto **Título do Mapa**.</span><span class="sxs-lookup"><span data-stu-id="63c66-156">A title with the text **Map Title**.</span></span>  
  
    -   <span data-ttu-id="63c66-157">Um mapa que exibe os municípios em Nova York onde cada município é uma cor diferente e o nome do município aparece onde possível na área do município.</span><span class="sxs-lookup"><span data-stu-id="63c66-157">A map that displays counties in New York where each county is a different color and the county name appears wherever it fits over the county area.</span></span>  
  
    -   <span data-ttu-id="63c66-158">Uma legenda que contém um título e uma lista de itens de 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="63c66-158">A legend that contains a title and a list of items 1 through 5.</span></span>  
  
    -   <span data-ttu-id="63c66-159">Uma escala de cores que contém valores de 0 a 160 e nenhuma cor.</span><span class="sxs-lookup"><span data-stu-id="63c66-159">A color scale that contains values 0 to 160 and no color.</span></span>  
  
    -   <span data-ttu-id="63c66-160">Uma escala de distância que exibe quilômetros (km) e milhas (mi).</span><span class="sxs-lookup"><span data-stu-id="63c66-160">A distance scale that displays kilometers (km) and miles (mi).</span></span>  
  
14. <span data-ttu-id="63c66-161">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="63c66-161">Click **Finish**.</span></span>  
  
     <span data-ttu-id="63c66-162">O mapa é adicionado à superfície de design.</span><span class="sxs-lookup"><span data-stu-id="63c66-162">The map is added to the design surface.</span></span>  
  
15. <span data-ttu-id="63c66-163">Clique no mapa para selecioná-lo e exibir o painel **Camadas do Mapa**.</span><span class="sxs-lookup"><span data-stu-id="63c66-163">Click the map to select it and display the **Map Layers Pane**.</span></span> <span data-ttu-id="63c66-164">O painel **Camadas do Mapa** mostra uma camada de polígono de tipo de camada **Inserido**.</span><span class="sxs-lookup"><span data-stu-id="63c66-164">The **Map Layers Pane** shows one polygon layer of layer type **Embedded**.</span></span> <span data-ttu-id="63c66-165">Cada região é um elemento do mapa inserido nessa camada.</span><span class="sxs-lookup"><span data-stu-id="63c66-165">Each county is an embedded map element on this layer.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="63c66-166">Se você não vir o painel **Camadas do Mapa** , talvez ele esteja fora da exibição atual.</span><span class="sxs-lookup"><span data-stu-id="63c66-166">If you do not see the **Map Layers** pane, it might be displayed outside your current view.</span></span> <span data-ttu-id="63c66-167">Use a barra de rolagem na parte inferior da janela do modo Design para alterar sua exibição.</span><span class="sxs-lookup"><span data-stu-id="63c66-167">Use the scroll bar at the bottom of the Design view window to change your view.</span></span> <span data-ttu-id="63c66-168">Opcionalmente, na guia **Exibir** , desmarque as **Propriedades** ou a opção **Dados do Relatório** para fornecer mais área de superfície de design.</span><span class="sxs-lookup"><span data-stu-id="63c66-168">Alternatively, in the **View** tab, clear the **Properties** or the **Report Data** option to provide more design surface area.</span></span>  
  
16. <span data-ttu-id="63c66-169">Clique com o botão direito do mouse no título do mapa e clique em **Propriedades do Título**.</span><span class="sxs-lookup"><span data-stu-id="63c66-169">Right-click the map title, and then click **Title Properties**.</span></span>  
  
17. <span data-ttu-id="63c66-170">Substitua o texto do título por **Vendas por Loja**.</span><span class="sxs-lookup"><span data-stu-id="63c66-170">Replace the title text with **Sales by Store**.</span></span>  
  
18. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
19. <span data-ttu-id="63c66-171">Visualize o relatório.</span><span class="sxs-lookup"><span data-stu-id="63c66-171">Preview the report.</span></span>  
  
 <span data-ttu-id="63c66-172">O relatório renderizado exibe o título do mapa, o mapa e a escala de distância.</span><span class="sxs-lookup"><span data-stu-id="63c66-172">The rendered report displays the map title, the map, and the distance scale.</span></span> <span data-ttu-id="63c66-173">Os municípios estão em uma camada do polígono de mapas.</span><span class="sxs-lookup"><span data-stu-id="63c66-173">The counties are on a map polygon layer.</span></span> <span data-ttu-id="63c66-174">Cada município é um polígono que varia por cor de uma paleta de cores, mas as cores não estão associadas a nenhum dado.</span><span class="sxs-lookup"><span data-stu-id="63c66-174">Each county is a polygon that varies by color from a color palette, but the colors are not associated with any data.</span></span> <span data-ttu-id="63c66-175">A escala de distância exibe distâncias em quilômetros e em milhas.</span><span class="sxs-lookup"><span data-stu-id="63c66-175">The distance scale displays distances in both kilometers and miles.</span></span>  
  
 <span data-ttu-id="63c66-176">A legenda de mapa e a escala de cores ainda não são exibidos porque não há dados analíticos associados a cada município.</span><span class="sxs-lookup"><span data-stu-id="63c66-176">The map legend and color scale do not yet appear because there is no analytical data associated with each county.</span></span> <span data-ttu-id="63c66-177">Você adicionará dados analíticos posteriormente neste tutorial.</span><span class="sxs-lookup"><span data-stu-id="63c66-177">You will add analytical data later in this tutorial.</span></span>  
  
##  <a name="2-add-a-map-point-layer-to-display-store-locations"></a><a name="PointLayer"></a><span data-ttu-id="63c66-178">2. adicionar uma camada de ponto do mapa para exibir locais de armazenamento</span><span class="sxs-lookup"><span data-stu-id="63c66-178">2. Add a Map Point Layer to Display Store Locations</span></span>  
 <span data-ttu-id="63c66-179">Use o assistente de camada do mapa para adicionar uma camada de pontos que exibe a localização das lojas.</span><span class="sxs-lookup"><span data-stu-id="63c66-179">Use the map layer wizard to add a point layer that displays the locations of stores.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63c66-180">Neste tutorial, a consulta contém os valores de dados para que não precise de uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="63c66-180">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="63c66-181">Isso torna a consulta bastante longa.</span><span class="sxs-lookup"><span data-stu-id="63c66-181">This makes the query quite long.</span></span> <span data-ttu-id="63c66-182">Em um ambiente empresarial, uma consulta não conteria os dados.</span><span class="sxs-lookup"><span data-stu-id="63c66-182">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="63c66-183">Isso é apenas para fins de aprendizado.</span><span class="sxs-lookup"><span data-stu-id="63c66-183">This is for learning purposes only.</span></span>  
  
#### <a name="to-add-a-point-layer-based-on-a-sql-server-spatial-query"></a><span data-ttu-id="63c66-184">Para adicionar uma camada de ponto com base em uma consulta espacial do SQL Server</span><span class="sxs-lookup"><span data-stu-id="63c66-184">To add a point layer based on a SQL Server spatial query</span></span>  
  
1.  <span data-ttu-id="63c66-185">Alterne para o modo Design.</span><span class="sxs-lookup"><span data-stu-id="63c66-185">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="63c66-186">Clique duas vezes no mapa para exibir o painel **Camada do Mapa** .</span><span class="sxs-lookup"><span data-stu-id="63c66-186">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="63c66-187">Na barra de ferramentas, clique no botão **Assistente de Nova Camada**![rs_IconMapLayerWizard](../../2014/tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard").</span><span class="sxs-lookup"><span data-stu-id="63c66-187">On the toolbar, click the **New layer wizard** button ![rs_IconMapLayerWizard](../../2014/tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard").</span></span>  
  
3.  <span data-ttu-id="63c66-188">Na página **Escolher uma fonte de dados espaciais** , selecione **Consulta espacial do SQL Server**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="63c66-188">On the **Choose a source of spatial data** page, select **SQL Server spatial query**, and click **Next**.</span></span>  
  
4.  <span data-ttu-id="63c66-189">Na página **Escolha um conjunto de dados com dados espaciais do SQL Server** , clique em **Adicionar um novo conjunto de dados com dados espaciais do SQL Server**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="63c66-189">On the **Choose a dataset with SQL Server spatial data** page, click **Add a new dataset with SQL Server spatial data**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="63c66-190">Na página **Escolha uma conexão com uma fonte de dados espaciais do SQL Server** , selecione uma fonte de dados existente ou navegue até o servidor de relatório e selecione uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="63c66-190">On the **Choose a connection to a SQL Server spatial data source** page, select an existing data source or browse to the report server and select a data source.</span></span>  
  
6.  <span data-ttu-id="63c66-191">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="63c66-191">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="63c66-192">Na página criar uma consulta, clique em **Editar como texto**.</span><span class="sxs-lookup"><span data-stu-id="63c66-192">On the Design a Query page, click **Edit as Text**.</span></span>  
  
8.  <span data-ttu-id="63c66-193">Cole o seguinte texto de consulta no painel da consulta:</span><span class="sxs-lookup"><span data-stu-id="63c66-193">Paste the following text in the query pane:</span></span>  
  
    ```  
    Select 114 as StoreKey, 'Contoso Albany Store' as StoreName, 1125 as SellingArea, 'Albany' as City, 'Albany' as County,   
     CAST(1000000 as money) as Sales, CAST('POINT(-73.7472924218681 42.6564617079878)' as geography) AS SpatialLocation  
    UNION ALL SELECT 115 AS StoreKey, 'Contoso New York No.1 Store' AS  StoreName, 500 as SellingArea, 'New York' AS City, 'New York City' as County,  
     CAST('2000000' as money) as Sales, CAST('POINT(-73.9922069374483 40.7549638237402)' as geography) AS SpatialLocation  
    UNION ALL Select 116 as StoreKey, 'Contoso Rochester No.1 Store' as StoreName, 462 as SellingArea, 'Rochester' as City,  'Monroe' as County,    
     CAST(3000000 as money) as Sales, CAST('POINT(-77.624041566786 43.1547066024338)' as geography)  AS SpatialLocation  
    UNION ALL Select 117 as StoreKey, 'Contoso New York No.2 Store' as StoreName, 700 as SellingArea, 'New York' as City,'New York City' as County,    
      CAST(4000000 as money) as Sales, CAST('POINT(-73.9712488 40.7830603)' as geography) AS SpatialLocation  
    UNION ALL Select 118 as StoreKey, 'Contoso Syracuse Store' as StoreName, 680 as SellingArea, 'Syracuse' as City, 'Onondaga' as County,  
     CAST(5000000 as money) as Sales, CAST('POINT(-76.1349120532546 43.0610223535974)' as geography) AS SpatialLocation  
    UNION ALL Select 120 as StoreKey, 'Contoso Plattsburgh Store' as StoreName, 560 as SellingArea, 'Plattsburgh' as City,  'Clinton' as County,  
     CAST(6000000 as money) as Sales, CAST('POINT(-73.4728622833178 44.7028831413324)' as geography) AS SpatialLocation  
    UNION ALL Select 121 as StoreKey, 'Contoso Brooklyn Store' as StoreName, 1125 as SellingArea, 'Brooklyn' as City, 'New York City' as County,  
     CAST(7000000 as money) as Sales, CAST('POINT (-73.9638533447143 40.6785123489351)' as geography) AS SpatialLocation  
    UNION ALL Select 122 as StoreKey, 'Contoso Oswego Store' as StoreName, 500 as SellingArea, 'Oswego' as City, 'Oswego' as County,    
     CAST(8000000 as money) as Sales, CAST('POINT(-76.4602850815536 43.4353224527794)' as geography) AS SpatialLocation  
    UNION ALL Select 123 as StoreKey, 'Contoso Ithaca Store' as StoreName, 460 as SellingArea, 'Ithaca' as City, 'Tompkins' as County,  
     CAST(9000000 as money) as Sales, CAST('POINT(-76.5001866085881 42.4310489934743)' as geography) AS SpatialLocation  
    UNION ALL Select 124 as StoreKey, 'Contoso Rochester No.2 Store' as StoreName, 700 as SellingArea, 'Rochester' as City, 'Monroe' as County,    
     CAST(100000 as money) as Sales, CAST('POINT(-77.6240415667866 43.1547066024338)' as geography) AS SpatialLocation  
    UNION ALL Select 125 as StoreKey, 'Contoso Queens Store' as StoreName, 700 as SellingArea,'Queens' as City, 'New York City' as County,  
     CAST(500000 as money) as Sales, CAST('POINT(-73.7930979029883 40.7152781765927)' as geography) AS SpatialLocation  
    UNION ALL Select 126 as StoreKey, 'Contoso Elmira Store' as StoreName, 680 as SellingArea, 'Elmira' as City, 'Chemung' as County,  
     CAST(800000 as money) as Sales, CAST('POINT(-76.7397414783301 42.0736492742663)' as geography) AS SpatialLocation  
    UNION ALL Select 127 as StoreKey, 'Contoso Poestenkill Store' as StoreName, 455 as SellingArea, 'Poestenkill' as City, 'Rensselaer' as County,    
    CAST(1500000 as money) as Sales, CAST('POINT(-73.5626737425063 42.6940551238618)' as geography) AS SpatialLocation  
    ```  
  
9. <span data-ttu-id="63c66-194">Na barra de ferramentas do designer de consultas, clique em **executar** (**!**).</span><span class="sxs-lookup"><span data-stu-id="63c66-194">On the query designer toolbar, click **Run** (**!**).</span></span>  
  
     <span data-ttu-id="63c66-195">O conjunto de resultados exibe sete colunas: StoreKey, StoreName, SellingArea, City, County, Sales e SpatialLocation.</span><span class="sxs-lookup"><span data-stu-id="63c66-195">The result set displays seven columns: StoreKey, StoreName, SellingArea, City, County, Sales, and SpatialLocation.</span></span> <span data-ttu-id="63c66-196">Esses dados representam um conjunto de lojas no Estado de Nova York que vendem bens de consumo.</span><span class="sxs-lookup"><span data-stu-id="63c66-196">This data represents a set of stores in New York State that sell consumer goods.</span></span> <span data-ttu-id="63c66-197">Cada linha no conjunto de resultados contém um identificador de loja, o nome da loja, a área disponível para exibição do produto, a cidade e o município no qual a loja está localizada, o total de vendas e o local espacial em longitude e latitude.</span><span class="sxs-lookup"><span data-stu-id="63c66-197">Each row in the result set contains a store identifier, store name, the area available for product display, the city and county where the store is located, the sales total, and the spatial location in longitude and latitude.</span></span> <span data-ttu-id="63c66-198">A área de exibição varia de 455 pés quadrados a 1.125 pés quadrados.</span><span class="sxs-lookup"><span data-stu-id="63c66-198">The display area ranges from 455 square feet to 1125 square feet.</span></span>  
  
10. <span data-ttu-id="63c66-199">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="63c66-199">Click **Next**.</span></span>  
  
     <span data-ttu-id="63c66-200">O conjunto de dados de relatório chamado DataSet1 é criado para você.</span><span class="sxs-lookup"><span data-stu-id="63c66-200">The report dataset named DataSet1 is created for you.</span></span> <span data-ttu-id="63c66-201">Após a conclusão do assistente, você poderá usar os Dados do Relatório para exibir sua coleção de campos.</span><span class="sxs-lookup"><span data-stu-id="63c66-201">After you complete the wizard, you can use the Report Data to its field collection.</span></span>  
  
11. <span data-ttu-id="63c66-202">Na página **escolher as opções de dados espaciais e de exibição de mapa** , verifique se o **campo espacial** é `SpatialLocation` e se o **tipo de camada** é **ponto**.</span><span class="sxs-lookup"><span data-stu-id="63c66-202">On the **Choose a spatial data and map view options** page, verify that the **Spatial field** is `SpatialLocation` and that the **Layer type** is **Point**.</span></span> <span data-ttu-id="63c66-203">Aceite os outros padrões nesta página.</span><span class="sxs-lookup"><span data-stu-id="63c66-203">Accept the other defaults on this page.</span></span>  
  
     <span data-ttu-id="63c66-204">A exibição do mapa mostra círculos que marcam o local de cada loja.</span><span class="sxs-lookup"><span data-stu-id="63c66-204">The map view displays circles that mark the location of each store.</span></span>  
  
12. <span data-ttu-id="63c66-205">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="63c66-205">Click **Next**.</span></span>  
  
13. <span data-ttu-id="63c66-206">Especifique um tipo de mapa que exiba marcadores que variem por dados analíticos.</span><span class="sxs-lookup"><span data-stu-id="63c66-206">Specify a map type that displays markers that vary by analytic data.</span></span> <span data-ttu-id="63c66-207">Na página Escolher visualização do mapa, clique em **Mapa de Marcador Analítico**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="63c66-207">On the Choose map visualization page, click **Analytical Marker Map**, and then click **Next**.</span></span>  
  
14. <span data-ttu-id="63c66-208">Na página **Escolher o conjunto de dados analíticos** , clique em DataSet1.</span><span class="sxs-lookup"><span data-stu-id="63c66-208">On the **Choose the analytical dataset** page, click DataSet1.</span></span> <span data-ttu-id="63c66-209">Esse conjunto de dados contém dados analíticos e dados espaciais que serão exibidos na nova camada de ponto.</span><span class="sxs-lookup"><span data-stu-id="63c66-209">This dataset contains both analytical data and spatial data that will be displayed on the new point layer.</span></span>  
  
15. <span data-ttu-id="63c66-210">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="63c66-210">Click **Next**.</span></span>  
  
16. <span data-ttu-id="63c66-211">Na página **Escolher o tema da cor e a visualização dos dados** , desmarque a opção **Usar cores de marcador para visualizar dados** e selecione **Usar tipos de marcador para visualizar dados**.</span><span class="sxs-lookup"><span data-stu-id="63c66-211">On the **Choose color theme and data visualization** page, clear the **Use marker colors to visualize data** option, and then select the option **Use marker types to visualize data**.</span></span>  
  
17. <span data-ttu-id="63c66-212">No **Campo de dados**, selecione `[Sum(SellingArea)]` para variar os tipos de marcador conforme o tamanho da área que uma loja reserva para exibir os produtos.</span><span class="sxs-lookup"><span data-stu-id="63c66-212">In **Data field**, select `[Sum(SellingArea)]` to vary marker types by the size of the area a store sets aside to display the products.</span></span>  
  
18. <span data-ttu-id="63c66-213">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="63c66-213">Click **Finish**.</span></span>  
  
     <span data-ttu-id="63c66-214">A camada do mapa é adicionada ao relatório.</span><span class="sxs-lookup"><span data-stu-id="63c66-214">The map layer is added to the report.</span></span> <span data-ttu-id="63c66-215">A legenda exibe os tipos de marcadores com base nos valores SellingArea.</span><span class="sxs-lookup"><span data-stu-id="63c66-215">The legend displays marker types based on SellingArea values.</span></span>  
  
     <span data-ttu-id="63c66-216">Clique duas vezes no mapa para exibir o painel **Camada do Mapa** .</span><span class="sxs-lookup"><span data-stu-id="63c66-216">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="63c66-217">O painel **Camada do Mapa** exibe uma nova camada, PointLayer1, com o tipo de fonte de dados espaciais **DataRegion**.</span><span class="sxs-lookup"><span data-stu-id="63c66-217">The **Map Layer** pane displays a new layer, PointLayer1, with spatial data source type **DataRegion**.</span></span>  
  
19. <span data-ttu-id="63c66-218">Adicione um título à legenda.</span><span class="sxs-lookup"><span data-stu-id="63c66-218">Add a legend title.</span></span> <span data-ttu-id="63c66-219">Clique com o botão direito do mouse no título e clique em **Propriedades do Título da Legenda**.</span><span class="sxs-lookup"><span data-stu-id="63c66-219">Right-click the legend title, and then click **Legend Title Properties**.</span></span>  
  
20. <span data-ttu-id="63c66-220">Exclua o título e digite a **Área de Exibição (Pés Quadrados)**.</span><span class="sxs-lookup"><span data-stu-id="63c66-220">Delete the title, and type **Display Area (Square Feet)**.</span></span>  
  
21. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
22. <span data-ttu-id="63c66-221">Exiba os valores padrão que foram definidos pelo assistente.</span><span class="sxs-lookup"><span data-stu-id="63c66-221">View the default values that were set by the wizard.</span></span> <span data-ttu-id="63c66-222">No painel **Camadas do Mapa**, clique com o botão direito na camada de ponto e clique em **Regra de Tipo de Marcador**.</span><span class="sxs-lookup"><span data-stu-id="63c66-222">In the **Map Layers Pane**, right-click the point layer, and then click **Marker Type Rule**.</span></span>  
  
     <span data-ttu-id="63c66-223">Na guia **Geral** , os marcadores são listados na ordem na qual eles são exibidos na legenda.</span><span class="sxs-lookup"><span data-stu-id="63c66-223">On the **General** tab, the markers are listed in the order in which they appear in the legend.</span></span> <span data-ttu-id="63c66-224">Na guia **Distribuição** , o número de subintervalos é 5.</span><span class="sxs-lookup"><span data-stu-id="63c66-224">On the **Distribution** tab, the number of subranges is 5.</span></span> <span data-ttu-id="63c66-225">Na guia **Legenda** , o texto de legenda é definido para exibir o valor de início e término em cada intervalo.</span><span class="sxs-lookup"><span data-stu-id="63c66-225">On the **Legend** tab, the legend text is set to display the start and end value in each range.</span></span>  
  
23. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
24. <span data-ttu-id="63c66-226">Visualize o relatório.</span><span class="sxs-lookup"><span data-stu-id="63c66-226">Preview the report.</span></span>  
  
 <span data-ttu-id="63c66-227">O mapa exibe os locais de lojas no estado de Nova York.</span><span class="sxs-lookup"><span data-stu-id="63c66-227">The map displays the locations of stores in New York state.</span></span> <span data-ttu-id="63c66-228">O tipo de marcador para cada loja se baseia na área de exibição.</span><span class="sxs-lookup"><span data-stu-id="63c66-228">The marker type for each store is based on the display area.</span></span> <span data-ttu-id="63c66-229">Foram calculados cinco intervalos de área de exibição automaticamente para você.</span><span class="sxs-lookup"><span data-stu-id="63c66-229">Five ranges of display area were automatically calculated for you.</span></span>  
  
##  <a name="3-add-a-map-line-layer-to-display-a-route"></a><a name="LineLayer"></a><span data-ttu-id="63c66-230">3. adicionar uma camada de linha de mapa para exibir uma rota</span><span class="sxs-lookup"><span data-stu-id="63c66-230">3. Add a Map Line Layer to Display a Route</span></span>  
 <span data-ttu-id="63c66-231">Use o assistente de camada do mapa para adicionar uma camada do mapa que exibe uma rota entre duas lojas.</span><span class="sxs-lookup"><span data-stu-id="63c66-231">Use the map layer wizard to add a map layer that displays a route between two stores.</span></span> <span data-ttu-id="63c66-232">Neste tutorial, o caminho é criado de três locais de loja.</span><span class="sxs-lookup"><span data-stu-id="63c66-232">In this tutorial, the path is created from three store locations.</span></span> <span data-ttu-id="63c66-233">Em um aplicativo comercial, o caminho pode ser a melhor rota entre lojas.</span><span class="sxs-lookup"><span data-stu-id="63c66-233">In a business application, the path might be the best route between stores.</span></span>  
  
#### <a name="to-add-a-line-layer-to-map"></a><span data-ttu-id="63c66-234">Para adicionar uma camada de linha ao mapa</span><span class="sxs-lookup"><span data-stu-id="63c66-234">To add a line layer to map</span></span>  
  
1.  <span data-ttu-id="63c66-235">Alterne para o modo Design.</span><span class="sxs-lookup"><span data-stu-id="63c66-235">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="63c66-236">Clique duas vezes no mapa para exibir o painel **Camada do Mapa** .</span><span class="sxs-lookup"><span data-stu-id="63c66-236">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="63c66-237">Na barra de ferramentas, clique em **Assistente de nova camada**.</span><span class="sxs-lookup"><span data-stu-id="63c66-237">On the toolbar, click **New layer wizard**.</span></span>  
  
3.  <span data-ttu-id="63c66-238">Na página **escolher uma fonte de dados espaciais** , selecione **SQL Server consulta espacial** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="63c66-238">On the **Choose a source of spatial data** page, select **SQL Server spatial query** and click **Next**.</span></span>  
  
4.  <span data-ttu-id="63c66-239">Na página **Escolher um conjunto de dados com dados espaciais do SQL Server** , clique em **Adicionar um novo conjunto de dados com dados espaciais do SQL Server** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="63c66-239">On the **Choose a dataset with SQL Server spatial data** page, click **Add a new dataset with SQL Server spatial data** and click **Next**.</span></span>  
  
5.  <span data-ttu-id="63c66-240">Em **Escolher uma conexão com uma fonte de dados espaciais do SQL Server**, selecione DataSource1, a fonte de dados que você criou no primeiro procedimento.</span><span class="sxs-lookup"><span data-stu-id="63c66-240">On the **Choose a connection to a SQL Server spatial data source**, select DataSource1, the data source that you created in the first procedure.</span></span>  
  
6.  <span data-ttu-id="63c66-241">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="63c66-241">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="63c66-242">Na página **criar uma consulta** , clique em **Editar como texto**.</span><span class="sxs-lookup"><span data-stu-id="63c66-242">On the **Design a Query** page, click **Edit as Text**.</span></span> <span data-ttu-id="63c66-243">O designer de consulta alterna para o modo baseado no texto.</span><span class="sxs-lookup"><span data-stu-id="63c66-243">The query designer switches to text-based mode.</span></span>  
  
8.  <span data-ttu-id="63c66-244">Cole o seguinte texto de consulta no painel da consulta:</span><span class="sxs-lookup"><span data-stu-id="63c66-244">Paste the following text in the query pane:</span></span>  
  
    ```  
    SELECT N'Path' AS Name, CAST('LINESTRING(  
       -76.5001866085881 42.4310489934743,  
       -76.4602850815536 43.4353224527794,  
       -73.4728622833178 44.7028831413324)' AS geography) as Route  
    ```  
  
9. <span data-ttu-id="63c66-245">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="63c66-245">Click **Next**.</span></span>  
  
     <span data-ttu-id="63c66-246">Um caminho é exibido no mapa que conecta três lojas.</span><span class="sxs-lookup"><span data-stu-id="63c66-246">A path appears on the map that connects three stores.</span></span>  
  
10. <span data-ttu-id="63c66-247">Na página **Escolher as opções de dados espaciais e de exibição de mapa** , verifique se o **Campo espacial** é **Route** e se o **Tipo de camada** é **Linha**.</span><span class="sxs-lookup"><span data-stu-id="63c66-247">On the **Choose spatial data and map view options** page, verify that the **Spatial field** is **Route** and that the **Layer type** is **Line**.</span></span> <span data-ttu-id="63c66-248">Aceite os outros padrões.</span><span class="sxs-lookup"><span data-stu-id="63c66-248">Accept the other defaults.</span></span>  
  
     <span data-ttu-id="63c66-249">A exibição de mapa exibe um caminho de uma loja na parte norte do estado de Nova York até uma loja na parte sul do estado de Nova York.</span><span class="sxs-lookup"><span data-stu-id="63c66-249">The map view displays a path from a store in the northern part of New York state to a store in the southern part of New York state.</span></span>  
  
11. <span data-ttu-id="63c66-250">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="63c66-250">Click **Next**.</span></span>  
  
12. <span data-ttu-id="63c66-251">Na página **Escolher visualização do mapa** , clique em **Mapa da Linha Básica**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="63c66-251">On the **Choose map visualization** page, click **Basic Line Map**, and then click **Next**.</span></span>  
  
13. <span data-ttu-id="63c66-252">Em **Escolher o tema da cor e a visualização dos dados**, selecione a opção **Mapa de Cor Única**.</span><span class="sxs-lookup"><span data-stu-id="63c66-252">On the **Choose color theme and data visualization**, select the option **Single color map**.</span></span> <span data-ttu-id="63c66-253">O caminho é exibida em uma única cor com base no tema selecionado.</span><span class="sxs-lookup"><span data-stu-id="63c66-253">The path appears as a single color based on the selected theme.</span></span>  
  
14. <span data-ttu-id="63c66-254">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="63c66-254">Click **Finish**.</span></span>  
  
 <span data-ttu-id="63c66-255">O mapa exibe uma nova camada de linha com o tipo de fonte de dados espaciais **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="63c66-255">The map displays a new line layer with spatial data source type **DataSet**.</span></span> <span data-ttu-id="63c66-256">Neste exemplo, os dados espaciais vêm de um conjunto de dados, mas nenhum dado analítico é associado à linha.</span><span class="sxs-lookup"><span data-stu-id="63c66-256">In this example, the spatial data comes from a dataset but no analytical data is associated with the line.</span></span>  
  
##  <a name="4-add-a-bing-maps-tile-background"></a><a name="TileLayer"></a><span data-ttu-id="63c66-257">4. adicionar um plano de fundo de bloco do Bing Maps</span><span class="sxs-lookup"><span data-stu-id="63c66-257">4. Add a Bing Maps Tile Background</span></span>  
 <span data-ttu-id="63c66-258">Adicione uma camada do mapa que exibe um plano de fundo lado a lado do Bing Maps.</span><span class="sxs-lookup"><span data-stu-id="63c66-258">Add a map layer that displays a Bing Maps tile background.</span></span>  
  
#### <a name="to-add-a-virtual-earth-tile-background"></a><span data-ttu-id="63c66-259">Para adicionar plano de fundo lado a lado de Terra Virtual</span><span class="sxs-lookup"><span data-stu-id="63c66-259">To add a Virtual Earth tile background</span></span>  
  
1.  <span data-ttu-id="63c66-260">Alterne para o modo Design.</span><span class="sxs-lookup"><span data-stu-id="63c66-260">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="63c66-261">Clique duas vezes no mapa para exibir o painel **Camada do Mapa** .</span><span class="sxs-lookup"><span data-stu-id="63c66-261">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="63c66-262">Na barra de ferramentas, clique em **Adicionar Camada**![rs_IconMapAddLayer](../../2014/tutorials/media/rs-iconmapaddlayer.gif "rs_IconMapAddLayer").</span><span class="sxs-lookup"><span data-stu-id="63c66-262">On the toolbar, click **Add Layer**![rs_IconMapAddLayer](../../2014/tutorials/media/rs-iconmapaddlayer.gif "rs_IconMapAddLayer").</span></span>  
  
3.  <span data-ttu-id="63c66-263">Na lista suspensa, clique em **Camada do Bloco**.</span><span class="sxs-lookup"><span data-stu-id="63c66-263">From the drop-down list, click **Tile Layer**.</span></span>  
  
     <span data-ttu-id="63c66-264">A última camada no painel **Camada do Mapa** é TileLayer1.</span><span class="sxs-lookup"><span data-stu-id="63c66-264">The last layer in the **Map Layer** pane is TileLayer1.</span></span> <span data-ttu-id="63c66-265">Por padrão, a camada lado a lado exibe o estilo de mapa rodoviário.</span><span class="sxs-lookup"><span data-stu-id="63c66-265">By default, the tile layer displays the road map style.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="63c66-266">No assistente, você também pode adicionar uma camada lado a lado na página **Escolher as opções de dados espaciais e de exibição do mapa** .</span><span class="sxs-lookup"><span data-stu-id="63c66-266">In the wizard, you can also add a tile layer on the **Choose spatial data and map view options** page.</span></span> <span data-ttu-id="63c66-267">Para fazer isso, selecione **Adicionar um plano de fundo do Bing Maps a esta exibição de mapa**.</span><span class="sxs-lookup"><span data-stu-id="63c66-267">To do this, select **Add a Bing Maps background for this map view**.</span></span> <span data-ttu-id="63c66-268">Em um relatório renderizado, o plano de fundo lado a lado exibirá itens lado a lado do Bing Maps para o visor e o nível de zoom do mapa atual.</span><span class="sxs-lookup"><span data-stu-id="63c66-268">In a rendered report, the tile background displays Bing Maps tiles for the current map viewport center and zoom level.</span></span>  
  
4.  <span data-ttu-id="63c66-269">Clique na seta para baixo em TileLayer1 e em **Propriedades da Peça**.</span><span class="sxs-lookup"><span data-stu-id="63c66-269">Click the down arrow on TileLayer1, and then click **Tile Properties**.</span></span>  
  
5.  <span data-ttu-id="63c66-270">Em **Tipo**, selecione **Aéreo**.</span><span class="sxs-lookup"><span data-stu-id="63c66-270">In **Type**, select **Aerial**.</span></span> <span data-ttu-id="63c66-271">A vista aérea não contém texto.</span><span class="sxs-lookup"><span data-stu-id="63c66-271">The aerial view does not contain text.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="5-make-a-layer-transparent"></a><a name="Transparent"></a><span data-ttu-id="63c66-272">5. tornar uma camada transparente</span><span class="sxs-lookup"><span data-stu-id="63c66-272">5. Make a Layer Transparent</span></span>  
 <span data-ttu-id="63c66-273">Para deixar que os itens em uma camada sejam exibidos por outra camada, você pode ajustar a ordem de camadas e a transparência de cada camada para obter o efeito desejado.</span><span class="sxs-lookup"><span data-stu-id="63c66-273">To let the items on one layer show through another layer, you can adjust the order of layers and the transparency of each layer to get the effect that you want.</span></span>  
  
#### <a name="to-set-the-transparency-of-a-layer"></a><span data-ttu-id="63c66-274">Para definir a transparência de uma camada</span><span class="sxs-lookup"><span data-stu-id="63c66-274">To set the transparency of a layer</span></span>  
  
1.  <span data-ttu-id="63c66-275">Alterne para o modo Design.</span><span class="sxs-lookup"><span data-stu-id="63c66-275">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="63c66-276">Clique duas vezes no mapa para exibir o painel **Camada do Mapa** .</span><span class="sxs-lookup"><span data-stu-id="63c66-276">Double-click the map to display the **Map Layer** pane.</span></span>  
  
3.  <span data-ttu-id="63c66-277">Clique na seta para baixo em PolygonLayer1 e em **Dados da Camada**.</span><span class="sxs-lookup"><span data-stu-id="63c66-277">Click the down arrow on PolygonLayer1, and then click **Layer Data**.</span></span> <span data-ttu-id="63c66-278">A caixa de diálogo **Mapear Propriedades de Camada do Polígono** aparece.</span><span class="sxs-lookup"><span data-stu-id="63c66-278">The **Map Polygon Layer Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="63c66-279">Clique em **Visibilidade**.</span><span class="sxs-lookup"><span data-stu-id="63c66-279">Click **Visibility**.</span></span>  
  
5.  <span data-ttu-id="63c66-280">Em **Transparência (%)**, digite **30**.</span><span class="sxs-lookup"><span data-stu-id="63c66-280">In **Transparency (%)**, type **30**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
 <span data-ttu-id="63c66-281">A superfície de design exibe os municípios como semitransparentes.</span><span class="sxs-lookup"><span data-stu-id="63c66-281">The design surface displays the counties as semi-transparent.</span></span>  
  
##  <a name="6-vary-county-color-based-on-sales"></a><a name="Vary"></a><span data-ttu-id="63c66-282">6. variar a cor do município com base nas vendas</span><span class="sxs-lookup"><span data-stu-id="63c66-282">6. Vary County Color Based on Sales</span></span>  
 <span data-ttu-id="63c66-283">Cada município na camada do polígono tem uma cor diferente porque o processador de relatório atribui um valor de cor automaticamente da paleta de cores com base no tema que você escolheu na última página do assistente de mapa.</span><span class="sxs-lookup"><span data-stu-id="63c66-283">Each county on the polygon layer has a different color because the report processor automatically assigns a color value from the color palette based on the theme that you chose on the last page of the map wizard.</span></span>  
  
 <span data-ttu-id="63c66-284">Nas etapas a seguir, especifique uma regra de cor para associar cores específicas a um intervalo de vendas de lojas para cada município.</span><span class="sxs-lookup"><span data-stu-id="63c66-284">In the following steps, specify a color rule to associate specific colors with a range of store sales for each county.</span></span> <span data-ttu-id="63c66-285">As cores vermelho-amarelo-verde indicam vendas altas-médias-baixas relativas.</span><span class="sxs-lookup"><span data-stu-id="63c66-285">The colors red-yellow-green indicate relative high-middle-low sales.</span></span> <span data-ttu-id="63c66-286">Formate a escala de cores para mostrar a moeda.</span><span class="sxs-lookup"><span data-stu-id="63c66-286">Format the color scale to show currency.</span></span> <span data-ttu-id="63c66-287">Exiba os intervalos de vendas anuais em uma nova legenda.</span><span class="sxs-lookup"><span data-stu-id="63c66-287">Display the annual sales ranges in a new legend.</span></span> <span data-ttu-id="63c66-288">Para municípios que não contêm lojas, não use nenhuma cor para mostrar que não há dados associados.</span><span class="sxs-lookup"><span data-stu-id="63c66-288">For counties that do not contain stores, use no color to show that there is no associated data.</span></span>  
  
###  <a name="6a-build-a-relationship-between-spatial-and-analytical-data"></a><a name="Relationship"></a><span data-ttu-id="63c66-289">6a.</span><span class="sxs-lookup"><span data-stu-id="63c66-289">6a.</span></span> <span data-ttu-id="63c66-290">Criar um relacionamento entre dados espaciais e analíticos</span><span class="sxs-lookup"><span data-stu-id="63c66-290">Build a Relationship between Spatial and Analytical Data</span></span>  
 <span data-ttu-id="63c66-291">Para variar as formas do município por cor, com base em dados analíticos, primeiro associe os dados analíticos aos dados espaciais.</span><span class="sxs-lookup"><span data-stu-id="63c66-291">To vary the county shapes by color based on analytical data, you first must associate the analytical data with the spatial data.</span></span> <span data-ttu-id="63c66-292">Neste tutorial, você usará o nome do município para correspondência.</span><span class="sxs-lookup"><span data-stu-id="63c66-292">In this tutorial, you will use the county name to match on.</span></span>  
  
##### <a name="to-build-a-relationship-between-spatial-data-and-analytical-data"></a><span data-ttu-id="63c66-293">Para criar uma relação entre os dados espaciais e os dados analíticos</span><span class="sxs-lookup"><span data-stu-id="63c66-293">To build a relationship between spatial data and analytical data</span></span>  
  
1.  <span data-ttu-id="63c66-294">Alterne para o modo Design.</span><span class="sxs-lookup"><span data-stu-id="63c66-294">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="63c66-295">Clique duas vezes no mapa para exibir o painel **Camada do Mapa** .</span><span class="sxs-lookup"><span data-stu-id="63c66-295">Double-click the map to display the **Map Layer** pane.</span></span>  
  
3.  <span data-ttu-id="63c66-296">Clique na seta para baixo em PolygonLayer1 e em **Dados da Camada**.</span><span class="sxs-lookup"><span data-stu-id="63c66-296">Click the down arrow on PolygonLayer1, and then click **Layer Data**.</span></span> <span data-ttu-id="63c66-297">A caixa de diálogo **Mapear Propriedades de Camada do Polígono** aparece.</span><span class="sxs-lookup"><span data-stu-id="63c66-297">The **Map Polygon Layer Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="63c66-298">Clique em **Dados Analíticos**.</span><span class="sxs-lookup"><span data-stu-id="63c66-298">Click **Analytical data**.</span></span>  
  
5.  <span data-ttu-id="63c66-299">Na lista suspensa, selecione DataSet1.</span><span class="sxs-lookup"><span data-stu-id="63c66-299">From the drop-down list, select DataSet1.</span></span> <span data-ttu-id="63c66-300">Esse conjunto de dados foi criado pelo assistente quando você especificou a consulta de dados espaciais para os municípios.</span><span class="sxs-lookup"><span data-stu-id="63c66-300">This dataset was created by the wizard when you specified the spatial data query for the counties.</span></span>  
  
6.  <span data-ttu-id="63c66-301">Em **Campos a serem associados**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="63c66-301">In **Fields to match on**, click **Add**.</span></span> <span data-ttu-id="63c66-302">Uma nova linha será adicionada.</span><span class="sxs-lookup"><span data-stu-id="63c66-302">A new row is added.</span></span>  
  
7.  <span data-ttu-id="63c66-303">Em **Do conjunto de dados espacial**, na lista suspensa, clique em COUNTYNAME.</span><span class="sxs-lookup"><span data-stu-id="63c66-303">In **From spatial dataset**, from the drop-down list, click COUNTYNAME.</span></span>  
  
8.  <span data-ttu-id="63c66-304">Em **Do conjunto de dados analítico**, na lista suspensa, clique em [County].</span><span class="sxs-lookup"><span data-stu-id="63c66-304">In **From analytical dataset**, from the drop-down list, click [County].</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="63c66-305">Visualize o relatório.</span><span class="sxs-lookup"><span data-stu-id="63c66-305">Preview the report.</span></span>  
  
 <span data-ttu-id="63c66-306">Ao especificar um campo de correspondência com base na fonte de dados espaciais e no conjunto de dados analítico, você permite que o processador de relatório agrupe dados analíticos com base nos elementos do mapa.</span><span class="sxs-lookup"><span data-stu-id="63c66-306">By specifying a match field from the spatial data source and from the analytical dataset, you enable the report processor to group analytical data based on the map elements.</span></span> <span data-ttu-id="63c66-307">Um elemento de mapa com ligação de dados tem uma correspondência para os valores especificados.</span><span class="sxs-lookup"><span data-stu-id="63c66-307">A data-bound map element has a successful match for the values that you specified.</span></span>  
  
 <span data-ttu-id="63c66-308">Cada município que contém uma loja tem uma cor baseada na paleta de cores para o estilo escolhido no assistente.</span><span class="sxs-lookup"><span data-stu-id="63c66-308">Each county that contains a store has a color that is based on the color palette for the style that you chose in the wizard.</span></span>  
  
###  <a name="6b-specify-color-rules-for-polygons"></a><a name="ColorRules"></a><span data-ttu-id="63c66-309">6B.</span><span class="sxs-lookup"><span data-stu-id="63c66-309">6b.</span></span> <span data-ttu-id="63c66-310">Especificar as regras de cores para polígonos</span><span class="sxs-lookup"><span data-stu-id="63c66-310">Specify Color Rules for Polygons</span></span>  
 <span data-ttu-id="63c66-311">Para criar uma regra que varia a cor de cada município baseada em vendas da loja, você deve especificar os valores de intervalo, o número de divisões dentro daquele intervalo que você deseja exibir, e as cores a serem usadas.</span><span class="sxs-lookup"><span data-stu-id="63c66-311">To create a rule that varies the color of each county based store sales, you must specify the range values, the number of divisions within that range that you want to display, and the colors to use.</span></span>  
  
##### <a name="to-specify-color-rules-for-all-polygons-that-have-associated-data"></a><span data-ttu-id="63c66-312">Para especificar regras de cores para todos os polígonos com dados associados</span><span class="sxs-lookup"><span data-stu-id="63c66-312">To specify color rules for all polygons that have associated data</span></span>  
  
1.  <span data-ttu-id="63c66-313">Alterne para o modo Design.</span><span class="sxs-lookup"><span data-stu-id="63c66-313">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="63c66-314">Clique na seta para baixo em PolygonLayer1 e clique em **Regra de Cor do Polígono**.</span><span class="sxs-lookup"><span data-stu-id="63c66-314">Click the down arrow on PolygonLayer1, and then click **Polygon Color Rule**.</span></span> <span data-ttu-id="63c66-315">A caixa de diálogo **Mapear Propriedades de Regras de Cor** é aberta.</span><span class="sxs-lookup"><span data-stu-id="63c66-315">The **Map Color Rules Properties** dialog box opens.</span></span> <span data-ttu-id="63c66-316">Observe que a opção de regra de cor **Visualizar dados usando a paleta de cores** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="63c66-316">Notice that the color rule option **Visualize data by using color palette** is selected.</span></span> <span data-ttu-id="63c66-317">Esta opção foi definida no assistente.</span><span class="sxs-lookup"><span data-stu-id="63c66-317">This option was set by the wizard.</span></span>  
  
3.  <span data-ttu-id="63c66-318">Selecione **Visualizar dados usando intervalos de cores**.</span><span class="sxs-lookup"><span data-stu-id="63c66-318">Select **Visualize data by using color ranges**.</span></span> <span data-ttu-id="63c66-319">A opção da paleta é substituída pelas opções de cor inicial, cor intermediária e cor final.</span><span class="sxs-lookup"><span data-stu-id="63c66-319">The palette option is replaced by start color, middle color, and end color options.</span></span>  
  
4.  <span data-ttu-id="63c66-320">Defina valores de intervalo para vendas por município.</span><span class="sxs-lookup"><span data-stu-id="63c66-320">Define range values for sales per county.</span></span> <span data-ttu-id="63c66-321">Em **Campo de dados**, na lista suspensa, selecione `[Sum(Sales)]`.</span><span class="sxs-lookup"><span data-stu-id="63c66-321">In **Data field**, from the drop-down list, select `[Sum(Sales)]`.</span></span>  
  
5.  <span data-ttu-id="63c66-322">Para alterar o formato para exibir moeda em milhares, altere a expressão para o seguinte: `=Sum(Fields!Sales.Value)/1000`</span><span class="sxs-lookup"><span data-stu-id="63c66-322">To change the format to display currency in thousands, change the expression to the following: `=Sum(Fields!Sales.Value)/1000`</span></span>  
  
6.  <span data-ttu-id="63c66-323">Altere **Cor inicial** para **Vermelho**.</span><span class="sxs-lookup"><span data-stu-id="63c66-323">Change **Start color** to **Red**.</span></span>  
  
7.  <span data-ttu-id="63c66-324">Altere **Cor final** para **Verde**.</span><span class="sxs-lookup"><span data-stu-id="63c66-324">Change **End color** to **Green**.</span></span>  
  
     <span data-ttu-id="63c66-325">**Vermelho** representa baixos valores de vendas, **Amarelo** representa valores de vendas intermediários e **Verde** representa valores de vendas altos.</span><span class="sxs-lookup"><span data-stu-id="63c66-325">**Red** represents low sales values, **Yellow** represents middle sales values, and **Green** represents high sales values.</span></span> <span data-ttu-id="63c66-326">O processador de relatório calcula um intervalo de cores com base nesses valores e as opções que você escolhe na página **Distribuição** .</span><span class="sxs-lookup"><span data-stu-id="63c66-326">The report processor calculates a range of colors based on these values and the options that you choose on the **Distribution** page.</span></span>  
  
8.  <span data-ttu-id="63c66-327">Clique em **Distribuição**.</span><span class="sxs-lookup"><span data-stu-id="63c66-327">Click **Distribution**.</span></span>  
  
9. <span data-ttu-id="63c66-328">Verifique se o tipo de distribuição é **Ideal**.</span><span class="sxs-lookup"><span data-stu-id="63c66-328">Verify that the distribution type is **Optimal**.</span></span> <span data-ttu-id="63c66-329">Para a expressão da etapa 5, a distribuição ideal divide os valores em subintervalos que equilibram o número de itens em cada intervalo e abrangem cada intervalo.</span><span class="sxs-lookup"><span data-stu-id="63c66-329">For the expression from step 5, optimal distribution divides the values into subranges that balance the number of items in each range and the span for each range.</span></span>  
  
10. <span data-ttu-id="63c66-330">Aceite os valores padrão para outras opções nesta página.</span><span class="sxs-lookup"><span data-stu-id="63c66-330">Accept the default values for other options on this page.</span></span> <span data-ttu-id="63c66-331">Quando você selecionar o tipo de distribuição ideal, o número de subintervalos será calculado quando o relatório for executado.</span><span class="sxs-lookup"><span data-stu-id="63c66-331">When you select the optimal distribution type, the number of subranges are calculated when the report runs.</span></span>  
  
11. <span data-ttu-id="63c66-332">Clique em **Legenda**.</span><span class="sxs-lookup"><span data-stu-id="63c66-332">Click **Legend**.</span></span>  
  
12. <span data-ttu-id="63c66-333">Em **Opções de escala de cores**, verifique se a opção **Mostrar em escala de cores** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="63c66-333">In **Color scale options**, verify that **Show in color scale** is selected.</span></span>  
  
13. <span data-ttu-id="63c66-334">Em **Mostrar nesta legenda**, selecione a linha em branco na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="63c66-334">In **Show in this legend**, from the drop-down list, select the blank line.</span></span> <span data-ttu-id="63c66-335">Por enquanto, você mostrará apenas os intervalos de cores na escala de cores.</span><span class="sxs-lookup"><span data-stu-id="63c66-335">For now, you will show the color ranges only in the color scale.</span></span>  
  
14. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
 <span data-ttu-id="63c66-336">A escala de cores exibe cinco cores: vermelho, laranja, amarelo, verde-amarelado e verde.</span><span class="sxs-lookup"><span data-stu-id="63c66-336">The color scale displays five colors: red, orange, yellow, yellow green, and green.</span></span> <span data-ttu-id="63c66-337">Cada cor representa um intervalo de vendas que é calculado automaticamente com base nas vendas por município.</span><span class="sxs-lookup"><span data-stu-id="63c66-337">Each color represents a sales range that is automatically calculated based on the sales by county.</span></span>  
  
###  <a name="6c-format-the-data-in-the-color-scale-as-currency"></a><a name="ColorScale"></a><span data-ttu-id="63c66-338">6c.</span><span class="sxs-lookup"><span data-stu-id="63c66-338">6c.</span></span> <span data-ttu-id="63c66-339">Formatar os dados na escala de cores como moeda</span><span class="sxs-lookup"><span data-stu-id="63c66-339">Format the Data in the Color Scale as Currency</span></span>  
 <span data-ttu-id="63c66-340">Por padrão, os dados têm um formato geral.</span><span class="sxs-lookup"><span data-stu-id="63c66-340">By default, data has a general format.</span></span> <span data-ttu-id="63c66-341">Você pode aplicar formatos personalizados.</span><span class="sxs-lookup"><span data-stu-id="63c66-341">You can apply custom formats.</span></span>  
  
##### <a name="to-set-the-format-for-the-color-scale"></a><span data-ttu-id="63c66-342">Para definir o formato da escala de cores</span><span class="sxs-lookup"><span data-stu-id="63c66-342">To set the format for the color scale</span></span>  
  
1.  <span data-ttu-id="63c66-343">Clique com o botão direito do mouse na escala de cores e clique em **Propriedades da Escala de Cores**.</span><span class="sxs-lookup"><span data-stu-id="63c66-343">Right-click the color scale, and then click **Color Scale Properties**.</span></span>  
  
2.  <span data-ttu-id="63c66-344">Clique em **Número**.</span><span class="sxs-lookup"><span data-stu-id="63c66-344">Click **Number**.</span></span>  
  
3.  <span data-ttu-id="63c66-345">Em **Categoria**, clique em **Moeda**.</span><span class="sxs-lookup"><span data-stu-id="63c66-345">In **Category**, click **Currency**.</span></span>  
  
4.  <span data-ttu-id="63c66-346">Em **Casas decimais**, digite **0**.</span><span class="sxs-lookup"><span data-stu-id="63c66-346">In **Decimal places**, type **0**.</span></span> <span data-ttu-id="63c66-347">Esse formato especifica que não haverá nenhuma casa decimal para moeda.</span><span class="sxs-lookup"><span data-stu-id="63c66-347">This format specifies no decimal places for currency.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="63c66-348">Visualize o relatório.</span><span class="sxs-lookup"><span data-stu-id="63c66-348">Preview the report.</span></span>  
  
 <span data-ttu-id="63c66-349">A escala de cores exibe as vendas anuais no formato de moeda para cada intervalo.</span><span class="sxs-lookup"><span data-stu-id="63c66-349">The color scale displays annual sales in currency format for each range.</span></span>  
  
###  <a name="6d-create-a-new-legend"></a><a name="NewLegend"></a><span data-ttu-id="63c66-350">6D.</span><span class="sxs-lookup"><span data-stu-id="63c66-350">6d.</span></span> <span data-ttu-id="63c66-351">Criar uma nova legenda</span><span class="sxs-lookup"><span data-stu-id="63c66-351">Create a New Legend</span></span>  
 <span data-ttu-id="63c66-352">Por padrão, todas as regras são exibidas na primeira legenda.</span><span class="sxs-lookup"><span data-stu-id="63c66-352">By default, all rules display in the first legend.</span></span> <span data-ttu-id="63c66-353">Para melhorar a exibição de um mapa, adicione legendas.</span><span class="sxs-lookup"><span data-stu-id="63c66-353">To improve the display for a map, you can add legends.</span></span>  
  
 <span data-ttu-id="63c66-354">Para alterar a exibição padrão, há duas etapas: crie uma nova legenda e associe os resultados da regra para uma camada do mapa à nova legenda.</span><span class="sxs-lookup"><span data-stu-id="63c66-354">To change the default display, there are two steps: create a new legend and then associate the rule results for a map layer with the new legend.</span></span>  
  
##### <a name="to-create-a-new-legend"></a><span data-ttu-id="63c66-355">Para criar uma nova legenda</span><span class="sxs-lookup"><span data-stu-id="63c66-355">To create a new legend</span></span>  
  
1.  <span data-ttu-id="63c66-356">Alterne para o modo Design.</span><span class="sxs-lookup"><span data-stu-id="63c66-356">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="63c66-357">Clique com o botão direito do mouse no mapa fora do visor e clique em **Adicionar Legenda**.</span><span class="sxs-lookup"><span data-stu-id="63c66-357">Right-click the map outside the viewport, and then click **Add Legend**.</span></span> <span data-ttu-id="63c66-358">Uma nova legenda será adicionada ao mapa em um local padrão.</span><span class="sxs-lookup"><span data-stu-id="63c66-358">A new legend is added to the map at a default location.</span></span>  
  
3.  <span data-ttu-id="63c66-359">Clique com o botão direito do mouse na legenda e clique em **Propriedades da Legenda**.</span><span class="sxs-lookup"><span data-stu-id="63c66-359">Right-click the legend, and then click **Legend Properties**.</span></span>  
  
4.  <span data-ttu-id="63c66-360">Em **Opções de Posição**, clique no local que especifica onde você deseja que a legenda apareça em relação ao visor.</span><span class="sxs-lookup"><span data-stu-id="63c66-360">In **Position options**, click the location that specifies where you want the legend to appear relative to the viewport.</span></span> <span data-ttu-id="63c66-361">O mapa na superfície de design é alterado para mostrar o efeito de suas seleções.</span><span class="sxs-lookup"><span data-stu-id="63c66-361">The map on the design surface changes to show the effect of your selections.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="63c66-362">Clique em **Título** na legenda para selecionar o título de legenda.</span><span class="sxs-lookup"><span data-stu-id="63c66-362">Click **Title** on the legend to select the legend title.</span></span>  
  
7.  <span data-ttu-id="63c66-363">Clique em **Título** novamente para entrar no modo de inserção de texto.</span><span class="sxs-lookup"><span data-stu-id="63c66-363">Click **Title** again to enter insert mode for the text.</span></span> <span data-ttu-id="63c66-364">Substitua o **Título** por **Vendas (Milhares)** e clique fora do texto.</span><span class="sxs-lookup"><span data-stu-id="63c66-364">Replace **Title** by **Sales (Thousands)**, and then click outside the text.</span></span>  
  
 <span data-ttu-id="63c66-365">A legenda se expande para exibir o título.</span><span class="sxs-lookup"><span data-stu-id="63c66-365">The legend expands to display the title.</span></span>  
  
###  <a name="6e-associate-legend-and-color-rules"></a><a name="Associate"></a><span data-ttu-id="63c66-366">6e.</span><span class="sxs-lookup"><span data-stu-id="63c66-366">6e.</span></span> <span data-ttu-id="63c66-367">Associar regras de cores e legenda</span><span class="sxs-lookup"><span data-stu-id="63c66-367">Associate Legend and Color Rules</span></span>  
 <span data-ttu-id="63c66-368">Cada legenda pode exibir um ou mais conjuntos de resultados de regra.</span><span class="sxs-lookup"><span data-stu-id="63c66-368">Each legend can display one or more sets of rule results.</span></span>  
  
##### <a name="to-associate-a-legend-with-color-rules"></a><span data-ttu-id="63c66-369">Para associar uma legenda a regras de cores</span><span class="sxs-lookup"><span data-stu-id="63c66-369">To associate a legend with color rules</span></span>  
  
1.  <span data-ttu-id="63c66-370">Clique duas vezes no mapa para exibir o painel **Camada do Mapa** .</span><span class="sxs-lookup"><span data-stu-id="63c66-370">Double-click the map to display the **Map Layer** pane.</span></span>  
  
2.  <span data-ttu-id="63c66-371">Clique na seta para baixo em PolygonLayer1 e clique em **Regra de Cor do Polígono**.</span><span class="sxs-lookup"><span data-stu-id="63c66-371">Click the down arrow on PolygonLayer1, and then click **Polygon Color Rule**.</span></span> <span data-ttu-id="63c66-372">A caixa de diálogo **Mapear Propriedades de Regras de Cor** é aberta.</span><span class="sxs-lookup"><span data-stu-id="63c66-372">The **Map Color Rules Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="63c66-373">Clique em **Legenda**.</span><span class="sxs-lookup"><span data-stu-id="63c66-373">Click **Legend**.</span></span>  
  
4.  <span data-ttu-id="63c66-374">Em **Opções de escala de cores**, limpe **Mostrar em escala de cores**.</span><span class="sxs-lookup"><span data-stu-id="63c66-374">In **Color scale options**, clear **Show in color scale**.</span></span>  
  
5.  <span data-ttu-id="63c66-375">Em **Opções de legenda**, na lista suspensa, selecione Legend2.</span><span class="sxs-lookup"><span data-stu-id="63c66-375">In **Legend options**, from the drop-down list, select Legend2.</span></span> <span data-ttu-id="63c66-376">A opção de texto da legenda aparece.</span><span class="sxs-lookup"><span data-stu-id="63c66-376">The legend text option appears.</span></span> <span data-ttu-id="63c66-377">Por padrão, texto de legenda é formatado com uma cadeia de formato geral do [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="63c66-377">By default, legend text is formatted with a general [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] format string.</span></span> <span data-ttu-id="63c66-378">Os 0 em N0 não especifica nenhum dígito decimal.</span><span class="sxs-lookup"><span data-stu-id="63c66-378">The 0 in N0 specifies no decimal digits.</span></span>  
  
6.  <span data-ttu-id="63c66-379">Em **texto da legenda**, use o seguinte formato para especificar a moeda sem dígitos decimais:`#FROMVALUE {C0} - #TOVALUE {C0}`</span><span class="sxs-lookup"><span data-stu-id="63c66-379">In **Legend text**, use the following format to specify currency with no decimal digits: `#FROMVALUE {C0} - #TOVALUE {C0}`</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="63c66-380">Na superfície de design, a legenda exibe os intervalos de cores com dados de exemplo formatados como moeda.</span><span class="sxs-lookup"><span data-stu-id="63c66-380">On the design surface, the legend displays the color ranges with sample data formatted as currency.</span></span>  
  
8.  <span data-ttu-id="63c66-381">Visualize o relatório.</span><span class="sxs-lookup"><span data-stu-id="63c66-381">Preview the report.</span></span>  
  
 <span data-ttu-id="63c66-382">Os municípios que têm lojas e vendas associadas são exibidos de acordo com as regras de cores.</span><span class="sxs-lookup"><span data-stu-id="63c66-382">The counties that have associated stores and sales display according to the color rules.</span></span> <span data-ttu-id="63c66-383">Municípios que não têm nenhuma venda não têm cores.</span><span class="sxs-lookup"><span data-stu-id="63c66-383">Counties that have no sales have no color.</span></span>  
  
###  <a name="6f-change-color-for-counties-with-no-data"></a><a name="NoData"></a><span data-ttu-id="63c66-384">6f.</span><span class="sxs-lookup"><span data-stu-id="63c66-384">6f.</span></span> <span data-ttu-id="63c66-385">Alterar a cor dos municípios para os quais não há dados</span><span class="sxs-lookup"><span data-stu-id="63c66-385">Change Color for Counties with No Data</span></span>  
 <span data-ttu-id="63c66-386">Você pode definir as opções de exibição padrão para todos os elementos de mapas em uma camada.</span><span class="sxs-lookup"><span data-stu-id="63c66-386">You can set the default display options for all map elements on a layer.</span></span> <span data-ttu-id="63c66-387">As regras de cores têm precedência sobre essas opções de exibição.</span><span class="sxs-lookup"><span data-stu-id="63c66-387">Color rules take precedence over these display options.</span></span>  
  
##### <a name="to-set-the-display-properties-for-all-elements-on-a-layer"></a><span data-ttu-id="63c66-388">Para definir as propriedades de exibição para todos os elementos em uma camada</span><span class="sxs-lookup"><span data-stu-id="63c66-388">To set the display properties for all elements on a layer</span></span>  
  
1.  <span data-ttu-id="63c66-389">Alterne para o modo Design.</span><span class="sxs-lookup"><span data-stu-id="63c66-389">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="63c66-390">Clique duas vezes no mapa para exibir o painel **Camada do Mapa** .</span><span class="sxs-lookup"><span data-stu-id="63c66-390">Double-click the map to display the **Map Layer** pane.</span></span>  
  
3.  <span data-ttu-id="63c66-391">Clique na seta para baixo em PolygonLayer1 e clique em **Propriedades do Polígono**.</span><span class="sxs-lookup"><span data-stu-id="63c66-391">Click the down arrow on PolygonLayer1, and then click **Polygon Properties**.</span></span> <span data-ttu-id="63c66-392">A caixa de diálogo **Mapear Propriedades do Polígono** aparece.</span><span class="sxs-lookup"><span data-stu-id="63c66-392">The **Map Polygon Properties** dialog box opens.</span></span> <span data-ttu-id="63c66-393">As opções de exibição definidas nesta caixa de diálogo se aplicam a todos os polígonos na camada antes de as opções de exibição baseadas em regras serem aplicadas.</span><span class="sxs-lookup"><span data-stu-id="63c66-393">Display options set in this dialog box apply to all polygons on the layer before rule-based display options are applied.</span></span>  
  
4.  <span data-ttu-id="63c66-394">Clique em **Preenchimento**.</span><span class="sxs-lookup"><span data-stu-id="63c66-394">Click **Fill**.</span></span>  
  
5.  <span data-ttu-id="63c66-395">Verifique se o estilo de preenchimento é **Sólido.**</span><span class="sxs-lookup"><span data-stu-id="63c66-395">Verify that the fill style is **Solid.**</span></span> <span data-ttu-id="63c66-396">Gradações e padrões se aplicam a todas as cores.</span><span class="sxs-lookup"><span data-stu-id="63c66-396">Gradients and patterns apply to all colors.</span></span>  
  
6.  <span data-ttu-id="63c66-397">Em **Cor**, clique na seta para baixo e clique em **Azul Claro Acinzentado**.</span><span class="sxs-lookup"><span data-stu-id="63c66-397">In **Color**, click the down arrow, and then click **Light Steel Blue**.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="63c66-398">Visualize o relatório.</span><span class="sxs-lookup"><span data-stu-id="63c66-398">Preview the report.</span></span>  
  
 <span data-ttu-id="63c66-399">Municípios sem dados associados são exibidos em azul.</span><span class="sxs-lookup"><span data-stu-id="63c66-399">Counties that have no associated data display as blue.</span></span> <span data-ttu-id="63c66-400">Somente os municípios com dados analíticos associados são exibidos nas cores de **Vermelho** a **Green** das regras de cores especificadas.</span><span class="sxs-lookup"><span data-stu-id="63c66-400">Only counties that have associated analytical data appear in the **Red** through **Green** colors from the color rules that you specified.</span></span>  
  
##  <a name="7-add-a-custom-point"></a><a name="CustomPoint"></a><span data-ttu-id="63c66-401">7. adicionar um ponto personalizado</span><span class="sxs-lookup"><span data-stu-id="63c66-401">7. Add a Custom Point</span></span>  
 <span data-ttu-id="63c66-402">Para representar uma nova loja que ainda não foi construída, especifique um ponto e use o tipo de marcador **PushPin** .</span><span class="sxs-lookup"><span data-stu-id="63c66-402">To represent a new store that has not yet been built, specify a point and use the **PushPin** marker type.</span></span>  
  
#### <a name="to-add-a-custom-point"></a><span data-ttu-id="63c66-403">Para adicionar um ponto personalizado</span><span class="sxs-lookup"><span data-stu-id="63c66-403">To add a custom point</span></span>  
  
1.  <span data-ttu-id="63c66-404">Alterne para o modo Design.</span><span class="sxs-lookup"><span data-stu-id="63c66-404">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="63c66-405">Clique duas vezes no mapa para exibir o painel **Camada do Mapa** .</span><span class="sxs-lookup"><span data-stu-id="63c66-405">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="63c66-406">Na barra de ferramentas, clique em **Adicionar Camada**e em **Camada de Ponto**.</span><span class="sxs-lookup"><span data-stu-id="63c66-406">On the toolbar, click **Add Layer**, and then click **Point Layer**.</span></span>  
  
     <span data-ttu-id="63c66-407">Uma nova camada de ponto é adicionada ao mapa.</span><span class="sxs-lookup"><span data-stu-id="63c66-407">A new point layer is added to the map.</span></span> <span data-ttu-id="63c66-408">Por padrão, a camada de ponto tem o tipo de dados espacial **Inserido**.</span><span class="sxs-lookup"><span data-stu-id="63c66-408">By default, the point layer has spatial data type **Embedded**.</span></span>  
  
3.  <span data-ttu-id="63c66-409">Clique na seta para baixo em PointLayer2 e em **Adicionar Ponto**.</span><span class="sxs-lookup"><span data-stu-id="63c66-409">Click the down arrow on PointLayer2, and then click **Add Point**.</span></span>  
  
4.  <span data-ttu-id="63c66-410">Mova o ponteiro sobre o visor do mapa.</span><span class="sxs-lookup"><span data-stu-id="63c66-410">Move the pointer over the map viewport.</span></span> <span data-ttu-id="63c66-411">O cursor se transforma em uma cruz.</span><span class="sxs-lookup"><span data-stu-id="63c66-411">The cursor changes to crosshairs.</span></span>  
  
5.  <span data-ttu-id="63c66-412">Clique no local no mapa em que você deseja adicionar um ponto.</span><span class="sxs-lookup"><span data-stu-id="63c66-412">Click the location on the map where you want to add a point.</span></span> <span data-ttu-id="63c66-413">Neste tutorial, clique em um local em um município no início da rota.</span><span class="sxs-lookup"><span data-stu-id="63c66-413">In this tutorial, click a location in a county next to the start of the route.</span></span> <span data-ttu-id="63c66-414">Um ponto marcado por um círculo é adicionado à camada no local em que você clicou.</span><span class="sxs-lookup"><span data-stu-id="63c66-414">A point marked by a circle is added to the layer at the location where you clicked.</span></span> <span data-ttu-id="63c66-415">Por padrão, o ponto é selecionado.</span><span class="sxs-lookup"><span data-stu-id="63c66-415">By default, the point is selected.</span></span>  
  
6.  <span data-ttu-id="63c66-416">Clique com o botão direito do mouse no ponto adicionado e clique em **Propriedades de Ponto Inserido**.</span><span class="sxs-lookup"><span data-stu-id="63c66-416">Right-click the point you added, and then click **Embedded Point Properties**.</span></span>  
  
7.  <span data-ttu-id="63c66-417">Selecione a opção **Substituir opções de ponto para esta camada**.</span><span class="sxs-lookup"><span data-stu-id="63c66-417">Select the option **Override point options for this layer**.</span></span> <span data-ttu-id="63c66-418">Páginas adicionais aparecem na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="63c66-418">Additional pages appear in the dialog box.</span></span> <span data-ttu-id="63c66-419">Os valores que você definiu aqui têm precedência sobre as opções de exibição da camada ou para regras de cores.</span><span class="sxs-lookup"><span data-stu-id="63c66-419">Values that you set here take precedence over display options for the layer or for color rules.</span></span>  
  
8.  <span data-ttu-id="63c66-420">Clique em **Marcador**.</span><span class="sxs-lookup"><span data-stu-id="63c66-420">Click **Marker**.</span></span>  
  
9. <span data-ttu-id="63c66-421">Para **Tipo de marcador**, selecione **Estrela**.</span><span class="sxs-lookup"><span data-stu-id="63c66-421">For **Marker type**, select **Star**.</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
11. <span data-ttu-id="63c66-422">Visualize o relatório.</span><span class="sxs-lookup"><span data-stu-id="63c66-422">Preview the report.</span></span>  
  
 <span data-ttu-id="63c66-423">O novo ponto adicionado aparece como um **Estrela**.</span><span class="sxs-lookup"><span data-stu-id="63c66-423">The new point you added appears as a **Star**.</span></span>  
  
#### <a name="to-add-a-label-for-the-custom-point"></a><span data-ttu-id="63c66-424">Para adicionar um rótulo ao ponto personalizado</span><span class="sxs-lookup"><span data-stu-id="63c66-424">To add a label for the custom point</span></span>  
  
1.  <span data-ttu-id="63c66-425">Alterne para o modo Design.</span><span class="sxs-lookup"><span data-stu-id="63c66-425">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="63c66-426">Clique com o botão direito do mouse no ponto recém-adicionado e clique em **Propriedades de Ponto Inserido**.</span><span class="sxs-lookup"><span data-stu-id="63c66-426">Right-click the point you just added, and then click **Embedded Point Properties**.</span></span>  
  
3.  <span data-ttu-id="63c66-427">Clique em **Rótulos**.</span><span class="sxs-lookup"><span data-stu-id="63c66-427">Click **Labels**.</span></span>  
  
4.  <span data-ttu-id="63c66-428">Em **Texto do rótulo**, digite **Nova Loja**.</span><span class="sxs-lookup"><span data-stu-id="63c66-428">In **Label text**, type **New Store**.</span></span>  
  
5.  <span data-ttu-id="63c66-429">Em **Posicionamento**, clique em **Superior**.</span><span class="sxs-lookup"><span data-stu-id="63c66-429">In **Placement**, click **Top**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="63c66-430">Visualize o relatório.</span><span class="sxs-lookup"><span data-stu-id="63c66-430">Preview the report.</span></span>  
  
 <span data-ttu-id="63c66-431">O rótulo aparece acima do local da loja.</span><span class="sxs-lookup"><span data-stu-id="63c66-431">The label appears above the store location.</span></span>  
  
##  <a name="center-the-map-view"></a><a name="CenterView"></a><span data-ttu-id="63c66-432">Centralizar a exibição do mapa</span><span class="sxs-lookup"><span data-stu-id="63c66-432">Center the Map View</span></span>  
 <span data-ttu-id="63c66-433">Altere o centro do visor do mapa e o nível de zoom.</span><span class="sxs-lookup"><span data-stu-id="63c66-433">Change the map viewport center and zoom level.</span></span>  
  
#### <a name="to-change-the-viewport"></a><span data-ttu-id="63c66-434">Para alterar o visor</span><span class="sxs-lookup"><span data-stu-id="63c66-434">To change the viewport</span></span>  
  
1.  <span data-ttu-id="63c66-435">Clique com o botão direito do mouse no visor do mapa clique em **Propriedades do Visor**.</span><span class="sxs-lookup"><span data-stu-id="63c66-435">Right-click the map viewport, and then click **Viewport Properties**.</span></span>  
  
2.  <span data-ttu-id="63c66-436">Clique em **Centralizar e Aplicar Zoom**.</span><span class="sxs-lookup"><span data-stu-id="63c66-436">Click **Center and Zoom**.</span></span>  
  
3.  <span data-ttu-id="63c66-437">Verifique se a opção **Definir um centro de exibição e um nível de zoom** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="63c66-437">Verify that the option **Set a view center and zoom level** is selected.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="63c66-438">Clique com o botão esquerdo do mouse no visor do mapa e arraste o centro do visor para o local desejado.</span><span class="sxs-lookup"><span data-stu-id="63c66-438">Left-click the map viewport, and drag the center of the viewport to the location that you want.</span></span>  
  
6.  <span data-ttu-id="63c66-439">Use a roda do mouse para alterar o nível de zoom do visor.</span><span class="sxs-lookup"><span data-stu-id="63c66-439">Use the mouse wheel to change the zoom level of the viewport.</span></span>  
  
7.  <span data-ttu-id="63c66-440">Visualize o relatório.</span><span class="sxs-lookup"><span data-stu-id="63c66-440">Preview the report.</span></span>  
  
 <span data-ttu-id="63c66-441">No modo Design, o mapa na superfície de exibição e a exibição se baseiam em dados de exemplo.</span><span class="sxs-lookup"><span data-stu-id="63c66-441">In Design view, the map on the display surface and the view is based on sample data.</span></span> <span data-ttu-id="63c66-442">No relatório renderizado, a exibição de mapa é centralizada na exibição especificada.</span><span class="sxs-lookup"><span data-stu-id="63c66-442">In the rendered report, the map view is centered on the view that you specified.</span></span>  
  
##  <a name="add-a-report-title"></a><a name="Title"></a><span data-ttu-id="63c66-443">Adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="63c66-443">Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="63c66-444">Para adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="63c66-444">To add a report title</span></span>  
  
1.  <span data-ttu-id="63c66-445">Na superfície de design, clique em **Clique para adicionar título**.</span><span class="sxs-lookup"><span data-stu-id="63c66-445">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="63c66-446">Digite **Vendas nas Lojas de Nova York** e clique fora da caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="63c66-446">Type **Sales in New York Stores** and then click outside the text box.</span></span>  
  
 <span data-ttu-id="63c66-447">Esse título aparecerá na parte superior do relatório.</span><span class="sxs-lookup"><span data-stu-id="63c66-447">This title will appear at the top of the report.</span></span> <span data-ttu-id="63c66-448">Os itens na parte superior do corpo do relatório quando não há cabeçalho de página definido são os equivalentes de um cabeçalho de relatório.</span><span class="sxs-lookup"><span data-stu-id="63c66-448">Items at the top of the report body when there is no page header defined are the equivalent of a report header.</span></span>  
  
##  <a name="save-the-report"></a><a name="Save"></a><span data-ttu-id="63c66-449">Salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="63c66-449">Save the Report</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="63c66-450">Para salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="63c66-450">To save the report</span></span>  
  
1.  <span data-ttu-id="63c66-451">Alterne para o modo Design.</span><span class="sxs-lookup"><span data-stu-id="63c66-451">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="63c66-452">No botão Construtor de Relatórios , clique em **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="63c66-452">From the Report Builder button, click **Save As**.</span></span>  
  
3.  <span data-ttu-id="63c66-453">Em **Nome**, digite **Vendas nas Lojas de Nova York**.</span><span class="sxs-lookup"><span data-stu-id="63c66-453">In **Name**, type **Store Sales in New York**.</span></span>  
  
 <span data-ttu-id="63c66-454">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="63c66-454">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="63c66-455">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="63c66-455">Next Steps</span></span>  
 <span data-ttu-id="63c66-456">Isso conclui o passo a passo da adição de um mapa ao seu relatório.</span><span class="sxs-lookup"><span data-stu-id="63c66-456">This concludes the walkthrough for how to add a map to your report.</span></span>  
  
 <span data-ttu-id="63c66-457">Para obter mais informações, consulte [mapas &#40;Construtor de relatórios e SSRS&#41;](report-design/maps-report-builder-and-ssrs.md) e a entrada de blog [cartográficas o ajuste de dados espaciais para SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=152771) em Blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="63c66-457">For more information, see [Maps &#40;Report Builder and SSRS&#41;](report-design/maps-report-builder-and-ssrs.md) and the blog entry [Cartographic Adjustment of Spatial Data for SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=152771) on blogs.msdn.com.</span></span>  
  
 <span data-ttu-id="63c66-458">Para obter mais tutoriais, consulte os [tutoriais &#40;Construtor de Relatórios&#41;](report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="63c66-458">For more tutorials, see [Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63c66-459">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="63c66-459">See Also</span></span>  
 <span data-ttu-id="63c66-460">[TUTORIAIS &#40;Construtor de Relatórios&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="63c66-460">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 <span data-ttu-id="63c66-461">[Construtor de Relatórios no SQL Server 2014](report-builder/report-builder-in-sql-server-2016.md) </span><span class="sxs-lookup"><span data-stu-id="63c66-461">[Report Builder in SQL Server 2014](report-builder/report-builder-in-sql-server-2016.md) </span></span>  
 <span data-ttu-id="63c66-462">[Assistente de mapa e assistente de camada do mapa &#40;Construtor de Relatórios e SSRS&#41;](report-design/map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="63c66-462">[Map Wizard and Map Layer Wizard &#40;Report Builder and SSRS&#41;](report-design/map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="63c66-463">Variar a exibição de polígono, linha e ponto por regras e dados analíticos &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="63c66-463">Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;</span></span>](report-design/vary-polygon-line-and-point-display-by-rules-and-analytical-data.md)  
  
  
