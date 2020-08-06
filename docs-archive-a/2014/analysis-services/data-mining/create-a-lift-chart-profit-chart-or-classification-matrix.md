---
title: Criar um gráfico de comparação de precisão, gráfico de ganho ou matriz de classificação | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Mining Accuracy Chart [Analysis Services], mining structures
ms.assetid: aa3d052f-58a9-4417-8e7a-5e6feb562af0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 932138b37b36269bed86df42786bd5d684f75ee9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679102"
---
# <a name="create-a-lift-chart-profit-chart-or-classification-matrix"></a><span data-ttu-id="c75ee-102">Criar um gráfico de comparação de precisão, gráfico de lucro ou matriz de classificação</span><span class="sxs-lookup"><span data-stu-id="c75ee-102">Create a Lift Chart, Profit Chart, or Classification Matrix</span></span>
  <span data-ttu-id="c75ee-103">Você pode criar um gráfico de precisão de um modelo de mineração de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] em cinco etapas básica:</span><span class="sxs-lookup"><span data-stu-id="c75ee-103">You can create an accuracy chart for an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] data mining model in five basic steps:</span></span>  
  
-   <span data-ttu-id="c75ee-104">Selecione a estrutura de mineração que contém os modelos de mineração que deseja comparar.</span><span class="sxs-lookup"><span data-stu-id="c75ee-104">Select the mining structure that contains the mining models that you want to compare.</span></span>  
  
-   <span data-ttu-id="c75ee-105">Selecione os modelos de mineração a serem adicionados ao gráfico.</span><span class="sxs-lookup"><span data-stu-id="c75ee-105">Select the mining models to add to the chart.</span></span>  
  
-   <span data-ttu-id="c75ee-106">Especifique uma fonte de dados de teste para usar na geração do gráfico.</span><span class="sxs-lookup"><span data-stu-id="c75ee-106">Specify a source of testing data to use in generating the chart.</span></span>  
  
-   <span data-ttu-id="c75ee-107">Escolha o tipo de gráfico.</span><span class="sxs-lookup"><span data-stu-id="c75ee-107">Choose the chart type.</span></span>  
  
-   <span data-ttu-id="c75ee-108">Configure as opções de gráfico.</span><span class="sxs-lookup"><span data-stu-id="c75ee-108">Configure the chart options.</span></span>  
  
 <span data-ttu-id="c75ee-109">Estas etapas básicas são iguais para o gráfico de comparação de precisão, o gráfico de ganho e a matriz de classificação.</span><span class="sxs-lookup"><span data-stu-id="c75ee-109">These basic steps are the same for the lift chart, profit chart, and classification matrix.</span></span> <span data-ttu-id="c75ee-110">Os procedimentos a seguir descrevem as etapas para configurar as opções básicas para estes tipos de gráfico.</span><span class="sxs-lookup"><span data-stu-id="c75ee-110">The following procedures outline the steps to configure the basic chart options for these chart types.</span></span> <span data-ttu-id="c75ee-111">Para obter informações sobre como criar um relatório de validação cruzada, consulte [Medidas no relatório de validação cruzada](measures-in-the-cross-validation-report.md).</span><span class="sxs-lookup"><span data-stu-id="c75ee-111">For information about how to create a cross-validation report, see [Measures in the Cross-Validation Report](measures-in-the-cross-validation-report.md).</span></span>  
  
### <a name="open-the-mining-structure-in-the-accuracy-chart-designer"></a><span data-ttu-id="c75ee-112">Abra a estrutura de mineração no Designer de Gráficos de Precisão</span><span class="sxs-lookup"><span data-stu-id="c75ee-112">Open the mining structure in the Accuracy Chart Designer</span></span>  
  
1.  <span data-ttu-id="c75ee-113">Abra o Designer de Mineração de Dados no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c75ee-113">Open the Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="c75ee-114">No Gerenciador de Soluções, clique duas vezes na estrutura que contém os modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="c75ee-114">In Solution Explorer, double-click the structure that contains the mining model or models.</span></span>  
  
3.  <span data-ttu-id="c75ee-115">Clique na guia **Gráfico de Precisão de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="c75ee-115">Click the **Mining Accuracy Chart** tab.</span></span>  
  
### <a name="select-mining-models-for-inclusion-in-the-chart"></a><span data-ttu-id="c75ee-116">Selecione modelos de mineração para inclusão no gráfico</span><span class="sxs-lookup"><span data-stu-id="c75ee-116">Select mining models for inclusion in the chart</span></span>  
  
1.  <span data-ttu-id="c75ee-117">Na guia **Gráfico de Precisão de Mineração** do Designer de Data Mining no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], clique na guia **Seleção de Entrada** .</span><span class="sxs-lookup"><span data-stu-id="c75ee-117">On the **Mining Accuracy Chart** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the **Input Selection** tab.</span></span>  
  
     <span data-ttu-id="c75ee-118">A lista exibe todos os modelos da estrutura atual que têm o mesmo atributo previsível.</span><span class="sxs-lookup"><span data-stu-id="c75ee-118">The list displays all models in the current structure that have the same predictable attribute.</span></span>  
  
2.  <span data-ttu-id="c75ee-119">Selecione a caixa **Mostrar** de cada modelo que deseja incluir no gráfico.</span><span class="sxs-lookup"><span data-stu-id="c75ee-119">Select the **Show box** for each model that you want to include in the chart.</span></span>  
  
3.  <span data-ttu-id="c75ee-120">Clique na caixa de texto **Nome da Coluna Previsível** e selecione o nome de uma coluna previsível da lista.</span><span class="sxs-lookup"><span data-stu-id="c75ee-120">Click the **Predictable Column Name** text box, and select the name of a predictable column from the list.</span></span> <span data-ttu-id="c75ee-121">Todos os modelos incluídos no gráfico devem usar a mesma coluna previsível.</span><span class="sxs-lookup"><span data-stu-id="c75ee-121">All models that you put in one chart must have the same predictable column.</span></span>  
  
4.  <span data-ttu-id="c75ee-122">Se você comparar dois modelos e as colunas previsíveis tiverem valores diferentes ou tipos de dados diferentes, desmarque a caixa **Sincronizar colunas de valores de previsão** para forçar uma comparação.</span><span class="sxs-lookup"><span data-stu-id="c75ee-122">If you compare two models and the predictable columns have different values or different data types, clear the **Synchonize prediction columns and values** box to force a comparison.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c75ee-123">Se a caixa **Sincronizar colunas de valores de previsão** estiver selecionada, o Analysis Services analisará os dados na coluna previsível do modelo e os dados de teste, e tentará encontrar a melhor correspondência.</span><span class="sxs-lookup"><span data-stu-id="c75ee-123">If the **Synchonize prediction columns and values** box is selected, Analysis Services analyzes the data in the predictable columns of the model and the test data, and attempts to find the best match.</span></span> <span data-ttu-id="c75ee-124">Portanto, não desmarque a caixa a menos que seja absolutamente necessário forçar uma comparação das colunas.</span><span class="sxs-lookup"><span data-stu-id="c75ee-124">Therefore, do not clear the box unless absolutely necessary to force a comparison of the columns.</span></span>  
  
5.  <span data-ttu-id="c75ee-125">Clique na caixa de texto **Valor de Previsão** e selecione um valor da lista.</span><span class="sxs-lookup"><span data-stu-id="c75ee-125">Click the **Predict Value** text box, and select a value from the list.</span></span> <span data-ttu-id="c75ee-126">Se a coluna previsível for um tipo de dados contínuo, você deve digitar um valor na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="c75ee-126">If the predictable column is a continuous data type, you must type a value in the text box.</span></span>  
  
     <span data-ttu-id="c75ee-127">Para obter informações, consulte [Escolher a coluna a ser usada em um teste de modelo de mineração](choose-the-column-to-use-for-testing-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="c75ee-127">For more information, see [Choose the Column to Use for Testing a Mining Model](choose-the-column-to-use-for-testing-a-mining-model.md).</span></span>  
  
### <a name="select-testing-data"></a><span data-ttu-id="c75ee-128">Selecionar dados de teste</span><span class="sxs-lookup"><span data-stu-id="c75ee-128">Select testing data</span></span>  
  
1.  <span data-ttu-id="c75ee-129">Na guia **Seleção de Entrada** da guia **Gráfico de Precisão de Mineração** , especifique a fonte de dados que será usada para gerar o gráfico selecionando uma das opções do grupo, **Selecionar conjunto de dados a ser usado para o gráfico de precisão**.</span><span class="sxs-lookup"><span data-stu-id="c75ee-129">On the **Input Selection** tab of the **Mining Accuracy Chart** tab, specify the source of the data that you will use to generate the chart by selecting one of the options in the group, **Select data set to be used for accuracy chart**.</span></span>  
  
    -   <span data-ttu-id="c75ee-130">Selecione a opção, **Usar casos de teste do modelo de mineração**, se desejar usar o subconjunto de casos definido pela interseção de casos de teste da estrutura de mineração e quaisquer filtros que tenham sido aplicados durante a criação do modelo.</span><span class="sxs-lookup"><span data-stu-id="c75ee-130">Select the option, **Use Mining Model test cases**, if you want to use the subset of cases that is defined by the intersection of the mining structure test cases and any filters that may have been applied during model creation.</span></span>  
  
    -   <span data-ttu-id="c75ee-131">Selecione a opção, **Usar casos de teste da estrutura de mineração**, para usar o conjunto completo de casos de teste definido como parte do conjunto de dados de controle de estruturas de mineração.</span><span class="sxs-lookup"><span data-stu-id="c75ee-131">Select the option, **Use mining structure test cases**, to use the full set of testing cases that were defined as part of the mining structures holdout data set.</span></span>  
  
    -   <span data-ttu-id="c75ee-132">Selecione a opção **Especificar um conjunto de dados diferente**se você quiser usar dados externos.</span><span class="sxs-lookup"><span data-stu-id="c75ee-132">Select the option, **Specify a different data set**, if you want to use external data.</span></span>  <span data-ttu-id="c75ee-133">O conjunto de dados deve estar disponível como uma exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c75ee-133">The data set must be available as a data source view.</span></span>   <span data-ttu-id="c75ee-134">Clique no botão procurar (**...**) para escolher as tabelas de dados a serem usadas para o gráfico de precisão.</span><span class="sxs-lookup"><span data-stu-id="c75ee-134">Click the browse (**...**) button to choose the data tables to use for the accuracy chart.</span></span> <span data-ttu-id="c75ee-135">Para obter mais informações, consulte [Escolher e mapear dados de teste de modelo](choose-and-map-model-testing-data.md).</span><span class="sxs-lookup"><span data-stu-id="c75ee-135">For more information, see [Choose and Map Model Testing Data](choose-and-map-model-testing-data.md).</span></span>  
  
         <span data-ttu-id="c75ee-136">Se você estiver usando um conjunto de dados externo, poderá filtrar, se desejar, o conjunto de dados de entrada.</span><span class="sxs-lookup"><span data-stu-id="c75ee-136">If you are using an external data set, you can optionally filter the input data set.</span></span> <span data-ttu-id="c75ee-137">Para obter mais informações, consulte [Aplicar filtros aos dados de teste de modelo](apply-filters-to-model-testing-data.md).</span><span class="sxs-lookup"><span data-stu-id="c75ee-137">For more information, see [Apply Filters to Model Testing Data](apply-filters-to-model-testing-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c75ee-138">Você não pode criar um filtro nos casos de teste do modelo ou nos casos de teste da estrutura de mineração na guia **seleção de entrada** . Para criar um filtro no modelo de mineração, modifique a propriedade Filter do modelo.</span><span class="sxs-lookup"><span data-stu-id="c75ee-138">You cannot create a filter on the model test cases or the mining structure test cases on the **Input Selection** tab. To create a filter on the mining model, modify the Filter property of the model.</span></span> <span data-ttu-id="c75ee-139">Para obter mais informações, consulte [Aplicar um filtro a um modelo de mineração](apply-a-filter-to-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="c75ee-139">For more information, see [Apply a Filter to a Mining Model](apply-a-filter-to-a-mining-model.md).</span></span>  
  
### <a name="configure-chart-settings-and-generate-the-chart"></a><span data-ttu-id="c75ee-140">Definir configurações de gráfico e gerar o gráfico</span><span class="sxs-lookup"><span data-stu-id="c75ee-140">Configure chart settings and generate the chart</span></span>  
  
1.  <span data-ttu-id="c75ee-141">Na guia **Gráfico de Precisão de Mineração** , clique na guia do gráfico que deseja criar.</span><span class="sxs-lookup"><span data-stu-id="c75ee-141">In the **Mining Accuracy Chart** tab, click the tab for the chart you want to create.</span></span>  
  
2.  <span data-ttu-id="c75ee-142">Para obter um gráfico de comparação de **precisão**, clique na guia gráfico de comparação de **precisão** . O gráfico é gerado automaticamente com base no modelo, atributos previsíveis e dados de entrada que você acabou de selecionar.</span><span class="sxs-lookup"><span data-stu-id="c75ee-142">For a **lift chart**, click the **Lift Chart** tab. The chart is automatically generated based on the model, predictable attributes, and input data that you just selected.</span></span>  
  
3.  <span data-ttu-id="c75ee-143">Para uma **matriz de classificação**, clique na guia **matriz de classificação** . Nenhuma configuração adicional é necessária; o gráfico é gerado automaticamente com base nos dados de entrada e no modelo que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="c75ee-143">For a **classification matrix**, click the **Classification Matrix** tab. No further settings are needed; the chart is automatically generated based on the input data and model that you selected.</span></span>  
  
4.  <span data-ttu-id="c75ee-144">Para um **gráfico de ganho**, primeiro clique na guia gráfico de comparação de **precisão** . Em seguida, na lista suspensa **tipo de gráfico** , selecione **gráfico de ganho**.</span><span class="sxs-lookup"><span data-stu-id="c75ee-144">For a **profit chart**, first click the **Lift Chart** tab. Then, from the **Chart type** drop-down list, select **Profit chart**.</span></span>  
  
     <span data-ttu-id="c75ee-145">Insira as configurações a seguir na caixa de diálogo **Configurações do Gráfico de Ganho** .</span><span class="sxs-lookup"><span data-stu-id="c75ee-145">Enter the following settings in the **Profit Chart Settings** dialog box.</span></span>  
  
     <span data-ttu-id="c75ee-146">**Média**</span><span class="sxs-lookup"><span data-stu-id="c75ee-146">**Population**</span></span>  
     <span data-ttu-id="c75ee-147">O número de casos do conjunto de dados que você quer usar ao criar o gráfico de comparação de precisão.</span><span class="sxs-lookup"><span data-stu-id="c75ee-147">The number of cases from the data set that you want to use when creating the lift chart.</span></span>  
  
     <span data-ttu-id="c75ee-148">O modelo sempre escolhe os casos na ordem de probabilidade decrescente, ou seja, se você está avaliando clientes em potencial e escolhe um número que representa somente metade dos registros do seu banco de dados de clientes, o modelo medirá a precisão no subconjunto de casos que melhor se adaptar ao seu modelo.</span><span class="sxs-lookup"><span data-stu-id="c75ee-148">The model always chooses the cases in order of decreasing probability; that is, if you are assessing potential customers and you choose a number that represents only half the records in your customer database, the model will measure accuracy on the subset of cases that best fit your model.</span></span>  
  
     <span data-ttu-id="c75ee-149">Isso acontece porque, ao usar o modelo para gerar uma correspondência ou criar uma campanha, você usa a probabilidade da previsão associada a cada caso para enviar mala direta apenas aos clientes com maior probabilidade de fornecer uma resposta positiva.</span><span class="sxs-lookup"><span data-stu-id="c75ee-149">This is because when you use the model to generate a mailing or create a campaign, you will use the prediction probability associated with each case to target only the customers who have the highest probability of making a positive response.</span></span>  
  
     <span data-ttu-id="c75ee-150">**Custo fixo**</span><span class="sxs-lookup"><span data-stu-id="c75ee-150">**Fixed Cost**</span></span>  
     <span data-ttu-id="c75ee-151">O custo fixo associado ao problema empresarial.</span><span class="sxs-lookup"><span data-stu-id="c75ee-151">The fixed cost that is associated with the business problem.</span></span>  
  
     <span data-ttu-id="c75ee-152">No caso de uma solução de mala direta, o custo fixo poderia representar a taxa de instalação de uma impressora, que é o custo inicial da preparação da mala direta promocional.</span><span class="sxs-lookup"><span data-stu-id="c75ee-152">If this were for a targeted mailing solution, the fixed cost might represent a printer setup fee that covers the initial cost of preparing the promotional mailing.</span></span>  
  
     <span data-ttu-id="c75ee-153">Esse custo se aplica uma vez a toda população alvo.</span><span class="sxs-lookup"><span data-stu-id="c75ee-153">This cost applies one time to the entire target population.</span></span>  
  
     <span data-ttu-id="c75ee-154">**Custo individual**</span><span class="sxs-lookup"><span data-stu-id="c75ee-154">**Individual Cost**</span></span>  
     <span data-ttu-id="c75ee-155">Os custos adicionais ao custo fixo, que podem estar associados a cada contato de cliente.</span><span class="sxs-lookup"><span data-stu-id="c75ee-155">Costs that are in addition to the fixed cost, that can be associated with each customer contact.</span></span> <span data-ttu-id="c75ee-156">Por exemplo, você poderia inserir o custo da tarifa de correio, no caso de mala direta promocional, ou de ligações telefônicas.</span><span class="sxs-lookup"><span data-stu-id="c75ee-156">For example, you might enter the postage cost for a promotional mailing or the cost of making telephone calls.</span></span>  
  
     <span data-ttu-id="c75ee-157">Esse custo deve ser o mesmo para toda a população alvo.</span><span class="sxs-lookup"><span data-stu-id="c75ee-157">This cost must be the same for the entire target population.</span></span> <span data-ttu-id="c75ee-158">Cada valor é multiplicado pelo número de casos designados.</span><span class="sxs-lookup"><span data-stu-id="c75ee-158">Each value is multiplied by the number of cases that are targeted.</span></span>  
  
     <span data-ttu-id="c75ee-159">**Receita por indivíduo**</span><span class="sxs-lookup"><span data-stu-id="c75ee-159">**Revenue Per Individual**</span></span>  
     <span data-ttu-id="c75ee-160">A receita associada a cada venda bem sucedida.</span><span class="sxs-lookup"><span data-stu-id="c75ee-160">The amount of revenue that is associated with each successful sale.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c75ee-161">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c75ee-161">See Also</span></span>  
 <span data-ttu-id="c75ee-162">[&#40;do gráfico de comparação de precisão Analysis Services-Mineração de dados&#41;](lift-chart-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="c75ee-162">[Lift Chart &#40;Analysis Services - Data Mining&#41;](lift-chart-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="c75ee-163">Matriz de classificação &#40;Analysis Services – Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="c75ee-163">Classification Matrix &#40;Analysis Services - Data Mining&#41;</span></span>](classification-matrix-analysis-services-data-mining.md)  
  
  
