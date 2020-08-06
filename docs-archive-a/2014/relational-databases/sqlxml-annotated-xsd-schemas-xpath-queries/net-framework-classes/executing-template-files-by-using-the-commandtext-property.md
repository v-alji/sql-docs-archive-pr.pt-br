---
title: Executando arquivos de modelo usando a propriedade CommandText | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- Managed Classes [SQLXML], executing template files
- SQLXML Managed Classes, executing template files
- templates [SQLXML], SQLXML Managed Classes
- executing template files [SQLXML]
- CommandText property
ms.assetid: f1b1278d-252d-4a06-836e-4ef77f338ef9
author: rothja
ms.author: jroth
ms.openlocfilehash: f5507e84daf57ca4646fae3efe78c6105af35700
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568415"
---
# <a name="executing-template-files-by-using-the-commandtext-property"></a><span data-ttu-id="822bf-102">Executando os arquivos de modelo usando a propriedade CommandText</span><span class="sxs-lookup"><span data-stu-id="822bf-102">Executing Template Files by Using the CommandText Property</span></span>
  <span data-ttu-id="822bf-103">Este exemplo ilustra como os arquivos de modelo que consistem em consultas SQL ou XPath podem ser especificados usando o CommandTextproperty.</span><span class="sxs-lookup"><span data-stu-id="822bf-103">This example illustrates how template files that consist of SQL or XPath queries can be specified by using the CommandTextproperty.</span></span> <span data-ttu-id="822bf-104">Em vez de especificar a consulta SQL ou XPath como o valor de CommandText, você pode especificar um nome de arquivo como o valor.</span><span class="sxs-lookup"><span data-stu-id="822bf-104">Instead of specifying the SQL or XPath query as the value of CommandText, you can specify a file name as the value.</span></span> <span data-ttu-id="822bf-105">No exemplo a seguir, a propriedade CommandType é especificada como SqlXmlCommandType. TemplateFile.</span><span class="sxs-lookup"><span data-stu-id="822bf-105">In the following example, the CommandType property is specified as SqlXmlCommandType.TemplateFile.</span></span>  
  
 <span data-ttu-id="822bf-106">O aplicativo de exemplo executa este modelo:</span><span class="sxs-lookup"><span data-stu-id="822bf-106">The sample application executes this template:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query>  
    SELECT TOP 2 ContactID, FirstName, LastName   
    FROM   Person.Contact  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="822bf-107">Este é o aplicativo de exemplo do C#.</span><span class="sxs-lookup"><span data-stu-id="822bf-107">This is the C# sample application.</span></span> <span data-ttu-id="822bf-108">Para testar o aplicativo, salve o modelo (TemplateFile.xml) e execute o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="822bf-108">To test the application, save the template (TemplateFile.xml) and then execute the application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="822bf-109">No código, é necessário fornecer o nome da instância do Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] na cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="822bf-109">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
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
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.CommandType = SqlXmlCommandType.TemplateFile;  
         cmd.CommandText = "TemplateFile.xml";  
         using (Stream strm = cmd.ExecuteStream()){  
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
  
### <a name="to-test-the-application"></a><span data-ttu-id="822bf-110">Para testar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="822bf-110">To test the application</span></span>  
  
1.  <span data-ttu-id="822bf-111">Verifique se você tem o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework instalado em seu computador.</span><span class="sxs-lookup"><span data-stu-id="822bf-111">Make sure that you have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
2.  <span data-ttu-id="822bf-112">Salve o modelo XML (TemplateFile.xml) fornecido neste exemplo em uma pasta.</span><span class="sxs-lookup"><span data-stu-id="822bf-112">Save the XML template (TemplateFile.xml) that is provided in this example in a folder.</span></span>  
  
3.  <span data-ttu-id="822bf-113">Salve o código C# (DocSample.cs) fornecido neste exemplo na mesma pasta em que o esquema está armazenado.</span><span class="sxs-lookup"><span data-stu-id="822bf-113">Save the C# code (DocSample.cs) that is provided in this example in the same folder in which the schema is stored.</span></span> <span data-ttu-id="822bf-114">(Se você armazenar os arquivos em pastas diferentes, terá que editar o código e especificar o caminho de diretório apropriado para o esquema de mapeamento.)</span><span class="sxs-lookup"><span data-stu-id="822bf-114">(If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.)</span></span>  
  
4.  <span data-ttu-id="822bf-115">Compile o código.</span><span class="sxs-lookup"><span data-stu-id="822bf-115">Compile the code.</span></span> <span data-ttu-id="822bf-116">Para compilar o código no prompt de comando, use:</span><span class="sxs-lookup"><span data-stu-id="822bf-116">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="822bf-117">Isso cria um executável (DocSample.exe).</span><span class="sxs-lookup"><span data-stu-id="822bf-117">This creates an executable (DocSample.exe).</span></span>  
  
5.  <span data-ttu-id="822bf-118">No prompt de comando, execute DocSample.exe.</span><span class="sxs-lookup"><span data-stu-id="822bf-118">At the command prompt, execute DocSample.exe.</span></span>  
  
 <span data-ttu-id="822bf-119">Se você passar um parâmetro para um modelo, o nome do parâmetro deverá começar com arroba (@); por exemplo, p.Name = " @ContactID ", onde p é um objeto SqlXmlParameter.</span><span class="sxs-lookup"><span data-stu-id="822bf-119">If you pass a parameter to a template, the parameter name must begin with at sign (@); for example, p.Name="@ContactID", where p is a SqlXmlParameter object.</span></span>  
  
 <span data-ttu-id="822bf-120">Este é o modelo atualizado que utiliza um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="822bf-120">This is the updated template which takes one parameter.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:header>  
     <sql:param name='ContactID'>1</sql:param>    
  </sql:header>  
  <sql:query>  
    SELECT ContactID, FirstName, LastName  
    FROM   Person.Contact  
    WHERE  ContactID=@ContactID  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="822bf-121">Este é o código atualizado no qual um parâmetro é transmitido para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="822bf-121">This is the updated code in which a parameter is passed in to execute the template.</span></span>  
  
```  
public static int testParams()  
{  
  
   Stream strm;  
   SqlXmlParameter p;  
  
   SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
   cmd.CommandType = SqlXmlCommandType.TemplateFile;  
   cmd.CommandText = "TemplateFile.xml";  
   p = cmd.CreateParameter();  
   p.Name="@ContactID";  
   p.Value = "1";  
   strm = cmd.ExecuteStream();  
   StreamReader sw = new StreamReader(strm);  
   Console.WriteLine(sw.ReadToEnd());  
   return 0;        
}  
```  
  
  
