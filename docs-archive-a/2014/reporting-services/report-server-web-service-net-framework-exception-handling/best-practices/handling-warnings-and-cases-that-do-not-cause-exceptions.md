---
title: Manipulando avisos e casos que não causam exceções | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- exceptions [Reporting Services], warnings that don't cause
- warnings [Reporting Services]
ms.assetid: 475c0713-6265-44e7-9ebc-ebdd1b89e0af
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 88d3daf63cf5f04975a2941d0634f357ce81456c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681397"
---
# <a name="handling-warnings-and-cases-that-do-not-cause-exceptions"></a><span data-ttu-id="d2b1c-102">Manipulando avisos e casos que não causam exceções</span><span class="sxs-lookup"><span data-stu-id="d2b1c-102">Handling Warnings and Cases That Do Not Cause Exceptions</span></span>
  <span data-ttu-id="d2b1c-103">O [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] não lança exceções para avisos e para certos erros.</span><span class="sxs-lookup"><span data-stu-id="d2b1c-103">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] does not throw exceptions for warnings and certain errors.</span></span> <span data-ttu-id="d2b1c-104">Por exemplo, quando você usa o método <xref:ReportService2010.ReportingService2010.CreateCatalogItem%2A> para publicar um novo relatório em um servidor de relatório, qualquer aviso que ocorrer será retornado como uma matriz de objetos de <xref:ReportService2010.Warning>.</span><span class="sxs-lookup"><span data-stu-id="d2b1c-104">For example, when you use the <xref:ReportService2010.ReportingService2010.CreateCatalogItem%2A> method to publish a new report to a report server, any warnings that occur are returned as an array of <xref:ReportService2010.Warning> objects.</span></span> <span data-ttu-id="d2b1c-105">Esses avisos devem ser manipulados e exibidos para que a ação apropriada seja tomada.</span><span class="sxs-lookup"><span data-stu-id="d2b1c-105">These warnings should be handled and displayed so that appropriate action can be taken.</span></span>  
  
```vb  
Try  
   rs.CreateCatalogItem(name, parentFolder, False, definition, Nothing, warnings)  
  
   If Not (warnings.Length = 0) Then  
      Dim warning As Warning  
      For Each warning In warnings  
         Console.WriteLine(warning.Message)  
      Next warning  
   Else  
      Console.WriteLine("Report {0} created successfully with no warnings", name)  
   End If  
  
Catch ex As SoapException  
   Console.WriteLine(ex.Detail("Message").InnerXml)  
End Try  
```  
  
```csharp  
try  
{  
   rs.CreateCatalogItem("Report", name, parentFolder, false, definition, null, out warnings);  
  
   if (warnings.Length != 0)  
   {  
      foreach (Warning warning in warnings)  
      {  
         Console.WriteLine(warning.Message);  
      }  
   }  
   else  
      Console.WriteLine("Report {0} created successfully with no warnings", name);  
}  
  
catch (SoapException ex)  
{  
   Console.WriteLine(ex.Detail["Message"].InnerXml);  
}  
```  
  
 <span data-ttu-id="d2b1c-106">Outro modo de manipular erros é avaliando os valores retornados de certos métodos.</span><span class="sxs-lookup"><span data-stu-id="d2b1c-106">Another way to handle errors is to evaluate the return values of certain methods.</span></span> <span data-ttu-id="d2b1c-107">Por exemplo, o método de <xref:ReportService2010.ReportingService2010.FindItems%2A> pode ser usado para procurar itens específicos no banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="d2b1c-107">For example, the <xref:ReportService2010.ReportingService2010.FindItems%2A> method can be used to search for specific items in the report server database.</span></span> <span data-ttu-id="d2b1c-108">Se não for localizado nenhum item que corresponda aos critérios de pesquisa, será retornada uma matriz nula de objetos de <xref:ReportService2010.CatalogItem>.</span><span class="sxs-lookup"><span data-stu-id="d2b1c-108">If no items are found that match the search criteria, a null array of <xref:ReportService2010.CatalogItem> objects is returned.</span></span> <span data-ttu-id="d2b1c-109">Avalie a matriz, verifique a existência de `null` e avise o usuário caso nenhum item tenha sido encontrado.</span><span class="sxs-lookup"><span data-stu-id="d2b1c-109">You should evaluate the array, check for `null`, and let the user know if no items were found.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2b1c-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d2b1c-110">See Also</span></span>  
 <xref:ReportService2010.CatalogItem>   
 <span data-ttu-id="d2b1c-111">[Introdução à manipulação de exceção no Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="d2b1c-111">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="d2b1c-112">Classe SoapException do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d2b1c-112">Reporting Services SoapException Class</span></span>](../soapexception-class/reporting-services-soapexception-class.md)  
  
  
