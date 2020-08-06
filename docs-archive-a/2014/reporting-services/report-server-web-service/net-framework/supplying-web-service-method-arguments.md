---
title: Fornecendo argumentos de método de serviço Web | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Report Server Web service, methods
- Web service [Reporting Services], methods
- methods [Reporting Services], arguments
- XML Web service [Reporting Services], methods
ms.assetid: f7b9ca05-fc4c-4b30-8e5d-172dd0f4a832
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3ef5188934628589751fe92d1839da0efb265766
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684491"
---
# <a name="supplying-web-service-method-arguments"></a><span data-ttu-id="ad7df-102">Fornecendo argumentos de método de serviço Web</span><span class="sxs-lookup"><span data-stu-id="ad7df-102">Supplying Web Service Method Arguments</span></span>
  <span data-ttu-id="ad7df-103">Um método do serviço Web do servidor de relatório envia uma solicitação para o serviço em uma determinada URL usando o SOAP por meio do HTTP.</span><span class="sxs-lookup"><span data-stu-id="ad7df-103">A Report Server Web service method sends a request to the service at a given URL using SOAP over HTTP.</span></span> <span data-ttu-id="ad7df-104">O serviço recebe a solicitação, a processa e, em seguida, retorna uma resposta.</span><span class="sxs-lookup"><span data-stu-id="ad7df-104">The service receives the request, processes it, and then returns a response.</span></span> <span data-ttu-id="ad7df-105">Essas solicitações e respostas estão no formulário de documentos XML.</span><span class="sxs-lookup"><span data-stu-id="ad7df-105">These requests and responses are in the form of XML documents.</span></span>  
  
## <a name="optional-parameters"></a><span data-ttu-id="ad7df-106">Parâmetros Opcionais</span><span class="sxs-lookup"><span data-stu-id="ad7df-106">Optional Parameters</span></span>  
 <span data-ttu-id="ad7df-107">Em alguns casos, um método de serviço Web pode ter parâmetros de entrada opcionais.</span><span class="sxs-lookup"><span data-stu-id="ad7df-107">In some cases, a Web service method can have optional input parameters.</span></span> <span data-ttu-id="ad7df-108">Mesmo se um parâmetro de entrada para um método de serviço Web for opcional, você deverá incluí-lo e definir o valor do parâmetro como `null` (`Nothing` no [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="ad7df-108">Even if an input parameter for a Web service method is optional, you must still include it and set the parameter value to `null` (`Nothing` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span></span> <span data-ttu-id="ad7df-109">A definição de um valor de parâmetro como `null` define o valor do elemento para aquele parâmetro na solicitação de SOAP como `null`.</span><span class="sxs-lookup"><span data-stu-id="ad7df-109">Setting a parameter value to `null` sets the element value for that parameter in the SOAP request to `null`.</span></span>  
  
 <span data-ttu-id="ad7df-110">O exemplo a seguir usa o método <xref:ReportService2010.ReportingService2010.CreateFolder%2A> para criar uma nova pasta nomeada como Vendas de Produto na pasta Vendas.</span><span class="sxs-lookup"><span data-stu-id="ad7df-110">The following example uses the <xref:ReportService2010.ReportingService2010.CreateFolder%2A> method to create a new folder named Product Sales in the Sales folder.</span></span> <span data-ttu-id="ad7df-111">Ao fornecer um valor `null` para as propriedades da pasta, nenhuma propriedade específica para o usuário será fornecida para a pasta:</span><span class="sxs-lookup"><span data-stu-id="ad7df-111">By supplying a `null` value for the folder properties, no user-specific properties are supplied for the folder:</span></span>  
  
```  
// C#  
rs.CreateFolder("Product Sales", "/Sales", null);  
```  
  
## <a name="complex-data-types"></a><span data-ttu-id="ad7df-112">Tipos dados complexos</span><span class="sxs-lookup"><span data-stu-id="ad7df-112">Complex Data Types</span></span>  
 <span data-ttu-id="ad7df-113">A classe principal do serviço Web Servidor de Relatórios é <xref:ReportService2010.ReportingService2010>, que você usa para invocar as operações SOAP ou os métodos Web da classe proxy.</span><span class="sxs-lookup"><span data-stu-id="ad7df-113">The core class of the Report Server Web service is <xref:ReportService2010.ReportingService2010>, which you use to invoke the SOAP operations or Web methods of the proxy class.</span></span> <span data-ttu-id="ad7df-114">Para suportar essa classe e seus métodos, o [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] inclui tipos de dados complexos definidos pelo usuário que são específicos para os parâmetros de entrada e saída dos métodos de serviço Web.</span><span class="sxs-lookup"><span data-stu-id="ad7df-114">To support this class and its methods, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] includes user-defined, complex data types that are specific to the input and output parameters of the Web service methods.</span></span> <span data-ttu-id="ad7df-115">Esses tipos de dados complexos fazem parte da classe de proxy gerada, que você pode usar ao desenvolver no [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] ambiente.</span><span class="sxs-lookup"><span data-stu-id="ad7df-115">These complex data types are part of the generated proxy class, which you can use when developing in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] environment.</span></span>  
  
 <span data-ttu-id="ad7df-116">Quando você gera uma classe de proxy, os tipos de dados complexos que são definidos no arquivo WSDL são representados pelas classes de proxy, que incluem propriedades que correspondem a vários elementos SOAP dos tipos de dados complexos.</span><span class="sxs-lookup"><span data-stu-id="ad7df-116">When you generate a proxy class, the complex data types that are defined in the WSDL file are represented by the classes of the proxy, which include properties that correspond to the various SOAP elements of the complex data types.</span></span> <span data-ttu-id="ad7df-117">As sequências desses tipos de dados se tornam matrizes de objetos que você pode enumerar através de seu código.</span><span class="sxs-lookup"><span data-stu-id="ad7df-117">Sequences of these data types become arrays of objects that you can enumerate through in your code.</span></span> <span data-ttu-id="ad7df-118">Isso elimina a necessidade de trabalhar diretamente com as estruturas de XML enviadas nas mensagens de SOAP.</span><span class="sxs-lookup"><span data-stu-id="ad7df-118">This eliminates the need to work directly with the XML structures sent in SOAP messages.</span></span> <span data-ttu-id="ad7df-119">O [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] trata dessa tradução para você.</span><span class="sxs-lookup"><span data-stu-id="ad7df-119">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] handles that translation for you.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad7df-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ad7df-120">See Also</span></span>  
 <span data-ttu-id="ad7df-121">[Criando aplicativos usando o serviço Web e o .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="ad7df-121">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="ad7df-122">[Serviço Web Servidor de Relatórios](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="ad7df-122">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 [<span data-ttu-id="ad7df-123">Referência técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ad7df-123">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
