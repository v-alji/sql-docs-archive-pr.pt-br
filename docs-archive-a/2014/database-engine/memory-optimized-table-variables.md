---
title: Variáveis de tabela com otimização de memória | Microsoft Docs
ms.custom: ''
ms.date: 07/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: bd102e95-53e2-4da6-9b8b-0e4f02d286d3
author: stevestein
ms.author: sstein
ms.openlocfilehash: bec720c53c257240ee92274a6391ebc3f17faa25
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574883"
---
# <a name="memory-optimized-table-variables"></a><span data-ttu-id="179c3-102">Variáveis de tabela com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="179c3-102">Memory-Optimized Table Variables</span></span>
  <span data-ttu-id="179c3-103">Além das tabelas com otimização de memória (para acesso eficiente a dados) e dos procedimentos armazenados compilados nativamente (para processamento eficiente de consulta e execução de lógica de negócios), o [!INCLUDE[hek_2](../includes/hek-2-md.md)] apresenta um terceiro tipo de objeto: o tipo de tabela com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="179c3-103">In addition to memory-optimized tables (for efficient data access) and natively compiled stored procedures (for efficient query processing and business logic execution) [!INCLUDE[hek_2](../includes/hek-2-md.md)] introduces a third kind of object: the memory-optimized table type.</span></span> <span data-ttu-id="179c3-104">Uma variável de tabela criada usando um tipo de tabela com otimização de memória é uma variável de tabela com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="179c3-104">A table variable created using a memory-optimized table type is a memory-optimized table variable.</span></span>  
  
 <span data-ttu-id="179c3-105">As variáveis de tabela com otimização de memória oferecem as seguintes vantagens em comparação com as variáveis de tabela baseada em disco:</span><span class="sxs-lookup"><span data-stu-id="179c3-105">Memory-optimized table variables offer the following advantages when compared to disk-based table variables:</span></span>  
  
-   <span data-ttu-id="179c3-106">As variáveis são armazenadas apenas na memória.</span><span class="sxs-lookup"><span data-stu-id="179c3-106">The variables are only stored in memory.</span></span> <span data-ttu-id="179c3-107">O acesso a dados é mais eficiente, pois o tipo de tabela com otimização de memória usa o mesmo algoritmo com otimização de memória e estrutura de dados utilizados para tabelas com otimização de memória, especialmente quando as variáveis são usadas em procedimentos armazenados compilados nativamente.</span><span class="sxs-lookup"><span data-stu-id="179c3-107">Data access is more efficient because memory-optimized table type use the same memory-optimized algorithm and data structures used for memory-optimized tables, especially when the variables are used in natively compiled stored procedures.</span></span>  
  
-   <span data-ttu-id="179c3-108">Com as variáveis de tabela com otimização de memória, não há utilização de tempdb.</span><span class="sxs-lookup"><span data-stu-id="179c3-108">With memory-optimized table variables, there is no tempdb utilization.</span></span> <span data-ttu-id="179c3-109">As variáveis de tabela não são armazenados em tempdb e não usam nenhum recurso em tempdb.</span><span class="sxs-lookup"><span data-stu-id="179c3-109">Table variables are not stored in tempdb and do not use any resources in tempdb.</span></span>  
  
 <span data-ttu-id="179c3-110">Os cenários de uso típicos para variáveis de tabela com otimização de memória são:</span><span class="sxs-lookup"><span data-stu-id="179c3-110">The typical usage scenarios for memory-optimized table variables are:</span></span>  
  
-   <span data-ttu-id="179c3-111">Armazenar resultados intermediários e criar conjuntos de resultados únicos com base em várias consultas nos procedimentos armazenados compilados nativamente.</span><span class="sxs-lookup"><span data-stu-id="179c3-111">Storing intermediate results and creating single result sets based on multiple queries in natively compiled stored procedures.</span></span>  
  
-   <span data-ttu-id="179c3-112">Passar parâmetros com valor de tabela para procedimentos armazenados compilados nativamente e procedimentos armazenados interpretados.</span><span class="sxs-lookup"><span data-stu-id="179c3-112">Passing table-valued parameters into natively compiled stored procedures and interpreted stored procedures.</span></span>  
  
-   <span data-ttu-id="179c3-113">Substituir variáveis de tabela baseadas em disco e, em alguns casos, tabelas #temp que são locais para um procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="179c3-113">Replacing disk-based table variables, and in some cases #temp tables that are local to a stored procedure.</span></span> <span data-ttu-id="179c3-114">Isso será particularmente útil se houver muita contenção de tempdb no sistema.</span><span class="sxs-lookup"><span data-stu-id="179c3-114">This is particularly useful if there is a lot of tempdb contention in the system.</span></span>  
  
-   <span data-ttu-id="179c3-115">As variáveis de tabela podem ser usados para simular cursores em procedimentos armazenados compilados nativamente, de modo que possam ajudar você a contornar as restrições da área da superfície em procedimentos armazenados compilados nativamente.</span><span class="sxs-lookup"><span data-stu-id="179c3-115">Table variables can be used to simulate cursors in natively compiled stored procedures, which can help you work around surface area limitations in natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="179c3-116">Como as tabelas com otimização de memória, o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] gera uma DLL para cada tipo de tabela com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="179c3-116">Like memory-optimized tables, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] generates a DLL for each memory-optimized table type.</span></span> <span data-ttu-id="179c3-117">(A compilação é invocada quando o tipo de tabela com otimização de memória é criado e não quando usado para criar variáveis de tabela com otimização de memória.) Essa DLL inclui as funções para acessar índices e recuperar dados de variáveis de tabela.</span><span class="sxs-lookup"><span data-stu-id="179c3-117">(Compilation is invoked when the memory-optimized table type is created and not when used to create memory-optimized table variables.) This DLL includes the functions for accessing indexes and retrieving data from the table variables.</span></span> <span data-ttu-id="179c3-118">Quando uma variável de tabela com otimização de memória é declarada com base no tipo de tabela, uma instância da tabela e das estruturas de índice correspondentes ao tipo de tabela é criada na sessão do usuário.</span><span class="sxs-lookup"><span data-stu-id="179c3-118">When a memory-optimized table variable is declared based on the table type, an instance of the table and index structures corresponding to the table type is created in the user session.</span></span> <span data-ttu-id="179c3-119">A variável de tabela pode ser usada da mesma maneira que as variáveis de tabela baseadas em disco.</span><span class="sxs-lookup"><span data-stu-id="179c3-119">The table variable can then be used in the same way as disk-based table variables.</span></span> <span data-ttu-id="179c3-120">Você pode inserir, atualizar e excluir linhas na variável de tabela e usar variáveis em consultas do [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="179c3-120">You can insert, update, and delete rows in the table variable, and you can use the variables in [!INCLUDE[tsql](../includes/tsql-md.md)] queries.</span></span> <span data-ttu-id="179c3-121">Você também pode passar as variáveis para procedimentos armazenados compilados nativamente e interpretados, como parâmetros com valor de tabela (TVP).</span><span class="sxs-lookup"><span data-stu-id="179c3-121">You can also pass the variables into natively compiled and interpreted stored procedures, as table-valued parameters (TVP).</span></span>  
  
 <span data-ttu-id="179c3-122">O exemplo a seguir mostra um tipo de tabela com otimização de memória do exemplo de OLTP na memória com base em AdventureWorks ([SQL Server exemplo de OLTP em memória do 2014](https://msftdbprodsamples.codeplex.com/releases/view/114491)).</span><span class="sxs-lookup"><span data-stu-id="179c3-122">The following sample shows a memory-optimized table type from the AdventureWorks-based In-Memory OLTP sample ([SQL Server 2014 In-Memory OLTP Sample](https://msftdbprodsamples.codeplex.com/releases/view/114491)).</span></span>  
  
```sql
CREATE TYPE Sales.SalesOrderDetailType_inmem
   AS TABLE
(
   OrderQty         smallint   NOT NULL,
   ProductID        int        NOT NULL,

   SpecialOfferID   int        NOT NULL
      INDEX  IX_SpecialOfferID  NONCLUSTERED,

   LocalID          int        NOT NULL,

   INDEX IX_ProductID HASH (ProductID)
      WITH ( BUCKET_COUNT = 8 )
)
WITH ( MEMORY_OPTIMIZED = ON );
```  
  
 <span data-ttu-id="179c3-123">O exemplo a seguir mostra que a sintaxe de tipos de tabela com otimização de memória é semelhante aos tipos de tabela baseados em disco, com as seguintes exceções:</span><span class="sxs-lookup"><span data-stu-id="179c3-123">The sample shows that the syntax of memory-optimized table types is similar to disk-based table types, with the following exceptions:</span></span>  
  
-   <span data-ttu-id="179c3-124">`MEMORY_OPTIMIZED=ON` indica se o tipo de tabela tem otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="179c3-124">`MEMORY_OPTIMIZED=ON` indicates that the table type is memory-optimized.</span></span>  
  
-   <span data-ttu-id="179c3-125">O tipo deve ter pelo menos um índice.</span><span class="sxs-lookup"><span data-stu-id="179c3-125">The type must have at least one index.</span></span> <span data-ttu-id="179c3-126">Assim como ocorre com as tabelas com otimização de memória, você pode usar índices de hash e não clusterizados.</span><span class="sxs-lookup"><span data-stu-id="179c3-126">As with memory-optimized tables, you can use hash and nonclustered indexes.</span></span>  
  
     <span data-ttu-id="179c3-127">Para um índice de hash, o número de buckets deve ser de cerca de uma a duas vezes o número de chaves de índice exclusivo esperado.</span><span class="sxs-lookup"><span data-stu-id="179c3-127">For a hash index, the bucket count should be about one to two times the number of expected unique index keys.</span></span> <span data-ttu-id="179c3-128">Para obter mais informações, consulte [Determining the Correct Bucket Count for Hash Indexes](../relational-databases/indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="179c3-128">For more information, see [Determining the Correct Bucket Count for Hash Indexes](../relational-databases/indexes/indexes.md).</span></span>  
  
-   <span data-ttu-id="179c3-129">O tipo de dados e as restrições da restrição nas tabelas com otimização de memória também se aplicam aos tipos de tabela com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="179c3-129">The data type and constraint restrictions on memory-optimized tables also apply to memory-optimized table types.</span></span> <span data-ttu-id="179c3-130">Por exemplo, no [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] há suporte para as restrições padrão, mas as restrições de verificação não têm esse suporte.</span><span class="sxs-lookup"><span data-stu-id="179c3-130">For example, in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] default constraints are supported, but check constraints are not.</span></span>  
  
 <span data-ttu-id="179c3-131">Assim como ocorre com as tabelas com otimização de memória, as variáveis de tabela com otimização de memória,</span><span class="sxs-lookup"><span data-stu-id="179c3-131">Like memory-optimized tables, memory-optimized table variables,</span></span>  
  
-   <span data-ttu-id="179c3-132">Não oferecem suporte a planos paralelos.</span><span class="sxs-lookup"><span data-stu-id="179c3-132">Do not support parallel plans.</span></span>  
  
-   <span data-ttu-id="179c3-133">Deve ajustar à memória e não usar recursos de disco.</span><span class="sxs-lookup"><span data-stu-id="179c3-133">Must fit in memory and do not use disk resources.</span></span>  
  
 <span data-ttu-id="179c3-134">As variáveis de tabela baseada em disco existem em tempdb.</span><span class="sxs-lookup"><span data-stu-id="179c3-134">Disk-based table variables exist in tempdb.</span></span> <span data-ttu-id="179c3-135">As variáveis de tabela com otimização de memória existem no banco de dados do usuário (mas não consomem armazenamento e não são recuperadas).</span><span class="sxs-lookup"><span data-stu-id="179c3-135">Memory-optimized table variables exist in the user database (but they do not consume storage and are not recovered).</span></span>  
  
 <span data-ttu-id="179c3-136">Você não pode criar uma variável de tabela com otimização de memória usando sintaxe de linha.</span><span class="sxs-lookup"><span data-stu-id="179c3-136">You cannot create a memory-optimized table variable using in-line syntax.</span></span> <span data-ttu-id="179c3-137">Diferentemente das variáveis de tabela baseadas em disco, você deve criar um tipo primeiro.</span><span class="sxs-lookup"><span data-stu-id="179c3-137">Unlike disk-based table variables, you must create a type first.</span></span>  
  
## <a name="table-valued-parameters"></a><span data-ttu-id="179c3-138">Parâmetros de valores de tabela</span><span class="sxs-lookup"><span data-stu-id="179c3-138">Table-Valued Parameters</span></span>  
 <span data-ttu-id="179c3-139">O exemplo de script a seguir mostra a declaração de uma variável de tabela como o tipo de tabela com otimização de memória `Sales.SalesOrderDetailType_inmem`, a inserção de três linhas na variável e a passagem da variável como um TVP para `Sales.usp_InsertSalesOrder_inmem`.</span><span class="sxs-lookup"><span data-stu-id="179c3-139">The following sample script shows the declaration of a table variable as the memory-optimized table type `Sales.SalesOrderDetailType_inmem`, the insert of three rows into the variable, and passing the variable as a TVP into `Sales.usp_InsertSalesOrder_inmem`.</span></span>  
  
```sql  
DECLARE @od Sales.SalesOrderDetailType_inmem,  
  @SalesOrderID uniqueidentifier,  
  @DueDate datetime2 = SYSDATETIME()  
  
INSERT @od (LocalID, ProductID, OrderQty, SpecialOfferID) VALUES  
  (1, 888, 2, 1),  
  (2, 450, 13, 1),  
  (3, 841, 1, 1)  
  
EXEC Sales.usp_InsertSalesOrder_inmem  
  @SalesOrderID = @SalesOrderID,  
  @DueDate = @DueDate,  
 @OnlineOrderFlag = 1,  
  @SalesOrderDetails = @od  
```  
  
 <span data-ttu-id="179c3-140">Os tipos de tabela com otimização de memória podem ser usados como o tipo para parâmetros com valor de tabela (TVPs) de procedimento armazenado e podem ser referenciados pelos clientes exatamente da mesma forma que os tipos de tabelas baseadas em disco e TVPs.</span><span class="sxs-lookup"><span data-stu-id="179c3-140">Memory-optimized table types can be used as the type for stored procedure table-valued parameters (TVPs) and can be referenced by clients exactly the same as disk-based table types and TVPs.</span></span> <span data-ttu-id="179c3-141">Assim, a chamada de procedimentos armazenados com TVPs com otimização de memória e procedimentos armazenados compilados nativamente funciona exatamente da mesma forma que a chamada de procedimentos armazenados interpretados com TVPs baseadas em disco.</span><span class="sxs-lookup"><span data-stu-id="179c3-141">Therefore, the invocation of stored procedures with memory-optimized TVPs, and natively compiled stored procedures works exactly the same as the invocation of interpreted stored procedures with disk-based TVPs.</span></span>  
  
## <a name="temp-table-replacement"></a><span data-ttu-id="179c3-142">#temp Substituição de tabela</span><span class="sxs-lookup"><span data-stu-id="179c3-142">#temp Table Replacement</span></span>  
 <span data-ttu-id="179c3-143">O exemplo a seguir mostra tipos de tabela com otimização de memória e variáveis de tabela em substituição a tabelas #temp locais para um procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="179c3-143">The following sample shows memory-optimized table types and table variables as a replacement for #temp tables that are local to a stored procedure.</span></span>  
  
```sql  
-- Using SQL procedure and temp table  
CREATE TABLE #tempTable (c INT NOT NULL PRIMARY KEY NONCLUSTERED)  
  
CREATE PROCEDURE sqlProc  
AS  
BEGIN  
  TRUNCATE TABLE #tempTable  
  
  INSERT #tempTable VALUES (1)  
  INSERT #tempTable VALUES (2)  
  INSERT #tempTable VALUES (3)  
  SELECT * FROM #tempTable  
END  
GO  
  
-- Using natively compiled stored procedure and table variable  
CREATE TYPE TT AS TABLE (c INT NOT NULL PRIMARY KEY NONCLUSTERED)  
GO  
  
CREATE PROCEDURE NCSPProc  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
  DECLARE @tableVariable TT  
  INSERT @tableVariable VALUES (1)  
  INSERT @tableVariable VALUES (2)  
  INSERT @tableVariable VALUES (3)  
  SELECT c FROM @tableVariable  
END  
GO  
```  
  
## <a name="creating-a-single-result-set"></a><span data-ttu-id="179c3-144">Criando um único conjunto de resultados</span><span class="sxs-lookup"><span data-stu-id="179c3-144">Creating a Single Result Set</span></span>  
 <span data-ttu-id="179c3-145">O exemplo a seguir mostra como armazenar os resultados intermediários e criar conjuntos de resultados únicos com base em várias consultas em procedimentos armazenados compilados nativamente.</span><span class="sxs-lookup"><span data-stu-id="179c3-145">The following sample shows how to store intermediate results and create single result sets based on multiple queries in natively compiled stored procedures.</span></span> <span data-ttu-id="179c3-146">O exemplo está calculando a união `SELECT c1 FROM dbo.t1 UNION SELECT c1 FROM dbo.t2`.</span><span class="sxs-lookup"><span data-stu-id="179c3-146">The sample is computing the union `SELECT c1 FROM dbo.t1 UNION SELECT c1 FROM dbo.t2`.</span></span>  
  
```sql  
CREATE DATABASE hk  
GO  
ALTER DATABASE hk ADD FILEGROUP hk_mod CONTAINS MEMORY_OPTIMIZED_DATA  
ALTER DATABASE hk ADD FILE( NAME = 'hk_mod' , FILENAME = 'c:\data\hk_mod') TO FILEGROUP hk_mod;  
  
USE hk  
GO  
  
CREATE TYPE tab1 AS TABLE (c1 INT NOT NULL, INDEX idx NONCLUSTERED(c1)) WITH (MEMORY_OPTIMIZED = ON)  
  
CREATE TABLE dbo.t1 (c1 INT NOT NULL, INDEX idx NONCLUSTERED(c1)) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
CREATE TABLE dbo.t2 (c1 INT NOT NULL, INDEX idx NONCLUSTERED(c1)) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
  
INSERT INTO dbo.t1 VALUES (1), (2)  
INSERT INTO dbo.t2 VALUES (3), (4)  
GO  
  
CREATE PROCEDURE dbo.p1  
  WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
  AS  
  BEGIN ATOMIC WITH ( TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english' )  
  
    DECLARE @t dbo.tab1  
    INSERT @t (c1)  
    SELECT c1 FROM dbo.t1;  
  
    INSERT @t (c1)  
    SELECT c1 FROM dbo.t2;  
  
    SELECT c1 FROM @t;  
  END  
GO  
  
EXEC dbo.p1  
GO  
```  
  
## <a name="memory-consumption-for-table-variables"></a><span data-ttu-id="179c3-147">Consumo de memória para variáveis de tabela</span><span class="sxs-lookup"><span data-stu-id="179c3-147">Memory Consumption for Table Variables</span></span>  
 <span data-ttu-id="179c3-148">O consumo de memória para variáveis de tabela é semelhante às tabelas com otimização de memória, com a exceção dos índices não clusterizados.</span><span class="sxs-lookup"><span data-stu-id="179c3-148">Memory consumption for table variables is similar to memory-optimized tables, with the exception of nonclustered indexes.</span></span> <span data-ttu-id="179c3-149">Se você inserir várias linhas em variáveis de tabela com otimização de memória com índices não clusterizados e se as chaves do índice forem grandes, essas variáveis de tabela usarão uma quantidade desproporcional de memória.</span><span class="sxs-lookup"><span data-stu-id="179c3-149">If you insert a lot of rows into memory-optimized table variables with nonclustered indexes and if the index keys are large, these table variables will use a disproportionate amount of memory.</span></span> <span data-ttu-id="179c3-150">Os índices não clusterizados em variáveis de grandes tabelas exige que proporcionalmente mais memória que um índice não clusterizado exigiria para o mesmo número de linhas inseridas em uma tabela (mais memória nas páginas de índice).</span><span class="sxs-lookup"><span data-stu-id="179c3-150">Nonclustered indexes on large table variables require proportionately more memory than a nonclustered index would require for the same number of rows inserted into a table (more memory in the index pages).</span></span>  
  
 <span data-ttu-id="179c3-151">A memória para variáveis de tabela é obtida do pool de recursos do administrador de recursos do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="179c3-151">Memory for table variables comes from the database's Resource Governor resource pool.</span></span>  
  
 <span data-ttu-id="179c3-152">Ao contrário das tabelas com otimização de memória, a memória consumida (incluindo linhas excluídas) por variáveis de tabela é liberada quando a variável de tabela sai do escopo.</span><span class="sxs-lookup"><span data-stu-id="179c3-152">Unlike memory-optimized tables, the memory consumed (including deleted rows) by table variables is freed when the table variable goes out of scope.</span></span>  
  
 <span data-ttu-id="179c3-153">A memória é contabilizada como parte de um único consumidor de memória de PGPOOL do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="179c3-153">Memory is accounted for as part of the single PGPOOL memory consumer of the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="179c3-154">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="179c3-154">See Also</span></span>  
 [<span data-ttu-id="179c3-155">Suporte ao Transact-SQL para OLTP in-memory</span><span class="sxs-lookup"><span data-stu-id="179c3-155">Transact-SQL Support for In-Memory OLTP</span></span>](../relational-databases/in-memory-oltp/transact-sql-support-for-in-memory-oltp.md)  
  
  
