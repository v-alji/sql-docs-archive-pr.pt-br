---
title: Validando modelos e usando modelos para previsão (suplementos de mineração de dados para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, validating
- mining models, charting
- validation [data mining]
- mining models, testing
ms.assetid: e245ac1f-1230-48e9-9091-e70b131aa2a8
author: minewiskan
ms.author: owend
ms.openlocfilehash: c1dd4f9bab977a90579076b824d2c0aa525c84af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572209"
---
# <a name="validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel"></a><span data-ttu-id="84408-102">Validando modelos e usando modelos para previsão (suplementos de mineração de dados para Excel)</span><span class="sxs-lookup"><span data-stu-id="84408-102">Validating Models and Using Models for Prediction (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="84408-103">Testar e validar o modelo são etapas importantes no processo de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="84408-103">Testing and validating your model is an important step in the data mining process.</span></span> <span data-ttu-id="84408-104">Você deve saber o quão bom é o desempenho dos modelos de mineração em relação aos dados reais, antes de implantá-los em um ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="84408-104">You must know how well your mining models perform against real data before you deploy the models into a production environment.</span></span>  
  
 <span data-ttu-id="84408-105">Os Suplementos de Mineração de Dados incluem ferramentas que ajudam você a testar os modelos criados e a criar previsões e recomendações usando os modelos.</span><span class="sxs-lookup"><span data-stu-id="84408-105">The Data Mining Add-ins include tools that help you test the models you built, and create predictions and recommendations using the models.</span></span>  
  
## <a name="accuracy-chart"></a><span data-ttu-id="84408-106">Gráfico de Precisão</span><span class="sxs-lookup"><span data-stu-id="84408-106">Accuracy Chart</span></span>  
 <span data-ttu-id="84408-107">O assistente de **gráfico de precisão** ajuda a criar uma consulta de previsão e a avaliar o desempenho de um modelo de Data Mining criando um gráfico de comparação de dispersão ou gráfico de comparação.</span><span class="sxs-lookup"><span data-stu-id="84408-107">The **Accuracy Chart** wizard helps you create a prediction query and assess the performance of a data mining model by creating a lift chart or scatter plot chart.</span></span> <span data-ttu-id="84408-108">O gráfico de comparação de precisão ajuda a diferenciar modelos de uma estrutura que são quase os mesmos, a fim de auxiliar a determinar qual modelo fornece as melhores previsões.</span><span class="sxs-lookup"><span data-stu-id="84408-108">The lift chart helps distinguish between models in a structure that are almost the same, to help you determine which model provides the best predictions.</span></span>  
  
 [<span data-ttu-id="84408-109">Gráfico de precisão &#40;SQL Server suplementos de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="84408-109">Accuracy Chart &#40;SQL Server Data Mining Add-ins&#41;</span></span>](accuracy-chart-sql-server-data-mining-add-ins.md)  
  
## <a name="classification-matrix"></a><span data-ttu-id="84408-110">Matriz de classificação</span><span class="sxs-lookup"><span data-stu-id="84408-110">Classification Matrix</span></span>  
 <span data-ttu-id="84408-111">O assistente de **matriz de classificação** ajuda a criar uma consulta de previsão para avaliar o desempenho de um modelo de classificação.</span><span class="sxs-lookup"><span data-stu-id="84408-111">The **Classification Matrix** wizard helps you create a prediction query to assess the performance of a classification model.</span></span> <span data-ttu-id="84408-112">A saída é um gráfico que resume previsões precisas e imprecisas feitas pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="84408-112">The output is a chart that summarizes both accurate and inaccurate predictions made by the model.</span></span> <span data-ttu-id="84408-113">A matriz é uma ferramenta valiosa porque além de mostrar com que frequência o modelo previu corretamente um valor, também mostra quais valores o modelo mais previu de forma incorreta.</span><span class="sxs-lookup"><span data-stu-id="84408-113">The matrix is a valuable tool because it not only shows how frequently the model correctly predicted a value, but also shows which values the model most frequently predicted incorrectly.</span></span>  
  
 [<span data-ttu-id="84408-114">&#40;de matrizes de classificação SQL Server suplementos de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="84408-114">Classification Matrix &#40;SQL Server Data Mining Add-ins&#41;</span></span>](classification-matrix-sql-server-data-mining-add-ins.md)  
  
## <a name="profit-chart"></a><span data-ttu-id="84408-115">Gráfico de ganho</span><span class="sxs-lookup"><span data-stu-id="84408-115">Profit Chart</span></span>  
 <span data-ttu-id="84408-116">O assistente de **gráfico de ganho** ajuda a avaliar os benefícios de usar um modelo de data mining e avaliar os custos de falsos positivos e falsos negativos</span><span class="sxs-lookup"><span data-stu-id="84408-116">The **Profit Chart** wizard helps you weigh the benefits of using a data mining model and assess the costs of both false positives and false negatives</span></span>  
  
 <span data-ttu-id="84408-117">Esse tipo de gráfico mede a precisão da previsão do modelo e incorpora custos unitários e gerais especificados por você.</span><span class="sxs-lookup"><span data-stu-id="84408-117">This chart type measures the prediction accuracy of the model and incorporates unit and overall costs that you specify.</span></span>  
  
 <span data-ttu-id="84408-118">[&#40;de gráfico de ganho SQL Server suplementos de mineração de dados&#41;](profit-chart-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="84408-118">[Profit Chart &#40;SQL Server Data Mining Add-ins&#41;](profit-chart-sql-server-data-mining-add-ins.md).</span></span>  
  
## <a name="cross-validation"></a><span data-ttu-id="84408-119">Validação cruzada</span><span class="sxs-lookup"><span data-stu-id="84408-119">Cross-Validation</span></span>  
 <span data-ttu-id="84408-120">A validação cruzada é uma técnica estabelecida na comunidade de mineração de dados para avaliar a validade de um conjunto de dados e a precisão de um modelo de mineração no conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="84408-120">Cross-validation is an established technique in the data mining community for assessing the validity of a data set and the accuracy of a mining model on that data set.</span></span> <span data-ttu-id="84408-121">Divide um conjunto de dados em subconjuntos e, então, cria, treina e testa interativamente modelos em cada subconjunto.</span><span class="sxs-lookup"><span data-stu-id="84408-121">It divides a set of data into subsets, and then iteratively creates, trains, and tests models on each subset.</span></span>  
  
 <span data-ttu-id="84408-122">O assistente de **validação cruzada** permite especificar o número de dobras pelos quais os dados são divididos e, em seguida, fornece um relatório de validação cruzada que descreve estatisticamente as diferenças entre essas seções cruzadas.</span><span class="sxs-lookup"><span data-stu-id="84408-122">The **Cross-Validation** wizard lets you specify the number of folds to divide your data by, and then provides a cross-validation report that statistically describes the differences among these cross-sections.</span></span> <span data-ttu-id="84408-123">A partir disso, você pode determinar se o modelo é bem-executado em todos os dados de treinamento ou talvez seja afetado por um subconjunto em particular.</span><span class="sxs-lookup"><span data-stu-id="84408-123">From this you can determine whether the model performs well on all training data, or might be skewed to a particular subset.</span></span>  
  
 [<span data-ttu-id="84408-124">&#40;de validação cruzada SQL Server suplementos de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="84408-124">Cross-Validation &#40;SQL Server Data Mining Add-ins&#41;</span></span>](cross-validation-sql-server-data-mining-add-ins.md)  
  
## <a name="query-wizard"></a><span data-ttu-id="84408-125">Assistente de Consulta</span><span class="sxs-lookup"><span data-stu-id="84408-125">Query Wizard</span></span>  
 <span data-ttu-id="84408-126">O assistente de **consulta** é uma ferramenta interativa que ajuda você a criar uma consulta de previsão.</span><span class="sxs-lookup"><span data-stu-id="84408-126">The **Query** wizard is an interactive tool that helps you build a prediction query.</span></span> <span data-ttu-id="84408-127">As consultas são uma forma de gerar recomendações, previsões futuras e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="84408-127">Queries are how you generate recommendations, future forecasts, and so forth.</span></span>  
  
 <span data-ttu-id="84408-128">No assistente de **consulta** , você escolhe um modelo e, em seguida, fornece dados de entrada, como valores únicos ou de uma tabela ou intervalo, e o assistente o ajuda a selecionar colunas para saída.</span><span class="sxs-lookup"><span data-stu-id="84408-128">In the **Query** wizard, you pick a model, and then provide input data, either as single values or from a table or range, and the wizard helps you select columns to output.</span></span> <span data-ttu-id="84408-129">Também é possível adicionar funções à sua consulta para gerar pontuações de probabilidade e outras estatísticas úteis.</span><span class="sxs-lookup"><span data-stu-id="84408-129">You can also add functions to your query to generate probability scores and other useful statistics.</span></span>  
  
 [<span data-ttu-id="84408-130">&#40;de consulta SQL Server suplementos de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="84408-130">Query &#40;SQL Server Data Mining Add-ins&#41;</span></span>](query-sql-server-data-mining-add-ins.md)  
  
## <a name="advanced-query-editor"></a><span data-ttu-id="84408-131">Editor Avançado de Consulta</span><span class="sxs-lookup"><span data-stu-id="84408-131">Advanced Query Editor</span></span>  
 <span data-ttu-id="84408-132">O **Editor de consulta avançada** é um conjunto interativo de caixas de diálogo que ajuda você a criar todos os tipos de instruções DMX, tudo, desde a execução de consultas personalizadas até a criação e o treinamento de novos modelos, a exclusão de modelos ou a criação de novos conjuntos de dados.</span><span class="sxs-lookup"><span data-stu-id="84408-132">The **Advanced Query Editor** is an interactive set of dialog boxes that helps you build all kinds of DMX statements, anything from running custom queries to creating and training new models, deleting models, or creating new data sets.</span></span>  
  
 [<span data-ttu-id="84408-133">Editor de Consulta Avançada de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="84408-133">Advanced Data Mining Query Editor</span></span>](advanced-data-mining-query-editor.md)  
  
## <a name="see-also"></a><span data-ttu-id="84408-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="84408-134">See Also</span></span>  
 <span data-ttu-id="84408-135">[Explorando e limpando dados](exploring-and-cleaning-data.md) </span><span class="sxs-lookup"><span data-stu-id="84408-135">[Exploring and Cleaning Data](exploring-and-cleaning-data.md) </span></span>  
 <span data-ttu-id="84408-136">[Criando um modelo de mineração de dados](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="84408-136">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 [<span data-ttu-id="84408-137">Implantando e dimensionando modelos de mineração &#40;suplementos de mineração de dados para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="84408-137">Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;</span></span>](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md)  
  
  
