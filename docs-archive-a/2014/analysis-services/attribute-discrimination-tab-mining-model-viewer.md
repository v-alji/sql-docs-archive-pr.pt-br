---
title: Guia discriminação de atributo (Visualizador do modelo de mineração) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.naivebayse.discrimination.f1
ms.assetid: 68323f23-121e-44fc-be85-6f9915d6d3c7
author: minewiskan
ms.author: owend
ms.openlocfilehash: a8b0d4bc99b1c8f1c5de0269312f02eeb09df022
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571175"
---
# <a name="attribute-discrimination-tab-mining-model-viewer"></a><span data-ttu-id="82d00-102">Guia Distinção de Atributo (Visualizador do Modelo de Mineração)</span><span class="sxs-lookup"><span data-stu-id="82d00-102">Attribute Discrimination Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="82d00-103">Utilize a guia **Distinção de Atributo** para comparar os estados dos atributos de entrada e ver como eles estão relacionados aos atributos de saída.</span><span class="sxs-lookup"><span data-stu-id="82d00-103">Use the **Attribute Discrimination** tab to compare the states of the input attributes and see how they are related to the outcome attribute.</span></span> <span data-ttu-id="82d00-104">Os valores de atributo que compõem a maior diferença entre os dois estados de atributos previsíveis são listados em primeiro lugar.</span><span class="sxs-lookup"><span data-stu-id="82d00-104">The attribute values that make the most difference between the two selected predictable attribute states are listed first.</span></span>  
  
 <span data-ttu-id="82d00-105">**Para obter mais informações:** [Algoritmo Microsoft Naive Bayes](data-mining/microsoft-naive-bayes-algorithm.md), [Procurar um modelo usando o Visualizador Naive Bayes da Microsoft](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="82d00-105">**For More Information:** [Microsoft Naive Bayes Algorithm](data-mining/microsoft-naive-bayes-algorithm.md), [Browse a Model Using the Microsoft Naive Bayes Viewer](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="82d00-106">Opções</span><span class="sxs-lookup"><span data-stu-id="82d00-106">Options</span></span>  
 <span data-ttu-id="82d00-107">**Atualizar conteúdo do visualizador**</span><span class="sxs-lookup"><span data-stu-id="82d00-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="82d00-108">Recarregue o modelo de mineração no visualizador.</span><span class="sxs-lookup"><span data-stu-id="82d00-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="82d00-109">**Modelo de mineração**</span><span class="sxs-lookup"><span data-stu-id="82d00-109">**Mining Model**</span></span>  
 <span data-ttu-id="82d00-110">Escolha um modelo de mineração dentre eles na estrutura de mineração atual.</span><span class="sxs-lookup"><span data-stu-id="82d00-110">Choose a mining model from those in the current mining structure.</span></span> <span data-ttu-id="82d00-111">O modelo de mineração é aberto automaticamente no visualizador personalizado correto.</span><span class="sxs-lookup"><span data-stu-id="82d00-111">The mining model automatically opens in the correct custom viewer.</span></span>  
  
 <span data-ttu-id="82d00-112">**Visualizador**</span><span class="sxs-lookup"><span data-stu-id="82d00-112">**Viewer**</span></span>  
 <span data-ttu-id="82d00-113">Escolha um visualizador a ser utilizado para explorar o modelo de mineração selecionado.</span><span class="sxs-lookup"><span data-stu-id="82d00-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="82d00-114">Para cada modelo, você pode escolher um visualizador personalizado ou o Visualizador de Conteúdo de Mineração da [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="82d00-114">For each model, you can choose either the custom viewer, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="82d00-115">Você também pode usar visualizadores de plug-in se houver.</span><span class="sxs-lookup"><span data-stu-id="82d00-115">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="82d00-116">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="82d00-116">**Attribute**</span></span>  
 <span data-ttu-id="82d00-117">Escolha um atributo previsível.</span><span class="sxs-lookup"><span data-stu-id="82d00-117">Choose a predictable attribute.</span></span>  
  
 <span data-ttu-id="82d00-118">**Valor 1**</span><span class="sxs-lookup"><span data-stu-id="82d00-118">**Value 1**</span></span>  
 <span data-ttu-id="82d00-119">Escolha um estado do atributo previsível a ser comparado com a condição que está contida em **Valor 2**.</span><span class="sxs-lookup"><span data-stu-id="82d00-119">Choose a state of the predictable attribute to compare to the state that is contained in **Value 2**.</span></span>  
  
 <span data-ttu-id="82d00-120">**Valor 2**</span><span class="sxs-lookup"><span data-stu-id="82d00-120">**Value 2**</span></span>  
 <span data-ttu-id="82d00-121">Selecione o estado do atributo previsível a ser comparado com o estado que está contido em **Valor 1**.</span><span class="sxs-lookup"><span data-stu-id="82d00-121">Select a state of the predictable attribute to compare to the state that is contained in **Value 1**.</span></span> <span data-ttu-id="82d00-122">Você também pode selecionar **todos os outros Estados** para comparar o valor no **valor 1** com seu complemento – ou seja, todos os outros valores, exceto o valor 1.</span><span class="sxs-lookup"><span data-stu-id="82d00-122">You can also select **All Other States** to compare the value in **Value 1** with its complement-that is, all other values except Value 1.</span></span>  
  
 <span data-ttu-id="82d00-123">**Pontuações de discriminação para \<Value 1> e\<Value 2>**</span><span class="sxs-lookup"><span data-stu-id="82d00-123">**Discrimination scores for \<Value 1> and \<Value 2>**</span></span>  
 <span data-ttu-id="82d00-124">O gráfico contém as seguintes colunas, que descrevem como o atributo de destino está relacionado aos estados específicos do atributo de entrada.</span><span class="sxs-lookup"><span data-stu-id="82d00-124">The graph contains the following columns, which describe how the target attribute is related to specific states of the input attribute.</span></span>  
  
|<span data-ttu-id="82d00-125">Valor</span><span class="sxs-lookup"><span data-stu-id="82d00-125">Value</span></span>|<span data-ttu-id="82d00-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="82d00-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="82d00-127">**Atributos**</span><span class="sxs-lookup"><span data-stu-id="82d00-127">**Attributes**</span></span>|<span data-ttu-id="82d00-128">Um atributo de entrada no modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="82d00-128">An input attribute in the mining model.</span></span>|  
|<span data-ttu-id="82d00-129">**Valores**</span><span class="sxs-lookup"><span data-stu-id="82d00-129">**Values**</span></span>|<span data-ttu-id="82d00-130">Um estado do atributo listado em **Atributos**.</span><span class="sxs-lookup"><span data-stu-id="82d00-130">A state of the attribute that is listed in **Attributes**.</span></span>|  
|<span data-ttu-id="82d00-131">**Enfatiza\<Value 1>**</span><span class="sxs-lookup"><span data-stu-id="82d00-131">**Favors \<Value 1>**</span></span>|<span data-ttu-id="82d00-132">A barra indica se o atributo atual e valor favorecem o resultado de destino selecionado em **Valor 1**.</span><span class="sxs-lookup"><span data-stu-id="82d00-132">The bar indicates whether the current attribute and value favor the target outcome selected in **Value 1**.</span></span>|  
|<span data-ttu-id="82d00-133">**Enfatiza\<Value 2>**</span><span class="sxs-lookup"><span data-stu-id="82d00-133">**Favors \<Value 2>**</span></span>|<span data-ttu-id="82d00-134">A barra indica se o atributo atual e valor favorecem o resultado de destino selecionado em **Valor 2**.</span><span class="sxs-lookup"><span data-stu-id="82d00-134">The bar indicates whether the current attribute and value favor the target outcome selected in **Value 2**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="82d00-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="82d00-135">See Also</span></span>  
 <span data-ttu-id="82d00-136">[Algoritmos de mineração de dados &#40;mineração de dados Analysis Services&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="82d00-136">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="82d00-137">[Visualizadores de modelo de mineração &#40;designer de modelo de mineração de dados&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="82d00-137">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="82d00-138">Visualizadores do Modelo de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="82d00-138">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
