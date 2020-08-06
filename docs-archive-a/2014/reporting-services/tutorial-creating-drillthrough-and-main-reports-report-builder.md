---
title: 'Tutorial: Criando relatórios principais e de detalhamento (Construtor de Relatórios) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7168c8d3-cef5-4c4a-a0bf-fff1ac5b8b71
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d7d30b59a0c5523ed50df06f8587bbd701ae4c79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684023"
---
# <a name="tutorial-creating-drillthrough-and-main-reports-report-builder"></a><span data-ttu-id="c6a29-102">Tutorial: criando relatórios principais e de detalhamento (Construtor de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="c6a29-102">Tutorial: Creating Drillthrough and Main Reports (Report Builder)</span></span>
  <span data-ttu-id="c6a29-103">Este tutorial ensina como criar dois tipos de relatório: um relatório detalhado e um relatório principal.</span><span class="sxs-lookup"><span data-stu-id="c6a29-103">This tutorial teaches you how to create two kinds of reports: a drillthrough report and a main report.</span></span> <span data-ttu-id="c6a29-104">Os dados de vendas de exemplo usados nestes relatórios são recuperados de um cubo do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="c6a29-104">The sample sales data used in these reports is retrieved from an Analysis Services cube.</span></span> <span data-ttu-id="c6a29-105">A ilustração a seguir mostra os relatórios que você criará.</span><span class="sxs-lookup"><span data-stu-id="c6a29-105">The following illustration shows the reports you will create.</span></span>  
  
 <span data-ttu-id="c6a29-106">![rs_DrillthroughCubeTutorial](../../2014/tutorials/media/rs-drillthroughcubetutorial.gif "rs_DrillthroughCubeTutorial")</span><span class="sxs-lookup"><span data-stu-id="c6a29-106">![rs_DrillthroughCubeTutorial](../../2014/tutorials/media/rs-drillthroughcubetutorial.gif "rs_DrillthroughCubeTutorial")</span></span>  
  
 <span data-ttu-id="c6a29-107">A ilustração a seguir mostra como o valor do campo, jogos e brinquedos, no relatório principal é exibido no título do relatório de detalhamento.</span><span class="sxs-lookup"><span data-stu-id="c6a29-107">The following illustration shows how the field value, Games and Toys, in the main report displays in the drillthrough report's title.</span></span> <span data-ttu-id="c6a29-108">Os dados no detalhamento pertencem à categoria de produto Games and Toys.</span><span class="sxs-lookup"><span data-stu-id="c6a29-108">The data in the drillthrough pertains to the Games and Toys product category.</span></span>  
  
 <span data-ttu-id="c6a29-109">![rs_DrillthroughCubeTutorialParmExpr](../../2014/tutorials/media/rs-drillthroughcubetutorialparmexpr.gif "rs_DrillthroughCubeTutorialParmExpr")</span><span class="sxs-lookup"><span data-stu-id="c6a29-109">![rs_DrillthroughCubeTutorialParmExpr](../../2014/tutorials/media/rs-drillthroughcubetutorialparmexpr.gif "rs_DrillthroughCubeTutorialParmExpr")</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="c6a29-110">O que você aprenderá</span><span class="sxs-lookup"><span data-stu-id="c6a29-110">What You Will Learn</span></span>  
 <span data-ttu-id="c6a29-111">**No relatório detalhado você aprenderá como:**</span><span class="sxs-lookup"><span data-stu-id="c6a29-111">**In the drillthrough report you will learn how to:**</span></span>  
  
1.  [<span data-ttu-id="c6a29-112">Criar um relatório de matriz de detalhamento e um conjunto de dados no Assistente de Tabela ou Matriz</span><span class="sxs-lookup"><span data-stu-id="c6a29-112">Create a Drillthrough Matrix Report and Dataset from the Table or Matrix Wizard</span></span>](#DMatrixAndDataset)  
  
    1.  [<span data-ttu-id="c6a29-113">Especificar uma conexão de dados</span><span class="sxs-lookup"><span data-stu-id="c6a29-113">Specify a Data Connection</span></span>](#DConnection)  
  
    2.  [<span data-ttu-id="c6a29-114">Criar uma consulta MDX</span><span class="sxs-lookup"><span data-stu-id="c6a29-114">Create an MDX Query</span></span>](#DMDXQuery)  
  
    3.  [<span data-ttu-id="c6a29-115">Organizar dados em estilo de grupos</span><span class="sxs-lookup"><span data-stu-id="c6a29-115">Organize Data into Groups Style</span></span>](#DLayout)  
  
    4.  [<span data-ttu-id="c6a29-116">Adicionar subtotais e totais</span><span class="sxs-lookup"><span data-stu-id="c6a29-116">Add Subtotals and Totals</span></span>](#DTotals)  
  
    5.  [<span data-ttu-id="c6a29-117">Escolha um estilo</span><span class="sxs-lookup"><span data-stu-id="c6a29-117">Choose a Style</span></span>](#DStyle)  
  
2.  [<span data-ttu-id="c6a29-118">Formatar dados como moeda</span><span class="sxs-lookup"><span data-stu-id="c6a29-118">Format Data as Currency</span></span>](#DFormat)  
  
3.  [<span data-ttu-id="c6a29-119">Adicionar colunas para mostrar valores de vendas em minigráficos</span><span class="sxs-lookup"><span data-stu-id="c6a29-119">Add columns to Show Sales Values in Sparklines</span></span>](#DSparkline)  
  
4.  [<span data-ttu-id="c6a29-120">Adicionar título de relatório com nome da categoria do produto</span><span class="sxs-lookup"><span data-stu-id="c6a29-120">Add Report Title with Product Category Name</span></span>](#DReportTitle)  
  
5.  [<span data-ttu-id="c6a29-121">Atualizar propriedades de parâmetros</span><span class="sxs-lookup"><span data-stu-id="c6a29-121">Update Parameter Properties</span></span>](#DParameter)  
  
6.  [<span data-ttu-id="c6a29-122">Salvar o relatório em uma biblioteca do SharePoint</span><span class="sxs-lookup"><span data-stu-id="c6a29-122">Save the Report to a SharePoint Library</span></span>](#DSave)  
  
 <span data-ttu-id="c6a29-123">**No relatório principal, você aprenderá como:**</span><span class="sxs-lookup"><span data-stu-id="c6a29-123">**In the main report you will learn how to:**</span></span>  
  
1.  [<span data-ttu-id="c6a29-124">Criar o relatório de matriz principal e o conjunto de dados no Assistente de Tabela ou Matriz</span><span class="sxs-lookup"><span data-stu-id="c6a29-124">Create the Main Matrix Report and Dataset from the Table or Matrix Wizard</span></span>](#MMatrixAndDataset)  
  
    1.  [<span data-ttu-id="c6a29-125">Especificar uma conexão de dados</span><span class="sxs-lookup"><span data-stu-id="c6a29-125">Specify a Data Connection</span></span>](#MConnection)  
  
    2.  [<span data-ttu-id="c6a29-126">Criar uma consulta MDX</span><span class="sxs-lookup"><span data-stu-id="c6a29-126">Create an MDX Query</span></span>](#MMDXQuery)  
  
    3.  [<span data-ttu-id="c6a29-127">Organizar dados em grupos</span><span class="sxs-lookup"><span data-stu-id="c6a29-127">Organize Data into Groups</span></span>](#MLayout)  
  
    4.  [<span data-ttu-id="c6a29-128">Adicionar subtotais e totais</span><span class="sxs-lookup"><span data-stu-id="c6a29-128">Add Subtotals and Totals</span></span>](#MTotals)  
  
    5.  [<span data-ttu-id="c6a29-129">Escolha um estilo</span><span class="sxs-lookup"><span data-stu-id="c6a29-129">Choose a Style</span></span>](#MStyle)  
  
2.  [<span data-ttu-id="c6a29-130">Remover a linha de total geral</span><span class="sxs-lookup"><span data-stu-id="c6a29-130">Remove the Grand Total Row</span></span>](#MGrandTotal)  
  
3.  [<span data-ttu-id="c6a29-131">Configurar ação de caixa de texto para detalhamento</span><span class="sxs-lookup"><span data-stu-id="c6a29-131">Configure Text Box Action for Drillthrough</span></span>](#MDrillthrough)  
  
4.  [<span data-ttu-id="c6a29-132">Substituir valores numéricos por indicadores</span><span class="sxs-lookup"><span data-stu-id="c6a29-132">Replace Numeric Values with Indicators</span></span>](#MIndicators)  
  
5.  [<span data-ttu-id="c6a29-133">Atualizar propriedades de parâmetros</span><span class="sxs-lookup"><span data-stu-id="c6a29-133">Update Parameter Properties</span></span>](#MParameter)  
  
6.  [<span data-ttu-id="c6a29-134">Adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="c6a29-134">Add a Report Title</span></span>](#MTitle)  
  
7.  [<span data-ttu-id="c6a29-135">Salvar o relatório em uma biblioteca do SharePoint</span><span class="sxs-lookup"><span data-stu-id="c6a29-135">Save the Report to a SharePoint Library</span></span>](#MSave)  
  
8.  [<span data-ttu-id="c6a29-136">Executar os relatórios principal e de detalhamento</span><span class="sxs-lookup"><span data-stu-id="c6a29-136">Run the Main and Drillthrough Reports</span></span>](#MRunReports)  
  
 <span data-ttu-id="c6a29-137">Tempo estimado para concluir este tutorial: 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="c6a29-137">Estimated time to complete this tutorial: 30 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6a29-138">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c6a29-138">Requirements</span></span>  
 <span data-ttu-id="c6a29-139">Este tutorial exige acesso ao cubo Vendas da Contoso.</span><span class="sxs-lookup"><span data-stu-id="c6a29-139">This tutorial requires access to the Contoso Sales cube.</span></span> <span data-ttu-id="c6a29-140">Esse requisito se aplica aos relatórios detalhados e principal.</span><span class="sxs-lookup"><span data-stu-id="c6a29-140">This requirement applies to both the drillthrough and the main reports.</span></span> <span data-ttu-id="c6a29-141">Para obter mais informações sobre os requisitos, consulte [Pré-requisitos para tutoriais &#40;Construtor de Relatórios&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="c6a29-141">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-drillthrough-report-from-the-table-or-matrix-wizard"></a><a name="DMatrixAndDataset"></a><span data-ttu-id="c6a29-142">1. criar um relatório detalhado do assistente de tabela ou matriz</span><span class="sxs-lookup"><span data-stu-id="c6a29-142">1. Create a Drillthrough Report from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="c6a29-143">Na caixa de diálogo Introdução , crie um relatório de matriz por meio do **Assistente de Tabela ou Matriz**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-143">From the Getting Started dialog box, create a matrix report by using the **Table or Matrix Wizard**.</span></span> <span data-ttu-id="c6a29-144">Há dois modos disponíveis no assistente: design de relatório e design de conjunto de dados compartilhado.</span><span class="sxs-lookup"><span data-stu-id="c6a29-144">There are two modes available in the wizard: report design and shared dataset design.</span></span> <span data-ttu-id="c6a29-145">Neste tutorial, você usará o modo design de relatório.</span><span class="sxs-lookup"><span data-stu-id="c6a29-145">In this tutorial, you will use the report design mode.</span></span>  
  
#### <a name="to-create-a-new-report"></a><span data-ttu-id="c6a29-146">Para criar um novo relatório</span><span class="sxs-lookup"><span data-stu-id="c6a29-146">To create a new report</span></span>  
  
1.  <span data-ttu-id="c6a29-147">Clique em **Iniciar**, aponte para **programas**, aponte para [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Construtor de relatórios**e, em seguida, clique em **Construtor de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-147">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="c6a29-148">A caixa de diálogo **Guia de Introdução** é aberta.</span><span class="sxs-lookup"><span data-stu-id="c6a29-148">The **Getting Started** dialog box opens.</span></span> <span data-ttu-id="c6a29-149">Se não aparecer, no botão **Construtor de relatórios** , clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-149">If it does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="c6a29-150">No painel esquerdo, verifique se **Novo Relatório** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="c6a29-150">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="c6a29-151">No painel direito, verifique se a opção **Assistente de Tabela ou Matriz** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="c6a29-151">In the right pane, verify that **Table or Matrix Wizard** is selected.</span></span>  
  
##  <a name="1a-specify-a-data-connection"></a><a name="DConnection"></a><span data-ttu-id="c6a29-152">1a.</span><span class="sxs-lookup"><span data-stu-id="c6a29-152">1a.</span></span> <span data-ttu-id="c6a29-153">Especificar uma conexão de dados</span><span class="sxs-lookup"><span data-stu-id="c6a29-153">Specify a Data Connection</span></span>  
 <span data-ttu-id="c6a29-154">Uma conexão de dados contém as informações necessárias para estabelecer conexões com uma fonte de dados externa, como um cubo do Analysis Services ou um banco de dados do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c6a29-154">A data connection contains the information necessary to connect to an external data source such as an Analysis Services cube or a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="c6a29-155">Para especificar uma conexão de dados, você pode usar uma fonte de dados compartilhada do servidor de relatório ou criar uma fonte de dados inserida que será usada somente neste relatório.</span><span class="sxs-lookup"><span data-stu-id="c6a29-155">To specify a data connection, you can use a shared data source from the report server or create an embedded data source that is used only in this report.</span></span> <span data-ttu-id="c6a29-156">Neste tutorial, você usará uma fonte de dados inserida.</span><span class="sxs-lookup"><span data-stu-id="c6a29-156">In this tutorial, you will use an embedded data source.</span></span> <span data-ttu-id="c6a29-157">Para saber mais sobre como usar uma fonte de dados compartilhada, consulte [Formas alternativas de obter uma conexão de dados &#40;Construtor de Relatórios&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="c6a29-157">To learn more about using a shared data source, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
#### <a name="to-create-an-embedded-data-source"></a><span data-ttu-id="c6a29-158">Para criar uma fonte de dados inserida</span><span class="sxs-lookup"><span data-stu-id="c6a29-158">To create an embedded data source</span></span>  
  
1.  <span data-ttu-id="c6a29-159">Na página **Escolher um conjunto de dados** , selecione **Criar um conjunto de dados**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-159">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="c6a29-160">A página **Escolher uma conexão com uma fonte de dados** é aberta.</span><span class="sxs-lookup"><span data-stu-id="c6a29-160">The **Choose a connection to a data source** page opens.</span></span>  
  
2.  <span data-ttu-id="c6a29-161">Clique em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-161">Click **New**.</span></span> <span data-ttu-id="c6a29-162">A caixa de diálogo **Propriedades da Fonte de Dados** é aberta.</span><span class="sxs-lookup"><span data-stu-id="c6a29-162">The **Data Source Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="c6a29-163">Em **Nome**, digite **Detalhes de Vendas Online e do Revendedor** como o nome da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c6a29-163">In **Name**, type **Online and Reseller Sales Detail** as the name for the data source.</span></span>  
  
4.  <span data-ttu-id="c6a29-164">Em **Selecione um tipo de conexão**, selecione **Microsoft SQL Server Analysis Services**e clique em **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-164">In **Select a connection type**, select **Microsoft SQL Server Analysis Services**, and then click **Build**.</span></span>  
  
5.  <span data-ttu-id="c6a29-165">Em **Fonte de dados**, verifique se a fonte de dados é **Microsoft SQL Server Analysis Services (AdomdClient)**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-165">In **Data source**, verify that the data source is **Microsoft SQL Server Analysis Services (AdomdClient)**.</span></span>  
  
6.  <span data-ttu-id="c6a29-166">Em **Nome do servidor**, digite o nome de um servidor em que uma instância do Analysis Services está instalada.</span><span class="sxs-lookup"><span data-stu-id="c6a29-166">In **Server name**, type the name of a server where an instance of Analysis Services is installed.</span></span>  
  
7.  <span data-ttu-id="c6a29-167">Em **Selecionar ou inserir um nome de banco de dados**, selecione o cubo Contoso.</span><span class="sxs-lookup"><span data-stu-id="c6a29-167">In **Select or enter a database name**, select the Contoso cube.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="c6a29-168">Verifique se **Cadeia de conexão** contém a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c6a29-168">Verify that **Connection string** contains the following syntax:</span></span>  
  
    ```  
    Data Source=<servername>; Initial Catalog = Contoso  
    ```  
  
     <span data-ttu-id="c6a29-169">O `<servername>` é o nome de uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] com o Analysis Services instalado.</span><span class="sxs-lookup"><span data-stu-id="c6a29-169">The `<servername>` is the name of an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] with Analysis Services installed.</span></span>  
  
10. <span data-ttu-id="c6a29-170">Clique em **Tipo de credenciais**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-170">Click **Credentials type**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c6a29-171">Dependendo de como as permissões estão configuradas na fonte de dados, poderá ser necessário alterar as opções de autenticação padrão.</span><span class="sxs-lookup"><span data-stu-id="c6a29-171">Depending on how permissions are configured on the data source, you might need to change the default authentication options.</span></span> <span data-ttu-id="c6a29-172">Para obter mais informações, consulte [Segurança &#40;Construtor de Relatórios&#41;](report-builder/security-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="c6a29-172">For more information, see [Security &#40;Report Builder&#41;](report-builder/security-report-builder.md).</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="c6a29-173">A página **Escolher uma conexão com uma fonte de dados** é exibida.</span><span class="sxs-lookup"><span data-stu-id="c6a29-173">The **Choose a connection to a data source** page appears.</span></span>  
  
12. <span data-ttu-id="c6a29-174">Para verificar se é possível se conectar à fonte de dados, clique em **Testar Conexão**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-174">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
     <span data-ttu-id="c6a29-175">A conexão da mensagem **criada com êxito** é exibida.</span><span class="sxs-lookup"><span data-stu-id="c6a29-175">The message **Connection created successfully** appears.</span></span>  
  
13. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
14. <span data-ttu-id="c6a29-176">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-176">Click **Next**.</span></span>  
  
##  <a name="1b-create-an-mdx-query"></a><a name="DMDXQuery"></a><span data-ttu-id="c6a29-177">1B.</span><span class="sxs-lookup"><span data-stu-id="c6a29-177">1b.</span></span> <span data-ttu-id="c6a29-178">Criar uma consulta MDX</span><span class="sxs-lookup"><span data-stu-id="c6a29-178">Create an MDX Query</span></span>  
 <span data-ttu-id="c6a29-179">Em um relatório, é possível usar um conjunto de dados compartilhado que tenha uma consulta predefinida. Se preferir, crie um conjunto de dados inserido para ser usado somente em seu relatório.</span><span class="sxs-lookup"><span data-stu-id="c6a29-179">In a report, you can use a shared dataset that has a predefined query, or you can create an embedded dataset for use only in your report.</span></span> <span data-ttu-id="c6a29-180">Neste tutorial, você criará um conjunto de dados inserido.</span><span class="sxs-lookup"><span data-stu-id="c6a29-180">In this tutorial, you will create an embedded dataset.</span></span>  
  
#### <a name="to-create-query-filters"></a><span data-ttu-id="c6a29-181">Para criar filtros de consulta</span><span class="sxs-lookup"><span data-stu-id="c6a29-181">To create query filters</span></span>  
  
1.  <span data-ttu-id="c6a29-182">Na página **criar uma consulta** , no painel metadados, clique no botão **(...)**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-182">On the **Design a query** page, in the Metadata pane, click the button **(...)**.</span></span>  
  
2.  <span data-ttu-id="c6a29-183">Na caixa de diálogo **Seleção de Cubo** , clique em Vendas e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-183">In the **Cube Selection** dialog box, click Sales, and then click **OK**.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="c6a29-184">Se não desejar criar a consulta MDX manualmente, clique no ícone ![Alternar para modo de Design](media/rsqdicon-designmode.gif "Alterna para o modo de design"), ative/desative o designer de consultas para o modo de Consulta, cole o MDX concluído no designer de consultas e vá para a etapa 6 em [Para criar o conjunto de dados](#DSkip).</span><span class="sxs-lookup"><span data-stu-id="c6a29-184">If you do not want to build the MDX query manually, click the ![Switch to Design mode](media/rsqdicon-designmode.gif "Switch to Design mode") icon, toggle the query designer to Query mode, paste the completed MDX to the query designer, and then proceed to step 6 in [To create the dataset](#DSkip).</span></span>  
  
    ```  
    SELECT NON EMPTY { [Measures].[Sales Amount], [Measures].[Sales Return Amount] } ON COLUMNS, NON EMPTY { ([Channel].[Channel Name].[Channel Name].ALLMEMBERS * [Product].[Product Category Name].[Product Category Name].ALLMEMBERS * [Product].[Product Subcategory Name].[Product Subcategory Name].ALLMEMBERS ) } DIMENSION PROPERTIES MEMBER_CAPTION, MEMBER_UNIQUE_NAME ON ROWS FROM ( SELECT ( { [Date].[Calendar Year].&[2009] } ) ON COLUMNS FROM ( SELECT ( { [Sales Territory].[Sales Territory Group].&[North America] } ) ON COLUMNS FROM ( SELECT ( STRTOSET(@ProductProductCategoryName, CONSTRAINED) ) ON COLUMNS FROM ( SELECT ( { [Channel].[Channel Name].&[2], [Channel].[Channel Name].&[4] } ) ON COLUMNS FROM [Sales])))) WHERE ( [Sales Territory].[Sales Territory Group].&[North America], [Date].[Calendar Year].&[2009] ) CELL PROPERTIES VALUE, BACK_COLOR, FORE_COLOR, FORMATTED_VALUE, FORMAT_STRING, FONT_NAME, FONT_SIZE, FONT_FLAGS  
    ```  
  
3.  <span data-ttu-id="c6a29-185">No painel Grupo de Medidas, expanda Canal e arraste Nome do Canal até a coluna **Hierarquia** no painel de filtro.</span><span class="sxs-lookup"><span data-stu-id="c6a29-185">In the Measure Group pane, expand Channel, and then drag Channel Name to the **Hierarchy** column in the filter pane.</span></span>  
  
     <span data-ttu-id="c6a29-186">O nome da dimensão, Canal, é adicionado automaticamente à coluna **Dimensão** .</span><span class="sxs-lookup"><span data-stu-id="c6a29-186">The dimension name, Channel, is automatically added to the **Dimension** column.</span></span> <span data-ttu-id="c6a29-187">Não altere as colunas **Dimensão** ou **Operador** .</span><span class="sxs-lookup"><span data-stu-id="c6a29-187">Do not change the **Dimension** or **Operator** columns.</span></span>  
  
4.  <span data-ttu-id="c6a29-188">Para abrir a lista **Expressão de Filtro** , clique na seta para baixo na coluna **Expressão de Filtro** .</span><span class="sxs-lookup"><span data-stu-id="c6a29-188">To open the **Filter Expression** list, click the down arrow in the **Filter Expression** column.</span></span>  
  
5.  <span data-ttu-id="c6a29-189">Na lista de expressões de filtro, expanda **Todo o Canal**, clique em **Online**, em **Revendedor**e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-189">In the filter expression list, expand **All Channel**, click **Online**, click **Reseller**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="c6a29-190">A consulta agora inclui um filtro para incluir apenas estes canais: Online e Revendedor.</span><span class="sxs-lookup"><span data-stu-id="c6a29-190">The query now includes a filter to include only these channels: Online and Reseller.</span></span>  
  
6.  <span data-ttu-id="c6a29-191">Expanda a dimensão Região de Vendas e arraste Grupo da Região de Vendas até a coluna **Hierarquia** (abaixo de **Nome do Canal**).</span><span class="sxs-lookup"><span data-stu-id="c6a29-191">Expand the Sales Territory dimension, and then drag Sales Territory Group to the **Hierarchy** column (below **Channel Name**).</span></span>  
  
7.  <span data-ttu-id="c6a29-192">Abra a lista **Expressão de Filtro** , expanda **Toda a Região de Vendas**, clique em **América do Norte**e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-192">Open the **Filter Expression** list, expand **All Sales Territory**, click **North America**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="c6a29-193">A consulta agora tem um filtro para incluir apenas vendas na América do Norte.</span><span class="sxs-lookup"><span data-stu-id="c6a29-193">The query now has a filter to include only sales in North America.</span></span>  
  
8.  <span data-ttu-id="c6a29-194">No painel Grupo de Medidas, expanda Data e arraste Ano Civil até a coluna **Hierarquia** no painel de filtro.</span><span class="sxs-lookup"><span data-stu-id="c6a29-194">In the Measure Group pane, expand Date, and then drag Calendar Year to the **Hierarchy** column in the filter pane.</span></span>  
  
     <span data-ttu-id="c6a29-195">O nome da dimensão, Data, é adicionado automaticamente à coluna **Dimensão** .</span><span class="sxs-lookup"><span data-stu-id="c6a29-195">The dimension name, Date, is automatically added to the **Dimension** column.</span></span> <span data-ttu-id="c6a29-196">Não altere as colunas **Dimensão** ou **Operador** .</span><span class="sxs-lookup"><span data-stu-id="c6a29-196">Do not change the **Dimension** or **Operator** columns.</span></span>  
  
9. <span data-ttu-id="c6a29-197">Para abrir a lista **Expressão de Filtro** , clique na seta para baixo na coluna **Expressão de Filtro** .</span><span class="sxs-lookup"><span data-stu-id="c6a29-197">To open the **Filter Expression** list, click the down arrow in the **Filter Expression** column.</span></span>  
  
10. <span data-ttu-id="c6a29-198">Na lista de expressões de filtro, expanda **Toda a Data**, clique em **Ano 2009**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-198">In the filter expression list, expand **All Date**, click **Year 2009**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="c6a29-199">A consulta agora inclui um filtro para incluir apenas o ano calendário 2009.</span><span class="sxs-lookup"><span data-stu-id="c6a29-199">The query now includes a filter to include only the calendar year 2009.</span></span>  
  
#### <a name="to-create-the-parameter"></a><span data-ttu-id="c6a29-200">Para criar o parâmetro</span><span class="sxs-lookup"><span data-stu-id="c6a29-200">To create the parameter</span></span>  
  
1.  <span data-ttu-id="c6a29-201">Expanda a dimensão Produto e arraste o membro Nome da Categoria do Produto até a coluna **Hierarquia** abaixo de **Ano Civil**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-201">Expand the Product dimension, and then drag the Product Category Name member to the **Hierarchy** column below **Calendar Year**.</span></span>  
  
2.  <span data-ttu-id="c6a29-202">Abra a lista **Expressão de Filtro** , clique em **Todos os Produtos**e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-202">Open the **Filter Expression** list, click **All Products**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="c6a29-203">Clique na caixa de seleção **Parâmetro** .</span><span class="sxs-lookup"><span data-stu-id="c6a29-203">Click the **Parameter** checkbox.</span></span> <span data-ttu-id="c6a29-204">A consulta agora inclui o parâmetro ProductProductCategoryName.</span><span class="sxs-lookup"><span data-stu-id="c6a29-204">The query now includes the parameter ProductProductCategoryName.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c6a29-205">O parâmetro contém os nomes das categorias de produto.</span><span class="sxs-lookup"><span data-stu-id="c6a29-205">The parameter contains the names of product categories.</span></span> <span data-ttu-id="c6a29-206">Quando você clica no nome de uma categoria de produto no relatório principal, o nome é passado para o relatório detalhado por meio desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="c6a29-206">When you click a product category name in the main report, its name is passed to the drillthrough report by using this parameter.</span></span>  
  
###  <a name="to-create-the-dataset"></a><a name="DSkip"></a><span data-ttu-id="c6a29-207">Para criar o conjunto de um</span><span class="sxs-lookup"><span data-stu-id="c6a29-207">To create the dataset</span></span>  
  
1.  <span data-ttu-id="c6a29-208">Na dimensão Canal, arraste Nome do Canal até o painel de dados.</span><span class="sxs-lookup"><span data-stu-id="c6a29-208">From the Channel dimension, drag Channel Name to the data pane.</span></span>  
  
2.  <span data-ttu-id="c6a29-209">Na dimensão Produto, arraste Nome da Categoria do Produto até o painel de dados e coloque-o à direita de Nome do Canal.</span><span class="sxs-lookup"><span data-stu-id="c6a29-209">From the Product dimension, drag Product Category Name to the data pane, and then place it to the right of Channel Name.</span></span>  
  
3.  <span data-ttu-id="c6a29-210">Na dimensão Produto, arraste Nome da Subcategoria do Produto até o painel de dados e coloque-o à direita de Nome da Categoria do Produto.</span><span class="sxs-lookup"><span data-stu-id="c6a29-210">From the Product dimension, drag Product Subcategory Name to the data pane, and then place it to the right of Product Category Name.</span></span>  
  
4.  <span data-ttu-id="c6a29-211">No painel Metadados, expanda **Medida**e Vendas.</span><span class="sxs-lookup"><span data-stu-id="c6a29-211">In the Metadata pane, expand **Measure**, and then expand Sales.</span></span>  
  
5.  <span data-ttu-id="c6a29-212">Arraste a medida Valor das Vendas até o painel de dados e coloque-a à direita de Nome da Subcategoria do Produto.</span><span class="sxs-lookup"><span data-stu-id="c6a29-212">Drag the Sales Amount measure to the data pane, and then place it to the right of Product Subcategory Name.</span></span>  
  
6.  <span data-ttu-id="c6a29-213">Na barra de ferramentas do designer de consultas, clique em **executar (!)**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-213">On the query designer toolbar, click **Run (!)**.</span></span>  
  
7.  <span data-ttu-id="c6a29-214">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-214">Click **Next**.</span></span>  
  
##  <a name="1c-organize-data-into-groups"></a><a name="DLayout"></a><span data-ttu-id="c6a29-215">1C.</span><span class="sxs-lookup"><span data-stu-id="c6a29-215">1c.</span></span> <span data-ttu-id="c6a29-216">Organizar dados em grupos</span><span class="sxs-lookup"><span data-stu-id="c6a29-216">Organize Data into Groups</span></span>  
 <span data-ttu-id="c6a29-217">Quando você seleciona os campos nos quais agrupar os dados, cria uma matriz com linhas e colunas que exibe dados detalhados e dados agregados.</span><span class="sxs-lookup"><span data-stu-id="c6a29-217">When you select the fields on which to group the data, you design a matrix with rows and columns that displays detail and aggregated data.</span></span>  
  
#### <a name="to-organize-data-into-groups"></a><span data-ttu-id="c6a29-218">Para organizar dados em grupos</span><span class="sxs-lookup"><span data-stu-id="c6a29-218">To organize data into groups</span></span>  
  
1.  <span data-ttu-id="c6a29-219">Para mudar para o modo design, clique em **Design**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-219">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="c6a29-220">Na página **Organizar campos** , arraste Product_Subcategory_Name até **Grupos de linhas**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-220">On the **Arrange fields** page, drag Product_Subcategory_Name to **Row groups**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c6a29-221">Os espaços nos nomes são substituídos por sublinhados (_).</span><span class="sxs-lookup"><span data-stu-id="c6a29-221">The spaces in the names are replaced with underscores (_).</span></span> <span data-ttu-id="c6a29-222">Por exemplo, Nome da Categoria do Produto é Product_Category_Name.</span><span class="sxs-lookup"><span data-stu-id="c6a29-222">For example Product Category Name is Product_Category_Name.</span></span>  
  
3.  <span data-ttu-id="c6a29-223">Arraste Channel_Name até **Grupos de colunas**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-223">Drag Channel_Name to **Column groups**.</span></span>  
  
4.  <span data-ttu-id="c6a29-224">Arraste Sales_Amount até **Valores**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-224">Drag Sales_Amount to **Values**.</span></span>  
  
     <span data-ttu-id="c6a29-225">Sales_Amount é agregado automaticamente pela função Sum, a agregação padrão para campos numéricos.</span><span class="sxs-lookup"><span data-stu-id="c6a29-225">Sales_Amount is automatically aggregated by the Sum function, the default aggregate for numeric fields.</span></span> <span data-ttu-id="c6a29-226">O valor é `[Sum(Sales_Amount)]`.</span><span class="sxs-lookup"><span data-stu-id="c6a29-226">The value is `[Sum(Sales_Amount)]`.</span></span>  
  
     <span data-ttu-id="c6a29-227">Para exibir as outras funções de agregação disponíveis, abra a lista suspensa (não altere a função de agregação).</span><span class="sxs-lookup"><span data-stu-id="c6a29-227">To view the other aggregate functions available, open the drop-down list (do not change the aggregate function).</span></span>  
  
5.  <span data-ttu-id="c6a29-228">Arraste Sales_Return_Amount até **Valores**e coloque-o abaixo de `[Sum(Sales_Amount)]`.</span><span class="sxs-lookup"><span data-stu-id="c6a29-228">Drag Sales_Return_Amount to **Values**, and then place it below `[Sum(Sales_Amount)]`.</span></span>  
  
     <span data-ttu-id="c6a29-229">As etapas 4 e 5 especificam os dados a serem exibidos na matriz.</span><span class="sxs-lookup"><span data-stu-id="c6a29-229">Steps 4 and 5 specify the data to display in the matrix.</span></span>  
  
6.  <span data-ttu-id="c6a29-230">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-230">Click **Next**.</span></span>  
  
##  <a name="1d-add-subtotals-and-totals"></a><a name="DTotals"></a><span data-ttu-id="c6a29-231">1D.</span><span class="sxs-lookup"><span data-stu-id="c6a29-231">1d.</span></span> <span data-ttu-id="c6a29-232">Adicionar subtotais e totais</span><span class="sxs-lookup"><span data-stu-id="c6a29-232">Add Subtotals and Totals</span></span>  
 <span data-ttu-id="c6a29-233">Depois de criar grupos, é possível adicionar e formatar linhas onde os valores de agregação dos campos serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="c6a29-233">After you create groups, you can add and format rows where the aggregate values for the fields will display.</span></span> <span data-ttu-id="c6a29-234">Também é possível escolher mostrar todos os dados ou permitir que um usuário expanda e recolha dados agrupados de forma interativa.</span><span class="sxs-lookup"><span data-stu-id="c6a29-234">You can also choose whether to show all the data or to let a user expand and collapse grouped data interactively.</span></span>  
  
#### <a name="to-add-subtotals-and-totals"></a><span data-ttu-id="c6a29-235">Para adicionar subtotais e totais</span><span class="sxs-lookup"><span data-stu-id="c6a29-235">To add subtotals and totals</span></span>  
  
1.  <span data-ttu-id="c6a29-236">Na página **escolher o layout** , em opções, verifique se a **opção** **Mostrar Subtotais e totais gerais** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="c6a29-236">On the **Choose the layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
     <span data-ttu-id="c6a29-237">O painel Visualizar do assistente exibe uma matriz com quatro linhas.</span><span class="sxs-lookup"><span data-stu-id="c6a29-237">The wizard Preview pane displays a matrix with four rows.</span></span>  
  
2.  <span data-ttu-id="c6a29-238">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-238">Click **Next**.</span></span>  
  
##  <a name="1e-choose-a-style"></a><a name="DStyle"></a><span data-ttu-id="c6a29-239">1e.</span><span class="sxs-lookup"><span data-stu-id="c6a29-239">1e.</span></span> <span data-ttu-id="c6a29-240">Escolha um estilo</span><span class="sxs-lookup"><span data-stu-id="c6a29-240">Choose a Style</span></span>  
 <span data-ttu-id="c6a29-241">Um estilo especifica um estilo de fonte, um conjunto de cores e um estilo de borda.</span><span class="sxs-lookup"><span data-stu-id="c6a29-241">A style specifies a font style, a set of colors, and a border style.</span></span>  
  
#### <a name="to-specify-a-style"></a><span data-ttu-id="c6a29-242">Para especificar um estilo</span><span class="sxs-lookup"><span data-stu-id="c6a29-242">To specify a style</span></span>  
  
1.  <span data-ttu-id="c6a29-243">Na página **escolher um estilo** , no painel estilos, selecione Slate.</span><span class="sxs-lookup"><span data-stu-id="c6a29-243">On the **Choose a Style** page, in the Styles pane, select Slate.</span></span>  
  
2.  <span data-ttu-id="c6a29-244">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-244">Click **Finish**.</span></span>  
  
     <span data-ttu-id="c6a29-245">A tabela é adicionada à superfície de design.</span><span class="sxs-lookup"><span data-stu-id="c6a29-245">The table is added to the design surface.</span></span>  
  
3.  <span data-ttu-id="c6a29-246">Para visualizar o relatório, clique em **Executar (!)**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-246">To preview the report, click **Run (!)**.</span></span>  
  
##  <a name="2-format-data-as-currency"></a><a name="DFormat"></a><span data-ttu-id="c6a29-247">2. formatar dados como moeda</span><span class="sxs-lookup"><span data-stu-id="c6a29-247">2. Format Data as Currency</span></span>  
 <span data-ttu-id="c6a29-248">Aplique a formatação de moeda aos campos de valor de vendas no relatório detalhado.</span><span class="sxs-lookup"><span data-stu-id="c6a29-248">Apply currency formatting to the sales amount fields in the drillthrough report.</span></span>  
  
#### <a name="to-format-data-as-currency"></a><span data-ttu-id="c6a29-249">Para formatar dados como moeda</span><span class="sxs-lookup"><span data-stu-id="c6a29-249">To format data as currency</span></span>  
  
1.  <span data-ttu-id="c6a29-250">Para mudar para o modo design, clique em **Design**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-250">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="c6a29-251">Para selecionar e formatar várias células de uma vez, pressione a tecla Ctrl e selecione as células que contêm os dados de vendas numéricos.</span><span class="sxs-lookup"><span data-stu-id="c6a29-251">To select and format multiple cells at one time, press the Ctrl key, and then select the cells that contain the numeric sales data.</span></span>  
  
3.  <span data-ttu-id="c6a29-252">Na guia **Início** , no grupo **Número** , clique em **Moeda**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-252">On the **Home** tab, in the **Number** group, click **Currency**.</span></span>  
  
##  <a name="3-add-columns-to-show-sales-values-in-sparklines"></a><a name="DSparkline"></a><span data-ttu-id="c6a29-253">3. adicionar colunas para mostrar valores de vendas em minigráficos</span><span class="sxs-lookup"><span data-stu-id="c6a29-253">3. Add Columns to Show Sales Values in Sparklines</span></span>  
 <span data-ttu-id="c6a29-254">Em vez de mostrar vendas e devoluções de vendas como valores de moeda, o relatório mostra os valores em um minigráfico.</span><span class="sxs-lookup"><span data-stu-id="c6a29-254">Instead of showing sales and sales returns as currency values, the report shows the values in a sparkline.</span></span>  
  
#### <a name="to-add-sparklines-to-columns"></a><span data-ttu-id="c6a29-255">Para adicionar minigráficos a colunas</span><span class="sxs-lookup"><span data-stu-id="c6a29-255">To add sparklines to columns</span></span>  
  
1.  <span data-ttu-id="c6a29-256">Para mudar para o modo design, clique em **Design**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-256">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="c6a29-257">No grupo Total da matriz, clique com o botão direito do mouse na coluna **Valor das Vendas** , clique em **Inserir Coluna**e em **Direita**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-257">In the Total group of the matrix, right-click the **Sales Amount** column, click **Insert Column**, and then click **Right**.</span></span>  
  
     <span data-ttu-id="c6a29-258">Uma coluna vazia é adicionada à direita de **Valor das Vendas**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-258">An empty column is added to the right of **Sales Amount**.</span></span>  
  
3.  <span data-ttu-id="c6a29-259">Na faixa de opções, clique em **Retângulo**e clique na célula vazia à direita da célula `[Sum(Sales_Amount)]` no grupo de linhas [Product_Subcategory].</span><span class="sxs-lookup"><span data-stu-id="c6a29-259">On the ribbon, click **Rectangle**, and then click the empty cell to the right of the `[Sum(Sales_Amount)]` cell in the [Product_Subcategory] row group.</span></span>  
  
4.  <span data-ttu-id="c6a29-260">Na faixa de opções, clique no ícone **Minigráfico** e clique na célula em que o retângulo foi adicionado.</span><span class="sxs-lookup"><span data-stu-id="c6a29-260">On the ribbon, click the **Sparkline** icon, and then click the cell where the rectangle was added.</span></span>  
  
5.  <span data-ttu-id="c6a29-261">Na caixa de diálogo **Selecionar Tipo de Minigráfico** , verifique se o tipo **Coluna** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="c6a29-261">In the **Select Sparkline Type** dialog box, verify that **Column** type is selected.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="c6a29-262">Clique com o botão direito do mouse no minigráfico.</span><span class="sxs-lookup"><span data-stu-id="c6a29-262">Right-click the sparkline.</span></span>  
  
8.  <span data-ttu-id="c6a29-263">No painel Dados do Gráfico, clique no ícone **Adicionar campo** e em Sales_Amount.</span><span class="sxs-lookup"><span data-stu-id="c6a29-263">In the Chart Data pane, click the **Add field** icon, and then click Sales_Amount.</span></span>  
  
9. <span data-ttu-id="c6a29-264">Clique com o botão direito do mouse na coluna `Sales_Return_Amount` e adicione uma coluna à direita dessa coluna.</span><span class="sxs-lookup"><span data-stu-id="c6a29-264">Right-click the `Sales_Return_Amount` column, and then add a column to the right of it.</span></span>  
  
10. <span data-ttu-id="c6a29-265">Repita as etapas 2 a 6.</span><span class="sxs-lookup"><span data-stu-id="c6a29-265">Repeat steps 2 through 6.</span></span>  
  
11. <span data-ttu-id="c6a29-266">Clique com o botão direito do mouse no minigráfico.</span><span class="sxs-lookup"><span data-stu-id="c6a29-266">Right-click the sparkline.</span></span>  
  
12. <span data-ttu-id="c6a29-267">No painel Dados do Gráfico, clique no ícone **Adicionar campo** e em Sales_Return_Amount.</span><span class="sxs-lookup"><span data-stu-id="c6a29-267">In the Chart Data pane, click the **Add field** icon, and then click Sales_Return_Amount.</span></span>  
  
13. <span data-ttu-id="c6a29-268">Para visualizar o relatório, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-268">To preview the report, click **Run**.</span></span>  
  
##  <a name="4-add-report-title-with-product-category-name"></a><a name="DReportTitle"></a><span data-ttu-id="c6a29-269">4. adicionar título de relatório com nome de categoria de produto</span><span class="sxs-lookup"><span data-stu-id="c6a29-269">4. Add Report Title with Product Category Name</span></span>  
 <span data-ttu-id="c6a29-270">Um título é exibido na parte superior do relatório.</span><span class="sxs-lookup"><span data-stu-id="c6a29-270">A report title appears at the top of the report.</span></span> <span data-ttu-id="c6a29-271">É possível colocar o título em um cabeçalho do relatório ou, se o relatório não usar um cabeçalho, em uma caixa de texto na parte superior do corpo do relatório.</span><span class="sxs-lookup"><span data-stu-id="c6a29-271">You can place the report title in a report header or, if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="c6a29-272">Neste tutorial, você usará a caixa de texto colocada automaticamente na parte superior do corpo do relatório.</span><span class="sxs-lookup"><span data-stu-id="c6a29-272">In this tutorial, you will use the text box that is automatically placed at the top of the report body.</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="c6a29-273">Para adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="c6a29-273">To add a report title</span></span>  
  
1.  <span data-ttu-id="c6a29-274">Para mudar para o modo design, clique em **Design**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-274">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="c6a29-275">Na superfície de design, clique em **Clique para adicionar título**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-275">On the design surface, click **Click to add title**.</span></span>  
  
3.  <span data-ttu-id="c6a29-276">Digite **Vendas e Devoluções por Categoria:**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-276">Type **Sales and Returns for Category:**.</span></span>  
  
4.  <span data-ttu-id="c6a29-277">Clique com o botão direito do mouse em **Criar Espaço Reservado**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-277">Right-click, and then click **Create Placeholder**.</span></span>  
  
5.  <span data-ttu-id="c6a29-278">Clique no botão **(fx)** à direita da lista **Valor** .</span><span class="sxs-lookup"><span data-stu-id="c6a29-278">Click the **(fx)** button to the right of the **Value** list.</span></span>  
  
6.  <span data-ttu-id="c6a29-279">Na caixa de diálogo **Expressão** , no painel Categoria, clique em **Conjunto de Dados**e, na lista **Valores** , clique duas vezes em `First(Product_Category_Name)`.</span><span class="sxs-lookup"><span data-stu-id="c6a29-279">In the **Expression** dialog box, in the Category pane, click **Dataset**, and then in the **Values** list double-click `First(Product_Category_Name)`.</span></span>  
  
     <span data-ttu-id="c6a29-280">A caixa **Expressão** contém a seguinte expressão:</span><span class="sxs-lookup"><span data-stu-id="c6a29-280">The **Expression** box contains the following expression:</span></span>  
  
    ```  
    =First(Fields!Product_Category_Name.Value, "DataSet1")  
    ```  
  
7.  <span data-ttu-id="c6a29-281">Para visualizar o relatório, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-281">To preview the report, click **Run**.</span></span>  
  
 <span data-ttu-id="c6a29-282">O título do relatório inclui o nome da primeira categoria de produto.</span><span class="sxs-lookup"><span data-stu-id="c6a29-282">The report title includes the name of the first product category.</span></span> <span data-ttu-id="c6a29-283">Posteriormente, depois que você executar esse relatório como um relatório detalhado, o nome da categoria do produto será alterado dinamicamente para refletir o nome da categoria do produto que foi clicada no relatório principal.</span><span class="sxs-lookup"><span data-stu-id="c6a29-283">Later, after you run this report as a drillthrough report, the product category name will dynamically change to reflect the name of the product category that was clicked in the main report.</span></span>  
  
##  <a name="5-update-parameter-properties"></a><a name="DParameter"></a><span data-ttu-id="c6a29-284">5. atualizar propriedades do parâmetro</span><span class="sxs-lookup"><span data-stu-id="c6a29-284">5. Update Parameter Properties</span></span>  
 <span data-ttu-id="c6a29-285">Por padrão, os parâmetros estão visíveis, o que não é apropriado para este relatório.</span><span class="sxs-lookup"><span data-stu-id="c6a29-285">By default parameters are visible, which is not appropriate for this report.</span></span> <span data-ttu-id="c6a29-286">Você atualizará as propriedades dos parâmetros do relatório detalhado.</span><span class="sxs-lookup"><span data-stu-id="c6a29-286">You will update the parameter properties for the drillthrough report.</span></span>  
  
#### <a name="to-hide-a-parameter"></a><span data-ttu-id="c6a29-287">Para ocultar um parâmetro</span><span class="sxs-lookup"><span data-stu-id="c6a29-287">To hide a parameter</span></span>  
  
1.  <span data-ttu-id="c6a29-288">No painel Dados do Relatório, expanda **Parâmetros**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-288">In the Report Data pane, expand **Parameters**.</span></span>  
  
2.  <span data-ttu-id="c6a29-289">Clique com o botão direito do mouse em \@ ProductProductCategoryName e clique em **Propriedades do parâmetro**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-289">Right-click \@ProductProductCategoryName, and then click **Parameter Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c6a29-290">O caractere \@ próximo ao nome indica que este é um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="c6a29-290">The \@ character next to the name indicates that this is a parameter.</span></span>  
  
3.  <span data-ttu-id="c6a29-291">Na guia **Geral** , clique em **Oculto**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-291">On the **General** tab, click **Hidden**.</span></span>  
  
4.  <span data-ttu-id="c6a29-292">Na caixa **Aviso** , digite **Categoria do Produto**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-292">In the **Prompt** box, type **Product Category**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c6a29-293">Como o parâmetro está oculto, esse aviso nunca é usado.</span><span class="sxs-lookup"><span data-stu-id="c6a29-293">Because the parameter is hidden, this prompt is never used.</span></span>  
  
5.  <span data-ttu-id="c6a29-294">Opcionalmente, clique em **Valores Disponíveis** e em **Valores Padrão** e examine as opções.</span><span class="sxs-lookup"><span data-stu-id="c6a29-294">Optionally, click **Available Values** and **Default Values** and review their options.</span></span> <span data-ttu-id="c6a29-295">Não altere nenhuma opção nessas guias.</span><span class="sxs-lookup"><span data-stu-id="c6a29-295">Do not change any options on these tabs.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="6-save-the-report-to-a-sharepoint-library"></a><a name="DSave"></a><span data-ttu-id="c6a29-296">6. salvar o relatório em uma biblioteca do SharePoint</span><span class="sxs-lookup"><span data-stu-id="c6a29-296">6. Save the Report to a SharePoint Library</span></span>  
 <span data-ttu-id="c6a29-297">É possível salvar o relatório em um biblioteca do SharePoint, em um servidor de relatório ou no computador.</span><span class="sxs-lookup"><span data-stu-id="c6a29-297">You can save the report to a SharePoint library, report server, or your computer.</span></span> <span data-ttu-id="c6a29-298">Se você salvar o relatório no computador, vários recursos do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , como partes do relatório e sub-relatórios, não estarão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c6a29-298">If you save the report to your computer, a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features such as report parts and subreports are not available.</span></span> <span data-ttu-id="c6a29-299">Neste tutorial, você salvará o relatório em uma biblioteca do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c6a29-299">In this tutorial, you will save the report to a SharePoint library.</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="c6a29-300">Para salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="c6a29-300">To save the report</span></span>  
  
1.  <span data-ttu-id="c6a29-301">No botão Construtor de Relatórios, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-301">From the Report Builder button, click **Save**.</span></span> <span data-ttu-id="c6a29-302">A caixa de diálogo **Salvar como Relatório** é aberta.</span><span class="sxs-lookup"><span data-stu-id="c6a29-302">The **Save As Report** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c6a29-303">Se você estiver salvando um relatório de novo, ele será salvo novamente automaticamente em seu local anterior.</span><span class="sxs-lookup"><span data-stu-id="c6a29-303">If you are resaving a report, it is automatically resaved to its previous location.</span></span> <span data-ttu-id="c6a29-304">Para alterar o local, use a opção **Salvar Como** .</span><span class="sxs-lookup"><span data-stu-id="c6a29-304">To change the location, use the **Save As** option.</span></span>  
  
2.  <span data-ttu-id="c6a29-305">Para mostrar uma lista de servidores de relatório e sites do SharePoint usados recentemente, clique em **Sites e Servidores Recentes**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-305">To show a list of recently used report servers and SharePoint sites, click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="c6a29-306">Selecione ou digite o nome do site do SharePoint onde você tem permissão para salvar relatórios.</span><span class="sxs-lookup"><span data-stu-id="c6a29-306">Select or type the name of the SharePoint site where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="c6a29-307">A URL da biblioteca do SharePoint tem a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c6a29-307">The URL of the SharePoint library has the following syntax:</span></span>  
  
    ```  
    Http://<ServerName>/<Sites>/  
    ```  
  
4.  <span data-ttu-id="c6a29-308">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-308">Click **Save**.</span></span>  
  
     <span data-ttu-id="c6a29-309">**Sites e Servidores Recentes** lista as bibliotecas no site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c6a29-309">**Recent Sites and Servers** lists the libraries on the SharePoint site.</span></span>  
  
5.  <span data-ttu-id="c6a29-310">Navegue para a biblioteca onde você salvará o relatório.</span><span class="sxs-lookup"><span data-stu-id="c6a29-310">Navigate to the library where you will save the report.</span></span>  
  
6.  <span data-ttu-id="c6a29-311">Na caixa **Nome** , substitua o nome padrão por **ResellerVSOnlineDrillthrough**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-311">In the **Name** box, replace the default name with **ResellerVSOnlineDrillthrough**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c6a29-312">Você salvará o relatório principal no mesmo local.</span><span class="sxs-lookup"><span data-stu-id="c6a29-312">You will save the main report to the same location.</span></span> <span data-ttu-id="c6a29-313">Se desejar salvar os relatórios principal e de detalhamento em sites ou bibliotecas diferentes, você deverá atualizar o caminho da ação **Ir para o relatório** no relatório principal.</span><span class="sxs-lookup"><span data-stu-id="c6a29-313">If you want to save the main and drillthrough reports to different sites or libraries, you must update the path of the **Go to report** action in the main report.</span></span>  
  
7.  <span data-ttu-id="c6a29-314">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-314">Click **Save**.</span></span>  
  
##  <a name="1-create-a-new-report-from-the-table-or-matrix-wizard"></a><a name="MMatrixAndDataset"></a><span data-ttu-id="c6a29-315">1. criar um novo relatório por meio do assistente de tabela ou matriz</span><span class="sxs-lookup"><span data-stu-id="c6a29-315">1. Create a New Report from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="c6a29-316">Na caixa de diálogo **Introdução** , crie um relatório de matriz por meio do **Assistente de Tabela ou Matriz**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-316">From the **Getting Started** dialog box, create a matrix report by using the **Table or Matrix Wizard**.</span></span>  
  
#### <a name="to-create-a-new-report"></a><span data-ttu-id="c6a29-317">Para criar um novo relatório</span><span class="sxs-lookup"><span data-stu-id="c6a29-317">To create a new report</span></span>  
  
1.  <span data-ttu-id="c6a29-318">Clique em **Iniciar**, aponte para **programas**, aponte para [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Construtor de relatórios**e, em seguida, clique em **Construtor de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-318">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Report Builder**, and then click **Report Builder**.</span></span>  
  
2.  <span data-ttu-id="c6a29-319">Na caixa de diálogo **Introdução** , verifique se a opção **Novo Relatório** está selecionada e clique em **Assistente de Tabela ou Matriz**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-319">In the **Getting Started** dialog box, verify that **New Report** is selected, and then click **Table or Matrix Wizard**.</span></span>  
  
##  <a name="1a-specify-a-data-connection"></a><a name="MConnection"></a><span data-ttu-id="c6a29-320">1a.</span><span class="sxs-lookup"><span data-stu-id="c6a29-320">1a.</span></span> <span data-ttu-id="c6a29-321">Especificar uma conexão de dados</span><span class="sxs-lookup"><span data-stu-id="c6a29-321">Specify a Data Connection</span></span>  
 <span data-ttu-id="c6a29-322">Você adicionará uma fonte de dados inserida ao relatório principal.</span><span class="sxs-lookup"><span data-stu-id="c6a29-322">You will add an embedded data source to the main report.</span></span>  
  
#### <a name="to-create-an-embedded-data-source"></a><span data-ttu-id="c6a29-323">Para criar uma fonte de dados inserida</span><span class="sxs-lookup"><span data-stu-id="c6a29-323">To create an embedded data source</span></span>  
  
1.  <span data-ttu-id="c6a29-324">Na página **Escolher um conjunto de dados** , selecione **Criar um conjunto de dados**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-324">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="c6a29-325">Clique em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-325">Click **New**.</span></span>  
  
3.  <span data-ttu-id="c6a29-326">Em **Nome**, digite **Principal de Vendas Online e do Revendedor** como o nome da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c6a29-326">In **Name**, type **Online and Reseller Sales Main** as the name for the data source.</span></span>  
  
4.  <span data-ttu-id="c6a29-327">Em **Selecione um tipo de conexão**, selecione **Microsoft SQL Server Analysis Services**e clique em **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-327">In **Select a connection type**, select **Microsoft SQL Server Analysis Services**, and then click **Build**.</span></span>  
  
5.  <span data-ttu-id="c6a29-328">Em **Fonte de dados**, verifique se a fonte de dados é **Microsoft SQL Server Analysis Services (AdomdClient)**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-328">In **Data source**, verify that the data source is **Microsoft SQL Server Analysis Services (AdomdClient)**.</span></span>  
  
6.  <span data-ttu-id="c6a29-329">Em **nome do servidor**, digite o nome de um servidor em que uma instância do [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] está instalada.</span><span class="sxs-lookup"><span data-stu-id="c6a29-329">In **Server name**, type the name of a server where an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] is installed.</span></span>  
  
7.  <span data-ttu-id="c6a29-330">Em **Selecionar ou inserir um nome de banco de dados**, selecione o cubo Contoso.</span><span class="sxs-lookup"><span data-stu-id="c6a29-330">In **Select or enter a database name**, select the Contoso cube.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="c6a29-331">Verifique se a **Cadeia de conexão** contém a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c6a29-331">Verify that the **Connection string** contains the following syntax:</span></span>  
  
    ```  
    Data Source=<servername>; Initial Catalog = Contoso  
    ```  
  
10. <span data-ttu-id="c6a29-332">Clique em **Tipo de credenciais**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-332">Click **Credentials type**.</span></span>  
  
     <span data-ttu-id="c6a29-333">Dependendo de como as permissões estão configuradas na fonte de dados, poderá ser necessário alterar a autenticação padrão.</span><span class="sxs-lookup"><span data-stu-id="c6a29-333">Depending on how permissions are configured on the data source, you might need to change the default authentication.</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
12. <span data-ttu-id="c6a29-334">Para verificar se é possível se conectar à fonte de dados, clique em **Testar Conexão**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-334">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
13. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
14. <span data-ttu-id="c6a29-335">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-335">Click **Next**.</span></span>  
  
##  <a name="1b-create-an-mdx-query"></a><a name="MMDXQuery"></a><span data-ttu-id="c6a29-336">1B.</span><span class="sxs-lookup"><span data-stu-id="c6a29-336">1b.</span></span> <span data-ttu-id="c6a29-337">Criar uma consulta MDX</span><span class="sxs-lookup"><span data-stu-id="c6a29-337">Create an MDX Query</span></span>  
 <span data-ttu-id="c6a29-338">Em seguida, crie um conjunto de dados inserido.</span><span class="sxs-lookup"><span data-stu-id="c6a29-338">Next, create an embedded dataset.</span></span> <span data-ttu-id="c6a29-339">Para fazer isso, você usará o designer de consulta para criar filtros, parâmetros e membros calculados como também o próprio conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="c6a29-339">To do so, you will use the query designer to create filters, parameters, and calculated members as well as the dataset itself.</span></span>  
  
#### <a name="to-create-query-filters"></a><span data-ttu-id="c6a29-340">Para criar filtros de consulta</span><span class="sxs-lookup"><span data-stu-id="c6a29-340">To create query filters</span></span>  
  
1.  <span data-ttu-id="c6a29-341">Na página **criar uma consulta** , no painel metadados, na seção cubo, clique nas reticências **(...)**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-341">On the **Design a query** page, in the Metadata pane, in the cube section, click the ellipsis **(...)**.</span></span>  
  
2.  <span data-ttu-id="c6a29-342">Na caixa de diálogo **Seleção de Cubo** , clique em Vendas e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-342">In the **Cube Selection** dialog box, click Sales, and then click **OK**.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="c6a29-343">Se não desejar criar a consulta MDX manualmente, clique no ícone ![Alternar para modo de Design](media/rsqdicon-designmode.gif "Alterna para o modo de design"), ative/desative o designer de consultas para o modo de Consulta, cole o MDX concluído no designer de consultas e vá para a etapa 5 em [Para criar o conjunto de dados](#MSkip).</span><span class="sxs-lookup"><span data-stu-id="c6a29-343">If you do not want to build the MDX query manually, click the ![Switch to Design mode](media/rsqdicon-designmode.gif "Switch to Design mode") icon, toggle the query designer to Query mode, paste the completed MDX to the query designer, and then proceed to step 5 in [To create the dataset](#MSkip).</span></span>  
  
    ```  
    WITH MEMBER [Measures].[Net QTY] AS [Measures].[Sales Quantity] -[Measures].[Sales Return Quantity] MEMBER [Measures].[Net Sales] AS [Measures].[Sales Amount] - [Measures].[Sales Return Amount] SELECT NON EMPTY { [Measures].[Net QTY], [Measures].[Net Sales] } ON COLUMNS, NON EMPTY { ([Channel].[Channel Name].[Channel Name].ALLMEMBERS * [Product].[Product Category Name].[Product Category Name].ALLMEMBERS ) } DIMENSION PROPERTIES MEMBER_CAPTION, MEMBER_UNIQUE_NAME ON ROWS FROM ( SELECT ( { [Date].[Calendar Year].&[2009] } ) ON COLUMNS FROM ( SELECT ( STRTOSET(@ProductProductCategoryName, CONSTRAINED) ) ON COLUMNS FROM ( SELECT ( { [Sales Territory].[Sales Territory Group].&[North America] } ) ON COLUMNS FROM ( SELECT ( { [Channel].[Channel Name].&[2], [Channel].[Channel Name].&[4] } ) ON COLUMNS FROM [Sales])))) WHERE ( [Sales Territory].[Sales Territory Group].&[North America], [Date].[Calendar Year].&[2009] ) CELL PROPERTIES VALUE, BACK_COLOR, FORE_COLOR, FORMATTED_VALUE, FORMAT_STRING, FONT_NAME, FONT_SIZE, FONT_FLAGSQuery text: Code.  
    ```  
  
3.  <span data-ttu-id="c6a29-344">No painel Grupo de Medidas, expanda Canal e arraste Nome do Canal até a coluna **Hierarquia** no painel de filtro.</span><span class="sxs-lookup"><span data-stu-id="c6a29-344">In the Measure Group pane, expand Channel, and then drag Channel Name to the **Hierarchy** column in the filter pane.</span></span>  
  
     <span data-ttu-id="c6a29-345">O nome da dimensão, Canal, é adicionado automaticamente à coluna **Dimensão** .</span><span class="sxs-lookup"><span data-stu-id="c6a29-345">The dimension name, Channel, is automatically added to the **Dimension** column.</span></span> <span data-ttu-id="c6a29-346">Não altere as colunas **Dimensão** ou **Operador** .</span><span class="sxs-lookup"><span data-stu-id="c6a29-346">Do not change the **Dimension** or **Operator** columns.</span></span>  
  
4.  <span data-ttu-id="c6a29-347">Para abrir a lista **Expressão de Filtro** , clique na seta para baixo na coluna **Expressão de Filtro** .</span><span class="sxs-lookup"><span data-stu-id="c6a29-347">To open the **Filter Expression** list, click the down arrow in the **Filter Expression** column.</span></span>  
  
5.  <span data-ttu-id="c6a29-348">Na lista de expressões de filtro, expanda **Todo o Canal**, clique em **Online** , em **Revendedor**e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-348">In the filter expression list, expand **All Channel**, click **Online** and **Reseller**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="c6a29-349">A consulta agora inclui um filtro para incluir apenas estes canais: Online e Revendedor.</span><span class="sxs-lookup"><span data-stu-id="c6a29-349">The query now includes a filter to include only these channels: Online and Reseller.</span></span>  
  
6.  <span data-ttu-id="c6a29-350">Expanda a dimensão região de vendas e arraste grupo região de vendas para a coluna **hierarquia** , abaixo do **nome do canal**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-350">Expand the Sales Territory dimension, and then drag Sales Territory Group to the **Hierarchy** column, below **Channel Name**.</span></span>  
  
7.  <span data-ttu-id="c6a29-351">Abra a lista **Expressão de Filtro** , expanda **Toda a Região de Vendas**, clique em **América do Norte**e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-351">Open the **Filter Expression** list, expand **All Sales Territory**, click **North America**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="c6a29-352">A consulta agora tem um filtro para incluir apenas vendas na América do Norte.</span><span class="sxs-lookup"><span data-stu-id="c6a29-352">The query now has a filter to include only sales in North America.</span></span>  
  
8.  <span data-ttu-id="c6a29-353">No painel Grupo de Medidas, expanda Data e arraste Ano Civil até a coluna **Hierarquia** no painel de filtro.</span><span class="sxs-lookup"><span data-stu-id="c6a29-353">In the Measure Group pane, expand Date, and drag Calendar Year to the **Hierarchy** column in the filter pane.</span></span>  
  
     <span data-ttu-id="c6a29-354">O nome da dimensão, Data, é adicionado automaticamente à coluna **Dimensão** .</span><span class="sxs-lookup"><span data-stu-id="c6a29-354">The dimension name, Date, is automatically added to the **Dimension** column.</span></span> <span data-ttu-id="c6a29-355">Não altere as colunas **Dimensão** ou **Operador** .</span><span class="sxs-lookup"><span data-stu-id="c6a29-355">Do not change the **Dimension** or **Operator** columns.</span></span>  
  
9. <span data-ttu-id="c6a29-356">Para abrir a lista **Expressão de Filtro** , clique na seta para baixo na coluna **Expressão de Filtro** .</span><span class="sxs-lookup"><span data-stu-id="c6a29-356">To open the **Filter Expression** list, click the down arrow in the **Filter Expression** column.</span></span>  
  
10. <span data-ttu-id="c6a29-357">Na lista de expressões de filtro, expanda **Toda a Data**, clique em **Ano 2009**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-357">In the filter expression list, expand **All Date**, click **Year 2009**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="c6a29-358">A consulta agora inclui um filtro para incluir apenas o ano calendário 2009.</span><span class="sxs-lookup"><span data-stu-id="c6a29-358">The query now includes a filter to include only the calendar year 2009.</span></span>  
  
#### <a name="to-create-the-parameter"></a><span data-ttu-id="c6a29-359">Para criar o parâmetro</span><span class="sxs-lookup"><span data-stu-id="c6a29-359">To create the parameter</span></span>  
  
1.  <span data-ttu-id="c6a29-360">Expanda a dimensão Produto e arraste o membro Nome da Categoria do Produto até a coluna **Hierarquia** , abaixo de **Grupo da Região de Vendas**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-360">Expand the Product dimension, and then drag the Product Category Name member to the **Hierarchy** column below **Sales Territory Group**.</span></span>  
  
2.  <span data-ttu-id="c6a29-361">Abra a lista **Expressão de Filtro** , clique em **Todos os Produtos**e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-361">Open the **Filter Expression** list, click **All Products**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="c6a29-362">Clique na caixa de seleção **Parâmetro** .</span><span class="sxs-lookup"><span data-stu-id="c6a29-362">Click the **Parameter** checkbox.</span></span> <span data-ttu-id="c6a29-363">A consulta agora inclui o parâmetro ProductProductCategoryName.</span><span class="sxs-lookup"><span data-stu-id="c6a29-363">The query now includes the parameter ProductProductCategoryName.</span></span>  
  
#### <a name="to-create-calculated-members"></a><span data-ttu-id="c6a29-364">Para criar membros calculados</span><span class="sxs-lookup"><span data-stu-id="c6a29-364">To create calculated members</span></span>  
  
1.  <span data-ttu-id="c6a29-365">Posicione o cursor no painel Membros Calculados, clique com o botão direito do mouse e clique em **Novo Membro Calculado**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-365">Place the cursor inside the Calculated Members pane, right-click, and then click **New Calculated Member**.</span></span>  
  
2.  <span data-ttu-id="c6a29-366">No painel metadados, expanda **medidas** e, em seguida, vendas.</span><span class="sxs-lookup"><span data-stu-id="c6a29-366">In the Metadata pane, expand **Measures** and then expand Sales.</span></span>  
  
3.  <span data-ttu-id="c6a29-367">Arraste a medida Quantidade de Vendas até a caixa **Expressão** , digite o caractere de subtração (-), arraste a medida Quantidade de Devoluções de Vendas até a caixa **Expressão** e coloque-a após o caractere de subtração.</span><span class="sxs-lookup"><span data-stu-id="c6a29-367">Drag the Sales Quantity measure to the **Expression** box, type the subtraction character (-), and then drag the Sales Return Quantity measure to the **Expression** box; place it after the subtraction character.</span></span>  
  
     <span data-ttu-id="c6a29-368">O código a seguir mostra a expressão:</span><span class="sxs-lookup"><span data-stu-id="c6a29-368">The following code shows the expression:</span></span>  
  
    ```  
    [Measures].[Sales Quantity] - [Measures].[Sales Return Quantity]  
    ```  
  
4.  <span data-ttu-id="c6a29-369">Na caixa Nome, digite **Qtd Líquida**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-369">In the Name box, type **Net QTY**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="c6a29-370">O painel Membros Calculados lista o membro calculado **Qtd Líquida** .</span><span class="sxs-lookup"><span data-stu-id="c6a29-370">The Calculated Members pane lists the **Net QTY** calculated member.</span></span>  
  
5.  <span data-ttu-id="c6a29-371">Clique com o botão direito do mouse em **Membros Calculados**e clique em **Novo Membro Calculado**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-371">Right-click **Calculated Members**, and then click **New Calculated Member**.</span></span>  
  
6.  <span data-ttu-id="c6a29-372">No painel Metadados, expanda **Medidas**e Vendas.</span><span class="sxs-lookup"><span data-stu-id="c6a29-372">In the Metadata pane, expand **Measures**, and then expand Sales.</span></span>  
  
7.  <span data-ttu-id="c6a29-373">Arraste a medida Valor das Vendas até a caixa **Expressão** , digite o caractere de subtração (-), arraste a medida Valor de Devolução das Vendas até a caixa **Expressão** e coloque-a após o caractere de subtração.</span><span class="sxs-lookup"><span data-stu-id="c6a29-373">Drag the Sales Amount measure to the **Expression** box, type the subtraction character (-), and then drag the Sales Return Amount measure to the **Expression** box; place it after the subtraction character.</span></span>  
  
     <span data-ttu-id="c6a29-374">O código a seguir mostra a expressão:</span><span class="sxs-lookup"><span data-stu-id="c6a29-374">The following code shows the expression:</span></span>  
  
    ```  
    [Measures].[Sales Amount] - [Measures].[Sales Return Amount]  
    ```  
  
8.  <span data-ttu-id="c6a29-375">Na caixa **Nome** , digite  **Vendas Líquidas**e clique em **OK**. O painel Membros Calculados lista o membro calculado **Vendas Líquidas** .</span><span class="sxs-lookup"><span data-stu-id="c6a29-375">In the **Name** box, type  **Net Sales**, and then click **OK**.The Calculated Members pane lists the **Net Sales** calculated member.</span></span>  
  
###  <a name="to-create-the-dataset"></a><a name="MSkip"></a><span data-ttu-id="c6a29-376">Para criar o conjunto de um</span><span class="sxs-lookup"><span data-stu-id="c6a29-376">To create the dataset</span></span>  
  
1.  <span data-ttu-id="c6a29-377">Na dimensão Canal, arraste Nome do Canal até o painel de dados.</span><span class="sxs-lookup"><span data-stu-id="c6a29-377">From the Channel dimension, drag Channel Name to the data pane.</span></span>  
  
2.  <span data-ttu-id="c6a29-378">Na dimensão Produto, arraste Nome da Categoria do Produto até o painel de dados e coloque-o à direita de Nome do Canal.</span><span class="sxs-lookup"><span data-stu-id="c6a29-378">From the Product dimension, drag Product Category Name to the data pane, and then place it to the right of Channel Name.</span></span>  
  
3.  <span data-ttu-id="c6a29-379">Em **Membros Calculados**, arraste `Net QTY` até o painel de dados e coloque-o à direita de Nome da Categoria do Produto.</span><span class="sxs-lookup"><span data-stu-id="c6a29-379">From **Calculated Members**, drag `Net QTY` to the data pane, and then place it to the right of Product Category Name.</span></span>  
  
4.  <span data-ttu-id="c6a29-380">Em Membros Calculados, arraste Vendas Líquidas até o painel de dados e coloque-o à direita de `Net QTY`.</span><span class="sxs-lookup"><span data-stu-id="c6a29-380">From Calculated Members, drag Net Sales to the data pane, and then place it to the right of `Net QTY`.</span></span>  
  
5.  <span data-ttu-id="c6a29-381">Na barra de ferramentas do designer de consultas, clique em **executar (!)**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-381">On the query designer toolbar, click **Run (!)**.</span></span>  
  
     <span data-ttu-id="c6a29-382">Revise o conjunto de resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="c6a29-382">Review the query result set.</span></span>  
  
6.  <span data-ttu-id="c6a29-383">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-383">Click **Next**.</span></span>  
  
##  <a name="1c-organize-data-into-groups"></a><a name="MLayout"></a><span data-ttu-id="c6a29-384">1C.</span><span class="sxs-lookup"><span data-stu-id="c6a29-384">1c.</span></span> <span data-ttu-id="c6a29-385">Organizar dados em grupos</span><span class="sxs-lookup"><span data-stu-id="c6a29-385">Organize Data into Groups</span></span>  
 <span data-ttu-id="c6a29-386">Quando seleciona os campos nos quais agrupar os dados, você cria uma matriz com linhas e colunas que exibe dados detalhados e dados agregados.</span><span class="sxs-lookup"><span data-stu-id="c6a29-386">When you select the fields on which to group data, you design a matrix with rows and columns that displays detail and aggregated data.</span></span>  
  
#### <a name="to-organize-data-into-groups"></a><span data-ttu-id="c6a29-387">Para organizar dados em grupos</span><span class="sxs-lookup"><span data-stu-id="c6a29-387">To organize data into groups</span></span>  
  
1.  <span data-ttu-id="c6a29-388">Na página **Organizar campos** , arraste Product_Category_Name até **Grupos de linhas**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-388">On the **Arrange fields** page, drag Product_Category_Name to **Row groups**.</span></span>  
  
2.  <span data-ttu-id="c6a29-389">Arraste Channel_Name até **Grupos de colunas**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-389">Drag Channel_Name to **Column groups**.</span></span>  
  
3.  <span data-ttu-id="c6a29-390">Arraste `Net_QTY` até **Valores**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-390">Drag `Net_QTY` to **Values**.</span></span>  
  
     <span data-ttu-id="c6a29-391">`Net_QTY` é agregado automaticamente pela função Sum, a agregação padrão para campos numéricos.</span><span class="sxs-lookup"><span data-stu-id="c6a29-391">`Net_QTY` is automatically aggregated by the Sum function, the default aggregate for numeric fields.</span></span> <span data-ttu-id="c6a29-392">O valor é `[Sum(Net_QTY)]`.</span><span class="sxs-lookup"><span data-stu-id="c6a29-392">The value is `[Sum(Net_QTY)]`.</span></span>  
  
     <span data-ttu-id="c6a29-393">Para exibir outras funções de agregação disponíveis, abra a lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="c6a29-393">To view the other aggregate functions available, open the drop-down list.</span></span> <span data-ttu-id="c6a29-394">Não altere a função de agregação.</span><span class="sxs-lookup"><span data-stu-id="c6a29-394">Do not change the aggregate function.</span></span>  
  
4.  <span data-ttu-id="c6a29-395">Arraste `Net_Sales_Return` até **Valores** e coloque-o abaixo de `[Sum(Net_QTY)]`.</span><span class="sxs-lookup"><span data-stu-id="c6a29-395">Drag `Net_Sales_Return` to **Values** and then place it below `[Sum(Net_QTY)]`.</span></span>  
  
     <span data-ttu-id="c6a29-396">As etapas 3 e 4 especificam os dados a serem exibidos na matriz.</span><span class="sxs-lookup"><span data-stu-id="c6a29-396">Steps 3 and 4 specify the data to display in the matrix.</span></span>  
  
##  <a name="1d-add-subtotals-and-totals"></a><a name="MTotals"></a><span data-ttu-id="c6a29-397">1D.</span><span class="sxs-lookup"><span data-stu-id="c6a29-397">1d.</span></span> <span data-ttu-id="c6a29-398">Adicionar subtotais e totais</span><span class="sxs-lookup"><span data-stu-id="c6a29-398">Add Subtotals and Totals</span></span>  
 <span data-ttu-id="c6a29-399">Você pode mostrar subtotais e totais gerais em relatórios.</span><span class="sxs-lookup"><span data-stu-id="c6a29-399">You can show subtotals and grand totals in reports.</span></span> <span data-ttu-id="c6a29-400">Os dados no relatório principal são exibidos como um indicador; você removerá o total geral depois de concluir o assistente.</span><span class="sxs-lookup"><span data-stu-id="c6a29-400">The data in the main report displays as an indicator; you will remove the grand total after you complete the wizard.</span></span>  
  
#### <a name="to-add-subtotals-and-grand-totals"></a><span data-ttu-id="c6a29-401">Para adicionar subtotais e totais gerais</span><span class="sxs-lookup"><span data-stu-id="c6a29-401">To add subtotals and grand totals</span></span>  
  
1.  <span data-ttu-id="c6a29-402">Na página **escolher o layout** , em opções, verifique se a **opção** **Mostrar Subtotais e totais gerais** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="c6a29-402">On the **Choose the layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
     <span data-ttu-id="c6a29-403">O painel Visualizar do assistente exibe uma matriz com quatro linhas.</span><span class="sxs-lookup"><span data-stu-id="c6a29-403">The wizard Preview pane displays a matrix with four rows.</span></span>  <span data-ttu-id="c6a29-404">Quando você executar o relatório, cada linha será exibida da seguinte maneira: a primeira linha é o grupo de colunas, a segunda linha contém os títulos das colunas, a terceira linha contém os dados da categoria do produto (`[Sum(Net_ QTY)]` e `[Sum(Net_Sales)]`) e a quarta linha contém os totais.</span><span class="sxs-lookup"><span data-stu-id="c6a29-404">When you run the report, each row will display in the following way: The first row is the column group, the second row contains the column headings, the third row contains the product category data (`[Sum(Net_ QTY)]` and `[Sum(Net_Sales)]`, and the fourth row contains the totals.</span></span>  
  
2.  <span data-ttu-id="c6a29-405">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-405">Click **Next**.</span></span>  
  
##  <a name="1e-choose-a-style"></a><a name="MStyle"></a><span data-ttu-id="c6a29-406">1e.</span><span class="sxs-lookup"><span data-stu-id="c6a29-406">1e.</span></span> <span data-ttu-id="c6a29-407">Escolha um estilo</span><span class="sxs-lookup"><span data-stu-id="c6a29-407">Choose a Style</span></span>  
 <span data-ttu-id="c6a29-408">Aplique o estilo Ardósia ao relatório.</span><span class="sxs-lookup"><span data-stu-id="c6a29-408">Apply the Slate style to the report.</span></span> <span data-ttu-id="c6a29-409">Esse é o mesmo estilo usado pelo relatório detalhado.</span><span class="sxs-lookup"><span data-stu-id="c6a29-409">This is the same style that the drillthrough report uses.</span></span>  
  
#### <a name="to-specify-a-style"></a><span data-ttu-id="c6a29-410">Para especificar um estilo</span><span class="sxs-lookup"><span data-stu-id="c6a29-410">To specify a style</span></span>  
  
1.  <span data-ttu-id="c6a29-411">Na página **escolher um estilo** , no painel estilos, selecione Slate.</span><span class="sxs-lookup"><span data-stu-id="c6a29-411">On the **Choose a Style** page, in the Styles pane, select Slate.</span></span>  
  
2.  <span data-ttu-id="c6a29-412">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-412">Click **Finish**.</span></span>  
  
3.  <span data-ttu-id="c6a29-413">Para visualizar o relatório, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-413">To preview the report, click **Run**.</span></span>  
  
##  <a name="2-remove-the-grand-total-row"></a><a name="MGrandTotal"></a><span data-ttu-id="c6a29-414">2. remover a linha de total geral</span><span class="sxs-lookup"><span data-stu-id="c6a29-414">2. Remove the Grand Total Row</span></span>  
 <span data-ttu-id="c6a29-415">Os valores de dados são mostrados como estados do indicador, inclusive o totais dos grupos de colunas.</span><span class="sxs-lookup"><span data-stu-id="c6a29-415">The data values are shown as indictor states, including the column group totals.</span></span> <span data-ttu-id="c6a29-416">Remova a linha que exibe o total geral.</span><span class="sxs-lookup"><span data-stu-id="c6a29-416">Remove the row that displays the grand total.</span></span>  
  
#### <a name="to-remove-the-grand-total-row"></a><span data-ttu-id="c6a29-417">Para remover a linha de total geral</span><span class="sxs-lookup"><span data-stu-id="c6a29-417">To remove the grand total row</span></span>  
  
1.  <span data-ttu-id="c6a29-418">Para mudar para o modo design, clique em **Design**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-418">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="c6a29-419">Clique na linha Total (a última linha da matriz), clique com o botão direito do mouse e clique em **Excluir Linhas**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-419">Click the Total row (the last row in the matrix), right-click, and then click **Delete Rows**.</span></span>  
  
3.  <span data-ttu-id="c6a29-420">Para visualizar o relatório, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-420">To preview the report, click **Run**.</span></span>  
  
##  <a name="3-configure-text-box-action-for-drillthrough"></a><a name="MDrillthrough"></a><span data-ttu-id="c6a29-421">3. Configurar ação da caixa de texto para detalhamento</span><span class="sxs-lookup"><span data-stu-id="c6a29-421">3. Configure Text Box Action for Drillthrough</span></span>  
 <span data-ttu-id="c6a29-422">Para habilitar o detalhamento, especifique uma ação em uma caixa de texto no relatório principal.</span><span class="sxs-lookup"><span data-stu-id="c6a29-422">To enable the drillthrough, specify an action on a text box in the main report.</span></span>  
  
#### <a name="to-enable-an-action"></a><span data-ttu-id="c6a29-423">Para habilitar uma ação</span><span class="sxs-lookup"><span data-stu-id="c6a29-423">To enable an action</span></span>  
  
1.  <span data-ttu-id="c6a29-424">Para mudar para o modo design, clique em **Design**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-424">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="c6a29-425">Clique com o botão direito do mouse na célula que contém Product_Category_Name e clique em **Propriedades da Caixa de Texto**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-425">Right-click the cell that contains Product_Category_Name, and then click **Text Box Properties**.</span></span>  
  
3.  <span data-ttu-id="c6a29-426">Clique na guia **Ações**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-426">Click the **Action** tab.</span></span>  
  
4.  <span data-ttu-id="c6a29-427">Selecione **ir para o relatório.**</span><span class="sxs-lookup"><span data-stu-id="c6a29-427">Select **Go to report.**</span></span>  
  
5.  <span data-ttu-id="c6a29-428">Em **Especificar um relatório**, clique em **Procurar**e localize o relatório de detalhamento chamado ResellerVSOnlineDrillthrough.</span><span class="sxs-lookup"><span data-stu-id="c6a29-428">In **Specify a report**, click **Browse**, and then locate the drillthrough report named ResellerVSOnlineDrillthrough.</span></span>  
  
6.  <span data-ttu-id="c6a29-429">Para adicionar um parâmetro para executar o relatório de detalhamento, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-429">To add a parameter to run the drillthrough report, click **Add**.</span></span>  
  
7.  <span data-ttu-id="c6a29-430">Na lista **Nome** , selecione ProductProductCategoryName.</span><span class="sxs-lookup"><span data-stu-id="c6a29-430">In the **Name** list, select ProductProductCategoryName.</span></span>  
  
8.  <span data-ttu-id="c6a29-431">Em **Valor**, digite `[Product_Category_Name.UniqueName]`.</span><span class="sxs-lookup"><span data-stu-id="c6a29-431">In **Value**, type `[Product_Category_Name.UniqueName]`.</span></span>  
  
     <span data-ttu-id="c6a29-432">Product_Category_Name é um campo do conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="c6a29-432">Product_Category_Name is a field in the dataset.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="c6a29-433">Você deve incluir a propriedade `UniqueName` porque a ação de detalhamento exige um valor exclusivo.</span><span class="sxs-lookup"><span data-stu-id="c6a29-433">You must include the `UniqueName` property because the drillthrough action requires a unique value.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-format-the-drillthrough-field"></a><span data-ttu-id="c6a29-434">Para formatar o campo de detalhamento</span><span class="sxs-lookup"><span data-stu-id="c6a29-434">To format the drillthrough field</span></span>  
  
1.  <span data-ttu-id="c6a29-435">Clique com o botão direito do mouse na célula que contém o `Product_Category_Name`e clique em **Propriedades da Caixa de Texto**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-435">Right-click the cell that contains the `Product_Category_Name`, and then click **Text Box Properties**.</span></span>  
  
2.  <span data-ttu-id="c6a29-436">Clique na guia **Fonte** .</span><span class="sxs-lookup"><span data-stu-id="c6a29-436">Click the **Font** tab.</span></span>  
  
3.  <span data-ttu-id="c6a29-437">Na lista **Efeitos** , selecione **Sublinhar**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-437">In the **Effects** list, select **Underline**.</span></span>  
  
4.  <span data-ttu-id="c6a29-438">Na lista **Cor** , selecione **Azul**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-438">In the **Color** list, select **Blue**.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="c6a29-439">Para visualizar o relatório, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-439">To preview your report, click **Run**.</span></span>  
  
 <span data-ttu-id="c6a29-440">Os nomes das categorias de produto estão no formato de link comum (azul e sublinhado).</span><span class="sxs-lookup"><span data-stu-id="c6a29-440">The product category names are in the common link format (blue and underlined).</span></span>  
  
##  <a name="4-replace-numeric-values-with-indicators"></a><a name="MIndicators"></a><span data-ttu-id="c6a29-441">4. substituir valores numéricos por indicadores</span><span class="sxs-lookup"><span data-stu-id="c6a29-441">4. Replace Numeric Values with Indicators</span></span>  
 <span data-ttu-id="c6a29-442">Use indicadores para mostrar o estado de quantidades e vendas dos canais Online e de Revendedor.</span><span class="sxs-lookup"><span data-stu-id="c6a29-442">Use indicators to show the state of quantities and sales for Online and Reseller channels.</span></span>  
  
#### <a name="to-add-an-indicator-for-net-qty-values"></a><span data-ttu-id="c6a29-443">Para adicionar um indicador para valores de QTD Líquida</span><span class="sxs-lookup"><span data-stu-id="c6a29-443">To add an indicator for Net QTY values</span></span>  
  
1.  <span data-ttu-id="c6a29-444">Para mudar para o modo design, clique em **Design**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-444">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="c6a29-445">Na faixa de opções, clique no ícone **Retângulo** e clique na célula `[Sum(Net QTY)]` do grupo de linhas `[Product_Category_Name]` no grupo de colunas `Channel_Name` .</span><span class="sxs-lookup"><span data-stu-id="c6a29-445">On the ribbon, click the **Rectangle** icon, and then click in the `[Sum(Net QTY)]` cell in the `[Product_Category_Name]` row group in the `Channel_Name` column group.</span></span>  
  
3.  <span data-ttu-id="c6a29-446">Na faixa de opções, clique no ícone **Indicador** e clique dentro do retângulo.</span><span class="sxs-lookup"><span data-stu-id="c6a29-446">On the ribbon, click the **Indicator** icon, and then click inside the rectangle.</span></span> <span data-ttu-id="c6a29-447">A caixa de diálogo **Selecionar Tipo de Indicador** é aberta com o indicador **Direcional** selecionado.</span><span class="sxs-lookup"><span data-stu-id="c6a29-447">The **Select Indicator Type** dialog box opens with the **Directional** indicator selected.</span></span>  
  
4.  <span data-ttu-id="c6a29-448">Clique no tipo **3 Sinais** e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-448">Click the **3 Signs** type, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="c6a29-449">Clique com o botão direito do mouse no indicador e, no painel Dados do Medidor, clique na seta para baixo ao lado de **(Não especificado)**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-449">Right-click the indicator and in the Gauge Data pane, click the down arrow next to **(Unspecified)**.</span></span> <span data-ttu-id="c6a29-450">Selecione `Net_QTY`.</span><span class="sxs-lookup"><span data-stu-id="c6a29-450">Select `Net_QTY`.</span></span>  
  
6.  <span data-ttu-id="c6a29-451">Repita as etapas 2 a 5 para a célula `[Sum(Net QTY)]` no grupo de linhas `[Product_Category_Name]` dentro de **Total**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-451">Repeat steps 2 through 5 for the `[Sum(Net QTY)]` cell in the `[Product_Category_Name]` row group within **Total**.</span></span>  
  
#### <a name="to-add-an-indicator-for-net-sales-values"></a><span data-ttu-id="c6a29-452">Para adicionar um indicador para valores de Vendas Líquidas</span><span class="sxs-lookup"><span data-stu-id="c6a29-452">To add an indicator for Net Sales values</span></span>  
  
1.  <span data-ttu-id="c6a29-453">Na faixa de opções, clique no ícone **Retângulo** e clique dentro da célula `[Sum(Net_Sales)]` no grupo de linhas `[Product_Category_Name]` do grupo de colunas `Channel_Name` .</span><span class="sxs-lookup"><span data-stu-id="c6a29-453">On the ribbon, click the **Rectangle** icon, and then click inside the `[Sum(Net_Sales)]` cell in the `[Product_Category_Name]` row group in the `Channel_Name` column group.</span></span>  
  
2.  <span data-ttu-id="c6a29-454">Na faixa de opções, clique no ícone **Indicador** e clique dentro do retângulo.</span><span class="sxs-lookup"><span data-stu-id="c6a29-454">On the ribbon, click the **Indicator** icon, and then click inside the rectangle.</span></span>  
  
3.  <span data-ttu-id="c6a29-455">Clique no tipo **3 Sinais** e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-455">Click the **3 Signs** type, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="c6a29-456">Clique com o botão direito do mouse no indicador e, no painel Dados do Medidor, clique na seta para baixo ao lado de **(Não especificado)**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-456">Right-click the indicator and in the Gauge Data pane, click the down arrow next to **(Unspecified)**.</span></span> <span data-ttu-id="c6a29-457">Selecione `Net_Sales`.</span><span class="sxs-lookup"><span data-stu-id="c6a29-457">Select `Net_Sales`.</span></span>  
  
5.  <span data-ttu-id="c6a29-458">Repita as etapas 1 a 4 para a célula `[Sum(Net_Sales)]` no grupo de linhas `[Product_Category_Name]` dentro de **Total**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-458">Repeat steps 1 through 4 for the `[Sum(Net_Sales)]` cell in the `[Product_Category_Name]` row group within **Total**.</span></span>  
  
6.  <span data-ttu-id="c6a29-459">Para visualizar o relatório, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-459">To preview your report, click **Run**.</span></span>  
  
##  <a name="5-update-parameter-properties"></a><a name="MParameter"></a><span data-ttu-id="c6a29-460">5. atualizar propriedades do parâmetro</span><span class="sxs-lookup"><span data-stu-id="c6a29-460">5. Update Parameter Properties</span></span>  
 <span data-ttu-id="c6a29-461">Por padrão, os parâmetros estão visíveis, o que não é apropriado para este relatório.</span><span class="sxs-lookup"><span data-stu-id="c6a29-461">By default, parameters are visible, which is not appropriate for this report.</span></span> <span data-ttu-id="c6a29-462">Você atualizará as propriedades dos parâmetros para tornar os parâmetros internos.</span><span class="sxs-lookup"><span data-stu-id="c6a29-462">You will update the parameter properties to make the parameter internal.</span></span>  
  
#### <a name="to-make-the-parameter-internal"></a><span data-ttu-id="c6a29-463">Para tornar o parâmetro interno</span><span class="sxs-lookup"><span data-stu-id="c6a29-463">To make the parameter internal</span></span>  
  
1.  <span data-ttu-id="c6a29-464">No painel Dados do Relatório, expanda **Parâmetros**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-464">In the Report Data pane, expand **Parameters**.</span></span>  
  
2.  <span data-ttu-id="c6a29-465">Clique com o botão direito do mouse em `@ProductProductCategoryName,` e clique em **Propriedades do Parâmetro**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-465">Right-click `@ProductProductCategoryName,` and then click **Parameter Properties**.</span></span>  
  
3.  <span data-ttu-id="c6a29-466">Na guia **Geral** , clique em **Interno**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-466">On the **General** tab, click **Internal**.</span></span>  
  
4.  <span data-ttu-id="c6a29-467">Opcionalmente, clique nas guias **Valores Disponíveis** e **Valores Padrão** e examine as opções.</span><span class="sxs-lookup"><span data-stu-id="c6a29-467">Optionally, click the **Available Values** and **Default Values** tabs and review their options.</span></span> <span data-ttu-id="c6a29-468">Não altere nenhuma opção nessas guias.</span><span class="sxs-lookup"><span data-stu-id="c6a29-468">Do not change any options on these tabs.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="6-add-a-report-title"></a><a name="MTitle"></a><span data-ttu-id="c6a29-469">6. adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="c6a29-469">6. Add a Report Title</span></span>  
 <span data-ttu-id="c6a29-470">Adicione um título ao relatório principal.</span><span class="sxs-lookup"><span data-stu-id="c6a29-470">Add a title to the main report.</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="c6a29-471">Para adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="c6a29-471">To add a report title</span></span>  
  
1.  <span data-ttu-id="c6a29-472">Na superfície de design, clique em **Clique para adicionar título**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-472">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="c6a29-473">Digite **Vendas de Categorias de Produtos de 2009: Categoria Online e Revendedor:**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-473">Type **2009 Product Category Sales: Online and Reseller Category:**.</span></span>  
  
3.  <span data-ttu-id="c6a29-474">Selecione o texto que você digitou.</span><span class="sxs-lookup"><span data-stu-id="c6a29-474">Select the text you typed.</span></span>  
  
4.  <span data-ttu-id="c6a29-475">Na guia **Início** da faixa de opções, no grupo Fonte, selecione a fonte **Times New Roman** , tamanho **16 pt** e os estilos **Negrito** e **Itálico** .</span><span class="sxs-lookup"><span data-stu-id="c6a29-475">On the **Home** tab of the ribbon, in the Font group, select the **Times New Roman** font, **16pt** size, and the **Bold** and **Italic** styles.</span></span>  
  
5.  <span data-ttu-id="c6a29-476">Para visualizar o relatório, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-476">To preview your report, click **Run**.</span></span>  
  
##  <a name="7-save-the-main-report-to-a-sharepoint-library"></a><a name="MSave"></a><span data-ttu-id="c6a29-477">7. salvar o relatório principal em uma biblioteca do SharePoint</span><span class="sxs-lookup"><span data-stu-id="c6a29-477">7. Save the Main Report to a SharePoint Library</span></span>  
 <span data-ttu-id="c6a29-478">Salve o relatório principal em uma biblioteca do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c6a29-478">Save the main report to a SharePoint library.</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="c6a29-479">Para salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="c6a29-479">To save the report</span></span>  
  
1.  <span data-ttu-id="c6a29-480">Para mudar para o modo design, clique em **Design**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-480">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="c6a29-481">No botão Construtor de Relatórios, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-481">From the Report Builder button, click **Save**.</span></span>  
  
3.  <span data-ttu-id="c6a29-482">Opcionalmente, para mostrar uma lista de servidores de relatório e sites do SharePoint usados recentemente, clique em **Sites e Servidores Recentes**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-482">Optionally, to show a list of recently used report servers and SharePoint sites, click **Recent Sites and Servers**.</span></span>  
  
4.  <span data-ttu-id="c6a29-483">Selecione ou digite o nome do site do SharePoint onde você tem permissão para salvar relatórios.</span><span class="sxs-lookup"><span data-stu-id="c6a29-483">Select or type the name of the SharePoint site where you have permission to save reports.</span></span> <span data-ttu-id="c6a29-484">A URL da biblioteca do SharePoint tem a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c6a29-484">The URL of the SharePoint library has the following syntax:</span></span>  
  
    ```  
    Http://<ServerName>/<Sites>/  
    ```  
  
5.  <span data-ttu-id="c6a29-485">Navegue para a biblioteca onde você deseja salvar o relatório.</span><span class="sxs-lookup"><span data-stu-id="c6a29-485">Navigate to the library where you want to save the report.</span></span>  
  
6.  <span data-ttu-id="c6a29-486">Em **Nome**, substitua o nome padrão por **ResellerVSOnlineMain**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-486">In **Name**, replace the default name with **ResellerVSOnlineMain**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="c6a29-487">Salve o relatório principal no mesmo local onde você salvou o relatório detalhado.</span><span class="sxs-lookup"><span data-stu-id="c6a29-487">Save the main report to the same location where you saved the drillthrough report.</span></span> <span data-ttu-id="c6a29-488">Para salvar os relatórios principal e de detalhamento em sites ou bibliotecas diferentes, confirme se a ação **Ir para o relatório** no relatório principal aponta para o local correto do relatório de detalhamento.</span><span class="sxs-lookup"><span data-stu-id="c6a29-488">To save the main and drillthrough reports to different sites or libraries, confirm that the **Go to report** action in the main report, points to the correct location of the drillthrough report.</span></span>  
  
7.  <span data-ttu-id="c6a29-489">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c6a29-489">Click **Save**.</span></span>  
  
##  <a name="8-run-the-main-and-drillthrough-reports"></a><a name="MRunReports"></a><span data-ttu-id="c6a29-490">8. executar os relatórios principal e de detalhamento</span><span class="sxs-lookup"><span data-stu-id="c6a29-490">8. Run the Main and Drillthrough Reports</span></span>  
 <span data-ttu-id="c6a29-491">Execute o relatório principal e clique nos valores da coluna de categorias de produto para executar o relatório detalhado.</span><span class="sxs-lookup"><span data-stu-id="c6a29-491">Run the main report, and then click values in the product category column to run the drillthrough report.</span></span>  
  
#### <a name="to-run-the-reports"></a><span data-ttu-id="c6a29-492">Para executar os relatórios</span><span class="sxs-lookup"><span data-stu-id="c6a29-492">To run the reports</span></span>  
  
1.  <span data-ttu-id="c6a29-493">Abra a biblioteca do SharePoint onde os relatórios foram salvos.</span><span class="sxs-lookup"><span data-stu-id="c6a29-493">Open the SharePoint library where the reports are saved.</span></span>  
  
2.  <span data-ttu-id="c6a29-494">Clique duas vezes em ResellerVSOnlineMain.</span><span class="sxs-lookup"><span data-stu-id="c6a29-494">Double-click ResellerVSOnlineMain.</span></span>  
  
     <span data-ttu-id="c6a29-495">O relatório é executado e exibe informações de vendas de categorias de produtos.</span><span class="sxs-lookup"><span data-stu-id="c6a29-495">The report runs and displays product category sales information.</span></span>  
  
3.  <span data-ttu-id="c6a29-496">Clique no link **Games and Toys** na coluna que contém nomes de categorias de produto.</span><span class="sxs-lookup"><span data-stu-id="c6a29-496">Click the **Games and Toys** link in the column that contains product category names.</span></span>  
  
     <span data-ttu-id="c6a29-497">O relatório detalhado é executado exibindo apenas os valores da categoria de produto Games and Toys.</span><span class="sxs-lookup"><span data-stu-id="c6a29-497">The drillthrough report runs, displaying only the values for the Games and Toys product category.</span></span>  
  
4.  <span data-ttu-id="c6a29-498">Para retornar ao relatório principal, clique no botão voltar do Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="c6a29-498">To return to the main report, click the Internet Explorer back button.</span></span>  
  
5.  <span data-ttu-id="c6a29-499">Opcionalmente, explore outras categorias de produto clicando nos respectivos nomes.</span><span class="sxs-lookup"><span data-stu-id="c6a29-499">Optionally, explore other product categories by clicking their names.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6a29-500">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c6a29-500">See Also</span></span>  
 [<span data-ttu-id="c6a29-501">TUTORIAIS &#40;Construtor de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="c6a29-501">Tutorials &#40;Report Builder&#41;</span></span>](report-builder-tutorials.md)  
  
  
