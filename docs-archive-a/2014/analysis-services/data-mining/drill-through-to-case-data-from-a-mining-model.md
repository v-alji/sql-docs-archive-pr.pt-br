---
title: Detalhar os dados de caso de um modelo de mineração | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- drillthrough [Analysis Services]
ms.assetid: b4d3f350-e543-4ea9-b3a2-b4f7c0a9ae27
author: minewiskan
ms.author: owend
ms.openlocfilehash: 74129c44fc92984a767a79c579a495084ae68754
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582208"
---
# <a name="drill-through-to-case-data-from-a-mining-model"></a><span data-ttu-id="9b4a1-102">Detalhar dados do caso a partir do modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="9b4a1-102">Drill Through to Case Data from a Mining Model</span></span>
  <span data-ttu-id="9b4a1-103">Se um modelo de mineração foi configurado para permitir que você detalhe os casos de modelo, quando você procurar o modelo, poderá recuperar informações detalhadas sobre os casos usados para criar o modelo.</span><span class="sxs-lookup"><span data-stu-id="9b4a1-103">If a mining model has been configured to let you drill through to model cases, when you browse the model, you can retrieve detailed information about the cases that were used to create the model.</span></span> <span data-ttu-id="9b4a1-104">Além do mais, se a estrutura de mineração subjacente tiver sido configurada para permitir o detalhamento para casos de estrutura e você tiver as permissões adequadas, poderá retornar as informações a partir da estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="9b4a1-104">Moreover, if the underlying mining structure has been configured to allow drillthrough to structure cases, and you have the appropriate permissions, you can return information from the mining structure.</span></span> <span data-ttu-id="9b4a1-105">Isso pode incluir colunas que não foram incluídas no modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="9b4a1-105">This can include columns that were not included in the mining model.</span></span>  
  
 <span data-ttu-id="9b4a1-106">Se a estrutura de mineração não permitir que você detalhe os dados subjacentes, mas o modelo de mineração permitir, você poderá exibir informações dos casos de modelo e não da estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="9b4a1-106">If the mining structure does not allow you to drill through to the underlying data, but the mining model does, you can view information from the model cases, but not from the mining structure.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9b4a1-107">Você pode acrescentar a habilidade de detalhamento em um modelo de mineração existente, configurando a propriedade `AllowDrillthrough` para `True`.</span><span class="sxs-lookup"><span data-stu-id="9b4a1-107">You can add the ability to drillthrough on an existing mining model by setting the property `AllowDrillthrough` to `True`.</span></span> <span data-ttu-id="9b4a1-108">Porém, depois que você habilitar o detalhamento, o modelo deverá ser reprocessado antes que você possa ver os dados do caso.</span><span class="sxs-lookup"><span data-stu-id="9b4a1-108">However, after you enable drillthrough, the model must be reprocessed before you can see the case data.</span></span> <span data-ttu-id="9b4a1-109">Para obter mais informações,consulte [Habilitar drillthrough para um modelo de mineração](enable-drillthrough-for-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="9b4a1-109">For more information, see [Enable Drillthrough for a Mining Model](enable-drillthrough-for-a-mining-model.md).</span></span>  
  
 <span data-ttu-id="9b4a1-110">Dependendo do tipo de visualizador utilizado, é possível selecionar o nó a ser detalhado das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="9b4a1-110">Depending on the type of viewer you are using, you can select the node for drillthrough in the following ways:</span></span>  
  
|<span data-ttu-id="9b4a1-111">Nome do visualizador</span><span class="sxs-lookup"><span data-stu-id="9b4a1-111">Viewer name</span></span>|<span data-ttu-id="9b4a1-112">Painel ou nome da guia</span><span class="sxs-lookup"><span data-stu-id="9b4a1-112">Pane or tab name</span></span>|<span data-ttu-id="9b4a1-113">Selecionar nó</span><span class="sxs-lookup"><span data-stu-id="9b4a1-113">Select node</span></span>|  
|-----------------|----------------------|-----------------|  
|<span data-ttu-id="9b4a1-114">**Visualizador de árvores da Microsoft**</span><span class="sxs-lookup"><span data-stu-id="9b4a1-114">**Microsoft Tree Viewer**</span></span>|<span data-ttu-id="9b4a1-115">Guia **árvore de decisão**</span><span class="sxs-lookup"><span data-stu-id="9b4a1-115">**Decision Tree** tab</span></span>|<span data-ttu-id="9b4a1-116">Clique em um nó de árvore.</span><span class="sxs-lookup"><span data-stu-id="9b4a1-116">Click a tree node.</span></span><br /><br /> <span data-ttu-id="9b4a1-117">**Observação** Evite usar o detalhamento no `All` nó, pois pode levar muito tempo para retornar resultados.</span><span class="sxs-lookup"><span data-stu-id="9b4a1-117">**Note** Avoid using drillthrough on the `All` node, because it may take a very long time to return results.</span></span>|  
|<span data-ttu-id="9b4a1-118">**Visualizador de cluster da Microsoft**</span><span class="sxs-lookup"><span data-stu-id="9b4a1-118">**Microsoft Cluster Viewer**</span></span>|<span data-ttu-id="9b4a1-119">**Diagrama de Cluster**</span><span class="sxs-lookup"><span data-stu-id="9b4a1-119">**Cluster Diagram**</span></span>|<span data-ttu-id="9b4a1-120">Clique em um nó de cluster.</span><span class="sxs-lookup"><span data-stu-id="9b4a1-120">Click a cluster node.</span></span>|  
|<span data-ttu-id="9b4a1-121">**Visualizador de cluster da Microsoft**</span><span class="sxs-lookup"><span data-stu-id="9b4a1-121">**Microsoft Cluster Viewer**</span></span>|<span data-ttu-id="9b4a1-122">**Perfis de cluster**</span><span class="sxs-lookup"><span data-stu-id="9b4a1-122">**Cluster Profiles**</span></span>|<span data-ttu-id="9b4a1-123">Clique em qualquer parte da coluna de cluster.</span><span class="sxs-lookup"><span data-stu-id="9b4a1-123">Click anywhere in cluster column.</span></span>|  
|<span data-ttu-id="9b4a1-124">**Visualizador de Associação da Microsoft**</span><span class="sxs-lookup"><span data-stu-id="9b4a1-124">**Microsoft Association Viewer**</span></span>|<span data-ttu-id="9b4a1-125">Guia **regras**</span><span class="sxs-lookup"><span data-stu-id="9b4a1-125">**Rules** tab</span></span>|<span data-ttu-id="9b4a1-126">Clique em uma linha que contém um conjunto de regras.</span><span class="sxs-lookup"><span data-stu-id="9b4a1-126">Click a row that contains a set of rules.</span></span>|  
|<span data-ttu-id="9b4a1-127">**Visualizador de Associação da Microsoft**</span><span class="sxs-lookup"><span data-stu-id="9b4a1-127">**Microsoft Association Viewer**</span></span>|<span data-ttu-id="9b4a1-128">Guia**Conjuntos de Itens**</span><span class="sxs-lookup"><span data-stu-id="9b4a1-128">**Itemsets** tab</span></span>|<span data-ttu-id="9b4a1-129">Clique em uma linha que contém um conjunto de itens.</span><span class="sxs-lookup"><span data-stu-id="9b4a1-129">Click a row that contains an itemset.</span></span>|  
|<span data-ttu-id="9b4a1-130">**Visualizador de Cluster de Sequência da Microsoft**</span><span class="sxs-lookup"><span data-stu-id="9b4a1-130">**Microsoft Sequence Clustering Viewer**</span></span>|<span data-ttu-id="9b4a1-131">Guia **regras**</span><span class="sxs-lookup"><span data-stu-id="9b4a1-131">**Rules** tab</span></span>|<span data-ttu-id="9b4a1-132">Clique em uma linha que contém um conjunto de regras.</span><span class="sxs-lookup"><span data-stu-id="9b4a1-132">Click a row that contains a set of rules.</span></span>|  
|<span data-ttu-id="9b4a1-133">**Visualizador de Cluster de Sequência da Microsoft**</span><span class="sxs-lookup"><span data-stu-id="9b4a1-133">**Microsoft Sequence Clustering Viewer**</span></span>|<span data-ttu-id="9b4a1-134">Guia**Conjuntos de Itens**</span><span class="sxs-lookup"><span data-stu-id="9b4a1-134">**Itemsets** tab</span></span>|<span data-ttu-id="9b4a1-135">Clique em uma linha que contém um conjunto de itens.</span><span class="sxs-lookup"><span data-stu-id="9b4a1-135">Click a row that contains an itemset.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="9b4a1-136">Alguns modelos não podem usar detalhamento.</span><span class="sxs-lookup"><span data-stu-id="9b4a1-136">Some models cannot use drillthrough.</span></span> <span data-ttu-id="9b4a1-137">A capacidade de usar detalhamento depende do algoritmo utilizado para criar o modelo.</span><span class="sxs-lookup"><span data-stu-id="9b4a1-137">The ability to use drillthrough depends on the algorithm that was used to create the model.</span></span> <span data-ttu-id="9b4a1-138">Para obter uma lista dos tipos de modelo de mineração que dão suporte ao drillthrough, consulte [Consultas de detalhamento &#40;Mineração de dados&#41;](drillthrough-queries-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="9b4a1-138">For a list of the mining model types that support drillthrough, see [Drillthrough Queries &#40;Data Mining&#41;](drillthrough-queries-data-mining.md).</span></span>  
  
### <a name="to-view-drillthrough-data-from-a-mining-model"></a><span data-ttu-id="9b4a1-139">Para exibir dados de detalhamento de um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="9b4a1-139">To view drillthrough data from a mining model</span></span>  
  
1.  <span data-ttu-id="9b4a1-140">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra a estrutura de mineração que contém o modelo de mineração desejado.</span><span class="sxs-lookup"><span data-stu-id="9b4a1-140">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the mining structure that contains the mining model you want.</span></span>  
  
2.  <span data-ttu-id="9b4a1-141">No Designer de Mineração de Dados, clique na guia **Visualizador do Modelo de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="9b4a1-141">In Data Mining Designer, click the **Mining Model Viewer** tab.</span></span>  
  
3.  <span data-ttu-id="9b4a1-142">Selecione o modelo na lista suspensa **Modelo de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="9b4a1-142">Select the model from the **Mining Model** drop-down list.</span></span>  
  
4.  <span data-ttu-id="9b4a1-143">Selecione um visualizador na lista suspensa **Visualizador** e clique com o botão direito do mouse no nó específico.</span><span class="sxs-lookup"><span data-stu-id="9b4a1-143">Select a viewer from the **Viewer** drop-down list, and right-click the specific node.</span></span>  
  
5.  <span data-ttu-id="9b4a1-144">Selecione **Detalhar**e, em seguida, selecione **Somente Colunas de Modelos**ou **Colunas de Modelo e Estrutura** para abrir a janela **Detalhar** .</span><span class="sxs-lookup"><span data-stu-id="9b4a1-144">Select **Drill Through**, and then select either **Models Columns Only**, or **Model and Structure Columns** to open the **Drill Through** window.</span></span>  
  
6.  <span data-ttu-id="9b4a1-145">Para copiar os dados para a Área de Transferência, clique com o botão direito do mouse na tabela e selecione **Copiar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="9b4a1-145">To copy the data to the Clipboard, right-click any row in the table, and select **Copy All**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b4a1-146">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9b4a1-146">See Also</span></span>  
 [<span data-ttu-id="9b4a1-147">Consultas de detalhamento &#40;Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="9b4a1-147">Drillthrough Queries &#40;Data Mining&#41;</span></span>](drillthrough-queries-data-mining.md)  
  
  
