---
title: Definir uma mensagem Nenhum Dado para uma região de dados (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4b194714-46f7-4f0e-9632-7f89d9600762
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9ed38ef14eb8f89753b4b3d7af3324ef0e88fa52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679710"
---
# <a name="set-a-no-data-message-for-a-data-region-report-builder-and-ssrs"></a><span data-ttu-id="2ebf8-102">Definir uma mensagem Nenhum Dado para uma região de dados (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="2ebf8-102">Set a No Data Message for a Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="2ebf8-103">Quando quiser especificar o texto que será exibido no relatório renderizado em vez de uma região de dados sem dados, defina a propriedade NoRowsMessage para uma tabela, matriz ou região de dados de lista, NoDataMessage para uma região de dados do gráfico e NoDataText para a escala de cores de um mapa.</span><span class="sxs-lookup"><span data-stu-id="2ebf8-103">When you want to specify text to show in the rendered report in place of a data region that has no data, set the NoRowsMessage property for a table, matrix, or list data region, the NoDataMessage for a chart data region, and the NoDataText for the color scale for a map.</span></span> <span data-ttu-id="2ebf8-104">No tempo de execução, o processador do relatório executa a consulta para cada conjunto de dados em um relatório e a consulta do conjunto de dados pode não produzir nenhum conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="2ebf8-104">At run time, the report processor runs the query for each dataset in a report and the dataset query may produce no result set.</span></span> <span data-ttu-id="2ebf8-105">Em uma região de dados associada a um conjunto de dados vazio, você pode especificar o texto que deseja exibir em vez de exibir uma região de dados vazia.</span><span class="sxs-lookup"><span data-stu-id="2ebf8-105">For a data region bound to an empty dataset, you can specify text to display instead of displaying an empty data region.</span></span> <span data-ttu-id="2ebf8-106">Também é possível definir a propriedade NoRowsMessage para um sub-relatório quando nenhum conjunto de dados no sub-relatório tiver dados no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="2ebf8-106">You can also set the NoRowsMessage property for a subreport when no datasets in the subreport have data at run time.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-the-norowsmessage-property-for-a-table-matrix-or-list"></a><span data-ttu-id="2ebf8-107">Para definir a propriedade NoRowsMessage para uma tabela, matriz ou lista</span><span class="sxs-lookup"><span data-stu-id="2ebf8-107">To set the NoRowsMessage property for a table, matrix, or list</span></span>  
  
1.  <span data-ttu-id="2ebf8-108">No modo Design, clique na região de dados de tabela, matriz ou lista ou no sub-relatório na superfície de design para selecioná-lo.</span><span class="sxs-lookup"><span data-stu-id="2ebf8-108">In Design view, click the table, matrix, or list data region or subreport on the design surface to select it.</span></span> <span data-ttu-id="2ebf8-109">O painel Propriedades exibe as propriedades do item selecionado.</span><span class="sxs-lookup"><span data-stu-id="2ebf8-109">The Properties pane displays the properties for the selected item.</span></span>  
  
2.  <span data-ttu-id="2ebf8-110">No painel Propriedades, digite o texto que você deseja exibir como uma mensagem no campo de `NoRowsMessage` propriedade.</span><span class="sxs-lookup"><span data-stu-id="2ebf8-110">In the Properties pane, type the text that you want to display as a message in `NoRowsMessage` property field.</span></span>  
  
     <span data-ttu-id="2ebf8-111">Como alternativa, na lista suspensa, clique em **Expressão** para abrir a caixa de diálogo **Expressão** e criar uma expressão.</span><span class="sxs-lookup"><span data-stu-id="2ebf8-111">Alternatively, from the drop-down list, click **Expression** to open the **Expression** dialog box and create an expression.</span></span>  
  
### <a name="to-set-the-nodatamessage-property-for-a-chart"></a><span data-ttu-id="2ebf8-112">Para definir a propriedade NoDataMessage para um gráfico</span><span class="sxs-lookup"><span data-stu-id="2ebf8-112">To set the NoDataMessage property for a chart</span></span>  
  
1.  <span data-ttu-id="2ebf8-113">Na exibição Design, clique no gráfico na superfície do design para selecioná-lo.</span><span class="sxs-lookup"><span data-stu-id="2ebf8-113">In Design view, click the chart on the design surface to select it.</span></span> <span data-ttu-id="2ebf8-114">O painel Propriedades exibe as propriedades do item selecionado.</span><span class="sxs-lookup"><span data-stu-id="2ebf8-114">The Properties pane displays the properties for the selected item.</span></span>  
  
2.  <span data-ttu-id="2ebf8-115">No painel Propriedades, expanda o nó para `NoDataMessage` .</span><span class="sxs-lookup"><span data-stu-id="2ebf8-115">In the Properties pane, expand the node for `NoDataMessage`.</span></span>  
  
3.  <span data-ttu-id="2ebf8-116">Em **legenda**, digite o texto que você deseja exibir como uma mensagem no `NoDataMessage` campo de propriedade.</span><span class="sxs-lookup"><span data-stu-id="2ebf8-116">In **Caption**, type the text that you want to display as a message in `NoDataMessage` property field.</span></span>  
  
     <span data-ttu-id="2ebf8-117">Como alternativa, na lista suspensa, clique em **Expressão** para abrir a caixa de diálogo **Expressão** e criar uma expressão.</span><span class="sxs-lookup"><span data-stu-id="2ebf8-117">Alternatively, from the drop-down list, click **Expression** to open the **Expression** dialog box and create an expression.</span></span>  
  
### <a name="to-set-the-norowsmessage-for-a-subreport"></a><span data-ttu-id="2ebf8-118">Para definir NoRowsMessage para um sub-relatório</span><span class="sxs-lookup"><span data-stu-id="2ebf8-118">To set the NoRowsMessage for a subreport</span></span>  
  
1.  <span data-ttu-id="2ebf8-119">Na exibição Design, clique no sub-relatório na superfície do design para selecioná-lo.</span><span class="sxs-lookup"><span data-stu-id="2ebf8-119">In Design view, click the subreport on the design surface to select it.</span></span> <span data-ttu-id="2ebf8-120">O painel Propriedades exibe as propriedades do item selecionado.</span><span class="sxs-lookup"><span data-stu-id="2ebf8-120">The Properties pane displays the properties for the selected item.</span></span>  
  
2.  <span data-ttu-id="2ebf8-121">No painel Propriedades, digite o texto que você deseja exibir como uma mensagem no campo de `NoRowsMessage` propriedade.</span><span class="sxs-lookup"><span data-stu-id="2ebf8-121">In the Properties pane, type the text that you want to display as a message in `NoRowsMessage` property field.</span></span>  
  
     <span data-ttu-id="2ebf8-122">Como alternativa, na lista suspensa, clique em **Expressão** para abrir a caixa de diálogo **Expressão** e criar uma expressão.</span><span class="sxs-lookup"><span data-stu-id="2ebf8-122">Alternatively, from the drop-down list, click **Expression** to open the **Expression** dialog box and create an expression.</span></span>  
  
### <a name="to-set-the-nodatatext-property-for-a-color-scale-for-a-map"></a><span data-ttu-id="2ebf8-123">Para definir a propriedade NoDataText para uma escala de cores para um mapa</span><span class="sxs-lookup"><span data-stu-id="2ebf8-123">To set the NoDataText property for a color scale for a map</span></span>  
  
1.  <span data-ttu-id="2ebf8-124">Na exibição Design, clique na escala de cores no mapa para selecioná-lo.</span><span class="sxs-lookup"><span data-stu-id="2ebf8-124">In Design view, click the color scale on the map to select it.</span></span> <span data-ttu-id="2ebf8-125">O painel Propriedades exibe as propriedades do item selecionado.</span><span class="sxs-lookup"><span data-stu-id="2ebf8-125">The Properties pane displays the properties for the selected item.</span></span>  
  
2.  <span data-ttu-id="2ebf8-126">No painel Propriedades, em `NoDataText` , digite o texto que você deseja exibir como um rótulo para cores sem valor de dados.</span><span class="sxs-lookup"><span data-stu-id="2ebf8-126">In the Properties pane, in `NoDataText`, type the text that you want to display as a label for colors with no data value.</span></span>  
  
     <span data-ttu-id="2ebf8-127">Como alternativa, na lista suspensa, clique em **Expressão** para abrir a caixa de diálogo **Expressão** e criar uma expressão.</span><span class="sxs-lookup"><span data-stu-id="2ebf8-127">Alternatively, from the drop-down list, click **Expression** to open the **Expression** dialog box and create an expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ebf8-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2ebf8-128">See Also</span></span>  
 <span data-ttu-id="2ebf8-129">[Sub-relatórios &#40;Construtor de Relatórios e SSRS&#41;](../report-design/subreports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2ebf8-129">[Subreports &#40;Report Builder and SSRS&#41;](../report-design/subreports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2ebf8-130">[Tabelas, matrizes e listas &#40;Construtor de Relatórios e SSRS&#41;](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2ebf8-130">[Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2ebf8-131">[Gráficos &#40;Construtor de Relatórios e SSRS&#41;](../report-design/charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2ebf8-131">[Charts &#40;Report Builder and SSRS&#41;](../report-design/charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2ebf8-132">[Mapas &#40;Construtor de Relatórios e SSRS&#41;](../report-design/maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2ebf8-132">[Maps &#40;Report Builder and SSRS&#41;](../report-design/maps-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="2ebf8-133">Sub-relatórios &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2ebf8-133">Subreports &#40;Report Builder and SSRS&#41;</span></span>](../report-design/subreports-report-builder-and-ssrs.md)  
  
  
