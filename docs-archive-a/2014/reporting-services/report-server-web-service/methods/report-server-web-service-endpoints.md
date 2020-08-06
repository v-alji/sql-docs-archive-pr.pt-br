---
title: Pontos de extremidade do serviço Web Servidor de Relatórios | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- management endpoints [Reporting Services]
- Web service [Reporting Services], endpoints
- endpoints [Reporting Services]
- execution endpoints [Reporting Services]
- Report Server Web service, endpoints
ms.assetid: f3f5d85f-9359-4508-bc5a-7f78a3cf7421
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 70281c5171eb37d9888d663542a7850820c81bea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681390"
---
# <a name="report-server-web-service-endpoints"></a><span data-ttu-id="3986e-102">Pontos de extremidade do serviço Web Servidor de Relatórios</span><span class="sxs-lookup"><span data-stu-id="3986e-102">Report Server Web Service Endpoints</span></span>
  <span data-ttu-id="3986e-103">O serviço Web Servidor de Relatórios fornece vários pontos de extremidade para gerenciar um servidor de relatório como também executar relatórios e navegar neles.</span><span class="sxs-lookup"><span data-stu-id="3986e-103">The Report Server Web service provides several endpoints for managing a report server as well as executing and navigating reports.</span></span>  
  
## <a name="the-management-endpoints"></a><span data-ttu-id="3986e-104">Pontos de extremidade de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="3986e-104">The Management Endpoints</span></span>  
 <span data-ttu-id="3986e-105">Existem três pontos de extremidade disponíveis para o gerenciamento de objetos em um servidor de relatório: <xref:ReportService2005>, <xref:ReportService2006> e <xref:ReportService2010>.</span><span class="sxs-lookup"><span data-stu-id="3986e-105">There are three endpoints available for managing objects on a report server, <xref:ReportService2005>, <xref:ReportService2006>, and <xref:ReportService2010>.</span></span> <span data-ttu-id="3986e-106">O ponto de extremidade <xref:ReportService2005> é usado para gerenciar objetos em um servidor de relatório que está configurado para o modo nativo.</span><span class="sxs-lookup"><span data-stu-id="3986e-106">The <xref:ReportService2005> endpoint is used for managing objects on a report server that is configured for native mode.</span></span> <span data-ttu-id="3986e-107">O ponto de extremidade <xref:ReportService2006> é usado para gerenciar objetos em um servidor de relatório que está configurado para o modo integrado do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3986e-107">The <xref:ReportService2006> endpoint is used for managing objects on a report server that is configured for SharePoint integrated mode.</span></span> <span data-ttu-id="3986e-108">O ponto de extremidade <xref:ReportService2010> mescla as funcionalidades do <xref:ReportService2005> e do <xref:ReportService2006> e pode gerenciar objetos em um servidor de relatório configurado para modo integrado ou nativo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3986e-108">The <xref:ReportService2010> endpoint merges the functionalities of <xref:ReportService2005> and <xref:ReportService2006> and can manage objects on a report server that are configured for either native or SharePoint integrated mode.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3986e-109">Quando um servidor de relatório estiver configurado para o modo integrado do SharePoint, as APIs <xref:ReportService2005> retornarão um erro `rsOperationNotSupportedSharePointMode`.</span><span class="sxs-lookup"><span data-stu-id="3986e-109">When a report server is configured for SharePoint integrated mode, the <xref:ReportService2005> APIs will return an `rsOperationNotSupportedSharePointMode` error.</span></span> <span data-ttu-id="3986e-110">Se o servidor de relatório estiver configurado para o modo nativo, as APIs do <xref:ReportService2006> retornarão um erro `rsOperationNotSupportedNativeMode`.</span><span class="sxs-lookup"><span data-stu-id="3986e-110">If the report server is configured for native mode, the <xref:ReportService2006> APIs will return an `rsOperationNotSupportedNativeMode` error.</span></span> <span data-ttu-id="3986e-111">Da mesma forma, quando APIs específicas ao modo no <xref:ReportService2010> forem usadas em modos sem finalidade, as APIs retornarão os respectivos erros.</span><span class="sxs-lookup"><span data-stu-id="3986e-111">Similarly, when mode-specific APIs in <xref:ReportService2010> are used on unintended modes, the APIs will return the respective errors.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3986e-112">Os pontos de extremidade <xref:ReportService2005> e <xref:ReportService2006> foram preteridos no [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3986e-112">The <xref:ReportService2005> and <xref:ReportService2006> endpoints are deprecated in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="3986e-113">O ponto de extremidade <xref:ReportService2010> inclui as funcionalidades dos dois pontos de extremidade e contém recursos de gerenciamento adicionais.</span><span class="sxs-lookup"><span data-stu-id="3986e-113">The <xref:ReportService2010> endpoint includes the functionalities of both endpoints and contains additional management features.</span></span>  
  
 <span data-ttu-id="3986e-114">Se o servidor de relatório estiver configurado para o modo nativo ou o modo integrado do SharePoint, o WSDL do ponto de extremidade de gerenciamento poderá ser acessado por meio de uma das seguintes URLs:</span><span class="sxs-lookup"><span data-stu-id="3986e-114">If the report server is configured for native mode or SharePoint integrate mode, the WSDL for the management endpoint can be accessed using one of the following URL:</span></span>  
  
```  
http://<Server Name>/ReportServer/ReportService2010.asmx?wsdl  
```  
  
 <span data-ttu-id="3986e-115">Para obter mais informações, consulte [Acessando a API SOAP](../accessing-the-soap-api.md).</span><span class="sxs-lookup"><span data-stu-id="3986e-115">For more information, see [Accessing the SOAP API](../accessing-the-soap-api.md).</span></span>  
  
## <a name="the-execution-endpoint"></a><span data-ttu-id="3986e-116">Ponto de extremidade de execução</span><span class="sxs-lookup"><span data-stu-id="3986e-116">The Execution Endpoint</span></span>  
 <span data-ttu-id="3986e-117">O ponto de extremidade do <xref:ReportExecution2005> permite que os desenvolvedores personalizem o processamento e a renderização do relatório de forma mais fácil em um servidor de relatório tanto no modo nativo como no integrado do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3986e-117">The <xref:ReportExecution2005> endpoint makes it easy for developers to customize report processing and rendering from a report server in both native and SharePoint integrated modes.</span></span> <span data-ttu-id="3986e-118">O ponto de extremidade inclui classes e métodos que existiram em versões anteriores do serviço Web Servidor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="3986e-118">The endpoint includes classes and methods that existed in earlier versions of the Report Server Web service.</span></span> <span data-ttu-id="3986e-119">Além disso, muitas classes e métodos novos foram adicionados ao serviço Web Servidor de Relatórios que foram expostos por meio do ponto de extremidade de execução.</span><span class="sxs-lookup"><span data-stu-id="3986e-119">In addition, many new classes and methods have been added to the Report Server Web service that are exposed through the execution endpoint.</span></span>  
  
 <span data-ttu-id="3986e-120">O WSDL para o ponto de extremidade de gerenciamento pode ser acessado através desta URL:</span><span class="sxs-lookup"><span data-stu-id="3986e-120">The WSDL for the management endpoint can be accessed using the following URL:</span></span>  
  
```  
http://<Server Name>/ReportServer/ReportExecution2005.asmx?wsdl  
```  
  
 <span data-ttu-id="3986e-121">Se o servidor de relatório for configurado para o modo de integração do SharePoint, o WSDL poderá ser acessado por meio da URL a seguir:</span><span class="sxs-lookup"><span data-stu-id="3986e-121">If the report server is configured for SharePoint integrate mode, the WSDL can be accessed using the following URL:</span></span>  
  
```  
http://<Server Name>/<Site Name>/_vti_bin/ReportServer/ReportExecution2005.asmx?wsdl  
```  
  
 <span data-ttu-id="3986e-122">Para obter mais informações, consulte [Acessando a API SOAP](../accessing-the-soap-api.md).</span><span class="sxs-lookup"><span data-stu-id="3986e-122">For more information, please see [Accessing the SOAP API](../accessing-the-soap-api.md).</span></span>  
  
## <a name="sharepoint-proxy-endpoints"></a><span data-ttu-id="3986e-123">Pontos de extremidade de proxy do SharePoint</span><span class="sxs-lookup"><span data-stu-id="3986e-123">SharePoint Proxy Endpoints</span></span>  
 <span data-ttu-id="3986e-124">Quando um servidor de relatório for configurado para o modo integrado do SharePoint e o Suplemento [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] tiver sido instalado, um conjunto de pontos de extremidade de proxy será instalado no servidor do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3986e-124">When a report server is configured for SharePoint integrated mode and the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Add-in has been installed, a set of proxy endpoints are installed on the SharePoint server.</span></span> <span data-ttu-id="3986e-125">Os pontos de extremidade de proxy são a API primária para desenvolver soluções de relatório quando um servidor de relatório é configurado para o modo integrado do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3986e-125">The proxy endpoints are the primary API for developing report solutions when a report server is configured for SharePoint integrated mode.</span></span> <span data-ttu-id="3986e-126">Quando você estiver desenvolvendo soluções nos pontos de extremidade de proxy, o Suplemento [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] gerenciará a troca de credenciais entre o SharePoint Server e o servidor de relatório no modo de autenticação de conta confiável.</span><span class="sxs-lookup"><span data-stu-id="3986e-126">When developing against the proxy endpoints, the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Add-in manages the exchange of credentials between the SharePoint server and the report server in Trusted account authentication mode.</span></span> <span data-ttu-id="3986e-127">Quando você estiver desenvolvendo soluções nos pontos de extremidade do servidor de relatório, o aplicativo de chamada terá que gerenciar a troca de credencial no modo de autenticação de conta confiável.</span><span class="sxs-lookup"><span data-stu-id="3986e-127">When developing against the report server endpoints, the calling application will have to manage the credential exchange in Trusted account authentication mode.</span></span> <span data-ttu-id="3986e-128">A tabela a seguir lista os pontos de extremidade que são instalados com o Suplemento [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3986e-128">The following table lists the endpoints that are installed with the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Add-in.</span></span>  
  
|<span data-ttu-id="3986e-129">Ponto de extremidade de proxy</span><span class="sxs-lookup"><span data-stu-id="3986e-129">Proxy Endpoint</span></span>|<span data-ttu-id="3986e-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="3986e-130">Description</span></span>|  
|--------------------|-----------------|  
|<xref:ReportService2006>|<span data-ttu-id="3986e-131">Fornece as APIs para gerenciar um servidor de relatório que é configurado para o modo de integração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3986e-131">Provides the APIs for managing a report server that is configured for SharePoint integrate mode.</span></span> <span data-ttu-id="3986e-132">**Observação:**  Esse ponto de extremidade foi preterido no [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3986e-132">**Note:**  This endpoint is deprecated in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)].</span></span>|  
|<xref:ReportService2010>|<span data-ttu-id="3986e-133">Fornece as APIs para gerenciamento de um servidor de relatório configurado para o modo nativo ou o modo integrado do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3986e-133">Provides the APIs for managing a report server that is configured for either native or SharePoint integrated mode.</span></span>|  
|<xref:ReportExecution2005>|<span data-ttu-id="3986e-134">Fornece as APIs para executar relatórios e navegar neles.</span><span class="sxs-lookup"><span data-stu-id="3986e-134">Provides the APIs for running and navigating reports.</span></span>|  
|<xref:ReportServiceAuthentication>|<span data-ttu-id="3986e-135">Fornece as APIs para autenticar os usuários em um servidor de relatório quando o aplicativo Web do SharePoint é configurado para a Autenticação de Formulários.</span><span class="sxs-lookup"><span data-stu-id="3986e-135">Provides the APIs for authenticating users against a report server when the SharePoint Web application is configured for Forms Authentication.</span></span>|  
  
 <span data-ttu-id="3986e-136">A seguir são apresentadas URLs de exemplo para referenciar os pontos de extremidade de proxy em um site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3986e-136">The following are example URLs for referencing the proxy endpoints on a SharePoint site.</span></span>  
  
```  
http://<Server Name>/<Site Name>/_vti_bin/ReportServer/ReportService2010.asmx  
```  
  
```  
http://<Server Name>/<Site Name>/_vti_bin/ReportServer/ReportExecution2005.asmx  
```  
  
```  
http://<Server Name>/<Site Name>/_vti_bin/ReportServer/ReportServiceAuthentication.asmx  
```  
  
## <a name="see-also"></a><span data-ttu-id="3986e-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3986e-137">See Also</span></span>  
 [<span data-ttu-id="3986e-138">Criando aplicativos usando o serviço Web e o .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3986e-138">Building Applications Using the Web Service and the .NET Framework</span></span>](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md)  
  
  
