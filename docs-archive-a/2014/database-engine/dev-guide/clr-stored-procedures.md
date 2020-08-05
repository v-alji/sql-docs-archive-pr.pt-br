---
title: Procedimentos armazenados CLR | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- database objects [CLR integration], stored procedures
- stored procedures [CLR integration]
- common language runtime [SQL Server], stored procedures
- building database objects [CLR integration], stored procedures
- output parameters [CLR integration]
- tabular results
ms.assetid: bbdd51b2-a9b4-4916-ba6f-7957ac6c3f33
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f8c69435e28bfa67c72e26b7a54e419cd91ef220
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571546"
---
# <a name="clr-stored-procedures"></a><span data-ttu-id="cf461-102">Procedimentos armazenados CLR</span><span class="sxs-lookup"><span data-stu-id="cf461-102">CLR Stored Procedures</span></span>
  <span data-ttu-id="cf461-103">Os procedimentos armazenados são rotinas que não podem ser usadas em expressões escalares.</span><span class="sxs-lookup"><span data-stu-id="cf461-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="cf461-104">Diferentemente das funções escalares, eles podem retornar resultados tabulares e mensagens para o cliente, invocar instruções DDL (linguagem de definição de dados) e DML (linguagem de manipulação de dados) e retornar parâmetros de saída.</span><span class="sxs-lookup"><span data-stu-id="cf461-104">Unlike scalar functions, they can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span> <span data-ttu-id="cf461-105">Para obter informações sobre as vantagens da integração CLR e como escolher entre código gerenciado e [!INCLUDE[tsql](../../includes/tsql-md.md)] , consulte [visão geral da integração do CLR](../../relational-databases/clr-integration/clr-integration-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cf461-105">For information about the advantages of CLR integration and choosing between managed code and [!INCLUDE[tsql](../../includes/tsql-md.md)], see [Overview of CLR Integration](../../relational-databases/clr-integration/clr-integration-overview.md).</span></span>  
  
## <a name="requirements-for-clr-stored-procedures"></a><span data-ttu-id="cf461-106">Requisitos dos procedimentos armazenados CLR</span><span class="sxs-lookup"><span data-stu-id="cf461-106">Requirements for CLR Stored Procedures</span></span>  
 <span data-ttu-id="cf461-107">No Common Language Runtime (CLR), os procedimentos armazenados são implementados como métodos estáticos públicos em uma classe em um [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] assembly.</span><span class="sxs-lookup"><span data-stu-id="cf461-107">In the common language runtime (CLR), stored procedures are implemented as public static methods on a class in a [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] assembly.</span></span> <span data-ttu-id="cf461-108">O método estático pode ser declarado como nulo ou retornar um valor inteiro.</span><span class="sxs-lookup"><span data-stu-id="cf461-108">The static method can either be declared as void, or return an integer value.</span></span> <span data-ttu-id="cf461-109">Se retornar um valor inteiro, o inteiro retornado será tratado como o código de retorno do procedimento.</span><span class="sxs-lookup"><span data-stu-id="cf461-109">If it returns an integer value, the integer returned is treated as the return code from the procedure.</span></span> <span data-ttu-id="cf461-110">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="cf461-110">For example:</span></span>  
  
 `EXECUTE @return_status = procedure_name`  
  
 <span data-ttu-id="cf461-111">A @return_status variável conterá o valor retornado pelo método.</span><span class="sxs-lookup"><span data-stu-id="cf461-111">The @return_status variable will contain the value returned by the method.</span></span> <span data-ttu-id="cf461-112">Se o método for declarado nulo, o código de retorno será 0.</span><span class="sxs-lookup"><span data-stu-id="cf461-112">If the method is declared void, the return code is 0.</span></span>  
  
 <span data-ttu-id="cf461-113">Se o método assumir parâmetros, o número de parâmetros na implementação [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] deverá ser o mesmo daqueles usados na declaração [!INCLUDE[tsql](../../includes/tsql-md.md)] do procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="cf461-113">If the method takes parameters, the number of parameters in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] implementation should be the same as the number of parameters used in the [!INCLUDE[tsql](../../includes/tsql-md.md)] declaration of the stored procedure.</span></span>  
  
 <span data-ttu-id="cf461-114">Os parâmetros passados para um procedimento armazenado CLR podem ser de qualquer um dos tipos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nativos que tenham um equivalente em código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="cf461-114">Parameters passed to a CLR stored procedure can be any of the native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types that have an equivalent in managed code.</span></span> <span data-ttu-id="cf461-115">Para que a sintaxe [!INCLUDE[tsql](../../includes/tsql-md.md)] crie o procedimento, esses tipos devem ser especificados com o equivalente do tipo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nativo mais apropriado.</span><span class="sxs-lookup"><span data-stu-id="cf461-115">For the [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax to create the procedure, these types should be specified with the most appropriate native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type equivalent.</span></span> <span data-ttu-id="cf461-116">Para obter mais informações sobre conversões de tipo, consulte [mapeando dados de parâmetro CLR](../../relational-databases/clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span><span class="sxs-lookup"><span data-stu-id="cf461-116">For more information about type conversions, see [Mapping CLR Parameter Data](../../relational-databases/clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span></span>  
  
### <a name="table-valued-parameters"></a><span data-ttu-id="cf461-117">Parâmetros de valores de tabela</span><span class="sxs-lookup"><span data-stu-id="cf461-117">Table-Valued Parameters</span></span>  
 <span data-ttu-id="cf461-118">Os TVPs (parâmetros com valor de tabela), ou seja, tipos de tabela definidos pelo usuário transmitidos para um procedimento ou uma função, oferecem uma maneira eficiente de passar várias linhas de dados para o servidor.</span><span class="sxs-lookup"><span data-stu-id="cf461-118">Table-valued parameters (TVPs), user-defined table types that are passed into a procedure or function, provide an efficient way to pass multiple rows of data to the server.</span></span> <span data-ttu-id="cf461-119">Os TVPs proporcionam funcionalidade semelhante para matrizes de parâmetro, porém com maior flexibilidade e integração com [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf461-119">TVPs provide similar functionality to parameter arrays, but offer greater flexibility and closer integration with [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="cf461-120">Eles também fornecem o potencial para melhor desempenho.</span><span class="sxs-lookup"><span data-stu-id="cf461-120">They also provide the potential for better performance.</span></span> <span data-ttu-id="cf461-121">Os TVPs também ajudam a reduzir o número de viagens de ida e volta para o servidor.</span><span class="sxs-lookup"><span data-stu-id="cf461-121">TVPs also help reduce the number of round trips to the server.</span></span> <span data-ttu-id="cf461-122">Em vez de enviar várias solicitações ao servidor, como com uma lista de parâmetros escalares, os dados podem ser enviados ao servidor como um TVP.</span><span class="sxs-lookup"><span data-stu-id="cf461-122">Instead of sending multiple requests to the server, such as with a list of scalar parameters, data can be sent to the server as a TVP.</span></span> <span data-ttu-id="cf461-123">Um tipo de tabela definido pelo usuário não pode ser passado como um parâmetro com valor de tabela para, ou ser retornado de, um procedimento armazenado ou uma função gerenciada(o) que é executada(o) no processo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cf461-123">A user-defined table type cannot be passed as a table-valued parameter to, or be returned from, a managed stored procedure or function executing in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process.</span></span> <span data-ttu-id="cf461-124">Para obter mais informações sobre TVPs, consulte [usar parâmetros com valor de tabela &#40;Mecanismo de Banco de Dados&#41;](../../relational-databases/tables/use-table-valued-parameters-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="cf461-124">For more information about TVPs, see [Use Table-Valued Parameters &#40;Database Engine&#41;](../../relational-databases/tables/use-table-valued-parameters-database-engine.md).</span></span>  
  
## <a name="returning-results-from-clr-stored-procedures"></a><span data-ttu-id="cf461-125">Retornando resultados de procedimentos armazenados CLR</span><span class="sxs-lookup"><span data-stu-id="cf461-125">Returning Results from CLR Stored Procedures</span></span>  
 <span data-ttu-id="cf461-126">As informações podem ser retornadas dos procedimentos armazenados do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] de várias maneiras.</span><span class="sxs-lookup"><span data-stu-id="cf461-126">Information may be returned from [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] stored procedures in several ways.</span></span> <span data-ttu-id="cf461-127">Isso inclui parâmetros de saída, resultados tabulares e mensagens.</span><span class="sxs-lookup"><span data-stu-id="cf461-127">This includes output parameters, tabular results, and messages.</span></span>  
  
### <a name="output-parameters-and-clr-stored-procedures"></a><span data-ttu-id="cf461-128">Parâmetros OUTPUT e procedimentos armazenados CLR</span><span class="sxs-lookup"><span data-stu-id="cf461-128">OUTPUT Parameters and CLR Stored Procedures</span></span>  
 <span data-ttu-id="cf461-129">Assim como nos procedimentos armazenados [!INCLUDE[tsql](../../includes/tsql-md.md)], as informações podem ser retornadas dos procedimentos armazenados do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] que usam parâmetros OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="cf461-129">As with [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures, information may be returned from [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] stored procedures using OUTPUT parameters.</span></span> <span data-ttu-id="cf461-130">A sintaxe de DML [!INCLUDE[tsql](../../includes/tsql-md.md)] usada para criar procedimentos armazenados do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] é a mesma usada para criar procedimentos armazenados escritos em [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf461-130">The [!INCLUDE[tsql](../../includes/tsql-md.md)] DML syntax used for creating [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] stored procedures is the same as that used for creating stored procedures written in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="cf461-131">O parâmetro correspondente no código de implementação da classe do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] deve usar um parâmetro de passagem-por-referência como argumento.</span><span class="sxs-lookup"><span data-stu-id="cf461-131">The corresponding parameter in the implementation code in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] class should use a pass-by-reference parameter as the argument.</span></span> <span data-ttu-id="cf461-132">Observe que Visual Basic não oferece suporte a parâmetros de saída da mesma maneira que o C#.</span><span class="sxs-lookup"><span data-stu-id="cf461-132">Note that Visual Basic does not support output parameters in the same way that C# does.</span></span> <span data-ttu-id="cf461-133">Você deve especificar o parâmetro por referência e aplicar o \<Out()> atributo para representar um parâmetro de saída, como no seguinte:</span><span class="sxs-lookup"><span data-stu-id="cf461-133">You must specify the parameter by reference and apply the \<Out()> attribute to represent an OUTPUT parameter, as in the following:</span></span>  
  
```vb
Imports System.Runtime.InteropServices  
...  
Public Shared Sub PriceSum ( <Out()> ByRef value As SqlInt32)  
```  
  
 <span data-ttu-id="cf461-134">A seguir está um procedimento armazenado que retorna informações por um parâmetro OUTPUT:</span><span class="sxs-lookup"><span data-stu-id="cf461-134">The following shows a stored procedure returning information through an OUTPUT parameter:</span></span>  
  
```csharp  
using System;  
using System.Data.SqlTypes;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void PriceSum(out SqlInt32 value)  
   {  
      using(SqlConnection connection = new SqlConnection("context connection=true"))   
      {  
         value = 0;  
         connection.Open();  
         SqlCommand command = new SqlCommand("SELECT Price FROM Products", connection);  
         SqlDataReader reader = command.ExecuteReader();  
  
         using (reader)  
         {  
            while( reader.Read() )  
            {  
               value += reader.GetSqlInt32(0);  
            }  
         }           
      }  
   }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
Imports System.Runtime.InteropServices  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Executes a query and iterates over the results to perform a summation.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub PriceSum( <Out()> ByRef value As SqlInt32)  
  
        Using connection As New SqlConnection("context connection=true")  
           value = 0  
           Connection.Open()  
           Dim command As New SqlCommand("SELECT Price FROM Products", connection)  
           Dim reader As SqlDataReader  
           reader = command.ExecuteReader()  
  
           Using reader  
              While reader.Read()  
                 value += reader.GetSqlInt32(0)  
              End While  
           End Using  
        End Using          
    End Sub  
End Class  
```  
  
 <span data-ttu-id="cf461-135">Depois que o assembly que contém o procedimento armazenado CLR acima tiver sido criado e criado no servidor, o seguinte [!INCLUDE[tsql](../../includes/tsql-md.md)] será usado para criar o procedimento no banco de dados e especifica *sum* como um parâmetro de saída.</span><span class="sxs-lookup"><span data-stu-id="cf461-135">Once the assembly containing the above CLR stored procedure has been built and created on the server, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] is used to create the procedure in the database, and specifies *sum* as an OUTPUT parameter.</span></span>  
  
```sql
CREATE PROCEDURE PriceSum (@sum int OUTPUT)  
AS EXTERNAL NAME TestStoredProc.StoredProcedures.PriceSum  
-- if StoredProcedures class was inside a namespace, called MyNS,  
-- you would use:  
-- AS EXTERNAL NAME TestStoredProc.[MyNS.StoredProcedures].PriceSum  
```  
  
 <span data-ttu-id="cf461-136">Observe que *sum* é declarado como um `int` tipo de dados SQL Server e que o parâmetro *Value* definido no procedimento CLR armazenado é especificado como um `SqlInt32` tipo de dados CLR.</span><span class="sxs-lookup"><span data-stu-id="cf461-136">Note that *sum* is declared as an `int` SQL Server data type, and that the *value* parameter defined in the CLR stored procedure is specified as a `SqlInt32` CLR data type.</span></span> <span data-ttu-id="cf461-137">Quando um programa de chamada executa o procedimento CLR armazenado, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o converte automaticamente o `SqlInt32` tipo de dados CLR em um `int` [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="cf461-137">When a calling program executes the CLR stored procedure, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] automatically converts the `SqlInt32` CLR data type to an `int`[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type.</span></span>  <span data-ttu-id="cf461-138">Para obter mais informações sobre quais tipos de dados CLR podem e não podem ser convertidos, consulte [mapeando dados de parâmetro CLR](../../relational-databases/clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span><span class="sxs-lookup"><span data-stu-id="cf461-138">For more information about which CLR data types can and cannot be converted, see [Mapping CLR Parameter Data](../../relational-databases/clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span></span>  
  
### <a name="returning-tabular-results-and-messages"></a><span data-ttu-id="cf461-139">Retornando resultados tabulares e mensagens</span><span class="sxs-lookup"><span data-stu-id="cf461-139">Returning Tabular Results and Messages</span></span>  
 <span data-ttu-id="cf461-140">O retorno dos resultados tabulares e mensagens para o cliente é executado através do objeto `SqlPipe`, que é obtido usando a propriedade `Pipe` da classe `SqlContext`.</span><span class="sxs-lookup"><span data-stu-id="cf461-140">Returning tabular results and messages to the client is done through the `SqlPipe` object, which is obtained by using the `Pipe` property of the `SqlContext` class.</span></span> <span data-ttu-id="cf461-141">O objeto `SqlPipe` tem um método `Send`.</span><span class="sxs-lookup"><span data-stu-id="cf461-141">The `SqlPipe` object has a `Send` method.</span></span> <span data-ttu-id="cf461-142">Chamando o método `Send`, você pode transmitir dados pelo pipe para o aplicativo de chamada.</span><span class="sxs-lookup"><span data-stu-id="cf461-142">By calling the `Send` method, you can transmit data through the pipe to the calling application.</span></span>  
  
 <span data-ttu-id="cf461-143">Há várias sobrecargas do método `SqlPipe.Send`, incluindo uma que envia um `SqlDataReader` e outra que simplesmente envia uma cadeia de caracteres de texto.</span><span class="sxs-lookup"><span data-stu-id="cf461-143">These are several overloads of the `SqlPipe.Send` method, including one that sends a `SqlDataReader` and another that simply sends a text string.</span></span>  
  
###### <a name="returning-messages"></a><span data-ttu-id="cf461-144">Retornando mensagens</span><span class="sxs-lookup"><span data-stu-id="cf461-144">Returning Messages</span></span>  
 <span data-ttu-id="cf461-145">Use `SqlPipe.Send(string)` para enviar mensagens para o aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="cf461-145">Use `SqlPipe.Send(string)` to send messages to the client application.</span></span> <span data-ttu-id="cf461-146">O texto da mensagem é limitado a 8000 caracteres.</span><span class="sxs-lookup"><span data-stu-id="cf461-146">The text of the message is limited to 8000 characters.</span></span> <span data-ttu-id="cf461-147">Se a mensagem ultrapassar os 8000 caracteres, ela será truncada.</span><span class="sxs-lookup"><span data-stu-id="cf461-147">If the message exceeds 8000 characters, it will be truncated.</span></span>  
  
###### <a name="returning-tabular-results"></a><span data-ttu-id="cf461-148">Retornando resultados tabulares</span><span class="sxs-lookup"><span data-stu-id="cf461-148">Returning Tabular Results</span></span>  
 <span data-ttu-id="cf461-149">Para enviar os resultados de uma consulta diretamente para o cliente, use uma das sobrecargas do método `Execute` no objeto `SqlPipe`.</span><span class="sxs-lookup"><span data-stu-id="cf461-149">To send the results of a query directly to the client, use one of the overloads of the `Execute` method on the `SqlPipe` object.</span></span> <span data-ttu-id="cf461-150">Essa é a maneira mais eficiente de retornar os resultados para o cliente, porque os dados são transferidos para os buffers de rede sem ser copiados para a memória gerenciada.</span><span class="sxs-lookup"><span data-stu-id="cf461-150">This is the most efficient way to return results to the client, since the data is transferred to the network buffers without being copied into managed memory.</span></span> <span data-ttu-id="cf461-151">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="cf461-151">For example:</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlTypes;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   /// <summary>  
   /// Execute a command and send the results to the client directly.  
   /// </summary>  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void ExecuteToClient()  
   {  
   using(SqlConnection connection = new SqlConnection("context connection=true"))   
   {  
      connection.Open();  
      SqlCommand command = new SqlCommand("select @@version", connection);  
      SqlContext.Pipe.ExecuteAndSend(command);  
      }  
   }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Execute a command and send the results to the client directly.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub ExecuteToClient()  
        Using connection As New SqlConnection("context connection=true")  
            connection.Open()  
            Dim command As New SqlCommand("SELECT @@VERSION", connection)  
            SqlContext.Pipe.ExecuteAndSend(command)  
        End Using  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="cf461-152">Para enviar os resultados de uma consulta que foi executada anteriormente através do provedor interno ao processo (ou pré-processar os dados usando uma implementação personalizada de `SqlDataReader`), use a sobrecarga do método `Send` que assume um `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="cf461-152">To send the results of a query that was executed previously through the in-process provider (or to pre-process the data using a custom implementation of `SqlDataReader`), use the overload of the `Send` method that takes a `SqlDataReader`.</span></span> <span data-ttu-id="cf461-153">Esse método é ligeiramente mais lento do que o método direto descrito anteriormente, mas oferece maior flexibilidade para manipular os dados antes de serem enviados para o cliente.</span><span class="sxs-lookup"><span data-stu-id="cf461-153">This method is slightly slower than the direct method described previously, but it offers greater flexibility to manipulate the data before it is sent to the client.</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlTypes;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   /// <summary>  
   /// Execute a command and send the resulting reader to the client  
   /// </summary>  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void SendReaderToClient()  
   {  
      using(SqlConnection connection = new SqlConnection("context connection=true"))   
      {  
         connection.Open();  
         SqlCommand command = new SqlCommand("select @@version", connection);  
         SqlDataReader r = command.ExecuteReader();  
         SqlContext.Pipe.Send(r);  
      }  
   }  
}  
```  
 
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Execute a command and send the results to the client directly.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub SendReaderToClient()  
        Using connection As New SqlConnection("context connection=true")  
            connection.Open()  
            Dim command As New SqlCommand("SELECT @@VERSION", connection)  
            Dim reader As SqlDataReader  
            reader = command.ExecuteReader()  
            SqlContext.Pipe.Send(reader)  
        End Using  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="cf461-154">Para criar um conjunto de resultados dinâmicos, preenchê-lo e enviá-lo para o cliente, você pode criar registros da conexão atual e enviá-los usando `SqlPipe.Send`.</span><span class="sxs-lookup"><span data-stu-id="cf461-154">To create a dynamic result set, populate it and send it to the client, you can create records from the current connection and send them using `SqlPipe.Send`.</span></span>  
  
```csharp  
using System.Data;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
using System.Data.SqlTypes;  
  
public class StoredProcedures   
{  
   /// <summary>  
   /// Create a result set on the fly and send it to the client.  
   /// </summary>  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void SendTransientResultSet()  
   {  
      // Create a record object that represents an individual row, including it's metadata.  
      SqlDataRecord record = new SqlDataRecord(new SqlMetaData("stringcol", SqlDbType.NVarChar, 128));  
  
      // Populate the record.  
      record.SetSqlString(0, "Hello World!");  
  
      // Send the record to the client.  
      SqlContext.Pipe.Send(record);  
   }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Create a result set on the fly and send it to the client.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub SendTransientResultSet()  
        ' Create a record object that represents an individual row, including it's metadata.  
        Dim record As New SqlDataRecord(New SqlMetaData("stringcol", SqlDbType.NVarChar, 128) )  
  
        ' Populate the record.  
        record.SetSqlString(0, "Hello World!")  
  
        ' Send the record to the client.  
        SqlContext.Pipe.Send(record)          
    End Sub  
End Class   
```  
  
 <span data-ttu-id="cf461-155">A seguir está um exemplo de envio de um resultado tabular e uma mensagem através de `SqlPipe`.</span><span class="sxs-lookup"><span data-stu-id="cf461-155">Here is an example of sending a tabular result and a message through `SqlPipe`.</span></span>  
  
```csharp  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void HelloWorld()  
   {  
      SqlContext.Pipe.Send("Hello world! It's now " + System.DateTime.Now.ToString()+"\n");  
      using(SqlConnection connection = new SqlConnection("context connection=true"))   
      {  
         connection.Open();  
         SqlCommand command = new SqlCommand("SELECT ProductNumber FROM ProductMaster", connection);  
         SqlDataReader reader = command.ExecuteReader();  
         SqlContext.Pipe.Send(reader);  
      }  
   }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Execute a command and send the results to the client directly.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub HelloWorld()  
        SqlContext.Pipe.Send("Hello world! It's now " & System.DateTime.Now.ToString() & "\n")  
        Using connection As New SqlConnection("context connection=true")  
            connection.Open()  
            Dim command As New SqlCommand("SELECT ProductNumber FROM ProductMaster", connection)  
            Dim reader As SqlDataReader  
            reader = command.ExecuteReader()  
            SqlContext.Pipe.Send(reader)  
        End Using  
    End Sub  
End Class   
```  
  
 <span data-ttu-id="cf461-156">O primeiro `Send` envia uma mensagem para o cliente, enquanto o segundo envia um resultado tabular que usa `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="cf461-156">The first `Send` sends a message to the client, while the second sends a tabular result using `SqlDataReader`.</span></span>  
  
 <span data-ttu-id="cf461-157">Observe que esses exemplos são meramente para fins ilustrativos.</span><span class="sxs-lookup"><span data-stu-id="cf461-157">Note that these examples are for illustrative purposes only.</span></span> <span data-ttu-id="cf461-158">As funções CLR são mais apropriadas do que instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] simples para aplicativos com uso intenso de cálculos.</span><span class="sxs-lookup"><span data-stu-id="cf461-158">CLR functions are more appropriate than simple [!INCLUDE[tsql](../../includes/tsql-md.md)] statements for computation-intensive applications.</span></span> <span data-ttu-id="cf461-159">Um procedimento armazenado [!INCLUDE[tsql](../../includes/tsql-md.md)] quase equivalente ao exemplo anterior é:</span><span class="sxs-lookup"><span data-stu-id="cf461-159">An almost equivalent [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure to the previous example is:</span></span>  
  
```sql
CREATE PROCEDURE HelloWorld() AS  
BEGIN  
PRINT('Hello world!')  
SELECT ProductNumber FROM ProductMaster  
END;  
```  
  
> [!NOTE]  
>  <span data-ttu-id="cf461-160">Mensagens e conjuntos de resultados são recuperados de maneira diferente no aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="cf461-160">Messages and result sets are retrieved differently in the client application.</span></span> <span data-ttu-id="cf461-161">Por exemplo, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] os conjuntos de resultados aparecem no modo de exibição de **resultados** e as mensagens são exibidas no painel **mensagens** .</span><span class="sxs-lookup"><span data-stu-id="cf461-161">For instance, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] result sets appear in the **Results** view, and messages appear in the **Messages** pane.</span></span>  
  
 <span data-ttu-id="cf461-162">Se o código Visual C# anterior for salvo em um arquivo MyFirstUdp.cs e compilado com:</span><span class="sxs-lookup"><span data-stu-id="cf461-162">If the above Visual C# code is saved in a file MyFirstUdp.cs and compiled with:</span></span>  
  
```console
csc /t:library /out:MyFirstUdp.dll MyFirstUdp.cs   
```  
  
 <span data-ttu-id="cf461-163">Ou então, se o código Visual Basic anterior for salvo em um arquivo MyFirstUdp.vb e compilado com:</span><span class="sxs-lookup"><span data-stu-id="cf461-163">Or, if the above Visual Basic code is saved in a file MyFirstUdp.vb and compiled with:</span></span>  
  
```console
vbc /t:library /out:MyFirstUdp.dll MyFirstUdp.vb   
```  
  
> [!NOTE]  
>  <span data-ttu-id="cf461-164">A partir do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], os objetos de banco de dados de Visual C++ (como os procedimentos armazenados) compilados com `/clr:pure` não são suportados para execução.</span><span class="sxs-lookup"><span data-stu-id="cf461-164">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], Visual C++ database objects (such as stored procedures) compiled with `/clr:pure` are not supported for execution.</span></span>  
  
 <span data-ttu-id="cf461-165">O assembly resultante pode ser registrado, e o ponto de entrada invocado, com o DDL a seguir:</span><span class="sxs-lookup"><span data-stu-id="cf461-165">The resulting assembly can be registered, and the entry point invoked, with the following DDL:</span></span>  
  
```sql
CREATE ASSEMBLY MyFirstUdp FROM 'C:\Programming\MyFirstUdp.dll';  
CREATE PROCEDURE HelloWorld  
AS EXTERNAL NAME MyFirstUdp.StoredProcedures.HelloWorld;  
EXEC HelloWorld;  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf461-166">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cf461-166">See Also</span></span>  
 <span data-ttu-id="cf461-167">[Funções CLR definidas pelo usuário](../../relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md) </span><span class="sxs-lookup"><span data-stu-id="cf461-167">[CLR User-Defined Functions](../../relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md) </span></span>  
 <span data-ttu-id="cf461-168">[Tipos definidos pelo usuário de CLR](../../relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types.md) </span><span class="sxs-lookup"><span data-stu-id="cf461-168">[CLR User-Defined Types](../../relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types.md) </span></span>  
 [<span data-ttu-id="cf461-169">Gatilhos de CLR</span><span class="sxs-lookup"><span data-stu-id="cf461-169">CLR Triggers</span></span>](../../../2014/database-engine/dev-guide/clr-triggers.md)  
  
  
