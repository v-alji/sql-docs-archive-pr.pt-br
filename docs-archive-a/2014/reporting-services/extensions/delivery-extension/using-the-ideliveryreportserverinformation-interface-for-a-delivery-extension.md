---
title: Usando a interface IDeliveryReportServerInformation para uma extensão de entrega | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- IDeliveryReportServerInformation interface
- delivery extensions [Reporting Services], retrieving report server information
ms.assetid: adbce647-18f3-470c-8114-42f8bcc95dc2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 52e137d1a866305ec6435a4940fe98448bce5778
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584022"
---
# <a name="using-the-ideliveryreportserverinformation-interface-for-a-delivery-extension"></a><span data-ttu-id="baa91-102">Usando a interface IDeliveryReportServerInformation para uma extensão de entrega</span><span class="sxs-lookup"><span data-stu-id="baa91-102">Using the IDeliveryReportServerInformation Interface for a Delivery Extension</span></span>
  <span data-ttu-id="baa91-103">A interface de <xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> exibe várias propriedades que você poderá usar para recuperar informações sobre um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="baa91-103">The <xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> interface exposes several properties that you can use to retrieve information about a report server.</span></span> <span data-ttu-id="baa91-104">Você pode usar essas informações para entregar notificações e relatórios.</span><span class="sxs-lookup"><span data-stu-id="baa91-104">You can use this information to deliver notifications and reports.</span></span> <span data-ttu-id="baa91-105">Ao implementar a sua classe de extensão de entrega, você implementa a propriedade <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension.ReportServerInformation%2A> como exigido pela interface de <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension>.</span><span class="sxs-lookup"><span data-stu-id="baa91-105">When implementing your delivery extension class, you implement the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension.ReportServerInformation%2A> property as required by the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> interface.</span></span> <span data-ttu-id="baa91-106">A propriedade de <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension.ReportServerInformation%2A> retorna um objeto que implementa a interface de <xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation>.</span><span class="sxs-lookup"><span data-stu-id="baa91-106">The <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension.ReportServerInformation%2A> property returns an object that implements the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> interface.</span></span> <span data-ttu-id="baa91-107">A partir desse objeto é possível obter uma lista de extensões de renderização atualmente suportadas pelo servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="baa91-107">From this object you can get a list of rendering extensions currently supported by the report server.</span></span>  
  
 <span data-ttu-id="baa91-108">O loop a seguir `for` pode ser usado para armazenar uma lista de extensões de renderização disponíveis atualmente no servidor de relatório em um objeto **ArrayList** .</span><span class="sxs-lookup"><span data-stu-id="baa91-108">The following `for` loop could be used to store a list of rendering extensions currently available on the report server in an **ArrayList** object.</span></span>  
  
```vb  
Dim renderFormats As New ArrayList()  
Dim e As Microsoft.ReportingServices.Interfaces.Extension  
For Each e In  ReportServerInformation.RenderingExtension  
   If e.Visible Then  
      renderFormats.Add(e.Name)  
   End If  
Next e  
```  
  
```csharp  
ArrayList renderFormats = new ArrayList();  
foreach (Microsoft.ReportingServices.Interfaces.Extension e in ReportServerInformation.RenderingExtension)  
{   
   if (e.Visible)  
   {  
      renderFormats.Add(e.Name);  
   }  
}  
```  
  
 <span data-ttu-id="baa91-109">Para obter mais informações sobre a interface <xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation>, consulte [Usando a interface IDeliveryReportServerInformation para uma extensão de entrega](using-the-ideliveryreportserverinformation-interface-for-a-delivery-extension.md).</span><span class="sxs-lookup"><span data-stu-id="baa91-109">For more information about the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> interface, see [Using the IDeliveryReportServerInformation Interface for a Delivery Extension](using-the-ideliveryreportserverinformation-interface-for-a-delivery-extension.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baa91-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="baa91-110">See Also</span></span>  
 <xref:Microsoft.ReportingServices.Interfaces>   
 <span data-ttu-id="baa91-111">[Implementando uma extensão de entrega](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="baa91-111">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="baa91-112">Biblioteca de extensões do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="baa91-112">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
