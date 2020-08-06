---
title: Construções com suporte em procedimentos armazenados compilados nativamente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 05515013-28b5-4ccf-9a54-ae861448945b
author: rothja
ms.author: jroth
ms.openlocfilehash: 65e6e794c5858a68c4b2a9b298513911b487cf52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583055"
---
# <a name="supported-constructs-in-natively-compiled-stored-procedures"></a><span data-ttu-id="d359f-102">Construções com suporte nos procedimentos armazenados compilados de modo nativo</span><span class="sxs-lookup"><span data-stu-id="d359f-102">Supported Constructs in Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="d359f-103">Este tópico contém uma lista de recursos com suporte para procedimentos armazenados compilados nativamente ([criar procedimento &#40;&#41;Transact-SQL ](/sql/t-sql/statements/create-procedure-transact-sql)):</span><span class="sxs-lookup"><span data-stu-id="d359f-103">This topic contains a list of supported features for natively compiled stored procedures ([CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql)):</span></span>  
  
-   [<span data-ttu-id="d359f-104">Programação em procedimentos armazenados compilados nativamente</span><span class="sxs-lookup"><span data-stu-id="d359f-104">Programmability in Natively Compiled Stored Procedures</span></span>](#pncsp)  
  
-   [<span data-ttu-id="d359f-105">Operadores com suporte</span><span class="sxs-lookup"><span data-stu-id="d359f-105">Supported Operators</span></span>](#so)  
  
-   [<span data-ttu-id="d359f-106">Funções internas em procedimentos armazenados compilados nativamente</span><span class="sxs-lookup"><span data-stu-id="d359f-106">Built-in Functions in Natively Compiled Stored Procedures</span></span>](#bfncsp)  
  
-   [<span data-ttu-id="d359f-107">Área da superfície de consulta em procedimentos armazenados compilados nativamente</span><span class="sxs-lookup"><span data-stu-id="d359f-107">Query Surface Area in Natively Compiled Stored Procedures</span></span>](#qsancsp)  
  
-   [<span data-ttu-id="d359f-108">Auditoria</span><span class="sxs-lookup"><span data-stu-id="d359f-108">Auditing</span></span>](#auditing)  
  
-   [<span data-ttu-id="d359f-109">Dicas de tabela, consulta e junção</span><span class="sxs-lookup"><span data-stu-id="d359f-109">Table, Query, and Join Hints</span></span>](#tqh)  
  
-   [<span data-ttu-id="d359f-110">Limitações na classificação</span><span class="sxs-lookup"><span data-stu-id="d359f-110">Limitations on Sorting</span></span>](#los)  
  
 <span data-ttu-id="d359f-111">Para obter informações sobre os tipos de dados suportados em procedimentos armazenados compilados de modo nativo, consulte [Supported Data Types](supported-data-types-for-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="d359f-111">For information on data types supported in natively compiled stored procedures, see [Supported Data Types](supported-data-types-for-in-memory-oltp.md).</span></span>  
  
 <span data-ttu-id="d359f-112">Para obter informações completas sobre construções sem suporte e sobre como resolver problemas de alguns recursos sem suporte em procedimentos armazenados compilados nativamente, consulte [Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="d359f-112">For complete information about unsupported constructs, and for information about how to work around some of the unsupported features in natively compiled stored procedures, see [Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md).</span></span> <span data-ttu-id="d359f-113">Para mais informações sobre os recursos sem suporte, veja [Constructos do Transact-SQL sem suporte no OLTP in-memory](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="d359f-113">For more information about unsupported features, see [Transact-SQL Constructs Not Supported by In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span></span>  
  
##  <a name="programmability-in-natively-compiled-stored-procedures"></a><a name="pncsp"></a><span data-ttu-id="d359f-114">Programação em procedimentos armazenados compilados nativamente</span><span class="sxs-lookup"><span data-stu-id="d359f-114">Programmability in Natively Compiled Stored Procedures</span></span>  
 <span data-ttu-id="d359f-115">Há suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d359f-115">The following are supported:</span></span>  
  
-   <span data-ttu-id="d359f-116">BEGIN ATOMIC (no nível externo do procedimento armazenado), LANGUAGE, ISOLATION LEVEL, DATEFORMAT e DATEFIRST.</span><span class="sxs-lookup"><span data-stu-id="d359f-116">BEGIN ATOMIC (at the outer level of the stored procedure), LANGUAGE, ISOLATION LEVEL, DATEFORMAT, and DATEFIRST.</span></span>  
  
-   <span data-ttu-id="d359f-117">Declaração de variáveis como NULL ou NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="d359f-117">Declaring variables as NULL or NOT NULL.</span></span> <span data-ttu-id="d359f-118">Se uma variável for declarada como NOT NULL, a declaração deverá ter um inicializador.</span><span class="sxs-lookup"><span data-stu-id="d359f-118">If a variable is declared as NOT NULL, the declaration must have an initializer.</span></span> <span data-ttu-id="d359f-119">Se uma variável não for declarada como NOT NULL, um inicializador será opcional.</span><span class="sxs-lookup"><span data-stu-id="d359f-119">If a variable is not declared as NOT NULL, an initializer is optional.</span></span>  
  
-   <span data-ttu-id="d359f-120">IF e WHILE</span><span class="sxs-lookup"><span data-stu-id="d359f-120">IF and WHILE</span></span>  
  
-   <span data-ttu-id="d359f-121">INSERT/UPDATE/DELETE</span><span class="sxs-lookup"><span data-stu-id="d359f-121">INSERT/UPDATE/DELETE</span></span>  
  
     <span data-ttu-id="d359f-122">Subconsultas têm suporte.</span><span class="sxs-lookup"><span data-stu-id="d359f-122">Subqueries are not supported.</span></span> <span data-ttu-id="d359f-123">Na cláusula WHERE ou HAVING, há suporte para AND e BETWEEN; não há suporte para OR, NOT e IN.</span><span class="sxs-lookup"><span data-stu-id="d359f-123">In the WHERE or HAVING clause, AND and BETWEEN are supported; OR, NOT, and IN are not supported.</span></span>  
  
-   <span data-ttu-id="d359f-124">Tipos de tabela com otimização de memória e variáveis de tabela.</span><span class="sxs-lookup"><span data-stu-id="d359f-124">Memory-optimized table types and table variables.</span></span>  
  
-   <span data-ttu-id="d359f-125">RETURN</span><span class="sxs-lookup"><span data-stu-id="d359f-125">RETURN</span></span>  
  
-   <span data-ttu-id="d359f-126">SELECT</span><span class="sxs-lookup"><span data-stu-id="d359f-126">SELECT</span></span>  
  
-   <span data-ttu-id="d359f-127">SET</span><span class="sxs-lookup"><span data-stu-id="d359f-127">SET</span></span>  
  
-   <span data-ttu-id="d359f-128">TRY/CATCH/THROW</span><span class="sxs-lookup"><span data-stu-id="d359f-128">TRY/CATCH/THROW</span></span>  
  
     <span data-ttu-id="d359f-129">Para otimizar o desempenho, use um único bloco TRY/CATCH para um procedimento armazenado originalmente compilado inteiro.</span><span class="sxs-lookup"><span data-stu-id="d359f-129">To optimize performance, use a single TRY/CATCH block for an entire natively compiled stored procedure.</span></span>  
  
##  <a name="supported-operators"></a><a name="so"></a> <span data-ttu-id="d359f-130">Operadores com suporte</span><span class="sxs-lookup"><span data-stu-id="d359f-130">Supported Operators</span></span>  
 <span data-ttu-id="d359f-131">Há suporte para os operadores que se seguem.</span><span class="sxs-lookup"><span data-stu-id="d359f-131">The following operators are supported.</span></span>  
  
-   <span data-ttu-id="d359f-132">[Operadores de comparação &#40;&#41;Transact-SQL](/sql/t-sql/language-elements/comparison-operators-transact-sql) (por exemplo, >, \<, > = e <=) têm suporte em condicionais (if, while).</span><span class="sxs-lookup"><span data-stu-id="d359f-132">[Comparison Operators &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/comparison-operators-transact-sql) (for example, >, \<, >=, and <=) are supported in conditionals (IF, WHILE).</span></span>  
  
-   <span data-ttu-id="d359f-133">Operadores unários (+, -).</span><span class="sxs-lookup"><span data-stu-id="d359f-133">Unary operators (+, -).</span></span>  
  
-   <span data-ttu-id="d359f-134">Operadores binários (\*, /, +, -, % (módulo)).</span><span class="sxs-lookup"><span data-stu-id="d359f-134">Binary operators (\*, /, +, -, % (modulo)).</span></span>  
  
     <span data-ttu-id="d359f-135">O operador de adição (+) tem suporte em números e cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="d359f-135">The plus operator (+) is supported on both numbers and strings.</span></span>  
  
-   <span data-ttu-id="d359f-136">Operadores lógicos (AND, OR, NOT).</span><span class="sxs-lookup"><span data-stu-id="d359f-136">Logical operators (AND, OR, NOT).</span></span> <span data-ttu-id="d359f-137">OR e NOT têm suporte em instruções IF e WHILE, mas não nas cláusulas WHERE ou HAVING.</span><span class="sxs-lookup"><span data-stu-id="d359f-137">OR and NOT are supported in IF and WHILE statements but not in WHERE or HAVING clauses.</span></span>  
  
-   <span data-ttu-id="d359f-138">Operadores bit a bit ~, &, |, e ^</span><span class="sxs-lookup"><span data-stu-id="d359f-138">Bitwise operators ~, &, |, and ^</span></span>  
  
##  <a name="built-in-functions-in-natively-compiled-stored-procedures"></a><a name="bfncsp"></a><span data-ttu-id="d359f-139">Funções internas em procedimentos armazenados compilados nativamente</span><span class="sxs-lookup"><span data-stu-id="d359f-139">Built-in Functions in Natively Compiled Stored Procedures</span></span>  
 <span data-ttu-id="d359f-140">As seguintes funções têm suporte em restrições padrão nas tabelas com otimização de memória e em procedimentos armazenados compilados nativamente.</span><span class="sxs-lookup"><span data-stu-id="d359f-140">The following functions are supported in default constraints on memory-optimized tables and in natively compiled stored procedures.</span></span>  
  
-   <span data-ttu-id="d359f-141">Funções matemáticas: ACOS, ASIN, ATAN, ATN2, COS, COT, DEGREES, EXP, LOG, LOG10, PI, POWER, RADIANS, RAND, SIN, SQRT, SQUARE e TAN</span><span class="sxs-lookup"><span data-stu-id="d359f-141">Math Functions: ACOS, ASIN, ATAN, ATN2, COS, COT, DEGREES, EXP, LOG, LOG10, PI, POWER, RADIANS, RAND, SIN, SQRT, SQUARE, and TAN</span></span>  
  
-   <span data-ttu-id="d359f-142">Funções de data: CURRENT_TIMESTAMP, DATEADD, DATEDIFF, DATEFROMPARTS, DATEPART, DATETIME2FROMPARTS, DATETIMEFROMPARTS, DAY, EOMONTH, GETDATE, GETUTCDATE, MONTH, SMALLDATETIMEFROMPARTS, SYSDATETIME, SYSUTCDATETIME e YEAR.</span><span class="sxs-lookup"><span data-stu-id="d359f-142">Date Functions: CURRENT_TIMESTAMP, DATEADD, DATEDIFF, DATEFROMPARTS, DATEPART, DATETIME2FROMPARTS, DATETIMEFROMPARTS, DAY, EOMONTH, GETDATE, GETUTCDATE, MONTH, SMALLDATETIMEFROMPARTS, SYSDATETIME, SYSUTCDATETIME, and YEAR.</span></span>  
  
-   <span data-ttu-id="d359f-143">Funções de cadeia de caracteres: LEN, LTRIM, RTRIM e SUBSTRING</span><span class="sxs-lookup"><span data-stu-id="d359f-143">String Functions: LEN, LTRIM, RTRIM, and SUBSTRING</span></span>  
  
-   <span data-ttu-id="d359f-144">Função de identidade: SCOPE_IDENTITY</span><span class="sxs-lookup"><span data-stu-id="d359f-144">Identity Function: SCOPE_IDENTITY</span></span>  
  
-   <span data-ttu-id="d359f-145">Funções NULL: ISNULL</span><span class="sxs-lookup"><span data-stu-id="d359f-145">NULL functions: ISNULL</span></span>  
  
-   <span data-ttu-id="d359f-146">Funções uniqueidentifier: NEWID e NEWSEQUENTIALID</span><span class="sxs-lookup"><span data-stu-id="d359f-146">Uniqueidentifier functions: NEWID and NEWSEQUENTIALID</span></span>  
  
-   <span data-ttu-id="d359f-147">Funções de erro: ERROR_LINE, ERROR_MESSAGE, ERROR_NUMBER, ERROR_PROCEDURE, ERROR_SEVERITY e ERROR_STATE</span><span class="sxs-lookup"><span data-stu-id="d359f-147">Error Functions: ERROR_LINE, ERROR_MESSAGE, ERROR_NUMBER, ERROR_PROCEDURE, ERROR_SEVERITY, and ERROR_STATE</span></span>  
  
-   <span data-ttu-id="d359f-148">Conversões: CAST e CONVERT.</span><span class="sxs-lookup"><span data-stu-id="d359f-148">Conversions: CAST and CONVERT.</span></span> <span data-ttu-id="d359f-149">Não há suporte para conversões entre cadeias de caracteres Unicode e não Unicode (n(var)char e (var)char).</span><span class="sxs-lookup"><span data-stu-id="d359f-149">Conversions between Unicode and non-Unicode character strings (n(var)char and (var)char) are not supported.</span></span>  
  
-   <span data-ttu-id="d359f-150">Funções do sistema: @@rowcount.</span><span class="sxs-lookup"><span data-stu-id="d359f-150">System Functions: @@rowcount.</span></span> <span data-ttu-id="d359f-151">As instruções dentro de procedimentos armazenados compilados nativamente atualizam @@rowcount e você pode usar @@rowcount em um procedimento armazenado compilado nativamente para determinar o número de linhas afetadas pela última instrução executada nesse procedimento armazenado compilado nativamente.</span><span class="sxs-lookup"><span data-stu-id="d359f-151">Statements inside natively compiled stored procedures update @@rowcount and you can use @@rowcount in a natively compiled stored procedure to determine the number of rows affected by the last statement executed within that natively compiled stored procedure.</span></span> <span data-ttu-id="d359f-152">No entanto, @@rowcount é redefinido como 0 no início e no final da execução de um procedimento armazenado compilado nativamente.</span><span class="sxs-lookup"><span data-stu-id="d359f-152">However, @@rowcount is reset to 0 at the start and at the end of the execution of a natively compiled stored procedure.</span></span>  
  
##  <a name="query-surface-area-in-natively-compiled-stored-procedures"></a><a name="qsancsp"></a><span data-ttu-id="d359f-153">Área de superfície de consulta em procedimentos armazenados compilados nativamente</span><span class="sxs-lookup"><span data-stu-id="d359f-153">Query Surface Area in Natively Compiled Stored Procedures</span></span>  
 <span data-ttu-id="d359f-154">Há suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d359f-154">The following are supported:</span></span>  
  
-   <span data-ttu-id="d359f-155">BETWEEN</span><span class="sxs-lookup"><span data-stu-id="d359f-155">BETWEEN</span></span>  
  
-   <span data-ttu-id="d359f-156">Aliases de nome de coluna (usando AS ou a sintaxe =).</span><span class="sxs-lookup"><span data-stu-id="d359f-156">Column name aliases (using either AS or = syntax).</span></span>  
  
-   <span data-ttu-id="d359f-157">CROSS JOIN e INNER JOIN, com suporte apenas com consultas SELECT.</span><span class="sxs-lookup"><span data-stu-id="d359f-157">CROSS JOIN and INNER JOIN, supported only with SELECT queries.</span></span>  
  
-   <span data-ttu-id="d359f-158">As expressões têm suporte na lista de seleção e [onde &#40;cláusula Transact-SQL&#41;](/sql/t-sql/queries/where-transact-sql) se eles usam um operador com suporte.</span><span class="sxs-lookup"><span data-stu-id="d359f-158">Expressions are supported in SELECT list and [WHERE &#40;Transact-SQL&#41;](/sql/t-sql/queries/where-transact-sql) clause if they use a supported operator.</span></span> <span data-ttu-id="d359f-159">Consulte [Supported Operators](#so) para obter a lista de operadores com suporte no momento.</span><span class="sxs-lookup"><span data-stu-id="d359f-159">See [Supported Operators](#so) for the list of currently-supported operators.</span></span>  
  
-   <span data-ttu-id="d359f-160">Predicado de filtro IS [NOT] NULL</span><span class="sxs-lookup"><span data-stu-id="d359f-160">Filter predicate IS [NOT] NULL</span></span>  
  
-   <span data-ttu-id="d359f-161">FROM \<memory optimized table></span><span class="sxs-lookup"><span data-stu-id="d359f-161">FROM \<memory optimized table></span></span>  
  
-   <span data-ttu-id="d359f-162">Há suporte para [GROUP BY &#40;&#41;Transact-SQL](/sql/t-sql/queries/select-group-by-transact-sql) , juntamente com as funções de agregação AVG, COUNT, COUNT_BIG, min, Max e Sum.</span><span class="sxs-lookup"><span data-stu-id="d359f-162">[GROUP BY &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-group-by-transact-sql) is supported, along with the aggregate functions AVG, COUNT, COUNT_BIG, MIN, MAX, and SUM.</span></span> <span data-ttu-id="d359f-163">MIN e MAX não têm suporte para os tipos nvarchar, char, varchar, varchar, varbinary e binary.</span><span class="sxs-lookup"><span data-stu-id="d359f-163">MIN and MAX are not supported for types nvarchar, char, varchar, varchar, varbinary, and binary.</span></span> <span data-ttu-id="d359f-164">A [cláusula ORDER BY &#40;&#41;Transact-SQL](/sql/t-sql/queries/select-order-by-clause-transact-sql) tem suporte com o [&#40;do transact-SQL&#41;](/sql/t-sql/queries/select-group-by-transact-sql) se uma expressão na lista ordenar por for exibida literalmente na lista Agrupar por.</span><span class="sxs-lookup"><span data-stu-id="d359f-164">[ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql) is supported with [GROUP BY &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-group-by-transact-sql) if an expression in the ORDER BY list appears verbatim in the GROUP BY list.</span></span> <span data-ttu-id="d359f-165">Por exemplo, GROUP BY + b ORDER BY a + b tem suporte, mas GROUP BY a, b ORDER BY a + b, não.</span><span class="sxs-lookup"><span data-stu-id="d359f-165">For example, GROUP BY a + b ORDER BY a + b is supported, but GROUP BY a, b ORDER BY a + b is not.</span></span>  
  
-   <span data-ttu-id="d359f-166">HAVING, sujeita às mesmas limitações de expressão da cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="d359f-166">HAVING, subject to the same expression limitations as the WHERE clause.</span></span>  
  
-   <span data-ttu-id="d359f-167">INSERT VALUES (uma linha por instrução) e INSERT SELECT</span><span class="sxs-lookup"><span data-stu-id="d359f-167">INSERT VALUES (one row per statement) and INSERT SELECT</span></span>  
  
-   <span data-ttu-id="d359f-168">ORDENAr por <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d359f-168">ORDER BY <sup>1</sup></span></span>  
  
-   <span data-ttu-id="d359f-169">Predicados que não fazem referência a uma coluna.</span><span class="sxs-lookup"><span data-stu-id="d359f-169">Predicates not referencing a column.</span></span>  
  
-   <span data-ttu-id="d359f-170">SELECT, UPDATE e DELETE</span><span class="sxs-lookup"><span data-stu-id="d359f-170">SELECT, UPDATE, and DELETE</span></span>  
  
-   <span data-ttu-id="d359f-171"><sup>1</sup> superior</span><span class="sxs-lookup"><span data-stu-id="d359f-171">TOP <sup>1</sup></span></span>  
  
-   <span data-ttu-id="d359f-172">Atribuição de variável na lista SELECT.</span><span class="sxs-lookup"><span data-stu-id="d359f-172">Variable assignment in the SELECT list.</span></span>  
  
-   <span data-ttu-id="d359f-173">ONDE... E</span><span class="sxs-lookup"><span data-stu-id="d359f-173">WHERE ... AND</span></span>  
  
 <span data-ttu-id="d359f-174"><sup>1</sup> order by e Top têm suporte em procedimentos armazenados compilados nativamente, com algumas restrições:</span><span class="sxs-lookup"><span data-stu-id="d359f-174"><sup>1</sup> ORDER BY and TOP are supported in natively compiled stored procedures, with some restrictions:</span></span>  
  
-   <span data-ttu-id="d359f-175">Não há suporte para `DISTINCT` na cláusula `SELECT` ou `ORDER BY`.</span><span class="sxs-lookup"><span data-stu-id="d359f-175">There is no support for `DISTINCT` in the `SELECT` or `ORDER BY` clause.</span></span>  
  
-   <span data-ttu-id="d359f-176">Não há suporte para `WITH TIES` ou `PERCENT` na cláusula `TOP`.</span><span class="sxs-lookup"><span data-stu-id="d359f-176">There is no support for `WITH TIES` or `PERCENT` in the `TOP` clause.</span></span>  
  
-   <span data-ttu-id="d359f-177">`TOP` combinado com `ORDER BY` não dá suporte a mais de 8.192 ao usar uma constante na cláusula `TOP`.</span><span class="sxs-lookup"><span data-stu-id="d359f-177">`TOP` combined with `ORDER BY` does not support more than 8,192 when using a constant in the `TOP` clause.</span></span> <span data-ttu-id="d359f-178">Esse limite poderá ser diminuído caso a consulta contenha junções ou funções de agregação.</span><span class="sxs-lookup"><span data-stu-id="d359f-178">This limit may be lowered in case the query contains joins or aggregate functions.</span></span> <span data-ttu-id="d359f-179">(Por exemplo, com uma junção (duas tabelas), o limite é 4.096 linhas.</span><span class="sxs-lookup"><span data-stu-id="d359f-179">(For example, with one join (two tables), the limit is 4,096 rows.</span></span> <span data-ttu-id="d359f-180">Com duas junções (três tabelas), o limite é 2.730 linhas.)</span><span class="sxs-lookup"><span data-stu-id="d359f-180">With two joins (three tables), the limit is 2,730 rows.)</span></span>  
  
     <span data-ttu-id="d359f-181">Você pode obter resultados maiores que 8.192 armazenando o número de linhas em uma variável:</span><span class="sxs-lookup"><span data-stu-id="d359f-181">You can obtain results greater than 8,192 by storing the number of rows in a variable:</span></span>  
  
    ```sql  
    DECLARE @v INT = 9000  
    SELECT TOP (@v) ... FROM ... ORDER BY ...  
    ```  
  
 <span data-ttu-id="d359f-182">No entanto, uma constante na cláusula `TOP` resulta em um desempenho melhor comparado a usar uma variável.</span><span class="sxs-lookup"><span data-stu-id="d359f-182">However, a constant in the `TOP` clause results in better performance compared to using a variable.</span></span>  
  
 <span data-ttu-id="d359f-183">Essas restrições não se aplicam ao acesso [!INCLUDE[tsql](../../includes/tsql-md.md)] interpretado em tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="d359f-183">These restrictions do not apply to interpreted [!INCLUDE[tsql](../../includes/tsql-md.md)] access on memory-optimized tables.</span></span>  
  
##  <a name="auditing"></a><a name="auditing"></a> <span data-ttu-id="d359f-184">Auditoria</span><span class="sxs-lookup"><span data-stu-id="d359f-184">Auditing</span></span>  
 <span data-ttu-id="d359f-185">A auditoria no nível de procedimento tem suporte em procedimentos armazenados compilados nativamente.</span><span class="sxs-lookup"><span data-stu-id="d359f-185">Procedure level auditing is supported in natively compiled stored procedures.</span></span> <span data-ttu-id="d359f-186">Não há suporte para a auditoria no nível da instrução.</span><span class="sxs-lookup"><span data-stu-id="d359f-186">Statement level auditing is not supported.</span></span>  
  
 <span data-ttu-id="d359f-187">Para obter mais informações sobre a auditoria, consulte [Criar uma especificação de auditoria de banco de dados e de servidor](../security/auditing/create-a-server-audit-and-database-audit-specification.md).</span><span class="sxs-lookup"><span data-stu-id="d359f-187">For more information about auditing, see [Create a Server Audit and Database Audit Specification](../security/auditing/create-a-server-audit-and-database-audit-specification.md).</span></span>  
  
##  <a name="table-query-and-join-hints"></a><a name="tqh"></a><span data-ttu-id="d359f-188">Dicas de tabela, consulta e junção</span><span class="sxs-lookup"><span data-stu-id="d359f-188">Table, Query, and Join Hints</span></span>  
 <span data-ttu-id="d359f-189">Há suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d359f-189">The following are supported:</span></span>  
  
-   <span data-ttu-id="d359f-190">As dicas INDEX, FORCESCAN e FORCESEEK, seja na sintaxe das dicas de tabela ou na [Cláusula OPTION &#40;Transact-SQL&#41;](/sql/t-sql/queries/option-clause-transact-sql) da consulta.</span><span class="sxs-lookup"><span data-stu-id="d359f-190">INDEX, FORCESCAN, and FORCESEEK hints, either in table hints syntax or in [OPTION Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/option-clause-transact-sql) of the query.</span></span>  
  
-   <span data-ttu-id="d359f-191">FORCE ORDER</span><span class="sxs-lookup"><span data-stu-id="d359f-191">FORCE ORDER</span></span>  
  
-   <span data-ttu-id="d359f-192">INNER LOOP JOIN</span><span class="sxs-lookup"><span data-stu-id="d359f-192">INNER LOOP JOIN</span></span>  
  
-   <span data-ttu-id="d359f-193">OPTIMIZE FOR</span><span class="sxs-lookup"><span data-stu-id="d359f-193">OPTIMIZE FOR</span></span>  
  
 <span data-ttu-id="d359f-194">Para obter mais informações, consulte [dicas &#40;&#41;Transact-SQL ](/sql/t-sql/queries/hints-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d359f-194">For more information, see [Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql).</span></span>  
  
##  <a name="limitations-on-sorting"></a><a name="los"></a> <span data-ttu-id="d359f-195">Limitações na classificação</span><span class="sxs-lookup"><span data-stu-id="d359f-195">Limitations on Sorting</span></span>  
 <span data-ttu-id="d359f-196">Você pode classificar maior que 8.000 linhas em uma consulta que usa [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) e uma [Cláusula ORDER BY &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d359f-196">You can sort greater than 8,000 rows in a query that uses [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) and an [ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql).</span></span> <span data-ttu-id="d359f-197">No entanto, sem a [Cláusula ORDER BY &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql), [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) pode classificar até 8.000 linhas (menos linhas se houver junções).</span><span class="sxs-lookup"><span data-stu-id="d359f-197">However, without [ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql), [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) can sort up to 8,000 rows (fewer rows if there are joins).</span></span>  
  
 <span data-ttu-id="d359f-198">Se sua consulta usar o operador [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) e uma [Cláusula ORDER BY &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql), você pode especificar até 8192 linhas para o operador TOP.</span><span class="sxs-lookup"><span data-stu-id="d359f-198">If your query uses both the [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) operator and an [ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql), you can specify up to 8192 rows for the TOP operator.</span></span> <span data-ttu-id="d359f-199">Se você especificar mais de 8192 linhas, receberá a mensagem de erro: **Msg 41398, Nível 16, Estado 1, Procedimento *\<procedureName>* , Linha *\<lineNumber>* O operador TOP pode retornar no máximo 8192 linhas; *\<number>* foi solicitado.**</span><span class="sxs-lookup"><span data-stu-id="d359f-199">If you specify more than 8192 rows you get the error message: **Msg 41398, Level 16, State 1, Procedure *\<procedureName>*, Line *\<lineNumber>* The TOP operator can return a maximum of 8192 rows; *\<number>* was requested.**</span></span>  
  
 <span data-ttu-id="d359f-200">Se você não tiver uma cláusula TOP, poderá classificar qualquer número de linhas com ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="d359f-200">If you do not have a TOP clause, you can sort any number of rows with ORDER BY.</span></span>  
  
 <span data-ttu-id="d359f-201">Se você não usar uma cláusula ORDER BY, poderá usar qualquer valor inteiro com o operador TOP.</span><span class="sxs-lookup"><span data-stu-id="d359f-201">If you do not use an ORDER BY clause, you can use any integer value with the TOP operator.</span></span>  
  
 <span data-ttu-id="d359f-202">Exemplo com TOP N = 8192: compila</span><span class="sxs-lookup"><span data-stu-id="d359f-202">Example with TOP N = 8192: Compiles</span></span>  
  
```sql  
CREATE PROCEDURE testTop  
WITH EXECUTE AS OWNER, SCHEMABINDING, NATIVE_COMPILATION  
  AS  
  BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
    SELECT TOP 8192 ShoppingCartId, CreatedDate, TotalPrice FROM dbo.ShoppingCart  
    ORDER BY ShoppingCartId DESC  
  END;  
GO  
```  
  
 <span data-ttu-id="d359f-203">Exemplo com TOP N > 8192: não compila.</span><span class="sxs-lookup"><span data-stu-id="d359f-203">Example with TOP N > 8192: Fails to compile.</span></span>  
  
```sql  
CREATE PROCEDURE testTop  
WITH EXECUTE AS OWNER, SCHEMABINDING, NATIVE_COMPILATION  
  AS  
  BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
    SELECT TOP 8193 ShoppingCartId, CreatedDate, TotalPrice FROM dbo.ShoppingCart  
    ORDER BY ShoppingCartId DESC  
  END;  
GO  
```  
  
 <span data-ttu-id="d359f-204">A limitação de 8192 linhas só se aplica a `TOP N` onde `N` é uma constante, como nos exemplos anteriores.</span><span class="sxs-lookup"><span data-stu-id="d359f-204">The 8192 row limitation only applies to `TOP N` where `N` is a constant, as in the preceding examples.</span></span>  <span data-ttu-id="d359f-205">Se você precisar de `N` maior que 8192, poderá atribuir o valor a uma variável e usar essa variável com `TOP`.</span><span class="sxs-lookup"><span data-stu-id="d359f-205">If you need `N` greater than 8192 you can assign the value to a variable and use that variable with `TOP`.</span></span>  
  
 <span data-ttu-id="d359f-206">Exemplo usando uma variável: compila</span><span class="sxs-lookup"><span data-stu-id="d359f-206">Example using a variable: Compiles</span></span>  
  
```sql  
CREATE PROCEDURE testTop  
WITH EXECUTE AS OWNER, SCHEMABINDING, NATIVE_COMPILATION  
  AS  
  BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
    DECLARE @v int = 8193   
    SELECT TOP (@v) ShoppingCartId, CreatedDate, TotalPrice FROM dbo.ShoppingCart  
    ORDER BY ShoppingCartId DESC  
  END;  
GO  
```  
  
 <span data-ttu-id="d359f-207">**Limitações nas linhas retornadas:** há dois casos em que isso pode, potencialmente, reduzir o número de linhas a serem retornadas pelo operador TOP:</span><span class="sxs-lookup"><span data-stu-id="d359f-207">**Limitations on rows returned:** There are two cases where that can potentially reduce the number of rows that can be returned by the TOP operator:</span></span>  
  
-   <span data-ttu-id="d359f-208">Uso de JOINs na consulta.</span><span class="sxs-lookup"><span data-stu-id="d359f-208">Using JOINs in the query.</span></span>  <span data-ttu-id="d359f-209">A influência de JOINs na limitação depende do plano de consulta.</span><span class="sxs-lookup"><span data-stu-id="d359f-209">The influence of JOINs on the limitation depends on the query plan.</span></span>  
  
-   <span data-ttu-id="d359f-210">Uso de funções de agregação ou de referências a funções de agregação na cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="d359f-210">Using aggregate functions or references to aggregate functions in the ORDER BY clause.</span></span>  
  
 <span data-ttu-id="d359f-211">A fórmula para calcular o pior caso de N com suporte em TOP N é: `N = floor ( 65536 / number_of_tables * 8 + total_size+of+aggs )`.</span><span class="sxs-lookup"><span data-stu-id="d359f-211">The formula to calculate a worst case maximum supported N in TOP N is: `N = floor ( 65536 / number_of_tables * 8 + total_size+of+aggs )`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d359f-212">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d359f-212">See Also</span></span>  
 <span data-ttu-id="d359f-213">[Procedimentos armazenados compilados nativamente](natively-compiled-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="d359f-213">[Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md) </span></span>  
 [<span data-ttu-id="d359f-214">Problemas de migração para procedimentos armazenados compilados nativamente</span><span class="sxs-lookup"><span data-stu-id="d359f-214">Migration Issues for Natively Compiled Stored Procedures</span></span>](migration-issues-for-natively-compiled-stored-procedures.md)  
  
  
