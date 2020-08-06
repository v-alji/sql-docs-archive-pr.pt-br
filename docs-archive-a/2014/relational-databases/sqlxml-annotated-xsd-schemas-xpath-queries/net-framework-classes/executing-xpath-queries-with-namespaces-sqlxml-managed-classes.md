---
title: Executando consultas XPath com namespaces (classes gerenciadas SQLXML) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- namespaces property
- XPath queries [SQLXML], SQLXML Managed Classes
- queries [SQLXML], SQLXML Managed Classes
- XPath queries [SQLXML], namespaces
- Managed Classes [SQLXML], executing XPath queries
- SQLXML Managed Classes, executing XPath queries
- namespaces [SQLXML], XPath queries
ms.assetid: c6fc46d8-6b42-4992-a8f1-a8d4b8886e6e
author: rothja
ms.author: jroth
ms.openlocfilehash: a2d726de95929709c1ae958ee22388df3195bc84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568413"
---
# <a name="executing-xpath-queries-with-namespaces-sqlxml-managed-classes"></a><span data-ttu-id="34b75-102">Executando consultas XPath com namespaces (classes gerenciadas SQLXML)</span><span class="sxs-lookup"><span data-stu-id="34b75-102">Executing XPath Queries with Namespaces (SQLXML Managed Classes)</span></span>
  <span data-ttu-id="34b75-103">As consultas XPath podem incluir namespaces.</span><span class="sxs-lookup"><span data-stu-id="34b75-103">XPath queries can include namespaces.</span></span> <span data-ttu-id="34b75-104">Se os elementos de esquema forem qualificados por namespace (use um namespace de destino), as consultas XPath no esquema deverão especificar o namespace.</span><span class="sxs-lookup"><span data-stu-id="34b75-104">If the schema elements are namespace-qualified (use a target namespace), the XPath queries against the schema must specify the namespace.</span></span>  
  
 <span data-ttu-id="34b75-105">Como o caractere curinga (\*) não é suportado no [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0, você precisa especificar a consulta XPath usando um prefixo de namespace.</span><span class="sxs-lookup"><span data-stu-id="34b75-105">Because the wildcard character (\*) is not supported in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0, you must specify the XPath query by using a namespace prefix.</span></span> <span data-ttu-id="34b75-106">Para resolver o prefixo, use a propriedade namespaces para especificar a associação de namespace.</span><span class="sxs-lookup"><span data-stu-id="34b75-106">To resolve the prefix, use the namespaces property to specify the namespace binding.</span></span>  
  
 <span data-ttu-id="34b75-107">No exemplo a seguir, a consulta XPath especifica namespaces usando o caractere curinga ( \* ) e as funções XPath de nome local () e namespace-URI ().</span><span class="sxs-lookup"><span data-stu-id="34b75-107">In the following example, the XPath query specifies namespaces by using the wildcard character (\*) and the local-name() and namespace-uri() XPath functions.</span></span> <span data-ttu-id="34b75-108">Essa consulta XPath retorna todos os elementos em que o nome local é `Employee` e o URI de namespace é `urn:myschema:Contacts`:</span><span class="sxs-lookup"><span data-stu-id="34b75-108">This XPath query returns all the elements where the local name is `Employee` and the namespace URI is `urn:myschema:Contacts`:</span></span>  
  
```  
/*[local-name() = 'Contact' and namespace-uri() = 'urn:myschema:Contacts']  
```  
  
 <span data-ttu-id="34b75-109">No SQLXML 4.0, especifique essa consulta XPath com um prefixo de namespace.</span><span class="sxs-lookup"><span data-stu-id="34b75-109">In SQLXML 4.0, specify this XPath query with a namespace prefix.</span></span> <span data-ttu-id="34b75-110">Um exemplo é `x:Contact`, em que `x` é o prefixo de namespace.</span><span class="sxs-lookup"><span data-stu-id="34b75-110">An example is `x:Contact`, where `x` is the namespace prefix.</span></span> <span data-ttu-id="34b75-111">Considere o esquema XSD a seguir:</span><span class="sxs-lookup"><span data-stu-id="34b75-111">Consider the following XSD schema:</span></span>  
  
```  
<schema xmlns="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema"  
            xmlns:con="urn:myschema:Contacts"  
            targetNamespace="urn:myschema:Contacts">  
<complexType name="ContactType">  
  <attribute name="CID" sql:field="ContactID" type="ID"/>  
  <attribute name="FName" sql:field="FirstName" type="string"/>  
  <attribute name="LName" sql:field="LastName"/>   
</complexType>  
<element name="Contact" type="con:ContactType" sql:relation="Person.Contact"/>  
</schema>  
```  
  
 <span data-ttu-id="34b75-112">Como esse esquema define o namespace de destino, uma consulta XPath (como "Employee") com relação a esse esquema precisa incluir o namespace.</span><span class="sxs-lookup"><span data-stu-id="34b75-112">Because this schema defines the target namespace, an XPath query (such as "Employee") against this schema must include the namespace.</span></span>  
  
 <span data-ttu-id="34b75-113">O exemplo de aplicativo C# a seguir executa uma consulta XPath com relação ao esquema XSD anterior (MySchema.xml).</span><span class="sxs-lookup"><span data-stu-id="34b75-113">The following C# sample application executes an XPath query against the preceding XSD schema (MySchema.xml).</span></span> <span data-ttu-id="34b75-114">Para resolver o prefixo, especifique a associação de namespace usando a propriedade namespaces do objeto SqlXmlCommand.</span><span class="sxs-lookup"><span data-stu-id="34b75-114">To resolve the prefix, specify the namespace binding by using the Namespaces property of the SqlXmlCommand object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="34b75-115">No código, é necessário fornecer o nome da instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] na cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="34b75-115">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
using System;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
      static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks;Integrated Security=SSPI";  
      public static int testXPath()  
      {  
         //Stream strm;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.CommandText = "x:Contact[@CID='1']";  
         cmd.CommandType = SqlXmlCommandType.XPath;  
         cmd.RootTag = "ROOT";  
         cmd.Namespaces = "xmlns:x='urn:myschema:Contacts'";  
         cmd.SchemaPath = "MySchema.xml";  
         using (Stream strm = cmd.ExecuteStream()){  
            using (StreamReader sr = new StreamReader(strm)){  
               Console.WriteLine(sr.ReadToEnd());  
            }  
         }  
         return 0;  
      }  
      public static int Main(String[] args)  
      {  
         testXPath();  
         return 0;  
      }  
   }  
```  
  
 <span data-ttu-id="34b75-116">Para testar este exemplo, é necessário ter o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="34b75-116">To test this example, you must have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="34b75-117">Para testar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="34b75-117">To test the application</span></span>  
  
1.  <span data-ttu-id="34b75-118">Salve o esquema XSD (MySchema.xml) que é fornecido neste exemplo em uma pasta.</span><span class="sxs-lookup"><span data-stu-id="34b75-118">Save the XSD schema (MySchema.xml) that is provided in this example in a folder.</span></span>  
  
2.  <span data-ttu-id="34b75-119">Salve o código C# (DocSample.cs) fornecido neste exemplo na mesma pasta em que o esquema está armazenado.</span><span class="sxs-lookup"><span data-stu-id="34b75-119">Save the C# code (DocSample.cs) that is provided in this example in the same folder in which the schema is stored.</span></span> <span data-ttu-id="34b75-120">(Se você armazenar os arquivos em pastas diferentes, terá que editar o código e especificar o caminho de diretório apropriado para o esquema de mapeamento.)</span><span class="sxs-lookup"><span data-stu-id="34b75-120">(If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.)</span></span>  
  
3.  <span data-ttu-id="34b75-121">Compile o código.</span><span class="sxs-lookup"><span data-stu-id="34b75-121">Compile the code.</span></span> <span data-ttu-id="34b75-122">Para compilar o código no prompt de comando, use:</span><span class="sxs-lookup"><span data-stu-id="34b75-122">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="34b75-123">Isso cria um executável (DocSample.exe).</span><span class="sxs-lookup"><span data-stu-id="34b75-123">This creates an executable (DocSample.exe).</span></span>  
  
4.  <span data-ttu-id="34b75-124">No prompt de comando, execute DocSample.exe.</span><span class="sxs-lookup"><span data-stu-id="34b75-124">At the command prompt, execute DocSample.exe.</span></span>  
  
  
