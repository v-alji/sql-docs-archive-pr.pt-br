---
title: Navegando em um modelo de rede neural | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- mining models, viewing
- mining model, neural network
- neural networks
- dependency network
ms.assetid: e4224cb7-115b-4889-ac07-03f096fb55fc
author: minewiskan
ms.author: owend
ms.openlocfilehash: ab2673d5b1881f74c2bc146b084d2efc7b06d69b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571109"
---
# <a name="browsing-a-neural-network-model"></a><span data-ttu-id="8daf3-102">Procurando um modelo de rede neural</span><span class="sxs-lookup"><span data-stu-id="8daf3-102">Browsing a Neural Network Model</span></span>
  <span data-ttu-id="8daf3-103">Quando você abre uma rede neural ou modelo de regressão logística usando **Procurar**, o modelo é exibido em um visualizador interativo, semelhante ao visualizador de modelo da rede neural no [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8daf3-103">When you open a neural network or logistic regression model using **Browse**, the model is displayed in an interactive viewer, similar to the neural network model viewer in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="8daf3-104">O visualizador ajuda a explorar correlações e obter informações sobre os padrões no modelo e os dados subjacentes.</span><span class="sxs-lookup"><span data-stu-id="8daf3-104">The viewer helps you explore correlations, and get information about the patterns in the model and the underlying data.</span></span>

##  <a name="explore-the-model"></a><a name="BKMK_Tabs"></a><span data-ttu-id="8daf3-105">Explorar o modelo</span><span class="sxs-lookup"><span data-stu-id="8daf3-105">Explore the Model</span></span>
 <span data-ttu-id="8daf3-106">Os modelos que são baseados na Rede Neural ou os algoritmos de Regressão Logística da [!INCLUDE[msCoName](../includes/msconame-md.md)] são semelhantes porque analisam dados como um conjunto de conexões entre entradas e saídas conhecidas.</span><span class="sxs-lookup"><span data-stu-id="8daf3-106">Models that are based on [!INCLUDE[msCoName](../includes/msconame-md.md)] Neural Network or Logistic Regression algorithms are similar in that they analyze data as a set of connections among known inputs and outputs.</span></span> <span data-ttu-id="8daf3-107">O visualizador **Procurar** ajuda a explorar essas conexões, usando os seguintes controles:</span><span class="sxs-lookup"><span data-stu-id="8daf3-107">The **Browse** viewer helps you to explore those connections, using the following controls:</span></span>

-   [<span data-ttu-id="8daf3-108">Variáveis</span><span class="sxs-lookup"><span data-stu-id="8daf3-108">Variables</span></span>](#BKMK_Variables)

-   [<span data-ttu-id="8daf3-109">Entradas</span><span class="sxs-lookup"><span data-stu-id="8daf3-109">Inputs</span></span>](#BKMK_Inputs)

-   [<span data-ttu-id="8daf3-110">Saídas</span><span class="sxs-lookup"><span data-stu-id="8daf3-110">Outputs</span></span>](#BKMK_Outputs)

 <span data-ttu-id="8daf3-111">Se quiser fazer experiências com esse visualizador, crie um modelo usando o assistente [Assistente de Classificação &#40;Suplementos de Mineração de Dados para Excel&#41;](classify-wizard-data-mining-add-ins-for-excel.md) e use a opção **Avançado** para alterar o algoritmo para Regressão Logística da Microsoft na caixa de diálogo **Parâmetros do Algoritmo**.</span><span class="sxs-lookup"><span data-stu-id="8daf3-111">If you want to experiment with this viewer, you can create a model using the [Classify Wizard &#40;Data Mining Add-ins for Excel&#41;](classify-wizard-data-mining-add-ins-for-excel.md) wizard, and use the **Advanced** option to change the algorithm to Microsoft Logistic Regression in the **Algorithm Parameters** dialog box.</span></span>

###  <a name="variables"></a><a name="BKMK_Variables"></a><span data-ttu-id="8daf3-112">As</span><span class="sxs-lookup"><span data-stu-id="8daf3-112">Variables</span></span>
 <span data-ttu-id="8daf3-113">O painel **Variáveis** exibe uma lista de variáveis de entrada pela ordem de seu efeito no modelo.</span><span class="sxs-lookup"><span data-stu-id="8daf3-113">The **Variables** pane displays a list of input variables in order of their effect on the model.</span></span> <span data-ttu-id="8daf3-114">Você usa os controles de **Entrada** e **Saída** para filtrar o modelo, afetando as variáveis que são exibidas, bem como sua ordem.</span><span class="sxs-lookup"><span data-stu-id="8daf3-114">You use the **Input** and **Output** controls to filter the model, affecting the variables that are displayed, as well as their order.</span></span>

 <span data-ttu-id="8daf3-115">Usando esse visualizador, você poderá explorar os fatores que são muito importantes para determinar se um cliente mais provavelmente pertence à categoria Comprador de bicicleta ou não.</span><span class="sxs-lookup"><span data-stu-id="8daf3-115">Using this viewer, you can explore the factors that are most important in determining whether a customer more likely belongs to the bike buyer category or the non-buyer category.</span></span>

 <span data-ttu-id="8daf3-116">![Testando o efeito no resultado de atributos selecionados](media/dm13-neuralnet-agebuyer1.gif "Testando o efeito no resultado de atributos selecionados")</span><span class="sxs-lookup"><span data-stu-id="8daf3-116">![Testing effect on outcome of selected attributes](media/dm13-neuralnet-agebuyer1.gif "Testing effect on outcome of selected attributes")</span></span>

##### <a name="explore-variables"></a><span data-ttu-id="8daf3-117">Explorar variáveis</span><span class="sxs-lookup"><span data-stu-id="8daf3-117">Explore variables</span></span>

1.  <span data-ttu-id="8daf3-118">Inicialmente, o painel **Variáveis** é classificado na ordem dos atributos mais importantes, considerando os filtros atuais.</span><span class="sxs-lookup"><span data-stu-id="8daf3-118">Initially, the **Variables** pane is sorted in order of the most important attributes, given the current filters.</span></span> <span data-ttu-id="8daf3-119">O comprimento da barra indica a intensidade do fator.</span><span class="sxs-lookup"><span data-stu-id="8daf3-119">The length of the bar indicates the strength of the factor.</span></span>

     <span data-ttu-id="8daf3-120">No exemplo, você pode ver que a renda é o fator mais influente, seguido por região.</span><span class="sxs-lookup"><span data-stu-id="8daf3-120">In the example, you can see that income is the most influential factor, followed by region.</span></span> <span data-ttu-id="8daf3-121">Por outro lado, os clientes com muitos carros e vários filhos são altamente menos prováveis de comprar uma bicicleta.</span><span class="sxs-lookup"><span data-stu-id="8daf3-121">On the other hand, customers with many cars and many children are highly unlikely to buy a bike.</span></span>

2.  <span data-ttu-id="8daf3-122">No painel **Variáveis**, clique no título de coluna para **Atributo**.</span><span class="sxs-lookup"><span data-stu-id="8daf3-122">In the **Variables** pane, click the column heading for **Attribute**.</span></span>

     <span data-ttu-id="8daf3-123">Ao classificando por atributo, você poderá consultar os compartimentos criados para cada uma das colunas de entrada.</span><span class="sxs-lookup"><span data-stu-id="8daf3-123">By sorting on attribute, you can see the bins that were created for each of the input columns.</span></span> <span data-ttu-id="8daf3-124">As colunas com valores discretos, como ocupação, são *compartimentadas* pelos valores literais.</span><span class="sxs-lookup"><span data-stu-id="8daf3-124">Columns with discrete values, such as occupation, are *binned* by the literal values.</span></span>

3.  <span data-ttu-id="8daf3-125">Observe os intervalos de valores que foram localizados para **Idade** e **Renda**.</span><span class="sxs-lookup"><span data-stu-id="8daf3-125">Notice the ranges of values that were found for **Age** and **Income**.</span></span>

     <span data-ttu-id="8daf3-126">Se alguma de suas colunas de entrada forem números (ou seja, a coluna de dados inteira é um tipo de dados numérico contínuo), os números serão particionados, ou compartimentados, em intervalos discretos.</span><span class="sxs-lookup"><span data-stu-id="8daf3-126">If any of your input columns are numbers (that is, the entire column of data is a continuous numeric data type), the numbers are bucketed, or binned, into discrete ranges.</span></span>

     <span data-ttu-id="8daf3-127">Para Renda, a coluna foi subdividida em agrupamentos como 78,4-154,06 (para o intervalo de renda mais alto).</span><span class="sxs-lookup"><span data-stu-id="8daf3-127">For Income, the column has been subdivided into groupings such as 78.4-154.06 (for the uppermost income range).</span></span>

     <span data-ttu-id="8daf3-128">![classificação para ver como as variáveis foram compartimentadas](media/dm13-nn-bucketing-variables.gif "classificação para ver como as variáveis foram compartimentadas")</span><span class="sxs-lookup"><span data-stu-id="8daf3-128">![sort to view how variables were binned](media/dm13-nn-bucketing-variables.gif "sort to view how variables were binned")</span></span>

     <span data-ttu-id="8daf3-129">Se você quiser agrupamentos diferentes, deverá usar a ferramenta [Rotular novamente &#40;Suplementos de Mineração de Dados do SQL Server&#41;](relabel-sql-server-data-mining-add-ins.md) ou funções do Excel, para criar novas categorias de renda antes de criar o modelo.</span><span class="sxs-lookup"><span data-stu-id="8daf3-129">If you want different groupings, you should use the [Relabel &#40;SQL Server Data Mining Add-ins&#41;](relabel-sql-server-data-mining-add-ins.md) tool, or Excel functions, to create new income categories before building the model.</span></span>

4.  <span data-ttu-id="8daf3-130">Clique em **Favorece Sim** para restaurar o gráfico para a exibição padrão.</span><span class="sxs-lookup"><span data-stu-id="8daf3-130">Click **Favors Yes** to restore the graph to the default view.</span></span>

     <span data-ttu-id="8daf3-131">Por padrão, a exibição será classificada pelo valor de **Favorece** para o valor do primeiro resultado.</span><span class="sxs-lookup"><span data-stu-id="8daf3-131">By default, the view is sorted by the value of **Favors** for the first outcome value.</span></span> <span data-ttu-id="8daf3-132">Você pode alterar quais resultados são atribuídos à primeira coluna e à segunda escolhendo um novo valor para **Valor 1** e **Valor 2** na **Saída**.</span><span class="sxs-lookup"><span data-stu-id="8daf3-132">You can change which outcomes are assigned to the first and second columns by choosing a new value for **Value 1** and **Value 2** in **Output**.</span></span>

5.  <span data-ttu-id="8daf3-133">Coloque o mouse sobre a barra colorida mais alta no gráfico.</span><span class="sxs-lookup"><span data-stu-id="8daf3-133">Pause the mouse over the topmost colored bar in the chart.</span></span>

     <span data-ttu-id="8daf3-134">Uma dica de ferramenta é exibida que inclui uma pontuação de *importância*, um par de pontuações de *probabilidade* e um par de valores de *comparação*.</span><span class="sxs-lookup"><span data-stu-id="8daf3-134">A ToolTip appears that includes an *importance* score, a pair of *probability* scores, and a pair of *lift* values.</span></span>

    -   <span data-ttu-id="8daf3-135">A **importância** é calculada pelo conjunto de dados inteiro e identifica o atributo que, considerando todas as entradas, está mais correlacionado com o resultado de destino.</span><span class="sxs-lookup"><span data-stu-id="8daf3-135">**Importance** is calculated across the entire dataset, and identifies the attribute that, given all inputs, is most correlated with the target outcome.</span></span> <span data-ttu-id="8daf3-136">O visualizador classifica os valores no gráfico pelas pontuações de importância.</span><span class="sxs-lookup"><span data-stu-id="8daf3-136">The viewer sorts the values in the chart by the importance scores.</span></span>

    -   <span data-ttu-id="8daf3-137">A **probabilidade** é calculada para cada conjunto de pares atributo-valor, para os resultados de destino em todo o conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="8daf3-137">**Probability** is calculated for each set of attribute-value pairs, for the target outcomes, across the entire data set.</span></span>

    -   <span data-ttu-id="8daf3-138">A **comparação de precisão** informa a utilidade desse par atributo-valor específico para promover um resultado ou outro.</span><span class="sxs-lookup"><span data-stu-id="8daf3-138">**Lift** tells you how useful this particular attribute-value pair is for promoting one outcome or another.</span></span>

     <span data-ttu-id="8daf3-139">Observação: a dica de ferramenta contém as mesmas informações independentemente de você posicionar o mouse sobre uma coluna ou sobre a outra.</span><span class="sxs-lookup"><span data-stu-id="8daf3-139">Note: The ToolTip contains the same information no matter whether you position the mouse over one column or the other.</span></span>

 [<span data-ttu-id="8daf3-140">Voltar ao início</span><span class="sxs-lookup"><span data-stu-id="8daf3-140">Back To Top</span></span>](#BKMK_Tabs)

###  <a name="inputs"></a><a name="BKMK_Inputs"></a><span data-ttu-id="8daf3-141">Informações</span><span class="sxs-lookup"><span data-stu-id="8daf3-141">Inputs</span></span>
 <span data-ttu-id="8daf3-142">O painel **Entradas** permite escolher um conjunto de entradas e aplicá-lo como um filtro para o modelo, o que permite ver o efeito dessas opções no resultado, com base nos dados de treinamento</span><span class="sxs-lookup"><span data-stu-id="8daf3-142">The **Inputs** pane lets you choose a set of inputs and apply that as a filter to the model, which lets you see the influence of those choices on the outcome, based on the training data</span></span>

##### <a name="explore-inputs"></a><span data-ttu-id="8daf3-143">Explorar entradas</span><span class="sxs-lookup"><span data-stu-id="8daf3-143">Explore inputs</span></span>

1.  <span data-ttu-id="8daf3-144">Suponha que você queira definir como destino um grupo específico e ver os fatores que mais influenciam a compra nesse grupo.</span><span class="sxs-lookup"><span data-stu-id="8daf3-144">Suppose you want to target a particular group, and see the factors that most influence purchasing in that group.</span></span>

     <span data-ttu-id="8daf3-145">No painel **entrada** , clique na **\<All>** célula em **atributo**e selecione **idade**.</span><span class="sxs-lookup"><span data-stu-id="8daf3-145">In the **Input** pane, click the **\<All>** cell under **Attribute**, and select **Age**.</span></span>

     <span data-ttu-id="8daf3-146">Para **Valor**, selecione a categoria de idade mais nova.</span><span class="sxs-lookup"><span data-stu-id="8daf3-146">For **Value**, select the youngest age category.</span></span>

2.  <span data-ttu-id="8daf3-147">Observe que até mesmo quando você filtra em uma faixa etária específica, a região do Pacífico aparece na parte superior da lista.</span><span class="sxs-lookup"><span data-stu-id="8daf3-147">Notice that even when you filter on a particular age group, the Pacific region comes to near the top of the list.</span></span> <span data-ttu-id="8daf3-148">Isso ocorre porque os clientes na região do Pacífico têm muito mais probabilidade de comprar uma bicicleta do que os clientes em outras regiões.</span><span class="sxs-lookup"><span data-stu-id="8daf3-148">This is because customers in the Pacific region are far more likely to buy a bike than customers in other regions.</span></span>

     <span data-ttu-id="8daf3-149">Como a região não é algo que você possa influenciar, para remover essa variável da consideração e ver outros fatores, você poderá alterar as entradas novamente.</span><span class="sxs-lookup"><span data-stu-id="8daf3-149">Since region is not something you can influence, to remove this variable from consideration and see other factors, you can change the inputs again.</span></span>

     <span data-ttu-id="8daf3-150">No painel **Entrada**, clique na célula em branco em **Idade** e selecione **Região**.</span><span class="sxs-lookup"><span data-stu-id="8daf3-150">In the **Input** pane, click the empty cell under **Age**, and select **Region**.</span></span>

     <span data-ttu-id="8daf3-151">Para **Valor**, selecione **Europa**.</span><span class="sxs-lookup"><span data-stu-id="8daf3-151">For **Value**, select **Europe**.</span></span>

3.  <span data-ttu-id="8daf3-152">Continue adicionando filtros de entrada para concentrar-se em um grupo de interesse específico.</span><span class="sxs-lookup"><span data-stu-id="8daf3-152">Continue adding input filters to focus on a group of particular interest.</span></span>

     <span data-ttu-id="8daf3-153">Por exemplo, para o atributo de entrada, adicione **Sexo** e selecione **Feminino** como o valor.</span><span class="sxs-lookup"><span data-stu-id="8daf3-153">For example, for the input attribute, add **Gender**, and select **Female** as the value.</span></span>

     <span data-ttu-id="8daf3-154">![Testando o efeito no resultado de atributos selecionados](media/dm13-neuralnet-agebuyer2.gif "Testando o efeito no resultado de atributos selecionados")</span><span class="sxs-lookup"><span data-stu-id="8daf3-154">![Testing effect on outcome of selected attributes](media/dm13-neuralnet-agebuyer2.gif "Testing effect on outcome of selected attributes")</span></span>

     <span data-ttu-id="8daf3-155">Observe como a lista de variáveis muda.</span><span class="sxs-lookup"><span data-stu-id="8daf3-155">Notice how the list of variables changes.</span></span> <span data-ttu-id="8daf3-156">Agora **Renda** é a variável que mais importante em prever o resultado do destino.</span><span class="sxs-lookup"><span data-stu-id="8daf3-156">Now **Income** is the variable that is most important in predicting the target outcome.</span></span>

     <span data-ttu-id="8daf3-157">A ordem na qual você aplica os filtros de entrada não afeta os resultados.</span><span class="sxs-lookup"><span data-stu-id="8daf3-157">The order in which you apply the input filters does not affect the results.</span></span>

 [<span data-ttu-id="8daf3-158">Voltar ao início</span><span class="sxs-lookup"><span data-stu-id="8daf3-158">Back To Top</span></span>](#BKMK_Tabs)

###  <a name="outputs"></a><a name="BKMK_Outputs"></a><span data-ttu-id="8daf3-159">Produz</span><span class="sxs-lookup"><span data-stu-id="8daf3-159">Outputs</span></span>
 <span data-ttu-id="8daf3-160">No painel **Saídas**, você poderá escolher o resultado no qual está interessado.</span><span class="sxs-lookup"><span data-stu-id="8daf3-160">In the **Outputs** pane, you can choose the outcome that you are interested in.</span></span> <span data-ttu-id="8daf3-161">As redes neurais permitem especificar quantas colunas de resultados você desejar, embora adicionar mais saídas adicione também mais complexidade do modelo e pode exigir um tempo maior de processamento.</span><span class="sxs-lookup"><span data-stu-id="8daf3-161">Neural networks let you specify as many outcome columns as you like, although adding more outputs adds to the complexity of the model and may require a much longer time to process.</span></span>

 <span data-ttu-id="8daf3-162">Para comparar duas saídas, elas deverão ter sido designadas como colunas **Prever** ou **Prever apenas**.</span><span class="sxs-lookup"><span data-stu-id="8daf3-162">To compare two outputs, they must have been designated as **Predict** or **Predict Only** columns.</span></span>

##### <a name="explore-outputs"></a><span data-ttu-id="8daf3-163">Explorar saída</span><span class="sxs-lookup"><span data-stu-id="8daf3-163">Explore outputs</span></span>

1.  <span data-ttu-id="8daf3-164">Use a lista **Atributo de saída** para selecionar um atributo.</span><span class="sxs-lookup"><span data-stu-id="8daf3-164">Use the **Output Attribute** list to select an attribute.</span></span>

2.  <span data-ttu-id="8daf3-165">Selecione dois resultados das listas Valor 1 e Valor 2.</span><span class="sxs-lookup"><span data-stu-id="8daf3-165">Select two outcomes from the Value 1 and Value 2 lists.</span></span> <span data-ttu-id="8daf3-166">Esses dois estados do atributo de saída serão comparados no painel **Variáveis** .</span><span class="sxs-lookup"><span data-stu-id="8daf3-166">These two states of the output attribute will be compared in the **Variables** pane.</span></span>

 [<span data-ttu-id="8daf3-167">Voltar ao início</span><span class="sxs-lookup"><span data-stu-id="8daf3-167">Back To Top</span></span>](#BKMK_Tabs)

## <a name="more-about-neural-network-models"></a><span data-ttu-id="8daf3-168">Mais sobre modelos de redes neurais</span><span class="sxs-lookup"><span data-stu-id="8daf3-168">More About Neural Network Models</span></span>
 <span data-ttu-id="8daf3-169">As informações no visualizador são recuperadas do servidor usando um procedimento armazenado específico para esse tipo de modelo: System.Microsoft.AnalysisServices.System.DataMining.NeuralNet.GetAttributeScores</span><span class="sxs-lookup"><span data-stu-id="8daf3-169">The information in the viewer is retrieved from the server using a stored procedure specific to this model type: System.Microsoft.AnalysisServices.System.DataMining.NeuralNet.GetAttributeScores.</span></span>

 <span data-ttu-id="8daf3-170">Se você quiser criar um modelo com vários atributos previsíveis usando os suplementos, use as opções de modelagem **Avançadas**.</span><span class="sxs-lookup"><span data-stu-id="8daf3-170">If you want to create a model with multiple predictable attributes using the add-ins, use the **Advanced** modeling options.</span></span>

 <span data-ttu-id="8daf3-171">Para obter mais informações, consulte [Criar uma estrutura de mineração &#40;Suplementos de mineração de dados do SQL Server&#41;](create-mining-structure-sql-server-data-mining-add-ins.md) e [Adicionar modelo à estrutura &#40;Suplementos de Mineração de Dados para Excel&#41;](add-model-to-structure-data-mining-add-ins-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="8daf3-171">For more information, see [Create Mining Structure &#40;SQL Server Data Mining Add-ins&#41;](create-mining-structure-sql-server-data-mining-add-ins.md) and [Add Model to Structure &#40;Data Mining Add-ins for Excel&#41;](add-model-to-structure-data-mining-add-ins-for-excel.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8daf3-172">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8daf3-172">See Also</span></span>
 [<span data-ttu-id="8daf3-173">Pesquisando modelos no Excel &#40;SQL Server suplementos de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="8daf3-173">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)


