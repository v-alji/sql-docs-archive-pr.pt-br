---
title: Criando um modelo de mineração de dados | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining models, creating
- forecasting [data mining]
- mining models, creating
- clustering [data mining]
- association [data mining]
- data modeling [data mining]
- estimation
- classification [data mining]
ms.assetid: 804b7db3-1f6a-4f73-a81d-bbe02520d7c6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1e27739d3733c0b48dc6cff3e83e01f9cb12bce7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574948"
---
# <a name="creating-a-data-mining-model"></a><span data-ttu-id="4b463-102">Criando um modelo de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="4b463-102">Creating a Data Mining Model</span></span>
  <span data-ttu-id="4b463-103">A modelagem de dados é a etapa de Data Mining em que você cria padrões e tendências aplicando *algoritmos* aos dados.</span><span class="sxs-lookup"><span data-stu-id="4b463-103">Data modeling is the step of data mining where you build patterns and trends by applying *algorithms* to data.</span></span> <span data-ttu-id="4b463-104">Posteriormente, você poderá usar esses padrões para análise ou para fazer previsões.</span><span class="sxs-lookup"><span data-stu-id="4b463-104">Later you can use those patterns for analysis, or to make predictions.</span></span>  
  
 <span data-ttu-id="4b463-105">Os Suplementos de Mineração de Dados para Office oferecem suporte a mineração de dados por meio de assistentes que facilitam a criação de modelos.</span><span class="sxs-lookup"><span data-stu-id="4b463-105">The Data Mining Add-ins for Office support data mining through wizards that make it easy to create models.</span></span> <span data-ttu-id="4b463-106">Os assistentes analisam os dados, identificam correlações, calculam o significado estatístico de todas as variáveis e selecionam automaticamente o melhor modelo.</span><span class="sxs-lookup"><span data-stu-id="4b463-106">The wizards analyze the data, identify correlations, compute statistical significance of all variables, and automatically select the best model.</span></span>  
  
 <span data-ttu-id="4b463-107">Embora essa funcionalidade seja cada vez mais potente que as ferramentas de Data Mining fornecidas pelo [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , a combinação de assistentes e a interface familiar do Excel facilita a criação, a modificação e o uso de data mining.</span><span class="sxs-lookup"><span data-stu-id="4b463-107">Although this functionality is every bit as powerful as the data mining tools provided by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], the combination of wizards and the familiar Excel interface makes it easy to create, modify, and use data mining.</span></span>  
  
## <a name="advanced-data-mining"></a><span data-ttu-id="4b463-108">Avançados (mineração de dados)</span><span class="sxs-lookup"><span data-stu-id="4b463-108">Advanced (Data Mining)</span></span>  
 <span data-ttu-id="4b463-109">Os assistentes avançados permitem criar novos modelos de Data Mining, com base nos dados armazenados no Excel, usando um dos algoritmos de Data Mining no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4b463-109">The Advanced wizards let you create new data mining models, based on data stored in Excel, by using one of the data mining algorithms in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
### <a name="create-mining-structure"></a><span data-ttu-id="4b463-110">Criar a Estrutura de Mineração</span><span class="sxs-lookup"><span data-stu-id="4b463-110">Create Mining Structure</span></span>  
 <span data-ttu-id="4b463-111">O Assistente para Criar Estrutura de Mineração o ajuda a criar uma nova estrutura de mineração de dados, que você pode usar como a base para vários modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="4b463-111">The Create Mining Structure wizard helps you build a new data mining structure, which you can use as the basis for multiple mining models.</span></span> <span data-ttu-id="4b463-112">O assistente lhe oferece a opção de separar parte dos dados para usar como um conjunto de testes, para que você possa avaliar todos os modelos que utilizam os mesmos dados de acordo com um padrão de teste consistente.</span><span class="sxs-lookup"><span data-stu-id="4b463-112">The wizard gives you the option to set aside a portion of the data to use as a testing set, so that you can evaluate all models that use the same data according to a consistent testing standard.</span></span>  
  
 [<span data-ttu-id="4b463-113">Crie &#40;de estrutura de mineração SQL Server suplementos de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="4b463-113">Create Mining Structure &#40;SQL Server Data Mining Add-ins&#41;</span></span>](create-mining-structure-sql-server-data-mining-add-ins.md)  
  
### <a name="add-model-to-structure"></a><span data-ttu-id="4b463-114">Adicionar modelo à estrutura</span><span class="sxs-lookup"><span data-stu-id="4b463-114">Add Model to Structure</span></span>  
 <span data-ttu-id="4b463-115">O assistente para Adicionar Modelo à Estrutura lhe permite escolher uma estrutura de mineração de dados existente e criar um novo modelo de mineração de dados para ela.</span><span class="sxs-lookup"><span data-stu-id="4b463-115">The Add Model to Structure wizard lets you choose an existing data mining structure and create a new data mining model for it.</span></span> <span data-ttu-id="4b463-116">Você pode adicionar vários modelos de mineração a uma estrutura, alterar os parâmetros ou escolher algoritmos de mineração de dados diferentes e personalizar a saída.</span><span class="sxs-lookup"><span data-stu-id="4b463-116">You can add multiple mining models to a structure, changing the parameters or choosing different data mining algorithms, and customize the output.</span></span>  
  
 [<span data-ttu-id="4b463-117">Adicionar modelo à estrutura &#40;suplementos de mineração de dados para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4b463-117">Add Model to Structure &#40;Data Mining Add-ins for Excel&#41;</span></span>](add-model-to-structure-data-mining-add-ins-for-excel.md)  
  
## <a name="analyze-key-influencers-analyze"></a><span data-ttu-id="4b463-118">Analisar os Influenciadores Principais (Analisar)</span><span class="sxs-lookup"><span data-stu-id="4b463-118">Analyze Key Influencers (Analyze)</span></span>  
 <span data-ttu-id="4b463-119">Você escolhe uma coluna ou um valor de saída e então o algoritmo analisa todos os dados de saída para identificar os fatores com mais influência no destino.</span><span class="sxs-lookup"><span data-stu-id="4b463-119">You choose a column or output value of interest, and then the algorithm analyzes all the input data to identify the factors that have the most influence on the target.</span></span> <span data-ttu-id="4b463-120">Opcionalmente, você pode criar um relatório que compara quaisquer dois valores, de forma que você possa ver como os influenciadores são alterados.</span><span class="sxs-lookup"><span data-stu-id="4b463-120">Optionally, you can create a report that compares any two values, so that you can see how the influencers change.</span></span>  
  
 <span data-ttu-id="4b463-121">A ferramenta **analisar influenciadores principais** usa o algoritmo Bayes simples da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4b463-121">The **Analyze Key Influencers** tool uses the Microsoft Naïve Bayes algorithm.</span></span>  
  
 [<span data-ttu-id="4b463-122">Analisar os influenciadores principais &#40;ferramentas de análise de tabela para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4b463-122">Analyze Key Influencers &#40;Table Analysis Tools for Excel&#41;</span></span>](analyze-key-influencers-table-analysis-tools-for-excel.md)  
  
## <a name="associate-data-mining"></a><span data-ttu-id="4b463-123">Associação (mineração de dados)</span><span class="sxs-lookup"><span data-stu-id="4b463-123">Associate (Data Mining)</span></span>  
 <span data-ttu-id="4b463-124">O assistente para **associar** cria um modelo de associação que detecta associações entre itens que aparecem em várias transações: por exemplo, na análise de cesta de mercado.</span><span class="sxs-lookup"><span data-stu-id="4b463-124">The **Associate** wizard builds an association model that detects associations between items that appear in multiple transactions: for example, in market basket analysis.</span></span>  
  
 [<span data-ttu-id="4b463-125">Assistente para associar &#40;cliente de mineração de dados para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4b463-125">Associate Wizard &#40;Data Mining Client for Excel&#41;</span></span>](associate-wizard-data-mining-client-for-excel.md)  
  
## <a name="classify-data-mining"></a><span data-ttu-id="4b463-126">Classificar (mineração de dados)</span><span class="sxs-lookup"><span data-stu-id="4b463-126">Classify (Data Mining)</span></span>  
 <span data-ttu-id="4b463-127">O **Assistente de classificação cria** um modelo de classificação que analisa os fatores que contribuíram para um resultado de destino.</span><span class="sxs-lookup"><span data-stu-id="4b463-127">The  **Classify** wizard builds a classification model that analyzes the factors that contributed to a target outcome.</span></span> <span data-ttu-id="4b463-128">Você pode usar vários algoritmos com este assistente, incluindo Árvores de Decisão, Naïve Bayes e Redes Neurais.</span><span class="sxs-lookup"><span data-stu-id="4b463-128">You can use multiple algorithms with this wizard, including Decision Trees, Naïve Bayes, and Neural Networks.</span></span>  
  
 [<span data-ttu-id="4b463-129">Assistente de classificação &#40;suplementos de mineração de dados para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4b463-129">Classify Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](classify-wizard-data-mining-add-ins-for-excel.md)  
  
## <a name="cluster-data-mining"></a><span data-ttu-id="4b463-130">Cluster (mineração de dados)</span><span class="sxs-lookup"><span data-stu-id="4b463-130">Cluster (Data Mining)</span></span>  
 <span data-ttu-id="4b463-131">O assistente de **cluster** cria um modelo de clustering que detecta grupos de linhas que compartilham características semelhantes.</span><span class="sxs-lookup"><span data-stu-id="4b463-131">The **Cluster** wizard builds a clustering model that detects groups of rows that share similar characteristics.</span></span> <span data-ttu-id="4b463-132">O clustering (às vezes chamado de *segmentação*) é uma técnica de aprendizado não supervisionada que é muito útil ao tentar entender os padrões e agrupamentos em novos dados.</span><span class="sxs-lookup"><span data-stu-id="4b463-132">Clustering (sometimes called *segmentation*) is an unsupervised learning technique that is very useful when trying to understand patterns and groupings in new data.</span></span>  
  
 <span data-ttu-id="4b463-133">O algoritmo Clustering da Microsoft dá suporte a diversas variedades do clustering K-means e de Maximização de expectativa (EM).</span><span class="sxs-lookup"><span data-stu-id="4b463-133">The Microsoft Clustering algorithm supports several varieties of both K-means and Expectation maximization (EM) clustering</span></span>  
  
 <span data-ttu-id="4b463-134">O [Assistente de Cluster &#40;suplementos de mineração de dados para&#41;do Excel ](cluster-wizard-data-mining-add-ins-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="4b463-134">[Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md).</span></span>  
  
## <a name="detect-categories-analyze"></a><span data-ttu-id="4b463-135">Detectar categorias (Analisar)</span><span class="sxs-lookup"><span data-stu-id="4b463-135">Detect Categories (Analyze)</span></span>  
 <span data-ttu-id="4b463-136">A ferramenta **detectar categorias** permite que você adicione qualquer conjunto de dados e aplique clustering para localizar agrupamentos de dados.</span><span class="sxs-lookup"><span data-stu-id="4b463-136">The **Detect Categories** tool lets you add any data set and apply clustering to find groupings of data.</span></span> <span data-ttu-id="4b463-137">É útil para encontrar semelhanças e para criar grupos para analisar ainda mais.</span><span class="sxs-lookup"><span data-stu-id="4b463-137">It's useful for finding similarities and for creating groups to further analyze.</span></span>  
  
 <span data-ttu-id="4b463-138">A ferramenta **detectar categorias** usa o algoritmo Microsoft Clustering.</span><span class="sxs-lookup"><span data-stu-id="4b463-138">The **Detect Categories** tool uses the Microsoft Clustering algorithm.</span></span>  
  
 [<span data-ttu-id="4b463-139">Detectar categorias &#40;ferramentas de análise de tabela para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4b463-139">Detect Categories &#40;Table Analysis Tools for Excel&#41;</span></span>](detect-categories-table-analysis-tools-for-excel.md)  
  
## <a name="estimate-data-mining"></a><span data-ttu-id="4b463-140">Estimar (mineração de dados)</span><span class="sxs-lookup"><span data-stu-id="4b463-140">Estimate (Data Mining)</span></span>  
 <span data-ttu-id="4b463-141">O assistente para Estimar cria um modelo de estimativa que extrai padrões de dados e usa esses padrões para prever valores numéricos contínuos, de data ou de hora.</span><span class="sxs-lookup"><span data-stu-id="4b463-141">The Estimate wizard builds an estimation model that extracts data patterns and uses the patterns to predict continuous numeric, date, or time values.</span></span> <span data-ttu-id="4b463-142">Usa o algoritmo Árvores de Decisão da [!INCLUDE[msCoName](../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b463-142">It uses the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm.</span></span>  
  
 [<span data-ttu-id="4b463-143">Assistente de estimativa &#40;suplementos de mineração de dados para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4b463-143">Estimate Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](estimate-wizard-data-mining-add-ins-for-excel.md)  
  
## <a name="fill-from-example-analyze"></a><span data-ttu-id="4b463-144">Preencher com Base no Exemplo (Analisar)</span><span class="sxs-lookup"><span data-stu-id="4b463-144">Fill From Example (Analyze)</span></span>  
 <span data-ttu-id="4b463-145">A ferramenta **preencher de exemplo** ajuda a imputar valores ausentes.</span><span class="sxs-lookup"><span data-stu-id="4b463-145">The **Fill From Example** tool helps you impute missing values.</span></span> <span data-ttu-id="4b463-146">Você fornece alguns exemplos de como deverão ser os valores ausentes e a ferramenta cria padrões com base em todos os dados da tabela, e então recomenda novos valores com base em padrões dos dados.</span><span class="sxs-lookup"><span data-stu-id="4b463-146">You provide some examples of what the missing values should be, and the tool builds patterns based on all data in the table, and then recommends new values based on patterns in the data.</span></span>  
  
 <span data-ttu-id="4b463-147">A ferramenta **preencher com exemplo** usa o algoritmo regressão logística da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4b463-147">The **Fill From Example** tool uses the Microsoft Logistic Regression algorithm.</span></span>  
  
 [<span data-ttu-id="4b463-148">Preencha com o exemplo &#40;ferramentas de análise de tabela para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4b463-148">Fill From Example &#40;Table Analysis Tools for Excel&#41;</span></span>](fill-from-example-table-analysis-tools-for-excel.md)  
  
## <a name="forecast-analyze"></a><span data-ttu-id="4b463-149">Previsão (Analisar)</span><span class="sxs-lookup"><span data-stu-id="4b463-149">Forecast (Analyze)</span></span>  
 <span data-ttu-id="4b463-150">A ferramenta de **previsão** usa dados que mudam ao longo do tempo e prevê valores futuros.</span><span class="sxs-lookup"><span data-stu-id="4b463-150">The **Forecast** tool takes data that changes over time, and predicts future values.</span></span>  
  
 <span data-ttu-id="4b463-151">A ferramenta de **previsão** usa o algoritmo Microsoft Time Series.</span><span class="sxs-lookup"><span data-stu-id="4b463-151">The **Forecast** tool uses the Microsoft Time Series algorithm.</span></span>  
  
 [<span data-ttu-id="4b463-152">Previsão de &#40;ferramentas de análise de tabela para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4b463-152">Forecast &#40;Table Analysis Tools for Excel&#41;</span></span>](forecast-table-analysis-tools-for-excel.md)  
  
## <a name="forecast-data-mining"></a><span data-ttu-id="4b463-153">Previsão (mineração de dados)</span><span class="sxs-lookup"><span data-stu-id="4b463-153">Forecast (Data Mining)</span></span>  
 <span data-ttu-id="4b463-154">O assistente de **previsão** cria um modelo de previsão que detecta padrões em uma série de células e, em seguida, prevê valores adicionais.</span><span class="sxs-lookup"><span data-stu-id="4b463-154">The **Forecast** wizard builds a forecasting model that detects patterns in a series of cells, and then forecasts additional values.</span></span>  
  
 [<span data-ttu-id="4b463-155">Assistente de previsão &#40;suplementos de mineração de dados para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4b463-155">Forecast Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](forecast-wizard-data-mining-add-ins-for-excel.md)  
  
## <a name="highlight-exceptions-analyze"></a><span data-ttu-id="4b463-156">Realçar Exceções (Analisar)</span><span class="sxs-lookup"><span data-stu-id="4b463-156">Highlight Exceptions (Analyze)</span></span>  
 <span data-ttu-id="4b463-157">A ferramenta **realçar exceções** analisa os padrões em uma tabela de dados e localiza linhas e valores que não se ajustam ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4b463-157">The **Highlight Exceptions** tool analyzes patterns in a table of data and finds rows and values that don't fit the pattern.</span></span> <span data-ttu-id="4b463-158">Então, você poderá examiná-los e corrigi-los e executar o modelo novamente, ou sinalizar valores para ação posterior.</span><span class="sxs-lookup"><span data-stu-id="4b463-158">You can then review and correct them and rerun the model, or flag values for later action.</span></span>  
  
 <span data-ttu-id="4b463-159">A ferramenta **realçar exceções** usa o algoritmo Microsoft Clustering.</span><span class="sxs-lookup"><span data-stu-id="4b463-159">The **Highlight Exceptions** tool uses the Microsoft Clustering algorithm.</span></span>  
  
 [<span data-ttu-id="4b463-160">Realçar exceções &#40;ferramentas de análise de tabela para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4b463-160">Highlight Exceptions &#40;Table Analysis Tools for Excel&#41;</span></span>](highlight-exceptions-table-analysis-tools-for-excel.md)  
  
## <a name="prediction-calculator-analyze"></a><span data-ttu-id="4b463-161">Cálculo de Previsão (Analisar)</span><span class="sxs-lookup"><span data-stu-id="4b463-161">Prediction Calculator (Analyze)</span></span>  
 <span data-ttu-id="4b463-162">Essa ferramenta cria um modelo que analisa os fatores que levam a resultados de destino e então prevê um resultado para qualquer nova entrada, com base em critérios derivados desses padrões. Também gera uma planilha de tomada de decisão interativa que permite a você a criar pontuação de novas entradas com facilidade.</span><span class="sxs-lookup"><span data-stu-id="4b463-162">This tool creates a model that analyzes the factors leading to target outcomes, and then predicts a result for any new input, based on criteria derived from these patterns It also generates an interactive decision making worksheet that lets you easily score new inputs.</span></span> <span data-ttu-id="4b463-163">Você também pode criar uma versão impressa da planilha de pontuação para uso offline.</span><span class="sxs-lookup"><span data-stu-id="4b463-163">You can also create a printed version of the scoring worksheet for offline use.</span></span>  
  
 <span data-ttu-id="4b463-164">A ferramenta de **cálculo de previsão** usa o algoritmo regressão logística da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4b463-164">The **Prediction Calculator** tool uses the Microsoft Logistic Regression algorithm.</span></span>  
  
 [<span data-ttu-id="4b463-165">Cálculo de Previsão &#40;ferramentas de análise de tabela para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4b463-165">Prediction Calculator &#40;Table Analysis Tools for Excel&#41;</span></span>](prediction-calculator-table-analysis-tools-for-excel.md)  
  
## <a name="scenario-goal-seek-analyze"></a><span data-ttu-id="4b463-166">Cenário: Metas a Atingir (Analisar)</span><span class="sxs-lookup"><span data-stu-id="4b463-166">Scenario: Goal Seek (Analyze)</span></span>  
 <span data-ttu-id="4b463-167">Na ferramenta **meta Seek** , você especifica um valor de destino e a ferramenta identifica os fatores subjacentes que devem ser alterados para atender a esse destino.</span><span class="sxs-lookup"><span data-stu-id="4b463-167">In the **Goal Seek** tool, you specify a target value, and the tool identifies the underlying factors that must change to meet that target.</span></span> <span data-ttu-id="4b463-168">Por exemplo, se você sabe que deve aumentar a satisfação da chamada em 20%, poderá solicitar ao modelo que preveja os fatores que devem mudar para que essa meta seja produzida.</span><span class="sxs-lookup"><span data-stu-id="4b463-168">For example, if you know that you must increase call satisfaction by 20%, you can ask the model to predict the factors that should change to produce that goal.</span></span>  
  
 <span data-ttu-id="4b463-169">A ferramenta **meta Seek** usa o algoritmo regressão logística da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4b463-169">The **Goal Seek** tool uses the Microsoft Logistic Regression algorithm.</span></span>  
  
 <span data-ttu-id="4b463-170">detalhes</span><span class="sxs-lookup"><span data-stu-id="4b463-170">details</span></span>  
  
 [<span data-ttu-id="4b463-171">Cenário de busca de meta &#40;ferramentas de análise de tabela para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4b463-171">Goal Seek Scenario &#40;Table Analysis Tools for Excel&#41;</span></span>](goal-seek-scenario-table-analysis-tools-for-excel.md)  
  
## <a name="scenario-what-if-scenario-analyze"></a><span data-ttu-id="4b463-172">Cenário: cenário E-Se (Analisar)</span><span class="sxs-lookup"><span data-stu-id="4b463-172">Scenario: What-If Scenario (Analyze)</span></span>  
 <span data-ttu-id="4b463-173">A ferramenta de **análise** de hipóteses complementa a ferramenta de **meta Seek** .</span><span class="sxs-lookup"><span data-stu-id="4b463-173">The **What-If Analysis** tool complements the **Goal Seek** tool.</span></span> <span data-ttu-id="4b463-174">Com essa ferramenta, você inseriu o valor que deseja alterar, e o modelo prevê se essa alteração será suficiente para obtenção do resultado desejado.</span><span class="sxs-lookup"><span data-stu-id="4b463-174">With this tool, you entered the value you want to change, and the model predicts whether that change will be sufficient to achieve the desired outcome.</span></span> <span data-ttu-id="4b463-175">Por exemplo, você poderia perguntar ao modelo para inferir se a adição de um operador de chamada extra poderia aumentar a satisfação do cliente em um ponto.</span><span class="sxs-lookup"><span data-stu-id="4b463-175">For example, you might ask the model to infer whether adding one extra call operator would increase customer satisfaction by one point.</span></span>  
  
 <span data-ttu-id="4b463-176">A ferramenta **What-If** usa o algoritmo de regressão logística da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4b463-176">The **What-If** tool uses the Microsoft Logistic Regression algorithm.</span></span>  
  
 [<span data-ttu-id="4b463-177">Cenário de hipóteses &#40;ferramentas de análise de tabela para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4b463-177">What-If Scenario &#40;Table Analysis Tools for Excel&#41;</span></span>](what-if-scenario-table-analysis-tools-for-excel.md)  
  
## <a name="shopping-basket-analysis-analyze"></a><span data-ttu-id="4b463-178">Análise da Cesta de Compras (Analisar)</span><span class="sxs-lookup"><span data-stu-id="4b463-178">Shopping Basket Analysis (Analyze)</span></span>  
 <span data-ttu-id="4b463-179">A ferramenta de **análise de cesta de compras** cria grupos de produtos que são frequentemente comprados juntos, para identificar padrões que podem ser usados na venda cruzada ou venda vertical.</span><span class="sxs-lookup"><span data-stu-id="4b463-179">The **Shopping Basket Analysis** tool creates groups of products that are frequently purchased together, to identify patterns that can be used in cross-selling or up-selling.</span></span> <span data-ttu-id="4b463-180">Também gera relatórios com base no preço e no custo de pacotes de produto relacionados, para auxiliar a tomada de decisão.</span><span class="sxs-lookup"><span data-stu-id="4b463-180">It also generates reports based on the price and cost of related product bundles, to aid in decision-making.</span></span>  
  
 <span data-ttu-id="4b463-181">Você também pode usar essa ferramenta para eventos que ocorrem juntos com frequência, fatores que levam a um diagnóstico ou qualquer outro conjunto de causas e resultados potenciais.</span><span class="sxs-lookup"><span data-stu-id="4b463-181">You can also use this tool for events that frequently occur together, factors leading to a diagnosis, or any other set of potential causes and outcomes.</span></span>  
  
 <span data-ttu-id="4b463-182">A ferramenta de **análise de cesta de compras** usa o algoritmo de associação da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4b463-182">The **Shopping Basket Analysis** tool uses the Microsoft Association algorithm.</span></span>  
  
 [<span data-ttu-id="4b463-183">Análise de cesta de compras &#40;tabela AnalysisTools para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4b463-183">Shopping Basket Analysis &#40;Table AnalysisTools for Excel&#41;</span></span>](shopping-basket-analysis-table-analysistools-for-excel.md)  
  
## <a name="see-also"></a><span data-ttu-id="4b463-184">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4b463-184">See Also</span></span>  
 <span data-ttu-id="4b463-185">[Explorando e limpando dados](exploring-and-cleaning-data.md) </span><span class="sxs-lookup"><span data-stu-id="4b463-185">[Exploring and Cleaning Data](exploring-and-cleaning-data.md) </span></span>  
 <span data-ttu-id="4b463-186">[Validando modelos e usando modelos para previsão &#40;suplementos de mineração de dados para Excel&#41;](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="4b463-186">[Validating Models and Using Models for Prediction &#40;Data Mining Add-ins for Excel&#41;](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md) </span></span>  
 [<span data-ttu-id="4b463-187">Implantando e dimensionando modelos de mineração &#40;suplementos de mineração de dados para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4b463-187">Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;</span></span>](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md)  
  
  
