---
title: Processando XML no lado do cliente (classes gerenciadas SQLXML) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- processing XML on client side [SQLXML]
- client-side XML formatting
- Managed Classes [SQLXML], client-side XML formatting
- SQLXML Managed Classes, client-side XML formatting
- ClientSideXml property
ms.assetid: 5e7ecf18-66fc-49ff-bc50-83635cd7ac0b
author: rothja
ms.author: jroth
ms.openlocfilehash: fb90f7c5c823c750b64f47d0c9df9551b9f857b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569305"
---
# <a name="processing-xml-on-the-client-side-sqlxml-managed-classes"></a><span data-ttu-id="0218b-102">Processando XML no cliente (classes gerenciadas SQLXML)</span><span class="sxs-lookup"><span data-stu-id="0218b-102">Processing XML on the Client Side (SQLXML Managed Classes)</span></span>
  <span data-ttu-id="0218b-103">Este exemplo ilustra o uso da propriedade ClientSideXml.</span><span class="sxs-lookup"><span data-stu-id="0218b-103">This example illustrates the use of the ClientSideXml property.</span></span> <span data-ttu-id="0218b-104">O aplicativo executa um procedimento armazenado no servidor.</span><span class="sxs-lookup"><span data-stu-id="0218b-104">The application executes a stored procedure on the server.</span></span> <span data-ttu-id="0218b-105">O resultado do procedimento armazenado (um conjunto de linhas de duas colunas) é processado no cliente para gerar um documento XML.</span><span class="sxs-lookup"><span data-stu-id="0218b-105">The result of the stored procedure (a two-column rowset) is processed on the client side to produce an XML document.</span></span>  
  
 <span data-ttu-id="0218b-106">O procedimento armazenado GetContacts a seguir retorna **FirstName** e **LastName** de employees na tabela Person. Contact no banco de dados AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="0218b-106">The following GetContacts stored procedure returns **FirstName** and **LastName** of employees in the Person.Contact table in the AdventureWorks database.</span></span>  
  
```  
USE AdventureWorks  
CREATE PROCEDURE GetContacts @LastName varchar(20)  
AS  
SELECT FirstName, LastName  
FROM   Person.Contact  
WHERE LastName = @LastName  
Go  
```  
  
 <span data-ttu-id="0218b-107">Este aplicativo C# executa o procedimento armazenado e especifica a opção FOR XML AUTO ao especificar o valor CommandText.</span><span class="sxs-lookup"><span data-stu-id="0218b-107">This C# application executes the stored procedure and specifies the FOR XML AUTO option in specifying the CommandText value.</span></span> <span data-ttu-id="0218b-108">No aplicativo, a propriedade ClientSideXml do objeto SqlXmlCommand é definida como true.</span><span class="sxs-lookup"><span data-stu-id="0218b-108">In the application, the ClientSideXml property of the SqlXmlCommand object is set to true.</span></span> <span data-ttu-id="0218b-109">Isto permite executar procedimentos armazenados pré-existentes que retornam um conjunto de linhas e aplicam uma transformação XML a ele no cliente.</span><span class="sxs-lookup"><span data-stu-id="0218b-109">This allows you to execute preexisting stored procedures that return a rowset and apply an XML transformation to it on the client.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0218b-110">No código, é necessário fornecer o nome da instância do Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] na cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="0218b-110">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
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
         SqlXmlParameter p;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.ClientSideXml = true;  
         cmd.CommandText = "EXEC GetContacts ? FOR XML NESTED";  
         p = cmd.CreateParameter();  
         p.Value = "Achong";  
         using (Stream strm = cmd.ExecuteStream())   
         {  
            using (StreamReader sr = new StreamReader(strm))  
                  {  
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
  
 <span data-ttu-id="0218b-111">Para testar este exemplo, é necessário ter o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="0218b-111">To test this example, you must have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="0218b-112">Para testar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="0218b-112">To test the application</span></span>  
  
1.  <span data-ttu-id="0218b-113">Crie o procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="0218b-113">Create the stored procedure.</span></span>  
  
2.  <span data-ttu-id="0218b-114">Salve o código C# (DocSample.cs) fornecido neste exemplo em uma pasta.</span><span class="sxs-lookup"><span data-stu-id="0218b-114">Save the C# code (DocSample.cs) that is provided in this example in a folder.</span></span> <span data-ttu-id="0218b-115">Edite o código para especificar as informações de logon e senha apropriadas.</span><span class="sxs-lookup"><span data-stu-id="0218b-115">Edit the code to specify appropriate login and password information.</span></span>  
  
3.  <span data-ttu-id="0218b-116">Compile o código.</span><span class="sxs-lookup"><span data-stu-id="0218b-116">Compile the code.</span></span> <span data-ttu-id="0218b-117">Para compilar o código no prompt de comando, use:</span><span class="sxs-lookup"><span data-stu-id="0218b-117">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="0218b-118">Isso cria um executável (DocSample.exe).</span><span class="sxs-lookup"><span data-stu-id="0218b-118">This creates an executable (DocSample.exe).</span></span>  
  
4.  <span data-ttu-id="0218b-119">No prompt de comando, execute DocSample.exe.</span><span class="sxs-lookup"><span data-stu-id="0218b-119">At the command prompt, execute DocSample.exe.</span></span>  
  
  
