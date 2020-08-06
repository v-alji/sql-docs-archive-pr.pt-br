---
title: Diretrizes para a lógica de repetição para transações em tabelas com otimização de memória | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: f2a35c37-4449-49ee-8bba-928028f1de66
author: stevestein
ms.author: sstein
ms.openlocfilehash: c9ffaccefb8d4e0a3044c4858a06029fd4350354
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681080"
---
# <a name="guidelines-for-retry-logic-for-transactions-on-memory-optimized-tables"></a><span data-ttu-id="70907-102">Diretrizes para lógica de repetição das transações em tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="70907-102">Guidelines for Retry Logic for Transactions on Memory-Optimized Tables</span></span>
  <span data-ttu-id="70907-103">Há condições de erro que ocorrem com transações que acessam tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="70907-103">There are error conditions that occur with transactions that access memory-optimized tables.</span></span>  
  
-   41302. <span data-ttu-id="70907-104">A transação atual tentou atualizar um registro que foi atualizado desde que a transação foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="70907-104">The current transaction attempted to update a record that has been updated since the transaction started.</span></span>  
  
-   41305. <span data-ttu-id="70907-105">A transação atual não foi confirmada devido a uma falha de validação de leitura repetida.</span><span class="sxs-lookup"><span data-stu-id="70907-105">The current transaction failed to commit due to a repeatable read validation failure.</span></span>  
  
-   41325. <span data-ttu-id="70907-106">A transação atual não foi confirmada devido a uma falha de validação serializável.</span><span class="sxs-lookup"><span data-stu-id="70907-106">The current transaction failed to commit due to a serializable validation failure.</span></span>  
  
-   41301. <span data-ttu-id="70907-107">Uma transação anterior na qual a transação atual obteve uma dependência foi anulada, e a transação atual não pode mais ser confirmada.</span><span class="sxs-lookup"><span data-stu-id="70907-107">A previous transaction that the current transaction took a dependency on has aborted, and the current transaction can no longer commit.</span></span>  
  
 <span data-ttu-id="70907-108">Uma causa comum desses erros é a interferência entre a transação executada simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="70907-108">A common cause of these errors is interference between concurrently executing transaction.</span></span> <span data-ttu-id="70907-109">A ação corretiva comum é repetir a transação.</span><span class="sxs-lookup"><span data-stu-id="70907-109">The common corrective action is to retry the transaction.</span></span>  
  
 <span data-ttu-id="70907-110">Para obter mais informações sobre essas condições de erro, consulte a seção sobre detecção de conflito, validação e verificações de dependência de confirmação em [transações em tabelas com otimização de memória](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="70907-110">For more information about these error conditions, see the section on Conflict Detection, Validation, and Commit Dependency Checks in [Transactions in Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span></span>  
  
 <span data-ttu-id="70907-111">Os deadlocks (código de erro 1205) não podem ocorrer em tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="70907-111">Deadlocks (error code 1205) cannot occur for memory-optimized tables.</span></span> <span data-ttu-id="70907-112">Os bloqueios não são usados em tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="70907-112">Locks are not used for memory-optimized tables.</span></span> <span data-ttu-id="70907-113">No entanto, se o aplicativo já contiver a lógica de repetição de deadlocks, a lógica existente pode ser estendida para incluir os novos códigos de erro.</span><span class="sxs-lookup"><span data-stu-id="70907-113">However, if the application already contains retry logic for deadlocks, the existing logic could be extended to include the new error codes.</span></span>  
  
## <a name="considerations-for-retrying"></a><span data-ttu-id="70907-114">Considerações sobre repetição</span><span class="sxs-lookup"><span data-stu-id="70907-114">Considerations for Retrying</span></span>  
 <span data-ttu-id="70907-115">Os aplicativos normalmente encontrarão conflitos entre transações e precisarão implementar a lógica de repetição para resolver esses conflitos.</span><span class="sxs-lookup"><span data-stu-id="70907-115">Applications will typically encounter conflicts between transactions and need to implement retry logic to resolve those conflicts.</span></span> <span data-ttu-id="70907-116">O número de conflitos encontrados depende de vários fatores:</span><span class="sxs-lookup"><span data-stu-id="70907-116">The number of conflicts encountered depends on a number of factors:</span></span>  
  
-   <span data-ttu-id="70907-117">Contenção para linhas individuais.</span><span class="sxs-lookup"><span data-stu-id="70907-117">Contention for individual rows.</span></span> <span data-ttu-id="70907-118">O potencial para conflitos aumenta à medida que o número de transações que tentam atualizar a mesma linha aumenta.</span><span class="sxs-lookup"><span data-stu-id="70907-118">The potential for conflicts increases as the number of transactions attempting to update the same row increases.</span></span>  
  
-   <span data-ttu-id="70907-119">O número de linhas lidas pelas transações REPEATABLE READ.</span><span class="sxs-lookup"><span data-stu-id="70907-119">Number of rows read by REPEATABLE READ transactions.</span></span> <span data-ttu-id="70907-120">Quanto mais linhas forem lidas, maior a possibilidade de algumas dessas linhas serem atualizadas por transações simultâneas.</span><span class="sxs-lookup"><span data-stu-id="70907-120">The more rows read, the greater the chance that some of these rows are updated by concurrent transactions.</span></span> <span data-ttu-id="70907-121">Isso causa falhas de validação de leitura repetida.</span><span class="sxs-lookup"><span data-stu-id="70907-121">This causes repeatable read validation failures.</span></span>  
  
-   <span data-ttu-id="70907-122">Tamanho dos intervalos de verificação usados pelas transações SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="70907-122">Size of the scan ranges used by SERIALIZABLE transactions.</span></span> <span data-ttu-id="70907-123">Quanto maior o intervalo de verificação, maior a possibilidade de as transações simultâneas inserirem linhas fantasmas, provocando falhas de validação serializável.</span><span class="sxs-lookup"><span data-stu-id="70907-123">The larger the scan ranges, the higher the chance that concurrent transactions will introduce phantom rows, causing serializable validation failures.</span></span>  
  
     <span data-ttu-id="70907-124">É difícil para um aplicativo evitar esses conflitos, o que exige uma lógica de repetição.</span><span class="sxs-lookup"><span data-stu-id="70907-124">It is difficult for an application to avoid these conflicts, requiring retry logic.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="70907-125">As transações de leitura/gravação que acessam tabelas com otimização de memória exigem a lógica de repetição.</span><span class="sxs-lookup"><span data-stu-id="70907-125">Read-write transactions that access memory-optimized tables require retry logic.</span></span>  
  
### <a name="considerations-for-read-only-transactions-and-natively-compiled-stored-procedures"></a><span data-ttu-id="70907-126">Considerações sobre transações somente leitura e procedimentos armazenados compilados nativamente</span><span class="sxs-lookup"><span data-stu-id="70907-126">Considerations for Read-Only Transactions and Natively Compiled Stored Procedures</span></span>  
 <span data-ttu-id="70907-127">As transações somente leitura que abrangem uma única execução de um procedimento armazenado compilado nativamente não requer a validação de transações REPEATABLE READ e SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="70907-127">Read-only transactions that span a single execution of a natively compiled stored procedure do not require validation for REPEATABLE READ and SERIALIZABLE transactions.</span></span> <span data-ttu-id="70907-128">Os conflitos de gravação não podem ocorrer quando uma transação é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="70907-128">Write conflicts cannot occur due to a transaction being read-only.</span></span>  
  
 <span data-ttu-id="70907-129">No entanto, as falhas de dependência ainda podem ocorrer.</span><span class="sxs-lookup"><span data-stu-id="70907-129">However, dependency failures can still occur.</span></span> <span data-ttu-id="70907-130">As falhas de dependência são mais raras do que os erros resultantes dos conflitos.</span><span class="sxs-lookup"><span data-stu-id="70907-130">Dependency failures are rarer than errors resulting from conflicts.</span></span> <span data-ttu-id="70907-131">Portanto, em muitos casos, uma lógica de repetição específica não é necessária em transações somente leitura que abrangem execuções únicas de procedimentos armazenados compilados nativamente.</span><span class="sxs-lookup"><span data-stu-id="70907-131">Therefore, in many cases, specific retry logic is not required for read-only transactions that span single executions of natively compiled stored procedures.</span></span>  
  
### <a name="considerations-for-read-only-transactions-and-cross-container-transactions"></a><span data-ttu-id="70907-132">Considerações sobre transações somente leitura e transações entre contêineres</span><span class="sxs-lookup"><span data-stu-id="70907-132">Considerations for Read-Only Transactions and Cross-Container Transactions</span></span>  
 <span data-ttu-id="70907-133">As transações somente leitura entre contêineres, que são as transações iniciadas fora do contexto de um procedimento armazenado compilado nativamente, não executarão a validação se as tabelas com otimização de memória forem acessadas no isolamento SNAPSHOT.</span><span class="sxs-lookup"><span data-stu-id="70907-133">Read-only cross-container transactions, which are transactions that are started outside the context of a natively compiled stored procedure, do not perform validation if the memory-optimized tables are all accessed under SNAPSHOT isolation.</span></span> <span data-ttu-id="70907-134">No entanto, quando as tabelas com otimização de memória forem acessadas no isolamento REPEATABLE READ ou SERIALIZABLE, a validação será executada no momento da confirmação.</span><span class="sxs-lookup"><span data-stu-id="70907-134">However, when memory-optimized tables are accessed under REPEATABLE READ or SERIALIZABLE isolation, validation is performed at commit time.</span></span> <span data-ttu-id="70907-135">Nesse caso, a lógica de repetição talvez seja necessária.</span><span class="sxs-lookup"><span data-stu-id="70907-135">In this case, retry logic may be required.</span></span>  
  
 <span data-ttu-id="70907-136">Para obter mais informações, consulte a seção sobre transações entre contêineres em [níveis de isolamento da transação](../../2014/database-engine/transaction-isolation-levels.md).</span><span class="sxs-lookup"><span data-stu-id="70907-136">For more information, see the section on Cross-Container Transactions in [Transaction Isolation Levels](../../2014/database-engine/transaction-isolation-levels.md).</span></span>  
  
## <a name="implementing-retry-logic"></a><span data-ttu-id="70907-137">Implementando a lógica de repetição</span><span class="sxs-lookup"><span data-stu-id="70907-137">Implementing Retry Logic</span></span>  
 <span data-ttu-id="70907-138">Como ocorre com todas as transações que acessam tabelas com otimização de memória, é necessário considerar a lógica de repetição para controlar as falhas potenciais, como conflitos de gravação (o código de erro 41302) ou falhas de dependência (código de erro 41301).</span><span class="sxs-lookup"><span data-stu-id="70907-138">As with all transactions that access memory-optimized tables, you need to consider retry logic to handle potential failures, such as write conflicts (error code 41302) or dependency failures (error code 41301).</span></span> <span data-ttu-id="70907-139">Na maioria dos aplicativos, a taxa de falhas será baixa, mas ainda será necessário controlar as falhas repetindo a transação.</span><span class="sxs-lookup"><span data-stu-id="70907-139">In most applications the failure rate will be low, but it is still necessary to handle failures by retrying the transaction.</span></span> <span data-ttu-id="70907-140">Duas maneiras sugeridas de implementar a lógica de repetição são:</span><span class="sxs-lookup"><span data-stu-id="70907-140">Two suggested ways of implementing retry logic are:</span></span>  
  
-   <span data-ttu-id="70907-141">Repetições do lado do cliente.</span><span class="sxs-lookup"><span data-stu-id="70907-141">Client-side retries.</span></span> <span data-ttu-id="70907-142">As tentativas do lado do cliente são a maneira preferida de implementar a lógica de repetição em casos gerais.</span><span class="sxs-lookup"><span data-stu-id="70907-142">Client-side retries is the preferred way to implement retry logic in the general case.</span></span> <span data-ttu-id="70907-143">O aplicativo cliente captura o erro gerado pela transação e repete a transação.</span><span class="sxs-lookup"><span data-stu-id="70907-143">The client application catches the error thrown by the transaction, and retries the transaction.</span></span> <span data-ttu-id="70907-144">Se um aplicativo cliente existente tiver a lógica de repetição para controlar deadlocks, você poderá estender o aplicativo para tratar os novos códigos de erro.</span><span class="sxs-lookup"><span data-stu-id="70907-144">If an existing client application has retry logic to handle deadlocks, you can extend the application to handle the new error codes.</span></span>  
  
-   <span data-ttu-id="70907-145">Usando um procedimentos armazenado de wrapper.</span><span class="sxs-lookup"><span data-stu-id="70907-145">Using a wrapper stored procedure.</span></span> <span data-ttu-id="70907-146">O cliente chama um procedimento armazenado [!INCLUDE[tsql](../includes/tsql-md.md)] interpretado que chama o procedimento armazenado originalmente criado ou executa a transação.</span><span class="sxs-lookup"><span data-stu-id="70907-146">The client calls an interpreted [!INCLUDE[tsql](../includes/tsql-md.md)] stored procedure that calls the natively compiled stored procedure or executes the transaction.</span></span> <span data-ttu-id="70907-147">O procedimento de wrapper em seguida usa a lógica try/catch para capturar o erro e repetir a chamada de procedimento se for necessário.</span><span class="sxs-lookup"><span data-stu-id="70907-147">The wrapper procedure then uses try/catch logic to catch the error and retry the procedure call if needed.</span></span> <span data-ttu-id="70907-148">É possível que os resultados sejam retornados para o cliente antes da falha, e o cliente não saberia como rejeitá-los.</span><span class="sxs-lookup"><span data-stu-id="70907-148">It is possible that results are returned to the client before the failure, and the client would not know to discard them.</span></span> <span data-ttu-id="70907-149">Portanto, para ter segurança, é melhor usar esse método apenas com procedimentos armazenados compilados de modo nativo que não retornam nenhum conjunto de resultados para o cliente.</span><span class="sxs-lookup"><span data-stu-id="70907-149">Therefore, to be safe, it is best to use this method only with natively compiled stored procedures that do not return any result sets to the client.</span></span>  
  
 <span data-ttu-id="70907-150">A lógica de repetição pode ser implementada no [!INCLUDE[tsql](../includes/tsql-md.md)] ou no código de aplicativo da camada intermediária.</span><span class="sxs-lookup"><span data-stu-id="70907-150">The retry logic can be implemented either in [!INCLUDE[tsql](../includes/tsql-md.md)] or in the application code in the mid-tier.</span></span>  
  
 <span data-ttu-id="70907-151">Dois motivos possíveis para considerar a lógica de repetição:</span><span class="sxs-lookup"><span data-stu-id="70907-151">Two possible reasons to consider the retry logic are:</span></span>  
  
-   <span data-ttu-id="70907-152">O aplicativo cliente tem uma lógica de repetição para outros códigos de erro, como 1205, que você pode estender.</span><span class="sxs-lookup"><span data-stu-id="70907-152">The client application has retry logic for other error codes, such as 1205, which you can extend.</span></span>  
  
-   <span data-ttu-id="70907-153">Os conflitos são raros, e é importante reduzir a latência completa usando a execução preparada.</span><span class="sxs-lookup"><span data-stu-id="70907-153">Conflicts are rare, and it is important to reduce end-to-end latency by using prepared execution.</span></span> <span data-ttu-id="70907-154">Para obter mais informações sobre como executar procedimentos armazenados compilados nativamente diretamente, consulte [procedimentos armazenados compilados nativamente](../relational-databases/in-memory-oltp/natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="70907-154">For more information about executing natively compiled stored procedures directly, see [Natively Compiled Stored Procedures](../relational-databases/in-memory-oltp/natively-compiled-stored-procedures.md).</span></span>  
  
 <span data-ttu-id="70907-155">O exemplo a seguir mostra uma lógica de repetição em um procedimento armazenado interpretado [!INCLUDE[tsql](../includes/tsql-md.md)], que contém uma chamada para um procedimento armazenado compilado nativamente ou para uma transação entre contêineres.</span><span class="sxs-lookup"><span data-stu-id="70907-155">The following sample shows retry logic in an interpreted [!INCLUDE[tsql](../includes/tsql-md.md)] stored procedure that contains a call either to a natively compiled stored procedure or to a cross-container transaction.</span></span>  
  
```sql  
CREATE PROCEDURE usp_my_procedure @param1 type1, @param2 type2, ...  
AS  
BEGIN  
  -- number of retries - tune based on the workload  
  DECLARE @retry INT = 10  
  
  WHILE (@retry > 0)  
  BEGIN  
    BEGIN TRY  
  
      -- exec usp_my_native_proc @param1, @param2, ...  
  
      --       or  
  
      -- BEGIN TRANSACTION  
      --   ...  
      -- COMMIT TRANSACTION  
  
      SET @retry = 0  
    END TRY  
    BEGIN CATCH  
      SET @retry -= 1  
  
      -- the error number for deadlocks (1205) does not need to be included for   
      -- transactions that do not access disk-based tables  
      IF (@retry > 0 AND error_number() in (41302, 41305, 41325, 41301, 1205))  
      BEGIN  
        -- these error conditions are transaction dooming - rollback the transaction  
        -- this is not needed if the transaction spans a single native proc execution  
        --   as the native proc will simply rollback when an error is thrown   
        IF XACT_STATE() = -1  
          ROLLBACK TRANSACTION  
  
        -- use a delay if there is a high rate of write conflicts (41302)  
        --   length of delay should depend on the typical duration of conflicting transactions  
        -- WAITFOR DELAY '00:00:00.001'  
      END  
      ELSE  
      BEGIN  
        -- insert custom error handling for other error conditions here  
  
        -- throw if this is not a qualifying error condition  
        ;THROW  
      END  
    END CATCH  
  END  
END  
```  
  
## <a name="see-also"></a><span data-ttu-id="70907-156">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="70907-156">See Also</span></span>  
 <span data-ttu-id="70907-157">[Noções básicas sobre transações em tabelas com otimização de memória](../../2014/database-engine/understanding-transactions-on-memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="70907-157">[Understanding Transactions on Memory-Optimized Tables](../../2014/database-engine/understanding-transactions-on-memory-optimized-tables.md) </span></span>  
 <span data-ttu-id="70907-158">[Transações em tabelas com otimização de memória](../relational-databases/in-memory-oltp/memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="70907-158">[Transactions in Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md) </span></span>  
 [<span data-ttu-id="70907-159">Diretrizes para níveis de isolamento da transação com tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="70907-159">Guidelines for Transaction Isolation Levels with Memory-Optimized Tables</span></span>](../../2014/database-engine/guidelines-for-transaction-isolation-levels-with-memory-optimized-tables.md)  
  
  
