---
title: Aplicando um XSL Transformation (provedor SQLXMLOLEDB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXMLOLEDB Provider, applying XSL transformations
- applying XSL transformations [SQLXML]
- xsl property
- Base Path property
- XSL Transformations [SQLXML]
ms.assetid: cb5e41ab-dd20-4873-af20-f417bd1bbf6d
author: rothja
ms.author: jroth
ms.openlocfilehash: 7fbb427a95d9f2308bf65724758a4a1563b42575
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575040"
---
# <a name="applying-an-xsl-transformation-sqlxmloledb-provider"></a><span data-ttu-id="d519a-102">Aplicando um XSL Transformation (provedor SQLXMLOLEDB)</span><span class="sxs-lookup"><span data-stu-id="d519a-102">Applying an XSL Transformation (SQLXMLOLEDB Provider)</span></span>
  <span data-ttu-id="d519a-103">Neste exemplo de aplicativo ADO, uma consulta SQL é executada e uma transformação em XSL é aplicada ao resultado.</span><span class="sxs-lookup"><span data-stu-id="d519a-103">In this sample ADO application, an SQL query is executed, and an XSL transformation is applied to the result.</span></span> <span data-ttu-id="d519a-104">Definir a propriedade ClientSideXML como true impõe o processamento do conjunto de linhas no lado do cliente.</span><span class="sxs-lookup"><span data-stu-id="d519a-104">Setting the ClientSideXML property to True enforces the processing of the rowset on the client side.</span></span> <span data-ttu-id="d519a-105">O dialeto do comando é definido como {5d531cb2-e6ed-11d2-b252-00c04f681b71}, porque a consulta SQL é especificada em um modelo e esse dialeto precisa ser especificado ao executar um modelo.</span><span class="sxs-lookup"><span data-stu-id="d519a-105">The command dialect is set to {5d531cb2-e6ed-11d2-b252-00c04f681b71}, because the SQL query is specified in a template and this dialect must be specified when executing a template.</span></span> <span data-ttu-id="d519a-106">A propriedade XSL especifica o arquivo XSL a ser usado para aplicar a transformação.</span><span class="sxs-lookup"><span data-stu-id="d519a-106">The xsl property specifies the XSL file to use to apply the transformation.</span></span> <span data-ttu-id="d519a-107">O valor da propriedade caminho base é usado para pesquisar o arquivo XSL.</span><span class="sxs-lookup"><span data-stu-id="d519a-107">The value of Base Path property is used to search for the XSL file.</span></span> <span data-ttu-id="d519a-108">Se você especificar um caminho no valor da propriedade XSL, o caminho será relativo ao caminho especificado na propriedade caminho base.</span><span class="sxs-lookup"><span data-stu-id="d519a-108">If you specify a path in the value of the xsl property, the path is relative to the path that is specified in the Base Path property.</span></span>  
  
 <span data-ttu-id="d519a-109">Este exemplo mostra como usar as propriedades específicas do Provedor SQLXMLOLEDB a seguir:</span><span class="sxs-lookup"><span data-stu-id="d519a-109">This example shows how to use the following SQLXMLOLEDB Provider-specific properties:</span></span>  
  
-   <span data-ttu-id="d519a-110">ClientSideXML</span><span class="sxs-lookup"><span data-stu-id="d519a-110">ClientSideXML</span></span>  
  
-   <span data-ttu-id="d519a-111">xsl</span><span class="sxs-lookup"><span data-stu-id="d519a-111">xsl</span></span>  
  
 <span data-ttu-id="d519a-112">Nesse aplicativo de exemplo de ADO do lado cliente, um modelo XML que consiste em uma consulta SQL é executado no servidor.</span><span class="sxs-lookup"><span data-stu-id="d519a-112">In this client-side ADO sample application, an XML template that consists of an SQL query is executed on the server.</span></span>  
  
 <span data-ttu-id="d519a-113">Como a propriedade ClientSideXML é definida como true, a instrução SELECT sem a cláusula FOR XML é enviada ao servidor.</span><span class="sxs-lookup"><span data-stu-id="d519a-113">Because the ClientSideXML property is set to True, the SELECT statement without the FOR XML clause is sent to the server.</span></span> <span data-ttu-id="d519a-114">O servidor executa a consulta e retorna um conjunto de linhas para o cliente.</span><span class="sxs-lookup"><span data-stu-id="d519a-114">The server executes the query and returns a rowset to the client.</span></span> <span data-ttu-id="d519a-115">O cliente aplica a transformação de FOR XML ao conjunto de linhas e produz o documento XML.</span><span class="sxs-lookup"><span data-stu-id="d519a-115">The client then applies the FOR XML transformation to the rowset and produces the XML document.</span></span>  
  
 <span data-ttu-id="d519a-116">A propriedade XSL é especificada no aplicativo; Portanto, a transformação XSL é aplicada ao documento XML gerado no cliente e o resultado é uma tabela de duas colunas.</span><span class="sxs-lookup"><span data-stu-id="d519a-116">The xsl property is specified in the application; therefore, the XSL transformation is applied to the XML document that is generated on the client, and the result is a two-column table.</span></span>  
  
 <span data-ttu-id="d519a-117">Para executar o comando de modelo, o modelo XML dialeto-{5d531cb2-e6ed-11d2-b252-00c04f681b71}-deve ser especificado.</span><span class="sxs-lookup"><span data-stu-id="d519a-117">To execute the template command, the XML template dialect - {5d531cb2-e6ed-11d2-b252-00c04f681b71} - must be specified.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d519a-118">No código, é necessário fornecer o nome da instância do Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] na cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="d519a-118">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span> <span data-ttu-id="d519a-119">Além disso, este exemplo especifica o uso do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client para o provedor de dados, o que requer a instalação de software cliente de rede adicional.</span><span class="sxs-lookup"><span data-stu-id="d519a-119">Also, this example specifies the use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client for the data provider which requires additional network client software to be installed.</span></span> <span data-ttu-id="d519a-120">Para obter mais informações, consulte [requisitos do sistema para SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="d519a-120">For more information, see [System Requirements for SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span></span>  
  
```  
Option Explicit  
Sub main()  
Dim oTestStream As New ADODB.Stream  
Dim oTestConnection As New ADODB.Connection  
Dim oTestCommand As New ADODB.Command  
oTestConnection.Open "provider=SQLXMLOLEDB.4.0;data provider=SQLNCLI11;data source=SqlServerName;initial catalog=AdventureWorks;Integrated Security=SSPI;"  
Set oTestCommand.ActiveConnection = oTestConnection  
oTestCommand.Properties("ClientSideXML") = True  
oTestCommand.CommandText = _  
        "<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql' >" & _  
       " <sql:query> " & _  
        "   SELECT TOP 25 FirstName, LastName FROM Person.Contact FOR XML AUTO " & _  
        "   </sql:query> " & _  
        " </ROOT> "  
oTestStream.Open  
' You need the dialect if you are executing a template.  
oTestCommand.Dialect = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
oTestCommand.Properties("Output Stream").Value = oTestStream  
oTestCommand.Properties("Base Path").Value = "c:\Schemas\SQLXML4\ExecuteTemplateWithXSL\"  
oTestCommand.Properties("xsl").Value = "myxsl.xsl"  
oTestCommand.Execute , , adExecuteStream  
  
oTestStream.Position = 0  
oTestStream.Charset = "utf-8"  
Debug.Print oTestStream.ReadText(adReadAll)  
End Sub  
Sub Form_Load()  
 main  
End Sub  
```  
  
 <span data-ttu-id="d519a-121">A seguir está o modelo XSL.</span><span class="sxs-lookup"><span data-stu-id="d519a-121">The XSL template follows.</span></span> <span data-ttu-id="d519a-122">O resultado da aplicação desse modelo XSL é uma tabela de duas colunas.</span><span class="sxs-lookup"><span data-stu-id="d519a-122">The result of applying this XSL template is a two-column table.</span></span>  
  
```  
<?xml version='1.0' encoding='UTF-8'?>            
 <xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">   
  
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
           <TR>  
              <TH >First name</TH>  
              <TH>Last name</TH>  
           </TR>  
           <xsl:apply-templates select = 'ROOT' />  
         </TABLE>  
        </BODY>  
      </HTML>  
    </xsl:template>  
</xsl:stylesheet>  
```  
  
  
