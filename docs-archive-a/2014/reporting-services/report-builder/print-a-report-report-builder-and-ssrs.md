---
title: Imprimir um relatório (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b96936c9-c387-41a9-8c19-6eb325769ffd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fe029019cdf9739153256db399cfa1426d3ba632
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571834"
---
# <a name="print-a-report-report-builder-and-ssrs"></a><span data-ttu-id="91f68-102">Imprimir um relatório (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="91f68-102">Print a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="91f68-103">Depois de salvar um relatório em um servidor de relatório, você pode exibir e imprimir o relatório de um navegador, do Gerenciador de Relatórios ou qualquer aplicativo usado para exibir um relatório exportado.</span><span class="sxs-lookup"><span data-stu-id="91f68-103">After you save a report to a report server, you can view and print the report from a browser, Report Manager, or any application that you use to view an exported report.</span></span> <span data-ttu-id="91f68-104">Antes de salvar um relatório, você pode imprimi-lo quando o visualiza.</span><span class="sxs-lookup"><span data-stu-id="91f68-104">Before saving a report, you can print it when you preview it.</span></span>  
  
 <span data-ttu-id="91f68-105">Quando você imprime um relatório, pode especificar o tamanho do papel a ser usado.</span><span class="sxs-lookup"><span data-stu-id="91f68-105">When you print a report, you can specify the size of the paper to use.</span></span> <span data-ttu-id="91f68-106">O tamanho do papel determina o número de páginas em um relatório e quais dados do relatório se ajustam em cada página.</span><span class="sxs-lookup"><span data-stu-id="91f68-106">The size of the paper determines the number of pages in a report and which report data fits on each page.</span></span> <span data-ttu-id="91f68-107">O tamanho do papel afeta somente relatórios renderizados com processadores de quebra de página não flexíveis: PDF, Imagem e Impressão.</span><span class="sxs-lookup"><span data-stu-id="91f68-107">Paper size affects only reports that are rendered with hard page-break renders: PDF, Image, and Print.</span></span> <span data-ttu-id="91f68-108">A definição do tamanho do papel não tem efeito sobre outros processadores.</span><span class="sxs-lookup"><span data-stu-id="91f68-108">Setting the paper size has no effect on other renderers.</span></span> <span data-ttu-id="91f68-109">Para obter mais informações, consulte [Comportamentos de renderização &#40;Construtor de Relatórios e SSRS&#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="91f68-109">For more information, see [Rendering Behaviors &#40;Report Builder  and SSRS&#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="91f68-110">Na barra de ferramentas do visualizador de relatórios no Gerenciador de Relatórios ou na visualização no Construtor de Relatórios, você pode exportar um relatório para um renderizador de quebra de página não flexível ou clicar no botão Imprimir para imprimir uma cópia do relatório.</span><span class="sxs-lookup"><span data-stu-id="91f68-110">From the report viewer toolbar in Report Manager or in preview in Report Builder, you can export a report to a hard page-break renderer or click the Print button to print a copy of the report.</span></span> <span data-ttu-id="91f68-111">Talvez você precise definir o tamanho do papel ou outras propriedades de configuração de página.</span><span class="sxs-lookup"><span data-stu-id="91f68-111">You might need to set the paper size or other page setup properties.</span></span> <span data-ttu-id="91f68-112">Use a caixa de diálogo **Propriedades do Relatório** para alterar as propriedades de configuração de página, inclusive o tamanho do papel.</span><span class="sxs-lookup"><span data-stu-id="91f68-112">Use the **Report Properties** dialog box to change page setup properties, including paper size.</span></span>  
  
 <span data-ttu-id="91f68-113">Você pode especificar margens de página de impressão em dois locais diferentes: em modo de design e em modo de execução.</span><span class="sxs-lookup"><span data-stu-id="91f68-113">You can specify print page margins in two different locations: in design mode and in run mode.</span></span>  
  
-   <span data-ttu-id="91f68-114">**Modo Design.**</span><span class="sxs-lookup"><span data-stu-id="91f68-114">**Design mode.**</span></span> <span data-ttu-id="91f68-115">Quando você define as margens da página em modo de design, essas configurações são salvas na definição do relatório quando o relatório é salvo.</span><span class="sxs-lookup"><span data-stu-id="91f68-115">When you set page margins in design mode, these settings are saved in the report definition when you save the report.</span></span>  
  
-   <span data-ttu-id="91f68-116">**Modo de execução.**</span><span class="sxs-lookup"><span data-stu-id="91f68-116">**Run mode.**</span></span> <span data-ttu-id="91f68-117">Quando você define as margens da página em modo de execução, essas informações não são salvas na definição do relatório.</span><span class="sxs-lookup"><span data-stu-id="91f68-117">When you set page margins in run mode, this information is not saved in the report definition.</span></span> <span data-ttu-id="91f68-118">Na próxima vez que imprimir o relatório, você obterá as configurações da definição do relatório, a menos que você indique as margens de impressão novamente.</span><span class="sxs-lookup"><span data-stu-id="91f68-118">The next time you print the report, you will get the settings from the report definition, unless you indicate your print margins again.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="91f68-119">As margens de impressão não são exibidas nos modos de design ou de execução.</span><span class="sxs-lookup"><span data-stu-id="91f68-119">Print margins are not displayed in design or run modes.</span></span> <span data-ttu-id="91f68-120">Não há nenhuma relação entre a área da superfície de design e a área de impressão do relatório.</span><span class="sxs-lookup"><span data-stu-id="91f68-120">There is no relationship between the design surface area and the print area of your report.</span></span> <span data-ttu-id="91f68-121">Em ver as margens de impressão, em modo de execução, clique em Layout de Impressão na guia **Executar** na Faixa de Opções.</span><span class="sxs-lookup"><span data-stu-id="91f68-121">To see print margins, in run mode, click Print Layout on the **Run** tab on the Ribbon.</span></span>  
  
 <span data-ttu-id="91f68-122">Para obter mais informações sobre paginação de relatório, consulte [Paginação no Reporting Services &#40;Construtor de Relatórios e SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="91f68-122">For more information about report paging, see [Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-print-a-report-in-report-builder"></a><span data-ttu-id="91f68-123">Para imprimir um relatório no Construtor de Relatórios</span><span class="sxs-lookup"><span data-stu-id="91f68-123">To print a report in Report Builder</span></span>  
  
1.  <span data-ttu-id="91f68-124">Abra um relatório.</span><span class="sxs-lookup"><span data-stu-id="91f68-124">Open a report.</span></span>  
  
2.  <span data-ttu-id="91f68-125">Na guia início, clique em **executar**.</span><span class="sxs-lookup"><span data-stu-id="91f68-125">On the Home tab, click **Run**.</span></span>  
  
3.  <span data-ttu-id="91f68-126">(opcional) Clique em **Layout de Impressão** para saber como o relatório ficará quando for impresso.</span><span class="sxs-lookup"><span data-stu-id="91f68-126">(optional) Click **Print Layout** to see how the report will look when it is printed.</span></span>  
  
4.  <span data-ttu-id="91f68-127">(opcional) Clique em **Configuração de Página** para definir o papel, a orientação e as margens.</span><span class="sxs-lookup"><span data-stu-id="91f68-127">(optional) Click **Page Setup** to set paper, orientation, and margins.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="91f68-128">Os valores padrão provêm das propriedades do relatório, definidas na exibição Design.</span><span class="sxs-lookup"><span data-stu-id="91f68-128">The default values for these come from the report properties, which are set in Design view.</span></span> <span data-ttu-id="91f68-129">Os valores definidos aqui na caixa de diálogo **Configuração de Página** somente são válidos durante esta sessão.</span><span class="sxs-lookup"><span data-stu-id="91f68-129">The values you set here in the **Page Setup** dialog box are for this session only.</span></span> <span data-ttu-id="91f68-130">Quando você fechar este relatório e reabri-lo, ele terá os valores padrão novamente.</span><span class="sxs-lookup"><span data-stu-id="91f68-130">When you close this report and reopen it, it will have the default values again.</span></span>  
  
5.  <span data-ttu-id="91f68-131">Clique em **Imprimir**.</span><span class="sxs-lookup"><span data-stu-id="91f68-131">Click **Print**.</span></span>  
  
6.  <span data-ttu-id="91f68-132">Na caixa de diálogo **Imprimir** , selecione uma impressora e especifique outras opções de impressão.</span><span class="sxs-lookup"><span data-stu-id="91f68-132">In the **Print** dialog box, select a printer and specify other printing options.</span></span>  
  
### <a name="to-print-a-report-from-a-web-browser-application"></a><span data-ttu-id="91f68-133">Para imprimir um relatório em um aplicativo de navegador da Web</span><span class="sxs-lookup"><span data-stu-id="91f68-133">To print a report from a Web browser application</span></span>  
  
1.  <span data-ttu-id="91f68-134">Inicie o [Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="91f68-134">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="91f68-135">No Gerenciador de Relatórios, navegue até o relatório a ser impresso.</span><span class="sxs-lookup"><span data-stu-id="91f68-135">In Report Manager, navigate to the report that you want to print.</span></span> <span data-ttu-id="91f68-136">Abra o relatório.</span><span class="sxs-lookup"><span data-stu-id="91f68-136">Open the report.</span></span>  
  
3.  <span data-ttu-id="91f68-137">Na barra de ferramentas na parte superior do relatório, clique em **Imprimir**.</span><span class="sxs-lookup"><span data-stu-id="91f68-137">On the toolbar at the top of the report, click **Print**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="91f68-138">Na primeira vez que você imprime um relatório HTML, o servidor de relatório solicita que você instale um controle ActiveX usado para impressão.</span><span class="sxs-lookup"><span data-stu-id="91f68-138">The first time you print an HTML report, the report server prompts you to install an ActiveX control used for printing.</span></span> <span data-ttu-id="91f68-139">Você deve instalar e configurar o controle para imprimir.</span><span class="sxs-lookup"><span data-stu-id="91f68-139">You must install and configure the control to print.</span></span>  
  
4.  <span data-ttu-id="91f68-140">Na caixa de diálogo **Imprimir** , selecione uma impressora e clique em **Imprimir**.</span><span class="sxs-lookup"><span data-stu-id="91f68-140">In the **Print** dialog box, select a printer, and then click **Prin**t.</span></span>  
  
### <a name="to-print-a-report-from-other-applications"></a><span data-ttu-id="91f68-141">Para imprimir um relatório em outros aplicativos</span><span class="sxs-lookup"><span data-stu-id="91f68-141">To print a report from other applications</span></span>  
  
1.  <span data-ttu-id="91f68-142">No Gerenciador de Relatórios, navegue até o relatório a ser impresso.</span><span class="sxs-lookup"><span data-stu-id="91f68-142">In Report Manager, navigate to the report that you want to print.</span></span> <span data-ttu-id="91f68-143">Abra o relatório.</span><span class="sxs-lookup"><span data-stu-id="91f68-143">Open the report.</span></span>  
  
2.  <span data-ttu-id="91f68-144">Na barra de ferramentas na parte superior do relatório, selecione um formato de renderização e clique em **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="91f68-144">On the toolbar at the top of the report, select a rendering format, and then click **Export**.</span></span> <span data-ttu-id="91f68-145">O relatório é aberto em um aplicativo de visualizador que corresponde ao formato de renderização.</span><span class="sxs-lookup"><span data-stu-id="91f68-145">The report opens in a viewer application that corresponds to the rendering format.</span></span>  
  
     <span data-ttu-id="91f68-146">Por exemplo, se você selecionar PDF, o relatório será aberto no Adobe Acrobat Reader.</span><span class="sxs-lookup"><span data-stu-id="91f68-146">For example, if you select PDF, the report opens in Adobe Acrobat Reader.</span></span>  
  
3.  <span data-ttu-id="91f68-147">No menu **Arquivo** desse programa, clique em **Imprimir**.</span><span class="sxs-lookup"><span data-stu-id="91f68-147">On the **File** menu in that program, click **Print**.</span></span>  
  
### <a name="to-change-paper-size"></a><span data-ttu-id="91f68-148">Para alterar o tamanho do papel</span><span class="sxs-lookup"><span data-stu-id="91f68-148">To change paper size</span></span>  
  
1.  <span data-ttu-id="91f68-149">Clique com o botão direito do mouse fora do corpo do relatório e clique em **Propriedades do Relatório**.</span><span class="sxs-lookup"><span data-stu-id="91f68-149">Right-click outside of the report body and click **Report Properties**.</span></span>  
  
2.  <span data-ttu-id="91f68-150">Em **Configuração de Página**, selecione um valor na lista **Tamanho do Papel** .</span><span class="sxs-lookup"><span data-stu-id="91f68-150">In **Page Setup**, select a value from the **Paper Size** list.</span></span> <span data-ttu-id="91f68-151">Cada opção preenche as propriedades **Largura** e **Altura** .</span><span class="sxs-lookup"><span data-stu-id="91f68-151">Each option populates the **Width** and **Height** properties.</span></span> <span data-ttu-id="91f68-152">Você também pode especificar um tamanho personalizado, digitando valores numéricos nas caixas **Largura** e **Altura** .</span><span class="sxs-lookup"><span data-stu-id="91f68-152">You can also specify a custom size by typing numeric values in the **Width** and **Height** boxes.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="91f68-153">Os valores de tamanho têm uma unidade padrão com base nas configurações de localidade do usuário.</span><span class="sxs-lookup"><span data-stu-id="91f68-153">Size values have a default unit based on the user's locale settings.</span></span> <span data-ttu-id="91f68-154">Para designar uma unidade diferente, digite um designador de unidade física como cm, mm, pt ou pc depois do valor numérico.</span><span class="sxs-lookup"><span data-stu-id="91f68-154">To designate a different unit, type a physical unit designator such as cm, mm, pt, or pc after the numeric value.</span></span>  
  
### <a name="to-set-page-margins-in-design-mode"></a><span data-ttu-id="91f68-155">Para definir as margens da página em modo de design</span><span class="sxs-lookup"><span data-stu-id="91f68-155">To set page margins in design mode</span></span>  
  
-   <span data-ttu-id="91f68-156">Clique com o botão direito do mouse na área azul ao redor da superfície de design, clique em **Propriedades do Relatório**e clique na página **Configurar Página** .</span><span class="sxs-lookup"><span data-stu-id="91f68-156">Right-click the blue area around the design surface, click **Report Properties**, and then click the **Page Setup** page.</span></span>  
  
### <a name="to-set-page-margins-in-run-mode"></a><span data-ttu-id="91f68-157">Para definir as margens da página em modo de design</span><span class="sxs-lookup"><span data-stu-id="91f68-157">To set page margins in run mode</span></span>  
  
-   <span data-ttu-id="91f68-158">Clique em **Configurar Página** na guia **Executar** .</span><span class="sxs-lookup"><span data-stu-id="91f68-158">Click **Page Setup** on the **Run** tab.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91f68-159">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="91f68-159">See Also</span></span>  
 <span data-ttu-id="91f68-160">[Imprimir relatórios &#40;Construtor de Relatórios e SSRS&#41;](print-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="91f68-160">[Print Reports &#40;Report Builder and SSRS&#41;](print-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="91f68-161">[Exportando relatórios &#40;Construtor de Relatórios e SSRS&#41;](export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="91f68-161">[Exporting Reports &#40;Report Builder and SSRS&#41;](export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="91f68-162">[Caixa de diálogo Propriedades do Relatório, Configuração de Página &#40;Construtor de Relatórios&#41;](../report-properties-dialog-box-page-setup-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="91f68-162">[Report Properties Dialog Box, Page Setup &#40;Report Builder&#41;](../report-properties-dialog-box-page-setup-report-builder.md) </span></span>  
 [<span data-ttu-id="91f68-163">Modo de exibição de Design de relatório &#40;Construtor de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="91f68-163">Report Design View &#40;Report Builder&#41;</span></span>](report-design-view-report-builder.md)  
  
  
