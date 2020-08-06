---
title: 'Lição 6: Adicionar agrupamentos e totais (Reporting Services) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e3d61228-2aa4-42cc-955e-602dbf3406a7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b98798005a984edf00aff469d4c1b09aa2e34d98
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582818"
---
# <a name="lesson-6-adding-grouping-and-totals-reporting-services"></a><span data-ttu-id="76085-102">Lição 6: Adicionar agrupamentos e totais (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="76085-102">Lesson 6: Adding Grouping and Totals (Reporting Services)</span></span>
  <span data-ttu-id="76085-103">Adicione agrupamento e totais ao relatório para organizar e resumir os dados.</span><span class="sxs-lookup"><span data-stu-id="76085-103">Add grouping and totals to your report to organize and summarize your data.</span></span>  
  
 <span data-ttu-id="76085-104">Para obter informações sobre como adicionar totais acumulados a relatórios, consulte: [adicionando totais a Reporting Services (SSRS) relatórios](https://www.tutorialgateway.org/add-total-and-subtotal-to-ssrs-report/).</span><span class="sxs-lookup"><span data-stu-id="76085-104">For information about adding running totals to reports, see: [Adding totals to Reporting Services (SSRS) reports](https://www.tutorialgateway.org/add-total-and-subtotal-to-ssrs-report/).</span></span>  
  
 <span data-ttu-id="76085-105">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="76085-105">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="76085-106">Para agrupar dados em um relatório</span><span class="sxs-lookup"><span data-stu-id="76085-106">To group data in a report</span></span>](#bkmk_groupdata)  
  
-   [<span data-ttu-id="76085-107">Para adicionar totais a um relatório</span><span class="sxs-lookup"><span data-stu-id="76085-107">To add totals to a report</span></span>](#bkmk_addtotals)  
  
-   [<span data-ttu-id="76085-108">Para adicionar um total diário a um relatório</span><span class="sxs-lookup"><span data-stu-id="76085-108">To add a daily total to a report</span></span>](#bkmk_adddailytotal)  
  
-   [<span data-ttu-id="76085-109">Para adicionar um total geral a um relatório</span><span class="sxs-lookup"><span data-stu-id="76085-109">To add a grand total to a report</span></span>](#bkmk_addgrandtotal)  
  
-   [<span data-ttu-id="76085-110">Para publicar o relatório no Servidor de Relatório (opcional)</span><span class="sxs-lookup"><span data-stu-id="76085-110">To Publish the Report to the Report Server (Optional)</span></span>](#bkmk_publishreport)  
  
##  <a name="to-group-data-in-a-report"></a><a name="bkmk_groupdata"></a><span data-ttu-id="76085-111">Para agrupar dados em um relatório</span><span class="sxs-lookup"><span data-stu-id="76085-111">To group data in a report</span></span>  
  
1.  <span data-ttu-id="76085-112">Clique na guia **Design** .</span><span class="sxs-lookup"><span data-stu-id="76085-112">Click the **Design** tab.</span></span>  
  
2.  <span data-ttu-id="76085-113">Se você não vir o painel **grupos de linhas** , clique com o botão direito do mouse na superfície de design e clique em **Exibir** e em **agrupamento**.</span><span class="sxs-lookup"><span data-stu-id="76085-113">If you do not see the **Row Groups** pane , right-click the design surface and click **view** and then click **Grouping**.</span></span>  
  
3.  <span data-ttu-id="76085-114">No painel **Dados do Relatório**, arraste o campo `Date` para o painel **Grupos de Linhas**.</span><span class="sxs-lookup"><span data-stu-id="76085-114">From the **Report Data** pane, drag the `Date` field to the **Row Groups** pane.</span></span> <span data-ttu-id="76085-115">Coloque-o acima da linha chamada **(Detalhes)**.</span><span class="sxs-lookup"><span data-stu-id="76085-115">Place it above the row called **(Details)**.</span></span>  
  
     <span data-ttu-id="76085-116">Observe que a alça de linha agora exibe um colchete para mostrar um grupo.</span><span class="sxs-lookup"><span data-stu-id="76085-116">Note that the row handle now has a bracket in it, to show a group.</span></span> <span data-ttu-id="76085-117">A tabela também tem duas colunas Data – uma em cada lado de uma linha pontilhada vertical.</span><span class="sxs-lookup"><span data-stu-id="76085-117">The table now also has two Date columns -- one on either side of a vertical dotted line.</span></span>  
  
     ![](../../2014/tutorials/media/rs-basictablegroups1design.gif "rs_BasicTableGroups1Design")  
  
4.  <span data-ttu-id="76085-118">No painel **Dados do Relatório**, arraste o campo `Order` para o painel **Grupos de Linhas**.</span><span class="sxs-lookup"><span data-stu-id="76085-118">From the **Report Data** pane, drag the `Order` field to the **Row Groups** pane.</span></span> <span data-ttu-id="76085-119">Coloque-o abaixo de Data e acima de **(Detalhes)**.</span><span class="sxs-lookup"><span data-stu-id="76085-119">Place it below Date and above **(Details)**.</span></span>  
  
     <span data-ttu-id="76085-120">Observe que a alça de linha agora exibe dois colchetes para mostrar dois grupos.</span><span class="sxs-lookup"><span data-stu-id="76085-120">Note that the row handle now has two brackets in it, to show two groups.</span></span> <span data-ttu-id="76085-121">A tabela agora também tem duas `Order` colunas.</span><span class="sxs-lookup"><span data-stu-id="76085-121">The table now has two `Order` columns, too.</span></span>  
  
5.  <span data-ttu-id="76085-122">Exclua as colunas Data e Pedido originais à **direita** da linha dupla.</span><span class="sxs-lookup"><span data-stu-id="76085-122">Delete the original Date and Order columns to the **right** of the double line.</span></span> <span data-ttu-id="76085-123">Isso removerá os valores do registro individual para que apenas o valor do grupo seja exibido.</span><span class="sxs-lookup"><span data-stu-id="76085-123">This removes this individual record values so that only the group value is displayed.</span></span> <span data-ttu-id="76085-124">Selecione as alças de coluna das duas colunas, clique com o botão direito do mouse e clique em **Excluir Colunas**.</span><span class="sxs-lookup"><span data-stu-id="76085-124">Select the column handles for the two columns, right-click and click **Delete Columns**.</span></span>  
  
     <span data-ttu-id="76085-125">![Selecionar colunas para exclusão](../../2014/tutorials/media/rs-basictablegroupsdeletecols.gif "Selecionar colunas para exclusão")</span><span class="sxs-lookup"><span data-stu-id="76085-125">![Select columns to delete](../../2014/tutorials/media/rs-basictablegroupsdeletecols.gif "Select columns to delete")</span></span>  
  
     <span data-ttu-id="76085-126">Você pode formatar os cabeçalhos de coluna e a data novamente.</span><span class="sxs-lookup"><span data-stu-id="76085-126">You can format the column headers and date again.</span></span>  
  
6.  <span data-ttu-id="76085-127">Alterne para a guia **Visualizar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="76085-127">Switch to the **Preview** tab to preview the report.</span></span> <span data-ttu-id="76085-128">Sua aparência deve ser similar a esta ilustração:</span><span class="sxs-lookup"><span data-stu-id="76085-128">It should look similar to the following illustration:</span></span>  
  
     <span data-ttu-id="76085-129">![Tabela agrupada por data e ordem](../../2014/tutorials/media/rs-basictablegroupspreview.gif "Tabela agrupada por data e ordem")</span><span class="sxs-lookup"><span data-stu-id="76085-129">![Table grouped by date and then order](../../2014/tutorials/media/rs-basictablegroupspreview.gif "Table grouped by date and then order")</span></span>  
  
##  <a name="to-add-totals-to-a-report"></a><a name="bkmk_addtotals"></a><span data-ttu-id="76085-130">Para adicionar totais a um relatório</span><span class="sxs-lookup"><span data-stu-id="76085-130">To add totals to a report</span></span>  
  
1.  <span data-ttu-id="76085-131">Alterne para o modo Design.</span><span class="sxs-lookup"><span data-stu-id="76085-131">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="76085-132">Clique com o botão direito do mouse na célula da região de dados que contém o campo `[LineTotal]`e clique em **Adicionar Total**.</span><span class="sxs-lookup"><span data-stu-id="76085-132">Right-click the data region cell that contains the field `[LineTotal]`, and click **Add Total**.</span></span>  
  
     <span data-ttu-id="76085-133">Isso adicionará uma linha com uma soma do valor monetário de cada pedido.</span><span class="sxs-lookup"><span data-stu-id="76085-133">This adds a row with a sum of the dollar amount for each order.</span></span>  
  
3.  <span data-ttu-id="76085-134">Clique com o botão direito do mouse na célula que contém o campo `[Qty]`e clique em **Adicionar Total**.</span><span class="sxs-lookup"><span data-stu-id="76085-134">Right-click the cell that contains the field `[Qty]`, and click **Add Total**.</span></span>  
  
     <span data-ttu-id="76085-135">Isso adicionará uma soma da quantidade de cada pedido à linha de total.</span><span class="sxs-lookup"><span data-stu-id="76085-135">This adds a sum of the quantity for each order to the totals row.</span></span>  
  
4.  <span data-ttu-id="76085-136">Na célula vazia à esquerda de `Sum[Qty]`, digite o rótulo "**Total de Pedidos"**.</span><span class="sxs-lookup"><span data-stu-id="76085-136">In the empty cell to the left of `Sum[Qty]`, type the label "**Order Total"**.</span></span>  
  
5.  <span data-ttu-id="76085-137">Você pode adicionar uma cor do plano de fundo à linha de total.</span><span class="sxs-lookup"><span data-stu-id="76085-137">You can add a background color to the totals row.</span></span> <span data-ttu-id="76085-138">Selecione as duas células de soma e a célula de rótulo.</span><span class="sxs-lookup"><span data-stu-id="76085-138">Select the two sum cells and the label cell.</span></span>  
  
6.  <span data-ttu-id="76085-139">No menu **Formatar** , clique em **Cor do Plano de Fundo**, clique em **Cinza Claro**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="76085-139">On the **Format** menu, click **Background Color**, click **Light Gray**, and click **OK**.</span></span>  
  
     <span data-ttu-id="76085-140">![Modo de design: Tabela básica com total do pedido](../../2014/tutorials/media/rs-basictablesumlinetotaldesign.gif "Modo de design: Tabela básica com total do pedido")</span><span class="sxs-lookup"><span data-stu-id="76085-140">![Design view: Basic table with order total](../../2014/tutorials/media/rs-basictablesumlinetotaldesign.gif "Design view: Basic table with order total")</span></span>  
  
##  <a name="to-add-a-daily-total-to-a-report"></a><a name="bkmk_adddailytotal"></a><span data-ttu-id="76085-141">Para adicionar um total diário a um relatório</span><span class="sxs-lookup"><span data-stu-id="76085-141">To add a daily total to a report</span></span>  
  
1.  <span data-ttu-id="76085-142">Clique com o botão direito do mouse na célula Pedido , aponte para **Adicionar Total**e clique em **Após**.</span><span class="sxs-lookup"><span data-stu-id="76085-142">Right-click the Order cell, point to **Add Total**, and click **After**.</span></span>  
  
     <span data-ttu-id="76085-143">Isso adiciona uma nova linha contendo somas da quantidade e do valor de dólar para cada dia e o rótulo "**total**" na coluna ordem.</span><span class="sxs-lookup"><span data-stu-id="76085-143">This adds a new row containing sums of the quantity and dollar amount for each day, and the label "**Total**" in the Order column.</span></span>  
  
2.  <span data-ttu-id="76085-144">Digite o palavra **Diário** depois da palavra **Total** na mesma célula para que apareça **Total Diário**.</span><span class="sxs-lookup"><span data-stu-id="76085-144">Type the word **Daily** before the word **Total** in the same cell, so it reads **Daily Total**.</span></span>  
  
3.  <span data-ttu-id="76085-145">Selecione a célula **Total Diário** , as duas células **Soma** e a célula vazia entre eles.</span><span class="sxs-lookup"><span data-stu-id="76085-145">Select the **Daily Total** cell, the two **Sum** cells and the empty cell between them.</span></span>  
  
4.  <span data-ttu-id="76085-146">No menu **Formatar** , clique em **Cor do Plano de Fundo**, clique em **Laranja**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="76085-146">On the **Format** menu, click **Background Color**, click **Orange**, and click **OK**.</span></span>  
  
     ![](../../2014/tutorials/media/rs-basictablesumdaytotaldesign.gif "rs_BasicTableSumDayTotalDesign")  
  
##  <a name="to-add-a-grand-total-to-a-report"></a><a name="bkmk_addgrandtotal"></a><span data-ttu-id="76085-147">Para adicionar um total geral a um relatório</span><span class="sxs-lookup"><span data-stu-id="76085-147">To add a grand total to a report</span></span>  
  
1.  <span data-ttu-id="76085-148">Clique com o botão direito do mouse na célula Data, aponte para **Adicionar Total**e clique em **Após**.</span><span class="sxs-lookup"><span data-stu-id="76085-148">Right-click the Date cell, point to **Add Total**, and click **After**.</span></span>  
  
     <span data-ttu-id="76085-149">Isso adiciona uma nova linha contendo as somas da quantidade e do valor de dólar do relatório inteiro e o rótulo **total** na `Date` coluna.</span><span class="sxs-lookup"><span data-stu-id="76085-149">This adds a new row containing sums of the quantity and dollar amount for the entire report, and the **Total** label in the `Date` column.</span></span>  
  
2.  <span data-ttu-id="76085-150">Digite a palavra **Geral** depois da palavra **Total** na mesma célula para que apareça **Total Geral**.</span><span class="sxs-lookup"><span data-stu-id="76085-150">Type the word **Grand** before the word **Total** in the same cell, so it reads **Grand Total**.</span></span>  
  
3.  <span data-ttu-id="76085-151">Selecione a célula **Total Geral** , as duas células **Soma** e as células vazias entre eles.</span><span class="sxs-lookup"><span data-stu-id="76085-151">Select the **Grand Total** cell, the two **Sum** cells and the empty cells between them.</span></span>  
  
4.  <span data-ttu-id="76085-152">No menu **Formatar** , clique em **Cor do Plano de Fundo**, clique em **Azul Claro**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="76085-152">On the **Format** menu, click **Background Color**, click **Light Blue**, and click **OK**.</span></span>  
  
     <span data-ttu-id="76085-153">![Modo de design: Total geral em tabela básica](../../2014/tutorials/media/rs-basictablesumgrandtotaldesign.gif "Modo de design: Total geral em tabela básica")</span><span class="sxs-lookup"><span data-stu-id="76085-153">![Design view: Grand total in basic table](../../2014/tutorials/media/rs-basictablesumgrandtotaldesign.gif "Design view: Grand total in basic table")</span></span>  
  
5.  <span data-ttu-id="76085-154">Clique em Visualizar.</span><span class="sxs-lookup"><span data-stu-id="76085-154">Click Preview.</span></span>  
  
     <span data-ttu-id="76085-155">A última página deve ter a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="76085-155">The last page should look something like this:</span></span>  
  
     <span data-ttu-id="76085-156">![Visualização: Tabela básica com total geral](../../2014/tutorials/media/rs-basictablesumgrandtotalpreview.gif "Visualização: Tabela básica com total geral")</span><span class="sxs-lookup"><span data-stu-id="76085-156">![Preview: Basic table with grand total](../../2014/tutorials/media/rs-basictablesumgrandtotalpreview.gif "Preview: Basic table with grand total")</span></span>  
  
##  <a name="to-publish-the-report-to-the-report-server-optional"></a><a name="bkmk_publishreport"></a><span data-ttu-id="76085-157">Para publicar o relatório no servidor de relatório (opcional)</span><span class="sxs-lookup"><span data-stu-id="76085-157">To Publish the Report to the Report Server (Optional)</span></span>  
  
1.  <span data-ttu-id="76085-158">Uma etapa opcional é publicar o relatório concluído no servidor de relatório de modo nativo para que você possa exibir o relatório no Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="76085-158">An optional step is to publish the completed report to the native mode report server so you can view the report from Report Manager.</span></span>  
  
2.  <span data-ttu-id="76085-159">Na barra de ferramentas, clique em **Projeto** e, em seguida, em **tutorial Propriedades...**.</span><span class="sxs-lookup"><span data-stu-id="76085-159">On the toolbar click **Project** and then click **tutorial Properties...**</span></span>  
  
3.  <span data-ttu-id="76085-160">Em **TargetServerURL** , digite o nome do nome do servidor de relatório, por exemplo **http:// \<servername> /ReportServer**</span><span class="sxs-lookup"><span data-stu-id="76085-160">In the **TargetServerURL** type the name of the name of your report server, for example **http://\<servername>/reportserver**</span></span>  
  
4.  <span data-ttu-id="76085-161">Clique em **OK**</span><span class="sxs-lookup"><span data-stu-id="76085-161">Click **OK**</span></span>  
  
5.  <span data-ttu-id="76085-162">Na barra de ferramentas, clique em **Compilar** e, em seguida, em **Implantar tutorial**.</span><span class="sxs-lookup"><span data-stu-id="76085-162">On the toolbar click **Build** and then click **Deploy tutorial**.</span></span>  
  
     <span data-ttu-id="76085-163">Se você vir uma mensagem semelhante à seguinte na janela de saída, ela indicará uma implantação com êxito.</span><span class="sxs-lookup"><span data-stu-id="76085-163">If you see a message similar to the following in the output window, it indicates a successful deployment.</span></span>  
  
    > <span data-ttu-id="76085-164">------ Build started: Project: tutorial, Configuration: Debug ------Skipping 'Sales Orders.rdl'.</span><span class="sxs-lookup"><span data-stu-id="76085-164">------ Build started: Project: tutorial, Configuration: Debug ------Skipping 'Sales Orders.rdl'.</span></span> <span data-ttu-id="76085-165">O item está atualizado. Compilação concluída--0 erros, 0 avisos------implantação iniciada: Projeto: tutorial, configuração: Depurar------implantando no \<server name> relatório http:///reportserverDeploying '/tutorial/Sales Orders '. Implantação concluída--0 erros, 0 avisos = = = = = = = = = = = Build: 1 êxito ou atualizado, 0 com falha, 0 ignorado = = = = = = = = = = = = = = = = = = = = = = = Deploy: 1 Succeeded, 0 com falha, 0 ignorada = = = = = = = = = =</span><span class="sxs-lookup"><span data-stu-id="76085-165">Item is up to date.Build complete -- 0 errors, 0 warnings------ Deploy started: Project: tutorial, Configuration: Debug ------Deploying to http://\<server name>/reportserverDeploying report '/tutorial/Sales Orders'.Deploy complete -- 0 errors, 0 warnings========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==================== Deploy: 1 succeeded, 0 failed, 0 skipped ==========</span></span>  
  
     <span data-ttu-id="76085-166">Se você vir uma mensagem de erro semelhante à seguinte, verifique se você tem permissões no servidor de relatório e se iniciou o [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] com privilégios de administrador.</span><span class="sxs-lookup"><span data-stu-id="76085-166">If you see an error message similar to the following, verify you have permissions on the report server and you have started [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] with administrator privileges.</span></span>  
  
    > <span data-ttu-id="76085-167">"As permissões concedidas ao usuário ' XXXXXXXX \\<seu nome \> de usuário ' são insuficientes para executar esta operação"</span><span class="sxs-lookup"><span data-stu-id="76085-167">"The permissions granted to user 'XXXXXXXX\\<your user name\>' are insufficient for performing this operation"</span></span>  
  
6.  <span data-ttu-id="76085-168">Inicie Report Manager com privilégios de administrador, por exemplo, clique com o botão direito do mouse no ícone do Internet Explorer e clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="76085-168">Start Report Manager with administrator privileges, for example, right-click the icon for Internet Explorer and click **Run as administrator**.</span></span>  
  
     <span data-ttu-id="76085-169">Navegue até a URL do Gerenciador de Relatórios, por exemplo: `http://<server name>/reports`.</span><span class="sxs-lookup"><span data-stu-id="76085-169">Browse to the Report Manager URL, for example: `http://<server name>/reports`.</span></span>  
  
7.  <span data-ttu-id="76085-170">Navegue até a pasta que contém o relatório e clique no nome do relatório `Sales Orders` para exibir o relatório renderizado no navegador.</span><span class="sxs-lookup"><span data-stu-id="76085-170">Browse to the folder that contains the report and click the name of the report `Sales Orders` to view the rendered report in the browser.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="76085-171">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="76085-171">Next Steps</span></span>  
 <span data-ttu-id="76085-172">Você concluiu com êxito o tutorial Criando um relatório de tabela básico.</span><span class="sxs-lookup"><span data-stu-id="76085-172">You have successfully completed the Creating a Basic Table Report tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76085-173">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="76085-173">See Also</span></span>  
 [<span data-ttu-id="76085-174">Filtrar, agrupar e classificar dados &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="76085-174">Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;</span></span>](report-design/filter-group-and-sort-data-report-builder-and-ssrs.md)  
  
  
