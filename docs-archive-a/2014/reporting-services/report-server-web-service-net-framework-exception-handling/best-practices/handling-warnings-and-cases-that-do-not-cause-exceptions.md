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
# <a name="handling-warnings-and-cases-that-do-not-cause-exceptions"></a>Manipulando avisos e casos que não causam exceções
  O [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] não lança exceções para avisos e para certos erros. Por exemplo, quando você usa o método <xref:ReportService2010.ReportingService2010.CreateCatalogItem%2A> para publicar um novo relatório em um servidor de relatório, qualquer aviso que ocorrer será retornado como uma matriz de objetos de <xref:ReportService2010.Warning>. Esses avisos devem ser manipulados e exibidos para que a ação apropriada seja tomada.  
  
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
  
 Outro modo de manipular erros é avaliando os valores retornados de certos métodos. Por exemplo, o método de <xref:ReportService2010.ReportingService2010.FindItems%2A> pode ser usado para procurar itens específicos no banco de dados do servidor de relatório. Se não for localizado nenhum item que corresponda aos critérios de pesquisa, será retornada uma matriz nula de objetos de <xref:ReportService2010.CatalogItem>. Avalie a matriz, verifique a existência de `null` e avise o usuário caso nenhum item tenha sido encontrado.  
  
## <a name="see-also"></a>Consulte Também  
 <xref:ReportService2010.CatalogItem>   
 [Introdução à manipulação de exceção no Reporting Services](../introducing-exception-handling-in-reporting-services.md)   
 [Classe SoapException do Reporting Services](../soapexception-class/reporting-services-soapexception-class.md)  
  
  
