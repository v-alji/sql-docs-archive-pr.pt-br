---
title: Métodos de envio em lote | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- methods [Reporting Services], batches
- BatchHeader SOAP header
- Web service [Reporting Services], methods
- Report Server Web service, batching
- batches [Reporting Services]
- XML Web service [Reporting Services], methods
- locking [Reporting Services]
- multiple Web service methods
ms.assetid: 86435534-c9fe-4b49-b88c-7fb6d21976b0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c778da186fdbbfaed17b9635d9ca7309a369552b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582284"
---
# <a name="batching-methods"></a><span data-ttu-id="832eb-102">Métodos de processamento em lote</span><span class="sxs-lookup"><span data-stu-id="832eb-102">Batching Methods</span></span>
  <span data-ttu-id="832eb-103">O uso de cabeçalhos SOAP no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] permite que você inclua vários métodos de serviço Web em uma única operação.</span><span class="sxs-lookup"><span data-stu-id="832eb-103">The use of SOAP headers in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] enables you to include multiple Web service methods in a single operation.</span></span> <span data-ttu-id="832eb-104">Os métodos são executados dentro do escopo de uma única transação de banco de dados, na ordem que são chamados.</span><span class="sxs-lookup"><span data-stu-id="832eb-104">Methods run within the scope of a single database transaction, in the order in which they are called.</span></span>  
  
 <span data-ttu-id="832eb-105">A reversão é uma vantagem da utilização de operações de lote de vários métodos.</span><span class="sxs-lookup"><span data-stu-id="832eb-105">Rollback is one advantage of using multiple-method batch operations.</span></span> <span data-ttu-id="832eb-106">Se houver um erro em qualquer uma das chamadas de método durante a execução do lote, o servidor de relatório interromperá a execução do lote e reverterá qualquer operação anterior.</span><span class="sxs-lookup"><span data-stu-id="832eb-106">If an error occurs on any of the method calls while a batch is running, the report server stops running the batch and rolls back any previous operations.</span></span> <span data-ttu-id="832eb-107">Isso é útil quando uma chamada de método depende da conclusão bem-sucedida de outras chamadas de método daquele lote.</span><span class="sxs-lookup"><span data-stu-id="832eb-107">This is useful when a method call depends on the successful completion of other method calls in that batch.</span></span>  
  
 <span data-ttu-id="832eb-108">O serviço Web não oferece semântica de bloqueio para operações de lote de vários métodos.</span><span class="sxs-lookup"><span data-stu-id="832eb-108">The Web service does not provide locking semantics for multiple-method batch operations.</span></span> <span data-ttu-id="832eb-109">As linhas do banco de dados do servidor de relatório não estarão bloqueadas para atualização até que a mensagem seja enviada ao servidor e que o comando Execute seja chamado.</span><span class="sxs-lookup"><span data-stu-id="832eb-109">Rows in the report server database are not locked for updating until the message is sent to the server and the Execute command is called.</span></span>  
  
 <span data-ttu-id="832eb-110">Também não há nenhum controle de simultaneidade para garantir que o banco de dados não foi alterado desde que os dados foram lidos pela última vez.</span><span class="sxs-lookup"><span data-stu-id="832eb-110">There are also no concurrency controls to guarantee that the database has not changed since the data was last read.</span></span> <span data-ttu-id="832eb-111">Se dois clientes modificarem o mesmo item, a última atualização terá êxito se os parâmetros ainda forem válidos (por exemplo, o item ainda não foi renomeado).</span><span class="sxs-lookup"><span data-stu-id="832eb-111">If two clients modify the same item, the last update succeeds if the parameters are still valid (for example, the item has not been renamed).</span></span>  
  
 <span data-ttu-id="832eb-112">O exemplo a seguir chama o método <xref:ReportService2005.ReportingService2005.CreateFolder%2A> três vezes e executa essas chamadas como um único lote.</span><span class="sxs-lookup"><span data-stu-id="832eb-112">The following example calls the <xref:ReportService2005.ReportingService2005.CreateFolder%2A> method three times and runs these calls as a single batch.</span></span> <span data-ttu-id="832eb-113">Se qualquer uma das chamadas para <xref:ReportService2005.ReportingService2005.CreateFolder%2A> falhar, o lote inteiro será cancelado.</span><span class="sxs-lookup"><span data-stu-id="832eb-113">If any of the calls to <xref:ReportService2005.ReportingService2005.CreateFolder%2A> fail, the entire batch is canceled.</span></span>  
  
```vb  
Imports System  
Imports System.Web.Services.Protocols  
Imports myNamespace.MyReferenceName  
  
Class Sample  
    Sub Main(args() As String)  
        Dim rs As New ReportingService2005()  
        rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
      ' Set the base Web service URL of the source server  
      rs.Url = "http://<Server Name>/reportserver/ReportService2005.asmx"  
  
        Dim bh As New BatchHeader()  
  
        bh.BatchId = service.CreateBatch()  
        rs.BatchHeaderValue = bh  
        rs.CreateFolder("New Folder1", "/", Nothing)  
        rs.CreateFolder("New Folder2", "/", Nothing)  
        rs.CreateFolder("New Folder3", "/", Nothing)  
  
        Console.WriteLine("Creating folders...")  
        rs.BatchHeaderValue = bh  
        rs.ExecuteBatch()  
        Console.WriteLine("Folders created successfully.")  
  
        rs.BatchHeaderValue = Nothing  
    End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Web.Services.Protocols;   
using myNamespace.MyReferenceName;  
  
class Sample  
{  
    static void Main(string[] args)  
    {  
        ReportingService2005 rs = new ReportingService2005();  
        rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
      // Set the base Web service URL of the source server  
      rs.Url = "http://<Server Name>/reportserver/ReportService2005.asmx"  
  
        BatchHeader bh = new BatchHeader();  
  
        bh1.BatchID = service.CreateBatch();  
        rs.BatchHeaderValue = bh;  
        rs.CreateFolder("New Folder1", "/", null);  
        rs.CreateFolder("New Folder2", "/", null);  
        rs.CreateFolder("New Folder3", "/", null);  
  
        Console.WriteLine("Creating folders...");  
        rs.BatchHeaderValue = bh1;  
        rs.ExecuteBatch();  
        Console.WriteLine("Folders created successfully.");  
  
        rs.BatchHeaderValue = null;  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="832eb-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="832eb-114">See Also</span></span>  
 <xref:ReportService2005.ReportingService2005.CancelBatch%2A>   
 <xref:ReportService2005.ReportingService2005.CreateBatch%2A>   
 <span data-ttu-id="832eb-115">[Referência técnica &#40;SSRS&#41;](../technical-reference-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="832eb-115">[Technical Reference &#40;SSRS&#41;](../technical-reference-ssrs.md) </span></span>  
 [<span data-ttu-id="832eb-116">Usando cabeçalhos SOAP do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="832eb-116">Using Reporting Services SOAP Headers</span></span>](using-reporting-services-soap-headers.md)  
  
  
