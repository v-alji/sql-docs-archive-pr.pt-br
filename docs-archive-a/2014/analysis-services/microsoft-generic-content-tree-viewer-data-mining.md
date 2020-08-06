---
title: Visualizador de árvore de conteúdo genérica da Microsoft (mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.contentviewer.f1
ms.assetid: 751b4393-f6fd-48c1-bcef-bdca589ce34c
author: minewiskan
ms.author: owend
ms.openlocfilehash: b0dab06d6af8f2c5af029d9ce831f518faa4067e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684944"
---
# <a name="microsoft-generic-content-tree-viewer-data-mining"></a><span data-ttu-id="892c4-102">Visualizador de árvore de conteúdo genérica da Microsoft (Mineração de Dados)</span><span class="sxs-lookup"><span data-stu-id="892c4-102">Microsoft Generic Content Tree Viewer (Data Mining)</span></span>
  <span data-ttu-id="892c4-103">O **Visualizador de Árvore de Conteúdo Genérica da Microsoft** exibe informações detalhadas sobre o conteúdo de um modo de mineração de dados em um formato de tabela HTML padronizado.</span><span class="sxs-lookup"><span data-stu-id="892c4-103">The **Microsoft Generic Content Tree Viewer** displays detailed information about the contents of a data mining mode in a standardized HTML table format.</span></span> <span data-ttu-id="892c4-104">Esta exibição é útil porque expõe a estrutura subjacente do modelo, assim como detalhes sobre coeficientes, a distribuição de valores e muito mais.</span><span class="sxs-lookup"><span data-stu-id="892c4-104">This view is useful because it exposes the underlying structure of the model, as well details about coefficients, the distribution of values, and much more.</span></span>  
  
 <span data-ttu-id="892c4-105">O conteúdo atual exibido na tabela varia dependendo do algoritmo usado e podem incluir colunas, regras, propriedades, atributos, nós e fórmulas.</span><span class="sxs-lookup"><span data-stu-id="892c4-105">The actual content displayed in the table varies depending on the algorithm that was used and might include columns, rules, properties, attributes, nodes, and formulas.</span></span> <span data-ttu-id="892c4-106">Para obter mais informações sobre o conteúdo do modelo e sobre como interpretar as informações de cada tipo de modelo, consulte [Conteúdo do modelo de mineração &#40;Analysis Services – Mineração de Dados&#41;](data-mining/mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="892c4-106">For more information about model content, and how to interpret the information for each model type, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](data-mining/mining-model-content-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="892c4-107">As informações exibidas no visualizador usam uma estrutura comum que é baseada no conjunto de linhas do esquema de conteúdo dos modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="892c4-107">The information that is displayed in the viewer uses a common structure that is based on the content schema rowset for mining models.</span></span> <span data-ttu-id="892c4-108">O conjunto de linhas do esquema de conteúdo é uma estrutura genérica para armazenar padrões, estatísticas e outros conteúdos de um modelo de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="892c4-108">The content schema rowset is a generic framework for storing patterns, statistics, and other contents of a data mining model.</span></span> <span data-ttu-id="892c4-109">Para obter uma lista das colunas do conjunto de linhas do esquema de mineração de dados para modelos de mineração, consulte [Conjunto de linhas DMSCHEMA_MINING_MODEL_CONTENT](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span><span class="sxs-lookup"><span data-stu-id="892c4-109">For a list of the columns in the data mining schema rowset for mining models, see [DMSCHEMA_MINING_MODEL_CONTENT Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span></span>  
  
## <a name="options"></a><span data-ttu-id="892c4-110">Opções</span><span class="sxs-lookup"><span data-stu-id="892c4-110">Options</span></span>  
 <span data-ttu-id="892c4-111">**Legenda do nó (ID exclusivo)**</span><span class="sxs-lookup"><span data-stu-id="892c4-111">**Node caption (Unique ID)**</span></span>  
 <span data-ttu-id="892c4-112">Este painel exibe uma lista de todos os nós no modelo de mineração selecionado.</span><span class="sxs-lookup"><span data-stu-id="892c4-112">This pane displays a list of all the nodes in the selected mining model.</span></span> <span data-ttu-id="892c4-113">A maneira como os nós são organizados na árvore é diferente dependendo do tipo de modelo que você está exibindo.</span><span class="sxs-lookup"><span data-stu-id="892c4-113">The way the nodes are arranged in the tree is different depending on the type of model you are viewing.</span></span>  
  
 <span data-ttu-id="892c4-114">Você pode clicar em cada nó para exibir detalhes sobre ele no painel **Detalhes do nó** .</span><span class="sxs-lookup"><span data-stu-id="892c4-114">You can click each node to display details about the node in the **Node details** pane.</span></span>  
  
 <span data-ttu-id="892c4-115">**Detalhes do nó**</span><span class="sxs-lookup"><span data-stu-id="892c4-115">**Node details**</span></span>  
 <span data-ttu-id="892c4-116">Exibe informações detalhadas sobre o conteúdo do nó selecionado.</span><span class="sxs-lookup"><span data-stu-id="892c4-116">Displays detailed information about the content of the selected node.</span></span> <span data-ttu-id="892c4-117">Cada nó armazena suas informações em um formato padronizado, mas o conteúdo e o significado de cada linha da tabela dependem do tipo de modelo ou tipo de nó que você está exibindo.</span><span class="sxs-lookup"><span data-stu-id="892c4-117">Each node stores its information in a standardized format, but the contents and significance of each line of the table depends on the type of model or type of node that you are viewing.</span></span> <span data-ttu-id="892c4-118">Por exemplo, as informações armazenadas para um nó que representa uma regra em um modelo de associação contêm informações diferentes de um nó que representa uma árvore em um modelo de árvores de decisão.</span><span class="sxs-lookup"><span data-stu-id="892c4-118">For example, the information stored for a node that represents a rule in an association model contains different information than a node that represents a tree in a decision trees model.</span></span>  
  
 <span data-ttu-id="892c4-119">Para obter informações sobre como interpretar as informações de um tipo específico de modelo, consulte [Conteúdo do modelo de mineração &#40;Analysis Services – Mineração de Dados&#41;](data-mining/mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="892c4-119">For information about how to interpret the node information for a specific model type, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](data-mining/mining-model-content-analysis-services-data-mining.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="892c4-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="892c4-120">See Also</span></span>  
 <span data-ttu-id="892c4-121">[Algoritmos de mineração de dados &#40;mineração de dados Analysis Services&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="892c4-121">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="892c4-122">[Visualizadores de modelo de mineração &#40;designer de modelo de mineração de dados&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="892c4-122">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="892c4-123">Consultas de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="892c4-123">Data Mining Queries</span></span>](data-mining/data-mining-queries.md)  
  
  
