---
title: Adicionar parâmetros em cascata a um relatório (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 3a22eec3-57a7-478e-b6fc-102a9dbe0591
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5419d448b2fa9526224e1bccd80d5c195e2763d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679140"
---
# <a name="add-cascading-parameters-to-a-report-report-builder-and-ssrs"></a><span data-ttu-id="acabc-102">Adicionar parâmetros em cascata a um relatório (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="acabc-102">Add Cascading Parameters to a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="acabc-103">Os parâmetros em cascata fornecem um modo de gerenciar grandes volumes de dados de relatório.</span><span class="sxs-lookup"><span data-stu-id="acabc-103">Cascading parameters provide a way of managing large amounts of report data.</span></span> <span data-ttu-id="acabc-104">É possível definir um conjunto de parâmetros relacionados de forma que a lista de valores de um parâmetro dependa do valor escolhido em outro parâmetro.</span><span class="sxs-lookup"><span data-stu-id="acabc-104">You can define a set of related parameters so that the list of values for one parameter depends on the value chosen in another parameter.</span></span> <span data-ttu-id="acabc-105">Por exemplo, o primeiro parâmetro é independente e pode apresentar uma lista de categorias de produtos.</span><span class="sxs-lookup"><span data-stu-id="acabc-105">For example, the first parameter is independent and might present a list of product categories.</span></span> <span data-ttu-id="acabc-106">Quando o usuário seleciona uma categoria, o segundo parâmetro é dependente do valor do primeiro parâmetro.</span><span class="sxs-lookup"><span data-stu-id="acabc-106">When the user selects a category, the second parameter is dependent on the value of the first parameter.</span></span> <span data-ttu-id="acabc-107">Seus valores são atualizados com uma lista de subcategorias dentro da categoria escolhida.</span><span class="sxs-lookup"><span data-stu-id="acabc-107">Its values are updated with a list of subcategories within the chosen category.</span></span> <span data-ttu-id="acabc-108">Quando o usuário exibe o relatório, os valores dos dois parâmetros de categoria e subcategoria são usados para filtrar dados do relatório.</span><span class="sxs-lookup"><span data-stu-id="acabc-108">When the user views the report, the values for both the category and subcategory parameters are used to filter report data.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="acabc-109">Para criar parâmetros em cascata, primeiro você define a consulta de conjunto de dados e inclui um parâmetro de consulta para cada parâmetro em cascata necessário.</span><span class="sxs-lookup"><span data-stu-id="acabc-109">To create cascading parameters, you define the dataset query first and include a query parameter for each cascading parameter that you need.</span></span> <span data-ttu-id="acabc-110">Você também deve criar um conjunto de dados separado para cada parâmetro em cascata para fornecer valores disponíveis.</span><span class="sxs-lookup"><span data-stu-id="acabc-110">You must also create a separate dataset for each cascading parameter to provide available values.</span></span> <span data-ttu-id="acabc-111">Para obter mais informações, consulte [Adicionar, alterar ou excluir os valores disponíveis de um parâmetro de relatório &#40;Construtor de Relatórios e SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span><span class="sxs-lookup"><span data-stu-id="acabc-111">For more information, see [Add, Change, or Delete Available Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span></span>  
  
 <span data-ttu-id="acabc-112">A ordem é importante para parâmetros em cascata porque a consulta do conjunto de dados para um parâmetro posterior na lista inclui uma referência a cada parâmetro anterior na lista.</span><span class="sxs-lookup"><span data-stu-id="acabc-112">Order is important for cascading parameters because the dataset query for a parameter later in the list includes a reference to each parameter that is earlier in the list.</span></span> <span data-ttu-id="acabc-113">Em tempo de execução, a ordem dos parâmetros no painel de dados do relatório determina a ordem na qual as consultas de parâmetro aparecem no relatório e, portanto, a ordem na qual um usuário escolhe cada valor de parâmetro sucessivo.</span><span class="sxs-lookup"><span data-stu-id="acabc-113">At run time, the order of the parameters in the Report Data pane determines the order in which the parameter queries appear in the report, and therefore, the order in which a user chooses each successive parameter value.</span></span>  
  
 <span data-ttu-id="acabc-114">Para obter informações sobre como criar parâmetros em cascata com diversos valores e o recurso Selecionar Tudo, consulte [Como ter um parâmetro em cascata de diversos valores com Selecionar Tudo](https://go.microsoft.com/fwlink/?LinkId=184757).</span><span class="sxs-lookup"><span data-stu-id="acabc-114">For information about creating cascading parameters with multiple values and including the Select All feature, see [How to have a Select All Multivalue Cascading Parameter](https://go.microsoft.com/fwlink/?LinkId=184757).</span></span>  
  
### <a name="to-create-the-main-dataset-with-a-query-that-includes-multiple-related-parameters"></a><span data-ttu-id="acabc-115">Para criar o conjunto de dados principal com uma consulta que inclui múltiplos parâmetros relacionados</span><span class="sxs-lookup"><span data-stu-id="acabc-115">To create the main dataset with a query that includes multiple related parameters</span></span>  
  
1.  <span data-ttu-id="acabc-116">No painel Dados do Relatório, clique com o botão direito do mouse em uma fonte de dados e clique em **Adicionar Conjunto de Dados**.</span><span class="sxs-lookup"><span data-stu-id="acabc-116">In the Report Data pane, right-click a data source, and then click **Add Dataset**.</span></span>  
  
2.  <span data-ttu-id="acabc-117">Em **Nome**, digite o nome do conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="acabc-117">In **Name**, type the name of the dataset.</span></span>  
  
3.  <span data-ttu-id="acabc-118">Em **Fonte de Dados**, escolha o nome da fonte de dados ou clique em **Nova** para criar uma.</span><span class="sxs-lookup"><span data-stu-id="acabc-118">In **Data source**, choose the name of the data source or click **New** to create one.</span></span>  
  
4.  <span data-ttu-id="acabc-119">Em **Tipo de consulta**, escolha o tipo de consulta para a fonte de dados selecionada.</span><span class="sxs-lookup"><span data-stu-id="acabc-119">In **Query type**, choose the type of query for the selected data source.</span></span> <span data-ttu-id="acabc-120">Neste tópico, o tipo de consulta **Text** é assumido.</span><span class="sxs-lookup"><span data-stu-id="acabc-120">In this topic, query type **Text** is assumed.</span></span>  
  
5.  <span data-ttu-id="acabc-121">Em **Consulta**, digite a consulta a ser usada para recuperar dados para este relatório.</span><span class="sxs-lookup"><span data-stu-id="acabc-121">In **Query**, type the query to use to retrieve data for this report.</span></span> <span data-ttu-id="acabc-122">A consulta deve incluir as seguintes partes:</span><span class="sxs-lookup"><span data-stu-id="acabc-122">The query must include the following parts:</span></span>  
  
    1.  <span data-ttu-id="acabc-123">Uma lista de campos de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="acabc-123">A list of data source fields.</span></span> <span data-ttu-id="acabc-124">Por exemplo, em uma instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] , a instrução SELECT especifica uma lista de nomes de colunas do banco de dados de uma determinada tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="acabc-124">For example, in a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, the SELECT statement specifies a list of database column names from a given table or view.</span></span>  
  
    2.  <span data-ttu-id="acabc-125">Um parâmetro de consulta para cada parâmetro em cascata.</span><span class="sxs-lookup"><span data-stu-id="acabc-125">One query parameter for each cascading parameter.</span></span> <span data-ttu-id="acabc-126">Um parâmetro de consulta limita os dados recuperados da fonte de dados especificando determinados valores a serem incluídos ou excluídos da consulta.</span><span class="sxs-lookup"><span data-stu-id="acabc-126">A query parameter limits the data retrieved from the data source by specifying certain values to include or exclude from the query.</span></span> <span data-ttu-id="acabc-127">Normalmente, parâmetros de consulta ocorrem em uma cláusula de restrição na consulta.</span><span class="sxs-lookup"><span data-stu-id="acabc-127">Typically, query parameters occur in a restriction clause in the query.</span></span> <span data-ttu-id="acabc-128">Por exemplo, em uma instrução SELECT do [!INCLUDE[tsql](../../includes/tsql-md.md)] , os parâmetros de consulta ocorrem na cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="acabc-128">For example, in a [!INCLUDE[tsql](../../includes/tsql-md.md)] SELECT statement, query parameters occur in the WHERE clause.</span></span> <span data-ttu-id="acabc-129">Para obter mais informações, consulte "Filtering Rows by Using WHERE and HAVING" na documentação do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] nos [Manuais Online do SQL Server](https://go.microsoft.com/fwlink/?linkid=120955).</span><span class="sxs-lookup"><span data-stu-id="acabc-129">For more information, see "Filtering Rows by Using WHERE and HAVING" in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] documentation in [SQL Server Books Online](https://go.microsoft.com/fwlink/?linkid=120955).</span></span>  
  
6.  <span data-ttu-id="acabc-130">Clique em **Executar** (**!**).</span><span class="sxs-lookup"><span data-stu-id="acabc-130">Click **Run** (**!**).</span></span> <span data-ttu-id="acabc-131">Depois que você incluir parâmetros de consulta e executar a consulta, os parâmetros do relatório que correspondem aos parâmetros da consulta serão criados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="acabc-131">After you include query parameters and then run the query, report parameters that correspond to the query parameters are automatically created.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="acabc-132">A ordem dos parâmetros de consulta na primeira vez que você executa uma consulta determina a ordem como eles são criados no relatório.</span><span class="sxs-lookup"><span data-stu-id="acabc-132">The order of query parameters the first time you run a query determines the order that they are created in the report.</span></span> <span data-ttu-id="acabc-133">Para alterar a ordem, consulte [Alterar a ordem de um parâmetro de relatório &#40;Construtor de Relatórios e SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="acabc-133">To change the order, see [Change the Order of a Report Parameter &#40;Report Builder and SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md)</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="acabc-134">Em seguida, você criará um conjunto de dados que fornece os valores para o parâmetro independente.</span><span class="sxs-lookup"><span data-stu-id="acabc-134">Next, you will create a dataset that provides the values for the independent parameter.</span></span>  
  
### <a name="to-create-a-dataset-to-provide-values-for-an-independent-parameter"></a><span data-ttu-id="acabc-135">Para criar um conjunto de dados para fornecer valores para um parâmetro independente</span><span class="sxs-lookup"><span data-stu-id="acabc-135">To create a dataset to provide values for an independent parameter</span></span>  
  
1.  <span data-ttu-id="acabc-136">No painel Dados do Relatório, clique com o botão direito do mouse em uma fonte de dados e clique em **Adicionar Conjunto de Dados**.</span><span class="sxs-lookup"><span data-stu-id="acabc-136">In the Report Data pane, right-click a data source, and then click **Add Dataset**.</span></span>  
  
2.  <span data-ttu-id="acabc-137">Em **Nome**, digite o nome do conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="acabc-137">In **Name**, type the name of the dataset.</span></span>  
  
3.  <span data-ttu-id="acabc-138">Em **Fonte de Dados**, verifique se o nome é o nome da fonte de dados escolhida na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="acabc-138">In **Data source**, verify the name is the name of the data source you chose in step 1.</span></span>  
  
4.  <span data-ttu-id="acabc-139">Em **Tipo de consulta**, escolha o tipo de consulta para a fonte de dados selecionada.</span><span class="sxs-lookup"><span data-stu-id="acabc-139">In **Query type**, choose the type of query for the selected data source.</span></span> <span data-ttu-id="acabc-140">Neste tópico, o tipo de consulta **Text** é assumido.</span><span class="sxs-lookup"><span data-stu-id="acabc-140">In this topic, query type **Text** is assumed.</span></span>  
  
5.  <span data-ttu-id="acabc-141">Em **Consulta**, digite a consulta a ser usada para recuperar valores para este parâmetro.</span><span class="sxs-lookup"><span data-stu-id="acabc-141">In **Query**, type the query to use to retrieve values for this parameter.</span></span> <span data-ttu-id="acabc-142">Normalmente, consultas de parâmetros independentes não contêm parâmetros de consulta.</span><span class="sxs-lookup"><span data-stu-id="acabc-142">Queries for independent parameters typically do not contain query parameters.</span></span> <span data-ttu-id="acabc-143">Por exemplo, para criar uma consulta para um parâmetro que fornece todos os valores de categoria, você pode usar uma instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="acabc-143">For example, to create a query for a parameter that provides all category values, you might use a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement similar to the following:</span></span>  
  
    ```  
    SELECT DISTINCT <column name> FROM <table>  
    ```  
  
     <span data-ttu-id="acabc-144">O comando SELECT DISTINCT remove valores duplicados do conjunto de resultados para que você obtenha cada valor exclusivo da coluna especificada na tabela especificada.</span><span class="sxs-lookup"><span data-stu-id="acabc-144">The SELECT DISTINCT command removes duplicate values from the result set so that you get each unique value from the specified column in the specified table.</span></span>  
  
     <span data-ttu-id="acabc-145">Clique em **Executar** (**!**).</span><span class="sxs-lookup"><span data-stu-id="acabc-145">Click **Run** (**!**).</span></span> <span data-ttu-id="acabc-146">O conjunto de resultados mostra os valores que estão disponíveis para esse primeiro parâmetro.</span><span class="sxs-lookup"><span data-stu-id="acabc-146">The result set shows the values that are available for this first parameter.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="acabc-147">Em seguida, você definirá as propriedades do primeiro parâmetro para usar este conjunto de dados para popular seus valores disponíveis em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="acabc-147">Next, you will set the properties of the first parameter to use this dataset to populate its available values at run-time.</span></span>  
  
### <a name="to-set-available-values-for-a-report-parameter"></a><span data-ttu-id="acabc-148">Para definir os valores disponíveis para um parâmetro de relatório</span><span class="sxs-lookup"><span data-stu-id="acabc-148">To set available values for a report parameter</span></span>  
  
1.  <span data-ttu-id="acabc-149">No painel Dados do Relatório, na pasta Parâmetros, clique com o botão direito do mouse no primeiro parâmetro e clique em **Propriedades do Parâmetro**.</span><span class="sxs-lookup"><span data-stu-id="acabc-149">In the Report Data pane, in the Parameters folder, right-click the first parameter, and then click **Parameter Properties**.</span></span>  
  
2.  <span data-ttu-id="acabc-150">Em **Nome**, verifique se o nome do parâmetro está correto.</span><span class="sxs-lookup"><span data-stu-id="acabc-150">In **Name**, verify that the name of the parameter is correct.</span></span>  
  
3.  <span data-ttu-id="acabc-151">Clique em **Valores Disponíveis**.</span><span class="sxs-lookup"><span data-stu-id="acabc-151">Click **Available Values**.</span></span>  
  
4.  <span data-ttu-id="acabc-152">Clique em **Obter valores de uma consulta**.</span><span class="sxs-lookup"><span data-stu-id="acabc-152">Click **Get values from a query**.</span></span> <span data-ttu-id="acabc-153">Três campos são exibidos.</span><span class="sxs-lookup"><span data-stu-id="acabc-153">Three fields appear.</span></span>  
  
5.  <span data-ttu-id="acabc-154">Em **Conjunto de Dados**, na lista suspensa, clique no nome do conjunto de dados criado no procedimento anterior.</span><span class="sxs-lookup"><span data-stu-id="acabc-154">In **Dataset**, from the drop-down list, click the name of the dataset you created in the previous procedure.</span></span>  
  
6.  <span data-ttu-id="acabc-155">No campo **Valor** , clique no nome do campo que fornece o valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="acabc-155">In **Value** field, click the name of the field that provides the parameter value.</span></span>  
  
7.  <span data-ttu-id="acabc-156">No campo **Rótulo** , clique no nome do campo que fornece o rótulo do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="acabc-156">In **Label** field, click the name of the field that provides the parameter label.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="acabc-157">Em seguida, você criará um conjunto de dados que fornece os valores para um parâmetro dependente.</span><span class="sxs-lookup"><span data-stu-id="acabc-157">Next, you will create a dataset that provides the values for a dependent parameter.</span></span>  
  
### <a name="to-create-a-dataset-to-provide-values-for-a-dependent-parameter"></a><span data-ttu-id="acabc-158">Para criar um conjunto de dados para fornecer valores para um parâmetro dependente</span><span class="sxs-lookup"><span data-stu-id="acabc-158">To create a dataset to provide values for a dependent parameter</span></span>  
  
1.  <span data-ttu-id="acabc-159">No painel Dados do Relatório, clique com o botão direito do mouse em uma fonte de dados e clique em **Adicionar Conjunto de Dados**.</span><span class="sxs-lookup"><span data-stu-id="acabc-159">In the Report Data pane, right-click a data source, and then click **Add Dataset**.</span></span>  
  
2.  <span data-ttu-id="acabc-160">Em **Nome**, digite o nome do conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="acabc-160">In **Name**, type the name of the dataset.</span></span>  
  
3.  <span data-ttu-id="acabc-161">Em **Fonte de Dados**, verifique se o nome é o nome da fonte de dados escolhida na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="acabc-161">In **Data source**, verify the name is the name of the data source you chose in step 1.</span></span>  
  
4.  <span data-ttu-id="acabc-162">Em **Tipo de consulta**, escolha o tipo de consulta para a fonte de dados selecionada.</span><span class="sxs-lookup"><span data-stu-id="acabc-162">In **Query type**, choose the type of query for the selected data source.</span></span> <span data-ttu-id="acabc-163">Neste tópico, o tipo de consulta **Text** é assumido.</span><span class="sxs-lookup"><span data-stu-id="acabc-163">In this topic, query type **Text** is assumed.</span></span>  
  
5.  <span data-ttu-id="acabc-164">Em **Consulta**, digite a consulta a ser usada para recuperar valores para este parâmetro.</span><span class="sxs-lookup"><span data-stu-id="acabc-164">In **Query**, type the query to use to retrieve values for this parameter.</span></span> <span data-ttu-id="acabc-165">Normalmente, consultas para parâmetros dependentes incluem parâmetros de consulta para cada parâmetro do qual este parâmetro é dependente.</span><span class="sxs-lookup"><span data-stu-id="acabc-165">Queries for dependent parameters typically include query parameters for each parameter that this parameter is dependent on.</span></span> <span data-ttu-id="acabc-166">Por exemplo, para criar uma consulta para um parâmetro que fornece todos os valores de subcategoria (parâmetro dependente) para uma categoria (parâmetro independente), você pode usar uma instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="acabc-166">For example, to create a query for a parameter that provides all subcategory (dependent parameter) values for a category (independent parameter), you might use a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement similar to the following:</span></span>  
  
    ```  
    SELECT DISTINCT Subcategory FROM <table>   
    WHERE (Category = @Category)  
    ```  
  
     <span data-ttu-id="acabc-167">Na cláusula WHERE, Category é o nome de um campo de \<table> e @Category é um parâmetro de consulta.</span><span class="sxs-lookup"><span data-stu-id="acabc-167">In the WHERE clause, Category is the name of a field from \<table> and @Category is a query parameter.</span></span> <span data-ttu-id="acabc-168">Essa instrução gera uma lista de subcategorias para a categoria especificada em @Category.</span><span class="sxs-lookup"><span data-stu-id="acabc-168">This statement produces a list of subcategories for the category specified in @Category.</span></span> <span data-ttu-id="acabc-169">Em tempo de execução, esse valor será preenchido com o valor escolhido pelo usuário para o parâmetro de relatório que tem o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="acabc-169">At run time, this value will be filled in with the value that the user chooses for the report parameter that has the same name.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="acabc-170">Em seguida, você definirá as propriedades do segundo parâmetro para usar este conjunto de dados para popular seus valores disponíveis em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="acabc-170">Next, you will set the properties of the second parameter to use this dataset to populate its available values at run time.</span></span>  
  
### <a name="to-set-available-values-for-a-report-parameter"></a><span data-ttu-id="acabc-171">Para definir os valores disponíveis para um parâmetro de relatório</span><span class="sxs-lookup"><span data-stu-id="acabc-171">To set available values for a report parameter</span></span>  
  
1.  <span data-ttu-id="acabc-172">No painel Dados do Relatório, na pasta Parâmetros, clique com o botão direito do mouse no primeiro parâmetro e clique em **Propriedades do Parâmetro**.</span><span class="sxs-lookup"><span data-stu-id="acabc-172">In the Report Data pane, in the Parameters folder, right-click the first parameter, and then click **Parameter Properties**.</span></span>  
  
2.  <span data-ttu-id="acabc-173">Em **Nome**, verifique se o nome do parâmetro está correto.</span><span class="sxs-lookup"><span data-stu-id="acabc-173">In **Name**, verify that the name of the parameter is correct.</span></span>  
  
3.  <span data-ttu-id="acabc-174">Clique em **Valores Disponíveis**.</span><span class="sxs-lookup"><span data-stu-id="acabc-174">Click **Available Values**.</span></span>  
  
4.  <span data-ttu-id="acabc-175">Clique em **Obter valores de uma consulta**.</span><span class="sxs-lookup"><span data-stu-id="acabc-175">Click **Get values from a query**.</span></span>  
  
5.  <span data-ttu-id="acabc-176">Em **Conjunto de Dados**, na lista suspensa, clique no nome do conjunto de dados criado no procedimento anterior.</span><span class="sxs-lookup"><span data-stu-id="acabc-176">In **Dataset**, from the drop-down list, click the name of the dataset you created in the previous procedure.</span></span>  
  
6.  <span data-ttu-id="acabc-177">No campo **Valor** , clique no nome do campo que fornece o valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="acabc-177">In **Value** field, click the name of the field that provides the parameter value.</span></span>  
  
7.  <span data-ttu-id="acabc-178">No campo **Rótulo** , clique no nome do campo que fornece o rótulo do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="acabc-178">In **Label** field, click the name of the field that provides the parameter label.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-test-the-cascading-parameters"></a><span data-ttu-id="acabc-179">Para testar os parâmetros em cascata</span><span class="sxs-lookup"><span data-stu-id="acabc-179">To test the cascading parameters</span></span>  
  
1.  <span data-ttu-id="acabc-180">Clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="acabc-180">Click **Run**.</span></span>  
  
2.  <span data-ttu-id="acabc-181">Na lista suspensa do primeiro parâmetro independente, escolha um valor.</span><span class="sxs-lookup"><span data-stu-id="acabc-181">From the drop-down list for the first, independent parameter, choose a value.</span></span>  
  
     <span data-ttu-id="acabc-182">O processador de relatório executa a consulta de conjunto de dados para o próximo parâmetro e passa para ele o valor que você escolheu para o primeiro parâmetro.</span><span class="sxs-lookup"><span data-stu-id="acabc-182">The report processor runs the dataset query for the next parameter and passes it the value you chose for the first parameter.</span></span> <span data-ttu-id="acabc-183">A lista suspensa do segundo parâmetro é populada com os valores disponíveis com base no valor do primeiro parâmetro.</span><span class="sxs-lookup"><span data-stu-id="acabc-183">The drop-down list for the second parameter is populated with the available values based on the first parameter value.</span></span>  
  
3.  <span data-ttu-id="acabc-184">Na lista suspensa do segundo, parâmetro dependente, escolha um valor.</span><span class="sxs-lookup"><span data-stu-id="acabc-184">From the drop-down list for the second, dependent parameter, choose a value.</span></span>  
  
     <span data-ttu-id="acabc-185">O relatório não é executado automaticamente depois que você escolhe o último parâmetro de forma que você pode alterar sua escolha.</span><span class="sxs-lookup"><span data-stu-id="acabc-185">The report does not run automatically after you choose the last parameter so that you can change your choice.</span></span>  
  
4.  <span data-ttu-id="acabc-186">Clique em **Exibir Relatório**.</span><span class="sxs-lookup"><span data-stu-id="acabc-186">Click **View Report**.</span></span> <span data-ttu-id="acabc-187">O relatório atualiza a exibição com base nos parâmetros escolhidos.</span><span class="sxs-lookup"><span data-stu-id="acabc-187">The report updates the display based on the parameters you have chosen.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acabc-188">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="acabc-188">See Also</span></span>  
 <span data-ttu-id="acabc-189">[Adicionar, alterar ou excluir um parâmetro de relatório &#40;Construtor de Relatórios e SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="acabc-189">[Add, Change, or Delete a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="acabc-190">[Parâmetros de relatório &#40;Construtor de Relatórios e Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="acabc-190">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="acabc-191">[Tutorial: adicionar um parâmetro ao seu relatório &#40;Construtor de Relatórios&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="acabc-191">[Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span></span>  
 <span data-ttu-id="acabc-192">[TUTORIAIS &#40;Construtor de Relatórios&#41;](../report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="acabc-192">[Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md) </span></span>  
 <span data-ttu-id="acabc-193">[Adicionar filtros de conjunto de dados, filtros de região e filtros de grupo &#40;Construtor de Relatórios e SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="acabc-193">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 [<span data-ttu-id="acabc-194">Conjuntos de itens de relatório inseridos e conjuntos de &#40;compartilhados Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="acabc-194">Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;</span></span>](../report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)  
  
  
