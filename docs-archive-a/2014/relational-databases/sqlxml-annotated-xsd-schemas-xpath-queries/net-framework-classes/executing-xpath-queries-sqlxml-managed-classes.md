---
title: Executando consultas XPath (classes gerenciadas SQLXML) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], SQLXML Managed Classes
- queries [SQLXML], SQLXML Managed Classes
- Managed Classes [SQLXML], executing XPath queries
- mapping schema [SQLXML], XPath queries
- SQLXML Managed Classes, executing XPath queries
ms.assetid: 8bef4c4d-bf0e-4236-a875-fd7d3e058396
author: rothja
ms.author: jroth
ms.openlocfilehash: d8f5fd2612a0992f18e0b7f32c749c352d29d2b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568414"
---
# <a name="executing-xpath-queries-sqlxml-managed-classes"></a><span data-ttu-id="6a4ad-102">Executando consultas XPath (classes gerenciadas por SQLXML)</span><span class="sxs-lookup"><span data-stu-id="6a4ad-102">Executing XPath Queries (SQLXML Managed Classes)</span></span>
  <span data-ttu-id="6a4ad-103">Este exemplo ilustra como consultas de XPath são executadas em relação a um esquema de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="6a4ad-103">This example illustrates how XPath queries are executed against a mapping schema.</span></span>  
  
 <span data-ttu-id="6a4ad-104">Considere este esquema:</span><span class="sxs-lookup"><span data-stu-id="6a4ad-104">Consider this schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Con" sql:relation="Person.Contact" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="FName"    
                     sql:field="FirstName"   
                     type="xsd:string" />   
        <xsd:element name="LName"    
                     sql:field="LastName"    
                     type="xsd:string" />  
     </xsd:sequence>  
     <xsd:attribute name="ContactID" type="xsd:integer" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="6a4ad-105">Este aplicativo C# executa uma consulta de XPath em relação a este esquema (MySchema.xml).</span><span class="sxs-lookup"><span data-stu-id="6a4ad-105">This C# application executes an XPath query against this schema (MySchema.xml).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6a4ad-106">No código, é necessário fornecer o nome da instância do Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] na cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="6a4ad-106">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
using System;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
      static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks;Integrated Security=SSPI";  
  
      public static int testXPath()  
      {  
         Stream strm;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.CommandText = "Con";  
         cmd.CommandType = SqlXmlCommandType.XPath;  
         cmd.RootTag = "ROOT";  
         cmd.SchemaPath = "MySchema.xml";  
         strm = cmd.ExecuteStream();  
         using (StreamReader sr = new StreamReader(strm)){  
            Console.WriteLine(sr.ReadToEnd());  
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
  
### <a name="to-test-the-application"></a><span data-ttu-id="6a4ad-107">Para testar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="6a4ad-107">To test the application</span></span>  
  
1.  <span data-ttu-id="6a4ad-108">Verifique se você tem o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework instalado em seu computador.</span><span class="sxs-lookup"><span data-stu-id="6a4ad-108">Make sure that you have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
2.  <span data-ttu-id="6a4ad-109">Salve o esquema XSD (MySchema.xml) que é fornecido neste exemplo em uma pasta.</span><span class="sxs-lookup"><span data-stu-id="6a4ad-109">Save the XSD schema (MySchema.xml) that is provided in this example in a folder.</span></span>  
  
3.  <span data-ttu-id="6a4ad-110">Salve o código C# (DocSample.cs) fornecido neste exemplo na mesma pasta em que o esquema está armazenado.</span><span class="sxs-lookup"><span data-stu-id="6a4ad-110">Save the C# code (DocSample.cs) that is provided in this example in the same folder in which the schema is stored.</span></span> <span data-ttu-id="6a4ad-111">(Se você armazenar os arquivos em pastas diferentes, terá que editar o código e especificar o caminho de diretório apropriado para o esquema de mapeamento.)</span><span class="sxs-lookup"><span data-stu-id="6a4ad-111">(If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.)</span></span>  
  
4.  <span data-ttu-id="6a4ad-112">Compile o código.</span><span class="sxs-lookup"><span data-stu-id="6a4ad-112">Compile the code.</span></span> <span data-ttu-id="6a4ad-113">Para compilar o código no prompt de comando, use:</span><span class="sxs-lookup"><span data-stu-id="6a4ad-113">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="6a4ad-114">Isso cria um executável (DocSample.exe).</span><span class="sxs-lookup"><span data-stu-id="6a4ad-114">This creates an executable (DocSample.exe).</span></span>  
  
5.  <span data-ttu-id="6a4ad-115">No prompt de comando, execute DocSample.exe.</span><span class="sxs-lookup"><span data-stu-id="6a4ad-115">At the command prompt, execute DocSample.exe.</span></span>  
  
  
