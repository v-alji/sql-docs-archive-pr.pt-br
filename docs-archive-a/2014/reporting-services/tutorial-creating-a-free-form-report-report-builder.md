---
title: 'Tutorial: Criando um relatório de formato livre (Construtor de Relatórios) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 87288b59-faf2-4b1d-a8e4-a7582baedf2f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 515b0d2566efa4e11216a28648338c7ec43f3950
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684033"
---
# <a name="tutorial-creating-a-free-form-report-report-builder"></a><span data-ttu-id="48eb7-102">Tutorial: criando um relatório de formato livre (Construtor de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="48eb7-102">Tutorial: Creating a Free Form Report (Report Builder)</span></span>
  <span data-ttu-id="48eb7-103">Este tutorial ensina a criar um relatório de formulário livre do SSRS que se parece com uma carta de formulários.</span><span class="sxs-lookup"><span data-stu-id="48eb7-103">This tutorial teaches you how to create an SSRS free form report that resembles a forms letter.</span></span> <span data-ttu-id="48eb7-104">Você pode organizar itens de relatório para criar um formulário com caixas de texto, imagens e outras regiões de dados.</span><span class="sxs-lookup"><span data-stu-id="48eb7-104">You can arrange report items to create a form with text boxes, images and other data regions.</span></span>

 <span data-ttu-id="48eb7-105">O relatório criado por você neste tutorial se baseia em dados de vendas de exemplo que estão incluídos no tutorial.</span><span class="sxs-lookup"><span data-stu-id="48eb7-105">The report you create in this tutorial is based on sample sales data that is included in the tutorial.</span></span> <span data-ttu-id="48eb7-106">O relatório agrupa informações por território e exibe o nome do gerente de vendas do território, bem como informações detalhadas e resumidas sobre as vendas.</span><span class="sxs-lookup"><span data-stu-id="48eb7-106">The report groups information by territory and displays the name of the sales manager for the territory as well as detailed and summary sales information.</span></span> <span data-ttu-id="48eb7-107">Você irá usar a região de dados da lista como a base do relatório de formato livre e, em seguida, adicionar um painel decorativo com uma imagem, um texto estático com dados inseridos, uma tabela para mostrar informações detalhadas e, opcionalmente, gráficos de pizza e de colunas para exibir informações resumidas.</span><span class="sxs-lookup"><span data-stu-id="48eb7-107">You will use the list data region as the foundation for the free form report, and then add a decorative panel with an image, static text with data inserted, a table to show detailed information, and optionally, pie and column charts to display summary information.</span></span>

##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="48eb7-108">O que você aprenderá</span><span class="sxs-lookup"><span data-stu-id="48eb7-108">What You Will Learn</span></span>
 <span data-ttu-id="48eb7-109">Neste tutorial, você aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="48eb7-109">In this tutorial, you will learn how to do the following:</span></span>

-   [<span data-ttu-id="48eb7-110">Criar um relatório em branco, uma fonte de dados e um conjunto de dados</span><span class="sxs-lookup"><span data-stu-id="48eb7-110">Create a Blank Report, Data Source, and Dataset</span></span>](#BlankReport)

-   [<span data-ttu-id="48eb7-111">Adicionar e configurar uma lista</span><span class="sxs-lookup"><span data-stu-id="48eb7-111">Add and Configure a List</span></span>](#List)

-   [<span data-ttu-id="48eb7-112">Adicionar gráficos</span><span class="sxs-lookup"><span data-stu-id="48eb7-112">Add Graphics</span></span>](#Graphics)

-   [<span data-ttu-id="48eb7-113">Adicionar texto de formato livre</span><span class="sxs-lookup"><span data-stu-id="48eb7-113">Add Free Form Text</span></span>](#Text)

-   [<span data-ttu-id="48eb7-114">Adicionar uma tabela para mostrar detalhes</span><span class="sxs-lookup"><span data-stu-id="48eb7-114">Add a Table to Show Details</span></span>](#Table)

-   [<span data-ttu-id="48eb7-115">Formatar dados</span><span class="sxs-lookup"><span data-stu-id="48eb7-115">Format Data</span></span>](#Format)

-   [<span data-ttu-id="48eb7-116">Salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="48eb7-116">Save the Report</span></span>](#Save)

### <a name="other-optional-steps"></a><span data-ttu-id="48eb7-117">Outras etapas opcionais</span><span class="sxs-lookup"><span data-stu-id="48eb7-117">Other Optional Steps</span></span>

-   [<span data-ttu-id="48eb7-118">Adicionar uma linha para separar áreas de relatório</span><span class="sxs-lookup"><span data-stu-id="48eb7-118">Add a Line to Separate Areas of Report</span></span>](#Line)

-   [<span data-ttu-id="48eb7-119">Adicionar visualização de dados resumidos</span><span class="sxs-lookup"><span data-stu-id="48eb7-119">Add Summary Data Visualization</span></span>](#Visualization)

 <span data-ttu-id="48eb7-120">Tempo estimado para concluir este tutorial: 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="48eb7-120">Estimated time to complete this tutorial: 20 minutes.</span></span>

## <a name="requirements"></a><span data-ttu-id="48eb7-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="48eb7-121">Requirements</span></span>
 <span data-ttu-id="48eb7-122">Para obter mais informações sobre os requisitos, consulte [Pré-requisitos para tutoriais &#40;Construtor de Relatórios&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="48eb7-122">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>

##  <a name="1-create-a-blank-report-data-source-and-dataset"></a><a name="BlankReport"></a><span data-ttu-id="48eb7-123">1. criar um relatório em branco, uma fonte de dados e um DataSet</span><span class="sxs-lookup"><span data-stu-id="48eb7-123">1. Create a Blank Report, Data Source, and Dataset</span></span>

> [!NOTE]
>  <span data-ttu-id="48eb7-124">Neste tutorial, como a consulta contém os valores de dados, o relatório não precisa de uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="48eb7-124">In this tutorial, the query contains the data values so that the report does not need an external data source.</span></span> <span data-ttu-id="48eb7-125">O uso desse tipo de dados internos é ótimo para fins de aprendizado, mas a abordagem torna a consulta longa.</span><span class="sxs-lookup"><span data-stu-id="48eb7-125">The use of this type of internal data is great for learning purposes, but the approach makes the query long.</span></span> <span data-ttu-id="48eb7-126">.</span><span class="sxs-lookup"><span data-stu-id="48eb7-126">.</span></span>

#### <a name="to-create-a-blank-report"></a><span data-ttu-id="48eb7-127">Para criar um relatório em branco</span><span class="sxs-lookup"><span data-stu-id="48eb7-127">To create a blank report</span></span>

1.  <span data-ttu-id="48eb7-128">Clique em **Iniciar**, aponte para **Programas**, para **Construtor de Relatórios do Microsoft SQL Server 2012**e clique em **Construtor de Relatórios**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-128">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="48eb7-129">A caixa de diálogo **Guia de Introdução** deve ser exibida.</span><span class="sxs-lookup"><span data-stu-id="48eb7-129">The **Getting Started** dialog box should appear.</span></span> <span data-ttu-id="48eb7-130">Se ela não for exibida, usando o botão do Construtor de Relatórios, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-130">If it does not, from the Report Builder button, click **New**.</span></span>

2.  <span data-ttu-id="48eb7-131">No painel esquerdo da caixa de diálogo **Guia de Introdução** , verifique se **Novo Relatório** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="48eb7-131">In the left pane of the **Getting Started** dialog box, verify that **New Report** is selected.</span></span>

3.  <span data-ttu-id="48eb7-132">No painel direito, clique em **Relatório em Branco**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-132">In the right pane, click **Blank Report**.</span></span>

#### <a name="to-create-a-new-data-source"></a><span data-ttu-id="48eb7-133">Para criar uma nova fonte de dados</span><span class="sxs-lookup"><span data-stu-id="48eb7-133">To create a new data source</span></span>

1.  <span data-ttu-id="48eb7-134">No painel dados do relatório, clique em **novo**e em **fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-134">In the Report Data pane, click **New**, and then click **Data Source**.</span></span>

2.  <span data-ttu-id="48eb7-135">Na `Name` caixa, digite: **ListDataSource**</span><span class="sxs-lookup"><span data-stu-id="48eb7-135">In the `Name` box, type: **ListDataSource**</span></span>

3.  <span data-ttu-id="48eb7-136">Clique em **Usar uma conexão inserida no meu relatório**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-136">Click **Use a connection embedded in my report**.</span></span>

4.  <span data-ttu-id="48eb7-137">Verifique se o tipo de conexão é Microsoft SQL Server e, em seguida, na caixa **cadeia de conexão** , digite: \*\*fonte de dados = \<servername> \*\*</span><span class="sxs-lookup"><span data-stu-id="48eb7-137">Verify that the connection type is Microsoft SQL Server, and then in the **Connection string** box type: **Data Source = \<servername>**</span></span>

     <span data-ttu-id="48eb7-138">\<servername>, por exemplo, Report001, especifica um computador no qual uma instância do SQL Server Mecanismo de Banco de Dados está instalada.</span><span class="sxs-lookup"><span data-stu-id="48eb7-138">\<servername>, for example Report001, specifies a computer on which an instance of the SQL Server Database Engine is installed.</span></span> <span data-ttu-id="48eb7-139">Como os dados do relatório não são extraídos de um banco de dados do SQL Server, você não precisa incluir o nome de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="48eb7-139">Because the report data is not extracted from a SQL Server database, you need not include the name of a database.</span></span> <span data-ttu-id="48eb7-140">O banco de dados padrão no servidor especificado é usado para analisar a consulta.</span><span class="sxs-lookup"><span data-stu-id="48eb7-140">The default database on the specified server is used to parse the query.</span></span>

5.  <span data-ttu-id="48eb7-141">Clique em **Credenciais**e insira as credenciais necessárias para conexão à instância do Mecanismo de Banco de Dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="48eb7-141">Click **Credentials**, and enter the credentials needed to connect to the instance of the SQL Server Database Engine.</span></span>

6.  <span data-ttu-id="48eb7-142">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-142">Click **OK**.</span></span>

#### <a name="to-create-a-new-dataset"></a><span data-ttu-id="48eb7-143">Para criar um novo conjunto de dados</span><span class="sxs-lookup"><span data-stu-id="48eb7-143">To create a new dataset</span></span>

1.  <span data-ttu-id="48eb7-144">No painel de dados do relatório, clique em **Novo**e em **Conjunto de Dados**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-144">In the Report Data pane, click **New**, and then click **Dataset**.</span></span>

2.  <span data-ttu-id="48eb7-145">Na `Name` caixa, digite: **ListDataset.**</span><span class="sxs-lookup"><span data-stu-id="48eb7-145">In the `Name` box, type: **ListDataset.**</span></span>

3.  <span data-ttu-id="48eb7-146">Clique em **Usar um conjunto de dados inserido em meu relatório**e verifique se a fonte de dados é **ListDataSource**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-146">Click **Use a dataset embedded in my report**, and verify that the data source is **ListDataSource**.</span></span>

4.  <span data-ttu-id="48eb7-147">Verifique se o tipo de consulta **Texto** está selecionado e, em seguida, clique em **Designer de Consulta**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-147">Verify that the **Text** query type is selected, and then click **Query Designer**.</span></span>

5.  <span data-ttu-id="48eb7-148">Clique em **Editar como Texto**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-148">Click **Edit as Text**.</span></span>

6.  <span data-ttu-id="48eb7-149">Copie e cole a seguinte consulta no painel de consulta:</span><span class="sxs-lookup"><span data-stu-id="48eb7-149">Copy and paste the following query into the query pane:</span></span>

    ```
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13747.25 AS money) AS Sales, 55 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(9248.15 AS money) As Sales, 37 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1800.00 AS money) AS Sales, 24 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1125.00 AS money) AS Sales, 15 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,  'Lens Adapter' as Product, CAST(742.50 AS money) AS Sales, 11 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1417.50 AS money) AS Sales, 21 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13497.30 AS money) AS Sales, 54 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(11997.60 AS money) AS Sales, 48 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(10247.95 AS money) As Sales, 41 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory, 'Tripod' as Product, CAST(1200.00 AS money) AS Sales, 16 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(2025.00 AS money) AS Sales, 27 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1425.00 AS money) AS Sales, 19 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(887.50 AS money) AS Sales, 13 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Lens Adapter' as Product, CAST(607.50 AS money) AS Sales, 9 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1215.00 AS money) AS Sales, 18 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(10191.00 AS money) AS Sales, 79 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8772.00 AS money) AS Sales, 68 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(10578.00 AS money) AS Sales, 82 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(7218.10 AS money) AS Sales, 38 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory,'Digital' as Subcategory,'Slim Digital' as Product, CAST(9307.55 AS money) AS Sales, 49 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(3870.00 AS money) AS Sales, 30 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(5805.00 AS money) AS Sales, 45 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8643.00 AS money) AS Sales, 67 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(9877.40 AS money) AS Sales, 52 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(12536.70 AS money) AS Sales, 66 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(6648.25 AS money) AS Sales, 35 as Quantity
    ```

7.  <span data-ttu-id="48eb7-150">Clique no ícone Executar para executar a consulta.</span><span class="sxs-lookup"><span data-stu-id="48eb7-150">Click Run icon to run the query.</span></span>

     <span data-ttu-id="48eb7-151">Os resultados da consulta são os dados disponíveis a serem exibidos no relatório.</span><span class="sxs-lookup"><span data-stu-id="48eb7-151">The query results are the data available to display in your report.</span></span>

     <span data-ttu-id="48eb7-152">![Designer de consultas](../../2014/tutorials/media/tutorial-querydesigner.png "Designer de Consulta")</span><span class="sxs-lookup"><span data-stu-id="48eb7-152">![Query Designer](../../2014/tutorials/media/tutorial-querydesigner.png "Query Designer")</span></span>

8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

##  <a name="2-add-and-configure-a-list"></a><a name="List"></a><span data-ttu-id="48eb7-153">2. adicionar e configurar uma lista</span><span class="sxs-lookup"><span data-stu-id="48eb7-153">2. Add and Configure a List</span></span>
 <span data-ttu-id="48eb7-154">O [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] fornece três modelos de região de dados: tabela, matriz e lista.</span><span class="sxs-lookup"><span data-stu-id="48eb7-154">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] provides three data region templates: table, matrix, and list.</span></span> <span data-ttu-id="48eb7-155">Esses modelos se baseiam na região de dados tablix.</span><span class="sxs-lookup"><span data-stu-id="48eb7-155">These templates are all based on a tablix data region.</span></span>

 <span data-ttu-id="48eb7-156">Neste tutorial, você usará uma lista para exibir as informações sobre as vendas dos territórios de vendas em um relatório semelhante a um boletim informativo.</span><span class="sxs-lookup"><span data-stu-id="48eb7-156">In this tutorial, you will use a list to display the sales information for sales territories in a report that resembles a newsletter.</span></span> <span data-ttu-id="48eb7-157">As informações são agrupadas por território.</span><span class="sxs-lookup"><span data-stu-id="48eb7-157">The information is grouped by territory.</span></span> <span data-ttu-id="48eb7-158">Você irá adicionar um novo grupo de linhas que reúne dados por território e, em seguida, excluir o grupo de linhas interno Detalhes.</span><span class="sxs-lookup"><span data-stu-id="48eb7-158">You will add a new row group that groups data by territory, and then delete the built-in Details row group.</span></span> <span data-ttu-id="48eb7-159">O modelo de lista é ideal para criar relatórios de formulário livre.</span><span class="sxs-lookup"><span data-stu-id="48eb7-159">The list template is ideal for creating free form reports.</span></span> <span data-ttu-id="48eb7-160">Para obter mais informações, consulte [listas &#40;Construtor de relatórios e SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="48eb7-160">For more information, see [Lists &#40;Report Builder and SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="48eb7-161">Esse relatório usa o tamanho de papel Carta (21,6 X 27,9) e margens de 2,54 centímetros.</span><span class="sxs-lookup"><span data-stu-id="48eb7-161">This report uses the paper size Letter (8.5 X11) and 1 inch margins.</span></span> <span data-ttu-id="48eb7-162">Uma página de relatório com mais de 22,86 centímetros de altura ou mais de 16,51 centímetros de largura pode gerar páginas em branco.</span><span class="sxs-lookup"><span data-stu-id="48eb7-162">A report page taller than 9 inches or wider than 6 1/2 inches might generate blank pages.</span></span>

#### <a name="to-add-a-list"></a><span data-ttu-id="48eb7-163">Para adicionar uma lista</span><span class="sxs-lookup"><span data-stu-id="48eb7-163">To add a list</span></span>

1.  <span data-ttu-id="48eb7-164">Na guia **Inserir** da faixa de opções, na área **Regiões de Dados** , clique em **Lista** e, em seguida, arraste a lista para dentro do corpo do relatório.</span><span class="sxs-lookup"><span data-stu-id="48eb7-164">On the **Insert** tab of the ribbon, in the **Data Regions** area, click **List** and then drag the list inside the report body.</span></span> <span data-ttu-id="48eb7-165">Crie a lista com cerca de 17,78 centímetros de altura e 15,87 centímetros de largura.</span><span class="sxs-lookup"><span data-stu-id="48eb7-165">Make the list 7 inches tall and 6.25 inches wide.</span></span>

2.  <span data-ttu-id="48eb7-166">Clique dentro da lista, clique com o botão direito do mouse na parte superior da lista e clique em **Propriedades do Tablix**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-166">Click inside the list, right-click the top of the list, and then click **Tablix Properties**.</span></span>

     <span data-ttu-id="48eb7-167">![Adicionando lista](../../2014/tutorials/media/tutorial-addinglistwithnumbers.png "Adicionando lista")</span><span class="sxs-lookup"><span data-stu-id="48eb7-167">![Adding list](../../2014/tutorials/media/tutorial-addinglistwithnumbers.png "Adding list")</span></span>

3.  <span data-ttu-id="48eb7-168">Na lista suspensa **Nome do conjunto de dados** , selecione **ListDataset**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-168">In the **Dataset name** drop-down list, select **ListDataset**.</span></span>

4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

5.  <span data-ttu-id="48eb7-169">Clique com o botão direito do mouse na lista e clique em **Propriedades do Retângulo**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-169">Right-click inside the list, and then click **Rectangle Properties**.</span></span>

     <span data-ttu-id="48eb7-170">![Comando Propriedades do Retângulo](../../2014/tutorials/media/tutorial-rectanglepropertiescommand.png "Comando Propriedades do Retângulo")</span><span class="sxs-lookup"><span data-stu-id="48eb7-170">![Rectangle Properties command](../../2014/tutorials/media/tutorial-rectanglepropertiescommand.png "Rectangle Properties command")</span></span>

6.  <span data-ttu-id="48eb7-171">Na guia **Geral** , marque a caixa de seleção **Adicionar uma quebra de página após** .</span><span class="sxs-lookup"><span data-stu-id="48eb7-171">On the **General** tab, select the **Add a page break after** checkbox.</span></span>

7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

#### <a name="to-add-a-new-row-group-and-to-delete-the-details-group"></a><span data-ttu-id="48eb7-172">Para adicionar um novo grupo de linhas e excluir o grupo Detalhes</span><span class="sxs-lookup"><span data-stu-id="48eb7-172">To add a new row group and to delete the Details group</span></span>

1.  <span data-ttu-id="48eb7-173">No painel Grupos de Linhas, clique com o botão direito do mouse no grupo Detalhes, aponte para **Adicionar Grupo**e clique em **Grupo Pai**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-173">In the Row Groups pane, right-click the Details group, point to **Add Group**, and then click **Parent Group**.</span></span>

     <span data-ttu-id="48eb7-174">![Comando Grupo Pai](../../2014/tutorials/media/tutorial-parentgroupcommand.png "Comando Grupo Pai")</span><span class="sxs-lookup"><span data-stu-id="48eb7-174">![Parent Group command](../../2014/tutorials/media/tutorial-parentgroupcommand.png "Parent Group command")</span></span>

2.  <span data-ttu-id="48eb7-175">Na lista suspensa, selecione `[Territory].`</span><span class="sxs-lookup"><span data-stu-id="48eb7-175">In the drop-down list, select `[Territory].`</span></span>

3.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

     <span data-ttu-id="48eb7-176">Uma coluna é adicionada à lista.</span><span class="sxs-lookup"><span data-stu-id="48eb7-176">A column is added to the list.</span></span> <span data-ttu-id="48eb7-177">A coluna contém a célula `[Territory].`</span><span class="sxs-lookup"><span data-stu-id="48eb7-177">The column contains the cell `[Territory].`</span></span>

4.  <span data-ttu-id="48eb7-178">Clique com o botão direito do mouse na coluna Territory da lista e clique em **Excluir Colunas**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-178">Right-click the Territory column in the list, and then click **Delete Columns**.</span></span>

     <span data-ttu-id="48eb7-179">![Excluir colunas](../../2014/tutorials/media/tutorial-deletecolumnscommand.png "Excluir Colunas")</span><span class="sxs-lookup"><span data-stu-id="48eb7-179">![Delete columns](../../2014/tutorials/media/tutorial-deletecolumnscommand.png "Delete columns")</span></span>

5.  <span data-ttu-id="48eb7-180">Clique em **Excluir somente colunas**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-180">Click **Delete Columns only**.</span></span>

     <span data-ttu-id="48eb7-181">![Caixa de diálogo excluir colunas](../../2014/tutorials/media/tutorial-deletecolumnsdialog.png "Caixa de diálogo Excluir Colunas")</span><span class="sxs-lookup"><span data-stu-id="48eb7-181">![Delete Columns dialog box](../../2014/tutorials/media/tutorial-deletecolumnsdialog.png "Delete Columns dialog box")</span></span>

6.  <span data-ttu-id="48eb7-182">No painel Grupos de Linhas, clique com o botão direito do mouse no grupo **Detalhes** e, em seguida, clique em **Excluir Grupo**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-182">In the Row Groups pane, right-click the **Details** group, and then click **Delete Group**.</span></span>

     <span data-ttu-id="48eb7-183">![Excluir detalhes do grupo](../../2014/tutorials/media/tutorial-deletedetailsgroup.png "Excluir detalhes do grupo")</span><span class="sxs-lookup"><span data-stu-id="48eb7-183">![Delete Details Group](../../2014/tutorials/media/tutorial-deletedetailsgroup.png "Delete Details Group")</span></span>

7.  <span data-ttu-id="48eb7-184">Clique em **Excluir grupo apenas**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-184">Click **Delete Group only**.</span></span>

8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

##  <a name="3-add-graphics"></a><a name="Graphics"></a><span data-ttu-id="48eb7-185">3. adicionar elementos gráficos</span><span class="sxs-lookup"><span data-stu-id="48eb7-185">3. Add Graphics</span></span>
 <span data-ttu-id="48eb7-186">Uma das vantagens de usar uma região de dados da lista é ser possível adicionar itens de relatório como retângulos e caixas de texto em qualquer lugar, em vez de haver limitação a um layout tabular.</span><span class="sxs-lookup"><span data-stu-id="48eb7-186">One of the advantages of using a list data region is that you can add report items such as rectangles and text boxes anywhere, instead of being limited to a tabular layout.</span></span> <span data-ttu-id="48eb7-187">Você aprimorará a aparência do relatório, adicionando um gráfico (um retângulo preenchido com uma cor).</span><span class="sxs-lookup"><span data-stu-id="48eb7-187">You will enhance the appearance of the report by adding a graphic (a rectangle filled with a color).</span></span>

#### <a name="to-add-graphic-elements-to-the-report"></a><span data-ttu-id="48eb7-188">Para adicionar elementos gráficos ao relatório</span><span class="sxs-lookup"><span data-stu-id="48eb7-188">To add graphic elements to the report</span></span>

1.  <span data-ttu-id="48eb7-189">Na guia **Inserir** da faixa de faixas, clique em **retângulo**e arraste um retângulo para o canto superior esquerdo da lista.</span><span class="sxs-lookup"><span data-stu-id="48eb7-189">On the **Insert** tab of the ribbon, click **Rectangle**,and then drag a rectangle to the upper left corner of the list.</span></span> <span data-ttu-id="48eb7-190">Crie o retângulo com cerca de 17,78 centímetros de altura e 2,54 centímetros de largura.</span><span class="sxs-lookup"><span data-stu-id="48eb7-190">Make the rectangle 7 inches tall and 1 inch wide.</span></span>

2.  <span data-ttu-id="48eb7-191">Clique com o botão direito do mouse no retângulo e, em seguida, clique em **Propriedades do Retângulo**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-191">Right-click the rectangle, and then click **Rectangle Properties**.</span></span>

3.  <span data-ttu-id="48eb7-192">Clique na guia **Preenchimento** .</span><span class="sxs-lookup"><span data-stu-id="48eb7-192">Click the **Fill** tab.</span></span>

4.  <span data-ttu-id="48eb7-193">Na lista suspensa **Cor de preenchimento** , clique em **Mais Cores**e, em seguida, selecione a cor **Azul escuro** .</span><span class="sxs-lookup"><span data-stu-id="48eb7-193">In the **Fill color** drop-down list, click **More Colors**, and then select the **DarkGray** color.</span></span>

     <span data-ttu-id="48eb7-194">![Selecionar cor de preenchimento](../../2014/tutorials/media/tutorial-selectfillcolorwithnumbers.png "Selecionar cor de preenchimento")</span><span class="sxs-lookup"><span data-stu-id="48eb7-194">![Select fill color](../../2014/tutorials/media/tutorial-selectfillcolorwithnumbers.png "Select fill color")</span></span>

5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

6.  <span data-ttu-id="48eb7-195">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="48eb7-195">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="48eb7-196">O lado esquerdo do relatório agora tem um gráfico vertical que consiste em um retângulo cinza-escuro.</span><span class="sxs-lookup"><span data-stu-id="48eb7-196">The left side of the report now has vertical graphic that consists of a dark gray rectangle.</span></span>

##  <a name="4-add-free-form-text"></a><a name="Text"></a><span data-ttu-id="48eb7-197">4. adicionar texto de forma livre</span><span class="sxs-lookup"><span data-stu-id="48eb7-197">4. Add Free Form Text</span></span>
 <span data-ttu-id="48eb7-198">Uma caixa de texto contém texto estático que é repetido em cada página de relatório, bem como campos de dados.</span><span class="sxs-lookup"><span data-stu-id="48eb7-198">A text box contains static text that is repeated on each report page as well as data fields.</span></span>

#### <a name="to-add-text-to-the-report"></a><span data-ttu-id="48eb7-199">Para adicionar texto ao relatório</span><span class="sxs-lookup"><span data-stu-id="48eb7-199">To add text to the report</span></span>

1.  <span data-ttu-id="48eb7-200">Clique em **Design** para retornar à exibição de design.</span><span class="sxs-lookup"><span data-stu-id="48eb7-200">Click **Design** to return to design view.</span></span>

2.  <span data-ttu-id="48eb7-201">Na guia **Inserir** da faixa de opções, clique em **Caixa de Texto**e, em seguida, arraste uma caixa de texto para o canto superior esquerdo da lista, mas dentro do retângulo adicionado por você anteriormente.</span><span class="sxs-lookup"><span data-stu-id="48eb7-201">On the **Insert** tab of the ribbon, click **Text Box**, and then drag a text box to the upper left corner of the list, but inside of the rectangle you added previously.</span></span> <span data-ttu-id="48eb7-202">Crie a caixa de texto com 7,62 centímetros de altura e 12,7 centímetros de largura.</span><span class="sxs-lookup"><span data-stu-id="48eb7-202">Make the text box about 3 inches tall and 5 inches wide.</span></span>

3.  <span data-ttu-id="48eb7-203">Posicione o cursor na parte superior da caixa de texto e, em seguida, digite: **Boletim informativo para** .</span><span class="sxs-lookup"><span data-stu-id="48eb7-203">Place the cursor in the upper part of the text box, and then type: **Newsletter for** .</span></span>

     <span data-ttu-id="48eb7-204">![Adicionar texto do título do boletim informativo](../../2014/tutorials/media/tutorial-newsletterfor.png "Adicionar texto do título do boletim informativo")</span><span class="sxs-lookup"><span data-stu-id="48eb7-204">![Add newsletter heading text](../../2014/tutorials/media/tutorial-newsletterfor.png "Add newsletter heading text")</span></span>

    > [!NOTE]
    >  <span data-ttu-id="48eb7-205">Inclua o espaço extra após a palavra "para".</span><span class="sxs-lookup"><span data-stu-id="48eb7-205">Be sure to include the extra space after the word "for".</span></span> <span data-ttu-id="48eb7-206">O espaço separa o texto e o campo que você adicionará na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="48eb7-206">The space separates the text and the field that you will add in the next step.</span></span>

4.  <span data-ttu-id="48eb7-207">Arraste o campo Territory para a caixa de texto e coloque-o depois do texto que você digitou na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="48eb7-207">Drag the Territory field to the text box and place it after the text you typed in step 3.</span></span>

     <span data-ttu-id="48eb7-208">![Adicionar campo Territorial](../../2014/tutorials/media/tutorial-addterritorialfield.png "Adicionar campo Territorial")</span><span class="sxs-lookup"><span data-stu-id="48eb7-208">![Add Territorial field](../../2014/tutorials/media/tutorial-addterritorialfield.png "Add Territorial field")</span></span>

5.  <span data-ttu-id="48eb7-209">Selecione todo o texto, clique com o botão direito do mouse e, em seguida, clique em **Propriedades de Texto**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-209">Select all text, right-click, and then click **Text Properties**.</span></span>

6.  <span data-ttu-id="48eb7-210">Clique na guia **Fonte** .</span><span class="sxs-lookup"><span data-stu-id="48eb7-210">Click the **Font** tab.</span></span>

7.  <span data-ttu-id="48eb7-211">Na lista **Fonte** , selecione **Times New Roman**. Em **Tamanho** , selecione **20 pt**, em **Cor** , selecione **Vermelho**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-211">In the **Font** list, select **Times New Roman**; in **Size** select **20 pt**, in **Color** select **Red**.</span></span>

     <span data-ttu-id="48eb7-212">![Propriedades de texto](../../2014/tutorials/media/tutorial-textpropertieswithnumbers.png "Propriedades de Texto")</span><span class="sxs-lookup"><span data-stu-id="48eb7-212">![Text Properties](../../2014/tutorials/media/tutorial-textpropertieswithnumbers.png "Text Properties")</span></span>

8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

9. <span data-ttu-id="48eb7-213">Posicione o cursor abaixo do texto que você digitou na etapa 3 e digite: **Olá** .</span><span class="sxs-lookup"><span data-stu-id="48eb7-213">Place the cursor below the text you typed in step 3 and type: **Hello** .</span></span>

    > [!NOTE]
    >  <span data-ttu-id="48eb7-214">Inclua o espaço extra após a palavra "Olá".</span><span class="sxs-lookup"><span data-stu-id="48eb7-214">Be sure to include the extra space after the word "Hello".</span></span> <span data-ttu-id="48eb7-215">O espaço separa o texto e o campo que você adicionará na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="48eb7-215">The space separates the text and the field that you will add in the next step.</span></span>

10. <span data-ttu-id="48eb7-216">Arraste o campo NomeCompleto para a caixa de texto e coloque-o depois do texto que você digitou na etapa 9 e, em seguida, digite uma vírgula (,).</span><span class="sxs-lookup"><span data-stu-id="48eb7-216">Drag the FullName field to the text box and place it after the text you typed in step 9, and then type a comma (,).</span></span>

     <span data-ttu-id="48eb7-217">![Adicionar campo Nome Completo](../../2014/tutorials/media/tutorial-addfullnamefield.png "Adicionar campo Nome Completo")</span><span class="sxs-lookup"><span data-stu-id="48eb7-217">![Add Full Name field](../../2014/tutorials/media/tutorial-addfullnamefield.png "Add Full Name field")</span></span>

11. <span data-ttu-id="48eb7-218">Selecione o texto que você adicionou nas etapas 9 e 10, clique com o botão direito do mouse e, em seguida, clique em **Propriedades de Texto**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-218">Select the text you added in steps 9 and 10, right-click, and then click **Text Properties**.</span></span>

12. <span data-ttu-id="48eb7-219">Clique na guia **Fonte** .</span><span class="sxs-lookup"><span data-stu-id="48eb7-219">Click the **Font** tab.</span></span>

13. <span data-ttu-id="48eb7-220">Na lista **Fonte** , selecione **Times New Roman**. Em **Tamanho** , selecione **16 pt**, em **Cor** , selecione **Preto** .</span><span class="sxs-lookup"><span data-stu-id="48eb7-220">In the **Font** list, select **Times New Roman**; in **Size** select **16 pt**, in **Color** select **Black** color.</span></span>

14. [!INCLUDE[clickOK](../includes/clickok-md.md)]

15. <span data-ttu-id="48eb7-221">Posicione o cursor abaixo do texto que você adicionou nas etapas de 9 a 13 e, em seguida, copie e cole o seguinte texto "greeked":</span><span class="sxs-lookup"><span data-stu-id="48eb7-221">Place the cursor below the text you added in steps 9 through 13, and then copy and paste the following "greeked" text:</span></span>

    ```
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin sed dolor in ipsum pulvinar egestas. Sed sed lacus at leo ornare ultricies. Vivamus velit risus, euismod nec sodales gravida, gravida in dui. Etiam ullamcorper elit vitae justo fermentum ut ullamcorper augue sodales. Ut placerat, nisl quis feugiat adipiscing, nibh est aliquet est, mollis faucibus mauris lectus quis arcu. In mollis tincidunt lacinia. In vitae erat ut lorem tincidunt luctus. Curabitur et magna nunc, sit amet adipiscing nisi. Nulla rhoncus elementum orci nec tincidunt. Aliquam imperdiet cursus erat vel tincidunt. Donec et neque ac urna rutrum sodales. In id purus et nisl dignissim dapibus. Sed rhoncus metus at felis feugiat eu tempor dolor vehicula. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam faucibus consectetur diam eu pellentesque. 
    Nulla facilisi. Proin ligula enim, porta ut tincidunt id, adipiscing sit amet eros. Ut purus sem, bibendum et vulputate sit amet, facilisis eget magna. Sed aliquam erat non erat eleifend hendrerit. Ut a ligula est, sit amet eleifend enim. Ut et nisl enim, sit amet adipiscing augue. Vivamus eu arcu ac libero posuere elementum. Integer condimentum bibendum venenatis. Integer odio tellus, feugiat in pellentesque semper, interdum nec sem. Sed cursus euismod sem, ut elementum sapien placerat vel. 
    ```

16. <span data-ttu-id="48eb7-222">Selecione o texto que você adicionou na etapa 15, clique com o botão direito do mouse e, em seguida, clique em **Propriedades de Texto**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-222">Select the text you added in steps 15, right-click, and then click **Text Properties**.</span></span>

17. <span data-ttu-id="48eb7-223">Clique na guia **Fonte** .</span><span class="sxs-lookup"><span data-stu-id="48eb7-223">Click the **Font** tab.</span></span>

18. <span data-ttu-id="48eb7-224">Na lista **Fonte** , selecione **Arial**; em **Tamanho** , selecione **10 pt**, em **Cor** , selecione **Preto**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-224">In the **Font** list, select **Arial**; in **Size** select **10 pt**, in **Color** select **Black**.</span></span>

19. [!INCLUDE[clickOK](../includes/clickok-md.md)]

     <span data-ttu-id="48eb7-225">![Adicionar texto do boletim informativo](../../2014/tutorials/media/tutorial-newslettertext.png "Adicionar texto do boletim informativo")</span><span class="sxs-lookup"><span data-stu-id="48eb7-225">![Add newsletter text](../../2014/tutorials/media/tutorial-newslettertext.png "Add newsletter text")</span></span>

20. <span data-ttu-id="48eb7-226">Posicione o cursor abaixo do texto que você colou na etapa 15 e, em seguida, digite: **Parabéns pelo total de vendas de** .</span><span class="sxs-lookup"><span data-stu-id="48eb7-226">Place the cursor below the text you pasted in step 15, and then type: **Congratulations on your total sales of** .</span></span>

    > [!NOTE]
    >  <span data-ttu-id="48eb7-227">Inclua o espaço extra após a palavra "de".</span><span class="sxs-lookup"><span data-stu-id="48eb7-227">Be sure to include the extra space after the word "of".</span></span> <span data-ttu-id="48eb7-228">O espaço separa o texto e o campo que você adicionará na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="48eb7-228">The space separates the text and the field that you will add in the next step.</span></span>

21. <span data-ttu-id="48eb7-229">Arraste o campo Sales para a caixa de texto, coloque-o depois do texto que você digitou na etapa 20 e, em seguida, digite um ponto de exclamação (!).</span><span class="sxs-lookup"><span data-stu-id="48eb7-229">Drag the Sales field to the text box, place it after the text you typed in step 20, and then type an exclamation mark (!).</span></span>

22. <span data-ttu-id="48eb7-230">Realce o campo vendas, clique com o botão direito do mouse no campo e clique em **expressão**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-230">Highlight the Sales field, right-click the field, and then click **Expression**.</span></span>

23. <span data-ttu-id="48eb7-231">Na caixa de expressão, altere a expressão para incluir a função Soma da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="48eb7-231">In the expression box, change the expression to include the Sum function as follows:</span></span>

    ```
    =Sum(Fields!Sales.value)
    ```

24. [!INCLUDE[clickOK](../includes/clickok-md.md)]

     <span data-ttu-id="48eb7-232">![Adicionar uma expressão ao campo vendas](../../2014/tutorials/media/tutorial-addexpressiontosalesfield.png "Adicionar uma expressão ao campo vendas")</span><span class="sxs-lookup"><span data-stu-id="48eb7-232">![Add an expression to sales field](../../2014/tutorials/media/tutorial-addexpressiontosalesfield.png "Add an expression to sales field")</span></span>

25. <span data-ttu-id="48eb7-233">Selecione o texto que você adicionou nas etapas de 20 a 23, clique com o botão direito do mouse e, em seguida, clique em **Propriedades de Texto**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-233">Select the text you added in steps 20 through 23, right-click, and then click **Text Properties**.</span></span>

26. <span data-ttu-id="48eb7-234">Clique na guia **Fonte** .</span><span class="sxs-lookup"><span data-stu-id="48eb7-234">Click the **Font** tab.</span></span>

27. <span data-ttu-id="48eb7-235">Na lista **Fonte** , selecione **Times New Roman**. Em **Tamanho** , selecione **16 pt**, em **Cor** , selecione **Vermelho**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-235">In the **Font** list, select **Times New Roman**; in **Size** select **16 pt**, in **Color** select **Red**.</span></span>

28. [!INCLUDE[clickOK](../includes/clickok-md.md)]

29. <span data-ttu-id="48eb7-236">Selecione `[Sum(Sales)]` e, na guia **Página Inicial** , no grupo **Número** , clique no botão **Moeda** .</span><span class="sxs-lookup"><span data-stu-id="48eb7-236">Select `[Sum(Sales)]` and on the **Home** tab, in the **Number** group, click the **Currency** button.</span></span>

     <span data-ttu-id="48eb7-237">![Adicionar símbolo de moeda](../../2014/tutorials/media/tutorial-addcurrencysymbol.png "Adicionar símbolo de moeda")</span><span class="sxs-lookup"><span data-stu-id="48eb7-237">![Add currency symbol](../../2014/tutorials/media/tutorial-addcurrencysymbol.png "Add currency symbol")</span></span>

30. <span data-ttu-id="48eb7-238">Clique com o botão direito do mouse na caixa de texto com o texto “Clique para adicionar título” e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-238">Right-click the text box with the "Click to add title" text, and then click **Delete**.</span></span>

31. <span data-ttu-id="48eb7-239">Selecione a caixa de listagem e, usando as teclas de direção, mova-a para parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="48eb7-239">Select the list box and using the arrow keys, move it to the top of the page.</span></span>

32. <span data-ttu-id="48eb7-240">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="48eb7-240">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="48eb7-241">O relatório exibe texto estático e cada página de relatório inclui dados pertencentes a um território.</span><span class="sxs-lookup"><span data-stu-id="48eb7-241">The report displays static text and each report page includes data that pertains to a territory.</span></span> <span data-ttu-id="48eb7-242">As vendas são formatadas como moeda.</span><span class="sxs-lookup"><span data-stu-id="48eb7-242">Sales are formatted as currency.</span></span>

 <span data-ttu-id="48eb7-243">![Visualização do boletim informativo](../../2014/tutorials/media/tutorial-newsletters.png "Visualização do boletim informativo")</span><span class="sxs-lookup"><span data-stu-id="48eb7-243">![Preview of Newsletter](../../2014/tutorials/media/tutorial-newsletters.png "Preview of Newsletter")</span></span>

##  <a name="5-add-a-table-to-show-sales-details"></a><a name="Table"></a><span data-ttu-id="48eb7-244">5. adicionar uma tabela para mostrar os detalhes de vendas</span><span class="sxs-lookup"><span data-stu-id="48eb7-244">5. Add a Table to Show Sales Details</span></span>
 <span data-ttu-id="48eb7-245">Use o Assistente de Nova Tabela e Matriz para adicionar uma tabela ao relatório de formato livre.</span><span class="sxs-lookup"><span data-stu-id="48eb7-245">Use the New Table and Matrix Wizard to add a table to the free form report.</span></span> <span data-ttu-id="48eb7-246">Depois de concluir o assistente, você adicionará manualmente uma linha para totais.</span><span class="sxs-lookup"><span data-stu-id="48eb7-246">After you complete the wizard, you will manually add a row for totals.</span></span>

#### <a name="to-add-a-table"></a><span data-ttu-id="48eb7-247">Para adicionar uma tabela</span><span class="sxs-lookup"><span data-stu-id="48eb7-247">To add a table</span></span>

1.  <span data-ttu-id="48eb7-248">Na guia **Inserir** da faixa de opções, na área **Regiões de Dados** , clique em **Tabela**e em **Assistente de tabela**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-248">On the **Insert** tab of the ribbon, in the **Data Regions** area, click **Table**, and then click **Table Wizard**.</span></span>

2.  <span data-ttu-id="48eb7-249">Na página Escolha um conjunto de dados, clique em **ListDataset**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-249">On the Choose a dataset page, click **ListDataset**.</span></span>

3.  <span data-ttu-id="48eb7-250">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-250">Click **Next**.</span></span>

4.  <span data-ttu-id="48eb7-251">Na página **Organizar campos** , arraste o campo Product de **Campos disponíveis** até **Valores**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-251">On the **Arrange fields** page, drag the Product field from **Available fields** to **Values.**</span></span>

5.  <span data-ttu-id="48eb7-252">Repita a etapa 4 para SalesDate, Quantity e Sales.</span><span class="sxs-lookup"><span data-stu-id="48eb7-252">Repeat step 4, for SalesDate, Quantity, and Sales.</span></span> <span data-ttu-id="48eb7-253">Posicione SalesDate abaixo de Product, Quantity abaixo de SalesDate e Sales abaixo de SalesDate.</span><span class="sxs-lookup"><span data-stu-id="48eb7-253">Place SalesDate below Product, Quantity below SalesDate, and Sales below SalesDate.</span></span>

6.  <span data-ttu-id="48eb7-254">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-254">Click **Next**.</span></span>

7.  <span data-ttu-id="48eb7-255">Na página **Escolha o layout** , exiba o layout da tabela.</span><span class="sxs-lookup"><span data-stu-id="48eb7-255">On the **Choose the layout** page, view the layout of the table.</span></span>

     <span data-ttu-id="48eb7-256">A tabela é muito simples.</span><span class="sxs-lookup"><span data-stu-id="48eb7-256">The table is very simple.</span></span> <span data-ttu-id="48eb7-257">Ela consiste em cinco colunas e não tem nenhum grupo de linhas ou de colunas.</span><span class="sxs-lookup"><span data-stu-id="48eb7-257">It consists of five columns and has no row or column groups.</span></span> <span data-ttu-id="48eb7-258">Por não haver nenhum grupo, as opções de layout relacionadas aos grupos não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="48eb7-258">Because it has no groups, the layout options related to groups, are not available.</span></span> <span data-ttu-id="48eb7-259">Você atualizará manualmente a tabela para incluir um total no tutorial posteriormente.</span><span class="sxs-lookup"><span data-stu-id="48eb7-259">You will manually update the table to include a total later in the tutorial.</span></span>

8.  <span data-ttu-id="48eb7-260">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-260">Click **Next**.</span></span>

9. <span data-ttu-id="48eb7-261">Na página **Escolha um estilo** , no painel **Estilos** , selecione **Ardósia**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-261">On the **Choose a Style** page, in the **Styles** pane, select **Slate**.</span></span>

10. <span data-ttu-id="48eb7-262">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-262">Click **Finish**.</span></span>

11. <span data-ttu-id="48eb7-263">Arraste a tabela para baixo da caixa de texto que você adicionou na lição 4.</span><span class="sxs-lookup"><span data-stu-id="48eb7-263">Drag the table to below the text box that you added in lesson 4.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="48eb7-264">Verifique se a tabela está dentro da lista.</span><span class="sxs-lookup"><span data-stu-id="48eb7-264">Make sure the table is inside the list.</span></span>

12. <span data-ttu-id="48eb7-265">Depois de confirmado que a tabela está selecionada, no painel Grupo de Linhas, clique com o botão direito do mouse em Detalhes, aponte para **Adicionar Total**e, em seguida, clique em **Depois**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-265">Confirmed that the table is selected, then in the Row Group pane right-click Details, point to **Add Total**, and then click **After**.</span></span>

     <span data-ttu-id="48eb7-266">![Adicionar total do relatório](../../2014/tutorials/media/tutorial-addtotal.png "Adicionar total do relatório")</span><span class="sxs-lookup"><span data-stu-id="48eb7-266">![Add report total](../../2014/tutorials/media/tutorial-addtotal.png "Add report total")</span></span>

13. <span data-ttu-id="48eb7-267">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="48eb7-267">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="48eb7-268">O primeiro relatório exibe uma tabela com detalhes e totais de vendas.</span><span class="sxs-lookup"><span data-stu-id="48eb7-268">The report displays a table with sales details and totals.</span></span>

 <span data-ttu-id="48eb7-269">![Totais de vendas no relatório](../../2014/tutorials/media/tutorial-reportsalestotals.png "Totais de vendas no relatório")</span><span class="sxs-lookup"><span data-stu-id="48eb7-269">![Sales totals in report](../../2014/tutorials/media/tutorial-reportsalestotals.png "Sales totals in report")</span></span>

##  <a name="6-format-data"></a><a name="Format"></a><span data-ttu-id="48eb7-270">6. formatar dados</span><span class="sxs-lookup"><span data-stu-id="48eb7-270">6. Format Data</span></span>
 <span data-ttu-id="48eb7-271">Formate dados numéricos como moeda e datas somente como dia e hora.</span><span class="sxs-lookup"><span data-stu-id="48eb7-271">Format numeric data as currency and dates as day and time only.</span></span>

#### <a name="to-format-fields-table"></a><span data-ttu-id="48eb7-272">Para formatar a tabela de campos</span><span class="sxs-lookup"><span data-stu-id="48eb7-272">To format fields table</span></span>

1.  <span data-ttu-id="48eb7-273">Clique em **Design** a fim de alternar para a exibição de design.</span><span class="sxs-lookup"><span data-stu-id="48eb7-273">Click **Design** to switch to design view.</span></span>

2.  <span data-ttu-id="48eb7-274">Clique nas células da tabela que contenham `[Sum(SalesSales)]` e, na guia **Página Inicial** , no grupo **Número** , clique no botão **Moeda** .</span><span class="sxs-lookup"><span data-stu-id="48eb7-274">Click the table cells that contain `[Sum(SalesSales)]` and on the **Home** tab, in the **Number** group, click the **Currency** button.</span></span>

     <span data-ttu-id="48eb7-275">![Adicionar símbolo da moeda para somar vendas](../../2014/tutorials/media/tutorial-sumsales-currencysymbol.png "Adicionar símbolo da moeda para somar vendas")</span><span class="sxs-lookup"><span data-stu-id="48eb7-275">![Add currency symbol to sum sales](../../2014/tutorials/media/tutorial-sumsales-currencysymbol.png "Add currency symbol to sum sales")</span></span>

3.  <span data-ttu-id="48eb7-276">Clique na célula que contenha `[SalesDate]` e, no grupo **Número** , na lista suspensa, selecione **Data**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-276">Click the cell that contains `[SalesDate]` and in the **Number** group, from the drop-down list, select **Date**.</span></span>

4.  <span data-ttu-id="48eb7-277">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="48eb7-277">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="48eb7-278">O relatório agora exibe dados formatados e é mais fácil de ler.</span><span class="sxs-lookup"><span data-stu-id="48eb7-278">The report now displays formatted data and is easier to read.</span></span>

 <span data-ttu-id="48eb7-279">![Formatar totais de vendas no relatório](../../2014/tutorials/media/tutorial-reportsalestotals-formatted.png "Formatar totais de vendas no relatório")</span><span class="sxs-lookup"><span data-stu-id="48eb7-279">![Format sales totals in report](../../2014/tutorials/media/tutorial-reportsalestotals-formatted.png "Format sales totals in report")</span></span>

##  <a name="7-save-the-report"></a><a name="Save"></a><span data-ttu-id="48eb7-280">7. salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="48eb7-280">7. Save the Report</span></span>
 <span data-ttu-id="48eb7-281">É possível salvar relatórios em um servidor de relatório, em uma biblioteca do SharePoint ou no computador.</span><span class="sxs-lookup"><span data-stu-id="48eb7-281">You can save reports to a report server, SharePoint library, or your computer.</span></span> <span data-ttu-id="48eb7-282">Você também pode exportar o relatório para uma variedade de formatos, como Word e PDF, executando o relatório e selecionando o formato do menu **Exportar** .</span><span class="sxs-lookup"><span data-stu-id="48eb7-282">You can also export the report to a variety of formats such as Word and PDF, by running the report and selecting the format from the **Export** menu.</span></span>

 <span data-ttu-id="48eb7-283">Neste tutorial, salve o relatório em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="48eb7-283">In this tutorial, save the report to a report server.</span></span> <span data-ttu-id="48eb7-284">Se você não tiver acesso ao servidor de relatório, salve o relatório no computador.</span><span class="sxs-lookup"><span data-stu-id="48eb7-284">If you do not have access to a report server, save the report to your computer.</span></span>

#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="48eb7-285">Para salvar o relatório em um servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="48eb7-285">To save the report on a report server</span></span>

1.  <span data-ttu-id="48eb7-286">No botão **Construtor de Relatórios** , clique em **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-286">From the **Report Builder** button, click **Save As**.</span></span>

2.  <span data-ttu-id="48eb7-287">Clique em **Sites e Servidores Recentes**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-287">Click **Recent Sites and Servers**.</span></span>

3.  <span data-ttu-id="48eb7-288">Selecione ou digite o nome do servidor de relatório no qual você tem permissão para salvar relatórios.</span><span class="sxs-lookup"><span data-stu-id="48eb7-288">Select or type the name of the report server where you have permission to save reports.</span></span>

     <span data-ttu-id="48eb7-289">A mensagem "Conectando-se a um servidor de relatório" é exibida.</span><span class="sxs-lookup"><span data-stu-id="48eb7-289">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="48eb7-290">Quando a conexão for concluída, você verá o conteúdo da pasta do relatório que o administrador do servidor de relatório especificou como o local padrão para relatórios.</span><span class="sxs-lookup"><span data-stu-id="48eb7-290">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>

4.  <span data-ttu-id="48eb7-291">Em `Name` , substitua o nome padrão por **SalesInformationByTerritory**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-291">In `Name`, replace the default name with **SalesInformationByTerritory**.</span></span>

5.  <span data-ttu-id="48eb7-292">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-292">Click **Save**.</span></span>

 <span data-ttu-id="48eb7-293">O relatório será salvo no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="48eb7-293">The report is saved to the report server.</span></span> <span data-ttu-id="48eb7-294">O nome do servidor de relatório ao qual você está conectado é exibido na barra de status da parte inferior da janela.</span><span class="sxs-lookup"><span data-stu-id="48eb7-294">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>

#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="48eb7-295">Para salvar o relatório no computador</span><span class="sxs-lookup"><span data-stu-id="48eb7-295">To save the report on your computer</span></span>

1.  <span data-ttu-id="48eb7-296">No botão **Construtor de Relatórios** , clique em **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-296">From the **Report Builder** button, click **Save As**.</span></span>

2.  <span data-ttu-id="48eb7-297">Clique em **Área de Trabalho**, **Meus Documentos**ou **Meu Computador**e, em seguida, navegue até a pasta na qual você deseja salvar o relatório.</span><span class="sxs-lookup"><span data-stu-id="48eb7-297">Click **Desktop**, **My Documents**, or **My computer**, and then browse to the folder where you want to save the report.</span></span>

3.  <span data-ttu-id="48eb7-298">Em `Name` , substitua o nome padrão por **SalesInformationByTerritory**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-298">In `Name`, replace the default name with **SalesInformationByTerritory**.</span></span>

4.  <span data-ttu-id="48eb7-299">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-299">Click **Save**.</span></span>

##  <a name="8-optional-add-a-line-to-separate-areas-of-the-report"></a><a name="Line"></a><span data-ttu-id="48eb7-300">8. (opcional) adicionar uma linha para separar áreas do relatório</span><span class="sxs-lookup"><span data-stu-id="48eb7-300">8. (Optional) Add a Line to Separate Areas of the Report</span></span>
 <span data-ttu-id="48eb7-301">Adicione uma linha para separar as áreas editoriais e detalhadas do relatório.</span><span class="sxs-lookup"><span data-stu-id="48eb7-301">Add a line to separate the editorial and details areas of the report.</span></span>

#### <a name="to-add-a-line"></a><span data-ttu-id="48eb7-302">Para adicionar uma linha</span><span class="sxs-lookup"><span data-stu-id="48eb7-302">To add a line</span></span>

1.  <span data-ttu-id="48eb7-303">Clique em **Design** para retornar à exibição de design.</span><span class="sxs-lookup"><span data-stu-id="48eb7-303">Click **Design** to return to design view.</span></span>

2.  <span data-ttu-id="48eb7-304">Na guia **Inserir** da faixa de opções, na área **Itens do Relatório** , clique em **Linha**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-304">On the **Insert** tab of the ribbon, in the **Report Items** area, click **Line.**</span></span>

3.  <span data-ttu-id="48eb7-305">Desenhe uma linha abaixo da caixa de texto de formato livre que você adicionou na lição 4.</span><span class="sxs-lookup"><span data-stu-id="48eb7-305">Draw a line below the free form text box you added in lesson 4.</span></span>

4.  <span data-ttu-id="48eb7-306">Clique na linha.</span><span class="sxs-lookup"><span data-stu-id="48eb7-306">Click the line.</span></span>

5.  <span data-ttu-id="48eb7-307">Clique na guia **Página Inicial** .</span><span class="sxs-lookup"><span data-stu-id="48eb7-307">Click the **Home** tab.</span></span>

6.  <span data-ttu-id="48eb7-308">Na área **Borda** , para a largura, selecione **4 1/2** pt e, para a cor, selecione **Vermelho**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-308">In the **Border** area, for width select **4 1/2** pt and for color, for color select **Red**.</span></span>

     <span data-ttu-id="48eb7-309">![Adicionar linha ao relatório](../../2014/tutorials/media/tutorial-reportwithline.png "Adicionar linha ao relatório")</span><span class="sxs-lookup"><span data-stu-id="48eb7-309">![Add line to report](../../2014/tutorials/media/tutorial-reportwithline.png "Add line to report")</span></span>

##  <a name="9-optional-add-summary-data-visualization"></a><a name="Visualization"></a><span data-ttu-id="48eb7-310">9. (opcional) adicionar visualização de dados de resumo</span><span class="sxs-lookup"><span data-stu-id="48eb7-310">9. (Optional) Add Summary Data Visualization</span></span>
 <span data-ttu-id="48eb7-311">Os retângulos ajudam a controlar a renderização do relatório.</span><span class="sxs-lookup"><span data-stu-id="48eb7-311">Rectangles help you control how the report renders.</span></span> <span data-ttu-id="48eb7-312">Posicione um gráfico de pizza e de colunas dentro de um retângulo para garantir que o relatório seja renderizado da maneira desejada.</span><span class="sxs-lookup"><span data-stu-id="48eb7-312">Place a pie and column chart inside a rectangle to ensure that the report renders the way you want.</span></span>

#### <a name="to-add-a-rectangle"></a><span data-ttu-id="48eb7-313">Para adicionar um retângulo</span><span class="sxs-lookup"><span data-stu-id="48eb7-313">To add a rectangle</span></span>

1.  <span data-ttu-id="48eb7-314">Clique em **Design** para retornar à exibição de design.</span><span class="sxs-lookup"><span data-stu-id="48eb7-314">Click **Design** to return to design view.</span></span>

2.  <span data-ttu-id="48eb7-315">Na guia **Inserir** da faixa de opções, na área **Itens do Relatório** , clique em **Retângulo**e, em seguida, arraste o retângulo para dentro da lista, à direita da tabela.</span><span class="sxs-lookup"><span data-stu-id="48eb7-315">On the **Insert** tab of the ribbon, in the **Report Items** area click **Rectangle**, and then drag the rectangle inside the list, to the right of the table.</span></span> <span data-ttu-id="48eb7-316">Crie o retângulo com 6,45 centímetros de altura e 10,16 centímetros de largura.</span><span class="sxs-lookup"><span data-stu-id="48eb7-316">Make the rectangle 2 inches wide and 4 inches tall.</span></span>

3.  <span data-ttu-id="48eb7-317">Alinhe as partes superiores do retângulo e da tabela.</span><span class="sxs-lookup"><span data-stu-id="48eb7-317">Align the tops of the rectangle and the table.</span></span>

#### <a name="to-add-a-pie-chart"></a><span data-ttu-id="48eb7-318">Para adicionar um gráfico de pizza</span><span class="sxs-lookup"><span data-stu-id="48eb7-318">To add a pie chart</span></span>

1.  <span data-ttu-id="48eb7-319">Na guia **Inserir** da faixa de opções, na área **Visualizações de Dados** , clique em **Gráfico** e em **Assistente de Gráfico**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-319">On the **Insert** tab of the ribbon, in the **Data Visualizations** area, click **Chart,** and then click **Chart Wizard**.</span></span>

2.  <span data-ttu-id="48eb7-320">Na página Escolha um conjunto de dados , clique em **ListDataset**e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-320">On the Choose a dataset page, click **ListDataset**, and then click **Next**.</span></span>

3.  <span data-ttu-id="48eb7-321">Clique em **Pizza**e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-321">Click **Pie**, and then click **Next**.</span></span>

4.  <span data-ttu-id="48eb7-322">Na página Organizar Campos de Gráfico, arraste Product até **Categorias**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-322">On the arrange chart fields page, drag Product to **Categories**.</span></span>

5.  <span data-ttu-id="48eb7-323">Arraste quantidade para **valores**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-323">Drag Quantity to **Values**, and then click **Next**.</span></span>

6.  <span data-ttu-id="48eb7-324">Na página **Escolha um estilo** , no painel **Estilos** , selecione **Ardósia**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-324">On the **Choose a Style** page, in the **Styles** pane, select **Slate**.</span></span>

7.  <span data-ttu-id="48eb7-325">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-325">Click **Finish**.</span></span>

8.  <span data-ttu-id="48eb7-326">Redimensione o gráfico exibido no canto superior esquerdo do relatório para que ele tenha 3,81 centímetros de altura e 5,08 centímetros de largura.</span><span class="sxs-lookup"><span data-stu-id="48eb7-326">Resize the chart that appears in the upper left corner of the report, to be 1 1/2 inches tall and 2 inches wide.</span></span>

9. <span data-ttu-id="48eb7-327">Arraste o gráfico para dentro do retângulo.</span><span class="sxs-lookup"><span data-stu-id="48eb7-327">Drag the chart inside the rectangle.</span></span>

     <span data-ttu-id="48eb7-328">![Adicionar gráfico de pizza](../../2014/tutorials/media/tutorial-addpiechart.png "Adicionar gráfico de pizza")</span><span class="sxs-lookup"><span data-stu-id="48eb7-328">![Add pie chart](../../2014/tutorials/media/tutorial-addpiechart.png "Add pie chart")</span></span>

10. <span data-ttu-id="48eb7-329">Clique com o botão direito do mouse no título do gráfico e, em seguida, clique em **Propriedades do Título**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-329">Right-click the chart title, and then click **Title Properties**.</span></span>

11. <span data-ttu-id="48eb7-330">Na caixa de diálogo **Propriedades do Título do Gráfico** , em Texto do título, digite: **Quantidades Vendidas do Produto**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-330">In the **Chart Title Properties** dialog box, in Title text, type: **Product Quantities Sold**.</span></span>

12. <span data-ttu-id="48eb7-331">Clique na guia **Fonte** e, na lista **Tamanho** , em **10pt**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-331">Click the **Font** tab, and in the **Size** list, click **10pt**.</span></span>

13. [!INCLUDE[clickOK](../includes/clickok-md.md)]

#### <a name="to-add-a-column-chart"></a><span data-ttu-id="48eb7-332">Para adicionar um gráfico de colunas</span><span class="sxs-lookup"><span data-stu-id="48eb7-332">To add a column chart</span></span>

1.  <span data-ttu-id="48eb7-333">Na guia **Inserir** da faixa de opções, na área **Visualizações de Dados** , clique em **Gráfico** e em **Assistente de Gráfico**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-333">On the **Insert** tab of the ribbon, in the **Data Visualizations** area, click **Chart,** and then click **Chart Wizard**.</span></span>

2.  <span data-ttu-id="48eb7-334">Na página **Escolha um conjunto de dados** , clique em **ListDataset**e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-334">On the **Choose a dataset** page, click **ListDataset**, and then click **Next**.</span></span>

3.  <span data-ttu-id="48eb7-335">Clique em **Coluna**e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-335">Click **Column**, and then click **Next**.</span></span>

4.  <span data-ttu-id="48eb7-336">Na página organizar campos de gráfico, arraste o campo produto para **categorias**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-336">On the arrange chart fields page, drag the Product field to **Categories**.</span></span>

5.  <span data-ttu-id="48eb7-337">Arraste Sales até **Valores** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-337">Drag Sales to **Values,** and then click **Next**.</span></span>

     <span data-ttu-id="48eb7-338">Os valores são exibidos no eixo vertical.</span><span class="sxs-lookup"><span data-stu-id="48eb7-338">Values display on the vertical axis.</span></span>

6.  <span data-ttu-id="48eb7-339">Na página **Escolha um estilo** , no painel **Estilos** , selecione **Ardósia**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-339">On the **Choose a Style** page, in the **Styles** pane, select **Slate**.</span></span>

7.  <span data-ttu-id="48eb7-340">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-340">Click **Finish**.</span></span>

     <span data-ttu-id="48eb7-341">Um gráfico de colunas é adicionado ao canto superior esquerdo do relatório.</span><span class="sxs-lookup"><span data-stu-id="48eb7-341">A column chart is added to the upper left corner of the report.</span></span>

8.  <span data-ttu-id="48eb7-342">Redimensione o gráfico para que ele tenha 5,08 centímetros de largura e 5,08 centímetros de altura.</span><span class="sxs-lookup"><span data-stu-id="48eb7-342">Resize the chart to be 2 inches wide and 2 inches tall.</span></span>

9. <span data-ttu-id="48eb7-343">Arraste o gráfico para dentro do retângulo, abaixo do gráfico de pizza.</span><span class="sxs-lookup"><span data-stu-id="48eb7-343">Drag the chart inside the rectangle, below the pie chart.</span></span>

     <span data-ttu-id="48eb7-344">![Adicione gráfico de colunas](../../2014/tutorials/media/tutorial-addcolumnchart.png "Adicione gráfico de colunas")</span><span class="sxs-lookup"><span data-stu-id="48eb7-344">![Add column chart](../../2014/tutorials/media/tutorial-addcolumnchart.png "Add column chart")</span></span>

10. <span data-ttu-id="48eb7-345">Clique com o botão direito do mouse no título do gráfico e clique em **Propriedades do título**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-345">Right-click the chart title and then click **Title Properties**.</span></span>

11. <span data-ttu-id="48eb7-346">Na caixa de diálogo **Propriedades do Título do Gráfico** , em Texto do título, digite: **Vendas do Produto**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-346">In the **Chart Title Properties** dialog box, in Title text, type: **Product Sales**.</span></span>

12. <span data-ttu-id="48eb7-347">Clique na guia **Fonte** e, na lista **Tamanho** , clique em **10pt**e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-347">Click the **Font** tab, and in the **Size** list click **10pt**, and then click **OK**.</span></span>

13. <span data-ttu-id="48eb7-348">No gráfico de colunas, clique com o botão direito do mouse no eixo vertical e, em seguida, desmarque **Mostrar Título do Eixo**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-348">In the column chart, right click the vertical axis, and then deselect **Show Axis Title**.</span></span>

14. <span data-ttu-id="48eb7-349">Repita a etapa 13 para o eixo horizontal.</span><span class="sxs-lookup"><span data-stu-id="48eb7-349">Repeat step 13 for the horizontal axis.</span></span>

15. <span data-ttu-id="48eb7-350">Clique com o botão direito do mouse na legenda e, em seguida, clique em **Excluir Legenda**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-350">Right click the legend, and then click **Delete Legend**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="48eb7-351">A remoção dos títulos dos eixos e da legenda deixará o gráfico mais legível quando ele for pequeno.</span><span class="sxs-lookup"><span data-stu-id="48eb7-351">Removing axis titles and the legend makes the chart more readable when it is a small size.</span></span>

 <span data-ttu-id="48eb7-352">![Alterar títulos de gráficos e remover título do eixo](../../2014/tutorials/media/tutorial-columnchart-newtitle-noaxistitle.png "Alterar títulos de gráficos e remover título do eixo")</span><span class="sxs-lookup"><span data-stu-id="48eb7-352">![Change chart titles and remove axis title](../../2014/tutorials/media/tutorial-columnchart-newtitle-noaxistitle.png "Change chart titles and remove axis title")</span></span>

#### <a name="to-verify-the-charts-are-inside-the-rectangle"></a><span data-ttu-id="48eb7-353">Para verificar se os gráficos estão dentro do retângulo</span><span class="sxs-lookup"><span data-stu-id="48eb7-353">To verify the charts are inside the rectangle</span></span>

1.  <span data-ttu-id="48eb7-354">Clique no retângulo que você adicionou anteriormente nesta lição.</span><span class="sxs-lookup"><span data-stu-id="48eb7-354">Click the rectangle you added earlier in this lesson.</span></span>

     <span data-ttu-id="48eb7-355">No painel Propriedades, a propriedade `Name` exibe o nome do retângulo.</span><span class="sxs-lookup"><span data-stu-id="48eb7-355">In the Properties pane, the `Name` property displays the name of the rectangle.</span></span>

     <span data-ttu-id="48eb7-356">![Nome do retângulo](../../2014/tutorials/media/tutorial-rectanglename.png "Nome do retângulo")</span><span class="sxs-lookup"><span data-stu-id="48eb7-356">![Name of rectangle](../../2014/tutorials/media/tutorial-rectanglename.png "Name of rectangle")</span></span>

2.  <span data-ttu-id="48eb7-357">Clique no gráfico de pizza.</span><span class="sxs-lookup"><span data-stu-id="48eb7-357">Click the pie chart.</span></span>

3.  <span data-ttu-id="48eb7-358">No painel **Propriedades** , verifique se a `Parent` propriedade contém o nome do retângulo.</span><span class="sxs-lookup"><span data-stu-id="48eb7-358">In the **Properties** pane, verify that the `Parent` property contains the name of the rectangle.</span></span>

     <span data-ttu-id="48eb7-359">![Propriedade Pai do gráfico de pizza](../../2014/tutorials/media/tutorial-piechart-parentproperty.png "Propriedade Pai do gráfico de pizza")</span><span class="sxs-lookup"><span data-stu-id="48eb7-359">![Parent property for pie chart](../../2014/tutorials/media/tutorial-piechart-parentproperty.png "Parent property for pie chart")</span></span>

4.  <span data-ttu-id="48eb7-360">Clique no gráfico de colunas e repita as etapas 2 e 3.</span><span class="sxs-lookup"><span data-stu-id="48eb7-360">Click the column chart and repeat steps 2 and 3.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="48eb7-361">Se os gráficos não estiverem dentro do retângulo, o relatório renderizado não exibirá os gráficos juntos.</span><span class="sxs-lookup"><span data-stu-id="48eb7-361">If the charts are not inside the rectangle, the rendered report does not display the charts together.</span></span>

#### <a name="to-make-the-charts-the-same-size"></a><span data-ttu-id="48eb7-362">Para deixar os gráficos com o mesmo tamanho</span><span class="sxs-lookup"><span data-stu-id="48eb7-362">To make the charts the same size</span></span>

1.  <span data-ttu-id="48eb7-363">Clique no gráfico de pizza, pressione a tecla Ctrl e, em seguida, clique no gráfico de colunas.</span><span class="sxs-lookup"><span data-stu-id="48eb7-363">Click the pie chart, press the Ctrl key, and then click the column chart.</span></span>

2.  <span data-ttu-id="48eb7-364">Com ambos os gráficos selecionados, clique com o botão direito do mouse, aponte para **Layout**e, em seguida, clique em **Mesma Largura**.</span><span class="sxs-lookup"><span data-stu-id="48eb7-364">With both charts selected, right-click, point to **Layout**, and then click **Make Same Width**.</span></span>

     <span data-ttu-id="48eb7-365">![Deixar as larguras do gráfico iguais](../../2014/tutorials/media/tutorial-makechartssamewidth.png "Deixar as larguras do gráfico iguais")</span><span class="sxs-lookup"><span data-stu-id="48eb7-365">![Make chart widths the same](../../2014/tutorials/media/tutorial-makechartssamewidth.png "Make chart widths the same")</span></span>

    > [!NOTE]
    >  <span data-ttu-id="48eb7-366">O item no qual você clica primeiro determina a largura de todos os itens selecionados.</span><span class="sxs-lookup"><span data-stu-id="48eb7-366">The item you click first determines the width of all the selected items.</span></span>

3.  <span data-ttu-id="48eb7-367">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="48eb7-367">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="48eb7-368">O relatório agora exibe dados de vendas resumidos em gráficos de pizza e de colunas.</span><span class="sxs-lookup"><span data-stu-id="48eb7-368">The report now displays summary sales data in pie and column charts.</span></span>

 <span data-ttu-id="48eb7-369">![Tutorial SSRS, relatório de forma livre](../../2014/tutorials/media/tutorial-reportfinal.png "Tutorial SSRS, relatório de forma livre")</span><span class="sxs-lookup"><span data-stu-id="48eb7-369">![SSRS tutorial, free form report](../../2014/tutorials/media/tutorial-reportfinal.png "SSRS tutorial, free form report")</span></span>

## <a name="more-information"></a><span data-ttu-id="48eb7-370">Mais informações</span><span class="sxs-lookup"><span data-stu-id="48eb7-370">More Information</span></span>
 <span data-ttu-id="48eb7-371">Para obter mais informações sobre listas, consulte [tabelas, matrizes e listas &#40;Construtor de relatórios e ssrs&#41;](report-design/tables-matrices-and-lists-report-builder-and-ssrs.md), [lista &#40;Construtor de Relatórios e SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md), [áreas de região de dados Tablix &#40;Construtor de relatórios e SSRS&#41;](report-design/tablix-data-region-areas-report-builder-and-ssrs.md)e [células, linhas e colunas da região de dados Tablix &#40;Construtor de relatórios&#41; e SSRS](report-design/tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="48eb7-371">For more information about lists, see [Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](report-design/tables-matrices-and-lists-report-builder-and-ssrs.md), [Lists &#40;Report Builder and SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md), [Tablix Data Region Areas &#40;Report Builder and SSRS&#41;](report-design/tablix-data-region-areas-report-builder-and-ssrs.md), and [Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](report-design/tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span></span>

 <span data-ttu-id="48eb7-372">Para obter mais informações sobre designers de consultas, consulte [Designers de Consultas &#40;Construtor de Relatórios&#41;](../../2014/reporting-services/query-designers-report-builder.md) e [Interface do usuário do Designer de Consultas Baseadas em Texto &#40;Construtor de Relatórios&#41;](report-data/text-based-query-designer-user-interface-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="48eb7-372">For more information about query designers, see [Query Designers &#40;Report Builder&#41;](../../2014/reporting-services/query-designers-report-builder.md) and [Text-based Query Designer User Interface &#40;Report Builder&#41;](report-data/text-based-query-designer-user-interface-report-builder.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="48eb7-373">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="48eb7-373">See Also</span></span>
 <span data-ttu-id="48eb7-374">[Tutoriais &#40;Construtor de Relatórios&#41;](report-builder-tutorials.md) [Construtor de Relatórios no SQL Server 2014](report-builder/report-builder-in-sql-server-2016.md)</span><span class="sxs-lookup"><span data-stu-id="48eb7-374">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) [Report Builder in SQL Server 2014](report-builder/report-builder-in-sql-server-2016.md)</span></span>


