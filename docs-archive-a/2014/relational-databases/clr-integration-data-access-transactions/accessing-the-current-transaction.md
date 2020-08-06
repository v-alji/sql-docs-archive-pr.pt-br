---
title: Acessando a transação atual | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- current transaction access
- Current property
- Transaction class
ms.assetid: 1a4e2ce5-f627-4c81-8960-6a9968cefda2
author: rothja
ms.author: jroth
ms.openlocfilehash: 34b7e67d30cb9d89a02eb918fcd03651b2915955
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685797"
---
# <a name="accessing-the-current-transaction"></a><span data-ttu-id="865c8-102">Acessando a transação atual</span><span class="sxs-lookup"><span data-stu-id="865c8-102">Accessing the Current Transaction</span></span>
  <span data-ttu-id="865c8-103">Se uma transação estiver ativa no ponto em que o código CLR (Common Language Runtime) que está sendo executado no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for inserido, ela será exposta pela classe `System.Transactions.Transaction`.</span><span class="sxs-lookup"><span data-stu-id="865c8-103">If a transaction is active at the point at which common language runtime (CLR) code running on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is entered, the transaction is exposed through the `System.Transactions.Transaction` class.</span></span> <span data-ttu-id="865c8-104">A propriedade `Transaction.Current` é usada para acessar a transação atual.</span><span class="sxs-lookup"><span data-stu-id="865c8-104">The `Transaction.Current` property is used to access the current transaction.</span></span> <span data-ttu-id="865c8-105">Na maioria das vezes, não é necessário acessar a transação explicitamente.</span><span class="sxs-lookup"><span data-stu-id="865c8-105">In most cases it is not necessary to access the transaction explicitly.</span></span> <span data-ttu-id="865c8-106">Para conexões de banco de dados, ADO.NET verifica `Transaction.Current` automaticamente quando o método `Connection.Open` é chamado e inscreve a conexão de forma transparente nessa transação (a menos que a palavra-chave `Enlist` esteja definida como falsa na cadeia de conexão).</span><span class="sxs-lookup"><span data-stu-id="865c8-106">For database connections, ADO.NET checks `Transaction.Current` automatically when the `Connection.Open` method is called, and transparently enlists the connection in that transaction (unless the `Enlist` keyword is set to false in the connection string).</span></span>  
  
 <span data-ttu-id="865c8-107">Convém usar o objeto `Transaction` diretamente nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="865c8-107">You might want to use the `Transaction` object directly in the following scenarios:</span></span>  
  
-   <span data-ttu-id="865c8-108">Se você desejar inscrever um recurso que não faz inscrição automática ou que, por algum motivo, não foi inscrito durante a inicialização.</span><span class="sxs-lookup"><span data-stu-id="865c8-108">If you want to enlist a resource that does not do automatic enlistment, or that for some reason was not enlisted during initialization.</span></span>  
  
-   <span data-ttu-id="865c8-109">Se você desejar inscrever um recurso explicitamente na transação.</span><span class="sxs-lookup"><span data-stu-id="865c8-109">If you want to explicitly enlist a resource in the transaction.</span></span>  
  
-   <span data-ttu-id="865c8-110">Se você quiser finalizar a transação externa de dentro do seu procedimento armazenado ou função.</span><span class="sxs-lookup"><span data-stu-id="865c8-110">If you want to terminate the external transaction from within your stored procedure or function.</span></span> <span data-ttu-id="865c8-111">Nesse caso, use <xref:System.Transactions.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="865c8-111">In this case, you use <xref:System.Transactions.TransactionScope>.</span></span> <span data-ttu-id="865c8-112">Por exemplo, o código a seguir reverterá a transação atual:</span><span class="sxs-lookup"><span data-stu-id="865c8-112">For example, the following code will rollback the current transaction:</span></span>  
  
    ```  
    using(TransactionScope transactionScope = new TransactionScope(TransactionScopeOptions.Required)) { }  
    ```  
  
 <span data-ttu-id="865c8-113">O resto deste tópico descreve outras maneiras de cancelar uma transação externa.</span><span class="sxs-lookup"><span data-stu-id="865c8-113">The rest of this topic describes other ways to cancel an external transaction.</span></span>  
  
## <a name="canceling-an-external-transaction"></a><span data-ttu-id="865c8-114">Cancelando uma transação externa</span><span class="sxs-lookup"><span data-stu-id="865c8-114">Canceling an External Transaction</span></span>  
 <span data-ttu-id="865c8-115">Você pode cancelar transações externas em uma função ou em um procedimento gerenciado das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="865c8-115">You can cancel external transactions from a managed procedure or function in the following ways:</span></span>  
  
-   <span data-ttu-id="865c8-116">A função ou o procedimento gerenciado pode retornar um valor usando um parâmetro de saída.</span><span class="sxs-lookup"><span data-stu-id="865c8-116">The managed procedure or function can return a value by using an output parameter.</span></span> <span data-ttu-id="865c8-117">O procedimento [!INCLUDE[tsql](../../includes/tsql-md.md)] de chamada pode verificar o valor retornado e, se apropriado, executar `ROLLBACK TRANSACTION`.</span><span class="sxs-lookup"><span data-stu-id="865c8-117">The calling [!INCLUDE[tsql](../../includes/tsql-md.md)] procedure can check the returned value and, if appropriate, execute `ROLLBACK TRANSACTION`.</span></span>  
  
-   <span data-ttu-id="865c8-118">A função ou o procedimento gerenciado pode gerar uma exceção personalizada.</span><span class="sxs-lookup"><span data-stu-id="865c8-118">The managed procedure or function can throw a custom exception.</span></span> <span data-ttu-id="865c8-119">O procedimento de chamada [!INCLUDE[tsql](../../includes/tsql-md.md)] pode capturar a exceção gerada pelo procedimento gerenciado ou função em um bloco try/catch e executar `ROLLBACK TRANSACTION` .</span><span class="sxs-lookup"><span data-stu-id="865c8-119">The calling [!INCLUDE[tsql](../../includes/tsql-md.md)] procedure can catch the exception thrown by the managed procedure or function in a try/catch block and execute `ROLLBACK TRANSACTION`.</span></span>  
  
-   <span data-ttu-id="865c8-120">A função ou o procedimento gerenciado poderá cancelar a transação atual chamando o método `Transaction.Rollback` se uma determinada condição for atendida.</span><span class="sxs-lookup"><span data-stu-id="865c8-120">The managed procedure or function can cancel the current transaction by calling the `Transaction.Rollback` method if a certain condition is met.</span></span>  
  
 <span data-ttu-id="865c8-121">Quando é chamado dentro de uma função ou um procedimento gerenciado, o método `Transaction.Rollback` gera uma exceção com uma mensagem de erro ambígua e pode ser ajustado em um bloco try/catch.</span><span class="sxs-lookup"><span data-stu-id="865c8-121">When it is called within a managed procedure or function, the `Transaction.Rollback` method throws an exception with an ambiguous error message and can be wrapped in a try/catch block.</span></span> <span data-ttu-id="865c8-122">A mensagem de erro vista é semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="865c8-122">The error message thresembles similar to the following:</span></span>  
  
```  
Msg 3994, Level 16, State 1, Procedure uspRollbackFromProc, Line 0  
Transaction is not allowed to roll back inside a user defined routine, trigger or aggregate because the transaction is not started in that CLR level. Change application logic to enforce strict transaction nesting.  
```  
  
 <span data-ttu-id="865c8-123">Essa exceção é esperada e o bloco try/catch é necessário para que a execução do código continue.</span><span class="sxs-lookup"><span data-stu-id="865c8-123">This exception is expected and the try/catch block is necessary for code execution to continue.</span></span> <span data-ttu-id="865c8-124">Sem o bloco try/catch, a exceção será gerada imediatamente para o procedimento [!INCLUDE[tsql](../../includes/tsql-md.md)] de chamada e a execução de código gerenciado será concluída.</span><span class="sxs-lookup"><span data-stu-id="865c8-124">Without the try/catch block, the exception will be immediately thrown to the calling [!INCLUDE[tsql](../../includes/tsql-md.md)] procedure and managed code execution will finish.</span></span> <span data-ttu-id="865c8-125">Quando o código gerenciado concluir a execução, outra exceção será gerada:</span><span class="sxs-lookup"><span data-stu-id="865c8-125">When the managed code finishes execution, another exception is raised:</span></span>  
  
```  
Msg 3991, Level 16, State 1, Procedure uspRollbackFromProc, Line 1   
The context transaction which was active before entering user defined routine, trigger or aggregate " uspRollbackFromProc " has been ended inside of it, which is not allowed. Change application logic to enforce strict transaction nesting. The statement has been terminated.  
```  
  
 <span data-ttu-id="865c8-126">Essa exceção também é esperada e, para que a execução continue, é preciso ter um bloco try/catch em torno da instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] que executa a ação que aciona o gatilho.</span><span class="sxs-lookup"><span data-stu-id="865c8-126">This exception is also expected, and for execution to continue, you must have a try/catch block around the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that performs the action that fires the trigger.</span></span> <span data-ttu-id="865c8-127">Apesar das duas exceções geradas, a transação é revertida e as alterações não são confirmadas.</span><span class="sxs-lookup"><span data-stu-id="865c8-127">Despite the two exceptions thrown, the transaction is rolled back and the changes are not committed.</span></span>  
  
### <a name="example"></a><span data-ttu-id="865c8-128">Exemplo</span><span class="sxs-lookup"><span data-stu-id="865c8-128">Example</span></span>  
 <span data-ttu-id="865c8-129">A seguir, é mostrado um exemplo de uma transação que é revertida de um procedimento gerenciado usando o método `Transaction.Rollback`.</span><span class="sxs-lookup"><span data-stu-id="865c8-129">The following is an example of a transaction being rolled back from a managed procedure by using the `Transaction.Rollback` method.</span></span> <span data-ttu-id="865c8-130">Observe o bloco try/catch em torno do método `Transaction.Rollback` no código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="865c8-130">Notice the try/catch block around the `Transaction.Rollback` method in the managed code.</span></span> <span data-ttu-id="865c8-131">O script [!INCLUDE[tsql](../../includes/tsql-md.md)] cria um assembly e um procedimento armazenado gerenciado.</span><span class="sxs-lookup"><span data-stu-id="865c8-131">The [!INCLUDE[tsql](../../includes/tsql-md.md)] script creates an assembly and managed stored procedure.</span></span> <span data-ttu-id="865c8-132">Lembre-se de que a `EXEC uspRollbackFromProc` instrução é encapsulada em um bloco try/catch, para que a exceção gerada quando o procedimento gerenciado concluir a execução seja detectada.</span><span class="sxs-lookup"><span data-stu-id="865c8-132">Be aware that the `EXEC uspRollbackFromProc` statement is wrapped in a try/catch block, so that the exception thrown when the managed procedure completes execution is caught.</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
using System.Transactions;  
  
public partial class StoredProcedures  
{  
[Microsoft.SqlServer.Server.SqlProcedure]  
public static void uspRollbackFromProc()  
{  
   using (SqlConnection connection = new SqlConnection(@"context connection=true"))  
   {  
      // Open the connection.  
      connection.Open();  
  
      bool successCondition = true;  
  
      // Success condition is met.  
      if (successCondition)  
      {  
         SqlContext.Pipe.Send("Success condition met in procedure.");   
         // Perform other actions here.  
      }  
  
      //  Success condition is not met, the transaction will be rolled back.  
      else  
      {  
         SqlContext.Pipe.Send("Success condition not met in managed procedure. Transaction rolling back...");  
         try  
         {  
               // Get the current transaction and roll it back.  
               Transaction trans = Transaction.Current;  
               trans.Rollback();  
         }  
         catch (SqlException ex)  
         {  
            // Catch the expected exception.   
            // This allows the connection to close correctly.                      
         }    
      }  
  
      // Close the connection.  
      connection.Close();  
   }  
}  
};  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Transactions  
  
Partial Public Class StoredProcedures  
<Microsoft.SqlServer.Server.SqlProcedure()> _  
Public Shared Sub  uspRollbackFromProc ()  
   Using connection As New SqlConnection("context connection=true")  
  
   ' Open the connection.  
   connection.Open()  
  
   Dim successCondition As Boolean  
   successCondition = False  
  
   ' Success condition is met.  
   If successCondition Then  
  
      SqlContext.Pipe.Send("Success condition met in procedure.")  
  
      ' Success condition is not met, the transaction will be rolled back.  
  
   Else  
      SqlContext.Pipe.Send("Success condition not met in managed procedure. Transaction rolling back...")  
      Try  
         ' Get the current transaction and roll it back.  
         Dim trans As Transaction  
         trans = Transaction.Current  
         trans.Rollback()  
  
      Catch ex As SqlException  
         ' Catch the exception instead of throwing it.    
         ' This allows the connection to close correctly.                      
      End Try  
  
   End If  
  
   ' Close the connection.  
   connection.Close()  
  
End Using  
End Sub  
End Class  
```  
  
 <span data-ttu-id="865c8-133">**Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="865c8-133">**Transact-SQL**</span></span>  
  
```  
--Register assembly.  
CREATE ASSEMBLY TestProcs FROM 'C:\Programming\TestProcs.dll'   
Go  
CREATE PROCEDURE uspRollbackFromProc AS EXTERNAL NAME TestProcs.StoredProcedures.uspRollbackFromProc  
Go  
  
-- Execute procedure.  
BEGIN TRY  
BEGIN TRANSACTION   
-- Perform other actions.  
Exec uspRollbackFromProc  
-- Perform other actions.  
PRINT N'Commiting transaction...'  
COMMIT TRANSACTION  
END TRY  
  
BEGIN CATCH  
SELECT ERROR_NUMBER() AS ErrorNum, ERROR_MESSAGE() AS ErrorMessage  
PRINT N'Exception thrown, rolling back transaction.'  
ROLLBACK TRANSACTION  
PRINT N'Transaction rolled back.'   
END CATCH  
Go  
  
-- Clean up.  
DROP Procedure uspRollbackFromProc;  
Go  
DROP ASSEMBLY TestProcs;  
Go  
```  
  
## <a name="see-also"></a><span data-ttu-id="865c8-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="865c8-134">See Also</span></span>  
 [<span data-ttu-id="865c8-135">Integração CLR e transações</span><span class="sxs-lookup"><span data-stu-id="865c8-135">CLR Integration and Transactions</span></span>](../native-client-ole-db-transactions/transactions.md)  
  
  
