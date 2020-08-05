---
title: Criar um relatório de nível (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5933c4f0-c713-4ecb-b521-ff46c9c63fff
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d845993ac1462cef2d39638101e5c7b9fc314b94
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572426"
---
# <a name="create-a-stepped-report-report-builder-and-ssrs"></a><span data-ttu-id="e66ed-102">Criar um novo relatório de nível (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="e66ed-102">Create a Stepped Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e66ed-103">Um relatório de nível mostra as linhas ou grupos filho de detalhes recuados sob um grupo pai na mesma coluna, conforme ilustrado no seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="e66ed-103">A stepped report shows detail rows or child groups indented under a parent group in the same column, as shown in the example below:</span></span>  
  
 <span data-ttu-id="e66ed-104">![Relatório escalonado renderizado](../media/steppedreportrendered.gif "Relatório escalonado renderizado")</span><span class="sxs-lookup"><span data-stu-id="e66ed-104">![Rendered stepped report](../media/steppedreportrendered.gif "Rendered stepped report")</span></span>  
  
 <span data-ttu-id="e66ed-105">Os relatórios de tabela tradicionais colocam o grupo pai em uma coluna adjacente no relatório.</span><span class="sxs-lookup"><span data-stu-id="e66ed-105">Traditional table reports place the parent group in an adjacent column on the report.</span></span> <span data-ttu-id="e66ed-106">A nova região de dados tablix permite adicionar um grupo e linhas ou grupos filho de detalhe à mesma coluna.</span><span class="sxs-lookup"><span data-stu-id="e66ed-106">The new tablix data region enables you to add a group and detail rows or child groups to the same column.</span></span> <span data-ttu-id="e66ed-107">Para diferenciar as linhas de grupo de linhas de detalhes ou de grupos filho, você pode aplicar uma formatação, como cor da fonte, ou recuar as linhas de detalhes.</span><span class="sxs-lookup"><span data-stu-id="e66ed-107">To differentiate the group rows from the detail or child group rows, you can apply formatting such as font color, or you can indent the detail rows.</span></span>  
  
 <span data-ttu-id="e66ed-108">Os procedimentos neste tópico mostram como criar manualmente um relatório de nível, mas você também pode usar o Assistente de Nova Tabela e Matriz.</span><span class="sxs-lookup"><span data-stu-id="e66ed-108">The procedures in this topic show you how to manually create a stepped report, but you can also use the New Table and Matrix Wizard.</span></span> <span data-ttu-id="e66ed-109">Ele fornece o layout para relatórios de nível, tornando fácil criá-los.</span><span class="sxs-lookup"><span data-stu-id="e66ed-109">It provides the layout for stepped reports, making it easy to create them.</span></span> <span data-ttu-id="e66ed-110">Depois de concluir o assistente, você poderá aperfeiçoar ainda mais o relatório.</span><span class="sxs-lookup"><span data-stu-id="e66ed-110">After you complete the wizard, you can further enhance the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e66ed-111">O assistente só está disponível no Construtor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="e66ed-111">The wizard is available only in Report Builder.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-create-a-stepped-report"></a><span data-ttu-id="e66ed-112">Para criar um relatório de nível</span><span class="sxs-lookup"><span data-stu-id="e66ed-112">To create a stepped report</span></span>  
  
1.  <span data-ttu-id="e66ed-113">Crie um relatório de tabela.</span><span class="sxs-lookup"><span data-stu-id="e66ed-113">Create a table report.</span></span> <span data-ttu-id="e66ed-114">Por exemplo, insira uma região de dados tablix e adicione campos à linha Dados.</span><span class="sxs-lookup"><span data-stu-id="e66ed-114">For example, insert a tablix data region and add fields to the Data row.</span></span>  
  
2.  <span data-ttu-id="e66ed-115">Adicione um grupo pai ao relatório.</span><span class="sxs-lookup"><span data-stu-id="e66ed-115">Add a parent group to your report.</span></span>  
  
    1.  <span data-ttu-id="e66ed-116">Clique em qualquer lugar da tabela para selecioná-la.</span><span class="sxs-lookup"><span data-stu-id="e66ed-116">Click anywhere in the table to select it.</span></span> <span data-ttu-id="e66ed-117">O painel Agrupamento exibe o grupo Detalhes no painel Grupos de Linha.</span><span class="sxs-lookup"><span data-stu-id="e66ed-117">The Grouping pane displays the Details group in the Row Groups pane.</span></span>  
  
    2.  <span data-ttu-id="e66ed-118">No painel Agrupamento, clique com o botão direito do mouse em Grupo de Detalhes, aponte para **Adicionar Grupo**e clique em **Grupo Pai**.</span><span class="sxs-lookup"><span data-stu-id="e66ed-118">In the Grouping Pane, right-click the Details Group, point to **Add Group**, and then click **Parent Group**.</span></span>  
  
    3.  <span data-ttu-id="e66ed-119">Na caixa de diálogo **Grupo Tablix** , forneça um nome para o grupo e digite ou selecione uma expressão de grupo na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="e66ed-119">In the **Tablix Group** dialog box, provide a name for the group and type or select a group expression from the drop-down list.</span></span> <span data-ttu-id="e66ed-120">A lista suspensa exibe as expressões de campo simples que estão disponíveis no painel de Dados do Relatório.</span><span class="sxs-lookup"><span data-stu-id="e66ed-120">The drop-down list displays the simple field expressions that are available in the Report Data pane.</span></span> <span data-ttu-id="e66ed-121">Por exemplo, [PostalCode] é uma expressão de campo simples para o campo PostalCode em um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="e66ed-121">For example, [PostalCode] is a simple field expression for the PostalCode field in a dataset.</span></span>  
  
    4.  <span data-ttu-id="e66ed-122">Selecione **Adicionar cabeçalho de grupo**.</span><span class="sxs-lookup"><span data-stu-id="e66ed-122">Select **Add group header**.</span></span> <span data-ttu-id="e66ed-123">Esta opção adiciona uma linha estática acima do grupo para o rótulo do grupo e os totais do grupo.</span><span class="sxs-lookup"><span data-stu-id="e66ed-123">This option adds a static row above the group for the group label and group totals.</span></span> <span data-ttu-id="e66ed-124">Da mesma forma, você pode selecionar **Adicionar rodapé de grupo** para adicionar uma linha estática sob o grupo.</span><span class="sxs-lookup"><span data-stu-id="e66ed-124">Likewise, you can select **Add group footer** to add a static row below the group.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     <span data-ttu-id="e66ed-125">Você tem agora, um relatório tabular básico.</span><span class="sxs-lookup"><span data-stu-id="e66ed-125">You now have a basic tabular report.</span></span> <span data-ttu-id="e66ed-126">Quando ele for renderizado, você poderá ver uma coluna com o valor da instância do grupo, e uma ou mais colunas com os dados dos detalhes agrupados.</span><span class="sxs-lookup"><span data-stu-id="e66ed-126">When it is rendered, you see one column with the group instance value, and one or more columns with grouped detail data.</span></span> <span data-ttu-id="e66ed-127">A figura a seguir mostra como pode ser a aparência da região de dados na superfície de design.</span><span class="sxs-lookup"><span data-stu-id="e66ed-127">The following figure shows what the data region might look like on the design surface.</span></span>  
  
     <span data-ttu-id="e66ed-128">![Região de dados de tabela com grupo](../media/tabledataregionwithgroup.gif "Região de dados de tabela com grupo")</span><span class="sxs-lookup"><span data-stu-id="e66ed-128">![Table data region with group](../media/tabledataregionwithgroup.gif "Table data region with group")</span></span>  
  
     <span data-ttu-id="e66ed-129">A figura a seguir mostra como pode ser a aparência da região de dados renderizada quando você visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="e66ed-129">The following figure shows how the rendered data region might look when you view the report.</span></span>  
  
     <span data-ttu-id="e66ed-130">![Relatório agrupado renderizado](../media/tablereportrendered.gif "Relatório agrupado renderizado")</span><span class="sxs-lookup"><span data-stu-id="e66ed-130">![Rendered grouped report](../media/tablereportrendered.gif "Rendered grouped report")</span></span>  
  
3.  <span data-ttu-id="e66ed-131">Em um relatório de nível, você não precisa da primeira coluna que mostra a instância de grupo.</span><span class="sxs-lookup"><span data-stu-id="e66ed-131">For a stepped report, you do not need the first column that shows the group instance.</span></span> <span data-ttu-id="e66ed-132">Em vez disso, copie o valor na célula de cabeçalho do grupo, exclua a coluna do grupo e cole na primeira caixa de texto na linha de cabeçalho do grupo.</span><span class="sxs-lookup"><span data-stu-id="e66ed-132">Instead, copy the value in the group header cell, delete the group column, and paste in the first text box in the group header row.</span></span> <span data-ttu-id="e66ed-133">Para remover a coluna de grupo, clique com o botão direito do mouse na coluna de grupo ou na célula e clique em **Excluir Colunas**.</span><span class="sxs-lookup"><span data-stu-id="e66ed-133">To remove the group column, right-click the group column or cell, and click **Delete Columns**.</span></span> <span data-ttu-id="e66ed-134">A figura a seguir mostra como pode ser a aparência da região de dados na superfície de design.</span><span class="sxs-lookup"><span data-stu-id="e66ed-134">The following figure shows what the data region might look like on the design surface.</span></span>  
  
     <span data-ttu-id="e66ed-135">![Região de dados com linha de cabeçalho de grupo](../media/tabledataregiongroupheader.gif "Região de dados com linha de cabeçalho de grupo")</span><span class="sxs-lookup"><span data-stu-id="e66ed-135">![Data region with group header row](../media/tabledataregiongroupheader.gif "Data region with group header row")</span></span>  
  
4.  <span data-ttu-id="e66ed-136">Para recuar as linhas de detalhes sob a linha de cabeçalho do grupo na mesma coluna, altere o preenchimento da célula de dados de detalhes.</span><span class="sxs-lookup"><span data-stu-id="e66ed-136">To indent the detail rows under the group header row in the same column, change the padding of the detail data cell.</span></span>  
  
    1.  <span data-ttu-id="e66ed-137">Selecione a célula com o campo de detalhes que você quer recuar.</span><span class="sxs-lookup"><span data-stu-id="e66ed-137">Select the cell with the detail field that you want to indent.</span></span> <span data-ttu-id="e66ed-138">As propriedades da caixa de texto dessa célula aparecem no painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="e66ed-138">The text box properties for that cell appear in the Properties pane.</span></span>  
  
    2.  <span data-ttu-id="e66ed-139">No painel Propriedades, em **Alinhamento**, expanda as propriedades para **Preenchimento**.</span><span class="sxs-lookup"><span data-stu-id="e66ed-139">In the Properties pane, under **Alignment**, expand the properties for **Padding**.</span></span>  
  
    3.  <span data-ttu-id="e66ed-140">Para **esquerda**, digite um novo valor de preenchimento, como `.5in` .</span><span class="sxs-lookup"><span data-stu-id="e66ed-140">For **Left**, type a new padding value, such as `.5in`.</span></span> <span data-ttu-id="e66ed-141">O preenchimento recua o texto na célula pelo valor que você especificar.</span><span class="sxs-lookup"><span data-stu-id="e66ed-141">Padding indents the text in the cell by the value you specify.</span></span> <span data-ttu-id="e66ed-142">O preenchimento padrão é 2 pontos.</span><span class="sxs-lookup"><span data-stu-id="e66ed-142">The default padding is 2 points.</span></span> <span data-ttu-id="e66ed-143">Os valores válidos para as propriedades de preenchimento são um número de zero ou um número maior, positivo, seguido por um designador de tamanho.</span><span class="sxs-lookup"><span data-stu-id="e66ed-143">Valid values for the Padding properties are zero or a positive number, followed by a size designator.</span></span>  
  
         <span data-ttu-id="e66ed-144">Os designadores de tamanho são:</span><span class="sxs-lookup"><span data-stu-id="e66ed-144">Size designators are:</span></span>  
  
        |||  
        |-|-|  
        |`in`|<span data-ttu-id="e66ed-145">Polegadas (1 polegada = 2,54 centímetros)</span><span class="sxs-lookup"><span data-stu-id="e66ed-145">Inches (1 inch = 2.54 centimeters)</span></span>|  
        |`cm`|<span data-ttu-id="e66ed-146">Centímetros</span><span class="sxs-lookup"><span data-stu-id="e66ed-146">Centimeters</span></span>|  
        |`mm`|<span data-ttu-id="e66ed-147">Milímetros</span><span class="sxs-lookup"><span data-stu-id="e66ed-147">Millimeters</span></span>|  
        |`pt`|<span data-ttu-id="e66ed-148">Pontos (1 ponto = 1/72 polegada)</span><span class="sxs-lookup"><span data-stu-id="e66ed-148">Points (1 point = 1/72 inch)</span></span>|  
        |`pc`|<span data-ttu-id="e66ed-149">Picas (1 pica = 12 pontos)</span><span class="sxs-lookup"><span data-stu-id="e66ed-149">Picas (1 pica = 12 points)</span></span>|  
  
     <span data-ttu-id="e66ed-150">Sua região de dados será semelhante ao exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="e66ed-150">Your data region will look similar to the following example.</span></span>  
  
     <span data-ttu-id="e66ed-151">![Região de dados para relatório escalonado](../media/steppedreportdataregion.gif "Região de dados para relatório escalonado")</span><span class="sxs-lookup"><span data-stu-id="e66ed-151">![Data region for stepped report](../media/steppedreportdataregion.gif "Data region for stepped report")</span></span>  
  
     <span data-ttu-id="e66ed-152">**Região de dados para layout de relatório de nível**</span><span class="sxs-lookup"><span data-stu-id="e66ed-152">**Data Region for Stepped Report Layout**</span></span>  
  
     <span data-ttu-id="e66ed-153">Na guia **Página Inicial** , clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="e66ed-153">On the **Home** tab Click **Run**.</span></span> <span data-ttu-id="e66ed-154">O relatório exibe o grupo com os níveis de recuo para os valores do grupo filho.</span><span class="sxs-lookup"><span data-stu-id="e66ed-154">The report displays the group with indented levels for the child group values.</span></span>  
  
### <a name="to-create-a-stepped-report-with-multiple-groups"></a><span data-ttu-id="e66ed-155">Para criar um relatório de nível com vários grupos</span><span class="sxs-lookup"><span data-stu-id="e66ed-155">To create a stepped report with multiple groups</span></span>  
  
1.  <span data-ttu-id="e66ed-156">Crie um relatório conforme descrito no procedimento anterior.</span><span class="sxs-lookup"><span data-stu-id="e66ed-156">Create a report as described in the previous procedure.</span></span>  
  
2.  <span data-ttu-id="e66ed-157">Acrescente grupos adicionais ao seu relatório.</span><span class="sxs-lookup"><span data-stu-id="e66ed-157">Add additional groups to your report.</span></span>  
  
    1.  <span data-ttu-id="e66ed-158">No painel Grupos de Linha, clique com o botão direito do mouse no grupo, clique em **Adicionar Grupo**e escolha o tipo de grupo que deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="e66ed-158">In the Row Groups pane, right-click the group, click **Add Group**, and then choose the type of group you want to add.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="e66ed-159">Há várias maneiras para acrescentar grupos a uma região de dados.</span><span class="sxs-lookup"><span data-stu-id="e66ed-159">There are several ways to add groups to a data region.</span></span> <span data-ttu-id="e66ed-160">Para obter mais informações, consulte [Adicionar ou excluir um grupo em uma região de dados &#40;Construtor de relatórios e SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e66ed-160">For more information, see [Add or Delete a Group in a Data Region &#40;Report Builder and SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md).</span></span>  
  
    2.  <span data-ttu-id="e66ed-161">Na caixa de diálogo **Grupo Tablix** , digite um nome.</span><span class="sxs-lookup"><span data-stu-id="e66ed-161">In the **Tablix Group** dialog box, type a name.</span></span>  
  
    3.  <span data-ttu-id="e66ed-162">Em **Expressão de grupo**, digite uma expressão ou selecione um campo do conjunto de dados para agrupar.</span><span class="sxs-lookup"><span data-stu-id="e66ed-162">In **Group expression**, type an expression or select a dataset field to group on.</span></span> <span data-ttu-id="e66ed-163">Para criar uma expressão, clique no botão de expressão (**fx**) para abrir a caixa de diálogo **Expressão** .</span><span class="sxs-lookup"><span data-stu-id="e66ed-163">To create an expression, click the expression (**fx**) button to open the **Expression** dialog box.</span></span>  
  
    4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
3.  <span data-ttu-id="e66ed-164">Altere o preenchimento da célula que exibe os dados do grupo.</span><span class="sxs-lookup"><span data-stu-id="e66ed-164">Change the padding for the cell that displays the group data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e66ed-165">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e66ed-165">See Also</span></span>  
 <span data-ttu-id="e66ed-166">[Cabeçalhos e rodapés de página &#40;Construtor de Relatórios e SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e66ed-166">[Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e66ed-167">[Formatando itens de relatório &#40;Construtor de Relatórios e SSRS&#41;](formatting-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e66ed-167">[Formatting Report Items &#40;Report Builder and SSRS&#41;](formatting-report-items-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e66ed-168">[Região de dados Tablix &#40;Construtor de Relatórios e SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e66ed-168">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e66ed-169">[Tabelas &#40;Construtor de Relatórios e SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e66ed-169">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e66ed-170">[Matrizes &#40;Construtor de Relatórios e SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e66ed-170">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e66ed-171">[Lista &#40;Construtor de Relatórios e SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e66ed-171">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e66ed-172">Tabelas, matrizes e listas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e66ed-172">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
