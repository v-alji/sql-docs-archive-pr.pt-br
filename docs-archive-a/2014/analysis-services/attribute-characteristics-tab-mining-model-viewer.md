---
title: Guia características do atributo (Visualizador do modelo de mineração) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.naivebayse.characteristics.f1
ms.assetid: f0c3350d-84c0-4ab8-9fb8-1527c2647299
author: minewiskan
ms.author: owend
ms.openlocfilehash: b29ba482c21bb674a10bc4c9e6c6eccdf30905dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571180"
---
# <a name="attribute-characteristics-tab-mining-model-viewer"></a><span data-ttu-id="7ce02-102">Guia Características de Atributo (Visualizador do Modelo de Mineração)</span><span class="sxs-lookup"><span data-stu-id="7ce02-102">Attribute Characteristics Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="7ce02-103">Use o painel **Características do Atributo** para explorar as relações entre resultados e atributos de entrada em um modelo de Naïve Bayes.</span><span class="sxs-lookup"><span data-stu-id="7ce02-103">Use the **Attribute Characteristics** pane to explore the relationships between outcomes and input attributes in a Naïve Bayes model.</span></span> <span data-ttu-id="7ce02-104">Você pode escolher o valor do atributo de destino e, em seguida, ver uma lista de atributos de entrada que tiverem o efeito mais forte nos resultados.</span><span class="sxs-lookup"><span data-stu-id="7ce02-104">You can choose the value of the target attribute, and then see a list of the input attributes that have the strongest effect on the outcomes.</span></span>  
  
 <span data-ttu-id="7ce02-105">**Para obter mais informações:** [Algoritmo Microsoft Naive Bayes](data-mining/microsoft-naive-bayes-algorithm.md), [Procurar um modelo usando o Visualizador Naive Bayes da Microsoft](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="7ce02-105">**For More Information:** [Microsoft Naive Bayes Algorithm](data-mining/microsoft-naive-bayes-algorithm.md), [Browse a Model Using the Microsoft Naive Bayes Viewer](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="7ce02-106">Opções</span><span class="sxs-lookup"><span data-stu-id="7ce02-106">Options</span></span>  
 <span data-ttu-id="7ce02-107">**Atualizar conteúdo do visualizador**</span><span class="sxs-lookup"><span data-stu-id="7ce02-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="7ce02-108">Recarregue o modelo de mineração no visualizador.</span><span class="sxs-lookup"><span data-stu-id="7ce02-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="7ce02-109">**Modelo de mineração**</span><span class="sxs-lookup"><span data-stu-id="7ce02-109">**Mining Model**</span></span>  
 <span data-ttu-id="7ce02-110">Escolha um modelo de mineração a ser exibido, dos modelos na estrutura de mineração atual.</span><span class="sxs-lookup"><span data-stu-id="7ce02-110">Choose a mining model to view, from the models in the current mining structure.</span></span> <span data-ttu-id="7ce02-111">O modelo de mineração abrirá automaticamente em um visualizador personalizado que seja melhor para o tipo específico de modelo você escolheu.</span><span class="sxs-lookup"><span data-stu-id="7ce02-111">The mining model will automatically open in a custom viewer that is best for the particular type of model you chose.</span></span>  
  
 <span data-ttu-id="7ce02-112">**Visualizador**</span><span class="sxs-lookup"><span data-stu-id="7ce02-112">**Viewer**</span></span>  
 <span data-ttu-id="7ce02-113">Escolha um visualizador a ser utilizado para explorar o modelo de mineração selecionado.</span><span class="sxs-lookup"><span data-stu-id="7ce02-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="7ce02-114">Para cada modelo, você tem a escolha de um visualizador personalizado ou o Visualizador de Conteúdo de Mineração da [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7ce02-114">For each model, you have the choice of a custom viewer, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="7ce02-115">Os visualizadores de plug-in também serão exibidos, se houver.</span><span class="sxs-lookup"><span data-stu-id="7ce02-115">Plug-in viewers also appear in this list if available.</span></span>  
  
 <span data-ttu-id="7ce02-116">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="7ce02-116">**Attribute**</span></span>  
 <span data-ttu-id="7ce02-117">Escolha o atributo previsível que você deseja analisar.</span><span class="sxs-lookup"><span data-stu-id="7ce02-117">Choose the predictable attribute that you want to analyze.</span></span>  
  
 <span data-ttu-id="7ce02-118">**Valor**</span><span class="sxs-lookup"><span data-stu-id="7ce02-118">**Value**</span></span>  
 <span data-ttu-id="7ce02-119">Escolha um estado para os atributos previsíveis definidos em **Atributo**.</span><span class="sxs-lookup"><span data-stu-id="7ce02-119">Choose a state for the predictable attribute that you set in **Attribute**.</span></span> <span data-ttu-id="7ce02-120">Como os modelos de Naïve Bayes não dão suporte a variáveis contínuas, todos os atributos de destino têm resultados discretos ou diferenciados.</span><span class="sxs-lookup"><span data-stu-id="7ce02-120">Because Naïve Bayes models do not support continuous variables, all target attributes have discrete or discretized outcomes.</span></span> <span data-ttu-id="7ce02-121">O atributo Ausente sempre é adicionado automaticamente à lista.</span><span class="sxs-lookup"><span data-stu-id="7ce02-121">The Missing attribute is always automatically added to the list.</span></span>  
  
 <span data-ttu-id="7ce02-122">**Características de\<predictable state>**</span><span class="sxs-lookup"><span data-stu-id="7ce02-122">**Characteristics for \<predictable state>**</span></span>  
 <span data-ttu-id="7ce02-123">O gráfico contém as seguintes colunas, que descrevem como os estados dos atributos de entrada estão relacionados ao estado do atributo previsível.</span><span class="sxs-lookup"><span data-stu-id="7ce02-123">The graph contains the following columns, which describe how states of the input attributes are related to the selected predictable attribute state.</span></span>  
  
|<span data-ttu-id="7ce02-124">Valor</span><span class="sxs-lookup"><span data-stu-id="7ce02-124">Value</span></span>|<span data-ttu-id="7ce02-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="7ce02-125">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7ce02-126">**Variável**</span><span class="sxs-lookup"><span data-stu-id="7ce02-126">**Variable**</span></span>|<span data-ttu-id="7ce02-127">Lista os atributos de entrada no modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="7ce02-127">Lists the input attributes in the mining model.</span></span>|  
|<span data-ttu-id="7ce02-128">**Valores**</span><span class="sxs-lookup"><span data-stu-id="7ce02-128">**Values**</span></span>|<span data-ttu-id="7ce02-129">Lista cada estado do atributo de entrada em **Variáveis**.</span><span class="sxs-lookup"><span data-stu-id="7ce02-129">Lists each state of the input attribute in **Variable**.</span></span>|  
|<span data-ttu-id="7ce02-130">**Probabilidade**</span><span class="sxs-lookup"><span data-stu-id="7ce02-130">**Probability**</span></span>|<span data-ttu-id="7ce02-131">A barra representa a probabilidade de que o atributo e o valor na linha estejam associados ao estado selecionado a partir do atributo previsível.</span><span class="sxs-lookup"><span data-stu-id="7ce02-131">The bar represents the probability that the attribute and value in that row are associated with the selected state of the predictable attribute.</span></span> <span data-ttu-id="7ce02-132">Passe o mouse sobre a barra para exibir a probabilidade como um percentual.</span><span class="sxs-lookup"><span data-stu-id="7ce02-132">Hover the mouse over the bar to view the probability as a percentage.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7ce02-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7ce02-133">See Also</span></span>  
 <span data-ttu-id="7ce02-134">[Algoritmos de mineração de dados &#40;mineração de dados Analysis Services&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="7ce02-134">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="7ce02-135">[Visualizadores de modelo de mineração &#40;designer de modelo de mineração de dados&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="7ce02-135">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="7ce02-136">Visualizadores do Modelo de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="7ce02-136">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
