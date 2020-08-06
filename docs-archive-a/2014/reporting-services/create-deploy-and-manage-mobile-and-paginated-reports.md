---
title: Reporting Services (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 11/25/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services]
- SSRS
- reports [Reporting Services], about reports
- Reporting Services
- SQL Server Reporting Services
ms.assetid: b8d18d3d-9db0-43e7-8286-7b46cc3a37ed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0418acaab54032148f4bc6d42d06c97070b89e1e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678658"
---
# <a name="reporting-services-ssrs"></a><span data-ttu-id="3ac23-102">SSRS (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="3ac23-102">Reporting Services (SSRS)</span></span>
  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]<span data-ttu-id="3ac23-103">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]fornece uma gama completa de ferramentas e serviços prontos para uso para ajudá-lo a criar, implantar e gerenciar relatórios para sua organização.</span><span class="sxs-lookup"><span data-stu-id="3ac23-103">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] provides a full range of ready-to-use tools and services to help you create, deploy, and manage reports for your organization.</span></span> <span data-ttu-id="3ac23-104">O [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] inclui recursos de programação que permitem estender e personalizar a sua funcionalidade de relatório.</span><span class="sxs-lookup"><span data-stu-id="3ac23-104">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] includes programming features that enable you to extend and customize your reporting functionality.</span></span>

 [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="3ac23-105">o é uma plataforma de relatórios baseada em servidor que fornece funcionalidade de relatório abrangente para uma variedade de fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="3ac23-105">is a server-based reporting platform that provides comprehensive reporting functionality for a variety of data sources.</span></span> [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="3ac23-106">inclui um conjunto completo de ferramentas para criar, gerenciar e entregar relatórios e APIs que permitem aos desenvolvedores integrar ou estender dados e processamento de relatórios em aplicativos personalizados.</span><span class="sxs-lookup"><span data-stu-id="3ac23-106">includes a complete set of tools for you to create, manage, and deliver reports, and APIs that enable developers to integrate or extend data and report processing in custom applications.</span></span> [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="3ac23-107">as ferramentas funcionam dentro do [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ambiente e são totalmente integradas a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ferramentas e componentes.</span><span class="sxs-lookup"><span data-stu-id="3ac23-107">tools work within the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] environment and are fully integrated with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tools and components.</span></span>

 <span data-ttu-id="3ac23-108">Com o [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], você pode criar relatórios interativos, tabulares, gráficos ou de forma livre de fontes de dados relacionais, multidimensionais ou baseadas em XML.</span><span class="sxs-lookup"><span data-stu-id="3ac23-108">With [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], you can create interactive, tabular, graphical, or free-form reports from relational, multidimensional, or XML-based data sources.</span></span> <span data-ttu-id="3ac23-109">Os relatórios podem incluir visualização de dados rica, inclusive gráficos, mapas e minigráficos.</span><span class="sxs-lookup"><span data-stu-id="3ac23-109">Reports can include rich data visualization, including charts, maps, and sparklines.</span></span> <span data-ttu-id="3ac23-110">Você pode publicar relatórios, agendar o processamento de relatório ou acessar relatórios sob demanda.</span><span class="sxs-lookup"><span data-stu-id="3ac23-110">You can publish reports, schedule report processing, or access reports on-demand.</span></span> <span data-ttu-id="3ac23-111">É possível selecionar entre uma variedade de formatos de exibição, exportar relatórios para outros aplicativos, como [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)], e assinar relatórios publicados.</span><span class="sxs-lookup"><span data-stu-id="3ac23-111">You can select from a variety of viewing formats, export reports to other applications such as [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)], and subscribe to published reports.</span></span> <span data-ttu-id="3ac23-112">Os relatórios criados podem ser exibidos através de uma conexão baseada na Web ou como parte de um aplicativo do [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows ou site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3ac23-112">The reports that you create can be viewed over a Web-based connection or as part of a [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows application or SharePoint site.</span></span> <span data-ttu-id="3ac23-113">Você pode criar também alertas de dados em relatórios publicados em um site do SharePoint e receber mensagens de email quando os dados do relatório forem alterados.</span><span class="sxs-lookup"><span data-stu-id="3ac23-113">You can also create data alerts on reports published to a SharePoint site and receive email messages when report data changes.</span></span>

 <span data-ttu-id="3ac23-114">Para obter mais informações sobre os recursos novos no [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , consulte [o que há de novo &#40;Reporting Services&#41;](../../2014/reporting-services/what-s-new-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="3ac23-114">For more information about features new in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], see [What's New &#40;Reporting Services&#41;](../../2014/reporting-services/what-s-new-reporting-services.md).</span></span>

 <span data-ttu-id="3ac23-115">Para obter informações sobre outros componentes, ferramentas e recursos do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , consulte os [Manuais Online do SQL Server.](../index.yml)</span><span class="sxs-lookup"><span data-stu-id="3ac23-115">For information about other [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] components, tools, and resources, see [SQL Server Books Online](../index.yml).</span></span>

 <span data-ttu-id="3ac23-116">Ícone **Procurar conteúdo por pasta de área** ![Folder icon](media/hlp-16folder.gif "Ícone de pasta") [Reporting Services servidor de relatório](../../2014/reporting-services/reporting-services-report-server.md)</span><span class="sxs-lookup"><span data-stu-id="3ac23-116">**Browse Content by Area** ![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Report Server](../../2014/reporting-services/reporting-services-report-server.md)</span></span>

 <span data-ttu-id="3ac23-117">![Ícone de pasta](media/hlp-16folder.gif "Ícone de pasta") [Reporting Services relatórios &#40;SSRS&#41;](reports/reporting-services-reports-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="3ac23-117">![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Reports &#40;SSRS&#41;](reports/reporting-services-reports-ssrs.md)</span></span>

 <span data-ttu-id="3ac23-118">![Ícone de pasta](media/hlp-16folder.gif "Ícone de pasta") [dados de relatório &#40;SSRS&#41;](report-data/report-data-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="3ac23-118">![Folder icon](media/hlp-16folder.gif "Folder icon") [Report Data &#40;SSRS&#41;](report-data/report-data-ssrs.md)</span></span>

 <span data-ttu-id="3ac23-119">![Ícone de pasta](media/hlp-16folder.gif "Ícone de pasta") [parâmetros de relatório &#40;Construtor de Relatórios e Report Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md)</span><span class="sxs-lookup"><span data-stu-id="3ac23-119">![Folder icon](media/hlp-16folder.gif "Folder icon") [Report Parameters &#40;Report Builder and Report Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md)</span></span>

 <span data-ttu-id="3ac23-120">![Ícone de pasta](media/hlp-16folder.gif "Ícone de pasta") [partes de relatório em Report Designer &#40;SSRS&#41;](report-design/report-parts-in-report-designer-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="3ac23-120">![Folder icon](media/hlp-16folder.gif "Folder icon") [Report Parts in Report Designer &#40;SSRS&#41;](report-design/report-parts-in-report-designer-ssrs.md)</span></span>

 <span data-ttu-id="3ac23-121">![Ícone de pasta](media/hlp-16folder.gif "Ícone de pasta") [agendas](subscriptions/schedules.md)</span><span class="sxs-lookup"><span data-stu-id="3ac23-121">![Folder icon](media/hlp-16folder.gif "Folder icon") [Schedules](subscriptions/schedules.md)</span></span>

 <span data-ttu-id="3ac23-122">![Folder icon](media/hlp-16folder.gif "Ícone de pasta") [Reporting Services de ícone de pasta e &#40;de entrega&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md)</span><span class="sxs-lookup"><span data-stu-id="3ac23-122">![Folder icon](media/hlp-16folder.gif "Folder icon") [Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md)</span></span>

 <span data-ttu-id="3ac23-123">![Ícone de pasta](media/hlp-16folder.gif "Ícone de pasta") [Reporting Services alertas de dados](../ssms/agent/alerts.md)</span><span class="sxs-lookup"><span data-stu-id="3ac23-123">![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Data Alerts](../ssms/agent/alerts.md)</span></span>

 <span data-ttu-id="3ac23-124">![Ícone de pasta](media/hlp-16folder.gif "Ícone de pasta") [Power View](https://office.microsoft.com/excel-help/power-view-explore-visualize-and-present-your-data-HA102835634.aspx)</span><span class="sxs-lookup"><span data-stu-id="3ac23-124">![Folder icon](media/hlp-16folder.gif "Folder icon") [Power View](https://office.microsoft.com/excel-help/power-view-explore-visualize-and-present-your-data-HA102835634.aspx)</span></span>

 <span data-ttu-id="3ac23-125">![Ícone de pasta](media/hlp-16folder.gif "Ícone de pasta") [Reporting Services segurança e proteção](security/reporting-services-security-and-protection.md)</span><span class="sxs-lookup"><span data-stu-id="3ac23-125">![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Security and Protection](security/reporting-services-security-and-protection.md)</span></span>

 <span data-ttu-id="3ac23-126">![Ícone de pasta](media/hlp-16folder.gif "Ícone de pasta") [acesso à URL &#40;SSRS&#41;](url-access-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="3ac23-126">![Folder icon](media/hlp-16folder.gif "Folder icon") [URL Access &#40;SSRS&#41;](url-access-ssrs.md)</span></span>

 <span data-ttu-id="3ac23-127">Extensões de ![ícone de pasta](media/hlp-16folder.gif "Ícone de pasta") [&#40;SSRS&#41;](extensions-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="3ac23-127">![Folder icon](media/hlp-16folder.gif "Folder icon") [Extensions &#40;SSRS&#41;](extensions-ssrs.md)</span></span>

 <span data-ttu-id="3ac23-128">![Ícone de pasta](media/hlp-16folder.gif "Ícone de pasta") [Reporting Services ferramentas](tools/reporting-services-tools.md)</span><span class="sxs-lookup"><span data-stu-id="3ac23-128">![Folder icon](media/hlp-16folder.gif "Folder icon") [Reporting Services Tools](tools/reporting-services-tools.md)</span></span>

 <span data-ttu-id="3ac23-129">![Folder icon](media/hlp-16folder.gif "Ícone de pasta") [Referência de erros e eventos de ícone de pasta &#40;Reporting Services&#41;](troubleshooting/errors-and-events-reference-reporting-services.md)</span><span class="sxs-lookup"><span data-stu-id="3ac23-129">![Folder icon](media/hlp-16folder.gif "Folder icon") [Errors and Events Reference &#40;Reporting Services&#41;](troubleshooting/errors-and-events-reference-reporting-services.md)</span></span>

 <span data-ttu-id="3ac23-130">![Ícone de pasta](media/hlp-16folder.gif "Ícone de pasta") [referência de recurso &#40;Reporting Services&#41;](feature-reference-reporting-services.md)</span><span class="sxs-lookup"><span data-stu-id="3ac23-130">![Folder icon](media/hlp-16folder.gif "Folder icon") [Feature Reference &#40;Reporting Services&#41;](feature-reference-reporting-services.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="3ac23-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3ac23-131">See Also</span></span>
 [<span data-ttu-id="3ac23-132">Central de Recursos do SQL Server</span><span class="sxs-lookup"><span data-stu-id="3ac23-132">SQL Server Resource Center</span></span>](https://go.microsoft.com/fwlink/?linkID=219676)


