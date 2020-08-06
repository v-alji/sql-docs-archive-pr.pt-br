---
title: Designer de mineração de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], structure
- mining structures [Analysis Services], modifying
- data mining editor [Analysis Services]
- Data Mining Designer
- data mining [Analysis Services], modifying
ms.assetid: 2540db5b-2bf3-4b6c-87c8-79c48d71acce
author: minewiskan
ms.author: owend
ms.openlocfilehash: 820cde158dfabff525081060369daace0e83c8dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569732"
---
# <a name="data-mining-designer"></a><span data-ttu-id="b4049-102">Data Mining Designer</span><span class="sxs-lookup"><span data-stu-id="b4049-102">Data Mining Designer</span></span>
  <span data-ttu-id="b4049-103">O designer de mineração de dados é o ambiente primário no qual você trabalha com modelos de mineração no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b4049-103">Data Mining Designer is the primary environment in which you work with mining models in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="b4049-104">Você pode acessar o designer selecionando uma estrutura de mineração existente ou usando o Assistente de Mineração de Dados para criar uma nova estrutura e um novo modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="b4049-104">You can access the designer either by selecting an existing mining structure, or by using the Data Mining Wizard to create a new mining structure and mining model.</span></span> <span data-ttu-id="b4049-105">É possível usar o Designer de Mineração de Dados para executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="b4049-105">You can use Data Mining Designer to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="b4049-106">Modificar a estrutura de mineração e o modelo de mineração criados inicialmente pelo Assistente de Mineração de Dados.</span><span class="sxs-lookup"><span data-stu-id="b4049-106">Modify the mining structure and the mining model that were initially created by the Data Mining Wizard.</span></span>  
  
-   <span data-ttu-id="b4049-107">Criar novos modelos baseados em uma estrutura de mineração existente.</span><span class="sxs-lookup"><span data-stu-id="b4049-107">Create new models based on an existing mining structure.</span></span>  
  
-   <span data-ttu-id="b4049-108">Treinar e procurar modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="b4049-108">Train and browse mining models.</span></span>  
  
-   <span data-ttu-id="b4049-109">Comparar modelos usando gráficos de exatidão.</span><span class="sxs-lookup"><span data-stu-id="b4049-109">Compare models by using accuracy charts.</span></span>  
  
-   <span data-ttu-id="b4049-110">Criar consultas de previsão baseadas em modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="b4049-110">Create prediction queries based on mining models.</span></span>  
  
## <a name="mining-structure-tab"></a><span data-ttu-id="b4049-111">Guia Estrutura de Mineração</span><span class="sxs-lookup"><span data-stu-id="b4049-111">Mining Structure Tab</span></span>  
 <span data-ttu-id="b4049-112">Use a guia **Estrutura de Mineração** para adicionar colunas e modificar as propriedades de uma estrutura de mineração existente.</span><span class="sxs-lookup"><span data-stu-id="b4049-112">Use the **Mining Structure** tab to add columns and modify the properties of an existing mining structure.</span></span> <span data-ttu-id="b4049-113">As seguintes tarefas e tópicos fornecem mais informações sobre o trabalho com estruturas de mineração:</span><span class="sxs-lookup"><span data-stu-id="b4049-113">The following tasks and topics provide more information about working with mining structures:</span></span>  
  
 [<span data-ttu-id="b4049-114">Estruturas de Mineração &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="b4049-114">Mining Structures &#40;Analysis Services - Data Mining&#41;</span></span>](mining-structures-analysis-services-data-mining.md)  
  
 [<span data-ttu-id="b4049-115">Tarefas e instruções da estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="b4049-115">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
## <a name="mining-models-tab"></a><span data-ttu-id="b4049-116">Guia Modelos de Mineração</span><span class="sxs-lookup"><span data-stu-id="b4049-116">Mining Models Tab</span></span>  
 <span data-ttu-id="b4049-117">Use a guia **Modelos de Mineração** para administrar modelos de mineração existentes e criar novos modelos.</span><span class="sxs-lookup"><span data-stu-id="b4049-117">Use the **Mining Models** tab to manage existing mining models and to create new models.</span></span> <span data-ttu-id="b4049-118">Os modelos de mineração sempre se baseiam em uma estrutura de mineração existente.</span><span class="sxs-lookup"><span data-stu-id="b4049-118">Mining models are always based on an existing mining structure .</span></span>  
  
 <span data-ttu-id="b4049-119">Na guia **Modelos de Mineração** , é possível alterar o tipo de algoritmo, adicionar ou remover colunas associadas à estrutura de modelo, ajustar as propriedades de coluna específicas do algoritmo, especificar o uso da coluna de modelo de mineração e ajustar os parâmetros de algoritmo associados ao modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="b4049-119">In the **Mining Models** tab, you can change the algorithm type, add or remove columns that are associated with the model structure, adjust algorithm-specific column properties, specify the mining model column usage, and adjust algorithm parameters that are associated with the mining model.</span></span> <span data-ttu-id="b4049-120">Também é possível processar a estrutura de mineração junto com os modelos selecionados ou todos os modelos associados.</span><span class="sxs-lookup"><span data-stu-id="b4049-120">You can also process the mining structure together with selected models or with all the associated models.</span></span>  
  
 <span data-ttu-id="b4049-121">Consulte os seguintes tópicos para obter mais informações sobre o trabalho com modelos de mineração:</span><span class="sxs-lookup"><span data-stu-id="b4049-121">See the following topics for more information about working with mining models:</span></span>  
  
 [<span data-ttu-id="b4049-122">Modelos de mineração &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="b4049-122">Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-models-analysis-services-data-mining.md)  
  
 [<span data-ttu-id="b4049-123">Tarefas e instruções do modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="b4049-123">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
## <a name="mining-model-viewer-tab"></a><span data-ttu-id="b4049-124">Guia Visualizador do Modelo de Mineração</span><span class="sxs-lookup"><span data-stu-id="b4049-124">Mining Model Viewer Tab</span></span>  
 <span data-ttu-id="b4049-125">Use a guia **Visualizador do Modelo de Mineração** para explorar seus modelos de mineração visualmente.</span><span class="sxs-lookup"><span data-stu-id="b4049-125">Use the **Mining Model Viewer** tab to visually explore your mining models.</span></span> <span data-ttu-id="b4049-126">Cada modelo de mineração é associado a um visualizador personalizado que exibe o conteúdo específico desse modelo.</span><span class="sxs-lookup"><span data-stu-id="b4049-126">Each mining model is associated with a custom viewer that displays content that is specific to that model.</span></span> <span data-ttu-id="b4049-127">Você também pode exibir o conteúdo de modelo de mineração usando o visualizador de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="b4049-127">You can also view mining model content by using the content viewer.</span></span>  
  
 <span data-ttu-id="b4049-128">Consulte os seguintes tópicos para obter mais informações sobre a exploração de modelos de mineração com os visualizadores de mineração de dados:</span><span class="sxs-lookup"><span data-stu-id="b4049-128">See the following topics for more information about exploring mining models with the data mining viewers:</span></span>  
  
 [<span data-ttu-id="b4049-129">Visualizadores do Modelo de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="b4049-129">Data Mining Model Viewers</span></span>](data-mining-model-viewers.md)  
  
 [<span data-ttu-id="b4049-130">Tarefas e instruções do visualizador do modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="b4049-130">Mining Model Viewer Tasks and How-tos</span></span>](mining-model-viewer-tasks-and-how-tos.md)  
  
## <a name="mining-accuracy-chart-tab"></a><span data-ttu-id="b4049-131">Guia Gráfico de Precisão de Mineração</span><span class="sxs-lookup"><span data-stu-id="b4049-131">Mining Accuracy Chart Tab</span></span>  
 <span data-ttu-id="b4049-132">Use a guia **Gráfico de Precisão de Mineração** para testar a precisão de previsão de um único modelo de mineração ou comparar a eficiência de vários modelos de mineração contidos em uma estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="b4049-132">Use the **Mining Accuracy Chart** tab to test the predictive accuracy of a single mining model, or to compare the effectiveness of multiple mining models contained within a mining structure.</span></span> <span data-ttu-id="b4049-133">A guia contém ferramentas para filtrar dados, selecionar modelos de mineração e exibir os resultados em um gráfico de comparação de precisão, gráfico de ganho ou matriz de classificação.</span><span class="sxs-lookup"><span data-stu-id="b4049-133">The tab contains tools for filtering the data, selecting mining models, and displaying the results in a lift chart, profit chart, or classification matrix.</span></span>  
  
 <span data-ttu-id="b4049-134">Consulte os seguintes tópicos para obter mais informações sobre o teste e a validação de modelos de mineração:</span><span class="sxs-lookup"><span data-stu-id="b4049-134">See the following topics for more information about testing and validating mining models:</span></span>  
  
 [<span data-ttu-id="b4049-135">Teste e validação &#40;Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="b4049-135">Testing and Validation &#40;Data Mining&#41;</span></span>](testing-and-validation-data-mining.md)  
  
 [<span data-ttu-id="b4049-136">Tarefas de teste e validação e instruções &#40;Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="b4049-136">Testing and Validation Tasks and How-tos &#40;Data Mining&#41;</span></span>](testing-and-validation-tasks-and-how-tos-data-mining.md)  
  
## <a name="mining-model-prediction-tab"></a><span data-ttu-id="b4049-137">Guia Previsão do Modelo de Mineração</span><span class="sxs-lookup"><span data-stu-id="b4049-137">Mining Model Prediction Tab</span></span>  
 <span data-ttu-id="b4049-138">A guia **Previsão do Modelo de Mineração** inclui o Construtor de Consultas de Previsão, que pode ser usado para criar uma consulta de previsão de extensões DMX.</span><span class="sxs-lookup"><span data-stu-id="b4049-138">The **Mining Model Prediction** tab includes Prediction Query Builder, which you can use to create a Data Mining Extensions (DMX) prediction query.</span></span> <span data-ttu-id="b4049-139">A guia contém ferramentas para especificar modelos de mineração e tabelas de entrada, mapear as colunas no modelo de mineração para colunas na tabela de entrada, adicionar funções a uma consulta e especificar critérios para cada coluna.</span><span class="sxs-lookup"><span data-stu-id="b4049-139">The tab contains tools for specifying mining models and input tables, mapping the columns in the mining model to columns in the input table, adding functions to a query, and specifying criteria for each column.</span></span>  
  
 <span data-ttu-id="b4049-140">Depois de criar uma consulta, você pode usar diferentes exibições na guia para exibir os resultados da consulta e modificar a consulta manualmente.</span><span class="sxs-lookup"><span data-stu-id="b4049-140">After you design a query, you can use different views in the tab to display the results of the query and to modify the query manually.</span></span> <span data-ttu-id="b4049-141">Você também pode salvar os resultados da consulta em uma tabela de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b4049-141">You can also save the results of the query to a table in a database.</span></span>  
  
 <span data-ttu-id="b4049-142">Consulte os seguintes tópicos para obter mais informações sobre a criação de consultas de mineração de dados:</span><span class="sxs-lookup"><span data-stu-id="b4049-142">See the following topics for more information about creating data mining queries:</span></span>  
  
 [<span data-ttu-id="b4049-143">Consultas de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="b4049-143">Data Mining Queries</span></span>](data-mining-queries.md)  
  
 [<span data-ttu-id="b4049-144">Tarefas e instruções de consulta de Data Mining</span><span class="sxs-lookup"><span data-stu-id="b4049-144">Data Mining Query Tasks and How-tos</span></span>](data-mining-query-tasks-and-how-tos.md)  
  
## <a name="see-also"></a><span data-ttu-id="b4049-145">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b4049-145">See Also</span></span>  
 [<span data-ttu-id="b4049-146">Soluções de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="b4049-146">Data Mining Solutions</span></span>](data-mining-solutions.md)  
  
  
