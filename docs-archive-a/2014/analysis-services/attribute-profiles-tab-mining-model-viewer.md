---
title: Guia perfis de atributo (Visualizador do modelo de mineração) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.naivebayse.profiles.f1
ms.assetid: 17c7e7ae-273c-4a6b-9a35-e8b9b8e65999
author: minewiskan
ms.author: owend
ms.openlocfilehash: 61c81b95f030bf1a69aed165bd64e58ff9af8339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571170"
---
# <a name="attribute-profiles-tab-mining-model-viewer"></a><span data-ttu-id="8bba3-102">Guia Perfis de Atributo (Visualizador do Modelo de Mineração)</span><span class="sxs-lookup"><span data-stu-id="8bba3-102">Attribute Profiles Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="8bba3-103">Utilize a guia **Perfis de Atributo** para ver como a distribuição de valores de entrada em um estado de modelo Naive Bayes contribui para cada estado do atributo de resultado.</span><span class="sxs-lookup"><span data-stu-id="8bba3-103">Use the **Attribute Profiles** tab to see how the distribution of input values in a Naive Bayes model state contribute to each state of the outcome attribute.</span></span> <span data-ttu-id="8bba3-104">A distribuição de valores é mostrada como um histograma colorido, todas as distribuições apresentadas em um formato de tabela, para facilitar a comparação de valores.</span><span class="sxs-lookup"><span data-stu-id="8bba3-104">The distribution of values is shown as a colored histogram, all distributions presented in a tabular format, to make it easier to compare values.</span></span>  
  
 <span data-ttu-id="8bba3-105">**Para obter mais informações:** [Algoritmo Microsoft Naive Bayes](data-mining/microsoft-naive-bayes-algorithm.md), [Procurar um modelo usando o Visualizador Naive Bayes da Microsoft](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="8bba3-105">**For More Information:** [Microsoft Naive Bayes Algorithm](data-mining/microsoft-naive-bayes-algorithm.md), [Browse a Model Using the Microsoft Naive Bayes Viewer](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="8bba3-106">Opções</span><span class="sxs-lookup"><span data-stu-id="8bba3-106">Options</span></span>  
 <span data-ttu-id="8bba3-107">**Atualizar conteúdo do visualizador**</span><span class="sxs-lookup"><span data-stu-id="8bba3-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="8bba3-108">Recarregue o modelo de mineração no visualizador.</span><span class="sxs-lookup"><span data-stu-id="8bba3-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="8bba3-109">**Modelo de mineração**</span><span class="sxs-lookup"><span data-stu-id="8bba3-109">**Mining Model**</span></span>  
 <span data-ttu-id="8bba3-110">Escolha um modelo de mineração a ser exibido, dentre eles na estrutura de mineração atual.</span><span class="sxs-lookup"><span data-stu-id="8bba3-110">Choose a mining model to view, from those in the current mining structure.</span></span> <span data-ttu-id="8bba3-111">O modelo de mineração será aberto no visualizador associado.</span><span class="sxs-lookup"><span data-stu-id="8bba3-111">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="8bba3-112">**Visualizador**</span><span class="sxs-lookup"><span data-stu-id="8bba3-112">**Viewer**</span></span>  
 <span data-ttu-id="8bba3-113">Escolha um visualizador a ser utilizado para explorar o modelo de mineração selecionado.</span><span class="sxs-lookup"><span data-stu-id="8bba3-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="8bba3-114">Você pode escolher um visualizador personalizado fornecido para cada modelo de mineração ou o Visualizador de Conteúdo de Mineração da [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8bba3-114">You can choose the custom viewer provided for each mining model, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="8bba3-115">Você também pode usar os visualizadores de plug-in se estiverem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="8bba3-115">You can also use plug-in viewers if they are available.</span></span>  
  
 <span data-ttu-id="8bba3-116">**Mostrar Legenda**</span><span class="sxs-lookup"><span data-stu-id="8bba3-116">**Show Legend**</span></span>  
 <span data-ttu-id="8bba3-117">Selecione esta opção para exibir uma chave que corresponde a cada valor em **States** a uma das cores usadas no gráfico de distribuição.</span><span class="sxs-lookup"><span data-stu-id="8bba3-117">Select this option to display a key that matches each value in **States** to one of the colors used in the distribution chart.</span></span>  
  
 <span data-ttu-id="8bba3-118">**Barras de Histograma**</span><span class="sxs-lookup"><span data-stu-id="8bba3-118">**Histogram bars**</span></span>  
 <span data-ttu-id="8bba3-119">Selecione quantas barras deseja incluir no histograma.</span><span class="sxs-lookup"><span data-stu-id="8bba3-119">Select how many bars to include in the histogram.</span></span> <span data-ttu-id="8bba3-120">Caso haja mais barras do que você opte por exibir, as barras de maior importância serão retidas e as restantes serão agrupadas em **Outras**.</span><span class="sxs-lookup"><span data-stu-id="8bba3-120">If more bars exist than you choose to display, the bars of highest importance are retained, and the remaining bars are grouped together into **Other**.</span></span>  
  
 <span data-ttu-id="8bba3-121">**Previsível**</span><span class="sxs-lookup"><span data-stu-id="8bba3-121">**Predictable**</span></span>  
 <span data-ttu-id="8bba3-122">Selecione uma coluna previsível a partir do modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="8bba3-122">Select a predictable column from the mining model.</span></span>  
  
 <span data-ttu-id="8bba3-123">**Perfis de atributo**</span><span class="sxs-lookup"><span data-stu-id="8bba3-123">**Attribute Profiles**</span></span>  
 <span data-ttu-id="8bba3-124">A tabela contém as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="8bba3-124">The table contains the following columns:</span></span>  
  
|<span data-ttu-id="8bba3-125">Valor</span><span class="sxs-lookup"><span data-stu-id="8bba3-125">Value</span></span>|<span data-ttu-id="8bba3-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="8bba3-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8bba3-127">**Atributos**</span><span class="sxs-lookup"><span data-stu-id="8bba3-127">**Attributes**</span></span>|<span data-ttu-id="8bba3-128">Lista as colunas do modelo de mineração contidas no modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="8bba3-128">Lists the mining model columns contained within the mining model.</span></span>|  
|<span data-ttu-id="8bba3-129">**Estados**</span><span class="sxs-lookup"><span data-stu-id="8bba3-129">**States**</span></span>|<span data-ttu-id="8bba3-130">Uma coluna opcional que descreve qual estado a cor da linha de atributos correspondente representa.</span><span class="sxs-lookup"><span data-stu-id="8bba3-130">An optional column that describes what state the color in the corresponding row of attributes represents.</span></span> <span data-ttu-id="8bba3-131">Some ou remova usando a caixa de seleção **Mostrar Legenda** .</span><span class="sxs-lookup"><span data-stu-id="8bba3-131">Add or remove by using the **Show Legend** check box.</span></span>|  
|<span data-ttu-id="8bba3-132">**Média**</span><span class="sxs-lookup"><span data-stu-id="8bba3-132">**Population**</span></span>|<span data-ttu-id="8bba3-133">Exibe a distribuição do atributo por todo o conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="8bba3-133">Displays the distribution of the attribute across the whole dataset.</span></span>|  
|<span data-ttu-id="8bba3-134">**Coluna para os estados de atributo previsível**</span><span class="sxs-lookup"><span data-stu-id="8bba3-134">**Column for states of predictable attribute**</span></span>|<span data-ttu-id="8bba3-135">Exibe uma coluna para cada estado da coluna previsível em relação a cada linha correspondente a um atributo de entrada no modelo.</span><span class="sxs-lookup"><span data-stu-id="8bba3-135">Displays a column for each state of the predictable column, with each row corresponding to an input attribute in the model.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8bba3-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8bba3-136">See Also</span></span>  
 <span data-ttu-id="8bba3-137">[Algoritmos de mineração de dados &#40;mineração de dados Analysis Services&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="8bba3-137">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="8bba3-138">[Visualizadores de modelo de mineração &#40;designer de modelo de mineração de dados&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="8bba3-138">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="8bba3-139">Visualizadores do Modelo de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="8bba3-139">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
