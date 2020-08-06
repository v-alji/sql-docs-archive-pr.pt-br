---
title: Algoritmos de mineração de dados (SQL Server suplementos de mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- segmentation
- data mining algorithms
- clustering [data mining]
- linear regression
- association [data mining]
- neural networks
- logistic regression
- regression
- sequence analysis
- decision tree [data mining]
- Naive Bayes
- time series [data mining]
ms.assetid: 3a1a62e4-9fb5-4cdb-a6c6-1b8b30d417ef
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3a73ce5a538756a740afd2db72d585fa54f03cae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582226"
---
# <a name="data-mining-algorithms-sql-server-data-mining-add-ins"></a><span data-ttu-id="1a30d-102">Algoritmos de mineração de dados (Suplementos de mineração de dados do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1a30d-102">Data Mining Algorithms (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="1a30d-103">Os Suplementos de Mineração de Dados para Office oferecem suporte à criação de modelos analíticos usando os algoritmos de mineração de dados a seguir.</span><span class="sxs-lookup"><span data-stu-id="1a30d-103">The Data Mining Add-ins for Office supports creation of analytical models using the following data mining algorithms.</span></span> <span data-ttu-id="1a30d-104">Todos os algoritmos são baseados nos métodos de aprendizado automatizado conhecido e foram implementados pelo Microsoft Research.</span><span class="sxs-lookup"><span data-stu-id="1a30d-104">All algorithms are based on well-known machine learning methods and have been implemented by Microsoft Research.</span></span>  
  
## <a name="algorithms"></a><span data-ttu-id="1a30d-105">Algoritmos</span><span class="sxs-lookup"><span data-stu-id="1a30d-105">Algorithms</span></span>  
  
|<span data-ttu-id="1a30d-106">Método de aprendizado automatizado</span><span class="sxs-lookup"><span data-stu-id="1a30d-106">Machine learning method</span></span>|<span data-ttu-id="1a30d-107">Como ele funciona</span><span class="sxs-lookup"><span data-stu-id="1a30d-107">How it works</span></span>|  
|-----------------------------|------------------|  
|<span data-ttu-id="1a30d-108">Algoritmo de Regras de Associação da Microsoft</span><span class="sxs-lookup"><span data-stu-id="1a30d-108">Microsoft Association Rules  algorithm</span></span>|<span data-ttu-id="1a30d-109">Descobrir quais produtos são comprados juntos ou quais eventos ocorrem juntos, e usar o modelo para criar recomendações.</span><span class="sxs-lookup"><span data-stu-id="1a30d-109">Discover which products are purchased together or which events occur together, and use the model to create recommendations.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174916.aspx](https://msdn.microsoft.com/library/ms174916.aspx)|  
|<span data-ttu-id="1a30d-110">Algoritmo Microsoft Clustering</span><span class="sxs-lookup"><span data-stu-id="1a30d-110">Microsoft Clustering algorithm</span></span>|<span data-ttu-id="1a30d-111">Definir segmentos de mercado, agrupar automaticamente clientes relacionados, ou localizar relações nos dados para usar em mineração adicional.</span><span class="sxs-lookup"><span data-stu-id="1a30d-111">Define market segments, automatically group related customers together, or find relationships in data to use in further mining.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174879.aspx](https://msdn.microsoft.com/library/ms174879.aspx)|  
|<span data-ttu-id="1a30d-112">Algoritmo Árvores de Decisão da Microsoft</span><span class="sxs-lookup"><span data-stu-id="1a30d-112">Microsoft Decision Trees algorithm</span></span>|<span data-ttu-id="1a30d-113">Identificar relações anteriormente desconhecidas entre vários elementos dos dados para informar melhor suas decisões, ou localizar os fatores que levam a resultados específicos.</span><span class="sxs-lookup"><span data-stu-id="1a30d-113">Identify previously unknown relationships between various elements of your data to better inform your decisions, or find the factors that lead to specific outcomes.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174923.aspx](https://msdn.microsoft.com/library/ms174923.aspx)|  
|<span data-ttu-id="1a30d-114">Algoritmo Regressão Linear da Microsoft</span><span class="sxs-lookup"><span data-stu-id="1a30d-114">Microsoft Linear Regression algorithm</span></span>|<span data-ttu-id="1a30d-115">Localizar uma fórmula matemática que descreva fatores que contribuem para um resultado numérico.</span><span class="sxs-lookup"><span data-stu-id="1a30d-115">Find a mathematical formula that describes factors that contribute to a numeric outcome.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174824.aspx](https://msdn.microsoft.com/library/ms174824.aspx)|  
|<span data-ttu-id="1a30d-116">Algoritmo Regressão Logística da Microsoft</span><span class="sxs-lookup"><span data-stu-id="1a30d-116">Microsoft Logistic Regression algorithm</span></span>|<span data-ttu-id="1a30d-117">Identificar os fatores que contribuem para os resultados binários, além de saber como usar isso para afetar os resultados.</span><span class="sxs-lookup"><span data-stu-id="1a30d-117">Identify the factors that contribute to binary outcomes, and learn how to use those to affect results.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174828.aspx](https://msdn.microsoft.com/library/ms174828.aspx)|  
|<span data-ttu-id="1a30d-118">Algoritmo Microsoft Naïve Bayes</span><span class="sxs-lookup"><span data-stu-id="1a30d-118">Microsoft Naïve Bayes algorithm</span></span>|<span data-ttu-id="1a30d-119">Explorar as relações nos seus dados e localizar aquelas mais associadas a um resultado.</span><span class="sxs-lookup"><span data-stu-id="1a30d-119">Explore relationships in your data and find those mostly closely correlated with an outcome.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174806.aspx](https://msdn.microsoft.com/library/ms174806.aspx)|  
|<span data-ttu-id="1a30d-120">Algoritmo Redes Neurais da Microsoft</span><span class="sxs-lookup"><span data-stu-id="1a30d-120">Microsoft Neural Networks algorithm</span></span>|<span data-ttu-id="1a30d-121">Localizar relações ocultas entre várias entradas e até mesmo saídas.</span><span class="sxs-lookup"><span data-stu-id="1a30d-121">Find hidden relationships among multiple inputs and even multiple outputs.</span></span> <span data-ttu-id="1a30d-122">Usar para exploração ou para previsão.</span><span class="sxs-lookup"><span data-stu-id="1a30d-122">Use for exploration or for prediction.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174941.aspx](https://msdn.microsoft.com/library/ms174941.aspx)|  
|<span data-ttu-id="1a30d-123">Algoritmo Microsoft Time Series</span><span class="sxs-lookup"><span data-stu-id="1a30d-123">Microsoft Time Series algorithm</span></span>|<span data-ttu-id="1a30d-124">Usar dados históricos para prever valores futuros.</span><span class="sxs-lookup"><span data-stu-id="1a30d-124">Use historical data to forecast future values.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174923.aspx](https://msdn.microsoft.com/library/ms174923.aspx)|  
  
## <a name="advanced-options"></a><span data-ttu-id="1a30d-125">Opções avançadas</span><span class="sxs-lookup"><span data-stu-id="1a30d-125">Advanced Options</span></span>  
 <span data-ttu-id="1a30d-126">Quando usa o Cliente de Mineração de Dados para Excel, você tem a opção de criar seus próprios modelos e estruturas de mineração de dados, ou de ajustar os parâmetros dos algoritmos.</span><span class="sxs-lookup"><span data-stu-id="1a30d-126">When you use the Data Mining Client for Excel, you have the option to create your own data mining structures and models, or to fine-tune the parameters of the algorithms.</span></span>  
  
 [<span data-ttu-id="1a30d-127">Parâmetros de algoritmo &#40;SQL Server suplementos de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="1a30d-127">Algorithm Parameters &#40;SQL Server Data Mining Add-ins&#41;</span></span>](algorithm-parameters-sql-server-data-mining-add-ins.md)  
  
 <span data-ttu-id="1a30d-128">Há duas maneiras de personalizar seus modelos usando essas opções avançadas:</span><span class="sxs-lookup"><span data-stu-id="1a30d-128">There are two ways to customize your models using these advanced options:</span></span>  
  
-   <span data-ttu-id="1a30d-129">Use o assistente de **consulta de mineração de dados** para criar seu modelo.</span><span class="sxs-lookup"><span data-stu-id="1a30d-129">Use the **Data Mining Query** wizard to create your model.</span></span>  
  
-   <span data-ttu-id="1a30d-130">No **cliente de mineração de dados**, depois de iniciar o assistente, clique em **parâmetros**.</span><span class="sxs-lookup"><span data-stu-id="1a30d-130">In the **Data Mining Client**, after you start the wizard, click **Parameters**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a30d-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1a30d-131">See Also</span></span>  
 <span data-ttu-id="1a30d-132">[&#40;de consulta SQL Server suplementos de mineração de dados&#41;](query-sql-server-data-mining-add-ins.md) </span><span class="sxs-lookup"><span data-stu-id="1a30d-132">[Query &#40;SQL Server Data Mining Add-ins&#41;](query-sql-server-data-mining-add-ins.md) </span></span>  
 [<span data-ttu-id="1a30d-133">Modelagem avançada &#40;suplementos de mineração de dados para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="1a30d-133">Advanced Modeling &#40;Data Mining Add-ins for Excel&#41;</span></span>](advanced-modeling-data-mining-add-ins-for-excel.md)  
  
  
