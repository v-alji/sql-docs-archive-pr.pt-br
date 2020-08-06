---
title: Sintaxe Transact-SQL com suporte do IntelliSense
ms.custom: seo-lt-2019
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- Transact-SQL IntelliSense
- IntelliSense [SQL Server], Transact-SQL syntax
ms.assetid: 194e8f4f-fd7e-4f32-a169-f23531128004
author: rothja
ms.author: jroth
ms.openlocfilehash: b3d34fc79dd7817e64b34b61083415477860ce97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681533"
---
# <a name="transact-sql-syntax-supported-by-intellisense"></a><span data-ttu-id="7ec65-102">Sintaxe Transact-SQL com suporte do IntelliSense</span><span class="sxs-lookup"><span data-stu-id="7ec65-102">Transact-SQL Syntax Supported by IntelliSense</span></span>
  <span data-ttu-id="7ec65-103">Este tópico descreve as instruções e os elementos de sintaxe [!INCLUDE[tsql](../../includes/tsql-md.md)] aos quais o IntelliSense dá suporte no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7ec65-103">This topic describes the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and syntax elements that are supported by IntelliSense in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="statements-supported-by-intellisense"></a><span data-ttu-id="7ec65-104">Instruções com suporte do IntelliSense</span><span class="sxs-lookup"><span data-stu-id="7ec65-104">Statements Supported by IntelliSense</span></span>  
 <span data-ttu-id="7ec65-105">No [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], o IntelliSense dá suporte apenas às instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] mais usadas.</span><span class="sxs-lookup"><span data-stu-id="7ec65-105">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], IntelliSense supports only the most commonly used [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="7ec65-106">Algumas condições gerais do Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] podem impedir que o IntelliSense funcione.</span><span class="sxs-lookup"><span data-stu-id="7ec65-106">Some general [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor conditions might prevent IntelliSense from functioning.</span></span> <span data-ttu-id="7ec65-107">Para obter mais informações, consulte [Solucionando problemas do IntelliSense &#40;SQL Server Management Studio&#41;](troubleshooting-intellisense.md).</span><span class="sxs-lookup"><span data-stu-id="7ec65-107">For more information, see [Troubleshooting IntelliSense &#40;SQL Server Management Studio&#41;](troubleshooting-intellisense.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7ec65-108">O IntelliSense não está disponível para objetos de banco de dados criptografados, como, por exemplo, procedimentos armazenados criptografados ou funções definidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="7ec65-108">IntelliSense is not available for encrypted database objects, such as encrypted stored procedures or user-defined functions.</span></span> <span data-ttu-id="7ec65-109">A ajuda de parâmetros e Informações Rápidas não estão disponíveis para os parâmetros de procedimentos armazenados estendidos e tipos definidos pelo usuário da Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="7ec65-109">Parameter help and Quick Info are not available for the parameters of extended stored procedures and CLR Integration user-defined types.</span></span>  
  
### <a name="select-statement"></a><span data-ttu-id="7ec65-110">Instrução SELECT</span><span class="sxs-lookup"><span data-stu-id="7ec65-110">SELECT Statement</span></span>  
 <span data-ttu-id="7ec65-111">O Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] dá suporte ao IntelliSense para os seguintes elementos de sintaxe na instrução SELECT:</span><span class="sxs-lookup"><span data-stu-id="7ec65-111">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor provides IntelliSense support for the following syntax elements in the SELECT statement:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7ec65-112">SELECT</span><span class="sxs-lookup"><span data-stu-id="7ec65-112">SELECT</span></span>|<span data-ttu-id="7ec65-113">WHERE</span><span class="sxs-lookup"><span data-stu-id="7ec65-113">WHERE</span></span>|  
|<span data-ttu-id="7ec65-114">FROM</span><span class="sxs-lookup"><span data-stu-id="7ec65-114">FROM</span></span>|<span data-ttu-id="7ec65-115">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="7ec65-115">ORDER BY</span></span>|  
|<span data-ttu-id="7ec65-116">HAVING</span><span class="sxs-lookup"><span data-stu-id="7ec65-116">HAVING</span></span>|<span data-ttu-id="7ec65-117">UNION</span><span class="sxs-lookup"><span data-stu-id="7ec65-117">UNION</span></span>|  
|<span data-ttu-id="7ec65-118">FOR</span><span class="sxs-lookup"><span data-stu-id="7ec65-118">FOR</span></span>|<span data-ttu-id="7ec65-119">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="7ec65-119">GROUP BY</span></span>|  
|<span data-ttu-id="7ec65-120">INÍCIO</span><span class="sxs-lookup"><span data-stu-id="7ec65-120">TOP</span></span>|<span data-ttu-id="7ec65-121">OPTION (dica)</span><span class="sxs-lookup"><span data-stu-id="7ec65-121">OPTION (hint)</span></span>|  
  
### <a name="additional-transact-sql-statements-that-are-supported"></a><span data-ttu-id="7ec65-122">Instruções Transact-SQL adicionais com suporte</span><span class="sxs-lookup"><span data-stu-id="7ec65-122">Additional Transact-SQL Statements That Are Supported</span></span>  
 <span data-ttu-id="7ec65-123">O Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] também dá suporte ao IntelliSense para instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] mostradas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="7ec65-123">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor also provides IntelliSense support for [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that are shown in the following table.</span></span>  
  
|<span data-ttu-id="7ec65-124">Instrução Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7ec65-124">Transact-SQL statement</span></span>|<span data-ttu-id="7ec65-125">Sintaxe com suporte</span><span class="sxs-lookup"><span data-stu-id="7ec65-125">Syntax supported</span></span>|  
|-----------------------------|----------------------|  
|[<span data-ttu-id="7ec65-126">INSERT</span><span class="sxs-lookup"><span data-stu-id="7ec65-126">INSERT</span></span>](/sql/t-sql/statements/insert-transact-sql)|<span data-ttu-id="7ec65-127">Toda a sintaxe, exceto a cláusula *execute_statement* .</span><span class="sxs-lookup"><span data-stu-id="7ec65-127">All syntax, except the *execute_statement* clause.</span></span>|  
|[<span data-ttu-id="7ec65-128">UPDATE</span><span class="sxs-lookup"><span data-stu-id="7ec65-128">UPDATE</span></span>](/sql/t-sql/queries/update-transact-sql)|<span data-ttu-id="7ec65-129">Toda a sintaxe.</span><span class="sxs-lookup"><span data-stu-id="7ec65-129">All syntax.</span></span>|  
|[<span data-ttu-id="7ec65-130">DELETE</span><span class="sxs-lookup"><span data-stu-id="7ec65-130">DELETE</span></span>](/sql/t-sql/statements/delete-transact-sql)|<span data-ttu-id="7ec65-131">Toda a sintaxe.</span><span class="sxs-lookup"><span data-stu-id="7ec65-131">All syntax.</span></span>|  
|[<span data-ttu-id="7ec65-132">Claro@local_variable</span><span class="sxs-lookup"><span data-stu-id="7ec65-132">DECLARE @local_variable</span></span>](/sql/t-sql/language-elements/declare-local-variable-transact-sql)|<span data-ttu-id="7ec65-133">Toda a sintaxe.</span><span class="sxs-lookup"><span data-stu-id="7ec65-133">All syntax.</span></span>|  
|[<span data-ttu-id="7ec65-134">Definição@local_variable</span><span class="sxs-lookup"><span data-stu-id="7ec65-134">SET @local_variable</span></span>](/sql/t-sql/language-elements/set-local-variable-transact-sql)|<span data-ttu-id="7ec65-135">Toda a sintaxe.</span><span class="sxs-lookup"><span data-stu-id="7ec65-135">All syntax.</span></span>|  
|[<span data-ttu-id="7ec65-136">Execute</span><span class="sxs-lookup"><span data-stu-id="7ec65-136">EXECUTE</span></span>](/sql/t-sql/language-elements/execute-transact-sql)|<span data-ttu-id="7ec65-137">Execução de procedimentos armazenados definidos pelo usuário, procedimentos armazenados do sistema, funções definidas pelo usuário e funções do sistema.</span><span class="sxs-lookup"><span data-stu-id="7ec65-137">Execution of user-defined stored procedures, system stored procedures, user-defined functions, and system functions.</span></span>|  
|[<span data-ttu-id="7ec65-138">CREATE TABLE</span><span class="sxs-lookup"><span data-stu-id="7ec65-138">CREATE TABLE</span></span>](/sql/t-sql/statements/create-table-transact-sql)|<span data-ttu-id="7ec65-139">Toda a sintaxe.</span><span class="sxs-lookup"><span data-stu-id="7ec65-139">All syntax.</span></span>|  
|[<span data-ttu-id="7ec65-140">CREATE VIEW</span><span class="sxs-lookup"><span data-stu-id="7ec65-140">CREATE VIEW</span></span>](/sql/t-sql/statements/create-view-transact-sql)|<span data-ttu-id="7ec65-141">Toda a sintaxe.</span><span class="sxs-lookup"><span data-stu-id="7ec65-141">All syntax.</span></span>|  
|[<span data-ttu-id="7ec65-142">CREATE PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="7ec65-142">CREATE PROCEDURE</span></span>](/sql/t-sql/statements/create-procedure-transact-sql)|<span data-ttu-id="7ec65-143">Toda a sintaxe, com as seguintes exceções:</span><span class="sxs-lookup"><span data-stu-id="7ec65-143">All syntax, with the following exceptions:</span></span><br /><br /> <span data-ttu-id="7ec65-144">Não há suporte do IntelliSense para a cláusula EXTERNAL NAME.</span><span class="sxs-lookup"><span data-stu-id="7ec65-144">There is no IntelliSense support for the EXTERNAL NAME clause.</span></span><br /><br /> <span data-ttu-id="7ec65-145">Na cláusula AS, o IntelliSense dá suporte apenas às instruções e à sintaxe listadas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="7ec65-145">In the AS clause, IntelliSense supports only the statements and syntax that are listed in this topic.</span></span>|  
|[<span data-ttu-id="7ec65-146">ALTER PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="7ec65-146">ALTER PROCEDURE</span></span>](/sql/t-sql/statements/alter-procedure-transact-sql)|<span data-ttu-id="7ec65-147">Toda a sintaxe, com as seguintes exceções:</span><span class="sxs-lookup"><span data-stu-id="7ec65-147">All syntax, with the following exceptions:</span></span><br /><br /> <span data-ttu-id="7ec65-148">Não há suporte do IntelliSense para a cláusula EXTERNAL NAME.</span><span class="sxs-lookup"><span data-stu-id="7ec65-148">There is no IntelliSense support for the EXTERNAL NAME clause.</span></span><br /><br /> <span data-ttu-id="7ec65-149">Na cláusula AS, o IntelliSense dá suporte apenas às instruções e à sintaxe listadas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="7ec65-149">In the AS clause, IntelliSense supports only the statements and syntax that are listed in this topic.</span></span>|  
|[<span data-ttu-id="7ec65-150">UTILIZÁ</span><span class="sxs-lookup"><span data-stu-id="7ec65-150">USE</span></span>](/sql/t-sql/language-elements/use-transact-sql)|<span data-ttu-id="7ec65-151">Toda a sintaxe.</span><span class="sxs-lookup"><span data-stu-id="7ec65-151">All syntax.</span></span>|  
  
## <a name="intellisense-in-supported-statements"></a><span data-ttu-id="7ec65-152">IntelliSense em instruções com suporte</span><span class="sxs-lookup"><span data-stu-id="7ec65-152">IntelliSense in Supported Statements</span></span>  
 <span data-ttu-id="7ec65-153">No Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] , o IntelliSense dá suporte aos seguintes elementos de sintaxe, quando usados em uma das instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] com suporte:</span><span class="sxs-lookup"><span data-stu-id="7ec65-153">IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor supports the following syntax elements when they are used in one of the supported [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
-   <span data-ttu-id="7ec65-154">Todos os tipos de junção, inclusive APPLY</span><span class="sxs-lookup"><span data-stu-id="7ec65-154">All join types, including APPLY</span></span>  
  
-   <span data-ttu-id="7ec65-155">PIVOT e UNPIVOT</span><span class="sxs-lookup"><span data-stu-id="7ec65-155">PIVOT and UNPIVOT</span></span>  
  
-   <span data-ttu-id="7ec65-156">Referências aos seguintes objetos de banco de dados:</span><span class="sxs-lookup"><span data-stu-id="7ec65-156">References to the following database objects:</span></span>  
  
    -   <span data-ttu-id="7ec65-157">Bancos de dados e esquemas</span><span class="sxs-lookup"><span data-stu-id="7ec65-157">Databases and schemas</span></span>  
  
    -   <span data-ttu-id="7ec65-158">Tabelas, exibições, funções com valor de tabela e expressões de tabela</span><span class="sxs-lookup"><span data-stu-id="7ec65-158">Tables, views, table-valued functions, and table expressions</span></span>  
  
    -   <span data-ttu-id="7ec65-159">Colunas</span><span class="sxs-lookup"><span data-stu-id="7ec65-159">Columns</span></span>  
  
    -   <span data-ttu-id="7ec65-160">Procedimentos e parâmetros de procedimentos</span><span class="sxs-lookup"><span data-stu-id="7ec65-160">Procedures and procedure parameters</span></span>  
  
    -   <span data-ttu-id="7ec65-161">Funções escalares e expressões escalares</span><span class="sxs-lookup"><span data-stu-id="7ec65-161">Scalar functions and scalar expressions</span></span>  
  
    -   <span data-ttu-id="7ec65-162">Variáveis locais</span><span class="sxs-lookup"><span data-stu-id="7ec65-162">Local variables</span></span>  
  
    -   <span data-ttu-id="7ec65-163">CTE (expressões de tabela comuns)</span><span class="sxs-lookup"><span data-stu-id="7ec65-163">Common table expressions (CTE)</span></span>  
  
-   <span data-ttu-id="7ec65-164">Objetos de banco de dados referenciados apenas nas instruções CREATE ou ALTER no script ou lote, mas que não existem no banco de dados porque o script ou lote ainda não foi executado.</span><span class="sxs-lookup"><span data-stu-id="7ec65-164">Database objects that are referenced only in CREATE or ALTER statements in the script or batch, but which do not exist in the database because the script or batch has not yet been run.</span></span> <span data-ttu-id="7ec65-165">Esses objetos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="7ec65-165">These objects are as follows:</span></span>  
  
    -   <span data-ttu-id="7ec65-166">Tabelas e procedimentos que foram especificados em uma instrução CREATE TABLE ou CREATE PROCEDURE no script ou lote.</span><span class="sxs-lookup"><span data-stu-id="7ec65-166">Tables and procedures that have been specified in a CREATE TABLE or CREATE PROCEDURE statement in the script or batch.</span></span>  
  
    -   <span data-ttu-id="7ec65-167">Alterações em tabelas e procedimentos que foram especificadas em uma instrução ALTER TABLE ou ALTER PROCEDURE no script ou lote.</span><span class="sxs-lookup"><span data-stu-id="7ec65-167">Changes to tables and procedures that have been specified in an ALTER TABLE or ALTER PROCEDURE statement in the script or batch.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7ec65-168">O IntelliSense não está disponível para as colunas de uma instrução CREATE VIEW até que a instrução CREATE VIEW tenha sido executada.</span><span class="sxs-lookup"><span data-stu-id="7ec65-168">IntelliSense is not available for the columns of a CREATE VIEW statement until the CREATE VIEW statement has been executed.</span></span>  
  
 <span data-ttu-id="7ec65-169">O IntelliSense não é fornecido para os elementos listados anteriormente quando eles são usados em outras instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7ec65-169">IntelliSense is not provided for the previously listed elements when they are used in other [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="7ec65-170">Por exemplo, há suporte do IntelliSense para nomes de colunas usados em uma instrução SELECT, mas não para colunas usadas na instrução CREATE FUNCTION.</span><span class="sxs-lookup"><span data-stu-id="7ec65-170">For example, there is IntelliSense support for column names that are used in a SELECT statement, but not for columns that are used in the CREATE FUNCTION statement.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="7ec65-171">Exemplos</span><span class="sxs-lookup"><span data-stu-id="7ec65-171">Examples</span></span>  
 <span data-ttu-id="7ec65-172">Em um script ou lote [!INCLUDE[tsql](../../includes/tsql-md.md)] , o IntelliSense no Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] dá suporte apenas às instruções e à sintaxe listadas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="7ec65-172">Within a [!INCLUDE[tsql](../../includes/tsql-md.md)] script or batch, IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor supports only the statements and syntax that are listed in this topic.</span></span> <span data-ttu-id="7ec65-173">Os exemplos de código [!INCLUDE[tsql](../../includes/tsql-md.md)] a seguir mostram as instruções e os elementos de sintaxe com suporte do IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="7ec65-173">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] code examples show what statements and syntax elements IntelliSense supports.</span></span> <span data-ttu-id="7ec65-174">Por exemplo, no lote a seguir, o IntelliSense está disponível para a instrução `SELECT` , quando codificada por si só, mas não quando a instrução `SELECT` está contida em uma instrução `CREATE FUNCTION` .</span><span class="sxs-lookup"><span data-stu-id="7ec65-174">For example, in the following batch, IntelliSense is available for the `SELECT` statement when it is coded by itself, but not when the `SELECT` is contained in a `CREATE FUNCTION` statement.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT Name  
FROM Production.Product  
WHERE Name LIKE N'Road-250%' and Color = N'Red';  
GO  
CREATE FUNCTION Production.ufn_Red250 ()  
RETURNS TABLE  
AS  
RETURN   
(  
    SELECT Name  
    FROM AdventureWorks2012.Production.Product  
    WHERE Name LIKE N'Road-250%'  
      AND Color = N'Red'  
);GO  
```  
  
 <span data-ttu-id="7ec65-175">Essa funcionalidade também se aplica aos conjuntos de instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] da cláusula AS de uma instrução CREATE PROCEDURE ou ALTER PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="7ec65-175">This functionality also applies to the sets of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the AS clause of a CREATE PROCEDURE or ALTER PROCEDURE statement.</span></span>  
  
 <span data-ttu-id="7ec65-176">Em um script ou lote [!INCLUDE[tsql](../../includes/tsql-md.md)] , o IntelliSense dá suporte a objetos que tenham sido especificados em uma instrução CREATE ou ALTER; no entanto, esses objetos não existem no banco de dados, porque as instruções não foram executadas.</span><span class="sxs-lookup"><span data-stu-id="7ec65-176">Within a [!INCLUDE[tsql](../../includes/tsql-md.md)] script or batch, IntelliSense supports objects that have been specified in a CREATE or ALTER statement; however, these objects do not exist in the database because the statements have not been executed.</span></span> <span data-ttu-id="7ec65-177">Por exemplo, você pode digitar o seguinte código no Editor de Consultas:</span><span class="sxs-lookup"><span data-stu-id="7ec65-177">For example, you might enter the following code in the Query Editor:</span></span>  
  
```  
USE MyTestDB;  
GO  
CREATE TABLE MyTable  
    (PrimaryKeyCol   INT PRIMARY KEY,  
    FirstNameCol      NVARCHAR(50),  
   LastNameCol       NVARCHAR(50));  
GO  
SELECT   
```  
  
 <span data-ttu-id="7ec65-178">Após digitar `SELECT`, o IntelliSense listará **PrimaryKeyCol**, **FirstNameCol**e **LastNameCol** como possíveis elementos na lista de seleção, mesmo que o script não tenha sido executado e `MyTable` ainda não exista em `MyTestDB`.</span><span class="sxs-lookup"><span data-stu-id="7ec65-178">After you type `SELECT`, IntelliSense lists **PrimaryKeyCol**, **FirstNameCol**, and **LastNameCol** as possible elements in the select list, even if the script has not been executed and `MyTable` does not yet exist in `MyTestDB`.</span></span>  
  
  
