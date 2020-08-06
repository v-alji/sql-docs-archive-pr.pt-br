---
title: Aplicando um XSL Transformation (classes gerenciadas SQLXML) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- applying XSL transformations [SQLXML]
- Managed Classes [SQLXML], applying XSL transformations
- SQLXML Managed Classes, applying XSL transformations
- XSL Transformations [SQLXML]
ms.assetid: 8562043b-3e9f-41a3-bb41-92b9f14363c4
author: rothja
ms.author: jroth
ms.openlocfilehash: d3225d838db284e2a34ebd41edb109400d0b72f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574580"
---
# <a name="applying-an-xsl-transformation-sqlxml-managed-classes"></a><span data-ttu-id="4144b-102">Aplicando uma transformação XSL (classes gerenciadas SQLXML)</span><span class="sxs-lookup"><span data-stu-id="4144b-102">Applying an XSL Transformation (SQLXML Managed Classes)</span></span>
  <span data-ttu-id="4144b-103">Neste exemplo, uma consulta SQL é executada no banco de dados AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="4144b-103">In this example, an SQL query is executed against the AdventureWorks database.</span></span> <span data-ttu-id="4144b-104">A transformação XSL é aplicada ao resultado da consulta para gerar uma tabela de duas colunas com os nomes e sobrenomes dos funcionários.</span><span class="sxs-lookup"><span data-stu-id="4144b-104">The XSL transformation is applied to the query result to generate a two-column table of the employees' first and last names.</span></span>  
  
 <span data-ttu-id="4144b-105">A propriedade XslPath do objeto SqlXmlCommand é usada para especificar o arquivo XSL e seu caminho de diretório.</span><span class="sxs-lookup"><span data-stu-id="4144b-105">The XslPath property of the SqlXmlCommand object is used to specify the XSL file and its directory path.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4144b-106">No código, é necessário fornecer o nome da instância do Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] na cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="4144b-106">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
using System;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
      static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks;Integrated Security=SSPI";  
      public static int testXSL()  
      {  
         //Stream strm;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.CommandText = "SELECT TOP 20 FirstName, LastName FROM Person.Contact FOR XML AUTO";  
         cmd.XslPath = "MyXSL.xsl";  
         cmd.RootTag = "root";  
         using (Stream strm = cmd.ExecuteStream()){  
            using (StreamReader sr = new StreamReader(strm)){  
               Console.WriteLine(sr.ReadToEnd());  
            }  
        }  
         return 0;  
      }  
      public static int Main(String[] args)  
      {  
         testXSL();     
         return 0;  
      }  
   }  
```  
  
 <span data-ttu-id="4144b-107">Esta é a folha de estilos XSL que você pode usar para testar o aplicativo:</span><span class="sxs-lookup"><span data-stu-id="4144b-107">This is the XSL style sheet you can use to test the application:</span></span>  
  
```  
<?xml version='1.0' encoding='UTF-8'?>  
 <xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">   
    <xsl:output method="html"/>  
    <xsl:template match = '*'>  
        <xsl:apply-templates />  
    </xsl:template>  
    <xsl:template match = 'Person.Contact'>  
       <TR>  
         <TD><xsl:value-of select = '@FirstName' /></TD>  
         <TD><B><xsl:value-of select = '@LastName' /></B></TD>  
       </TR>  
    </xsl:template>  
    <xsl:template match = '/'>  
      <HTML>  
        <HEAD>  
           <STYLE>th { background-color: #CCCCCC }</STYLE>  
        </HEAD>  
        <BODY>  
         <TABLE border='1' style='width:300;'>  
           <TR><TH colspan='2'>Contacts</TH></TR>  
           <TR><TH >First name</TH><TH>Last name</TH></TR>  
           <xsl:apply-templates select = 'root' />  
         </TABLE>  
        </BODY>  
      </HTML>  
    </xsl:template>  
</xsl:stylesheet>  
```  
  
 <span data-ttu-id="4144b-108">Para testar este exemplo, é necessário ter o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="4144b-108">To test this example, you must have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="4144b-109">Para testar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="4144b-109">To test the application</span></span>  
  
1.  <span data-ttu-id="4144b-110">Salve a folha de estilos XSL em um arquivo (MyXSL.xsl).</span><span class="sxs-lookup"><span data-stu-id="4144b-110">Save the XSL style sheet in a file (MyXSL.xsl).</span></span>  
  
2.  <span data-ttu-id="4144b-111">Salve o código C# (DocSample.cs) que é fornecido nesse exemplo na mesma pasta na qual a folha de estilos está armazenada.</span><span class="sxs-lookup"><span data-stu-id="4144b-111">Save the C# code (DocSample.cs) that is provided in this example in the same folder in which the style sheet is stored.</span></span>  
  
3.  <span data-ttu-id="4144b-112">Compile o código.</span><span class="sxs-lookup"><span data-stu-id="4144b-112">Compile the code.</span></span> <span data-ttu-id="4144b-113">Para compilar o código no prompt de comando, use:</span><span class="sxs-lookup"><span data-stu-id="4144b-113">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="4144b-114">Isso cria um executável (DocSample.exe).</span><span class="sxs-lookup"><span data-stu-id="4144b-114">This creates an executable (DocSample.exe).</span></span>  
  
4.  <span data-ttu-id="4144b-115">No prompt de comando, execute DocSample.exe.</span><span class="sxs-lookup"><span data-stu-id="4144b-115">At the command prompt, execute DocSample.exe.</span></span>  
  
## <a name="applying-an-xsl-transformation-in-the-net-framework"></a><span data-ttu-id="4144b-116">Aplicando uma transformação XSL no .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4144b-116">Applying an XSL Transformation in the .NET Framework</span></span>  
 <span data-ttu-id="4144b-117">Em vez de aplicar uma transformação XSL na camada intermediária, como descrito anteriormente, você pode aplicar uma transformação XSL do lado do cliente (no .NET Framework).</span><span class="sxs-lookup"><span data-stu-id="4144b-117">Instead of applying an XSL transformation in the middle tier, as described previously, you can apply an XSL transformation on the client side (in the .NET Framework).</span></span> <span data-ttu-id="4144b-118">O código C# revisado a seguir mostra como a transformação XSL é aplicada no .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4144b-118">The following revised C# code shows how the XSL transformation is applied in the .NET Framework.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4144b-119">No código, é necessário fornecer o nome da instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] na cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="4144b-119">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
using System;  
using System.Xml;  
using Microsoft.Data.SqlXml;  
using System.IO;  
using System.Xml.XPath;  
using System.Xml.Xsl;  
  
class Test  
{  
      static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks;Integrated Security=SSPI";  
      public static int testXSL()  
      {  
         //Stream strm;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.CommandText = "SELECT TOP 20 FirstName, LastName FROM Person.Contact FOR XML AUTO";  
         cmd.RootTag = "root";  
         using (Stream strm = cmd.ExecuteStream()){  
            XmlReader reader = new XmlReader(strm);  
            XPathDocument xd = new XPathDocument(reader, XmlSpace.Preserve);  
            XslCompiledTransform xslt = new XslCompiledTransform();  
            xslt.Load("MyXSL.xsl");  
            XmlWriter writer = XmlWriter.Create("xslt_output.html");  
            xslt.Transform(xd, writer);  
            reader.Close();  
            writer.Close();  
         }  
         return 0;  
      }  
      public static int Main(String[] args)  
      {  
         testXSL();     
         return 0;  
      }  
   }  
```  
  
  
