---
title: Recursos preteridos do SQL Server Reporting Services no SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services, backward compatibility
- deprecated features [Reporting Services]
- HTML OWC rendering extension [Reporting Services]
- Report Server Web service, endpoints
ms.assetid: 3876c01e-f81d-4cce-9104-5106a8c369e6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: af858ae94bf5ea3d9f0cfe0b99759442dabd6629
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574542"
---
# <a name="deprecated-features-in-sql-server-reporting-services-in-sql-server-2014"></a><span data-ttu-id="f6bc5-102">Recursos preteridos no SQL Server Reporting Services do SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="f6bc5-102">Deprecated Features in SQL Server Reporting Services in SQL Server 2014</span></span>
  <span data-ttu-id="f6bc5-103">Este tópico descreve os recursos preteridos do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f6bc5-103">This topic describes the deprecated [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features.</span></span> <span data-ttu-id="f6bc5-104">Os recursos ainda estão disponíveis na versão em que foram preteridos; porém, os recursos estão agendados para ser removidos em uma versão futura do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f6bc5-104">The features are still available in the release in which they are deprecated; however the features are scheduled to be removed in a future release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f6bc5-105">Recursos preteridos não devem ser usados em aplicativos novos.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-105">Deprecated features should not be used in new applications.</span></span>  
  
 <span data-ttu-id="f6bc5-106">Neste tópico:</span><span class="sxs-lookup"><span data-stu-id="f6bc5-106">In this topic:</span></span>  
  
-   [<span data-ttu-id="f6bc5-107">Recursos preteridos no SQL Server 2014 Reporting Services</span><span class="sxs-lookup"><span data-stu-id="f6bc5-107">SQL Server 2014 Reporting Services Deprecated Features</span></span>](#bkmk_2014)  
  
-   [<span data-ttu-id="f6bc5-108">Recursos preteridos no SQL Server 2012 SP1 Reporting Services</span><span class="sxs-lookup"><span data-stu-id="f6bc5-108">SQL Server 2012 SP1 Reporting Services Deprecated Features</span></span>](#bkmk_2012sp1)  
  
-   [<span data-ttu-id="f6bc5-109">Recursos preteridos no SQL Server 2012 Reporting Services</span><span class="sxs-lookup"><span data-stu-id="f6bc5-109">SQL Server 2012 Reporting Services Deprecated Features</span></span>](#bkmk_2012)  
  
-   [<span data-ttu-id="f6bc5-110">Recursos preteridos no SQL Server 2008 R2 Reporting Services</span><span class="sxs-lookup"><span data-stu-id="f6bc5-110">SQL Server 2008 R2 Reporting Services Deprecated Features</span></span>](#bkmk_kj)  
  
##  <a name="sql-server-2014-reporting-services-deprecated-features"></a><a name="bkmk_2014"></a><span data-ttu-id="f6bc5-111">SQL Server 2014 Reporting Services recursos preteridos</span><span class="sxs-lookup"><span data-stu-id="f6bc5-111">SQL Server 2014 Reporting Services Deprecated Features</span></span>  
  
### <a name="features-not-supported-in-the-next-version-of-sql-server"></a><span data-ttu-id="f6bc5-112">Recursos sem suporte na próxima versão do SQL Server</span><span class="sxs-lookup"><span data-stu-id="f6bc5-112">Features Not Supported in the Next Version of SQL Server</span></span>  
 <span data-ttu-id="f6bc5-113">Os recursos a seguir [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] não terão suporte na **próxima** versão do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f6bc5-113">The following [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features will not be supported in the **next** version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f6bc5-114">Não use esses recursos em novo trabalho de desenvolvimento e, assim que possível, modifique os aplicativos que os utilizam atualmente.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-114">Do not use these features in new development work, and modify applications that currently use these features as soon as possible.</span></span>  
  
#### <a name="html-rendering-extension-device-information-settings"></a><span data-ttu-id="f6bc5-115">Configurações de informações de dispositivos para extensões de renderização HTML</span><span class="sxs-lookup"><span data-stu-id="f6bc5-115">HTML Rendering Extension Device Information Settings</span></span>  
 <span data-ttu-id="f6bc5-116">As configurações de informações de dispositivos da extensão de renderização HTML a seguir foram preteridas.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-116">The following device information settings for the HTML rendering extension are deprecated.</span></span>  
  
-   <span data-ttu-id="f6bc5-117">ActionScript</span><span class="sxs-lookup"><span data-stu-id="f6bc5-117">ActionScript</span></span>  
  
-   <span data-ttu-id="f6bc5-118">ActiveXControls</span><span class="sxs-lookup"><span data-stu-id="f6bc5-118">ActiveXControls</span></span>  
  
-   <span data-ttu-id="f6bc5-119">GetImage</span><span class="sxs-lookup"><span data-stu-id="f6bc5-119">GetImage</span></span>  
  
-   <span data-ttu-id="f6bc5-120">OnlyVisibleStyles</span><span class="sxs-lookup"><span data-stu-id="f6bc5-120">OnlyVisibleStyles</span></span>  
  
-   <span data-ttu-id="f6bc5-121">ReplacementRoot</span><span class="sxs-lookup"><span data-stu-id="f6bc5-121">ReplacementRoot</span></span>  
  
-   <span data-ttu-id="f6bc5-122">ResourceStreamRoot</span><span class="sxs-lookup"><span data-stu-id="f6bc5-122">ResourceStreamRoot</span></span>  
  
-   <span data-ttu-id="f6bc5-123">StreamRoot</span><span class="sxs-lookup"><span data-stu-id="f6bc5-123">StreamRoot</span></span>  
  
-   <span data-ttu-id="f6bc5-124">UsePx</span><span class="sxs-lookup"><span data-stu-id="f6bc5-124">UsePx</span></span>  
  
-   <span data-ttu-id="f6bc5-125">Zoom</span><span class="sxs-lookup"><span data-stu-id="f6bc5-125">Zoom</span></span>  
  
 <span data-ttu-id="f6bc5-126">Para obter mais informações sobre a extensão de renderização HTML, consulte [HTML Device Information Settings](html-device-information-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f6bc5-126">For more information on the HTML rendering extension, see [HTML Device Information Settings](html-device-information-settings.md)</span></span>  
  
#### <a name="microsoft-word-and-microsoft-excel-1997-2003-rendering"></a><span data-ttu-id="f6bc5-127">Renderização do Microsoft Word e do Microsoft Excel 1997-2003</span><span class="sxs-lookup"><span data-stu-id="f6bc5-127">Microsoft Word and Microsoft Excel 1997-2003 Rendering</span></span>  
 <span data-ttu-id="f6bc5-128">As [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] extensões de renderização BIFF8 são [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] relatadas para o [!INCLUDE[msCoName](../includes/msconame-md.md)] formato de arquivo de intercâmbio binário do Word e [!INCLUDE[msCoName](../includes/msconame-md.md)] Excel 1997-2003.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-128">The[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] BIFF8 rendering extensions [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports to the [!INCLUDE[msCoName](../includes/msconame-md.md)] Word and [!INCLUDE[msCoName](../includes/msconame-md.md)] Excel 1997-2003 binary interchange file format.</span></span> [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="f6bc5-129">inclui extensões que são renderizadas no [!INCLUDE[msCoName](../includes/msconame-md.md)] formato XML aberto do Office 2007-2010.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-129">includes extensions that render in the [!INCLUDE[msCoName](../includes/msconame-md.md)] Office 2007-2010 Open XML format.</span></span>  
  
#### <a name="report-definition-language-rdl-2005-and-earlier"></a><span data-ttu-id="f6bc5-130">Linguagem RDL 2005 e versões anteriores</span><span class="sxs-lookup"><span data-stu-id="f6bc5-130">Report Definition Language (RDL) 2005 and Earlier</span></span>  
 <span data-ttu-id="f6bc5-131">A linguagem RDL 2005 e as versões anteriores foram preteridos.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-131">Report Definition Language (RDL) 2005 and earlier is deprecated.</span></span> <span data-ttu-id="f6bc5-132">Para obter mais informações sobre o RDL, consulte [linguagem de definição de relatório &#40;&#41;SSRS ](reports/report-definition-language-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f6bc5-132">For more information about RDL, see [Report Definition Language &#40;SSRS&#41;](reports/report-definition-language-ssrs.md).</span></span>  
  
 <span data-ttu-id="f6bc5-133">Para obter mais informações como atualizar relatórios, consulte [Upgrade Reports](install-windows/upgrade-reports.md).</span><span class="sxs-lookup"><span data-stu-id="f6bc5-133">For more information on upgrading reports, see [Upgrade Reports](install-windows/upgrade-reports.md).</span></span>  
  
#### <a name="sql-server-2005-and-earlier-custom-report-items"></a><span data-ttu-id="f6bc5-134">Itens de relatório personalizados do SQL Server 2005 e versões anteriores</span><span class="sxs-lookup"><span data-stu-id="f6bc5-134">SQL Server 2005 and earlier Custom Report Items</span></span>  
 <span data-ttu-id="f6bc5-135">Os itens de relatório personalizados (CRI) compilados para [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 e anteriores foram preteridos.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-135">Custom Report Items (CRI) compiled for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 and earlier are deprecated.</span></span>  
  
#### <a name="reporting-services-snapshots-2005-and-earlier"></a><span data-ttu-id="f6bc5-136">Instantâneos do Reporting Services 2005 e versões anteriores</span><span class="sxs-lookup"><span data-stu-id="f6bc5-136">Reporting Services Snapshots 2005 and earlier</span></span>  
 [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="f6bc5-137">os instantâneos renderizados com [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 e anteriores são preteridos.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-137">snapshots rendered with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 and earlier are deprecated.</span></span>  
  
#### <a name="report-models"></a><span data-ttu-id="f6bc5-138">Modelos de relatório</span><span class="sxs-lookup"><span data-stu-id="f6bc5-138">Report Models</span></span>  
 <span data-ttu-id="f6bc5-139">Os modelos de relatório SMDL (linguagem de modelagem semântica) foram preteridos.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-139">Semantic modeling language (SMDL) report models are deprecated.</span></span> <span data-ttu-id="f6bc5-140">Embora você possa continuar usando modelos de relatório existentes como fontes de dados em [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] relatórios, você deve considerar atualizar seus relatórios para remover sua dependência em modelos de relatório.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-140">Although you can you continue to use existing report models as data sources in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)][!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports you should consider updating your reports to remove their dependency on report models.</span></span>  
  
 [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="f6bc5-141">Não [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] inclui ferramentas para criar ou atualizar modelos de relatório.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-141">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] does not include tools for creating or updating report models.</span></span> <span data-ttu-id="f6bc5-142">Para obter mais informações, consulte [alterações significativas em SQL Server Reporting Services no SQL Server 2014](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="f6bc5-142">For more information, see [Breaking Changes in SQL Server Reporting Services in SQL Server 2014](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md).</span></span>  
  
#### <a name="deprecated-methods-in-the-web-service-endpoint"></a><span data-ttu-id="f6bc5-143">Métodos preteridos no ponto de extremidade de serviço Web</span><span class="sxs-lookup"><span data-stu-id="f6bc5-143">Deprecated Methods in the Web Service Endpoint</span></span>  
 <span data-ttu-id="f6bc5-144">As operações a seguir foram preteridas no ponto de extremidade do serviço Web do <xref:ReportService2010.ReportingService2010>:</span><span class="sxs-lookup"><span data-stu-id="f6bc5-144">The following operations are deprecated in the <xref:ReportService2010.ReportingService2010> Web service endpoint:</span></span>  
  
-   <xref:ReportService2010.ReportingService2010.GetProperties%2A>  
  
-   <xref:ReportService2010.ReportingService2010.IsSSLRequired%2A>  
  
#### <a name="sharepoint-web-parts"></a><span data-ttu-id="f6bc5-145">Web Parts do SharePoint</span><span class="sxs-lookup"><span data-stu-id="f6bc5-145">SharePoint Web Parts</span></span>  
 <span data-ttu-id="f6bc5-146">O arquivo de gabinete de instalação **RSWebParts.cab** e as Web Parts do SharePoint que podem ser extraídos do arquivo cab são preteridos.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-146">The installation cabinet file **RSWebParts.cab** and the SharePoint web parts that can be extracted from the cab file, are deprecated.</span></span> <span data-ttu-id="f6bc5-147">As Web Parts preteridas são o Gerenciador de relatórios (**comexplorer. dwp**) e o Visualizador de relatórios (**comviewer. dwp**).</span><span class="sxs-lookup"><span data-stu-id="f6bc5-147">The deprecated web parts are Report Explorer (**SPExplorer.dwp**) and Report Viewer (**SPViewer.dwp**).</span></span>  
  
 <span data-ttu-id="f6bc5-148">Para obter mais informações sobre as Web Parts preteridas, consulte [Exibir e explorar relatórios de modo nativo usando o SharePoint Web Parts (SSRS)](https://msdn.microsoft.com/library/ms159772.aspx)</span><span class="sxs-lookup"><span data-stu-id="f6bc5-148">For more information on the deprecated web parts, see [View and Explore Native Mode Reports Using SharePoint Web Parts (SSRS)](https://msdn.microsoft.com/library/ms159772.aspx)</span></span>  
  
### <a name="features-not-supported-in-a-future-version-of-sql-server"></a><span data-ttu-id="f6bc5-149">Recursos sem suporte em uma versão futura do SQL Server</span><span class="sxs-lookup"><span data-stu-id="f6bc5-149">Features Not Supported in a Future Version of SQL Server</span></span>  
 <span data-ttu-id="f6bc5-150">Os recursos do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] a seguir terão suporte na próxima versão do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], mas serão removidos em uma versão posterior.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-150">The following [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features are supported in the next version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], but will be removed in a later version.</span></span> <span data-ttu-id="f6bc5-151">A versão específica do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] não foi determinada.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-151">The specific version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] has not been determined.</span></span>  
  
 <span data-ttu-id="f6bc5-152">Nenhum recurso do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] foi preterido no [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f6bc5-152">No [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features were deprecated in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
##  <a name="sql-server-2012-sp1-reporting-services-deprecated-features"></a><a name="bkmk_2012sp1"></a><span data-ttu-id="f6bc5-153">SQL Server 2012 SP1 Reporting Services recursos preteridos</span><span class="sxs-lookup"><span data-stu-id="f6bc5-153">SQL Server 2012 SP1 Reporting Services Deprecated Features</span></span>  
 <span data-ttu-id="f6bc5-154">Esta seção descreve os recursos do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] preteridos no [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f6bc5-154">This section describes [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features deprecated in [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)].</span></span> <span data-ttu-id="f6bc5-155">Os recursos do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] a seguir terão suporte na próxima versão do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], mas serão removidos em uma versão posterior.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-155">The following [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features are supported in the next version of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], but will be removed in a later version.</span></span> <span data-ttu-id="f6bc5-156">A versão específica do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] não foi determinada.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-156">The specific version of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] has not been determined.</span></span>  
  
### <a name="sharepoint-web-parts"></a><span data-ttu-id="f6bc5-157">Web Parts do SharePoint</span><span class="sxs-lookup"><span data-stu-id="f6bc5-157">SharePoint Web Parts</span></span>  
 <span data-ttu-id="f6bc5-158">O arquivo de gabinete de instalação **RSWebParts.cab** e as Web Parts do SharePoint que podem ser extraídos do arquivo cab são preteridos.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-158">The installation cabinet file **RSWebParts.cab** and the SharePoint web parts that can be extracted from the cab file, are deprecated.</span></span> <span data-ttu-id="f6bc5-159">As Web Parts preteridas são o Gerenciador de relatórios (**comexplorer. dwp**) e o Visualizador de relatórios (**comviewer. dwp**).</span><span class="sxs-lookup"><span data-stu-id="f6bc5-159">The deprecated web parts are Report Explorer (**SPExplorer.dwp**) and Report Viewer (**SPViewer.dwp**).</span></span>  
  
 <span data-ttu-id="f6bc5-160">Para obter mais informações sobre as Web Parts preteridas, consulte [Exibir e explorar relatórios de modo nativo usando o SharePoint Web Parts (SSRS)](https://msdn.microsoft.com/library/ms159772.aspx)</span><span class="sxs-lookup"><span data-stu-id="f6bc5-160">For more information on the deprecated web parts, see [View and Explore Native Mode Reports Using SharePoint Web Parts (SSRS)](https://msdn.microsoft.com/library/ms159772.aspx)</span></span>  
  
##  <a name="sql-server-2012-reporting-services-deprecated-features"></a><a name="bkmk_2012"></a><span data-ttu-id="f6bc5-161">SQL Server 2012 Reporting Services recursos preteridos</span><span class="sxs-lookup"><span data-stu-id="f6bc5-161">SQL Server 2012 Reporting Services Deprecated Features</span></span>  
 <span data-ttu-id="f6bc5-162">Esta seção descreve os recursos do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] preteridos no [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f6bc5-162">This section describes [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features deprecated in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span></span>  
  
### <a name="html-rendering-extension-device-information-settings"></a><span data-ttu-id="f6bc5-163">Configurações de informações de dispositivos para extensões de renderização HTML</span><span class="sxs-lookup"><span data-stu-id="f6bc5-163">HTML Rendering Extension Device Information Settings</span></span>  
 <span data-ttu-id="f6bc5-164">As configurações de informações de dispositivos da extensão de renderização HTML a seguir foram preteridas.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-164">The following device information settings for the HTML rendering extension are deprecated.</span></span>  
  
-   <span data-ttu-id="f6bc5-165">ActionScript</span><span class="sxs-lookup"><span data-stu-id="f6bc5-165">ActionScript</span></span>  
  
-   <span data-ttu-id="f6bc5-166">ActiveXControls</span><span class="sxs-lookup"><span data-stu-id="f6bc5-166">ActiveXControls</span></span>  
  
-   <span data-ttu-id="f6bc5-167">GetImage</span><span class="sxs-lookup"><span data-stu-id="f6bc5-167">GetImage</span></span>  
  
-   <span data-ttu-id="f6bc5-168">OnlyVisibleStyles</span><span class="sxs-lookup"><span data-stu-id="f6bc5-168">OnlyVisibleStyles</span></span>  
  
-   <span data-ttu-id="f6bc5-169">ReplacementRoot</span><span class="sxs-lookup"><span data-stu-id="f6bc5-169">ReplacementRoot</span></span>  
  
-   <span data-ttu-id="f6bc5-170">ResourceStreamRoot</span><span class="sxs-lookup"><span data-stu-id="f6bc5-170">ResourceStreamRoot</span></span>  
  
-   <span data-ttu-id="f6bc5-171">StreamRoot</span><span class="sxs-lookup"><span data-stu-id="f6bc5-171">StreamRoot</span></span>  
  
-   <span data-ttu-id="f6bc5-172">UsePx</span><span class="sxs-lookup"><span data-stu-id="f6bc5-172">UsePx</span></span>  
  
-   <span data-ttu-id="f6bc5-173">Zoom</span><span class="sxs-lookup"><span data-stu-id="f6bc5-173">Zoom</span></span>  
  
 <span data-ttu-id="f6bc5-174">Para obter mais informações sobre a extensão de renderização HTML, consulte [HTML Device Information Settings](html-device-information-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f6bc5-174">For more information on the HTML rendering extension, see [HTML Device Information Settings](html-device-information-settings.md)</span></span>  
  
### <a name="microsoft-word-and-microsoft-excel-1997-2003-rendering"></a><span data-ttu-id="f6bc5-175">Renderização do Microsoft Word e do Microsoft Excel 1997-2003</span><span class="sxs-lookup"><span data-stu-id="f6bc5-175">Microsoft Word and Microsoft Excel 1997-2003 Rendering</span></span>  
 <span data-ttu-id="f6bc5-176">As [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] extensões de renderização BIFF8 são [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] relatadas para o [!INCLUDE[msCoName](../includes/msconame-md.md)] formato de arquivo de intercâmbio binário do Word e [!INCLUDE[msCoName](../includes/msconame-md.md)] Excel 1997-2003.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-176">The[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] BIFF8 rendering extensions [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports to the [!INCLUDE[msCoName](../includes/msconame-md.md)] Word and [!INCLUDE[msCoName](../includes/msconame-md.md)] Excel 1997-2003 binary interchange file format.</span></span> [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="f6bc5-177">inclui extensões que são renderizadas no [!INCLUDE[msCoName](../includes/msconame-md.md)] formato XML aberto do Office 2007-2010.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-177">includes extensions that render in the [!INCLUDE[msCoName](../includes/msconame-md.md)] Office 2007-2010 Open XML format.</span></span>  
  
### <a name="report-definition-language-rdl-2005-and-earlier"></a><span data-ttu-id="f6bc5-178">Linguagem RDL 2005 e versões anteriores</span><span class="sxs-lookup"><span data-stu-id="f6bc5-178">Report Definition Language (RDL) 2005 and Earlier</span></span>  
 <span data-ttu-id="f6bc5-179">A linguagem RDL 2005 e as versões anteriores foram preteridos.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-179">Report Definition Language (RDL) 2005 and earlier is deprecated.</span></span> <span data-ttu-id="f6bc5-180">Para obter mais informações sobre o RDL, consulte [linguagem de definição de relatório &#40;&#41;SSRS ](reports/report-definition-language-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f6bc5-180">For more information about RDL, see [Report Definition Language &#40;SSRS&#41;](reports/report-definition-language-ssrs.md).</span></span>  
  
 <span data-ttu-id="f6bc5-181">Para obter mais informações como atualizar relatórios, consulte [Upgrade Reports](install-windows/upgrade-reports.md).</span><span class="sxs-lookup"><span data-stu-id="f6bc5-181">For more information on upgrading reports, see [Upgrade Reports](install-windows/upgrade-reports.md).</span></span>  
  
### <a name="sql-server-2005-and-earlier-custom-report-items"></a><span data-ttu-id="f6bc5-182">Itens de relatório personalizados do SQL Server 2005 e versões anteriores</span><span class="sxs-lookup"><span data-stu-id="f6bc5-182">SQL Server 2005 and earlier Custom Report Items</span></span>  
 <span data-ttu-id="f6bc5-183">Os itens de relatório personalizados (CRI) compilados para [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 e anteriores foram preteridos.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-183">Custom Report Items (CRI) compiled for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 and earlier are deprecated.</span></span>  
  
### <a name="reporting-services-snapshots-2005-and-earlier"></a><span data-ttu-id="f6bc5-184">Instantâneos do Reporting Services 2005 e versões anteriores</span><span class="sxs-lookup"><span data-stu-id="f6bc5-184">Reporting Services Snapshots 2005 and earlier</span></span>  
 [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="f6bc5-185">os instantâneos renderizados com [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 e anteriores são preteridos.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-185">snapshots rendered with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] 2005 and earlier are deprecated.</span></span>  
  
### <a name="report-models"></a><span data-ttu-id="f6bc5-186">Modelos de relatório</span><span class="sxs-lookup"><span data-stu-id="f6bc5-186">Report Models</span></span>  
 <span data-ttu-id="f6bc5-187">Os modelos de relatório SMDL (linguagem de modelagem semântica) foram preteridos.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-187">Semantic modeling language (SMDL) report models are deprecated.</span></span> <span data-ttu-id="f6bc5-188">Embora você possa continuar usando modelos de relatório existentes como fontes de dados em [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] relatórios, você deve considerar atualizar seus relatórios para remover sua dependência em modelos de relatório.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-188">Although you can you continue to use existing report models as data sources in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)][!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports you should consider updating your reports to remove their dependency on report models.</span></span>  
  
 [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="f6bc5-189">Não [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] inclui ferramentas para criar ou atualizar modelos de relatório.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-189">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] does not include tools for creating or updating report models.</span></span> <span data-ttu-id="f6bc5-190">Para obter mais informações, consulte [alterações significativas em SQL Server Reporting Services no SQL Server 2014](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="f6bc5-190">For more information, see [Breaking Changes in SQL Server Reporting Services in SQL Server 2014](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md).</span></span>  
  
### <a name="deprecated-methods-in-the-web-service-endpoint"></a><span data-ttu-id="f6bc5-191">Métodos preteridos no ponto de extremidade de serviço Web</span><span class="sxs-lookup"><span data-stu-id="f6bc5-191">Deprecated Methods in the Web Service Endpoint</span></span>  
 <span data-ttu-id="f6bc5-192">As operações a seguir foram preteridas no ponto de extremidade do serviço Web do <xref:ReportService2010.ReportingService2010>:</span><span class="sxs-lookup"><span data-stu-id="f6bc5-192">The following operations are deprecated in the <xref:ReportService2010.ReportingService2010> Web service endpoint:</span></span>  
  
-   <xref:ReportService2010.ReportingService2010.GetProperties%2A>  
  
-   <xref:ReportService2010.ReportingService2010.IsSSLRequired%2A>  
  
##  <a name="sql-server-2008-r2-reporting-services-deprecated-features"></a><a name="bkmk_kj"></a><span data-ttu-id="f6bc5-193">SQL Server 2008 R2 Reporting Services recursos preteridos</span><span class="sxs-lookup"><span data-stu-id="f6bc5-193">SQL Server 2008 R2 Reporting Services Deprecated Features</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f6bc5-194">Como o SQL Server 2008 R2 é uma atualização de versão secundária do SQL Server 2008, recomendamos que você também revise o conteúdo na seção do SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-194">Because SQL Server 2008 R2 is a minor version upgrade of SQL Server 2008, we recommend that you also review the content in the SQL Server 2008 section.</span></span>  
  
### <a name="report-server-web-service-endpoints"></a><span data-ttu-id="f6bc5-195">Pontos de extremidade do serviço Web Servidor de Relatórios</span><span class="sxs-lookup"><span data-stu-id="f6bc5-195">Report Server Web Service Endpoints</span></span>  
 <span data-ttu-id="f6bc5-196">Os serviços Web <xref:ReportService2005.ReportingService2005> e <xref:ReportService2006.ReportingService2006> foram preteridos nessa versão.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-196">The Web services <xref:ReportService2005.ReportingService2005> and <xref:ReportService2006.ReportingService2006> have been deprecated in this release.</span></span> <span data-ttu-id="f6bc5-197">Estes pontos de extremidade foram substituídos por um novo ponto de extremidade: <xref:ReportService2010.ReportingService2010>.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-197">These endpoints have been replaced by a new endpoint: <xref:ReportService2010.ReportingService2010>.</span></span>  
  
 <span data-ttu-id="f6bc5-198">O novo ponto de extremidade inclui toda a funcionalidade disponível nos pontos de extremidade preteridos e os novos recursos introduzidos no SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="f6bc5-198">The new endpoint includes all the functionality available in the deprecated endpoints and the new features introduced in SQL Server 2008 R2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6bc5-199">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f6bc5-199">See Also</span></span>  
 <span data-ttu-id="f6bc5-200">[O que há de novo &#40;Reporting Services&#41;](what-s-new-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="f6bc5-200">[What's New &#40;Reporting Services&#41;](what-s-new-reporting-services.md) </span></span>  
 <span data-ttu-id="f6bc5-201">[Compatibilidade com versões anteriores](../getting-started/backward-compatibility.md) </span><span class="sxs-lookup"><span data-stu-id="f6bc5-201">[Backward Compatibility](../getting-started/backward-compatibility.md) </span></span>  
 <span data-ttu-id="f6bc5-202">[Alterações de comportamento para SQL Server Reporting Services no SQL Server 2014](behavior-changes-to-sql-server-reporting-services-in-sql-server-2016.md) </span><span class="sxs-lookup"><span data-stu-id="f6bc5-202">[Behavior Changes to SQL Server Reporting Services  in SQL Server 2014](behavior-changes-to-sql-server-reporting-services-in-sql-server-2016.md) </span></span>  
 [<span data-ttu-id="f6bc5-203">Funcionalidade descontinuada do SQL Server Reporting Services no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="f6bc5-203">Discontinued Functionality to SQL Server Reporting Services in SQL Server 2014</span></span>](discontinued-functionality-to-sql-server-reporting-services-in-sql-server.md)  
  
  
