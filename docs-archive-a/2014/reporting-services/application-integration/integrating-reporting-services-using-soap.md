---
title: Integrando o Reporting Services usando o SOAP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Report Server Web service, application integration
- SOAP [Reporting Services]
- SOAP [Reporting Services], about report integration
- integrating reports [Reporting Services]
- Web service [Reporting Services], application integration
ms.assetid: 6bc17af5-883c-4bfa-87d9-48cd7056d145
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7b6fffd65b22900d7c505c4b50ec290b95fe9ab4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569213"
---
# <a name="integrating-reporting-services-using-soap"></a><span data-ttu-id="99cbe-102">Integrando o Reporting Services por meio do acesso de SOAP</span><span class="sxs-lookup"><span data-stu-id="99cbe-102">Integrating Reporting Services Using SOAP</span></span>
  <span data-ttu-id="99cbe-103">A [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] API SOAP fornece vários pontos de extremidade de serviço Web para o desenvolvimento de soluções de relatório personalizadas.</span><span class="sxs-lookup"><span data-stu-id="99cbe-103">The [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SOAP API provides several Web service endpoints for developing custom reporting solutions.</span></span> <span data-ttu-id="99cbe-104">Atualmente, os pontos de extremidade recaem em duas categorias: gerenciamento e execução.</span><span class="sxs-lookup"><span data-stu-id="99cbe-104">The endpoints currently fall into two categories: management and execution.</span></span> <span data-ttu-id="99cbe-105">A funcionalidade de gerenciamento é exposta por meio dos pontos de extremidade <xref:ReportService2005>, <xref:ReportService2006> e <xref:ReportService2010>.</span><span class="sxs-lookup"><span data-stu-id="99cbe-105">The management functionality is exposed through the <xref:ReportService2005>, <xref:ReportService2006>, and <xref:ReportService2010> endpoints.</span></span> <span data-ttu-id="99cbe-106">O ponto de extremidade <xref:ReportService2005> é usado para o gerenciamento de um servidor de relatório configurado em modo nativo e o ponto de extremidade <xref:ReportService2006> é usado para o gerenciamento de um servidor de relatório configurado para modo integrado do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="99cbe-106">The <xref:ReportService2005> endpoint is used for managing a report server that is configured in native mode and the <xref:ReportService2006> endpoint is used for managing a report server that is configured for SharePoint integrated mode.</span></span> <span data-ttu-id="99cbe-107">O <xref:ReportService2010> mescla as funcionalidades de <xref:ReportService2005> e <xref:ReportService2006> e pode gerenciar um servidor de relatório configurado para modo nativo ou integrado do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="99cbe-107">The <xref:ReportService2010> merges the functionalities of <xref:ReportService2005> and <xref:ReportService2006> and can manage a report server that is configured for either native or SharePoint integrated mode.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="99cbe-108">Os pontos de extremidade <xref:ReportService2005> e <xref:ReportService2006> foram preteridos no [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99cbe-108">The <xref:ReportService2005> and <xref:ReportService2006> endpoints are deprecated in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="99cbe-109">O ponto de extremidade <xref:ReportService2010> inclui as funcionalidades dos dois pontos de extremidade e contém recursos de gerenciamento adicionais.</span><span class="sxs-lookup"><span data-stu-id="99cbe-109">The <xref:ReportService2010> endpoint includes the functionalities of both endpoints and contains additional management features.</span></span>  
  
 <span data-ttu-id="99cbe-110">A funcionalidade de execução é exibida por meio do ponto de extremidade <xref:ReportExecution2005> e é usado quando um servidor de relatório é configurado em modo nativo ou integrado do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="99cbe-110">The execution functionality is exposed through the <xref:ReportExecution2005> endpoint and it is used when the report server is configured in native or SharePoint integrated mode.</span></span> <span data-ttu-id="99cbe-111">Os tópicos a seguir mostram como esses pontos de extremidade podem ser usados para desenvolver soluções de relatório no [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, SharePoint e em aplicativos Web.</span><span class="sxs-lookup"><span data-stu-id="99cbe-111">The following topics show how these endpoints can be used for developing reporting solutions in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, SharePoint, and Web applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="99cbe-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="99cbe-112">In This Section</span></span>  
 [<span data-ttu-id="99cbe-113">Usando a API SOAP em um aplicativo do Windows</span><span class="sxs-lookup"><span data-stu-id="99cbe-113">Using the SOAP API in a Windows Application</span></span>](integrating-reporting-services-using-soap-windows-application.md)  
 <span data-ttu-id="99cbe-114">Descreve como usar a API SOAP para integrar o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] a um ambiente Windows.</span><span class="sxs-lookup"><span data-stu-id="99cbe-114">Describes how to use the SOAP API to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into a Windows environment.</span></span>  
  
 [<span data-ttu-id="99cbe-115">Usando a API SOAP em um aplicativo Web</span><span class="sxs-lookup"><span data-stu-id="99cbe-115">Using the SOAP API in a Web Application</span></span>](integrating-reporting-services-using-soap-web-application.md)  
 <span data-ttu-id="99cbe-116">Descreve como usar a API SOAP para integrar o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] a um ambiente Web.</span><span class="sxs-lookup"><span data-stu-id="99cbe-116">Describes how to use the SOAP API to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into a Web environment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99cbe-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="99cbe-117">See Also</span></span>  
 <span data-ttu-id="99cbe-118">[Integrando Reporting Services em aplicativos](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="99cbe-118">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 <span data-ttu-id="99cbe-119">[Serviço Web Servidor de Relatórios](../report-server-web-service/report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="99cbe-119">[Report Server Web Service](../report-server-web-service/report-server-web-service.md) </span></span>  
 [<span data-ttu-id="99cbe-120">Criando aplicativos usando o serviço Web e o .NET Framework</span><span class="sxs-lookup"><span data-stu-id="99cbe-120">Building Applications Using the Web Service and the .NET Framework</span></span>](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md)  
  
  
