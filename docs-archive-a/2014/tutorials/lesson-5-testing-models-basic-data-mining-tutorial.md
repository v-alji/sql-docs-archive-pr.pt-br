---
title: 'Lição 5: testando modelos (tutorial de mineração de dados básico) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: e9a7ddcf-2b01-485f-bbb5-62638b303bc6
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: fcfd9a9e90d9c6800af4dfd1599bbdd62d9520ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681959"
---
# <a name="lesson-5-testing-models-basic-data-mining-tutorial"></a><span data-ttu-id="e0799-102">Lição 5: Testando modelos (Tutorial de mineração de dados básico)</span><span class="sxs-lookup"><span data-stu-id="e0799-102">Lesson 5: Testing Models (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="e0799-103">Agora que você processou o modelo usando o conjunto de treinamentos de cenário de mala direta, verificará os seus modelos usando um conjunto de testes.</span><span class="sxs-lookup"><span data-stu-id="e0799-103">Now that you have processed the model by using the targeted mailing scenario training set, you will test your models against the testing set.</span></span> <span data-ttu-id="e0799-104">A validação é uma etapa importante do processo de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="e0799-104">Validation is an important step in the data mining process.</span></span> <span data-ttu-id="e0799-105">É importante saber como é o desempenho dos seus modelos de mineração de mala direta usando dados reais antes de implantá-los em um ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="e0799-105">Knowing how well your targeted mailing mining models perform against real data is important before you deploy the models into a production environment.</span></span>  
  
 <span data-ttu-id="e0799-106">Como os dados no conjunto de teste já contêm valores conhecidos para a compra de bicicleta, é fácil determinar se a precisão das previsões do modelo está correta.</span><span class="sxs-lookup"><span data-stu-id="e0799-106">Because the data in the testing set already contains known values for bike buying, it is easy to determine whether the model's predictions are correct.</span></span> <span data-ttu-id="e0799-107">O modelo que executa a melhor será usado pelo departamento de [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] marketing para identificar os clientes para sua campanha de mala direta.</span><span class="sxs-lookup"><span data-stu-id="e0799-107">The model that performs the best will be used by the [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] marketing department to identify the customers for their targeted mailing campaign.</span></span>  
  
 <span data-ttu-id="e0799-108">Nesta lição, você validará seus modelos usando vários métodos:</span><span class="sxs-lookup"><span data-stu-id="e0799-108">In this lesson you will validate your models using multiple methods:</span></span>  
  
1.  <span data-ttu-id="e0799-109">Você fará previsões em relação ao conjunto de testes para ver quão precisas o modelo está em resultados conhecidos.</span><span class="sxs-lookup"><span data-stu-id="e0799-109">You'll make predictions against the testing set to see how accurate the model is on known results.</span></span> <span data-ttu-id="e0799-110">Você usará um *gráfico* de comparação de precisão para medir sua eficácia.</span><span class="sxs-lookup"><span data-stu-id="e0799-110">You'll use a *lift chart* to measure its effectiveness.</span></span>  
  
     [<span data-ttu-id="e0799-111">Testando a precisão com gráficos de comparação de precisão &#40;Tutorial de mineração de dados básica&#41;</span><span class="sxs-lookup"><span data-stu-id="e0799-111">Testing Accuracy with Lift Charts &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-accuracy-with-lift-charts-basic-data-mining-tutorial.md)  
  
2.  <span data-ttu-id="e0799-112">Você testará seus modelos em um subconjunto filtrado dos dados.</span><span class="sxs-lookup"><span data-stu-id="e0799-112">You will test your models on a filtered subset of the data.</span></span> <span data-ttu-id="e0799-113">Você pode comparar vários modelos no mesmo gráfico de comparação de precisão.</span><span class="sxs-lookup"><span data-stu-id="e0799-113">You can compare multiple models in the same lift chart.</span></span>  
  
     [<span data-ttu-id="e0799-114">Testando um modelo filtrado &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="e0799-114">Testing a Filtered Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-a-filtered-model-basic-data-mining-tutorial.md)  
  
 <span data-ttu-id="e0799-115">Para obter mais informações sobre como a validação de modelo em geral, consulte [conceitos de mineração de dados](../../2014/analysis-services/data-mining/data-mining-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="e0799-115">For more information about how model validation in general, see [Data Mining Concepts](../../2014/analysis-services/data-mining/data-mining-concepts.md).</span></span>  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="e0799-116">Primeira tarefa na lição</span><span class="sxs-lookup"><span data-stu-id="e0799-116">First Task in Lesson</span></span>  
 [<span data-ttu-id="e0799-117">Testando a precisão com gráficos de comparação de precisão &#40;Tutorial de mineração de dados básica&#41;</span><span class="sxs-lookup"><span data-stu-id="e0799-117">Testing Accuracy with Lift Charts &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-accuracy-with-lift-charts-basic-data-mining-tutorial.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="e0799-118">Lição anterior</span><span class="sxs-lookup"><span data-stu-id="e0799-118">Previous Lesson</span></span>  
 [<span data-ttu-id="e0799-119">Lição 4: explorando os modelos de mala direta direcionados &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="e0799-119">Lesson 4: Exploring the Targeted Mailing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-exploring-the-targeted-mailing-models-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="e0799-120">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="e0799-120">Next Lesson</span></span>  
 [<span data-ttu-id="e0799-121">Lição 6: Criando e trabalhando com previsões &#40;Tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="e0799-121">Lesson 6: Creating and Working with Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-6-creating-and-working-with-predictions-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="e0799-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e0799-122">See Also</span></span>  
 <span data-ttu-id="e0799-123">[Guia gráfico de comparação &#40;exibição de gráfico de precisão de mineração&#41;](../../2014/analysis-services/lift-chart-tab-mining-accuracy-chart-view.md) </span><span class="sxs-lookup"><span data-stu-id="e0799-123">[Lift Chart Tab &#40;Mining Accuracy Chart View&#41;](../../2014/analysis-services/lift-chart-tab-mining-accuracy-chart-view.md) </span></span>  
 <span data-ttu-id="e0799-124">[&#40;do gráfico de comparação de precisão Analysis Services-Mineração de dados&#41;](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="e0799-124">[Lift Chart &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="e0799-125">[Teste e validação &#40;mineração de dados&#41;](../../2014/analysis-services/data-mining/testing-and-validation-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="e0799-125">[Testing and Validation &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/testing-and-validation-data-mining.md) </span></span>  
 <span data-ttu-id="e0799-126">[Guia matriz de classificação &#40;exibição de gráfico de precisão de mineração&#41;](../../2014/analysis-services/classification-matrix-tab-mining-accuracy-chart-view.md) </span><span class="sxs-lookup"><span data-stu-id="e0799-126">[Classification Matrix Tab &#40;Mining Accuracy Chart View&#41;](../../2014/analysis-services/classification-matrix-tab-mining-accuracy-chart-view.md) </span></span>  
 [<span data-ttu-id="e0799-127">Matriz de classificação &#40;Analysis Services – Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="e0799-127">Classification Matrix &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/classification-matrix-analysis-services-data-mining.md)  
  
  
