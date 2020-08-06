---
title: Publicar uma fonte de dados compartilhada em uma biblioteca do SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- data sources [Reporting Services], publishing to a SharePoint library
- SharePoint integration [Reporting Services], publishing to a library
- publishing reports [Reporting Services], to a SharePoint library
ms.assetid: 966ed425-3ce2-4e76-8237-3c1c977954ae
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 77ee25535ccb98638ae02ca64e3bcbfc88291c12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679137"
---
# <a name="publish-a-shared-data-source-to-a-sharepoint-library"></a><span data-ttu-id="1f71c-102">Publicar uma fonte de dados compartilhada em uma biblioteca do SharePoint</span><span class="sxs-lookup"><span data-stu-id="1f71c-102">Publish a Shared Data Source to a SharePoint Library</span></span>
  <span data-ttu-id="1f71c-103">Para publicar uma fonte de dados compartilhada em um servidor de relatório executado no modo integrado SharePoint, defina as propriedades do projeto de relatório no Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="1f71c-103">To publish a shared data source to a report server that is running in SharePoint integrated mode, you must set the report project properties in Report Designer.</span></span> <span data-ttu-id="1f71c-104">Nas propriedades do projeto, todas as referências a servidores, relatórios e fontes de dados compartilhadas devem ser URLs totalmente qualificadas.</span><span class="sxs-lookup"><span data-stu-id="1f71c-104">In the project properties, all references to servers, reports, and shared data sources must be fully qualified URLs.</span></span>  
  
 <span data-ttu-id="1f71c-105">Você deve ter permissão de **Membro** ou **Proprietário** no site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1f71c-105">You must have **Member** or **Owner** permission on the SharePoint site.</span></span> <span data-ttu-id="1f71c-106">Para obter mais informações, consulte [Exemplos de URL para itens de relatório publicados em um Servidor de Relatório no modo do SharePoint &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md).</span><span class="sxs-lookup"><span data-stu-id="1f71c-106">For more information, see [URL Examples for Published Report Items on a Report Server in SharePoint Mode &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md).</span></span>  
  
### <a name="to-publish-a-shared-data-source-to-a-sharepoint-site"></a><span data-ttu-id="1f71c-107">Para publicar uma fonte de dados compartilhada em um site do SharePoint</span><span class="sxs-lookup"><span data-stu-id="1f71c-107">To publish a shared data source to a SharePoint site</span></span>  
  
1.  <span data-ttu-id="1f71c-108">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra um projeto do Servidor de Relatório existente ou novo.</span><span class="sxs-lookup"><span data-stu-id="1f71c-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open your existing or new Report Server project.</span></span>  
  
2.  <span data-ttu-id="1f71c-109">No menu **Projeto** , clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="1f71c-109">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="1f71c-110">A _\<project>_ caixa de diálogo **páginas de propriedades** é aberta.</span><span class="sxs-lookup"><span data-stu-id="1f71c-110">The _\<project>_**Property Pages** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="1f71c-111">Escolha a **Configuração** que deseja usar para publicar no site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1f71c-111">Choose the **Configuration** you use to publish to a SharePoint site.</span></span>  
  
4.  <span data-ttu-id="1f71c-112">Para publicar fontes de dados compartilhadas no seu projeto e substituir as fontes de dados compartilhadas publicadas, defina **OverwriteDataSources** como **True**.</span><span class="sxs-lookup"><span data-stu-id="1f71c-112">If you want to publish the shared data sources in your project and overwrite previously published shared data sources, set **OverwriteDataSources** to **True**.</span></span>  
  
5.  <span data-ttu-id="1f71c-113">(Opcional) Para **TargetDataSourceFolder**, digite uma URL em uma biblioteca do SharePoint ou pasta de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="1f71c-113">(Optional) For **TargetDataSourceFolder**, type a URL to a SharePoint library or library folder.</span></span> <span data-ttu-id="1f71c-114">Por exemplo, *http://TestServer/TestSite/Documents/DataSources*.</span><span class="sxs-lookup"><span data-stu-id="1f71c-114">For example, *http://TestServer/TestSite/Documents/DataSources*.</span></span>  
  
     <span data-ttu-id="1f71c-115">Se você não especificar um valor, o valor **TargetReportFolder** será usado.</span><span class="sxs-lookup"><span data-stu-id="1f71c-115">If you do not specify a value, the **TargetReportFolder** value is used.</span></span>  
  
6.  <span data-ttu-id="1f71c-116">Para **TargetReportFolder**, digite uma URL em uma biblioteca ou pasta de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="1f71c-116">For **TargetReportFolder**, type a URL to a library or library folder.</span></span> <span data-ttu-id="1f71c-117">Por exemplo, http:*//TestServer/TestSite/Documents/Reports*.</span><span class="sxs-lookup"><span data-stu-id="1f71c-117">For example, http:*//TestServer/TestSite/Documents/Reports*.</span></span>  
  
7.  <span data-ttu-id="1f71c-118">Para **TargetServerURL**, digite uma URL em um site de nível superior ou subsite do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1f71c-118">For **TargetServerURL**, type a URL to a SharePoint top-level site or subsite.</span></span> <span data-ttu-id="1f71c-119">Se você não especificar um site, o site padrão de nível superior será usado.</span><span class="sxs-lookup"><span data-stu-id="1f71c-119">If you do not specify a site, the default top-level site is used.</span></span> <span data-ttu-id="1f71c-120">Por exemplo, http://*nome_do_servidor*, http://*nome_do_servidor*/*site*ou http://*nome_do_servidor*/*site*/*subsite*.</span><span class="sxs-lookup"><span data-stu-id="1f71c-120">For example, http://*servername*, http://*servername*/*site*, or http://*servername*/*site*/*subsite*.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
9. <span data-ttu-id="1f71c-121">No Gerenciador de Soluções, clique com o botão direito do mouse na fonte de dados compartilhada que você deseja publicar e, em seguida, clique em **Implantar**.</span><span class="sxs-lookup"><span data-stu-id="1f71c-121">In Solution Explorer, right-click the shared data source you want to publish, and click **Deploy**.</span></span> <span data-ttu-id="1f71c-122">A fonte de dados será publicada no local especificado em **TargetDataSourceFolder**.</span><span class="sxs-lookup"><span data-stu-id="1f71c-122">The data source is published to the location specified in **TargetDataSourceFolder**.</span></span> <span data-ttu-id="1f71c-123">Erros de implantação são exibidos na janela Saída.</span><span class="sxs-lookup"><span data-stu-id="1f71c-123">Deployment errors appear in the Output window.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1f71c-124">Após a publicação de uma fonte de dados compartilhada em um site do SharePoint, a extensão de nome de arquivo será alterada para .rsds.</span><span class="sxs-lookup"><span data-stu-id="1f71c-124">After you publish a shared data source to a SharePoint site, the file name extension is changed to .rsds.</span></span> <span data-ttu-id="1f71c-125">Você pode editar e gerenciar uma fonte de dados compartilhada diretamente no site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1f71c-125">You can edit and manage a shared data source directly on the SharePoint site.</span></span> <span data-ttu-id="1f71c-126">Para obter mais informações, consulte [Criar e gerenciar fontes de dados compartilhadas &#40;Reporting Services no modo integrado do SharePoint&#41;](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md).</span><span class="sxs-lookup"><span data-stu-id="1f71c-126">For more information, see [Create and Manage Shared Data Sources &#40;Reporting Services in SharePoint Integrated Mode&#41;](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f71c-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1f71c-127">See Also</span></span>  
 <span data-ttu-id="1f71c-128">[Publicar um relatório em uma biblioteca do SharePoint](publish-a-report-to-a-sharepoint-library.md) </span><span class="sxs-lookup"><span data-stu-id="1f71c-128">[Publish a Report to a SharePoint Library](publish-a-report-to-a-sharepoint-library.md) </span></span>  
 <span data-ttu-id="1f71c-129">[Exemplos de URL para itens de relatório publicados em um servidor de relatório no modo do SharePoint &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md) </span><span class="sxs-lookup"><span data-stu-id="1f71c-129">[URL Examples for Published Report Items on a Report Server in SharePoint Mode &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md) </span></span>  
 <span data-ttu-id="1f71c-130">[Caixa de diálogo páginas de propriedades do projeto](../tools/project-property-pages-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="1f71c-130">[Project Property Pages Dialog Box](../tools/project-property-pages-dialog-box.md) </span></span>  
 <span data-ttu-id="1f71c-131">[Definir propriedades de implantação &#40;Reporting Services&#41;](../tools/set-deployment-properties-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="1f71c-131">[Set Deployment Properties &#40;Reporting Services&#41;](../tools/set-deployment-properties-reporting-services.md) </span></span>  
 <span data-ttu-id="1f71c-132">[Publicando relatórios em um servidor de relatório](publishing-reports-to-a-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="1f71c-132">[Publishing Reports to a Report Server](publishing-reports-to-a-report-server.md) </span></span>  
 [<span data-ttu-id="1f71c-133">Usar uma conexão de dados do Office &#40;.odc&#41; com relatórios &#40;Reporting Services no modo integrado do SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="1f71c-133">Use an Office Data Connection &#40;.odc&#41; with Reports &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../report-data/use-an-office-data-connection-odc-with-reports.md)  
  
  
