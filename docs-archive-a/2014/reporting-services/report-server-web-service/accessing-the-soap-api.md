---
title: Acessando a API SOAP | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- XML Web service [Reporting Services], WSDL
- Web service [Reporting Services], SOAP
- calling Web service
- SOAP [Reporting Services], accessing
- Report Server Web service, SOAP
- Web service [Reporting Services], WSDL
- WSDL [Reporting Services]
- XML Web service [Reporting Services], SOAP
- Report Server Web service, WSDL
- referencing WSDL
ms.assetid: 63bb870a-4dbf-46bd-8921-78f8ebe5fd75
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6e8a0c21bb53deff746cfd916b6ae2c96fa0de19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582280"
---
# <a name="accessing-the-soap-api"></a><span data-ttu-id="4f2a9-102">Acessando a API SOAP</span><span class="sxs-lookup"><span data-stu-id="4f2a9-102">Accessing the SOAP API</span></span>
  <span data-ttu-id="4f2a9-103">O serviço Web Serviço de Relatório usa o SOAP sobre HTTP e age como uma interface de comunicações entre programas cliente e o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="4f2a9-103">The Report Server Web service uses Simple Object Access Protocol (SOAP) over HTTP and acts as a communications interface between client programs and the report server.</span></span> <span data-ttu-id="4f2a9-104">O serviço Web oferece dois pontos de extremidade - um para a execução de relatórios e outro para o gerenciamento de relatórios - e consiste em métodos e em um conjunto de objetos de tipo complexo que podem ser usados para o acesso da funcionalidade completa do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f2a9-104">The Web service provides two endpoints - one for report execution and one for report management - and consists of methods and a set of complex type objects that you can use to access the complete functionality of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="4f2a9-105">Para chamar o serviço, referencie a WSDL (Reporting Services Web Services Description Language).</span><span class="sxs-lookup"><span data-stu-id="4f2a9-105">To call the service, you must reference the Reporting Services Web Services Description Language (WSDL).</span></span>  
  
## <a name="referencing-the-reporting-services-wsdl"></a><span data-ttu-id="4f2a9-106">Referenciando a WSDL do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="4f2a9-106">Referencing the Reporting Services WSDL</span></span>  
 <span data-ttu-id="4f2a9-107">Para chamar um serviço Web com êxito, você precisa saber como acessá-lo, a que operações ele dá suporte, que parâmetros ele espera e o que ele retorna.</span><span class="sxs-lookup"><span data-stu-id="4f2a9-107">To call a Web service successfully, you must know how to access the service, what operations the service supports, what parameters the service expects, and what the service returns.</span></span> <span data-ttu-id="4f2a9-108">A WSDL oferece essas informações em um documento XML que pode ser lido ou processado por um computador.</span><span class="sxs-lookup"><span data-stu-id="4f2a9-108">WSDL provides this information in an XML document that can be read or processed by a computer.</span></span>  
  
 <span data-ttu-id="4f2a9-109">Os serviços Web do Servidor de Relatório são expostos em três pontos de extremidade diferentes.</span><span class="sxs-lookup"><span data-stu-id="4f2a9-109">The Report Server Web services are exposed in three different endpoints.</span></span> <span data-ttu-id="4f2a9-110">O nome do arquivo WSDL é diferente para cada ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="4f2a9-110">The name of the WSDL file is different for each endpoint.</span></span> <span data-ttu-id="4f2a9-111">O ponto de extremidade <xref:ReportService2010> contém métodos para gerenciar objetos em um Servidor de Relatório em modo nativo ou integrado do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4f2a9-111">The <xref:ReportService2010> endpoint contains methods for managing objects in a Report Server in either native or SharePoint integrated mode.</span></span> <span data-ttu-id="4f2a9-112">A WSDL para esse ponto de extremidade é acessada por meio do `ReportService2010.asmx?wsdl.`.</span><span class="sxs-lookup"><span data-stu-id="4f2a9-112">The WSDL for this endpoint is accessed through `ReportService2010.asmx?wsdl.`</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4f2a9-113">Os pontos de extremidade <xref:ReportService2005> e <xref:ReportService2006> foram preteridos no [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f2a9-113">The <xref:ReportService2005> and <xref:ReportService2006> endpoints are deprecated in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="4f2a9-114">O ponto de extremidade <xref:ReportService2010> inclui as funcionalidades dos dois pontos de extremidade e contém recursos de gerenciamento adicionais.</span><span class="sxs-lookup"><span data-stu-id="4f2a9-114">The <xref:ReportService2010> endpoint includes the functionalities of both endpoints and contains additional management features.</span></span>  
  
-   <span data-ttu-id="4f2a9-115">O ponto de extremidade <xref:ReportExecution2005> permite que os desenvolvedores processem e renderizem relatórios programaticamente em um Servidor de Relatório.</span><span class="sxs-lookup"><span data-stu-id="4f2a9-115">The <xref:ReportExecution2005> endpoint allows developers to programmatically process and render reports in a Report Server.</span></span> <span data-ttu-id="4f2a9-116">A WSDL para esse ponto de extremidade é acessada por meio de `ReportExecution2005.asmx?wsdl`.</span><span class="sxs-lookup"><span data-stu-id="4f2a9-116">The WSDL for this endpoint is accessed through `ReportExecution2005.asmx?wsdl`.</span></span>  
  
 <span data-ttu-id="4f2a9-117">O WSDL pode ser consumido por kits de desenvolvimento que dão suporte a SOAP e a serviços Web, como o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span><span class="sxs-lookup"><span data-stu-id="4f2a9-117">WSDL can be consumed by development kits that support SOAP and Web services, such as the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span></span>  
  
 <span data-ttu-id="4f2a9-118">O exemplo a seguir mostra o formato da URL para o arquivo WSDL de gerenciamento do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="4f2a9-118">The following example shows the format of the URL to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] management WSDL file:</span></span>  
  
```  
http://server/reportserver/ReportService2010.asmx?wsdl  
```  
  
 <span data-ttu-id="4f2a9-119">A tabela a seguir descreve cada elemento da URL.</span><span class="sxs-lookup"><span data-stu-id="4f2a9-119">The following table describes each element in the URL.</span></span>  
  
|<span data-ttu-id="4f2a9-120">Elemento da URL</span><span class="sxs-lookup"><span data-stu-id="4f2a9-120">URL element</span></span>|<span data-ttu-id="4f2a9-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="4f2a9-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="4f2a9-122">*server*</span><span class="sxs-lookup"><span data-stu-id="4f2a9-122">*server*</span></span>|<span data-ttu-id="4f2a9-123">O nome do servidor no qual o servidor de relatório é implantado.</span><span class="sxs-lookup"><span data-stu-id="4f2a9-123">The name of the server on which the report server is deployed.</span></span>|  
|<span data-ttu-id="4f2a9-124">*ReportServer*</span><span class="sxs-lookup"><span data-stu-id="4f2a9-124">*reportserver*</span></span>|<span data-ttu-id="4f2a9-125">O nome da pasta que contém o serviço Web XML.</span><span class="sxs-lookup"><span data-stu-id="4f2a9-125">The name of the folder that contains the XML Web service.</span></span> <span data-ttu-id="4f2a9-126">Configurado durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="4f2a9-126">This is configured during setup.</span></span>|  
|<span data-ttu-id="4f2a9-127">*\<endpoint name>. asmx*</span><span class="sxs-lookup"><span data-stu-id="4f2a9-127">*\<endpoint name>.asmx*</span></span>|<span data-ttu-id="4f2a9-128">O nome do ponto de extremidade do serviço web.</span><span class="sxs-lookup"><span data-stu-id="4f2a9-128">The name of the web service endpoint.</span></span>|  
  
 <span data-ttu-id="4f2a9-129">Para saber mais sobre o formato WSDL, veja a especificação de WSDL feita pelo W3C (World Wide Web Consortium) em http://www.w3.org/TR/wsdl.</span><span class="sxs-lookup"><span data-stu-id="4f2a9-129">For more information about the WSDL format, see the World Wide Web Consortium (W3C) WSDL specification at http://www.w3.org/TR/wsdl.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f2a9-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4f2a9-130">See Also</span></span>  
 <span data-ttu-id="4f2a9-131">[Criando aplicativos usando o serviço Web e o .NET Framework](net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="4f2a9-131">[Building Applications Using the Web Service and the .NET Framework](net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="4f2a9-132">Serviço Web do Servidor de Relatório</span><span class="sxs-lookup"><span data-stu-id="4f2a9-132">Report Server Web Service</span></span>](report-server-web-service.md)  
  
  
