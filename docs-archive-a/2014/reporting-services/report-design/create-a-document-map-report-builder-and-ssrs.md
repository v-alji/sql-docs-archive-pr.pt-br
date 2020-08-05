---
title: Criar um mapa do documento (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c200a97b-67f2-499f-8374-3ed1ebe3f33c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a9dad0f8e6ee1d9b9ada44fda0eec5908f27cfcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572444"
---
# <a name="create-a-document-map-report-builder-and-ssrs"></a><span data-ttu-id="812e3-102">Criar um mapa de documentos (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="812e3-102">Create a Document Map (Report Builder and SSRS)</span></span>
  <span data-ttu-id="812e3-103">O mapa do documento fornece um conjunto de links de navegação aos itens de relatório em um relatório renderizado.</span><span class="sxs-lookup"><span data-stu-id="812e3-103">A document map provides a set of navigational links to report items in a rendered report.</span></span> <span data-ttu-id="812e3-104">Ao exibir um relatório que inclui um mapa do documento, um painel lateral separado é exibido ao lado do relatório.</span><span class="sxs-lookup"><span data-stu-id="812e3-104">When you view a report that includes a document map, a separate side pane appears next to the report.</span></span> <span data-ttu-id="812e3-105">Um usuário pode clicar nos links do mapa do documento para ir para a página de relatório que exibe esse item.</span><span class="sxs-lookup"><span data-stu-id="812e3-105">A user can click links in the document map to jump to the report page that displays that item.</span></span> <span data-ttu-id="812e3-106">Seções e grupos de relatórios são organizados em uma hierarquia de links.</span><span class="sxs-lookup"><span data-stu-id="812e3-106">Report sections and groups are arranged in a hierarchy of links.</span></span> <span data-ttu-id="812e3-107">Clicar nos itens do mapa do documento atualiza o relatório e exibe a área do relatório que corresponde ao item no mapa do documento.</span><span class="sxs-lookup"><span data-stu-id="812e3-107">Clicking items in the document map refreshes the report and displays the area of the report that corresponds to the item in the document map.</span></span>  
  
 <span data-ttu-id="812e3-108">Para adicionar links ao mapa do documento, defina a propriedade `DocumentMapLabel` do item de relatório para o texto que você criar ou para uma expressão que seja avaliada como o texto que você deseja exibir no mapa do documento.</span><span class="sxs-lookup"><span data-stu-id="812e3-108">To add links to the document map, you set the `DocumentMapLabel` property of the report item to text that you create or to an expression that evaluates to the text that you want display in the document map.</span></span> <span data-ttu-id="812e3-109">Você também pode adicionar valores exclusivos ao grupo de tabelas ou matrizes para o mapa do documento.</span><span class="sxs-lookup"><span data-stu-id="812e3-109">You can also add the unique values for a table or matrix group to the document map.</span></span> <span data-ttu-id="812e3-110">Por exemplo, para um grupo com base em cores, cada cor exclusiva tem um link que o direciona para a página do relatório que exibe a instância de grupo daquela cor.</span><span class="sxs-lookup"><span data-stu-id="812e3-110">For example, for a group based on color, each unique color is a link to the report page that displays the group instance for that color.</span></span>  
  
 <span data-ttu-id="812e3-111">Também é possível criar uma URL para um relatório que substitui a exibição do mapa do documento, portanto, você poderá executar o relatório sem exibir o mapa do documento e clicar no botão **Mostrar/Ocultar Mapa do Documento** na barra de ferramentas do visualizador de relatórios para alternar a exibição.</span><span class="sxs-lookup"><span data-stu-id="812e3-111">You can also create a URL to a report that overrides the display of the document map, so that you can run the report without displaying the document map, and then click the **Show/Hide Document Map** button on the report viewer toolbar to toggle the display.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="document-maps-and-rendering-extensions"></a><a name="DocMapRenderExtensions"></a> <span data-ttu-id="812e3-112">Mapas do documento e extensões de renderização</span><span class="sxs-lookup"><span data-stu-id="812e3-112">Document Maps and Rendering Extensions</span></span>  
 <span data-ttu-id="812e3-113">O mapa do documento é planejado para uso na extensão de renderização HTML, por exemplo, na Versão prévia e no Visualizador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="812e3-113">The document map is intended for use in the HTML rendering extension-for example, in Preview and the Report Viewer.</span></span> <span data-ttu-id="812e3-114">Outras extensões de renderização têm maneiras diferentes de articular um mapa do documento:</span><span class="sxs-lookup"><span data-stu-id="812e3-114">Other rendering extensions have different ways of articulating a document map:</span></span>  
  
-   <span data-ttu-id="812e3-115">O PDF renderiza o mapa do documento como painel de Indicações.</span><span class="sxs-lookup"><span data-stu-id="812e3-115">PDF renders a document map as the Bookmarks pane.</span></span>  
  
-   <span data-ttu-id="812e3-116">O Excel renderiza um mapa do documento como uma planilha nomeada que inclui uma hierarquia de links.</span><span class="sxs-lookup"><span data-stu-id="812e3-116">Excel renders a document map as a named worksheet that includes a hierarchy of links.</span></span> <span data-ttu-id="812e3-117">As seções de relatórios são renderizadas em planilhas separadas incluídas com o mapa do documento na mesma pasta de trabalho.</span><span class="sxs-lookup"><span data-stu-id="812e3-117">Report sections are rendered in separate worksheets that are included with the document map in the same workbook.</span></span>  
  
-   <span data-ttu-id="812e3-118">O Word inclui um mapa do documento como o sumário.</span><span class="sxs-lookup"><span data-stu-id="812e3-118">Word includes a document map as the table of contents.</span></span>  
  
-   <span data-ttu-id="812e3-119">Atom, TIFF, XML e CSV ignoram os mapas dos documentos.</span><span class="sxs-lookup"><span data-stu-id="812e3-119">Atom, TIFF, XML, and CSV ignore document maps.</span></span>  
  
 <span data-ttu-id="812e3-120">Para obter mais informações, consulte [Funcionalidade interativa para extensões de renderização de relatório diferentes &#40;Construtor de Relatórios e SSRS&#41;](../report-builder/interactive-functionality-different-report-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="812e3-120">For more information, see [Interactive Functionality for Different Report Rendering Extensions &#40;Report Builder and SSRS&#41;](../report-builder/interactive-functionality-different-report-rendering-extensions.md).</span></span>  
  
##  <a name="AddRptItemToMap"></a>   
#### <a name="to-add-a-report-item-to-a-document-map"></a><span data-ttu-id="812e3-121">Para adicionar um item de relatório a um mapa do documento</span><span class="sxs-lookup"><span data-stu-id="812e3-121">To add a report item to a document map</span></span>  
  
1.  <span data-ttu-id="812e3-122">No modo de exibição Design, selecione o item de relatório (por exemplo, tabela, matriz ou medidor) que você deseja adicionar ao mapa do documento.</span><span class="sxs-lookup"><span data-stu-id="812e3-122">In Design view, select the report item such as a table, matrix, or gauge that you want to add to the document map.</span></span> <span data-ttu-id="812e3-123">As propriedades do item de relatório aparecem no painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="812e3-123">The report item properties appear in the Properties pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="812e3-124">Para selecionar uma região de dados tablix, clique em uma célula para exibir as alças de linha e coluna e, em seguida, clique na alça de canto.</span><span class="sxs-lookup"><span data-stu-id="812e3-124">To select a tablix data region, click in any cell to display the row and column handles, and then click the corner handle.</span></span>  
  
2.  <span data-ttu-id="812e3-125">No painel Propriedades, digite o texto que você deseja que apareça no mapa do documento na `DocumentMapLabel` propriedade ou insira uma expressão que seja avaliada como um rótulo.</span><span class="sxs-lookup"><span data-stu-id="812e3-125">In the Properties pane, type the text that you want to appear in the document map in the `DocumentMapLabel` property, or enter an expression that evaluates to a label.</span></span> <span data-ttu-id="812e3-126">Por exemplo, digite **Gráfico de Vendas**.</span><span class="sxs-lookup"><span data-stu-id="812e3-126">For example, type **Sales Chart**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="812e3-127">Se você não vir o painel Propriedades, na guia **Exibir** , no grupo **Mostrar/Ocultar** , clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="812e3-127">If you do not see the Properties pane, on the **View** tab, in the **Show/Hide** group, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="812e3-128">Repita as etapas 1 e 2 para cada item de relatório que você deseja exibir no mapa do documento.</span><span class="sxs-lookup"><span data-stu-id="812e3-128">Repeat steps 1 and 2 for every report item that you want to appear in the document map.</span></span>  
  
4.  <span data-ttu-id="812e3-129">Clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="812e3-129">Click **Run**.</span></span> <span data-ttu-id="812e3-130">O relatório é executado e o mapa do documento exibe os rótulos criados.</span><span class="sxs-lookup"><span data-stu-id="812e3-130">The report runs and the document map displays the labels you created.</span></span> <span data-ttu-id="812e3-131">Clique em qualquer link para ir para a página do relatório relacionada ao item.</span><span class="sxs-lookup"><span data-stu-id="812e3-131">Click any link to jump to the report page with that item.</span></span>  
  
 
  
##  <a name="AddUniqueValuesToMap"></a>   
#### <a name="to-add-unique-group-values-to-a-document-map"></a><span data-ttu-id="812e3-132">Para adicionar valores de grupo exclusivos a um mapa do documento</span><span class="sxs-lookup"><span data-stu-id="812e3-132">To add unique group values to a document map</span></span>  
  
1.  <span data-ttu-id="812e3-133">Na exibição Design, selecione a tabela, matriz ou lista que contém o grupo que você deseja exibir no mapa do documento.</span><span class="sxs-lookup"><span data-stu-id="812e3-133">In Design view, select the table, matrix, or list that contains the group that you want to display in the document map.</span></span> <span data-ttu-id="812e3-134">O painel Agrupamento exibe os grupos de linhas e colunas.</span><span class="sxs-lookup"><span data-stu-id="812e3-134">The Grouping pane displays the row and column groups.</span></span>  
  
2.  <span data-ttu-id="812e3-135">No painel Grupos de Linhas, clique com o botão direito do mouse no grupo e escolha **Editar Grupo**.</span><span class="sxs-lookup"><span data-stu-id="812e3-135">In the Row Groups pane, right-click the group, and then click **Edit Group**.</span></span> <span data-ttu-id="812e3-136">A página **Geral** da caixa de diálogo **Propriedades do Grupo Tablix** é aberta.</span><span class="sxs-lookup"><span data-stu-id="812e3-136">The **General** page of the **Tablix Group Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="812e3-137">Clique em **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="812e3-137">Click **Advanced**.</span></span>  
  
4.  <span data-ttu-id="812e3-138">Na caixa de lista **Mapa do Documento** , digite ou selecione uma expressão que corresponda à expressão do grupo.</span><span class="sxs-lookup"><span data-stu-id="812e3-138">In the **Document map** list box, type or select an expression that matches the group expression.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="812e3-139">Repita as etapas 1 a 4 para cada grupo que você deseja exibir no mapa do documento.</span><span class="sxs-lookup"><span data-stu-id="812e3-139">Repeat steps 1-4 for every group that you want to appear in the document map.</span></span>  
  
7.  <span data-ttu-id="812e3-140">Clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="812e3-140">Click **Run**.</span></span> <span data-ttu-id="812e3-141">O relatório é executado e o mapa do documento exibe os valores do grupo.</span><span class="sxs-lookup"><span data-stu-id="812e3-141">The report runs and the document map displays the group values.</span></span> <span data-ttu-id="812e3-142">Clique em qualquer link para ir para a página do relatório relacionada ao item.</span><span class="sxs-lookup"><span data-stu-id="812e3-142">Click any link to jump to the report page with that item.</span></span>  
  
 
  
##  <a name="HideMapWhenViewRpt"></a>   
#### <a name="to-hide-the-document-map-when-you-view-a-report"></a><span data-ttu-id="812e3-143">Para ocultar o mapa do documento quando exibir um relatório</span><span class="sxs-lookup"><span data-stu-id="812e3-143">To hide the document map when you view a report</span></span>  
  
1.  <span data-ttu-id="812e3-144">No Gerenciador de Relatórios, navegue até o relatório que contém o mapa do documento.</span><span class="sxs-lookup"><span data-stu-id="812e3-144">In Report Manager, browse to the report that has the document map.</span></span>  
  
     <span data-ttu-id="812e3-145">Por exemplo, para os relatórios de exemplo em [!INCLUDE[ssSampleDBUserInputNonLocal](../../includes/sssampledbuserinputnonlocal-md.md)] , a URL a seguir especifica o relatório chamado Catálogo de Produtos.</span><span class="sxs-lookup"><span data-stu-id="812e3-145">For example, for the [!INCLUDE[ssSampleDBUserInputNonLocal](../../includes/sssampledbuserinputnonlocal-md.md)] sample reports, the following URL specifies the report named Product Catalog.</span></span>  
  
    ```  
    http://localhost/Reports/Pages/Report.aspx?ItemPath=%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog  
    ```  
  
2.  <span data-ttu-id="812e3-146">Copie o caminho do relatório no servidor.</span><span class="sxs-lookup"><span data-stu-id="812e3-146">Copy the report path on the server.</span></span> <span data-ttu-id="812e3-147">No exemplo, o caminho do relatório é `%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog`.</span><span class="sxs-lookup"><span data-stu-id="812e3-147">In the example, the report path is `%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog`.</span></span>  
  
3.  <span data-ttu-id="812e3-148">Crie uma nova URL com os três componentes a seguir:</span><span class="sxs-lookup"><span data-stu-id="812e3-148">Create a new URL with the following three components:</span></span>  
  
    -   <span data-ttu-id="812e3-149">O visualizador de relatórios no servidor de relatórios: `http://localhost/ReportServer/Pages/ReportViewer.aspx?`</span><span class="sxs-lookup"><span data-stu-id="812e3-149">The report viewer on the report server: `http://localhost/ReportServer/Pages/ReportViewer.aspx?`</span></span>  
  
    -   <span data-ttu-id="812e3-150">O nome do relatório que você copiou na etapa 1, por exemplo: `%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog`</span><span class="sxs-lookup"><span data-stu-id="812e3-150">The name of the report you copied in step 1, for example: `%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog`</span></span>  
  
    -   <span data-ttu-id="812e3-151">Os parâmetros de informação do dispositivo que especificam se o mapa do documento será ocultado: `&rs%3aCommand=Render&rc%3aFormat=HTML4.0&rc%3aDocMap=False`</span><span class="sxs-lookup"><span data-stu-id="812e3-151">The device information parameters that specify hiding the document map: `&rs%3aCommand=Render&rc%3aFormat=HTML4.0&rc%3aDocMap=False`</span></span>  
  
     <span data-ttu-id="812e3-152">A URL a seguir é composta por esses três componentes anexos na ordem em que foram listados.</span><span class="sxs-lookup"><span data-stu-id="812e3-152">The following URL consists of these three components appended in the order they are listed.</span></span>  
  
    ```  
    http://localhost/ReportServer/Pages/ReportViewer.aspx?  
    %2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog  
    &rs%3aCommand=Render&rc%3aFormat=HTML4.0&rc%3aDocMap=False  
    ```  
  
     <span data-ttu-id="812e3-153">Para usar essa URL, copie-a e remova todas as quebras de linha.</span><span class="sxs-lookup"><span data-stu-id="812e3-153">To use this URL, copy it and remove all line breaks.</span></span>  
  
4.  <span data-ttu-id="812e3-154">Cole a URL no Gerenciador de Relatórios e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="812e3-154">Paste the URL in Report Manager, and then press ENTER.</span></span> <span data-ttu-id="812e3-155">O relatório será executado e o mapa do documento será ocultado.</span><span class="sxs-lookup"><span data-stu-id="812e3-155">The report runs, and the document map is hidden.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="812e3-156">Para obter mais informações sobre como baixar relatórios de exemplo, consulte [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [Construtor de Relatórios e Report Designer relatórios de exemplo](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="812e3-156">For more information about downloading sample reports, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
>   
>  <span data-ttu-id="812e3-157">Para obter mais informações, consulte “Acesso à URL” na [documentação do Reporting Services](https://go.microsoft.com/fwlink/?linkid=121312) nos Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="812e3-157">For more information, see "URL Access" in the [Reporting Services documentation](https://go.microsoft.com/fwlink/?linkid=121312) in SQL Server Books Online.</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="812e3-158">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="812e3-158">See Also</span></span>  
 [<span data-ttu-id="812e3-159">Localizando e exibindo relatórios no Gerenciador de Relatórios &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="812e3-159">Finding and Viewing Reports in Report Manager &#40;Report Builder and SSRS&#41;</span></span>](../report-builder/finding-and-viewing-reports-in-the-web-portal-report-builder-and-ssrs.md)  
  
  
