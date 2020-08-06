---
title: Usando métodos seguros do serviço Web | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- SOAP [Reporting Services], secure connections
- Web service [Reporting Services], SOAP
- Report Server Web service, SOAP
- XML Web service [Reporting Services], SOAP
ms.assetid: 87329299-c2ea-4517-9148-d855726768a9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e88a164602f9bbe6ad42c3897285a484cac94466
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684493"
---
# <a name="using-secure-web-service-methods"></a><span data-ttu-id="24b47-102">Usando métodos seguros do serviço Web</span><span class="sxs-lookup"><span data-stu-id="24b47-102">Using Secure Web Service Methods</span></span>
  <span data-ttu-id="24b47-103">Certos métodos do serviço Web Servidor de Relatório podem exigir uma conexão segura quando chamados.</span><span class="sxs-lookup"><span data-stu-id="24b47-103">Certain Report Server Web service methods may require a secure connection when you invoke them.</span></span> <span data-ttu-id="24b47-104">Os métodos que exigem uma conexão segura são determinados pela configuração `SecureConnectionLevel` no arquivo RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="24b47-104">The methods that require a secure connection are determined by the `SecureConnectionLevel` setting in the RSReportServer.config file.</span></span> <span data-ttu-id="24b47-105">O valor da configuração é um valor inteiro com um intervalo válido 0 e superior.</span><span class="sxs-lookup"><span data-stu-id="24b47-105">The value of the setting is an integer value with a valid range of 0 and higher.</span></span> <span data-ttu-id="24b47-106">A tabela a seguir descreve esses valores.</span><span class="sxs-lookup"><span data-stu-id="24b47-106">The following table describes these values.</span></span>  
  
|<span data-ttu-id="24b47-107">Nível</span><span class="sxs-lookup"><span data-stu-id="24b47-107">Level</span></span>|<span data-ttu-id="24b47-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="24b47-108">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="24b47-109">**0**</span><span class="sxs-lookup"><span data-stu-id="24b47-109">**0**</span></span>|<span data-ttu-id="24b47-110">Não é segura.</span><span class="sxs-lookup"><span data-stu-id="24b47-110">Not secure.</span></span> <span data-ttu-id="24b47-111">Chamadas feitas ao API SOAP do Reporting Services não exigem uma conexão segura.</span><span class="sxs-lookup"><span data-stu-id="24b47-111">Calls made to the Reporting Services SOAP API do not require a secure connection.</span></span>|  
|<span data-ttu-id="24b47-112">Maior que **0**</span><span class="sxs-lookup"><span data-stu-id="24b47-112">Greater than **0**</span></span>|<span data-ttu-id="24b47-113">Segura.</span><span class="sxs-lookup"><span data-stu-id="24b47-113">Secure.</span></span> <span data-ttu-id="24b47-114">Todas as chamadas feitas ao API SOAP do Reporting Services exigem uma conexão segura.</span><span class="sxs-lookup"><span data-stu-id="24b47-114">All calls made to the Reporting Services SOAP API require a secure connection.</span></span>|  
  
 <span data-ttu-id="24b47-115">Você pode usar o método <xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A> do serviço Web para retornar uma lista de métodos do serviço Web que exigem uma conexão segura de acordo com a configuração atual do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="24b47-115">You can use the <xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A> method of the Web service to return a list of Web service methods that require a secure connection according to the current configuration of the report server.</span></span> <span data-ttu-id="24b47-116">Em um cenário SSL, avalie a lista de métodos retornados por <xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A> e altere o nome do esquema da URI do serviço Web para "https" ou "http", dependendo do método chamado.</span><span class="sxs-lookup"><span data-stu-id="24b47-116">In an SSL scenario, you should evaluate the list of methods that are returned by <xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A> and change the scheme name of the Web service URI to "https" or "http" depending on the method being called.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24b47-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="24b47-117">See Also</span></span>  
 <span data-ttu-id="24b47-118">[Criando aplicativos usando o serviço Web e o .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="24b47-118">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="24b47-119">Serviço Web do Servidor de Relatório</span><span class="sxs-lookup"><span data-stu-id="24b47-119">Report Server Web Service</span></span>](../report-server-web-service.md)  
  
  
