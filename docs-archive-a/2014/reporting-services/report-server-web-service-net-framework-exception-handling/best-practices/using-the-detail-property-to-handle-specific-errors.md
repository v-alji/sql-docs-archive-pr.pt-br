---
title: Usando a propriedade Detail para tratar erros específicos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- exceptions [Reporting Services], Detail property
- Detail property
- InnerText property
ms.assetid: 4392633d-b46b-41e6-bc12-efb64e166704
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4f8ac62dc381d8f665a44fc0897ba1f4215aa8e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682116"
---
# <a name="using-the-detail-property-to-handle-specific-errors"></a><span data-ttu-id="7f3f6-102">Usando a propriedade Detail para manipular erros específicos</span><span class="sxs-lookup"><span data-stu-id="7f3f6-102">Using the Detail Property to Handle Specific Errors</span></span>
  <span data-ttu-id="7f3f6-103">Para classificar ainda mais as exceções, o [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] retorna informações de erro adicionais na propriedade **InnerText** dos elementos filho da propriedade **Detail** da exceção SOAP.</span><span class="sxs-lookup"><span data-stu-id="7f3f6-103">To further classify exceptions, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] returns additional error information in the **InnerText** property of the child elements in the SOAP exception's **Detail** property.</span></span> <span data-ttu-id="7f3f6-104">Como a propriedade **Detail** é um objeto **XmlNode**, você pode acessar o texto interno do elemento filho **Message** usando o código a seguir.</span><span class="sxs-lookup"><span data-stu-id="7f3f6-104">Because the **Detail** property is an **XmlNode** object, you can access the inner text of the **Message** child element using the following code.</span></span>  
  
 <span data-ttu-id="7f3f6-105">Para obter uma lista de todos os elementos filho disponíveis contidos na propriedade **Detail**, consulte [Propriedade Detail](../soapexception-class/detail-property.md).</span><span class="sxs-lookup"><span data-stu-id="7f3f6-105">For a list of all of the available child elements contained in the **Detail** property, see [Detail Property](../soapexception-class/detail-property.md).</span></span> <span data-ttu-id="7f3f6-106">Para obter mais informações, consulte "propriedade Detail" na [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] documentação do SDK.</span><span class="sxs-lookup"><span data-stu-id="7f3f6-106">For more information, see "Detail Property" in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
```vb  
Try  
' Code for accessing the report server  
Catch ex As SoapException  
   ' The exception is a SOAP exception, so use  
   ' the Detail property's Message element.  
   Console.WriteLine(ex.Detail("Message").InnerXml)  
End Try  
```  
  
```csharp  
try  
{  
   // Code for accessing the report server  
}  
catch (SoapException ex)  
{  
   // The exception is a SOAP exception, so use  
   // the Detail property's Message element.  
   Console.WriteLine(ex.Detail["Message"].InnerXml);  
}  
```  
  
```vb  
Try  
' Code for accessing the report server  
Catch ex As SoapException  
   If ex.Detail("ErrorCode").InnerXml = "rsInvalidItemName" Then  
   End If ' Perform an action based on the specific error code  
End Try  
```  
  
```csharp  
try  
{  
   // Code for accessing the report server  
}  
catch (SoapException ex)  
{  
   if (ex.Detail["ErrorCode"].InnerXml == "rsInvalidItemName")  
   {  
      // Perform an action based on the specific error code  
   }  
}  
```  
  
 <span data-ttu-id="7f3f6-107">A linha de código a seguir grava o código de erro específico retornado na Exceção SOAP para o console.</span><span class="sxs-lookup"><span data-stu-id="7f3f6-107">The following line of code writes the specific error code being returned in the SOAP Exception to the console.</span></span> <span data-ttu-id="7f3f6-108">Você também pode avaliar o código de erro e executar ações específicas.</span><span class="sxs-lookup"><span data-stu-id="7f3f6-108">You could also evaluate the error code and perform specific actions.</span></span>  
  
```vb  
Console.WriteLine(ex.Detail("ErrorCode").InnerXml)  
```  
  
```csharp  
Console.WriteLine(ex.Detail["ErrorCode"].InnerXml);  
```  
  
## <a name="see-also"></a><span data-ttu-id="7f3f6-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7f3f6-109">See Also</span></span>  
 <span data-ttu-id="7f3f6-110">[Introdução à manipulação de exceção no Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="7f3f6-110">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 <span data-ttu-id="7f3f6-111">[Classe SoapException Reporting Services](../soapexception-class/reporting-services-soapexception-class.md) </span><span class="sxs-lookup"><span data-stu-id="7f3f6-111">[Reporting Services SoapException Class](../soapexception-class/reporting-services-soapexception-class.md) </span></span>  
 [<span data-ttu-id="7f3f6-112">Tabela de erros SoapException</span><span class="sxs-lookup"><span data-stu-id="7f3f6-112">SoapException Errors Table</span></span>](../soapexception-class/soapexception-errors-table.md)  
  
  
