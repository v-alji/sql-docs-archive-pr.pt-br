---
title: Exibir ou alterar parâmetros de algoritmo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- algorithms [data mining]
- mining models [Analysis Services], algorithms
ms.assetid: 151b899b-c27a-4a09-bcf5-5c9f0ec24168
author: minewiskan
ms.author: owend
ms.openlocfilehash: 30719cd50e0c473cf2aab5d9689d27dff4f26343
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572823"
---
# <a name="view-or-change-algorithm-parameters"></a><span data-ttu-id="3b0ad-102">Exibir ou alterar parâmetros do algoritmo</span><span class="sxs-lookup"><span data-stu-id="3b0ad-102">View or Change Algorithm Parameters</span></span>
  <span data-ttu-id="3b0ad-103">Você pode alterar os parâmetros fornecidos com os algoritmos usados para criar modelos de mineração de dados para personalizar os resultados do modelo.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-103">You can change the parameters provided with the algorithms that you use to build data mining models to customize the results of the model.</span></span>  
  
 <span data-ttu-id="3b0ad-104">Os parâmetros de algoritmo fornecidos na [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] alteração é muito mais do que apenas propriedades no modelo: eles podem ser usados para alterar fundamentalmente a forma como os dados são processados, agrupados e exibidos.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-104">The algorithm parameters provided in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] change much more than just properties on the model: they can be used to fundamentally alter the way that data is processed, grouped, and displayed.</span></span> <span data-ttu-id="3b0ad-105">Por exemplo, você pode usar parâmetros de algoritmo para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3b0ad-105">For example, you can use algorithm parameters to do the following:</span></span>  
  
-   <span data-ttu-id="3b0ad-106">Alterar o método de análise, como o método de clustering.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-106">Change the method of analysis, such as the clustering method.</span></span>  
  
-   <span data-ttu-id="3b0ad-107">Controlar o comportamento da seleção de recursos.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-107">Control feature selection behavior.</span></span>  
  
-   <span data-ttu-id="3b0ad-108">Especificar o tamanho de conjuntos de itens ou a probabilidade de regras.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-108">Specify the size of itemsets or the probability of rules.</span></span>  
  
-   <span data-ttu-id="3b0ad-109">Controlar a ramificação e a profundidade de árvores de decisão.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-109">Control branching and depth of decision trees.</span></span>  
  
-   <span data-ttu-id="3b0ad-110">Especificar um valor de semente ou o tamanho do conjunto de controle interno usado na criação de modelo.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-110">Specify a seed value or the size of the internal holdout set used for model creation.</span></span>  
  
 <span data-ttu-id="3b0ad-111">Os parâmetros fornecidos para cada algoritmo variam muito; para obter uma lista dos parâmetros que você pode definir para cada algoritmo, consulte os tópicos de referência técnica nesta seção: [Algoritmos de mineração de dados &#40;Analysis Services – Mineração de dados&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="3b0ad-111">The parameters provided for each algorithm vary greatly; for a list of the parameters that you can set for each algorithm, see the technical reference topics in this section: [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span>  
  
### <a name="change-an-algorithm-parameter"></a><span data-ttu-id="3b0ad-112">Alterar um parâmetro de algoritmo</span><span class="sxs-lookup"><span data-stu-id="3b0ad-112">Change an algorithm parameter</span></span>  
  
1.  <span data-ttu-id="3b0ad-113">Na guia **Modelos de Mineração** do Designer de Mineração de Dados no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], clique com o botão direito do mouse no tipo de modelo de mineração para o qual você quer ajustar o algoritmo e selecione **Definir Parâmetros de Algoritmo**.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-113">On the **Mining Models** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], right-click the algorithm type of the mining model for which you want to tune the algorithm, and select **Set Algorithm Parameters**.</span></span>  
  
     <span data-ttu-id="3b0ad-114">A caixa de diálogo **Parâmetros do Algoritmo** é exibida.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-114">The **Algorithm Parameters** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="3b0ad-115">Na coluna **Valor** , defina um novo valor para o algoritmo que você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-115">In the **Value** column, set a new value for the algorithm that you want to change.</span></span>  
  
     <span data-ttu-id="3b0ad-116">Se você não digitar um valor na coluna **Valor** , o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] usará o valor de parâmetro padrão.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-116">If you do not enter a value in the **Value** column, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] uses the default parameter value.</span></span> <span data-ttu-id="3b0ad-117">A coluna **Intervalo** descreve os possíveis valores que você pode digitar.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-117">The **Range** column describes the possible values that you can enter.</span></span>  
  
3.  <span data-ttu-id="3b0ad-118">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-118">Click **OK**.</span></span>  
  
     <span data-ttu-id="3b0ad-119">O parâmetro de algoritmo será definido com o novo valor.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-119">The algorithm parameter is set with the new value.</span></span> <span data-ttu-id="3b0ad-120">A alteração de parâmetro não será refletida no modelo de mineração até que você processe o modelo novamente.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-120">The parameter change will not be reflected in the mining model until you reprocess the model.</span></span>  
  
### <a name="view-the-parameters-used-in-an-existing-model"></a><span data-ttu-id="3b0ad-121">Exibir os parâmetros usados em um modelo existente</span><span class="sxs-lookup"><span data-stu-id="3b0ad-121">View the parameters used in an existing model</span></span>  
  
1.  <span data-ttu-id="3b0ad-122">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra uma janela de consulta DMX.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open a DMX Query window.</span></span>  
  
2.  <span data-ttu-id="3b0ad-123">Digite uma consulta como esta:</span><span class="sxs-lookup"><span data-stu-id="3b0ad-123">Type a query like this one:</span></span>  
  
    ```  
    select MINING_PARAMETERS   
    from $system.DMSCHEMA_MINING_MODELS  
    WHERE MODEL_NAME = '<model name>'  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3b0ad-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3b0ad-124">See Also</span></span>  
 [<span data-ttu-id="3b0ad-125">Tarefas e instruções do modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="3b0ad-125">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
