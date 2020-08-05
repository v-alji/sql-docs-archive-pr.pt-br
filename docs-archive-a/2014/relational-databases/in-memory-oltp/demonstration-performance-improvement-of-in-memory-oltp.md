---
title: 'Demonstração: melhoria do desempenho do OLTP in-memory | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: c6def45d-d2d4-4d24-8068-fab4cd94d8cc
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4858e4c35263ab3dd1d9fdcf55a2b136dd8eeaf2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573984"
---
# <a name="demonstration-performance-improvement-of-in-memory-oltp"></a><span data-ttu-id="6fb69-102">Demonstração: aprimoramento do desempenho do OLTP na memória</span><span class="sxs-lookup"><span data-stu-id="6fb69-102">Demonstration: Performance Improvement of In-Memory OLTP</span></span>
  <span data-ttu-id="6fb69-103">Este exemplo mostra as melhorias de desempenho ao usar OLTP na Memória, comparando as diferenças nos tempos de resposta ao executar uma consulta Transact-SQL idêntica em tabelas baseadas em disco tradicionais e com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="6fb69-103">This example shows performance improvements when using In-Memory OLTP by comparing differences in response times when running an identical Transact-SQL query against memory-optimized and traditional disk-based tables.</span></span> <span data-ttu-id="6fb69-104">Além disso, um procedimento armazenado compilado nativamente também é criado (com base na mesma consulta) e executado para demonstrar que você normalmente obtém os melhores tempos de resposta ao consultar uma tabela com otimização de memória com um procedimento armazenado compilados nativamente.</span><span class="sxs-lookup"><span data-stu-id="6fb69-104">Additionally, a natively-compiled stored procedure is also created (based on the same query) and then run to demonstrate that you typically get the best response times when querying a memory-optimized table with a natively-compiled stored procedure.</span></span> <span data-ttu-id="6fb69-105">Este exemplo mostra apenas um aspecto das melhorias de desempenho ao acessar dados em tabelas com otimização de memória; a eficiência do acesso a dados ao executar inserções.</span><span class="sxs-lookup"><span data-stu-id="6fb69-105">This sample only shows one aspect of performance improvements when accessing data in memory-optimized tables; data access efficiency when performing inserts.</span></span> <span data-ttu-id="6fb69-106">Este exemplo é de thread único e não aproveita os benefícios de simultaneidade do OLTP na memória.</span><span class="sxs-lookup"><span data-stu-id="6fb69-106">This sample is single-threaded and does not take advantage of the concurrency benefits of In-Memory OLTP.</span></span> <span data-ttu-id="6fb69-107">Uma carga de trabalho que usa a simultaneidade apresentará um maior ganho de desempenho.</span><span class="sxs-lookup"><span data-stu-id="6fb69-107">A workload that uses concurrency will see a greater performance gain.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6fb69-108">Outro exemplo que demonstra as tabelas com otimização de memória está disponível em [Exemplos de OLTP na memória do SQL Server 2014](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span><span class="sxs-lookup"><span data-stu-id="6fb69-108">Another sample demonstrating memory-optimized tables is available at [SQL Server 2014 In-Memory OLTP Sample](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span></span>  
  
 <span data-ttu-id="6fb69-109">Para concluir este exemplo, você executará o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6fb69-109">To complete this sample you will perform the following:</span></span>  
  
1.  <span data-ttu-id="6fb69-110">Criar um banco de dados chamado **imoltp** e alterar seus detalhes do arquivo e configurá-lo para usar o OLTP na Memória.</span><span class="sxs-lookup"><span data-stu-id="6fb69-110">Create a database named **imoltp** and alter its file details to set it up for using In-Memory OLTP.</span></span>  
  
2.  <span data-ttu-id="6fb69-111">Criar os objetos de banco de dados para o nosso exemplo: três tabelas e um procedimento armazenado compilado nativamente.</span><span class="sxs-lookup"><span data-stu-id="6fb69-111">Create the database objects for our sample: three tables and a natively-compiled stored procedure.</span></span>  
  
3.  <span data-ttu-id="6fb69-112">Executar as diferentes consultas e exibir os tempos de resposta para cada consulta.</span><span class="sxs-lookup"><span data-stu-id="6fb69-112">Run the different queries and display the response times for each query.</span></span>  
  
 <span data-ttu-id="6fb69-113">Para configurar o banco de dados **imoltp** para nosso exemplo, crie primeiro uma pasta vazia: **c:\imoltp_data**, e, em seguida, execute o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="6fb69-113">To setup the **imoltp** database for our example, first create an empty folder: **c:\imoltp_data**, and then run the following code:</span></span>  
  
```sql  
USE master  
GO  
  
-- Create a new database.  
CREATE DATABASE imoltp  
GO  
  
-- Prepare the database for In-Memory OLTP by  
-- adding a memory-optimized filegroup to the database.  
ALTER DATABASE imoltp ADD FILEGROUP imoltp_file_group  
    CONTAINS MEMORY_OPTIMIZED_DATA;  
  
-- Add a file (to hold the memory-optimized data) to the new filegroup.  
ALTER DATABASE imoltp ADD FILE (name='imoltp_file', filename='c:\imoltp_data\imoltp_file')  
    TO FILEGROUP imoltp_file_group;  
GO  
  
```  
  
 <span data-ttu-id="6fb69-114">Em seguida, execute o seguinte código para criar a tabela baseada em disco, 2 (duas) tabelas com otimização de memória e o procedimento armazenado compilado nativamente que será usado para demonstrar os métodos de acesso de dados diferentes:</span><span class="sxs-lookup"><span data-stu-id="6fb69-114">Next, run the following code to create the disk-based table, two (2) memory-optimized tables, and the natively-compiled stored procedure that will be used to demonstrate the different data access methods:</span></span>  
  
```sql  
USE imoltp  
GO  
  
-- If the tables or stored procedure already exist, drop them to start clean.  
IF EXISTS (SELECT NAME FROM sys.objects WHERE NAME = 'DiskBasedTable')  
   DROP TABLE [dbo].[DiskBasedTable]  
GO  
  
IF EXISTS (SELECT NAME FROM sys.objects WHERE NAME = 'InMemTable')  
   DROP TABLE [dbo].[InMemTable]  
GO  
  
IF EXISTS (SELECT NAME FROM sys.objects  WHERE NAME = 'InMemTable2')  
   DROP TABLE [dbo].[InMemTable2]  
GO  
  
IF EXISTS (SELECT NAME FROM sys.objects  WHERE NAME = 'usp_InsertData')  
   DROP PROCEDURE [dbo].[usp_InsertData]  
GO  
  
-- Create a traditional disk-based table.  
CREATE TABLE [dbo].[DiskBasedTable] (  
  c1 INT NOT NULL PRIMARY KEY,  
  c2 NCHAR(48) NOT NULL  
)  
GO  
  
-- Create a memory-optimized table.  
CREATE TABLE [dbo].[InMemTable] (  
  c1 INT NOT NULL PRIMARY KEY NONCLUSTERED HASH WITH (BUCKET_COUNT=1000000),  
  c2 NCHAR(48) NOT NULL  
) WITH (MEMORY_OPTIMIZED=ON, DURABILITY = SCHEMA_AND_DATA);  
GO  
  
-- Create a 2nd memory-optimized table.  
CREATE TABLE [dbo].[InMemTable2] (  
  c1 INT NOT NULL PRIMARY KEY NONCLUSTERED HASH WITH (BUCKET_COUNT=1000000),  
  c2 NCHAR(48) NOT NULL  
) WITH (MEMORY_OPTIMIZED=ON, DURABILITY = SCHEMA_AND_DATA);  
GO  
  
-- Create a natively-compiled stored procedure.  
CREATE PROCEDURE [dbo].[usp_InsertData]   
  @rowcount INT,  
  @c NCHAR(48)  
  WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
  AS   
  BEGIN ATOMIC   
  WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
  DECLARE @i INT = 1;  
  WHILE @i <= @rowcount  
  BEGIN  
    INSERT INTO [dbo].[inMemTable2](c1,c2) VALUES (@i, @c);  
    SET @i += 1;  
  END  
END  
GO  
  
```  
  
 <span data-ttu-id="6fb69-115">A instalação foi concluída e você está pronto para executar as consultas que exibirão os tempos de resposta comparando o desempenho entre os métodos de acesso de dados.</span><span class="sxs-lookup"><span data-stu-id="6fb69-115">The setup is complete and we are ready to execute the queries that will display the response times comparing the performance between the data access methods.</span></span>  
  
 <span data-ttu-id="6fb69-116">Para concluir o exemplo, execute o seguinte código várias vezes.</span><span class="sxs-lookup"><span data-stu-id="6fb69-116">To complete the example run the following code multiple times.</span></span> <span data-ttu-id="6fb69-117">Ignore os resultados da primeira execução, que são afetados negativamente pela alocação de memória inicial.</span><span class="sxs-lookup"><span data-stu-id="6fb69-117">Ignore the results from the first run which is negatively affected by initial memory allocation.</span></span>  
  
```sql  
SET STATISTICS TIME OFF;  
SET NOCOUNT ON;  
  
-- Delete data from all tables to reset the example.  
DELETE FROM [dbo].[DiskBasedTable]   
    WHERE [c1]>0  
GO  
DELETE FROM [dbo].[inMemTable]   
    WHERE [c1]>0  
GO  
DELETE FROM [dbo].[InMemTable2]   
    WHERE [c1]>0  
GO  
  
-- Declare parameters for the test queries.  
DECLARE @i INT = 1;  
DECLARE @rowcount INT = 100000;  
DECLARE @c NCHAR(48) = N'12345678901234567890123456789012345678';  
DECLARE @timems INT;  
DECLARE @starttime datetime2 = sysdatetime();  
  
-- Disk-based table queried with interpreted Transact-SQL.  
BEGIN TRAN  
  WHILE @I <= @rowcount  
  BEGIN  
    INSERT INTO [dbo].[DiskBasedTable](c1,c2) VALUES (@i, @c);  
    SET @i += 1;  
  END  
COMMIT  
  
SET @timems = datediff(ms, @starttime, sysdatetime());  
SELECT CAST(@timems AS VARCHAR(10)) + ' ms (disk-based table with interpreted Transact-SQL).';  
  
-- Memory-optimized table queried with interpreted Transact-SQL.  
SET @i = 1;  
SET @starttime = sysdatetime();  
  
BEGIN TRAN  
  WHILE @i <= @rowcount  
    BEGIN  
      INSERT INTO [dbo].[InMemTable](c1,c2) VALUES (@i, @c);  
      SET @i += 1;  
    END  
COMMIT  
  
SET @timems = datediff(ms, @starttime, sysdatetime());  
SELECT CAST(@timems AS VARCHAR(10)) + ' ms (memory-optimized table with interpreted Transact-SQL).';  
  
-- Memory-optimized table queried with a natively-compiled stored procedure.  
SET @starttime = sysdatetime();  
  
EXEC usp_InsertData @rowcount, @c;  
  
SET @timems = datediff(ms, @starttime, sysdatetime());  
SELECT CAST(@timems AS VARCHAR(10)) + ' ms (memory-optimized table with natively-compiled stored procedure).';  
  
```  
  
 <span data-ttu-id="6fb69-118">Os resultados esperados fornecem tempos de resposta reais mostrando como usar tabelas com otimização de e procedimentos armazenados compilados nativamente normalmente fornecem tempos de resposta consistentemente mais rápidos que as mesmas cargas de trabalho executadas em tabelas baseadas em disco tradicionais.</span><span class="sxs-lookup"><span data-stu-id="6fb69-118">The expected results provide actual response times showing how using memory-optimized tables and natively-compiled stored procedures typically provides consistently faster response times than the same workloads running against traditional disk-based tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fb69-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6fb69-119">See Also</span></span>  
 <span data-ttu-id="6fb69-120">[Extensões para o AdventureWorks para demonstrar o OLTP na memória](../../database-engine/extensions-to-adventureworks-to-demonstrate-in-memory-oltp.md) </span><span class="sxs-lookup"><span data-stu-id="6fb69-120">[Extensions to AdventureWorks to Demonstrate In-Memory OLTP](../../database-engine/extensions-to-adventureworks-to-demonstrate-in-memory-oltp.md) </span></span>  
 <span data-ttu-id="6fb69-121">[OLTP in-memory &#40;Otimização na memória&#41;](in-memory-oltp-in-memory-optimization.md) </span><span class="sxs-lookup"><span data-stu-id="6fb69-121">[In-Memory OLTP &#40;In-Memory Optimization&#41;](in-memory-oltp-in-memory-optimization.md) </span></span>  
 <span data-ttu-id="6fb69-122">[Tabelas com otimização de memória](memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="6fb69-122">[Memory-Optimized Tables](memory-optimized-tables.md) </span></span>  
 <span data-ttu-id="6fb69-123">[Procedimentos armazenados compilados nativamente](natively-compiled-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="6fb69-123">[Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md) </span></span>  
 <span data-ttu-id="6fb69-124">[Requisitos para usar tabelas com otimização de memória](requirements-for-using-memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="6fb69-124">[Requirements for Using Memory-Optimized Tables](requirements-for-using-memory-optimized-tables.md) </span></span>  
 <span data-ttu-id="6fb69-125">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6fb69-125">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="6fb69-126">[Opções de arquivo e grupos de arquivos ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) </span><span class="sxs-lookup"><span data-stu-id="6fb69-126">[ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) </span></span>  
 [<span data-ttu-id="6fb69-127">CRIAR procedimento e tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="6fb69-127">CREATE PROCEDURE and Memory-Optimized Tables</span></span>](/sql/t-sql/statements/create-procedure-transact-sql)  
  
  
