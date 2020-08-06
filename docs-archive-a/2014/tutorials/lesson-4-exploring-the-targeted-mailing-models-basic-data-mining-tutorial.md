---
title: 'Lição 4: explorando os modelos de endereçamento de destino (tutorial de mineração de dados básico) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 1e00c5b9-a9f8-4503-99ee-377c9cc02d7f
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 8659350b126164e06550acdbecec04bb07499c55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683193"
---
# <a name="lesson-4-exploring-the-targeted-mailing-models-basic-data-mining-tutorial"></a><span data-ttu-id="84bac-102">Lição 4: Explorando os modelos de mala direta (Tutorial de mineração de dados básico)</span><span class="sxs-lookup"><span data-stu-id="84bac-102">Lesson 4: Exploring the Targeted Mailing Models (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="84bac-103">Depois que os modelos do seu projeto tiverem sido processados, você poderá explorá-los para procurar por tendências que sejam interessantes.</span><span class="sxs-lookup"><span data-stu-id="84bac-103">After the models in your project have been processed, you can explore them to look for interesting trends.</span></span> <span data-ttu-id="84bac-104">Como padrões podem ser complexos e difíceis se analisarmos somente os números, a Mineração de Dados do SQL Server oferece algumas ferramentas visuais que o ajudam a investigar os dados e a compreender as regras e as relações que os algoritmos encontraram nos dados.</span><span class="sxs-lookup"><span data-stu-id="84bac-104">Because patterns can be complex and difficult simply by looking at numbers, SQL Server Data Mining provides some visual tools that help you investigate the data and understand the rules and relationships that the algorithms have discovered within the data.</span></span> <span data-ttu-id="84bac-105">Você também pode usar uma variedade de testes de precisão para validar seu conjunto de dados ou para descobrir qual o melhor modelo antes de implantá-lo.</span><span class="sxs-lookup"><span data-stu-id="84bac-105">You can also use a variety of accuracy tests to validate your dataset or discover which model performs best before you deploy it.</span></span>  
  
 <span data-ttu-id="84bac-106">Quando você usa o [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para explorar seus modelos, cada modelo que você criou é listado na guia **Visualizador do modelo de mineração** no designer de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="84bac-106">When you use [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to explore your models, each model you created is listed in the **Mining Model Viewer** tab in Data Mining Designer.</span></span> <span data-ttu-id="84bac-107">Você pode usar os visualizadores para explorar os modelos.</span><span class="sxs-lookup"><span data-stu-id="84bac-107">You can use the viewers to explore the models.</span></span> <span data-ttu-id="84bac-108">Estes visualizadores também estão disponíveis no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="84bac-108">These viewers are also available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="84bac-109">Cada algoritmo usado para criar um modelo no [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] retorna um tipo diferente de resultado.</span><span class="sxs-lookup"><span data-stu-id="84bac-109">Each algorithm that you used to build a model in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] returns a different type of result.</span></span> <span data-ttu-id="84bac-110">Consequentemente, o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] fornece visualizadores personalizados para cada tipo de modelo de aprendizado automatizado.</span><span class="sxs-lookup"><span data-stu-id="84bac-110">Therefore, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] provides custom viewers for each type of machine learning model.</span></span>  
  
 <span data-ttu-id="84bac-111">Se você quiser obter detalhes, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] o também fornece um visualizador de HTML, chamado **Visualizador de árvore de conteúdo genérico**, que exibe informações detalhadas sobre os dados do modelo e quaisquer padrões encontrados, em um formato semitabular.</span><span class="sxs-lookup"><span data-stu-id="84bac-111">If you want to get into details, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] also provides an HTML viewer, called the **Generic Content Tree Viewer**, that displays detailed information about the model data and any patterns that were found, in a semi-tabular format.</span></span> <span data-ttu-id="84bac-112">Para obter mais informações, consulte [Procurar um modelo usando o Visualizador de Árvore de Conteúdo Genérico da Microsoft](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-generic-content-tree-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="84bac-112">For more information, see [Browse a Model Using the Microsoft Generic Content Tree Viewer](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-generic-content-tree-viewer.md).</span></span>  
  
 <span data-ttu-id="84bac-113">Nesta lição, você examinará os resultados dos seus três modelos.</span><span class="sxs-lookup"><span data-stu-id="84bac-113">In this lesson you will look at the results from your three models.</span></span> <span data-ttu-id="84bac-114">Cada tipo de modelo se baseia em um algoritmo diferente e oferece ideias diferentes sobre os dados.</span><span class="sxs-lookup"><span data-stu-id="84bac-114">Each model type is based on a different algorithm and provides different insights into the data.</span></span>  
  
-   <span data-ttu-id="84bac-115">O modelo Árvore de Decisão mostra os fatores que influenciam a compra de uma bicicleta.</span><span class="sxs-lookup"><span data-stu-id="84bac-115">The Decision Tree model tells you about factors that influence bike buying.</span></span>  
  
-   <span data-ttu-id="84bac-116">O modelo Clustering agrupa seus clientes por atributos que incluem seu comportamento na compra de bicicletas e outros atributos selecionados.</span><span class="sxs-lookup"><span data-stu-id="84bac-116">The Clustering model groups your customers by attributes that include their bike buying behavior and other selected attributes.</span></span>  
  
-   <span data-ttu-id="84bac-117">O modelo Naive Baynes permite que você explore o relacionamento entre os atributos diferentes.</span><span class="sxs-lookup"><span data-stu-id="84bac-117">The Naive Bayes model enables you to explore the relationship between different attributes.</span></span>  
  
 <span data-ttu-id="84bac-118">Consulte os tópicos a seguir para saber mais sobre os visualizadores do modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="84bac-118">See the following topics to learn more about each of the mining model viewers.</span></span>  
  
-   [<span data-ttu-id="84bac-119">Exploração do modelo de árvore de decisão &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="84bac-119">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="84bac-120">Explorando o modelo de clustering &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="84bac-120">Exploring the Clustering Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="84bac-121">Explorando o Naive Bayes do modelo de mineração de dados &#40;Basic&#41;</span><span class="sxs-lookup"><span data-stu-id="84bac-121">Exploring the Naive Bayes Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-naive-bayes-model-basic-data-mining-tutorial.md)  
  
 <span data-ttu-id="84bac-122">Todos os três modelos podem ser exibidos usando o **Visualizador de árvore de conteúdo genérico**, para extrair fórmulas, valores de dados e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="84bac-122">All three models can be viewed using the **Generic Content Tree Viewer**, to extract formulas, data values, and so forth.</span></span>  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="84bac-123">Primeira tarefa na lição</span><span class="sxs-lookup"><span data-stu-id="84bac-123">First Task in Lesson</span></span>  
 [<span data-ttu-id="84bac-124">Exploração do modelo de árvore de decisão &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="84bac-124">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="84bac-125">Lição anterior</span><span class="sxs-lookup"><span data-stu-id="84bac-125">Previous Lesson</span></span>  
 [<span data-ttu-id="84bac-126">Lição 3: Adicionando e processando modelos</span><span class="sxs-lookup"><span data-stu-id="84bac-126">Lesson 3: Adding and Processing Models</span></span>](../../2014/tutorials/lesson-3-adding-and-processing-models.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="84bac-127">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="84bac-127">Next Lesson</span></span>  
 [<span data-ttu-id="84bac-128">Lição 5: testando modelos &#40;o tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="84bac-128">Lesson 5: Testing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-testing-models-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="84bac-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="84bac-129">See Also</span></span>  
 <span data-ttu-id="84bac-130">[Tarefas e instruções do Visualizador do modelo de mineração](../../2014/analysis-services/data-mining/mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="84bac-130">[Mining Model Viewer Tasks and How-tos](../../2014/analysis-services/data-mining/mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="84bac-131">Visualizadores do Modelo de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="84bac-131">Data Mining Model Viewers</span></span>](../../2014/analysis-services/data-mining/data-mining-model-viewers.md)  
  
  
