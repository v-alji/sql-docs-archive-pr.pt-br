---
title: Exibir relatórios de Reporting Services em dispositivos Microsoft Surface e dispositivos Apple iOS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- iPad
- Safari
- SSRS
- Report Viewer [Reporting Services]
- iOS
ms.assetid: 2124bcf5-d60a-475f-a4ae-de6df44d2860
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: db52ed500559969ae52eb9477caa6b410889c1d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576208"
---
# <a name="view-reporting-services-reports-on-microsoft-surface-devices-and--apple-ios-devices"></a><span data-ttu-id="78ff4-102">Exibir relatórios do Reporting Services em dispositivos Microsoft Surface e Apple iOS</span><span class="sxs-lookup"><span data-stu-id="78ff4-102">View Reporting Services Reports on Microsoft Surface Devices and  Apple iOS Devices</span></span>
  <span data-ttu-id="78ff4-103">Este artigo descreve os recursos e fluxos de trabalho do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] com suporte par dispositivos Microsoft Surface e dispositivos com Apple iOS 6 e Apple Safari, tal como o iPad.</span><span class="sxs-lookup"><span data-stu-id="78ff4-103">This article describes the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features and workflows supported for Microsoft Surface devices, and devices with Apple iOS 6 and Apple Safari such as the iPad.</span></span>

## <a name="view-and-interact-with-reports"></a><span data-ttu-id="78ff4-104">Exibir e interagir com relatórios</span><span class="sxs-lookup"><span data-stu-id="78ff4-104">View and Interact With Reports</span></span>
 <span data-ttu-id="78ff4-105">A partir do [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)], o [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] oferece suporte à exibição e à interatividade básica com relatórios em dispositivos Microsoft Surface, e em dispositivos com Apple iOS 6 e Apple Safari, como o iPad.</span><span class="sxs-lookup"><span data-stu-id="78ff4-105">Starting with [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)], [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] supports viewing and basic interactivity with reports on Microsoft Surface devices, and devices with Apple iOS 6 and Apple Safari browser such as the iPad.</span></span> <span data-ttu-id="78ff4-106">Você também pode publicar relatórios usando dispositivos Microsoft Surface.</span><span class="sxs-lookup"><span data-stu-id="78ff4-106">You can also publish reports using Microsoft Surface devices.</span></span>

 <span data-ttu-id="78ff4-107">![Área de trabalho do iPad](media/videothumbnail.jpg "Área de trabalho de IPad") Assista a uma demonstração de exibição de relatórios em um iPad.</span><span class="sxs-lookup"><span data-stu-id="78ff4-107">![IPad Desktop](media/videothumbnail.jpg "IPad Desktop") Watch a demonstration of viewing reports on an iPad.</span></span>

 <span data-ttu-id="78ff4-108">Você também pode exibir relatórios do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] em um dispositivo Windows Phone 8.</span><span class="sxs-lookup"><span data-stu-id="78ff4-108">You can also view [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports on a Windows Phone 8 device.</span></span>

 <span data-ttu-id="78ff4-109">Para usar os recursos descritos neste tópico, instale um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="78ff4-109">To utilize the features described in this topic, install one of the following:</span></span>

-   <span data-ttu-id="78ff4-110">Para um servidor de relatório de modo nativo, instale o [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)] ou posterior.</span><span class="sxs-lookup"><span data-stu-id="78ff4-110">For a native mode report server, install [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)] or later.</span></span>

     [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)]<span data-ttu-id="78ff4-111">está disponível para download no [centro de download da Microsoft](https://www.microsoft.com/download/details.aspx?id=35575).</span><span class="sxs-lookup"><span data-stu-id="78ff4-111">is available for download from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=35575).</span></span>

-   <span data-ttu-id="78ff4-112">Para um servidor de relatório do modo do SharePoint, instale o [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)] ou posterior do suplemento [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] para produtos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="78ff4-112">For a SharePoint mode report server, install [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)] or later of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] add-in for SharePoint products.</span></span>

 <span data-ttu-id="78ff4-113">**Para exibir e interagir com um relatório no dispositivo iPad ou Microsoft Surface**</span><span class="sxs-lookup"><span data-stu-id="78ff4-113">**To view and interact with a report on an iPad device or Microsoft Surface device**</span></span>

1.  <span data-ttu-id="78ff4-114">Você deve ser capaz de se conectar ao servidor de relatório ou ao site do SharePoint onde o relatório reside.</span><span class="sxs-lookup"><span data-stu-id="78ff4-114">Make sure that you can connect to the report server or SharePoint site where the report resides.</span></span>

2.  <span data-ttu-id="78ff4-115">Abra o relatório seguindo um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="78ff4-115">Open the report by doing one of the following.</span></span>

    -   <span data-ttu-id="78ff4-116">**Início no email:** em um email criado por uma assinatura do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , toque na URL do relatório.</span><span class="sxs-lookup"><span data-stu-id="78ff4-116">**Start from e-mail:** From an e-mail that is created by a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] subscription, tap the URL of the report.</span></span> <span data-ttu-id="78ff4-117">O relatório será aberto no navegador.</span><span class="sxs-lookup"><span data-stu-id="78ff4-117">The report will open in the browser.</span></span>

    -   <span data-ttu-id="78ff4-118">**Início a partir do servidor de relatório:** procure o diretório no servidor de relatório do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] e toque no nome do relatório para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="78ff4-118">**Start from Report Server:** Browse the directory on the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report server, and then tap the report name to open the report.</span></span>

    -   <span data-ttu-id="78ff4-119">**Início a partir de uma biblioteca de documentos do SharePoint:** navegue até uma biblioteca de documentos do SharePoint que contenha relatórios do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] e toque no nome do relatório.</span><span class="sxs-lookup"><span data-stu-id="78ff4-119">**Start from a SharePoint document library:** Browse to a SharePoint document library that contains [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports, and then tap the report name.</span></span> <span data-ttu-id="78ff4-120">Você pode exibir e interagir com o relatório.</span><span class="sxs-lookup"><span data-stu-id="78ff4-120">You can view and interact with the report.</span></span>

        > [!IMPORTANT]
        >  <span data-ttu-id="78ff4-121">Para o iPad, certifique-se de que a propriedade de **Navegação Particular** para Safari esteja desativada.</span><span class="sxs-lookup"><span data-stu-id="78ff4-121">For the iPad, ensure that the **Private Browsing** property for Safari is turned off.</span></span>

    -   <span data-ttu-id="78ff4-122">**Web parts de SharePoint:** se a Web Part foi adicionada a uma página do SharePoint, você pode exibir relatórios do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="78ff4-122">**SharePoint web part:** If the web part has been added to a SharePoint page, you can view [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports.</span></span>

3.  <span data-ttu-id="78ff4-123">No dispositivo Microsoft Surface, você também pode abrir o relatório usando o Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="78ff4-123">On your Microsoft Surface device, you can also open the report by using Report Manager.</span></span> <span data-ttu-id="78ff4-124">Procure o diretório no Gerenciador de Relatórios do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] e toque no nome do relatório para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="78ff4-124">Browse the directory in [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Report Manager, and then tap the report name to open the report.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="78ff4-125">Não há suporte à exibição de relatórios no Gerenciador de Relatórios em um iPad.</span><span class="sxs-lookup"><span data-stu-id="78ff4-125">Viewing reports in Report Manager is not supported on an iPad.</span></span>

4.  <span data-ttu-id="78ff4-126">Role e aplique zoom fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="78ff4-126">Scroll and zoom by doing the following.</span></span>

    -   <span data-ttu-id="78ff4-127">Para rolar o relatório, arraste seu dedo na tela (para cima, para baixo, para a esquerda ou para a direita).</span><span class="sxs-lookup"><span data-stu-id="78ff4-127">To scroll the report, drag your finger across the screen (up, down, left or right).</span></span> <span data-ttu-id="78ff4-128">Este é o gesto de passar o dedo.</span><span class="sxs-lookup"><span data-stu-id="78ff4-128">This is the swipe gesture.</span></span>

    -   <span data-ttu-id="78ff4-129">Para ampliar, coloque dois dedos na tela e separe-os.</span><span class="sxs-lookup"><span data-stu-id="78ff4-129">To zoom in, place two fingers on the screen and separate the fingers.</span></span> <span data-ttu-id="78ff4-130">Para reduzir, coloque dois dedos na tela e aproxime-os.</span><span class="sxs-lookup"><span data-stu-id="78ff4-130">To zoom out, place two fingers on the screen and move the fingers together.</span></span> <span data-ttu-id="78ff4-131">Este é o gesto de pinçagem.</span><span class="sxs-lookup"><span data-stu-id="78ff4-131">This is the pinch gesture.</span></span>

5.  <span data-ttu-id="78ff4-132">Navegue e interaja com o relatório fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="78ff4-132">Navigate and interact with the report by doing the following.</span></span>

    -   <span data-ttu-id="78ff4-133">Reduza e expanda itens de relatório e as linhas e colunas associadas a grupos tocando em (+) para reduzir e (-) para expandir.</span><span class="sxs-lookup"><span data-stu-id="78ff4-133">Collapse and expand report items, and rows and columns that are associated with groups, by taping the plus (+) sign to collapse and the minus (-) sign to expand.</span></span>

    -   <span data-ttu-id="78ff4-134">Alterne entres as ordens crescente e decrescente para linhas de uma tabela ou para linhas e colunas de uma matriz tocando no botão de classificação.</span><span class="sxs-lookup"><span data-stu-id="78ff4-134">Toggle between ascending and descending order for rows in a table or for rows and columns in a matrix, by tapping the sort button.</span></span> <span data-ttu-id="78ff4-135">O botão de classificação geralmente é posicionado no cabeçalho da coluna.</span><span class="sxs-lookup"><span data-stu-id="78ff4-135">The sort button is usually located in the column header.</span></span>

    -   <span data-ttu-id="78ff4-136">Expanda e reduza o painel do parâmetro tocando no botão de seta próximo à parte superior do relatório.</span><span class="sxs-lookup"><span data-stu-id="78ff4-136">Expand and collapse the parameter pane, by tapping the arrow button near the top of the report.</span></span>

    -   <span data-ttu-id="78ff4-137">Selecione um valor de parâmetro tocando na caixa ou no controle ao lado do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="78ff4-137">Select a parameter value by tapping the box or control next to the parameter.</span></span> <span data-ttu-id="78ff4-138">Clique em **Exibir Relatório** para aplicar o valor do parâmetro ao relatório.</span><span class="sxs-lookup"><span data-stu-id="78ff4-138">Tap **View Report** to apply the parameter value to the report.</span></span>

    -   <span data-ttu-id="78ff4-139">Pesquise o conteúdo do relatório clicando na caixa ao lado de **Localizar**, digitando um termo de pesquisa e clicando em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="78ff4-139">Search the report content by taping the box next to **Find**, typing a search term, and then taping **Find**.</span></span>

    -   <span data-ttu-id="78ff4-140">Navegue pelas páginas do relatório clicando nos botões de navegação ou na caixa de texto ao lado dos botões e digitando o número da página.</span><span class="sxs-lookup"><span data-stu-id="78ff4-140">Navigate the report pages by tapping the navigation buttons, or tapping the text box next to the buttons and typing the page number.</span></span>

    -   <span data-ttu-id="78ff4-141">Navegue até as URLs clicando nos hiperlinks que foram adicionados aos itens de relatório, como caixas de texto, imagens, gráficos e medidores.</span><span class="sxs-lookup"><span data-stu-id="78ff4-141">Navigate to URLs by taping hyperlinks that have been added to report items such as text boxes, images, charts, and gauges.</span></span>

    -   <span data-ttu-id="78ff4-142">Exporte o relatório tocando no ícone do **Menu suspenso Exportar** e toque em um formato de arquivo.</span><span class="sxs-lookup"><span data-stu-id="78ff4-142">Export the report by tapping the icon for the **Export drop down menu** and then tapping a file format.</span></span>

        -   <span data-ttu-id="78ff4-143">Se você estiver exibindo o relatório em um dispositivo Microsoft Surface, poderá exportar o relatório para um dos formatos a seguir.</span><span class="sxs-lookup"><span data-stu-id="78ff4-143">If you're viewing the report on a Microsoft Surface device, you can export the report to one of the following formats.</span></span>

            -   <span data-ttu-id="78ff4-144">Arquivo XML com dados de relatório</span><span class="sxs-lookup"><span data-stu-id="78ff4-144">XML file with report data</span></span>

            -   <span data-ttu-id="78ff4-145">CSV (delimitado por vírgulas)</span><span class="sxs-lookup"><span data-stu-id="78ff4-145">CSV (comma delimited)</span></span>

            -   <span data-ttu-id="78ff4-146">PDF</span><span class="sxs-lookup"><span data-stu-id="78ff4-146">PDF</span></span>

            -   <span data-ttu-id="78ff4-147">MHTML (arquivo da Web)</span><span class="sxs-lookup"><span data-stu-id="78ff4-147">MHTML (web archive)</span></span>

            -   <span data-ttu-id="78ff4-148">Excel</span><span class="sxs-lookup"><span data-stu-id="78ff4-148">Excel</span></span>

            -   <span data-ttu-id="78ff4-149">TIFF</span><span class="sxs-lookup"><span data-stu-id="78ff4-149">TIFF</span></span>

            -   <span data-ttu-id="78ff4-150">Word</span><span class="sxs-lookup"><span data-stu-id="78ff4-150">Word</span></span>

        -   <span data-ttu-id="78ff4-151">Se você estiver exibindo o relatório em um iPad, poderá exportar o relatório como um arquivo TIFF ou PDF.</span><span class="sxs-lookup"><span data-stu-id="78ff4-151">If you're viewing the report on an iPad, you can export the report as a TIFF or PDF file.</span></span>

## <a name="authentication"></a><span data-ttu-id="78ff4-152">Autenticação</span><span class="sxs-lookup"><span data-stu-id="78ff4-152">Authentication</span></span>
 <span data-ttu-id="78ff4-153">As autenticações RSWindowsNTLM e RSWindowsBasic funcionam apenas com [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] no modo nativo e iPad.</span><span class="sxs-lookup"><span data-stu-id="78ff4-153">RSWindowsNTLM authentication and RSWindowsBasic authentication work with [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in native mode and the iPad.</span></span>

 <span data-ttu-id="78ff4-154">Em geral, é recomendado que RSWindowsBasic não seja usado em ambientes que não são HTTPs porque esse tipo de autenticação não garante a confidencialidade das credenciais transmitidas.</span><span class="sxs-lookup"><span data-stu-id="78ff4-154">In general, it is recommended that RSWindowsBasic is not used in non-https environments because this type of authentication provides no confidentiality for the transmitted credentials.</span></span>

 <span data-ttu-id="78ff4-155">Para obter mais informações sobre RSWindowsNTLM e autenticação RSWindowsBasic, consulte [Authentication with the Report Server](security/authentication-with-the-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="78ff4-155">For more information about RSWindowsNTLM and RSWindowsBasic authentication, see [Authentication with the Report Server](security/authentication-with-the-report-server.md).</span></span>

## <a name="uploading-reports"></a><span data-ttu-id="78ff4-156">Carregando relatórios</span><span class="sxs-lookup"><span data-stu-id="78ff4-156">Uploading Reports</span></span>
 <span data-ttu-id="78ff4-157">Você poderá publicar relatórios de um dispositivo Microsoft Surface usando um dos métodos a seguir, desde que tenha as permissões apropriadas.</span><span class="sxs-lookup"><span data-stu-id="78ff4-157">You can publish reports from a Microsoft Surface device using one of the following methods, if you have the appropriate permissions.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="78ff4-158">Esses métodos não têm suporte no iPad.</span><span class="sxs-lookup"><span data-stu-id="78ff4-158">These methods are not supported on the iPad.</span></span>

-   <span data-ttu-id="78ff4-159">Carregar um arquivo de definição de relatório (.rdl) em uma biblioteca de documentos do SharePoint abrindo a biblioteca e tocando em **Carregar Documento**.</span><span class="sxs-lookup"><span data-stu-id="78ff4-159">Upload a report definition file (.rdl) to a SharePoint document library by opening the library and tapping **Upload Document**.</span></span>

-   <span data-ttu-id="78ff4-160">Carregar um arquivo de definição de relatório no banco de dados do servidor de relatórios abrindo o Gerenciador de Relatórios e tocando em **Carregar Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="78ff4-160">Upload a report definition file to the report server database by opening Report Manager and tapping **Upload File**.</span></span>

## <a name="additional-information"></a><span data-ttu-id="78ff4-161">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="78ff4-161">Additional Information</span></span>
 <span data-ttu-id="78ff4-162">Para obter mais informações sobre o [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] e navegadores com suporte, consulte:</span><span class="sxs-lookup"><span data-stu-id="78ff4-162">For more information on [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] and supported browsers, see:</span></span>

-   [<span data-ttu-id="78ff4-163">Planejamento para Reporting Services e suporte ao navegador de Power View &#40;Reporting Services 2014&#41;</span><span class="sxs-lookup"><span data-stu-id="78ff4-163">Planning for Reporting Services and Power View Browser Support &#40;Reporting Services 2014&#41;</span></span>](../../2014/reporting-services/browser-support-for-reporting-services-and-power-view.md)

 <span data-ttu-id="78ff4-164">Para obter mais informações sobre o Microsoft Business Intelligence e dispositivos móveis, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="78ff4-164">For more information on Microsoft Business Intelligence and Mobile devices, see the following:</span></span>

-   <span data-ttu-id="78ff4-165">[Visão geral de dispositivos móveis e do SharePoint 2013](https://technet.microsoft.com/library/fp161351\(v=office.15\).aspx) ( https://technet.microsoft.com/library/fp161351(v=office.15).aspx) .</span><span class="sxs-lookup"><span data-stu-id="78ff4-165">[Overview of mobile devices and SharePoint 2013](https://technet.microsoft.com/library/fp161351\(v=office.15\).aspx) (https://technet.microsoft.com/library/fp161351(v=office.15).aspx).</span></span>

-   <span data-ttu-id="78ff4-166">[Navegadores de dispositivos móveis com suporte no SharePoint 2013](https://technet.microsoft.com/library/fp161353\(v=office.15\).aspx) ( https://technet.microsoft.com/library/fp161353(v=office.15).aspx) .</span><span class="sxs-lookup"><span data-stu-id="78ff4-166">[Supported mobile device browsers in SharePoint 2013](https://technet.microsoft.com/library/fp161353\(v=office.15\).aspx) (https://technet.microsoft.com/library/fp161353(v=office.15).aspx).</span></span>

-   <span data-ttu-id="78ff4-167">[Exibindo relatórios e scorecards em dispositivos Apple iPad (SharePoint Server 2010)](https://technet.microsoft.com/library/hh697482.aspx) ( https://technet.microsoft.com/library/hh697482.aspx) .</span><span class="sxs-lookup"><span data-stu-id="78ff4-167">[Viewing reports and scorecards on Apple iPad devices (SharePoint Server 2010)](https://technet.microsoft.com/library/hh697482.aspx) (https://technet.microsoft.com/library/hh697482.aspx).</span></span>

-   <span data-ttu-id="78ff4-168">[Exibindo Reporting Services relatórios em um iPad (vídeo)](https://technet.microsoft.com/sqlserver/jj873792.aspx) ( https://technet.microsoft.com/sqlserver/jj873792.aspx) .</span><span class="sxs-lookup"><span data-stu-id="78ff4-168">[Viewing Reporting Services Reports on an iPad (video)](https://technet.microsoft.com/sqlserver/jj873792.aspx) (https://technet.microsoft.com/sqlserver/jj873792.aspx).</span></span>

-   [<span data-ttu-id="78ff4-169">Exibindo relatórios do Reporting Services em um dispositivo Microsoft Surface RT (vídeo)</span><span class="sxs-lookup"><span data-stu-id="78ff4-169">Viewing Reporting Services Reports on a Microsoft Surface RT Device (video)</span></span>](https://technet.microsoft.com/sqlserver/dn146017)


