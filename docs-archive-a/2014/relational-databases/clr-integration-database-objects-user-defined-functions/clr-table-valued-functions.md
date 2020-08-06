---
title: Funções com valor de tabela do CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
- VB
- CSharp
helpviewer_keywords:
- Transact-SQL table-valued functions
- table-valued functions [CLR integration]
- TVFs [CLR integration]
ms.assetid: 9a6133ea-36e9-45bf-b572-1c0df3d6c194
author: rothja
ms.author: jroth
ms.openlocfilehash: b700aba5a753ecd8ee50ee9b7679cafb2f1f8581
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574737"
---
# <a name="clr-table-valued-functions"></a><span data-ttu-id="2d524-102">Funções com valor de tabela CLR</span><span class="sxs-lookup"><span data-stu-id="2d524-102">CLR Table-Valued Functions</span></span>
  <span data-ttu-id="2d524-103">Uma função com valor de tabela é uma função definida pelo usuário que retorna uma tabela.</span><span class="sxs-lookup"><span data-stu-id="2d524-103">A table-valued function is a user-defined function that returns a table.</span></span>  
  
 <span data-ttu-id="2d524-104">A partir do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estende a funcionalidade das funções com valor de tabela permitindo definir uma função com valor de tabela em qualquer idioma gerenciado.</span><span class="sxs-lookup"><span data-stu-id="2d524-104">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] extends the functionality of table-valued functions by allowing you to define a table-valued function in any managed language.</span></span> <span data-ttu-id="2d524-105">Os dados são retornados de uma função com valor de tabela por meio de um objeto `IEnumerable` ou `IEnumerator`.</span><span class="sxs-lookup"><span data-stu-id="2d524-105">Data is returned from a table-valued function through an `IEnumerable` or `IEnumerator` object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2d524-106">Para as funções com valor de tabela, as colunas do tipo de tabela de retorno não podem incluir colunas de carimbo de data e hora ou colunas de tipo de dados da cadeia de caracteres não Unicode (como `char`, `varchar` e `text`).</span><span class="sxs-lookup"><span data-stu-id="2d524-106">For table-valued functions, the columns of the return table type cannot include timestamp columns or non-Unicode string data type columns (such as `char`, `varchar`, and `text`).</span></span> <span data-ttu-id="2d524-107">Não tem suporte para a restrição NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="2d524-107">The NOT NULL constraint is not supported.</span></span>  
  
## <a name="differences-between-transact-sql-and-clr-table-valued-functions"></a><span data-ttu-id="2d524-108">Diferenças entre as funções com valor de tabela Transact-SQL e CLR</span><span class="sxs-lookup"><span data-stu-id="2d524-108">Differences Between Transact-SQL and CLR Table-Valued Functions</span></span>  
 <span data-ttu-id="2d524-109">As funções com valor de tabela do [!INCLUDE[tsql](../../includes/tsql-md.md)] materializam os resultados chamando a função em uma tabela intermediária.</span><span class="sxs-lookup"><span data-stu-id="2d524-109">[!INCLUDE[tsql](../../includes/tsql-md.md)] table-valued functions materialize the results of calling the function into an intermediate table.</span></span> <span data-ttu-id="2d524-110">Como elas usam uma tabela intermediária, podem dar suporte a restrições e índices exclusivos nos resultados.</span><span class="sxs-lookup"><span data-stu-id="2d524-110">Since they use an intermediate table, they can support constraints and unique indexes over the results.</span></span> <span data-ttu-id="2d524-111">Esses recursos podem ser extremamente úteis quando resultados grandes são retornados.</span><span class="sxs-lookup"><span data-stu-id="2d524-111">These features can be extremely useful when large results are returned.</span></span>  
  
 <span data-ttu-id="2d524-112">Em contrapartida, as funções com valor de tabela do CLR representam uma alternativa de streaming.</span><span class="sxs-lookup"><span data-stu-id="2d524-112">In contrast, CLR table-valued functions represent a streaming alternative.</span></span> <span data-ttu-id="2d524-113">Não há nenhum requisito de que todo o conjunto de resultados deva ser materializado em uma única tabela.</span><span class="sxs-lookup"><span data-stu-id="2d524-113">There is no requirement that the entire set of results be materialized in a single table.</span></span> <span data-ttu-id="2d524-114">O objeto `IEnumerable` retornado pela função gerenciada é diretamente chamado pelo plano de execução da consulta que chama a função com valor de tabela e os resultados são consumidos de uma maneira incremental.</span><span class="sxs-lookup"><span data-stu-id="2d524-114">The `IEnumerable` object returned by the managed function is directly called by the execution plan of the query that calls the table-valued function, and the results are consumed in an incremental manner.</span></span> <span data-ttu-id="2d524-115">Este modelo de streaming garante que os resultados possam ser consumidos imediatamente depois que a primeira linha estiver disponível, em vez de aguardar até que toda a tabela seja populada.</span><span class="sxs-lookup"><span data-stu-id="2d524-115">This streaming model ensures that results can be consumed immediately after the first row is available, instead of waiting for the entire table to be populated.</span></span> <span data-ttu-id="2d524-116">Ele também será a melhor alternativa, se você tiver uma grande quantidade de linhas retornadas, pois elas não precisam ser totalmente materializadas na memória.</span><span class="sxs-lookup"><span data-stu-id="2d524-116">It is also a better alternative if you have very large numbers of rows returned, because they do not have to be materialized in memory as a whole.</span></span> <span data-ttu-id="2d524-117">Por exemplo, uma função com valor de tabela gerenciada pode ser usada para analisar um arquivo de texto e retornar todas as linhas como uma linha.</span><span class="sxs-lookup"><span data-stu-id="2d524-117">For example, a managed table-valued function could be used to parse a text file and return each line as a row.</span></span>  
  
## <a name="implementing-table-valued-functions"></a><span data-ttu-id="2d524-118">Implementando funções com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="2d524-118">Implementing Table-Valued Functions</span></span>  
 <span data-ttu-id="2d524-119">Implemente as funções com valor de tabela como métodos em uma classe em um assembly do [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2d524-119">Implement table-valued functions as methods on a class in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework assembly.</span></span> <span data-ttu-id="2d524-120">O código da função com valor de tabela deve implementar a interface `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="2d524-120">Your table-valued function code must implement the `IEnumerable` interface.</span></span> <span data-ttu-id="2d524-121">A interface `IEnumerable` é definida no .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2d524-121">The `IEnumerable` interface is defined in the .NET Framework.</span></span> <span data-ttu-id="2d524-122">Os tipos que representam matrizes e coleções no .NET Framework já implementam a interface `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="2d524-122">Types representing arrays and collections in the .NET Framework already implement the `IEnumerable` interface.</span></span> <span data-ttu-id="2d524-123">Isso facilita a gravação de funções com valor de tabela que convertem uma coleção ou uma matriz em um conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="2d524-123">This makes it easy for writing table-valued functions that convert a collection or an array into a result set.</span></span>  
  
## <a name="table-valued-parameters"></a><span data-ttu-id="2d524-124">Parâmetros de valores de tabela</span><span class="sxs-lookup"><span data-stu-id="2d524-124">Table-Valued Parameters</span></span>  
 <span data-ttu-id="2d524-125">Os parâmetros com valor de tabela são tipos de tabela definidos pelo usuário, transmitidos em um procedimento ou função e fornecem uma maneira eficiente de passar várias linhas de dados para o servidor.</span><span class="sxs-lookup"><span data-stu-id="2d524-125">Table-valued parameters are user-defined table types that are passed into a procedure or function and provide an efficient way to pass multiple rows of data to the server.</span></span> <span data-ttu-id="2d524-126">Os parâmetros com valor de tabela fornecem funcionalidade semelhante para matrizes de parâmetros, mas oferecem maior flexibilidade e integração maior com o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d524-126">Table-valued parameters provide similar functionality to parameter arrays, but offer greater flexibility and closer integration with [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="2d524-127">Eles também fornecem o potencial para melhor desempenho.</span><span class="sxs-lookup"><span data-stu-id="2d524-127">They also provide the potential for better performance.</span></span> <span data-ttu-id="2d524-128">Os parâmetros com valor de tabela também ajudam a reduzir o número de viagens de ida e volta para o servidor.</span><span class="sxs-lookup"><span data-stu-id="2d524-128">Table-valued parameters also help reduce the number of round trips to the server.</span></span> <span data-ttu-id="2d524-129">Em vez de enviar várias solicitações ao servidor, como com uma lista de parâmetros escalares, os dados podem ser enviados ao servidor como um parâmetro com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="2d524-129">Instead of sending multiple requests to the server, such as with a list of scalar parameters, data can be sent to the server as a table-valued parameter.</span></span> <span data-ttu-id="2d524-130">Um tipo de tabela definido pelo usuário não pode ser passado como um parâmetro com valor de tabela para, ou ser retornado de, um procedimento armazenado ou uma função gerenciada(o) que é executada(o) no processo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2d524-130">A user-defined table type cannot be passed as a table-valued parameter to, or be returned from, a managed stored procedure or function executing in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process.</span></span> <span data-ttu-id="2d524-131">Para obter mais informações sobre parâmetros com valor de tabela, consulte [Usar parâmetros com valor de tabela &#40;Mecanismo de Banco de Dados&#41;](../tables/use-table-valued-parameters-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="2d524-131">For more information about table-valued parameters, see [Use Table-Valued Parameters &#40;Database Engine&#41;](../tables/use-table-valued-parameters-database-engine.md).</span></span>  
  
## <a name="output-parameters-and-table-valued-functions"></a><span data-ttu-id="2d524-132">Parâmetros de saída e funções com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="2d524-132">Output Parameters and Table-Valued Functions</span></span>  
 <span data-ttu-id="2d524-133">As informações podem ser retornadas de funções com valor de tabela que usam parâmetros de saída.</span><span class="sxs-lookup"><span data-stu-id="2d524-133">Information may be returned from table-valued functions using output parameters.</span></span> <span data-ttu-id="2d524-134">O parâmetro correspondente na função com valor de tabela do código de implementação deve usar um parâmetro de passagem por referência como o argumento.</span><span class="sxs-lookup"><span data-stu-id="2d524-134">The corresponding parameter in the implementation code table-valued function should use a pass-by-reference parameter as the argument.</span></span> <span data-ttu-id="2d524-135">Observe que o Visual Basic não suporta parâmetros de saída da mesma maneira que o Visual C#.</span><span class="sxs-lookup"><span data-stu-id="2d524-135">Note that Visual Basic does not support output parameters in the same way that Visual C# does.</span></span> <span data-ttu-id="2d524-136">Você deve especificar o parâmetro por referência e aplicar o \<Out()> atributo para representar um parâmetro de saída, como no seguinte:</span><span class="sxs-lookup"><span data-stu-id="2d524-136">You must specify the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
...  
Public Shared Sub FillRow ( <Out()> ByRef value As SqlInt32)  
```  
  
### <a name="defining-a-table-valued-function-in-transact-sql"></a><span data-ttu-id="2d524-137">Definindo uma função com valor de tabela no Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2d524-137">Defining a Table-Valued Function in Transact-SQL</span></span>  
 <span data-ttu-id="2d524-138">A sintaxe para definir uma função com valor de tabela de CLR é semelhante a de uma função com valor de tabela do [!INCLUDE[tsql](../../includes/tsql-md.md)], com a adição da cláusula `EXTERNAL NAME`.</span><span class="sxs-lookup"><span data-stu-id="2d524-138">The syntax for defining a CLR table-valued function is similar to that of a [!INCLUDE[tsql](../../includes/tsql-md.md)] table-valued function, with the addition of the `EXTERNAL NAME` clause.</span></span> <span data-ttu-id="2d524-139">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2d524-139">For example:</span></span>  
  
```  
CREATE FUNCTION GetEmpFirstLastNames()  
RETURNS TABLE (FirstName NVARCHAR(4000), LastName NVARCHAR(4000))  
EXTERNAL NAME MyDotNETAssembly.[MyNamespace.MyClassname]. GetEmpFirstLastNames;  
```  
  
 <span data-ttu-id="2d524-140">As funções com valor de tabela são usadas para representar dados em formato relacional para processamento posterior em consultas como:</span><span class="sxs-lookup"><span data-stu-id="2d524-140">Table-valued functions are used to represent data in relational form for further processing in queries such as:</span></span>  
  
```  
select * from function();  
select * from tbl join function() f on tbl.col = f.col;  
select * from table t cross apply function(t.column);  
```  
  
 <span data-ttu-id="2d524-141">As funções com valor de tabela podem retornar uma tabela quando:</span><span class="sxs-lookup"><span data-stu-id="2d524-141">Table-valued functions can return a table when:</span></span>  
  
-   <span data-ttu-id="2d524-142">Criadas a partir de argumentos de entrada escalar.</span><span class="sxs-lookup"><span data-stu-id="2d524-142">Created from scalar input arguments.</span></span> <span data-ttu-id="2d524-143">Por exemplo, uma função com valor de tabela que usa uma cadeia de caracteres de números delimitada por vírgulas e converte-os em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="2d524-143">For example, a table-valued function that takes a comma-delimited string of numbers and pivots them into a table.</span></span>  
  
-   <span data-ttu-id="2d524-144">Geradas de dados externos.</span><span class="sxs-lookup"><span data-stu-id="2d524-144">Generated from external data.</span></span> <span data-ttu-id="2d524-145">Por exemplo, uma função com valor de tabela que lê o log de eventos e o expõe como uma tabela.</span><span class="sxs-lookup"><span data-stu-id="2d524-145">For example, a table-valued function that reads the event log and exposes it as a table.</span></span>  
  
 <span data-ttu-id="2d524-146">**Observação** Uma função com valor de tabela só pode executar o acesso a dados por meio de uma [!INCLUDE[tsql](../../includes/tsql-md.md)] consulta no `InitMethod` método e não no `FillRow` método.</span><span class="sxs-lookup"><span data-stu-id="2d524-146">**Note** A table-valued function can only perform data access through a [!INCLUDE[tsql](../../includes/tsql-md.md)] query in the `InitMethod` method, and not in the `FillRow` method.</span></span> <span data-ttu-id="2d524-147">O método `InitMethod` deverá ser marcado com a propriedade do atributo `SqlFunction.DataAccess.Read` se uma consulta [!INCLUDE[tsql](../../includes/tsql-md.md)] for executada.</span><span class="sxs-lookup"><span data-stu-id="2d524-147">The `InitMethod` should be marked with the `SqlFunction.DataAccess.Read` attribute property if a [!INCLUDE[tsql](../../includes/tsql-md.md)] query is performed.</span></span>  
  
## <a name="a-sample-table-valued-function"></a><span data-ttu-id="2d524-148">Um exemplo de função com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="2d524-148">A Sample Table-Valued Function</span></span>  
 <span data-ttu-id="2d524-149">A função com valor de tabela a seguir retorna informações do log de eventos do sistema.</span><span class="sxs-lookup"><span data-stu-id="2d524-149">The following table-valued function returns information from the system event log.</span></span> <span data-ttu-id="2d524-150">A função adota um único argumento de cadeia de caracteres que contém o nome do log de eventos a ser lido.</span><span class="sxs-lookup"><span data-stu-id="2d524-150">The function takes a single string argument containing the name of the event log to read.</span></span>  
  
###### <a name="sample-code"></a><span data-ttu-id="2d524-151">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="2d524-151">Sample Code</span></span>  
  
```csharp  
using System;  
using System.Data.Sql;  
using Microsoft.SqlServer.Server;  
using System.Collections;  
using System.Data.SqlTypes;  
using System.Diagnostics;  
  
public class TabularEventLog  
{  
    [SqlFunction(FillRowMethodName = "FillRow")]  
    public static IEnumerable InitMethod(String logname)  
    {  
        return new EventLog(logname).Entries;    }  
  
    public static void FillRow(Object obj, out SqlDateTime timeWritten, out SqlChars message, out SqlChars category, out long instanceId)  
    {  
        EventLogEntry eventLogEntry = (EventLogEntry)obj;  
        timeWritten = new SqlDateTime(eventLogEntry.TimeWritten);  
        message = new SqlChars(eventLogEntry.Message);  
        category = new SqlChars(eventLogEntry.Category);  
        instanceId = eventLogEntry.InstanceId;  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.Data.Sql  
Imports Microsoft.SqlServer.Server  
Imports System.Collections  
Imports System.Data.SqlTypes  
Imports System.Diagnostics  
Imports System.Runtime.InteropServices  
  
Public Class TabularEventLog  
    <SqlFunction(FillRowMethodName:="FillRow")> _  
    Public Shared Function InitMethod(ByVal logname As String) As IEnumerable  
        Return New EventLog(logname).Entries  
    End Function  
  
    Public Shared Sub FillRow(ByVal obj As Object, <Out()> ByRef timeWritten As SqlDateTime, <Out()> ByRef message As SqlChars, <Out()> ByRef category As SqlChars, <Out()> ByRef instanceId As Long)  
        Dim eventLogEnTry As EventLogEntry = CType(obj, EventLogEntry)  
        timeWritten = New SqlDateTime(eventLogEnTry.TimeWritten)  
        message = New SqlChars(eventLogEnTry.Message)  
        category = New SqlChars(eventLogEnTry.Category)  
        instanceId = eventLogEnTry.InstanceId  
    End Sub  
End Class  
```  
  
###### <a name="declaring-and-using-the-sample-table-valued-function"></a><span data-ttu-id="2d524-152">Declarando e usando a função com valor de tabela de exemplo</span><span class="sxs-lookup"><span data-stu-id="2d524-152">Declaring and Using the Sample Table-Valued Function</span></span>  
 <span data-ttu-id="2d524-153">Depois que a função com valor de tabela de exemplo foi compilada, ela pode ser declarada no [!INCLUDE[tsql](../../includes/tsql-md.md)] da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="2d524-153">After the sample table-valued function has been compiled, it can be declared in [!INCLUDE[tsql](../../includes/tsql-md.md)] like this:</span></span>  
  
```  
use master;  
-- Replace SQL_Server_logon with your SQL Server user credentials.  
GRANT EXTERNAL ACCESS ASSEMBLY TO [SQL_Server_logon];   
-- Modify the following line to specify a different database.  
ALTER DATABASE master SET TRUSTWORTHY ON;  
  
-- Modify the next line to use the appropriate database.  
CREATE ASSEMBLY tvfEventLog   
FROM 'D:\assemblies\tvfEventLog\tvfeventlog.dll'   
WITH PERMISSION_SET = EXTERNAL_ACCESS;  
GO  
CREATE FUNCTION ReadEventLog(@logname nvarchar(100))  
RETURNS TABLE   
(logTime datetime,Message nvarchar(4000),Category nvarchar(4000),InstanceId bigint)  
AS   
EXTERNAL NAME tvfEventLog.TabularEventLog.InitMethod;  
GO  
```  
  
 <span data-ttu-id="2d524-154">Não há suporte para objetos de banco de dados do Visual C++ compilados com /clr:pure para a execução no [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d524-154">Visual C++ database objects compiled with /clr:pure are not supported for execution on [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="2d524-155">Por exemplo, esses objetos de banco de dados incluem funções com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="2d524-155">For example, such database objects include table-valued functions.</span></span>  
  
 <span data-ttu-id="2d524-156">Para testar o exemplo, tente o seguinte código [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="2d524-156">To test the sample, try the following [!INCLUDE[tsql](../../includes/tsql-md.md)] code:</span></span>  
  
```  
-- Select the top 100 events,  
SELECT TOP 100 *  
FROM dbo.ReadEventLog(N'Security') as T;  
go  
  
-- Select the last 10 login events.  
SELECT TOP 10 T.logTime, T.Message, T.InstanceId   
FROM dbo.ReadEventLog(N'Security') as T  
WHERE T.Category = N'Logon/Logoff';  
go  
```  
  
## <a name="sample-returning-the-results-of-a-sql-server-query"></a><span data-ttu-id="2d524-157">Exemplo: Retornando os resultados de uma consulta do SQL Server</span><span class="sxs-lookup"><span data-stu-id="2d524-157">Sample: Returning the Results of a SQL Server Query</span></span>  
 <span data-ttu-id="2d524-158">O exemplo a seguir mostra uma função com valor de tabela que consulta um banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d524-158">The following sample shows a table-valued function that queries a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="2d524-159">Este exemplo usa o banco de dados AdventureWorks Light do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d524-159">This sample uses the AdventureWorks Light database from [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span> <span data-ttu-id="2d524-160">Consulte [https://www.codeplex.com/sqlserversamples](https://go.microsoft.com/fwlink/?LinkId=87843) para obter mais informações sobre como baixar o AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="2d524-160">See [https://www.codeplex.com/sqlserversamples](https://go.microsoft.com/fwlink/?LinkId=87843) for more information on downloading AdventureWorks.</span></span>  
  
 <span data-ttu-id="2d524-161">Nomeie seu arquivo de código-fonte como FindInvalidEmails.cs ou FindInvalidEmails.vb.</span><span class="sxs-lookup"><span data-stu-id="2d524-161">Name your source code file FindInvalidEmails.cs or FindInvalidEmails.vb.</span></span>  
  
```csharp  
using System;  
using System.Collections;  
using System.Data;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
  
using Microsoft.SqlServer.Server;  
  
public partial class UserDefinedFunctions {  
   private class EmailResult {  
      public SqlInt32 CustomerId;  
      public SqlString EmailAdress;  
  
      public EmailResult(SqlInt32 customerId, SqlString emailAdress) {  
         CustomerId = customerId;  
         EmailAdress = emailAdress;  
      }  
   }  
  
   public static bool ValidateEmail(SqlString emailAddress) {  
      if (emailAddress.IsNull)  
         return false;  
  
      if (!emailAddress.Value.EndsWith("@adventure-works.com"))  
         return false;  
  
      // Validate the address. Put any more rules here.  
      return true;  
   }  
  
   [SqlFunction(  
       DataAccess = DataAccessKind.Read,  
       FillRowMethodName = "FindInvalidEmails_FillRow",  
       TableDefinition="CustomerId int, EmailAddress nvarchar(4000)")]  
   public static IEnumerable FindInvalidEmails(SqlDateTime modifiedSince) {  
      ArrayList resultCollection = new ArrayList();  
  
      using (SqlConnection connection = new SqlConnection("context connection=true")) {  
         connection.Open();  
  
         using (SqlCommand selectEmails = new SqlCommand(  
             "SELECT " +  
             "[CustomerID], [EmailAddress] " +  
             "FROM [AdventureWorksLT2008].[SalesLT].[Customer] " +  
             "WHERE [ModifiedDate] >= @modifiedSince",  
             connection)) {  
            SqlParameter modifiedSinceParam = selectEmails.Parameters.Add(  
                "@modifiedSince",  
                SqlDbType.DateTime);  
            modifiedSinceParam.Value = modifiedSince;  
  
            using (SqlDataReader emailsReader = selectEmails.ExecuteReader()) {  
               while (emailsReader.Read()) {  
                  SqlString emailAddress = emailsReader.GetSqlString(1);  
                  if (ValidateEmail(emailAddress)) {  
                     resultCollection.Add(new EmailResult(  
                         emailsReader.GetSqlInt32(0),  
                         emailAddress));  
                  }  
               }  
            }  
         }  
      }  
  
      return resultCollection;  
   }  
  
   public static void FindInvalidEmails_FillRow(  
       object emailResultObj,  
       out SqlInt32 customerId,  
       out SqlString emailAdress) {  
      EmailResult emailResult = (EmailResult)emailResultObj;  
  
      customerId = emailResult.CustomerId;  
      emailAdress = emailResult.EmailAdress;  
   }  
};  
```  
  
```vb  
Imports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
  
Public Partial Class UserDefinedFunctions  
   Private Class EmailResult  
      Public CustomerId As SqlInt32  
      Public EmailAdress As SqlString  
  
      Public Sub New(customerId__1 As SqlInt32, emailAdress__2 As SqlString)  
         CustomerId = customerId__1  
         EmailAdress = emailAdress__2  
      End Sub  
   End Class  
  
   Public Shared Function ValidateEmail(emailAddress As SqlString) As Boolean  
      If emailAddress.IsNull Then  
         Return False  
      End If  
  
      If Not emailAddress.Value.EndsWith("@adventure-works.com") Then  
         Return False  
      End If  
  
      ' Validate the address. Put any more rules here.  
      Return True  
   End Function  
  
   <SqlFunction(DataAccess := DataAccessKind.Read, FillRowMethodName := "FindInvalidEmails_FillRow", TableDefinition := "CustomerId int, EmailAddress nvarchar(4000)")> _  
   Public Shared Function FindInvalidEmails(modifiedSince As SqlDateTime) As IEnumerable  
      Dim resultCollection As New ArrayList()  
  
      Using connection As New SqlConnection("context connection=true")  
         connection.Open()  
  
         Using selectEmails As New SqlCommand("SELECT " & "[CustomerID], [EmailAddress] " & "FROM [AdventureWorksLT2008].[SalesLT].[Customer] " & "WHERE [ModifiedDate] >= @modifiedSince", connection)  
            Dim modifiedSinceParam As SqlParameter = selectEmails.Parameters.Add("@modifiedSince", SqlDbType.DateTime)  
            modifiedSinceParam.Value = modifiedSince  
  
            Using emailsReader As SqlDataReader = selectEmails.ExecuteReader()  
               While emailsReader.Read()  
                  Dim emailAddress As SqlString = emailsReader.GetSqlString(1)  
                  If ValidateEmail(emailAddress) Then  
                     resultCollection.Add(New EmailResult(emailsReader.GetSqlInt32(0), emailAddress))  
                  End If  
               End While  
            End Using  
         End Using  
      End Using  
  
      Return resultCollection  
   End Function  
  
   Public Shared Sub FindInvalidEmails_FillRow(emailResultObj As Object, ByRef customerId As SqlInt32, ByRef emailAdress As SqlString)  
      Dim emailResult As EmailResult = DirectCast(emailResultObj, EmailResult)  
  
      customerId = emailResult.CustomerId  
      emailAdress = emailResult.EmailAdress  
   End Sub  
End ClassImports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
  
Public Partial Class UserDefinedFunctions  
   Private Class EmailResult  
      Public CustomerId As SqlInt32  
      Public EmailAdress As SqlString  
  
      Public Sub New(customerId__1 As SqlInt32, emailAdress__2 As SqlString)  
         CustomerId = customerId__1  
         EmailAdress = emailAdress__2  
      End Sub  
   End Class  
  
   Public Shared Function ValidateEmail(emailAddress As SqlString) As Boolean  
      If emailAddress.IsNull Then  
         Return False  
      End If  
  
      If Not emailAddress.Value.EndsWith("@adventure-works.com") Then  
         Return False  
      End If  
  
      ' Validate the address. Put any more rules here.  
      Return True  
   End Function  
  
   <SqlFunction(DataAccess := DataAccessKind.Read, FillRowMethodName := "FindInvalidEmails_FillRow", TableDefinition := "CustomerId int, EmailAddress nvarchar(4000)")> _  
   Public Shared Function FindInvalidEmails(modifiedSince As SqlDateTime) As IEnumerable  
      Dim resultCollection As New ArrayList()  
  
      Using connection As New SqlConnection("context connection=true")  
         connection.Open()  
  
         Using selectEmails As New SqlCommand("SELECT " & "[CustomerID], [EmailAddress] " & "FROM [AdventureWorksLT2008].[SalesLT].[Customer] " & "WHERE [ModifiedDate] >= @modifiedSince", connection)  
            Dim modifiedSinceParam As SqlParameter = selectEmails.Parameters.Add("@modifiedSince", SqlDbType.DateTime)  
            modifiedSinceParam.Value = modifiedSince  
  
            Using emailsReader As SqlDataReader = selectEmails.ExecuteReader()  
               While emailsReader.Read()  
                  Dim emailAddress As SqlString = emailsReader.GetSqlString(1)  
                  If ValidateEmail(emailAddress) Then  
                     resultCollection.Add(New EmailResult(emailsReader.GetSqlInt32(0), emailAddress))  
                  End If  
               End While  
            End Using  
         End Using  
      End Using  
  
      Return resultCollection  
   End Function  
  
   Public Shared Sub FindInvalidEmails_FillRow(emailResultObj As Object, customerId As SqlInt32, emailAdress As SqlString)  
      Dim emailResult As EmailResult = DirectCast(emailResultObj, EmailResult)  
  
      customerId = emailResult.CustomerId  
      emailAdress = emailResult.EmailAdress  
   End Sub  
End Class  
```  
  
 <span data-ttu-id="2d524-162">Compile o código-fonte em uma DLL e copie a DLL no diretório raiz de sua unidade C.</span><span class="sxs-lookup"><span data-stu-id="2d524-162">Compile the source code to a DLL and copy the DLL to the root directory of your C drive.</span></span>  <span data-ttu-id="2d524-163">Em seguida, execute a seguinte consulta [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d524-163">Then, execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] query.</span></span>  
  
```  
use AdventureWorksLT2008;  
go  
  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'FindInvalidEmails')  
   DROP FUNCTION FindInvalidEmails;  
go  
  
IF EXISTS (SELECT name FROM sys.assemblies WHERE name = 'MyClrCode')  
   DROP ASSEMBLY MyClrCode;  
go  
  
CREATE ASSEMBLY MyClrCode FROM 'C:\FindInvalidEmails.dll'  
WITH PERMISSION_SET = SAFE -- EXTERNAL_ACCESS;  
GO  
  
CREATE FUNCTION FindInvalidEmails(@ModifiedSince datetime)   
RETURNS TABLE (  
   CustomerId int,  
   EmailAddress nvarchar(4000)  
)  
AS EXTERNAL NAME MyClrCode.UserDefinedFunctions.[FindInvalidEmails];  
go  
  
SELECT * FROM FindInvalidEmails('2000-01-01');  
go  
```  
  
