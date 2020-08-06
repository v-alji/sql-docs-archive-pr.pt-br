---
title: 'Tutorial: Adicionar um minigráfico ao relatório (Construtor de Relatórios) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 18c90a36-48bf-4805-a960-2d1e8f00c2dc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fb1bf83810b6c743b977e399864ce2edd514f572
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683355"
---
# <a name="tutorial-add-a-sparkline-to-your-report-report-builder"></a><span data-ttu-id="3206a-102">Tutorial: Adicionar um minigráfico ao relatório (Construtor de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="3206a-102">Tutorial: Add a Sparkline to Your Report (Report Builder)</span></span>
  <span data-ttu-id="3206a-103">Neste tutorial, você cria um relatório de tabela básico com base em dados de vendas de exemplo e, em seguida, adiciona um minigráfico a uma célula da tabela.</span><span class="sxs-lookup"><span data-stu-id="3206a-103">In this tutorial, you create a basic table report based on sample sales data, and then add a sparkline chart to a cell in the table.</span></span>  
  
 <span data-ttu-id="3206a-104">Uma versão aprimorada do relatório criado por você neste tutorial está disponível como um relatório de exemplo do Construtor de Relatórios da [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3206a-104">An enhanced version of the report you create in this tutorial is available as a sample [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Report Builder report.</span></span> <span data-ttu-id="3206a-105">Para obter mais informações sobre como baixar este relatório de exemplo e outros, consulte [Construtor de relatórios relatórios de exemplo](https://go.microsoft.com/fwlink/?LinkId=184851).</span><span class="sxs-lookup"><span data-stu-id="3206a-105">For more information about downloading this sample report and others, see [Report Builder sample reports](https://go.microsoft.com/fwlink/?LinkId=184851).</span></span> <span data-ttu-id="3206a-106">A ilustração a seguir mostra o relatório de exemplo semelhante ao que você criará.</span><span class="sxs-lookup"><span data-stu-id="3206a-106">The following illustration shows the sample report similar to the one that you will create.</span></span>  
  
 <span data-ttu-id="3206a-107">![rs_SparklineMatrixTutorial](../../2014/tutorials/media/rs-sparklinematrixtutorial.gif "rs_SparklineMatrixTutorial")</span><span class="sxs-lookup"><span data-stu-id="3206a-107">![rs_SparklineMatrixTutorial](../../2014/tutorials/media/rs-sparklinematrixtutorial.gif "rs_SparklineMatrixTutorial")</span></span>  
  
 <span data-ttu-id="3206a-108">O vídeo [como: criar um minigráfico em uma tabela (Construtor de relatórios vídeo)](https://technet.microsoft.com/bi/ff871942.aspx) ilustra como criar um relatório semelhante com minigráficos.</span><span class="sxs-lookup"><span data-stu-id="3206a-108">The video [How to: Create a Sparkline in a Table (Report Builder Video)](https://technet.microsoft.com/bi/ff871942.aspx) illustrates how to create a similar report with sparklines.</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="3206a-109">O que você aprenderá</span><span class="sxs-lookup"><span data-stu-id="3206a-109">What You Will Learn</span></span>  
 <span data-ttu-id="3206a-110">Neste tutorial, você aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="3206a-110">In this tutorial, you will learn how to do the following:</span></span>  
  
 1. [<span data-ttu-id="3206a-111">Criar um relatório com uma tabela</span><span class="sxs-lookup"><span data-stu-id="3206a-111">Create a Report with a Table</span></span>](#CreateTable)  
  
 2. [<span data-ttu-id="3206a-112">Criar uma consulta no Assistente de Tabela ou Matriz</span><span class="sxs-lookup"><span data-stu-id="3206a-112">Create a Query in the Table or Matrix Wizard</span></span>](#Query)  
  
 3. [<span data-ttu-id="3206a-113">Adicionar um minigráfico à tabela</span><span class="sxs-lookup"><span data-stu-id="3206a-113">Add a Sparkline to the Table</span></span>](#Sparkline)  
  
 4. [<span data-ttu-id="3206a-114">Alinhar os minigráficos vertical e horizontalmente</span><span class="sxs-lookup"><span data-stu-id="3206a-114">Align the Sparklines Vertically and Horizontally</span></span>](#AlignSparklines)  
  
### <a name="other-optional-steps"></a><span data-ttu-id="3206a-115">Outras etapas opcionais</span><span class="sxs-lookup"><span data-stu-id="3206a-115">Other Optional Steps</span></span>  
 5. [<span data-ttu-id="3206a-116">Formatar dados como moeda</span><span class="sxs-lookup"><span data-stu-id="3206a-116">Format Data as Currency</span></span>](#FormatCurrency)  
  
 6. [<span data-ttu-id="3206a-117">Formatar dados como datas</span><span class="sxs-lookup"><span data-stu-id="3206a-117">Format Data as Dates</span></span>](#FormatDates)  
  
 7. [<span data-ttu-id="3206a-118">Alterar a Largura das Colunas</span><span class="sxs-lookup"><span data-stu-id="3206a-118">Change Column Widths</span></span>](#Width)  
  
 8. [<span data-ttu-id="3206a-119">Adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="3206a-119">Add a Report Title</span></span>](#Title)  
  
 9. [<span data-ttu-id="3206a-120">Salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="3206a-120">Save the Report</span></span>](#Save)  
  
 <span data-ttu-id="3206a-121">Tempo estimado para concluir este tutorial: 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="3206a-121">Estimated time to complete this tutorial: 30 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3206a-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3206a-122">Requirements</span></span>  
 <span data-ttu-id="3206a-123">Para obter mais informações sobre os requisitos, consulte [Pré-requisitos para tutoriais &#40;Construtor de Relatórios&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="3206a-123">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-report-with-a-table"></a><a name="CreateTable"></a><span data-ttu-id="3206a-124">1. criar um relatório com uma tabela</span><span class="sxs-lookup"><span data-stu-id="3206a-124">1. Create a Report with a Table</span></span>  
  
#### <a name="to-create-a-report"></a><span data-ttu-id="3206a-125">Para criar um relatório</span><span class="sxs-lookup"><span data-stu-id="3206a-125">To create a report</span></span>  
  
1.  <span data-ttu-id="3206a-126">Clique em **Iniciar**, aponte para **Programas**, para **Construtor de Relatórios do Microsoft SQL Server 2012**e clique em **Construtor de Relatórios**.</span><span class="sxs-lookup"><span data-stu-id="3206a-126">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="3206a-127">A caixa de diálogo **Guia de Introdução** é aberta.</span><span class="sxs-lookup"><span data-stu-id="3206a-127">The **Getting Started** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3206a-128">Se a caixa de diálogo **introdução** não for exibida, no botão **Construtor de relatórios** , clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="3206a-128">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="3206a-129">No painel esquerdo, verifique se **Novo Relatório** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="3206a-129">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="3206a-130">No painel direito, clique em **Assistente de Tabela ou Matriz**.</span><span class="sxs-lookup"><span data-stu-id="3206a-130">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="3206a-131">Na página **Escolher um conjunto de dados** , selecione **Criar um conjunto de dados**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="3206a-131">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="3206a-132">A página **Escolher uma conexão com uma fonte de dados** é aberta.</span><span class="sxs-lookup"><span data-stu-id="3206a-132">The **Choose a connection to a data source** page opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3206a-133">Este tutorial não precisa de dados específicos; ele só precisa de uma conexão com um banco de dados [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3206a-133">This tutorial does not need specific data; it just needs a connection to a [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] database.</span></span> <span data-ttu-id="3206a-134">Se você já tiver uma conexão de fonte de dados listada em **Conexões de Fonte de Dados**, será possível selecioná-la e ir para a etapa 10.</span><span class="sxs-lookup"><span data-stu-id="3206a-134">If you already have a data source connection listed under **Data Source Connections**, you can select it and go to step 10.</span></span> <span data-ttu-id="3206a-135">Para obter mais informações, consulte [Formas alternativas de obter uma conexão de dados &#40;Construtor de Relatórios&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="3206a-135">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
5.  <span data-ttu-id="3206a-136">Clique em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="3206a-136">Click **New**.</span></span> <span data-ttu-id="3206a-137">A caixa de diálogo **Propriedades da Fonte de Dados** é aberta.</span><span class="sxs-lookup"><span data-stu-id="3206a-137">The **Data Source Properties** dialog box opens.</span></span>  
  
6.  <span data-ttu-id="3206a-138">Em **Nome**, digite **Vendas de Produtos**, um nome para a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="3206a-138">In **Name**, type **Product Sales**, a name for the data source.</span></span>  
  
7.  <span data-ttu-id="3206a-139">Em **Selecionar um tipo de conexão**, verifique se a opção **Microsoft SQL Server** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="3206a-139">In **Select a connection type**, verify that **Microsoft SQL Server** is selected.</span></span>  
  
8.  <span data-ttu-id="3206a-140">Em **Cadeia de conexão**, digite o seguinte texto:</span><span class="sxs-lookup"><span data-stu-id="3206a-140">In **Connection string**, type the following text:</span></span>  
  
     <span data-ttu-id="3206a-141">**Fonte de dados =\<servername>**</span><span class="sxs-lookup"><span data-stu-id="3206a-141">**Data Source=\<servername>**</span></span>  
  
     <span data-ttu-id="3206a-142">A expressão \<servername>, por exemplo, Report001, especifica um computador no qual há uma instância do Mecanismo de Banco de Dados do SQL Server instalada.</span><span class="sxs-lookup"><span data-stu-id="3206a-142">The expression \<servername>, for example Report001, specifies a computer on which an instance of the SQL Server Database Engine is installed.</span></span> <span data-ttu-id="3206a-143">Como os dados do relatório não são extraídos de um banco de dados do SQL Server, você não precisa incluir o nome de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3206a-143">Because the report data is not extracted from a SQL Server database, you need not include the name of a database.</span></span> <span data-ttu-id="3206a-144">O banco de dados padrão no servidor especificado é usado para analisar a consulta.</span><span class="sxs-lookup"><span data-stu-id="3206a-144">The default database on the specified server is used to parse the query.</span></span>  
  
9. <span data-ttu-id="3206a-145">Clique em **Credenciais**.</span><span class="sxs-lookup"><span data-stu-id="3206a-145">Click **Credentials**.</span></span> <span data-ttu-id="3206a-146">Insira as credenciais necessárias para acessar a fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="3206a-146">Enter the credentials that you need to access the external data source.</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="3206a-147">Você voltará à página **Escolher uma conexão com uma fonte de dados** .</span><span class="sxs-lookup"><span data-stu-id="3206a-147">You are back on the **Choose a connection to a data source** page.</span></span>  
  
11. <span data-ttu-id="3206a-148">Para verificar se é possível se conectar à fonte de dados, clique em **Testar Conexão**.</span><span class="sxs-lookup"><span data-stu-id="3206a-148">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
     <span data-ttu-id="3206a-149">A mensagem "Conexão criada com êxito" será exibida.</span><span class="sxs-lookup"><span data-stu-id="3206a-149">The message "Connection created successfully" appears.</span></span>  
  
12. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
13. <span data-ttu-id="3206a-150">Clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="3206a-150">Click **Next**.</span></span>  
  
##  <a name="2-create-a-query-in-the-table-wizard"></a><a name="Query"></a><span data-ttu-id="3206a-151">2. criar uma consulta no assistente de tabela</span><span class="sxs-lookup"><span data-stu-id="3206a-151">2. Create a Query in the Table Wizard</span></span>  
 <span data-ttu-id="3206a-152">Em um relatório, é possível usar um conjunto de dados compartilhado que tenha uma consulta predefinida. Se preferir, crie um conjunto de dados inserido para ser usado somente em seu relatório.</span><span class="sxs-lookup"><span data-stu-id="3206a-152">In a report, you can use a shared dataset that has a predefined query, or you can create an embedded dataset for use only in your report.</span></span> <span data-ttu-id="3206a-153">Neste tutorial, você criará um conjunto de dados inserido.</span><span class="sxs-lookup"><span data-stu-id="3206a-153">In this tutorial, you will create an embedded dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3206a-154">Neste tutorial, a consulta contém os valores de dados para que não precise de uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="3206a-154">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="3206a-155">Isso torna a consulta bastante longa.</span><span class="sxs-lookup"><span data-stu-id="3206a-155">This makes the query quite long.</span></span> <span data-ttu-id="3206a-156">Em um ambiente empresarial, uma consulta não conteria os dados.</span><span class="sxs-lookup"><span data-stu-id="3206a-156">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="3206a-157">Isso é apenas para fins de aprendizado.</span><span class="sxs-lookup"><span data-stu-id="3206a-157">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-query"></a><span data-ttu-id="3206a-158">Para criar uma consulta</span><span class="sxs-lookup"><span data-stu-id="3206a-158">To create a query</span></span>  
  
1.  <span data-ttu-id="3206a-159">Na página **Criar uma consulta** , o designer de consultas relacionais é aberto.</span><span class="sxs-lookup"><span data-stu-id="3206a-159">On the **Design a query** page, the relational query designer is open.</span></span> <span data-ttu-id="3206a-160">Para este tutorial, você usará o designer de consulta baseado em texto.</span><span class="sxs-lookup"><span data-stu-id="3206a-160">For this tutorial, you will use the text-based query designer.</span></span>  
  
2.  <span data-ttu-id="3206a-161">Clique em **Editar como texto**.</span><span class="sxs-lookup"><span data-stu-id="3206a-161">Click **Edit As Text**.</span></span> <span data-ttu-id="3206a-162">O designer de consulta baseado em texto exibe um painel de consulta e um painel de resultados.</span><span class="sxs-lookup"><span data-stu-id="3206a-162">The text-based query designer displays a query pane and a results pane.</span></span>  
  
3.  <span data-ttu-id="3206a-163">Cole a consulta [!INCLUDE[tsql](../includes/tsql-md.md)] a seguir na caixa **Consulta** .</span><span class="sxs-lookup"><span data-stu-id="3206a-163">Paste the following [!INCLUDE[tsql](../includes/tsql-md.md)] query into the **Query** box.</span></span>  
  
    ```  
    SELECT CAST('2010-01-04' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity  
    UNION SELECT CAST('2010-01-05' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Carrying Case' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2010-01-10' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Carrying Case' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2010-01-04' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Budget Movie-Maker' as Product, CAST(1056.00 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2010-01-05' AS date) as SalesDate,  'Accessories' as Subcategory,  
       'Slim Digital' as Product, CAST(1380.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2010-01-05' AS date) as SalesDate,'Accessories' as Subcategory,    
       'Budget Movie-Maker' as Product, CAST(780.00 AS money) AS Sales, 26 as Quantity  
    UNION SELECT CAST('2010-01-07' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(3798.00 AS money) AS Sales, 9 as Quantity  
    UNION SELECT CAST('2010-01-08' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(10400.00 AS money) AS Sales, 13 as Quantity  
    UNION SELECT CAST('2010-01-09' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(3000.00 AS money) AS Sales, 60 as Quantity  
    UNION SELECT CAST('2010-01-10' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(7234.50 AS money) AS Sales, 39 as Quantity  
    UNION SELECT CAST('2010-01-06' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Carrying Case' as Product, CAST(10836.00 AS money) AS Sales, 84 as Quantity  
    UNION SELECT CAST('2010-01-07' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Slim Digital' as Product, CAST(2550.00 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2010-01-04' AS date) as SalesDate, 'Digital' as Subcategory,   
       'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2010-01-08' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'Slim Digital' as Product, CAST(18530.00 AS money) AS Sales, 34 as Quantity  
    UNION SELECT CAST('2010-01-06' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'Slim Digital' as Product, CAST(26576.00 AS money) AS Sales, 88 as Quantity  
    ```  
  
4.  <span data-ttu-id="3206a-164">Na barra de ferramentas do designer de consultas, clique em Executar (**!**).</span><span class="sxs-lookup"><span data-stu-id="3206a-164">On the query designer toolbar, click Run  (**!**).</span></span>  
  
     <span data-ttu-id="3206a-165">A consulta é executada e exibe o conjunto de resultados dos campos **SalesDate**, **Subcategory**, **Product**, **Sales**e **Quantity**.</span><span class="sxs-lookup"><span data-stu-id="3206a-165">The query runs and displays the result set for the fields **SalesDate**, **Subcategory**, **Product**, **Sales**, and **Quantity**.</span></span>  
  
5.  <span data-ttu-id="3206a-166">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="3206a-166">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="3206a-167">Na página **Organizar campos** , arraste **Sales** até **Valores**.</span><span class="sxs-lookup"><span data-stu-id="3206a-167">On the **Arrange fields** page, drag **Sales** to **Values**.</span></span>  
  
     <span data-ttu-id="3206a-168">**Sales** é agregado pela função Sum.</span><span class="sxs-lookup"><span data-stu-id="3206a-168">**Sales** is aggregated by the Sum function.</span></span> <span data-ttu-id="3206a-169">O valor é [Sum(Sales)].</span><span class="sxs-lookup"><span data-stu-id="3206a-169">The value is [Sum(Sales)].</span></span>  
  
7.  <span data-ttu-id="3206a-170">Arraste **Product** até **Grupos de linhas**.</span><span class="sxs-lookup"><span data-stu-id="3206a-170">Drag **Product** to **Row groups**.</span></span>  
  
8.  <span data-ttu-id="3206a-171">Arraste **SalesDate** até **Grupos de colunas**.</span><span class="sxs-lookup"><span data-stu-id="3206a-171">Drag **SalesDate** to **Column groups**.</span></span>  
  
9. <span data-ttu-id="3206a-172">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="3206a-172">Click **Next**.</span></span>  
  
10. <span data-ttu-id="3206a-173">Na página **escolher o layout** , em opções, verifique se a **opção** **Mostrar Subtotais e totais gerais** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="3206a-173">On the **Choose the layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
     <span data-ttu-id="3206a-174">O painel Visualizar do assistente exibe uma tabela com três linhas.</span><span class="sxs-lookup"><span data-stu-id="3206a-174">The wizard Preview pane displays a table with three rows.</span></span> <span data-ttu-id="3206a-175">Ao executar o relatório, cada linha será exibida da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="3206a-175">When you run the report, each row will display in the following way:</span></span>  
  
    1.  <span data-ttu-id="3206a-176">A primeira linha aparecerá uma vez para a tabela a fim de mostrar os títulos da coluna.</span><span class="sxs-lookup"><span data-stu-id="3206a-176">The first row will appear once for the table to show column headings.</span></span>  
  
    2.  <span data-ttu-id="3206a-177">A segunda linha será repetida uma vez para cada produto e exibirá o nome do produto, o total por dia e o total da linha.</span><span class="sxs-lookup"><span data-stu-id="3206a-177">The second row will repeat once for each product and display the product name, total per day, and line total.</span></span>  
  
    3.  <span data-ttu-id="3206a-178">A terceira linha aparecerá uma vez para a tabela a fim de exibir totais gerais.</span><span class="sxs-lookup"><span data-stu-id="3206a-178">The third row will appear once for the table to display the grand totals.</span></span>  
  
11. <span data-ttu-id="3206a-179">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="3206a-179">Click **Next**.</span></span>  
  
12. <span data-ttu-id="3206a-180">Na página **Escolha um estilo** , no painel **Estilos** , selecione **Ardósia**.</span><span class="sxs-lookup"><span data-stu-id="3206a-180">On the **Choose a Style** page, in the **Styles** pane, select **Slate**.</span></span>  
  
     <span data-ttu-id="3206a-181">O painel Visualizar exibirá um exemplo da tabela com esse estilo.</span><span class="sxs-lookup"><span data-stu-id="3206a-181">The Preview pane displays a sample of the table with that style.</span></span>  
  
13. <span data-ttu-id="3206a-182">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="3206a-182">Click **Finish**.</span></span>  
  
14. <span data-ttu-id="3206a-183">A tabela é adicionada à superfície de design.</span><span class="sxs-lookup"><span data-stu-id="3206a-183">The table is added to the design surface.</span></span> <span data-ttu-id="3206a-184">A tabela tem três colunas e três linhas.</span><span class="sxs-lookup"><span data-stu-id="3206a-184">The table has three columns and three rows.</span></span>  
  
     <span data-ttu-id="3206a-185">Pesquisar o painel Agrupamento.</span><span class="sxs-lookup"><span data-stu-id="3206a-185">Look in the Grouping pane.</span></span> <span data-ttu-id="3206a-186">Se você não conseguir ver o painel Agrupamento, no menu **Exibir** , clique em **Agrupamento**.</span><span class="sxs-lookup"><span data-stu-id="3206a-186">If you can't see the Grouping pane, on the **View** menu, click **Grouping**.</span></span> <span data-ttu-id="3206a-187">O painel Grupos de Linhas mostra um grupo de linhas: **Product**.</span><span class="sxs-lookup"><span data-stu-id="3206a-187">The Row Groups pane shows one row group: **Product**.</span></span> <span data-ttu-id="3206a-188">O painel Grupos de Colunas mostra um grupo de colunas: **SalesDate**.</span><span class="sxs-lookup"><span data-stu-id="3206a-188">The Column Groups pane shows one column group: **SalesDate**.</span></span> <span data-ttu-id="3206a-189">Os dados detalhados são todos os dados recuperados pela consulta do conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="3206a-189">Detail data is all the data that is retrieved by the dataset query.</span></span>  
  
15. <span data-ttu-id="3206a-190">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="3206a-190">Click **Run** to preview the report.</span></span>  
  
##  <a name="3-add-a-sparkline"></a><a name="Sparkline"></a><span data-ttu-id="3206a-191">3. adicionar um minigráfico</span><span class="sxs-lookup"><span data-stu-id="3206a-191">3. Add a Sparkline</span></span>  
  
#### <a name="to-add-a-sparkline-chart-to-a-table"></a><span data-ttu-id="3206a-192">Para adicionar um minigráfico a uma tabela</span><span class="sxs-lookup"><span data-stu-id="3206a-192">To add a sparkline chart to a table</span></span>  
  
1.  <span data-ttu-id="3206a-193">Clique em **Design** para retornar à exibição de design.</span><span class="sxs-lookup"><span data-stu-id="3206a-193">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="3206a-194">Selecione a coluna Total na tabela.</span><span class="sxs-lookup"><span data-stu-id="3206a-194">Select the Total column in your table.</span></span>  
  
3.  <span data-ttu-id="3206a-195">Clique com o botão direito do mouse, aponte para **Inserir Coluna**e clique em **Esquerda**.</span><span class="sxs-lookup"><span data-stu-id="3206a-195">Right-click, point to **Insert Column**, and then click **Left**.</span></span>  
  
4.  <span data-ttu-id="3206a-196">Na nova coluna, clique com o botão direito do mouse na linha [Product], aponte para a guia **Inserir** faixa de bits e clique em **minigráfico**.</span><span class="sxs-lookup"><span data-stu-id="3206a-196">In the new column, right-click in the [Product] row, point to the **Insert** ribbon tab, and then click **Sparkline**.</span></span>  
  
5.  <span data-ttu-id="3206a-197">Verifique se o primeiro minigráfico na linha da **coluna** está selecionado e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3206a-197">Make sure the first sparkline in the **Column** row is selected and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="3206a-198">Clique no minigráfico para mostrar o painel Dados do Gráfico.</span><span class="sxs-lookup"><span data-stu-id="3206a-198">Click the sparkline to show the Chart Data pane.</span></span>  
  
7.  <span data-ttu-id="3206a-199">Clique no sinal de mais (+) na caixa valores e clique em **vendas**.</span><span class="sxs-lookup"><span data-stu-id="3206a-199">Click the plus (+) sign in the Values box, and then click **Sales**.</span></span>  
  
     <span data-ttu-id="3206a-200">Os valores no campo **Sales** agora são os valores do minigráfico.</span><span class="sxs-lookup"><span data-stu-id="3206a-200">The values in the **Sales** field are now the values for the sparkline.</span></span>  
  
8.  <span data-ttu-id="3206a-201">Clique no sinal de mais (+) na caixa grupos de categorias e, em seguida, clique em **SalesDate**.</span><span class="sxs-lookup"><span data-stu-id="3206a-201">Click the plus (+) sign in the Category Groups box, and then click **SalesDate**.</span></span>  
  
9. <span data-ttu-id="3206a-202">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="3206a-202">Click **Run** to preview your report.</span></span>  
  
     <span data-ttu-id="3206a-203">Observe que há minigráficos em cada linha da tabela, mas eles não estão corretos.</span><span class="sxs-lookup"><span data-stu-id="3206a-203">Note that there are sparkline charts in each row of the table, but they're not correct.</span></span> <span data-ttu-id="3206a-204">As barras nos gráficos não se alinham.</span><span class="sxs-lookup"><span data-stu-id="3206a-204">The bars in the charts don't line up with each other.</span></span> <span data-ttu-id="3206a-205">Como só há quatro barras na segunda linha de dados, as barras são mais largas do que as barras na primeira linha, que tem seis.</span><span class="sxs-lookup"><span data-stu-id="3206a-205">There are only four bars in the second row of data, so the bars are wider than the bars in the first row, which has six.</span></span> <span data-ttu-id="3206a-206">Não é possível comparar valores para cada produto por dia.</span><span class="sxs-lookup"><span data-stu-id="3206a-206">You can't compare values for each product per day.</span></span> <span data-ttu-id="3206a-207">Elas precisam se alinhar.</span><span class="sxs-lookup"><span data-stu-id="3206a-207">They need to line up with each other.</span></span>  
  
     <span data-ttu-id="3206a-208">Também observe que, para cada linha, a maior barra na linha é da altura da linha.</span><span class="sxs-lookup"><span data-stu-id="3206a-208">Also note that for each row, the tallest bar for that row is the height of the row.</span></span> <span data-ttu-id="3206a-209">Isso também é enganador, porque os maiores valores para cada linha não são iguais: o maior valor para o criador de filmes de orçamento é $10400, mas o maior valor para o slim digital é $26576-mais do que duas vezes maior.</span><span class="sxs-lookup"><span data-stu-id="3206a-209">This is misleading, too, because the largest values for each row are not equal: the largest value for Budget Movie-Maker is $10,400, but the largest value for Slim Digital is $26,576-more than twice as large.</span></span> <span data-ttu-id="3206a-210">Além disso, as barras maiores nessas duas linhas têm aproximadamente a mesma altura.</span><span class="sxs-lookup"><span data-stu-id="3206a-210">And yet the largest bars in those two rows are about the same height.</span></span> <span data-ttu-id="3206a-211">Também é preciso fazer isso para dimensioná-las com os outros minigráficos.</span><span class="sxs-lookup"><span data-stu-id="3206a-211">That also needs to be made to scale with the other sparklines.</span></span>  
  
     <span data-ttu-id="3206a-212">![rs_SprklineMtrxUnaligndBars](../../2014/tutorials/media/rs-sprklinemtrxunaligndbars.gif "rs_SprklineMtrxUnaligndBars")</span><span class="sxs-lookup"><span data-stu-id="3206a-212">![rs_SprklineMtrxUnaligndBars](../../2014/tutorials/media/rs-sprklinemtrxunaligndbars.gif "rs_SprklineMtrxUnaligndBars")</span></span>  
  
##  <a name="4-align-the-sparklines-vertically-and-horizontally"></a><a name="AlignSparklines"></a><span data-ttu-id="3206a-213">4. alinhar os minigráficos vertical e horizontalmente</span><span class="sxs-lookup"><span data-stu-id="3206a-213">4. Align the Sparklines Vertically and Horizontally</span></span>  
 <span data-ttu-id="3206a-214">Os Minigráficos são difíceis de ler quando nem todos usam as mesmas medições.</span><span class="sxs-lookup"><span data-stu-id="3206a-214">The sparklines are hard to read when they don't all use the same measurements.</span></span> <span data-ttu-id="3206a-215">Os eixos horizontal e vertical de cada um deles precisa corresponder ao resto.</span><span class="sxs-lookup"><span data-stu-id="3206a-215">Both the horizontal and vertical axes for each need to match the rest.</span></span>  
  
#### <a name="to-set-alignment-for-the-sparklines-in-the-table"></a><span data-ttu-id="3206a-216">Para definir o alinhamento dos minigráficos na tabela</span><span class="sxs-lookup"><span data-stu-id="3206a-216">To set alignment for the sparklines in the table</span></span>  
  
1.  <span data-ttu-id="3206a-217">Clique em **Design** para retornar à exibição de design.</span><span class="sxs-lookup"><span data-stu-id="3206a-217">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="3206a-218">Clique com o botão direito do mouse no minigráfico e clique em **Propriedades do Eixo Vertical**.</span><span class="sxs-lookup"><span data-stu-id="3206a-218">Right-click the sparkline and click **Vertical Axis Properties**.</span></span>  
  
3.  <span data-ttu-id="3206a-219">Marque a caixa de seleção **Alinhar eixos em** .</span><span class="sxs-lookup"><span data-stu-id="3206a-219">Check the **Align axes in** check box.</span></span>  
  
     <span data-ttu-id="3206a-220">Tablix1 está aparecendo na lista.</span><span class="sxs-lookup"><span data-stu-id="3206a-220">Tablix1 is showing in the list.</span></span> <span data-ttu-id="3206a-221">Essa é a única opção.</span><span class="sxs-lookup"><span data-stu-id="3206a-221">That is the only option.</span></span> <span data-ttu-id="3206a-222">Isso define a altura das barras em cada minigráfico referente às outras.</span><span class="sxs-lookup"><span data-stu-id="3206a-222">This sets the height of the bars in each sparkline relative to the others.</span></span>  
  
4.  <span data-ttu-id="3206a-223">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3206a-223">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="3206a-224">Clique com o botão direito do mouse no minigráfico e clique em **Propriedades do Eixo Horizontal**.</span><span class="sxs-lookup"><span data-stu-id="3206a-224">Right-click the sparkline and click **Horizontal Axis Properties**.</span></span>  
  
6.  <span data-ttu-id="3206a-225">Marque a caixa de seleção **Alinhar eixos em** .</span><span class="sxs-lookup"><span data-stu-id="3206a-225">Check the **Align axes in** check box.</span></span>  
  
     <span data-ttu-id="3206a-226">Tablix1 está aparecendo na lista.</span><span class="sxs-lookup"><span data-stu-id="3206a-226">Tablix1 is showing in the list.</span></span> <span data-ttu-id="3206a-227">Essa é a única opção.</span><span class="sxs-lookup"><span data-stu-id="3206a-227">That is the only option.</span></span> <span data-ttu-id="3206a-228">Isso define a largura das barras em cada minigráfico referente às outras.</span><span class="sxs-lookup"><span data-stu-id="3206a-228">This sets the width of the bars in each sparkline relative to the others.</span></span> <span data-ttu-id="3206a-229">Se alguns minigráficos tiverem menos barras em sequência do que outros, esses minigráficos terão espaços em branco para os dados não encontrados.</span><span class="sxs-lookup"><span data-stu-id="3206a-229">If some sparklines have fewer bars than others, then those sparklines will have blank spaces for the missing data.</span></span>  
  
7.  <span data-ttu-id="3206a-230">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3206a-230">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="3206a-231">Clique em **Executar** para visualizar o relatório novamente.</span><span class="sxs-lookup"><span data-stu-id="3206a-231">Click **Run** to preview your report again.</span></span>  
  
 <span data-ttu-id="3206a-232">Observe que todas as barras agora estão alinhadas com as barras nas outras linhas.</span><span class="sxs-lookup"><span data-stu-id="3206a-232">Note that all the bars are now aligned with the bars in the other rows.</span></span>  
  
##  <a name="5-optional-format-data-as-currency"></a><a name="FormatCurrency"></a><span data-ttu-id="3206a-233">5. (opcional) formatar dados como moeda</span><span class="sxs-lookup"><span data-stu-id="3206a-233">5. (Optional) Format Data as Currency</span></span>  
 <span data-ttu-id="3206a-234">Por padrão, os dados de resumo do campo **vendas** exibem um número geral.</span><span class="sxs-lookup"><span data-stu-id="3206a-234">By default, the summary data for the **Sales** field displays a general number.</span></span> <span data-ttu-id="3206a-235">Formate-o para exibir o número como moeda.</span><span class="sxs-lookup"><span data-stu-id="3206a-235">Format it to display the number as currency.</span></span> <span data-ttu-id="3206a-236">Ative/desative **Estilos de Espaço Reservado** para exibir caixas de texto formatadas e texto de espaço reservado como valores de exemplo.</span><span class="sxs-lookup"><span data-stu-id="3206a-236">Toggle **Placeholder Styles** to display formatted text boxes and placeholder text as sample values.</span></span>  
  
#### <a name="to-format-a-currency-field"></a><span data-ttu-id="3206a-237">Para formatar um campo de conversor de moedas</span><span class="sxs-lookup"><span data-stu-id="3206a-237">To format a currency field</span></span>  
  
1.  <span data-ttu-id="3206a-238">Clique em **Design** a fim de alternar para a exibição de design.</span><span class="sxs-lookup"><span data-stu-id="3206a-238">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="3206a-239">Clique na célula na segunda linha (sob a linha títulos de coluna) na coluna **SalesDate** e arraste para selecionar todas as células que contêm `[Sum(Sales)]` .</span><span class="sxs-lookup"><span data-stu-id="3206a-239">Click the cell in the second row (under the column headings row) in the **SalesDate** column and drag to select all cells that contain `[Sum(Sales)]`.</span></span>  
  
3.  <span data-ttu-id="3206a-240">Na guia **Início** , no grupo **Número** , clique no botão **Moeda** .</span><span class="sxs-lookup"><span data-stu-id="3206a-240">On the **Home** tab, in the **Number** group, click the **Currency** button.</span></span> <span data-ttu-id="3206a-241">As células são alteradas para mostrar a moeda formatada.</span><span class="sxs-lookup"><span data-stu-id="3206a-241">The cells change to show the formatted currency.</span></span>  
  
     <span data-ttu-id="3206a-242">Se a configuração regional for Inglês (Estados Unidos), o texto de exemplo padrão será [**$12,345.00**].</span><span class="sxs-lookup"><span data-stu-id="3206a-242">If your regional setting is English (United States), the default sample text is [**$12,345.00**].</span></span> <span data-ttu-id="3206a-243">Se você não vir um valor de moeda de exemplo, clique em **estilos de espaço reservado** no grupo **números** e clique em **valores de exemplo**.</span><span class="sxs-lookup"><span data-stu-id="3206a-243">If you do not see an example currency value, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="3206a-244">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="3206a-244">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="3206a-245">Os valores de resumo para exibição de **vendas** como moeda.</span><span class="sxs-lookup"><span data-stu-id="3206a-245">The summary values for **Sales** display as currency.</span></span>  
  
##  <a name="6-optional-format-data-as-dates"></a><a name="FormatDates"></a><span data-ttu-id="3206a-246">6. (opcional) formatar dados como datas</span><span class="sxs-lookup"><span data-stu-id="3206a-246">6. (Optional) Format Data as Dates</span></span>  
 <span data-ttu-id="3206a-247">Por padrão, o campo **SalesDate** exibe informações de data e hora.</span><span class="sxs-lookup"><span data-stu-id="3206a-247">By default, the **SalesDate** field displays both date and time information.</span></span> <span data-ttu-id="3206a-248">É possível formatá-lo para exibir somente a data.</span><span class="sxs-lookup"><span data-stu-id="3206a-248">You can format them to display only the date.</span></span>  
  
#### <a name="to-format-a-date-field-as-the-default-format"></a><span data-ttu-id="3206a-249">Para formatar um campo de data como o formato padrão</span><span class="sxs-lookup"><span data-stu-id="3206a-249">To format a date field as the default format</span></span>  
  
1.  <span data-ttu-id="3206a-250">Clique em **Design** para retornar à exibição de design.</span><span class="sxs-lookup"><span data-stu-id="3206a-250">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="3206a-251">Clique na célula que contém `[SalesDate]`.</span><span class="sxs-lookup"><span data-stu-id="3206a-251">Click the cell that contains `[SalesDate]`.</span></span>  
  
3.  <span data-ttu-id="3206a-252">Na faixa de opções, na guia **início** , no grupo **número** , na lista suspensa, selecione **Data**.</span><span class="sxs-lookup"><span data-stu-id="3206a-252">On the Ribbon, on the **Home** tab, in the **Number** group, from the drop-down list, select **Date**.</span></span>  
  
     <span data-ttu-id="3206a-253">A célula exibe a data de exemplo **[1/31/2000]**.</span><span class="sxs-lookup"><span data-stu-id="3206a-253">The cell displays the example date **[1/31/2000]**.</span></span> <span data-ttu-id="3206a-254">Se uma data de exemplo não estiver visível, clique em **Estilos de Espaço Reservado** no grupo **Números** e clique em **Valores de Exemplo**.</span><span class="sxs-lookup"><span data-stu-id="3206a-254">If you do not see an example date, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="3206a-255">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="3206a-255">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="3206a-256">Os valores de **SalesDate** são exibidos no formato de data padrão.</span><span class="sxs-lookup"><span data-stu-id="3206a-256">The **SalesDate** values display in the default date format.</span></span>  
  
##  <a name="7-optional-change-column-widths"></a><a name="Width"></a><span data-ttu-id="3206a-257">7. (opcional) alterar larguras de coluna</span><span class="sxs-lookup"><span data-stu-id="3206a-257">7. (Optional) Change Column Widths</span></span>  
 <span data-ttu-id="3206a-258">Por padrão, cada célula da tabela contém uma caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="3206a-258">By default, each cell in a table contains a text box.</span></span> <span data-ttu-id="3206a-259">Uma caixa de texto é expandida verticalmente para acomodar o texto quando a página é renderizada.</span><span class="sxs-lookup"><span data-stu-id="3206a-259">A text box expands vertically to accommodate text when the page is rendered.</span></span> <span data-ttu-id="3206a-260">No relatório renderizado, cada linha é expandida até a altura da caixa de texto renderizada mais alta da linha.</span><span class="sxs-lookup"><span data-stu-id="3206a-260">In the rendered report, each row expands to the height of the tallest rendered text box in the row.</span></span> <span data-ttu-id="3206a-261">A altura da linha na superfície de design não tem nenhum efeito na altura da linha no relatório renderizado.</span><span class="sxs-lookup"><span data-stu-id="3206a-261">The height of the row on the design surface has no affect on the height of the row in the rendered report.</span></span>  
  
 <span data-ttu-id="3206a-262">Para reduzir a quantidade de espaço vertical que cada linha ocupa, expanda a largura da coluna para acomodar em uma única linha o conteúdo esperado das caixas de texto da coluna.</span><span class="sxs-lookup"><span data-stu-id="3206a-262">To reduce the amount of vertical space each row takes, expand the column width to accommodate the expected contents of the text boxes in the column on one line.</span></span>  
  
#### <a name="to-change-the-width-of-columns"></a><span data-ttu-id="3206a-263">Para alterar a largura das colunas</span><span class="sxs-lookup"><span data-stu-id="3206a-263">To change the width of columns</span></span>  
  
1.  <span data-ttu-id="3206a-264">Clique em **Design** para retornar à exibição de design.</span><span class="sxs-lookup"><span data-stu-id="3206a-264">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="3206a-265">Clique na tabela de forma que os identificadores de coluna e linha sejam exibidos acima e ao lado da tabela.</span><span class="sxs-lookup"><span data-stu-id="3206a-265">Click the table so that column and row handles appear above and next to the table.</span></span>  
  
     <span data-ttu-id="3206a-266">As barras em cinza ao longo da parte superior e ao lado da tabela são os identificadores de coluna e de linha.</span><span class="sxs-lookup"><span data-stu-id="3206a-266">The gray bars along the top and side of the table are the column and row handles.</span></span>  
  
3.  <span data-ttu-id="3206a-267">Aponte para a linha entre os identificadores de coluna para que o cursor seja alterado para uma seta dupla.</span><span class="sxs-lookup"><span data-stu-id="3206a-267">Point to the line between column handles so that the cursor changes into a double arrow.</span></span> <span data-ttu-id="3206a-268">Arraste as colunas de acordo com o tamanho desejado.</span><span class="sxs-lookup"><span data-stu-id="3206a-268">Drag the columns to the size you want.</span></span> <span data-ttu-id="3206a-269">Por exemplo, expanda a coluna do **produto** para que o nome do produto seja exibido em uma linha.</span><span class="sxs-lookup"><span data-stu-id="3206a-269">For example, expand the column for **Product** so that the product name displays on one line.</span></span>  
  
4.  <span data-ttu-id="3206a-270">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="3206a-270">Click **Run** to preview your report.</span></span>  
  
##  <a name="8-optional-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="3206a-271">8. (opcional) adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="3206a-271">8. (Optional) Add a Report Title</span></span>  
 <span data-ttu-id="3206a-272">Um título é exibido na parte superior do relatório.</span><span class="sxs-lookup"><span data-stu-id="3206a-272">A report title appears at the top of the report.</span></span> <span data-ttu-id="3206a-273">É possível colocar o título em um cabeçalho do relatório. No entanto, se ele não usar um cabeçalho, será possível colocar o título em uma caixa de texto na parte superior do corpo do relatório.</span><span class="sxs-lookup"><span data-stu-id="3206a-273">You can place the report title in a report header or if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="3206a-274">Neste tutorial, você usará a caixa de texto colocada automaticamente na parte superior do corpo do relatório.</span><span class="sxs-lookup"><span data-stu-id="3206a-274">In this tutorial, you will use the text box that is automatically placed at the top of the report body.</span></span>  
  
 <span data-ttu-id="3206a-275">O texto pode ser aprimorado ainda mais aplicando-se estilos, tamanhos e cores de fontes diferentes a frases e caracteres individuais do texto.</span><span class="sxs-lookup"><span data-stu-id="3206a-275">The text can be further enhanced by applying different font styles, sizes, and colors to phrases and individual characters of the text.</span></span> <span data-ttu-id="3206a-276">Para obter mais informações, consulte [Formatar o texto em uma caixa de texto &#40;Construtor de Relatórios e SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3206a-276">For more information, see [Format Text in a Text Box &#40;Report Builder and SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="3206a-277">Para adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="3206a-277">To add a report title</span></span>  
  
1.  <span data-ttu-id="3206a-278">Na superfície de design, clique em **Clique para adicionar título**.</span><span class="sxs-lookup"><span data-stu-id="3206a-278">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="3206a-279">Digite **Vendas de Produtos**e clique fora da caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="3206a-279">Type **Product Sales**, and then click outside the text box.</span></span>  
  
3.  <span data-ttu-id="3206a-280">Clique com o botão direito do mouse na caixa de texto que contém **Vendas de Produtos** e clique em **Propriedades da Caixa de Texto**.</span><span class="sxs-lookup"><span data-stu-id="3206a-280">Right-click the text box that contains **Product Sales** and click **Text Box Properties**.</span></span>  
  
4.  <span data-ttu-id="3206a-281">Na caixa de diálogo **Propriedades da Caixa de Texto** , clique em **Fonte**.</span><span class="sxs-lookup"><span data-stu-id="3206a-281">In the **Text Box Properties** dialog box, click **Font**.</span></span>  
  
5.  <span data-ttu-id="3206a-282">Na lista **Tamanho** , selecione **18pt**.</span><span class="sxs-lookup"><span data-stu-id="3206a-282">In the **Size** list, select **18pt**.</span></span>  
  
6.  <span data-ttu-id="3206a-283">Na lista **cor** , selecione **bordô**.</span><span class="sxs-lookup"><span data-stu-id="3206a-283">In the **Color** list, select **Maroon**.</span></span>  
  
7.  <span data-ttu-id="3206a-284">Selecione **Negrito**.</span><span class="sxs-lookup"><span data-stu-id="3206a-284">Select **Bold**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="9-save-the-report"></a><a name="Save"></a><span data-ttu-id="3206a-285">9. salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="3206a-285">9. Save the Report</span></span>  
 <span data-ttu-id="3206a-286">Salve o relatório em um servidor de relatório ou no computador.</span><span class="sxs-lookup"><span data-stu-id="3206a-286">Save the report to a report server or your computer.</span></span> <span data-ttu-id="3206a-287">Se você não salvar o relatório no servidor de relatório, vários recursos do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , como partes do relatório e sub-relatórios, não estarão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="3206a-287">If you do not save the report to the report server, a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features such as report parts and subreports are not available.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="3206a-288">Para salvar o relatório em um servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="3206a-288">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="3206a-289">No botão **Construtor de Relatórios** , clique em **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="3206a-289">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="3206a-290">Clique em **Sites e Servidores Recentes**.</span><span class="sxs-lookup"><span data-stu-id="3206a-290">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="3206a-291">Selecione ou digite o nome do servidor de relatório no qual você tem permissão para salvar relatórios.</span><span class="sxs-lookup"><span data-stu-id="3206a-291">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="3206a-292">A mensagem "Conectando-se a um servidor de relatório" é exibida.</span><span class="sxs-lookup"><span data-stu-id="3206a-292">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="3206a-293">Quando a conexão for concluída, você verá o conteúdo da pasta do relatório que o administrador do servidor de relatório especificou como o local padrão para relatórios.</span><span class="sxs-lookup"><span data-stu-id="3206a-293">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="3206a-294">Em **Nome**, substitua o nome padrão por **Vendas de Produtos**.</span><span class="sxs-lookup"><span data-stu-id="3206a-294">In **Name**, replace the default name with **Product Sales**.</span></span>  
  
5.  <span data-ttu-id="3206a-295">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3206a-295">Click **Save**.</span></span>  
  
 <span data-ttu-id="3206a-296">O relatório será salvo no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="3206a-296">The report is saved to the report server.</span></span> <span data-ttu-id="3206a-297">O nome do servidor de relatório ao qual você está conectado é exibido na barra de status da parte inferior da janela.</span><span class="sxs-lookup"><span data-stu-id="3206a-297">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="3206a-298">Para salvar o relatório no computador</span><span class="sxs-lookup"><span data-stu-id="3206a-298">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="3206a-299">No botão **Construtor de Relatórios** , clique em **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="3206a-299">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="3206a-300">Clique em **Área de Trabalho**, **Meus Documentos**ou **Meu computador**e procure a pasta na qual você quer salvar o relatório.</span><span class="sxs-lookup"><span data-stu-id="3206a-300">Click **Desktop**, **My Documents**, or **My computer**, and browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="3206a-301">Em **Nome**, substitua o nome padrão por **Vendas de Produtos**.</span><span class="sxs-lookup"><span data-stu-id="3206a-301">In **Name**, replace the default name with **Product Sales**.</span></span>  
  
4.  <span data-ttu-id="3206a-302">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3206a-302">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="3206a-303">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="3206a-303">Next Steps</span></span>  
 <span data-ttu-id="3206a-304">Isso conclui o tutorial para criar um relatório de tabela com minigráficos.</span><span class="sxs-lookup"><span data-stu-id="3206a-304">This concludes the tutorial for creating a table report with sparkline charts.</span></span> <span data-ttu-id="3206a-305">Para obter mais informações sobre minigráficos, consulte [Minigráficos e barras de dados &#40;Construtor de Relatórios e SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3206a-305">For more information about sparklines, see [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3206a-306">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3206a-306">See Also</span></span>  
 <span data-ttu-id="3206a-307">[TUTORIAIS &#40;Construtor de Relatórios&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="3206a-307">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="3206a-308">Construtor de Relatórios no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="3206a-308">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
