---
title: Testando um modelo filtrado (tutorial de mineração de dados básico) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f0d74f8c-600d-4df5-a742-695e6947a071
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a97b5ca3523d1fc73405baba52b179a9bef04767
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568932"
---
# <a name="testing-a-filtered-model-basic-data-mining-tutorial"></a><span data-ttu-id="939a8-102">Testando um modelo filtrado (Tutorial de mineração de dados básico)</span><span class="sxs-lookup"><span data-stu-id="939a8-102">Testing a Filtered Model (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="939a8-103">Agora que você determinou que o `TM_Decision_Tree` modelo é o mais preciso, você personalizará o modelo para se adequar melhor às necessidades da [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] campanha de mala direta.</span><span class="sxs-lookup"><span data-stu-id="939a8-103">Now that you have determined that the `TM_Decision_Tree` model is the most accurate, you will customize the model to better suit the needs of the [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] targeted mailing campaign.</span></span> <span data-ttu-id="939a8-104">Especificamente, o departamento de marketing gostaria de saber se existe alguma diferença entre os clientes masculino e feminino.</span><span class="sxs-lookup"><span data-stu-id="939a8-104">Specifically, the Marketing department would like to know if there are any differences between male and female customers.</span></span> <span data-ttu-id="939a8-105">As informações podem ajudá-los a decidir que revistas serão usadas para a propaganda e que produtos deverão ser incluídos em suas malas diretas.</span><span class="sxs-lookup"><span data-stu-id="939a8-105">The information could help them decide which magazines to use for advertising and which products to feature in their mailings.</span></span>  
  
## <a name="using-filters"></a><span data-ttu-id="939a8-106">Usando filtros</span><span class="sxs-lookup"><span data-stu-id="939a8-106">Using Filters</span></span>  
 <span data-ttu-id="939a8-107">A filtragem permite que você crie com facilidade modelos criados com base em subconjuntos de seus dados.</span><span class="sxs-lookup"><span data-stu-id="939a8-107">Filtering enables you to easily create models built on subsets of your data.</span></span> <span data-ttu-id="939a8-108">O filtro só é aplicado ao modelo e não altera a fonte de dados subjacente.</span><span class="sxs-lookup"><span data-stu-id="939a8-108">The filter is applied only to the model and does not change the underlying data source.</span></span>  
  
 <span data-ttu-id="939a8-109">Nesta lição, você criará um modelo filtrado por gênero, para prever as características que mais influenciam no comportamento de compra em homens e mulheres.</span><span class="sxs-lookup"><span data-stu-id="939a8-109">In this lesson, you will create a model that is filtered on gender, to predict the characteristics that most influence buying behavior in males and female.</span></span>  
  
 <span data-ttu-id="939a8-110">Primeiro, você fará uma cópia do `TM_Decision_Tree` modelo.</span><span class="sxs-lookup"><span data-stu-id="939a8-110">First you will make a copy of the `TM_Decision_Tree` model.</span></span>  
  
#### <a name="to-copy-the-decision-tree-model"></a><span data-ttu-id="939a8-111">Para copiar o modelo de árvore de decisão</span><span class="sxs-lookup"><span data-stu-id="939a8-111">To copy the Decision Tree Model</span></span>  
  
1.  <span data-ttu-id="939a8-112">Em [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , em Gerenciador de soluções, selecione **BasicDataMining**.</span><span class="sxs-lookup"><span data-stu-id="939a8-112">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in Solution Explorer, select **BasicDataMining**.</span></span>  
  
2.  <span data-ttu-id="939a8-113">Clique na guia **Modelos de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="939a8-113">Click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="939a8-114">Clique com o botão direito do mouse no `TM_Decision_Tree` modelo e selecione **novo modelo de mineração.**</span><span class="sxs-lookup"><span data-stu-id="939a8-114">Right click the `TM_Decision_Tree` model, and select **New Mining Model.**</span></span>  
  
4.  <span data-ttu-id="939a8-115">No campo **nome do modelo** , digite `TM_Decision_Tree_Male` .</span><span class="sxs-lookup"><span data-stu-id="939a8-115">In the **Model name** field, type `TM_Decision_Tree_Male`.</span></span>  
  
5.  <span data-ttu-id="939a8-116">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="939a8-116">Click **OK**.</span></span>  
  
 <span data-ttu-id="939a8-117">Em seguida, crie um filtro para selecionar clientes para o modelo baseado em gênero.</span><span class="sxs-lookup"><span data-stu-id="939a8-117">Next, create a filter to select customers for the model based on their gender.</span></span>  
  
#### <a name="to-create-a-case-filter-on-a-mining-model"></a><span data-ttu-id="939a8-118">Para criar um filtro de caso em um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="939a8-118">To create a case filter on a mining model</span></span>  
  
1.  <span data-ttu-id="939a8-119">Clique com o botão direito do mouse no `TM_Decision_Tree_Male` modelo de mineração para abrir o menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="939a8-119">Right-click the `TM_Decision_Tree_Male` mining model to open the shortcut menu.</span></span>  
  
     <span data-ttu-id="939a8-120">-- ou --</span><span class="sxs-lookup"><span data-stu-id="939a8-120">-- or --</span></span>  
  
     <span data-ttu-id="939a8-121">Selecione o modelo.</span><span class="sxs-lookup"><span data-stu-id="939a8-121">Select the model.</span></span> <span data-ttu-id="939a8-122">No menu **Modelo de Mineração** , selecione **Definir Filtro de Modelos**.</span><span class="sxs-lookup"><span data-stu-id="939a8-122">On the **Mining Model** menu, select **Set Model Filter**.</span></span>  
  
2.  <span data-ttu-id="939a8-123">Na caixa de diálogo **Filtro de Modelos** , clique na linha superior da grade, na caixa de texto **Coluna da Estrutura de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="939a8-123">In the **Model Filter** dialog box, click the top row in the grid, in the **Mining Structure Column** text box.</span></span>  
  
     <span data-ttu-id="939a8-124">A lista suspensa só exibe os nomes das colunas dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="939a8-124">The drop-down list displays only the names of the columns in that table.</span></span>  
  
3.  <span data-ttu-id="939a8-125">Na caixa de texto coluna da estrutura de mineração, selecione **sexo**.</span><span class="sxs-lookup"><span data-stu-id="939a8-125">In the Mining Structure Column text box, select **Gender**.</span></span>  
  
     <span data-ttu-id="939a8-126">O ícone no lado esquerdo da caixa de texto muda para indicar que o item selecionado é uma tabela ou uma coluna.</span><span class="sxs-lookup"><span data-stu-id="939a8-126">The icon at the left side of the text box changes to indicate that the selected item is a table or a column.</span></span>  
  
4.  <span data-ttu-id="939a8-127">Clique na caixa de texto **operador** e selecione o operador igual (=) na lista.</span><span class="sxs-lookup"><span data-stu-id="939a8-127">Click the **Operator** text box and select the equal (=) operator from the list.</span></span>  
  
5.  <span data-ttu-id="939a8-128">Clique na caixa de texto **valor** e digite **M**.</span><span class="sxs-lookup"><span data-stu-id="939a8-128">Click the **Value** text box, and type **M**.</span></span>  
  
6.  <span data-ttu-id="939a8-129">Na grade, clique na linha seguinte.</span><span class="sxs-lookup"><span data-stu-id="939a8-129">Click the next row in the grid.</span></span>  
  
7.  <span data-ttu-id="939a8-130">Clique em **OK** para fechar a caixa de diálogo **filtro de modelo** .</span><span class="sxs-lookup"><span data-stu-id="939a8-130">Click **OK** to close the **Model Filter** dialog box.</span></span>  
  
     <span data-ttu-id="939a8-131">O filtro é exibido na janela **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="939a8-131">The filter displays in the **Properties** window.</span></span> <span data-ttu-id="939a8-132">Como alternativa, você pode iniciar a caixa de diálogo **filtro de modelo** na janela **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="939a8-132">Alternately, you can launch the **Model Filter** dialog from the **Properties** window.</span></span>  
  
8.  <span data-ttu-id="939a8-133">Repita as etapas acima, mas desta vez Nomeie o modelo `TM_Decision_Tree_Female` e digite **F** na caixa de texto **valor** .</span><span class="sxs-lookup"><span data-stu-id="939a8-133">Repeat the above steps, but this time name the model `TM_Decision_Tree_Female` and type **F** in the **Value** text box.</span></span>  
  
## <a name="process-the-filtered-models"></a><span data-ttu-id="939a8-134">Processar os modelos filtrados</span><span class="sxs-lookup"><span data-stu-id="939a8-134">Process the Filtered Models</span></span>  
 <span data-ttu-id="939a8-135">Os modelos só poderão ser usados depois de serem implantados e processados.</span><span class="sxs-lookup"><span data-stu-id="939a8-135">Models cannot be used until they have been deployed and processed.</span></span> <span data-ttu-id="939a8-136">Para obter mais informações sobre modelos de processamento, consulte [processando modelos na estrutura de mala direta direcionada &#40;tutorial de mineração de dados básico&#41;](../../2014/tutorials/processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="939a8-136">For more information on processing models, see [Processing Models in the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;](../../2014/tutorials/processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial.md).</span></span>  
  
#### <a name="to-process-the-filtered-model"></a><span data-ttu-id="939a8-137">Para processar o modelo filtrado</span><span class="sxs-lookup"><span data-stu-id="939a8-137">To process the filtered model</span></span>  
  
1.  <span data-ttu-id="939a8-138">Clique com o botão direito do mouse no `TM_Decision_Tree_Male` modelo e selecione **processar estrutura de mineração e todos os modelos**s</span><span class="sxs-lookup"><span data-stu-id="939a8-138">Right-click the `TM_Decision_Tree_Male` model and select **Process Mining Structure and all Model**s</span></span>  
  
2.  <span data-ttu-id="939a8-139">Clique em **executar** para processar os novos modelos.</span><span class="sxs-lookup"><span data-stu-id="939a8-139">Click **Run** to process the new models.</span></span>  
  
3.  <span data-ttu-id="939a8-140">Após a conclusão do processamento, clique em **fechar** em ambas as janelas de processamento.</span><span class="sxs-lookup"><span data-stu-id="939a8-140">After processing is complete, click **Close** on both processing windows.</span></span>  
  
     <span data-ttu-id="939a8-141">Agora você tem dois novos modelos exibidos na guia **modelos de mineração** .</span><span class="sxs-lookup"><span data-stu-id="939a8-141">You now have two new models displayed in the **Mining Models** tab.</span></span>  
  
## <a name="evaluate-the-results"></a><span data-ttu-id="939a8-142">Avaliar os resultados.</span><span class="sxs-lookup"><span data-stu-id="939a8-142">Evaluate the Results</span></span>  
 <span data-ttu-id="939a8-143">Examine os resultados e avalie a precisão dos modelos filtrados da mesma forma como foi feito nos três modelos anteriores.</span><span class="sxs-lookup"><span data-stu-id="939a8-143">View the results and assess the accuracy of the filtered models in much the same way as you did for the previous three models.</span></span> <span data-ttu-id="939a8-144">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="939a8-144">For more information, see:</span></span>  
  
 [<span data-ttu-id="939a8-145">Exploração do modelo de árvore de decisão &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="939a8-145">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="939a8-146">Testando a precisão com gráficos de comparação de precisão &#40;Tutorial de mineração de dados básica&#41;</span><span class="sxs-lookup"><span data-stu-id="939a8-146">Testing Accuracy with Lift Charts &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-accuracy-with-lift-charts-basic-data-mining-tutorial.md)  
  
#### <a name="to-explore-the-filtered-models"></a><span data-ttu-id="939a8-147">Para explorar os modelos filtrados</span><span class="sxs-lookup"><span data-stu-id="939a8-147">To explore the filtered models</span></span>  
  
1.  <span data-ttu-id="939a8-148">Selecione a guia **Visualizador do modelo de mineração** no designer de mineração de **dados**.</span><span class="sxs-lookup"><span data-stu-id="939a8-148">Select the **Mining Model Viewer** tab in **Data Mining Designer**.</span></span>  
  
2.  <span data-ttu-id="939a8-149">Na caixa modelo de mineração, selecione `TM_Decision_Tree_Male` .</span><span class="sxs-lookup"><span data-stu-id="939a8-149">In the Mining Model box, select `TM_Decision_Tree_Male`.</span></span>  
  
3.  <span data-ttu-id="939a8-150">Deslizar **nível de apresentação** para `3` .</span><span class="sxs-lookup"><span data-stu-id="939a8-150">Slide **Show Level** to `3`.</span></span>  
  
4.  <span data-ttu-id="939a8-151">Altere o valor de **plano de fundo** para `1` .</span><span class="sxs-lookup"><span data-stu-id="939a8-151">Change the **Background** value to `1`.</span></span>  
  
5.  <span data-ttu-id="939a8-152">Coloque o cursor sobre o nó rotulado **tudo** para ver o número de compradores de bicicletas versus compradores sem bicicletas.</span><span class="sxs-lookup"><span data-stu-id="939a8-152">Place your cursor over the node labeled **All** to see the number of bike buyers versus non-bike buyers.</span></span>  
  
6.  <span data-ttu-id="939a8-153">Repita as etapas 1-5 para `TM_Decision_Tree_Female` .</span><span class="sxs-lookup"><span data-stu-id="939a8-153">Repeat steps 1 - 5 for `TM_Decision_Tree_Female`.</span></span>  
  
7.  <span data-ttu-id="939a8-154">Explore os resultados para o `TM_Decision_Tree` e os modelos filtrados para gênero.</span><span class="sxs-lookup"><span data-stu-id="939a8-154">Explore the results for the `TM_Decision_Tree` and the models filtered for gender.</span></span> <span data-ttu-id="939a8-155">Em comparação a todos os compradores de bicicleta, os compradores de bicicleta homens e mulheres compartilham as mesmas características dos compradores de bicicleta não filtrados, mas todos os três também possuem diferenças interessantes.</span><span class="sxs-lookup"><span data-stu-id="939a8-155">Compared to all bike buyers, male and female bike buyers share some of the same characteristics as the unfiltered bike buyers but all three have interesting differences as well.</span></span> <span data-ttu-id="939a8-156">Essas são informações úteis que [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] podem ser usadas para desenvolver sua campanha de marketing.</span><span class="sxs-lookup"><span data-stu-id="939a8-156">This is useful information that [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] can use to develop their marketing campaign.</span></span>  
  
#### <a name="to-test-the-lift-of-the-filtered-models"></a><span data-ttu-id="939a8-157">Para testar a comparação de precisão dos modelos filtrados</span><span class="sxs-lookup"><span data-stu-id="939a8-157">To test the lift of the filtered models</span></span>  
  
1.  <span data-ttu-id="939a8-158">Alterne para a guia **gráfico de precisão de mineração** no designer de mineração de dados no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] e selecione a guia **seleção de entrada** .</span><span class="sxs-lookup"><span data-stu-id="939a8-158">Switch to the **Mining Accuracy Chart** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and select the **Input Selection** tab.</span></span>  
  
2.  <span data-ttu-id="939a8-159">Na caixa de grupo **selecionar conjunto de dados a ser usado para o gráfico de precisão** , selecione **usar casos de teste da estrutura de mineração**.</span><span class="sxs-lookup"><span data-stu-id="939a8-159">In the **Select data set to be used for Accuracy Chart** group box, select **Use mining structure test cases**.</span></span>  
  
3.  <span data-ttu-id="939a8-160">Na guia **seleção de entrada** do designer de mineração de dados, em **selecionar colunas do modelo de mineração previsível para mostrar no gráfico**de comparação de precisão, marque a caixa de seleção para **sincronizar colunas de previsão e valores**.</span><span class="sxs-lookup"><span data-stu-id="939a8-160">On the **Input Selection** tab of Data Mining Designer, under **Select predictable mining model columns to show in the lift chart**, select the checkbox for **Synchronize Prediction Columns and Values**.</span></span>  
  
4.  <span data-ttu-id="939a8-161">Na coluna **nome da coluna previsível** , verifique se o **comprador de bicicleta** está selecionado para cada modelo.</span><span class="sxs-lookup"><span data-stu-id="939a8-161">In the **Predictable Column Name** column, verify that **Bike Buyer** is selected for each model.</span></span>  
  
5.  <span data-ttu-id="939a8-162">Na coluna **Mostrar** , selecione cada um dos modelos.</span><span class="sxs-lookup"><span data-stu-id="939a8-162">In the **Show** column, select each of the models.</span></span>  
  
6.  <span data-ttu-id="939a8-163">Na coluna **valor da previsão** , selecione `1` .</span><span class="sxs-lookup"><span data-stu-id="939a8-163">In the **Predict Value** column, select `1`.</span></span>  
  
7.  <span data-ttu-id="939a8-164">Selecione a guia gráfico de comparação de **precisão** para exibir o gráfico de comparação de precisão.</span><span class="sxs-lookup"><span data-stu-id="939a8-164">Select the **Lift Chart** tab to display the lift chart.</span></span>  
  
     <span data-ttu-id="939a8-165">Você observará que todos os três modelos de Árvore de Decisão oferecem uma precisão significativa comparado com o modelo de previsão aleatório, além de superarem os modelos Clustering e Naive Bayes.</span><span class="sxs-lookup"><span data-stu-id="939a8-165">You will now notice that all three Decision Tree models provide significant lift compared to the random guess model, and also outperform the Clustering and Naive-Bayes models.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="939a8-166">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="939a8-166">Related Tasks</span></span>  
 <span data-ttu-id="939a8-167">Para obter mais informações sobre filtros, consulte [filtros para modelos de mineração &#40;&#41;de mineração de dados Analysis Services ](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="939a8-167">For more information on filters, see [Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="939a8-168">Para obter um exemplo de como aplicar filtros a tabelas aninhadas, consulte [tutorial de mineração de dados intermediário &#40;Analysis Services&#41;de mineração de dados ](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="939a8-168">For an example of how to apply filters to nested tables, see [Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="939a8-169">Tarefa anterior da lição</span><span class="sxs-lookup"><span data-stu-id="939a8-169">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="939a8-170">Testando a precisão com gráficos de comparação de precisão &#40;Tutorial de mineração de dados básica&#41;</span><span class="sxs-lookup"><span data-stu-id="939a8-170">Testing Accuracy with Lift Charts &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-accuracy-with-lift-charts-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="939a8-171">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="939a8-171">Next Lesson</span></span>  
 [<span data-ttu-id="939a8-172">Lição 6: Criando e trabalhando com previsões &#40;Tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="939a8-172">Lesson 6: Creating and Working with Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-6-creating-and-working-with-predictions-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="939a8-173">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="939a8-173">See Also</span></span>  
 <span data-ttu-id="939a8-174">[Tutorial de mineração de dados intermediário &#40;Analysis Services de mineração de dados&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="939a8-174">[Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="939a8-175">[Tarefas e instruções do modelo de mineração](../../2014/analysis-services/data-mining/mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="939a8-175">[Mining Model Tasks and How-tos](../../2014/analysis-services/data-mining/mining-model-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="939a8-176">[Excluir um filtro de um modelo de mineração](../../2014/analysis-services/data-mining/delete-a-filter-from-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="939a8-176">[Delete a Filter from a Mining Model](../../2014/analysis-services/data-mining/delete-a-filter-from-a-mining-model.md) </span></span>  
 [<span data-ttu-id="939a8-177">Filtros para modelos de mineração &#40;Analysis Services – Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="939a8-177">Filters for Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md)  
  
  
