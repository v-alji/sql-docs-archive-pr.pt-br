---
title: Navegando em um modelo de Bayes Naive | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f9160b48-3beb-439c-9694-f084e1afa625
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3b0d18cd74e71f1ef18bffd6b0998e0b326e887a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571113"
---
# <a name="browsing-a-naive-bayes-model"></a><span data-ttu-id="bd4f8-102">Procurando um modelo Naive Bayes</span><span class="sxs-lookup"><span data-stu-id="bd4f8-102">Browsing a Naive Bayes Model</span></span>
  <span data-ttu-id="bd4f8-103">Quando você abre um modelo Bayes simples usando **procurar**, o modelo é exibido em um visualizador interativo com quatro painéis diferentes.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-103">When you open a Naïve Bayes model using **Browse**, the model is displayed in an interactive viewer with four different panes.</span></span> <span data-ttu-id="bd4f8-104">Use o visualizador para explorar correlações e obter informações sobre o modelo e os dados subjacentes.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-104">Use the viewer to explore correlations, and get information about the model and the underlying data.</span></span>  
  
-   [<span data-ttu-id="bd4f8-105">Rede de Dependências</span><span class="sxs-lookup"><span data-stu-id="bd4f8-105">Dependency Network</span></span>](#bkmk_DepNet)  
  
-   [<span data-ttu-id="bd4f8-106">Perfis de atributo</span><span class="sxs-lookup"><span data-stu-id="bd4f8-106">Attribute Profiles</span></span>](#bkmk_AttProf)  
  
-   [<span data-ttu-id="bd4f8-107">Características do atributo</span><span class="sxs-lookup"><span data-stu-id="bd4f8-107">Attribute Characteristics</span></span>](#bkmk_AttChar)  
  
-   [<span data-ttu-id="bd4f8-108">Discriminação de atributo</span><span class="sxs-lookup"><span data-stu-id="bd4f8-108">Attribute Discrimination</span></span>](#bkmk_AttDisc)  
  
##  <a name="explore-the-model"></a><a name="BKMK_Tabs"></a><span data-ttu-id="bd4f8-109">Explorar o modelo</span><span class="sxs-lookup"><span data-stu-id="bd4f8-109">Explore the Model</span></span>  
 <span data-ttu-id="bd4f8-110">A finalidade do visualizador é ajudar a explorar a interação entre os atributos de entrada e saída (entradas e variáveis dependentes) que foram descobertos pelo modelo Naïve Bayes da [!INCLUDE[msCoName](../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd4f8-110">The purpose of the viewer is to help you explore the interaction between input and output attributes (inputs and dependent variables) that were discovered by the [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes model.</span></span>  
  
 <span data-ttu-id="bd4f8-111">Se você quiser experimentar o Bayes Viewer do ingênua, use o [Assistente para classificar &#40;suplementos de mineração de dados para Excel&#41;](classify-wizard-data-mining-add-ins-for-excel.md) na faixa de opções mineração de dados, clique na opção **avançado** e altere o algoritmo para usar o algoritmo de Bayes ingênua</span><span class="sxs-lookup"><span data-stu-id="bd4f8-111">If you want to experiment with the Naïve Bayes viewer, use the [Classify Wizard &#40;Data Mining Add-ins for Excel&#41;](classify-wizard-data-mining-add-ins-for-excel.md) wizard in the Data Mining ribbon, click the **Advanced** option, and change the algorithm to use the Naïve Bayes algorithm</span></span>  
  
 <span data-ttu-id="bd4f8-112">Para esses exemplos, usamos os dados de origem na pasta de trabalho de exemplo e agrupamos a coluna, **renda anual**, em cinco grupos de renda, de **muito baixo** para **muito alto**.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-112">For these examples, we used the Source data in the sample workbook, and grouped the column, **Yearly Income**, into five income groups, from **Very Low** to **Very High**.</span></span> <span data-ttu-id="bd4f8-113">O modelo Naïve Bayes analisou os fatores correlacionadas com cada categoria de renda.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-113">The Naïve Bayes model then analyzed the factors correlated with each income category.</span></span>  
  
###  <a name="dependency-network"></a><a name="bkmk_DepNet"></a><span data-ttu-id="bd4f8-114">Rede de dependências</span><span class="sxs-lookup"><span data-stu-id="bd4f8-114">Dependency Network</span></span>  
 <span data-ttu-id="bd4f8-115">A primeira janela que você usará é a **rede de dependência**.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-115">The first window you'll use is the **Dependency Network**.</span></span> <span data-ttu-id="bd4f8-116">Ela mostra uma visão geral cujas entradas estão estreitamente correlacionadas ao resultado selecionado.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-116">It shows you at a glance which inputs are closely correlated to the selected outcome.</span></span>  
  
 <span data-ttu-id="bd4f8-117">![rede de dependências no Visualizador Naive Bayes](media/dm13-nb.gif "rede de dependências no Visualizador Naive Bayes")</span><span class="sxs-lookup"><span data-stu-id="bd4f8-117">![dependency network in Naive Bayes viewer](media/dm13-nb.gif "dependency network in Naive Bayes viewer")</span></span>  
  
##### <a name="explore-the-dependency-network"></a><span data-ttu-id="bd4f8-118">Explorar a rede de dependências</span><span class="sxs-lookup"><span data-stu-id="bd4f8-118">Explore the dependency network</span></span>  
  
1.  <span data-ttu-id="bd4f8-119">Primeiro, clique no resultado de destino, **renda anual**, que é representado como um nó no grafo.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-119">First, click the target outcome, **Yearly Income**, which is represented as a node in the graph.</span></span>  
  
     <span data-ttu-id="bd4f8-120">Os nós realçados em volta da variável pretendida são os que estão correlacionadas estatisticamente com esse resultado.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-120">The highlighted nodes surrounding the target variable are those that are statistically correlated with this outcome.</span></span> <span data-ttu-id="bd4f8-121">Use a legenda na parte inferior do visualizador para entender a natureza da relação.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-121">Use the legend at the bottom of the viewer to understand the nature of the relationship.</span></span>  
  
2.  <span data-ttu-id="bd4f8-122">Clique no controle deslizante à esquerda do visualizador e arraste-o para baixo.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-122">Click the slider at the left of the viewer and drag it downward.</span></span>  
  
     <span data-ttu-id="bd4f8-123">Esse controle filtra as variáveis independentes, com base nos pontos fortes das dependências.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-123">This control filters the independent variables, based on the strengths of the dependencies.</span></span> <span data-ttu-id="bd4f8-124">Quando você arrasta o controle deslizante para baixo, apenas os links mais importantes permanecem no gráfico.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-124">When you drag the slider down, only the strongest links remain in the graph.</span></span>  
  
3.  <span data-ttu-id="bd4f8-125">Depois de filtrar o grafo, clique no botão **copiar exibição de gráfico**.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-125">After you have filtered the graph, click the button, **Copy Graph View**.</span></span> <span data-ttu-id="bd4f8-126">Selecione uma planilha do Excel e pressione Ctrl+V.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-126">Then select a worksheet in Excel, and press Ctrl+V.</span></span>  
  
     <span data-ttu-id="bd4f8-127">Essa opção copia a exibição selecionada, inclusive filtros e realce.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-127">This option copies the view that you have selected, including filters and highlighting.</span></span>  
  
 [<span data-ttu-id="bd4f8-128">Voltar ao início</span><span class="sxs-lookup"><span data-stu-id="bd4f8-128">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="attribute-profiles"></a><a name="bkmk_AttProf"></a> <span data-ttu-id="bd4f8-129">Perfis de Atributo</span><span class="sxs-lookup"><span data-stu-id="bd4f8-129">Attribute Profiles</span></span>  
 <span data-ttu-id="bd4f8-130">As janelas de **perfis de atributo** proporcionam a você uma indicação visual de como todas as outras variáveis estão relacionadas aos resultados individuais.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-130">The **Attribute Profiles** windows gives you a visual indication of how all other variables are related to the individual outcomes.</span></span>  
  
##### <a name="explore-the-profiles"></a><span data-ttu-id="bd4f8-131">Explorar os perfis</span><span class="sxs-lookup"><span data-stu-id="bd4f8-131">Explore the profiles</span></span>  
  
1.  <span data-ttu-id="bd4f8-132">Para ocultar alguns valores para que você possa comparar resultados mais facilmente, clique no título da coluna e arraste-o para baixo de outra coluna.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-132">To hide some values so that you can more easily compare outcomes, click the column heading and drag it under another column.</span></span>  
  
     <span data-ttu-id="bd4f8-133">![perfis de atributos no Visualizador Naive Bayes](media/dm13-nb-attprof.gif "perfis de atributos no Visualizador Naive Bayes")</span><span class="sxs-lookup"><span data-stu-id="bd4f8-133">![attribute profiles in Naive Bayes viewer](media/dm13-nb-attprof.gif "attribute profiles in Naive Bayes viewer")</span></span>  
  
2.  <span data-ttu-id="bd4f8-134">Clique em qualquer célula para exibir a distribuição de valores na **legenda de mineração**.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-134">Click in any cell to view the distribution of values in the **Mining Legend**.</span></span>  
  
     <span data-ttu-id="bd4f8-135">Como os atributos associados a resultados diferentes são exibidos visualmente, é fácil reconhecer correlações interessantes, por exemplo, como as rendas são distribuídas por região.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-135">Because the attributes associated with different outcomes are displayed visually, it is easy to spot interesting correlations, such as how incomes are distributed by region.</span></span>  
  
3.  <span data-ttu-id="bd4f8-136">Para obter os dados subjacentes a essa exibição, clique em **copiar para o Excel**.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-136">To obtain the data underlying this view, click **Copy to Excel**.</span></span> <span data-ttu-id="bd4f8-137">Uma tabela é gerada em uma nova planilha que mostra as correlações entre atributos individuais e resultados.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-137">A table is generated in a new worksheet that shows the correlations among individual attributes and outcomes.</span></span> <span data-ttu-id="bd4f8-138">Nessa tabela do Excel, você pode facilmente ocultar ou filtrar colunas.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-138">In this Excel table you can easily hide or filter columns.</span></span>  
  
 [<span data-ttu-id="bd4f8-139">Voltar ao início</span><span class="sxs-lookup"><span data-stu-id="bd4f8-139">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="attribute-characteristics"></a><a name="bkmk_AttChar"></a> <span data-ttu-id="bd4f8-140">Características do Atributo</span><span class="sxs-lookup"><span data-stu-id="bd4f8-140">Attribute Characteristics</span></span>  
 <span data-ttu-id="bd4f8-141">A exibição de **características de atributo** é útil para o exame detalhado de uma variável de resultado específica e os fatores de contribuição.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-141">The **Attribute Characteristics** view is useful for in-depth examination of a particular outcome variable and the contributing factors.</span></span>  
  
 <span data-ttu-id="bd4f8-142">![características de atributos no Visualizador Naive Bayes](media/dm13-nb-viewer.gif "características de atributos no Visualizador Naive Bayes")</span><span class="sxs-lookup"><span data-stu-id="bd4f8-142">![attribute characteristics in Naive Bayes viewer](media/dm13-nb-viewer.gif "attribute characteristics in Naive Bayes viewer")</span></span>  
  
##### <a name="explore-the-attribute-characteristics"></a><span data-ttu-id="bd4f8-143">Explorar as características do atributo</span><span class="sxs-lookup"><span data-stu-id="bd4f8-143">Explore the attribute characteristics</span></span>  
  
1.  <span data-ttu-id="bd4f8-144">Clique em **valor** e selecione um item do **valor**.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-144">Click **Value** and select an item from the **Value**.</span></span>  
  
     <span data-ttu-id="bd4f8-145">Quando você selecionar um resultado pretendido, o gráfico será atualizado para mostrar os fatores que estão mais fortemente associados ao resultado, classificados por importância.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-145">As you select a target outcome, the graph updates to show the factors that are most strongly associated with the outcome, sorted by importance.</span></span>  
  
     <span data-ttu-id="bd4f8-146">Observe que se você criar um modelo usando a opção [analisar influenciadores de chave &#40;ferramentas de análise de tabela para Excel&#41;](analyze-key-influencers-table-analysis-tools-for-excel.md) , poderá criar modelos que tenham mais de um atributo previsível.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-146">Note that if you create a model using the [Analyze Key Influencers &#40;Table Analysis Tools for Excel&#41;](analyze-key-influencers-table-analysis-tools-for-excel.md) option, you can create models that have more than one predictable attribute.</span></span> <span data-ttu-id="bd4f8-147">No entanto, todos os outros assistentes nos suplementos de Mineração de Dados limitam a um atributo previsível.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-147">However, all other wizards in the Data Mining add-ins limit you to one predictable attribute.</span></span>  
  
2.  <span data-ttu-id="bd4f8-148">Clique em **copiar para o Excel** para criar uma tabela, em uma nova planilha, listando as pontuações de todos os atributos relacionados ao resultado de destino selecionado.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-148">Click **Copy to Excel** to create a table, in a new worksheet, listing the scores for all attributes that are related to the selected target outcome.</span></span>  
  
 [<span data-ttu-id="bd4f8-149">Voltar ao início</span><span class="sxs-lookup"><span data-stu-id="bd4f8-149">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="attribute-discrimination"></a><a name="bkmk_AttDisc"></a> <span data-ttu-id="bd4f8-150">Distinção de Atributo</span><span class="sxs-lookup"><span data-stu-id="bd4f8-150">Attribute Discrimination</span></span>  
 <span data-ttu-id="bd4f8-151">A exibição de **discriminação de atributo** ajuda a comparar dois resultados, ou um resultado versus todos os outros resultados.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-151">The **Attribute Discrimination** view helps compare two outcomes, or one outcome vs. all other outcomes.</span></span>  
  
 <span data-ttu-id="bd4f8-152">![discriminação de atributos no Visualizador Naive Bayes](media/dm13-nb-attdisc.gif "discriminação de atributos no Visualizador Naive Bayes")</span><span class="sxs-lookup"><span data-stu-id="bd4f8-152">![attribute discrimination in Naive Bayes viewer](media/dm13-nb-attdisc.gif "attribute discrimination in Naive Bayes viewer")</span></span>  
  
##### <a name="explore-attribute-discrimination"></a><span data-ttu-id="bd4f8-153">Explorar distinção de atributo</span><span class="sxs-lookup"><span data-stu-id="bd4f8-153">Explore attribute discrimination</span></span>  
  
1.  <span data-ttu-id="bd4f8-154">Use os controles, **valor 1** e **valor 2**, para selecionar os resultados que você deseja comparar.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-154">Use the controls, **Value 1** and **Value 2**, to select the outcomes that you want to compare.</span></span>  
  
     <span data-ttu-id="bd4f8-155">Por exemplo, nesse modelo havia alguns atributos interessantes no grupo de baixo rendimento, portanto, escolhemos o menor grupo de renda na primeira lista suspensa e escolhemos **todos os outros Estados** na segunda lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-155">For example, in this model there were some interesting attributes in the low income group, so we chose the lowest income group in the first dropdown list, and chose **All other states** in the second dropdown list.</span></span>  
  
     <span data-ttu-id="bd4f8-156">Os atributos são classificados por ordem de importância (calculada com base nos dados de treinamento).</span><span class="sxs-lookup"><span data-stu-id="bd4f8-156">The attributes are sorted by order of importance (calculated based on the training data).</span></span> <span data-ttu-id="bd4f8-157">Consequentemente, a ocupação é o fator mais correlacionado com renda (para este grupo-alvo, pelo menos).</span><span class="sxs-lookup"><span data-stu-id="bd4f8-157">Therefore, occupation is the factor most closely correlated with income (for this target group, at least),</span></span>  
  
     <span data-ttu-id="bd4f8-158">Para ver as figuras exatas, clique na barra colorida e exiba a **legenda de mineração**.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-158">To see the exact figures, click the colored bar and view the **Mining Legend**.</span></span>  
  
2.  <span data-ttu-id="bd4f8-159">Observe que rendas mais baixas também estão correlacionadas com a região da Europa.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-159">Note that lower incomes are also correlated with the Europe region.</span></span>  
  
     <span data-ttu-id="bd4f8-160">O modelo Naïve Bayes não oferece suporte à busca detalhada; no entanto, se você quiser verificar os casos associados a esse grupo de resultados, poderá usar uma consulta.</span><span class="sxs-lookup"><span data-stu-id="bd4f8-160">The Naïve Bayes model does not support drilldown; however, if you wanted to investigate the cases associated with this outcome group, you could use a query.</span></span> <span data-ttu-id="bd4f8-161">Para obter informações sobre consultas sobre esse tipo de modelo, consulte [exemplos de consulta de modelo do Naive Bayes](data-mining/naive-bayes-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="bd4f8-161">For information about queries on this type of model, see [Naive Bayes Model Query Examples](data-mining/naive-bayes-model-query-examples.md).</span></span>  
  
 [<span data-ttu-id="bd4f8-162">Voltar ao início</span><span class="sxs-lookup"><span data-stu-id="bd4f8-162">Back To Top</span></span>](#BKMK_Tabs)  
  
## <a name="see-also"></a><span data-ttu-id="bd4f8-163">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bd4f8-163">See Also</span></span>  
 [<span data-ttu-id="bd4f8-164">Pesquisando modelos no Excel &#40;SQL Server suplementos de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="bd4f8-164">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
