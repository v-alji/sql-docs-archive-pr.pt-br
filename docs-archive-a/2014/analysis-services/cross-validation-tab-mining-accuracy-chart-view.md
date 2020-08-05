---
title: Guia validação cruzada (exibição de gráfico de precisão de mineração) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.accuracychart.crossvalidation.f1
ms.assetid: bd215a68-1ad7-4046-9c44-ec8e2be13a64
author: minewiskan
ms.author: owend
ms.openlocfilehash: 867bd6d1abffb29ec3eb2a8a78e562e5cbcc5b29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572862"
---
# <a name="cross-validation-tab-mining-accuracy-chart-view"></a><span data-ttu-id="cd1f7-102">Guia da validação cruzada (Exibição do gráfico de precisão de mineração)</span><span class="sxs-lookup"><span data-stu-id="cd1f7-102">Cross-Validation Tab (Mining Accuracy Chart View)</span></span>
  <span data-ttu-id="cd1f7-103">A validação cruzada permite dividir uma estrutura de mineração em seções cruzadas e interativamente treinar e testar modelos com cada seção cruzada.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-103">Cross-validation lets you partition a mining structure into cross-sections and iteratively train and test models against each cross-section.</span></span> <span data-ttu-id="cd1f7-104">Você especifica um número de partições para dividir e colocar os dados; cada partição, por sua vez, é usada como dados de teste, enquanto os dados restantes são usados para treinar o novo modelo.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-104">You specify a number of folds to divide the data into, and each fold is used in turn as the test data, whereas the remaining data is used to train a new model.</span></span> <span data-ttu-id="cd1f7-105">O [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] gera um conjunto de métricas de precisão padrão para cada modelo.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-105">[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] then generates a set of standard accuracy metrics for each model.</span></span> <span data-ttu-id="cd1f7-106">Comparando as métricas dos modelos geradas para cada seção cruzada, é possível obter uma boa noção da confiabilidade do modelo em relação a todo conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-106">By comparing the metrics for the models generated for each cross-section, you can get a good idea of how reliable the mining model is for the whole data set.</span></span>  
  
 <span data-ttu-id="cd1f7-107">Para obter mais informações, consulte [Validação cruzada &#40;Analysis Services – Mineração de dados&#41;](data-mining/cross-validation-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="cd1f7-107">For more information, see [Cross-Validation &#40;Analysis Services - Data Mining&#41;](data-mining/cross-validation-analysis-services-data-mining.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd1f7-108">A validação cruzada não pode ser usada com modelos que foram criados usando os algoritmos [!INCLUDE[msCoName](../includes/msconame-md.md)] MTS ou o [!INCLUDE[msCoName](../includes/msconame-md.md)] MSC.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-108">Cross-validation cannot be used with models that were built by using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series algorithm or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Sequence Clustering algorithm.</span></span> <span data-ttu-id="cd1f7-109">Se você executar o relatório em uma estrutura de mineração que contenha estes tipos de modelos, os modelos não serão incluídos no relatório.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-109">If you run the report on a mining structure that contains these types of models, the models will not be included in the report.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="cd1f7-110">Lista de Tarefas</span><span class="sxs-lookup"><span data-stu-id="cd1f7-110">Task List</span></span>  
  
-   <span data-ttu-id="cd1f7-111">Especificar o número de dobras.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-111">Specify the number of folds.</span></span>  
  
-   <span data-ttu-id="cd1f7-112">Especificar o número máximo de casos para usar para validação cruzada.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-112">Specify the maximum number of cases to use for cross-validation.</span></span>  
  
-   <span data-ttu-id="cd1f7-113">Especificar a coluna previsível.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-113">Specify the predictable column.</span></span>  
  
-   <span data-ttu-id="cd1f7-114">Opcionalmente, especificar um estado previsível.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-114">Optionally, specify a predictable state.</span></span>  
  
-   <span data-ttu-id="cd1f7-115">Opcionalmente, ajuste os parâmetros que controlam como a exatidão da previsão é avaliada.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-115">Optionally, set parameters that control how the accuracy of prediction is assessed.</span></span>  
  
-   <span data-ttu-id="cd1f7-116">Clique em **Obter Resultados** para exibir os resultados de validação cruzada.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-116">Click **Get Results** to display the results of cross-validation.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="cd1f7-117">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="cd1f7-117">UI element list</span></span>  
 <span data-ttu-id="cd1f7-118">**Contagem de dobras**</span><span class="sxs-lookup"><span data-stu-id="cd1f7-118">**Fold Count**</span></span>  
 <span data-ttu-id="cd1f7-119">Especifique o número de dobras ou partições para criar.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-119">Specify the number of folds, or partitions, to create.</span></span> <span data-ttu-id="cd1f7-120">O valor mínimo é 2, significando que a metade do conjunto de dados é usada para testar e metade para treinar.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-120">The minimum value is 2, meaning that half the data set is used for testing and half for training.</span></span>  
  
 <span data-ttu-id="cd1f7-121">O valor máximo é 10 para estruturas de mineração da sessão.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-121">The maximum value is 10 for session mining structures.</span></span>  
  
 <span data-ttu-id="cd1f7-122">O valor máximo será 256 se a estrutura de mineração for armazenada em uma instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cd1f7-122">The maximum value is 256 if the mining structure is stored in an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd1f7-123">À medida que você aumenta o número de partições, o tempo necessário para realizar a validação cruzada também aumenta em n.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-123">As you increase the number of folds, the time that is required to perform cross-validation similarly increases by n.</span></span> <span data-ttu-id="cd1f7-124">Você poderá enfrentar problemas de desempenho se o número de casos for grande e o valor de **Número de Partições** também for alto.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-124">You might experience performance issues if the number of cases is large and the value of **Fold Count** is also large.</span></span>  
  
 <span data-ttu-id="cd1f7-125">**Máx. Casos**</span><span class="sxs-lookup"><span data-stu-id="cd1f7-125">**Max Cases**</span></span>  
 <span data-ttu-id="cd1f7-126">Especificar o número máximo de casos para usar para validação cruzada.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-126">Specify the maximum number of cases to use for cross-validation.</span></span> <span data-ttu-id="cd1f7-127">O número de casos em qualquer dobra em particular é igual ao valor de **Máx. de Casos** dividido pelo valor de **Número de Partições** .</span><span class="sxs-lookup"><span data-stu-id="cd1f7-127">The number of cases in any particular fold is equal to the **Max Cases** value divided by the **Fold Count** value.</span></span>  
  
 <span data-ttu-id="cd1f7-128">Se você usar **0**, todas os casos nos dados de origem serão usados para validação cruzada.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-128">If you use **0**, all cases in the source data are used for cross-validation.</span></span>  
  
 <span data-ttu-id="cd1f7-129">Sem valor padrão.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-129">There is no default value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd1f7-130">Ao aumentar o número de casos, o tempo de processamento também aumentara.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-130">As you increase the number of cases, processing time also increases.</span></span>  
  
 <span data-ttu-id="cd1f7-131">**Atributo de destino**</span><span class="sxs-lookup"><span data-stu-id="cd1f7-131">**Target Attribute**</span></span>  
 <span data-ttu-id="cd1f7-132">Selecione uma coluna da lista de colunas previsíveis encontradas em todos os modelos.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-132">Select a column from the list of predictable columns found in all models.</span></span> <span data-ttu-id="cd1f7-133">Você só pode selecionar uma coluna previsível toda vez que executar a validação cruzada.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-133">You can only select one predictable column every time that you perform cross-validation.</span></span>  
  
 <span data-ttu-id="cd1f7-134">Para testar somente modelos de clustering, selecione **Cluster**.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-134">To test only clustering models, select **Cluster**.</span></span>  
  
 <span data-ttu-id="cd1f7-135">**Estado de destino**</span><span class="sxs-lookup"><span data-stu-id="cd1f7-135">**Target State**</span></span>  
 <span data-ttu-id="cd1f7-136">Digite um valor ou selecione um valor de destino de uma listagem suspensa de valores.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-136">Type a value, or select a target value from a drop-down list of values.</span></span>  
  
 <span data-ttu-id="cd1f7-137">O valor padrão é `null`, indicando que todos os estados serão testados.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-137">The default value is `null`, indicating that all states are to be tested.</span></span>  
  
 <span data-ttu-id="cd1f7-138">Desabilitado para modelos de clustering.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-138">Disabled for clustering models.</span></span>  
  
 <span data-ttu-id="cd1f7-139">**Target\*\*\*\*Limite** de destino  </span><span class="sxs-lookup"><span data-stu-id="cd1f7-139">**Target**  **Threshold**</span></span>  
 <span data-ttu-id="cd1f7-140">Especifique um valor entre 0 e 1 que indica a condição acima do estado previsível em que a probabilidade da previsão é considerada para estar correta.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-140">Specify a value between 0 and 1 that indicates the prediction probability above which a predicted state is considered to be correct.</span></span> <span data-ttu-id="cd1f7-141">O valor pode ser definido em acréscimos de 0,1.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-141">The value can be set in 0.1 increments.</span></span>  
  
 <span data-ttu-id="cd1f7-142">O padrão é `null`, indicando que a previsão mais provável é contada como correta.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-142">The default is `null`, indicating that the most probable prediction is counted as correct.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd1f7-143">Embora você possa definir o valor como 0,0, usando este valor ira aumentar o tempo de processamento sem resultados significativos de rendimento.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-143">Although you can set the value to 0.0, using this value will increase processing time and not yield meaningful results.</span></span>  
  
 <span data-ttu-id="cd1f7-144">**Obter Resultados**</span><span class="sxs-lookup"><span data-stu-id="cd1f7-144">**Get Results**</span></span>  
 <span data-ttu-id="cd1f7-145">Clique para começar a validação cruzada do modelo usando os parâmetros especificados.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-145">Click to begin cross-validation of the model using the specified parameters.</span></span>  
  
 <span data-ttu-id="cd1f7-146">O modelo é dividido no número especificado de dobras e um modelo separado é testado para cada dobra.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-146">The model is partitioned into the specified number of folds and a separate model is tested for each fold.</span></span> <span data-ttu-id="cd1f7-147">Portanto, pode levar algum tempo para a validação cruzada retornar os resultados.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-147">Therefore, it might take some time for cross-validation to return the results.</span></span>  
  
 <span data-ttu-id="cd1f7-148">Para obter mais informações sobre como interpretar os resultados do relatório de validação cruzada, consulte [Medidas no relatório de validação cruzada](data-mining/measures-in-the-cross-validation-report.md).</span><span class="sxs-lookup"><span data-stu-id="cd1f7-148">For more information about how to interpret the results of the cross-validation report, see [Measures in the Cross-Validation Report](data-mining/measures-in-the-cross-validation-report.md).</span></span>  
  
## <a name="setting-the-accuracy-threshold"></a><span data-ttu-id="cd1f7-149">Definir o limite de precisão</span><span class="sxs-lookup"><span data-stu-id="cd1f7-149">Setting the Accuracy Threshold</span></span>  
 <span data-ttu-id="cd1f7-150">Você pode controlar o padrão para medir a precisão da previsão definindo um valor para **Limite** **de Destino**.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-150">You can control the standard for measuring prediction accuracy by setting a value for **Target** **Threshold**.</span></span> <span data-ttu-id="cd1f7-151">Um limite representa um tipo de barra de precisão.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-151">A threshold represents a kind of accuracy bar.</span></span> <span data-ttu-id="cd1f7-152">Para cada previsão é atribuída uma probabilidade de que o valor previsto está correto.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-152">Each prediction is assigned a probability that the predicted value is correct.</span></span> <span data-ttu-id="cd1f7-153">Portanto, ao definir o valor **Limite** **de Destino** próximo de 1, você está requerendo que a probabilidade de qualquer predição em particular seja razoavelmente alta para ser considerada como uma boa previsão.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-153">Therefore, if you set the **Target** **Threshold** value closer to 1, you are requiring that the probability for any particular prediction to be fairly high to be counted as a good prediction.</span></span> <span data-ttu-id="cd1f7-154">Por outro lado, se você definir o **Limite** **de Destino** próximo de 0, mesmo as previsões com baixos valores de probabilidade serão contadas como “boas”.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-154">Conversely, if you set **Target** **Threshold** closer to 0, even predictions with lower probability values are counted as "good" predictions.</span></span>  
  
 <span data-ttu-id="cd1f7-155">Não existe um valor de limite recomendado porque a probabilidade de qualquer previsão depende da quantidade de dados e do tipo de previsão que você esta fazendo.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-155">There is no recommended threshold value because the probability of any prediction depends on the amount of data and the type of prediction you are making.</span></span> <span data-ttu-id="cd1f7-156">Você deve analisar algumas previsões a níveis de probabilidades diferentes para determinar uma barra de precisão apropriada para seus dados.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-156">You should review some predictions at different probability levels to determine an appropriate accuracy bar for your data.</span></span> <span data-ttu-id="cd1f7-157">É importante que se faça isto, porque o valor que você define para o **Limite** **de Destino** afeta a precisão medida do modelo.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-157">It is important that you do this, because the value that you set for **Target** **Threshold** affects the measured accuracy of the model.</span></span>  
  
 <span data-ttu-id="cd1f7-158">Por exemplo, suponha que três previsões são feitas para um determinado estado de destino, e as probabilidades de cada previsão são 0,05, 0,15 e 0,8.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-158">For example, suppose three predictions are made for a particular target state, and the probabilities of each prediction are 0.05, 0.15, and 0.8.</span></span> <span data-ttu-id="cd1f7-159">Se você definir o limite de 0,5, só uma previsão será contada como estando correta.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-159">If you set the threshold to 0.5, only one prediction is counted as being correct.</span></span> <span data-ttu-id="cd1f7-160">Se você definir o **Limite** **do Destino** como 0,10, serão contadas duas previsões como estando corretas.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-160">If you set **Target** **Threshold** to 0.10, two predictions are counted as being correct.</span></span>  
  
 <span data-ttu-id="cd1f7-161">Quando o **limite** de **destino** é definido como `null` , que é o valor padrão, a previsão mais provável para cada caso é contada como correta.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-161">When **Target** **Threshold** is set to `null`, which is the default value, the most probable prediction for each case is counted as correct.</span></span> <span data-ttu-id="cd1f7-162">No exemplo a pouco citado, 0,05, 0,15 e 0,8 são as probabilidades para previsões em três casos diferentes.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-162">In the example just cited, 0.05, 0.15, and 0.8 are the probabilities for predictions in three different cases.</span></span> <span data-ttu-id="cd1f7-163">Embora as probabilidades sejam muito diferentes, cada previsão será contada como correta, porque cada caso gera somente uma previsão e essas são as melhores previsões para esses casos.</span><span class="sxs-lookup"><span data-stu-id="cd1f7-163">Although the probabilities are very different, each prediction would be counted as correct, because each case generates only one prediction and these are the best predictions for these cases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd1f7-164">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cd1f7-164">See Also</span></span>  
 <span data-ttu-id="cd1f7-165">[Teste e validação &#40;mineração de dados&#41;](data-mining/testing-and-validation-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="cd1f7-165">[Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md) </span></span>  
 <span data-ttu-id="cd1f7-166">[&#40;de validação cruzada Analysis Services&#41;de mineração de dados](data-mining/cross-validation-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="cd1f7-166">[Cross-Validation &#40;Analysis Services - Data Mining&#41;](data-mining/cross-validation-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="cd1f7-167">[Medidas no relatório de validação cruzada](data-mining/measures-in-the-cross-validation-report.md) </span><span class="sxs-lookup"><span data-stu-id="cd1f7-167">[Measures in the Cross-Validation Report](data-mining/measures-in-the-cross-validation-report.md) </span></span>  
 [<span data-ttu-id="cd1f7-168">Procedimentos armazenados da mineração de dados &#40;Analysis Services – Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="cd1f7-168">Data Mining Stored Procedures &#40;Analysis Services - Data Mining&#41;</span></span>](/sql/analysis-services/data-mining/data-mining-stored-procedures-analysis-services-data-mining)  
  
  
