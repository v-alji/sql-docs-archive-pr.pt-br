---
title: 'Tutorial: Criar um relatório de tabela básico (Construtor de Relatórios) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d9e30521-f8ae-4c45-89c3-d40727f622f7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3587e2a53e2b09dd347a2733875eafd708b8a05a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571260"
---
# <a name="tutorial-creating-a-basic-table-report-report-builder"></a><span data-ttu-id="b7b46-102">Tutorial: Criar um relatório de tabela básico (Construtor de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="b7b46-102">Tutorial: Creating a Basic Table Report (Report Builder)</span></span>
  <span data-ttu-id="b7b46-103">Este tutorial ensina a criar um relatório de tabela básico com base em dados de vendas de exemplo.</span><span class="sxs-lookup"><span data-stu-id="b7b46-103">This tutorial teaches you to create a basic table report based on sample sales data.</span></span> <span data-ttu-id="b7b46-104">A ilustração a seguir mostra o relatório que você criará.</span><span class="sxs-lookup"><span data-stu-id="b7b46-104">The following illustration shows the report you will create.</span></span>  
  
 <span data-ttu-id="b7b46-105">![rs_CreateBasicReportTutorial](../../2014/tutorials/media/rs-createbasicreporttutorial.gif "rs_CreateBasicReportTutorial")</span><span class="sxs-lookup"><span data-stu-id="b7b46-105">![rs_CreateBasicReportTutorial](../../2014/tutorials/media/rs-createbasicreporttutorial.gif "rs_CreateBasicReportTutorial")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="b7b46-106">O que você aprenderá</span><span class="sxs-lookup"><span data-stu-id="b7b46-106">What You Will Learn</span></span>  
 <span data-ttu-id="b7b46-107">Neste tutorial, você aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="b7b46-107">In this tutorial, you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="b7b46-108">Criar um Novo Relatório em Introdução</span><span class="sxs-lookup"><span data-stu-id="b7b46-108">Create a New Report from Getting Started</span></span>](#CreateTable)  
  
    1.  [<span data-ttu-id="b7b46-109">Especificar uma conexão de dados no assistente de tabela</span><span class="sxs-lookup"><span data-stu-id="b7b46-109">Specify a Data Connection in the Table Wizard</span></span>](#DataConnection)  
  
    2.  [<span data-ttu-id="b7b46-110">Criar uma Consulta no Assistente de Tabela</span><span class="sxs-lookup"><span data-stu-id="b7b46-110">Create a Query in the Table Wizard</span></span>](#Query)  
  
    3.  [<span data-ttu-id="b7b46-111">Organizar Dados em Grupos no Assistente de Tabela</span><span class="sxs-lookup"><span data-stu-id="b7b46-111">Organize Data into Groups in the Table Wizard</span></span>](#Groups)  
  
    4.  [<span data-ttu-id="b7b46-112">Adicionar Linhas de Subtotal e de Total no Assistente de Tabela</span><span class="sxs-lookup"><span data-stu-id="b7b46-112">Add Subtotal and Total Rows in the Table Wizard</span></span>](#Subtotals)  
  
    5.  [<span data-ttu-id="b7b46-113">Escolher um Estilo no Assistente de Tabela</span><span class="sxs-lookup"><span data-stu-id="b7b46-113">Choose a Style in the Table Wizard</span></span>](#Style)  
  
2.  [<span data-ttu-id="b7b46-114">Formatar dados como moeda</span><span class="sxs-lookup"><span data-stu-id="b7b46-114">Format Data as Currency</span></span>](#FormatCurrency)  
  
3.  [<span data-ttu-id="b7b46-115">Formatar dados como data</span><span class="sxs-lookup"><span data-stu-id="b7b46-115">Format Data as Date</span></span>](#FormatDate)  
  
4.  [<span data-ttu-id="b7b46-116">Alterar a Largura das Colunas</span><span class="sxs-lookup"><span data-stu-id="b7b46-116">Change Column Widths</span></span>](#Width)  
  
5.  [<span data-ttu-id="b7b46-117">Adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="b7b46-117">Add a Report Title</span></span>](#Title)  
  
6.  [<span data-ttu-id="b7b46-118">Salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="b7b46-118">Save the Report</span></span>](#Save)  
  
7.  [<span data-ttu-id="b7b46-119">Exportar o relatório</span><span class="sxs-lookup"><span data-stu-id="b7b46-119">Export the Report</span></span>](#Export)  
  
 <span data-ttu-id="b7b46-120">Tempo estimado para concluir este tutorial: 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="b7b46-120">Estimated time to complete this tutorial: 20 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7b46-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7b46-121">Requirements</span></span>  
 <span data-ttu-id="b7b46-122">Para obter mais informações sobre os requisitos, consulte [Pré-requisitos para tutoriais &#40;Construtor de Relatórios&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="b7b46-122">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-new-report-from-getting-started"></a><a name="CreateTable"></a><span data-ttu-id="b7b46-123">1. criar um novo relatório de Introdução</span><span class="sxs-lookup"><span data-stu-id="b7b46-123">1. Create a New Report from Getting Started</span></span>  
 <span data-ttu-id="b7b46-124">Crie um relatório de tabela na caixa de diálogo **introdução** .</span><span class="sxs-lookup"><span data-stu-id="b7b46-124">Create a table report from the **Getting Started** dialog box.</span></span> <span data-ttu-id="b7b46-125">Há dois modos: design de relatório e design de conjunto de dados compartilhado.</span><span class="sxs-lookup"><span data-stu-id="b7b46-125">There are two modes: report design and shared dataset design.</span></span> <span data-ttu-id="b7b46-126">No modo design de relatório, especifique dados no painel de Dados do Relatório e o layout do relatório na superfície de design.</span><span class="sxs-lookup"><span data-stu-id="b7b46-126">In report design mode, you specify data in the Report Data pane and the report layout on the design surface.</span></span> <span data-ttu-id="b7b46-127">No modo design de conjunto de dados compartilhado, crie consultas de conjunto de dados para compartilhar com outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="b7b46-127">In shared dataset design mode, you create dataset queries to share with others.</span></span> <span data-ttu-id="b7b46-128">Neste tutorial, você usará o modo design de relatório.</span><span class="sxs-lookup"><span data-stu-id="b7b46-128">In this tutorial, you will be using report design mode.</span></span>  
  
#### <a name="to-create-a-new-report"></a><span data-ttu-id="b7b46-129">Para criar um novo relatório</span><span class="sxs-lookup"><span data-stu-id="b7b46-129">To create a new report</span></span>  
  
1.  <span data-ttu-id="b7b46-130">Clique em **Iniciar**, aponte para **Programas**, para **Construtor de Relatórios do Microsoft SQL Server 2012**e clique em **Construtor de Relatórios**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-130">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="b7b46-131">A caixa de diálogo **Guia de Introdução** é aberta.</span><span class="sxs-lookup"><span data-stu-id="b7b46-131">The **Getting Started** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b7b46-132">Se a caixa de diálogo **introdução** não for exibida, no botão **Construtor de relatórios** , clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-132">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="b7b46-133">No painel esquerdo, verifique se **Novo Relatório** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="b7b46-133">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="b7b46-134">No painel direito, verifique se a opção **Assistente de Tabela ou Matriz** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="b7b46-134">In the right pane, verify that **Table or Matrix Wizard** is selected.</span></span>  
  
##  <a name="1a-specify-a-data-connection-in-the-table-wizard"></a><a name="DataConnection"></a><span data-ttu-id="b7b46-135">1a.</span><span class="sxs-lookup"><span data-stu-id="b7b46-135">1a.</span></span> <span data-ttu-id="b7b46-136">Especificar uma conexão de dados no assistente de tabela</span><span class="sxs-lookup"><span data-stu-id="b7b46-136">Specify a Data Connection in the Table Wizard</span></span>  
 <span data-ttu-id="b7b46-137">Uma conexão de dados contém as informações para estabelecer conexões com uma fonte de dados externa, como um banco de dados [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b7b46-137">A data connection contains the information to connect to an external data source such as a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="b7b46-138">Geralmente, você obtém as informações sobre a conexão e o tipo de credenciais a ser usado do proprietário da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b7b46-138">Usually, you get the connection information and the type of credentials to use from the data source owner.</span></span> <span data-ttu-id="b7b46-139">Para especificar uma conexão de dados, você pode usar uma fonte de dados compartilhada do servidor de relatório ou criar uma fonte de dados inserida que será usada somente neste relatório.</span><span class="sxs-lookup"><span data-stu-id="b7b46-139">To specify a data connection, you can use a shared data source from the report server or create an embedded data source that is used only in this report.</span></span>  
  
 <span data-ttu-id="b7b46-140">Neste tutorial, você usará uma fonte de dados inserida.</span><span class="sxs-lookup"><span data-stu-id="b7b46-140">In this tutorial, you will use an embedded data source.</span></span> <span data-ttu-id="b7b46-141">Para saber mais sobre como usar fontes de dados compartilhadas, consulte [Formas alternativas de obter uma conexão de dados &#40;Construtor de Relatórios&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="b7b46-141">To learn more about using a shared data sources, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
#### <a name="to-create-an-embedded-data-source"></a><span data-ttu-id="b7b46-142">Para criar uma fonte de dados inserida</span><span class="sxs-lookup"><span data-stu-id="b7b46-142">To create an embedded data source</span></span>  
  
1.  <span data-ttu-id="b7b46-143">Na página **Escolher um conjunto de dados** , selecione **Criar um conjunto de dados**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-143">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="b7b46-144">A página **Escolher uma conexão com uma fonte de dados** é aberta.</span><span class="sxs-lookup"><span data-stu-id="b7b46-144">The **Choose a connection to a data source** page opens.</span></span>  
  
2.  <span data-ttu-id="b7b46-145">Clique em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-145">Click **New**.</span></span> <span data-ttu-id="b7b46-146">A caixa de diálogo **Propriedades da Fonte de Dados** é aberta.</span><span class="sxs-lookup"><span data-stu-id="b7b46-146">The **Data Source Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="b7b46-147">Em **nome**, digite **vendas do produto** um nome para a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b7b46-147">In **Name**, type **Product Sales** a name for the data source.</span></span>  
  
4.  <span data-ttu-id="b7b46-148">Em **Selecionar um tipo de conexão**, verifique se a opção **Microsoft SQL Server** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="b7b46-148">In **Select a connection type**, verify that **Microsoft SQL Server** is selected.</span></span>  
  
5.  <span data-ttu-id="b7b46-149">Em **cadeia de conexão**, digite o seguinte texto, em que *\<servername>* é o nome de uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="b7b46-149">In **Connection string**, type the following text, where *\<servername>* is the name of an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]:</span></span>  
  
    ```  
    Data Source=<servername>  
    ```  
  
     <span data-ttu-id="b7b46-150">Como você usará uma consulta que contém os dados, em vez de recuperá-los de um banco de dados, a cadeia de conexão não incluirá o nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b7b46-150">Because you will use a query that contains the data instead of retrieving the data from a database, the connection string does not include the database name.</span></span> <span data-ttu-id="b7b46-151">Para saber mais, veja [Pré-requisitos para tutoriais &#40;Construtor de Relatórios&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="b7b46-151">For more information, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
6.  <span data-ttu-id="b7b46-152">Clique em **Credenciais**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-152">Click **Credentials**.</span></span> <span data-ttu-id="b7b46-153">Insira as credenciais necessárias para acessar a fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="b7b46-153">Enter the credentials that you need to access the external data source.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="b7b46-154">Você voltará à página **Escolher uma conexão com uma fonte de dados** .</span><span class="sxs-lookup"><span data-stu-id="b7b46-154">You are back on the **Choose a connection to a data source** page.</span></span>  
  
8.  <span data-ttu-id="b7b46-155">Para verificar se é possível se conectar à fonte de dados, clique em **Testar Conexão**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-155">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
     <span data-ttu-id="b7b46-156">A mensagem "Conexão criada com êxito" será exibida.</span><span class="sxs-lookup"><span data-stu-id="b7b46-156">The message "Connection created successfully" appears.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="b7b46-157">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-157">Click **Next**.</span></span>  
  
##  <a name="1b-create-a-query-in-the-table-wizard"></a><a name="Query"></a><span data-ttu-id="b7b46-158">1B.</span><span class="sxs-lookup"><span data-stu-id="b7b46-158">1b.</span></span> <span data-ttu-id="b7b46-159">Criar uma Consulta no Assistente de Tabela</span><span class="sxs-lookup"><span data-stu-id="b7b46-159">Create a Query in the Table Wizard</span></span>  
 <span data-ttu-id="b7b46-160">Em um relatório, é possível usar um conjunto de dados compartilhado que tenha uma consulta predefinida. Se preferir, crie um conjunto de dados inserido para ser usado somente em seu relatório.</span><span class="sxs-lookup"><span data-stu-id="b7b46-160">In a report, you can use a shared dataset that has a predefined query, or you can create an embedded dataset for use only in your report.</span></span> <span data-ttu-id="b7b46-161">Neste tutorial, você criará um conjunto de dados inserido.</span><span class="sxs-lookup"><span data-stu-id="b7b46-161">In this tutorial, you will create an embedded dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b7b46-162">Neste tutorial, a consulta contém os valores de dados para que não precise de uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="b7b46-162">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="b7b46-163">Isso torna a consulta bastante longa.</span><span class="sxs-lookup"><span data-stu-id="b7b46-163">This makes the query quite long.</span></span> <span data-ttu-id="b7b46-164">Em um ambiente empresarial, uma consulta não conteria os dados.</span><span class="sxs-lookup"><span data-stu-id="b7b46-164">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="b7b46-165">Isso é apenas para fins de aprendizado.</span><span class="sxs-lookup"><span data-stu-id="b7b46-165">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-query"></a><span data-ttu-id="b7b46-166">Para criar uma consulta</span><span class="sxs-lookup"><span data-stu-id="b7b46-166">To create a query</span></span>  
  
1.  <span data-ttu-id="b7b46-167">Na página **Criar uma consulta** , o designer de consultas relacionais é aberto.</span><span class="sxs-lookup"><span data-stu-id="b7b46-167">On the **Design a query** page, the relational query designer is open.</span></span> <span data-ttu-id="b7b46-168">Para este tutorial, você usará o designer de consulta baseado em texto.</span><span class="sxs-lookup"><span data-stu-id="b7b46-168">For this tutorial, you will use the text-based query designer.</span></span>  
  
     <span data-ttu-id="b7b46-169">Clique em **Editar como texto**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-169">Click **Edit As Text**.</span></span> <span data-ttu-id="b7b46-170">O designer de consulta baseado em texto exibe um painel de consulta e um painel de resultados.</span><span class="sxs-lookup"><span data-stu-id="b7b46-170">The text-based query designer displays a query pane and a results pane.</span></span>  
  
2.  <span data-ttu-id="b7b46-171">Cole a consulta [!INCLUDE[tsql](../includes/tsql-md.md)] a seguir na caixa **Consulta** .</span><span class="sxs-lookup"><span data-stu-id="b7b46-171">Paste the following [!INCLUDE[tsql](../includes/tsql-md.md)] query into the **Query** box.</span></span>  
  
    ```  
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Carrying Case' as Product, CAST(9924.60 AS money) AS Sales, 68 as Quantity  
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
  
3.  <span data-ttu-id="b7b46-172">Na barra de ferramentas do designer de consultas, clique em **executar** (**!**).</span><span class="sxs-lookup"><span data-stu-id="b7b46-172">On the query designer toolbar, click **Run** (**!**).</span></span>  
  
     <span data-ttu-id="b7b46-173">A consulta executa e exibe o conjunto de resultados para os campos SalesDate, Subcategory, Product, Sales e Quantity.</span><span class="sxs-lookup"><span data-stu-id="b7b46-173">The query runs and displays the result set for the fields SalesDate, Subcategory, Product, Sales, and Quantity.</span></span>  
  
     <span data-ttu-id="b7b46-174">No conjunto de resultados, os cabeçalhos das colunas têm como base os nomes na consulta.</span><span class="sxs-lookup"><span data-stu-id="b7b46-174">In the result set, the column headings are based on the names in the query.</span></span> <span data-ttu-id="b7b46-175">No conjunto de dados, os cabeçalhos das colunas se transformam nos nomes dos campos e são salvos no relatório.</span><span class="sxs-lookup"><span data-stu-id="b7b46-175">In the dataset, the column headings become the field names, and are saved in the report.</span></span> <span data-ttu-id="b7b46-176">Depois de concluir o assistente, você poderá usar o painel de Dados do Relatório para exibir a coleção de campos do conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="b7b46-176">After you complete the wizard, you can use the Report Data pane to view the collection of dataset fields.</span></span>  
  
4.  <span data-ttu-id="b7b46-177">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-177">Click **Next**.</span></span>  
  
##  <a name="1c-organize-data-into-groups-in-the-table-wizard"></a><a name="Groups"></a><span data-ttu-id="b7b46-178">1C.</span><span class="sxs-lookup"><span data-stu-id="b7b46-178">1c.</span></span> <span data-ttu-id="b7b46-179">Organizar Dados em Grupos no Assistente de Tabela</span><span class="sxs-lookup"><span data-stu-id="b7b46-179">Organize Data into Groups in the Table Wizard</span></span>  
 <span data-ttu-id="b7b46-180">Quando você seleciona campos nos quais fazer agrupamentos, cria uma tabela com linhas e colunas que exibem dados detalhados e dados agregados.</span><span class="sxs-lookup"><span data-stu-id="b7b46-180">When you select fields to group on, you design a table that has rows and columns that display detail data and aggregated data.</span></span>  
  
#### <a name="to-organize-data-into-groups"></a><span data-ttu-id="b7b46-181">Para organizar dados em grupos</span><span class="sxs-lookup"><span data-stu-id="b7b46-181">To organize data into groups</span></span>  
  
1.  <span data-ttu-id="b7b46-182">Na página **organizar campos** , arraste produto para **valores**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-182">On the **Arrange fields** page, drag Product to **Values**.</span></span>  
  
2.  <span data-ttu-id="b7b46-183">Arraste Quantity até **Values** e coloque-o abaixo de Product.</span><span class="sxs-lookup"><span data-stu-id="b7b46-183">Drag Quantity to **Values** and place below Product.</span></span>  
  
     <span data-ttu-id="b7b46-184">Quantity é automaticamente agregado pela função Sum, a função de agregação padrão para campos numéricos.</span><span class="sxs-lookup"><span data-stu-id="b7b46-184">Quantity is automatically aggregated by the Sum function, the default aggregate for numeric fields.</span></span> <span data-ttu-id="b7b46-185">O valor é [Sum(Quantity)].</span><span class="sxs-lookup"><span data-stu-id="b7b46-185">The value is [Sum(Quantity)].</span></span>  
  
     <span data-ttu-id="b7b46-186">Você pode abrir a lista suspensa para exibir as outras funções de agregação disponíveis.</span><span class="sxs-lookup"><span data-stu-id="b7b46-186">You can open the drop-down list to view the other aggregate functions available.</span></span> <span data-ttu-id="b7b46-187">Não altere a função de agregação.</span><span class="sxs-lookup"><span data-stu-id="b7b46-187">Do not change the aggregate function.</span></span>  
  
3.  <span data-ttu-id="b7b46-188">Arraste Sales até **Values** e coloque-o abaixo de [Sum(Quantity)].</span><span class="sxs-lookup"><span data-stu-id="b7b46-188">Drag Sales to **Values** and place below [Sum(Quantity)].</span></span>  
  
     <span data-ttu-id="b7b46-189">Sales é agregado pela função Sum.</span><span class="sxs-lookup"><span data-stu-id="b7b46-189">Sales is aggregated by the Sum function.</span></span> <span data-ttu-id="b7b46-190">O valor é [Sum(Sales)].</span><span class="sxs-lookup"><span data-stu-id="b7b46-190">The value is [Sum(Sales)].</span></span>  
  
     <span data-ttu-id="b7b46-191">As etapas 1, 2 e 3 especificam os dados a serem exibidos na tabela.</span><span class="sxs-lookup"><span data-stu-id="b7b46-191">Steps 1, 2, and 3 specify the data to display in the table.</span></span>  
  
4.  <span data-ttu-id="b7b46-192">Arraste SalesDate até **Grupos de linhas**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-192">Drag SalesDate to **Row groups**.</span></span>  
  
5.  <span data-ttu-id="b7b46-193">Arraste Subcategory até **Grupos de linhas** e coloque-o abaixo de SalesDate.</span><span class="sxs-lookup"><span data-stu-id="b7b46-193">Drag Subcategory to **Row groups** and place below SalesDate.</span></span>  
  
     <span data-ttu-id="b7b46-194">As etapas 4 e 5 organizam os valores dos campos primeiro por data e depois por subcategoria de produto dessa data.</span><span class="sxs-lookup"><span data-stu-id="b7b46-194">Steps 4 and 5 organize the values for the fields first by date, and then by product subcategory for that date.</span></span>  
  
6.  <span data-ttu-id="b7b46-195">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-195">Click **Next**.</span></span>  
  
##  <a name="1d-add-subtotal-and-total-rows-in-the-table-wizard"></a><a name="Subtotals"></a><span data-ttu-id="b7b46-196">1D.</span><span class="sxs-lookup"><span data-stu-id="b7b46-196">1d.</span></span> <span data-ttu-id="b7b46-197">Adicionar Linhas de Subtotal e de Total no Assistente de Tabela</span><span class="sxs-lookup"><span data-stu-id="b7b46-197">Add Subtotal and Total Rows in the Table Wizard</span></span>  
 <span data-ttu-id="b7b46-198">Depois de criar grupos, é possível adicionar e formatar linhas nas quais exibir valores de agregação dos campos.</span><span class="sxs-lookup"><span data-stu-id="b7b46-198">After you create groups, you can add and format rows on which to display aggregate values for the fields.</span></span> <span data-ttu-id="b7b46-199">Você pode optar por exibir todos os dados ou deixar um usuário expandir e recolher dados agrupados de forma interativa.</span><span class="sxs-lookup"><span data-stu-id="b7b46-199">You can choose whether to show all the data or to let a user expand and collapse grouped data interactively.</span></span>  
  
#### <a name="to-add-subtotals-and-totals"></a><span data-ttu-id="b7b46-200">Para adicionar subtotais e totais</span><span class="sxs-lookup"><span data-stu-id="b7b46-200">To add subtotals and totals</span></span>  
  
1.  <span data-ttu-id="b7b46-201">Na página **escolher o layout** , em opções, verifique se a **opção** **Mostrar Subtotais e totais gerais** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="b7b46-201">On the **Choose the layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
2.  <span data-ttu-id="b7b46-202">Verifique se a opção **Bloqueado, subtotal abaixo** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="b7b46-202">Verify that **Blocked, subtotal below** is selected.</span></span>  
  
     <span data-ttu-id="b7b46-203">O painel Visualizar assistente exibe uma tabela com cinco linhas.</span><span class="sxs-lookup"><span data-stu-id="b7b46-203">The wizard Preview pane displays a table with five rows.</span></span> <span data-ttu-id="b7b46-204">Ao executar o relatório, cada linha será exibida da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="b7b46-204">When you run the report, each row will display in the following way:</span></span>  
  
    1.  <span data-ttu-id="b7b46-205">A primeira linha será repetida uma vez para a tabela para mostrar títulos de coluna.</span><span class="sxs-lookup"><span data-stu-id="b7b46-205">The first row will repeat once for the table to show column headings.</span></span>  
  
    2.  <span data-ttu-id="b7b46-206">A segunda linha será repetida uma vez para cada item de linha no pedido de vendas e exibirá o nome do produto, a quantidade do pedido e o total da linha.</span><span class="sxs-lookup"><span data-stu-id="b7b46-206">The second row will repeat once for each line item in the sales order and display the product name, order quantity, and line total.</span></span>  
  
    3.  <span data-ttu-id="b7b46-207">A terceira linha será repetida uma vez para cada pedido de vendas para exibir subtotais por pedido.</span><span class="sxs-lookup"><span data-stu-id="b7b46-207">The third row will repeat once for each sales order to display subtotals per order.</span></span>  
  
    4.  <span data-ttu-id="b7b46-208">A quarta será repetida uma vez para cada data de pedido de vendas para exibir subtotais por dia.</span><span class="sxs-lookup"><span data-stu-id="b7b46-208">The fourth row will repeat once for each order date to display the subtotals per day.</span></span>  
  
    5.  <span data-ttu-id="b7b46-209">A quinta linha será repetida uma vez para a tabela para mostrar totais gerais.</span><span class="sxs-lookup"><span data-stu-id="b7b46-209">The fifth row will repeat once for the table to display the grand totals.</span></span>  
  
3.  <span data-ttu-id="b7b46-210">Desmarque a opção **Expandir/recolher grupos**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-210">Clear the option **Expand/collapse groups**.</span></span> <span data-ttu-id="b7b46-211">Neste tutorial, o relatório criado não usa o recurso de detalhamento que permite a um usuário expandir uma hierarquia de grupo pai para exibir linhas de grupo filho e linhas de detalhes.</span><span class="sxs-lookup"><span data-stu-id="b7b46-211">In this tutorial, the report you create does not use the drilldown feature that lets a user expand a parent group hierarchy to display child group rows and detail rows.</span></span>  
  
4.  <span data-ttu-id="b7b46-212">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-212">Click **Next**.</span></span>  
  
##  <a name="1e-choose-a-style-in-the-table-wizard"></a><a name="Style"></a><span data-ttu-id="b7b46-213">1e.</span><span class="sxs-lookup"><span data-stu-id="b7b46-213">1e.</span></span> <span data-ttu-id="b7b46-214">Escolher um Estilo no Assistente de Tabela</span><span class="sxs-lookup"><span data-stu-id="b7b46-214">Choose a Style in the Table Wizard</span></span>  
 <span data-ttu-id="b7b46-215">Um estilo especifica um estilo de fonte, um conjunto de cores e um estilo de borda.</span><span class="sxs-lookup"><span data-stu-id="b7b46-215">A style specifies a font style, a set of colors, and a border style.</span></span>  
  
#### <a name="to-specify-a-table-style"></a><span data-ttu-id="b7b46-216">Para especificar um estilo de tabela</span><span class="sxs-lookup"><span data-stu-id="b7b46-216">To specify a table style</span></span>  
  
1.  <span data-ttu-id="b7b46-217">Na página **escolher um estilo** , no painel estilos, selecione oceano.</span><span class="sxs-lookup"><span data-stu-id="b7b46-217">On the **Choose a Style** page, in the Styles pane, select Ocean.</span></span>  
  
     <span data-ttu-id="b7b46-218">O painel Visualizar exibirá um exemplo da tabela com esse estilo.</span><span class="sxs-lookup"><span data-stu-id="b7b46-218">The Preview pane displays a sample of the table with that style.</span></span>  
  
2.  <span data-ttu-id="b7b46-219">Se preferir, clique nos demais estilos para visualizar exemplos de suas aplicações.</span><span class="sxs-lookup"><span data-stu-id="b7b46-219">Optionally, click the other styles to see the sample with them applied.</span></span>  
  
3.  <span data-ttu-id="b7b46-220">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-220">Click **Finish**.</span></span>  
  
 <span data-ttu-id="b7b46-221">A tabela é adicionada à superfície de design.</span><span class="sxs-lookup"><span data-stu-id="b7b46-221">The table is added to the design surface.</span></span> <span data-ttu-id="b7b46-222">A tabela tem 5 colunas e 5 linhas.</span><span class="sxs-lookup"><span data-stu-id="b7b46-222">The table has 5 columns and 5 rows.</span></span> <span data-ttu-id="b7b46-223">O painel Grupos de Linhas mostra três grupos de linhas: SalesDate, Subcategory e Details.</span><span class="sxs-lookup"><span data-stu-id="b7b46-223">The Row Groups pane shows three row groups: SalesDate, Subcategory, and Details.</span></span> <span data-ttu-id="b7b46-224">Os dados detalhados são todos os dados recuperados pela consulta do conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="b7b46-224">Detail data is all the data that is retrieved by the dataset query.</span></span>  
  
##  <a name="2-format-data-as-currency"></a><a name="FormatCurrency"></a><span data-ttu-id="b7b46-225">2. formatar dados como moeda</span><span class="sxs-lookup"><span data-stu-id="b7b46-225">2. Format Data as Currency</span></span>  
 <span data-ttu-id="b7b46-226">Por padrão, os dados resumidos do campo Sales exibe um número geral.</span><span class="sxs-lookup"><span data-stu-id="b7b46-226">By default, the summary data for the Sales field displays a general number.</span></span> <span data-ttu-id="b7b46-227">Formate-o para exibir o número como moeda.</span><span class="sxs-lookup"><span data-stu-id="b7b46-227">Format it to display the number as currency.</span></span> <span data-ttu-id="b7b46-228">Ative/desative **Estilos de Espaço Reservado** para exibir caixas de texto formatadas e texto de espaço reservado como valores de exemplo.</span><span class="sxs-lookup"><span data-stu-id="b7b46-228">Toggle **Placeholder Styles** to display formatted text boxes and placeholder text as sample values.</span></span>  
  
#### <a name="to-format-a-currency-field"></a><span data-ttu-id="b7b46-229">Para formatar um campo de conversor de moedas</span><span class="sxs-lookup"><span data-stu-id="b7b46-229">To format a currency field</span></span>  
  
1.  <span data-ttu-id="b7b46-230">Clique em **Design** a fim de alternar para a exibição de design.</span><span class="sxs-lookup"><span data-stu-id="b7b46-230">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="b7b46-231">Clique na célula da segunda linha (na linha dos cabeçalhos das colunas) na coluna Vendas e arraste-a para baixo para selecionar todas as células que contenham `[Sum(Sales)]`.</span><span class="sxs-lookup"><span data-stu-id="b7b46-231">Click the cell in the second row (under the column headings row) in the Sales column and drag down to select all cells that contain `[Sum(Sales)]`.</span></span>  
  
3.  <span data-ttu-id="b7b46-232">Na guia **Início** , no grupo **Número** , clique no botão **Moeda** .</span><span class="sxs-lookup"><span data-stu-id="b7b46-232">On the **Home** tab, in the **Number** group, click the **Currency** button.</span></span> <span data-ttu-id="b7b46-233">As células são alteradas para mostrar a moeda formatada.</span><span class="sxs-lookup"><span data-stu-id="b7b46-233">The cells change to show the formatted currency.</span></span>  
  
     <span data-ttu-id="b7b46-234">Se a configuração regional for Inglês (Estados Unidos), o texto de exemplo padrão será [**$12,345.00**].</span><span class="sxs-lookup"><span data-stu-id="b7b46-234">If your regional setting is English (United States), the default sample text is [**$12,345.00**].</span></span> <span data-ttu-id="b7b46-235">Se você não vir um valor de moeda de exemplo, clique em **estilos de espaço reservado** no grupo **números** e clique em **valores de exemplo**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-235">If you do not see an example currency value, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="b7b46-236">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="b7b46-236">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="b7b46-237">Os valores resumidos de Vendas são exibidos como conversor de moedas.</span><span class="sxs-lookup"><span data-stu-id="b7b46-237">The summary values for Sales display as currency.</span></span>  
  
##  <a name="3-format-data-as-date"></a><a name="FormatDate"></a><span data-ttu-id="b7b46-238">3. formatar dados como data</span><span class="sxs-lookup"><span data-stu-id="b7b46-238">3. Format Data as Date</span></span>  
 <span data-ttu-id="b7b46-239">Por padrão, o campo SalesDate exibe informações de data e hora.</span><span class="sxs-lookup"><span data-stu-id="b7b46-239">By default, the SalesDate field displays both date and time information.</span></span> <span data-ttu-id="b7b46-240">É possível formatá-lo para exibir somente a data.</span><span class="sxs-lookup"><span data-stu-id="b7b46-240">You can format them to display only the date.</span></span>  
  
#### <a name="to-format-a-date-field-as-the-default-format"></a><span data-ttu-id="b7b46-241">Para formatar um campo de data como o formato padrão</span><span class="sxs-lookup"><span data-stu-id="b7b46-241">To format a date field as the default format</span></span>  
  
1.  <span data-ttu-id="b7b46-242">Clique em **Design** para retornar à exibição de design.</span><span class="sxs-lookup"><span data-stu-id="b7b46-242">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="b7b46-243">Clique na célula que contém `[SalesDate]`.</span><span class="sxs-lookup"><span data-stu-id="b7b46-243">Click the cell that contains `[SalesDate]`.</span></span>  
  
3.  <span data-ttu-id="b7b46-244">Na faixa de opções, na guia **início** , no grupo **número** , na lista suspensa, selecione **Data**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-244">On the Ribbon, on the **Home** tab, in the **Number** group, from the drop-down list, select **Date**.</span></span>  
  
     <span data-ttu-id="b7b46-245">A célula exibe a data de exemplo **[1/31/2000]**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-245">The cell displays the example date **[1/31/2000]**.</span></span> <span data-ttu-id="b7b46-246">Se uma data de exemplo não estiver visível, clique em **Estilos de Espaço Reservado** no grupo **Números** e clique em **Valores de Exemplo**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-246">If you do not see an example date, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="b7b46-247">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="b7b46-247">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="b7b46-248">Os valores SalesDate são exibidos no formato de data padrão.</span><span class="sxs-lookup"><span data-stu-id="b7b46-248">The SalesDate values display in the default date format.</span></span>  
  
#### <a name="to-change-the-date-format-to-a-custom-format"></a><span data-ttu-id="b7b46-249">Para alterar o formato de data para um formato personalizado</span><span class="sxs-lookup"><span data-stu-id="b7b46-249">To change the date format to a custom format</span></span>  
  
1.  <span data-ttu-id="b7b46-250">Clique em **Design** para retornar à exibição de design.</span><span class="sxs-lookup"><span data-stu-id="b7b46-250">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="b7b46-251">Clique na célula que contém `[SalesDate]`.</span><span class="sxs-lookup"><span data-stu-id="b7b46-251">Click the cell that contains `[SalesDate]`.</span></span>  
  
3.  <span data-ttu-id="b7b46-252">Na guia **início** , no grupo **número** , clique no iniciador da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b7b46-252">On the **Home** tab, in the **Number** group, click the dialog box launcher.</span></span>  
  
     <span data-ttu-id="b7b46-253">O iniciador é a pequena seta no canto direito do grupo.</span><span class="sxs-lookup"><span data-stu-id="b7b46-253">The launcher is the small arrow in the right-hand corner of the group.</span></span> <span data-ttu-id="b7b46-254">A caixa de diálogo **Propriedades da Caixa de Texto** é aberta.</span><span class="sxs-lookup"><span data-stu-id="b7b46-254">The **Text Box Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="b7b46-255">No painel Categoria, verifique se a opção **Data** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="b7b46-255">In the Category pane, verify that **Date** is selected.</span></span>  
  
5.  <span data-ttu-id="b7b46-256">No painel **Tipo** , selecione **31 de janeiro de 2000**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-256">In the **Type** pane, select **January 31, 2000**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="b7b46-257">A célula exibe a data de exemplo **[31 de janeiro de 2000]**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-257">The cell displays the example date **[January 31, 2000]**.</span></span>  
  
7.  <span data-ttu-id="b7b46-258">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="b7b46-258">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="b7b46-259">O valor de SalesDate é exibido com o nome do mês, e não com o número dele.</span><span class="sxs-lookup"><span data-stu-id="b7b46-259">The SalesDate value displays with the name of the month instead of the number for the month.</span></span>  
  
##  <a name="4-change-column-widths"></a><a name="Width"></a><span data-ttu-id="b7b46-260">4. alterar larguras de coluna</span><span class="sxs-lookup"><span data-stu-id="b7b46-260">4. Change Column Widths</span></span>  
 <span data-ttu-id="b7b46-261">Por padrão, cada célula da tabela contém uma caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="b7b46-261">By default, each cell in a table contains a text box.</span></span> <span data-ttu-id="b7b46-262">Uma caixa de texto é expandida verticalmente para acomodar o texto quando a página é renderizada.</span><span class="sxs-lookup"><span data-stu-id="b7b46-262">A text box expands vertically to accommodate text when the page is rendered.</span></span> <span data-ttu-id="b7b46-263">No relatório renderizado, cada linha é expandida até a altura da caixa de texto renderizada mais alta da linha.</span><span class="sxs-lookup"><span data-stu-id="b7b46-263">In the rendered report, each row expands to the height of the tallest rendered text box in the row.</span></span> <span data-ttu-id="b7b46-264">A altura da linha na superfície de design não tem nenhum efeito na altura da linha no relatório renderizado.</span><span class="sxs-lookup"><span data-stu-id="b7b46-264">The height of the row on the design surface has no affect on the height of the row in the rendered report.</span></span>  
  
 <span data-ttu-id="b7b46-265">Para reduzir a quantidade de espaço vertical que cada linha ocupa, expanda a largura da coluna para acomodar em uma única linha o conteúdo esperado das caixas de texto da coluna.</span><span class="sxs-lookup"><span data-stu-id="b7b46-265">To reduce the amount of vertical space each row takes, expand the column width to accommodate the expected contents of the text boxes in the column on one line.</span></span>  
  
#### <a name="to-change-the-width-of-table-columns"></a><span data-ttu-id="b7b46-266">Para alterar a largura das colunas da tabela</span><span class="sxs-lookup"><span data-stu-id="b7b46-266">To change the width of table columns</span></span>  
  
1.  <span data-ttu-id="b7b46-267">Clique em **Design** para retornar à exibição de design.</span><span class="sxs-lookup"><span data-stu-id="b7b46-267">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="b7b46-268">Clique na tabela de forma que os identificadores de coluna e linha sejam exibidos acima e ao lado da tabela.</span><span class="sxs-lookup"><span data-stu-id="b7b46-268">Click the table so that column and row handles appear above and next to the table.</span></span>  
  
     <span data-ttu-id="b7b46-269">As barras em cinza ao longo da parte superior e ao lado da tabela são os identificadores de coluna e de linha.</span><span class="sxs-lookup"><span data-stu-id="b7b46-269">The gray bars along the top and side of the table are the column and row handles.</span></span>  
  
3.  <span data-ttu-id="b7b46-270">Aponte para a linha entre os identificadores de coluna para que o cursor seja alterado para uma seta dupla.</span><span class="sxs-lookup"><span data-stu-id="b7b46-270">Point to the line between column handles so that the cursor changes into a double arrow.</span></span> <span data-ttu-id="b7b46-271">Arraste as colunas de acordo com o tamanho desejado.</span><span class="sxs-lookup"><span data-stu-id="b7b46-271">Drag the columns to the size you want.</span></span> <span data-ttu-id="b7b46-272">Por exemplo, expanda a coluna Produto, de forma que o nome do produto seja exibido em uma linha.</span><span class="sxs-lookup"><span data-stu-id="b7b46-272">For example, expand the column for Product so that the product name displays on one line.</span></span>  
  
4.  <span data-ttu-id="b7b46-273">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="b7b46-273">Click **Run** to preview your report.</span></span>  
  
##  <a name="5-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="b7b46-274">5. adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="b7b46-274">5. Add a Report Title</span></span>  
 <span data-ttu-id="b7b46-275">Um título é exibido na parte superior do relatório.</span><span class="sxs-lookup"><span data-stu-id="b7b46-275">A report title appears at the top of the report.</span></span> <span data-ttu-id="b7b46-276">É possível colocar o título em um cabeçalho do relatório. No entanto, se ele não usar um cabeçalho, será possível colocar o título em uma caixa de texto na parte superior do corpo do relatório.</span><span class="sxs-lookup"><span data-stu-id="b7b46-276">You can place the report title in a report header or if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="b7b46-277">Neste tutorial, você usará a caixa de texto colocada automaticamente na parte superior do corpo do relatório.</span><span class="sxs-lookup"><span data-stu-id="b7b46-277">In this tutorial, you will use the text box that is automatically placed at the top of the report body.</span></span>  
  
 <span data-ttu-id="b7b46-278">O texto pode ser aprimorado ainda mais aplicando-se estilos, tamanhos e cores de fontes diferentes a frases e caracteres individuais do texto.</span><span class="sxs-lookup"><span data-stu-id="b7b46-278">The text can be further enhanced by applying different font styles, sizes, and colors to phrases and individual characters of the text.</span></span> <span data-ttu-id="b7b46-279">Para obter mais informações, consulte [Formatar o texto em uma caixa de texto &#40;Construtor de Relatórios e SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b7b46-279">For more information, see [Format Text in a Text Box &#40;Report Builder and SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="b7b46-280">Para adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="b7b46-280">To add a report title</span></span>  
  
1.  <span data-ttu-id="b7b46-281">Na superfície de design, clique em **Clique para adicionar título**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-281">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="b7b46-282">Digite **Vendas de Produtos**e clique fora da caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="b7b46-282">Type **Product Sales**, and then click outside the text box.</span></span>  
  
3.  <span data-ttu-id="b7b46-283">Clique com o botão direito do mouse na caixa de texto que contém **Vendas de Produtos** e clique em **Propriedades da Caixa de Texto**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-283">Right-click the text box that contains **Product Sales** and click **Text Box Properties**.</span></span>  
  
4.  <span data-ttu-id="b7b46-284">Na caixa de diálogo **Propriedades da Caixa de Texto** , clique em **Fonte**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-284">In the **Text Box Properties** dialog box, click **Font**.</span></span>  
  
5.  <span data-ttu-id="b7b46-285">Na lista **Tamanho** , selecione **18pt**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-285">In the **Size** list, select **18pt**.</span></span>  
  
6.  <span data-ttu-id="b7b46-286">Na lista **Cor** , selecione **Azul-centáurea**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-286">In the **Color** list, select **Cornflower Blue**.</span></span>  
  
7.  <span data-ttu-id="b7b46-287">Selecione **Negrito**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-287">Select **Bold**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="6-save-the-report"></a><a name="Save"></a><span data-ttu-id="b7b46-288">6. salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="b7b46-288">6. Save the Report</span></span>  
 <span data-ttu-id="b7b46-289">Salve o relatório em um servidor de relatório ou no computador.</span><span class="sxs-lookup"><span data-stu-id="b7b46-289">Save the report to a report server or your computer.</span></span> <span data-ttu-id="b7b46-290">Se você não salvar o relatório no servidor de relatório, vários recursos do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , como partes do relatório e sub-relatórios, não estarão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="b7b46-290">If you do not save the report to the report server, a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features such as report parts and subreports are not available.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="b7b46-291">Para salvar o relatório em um servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="b7b46-291">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="b7b46-292">No botão **Construtor de Relatórios** , clique em **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-292">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="b7b46-293">Clique em **Sites e Servidores Recentes**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-293">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="b7b46-294">Selecione ou digite o nome do servidor de relatório no qual você tem permissão para salvar relatórios.</span><span class="sxs-lookup"><span data-stu-id="b7b46-294">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="b7b46-295">A mensagem "Conectando-se a um servidor de relatório" é exibida.</span><span class="sxs-lookup"><span data-stu-id="b7b46-295">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="b7b46-296">Quando a conexão for concluída, você verá o conteúdo da pasta do relatório que o administrador do servidor de relatório especificou como o local padrão para relatórios.</span><span class="sxs-lookup"><span data-stu-id="b7b46-296">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="b7b46-297">Em **Nome**, substitua o nome padrão por **Vendas de Produtos**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-297">In **Name**, replace the default name with **Product Sales**.</span></span>  
  
5.  <span data-ttu-id="b7b46-298">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-298">Click **Save**.</span></span>  
  
 <span data-ttu-id="b7b46-299">O relatório será salvo no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="b7b46-299">The report is saved to the report server.</span></span> <span data-ttu-id="b7b46-300">O nome do servidor de relatório ao qual você está conectado é exibido na barra de status da parte inferior da janela.</span><span class="sxs-lookup"><span data-stu-id="b7b46-300">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="b7b46-301">Para salvar o relatório no computador</span><span class="sxs-lookup"><span data-stu-id="b7b46-301">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="b7b46-302">No botão **Construtor de Relatórios** , clique em **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-302">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="b7b46-303">Clique em **Área de Trabalho**, **Meus Documentos**ou **Meu computador**e procure a pasta na qual você quer salvar o relatório.</span><span class="sxs-lookup"><span data-stu-id="b7b46-303">Click **Desktop**, **My Documents**, or **My computer**, and browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="b7b46-304">Em **Nome**, substitua o nome padrão por **Vendas de Produtos**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-304">In **Name**, replace the default name with **Product Sales**.</span></span>  
  
4.  <span data-ttu-id="b7b46-305">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-305">Click **Save**.</span></span>  
  
##  <a name="7-export-the-report"></a><a name="Export"></a><span data-ttu-id="b7b46-306">7. exportar o relatório</span><span class="sxs-lookup"><span data-stu-id="b7b46-306">7. Export the Report</span></span>  
 <span data-ttu-id="b7b46-307">Os relatórios podem ser exportados para diversos formatos, como Microsoft Excel e CSV (valores separados por vírgulas).</span><span class="sxs-lookup"><span data-stu-id="b7b46-307">Reports can be exported to different formats such Microsoft Excel and comma separated value (CSV).</span></span> <span data-ttu-id="b7b46-308">Para obter mais informações, consulte [Exportando relatórios &#40;Construtor de relatórios e SSRS&#41;](report-builder/export-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b7b46-308">For more information, see [Exporting Reports &#40;Report Builder and SSRS&#41;](report-builder/export-reports-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="b7b46-309">Neste tutorial, você exportará o relatório para o Excel e definirá uma propriedade no relatório para atribuir um nome personalizado à guia Pasta de Trabalho.</span><span class="sxs-lookup"><span data-stu-id="b7b46-309">In this tutorial, you will export the report to Excel and set a property on the report to provide a custom name for the workbook tab.</span></span>  
  
#### <a name="to-specify-the-workbook-tab-name"></a><span data-ttu-id="b7b46-310">Para especificar o nome da guia Pasta de Trabalho</span><span class="sxs-lookup"><span data-stu-id="b7b46-310">To specify the workbook tab name</span></span>  
  
1.  <span data-ttu-id="b7b46-311">Clique em **Design** para retornar à exibição de design.</span><span class="sxs-lookup"><span data-stu-id="b7b46-311">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="b7b46-312">Clique em qualquer ponto fora do relatório.</span><span class="sxs-lookup"><span data-stu-id="b7b46-312">Click anywhere outside the report.</span></span>  
  
3.  <span data-ttu-id="b7b46-313">. No painel Propriedades, localize a propriedade InitialPageName e digite **Sales do produto Excel**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-313">.In the Properties pane, locate the InitialPageName property and type **Product Sales Excel**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b7b46-314">Se o painel Propriedades não estiver visível, clique na guia Exibir na faixa de e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-314">If the Properties pane is not visible, click the View tab on the ribbon, and then click **Properties**.</span></span>  
  
#### <a name="to-export-a-report-to-excel"></a><span data-ttu-id="b7b46-315">Para exportar um relatório para o Excel</span><span class="sxs-lookup"><span data-stu-id="b7b46-315">To export a report to Excel</span></span>  
  
1.  <span data-ttu-id="b7b46-316">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="b7b46-316">Click **Run** to preview the report.</span></span>  
  
2.  <span data-ttu-id="b7b46-317">. Na faixa de faixas, clique em **Exportar**e, em seguida, clique em **Excel**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-317">.On the ribbon, click **Export**, and then click **Excel**.</span></span>  
  
     <span data-ttu-id="b7b46-318">A caixa de diálogo **Salvar como** é aberta.</span><span class="sxs-lookup"><span data-stu-id="b7b46-318">The **Save As** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="b7b46-319">Navegue até a pasta **documentos** .</span><span class="sxs-lookup"><span data-stu-id="b7b46-319">Browse to the **Documents** folder.</span></span>  
  
4.  <span data-ttu-id="b7b46-320">Na caixa de texto **nome do arquivo** , digite **Sales do produto Excel**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-320">In the **File name** text box, type **Product Sales Excel**.</span></span>  
  
5.  <span data-ttu-id="b7b46-321">Verifique se o tipo de arquivo é **pasta de trabalho do Excel**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-321">Verify that the file type is **Excel Workbook**.</span></span>  
  
6.  <span data-ttu-id="b7b46-322">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-322">Click **Save**.</span></span>  
  
#### <a name="to-view-the-report-in-excel"></a><span data-ttu-id="b7b46-323">Para exibir o relatório no Excel</span><span class="sxs-lookup"><span data-stu-id="b7b46-323">To view the report in Excel</span></span>  
  
1.  <span data-ttu-id="b7b46-324">Abra a pasta **documentos** e clique duas vezes em **vendas de produtos Excel.xlsx**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-324">Open the **Documents** folder and double click **Product Sales Excel.xlsx**.</span></span>  
  
2.  <span data-ttu-id="b7b46-325">Verifique se o nome da guia de pasta de trabalho é **Vendas de Produtos em Excel**.</span><span class="sxs-lookup"><span data-stu-id="b7b46-325">Verify that the name of the workbook tab is **Product Sales Excel**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b7b46-326">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="b7b46-326">Next Steps</span></span>  
 <span data-ttu-id="b7b46-327">Isso conclui o passo a passo sobre como criar um relatório de tabela básico.</span><span class="sxs-lookup"><span data-stu-id="b7b46-327">This concludes the walkthrough for how to create a basic table report.</span></span> <span data-ttu-id="b7b46-328">Para obter mais informações sobre tabelas, consulte [Tabelas, matrizes e listas &#40;Construtor de Relatórios e SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b7b46-328">For more information about tables, see [Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7b46-329">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b7b46-329">See Also</span></span>  
 <span data-ttu-id="b7b46-330">[TUTORIAIS &#40;Construtor de Relatórios&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="b7b46-330">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="b7b46-331">Construtor de Relatórios no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="b7b46-331">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
