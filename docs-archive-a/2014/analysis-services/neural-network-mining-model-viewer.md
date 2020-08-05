---
title: Rede neural (Visualizador do modelo de mineração) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.neuralnet.f1
ms.assetid: 18d87e7b-a821-40ea-9bd8-c6fecf189a1c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 39ca8d3cd9f2a327abd8558b13a018ceda27968d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572728"
---
# <a name="neural-network-mining-model-viewer"></a><span data-ttu-id="9d383-102">Rede Neural (Visualizador do Modelo de Mineração)</span><span class="sxs-lookup"><span data-stu-id="9d383-102">Neural Network (Mining Model Viewer)</span></span>
  <span data-ttu-id="9d383-103">Use o visualizador da **Rede Neural** para explorar modelos de mineração que sejam baseados no algoritmo Rede Neural da [!INCLUDE[msCoName](../includes/msconame-md.md)] ou no algoritmo Regressão Logística da [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9d383-103">Use the **Neural Net** viewer to explore mining models that are based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Neural Network algorithm or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Logistic Regression algorithm.</span></span>  
  
 <span data-ttu-id="9d383-104">**Para obter mais informações:** [Algoritmo Rede Neural da Microsoft](data-mining/microsoft-neural-network-algorithm.md), [Algoritmo Regressão Logística da Microsoft](data-mining/microsoft-logistic-regression-algorithm.md),[Procurar um modelo usando o Visualizador da Rede Neural da Microsoft](data-mining/browse-a-model-using-the-microsoft-neural-network-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="9d383-104">**For More Information:** [Microsoft Neural Network Algorithm](data-mining/microsoft-neural-network-algorithm.md), [Microsoft Logistic Regression Algorithm](data-mining/microsoft-logistic-regression-algorithm.md),[Browse a Model Using the Microsoft Neural Network Viewer](data-mining/browse-a-model-using-the-microsoft-neural-network-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="9d383-105">Opções</span><span class="sxs-lookup"><span data-stu-id="9d383-105">Options</span></span>  
 <span data-ttu-id="9d383-106">**Atualizar conteúdo do visualizador**</span><span class="sxs-lookup"><span data-stu-id="9d383-106">**Refresh viewer content**</span></span>  
 <span data-ttu-id="9d383-107">Recarregue o modelo de mineração no visualizador.</span><span class="sxs-lookup"><span data-stu-id="9d383-107">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="9d383-108">**Modelo de mineração**</span><span class="sxs-lookup"><span data-stu-id="9d383-108">**Mining Model**</span></span>  
 <span data-ttu-id="9d383-109">Escolha um modelo de mineração a ser exibido, dentre eles na estrutura de mineração atual.</span><span class="sxs-lookup"><span data-stu-id="9d383-109">Choose a mining model to view, from those in the current mining structure.</span></span> <span data-ttu-id="9d383-110">O modelo de mineração será aberto no visualizador associado.</span><span class="sxs-lookup"><span data-stu-id="9d383-110">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="9d383-111">**Visualizador**</span><span class="sxs-lookup"><span data-stu-id="9d383-111">**Viewer**</span></span>  
 <span data-ttu-id="9d383-112">Escolha um visualizador a ser utilizado para explorar o modelo de mineração selecionado.</span><span class="sxs-lookup"><span data-stu-id="9d383-112">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="9d383-113">Você pode usar o visualizador personalizado, ou o **Visualizador de Árvore de Conteúdo Genérica da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="9d383-113">You can use the custom viewer, or the **Microsoft Generic Content Tree Viewer**.</span></span> <span data-ttu-id="9d383-114">Você também pode usar visualizadores de plug-in se houver.</span><span class="sxs-lookup"><span data-stu-id="9d383-114">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="9d383-115">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="9d383-115">**Input**</span></span>  
 <span data-ttu-id="9d383-116">Use esta área para escolher atributos de entrada e valores, para que você possa explorar posteriormente como eles afetam o resultado.</span><span class="sxs-lookup"><span data-stu-id="9d383-116">Use this area to choose input attributes and values, so that you can later explore how these affect the outcome.</span></span>  
  
|<span data-ttu-id="9d383-117">Valor</span><span class="sxs-lookup"><span data-stu-id="9d383-117">Value</span></span>|<span data-ttu-id="9d383-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="9d383-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9d383-119">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="9d383-119">**Attribute**</span></span>|<span data-ttu-id="9d383-120">Escolha um atributo de entrada na lista.</span><span class="sxs-lookup"><span data-stu-id="9d383-120">Choose an input attribute from the list.</span></span> <span data-ttu-id="9d383-121">Se você deixar a seleção como padrão, **\<All>** o gráfico mostrará uma lista de todos os atributos de entrada, classificados por seu impacto sobre o atributo previsível.</span><span class="sxs-lookup"><span data-stu-id="9d383-121">If you leave the selection as the default, **\<All>**, the chart shows a list of all input attributes, ranked by their impact on the predictable attribute.</span></span>|  
|<span data-ttu-id="9d383-122">**Valor**</span><span class="sxs-lookup"><span data-stu-id="9d383-122">**Value**</span></span>|<span data-ttu-id="9d383-123">Escolha um valor para o atributo de entrada.</span><span class="sxs-lookup"><span data-stu-id="9d383-123">Choose a value for the input attribute.</span></span>|  
  
 <span data-ttu-id="9d383-124">**Saída**</span><span class="sxs-lookup"><span data-stu-id="9d383-124">**Output**</span></span>  
 <span data-ttu-id="9d383-125">Use estes controles para escolher um atributo previsível e um valor para analisar e comparar no gráfico de barras.</span><span class="sxs-lookup"><span data-stu-id="9d383-125">Use these controls to choose a predictable attribute and value to analyze and compare in the bar graph.</span></span> <span data-ttu-id="9d383-126">Se você não alterar as seleções, o gráfico de barras comparará os dois principais estados de resultado.</span><span class="sxs-lookup"><span data-stu-id="9d383-126">If you do not change the selections, the bar graph compares the top two outcome states.</span></span>  
  
|<span data-ttu-id="9d383-127">Valor</span><span class="sxs-lookup"><span data-stu-id="9d383-127">Value</span></span>|<span data-ttu-id="9d383-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="9d383-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9d383-129">**Atributo de Saída**</span><span class="sxs-lookup"><span data-stu-id="9d383-129">**Output Attribute**</span></span>|<span data-ttu-id="9d383-130">Escolha um atributo previsível.</span><span class="sxs-lookup"><span data-stu-id="9d383-130">Choose a predictable attribute.</span></span> <span data-ttu-id="9d383-131">Se você não definiu a coluna como previsível ao criar o modelo, não poderá adicioná-la aqui.</span><span class="sxs-lookup"><span data-stu-id="9d383-131">If you did not define the column as a predictable one when you created the model, you cannot add it here.</span></span>|  
|<span data-ttu-id="9d383-132">**Valor 1**</span><span class="sxs-lookup"><span data-stu-id="9d383-132">**Value 1**</span></span>|<span data-ttu-id="9d383-133">Escolha um estado do atributo previsível a ser comparado com a condição que está contida em **Valor 2**.</span><span class="sxs-lookup"><span data-stu-id="9d383-133">Choose a state of the predictable attribute to compare to the state that is contained in **Value 2**.</span></span><br /><br /> <span data-ttu-id="9d383-134">Você pode comparar dois valores discretos ou diferenciados; porém, não pode comparar um valor com seu complemento, como pode em outros visualizadores.</span><span class="sxs-lookup"><span data-stu-id="9d383-134">You can compare any two discrete or discretized values; however, you cannot compare a value to its complement, as you can in other viewers.</span></span>|  
|<span data-ttu-id="9d383-135">**Valor 2**</span><span class="sxs-lookup"><span data-stu-id="9d383-135">**Value 2**</span></span>|<span data-ttu-id="9d383-136">Selecione o estado do atributo previsível a ser comparado com o estado que está contido em **Valor 1**.</span><span class="sxs-lookup"><span data-stu-id="9d383-136">Select a state of the predictable attribute to compare to the state that is contained in **Value 1**.</span></span>|  
  
 <span data-ttu-id="9d383-137">**Variáveis**</span><span class="sxs-lookup"><span data-stu-id="9d383-137">**Variables**</span></span>  
 <span data-ttu-id="9d383-138">Esta parte da guia **Rede Neural** contém um gráfico de barras interativo que responde às seleções que você fez para atributos de entrada e de resultado.</span><span class="sxs-lookup"><span data-stu-id="9d383-138">This part of the **Neural Network** tab contains an interactive bar graph, which responds to the selections that you made for input and outcome attributes.</span></span> <span data-ttu-id="9d383-139">Como uma rede neural calcula a probabilidade de um valor específico influenciar um resultado específico, você pode escolher qualquer combinação de entradas e o gráfico de barras exibirá como essa combinação afetará o par de resultados que você está comparando.</span><span class="sxs-lookup"><span data-stu-id="9d383-139">Because a neural network calculates the likelihood that a particular value influences a particular outcome, you can choose any combination of inputs, and the bar chart will display how that combination affects the pair of outcomes that you are comparing.</span></span>  
  
|<span data-ttu-id="9d383-140">Valor</span><span class="sxs-lookup"><span data-stu-id="9d383-140">Value</span></span>|<span data-ttu-id="9d383-141">Descrição</span><span class="sxs-lookup"><span data-stu-id="9d383-141">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9d383-142">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="9d383-142">**Attribute**</span></span>|<span data-ttu-id="9d383-143">Mostra o nome do atributo de entrada selecionado em **Atributo**.</span><span class="sxs-lookup"><span data-stu-id="9d383-143">Shows the name of the input attribute you selected in **Attribute**.</span></span>|  
|<span data-ttu-id="9d383-144">**Valor**</span><span class="sxs-lookup"><span data-stu-id="9d383-144">**Value**</span></span>|<span data-ttu-id="9d383-145">Mostra o valor para o atributo de entrada selecionado.</span><span class="sxs-lookup"><span data-stu-id="9d383-145">Shows the value for the selected input attribute.</span></span>|  
|<span data-ttu-id="9d383-146">**Enfatiza\<Value 1>**</span><span class="sxs-lookup"><span data-stu-id="9d383-146">**Favors \<Value 1>**</span></span>|<span data-ttu-id="9d383-147">Exibe uma barra que indica quanto esta combinação específica de atributo e valor afeta o resultado de destino escolhido em **Valor 1**.</span><span class="sxs-lookup"><span data-stu-id="9d383-147">Displays a bar that indicates how much this particular attribute-value combination affects the target outcome chosen in **Value 1**.</span></span>|  
|<span data-ttu-id="9d383-148">**Enfatiza\<Value 2>**</span><span class="sxs-lookup"><span data-stu-id="9d383-148">**Favors \<Value 2>**</span></span>|<span data-ttu-id="9d383-149">Exibe uma barra que indica quanto esta combinação específica de atributo e valor afeta o resultado de destino escolhido em **Valor 2**.</span><span class="sxs-lookup"><span data-stu-id="9d383-149">Displays a bar that indicates how much this particular attribute-value combination affects the target outcome chosen in **Value 2**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9d383-150">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9d383-150">See Also</span></span>  
 <span data-ttu-id="9d383-151">[Algoritmos de mineração de dados &#40;mineração de dados Analysis Services&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="9d383-151">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="9d383-152">[Visualizadores de modelo de mineração &#40;designer de modelo de mineração de dados&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="9d383-152">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="9d383-153">Visualizadores do Modelo de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="9d383-153">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
