---
title: Mineração de dados (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], about data mining
ms.assetid: b1c912da-72f6-4d96-89c8-55a2c4f19e88
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7044ee397d457f7924d0db99dbec6659f969f104
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581621"
---
# <a name="data-mining-ssas"></a><span data-ttu-id="094f0-102">Mineração de dados (SSAS)</span><span class="sxs-lookup"><span data-stu-id="094f0-102">Data Mining (SSAS)</span></span>
  <span data-ttu-id="094f0-103">O [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] fornece uma plataforma integrada para soluções que incorporam mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="094f0-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides an integrated platform for solutions that incorporate data mining.</span></span> <span data-ttu-id="094f0-104">Você pode usar dados relacionais ou de cubo para criar soluções de business intelligence com análises preditivas.</span><span class="sxs-lookup"><span data-stu-id="094f0-104">You can use either relational or cube data to create business intelligence solutions with predictive analytics.</span></span>  
  
## <a name="benefits-of-data-mining"></a><span data-ttu-id="094f0-105">Benefícios da mineração de dados</span><span class="sxs-lookup"><span data-stu-id="094f0-105">Benefits of Data Mining</span></span>  
 <span data-ttu-id="094f0-106">A mineração de dados usa princípios estatísticos pesquisados para descobrir padrões em seus dados, ajudando-o a tomar decisões inteligentes sobre problemas complexos.</span><span class="sxs-lookup"><span data-stu-id="094f0-106">Data mining uses well-researched statistical principles to discover patterns in your data, helping you make intelligent decisions about complex problems.</span></span> <span data-ttu-id="094f0-107">Ao aplicar os algoritmos de mineração de dados a seus dados no [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , você pode prever tendências, identificar padrões, criar regras e recomendações, analisar a sequência de eventos em conjuntos de dados complexos e ter novas ideias.</span><span class="sxs-lookup"><span data-stu-id="094f0-107">By applying the data mining algorithms in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to your data, you can forecast trends, identify patterns, create rules and recommendations, analyze the sequence of events in complex data sets, and gain new insights.</span></span>  
  
 <span data-ttu-id="094f0-108">No [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], a mineração de dados é um recurso avançado, acessível e integrado com as ferramentas que muitas pessoas preferem usar para análise e relatório.</span><span class="sxs-lookup"><span data-stu-id="094f0-108">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], data mining is powerful, accessible, and integrated with the tools that many people prefer to use for analysis and reporting.</span></span> <span data-ttu-id="094f0-109">Veja os links nesta seção para obter as informações essenciais sobre mineração de dados de que você precisa para começar.</span><span class="sxs-lookup"><span data-stu-id="094f0-109">See the links in this section to get the broad background about data mining that you need to get started.</span></span>  
  
## <a name="key-data-mining-features"></a><span data-ttu-id="094f0-110">Principais recursos de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="094f0-110">Key Data Mining Features</span></span>  
 <span data-ttu-id="094f0-111">O SQL Server fornece os recursos a seguir ao dar suporte a soluções de mineração de dados integradas:</span><span class="sxs-lookup"><span data-stu-id="094f0-111">SQL Server provides the following features in support of integrated data mining solutions:</span></span>  
  
-   <span data-ttu-id="094f0-112">Várias fontes de dados: você não tem que criar um data warehouse ou um cubo OLAP para fazer mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="094f0-112">Multiple data sources: You do not have to create a data warehouse or an OLAP cube to do data mining.</span></span> <span data-ttu-id="094f0-113">Você pode usar dados de tabelas de provedores externos, de planilhas e até mesmo de arquivos de texto.</span><span class="sxs-lookup"><span data-stu-id="094f0-113">You can use tabular data from external providers, spreadsheets, and even text files.</span></span> <span data-ttu-id="094f0-114">Também é possível minerar facilmente cubos OLAP criados no [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="094f0-114">You can also easily mine OLAP cubes created in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="094f0-115">No entanto, você não pode usar dados de um banco de dados na memória.</span><span class="sxs-lookup"><span data-stu-id="094f0-115">However, you cannot use data from an in-memory database.</span></span>  
  
-   <span data-ttu-id="094f0-116">Limpeza de dados integrada, gerenciamento de dados e ETL: Data Quality Services fornecem ferramentas avançadas para criação de perfil e limpar dados.</span><span class="sxs-lookup"><span data-stu-id="094f0-116">Integrated data cleansing, data management, and ETL: Data Quality Services provides advanced tools for profiling and cleansing data.</span></span> <span data-ttu-id="094f0-117">O Integration Services pode ser usado para criar processos ETL para limpar dados e também para criar, processar, treinar e atualizar modelos.</span><span class="sxs-lookup"><span data-stu-id="094f0-117">Integration Services can be used to build ETL processes for cleaning data, and also for building, processing, training, and updating models.</span></span>  
  
-   <span data-ttu-id="094f0-118">Vários algoritmos personalizáveis: além de fornecer algoritmos como clustering, redes neurais e árvores de decisões, a plataforma dá suporte a desenvolvimento de seus próprios algoritmos de plug-in personalizados.</span><span class="sxs-lookup"><span data-stu-id="094f0-118">Multiple customizable algorithms: In addition to providing algorithms such as clustering, neural networks, and decisions trees, the platform supports development of your own custom plug-in algorithms.</span></span>  
  
-   <span data-ttu-id="094f0-119">Infraestrutura de testes de modelo: teste seus modelos e conjuntos de dados usando ferramentas estatísticas importantes como validação cruzada, matrizes de classificação, gráficos de comparação de precisão e dispersões.</span><span class="sxs-lookup"><span data-stu-id="094f0-119">Model testing infrastructure: Test your models and data sets using important statistical tools as cross-validation, classification matrices, lift charts, and scatter plots.</span></span> <span data-ttu-id="094f0-120">Crie e gerencie conjuntos de teste e treinamento com facilidade.</span><span class="sxs-lookup"><span data-stu-id="094f0-120">Easily create and manage testing and training sets.</span></span>  
  
-   <span data-ttu-id="094f0-121">Consulta e detalhamento: crie consultas de previsão, recupere padrões modelo e estatísticas e detalhe os dados de caso.</span><span class="sxs-lookup"><span data-stu-id="094f0-121">Querying and drillthrough: Create prediction queries, retrieve model patterns and statistics, and drill through to case data.</span></span>  
  
-   <span data-ttu-id="094f0-122">Ferramentas de cliente: além dos estúdios de desenvolvimento e design fornecidos pelo SQL Server, você pode usar os Suplementos de Mineração de Dados para Excel para criar, consultar e procurar modelos.</span><span class="sxs-lookup"><span data-stu-id="094f0-122">Client tools: In addition to the development and design studios provided by SQL Server, you can use the Data Mining Add-ins for Excel to create, query, and browse models.</span></span> <span data-ttu-id="094f0-123">Ou crie clientes personalizados, inclusive serviços Web.</span><span class="sxs-lookup"><span data-stu-id="094f0-123">Or, create custom clients, including Web services.</span></span>  
  
-   <span data-ttu-id="094f0-124">Suporte a linguagem de scripts e API gerenciada: todos os objetos de mineração de dados são completamente programáveis.</span><span class="sxs-lookup"><span data-stu-id="094f0-124">Scripting language support and managed API: All data mining objects are fully programmable.</span></span> <span data-ttu-id="094f0-125">Gerar scripts é possível por meio do MDX, XMLA ou as extensões de PowerShell para o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="094f0-125">Scripting is possible through MDX, XMLA, or the PowerShell extensions for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="094f0-126">Use a linguagem DMX (Data Mining Extensions) para consultar e gerar script rapidamente.</span><span class="sxs-lookup"><span data-stu-id="094f0-126">Use the Data Mining Extensions (DMX) language for fast querying and scripting.</span></span>  
  
-   <span data-ttu-id="094f0-127">Segurança e implantação: fornece segurança baseada em função por meio do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], inclusive permissões separadas para drillthrough para modelar e estruturar dados.</span><span class="sxs-lookup"><span data-stu-id="094f0-127">Security and deployment: Provides role-based security through [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], including separate permissions for drillthrough to model and structure data.</span></span> <span data-ttu-id="094f0-128">Implantação fácil de modelos para outros servidores, de forma que os usuários possam acessar os padrões ou executar previsões</span><span class="sxs-lookup"><span data-stu-id="094f0-128">Easy deployment of models to other servers, so that users can access the patterns or perform predictions</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="094f0-129">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="094f0-129">In This Section</span></span>  
 <span data-ttu-id="094f0-130">Os tópicos nesta seção apresentam os recursos principais de Mineração de Dados do SQL Server e tarefas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="094f0-130">The topics in this section introduce the principal features of SQL Server Data Mining and related tasks.</span></span>  
  
-   [<span data-ttu-id="094f0-131">Conceitos de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="094f0-131">Data Mining Concepts</span></span>](data-mining-concepts.md)  
  
-   [<span data-ttu-id="094f0-132">Algoritmos de mineração de dados &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="094f0-132">Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;</span></span>](data-mining-algorithms-analysis-services-data-mining.md)  
  
-   [<span data-ttu-id="094f0-133">Estruturas de Mineração &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="094f0-133">Mining Structures &#40;Analysis Services - Data Mining&#41;</span></span>](mining-structures-analysis-services-data-mining.md)  
  
-   [<span data-ttu-id="094f0-134">Modelos de mineração &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="094f0-134">Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-models-analysis-services-data-mining.md)  
  
-   [<span data-ttu-id="094f0-135">Teste e validação &#40;Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="094f0-135">Testing and Validation &#40;Data Mining&#41;</span></span>](testing-and-validation-data-mining.md)  
  
-   [<span data-ttu-id="094f0-136">Consultas de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="094f0-136">Data Mining Queries</span></span>](data-mining-queries.md)  
  
-   [<span data-ttu-id="094f0-137">Soluções de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="094f0-137">Data Mining Solutions</span></span>](data-mining-solutions.md)  
  
-   [<span data-ttu-id="094f0-138">Ferramentas de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="094f0-138">Data Mining Tools</span></span>](data-mining-tools.md)  
  
-   [<span data-ttu-id="094f0-139">Arquitetura de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="094f0-139">Data Mining Architecture</span></span>](data-mining-architecture.md)  
  
-   [<span data-ttu-id="094f0-140">Visão geral de segurança &#40;Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="094f0-140">Security Overview &#40;Data Mining&#41;</span></span>](security-overview-data-mining.md)  
  
  
