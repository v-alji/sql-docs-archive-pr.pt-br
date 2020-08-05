---
title: Guia perfis de cluster (Visualizador do modelo de mineração) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.clustering.profiles.f1
ms.assetid: 1ebafa1f-74e9-4c05-b278-a690fa8543bd
author: minewiskan
ms.author: owend
ms.openlocfilehash: a7ec1ce5b5204ae81a9313ca7b7e5df58c98c5da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571689"
---
# <a name="cluster-profiles-tab-mining-model-viewer"></a><span data-ttu-id="5007d-102">Guia Perfis de Cluster (Visualizador do Modelo de Mineração)</span><span class="sxs-lookup"><span data-stu-id="5007d-102">Cluster Profiles Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="5007d-103">Use a guia **Perfis de Cluster** para obter uma exibição global dos clusters que o algoritmo descobriu dentro de um modelo de clustering.</span><span class="sxs-lookup"><span data-stu-id="5007d-103">Use the **Cluster Profiles** tab for an overall view of the clusters that the algorithm discovered within a clustering model.</span></span> <span data-ttu-id="5007d-104">A guia exibe cada atributo, junto com a distribuição do atributo em cada cluster.</span><span class="sxs-lookup"><span data-stu-id="5007d-104">The tab displays each attribute, together with the distribution of the attribute in each cluster.</span></span>  
  
 <span data-ttu-id="5007d-105">**Para obter mais informações:** [Algoritmo MSC](data-mining/microsoft-clustering-algorithm.md), [Procurar um modelo usando o Visualizador de Cluster da Microsoft](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="5007d-105">**For More Information:** [Microsoft Clustering Algorithm](data-mining/microsoft-clustering-algorithm.md), [Browse a Model Using the Microsoft Cluster Viewer](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="5007d-106">Opções</span><span class="sxs-lookup"><span data-stu-id="5007d-106">Options</span></span>  
 <span data-ttu-id="5007d-107">**Atualizar conteúdo do visualizador**</span><span class="sxs-lookup"><span data-stu-id="5007d-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="5007d-108">Recarregue o modelo de mineração no visualizador.</span><span class="sxs-lookup"><span data-stu-id="5007d-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="5007d-109">**Modelo de mineração**</span><span class="sxs-lookup"><span data-stu-id="5007d-109">**Mining Model**</span></span>  
 <span data-ttu-id="5007d-110">Escolha um modelo de mineração dentre eles na estrutura de mineração atual.</span><span class="sxs-lookup"><span data-stu-id="5007d-110">Choose a mining model from those in the current mining structure.</span></span> <span data-ttu-id="5007d-111">O modelo de mineração será aberto no visualizador associado.</span><span class="sxs-lookup"><span data-stu-id="5007d-111">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="5007d-112">**Visualizador**</span><span class="sxs-lookup"><span data-stu-id="5007d-112">**Viewer**</span></span>  
 <span data-ttu-id="5007d-113">Escolha um visualizador para exibir o modelo de mineração selecionado.</span><span class="sxs-lookup"><span data-stu-id="5007d-113">Choose a viewer to use to view the selected mining model.</span></span> <span data-ttu-id="5007d-114">Você pode usar o visualizador personalizado para o modelo de mineração, ou Visualizador de Conteúdo de Mineração da [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5007d-114">You can use the custom viewer for the mining model, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="5007d-115">Você também pode usar visualizadores de plug-in se houver.</span><span class="sxs-lookup"><span data-stu-id="5007d-115">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="5007d-116">**Mostrar Legenda**</span><span class="sxs-lookup"><span data-stu-id="5007d-116">**Show Legend**</span></span>  
 <span data-ttu-id="5007d-117">Escolha esta opção para exibir uma chave que mostra o mapeamento de cores no visualizador para valores na coluna **Estados** .</span><span class="sxs-lookup"><span data-stu-id="5007d-117">Select this option to display a key that shows the mapping of colors in the viewer to values in the **States** column.</span></span>  
  
 <span data-ttu-id="5007d-118">**Barras de histograma**</span><span class="sxs-lookup"><span data-stu-id="5007d-118">**Histogram Bars**</span></span>  
 <span data-ttu-id="5007d-119">Altere este valor para controlar quantos estados estão incluídos em cada histograma.</span><span class="sxs-lookup"><span data-stu-id="5007d-119">Change this value to control how many states are included in each histogram.</span></span> <span data-ttu-id="5007d-120">Se houver mais estados do que você opte por exibir, os estados de maior importância serão mostrados no histograma e os restantes serão agrupados em **Outras**.</span><span class="sxs-lookup"><span data-stu-id="5007d-120">If there are more states than you choose to display, the states with the highest probability are shown in the histogram, and the remaining states are grouped together into **Other**.</span></span>  
  
 <span data-ttu-id="5007d-121">**Atributos**</span><span class="sxs-lookup"><span data-stu-id="5007d-121">**Attributes**</span></span>  
 <span data-ttu-id="5007d-122">Lista as colunas que estão no modelo de clustering.</span><span class="sxs-lookup"><span data-stu-id="5007d-122">Lists the columns that are in the clustering model.</span></span> <span data-ttu-id="5007d-123">Os histogramas para cada atributo mostram como ele é distribuído entre os clusters identificados pelo algoritmo.</span><span class="sxs-lookup"><span data-stu-id="5007d-123">The histograms for each attribute show how the attribute is distributed among the clusters identified by the algorithm.</span></span>  
  
 <span data-ttu-id="5007d-124">**Estados**</span><span class="sxs-lookup"><span data-stu-id="5007d-124">**States**</span></span>  
 <span data-ttu-id="5007d-125">Fornece uma chave que denota que cor representa cada estado na linha de clusters correspondente, ou um controle deslizante com losango que indica a distribuição de valores numéricos contínuos.</span><span class="sxs-lookup"><span data-stu-id="5007d-125">Provides a key that either denotes what color represents each state in the corresponding row of clusters, or a slider with diamond that indicates the distribution of continuous numeric values.</span></span> <span data-ttu-id="5007d-126">Você pode mostrar ou ocultar esta coluna usando a caixa de seleção **Mostrar Legenda** .</span><span class="sxs-lookup"><span data-stu-id="5007d-126">You can show or hide this column by using the **Show Legend** check box.</span></span>  
  
 <span data-ttu-id="5007d-127">**Perfis de cluster**</span><span class="sxs-lookup"><span data-stu-id="5007d-127">**Cluster Profiles**</span></span>  
 <span data-ttu-id="5007d-128">Esta seção contém uma coluna para cada cluster no modelo.</span><span class="sxs-lookup"><span data-stu-id="5007d-128">This section contains a column for each cluster in the model.</span></span> <span data-ttu-id="5007d-129">Para cada atributo, o histograma mostra a distribuição dos valores no atributo somente para esse cluster.</span><span class="sxs-lookup"><span data-stu-id="5007d-129">For each attribute, the histogram shows the distribution of the values in the attribute for just that cluster.</span></span> <span data-ttu-id="5007d-130">O gráfico também tem uma coluna para **População**, que também usa histogramas para exibir a distribuição de valores para cada atributo, mas para todos os casos no modelo.</span><span class="sxs-lookup"><span data-stu-id="5007d-130">The chart also has a column for **Population**, which also uses histograms to display the distribution of values for each attribute, but for all cases in the model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5007d-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5007d-131">See Also</span></span>  
 <span data-ttu-id="5007d-132">[Algoritmos de mineração de dados &#40;mineração de dados Analysis Services&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="5007d-132">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="5007d-133">[Visualizadores de modelo de mineração &#40;designer de modelo de mineração de dados&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="5007d-133">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="5007d-134">Visualizadores do Modelo de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="5007d-134">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
