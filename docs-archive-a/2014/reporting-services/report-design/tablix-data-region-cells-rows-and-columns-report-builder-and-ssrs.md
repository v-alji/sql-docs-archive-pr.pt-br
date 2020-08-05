---
title: Células, linhas e colunas da região de dados Tablix (Construtor de Relatórios) e SSRS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10058"
- "10057"
- sql12.rtp.rptdesigner.deleterows.f1
- sql12.rtp.rptdesigner.deletecolumns.f1
ms.assetid: 70eef636-6d8c-495e-83fc-dc0fe9771658
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fc5ee01368c02781f86a04f4b93f7db873fcb0dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573660"
---
# <a name="tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs"></a><span data-ttu-id="40894-102">Células, linhas e colunas da região de dados Tablix (Construtor de Relatórios) e SSRS</span><span class="sxs-lookup"><span data-stu-id="40894-102">Tablix Data Region Cells, Rows, and Columns (Report Builder) and SSRS</span></span>
  <span data-ttu-id="40894-103">Para controlar como as linhas e colunas de uma região de dados tablix exibem dados em um relatório, você deve compreender como especificá-las para dados detalhados, dados de grupo, além de rótulos e totais.</span><span class="sxs-lookup"><span data-stu-id="40894-103">To control how the rows and columns of a tablix data region display data in a report, you must understand how to specify rows and columns for detail data, for group data, and for labels and totals.</span></span> <span data-ttu-id="40894-104">Em muitos casos, é possível usar as estruturas padrão em uma tabela, matriz ou lista para exibir os dados.</span><span class="sxs-lookup"><span data-stu-id="40894-104">In many cases, you can use the default structures for a table, matrix, or list to display your data.</span></span> <span data-ttu-id="40894-105">Para obter mais informações, consulte [tabelas &#40;Construtor de relatórios e ssrs&#41;](tables-report-builder-and-ssrs.md), [matrizes &#40;Construtor de Relatórios e SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md)ou [listas &#40;Construtor de relatórios e SSRS ](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md)&#41;.</span><span class="sxs-lookup"><span data-stu-id="40894-105">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md), [Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md), or [Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="40894-106">Uma região de dados tablix exibe dados detalhados em linhas e colunas detalhadas, além de dados agrupados em linhas e colunas agrupadas.</span><span class="sxs-lookup"><span data-stu-id="40894-106">A tablix data region displays detail data on detail rows and detail columns and grouped data on group rows and group columns.</span></span> <span data-ttu-id="40894-107">Quando você adiciona grupos de linhas e de colunas a uma região de dados tablix, as linhas e as colunas nas quais os dados são exibidos são adicionadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="40894-107">When you add row groups and column groups to a tablix data region, rows and columns on which to display the data are automatically added.</span></span> <span data-ttu-id="40894-108">É possível adicionar e remover manualmente linhas e colunas para personalizar uma região de dados tablix e controlar a forma como os dados são exibidos no relatório.</span><span class="sxs-lookup"><span data-stu-id="40894-108">You can manually add and remove rows and columns to customize a tablix data region and control the way your data displays in the report.</span></span>  
  
 <span data-ttu-id="40894-109">Para compreender como personalizar uma região de dados tablix, você deve compreender inicialmente como interpretar as indicações visuais exibidas quando você seleciona uma região de dados tablix na superfície de design.</span><span class="sxs-lookup"><span data-stu-id="40894-109">To understand how to customize a tablix data region, you should first understand how to interpret the visual cues you see when you select a tablix data region on the design surface.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="understanding-tablix-visual-cues"></a><span data-ttu-id="40894-110">Compreendendo as indicações visuais Tablix</span><span class="sxs-lookup"><span data-stu-id="40894-110">Understanding Tablix Visual Cues</span></span>  
 <span data-ttu-id="40894-111">As indicações visuais em uma região de dados tablix ajudam você a trabalhar com uma região de dados tablix para exibir os dados desejados.</span><span class="sxs-lookup"><span data-stu-id="40894-111">Visual cues on a tablix data region help you work with a tablix data region to display the data you want.</span></span>  
  
### <a name="row-and-column-handles"></a><span data-ttu-id="40894-112">Identificadores de linha e de coluna</span><span class="sxs-lookup"><span data-stu-id="40894-112">Row and Column Handles</span></span>  
 <span data-ttu-id="40894-113">Quando você seleciona uma região de dados tablix, gráficos indicadores de linha e de coluna apontam o propósito de cada uma delas.</span><span class="sxs-lookup"><span data-stu-id="40894-113">When you select a tablix data region, the row and column handle graphics indicate the purpose of each row and column.</span></span> <span data-ttu-id="40894-114">Os identificadores mostram as linhas e as colunas que estão dentro ou fora de um grupo.</span><span class="sxs-lookup"><span data-stu-id="40894-114">Handles indicate rows and columns that are inside a group or outside a group.</span></span> <span data-ttu-id="40894-115">A tabela a seguir mostra várias exibições de identificadores.</span><span class="sxs-lookup"><span data-stu-id="40894-115">The following table shows a variety of handle displays.</span></span>  
  
|<span data-ttu-id="40894-116">Ícone</span><span class="sxs-lookup"><span data-stu-id="40894-116">Icon</span></span>|<span data-ttu-id="40894-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="40894-117">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="40894-118">![Identificador de linha com três linhas paralelas para a linha de detalhes](../media/rs-icontablix-detailsrow.gif "Identificador de linha com três linhas paralelas para a linha de detalhes")</span><span class="sxs-lookup"><span data-stu-id="40894-118">![Row handle with 3 parallel lines for details row](../media/rs-icontablix-detailsrow.gif "Row handle with 3 parallel lines for details row")</span></span>|<span data-ttu-id="40894-119">Apenas o grupo detalhado na hierarquia do grupo de linhas</span><span class="sxs-lookup"><span data-stu-id="40894-119">Only the details group on the row group hierarchy</span></span>|  
|<span data-ttu-id="40894-120">![Identificador de linha com linha de detalhes e um grupo externo](../media/rs-icontablix-groupwithdetails.gif "Identificador de linha com linha de detalhes e um grupo externo")</span><span class="sxs-lookup"><span data-stu-id="40894-120">![Row handle with details row and one outer group](../media/rs-icontablix-groupwithdetails.gif "Row handle with details row and one outer group")</span></span>|<span data-ttu-id="40894-121">Um grupo externo e o grupo detalhado filho</span><span class="sxs-lookup"><span data-stu-id="40894-121">One outer group and the child details group</span></span>|  
|<span data-ttu-id="40894-122">![Dois colchetes paralelos mostrando grupos aninhados](../media/rs-icontablix-nestedgroupnodetails.gif "Dois colchetes paralelos mostrando grupos aninhados")</span><span class="sxs-lookup"><span data-stu-id="40894-122">![Two parallel brackets showing nested groups](../media/rs-icontablix-nestedgroupnodetails.gif "Two parallel brackets showing nested groups")</span></span>|<span data-ttu-id="40894-123">Um grupo externo, um grupo interno; nenhum grupo detalhado</span><span class="sxs-lookup"><span data-stu-id="40894-123">One outer group, one inner group; no details group</span></span>|  
|<span data-ttu-id="40894-124">![Dois colchetes e três linhas empilhadas para aninhadas e detalhes](../media/rs-icontablix-nestedgroupwithdetails.gif "Dois colchetes e três linhas empilhadas para aninhadas e detalhes")</span><span class="sxs-lookup"><span data-stu-id="40894-124">![2 brackets & 3 stacked lines for nested & details](../media/rs-icontablix-nestedgroupwithdetails.gif "2 brackets & 3 stacked lines for nested & details")</span></span>|<span data-ttu-id="40894-125">Um grupo externo, um grupo interno e o grupo detalhado filho</span><span class="sxs-lookup"><span data-stu-id="40894-125">One outer group, one inner group, and the child details group</span></span>|  
|<span data-ttu-id="40894-126">![Um grupo externo com linha de rodapé, um grupo interno](../media/rs-icontablix-nestedgroupwithparentfooter.gif "Um grupo externo com linha de rodapé, um grupo interno")</span><span class="sxs-lookup"><span data-stu-id="40894-126">![One outer group with footer row, one inner group](../media/rs-icontablix-nestedgroupwithparentfooter.gif "One outer group with footer row, one inner group")</span></span>|<span data-ttu-id="40894-127">Um grupo externo com uma linha de rodapé para totais e um grupo interno</span><span class="sxs-lookup"><span data-stu-id="40894-127">One outer group with a footer row for totals and one inner group</span></span>|  
|<span data-ttu-id="40894-128">![colchete de grupo externo, colchete de grupo interno, detalhes](../media/rs-icontablix-nestedgroupwithdetailsandtotals.gif "colchete de grupo externo, colchete de grupo interno, detalhes")</span><span class="sxs-lookup"><span data-stu-id="40894-128">![outer group bracket, inner group bracket, details](../media/rs-icontablix-nestedgroupwithdetailsandtotals.gif "outer group bracket, inner group bracket, details")</span></span>|<span data-ttu-id="40894-129">Um grupo externo com uma linha de rodapé para totais, um grupo interno com uma linha de rodapé para totais e uma linha detalhada</span><span class="sxs-lookup"><span data-stu-id="40894-129">One outer group with a footer row for totals, one inner group with a footer row for totals, and one details row</span></span>|  
|<span data-ttu-id="40894-130">![cabeçalho e rodapé pai e também grupo filho](../media/rs-icontablix-nestedgroupwithparentheaderandfooter.gif "cabeçalho e rodapé pai e também grupo filho")</span><span class="sxs-lookup"><span data-stu-id="40894-130">![parent header and footer, and also child group](../media/rs-icontablix-nestedgroupwithparentheaderandfooter.gif "parent header and footer, and also child group")</span></span>|<span data-ttu-id="40894-131">Um grupo externo com um cabeçalho para rótulos e um rodapé para totais, além de um grupo interno; nenhum grupo detalhado</span><span class="sxs-lookup"><span data-stu-id="40894-131">One outer group with a header for labels and a footer for totals, and an inner group; no details group</span></span>|  
  
### <a name="group-rows"></a><span data-ttu-id="40894-132">Linhas de grupo</span><span class="sxs-lookup"><span data-stu-id="40894-132">Group Rows</span></span>  
 <span data-ttu-id="40894-133">As linhas dentro de um grupo se repetem uma vez por valor de grupo exclusivo e costumam ser usadas em resumos de agregação.</span><span class="sxs-lookup"><span data-stu-id="40894-133">Rows inside a group repeat once per unique group value and are typically used for aggregate summaries.</span></span> <span data-ttu-id="40894-134">Linhas fora de um grupo se repetem uma vez em relação ao grupo e são usadas em rótulos ou subtotais.</span><span class="sxs-lookup"><span data-stu-id="40894-134">Rows outside a group repeat once with respect to the group and are used for labels or subtotals.</span></span> <span data-ttu-id="40894-135">Quando você seleciona uma célula tablix, identificadores e colchetes dentro da região de dados tablix mostram os grupos aos quais uma célula pertence.</span><span class="sxs-lookup"><span data-stu-id="40894-135">When you select a tablix cell, row and column handles and brackets inside the tablix data region show the groups to which a cell belongs.</span></span> <span data-ttu-id="40894-136">Esta figura exibe as seguintes indicações visuais:</span><span class="sxs-lookup"><span data-stu-id="40894-136">This figure displays the following visual cues:</span></span>  
  
-   <span data-ttu-id="40894-137">Identificadores e linha e coluna que mostram associações de grupo.</span><span class="sxs-lookup"><span data-stu-id="40894-137">Row and column handles that indicate group associations.</span></span>  
  
-   <span data-ttu-id="40894-138">Indicadores de grupo realçados que mostram a associação ao grupo interno de uma célula selecionada.</span><span class="sxs-lookup"><span data-stu-id="40894-138">Highlighted group indicators that show the innermost group membership for a selected cell.</span></span>  
  
-   <span data-ttu-id="40894-139">Indicadores de grupo que mostram todas as associações a grupo de uma célula selecionada.</span><span class="sxs-lookup"><span data-stu-id="40894-139">Group indicators that show all group memberships for a selected cell.</span></span>  
  
 <span data-ttu-id="40894-140">![Tabela com detalhes e grupos de linhas aninhadas](../media/rs-tablixrowgroupvisualcues.gif "Tabela com detalhes e grupos de linhas aninhadas")</span><span class="sxs-lookup"><span data-stu-id="40894-140">![Table with detail and nested row groups](../media/rs-tablixrowgroupvisualcues.gif "Table with detail and nested row groups")</span></span>  
  
### <a name="total-rows"></a><span data-ttu-id="40894-141">Linhas de total</span><span class="sxs-lookup"><span data-stu-id="40894-141">Total Rows</span></span>  
 <span data-ttu-id="40894-142">Após adicionar grupos de linhas e de colunas, é possível adicionar uma linha para exibir totais de colunas e uma coluna para exibir totais de linhas.</span><span class="sxs-lookup"><span data-stu-id="40894-142">After you add row and column groups, you can add a row to display totals for columns and a column to display totals for rows.</span></span> <span data-ttu-id="40894-143">A seguinte figura mostra uma matriz com grupos de linhas e de colunas, além de uma linha e uma coluna de total.</span><span class="sxs-lookup"><span data-stu-id="40894-143">The following figure shows a matrix with both row and column groups, and a total row and a total column.</span></span>  
  
 <span data-ttu-id="40894-144">![região de dados Tablix](../media/rs-tablixparts.gif "região de dados Tablix")</span><span class="sxs-lookup"><span data-stu-id="40894-144">![Tablix data region](../media/rs-tablixparts.gif "Tablix data region")</span></span>  
  
### <a name="grouping-pane"></a><span data-ttu-id="40894-145">Painel Agrupamento</span><span class="sxs-lookup"><span data-stu-id="40894-145">Grouping Pane</span></span>  
 <span data-ttu-id="40894-146">O painel Agrupamento exibe os grupos de linhas e de colunas referentes à região de dados tablix selecionada na superfície de design no momento.</span><span class="sxs-lookup"><span data-stu-id="40894-146">The Grouping pane displays the row and column groups for the currently selected tablix data region on the design surface.</span></span> <span data-ttu-id="40894-147">A seguinte figura mostra o painel Agrupamento da região de dados tablix.</span><span class="sxs-lookup"><span data-stu-id="40894-147">The following figure shows the Grouping pane for this tablix data region.</span></span>  
  
 <span data-ttu-id="40894-148">![Painel Agrupamento para grupos de linhas e colunas aninhadas](../media/rs-basictablixdesigngroupingpanedefaultview.gif "Painel Agrupamento para grupos de linhas e colunas aninhadas")</span><span class="sxs-lookup"><span data-stu-id="40894-148">![Grouping pane for nested row and column groups](../media/rs-basictablixdesigngroupingpanedefaultview.gif "Grouping pane for nested row and column groups")</span></span>  
  
 <span data-ttu-id="40894-149">O painel Grupos de Linhas mostra o grupo pai Categoria e o grupo filho Subcat.</span><span class="sxs-lookup"><span data-stu-id="40894-149">The Row Groups pane shows the parent group Category and child group Subcat.</span></span> <span data-ttu-id="40894-150">O painel Grupos de Colunas mostra o grupo pai Geografia e o grupo filho CountryRegion, além do grupo Ano, adjacente ao grupo Geografia.</span><span class="sxs-lookup"><span data-stu-id="40894-150">The Column groups pane shows the parent group Geography and child group CountryRegion, and also the Year group, which is an adjacent group to the Geography group.</span></span> <span data-ttu-id="40894-151">Quando você seleciona o grupo Subcat no painel Grupos de Linhas, a barra do grupo é exibida com uma sombra laranja mais escura e a célula do membro do grupo de linhas correspondente é selecionada na superfície de design.</span><span class="sxs-lookup"><span data-stu-id="40894-151">When you select the Subcat group in the Row Groups pane, the group bar turns a darker shade of orange, and the corresponding row group member cell is selected on the design surface.</span></span>  
  
## <a name="displaying-data-on-rows-and-columns"></a><span data-ttu-id="40894-152">Exibindo dados em linhas e colunas</span><span class="sxs-lookup"><span data-stu-id="40894-152">Displaying Data on Rows and Columns</span></span>  
 <span data-ttu-id="40894-153">Linhas e grupos de linhas e colunas e grupos de colunas têm relações idênticas.</span><span class="sxs-lookup"><span data-stu-id="40894-153">Rows and row groups and columns and column groups have identical relationships.</span></span> <span data-ttu-id="40894-154">A seguinte descrição aborda como adicionar linhas para exibir detalhes e agrupar dados em linhas em uma região de dados tablix, embora os mesmos princípios se apliquem à adição de colunas para exibir dados detalhados e agrupados.</span><span class="sxs-lookup"><span data-stu-id="40894-154">The following discussion describes how to add rows to display detail and group data on rows in a tablix data region, but the same principles apply to adding columns to display detail and grouped data.</span></span>  
  
 <span data-ttu-id="40894-155">Para cada linha de uma região de dados tablix, uma linha permanece dentro ou fora de cada grupo de linhas.</span><span class="sxs-lookup"><span data-stu-id="40894-155">For each row in a tablix data region, a row is either inside or outside each row group.</span></span> <span data-ttu-id="40894-156">Caso esteja dentro de um grupo de linhas, a linha se repete uma vez para todos os valores exclusivos do grupo, o que é conhecido como *instância de grupo*.</span><span class="sxs-lookup"><span data-stu-id="40894-156">If the row is inside a row group, it repeats once for every unique value of the group, known as a *group instance*.</span></span> <span data-ttu-id="40894-157">Caso esteja fora de um grupo de linhas, ela se repete apenas uma vez em relação ao grupo.</span><span class="sxs-lookup"><span data-stu-id="40894-157">If the row is outside a row group, it repeats only once in relation to that group.</span></span> <span data-ttu-id="40894-158">Linhas fora de todos os grupos de linhas são estáticas e são repetidas apenas uma vez para a região de dados.</span><span class="sxs-lookup"><span data-stu-id="40894-158">Rows outside all row groups are static and repeat only once for the data region.</span></span> <span data-ttu-id="40894-159">Por exemplo, um cabeçalho da tabela ou linha de rodapé é uma linha estática.</span><span class="sxs-lookup"><span data-stu-id="40894-159">For example, a table header or footer row is a static row.</span></span> <span data-ttu-id="40894-160">As linhas que se repetem em pelo menos um grupo são dinâmicas.</span><span class="sxs-lookup"><span data-stu-id="40894-160">Rows that repeat with at least one group are dynamic.</span></span>  
  
 <span data-ttu-id="40894-161">Quando há grupos aninhados, uma linha pode estar dentro de um grupo pai, mas fora de um grupo filho.</span><span class="sxs-lookup"><span data-stu-id="40894-161">When you have nested groups, a row can be inside a parent group but outside a child group.</span></span> <span data-ttu-id="40894-162">A linha se repete em todos os valores do grupo pai, mas é exibida apenas uma vez em relação ao grupo filho.</span><span class="sxs-lookup"><span data-stu-id="40894-162">The row repeats for every group value in the parent group, but displays only once in relation to the child group.</span></span> <span data-ttu-id="40894-163">Para exibir rótulos ou totais de um grupo, adicione uma linha fora do grupo.</span><span class="sxs-lookup"><span data-stu-id="40894-163">To display labels or totals for a group, add a row outside the group.</span></span> <span data-ttu-id="40894-164">Para exibir dados que se alteram a cada instância de grupo, adicione uma linha dentro do grupo.</span><span class="sxs-lookup"><span data-stu-id="40894-164">To display data that changes for every group instance, add a row inside the group.</span></span>  
  
 <span data-ttu-id="40894-165">Quando há grupos detalhados, cada linha detalhada permanece dentro do grupo.</span><span class="sxs-lookup"><span data-stu-id="40894-165">When you have detail groups, each detail row is inside the detail group.</span></span> <span data-ttu-id="40894-166">A linha se repete em todos os valores do conjunto de resultados da consulta do conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="40894-166">The row repeats for every value in the dataset query result set.</span></span>  
  
 <span data-ttu-id="40894-167">Para obter mais informações sobre hierarquias de grupos, consulte [Noções básicas sobre grupos &#40;Construtor de Relatórios e SSRS&#41;](understanding-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="40894-167">For more information about group hierarchies, see [Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="40894-168">A seguinte figura mostra uma região de dados tablix com grupos de linhas aninhados e um grupo detalhado.</span><span class="sxs-lookup"><span data-stu-id="40894-168">The following figure shows a tablix data region with nested row groups and a details group.</span></span>  
  
 <span data-ttu-id="40894-169">![Modo de exibição de Design, adicionar total de linhas ao grupo e à tabela](../media/rs-basictablegroupstotalscolordesign.gif "Modo de exibição de Design, adicionar total de linhas ao grupo e à tabela")</span><span class="sxs-lookup"><span data-stu-id="40894-169">![Design view, add total rows to group and table](../media/rs-basictablegroupstotalscolordesign.gif "Design view, add total rows to group and table")</span></span>  
  
 <span data-ttu-id="40894-170">Em uma região de dados tablix que exibe dados detalhados, o grupo detalhado é o grupo filho interno.</span><span class="sxs-lookup"><span data-stu-id="40894-170">For a tablix data region that displays detail data, the details group is the innermost child group.</span></span> <span data-ttu-id="40894-171">As linhas adicionadas a um grupo detalhado se repetem uma vez por linha no conjunto de resultados da consulta referente ao conjunto de dados vinculado à região de dados tablix.</span><span class="sxs-lookup"><span data-stu-id="40894-171">Rows that you add to a details group repeat once per row in the result set for the query for the dataset linked to this tablix data region.</span></span> <span data-ttu-id="40894-172">A seguinte figura mostra a última página do relatório renderizado.</span><span class="sxs-lookup"><span data-stu-id="40894-172">The following figure shows the last page of the rendered report.</span></span> <span data-ttu-id="40894-173">Nela, é possível ver as últimas linhas detalhadas e a linha de subtotal referente ao último pedido.</span><span class="sxs-lookup"><span data-stu-id="40894-173">In this figure, you can see the last detail rows and the subtotal row for the last order.</span></span>  
  
 <span data-ttu-id="40894-174">![Visualização, Tabela com Totais de Grupo, últimas linhas](../media/rs-basictablegroupstotalscolorpreviewbottom.gif "Visualização, Tabela com Totais de Grupo, últimas linhas")</span><span class="sxs-lookup"><span data-stu-id="40894-174">![Preview, Table with Group Totals, last rows](../media/rs-basictablegroupstotalscolorpreviewbottom.gif "Preview, Table with Group Totals, last rows")</span></span>  
  
 <span data-ttu-id="40894-175">Para cada coluna de uma região de dados tablix, se aplicam os mesmos princípios.</span><span class="sxs-lookup"><span data-stu-id="40894-175">For each column in a tablix data region, the same principles apply.</span></span> <span data-ttu-id="40894-176">Por exemplo, uma coluna está dentro ou fora de cada grupo de colunas. Para exibir totais, adicione uma coluna fora do grupo.</span><span class="sxs-lookup"><span data-stu-id="40894-176">For example, a column is either inside or outside each column group; to display totals, add a column outside the group.</span></span>  
  
 <span data-ttu-id="40894-177">Para remover linhas e colunas associadas a um grupo, é possível excluí-lo.</span><span class="sxs-lookup"><span data-stu-id="40894-177">To remove rows and columns associated to a group, you can delete the group.</span></span> <span data-ttu-id="40894-178">Ao excluir um grupo, você tem a opção de excluir apenas a definição de grupo ou excluir o grupo e todas as linhas e colunas associadas.</span><span class="sxs-lookup"><span data-stu-id="40894-178">When you delete a group, you have the choice between deleting the group definition only or deleting the group and all its associated rows and columns.</span></span> <span data-ttu-id="40894-179">Excluindo apenas o grupo, você preserva o layout da linha e da coluna na região de dados.</span><span class="sxs-lookup"><span data-stu-id="40894-179">By deleting just the group, you preserve the row and column layout on the data region.</span></span> <span data-ttu-id="40894-180">Ao excluir o grupo e as linhas e colunas relacionadas, você está excluindo todas as linhas e colunas estáticas (inclusive cabeçalhos e rodapés do grupo), além das linhas e colunas dinâmicas (inclusive instâncias de grupo) associadas ao grupo.</span><span class="sxs-lookup"><span data-stu-id="40894-180">When you delete the group and its related rows and columns, you are deleting all static rows and columns (including group headers and footers) and dynamic rows and columns (including group instances) that are associated with that group.</span></span>  
  
 <span data-ttu-id="40894-181">Para obter instruções passo a passo sobre como adicionar ou excluir linhas e colunas, consulte [Inserir ou excluir uma linha &#40;Construtor de Relatórios e SSRS&#41;](insert-or-delete-a-row-report-builder-and-ssrs.md) e [Inserir ou excluir uma coluna &#40;Construtor de Relatórios e SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="40894-181">For step-by-step instructions about adding or deleting rows and columns, see [Insert or Delete a Row &#40;Report Builder and SSRS&#41;](insert-or-delete-a-row-report-builder-and-ssrs.md) and [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
## <a name="understanding-tablix-cells"></a><span data-ttu-id="40894-182">Compreendendo células Tablix</span><span class="sxs-lookup"><span data-stu-id="40894-182">Understanding Tablix Cells</span></span>  
 <span data-ttu-id="40894-183">As células tablix pertencem a uma das quatro áreas tablix: corpo, áreas do grupo de linhas ou de colunas ou canto.</span><span class="sxs-lookup"><span data-stu-id="40894-183">Tablix cells belong to one of four tablix areas: the tablix body, tablix row or tablix column group areas, or the tablix corner.</span></span> <span data-ttu-id="40894-184">Embora cada célula possa exibir qualquer valor no conjunto de dados, a função padrão de cada célula é determinada pelo local.</span><span class="sxs-lookup"><span data-stu-id="40894-184">Although each cell can potentially display any value in the dataset, the default function for each cell is determined by its location.</span></span> <span data-ttu-id="40894-185">Para obter informações detalhadas sobre áreas Tablix, consulte [Áreas da região de dados Tablix &#40;Construtor de Relatórios e SSRS&#41;](tablix-data-region-areas-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="40894-185">For detailed information about tablix areas, see [Tablix Data Region Areas &#40;Report Builder and SSRS&#41;](tablix-data-region-areas-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="40894-186">Por padrão, células nas áreas dos grupos de linhas e de colunas tablix representam membros de grupo.</span><span class="sxs-lookup"><span data-stu-id="40894-186">By default, cells in tablix row and column group areas represent group members.</span></span> <span data-ttu-id="40894-187">Os membros do grupo são organizados em várias estruturas de árvore na definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="40894-187">Group members are organized into multiple tree structures in the report definition.</span></span> <span data-ttu-id="40894-188">A hierarquia de grupo da linha se expande horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="40894-188">The row group hierarchy expands horizontally.</span></span> <span data-ttu-id="40894-189">A hierarquia de grupo da coluna se expande verticalmente.</span><span class="sxs-lookup"><span data-stu-id="40894-189">The column group hierarchy expands vertically.</span></span> <span data-ttu-id="40894-190">Essas células são adicionadas automaticamente quando você cria um grupo e exibem os valores exclusivos de um grupo em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="40894-190">These cells are added automatically when you create a group, and display the unique values for a group at run time.</span></span>  
  
 <span data-ttu-id="40894-191">As células no canto tablix são criadas quando há áreas dos grupos de linhas e de colunas.</span><span class="sxs-lookup"><span data-stu-id="40894-191">Cells in the tablix corner are created when there are both row and column group areas.</span></span> <span data-ttu-id="40894-192">É possível mesclar células nessa área para criar um rótulo ou inserir outro item de relatório.</span><span class="sxs-lookup"><span data-stu-id="40894-192">You can merge cells in this area to create a label or embed another report item.</span></span>  
  
 <span data-ttu-id="40894-193">As células na área do corpo tablix podem exibir dados detalhados quando a célula está em uma linha ou coluna detalhada e dados agregados quando ela se encontra em uma linha ou coluna do grupo.</span><span class="sxs-lookup"><span data-stu-id="40894-193">Cells in the tablix body area can display detail data when the cell is in a detail row or column and aggregated group data when the cell is in a group row or column.</span></span> <span data-ttu-id="40894-194">O escopo dos dados de uma célula é a interseção entre os grupos internos de linhas e de colunas aos quais a célula pertence.</span><span class="sxs-lookup"><span data-stu-id="40894-194">The scope for the data in a cell is the intersection of the innermost row group and innermost column group to which the cell belongs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="40894-195">Os dados reais exibidos referentes a cada célula formam a expressão avaliada do item de relatório que ela contém, normalmente uma caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="40894-195">The actual data that is displayed for each cell is the evaluated expression for the report item that the cell contains, which is typically a text box.</span></span> <span data-ttu-id="40894-196">Em uma célula pertencente a uma linha ou coluna detalhada, a expressão usa como padrão os dados detalhados (por exemplo, **[LineTotal])**.</span><span class="sxs-lookup"><span data-stu-id="40894-196">In a cell that belongs to a detail row or column, the expression defaults to the detail data (for example, **[LineTotal])**.</span></span> <span data-ttu-id="40894-197">Em uma célula não pertencente a uma linha ou coluna detalhada, a expressão usa como padrão uma função de agregação (por exemplo, **Sum[LineTotal])**.</span><span class="sxs-lookup"><span data-stu-id="40894-197">In a cell that does not belong to a detail row or column, the expression defaults to an aggregate function (for example, **Sum[LineTotal])**.</span></span> <span data-ttu-id="40894-198">Caso uma expressão não especifique uma função de agregação mesmo que a célula pertença a uma linha ou coluna do grupo, é exibido o primeiro valor do grupo.</span><span class="sxs-lookup"><span data-stu-id="40894-198">If an expression does not specify an aggregate function even though the cell belongs to a group row or column, the first value in the group is displayed.</span></span> <span data-ttu-id="40894-199">Para obter mais informações sobre agregações, consulte [Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="40894-199">For more information about aggregates, see [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
### <a name="merging-and-splitting-cells"></a><span data-ttu-id="40894-200">Mesclando e dividindo células</span><span class="sxs-lookup"><span data-stu-id="40894-200">Merging and Splitting Cells</span></span>  
 <span data-ttu-id="40894-201">Em uma área tablix, é possível mesclar várias células adjacentes.</span><span class="sxs-lookup"><span data-stu-id="40894-201">Inside a tablix area, you can merge multiple adjacent cells together.</span></span> <span data-ttu-id="40894-202">Por exemplo, você pode criar células para rótulos que incluam várias colunas ou linhas.</span><span class="sxs-lookup"><span data-stu-id="40894-202">For example, you can create cells for labels that span multiple columns or rows.</span></span>  
  
 <span data-ttu-id="40894-203">Na área de canto tablix, as células podem ser combinadas em uma única direção por vez: horizontalmente nas colunas ou verticalmente nas linhas.</span><span class="sxs-lookup"><span data-stu-id="40894-203">In the tablix corner area, cells can be combined in only one direction at a time: horizontally across columns or vertically down rows.</span></span> <span data-ttu-id="40894-204">Para mesclar um bloco de células, mescle primeiro as células horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="40894-204">To merge a block of cells, merge the cells horizontally first.</span></span> <span data-ttu-id="40894-205">Após a mesclagem de todas as células em uma única célula em cada linha, selecione as células adjacentes (é possível selecionar todas as células adjacentes em uma coluna) e as mescle.</span><span class="sxs-lookup"><span data-stu-id="40894-205">After all cells have been merged into a single cell in each row, select adjacent cells (you can select all adjacent cells in a column) and merge them.</span></span>  
  
 <span data-ttu-id="40894-206">Na área de corpo tablix, as células só podem ser mescladas horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="40894-206">In the tablix body area, cells can only be merged horizontally.</span></span> <span data-ttu-id="40894-207">Não há suporte para a mesclagem vertical.</span><span class="sxs-lookup"><span data-stu-id="40894-207">Merging cells vertically is not supported.</span></span>  
  
 <span data-ttu-id="40894-208">Para obter mais informações, consulte [Mesclar células em uma região de dados &#40;Construtor de Relatórios e SSRS&#41;](merge-cells-in-a-data-region-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="40894-208">For more information, see [Merge Cells in a Data Region &#40;Report Builder and SSRS&#41;](merge-cells-in-a-data-region-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="40894-209">É possível dividir uma célula mesclada previamente.</span><span class="sxs-lookup"><span data-stu-id="40894-209">You can split a cell that was previously merged.</span></span> <span data-ttu-id="40894-210">Você pode dividir as células horizontalmente em colunas ou verticalmente em linhas.</span><span class="sxs-lookup"><span data-stu-id="40894-210">You can split cells horizontally across columns or vertically down rows.</span></span> <span data-ttu-id="40894-211">Para dividir uma célula em um bloco de células, divida primeiro a célula horizontalmente e divida verticalmente quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="40894-211">To split a cell into a block of cells, split the cell horizontally first, and then split vertically as many times as necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40894-212">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="40894-212">See Also</span></span>  
 [<span data-ttu-id="40894-213">Região de dados Tablix &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="40894-213">Tablix Data Region &#40;Report Builder and SSRS&#41;</span></span>](../tablix-data-region-report-builder-and-ssrs.md)  
  
  