---
title: Prevenindo solicitações inválidas | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- invalid requests [Reporting Services]
- exceptions [Reporting Services], invalid requests
- valid requests [Reporting Services]
ms.assetid: 4a4a2d97-4c10-43a9-8298-ef5a820ea549
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 12343955c46fb98fea75048a38749b1db993fa11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582289"
---
# <a name="preventing-invalid-requests"></a><span data-ttu-id="db3db-102">Impedindo solicitações inválidas</span><span class="sxs-lookup"><span data-stu-id="db3db-102">Preventing Invalid Requests</span></span>
  <span data-ttu-id="db3db-103">Você pode impedir que alguns tipos de exceções sejam lançados ao analisar o fluxo do seu aplicativo e garantir que as solicitações enviadas ao servidor de relatório sejam válidas.</span><span class="sxs-lookup"><span data-stu-id="db3db-103">You can prevent some types of exceptions from being thrown by analyzing your application flow and ensuring that the requests being sent to the report server are valid.</span></span> <span data-ttu-id="db3db-104">Por exemplo, em aplicativos que permitem que usuários adicionem ou atualizem o nome de um relatório, fonte de dados ou outro item de servidor de relatório, valide o texto que possa ser inserido por um usuário.</span><span class="sxs-lookup"><span data-stu-id="db3db-104">For example, in applications that enable users to add or update the name of a report, data source, or other report server item, you should validate the text that a user might enter.</span></span> <span data-ttu-id="db3db-105">Sempre verifique a existência de caracteres reservados antes de enviar a solicitação para um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="db3db-105">You should always check for reserved characters before sending the request to a report server.</span></span> <span data-ttu-id="db3db-106">Use instruções **if** condicionais ou outros constructos lógicos no código para alertar o usuário de que ele não atendeu às condições necessárias para enviar solicitações ao servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="db3db-106">Use conditional **if** statements or other logical constructs in your code to alert the user that they have not met the conditions necessary to send requests to the report server.</span></span>  
  
 <span data-ttu-id="db3db-107">No exemplo de C# simplificado a seguir, os usuários obtêm uma mensagem de erro amigável quando tentam criar um relatório com um nome que contém um caractere de barra (/).</span><span class="sxs-lookup"><span data-stu-id="db3db-107">In the following, simplified C# example, users are presented with a friendly error message when they attempt to create a report with a name that contains a forward slash (/) character.</span></span>  
  
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
         "see the help documentation";  
  
      MessageBox.Show(message, "Invalid Input Error");  
   }  
   else // Publish the report  
   {  
      Byte[] definition = null;  
      Warning[] warnings = {};  
      string name = nameTextBox.Text;  
  
      FileStream stream = File.OpenRead("MyReport.rdl");  
      definition = new Byte[stream.Length];  
      stream.Read(definition, 0, (int) stream.Length);  
      stream.Close();  
      // Create report with user-defined name  
      rs.CreateCatalogItem("Report", name, "/Samples", false, definition, null, out warnings);  
      MessageBox.Show("Report: {0} created successfully", name);  
   }  
}  
```  
  
 <span data-ttu-id="db3db-108">Para obter mais informações sobre os tipos de erros que podem ser impedidos antes das solicitações serem enviadas ao servidor de relatório, consulte [Tabela de erros SoapException](../soapexception-class/soapexception-errors-table.md).</span><span class="sxs-lookup"><span data-stu-id="db3db-108">For more information about the types of errors that can be prevented before requests are sent to the report server, see [SoapException Errors Table](../soapexception-class/soapexception-errors-table.md).</span></span> <span data-ttu-id="db3db-109">Para obter mais informações sobre como aprimorar ainda mais o exemplo anterior usando blocos try/catch, consulte [Usando blocos Try e Catch](using-try-and-catch-blocks.md).</span><span class="sxs-lookup"><span data-stu-id="db3db-109">For more information about further enhancing the previous example using try/catch blocks, see [Using Try and Catch Blocks](using-try-and-catch-blocks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db3db-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="db3db-110">See Also</span></span>  
 <span data-ttu-id="db3db-111">[Introdução à manipulação de exceção no Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="db3db-111">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="db3db-112">Classe SoapException do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="db3db-112">Reporting Services SoapException Class</span></span>](../soapexception-class/reporting-services-soapexception-class.md)  
  
  
