---
title: Assistente de estimativa (suplementos de mineração de dados para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data modeling [data mining]
- estimation
ms.assetid: 7f2b1d5f-c9b3-4939-b35a-34ae099af15f
author: minewiskan
ms.author: owend
ms.openlocfilehash: ace9fa3a62690061677312d4f7dbb6b8a1d0ea5a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681897"
---
# <a name="estimate-wizard-data-mining-add-ins-for-excel"></a><span data-ttu-id="82ff6-102">Assistente de Estimativa (Suplementos de Mineração de Dados para Excel)</span><span class="sxs-lookup"><span data-stu-id="82ff6-102">Estimate Wizard (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="82ff6-103">![Assistente de Estimativa na faixa de opções Mineração de Dados](media/dmc-estimate.gif "Assistente de Estimativa na faixa de opções Mineração de Dados")</span><span class="sxs-lookup"><span data-stu-id="82ff6-103">![Estimate wizard in Data Mining ribbon](media/dmc-estimate.gif "Estimate wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="82ff6-104">O assistente de **estimativa** ajuda a criar um modelo de estimativa.</span><span class="sxs-lookup"><span data-stu-id="82ff6-104">The **Estimate** wizard helps you create an estimation model.</span></span> <span data-ttu-id="82ff6-105">Um modelo de estimativa extrai padrões dos dados e usa esses padrões para prever os fatores que afetam os resultados.</span><span class="sxs-lookup"><span data-stu-id="82ff6-105">An estimation model extracts patterns from data and uses the patterns to predict the factors that affect outcomes.</span></span>  
  
 <span data-ttu-id="82ff6-106">A estimativa é usada prever resultados numéricos.</span><span class="sxs-lookup"><span data-stu-id="82ff6-106">Estimation is used for predicting numeric outcomes.</span></span> <span data-ttu-id="82ff6-107">Por exemplo, se a coluna de destino contiver taxas de graduação para escolas, com essas taxas de graduação expressas como porcentagens, você poderá analisar os fatores que podem aumentar ou diminuir essas taxas de graduação, como o número de alunos por escola, a proporção aluno-professor e o número de professores.</span><span class="sxs-lookup"><span data-stu-id="82ff6-107">For example, if your target column contains graduation rates for schools, with graduation rates expressed as percentages, you could analyze factors that potentially increase or decrease graduation rates, such as the number of students per school, the student-teacher ratio, and the number of teachers.</span></span>  
  
## <a name="using-the-estimate-data-wizard"></a><span data-ttu-id="82ff6-108">Usando o Assistente para Estimar Dados</span><span class="sxs-lookup"><span data-stu-id="82ff6-108">Using the Estimate Data Wizard</span></span>  
  
1.  <span data-ttu-id="82ff6-109">Na faixa de faixas de **mineração de dados** , clique em **estimativa**.</span><span class="sxs-lookup"><span data-stu-id="82ff6-109">On the **Data Mining** ribbon, click **Estimate**.</span></span>  
  
2.  <span data-ttu-id="82ff6-110">Na caixa de diálogo **selecionar dados de origem** , selecione os dados de origem a serem usados.</span><span class="sxs-lookup"><span data-stu-id="82ff6-110">In the **Select Source Data** dialog box, select the source data to use.</span></span> <span data-ttu-id="82ff6-111">Você pode usar dados em uma **tabela**do Excel, um **intervalo de dados**do Excel ou de uma **fonte de dados externa**.</span><span class="sxs-lookup"><span data-stu-id="82ff6-111">You can use data in an Excel **Table**, an Excel **Data Range**, or from an **External data source**.</span></span>  
  
     <span data-ttu-id="82ff6-112">Se você usar uma fonte de dados externa, poderá criar exibições personalizadas ou as consultas e salvá-las como uma fonte de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82ff6-112">If you use an external data source, you can create custom views or queries and save them as an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source.</span></span>  
  
3.  <span data-ttu-id="82ff6-113">Na caixa de diálogo **estimativa** , selecione a **coluna a ser analisada**.</span><span class="sxs-lookup"><span data-stu-id="82ff6-113">In the **Estimation** dialog box, select the **Column to analyze**.</span></span>  
  
     <span data-ttu-id="82ff6-114">A coluna de destino deve conter dados numéricos contínuos.</span><span class="sxs-lookup"><span data-stu-id="82ff6-114">The target column must contain continuous numeric data.</span></span>  
  
4.  <span data-ttu-id="82ff6-115">Selecione as colunas a serem usadas como entrada marcando a caixa de seleção **colunas de entrada** .</span><span class="sxs-lookup"><span data-stu-id="82ff6-115">Select columns to use as input by checking the **Input columns** checkbox.</span></span>  
  
     <span data-ttu-id="82ff6-116">Essas colunas serão usadas para criar os padrões.</span><span class="sxs-lookup"><span data-stu-id="82ff6-116">These columns will be used to create the patterns.</span></span> <span data-ttu-id="82ff6-117">Você deverá eliminar da análise qualquer coluna que provavelmente não vá ajudar, como números de ID ou colunas que contenham dados irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="82ff6-117">You should eliminate from analysis any columns that are not likely to help, such as ID numbers, or columns that contain irrelevant data.</span></span>  
  
5.  <span data-ttu-id="82ff6-118">O assistente de **estimativa** seleciona o algoritmo ideal para seu conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="82ff6-118">The **Estimate** wizard selects the optimum algorithm for your data set.</span></span> <span data-ttu-id="82ff6-119">No entanto, você pode clicar em **parâmetros** para abrir a caixa de diálogo **parâmetros de algoritmo** e definir opções avançadas.</span><span class="sxs-lookup"><span data-stu-id="82ff6-119">However, you can click **Parameters** to open the **Algorithm Parameters** dialog box and set advanced options.</span></span>  
  
6.  <span data-ttu-id="82ff6-120">Se os dados forem numéricos e você puder usar o método de regressão linear da Microsoft, você poderá marcar a caixa **regressor** para todas as colunas numéricas que você souber (ou fortemente suspeitas) que serão correlacionadas com o valor previsível.</span><span class="sxs-lookup"><span data-stu-id="82ff6-120">If your data is numeric and you can use the Microsoft Linear Regression method, you can check the **Regressor** box for any numeric columns that you know (or strongly suspect) to be correlated with the predictable value.</span></span>  
  
     <span data-ttu-id="82ff6-121">O algoritmo irá testar os valores nessa coluna para determinar se eles afetam os resultados.</span><span class="sxs-lookup"><span data-stu-id="82ff6-121">The algorithm will then test the values in that column to determine if they affect the outcomes.</span></span> <span data-ttu-id="82ff6-122">Se você não tiver certeza, clique em **sugerir** e o algoritmo testará todas as colunas e detectará automaticamente os melhores valores a serem usados como regressores.</span><span class="sxs-lookup"><span data-stu-id="82ff6-122">If you are unsure, click **Suggest** and the algorithm will test all column and automatically detect the best values to use as regressors.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="82ff6-123">Um regressor é necessário para criar uma estimativa.</span><span class="sxs-lookup"><span data-stu-id="82ff6-123">A regressor is required to create an estimate.</span></span> <span data-ttu-id="82ff6-124">O assistente sempre recomenda o melhor regressor, com base em uma passagem inicial sobre os dados.</span><span class="sxs-lookup"><span data-stu-id="82ff6-124">The wizard always recommends the best regressor, based on an initial pass over the data.</span></span> <span data-ttu-id="82ff6-125">Assim, caso você não tenha certeza, será melhor aceitar as seleções recomendadas.</span><span class="sxs-lookup"><span data-stu-id="82ff6-125">Therefore, if you are not sure, it is best to accept the recommended selections.</span></span>  
  
7.  <span data-ttu-id="82ff6-126">Na página **dividir os dados em conjuntos de treinamento e teste** , especifique se deseja criar um pequeno subconjunto dos dados para teste.</span><span class="sxs-lookup"><span data-stu-id="82ff6-126">On the **Split data into training and testing sets** page, specify whether you want to create a small subset of the data for testing.</span></span>  
  
8.  <span data-ttu-id="82ff6-127">Na página **concluir** , forneça nomes para a nova estrutura de mineração e modo de mineração, ou aceite os nomes padrão fornecidos.</span><span class="sxs-lookup"><span data-stu-id="82ff6-127">On the **Finish** page, provide names for the new mining structure and mining mode, or accept the default names that are provided.</span></span>  
  
9. <span data-ttu-id="82ff6-128">Defina opções para usar o modelo.</span><span class="sxs-lookup"><span data-stu-id="82ff6-128">Set options for using the model.</span></span>  
  
    -   <span data-ttu-id="82ff6-129">Selecione **procurar** para abrir imediatamente o modelo em um visualizador.</span><span class="sxs-lookup"><span data-stu-id="82ff6-129">Select **Browse** to immediately open the model in a viewer.</span></span>  
  
         <span data-ttu-id="82ff6-130">Esse visualizador gráfico exibe um gráfico de rede de dependências e a árvore de decisão gerada pelo algoritmo.</span><span class="sxs-lookup"><span data-stu-id="82ff6-130">This graphical viewer displays a dependency network graph and the decision tree generated by the algorithm.</span></span> <span data-ttu-id="82ff6-131">Ao explorar essas informações, você pode entender melhor os fatores que colaboram para os valores estimados.</span><span class="sxs-lookup"><span data-stu-id="82ff6-131">By exploring this information, you can better understand the factors that contribute to the estimated values.</span></span>  
  
    -   <span data-ttu-id="82ff6-132">Selecione **habilitar detalhamento** para permitir que os usuários da sua análise exibam os dados subjacentes.</span><span class="sxs-lookup"><span data-stu-id="82ff6-132">Select **Enable drillthrough** to let users of your analysis view the underlying data.</span></span>  
  
         <span data-ttu-id="82ff6-133">Essa opção estará disponível somente se você usar os algoritmos de Árvore de Decisão ou Regressão Linear.</span><span class="sxs-lookup"><span data-stu-id="82ff6-133">This option is available only if you use the Decision Trees opr Linear Regression algorithms.</span></span>  
  
    -   <span data-ttu-id="82ff6-134">**Use o modelo temporário**.</span><span class="sxs-lookup"><span data-stu-id="82ff6-134">**Use temporary model**.</span></span> <span data-ttu-id="82ff6-135">Se você selecionar esta opção, o modelo não será salvo no servidor.</span><span class="sxs-lookup"><span data-stu-id="82ff6-135">If you select this option, the model will not be saved to the server.</span></span> <span data-ttu-id="82ff6-136">Os modelos temporários serão excluídos quando você fechar o Excel.</span><span class="sxs-lookup"><span data-stu-id="82ff6-136">Temporary models are deleted when you close Excel.</span></span>  
  
## <a name="more-about-estimation-models"></a><span data-ttu-id="82ff6-137">Mais informações sobre modelos de estimativa</span><span class="sxs-lookup"><span data-stu-id="82ff6-137">More About Estimation Models</span></span>  
 <span data-ttu-id="82ff6-138">O assistente de **estimativa** dá suporte ao uso de qualquer um dos seguintes algoritmos:</span><span class="sxs-lookup"><span data-stu-id="82ff6-138">The **Estimate** wizard supports the use of any of the following algorithms:</span></span>  
  
-   <span data-ttu-id="82ff6-139">Algoritmo da árvore de decisão da Microsoft</span><span class="sxs-lookup"><span data-stu-id="82ff6-139">Microsoft Decision Tree algorithm</span></span>  
  
-   <span data-ttu-id="82ff6-140">Algoritmo Regressão Linear da Microsoft</span><span class="sxs-lookup"><span data-stu-id="82ff6-140">Microsoft Linear Regression algorithm</span></span>  
  
-   <span data-ttu-id="82ff6-141">Algoritmo Regressão Logística da Microsoft</span><span class="sxs-lookup"><span data-stu-id="82ff6-141">Microsoft Logistic Regression algorithm</span></span>  
  
-   <span data-ttu-id="82ff6-142">Algoritmo rede neural da Microsoft</span><span class="sxs-lookup"><span data-stu-id="82ff6-142">Microsoft Neural network algorithm</span></span>  
  
 <span data-ttu-id="82ff6-143">Na caixa de diálogo **parâmetros de algoritmo** , você pode definir opções avançadas adicionais, dependendo do algoritmo escolhido.</span><span class="sxs-lookup"><span data-stu-id="82ff6-143">In the **Algorithm Parameters** dialog box, you can set additional advanced options, depending on which algorithm you chose.</span></span> <span data-ttu-id="82ff6-144">Para obter informações sobre as opções para cada um desses algoritmos, consulte esses tópicos nos Manuais Online do SQL Server:</span><span class="sxs-lookup"><span data-stu-id="82ff6-144">For information on the options for each algorithm see these topics in SQL Server Books Online:</span></span>  
  
 [<span data-ttu-id="82ff6-145">Referência técnica do algoritmo Árvores de Decisão da Microsoft</span><span class="sxs-lookup"><span data-stu-id="82ff6-145">Microsoft Decision Trees Algorithm Technical Reference</span></span>](data-mining/microsoft-decision-trees-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="82ff6-146">Referência Técnica do Algoritmo de Regressão Linear da Microsoft</span><span class="sxs-lookup"><span data-stu-id="82ff6-146">Microsoft Linear Regression Algorithm Technical Reference</span></span>](data-mining/microsoft-linear-regression-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="82ff6-147">Referência técnica do algoritmo Regressão Logística da Microsoft</span><span class="sxs-lookup"><span data-stu-id="82ff6-147">Microsoft Logistic Regression Algorithm Technical Reference</span></span>](data-mining/microsoft-logistic-regression-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="82ff6-148">Microsoft Neural Network Algorithm Technical Reference</span><span class="sxs-lookup"><span data-stu-id="82ff6-148">Microsoft Neural Network Algorithm Technical Reference</span></span>](data-mining/microsoft-neural-network-algorithm-technical-reference.md)  
  
### <a name="requirements"></a><span data-ttu-id="82ff6-149">Requisitos</span><span class="sxs-lookup"><span data-stu-id="82ff6-149">Requirements</span></span>  
 <span data-ttu-id="82ff6-150">Para usar o Assistente para Estimar Dados, você deve estar conectado a um banco de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82ff6-150">To use the Estimate Data Wizard, you must be connected to a [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="82ff6-151">Para obter informações sobre como criar uma conexão, consulte [conectar-se a dados de origem &#40;cliente de mineração de dados para Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="82ff6-151">For information about how to create a connection, see [Connect to Source Data &#40;Data Mining Client for Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span></span>  
  
 <span data-ttu-id="82ff6-152">Para usar um algoritmo de estimativa, o resultado que você está tentando prever deve ser expresso como um valor numérico, por exemplo, uma moeda, um valor de vendas, uma data ou uma hora.</span><span class="sxs-lookup"><span data-stu-id="82ff6-152">To use the estimation algorithm, the outcome that you are trying to predict must be expressed as a numeric value, such as a currency, sales amount, date, or time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82ff6-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="82ff6-153">See Also</span></span>  
 <span data-ttu-id="82ff6-154">[Criando um modelo de mineração de dados](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="82ff6-154">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 [<span data-ttu-id="82ff6-155">Explicação do diagrama de árvore de decisão &#40;suplementos de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="82ff6-155">Decision Tree Diagram Walkthrough  &#40;Data Mining Add-ins&#41;</span></span>](decision-tree-diagram-walkthrough-data-mining-add-ins.md)  
  
  
