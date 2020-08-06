---
title: Usando System. Transactions | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- TransactionScope class
- Dispose method
- System.Transactions namespace
ms.assetid: 79656ce5-ce46-4c5e-9540-cf9869bd774b
author: rothja
ms.author: jroth
ms.openlocfilehash: 277edd75ea0437dc532ed5672e3c7b8a0569af8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685788"
---
# <a name="using-systemtransactions"></a><span data-ttu-id="6bfc7-102">Usando System.Transactions</span><span class="sxs-lookup"><span data-stu-id="6bfc7-102">Using System.Transactions</span></span>
  <span data-ttu-id="6bfc7-103">O `System.Transactions` fornece uma estrutura de transação que é totalmente integrada com o ADO.NET e a integração CLR (Common Language Runtime) do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6bfc7-103">The `System.Transactions` namespace provides a transaction framework that is fully integrated with ADO.NET and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] common language runtime (CLR) integration.</span></span> <span data-ttu-id="6bfc7-104">Uma classe `System.Transactions.TransactionScope` torna um bloco de código transacional inscrevendo implicitamente conexões em uma transação distribuída.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-104">The `System.Transactions.TransactionScope` class makes a code block transactional by implicitly enlisting connections in a distributed transaction.</span></span> <span data-ttu-id="6bfc7-105">Chame o método `Complete` no final do bloco de código marcado pelo `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-105">You must call the `Complete` method at the end of the code block marked by the `TransactionScope`.</span></span> <span data-ttu-id="6bfc7-106">O método `Dispose` será invocado quando a execução do programa deixar um bloco de código, fazendo a transação ser descontinuada se o método `Complete` não for chamado.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-106">The `Dispose` method is invoked when program execution leaves a code block, causing the transaction to be discontinued if the `Complete` method is not called.</span></span> <span data-ttu-id="6bfc7-107">Se tiver sido lançada uma exceção que faz o código deixar o escopo, a transação será considerada descontinuada.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-107">If an exception has been thrown that causes the code to leave scope, the transaction is considered to be discontinued.</span></span>  
  
 <span data-ttu-id="6bfc7-108">É recomendável utilizar um bloco `using` para assegurar que o método `Dispose` seja chamado no objeto `TransactionScope` ao sair do bloco `using`.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-108">We recommend that you employ a `using` block to ensure that the `Dispose` method is called on the `TransactionScope` object when the `using` block is exited.</span></span> <span data-ttu-id="6bfc7-109">Uma falha ao confirmar ou reverter transações pendentes pode diminuir muito o desempenho, pois o tempo limite padrão para o `TransactionScope` é de um minuto.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-109">Failure to commit or roll back pending transactions can seriously degrade performance because the default time-out for the `TransactionScope` is one minute.</span></span> <span data-ttu-id="6bfc7-110">Se você não usar uma instrução `using`, deverá executar todo o trabalho em um bloco `Try` e chamar explicitamente o método `Dispose` no bloco `Finally`.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-110">If you do not use a `using` statement, you must perform all work in a `Try` block and explicitly call the `Dispose` method in the `Finally` block.</span></span>  
  
 <span data-ttu-id="6bfc7-111">Se ocorrer uma exceção no `TransactionScope`, a transação será marcada como inconsistente e abandonada.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-111">If an exception occurs within the `TransactionScope`, the transaction is marked as inconsistent and is abandoned.</span></span> <span data-ttu-id="6bfc7-112">Ela será revertida quando o `TransactionScope` for descartado.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-112">It is rolled back when the `TransactionScope` is disposed.</span></span> <span data-ttu-id="6bfc7-113">Se nenhuma exceção ocorrer, as transações participantes serão confirmadas.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-113">If no exception occurs, participating transactions commit.</span></span>  
  
 <span data-ttu-id="6bfc7-114">`TransactionScope` deve ser usado somente quando são acessados gerenciadores de recursos externos ou fontes de dados locais e remotas.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-114">`TransactionScope` should be used only when local and remote data sources or external resource managers are being accessed.</span></span> <span data-ttu-id="6bfc7-115">Isso porque `TransactionScope` sempre causa a elevação de transações, mesmo que esteja sendo usado apenas em uma conexão de contexto.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-115">This is because `TransactionScope` always causes transactions to promote, even if it is being used only within a context connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6bfc7-116">Por padrão, a classe `TransactionScope` cria uma transação com um `System.Transactions.Transaction.IsolationLevel` de `Serializable`.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-116">The `TransactionScope` class creates a transaction with a `System.Transactions.Transaction.IsolationLevel` of `Serializable` by default.</span></span> <span data-ttu-id="6bfc7-117">Dependendo do seu aplicativo, talvez você queira considerar abaixar o nível de isolamento para evitar uma contenção elevada em seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-117">Depending on your application, you might want to consider lowering the isolation level to avoid high contention in your application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6bfc7-118">É recomendável executar apenas atualizações, inserções e exclusões em transações distribuídas em servidores remotos, pois isso consume recursos de banco de dados significativos.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-118">We recommend that you perform only updates, inserts, and deletes within distributed transactions against remote servers because they consume significant database resources.</span></span> <span data-ttu-id="6bfc7-119">Caso a operação seja executada no servidor local, uma transação distribuída não será necessária e uma transação local será suficiente.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-119">If the operation is going to be performed on the local server, a distributed transaction is not necessary and a local transaction will suffice.</span></span> <span data-ttu-id="6bfc7-120">Instruções SELECT podem bloquear recursos do banco de dados desnecessariamente e, em alguns cenários, pode ser necessário usar transações para seleções.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-120">SELECT statements may lock database resources unnecessarily, and in some scenarios it may be necessary to use transactions for selects.</span></span> <span data-ttu-id="6bfc7-121">Qualquer trabalho que não seja do banco de dados deve ser executado fora do escopo da transação, a menos que envolva outros gerenciadores de recursos transacionados.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-121">Any non-database work should be done outside of the scope of the transaction, unless it involves other transacted resource managers.</span></span> <span data-ttu-id="6bfc7-122">Apesar de uma exceção no escopo da transação evitar que a transação seja confirmada, a classe `TransactionScope` não tem provisão para reverter as alterações que seu código tenha feito fora do escopo da própria transação.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-122">Although an exception within the scope of the transaction prevents the transaction from committing, the `TransactionScope` class has no provision for rolling back any changes your code has made outside of the scope of the transaction itself.</span></span> <span data-ttu-id="6bfc7-123">Se precisar executar alguma ação ao reverter a ação, será necessário escrever sua própria implementação da interface `System.Transactions.IEnlistmentNotification` e inscrevê-la na transação explicitamente.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-123">If you need to take some action when the transaction is rolled back, you must write your own implementation of the `System.Transactions.IEnlistmentNotification` interface, and explicitly enlist in the transaction.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6bfc7-124">Exemplo</span><span class="sxs-lookup"><span data-stu-id="6bfc7-124">Example</span></span>  
 <span data-ttu-id="6bfc7-125">Para trabalhar com `System.Transactions`, é necessário ter uma referência para o arquivo System.Transactions.dll.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-125">To work with `System.Transactions`, you must have a reference to the System.Transactions.dll file.</span></span>  
  
 <span data-ttu-id="6bfc7-126">O código a seguir demonstra como criar uma transação que pode ser elevada em duas instâncias diferentes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6bfc7-126">The following code demonstrates how to create a transaction that can be promoted against two different instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6bfc7-127">Essas instâncias são representadas por dois objetos `System.Data.SqlClient.SqlConnection` diferentes, que são quebrados em um bloco `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-127">These instances are represented by two different `System.Data.SqlClient.SqlConnection` objects, which are wrapped in a `TransactionScope` block.</span></span> <span data-ttu-id="6bfc7-128">O código cria o bloco `TransactionScope` com uma instrução `using` e abre a primeira conexão, que o inscreve automaticamente no `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-128">The code creates the `TransactionScope` block with a `using` statement, and opens the first connection, which automatically enlists it in the `TransactionScope`.</span></span> <span data-ttu-id="6bfc7-129">A transação é inscrita inicialmente como uma transação lightweight, não uma transação distribuída completa.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-129">The transaction is initially enlisted as a lightweight transaction, not a full distributed transaction.</span></span> <span data-ttu-id="6bfc7-130">O código presume a existência de uma lógica condicional (que foi omitida para ser breve).</span><span class="sxs-lookup"><span data-stu-id="6bfc7-130">The code assumes the existence of conditional logic (which has been omitted for brevity).</span></span> <span data-ttu-id="6bfc7-131">Ele abrirá a segunda conexão somente se for necessário, inscrevendo-o no `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-131">It opens the second connection only if it is needed, enlisting it in the `TransactionScope`.</span></span> <span data-ttu-id="6bfc7-132">Quando a conexão é aberta, a transação é automaticamente elevada a uma transação distribuída completa.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-132">When the connection is opened, the transaction is automatically promoted to a full distributed transaction.</span></span> <span data-ttu-id="6bfc7-133">Então, o código invoca `TransactionScope.Complete`, que confirma a transação.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-133">The code then invokes `TransactionScope.Complete`, which commits the transaction.</span></span> <span data-ttu-id="6bfc7-134">O código dispõe das duas conexões ao sair das instruções `using` para as conexões.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-134">The code disposes of the two connections when exiting the `using` statements for the connections.</span></span> <span data-ttu-id="6bfc7-135">O método `TransactionScope.Dispose` para o `TransactionScope` é chamado automaticamente no encerramento do bloco `using` para o `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-135">The `TransactionScope.Dispose` method for the `TransactionScope` is automatically called at the termination of the `using` block for the `TransactionScope`.</span></span> <span data-ttu-id="6bfc7-136">Se uma exceção tiver sido lançada em qualquer ponto no bloco `TransactionScope`, `Complete` não será chamado e a transação distribuída será revertida quando o `TransactionScope` for descartado.</span><span class="sxs-lookup"><span data-stu-id="6bfc7-136">If an exception has been thrown at any point in the `TransactionScope` block, `Complete` does not get called, and the distributed transaction will roll back when the `TransactionScope` is disposed.</span></span>  
  
 <span data-ttu-id="6bfc7-137">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6bfc7-137">Visual Basic</span></span>  
  
```  
Using transScope As New TransactionScope()  
    Using connection1 As New SqlConnection(connectString1)  
        ' Opening connection1 automatically enlists it in the   
        ' TransactionScope as a lightweight transaction.  
        connection1.Open()  
  
        ' Do work in the first connection.  
  
        ' Assumes conditional logic in place where the second  
        ' connection will only be opened as needed.  
        Using connection2 As New SqlConnection(connectString2)  
            ' Open the second connection, which enlists the   
            ' second connection and promotes the transaction to  
            ' a full distributed transaction.  
            connection2.Open()  
  
            ' Do work in the second connection.  
  
        End Using  
    End Using  
  
    ' Commit the transaction.  
    transScope.Complete()  
End Using  
```  
  
 <span data-ttu-id="6bfc7-138">C#</span><span class="sxs-lookup"><span data-stu-id="6bfc7-138">C#</span></span>  
  
```  
using (TransactionScope transScope = new TransactionScope())  
{  
    using (SqlConnection connection1 = new   
       SqlConnection(connectString1))  
    {  
        // Opening connection1 automatically enlists it in the   
        // TransactionScope as a lightweight transaction.  
        connection1.Open();  
  
        // Do work in the first connection.  
  
        // Assumes conditional logic in place where the second  
        // connection will only be opened as needed.  
        using (SqlConnection connection2 = new   
            SqlConnection(connectString2))  
        {  
            // Open the second connection, which enlists the   
            // second connection and promotes the transaction to  
            // a full distributed transaction.   
            connection2.Open();  
  
            // Do work in the second connection.  
        }  
    }  
    //  The Complete method commits the transaction.  
    transScope.Complete();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="6bfc7-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6bfc7-139">See Also</span></span>  
 [<span data-ttu-id="6bfc7-140">Integração CLR e transações</span><span class="sxs-lookup"><span data-stu-id="6bfc7-140">CLR Integration and Transactions</span></span>](../native-client-ole-db-transactions/transactions.md)  
  
  
