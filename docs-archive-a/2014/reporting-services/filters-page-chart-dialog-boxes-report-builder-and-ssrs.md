---
title: Página filtros, caixas de diálogo de gráfico (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.categorygroupproperties.filters.f1
- "10409"
- sql12.rtp.rptdesigner.seriesgroupproperties.filters.f1
- "10401"
- sql12.rtp.rptdesigner.chartproperties.filters.f1
- "10165"
ms.assetid: fab97b2f-d53f-42f2-900c-c159653d89ed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 01d5054ce7d0c3e02d960885f149bd0ef209dc34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680838"
---
# <a name="filters-page-chart-dialog-boxes-report-builder-and-ssrs"></a><span data-ttu-id="7ab67-102">Página Filtros, caixas de diálogo de Gráficos (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="7ab67-102">Filters page, Chart Dialog Boxes (Report Builder and SSRS)</span></span>
  <span data-ttu-id="7ab67-103">Clique em **filtros** no:</span><span class="sxs-lookup"><span data-stu-id="7ab67-103">Click **Filters** in the:</span></span>  
  
-   <span data-ttu-id="7ab67-104">caixa de diálogo**Propriedades do Grupo de Categorias** para filtrar pontos de dados em uma série agrupada por categoria.</span><span class="sxs-lookup"><span data-stu-id="7ab67-104">**Category Group Properties** dialog box to filter data points in a series that has been grouped by category.</span></span>  
  
-   <span data-ttu-id="7ab67-105">caixa de diálogo**Propriedades do Gráfico** para definir as opções de filtragem do gráfico.</span><span class="sxs-lookup"><span data-stu-id="7ab67-105">**Chart Properties** dialog box to define filtering options for the chart.</span></span>  
  
-   <span data-ttu-id="7ab67-106">caixa de diálogo**Propriedades do Grupo de Séries** para limitar o número de séries no grupo selecionado.</span><span class="sxs-lookup"><span data-stu-id="7ab67-106">**Series Group Properties** dialog box to limit the number of series in the selected group.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7ab67-107">Opções</span><span class="sxs-lookup"><span data-stu-id="7ab67-107">Options</span></span>  
 <span data-ttu-id="7ab67-108">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="7ab67-108">**Add**</span></span>  
 <span data-ttu-id="7ab67-109">Clique para adicionar uma nova cláusula de filtro à lista.</span><span class="sxs-lookup"><span data-stu-id="7ab67-109">Click to add a new filter clause to the list.</span></span>  
  
 <span data-ttu-id="7ab67-110">**Excluir**</span><span class="sxs-lookup"><span data-stu-id="7ab67-110">**Delete**</span></span>  
 <span data-ttu-id="7ab67-111">Clique para excluir a cláusula de filtro selecionada da lista.</span><span class="sxs-lookup"><span data-stu-id="7ab67-111">Click to delete the selected filter clause from the list.</span></span>  
  
 <span data-ttu-id="7ab67-112">**Seta para cima**</span><span class="sxs-lookup"><span data-stu-id="7ab67-112">**Up arrow**</span></span>  
 <span data-ttu-id="7ab67-113">Clique para mover o filtro selecionado para cima na lista.</span><span class="sxs-lookup"><span data-stu-id="7ab67-113">Click to move the selected filter up in the list.</span></span>  
  
 <span data-ttu-id="7ab67-114">**Seta para baixo**</span><span class="sxs-lookup"><span data-stu-id="7ab67-114">**Down arrow**</span></span>  
 <span data-ttu-id="7ab67-115">Clique para mover o filtro selecionado para baixo na lista.</span><span class="sxs-lookup"><span data-stu-id="7ab67-115">Click to move the selected filter down in the list.</span></span>  
  
 <span data-ttu-id="7ab67-116">**Expression**</span><span class="sxs-lookup"><span data-stu-id="7ab67-116">**Expression**</span></span>  
 <span data-ttu-id="7ab67-117">Digite ou escolha a expressão à qual deseja aplicar um filtro.</span><span class="sxs-lookup"><span data-stu-id="7ab67-117">Type or choose the expression to which you want to apply a filter.</span></span> <span data-ttu-id="7ab67-118">Clique no botão expressão (**FX**) para editar a expressão.</span><span class="sxs-lookup"><span data-stu-id="7ab67-118">Click the Expression (**fx**) button to edit the expression.</span></span>  
  
 <span data-ttu-id="7ab67-119">**Data type**</span><span class="sxs-lookup"><span data-stu-id="7ab67-119">**Data type**</span></span>  
 <span data-ttu-id="7ab67-120">Escolha o tipo de dados para **Valor**.</span><span class="sxs-lookup"><span data-stu-id="7ab67-120">Choose the data type for **Value**.</span></span> <span data-ttu-id="7ab67-121">Sempre que possível, escolha um tipo de dados correspondente ao tipo de dados de **Expressão**.</span><span class="sxs-lookup"><span data-stu-id="7ab67-121">When possible, choose a data type that matches the data type for **Expression**.</span></span>  
  
 <span data-ttu-id="7ab67-122">Os valores em **Expressão** e **Valor** devem ser avaliados como o mesmo tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="7ab67-122">The values in **Expression** and **Value** must evaluate to the same data type.</span></span> <span data-ttu-id="7ab67-123">Por exemplo, se a opção **Expressão** for definida como um campo que tem o tipo de dados System.Int32 e **Valor** como 7, na lista suspensa, escolha **Inteiro**.</span><span class="sxs-lookup"><span data-stu-id="7ab67-123">For example, if **Expression** is set to a field that has the data type System.Int32 and **Value** is set to 7, from the drop-down list, choose **Integer**.</span></span>  
  
 <span data-ttu-id="7ab67-124">Se a opção de tipo de dados necessária não estiver na lista suspensa, escreva uma expressão para converter o valor no tipo de dados correto.</span><span class="sxs-lookup"><span data-stu-id="7ab67-124">If the data type option you need is not in the drop-down list, write an expression to convert the value to the correct data type.</span></span> <span data-ttu-id="7ab67-125">Para obter mais informações, consulte [Exemplos de equações de filtro &#40;Construtor de Relatórios e SSRS&#41;](report-design/filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7ab67-125">For more information, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](report-design/filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="7ab67-126">**Operador**</span><span class="sxs-lookup"><span data-stu-id="7ab67-126">**Operator**</span></span>  
 <span data-ttu-id="7ab67-127">Selecione o operador que será usado para comparar a expressão e o valor.</span><span class="sxs-lookup"><span data-stu-id="7ab67-127">Choose the operator to use to compare the expression and the value.</span></span>  
  
 <span data-ttu-id="7ab67-128">**Valor**</span><span class="sxs-lookup"><span data-stu-id="7ab67-128">**Value**</span></span>  
 <span data-ttu-id="7ab67-129">Digite a expressão ou valor com o qual avaliar a expressão em **Expressão**.</span><span class="sxs-lookup"><span data-stu-id="7ab67-129">Type the expression or value against which to evaluate the expression in **Expression**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ab67-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7ab67-130">See Also</span></span>  
 <span data-ttu-id="7ab67-131">[Adicionar filtros de conjunto de dados, filtros de região e filtros de grupo &#40;Construtor de Relatórios e SSRS&#41;](report-design/add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="7ab67-131">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](report-design/add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="7ab67-132">[Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7ab67-132">[Expression Examples &#40;Report Builder and SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7ab67-133">[Expressões &#40;Construtor de Relatórios e SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7ab67-133">[Expressions &#40;Report Builder and SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="7ab67-134">Filtrar, agrupar e classificar dados &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7ab67-134">Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;</span></span>](report-design/filter-group-and-sort-data-report-builder-and-ssrs.md)  
  
  
