---
title: 'Lição 2: adicionar dados | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 13c3a8cc-b1db-4aba-ad9b-038b7971be8d
author: minewiskan
ms.author: owend
ms.openlocfilehash: c844ea6558949407ca9b8206601ff7fe802ec399
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571668"
---
# <a name="lesson-2-add-data"></a><span data-ttu-id="3b0b0-102">Lição 2: Adicionar dados</span><span class="sxs-lookup"><span data-stu-id="3b0b0-102">Lesson 2: Add Data</span></span>
  <span data-ttu-id="3b0b0-103">Nesta lição, você usará o Assistente de Importação de Tabela do [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] para se conectar ao banco de dados SQL AdventureWorksDW, selecionar, visualizar e filtrar os dados, e importá-los para o workspace do modelo.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-103">In this lesson, you will use the Table Import Wizard in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] to connect to the AdventureWorksDW SQL database, select data, preview, and filter the data, and then import the data into your model workspace.</span></span>  
  
 <span data-ttu-id="3b0b0-104">Usando o Assistente de importação de tabela, você pode importar dados de uma variedade de fontes relacionais: Access, SQL, Oracle, Sybase, Informix, DB2, Teradata e muito mais.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-104">By using the Table Import Wizard, you can import data from a variety of relational sources: Access, SQL, Oracle, Sybase, Informix, DB2, Teradata, and more.</span></span> <span data-ttu-id="3b0b0-105">As etapas de importação de dados de cada uma dessas fontes relacionais são bem parecidas com as descritas a seguir.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-105">The steps for importing data from each of these relational sources are very similar to what is described below.</span></span> <span data-ttu-id="3b0b0-106">Além disso, os dados podem ser selecionados por meio de um procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-106">Additionally, data can be selected using a stored procedure.</span></span>  
  
 <span data-ttu-id="3b0b0-107">Para saber mais sobre como importar dados e os diferentes tipos de fontes de dados das quais você pode importar dados, consulte [Fontes de dados &#40;SSAS Tabular&#41;](data-sources-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="3b0b0-107">To learn more about importing data and the different types of data sources you can import from, see [Data Sources &#40;SSAS Tabular&#41;](data-sources-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="3b0b0-108">Tempo estimado para conclusão desta lição: **20 minutos**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-108">Estimated time to complete this lesson: **20 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3b0b0-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="3b0b0-109">Prerequisites</span></span>  
 <span data-ttu-id="3b0b0-110">Este tópico faz parte de um tutorial de modelagem tabular, que deve ser concluído na devida ordem.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-110">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="3b0b0-111">Antes de executar as tarefas nesta lição, você deve ter concluído a lição anterior: [lição 1: criar um novo projeto de modelo de tabela](lesson-1-create-a-new-tabular-model-project.md).</span><span class="sxs-lookup"><span data-stu-id="3b0b0-111">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 1: Create a New Tabular Model Project](lesson-1-create-a-new-tabular-model-project.md).</span></span>  
  
## <a name="create-a-connection"></a><span data-ttu-id="3b0b0-112">Criar uma conexão</span><span class="sxs-lookup"><span data-stu-id="3b0b0-112">Create a Connection</span></span>  
  
#### <a name="to-create-a-connection-to-a-the-adventureworksdw2012-database"></a><span data-ttu-id="3b0b0-113">Para criar uma conexão com um banco de dados AdventureWorksDW2012.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-113">To create a connection to a the AdventureWorksDW2012 database</span></span>  
  
1.  <span data-ttu-id="3b0b0-114">No [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], clique no menu **Modelo** e em **Importar de Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-114">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **Model** menu, and then click **Import from Data Source**.</span></span>  
  
     <span data-ttu-id="3b0b0-115">Esse procedimento iniciará o Assistente de Importação de Tabela que o orientará no processo de configuração de uma conexão a uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-115">This launches the Table Import Wizard which guides you through setting up a connection to a data source.</span></span> <span data-ttu-id="3b0b0-116">Se a opção **Importar da Fonte de Dados** estiver acinzentada, clique duas vezes em **Model.bim** no **Gerenciador de Soluções** para abrir o modelo no designer.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-116">If **Import from Data Source** is greyed out, double click **Model.bim** in **Solution Explorer** to open the model in the designer.</span></span>  
  
2.  <span data-ttu-id="3b0b0-117">No **Assistente de Importação de Tabela**, em **Bancos de Dados Relacionais**, clique em **Microsoft SQL Server**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-117">In the **Table Import Wizard**, under **Relational Databases**, click **Microsoft SQL Server**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="3b0b0-118">Na página **conectar a um banco de dados Microsoft SQL Server** , em **nome de conexão amigável**, digite `Adventure Works DB from SQL` .</span><span class="sxs-lookup"><span data-stu-id="3b0b0-118">In the **Connect to a Microsoft SQL Server Database** page, in **Friendly Connection Name**, type `Adventure Works DB from SQL`.</span></span>  
  
4.  <span data-ttu-id="3b0b0-119">Na caixa **Nome do servidor**, digite o nome do servidor no qual você instalou o banco de dados AdventureWorksDW.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-119">In **Server name**, type the name of the server you installed the AdventureWorksDW database.</span></span>  
  
5.  <span data-ttu-id="3b0b0-120">No campo **Nome do banco de dados** , clique na seta para baixo e selecione **AdventureWorksDW**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-120">In the **Database name** field, click the down arrow and select **AdventureWorksDW**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="3b0b0-121">Na página **Informações sobre Representação** , é necessário especificar as credenciais que o Analysis Services usará para se conectar à fonte de dados ao importar e processar dados.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-121">In the **Impersonation Information** page, you need to specify the credentials Analysis Services will use to connect to the data source when importing and processing data.</span></span> <span data-ttu-id="3b0b0-122">Verifique se a opção **Nome de usuário e senha específicos do Windows** está selecionada e, em **Nome de Usuário** e **Senha**, insira suas credenciais de logon do Windows e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-122">Verify **Specific Windows user name and password** is selected, and then in **User Name** and **Password**, enter your Windows logon credentials, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3b0b0-123">O uso de uma conta de usuário e senha do Windows é o método mais seguro de conexão a uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-123">Using a Windows user account and password provides the most secure method of connecting to a data source.</span></span> <span data-ttu-id="3b0b0-124">Para obter mais informações, consulte [Representação &#40;SSAS de Tabela&#41;](tabular-models/impersonation-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="3b0b0-124">For more information, see [Impersonation &#40;SSAS Tabular&#41;](tabular-models/impersonation-ssas-tabular.md).</span></span>  
  
7.  <span data-ttu-id="3b0b0-125">Na página **Escolher como Importar os Dados** , verifique se a opção **Selecionar itens em uma lista de tabelas e exibições para escolher os dados a serem importados** está marcada.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-125">In the **Choose How to Import the Data** page, verify **Select from a list of tables and views to choose the data to import** is selected.</span></span> <span data-ttu-id="3b0b0-126">Para selecionar em uma lista de tabelas e exibições, clique em **Avançar** para exibir uma lista de todas as tabelas de origem do banco de dados de origem.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-126">You want to select from a list of tables and views, so click **Next** to display a list of all the source tables in the source database.</span></span>  
  
8.  <span data-ttu-id="3b0b0-127">Na página **Selecionar tabelas e exibições** , marque a caixa de seleção para as tabelas a seguir: **DimCustomer**, **DimDate**, **DimGeography**, **DimProduct**, **DimProductCategory**, **DimProductSubcategory**e **FactInternetSales**.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-127">In the **Select Tables and Views** page, select the check box for the following tables: **DimCustomer**, **DimDate**, **DimGeography**, **DimProduct**, **DimProductCategory**, **DimProductSubcategory**, and **FactInternetSales**.</span></span>  
  
9. <span data-ttu-id="3b0b0-128">Desejamos atribuir às tabelas do modelo nomes mais explicativos.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-128">We want to give the tables in the model more easily understood names.</span></span> <span data-ttu-id="3b0b0-129">Clique na célula da coluna **Nome Amigável** de **DimCustomer**.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-129">Click on the cell in the **Friendly Name** column for **DimCustomer**.</span></span> <span data-ttu-id="3b0b0-130">Renomeie a tabela removendo "Dim" de DimCustomer.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-130">Rename the table by removing "Dim" from DimCustomer.</span></span>  
  
10. <span data-ttu-id="3b0b0-131">Renomeie as outras tabelas:</span><span class="sxs-lookup"><span data-stu-id="3b0b0-131">Rename the other tables:</span></span>  
  
    |<span data-ttu-id="3b0b0-132">Nome de origem</span><span class="sxs-lookup"><span data-stu-id="3b0b0-132">Source name</span></span>|<span data-ttu-id="3b0b0-133">Nome amigável</span><span class="sxs-lookup"><span data-stu-id="3b0b0-133">Friendly Name</span></span>|  
    |-----------------|-------------------|  
    |<span data-ttu-id="3b0b0-134">DimDate</span><span class="sxs-lookup"><span data-stu-id="3b0b0-134">DimDate</span></span>|<span data-ttu-id="3b0b0-135">Data</span><span class="sxs-lookup"><span data-stu-id="3b0b0-135">Date</span></span>|  
    |<span data-ttu-id="3b0b0-136">DimGeography</span><span class="sxs-lookup"><span data-stu-id="3b0b0-136">DimGeography</span></span>|<span data-ttu-id="3b0b0-137">painel Geografia do app&#39;s selecionado</span><span class="sxs-lookup"><span data-stu-id="3b0b0-137">Geography</span></span>|  
    |<span data-ttu-id="3b0b0-138">DimProduct</span><span class="sxs-lookup"><span data-stu-id="3b0b0-138">DimProduct</span></span>|<span data-ttu-id="3b0b0-139">Produto</span><span class="sxs-lookup"><span data-stu-id="3b0b0-139">Product</span></span>|  
    |<span data-ttu-id="3b0b0-140">DimProductCategory</span><span class="sxs-lookup"><span data-stu-id="3b0b0-140">DimProductCategory</span></span>|<span data-ttu-id="3b0b0-141">Categoria do Produto</span><span class="sxs-lookup"><span data-stu-id="3b0b0-141">Product Category</span></span>|  
    |<span data-ttu-id="3b0b0-142">DimProductSubcategory</span><span class="sxs-lookup"><span data-stu-id="3b0b0-142">DimProductSubcategory</span></span>|<span data-ttu-id="3b0b0-143">Product Subcategory</span><span class="sxs-lookup"><span data-stu-id="3b0b0-143">Product Subcategory</span></span>|  
    |<span data-ttu-id="3b0b0-144">FactInternetSales</span><span class="sxs-lookup"><span data-stu-id="3b0b0-144">FactInternetSales</span></span>|<span data-ttu-id="3b0b0-145">Internet Sales</span><span class="sxs-lookup"><span data-stu-id="3b0b0-145">Internet Sales</span></span>|  
  
     <span data-ttu-id="3b0b0-146">**NÃO** clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-146">**DO NOT** click **Finish**.</span></span>  
  
 <span data-ttu-id="3b0b0-147">Agora que você se conectou ao banco de dados, selecionou as tabelas a serem importadas e atribuiu nomes amigáveis às tabelas, vá para a próxima seção, [Filtrar os dados da tabela antes de importar](#FilterData).</span><span class="sxs-lookup"><span data-stu-id="3b0b0-147">Now that you have connected to the database, selected the tables to import, and given the tables friendly names, go to the next section, [Filter the Table Data prior to Importing](#FilterData).</span></span>  
  
##  <a name="filter-the-table-data"></a><a name="FilterData"></a><span data-ttu-id="3b0b0-148">Filtrar os dados da tabela</span><span class="sxs-lookup"><span data-stu-id="3b0b0-148">Filter the Table Data</span></span>  
 <span data-ttu-id="3b0b0-149">A tabela DimCustomer que você está importando do banco de dados contém um subconjunto dos dados contidos no banco de dados Adventure Works original do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-149">The DimCustomer table that you are importing from the database contains a subset of the data from the original SQL Server Adventure Works database.</span></span> <span data-ttu-id="3b0b0-150">Você filtrará algumas das colunas da tabela DimCustomer que não são necessárias.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-150">You will filter out some of the columns from the DimCustomer table that aren't necessary.</span></span> <span data-ttu-id="3b0b0-151">Quando possível, você desejará filtrar dados que não serão usados para economizar espaço na memória usado pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-151">When possible, you will want to filter out data that will not be used in order to save in-memory space used by the model.</span></span>  
  
#### <a name="to-filter-the-table-data-prior-to-importing"></a><span data-ttu-id="3b0b0-152">Para filtrar os dados da tabela antes de importar</span><span class="sxs-lookup"><span data-stu-id="3b0b0-152">To filter the table data prior to importing</span></span>  
  
1.  <span data-ttu-id="3b0b0-153">Selecione a linha da tabela **Customer** e clique em **Visualizar e Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-153">Select the row for the **Customer** table, and then click **Preview & Filter**.</span></span> <span data-ttu-id="3b0b0-154">A janela **Visualizar Tabela Selecionada** é aberta com todas as colunas da tabela DimCustomer de origem exibida.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-154">The **Preview Selected Table** window opens with all the columns in the DimCustomer source table displayed.</span></span>  
  
2.  <span data-ttu-id="3b0b0-155">Desmarque a caixa de seleção na parte superior das seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="3b0b0-155">Clear the checkbox at the top of the following columns:</span></span>  
  
    |<span data-ttu-id="3b0b0-156">Cliente</span><span class="sxs-lookup"><span data-stu-id="3b0b0-156">Customer</span></span>|  
    |--------------|  
    |<span data-ttu-id="3b0b0-157">**SpanishEducation**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-157">**SpanishEducation**</span></span>|  
    |<span data-ttu-id="3b0b0-158">**FrenchEducation**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-158">**FrenchEducation**</span></span>|  
    |<span data-ttu-id="3b0b0-159">**SpanishOccupation**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-159">**SpanishOccupation**</span></span>|  
    |<span data-ttu-id="3b0b0-160">**FrenchOccupation**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-160">**FrenchOccupation**</span></span>|  
  
     <span data-ttu-id="3b0b0-161">Como os valores destas colunas não são pertinentes à análise de vendas da Internet, não há necessidade de importar essas colunas.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-161">Since the values for these columns are not relevant to Internet sales analysis, there is no need to import these columns.</span></span> <span data-ttu-id="3b0b0-162">A eliminação de colunas desnecessárias reduzirá o tamanho do modelo.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-162">Eliminating unnecessary columns will make your model smaller.</span></span>  
  
3.  <span data-ttu-id="3b0b0-163">Verifique se todas as outras colunas estão marcadas e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-163">Verify that all other columns are checked, and then click **OK**.</span></span>  
  
     <span data-ttu-id="3b0b0-164">Observe que as palavras **filtros aplicados** agora são exibidas na coluna **Filtrar detalhes** na linha **cliente** ; Se você clicar nesse link, verá uma descrição de texto dos filtros que você acabou de aplicar.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-164">Notice the words **Applied filters** are now displayed in the **Filter Details** column in the **Customer** row; if you click on that link you'll see a text description of the filters you just applied.</span></span>  
  
4.  <span data-ttu-id="3b0b0-165">Filtre as tabelas restantes desmarcando as caixas de seleção das colunas seguintes em cada tabela:</span><span class="sxs-lookup"><span data-stu-id="3b0b0-165">Filter the remaining tables by clearing the checkboxes for the following columns in each table:</span></span>  
  
    |<span data-ttu-id="3b0b0-166">Data</span><span class="sxs-lookup"><span data-stu-id="3b0b0-166">Date</span></span>|  
    |----------|  
    |<span data-ttu-id="3b0b0-167">**DateKey**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-167">**DateKey**</span></span>|  
    |<span data-ttu-id="3b0b0-168">**SpanishDayNameOfWeek**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-168">**SpanishDayNameOfWeek**</span></span>|  
    |<span data-ttu-id="3b0b0-169">**FrenchDayNameOfWeek**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-169">**FrenchDayNameOfWeek**</span></span>|  
    |<span data-ttu-id="3b0b0-170">**SpanishMonthName**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-170">**SpanishMonthName**</span></span>|  
    |<span data-ttu-id="3b0b0-171">**FrenchMonthName**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-171">**FrenchMonthName**</span></span>|  
  
    |<span data-ttu-id="3b0b0-172">painel Geografia do app&#39;s selecionado</span><span class="sxs-lookup"><span data-stu-id="3b0b0-172">Geography</span></span>|  
    |---------------|  
    |<span data-ttu-id="3b0b0-173">**SpanishCountryRegionName**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-173">**SpanishCountryRegionName**</span></span>|  
    |<span data-ttu-id="3b0b0-174">**FrenchCountryRegionName**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-174">**FrenchCountryRegionName**</span></span>|  
    |<span data-ttu-id="3b0b0-175">**IpAddressLocator**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-175">**IpAddressLocator**</span></span>|  
  
    |<span data-ttu-id="3b0b0-176">Produto</span><span class="sxs-lookup"><span data-stu-id="3b0b0-176">Product</span></span>|  
    |-------------|  
    |<span data-ttu-id="3b0b0-177">**SpanishProductName**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-177">**SpanishProductName**</span></span>|  
    |<span data-ttu-id="3b0b0-178">**FrenchProductName**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-178">**FrenchProductName**</span></span>|  
    |<span data-ttu-id="3b0b0-179">**FrenchDescription**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-179">**FrenchDescription**</span></span>|  
    |<span data-ttu-id="3b0b0-180">**ChineseDescription**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-180">**ChineseDescription**</span></span>|  
    |<span data-ttu-id="3b0b0-181">**ArabicDescription**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-181">**ArabicDescription**</span></span>|  
    |<span data-ttu-id="3b0b0-182">**HebrewDescription**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-182">**HebrewDescription**</span></span>|  
    |<span data-ttu-id="3b0b0-183">**ThaiDescription**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-183">**ThaiDescription**</span></span>|  
    |<span data-ttu-id="3b0b0-184">**GermanDescription**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-184">**GermanDescription**</span></span>|  
    |<span data-ttu-id="3b0b0-185">**JapaneseDescription**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-185">**JapaneseDescription**</span></span>|  
    |<span data-ttu-id="3b0b0-186">**TurkishDescription**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-186">**TurkishDescription**</span></span>|  
  
    |<span data-ttu-id="3b0b0-187">Categoria do Produto</span><span class="sxs-lookup"><span data-stu-id="3b0b0-187">Product Category</span></span>|  
    |----------------------|  
    |<span data-ttu-id="3b0b0-188">**SpanishProductCategoryName**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-188">**SpanishProductCategoryName**</span></span>|  
    |<span data-ttu-id="3b0b0-189">**FrenchProductCategoryName**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-189">**FrenchProductCategoryName**</span></span>|  
  
    |<span data-ttu-id="3b0b0-190">Product Subcategory</span><span class="sxs-lookup"><span data-stu-id="3b0b0-190">Product Subcategory</span></span>|  
    |-------------------------|  
    |<span data-ttu-id="3b0b0-191">**SpanishProductSubcategoryName**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-191">**SpanishProductSubcategoryName**</span></span>|  
    |<span data-ttu-id="3b0b0-192">**FrenchProductSubcategoryName**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-192">**FrenchProductSubcategoryName**</span></span>|  
  
    |<span data-ttu-id="3b0b0-193">Internet Sales</span><span class="sxs-lookup"><span data-stu-id="3b0b0-193">Internet Sales</span></span>|  
    |--------------------|  
    |<span data-ttu-id="3b0b0-194">**OrderDateKey**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-194">**OrderDateKey**</span></span>|  
    |<span data-ttu-id="3b0b0-195">**DueDateKey**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-195">**DueDateKey**</span></span>|  
    |<span data-ttu-id="3b0b0-196">**ShipDateKey**</span><span class="sxs-lookup"><span data-stu-id="3b0b0-196">**ShipDateKey**</span></span>|  
  
 <span data-ttu-id="3b0b0-197">Agora que você visualizou e filtrou os dados desnecessários, poderá importar os dados.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-197">Now that you have previewed and filtered out unnecessary data, you can import the data.</span></span> <span data-ttu-id="3b0b0-198">Vá para a próxima seção **Importar as tabelas e os dados de coluna selecionados**.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-198">Go to the next section **Import the Selected Tables and Column Data**.</span></span>  
  
##  <a name="import-the-selected-tables-and-column-data"></a><a name="Import"></a><span data-ttu-id="3b0b0-199">Importar as tabelas e os dados de coluna selecionados</span><span class="sxs-lookup"><span data-stu-id="3b0b0-199">Import the Selected Tables and Column Data</span></span>  
 <span data-ttu-id="3b0b0-200">Agora você pode importar os dados selecionados.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-200">You can now import the selected data.</span></span> <span data-ttu-id="3b0b0-201">O assistente importa os dados da tabela junto com as relações entre as tabelas.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-201">The wizard imports the table data along with any relationships between tables.</span></span> <span data-ttu-id="3b0b0-202">São criadas novas tabelas e colunas no modelo usando os nomes amigáveis que você especificou, e os dados que você filtrou não serão importados.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-202">New tables and columns are created in the model using the friendly names you specified, and data that you filtered out will not be imported.</span></span>  
  
#### <a name="to-import-the-selected-tables-and-column-data"></a><span data-ttu-id="3b0b0-203">Para importar os dados de colunas e tabelas selecionadas</span><span class="sxs-lookup"><span data-stu-id="3b0b0-203">To import the selected tables and column data</span></span>  
  
1.  <span data-ttu-id="3b0b0-204">Examine suas seleções.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-204">Review your selections.</span></span> <span data-ttu-id="3b0b0-205">Se tudo estiver correto, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-205">If everything looks OK, click **Finish**.</span></span>  
  
     <span data-ttu-id="3b0b0-206">Durante a importação dos dados, o assistente exibirá quantas linhas foram buscadas.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-206">While importing the data, the wizard displays how many rows have been fetched.</span></span> <span data-ttu-id="3b0b0-207">Quando todos os dados tiverem sido importados, será exibida uma mensagem indicando êxito.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-207">When all the data has been imported, a message indicating success is displayed.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="3b0b0-208"> Para consultar as relações que foram criadas automaticamente entre as tabelas importadas, na linha **Preparação de dados** , clique em **Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-208">To see the relationships that were automatically created between the imported tables, on the **Data preparation** row, click **Details**.</span></span>  
  
2.  <span data-ttu-id="3b0b0-209">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-209">Click **Close**.</span></span>  
  
     <span data-ttu-id="3b0b0-210">O assistente é fechado e o modelo de designer fica visível.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-210">The wizard closes and the model designer is visible.</span></span> <span data-ttu-id="3b0b0-211">Cada tabela foi adicionada como uma nova guia no designer de modelos.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-211">Each table has been added as a new tab in the model designer.</span></span>  
  
## <a name="save-the-model-project"></a><span data-ttu-id="3b0b0-212">Salve o Projeto de Modelo.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-212">Save the Model Project</span></span>  
 <span data-ttu-id="3b0b0-213">É importante salvar frequentemente seu projeto de modelo.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-213">It is important to frequently save your model project.</span></span>  
  
#### <a name="to-save-the-model-project"></a><span data-ttu-id="3b0b0-214">Para salvar o projeto de modelo</span><span class="sxs-lookup"><span data-stu-id="3b0b0-214">To save the model project</span></span>  
  
-   <span data-ttu-id="3b0b0-215">Em [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], clique no menu **Arquivo** e clique em **Salvar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="3b0b0-215">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **File** menu, and then click **Save All**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="3b0b0-216">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="3b0b0-216">Next Step</span></span>  
 <span data-ttu-id="3b0b0-217">Para continuar este tutorial, vá para a próxima lição: [Lição 3: Renomear colunas](rename-columns.md).</span><span class="sxs-lookup"><span data-stu-id="3b0b0-217">To continue this tutorial, go to the next lesson: [Lesson 3: Rename Columns](rename-columns.md).</span></span>  
  
  
