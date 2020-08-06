---
title: Exibir os mesmos dados em uma matriz e um gráfico (Construtor de Relatórios) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 1262f283-9fc2-4bc1-9c79-457f7642abc7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7746ce1f06d4dcc67c51ddc40714f19a3ff83d51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683424"
---
# <a name="display-the-same-data-on-a-matrix-and-a-chart-report-builder"></a><span data-ttu-id="429a3-102">Exibir os mesmos dados em uma matriz e um gráfico (Construtor de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="429a3-102">Display the Same Data on a Matrix and a Chart (Report Builder)</span></span>
  <span data-ttu-id="429a3-103">Quando quiser mostrar os mesmos dados em uma matriz e em um gráfico, defina propriedades em ambas as regiões de dados para especificar o mesmo conjunto de dados, além das mesmas expressões para filtros, grupos, classificações e dados.</span><span class="sxs-lookup"><span data-stu-id="429a3-103">When you want to show the same data in a matrix and a chart, you must set properties on both data regions to specify the same dataset, and also the same expressions for filters, groups, sorts, and data.</span></span>  
  
 <span data-ttu-id="429a3-104">Como as regiões de dados terão o mesmo ancestral de dados (o conjunto de dados de relatório), você pode adicionar um botão de classificação interativo à matriz que, quando clicado, altera a ordem de classificação tanto da matriz quanto do gráfico.</span><span class="sxs-lookup"><span data-stu-id="429a3-104">Because both data regions will have the same ancestor for data (the report dataset), you can add an interactive sort button to the matrix that, when the user clicks it, changes the sort order for both the matrix and the chart.</span></span> <span data-ttu-id="429a3-105">Para obter mais informações, consulte [Adicionar classificação interativa a uma tabela ou matriz &#40;Construtor de Relatórios e SSRS&#41;](add-interactive-sort-to-a-table-or-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="429a3-105">For more information, see [Add Interactive Sort to a Table or Matrix &#40;Report Builder and SSRS&#41;](add-interactive-sort-to-a-table-or-matrix-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="429a3-106">Para usar os valores do grupo de colunas da matriz como legenda do gráfico, você deve especificar as cores dos dados da série no gráfico e usar as mesmas cores como cores de preenchimento no plano de fundo das caixas de texto da célula da matriz que exibe os valores do grupo.</span><span class="sxs-lookup"><span data-stu-id="429a3-106">To use the matrix column group values as a legend for the chart, you must specify the colors for the series data on the chart, and then use the same colors as the fill colors for the background of the text boxes in the matrix cell that displays the group values.</span></span> <span data-ttu-id="429a3-107">Para obter mais informações, consulte [Especificar cores consistentes em gráficos com várias formas &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="429a3-107">For more information, see [Specify Consistent Colors across Multiple Shape Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="429a3-108">Em tempo de execução, o relatório pode ficar desorganizado caso haja muitos valores para as definições de grupo.</span><span class="sxs-lookup"><span data-stu-id="429a3-108">At run-time, your report may appear cluttered if there are too many group values for your group definitions.</span></span> <span data-ttu-id="429a3-109">Você talvez precise filtrar valores, combinar grupos ou ajustar o limite do gráfico combinar grupos.</span><span class="sxs-lookup"><span data-stu-id="429a3-109">You might need to filter values, combine groups, or adjust the threshold for the chart to combine groups for you.</span></span> <span data-ttu-id="429a3-110">Para obter mais informações, consulte [Vinculando várias regiões de dados ao mesmo conjunto de dados &#40;Construtor de Relatórios e SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="429a3-110">For more information, see [Linking Multiple Data Regions to the Same Dataset &#40;Report Builder and SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md)</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-matrix-and-chart-to-display-the-same-data"></a><span data-ttu-id="429a3-111">Para adicionar uma matriz e um gráfico e exibir os mesmos dados</span><span class="sxs-lookup"><span data-stu-id="429a3-111">To add a matrix and chart to display the same data</span></span>  
  
1.  <span data-ttu-id="429a3-112">Abra um relatório no modo Design.</span><span class="sxs-lookup"><span data-stu-id="429a3-112">Open a report in design view.</span></span>  
  
2.  <span data-ttu-id="429a3-113">Na guia **Inserir** , no grupo **Regiões de Dados** , clique em **Matriz**e, em seguida, clique no corpo do relatório ou em um retângulo no corpo do relatório.</span><span class="sxs-lookup"><span data-stu-id="429a3-113">From the **Insert** tab, in the **Data Regions** group, click **Matrix**, and then click the report body or in a rectangle in the report body.</span></span> <span data-ttu-id="429a3-114">Uma matriz será adicionada ao relatório.</span><span class="sxs-lookup"><span data-stu-id="429a3-114">A matrix is added to the report.</span></span>  
  
3.  <span data-ttu-id="429a3-115">Na guia **Inserir** , no grupo **Regiões de Dados** , clique em **Gráfico**e, em seguida, selecione o tipo de gráfico.</span><span class="sxs-lookup"><span data-stu-id="429a3-115">From the **Insert** tab, in the **Data Regions** group, click **Chart**, and then select the chart type.</span></span> <span data-ttu-id="429a3-116">Um gráfico será adicionado ao relatório.</span><span class="sxs-lookup"><span data-stu-id="429a3-116">A chart is added to the report.</span></span>  
  
4.  <span data-ttu-id="429a3-117">(Opcional) Na guia **Inserir** , no grupo **Itens de Relatório** , clique em **Retângulo**e clique no relatório.</span><span class="sxs-lookup"><span data-stu-id="429a3-117">(Optional) From the **Insert** tab, in the **Report Items** group, click **Rectangle**, and then click the report.</span></span> <span data-ttu-id="429a3-118">Um retângulo será adicionado ao relatório.</span><span class="sxs-lookup"><span data-stu-id="429a3-118">A rectangle is added to the report.</span></span> <span data-ttu-id="429a3-119">Arraste a matriz e o gráfico das etapas 2 e 3 para o retângulo.</span><span class="sxs-lookup"><span data-stu-id="429a3-119">Drag the matrix and chart from steps 2 and 3 into the rectangle.</span></span>  
  
     <span data-ttu-id="429a3-120">Ao colocar várias regiões de dados no contêiner do retângulo, você ajuda a controlar como a matriz e o gráfico serão renderizados quando você exibir o relatório.</span><span class="sxs-lookup"><span data-stu-id="429a3-120">By placing multiple data regions in the rectangle container, you help control how the matrix and chart render when you view the report.</span></span>  
  
     <span data-ttu-id="429a3-121">Nas próximas etapas, você escolherá o mesmo campo do conjunto de dados que será exibido na matriz e no gráfico.</span><span class="sxs-lookup"><span data-stu-id="429a3-121">In the next few steps, you will choose the same dataset field to display in the matrix and to display in the chart.</span></span>  
  
5.  <span data-ttu-id="429a3-122">No painel de dados do relatório, arraste um campo de conjunto de dados numérico para a célula Dados na matriz.</span><span class="sxs-lookup"><span data-stu-id="429a3-122">From the Report Data pane, drag a numeric dataset field to the Data cell in the matrix.</span></span>  
  
     <span data-ttu-id="429a3-123">Por padrão, a função de agregação Sum é usada para calcular o valor do grupo.</span><span class="sxs-lookup"><span data-stu-id="429a3-123">By default, the aggregate function Sum is used for calculating the group value.</span></span> <span data-ttu-id="429a3-124">Caso altere a função de agregação na matriz, você deve alterá-la no gráfico também.</span><span class="sxs-lookup"><span data-stu-id="429a3-124">If you change the aggregate function in the matrix, you must change in the chart also.</span></span>  
  
6.  <span data-ttu-id="429a3-125">Na matriz, clique com o botão direito do mouse na célula com dados, clique em **Propriedades da Caixa de Texto**e em **Número**.</span><span class="sxs-lookup"><span data-stu-id="429a3-125">In the matrix, right-click the cell with data, click **Text Box Properties**, and then click **Number**.</span></span> <span data-ttu-id="429a3-126">Escolha um formato apropriado ao valor do campo de conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="429a3-126">Choose an appropriate format for the dataset field value.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="429a3-127">Arraste o mesmo campo do conjunto de dados que você escolheu na etapa 3 para a área **Valores** no gráfico.</span><span class="sxs-lookup"><span data-stu-id="429a3-127">Drag the same dataset field you chose in step 3 to the **Values** area on the chart.</span></span>  
  
9. <span data-ttu-id="429a3-128">No gráfico, clique com o botão direito do mouse no eixo Y, clique em **Propriedades do Eixo**e em **Número**.</span><span class="sxs-lookup"><span data-stu-id="429a3-128">In the chart, right-click the Y axis, click **Axis Properties**, and then click **Number**.</span></span> <span data-ttu-id="429a3-129">Escolha o mesmo formato dos dados escolhidos na etapa 4.</span><span class="sxs-lookup"><span data-stu-id="429a3-129">Choose the same format for the data that you chose in step 4.</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="429a3-130">Nas próximas etapas, você definirá o grupo de linhas da matriz e o grupo de séries do gráfico usando a mesma expressão, além de definir a ordem de classificação do grupo de séries do gráfico.</span><span class="sxs-lookup"><span data-stu-id="429a3-130">In the next few steps, you will set the matrix row group and the chart series group to the same expression, and also set the sort order for the chart series group.</span></span>  
  
11. <span data-ttu-id="429a3-131">No painel de dados do relatório, arraste o campo de conjunto de dados que você deseja agrupar por linhas de matriz para o painel Grupos de Linhas.</span><span class="sxs-lookup"><span data-stu-id="429a3-131">From the Report Data pane, drag the dataset field that you want to group by for matrix rows to the Row Groups pane.</span></span>  
  
     <span data-ttu-id="429a3-132">Por padrão, o grupo de linhas da matriz adiciona uma expressão de classificação igual à expressão de grupo.</span><span class="sxs-lookup"><span data-stu-id="429a3-132">By default, the matrix row group adds a sort expression that is the same as the group expression.</span></span>  
  
12. <span data-ttu-id="429a3-133">Arraste o mesmo campo de conjunto de dados usado na etapa 9 para a área **Grupos de Séries** do gráfico.</span><span class="sxs-lookup"><span data-stu-id="429a3-133">Drag the same dataset field that you used in step 9 to the **Series Groups** area for the chart.</span></span>  
  
13. <span data-ttu-id="429a3-134">Clique com o botão direito do mouse na área **Grupos de Séries** e clique em **Propriedades do Grupo de Séries**.</span><span class="sxs-lookup"><span data-stu-id="429a3-134">Right-click the group in the **Series Groups** area, and then click **Series Group Properties**.</span></span>  
  
14. <span data-ttu-id="429a3-135">Clique em **Classificar**.</span><span class="sxs-lookup"><span data-stu-id="429a3-135">Click **Sorting**.</span></span>  
  
15. <span data-ttu-id="429a3-136">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="429a3-136">Click **Add**.</span></span> <span data-ttu-id="429a3-137">Uma nova linha é exibida na grade das expressões de classificação.</span><span class="sxs-lookup"><span data-stu-id="429a3-137">A new row appears in the sort expressions grid.</span></span>  
  
16. <span data-ttu-id="429a3-138">Em **Classificar por**, na lista suspensa, escolha o mesmo campo de conjunto de dados escolhido para agrupamento na etapa 9.</span><span class="sxs-lookup"><span data-stu-id="429a3-138">In **Sort by**, from the drop-down list, choose the dataset field that you chose to group by in step 9.</span></span>  
  
17. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="429a3-139">Nas próximas etapas, você definirá o grupo de colunas da matriz e o grupo de categorias do gráfico usando a mesma expressão, além de definir a ordem de classificação do grupo de categorias do gráfico.</span><span class="sxs-lookup"><span data-stu-id="429a3-139">In the next few steps, you will set the matrix column group and the chart category group to the same expression, and also set the sort order for the chart category group.</span></span>  
  
18. <span data-ttu-id="429a3-140">No painel de dados do relatório, arraste o campo de conjunto de dados que você deseja agrupar por colunas de matriz para o painel Grupos de Colunas.</span><span class="sxs-lookup"><span data-stu-id="429a3-140">From the Report Data pane, drag the dataset field that you want to group by for matrix columns to the Column Groups pane.</span></span>  
  
     <span data-ttu-id="429a3-141">Por padrão, o grupo de colunas da matriz adiciona uma expressão de classificação igual à expressão de grupo.</span><span class="sxs-lookup"><span data-stu-id="429a3-141">By default, the matrix column group adds a sort expression that is the same as the group expression.</span></span>  
  
19. <span data-ttu-id="429a3-142">Arraste o mesmo campo de conjunto de dados usado na etapa 16 para a área **Grupos de Categorias** do gráfico.</span><span class="sxs-lookup"><span data-stu-id="429a3-142">Drag the same dataset field that you used in step 16 to the **Category Groups** area for the chart.</span></span>  
  
20. <span data-ttu-id="429a3-143">Clique com o botão direito do mouse no grupo na área **Grupos de Categorias** e clique em **Propriedades de Grupo de Categorias**.</span><span class="sxs-lookup"><span data-stu-id="429a3-143">Right-click the group in the **CategoryGroups** area, and then click **Category Group Properties**.</span></span>  
  
21. <span data-ttu-id="429a3-144">Clique em **Classificar**.</span><span class="sxs-lookup"><span data-stu-id="429a3-144">Click **Sorting**.</span></span>  
  
22. <span data-ttu-id="429a3-145">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="429a3-145">Click **Add**.</span></span> <span data-ttu-id="429a3-146">Uma nova linha é exibida na grade das expressões de classificação.</span><span class="sxs-lookup"><span data-stu-id="429a3-146">A new row appears in the sort expressions grid.</span></span>  
  
23. <span data-ttu-id="429a3-147">Em **Classificar por**, na lista suspensa, escolha o mesmo campo de conjunto de dados escolhido para agrupamento na etapa 16.</span><span class="sxs-lookup"><span data-stu-id="429a3-147">In **Sort by**, from the drop-down list, choose the dataset field that you chose to group by in step 16.</span></span>  
  
24. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
25. <span data-ttu-id="429a3-148">Visualize o resultado.</span><span class="sxs-lookup"><span data-stu-id="429a3-148">Preview the result.</span></span> <span data-ttu-id="429a3-149">Os grupos de linhas e de colunas da matriz exibem os mesmos dados dos grupos de séries e de categorias do gráfico.</span><span class="sxs-lookup"><span data-stu-id="429a3-149">The matrix row and column groups display the same data as the chart series and category groups.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="429a3-150">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="429a3-150">See Also</span></span>  
 <span data-ttu-id="429a3-151">[Vinculando várias regiões de dados ao mesmo conjunto de dados &#40;Construtor de Relatórios e SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="429a3-151">[Linking Multiple Data Regions to the Same Dataset &#40;Report Builder and SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="429a3-152">[Adicionar filtros de conjunto de dados, de região de dados e de grupo &#40;Construtor de Relatórios e SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="429a3-152">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="429a3-153">[Lista &#40;Construtor de Relatórios e SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="429a3-153">[Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="429a3-154">Gráficos &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="429a3-154">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
