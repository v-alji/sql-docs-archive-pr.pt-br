---
title: Usando blocos Try e Catch | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- exceptions [Reporting Services], try/catch blocks
- try/catch blocks [Reporting Services]
ms.assetid: a7a9ef53-e3b6-4bf7-81f3-d85615954e6f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a6aadb392fa4117484f3373ae232c3ed9c4b1d63
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684492"
---
# <a name="using-try-and-catch-blocks"></a><span data-ttu-id="7e032-102">Usando blocos Try e Catch</span><span class="sxs-lookup"><span data-stu-id="7e032-102">Using Try and Catch Blocks</span></span>
  <span data-ttu-id="7e032-103">Depois de limitar solicitações inválidas feitas ao servidor de relatório ao adicionar instruções condicionais ao seu código, forneça a manipulação de exceções adequada usando blocos try/catch.</span><span class="sxs-lookup"><span data-stu-id="7e032-103">After you limit invalid requests to the report server by adding conditional statements to your code, you should supply adequate exception handling through the use of try/catch blocks.</span></span> <span data-ttu-id="7e032-104">Essa técnica oferece outra camada de proteção contra solicitações que não são válidas.</span><span class="sxs-lookup"><span data-stu-id="7e032-104">This technique provides another layer of protection against requests that are not valid.</span></span> <span data-ttu-id="7e032-105">Se uma solicitação feita ao servidor de relatório for encapsulada em um bloco try e se essa solicitação fizer com que o servidor de relatório lance uma exceção, a exceção será capturada em um bloco catch, impedindo que o seu aplicativo seja interrompido inesperadamente.</span><span class="sxs-lookup"><span data-stu-id="7e032-105">If a request to the report server is encased in a try block and that request causes the report server to throw an exception, the exception is caught in the catch block, thus preventing your application from ending unexpectedly.</span></span> <span data-ttu-id="7e032-106">Depois que a exceção tiver sido capturada, você poderá usá-la para instruir o usuário a fazer algo diferente ou simplesmente avisá-lo, de uma forma amigável, de que houve um erro.</span><span class="sxs-lookup"><span data-stu-id="7e032-106">Once the exception is caught, you can use the exception to either instruct the user to do something differently, or just let the user know, in a friendly way, that an error has occurred.</span></span> <span data-ttu-id="7e032-107">Por fim, você poderá usar um bloco finally para limpar qualquer recurso.</span><span class="sxs-lookup"><span data-stu-id="7e032-107">You can then use a finally block to clean up any resources.</span></span> <span data-ttu-id="7e032-108">Idealmente, você deve gerar um plano de manipulação de exceções gerais para evitar a duplicação desnecessária de blocos try/catch.</span><span class="sxs-lookup"><span data-stu-id="7e032-108">Ideally, you should generate a general exception-handling plan to avoid unnecessary duplication of try/catch blocks.</span></span>  
  
 <span data-ttu-id="7e032-109">O exemplo a seguir usa blocos try/catch para aumentar a confiabilidade do código de manipulação de exceções.</span><span class="sxs-lookup"><span data-stu-id="7e032-109">The following example uses try/catch blocks to enhance the reliability of the exception handling code.</span></span>  
  
```  
// C#  
private void PublishReport()  
{  
   int index;  
   string reservedChar;  
   string message;  
  
   // Check the text value of the name text box for "/",  
   // a reserved character  
   index = nameTextBox.Text.IndexOf(@"/");  
  
   if ( index != -1) // The text contains the character  
   {  
      reservedChar = nameTextBox.Text.Substring(index, 1);  
      // Build a user-friendly error message  
      message = "The name of the report cannot contain the reserved character " +  
         "\"" + reservedChar + "\". " +  
         "Please enter a valid name for the report. " +  
         "For more information about reserved characters, " +  
         "consult the online documentation";  
  
      MessageBox.Show(message, "Invalid Input Error");  
   }  
   else // Publish the report  
   {  
      Byte[] definition = null;  
      Warning[] warnings = {};  
      string name = nameTextBox.Text;  
  
      try  
      {  
         FileStream stream = File.OpenRead("MyReport.rdl");  
         definition = new Byte[stream.Length];  
         stream.Read(definition, 0, (int) stream.Length);  
         stream.Close();  
         // Create report with user-defined name  
         rs.CreateCatalogItem("Report", name, "/Samples", false, definition, null, out warnings);  
         MessageBox.Show("Report: {0} created successfully", name);  
      }  
  
      // Catch expected exceptions beginning with the most specific,  
      // moving to the least specific  
      catch(IOException ex)  
      {  
         MessageBox.Show(ex.Message, "File IO Exception");  
      }  
  
      catch (SoapException ex)  
      {  
         // The exception is a SOAP exception, so use  
         // the Detail property's Message element.  
         MessageBox.Show(ex.Detail["Message"].InnerXml, "SOAP Exception");   
      }  
  
      catch (Exception ex)  
      {  
         MessageBox.Show(ex.Message, "General Exception");  
      }  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="7e032-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7e032-110">See Also</span></span>  
 <span data-ttu-id="7e032-111">[Introdução à manipulação de exceção no Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="7e032-111">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="7e032-112">Classe SoapException do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7e032-112">Reporting Services SoapException Class</span></span>](../soapexception-class/reporting-services-soapexception-class.md)  
  
  
