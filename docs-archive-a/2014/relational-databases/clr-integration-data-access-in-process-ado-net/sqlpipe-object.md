---
title: Objeto SqlPipe | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- custom result sets [CLR integration]
- SqlPipe object
- tabular results
ms.assetid: 3e090faf-085f-4c01-a565-79e3f1c36e3b
author: rothja
ms.author: jroth
ms.openlocfilehash: 0044815a0b20d72b48b87bfe8f693d7196aaeaf3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575169"
---
# <a name="sqlpipe-object"></a><span data-ttu-id="ffcb2-102">Objeto SqlPipe</span><span class="sxs-lookup"><span data-stu-id="ffcb2-102">SqlPipe Object</span></span>
  <span data-ttu-id="ffcb2-103">Nas versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], era muito comum gravar um procedimento armazenado (ou um procedimento armazenado estendido) para enviar resultados ou parâmetros de saída ao cliente que fez a chamada.</span><span class="sxs-lookup"><span data-stu-id="ffcb2-103">In previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], it is very common to write a stored procedure (or an extended stored procedure) that sends results or output parameters to the calling client.</span></span>  
  
 <span data-ttu-id="ffcb2-104">Em um procedimento armazenado [!INCLUDE[tsql](../../includes/tsql-md.md)], qualquer instrução `SELECT` que retorna zero ou mais linhas envia os resultados ao "pipe" do chamador conectado.</span><span class="sxs-lookup"><span data-stu-id="ffcb2-104">In a [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure, any `SELECT` statement that returns zero or more rows sends the results to the connected caller's "pipe."</span></span>  
  
 <span data-ttu-id="ffcb2-105">No caso dos objetos de banco de dados CLR (common language runtime) executados no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], é possível enviar resultados ao pipe conectado usando os métodos `Send` do objeto `SqlPipe`.</span><span class="sxs-lookup"><span data-stu-id="ffcb2-105">For common language runtime (CLR) database objects running in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can send results to the connected pipe using the `Send` methods of the `SqlPipe` object.</span></span> <span data-ttu-id="ffcb2-106">Acesse a propriedade `Pipe` do objeto `SqlContext` para obter o objeto `SqlPipe`.</span><span class="sxs-lookup"><span data-stu-id="ffcb2-106">Access the `Pipe` property of the `SqlContext` object to obtain the `SqlPipe` object.</span></span> <span data-ttu-id="ffcb2-107">A classe `SqlPipe` é conceitualmente semelhante à classe `Response` localizada no ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ffcb2-107">The `SqlPipe` class is conceptually similar to the `Response` class found in ASP.NET.</span></span> <span data-ttu-id="ffcb2-108">Para obter mais informações, consulte a documentação de referência da classe SqlPipe no .NET Framework SDK (Software Development Kit).</span><span class="sxs-lookup"><span data-stu-id="ffcb2-108">For more information, see the SqlPipe Class reference documentation in the .NET Framework software development kit.</span></span>  
  
## <a name="returning-tabular-results-and-messages"></a><span data-ttu-id="ffcb2-109">Retornando resultados tabulares e mensagens</span><span class="sxs-lookup"><span data-stu-id="ffcb2-109">Returning Tabular Results and Messages</span></span>  
 <span data-ttu-id="ffcb2-110">A `SqlPipe` tem um método `Send` com três sobrecargas.</span><span class="sxs-lookup"><span data-stu-id="ffcb2-110">The `SqlPipe` has a `Send` method, which has three overloads.</span></span> <span data-ttu-id="ffcb2-111">Eles são:</span><span class="sxs-lookup"><span data-stu-id="ffcb2-111">They are:</span></span>  
  
-   `void Send(string message)`  
  
-   `void Send(SqlDataReader reader)`  
  
-   `void Send(SqlDataRecord record)`  
  
 <span data-ttu-id="ffcb2-112">O método `Send` envia dados diretamente ao cliente ou chamador.</span><span class="sxs-lookup"><span data-stu-id="ffcb2-112">The `Send` method sends data straight to the client or caller.</span></span> <span data-ttu-id="ffcb2-113">Em geral, é o cliente que consome a saída de `SqlPipe`, mas no caso de procedimentos armazenados aninhados CLR, o consumidor de saída também pode ser um procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="ffcb2-113">It is usually the client that consumes the output from the `SqlPipe`, but in the case of nested CLR stored procedures the output consumer can also be a stored procedure.</span></span> <span data-ttu-id="ffcb2-114">Por exemplo, Procedure1 chama SqlCommand.ExecuteReader () com o texto de comando "EXEC Procedure2".</span><span class="sxs-lookup"><span data-stu-id="ffcb2-114">For example, Procedure1 calls SqlCommand.ExecuteReader() with the command text "EXEC Procedure2".</span></span> <span data-ttu-id="ffcb2-115">Procedure2 também é um procedimento armazenado gerenciado.</span><span class="sxs-lookup"><span data-stu-id="ffcb2-115">Procedure2 is also a managed stored procedure.</span></span> <span data-ttu-id="ffcb2-116">Se Procedure2 chamar SqlPipe.Send (SqlDataRecord) agora, a linha será enviada ao leitor de Procedure1, não ao cliente.</span><span class="sxs-lookup"><span data-stu-id="ffcb2-116">If Procedure2 now calls SqlPipe.Send( SqlDataRecord ), the row is sent to Procedure1's reader, not the client.</span></span>  
  
 <span data-ttu-id="ffcb2-117">O método `Send` envia uma mensagem de cadeia de caracteres que aparece no cliente como uma mensagem de informações, equivalente a PRINT em [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ffcb2-117">The `Send` method sends a string message that appears on the client as an information message, equivalent to PRINT in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="ffcb2-118">Ele também pode enviar um conjunto de resultados de uma única linha usando `SqlDataRecord`ou um conjunto de resultados de várias linhas usando `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="ffcb2-118">It can also send a single-row result-set using `SqlDataRecord`, or a multi-row result-set using a `SqlDataReader`.</span></span>  
  
 <span data-ttu-id="ffcb2-119">O objeto `SqlPipe` também tem um método `ExecuteAndSend`.</span><span class="sxs-lookup"><span data-stu-id="ffcb2-119">The `SqlPipe` object also has an `ExecuteAndSend` method.</span></span> <span data-ttu-id="ffcb2-120">Esse método pode ser usado para executar um comando (transmitido como um objeto `SqlCommand`) e enviar resultados diretamente ao chamador.</span><span class="sxs-lookup"><span data-stu-id="ffcb2-120">This method can be used to execute a command (passed as a `SqlCommand` object) and send results directly back to the caller.</span></span> <span data-ttu-id="ffcb2-121">Em caso de erros no comando enviado, as exceções são enviadas ao pipe, mas uma cópia também é enviada ao código gerenciado que efetuou a chamada.</span><span class="sxs-lookup"><span data-stu-id="ffcb2-121">If there are errors in the command that was submitted, exceptions are sent to the pipe, but a copy is also sent to calling managed code.</span></span> <span data-ttu-id="ffcb2-122">Se o código que efetuou a chamada não retornar a exceção, ele propagará a pilha no código [!INCLUDE[tsql](../../includes/tsql-md.md)] e aparecerá duas vezes na saída.</span><span class="sxs-lookup"><span data-stu-id="ffcb2-122">If the calling code does not catch the exception, it propagates up the stack to the [!INCLUDE[tsql](../../includes/tsql-md.md)] code and appears in the output twice.</span></span> <span data-ttu-id="ffcb2-123">Caso o código que efetuou a chamada retorne a exceção, o consumidor de pipe ainda verá o erro, mas não haverá erro duplicado.</span><span class="sxs-lookup"><span data-stu-id="ffcb2-123">If the calling code does catch the exception, the pipe consumer still sees the error, but there is not a duplicate error.</span></span>  
  
 <span data-ttu-id="ffcb2-124">Ele só pode obter um `SqlCommand` que esteja associado à conexão de contexto; ele não pode retornar um comando associado à conexão sem-contexto.</span><span class="sxs-lookup"><span data-stu-id="ffcb2-124">It can only take a `SqlCommand` that is associated with the context connection; it cannot take a command that is associated with the non-context connection.</span></span>  
  
## <a name="returning-custom-result-sets"></a><span data-ttu-id="ffcb2-125">Retornando conjuntos de resultados personalizados</span><span class="sxs-lookup"><span data-stu-id="ffcb2-125">Returning Custom Result Sets</span></span>  
 <span data-ttu-id="ffcb2-126">Os procedimentos armazenados gerenciados podem enviar conjuntos de resultados que não vêm de um `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="ffcb2-126">Managed stored procedures can send result sets that do not come from a `SqlDataReader`.</span></span> <span data-ttu-id="ffcb2-127">O método `SendResultsStart`, junto com `SendResultsRow` e `SendResultsEnd`, permite procedimentos armazenados para enviar conjuntos de resultados personalizados ao cliente.</span><span class="sxs-lookup"><span data-stu-id="ffcb2-127">The `SendResultsStart` method, along with `SendResultsRow` and `SendResultsEnd`, allows stored procedures to send custom result sets to the client.</span></span>  
  
 <span data-ttu-id="ffcb2-128">`SendResultsStart` usa um `SqlDataRecord` como uma entrada.</span><span class="sxs-lookup"><span data-stu-id="ffcb2-128">`SendResultsStart` takes a `SqlDataRecord` as an input.</span></span> <span data-ttu-id="ffcb2-129">Ele marca o começo de um conjunto de resultados e usa os metadados de registro para criar os metadados que descrevem o conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="ffcb2-129">It marks the beginning of a result set and uses the record metadata to construct the metadata that describes the result set.</span></span> <span data-ttu-id="ffcb2-130">Ele não envia o valor do registro com `SendResultsStart`.</span><span class="sxs-lookup"><span data-stu-id="ffcb2-130">It does not send the value of the record with `SendResultsStart`.</span></span> <span data-ttu-id="ffcb2-131">Todas as linhas subsequentes, enviadas com `SendResultsRow`, devem corresponder àquela definição de metadados.</span><span class="sxs-lookup"><span data-stu-id="ffcb2-131">All the subsequent rows, sent using `SendResultsRow`, must match that metadata definition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ffcb2-132">Depois de chamar o método `SendResultsStart` apenas `SendResultsRow` e `SendResultsEnd` podem ser chamados.</span><span class="sxs-lookup"><span data-stu-id="ffcb2-132">After calling the `SendResultsStart` method only `SendResultsRow` and `SendResultsEnd` can be called.</span></span> <span data-ttu-id="ffcb2-133">Chamar qualquer outro método na mesma instância de `SqlPipe` resulta em um `InvalidOperationException`.</span><span class="sxs-lookup"><span data-stu-id="ffcb2-133">Calling any other method in the same instance of `SqlPipe` causes an `InvalidOperationException`.</span></span> <span data-ttu-id="ffcb2-134">`SendResultsEnd` define `SqlPipe` de volta ao estado original no qual outros métodos podem ser chamados.</span><span class="sxs-lookup"><span data-stu-id="ffcb2-134">`SendResultsEnd` sets `SqlPipe` back to the initial state in which other methods can be called.</span></span>  
  
### <a name="example"></a><span data-ttu-id="ffcb2-135">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ffcb2-135">Example</span></span>  
 <span data-ttu-id="ffcb2-136">O procedimento armazenado `uspGetProductLine` retorna o nome, o número do produto, a cor e o preço de tabela de todos os produtos de uma linha de produtos específica.</span><span class="sxs-lookup"><span data-stu-id="ffcb2-136">The `uspGetProductLine` stored procedure returns the name, product number, color, and list price of all products within a specified product line.</span></span> <span data-ttu-id="ffcb2-137">Esse procedimento armazenado aceita correspondências exatas para *prodLine*.</span><span class="sxs-lookup"><span data-stu-id="ffcb2-137">This stored procedure accepts exact matches for *prodLine*.</span></span>  
  
 <span data-ttu-id="ffcb2-138">C#</span><span class="sxs-lookup"><span data-stu-id="ffcb2-138">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
  
public partial class StoredProcedures  
{  
[Microsoft.SqlServer.Server.SqlProcedure]  
public static void uspGetProductLine(SqlString prodLine)  
{  
    // Connect through the context connection.  
    using (SqlConnection connection = new SqlConnection("context connection=true"))  
    {  
        connection.Open();  
  
        SqlCommand command = new SqlCommand(  
            "SELECT Name, ProductNumber, Color, ListPrice " +  
            "FROM Production.Product " +   
            "WHERE ProductLine = @prodLine;", connection);  
  
        command.Parameters.AddWithValue("@prodLine", prodLine);  
  
        try  
        {  
            // Execute the command and send the results to the caller.  
            SqlContext.Pipe.ExecuteAndSend(command);  
        }  
        catch (System.Data.SqlClient.SqlException ex)  
        {  
            // An error occurred executing the SQL command.  
        }  
     }  
}  
};  
```  
  
 <span data-ttu-id="ffcb2-139">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ffcb2-139">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
  
Partial Public Class StoredProcedures  
<Microsoft.SqlServer.Server.SqlProcedure()> _  
Public Shared Sub uspGetProductLine(ByVal prodLine As SqlString)  
    Dim command As SqlCommand  
  
    ' Connect through the context connection.  
    Using connection As New SqlConnection("context connection=true")  
        connection.Open()  
  
        command = New SqlCommand( _  
        "SELECT Name, ProductNumber, Color, ListPrice " & _  
        "FROM Production.Product " & _  
        "WHERE ProductLine = @prodLine;", connection)  
        command.Parameters.AddWithValue("@prodLine", prodLine)  
  
        Try  
            ' Execute the command and send the results   
            ' directly to the caller.  
            SqlContext.Pipe.ExecuteAndSend(command)  
        Catch ex As System.Data.SqlClient.SqlException  
            ' An error occurred executing the SQL command.  
        End Try  
    End Using  
End Sub  
End Class  
```  
  
 <span data-ttu-id="ffcb2-140">A instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] a seguir executa o procedimento `uspGetProduct` que retorna uma lista de produtos de bicicleta.</span><span class="sxs-lookup"><span data-stu-id="ffcb2-140">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement executes the `uspGetProduct` procedure, which returns a list of touring bike products.</span></span>  
  
```  
EXEC uspGetProductLineVB 'T';  
```  
  
## <a name="see-also"></a><span data-ttu-id="ffcb2-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ffcb2-141">See Also</span></span>  
 <span data-ttu-id="ffcb2-142">[Objeto SqlDataRecord](sqldatarecord-object.md) </span><span class="sxs-lookup"><span data-stu-id="ffcb2-142">[SqlDataRecord Object](sqldatarecord-object.md) </span></span>  
 <span data-ttu-id="ffcb2-143">[Procedimentos armazenados CLR](../../database-engine/dev-guide/clr-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="ffcb2-143">[CLR Stored Procedures](../../database-engine/dev-guide/clr-stored-procedures.md) </span></span>  
 [<span data-ttu-id="ffcb2-144">Extensões específicas em processo do SQL Server para o ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ffcb2-144">SQL Server In-Process Specific Extensions to ADO.NET</span></span>](sql-server-in-process-specific-extensions-to-ado-net.md)  
  
  
