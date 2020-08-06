---
title: Navegando em um modelo de árvores de decisão | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- mining models, viewing
- tree viewer
- mining model, decision tree
- decision tree [data mining]
- dependency network
ms.assetid: 6b3dd1ae-caff-41c3-817b-802dc020ff88
author: minewiskan
ms.author: owend
ms.openlocfilehash: 809d2e494cfa7a6c4078acf95c2c70a0e68c188d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571120"
---
# <a name="browsing-a-decision-trees-model"></a><span data-ttu-id="90eb6-102">Procurando um modelo de árvores de decisão</span><span class="sxs-lookup"><span data-stu-id="90eb6-102">Browsing a Decision Trees Model</span></span>
  <span data-ttu-id="90eb6-103">Quando você abre um modelo de classificação usando **procurar**, o modelo é exibido em um visualizador de árvore de decisão interativa, semelhante ao [!INCLUDE[msCoName](../includes/msconame-md.md)] Visualizador de árvores de decisão no [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="90eb6-103">When you open a classification model using **Browse**, the model is displayed in an interactive decision tree viewer, similar to the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees viewer in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="90eb6-104">O visualizador exibe os resultados da classificação como um gráfico que foi criado para realçar os critérios que diferenciam um grupo de dados do outro.</span><span class="sxs-lookup"><span data-stu-id="90eb6-104">The viewer displays the results of classification as a graph that is designed to highlight the criteria that differentiate one group of data from another.</span></span> <span data-ttu-id="90eb6-105">Você também pode analisar subconjuntos individuais da árvore e recuperar os dados subjacentes.</span><span class="sxs-lookup"><span data-stu-id="90eb6-105">You can also drill down into individual subsets of the tree and retrieve the underlying data.</span></span>  
  
##  <a name="explore-the-model"></a><a name="bkmk_Top"></a><span data-ttu-id="90eb6-106">Explorar o modelo</span><span class="sxs-lookup"><span data-stu-id="90eb6-106">Explore the Model</span></span>  
 <span data-ttu-id="90eb6-107">Os modelos baseados no algoritmo Árvores de Decisão têm várias informações interessantes para explorar.</span><span class="sxs-lookup"><span data-stu-id="90eb6-107">Models based on the Decision Trees algorithm have lots of interesting information to explore.</span></span> <span data-ttu-id="90eb6-108">A janela **procurar** inclui as seguintes guias e painéis para ajudá-lo a aprender os padrões e prever os resultados usando o grafo:</span><span class="sxs-lookup"><span data-stu-id="90eb6-108">The **Browse** window includes the following tabs and panes to help you learn the patterns and predict outcomes using the graph:</span></span>  
  
-   [<span data-ttu-id="90eb6-109">Árvore de decisões</span><span class="sxs-lookup"><span data-stu-id="90eb6-109">Decision Tree</span></span>](#BKMK_DecisionTree)  
  
-   [<span data-ttu-id="90eb6-110">Rede de Dependências</span><span class="sxs-lookup"><span data-stu-id="90eb6-110">Dependency Network</span></span>](#BKMK_DNetwork)  
  
 <span data-ttu-id="90eb6-111">Para experimentar um modelo de árvores de decisão, você poderá usar os dados de exemplo na guia Dados de Treinamento (ou os Dados de Origem) da pasta de trabalho de dados de exemplo e criar um modelo de árvore de decisão usando Bike Buyer como o atributo previsível.</span><span class="sxs-lookup"><span data-stu-id="90eb6-111">To experiment with a decision trees model, you can use the sample data on the Training Data (or Source Data) tab of the sample data workbook, and build a decision tree model using Bike Buyer as the predictable attribute.</span></span>  
  
###  <a name="decision-tree"></a><a name="BKMK_DecisionTree"></a><span data-ttu-id="90eb6-112">Árvore de decisão</span><span class="sxs-lookup"><span data-stu-id="90eb6-112">Decision Tree</span></span>  
 <span data-ttu-id="90eb6-113">Essa exibição pretende ajudá-lo a compreender e explorar os fatores que levam a um resultado.</span><span class="sxs-lookup"><span data-stu-id="90eb6-113">This view is intended to help you understand and explore the factors that lead to an outcome.</span></span>  
  
 <span data-ttu-id="90eb6-114">O gráfico da árvore de decisão pode ser lido da esquerda para a direita da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="90eb6-114">The decision tree graph can be read from left to right as follows:</span></span>  
  
-   <span data-ttu-id="90eb6-115">Os retângulos, que são chamados de *nós*, contêm subconjuntos dos dados.</span><span class="sxs-lookup"><span data-stu-id="90eb6-115">The rectangles, which are referred to as *nodes*, contain subsets of the data.</span></span> <span data-ttu-id="90eb6-116">O rótulo no nó informa as características de definição desse subconjunto.</span><span class="sxs-lookup"><span data-stu-id="90eb6-116">The label on the node tells you the defining characteristics of that subset.</span></span>  
  
-   <span data-ttu-id="90eb6-117">O nó mais à esquerda, rotulado como **todos**, representa o conjunto de dados completo.</span><span class="sxs-lookup"><span data-stu-id="90eb6-117">The leftmost node, labeled **All**, represents the complete data set.</span></span> <span data-ttu-id="90eb6-118">Todos os nós subsequentes representam subconjuntos dos dados.</span><span class="sxs-lookup"><span data-stu-id="90eb6-118">All subsequent nodes represent subsets of the data.</span></span>  
  
-   <span data-ttu-id="90eb6-119">Uma árvore de decisão contém muitas *divisões*ou locais onde os dados divergem em vários conjuntos com base em atributos.</span><span class="sxs-lookup"><span data-stu-id="90eb6-119">A decision tree contains many *splits*, or places where the data diverges into multiple sets based on attributes.</span></span>  
  
     <span data-ttu-id="90eb6-120">Por exemplo, a primeira divisão no modelo de exemplo divide o conjunto de dados em três grupos por idade.</span><span class="sxs-lookup"><span data-stu-id="90eb6-120">For example, the first split in the sample model divides the dataset into three groups by age.</span></span>  
  
-   <span data-ttu-id="90eb6-121">A divisão imediatamente após o nó **All** é mais importante porque mostra a condição principal que divide esse conjunto de DataSet.</span><span class="sxs-lookup"><span data-stu-id="90eb6-121">The split immediately after the **All** node is most important because it shows the primary condition that divides this dataset.</span></span>  
  
     <span data-ttu-id="90eb6-122">Divisões adicionais ocorrem à direita.</span><span class="sxs-lookup"><span data-stu-id="90eb6-122">Additional splits occur to the right.</span></span> <span data-ttu-id="90eb6-123">Portanto, ao analisar segmentos diferentes da árvore, você poderá saber quais atributos tinham mais influência sobre o comportamento de compra.</span><span class="sxs-lookup"><span data-stu-id="90eb6-123">Thus, by analyzing different segments of the tree, you can learn which attributes had the most influence on purchasing behavior.</span></span>  
  
 <span data-ttu-id="90eb6-124">![Gráfico da rede de dependências para um modelo de associação](media/dm13-dec-tree-split-definition.gif "Gráfico da rede de dependências para um modelo de associação")</span><span class="sxs-lookup"><span data-stu-id="90eb6-124">![Dependency network graph for an association model](media/dm13-dec-tree-split-definition.gif "Dependency network graph for an association model")</span></span>  
  
 <span data-ttu-id="90eb6-125">Usando essas informações, você poderá concentrar uma campanha de marketing nos clientes que podem apenas precisar de incentivo para fazer uma compra.</span><span class="sxs-lookup"><span data-stu-id="90eb6-125">Using this information, you might focus a marketing campaign on customers that might simply need encouragement to make a purchase.</span></span>  
  
##### <a name="explore-the-decision-tree"></a><span data-ttu-id="90eb6-126">Explorar a árvore de decisão</span><span class="sxs-lookup"><span data-stu-id="90eb6-126">Explore the decision tree</span></span>  
  
1.  <span data-ttu-id="90eb6-127">Clique no nó **todos** e examine a legenda de **mineração**.</span><span class="sxs-lookup"><span data-stu-id="90eb6-127">Click the **All** node, and look at the **Mining Legend**.</span></span>  
  
     <span data-ttu-id="90eb6-128">Ela exibe a contagem exata dos casos no conjunto de dados de treinamento, assim como uma análise dos resultados.</span><span class="sxs-lookup"><span data-stu-id="90eb6-128">It displays the exact count of cases in the training data set, as well as a breakdown of the outcomes.</span></span>  
  
     <span data-ttu-id="90eb6-129">Você poderá exibir as mesmas informações em uma dica de ferramenta se para o mouse sobre um nó.</span><span class="sxs-lookup"><span data-stu-id="90eb6-129">You can view the same information in a tooltip if you pause the mouse over a node.</span></span>  
  
2.  <span data-ttu-id="90eb6-130">Clique nos sinais de adição e subtração ao lado de cada nó para expandir ou recolher a árvore.</span><span class="sxs-lookup"><span data-stu-id="90eb6-130">Click the plus and minus signs next to each node to expand or collapse the tree.</span></span>  
  
     <span data-ttu-id="90eb6-131">Você também pode usar o controle deslizante **Mostrar nível** para expandir ou reduzir a árvore.</span><span class="sxs-lookup"><span data-stu-id="90eb6-131">You can also use the **Show Level** slider to expand or shrink the tree.</span></span>  
  
3.  <span data-ttu-id="90eb6-132">Observa que alguns nós são mais escuros do que outros?</span><span class="sxs-lookup"><span data-stu-id="90eb6-132">Notice that some nodes are darker than others?</span></span>  
  
     <span data-ttu-id="90eb6-133">Por padrão, a **população** é usada como a variável de sombreamento, o que significa que a intensidade da cor mostra quais nós têm o máximo de suporte.</span><span class="sxs-lookup"><span data-stu-id="90eb6-133">By default, **Population** is used as the shading variable, which means that the intensity of the color shows you which nodes have the most support.</span></span>  
  
     <span data-ttu-id="90eb6-134">Consequentemente, o nó mais à esquerda é o mais escuro, porque contém o conjunto de dados inteiro.</span><span class="sxs-lookup"><span data-stu-id="90eb6-134">Therefore the leftmost node is darkest, because it contains the entire dataset.</span></span>  
  
4.  <span data-ttu-id="90eb6-135">Altere o valor de **plano de fundo** de **todos os casos** para **Sim**.</span><span class="sxs-lookup"><span data-stu-id="90eb6-135">Change the value for **Background** from **All Cases** to **Yes**.</span></span>  
  
     <span data-ttu-id="90eb6-136">![alterando o gráfico de árvore de decisão para realçar compradores](media/dm13-dectreeshadedbuyer.gif "alterando o gráfico de árvore de decisão para realçar compradores")</span><span class="sxs-lookup"><span data-stu-id="90eb6-136">![changing decision tree graph to highlight buyers](media/dm13-dectreeshadedbuyer.gif "changing decision tree graph to highlight buyers")</span></span>  
  
5.  <span data-ttu-id="90eb6-137">Agora a intensidade da cor informa quantos clientes em cada nó compraram uma bicicleta, que é o comportamento no qual você está interessado.</span><span class="sxs-lookup"><span data-stu-id="90eb6-137">Now the intensity of the color tells you how many customers in each node purchased a bike, which is the behavior you are interested in.</span></span>  
  
     <span data-ttu-id="90eb6-138">Observe as barras coloridas em cada nó.</span><span class="sxs-lookup"><span data-stu-id="90eb6-138">Notice the colored bars within each node.</span></span> <span data-ttu-id="90eb6-139">Este é um histograma que mostra a distribuição de resultados nesse subconjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="90eb6-139">This is a histogram that shows the distribution of outcomes within this subset of data.</span></span> <span data-ttu-id="90eb6-140">Por exemplo, na árvore de decisão de comprador de bicicletas de amostra, a barra colorida mostra a proporção de clientes que compraram bicicletas (valores Sim) versus aqueles que não (nenhum valor).</span><span class="sxs-lookup"><span data-stu-id="90eb6-140">For example, in the sample Bike Buyer decision tree, the colored bar shows the proportion of customers who bought bikes (Yes values) vs. those who did not (No values).</span></span> <span data-ttu-id="90eb6-141">Para obter os valores exatos, você pode clicar no nó e exibir a **legenda de mineração**.</span><span class="sxs-lookup"><span data-stu-id="90eb6-141">To get the exact values, you can click the node and view the **Mining Legend**.</span></span>  
  
6.  <span data-ttu-id="90eb6-142">Ao seguir o gráfico, você poderá ver como cada subconjunto de dados é decomposto em grupos menores, e quais os atributos são os mais úteis para prever um resultado.</span><span class="sxs-lookup"><span data-stu-id="90eb6-142">By following the graph, you can see how each subset of data is further decomposed into smaller groups, and which attributes are most useful in predicting an outcome.</span></span>  
  
     <span data-ttu-id="90eb6-143">Apenas examinar a intensidade do sombreamento, você poderá se concentrar em alguns grupos de interesse, e obter dados mais detalhados sobre eles para comparação.</span><span class="sxs-lookup"><span data-stu-id="90eb6-143">Just by looking at the intensity of the shading, you can focus on a couple groups of interest, and get more detailed data on them for comparison.</span></span> <span data-ttu-id="90eb6-144">Por exemplo, esses grupos têm uma probabilidade consideravelmente mais alta de comprar bicicletas:</span><span class="sxs-lookup"><span data-stu-id="90eb6-144">For example, these groups have a fairly high probability of buying bikes:</span></span>  
  
    -   <span data-ttu-id="90eb6-145">Age >= 32 e \< 53 and Yearly Income > = 26000 e filhos = 0</span><span class="sxs-lookup"><span data-stu-id="90eb6-145">Age >= 32 and \< 53 and Yearly Income >= 26000 and Children = 0</span></span>  
  
         <span data-ttu-id="90eb6-146">Total de casos: 1150</span><span class="sxs-lookup"><span data-stu-id="90eb6-146">Total cases: 1150</span></span>  
  
         <span data-ttu-id="90eb6-147">Probabilidade do comprador de bicicletas: 18%</span><span class="sxs-lookup"><span data-stu-id="90eb6-147">Bike buyer probability: 18%</span></span>  
  
    -   <span data-ttu-id="90eb6-148">Age >= 32 e \< 53 and Yearly Income > = 26000 e filhos não = 0 e status civil = ' single '</span><span class="sxs-lookup"><span data-stu-id="90eb6-148">Age >= 32 and \< 53 and Yearly Income >= 26000 and Children not = 0 and Marital Status = 'Single'</span></span>  
  
         <span data-ttu-id="90eb6-149">Total de casos: 402</span><span class="sxs-lookup"><span data-stu-id="90eb6-149">Total cases: 402</span></span>  
  
         <span data-ttu-id="90eb6-150">Probabilidade do comprador de bicicletas: 16%</span><span class="sxs-lookup"><span data-stu-id="90eb6-150">Bike buyer probability: 16%</span></span>  
  
7.  <span data-ttu-id="90eb6-151">Altere o valor de **plano de fundo** de **Sim** para **não** e veja como o grafo é alterado.</span><span class="sxs-lookup"><span data-stu-id="90eb6-151">Change the value for **Background** from **Yes** to **No** and see how the graph changes.</span></span>  
  
     <span data-ttu-id="90eb6-152">![Gráfico da rede de dependências para um modelo de associação](media/dm13-dec-tree-background-no.gif "Gráfico da rede de dependências para um modelo de associação")</span><span class="sxs-lookup"><span data-stu-id="90eb6-152">![Dependency network graph for an association model](media/dm13-dec-tree-background-no.gif "Dependency network graph for an association model")</span></span>  
  
 <span data-ttu-id="90eb6-153">**Dicas**</span><span class="sxs-lookup"><span data-stu-id="90eb6-153">**Tips**</span></span>  
  
-   <span data-ttu-id="90eb6-154">Se os dados puderem ser divididos em várias séries, um modelo diferente será criado para cada conjunto de dados que você quiser modelar.</span><span class="sxs-lookup"><span data-stu-id="90eb6-154">If your data can be divided into multiple series, a different model is built for each set of data that you want to model.</span></span>  
  
-   <span data-ttu-id="90eb6-155">No modelo de dados de exemplo, há apenas um comprador de bicicletas de resultado previsível, mas suponha que você tenha informações sobre se o cliente comprou um plano de serviço e queria prever isso também.</span><span class="sxs-lookup"><span data-stu-id="90eb6-155">In the sample data model, there is only one predictable outcome - Bike Buyer - but suppose you had information about whether the customer purchased a service plan and wanted to predict that as well.</span></span> <span data-ttu-id="90eb6-156">Nesse caso, você teria esses dados em uma coluna separada e incluiria dois atributos previsíveis no modelo.</span><span class="sxs-lookup"><span data-stu-id="90eb6-156">In that case you would have that data in a separate column, and include two predictable attributes in the model.</span></span>  
  
     <span data-ttu-id="90eb6-157">Clique na opção **histograma** , no canto superior esquerdo do painel árvore de decisão, para alterar o número máximo de Estados que podem aparecer nos histogramas da árvore.</span><span class="sxs-lookup"><span data-stu-id="90eb6-157">Click the **Histogram** option, in the upper left corner of the Decision Tree pane, to change the maximum number of states that can appear in the histograms in the tree.</span></span> <span data-ttu-id="90eb6-158">Isso será útil se o atributo previsível tiver muitos estados.</span><span class="sxs-lookup"><span data-stu-id="90eb6-158">This is useful if the predictable attribute has many states.</span></span> <span data-ttu-id="90eb6-159">Os estados aparecem em um histograma na ordem de popularidade da esquerda para a direita.</span><span class="sxs-lookup"><span data-stu-id="90eb6-159">The states appear in a histogram in order of popularity from left to right.</span></span>  
  
-   <span data-ttu-id="90eb6-160">Você também pode usar as opções na guia **árvore de decisão** para afetar a forma como a árvore é exibida, ampliando ou redimensionando o gráfico para se ajustar à janela.</span><span class="sxs-lookup"><span data-stu-id="90eb6-160">You can also use the options on the **Decision Tree** tab to affect how the tree is displayed, by zooming in or out, or sizing the graph to fit the window.</span></span>  
  
-   <span data-ttu-id="90eb6-161">Use a opção **Expansão Padrão** para definir o número padrão de níveis exibidos em todas as árvores no modelo.</span><span class="sxs-lookup"><span data-stu-id="90eb6-161">Use **Default Expansion** to set the default number of levels that are displayed for all trees in the model.</span></span>  
  
-   <span data-ttu-id="90eb6-162">Selecione **Mostrar nome longo** para exibir o nome completo do atributo, incluindo a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="90eb6-162">Select **Show long name** to display the full name of the attribute, including the data source.</span></span> <span data-ttu-id="90eb6-163">Os nomes curtos e longos são iguais, a menos que seus casos sejam obtidos de uma fonte de dados diferente dos atributos para cada caso.</span><span class="sxs-lookup"><span data-stu-id="90eb6-163">Short names and long names are the same unless your cases are obtained from a different data source than the attributes for each case.</span></span>  
  
 [<span data-ttu-id="90eb6-164">Voltar ao início</span><span class="sxs-lookup"><span data-stu-id="90eb6-164">Back To Top</span></span>](#bkmk_Top)  
  
###  <a name="dependency-network"></a><a name="BKMK_DNetwork"></a><span data-ttu-id="90eb6-165">Rede de dependências</span><span class="sxs-lookup"><span data-stu-id="90eb6-165">Dependency Network</span></span>  
 <span data-ttu-id="90eb6-166">A exibição **rede de dependências** exibe as conexões entre os atributos de entrada e os atributos previsíveis no modelo.</span><span class="sxs-lookup"><span data-stu-id="90eb6-166">The **Dependency Network** view displays the connections between the input attributes and the predictable attributes in the model.</span></span>  
  
1.  <span data-ttu-id="90eb6-167">Clique e arraste o controle deslizante à esquerda do visualizador</span><span class="sxs-lookup"><span data-stu-id="90eb6-167">Click and drag the slider at the left of the viewer</span></span>  
  
     <span data-ttu-id="90eb6-168">Na posição superior, todas as conexões são mostradas.</span><span class="sxs-lookup"><span data-stu-id="90eb6-168">At the top position, all connections are shown.</span></span> <span data-ttu-id="90eb6-169">Quando você arrasta o controle deslizante para baixo, apenas os links mais importantes são mostrados no visualizador.</span><span class="sxs-lookup"><span data-stu-id="90eb6-169">When you drag the slider down, only the strongest links are shown in the viewer.</span></span>  
  
2.  <span data-ttu-id="90eb6-170">Agora clique no nó Comprador de bicicleta.</span><span class="sxs-lookup"><span data-stu-id="90eb6-170">Now click the Bike Buyer node.</span></span>  
  
     <span data-ttu-id="90eb6-171">![Exibição de rede de dependência para árvores de decisão](media/dm13-dectree-depnet.gif "Exibição de rede de dependência para árvores de decisão")</span><span class="sxs-lookup"><span data-stu-id="90eb6-171">![Dependency network view for decision trees](media/dm13-dectree-depnet.gif "Dependency network view for decision trees")</span></span>  
  
     <span data-ttu-id="90eb6-172">Quando você selecionar um nó, o visualizador destacará as dependências específicas ao nó.</span><span class="sxs-lookup"><span data-stu-id="90eb6-172">When you select a node, the viewer highlights the dependencies that are specific to the node.</span></span> <span data-ttu-id="90eb6-173">Nesse caso, o visualizador destacará cada nó que ajuda a prever o resultado.</span><span class="sxs-lookup"><span data-stu-id="90eb6-173">In this case, the viewer highlights each node that helps predict the outcome.</span></span>  
  
3.  <span data-ttu-id="90eb6-174">Se o visualizador contiver muitos nós, você poderá pesquisar nós específicos usando o botão **Localizar nó** .</span><span class="sxs-lookup"><span data-stu-id="90eb6-174">If the viewer contains many nodes, you can search for specific nodes by using the **Find Node** button.</span></span> <span data-ttu-id="90eb6-175">Clicar em **Localizar Nó** faz com que a caixa de diálogo **Localizar Nó** seja aberta, na qual você pode usar um filtro para pesquisar e selecionar nós específicos.</span><span class="sxs-lookup"><span data-stu-id="90eb6-175">Clicking **Find Node** opens the **Find Node** dialog box, in which you can use a filter to search for and select specific nodes.</span></span>  
  
4.  <span data-ttu-id="90eb6-176">A legenda na parte inferior do visualizador vincula os nós de cores ao tipo de dependência no gráfico.</span><span class="sxs-lookup"><span data-stu-id="90eb6-176">The legend at the bottom of the viewer links color codes to the type of dependency in the graph.</span></span> <span data-ttu-id="90eb6-177">Por exemplo, quando você seleciona um nó previsível, ele fica sombreado na cor turquesa e os nós que preveem o nó selecionado são sombreados em laranja.</span><span class="sxs-lookup"><span data-stu-id="90eb6-177">For example, when you select a predictable node, the predictable node is shaded turquoise, and the nodes that predict the selected node are shaded orange.</span></span>  
  
 [<span data-ttu-id="90eb6-178">Voltar ao início</span><span class="sxs-lookup"><span data-stu-id="90eb6-178">Back To Top</span></span>](#bkmk_Top)  
  
### <a name="drill-through-to-underlying-data"></a><span data-ttu-id="90eb6-179">Detalhar os dados subjacentes</span><span class="sxs-lookup"><span data-stu-id="90eb6-179">Drill through to Underlying Data</span></span>  
 <span data-ttu-id="90eb6-180">Vários tipos de modelos oferecem suporte à capacidade de *detalhamento* do modelo para os dados de caso subjacentes.</span><span class="sxs-lookup"><span data-stu-id="90eb6-180">Several types of models support the ability to *drill through* from the model to the underlying case data.</span></span> <span data-ttu-id="90eb6-181">Isso pode ser muito útil se você quiser contatar os clientes em um segmento específico ou retirar os dados para executar uma análise mais detalhada.</span><span class="sxs-lookup"><span data-stu-id="90eb6-181">This can be very useful if you want to contact customers in a particular segment or pull out the data to perform further analysis.</span></span>  
  
##### <a name="get-case-data"></a><span data-ttu-id="90eb6-182">Obter dados de caso</span><span class="sxs-lookup"><span data-stu-id="90eb6-182">Get case data</span></span>  
  
1.  <span data-ttu-id="90eb6-183">Clique com o botão direito do mouse no nó na árvore que contém os dados desejados e selecione uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="90eb6-183">Right-click the node in the tree that contains the desired data and select one of these options:</span></span>  
  
    -   <span data-ttu-id="90eb6-184">**Modelo de Drill-through**.</span><span class="sxs-lookup"><span data-stu-id="90eb6-184">**Drill Through Model**.</span></span> <span data-ttu-id="90eb6-185">Essa opção obtém os casos que pertencem ao nó selecionado e salva-os em uma tabela no Excel.</span><span class="sxs-lookup"><span data-stu-id="90eb6-185">This option gets the cases that belong to the selected node, and saves them to a table in Excel.</span></span> <span data-ttu-id="90eb6-186">Você obtém de volta apenas as colunas de dados que foram realmente usadas para criar o modelo.</span><span class="sxs-lookup"><span data-stu-id="90eb6-186">You get back only the columns of data that were actually used in building the model.</span></span>  
  
    -   <span data-ttu-id="90eb6-187">**Detalhar colunas de estrutura**.</span><span class="sxs-lookup"><span data-stu-id="90eb6-187">**Drill Through Structure Columns**.</span></span> <span data-ttu-id="90eb6-188">Essa opção obtém os casos que pertencem ao nó selecionado e salva-os em uma tabela no Excel.</span><span class="sxs-lookup"><span data-stu-id="90eb6-188">This option gets the cases that belong to the selected node, and saves them to a table in Excel.</span></span> <span data-ttu-id="90eb6-189">Você obtém todas as informações disponíveis nos dados subjacentes quando a criou, mesmo de uma coluna não foi usada no modelo.</span><span class="sxs-lookup"><span data-stu-id="90eb6-189">You get all information that was available in the underlying data when you built it, even of a column wasn't used in the model.</span></span> <span data-ttu-id="90eb6-190">Por exemplo, você pode ter excluído o endereço e o código postal do cliente porque esses campos não são úteis na análise, mas deixou-os na estrutura.</span><span class="sxs-lookup"><span data-stu-id="90eb6-190">For example, you might have excluded the customer address and zip code because those fields are not useful with analysis, but left them in the structure.</span></span>  
  
     <span data-ttu-id="90eb6-191">Retorne para o Excel para exibir seus dados.</span><span class="sxs-lookup"><span data-stu-id="90eb6-191">Return to Excel to view your data.</span></span> <span data-ttu-id="90eb6-192">O visualizador Procurar executa uma consulta, salva os dados em uma tabela em uma nova planilha e rotula os resultados.</span><span class="sxs-lookup"><span data-stu-id="90eb6-192">The Browse viewer runs a query, saves the data to a table in a new worksheet, and labels the results.</span></span>  
  
     <span data-ttu-id="90eb6-193">![os resultados de detalhamento são salvos no Excel](media/dm13-dectree-drillthroughresults.gif "os resultados de detalhamento são salvos no Excel")</span><span class="sxs-lookup"><span data-stu-id="90eb6-193">![results of drillthrough are saved to Excel](media/dm13-dectree-drillthroughresults.gif "results of drillthrough are saved to Excel")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90eb6-194">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="90eb6-194">See Also</span></span>  
 [<span data-ttu-id="90eb6-195">Pesquisando modelos no Excel &#40;SQL Server suplementos de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="90eb6-195">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
