---
title: Especificar uma coluna a ser usada como regressor em um modelo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d8e0cb8e-302a-4166-9ed0-e2d9e2919b0a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 86899d3793985b5e3c07618360d7b6a540935a54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568888"
---
# <a name="specify-a-column-to-use-as-regressor-in-a-model"></a><span data-ttu-id="6be1b-102">Especificar uma coluna para usar como regressor em um modelo</span><span class="sxs-lookup"><span data-stu-id="6be1b-102">Specify a Column to Use as Regressor in a Model</span></span>
  <span data-ttu-id="6be1b-103">Um modelo de regressão linear representa o valor do atributo previsível como resultado de uma fórmula, que combina as entradas de forma que os dados são ajustados o mais próximo possível a uma linha de regressão estimada.</span><span class="sxs-lookup"><span data-stu-id="6be1b-103">A linear regression model represents the value of the predictable attribute as the result of a formula that combines the inputs in such a way that the data is fitted as a closely as possible to an estimated regression line.</span></span> <span data-ttu-id="6be1b-104">O algoritmo aceita somente valores numéricos como entradas e detecta automaticamente as entradas que oferecem o melhor ajuste.</span><span class="sxs-lookup"><span data-stu-id="6be1b-104">The algorithm accepts only numeric values as inputs, and automatically detects the inputs that provide the best fit.</span></span>  
  
 <span data-ttu-id="6be1b-105">Entretanto, você poderá especificar que uma coluna seja incluída como um regressor adicionando o parâmetro FORCE_REGRESSOR ao modelo e especificando os regressores a serem usados.</span><span class="sxs-lookup"><span data-stu-id="6be1b-105">However, you can specify that a column be included as a regressor by adding the FORCE_REGRESSOR parameter to the model and specifying the regressors to use.</span></span> <span data-ttu-id="6be1b-106">Você poderá fazer isso nos casos em que o atributo tenha significado, mesmo se o efeito for muito pequeno para ser detectado pelo modelo, ou quando quiser assegurar que o atributo seja incluído na fórmula.</span><span class="sxs-lookup"><span data-stu-id="6be1b-106">You might want to do this in cases where the attribute has meaning even if the effect is too small to be detected by the model, or when you want to ensure that the attribute is included in the formula.</span></span>  
  
 <span data-ttu-id="6be1b-107">O procedimento a seguir descreve como criar um modelo de regressão linear simples, usando os mesmos dados de exemplo que são usados para o [tutorial de redes neurais](../../tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="6be1b-107">The following procedure describes how to create a simple linear regression model, using the same sample data that is used for the [neural networks tutorial](../../tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md).</span></span> <span data-ttu-id="6be1b-108">O modelo não é necessariamente robusto, mas demonstra como usar o Designer de Mineração de Dados para personalizar um modelo de regressão linear.</span><span class="sxs-lookup"><span data-stu-id="6be1b-108">The model is not necessarily robust, but demonstrates how to use the Data Mining Designer to customize a linear regression model.</span></span>  
  
### <a name="how-to-create-a-simple-linear-regression-model"></a><span data-ttu-id="6be1b-109">Como criar um modelo de regressão linear simples</span><span class="sxs-lookup"><span data-stu-id="6be1b-109">How to create a simple linear regression model</span></span>  
  
1.  <span data-ttu-id="6be1b-110">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], no **Gerenciador de Soluções**, expanda **Estruturas de Mineração**.</span><span class="sxs-lookup"><span data-stu-id="6be1b-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in **Solution Explorer**, expand **Mining Structures**.</span></span>  
  
2.  <span data-ttu-id="6be1b-111">Clique duas vezes em Call Center.dmm para abri-lo no designer.</span><span class="sxs-lookup"><span data-stu-id="6be1b-111">Double-click Call Center.dmm to open it in the designer.</span></span>  
  
3.  <span data-ttu-id="6be1b-112">No menu **Modelo de Mineração** , selecione **Novo Modelo de Mineração**.</span><span class="sxs-lookup"><span data-stu-id="6be1b-112">From the **Mining Model** menu, select **New Mining Model**.</span></span>  
  
4.  <span data-ttu-id="6be1b-113">Para o algoritmo, selecione **Regressão Linear da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="6be1b-113">For the algorithm, select **Microsoft Linear Regression**.</span></span> <span data-ttu-id="6be1b-114">Para o nome, digite **Regressão de Call Center**.</span><span class="sxs-lookup"><span data-stu-id="6be1b-114">For the name, type **Call Center Regression**.</span></span>  
  
5.  <span data-ttu-id="6be1b-115">Na guia **Modelos de Mineração** , altere o uso de colunas como a seguir.</span><span class="sxs-lookup"><span data-stu-id="6be1b-115">In the **Mining Models** tab, change the column usage as follows.</span></span> <span data-ttu-id="6be1b-116">Todas as colunas que não estiverem na lista a seguir deverão ser definidas como **Ignorar**, caso ainda não estejam.</span><span class="sxs-lookup"><span data-stu-id="6be1b-116">All columns not in the following list should be set to **Ignore**, if they are not already.</span></span>  
  
     <span data-ttu-id="6be1b-117">FactCallCenterID**Key**</span><span class="sxs-lookup"><span data-stu-id="6be1b-117">FactCallCenterID**Key**</span></span>  
  
     <span data-ttu-id="6be1b-118">ServiceGrade**PredictOnly**</span><span class="sxs-lookup"><span data-stu-id="6be1b-118">ServiceGrade**PredictOnly**</span></span>  
  
     <span data-ttu-id="6be1b-119">Total de operadores**Entrada**</span><span class="sxs-lookup"><span data-stu-id="6be1b-119">Total Operators**Input**</span></span>  
  
     <span data-ttu-id="6be1b-120">AverageTimePerIssue**Input**</span><span class="sxs-lookup"><span data-stu-id="6be1b-120">AverageTimePerIssue**Input**</span></span>  
  
6.  <span data-ttu-id="6be1b-121">No menu **Modelo de Mineração** , selecione **Definir Parâmetros do Modelo**.</span><span class="sxs-lookup"><span data-stu-id="6be1b-121">From the **Mining Model** menu, select **Set Model Parameters**.</span></span>  
  
7.  <span data-ttu-id="6be1b-122">Para o parâmetro FORCE_REGRESSOR, na coluna **Valor** , digite os nomes de colunas entre colchetes e separados por uma vírgula, como a seguir:</span><span class="sxs-lookup"><span data-stu-id="6be1b-122">For the parameter, FORCE_REGRESSOR, in the **Value** column, type the column names enclosed in brackets and separated by a comma, as follows:</span></span>  
  
    ```  
    [Average Time Per Issue],[Total Operators]  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="6be1b-123">O algoritmo detectará automaticamente que colunas são os melhores regressores.</span><span class="sxs-lookup"><span data-stu-id="6be1b-123">The algorithm will automatically detect which columns are the best regressors.</span></span> <span data-ttu-id="6be1b-124">Você precisará apenas impor os regressores quando desejar assegurar que uma coluna seja incluída na fórmula final.</span><span class="sxs-lookup"><span data-stu-id="6be1b-124">You only need to force regressors when you want to ensure that a column is included in the final formula.</span></span>  
  
8.  <span data-ttu-id="6be1b-125">No menu **Modelo de Mineração** , selecione **Processar Modelo**.</span><span class="sxs-lookup"><span data-stu-id="6be1b-125">From the **Mining Model** menu, select **Process Model**.</span></span>  
  
     <span data-ttu-id="6be1b-126">No visualizador, o modelo é representando como um único nó contendo a fórmula de regressão.</span><span class="sxs-lookup"><span data-stu-id="6be1b-126">In the viewer, the model is represented a single node containing the regression formula.</span></span> <span data-ttu-id="6be1b-127">Você poderá exibir a fórmula na **Legenda de Mineração**ou extrair os coeficientes da fórmula usando consultas.</span><span class="sxs-lookup"><span data-stu-id="6be1b-127">You can view the formula in the **Mining Legend**, or you can extract the coefficients for the formula by using queries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6be1b-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6be1b-128">See Also</span></span>  
 <span data-ttu-id="6be1b-129">[Algoritmo de regressão linear da Microsoft](microsoft-linear-regression-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="6be1b-129">[Microsoft Linear Regression Algorithm](microsoft-linear-regression-algorithm.md) </span></span>  
 <span data-ttu-id="6be1b-130">[Consultas de mineração de dados](data-mining-queries.md) </span><span class="sxs-lookup"><span data-stu-id="6be1b-130">[Data Mining Queries](data-mining-queries.md) </span></span>  
 <span data-ttu-id="6be1b-131">[Referência técnica do algoritmo regressão linear da Microsoft](microsoft-linear-regression-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="6be1b-131">[Microsoft Linear Regression Algorithm Technical Reference](microsoft-linear-regression-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="6be1b-132">Conteúdo do modelo de mineração para modelos de regressão linear &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="6be1b-132">Mining Model Content for Linear Regression Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-model-content-for-linear-regression-models-analysis-services-data-mining.md)  
  
  
