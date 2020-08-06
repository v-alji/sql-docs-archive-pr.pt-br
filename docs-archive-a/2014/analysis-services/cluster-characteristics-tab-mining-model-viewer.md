---
title: Guia características do cluster (Visualizador do modelo de mineração) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.clustering.characteristics.f1
ms.assetid: 8e33ed1d-1ce4-405d-895b-7e995b2c910d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 959d94767b6cb27d9ebb6e06c592034fca20ac89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571069"
---
# <a name="cluster-characteristics-tab-mining-model-viewer"></a><span data-ttu-id="7a104-102">Guia Características do Cluster (Visualizador do Modelo de Mineração)</span><span class="sxs-lookup"><span data-stu-id="7a104-102">Cluster Characteristics Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="7a104-103">A guia **Características de Cluster** permite explorar as características de um cluster em um modelo de clustering ou o conjunto de todos os casos no modelo.</span><span class="sxs-lookup"><span data-stu-id="7a104-103">The **Cluster Characteristics** tab lets you explore the characteristics of a cluster in a clustering model, or the set of all cases in the model.</span></span> <span data-ttu-id="7a104-104">O gráfico mostra a importância de cada par atributo-valor como uma característica que define o cluster, em comparação com outros clusters.</span><span class="sxs-lookup"><span data-stu-id="7a104-104">The graph shows the importance of each attribute-value pair as a characteristic that defines the cluster, in comparison with other clusters.</span></span>  
  
 <span data-ttu-id="7a104-105">**Para obter mais informações:** [Algoritmo MSC](data-mining/microsoft-clustering-algorithm.md), [Procurar um modelo usando o Visualizador de Cluster da Microsoft](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="7a104-105">**For More Information:** [Microsoft Clustering Algorithm](data-mining/microsoft-clustering-algorithm.md), [Browse a Model Using the Microsoft Cluster Viewer](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="7a104-106">Opções</span><span class="sxs-lookup"><span data-stu-id="7a104-106">Options</span></span>  
 <span data-ttu-id="7a104-107">**Atualizar conteúdo do visualizador**</span><span class="sxs-lookup"><span data-stu-id="7a104-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="7a104-108">Recarregue o modelo de mineração no visualizador.</span><span class="sxs-lookup"><span data-stu-id="7a104-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="7a104-109">**Modelo de mineração**</span><span class="sxs-lookup"><span data-stu-id="7a104-109">**Mining Model**</span></span>  
 <span data-ttu-id="7a104-110">Escolha um modelo de mineração dentre eles na estrutura de mineração atual.</span><span class="sxs-lookup"><span data-stu-id="7a104-110">Choose a mining model from those in the current mining structure.</span></span> <span data-ttu-id="7a104-111">O modelo de mineração será aberto no visualizador personalizado.</span><span class="sxs-lookup"><span data-stu-id="7a104-111">The mining model will open in the custom viewer.</span></span>  
  
 <span data-ttu-id="7a104-112">**Visualizador**</span><span class="sxs-lookup"><span data-stu-id="7a104-112">**Viewer**</span></span>  
 <span data-ttu-id="7a104-113">Escolha um visualizador a ser utilizado para explorar o modelo de mineração selecionado.</span><span class="sxs-lookup"><span data-stu-id="7a104-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="7a104-114">Você pode usar o visualizador personalizado associado a esse tipo de modelo, ou o Visualizador de Conteúdo de Mineração do [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7a104-114">You can use the custom viewer associated with this model type, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="7a104-115">Você também pode usar visualizadores de plug-in que estiverem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="7a104-115">You can also use any plug-in viewers that are available.</span></span>  
  
 <span data-ttu-id="7a104-116">**Cluster**</span><span class="sxs-lookup"><span data-stu-id="7a104-116">**Cluster**</span></span>  
 <span data-ttu-id="7a104-117">Escolha o cluster que você deseja exibir ou escolha **População (Tudo)** para ver a distribuição de atributos para o modelo como um todo.</span><span class="sxs-lookup"><span data-stu-id="7a104-117">Choose the cluster you want to view, or choose **Population (All)** to see the distribution of attributes for the model as a whole.</span></span>  
  
 <span data-ttu-id="7a104-118">**Características de\<cluster>**</span><span class="sxs-lookup"><span data-stu-id="7a104-118">**Characteristics for \<cluster>**</span></span>  
 <span data-ttu-id="7a104-119">O gráfico contém as seguintes colunas, que descrevem as características do cluster selecionado.</span><span class="sxs-lookup"><span data-stu-id="7a104-119">The graph contains the following columns, which describe the characteristics of the selected cluster.</span></span>  
  
|<span data-ttu-id="7a104-120">Valor</span><span class="sxs-lookup"><span data-stu-id="7a104-120">Value</span></span>|<span data-ttu-id="7a104-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="7a104-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7a104-122">**Variável**</span><span class="sxs-lookup"><span data-stu-id="7a104-122">**Variable**</span></span>|<span data-ttu-id="7a104-123">Lista os atributos do modelo de mineração que são localizados no cluster selecionado.</span><span class="sxs-lookup"><span data-stu-id="7a104-123">Lists the attributes from the mining model that are found in the selected cluster.</span></span>|  
|<span data-ttu-id="7a104-124">**Valores**</span><span class="sxs-lookup"><span data-stu-id="7a104-124">**Values**</span></span>|<span data-ttu-id="7a104-125">Lista os valores dos atributos atuais que são localizados no cluster selecionado atualmente.</span><span class="sxs-lookup"><span data-stu-id="7a104-125">Lists the values of the current attributes that are found in the currently selected cluster.</span></span>|  
|<span data-ttu-id="7a104-126">**Probabilidade**</span><span class="sxs-lookup"><span data-stu-id="7a104-126">**Probability**</span></span>|<span data-ttu-id="7a104-127">A barra indica a força do par atributo-valor como um recurso distintivo deste cluster.</span><span class="sxs-lookup"><span data-stu-id="7a104-127">The bar indicates the strength of the attribute-value pair as a distinguishing feature of this cluster.</span></span> <span data-ttu-id="7a104-128">Se você passar o mouse sobre a barra, poderá ver o valor da probabilidade, representado como uma porcentagem.</span><span class="sxs-lookup"><span data-stu-id="7a104-128">If you hover the mouse over the bar, you can see the probability value, represented as a percentage.</span></span> <span data-ttu-id="7a104-129">O que isso indica é, considerando esta combinação de atributo e valor neste caso específico, qual é a probabilidade desse caso pertencer a este cluster.</span><span class="sxs-lookup"><span data-stu-id="7a104-129">What this indicates is, given this attribute and value combination in any particular case, what is the probability that the case would belong in this cluster.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7a104-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7a104-130">See Also</span></span>  
 <span data-ttu-id="7a104-131">[Algoritmos de mineração de dados &#40;mineração de dados Analysis Services&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="7a104-131">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="7a104-132">[Visualizadores de modelo de mineração &#40;designer de modelo de mineração de dados&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="7a104-132">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="7a104-133">Visualizadores do Modelo de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="7a104-133">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
