---
title: Introdução ao tratamento de exceção no Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], exception handling
- errors [Reporting Services]
- exceptions [Reporting Services]
- Report Server Web service, exception handling
- XML Web service [Reporting Services], exception handling
ms.assetid: 54381870-ce67-482b-aa83-6a838cdbf9b9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 091b1f40d293515617e369b750a5f18dfe12951b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680326"
---
# <a name="introducing-exception-handling-in-reporting-services"></a><span data-ttu-id="16945-102">Introduzindo a manipulação de exceção no Reporting Services</span><span class="sxs-lookup"><span data-stu-id="16945-102">Introducing Exception Handling in Reporting Services</span></span>
  <span data-ttu-id="16945-103">Se o seu aplicativo do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] enviar uma solicitação ao serviço Web Servidor de Relatórios que o serviço não for capaz de processar, ele retornará uma exceção SOAP ao cliente.</span><span class="sxs-lookup"><span data-stu-id="16945-103">If your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] application sends a request to the Report Server Web service that the service is unable to process, the service returns a SOAP exception to the client.</span></span> <span data-ttu-id="16945-104">A manipulação de exceções lançada pelo serviço Web Servidor de Relatórios é uma parte importante dos aplicativos desenvolvidos por você, já que é possível retornar informações úteis para os usuários quando erros ocorrerem.</span><span class="sxs-lookup"><span data-stu-id="16945-104">Handling exceptions thrown by the Report Server Web service is an important part of the applications that you develop because you can return useful information to users when errors occur.</span></span>  
  
 <span data-ttu-id="16945-105">Esta seção contém informações específicas sobre a manipulação de exceções, como impedir a entrada de usuário que não seja válida e o retorno de informações de erro significativas para usuários.</span><span class="sxs-lookup"><span data-stu-id="16945-105">This section contains specific information about handling exceptions, preventing user input that is not valid, and returning meaningful error information to users.</span></span> <span data-ttu-id="16945-106">Para obter informações gerais sobre a manipulação de exceções, consulte "manipulando e gerando exceções" na [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] documentação do SDK.</span><span class="sxs-lookup"><span data-stu-id="16945-106">For general information about exception handling, see "Handling and Throwing Exceptions" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="16945-107">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="16945-107">In This Section</span></span>  
  
|<span data-ttu-id="16945-108">Tópico</span><span class="sxs-lookup"><span data-stu-id="16945-108">Topic</span></span>|<span data-ttu-id="16945-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="16945-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="16945-110">Manipulando exceções no Reporting Services</span><span class="sxs-lookup"><span data-stu-id="16945-110">Handling Exceptions in Reporting Services</span></span>](handling-exceptions-in-reporting-services.md)|<span data-ttu-id="16945-111">Oferece uma visão geral sobre exceções no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e sobre a função de SOAP no retorno de erros de um serviço Web.</span><span class="sxs-lookup"><span data-stu-id="16945-111">Provides an overview of exceptions in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and the role of SOAP in returning errors from a Web service.</span></span>|  
|[<span data-ttu-id="16945-112">Práticas recomendadas para a manipulação de exceção do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="16945-112">Best Practices for Reporting Services Exception Handling</span></span>](best-practices/best-practices-for-reporting-services-exception-handling.md)|<span data-ttu-id="16945-113">Oferece recomendações sobre como manipular exceções no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16945-113">Provides recommendations on how to handle exceptions in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="16945-114">Classe SoapException do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="16945-114">Reporting Services SoapException Class</span></span>](soapexception-class/reporting-services-soapexception-class.md)|<span data-ttu-id="16945-115">Descreve a classe **SoapException** no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16945-115">Describes the **SoapException** class in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="16945-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="16945-116">See Also</span></span>  
 [<span data-ttu-id="16945-117">Criando aplicativos usando o serviço Web e o .NET Framework</span><span class="sxs-lookup"><span data-stu-id="16945-117">Building Applications Using the Web Service and the .NET Framework</span></span>](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md)  
  
  
