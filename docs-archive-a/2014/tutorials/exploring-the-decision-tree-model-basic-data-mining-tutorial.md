---
title: Explorando o modelo de árvore de decisão (tutorial de mineração de dados básico) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2e1472c2-3f3e-4dae-acb3-62fca374d397
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a2c7f063d7cb73cdc431fb1bc94188c9266c10c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681976"
---
# <a name="exploring-the-decision-tree-model-basic-data-mining-tutorial"></a><span data-ttu-id="38314-102">Explorando o modelo de árvore de decisão (Tutorial de mineração de dados básico)</span><span class="sxs-lookup"><span data-stu-id="38314-102">Exploring the Decision Tree Model (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="38314-103">O algoritmo Árvores de Decisão da [!INCLUDE[msCoName](../includes/msconame-md.md)] prevê que colunas influenciam a decisão de compra de uma bicicleta com base nas colunas restantes do conjunto de treinamento.</span><span class="sxs-lookup"><span data-stu-id="38314-103">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm predicts which columns influence the decision to purchase a bike based upon the remaining columns in the training set.</span></span>  
  

  
##  <a name="decision-tree-tab"></a><a name="Decision_Tree_Tab"></a><span data-ttu-id="38314-104">Guia árvore de decisão</span><span class="sxs-lookup"><span data-stu-id="38314-104">Decision Tree Tab</span></span>  
 <span data-ttu-id="38314-105">Na guia **árvore de decisão** , você pode exibir árvores de decisão para cada atributo previsível no conjunto de um.</span><span class="sxs-lookup"><span data-stu-id="38314-105">On the **Decision Tree** tab, you can view decision trees for every predictable attribute in the dataset.</span></span>  
  
 <span data-ttu-id="38314-106">Nesse caso, o modelo prevê apenas uma coluna, comprador de bicicletas e, portanto, há apenas uma árvore a ser exibida.</span><span class="sxs-lookup"><span data-stu-id="38314-106">In this case, the model predicts only one column, Bike Buyer, so there is only one tree to view.</span></span> <span data-ttu-id="38314-107">Se houver mais árvores, você poderá usar a caixa de **árvore** para escolher outra árvore.</span><span class="sxs-lookup"><span data-stu-id="38314-107">If there were more trees, you could use the **Tree** box to choose another tree.</span></span>  
  
 <span data-ttu-id="38314-108">Ao exibir o `TM_Decision_Tree` modelo no Visualizador de árvore de decisão, você pode ver os atributos mais importantes no lado esquerdo do gráfico.</span><span class="sxs-lookup"><span data-stu-id="38314-108">As you view the `TM_Decision_Tree` model in the Decision Tree viewer, you can see the most important attributes at the left side of the chart.</span></span> <span data-ttu-id="38314-109">"Mais importante" significa que esses atributos têm a maior influência sobre o resultado.</span><span class="sxs-lookup"><span data-stu-id="38314-109">"Most important" means that these attributes have the greatest influence on the outcome.</span></span> <span data-ttu-id="38314-110">Os atributos mais abaixo na árvore (à direita do gráfico) têm menos influência.</span><span class="sxs-lookup"><span data-stu-id="38314-110">Attributes further down the tree (to the right of the chart) have less of an effect.</span></span>  
  
 <span data-ttu-id="38314-111">Neste exemplo, a idade é o fator mais importante na previsão da compra de bicicletas.</span><span class="sxs-lookup"><span data-stu-id="38314-111">In this example, age is the single most important factor in predicting bike buying.</span></span> <span data-ttu-id="38314-112">O modelo agrupa os clientes por idade e depois mostra o próximo atributo mais importante de cada faixa etária.</span><span class="sxs-lookup"><span data-stu-id="38314-112">The model groups customers by age, and then shows the next more important attribute for each age group.</span></span> <span data-ttu-id="38314-113">Por exemplo, no grupo de clientes com idades entre 34 e 40 anos, o número de carros é o fator de previsão mais importante depois da idade.</span><span class="sxs-lookup"><span data-stu-id="38314-113">For example, in the group of customers aged 34 to 40, the number of cars owned is the strongest predictor after age.</span></span>  
  
#### <a name="to-explore-the-model-in-the-decision-tree-tab"></a><span data-ttu-id="38314-114">Para explorar o modelo na guia Árvore de Decisão</span><span class="sxs-lookup"><span data-stu-id="38314-114">To explore the model in the Decision Tree tab</span></span>  
  
1.  <span data-ttu-id="38314-115">Selecione a guia **Visualizador do modelo de mineração** no designer de mineração de **dados**.</span><span class="sxs-lookup"><span data-stu-id="38314-115">Select the **Mining Model Viewer** tab in **Data Mining Designer**.</span></span>  
  
     <span data-ttu-id="38314-116">Por padrão, o designer é aberto para o primeiro modelo que foi adicionado à estrutura – nesse caso, `TM_Decision_Tree` .</span><span class="sxs-lookup"><span data-stu-id="38314-116">By default, the designer opens to the first model that was added to the structure -- in this case, `TM_Decision_Tree`.</span></span>  
  
2.  <span data-ttu-id="38314-117">Use os botões de lente de aumento para ajustar o tamanho da exibição da árvore.</span><span class="sxs-lookup"><span data-stu-id="38314-117">Use the magnifying glass buttons to adjust the size of the tree display.</span></span>  
  
     <span data-ttu-id="38314-118">Por padrão, o Visualizador de Árvore da [!INCLUDE[msCoName](../includes/msconame-md.md)] mostra somente os três primeiros níveis da árvore.</span><span class="sxs-lookup"><span data-stu-id="38314-118">By default, the [!INCLUDE[msCoName](../includes/msconame-md.md)] Tree Viewer shows only the first three levels of the tree.</span></span> <span data-ttu-id="38314-119">Se a árvore tiver menos de três níveis, o visualizador mostrará só os níveis existentes.</span><span class="sxs-lookup"><span data-stu-id="38314-119">If the tree contains fewer than three levels, the viewer shows only the existing levels.</span></span> <span data-ttu-id="38314-120">Você pode exibir mais níveis usando o controle deslizante **Mostrar nível** ou a lista de **expansão padrão** .</span><span class="sxs-lookup"><span data-stu-id="38314-120">You can view more levels by using the **Show Level** slider or the **Default Expansion** list.</span></span>  
  
3.  <span data-ttu-id="38314-121">Deslizar **nível de apresentação** para a quarta barra.</span><span class="sxs-lookup"><span data-stu-id="38314-121">Slide **Show Level** to the fourth bar.</span></span>  
  
4.  <span data-ttu-id="38314-122">Altere o valor de **plano de fundo** para `1` .</span><span class="sxs-lookup"><span data-stu-id="38314-122">Change the **Background** value to `1`.</span></span>  
  
     <span data-ttu-id="38314-123">Alterando a configuração de **plano de fundo** , você pode ver rapidamente o número de casos em cada nó que têm o valor de destino de `1` para [comprador de bicicletas].</span><span class="sxs-lookup"><span data-stu-id="38314-123">By changing the **Background** setting, you can quickly see the number of cases in each node that have the target value of `1` for [Bike Buyer].</span></span> <span data-ttu-id="38314-124">Lembre-se de que neste cenário específico, cada caso representa um cliente.</span><span class="sxs-lookup"><span data-stu-id="38314-124">Remember that in this particular scenario, each case represents a customer.</span></span> <span data-ttu-id="38314-125">O valor `1` indica que o cliente comprou uma bicicleta anteriormente. o valor **0** indica que o cliente não comprou uma bicicleta.</span><span class="sxs-lookup"><span data-stu-id="38314-125">The value `1` indicates that the customer previously purchased a bike; the value **0** indicates that the customer has not purchased a bike.</span></span> <span data-ttu-id="38314-126">Quanto mais escuro for o sombreamento do nó, maior será a porcentagem de casos desse nó com o valor de destino.</span><span class="sxs-lookup"><span data-stu-id="38314-126">The darker the shading of the node, the higher the percentage of cases in the node that have the target value.</span></span>  
  
5.  <span data-ttu-id="38314-127">Coloque o cursor sobre o nó rotulado como **tudo**.</span><span class="sxs-lookup"><span data-stu-id="38314-127">Place your cursor over the node labeled **All**.</span></span> <span data-ttu-id="38314-128">Uma dica de ferramenta será exibida com as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="38314-128">An tooltip will display the following information:</span></span>  
  
    -   <span data-ttu-id="38314-129">Número total de casos</span><span class="sxs-lookup"><span data-stu-id="38314-129">Total number of cases</span></span>  
  
    -   <span data-ttu-id="38314-130">Número de casos de pessoas que não compram bicicleta</span><span class="sxs-lookup"><span data-stu-id="38314-130">Number of non bike buyer cases</span></span>  
  
    -   <span data-ttu-id="38314-131">Número de casos de compradores de bicicleta</span><span class="sxs-lookup"><span data-stu-id="38314-131">Number of bike buyer cases</span></span>  
  
    -   <span data-ttu-id="38314-132">Número de casos com valores ausentes para [Comprador de Bicicleta]</span><span class="sxs-lookup"><span data-stu-id="38314-132">Number of cases with missing values for [Bike Buyer]</span></span>  
  
     <span data-ttu-id="38314-133">Como alternativa, coloque o seu cursor sobre qualquer nó da árvore para ver a condição exigida para alcançar aquele nó a partir do nó anterior.</span><span class="sxs-lookup"><span data-stu-id="38314-133">Alternately, place your cursor over any node in the tree to see the condition that is required to reach that node from the node that comes before it.</span></span> <span data-ttu-id="38314-134">Você também pode exibir essas mesmas informações na **legenda de mineração**.</span><span class="sxs-lookup"><span data-stu-id="38314-134">You can also view this same information in the **Mining Legend**.</span></span>  
  
6.  <span data-ttu-id="38314-135">Clique no nó para **idade >= 34 e < 41**.</span><span class="sxs-lookup"><span data-stu-id="38314-135">Click on the node for **Age >=34 and < 41**.</span></span> <span data-ttu-id="38314-136">O histograma é exibido como uma barra horizontal final no nó e representa a distribuição de clientes nesse intervalo de idade que compraram (rosa) e que não compraram (azul) uma bicicleta anteriormente.</span><span class="sxs-lookup"><span data-stu-id="38314-136">The histogram is displayed as a thin horizontal bar across the node and represents the distribution of customers in this age range who previously did (pink) and did not (blue) purchase a bike.</span></span> <span data-ttu-id="38314-137">O Visualizador nos mostra que os clientes entre os 34 e os 40 anos com um ou nenhum carro têm probabilidade de comprar uma bicicleta.</span><span class="sxs-lookup"><span data-stu-id="38314-137">The Viewer shows us that customers between the ages of 34 and 40 with one or no cars are likely to purchase a bike.</span></span> <span data-ttu-id="38314-138">Levando isso um pouco mais adiante, descobrimos que a probabilidade de compra de uma bicicleta aumenta caso o cliente tenha realmente entre 38 e 40 anos.</span><span class="sxs-lookup"><span data-stu-id="38314-138">Taking it one step further, we find that the likelihood to purchase a bike increases if the customer is actually age 38 to 40.</span></span>  
  
 <span data-ttu-id="38314-139">Como você habilitou o detalhamento quando criou a estrutura e o modelo, poderá recuperar informações detalhadas dos casos de modelo e da estrutura de mineração, incluindo as colunas não incluídas no modelo de mineração (por exemplo, emailAddress, FirstName).</span><span class="sxs-lookup"><span data-stu-id="38314-139">Because you enabled drillthrough when you created the structure and model, you can retrieve detailed information from the model cases and mining structure, including those columns that were not included in the mining model (e.g., emailAddress, FirstName).</span></span>  
  
 <span data-ttu-id="38314-140">Para obter mais informações, consulte [Consultas de detalhamento &#40;Mineração de dados&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="38314-140">For more information, see [Drillthrough Queries &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md).</span></span>  
  
#### <a name="to-drill-through-to-case-data"></a><span data-ttu-id="38314-141">Para detalhar os dados de caso</span><span class="sxs-lookup"><span data-stu-id="38314-141">To drill through to case data</span></span>  
  
1.  <span data-ttu-id="38314-142">Clique com o botão direito do mouse em um nó e selecione **detalhar** **apenas colunas de modelo**.</span><span class="sxs-lookup"><span data-stu-id="38314-142">Right-click a node, and select **Drill Through** then **Model Columns Only**.</span></span>  
  
     <span data-ttu-id="38314-143">Os detalhes para cada caso de treinamento são exibidos em formato de planilha.</span><span class="sxs-lookup"><span data-stu-id="38314-143">The details for each training case are displayed in spreadsheet format.</span></span> <span data-ttu-id="38314-144">Esses detalhes vêm da exibição vTargetMail, selecionada como a tabela de caso durante a criação da estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="38314-144">These details come from the vTargetMail view that you selected as the case table when building the mining structure.</span></span>  
  
2.  <span data-ttu-id="38314-145">Clique com o botão direito do mouse em um nó e selecione **detalhar** as **colunas modelo e estrutura**.</span><span class="sxs-lookup"><span data-stu-id="38314-145">Right-click a node, and select **Drill Through** then **Model and Structure Columns**.</span></span>  
  
     <span data-ttu-id="38314-146">A mesma planilha será exibida com as colunas da estrutura anexadas no final.</span><span class="sxs-lookup"><span data-stu-id="38314-146">The same spreadsheet displays with the structure columns appended to the end.</span></span>  
  
  
###  <a name="dependency-network-tab"></a><a name="Dependency_Network_Tab"></a><span data-ttu-id="38314-147">Guia rede de dependências</span><span class="sxs-lookup"><span data-stu-id="38314-147">Dependency Network Tab</span></span>  
 <span data-ttu-id="38314-148">A guia **rede de dependências** exibe as relações entre os atributos que contribuem para a capacidade preditiva do modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="38314-148">The **Dependency Network** tab displays the relationships between the attributes that contribute to the predictive ability of the mining model.</span></span> <span data-ttu-id="38314-149">O visualizador Rede de Dependências reforça as nossas descobertas de que Idade e Região são fatores importantes na previsão de compra de bicicletas.</span><span class="sxs-lookup"><span data-stu-id="38314-149">The Dependency Network viewer reinforces our findings that Age and Region are important factors in predicting bike buying.</span></span>  
  
##### <a name="to-explore-the-model-in-the-dependency-network-tab"></a><span data-ttu-id="38314-150">Para explorar o modelo na guia Rede de Dependências</span><span class="sxs-lookup"><span data-stu-id="38314-150">To explore the model in the Dependency Network tab</span></span>  
  
1.  <span data-ttu-id="38314-151">Clique no `Bike Buyer` nó para identificar suas dependências.</span><span class="sxs-lookup"><span data-stu-id="38314-151">Click the `Bike Buyer` node to identify its dependencies.</span></span>  
  
     <span data-ttu-id="38314-152">O nó central da rede de dependências, `Bike Buyer` , representa o atributo previsível no modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="38314-152">The center node for the dependency network, `Bike Buyer`, represents the predictable attribute in the mining model.</span></span> <span data-ttu-id="38314-153">O gráfico destaca todos os nós conectados que têm um efeito sobre o atributo previsível.</span><span class="sxs-lookup"><span data-stu-id="38314-153">The graph highlights any connected nodes that have an effect on the predictable attribute.</span></span>  
  
2.  <span data-ttu-id="38314-154">Ajuste o controle deslizante **todos os links** para identificar o atributo mais influente.</span><span class="sxs-lookup"><span data-stu-id="38314-154">Adjust the **All Links** slider to identify the most influential attribute.</span></span>  
  
     <span data-ttu-id="38314-155">À medida que você arrasta o controle deslizante, os atributos que têm apenas um efeito fraco na coluna [comprador de bicicletas] são removidos do grafo.</span><span class="sxs-lookup"><span data-stu-id="38314-155">As you drag down the slider, attributes that have only a weak effect on the [Bike Buyer] column are removed from the graph.</span></span> <span data-ttu-id="38314-156">Ao ajustar o controle deslizante, você poderá descobrir que Idade e Região são os principais fatores para prever se alguém é um comprador de bicicletas.</span><span class="sxs-lookup"><span data-stu-id="38314-156">By adjusting the slider, you can discover that Age and Region are the greatest factors in predicting whether someone is a bike buyer.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="38314-157">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="38314-157">Related Tasks</span></span>  
 <span data-ttu-id="38314-158">Consulte estes tópicos para explorar os dados usando outros tipos de modelos.</span><span class="sxs-lookup"><span data-stu-id="38314-158">See these topics to explore the data using the other kinds of models.</span></span>  
  
-   [<span data-ttu-id="38314-159">Explorando o modelo de clustering &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="38314-159">Exploring the Clustering Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="38314-160">Explorando o Naive Bayes do modelo de mineração de dados &#40;Basic&#41;</span><span class="sxs-lookup"><span data-stu-id="38314-160">Exploring the Naive Bayes Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-naive-bayes-model-basic-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="38314-161">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="38314-161">Next Task in Lesson</span></span>  
 [<span data-ttu-id="38314-162">Explorando o modelo de clustering &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="38314-162">Exploring the Clustering Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="38314-163">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="38314-163">See Also</span></span>  
 <span data-ttu-id="38314-164">[Tarefas e instruções do Visualizador do modelo de mineração](../../2014/analysis-services/data-mining/mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="38314-164">[Mining Model Viewer Tasks and How-tos](../../2014/analysis-services/data-mining/mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="38314-165">[Guia árvore de decisão &#40;Visualizador do modelo de mineração&#41;](../../2014/analysis-services/decision-tree-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="38314-165">[Decision Tree Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/decision-tree-tab-mining-model-viewer.md) </span></span>  
 <span data-ttu-id="38314-166">[Guia rede de dependências &#40;Visualizador do modelo de mineração&#41;](../../2014/analysis-services/dependency-network-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="38314-166">[Dependency Network Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/dependency-network-tab-mining-model-viewer.md) </span></span>  
 [<span data-ttu-id="38314-167">Procurar um modelo usando a Exibição de Árvore da Microsoft</span><span class="sxs-lookup"><span data-stu-id="38314-167">Browse a Model Using the Microsoft Tree Viewer</span></span>](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-tree-viewer.md)  
  
  
