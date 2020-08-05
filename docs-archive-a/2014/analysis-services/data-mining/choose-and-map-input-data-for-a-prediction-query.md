---
title: Escolher e mapear dados de entrada para uma consulta de previsão | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- tables [Analysis Services], prediction queries
- Mining Model Prediction [Analysis Services], input tables
ms.assetid: 00d330a0-879d-4da0-9f29-53c288116f4d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 54e11752d6278e01e50a379bf7bb57521ff9bb29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572853"
---
# <a name="choose-and-map-input-data-for-a-prediction-query"></a><span data-ttu-id="997e6-102">Escolher e mapear dados de entrada para uma consulta de previsão</span><span class="sxs-lookup"><span data-stu-id="997e6-102">Choose and Map Input Data for a Prediction Query</span></span>
  <span data-ttu-id="997e6-103">Quando você cria previsões de um modelo de mineração, geralmente o faz alimentando novos dados no modelo.</span><span class="sxs-lookup"><span data-stu-id="997e6-103">When you create predictions from a mining model, you generally do this by feeding new data into the model.</span></span> <span data-ttu-id="997e6-104">(A exceção são modelos de série temporal, que só podem fazer previsões com base em dados históricos.) Para oferecer novos dados ao modelo, verifique se os dados estão disponíveis como parte de uma exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="997e6-104">(The exception is time series models, which can make predictions based on historical data only.) To provide the model with new data, you must make sure that the data is available as part of a data source view.</span></span> <span data-ttu-id="997e6-105">Se souber antecipadamente os dados que serão usados na previsão, você poderá incluí-los na exibição de fonte de dados usada para criar o modelo.</span><span class="sxs-lookup"><span data-stu-id="997e6-105">If you know in advance which data you will use for prediction, you can include it in the data source view that you used to create the model.</span></span> <span data-ttu-id="997e6-106">Caso contrário, talvez precise criar uma nova exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="997e6-106">Otherwise, you might have to create a new data source view.</span></span> <span data-ttu-id="997e6-107">Para obter mais informações, consulte [Exibições de fontes de dados em modelos multidimensionais](../multidimensional-models/data-source-views-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="997e6-107">For more information, see [Data Source Views in Multidimensional Models](../multidimensional-models/data-source-views-in-multidimensional-models.md).</span></span>  
  
 <span data-ttu-id="997e6-108">Às vezes, os dados de que você precisa podem estar contidos em mais de uma tabela em uma junção um-para-muitos.</span><span class="sxs-lookup"><span data-stu-id="997e6-108">Sometimes the data that you need might be contained within more than one table in a one-to-many join.</span></span> <span data-ttu-id="997e6-109">Este é o caso de dados usados em modelos de associação ou modelos de clustering de sequência, que usam uma tabela de casos vinculada a uma tabela aninhada que contém detalhes do produto ou da transação.</span><span class="sxs-lookup"><span data-stu-id="997e6-109">This is the case with data used for association models or sequence clustering models, which use a case table linked to a nested table that contains product or transaction details.</span></span> <span data-ttu-id="997e6-110">Se o seu modelo usa uma estrutura de tabela aninhada de caso, os dados usados para previsão também precisam ter uma estrutura de tabela aninhada de caso.</span><span class="sxs-lookup"><span data-stu-id="997e6-110">If your model uses a case-nested table structure, the data that you use for prediction must also have a case-nested table structure.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="997e6-111">Não é possível adicionar colunas novas ou mapear colunas que estão em uma exibição de fonte de dados diferente.</span><span class="sxs-lookup"><span data-stu-id="997e6-111">You cannot add new columns or map columns that are in a different data source view.</span></span> <span data-ttu-id="997e6-112">A exibição da fonte de dados selecionada deve conter todas as colunas que você precisa para a consulta de previsão.</span><span class="sxs-lookup"><span data-stu-id="997e6-112">The data source view that you select must contain all the columns that you need for the prediction query.</span></span>  
  
 <span data-ttu-id="997e6-113">Após identificar as tabelas que contêm os dados a serem usados em previsões, mapeie as colunas nos dados externos para as colunas do modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="997e6-113">After you have identified the tables that contain the data you will use for predictions, you must map the columns in the external data to the columns in the mining model.</span></span> <span data-ttu-id="997e6-114">Por exemplo, se seu modelo prever o comportamento de compra do cliente com base em demografia e em respostas de pesquisa, seus dados de entrada deverão conter informações que geralmente correspondem ao que está no modelo.</span><span class="sxs-lookup"><span data-stu-id="997e6-114">For example, if your model predicts customer purchasing behavior based on demographics and survey responses, your input data should contains information that generally corresponds to what is in the model.</span></span> <span data-ttu-id="997e6-115">Você não precisa ter dados correspondentes para cada coluna única, mas quanto maior for o número de colunas com correspondência, melhor.</span><span class="sxs-lookup"><span data-stu-id="997e6-115">You do not need to have matching data for every single column, but the more columns you can match, the better.</span></span> <span data-ttu-id="997e6-116">Se você tentar mapear colunas com tipos de dados diferentes, poderá obter um erro.</span><span class="sxs-lookup"><span data-stu-id="997e6-116">If you try to map columns that have different data types, you might get an error.</span></span> <span data-ttu-id="997e6-117">Nesse caso, você pode definir um cálculo nomeado na exibição da fonte de dados para converter os novos dados de coluna no tipo de dados solicitado pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="997e6-117">In that case, you could define a named calculation in the data source view to cast or convert the new column data to the data type required by the model.</span></span> <span data-ttu-id="997e6-118">Para obter mais informações, consulte [definir cálculos nomeados em uma exibição da fonte de dados &#40;Analysis Services&#41;](../multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="997e6-118">For more information, see [Define Named Calculations in a Data Source View &#40;Analysis Services&#41;](../multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md).</span></span>  
  
 <span data-ttu-id="997e6-119">Quando você escolher os dados a serem usados para previsão, talvez algumas colunas na fonte de dados selecionada sejam mapeadas automaticamente para as colunas de modelo de mineração, com base na semelhança de nome e no tipo de dados correspondente.</span><span class="sxs-lookup"><span data-stu-id="997e6-119">When you choose the data to use for prediction, some columns in the selected data source might be automatically mapped to the mining model columns, based on name similarity and matching data type.</span></span> <span data-ttu-id="997e6-120">Você pode usar a caixa de diálogo **Modificar Mapeamento** na **Previsão de Modelo de Mineração** para alterar as colunas que são mapeadas, excluir mapeamentos impróprios ou criar novos mapeamentos para colunas existentes.</span><span class="sxs-lookup"><span data-stu-id="997e6-120">You can use the **Modify Mapping** dialog box in the **Mining Model Prediction** to change the columns that are mapped, delete inappropriate mappings, or create new mappings for existing columns.</span></span> <span data-ttu-id="997e6-121">A superfície de design **Previsão de Modelo de Mineração** também dá suporte ao recurso de edição do tipo “arrastar e soltar” de conexões.</span><span class="sxs-lookup"><span data-stu-id="997e6-121">The **Mining Model Prediction** design surface also supports drag-and-drop editing of connections.</span></span>  
  
-   <span data-ttu-id="997e6-122">Para criar uma nova conexão, basta selecionar uma coluna na tabela **Modelo de Mineração** e arrastá-la até a coluna correspondente na tabela **Selecionar Tabela(s) de Entrada** .</span><span class="sxs-lookup"><span data-stu-id="997e6-122">To create a new connection, just select a column in the **Mining Model** table and drag it to the corresponding column in the **SelectInput Table(s)** table.</span></span>  
  
-   <span data-ttu-id="997e6-123">Para remover uma conexão, selecione a linha da conexão e pressione a tecla DELETE.</span><span class="sxs-lookup"><span data-stu-id="997e6-123">To remove a connection, select the connection line and press the DELETE key.</span></span>  
  
 <span data-ttu-id="997e6-124">O procedimento a seguir descreve como você pode modificar as junções criadas entre a tabela de casos e uma tabela aninhada usadas como entradas para uma consulta de previsão, usando a caixa de diálogo **Especificar Junção Aninhada** .</span><span class="sxs-lookup"><span data-stu-id="997e6-124">The following procedure describes how you can modify the joins that have been created between the case table and a nested table used as inputs to a prediction query, using the **Specify Nested Join** dialog box.</span></span>  
  
### <a name="select-an-input-table"></a><span data-ttu-id="997e6-125">Selecionar uma tabela de entrada</span><span class="sxs-lookup"><span data-stu-id="997e6-125">Select an input table</span></span>  
  
1.  <span data-ttu-id="997e6-126">Na tabela **Selecionar Tabela(s) de Entrada** da guia **Gráfico de Precisão de Mineração** do Designer de Mineração de Dados no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], clique em **Selecionar Tabela de Casos**.</span><span class="sxs-lookup"><span data-stu-id="997e6-126">On the **Select Input Table(s)** table of the **Mining Accuracy Chart** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click **Select Case Table**.</span></span>  
  
     <span data-ttu-id="997e6-127">A caixa de diálogo **Selecionar Tabela** é exibida, na qual você pode selecionar a tabela que contém os dados nos quais deseja que as suas consultas se baseiem.</span><span class="sxs-lookup"><span data-stu-id="997e6-127">The **Select Table** dialog box opens, in which you can select the table that contains the data on which to base your queries.</span></span>  
  
2.  <span data-ttu-id="997e6-128">Na caixa de diálogo **Selecionar Tabela** , selecione uma fonte de dados na lista **Fonte de Dados** .</span><span class="sxs-lookup"><span data-stu-id="997e6-128">In the **Select Table** dialog box, select a data source from the **Data Source** list.</span></span>  
  
3.  <span data-ttu-id="997e6-129">Em **Nome de Tabela/Exibição**, selecione a tabela que contém os dados você quer usar para testar os modelos.</span><span class="sxs-lookup"><span data-stu-id="997e6-129">Under **Table/View Name**, select the table that contains the data you want to use to test the models.</span></span>  
  
4.  <span data-ttu-id="997e6-130">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="997e6-130">Click **OK**.</span></span>  
  
     <span data-ttu-id="997e6-131">As colunas na estrutura de mineração são mapeadas automaticamente para colunas que tenham o mesmo nome na tabela de entrada.</span><span class="sxs-lookup"><span data-stu-id="997e6-131">The columns in the mining structure are automatically mapped to the columns that have the same name in the input table.</span></span>  
  
### <a name="change-the-way-that-input-data-is-mapped-to-the-model"></a><span data-ttu-id="997e6-132">Altere a maneira como os dados de entrada são mapeados para o modelo</span><span class="sxs-lookup"><span data-stu-id="997e6-132">Change the way that input data is mapped to the model</span></span>  
  
1.  <span data-ttu-id="997e6-133">No Designer de Mineração de Dados no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], selecione a guia **Previsão de Modelo de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="997e6-133">In Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], select the **Mining Model Prediction** tab.</span></span>  
  
2.  <span data-ttu-id="997e6-134">No menu **Modelo de Mineração** , selecione **Modificar Conexões**.</span><span class="sxs-lookup"><span data-stu-id="997e6-134">On the **Mining Model** menu, select **Modify Connections**.</span></span>  
  
     <span data-ttu-id="997e6-135">A caixa de diálogo **Modificar Mapeamento** abre.</span><span class="sxs-lookup"><span data-stu-id="997e6-135">The **Modify Mapping** dialog box opens.</span></span> <span data-ttu-id="997e6-136">Nesta caixa de diálogo, a coluna **Coluna do Modelo de Mineração** lista as colunas na estrutura de mineração selecionada.</span><span class="sxs-lookup"><span data-stu-id="997e6-136">In this dialog box, the column **Mining Model Column** lists the columns in the selected mining structure.</span></span> <span data-ttu-id="997e6-137">A **Coluna da Tabela** lista as colunas na fonte de dados externa que você escolheu na caixa de diálogo **Selecionar Tabela(s) de Entrada** .</span><span class="sxs-lookup"><span data-stu-id="997e6-137">The column **Table Column** lists the columns in the external data source that you chose in the **SelectInput Table(s)** dialog box.</span></span> <span data-ttu-id="997e6-138">As colunas na fonte de dados externa são mapeadas para colunas no modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="997e6-138">The columns in the external data source are mapped to columns in the mining model.</span></span>  
  
3.  <span data-ttu-id="997e6-139">Em **Coluna da Tabela**, selecione a linha que corresponde à coluna de modelo de mineração para a qual você deseja mapear.</span><span class="sxs-lookup"><span data-stu-id="997e6-139">Under **Table Column**, select the row that corresponds to the mining model column that you want to map to.</span></span>  
  
4.  <span data-ttu-id="997e6-140">Selecione uma coluna nova na lista de colunas disponíveis na fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="997e6-140">Select a new column from the list of available columns in the external data source.</span></span> <span data-ttu-id="997e6-141">Selecione o item em branco na lista para excluir o mapeamento de coluna.</span><span class="sxs-lookup"><span data-stu-id="997e6-141">Select the blank item in the list to delete the column mapping.</span></span>  
  
5.  <span data-ttu-id="997e6-142">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="997e6-142">Click **OK**.</span></span>  
  
     <span data-ttu-id="997e6-143">Os novos mapeamentos de coluna são exibidos no designer.</span><span class="sxs-lookup"><span data-stu-id="997e6-143">The new column mappings are displayed in the designer.</span></span>  
  
### <a name="remove-a-relationship-between-input-tables"></a><span data-ttu-id="997e6-144">Remover uma relação entre tabelas de entrada</span><span class="sxs-lookup"><span data-stu-id="997e6-144">Remove a relationship between input tables</span></span>  
  
1.  <span data-ttu-id="997e6-145">Na tabela **Selecionar Tabela(s) de Entrada** da guia **Previsão do Modelo de Mineração** do Designer de Mineração de Dados no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], clique em **Modificar Junção**.</span><span class="sxs-lookup"><span data-stu-id="997e6-145">On the **Select Input Table(s)** table of the **Mining Model Prediction** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click **Modify Join**.</span></span>  
  
     <span data-ttu-id="997e6-146">A caixa de diálogo **Especificar Junção Aninhada** é aberta.</span><span class="sxs-lookup"><span data-stu-id="997e6-146">The **Specify Nested Join** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="997e6-147">Selecione uma relação.</span><span class="sxs-lookup"><span data-stu-id="997e6-147">Select a relationship.</span></span>  
  
3.  <span data-ttu-id="997e6-148">Clique em **Remover Relação**.</span><span class="sxs-lookup"><span data-stu-id="997e6-148">Click **Remove Relationship**.</span></span>  
  
4.  <span data-ttu-id="997e6-149">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="997e6-149">Click **OK**.</span></span>  
  
     <span data-ttu-id="997e6-150">A relação entre a tabela de casos e a tabela aninhada foi removida.</span><span class="sxs-lookup"><span data-stu-id="997e6-150">The relationship between the case table and the nested table has been removed.</span></span>  
  
### <a name="create-a-new-relationship-between-input-tables"></a><span data-ttu-id="997e6-151">Criar uma nova relação entre tabelas de entrada</span><span class="sxs-lookup"><span data-stu-id="997e6-151">Create a new relationship between input tables</span></span>  
  
1.  <span data-ttu-id="997e6-152">Na tabela **Selecionar Tabela(s) de Entrada** da guia **Previsão do Modelo de Mineração** do Designer de Mineração de Dados, clique em **Modificar Junção**.</span><span class="sxs-lookup"><span data-stu-id="997e6-152">On the **Select Input Table(s)** table of the **Mining Model Prediction** tab in Data Mining Designer, click **Modify Join**.</span></span>  
  
     <span data-ttu-id="997e6-153">A caixa de diálogo **Especificar Junção Aninhada** é aberta.</span><span class="sxs-lookup"><span data-stu-id="997e6-153">The **Specify Nested Join** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="997e6-154">Clique em **Adicionar Relação**.</span><span class="sxs-lookup"><span data-stu-id="997e6-154">Click **Add Relationship**.</span></span>  
  
     <span data-ttu-id="997e6-155">A caixa de diálogo **Criar Relação** é aberta.</span><span class="sxs-lookup"><span data-stu-id="997e6-155">The **Create Relationship** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="997e6-156">Selecione a chave da tabela aninhada em **Colunas de Origem**.</span><span class="sxs-lookup"><span data-stu-id="997e6-156">Select the key of the nested table in **Source Columns**.</span></span>  
  
4.  <span data-ttu-id="997e6-157">Selecione a chave da tabela de casos em **Colunas de Destino**.</span><span class="sxs-lookup"><span data-stu-id="997e6-157">Select the key of the case table in **Destination Columns**.</span></span>  
  
5.  <span data-ttu-id="997e6-158">Clique em **OK** na caixa de diálogo **Criar Relação** .</span><span class="sxs-lookup"><span data-stu-id="997e6-158">Click **OK** in the **Create Relationship** dialog box.</span></span>  
  
6.  <span data-ttu-id="997e6-159">Clique em **OK** na caixa de diálogo **Especificar Junção Aninhada** .</span><span class="sxs-lookup"><span data-stu-id="997e6-159">Click **OK** in the **Specify Nested Join** dialog box.</span></span>  
  
     <span data-ttu-id="997e6-160">Uma nova relação foi criada entre a tabela de casos e a tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="997e6-160">A new relationship has been created between the case table and the nested table.</span></span>  
  
### <a name="add-a-nested-table-to-the-input-tables-of-a-prediction-query"></a><span data-ttu-id="997e6-161">Adicionar uma tabela aninhada às tabelas de entrada de uma consulta de previsão</span><span class="sxs-lookup"><span data-stu-id="997e6-161">Add a nested table to the input tables of a prediction query</span></span>  
  
1.  <span data-ttu-id="997e6-162">Na guia **Previsão de Modelo de Mineração** do Designer de Mineração de Dados, clique em **Selecionar Tabela de Casos** para abrir a caixa de diálogo **Selecionar Tabela** .</span><span class="sxs-lookup"><span data-stu-id="997e6-162">On the **Mining Model Prediction** tab in Data Mining Designer, click **Select Case Table** to open the **Select Table** dialog box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="997e6-163">Não é possível adicionar uma tabela aninhada às entradas, a menos que você tenha especificado uma tabela de casos.</span><span class="sxs-lookup"><span data-stu-id="997e6-163">You cannot add a nested table to the inputs unless you have specified a case table.</span></span> <span data-ttu-id="997e6-164">O uso de uma tabela aninhada exige que o modelo de mineração usado na previsão também utilize uma tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="997e6-164">Use of a nested table requires that the mining model you are using for prediction also uses a nested table.</span></span>  
  
2.  <span data-ttu-id="997e6-165">Na caixa de diálogo **Selecionar Tabela** , selecione uma fonte de dados da lista **Fonte de Dados** e selecione a tabela na exibição de fonte de dados que contém os dados de caso.</span><span class="sxs-lookup"><span data-stu-id="997e6-165">In the **Select Table** dialog box, select a data source from the **Data Source** list, and select the table in the data source view that contains the case data.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
3.  <span data-ttu-id="997e6-166">Clique em **Selecionar Tabela Aninhada** para abrir a caixa de diálogo **Selecionar Tabela** .</span><span class="sxs-lookup"><span data-stu-id="997e6-166">Click **Select Nested Table** to open the **Select Table** dialog box.</span></span>  
  
4.  <span data-ttu-id="997e6-167">Na caixa de diálogo **Selecionar Tabela** , selecione uma fonte de dados da lista **Fonte de Dados** e selecione a tabela na exibição de fonte de dados que contém os dados aninhados.</span><span class="sxs-lookup"><span data-stu-id="997e6-167">In the **Select Table** dialog box, select a data source from the **Data Source** list, and select the table in the data source view that contains the nested data.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="997e6-168">Se já existir uma relação, as colunas no modelo de mineração serão mapeados automaticamente para as colunas que possuem o mesmo nome na tabela de entrada.</span><span class="sxs-lookup"><span data-stu-id="997e6-168">If a relationship already exists, the columns in the mining model are automatically mapped to the columns that have the same name in the input table.</span></span> <span data-ttu-id="997e6-169">É possível modificar a relação entre a tabela aninhada e a tabela de casos clicando em **Modificar Junção**, que abre a caixa de diálogo **Criar Relação** .</span><span class="sxs-lookup"><span data-stu-id="997e6-169">You can modify the relationship between the nested table and the case table by clicking **Modify Join**, which opens the **Create Relationship** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="997e6-170">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="997e6-170">See Also</span></span>  
 [<span data-ttu-id="997e6-171">Consultas de previsão &#40;Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="997e6-171">Prediction Queries &#40;Data Mining&#41;</span></span>](prediction-queries-data-mining.md)  
  
  
