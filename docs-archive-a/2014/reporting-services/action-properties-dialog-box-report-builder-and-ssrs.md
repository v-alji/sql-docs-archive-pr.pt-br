---
title: Caixa de diálogo Propriedades da ação (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.shared.action.f1
- "10413"
- "10504"
- sql12.rtp.rptdesigner.calculatedseriesproperties.action.f1
- sql12.rtp.rptdesigner.pictureproperties.action.f1
- sql12.rtp.rptdesigner.actionproperties.f1
- sql12.rtp.rptdesigner.charttitleproperties.action.f1
- "10133"
- "10052"
- "10147"
- sql12.rtp.rptdesigner.chartproperties.action.f1
- "10122"
- sql12.rtp.rptdesigner.serieslabelproperties.action.f1
- sql12.rtp.rptdesigner.textboxproperties.action.f1
- "10162"
- "10168"
- sql12.rtp.rptdesigner.textproperties.action.f1
- sql12.rtp.rptdesigner.placeholderproperties.action.f1
- "10250"
- "10129"
- "10244"
- sql12.rtp.rptdesigner.seriesproperties.action.f1
ms.assetid: 2c5d915b-4f97-42cf-b8f1-49ca3ff3d0f9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 77b51af0763010676b95fcedb433ab963fc7fcdf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575665"
---
# <a name="action-properties-dialog-box-report-builder-and-ssrs"></a><span data-ttu-id="46c6d-102">Caixa de diálogo Propriedades de Ação (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="46c6d-102">Action Properties Dialog Box (Report Builder and SSRS)</span></span>
  <span data-ttu-id="46c6d-103">A caixa de diálogo **Ação** pode ser usada para habilitar opções de hiperlink para um gráfico, um medidor e elementos de mapa com suporte para links.</span><span class="sxs-lookup"><span data-stu-id="46c6d-103">The **Action** dialog box can be used to enable hyperlink options for a chart, gauge, and map elements that support links.</span></span> <span data-ttu-id="46c6d-104">Defina uma ação para que um usuário possa clicar no relatório e vincular a uma URL, para um relatório diferente no mesmo servidor de relatório ou em um site do SharePoint integrado a um servidor de relatório ou para um local diferente no mesmo relatório.</span><span class="sxs-lookup"><span data-stu-id="46c6d-104">Define an action so that a user can click on the report and link to a URL, to a different report on the same report server or on a SharePoint site that is integrated with a report server, or to a different location in the same report.</span></span>  
  
## <a name="options"></a><span data-ttu-id="46c6d-105">Opções</span><span class="sxs-lookup"><span data-stu-id="46c6d-105">Options</span></span>  
 <span data-ttu-id="46c6d-106">**Habilitar como uma ação**</span><span class="sxs-lookup"><span data-stu-id="46c6d-106">**Enable as an action**</span></span>  
 <span data-ttu-id="46c6d-107">Selecione uma opção para indicar a ação que será executada quando o usuário clicar no item.</span><span class="sxs-lookup"><span data-stu-id="46c6d-107">Select an option to indicate the action to perform when the user clicks the item.</span></span>  
  
 <span data-ttu-id="46c6d-108">**Nenhuma**</span><span class="sxs-lookup"><span data-stu-id="46c6d-108">**None**</span></span>  
 <span data-ttu-id="46c6d-109">Escolha esta opção para indicar que o item não tem nenhuma ação.</span><span class="sxs-lookup"><span data-stu-id="46c6d-109">Choose this option to indicate that the item has no action.</span></span>  
  
 <span data-ttu-id="46c6d-110">**Ir para o relatório**</span><span class="sxs-lookup"><span data-stu-id="46c6d-110">**Go to report**</span></span>  
 <span data-ttu-id="46c6d-111">Escolha esta opção para criar um link para um relatório detalhado localizado em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="46c6d-111">Choose this option to create a link to a drillthrough report that is located on a report server.</span></span> <span data-ttu-id="46c6d-112">As opções adicionais a seguir aparecem quando você seleciona **Ir para o relatório**.</span><span class="sxs-lookup"><span data-stu-id="46c6d-112">The following additional options appear when you select **Go to report**.</span></span>  
  
 <span data-ttu-id="46c6d-113">**Especifique um relatório**</span><span class="sxs-lookup"><span data-stu-id="46c6d-113">**Specify a report**</span></span>  
 <span data-ttu-id="46c6d-114">Digite ou selecione o nome do relatório que você deseja usar como um relatório detalhado.</span><span class="sxs-lookup"><span data-stu-id="46c6d-114">Type or select the name of the report that you want to use as a drillthrough report.</span></span> <span data-ttu-id="46c6d-115">Relatórios detalhados devem estar no mesmo servidor de relatório que esse relatório.</span><span class="sxs-lookup"><span data-stu-id="46c6d-115">Drillthrough reports must be on the same report server as this report.</span></span>  
  
 <span data-ttu-id="46c6d-116">Em um relatório publicado em um servidor de relatório configurado para o modo nativo, use um caminho completo ou relativo sem a extensão do nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="46c6d-116">For a report published to a report server configured for native mode, use a full or relative path without the file name extension.</span></span> <span data-ttu-id="46c6d-117">Se o relatório estiver na mesma pasta do relatório atual, use apenas o nome do relatório.</span><span class="sxs-lookup"><span data-stu-id="46c6d-117">If the report is in the same folder as the current report, use the name of the report only.</span></span> <span data-ttu-id="46c6d-118">Se o relatório estiver em outra pasta no mesmo servidor de relatório, use um caminho relativo ou um caminho completo.</span><span class="sxs-lookup"><span data-stu-id="46c6d-118">If the report is in a different folder on the same report server, use a relative path or a full path.</span></span> <span data-ttu-id="46c6d-119">Um caminho relativo inicia na pasta atual e é movido para cima na hierarquia de pastas, por exemplo,../Folder2/Report1.</span><span class="sxs-lookup"><span data-stu-id="46c6d-119">A relative path starts from the current folder and moves up the folder hierarchy, for example, ../Folder2/Report1.</span></span> <span data-ttu-id="46c6d-120">Um caminho completo inicia em /, a pasta base.</span><span class="sxs-lookup"><span data-stu-id="46c6d-120">A full path starts from /, the Home folder.</span></span> <span data-ttu-id="46c6d-121">Por exemplo, /Reports/Report1.</span><span class="sxs-lookup"><span data-stu-id="46c6d-121">For example, /Reports/Report1.</span></span>  
  
 <span data-ttu-id="46c6d-122">Para um relatório publicado em um servidor de relatórios configurado para o modo integrado do SharePoint, use uma URL totalmente qualificada incluindo a extensão do nome de arquivo (.rdl).</span><span class="sxs-lookup"><span data-stu-id="46c6d-122">For a report published to a report server configured in SharePoint integrated mode, use a fully qualified URL including the file name extension (.rdl).</span></span> <span data-ttu-id="46c6d-123">Por exemplo, http:// *\<SharePointservername>/\<site>* /Documents/Report1.RDL.</span><span class="sxs-lookup"><span data-stu-id="46c6d-123">For example, http://*\<SharePointservername>/\<site>*/Documents/Report1.rdl.</span></span> <span data-ttu-id="46c6d-124">Não há suporte para caminhos relativos.</span><span class="sxs-lookup"><span data-stu-id="46c6d-124">Relative paths are not supported.</span></span>  
  
 <span data-ttu-id="46c6d-125">Para obter mais informações, consulte [Como especificar caminhos para itens externos &#40;Construtor de Relatórios e SSRS&#41;](report-design/specifying-paths-to-external-items-report-builder-and-ssrs.md) na [documentação do Construtor de Relatórios](https://go.microsoft.com/fwlink/?LinkId=154494) em msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="46c6d-125">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](report-design/specifying-paths-to-external-items-report-builder-and-ssrs.md) in the [Report Builder documentation](https://go.microsoft.com/fwlink/?LinkId=154494) on msdn.microsoft.com.</span></span>  
  
 <span data-ttu-id="46c6d-126">**Use estes parâmetros para executar o relatório**</span><span class="sxs-lookup"><span data-stu-id="46c6d-126">**Use these parameters to run the report**</span></span>  
 <span data-ttu-id="46c6d-127">Adicione uma lista de parâmetros para passar para o relatório detalhado.</span><span class="sxs-lookup"><span data-stu-id="46c6d-127">Add a list of parameters to pass to the drillthrough report.</span></span> <span data-ttu-id="46c6d-128">Os nomes de parâmetro devem corresponder aos parâmetros definidos para o relatório de destino.</span><span class="sxs-lookup"><span data-stu-id="46c6d-128">The parameter names must match the parameters defined for the target report.</span></span> <span data-ttu-id="46c6d-129">Use os botões **Adicionar** e **Excluir** para adicionar ou remover parâmetros e use as setas para cima e para baixo para ordenar a lista de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="46c6d-129">Use the **Add** and **Delete** buttons to add and remove parameters and use the up and down arrows to order the list of parameters.</span></span>  
  
 <span data-ttu-id="46c6d-130">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="46c6d-130">**Add**</span></span>  
 <span data-ttu-id="46c6d-131">Adicione um novo parâmetro para passar para o relatório detalhado.</span><span class="sxs-lookup"><span data-stu-id="46c6d-131">Add a new parameter to pass to the drillthrough report.</span></span>  
  
 <span data-ttu-id="46c6d-132">**Delete (excluir)**</span><span class="sxs-lookup"><span data-stu-id="46c6d-132">**Delete**</span></span>  
 <span data-ttu-id="46c6d-133">Exclua um parâmetro para o relatório detalhado.</span><span class="sxs-lookup"><span data-stu-id="46c6d-133">Delete a parameter for the drillthrough report.</span></span>  
  
 <span data-ttu-id="46c6d-134">**Seta para cima**</span><span class="sxs-lookup"><span data-stu-id="46c6d-134">**Up arrow**</span></span>  
 <span data-ttu-id="46c6d-135">Mova o parâmetro para cima na lista.</span><span class="sxs-lookup"><span data-stu-id="46c6d-135">Move the parameter up in the list.</span></span>  
  
 <span data-ttu-id="46c6d-136">**Seta para baixo**</span><span class="sxs-lookup"><span data-stu-id="46c6d-136">**Down arrow**</span></span>  
 <span data-ttu-id="46c6d-137">Mova o parâmetro para baixo na lista.</span><span class="sxs-lookup"><span data-stu-id="46c6d-137">Move the parameter down in the list.</span></span>  
  
 <span data-ttu-id="46c6d-138">**Nome**</span><span class="sxs-lookup"><span data-stu-id="46c6d-138">**Name**</span></span>  
 <span data-ttu-id="46c6d-139">Digite o texto que é o nome de um parâmetro definido no relatório detalhado.</span><span class="sxs-lookup"><span data-stu-id="46c6d-139">Type text that is the name of a parameter defined in the drillthrough report.</span></span>  
  
 <span data-ttu-id="46c6d-140">**Valor**</span><span class="sxs-lookup"><span data-stu-id="46c6d-140">**Value**</span></span>  
 <span data-ttu-id="46c6d-141">Digite ou selecione um valor para passar para o parâmetro nomeado no relatório detalhado.</span><span class="sxs-lookup"><span data-stu-id="46c6d-141">Type or select a value to pass for the named parameter in the drillthrough report.</span></span> <span data-ttu-id="46c6d-142">Clique no botão **expressão** (*FX*) para editar a expressão.</span><span class="sxs-lookup"><span data-stu-id="46c6d-142">Click the **Expression** (*fx*) button to edit the expression.</span></span>  
  
 <span data-ttu-id="46c6d-143">**Omitir**</span><span class="sxs-lookup"><span data-stu-id="46c6d-143">**Omit**</span></span>  
 <span data-ttu-id="46c6d-144">Selecione para impedir que o parâmetro execute.</span><span class="sxs-lookup"><span data-stu-id="46c6d-144">Select to prevent the parameter from running.</span></span> <span data-ttu-id="46c6d-145">Por padrão, esta caixa de seleção é desmarcada e não ativa.</span><span class="sxs-lookup"><span data-stu-id="46c6d-145">By default, this check box is cleared and not active.</span></span> <span data-ttu-id="46c6d-146">Para marcar a caixa de seleção, clique no botão **expressão** (*FX*) e digite **true** ou crie uma expressão.</span><span class="sxs-lookup"><span data-stu-id="46c6d-146">To select the check box, click the **Expression** (*fx*) button and either type **True** or create an expression.</span></span> <span data-ttu-id="46c6d-147">A caixa de seleção é marcada quando você clica em **OK** na caixa de diálogo **Expressão** .</span><span class="sxs-lookup"><span data-stu-id="46c6d-147">The check box is selected when you click **OK** in the **Expression** dialog box.</span></span>  
  
 <span data-ttu-id="46c6d-148">**Ir para o indicador**</span><span class="sxs-lookup"><span data-stu-id="46c6d-148">**Go to bookmark**</span></span>  
 <span data-ttu-id="46c6d-149">Escolha esta opção para definir um link para um indicador no relatório atual.</span><span class="sxs-lookup"><span data-stu-id="46c6d-149">Choose this option to define a link to a bookmark in the current report.</span></span> <span data-ttu-id="46c6d-150">A opção adicional a seguir aparece quando você seleciona **Ir para o indicador**.</span><span class="sxs-lookup"><span data-stu-id="46c6d-150">The following additional option appears when you select **Go to bookmark**.</span></span>  
  
 <span data-ttu-id="46c6d-151">**Selecione o indicador**</span><span class="sxs-lookup"><span data-stu-id="46c6d-151">**Select bookmark**</span></span>  
 <span data-ttu-id="46c6d-152">Digite ou selecione uma ID de indicador para o relatório passar quando o usuário clicar no link.</span><span class="sxs-lookup"><span data-stu-id="46c6d-152">Type or select the bookmark ID for the report to jump to when the user clicks the link.</span></span> <span data-ttu-id="46c6d-153">Clique no botão expressão (**FX**) para alterar a expressão.</span><span class="sxs-lookup"><span data-stu-id="46c6d-153">Click the Expression (**fx**) button to change the expression.</span></span> <span data-ttu-id="46c6d-154">A ID de indicador pode ser uma ID estática ou uma expressão que seja avaliada por uma ID de indicador.</span><span class="sxs-lookup"><span data-stu-id="46c6d-154">The bookmark ID can be either a static ID or an expression that evaluates to a bookmark ID.</span></span> <span data-ttu-id="46c6d-155">A expressão pode incluir um campo que contenha uma ID de indicador.</span><span class="sxs-lookup"><span data-stu-id="46c6d-155">The expression can include a field that contains a bookmark ID.</span></span>  
  
 <span data-ttu-id="46c6d-156">Para criar um link para um indicador, você deve primeiro definir a propriedade Bookmark de um item de relatório.</span><span class="sxs-lookup"><span data-stu-id="46c6d-156">To link to a bookmark, you must first set the Bookmark property of a report item.</span></span> <span data-ttu-id="46c6d-157">Para definir a propriedade Bookmark, selecione um item de relatório e, no painel Propriedades, digite um valor ou uma expressão para a ID do indicador. Por exemplo, GráficoDeVendas ou 5MaioresVendas.</span><span class="sxs-lookup"><span data-stu-id="46c6d-157">To set the Bookmark property, select a report item, and in the Properties pane, type a value or expression for the bookmark ID; for example, SalesChart or 5TopSales.</span></span>  
  
 <span data-ttu-id="46c6d-158">**Ir para a URL**</span><span class="sxs-lookup"><span data-stu-id="46c6d-158">**Go to URL**</span></span>  
 <span data-ttu-id="46c6d-159">Escolha esta opção para definir um vínculo para uma página da Web.</span><span class="sxs-lookup"><span data-stu-id="46c6d-159">Choose this option to define a link to a Web page.</span></span> <span data-ttu-id="46c6d-160">Digite ou selecione a URL de uma página da Web ou uma expressão que seja avaliada por uma URL de uma página da Web.</span><span class="sxs-lookup"><span data-stu-id="46c6d-160">Type or select the URL of a Web page or an expression that evaluates to the URL of a Web page.</span></span> <span data-ttu-id="46c6d-161">Clique no botão **expressão** (*FX*) para alterar a expressão.</span><span class="sxs-lookup"><span data-stu-id="46c6d-161">Click the **Expression** (*fx*) button to change the expression.</span></span> <span data-ttu-id="46c6d-162">Essa expressão pode conter um campo com uma URL.</span><span class="sxs-lookup"><span data-stu-id="46c6d-162">This expression can include a field that contains a URL.</span></span> <span data-ttu-id="46c6d-163">A opção adicional a seguir aparece quando você seleciona **Ir para a URL**.</span><span class="sxs-lookup"><span data-stu-id="46c6d-163">The following additional option appears when you select **Go to URL**.</span></span>  
  
 <span data-ttu-id="46c6d-164">**Selecionar a URL**</span><span class="sxs-lookup"><span data-stu-id="46c6d-164">**Select URL**</span></span>  
 <span data-ttu-id="46c6d-165">Digite ou insira a URL do item.</span><span class="sxs-lookup"><span data-stu-id="46c6d-165">Type or enter the URL of the item.</span></span> <span data-ttu-id="46c6d-166">Para um item publicado em um servidor de relatórios configurado para o modo nativo, use um caminho completo ou relativo.</span><span class="sxs-lookup"><span data-stu-id="46c6d-166">For an item published to a report server configured for native mode, use a full or relative path.</span></span> <span data-ttu-id="46c6d-167">Por exemplo, http:// *\<servername>* /images/image1.jpg.</span><span class="sxs-lookup"><span data-stu-id="46c6d-167">For example, http://*\<servername>*/images/image1.jpg.</span></span> <span data-ttu-id="46c6d-168">Para um item publicado em um servidor de relatório configurado no modo integrado do SharePoint, use uma URL totalmente qualificada (por exemplo, http:// *\<SharePointservername>/\<site>* /Documents/images/image1.jpg).</span><span class="sxs-lookup"><span data-stu-id="46c6d-168">For an item published to a report server configured in SharePoint integrated mode, use a fully qualified URL (for example, http://*\<SharePointservername>/\<site>*/Documents/images/image1.jpg).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46c6d-169">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="46c6d-169">See Also</span></span>  
 <span data-ttu-id="46c6d-170">[Gráficos &#40;Construtor de Relatórios e SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="46c6d-170">[Charts &#40;Report Builder and SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="46c6d-171">[Construtor de Relatórios ajuda para caixas de diálogo, painéis e assistentes](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="46c6d-171">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="46c6d-172">[Parâmetros de relatório &#40;Construtor de Relatórios e Report Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="46c6d-172">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="46c6d-173">[Adicionar um sub-relatório e parâmetros &#40;Construtor de Relatórios e SSRS&#41;](report-design/add-a-subreport-and-parameters-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="46c6d-173">[Add a Subreport and Parameters &#40;Report Builder and SSRS&#41;](report-design/add-a-subreport-and-parameters-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="46c6d-174">Classificação interativa, mapas de documentos e links &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="46c6d-174">Interactive Sort, Document Maps, and Links &#40;Report Builder and SSRS&#41;</span></span>](report-design/interactive-sort-document-maps-and-links-report-builder-and-ssrs.md)  
  
  
