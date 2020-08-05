---
title: Melhores práticas para tratamento de exceção do Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- exceptions [Reporting Services], best practices
ms.assetid: 72fecf28-f02e-4338-b50f-0b21f520302d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2e0561c19fbd3e709a0440a55f023f938eabf692
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572939"
---
# <a name="best-practices-for-reporting-services-exception-handling"></a><span data-ttu-id="1ec7f-102">Práticas recomendadas para a manipulação de exceção do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="1ec7f-102">Best Practices for Reporting Services Exception Handling</span></span>
  <span data-ttu-id="1ec7f-103">Durante o desenvolvimento de aplicativos do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], existem várias metodologias que você pode usar para eliminar ou reduzir a ocorrência de exceções.</span><span class="sxs-lookup"><span data-stu-id="1ec7f-103">When developing [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] applications, there are several methodologies you can use to eliminate or reduce the occurrence of exceptions.</span></span> <span data-ttu-id="1ec7f-104">Quando houver exceções, forneça mensagens de erro claras e concisas ao usuário e adicione manipulação de exceção adequada para impedir que seus aplicativos sejam encerrados de forma inesperada.</span><span class="sxs-lookup"><span data-stu-id="1ec7f-104">When exceptions do occur, provide clear and concise error messages to the user, and add adequate exception handling to prevent your applications from ending unexpectedly.</span></span>  
  
 <span data-ttu-id="1ec7f-105">Um aplicativo que envia solicitações ao serviço Web Servidor de Relatório deve fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1ec7f-105">An application that sends requests to the Report Server Web service should do the following:</span></span>  
  
-   <span data-ttu-id="1ec7f-106">Evitar as exceções impedindo quantas solicitações inválidas for possível.</span><span class="sxs-lookup"><span data-stu-id="1ec7f-106">Avoid causing exceptions by preventing as many invalid requests as possible.</span></span>  
  
-   <span data-ttu-id="1ec7f-107">Capturar exceções e fornecer código de manipulação de erro específico sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="1ec7f-107">Catch exceptions and provide specific error-handling code whenever possible.</span></span>  
  
-   <span data-ttu-id="1ec7f-108">Lidar com casos de erro que não lançam exceções.</span><span class="sxs-lookup"><span data-stu-id="1ec7f-108">Deal with error cases that do not throw exceptions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1ec7f-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="1ec7f-109">In This Section</span></span>  
  
|<span data-ttu-id="1ec7f-110">Tópico</span><span class="sxs-lookup"><span data-stu-id="1ec7f-110">Topic</span></span>|<span data-ttu-id="1ec7f-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="1ec7f-111">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="1ec7f-112">Impedindo solicitações inválidas</span><span class="sxs-lookup"><span data-stu-id="1ec7f-112">Preventing Invalid Requests</span></span>](preventing-invalid-requests.md)|<span data-ttu-id="1ec7f-113">Descreve técnicas para impedir que solicitações que não são válidas sejam enviadas ao servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="1ec7f-113">Describes techniques for preventing requests that are not valid from being sent to the report server.</span></span>|  
|[<span data-ttu-id="1ec7f-114">Usando blocos Try e Catch</span><span class="sxs-lookup"><span data-stu-id="1ec7f-114">Using Try and Catch Blocks</span></span>](using-try-and-catch-blocks.md)|<span data-ttu-id="1ec7f-115">Descreve como aprimorar ainda mais a confiabilidade de seu aplicativo com blocos try/catch.</span><span class="sxs-lookup"><span data-stu-id="1ec7f-115">Describes how to further enhance the reliability of your application with try/catch blocks.</span></span>|  
|[<span data-ttu-id="1ec7f-116">Manipulando avisos e casos que não causam exceções</span><span class="sxs-lookup"><span data-stu-id="1ec7f-116">Handling Warnings and Cases That Do Not Cause Exceptions</span></span>](handling-warnings-and-cases-that-do-not-cause-exceptions.md)|<span data-ttu-id="1ec7f-117">Explica como manipular erros que não resultam em uma exceção é lançada pelo [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ec7f-117">Explains how to handle errors that do not result in an exception being thrown by [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="1ec7f-118">Usando a propriedade Detail para manipular erros específicos</span><span class="sxs-lookup"><span data-stu-id="1ec7f-118">Using the Detail Property to Handle Specific Errors</span></span>](using-the-detail-property-to-handle-specific-errors.md)|<span data-ttu-id="1ec7f-119">Explica como tratar erros específicos de forma programática usando a propriedade **Detail** do objeto **SoapException**.</span><span class="sxs-lookup"><span data-stu-id="1ec7f-119">Explains how to programmatically handle specific errors by using the **Detail** property of the **SoapException** object.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1ec7f-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1ec7f-120">See Also</span></span>  
 <span data-ttu-id="1ec7f-121">[Propriedade Detail](../soapexception-class/detail-property.md) </span><span class="sxs-lookup"><span data-stu-id="1ec7f-121">[Detail Property](../soapexception-class/detail-property.md) </span></span>  
 <span data-ttu-id="1ec7f-122">[Introdução à manipulação de exceção no Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="1ec7f-122">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="1ec7f-123">Classe SoapException do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="1ec7f-123">Reporting Services SoapException Class</span></span>](../soapexception-class/reporting-services-soapexception-class.md)  
  
  
