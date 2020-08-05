---
title: Usar parâmetros com valor de tabela (Mecanismo de Banco de Dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- DECLARE
- CREATE TYPE
helpviewer_keywords:
- table-valued parameters
- table-valued parameters, about table-valued parameters
- parameters [SQL Server], table-valued
- TVP See table-valued parameters
ms.assetid: 5e95a382-1e01-4c74-81f5-055612c2ad99
author: stevestein
ms.author: sstein
ms.openlocfilehash: fa7013fddc6b2ce12ad9ad0f9fcb511d93915e05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573865"
---
# <a name="use-table-valued-parameters-database-engine"></a><span data-ttu-id="34737-102">Usar parâmetros com valor de tabela (Mecanismo de Banco de Dados)</span><span class="sxs-lookup"><span data-stu-id="34737-102">Use Table-Valued Parameters (Database Engine)</span></span>
  <span data-ttu-id="34737-103">Os parâmetros com valor de tabela são declarados usando tipos de tabela definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="34737-103">Table-valued parameters are declared by using user-defined table types.</span></span> <span data-ttu-id="34737-104">Você pode usar parâmetros com valor de tabela para enviar várias linhas de dados para uma rotina ou instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] , como um procedimento armazenado ou função, sem criar uma tabela temporária ou muitos parâmetros.</span><span class="sxs-lookup"><span data-stu-id="34737-104">You can use table-valued parameters to send multiple rows of data to a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or a routine, such as a stored procedure or function, without creating a temporary table or many parameters.</span></span>  
  
 <span data-ttu-id="34737-105">Os parâmetros com valor de tabela são como matrizes de parâmetro em OLE DB e ODBC, mas oferecem mais flexibilidade e integração mais próxima ao [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34737-105">Table-valued parameters are like parameter arrays in OLE DB and ODBC, but offer more flexibility and closer integration with [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="34737-106">Eles também têm o benefício de poder participar de operações com base em conjunto.</span><span class="sxs-lookup"><span data-stu-id="34737-106">Table-valued parameters also have the benefit of being able to participate in set-based operations.</span></span>  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="34737-107">passa parâmetros com valor de tabela para rotinas por referência, para evitar a criação de uma cópia dos dados de entrada.</span><span class="sxs-lookup"><span data-stu-id="34737-107">passes table-valued parameters to routines by reference to avoid making a copy of the input data.</span></span> <span data-ttu-id="34737-108">Você pode criar e executar rotinas [!INCLUDE[tsql](../../includes/tsql-md.md)] com parâmetros com valor de tabela e chamá-las do código [!INCLUDE[tsql](../../includes/tsql-md.md)] , de clientes nativos e gerenciados em qualquer linguagem gerenciada.</span><span class="sxs-lookup"><span data-stu-id="34737-108">You can create and execute [!INCLUDE[tsql](../../includes/tsql-md.md)] routines with table-valued parameters, and call them from [!INCLUDE[tsql](../../includes/tsql-md.md)] code, managed and native clients in any managed language.</span></span>  
  
 <span data-ttu-id="34737-109">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="34737-109">**In This Topic:**</span></span>  
  
 [<span data-ttu-id="34737-110">Benefícios</span><span class="sxs-lookup"><span data-stu-id="34737-110">Benefits</span></span>](#Benefits)  
  
 [<span data-ttu-id="34737-111">Restrições</span><span class="sxs-lookup"><span data-stu-id="34737-111">Restrictions</span></span>](#Restrictions)  
  
 [<span data-ttu-id="34737-112">Parâmetros com valor de tabela vs. Operações BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="34737-112">Table-Valued Parameters vs. BULK INSERT Operations</span></span>](#BulkInsert)  
  
 [<span data-ttu-id="34737-113">Exemplo</span><span class="sxs-lookup"><span data-stu-id="34737-113">Example</span></span>](#Example)  
  
##  <a name="benefits"></a><a name="Benefits"></a> <span data-ttu-id="34737-114">Benefícios</span><span class="sxs-lookup"><span data-stu-id="34737-114">Benefits</span></span>  
 <span data-ttu-id="34737-115">Um parâmetro com valor de tabela é delimitado ao procedimento armazenado, à função ou ao texto [!INCLUDE[tsql](../../includes/tsql-md.md)] dinâmico, exatamente como outros parâmetros.</span><span class="sxs-lookup"><span data-stu-id="34737-115">A table-valued parameter is scoped to the stored procedure, function, or dynamic [!INCLUDE[tsql](../../includes/tsql-md.md)] text, exactly like other parameters.</span></span> <span data-ttu-id="34737-116">Do mesmo modo, uma variável de tipo de tabela tem escopo como qualquer outra variável local criada com uma instrução DECLARE.</span><span class="sxs-lookup"><span data-stu-id="34737-116">Similarly, a variable of table type has scope like any other local variable that is created by using a DECLARE statement.</span></span> <span data-ttu-id="34737-117">Você pode declarar variáveis com valor de tabela em instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] dinâmicas e passar essas variáveis como parâmetros com valor de tabela para funções e procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="34737-117">You can declare table-valued variables within dynamic [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and pass these variables as table-valued parameters to stored procedures and functions.</span></span>  
  
 <span data-ttu-id="34737-118">Os parâmetros com valor de tabela oferecem mais flexibilidade e, em alguns casos, melhor desempenho do que tabelas temporárias ou outras formas de passar uma lista de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="34737-118">Table-valued parameters offer more flexibility and in some cases better performance than temporary tables or other ways to pass a list of parameters.</span></span> <span data-ttu-id="34737-119">Eles oferecem os seguintes benefícios:</span><span class="sxs-lookup"><span data-stu-id="34737-119">Table-valued parameters offer the following benefits:</span></span>  
  
-   <span data-ttu-id="34737-120">Não adquirem bloqueios para a população inicial de dados de um cliente.</span><span class="sxs-lookup"><span data-stu-id="34737-120">Do not acquire locks for the initial population of data from a client.</span></span>  
  
-   <span data-ttu-id="34737-121">Fornecem um modelo de programação simples.</span><span class="sxs-lookup"><span data-stu-id="34737-121">Provide a simple programming model.</span></span>  
  
-   <span data-ttu-id="34737-122">Permitem que você inclua lógica de negócios complexa em uma única rotina.</span><span class="sxs-lookup"><span data-stu-id="34737-122">Enable you to include complex business logic in a single routine.</span></span>  
  
-   <span data-ttu-id="34737-123">Reduzem viagens de ida e volta ao servidor.</span><span class="sxs-lookup"><span data-stu-id="34737-123">Reduce round trips to the server.</span></span>  
  
-   <span data-ttu-id="34737-124">Podem ter uma estrutura de tabela de cardinalidade diferente.</span><span class="sxs-lookup"><span data-stu-id="34737-124">Can have a table structure of different cardinality.</span></span>  
  
-   <span data-ttu-id="34737-125">Possuem rigidez de tipo.</span><span class="sxs-lookup"><span data-stu-id="34737-125">Are strongly typed.</span></span>  
  
-   <span data-ttu-id="34737-126">Permitem que o cliente especifique a ordem de classificação e as chaves exclusivas.</span><span class="sxs-lookup"><span data-stu-id="34737-126">Enable the client to specify sort order and unique keys.</span></span>  
  
-   <span data-ttu-id="34737-127">São armazenados em cache como uma tabela temporária quando usado em um procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="34737-127">Are cached like a temp table when used in a stored procedure.</span></span> <span data-ttu-id="34737-128">A partir do [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], os parâmetros com valor de tabela também são armazenados em cache para consultas parametrizadas.</span><span class="sxs-lookup"><span data-stu-id="34737-128">Starting with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], table-valued parameters are also cached for parameterized queries.</span></span>  
  
##  <a name="restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="34737-129">Restrições</span><span class="sxs-lookup"><span data-stu-id="34737-129">Restrictions</span></span>  
 <span data-ttu-id="34737-130">Os parâmetros com valor de tabela têm as seguintes restrições:</span><span class="sxs-lookup"><span data-stu-id="34737-130">Table-valued parameters have the following restrictions:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="34737-131">não mantém estatísticas em colunas de parâmetros com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="34737-131">does not maintain statistics on columns of table-valued parameters.</span></span>  
  
-   <span data-ttu-id="34737-132">Os parâmetros com valor de tabela devem ser passados como parâmetros de entrada READONLY para rotinas [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34737-132">Table-valued parameters must be passed as input READONLY parameters to [!INCLUDE[tsql](../../includes/tsql-md.md)] routines.</span></span> <span data-ttu-id="34737-133">Não é possível executar operações DML como UPDATE, DELETE ou INSERT em um parâmetro com valor de tabela no corpo de uma rotina.</span><span class="sxs-lookup"><span data-stu-id="34737-133">You cannot perform DML operations such as UPDATE, DELETE, or INSERT on a table-valued parameter in the body of a routine.</span></span>  
  
-   <span data-ttu-id="34737-134">Você não pode usar um parâmetro com valor de tabela como destino de uma instrução SELECT INTO ou INSERT EXEC.</span><span class="sxs-lookup"><span data-stu-id="34737-134">You cannot use a table-valued parameter as target of a SELECT INTO or INSERT EXEC statement.</span></span> <span data-ttu-id="34737-135">Um parâmetro com valor de tabela pode estar na cláusula FROM de SELECT INTO ou na cadeia de caracteres ou procedimento armazenado INSERT EXEC.</span><span class="sxs-lookup"><span data-stu-id="34737-135">A table-valued parameter can be in the FROM clause of SELECT INTO or in the INSERT EXEC string or stored procedure.</span></span>  
  
##  <a name="table-valued-parameters-vs-bulk-insert-operations"></a><a name="BulkInsert"></a><span data-ttu-id="34737-136">Parâmetros com valor de tabela versus operações de BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="34737-136">Table-Valued Parameters vs. BULK INSERT Operations</span></span>  
 <span data-ttu-id="34737-137">O uso de parâmetros com valor de tabela é comparável a outros modos de usar variáveis com base em conjunto; no entanto, o uso de parâmetros com valor de tabela normalmente pode ser mais rápido em grandes conjuntos de dados.</span><span class="sxs-lookup"><span data-stu-id="34737-137">Using table-valued parameters is comparable to other ways of using set-based variables; however, using table-valued parameters frequently can be faster for large data sets.</span></span> <span data-ttu-id="34737-138">Comparado a operações em massa que têm um custo maior de inicialização, os parâmetros com valor de tabela têm bom desempenho para inserção de menos de 1000 linhas.</span><span class="sxs-lookup"><span data-stu-id="34737-138">Compared to bulk operations that have a greater startup cost than table-valued parameters, table-valued parameters perform well for inserting less than 1000 rows.</span></span>  
  
 <span data-ttu-id="34737-139">Os parâmetros com valor de tabela que são reutilizados beneficiam-se de cache de tabela temporária.</span><span class="sxs-lookup"><span data-stu-id="34737-139">Table-valued parameters that are reused benefit from temporary table caching.</span></span> <span data-ttu-id="34737-140">Esse cache de tabela habilita uma escalabilidade melhor do que operações BULK INSERT equivalentes.</span><span class="sxs-lookup"><span data-stu-id="34737-140">This table caching enables better scalability than equivalent BULK INSERT operations.</span></span> <span data-ttu-id="34737-141">Ao usar pequenas operações de inserção de linha, pode haver um pequeno ganho de benefício de desempenho se forem usadas listas de parâmetros ou instruções processadas em lotes em vez de operações BULK INSERT ou parâmetros com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="34737-141">By using small row-insert operations a small performance benefit might be gained by using parameter lists or batched statements instead of BULK INSERT operations or table-valued parameters.</span></span> <span data-ttu-id="34737-142">Porém, esses métodos são menos convenientes ao programa e o desempenho diminui rapidamente à medida que as linhas aumentam.</span><span class="sxs-lookup"><span data-stu-id="34737-142">However, these methods are less convenient to program, and performance decreases quickly as rows increase.</span></span>  
  
 <span data-ttu-id="34737-143">Os parâmetros com valor de tabela têm desempenho igualmente bom ou melhor do que uma implementação de matriz de parâmetros equivalente.</span><span class="sxs-lookup"><span data-stu-id="34737-143">Table-valued parameters perform equally well or better than an equivalent parameter array implementation.</span></span>  
  
##  <a name="example"></a><a name="Example"></a> <span data-ttu-id="34737-144">Exemplo</span><span class="sxs-lookup"><span data-stu-id="34737-144">Example</span></span>  
 <span data-ttu-id="34737-145">O exemplo a seguir usa o [!INCLUDE[tsql](../../includes/tsql-md.md)] e mostra como criar um tipo de parâmetro com valor de tabela, declarar uma variável para referenciá-lo, preencher a lista de parâmetros e passar os valores para um procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="34737-145">The following example uses [!INCLUDE[tsql](../../includes/tsql-md.md)] and shows you how to create a table-valued parameter type, declare a variable to reference it, fill the parameter list, and then pass the values to a stored procedure.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
  
/* Create a table type. */  
CREATE TYPE LocationTableType AS TABLE   
( LocationName VARCHAR(50)  
, CostRate INT );  
GO  
  
/* Create a procedure to receive data for the table-valued parameter. */  
CREATE PROCEDURE dbo. usp_InsertProductionLocation  
    @TVP LocationTableType READONLY  
    AS   
    SET NOCOUNT ON  
    INSERT INTO AdventureWorks2012.Production.Location  
           (Name  
           ,CostRate  
           ,Availability  
           ,ModifiedDate)  
        SELECT *, 0, GETDATE()  
        FROM  @TVP;  
        GO  
  
/* Declare a variable that references the type. */  
DECLARE @LocationTVP AS LocationTableType;  
  
/* Add data to the table variable. */  
INSERT INTO @LocationTVP (LocationName, CostRate)  
    SELECT Name, 0.00  
    FROM AdventureWorks2012.Person.StateProvince;  
  
/* Pass the table variable data to a stored procedure. */  
EXEC usp_InsertProductionLocation @LocationTVP;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="34737-146">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="34737-146">See Also</span></span>  
 <span data-ttu-id="34737-147">[CREATE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-type-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="34737-147">[CREATE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-type-transact-sql) </span></span>  
 <span data-ttu-id="34737-148">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="34737-148">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span></span>  
 <span data-ttu-id="34737-149">[os tipos sys. Types &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="34737-149">[sys.types &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-types-transact-sql) </span></span>  
 <span data-ttu-id="34737-150">[sys. Parameters &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-parameters-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="34737-150">[sys.parameters &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-parameters-transact-sql) </span></span>  
 <span data-ttu-id="34737-151">[sys. parameter_type_usages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-parameter-type-usages-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="34737-151">[sys.parameter_type_usages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-parameter-type-usages-transact-sql) </span></span>  
 <span data-ttu-id="34737-152">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="34737-152">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span></span>  
 [<span data-ttu-id="34737-153">CREATE FUNCTION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="34737-153">CREATE FUNCTION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-function-transact-sql)  
  
  
