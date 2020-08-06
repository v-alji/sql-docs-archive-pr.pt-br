---
title: Excluir um filtro de um modelo de mineração | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- filters [Analysis Services]
ms.assetid: 91220b21-adbc-49a9-b200-8bf0a724eff1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 404c23c0e55bffba2ce8410c9c30d6ad1fa1991b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570331"
---
# <a name="delete-a-filter-from-a-mining-model"></a><span data-ttu-id="0e788-102">Excluir um filtro de um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="0e788-102">Delete a Filter from a Mining Model</span></span>
  <span data-ttu-id="0e788-103">Quando você cria um filtro em um modelo de mineração, pode criar modelos em um subconjunto dos dados na exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="0e788-103">When you create a filter on a mining model, you can create models on a subset of the data in the data source view.</span></span> <span data-ttu-id="0e788-104">Os filtros também são úteis para testar a precisão do modelo em um subconjunto dos dados originais.</span><span class="sxs-lookup"><span data-stu-id="0e788-104">Filters are also useful for testing the accuracy of the model on a subset of the original data.</span></span>  
  
 <span data-ttu-id="0e788-105">Porém, você deve excluir o filtro se quiser exibir novamente o conjunto completo de casos.</span><span class="sxs-lookup"><span data-stu-id="0e788-105">However, you must delete the filter if you want to view the complete set of cases again.</span></span> <span data-ttu-id="0e788-106">Este procedimento descreve como remover as condições em um filtro ou excluir completamente o filtro.</span><span class="sxs-lookup"><span data-stu-id="0e788-106">This procedure describes how to remove conditions on a filter, or delete the filter completely.</span></span>  
  
### <a name="to-delete-a-condition-from-a-filter-on-a-mining-model"></a><span data-ttu-id="0e788-107">Para excluir uma condição de um filtro em um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="0e788-107">To delete a condition from a filter on a mining model</span></span>  
  
1.  <span data-ttu-id="0e788-108">Em [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], no Gerenciador de Soluções, clique na estrutura de mineração que contém o modelo de mineração a filtrar.</span><span class="sxs-lookup"><span data-stu-id="0e788-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in Solution Explorer, click the mining structure that contains the mining model you want to filter.</span></span>  
  
2.  <span data-ttu-id="0e788-109">Clique na guia **Modelos de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="0e788-109">Click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="0e788-110">Selecione o modelo, e clique com o botão direito do mouse para abrir o menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="0e788-110">Select the model, and right-click to open the shortcut menu.</span></span>  
  
     <span data-ttu-id="0e788-111">- ou -</span><span class="sxs-lookup"><span data-stu-id="0e788-111">-or-</span></span>  
  
     <span data-ttu-id="0e788-112">Selecione o modelo.</span><span class="sxs-lookup"><span data-stu-id="0e788-112">Select the model.</span></span> <span data-ttu-id="0e788-113">No menu **Modelo de Mineração** , selecione **Definir Filtro de Modelos**.</span><span class="sxs-lookup"><span data-stu-id="0e788-113">On the **Mining Model** menu, select **Set Model Filter**.</span></span>  
  
4.  <span data-ttu-id="0e788-114">Na caixa de diálogo **Filtro de Modelos** , clique com o botão direito do mouse na linha da grade que contém a condição a excluir.</span><span class="sxs-lookup"><span data-stu-id="0e788-114">In the **Model Filter** dialog box, right-click the row in the grid that contains the condition you want to delete.</span></span>  
  
5.  <span data-ttu-id="0e788-115">Selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="0e788-115">Select **Delete**.</span></span>  
  
### <a name="to-clear-the-filter-on-a-mining-model-in-the-filter-editor-dialog-box"></a><span data-ttu-id="0e788-116">Para desmarcar o filtro em um modelo de mineração na caixa de diálogo Editor de Filtro</span><span class="sxs-lookup"><span data-stu-id="0e788-116">To clear the filter on a mining model in the Filter Editor dialog box</span></span>  
  
-   <span data-ttu-id="0e788-117">Na caixa de diálogo **Editor de Filtro** , clique com o botão direito do mouse em uma linha na grade e selecione **Excluir Tudo**.</span><span class="sxs-lookup"><span data-stu-id="0e788-117">In the **Filter Editor** dialog box, right-click any row in the grid, and select **Delete All**.</span></span>  
  
## <a name="working-with-model-filters-using-the-properties-window"></a><span data-ttu-id="0e788-118">Trabalhando com os filtros de modelos usando a janela Propriedades</span><span class="sxs-lookup"><span data-stu-id="0e788-118">Working with Model Filters Using the Properties Window</span></span>  
 <span data-ttu-id="0e788-119">Para excluir o filtro inteiro, você não precisa abrir as caixas de diálogo do editor de filtro.</span><span class="sxs-lookup"><span data-stu-id="0e788-119">If you want to delete the whole filter, you do not need to open the filter editor dialog boxes.</span></span> <span data-ttu-id="0e788-120">As condições de filtro que você criou estão disponíveis na propriedade `Filter` do modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="0e788-120">The filter conditions that you created are available in the `Filter` property of the mining model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0e788-121">Você pode exibir as propriedades de um modelo de mineração no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], mas não no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e788-121">You can view the properties of a mining model in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], but not in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-clear-the-filter-on-a-mining-model-in-solution-explorer"></a><span data-ttu-id="0e788-122">Para desmarcar o filtro em um modelo de mineração no Gerenciador de Soluções</span><span class="sxs-lookup"><span data-stu-id="0e788-122">To clear the filter on a mining model in Solution Explorer</span></span>  
  
1.  <span data-ttu-id="0e788-123">No Gerenciador de Soluções, clique no modelo de mineração que contém o filtro.</span><span class="sxs-lookup"><span data-stu-id="0e788-123">In Solution Explorer, click the mining model that contains the filter.</span></span>  
  
2.  <span data-ttu-id="0e788-124">Na janela **Propriedades** , clique com o botão direito do mouse no texto do filtro na `Filter` propriedade e selecione **selecionar tudo**.</span><span class="sxs-lookup"><span data-stu-id="0e788-124">In the **Properties** window, right-click the filter text in the `Filter` property, and select **Select All**.</span></span>  
  
3.  <span data-ttu-id="0e788-125">Pressione a tecla Backspace ou Delete.</span><span class="sxs-lookup"><span data-stu-id="0e788-125">Press the Backspace or Delete key.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e788-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0e788-126">See Also</span></span>  
 <span data-ttu-id="0e788-127">[Detalhar os dados de caso de um modelo de mineração](drill-through-to-case-data-from-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="0e788-127">[Drill Through to Case Data from a Mining Model](drill-through-to-case-data-from-a-mining-model.md) </span></span>  
 <span data-ttu-id="0e788-128">[Tarefas e instruções do modelo de mineração](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="0e788-128">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="0e788-129">Filtros para modelos de mineração &#40;Analysis Services – Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="0e788-129">Filters for Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-models-analysis-services-data-mining.md)  
  
  
