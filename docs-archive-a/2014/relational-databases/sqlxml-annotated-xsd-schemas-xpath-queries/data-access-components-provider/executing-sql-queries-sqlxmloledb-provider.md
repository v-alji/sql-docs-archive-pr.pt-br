---
title: Executando consultas SQL (provedor SQLXMLOLEDB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- queries [SQLXML], SQLXMLOLEDB Provider
- xml root property [SQLXML]
- SQLXMLOLEDB Provider, executing SQL queries
- SQL queries [SQLXML]
ms.assetid: 50334cf5-9c87-4c00-9beb-e08577c4fa82
author: rothja
ms.author: jroth
ms.openlocfilehash: a1e2cc87f90700e3b81a5a2ec3dd80f219a9b1d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575753"
---
# <a name="executing-sql-queries-sqlxmloledb-provider"></a><span data-ttu-id="25b9e-102">Executando consultas SQL (provedor SQLXMLOLEDB)</span><span class="sxs-lookup"><span data-stu-id="25b9e-102">Executing SQL Queries (SQLXMLOLEDB Provider)</span></span>
  <span data-ttu-id="25b9e-103">Este exemplo ilustra o uso das seguintes propriedades específicas de provedor SQLXMLOLEDB:</span><span class="sxs-lookup"><span data-stu-id="25b9e-103">This example illustrates the use of the following SQLXMLOLEDB Provider-specific properties:</span></span>  
  
-   <span data-ttu-id="25b9e-104">ClientSideXML</span><span class="sxs-lookup"><span data-stu-id="25b9e-104">ClientSideXML</span></span>  
  
-   <span data-ttu-id="25b9e-105">xml root</span><span class="sxs-lookup"><span data-stu-id="25b9e-105">xml root</span></span>  
  
 <span data-ttu-id="25b9e-106">Neste aplicativo de exemplo ADO do lado do cliente, uma consulta SQL simples é executada no cliente.</span><span class="sxs-lookup"><span data-stu-id="25b9e-106">In this client-side ADO sample application, a simple SQL query is executed on the client.</span></span> <span data-ttu-id="25b9e-107">Como a propriedade ClientSideXML é definida como true, a instrução SELECT sem a cláusula FOR XML é enviada ao servidor.</span><span class="sxs-lookup"><span data-stu-id="25b9e-107">Because the ClientSideXML property is set to True, the SELECT statement without the FOR XML clause is sent to the server.</span></span> <span data-ttu-id="25b9e-108">O servidor executa a consulta e retorna um conjunto de linhas para o cliente.</span><span class="sxs-lookup"><span data-stu-id="25b9e-108">The server executes the query and returns a rowset to the client.</span></span> <span data-ttu-id="25b9e-109">O cliente aplica a transformação de FOR XML ao conjunto de linhas e produz um documento XML.</span><span class="sxs-lookup"><span data-stu-id="25b9e-109">The client then applies the FOR XML transformation to the rowset and produces an XML document.</span></span>  
  
 <span data-ttu-id="25b9e-110">A propriedade raiz XML fornece o único elemento raiz de nível superior para o documento XML gerado.</span><span class="sxs-lookup"><span data-stu-id="25b9e-110">The xml root property provides the single top-level root element for the XML document that is generated.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="25b9e-111">No código, é necessário fornecer o nome da instância do Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] na cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="25b9e-111">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span> <span data-ttu-id="25b9e-112">Este exemplo também especifica o uso do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) para o provedor de dados, o que requer a instalação adicional do software cliente da rede.</span><span class="sxs-lookup"><span data-stu-id="25b9e-112">Also, this example specifies the use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) for the data provider, which requires additional network client software to be installed.</span></span> <span data-ttu-id="25b9e-113">Para obter mais informações, consulte [requisitos do sistema para SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="25b9e-113">For more information, see [System Requirements for SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span></span>  
  
```  
Option Explicit  
Sub main()  
Dim oTestStream As New ADODB.Stream  
Dim oTestConnection As New ADODB.Connection  
Dim oTestCommand As New ADODB.Command  
  
oTestConnection.Open "provider=SQLXMLOLEDB.4.0;data provider=SQLNCLI11;data source=SqlServerName;initial catalog=AdventureWorks;Integrated Security=SSPI ;"  
oTestCommand.ActiveConnection = oTestConnection  
oTestCommand.Properties("ClientSideXML") = True  
oTestCommand.CommandText = "SELECT TOP 10 FirstName, LastName FROM Person.Contact FOR XML AUTO"  
oTestStream.Open  
oTestCommand.Properties("Output Stream").Value = oTestStream  
oTestCommand.Properties("xml root") = "root"  
oTestCommand.Execute , , adExecuteStream  
  
oTestStream.Position = 0  
oTestStream.Charset = "utf-8"  
Debug.Print oTestStream.ReadText(adReadAll)  
End Sub  
Sub Form_Load()  
 main  
End Sub  
```  
  
  
