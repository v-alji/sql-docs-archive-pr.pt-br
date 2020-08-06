---
title: Criando um componente de item de relatório personalizado em tempo de execução | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom report items, creating
ms.assetid: b3e15a4a-98f8-4dbb-b847-bbcb20327051
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 50c5c0211bc5cd1359af9d1493782bd9d96c2b3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569215"
---
# <a name="creating-a-custom-report-item-run-time-component"></a><span data-ttu-id="9251e-102">Criando um componente de item de relatório personalizado em tempo de execução</span><span class="sxs-lookup"><span data-stu-id="9251e-102">Creating a Custom Report Item Run-Time Component</span></span>
  <span data-ttu-id="9251e-103">O componente de tempo de execução do item de relatório personalizado é implementado como um [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] componente usando qualquer linguagem compatível com CLS e é chamado pelo processador de relatório em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="9251e-103">The custom report item run-time component is implemented as a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] component using any CLS-compliant language, and is called by the report processor at run time.</span></span> <span data-ttu-id="9251e-104">Para definir as propriedades do componente em tempo de execução no ambiente de design, modifique o componente em tempo de design correspondente do item de relatório personalizado.</span><span class="sxs-lookup"><span data-stu-id="9251e-104">You define the properties for the run-time component in the design environment by modifying the custom report item's corresponding design-time component.</span></span>  

<!--
Replacing the following multiValue.....

ms.technology: 
  - "docset-sql-devref"
  - "reporting-services-native"

.....with the following single value.....

ms.technology: reporting-services
.

(GeneMi = MightyPen  ,  2019-04-20  ,  DevO= 1515083)
-->

 <span data-ttu-id="9251e-105">Para obter uma amostra de um item de relatório personalizado totalmente implementado, consulte [Amostras de produto do SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="9251e-105">For a sample of a fully implemented custom report item, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="definition-and-instance-objects"></a><span data-ttu-id="9251e-106">Objetos de definição e objetos de instância</span><span class="sxs-lookup"><span data-stu-id="9251e-106">Definition and Instance Objects</span></span>  
 <span data-ttu-id="9251e-107">Antes de implementar um item de relatório personalizado, é importante compreender a diferença entre *objetos de definição* e *objetos de instância*.</span><span class="sxs-lookup"><span data-stu-id="9251e-107">Before implementing a custom report item it is important to understand the difference between *definition objects* and *instance objects*.</span></span> <span data-ttu-id="9251e-108">Objetos de definição fornecem a representação de RDL do item de relatório personalizado, enquanto objetos de instância são as versões avaliadas dos objetos de definição.</span><span class="sxs-lookup"><span data-stu-id="9251e-108">Definition objects provide the RDL representation of the custom report item whereas instance objects are the evaluated versions of the definition objects.</span></span> <span data-ttu-id="9251e-109">Há apenas um objeto de definição para cada item do relatório.</span><span class="sxs-lookup"><span data-stu-id="9251e-109">There is only one definition object for each item on the report.</span></span> <span data-ttu-id="9251e-110">Ao acessar propriedades em um objeto de definição contendo expressões, você obterá a cadeia de caracteres de expressão não avaliada.</span><span class="sxs-lookup"><span data-stu-id="9251e-110">When accessing properties on a definition object that contain expressions, you will get the unevaluated expression string.</span></span> <span data-ttu-id="9251e-111">Os objetos de instância contêm as versões avaliadas dos objetos de definição e têm uma relação um-para-muitos com o objeto de definição de um item.</span><span class="sxs-lookup"><span data-stu-id="9251e-111">Instance objects contain the evaluated versions of the definition objects and can have a one-to-many relationship with an item's definition object.</span></span> <span data-ttu-id="9251e-112">Por exemplo, se um relatório tiver uma região de dados <xref:Microsoft.ReportingServices.OnDemandReportRendering.Tablix> que contém um <xref:Microsoft.ReportingServices.OnDemandReportRendering.CustomReportItem> na linha de detalhes, haverá apenas um objeto de definição, mas haverá um objeto de instância para cada linha da região de dados.</span><span class="sxs-lookup"><span data-stu-id="9251e-112">For example, if a report has a <xref:Microsoft.ReportingServices.OnDemandReportRendering.Tablix> data region that contains a <xref:Microsoft.ReportingServices.OnDemandReportRendering.CustomReportItem> in a detail row, there will be only one definition object but there will be an instance object for each row in the data region.</span></span>  
  
## <a name="implementing-the-icustomreportitem-interface"></a><span data-ttu-id="9251e-113">Implementando a interface ICustomReportItem</span><span class="sxs-lookup"><span data-stu-id="9251e-113">Implementing the ICustomReportItem Interface</span></span>  
 <span data-ttu-id="9251e-114">Para criar um componente em tempo de execução `CustomReportItem`, implemente a interface <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem> que é definida no Microsoft.ReportingServices.ProcessingCore.dll:</span><span class="sxs-lookup"><span data-stu-id="9251e-114">To create a `CustomReportItem` run-time component you will need to implement the <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem> interface that is defined in the Microsoft.ReportingServices.ProcessingCore.dll:</span></span>  
  
```csharp  
namespace Microsoft.ReportingServices.OnDemandReportRendering  
{  
    public interface ICustomReportItem  
    {  
        void GenerateReportItemDefinition(CustomReportItem customReportItem);  
void EvaluateReportItemInstance(CustomReportItem customReportItem);  
    }  
}  
```  
  
 <span data-ttu-id="9251e-115">Depois que você implementar a interface <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem>, dois stubs de método serão gerados: <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.GenerateReportItemDefinition%2A> e <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.EvaluateReportItemInstance%2A>.</span><span class="sxs-lookup"><span data-stu-id="9251e-115">After you have implemented the <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem> interface, two method stubs will be generated for you: <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.GenerateReportItemDefinition%2A> and <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.EvaluateReportItemInstance%2A>.</span></span> <span data-ttu-id="9251e-116">O método <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.GenerateReportItemDefinition%2A> é chamado primeiro e é usado para configurar propriedades de definição e criar o objeto <xref:Microsoft.ReportingServices.OnDemandReportRendering.Image> que conterá as propriedades de definição e de instância que são usadas para renderizar o item.</span><span class="sxs-lookup"><span data-stu-id="9251e-116">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.GenerateReportItemDefinition%2A> method is called first and is used for setting definition properties and creating the <xref:Microsoft.ReportingServices.OnDemandReportRendering.Image> object that will contain both the definition and instance properties that are used for rendering the item.</span></span> <span data-ttu-id="9251e-117">O método <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.EvaluateReportItemInstance%2A> é chamado depois da avaliação dos objetos de definição, e ele fornece os objetos de instância que serão usados para renderizar o item.</span><span class="sxs-lookup"><span data-stu-id="9251e-117">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.EvaluateReportItemInstance%2A> method is called after the definition objects have been evaluated, and it provides the instance objects that will be used for rendering the item.</span></span>  
  
 <span data-ttu-id="9251e-118">Veja a seguir uma implementação de exemplo de um item de relatório personalizado que renderiza o nome do controle como uma imagem.</span><span class="sxs-lookup"><span data-stu-id="9251e-118">The following is an example implementation of a custom report item that renders the name of the control as an image.</span></span>  
  
```csharp  
namespace Microsoft.Samples.ReportingServices  
{  
    using System;  
    using System.Collections.Generic;  
    using System.Collections.Specialized;  
    using System.Drawing.Imaging;  
    using System.IO;  
    using System.Text;  
    using Microsoft.ReportingServices.OnDemandReportRendering;  
  
    public class PolygonsCustomReportItem : ICustomReportItem  
    {  
        #region ICustomReportItem Members  
  
        public void GenerateReportItemDefinition(CustomReportItem cri)  
        {  
            // Create the Image object that will be   
            // used to render the custom report item  
            cri.CreateCriImageDefinition();  
            Image polygonImage = (Image)cri.GeneratedReportItem;  
        }  
  
        public void EvaluateReportItemInstance(CustomReportItem cri)  
        {  
            // Get the Image definition  
            Image polygonImage = (Image)cri.GeneratedReportItem;  
  
            // Create the image for the custom report item  
            polygonImage.ImageInstance.ImageData = DrawImage(cri);  
        }  
  
        #endregion  
  
        /// <summary>  
        /// Creates an image of the CustomReportItem's name  
        /// </summary>  
        private byte[] DrawImage(CustomReportItem customReportItem)  
        {  
            int width = 1;          // pixels  
            int height = 1;         // pixels  
            int resolution = 75;    // dpi  
  
            System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap(width, height);  
            bitmap.SetResolution(resolution, resolution);  
  
            System.Drawing.Graphics graphics = System.Drawing.Graphics.FromImage(bitmap);  
            graphics.PageUnit = System.Drawing.GraphicsUnit.Pixel;  
  
            // Get the Font for the Text  
            System.Drawing.Font font = new System.Drawing.Font(System.Drawing.FontFamily.GenericMonospace,  
                12, System.Drawing.FontStyle.Regular);  
  
            // Get the Brush for drawing the Text  
            System.Drawing.Brush brush = new System.Drawing.SolidBrush(System.Drawing.Color.LightGreen);  
  
            // Get the measurements for the image  
            System.Drawing.SizeF maxStringSize = graphics.MeasureString(customReportItem.Name, font);  
            width = (int)(maxStringSize.Width + 2 * font.GetHeight(resolution));  
            height = (int)(maxStringSize.Height + 2 * font.GetHeight(resolution));  
  
            bitmap.Dispose();  
            bitmap = new System.Drawing.Bitmap(width, height);  
            bitmap.SetResolution(resolution, resolution);  
  
            graphics.Dispose();  
            graphics = System.Drawing.Graphics.FromImage(bitmap);  
            graphics.PageUnit = System.Drawing.GraphicsUnit.Pixel;  
  
            // Draw the text  
            graphics.DrawString(customReportItem.Name, font, brush, font.GetHeight(resolution),   
                font.GetHeight(resolution));  
  
            // Create the byte array of the image data  
            MemoryStream memoryStream = new MemoryStream();  
            bitmap.Save(memoryStream, ImageFormat.Bmp);  
            memoryStream.Position = 0;  
            byte[] imageData = new byte[memoryStream.Length];  
            memoryStream.Read(imageData, 0, imageData.Length);  
  
            return imageData;  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="9251e-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9251e-119">See Also</span></span>  
 <span data-ttu-id="9251e-120">[Arquitetura de item de relatório personalizado](custom-report-item-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="9251e-120">[Custom Report Item Architecture](custom-report-item-architecture.md) </span></span>  
 <span data-ttu-id="9251e-121">[Criando um componente de item de relatório personalizado em tempo de design](creating-a-custom-report-item-design-time-component.md) </span><span class="sxs-lookup"><span data-stu-id="9251e-121">[Creating a Custom Report Item Design-Time Component](creating-a-custom-report-item-design-time-component.md) </span></span>  
 <span data-ttu-id="9251e-122">[Bibliotecas de classe de item de relatório personalizado](custom-report-item-class-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="9251e-122">[Custom Report Item Class Libraries](custom-report-item-class-libraries.md) </span></span>  
 [<span data-ttu-id="9251e-123">Como: implantar um Item de relatório personalizado</span><span class="sxs-lookup"><span data-stu-id="9251e-123">How to: Deploy a Custom Report Item</span></span>](how-to-deploy-a-custom-report-item.md)  
  
  
