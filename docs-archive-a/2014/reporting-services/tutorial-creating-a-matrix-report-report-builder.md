---
title: 'Tutorial: Criando um relatório de matriz (Construtor de Relatórios) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9ee19c2e-2a8c-4bb0-9274-04a5812c2e96
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3df32098d9e6400931ba2a88b2ffd22d6e015a62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684027"
---
# <a name="tutorial-creating-a-matrix-report-report-builder"></a><span data-ttu-id="bcf19-102">Tutorial: criando um relatório de matriz (Construtor de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="bcf19-102">Tutorial: Creating a Matrix Report (Report Builder)</span></span>
  <span data-ttu-id="bcf19-103">Este tutorial ensina a criar um relatório de matriz básico com base em dados de vendas de exemplo.</span><span class="sxs-lookup"><span data-stu-id="bcf19-103">This tutorial teaches you how to create a basic matrix report based on sample sales data.</span></span> <span data-ttu-id="bcf19-104">A matriz tem grupos de linhas e de colunas aninhados e um grupo de colunas adjacente.</span><span class="sxs-lookup"><span data-stu-id="bcf19-104">The matrix has nested row and column groups and an adjacent column group.</span></span> <span data-ttu-id="bcf19-105">Você também aprenderá a formatar colunas e a girar texto.</span><span class="sxs-lookup"><span data-stu-id="bcf19-105">You will also learn how to format columns and rotate text.</span></span> <span data-ttu-id="bcf19-106">A ilustração a seguir mostra um relatório semelhante ao que você criará.</span><span class="sxs-lookup"><span data-stu-id="bcf19-106">The following illustration shows a report similar to the one you will create.</span></span>  
  
 <span data-ttu-id="bcf19-107">![rs_CreateMatixReportTutorial](../../2014/tutorials/media/rs-creatematixreporttutorial.gif "rs_CreateMatixReportTutorial")</span><span class="sxs-lookup"><span data-stu-id="bcf19-107">![rs_CreateMatixReportTutorial](../../2014/tutorials/media/rs-creatematixreporttutorial.gif "rs_CreateMatixReportTutorial")</span></span>  
  
 <span data-ttu-id="bcf19-108">Uma versão aprimorada do relatório que você criará neste tutorial está disponível como um relatório de exemplo do [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Report Builder.</span><span class="sxs-lookup"><span data-stu-id="bcf19-108">An enhanced version of the report you will create in this tutorial is available as a sample [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Report Builder report.</span></span> <span data-ttu-id="bcf19-109">Para obter mais informações sobre como baixar este relatório de exemplo e outros, consulte [Construtor de relatórios relatórios de exemplo](https://go.microsoft.com/fwlink/?LinkId=184851).</span><span class="sxs-lookup"><span data-stu-id="bcf19-109">For more information about downloading this sample report and others, see [Report Builder sample reports](https://go.microsoft.com/fwlink/?LinkId=184851).</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="bcf19-110">O que você aprenderá</span><span class="sxs-lookup"><span data-stu-id="bcf19-110">What You Will Learn</span></span>  
 <span data-ttu-id="bcf19-111">Neste tutorial, você aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="bcf19-111">In this tutorial, you will learn how to:</span></span>  
  
1.  [<span data-ttu-id="bcf19-112">Criar um relatório de matriz e um conjunto de dados no Assistente de Nova Tabela ou Matriz</span><span class="sxs-lookup"><span data-stu-id="bcf19-112">Create a Matrix Report and Dataset from the New Table or Matrix Wizard</span></span>](#CreateMatrix)  
  
2.  [<span data-ttu-id="bcf19-113">Organizar dados e escolher layout e estilo no Assistente de Nova Tabela ou Matriz</span><span class="sxs-lookup"><span data-stu-id="bcf19-113">Organize Data and Choose Layout and Style from the New Table or Matrix Wizard</span></span>](#Groups)  
  
3.  [<span data-ttu-id="bcf19-114">Formatar dados</span><span class="sxs-lookup"><span data-stu-id="bcf19-114">Format Data</span></span>](#FormatData)  
  
4.  [<span data-ttu-id="bcf19-115">Adicionar grupo de colunas adjacente</span><span class="sxs-lookup"><span data-stu-id="bcf19-115">Add Adjacent Column Group</span></span>](#AdjacentGroup)  
  
5.  [<span data-ttu-id="bcf19-116">Alterar a Largura das Colunas</span><span class="sxs-lookup"><span data-stu-id="bcf19-116">Change Column Widths</span></span>](#Width)  
  
6.  [<span data-ttu-id="bcf19-117">Mesclar células na matriz</span><span class="sxs-lookup"><span data-stu-id="bcf19-117">Merge Matrix Cells</span></span>](#MergeCells)  
  
7.  [<span data-ttu-id="bcf19-118">Adicionar um cabeçalho e um título de relatório</span><span class="sxs-lookup"><span data-stu-id="bcf19-118">Add a Report Header and Report Title</span></span>](#HeaderTitle)  
  
8.  [<span data-ttu-id="bcf19-119">Salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="bcf19-119">Save the Report</span></span>](#Save)  
  
### <a name="other-optional-step"></a><span data-ttu-id="bcf19-120">Outra etapa opcional</span><span class="sxs-lookup"><span data-stu-id="bcf19-120">Other Optional Step</span></span>  
  
1.  [<span data-ttu-id="bcf19-121">Girar caixa de texto em 270 graus</span><span class="sxs-lookup"><span data-stu-id="bcf19-121">Rotate Text Box 270 Degrees</span></span>](#RotateTextBox)  
  
 <span data-ttu-id="bcf19-122">Tempo estimado para concluir este tutorial: 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="bcf19-122">Estimated time to complete this tutorial: 20 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcf19-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bcf19-123">Requirements</span></span>  
 <span data-ttu-id="bcf19-124">Para obter mais informações sobre os requisitos, consulte [Pré-requisitos para tutoriais &#40;Construtor de Relatórios&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="bcf19-124">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-matrix-report-and-dataset-from-the-new-table-or-matrix-wizard"></a><a name="CreateMatrix"></a><span data-ttu-id="bcf19-125">1. criar um relatório de matriz e um conjunto de relatórios do novo assistente de tabela ou matriz</span><span class="sxs-lookup"><span data-stu-id="bcf19-125">1. Create a Matrix Report and Dataset from the New Table or Matrix Wizard</span></span>  
 <span data-ttu-id="bcf19-126">Na caixa de diálogo **introdução** no construtor de relatórios, escolha uma fonte de dados compartilhada, crie um conjunto de dado inserido e, em seguida, exiba os dados em uma matriz.</span><span class="sxs-lookup"><span data-stu-id="bcf19-126">From the **Getting Started** dialog box in Report Builder, choose a shared data source, create an embedded dataset, and then display the data in a matrix.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bcf19-127">Neste tutorial, como já contém os valores de dados, a consulta não precisa de uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="bcf19-127">In this tutorial, the query already contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="bcf19-128">Isso torna a consulta bastante longa.</span><span class="sxs-lookup"><span data-stu-id="bcf19-128">This makes the query quite long.</span></span> <span data-ttu-id="bcf19-129">Em um ambiente empresarial, uma consulta não conteria os dados.</span><span class="sxs-lookup"><span data-stu-id="bcf19-129">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="bcf19-130">Isso é apenas para fins de aprendizado.</span><span class="sxs-lookup"><span data-stu-id="bcf19-130">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-matrix"></a><span data-ttu-id="bcf19-131">Para criar uma nova matriz</span><span class="sxs-lookup"><span data-stu-id="bcf19-131">To create a new matrix</span></span>  
  
1.  <span data-ttu-id="bcf19-132">Clique em **Iniciar**, aponte para **Programas**, para **Construtor de Relatórios do Microsoft SQL Server 2012**e clique em **Construtor de Relatórios**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-132">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bcf19-133">A caixa de diálogo **Guia de Introdução** deve ser exibida.</span><span class="sxs-lookup"><span data-stu-id="bcf19-133">The **Getting Started** dialog box should appear.</span></span> <span data-ttu-id="bcf19-134">Se não estiver, no botão Construtor de Relatórios, clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-134">If it doesn't, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="bcf19-135">No painel esquerdo, verifique se **Novo Relatório** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="bcf19-135">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="bcf19-136">No painel direito, clique em **Assistente de Tabela ou Matriz**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-136">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="bcf19-137">Na página **Escolher um conjunto de dados** , clique em **Criar um conjunto de dados**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-137">On the **Choose a dataset** page, click **Create a dataset**.</span></span>  
  
5.  <span data-ttu-id="bcf19-138">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-138">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="bcf19-139">Na página **escolher uma conexão com uma fonte de dados** , selecione uma fonte de dados existente ou navegue até o servidor de relatório e selecione uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="bcf19-139">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server, and then select a data source.</span></span> <span data-ttu-id="bcf19-140">Se não houver nenhuma fonte de dados disponível ou você não tiver acesso a um servidor de relatório, em vez disso, será possível usar uma fonte de dados inserida.</span><span class="sxs-lookup"><span data-stu-id="bcf19-140">If no data source is available or you do not have access to a report server, you can use an embedded data source instead.</span></span> <span data-ttu-id="bcf19-141">Para obter mais informações sobre como criar uma fonte de dados inserida, consulte [tutorial: Criando um relatório de tabela básico &#40;Construtor de Relatórios&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="bcf19-141">For more information about creating an embedded data source, see [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
7.  <span data-ttu-id="bcf19-142">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-142">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="bcf19-143">Na página **Crie uma consulta** , clique em **Editar como Texto**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-143">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
9. <span data-ttu-id="bcf19-144">Copie e cole a seguinte consulta no painel de consulta:</span><span class="sxs-lookup"><span data-stu-id="bcf19-144">Copy and paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13747.25 AS money) AS Sales, 55 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(9248.15 AS money) As Sales, 37 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1800.00 AS money) AS Sales, 24 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1125.00 AS money) AS Sales, 15 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory,  'Lens Adapter' as Product, CAST(742.50 AS money) AS Sales, 11 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1417.50 AS money) AS Sales, 21 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13497.30 AS money) AS Sales, 54 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(11997.60 AS money) AS Sales, 48 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(10247.95 AS money) As Sales, 41 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory, 'Tripod' as Product, CAST(1200.00 AS money) AS Sales, 16 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(2025.00 AS money) AS Sales, 27 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1425.00 AS money) AS Sales, 19 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(887.50 AS money) AS Sales, 13 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory, 'Lens Adapter' as Product, CAST(607.50 AS money) AS Sales, 9 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1215.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(10191.00 AS money) AS Sales, 79 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'North' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8772.00 AS money) AS Sales, 68 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(10578.00 AS money) AS Sales, 82 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Central' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(7218.10 AS money) AS Sales, 38 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'North' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'South' as Territory,'Digital' as Subcategory,'Slim Digital' as Product, CAST(9307.55 AS money) AS Sales, 49 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(3870.00 AS money) AS Sales, 30 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'North' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(5805.00 AS money) AS Sales, 45 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8643.00 AS money) AS Sales, 67 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Central' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(9877.40 AS money) AS Sales, 52 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'North' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(12536.70 AS money) AS Sales, 66 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'South' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(6648.25 AS money) AS Sales, 35 as Quantity  
    ```  
  
10. <span data-ttu-id="bcf19-145">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-145">Click **Next**.</span></span>  
  
##  <a name="2-organize-data-and-choose-layout-and-style-from-the-new-table-or-matrix-wizard"></a><a name="Groups"></a><span data-ttu-id="bcf19-146">2. organizar dados e escolher layout e estilo no assistente de nova tabela ou matriz</span><span class="sxs-lookup"><span data-stu-id="bcf19-146">2. Organize Data and Choose Layout and Style from the New Table or Matrix Wizard</span></span>  
 <span data-ttu-id="bcf19-147">Use o assistente para fornecer um design inicial no qual exibir dados.</span><span class="sxs-lookup"><span data-stu-id="bcf19-147">Use the wizard to provide a starting design on which to display data.</span></span> <span data-ttu-id="bcf19-148">O painel de visualização no assistente ajuda a visualizar o resultado dos dados de agrupamento antes de concluir o design da matriz.</span><span class="sxs-lookup"><span data-stu-id="bcf19-148">The preview pane in the wizard helps you to visualize the result of grouping data before you complete the matrix design.</span></span>  
  
#### <a name="to-organize-data-into-groups-and-choose-a-layout-and-style"></a><span data-ttu-id="bcf19-149">Para organizar dados em grupos e escolher um layout e um estilo</span><span class="sxs-lookup"><span data-stu-id="bcf19-149">To organize data into groups and choose a layout and style</span></span>  
  
1.  <span data-ttu-id="bcf19-150">Na página **Organizar campos** , arraste Territory de **Campos disponíveis** até **Grupos de linhas**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-150">On the **Arrange fields** page, drag Territory from **Available fields** to **Row groups**.</span></span>  
  
2.  <span data-ttu-id="bcf19-151">Arraste SalesDate até **Grupos de linhas** e coloque-o abaixo de Territory.</span><span class="sxs-lookup"><span data-stu-id="bcf19-151">Drag SalesDate to **Row groups** and place it below Territory.</span></span>  
  
     <span data-ttu-id="bcf19-152">A ordem na qual os campos são listados em **Grupos de linhas** define a hierarquia do grupo.</span><span class="sxs-lookup"><span data-stu-id="bcf19-152">The order in which fields are listed in **Row groups** defines the group hierarchy.</span></span> <span data-ttu-id="bcf19-153">As etapas 1 e 2 organizam os valores dos campos primeiro por território e, em seguida, por data das vendas.</span><span class="sxs-lookup"><span data-stu-id="bcf19-153">Steps 1 and 2 organize the values of the fields first by territory, and then by sales date.</span></span>  
  
3.  <span data-ttu-id="bcf19-154">Arraste Subcategory até **Grupos de colunas**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-154">Drag Subcategory to **Column groups**.</span></span>  
  
4.  <span data-ttu-id="bcf19-155">Arraste produto para **grupos de colunas** e coloque abaixo da subcategoria.</span><span class="sxs-lookup"><span data-stu-id="bcf19-155">Drag Product to **Column groups,** and then place below Subcategory.</span></span>  
  
     <span data-ttu-id="bcf19-156">A ordem na qual os campos são listados em **grupos de colunas** define a hierarquia de grupos.</span><span class="sxs-lookup"><span data-stu-id="bcf19-156">The order in which fields are listed in **Column groups** defines the group hierarchy.</span></span>  
  
     <span data-ttu-id="bcf19-157">As etapas 3 e 4 organizam os valores dos campos primeiro por subcategoria e, em seguida, por produto.</span><span class="sxs-lookup"><span data-stu-id="bcf19-157">Steps 3 and 4 organize the values for the fields first by subcategory, and then by product.</span></span>  
  
5.  <span data-ttu-id="bcf19-158">Arraste Sales até **Valores**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-158">Drag Sales to **Values**.</span></span>  
  
     <span data-ttu-id="bcf19-159">Sales é resumido com a função Soma, a função padrão para resumir campos numéricos.</span><span class="sxs-lookup"><span data-stu-id="bcf19-159">Sales is summarized with the Sum function, the default function to summarize numeric fields.</span></span>  
  
6.  <span data-ttu-id="bcf19-160">Arraste Quantity até **Valores**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-160">Drag Quantity to **Values**.</span></span>  
  
     <span data-ttu-id="bcf19-161">Quantity é resumida com a função Soma.</span><span class="sxs-lookup"><span data-stu-id="bcf19-161">Quantity is summarized with the Sum function.</span></span>  
  
     <span data-ttu-id="bcf19-162">As etapas 5 e 6 especificam os dados a serem exibidos nas células de dados da matriz.</span><span class="sxs-lookup"><span data-stu-id="bcf19-162">Steps 5 and 6 specify the data to display in the matrix data cells.</span></span>  
  
7.  <span data-ttu-id="bcf19-163">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-163">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="bcf19-164">Na página Escolher o Layout, em **Opções**, verifique se a opção **Mostrar subtotais e totais gerais** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="bcf19-164">On the Choose the Layout page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
9. <span data-ttu-id="bcf19-165">Verifique se a opção **Bloqueado, subtotal abaixo** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="bcf19-165">Verify that **Blocked, subtotal below** is selected.</span></span>  
  
10. <span data-ttu-id="bcf19-166">Verifique se a opção **Expandir/recolher grupos** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="bcf19-166">Verify the option **Expand/collapse groups** is selected.</span></span>  
  
11. <span data-ttu-id="bcf19-167">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-167">Click **Next**.</span></span>  
  
12. <span data-ttu-id="bcf19-168">Na página Escolha um estilo , no painel Estilos , selecione **Ardósia**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-168">On the Choose a Style page, in the Styles pane, select **Slate**.</span></span>  
  
13. <span data-ttu-id="bcf19-169">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-169">Click **Finish**.</span></span>  
  
     <span data-ttu-id="bcf19-170">A matriz é adicionada à superfície de design.</span><span class="sxs-lookup"><span data-stu-id="bcf19-170">The matrix is added to the design surface.</span></span> <span data-ttu-id="bcf19-171">O painel Grupos de Linhas mostra dois grupos de linhas: Territory e SalesDate.</span><span class="sxs-lookup"><span data-stu-id="bcf19-171">The Row Groups pane shows two row groups: Territory and SalesDate.</span></span> <span data-ttu-id="bcf19-172">O painel Grupos de Colunas mostra dois grupos de colunas: Subcategory e Product.</span><span class="sxs-lookup"><span data-stu-id="bcf19-172">The Column Groups pane shows two column groups: Subcategory and Product.</span></span> <span data-ttu-id="bcf19-173">Os dados detalhados são todos os dados recuperados pela consulta do conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="bcf19-173">Detail data is all the data that is retrieved by the dataset query.</span></span>  
  
14. <span data-ttu-id="bcf19-174">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="bcf19-174">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="bcf19-175">Para cada produto vendido em uma data específica, a matriz mostra a subcategoria a que o produto pertence e o território das vendas.</span><span class="sxs-lookup"><span data-stu-id="bcf19-175">For each product that is sold on a specific date, the matrix shows the subcategory to which the product belongs and the territory of the sales.</span></span>  
  
##  <a name="3-format-data"></a><a name="FormatData"></a><span data-ttu-id="bcf19-176">3. formatar dados</span><span class="sxs-lookup"><span data-stu-id="bcf19-176">3. Format Data</span></span>  
 <span data-ttu-id="bcf19-177">Por padrão, os dados resumidos do campo Sales exibem um número geral e o campo SalesDate exibe informações de data e hora.</span><span class="sxs-lookup"><span data-stu-id="bcf19-177">By default, the summary data for the Sales field displays a general number and the SalesDate field displays both date and time information.</span></span> <span data-ttu-id="bcf19-178">Formate o campo Sales para exibir o número como moeda e o campo SalesDate para exibir apenas a data.</span><span class="sxs-lookup"><span data-stu-id="bcf19-178">Format the Sales field to display the number as currency and the SalesDate field to display only the date.</span></span> <span data-ttu-id="bcf19-179">Ative/desative **Estilos de Espaço Reservado** para exibir caixas de texto formatadas e texto de espaço reservado como valores de exemplo.</span><span class="sxs-lookup"><span data-stu-id="bcf19-179">Toggle **Placeholder Styles** to display formatted text boxes and placeholder text as sample values.</span></span>  
  
#### <a name="to-format-fields"></a><span data-ttu-id="bcf19-180">Para formatar campos</span><span class="sxs-lookup"><span data-stu-id="bcf19-180">To format fields</span></span>  
  
1.  <span data-ttu-id="bcf19-181">Clique em **Design** a fim de alternar para a exibição de design.</span><span class="sxs-lookup"><span data-stu-id="bcf19-181">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="bcf19-182">Pressione a tecla Ctrl e, em seguida, selecione as nove células que contenham `[Sum(Sales)]`.</span><span class="sxs-lookup"><span data-stu-id="bcf19-182">Press the Ctrl key, and then select the nine cells that contain `[Sum(Sales)]`.</span></span>  
  
3.  <span data-ttu-id="bcf19-183">Na guia **Início** , no grupo **Número** , clique em **Moeda**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-183">On the **Home** tab, in the **Number** group, click **Currency**.</span></span> <span data-ttu-id="bcf19-184">As células são alteradas para mostrar a moeda formatada.</span><span class="sxs-lookup"><span data-stu-id="bcf19-184">The cells changeto show the formatted currency.</span></span>  
  
     <span data-ttu-id="bcf19-185">Se a configuração regional for Inglês (Estados Unidos), o texto de exemplo padrão será [**$12,345.00**].</span><span class="sxs-lookup"><span data-stu-id="bcf19-185">If your regional setting is English (United States), the default sample text is [**$12,345.00**].</span></span> <span data-ttu-id="bcf19-186">Se você não vir um valor de moeda de exemplo, clique em **estilos de espaço reservado** no grupo **números** e clique em **valores de exemplo**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-186">If you do not see an example currency value, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="bcf19-187">Clique na célula que contém `[SalesDate]`.</span><span class="sxs-lookup"><span data-stu-id="bcf19-187">Click the cell that contains `[SalesDate]`.</span></span>  
  
5.  <span data-ttu-id="bcf19-188">No grupo **número** , na lista suspensa, selecione **Data**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-188">In the **Number** group, from the drop-down list, select **Date**.</span></span>  
  
     <span data-ttu-id="bcf19-189">A célula exibe a data de exemplo **[1/31/2000]**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-189">The cell displays the example date **[1/31/2000]**.</span></span> <span data-ttu-id="bcf19-190">Se uma data de exemplo não estiver visível, clique em **Estilos de Espaço Reservado** no grupo **Números** e clique em **Valores de Exemplo**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-190">If you do not see an example date, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
6.  <span data-ttu-id="bcf19-191">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="bcf19-191">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="bcf19-192">Os valores de data só exibem datas e os valores de vendas são exibidos como moeda.</span><span class="sxs-lookup"><span data-stu-id="bcf19-192">The date values display only dates and the sales values display as currency.</span></span>  
  
##  <a name="4-add-adjacent-column-group"></a><a name="AdjacentGroup"></a><span data-ttu-id="bcf19-193">4. Adicionar grupo de colunas adjacente</span><span class="sxs-lookup"><span data-stu-id="bcf19-193">4. Add Adjacent Column Group</span></span>  
 <span data-ttu-id="bcf19-194">É possível aninhar grupos de linhas e de colunas em relações de pai e filho ou adjacentes em relações de irmão.</span><span class="sxs-lookup"><span data-stu-id="bcf19-194">You can nest row and column groups in parent child relationships or adjacent in sibling relationships.</span></span>  
  
 <span data-ttu-id="bcf19-195">Adicione um grupo de colunas adjacente ao grupo de colunas Subcategory, copie células para popular o novo grupo de colunas e, em seguida, use uma expressão para criar o valor do cabeçalho do grupo de colunas.</span><span class="sxs-lookup"><span data-stu-id="bcf19-195">Add a column group that is adjacent to the Subcategory column group, copy cells to populate the new column group, and then use an expression to create the value of the column group header.</span></span>  
  
#### <a name="to-add-an-adjacent-column-group"></a><span data-ttu-id="bcf19-196">Para adicionar um grupo de colunas adjacente</span><span class="sxs-lookup"><span data-stu-id="bcf19-196">To add an adjacent column group</span></span>  
  
1.  <span data-ttu-id="bcf19-197">Clique em **Design** para retornar à exibição de design.</span><span class="sxs-lookup"><span data-stu-id="bcf19-197">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="bcf19-198">Clique com o botão direito do mouse na célula que contém `[Subcategory]`, aponte para **Adicionar Grupo**e clique em **Adjacente à Direita**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-198">Right-click the cell that contains `[Subcategory]`, point to **Add Group**, and then click **Adjacent Right**.</span></span>  
  
     <span data-ttu-id="bcf19-199">A caixa de diálogo **Grupo Tablix** é aberta.</span><span class="sxs-lookup"><span data-stu-id="bcf19-199">The **Tablix Group** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="bcf19-200">Na lista **Agrupar Por** , selecione SalesDate e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-200">In the **Group By** list, select SalesDate, and then click **OK**.</span></span>  
  
     <span data-ttu-id="bcf19-201">Um novo grupo de colunas é adicionado à esquerda do grupo de colunas Subcategory.</span><span class="sxs-lookup"><span data-stu-id="bcf19-201">A new column group is added to the left of the Subcategory column group.</span></span>  
  
4.  <span data-ttu-id="bcf19-202">Clique com o botão direito do mouse na célula do novo grupo de colunas que contém `[SalesDate],` e clique em **Expressão**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-202">Right-click the cell in the new column group that contains `[SalesDate],` and then click **Expression**.</span></span>  
  
5.  <span data-ttu-id="bcf19-203">Copie a expressão a seguir para a caixa Expressão.</span><span class="sxs-lookup"><span data-stu-id="bcf19-203">Copy the following expression to expression box.</span></span>  
  
    ```  
    =WeekdayName(DatePart("w",Fields!SalesDate.Value))  
    ```  
  
     <span data-ttu-id="bcf19-204">Essa expressão extrai o nome do dia da semana da data das vendas.</span><span class="sxs-lookup"><span data-stu-id="bcf19-204">This expression extracts the weekday name from the sales date.</span></span> <span data-ttu-id="bcf19-205">Para obter mais informações, consulte [Expressões &#40;Construtor de Relatórios e SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bcf19-205">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md).</span></span>  
  
6.  <span data-ttu-id="bcf19-206">Clique com o botão direito do mouse na célula do grupo de colunas Subcategory que contém Total e clique em **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-206">Right-click the cell in the Subcategory column group that contains Total, and then click **Copy**.</span></span>  
  
7.  <span data-ttu-id="bcf19-207">Clique com o botão direito do mouse na célula logo abaixo da célula que contém a expressão criada na etapa 5 e clique em **Colar**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-207">Right-click the cell immediately below the cell that contains the expression you created in step 5 and click **Paste**.</span></span>  
  
8.  <span data-ttu-id="bcf19-208">Pressione a tecla Ctrl.</span><span class="sxs-lookup"><span data-stu-id="bcf19-208">Press the Ctrl key.</span></span>  
  
9. <span data-ttu-id="bcf19-209">No grupo Subcategory, clique no cabeçalho da coluna Sales e nas três células abaixo dela, clique com o botão direito do mouse nela e clique em **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-209">In the Subcategory group, click the Sales column header and the three cells below it, right-click, and then click **Copy**.</span></span>  
  
10. <span data-ttu-id="bcf19-210">Cole as quatro células nas quatro células vazias do novo grupo de colunas.</span><span class="sxs-lookup"><span data-stu-id="bcf19-210">Paste the four cells into the four empty cells in the new column group.</span></span>  
  
11. <span data-ttu-id="bcf19-211">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="bcf19-211">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="bcf19-212">O relatório inclui colunas nomeadas Monday e Tuesday.</span><span class="sxs-lookup"><span data-stu-id="bcf19-212">The report includes columns named Monday and Tuesday.</span></span> <span data-ttu-id="bcf19-213">O conjunto de dados contém apenas dados referentes a esses dois dias.</span><span class="sxs-lookup"><span data-stu-id="bcf19-213">The dataset contains only data for these two days.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bcf19-214">Se os dados incluíssem outros dias, o relatório também incluiria colunas para eles.</span><span class="sxs-lookup"><span data-stu-id="bcf19-214">If the data included other days, the report would include columns for them as well.</span></span> <span data-ttu-id="bcf19-215">Cada coluna tem o cabeçalho da coluna, `Sales` e os totais de vendas por região.</span><span class="sxs-lookup"><span data-stu-id="bcf19-215">Each column has the column header, `Sales`, and sales totals by territory.</span></span>  
  
##  <a name="5-change-column-widths"></a><a name="Width"></a><span data-ttu-id="bcf19-216">5. alterar larguras de coluna</span><span class="sxs-lookup"><span data-stu-id="bcf19-216">5. Change Column Widths</span></span>  
 <span data-ttu-id="bcf19-217">Um relatório que inclua uma matriz normalmente se expande horizontalmente, bem como verticalmente, quando executado.</span><span class="sxs-lookup"><span data-stu-id="bcf19-217">A report that includes a matrix typically expands horizontally as well as vertically when it runs.</span></span> <span data-ttu-id="bcf19-218">O controle da expansão horizontal será especialmente importante se você planejar exportar o relatório para formatos como Microsoft Word ou Adobe PDF, usados em relatórios impressos.</span><span class="sxs-lookup"><span data-stu-id="bcf19-218">Controlling horizontal expansion is particularly important if you plan to export the report to formats such as Microsoft Word or Adobe PDF that are used for printed reports.</span></span> <span data-ttu-id="bcf19-219">Se o relatório se expandir horizontalmente em várias páginas, será difícil compreender o relatório impresso.</span><span class="sxs-lookup"><span data-stu-id="bcf19-219">If the report expands horizontally across multiple pages, the printed report is difficult to understand.</span></span> <span data-ttu-id="bcf19-220">Para minimizar a expansão horizontal, é possível redimensionar colunas seguindo exclusivamente a largura necessária para exibir os dados sem quebra de texto.</span><span class="sxs-lookup"><span data-stu-id="bcf19-220">To minimize horizontal expansion, you can resize columns to be only the width necessary to display the data without wrapping.</span></span> <span data-ttu-id="bcf19-221">Também é possível renomear colunas para que os títulos se ajustem à largura necessária para exibir os dados.</span><span class="sxs-lookup"><span data-stu-id="bcf19-221">You can also rename columns so that their titles fit the width needed to display the data.</span></span>  
  
#### <a name="to-rename-and-resize-the-columns"></a><span data-ttu-id="bcf19-222">Para renomear e redimensionar as colunas</span><span class="sxs-lookup"><span data-stu-id="bcf19-222">To rename and resize the columns</span></span>  
  
1.  <span data-ttu-id="bcf19-223">Clique em **Design** para retornar à exibição de design.</span><span class="sxs-lookup"><span data-stu-id="bcf19-223">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="bcf19-224">Selecione o texto na coluna Quantity mais à esquerda e digite **QTY**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-224">Select the text in the furthest Quantity column to the left, and then type **QTY**.</span></span>  
  
     <span data-ttu-id="bcf19-225">O título da coluna agora é QTY.</span><span class="sxs-lookup"><span data-stu-id="bcf19-225">The column title is now QTY.</span></span>  
  
3.  <span data-ttu-id="bcf19-226">Repita a etapa 2 para as outras colunas nomeadas Quantity.</span><span class="sxs-lookup"><span data-stu-id="bcf19-226">Repeat step 2 for the other columns named Quantity.</span></span> <span data-ttu-id="bcf19-227">Há duas delas.</span><span class="sxs-lookup"><span data-stu-id="bcf19-227">There are two of them.</span></span>  
  
4.  <span data-ttu-id="bcf19-228">Clique na matriz para que os identificadores de coluna e de linha sejam exibidos acima e ao lado da matriz.</span><span class="sxs-lookup"><span data-stu-id="bcf19-228">Click the matrix so that column and row handles appear above and next to the matrix.</span></span>  
  
     <span data-ttu-id="bcf19-229">As barras em cinza ao longo da parte superior e ao lado da tabela são os identificadores de coluna e de linha.</span><span class="sxs-lookup"><span data-stu-id="bcf19-229">The gray bars along the top and side of the table are the column and row handles.</span></span>  
  
5.  <span data-ttu-id="bcf19-230">Para redimensionar a coluna QTY mais à esquerda, aponte para a linha entre os identificadores de coluna de forma que o cursor seja alterado para uma seta dupla.</span><span class="sxs-lookup"><span data-stu-id="bcf19-230">To resize the furthest QTY column to the left, point to the line between column handles so that the cursor changes into a double arrow.</span></span> <span data-ttu-id="bcf19-231">Arraste a coluna para a esquerda até que ela tenha 1,27 centímetros de largura.</span><span class="sxs-lookup"><span data-stu-id="bcf19-231">Drag the column towards the left until it is 1/2 inch wide.</span></span>  
  
     <span data-ttu-id="bcf19-232">Uma largura da coluna de 1,27 centímetros é suficiente para exibir a quantidade.</span><span class="sxs-lookup"><span data-stu-id="bcf19-232">A column width of 1/2 inch is adequate to display the quantity.</span></span>  
  
6.  <span data-ttu-id="bcf19-233">Repita a etapa 5 para as outras colunas nomeadas QTY.</span><span class="sxs-lookup"><span data-stu-id="bcf19-233">Repeat step 5 for the other columns named QTY.</span></span>  
  
7.  <span data-ttu-id="bcf19-234">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="bcf19-234">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="bcf19-235">As colunas no relatório que contenha quantidades agora são nomeadas QTY e estão mais estreitas.</span><span class="sxs-lookup"><span data-stu-id="bcf19-235">The columns in the report that contains quantities are now named QTY and the columns are narrower.</span></span>  
  
##  <a name="6-merge-matrix-cells"></a><a name="MergeCells"></a><span data-ttu-id="bcf19-236">6. mesclar células da matriz</span><span class="sxs-lookup"><span data-stu-id="bcf19-236">6. Merge Matrix Cells</span></span>  
 <span data-ttu-id="bcf19-237">A área de canto está no canto superior esquerdo da matriz.</span><span class="sxs-lookup"><span data-stu-id="bcf19-237">The corner area is in the upper left corner of the matrix.</span></span> <span data-ttu-id="bcf19-238">Dependendo do número de grupos de linhas e de colunas na matriz, o número de células na área de canto varia.</span><span class="sxs-lookup"><span data-stu-id="bcf19-238">Depending on the number of row and column groups in the matrix, the number of cells in the corner area varies.</span></span> <span data-ttu-id="bcf19-239">A matriz, interna neste tutorial, tem quatro células na área de canto.</span><span class="sxs-lookup"><span data-stu-id="bcf19-239">The matrix, built in this tutorial, has four cells in its corner area.</span></span> <span data-ttu-id="bcf19-240">As células são organizadas em duas linhas e duas colunas, o que reflete a profundidade das hierarquias dos grupos de linhas e de colunas.</span><span class="sxs-lookup"><span data-stu-id="bcf19-240">The cells are arranged in two rows and two columns, reflecting the depth of row and column group hierarchies.</span></span> <span data-ttu-id="bcf19-241">As quatro células não são usadas neste relatório, e você as mesclará em uma só.</span><span class="sxs-lookup"><span data-stu-id="bcf19-241">The four cells are not used in this report and you will merge them into one.</span></span>  
  
#### <a name="to-merge-matrix-cells"></a><span data-ttu-id="bcf19-242">Para mesclar células na matriz</span><span class="sxs-lookup"><span data-stu-id="bcf19-242">To merge matrix cells</span></span>  
  
1.  <span data-ttu-id="bcf19-243">Clique em **Design** para retornar à exibição de design.</span><span class="sxs-lookup"><span data-stu-id="bcf19-243">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="bcf19-244">Clique na matriz para que os identificadores de coluna e de linha sejam exibidos acima e ao lado da matriz.</span><span class="sxs-lookup"><span data-stu-id="bcf19-244">Click the matrix so that column and row handles appear above and next to the matrix.</span></span>  
  
3.  <span data-ttu-id="bcf19-245">Pressione a tecla Ctrl e, em seguida, selecione as quatro células de canto.</span><span class="sxs-lookup"><span data-stu-id="bcf19-245">Press the Ctrl key, and then select the four corner cells.</span></span>  
  
4.  <span data-ttu-id="bcf19-246">Clique com o botão direito do mouse nas células e clique em **mesclar células**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-246">Right-click the cells and then click **Merge Cells**.</span></span>  
  
5.  <span data-ttu-id="bcf19-247">Clique com o botão direito do mouse na célula de canto e clique em **Propriedades da caixa de texto**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-247">Right-click the corner cell, and then click **Text Box Properties**.</span></span>  
  
6.  <span data-ttu-id="bcf19-248">Clique na guia **Preenchimento** .</span><span class="sxs-lookup"><span data-stu-id="bcf19-248">Click the **Fill** tab.</span></span>  
  
7.  <span data-ttu-id="bcf19-249">Clique no botão (***FX***) para **cor de preenchimento**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-249">Click the (***fx***) button for **Fill color**.</span></span>  
  
8.  <span data-ttu-id="bcf19-250">Copie e cole a expressão a seguir na caixa de expressão.</span><span class="sxs-lookup"><span data-stu-id="bcf19-250">Copy and paste the following expression in the expression box.</span></span>  
  
    ```  
    #96a4b2  
    ```  
  
     <span data-ttu-id="bcf19-251">Trata-se do valor hexadecimal RGB de uma cor azul acinzentada usada no estilo Ardósia.</span><span class="sxs-lookup"><span data-stu-id="bcf19-251">This is the RGB hex value for a gray blue color used in the Slate style.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="bcf19-252">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="bcf19-252">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="bcf19-253">A matriz de canto superior é uma única célula e tem a mesma cor das células dos grupos de linhas e de colunas.</span><span class="sxs-lookup"><span data-stu-id="bcf19-253">The upper corner matrix is a single cell and has the same color as the row group and column group cells.</span></span>  
  
##  <a name="7-add-a-report-header-and-report-title"></a><a name="HeaderTitle"></a><span data-ttu-id="bcf19-254">7. adicionar um cabeçalho de relatório e um título de relatório</span><span class="sxs-lookup"><span data-stu-id="bcf19-254">7. Add a Report Header and Report Title</span></span>  
 <span data-ttu-id="bcf19-255">Um título é exibido na parte superior do relatório.</span><span class="sxs-lookup"><span data-stu-id="bcf19-255">A report title appears at the top of the report.</span></span> <span data-ttu-id="bcf19-256">É possível colocar o título em um cabeçalho do relatório. No entanto, se ele não usar um cabeçalho, será possível colocar o título em uma caixa de texto na parte superior do corpo do relatório.</span><span class="sxs-lookup"><span data-stu-id="bcf19-256">You can place the report title in a report header or if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="bcf19-257">Neste tutorial, você irá remover a caixa de texto na parte superior do relatório e adicionar um título ao cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="bcf19-257">In this tutorial, you will remove the text box at the top of the report and add a title to the header.</span></span>  
  
#### <a name="to-add-a-report-header-and-report-title"></a><span data-ttu-id="bcf19-258">Para adicionar um cabeçalho e um título de relatório</span><span class="sxs-lookup"><span data-stu-id="bcf19-258">To add a report header and report title</span></span>  
  
1.  <span data-ttu-id="bcf19-259">Clique em **Design** para retornar à exibição de design.</span><span class="sxs-lookup"><span data-stu-id="bcf19-259">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="bcf19-260">Clique na caixa de texto na parte superior do corpo do relatório que contém **clique para adicionar título**e pressione a tecla Delete.</span><span class="sxs-lookup"><span data-stu-id="bcf19-260">Click the text box at the top of the report body that contains **Click to add title**, and then press the Delete key.</span></span>  
  
3.  <span data-ttu-id="bcf19-261">Na guia **Inserir** da faixa de faixas, clique em **cabeçalho** e em **Adicionar cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-261">On the **Insert** tab of the ribbon, click **Header** and then click **Add Header**.</span></span>  
  
     <span data-ttu-id="bcf19-262">Um cabeçalho é adicionado à parte superior do corpo do relatório.</span><span class="sxs-lookup"><span data-stu-id="bcf19-262">A header is added to the top of the report body.</span></span>  
  
4.  <span data-ttu-id="bcf19-263">Na guia **Inserir** , clique em **Caixa de Texto**e arraste uma caixa de texto para dentro do cabeçalho do relatório.</span><span class="sxs-lookup"><span data-stu-id="bcf19-263">On the **Insert** tab, click **Text Box**, and then drag a text box inside the report header.</span></span> <span data-ttu-id="bcf19-264">Crie a caixa de texto com 15,24 centímetros de comprimento e 1,90 centímetros de altura e posicione-a no lado esquerdo do cabeçalho do relatório.</span><span class="sxs-lookup"><span data-stu-id="bcf19-264">Make the text box about 6 inches long and 3/4 inch tall and place it on the left side of the report header.</span></span>  
  
5.  <span data-ttu-id="bcf19-265">Na caixa de texto, digite **Vendas por Região, Subcategoria e Dia**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-265">In the text box, type **Sales by Territory, Subcategory, and Day**.</span></span>  
  
6.  <span data-ttu-id="bcf19-266">Selecione o texto que você digitou, clique com o botão direito do mouse e clique em **Propriedades de texto**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-266">Select the text you typed, right-click, and then click **Text Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bcf19-267">Para formatar caracteres simultaneamente, eles devem ser contíguos.</span><span class="sxs-lookup"><span data-stu-id="bcf19-267">To format characters at the same time, they must be contiguous.</span></span>  
  
7.  <span data-ttu-id="bcf19-268">Na caixa de diálogo **Propriedades de texto** , clique em **fonte**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-268">In the **Text Properties** dialog box, click **Font**.</span></span>  
  
8.  <span data-ttu-id="bcf19-269">Na lista **fonte** , selecione **Times New Roman**; em **tamanho** , selecione **24 pt**, **em cor** , selecione **bordô**e, em **estilo** , selecione **itálico**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-269">In the **Font** list, select **Times New Roman**; in **Size** select **24 pt**, in **Color** select **Maroon**, and in **Style** select **Italic**.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="bcf19-270">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="bcf19-270">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="bcf19-271">O relatório inclui um título do relatório no cabeçalho do relatório.</span><span class="sxs-lookup"><span data-stu-id="bcf19-271">The report includes a report title in the report header.</span></span>  
  
##  <a name="8-save-the-report"></a><a name="Save"></a><span data-ttu-id="bcf19-272">8. salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="bcf19-272">8. Save the Report</span></span>  
 <span data-ttu-id="bcf19-273">É possível salvar relatórios em um servidor de relatório, em uma biblioteca do SharePoint ou no computador.</span><span class="sxs-lookup"><span data-stu-id="bcf19-273">You can save reports to a report server, SharePoint library, or your computer.</span></span>  
  
 <span data-ttu-id="bcf19-274">Neste tutorial, salve o relatório em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="bcf19-274">In this tutorial, save the report to a report server.</span></span> <span data-ttu-id="bcf19-275">Se você não tiver acesso ao servidor de relatório, salve o relatório no computador.</span><span class="sxs-lookup"><span data-stu-id="bcf19-275">If you do not have access to a report server, save the report to your computer.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="bcf19-276">Para salvar o relatório em um servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="bcf19-276">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="bcf19-277">No botão **Construtor de Relatórios** , clique em **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-277">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="bcf19-278">Clique em **Sites e Servidores Recentes**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-278">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="bcf19-279">Selecione ou digite o nome do servidor de relatório no qual você tem permissão para salvar relatórios.</span><span class="sxs-lookup"><span data-stu-id="bcf19-279">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="bcf19-280">A mensagem "Conectando-se a um servidor de relatório" é exibida.</span><span class="sxs-lookup"><span data-stu-id="bcf19-280">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="bcf19-281">Quando a conexão for estabelecida, você verá o conteúdo da pasta de relatório que o administrador do servidor de relatório especificou como o local de relatório padrão.</span><span class="sxs-lookup"><span data-stu-id="bcf19-281">When the connection is complete, you will see the contents of the report folder that the report server administrator specified as the default report location.</span></span>  
  
4.  <span data-ttu-id="bcf19-282">Em **Nome**, substitua o nome padrão por **SalesByTerritorySubcategory**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-282">In **Name**, replace the default name with **SalesByTerritorySubcategory**.</span></span>  
  
5.  <span data-ttu-id="bcf19-283">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-283">Click **Save**.</span></span>  
  
 <span data-ttu-id="bcf19-284">O relatório será salvo no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="bcf19-284">The report is saved to the report server.</span></span> <span data-ttu-id="bcf19-285">O nome do servidor de relatório ao qual você está conectado é exibido na barra de status da parte inferior da janela.</span><span class="sxs-lookup"><span data-stu-id="bcf19-285">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="bcf19-286">Para salvar o relatório no computador</span><span class="sxs-lookup"><span data-stu-id="bcf19-286">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="bcf19-287">No botão **Construtor de Relatórios** , clique em **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-287">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="bcf19-288">Clique em **Área de Trabalho**, **Meus Documentos**ou **Meu Computador**e, em seguida, navegue até a pasta na qual você deseja salvar o relatório.</span><span class="sxs-lookup"><span data-stu-id="bcf19-288">Click **Desktop**, **My Documents**, or **My computer**, and then browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="bcf19-289">Em **Nome**, substitua o nome padrão por **SalesByTerritorySubcategory**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-289">In **Name**, replace the default name with **SalesByTerritorySubcategory**.</span></span>  
  
4.  <span data-ttu-id="bcf19-290">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-290">Click **Save**.</span></span>  
  
##  <a name="9-optional-rotate-text-box-270-degrees"></a><a name="RotateTextBox"></a><span data-ttu-id="bcf19-291">9. (opcional) girar caixa de texto 270 graus</span><span class="sxs-lookup"><span data-stu-id="bcf19-291">9. (Optional) Rotate Text Box 270 Degrees</span></span>  
 <span data-ttu-id="bcf19-292">Um relatório com matrizes pode se expandir horizontal e verticalmente quando executado.</span><span class="sxs-lookup"><span data-stu-id="bcf19-292">A report with matrices can expand horizontally and vertically when it runs.</span></span> <span data-ttu-id="bcf19-293">Girando-se caixas de texto verticalmente, ou em 270 graus, é possível economizar espaço horizontal.</span><span class="sxs-lookup"><span data-stu-id="bcf19-293">By rotating text boxes vertically, or 270 degrees, you can save horizontal space.</span></span> <span data-ttu-id="bcf19-294">Em seguida, o relatório renderizado é estreitado e, se exportado para um formato como o Microsoft Word, será mais provável o ajuste em uma página impressa.</span><span class="sxs-lookup"><span data-stu-id="bcf19-294">The rendered report is then narrower and if exported to a format such as Microsoft Word, will be more likely to fit on a printed page.</span></span>  
  
 <span data-ttu-id="bcf19-295">Uma caixa de texto também pode exibir texto na horizontal, vertical (de cima para baixo).</span><span class="sxs-lookup"><span data-stu-id="bcf19-295">A text box can also display text as horizontal, vertical (top to bottom).</span></span> <span data-ttu-id="bcf19-296">Para obter mais informações, consulte [Caixas de texto &#40;Construtor de Relatórios e SSRS&#41;](report-design/text-boxes-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bcf19-296">For more information, see [Text Boxes &#40;Report Builder and SSRS&#41;](report-design/text-boxes-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-rotate-text-box-270-degrees"></a><span data-ttu-id="bcf19-297">Para girar caixa de texto em 270 graus</span><span class="sxs-lookup"><span data-stu-id="bcf19-297">To rotate text box 270 degrees</span></span>  
  
1.  <span data-ttu-id="bcf19-298">Clique em **Design** para retornar à exibição de design.</span><span class="sxs-lookup"><span data-stu-id="bcf19-298">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="bcf19-299">Clique na célula que contenha `[Territory].`</span><span class="sxs-lookup"><span data-stu-id="bcf19-299">Click the cell that contains `[Territory].`</span></span>  
  
3.  <span data-ttu-id="bcf19-300">No painel Propriedades, localize a propriedade WritingMode e, em sua lista suspensa, selecione **Rotate270**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-300">In the Properties pane, locate the WritingMode property and in its drop-down list, select **Rotate270**.</span></span>  
  
     <span data-ttu-id="bcf19-301">Se o painel Propriedades não estiver aberto, clique na guia **Exibir** da faixa de opções e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="bcf19-301">If the Properties pane is not open, click the **View** tab of the ribbon, and then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="bcf19-302">Verifique se a propriedade PodeAmpliar está definida como `True` .</span><span class="sxs-lookup"><span data-stu-id="bcf19-302">Verify that the CanGrow property is set to `True`.</span></span>  
  
5.  <span data-ttu-id="bcf19-303">Redimensione a coluna Territory para ter 1,27 centímetro de largura e exclua o título da coluna.</span><span class="sxs-lookup"><span data-stu-id="bcf19-303">Resize the Territory column to be 1/2 inch wide and delete the column title.</span></span>  
  
6.  <span data-ttu-id="bcf19-304">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="bcf19-304">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="bcf19-305">O nome de território é escrito verticalmente, de baixo para cima.</span><span class="sxs-lookup"><span data-stu-id="bcf19-305">The territory name is written vertically, bottom to top.</span></span> <span data-ttu-id="bcf19-306">A altura do grupo de linhas Territory varia de acordo com o tamanho do nome do território.</span><span class="sxs-lookup"><span data-stu-id="bcf19-306">The height of the Territory row group varies by the length of the territory name.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="bcf19-307">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="bcf19-307">Next Steps</span></span>  
 <span data-ttu-id="bcf19-308">Isso conclui o tutorial sobre como criar um relatório de matriz.</span><span class="sxs-lookup"><span data-stu-id="bcf19-308">This concludes the tutorial for how to create a matrix report.</span></span> <span data-ttu-id="bcf19-309">Para obter mais informações sobre matrizes, consulte [tabelas, matrizes e listas &#40;Construtor de relatórios e ssrs&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md), [matrizes &#40;Construtor de Relatórios e SSRS&#41;](report-design/create-a-matrix-report-builder-and-ssrs.md), [áreas de região de dados Tablix &#40;Construtor de relatórios e SSRS&#41;](report-design/tablix-data-region-areas-report-builder-and-ssrs.md)e [células, linhas e colunas da região de dados Tablix &#40;Construtor de relatórios&#41; e SSRS](report-design/tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="bcf19-309">For more information about matrices, see [Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md), [Matrices &#40;Report Builder and SSRS&#41;](report-design/create-a-matrix-report-builder-and-ssrs.md), [Tablix Data Region Areas &#40;Report Builder and SSRS&#41;](report-design/tablix-data-region-areas-report-builder-and-ssrs.md), and [Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](report-design/tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcf19-310">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bcf19-310">See Also</span></span>  
 <span data-ttu-id="bcf19-311">[TUTORIAIS &#40;Construtor de Relatórios&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="bcf19-311">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="bcf19-312">Construtor de Relatórios no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="bcf19-312">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
