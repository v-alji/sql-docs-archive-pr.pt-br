---
title: Executando consultas SQL (classes gerenciadas SQLXML) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- queries [SQLXML], SQLXML Managed Classes
- SQLXML Managed Classes, executing SQL queries
- Managed Classes [SQLXML], executing SQL queries
- ExecuteToStream method
- SQL queries [SQLXML]
ms.assetid: a561ae83-a8b6-4b9b-a819-9b86839546b4
author: rothja
ms.author: jroth
ms.openlocfilehash: d869e45de359e602b2451b9f66fa3046f6823c1e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574575"
---
# <a name="executing-sql-queries-sqlxml-managed-classes"></a><span data-ttu-id="01a29-102">Executando consultas SQL (classes gerenciadas SQLXML)</span><span class="sxs-lookup"><span data-stu-id="01a29-102">Executing SQL Queries (SQLXML Managed Classes)</span></span>
  <span data-ttu-id="01a29-103">Este exemplo demonstra como:</span><span class="sxs-lookup"><span data-stu-id="01a29-103">This example demonstrates:</span></span>  
  
-   <span data-ttu-id="01a29-104">Criando parâmetros (objetos SqlXmlParameter).</span><span class="sxs-lookup"><span data-stu-id="01a29-104">Creating parameters (SqlXmlParameter objects).</span></span>  
  
-   <span data-ttu-id="01a29-105">Atribuindo valores às propriedades (nome e valor) dos objetos SqlXmlParameter.</span><span class="sxs-lookup"><span data-stu-id="01a29-105">Assigning values to the properties (Name and Value) of SqlXmlParameter objects.</span></span>  
  
 <span data-ttu-id="01a29-106">Neste exemplo, uma consulta SQL simples é executada para recuperar o nome, o sobrenome e a data de nascimento do funcionário cujo valor de sobrenome é passado como parâmetro.</span><span class="sxs-lookup"><span data-stu-id="01a29-106">In this example, a simple SQL query is executed to retrieve the first name, last name, and birth date of the employee whose last name value is passed as a parameter.</span></span> <span data-ttu-id="01a29-107">Ao especificar o parâmetro (*LastName*), somente a propriedade Value é definida.</span><span class="sxs-lookup"><span data-stu-id="01a29-107">In specifying the parameter (*LastName*), only the Value property is set.</span></span> <span data-ttu-id="01a29-108">A propriedade Name não está definida, pois, nesta consulta, o parâmetro é posicional e nenhum nome é necessário.</span><span class="sxs-lookup"><span data-stu-id="01a29-108">The Name property is not set, because in this query the parameter is positional and no name is required.</span></span>  
  
 <span data-ttu-id="01a29-109">A propriedade CommandType do objeto SqlXmlCommand, por padrão, é **SQL**.</span><span class="sxs-lookup"><span data-stu-id="01a29-109">The CommandType property of the SqlXmlCommand object by default is **Sql**.</span></span> <span data-ttu-id="01a29-110">Portanto, a propriedade não é definida explicitamente.</span><span class="sxs-lookup"><span data-stu-id="01a29-110">Therefore, the property is not explicitly set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="01a29-111">No código, é necessário fornecer o nome da instância do Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] na cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="01a29-111">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
 <span data-ttu-id="01a29-112">Este é o código C#:</span><span class="sxs-lookup"><span data-stu-id="01a29-112">This is the C# code:</span></span>  
  
```  
using System;  
  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
      static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks;Integrated Security=SSPI";  
      public static int testParams()  
      {  
         Stream strm;  
         SqlXmlParameter p;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);        
         cmd.CommandText = "SELECT FirstName, LastName FROM Person.Contact WHERE LastName=? For XML Auto";  
         p = cmd.CreateParameter();  
         p.Value = "Achong";  
         string strResult;  
         try   
         {  
            strm = cmd.ExecuteStream();  
            strm.Position = 0;  
            using(StreamReader sr = new StreamReader(strm))  
            {  
               Console.WriteLine(sr.ReadToEnd());  
            }  
         }  
         catch (SqlXmlException e)  
         {  
            //in case of an error, this prints error returned.  
            e.ErrorStream.Position=0;  
            strResult=new StreamReader(e.ErrorStream).ReadToEnd();  
            System.Console.WriteLine(strResult);  
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
  
### <a name="to-test-the-application"></a><span data-ttu-id="01a29-113">Para testar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="01a29-113">To test the application</span></span>  
  
1.  <span data-ttu-id="01a29-114">Salve o código C# (DocSample.cs) fornecido neste tópico em uma pasta.</span><span class="sxs-lookup"><span data-stu-id="01a29-114">Save the C# code (DocSample.cs) provided in this topic in a folder.</span></span>  
  
2.  <span data-ttu-id="01a29-115">Compile o código.</span><span class="sxs-lookup"><span data-stu-id="01a29-115">Compile the code.</span></span> <span data-ttu-id="01a29-116">Para compilar o código no prompt de comando, use:</span><span class="sxs-lookup"><span data-stu-id="01a29-116">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="01a29-117">Isso cria um executável (DocSample.exe).</span><span class="sxs-lookup"><span data-stu-id="01a29-117">This creates an executable (DocSample.exe).</span></span>  
  
3.  <span data-ttu-id="01a29-118">No prompt de comando, execute DocSample.exe.</span><span class="sxs-lookup"><span data-stu-id="01a29-118">At the command prompt, execute DocSample.exe.</span></span>  
  
 <span data-ttu-id="01a29-119">Para testar este exemplo, é necessário ter o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="01a29-119">To test this example, you must have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
 <span data-ttu-id="01a29-120">Em vez de especificar consultas SQL como o texto de comando, você pode especificar um modelo (conforme mostrado no fragmento de código a seguir) que executa um diagrama de atualização (que também é um modelo) para inserir um registro de cliente.</span><span class="sxs-lookup"><span data-stu-id="01a29-120">Instead of specifying SQL queries as the command text, you can specify a template (as shown in the following code fragment) that executes an updategram (which is also a template) to insert a customer record.</span></span> <span data-ttu-id="01a29-121">Você pode especificar modelos e diagramas de atualização em arquivos e também executar arquivos.</span><span class="sxs-lookup"><span data-stu-id="01a29-121">You can specify templates and updategrams in files and execute files.</span></span> <span data-ttu-id="01a29-122">Para obter mais informações, consulte [executando arquivos de modelo usando a propriedade CommandText](executing-template-files-by-using-the-commandtext-property.md).</span><span class="sxs-lookup"><span data-stu-id="01a29-122">For more information, see [Executing Template Files by Using the CommandText Property](executing-template-files-by-using-the-commandtext-property.md).</span></span>  
  
```  
SqlXmlCommand cmd = new SqlXmlCommand("Provider=SQLOLEDB;Data Source=SqlServerName;Initial Catalog=Database; Integrated Security=SSPI;");  
Stream stm;  
cmd.CommandType = SqlXmlCommandType.UpdateGram;  
cmd.CommandText = "<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql' xmlns:updg='urn:schemas-microsoft-com:xml-updategram'>" +  
      "<updg:sync>" +  
       "<updg:before/>" +  
       "<updg:after>" +  
         "<Customer CustomerID='aaaaa' CustomerName='Some Name' CustomerTitle='SomeTitle' />" +  
       "</updg:after>" +  
       "</updg:sync>" +  
       "</ROOT>";  
  
stm = cmd.ExecuteStream();  
stm = null;  
cmd = null;  
```  
  
## <a name="using-executetostream"></a><span data-ttu-id="01a29-123">Usando ExecuteToStream</span><span class="sxs-lookup"><span data-stu-id="01a29-123">Using ExecuteToStream</span></span>  
 <span data-ttu-id="01a29-124">Se você tiver um fluxo existente, poderá usar o método ExecuteToStream em vez de criar um objeto de fluxo e usar o método execute.</span><span class="sxs-lookup"><span data-stu-id="01a29-124">If you have an existing stream, you can use the ExecuteToStream method instead of creating a Stream object and using the Execute method.</span></span> <span data-ttu-id="01a29-125">O código do exemplo anterior é revisado aqui para usar o método ExecuteToStream:</span><span class="sxs-lookup"><span data-stu-id="01a29-125">The code from the preceding example is revised here to use the ExecuteToStream method:</span></span>  
  
```  
using System;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
   static string ConnString = "Provider=SQLOLEDB;Server=SqlServerName;database=AdventureWorks;Integrated Security=SSPI;";  
   public static int testParams()  
   {  
      SqlXmlParameter p;  
      MemoryStream ms = new MemoryStream();  
      StreamReader sr = new StreamReader(ms);  
      ms.Position = 0;  
      SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
      cmd.CommandText = "select FirstName, LastName from Person.Contact where LastName = ? For XML Auto";  
      p = cmd.CreateParameter();  
      p.Value = "Achong";  
      cmd.ExecuteToStream(ms);  
      ms.Position = 0;  
      Console.WriteLine(sr.ReadToEnd());  
      return 0;        
   }  
   public static int Main(String[] args)  
   {  
      testParams();     
      return 0;  
   }  
}  
```  
  
> [!NOTE]  
>  <span data-ttu-id="01a29-126">Você também pode usar o ExecuteXMLReadermethod que retorna um objeto XmlReader.</span><span class="sxs-lookup"><span data-stu-id="01a29-126">You can also use the ExecuteXMLReadermethod that returns an XmlReader object.</span></span> <span data-ttu-id="01a29-127">Para obter mais informações, consulte [executando consultas SQL usando o método ExecuteXMLReader](executing-sql-queries-by-using-the-executexmlreader-method.md).</span><span class="sxs-lookup"><span data-stu-id="01a29-127">For more information, see [Executing SQL Queries by Using the ExecuteXMLReader Method](executing-sql-queries-by-using-the-executexmlreader-method.md).</span></span>  
  
  
