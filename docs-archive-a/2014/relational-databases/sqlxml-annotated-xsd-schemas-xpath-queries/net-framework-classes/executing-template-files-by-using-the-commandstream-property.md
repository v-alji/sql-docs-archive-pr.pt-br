---
title: Executando arquivos de modelo usando a propriedade CommandStream | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- Managed Classes [SQLXML], executing template files
- SQLXML Managed Classes, executing template files
- templates [SQLXML], SQLXML Managed Classes
- CommandStream property
ms.assetid: 55c564e3-56d1-4d85-bcaa-703e2905dd57
author: rothja
ms.author: jroth
ms.openlocfilehash: c57a2ab2f3780a8bc75b53b0cceeee0799fcfcc2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568416"
---
# <a name="executing-template-files-by-using-the-commandstream-property"></a><span data-ttu-id="fb0c0-102">Executando os arquivos de modelo usando a propriedade CommandStream</span><span class="sxs-lookup"><span data-stu-id="fb0c0-102">Executing Template Files by Using the CommandStream Property</span></span>
  <span data-ttu-id="fb0c0-103">Este exemplo ilustra como os arquivos de modelo que consistem em consultas SQL ou XPath podem ser especificados usando a propriedade CommandStream do objeto SqlXmlCommand.</span><span class="sxs-lookup"><span data-stu-id="fb0c0-103">This example illustrates how template files that consist of SQL or XPath queries can be specified by using the CommandStream property of the SqlXmlCommand object.</span></span> <span data-ttu-id="fb0c0-104">Nesse aplicativo, um filestreamobject é aberto para um arquivo de comando e o fluxo de arquivos é atribuído como o CommandStream que é executado.</span><span class="sxs-lookup"><span data-stu-id="fb0c0-104">In this application, a FileStreamobject is opened for a command file, and the file stream is assigned as the CommandStream that is executed.</span></span>  
  
 <span data-ttu-id="fb0c0-105">No exemplo a seguir, a propriedade CommandType é especificada como SqlXmlCommandType. Template (não como TemplateFile).</span><span class="sxs-lookup"><span data-stu-id="fb0c0-105">In the following example, the CommandType property is specified as SqlXmlCommandType.Template (not as TemplateFile).</span></span>  
  
 <span data-ttu-id="fb0c0-106">Este é o modelo XML de exemplo:</span><span class="sxs-lookup"><span data-stu-id="fb0c0-106">This is the sample XML template:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query>  
    SELECT TOP 2 ContactID, FirstName, LastName   
    FROM   Person.Contact  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="fb0c0-107">Esse é o aplicativo C# de exemplo.</span><span class="sxs-lookup"><span data-stu-id="fb0c0-107">This is the sample C# application.</span></span> <span data-ttu-id="fb0c0-108">Para testar o aplicativo, salve o modelo (TemplateFile.xml) e execute o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="fb0c0-108">To test the application, save the template (TemplateFile.xml) and then execute the application.</span></span> <span data-ttu-id="fb0c0-109">O aplicativo executa a consulta especificada no modelo XML e exibe o documento XML gerado na tela.</span><span class="sxs-lookup"><span data-stu-id="fb0c0-109">The application executes the query that is specified in the XML template and displays the XML document that is generated on the screen.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fb0c0-110">No código, é necessário fornecer o nome da instância do Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] na cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="fb0c0-110">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
using System;  
using Microsoft.Data.SqlXml;  
using System.IO;  
  
class Test  
{  
      static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks;Integrated Security=SSPI";  
      public static int testParams()  
      {  
         //Stream strm;  
         MemoryStream ms = new MemoryStream();  
         StreamWriter sw = new StreamWriter(ms);  
         ms.Position = 0;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.CommandStream = new FileStream("TemplateFile.xml", FileMode.Open, FileAccess.Read);  
         cmd.CommandType = SqlXmlCommandType.Template;  
         using (Stream strm = cmd.ExecuteStream())  
         {  
            using (StreamReader sr = new StreamReader(strm)){  
               Console.WriteLine(sr.ReadToEnd());  
            }  
         }  
         return 0;        
      }  
  
      public static int Main(String[] args)  
      {  
         testParams();     
         return 0;  
      }  
   }  
```  
  
### <a name="to-test-the-application"></a><span data-ttu-id="fb0c0-111">Para testar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="fb0c0-111">To test the application</span></span>  
  
1.  <span data-ttu-id="fb0c0-112">Salve o modelo XML (TemplateFile.xml) fornecido neste exemplo em uma pasta.</span><span class="sxs-lookup"><span data-stu-id="fb0c0-112">Save the XML template (TemplateFile.xml) that is provided in this example in a folder.</span></span>  
  
2.  <span data-ttu-id="fb0c0-113">Salve o código C# (DocSample.cs) fornecido neste exemplo na mesma pasta em que o esquema está armazenado.</span><span class="sxs-lookup"><span data-stu-id="fb0c0-113">Save the C# code (DocSample.cs) that is provided in this example in the same folder in which the schema is stored.</span></span> <span data-ttu-id="fb0c0-114">(Se você armazenar os arquivos em pastas diferentes, terá que editar o código e especificar o caminho de diretório apropriado para o esquema de mapeamento.)</span><span class="sxs-lookup"><span data-stu-id="fb0c0-114">(If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.)</span></span>  
  
3.  <span data-ttu-id="fb0c0-115">Compile o código.</span><span class="sxs-lookup"><span data-stu-id="fb0c0-115">Compile the code.</span></span> <span data-ttu-id="fb0c0-116">Para compilar o código no prompt de comando, use:</span><span class="sxs-lookup"><span data-stu-id="fb0c0-116">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="fb0c0-117">Isso cria um executável (DocSample.exe).</span><span class="sxs-lookup"><span data-stu-id="fb0c0-117">This creates an executable (DocSample.exe).</span></span>  
  
4.  <span data-ttu-id="fb0c0-118">No prompt de comando, execute DocSample.exe.</span><span class="sxs-lookup"><span data-stu-id="fb0c0-118">At the command prompt, execute DocSample.exe.</span></span>  
  
  
