---
title: Conectar a Web Part de filtro ou documentos (Reporting Services no modo integrado do SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Filter Web Part [Reporting Services]
- SharePoint integration [Reporting Services], Web Parts
- Report Viewer Web Part [Reporting Services]
- Documents Web Part [Reporting Services]
ms.assetid: 6a303135-c0ef-44cd-a423-1cea8df3dcf3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5ea7b9f9aba128052ae6ac7f05ef40517eb50e6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571339"
---
# <a name="connect-filter-or-documents-web-part-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="de8f8-102">Conectar Web Part de filtro ou de documentos (Reporting Services no modo integrado do SharePoint)</span><span class="sxs-lookup"><span data-stu-id="de8f8-102">Connect Filter or Documents Web Part (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="de8f8-103">Se estiver usando um produto do SharePoint, você poderá criar um painel ou Página de Web Part que inclua uma Web Part de filtro ou de documentos e uma Web Part do Visualizador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="de8f8-103">If you are using a SharePoint product, you can create a dashboard or Web Part Page that includes a Filter Web Part or Documents Web part and a Report Viewer Web Part.</span></span> <span data-ttu-id="de8f8-104">As versões com suporte são [!INCLUDE[SPF2010](../includes/spf2010-md.md)] ou [!INCLUDE[SPS2010](../includes/sps2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de8f8-104">Supported versions are [!INCLUDE[SPF2010](../includes/spf2010-md.md)] or [!INCLUDE[SPS2010](../includes/sps2010-md.md)].</span></span> <span data-ttu-id="de8f8-105">Também há suporte para [!INCLUDE[winSPServ3](../includes/winspserv3-md.md)] ou [!INCLUDE[offSPServ](../includes/offspserv-md.md)] 2007.</span><span class="sxs-lookup"><span data-stu-id="de8f8-105">Also supported are [!INCLUDE[winSPServ3](../includes/winspserv3-md.md)] or [!INCLUDE[offSPServ](../includes/offspserv-md.md)] 2007.</span></span> <span data-ttu-id="de8f8-106">Ao conectarem uma Web Part de filtro, os usuários que selecionam valores de filtro em uma Web Part de filtro podem enviar o valor para um relatório parametrizado na mesma página.</span><span class="sxs-lookup"><span data-stu-id="de8f8-106">By connecting a Filter Web Part, users who select filter values in a Filter Web Part can send the value to a parameterized report on the same page.</span></span> <span data-ttu-id="de8f8-107">Ao conectarem uma Web Part de documento, os usuários que clicarem na biblioteca de Documentos podem exibir o relatório em uma Web Part do Visualizador de Relatórios adjacente.</span><span class="sxs-lookup"><span data-stu-id="de8f8-107">By connecting a Documents Web Part, users who click on reports in the Documents library can view the report in an adjacent Report Viewer Web Part.</span></span>  
  
 <span data-ttu-id="de8f8-108">A Web Part de filtro é usada para enviar valores a um ou mais parâmetros em um relatório.</span><span class="sxs-lookup"><span data-stu-id="de8f8-108">The Filter Web Part is used to send values to one or more parameters on a report.</span></span> <span data-ttu-id="de8f8-109">Para usar uma Web Part de filtro, o relatório deve ter parâmetros definidos para ele, compatíveis com os valores, o tipo de dados e o formato enviado pela Web Part.</span><span class="sxs-lookup"><span data-stu-id="de8f8-109">To use a Filter Web Part, the report must have parameters defined for it that are compatible with the values, data type, and format sent by the Web Part.</span></span>  
  
 <span data-ttu-id="de8f8-110">A Web Part de documento é associada à biblioteca de Documentos do site Inicial.</span><span class="sxs-lookup"><span data-stu-id="de8f8-110">The Documents Web Part is associated with the Documents library of the Home site.</span></span> <span data-ttu-id="de8f8-111">Para exibir, adicionar ou remover itens na Biblioteca de Documentos, clique em **Exibir Todo o Conteúdo do Site**.</span><span class="sxs-lookup"><span data-stu-id="de8f8-111">To view, add, or remove items from the Documents library, click **View All Site Content**.</span></span> <span data-ttu-id="de8f8-112">Em Bibliotecas, clique em **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="de8f8-112">In Libraries, click **Documents**.</span></span> <span data-ttu-id="de8f8-113">Você pode usar os menus **Novo**, **Carregar**e **Ações** para gerenciar os itens da Biblioteca de Documentos.</span><span class="sxs-lookup"><span data-stu-id="de8f8-113">You can use the **New**, **Upload**, and **Actions** menu to manage the items in the Documents library.</span></span>  
  
### <a name="to-connect-a-filter-web-part"></a><span data-ttu-id="de8f8-114">Para conectar uma Web Part de filtro</span><span class="sxs-lookup"><span data-stu-id="de8f8-114">To connect a Filter Web Part</span></span>  
  
1.  <span data-ttu-id="de8f8-115">Abra ou crie uma página ou um painel da Web Part.</span><span class="sxs-lookup"><span data-stu-id="de8f8-115">Open or create the Web Part page or dashboard.</span></span>  
  
2.  <span data-ttu-id="de8f8-116">No menu **Ações do Site** , clique em **Editar Página**.</span><span class="sxs-lookup"><span data-stu-id="de8f8-116">On the **Site Actions** menu, click **Edit Page**.</span></span>  
  
3.  <span data-ttu-id="de8f8-117">Clique em **Adicionar uma Web Part**.</span><span class="sxs-lookup"><span data-stu-id="de8f8-117">Click **Add a Web Part**.</span></span>  
  
4.  <span data-ttu-id="de8f8-118">Em **todos os Web Parts**, na categoria **diversos** , selecione **SQL Server Reporting Services Visualizador de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="de8f8-118">In **All Web Parts**, in the **Miscellaneous** category, select **SQL Server Reporting Services Report Viewer**.</span></span>  
  
5.  <span data-ttu-id="de8f8-119">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="de8f8-119">Click **Add**.</span></span> <span data-ttu-id="de8f8-120">A Web Part será adicionada à parte superior da zona.</span><span class="sxs-lookup"><span data-stu-id="de8f8-120">The Web Part is added at the top of the zone.</span></span>  
  
6.  <span data-ttu-id="de8f8-121">Em outra zona na mesma página de Web Part ou no painel, clique em **Adicionar uma Web Part**.</span><span class="sxs-lookup"><span data-stu-id="de8f8-121">On another zone in the same Web Part page or dashboard, click **Add a Web Part**.</span></span>  
  
7.  <span data-ttu-id="de8f8-122">Em **todos os Web Parts**, na seção **filtros** , selecione uma Web Part.</span><span class="sxs-lookup"><span data-stu-id="de8f8-122">In **All Web Parts**, in the **Filters** section, select a Web Part.</span></span>  
  
8.  <span data-ttu-id="de8f8-123">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="de8f8-123">Click **Add**.</span></span> <span data-ttu-id="de8f8-124">A Web Part será adicionada à parte superior da zona.</span><span class="sxs-lookup"><span data-stu-id="de8f8-124">The Web Part is added at the top of the zone.</span></span>  
  
9. <span data-ttu-id="de8f8-125">Na zona que contém a Web Part, clique no menu **Editar** da Web Part, aponte para **Conexões**, para **Enviar Valores de Filtro Para**e selecione **Visualizador de Relatórios** - *nome do relatório*.</span><span class="sxs-lookup"><span data-stu-id="de8f8-125">In the zone that contains the Web Part, click the Web Part **edit** menu, point to **Connections**, point to **Send Filter Values To**, and then select **Report Viewer** - *report name*.</span></span>  
  
10. <span data-ttu-id="de8f8-126">Verifique suas alterações e salve a página.</span><span class="sxs-lookup"><span data-stu-id="de8f8-126">Check in your changes and save the page.</span></span>  
  
### <a name="to-connect-a-documents-web-part"></a><span data-ttu-id="de8f8-127">Para conectar uma Web Part de documento</span><span class="sxs-lookup"><span data-stu-id="de8f8-127">To connect a Documents Web Part</span></span>  
  
1.  <span data-ttu-id="de8f8-128">Abra ou crie uma página ou um painel da Web Part.</span><span class="sxs-lookup"><span data-stu-id="de8f8-128">Open or create the Web Part page or dashboard.</span></span>  
  
2.  <span data-ttu-id="de8f8-129">No menu **Ações do Site** , clique em **Editar Página**.</span><span class="sxs-lookup"><span data-stu-id="de8f8-129">On the **Site Actions** menu, click **Edit Page**.</span></span>  
  
3.  <span data-ttu-id="de8f8-130">Clique em **Adicionar uma Web Part**.</span><span class="sxs-lookup"><span data-stu-id="de8f8-130">Click **Add a Web Part**.</span></span>  
  
4.  <span data-ttu-id="de8f8-131">Em **Todas as Web Parts**, na seção **Listas e Biblioteca** , selecione **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="de8f8-131">In **All Web Parts**, in the **Lists and Library** section, select **Documents.**</span></span>  
  
5.  <span data-ttu-id="de8f8-132">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="de8f8-132">Click **Add**.</span></span> <span data-ttu-id="de8f8-133">A Web Part será adicionada à parte superior da zona.</span><span class="sxs-lookup"><span data-stu-id="de8f8-133">The Web Part is added at the top of the zone.</span></span>  
  
6.  <span data-ttu-id="de8f8-134">Clique em **Aplicar** na parte inferior do painel de ferramentas e clique em **OK** para fechar esse painel.</span><span class="sxs-lookup"><span data-stu-id="de8f8-134">Click **Apply** at the bottom of the tool pane, and then click **OK** to close the pane.</span></span>  
  
7.  <span data-ttu-id="de8f8-135">Em outra zona na mesma página de Web Part ou no painel, clique em **Adicionar uma Web Part**.</span><span class="sxs-lookup"><span data-stu-id="de8f8-135">On another zone in the same Web Part page or dashboard, click **Add a Web Part**.</span></span>  
  
8.  <span data-ttu-id="de8f8-136">Em **Todas as Web Parts**, na categoria **Diversos** , selecione **Visualizador de Relatórios do SQL Server Reporting Services.**</span><span class="sxs-lookup"><span data-stu-id="de8f8-136">In **All Web Parts**, in the **Miscellaneous** category, select **SQL Server Reporting Services Report Viewer.**</span></span>  
  
9. <span data-ttu-id="de8f8-137">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="de8f8-137">Click **Add**.</span></span> <span data-ttu-id="de8f8-138">A Web Part será adicionada à parte superior da zona.</span><span class="sxs-lookup"><span data-stu-id="de8f8-138">The Web Part is added at the top of the zone.</span></span>  
  
10. <span data-ttu-id="de8f8-139">Na zona que contém a Web Part, clique no menu **Editar** da Web Part, aponte para **Conexões**, para **Obter definições de relatório de**e selecione **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="de8f8-139">In the zone that contains the Web Part, click the Web Part **edit** menu, point to **Connections**, point to **Get report definitions from**, and then select **Documents**.</span></span>  
  
11. <span data-ttu-id="de8f8-140">Verifique suas alterações e salve a página.</span><span class="sxs-lookup"><span data-stu-id="de8f8-140">Check in your changes and save the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de8f8-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="de8f8-141">See Also</span></span>  
 <span data-ttu-id="de8f8-142">[Adicione a Web Part do Visualizador de relatórios a uma página da Web &#40;Reporting Services no modo integrado do SharePoint&#41;](report-server-sharepoint/add-reporting-services-content-types-to-a-sharepoint-library.md) </span><span class="sxs-lookup"><span data-stu-id="de8f8-142">[Add the Report Viewer Web Part to a Web Page &#40;Reporting Services in SharePoint Integrated Mode&#41;](report-server-sharepoint/add-reporting-services-content-types-to-a-sharepoint-library.md) </span></span>  
 <span data-ttu-id="de8f8-143">[Web Part do Visualizador de relatórios em um site do SharePoint](../../2014/reporting-services/report-viewer-web-part-on-a-sharepoint-site.md) </span><span class="sxs-lookup"><span data-stu-id="de8f8-143">[Report Viewer Web Part on a SharePoint Site](../../2014/reporting-services/report-viewer-web-part-on-a-sharepoint-site.md) </span></span>  
 [<span data-ttu-id="de8f8-144">Personalizar a Web Part do Visualizador de relatórios</span><span class="sxs-lookup"><span data-stu-id="de8f8-144">Customize the Report Viewer Web Part</span></span>](../../2014/reporting-services/customize-the-report-viewer-web-part.md)  
  
  
