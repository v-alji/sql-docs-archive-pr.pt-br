---
title: Adicionar um filtro (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 10ae54e7-0e8a-4dff-995d-05516c51d076
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 61a5444c437027d92a9f054e74cbcac6af5cc776
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686061"
---
# <a name="add-a-filter-report-builder-and-ssrs"></a><span data-ttu-id="7414a-102">Adicionar um filtro (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="7414a-102">Add a Filter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="7414a-103">Adicione um filtro a um conjunto de dados, região de dados ou grupo quando quiser incluir ou excluir valores específicos para cálculos ou exibição.</span><span class="sxs-lookup"><span data-stu-id="7414a-103">Add a filter to a dataset, data region, or group when you want to include or exclude specific values for calculations or display.</span></span> <span data-ttu-id="7414a-104">Os filtros são aplicados em tempo de execução, primeiro, no conjunto de dados, depois, na região de dados e, em seguida, no grupo, de cima para baixo nas hierarquias de grupo.</span><span class="sxs-lookup"><span data-stu-id="7414a-104">Filters are applied at run time first on the dataset, and then on the data region, and then on the group, in top-down order for group hierarchies.</span></span> <span data-ttu-id="7414a-105">Em uma tabela, matriz ou lista, os filtros para grupos de linha, grupos de coluna e grupos adjacentes são aplicados de forma independente.</span><span class="sxs-lookup"><span data-stu-id="7414a-105">In a table, matrix, or list, filters for row groups, column groups, and adjacent groups are applied independently.</span></span> <span data-ttu-id="7414a-106">Em um gráfico, os filtros para grupos de categoria e grupos de série são aplicados de forma independente.</span><span class="sxs-lookup"><span data-stu-id="7414a-106">In a chart, filters for category groups and series groups are applied independently.</span></span>  
  
 <span data-ttu-id="7414a-107">Para adicionar um filtro, é necessário especificar uma ou mais equações de filtro.</span><span class="sxs-lookup"><span data-stu-id="7414a-107">To add a filter, you must specify one or more filter equations.</span></span> <span data-ttu-id="7414a-108">Uma equação de filtro é composta por uma expressão que identifica os dados que você deseja filtrar, um operador, e o valor para comparação.</span><span class="sxs-lookup"><span data-stu-id="7414a-108">A filter equation consists of an expression that identifies the data that you want to filter, an operator, and the value to compare to.</span></span> <span data-ttu-id="7414a-109">Os tipos de dados dos dados filtrados e o valor devem coincidir.</span><span class="sxs-lookup"><span data-stu-id="7414a-109">The data types of the filtered data and the value must match.</span></span> <span data-ttu-id="7414a-110">Não há suporte para filtragem de valores de agregação para um conjunto de dados ou região de dados.</span><span class="sxs-lookup"><span data-stu-id="7414a-110">Filtering on aggregate values for a dataset or data region is not supported.</span></span>  
  
 <span data-ttu-id="7414a-111">Para filtrar pontos de dados em um gráfico, você pode definir um filtro em um grupo de categoria ou um grupo de série.</span><span class="sxs-lookup"><span data-stu-id="7414a-111">To filter data points in a chart, you can set a filter on a category group or a series group.</span></span> <span data-ttu-id="7414a-112">Por padrão, o gráfico usa a função interna Sum para agregar valores que pertencem ao mesmo grupo em um ponto de dados individual na série.</span><span class="sxs-lookup"><span data-stu-id="7414a-112">By default, the chart uses the built-in function Sum to aggregate values that belong to the same group into an individual data point in the series.</span></span> <span data-ttu-id="7414a-113">Se você alterar a função de agregação de uma série, deverá alterar a função de agregação na expressão de filtro.</span><span class="sxs-lookup"><span data-stu-id="7414a-113">If you change the aggregate function of a series, you must change the aggregate function in the filter expression.</span></span>  
  
 <span data-ttu-id="7414a-114">Para obter mais informações sobre como filtrar conjuntos de dados inseridos e compartilhados, consulte [Adicionar um filtro a um conjunto de dados &#40;Construtor de Relatórios e SSRS&#41;](../report-data/add-a-filter-to-a-dataset-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7414a-114">For more information about filtering embedded and shared datasets, see [Add a Filter to a Dataset &#40;Report Builder and SSRS&#41;](../report-data/add-a-filter-to-a-dataset-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-a-filter-on-a-data-region"></a><span data-ttu-id="7414a-115">Para definir um filtro em uma região de dados</span><span class="sxs-lookup"><span data-stu-id="7414a-115">To set a filter on a data region</span></span>  
  
1.  <span data-ttu-id="7414a-116">Abra um relatório no modo de exibição de **Design** .</span><span class="sxs-lookup"><span data-stu-id="7414a-116">Open a report in **Design** view.</span></span>  
  
2.  <span data-ttu-id="7414a-117">Selecione a região de dados na superfície de design e clique com o botão direito do mouse em _\<data region>_ **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="7414a-117">Select the data region on the design surface, and then right-click _\<data region>_**Properties**.</span></span> <span data-ttu-id="7414a-118">Para um medidor, selecione **Propriedades do Painel de Medidores**.</span><span class="sxs-lookup"><span data-stu-id="7414a-118">For a gauge, select **Gauge Panel Properties**.</span></span> <span data-ttu-id="7414a-119">A _\<data region>_ caixa de diálogo **Propriedades** é aberta.</span><span class="sxs-lookup"><span data-stu-id="7414a-119">The _\<data region>_**Properties** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7414a-120">Em uma região de dados do Tablix, clique com o botão direito do mouse na alça de canto da célula, linha ou coluna e clique em **Propriedades do Tablix**.</span><span class="sxs-lookup"><span data-stu-id="7414a-120">On a Tablix data region, right-click the corner cell or a row or column handle, and then click **Tablix Properties**.</span></span>  
  
3.  <span data-ttu-id="7414a-121">Clique em **Filtros**.</span><span class="sxs-lookup"><span data-stu-id="7414a-121">Click **Filters**.</span></span> <span data-ttu-id="7414a-122">Isso exibirá a lista atual de equações de filtros.</span><span class="sxs-lookup"><span data-stu-id="7414a-122">This displays the current list of filter equations.</span></span> <span data-ttu-id="7414a-123">Por padrão, a lista está vazia.</span><span class="sxs-lookup"><span data-stu-id="7414a-123">By default, the list is empty.</span></span>  
  
4.  <span data-ttu-id="7414a-124">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="7414a-124">Click **Add**.</span></span> <span data-ttu-id="7414a-125">Uma nova equação de filtro em branco é exibida.</span><span class="sxs-lookup"><span data-stu-id="7414a-125">A new blank filter equation appears.</span></span>  
  
5.  <span data-ttu-id="7414a-126">Em **Expressão**, digite ou selecione a expressão do campo a ser filtrada.</span><span class="sxs-lookup"><span data-stu-id="7414a-126">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="7414a-127">Para editar a expressão, clique no botão de expressão (*fx*).</span><span class="sxs-lookup"><span data-stu-id="7414a-127">To edit the expression, click the expression (*fx*) button.</span></span>  
  
6.  <span data-ttu-id="7414a-128">Na caixa suspensa, selecione o tipo de dados que coincide com o tipo de dados da expressão criada na etapa 5.</span><span class="sxs-lookup"><span data-stu-id="7414a-128">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
7.  <span data-ttu-id="7414a-129">Na caixa **Operador** , selecione o operador que você deseja que o filtro use para comparar os valores nas caixas **Expressão** e **Valor** .</span><span class="sxs-lookup"><span data-stu-id="7414a-129">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="7414a-130">O operador escolhido determinará o número de valores que serão usados na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="7414a-130">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
8.  <span data-ttu-id="7414a-131">Na caixa **Valor** , digite a expressão ou o valor em relação ao qual você deseja que o filtro avalie o valor em **Expressão**.</span><span class="sxs-lookup"><span data-stu-id="7414a-131">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="7414a-132">Para obter exemplos de equações de filtro, consulte [Exemplos de equações de filtro &#40;Construtor de Relatórios e SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7414a-132">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-set-a-filter-on-a-tablix-row-or-column-group"></a><span data-ttu-id="7414a-133">Para definir um filtro em um grupo de colunas ou linhas Tablix</span><span class="sxs-lookup"><span data-stu-id="7414a-133">To set a filter on a Tablix row or column group</span></span>  
  
1.  <span data-ttu-id="7414a-134">Abra um relatório no modo de exibição de **Design** .</span><span class="sxs-lookup"><span data-stu-id="7414a-134">Open a report in **Design** view.</span></span>  
  
2.  <span data-ttu-id="7414a-135">Clique com o botão direito do mouse na região de dados da tabela, matriz ou lista na superfície de design para selecioná-la.</span><span class="sxs-lookup"><span data-stu-id="7414a-135">Right-click the table, matrix, or list data region on the design surface to select it.</span></span> <span data-ttu-id="7414a-136">O painel Agrupamento exibe os grupos do item selecionado.</span><span class="sxs-lookup"><span data-stu-id="7414a-136">The Grouping pane displays the groups for the selected item.</span></span>  
  
3.  <span data-ttu-id="7414a-137">No painel Agrupamento, clique com o botão direito do mouse no grupo e clique em **Editar Grupo**.</span><span class="sxs-lookup"><span data-stu-id="7414a-137">In the Grouping pane, right-click the group, and then click **Edit Group**.</span></span> <span data-ttu-id="7414a-138">A caixa de diálogo **Grupo Tablix** é aberta.</span><span class="sxs-lookup"><span data-stu-id="7414a-138">The **Tablix Group** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="7414a-139">Clique em **Filtros**.</span><span class="sxs-lookup"><span data-stu-id="7414a-139">Click **Filters**.</span></span> <span data-ttu-id="7414a-140">Isso exibirá a lista atual de equações de filtros.</span><span class="sxs-lookup"><span data-stu-id="7414a-140">This displays the current list of filter equations.</span></span> <span data-ttu-id="7414a-141">Por padrão, a lista está vazia.</span><span class="sxs-lookup"><span data-stu-id="7414a-141">By default, the list is empty.</span></span>  
  
5.  <span data-ttu-id="7414a-142">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="7414a-142">Click **Add**.</span></span> <span data-ttu-id="7414a-143">Uma nova equação de filtro em branco é exibida.</span><span class="sxs-lookup"><span data-stu-id="7414a-143">A new blank filter equation appears.</span></span>  
  
6.  <span data-ttu-id="7414a-144">Em **Expressão**, digite ou selecione a expressão do campo a ser filtrada.</span><span class="sxs-lookup"><span data-stu-id="7414a-144">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="7414a-145">Para editar a expressão, clique no botão de expressão (*fx*).</span><span class="sxs-lookup"><span data-stu-id="7414a-145">To edit the expression, click the expression (*fx*) button.</span></span>  
  
7.  <span data-ttu-id="7414a-146">Na caixa suspensa, selecione o tipo de dados que coincide com o tipo de dados da expressão criada na etapa 5.</span><span class="sxs-lookup"><span data-stu-id="7414a-146">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
8.  <span data-ttu-id="7414a-147">Na caixa **Operador** , selecione o operador que você deseja que o filtro use para comparar os valores nas caixas **Expressão** e **Valor** .</span><span class="sxs-lookup"><span data-stu-id="7414a-147">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="7414a-148">O operador escolhido determinará o número de valores que serão usados na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="7414a-148">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
9. <span data-ttu-id="7414a-149">Na caixa **Valor** , digite a expressão ou o valor em relação ao qual você deseja que o filtro avalie o valor em **Expressão**.</span><span class="sxs-lookup"><span data-stu-id="7414a-149">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="7414a-150">Para obter exemplos de equações de filtro, consulte [Exemplos de equações de filtro &#40;Construtor de Relatórios e SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7414a-150">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-set-a-filter-on-a-chart-category-group"></a><span data-ttu-id="7414a-151">Para definir um filtro em um grupo de categoria de Gráfico</span><span class="sxs-lookup"><span data-stu-id="7414a-151">To set a filter on a Chart category group</span></span>  
  
1.  <span data-ttu-id="7414a-152">Abra um relatório no modo de exibição de **Design** .</span><span class="sxs-lookup"><span data-stu-id="7414a-152">Open a report in **Design** view.</span></span>  
  
2.  <span data-ttu-id="7414a-153">Na superfície do design, clique duas vezes no gráfico para chamar as zonas de descarte de campo de dados, série e categoria.</span><span class="sxs-lookup"><span data-stu-id="7414a-153">On the design surface, click the chart twice to bring up data, series and category field drop zones.</span></span>  
  
3.  <span data-ttu-id="7414a-154">Clique com o botão direito do mouse em um campo contido na área para arrastar e soltar do campo de categoria e selecione **Propriedades do Grupo de Categoria**.</span><span class="sxs-lookup"><span data-stu-id="7414a-154">Right-click on a field contained in the category field drop zone and select **Category Group Properties**.</span></span>  
  
4.  <span data-ttu-id="7414a-155">Clique em **Filtros**.</span><span class="sxs-lookup"><span data-stu-id="7414a-155">Click **Filters**.</span></span> <span data-ttu-id="7414a-156">Isso exibirá a lista atual de equações de filtros.</span><span class="sxs-lookup"><span data-stu-id="7414a-156">This displays the current list of filter equations.</span></span> <span data-ttu-id="7414a-157">Por padrão, a lista está vazia.</span><span class="sxs-lookup"><span data-stu-id="7414a-157">By default, the list is empty.</span></span>  
  
5.  <span data-ttu-id="7414a-158">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="7414a-158">Click **Add**.</span></span> <span data-ttu-id="7414a-159">Uma nova equação de filtro em branco é exibida.</span><span class="sxs-lookup"><span data-stu-id="7414a-159">A new blank filter equation appears.</span></span>  
  
6.  <span data-ttu-id="7414a-160">Em **Expressão**, digite ou selecione a expressão do campo a ser filtrada.</span><span class="sxs-lookup"><span data-stu-id="7414a-160">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="7414a-161">Para editar a expressão, clique no botão de expressão (*fx*).</span><span class="sxs-lookup"><span data-stu-id="7414a-161">To edit the expression, click the expression (*fx*) button.</span></span>  
  
7.  <span data-ttu-id="7414a-162">Na caixa suspensa, selecione o tipo de dados que coincide com o tipo de dados da expressão criada na etapa 5.</span><span class="sxs-lookup"><span data-stu-id="7414a-162">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
8.  <span data-ttu-id="7414a-163">Na caixa **Operador** , selecione o operador que você deseja que o filtro use para comparar os valores nas caixas **Expressão** e **Valor** .</span><span class="sxs-lookup"><span data-stu-id="7414a-163">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="7414a-164">O operador escolhido determinará o número de valores que serão usados na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="7414a-164">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
9. <span data-ttu-id="7414a-165">Na caixa **Valor** , digite a expressão ou o valor em relação ao qual você deseja que o filtro avalie o valor em **Expressão**.</span><span class="sxs-lookup"><span data-stu-id="7414a-165">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="7414a-166">Para obter exemplos de equações de filtro, consulte [Exemplos de equações de filtro &#40;Construtor de Relatórios e SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7414a-166">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-set-a-filter-on-a-chart-series-group"></a><span data-ttu-id="7414a-167">Para definir um filtro em um grupo de série de Gráfico</span><span class="sxs-lookup"><span data-stu-id="7414a-167">To set a filter on a Chart series group</span></span>  
  
1.  <span data-ttu-id="7414a-168">Abra um relatório no modo de exibição de **Design** .</span><span class="sxs-lookup"><span data-stu-id="7414a-168">Open a report in **Design** view.</span></span>  
  
2.  <span data-ttu-id="7414a-169">Na superfície do design, clique duas vezes no gráfico para chamar as zonas de descarte de campo de dados, série e categoria.</span><span class="sxs-lookup"><span data-stu-id="7414a-169">On the design surface, click the chart twice to bring up data, series and category field drop zones.</span></span>  
  
3.  <span data-ttu-id="7414a-170">Clique com o botão direito do mouse em um campo contido na área para arrastar e soltar do campo de série e selecione **Propriedades do Grupo de Série**.</span><span class="sxs-lookup"><span data-stu-id="7414a-170">Right-click on a field contained in the series field drop zone and select **Series Group Properties**.</span></span>  
  
4.  <span data-ttu-id="7414a-171">Clique em **Filtros**.</span><span class="sxs-lookup"><span data-stu-id="7414a-171">Click **Filters**.</span></span> <span data-ttu-id="7414a-172">Isso exibirá a lista atual de equações de filtros.</span><span class="sxs-lookup"><span data-stu-id="7414a-172">This displays the current list of filter equations.</span></span> <span data-ttu-id="7414a-173">Por padrão, a lista está vazia.</span><span class="sxs-lookup"><span data-stu-id="7414a-173">By default, the list is empty.</span></span>  
  
5.  <span data-ttu-id="7414a-174">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="7414a-174">Click **Add**.</span></span> <span data-ttu-id="7414a-175">Uma nova equação de filtro em branco é exibida.</span><span class="sxs-lookup"><span data-stu-id="7414a-175">A new blank filter equation appears.</span></span>  
  
6.  <span data-ttu-id="7414a-176">Em **Expressão**, digite ou selecione a expressão do campo a ser filtrada.</span><span class="sxs-lookup"><span data-stu-id="7414a-176">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="7414a-177">Para editar a expressão, clique no botão de expressão (*fx*).</span><span class="sxs-lookup"><span data-stu-id="7414a-177">To edit the expression, click the expression (*fx*) button.</span></span>  
  
7.  <span data-ttu-id="7414a-178">Na caixa suspensa, selecione o tipo de dados que coincide com o tipo de dados da expressão criada na etapa 5.</span><span class="sxs-lookup"><span data-stu-id="7414a-178">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
8.  <span data-ttu-id="7414a-179">Na caixa **Operador** , selecione o operador que você deseja que o filtro use para comparar os valores nas caixas **Expressão** e **Valor** .</span><span class="sxs-lookup"><span data-stu-id="7414a-179">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="7414a-180">O operador escolhido determinará o número de valores que serão usados na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="7414a-180">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
9. <span data-ttu-id="7414a-181">Na caixa **Valor** , digite a expressão ou o valor em relação ao qual você deseja que o filtro avalie o valor em **Expressão**.</span><span class="sxs-lookup"><span data-stu-id="7414a-181">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="7414a-182">Para obter exemplos de equações de filtro, consulte [Exemplos de equações de filtro &#40;Construtor de Relatórios e SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7414a-182">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7414a-183">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7414a-183">See Also</span></span>  
 <span data-ttu-id="7414a-184">[Adicionar filtros de conjunto de dados, de região de dados e de grupo &#40;Construtor de Relatórios e SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="7414a-184">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="7414a-185">[Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7414a-185">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7414a-186">[Medidores &#40;Construtor de Relatórios e SSRS&#41;](gauges-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7414a-186">[Gauges &#40;Report Builder and SSRS&#41;](gauges-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7414a-187">[Lista &#40;Construtor de Relatórios e SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7414a-187">[Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="7414a-188">Gráficos &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7414a-188">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
