---
title: Exportar um relatório como outro tipo de arquivo (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b577568b-ecbd-44c3-be88-31dab6fc38a2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 240d3266b7b8c9a445658a9fd21fb9ea18a4c113
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678656"
---
# <a name="export-a-report-as-another-file-type-report-builder-and-ssrs"></a><span data-ttu-id="16b03-102">Exportar um relatório como outro tipo de arquivo (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="16b03-102">Export a Report as Another File Type (Report Builder and SSRS)</span></span>
  <span data-ttu-id="16b03-103">Você pode renderizar um relatório para outro formato de arquivo, como CSV, Imagem, PDF, [!INCLUDE[ofprword](../includes/ofprword-md.md)]ou [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)], enquanto visualiza seu relatório no Construtor de Relatórios ou no Designer de Relatórios, ou pode renderizar o relatório enquanto visualiza-o no servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="16b03-103">You can render a report to another file format, such as CSV, Image, PDF, [!INCLUDE[ofprword](../includes/ofprword-md.md)], or [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)], while previewing your report in Report Builder or Report Designer, or you can render the report while viewing the report on the report server.</span></span> <span data-ttu-id="16b03-104">A renderização do relatório em um formato específico será útil se você desejar salvá-lo imediatamente como outro tipo de arquivo, sem publicar o relatório no servidor de relatório, ou se quiser ver como o design do relatórios será exibido quando ele for entregue aos leitores de relatórios em um formato específico.</span><span class="sxs-lookup"><span data-stu-id="16b03-104">Rendering the report in a specific format in is helpful when you want to immediately save the report as another file type without publishing the report to the report server or when you want to see how your report design will appear when delivered to your report readers in a specific format.</span></span> <span data-ttu-id="16b03-105">A renderização do relatório no servidor de relatórios é útil quando você configura assinaturas ou fornece seus relatórios por email, ou quando deseja salvar um relatório disponível no servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="16b03-105">Rendering the report on the report server is useful when you set up subscriptions or deliver your reports via e-mail, or if you want to save a report that is available on the report server.</span></span> <span data-ttu-id="16b03-106">Para obter mais informações, consulte [Assinaturas e entrega &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="16b03-106">For more information, see [Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../includes/ssrbrddup-md.md)]  
  
### <a name="to-export-a-report-as-another-file-type-in-report-builder"></a><span data-ttu-id="16b03-107">Para exportar um relatório como outro tipo de arquivo no Construtor de Relatórios</span><span class="sxs-lookup"><span data-stu-id="16b03-107">To export a report as another file type in Report Builder</span></span>  
  
1.  <span data-ttu-id="16b03-108">Visualize o relatório.</span><span class="sxs-lookup"><span data-stu-id="16b03-108">Preview the report.</span></span>  
  
2.  <span data-ttu-id="16b03-109">Na faixa de opções, clique em **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="16b03-109">On the ribbon, click **Export**.</span></span>  
  
3.  <span data-ttu-id="16b03-110">Selecione o formato que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="16b03-110">Select the format that you want to use.</span></span>  
  
     <span data-ttu-id="16b03-111">A caixa de diálogo **Salvar como** é aberta.</span><span class="sxs-lookup"><span data-stu-id="16b03-111">The **Save As** dialog box opens.</span></span> <span data-ttu-id="16b03-112">Por padrão, o nome do arquivo é o mesmo do relatório que você exportou.</span><span class="sxs-lookup"><span data-stu-id="16b03-112">By default, the file name is that of the report that you exported.</span></span> <span data-ttu-id="16b03-113">Opcionalmente, você pode alterar o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="16b03-113">Optionally, you can change the file name.</span></span>  
  
4.  <span data-ttu-id="16b03-114">Navegue até o local em que o relatório exportado foi salvo e abra-o.</span><span class="sxs-lookup"><span data-stu-id="16b03-114">Navigate to the location where you saved the exported report and open it.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="16b03-115">Se o programa não puder abrir o relatório no formato escolhido porque você não tem um programa associado a esse tipo de arquivo, será solicitado que você salve o relatório exportado ou localize um programa online para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="16b03-115">If the program cannot open the report in the format that you chose because you do not have a program associated with this file type, you will be prompted to save the exported report or to find a program online to open the report.</span></span>  
  
### <a name="to-export-a-report-as-another-file-type-in-report-manager"></a><span data-ttu-id="16b03-116">Para exportar um relatório como outro tipo de arquivo no Gerenciador de Relatórios</span><span class="sxs-lookup"><span data-stu-id="16b03-116">To export a report as another file type in Report Manager</span></span>  
  
1.  <span data-ttu-id="16b03-117">No Gerenciador de Relatórios, na página **inicial** , navegue até o relatório que deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="16b03-117">From the Report Manager **Home** page, navigate to the report that you want to export.</span></span>  
  
2.  <span data-ttu-id="16b03-118">Clique no relatório.</span><span class="sxs-lookup"><span data-stu-id="16b03-118">Click the report.</span></span>  
  
     <span data-ttu-id="16b03-119">O relatório é gerado.</span><span class="sxs-lookup"><span data-stu-id="16b03-119">The report is generated.</span></span>  
  
3.  <span data-ttu-id="16b03-120">Na barra de ferramentas do Report Viewer, clique na seta suspensa **Selecionar um formato** .</span><span class="sxs-lookup"><span data-stu-id="16b03-120">On the Report Viewer toolbar, click the **Select a format** drop-down arrow.</span></span>  
  
4.  <span data-ttu-id="16b03-121">Selecione o formato que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="16b03-121">Select the format that you want to use.</span></span>  
  
5.  <span data-ttu-id="16b03-122">Clique em **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="16b03-122">Click **Export**.</span></span>  
  
     <span data-ttu-id="16b03-123">Uma mensagem é exibida perguntando se deseja abrir ou salvar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="16b03-123">A message appears asking you if you want to open or save the file.</span></span>  
  
6.  <span data-ttu-id="16b03-124">Para exibir o relatório no formato de exportação selecionado, clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="16b03-124">To view the report in the selected export format, click **Open**.</span></span>  
  
     <span data-ttu-id="16b03-125">\- ou –</span><span class="sxs-lookup"><span data-stu-id="16b03-125">\- or -</span></span>  
  
     <span data-ttu-id="16b03-126">Para salvar imediatamente o relatório no formato de exportação selecionado, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="16b03-126">To immediately save the report in the selected export format, click **Save**.</span></span>  
  
     <span data-ttu-id="16b03-127">Usando o aplicativo associado ao formato escolhido, o relatório é exibido ou salvo.</span><span class="sxs-lookup"><span data-stu-id="16b03-127">Using the application that is associated with the format that you chose, the report is either displayed or saved.</span></span> <span data-ttu-id="16b03-128">Se você clicar em **Salvar**, você será solicitado a indicar um local no qual seja possível salvar o relatório.</span><span class="sxs-lookup"><span data-stu-id="16b03-128">If you click **Save**, you will be prompted for a location where you can save your report.</span></span>  
  
     <span data-ttu-id="16b03-129">**Observação** Se o programa não puder abrir o relatório no formato escolhido porque você não tem um programa associado a esse tipo de arquivo, você será solicitado a salvar o relatório exportado ou a localizar um programa online para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="16b03-129">**Note** If the program cannot open the report in the format that you chose because you do not have a program associated with this file type, you will be prompted to save the exported report or to find a program online to open the report.</span></span>  
  
### <a name="to-export-a-report-as-another-file-type-in-a-sharepoint-library"></a><span data-ttu-id="16b03-130">Para exportar um relatório como outro tipo de arquivo em uma biblioteca do SharePoint</span><span class="sxs-lookup"><span data-stu-id="16b03-130">To export a report as another file type in a SharePoint library</span></span>  
  
1.  <span data-ttu-id="16b03-131">Visualize o relatório.</span><span class="sxs-lookup"><span data-stu-id="16b03-131">Preview the report.</span></span>  
  
2.  <span data-ttu-id="16b03-132">Na barra de ferramentas, clique em **Ações**, aponte para **Exportar**e selecione o formato desejado.</span><span class="sxs-lookup"><span data-stu-id="16b03-132">On the toolbar, click **Actions**, point to **Export**, and then select the format that you want to use.</span></span>  
  
     <span data-ttu-id="16b03-133">A caixa de diálogo **Download de Arquivo** é aberta.</span><span class="sxs-lookup"><span data-stu-id="16b03-133">The **File Download** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="16b03-134">Para exibir o relatório no formato de exportação selecionado, clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="16b03-134">To view the report in the selected export format, click **Open**.</span></span>  
  
     <span data-ttu-id="16b03-135">\- ou –</span><span class="sxs-lookup"><span data-stu-id="16b03-135">\- or -</span></span>  
  
     <span data-ttu-id="16b03-136">Para salvar imediatamente o relatório no formato de exportação selecionado, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="16b03-136">To immediately save the report in the selected export format, click **Save**.</span></span>  
  
     <span data-ttu-id="16b03-137">Usando o aplicativo associado ao formato escolhido, o relatório é exibido ou salvo.</span><span class="sxs-lookup"><span data-stu-id="16b03-137">Using the application that is associated with the format that you chose, the report is either displayed or saved.</span></span> <span data-ttu-id="16b03-138">Se você clicar em **Salvar**, você será solicitado a indicar um local no qual seja possível salvar o relatório.</span><span class="sxs-lookup"><span data-stu-id="16b03-138">If you click **Save**, you will be prompted for a location where you can save your report.</span></span>  
  
     <span data-ttu-id="16b03-139">Outra opção é alterar o nome do arquivo do relatório exportado.</span><span class="sxs-lookup"><span data-stu-id="16b03-139">Optionally, change the file name of the exported report.</span></span>  
  
     <span data-ttu-id="16b03-140">**Observação** Se o programa não puder abrir o relatório no formato escolhido porque você não tem um programa associado a esse tipo de arquivo, você será solicitado a salvar o relatório exportado ou a localizar um programa online para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="16b03-140">**Note** If the program cannot open the report in the format that you chose because you do not have a program associated with this file type, you will be prompted to save the exported report or to find a program online to open the report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16b03-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="16b03-141">See Also</span></span>  
 <span data-ttu-id="16b03-142">[Exportando relatórios &#40;Construtor de Relatórios e SSRS&#41;](report-builder/export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="16b03-142">[Exporting Reports &#40;Report Builder and SSRS&#41;](report-builder/export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="16b03-143">[Paginação em Reporting Services &#40;Construtor de Relatórios e SSRS&#41;](report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="16b03-143">[Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="16b03-144">Funcionalidade interativa para extensões de renderização de relatório diferentes &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="16b03-144">Interactive Functionality for Different Report Rendering Extensions &#40;Report Builder and SSRS&#41;</span></span>](report-builder/interactive-functionality-different-report-rendering-extensions.md)  
  
  
