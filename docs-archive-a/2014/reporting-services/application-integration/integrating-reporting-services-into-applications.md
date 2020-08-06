---
title: Integrando o Reporting Services em aplicativos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- integrating reports [Reporting Services]
- custom applications [SSRS]
- Reporting Services, application integration
- application integration [Reporting Services]
- reports [Reporting Services], integrating
ms.assetid: 49eb539c-d89b-4291-839a-0ec1a65cd270
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3ab92008c5beb4d931e8e781857d766bb56a1efd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569219"
---
# <a name="integrating-reporting-services-into-applications"></a><span data-ttu-id="38b92-102">Integrando o Reporting Services em aplicativos</span><span class="sxs-lookup"><span data-stu-id="38b92-102">Integrating Reporting Services into Applications</span></span>
  <span data-ttu-id="38b92-103">O [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] é uma plataforma de relatório aberta e extensível criada para fornecer aos desenvolvedores um conjunto abrangente de APIs para soluções de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="38b92-103">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is an open and extensible reporting platform designed to provide developers with a comprehensive set of APIs for developing solutions.</span></span>  
  
 <span data-ttu-id="38b92-104">Há três opções de integração [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] em aplicativos personalizados: o serviço Web servidor de relatórios, também conhecido como [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] API SOAP, os controles ReportViewer para [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] e o acesso à URL.</span><span class="sxs-lookup"><span data-stu-id="38b92-104">There are three options for integrating [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into custom applications: the Report Server Web service, also known as the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SOAP API, the ReportViewer controls for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)], and URL access.</span></span> <span data-ttu-id="38b92-105">Cada opção fornece uma abordagem diferente para a integração do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] com os aplicativos.</span><span class="sxs-lookup"><span data-stu-id="38b92-105">Each option provides a different approach for integrating [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into your applications.</span></span>  
  
## <a name="report-server-web-service"></a><span data-ttu-id="38b92-106">serviço Web Servidor de Relatórios</span><span class="sxs-lookup"><span data-stu-id="38b92-106">Report Server Web Service</span></span>  
 <span data-ttu-id="38b92-107">O serviço Web Servidor de Relatórios é a principal interface de desenvolvimento no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38b92-107">The Report Server Web service is the primary interface for developing against [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="38b92-108">Esteja você desenvolvendo código para gerenciar o seu catálogo de relatórios ou desenvolvendo código para renderizar relatórios em um formato suportado, o serviço Web exibe todos os métodos necessários para a integração do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] aos seus aplicativos.</span><span class="sxs-lookup"><span data-stu-id="38b92-108">Whether you are developing code to manage your report catalog or developing code to render reports to a supported format, the Web service exposes all the necessary methods to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into your applications.</span></span> <span data-ttu-id="38b92-109">Um exemplo desse aplicativo é o Gerenciador de Relatórios, incluído no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]; ele usa o serviço Web para gerenciar o banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="38b92-109">An example of one such application is Report Manager, which is included with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]; it uses the Web service to manage the report server database.</span></span>  
  
## <a name="reportviewer-controls-for-visual-studio"></a><span data-ttu-id="38b92-110">Controles ReportViewer do Visual Studio</span><span class="sxs-lookup"><span data-stu-id="38b92-110">ReportViewer Controls for Visual Studio</span></span>  
 <span data-ttu-id="38b92-111">Os controles ReportViewer incluídos no [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] são usados para a integração da exibição de relatório com os aplicativos.</span><span class="sxs-lookup"><span data-stu-id="38b92-111">The ReportViewer controls included with [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] are used for integrating report viewing into your applications.</span></span> <span data-ttu-id="38b92-112">Existem dois controles: um para aplicativos baseados em Windows Forms e um para aplicativos Web Forms.</span><span class="sxs-lookup"><span data-stu-id="38b92-112">There are two controls: one for Windows Forms-based applications and one for Web Forms applications.</span></span> <span data-ttu-id="38b92-113">Cada controle oferece o recurso de exibição de relatórios implantados como um servidor de relatório além da capacidade de renderizar relatórios existentes em um ambiente onde um servidor de relatório não foi instalado.</span><span class="sxs-lookup"><span data-stu-id="38b92-113">Each control provides the capability for viewing reports that have been deployed to a report server as well as the ability to render reports that exist in an environment where a report server has not been installed.</span></span>  
  
## <a name="url-access"></a><span data-ttu-id="38b92-114">Acesso à URL</span><span class="sxs-lookup"><span data-stu-id="38b92-114">URL Access</span></span>  
 <span data-ttu-id="38b92-115">O acesso à URL é outra opção para a integração da exibição de relatório com os aplicativos, se os controles ReportViewer não forem uma opção.</span><span class="sxs-lookup"><span data-stu-id="38b92-115">URL access is another option for integrating report viewing into your applications if the ReportViewer controls are not an option.</span></span> <span data-ttu-id="38b92-116">Além disso, o acesso à URL é útil para enviar aos usuários, por email, links para relatórios.</span><span class="sxs-lookup"><span data-stu-id="38b92-116">In addition, URL access is useful for sending links to reports to users via e-mail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="38b92-117">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="38b92-117">In This Section</span></span>  
 [<span data-ttu-id="38b92-118">Integrando Reporting Services usando SOAP</span><span class="sxs-lookup"><span data-stu-id="38b92-118">Integrating Reporting Services Using SOAP</span></span>](../application-integration/integrating-reporting-services-using-soap.md)  
 <span data-ttu-id="38b92-119">Descreve como integrar a navegação de relatório do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e o gerenciamento aos seus aplicativos comerciais existentes usando o serviço Web Servidor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="38b92-119">Describes how to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report navigation and management into your existing business applications using the Report Server Web service.</span></span>  
  
 [<span data-ttu-id="38b92-120">Integrando o Reporting Services usando os controles ReportViewer</span><span class="sxs-lookup"><span data-stu-id="38b92-120">Integrating Reporting Services Using the ReportViewer Controls</span></span>](../application-integration/integrating-reporting-services-using-reportviewer-controls.md)  
 <span data-ttu-id="38b92-121">Descreve como integrar a exibição de relatório aos seus aplicativos existentes usando os controles ReportViewer.</span><span class="sxs-lookup"><span data-stu-id="38b92-121">Describes how to integrate report viewing into your existing applications using the ReportViewer controls.</span></span>  
  
 [<span data-ttu-id="38b92-122">Integrando Reporting Services usando o acesso à URL</span><span class="sxs-lookup"><span data-stu-id="38b92-122">Integrating Reporting Services Using URL Access</span></span>](../application-integration/integrating-reporting-services-using-url-access.md)  
 <span data-ttu-id="38b92-123">Descreve como integrar navegação de relatório do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] aos seus aplicativos comerciais existentes usando o acesso à URL.</span><span class="sxs-lookup"><span data-stu-id="38b92-123">Describes how to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report navigation into your existing business applications using URL access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38b92-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="38b92-124">See Also</span></span>  
 <span data-ttu-id="38b92-125">[Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;](../../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="38b92-125">[Report Manager  &#40;SSRS Native Mode&#41;](../../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="38b92-126">[Escolhendo entre o acesso à URL e SOAP](../../../2014/reporting-services/application-integration/choosing-between-url-access-and-soap.md) </span><span class="sxs-lookup"><span data-stu-id="38b92-126">[Choosing Between URL Access and SOAP](../../../2014/reporting-services/application-integration/choosing-between-url-access-and-soap.md) </span></span>  
 <span data-ttu-id="38b92-127">[Referência técnica &#40;SSRS&#41;](../../../2014/reporting-services/technical-reference-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="38b92-127">[Technical Reference &#40;SSRS&#41;](../../../2014/reporting-services/technical-reference-ssrs.md) </span></span>  
 [<span data-ttu-id="38b92-128">Serviço Web do Servidor de Relatório</span><span class="sxs-lookup"><span data-stu-id="38b92-128">Report Server Web Service</span></span>](../report-server-web-service/report-server-web-service.md)  
  
  
