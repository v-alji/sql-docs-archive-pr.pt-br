---
title: Procurar um modelo usando o Visualizador de árvore de conteúdo genérica da Microsoft | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining model content, viewing
ms.assetid: 4a5f7c51-c704-4214-b05d-21cf735e6d96
author: minewiskan
ms.author: owend
ms.openlocfilehash: 90d47262a09060a11020e50b3724753799d2d188
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583271"
---
# <a name="browse-a-model-using-the-microsoft-generic-content-tree-viewer"></a><span data-ttu-id="22abc-102">Procurar um modelo usando o Visualizador de Árvore de Conteúdo Genérica da Microsoft</span><span class="sxs-lookup"><span data-stu-id="22abc-102">Browse a Model Using the Microsoft Generic Content Tree Viewer</span></span>
  <span data-ttu-id="22abc-103">O Visualizador de Conteúdo do Modelo de Mineração Genérico da [!INCLUDE[msCoName](../../includes/msconame-md.md)] fornece informações detalhadas sobre os padrões encontrados pelo algoritmos de mineração e também fornece acesso a várias estatísticas geradas durante o processo de análise.</span><span class="sxs-lookup"><span data-stu-id="22abc-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Mining Model Content Viewer provides detailed information about the patterns found by the mining algorithm, and also provides access to various statistics generated during the analysis process.</span></span> <span data-ttu-id="22abc-104">A quantidade e o tipo de informação dependem do algoritmo usado, mas podem incluir as seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="22abc-104">The amount and type of information depends on the algorithm that was used, but can include the following categories:</span></span>  
  
-   <span data-ttu-id="22abc-105">Segmentos de dados e suas características.</span><span class="sxs-lookup"><span data-stu-id="22abc-105">Segments of data, and their characteristics.</span></span>  
  
-   <span data-ttu-id="22abc-106">Estatísticas descritivas sobre cada grupo ou sobre o conjunto de dados inteiro.</span><span class="sxs-lookup"><span data-stu-id="22abc-106">Descriptive statistics about each group or about the whole set of data.</span></span>  
  
-   <span data-ttu-id="22abc-107">O número de ramificações ou nós filho de uma árvore.</span><span class="sxs-lookup"><span data-stu-id="22abc-107">The number of branches or child nodes in a tree.</span></span>  
  
-   <span data-ttu-id="22abc-108">Cálculos, como variância e média, para um cluster ou um conjunto de dados inteiro.</span><span class="sxs-lookup"><span data-stu-id="22abc-108">Calculations, such as variance and mean, for a cluster or a whole set of data.</span></span>  
  
 <span data-ttu-id="22abc-109">Exibir essas informações pode ajudar a entender melhor os resultados da análise.</span><span class="sxs-lookup"><span data-stu-id="22abc-109">Viewing this information can help you better understand the results of your analysis.</span></span> <span data-ttu-id="22abc-110">Você também pode identificar maneiras de ajustar e, em seguida, treinar novamente seu modelo.</span><span class="sxs-lookup"><span data-stu-id="22abc-110">You can also identify ways to fine-tune, and then retrain, your model.</span></span> <span data-ttu-id="22abc-111">Ou pode decidir fazer um novo treinamento usando um outro algoritmo.</span><span class="sxs-lookup"><span data-stu-id="22abc-111">Or, you might decide to retrain by using a different algorithm.</span></span>  
  
## <a name="viewing-mining-model-content"></a><span data-ttu-id="22abc-112">Exibindo conteúdo do modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="22abc-112">Viewing Mining Model Content</span></span>  
 <span data-ttu-id="22abc-113">O Visualizador de Conteúdo Genérico da [!INCLUDE[msCoName](../../includes/msconame-md.md)] exibe as colunas, as regras, as propriedades, os atributos, os nós e outros conteúdos no *conjunto de linhas de esquema de conteúdo* do modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="22abc-113">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Viewer displays the columns, rules, properties, attributes, nodes, and other content from the *content schema rowset* of the mining model.</span></span> <span data-ttu-id="22abc-114">O conjunto de linhas de esquema de conteúdo é uma estrutura genérica de apresentação de informações detalhadas sobre o conteúdo de um modelo de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="22abc-114">The content schema rowset is a generic framework for presenting detailed information about the content of a data mining model.</span></span>  
  
 <span data-ttu-id="22abc-115">Estas informações detalhadas estão contidas em uma tabela HTML que representa os patterns, clusters ou árvores no modelo como nós.</span><span class="sxs-lookup"><span data-stu-id="22abc-115">This detailed information is contained in an HTML table that represents the patterns, clusters, or trees in the model as nodes.</span></span> <span data-ttu-id="22abc-116">Você pode clicar em cada nó e expandi-lo para ver mais detalhes, como as fórmulas ou a contagem de valores distintos para um atributo numérico.</span><span class="sxs-lookup"><span data-stu-id="22abc-116">You can click on each node and expand it to see more detail, such as the formulas or the count of distinct values for a numeric attribute.</span></span> <span data-ttu-id="22abc-117">Também pode explorar as relações filho-pai entre os nós.</span><span class="sxs-lookup"><span data-stu-id="22abc-117">You can also explore the child-parent relationships among the nodes.</span></span>  
  
 <span data-ttu-id="22abc-118">Para obter mais informações sobre o significado geral dos termos usados no conteúdo do modelo de mineração, consulte [Conteúdo do modelo de mineração  40Analysis Services – Mineração de dados&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="22abc-118">For more information about the general meaning of the terms used in the mining model content, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span> <span data-ttu-id="22abc-119">O tópico também contém links para informações sobre o conteúdo do modelo de mineração para tipos específicos de modelos.</span><span class="sxs-lookup"><span data-stu-id="22abc-119">The topic also contains links to information about mining model content for specific types of models.</span></span> <span data-ttu-id="22abc-120">Cada tipo de modelo de mineração contém informações altamente específicas do algoritmo e os padrões encontrados nos dados; portanto, é recomendável consultar o tópico de referência técnica para cada tipo de modelo para compreender bem cada tipo de modelo.</span><span class="sxs-lookup"><span data-stu-id="22abc-120">Each type of mining model contains information that is highly specific to the algorithm and the patterns found in the data, so we recommend that you consult the technical reference topic for each model type in order to fully understand each model type.</span></span>  
  
## <a name="querying-mining-model-content"></a><span data-ttu-id="22abc-121">Consultando o conteúdo do modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="22abc-121">Querying Mining Model Content</span></span>  
 <span data-ttu-id="22abc-122">As mesmas informações fornecidas pelo Visualizador de Árvore de Conteúdo Genéricas da [!INCLUDE[msCoName](../../includes/msconame-md.md)] também estão disponíveis através da consulta ao modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="22abc-122">The same information that is provided by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Tree Viewer is also available by querying the mining model.</span></span> <span data-ttu-id="22abc-123">Você pode criar consultas no conteúdo do modelo de mineração usando instruções DMX (Data Mining Extensions).</span><span class="sxs-lookup"><span data-stu-id="22abc-123">You can create queries against mining model content by using Data Mining Extensions (DMX) statements.</span></span> <span data-ttu-id="22abc-124">Por exemplo, no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], você pode realizar uma consulta de conteúdo executando a seguinte instrução DMX:</span><span class="sxs-lookup"><span data-stu-id="22abc-124">For example, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you can run a content query by executing the following DMX statement:</span></span>  
  
```  
SELECT * FROM [<mining model name>].CONTENT  
```  
  
 <span data-ttu-id="22abc-125">Para obter mais informações, consulte [Consultas de mineração de dados](data-mining-queries.md).</span><span class="sxs-lookup"><span data-stu-id="22abc-125">For more information, see [Data Mining Queries](data-mining-queries.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22abc-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="22abc-126">See Also</span></span>  
 <span data-ttu-id="22abc-127">[Visualizador de árvore de conteúdo genérica da Microsoft &#40;mineração de dados&#41;](../microsoft-generic-content-tree-viewer-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="22abc-127">[Microsoft Generic Content Tree Viewer &#40;Data Mining&#41;](../microsoft-generic-content-tree-viewer-data-mining.md) </span></span>  
 [<span data-ttu-id="22abc-128">Algoritmos de mineração de dados &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="22abc-128">Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;</span></span>](data-mining-algorithms-analysis-services-data-mining.md)  
  
  
