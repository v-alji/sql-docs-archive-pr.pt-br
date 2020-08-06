---
title: Assistente de classificação (suplementos de mineração de dados para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data modeling [data mining]
- classification [data mining]
ms.assetid: 409c5076-c4c3-4f09-8f30-d3297df45f13
author: minewiskan
ms.author: owend
ms.openlocfilehash: b82fc98df10ae2e6754a378dacea108f9f3379ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571074"
---
# <a name="classify-wizard-data-mining-add-ins-for-excel"></a><span data-ttu-id="18c54-102">Assistente de Classificação (Suplementos de Mineração de Dados para Excel)</span><span class="sxs-lookup"><span data-stu-id="18c54-102">Classify Wizard (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="18c54-103">![Assistente para Classificação na faixa de opções Mineração de Dados](media/dmc-classify.gif "Assistente para Classificação na faixa de opções Mineração de Dados")</span><span class="sxs-lookup"><span data-stu-id="18c54-103">![Classify wizard in Data Mining ribbon](media/dmc-classify.gif "Classify wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="18c54-104">O assistente de **classificação** ajuda a criar um modelo de classificação com base nos dados existentes em uma tabela do Excel, em um intervalo do Excel ou em uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="18c54-104">The **Classify** wizard helps you build a classification model based on existing data in an Excel table, an Excel range, or an external data source.</span></span>  
  
 <span data-ttu-id="18c54-105">Um modelo de classificação extrai padrões nos dados que indicam similaridades e o ajudam a fazer previsões com base nos agrupamentos de valores.</span><span class="sxs-lookup"><span data-stu-id="18c54-105">A classification model extracts patterns in your data that indicate similarities and helps you make predictions based on groupings of values.</span></span> <span data-ttu-id="18c54-106">Por exemplo, um modelo de classificação talvez seja usado para prever o risco com base em padrões de renda ou gastos.</span><span class="sxs-lookup"><span data-stu-id="18c54-106">For example, a classification model might be used to predict risk based on income or spending patterns.</span></span>  
  
## <a name="using-the-classify-wizard"></a><span data-ttu-id="18c54-107">Usando o Assistente para Classificar</span><span class="sxs-lookup"><span data-stu-id="18c54-107">Using the Classify Wizard</span></span>  
  
1.  <span data-ttu-id="18c54-108">Na faixa de faixas de **mineração de dados** , clique em **classificar**e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="18c54-108">In the **Data Mining** ribbon, click **Classify**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="18c54-109">Na página **selecionar dados de origem** , escolha os dados a serem analisados.</span><span class="sxs-lookup"><span data-stu-id="18c54-109">In the **Select Source Data** page, choose the data to analyze.</span></span>  
  
     <span data-ttu-id="18c54-110">Esse assistente oferece suporte a vários tipos de dados: tabelas do Excel, intervalos do Excel e fontes de dados externas.</span><span class="sxs-lookup"><span data-stu-id="18c54-110">This wizard supports multiple kinds of data: Excel tables, Excel ranges, and external data sources.</span></span> <span data-ttu-id="18c54-111">Com dados externos, você poderá adicioná-la ao Excel ou escolher um conjunto de tabelas ou exibições em uma fonte de dados do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="18c54-111">With external data, you can either add it into Excel, or choose a set of tables or views in an Analysis Services data source.</span></span> <span data-ttu-id="18c54-112">Você também pode adicionar tabelas e alterar colunas para criar fontes de dados ad hoc.</span><span class="sxs-lookup"><span data-stu-id="18c54-112">You can also add tables and change columns to create ad hoc data sources.</span></span>  
  
3.  <span data-ttu-id="18c54-113">Na página **classificação** , escolha a coluna que você deseja classificar.</span><span class="sxs-lookup"><span data-stu-id="18c54-113">On the **Classification** page, choose the column that you want to classify.</span></span>  
  
     <span data-ttu-id="18c54-114">Examine as colunas na lista, **colunas de entrada**e desmarque as colunas que têm valores exclusivos e, portanto, não são úteis para a criação de padrões, como números de ID, nomes de clientes e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="18c54-114">Review the columns in the list, **Input columns**, and deselect any columns that have unique values and thus aren't useful for creating patterns, such as ID numbers, customer names, and so on.</span></span> <span data-ttu-id="18c54-115">Você também deve remover colunas que essencialmente duplicam a coluna classificável.</span><span class="sxs-lookup"><span data-stu-id="18c54-115">You should also remove columns that essentially duplicate the classifiable column.</span></span>  
  
     <span data-ttu-id="18c54-116">Por exemplo, se você estiver classificando a previsão da categoria de um produto, deverá excluir o campo da subcategoria se houver uma regra de negócio conhecida, caso contrário, a intensidade dessa regra pode impedir que você descubra outras correlações.</span><span class="sxs-lookup"><span data-stu-id="18c54-116">For example, if you are classifying predicting the category of a product, you should exclude the subcategory field if there is a known business rule, or else the strength of that rule might prevent you from discovering other correlations.</span></span>  
  
4.  <span data-ttu-id="18c54-117">Opcionalmente, clique em **parâmetros** para alterar os parâmetros do algoritmo e personalizar o comportamento do modelo de clustering.</span><span class="sxs-lookup"><span data-stu-id="18c54-117">Optionally, click **Parameters** to change the algorithm parameters and customize the behavior of the clustering model.</span></span>  
  
5.  <span data-ttu-id="18c54-118">Na página **dividir os dados em conjuntos de treinamento e teste** , especifique a quantidade de dados a serem retidos para teste.</span><span class="sxs-lookup"><span data-stu-id="18c54-118">In the **Split data into training and testing sets** page, specify how much data to hold out for testing.</span></span> <span data-ttu-id="18c54-119">O restante é sempre usado para treinar o modelo.</span><span class="sxs-lookup"><span data-stu-id="18c54-119">The remainder is always used for training the model.</span></span>  
  
     <span data-ttu-id="18c54-120">A configuração padrão é de 30% de dados para teste e 70% de dados para treinamento.</span><span class="sxs-lookup"><span data-stu-id="18c54-120">The default setting is 30% testing data and 70% training data.</span></span>  
  
6.  <span data-ttu-id="18c54-121">Na página **concluir** , forneça um nome descritivo para seu conjunto de dados e modelo e defina as seguintes opções que controlam como você trabalha com o modelo concluído:</span><span class="sxs-lookup"><span data-stu-id="18c54-121">On the **Finish** page, provide a descriptive name for your data set and model, and set the following options that control how you work with the finished model:</span></span>  
  
    -   <span data-ttu-id="18c54-122">**Procurar modelo**.</span><span class="sxs-lookup"><span data-stu-id="18c54-122">**Browse model**.</span></span> <span data-ttu-id="18c54-123">Quando essa opção é selecionada, assim que o assistente termina de processar o modelo, ele abre uma janela de **procura** para ajudá-lo a explorar os resultados.</span><span class="sxs-lookup"><span data-stu-id="18c54-123">When this option is selected, as soon as the wizard finishes processing the model, it opens a **Browse** window to help you explore the results.</span></span> <span data-ttu-id="18c54-124">O conteúdo do visualizador depende do tipo de modelo que você criou.</span><span class="sxs-lookup"><span data-stu-id="18c54-124">The contents of the viewer depend on the type of model you built.</span></span> <span data-ttu-id="18c54-125">Para obter mais informações, consulte [navegando em um modelo de árvores de decisão](browsing-a-decision-trees-model.md) e [navegando em um modelo de rede neural](browsing-a-neural-network-model.md).</span><span class="sxs-lookup"><span data-stu-id="18c54-125">For more information, see [Browsing a Decision Trees Model](browsing-a-decision-trees-model.md) and [Browsing a Neural Network Model](browsing-a-neural-network-model.md).</span></span>  
  
    -   <span data-ttu-id="18c54-126">**Habilitar detalhamento**.</span><span class="sxs-lookup"><span data-stu-id="18c54-126">**Enable drillthrough**.</span></span> <span data-ttu-id="18c54-127">Selecione esta opção para visualizar os dados subjacentes do modelo finalizado.</span><span class="sxs-lookup"><span data-stu-id="18c54-127">Select this option to view the underlying data from the finished model.</span></span> <span data-ttu-id="18c54-128">Essa opção estará disponível somente se você criar um modelo de Árvore de Decisão.</span><span class="sxs-lookup"><span data-stu-id="18c54-128">This option is only available if you build a Decision Tree model.</span></span>  
  
    -   <span data-ttu-id="18c54-129">**Use o modelo temporário**.</span><span class="sxs-lookup"><span data-stu-id="18c54-129">**Use temporary model**.</span></span> <span data-ttu-id="18c54-130">Se você selecionar esta opção, o modelo não será salvo no servidor.</span><span class="sxs-lookup"><span data-stu-id="18c54-130">If you select this option, the model will not be saved to the server.</span></span> <span data-ttu-id="18c54-131">Os modelos temporários serão excluídos quando você fechar o Excel.</span><span class="sxs-lookup"><span data-stu-id="18c54-131">Temporary models are deleted when you close Excel.</span></span>  
  
## <a name="more-about-classification-models"></a><span data-ttu-id="18c54-132">Mais informações sobre os modelos de classificação</span><span class="sxs-lookup"><span data-stu-id="18c54-132">More About Classification Models</span></span>  
 <span data-ttu-id="18c54-133">Na caixa de diálogo **parâmetros de algoritmo** , você também pode escolher o método de classificação entre esses algoritmos fornecidos no Analysis Services:</span><span class="sxs-lookup"><span data-stu-id="18c54-133">In the **Algorithm Parameters** dialog box, you can also choose the classification method from among these algorithms provided in Analysis Services:</span></span>  
  
-   <span data-ttu-id="18c54-134">Árvore de Decisão da Microsoft</span><span class="sxs-lookup"><span data-stu-id="18c54-134">Microsoft Decision Tree</span></span>  
  
-   <span data-ttu-id="18c54-135">Regressão Logística da Microsoft</span><span class="sxs-lookup"><span data-stu-id="18c54-135">Microsoft Logistic Regression</span></span>  
  
-   <span data-ttu-id="18c54-136">Microsoft Naïve Bayes</span><span class="sxs-lookup"><span data-stu-id="18c54-136">Microsoft Naïve Bayes</span></span>  
  
-   <span data-ttu-id="18c54-137">Rede Neural da Microsoft</span><span class="sxs-lookup"><span data-stu-id="18c54-137">Microsoft Neural Network</span></span>  
  
 <span data-ttu-id="18c54-138">Embora os algoritmos possam gerar resultados semelhantes, eles analisam os dados de maneira diferente. Portanto, é recomendável tentar vários algoritmos e comparar os resultados.</span><span class="sxs-lookup"><span data-stu-id="18c54-138">Although the algorithms might yield similar results, they analyze the data differently, so we recommend trying several algorithms and comparing the results.</span></span> <span data-ttu-id="18c54-139">O método padrão é Árvores de Decisão da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="18c54-139">The default method is Microsoft Decision Trees.</span></span>  
  
 <span data-ttu-id="18c54-140">Na lista de **parâmetros** , você pode alterar as opções avançadas, que dependem do tipo de algoritmo escolhido.</span><span class="sxs-lookup"><span data-stu-id="18c54-140">In the **Parameters** list, you can change advanced options, which depend on the type of algorithm you choose.</span></span> <span data-ttu-id="18c54-141">Os parâmetros para cada algoritmo são descritos mais detalhadamente nos Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="18c54-141">The parameters for each algorithm are described in more detail in SQL Server Books Online.</span></span>  
  
 [<span data-ttu-id="18c54-142">Referência técnica do algoritmo Árvores de Decisão da Microsoft</span><span class="sxs-lookup"><span data-stu-id="18c54-142">Microsoft Decision Trees Algorithm Technical Reference</span></span>](data-mining/microsoft-decision-trees-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="18c54-143">Referência técnica do algoritmo Regressão Logística da Microsoft</span><span class="sxs-lookup"><span data-stu-id="18c54-143">Microsoft Logistic Regression Algorithm Technical Reference</span></span>](data-mining/microsoft-logistic-regression-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="18c54-144">Referência técnica do algoritmo Microsoft Naive Bayes</span><span class="sxs-lookup"><span data-stu-id="18c54-144">Microsoft Naive Bayes Algorithm Technical Reference</span></span>](data-mining/microsoft-naive-bayes-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="18c54-145">Microsoft Neural Network Algorithm Technical Reference</span><span class="sxs-lookup"><span data-stu-id="18c54-145">Microsoft Neural Network Algorithm Technical Reference</span></span>](data-mining/microsoft-neural-network-algorithm-technical-reference.md)  
  
### <a name="requirements"></a><span data-ttu-id="18c54-146">Requisitos</span><span class="sxs-lookup"><span data-stu-id="18c54-146">Requirements</span></span>  
 <span data-ttu-id="18c54-147">Para usar o assistente de **classificação** , você deve estar conectado a um [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] banco de dados.</span><span class="sxs-lookup"><span data-stu-id="18c54-147">To use the **Classify** wizard, you must be connected to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="18c54-148">Para obter informações sobre como criar uma conexão, consulte [conectar-se a dados de origem &#40;cliente de mineração de dados para Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="18c54-148">For information about how to create a connection, see [Connect to Source Data &#40;Data Mining Client for Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18c54-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="18c54-149">See Also</span></span>  
 [<span data-ttu-id="18c54-150">Criar um modelo de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="18c54-150">Creating a Data Mining Model</span></span>](creating-a-data-mining-model.md)  
  
  
