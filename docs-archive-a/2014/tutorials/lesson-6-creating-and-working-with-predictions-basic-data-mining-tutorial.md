---
title: 'Lição 6: Criando e trabalhando com previsões (tutorial de mineração de dados básico) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b213cb58-2c40-4c89-b08b-d3c36a4afad3
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d0a8bfdf83e96622a19ac72490e8602d12afc9df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571715"
---
# <a name="lesson-6-creating-and-working-with-predictions-basic-data-mining-tutorial"></a><span data-ttu-id="7d633-102">Lição 6: Criando e trabalhando com previsões (Tutorial de mineração de dados básico)</span><span class="sxs-lookup"><span data-stu-id="7d633-102">Lesson 6: Creating and Working with Predictions (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="7d633-103">Você testou e explorou os modelos de mineração de dados criados e fez treinamentos sobre eles.</span><span class="sxs-lookup"><span data-stu-id="7d633-103">You have trained, tested, and explored the data mining models you created.</span></span> <span data-ttu-id="7d633-104">Agora você está pronto para usar os modelos para identificar as pessoas com maior probabilidade de responder à nova campanha de mala direta.</span><span class="sxs-lookup"><span data-stu-id="7d633-104">Now you are ready to use the models to identify the people most likely to respond to the new targeted mailing campaign.</span></span>  
  
 <span data-ttu-id="7d633-105">Nesta lição, você criará uma consulta para prever quais clientes têm mais probabilidade de comprar uma bicicleta.</span><span class="sxs-lookup"><span data-stu-id="7d633-105">In this lesson you will create a query to predict which customers are most likely to purchase a bike.</span></span> <span data-ttu-id="7d633-106">Você também recuperará a *probabilidade* de que a previsão esteja correta, para que o departamento de marketing possa decidir se você pode optar por usar a previsão ou não.</span><span class="sxs-lookup"><span data-stu-id="7d633-106">You will also retrieve the *probability* that the prediction is correct, so the marketing department can decide whether to you can decide whether to use the prediction or not.</span></span>  
  
 <span data-ttu-id="7d633-107">Depois de identificar clientes com uma grande probabilidade de comprar uma bicicleta, você detalhará os casos no modelo de mineração para recuperar nomes e informações de contato para esses clientes.</span><span class="sxs-lookup"><span data-stu-id="7d633-107">Once you have identified customers with a high probability of purchasing a bike, you will drill through to the details of the cases in the mining model to retrieve names and contact information for these customers.</span></span>  
  
 <span data-ttu-id="7d633-108">Eis os tópicos desta lição:</span><span class="sxs-lookup"><span data-stu-id="7d633-108">This lesson contains the following topics:</span></span>  
  
 [<span data-ttu-id="7d633-109">Criando previsões &#40;Tutorial básico de Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="7d633-109">Creating Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-predictions-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="7d633-110">Usando o detalhamento em dados de estrutura &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="7d633-110">Using Drillthrough on Structure Data &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/using-drillthrough-on-structure-data-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="7d633-111">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="7d633-111">Next Lesson</span></span>  
 [<span data-ttu-id="7d633-112">Tutorial de mineração de dados intermediário &#40;Analysis Services de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="7d633-112">Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="7d633-113">Lição anterior</span><span class="sxs-lookup"><span data-stu-id="7d633-113">Previous Lesson</span></span>  
 [<span data-ttu-id="7d633-114">Lição 5: testando modelos &#40;o tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="7d633-114">Lesson 5: Testing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-testing-models-basic-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="7d633-115">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="7d633-115">Next Task in Lesson</span></span>  
 [<span data-ttu-id="7d633-116">Criando previsões &#40;Tutorial básico de Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="7d633-116">Creating Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-predictions-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="7d633-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7d633-117">See Also</span></span>  
 <span data-ttu-id="7d633-118">[Conteúdo do modelo de mineração para modelos de árvore de decisão &#40;Analysis Services de mineração de dados&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-decision-tree-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="7d633-118">[Mining Model Content for Decision Tree Models &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-decision-tree-models-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="7d633-119">Criar uma consulta de previsão usando o construtor de consultas de previsão</span><span class="sxs-lookup"><span data-stu-id="7d633-119">Create a Prediction Query Using the Prediction Query Builder</span></span>](../../2014/analysis-services/data-mining/create-a-prediction-query-using-the-prediction-query-builder.md)  
  
  
