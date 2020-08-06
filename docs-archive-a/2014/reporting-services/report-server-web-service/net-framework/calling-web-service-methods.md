---
title: Chamando métodos do serviço Web | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], SOAP
- Web service [Reporting Services], calls
- calling Web service
- Report Server Web service, SOAP
- XML Web service [Reporting Services], calls
- Report Server Web service, calls
- XML Web service [Reporting Services], SOAP
- SOAP [Reporting Services], calls
ms.assetid: f6f0c6e3-8bb5-4c44-9d19-1872edc72746
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 87f1485b4e3c0ed064e42bb3b411fece96eba8d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679687"
---
# <a name="calling-web-service-methods"></a><span data-ttu-id="f753c-102">Chamando métodos do serviço Web</span><span class="sxs-lookup"><span data-stu-id="f753c-102">Calling Web Service Methods</span></span>
  <span data-ttu-id="f753c-103">Quando você usa uma [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] classe proxy para chamar operações de serviço Web, você faz isso usando os métodos dessa classe.</span><span class="sxs-lookup"><span data-stu-id="f753c-103">When you use a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] proxy class to call Web service operations, you do so by using the methods of that class.</span></span> <span data-ttu-id="f753c-104">Esses métodos respondem como qualquer outro método de uma classe da biblioteca de classes [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f753c-104">These methods respond like any other method of a class in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] class library.</span></span> <span data-ttu-id="f753c-105">Todos os métodos do serviço Web têm acesso público e exigem que você forneça o número e tipos de argumentos adequados.</span><span class="sxs-lookup"><span data-stu-id="f753c-105">All Web service methods have public access and require you to supply the appropriate number of arguments and argument types.</span></span> <span data-ttu-id="f753c-106">Depois de criar uma instância da classe de proxy em seu projeto, você poderá chamar os métodos para realizar operações de relatório por meio do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="f753c-106">After you have created an instance of the proxy class in your project, you can call the methods to perform reporting operations via the report server.</span></span> <span data-ttu-id="f753c-107">O código C# a seguir ilustra o uso do método <xref:ReportService2010.ReportingService2010.ListChildren%2A> da classe proxy <xref:ReportService2010.ReportingService2010>.</span><span class="sxs-lookup"><span data-stu-id="f753c-107">The following C# code illustrates the use of the <xref:ReportService2010.ReportingService2010.ListChildren%2A> method of the <xref:ReportService2010.ReportingService2010> proxy class.</span></span> <span data-ttu-id="f753c-108">Esse código é usado para realizar uma chamada recursiva para o serviço Web que retorna uma matriz dos objetos <xref:ReportService2010.CatalogItem> que contém uma lista de todos os itens do banco de dados do servidor de relatório:</span><span class="sxs-lookup"><span data-stu-id="f753c-108">The code is used to make a recursive call to the Web service that returns an array of <xref:ReportService2010.CatalogItem> objects that contains a list of all items in the report server database:</span></span>  
  
```vb  
Dim rs As New ReportingService2010()  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
Dim items As CatalogItem() = rs.ListChildren("/", True)  
```  
  
```csharp  
ReportingService2010 rs = new ReportingService2010();  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
CatalogItem[] items = rs.ListChildren("/", true);  
```  
  
## <a name="see-also"></a><span data-ttu-id="f753c-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f753c-109">See Also</span></span>  
 <span data-ttu-id="f753c-110">[Criando aplicativos usando o serviço Web e o .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="f753c-110">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="f753c-111">[Serviço Web Servidor de Relatórios](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="f753c-111">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 [<span data-ttu-id="f753c-112">Referência técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f753c-112">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
