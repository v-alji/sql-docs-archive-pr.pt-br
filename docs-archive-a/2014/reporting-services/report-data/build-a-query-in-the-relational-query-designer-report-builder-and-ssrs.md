---
title: Compilar uma consulta no designer de consultas relacionais (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 28b25861-f3b4-4c3e-a9b0-03d6e4cfea26
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 555d72c4d3bca8677d04fdc4160639f004d6bbe9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684562"
---
# <a name="build-a-query-in-the-relational-query-designer-report-builder-and-ssrs"></a><span data-ttu-id="5fbe5-102">Compilar uma consulta no designer de consulta relacional (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="5fbe5-102">Build a Query in the Relational Query Designer (Report Builder and SSRS)</span></span>
  <span data-ttu-id="5fbe5-103">Um designer de consulta ajuda a especificar quais dados devem ser recuperados de uma fonte de dados externa para um conjunto de dados de relatório.</span><span class="sxs-lookup"><span data-stu-id="5fbe5-103">A query designer helps you specify which data to retrieve from an external data source for a report dataset.</span></span> <span data-ttu-id="5fbe5-104">Você usa um designer de consulta quando compila uma consulta em um assistente ou cria uma consulta de conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="5fbe5-104">You use a query designer when you build a query in a wizard or create a dataset query.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="5fbe5-105">Um conjunto de dados se baseia em uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="5fbe5-105">A dataset is based on a data source.</span></span> <span data-ttu-id="5fbe5-106">O tipo de fonte de dados e o ambiente de criação determinam qual designer de consulta é aberto quando você define a consulta de conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="5fbe5-106">The type of data source and the authoring environment determines which query designer opens when you define the dataset query.</span></span> <span data-ttu-id="5fbe5-107">Os recursos do designer de consulta variam de acordo com a fonte de dados subjacente.</span><span class="sxs-lookup"><span data-stu-id="5fbe5-107">Query designer features vary based on the underlying data source.</span></span> <span data-ttu-id="5fbe5-108">Para obter mais informações sobre camadas de dados, consulte [conexões de dados, fontes de dados e cadeias de conexão em Construtor de relatórios](../data-connections-data-sources-and-connection-strings-in-report-builder.md) ou [conexões de dados, fontes de dados e cadeias de conexão no Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="5fbe5-108">For more information about data layers, see [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md) or [Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md).</span></span>  
  
 <span data-ttu-id="5fbe5-109">É possível usar um designer de consulta para as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="5fbe5-109">You can use a query designer for the following tasks:</span></span>  
  
-   <span data-ttu-id="5fbe5-110">Explorar os metadados de vários esquemas na fonte de dados externa</span><span class="sxs-lookup"><span data-stu-id="5fbe5-110">Explore the metadata for multiple schemas on the external data source</span></span>  
  
-   <span data-ttu-id="5fbe5-111">Especificar campos a serem recuperados para o conjunto de dados</span><span class="sxs-lookup"><span data-stu-id="5fbe5-111">Specify fields to retrieve for the dataset</span></span>  
  
-   <span data-ttu-id="5fbe5-112">Especificar relações entre dois objetos, como tabelas</span><span class="sxs-lookup"><span data-stu-id="5fbe5-112">Specify relationships between two objects such as tables</span></span>  
  
-   <span data-ttu-id="5fbe5-113">Especificar filtros para restringir os dados antes de serem recuperados como dados de relatório</span><span class="sxs-lookup"><span data-stu-id="5fbe5-113">Specify filters to restrict the data before it is retrieved as report data</span></span>  
  
-   <span data-ttu-id="5fbe5-114">Indicar se é necessário criar parâmetros</span><span class="sxs-lookup"><span data-stu-id="5fbe5-114">Indicate whether to create parameters</span></span>  
  
-   <span data-ttu-id="5fbe5-115">Especificar agregações para executar cálculos na fonte de dados externa</span><span class="sxs-lookup"><span data-stu-id="5fbe5-115">Specify aggregates to perform calculations on the external data source</span></span>  
  
 <span data-ttu-id="5fbe5-116">Depois de abrir um designer de consulta, você cria uma consulta da mesma forma para um conjunto de dados inserido ou um compartilhado.</span><span class="sxs-lookup"><span data-stu-id="5fbe5-116">After you open a query designer, you build a query in the same way for either an embedded dataset or a shared dataset.</span></span> <span data-ttu-id="5fbe5-117">Os procedimentos a seguir usam uma consulta do conjunto de dados inserida.</span><span class="sxs-lookup"><span data-stu-id="5fbe5-117">The following procedures use an embedded dataset query.</span></span>  
  
 <span data-ttu-id="5fbe5-118">Para obter mais informações, consulte [Interface do usuário do Designer de Consultas Relacionais &#40;Construtor de Relatórios&#41;](relational-query-designer-user-interface-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="5fbe5-118">For more information, see [Relational Query Designer User Interface &#40;Report Builder&#41;](relational-query-designer-user-interface-report-builder.md).</span></span>  
  
### <a name="to-build-a-query-for-an-embedded-dataset-in-report-design-view"></a><span data-ttu-id="5fbe5-119">Para compilar uma consulta para um conjunto de dados inserido na exibição Design do Relatório</span><span class="sxs-lookup"><span data-stu-id="5fbe5-119">To build a query for an embedded dataset in Report Design View</span></span>  
  
1.  <span data-ttu-id="5fbe5-120">Abra o designer de consulta.</span><span class="sxs-lookup"><span data-stu-id="5fbe5-120">Open the query designer.</span></span> <span data-ttu-id="5fbe5-121">No painel Dados do Relatório, clique com o botão direito do mouse no conjunto de dados e clique em **Consulta**.</span><span class="sxs-lookup"><span data-stu-id="5fbe5-121">In the Report Data pane, right-click the dataset, and then click **Query**.</span></span>  
  
     <span data-ttu-id="5fbe5-122">O designer de consulta associado à fonte de dados é aberto.</span><span class="sxs-lookup"><span data-stu-id="5fbe5-122">The query designer that is associated with the data source opens.</span></span>  
  
2.  <span data-ttu-id="5fbe5-123">No painel de exibição Banco de dados, expanda as pastas que mostrem uma exibição hierárquica dos objetos de esquema de banco de dados, como tabelas, exibições e procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="5fbe5-123">In the Database view pane, expand the folders that display a hierarchical view of database schema objects such as tables, views, and stored procedures.</span></span> <span data-ttu-id="5fbe5-124">Clique na caixa de seleção para selecionar todos os campos para um objeto ou expanda o nó para selecionar campos individuais.</span><span class="sxs-lookup"><span data-stu-id="5fbe5-124">Click the select box to select all fields for an object or expand the node to select individual fields.</span></span>  
  
     <span data-ttu-id="5fbe5-125">À medida que você seleciona campos no painel de exibição Banco de Dados, o painel **Selecionar campos** exibe suas seleções.</span><span class="sxs-lookup"><span data-stu-id="5fbe5-125">As you select fields from the Database view pane, the **Select fields** pane displays your selections.</span></span>  
  
     <span data-ttu-id="5fbe5-126">Se você selecionar campos de mais de uma tabela de banco de dados relacionada, use o painel Relações para exibir as relações de tabelas detectadas no esquema de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="5fbe5-126">If you select fields from more than one related database table, use the Relationships pane to view the table relationships that were detected from the database schema.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="5fbe5-127">A lista de campos do conjunto de dados é exibida no painel de dados do relatório.</span><span class="sxs-lookup"><span data-stu-id="5fbe5-127">The list of dataset fields appears in the Report Data pane.</span></span>  
  
### <a name="to-specify-limits-for-a-query"></a><span data-ttu-id="5fbe5-128">Para especificar limites para uma consulta</span><span class="sxs-lookup"><span data-stu-id="5fbe5-128">To specify limits for a query</span></span>  
  
1.  <span data-ttu-id="5fbe5-129">No designer de consultas relacionais, verifique se você tem campos selecionados e se os campos são exibidos no painel **Campos selecionados** .</span><span class="sxs-lookup"><span data-stu-id="5fbe5-129">In the relational query designer, verify that you have fields selected and that the fields appear in the **Selected fields** pane.</span></span>  
  
2.  <span data-ttu-id="5fbe5-130">Na barra de ferramentas do painel Filtros aplicados, clique em **Adicionar Filtro**.</span><span class="sxs-lookup"><span data-stu-id="5fbe5-130">In the Applied filters pane toolbar, click **Add Filter**.</span></span> <span data-ttu-id="5fbe5-131">Uma nova linha de filtro é exibida.</span><span class="sxs-lookup"><span data-stu-id="5fbe5-131">A new filter row appears.</span></span>  
  
3.  <span data-ttu-id="5fbe5-132">Em **Nome do campo**, clique para exibir a lista suspensa de campos e clique no nome do campo pelo qual você deseja filtrar.</span><span class="sxs-lookup"><span data-stu-id="5fbe5-132">In **Field name**, click to display the drop-down list of fields, and then click the name of the field that you want to filter by.</span></span> <span data-ttu-id="5fbe5-133">Por exemplo, para filtrar por quantidade, clique no campo que contém o número de itens.</span><span class="sxs-lookup"><span data-stu-id="5fbe5-133">For example, to filter by quantity, click the field that contains the number of items.</span></span>  
  
4.  <span data-ttu-id="5fbe5-134">Em **Operador**, clique para exibir a lista suspensa de operadores e selecione o operador de comparação a ser usado no filtro.</span><span class="sxs-lookup"><span data-stu-id="5fbe5-134">In **Operator**, click to display the drop-down list of operators, and then select the comparison operator to use in the filter.</span></span>  
  
5.  <span data-ttu-id="5fbe5-135">Em **Valor**, digite o valor pelo qual você deseja filtrar.</span><span class="sxs-lookup"><span data-stu-id="5fbe5-135">In **Value**, type the value that you want to filter by.</span></span> <span data-ttu-id="5fbe5-136">Por exemplo, para filtrar quantidade maior que 100, digite 100.</span><span class="sxs-lookup"><span data-stu-id="5fbe5-136">For example, to filter on quantity greater than 100, type 100.</span></span>  
  
6.  <span data-ttu-id="5fbe5-137">Selecione a opção de parâmetro nessa linha para criar um parâmetro de conjunto de dados e permitir a um usuário especificar um valor de filtro.</span><span class="sxs-lookup"><span data-stu-id="5fbe5-137">Select the parameter option in this row to create a dataset parameter to enable a user to specify a filter value.</span></span> <span data-ttu-id="5fbe5-138">Um parâmetro de relatório correspondente ao parâmetro do conjunto de dados é criado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5fbe5-138">A report parameter that matches the dataset parameter is automatically created.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="5fbe5-139">A lista de campos do conjunto de dados é exibida no painel de dados do relatório.</span><span class="sxs-lookup"><span data-stu-id="5fbe5-139">The list of dataset fields appears in the Report Data pane.</span></span>  
  
### <a name="to-view-a-query-result-set"></a><span data-ttu-id="5fbe5-140">Para exibir um conjunto de resultados da consulta</span><span class="sxs-lookup"><span data-stu-id="5fbe5-140">To view a query result set</span></span>  
  
1.  <span data-ttu-id="5fbe5-141">Na barra de ferramentas do designer de consultas, clique em **Executar Consulta (!)** .</span><span class="sxs-lookup"><span data-stu-id="5fbe5-141">On the query designer toolbar, click **Run Query (!)**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5fbe5-142">O designer de consulta usa credenciais do momento do design para executar a consulta e recuperar o conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="5fbe5-142">The query designer uses design time credentials to run the query and retrieve the result set.</span></span> <span data-ttu-id="5fbe5-143">Para obter mais informações, consulte [Especificar as credenciais no Construtor de Relatórios](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="5fbe5-143">For more information, see [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  
 <span data-ttu-id="5fbe5-144">A consulta é executada na fonte de dados e retorna dados de exemplo no painel de resultados Consulta.</span><span class="sxs-lookup"><span data-stu-id="5fbe5-144">The query runs on the data source and returns example data in the Query results pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fbe5-145">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5fbe5-145">See Also</span></span>  
 <span data-ttu-id="5fbe5-146">[Adicionar dados a um relatório &#40;Construtor de Relatórios e SSRS&#41;](report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5fbe5-146">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="5fbe5-147">[Adicionar dados de fontes de dados externas &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5fbe5-147">[Add Data from External Data Sources &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) </span></span>  
 <span data-ttu-id="5fbe5-148">[Designers de consulta &#40;Construtor de Relatórios&#41;](../query-designers-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="5fbe5-148">[Query Designers &#40;Report Builder&#41;](../query-designers-report-builder.md) </span></span>  
 <span data-ttu-id="5fbe5-149">[Criar um conjunto de dados compartilhado ou um conjunto de dados inserido &#40;Construtor de Relatórios e SSRS&#41;](create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5fbe5-149">[Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;](create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5fbe5-150">[Modo de exibição de Design de relatório &#40;Construtor de Relatórios&#41;](../report-builder/report-design-view-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="5fbe5-150">[Report Design View &#40;Report Builder&#41;](../report-builder/report-design-view-report-builder.md) </span></span>  
 <span data-ttu-id="5fbe5-151">[Modo de exibição de Design de conjunto de dados compartilhados &#40;Construtor de Relatórios&#41;](../report-builder/shared-dataset-design-view-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="5fbe5-151">[Shared Dataset Design View &#40;Report Builder&#41;](../report-builder/shared-dataset-design-view-report-builder.md) </span></span>  
 [<span data-ttu-id="5fbe5-152">Designers de Consultas do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="5fbe5-152">Reporting Services Query Designers</span></span>](../reporting-services-query-designers.md)  
  
  
