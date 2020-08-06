---
title: Usando os cabeçalhos SOAP do Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], SOAP
- Report Server Web service, SOAP
- SOAP headers [Reporting Services]
- SOAP [Reporting Services], headers
- XML Web service [Reporting Services], SOAP
ms.assetid: 306d2c06-a25a-40f8-8a35-13dd32e8841e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f48be183398d4d441b5781c9f9467178c3011e32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681394"
---
# <a name="using-reporting-services-soap-headers"></a><span data-ttu-id="27228-102">Usando cabeçalhos SOAP do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="27228-102">Using Reporting Services SOAP Headers</span></span>
  <span data-ttu-id="27228-103">A comunicação com um método de serviço Web que usa o SOAP segue um formato padrão.</span><span class="sxs-lookup"><span data-stu-id="27228-103">Communication with a Web service method using SOAP follows a standard format.</span></span> <span data-ttu-id="27228-104">Parte desse formato são os dados codificados em um documento XML.</span><span class="sxs-lookup"><span data-stu-id="27228-104">Part of this format is the data that is encoded in an XML document.</span></span> <span data-ttu-id="27228-105">O documento XML consiste em um elemento raiz **Envelope** que, por sua vez, consiste em um elemento **Body** obrigatório e um elemento **Header** opcional.</span><span class="sxs-lookup"><span data-stu-id="27228-105">The XML document consists of a root **Envelope** element, which in turn consists of a required **Body** element and an optional **Header** element.</span></span> <span data-ttu-id="27228-106">O elemento **Body** contém os dados específicos à mensagem.</span><span class="sxs-lookup"><span data-stu-id="27228-106">The **Body** element contains the data specific to the message.</span></span> <span data-ttu-id="27228-107">O elemento **Header** opcional pode conter informações adicionais que não estão diretamente relacionadas à mensagem específica.</span><span class="sxs-lookup"><span data-stu-id="27228-107">The optional **Header** element can contain additional information not directly related to the particular message.</span></span> <span data-ttu-id="27228-108">Cada elemento filho do elemento **Header** é chamado de cabeçalho SOAP.</span><span class="sxs-lookup"><span data-stu-id="27228-108">Each child element of the **Header** element is called a SOAP header.</span></span>  
  
 <span data-ttu-id="27228-109">Embora os cabeçalhos SOAP possam conter dados relacionados à mensagem, eles costumam conter informações processadas pela infraestrutura do servidor Web.</span><span class="sxs-lookup"><span data-stu-id="27228-109">Although the SOAP headers can contain data related to the message, they typically contain information processed by the Web server infrastructure.</span></span>  
  
 <span data-ttu-id="27228-110">Os serviços Web do Servidor de Relatório definem várias classes para uso no cabeçalho SOAP: <xref:ReportService2005.BatchHeader>, <xref:ReportService2010.ItemNamespaceHeader>, <xref:ReportService2010.ServerInfoHeader>, <xref:ReportService2010.TrustedUserHeader> e <xref:ReportExecution2005.ExecutionHeader>.</span><span class="sxs-lookup"><span data-stu-id="27228-110">The Report Server Web services define several classes for use in the SOAP header: <xref:ReportService2005.BatchHeader>, <xref:ReportService2010.ItemNamespaceHeader>, <xref:ReportService2010.ServerInfoHeader>, <xref:ReportService2010.TrustedUserHeader>, and <xref:ReportExecution2005.ExecutionHeader>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="27228-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="27228-111">In This Section</span></span>  
  
|<span data-ttu-id="27228-112">Tópico</span><span class="sxs-lookup"><span data-stu-id="27228-112">Topic</span></span>|<span data-ttu-id="27228-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="27228-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="27228-114">Métodos de processamento em lote</span><span class="sxs-lookup"><span data-stu-id="27228-114">Batching Methods</span></span>](batching-methods.md)|<span data-ttu-id="27228-115">Descreve como processar em lotes várias operações em uma única transação usando o <xref:ReportService2005.BatchHeader>.</span><span class="sxs-lookup"><span data-stu-id="27228-115">Describes how to batch multiple operations into a single transaction using <xref:ReportService2005.BatchHeader>.</span></span>|  
|[<span data-ttu-id="27228-116">Identificando o estado de execução</span><span class="sxs-lookup"><span data-stu-id="27228-116">Identifying Execution State</span></span>](identifying-execution-state.md)|<span data-ttu-id="27228-117">Descreve como gerenciar o estado de sessão no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] usando o **SessionHeader**.</span><span class="sxs-lookup"><span data-stu-id="27228-117">Describes how to manage session state in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] using **SessionHeader**.</span></span>|  
|[<span data-ttu-id="27228-118">Definindo o namespace Item para o método GetProperties</span><span class="sxs-lookup"><span data-stu-id="27228-118">Setting the Item Namespace for the GetProperties Method</span></span>](setting-the-item-namespace-for-the-getproperties-method.md)|<span data-ttu-id="27228-119">Descreve como recuperar propriedades com base no caminho ou na ID de um item usando o método <xref:ReportService2010.ReportingService2010.GetProperties%2A> e o cabeçalho SOAP <xref:ReportService2010.ItemNamespaceHeader>.</span><span class="sxs-lookup"><span data-stu-id="27228-119">Describes how to retrieve properties based on either the path or the ID of an item by using the <xref:ReportService2010.ReportingService2010.GetProperties%2A> method and the <xref:ReportService2010.ItemNamespaceHeader> SOAP header.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="27228-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="27228-120">See Also</span></span>  
 <span data-ttu-id="27228-121">[Criando aplicativos usando o serviço Web e o .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="27228-121">[Building Applications Using the Web Service and the .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="27228-122">Referência técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="27228-122">Technical Reference &#40;SSRS&#41;</span></span>](../technical-reference-ssrs.md)  
  
  
