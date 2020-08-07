---
title: Testando a exatidão com gráficos de comparação de precisão (tutorial de mineração de dados básico) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 822d414b-4a39-473f-80c3-53476e30655a
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 7a3dcdd1d1b78911f5ffd37a383532abdd4814c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681934"
---
# <a name="testing-accuracy-with-lift-charts-basic-data-mining-tutorial"></a><span data-ttu-id="cc44b-102">Testando a precisão com gráficos de comparação de precisão (Tutorial de mineração de dados básico)</span><span class="sxs-lookup"><span data-stu-id="cc44b-102">Testing Accuracy with Lift Charts (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="cc44b-103">Na guia **gráfico de precisão de mineração** do designer de mineração de dados, você pode calcular como cada um de seus modelos faz previsões e comparar os resultados de cada modelo diretamente com os resultados dos outros modelos.</span><span class="sxs-lookup"><span data-stu-id="cc44b-103">On the **Mining Accuracy Chart** tab of Data Mining Designer, you can calculate how well each of your models makes predictions, and compare the results of each model directly against the results of the other models.</span></span> <span data-ttu-id="cc44b-104">Esse método de comparação é conhecido como um gráfico de aumento de *precisão*.</span><span class="sxs-lookup"><span data-stu-id="cc44b-104">This method of comparison is referred to as a *lift chart*.</span></span> <span data-ttu-id="cc44b-105">Normalmente, a precisão da previsão de um modelo de mineração é medida pela comparação de precisão ou pela precisão de classificação.</span><span class="sxs-lookup"><span data-stu-id="cc44b-105">Typically, the predictive accuracy of a mining model is measured by either lift or classification accuracy.</span></span> <span data-ttu-id="cc44b-106">Para este tutorial, só usaremos o gráfico de comparação de precisão.</span><span class="sxs-lookup"><span data-stu-id="cc44b-106">For this tutorial we will use the lift chart only.</span></span>  
  
 <span data-ttu-id="cc44b-107">Neste tópico, você executará as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="cc44b-107">In this topic, you will perform the following tasks:</span></span>  
  
-   [<span data-ttu-id="cc44b-108">Escolher os dados de entrada</span><span class="sxs-lookup"><span data-stu-id="cc44b-108">Choose the Input Data</span></span>](#BKMK_InputData)  
  
-   [<span data-ttu-id="cc44b-109">Configurar parâmetros do gráfico de precisão</span><span class="sxs-lookup"><span data-stu-id="cc44b-109">Configure Accuracy Chart Parameters</span></span>](#BKMK_Selecting)  
  
##  <a name="choosing-the-input-data"></a><a name="BKMK_InputData"></a><span data-ttu-id="cc44b-110">Escolhendo os dados de entrada</span><span class="sxs-lookup"><span data-stu-id="cc44b-110">Choosing the Input Data</span></span>  
 <span data-ttu-id="cc44b-111">A primeira etapa para testar a precisão dos modelos de mineração é selecionar a fonte de dados que será usada para teste.</span><span class="sxs-lookup"><span data-stu-id="cc44b-111">The first step in testing the accuracy of your mining models is to select the data source that you will use for testing.</span></span> <span data-ttu-id="cc44b-112">Você testará o desempenho dos modelos com os dados de teste e os usará com dados externos.</span><span class="sxs-lookup"><span data-stu-id="cc44b-112">You will test how well the models perform against your testing data and then you will use them with external data.</span></span>  
  
#### <a name="to-select-the-data-set"></a><span data-ttu-id="cc44b-113">Para selecionar o conjunto de dados</span><span class="sxs-lookup"><span data-stu-id="cc44b-113">To select the data set</span></span>  
  
1.  <span data-ttu-id="cc44b-114">Alterne para a guia **gráfico de precisão de mineração** no designer de mineração de dados no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] e selecione a guia **seleção de entrada** .</span><span class="sxs-lookup"><span data-stu-id="cc44b-114">Switch to the **Mining Accuracy Chart** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and select the **Input Selection** tab.</span></span>  
  
2.  <span data-ttu-id="cc44b-115">Na caixa de grupo **selecionar conjunto de dados a ser usado para o gráfico de precisão** , selecione **usar casos de teste da estrutura de mineração**.</span><span class="sxs-lookup"><span data-stu-id="cc44b-115">In the **Select data set to be used for Accuracy Chart** group box, select **Use mining structure test cases**.</span></span> <span data-ttu-id="cc44b-116">Esses são os dados de teste que você reservou quando criou a estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="cc44b-116">This is the testing data that you set aside when you created the mining structure.</span></span>  
  
     <span data-ttu-id="cc44b-117">Para obter mais informações sobre as outras opções, consulte [escolher um tipo de gráfico de precisão e definir opções de gráfico](../../2014/analysis-services/data-mining/choose-an-accuracy-chart-type-and-set-chart-options.md).</span><span class="sxs-lookup"><span data-stu-id="cc44b-117">For more information on the other options, see [Choose an Accuracy Chart Type and Set Chart Options](../../2014/analysis-services/data-mining/choose-an-accuracy-chart-type-and-set-chart-options.md).</span></span>  
  
##  <a name="setting-accuracy-chart-parameters"></a><a name="BKMK_Selecting"></a><span data-ttu-id="cc44b-118">Definindo parâmetros de gráfico de precisão</span><span class="sxs-lookup"><span data-stu-id="cc44b-118">Setting Accuracy Chart Parameters</span></span>  
 <span data-ttu-id="cc44b-119">Para criar um gráfico de precisão, você deve definir três parâmetros:</span><span class="sxs-lookup"><span data-stu-id="cc44b-119">To create an accuracy chart, you must define three things:</span></span>  
  
-   <span data-ttu-id="cc44b-120">Que modelos você deve incluir no gráfico de precisão?</span><span class="sxs-lookup"><span data-stu-id="cc44b-120">Which models should you include in the accuracy chart?</span></span>  
  
-   <span data-ttu-id="cc44b-121">Que atributo previsível você deseja medir?</span><span class="sxs-lookup"><span data-stu-id="cc44b-121">Which predictable attribute do you want to measure?</span></span> <span data-ttu-id="cc44b-122">Alguns modelos podem ter vários destinos, mas cada gráfico pode medir apenas um resultado de cada vez.</span><span class="sxs-lookup"><span data-stu-id="cc44b-122">Some models might have multiple targets, but each chart can measure only one outcome at a time.</span></span>  
  
     <span data-ttu-id="cc44b-123">Para usar uma coluna como o **nome de coluna previsível** em um gráfico de precisão, as colunas devem ter o tipo de uso de `Predict` ou `Predict Only` .</span><span class="sxs-lookup"><span data-stu-id="cc44b-123">To use a column as the **Predictable Column Name** in an accuracy chart, the columns must have the usage type of `Predict` or `Predict Only`.</span></span> <span data-ttu-id="cc44b-124">Além disso, o tipo de conteúdo da coluna de destino deve ser `Discrete` ou `Discretized`.</span><span class="sxs-lookup"><span data-stu-id="cc44b-124">Also, the content type of the target column must be either `Discrete` or `Discretized`.</span></span> <span data-ttu-id="cc44b-125">Em outras palavras, você não pode medir a precisão em relação a resultados numéricos contínuos que usem o gráfico de comparação de precisão.</span><span class="sxs-lookup"><span data-stu-id="cc44b-125">In other words, you cannot measure accuracy against continuous numeric outputs using the lift chart.</span></span>  
  
-   <span data-ttu-id="cc44b-126">Deseja medir a precisão geral do modelo ou sua precisão na previsão de um valor específico (como [comprador de bicicletas] = ' Sim ')</span><span class="sxs-lookup"><span data-stu-id="cc44b-126">Do you want to measure the model's general accuracy, or its accuracy  in predicting a particular value (such as [Bike Buyer] = 'Yes')</span></span>  
  
#### <a name="to-generate-the-lift-chart"></a><span data-ttu-id="cc44b-127">Para gerar o gráfico de comparação de precisão</span><span class="sxs-lookup"><span data-stu-id="cc44b-127">To generate the lift chart</span></span>  
  
1.  <span data-ttu-id="cc44b-128">Na guia **seleção de entrada** do designer de mineração de dados, em **selecionar colunas do modelo de mineração previsível para mostrar no gráfico**de comparação de precisão, marque a caixa de seleção para **sincronizar colunas de previsão e valores**.</span><span class="sxs-lookup"><span data-stu-id="cc44b-128">On the **Input Selection** tab of Data Mining Designer, under **Select predictable mining model columns to show in the lift chart**, select the checkbox for **Synchronize Prediction Columns and Values**.</span></span>  
  
2.  <span data-ttu-id="cc44b-129">Na coluna **nome da coluna previsível** , verifique se o **comprador de bicicleta** está selecionado para cada modelo.</span><span class="sxs-lookup"><span data-stu-id="cc44b-129">In the **Predictable Column Name** column, verify that **Bike Buyer** is selected for each model.</span></span>  
  
3.  <span data-ttu-id="cc44b-130">Na coluna **Mostrar** , selecione cada um dos modelos.</span><span class="sxs-lookup"><span data-stu-id="cc44b-130">In the **Show** column, select each of the models.</span></span>  
  
     <span data-ttu-id="cc44b-131">Por padrão, são selecionados todos os modelos na estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="cc44b-131">By default, all the models in the mining structure are selected.</span></span> <span data-ttu-id="cc44b-132">Você pode optar por não incluir um modelo, mas para este tutorial deixe todos os modelos selecionados.</span><span class="sxs-lookup"><span data-stu-id="cc44b-132">You can decide not to include a model, but for this tutorial leave all the models selected.</span></span>  
  
4.  <span data-ttu-id="cc44b-133">Na coluna **valor da previsão** , selecione **1**.</span><span class="sxs-lookup"><span data-stu-id="cc44b-133">In the **Predict Value** column, select **1**.</span></span> <span data-ttu-id="cc44b-134">O mesmo valor é preenchido automaticamente para cada modelo que tenha a mesma coluna previsível.</span><span class="sxs-lookup"><span data-stu-id="cc44b-134">The same value is automatically filled in for each model that has the same predictable column.</span></span>  
  
5.  <span data-ttu-id="cc44b-135">Selecione a guia gráfico de comparação de **precisão** .</span><span class="sxs-lookup"><span data-stu-id="cc44b-135">Select the **Lift Chart** tab.</span></span>  
  
     <span data-ttu-id="cc44b-136">Quando você clicar na guia, uma consulta de previsão será executada para obter as previsões dos dados de teste, e os resultados serão comparados com os valores existentes.</span><span class="sxs-lookup"><span data-stu-id="cc44b-136">When you click the tab, a prediction query is executed to get predictions for the test data, and the results are compared against the known values.</span></span> <span data-ttu-id="cc44b-137">Os resultados serão plotados no gráfico.</span><span class="sxs-lookup"><span data-stu-id="cc44b-137">The results are plotted on the graph.</span></span>  
  
     <span data-ttu-id="cc44b-138">Se você especificou um determinado resultado de destino usando a opção **prever valor** , o gráfico de comparação de precisão plota os resultados de palpites aleatórios e os resultados de um modelo ideal.</span><span class="sxs-lookup"><span data-stu-id="cc44b-138">If you specified a particular target outcome using the **Predict Value** option, the lift chart plots the results of random guesses and the results of an ideal model.</span></span>  
  
    -   <span data-ttu-id="cc44b-139">A linha de estimativa aleatória mostra como a precisão do modelo seria se nenhum dado fosse usado para informar as previsões: ou seja, uma divisão 50-50 entre dois resultados.</span><span class="sxs-lookup"><span data-stu-id="cc44b-139">The random guess line shows how accurate the model would be without using any data to inform its predictions: that is, a 50-50 split between two outcomes.</span></span> <span data-ttu-id="cc44b-140">O gráfico de comparação de precisão ajuda você a visualizar melhor o desempenho do seu modelo em comparação com uma estimativa aleatória.</span><span class="sxs-lookup"><span data-stu-id="cc44b-140">The lift chart helps you visualize how much better your model performs in comparison to a random guess.</span></span>  
  
    -   <span data-ttu-id="cc44b-141">A linha de modelo ideal representa o limite superior de precisão.</span><span class="sxs-lookup"><span data-stu-id="cc44b-141">The ideal model line represents the upper bound of accuracy.</span></span> <span data-ttu-id="cc44b-142">Ela mostra o benefício máximo possível que você poderia obter se seu modelo sempre previsse com precisão.</span><span class="sxs-lookup"><span data-stu-id="cc44b-142">It shows you the maximum possible benefit you could achieve if your model always predicted accurately.</span></span>  
  
     <span data-ttu-id="cc44b-143">Em geral, os modelos de mineração criados ficarão entre esses dois extremos.</span><span class="sxs-lookup"><span data-stu-id="cc44b-143">The mining models you created will usually fall between these two extremes.</span></span> <span data-ttu-id="cc44b-144">Qualquer melhoria da estimativa aleatória é considerada uma *elevação*.</span><span class="sxs-lookup"><span data-stu-id="cc44b-144">Any improvement from the random guess is considered to be *lift*.</span></span>  
  
6.  <span data-ttu-id="cc44b-145">Use a legenda para localizar as linhas coloridas que representam o Modelo Ideal e o Modelo de Previsão Aleatório.</span><span class="sxs-lookup"><span data-stu-id="cc44b-145">Use the legend to locate the colored lines representing the Ideal Model and the Random Guess Model.</span></span>  
  
     <span data-ttu-id="cc44b-146">Você observará que o `TM_Decision_Tree` modelo fornece o maior aumento, o desempenho dos modelos Naive Bayes e clustering.</span><span class="sxs-lookup"><span data-stu-id="cc44b-146">You'll notice that the `TM_Decision_Tree` model provides the greatest lift,  outperforming both the Clustering and Naive Bayes models.</span></span>  
  
 <span data-ttu-id="cc44b-147">Para obter uma explicação detalhada de um gráfico de comparação de precisão semelhante ao criado nesta lição, consulte o gráfico de comparação de [precisão &#40;Analysis Services&#41;de mineração de dados ](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="cc44b-147">For an in-depth explanation of a lift chart similar to the one created in this lesson, see [Lift Chart &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="cc44b-148">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="cc44b-148">Next Task in Lesson</span></span>  
 [<span data-ttu-id="cc44b-149">Testando um modelo filtrado &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="cc44b-149">Testing a Filtered Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-a-filtered-model-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="cc44b-150">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cc44b-150">See Also</span></span>  
 <span data-ttu-id="cc44b-151">[&#40;do gráfico de comparação de precisão Analysis Services-Mineração de dados&#41;](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="cc44b-151">[Lift Chart &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="cc44b-152">Guia gráfico de comparação &#40;exibição de gráfico de precisão de mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="cc44b-152">Lift Chart Tab &#40;Mining Accuracy Chart View&#41;</span></span>](../../2014/analysis-services/lift-chart-tab-mining-accuracy-chart-view.md)  
  
  
