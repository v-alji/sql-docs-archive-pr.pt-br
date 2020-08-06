---
title: Reporting Services a instalação do modo do SharePoint (SharePoint 2010 e SharePoint 2013) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- default configuration [Reporting Services]
- installing Reporting Services, SharePoint integrated mode
- installation options [Reporting Services]
ms.assetid: ac6cba68-2665-4a39-8fa3-cb7d7e6723c0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c27b6f9fbeebcc896b1a6097cb51e8d2e15924bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569839"
---
# <a name="reporting-services-sharepoint-mode-installation-sharepoint-2010-and-sharepoint-2013"></a><span data-ttu-id="2a86c-102">Instalação do modo do SharePoint do Reporting Services (SharePoint 2010 e SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="2a86c-102">Reporting Services SharePoint Mode Installation (SharePoint 2010 and SharePoint 2013)</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]<span data-ttu-id="2a86c-103">no modo do SharePoint, há uma coleção de componentes de servidor que fornecem geração e entrega de relatórios, com base em [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[msCoName](../../includes/msconame-md.md)] produtos e SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2a86c-103">in SharePoint mode is a collection of server components that provide report generation and delivery, based on [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[msCoName](../../includes/msconame-md.md)] SharePoint products.</span></span>  
  
 <span data-ttu-id="2a86c-104">A execução do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] em modo do SharePoint fornece o [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] e recursos de alerta de dados.</span><span class="sxs-lookup"><span data-stu-id="2a86c-104">Running [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in SharePoint mode provides the [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] and data alerting features.</span></span> <span data-ttu-id="2a86c-105">Para obter mais informações sobre os recursos no modo do SharePoint, consulte a seção "suporte a recursos e diferenças de comportamento por modo de servidor" em [Reporting Services servidor de relatório](../reporting-services-report-server.md)</span><span class="sxs-lookup"><span data-stu-id="2a86c-105">For more information regarding features in SharePoint mode, see the section "Feature Support and Behavior Differences by Server Mode" in [Reporting Services Report Server](../reporting-services-report-server.md)</span></span>  
  
 <span data-ttu-id="2a86c-106">Há duas instalações fundamentais necessárias ao [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] no modo do SharePoint:</span><span class="sxs-lookup"><span data-stu-id="2a86c-106">There are two fundamental installations needed for [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in SharePoint mode:</span></span>  
  
|<span data-ttu-id="2a86c-107">Instalação</span><span class="sxs-lookup"><span data-stu-id="2a86c-107">Installation</span></span>|<span data-ttu-id="2a86c-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="2a86c-108">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="2a86c-109">O [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] suplemento para produtos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2a86c-109">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] add-in for SharePoint products.</span></span>|<span data-ttu-id="2a86c-110">O suplemento instala páginas e recursos de interface do usuário [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] em um servidor front-end de Web do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2a86c-110">The add-in installs the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] user interface (UI) pages and features on a SharePoint web front-end server.</span></span> <span data-ttu-id="2a86c-111">Os recursos de interface do usuário incluem o [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)], páginas de administração na Administração Central do SharePoint, páginas de recursos usadas em bibliotecas de documentos do SharePoint e páginas de alertas de dados do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2a86c-111">The UI features include [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)], administration pages in SharePoint Central Administration, feature pages used within SharePoint document libraries, and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Data Alerting pages.</span></span>|  
|<span data-ttu-id="2a86c-112">O [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] servidor de relatório instalado no modo do SharePoint</span><span class="sxs-lookup"><span data-stu-id="2a86c-112">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report server installed in SharePoint Mode</span></span>|<span data-ttu-id="2a86c-113">O servidor de relatório controla o processamento e a renderização de dados e de relatórios, bem como a assinatura e o processamento de Alerta de Dados</span><span class="sxs-lookup"><span data-stu-id="2a86c-113">The report server handles the data and report processing and rendering as well subscription and Data Alert processing.</span></span> <span data-ttu-id="2a86c-114">O servidor de relatório no modo do SharePoint é projetado e instalado como um Serviço Compartilhado do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2a86c-114">The SharePoint mode report server is architected and installed as a SharePoint Shared Service.</span></span>|  
  
 <span data-ttu-id="2a86c-115">Para instalar o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], use a mídia de instalação do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a86c-115">To install [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], use the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] installation media.</span></span>  
  
 <span data-ttu-id="2a86c-116">Para obter instruções sobre cenários de implantação avançada, consulte [lista de verificação de implantação: Reporting Services, Power View e PowerPivot para SharePoint](../../sql-server/install/deployment-checklist-reporting-services-power-view-power-pivot-for-sharepoint.md) e lista de verificação de [implantação: instalar Reporting Services em um farm existente do SharePoint](../../sql-server/install/deployment-checklist-install-reporting-services-existing-sharepoint-farm.md).</span><span class="sxs-lookup"><span data-stu-id="2a86c-116">For instructions on advanced deployment scenarios, see [Deployment Checklist: Reporting Services, Power View, and PowerPivot for SharePoint](../../sql-server/install/deployment-checklist-reporting-services-power-view-power-pivot-for-sharepoint.md) and [Deployment Checklist: Install Reporting Services into an Existing SharePoint Farm](../../sql-server/install/deployment-checklist-install-reporting-services-existing-sharepoint-farm.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2a86c-117">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="2a86c-117">In This Section</span></span>  
 [<span data-ttu-id="2a86c-118">Combinações com suporte do SharePoint e Reporting Services Server e suplemento &#40;SQL Server 2014&#41;</span><span class="sxs-lookup"><span data-stu-id="2a86c-118">Supported Combinations of SharePoint and Reporting Services Server and Add-in &#40;SQL Server 2014&#41;</span></span>](supported-combinations-of-sharepoint-and-reporting-services-server.md)  
  
 [<span data-ttu-id="2a86c-119">Instalar o Reporting Services SharePoint Mode para SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="2a86c-119">Install Reporting Services SharePoint Mode for SharePoint 2013</span></span>](../../sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2013.md)  
  
 [<span data-ttu-id="2a86c-120">Instalar o Reporting Services modo do SharePoint para SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="2a86c-120">Install Reporting Services SharePoint Mode for SharePoint 2010</span></span>](../../sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2010.md)  
  
 [<span data-ttu-id="2a86c-121">Instalar ou desinstalar o suplemento Reporting Services para SharePoint &#40;SharePoint 2010 e SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="2a86c-121">Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)  
  
 [<span data-ttu-id="2a86c-122">Onde encontrar o suplemento Reporting Services para produtos do SharePoint</span><span class="sxs-lookup"><span data-stu-id="2a86c-122">Where to find the Reporting Services add-in for SharePoint Products</span></span>](where-to-find-the-reporting-services-add-in-for-sharepoint-products.md)  
  
 [<span data-ttu-id="2a86c-123">Adicionar um servidor de relatório a um farm &#40;Expansão do SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2a86c-123">Add an Additional Report Server to a Farm &#40;SSRS Scale-out&#41;</span></span>](add-an-additional-report-server-to-a-farm-ssrs-scale-out.md)  
  
 [<span data-ttu-id="2a86c-124">Adicionar um front-end da Web do Reporting Services a um farm</span><span class="sxs-lookup"><span data-stu-id="2a86c-124">Add an Additional Reporting Services Web Front-end to a Farm</span></span>](add-an-additional-reporting-services-web-front-end-to-a-farm.md)  
  
 [<span data-ttu-id="2a86c-125">Configurar o email para um serviço de aplicativo do Reporting Services &#40;SharePoint 2010 e SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="2a86c-125">Configure E-mail for a Reporting Services Service Application &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](configure-e-mail-for-a-reporting-services-service-application.md)  
  
 [<span data-ttu-id="2a86c-126">Provisionar Assinaturas e Alertas para aplicativos de serviço SSRS</span><span class="sxs-lookup"><span data-stu-id="2a86c-126">Provision Subscriptions and Alerts for SSRS Service Applications</span></span>](provision-subscriptions-and-alerts-for-ssrs-service-applications.md)  
  
 [<span data-ttu-id="2a86c-127">Declarações para o serviço de token do Windows &#40;C2WTS&#41; e Reporting Services</span><span class="sxs-lookup"><span data-stu-id="2a86c-127">Claims to Windows Token Service &#40;C2WTS&#41; and Reporting Services</span></span>](../../sql-server/install/claims-to-windows-token-service-c2wts-and-reporting-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="2a86c-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2a86c-128">See Also</span></span>  
 <span data-ttu-id="2a86c-129">[Fluxo de trabalho e arquitetura de alertas de dados](../reporting-services-data-alerts.md#AlertingWF) </span><span class="sxs-lookup"><span data-stu-id="2a86c-129">[Data Alerts Architecture and Workflow](../reporting-services-data-alerts.md#AlertingWF) </span></span>  
 [<span data-ttu-id="2a86c-130">Gerenciador de Alertas de dados para administradores de alertas</span><span class="sxs-lookup"><span data-stu-id="2a86c-130">Data Alert Manager for Alerting Administrators</span></span>](../data-alert-manager-for-alerting-administrators.md)  
  
  
