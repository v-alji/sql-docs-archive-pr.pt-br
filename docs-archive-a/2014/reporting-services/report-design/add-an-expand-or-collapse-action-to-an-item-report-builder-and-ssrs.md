---
title: Adicionar uma ação de expandir ou recolher a um item (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 49f07ad6-242b-4861-8fc1-91ca78c36d6c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 331c6a14a4a898ffcdf86f274c00e7ad3c801ec7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679147"
---
# <a name="add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs"></a><span data-ttu-id="ca6d9-102">Adicionar uma ação de expandir ou recolher a um item (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="ca6d9-102">Add an Expand or Collapse Action to an Item (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ca6d9-103">Você pode permitir que um usuário expanda ou recolha interativamente itens de relatório ou expanda ou recolha linhas e colunas associadas a um grupo para uma tabela ou matriz.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-103">You can enable a user to interactively expand or collapse report items, or expand or collapse rows and columns associated with a group for a table or matrix.</span></span> <span data-ttu-id="ca6d9-104">Para permitir que os usuários expandam ou recolham um item, defina as propriedades de visibilidade do item.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-104">To allow users to expand or collapse an item, you set the visibility properties for that item.</span></span> <span data-ttu-id="ca6d9-105">A definição de trabalhos de visibilidade em um visualizador de relatórios HTML às vezes é chamada de uma ação de *detalhamento* .</span><span class="sxs-lookup"><span data-stu-id="ca6d9-105">Setting visibility works in an HTML report viewer, and is sometimes called a *drilldown* action.</span></span>  
  
 <span data-ttu-id="ca6d9-106">Na exibição de design de relatório, você especifica o nome da caixa de texto no relatório onde deseja exibir os ícones de alternância para expandir e recolher.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-106">In report design view, you specify the name of the text box where you want to display the expand and collapse toggle icons.</span></span> <span data-ttu-id="ca6d9-107">No relatório renderizado, a caixa de texto exibe um sinal de mais (+) ou de menos (-) além de seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-107">In the rendered report, the text box displays a plus (+) or minus (-) sign in addition to its contents.</span></span> <span data-ttu-id="ca6d9-108">Quando o usuário clica na alternância, a exibição do relatório é atualizada para mostrar ou ocultar o item de relatório nas configurações de visibilidade atuais dos itens do relatório.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-108">When the user clicks the toggle, the report display is refreshed to show or hide the report item, based on the current visibility settings for items in the report.</span></span>  
  
 <span data-ttu-id="ca6d9-109">Em geral, as ações de expansão e recolhimento são usadas inicialmente para exibir apenas os dados de resumo e permitir que o usuário clique no sinal de adição para mostrar os dados detalhados.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-109">Typically, the expand and collapse action is used to initially display only summary data and to enable the user to click the plus sign to show detail data.</span></span> <span data-ttu-id="ca6d9-110">Por exemplo, é possível ocultar inicialmente uma tabela que exibe valores de um gráfico ou grupos filho de uma tabela com grupos de linhas e de colunas aninhados, como em um relatório detalhado.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-110">For example, you can initially hide a table that displays values for a chart, or hide child groups for a table with nested row or column groups, as in a drilldown report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-expand-and-collapse-action-to-a-group"></a><span data-ttu-id="ca6d9-111">Para adicionar uma ação de expansão e recolhimento a um grupo</span><span class="sxs-lookup"><span data-stu-id="ca6d9-111">To add expand and collapse action to a group</span></span>  
  
1.  <span data-ttu-id="ca6d9-112">Na exibição de design de relatório, clique na tabela ou na matriz para selecioná-la.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-112">In report design view, click the table or matrix to select it.</span></span> <span data-ttu-id="ca6d9-113">O painel Agrupamento exibe os grupos de linhas e colunas.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-113">The Grouping pane displays the row and column groups.</span></span>  
  
     <span data-ttu-id="ca6d9-114">![Painel Agrupamento](../media/groupingpane.png "Painel Agrupamento")</span><span class="sxs-lookup"><span data-stu-id="ca6d9-114">![Grouping Pane](../media/groupingpane.png "Grouping Pane")</span></span>  
  
     <span data-ttu-id="ca6d9-115">Se o painel Agrupamento não aparecer, clique no menu **Exibir** e clique em **Agrupamento**.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-115">If the Grouping pane does not appear, click the **View** menu and then click **Grouping**.</span></span>  
  
2.  <span data-ttu-id="ca6d9-116">Clique com o botão direito do mouse em qualquer lugar na barra de título do painel Agrupamento e clique em **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-116">Right-click anywhere in the title bar of the Grouping pane, and then click **Advanced**.</span></span> <span data-ttu-id="ca6d9-117">O modo do painel Agrupamento é alternado para mostrar a estrutura de exibição subjacente de linhas e colunas na superfície de design.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-117">The Grouping pane mode toggles to show the underlying display structure for rows and columns on the design surface.</span></span>  
  
     <span data-ttu-id="ca6d9-118">![Painel Agrupamento com o menu Modo Avançado](../media/groupingpane-advancedmode.png "Painel Agrupamento com o menu Modo Avançado")</span><span class="sxs-lookup"><span data-stu-id="ca6d9-118">![Grouping Pane with Advanced Mode menu](../media/groupingpane-advancedmode.png "Grouping Pane with Advanced Mode menu")</span></span>  
  
3.  <span data-ttu-id="ca6d9-119">No painel de grupo apropriado, clique no nome do grupo de linhas ou de colunas do qual você deseja ocultar as linhas ou colunas associadas.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-119">In the appropriate group pane, click the name of the row group or column group for which you want to hide the associated rows or columns.</span></span> <span data-ttu-id="ca6d9-120">O grupo é selecionado e o painel Propriedades mostra as propriedades do **Membro do Tablix** .</span><span class="sxs-lookup"><span data-stu-id="ca6d9-120">The group is selected and the Properties pane shows the **Tablix Member** properties.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ca6d9-121">Se o painel Propriedades não for exibido, clique em **Exibir** na Faixa de opções e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-121">If you do not see the Properties pane, click **View** on the Ribbon and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="ca6d9-122">No `Hidden` , escolha uma das opções a seguir para definir a visibilidade desse item de relatório na primeira vez em que você executar um relatório:</span><span class="sxs-lookup"><span data-stu-id="ca6d9-122">In `Hidden`, choose one of the following options to set the visibility of this report item the first time you run a report:</span></span>  
  
    -   <span data-ttu-id="ca6d9-123">Selecione `False` para exibir o item de relatório.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-123">Select `False` to display the report item.</span></span>  
  
    -   <span data-ttu-id="ca6d9-124">Selecione `True` para ocultar o item de relatório.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-124">Select `True` to hide the report item.</span></span>  
  
    -   <span data-ttu-id="ca6d9-125">Selecione **\<Expression>** para abrir a caixa de diálogo **expressão** para criar uma expressão que é avaliada em tempo de execução para determinar a visibilidade.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-125">Select **\<Expression>** to open the **Expression** dialog box to create an expression that is evaluated at run time to determine the visibility.</span></span>  
  
5.  <span data-ttu-id="ca6d9-126">Em **ToggleItem**, na caixa suspensa, selecione o nome de uma caixa de texto à qual adicionar a imagem de alternância.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-126">In **ToggleItem**, from the drop-down box, select the name of a text box to which to add the toggle image.</span></span>  
  
     <span data-ttu-id="ca6d9-127">Na imagem a seguir, o grupo de linhas Cor está configurado para permitir que os usuários expandam e recolham linhas associadas.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-127">In the following image, the Color row group is configured enable users to expand and collapse associated rows.</span></span>  
  
     <span data-ttu-id="ca6d9-128">![Como configurar um grupo de linhas a ser expandido](../media/expandcollapse-confighiddentoggleitemwithnumbers.png "Como configurar um grupo de linhas a ser expandido")</span><span class="sxs-lookup"><span data-stu-id="ca6d9-128">![Configuring a row group to be expanded](../media/expandcollapse-confighiddentoggleitemwithnumbers.png "Configuring a row group to be expanded")</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ca6d9-129">A caixa de texto com a imagem de alternância não pode ser o grupo de linhas ou de colunas do qual você deseja ocultar as linhas ou colunas associadas.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-129">The text box with the toggle image cannot be the row or column group for which you want to hide the associated rows or columns.</span></span> <span data-ttu-id="ca6d9-130">Ela deve estar no mesmo grupo que o item que está sendo ocultado ou em um grupo ancestral.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-130">It must either be in the same group as the item that is being hidden or in an ancestor group.</span></span> <span data-ttu-id="ca6d9-131">Por exemplo, para alternar a visibilidade de linhas associadas a um grupo filho, selecione uma caixa de texto em uma linha associada ao grupo pai.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-131">For example, to toggle visibility of rows associated with a child group, select a text box in a row associated with the parent group.</span></span>  
  
6.  <span data-ttu-id="ca6d9-132">Para testar a alternância, execute o relatório e clique na caixa de texto com a imagem de alternância.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-132">To test the toggle, run the report and click the text box with the toggle image.</span></span> <span data-ttu-id="ca6d9-133">A exibição do relatório é atualizada para mostrar grupos de linhas e de colunas com a visibilidade alternada.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-133">The report display refreshes to show row groups and column groups with their toggled visibility.</span></span>  
  
     <span data-ttu-id="ca6d9-134">![Executar relatório com um grupo de linhas expansível](../media/expandcollapse-runreport-rowgroup.png "Executar relatório com um grupo de linhas expansível")</span><span class="sxs-lookup"><span data-stu-id="ca6d9-134">![Running report with expandable row group](../media/expandcollapse-runreport-rowgroup.png "Running report with expandable row group")</span></span>  
  
### <a name="to-add-expand-and-collapse-action-to-a-report-item"></a><span data-ttu-id="ca6d9-135">Para adicionar uma ação de expansão e recolhimento a um item de relatório</span><span class="sxs-lookup"><span data-stu-id="ca6d9-135">To add expand and collapse action to a report item</span></span>  
  
1.  <span data-ttu-id="ca6d9-136">No modo de exibição de design de relatório, clique com o botão direito do mouse no item de relatório para mostrar ou ocultar e clique em *\<report item>* **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-136">In report design view, right-click the report item to show or hide, and then click *\<report item>* **Properties**.</span></span> <span data-ttu-id="ca6d9-137">A *\<report item>* caixa de diálogo **Propriedades** do item de relatório é aberta.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-137">The *\<report item>* **Properties** dialog box for the report item opens.</span></span>  
  
2.  <span data-ttu-id="ca6d9-138">Clique em **Visibilidade**.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-138">Click **Visibility**.</span></span>  
  
3.  <span data-ttu-id="ca6d9-139">Em **Quando o relatório for executado inicialmente**, escolha uma das opções a seguir para definir a visibilidade desse item de relatório na primeira vez em que o relatório for executado:</span><span class="sxs-lookup"><span data-stu-id="ca6d9-139">In **When the report is initially run**, choose one of the following options to set the visibility of this report item the first time you run a report:</span></span>  
  
    -   <span data-ttu-id="ca6d9-140">Selecione **Mostrar** para exibir o item de relatório.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-140">Select **Show** to display the report item.</span></span>  
  
    -   <span data-ttu-id="ca6d9-141">Selecione **Ocultar** para ocultar o item de relatório.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-141">Select **Hide** to hide the report item.</span></span>  
  
    -   <span data-ttu-id="ca6d9-142">Selecione **Mostrar ou ocultar com base em uma expressão** para usar uma expressão avaliada em tempo de execução para determinar a visibilidade.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-142">Select **Show or hide based on an expression** to use an expression evaluated at run time to determine the visibility.</span></span> <span data-ttu-id="ca6d9-143">Clique em (**fx**) para abrir a caixa de diálogo **Expressão** para criar uma expressão.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-143">Click (**fx**) to open the **Expression** dialog box to create an expression.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="ca6d9-144">Quando você especifica uma expressão para visibilidade, está configurando a propriedade Hidden do item de relatório.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-144">When you specify an expression for visibility, you are setting the Hidden property of the report item.</span></span> <span data-ttu-id="ca6d9-145">A expressão é avaliada como um valor `Boolean``True` para ocultar o item e `False` para mostrar o item.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-145">The expression evaluates to a `Boolean` value of `True` to hide the item and `False` to show the item.</span></span>  
  
4.  <span data-ttu-id="ca6d9-146">Em **A exibição pode ser alternada por este item de relatório**, na caixa suspensa, digite ou selecione o nome de uma caixa de texto no relatório na qual exibir uma imagem de alternância, por exemplo, Textbox1.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-146">In **Display can be toggled by this report item**, from the drop-down box, type or select the name of a text box in the report in which to display a toggle image; for example, Textbox1.</span></span>  
  
     <span data-ttu-id="ca6d9-147">Na imagem a seguir, a tabela está configurada para permitir que os usuários expandam e recolham-na.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-147">In the following image, the table is configured to enable users to expand and collapse it.</span></span> <span data-ttu-id="ca6d9-148">A exibição da tabela é alternada pela caixa de texto Tabela de Produtos.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-148">The display of the table is toggled by the Products Table text box.</span></span>  
  
     <span data-ttu-id="ca6d9-149">![Configure uma tabela de relatório a ser expandida](../media/expandcollapse-reporttable.png "Configure uma tabela de relatório a ser expandida")</span><span class="sxs-lookup"><span data-stu-id="ca6d9-149">![Configure a report table to be expanded](../media/expandcollapse-reporttable.png "Configure a report table to be expanded")</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ca6d9-150">A caixa de texto que você escolher deve estar no escopo atual ou de contenção para esse item de relatório (até e incluindo o corpo do relatório).</span><span class="sxs-lookup"><span data-stu-id="ca6d9-150">The text box that you choose must be in the current or containing scope for this report item (up to and including the report body).</span></span> <span data-ttu-id="ca6d9-151">Por exemplo, para alternar a visibilidade de um gráfico, selecione uma caixa de texto que esteja no mesmo escopo de contenção que o gráfico. Por exemplo, o corpo do relatório ou um retângulo.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-151">For example, to toggle visibility of a chart, select a text box that is in the same containing scope as the chart; for example, the report body or a rectangle.</span></span> <span data-ttu-id="ca6d9-152">A caixa de texto deve estar na mesma ou em uma hierarquia de contêiner superior.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-152">The text box must be in the same container hierarchy or higher.</span></span>  
  
5.  <span data-ttu-id="ca6d9-153">Para testar a alternância, execute o relatório e clique na caixa de texto com a imagem de alternância.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-153">To test the toggle, run the report and click the text box with the toggle image.</span></span> <span data-ttu-id="ca6d9-154">A exibição do relatório é atualizada para mostrar itens de relatório com a visibilidade alternada.</span><span class="sxs-lookup"><span data-stu-id="ca6d9-154">The report display refreshes to show report items with their toggled visibility.</span></span>  
  
     <span data-ttu-id="ca6d9-155">![Executar relatório com uma tabela de expansão](../media/expandcollapse-runreport-reporttable.png "Executar relatório com uma tabela de expansão")</span><span class="sxs-lookup"><span data-stu-id="ca6d9-155">![Running report with an expanding table](../media/expandcollapse-runreport-reporttable.png "Running report with an expanding table")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca6d9-156">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ca6d9-156">See Also</span></span>  
 <span data-ttu-id="ca6d9-157">[Ação de busca detalhada &#40;Construtor de Relatórios e SSRS&#41;](drilldown-action-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ca6d9-157">[Drilldown Action &#40;Report Builder and SSRS&#41;](drilldown-action-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ca6d9-158">Ocultar um item &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ca6d9-158">Hide an Item &#40;Report Builder and SSRS&#41;</span></span>](../report-builder/hide-an-item-report-builder-and-ssrs.md)  
  
  
