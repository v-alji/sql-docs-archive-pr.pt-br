---
title: Usando a classe RenderedOutputFile para uma extensão de entrega | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- RenderedOutputFile class
- data streams [Reporting Services]
- delivery extensions [Reporting Services], data streams
ms.assetid: 8b591801-42d5-49fa-b710-bf7e6917accf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1dcbf250a367326e5cad528384e533a9ac9d945b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584021"
---
# <a name="using-the-renderedoutputfile-class-for-a-delivery-extension"></a><span data-ttu-id="47fca-102">Usando a classe RenderedOutputFile para uma extensão de entrega</span><span class="sxs-lookup"><span data-stu-id="47fca-102">Using the RenderedOutputFile Class for a Delivery Extension</span></span>
  <span data-ttu-id="47fca-103">A classe de <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> representa um fluxo de dados e informações sobre as propriedades associadas ao fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="47fca-103">The <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> class represents a data stream and information about the data stream's associated properties.</span></span> <span data-ttu-id="47fca-104">A propriedade **Data** da classe <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> é usada para representar um relatório renderizado ou relatar um recurso como um objeto **Stream**.</span><span class="sxs-lookup"><span data-stu-id="47fca-104">The **Data** property of the <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> class is used to represent a rendered report or report resource as a **Stream** object.</span></span>  
  
 <span data-ttu-id="47fca-105">O método <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> do objeto **Report** retorna uma matriz de um ou mais objetos <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> que juntos constituem um único relatório renderizado.</span><span class="sxs-lookup"><span data-stu-id="47fca-105">The <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> method of the **Report** object returns an array of one or more <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> objects that together constitute a single rendered report.</span></span> <span data-ttu-id="47fca-106">O primeiro objeto de <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> é o relatório renderizado.</span><span class="sxs-lookup"><span data-stu-id="47fca-106">The first <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object is the rendered report.</span></span> <span data-ttu-id="47fca-107">Qualquer outro objeto de <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> será o recurso a ser entregue junto com os dados de relatório (por exemplo, um arquivo HTML e as imagens associadas).</span><span class="sxs-lookup"><span data-stu-id="47fca-107">Any other <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> objects are resources that must be delivered along with the report data (for example, an HTML file and associated images).</span></span> <span data-ttu-id="47fca-108">A renderização de extensões que são extensões de renderização de fluxo único (IMAGE, PDF, MHTML e EXCEL) retornará só um objeto de <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> na matriz.</span><span class="sxs-lookup"><span data-stu-id="47fca-108">Rendering extensions that are single-stream rendering extensions (IMAGE, PDF, MHTML, and EXCEL) return only one <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object in the array.</span></span>  
  
 <span data-ttu-id="47fca-109">Para obter um exemplo de como usar a classe <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile>, consulte [Amostras de produto do SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="47fca-109">For an example of how to use the <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> class, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47fca-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="47fca-110">See Also</span></span>  
 <span data-ttu-id="47fca-111">[Implementando uma extensão de entrega](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="47fca-111">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="47fca-112">Biblioteca de extensões do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="47fca-112">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
