---
title: Classificar dados em uma região de dados (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2fcb9be2-1daa-4c92-ad00-5f63cdf39f70
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bc1fb458066bb942a490b08c0faad876dd3d5438
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684495"
---
# <a name="sort-data-in-a-data-region-report-builder-and-ssrs"></a><span data-ttu-id="1b862-102">Classificar dados em uma região de dados (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="1b862-102">Sort Data in a Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="1b862-103">Para alterar a ordem de classificação dos dados em uma região quando um relatório for executado pela primeira vez, defina a expressão de classificação na região de dados ou no grupo.</span><span class="sxs-lookup"><span data-stu-id="1b862-103">To change the sort order of data in a data region when a report first runs, you must set the sort expression on the data region or group.</span></span> <span data-ttu-id="1b862-104">Por padrão, a expressão de classificação de um grupo é definida automaticamente como o mesmo valor da expressão do grupo.</span><span class="sxs-lookup"><span data-stu-id="1b862-104">By default, the sort expression for a group is automatically set to the same value as the group expression.</span></span>  
  
-   <span data-ttu-id="1b862-105">Em uma região de dados tablix, defina a expressão de classificação da região de dados ou de cada grupo, inclusive o grupo detalhado.</span><span class="sxs-lookup"><span data-stu-id="1b862-105">In a tablix data region, set the sort expression for the data region or for each group, including the details group.</span></span> <span data-ttu-id="1b862-106">Se você tiver apenas um grupo detalhado em uma região de dados tablix, será possível definir uma expressão de classificação na consulta, na região de dados ou no grupo detalhado, e todos têm o mesmo efeito.</span><span class="sxs-lookup"><span data-stu-id="1b862-106">If you have only one details group in a tablix data region, you can define a sort expression in the query, on the data region, or on the details group and they all have the same effect.</span></span>  
  
-   <span data-ttu-id="1b862-107">Em uma região de dados do gráfico, defina a expressão de classificação dos grupos Categoria e Série para controlar a ordem de classificação de cada um.</span><span class="sxs-lookup"><span data-stu-id="1b862-107">In a chart data region, set the sort expression for the Category and Series groups to control the sort order for each group.</span></span> <span data-ttu-id="1b862-108">A ordem das cores em uma legenda de gráfico é determinada pela expressão de classificação dos pontos de dados no grupo Categoria.</span><span class="sxs-lookup"><span data-stu-id="1b862-108">The order for colors in a chart legend is determined by the sort expression for the data points in the Category group.</span></span>  
  
-   <span data-ttu-id="1b862-109">Em uma região de dados do medidor, você normalmente não precisa classificar dados porque o medidor exibe um único valor relativo a um intervalo.</span><span class="sxs-lookup"><span data-stu-id="1b862-109">In a gauge data region, you do not typically need to sort data because the gauge displays a single value relative to a range.</span></span> <span data-ttu-id="1b862-110">Caso precise classificar dados em um medidor, você deve primeiro definir um grupo e, em seguida, definir a expressão de classificação do grupo.</span><span class="sxs-lookup"><span data-stu-id="1b862-110">If you do need sort data in a gauge, you must first define a group, and then set the sort expression for the group.</span></span>  
  
 <span data-ttu-id="1b862-111">Para obter mais informações, consulte [Filtrar, agrupar e classificar dados &#40;Construtor de Relatórios e SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1b862-111">For more information, see [Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="1b862-112">Em uma região de dados tablix, também é possível adicionar um botão de classificação interativo à parte superior do cabeçalho da coluna para permitir que o usuário altere a ordem de classificação dos grupos ou das linhas detalhadas.</span><span class="sxs-lookup"><span data-stu-id="1b862-112">For a tablix data region, you can also add an interactive sort button to the top of a column header to provide the user with the ability to change the sort order of groups or detail rows.</span></span> <span data-ttu-id="1b862-113">Para obter mais informações, consulte [Classificação interativa e &#40;Construtor de Relatórios e SSRS&#41;](interactive-sort-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1b862-113">For more information, see [Interactive Sort &#40;Report Builder and SSRS&#41;](interactive-sort-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-sort-data-in-a-tablix-data-region"></a><span data-ttu-id="1b862-114">Para classificar dados em uma região de dados Tablix</span><span class="sxs-lookup"><span data-stu-id="1b862-114">To sort data in a Tablix data region</span></span>  
  
1.  <span data-ttu-id="1b862-115">Na superfície de design, clique com o botão direito do mouse em um identificador de linha e clique em **Propriedades do Tablix**.</span><span class="sxs-lookup"><span data-stu-id="1b862-115">On the design surface, right-click a row handle, and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="1b862-116">Clique em **Classificar**.</span><span class="sxs-lookup"><span data-stu-id="1b862-116">Click **Sorting**.</span></span>  
  
3.  <span data-ttu-id="1b862-117">Em cada expressão de classificação, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="1b862-117">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="1b862-118">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1b862-118">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="1b862-119">Digite ou selecione uma expressão pela qual os dados são classificados.</span><span class="sxs-lookup"><span data-stu-id="1b862-119">Type or select an expression by which to sort the data.</span></span>  
  
    3.  <span data-ttu-id="1b862-120">Na lista suspensa da coluna **Ordem** , escolha a direção de classificação de cada expressão.</span><span class="sxs-lookup"><span data-stu-id="1b862-120">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="1b862-121">**A-Z** classifica a expressão em ordem crescente.</span><span class="sxs-lookup"><span data-stu-id="1b862-121">**A-Z** sorts the expression in ascending order.</span></span> <span data-ttu-id="1b862-122">**Z-A** classifica a expressão em ordem decrescente.</span><span class="sxs-lookup"><span data-stu-id="1b862-122">**Z-A** sorts the expression in descending order.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-sort-values-in-a-group-including-the-details-group-for-a-tablix"></a><span data-ttu-id="1b862-123">Para classificar valores em um grupo, inclusive o grupo detalhado, para um Tablix</span><span class="sxs-lookup"><span data-stu-id="1b862-123">To sort values in a group, including the details group, for a Tablix</span></span>  
  
1.  <span data-ttu-id="1b862-124">Na superfície de design, clique na região de dados tablix para selecioná-la.</span><span class="sxs-lookup"><span data-stu-id="1b862-124">On the design surface, click in the tablix data region to select it.</span></span> <span data-ttu-id="1b862-125">O painel Agrupamento exibe os grupos de linhas e de colunas da região de dados Tablix.</span><span class="sxs-lookup"><span data-stu-id="1b862-125">The Grouping pane displays the row groups and column groups for the Tablix data region.</span></span>  
  
2.  <span data-ttu-id="1b862-126">No painel Grupos de Linhas, clique com o botão direito do mouse no nome do grupo e clique em **Editar Grupo**.</span><span class="sxs-lookup"><span data-stu-id="1b862-126">In the Row Groups pane, right-click the group name, and then click **Edit Group**.</span></span>  
  
3.  <span data-ttu-id="1b862-127">Na caixa de diálogo **Grupo Tablix** , clique em **Classificar**.</span><span class="sxs-lookup"><span data-stu-id="1b862-127">In the **Tablix Group** dialog box, click **Sort**.</span></span>  
  
4.  <span data-ttu-id="1b862-128">Em cada expressão de classificação, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="1b862-128">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="1b862-129">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1b862-129">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="1b862-130">Digite ou selecione uma expressão pela qual os dados são classificados.</span><span class="sxs-lookup"><span data-stu-id="1b862-130">Type or select an expression by which to sort the data.</span></span>  
  
    3.  <span data-ttu-id="1b862-131">Na lista suspensa da coluna **Ordem** , escolha a direção de classificação de cada expressão.</span><span class="sxs-lookup"><span data-stu-id="1b862-131">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="1b862-132">**A-Z** classifica a expressão em ordem crescente.</span><span class="sxs-lookup"><span data-stu-id="1b862-132">**A-Z** sorts the expression in ascending order.</span></span> <span data-ttu-id="1b862-133">**Z-A** classifica a expressão em ordem decrescente.</span><span class="sxs-lookup"><span data-stu-id="1b862-133">**Z-A** sorts the expression in descending order.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-sort-x-axis-labels-in-alphabetical-order-on-a-chart"></a><span data-ttu-id="1b862-134">Para classificar rótulos do eixo x em ordem alfabética em um gráfico</span><span class="sxs-lookup"><span data-stu-id="1b862-134">To sort x-axis labels in alphabetical order on a chart</span></span>  
  
1.  <span data-ttu-id="1b862-135">Clique com o botão direito do mouse em um campo na área para arrastar e soltar Campo de Categoria e clique em **Propriedades do Grupo de Categorias**.</span><span class="sxs-lookup"><span data-stu-id="1b862-135">Right-click a field in the Category Field drop-zone and click **Category GroupProperties**.</span></span>  
  
2.  <span data-ttu-id="1b862-136">Na caixa de diálogo **Propriedades do Grupo de Categorias** , clique em **Classificação**.</span><span class="sxs-lookup"><span data-stu-id="1b862-136">In the **Category Group Properties** dialog box, click **Sorting**.</span></span>  
  
3.  <span data-ttu-id="1b862-137">Em cada expressão de classificação, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="1b862-137">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="1b862-138">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1b862-138">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="1b862-139">Selecione a expressão correspondente ao campo de agrupamento.</span><span class="sxs-lookup"><span data-stu-id="1b862-139">Select the expression that matches your grouping field.</span></span> <span data-ttu-id="1b862-140">É possível verificar a expressão do campo de agrupamento clicando em **Agrupamento**.</span><span class="sxs-lookup"><span data-stu-id="1b862-140">You can verify the expression for the grouping field by clicking **Grouping**.</span></span>  
  
    3.  <span data-ttu-id="1b862-141">Na lista suspensa da coluna **Ordem** , escolha a direção de classificação de cada expressão.</span><span class="sxs-lookup"><span data-stu-id="1b862-141">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="1b862-142">**A-Z** classifica a expressão em ordem alfabética crescente.</span><span class="sxs-lookup"><span data-stu-id="1b862-142">**A-Z** sorts the expression in ascending alphabetical order.</span></span> <span data-ttu-id="1b862-143">**Z-A** classifica a expressão em ordem alfabética decrescente.</span><span class="sxs-lookup"><span data-stu-id="1b862-143">**Z-A** sorts the expression in descending alphabetical order.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-sort-the-data-points-in-ascending-or-descending-order-on-a-chart"></a><span data-ttu-id="1b862-144">Para classificar os pontos de dados em ordem crescente ou decrescente em um gráfico</span><span class="sxs-lookup"><span data-stu-id="1b862-144">To sort the data points in ascending or descending order on a chart</span></span>  
  
1.  <span data-ttu-id="1b862-145">Clique com o botão direito do mouse em um campo na área para arrastar e soltar Campo de Categoria e clique em **Propriedades do Grupo de Categorias**.</span><span class="sxs-lookup"><span data-stu-id="1b862-145">Right-click a field in the Category Field drop zone and click **Category GroupProperties**.</span></span>  
  
2.  <span data-ttu-id="1b862-146">Na caixa de diálogo **Propriedades do Grupo de Categorias** , clique em **Classificação**.</span><span class="sxs-lookup"><span data-stu-id="1b862-146">In the **Category Group Properties** dialog box, click **Sorting**.</span></span>  
  
3.  <span data-ttu-id="1b862-147">Em cada expressão de classificação, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="1b862-147">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="1b862-148">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1b862-148">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="1b862-149">Selecione a expressão correspondente ao campo de dados.</span><span class="sxs-lookup"><span data-stu-id="1b862-149">Select the expression that matches your data field.</span></span> <span data-ttu-id="1b862-150">Na maior parte dos casos, trata-se de um valor agregado como, por exemplo, `=Sum(Fields!Quantity.Value)`.</span><span class="sxs-lookup"><span data-stu-id="1b862-150">In most cases, this is an aggregated value, such as `=Sum(Fields!Quantity.Value)`.</span></span>  
  
    3.  <span data-ttu-id="1b862-151">Na lista suspensa da coluna **Ordem** , escolha a direção de classificação de cada expressão.</span><span class="sxs-lookup"><span data-stu-id="1b862-151">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="1b862-152">**A-Z** classifica a expressão em ordem crescente.</span><span class="sxs-lookup"><span data-stu-id="1b862-152">**A-Z** sorts the expression in ascending order.</span></span> <span data-ttu-id="1b862-153">**Z-A** classifica a expressão em ordem decrescente.</span><span class="sxs-lookup"><span data-stu-id="1b862-153">**Z-A** sorts the expression in descending order.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-sort-data-in-ascending-or-descending-order-for-display-on-a-gauge"></a><span data-ttu-id="1b862-154">Para classificar dados em ordem crescente ou decrescente a serem exibidos em um medidor</span><span class="sxs-lookup"><span data-stu-id="1b862-154">To sort data in ascending or descending order for display on a gauge</span></span>  
  
1.  <span data-ttu-id="1b862-155">Clique com o botão direito do mouse no medidor e clique em **Adicionar Grupo de Dados**.</span><span class="sxs-lookup"><span data-stu-id="1b862-155">Right-click the gauge and click **Add Data Group**.</span></span>  
  
2.  <span data-ttu-id="1b862-156">Na caixa de diálogo **Propriedades do Grupo do Painel do Medidor** , clique em **Geral** , se necessário.</span><span class="sxs-lookup"><span data-stu-id="1b862-156">In the **Gauge Panel GroupProperties** dialog box, click **General** if necessary.</span></span>  
  
3.  <span data-ttu-id="1b862-157">Em **Expressões de grupo**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1b862-157">In **Group expressions**, click **Add**.</span></span>  
  
4.  <span data-ttu-id="1b862-158">Em **Agrupar em**, digite ou selecione uma expressão pela qual agrupar os dados.</span><span class="sxs-lookup"><span data-stu-id="1b862-158">In **Group on**, type or select an expression by which to group the data.</span></span>  
  
5.  <span data-ttu-id="1b862-159">Repita as etapas 3 e 4 até que todas as expressões de grupo que deseja usar sejam adicionadas.</span><span class="sxs-lookup"><span data-stu-id="1b862-159">Repeat steps 3 and 4 until you have added all the group expressions you want to use.</span></span>  
  
6.  <span data-ttu-id="1b862-160">Clique em **Classificar**.</span><span class="sxs-lookup"><span data-stu-id="1b862-160">Click **Sorting**.</span></span>  
  
7.  <span data-ttu-id="1b862-161">Em cada expressão de classificação, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="1b862-161">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="1b862-162">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1b862-162">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="1b862-163">Selecione a expressão correspondente ao campo de agrupamento.</span><span class="sxs-lookup"><span data-stu-id="1b862-163">Select the expression that matches your grouping field.</span></span> <span data-ttu-id="1b862-164">É possível verificar a expressão do campo de agrupamento clicando em **Agrupamento**.</span><span class="sxs-lookup"><span data-stu-id="1b862-164">You can verify the expression for the grouping field by clicking **Grouping**.</span></span>  
  
    3.  <span data-ttu-id="1b862-165">Na lista suspensa da coluna **Ordem** , escolha a direção de classificação de cada expressão.</span><span class="sxs-lookup"><span data-stu-id="1b862-165">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="1b862-166">**A-Z** classifica a expressão em ordem crescente.</span><span class="sxs-lookup"><span data-stu-id="1b862-166">**A-Z** sorts the expression in ascending order.</span></span> <span data-ttu-id="1b862-167">**Z-A** classifica a expressão em ordem decrescente.</span><span class="sxs-lookup"><span data-stu-id="1b862-167">**Z-A** sorts the expression in descending order.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="1b862-168">Para obter mais informações sobre como os dados são agrupados em um medidor, consulte [Medidores &#40;Construtor de Relatórios e SSRS&#41;](gauges-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1b862-168">For more information about how data is grouped in a gauge, see [Gauges &#40;Report Builder and SSRS&#41;](gauges-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b862-169">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1b862-169">See Also</span></span>  
 <span data-ttu-id="1b862-170">[Construtor de Relatórios ajuda para caixas de diálogo, painéis e assistentes](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="1b862-170">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="1b862-171">[Gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1b862-171">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1b862-172">[Formatando rótulos de eixo em um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1b862-172">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="1b862-173">Especificar cores consistentes em gráficos com várias formas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1b862-173">Specify Consistent Colors across Multiple Shape Charts &#40;Report Builder and SSRS&#41;</span></span>](shape-charts-report-builder-and-ssrs.md)  
  
  
