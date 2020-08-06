---
title: Adicionar ou excluir um grupo em uma região de dados (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4de53c3c-c6fc-49ce-b692-3609fc0b3ec5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c355ca87db578d47181935e1ca6bc48e75bf8b8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682139"
---
# <a name="add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs"></a><span data-ttu-id="008f0-102">Adicionar ou excluir um grupo em uma região de dados (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="008f0-102">Add or Delete a Group in a Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="008f0-103">Adicione um grupo a uma região de dados quando quiser organizar os dados por um valor ou conjunto de expressões específico para exibição e cálculos.</span><span class="sxs-lookup"><span data-stu-id="008f0-103">Add a group to a data region when you want to organize data by a specific value or set of expressions, for display and calculations.</span></span> <span data-ttu-id="008f0-104">Um grupo tem um nome e uma expressão que identificam quais dados de um conjunto de dados pertencem ao grupo.</span><span class="sxs-lookup"><span data-stu-id="008f0-104">A group has a name and an expression that identifies which data from a dataset belongs to the group.</span></span> <span data-ttu-id="008f0-105">Para obter mais informações sobre grupos, consulte [Noções básicas sobre grupos &#40;Construtor de Relatórios e SSRS&#41;](understanding-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="008f0-105">For more information about groups, see [Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="008f0-106">Em uma região de dados tablix, clique na tabela, matriz ou lista para exibir o painel Agrupamento.</span><span class="sxs-lookup"><span data-stu-id="008f0-106">In a tablix data region, click in the table, matrix, or list to display the Grouping pane.</span></span> <span data-ttu-id="008f0-107">Arraste campos do conjunto de dados para os painéis Grupo de Linhas e Grupo de Colunas para criar grupos pai ou filho.</span><span class="sxs-lookup"><span data-stu-id="008f0-107">Drag dataset fields to the Row Group and Column Group pane to create parent or child groups.</span></span> <span data-ttu-id="008f0-108">Clique com o botão direito do mouse em um grupo existente para adicionar um grupo adjacente.</span><span class="sxs-lookup"><span data-stu-id="008f0-108">Right-click an existing group to add an adjacent group.</span></span> <span data-ttu-id="008f0-109">Por definição, o grupo de detalhes é o grupo interno e pode ser adicionado somente como um grupo filho.</span><span class="sxs-lookup"><span data-stu-id="008f0-109">By definition, the details group is the innermost group and can only be added as a child group.</span></span> <span data-ttu-id="008f0-110">Clique com o botão direito do mouse em um grupo existente para excluí-lo.</span><span class="sxs-lookup"><span data-stu-id="008f0-110">Right-click an existing group to delete it.</span></span> <span data-ttu-id="008f0-111">Linhas e colunas nas quais exibir valores de grupos são adicionadas automaticamente para você.</span><span class="sxs-lookup"><span data-stu-id="008f0-111">Rows and columns on which to display group values are automatically added for you.</span></span> <span data-ttu-id="008f0-112">Para obter mais informações, consulte [Tabelas, matrizes e listas &#40;Construtor de Relatórios e SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="008f0-112">For more information, see [Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="008f0-113">Em uma região de dados do Gráfico, clique no gráfico para exibir as áreas para arrastar e soltar.</span><span class="sxs-lookup"><span data-stu-id="008f0-113">In a Chart data region, click in the chart to display the drop-zones.</span></span> <span data-ttu-id="008f0-114">Crie grupos arrastando campos do conjunto de dados para as áreas para arrastar e soltar categorias e séries.</span><span class="sxs-lookup"><span data-stu-id="008f0-114">Create groups by dragging dataset fields to the category and series drop zones.</span></span> <span data-ttu-id="008f0-115">Para adicionar grupos aninhados, adicione vários campos à área para arrastar e soltar.</span><span class="sxs-lookup"><span data-stu-id="008f0-115">To add nested groups, add multiple fields to the drop-zone.</span></span>  
  
 <span data-ttu-id="008f0-116">Por padrão, os grupos não são definidos em um medidor.</span><span class="sxs-lookup"><span data-stu-id="008f0-116">Groups are not defined in a gauge by default.</span></span> <span data-ttu-id="008f0-117">O comportamento padrão do medidor é agregar todos os valores no campo especificado em um valor que é exibido no medidor.</span><span class="sxs-lookup"><span data-stu-id="008f0-117">The default behavior for the gauge is to aggregate all values in the specified field into one value that is displayed on the gauge.</span></span> <span data-ttu-id="008f0-118">Para obter mais informações, consulte [Medidores &#40;Construtor de Relatórios e SSRS&#41;](gauges-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="008f0-118">For more information, see [Gauges &#40;Report Builder and SSRS&#41;](gauges-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-parent-or-child-row-or-column-group-to-a-tablix-data-region"></a><span data-ttu-id="008f0-119">Para adicionar uma linha pai ou filho ou grupo de colunas a uma região de dados tablix</span><span class="sxs-lookup"><span data-stu-id="008f0-119">To add a parent or child row or column group to a tablix data region</span></span>  
  
1.  <span data-ttu-id="008f0-120">Arraste um campo do painel **Dados do Relatório** para o painel **Grupos de Linhas** ou para o painel **Grupos de Colunas** .</span><span class="sxs-lookup"><span data-stu-id="008f0-120">Drag a field from the **Report Data** pane to the **Row Groups** pane or the **Column Groups** pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="008f0-121">Se o painel Agrupamento não estiver visível, na guia Exibir, clique em **Agrupamento**.</span><span class="sxs-lookup"><span data-stu-id="008f0-121">If you do not see the Grouping pane, on the View tab, click **Grouping**.</span></span>  
  
2.  <span data-ttu-id="008f0-122">Solte o campo acima ou abaixo da hierarquia do grupo usando a barra de guias para colocar o grupo como um grupo pai ou filho em um grupo existente.</span><span class="sxs-lookup"><span data-stu-id="008f0-122">Drop the field above or below the group hierarchy using the guide bar to place the group as a parent group or a child group to an existing group.</span></span>  
  
     <span data-ttu-id="008f0-123">O grupo é adicionado com um nome padrão, expressão de grupo e expressão de classificação que é baseada no nome do campo.</span><span class="sxs-lookup"><span data-stu-id="008f0-123">The group is added with a default name, group expression, and sort expression that is based on the field name.</span></span>  
  
### <a name="to-add-an-adjacent-row-or-column-group-to-a-tablix-data-region"></a><span data-ttu-id="008f0-124">Para adicionar uma linha adjacente ou grupo de colunas a uma região de dados tablix</span><span class="sxs-lookup"><span data-stu-id="008f0-124">To add an adjacent row or column group to a tablix data region</span></span>  
  
1.  <span data-ttu-id="008f0-125">No painel Agrupamento, clique com o botão direito do mouse em um grupo que seja do mesmo nível que o grupo que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="008f0-125">In the Grouping pane, right-click a group that is a peer to the group that you want to add.</span></span> <span data-ttu-id="008f0-126">Clique em **Adicionar Grupo**e em **Adjacente Antes** ou **Adjacente Após** para especificar onde adicionar o grupo.</span><span class="sxs-lookup"><span data-stu-id="008f0-126">Click **Add Group**, and then click **Adjacent Before** or **Adjacent After** to specify where to add the group.</span></span> <span data-ttu-id="008f0-127">A caixa de diálogo **Grupo Tablix** é aberta.</span><span class="sxs-lookup"><span data-stu-id="008f0-127">The **Tablix Group** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="008f0-128">Em **Nome**, digite um nome para o grupo.</span><span class="sxs-lookup"><span data-stu-id="008f0-128">In **Name**, type a name for the group.</span></span>  
  
3.  <span data-ttu-id="008f0-129">Em **Expressão de grupo**, digite uma expressão ou clique no botão de expressão (**fx**) para criar uma expressão.</span><span class="sxs-lookup"><span data-stu-id="008f0-129">In **Group expression**, type an expression or click the expression button (**fx**) to create an expression.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="008f0-130">Um novo grupo é adicionado ao painel Agrupamento e uma linha ou coluna na qual exibir valores de grupo é adicionada à região de dados tablix na superfície de design.</span><span class="sxs-lookup"><span data-stu-id="008f0-130">A new group is added to the Grouping pane and a row or column on which to display group values is added to the tablix data region on the design surface.</span></span>  
  
### <a name="to-add-a-details-group-to-a-tablix-data-region"></a><span data-ttu-id="008f0-131">Para adicionar um grupo de detalhes a uma região de dados tablix</span><span class="sxs-lookup"><span data-stu-id="008f0-131">To add a details group to a tablix data region</span></span>  
  
1.  <span data-ttu-id="008f0-132">No painel Agrupamento, clique com o botão direito do mouse no grupo filho mais interno, mas não no grupo **Detalhes** .</span><span class="sxs-lookup"><span data-stu-id="008f0-132">In the Grouping pane, right-click a group that is the innermost child group, but not the **Details** group.</span></span> <span data-ttu-id="008f0-133">Clique em **Adicionar Grupo**e em **Grupo Filho**.</span><span class="sxs-lookup"><span data-stu-id="008f0-133">Click **Add Group**, and then click **Child Group**.</span></span> <span data-ttu-id="008f0-134">A caixa de diálogo **Grupo Tablix** é aberta.</span><span class="sxs-lookup"><span data-stu-id="008f0-134">The **Tablix Group** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="008f0-135">Em **Expressão de Grupo**, deixe a expressão em branco.</span><span class="sxs-lookup"><span data-stu-id="008f0-135">In **Group expression**, leave the expression blank.</span></span> <span data-ttu-id="008f0-136">Um grupo de detalhes não tem nenhuma expressão.</span><span class="sxs-lookup"><span data-stu-id="008f0-136">A details group has no expression.</span></span>  
  
3.  <span data-ttu-id="008f0-137">Selecione **Mostrar dados de detalhes**.</span><span class="sxs-lookup"><span data-stu-id="008f0-137">Select **Show detail data**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="008f0-138">Um novo grupo de detalhes é adicionado como um grupo filho ao painel Agrupamento e o identificador da linha do grupo selecionado na etapa 1 exibe o ícone do grupo de detalhes.</span><span class="sxs-lookup"><span data-stu-id="008f0-138">A new details group is added as a child group in the Grouping pane, and the row handle for the group you selected in step 1 displays the details group icon.</span></span> <span data-ttu-id="008f0-139">Para obter mais informações sobre identificadores, consulte [Células, linhas e colunas da região de dados Tablix &#40;Construtor de Relatórios&#41; e SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="008f0-139">For more information about handles, see [Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-edit-a-row-or-column-group-in-a-tablix-data-region"></a><span data-ttu-id="008f0-140">Para editar uma linha ou um grupo de colunas em uma região de dados tablix</span><span class="sxs-lookup"><span data-stu-id="008f0-140">To edit a row or column group in a tablix data region</span></span>  
  
1.  <span data-ttu-id="008f0-141">Na superfície de design de relatório, clique em qualquer lugar na região de dados tablix para selecioná-la.</span><span class="sxs-lookup"><span data-stu-id="008f0-141">On the report design surface, click anywhere in the tablix data region to select it.</span></span> <span data-ttu-id="008f0-142">O painel Agrupamento exibe os grupos de linhas e colunas.</span><span class="sxs-lookup"><span data-stu-id="008f0-142">The Grouping pane displays the row and column groups.</span></span>  
  
2.  <span data-ttu-id="008f0-143">Clique com o botão direito do mouse no grupo e clique em **Propriedades do Grupo**.</span><span class="sxs-lookup"><span data-stu-id="008f0-143">Right-click the group, and then click **Group Properties**.</span></span>  
  
3.  <span data-ttu-id="008f0-144">Em **Nome**, digite o nome do grupo.</span><span class="sxs-lookup"><span data-stu-id="008f0-144">In **Name**, type the name of the group.</span></span>  
  
4.  <span data-ttu-id="008f0-145">Em **Expressões de grupo**, digite ou selecione uma expressão simples ou clique no botão Expressão (**fx**) para criar uma expressão de grupo.</span><span class="sxs-lookup"><span data-stu-id="008f0-145">In **Group expressions**, type or select a simple expression, or click the Expression (**fx**) button to create a group expression.</span></span>  
  
5.  <span data-ttu-id="008f0-146">Clique em **Adicionar** para criar expressões adicionais.</span><span class="sxs-lookup"><span data-stu-id="008f0-146">Click **Add** to create additional expressions.</span></span> <span data-ttu-id="008f0-147">Todas as expressões especificadas são combinadas usando um AND lógico para especificar dados para esse grupo.</span><span class="sxs-lookup"><span data-stu-id="008f0-147">All expressions you specify are combined using a logical AND to specify data for this group.</span></span>  
  
6.  <span data-ttu-id="008f0-148">(Opcional) Clique em **Quebras de Página** para definir opções de quebra de página.</span><span class="sxs-lookup"><span data-stu-id="008f0-148">(Optional) Click **Page Breaks** to set page break options.</span></span>  
  
7.  <span data-ttu-id="008f0-149">(Opcional) Clique em **Classificação** para selecionar ou digitar expressões que especificam a ordem de classificação dos valores no grupo.</span><span class="sxs-lookup"><span data-stu-id="008f0-149">(Optional) Click **Sorting** to select or type expressions that specify the sort order for values in the group.</span></span>  
  
8.  <span data-ttu-id="008f0-150">(Opcional) Clique em **Visibilidade** para selecionar as opções de visibilidade do item.</span><span class="sxs-lookup"><span data-stu-id="008f0-150">(Optional) Click **Visibility** to select the visibility options for the item.</span></span>  
  
9. <span data-ttu-id="008f0-151">(Opcional) Clique em **Filtros** para definir filtros para esse grupo.</span><span class="sxs-lookup"><span data-stu-id="008f0-151">(Optional) Click **Filters** to set filters for this group.</span></span>  
  
10. <span data-ttu-id="008f0-152">(Opcional) Clique em **Variáveis** para definir variáveis com escopo para esse grupo e acessíveis de qualquer grupo filho.</span><span class="sxs-lookup"><span data-stu-id="008f0-152">(Optional) Click **Variables** to define variables scoped to this group and accessible from any child groups.</span></span>  
  
11. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-group-from-a-tablix-data-region"></a><span data-ttu-id="008f0-153">Para excluir um grupo de uma região de dados tablix</span><span class="sxs-lookup"><span data-stu-id="008f0-153">To delete a group from a tablix data region</span></span>  
  
1.  <span data-ttu-id="008f0-154">No painel Agrupamento, clique com o botão direito do mouse no grupo e clique em **Excluir Grupo**.</span><span class="sxs-lookup"><span data-stu-id="008f0-154">In the Grouping pane, right-click the group, and then click **Delete Group**.</span></span>  
  
2.  <span data-ttu-id="008f0-155">Na caixa de diálogo **Excluir Grupo** , selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="008f0-155">In the **Delete Group** dialog box, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="008f0-156">**Excluir grupo e linhas e colunas relacionadas** Escolha esta opção para excluir a definição do grupo e todas as linhas relacionadas que exibem dados do grupo.</span><span class="sxs-lookup"><span data-stu-id="008f0-156">**Delete group and related rows and columns** Choose this option to delete the group definition and all related rows that display group data.</span></span> <span data-ttu-id="008f0-157">Para obter o grupo de detalhes, se a mesma linha pertencer a detalhes e a dados do grupo, só as linhas de dados de detalhes serão excluídas.</span><span class="sxs-lookup"><span data-stu-id="008f0-157">For the details group, if the same row belongs to both detail and group data, only the detail data rows are deleted.</span></span>  
  
    -   <span data-ttu-id="008f0-158">**Excluir grupo somente** Escolha esta opção para manter a mesma estrutura da região de dados tablix e excluir só a definição do grupo.</span><span class="sxs-lookup"><span data-stu-id="008f0-158">**Delete group only** Choose this option to keep the structure of the tablix data region the same and delete only the group definition.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-details-group-from-a-tablix-data-region"></a><span data-ttu-id="008f0-159">Para excluir um grupo de detalhes de uma região de dados tablix</span><span class="sxs-lookup"><span data-stu-id="008f0-159">To delete a details group from a tablix data region</span></span>  
  
1.  <span data-ttu-id="008f0-160">No painel Agrupamento, clique com o botão direito do mouse no grupo de detalhes e clique em **Excluir Grupo**.</span><span class="sxs-lookup"><span data-stu-id="008f0-160">In the Grouping pane, right-click the details group, and then click **Delete Group**.</span></span>  
  
2.  <span data-ttu-id="008f0-161">Na caixa de diálogo **Excluir Grupo** , selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="008f0-161">In the **Delete Group** dialog box, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="008f0-162">**Excluir grupo e linhas e colunas relacionadas** Escolha esta opção para excluir a definição do grupo e todas as linhas relacionadas que exibem dados do grupo.</span><span class="sxs-lookup"><span data-stu-id="008f0-162">**Delete group and related rows and columns** Choose this option to delete the group definition and all related rows that display group data.</span></span> <span data-ttu-id="008f0-163">Para obter o grupo de detalhes, se a mesma linha pertencer a detalhes e a dados do grupo, só as linhas de dados de detalhes serão excluídas.</span><span class="sxs-lookup"><span data-stu-id="008f0-163">For the details group, if the same row belongs to both detail and group data, only the detail data rows are deleted.</span></span>  
  
    -   <span data-ttu-id="008f0-164">**Excluir grupo somente** Escolha esta opção para manter a mesma estrutura da região de dados tablix e excluir só a definição do grupo.</span><span class="sxs-lookup"><span data-stu-id="008f0-164">**Delete group only** Choose this option to keep the structure of the tablix data region the same and delete only the group definition.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="008f0-165">O grupo de detalhes é excluído.</span><span class="sxs-lookup"><span data-stu-id="008f0-165">The details group is deleted.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="008f0-166">Depois da remoção de uma linha de detalhes, verifique se a expressão em cada célula especifica uma expressão de agregação quando apropriado.</span><span class="sxs-lookup"><span data-stu-id="008f0-166">Verify that after you remove a details row, the expression in each cell specifies an aggregate expression where appropriate.</span></span> <span data-ttu-id="008f0-167">Se necessário, edite a expressão para especificar funções de agregação.</span><span class="sxs-lookup"><span data-stu-id="008f0-167">If necessary, edit the expression to specify aggregate functions as needed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="008f0-168">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="008f0-168">See Also</span></span>  
 <span data-ttu-id="008f0-169">[Referências de coleções de variáveis de grupo e de relatório &#40;Construtor de Relatórios e SSRS&#41;](built-in-collections-report-and-group-variables-references-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="008f0-169">[Report and Group Variables Collections References &#40;Report Builder and SSRS&#41;](built-in-collections-report-and-group-variables-references-report-builder.md) </span></span>  
 <span data-ttu-id="008f0-170">[Exemplos de expressões de grupo &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="008f0-170">[Group Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="008f0-171">[Filtrar, agrupar e classificar dados &#40;Construtor de Relatórios e SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="008f0-171">[Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="008f0-172">[Região de dados Tablix &#40;Construtor de Relatórios e SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="008f0-172">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="008f0-173">[Tabelas &#40;Construtor de Relatórios e SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="008f0-173">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="008f0-174">[Matrizes &#40;Construtor de Relatórios e SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="008f0-174">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="008f0-175">[Listas &#40;Construtor de Relatórios e SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="008f0-175">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="008f0-176">Tabelas, matrizes e listas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="008f0-176">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
