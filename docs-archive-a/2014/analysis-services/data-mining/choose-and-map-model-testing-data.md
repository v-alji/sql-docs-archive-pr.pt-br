---
title: Escolher e mapear dados de teste de modelo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- columns [data mining], mining accuracy charts
- Mining Accuracy Chart [Analysis Services], column mappings
- input column mapping [Analysis Services]
- mapping input columns [Analysis Services]
ms.assetid: be0d9f20-40c3-4dac-81da-281cfe724126
author: minewiskan
ms.author: owend
ms.openlocfilehash: 84f1d01c40070069d610bb028ab003223c5afbcd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572849"
---
# <a name="choose-and-map-model-testing-data"></a><span data-ttu-id="9c3d3-102">Escolher e mapear dados de testes modelo</span><span class="sxs-lookup"><span data-stu-id="9c3d3-102">Choose and Map Model Testing Data</span></span>
  <span data-ttu-id="9c3d3-103">Para criar um gráfico de precisão no [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], escolha os dados que serão usados para testar o modelo e mapeie os dados para o modelo.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-103">To create an accuracy chart in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you must choose the data that will be used to test the model, and map the data to the model.</span></span>  
  
 <span data-ttu-id="9c3d3-104">Por padrão, o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] usará os dados de teste do modelo de mineração, desde que você tenha criado um conjunto de dados de controle quando criou a estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-104">By default, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will use the mining model testing data, provided that you created a holdout data set when you built the mining structure.</span></span> <span data-ttu-id="9c3d3-105">A criação de um conjunto de testes de controle é a maneira mais fácil de testar modelos baseados na mesma estrutura de mineração porque os nomes de colunas e os tipos de dados sempre coincidirão com o modelo. Além disso, você tem uma garantia razoável de que a distribuição dos dados é semelhante.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-105">Creating a holdout test set is the easiest way to test models that are based on the same mining structure, because the column names and data types will always match the model, and you can be reasonably assured that the distribution of the data is similar.</span></span> <span data-ttu-id="9c3d3-106">Somado a isso, o designer criará automaticamente as relações entre as colunas de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-106">Also, the designer will automatically create the relationships between the input and model columns.</span></span>  
  
 <span data-ttu-id="9c3d3-107">Outra alternativa é especificar uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-107">Alternatively, you can specify an external source of data.</span></span> <span data-ttu-id="9c3d3-108">Para dados externos, há alguns requisitos adicionais:</span><span class="sxs-lookup"><span data-stu-id="9c3d3-108">For external data, there are some additional requirements:</span></span>  
  
-   <span data-ttu-id="9c3d3-109">O conjunto de dados externos deve ser definido como uma exibição da fonte de dados em uma instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c3d3-109">The external data set must be defined as a data source view in an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="9c3d3-110">O conjunto de dados externos deve conter pelo menos uma coluna que possa ser mapeada para a coluna previsível no modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-110">The external data set must at least contain one column that can be mapped to the predictable column in the mining model.</span></span> <span data-ttu-id="9c3d3-111">Você pode optar por ignorar algumas colunas.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-111">You can choose to ignore some columns.</span></span>  
  
-   <span data-ttu-id="9c3d3-112">Você não pode adicionar novas colunas nem mapear colunas em uma exibição de fonte de dados diferente.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-112">You cannot add new columns or map columns in a different data source view.</span></span> <span data-ttu-id="9c3d3-113">A exibição da fonte de dados selecionada deve conter todas as colunas que você precisa para a consulta de previsão.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-113">The data source view that you select must contain all the columns that you need for the prediction query.</span></span>  
  
-   <span data-ttu-id="9c3d3-114">Se os nomes da coluna externa coincidirem exatamente com os nomes no modelo, o designer irá mapeá-los para você.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-114">If the external column names exactly match those in the model, the designer will map them for you.</span></span> <span data-ttu-id="9c3d3-115">Se os mapeamentos estiverem errados, você poderá alterá-los, ou excluir e criar novos mapeamentos para colunas existentes.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-115">If the mappings are wrong, you can change them, or delete and create new mappings for existing columns.</span></span>  
  
-   <span data-ttu-id="9c3d3-116">Se você usar uma fonte de dados externa, poderá aplicar filtros para restringir os dados de testes a um subconjunto relevante de casos.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-116">If you use an external data source, you can apply filters to restrict the testing data to a relevant subset of cases.</span></span>  
  
-   <span data-ttu-id="9c3d3-117">Mesmo ao usar o conjunto de testes de controle, lembre-se de que filtros podem causar diferenças entre os dados de testes associados com uma estrutura de mineração e os casos de testes do modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-117">Even when you use the holdout test set, you should be aware that filters can cause differences between the testing data associated with a mining structure and the mining model test cases.</span></span>  
  
 <span data-ttu-id="9c3d3-118">Este tópico descreve como escolher e mapear dados de testes:</span><span class="sxs-lookup"><span data-stu-id="9c3d3-118">This topic describes how to choose and map the testing data:</span></span>  
  
 [<span data-ttu-id="9c3d3-119">Selecione tabelas de entrada para testar a precisão de um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="9c3d3-119">Select input tables to test the accuracy of a mining model</span></span>](#bkmk_SelectInputs)  
  
 [<span data-ttu-id="9c3d3-120">Mapeie colunas modelo para as colunas nos dados de testes</span><span class="sxs-lookup"><span data-stu-id="9c3d3-120">Map model columns to the columns in the testing data</span></span>](#bkmk_MapColumns)  
  
 [<span data-ttu-id="9c3d3-121">Altere a forma como colunas nos dados de testes são mapeadas para o modelo</span><span class="sxs-lookup"><span data-stu-id="9c3d3-121">Change the way that columns in the testing data are mapped to the model</span></span>](#bkmk_ChangeMappings)  
  
##  <a name="to-select-input-tables-to-test-the-accuracy-of-a-mining-model"></a><a name="bkmk_SelectInputs"></a> <span data-ttu-id="9c3d3-122">Para selecionar tabelas de entrada para testar a exatidão de um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="9c3d3-122">To select input tables to test the accuracy of a mining model</span></span>  
  
1.  <span data-ttu-id="9c3d3-123">No Designer de Mineração de Dados do [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], clique duas vezes na estrutura de mineração que contém os modelos com os quais deseja fazer o gráfico.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-123">In Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], double-click the mining structure that contains the models you want to chart.</span></span>  
  
2.  <span data-ttu-id="9c3d3-124">Selecione a guia **Gráfico de Precisão de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="9c3d3-124">Select the **Mining Accuracy Chart** tab.</span></span>  
  
3.  <span data-ttu-id="9c3d3-125">Na **Guia Seleção de Entrada** da exibição **Gráfico de Precisão de Mineração** , selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="9c3d3-125">On the **Input Selection Tab** of the **Mining Accuracy Chart** view, select one of the following options:</span></span>  
  
     <span data-ttu-id="9c3d3-126">**Usar casos de teste do modelo de mineração**</span><span class="sxs-lookup"><span data-stu-id="9c3d3-126">**Use mining model test cases**</span></span>  
  
     <span data-ttu-id="9c3d3-127">**Usar casos de teste da estrutura de mineração**</span><span class="sxs-lookup"><span data-stu-id="9c3d3-127">**Use mining structure test cases**</span></span>  
  
     <span data-ttu-id="9c3d3-128">**Especificar um conjunto de dados diferente**</span><span class="sxs-lookup"><span data-stu-id="9c3d3-128">**Specify a different data set**</span></span>  
  
4.  <span data-ttu-id="9c3d3-129">Se você selecionou **Especificar um conjunto de dados diferente**, opcionalmente, clique em **Abrir Editor de Filtro** para criar condições de filtro no conjunto de dados de entrada.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-129">If you selected **Specify a different data set**, optionally click **Open Filter Editor** to create filter conditions on the input data set.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="9c3d3-130">Clique na guia **Gráfico de Comparação de Precisão** ou na guia **Matriz de Classificação** para criar automaticamente o gráfico usando os dados de teste recém-especificados.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-130">Click the **Lift Chart** tab or the **Classification Matrix** tab to automatically build the chart by using the testing data you specified.</span></span>  
  
##  <a name="to-map-model-columns-to-the-columns-in-the-testing-data"></a><a name="bkmk_MapColumns"></a> <span data-ttu-id="9c3d3-131">Para mapear colunas modelo para as colunas nos dados de testes</span><span class="sxs-lookup"><span data-stu-id="9c3d3-131">To map model columns to the columns in the testing data</span></span>  
  
1.  <span data-ttu-id="9c3d3-132">Clique duas vezes na estrutura de mineração que contém os modelos que você deseja incluir no gráfico, para abrir a estrutura e seus modelos no Designer de Mineração de Dados.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-132">Double-click the mining structure that contains the models you want to chart, to open the structure and models in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="9c3d3-133">Selecione a guia **Gráfico de Precisão da Mineração** e, em seguida, selecione a guia **Seleção de Entrada** .</span><span class="sxs-lookup"><span data-stu-id="9c3d3-133">Select the **Mining Accuracy Chart** tab, and then select the **Input Selection** tab.</span></span>  
  
3.  <span data-ttu-id="9c3d3-134">Na guia **Seleção de Entrada** , em **Selecionar conjunto de dados a ser usado para Gráfico de Precisão**, selecione **Especificar um conjunto de dados diferente**.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-134">In the **Input Selection** tab, under **Select data set to be used for Accuracy Chart**, select **Specify a different data set**.</span></span>  
  
4.  <span data-ttu-id="9c3d3-135">Clique no botão procurar **(...)** para abrir uma caixa de diálogo e criar a definição do conjunto de dados externos.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-135">Click the browse button **(...)** to open a dialog box and build the definition of the external data set.</span></span>  
  
5.  <span data-ttu-id="9c3d3-136">Na caixa de diálogo **Selecionar Estrutura de Mineração** , selecione a estrutura de mineração que contém os modelos com os quais deseja trabalhar e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-136">In the **Select Mining Structure** dialog box, select the mining structure that contains the models you want to work with, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="9c3d3-137">Na tabela **Selecionar Tabela(s) de Entrada** da guia **Gráfico de Precisão de Mineração** , clique em **Selecionar Tabela de Casos** para abrir a caixa de diálogo **Selecionar Tabela** .</span><span class="sxs-lookup"><span data-stu-id="9c3d3-137">On the **Select Input Table(s)** table of the **Mining Accuracy Chart** tab, click **Select Case Table** to open the **Select Table** dialog box.</span></span>  
  
7.  <span data-ttu-id="9c3d3-138">Na caixa de diálogo **Selecionar Tabela** , selecione uma fonte de dados na lista **Fonte de Dados** .</span><span class="sxs-lookup"><span data-stu-id="9c3d3-138">In the **Select Table** dialog box, select a data source from the **Data Source** list.</span></span> <span data-ttu-id="9c3d3-139">Escolha uma tabela que contém os dados que deseja usar nas consultas de previsão para determinar a precisão dos modelos.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-139">Choose a table that contains the data that you want to use in the prediction queries to determine the accuracy of the models.</span></span>  
  
8.  <span data-ttu-id="9c3d3-140">Na caixa **Nome de Tabela/Exibição** , selecione a tabela que contém os dados que deseja usar para testar os modelos.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-140">In the **Table/View Name** box, select the table that contains the data that you want to use to test the models.</span></span>  
  
9. <span data-ttu-id="9c3d3-141">Edite os mapeamentos, se necessário.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-141">Edit the mappings, if necessary.</span></span> <span data-ttu-id="9c3d3-142">As colunas da estrutura de mineração são mapeadas automaticamente para colunas com o mesmo nome na tabela de entrada.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-142">Columns in the mining structure are automatically mapped to the columns with the same name in the input table.</span></span> <span data-ttu-id="9c3d3-143">Para criar mapeamentos manualmente, clique em uma coluna na tabela **Selecionar Tabela(s) de Entrada** e arraste-a na coluna correspondente na tabela **Estrutura de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="9c3d3-143">To manually create mappings, click a column in the **Select Input Table(s)** table and drag it onto the corresponding column in the **Mining Structure** table.</span></span> <span data-ttu-id="9c3d3-144">Para excluir um mapeamento, clique na linha que vincula a coluna na tabela **Estrutura de Mineração** à coluna mapeada na tabela **Selecionar Tabela(s) de Entrada** e pressione DELETE.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-144">To delete a mapping, click the line that links the column in the **Mining Structure** table to the mapped column in the **Select Input Table(s)** table, and then press DELETE.</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="to-modify-the-way-input-data-is-mapped-to-the-model"></a><a name="bkmk_ChangeMappings"></a><span data-ttu-id="9c3d3-145">Para modificar a maneira como os dados de entrada são mapeados para o modelo</span><span class="sxs-lookup"><span data-stu-id="9c3d3-145">To modify the way input data is mapped to the model</span></span>  
  
1.  <span data-ttu-id="9c3d3-146">No Designer do Data Mining, clique duas vezes na estrutura que contém os modelos com os quais deseja criar o gráfico.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-146">In Data Mining Designer, double-click the structure that contains the models you want to chart.</span></span>  
  
2.  <span data-ttu-id="9c3d3-147">Selecione a guia **Gráfico de Precisão de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="9c3d3-147">Select the **Mining Accuracy Chart** tab.</span></span>  
  
3.  <span data-ttu-id="9c3d3-148">Clique na guia **Seleção de Entrada** .</span><span class="sxs-lookup"><span data-stu-id="9c3d3-148">Click the **Input Selection** tab.</span></span>  
  
4.  <span data-ttu-id="9c3d3-149">Em **selecionar conjunto de dados a ser usado para o gráfico de precisão**, selecione a opção **especificar um conjunto de dados diferente**.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-149">In **Select data set to be used for Accuracy Chart**, select the option **Specify a different data set**.</span></span>  
  
5.  <span data-ttu-id="9c3d3-150">Clique no botão procurar **(...)** para abrir uma caixa de diálogo e criar a definição da fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-150">Click the browse button **(...)** to open a dialog box and build the definition of the external data source.</span></span>  
  
6.  <span data-ttu-id="9c3d3-151">Na caixa de diálogo **Especificar Mapeamento de Coluna** , clique em **Selecionar Tabela de Casos**.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-151">In the **Specify Column Mapping** dialog box, click **Select Case Table**.</span></span>  
  
7.  <span data-ttu-id="9c3d3-152">Na caixa de diálogo Selecionar Tabela, selecione uma fonte de dados na lista e a tabela que contém os dados de caso.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-152">In the Select Table dialog box, Select a data source view from the list, and select the table that contains the case data.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="9c3d3-153">Se a tabela necessária não estiver disponível, feche a caixa de diálogo e crie uma nova exibição da fonte de dados que contenha a tabela.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-153">If the tables you need are not available, close the dialog box and create a new data source view that contains the table.</span></span> <span data-ttu-id="9c3d3-154">Para obter informações sobre como criar uma exibição de fonte de dados, consulte [Definindo uma exibição da fonte de dados &#40;Analysis Services&#41;](../multidimensional-models/defining-a-data-source-view-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="9c3d3-154">For information about how to create a data source view, see [Defining a Data Source View &#40;Analysis Services&#41;](../multidimensional-models/defining-a-data-source-view-analysis-services.md).</span></span>  
  
9. <span data-ttu-id="9c3d3-155">Se o modelo de mineração tiver uma tabela aninhada, clique em **Selecionar Tabela Aninhada**e selecione a tabela aninhada na lista de tabelas na exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-155">If the mining model contains a nested table, click **Select Nested Table**, and select the nested table from the list of tables in the data source view.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
10. <span data-ttu-id="9c3d3-156">Selecione a linha de junção do mapeamento que você quer modificar e, depois, **Modificar Conexões**.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-156">Select the join line of the mapping you want to modify, and select **Modify Connections**.</span></span>  
  
     <span data-ttu-id="9c3d3-157">A caixa de diálogo **Modificar Mapeamento** abre.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-157">The **Modify Mapping** dialog box opens.</span></span> <span data-ttu-id="9c3d3-158">Na tabela nessa caixa de diálogo, **Colunas de Estrutura de Mineração** lista cada coluna que a estrutura de mineração selecionada contém, e **Colunas da tabela** lista as colunas das tabelas de entrada que estão mapeadas para colunas na estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-158">In the table in this dialog box, **Mining Structure Column** lists each column that the selected mining structure contains, and **Table Column** lists the columns from input tables that are mapped to columns in the mining structure.</span></span>  
  
11. <span data-ttu-id="9c3d3-159">Em **Coluna da Tabela**, selecione a linha que corresponde à linha em **Colunas de Estrutura de Mineração** para a qual você deseja modificar uma relação.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-159">Under **Table Column**, select the row that corresponds to the row under **Mining Structure Column** for which you want to modify a relationship.</span></span> <span data-ttu-id="9c3d3-160">Selecione uma nova coluna ou a entrada em branco na lista para excluir a coluna.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-160">Select a new column from the list, or select the blank entry from the list to delete the column.</span></span>  
  
12. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="9c3d3-161">Os mapeamentos das novas colunas são exibidos na caixa de diálogo **Especificar Mapeamento de Coluna** .</span><span class="sxs-lookup"><span data-stu-id="9c3d3-161">The new column mappings are displayed in the **Specify Column Mapping** dialog box.</span></span> <span data-ttu-id="9c3d3-162">Você pode remover um mapeamento selecionando a linha entre as colunas e pressionando a tecla DELETE.</span><span class="sxs-lookup"><span data-stu-id="9c3d3-162">You can remove a mapping by selecting the line between the columns and pressing the DELETE key.</span></span> <span data-ttu-id="9c3d3-163">Você também pode criar uma nova conexão selecionando uma coluna na tabela **Estrutura de Mineração** e arrastando-a para a coluna correspondente na tabela **Tabelas SelectInput** .</span><span class="sxs-lookup"><span data-stu-id="9c3d3-163">You can create a new connection by selecting a column in the **Mining Structure** table and dragging it to the corresponding column in the **SelectInput Table(s)** table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c3d3-164">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9c3d3-164">See Also</span></span>  
 [<span data-ttu-id="9c3d3-165">Tarefas de teste e validação e instruções &#40;Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="9c3d3-165">Testing and Validation Tasks and How-tos &#40;Data Mining&#41;</span></span>](testing-and-validation-tasks-and-how-tos-data-mining.md)  
  
  
