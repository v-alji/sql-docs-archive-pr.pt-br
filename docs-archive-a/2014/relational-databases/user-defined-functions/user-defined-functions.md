---
title: Funções definidas pelo usuário | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- user-defined functions [SQL Server], components
- user-defined functions [SQL Server], about user-defined functions
ms.assetid: d7ddafab-f5a6-44b0-81d5-ba96425aada4
author: rothja
ms.author: jroth
ms.openlocfilehash: c7e4b1a77f2fe5a13e21d8b3fe59e37931669b30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568394"
---
# <a name="user-defined-functions"></a><span data-ttu-id="ddece-102">Funções definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="ddece-102">User-Defined Functions</span></span>
  <span data-ttu-id="ddece-103">Assim como as funções em linguagens de programação, as funções do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] definidas pelo usuário são rotinas que aceitam parâmetros, executam uma ação, como um cálculo complexo, e retornam o resultado dessa ação como um valor.</span><span class="sxs-lookup"><span data-stu-id="ddece-103">Like functions in programming languages, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user-defined functions are routines that accept parameters, perform an action, such as a complex calculation, and return the result of that action as a value.</span></span> <span data-ttu-id="ddece-104">O valor de retorno pode ser um único valor escalar ou um conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="ddece-104">The return value can either be a single scalar value or a result set.</span></span>  
  
 <span data-ttu-id="ddece-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="ddece-105">**In This Topic**</span></span>  
  
 [<span data-ttu-id="ddece-106">Benefícios da função definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="ddece-106">User-defined Function Benefits</span></span>](#Benefits)  
  
 [<span data-ttu-id="ddece-107">Tipos de funções</span><span class="sxs-lookup"><span data-stu-id="ddece-107">Types of Functions</span></span>](#FunctionTypes)  
  
 [<span data-ttu-id="ddece-108">Diretrizes</span><span class="sxs-lookup"><span data-stu-id="ddece-108">Guidelines</span></span>](#Guidelines)  
  
 [<span data-ttu-id="ddece-109">Instruções válidas em uma função</span><span class="sxs-lookup"><span data-stu-id="ddece-109">Valid Statements in a Function</span></span>](#ValidStatements)  
  
 [<span data-ttu-id="ddece-110">Funções associadas a esquema</span><span class="sxs-lookup"><span data-stu-id="ddece-110">Schema Bound Functions</span></span>](#SchemaBound)  
  
 [<span data-ttu-id="ddece-111">Especificando parâmetros</span><span class="sxs-lookup"><span data-stu-id="ddece-111">Specifying Parameters</span></span>](#Parameters)  
  
 [<span data-ttu-id="ddece-112">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="ddece-112">Related Tasks</span></span>](#Tasks)  
  
##  <a name="user-defined-function-benefits"></a><a name="Benefits"></a><span data-ttu-id="ddece-113">Benefícios da função definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="ddece-113">User-defined Function Benefits</span></span>  
 <span data-ttu-id="ddece-114">Os benefícios de usar funções definidas pelo usuário em [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] são:</span><span class="sxs-lookup"><span data-stu-id="ddece-114">The benefits of using user-defined functions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are:</span></span>  
  
-   <span data-ttu-id="ddece-115">Eles permitem programação modular.</span><span class="sxs-lookup"><span data-stu-id="ddece-115">They allow modular programming.</span></span>  
  
     <span data-ttu-id="ddece-116">Você pode criar a função uma vez, armazená-la no banco de dados e chamá-la quantas vezes quiser em seu programa.</span><span class="sxs-lookup"><span data-stu-id="ddece-116">You can create the function once, store it in the database, and call it any number of times in your program.</span></span> <span data-ttu-id="ddece-117">Funções definidas pelo usuário podem ser modificadas independentemente do código-fonte do programa.</span><span class="sxs-lookup"><span data-stu-id="ddece-117">User-defined functions can be modified independently of the program source code.</span></span>  
  
-   <span data-ttu-id="ddece-118">Elas permitem execução mais rápida.</span><span class="sxs-lookup"><span data-stu-id="ddece-118">They allow faster execution.</span></span>  
  
     <span data-ttu-id="ddece-119">Semelhantemente aos procedimentos armazenados, [!INCLUDE[tsql](../../includes/tsql-md.md)] as funções definidas pelo usuário reduzem o custo de compilação do código [!INCLUDE[tsql](../../includes/tsql-md.md)] colocando os planos em cache e reusando-os para execuções repetidas.</span><span class="sxs-lookup"><span data-stu-id="ddece-119">Similar to stored procedures, [!INCLUDE[tsql](../../includes/tsql-md.md)] user-defined functions reduce the compilation cost of [!INCLUDE[tsql](../../includes/tsql-md.md)] code by caching the plans and reusing them for repeated executions.</span></span> <span data-ttu-id="ddece-120">Isso significa que a função definida pelo usuário não precisa ser reanalisada e reotimizada em cada utilização resultando em tempos de execução mais rápidos.</span><span class="sxs-lookup"><span data-stu-id="ddece-120">This means the user-defined function does not need to be reparsed and reoptimized with each use resulting in much faster execution times.</span></span>  
  
     <span data-ttu-id="ddece-121">As funções CLR oferecem uma vantagem de desempenho significativa sobre funções [!INCLUDE[tsql](../../includes/tsql-md.md)] para tarefas de computação, manipulação de cadeias de caracteres e lógica de negócios.</span><span class="sxs-lookup"><span data-stu-id="ddece-121">CLR functions offer significant performance advantage over [!INCLUDE[tsql](../../includes/tsql-md.md)] functions for computational tasks, string manipulation, and business logic.</span></span> <span data-ttu-id="ddece-122">As funções [!INCLUDE[tsql](../../includes/tsql-md.md)] são mais adequadas à lógica intensiva de acesso a dados.</span><span class="sxs-lookup"><span data-stu-id="ddece-122">[!INCLUDE[tsql](../../includes/tsql-md.md)] functions are better suited for data-access intensive logic.</span></span>  
  
-   <span data-ttu-id="ddece-123">Eles podem reduzir o tráfego de rede.</span><span class="sxs-lookup"><span data-stu-id="ddece-123">They can reduce network traffic.</span></span>  
  
     <span data-ttu-id="ddece-124">Uma operação que filtra dados com base em alguma restrição complexa que não pode ser expressa em uma única expressão escalar pode ser expressa como uma função.</span><span class="sxs-lookup"><span data-stu-id="ddece-124">An operation that filters data based on some complex constraint that cannot be expressed in a single scalar expression can be expressed as a function.</span></span> <span data-ttu-id="ddece-125">Em seguida, a função pode ser invocada na cláusula WHERE para reduzir o número ou linhas enviadas ao cliente.</span><span class="sxs-lookup"><span data-stu-id="ddece-125">The function can then invoked in the WHERE clause to reduce the number or rows sent to the client.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ddece-126">As funções definidas pelo usuário [!INCLUDE[tsql](../../includes/tsql-md.md)] em consultas só podem ser executadas em um único thread (plano de execução serial).</span><span class="sxs-lookup"><span data-stu-id="ddece-126">[!INCLUDE[tsql](../../includes/tsql-md.md)] user-defined functions in queries can only be executed on a single thread (serial execution plan).</span></span>  
  
##  <a name="types-of-functions"></a><a name="FunctionTypes"></a><span data-ttu-id="ddece-127">Tipos de funções</span><span class="sxs-lookup"><span data-stu-id="ddece-127">Types of Functions</span></span>  
 <span data-ttu-id="ddece-128">Função escalar</span><span class="sxs-lookup"><span data-stu-id="ddece-128">Scalar Function</span></span>  
 <span data-ttu-id="ddece-129">As funções escalares definidas pelo usuário retornam um valor único de dados do tipo definido na cláusula RETURNS.</span><span class="sxs-lookup"><span data-stu-id="ddece-129">User-defined scalar functions return a single data value of the type defined in the RETURNS clause.</span></span> <span data-ttu-id="ddece-130">Para uma função escalar embutida, não há um corpo de função; o valor escalar é o resultado de uma única instrução.</span><span class="sxs-lookup"><span data-stu-id="ddece-130">For an inline scalar function, there is no function body; the scalar value is the result of a single statement.</span></span> <span data-ttu-id="ddece-131">Para uma função escalar de várias instruções, o corpo da função, definido em um bloco BEGIN...END, contém uma série de instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] , que retornam o valor único.</span><span class="sxs-lookup"><span data-stu-id="ddece-131">For a multistatement scalar function, the function body, defined in a BEGIN...END block, contains a series of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that return the single value.</span></span> <span data-ttu-id="ddece-132">O tipo de retorno pode ser qualquer tipo de dados, exceto `text`, `ntext`, `image`, `cursor`e `timestamp`.</span><span class="sxs-lookup"><span data-stu-id="ddece-132">The return type can be any data type except `text`, `ntext`, `image`, `cursor`, and `timestamp`.</span></span>  
  
 <span data-ttu-id="ddece-133">Funções com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="ddece-133">Table-Valued Functions</span></span>  
 <span data-ttu-id="ddece-134">As funções com valor de tabela definidas pelo usuário retornam um tipo de dados `table`.</span><span class="sxs-lookup"><span data-stu-id="ddece-134">User-defined table-valued functions return a `table` data type.</span></span> <span data-ttu-id="ddece-135">Para uma função com valor de tabela embutida, não há um corpo de função; a tabela é o conjunto de resultados de uma única instrução SELECT.</span><span class="sxs-lookup"><span data-stu-id="ddece-135">For an inline table-valued function, there is no function body; the table is the result set of a single SELECT statement.</span></span>  
  
 <span data-ttu-id="ddece-136">Funções do sistema</span><span class="sxs-lookup"><span data-stu-id="ddece-136">System Functions</span></span>  
 <span data-ttu-id="ddece-137">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fornece muitas funções de sistema que você pode usar para executar uma variedade de operações.</span><span class="sxs-lookup"><span data-stu-id="ddece-137">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides many system functions that you can use to perform a variety of operations.</span></span> <span data-ttu-id="ddece-138">Elas não podem ser modificadas.</span><span class="sxs-lookup"><span data-stu-id="ddece-138">They cannot be modified.</span></span> <span data-ttu-id="ddece-139">Para obter mais informações, consulte [Funções internas &#40;Transact-SQL&#41;](/sql/t-sql/functions/functions), [Funções armazenadas do sistema &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/system-functions-for-transact-sql) e [Exibições e funções de gerenciamento dinâmico &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/system-dynamic-management-views).</span><span class="sxs-lookup"><span data-stu-id="ddece-139">For more information, see [Built-in Functions &#40;Transact-SQL&#41;](/sql/t-sql/functions/functions), [System Stored Functions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/system-functions-for-transact-sql), and [Dynamic Management Views and Functions &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/system-dynamic-management-views).</span></span>  
  
##  <a name="guidelines"></a><a name="Guidelines"></a> <span data-ttu-id="ddece-140">Diretrizes</span><span class="sxs-lookup"><span data-stu-id="ddece-140">Guidelines</span></span>  
 <span data-ttu-id="ddece-141">Erros de [!INCLUDE[tsql](../../includes/tsql-md.md)] que levam ao cancelamento de uma instrução e continuam com a instrução seguinte no módulo (como gatilhos ou procedimentos armazenados) tratados de modo diferente em uma função.</span><span class="sxs-lookup"><span data-stu-id="ddece-141">[!INCLUDE[tsql](../../includes/tsql-md.md)] errors that cause a statement to be canceled and continue with the next statement in the module (such as triggers or stored procedures) are treated differently inside a function.</span></span> <span data-ttu-id="ddece-142">Nas funções, esses erros fazem com que a execução da função seja interrompida.</span><span class="sxs-lookup"><span data-stu-id="ddece-142">In functions, such errors cause the execution of the function to stop.</span></span> <span data-ttu-id="ddece-143">Em troca, isso faz com que a instrução que chamou a função seja cancelada.</span><span class="sxs-lookup"><span data-stu-id="ddece-143">This in turn causes the statement that invoked the function to be canceled.</span></span>  
  
 <span data-ttu-id="ddece-144">As instruções em um bloco BEGIN... END não podem ter nenhum efeito colateral.</span><span class="sxs-lookup"><span data-stu-id="ddece-144">The statements in a BEGIN...END block cannot have any side effects.</span></span> <span data-ttu-id="ddece-145">Os efeitos colaterais da função são as alterações permanentes realizada no estado de um recurso que tem um escopo fora da função como uma modificação em uma tabela do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ddece-145">Function side effects are any permanent changes to the state of a resource that has a scope outside the function such as a modification to a database table.</span></span> <span data-ttu-id="ddece-146">As únicas alterações que podem ser feitas pelas instruções na função são alterações em objetos locais à função, como cursores ou variáveis locais.</span><span class="sxs-lookup"><span data-stu-id="ddece-146">The only changes that can be made by the statements in the function are changes to objects local to the function, such as local cursors or variables.</span></span> <span data-ttu-id="ddece-147">As modificações em tabelas de banco de dados, operações em cursores que não são locais à função, envio de e-mail, tentativa de modificação em catálogo e geração de um conjunto de resultados retornados ao usuário são exemplos de ações que não devem ser realizadas em uma função.</span><span class="sxs-lookup"><span data-stu-id="ddece-147">Modifications to database tables, operations on cursors that are not local to the function, sending e-mail, attempting a catalog modification, and generating a result set that is returned to the user are examples of actions that cannot be performed in a function.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ddece-148">Se a instrução CREATE FUNCTION produzir efeitos colaterais contra os recursos que não existem quanto a instrução CREATE FUNCTION é emitida, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executa a instrução.</span><span class="sxs-lookup"><span data-stu-id="ddece-148">If a CREATE FUNCTION statement produces side effects against resources that do not exist when the CREATE FUNCTION statement is issued, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executes the statement.</span></span> <span data-ttu-id="ddece-149">Porém, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não executa a função quando é chamada.</span><span class="sxs-lookup"><span data-stu-id="ddece-149">However, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not execute the function when it is invoked.</span></span>  
  
 <span data-ttu-id="ddece-150">O número de vezes em que uma função especificada em uma consulta é realmente executada pode variar entre os planos de execução desenvolvidos pelo otimizador.</span><span class="sxs-lookup"><span data-stu-id="ddece-150">The number of times that a function specified in a query is actually executed can vary between execution plans built by the optimizer.</span></span> <span data-ttu-id="ddece-151">Um exemplo é a função chamada por uma subconsulta em uma cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="ddece-151">An example is a function invoked by a subquery in a WHERE clause.</span></span> <span data-ttu-id="ddece-152">O número de vezes em que a subconsulta e sua função são executadas pode variar com os caminhos de acesso diferentes escolhidos pelo otimizador.</span><span class="sxs-lookup"><span data-stu-id="ddece-152">The number of times the subquery and its function is executed can vary with different access paths chosen by the optimizer.</span></span>  
  
##  <a name="valid-statements-in-a-function"></a><a name="ValidStatements"></a><span data-ttu-id="ddece-153">Instruções válidas em uma função</span><span class="sxs-lookup"><span data-stu-id="ddece-153">Valid Statements in a Function</span></span>  
 <span data-ttu-id="ddece-154">Os tipos de instruções que são válidos em uma função incluem:</span><span class="sxs-lookup"><span data-stu-id="ddece-154">The types of statements that are valid in a function include:</span></span>  
  
-   <span data-ttu-id="ddece-155">As instruções DECLARE podem ser usadas para definir variáveis de dados e cursores que são locais à função.</span><span class="sxs-lookup"><span data-stu-id="ddece-155">DECLARE statements can be used to define data variables and cursors that are local to the function.</span></span>  
  
-   <span data-ttu-id="ddece-156">A atribuição de valores a objetos locais à função, como o uso de SET para atribuir valores para escalar e para as variáveis locais à tabela.</span><span class="sxs-lookup"><span data-stu-id="ddece-156">Assignments of values to objects local to the function, such as using SET to assign values to scalar and table local variables.</span></span>  
  
-   <span data-ttu-id="ddece-157">As operações de cursor que referenciam cursores locais são declaradas, abertas, fechadas e desalocadas na função.</span><span class="sxs-lookup"><span data-stu-id="ddece-157">Cursor operations that reference local cursors that are declared, opened, closed, and deallocated in the function.</span></span> <span data-ttu-id="ddece-158">As instruções FETCH que retornam os dados aos clientes não são permitidas.</span><span class="sxs-lookup"><span data-stu-id="ddece-158">FETCH statements that return data to the client are not allowed.</span></span> <span data-ttu-id="ddece-159">Somente instruções FETCH que atribuem valores a variáveis locais usando a cláusula INTO são permitidas.</span><span class="sxs-lookup"><span data-stu-id="ddece-159">Only FETCH statements that assign values to local variables using the INTO clause are allowed.</span></span>  
  
-   <span data-ttu-id="ddece-160">Instruções de controle-de-fluxo exceto as instruções TRY ... CATCH.</span><span class="sxs-lookup"><span data-stu-id="ddece-160">Control-of-flow statements except TRY...CATCH statements.</span></span>  
  
-   <span data-ttu-id="ddece-161">Instruções SELECT com listas de seleção com expressões que atribuem valores às variáveis que são locais à função.</span><span class="sxs-lookup"><span data-stu-id="ddece-161">SELECT statements containing select lists with expressions that assign values to variables that are local to the function.</span></span>  
  
-   <span data-ttu-id="ddece-162">As instruções UPDATE, INSERT e DELETE que modificam variáveis de tabela que são locais à função.</span><span class="sxs-lookup"><span data-stu-id="ddece-162">UPDATE, INSERT, and DELETE statements modifying table variables that are local to the function.</span></span>  
  
-   <span data-ttu-id="ddece-163">Instruções EXECUTE que chamam um procedimento armazenado estendido.</span><span class="sxs-lookup"><span data-stu-id="ddece-163">EXECUTE statements calling an extended stored procedure.</span></span>  
  
### <a name="built-in-system-functions"></a><span data-ttu-id="ddece-164">Funções do sistema internas</span><span class="sxs-lookup"><span data-stu-id="ddece-164">Built-in System Functions</span></span>  
 <span data-ttu-id="ddece-165">As funções não determinísticas internas a seguir podem ser usadas nas funções definidas por usuário Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="ddece-165">The following nondeterministic built-in functions can be used in Transact-SQL user-defined functions.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ddece-166">CURRENT_TIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="ddece-166">CURRENT_TIMESTAMP</span></span>|<span data-ttu-id="ddece-167">@@MAX_CONNECTIONS</span><span class="sxs-lookup"><span data-stu-id="ddece-167">@@MAX_CONNECTIONS</span></span>|  
|<span data-ttu-id="ddece-168">GET_TRANSMISSION_STATUS</span><span class="sxs-lookup"><span data-stu-id="ddece-168">GET_TRANSMISSION_STATUS</span></span>|<span data-ttu-id="ddece-169">@@PACK_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="ddece-169">@@PACK_RECEIVED</span></span>|  
|<span data-ttu-id="ddece-170">GETDATE</span><span class="sxs-lookup"><span data-stu-id="ddece-170">GETDATE</span></span>|<span data-ttu-id="ddece-171">@@PACK_SENT</span><span class="sxs-lookup"><span data-stu-id="ddece-171">@@PACK_SENT</span></span>|  
|<span data-ttu-id="ddece-172">GETUTCDATE</span><span class="sxs-lookup"><span data-stu-id="ddece-172">GETUTCDATE</span></span>|<span data-ttu-id="ddece-173">@@PACKET_ERRORS</span><span class="sxs-lookup"><span data-stu-id="ddece-173">@@PACKET_ERRORS</span></span>|  
|<span data-ttu-id="ddece-174">@@CONNECTIONS</span><span class="sxs-lookup"><span data-stu-id="ddece-174">@@CONNECTIONS</span></span>|<span data-ttu-id="ddece-175">@@TIMETICKS</span><span class="sxs-lookup"><span data-stu-id="ddece-175">@@TIMETICKS</span></span>|  
|<span data-ttu-id="ddece-176">@@CPU_BUSY</span><span class="sxs-lookup"><span data-stu-id="ddece-176">@@CPU_BUSY</span></span>|<span data-ttu-id="ddece-177">@@TOTAL_ERRORS</span><span class="sxs-lookup"><span data-stu-id="ddece-177">@@TOTAL_ERRORS</span></span>|  
|<span data-ttu-id="ddece-178">@@DBTS</span><span class="sxs-lookup"><span data-stu-id="ddece-178">@@DBTS</span></span>|<span data-ttu-id="ddece-179">@@TOTAL_READ</span><span class="sxs-lookup"><span data-stu-id="ddece-179">@@TOTAL_READ</span></span>|  
|<span data-ttu-id="ddece-180">@@IDLE</span><span class="sxs-lookup"><span data-stu-id="ddece-180">@@IDLE</span></span>|<span data-ttu-id="ddece-181">@@TOTAL_WRITE</span><span class="sxs-lookup"><span data-stu-id="ddece-181">@@TOTAL_WRITE</span></span>|  
|<span data-ttu-id="ddece-182">@@IO_BUSY</span><span class="sxs-lookup"><span data-stu-id="ddece-182">@@IO_BUSY</span></span>||  
  
 <span data-ttu-id="ddece-183">As funções não determinísticas internas a seguir não podem ser usadas nas funções definidas pelo usuário Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="ddece-183">The following nondeterministic built-in functions cannot be used in Transact-SQL user-defined functions.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ddece-184">NEWID</span><span class="sxs-lookup"><span data-stu-id="ddece-184">NEWID</span></span>|<span data-ttu-id="ddece-185">RAND</span><span class="sxs-lookup"><span data-stu-id="ddece-185">RAND</span></span>|  
|<span data-ttu-id="ddece-186">NEWSEQUENTIALID</span><span class="sxs-lookup"><span data-stu-id="ddece-186">NEWSEQUENTIALID</span></span>|<span data-ttu-id="ddece-187">TEXTPTR</span><span class="sxs-lookup"><span data-stu-id="ddece-187">TEXTPTR</span></span>|  
  
 <span data-ttu-id="ddece-188">Para obter uma lista das funções internas do sistema determinísticas e não determinísticas, consulte [Funções determinísticas e não determinísticas](../user-defined-functions/deterministic-and-nondeterministic-functions.md).</span><span class="sxs-lookup"><span data-stu-id="ddece-188">For a list of deterministic and nondeterministic built-in system functions, see [Deterministic and Nondeterministic Functions](../user-defined-functions/deterministic-and-nondeterministic-functions.md).</span></span>  
  
##  <a name="schema-bound-functions"></a><a name="SchemaBound"></a><span data-ttu-id="ddece-189">Funções associadas a esquema</span><span class="sxs-lookup"><span data-stu-id="ddece-189">Schema-Bound Functions</span></span>  
 <span data-ttu-id="ddece-190">CREATE FUNCTION dá suporte à cláusula SCHEMABINDING que associa a função ao esquema de qualquer objeto que ela referencia, como tabelas, exibições e demais funções definidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="ddece-190">CREATE FUNCTION supports a SCHEMABINDING clause that binds the function to the schema of any objects it references, such as tables, views, and other user-defined functions.</span></span> <span data-ttu-id="ddece-191">Uma tentativa para alterar ou descartar qualquer objeto referenciado por uma função associada a esquema falhará.</span><span class="sxs-lookup"><span data-stu-id="ddece-191">An attempt to alter or drop any object referenced by a schema-bound function fails.</span></span>  
  
 <span data-ttu-id="ddece-192">Essas condições devem ser cumpridas antes de especificar SCHEMABINDING em CREATE FUNCTION:</span><span class="sxs-lookup"><span data-stu-id="ddece-192">These conditions must be met before you can specify SCHEMABINDING in CREATE FUNCTION:</span></span>  
  
-   <span data-ttu-id="ddece-193">Todas as exibições e as funções definidas pelo usuário referenciadas pela função devem ser associadas a esquema.</span><span class="sxs-lookup"><span data-stu-id="ddece-193">All views and user-defined functions referenced by the function must be schema-bound.</span></span>  
  
-   <span data-ttu-id="ddece-194">Todos os objetos referenciados pela função devem estar no mesmo banco de dados da função.</span><span class="sxs-lookup"><span data-stu-id="ddece-194">All objects referenced by the function must be in the same database as the function.</span></span> <span data-ttu-id="ddece-195">Os objetos devem ser referenciados usando nomes de uma única parte ou nomes de duas partes.</span><span class="sxs-lookup"><span data-stu-id="ddece-195">The objects must be referenced using either one-part or two-part names.</span></span>  
  
-   <span data-ttu-id="ddece-196">Você deve ter permissão REFERENCES em todos os objetos (tabelas, exibições e funções definidas pelo usuário) referenciados na função.</span><span class="sxs-lookup"><span data-stu-id="ddece-196">You must have REFERENCES permission on all objects (tables, views, and user-defined functions) referenced in the function.</span></span>  
  
 <span data-ttu-id="ddece-197">Você pode usar ALTER FUNCTION para remover a associação a esquema.</span><span class="sxs-lookup"><span data-stu-id="ddece-197">You can use ALTER FUNCTION to remove the schema binding.</span></span> <span data-ttu-id="ddece-198">A instrução ALTER FUNCTION deve redefinir a função sem especificar WITH SCHEMABINDING.</span><span class="sxs-lookup"><span data-stu-id="ddece-198">The ALTER FUNCTION statement should redefine the function without specifying WITH SCHEMABINDING.</span></span>  
  
##  <a name="specifying-parameters"></a><a name="Parameters"></a><span data-ttu-id="ddece-199">Especificando parâmetros</span><span class="sxs-lookup"><span data-stu-id="ddece-199">Specifying Parameters</span></span>  
 <span data-ttu-id="ddece-200">Uma função definida pelo usuário usa parâmetros de entrada zero ou mais e retorna um valor escalar ou uma tabela.</span><span class="sxs-lookup"><span data-stu-id="ddece-200">A user-defined function takes zero or more input parameters and returns either a scalar value or a table.</span></span> <span data-ttu-id="ddece-201">A função pode ter um máximo de 1024 parâmetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="ddece-201">A function can have a maximum of 1024 input parameters.</span></span> <span data-ttu-id="ddece-202">Quando um parâmetro da função tiver um valor padrão, a palavra-chave DEFAULT deve ser especificada quando a função for chamada para obter o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="ddece-202">When a parameter of the function has a default value, the keyword DEFAULT must be specified when calling the function to get the default value.</span></span> <span data-ttu-id="ddece-203">Esse comportamento é diferente dos parâmetros com valores padrão nos procedimentos armazenados definidos pelo usuário nos quais a omissão de parâmetro também implica o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="ddece-203">This behavior is different from parameters with default values in user-defined stored procedures in which omitting the parameter also implies the default value.</span></span> <span data-ttu-id="ddece-204">Funções definidas pelo usuário não dão suporte aos parâmetros de saída.</span><span class="sxs-lookup"><span data-stu-id="ddece-204">User-defined functions do not support output parameters.</span></span>  
  
##  <a name="related-tasks"></a><a name="Tasks"></a> <span data-ttu-id="ddece-205">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="ddece-205">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ddece-206">**Descrição da tarefa**</span><span class="sxs-lookup"><span data-stu-id="ddece-206">**Task Description**</span></span>|<span data-ttu-id="ddece-207">**Tópico**</span><span class="sxs-lookup"><span data-stu-id="ddece-207">**Topic**</span></span>|  
|<span data-ttu-id="ddece-208">Descreve como criar uma função definida pelo usuário do Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ddece-208">Describes how to create a Transact-SQL user-defined function.</span></span>|[<span data-ttu-id="ddece-209">Criar funções definidas pelo usuário &#40;Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="ddece-209">Create User-defined Functions &#40;Database Engine&#41;</span></span>](../user-defined-functions/create-user-defined-functions-database-engine.md)|  
|<span data-ttu-id="ddece-210">Descreve como criar uma função CLR.</span><span class="sxs-lookup"><span data-stu-id="ddece-210">Describes how create a CLR function.</span></span>|[<span data-ttu-id="ddece-211">Criar funções CLR</span><span class="sxs-lookup"><span data-stu-id="ddece-211">Create CLR Functions</span></span>](../user-defined-functions/create-clr-functions.md)|  
|<span data-ttu-id="ddece-212">Descreve como criar uma função de agregação definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="ddece-212">Describes how to create a user-defined aggregate function</span></span>|[<span data-ttu-id="ddece-213">Criar agregações definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="ddece-213">Create User-defined Aggregates</span></span>](../user-defined-functions/create-user-defined-aggregates.md)|  
|<span data-ttu-id="ddece-214">Descreve como modificar uma função definida pelo usuário do Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ddece-214">Describes how to modify a Transact-SQL user-defined function.</span></span>|[<span data-ttu-id="ddece-215">Modificar funções definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="ddece-215">Modify User-defined Functions</span></span>](../user-defined-functions/user-defined-functions.md)|  
|<span data-ttu-id="ddece-216">Descreve como excluir uma função definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="ddece-216">Describes how to delete a user-defined function.</span></span>|[<span data-ttu-id="ddece-217">Excluir funções definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="ddece-217">Delete User-defined Functions</span></span>](../user-defined-functions/delete-user-defined-functions.md)|  
|<span data-ttu-id="ddece-218">Descreve como executar uma função definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="ddece-218">Describes how to execute a user-defined function.</span></span>|[<span data-ttu-id="ddece-219">Executar funções definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="ddece-219">Execute User-defined Functions</span></span>](../user-defined-functions/execute-user-defined-functions.md)|  
|<span data-ttu-id="ddece-220">Descreve como renomear uma função definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="ddece-220">Describes how to rename a user-defined function</span></span>|[<span data-ttu-id="ddece-221">Renomear funções definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="ddece-221">Rename User-defined Functions</span></span>](../user-defined-functions/rename-user-defined-functions.md)|  
|<span data-ttu-id="ddece-222">Descreve como exibir a definição de uma função definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="ddece-222">Describes how to view the definition of a user-defined function.</span></span>|[<span data-ttu-id="ddece-223">Exibir funções definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="ddece-223">View User-defined Functions</span></span>](view-user-defined-functions.md)|  
  
  