---
title: Alterar as propriedades de um modelo de mineração | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], properties
- properties [data mining]
ms.assetid: aefaeb7f-d174-48d1-a188-0987a3b1196b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 395e6a4cb9c0f0dac0f0c717dfe0695033cad050
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569733"
---
# <a name="change-the-properties-of-a-mining-model"></a><span data-ttu-id="8435e-102">Alterar as propriedades de um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="8435e-102">Change the Properties of a Mining Model</span></span>
  <span data-ttu-id="8435e-103">Algumas propriedades de modelo de mineração se aplicam ao modelo como um todo, enquanto outras propriedades de modelo se aplicam a colunas individuais.</span><span class="sxs-lookup"><span data-stu-id="8435e-103">Some mining model properties apply to the model as a whole, and other model properties apply to individual columns.</span></span> <span data-ttu-id="8435e-104">Exemplos de propriedades que se aplicam ao modelo inteiro seriam a propriedade `Drillthrough`, que especifica se os dados de caso devem estar disponíveis para consulta, e a propriedade `Description`.</span><span class="sxs-lookup"><span data-stu-id="8435e-104">Examples of properties that apply to the entire model would be the `Drillthrough` property, which specifies whether the case data should be available for querying, and the `Description` property.</span></span> <span data-ttu-id="8435e-105">Propriedades que se aplicam à coluna incluem `Usage` e `ModelingFlags`, que controlam como os dados na coluna são usados no modelo.</span><span class="sxs-lookup"><span data-stu-id="8435e-105">Properties that apply to the column include `Usage` and `ModelingFlags`, which control how data in the column is used within the model.</span></span>  
  
 <span data-ttu-id="8435e-106">As propriedades modelo a seguir têm editores avançados que você pode usar para criar expressões ou configurar propriedades de modelo complexas.</span><span class="sxs-lookup"><span data-stu-id="8435e-106">The following model properties have advanced editors that you can use to create expressions or configure complex model properties.</span></span> <span data-ttu-id="8435e-107">Estas propriedades oferecem:</span><span class="sxs-lookup"><span data-stu-id="8435e-107">The following properties provide:</span></span>  
  
-   <span data-ttu-id="8435e-108">`Filter`Propriedade: abre a [caixa de diálogo Filtro de conjunto de dados ou filtro de modelo](../data-set-filter-or-model-filter-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="8435e-108">`Filter` property: Opens the [Data Set Filter or Model Filter Dialog Box](../data-set-filter-or-model-filter-dialog-box.md).</span></span>  
  
-   <span data-ttu-id="8435e-109">`AlgorithmParameters`Propriedade: abre a [caixa de diálogo parâmetros de algoritmo &#40;exibição de modelos de mineração&#41;](../algorithm-parameters-dialog-box-mining-models-view.md).</span><span class="sxs-lookup"><span data-stu-id="8435e-109">`AlgorithmParameters` property: Opens the [Algorithm Parameters Dialog Box &#40;Mining Models View&#41;](../algorithm-parameters-dialog-box-mining-models-view.md).</span></span>  
  
 <span data-ttu-id="8435e-110">Para obter informações sobre como definir as propriedades em um modelo de mineração, consulte [Colunas do modelo de mineração](mining-model-columns.md).</span><span class="sxs-lookup"><span data-stu-id="8435e-110">For information about how to set the properties in a mining model, see [Mining Model Columns](mining-model-columns.md).</span></span>  
  
### <a name="to-change-the-properties-of-a-mining-model"></a><span data-ttu-id="8435e-111">Para alterar as propriedades de um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="8435e-111">To change the properties of a mining model</span></span>  
  
1.  <span data-ttu-id="8435e-112">Na guia **Modelos de Mineração** do Designer de Data Mining, clique com o botão direito do mouse no cabeçalho da coluna que contém o nome do modelo de mineração ou na linha da grade que contém o nome do algoritmo de mineração e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8435e-112">In the **Mining Models** tab in Data Mining Designer, right-click either the column header that contains the name of the mining model, or the row in the grid that contains the name of the mining algorithm, and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="8435e-113">Na janela **Propriedades** na lateral direita da tela, realce o valor que corresponde à propriedade que você deseja alterar e digite o novo valor.</span><span class="sxs-lookup"><span data-stu-id="8435e-113">In the **Properties** window on the right side of the screen, highlight the value that corresponds to the property that you want to change, and enter the new value.</span></span>  
  
     <span data-ttu-id="8435e-114">O novo valor entrará em vigor quando você selecionar um elemento diferente no designer.</span><span class="sxs-lookup"><span data-stu-id="8435e-114">The new value will take effect when you select a different element in the designer.</span></span>  
  
### <a name="to-change-the-properties-of-a-mining-model-column"></a><span data-ttu-id="8435e-115">Para alterar as propriedades de uma coluna de modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="8435e-115">To change the properties of a mining model column</span></span>  
  
1.  <span data-ttu-id="8435e-116">Na guia **Modelos de Mineração** no Designer de Data Mining, clique com o botão direito do mouse na célula da grade na interseção da coluna da estrutura de mineração e do modelo de mineração e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8435e-116">In the **Mining Models** tab in Data Mining Designer, right-click the cell in the grid at the intersection of the mining structure column and the mining model, and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="8435e-117">Na janela **Propriedades** na lateral direita da tela, realce o valor que corresponde à propriedade que você deseja alterar e digite o novo valor.</span><span class="sxs-lookup"><span data-stu-id="8435e-117">In the **Properties** window on the right side of the screen, highlight the value that corresponds to the property that you want to change, and enter the new value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8435e-118">Se o uso da coluna for definido como `Ignore` , a janela **Propriedades** da coluna ficará em branco.</span><span class="sxs-lookup"><span data-stu-id="8435e-118">If the column usage is set to `Ignore`, the **Properties** window for the column is blank.</span></span>  
  
     <span data-ttu-id="8435e-119">O novo valor entrará em vigor quando você selecionar um elemento diferente no designer.</span><span class="sxs-lookup"><span data-stu-id="8435e-119">The new value will take effect when you select a different element in the designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8435e-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8435e-120">See Also</span></span>  
 [<span data-ttu-id="8435e-121">Tarefas e instruções do modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="8435e-121">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
