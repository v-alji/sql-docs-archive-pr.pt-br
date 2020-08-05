---
title: 'Lição 4: atualizar a definição de relatório programaticamente | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 1f0a1d46-6d6d-4f67-b51e-06dbbbffacf9
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: c090fc023e3ac47927b99ab61a45fd8ca2c79321
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572871"
---
# <a name="lesson-4-update-the-report-definition-programmatically"></a><span data-ttu-id="af642-102">Lição 4: Atualizar a definição do relatório programaticamente</span><span class="sxs-lookup"><span data-stu-id="af642-102">Lesson 4: Update the Report Definition Programmatically</span></span>
  <span data-ttu-id="af642-103">Agora que a definição do relatório foi carregada do servidor de relatório e você tem uma referência a ela que usa o campo de relatório, será necessário atualizar essa definição.</span><span class="sxs-lookup"><span data-stu-id="af642-103">Now that the report definition has been loaded from the report server and you have a reference to it using the report field, you need to update the report definition.</span></span> <span data-ttu-id="af642-104">Para este exemplo, você atualizará a propriedade `Description` do relatório.</span><span class="sxs-lookup"><span data-stu-id="af642-104">For this example, you will update the `Description` property for the report.</span></span>  
  
### <a name="to-update-the-report-definition"></a><span data-ttu-id="af642-105">Para atualizar a definição do relatório</span><span class="sxs-lookup"><span data-stu-id="af642-105">To update the report definition</span></span>  
  
1.  <span data-ttu-id="af642-106">Substitua o código do método UpdateReportDefinition () no arquivo Program.cs (Module1. vb para [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] ) pelo seguinte código:</span><span class="sxs-lookup"><span data-stu-id="af642-106">Replace the code for the UpdateReportDefinition() method in the Program.cs file (Module1.vb for [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) with the following code:</span></span>  
  
    ```csharp  
    private void UpdateReportDefinition()  
    {  
        System.Console.WriteLine("Updating Report Definition");  
  
        // Create a list of the Items Choices for the Report. The   
        // ItemsChoiceType118 enum represents all the properties  
        // available in the report and the ItemsElementName   
        // represents the properties that exist in the current   
        // instance of the report.  
        List<ItemsChoiceType118> _reportItems =   
            new List<ItemsChoiceType118>(_report.ItemsElementName);  
  
        // Locate the index for the Description property  
        int index = _reportItems.IndexOf(  
            ItemsChoiceType118.Description);  
  
        // The Description item is of type StringLocIDType, so   
        // cast the item type first and then assign new value.  
        System.Console.WriteLine("- Old Description: " +   
            ((StringLocIDType)_report.Items[index]).Value );  
  
        // Update the Description for the Report  
        ((StringLocIDType)_report.Items[index]).Value =   
            "New Report Description";  
  
        System.Console.WriteLine("- New Description: " +   
            ((StringLocIDType)_report.Items[index]).Value );  
    }  
    ```  
  
    ```vb  
    Private Sub UpdateReportDefinition()  
  
        System.Console.WriteLine("Updating Report Definition")  
  
        'Create a list of the Items Choices for the Report. The   
        'ItemsChoiceType118 enum represents all the properties  
        'available in the report and the ItemsElementName   
        'represents the properties that exist in the current   
        'instance of the report.  
        Dim reportItems As List(Of ItemsChoiceType118) = _  
            New List(Of ItemsChoiceType118)(m_report.ItemsElementName)  
  
        'Locate the index for the Description property  
        Dim index As Integer = _  
            reportItems.IndexOf(ItemsChoiceType118.Description)  
  
        'The Description item is of type StringLocIDType, so   
        'cast the item type first and then assign new value.  
        System.Console.WriteLine("- Old Description: " & _  
            DirectCast(m_report.Items(index), StringLocIDType).Value)  
  
        'Update the Description for the Report  
        DirectCast(m_report.Items(index), StringLocIDType).Value = _  
            "New Report Description"  
  
        System.Console.WriteLine("- New Description: " & _  
            DirectCast(m_report.Items(index), StringLocIDType).Value)  
  
    End Sub  
    ```  
  
## <a name="next-lesson"></a><span data-ttu-id="af642-107">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="af642-107">Next Lesson</span></span>  
 <span data-ttu-id="af642-108">Na próxima lição, você salvará a definição do relatório atualizada no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="af642-108">In the next lesson, you will save the updated report definition back to the report server.</span></span> <span data-ttu-id="af642-109">Consulte [lição 5: publicar a definição de relatório no servidor de relatório](../../2014/tutorials/lesson-5-publish-the-report-definition-to-the-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="af642-109">See [Lesson 5: Publish the Report Definition to the Report Server](../../2014/tutorials/lesson-5-publish-the-report-definition-to-the-report-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af642-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="af642-110">See Also</span></span>  
 [<span data-ttu-id="af642-111">Atualizando relatórios usando classes geradas do esquema RDL &#40;tutorial do SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="af642-111">Updating Reports Using Classes Generated from the RDL Schema &#40;SSRS Tutorial&#41;</span></span>](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md)  
  
  
