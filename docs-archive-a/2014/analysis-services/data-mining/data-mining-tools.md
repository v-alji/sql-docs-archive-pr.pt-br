---
title: Ferramentas de mineração de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- tools [Analysis Services]
- mining models [Analysis Services], tools
- data mining [Analysis Services], tools
- data mining [Analysis Services], development
ms.assetid: 003ada6a-0bcd-4f16-8c34-1a9ffc75cd2c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4be2f343f0fb7969f76b63ec1eb1677c1c9e589f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583909"
---
# <a name="data-mining-tools"></a><span data-ttu-id="be4ad-102">Ferramentas de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="be4ad-102">Data Mining Tools</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="be4ad-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] fornece as seguintes ferramentas que você pode usar para criar soluções de Data Mining:</span><span class="sxs-lookup"><span data-stu-id="be4ad-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides the following tools that you can use to create data mining solutions:</span></span>  
  
-   <span data-ttu-id="be4ad-104">O **Assistente de Mineração de Dados** no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] facilita a criação de estruturas e modelos de mineração usando fontes de dados relacionais ou dados multidimensionais em cubos.</span><span class="sxs-lookup"><span data-stu-id="be4ad-104">The **Data Mining Wizard** in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] makes it easy to create mining structures and mining models, using either relational data sources or multidimensional data in cubes.</span></span>  
  
     <span data-ttu-id="be4ad-105">No assistente, você escolhe dados para usar e em seguida aplica técnicas específicas de mineração de dados como clustering, redes neurais ou modelagem de série temporal.</span><span class="sxs-lookup"><span data-stu-id="be4ad-105">In the wizard, you choose data to use, and then apply specific data mining techniques, such as clustering, neural networks, or time series modeling.</span></span>  
  
-   <span data-ttu-id="be4ad-106">Os**visualizadores de modelos** são fornecidos no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], para explorar seus modelos de mineração depois que são criados.</span><span class="sxs-lookup"><span data-stu-id="be4ad-106">**Model viewers** are provided in both [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], for exploring your mining models after they are created.</span></span>  <span data-ttu-id="be4ad-107">Você pode procurar modelos usando visualizadores feitos especialmente para cada algoritmo ou se aprofundar mais na análise usando o visualizador de conteúdo do modelo.</span><span class="sxs-lookup"><span data-stu-id="be4ad-107">You can browse models using viewers tailored to each algorithm, or go deeper into analysis by using the model content viewer.</span></span>  
  
-   <span data-ttu-id="be4ad-108">O **Construtor de Consultas de Previsão** é fornecido no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] para ajudá-lo a criar consultas de previsão.</span><span class="sxs-lookup"><span data-stu-id="be4ad-108">The **Prediction Query Builder** is provided in both [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to help you create prediction queries.</span></span> <span data-ttu-id="be4ad-109">Você também pode testar a precisão de modelos em um conjunto de dados de validação ou dados externos, ou usar validação cruzada para avaliar a qualidade de seu conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="be4ad-109">You can also test the accuracy of models against a holdout data set or external data, or use cross-validation to assess the quality of your data set.</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="be4ad-110">é a interface onde você gerencia as soluções de mineração de dados existentes que foram implantadas em uma instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="be4ad-110">is the interface where you manage existing data mining solutions that have been deployed to an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="be4ad-111">Você pode reprocessar estruturas e modelos para atualizar os dados neles.</span><span class="sxs-lookup"><span data-stu-id="be4ad-111">You can reprocess structures and models to update the data in them.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="be4ad-112">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]contém ferramentas que você pode usar para limpar dados, automatizar tarefas como criar previsões e atualizar modelos e criar soluções de mineração de texto.</span><span class="sxs-lookup"><span data-stu-id="be4ad-112">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] contains tools that you can use to clean data, to automate tasks such as creating predictions and updating models, and to create text mining solutions.</span></span>  
  
 <span data-ttu-id="be4ad-113">As seções a seguir oferecem mais informações sobre as ferramentas de mineração de dados no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="be4ad-113">The following sections provide more information about the data mining tools in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="data-mining-wizard"></a><span data-ttu-id="be4ad-114">Assistente de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="be4ad-114">Data Mining Wizard</span></span>  
 <span data-ttu-id="be4ad-115">Use o Assistente de Mineração de Dados para começar a criar soluções de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="be4ad-115">Use the Data Mining Wizard to get started creating data mining solutions.</span></span> <span data-ttu-id="be4ad-116">O assistente é fácil e rápido, e foi criado para guiá-lo no processo de criação de uma estrutura de mineração de dados e um modelo de mineração inicial relacionado; além disso, inclui as tarefas de seleção de um tipo de algoritmo e uma fonte de dados, bem como de definição dos dados de caso usados para a análise.</span><span class="sxs-lookup"><span data-stu-id="be4ad-116">The wizard is quick and easy, and guides you through the process of creating a data mining structure and an initial related mining model, and includes the tasks of selecting an algorithm type and a data source, and defining the case data used for analysis.</span></span>  
  
 <span data-ttu-id="be4ad-117">**Para obter mais informações:** [Assistente de Mineração de Dados &#40;Analysis Services – Mineração de dados&#41;](data-mining-wizard-analysis-services-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="be4ad-117">**For More Information:** [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-analysis-services-data-mining.md)</span></span>  
  
## <a name="data-mining-designer"></a><span data-ttu-id="be4ad-118">Data Mining Designer</span><span class="sxs-lookup"><span data-stu-id="be4ad-118">Data Mining Designer</span></span>  
 <span data-ttu-id="be4ad-119">Após ter criado uma estrutura de mineração e um modelo de mineração usando o Assistente de Mineração de Dados, você pode utilizar o Designer de Mineração de Dados do [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] ou [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para trabalhar com modelos e estruturas existentes.</span><span class="sxs-lookup"><span data-stu-id="be4ad-119">After you have created a mining structure and mining model by using the Data Mining Wizard, you can use the Data Mining Designer from either [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to work with existing models and structures.</span></span>  
  
 <span data-ttu-id="be4ad-120">O designer inclui ferramentas para estas tarefas:</span><span class="sxs-lookup"><span data-stu-id="be4ad-120">The designer includes tools for these tasks:</span></span>  
  
-   <span data-ttu-id="be4ad-121">Modifique as propriedades de estruturas de mineração, adicione colunas e crie aliases de coluna, altere o método de compartimento ou a distribuição de valores esperada.</span><span class="sxs-lookup"><span data-stu-id="be4ad-121">Modify the properties of mining structures, add columns and create column aliases, change the binning method or expected distribution of values.</span></span>  
  
-   <span data-ttu-id="be4ad-122">Adicione novos modelos a uma estrutura existente; copie modelos, altere as propriedades do modelo ou metadados, ou defina filtros em um modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="be4ad-122">Add new models to an existing structure; copy models, change model properties or metadata, or define filters on a mining model.</span></span>  
  
-   <span data-ttu-id="be4ad-123">Procure os padrões e as regras dentro do modelo; explore associações ou árvores de decisão.</span><span class="sxs-lookup"><span data-stu-id="be4ad-123">Browse the patterns and rules within the model; explore associations or decision trees.</span></span> <span data-ttu-id="be4ad-124">Obter estatísticas detalhadas sobre</span><span class="sxs-lookup"><span data-stu-id="be4ad-124">Get detailed statistics about</span></span>  
  
     <span data-ttu-id="be4ad-125">Os visualizadores padrão são fornecidos para cada momento diferente do modelo, para ajudá-lo a analisar seus dados e explorar os padrões revelados pela mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="be4ad-125">Custom viewers are provided for each different time of model, to help you analyze your data and explore the patterns revealed by data mining.</span></span>  
  
-   <span data-ttu-id="be4ad-126">Valide modelos criando gráficos de comparação de precisão ou analisando a curva de lucro para modelos.</span><span class="sxs-lookup"><span data-stu-id="be4ad-126">Validate models by creating lift charts, or analyzing the profit curve for models.</span></span> <span data-ttu-id="be4ad-127">Compare modelos usando matrizes de classificação ou valide um conjunto de dados e seus modelos usando validação cruzada.</span><span class="sxs-lookup"><span data-stu-id="be4ad-127">Compare models using classification matrices, or validate a data set and its models by using cross-validation.</span></span>  
  
-   <span data-ttu-id="be4ad-128">Crie previsões e consultas de conteúdo em modelos de mineração existentes.</span><span class="sxs-lookup"><span data-stu-id="be4ad-128">Create predictions and content queries against existing mining models.</span></span> <span data-ttu-id="be4ad-129">Crie consultas únicas ou configure consultas para gerar previsões para tabelas inteiras de dados externos.</span><span class="sxs-lookup"><span data-stu-id="be4ad-129">Build one-off queries, or set up queries to generate predictions for entire tables of external data.</span></span>  
  
 <span data-ttu-id="be4ad-130">**Para obter mais informações:** [Designer de Mineração de Dados](data-mining-designer.md)</span><span class="sxs-lookup"><span data-stu-id="be4ad-130">**For More Information:** [Data Mining Designer](data-mining-designer.md)</span></span>  
  
## <a name="sql-server-management-studio"></a><span data-ttu-id="be4ad-131">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="be4ad-131">SQL Server Management Studio</span></span>  
 <span data-ttu-id="be4ad-132">Depois que você criar e implantar modelos de mineração em um servidor, pode usar o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para gerenciar o banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que hospeda os objetos de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="be4ad-132">After you create and deploy mining models to a server, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to manage the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database that hosts the data mining objects.</span></span> <span data-ttu-id="be4ad-133">Você também pode continuar executando tarefas que usam o modelo, como explorar os modelos, processar novos dados e criar previsões.</span><span class="sxs-lookup"><span data-stu-id="be4ad-133">You can also continue to perform tasks that use the model, such as exploring the models, processing new data, and creating predictions.</span></span>  
  
 [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] <span data-ttu-id="be4ad-134">também contém editores de consulta que você pode usar para criar e executar consultas de extensões DMX ou para trabalhar com objetos de mineração de dados usando XMLA.</span><span class="sxs-lookup"><span data-stu-id="be4ad-134">also contains query editors that you can use to design and execute Data Mining Extensions (DMX) queries, or ot work with data mining objects by using XMLA.</span></span>  
  
## <a name="integration-services-data-mining-tasks-and-transformations"></a><span data-ttu-id="be4ad-135">Tarefas e transformações de serviços de mineração de dados de integração</span><span class="sxs-lookup"><span data-stu-id="be4ad-135">Integration Services Data Mining Tasks and Transformations</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="be4ad-136">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]fornece muitos componentes que dão suporte a data mining.</span><span class="sxs-lookup"><span data-stu-id="be4ad-136">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides many components that support data mining.</span></span>  
  
 <span data-ttu-id="be4ad-137">Algumas ferramentas no [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] são criadas para ajudar a automatizar tarefas comuns de mineração de dados, incluindo previsão, criação de modelo e processamento.</span><span class="sxs-lookup"><span data-stu-id="be4ad-137">Some tools in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] are designed to help automate common data mining tasks, including prediction, model building, and processing.</span></span> <span data-ttu-id="be4ad-138">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="be4ad-138">For example:</span></span>  
  
-   <span data-ttu-id="be4ad-139">Crie um pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que automaticamente atualiza o modelo toda vez que o conjunto de dados é atualizado com novos clientes</span><span class="sxs-lookup"><span data-stu-id="be4ad-139">Create an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that automatically updates the model every time the dataset is updated with new customers</span></span>  
  
-   <span data-ttu-id="be4ad-140">Execute a segmentação personalizada ou amostragem personalizada de registros de casos.</span><span class="sxs-lookup"><span data-stu-id="be4ad-140">Perform custom segmentation or custom sampling of case records.</span></span>  
  
-   <span data-ttu-id="be4ad-141">Automaticamente gere modelos passados em parâmetros.</span><span class="sxs-lookup"><span data-stu-id="be4ad-141">Automatically generate models passed on parameters.</span></span>  
  
 <span data-ttu-id="be4ad-142">Porém, você também pode usar a mineração de dados em um fluxo de trabalho de pacote, como uma entrada para outros processos.</span><span class="sxs-lookup"><span data-stu-id="be4ad-142">However, you can also use data mining in a package workflow, as an input to other processes.</span></span> <span data-ttu-id="be4ad-143">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="be4ad-143">For example:</span></span>  
  
-   <span data-ttu-id="be4ad-144">Use valores de probabilidade gerados pelo modelo para pesar pontuações para mineração de texto ou outras tarefas de classificação.</span><span class="sxs-lookup"><span data-stu-id="be4ad-144">Use probability values generated by the model to weight scores for text mining or other classification tasks.</span></span>  
  
-   <span data-ttu-id="be4ad-145">Automaticamente gere previsões com base em dados anteriores e use esses valores para avaliar a validade de novos dados.</span><span class="sxs-lookup"><span data-stu-id="be4ad-145">Automatically generate predictions based on prior data and use those values to assess the validity of new data.</span></span>  
  
-   <span data-ttu-id="be4ad-146">Usando regressão logística para segmentar clientes de entrada por risco.</span><span class="sxs-lookup"><span data-stu-id="be4ad-146">Using logistic regression to segment incoming customers by risk.</span></span>  
  
 <span data-ttu-id="be4ad-147">**Para obter mais informações:** [Projetos relacionados a soluções de mineração de dados](data-mining-solutions.md)</span><span class="sxs-lookup"><span data-stu-id="be4ad-147">**For More Information:** [Related Projects for Data Mining Solutions](data-mining-solutions.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be4ad-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="be4ad-148">See Also</span></span>  
 <span data-ttu-id="be4ad-149">[Referência de&#41; &#40;DMX de extensões de mineração de dados](/sql/dmx/data-mining-extensions-dmx-reference) </span><span class="sxs-lookup"><span data-stu-id="be4ad-149">[Data Mining Extensions &#40;DMX&#41; Reference](/sql/dmx/data-mining-extensions-dmx-reference) </span></span>  
 <span data-ttu-id="be4ad-150">[Tarefas e instruções do modelo de mineração](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="be4ad-150">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="be4ad-151">[Tarefas e instruções do Visualizador do modelo de mineração](mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="be4ad-151">[Mining Model Viewer Tasks and How-tos](mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="be4ad-152">Soluções de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="be4ad-152">Data Mining Solutions</span></span>](data-mining-solutions.md)  
  
  
