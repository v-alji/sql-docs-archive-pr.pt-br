---
title: Modificar o modo de exibição de resultados de rastreamento | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 860a80dc-bac0-4ef0-bf7f-7a9b430d7aa3
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 050c8f179742cf3cef6473b03f062390caf195f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570192"
---
# <a name="modify-the-trace-results-view"></a><span data-ttu-id="cbfe7-102">Modificar a exibição dos resultados de rastreamento</span><span class="sxs-lookup"><span data-stu-id="cbfe7-102">Modify the Trace Results View</span></span>
  <span data-ttu-id="cbfe7-103">Este tópico descreve como modificar a exibição dos resultados do rastreamento de uma sessão de Eventos Estendidos no [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] executando as tarefas a seguir.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-103">This topic describes how to modify the trace results view of an Extended Events session in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] by performing the following tasks.</span></span>  
  
1.  [<span data-ttu-id="cbfe7-104">Adicionar ou remover colunas</span><span class="sxs-lookup"><span data-stu-id="cbfe7-104">Add or Remove Columns</span></span>](#AddRemoveColumns)  
  
2.  [<span data-ttu-id="cbfe7-105">Criar, editar ou excluir colunas mescladas</span><span class="sxs-lookup"><span data-stu-id="cbfe7-105">Create, Edit, or Delete Merged Columns</span></span>](#ChangeColumns)  
  
3.  [<span data-ttu-id="cbfe7-106">Classificar os resultados</span><span class="sxs-lookup"><span data-stu-id="cbfe7-106">Sort the Results</span></span>](#SortResults)  
  
4.  [<span data-ttu-id="cbfe7-107">Agrupar os resultados</span><span class="sxs-lookup"><span data-stu-id="cbfe7-107">Group the Results</span></span>](#GroupResults)  
  
5.  [<span data-ttu-id="cbfe7-108">Agregar os resultados</span><span class="sxs-lookup"><span data-stu-id="cbfe7-108">Aggregate the Results</span></span>](#AggregateResults)  
  
6.  [<span data-ttu-id="cbfe7-109">Filtrar os resultados</span><span class="sxs-lookup"><span data-stu-id="cbfe7-109">Filter the Results</span></span>](#Filter)  
  
7.  [<span data-ttu-id="cbfe7-110">Pesquisar texto nas colunas</span><span class="sxs-lookup"><span data-stu-id="cbfe7-110">Search for Text in Columns</span></span>](#Search)  
  
8.  [<span data-ttu-id="cbfe7-111">Alterar as configurações de exibição</span><span class="sxs-lookup"><span data-stu-id="cbfe7-111">Change the Display Settings</span></span>](#ChangeDisplay)  
  
##  <a name="add-or-remove-columns"></a><a name="AddRemoveColumns"></a><span data-ttu-id="cbfe7-112">Adicionar ou remover colunas</span><span class="sxs-lookup"><span data-stu-id="cbfe7-112">Add or Remove Columns</span></span>  
  
1.  <span data-ttu-id="cbfe7-113">Abra um arquivo .XEL para exibir os resultados do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-113">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cbfe7-114">Você também pode clicar com o botão direito do mouse no nome da sessão e selecionar **observar dados dinâmicos**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-114">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="cbfe7-115">Na janela de resultados de rastreamento, clique com o botão direito no cabeçalho de coluna e selecione **Escolher Colunas**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-115">In the trace results window, right-click the column header, and then select **Choose Columns**.</span></span>  
  
3.  <span data-ttu-id="cbfe7-116">Na caixa de diálogo **Escolher Colunas** , na seção **Colunas disponíveis** , selecione os nomes de colunas que você quer adicionar e clique na seta para a direita.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-116">In the **Choose Columns** dialog box, in the **Available columns** section, select the column names you want to add, and then click the right arrow.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cbfe7-117">Por padrão, as colunas são organizadas por nome.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-117">By default, the columns are arranged by name.</span></span> <span data-ttu-id="cbfe7-118">Para exibir as colunas por evento, clique em **Organizar por evento**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-118">To display the columns by event, click **Arrange by event**.</span></span>  
  
     <span data-ttu-id="cbfe7-119">Para remover colunas, na seção **Colunas selecionadas** , selecione as colunas que você quer remover e clique na seta para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-119">To remove columns, in the **Selected columns** section, select the columns you want to remove, and click the left arrow.</span></span>  
  
4.  <span data-ttu-id="cbfe7-120">Na seção **Colunas selecionadas** , para alterar a exibição da ordem das colunas, clique em **Mover para cima** ou **Mover para baixo** respectivamente.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-120">In the **Selected columns** section, to change the column order display, click **Move Up** or **Move Down** respectively.</span></span> <span data-ttu-id="cbfe7-121">Você não pode mover várias linhas.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-121">You cannot move multiple rows.</span></span>  
  
5.  <span data-ttu-id="cbfe7-122">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-122">Click **OK**.</span></span>  
  
##  <a name="create-edit-or-delete-merged-columns"></a><a name="ChangeColumns"></a><span data-ttu-id="cbfe7-123">Criar, editar ou excluir colunas mescladas</span><span class="sxs-lookup"><span data-stu-id="cbfe7-123">Create, Edit, or Delete Merged Columns</span></span>  
  
#### <a name="to-create-merged-columns"></a><span data-ttu-id="cbfe7-124">Para criar colunas mescladas</span><span class="sxs-lookup"><span data-stu-id="cbfe7-124">To create merged columns</span></span>  
  
1.  <span data-ttu-id="cbfe7-125">Abra um arquivo .XEL para exibir os resultados do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-125">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cbfe7-126">Você também pode clicar com o botão direito do mouse no nome da sessão e selecionar **observar dados dinâmicos**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-126">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="cbfe7-127">Na janela de resultados de rastreamento, clique com o botão direito no cabeçalho de coluna e clique em **Escolher Colunas**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-127">In the trace results window, right-click the column header, and then click **Choose Columns**.</span></span>  
  
3.  <span data-ttu-id="cbfe7-128">Na caixa de diálogo **Escolher Colunas** , clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-128">In the **Choose Columns** dialog box, click **New**.</span></span>  
  
4.  <span data-ttu-id="cbfe7-129">Na caixa de diálogo **Nova Coluna Mesclada** , na caixa **Nome da coluna mesclada** , insira um nome para as colunas mescladas.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-129">In the **New Merged Column** dialog box, in the **Merged column name** box, enter a name for the merged columns.</span></span>  
  
5.  <span data-ttu-id="cbfe7-130">Na caixa **Colunas originais a serem mescladas** , selecione duas ou mais colunas para serem mescladas da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-130">In the **Original columns to merge** box, select two or more columns to merge from the drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cbfe7-131">Eventos Estendidos só dão suporte a mesclagem de até cinco colunas.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-131">Extended Events only supports merging up to five columns.</span></span>  
  
6.  <span data-ttu-id="cbfe7-132">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-132">Click **OK**.</span></span>  
  
#### <a name="to-edit-merged-columns"></a><span data-ttu-id="cbfe7-133">Para editar colunas mescladas</span><span class="sxs-lookup"><span data-stu-id="cbfe7-133">To edit merged columns</span></span>  
  
1.  <span data-ttu-id="cbfe7-134">Abra um arquivo .XEL para exibir os resultados do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-134">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cbfe7-135">Você também pode clicar com o botão direito do mouse no nome da sessão e selecionar **observar dados dinâmicos**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-135">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="cbfe7-136">Na janela de resultados de rastreamento, clique com o botão direito no cabeçalho de coluna e clique em **Escolher Colunas**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-136">In the trace results window, right-click the column header, and then click **Choose Columns**.</span></span>  
  
3.  <span data-ttu-id="cbfe7-137">Na caixa de diálogo **Escolher Colunas** , clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-137">In the **Choose Columns** dialog box, click **Edit**.</span></span>  
  
4.  <span data-ttu-id="cbfe7-138">Para alterar o nome da coluna mesclada, na caixa de diálogo **Nova Coluna Mesclada** , na caixa **Nome da coluna mesclada** , insira um nome.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-138">To change the name of the merged column, in the **New Merged Column** dialog box, in the **Merged column name** box, enter the new name.</span></span>  
  
     <span data-ttu-id="cbfe7-139">Para alterar as colunas que você quer mesclar, na caixa **Colunas originais a serem mescladas** , selecione as colunas que você quer mesclar na lista suspensa e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-139">To change the columns you want to merge, in the **Original columns to merge** box, select the columns you want to merge from the drop-down list, and then click **OK**.</span></span>  
  
#### <a name="to-delete-merged-columns"></a><span data-ttu-id="cbfe7-140">Para excluir as colunas mescladas</span><span class="sxs-lookup"><span data-stu-id="cbfe7-140">To delete merged columns</span></span>  
  
1.  <span data-ttu-id="cbfe7-141">Abra um arquivo .XEL para exibir os resultados do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-141">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cbfe7-142">Você também pode clicar com o botão direito do mouse no nome da sessão e selecionar **observar dados dinâmicos**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-142">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="cbfe7-143">Na janela de resultados de rastreamento, clique com o botão direito no cabeçalho de coluna e clique em **Escolher Colunas**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-143">In the trace results window, right-click the column header, and then click **Choose Columns**.</span></span>  
  
3.  <span data-ttu-id="cbfe7-144">Na caixa de diálogo **Escolher Colunas** , marque o nome da coluna mesclada que você quer excluir e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-144">In the **Choose Columns** dialog box, select the name of the merged column you want to delete, and then click **Delete**.</span></span>  
  
##  <a name="sort-the-results"></a><a name="SortResults"></a><span data-ttu-id="cbfe7-145">Classificar os resultados</span><span class="sxs-lookup"><span data-stu-id="cbfe7-145">Sort the Results</span></span>  
  
#### <a name="to-sort-the-results-in-ascending-or-descending-order"></a><span data-ttu-id="cbfe7-146">Para classificar os resultados em ordem crescente ou decrescente</span><span class="sxs-lookup"><span data-stu-id="cbfe7-146">To sort the results in ascending or descending order</span></span>  
  
-   <span data-ttu-id="cbfe7-147">Abra um arquivo .XEL para exibir os resultados do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-147">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cbfe7-148">Você também pode clicar com o botão direito do mouse no nome da sessão, selecionar **observar dados dinâmicos**e clicar no botão **parar feed de dados** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-148">You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the toolbar.</span></span>  
  
-   <span data-ttu-id="cbfe7-149">Na janela dos resultados de rastreamento, clique com o botão direito em um cabeçalho de coluna que você deseja classificar.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-149">In the trace results window, right-click the column heading you want to sort.</span></span> <span data-ttu-id="cbfe7-150">Clique em **Classificação Crescente** ou em **Classificação Decrescente** para classificar a coluna em ordem crescente ou decrescente respectivamente.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-150">Click **Sort Ascending** or **Sort Descending** to sort the column in ascending or descending order respectively.</span></span>  
  
     <span data-ttu-id="cbfe7-151">Se você agrupou colunas, classificar a coluna só classificará os dados dentro do grupo.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-151">If you have grouped columns, sorting the column will only sort data within the group.</span></span>  
  
##  <a name="group-results"></a><a name="GroupResults"></a><span data-ttu-id="cbfe7-152">Resultados do grupo</span><span class="sxs-lookup"><span data-stu-id="cbfe7-152">Group Results</span></span>  
  
#### <a name="to-group-the-results-by-a-single-column"></a><span data-ttu-id="cbfe7-153">Para agrupar os resultados por uma única coluna</span><span class="sxs-lookup"><span data-stu-id="cbfe7-153">To group the results by a single column</span></span>  
  
1.  <span data-ttu-id="cbfe7-154">Abra um arquivo .XEL para exibir os resultados do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-154">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cbfe7-155">Você também pode clicar com o botão direito no nome da sessão, **Observar Dados Dinâmicos**e em seguida clicar no botão **Parar Feed de Dados** na barra de ferramentas Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-155">You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the Extended Events toolbar.</span></span>  
  
2.  <span data-ttu-id="cbfe7-156">Na janela dos resultados de rastreamento, clique com o botão direito do mouse no cabeçalho da coluna que você quer agrupar e clique em **Agrupar por Esta Coluna**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-156">In the trace results window, right-click the column header you want to group, and then click **Group By This Column**.</span></span>  
  
#### <a name="to-group-the-results-by-multiple-columns"></a><span data-ttu-id="cbfe7-157">Para agrupar os resultados por várias colunas</span><span class="sxs-lookup"><span data-stu-id="cbfe7-157">To group the results by multiple columns</span></span>  
  
1.  <span data-ttu-id="cbfe7-158">Abra um arquivo .XEL para exibir os resultados do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-158">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cbfe7-159">Você também pode clicar com o botão direito do mouse no nome da sessão, selecionar **observar dados dinâmicos**e clicar no botão **parar feed de dados** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-159">You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the toolbar.</span></span>  
  
2.  <span data-ttu-id="cbfe7-160">Clique no botão **Agrupamento** na barra de ferramentas Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-160">Click the **Grouping** button on the Extended Events toolbar.</span></span>  
  
3.  <span data-ttu-id="cbfe7-161">Na caixa de diálogo **Agrupamento** , na caixa **Colunas disponíveis** , selecione as colunas que você deseja agrupar e clique na seta para a direita.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-161">In the **Grouping** dialog box, in the **Available columns** box, select the columns you want to group, and then click the right arrow.</span></span>  
  
     <span data-ttu-id="cbfe7-162">Para alterar a ordem de agrupamento, na seção **Colunas agrupadas em** , clique nas setas para cima ou para baixo.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-162">To change the grouping order, in the **Columns grouped on** section, click the up or down arrows.</span></span>  
  
     <span data-ttu-id="cbfe7-163">Para remover colunas do agrupamento, na caixa **Colunas agrupadas em** , selecione as colunas que você quer remover e clique na seta para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-163">To remove columns from the grouping, in the **Columns grouped on** box, select the columns you want to remove and then click the left arrow.</span></span>  
  
4.  <span data-ttu-id="cbfe7-164">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-164">Click **OK**.</span></span>  
  
##  <a name="aggregate-results"></a><a name="AggregateResults"></a><span data-ttu-id="cbfe7-165">Agregar resultados</span><span class="sxs-lookup"><span data-stu-id="cbfe7-165">Aggregate Results</span></span>  
 <span data-ttu-id="cbfe7-166">Eventos Estendidos dão suporte a cinco funções de agregação:</span><span class="sxs-lookup"><span data-stu-id="cbfe7-166">Extended Events supports five aggregation functions:</span></span>  
  
-   <span data-ttu-id="cbfe7-167">Somar</span><span class="sxs-lookup"><span data-stu-id="cbfe7-167">Sum</span></span>  
  
-   <span data-ttu-id="cbfe7-168">Mín</span><span class="sxs-lookup"><span data-stu-id="cbfe7-168">Min</span></span>  
  
-   <span data-ttu-id="cbfe7-169">Max</span><span class="sxs-lookup"><span data-stu-id="cbfe7-169">Max</span></span>  
  
-   <span data-ttu-id="cbfe7-170">Média</span><span class="sxs-lookup"><span data-stu-id="cbfe7-170">Average</span></span>  
  
-   <span data-ttu-id="cbfe7-171">Contagem</span><span class="sxs-lookup"><span data-stu-id="cbfe7-171">Count</span></span>  
  
 <span data-ttu-id="cbfe7-172">Sum, Min, Max e Average podem ser usados somente com as colunas numéricas disponíveis.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-172">Sum, Min,  Max, and Average can only be used with available numeric columns.</span></span> <span data-ttu-id="cbfe7-173">Count é o número de valores não nulos que existem para a coluna selecionada no grupo.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-173">Count is the number of non-null values that exist for the selected column in the group.</span></span>  
  
#### <a name="to-aggregate-results"></a><span data-ttu-id="cbfe7-174">Para agregar resultados</span><span class="sxs-lookup"><span data-stu-id="cbfe7-174">To aggregate results</span></span>  
  
1.  <span data-ttu-id="cbfe7-175">Abra um arquivo .XEL para exibir os resultados do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-175">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cbfe7-176">Você também pode clicar com o botão direito do mouse no nome da sessão, selecionar **observar dados dinâmicos**e clicar no botão **parar feed de dados** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-176">You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the toolbar.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cbfe7-177">A agregação é executada em um grupo; portanto, você deve agrupar os resultados antes de você executar a agregação.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-177">Aggregation is run against a group, so you must group the results before you can perform the aggregation.</span></span>  
  
2.  <span data-ttu-id="cbfe7-178">Na barra de ferramentas Eventos Estendidos, clique no botão **Agregação** .</span><span class="sxs-lookup"><span data-stu-id="cbfe7-178">On the Extended Events toolbar, click the **Aggregate** button.</span></span>  
  
     <span data-ttu-id="cbfe7-179">A caixa de diálogo **Agregação** aparece exibindo as colunas disponíveis para agregação.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-179">The **Aggregation** dialog box appears displaying the columns available for aggregation.</span></span>  
  
3.  <span data-ttu-id="cbfe7-180">Em **Tipo de Agregação**, selecione como você deseja agregar a coluna correspondente da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-180">Under **Aggregation Type**, select how you want to aggregate the corresponding column from the drop-down list.</span></span>  
  
4.  <span data-ttu-id="cbfe7-181">Na caixa **Classificar agregação por** , selecione a coluna pela qual deseja classificar na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-181">In the **Sort aggregation by** box, select the column you want to sort by from the drop-down list.</span></span>  
  
5.  <span data-ttu-id="cbfe7-182">Selecione a opção **Em ordem crescente** para classificar o resultado da agregação em ordem crescente.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-182">Select the **In ascending order** option to sort the aggregation result in ascending order.</span></span>  
  
6.  <span data-ttu-id="cbfe7-183">Selecione a opção **Em ordem decrescente** para classificar o resultado da agregação em ordem decrescente.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-183">Select the **In descending order** option to sort the aggregation result in descending order.</span></span>  
  
7.  <span data-ttu-id="cbfe7-184">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-184">Click **OK**.</span></span>  
  
##  <a name="filter-results"></a><a name="Filter"></a><span data-ttu-id="cbfe7-185">Filtrar resultados</span><span class="sxs-lookup"><span data-stu-id="cbfe7-185">Filter Results</span></span>  
 <span data-ttu-id="cbfe7-186">Você pode aplicar filtros para refinar os resultados do rastreamento que são exibidos na janela de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-186">You can apply filters to narrow down the trace results that are displayed in the trace window.</span></span> <span data-ttu-id="cbfe7-187">O filtro de exibição inclui um filtro de hora e um filtro avançado.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-187">The display filter includes a time filter and an advanced filter.</span></span> <span data-ttu-id="cbfe7-188">Use o filtro de hora para filtrar os resultados de rastreamento por carimbo de data/hora de evento e use o filtro avançado para construir condições de filtro usando os campos de eventos e ações.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-188">You use the time filter to filter the trace results by event timestamp, and you use the advanced filter to construct filter conditions using the event fields and actions.</span></span> <span data-ttu-id="cbfe7-189">Há uma relação AND lógica entre os filtros Hora e Avançado.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-189">There is an logical AND relationship between the Time and Advanced Filters.</span></span>  
  
#### <a name="to-create-a-filter"></a><span data-ttu-id="cbfe7-190">Para criar um filtro</span><span class="sxs-lookup"><span data-stu-id="cbfe7-190">To create a filter</span></span>  
  
1.  <span data-ttu-id="cbfe7-191">Abra um arquivo .XEL para exibir os resultados do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-191">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cbfe7-192">Você também pode clicar com o botão direito do mouse no nome da sessão e selecionar **observar dados dinâmicos**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-192">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="cbfe7-193">Na janela de resultados de rastreamento, selecione os resultados que você deseja filtrar e, na barra de ferramentas Eventos Estendidos, clique no botão **Filtros** .</span><span class="sxs-lookup"><span data-stu-id="cbfe7-193">In the trace results window, select the results you want to filter, and then on the Extended Events toolbar, click the **Filters** button.</span></span>  
  
3.  <span data-ttu-id="cbfe7-194">Na caixa de diálogo **Filtros** , selecione **Definir filtro de hora** para definir o filtro de hora arrastando o controle deslizante tranca para definir a linha de tempo.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-194">In the **Filters** dialog box, select **Set time filter** to set the time filter by dragging the slider bars to set the timeline.</span></span> <span data-ttu-id="cbfe7-195">Observe que, quando você move as barras de controle deslizante, a caixa de hora exibe o valor de tempo de acordo.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-195">Note that when you move the slider bars, the time box displays the time value accordingly.</span></span> <span data-ttu-id="cbfe7-196">Você também pode inserir a hora nas caixas de hora ou selecioná-la na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-196">You can also enter the time in the time boxes, or you select it from the drop-down list.</span></span> <span data-ttu-id="cbfe7-197">Observe que, quando você inserir a hora, o controle deslizante do tempo restante moverá de acordo.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-197">Note that when you enter the time, the left time slider will move accordingly.</span></span>  
  
4.  <span data-ttu-id="cbfe7-198">Na seção **filtros adicionais** , aplique os critérios de filtro e clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-198">In the **Additional Filters** section, apply your filter criteria, and then click **Apply**.</span></span> <span data-ttu-id="cbfe7-199">Quando acabar de criar o filtro, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-199">When your finished created the filter, click **OK**.</span></span>  
  
 <span data-ttu-id="cbfe7-200">Uma situação especial ocorre quando um campo de evento tem o mesmo nome de uma ação.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-200">A special situation is when an event field has the same name as an action.</span></span> <span data-ttu-id="cbfe7-201">Um exemplo disso seria session_id.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-201">An example of this would be session_id.</span></span> <span data-ttu-id="cbfe7-202">Há vários eventos que incluem um campo session_id e você também pode adicionar a ação session_id.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-202">There are several events that include a session_id field and you could also add the session_id action.</span></span> <span data-ttu-id="cbfe7-203">Ambas as informações são coletadas, mas a grade de exibição do profiler Eventos Estendidos usa a lógica a seguir.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-203">Both pieces of information are collected, but the Extended Events profiler display grid uses the following logic.</span></span>  
  
-   <span data-ttu-id="cbfe7-204">Somente uma cópia da coluna (session_id nesse caso) é mostrada na exibição de grade.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-204">Only one copy of the column (session_id in this case) is shown in the grid display.</span></span>  
  
-   <span data-ttu-id="cbfe7-205">Se houver campos e ação nos dados, o valor do campo será mostrado.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-205">If both fields and action exist in the data, the field value is shown.</span></span>  
  
-   <span data-ttu-id="cbfe7-206">Se apenas o campo ou a ação existir nos dados, o campo ou a ação será exibido.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-206">If only field or action is exists in the data, the field or action is displayed.</span></span>  
  
-   <span data-ttu-id="cbfe7-207">Se não houver nem o campo nem a ação, NULL será exibido.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-207">If neither action nor field exists, display NULL.</span></span>  
  
##  <a name="search-for-text-in-columns"></a><a name="Search"></a><span data-ttu-id="cbfe7-208">Pesquisar texto em colunas</span><span class="sxs-lookup"><span data-stu-id="cbfe7-208">Search for Text in Columns</span></span>  
  
1.  <span data-ttu-id="cbfe7-209">Abra um arquivo .XEL para exibir os resultados do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-209">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cbfe7-210">Você também pode clicar com o botão direito do mouse no nome da sessão e selecionar **observar dados dinâmicos**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-210">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="cbfe7-211">Na barra de ferramentas Eventos Estendidos, clique no botão **Localizar** .</span><span class="sxs-lookup"><span data-stu-id="cbfe7-211">On the Extended Events toolbar, click the **Find** button.</span></span>  
  
3.  <span data-ttu-id="cbfe7-212">Na caixa de diálogo **Localizar nos Eventos Estendidos** , na caixa **Localizar** , insira o texto que você quer procurar.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-212">In the **Find in Extended Events** dialog box, in the **Find what** box, enter the text you want to search for.</span></span>  
  
     <span data-ttu-id="cbfe7-213">Você pode selecionar uma das suas últimas 20 cadeias de caracteres pesquisadas na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-213">You can select one of your last 20 search strings from the drop-down list.</span></span>  
  
4.  <span data-ttu-id="cbfe7-214">Na caixa **Examinar** , selecione o local no qual procurar o texto especificado na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-214">In the **Look in** box, select the location in which to search for the specified text from the drop-down list.</span></span> <span data-ttu-id="cbfe7-215">Use as seguintes opções para procurar:</span><span class="sxs-lookup"><span data-stu-id="cbfe7-215">Use the following options for searching:</span></span>  
  
    -   <span data-ttu-id="cbfe7-216">**Colunas da tabela**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-216">**Table Columns**.</span></span> <span data-ttu-id="cbfe7-217">Use esta opção para procurar todas as colunas visíveis na janela de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-217">Use this option to search all visible columns in the trace window.</span></span>  
  
    -   <span data-ttu-id="cbfe7-218">**Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-218">**Details**.</span></span> <span data-ttu-id="cbfe7-219">Use esta opção para pesquisar todas as colunas (promovidas e não promovidas) na janela de rastreamento que foram selecionadas antes de abrir a caixa de diálogo **Localizar em eventos estendidos** .</span><span class="sxs-lookup"><span data-stu-id="cbfe7-219">Use this option to search all columns (promoted and non-promoted) in the trace window that were selected before opening the **Find in Extended Events** dialog box.</span></span>  
  
    -   <span data-ttu-id="cbfe7-220">**\<Event column name>**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-220">**\<Event column name>**.</span></span> <span data-ttu-id="cbfe7-221">Use esta opção para procurar uma coluna de evento específica na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-221">Use this option to search in a specific event column from the drop-down list.</span></span>  
  
5.  <span data-ttu-id="cbfe7-222">Use as opções a seguir para especificar como você quer definir a pesquisa:</span><span class="sxs-lookup"><span data-stu-id="cbfe7-222">Use the following options to specify how you want to define the search:</span></span>  
  
    1.  <span data-ttu-id="cbfe7-223">**Diferenciar maiúsculas de minúsculas**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-223">**Match case**.</span></span> <span data-ttu-id="cbfe7-224">Use esta opção para exibir os resultados da pesquisa para o texto que você inseriu na caixa **Localizar** que corresponde tanto ao conteúdo quanto ao caso.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-224">Use this option to display the search results for the text you entered in the **Find what** box that are matched both by content and by case.</span></span>  
  
    2.  <span data-ttu-id="cbfe7-225">**Coincidir palavra inteira**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-225">**Match whole word**.</span></span> <span data-ttu-id="cbfe7-226">Use esta opção para exibir somente os resultados da pesquisa para o texto que você inseriu que corresponde palavras completas.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-226">Use this option to display only the search results for the text you entered that match complete words.</span></span>  
  
    3.  <span data-ttu-id="cbfe7-227">**Pesquisar para cima**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-227">**Search up**.</span></span> <span data-ttu-id="cbfe7-228">Use esta opção para pesquisar do local do seu cursor para o início dos resultados.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-228">Use this option to search from your cursor location to the beginning of the results.</span></span>  
  
    4.  <span data-ttu-id="cbfe7-229">**Use**o.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-229">**Use**.</span></span> <span data-ttu-id="cbfe7-230">Use esta opção para interpretar os caracteres especiais e as expressões regulares que você inseriu na caixa **Localizar** .</span><span class="sxs-lookup"><span data-stu-id="cbfe7-230">Use this option to interpret the special characters and the regular expressions you entered in the **Find what** box.</span></span> <span data-ttu-id="cbfe7-231">Caracteres especiais incluem os caracteres curinga (\*) e (?) para representar um ou mais caracteres.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-231">Special characters include the wildcard characters (\*) and (?) to represent one or more characters.</span></span> <span data-ttu-id="cbfe7-232">Expressões regulares são notações especiais usadas para definir padrões de texto de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-232">Regular expressions are special notations used to define patterns of search text.</span></span>  
  
6.  <span data-ttu-id="cbfe7-233">Clique em **Localizar Próximo** para procurar o próximo texto que você inseriu na caixa **Localizar** .</span><span class="sxs-lookup"><span data-stu-id="cbfe7-233">Click **Find Next** to search for the next text that you entered in the **Find what** box.</span></span>  
  
##  <a name="change-the-display-settings"></a><a name="ChangeDisplay"></a><span data-ttu-id="cbfe7-234">Alterar as configurações de exibição</span><span class="sxs-lookup"><span data-stu-id="cbfe7-234">Change the Display Settings</span></span>  
 <span data-ttu-id="cbfe7-235">Você pode salvar informações de coluna (ordem de coluna, coluna de mesclagem e largura de coluna) e informações de filtro de um resultado de rastreamento em um arquivo de configuração de exibição de Eventos Estendidos (arquivo .viewsetting).</span><span class="sxs-lookup"><span data-stu-id="cbfe7-235">You can save column information (column order, merge column, and column width) and filter information of a trace result into an Extended Events display setting file (.viewsetting file).</span></span> <span data-ttu-id="cbfe7-236">Após salvar o arquivo, você pode aplicá-lo aos seus resultados de rastreamento para alterar a exibição.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-236">After saving the file, you can apply it to your trace results to change the view.</span></span>  
  
#### <a name="to-change-the-display-settings"></a><span data-ttu-id="cbfe7-237">Para alterar as configurações de exibição</span><span class="sxs-lookup"><span data-stu-id="cbfe7-237">To change the display settings</span></span>  
  
1.  <span data-ttu-id="cbfe7-238">Abra um arquivo .XEL para exibir os resultados do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-238">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cbfe7-239">Você também pode clicar com o botão direito do mouse no nome da sessão e selecionar **observar dados dinâmicos**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-239">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="cbfe7-240">Na janela de resultados de rastreamento, na barra de ferramentas ou no menu Eventos Estendidos, selecione **Configurações de Vídeo**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-240">In the trace results window, on the Extended Events toolbar or menu, select **Display Settings**.</span></span>  
  
3.  <span data-ttu-id="cbfe7-241">Na lista suspensa, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="cbfe7-241">From the drop-down list, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="cbfe7-242">**Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-242">**Save as**.</span></span> <span data-ttu-id="cbfe7-243">Salve as colunas e informações de filtro de um resultado de rastreamento em um arquivo .viewsetting.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-243">Save the columns and filter information of a trace result to a .viewsetting file.</span></span>  
  
    -   <span data-ttu-id="cbfe7-244">**Abra**o.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-244">**Open**.</span></span> <span data-ttu-id="cbfe7-245">Abra um arquivo .viewsetting existente.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-245">Open an existing .viewsetting file.</span></span>  
  
    -   <span data-ttu-id="cbfe7-246">**Abra recente**.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-246">**Open recent**.</span></span> <span data-ttu-id="cbfe7-247">Abra um arquivo .viewsetting salvo recentemente.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-247">Open a recently saved .viewsetting file.</span></span>  
  
  
