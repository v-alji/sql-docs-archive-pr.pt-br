---
title: Aplicar filtros aos dados de teste de modelo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- input row filtering [SQL Server]
- filtering input rows [Analysis Services]
- Mining Accuracy Chart [Analysis Services], filtering input rows
ms.assetid: 9ccc9a23-5597-4b35-a05f-2fc8eb885147
author: minewiskan
ms.author: owend
ms.openlocfilehash: d1fd2b643ae4f7d831cab980ca45b7d43d8b58f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569735"
---
# <a name="apply-filters-to-model-testing-data"></a><span data-ttu-id="b25b8-102">Aplicar filtros a dados de testes de modelo</span><span class="sxs-lookup"><span data-stu-id="b25b8-102">Apply Filters to Model Testing Data</span></span>
  <span data-ttu-id="b25b8-103">Quando você especifica uma fonte de dados externa a ser usada para testar um modelo, pode opcionalmente aplicar um filtro para restringir os dados de entrada.</span><span class="sxs-lookup"><span data-stu-id="b25b8-103">When you specify an external data source to use in testing a model, you can optionally apply a filter to restrict the input data.</span></span> <span data-ttu-id="b25b8-104">Por exemplo, talvez queira testar o modelo especificamente para previsões sobre clientes com determinada faixa de renda.</span><span class="sxs-lookup"><span data-stu-id="b25b8-104">For example, you might want to test the model specifically for predictions on customers in a certain income range.</span></span>  
  
 <span data-ttu-id="b25b8-105">Por exemplo, no cenário de endereçamento de destino AdventureWorks, você pode criar uma expressão de filtro como a seguinte em ProspectiveBuyer, que é a tabela que contém os dados de teste e restringir os casos de teste por intervalo de renda:</span><span class="sxs-lookup"><span data-stu-id="b25b8-105">For example, in the AdventureWorks targeted mailing scenario, you can create a filter expression like the following one on ProspectiveBuyer, which is the table that contains the testing data, and restrict testing cases by income range:</span></span>  
  
 `[YearlyIncome] = '50000'`  
  
 <span data-ttu-id="b25b8-106">O comportamento de filtros é um pouco diferente, dependendo se você está filtrando dados de treinamento do modelo ou um conjunto de dados de teste:</span><span class="sxs-lookup"><span data-stu-id="b25b8-106">The behavior of filters is slightly different, depending on whether you are filtering model training data or a testing data set:</span></span>  
  
-   <span data-ttu-id="b25b8-107">Quando você define um filtro em um conjunto de dados de teste, cria uma cláusula WHERE nos dados de entrada.</span><span class="sxs-lookup"><span data-stu-id="b25b8-107">When you define a filter on a testing data set, you create a WHERE clause on the incoming data.</span></span> <span data-ttu-id="b25b8-108">Se estiver filtrando um conjunto de dados de entrada usado para avaliar um modelo, a expressão de filtro será convertida em uma instrução Transact-SQL e aplicada à tabela de entrada quando o gráfico for criado.</span><span class="sxs-lookup"><span data-stu-id="b25b8-108">If you are filtering an input data set used for evaluating a model, the filter expression is translated to a Transact-SQL statement and applied to the input table when the chart is created.</span></span> <span data-ttu-id="b25b8-109">Como resultado, o número de casos de teste pode ser reduzido consideravelmente.</span><span class="sxs-lookup"><span data-stu-id="b25b8-109">As a result, the number of test cases can be greatly reduced.</span></span>  
  
-   <span data-ttu-id="b25b8-110">Quando você aplica um filtro a um modelo de mineração, a expressão de filtro que você cria é convertida em uma instrução DMX (extensões DMX), e aplicada ao modelo individual.</span><span class="sxs-lookup"><span data-stu-id="b25b8-110">When you apply a filter to a mining model, the filter expression that you create is translated to a Data Mining Extensions (DMX) statement, and applied to the individual model.</span></span> <span data-ttu-id="b25b8-111">Portanto, quando você aplica um filtro a um modelo, somente um subconjunto dos dados originais é usado para treinar o modelo.</span><span class="sxs-lookup"><span data-stu-id="b25b8-111">Therefore, when you apply a filter to a model, only a subset of the original data is used to train the model.</span></span> <span data-ttu-id="b25b8-112">Isso pode gerar problemas quando você filtra o modelo de treinamento com um conjunto de critérios, de forma que o modelo seja ajustado a determinado conjunto de dados e, depois, testa o modelo com outro conjunto de critérios.</span><span class="sxs-lookup"><span data-stu-id="b25b8-112">This can cause problems if you filter the training model with one set of criteria, so that the model is tuned to a certain set of data, and then test the model with another set of criteria.</span></span>  
  
-   <span data-ttu-id="b25b8-113">Se você definiu um conjunto de dados de teste ao criar a estrutura, os casos do modelo usados para treinamento incluirão apenas os casos que constam no conjunto de treinamento da estrutura de mineração **e** que atendam as condições do filtro.</span><span class="sxs-lookup"><span data-stu-id="b25b8-113">If you defined a testing data set when you created the structure, the model cases used for training include only those cases that are in the mining structure training set **and** which meet the conditions of the filter.</span></span> <span data-ttu-id="b25b8-114">Portanto, quando você está testando um modelo e seleciona a opção **Usar casos de teste do modelo de mineração**, os casos de testes incluem somente os casos que estão no conjunto de testes da estrutura de mineração e que atendem às condições do filtro.</span><span class="sxs-lookup"><span data-stu-id="b25b8-114">Thus, when you are testing a model and select the option **Use mining model test cases**, the testing cases will include only the cases that are in the mining structure test set and which meet the conditions of the filter.</span></span> <span data-ttu-id="b25b8-115">Entretanto, se você não definiu um conjunto de dados de validação, os casos do modelo usados para testes incluirão todos os casos do conjunto de dados que atendam às condições de filtro</span><span class="sxs-lookup"><span data-stu-id="b25b8-115">However, if you did not define a holdout data set, the model cases used for testing include all the cases in the data set that meet the filter conditions</span></span>  
  
-   <span data-ttu-id="b25b8-116">As condições de filtro que você aplica a um modelo também afetam as consultas de detalhamento nos casos do modelo.</span><span class="sxs-lookup"><span data-stu-id="b25b8-116">Filter conditions that you apply on a model also affect drillthrough queries on the model cases.</span></span>  
  
 <span data-ttu-id="b25b8-117">Em suma, quando você testa vários modelos, mesmo que todos os modelos se baseiem na mesma estrutura de mineração, lembre-se de que os modelos potencialmente usam diferentes subconjuntos de dados para treinamentos e testes.</span><span class="sxs-lookup"><span data-stu-id="b25b8-117">In summary, when you test multiple models, even if all the models are based on the same mining structure, you must be aware that the models potentially use different subsets of data for training and testing.</span></span> <span data-ttu-id="b25b8-118">Isso pode ter os seguintes efeitos em gráficos de precisão:</span><span class="sxs-lookup"><span data-stu-id="b25b8-118">This can have the following effects on accuracy charts:</span></span>  
  
-   <span data-ttu-id="b25b8-119">O número total de casos nos conjuntos de testes varia entre os modelos testados.</span><span class="sxs-lookup"><span data-stu-id="b25b8-119">The total number of cases in the testing sets can vary among the models being tested.</span></span>  
  
-   <span data-ttu-id="b25b8-120">Os percentuais de cada modelo podem não estar alinhados no gráfico quando os modelos usam diferentes subconjuntos de dados de treinamento ou dados de teste.</span><span class="sxs-lookup"><span data-stu-id="b25b8-120">The percentages for each model may not align in the chart, if the models use different subsets of training data or testing data.</span></span>  
  
 <span data-ttu-id="b25b8-121">Para determinar se um modelo contém um filtro predefinido que possa afetar os resultados, você pode procurar a propriedade **Filter** no painel **Propriedade** ou consultar o modelo usando os conjuntos de linhas do esquema de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="b25b8-121">To determine whether a model contains a predefined filter that might affect results, you can look for the **Filter** property in the **Property** pane, or you can query the model by using the data mining schema rowsets.</span></span> <span data-ttu-id="b25b8-122">Por exemplo, esta consulta retorna o texto de filtro para o modelo especificado:</span><span class="sxs-lookup"><span data-stu-id="b25b8-122">For example, the following query returns the filter text for the specified model:</span></span>  
  
 `SELECT [FILTER] FROM $system.DMSCHEMA_MINING_MODELS WHERE MODEL_NAME = 'name of model'`  
  
> [!WARNING]  
>  <span data-ttu-id="b25b8-123">Se desejar remover o filtro de um modelo de mineração existente ou alterar as condições do filtro, reprocesse o modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="b25b8-123">If you want to remove the filter from an existing mining model, or change the filter conditions, you must reprocess the mining model.</span></span>  
  
 <span data-ttu-id="b25b8-124">Para obter mais informações sobre os tipos de filtros que você pode aplicar e como as expressões de filtro são avaliadas, consulte [Sintaxe de filtro de modelo e exemplos &#40;Analysis Services – Mineração de dados&#41;](model-filter-syntax-and-examples-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="b25b8-124">For more information about the kinds of filters you can apply, and how filter expressions are evaluated, see [Model Filter Syntax and Examples &#40;Analysis Services - Data Mining&#41;](model-filter-syntax-and-examples-analysis-services-data-mining.md).</span></span>  
  
### <a name="create-a-filter-on-external-testing-data"></a><span data-ttu-id="b25b8-125">Criar um filtro em dados de testes externos</span><span class="sxs-lookup"><span data-stu-id="b25b8-125">Create a filter on external testing data</span></span>  
  
1.  <span data-ttu-id="b25b8-126">Clique duas vezes na estrutura de mineração que contém o modelo a ser testado, para abrir o Designer de Mineração de Dados.</span><span class="sxs-lookup"><span data-stu-id="b25b8-126">Double-click the mining structure that contains the model you want to test, to open Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="b25b8-127">Selecione a guia **Gráfico de Precisão da Mineração** e, em seguida, selecione a guia **Seleção de Entrada** .</span><span class="sxs-lookup"><span data-stu-id="b25b8-127">Select the **Mining Accuracy Chart** tab, and then select the **Input Selection** tab.</span></span>  
  
3.  <span data-ttu-id="b25b8-128">Na guia **Seleção de Entrada** , em **Selecionar conjunto de dados a ser usado para Gráfico de Precisão**, selecione a opção **Especificar um conjunto de dados diferente**.</span><span class="sxs-lookup"><span data-stu-id="b25b8-128">On the **Input Selection** tab, under **Select data set to be used for Accuracy Chart**, select the option **Specify a different data set**.</span></span>  
  
4.  <span data-ttu-id="b25b8-129">Clique no botão procurar **(...)** para abrir uma caixa de diálogo e escolha o conjunto de dados externos.</span><span class="sxs-lookup"><span data-stu-id="b25b8-129">Click the browse button **(...)** to open a dialog box and choose the external data set.</span></span>  
  
5.  <span data-ttu-id="b25b8-130">Escolha a tabela de caso e adicione uma tabela aninhada, caso necessário.</span><span class="sxs-lookup"><span data-stu-id="b25b8-130">Choose the case table, and add a nested table if necessary.</span></span> <span data-ttu-id="b25b8-131">Mapeie colunas no modelo para colunas no conjunto de dados externo, caso necessário.</span><span class="sxs-lookup"><span data-stu-id="b25b8-131">Map columns in the model to columns in the external data set as necessary.</span></span> <span data-ttu-id="b25b8-132">Feche a caixa de diálogo **Especificar Mapeamento de Coluna** para salvar a definição de tabela de origem.</span><span class="sxs-lookup"><span data-stu-id="b25b8-132">Close the **Specify Column Mapping** dialog box to save the source table definition.</span></span>  
  
6.  <span data-ttu-id="b25b8-133">Clique em **Abrir Editor de Filtro** para definir um filtro para o conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="b25b8-133">Click **Open Filter Editor** to define a filter for the data set.</span></span>  
  
     <span data-ttu-id="b25b8-134">A caixa de diálogo **Filtro do Conjunto de Dados** se abre.</span><span class="sxs-lookup"><span data-stu-id="b25b8-134">The **Data Set Filter** dialog box opens.</span></span> <span data-ttu-id="b25b8-135">Se a estrutura contiver uma tabela aninhada, você poderá criar um filtro em duas partes.</span><span class="sxs-lookup"><span data-stu-id="b25b8-135">If the structure contains a nested table, you can create a filter in two parts.</span></span> <span data-ttu-id="b25b8-136">Primeiro, defina as condições na tabela de casos, utilizando a caixa de diálogo **Filtro do Conjunto de Dados** e, em seguida, defina as condições nas linhas aninhadas utilizando a caixa de diálogo **Filtrar** .</span><span class="sxs-lookup"><span data-stu-id="b25b8-136">First, set conditions on the case table by using the **Data Set Filter** dialog box, and then set conditions on the nested rows by using the **Filter** dialog box.</span></span>  
  
7.  <span data-ttu-id="b25b8-137">Na caixa de diálogo **Filtro do Conjunto de Dados** , clique na linha superior da grade, em **Coluna da Estrutura de Mineração**, e selecione uma tabela ou coluna da lista.</span><span class="sxs-lookup"><span data-stu-id="b25b8-137">In the **Data Set Filter** dialog box, click the top row in the grid, under **Mining Structure Column**, and select a table or column from the list.</span></span>  
  
     <span data-ttu-id="b25b8-138">Se a exibição da fonte de dados contiver várias tabelas ou uma tabela aninhada, selecione o nome da tabela primeiro.</span><span class="sxs-lookup"><span data-stu-id="b25b8-138">If the data source view contains multiple tables, or a nested table, you must first select the table name.</span></span> <span data-ttu-id="b25b8-139">Caso contrário, você pode selecionar colunas diretamente na tabela de casos.</span><span class="sxs-lookup"><span data-stu-id="b25b8-139">Otherwise, you can select columns from the case table directly.</span></span>  
  
     <span data-ttu-id="b25b8-140">Adicione uma linha nova para cada coluna que você deseja filtrar.</span><span class="sxs-lookup"><span data-stu-id="b25b8-140">Add a new row for each column that you want to filter.</span></span>  
  
8.  <span data-ttu-id="b25b8-141">Use **Operador**e as colunas **Valor** para definir como a coluna é filtrada.</span><span class="sxs-lookup"><span data-stu-id="b25b8-141">Use **Operator**, and **Value** columns to define how the column is filtered.</span></span>  
  
     <span data-ttu-id="b25b8-142">**Nota** Digite os valores sem usar aspa.</span><span class="sxs-lookup"><span data-stu-id="b25b8-142">**Note** Type values without using quotation marks.</span></span>  
  
9. <span data-ttu-id="b25b8-143">Clique na caixa de texto **E/Ou** e selecione um operador lógico para definir como combinar várias condições.</span><span class="sxs-lookup"><span data-stu-id="b25b8-143">Click the **And/Or** text box and select a logical operator to define how multiple conditions are combine.</span></span>  
  
10. <span data-ttu-id="b25b8-144">Opcionalmente, clique no botão procurar **(...)** à direita da caixa de texto **valor** para abrir a caixa de diálogo **Filtrar** e definir condições na tabela aninhada ou nas colunas da tabela de casos individuais.</span><span class="sxs-lookup"><span data-stu-id="b25b8-144">Optionally, click the browse button **(...)** at the right of the **Value** text box to open the **Filter** dialog box and set conditions on the nested table or on the individual case table columns.</span></span>  
  
11. <span data-ttu-id="b25b8-145">Verifique se as condições de filtro atendidas estão corretas exibindo o texto no painel **Expressão** .</span><span class="sxs-lookup"><span data-stu-id="b25b8-145">Verify that the completed filter conditions are correct by viewing the text in the **Expression** pane.</span></span>  
  
12. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="b25b8-146">A condição de filtro é aplicada à fonte de dados quando você cria o gráfico de precisão.</span><span class="sxs-lookup"><span data-stu-id="b25b8-146">The filter condition is applied to the data source when you create the accuracy chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b25b8-147">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b25b8-147">See Also</span></span>  
 <span data-ttu-id="b25b8-148">[Escolher e mapear dados de teste de modelo](choose-and-map-model-testing-data.md) </span><span class="sxs-lookup"><span data-stu-id="b25b8-148">[Choose and Map Model Testing Data](choose-and-map-model-testing-data.md) </span></span>  
 <span data-ttu-id="b25b8-149">[Usando dados de tabela aninhada como uma entrada para um gráfico de precisão](using-nested-table-data-as-an-input-for-an-accuracy-chart.md) </span><span class="sxs-lookup"><span data-stu-id="b25b8-149">[Using Nested Table Data as an Input for an Accuracy Chart](using-nested-table-data-as-an-input-for-an-accuracy-chart.md) </span></span>  
 [<span data-ttu-id="b25b8-150">Escolher um tipo de gráfico de precisão e definir opções de gráfico</span><span class="sxs-lookup"><span data-stu-id="b25b8-150">Choose an Accuracy Chart Type and Set Chart Options</span></span>](choose-an-accuracy-chart-type-and-set-chart-options.md)  
  
  
