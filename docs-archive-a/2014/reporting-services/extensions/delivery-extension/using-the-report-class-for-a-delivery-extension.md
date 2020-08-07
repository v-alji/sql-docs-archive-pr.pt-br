---
title: Usando a classe Report para uma extensão de entrega | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery extensions [Reporting Services], report information
- Report class
ms.assetid: 1145ac63-eafd-452a-82af-16f85b1676dd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a3f750c2383253636db255cbe9f1ce0ee676a9d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584018"
---
# <a name="using-the-report-class-for-a-delivery-extension"></a><span data-ttu-id="5b416-102">Usando a classe Report para uma extensão de entrega</span><span class="sxs-lookup"><span data-stu-id="5b416-102">Using the Report Class for a Delivery Extension</span></span>
  <span data-ttu-id="5b416-103">A classe de <xref:Microsoft.ReportingServices.Interfaces.Report> representa um relatório no banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="5b416-103">The <xref:Microsoft.ReportingServices.Interfaces.Report> class represents a report in the report server database.</span></span> <span data-ttu-id="5b416-104">Qualquer assinatura é associada a um relatório específico.</span><span class="sxs-lookup"><span data-stu-id="5b416-104">Any subscription is associated with a specific report.</span></span> <span data-ttu-id="5b416-105">O relatório está contido na notificação.</span><span class="sxs-lookup"><span data-stu-id="5b416-105">The report is contained in the notification.</span></span> <span data-ttu-id="5b416-106">A sua extensão de entrega pode usar o objeto de <xref:Microsoft.ReportingServices.Interfaces.Report> que faz parte da notificação para renderizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="5b416-106">Your delivery extension can use the <xref:Microsoft.ReportingServices.Interfaces.Report> object that is part of the notification to render the report.</span></span> <span data-ttu-id="5b416-107">O objeto de <xref:Microsoft.ReportingServices.Interfaces.Report> também contém propriedades específicas do relatório, como a URL para o relatório no servidor de relatório e o nome do relatório.</span><span class="sxs-lookup"><span data-stu-id="5b416-107">The <xref:Microsoft.ReportingServices.Interfaces.Report> object also contains report-specific properties, such as the URL to the report on the report server and the name of the report.</span></span> <span data-ttu-id="5b416-108">Todas essas propriedades podem ser usadas como parte de seu provedor de entrega.</span><span class="sxs-lookup"><span data-stu-id="5b416-108">These properties can all be used as part of your delivery provider.</span></span>  
  
 <span data-ttu-id="5b416-109">O método de <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> da classe de <xref:Microsoft.ReportingServices.Interfaces.Report> pode ser usado para renderizar um relatório.</span><span class="sxs-lookup"><span data-stu-id="5b416-109">The <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> method of the <xref:Microsoft.ReportingServices.Interfaces.Report> class can be used to render a report.</span></span> <span data-ttu-id="5b416-110">O método <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> retorna uma matriz de um ou mais objetos de <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> que, juntos, formam um único relatório renderizado.</span><span class="sxs-lookup"><span data-stu-id="5b416-110">The <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> method returns an array of one or more <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> objects that together comprise a single rendered report.</span></span> <span data-ttu-id="5b416-111">O primeiro objeto de <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> é o relatório renderizado.</span><span class="sxs-lookup"><span data-stu-id="5b416-111">The first <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object is the rendered report.</span></span> <span data-ttu-id="5b416-112">Qualquer outro objeto de <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> será o recurso a ser entregue junto com os dados de relatório (por exemplo, um arquivo HTML e as imagens associadas).</span><span class="sxs-lookup"><span data-stu-id="5b416-112">Any other <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> objects are resources that must be delivered along with the report data (for example, an HTML file and associated images).</span></span> <span data-ttu-id="5b416-113">A renderização de extensões que são extensões de renderização de fluxo único (IMAGE, PDF, MHTML e Excel) retornará só um objeto de <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> na matriz.</span><span class="sxs-lookup"><span data-stu-id="5b416-113">Rendering extensions that are single-stream rendering extensions (IMAGE, PDF, MHTML, and Excel) return only one <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object in the array.</span></span>  
  
 <span data-ttu-id="5b416-114">O objeto de <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> que contém o fluxo de relatório pode ser incluído como parte de uma entrega.</span><span class="sxs-lookup"><span data-stu-id="5b416-114">The <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object, which contains the report stream, can be included as part of a delivery.</span></span>  
  
 <span data-ttu-id="5b416-115">Para obter um exemplo de como usar a classe <xref:Microsoft.ReportingServices.Interfaces.Report>, consulte [Amostras de produto do SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889)</span><span class="sxs-lookup"><span data-stu-id="5b416-115">For an example of how to use the <xref:Microsoft.ReportingServices.Interfaces.Report> class, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b416-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5b416-116">See Also</span></span>  
 <span data-ttu-id="5b416-117">[Implementando uma extensão de entrega](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="5b416-117">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 <span data-ttu-id="5b416-118">[Biblioteca de extensões do Reporting Services](../reporting-services-extension-library.md) </span><span class="sxs-lookup"><span data-stu-id="5b416-118">[Reporting Services Extension Library](../reporting-services-extension-library.md) </span></span>  
 [<span data-ttu-id="5b416-119">Usar a classe RenderedOutputFile para uma extensão de entrega</span><span class="sxs-lookup"><span data-stu-id="5b416-119">Using the RenderedOutputFile Class for a Delivery Extension</span></span>](using-the-renderedoutputfile-class-for-a-delivery-extension.md)  
  
  
