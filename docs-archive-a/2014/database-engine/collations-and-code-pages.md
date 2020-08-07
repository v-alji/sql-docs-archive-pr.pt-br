---
title: Agrupamentos e páginas de código | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: c626dcac-0474-432d-acc0-cfa643345372
author: stevestein
ms.author: sstein
ms.openlocfilehash: ab904771fa8ac4acf25a624cbf3e1139f7e96434
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575366"
---
# <a name="collations-and-code-pages"></a><span data-ttu-id="64c3b-102">Páginas de código de ordenações</span><span class="sxs-lookup"><span data-stu-id="64c3b-102">Collations and Code Pages</span></span>
  <span data-ttu-id="64c3b-103">O [!INCLUDE[hek_2](../includes/hek-2-md.md)] tem restrições nas páginas de código com suporte para colunas (var)char em tabelas com otimização de memória e ordenações com suporte usados em índices e em procedimentos armazenados compilados nativamente.</span><span class="sxs-lookup"><span data-stu-id="64c3b-103">[!INCLUDE[hek_2](../includes/hek-2-md.md)] has restrictions on supported code pages for (var)char columns in memory-optimized tables and supported collations used in indexes and natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="64c3b-104">A página de código para um valor (var)char determina o mapeamento entre caracteres e a representação de bytes que é armazenada na tabela.</span><span class="sxs-lookup"><span data-stu-id="64c3b-104">The code page for a (var)char value determines the mapping between characters and the byte representation that is stored in the table.</span></span> <span data-ttu-id="64c3b-105">Por exemplo, com a página de código Latin 1 do Windows (1252; o padrão do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]), o caractere 'a' corresponde ao byte 0x61.</span><span class="sxs-lookup"><span data-stu-id="64c3b-105">For example, with the Windows Latin 1 code page (1252; the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] default), the character 'a' corresponds to the byte 0x61.</span></span>  
  
 <span data-ttu-id="64c3b-106">A página de código do valor (var)char é determinada pela ordenação associada ao valor.</span><span class="sxs-lookup"><span data-stu-id="64c3b-106">The code page of a (var)char value is determined by the collation associated with the value.</span></span> <span data-ttu-id="64c3b-107">Por exemplo, a ordenação SQL_Latin1_General_CP1_CI_AS tem a página de código associada 1252.</span><span class="sxs-lookup"><span data-stu-id="64c3b-107">For example, the collation SQL_Latin1_General_CP1_CI_AS has the associated code page 1252.</span></span>  
  
 <span data-ttu-id="64c3b-108">A ordenação de um valor é herdada da ordenação de banco de dados ou pode ser especificada explicitamente usando a palavra-chave COLLATE.</span><span class="sxs-lookup"><span data-stu-id="64c3b-108">The collation of a value is either inherited from the database collation, or can be specified explicitly using the COLLATE keyword.</span></span> <span data-ttu-id="64c3b-109">A ordenação de banco de dados não poderá ser alterada se o banco de dados contiver tabelas com otimização de memória ou procedimentos armazenados nativamente compilados.</span><span class="sxs-lookup"><span data-stu-id="64c3b-109">Database collation cannot be changed if the database contains memory-optimized tables or natively compiled stored procedures.</span></span> <span data-ttu-id="64c3b-110">O exemplo a seguir define a ordenação de banco de dados e cria uma tabela, que tem uma coluna com uma ordenação diferente.</span><span class="sxs-lookup"><span data-stu-id="64c3b-110">The following example sets the database collation and creates a table, which has a column with a different collation.</span></span> <span data-ttu-id="64c3b-111">O banco de dados usa a ordenação Latin que não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="64c3b-111">The database uses Latin case-insensitive collation.</span></span>  
  
 <span data-ttu-id="64c3b-112">Os índices só poderão ser criados em colunas de cadeia de caracteres se usarem uma ordenação BIN2.</span><span class="sxs-lookup"><span data-stu-id="64c3b-112">Indexes can only be created on string columns if they use a BIN2 collation.</span></span> <span data-ttu-id="64c3b-113">A variável LastName usa a ordenação BIN2.</span><span class="sxs-lookup"><span data-stu-id="64c3b-113">The LastName variable uses BIN2 collation.</span></span> <span data-ttu-id="64c3b-114">FirstName usa o padrão de banco de dados, que é CI_AS (sem diferenciação de maiúsculas e minúsculas, com diferenciação de acentos).</span><span class="sxs-lookup"><span data-stu-id="64c3b-114">FirstName uses the database default, which is CI_AS (case-insensitive, accent-sensitive).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="64c3b-115">Você não pode usar ordenar por ou agrupar por em colunas de cadeia de caracteres de índice que não utilizem a ordenação BIN2.</span><span class="sxs-lookup"><span data-stu-id="64c3b-115">You cannot use order by or group by on index string columns that do not use BIN2 collation.</span></span>  
  
```sql  
CREATE DATABASE IMOLTP  
  
ALTER DATABASE IMOLTP ADD FILEGROUP IMOLTP_mod CONTAINS MEMORY_OPTIMIZED_DATA  
ALTER DATABASE IMOLTP ADD FILE( NAME = 'IMOLTP_mod' , FILENAME = 'c:\data\IMOLTP_mod') TO FILEGROUP IMOLTP_mod;  
--GO  
  
--  set the database collations  
ALTER DATABASE IMOLTP COLLATE Latin1_General_100_CI_AS  
GO  
  
--  
USE IMOLTP   
GO  
  
-- create a table with collation  
CREATE TABLE Employees (  
  EmployeeID int NOT NULL ,   
  LastName nvarchar(20) COLLATE Latin1_General_100_BIN2 NOT NULL INDEX IX_LastName NONCLUSTERED,   
  FirstName nvarchar(10) NOT NULL ,  
  CONSTRAINT PK_Employees PRIMARY KEY NONCLUSTERED HASH(EmployeeID)  WITH (BUCKET_COUNT=1024)  
) WITH (MEMORY_OPTIMIZED=ON, DURABILITY=SCHEMA_AND_DATA)  
GO  
```  
  
 <span data-ttu-id="64c3b-116">As seguintes restrições se aplicam a tabelas com otimização de memória e a procedimentos armazenados compilados nativamente:</span><span class="sxs-lookup"><span data-stu-id="64c3b-116">The following restrictions apply to memory-optimized tables and natively compiled stored procedures:</span></span>  
  
-   <span data-ttu-id="64c3b-117">As colunas (var)char em tabelas com otimização de memória devem usar ordenação 1252 de página de código.</span><span class="sxs-lookup"><span data-stu-id="64c3b-117">(var)char columns in memory-optimized tables must use code page 1252 collation.</span></span> <span data-ttu-id="64c3b-118">Essa restrição não se aplica às colunas n(var)char.</span><span class="sxs-lookup"><span data-stu-id="64c3b-118">This restriction does not apply to n(var)char columns.</span></span> <span data-ttu-id="64c3b-119">O código a seguir recupera todas as ordenações 1252:</span><span class="sxs-lookup"><span data-stu-id="64c3b-119">The following code retrieves all 1252 collations:</span></span>  
  
    ```sql  
    -- all supported collations for (var)char columns in memory-optimized tables  
    select * from sys.fn_helpcollations()  
    where collationproperty(name, 'codepage') = 1252;  
    ```  
  
     <span data-ttu-id="64c3b-120">Se você precisar armazenar caracteres não latinos, use colunas n(var)char.</span><span class="sxs-lookup"><span data-stu-id="64c3b-120">If you need to store non-Latin characters, use n(var)char columns.</span></span>  
  
-   <span data-ttu-id="64c3b-121">Índices nas colunas (n)(var)char só podem ser especificados com ordenações BIN2 (veja o primeiro exemplo).</span><span class="sxs-lookup"><span data-stu-id="64c3b-121">Indexes on (n)(var)char columns can only be specified with BIN2 collations (see the first example).</span></span> <span data-ttu-id="64c3b-122">A consulta a seguir recupera todas as ordenações BIN2 com suporte:</span><span class="sxs-lookup"><span data-stu-id="64c3b-122">The following query retrieves all supported BIN2 collations:</span></span>  
  
    ```sql  
    -- all supported collations for indexes on memory-optimized tables and   
    -- comparison/sorting in natively compiled stored procedures  
    select * from sys.fn_helpcollations() where name like '%BIN2'  
    ```  
  
     <span data-ttu-id="64c3b-123">Ao acessar a tabela pelo [!INCLUDE[tsql](../includes/tsql-md.md)]interpretado, você pode usar a palavra-chave `COLLATE` para alterar a ordenação com expressões ou operações de classificação.</span><span class="sxs-lookup"><span data-stu-id="64c3b-123">If you access the table through interpreted [!INCLUDE[tsql](../includes/tsql-md.md)], you can use the `COLLATE` keyword to change the collation with expressions or sort operations.</span></span> <span data-ttu-id="64c3b-124">Consulte o último exemplo para obter uma amostra disso.</span><span class="sxs-lookup"><span data-stu-id="64c3b-124">See the last example for a sample of this.</span></span>  
  
-   <span data-ttu-id="64c3b-125">Os procedimentos armazenados nativamente compilados não podem usar parâmetros, variáveis locais ou constantes de cadeia de caracteres do tipo (var)char se a ordenação de banco de dados não for uma ordenação 1252 de página de código.</span><span class="sxs-lookup"><span data-stu-id="64c3b-125">Natively compiled stored procedures cannot use parameters, local variables, or string constants of (var)char type if the database collation is not a code page 1252 collation.</span></span>  
  
-   <span data-ttu-id="64c3b-126">Todas as expressões e operações de classificação dentro dos procedimentos armazenados compilados nativamente devem usar ordenações BIN2.</span><span class="sxs-lookup"><span data-stu-id="64c3b-126">All expressions and sort operations inside natively compiled stored procedures must use BIN2 collations.</span></span> <span data-ttu-id="64c3b-127">A implicação é que todas as comparações e operações de classificação são baseadas nos pontos de código Unicode dos caracteres (representações binárias).</span><span class="sxs-lookup"><span data-stu-id="64c3b-127">The implication is that all comparisons and sort operations are based on the Unicode code points of the characters (binary representations).</span></span> <span data-ttu-id="64c3b-128">Por exemplo, todas as classificações diferenciam maiúsculas de minúsculas ('Z' vem antes de 'a').</span><span class="sxs-lookup"><span data-stu-id="64c3b-128">For example all sorting is case sensitive ('Z' comes before 'a').</span></span> <span data-ttu-id="64c3b-129">Se necessário, use [!INCLUDE[tsql](../includes/tsql-md.md)] interpretado para classificação e comparação sem diferenciação de maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="64c3b-129">If necessary, use interpreted [!INCLUDE[tsql](../includes/tsql-md.md)] for case-insensitive sorting and comparison.</span></span>  
  
-   <span data-ttu-id="64c3b-130">O truncamento de dados UTF-16 não tem suporte dentro de procedimentos armazenados compilados nativamente.</span><span class="sxs-lookup"><span data-stu-id="64c3b-130">Truncation of UTF-16 data is not supported inside natively compiled stored procedures.</span></span> <span data-ttu-id="64c3b-131">Isso significa que n (var) valores de Char (*n*) não podem ser convertidos para o tipo n (var) Char (*i*), se *eu*  <  *n*, se o agrupamento tiver a propriedade _SC.</span><span class="sxs-lookup"><span data-stu-id="64c3b-131">This means that n(var)char(*n*) values cannot be converted to type n(var)char(*i*), if *i* < *n*, if the collation has _SC property.</span></span> <span data-ttu-id="64c3b-132">Por exemplo, o seguinte não tem suporte:</span><span class="sxs-lookup"><span data-stu-id="64c3b-132">For example, the following is not supported:</span></span>  
  
    ```sql  
    -- column definition using an _SC collation  
     c2 nvarchar(200) collate Latin1_General_100_CS_AS_SC not null   
    -- assignment to a smaller variable, requiring truncation  
     declare @c2 nvarchar(100) = '';  
     select @c2 = c2  
    ```  
  
     <span data-ttu-id="64c3b-133">As funções de manipulação de cadeia de caracteres, como LEN, SUBSTRING, LTRIM e RTRIM com dados UTF-16 não têm suporte dentro de procedimentos armazenados compilados nativamente.</span><span class="sxs-lookup"><span data-stu-id="64c3b-133">String manipulation functions, such as LEN, SUBSTRING, LTRIM, and RTRIM with UTF-16 data are not supported inside natively compiled stored procedures.</span></span> <span data-ttu-id="64c3b-134">Não é possível usar essas funções de manipulação de cadeia de caracteres para os valores de n(var)char que têm uma ordenação _SC.</span><span class="sxs-lookup"><span data-stu-id="64c3b-134">You cannot use these string manipulation functions for n(var)char values that have an _SC collation.</span></span>  
  
     <span data-ttu-id="64c3b-135">Declare variáveis usando os tipos que são grandes o suficiente para impedir o truncamento.</span><span class="sxs-lookup"><span data-stu-id="64c3b-135">Declare variables using types that are large enough to avoid truncation.</span></span>  
  
 <span data-ttu-id="64c3b-136">O exemplo a seguir mostra algumas das implicações e soluções alternativas para as limitações de ordenação na OLTP na memória.</span><span class="sxs-lookup"><span data-stu-id="64c3b-136">The following example shows some of the implications and workarounds for the collation limitations in In-Memory OLTP.</span></span> <span data-ttu-id="64c3b-137">O exemplo usa a tabela Employees especificada acima.</span><span class="sxs-lookup"><span data-stu-id="64c3b-137">The example uses the Employees table specified above.</span></span> <span data-ttu-id="64c3b-138">Este exemplo lista todos os funcionários.</span><span class="sxs-lookup"><span data-stu-id="64c3b-138">This sample list all employees .</span></span> <span data-ttu-id="64c3b-139">Observe que para LastName, devido à ordenação primária, os nomes em letras maiúsculas são classificados antes daqueles com letras minúsculas.</span><span class="sxs-lookup"><span data-stu-id="64c3b-139">Notice that for LastName, due to the binary collation, the upper case names are sorted before lower case.</span></span> <span data-ttu-id="64c3b-140">Consequentemente, 'Thomas' vem antes de 'nolan' porque os caracteres maiúsculos têm pontos de código inferiores.</span><span class="sxs-lookup"><span data-stu-id="64c3b-140">Therefore, 'Thomas' comes before 'nolan' because upper case characters have lower code points.</span></span> <span data-ttu-id="64c3b-141">FirstName tem uma ordenação sem diferenciação de maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="64c3b-141">FirstName has a case-insensitive collation.</span></span> <span data-ttu-id="64c3b-142">Desse modo, a classificação é por ordem alfabética, e não pelo ponto de código dos caracteres.</span><span class="sxs-lookup"><span data-stu-id="64c3b-142">So, sorting is by letter of the alphabet, not code point of the characters.</span></span>  
  
```sql  
-- insert a number of values  
INSERT Employees VALUES (1,'thomas', 'john')  
INSERT Employees VALUES (2,'Thomas', 'rupert')  
INSERT Employees VALUES (3,'Thomas', 'Jack')  
INSERT Employees VALUES (4,'Thomas', 'annie')  
INSERT Employees VALUES (5,'nolan', 'John')  
GO  
  
-- ===========  
SELECT EmployeeID, LastName, FirstName FROM Employees  
ORDER BY LastName, FirstName  
GO  
  
-- ===========  
-- specify collation: sorting uses case-insensitive collation, thus 'nolan' comes before 'Thomas'  
SELECT * FROM Employees  
ORDER BY LastName COLLATE Latin1_General_100_CI_AS, FirstName  
GO  
  
-- ===========  
-- retrieve employee by Name  
-- must use BIN2 collation for comparison in natively compiled stored procedures  
CREATE PROCEDURE usp_EmployeeByName @LastName nvarchar(20), @FirstName nvarchar(10)  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH   
(  TRANSACTION ISOLATION LEVEL = SNAPSHOT,  
  LANGUAGE = N'us_english'  
)  
  SELECT EmployeeID, LastName, FirstName FROM dbo.Employees  
  WHERE   
    LastName = @LastName AND  
    FirstName COLLATE Latin1_General_100_BIN2 = @FirstName  
  
END  
GO  
  
-- this does not return any rows, as EmployeeID 1 has first name 'john', which is not equal to 'John' in a binary collation  
EXEC usp_EmployeeByName 'thomas', 'John'  
  
-- this retrieves EmployeeID 1  
EXEC usp_EmployeeByName 'thomas', 'john'  
```  
  
## <a name="see-also"></a><span data-ttu-id="64c3b-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="64c3b-143">See Also</span></span>  
 [<span data-ttu-id="64c3b-144">OLTP in-memory &#40;Otimização na memória&#41;</span><span class="sxs-lookup"><span data-stu-id="64c3b-144">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
