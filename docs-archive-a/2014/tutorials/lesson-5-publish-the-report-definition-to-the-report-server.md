---
title: 'Lição 5: publicar a definição de relatório no servidor de relatório | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 57fab70f-4a72-4413-a0ad-d0525caca3f7
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 54c2bad9f5b11e5ea72036fed9f60371ba9c593c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571716"
---
# <a name="lesson-5-publish-the-report-definition-to-the-report-server"></a><span data-ttu-id="7364b-102">Lição 5: Publicar a definição de relatório no servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="7364b-102">Lesson 5: Publish the Report Definition to the Report Server</span></span>
  <span data-ttu-id="7364b-103">A última etapa para atualizar a definição de relatório é publicá-la novamente no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="7364b-103">The last step for updating the report definition is to publish it back to the report server.</span></span>  
  
### <a name="to-publish-the-report-to-the-report-catalog"></a><span data-ttu-id="7364b-104">Para publicar o relatório no catálogo de relatório</span><span class="sxs-lookup"><span data-stu-id="7364b-104">To publish the report to the report catalog</span></span>  
  
1.  <span data-ttu-id="7364b-105">Substitua o código do `PublishReportDefinition()` método no arquivo Program.cs (Module1. vb para [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] ) pelo seguinte código:</span><span class="sxs-lookup"><span data-stu-id="7364b-105">Replace the code for the `PublishReportDefinition()` method in your Program.cs file (Module1.vb for [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) with the following code:</span></span>  
  
    ```csharp  
    private void PublishReportDefinition()  
    {  
        System.Console.WriteLine("Publishing Report Definition");  
  
        string reportPath =  
            "/AdventureWorks 2012 Sample Reports/Company Sales 2012";  
  
        XmlSerializer serializer =  
            new XmlSerializer(typeof(Report));  
  
        using (MemoryStream stream = new MemoryStream())  
        {  
            // Serialize the report into the MemoryStream  
            serializer.Serialize(stream, _report);  
            stream.Position = 0;  
  
            byte[] bytes = stream.ToArray();  
  
            // Update the report on the report server  
            Warning[] warnings =   
                _reportService.SetItemDefinition(reportPath, bytes, null);  
        }  
    }  
    ```  
  
    ```vb  
    Private Sub PublishReportDefinition()  
  
        System.Console.WriteLine("Publishing Report Definition")  
  
        Dim reportPath As String = _  
            "/AdventureWorks 2012 Sample Reports/Company Sales 2012"  
        Dim serializer As XmlSerializer = _  
            New XmlSerializer(GetType(Report))  
  
        Using stream As MemoryStream = New MemoryStream  
  
            'Serialize the report into the MemoryStream  
            serializer.Serialize(stream, m_report)  
            stream.Position = 0  
  
            'Update the report on the report server  
            Dim bytes As Byte() = stream.ToArray  
            Dim warnings As Warning() = _  
                m_reportService.SetItemDefinition(reportPath, bytes, Nothing)  
  
        End Using  
  
    End Sub  
    ```  
  
## <a name="next-lesson"></a><span data-ttu-id="7364b-106">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="7364b-106">Next Lesson</span></span>  
 <span data-ttu-id="7364b-107">Na próxima lição, você compilará e executará o `SampleRDLSchema` aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7364b-107">In the next lesson, you will compile and run the `SampleRDLSchema` application.</span></span> <span data-ttu-id="7364b-108">Consulte [lição 6: executar o aplicativo de esquema RDL &#40;VB-C&#35;&#41;](../../2014/tutorials/lesson-6-run-the-rdl-schema-application-vb-csharp.md).</span><span class="sxs-lookup"><span data-stu-id="7364b-108">See [Lesson 6: Run the RDL Schema Application &#40;VB-C&#35;&#41;](../../2014/tutorials/lesson-6-run-the-rdl-schema-application-vb-csharp.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7364b-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7364b-109">See Also</span></span>  
 <span data-ttu-id="7364b-110">[Atualizando relatórios usando classes geradas do esquema RDL &#40;tutorial do SSRS&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="7364b-110">[Updating Reports Using Classes Generated from the RDL Schema &#40;SSRS Tutorial&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span></span>  
 [<span data-ttu-id="7364b-111">Linguagem RDL &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7364b-111">Report Definition Language &#40;SSRS&#41;</span></span>](../reporting-services/reports/report-definition-language-ssrs.md)  
  
  
