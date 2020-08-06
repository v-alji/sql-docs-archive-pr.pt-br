---
title: Configuração e administração de um servidor de relatório (Reporting Services modo do SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 11/25/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 846e86d0-fbbb-426c-97f9-f179cd42b390
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ce7c1f524eec4785ddbc25d95c641d070ecbf408
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684607"
---
# <a name="configuration-and-administration-of-a-report-server-reporting-services-sharepoint-mode"></a><span data-ttu-id="efa38-102">Configuração e administração de um servidor de relatórios (modo do SharePoint do Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="efa38-102">Configuration and Administration of a Report Server (Reporting Services SharePoint Mode)</span></span>
  [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="efa38-103">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] o é uma plataforma de relatórios baseada em servidor que fornece uma gama completa de ferramentas e serviços prontos para uso para ajudá-lo a criar, implantar e gerenciar relatórios para sua organização, bem como recursos de programação que permitem estender e personalizar sua funcionalidade de relatório.</span><span class="sxs-lookup"><span data-stu-id="efa38-103">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] is a server-based reporting platform that provides a full range of ready-to-use tools and services to help you create, deploy, and manage reports for your organization, as well as programming features that enable you to extend and customize your reporting functionality.</span></span> <span data-ttu-id="efa38-104">Você pode integrar seu ambiente de relatório com um produto do SharePoint para experimentar os benefícios de usar o ambiente de colaboração fornecidos por sites do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="efa38-104">You can integrate your reporting environment with a SharePoint product to experience the benefits of using the collaborative environment provided by SharePoint sites.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="efa38-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="efa38-105">In this section</span></span>  
 <span data-ttu-id="efa38-106">As seguintes seções vão ajudar a compreender conceitos, cenários de implantação, procedimentos e muito mais para integrar seu ambiente do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] com um produto ou tecnologia do SharePoint:</span><span class="sxs-lookup"><span data-stu-id="efa38-106">Use the following sections to help you understand concepts, deployment scenarios, procedures, and more for integrating your [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] environment with a SharePoint product or technology:</span></span>  
  
-   <span data-ttu-id="efa38-107">Opções de menu em uma biblioteca do SharePoint</span><span class="sxs-lookup"><span data-stu-id="efa38-107">Menu options in a SharePoint document library</span></span>  
  
    -   [<span data-ttu-id="efa38-108">Gerenciador de Alertas de Dados para Usuários do SharePoint</span><span class="sxs-lookup"><span data-stu-id="efa38-108">Data Alert Manager for SharePoint Users</span></span>](../../2014/reporting-services/data-alert-manager-for-sharepoint-users.md)  
  
    -   [<span data-ttu-id="efa38-109">Criar e gerenciar assinaturas de servidores de relatório no modo SharePoint</span><span class="sxs-lookup"><span data-stu-id="efa38-109">Create and Manage Subscriptions for SharePoint Mode Report Servers</span></span>](subscriptions/create-and-manage-subscriptions-for-sharepoint-mode-report-servers.md)  
  
    -   [<span data-ttu-id="efa38-110">Atualizar credenciais em fontes de dados de relatório de um site do SharePoint</span><span class="sxs-lookup"><span data-stu-id="efa38-110">Update Credentials in Report Data Sources from a SharePoint Site</span></span>](report-data/update-credentials-in-report-data-sources-from-a-sharepoint-site.md)  
  
    -   [<span data-ttu-id="efa38-111">Gerenciar conjuntos de dados compartilhados</span><span class="sxs-lookup"><span data-stu-id="efa38-111">Manage Shared Datasets</span></span>](report-data/manage-shared-datasets.md)  
  
    -   [<span data-ttu-id="efa38-112">Definir parâmetros em um relatório publicado &#40;Reporting Services no modo integrado do SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="efa38-112">Set Parameters on a Published Report &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](report-design/set-parameters-on-a-published-report-sharepoint-integrated-mode.md)  
  
    -   [<span data-ttu-id="efa38-113">Definir opções de processamento &#40;Reporting Services no modo integrado do SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="efa38-113">Set Processing Options &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../../2014/reporting-services/set-processing-options-reporting-services-in-sharepoint-integrated-mode.md)  
  
    -   [<span data-ttu-id="efa38-114">Opções de atualização do cache &#40;Gerenciador de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="efa38-114">Cache Refresh Options &#40;Report Manager&#41;</span></span>](../../2014/reporting-services/cache-refresh-options-report-manager.md)  
  
-   [<span data-ttu-id="efa38-115">Reporting Services recursos do conjunto de sites</span><span class="sxs-lookup"><span data-stu-id="efa38-115">Reporting Services Site Collection Features</span></span>](../../2014/reporting-services/reporting-services-site-collection-features.md)  
  
-   [<span data-ttu-id="efa38-116">Ativar o servidor de relatório e os recursos de integração do Power View no SharePoint</span><span class="sxs-lookup"><span data-stu-id="efa38-116">Activate the Report Server and Power View Integration Features in SharePoint</span></span>](activate-the-report-server-and-power-view-integration-features-in-sharepoint.md)  
  
-   [<span data-ttu-id="efa38-117">Configurações de Site e Recursos de Site do Reporting Services &#40;Modo SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="efa38-117">Reporting Services Site Settings and Site Features&#40;SharePoint Mode&#41;</span></span>](../../2014/reporting-services/reporting-services-site-settings-and-site-features-sharepoint-mode.md)  
  
-   [<span data-ttu-id="efa38-118">Ativar o recurso de sincronização de relatório do Servidor de Relatório na Administração Central do SharePoint</span><span class="sxs-lookup"><span data-stu-id="efa38-118">Activate the Report Server File Sync Feature in SharePoint Central Administration</span></span>](../../2014/reporting-services/activate-report-server-file-sync-feature-sharepoint-central-administration.md)  
  
-   [<span data-ttu-id="efa38-119">Adicione tipos de conteúdo do servidor de relatório a uma biblioteca &#40;Reporting Services no modo integrado do SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="efa38-119">Add Report Server Content Types to a Library &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../../2014/reporting-services/add-reporting-services-content-types-to-a-sharepoint-library.md)  
  
-   [<span data-ttu-id="efa38-120">Relatórios em Modo Local vs. em modo Conectado no Visualizador de Relatórios &#40;Reporting Services no modo do SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="efa38-120">Local Mode vs. Connected Mode Reports in the Report Viewer &#40;Reporting Services in SharePoint Mode&#41;</span></span>](../../2014/reporting-services/local-vs-connected-mode-report-viewer-reporting-services-sharepoint-mode.md)  
  
-   [<span data-ttu-id="efa38-121">Carregar documentos em uma biblioteca do SharePoint &#40;Reporting Services no modo do SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="efa38-121">Upload Documents to a SharePoint Library &#40;Reporting Services in SharePoint Mode&#41;</span></span>](../../2014/reporting-services/upload-documents-to-a-sharepoint-library-reporting-services-in-sharepoint-mode.md)  
  
-   [<span data-ttu-id="efa38-122">Definir opções de processamento &#40;Reporting Services no modo integrado do SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="efa38-122">Set Processing Options &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../../2014/reporting-services/set-processing-options-reporting-services-in-sharepoint-integrated-mode.md)  
  
 <span data-ttu-id="efa38-123">Para obter mais informações gerais sobre [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], consulte [Reporting Services &#40;SSRS&#41;](create-deploy-and-manage-mobile-and-paginated-reports.md) nos Manuais Online do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="efa38-123">For more general information about [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], see [Reporting Services &#40;SSRS&#41;](create-deploy-and-manage-mobile-and-paginated-reports.md) in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="efa38-124">Para obter informações sobre outros componentes, ferramentas e recursos do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , consulte os [Manuais Online do SQL Server.](../index.yml)</span><span class="sxs-lookup"><span data-stu-id="efa38-124">For information about other [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] components, tools, and resources, see [SQL Server Books Online](../index.yml).</span></span>  
  
  
