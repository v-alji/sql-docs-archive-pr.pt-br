---
title: Transações entre contêineres | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 5d84b51a-ec17-4c5c-b80e-9e994fc8ae80
author: stevestein
ms.author: sstein
ms.openlocfilehash: 28437f0903459616a574e713c0f138e8bb459870
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574254"
---
# <a name="cross-container-transactions"></a><span data-ttu-id="85ecc-102">Transações entre contêineres</span><span class="sxs-lookup"><span data-stu-id="85ecc-102">Cross-Container Transactions</span></span>
  <span data-ttu-id="85ecc-103">As transações entre contêineres são as transações de usuário implícitas ou explícitas que incluem chamadas para procedimentos armazenados compilados nativamente ou para operações em tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="85ecc-103">Cross-container transactions are either implicit or explicit user transactions that include calls to natively-compiled stored procedures or operations on memory-optimized tables.</span></span>  
  
 <span data-ttu-id="85ecc-104">No [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], as chamadas aos procedimentos armazenados não iniciam uma transação.</span><span class="sxs-lookup"><span data-stu-id="85ecc-104">In [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], calls to stored procedures do not initiate a transaction.</span></span> <span data-ttu-id="85ecc-105">As execuções de procedimentos compilados nativamente no modo de confirmação automática (não no contexto de uma transação de usuário) não são consideradas transações entre contêineres.</span><span class="sxs-lookup"><span data-stu-id="85ecc-105">Executions of natively compiled procedures in autocommit mode (not in the context of a user transaction) are not considered cross-container transactions.</span></span>  
  
 <span data-ttu-id="85ecc-106">Qualquer consulta interpretada que faça referência a tabelas com otimização de memória é considerada uma parte de uma transação entre contêineres, seja ela executada de uma transação explícita ou implícita, ou no modo de confirmação automática.</span><span class="sxs-lookup"><span data-stu-id="85ecc-106">Any interpreted query that references memory-optimized tables is considered a part of a cross-container transaction, whether executed from an explicit or implicit transaction or in auto-commit mode.</span></span>  
  
##  <a name="isolation-of-individual-operations"></a><a name="isolation"></a><span data-ttu-id="85ecc-107">Isolamento de operações individuais</span><span class="sxs-lookup"><span data-stu-id="85ecc-107">Isolation of Individual Operations</span></span>  
 <span data-ttu-id="85ecc-108">Cada transação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tem um nível de isolamento.</span><span class="sxs-lookup"><span data-stu-id="85ecc-108">Each [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] transaction has an isolation level.</span></span> <span data-ttu-id="85ecc-109">O nível de isolamento padrão é Read Committed.</span><span class="sxs-lookup"><span data-stu-id="85ecc-109">The default isolation level is Read Committed.</span></span> <span data-ttu-id="85ecc-110">Para usar um nível de isolamento diferente, você pode definir o nível de isolamento usando [SET TRANSACTION ISOLATION level &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="85ecc-110">To use a different isolation level, you can set the isolation level using [SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span></span>  
  
 <span data-ttu-id="85ecc-111">Geralmente, é necessário executar operações em tabelas com otimização de memória em um nível de isolamento diferente das operações em tabelas baseadas em disco.</span><span class="sxs-lookup"><span data-stu-id="85ecc-111">It is often necessary to perform operations on memory-optimized tables at a different isolation level than operations on disk-based tables.</span></span> <span data-ttu-id="85ecc-112">Em uma transação, é possível definir um nível de isolamento diferente para uma coleção de instruções ou para uma operação de leitura individual.</span><span class="sxs-lookup"><span data-stu-id="85ecc-112">In a transaction, it is possible to set a different isolation level for a collection of statements or for an individual read operation.</span></span>  
  
### <a name="specifying-the-isolation-level-of-individual-operations"></a><span data-ttu-id="85ecc-113">Especificando o nível de isolamento de operações individuais</span><span class="sxs-lookup"><span data-stu-id="85ecc-113">Specifying the Isolation Level of Individual Operations</span></span>  
 <span data-ttu-id="85ecc-114">Para definir um nível de isolamento diferente para um conjunto de instruções em uma transação, você pode usar `SET TRANSACTION ISOLATION LEVEL`.</span><span class="sxs-lookup"><span data-stu-id="85ecc-114">To set a different isolation level for a set of statements in a transaction, you can use `SET TRANSACTION ISOLATION LEVEL`.</span></span> <span data-ttu-id="85ecc-115">O exemplo a seguir de uma transação usa o nível de isolamento serializável como padrão.</span><span class="sxs-lookup"><span data-stu-id="85ecc-115">The following example of a transaction uses the serializable isolation level as default.</span></span> <span data-ttu-id="85ecc-116">As operações de inserção e seleção em t3, t2 e t1 são executadas sob o isolamento de leitura repetida.</span><span class="sxs-lookup"><span data-stu-id="85ecc-116">The insert and select operations on t3, t2, and t1 are executed under repeatable read isolation.</span></span>  
  
```sql  
set transaction isolation level serializable  
go  
  
begin transaction  
 ......  
  set transaction isolation level repeatable read  
  
  insert t3 select * from t1 join t2 on t1.id=t2.id  
  
  set transaction isolation level serializable  
 ......  
commit  
```  
  
 <span data-ttu-id="85ecc-117">Para definir um nível de isolamento para operações de leitura individual que seja diferente do padrão da transação, você pode usar uma dica de tabela (por exemplo, serializável).</span><span class="sxs-lookup"><span data-stu-id="85ecc-117">To set an isolation level for individual read operations that is different from the transaction default, you can use a table hint (for example, serializable).</span></span> <span data-ttu-id="85ecc-118">Cada seleção corresponde a uma operação de leitura, assim como cada atualização e cada exclusão correspondem a uma leitura, pois a linha sempre precisa ser lida para poder ser atualizada ou excluída.</span><span class="sxs-lookup"><span data-stu-id="85ecc-118">Every select corresponds to a read operation and every update and every delete corresponds to a read, because the row always needs to be read before it can be updated or deleted.</span></span> <span data-ttu-id="85ecc-119">As operações de inserção não têm um nível de isolamento, pois as gravações são sempre isoladas no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85ecc-119">Insert operations do not have an isolation level, because writes are always isolated in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="85ecc-120">No exemplo a seguir, o nível de isolamento padrão da transação é leitura confirmada, mas a tabela t1 é acessada em serializável e t2 no isolamento de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="85ecc-120">In the following example, the default isolation level for the transaction is read committed, but table t1 is accessed under serializable and t2 under snapshot isolation.</span></span>  
  
```sql  
set transaction isolation level read committed  
go  
  
begin transaction  
 ......  
  
  insert t3 select * from t1 (serializable) join t2 (snapshot) on t1.id=t2.id  
  
  ......  
commit  
```  
  
### <a name="isolation-semantics-for-individual-operations"></a><span data-ttu-id="85ecc-121">Semântica de isolamento para operações individuais</span><span class="sxs-lookup"><span data-stu-id="85ecc-121">Isolation Semantics for Individual Operations</span></span>  
 <span data-ttu-id="85ecc-122">Uma transação serializável T é executada em isolamento completo.</span><span class="sxs-lookup"><span data-stu-id="85ecc-122">A serializable transaction T is executed in complete isolation.</span></span> <span data-ttu-id="85ecc-123">É como se todas as outras transações tivessem sido confirmadas antes de T ter sido iniciada, ou elas foram iniciadas depois de T ter sido confirmada.</span><span class="sxs-lookup"><span data-stu-id="85ecc-123">It is as if every other transaction has either committed before T started, or is started after T committed.</span></span> <span data-ttu-id="85ecc-124">Isso se torna mais complexo quando operações diferentes em uma transação têm diferentes níveis de isolamento.</span><span class="sxs-lookup"><span data-stu-id="85ecc-124">It becomes more complex when different operations in a transaction have different isolation levels.</span></span>  
  
 <span data-ttu-id="85ecc-125">A semântica geral dos níveis de isolamento da transação no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , juntamente com as implicações no bloqueio, é explicada em [definir nível de isolamento da transação &#40;&#41;TRANSACT-SQL ](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="85ecc-125">The general semantics of the transaction isolation levels in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], along with the implications on locking, is explained in [SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span></span>  
  
 <span data-ttu-id="85ecc-126">Para transações entre contêineres em que operações diferentes podem ter níveis de isolamento diferentes, você precisa entender a semântica de isolamento das operações de leitura individual.</span><span class="sxs-lookup"><span data-stu-id="85ecc-126">For cross-container transactions where different operations may have different isolation levels, you need to understand the semantics of isolation of individual read operations.</span></span> <span data-ttu-id="85ecc-127">As operações de gravação sempre são isoladas.</span><span class="sxs-lookup"><span data-stu-id="85ecc-127">Write operations are always isolated.</span></span> <span data-ttu-id="85ecc-128">As gravações em transações diferentes não podem se afetar.</span><span class="sxs-lookup"><span data-stu-id="85ecc-128">Writes in different transactions cannot impact each other.</span></span>  
  
 <span data-ttu-id="85ecc-129">Uma operação de leitura de dados retorna um número de linhas que atendem a uma condição de filtro.</span><span class="sxs-lookup"><span data-stu-id="85ecc-129">A data read operation returns a number of rows that satisfy a filter condition.</span></span>  
  
 <span data-ttu-id="85ecc-130">As leituras são executadas como parte de um T de transação. os níveis de isolamento para operações de leitura podem ser compreendidos em termos de,</span><span class="sxs-lookup"><span data-stu-id="85ecc-130">Reads are performed as part of a transaction T. Isolation levels for read operations can be understood in terms of,</span></span>  
  
 <span data-ttu-id="85ecc-131">Status de confirmação</span><span class="sxs-lookup"><span data-stu-id="85ecc-131">Commit Status</span></span>  
 <span data-ttu-id="85ecc-132">O status de confirmação se refere à garantia de confirmação da leitura dos dados.</span><span class="sxs-lookup"><span data-stu-id="85ecc-132">Commit status refers to whether the data read is guaranteed to be committed.</span></span>  
  
 <span data-ttu-id="85ecc-133">(Transacional) Consistência</span><span class="sxs-lookup"><span data-stu-id="85ecc-133">(Transactional) Consistency</span></span>  
 <span data-ttu-id="85ecc-134">A consistência transacional para um conjunto de leituras se refere à garantia de que as versões de linha lidas incluirão atualizações precisamente do mesmo conjunto de transações.</span><span class="sxs-lookup"><span data-stu-id="85ecc-134">Transactional consistency for a set of reads refers to whether the row versions read are all guaranteed to include updates from precisely the same set of transactions.</span></span>  
  
 <span data-ttu-id="85ecc-135">A estabilidade garante que o sistema forneça à transação T informações sobre a leitura de dados.</span><span class="sxs-lookup"><span data-stu-id="85ecc-135">Stability guarantees the system gives to transaction T about the data read.</span></span>  
 <span data-ttu-id="85ecc-136">A estabilidade se refere se as leituras da transação podem ser repetidas.</span><span class="sxs-lookup"><span data-stu-id="85ecc-136">Stability refers to whether the transaction's reads are repeatable.</span></span> <span data-ttu-id="85ecc-137">Isto é, se as leituras fossem repetidas, elas retornariam as mesmas linhas e versões de linha?</span><span class="sxs-lookup"><span data-stu-id="85ecc-137">That is, if the reads were repeated would they return the same rows and row versions?</span></span>  
  
 <span data-ttu-id="85ecc-138">Determinadas garantias se referem à hora de término lógica da transação.</span><span class="sxs-lookup"><span data-stu-id="85ecc-138">Certain guarantees refer to the logical end time of the transaction.</span></span> <span data-ttu-id="85ecc-139">De modo geral, a hora de término lógica é a hora em que a transação foi confirmada no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="85ecc-139">In general, the logical end time is the time the transaction is committed to the database.</span></span> <span data-ttu-id="85ecc-140">Se as tabelas com otimização de memória são acessadas pela transação, a hora de término lógica, tecnicamente, é o início da fase de validação.</span><span class="sxs-lookup"><span data-stu-id="85ecc-140">If memory-optimized tables are accessed by the transaction, the logical end time is technically the beginning of the validation phase.</span></span> <span data-ttu-id="85ecc-141">(Para obter mais informações, consulte a discussão de vida útil da transação em [transações em tabelas com otimização de memória](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="85ecc-141">(For more information, see the transaction lifetime discussion in [Transactions in Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span></span>  
  
 <span data-ttu-id="85ecc-142">Independentemente do nível de isolamento, uma transação (T) sempre vê suas próprias atualizações:</span><span class="sxs-lookup"><span data-stu-id="85ecc-142">Regardless of isolation level, a transaction (T) always sees its own updates:</span></span>  
  
 <span data-ttu-id="85ecc-143">READ UNCOMMITTED</span><span class="sxs-lookup"><span data-stu-id="85ecc-143">READ UNCOMMITTED</span></span>  
 <span data-ttu-id="85ecc-144">A leitura de dados não pode ser confirmada, consistente ou estável.</span><span class="sxs-lookup"><span data-stu-id="85ecc-144">The data read may neither be committed, consistent, or stable.</span></span> <span data-ttu-id="85ecc-145">No entanto, ela incluirá operações de gravação anteriores feitas por T.</span><span class="sxs-lookup"><span data-stu-id="85ecc-145">However, it will include earlier write operations done by T.</span></span>  
  
 <span data-ttu-id="85ecc-146">READ COMMITTED</span><span class="sxs-lookup"><span data-stu-id="85ecc-146">READ COMMITTED</span></span>  
 <span data-ttu-id="85ecc-147">A leitura de dados será confirmada.</span><span class="sxs-lookup"><span data-stu-id="85ecc-147">The data read will be committed.</span></span>  
  
 <span data-ttu-id="85ecc-148">SNAPSHOT</span><span class="sxs-lookup"><span data-stu-id="85ecc-148">SNAPSHOT</span></span>  
 <span data-ttu-id="85ecc-149">Todas as operações de leitura executadas por T no isolamento instantâneo têm a mesma hora de leitura lógica, que é o início da transação.</span><span class="sxs-lookup"><span data-stu-id="85ecc-149">All read operations performed by T under snapshot isolation have the same logical read time, which is the beginning of the transaction.</span></span> <span data-ttu-id="85ecc-150">A leitura de dados tem a garantia de confirmação e consistência a partir da hora de leitura lógica.</span><span class="sxs-lookup"><span data-stu-id="85ecc-150">The data read is guaranteed to be committed and consistent as of the logical read time.</span></span> <span data-ttu-id="85ecc-151">A repetição de uma leitura a partir da hora de leitura original é garantia de retorno do mesmo resultado.</span><span class="sxs-lookup"><span data-stu-id="85ecc-151">Repeating a read as of the original read time is guaranteed to return the same result.</span></span>  
  
 <span data-ttu-id="85ecc-152">REPEATABLE READ</span><span class="sxs-lookup"><span data-stu-id="85ecc-152">REPEATABLE READ</span></span>  
 <span data-ttu-id="85ecc-153">A leitura de dados tem garantia de confirmação e estabilização até a hora de término lógica da transação.</span><span class="sxs-lookup"><span data-stu-id="85ecc-153">The data read is guaranteed to be committed and stable up to the logical end time of the transaction.</span></span>  
  
 <span data-ttu-id="85ecc-154">SERIALIZABLE</span><span class="sxs-lookup"><span data-stu-id="85ecc-154">SERIALIZABLE</span></span>  
 <span data-ttu-id="85ecc-155">Todas as garantias de leitura REPETIda e de eliminação de fantasma e a consistência transacional com relação a todas as operações de leitura serializáveis executadas por T. a desexecução de fantasma significa que a operação de verificação só pode retornar linhas adicionais que foram escritas por T, mas nenhuma linha que foi gravada por outras transações.</span><span class="sxs-lookup"><span data-stu-id="85ecc-155">All guarantees of REPEATABLE READ plus phantom avoidance and transactional consistency with respect to all serializable read operations performed by T. Phantom avoidance means that the scan operation can only return additional rows that were written by T, but no rows that were written by other transactions.</span></span>  
  
 <span data-ttu-id="85ecc-156">Considere a seguinte transação:</span><span class="sxs-lookup"><span data-stu-id="85ecc-156">Consider the following transaction,</span></span>  
  
```sql  
set transaction isolation level read committed  
go  
  
begin transaction  
  -- remove all rows from t3; the related read operation is performed under read committed   
  -- isolation, as this is the default for the transaction  
  delete from t3  
  
  -- copy the contents from t1 to t3; the read on t1 is performed under the serializable   
  -- isolation level  
  insert t3 select * from t1 (serializable)  
  
  -- compare t3 and t1; note: the result set may not be empty, as rows may have been added   
  -- by other transaction before this select, due to the read committed isolation level  
  select * from t3 except t1  
  
  -- compare t1 and t3; note: the result set is empty, as no rows have been added to t1   
  -- since its contents were copied to t1, due to the serializable isolation level  
  select * from t1 except t3  
commit  
```  
  
 <span data-ttu-id="85ecc-157">Essa transação exclui todas as linhas de t3 em isolamento de leitura confirmada, copia todas as linhas de t1 a t3 no isolamento serializável e então compara t1 e t3.</span><span class="sxs-lookup"><span data-stu-id="85ecc-157">This transaction deletes all rows from t3 under read committed isolation, copies all rows from t1 to t3 under serializable isolation, and then compares t1 and t3.</span></span> <span data-ttu-id="85ecc-158">Algumas linhas [não em t1] podem ter sido adicionadas ao t3, uma vez que a tabela estava vazia.</span><span class="sxs-lookup"><span data-stu-id="85ecc-158">Some rows [not in t1] may have been added to t3 since the table was emptied.</span></span> <span data-ttu-id="85ecc-159">Nenhuma linha foi adicionada à t1, pois a cópia era serializável.</span><span class="sxs-lookup"><span data-stu-id="85ecc-159">No rows were added to t1 as the copy was serializable.</span></span>  
  
 <span data-ttu-id="85ecc-160">Embora a leitura de t1 no fim da transação seja uma leitura confirmada sintaticamente, ela é eficazmente serializável, pois a mesma leitura foi executada anteriormente na transação no isolamento serializável: a capacidade de serialização garante que, se a leitura for executada em qualquer ponto posterior na transação, as mesmas linhas sejam retornadas.</span><span class="sxs-lookup"><span data-stu-id="85ecc-160">Although the read from t1 at the end of the transaction is syntactically read committed, it is effectively serializable, because the same read was performed earlier in the transaction under serializable isolation: serializability guarantees that if the read is performed at any later point in the transaction, the same rows are returned.</span></span>  
  
## <a name="cross-container-transactions-and-isolation-levels"></a><span data-ttu-id="85ecc-161">Transações entre contêineres e níveis de isolamento</span><span class="sxs-lookup"><span data-stu-id="85ecc-161">Cross-Container Transactions and Isolation Levels</span></span>  
 <span data-ttu-id="85ecc-162">Uma transação entre contêineres têm dois lados: um lado baseado em disco (para operações em tabelas baseadas em disco) e um lado com otimização de memória (para operações em tabelas com otimização de memória).</span><span class="sxs-lookup"><span data-stu-id="85ecc-162">A cross-container transaction can be seen as having two sides: a disk-based side (for operations on disk-based tables) and a memory-optimized side (for operations on memory-optimized tables).</span></span> <span data-ttu-id="85ecc-163">Esses dois lados podem ter diferentes níveis de isolamento.</span><span class="sxs-lookup"><span data-stu-id="85ecc-163">These two sides may have different isolation levels.</span></span> <span data-ttu-id="85ecc-164">Na verdade, as operações de leitura individuais em cada lado podem ter níveis de isolamento diferentes.</span><span class="sxs-lookup"><span data-stu-id="85ecc-164">In fact, individual read operations on each side may have different isolation levels.</span></span>  
  
 <span data-ttu-id="85ecc-165">O lado baseado em disco de uma determinada transação T atingirá um determinado nível de isolamento X se uma das seguintes condições for atendida:</span><span class="sxs-lookup"><span data-stu-id="85ecc-165">The disk-based side of a given transaction T reaches a certain isolation level X if one of the following conditions is met:</span></span>  
  
-   <span data-ttu-id="85ecc-166">Ele começa em X. Ou seja, o padrão da sessão era X, porque você executou `SET TRANSACTION ISOLATION LEVEL` ou é o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] padrão.</span><span class="sxs-lookup"><span data-stu-id="85ecc-166">It starts in X. That is, the session default was X, either because you executed `SET TRANSACTION ISOLATION LEVEL`, or it is the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] default.</span></span>  
  
-   <span data-ttu-id="85ecc-167">Durante a transação, o nível de isolamento padrão foi alterado para X usando `SET TRANSACTION ISOLATION LEVEL`.</span><span class="sxs-lookup"><span data-stu-id="85ecc-167">During the transaction, the default isolation level is changed to X using `SET TRANSACTION ISOLATION LEVEL`.</span></span>  
  
-   <span data-ttu-id="85ecc-168">Uma operação de leitura em uma tabela com base em disco é executada no nível de isolamento X usando a sintaxe `WITH (X)`.</span><span class="sxs-lookup"><span data-stu-id="85ecc-168">A read operation on a disk-based table is executed under isolation level X, using the syntax `WITH (X)`.</span></span>  
  
 <span data-ttu-id="85ecc-169">O lado com otimização de memória T atingirá um nível de isolamento Y se, durante a execução de T, qualquer operação de leitura em uma tabela com otimização de memória ou qualquer procedimento armazenado compilado nativamente for executado no nível de isolamento Y.</span><span class="sxs-lookup"><span data-stu-id="85ecc-169">The memory-optimized side of T reaches an isolation level Y if during execution of T, any read operation on a memory-optimized table or any natively compiled stored procedure is executed under isolation level Y.</span></span>  
  
 <span data-ttu-id="85ecc-170">Considere a seguinte transação como um exemplo.</span><span class="sxs-lookup"><span data-stu-id="85ecc-170">Consider the following transaction as an example.</span></span> <span data-ttu-id="85ecc-171">Aqui, t1 e t2 são tabelas baseadas em disco, e t3 e t4 são tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="85ecc-171">Here, t1 and t2 are disk-based tables and t3 and t4 are memory-optimized tables.</span></span>  
  
 <span data-ttu-id="85ecc-172">O lado baseado em disco da transação atinge o nível de isolamento de leitura confirmada, pois ela é iniciada nesse nível.</span><span class="sxs-lookup"><span data-stu-id="85ecc-172">The disk-based side of the transaction reaches the isolation level read committed, because it starts in that level.</span></span> <span data-ttu-id="85ecc-173">O lado baseado em disco também atinge o nível de leitura repetida, pois a primeira operação de leitura é executada nesse nível de isolamento.</span><span class="sxs-lookup"><span data-stu-id="85ecc-173">The disk-based side also reaches repeatable read, because the first read operation is executed under that isolation level.</span></span> <span data-ttu-id="85ecc-174">A exclusão no fim da transação é executada no nível de isolamento de leitura confirmada e, desse modo, não introduz um novo nível de isolamento.</span><span class="sxs-lookup"><span data-stu-id="85ecc-174">The delete at the end of the transaction is executed under read committed isolation level, and so does not introduce a new isolation level.</span></span>  
  
 <span data-ttu-id="85ecc-175">O lado com otimização de memória da transação pode alcançar um dos dois níveis: se condição1 for true, ele atingirá serializável, enquanto se for false, o lado com otimização de memória atingirá apenas o isolamento de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="85ecc-175">The memory-optimized side of the transaction can reach one of two levels: if condition1 is true, it reaches serializable, while if it is false, the memory-optimized side reaches only snapshot isolation.</span></span>  
  
```sql  
set transaction isolation level read committed  
go  
  
begin transaction  
  select * from t1 (repeatableread)  
  
  if condition1 begin  
    insert t3 select * from t4 (serializable)  
  end  
  else begin  
    insert t3 select * from t4 (snapshot)  
  end  
  
  delete from t1  
commit  
```  
  
### <a name="supported-isolation-levels-for-cross-container-transactions"></a><span data-ttu-id="85ecc-176">Níveis de isolamento com suporte para transações entre contêineres</span><span class="sxs-lookup"><span data-stu-id="85ecc-176">Supported Isolation Levels for Cross-Container Transactions</span></span>  
 <span data-ttu-id="85ecc-177">Há limitações sobre os níveis de isolamento usados com operações em tabelas com otimização de memória nas transações entre contêineres.</span><span class="sxs-lookup"><span data-stu-id="85ecc-177">There are limitations on the isolation levels used with operations on memory-optimized tables in cross-container transactions.</span></span>  
  
 <span data-ttu-id="85ecc-178">As tabelas com otimização de memória oferecem suporte aos níveis de isolamento SNAPSHOT, REPEATABLE READ e SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="85ecc-178">Memory-optimized tables support the isolation levels SNAPSHOT, REPEATABLE READ, and SERIALIZABLE.</span></span> <span data-ttu-id="85ecc-179">Para transações de confirmação automática, as tabelas com otimização de memória oferecem suporte ao nível de isolamento READ COMMITTED.</span><span class="sxs-lookup"><span data-stu-id="85ecc-179">For autocommit transactions, memory-optimized tables support the isolation level READ COMMITTED.</span></span>  
  
 <span data-ttu-id="85ecc-180">Os cenários a seguir têm suporte:</span><span class="sxs-lookup"><span data-stu-id="85ecc-180">The following scenarios are supported:</span></span>  
  
-   <span data-ttu-id="85ecc-181">As transações entre contêineres READ UNCOMMITTED, READ COMMITTED e READ_COMMITTED_SNAPSHOT podem acessar tabelas com otimização de memória no isolamento SNAPSHOT, REPEATABLE READ e SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="85ecc-181">READ UNCOMMITTED, READ COMMITTED, and READ_COMMITTED_SNAPSHOT cross-container transactions can access memory-optimized tables under SNAPSHOT, REPEATABLE READ, and SERIALIZABLE isolation.</span></span> <span data-ttu-id="85ecc-182">A garantia READ COMMITTED é mantida para a transação; todas as linhas lidas pela transação foram confirmadas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="85ecc-182">The READ COMMITTED guarantee holds for the transaction; all rows read by the transaction have been committed to the database.</span></span>  
  
-   <span data-ttu-id="85ecc-183">As transações REPEATABLE READ e SERIALIZABLE podem acessar tabelas com otimização de memória no isolamento SNAPSHOT.</span><span class="sxs-lookup"><span data-stu-id="85ecc-183">REPEATABLE READ and SERIALIZABLE transactions can access memory-optimized tables under SNAPSHOT isolation.</span></span>  
  
## <a name="read-only-cross-container-transactions"></a><span data-ttu-id="85ecc-184">Transações entre contêineres somente leitura</span><span class="sxs-lookup"><span data-stu-id="85ecc-184">Read-only Cross-Container Transactions</span></span>  
 <span data-ttu-id="85ecc-185">A maioria das transações somente leitura no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] é revertida no momento da confirmação.</span><span class="sxs-lookup"><span data-stu-id="85ecc-185">Most read-only transactions in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] are rolled back at commit time.</span></span> <span data-ttu-id="85ecc-186">Como não há nenhuma alteração a ser confirmada no banco de dados, o sistema simplesmente libera os recursos usados pela transação.</span><span class="sxs-lookup"><span data-stu-id="85ecc-186">Because there are no changes to commit to the database, the system simply frees the resources used by the transaction.</span></span> <span data-ttu-id="85ecc-187">Para transações baseadas em disco somente leitura, todos os bloqueios aplicados pela transação são liberados nesse momento.</span><span class="sxs-lookup"><span data-stu-id="85ecc-187">For read-only disk-based transactions, all locks taken by the transaction are released at this time.</span></span> <span data-ttu-id="85ecc-188">Para transações com otimização de memória somente leitura que abrangem uma única execução do procedimento originalmente compilado, nenhuma validação é executada.</span><span class="sxs-lookup"><span data-stu-id="85ecc-188">For read-only memory-optimized transactions that span a single natively compiled procedure execution, no validation is performed.</span></span>  
  
 <span data-ttu-id="85ecc-189">As transações somente leitura entre contêineres no modo de confirmação automática são simplesmente revertidas no fim da transação.</span><span class="sxs-lookup"><span data-stu-id="85ecc-189">Cross-container, read-only transactions in autocommit mode are simply rolled back at the end of the transaction.</span></span> <span data-ttu-id="85ecc-190">Nenhuma validação é executada.</span><span class="sxs-lookup"><span data-stu-id="85ecc-190">No validation is performed.</span></span>  
  
 <span data-ttu-id="85ecc-191">As transações somente leitura entre contêineres explícitas ou implícitas executarão a validação no momento da confirmação se a transação acessar tabelas com otimização de memória no isolamento REPEATABLE READ ou SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="85ecc-191">Explicit or implicit cross-container, read-only transactions perform validation at commit time if the transaction accesses memory-optimized tables under REPEATABLE READ or SERIALIZABLE isolation.</span></span> <span data-ttu-id="85ecc-192">Para obter detalhes sobre a validação, consulte a seção sobre detecção de conflito, validação e verificações de dependência de confirmação em [transações em tabelas com otimização de memória](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="85ecc-192">For details about validation see the section on Conflict Detection, Validation, and Commit Dependency Checks in [Transactions in Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85ecc-193">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="85ecc-193">See Also</span></span>  
 <span data-ttu-id="85ecc-194">[Noções básicas sobre transações em tabelas com otimização de memória](../../2014/database-engine/understanding-transactions-on-memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="85ecc-194">[Understanding Transactions on Memory-Optimized Tables](../../2014/database-engine/understanding-transactions-on-memory-optimized-tables.md) </span></span>  
 <span data-ttu-id="85ecc-195">[Diretrizes para níveis de isolamento de transação com tabelas com otimização de memória](../../2014/database-engine/guidelines-for-transaction-isolation-levels-with-memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="85ecc-195">[Guidelines for Transaction Isolation Levels with Memory-Optimized Tables](../../2014/database-engine/guidelines-for-transaction-isolation-levels-with-memory-optimized-tables.md) </span></span>  
 [<span data-ttu-id="85ecc-196">Diretrizes para lógica de repetição das transações em tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="85ecc-196">Guidelines for Retry Logic for Transactions on Memory-Optimized Tables</span></span>](../../2014/database-engine/guidelines-for-retry-logic-for-transactions-on-memory-optimized-tables.md)  
  
  
