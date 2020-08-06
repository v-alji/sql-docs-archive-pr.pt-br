---
title: Publicar um relatório em uma biblioteca do SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- deploying [Reporting Services], reports in SharePoint integrated mode
- SharePoint integration [Reporting Services], publishing to a library
- publishing reports [Reporting Services], to a SharePoint library
ms.assetid: 3f6dfc28-50d8-4231-bd25-871b5f77cce6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 23b74ffb04bf1e13523dcf6ec5d774089d80f73b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679139"
---
# <a name="publish-a-report-to-a-sharepoint-library"></a><span data-ttu-id="de41b-102">Publicar um relatório em uma biblioteca do SharePoint</span><span class="sxs-lookup"><span data-stu-id="de41b-102">Publish a Report to a SharePoint Library</span></span>
  <span data-ttu-id="de41b-103">Para publicar um relatório em um site do SharePoint configurado para integração do SharePoint, você deve definir as propriedades do projeto no Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="de41b-103">To publish a report to a SharePoint site configured for SharePoint integration, you must set the project properties in Report Designer.</span></span> <span data-ttu-id="de41b-104">Nas propriedades do projeto, todas as referências a servidores, relatórios e fontes de dados compartilhadas devem ser URLs totalmente qualificadas.</span><span class="sxs-lookup"><span data-stu-id="de41b-104">In the project properties, all references to servers, reports, and shared data sources must be fully qualified URLs.</span></span> <span data-ttu-id="de41b-105">Na definição de relatórios, todas as referências a sub-relatórios, relatórios detalhados e recursos como imagens com base na Web devem ser URLs totalmente qualificadas.</span><span class="sxs-lookup"><span data-stu-id="de41b-105">In the report definition, all references to subreports, drillthrough reports, and resources such as Web-based images, must be fully qualified URLS.</span></span>  
  
 <span data-ttu-id="de41b-106">Você deve ter permissão de **Membro** ou **Proprietário** no site do SharePoint para definir as propriedades no projeto.</span><span class="sxs-lookup"><span data-stu-id="de41b-106">You must have **Member** or **Owner** permission on the SharePoint site to set the properties on the project.</span></span> <span data-ttu-id="de41b-107">Para obter mais informações, consulte [Exemplos de URL para itens de relatório publicados em um Servidor de Relatório no modo do SharePoint &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md).</span><span class="sxs-lookup"><span data-stu-id="de41b-107">For more information, see [URL Examples for Published Report Items on a Report Server in SharePoint Mode &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md).</span></span>  
  
### <a name="to-publish-a-report-to-a-sharepoint-site"></a><span data-ttu-id="de41b-108">Para publicar um relatório em um site do SharePoint</span><span class="sxs-lookup"><span data-stu-id="de41b-108">To publish a report to a SharePoint site</span></span>  
  
1.  <span data-ttu-id="de41b-109">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra um projeto existente ou novo do Servidor de Relatório.</span><span class="sxs-lookup"><span data-stu-id="de41b-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open an existing or new Report Server project.</span></span>  
  
2.  <span data-ttu-id="de41b-110">No menu **Projeto** , clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="de41b-110">From the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="de41b-111">A _\<project>_ caixa de diálogo **páginas de propriedades** é aberta.</span><span class="sxs-lookup"><span data-stu-id="de41b-111">The _\<project>_**Property Pages** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="de41b-112">Na lista **Configuração** , selecione o nome de uma configuração de build de solução a ser usado para criar e publicar seu relatório.</span><span class="sxs-lookup"><span data-stu-id="de41b-112">In the **Configuration** list, select the name of a solution build configuration to use to build and publish your report.</span></span> <span data-ttu-id="de41b-113">A configuração atual é listada como **ativa**( *\<configuration>* ).</span><span class="sxs-lookup"><span data-stu-id="de41b-113">The current configuration is listed as **Active**(*\<configuration>*).</span></span>  
  
4.  <span data-ttu-id="de41b-114">Para publicar fontes de dados compartilhadas no seu projeto e substituir as fontes de dados compartilhadas publicadas, defina **OverwriteDataSources** como **True**.</span><span class="sxs-lookup"><span data-stu-id="de41b-114">If you want to publish the shared data sources in your project and overwrite previously published shared data sources, set **OverwriteDataSources** to **True**.</span></span>  
  
5.  <span data-ttu-id="de41b-115">Adicional Para **TargetDataSourceFolder**, digite uma URL para uma biblioteca do SharePoint ou pasta de biblioteca (por exemplo, *http://TestServer/TestSite/Documents/DataSources)* .</span><span class="sxs-lookup"><span data-stu-id="de41b-115">(Optional) For **TargetDataSourceFolder**, type a URL to a SharePoint library or library folder (for example, *http://TestServer/TestSite/Documents/DataSources)*.</span></span>  
  
     <span data-ttu-id="de41b-116">Se você não especificar um valor, o valor **TargetReportFolder** será usado.</span><span class="sxs-lookup"><span data-stu-id="de41b-116">If you do not specify a value, the **TargetReportFolder** value is used.</span></span>  
  
6.  <span data-ttu-id="de41b-117">Para **TargetReportFolder**, digite uma URL para uma biblioteca ou pasta de biblioteca (por exemplo, *http://TestServer/TestSite/Documents/Reports)* .</span><span class="sxs-lookup"><span data-stu-id="de41b-117">For **TargetReportFolder**, type a URL to a library or library folder (for example, *http://TestServer/TestSite/Documents/Reports)*.</span></span>  
  
7.  <span data-ttu-id="de41b-118">Para **TargetServerURL**, digite uma URL em um site de nível superior ou subsite do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="de41b-118">For **TargetServerURL**, type a URL to a SharePoint top-level site or subsite.</span></span> <span data-ttu-id="de41b-119">Se você não especificar um site, o site de nível superior padrão será usado (por exemplo,, *http://servername* *http://servername/site* ou *http://servername/site/subsite* ).</span><span class="sxs-lookup"><span data-stu-id="de41b-119">If you do not specify a site, the default top-level site is used (for example, *http://servername*, *http://servername/site*, or *http://servername/site/subsite*).</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
9. <span data-ttu-id="de41b-120">No Gerenciador de Soluções, clique com o botão direito do mouse no relatório que você quer publicar e clique em **Implantar**.</span><span class="sxs-lookup"><span data-stu-id="de41b-120">In Solution Explorer, right-click the report you want to publish, and click **Deploy**.</span></span> <span data-ttu-id="de41b-121">O relatório será publicado no local especificado em **TargetReportFolder**.</span><span class="sxs-lookup"><span data-stu-id="de41b-121">The report is published to the location specified in **TargetReportFolder**.</span></span> <span data-ttu-id="de41b-122">Erros de implantação são exibidos na janela Saída.</span><span class="sxs-lookup"><span data-stu-id="de41b-122">Deployment errors appear in the Output window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de41b-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="de41b-123">See Also</span></span>  
 <span data-ttu-id="de41b-124">[Caixa de diálogo páginas de propriedades do projeto](../tools/project-property-pages-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="de41b-124">[Project Property Pages Dialog Box](../tools/project-property-pages-dialog-box.md) </span></span>  
 <span data-ttu-id="de41b-125">[Definir propriedades de implantação &#40;Reporting Services&#41;](../tools/set-deployment-properties-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="de41b-125">[Set Deployment Properties &#40;Reporting Services&#41;](../tools/set-deployment-properties-reporting-services.md) </span></span>  
 <span data-ttu-id="de41b-126">[Publicando relatórios em um servidor de relatório](publishing-reports-to-a-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="de41b-126">[Publishing Reports to a Report Server](publishing-reports-to-a-report-server.md) </span></span>  
 <span data-ttu-id="de41b-127">[Exemplos de URL para itens de relatório publicados em um servidor de relatório no modo do SharePoint &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md) </span><span class="sxs-lookup"><span data-stu-id="de41b-127">[URL Examples for Published Report Items on a Report Server in SharePoint Mode &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md) </span></span>  
 [<span data-ttu-id="de41b-128">Usar uma conexão de dados do Office &#40;.odc&#41; com relatórios &#40;Reporting Services no modo integrado do SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="de41b-128">Use an Office Data Connection &#40;.odc&#41; with Reports &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../report-data/use-an-office-data-connection-odc-with-reports.md)  
  
  
