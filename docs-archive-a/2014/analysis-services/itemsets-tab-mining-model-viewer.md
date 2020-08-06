---
title: Guia conjuntos de itens (Visualizador do modelo de mineração) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.associationrules.itemsets.f1
ms.assetid: 95b2b805-b142-4064-9c80-4b1b3fe2fe63
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2b99b62b01b196fd62e1ef264e530487018f6a60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570963"
---
# <a name="itemsets-tab-mining-model-viewer"></a><span data-ttu-id="56f1e-102">Guia Conjuntos de Itens (Visualizador do Modelo de Mineração)</span><span class="sxs-lookup"><span data-stu-id="56f1e-102">Itemsets Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="56f1e-103">Use o painel **Conjunto de Itens** para exibir os conjuntos de itens frequentes presentes em um modelo de mineração de regras por associação.</span><span class="sxs-lookup"><span data-stu-id="56f1e-103">You can use the **Itemsets** pane to view the frequent itemsets that an association rules mining model contains.</span></span> <span data-ttu-id="56f1e-104">Como um modelo de associação pode conter muitos conjuntos de itens, os controles são fornecidos no visualizador para ajudá-lo a filtrar os conjuntos de itens exibidos no visualizador.</span><span class="sxs-lookup"><span data-stu-id="56f1e-104">Because an association model can contain many itemsets, controls are provided in the viewer to help you filter the itemsets that are displayed in the viewer.</span></span>  
  
 <span data-ttu-id="56f1e-105">**Para obter mais informações:** [Algoritmo de associação da Microsoft](data-mining/microsoft-association-algorithm.md), [Procurar um modelo usando o Visualizador de regras da Microsoft](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="56f1e-105">**For More Information:** [Microsoft Association Algorithm](data-mining/microsoft-association-algorithm.md), [Browse a Model Using the Microsoft Association Rules Viewer](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="56f1e-106">Opções</span><span class="sxs-lookup"><span data-stu-id="56f1e-106">Options</span></span>  
 <span data-ttu-id="56f1e-107">**Atualizar conteúdo do visualizador**</span><span class="sxs-lookup"><span data-stu-id="56f1e-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="56f1e-108">Recarregue o modelo de mineração no visualizador.</span><span class="sxs-lookup"><span data-stu-id="56f1e-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="56f1e-109">**Modelo de mineração**</span><span class="sxs-lookup"><span data-stu-id="56f1e-109">**Mining Model**</span></span>  
 <span data-ttu-id="56f1e-110">Escolha um modelo de mineração para exibir o que está presente na estrutura de mineração atual.</span><span class="sxs-lookup"><span data-stu-id="56f1e-110">Choose a mining model to view that is contained in the current mining structure.</span></span> <span data-ttu-id="56f1e-111">O modelo de mineração será aberto no visualizador associado.</span><span class="sxs-lookup"><span data-stu-id="56f1e-111">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="56f1e-112">**Visualizador**</span><span class="sxs-lookup"><span data-stu-id="56f1e-112">**Viewer**</span></span>  
 <span data-ttu-id="56f1e-113">Escolha um visualizador para exibir o modelo de mineração selecionado.</span><span class="sxs-lookup"><span data-stu-id="56f1e-113">Choose a viewer to use to view the selected mining model.</span></span> <span data-ttu-id="56f1e-114">Você pode usar o visualizador personalizado para modelos de associação ou o Visualizador de Árvore de Conteúdo Genérica da [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="56f1e-114">You can use either the custom viewer for association models, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Generic Content Tree viewer.</span></span> <span data-ttu-id="56f1e-115">Você também pode usar visualizadores de plug-in se houver.</span><span class="sxs-lookup"><span data-stu-id="56f1e-115">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="56f1e-116">**Suporte mínimo**</span><span class="sxs-lookup"><span data-stu-id="56f1e-116">**Minimum support**</span></span>  
 <span data-ttu-id="56f1e-117">Altere este valor para definir o suporte mínimo que um conjunto de itens precisa conter para aparecer no visualizador.</span><span class="sxs-lookup"><span data-stu-id="56f1e-117">Change this value to set the minimum support that an itemset must contain to appear in the viewer.</span></span> <span data-ttu-id="56f1e-118">O valor padrão que é exibido quando você primeiro abre o modelo é calculado pelo modelo, mas você pode alterá-lo para ver mais ou menos conjuntos de itens.</span><span class="sxs-lookup"><span data-stu-id="56f1e-118">The default value that is displayed when you first open the model is calculated by the model, but you can change it to see more or fewer itemsets.</span></span>  
  
 <span data-ttu-id="56f1e-119">**Tamanho mínimo do conjunto de itens**</span><span class="sxs-lookup"><span data-stu-id="56f1e-119">**Minimum itemset size**</span></span>  
 <span data-ttu-id="56f1e-120">Altere este valor para definir o número mínimo de itens que devem ser incluídos em um conjunto de itens antes de ele ser exibido no visualizador.</span><span class="sxs-lookup"><span data-stu-id="56f1e-120">Change this value to set the minimum number of items that must be included in an itemset before the itemset can be displayed in the viewer.</span></span>  
  
 <span data-ttu-id="56f1e-121">**Filtrar Conjunto de Itens**</span><span class="sxs-lookup"><span data-stu-id="56f1e-121">**Filter Itemset**</span></span>  
 <span data-ttu-id="56f1e-122">Digite um valor de cadeia de caracteres para filtrar os conjuntos de itens que aparecem no visualizador.</span><span class="sxs-lookup"><span data-stu-id="56f1e-122">Type a string value to filter the number of itemsets that appear in the viewer.</span></span>  
  
 <span data-ttu-id="56f1e-123">Você também pode digitar expressões regulares do .NET como critérios de filtro.</span><span class="sxs-lookup"><span data-stu-id="56f1e-123">You can also type .NET regular expressions as filter criteria.</span></span> <span data-ttu-id="56f1e-124">Por exemplo, a expressão a seguir retorna todos os conjuntos de itens que contêm 'Road Bottle Cage':</span><span class="sxs-lookup"><span data-stu-id="56f1e-124">For example, the following expression returns all itemsets that contain 'Road Bottle Cage':</span></span>  
  
 `\bRoad\b.\bBottle\b.\bCage\b.*`  
  
 <span data-ttu-id="56f1e-125">Observe que você pode precisar atualizar a exibição para ver os critérios de filtro serem aplicados.</span><span class="sxs-lookup"><span data-stu-id="56f1e-125">Note that you might need to refresh the view to see the filter criteria apply.</span></span> <span data-ttu-id="56f1e-126">Você também pode alternar a opção **Mostrar nome longo** como ligada e desligada para atualizar a lista.</span><span class="sxs-lookup"><span data-stu-id="56f1e-126">You can also toggle the **Show long name** option on and off to refresh the list.</span></span>  
  
 <span data-ttu-id="56f1e-127">Por padrão os critérios de filtro aplicam-se ao nome completo da combinação atributo-valor; portanto, se você só estiver exibindo o nome de atributo, pode não ser óbvio que os critérios de filtro foram aplicados corretamente.</span><span class="sxs-lookup"><span data-stu-id="56f1e-127">By default the filter criteria applies to the full name of the attribute-value combination; therefore, if you are viewing the attribute name only, it might not be obvious that the filter criteria has applied correctly.</span></span> <span data-ttu-id="56f1e-128">Use a lista suspensa **Mostrar** para selecionar **Mostrar o nome e valor de atributo**e verifique se a lista de conjuntos de itens está filtrada corretamente.</span><span class="sxs-lookup"><span data-stu-id="56f1e-128">Use the **Show** dropdown list to select **Show attribute name and value**, and verify that the list of itemsets is filtered correctly.</span></span>  
  
 <span data-ttu-id="56f1e-129">**Mostrar**</span><span class="sxs-lookup"><span data-stu-id="56f1e-129">**Show**</span></span>  
 <span data-ttu-id="56f1e-130">Ajuste como o conjunto de itens será exibido no visualizador.</span><span class="sxs-lookup"><span data-stu-id="56f1e-130">Adjust how the itemset is displayed in the viewer.</span></span> <span data-ttu-id="56f1e-131">Você pode selecionar uma das três opções seguintes:</span><span class="sxs-lookup"><span data-stu-id="56f1e-131">You can select one of the three following options:</span></span>  
  
-   <span data-ttu-id="56f1e-132">Mostrar o nome e valor de atributo</span><span class="sxs-lookup"><span data-stu-id="56f1e-132">Show attribute name and value</span></span>  
  
-   <span data-ttu-id="56f1e-133">Mostrar apenas o valor de atributo</span><span class="sxs-lookup"><span data-stu-id="56f1e-133">Show attribute value only</span></span>  
  
-   <span data-ttu-id="56f1e-134">Mostrar apenas o nome do atributo</span><span class="sxs-lookup"><span data-stu-id="56f1e-134">Show attribute name only</span></span>  
  
 <span data-ttu-id="56f1e-135">Observe que esta opção não exige o modelo; ela apenas filtra os atributos ou valores exibidos.</span><span class="sxs-lookup"><span data-stu-id="56f1e-135">Note that this option does not requery the model; it only filters the attributes or values that are displayed.</span></span>  
  
 <span data-ttu-id="56f1e-136">**Mostrar nome longo**</span><span class="sxs-lookup"><span data-stu-id="56f1e-136">**Show long name**</span></span>  
 <span data-ttu-id="56f1e-137">Selecione esta opção para exibir o nome completo do conjunto de itens como aparece no conteúdo do modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="56f1e-137">Select this option to display the full name of the itemset as it appears in the mining model content.</span></span>  
  
 <span data-ttu-id="56f1e-138">**Máximo de linhas**</span><span class="sxs-lookup"><span data-stu-id="56f1e-138">**Maximum rows**</span></span>  
 <span data-ttu-id="56f1e-139">Limite o número de conjunto de itens que serão exibidos no visualizador.</span><span class="sxs-lookup"><span data-stu-id="56f1e-139">Limit the number of itemsets that are displayed in the viewer.</span></span> <span data-ttu-id="56f1e-140">Por padrão, os conjuntos de itens são ordenados por suporte em ordem decrescente, de modo que abaixar este valor restringirá a lista aos conjuntos de itens mais comuns.</span><span class="sxs-lookup"><span data-stu-id="56f1e-140">By default, itemsets are ordered by support in descending order, so lowering this value restricts the list to the most common itemsets.</span></span>  
  
 <span data-ttu-id="56f1e-141">**Suporte**</span><span class="sxs-lookup"><span data-stu-id="56f1e-141">**Support**</span></span>  
 <span data-ttu-id="56f1e-142">Exibe o suporte para cada conjunto de itens.</span><span class="sxs-lookup"><span data-stu-id="56f1e-142">Displays the support for each itemset.</span></span>  
  
 <span data-ttu-id="56f1e-143">**Tamanho**</span><span class="sxs-lookup"><span data-stu-id="56f1e-143">**Size**</span></span>  
 <span data-ttu-id="56f1e-144">Exibe o número de itens que há em cada conjunto de itens.</span><span class="sxs-lookup"><span data-stu-id="56f1e-144">Displays the number of items that exist in each itemset.</span></span>  
  
 <span data-ttu-id="56f1e-145">**Conjunto de Itens**</span><span class="sxs-lookup"><span data-stu-id="56f1e-145">**Itemset**</span></span>  
 <span data-ttu-id="56f1e-146">Exibe a descrição da dimensão de cada conjunto de itens.</span><span class="sxs-lookup"><span data-stu-id="56f1e-146">Displays the description of each itemset.</span></span> <span data-ttu-id="56f1e-147">Por padrão, os conjuntos de itens são apresentados como uma lista delimitada por vírgulas de atributos e os respectivos valores.</span><span class="sxs-lookup"><span data-stu-id="56f1e-147">By default, itemsets are presented as a comma-delimited list of attributes and their values.</span></span> <span data-ttu-id="56f1e-148">Você pode alterar o modo como eles são exibidos usando a opção **Mostrar** .</span><span class="sxs-lookup"><span data-stu-id="56f1e-148">You can change the way they are displayed by using the **Show** option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56f1e-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="56f1e-149">See Also</span></span>  
 <span data-ttu-id="56f1e-150">[Algoritmos de mineração de dados &#40;mineração de dados Analysis Services&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="56f1e-150">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="56f1e-151">[Visualizadores de modelo de mineração &#40;designer de modelo de mineração de dados&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="56f1e-151">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="56f1e-152">Visualizadores do Modelo de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="56f1e-152">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
