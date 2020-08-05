---
title: Guia regras (Visualizador do modelo de mineração) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.associationrules.rules.f1
ms.assetid: 705d5492-b58f-45d9-94d7-ed57b7025823
author: minewiskan
ms.author: owend
ms.openlocfilehash: d0d86931865fd9352074669de93b14dacfc84537
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570929"
---
# <a name="rules-tab-mining-model-viewer"></a><span data-ttu-id="54067-102">Guia Regras (Visualizador do Modelo de Mineração)</span><span class="sxs-lookup"><span data-stu-id="54067-102">Rules Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="54067-103">Use o painel **Regras** em um modelo de associação para exibir as regras que o algoritmo extraiu dos dados.</span><span class="sxs-lookup"><span data-stu-id="54067-103">Use the **Rules** pane in an association model to view the rules that the algorithm extracted from the data.</span></span> <span data-ttu-id="54067-104">As regras descrevem como os itens estão relacionados uns com os outros e podem ser usados para criar recomendações.</span><span class="sxs-lookup"><span data-stu-id="54067-104">Rules describe how items are related to each other, and can be used to create recommendations.</span></span>  
  
 <span data-ttu-id="54067-105">Pode-se utilizar as opções do visualizador para filtrar o número de regras exibidas no visualizador.</span><span class="sxs-lookup"><span data-stu-id="54067-105">You can use the options in the viewer to filter the number of rules that are displayed in the viewer.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="54067-106">Por padrão, somente as regras que estão acima do limite de probabilidade definidas em **Probabilidade mínima** são exibidas no visualizador.</span><span class="sxs-lookup"><span data-stu-id="54067-106">By default, only the rules that are above the probability threshold defined in **Minimum probability** are displayed in the viewer.</span></span> <span data-ttu-id="54067-107">Você não pode diminuir este valor usando o visualizador, porque o limite de probabilidade para saída de regra é determinado quando o modelo é criado.</span><span class="sxs-lookup"><span data-stu-id="54067-107">You cannot make this value any smaller by using the viewer, because the probability threshold for rule output is determined when the model is created.</span></span> <span data-ttu-id="54067-108">Para obter mais informações, consulte [Referência técnica do algoritmo de associação da Microsoft](data-mining/microsoft-association-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="54067-108">For more information, see [Microsoft Association Algorithm Technical Reference](data-mining/microsoft-association-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="54067-109">**Para obter mais informações:** [Algoritmo de associação da Microsoft](data-mining/microsoft-association-algorithm.md), [Procurar um modelo usando o Visualizador de regras da Microsoft](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="54067-109">**For More Information:** [Microsoft Association Algorithm](data-mining/microsoft-association-algorithm.md), [Browse a Model Using the Microsoft Association Rules Viewer](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="54067-110">Opções</span><span class="sxs-lookup"><span data-stu-id="54067-110">Options</span></span>  
 <span data-ttu-id="54067-111">**Atualizar conteúdo do visualizador**</span><span class="sxs-lookup"><span data-stu-id="54067-111">**Refresh viewer content**</span></span>  
 <span data-ttu-id="54067-112">Recarregue o modelo de mineração no visualizador.</span><span class="sxs-lookup"><span data-stu-id="54067-112">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="54067-113">**Modelo de mineração**</span><span class="sxs-lookup"><span data-stu-id="54067-113">**Mining Model**</span></span>  
 <span data-ttu-id="54067-114">Escolha um modelo de mineração para exibir o que está presente na estrutura de mineração atual.</span><span class="sxs-lookup"><span data-stu-id="54067-114">Choose a mining model to view that is contained in the current mining structure.</span></span> <span data-ttu-id="54067-115">O modelo de mineração será aberto no visualizador associado.</span><span class="sxs-lookup"><span data-stu-id="54067-115">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="54067-116">**Visualizador**</span><span class="sxs-lookup"><span data-stu-id="54067-116">**Viewer**</span></span>  
 <span data-ttu-id="54067-117">Escolha um visualizador para exibir o modelo de mineração selecionado.</span><span class="sxs-lookup"><span data-stu-id="54067-117">Choose a viewer to use to view the selected mining model.</span></span> <span data-ttu-id="54067-118">Você pode usar o visualizador personalizado para cada modelo de mineração, ou o **Visualizador de Árvore de Conteúdo Genérica da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="54067-118">You can use the custom viewer for each mining model, or the **Microsoft Generic Content Tree Viewer**.</span></span> <span data-ttu-id="54067-119">Você também pode usar visualizadores de plug-in se houver.</span><span class="sxs-lookup"><span data-stu-id="54067-119">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="54067-120">**Probabilidade mínima**</span><span class="sxs-lookup"><span data-stu-id="54067-120">**Minimum probability**</span></span>  
 <span data-ttu-id="54067-121">Altere este valor para definir a probabilidade mínima exigida para uma regra a ser exibida no visualizador.</span><span class="sxs-lookup"><span data-stu-id="54067-121">Change this value to set the minimum probability required for a rule to be displayed in the viewer.</span></span> <span data-ttu-id="54067-122">Aumentar o valor para a probabilidade reduzirá o número de regras que são exibidas.</span><span class="sxs-lookup"><span data-stu-id="54067-122">Increasing the value for probability will reduce the number of rules that are displayed.</span></span>  
  
 <span data-ttu-id="54067-123">**Importância mínima**</span><span class="sxs-lookup"><span data-stu-id="54067-123">**Minimum importance**</span></span>  
 <span data-ttu-id="54067-124">Altere este valor para definir a importância mínima exigida para uma regra a ser exibida no visualizador.</span><span class="sxs-lookup"><span data-stu-id="54067-124">Change this value to set the minimum importance required for a rule to be displayed in the viewer.</span></span> <span data-ttu-id="54067-125">Aumentar o valor para a importância reduzirá o número de regras que são exibidas.</span><span class="sxs-lookup"><span data-stu-id="54067-125">Increasing the value for importance will reduce the number of rules that are displayed.</span></span>  
  
 <span data-ttu-id="54067-126">**Regra do Filtro**</span><span class="sxs-lookup"><span data-stu-id="54067-126">**Filter Rule**</span></span>  
 <span data-ttu-id="54067-127">Digite um valor de cadeia de caracteres para filtrar o número de regras que aparecem no visualizador.</span><span class="sxs-lookup"><span data-stu-id="54067-127">Type a string value to filter the number of rules that appear in the viewer.</span></span>  
  
 <span data-ttu-id="54067-128">Você também pode digitar expressões regulares do .NET como critérios de filtro.</span><span class="sxs-lookup"><span data-stu-id="54067-128">You can also type .NET regular expressions as filter criteria.</span></span> <span data-ttu-id="54067-129">Por exemplo, a expressão a seguir retorna todas as regras que contêm 'Road Bottle Cage' no lado esquerdo da regra:</span><span class="sxs-lookup"><span data-stu-id="54067-129">For example, the following expression returns all rules that contain 'Road Bottle Cage' on the left side of the rule:</span></span>  
  
 `\bRoad\b.\bBottle\b.\bCage\b.*->.*`  
  
 <span data-ttu-id="54067-130">Observe que você pode precisar atualizar a exibição para ver os critérios de filtro serem aplicados.</span><span class="sxs-lookup"><span data-stu-id="54067-130">Note that you might need to refresh the view to see the filter criteria apply.</span></span> <span data-ttu-id="54067-131">Você também pode alternar a opção **Mostrar nome longo** como ligada e desligada para atualizar a lista.</span><span class="sxs-lookup"><span data-stu-id="54067-131">You can also toggle the **Show long name** option on and off to refresh the list.</span></span>  
  
 <span data-ttu-id="54067-132">Por padrão os critérios de filtro aplicam-se ao nome completo da combinação atributo-valor; portanto, se você só estiver exibindo o nome de atributo, pode não ser óbvio que os critérios de filtro foram aplicados corretamente.</span><span class="sxs-lookup"><span data-stu-id="54067-132">By default the filter criteria applies to the full name of the attribute-value combination; therefore, if you are viewing the attribute name only, it might not be obvious that the filter criteria has applied correctly.</span></span> <span data-ttu-id="54067-133">Use a lista suspensa **Mostrar** para selecionar **Mostrar o nome e valor de atributo**e verifique se a lista de conjuntos de itens está filtrada corretamente.</span><span class="sxs-lookup"><span data-stu-id="54067-133">Use the **Show** dropdown list to select **Show attribute name and value**, and verify that the list of itemsets is filtered correctly.</span></span>  
  
 <span data-ttu-id="54067-134">**Mostrar**</span><span class="sxs-lookup"><span data-stu-id="54067-134">**Show**</span></span>  
 <span data-ttu-id="54067-135">Ajuste o modo pelo qual a regra é exibida no visualizador.</span><span class="sxs-lookup"><span data-stu-id="54067-135">Adjust the way that the rule is displayed in the viewer.</span></span> <span data-ttu-id="54067-136">Você pode selecionar uma das três opções seguintes:</span><span class="sxs-lookup"><span data-stu-id="54067-136">You can select one of the three following options:</span></span>  
  
-   <span data-ttu-id="54067-137">Mostrar o nome e valor de atributo</span><span class="sxs-lookup"><span data-stu-id="54067-137">Show the attribute name and value</span></span>  
  
-   <span data-ttu-id="54067-138">Mostrar apenas o valor de atributo</span><span class="sxs-lookup"><span data-stu-id="54067-138">Show the attribute value only</span></span>  
  
-   <span data-ttu-id="54067-139">Mostrar apenas o nome de atributo</span><span class="sxs-lookup"><span data-stu-id="54067-139">Show the attribute name only</span></span>  
  
 <span data-ttu-id="54067-140">**Mostrar nome longo**</span><span class="sxs-lookup"><span data-stu-id="54067-140">**Show long name**</span></span>  
 <span data-ttu-id="54067-141">Mostrar o nome longo da regra conforme aparece no conteúdo de modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="54067-141">Show the full name of the rule as it appears in the mining model content.</span></span>  
  
 <span data-ttu-id="54067-142">**Máximo de linhas**</span><span class="sxs-lookup"><span data-stu-id="54067-142">**Maximum rows**</span></span>  
 <span data-ttu-id="54067-143">Limitar o número de regras exibidas no visualizador.</span><span class="sxs-lookup"><span data-stu-id="54067-143">Limit the number of rules that are displayed in the viewer.</span></span>  
  
 <span data-ttu-id="54067-144">**Probabilidade**</span><span class="sxs-lookup"><span data-stu-id="54067-144">**Probability**</span></span>  
 <span data-ttu-id="54067-145">Esta coluna no gráfico exibe a probabilidade para cada regra.</span><span class="sxs-lookup"><span data-stu-id="54067-145">This column in the chart displays the probability for each rule.</span></span>  
  
 <span data-ttu-id="54067-146">Clique no cabeçalho da coluna para classificar por probabilidade.</span><span class="sxs-lookup"><span data-stu-id="54067-146">You can click the column heading to sort by probability.</span></span>  
  
 <span data-ttu-id="54067-147">**Importância**</span><span class="sxs-lookup"><span data-stu-id="54067-147">**Importance**</span></span>  
 <span data-ttu-id="54067-148">Esta coluna no gráfico exibe a importância para cada regra.</span><span class="sxs-lookup"><span data-stu-id="54067-148">This column in the chart displays the importance for each rule.</span></span>  
  
 <span data-ttu-id="54067-149">Clique no cabeçalho da coluna para classificar por importância.</span><span class="sxs-lookup"><span data-stu-id="54067-149">You can click the column heading to sort by importance.</span></span>  
  
 <span data-ttu-id="54067-150">**Regra**</span><span class="sxs-lookup"><span data-stu-id="54067-150">**Rule**</span></span>  
 <span data-ttu-id="54067-151">Esta coluna no gráfico exibe a descrição de texto para cada regra, de acordo com o formato especificado usando as opções **Mostrar** e **Mostrar nome longo**.</span><span class="sxs-lookup"><span data-stu-id="54067-151">This column in the chart displays the text description for each rule, according to the format specified by using the options, **Show** and **Show long name**.</span></span>  
  
 <span data-ttu-id="54067-152">Clique no cabeçalho da coluna para classificar pelo texto da regra.</span><span class="sxs-lookup"><span data-stu-id="54067-152">You can click the column heading to sort by the text of the rule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54067-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="54067-153">See Also</span></span>  
 <span data-ttu-id="54067-154">[Algoritmos de mineração de dados &#40;mineração de dados Analysis Services&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="54067-154">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="54067-155">[Visualizadores de modelo de mineração &#40;designer de modelo de mineração de dados&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="54067-155">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="54067-156">Visualizadores do Modelo de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="54067-156">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
