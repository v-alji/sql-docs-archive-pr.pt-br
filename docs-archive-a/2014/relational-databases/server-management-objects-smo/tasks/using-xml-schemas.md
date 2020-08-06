---
title: Usando esquemas XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- XML [SMO]
ms.assetid: 9d04de01-efeb-4b2d-8c28-3234bc7ff2f3
author: stevestein
ms.author: sstein
ms.openlocfilehash: a0e5c58bb05da7025651a4e55e29541d694ba1ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685484"
---
# <a name="using-xml-schemas"></a><span data-ttu-id="0d2a7-102">Usando esquemas XML</span><span class="sxs-lookup"><span data-stu-id="0d2a7-102">Using XML Schemas</span></span>
  <span data-ttu-id="0d2a7-103">A programação XML no SMO se restringe ao fornecimento de tipos de dados XML, namespaces XML e indexação simples em colunas de tipo de dados XML.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-103">XML programming in SMO is limited to providing XML data types, XML namespaces, and simple indexing on XML data type columns.</span></span>  
  
 [!INCLUDE[msCoName](../../../includes/msconame-md.md)]<span data-ttu-id="0d2a7-104">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]fornece armazenamento nativo para instâncias de documento XML.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-104">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provides native storage for XML document instances.</span></span> <span data-ttu-id="0d2a7-105">Esquemas XML permitem que você defina tipos de dados XML complexos, que podem ser usados para validar documentos XML a fim de garantir a integridade dos dados.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-105">XML schemas let you define complex XML data types, which can be used to validate XML documents to ensure data integrity.</span></span> <span data-ttu-id="0d2a7-106">O esquema XML é definido no objeto <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection>.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-106">The XML schema is defined in the <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d2a7-107">Exemplo</span><span class="sxs-lookup"><span data-stu-id="0d2a7-107">Example</span></span>  
 <span data-ttu-id="0d2a7-108">Para usar qualquer exemplo de código fornecido, será necessário escolher o ambiente de programação, o modelo de programação e a linguagem de programação para criar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-108">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="0d2a7-109">Para obter mais informações, consulte [criar um projeto Visual Basic Smo no Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) ou [criar um projeto do Visual C&#35; Smo no Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="0d2a7-109">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-an-xml-schema-in-visual-basic"></a><span data-ttu-id="0d2a7-110">Criando um esquema XML no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0d2a7-110">Creating an XML Schema in Visual Basic</span></span>  
 <span data-ttu-id="0d2a7-111">Este exemplo de código mostra como criar um esquema XML com o objeto <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection>.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-111">This code example shows how to create an XML schema by using the <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection> object.</span></span> <span data-ttu-id="0d2a7-112">A propriedade <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A>, que define a coleção de esquemas XML, contém várias aspas duplas.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-112">The <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A> property, which defines the XML schema collection, contains several double quotation marks.</span></span> <span data-ttu-id="0d2a7-113">Elas são substituídas pela cadeia de caracteres `chr(34)`.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-113">These are replaced by the `chr(34)` string.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBXMLSchema1](SMO How to#SMO_VBXMLSchema1)]  -->  
  
## <a name="creating-an-xml-schema-in-visual-c"></a><span data-ttu-id="0d2a7-114">Criando um esquema XML no Visual C#</span><span class="sxs-lookup"><span data-stu-id="0d2a7-114">Creating an XML Schema in Visual C#</span></span>  
 <span data-ttu-id="0d2a7-115">Este exemplo de código mostra como criar um esquema XML com o objeto <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection>.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-115">This code example shows how to create an XML schema by using the <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection> object.</span></span> <span data-ttu-id="0d2a7-116">A propriedade <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A>, que define a coleção de esquemas XML, contém várias aspas duplas.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-116">The <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A> property, which defines the XML schema collection, contains several double quotation marks.</span></span> <span data-ttu-id="0d2a7-117">Elas são substituídas pela cadeia de caracteres `chr(34)`.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-117">These are replaced by the `chr(34)` string.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
            Server srv = default(Server);  
            srv = new Server();  
            //Reference the AdventureWorks2012 database.   
            Database db = default(Database);  
            db = srv.Databases["AdventureWorks2012"];  
            //Define an XmlSchemaCollection object by supplying the parent  
            // database and name arguments in the constructor.   
            XmlSchemaCollection xsc = default(XmlSchemaCollection);  
            xsc = new XmlSchemaCollection(db, "MySampleCollection");  
            xsc.Text = "<schema xmlns=" + Strings.Chr(34) + "http://www.w3.org/2001/XMLSchema" + Strings.Chr(34) + " xmlns:ns=" + Strings.Chr(34) + "http://ns" + Strings.Chr(34) + "><element name=" + Strings.Chr(34) + "e" + Strings.Chr(34) + " type=" + Strings.Chr(34) + "dateTime" + Strings.Chr(34) + "/></schema>";  
            //Create the XML schema collection on the instance of SQL Server.   
            xsc.Create();  
        }  
```  
  
## <a name="creating-an-xml-schema-in-powershell"></a><span data-ttu-id="0d2a7-118">Criando um esquema XML no PowerShell</span><span class="sxs-lookup"><span data-stu-id="0d2a7-118">Creating an XML Schema in PowerShell</span></span>  
 <span data-ttu-id="0d2a7-119">Este exemplo de código mostra como criar um esquema XML com o objeto <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection>.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-119">This code example shows how to create an XML schema by using the <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection> object.</span></span> <span data-ttu-id="0d2a7-120">A propriedade <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A>, que define a coleção de esquemas XML, contém várias aspas duplas.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-120">The <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A> property, which defines the XML schema collection, contains several double quotation marks.</span></span> <span data-ttu-id="0d2a7-121">Elas são substituídas pela cadeia de caracteres `chr(34)`.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-121">These are replaced by the `chr(34)` string.</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance replace LocalMachine with the physical server  
cd \sql\LocalHost  
$srv = Get-Item default  
  
#Reference the AdventureWorks database.  
$db = $srv.Databases["AdventureWorks2012"]  
  
#Create a new schema collection  
$xsc = New-Object -TypeName Microsoft.SqlServer.Management.SMO.XmlSchemaCollection `  
-argumentlist $db,"MySampleCollection"  
  
#Add the xml  
$dq = '"' # the double quote character  
$xsc.Text = "<schema xmlns=" + $dq + "http://www.w3.org/2001/XMLSchema" + $dq + `  
"  xmlns:ns=" + $dq + "http://ns" + $dq + "><element name=" + $dq + "e" + $dq +`  
 " type=" + $dq + "dateTime" + $dq + "/></schema>"  
  
#Create the XML schema collection on the instance of SQL Server.  
$xsc.Create()  
```  
