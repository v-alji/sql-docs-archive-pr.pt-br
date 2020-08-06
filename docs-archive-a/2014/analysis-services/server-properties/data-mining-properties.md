---
title: Propriedades de mineração de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- ClusterCount property
- AllowedProvidersInOpenRowset property
- MinimumSeriesValue property
- ScoreMethod property
- MinimumImportance property
- ModellingCardinality property
- BrentTolerance property
- ComplexityPenalty property
- MaximumItemsetCount property
- MinimumSupport property
- AllowSessionMiningModels property
- HoldoutPercentage property
- ClusterCountPrior property
- MaximumSequenceStates property
- OptimizedPredictionCount property
- data mining [Analysis Services], properties
- MaximumStates property
- MaximumContinuousInputAttributes property
- MaximumOutputAttributes property
- AllowAdHocOpenRowsetQueries property
- Enabled property
- HistoricModelGap property
- SampleSize property
- MaximumInputAttributes property
- PeriodicityHint property
- MissingValueSubstitution property
- SplitMethod property
- ForceRegressor property
- MaximumBucketsForContinuousSplit property
- MaxConcurrentPredictionQueries property
- MinimumItemsetSize property
- AcyclicGraph property
- HoldoutMethod property
- StoppingTolerance property
- properties [data mining]
- AutoDetectPeriodicity property
- HoldoutTolerance property
- MinimumLeafCases property
- HoldoutSeed property
- MinimumClusterCases property
- ClusterCountDeviation property
- MinimumDependencyProbability property
- ClusteringMethod property
- MaximumItemsetSize property
- HiddenNodeRatio property
- MaximumSeriesValue property
ms.assetid: 9bc9abed-180a-4bd8-b2eb-89c62fa88110
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5ed1c47faafeb0c680e6afb6f8e509c426760da2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686400"
---
# <a name="data-mining-properties"></a><span data-ttu-id="726e9-102">Propriedades de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="726e9-102">Data Mining Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="726e9-103">oferece suporte às propriedades do servidor de mineração de dados listadas nas tabelas a seguir.</span><span class="sxs-lookup"><span data-stu-id="726e9-103">supports the data mining server properties listed in the following tables.</span></span> <span data-ttu-id="726e9-104">Para obter mais informações sobre as propriedades de servidor adicionais e como defini-las, consulte [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="726e9-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="726e9-105">**Aplica-se a:** Somente modo de servidor multidimensional</span><span class="sxs-lookup"><span data-stu-id="726e9-105">**Applies to:** Multidimensional server mode only</span></span>  
  
## <a name="non-specific-category"></a><span data-ttu-id="726e9-106">Categoria não específica</span><span class="sxs-lookup"><span data-stu-id="726e9-106">Non-Specific Category</span></span>  
 `AllowSessionMiningModels`  
 <span data-ttu-id="726e9-107">Uma propriedade Booleana que indica se podem ser criados modelos de mineração de sessão.</span><span class="sxs-lookup"><span data-stu-id="726e9-107">A Boolean property that indicates whether session mining models can be created.</span></span>  
  
 <span data-ttu-id="726e9-108">O valor padrão para essa propriedade é false, o que indica que modelos de mineração de sessão não podem ser criados.</span><span class="sxs-lookup"><span data-stu-id="726e9-108">The default value for this property is false, which indicates that session mining models cannot be created.</span></span>  
  
 `AllowAdHocOpenRowsetQueries`  
 <span data-ttu-id="726e9-109">Uma propriedade Booleana que indica se consultas ad hoc abertas de conjunto de linhas são permitidas.</span><span class="sxs-lookup"><span data-stu-id="726e9-109">A Boolean property that indicates whether adhoc open rowset queries are allowed.</span></span>  
  
 <span data-ttu-id="726e9-110">O valor padrão para essa propriedade é false, o que indica que as consultas abertas de conjuntos de linhas não são permitidas durante uma sessão.</span><span class="sxs-lookup"><span data-stu-id="726e9-110">The default value for this property is false, which indicates that open rowset queries are not allowed during a session.</span></span>  
  
 `AllowedProvidersInOpenRowset`  
 <span data-ttu-id="726e9-111">Uma propriedade de cadeia de caracteres que identifica quais fornecedores são permitidos em um conjunto de linhas aberto, consistindo de uma lista de ProgIDs ou [All] de fornecedores separada por vírgula/ponto-e-vírgula.</span><span class="sxs-lookup"><span data-stu-id="726e9-111">A string property that identifies which providers are allowed in an open rowset, consisting of a comma/semi-colon separated list of provider ProgIDs, or else [All].</span></span>  
  
 `MaxConcurrentPredictionQueries`  
 <span data-ttu-id="726e9-112">Uma propriedade de inteiro de 32 bits assinada que define o número máximo de consultas de previsão simultâneas.</span><span class="sxs-lookup"><span data-stu-id="726e9-112">A signed 32-bit integer property that defines the maximum number of concurrent prediction queries.</span></span>  
  
## <a name="algorithms-category"></a><span data-ttu-id="726e9-113">Categoria de algoritmos</span><span class="sxs-lookup"><span data-stu-id="726e9-113">Algorithms Category</span></span>  
 `Microsoft_Association_Rules\ Enabled`  
 <span data-ttu-id="726e9-114">Uma propriedade Booleana que indica se o algoritmo Microsoft_Association_Rules está habilitado.</span><span class="sxs-lookup"><span data-stu-id="726e9-114">A Boolean property that indicates whether the Microsoft_Association_Rules algorithm is enabled.</span></span>  
  
 `Microsoft_Clustering\ Enabled`  
 <span data-ttu-id="726e9-115">Uma propriedade Booleana que indica se o algoritmo Microsoft_Clustering está habilitado.</span><span class="sxs-lookup"><span data-stu-id="726e9-115">A Boolean property that indicates whether the Microsoft_Clustering algorithm is enabled.</span></span>  
  
 `Microsoft_Decision_Trees\ Enabled`  
 <span data-ttu-id="726e9-116">Uma propriedade Booleana que indica se o algoritmo Microsoft_ DecisionTrees está habilitado.</span><span class="sxs-lookup"><span data-stu-id="726e9-116">A Boolean property that indicates whether the Microsoft_DecisionTrees algorithm is enabled.</span></span>  
  
 `Microsoft_Naive_Bayes\ Enabled`  
 <span data-ttu-id="726e9-117">Uma propriedade Booleana que indica se o algoritmo Microsoft_ Naive_Bayes está habilitado.</span><span class="sxs-lookup"><span data-stu-id="726e9-117">A Boolean property that indicates whether the Microsoft_ Naive_Bayes algorithm is enabled.</span></span>  
  
 `Microsoft_Neural_Network\ Enabled`  
 <span data-ttu-id="726e9-118">Uma propriedade Booleana que indica se o algoritmo Microsoft_Neural_Network está habilitado.</span><span class="sxs-lookup"><span data-stu-id="726e9-118">A Boolean property that indicates whether the Microsoft_Neural_Network algorithm is enabled.</span></span>  
  
 `Microsoft_Sequence_Clustering\ Enabled`  
 <span data-ttu-id="726e9-119">Uma propriedade Booleana que indica se o algoritmo Microsoft_ Sequence_Clustering está habilitado.</span><span class="sxs-lookup"><span data-stu-id="726e9-119">A Boolean property that indicates whether the Microsoft_Sequence_Clustering algorithm is enabled.</span></span>  
  
 `Microsoft_Time_Series\ Enabled`  
 <span data-ttu-id="726e9-120">Uma propriedade Booleana que indica se o algoritmo Microsoft_Time_Series está habilitado.</span><span class="sxs-lookup"><span data-stu-id="726e9-120">A Boolean property that indicates whether the Microsoft_Time_Series algorithm is enabled.</span></span>  
  
 `Microsoft_Linear_Regression\ Enabled`  
 <span data-ttu-id="726e9-121">Uma propriedade Booleana que indica se o algoritmo Microsoft_Linear_Regression está habilitado.</span><span class="sxs-lookup"><span data-stu-id="726e9-121">A Boolean property that indicates whether the Microsoft_Linear_Regression algorithm is enabled.</span></span>  
  
 `Microsoft_Logistic_Regression\ Enabled`  
 <span data-ttu-id="726e9-122">Uma propriedade Booleana que indica se o algoritmo Microsoft_Logistic_Regression está habilitado.</span><span class="sxs-lookup"><span data-stu-id="726e9-122">A Boolean property that indicates whether the Microsoft_Logistic_Regression algorithm is enabled.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="726e9-123">Além das propriedades que definem os serviços mineração de dados disponíveis no servidor, há propriedades de mineração de dados que definem o comportamento de algoritmos específicos.</span><span class="sxs-lookup"><span data-stu-id="726e9-123">In addition to properties that define the data mining services available on the server, there are data mining properties that define the behavior of specific algorithms.</span></span> <span data-ttu-id="726e9-124">Essas propriedades são configuradas quando você criar um modelo de mineração de dados individual, não ao nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="726e9-124">You configure these properties when you create an individual data mining model, not at the server level.</span></span> <span data-ttu-id="726e9-125">Para obter mais informações, consulte [Algoritmos de mineração de dados &#40;Analysis Services – Mineração de Dados&#41;](../data-mining/data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="726e9-125">For more information, see [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](../data-mining/data-mining-algorithms-analysis-services-data-mining.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="726e9-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="726e9-126">See Also</span></span>  
 <span data-ttu-id="726e9-127">[Arquitetura física &#40;Analysis Services&#41;de mineração de dados](../data-mining/physical-architecture-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="726e9-127">[Physical Architecture &#40;Analysis Services - Data Mining&#41;](../data-mining/physical-architecture-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="726e9-128">[Configurar propriedades do servidor no Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="726e9-128">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="726e9-129">Determina o Modo de Servidor de uma instância do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="726e9-129">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
