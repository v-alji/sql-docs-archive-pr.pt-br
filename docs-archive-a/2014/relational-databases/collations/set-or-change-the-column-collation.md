---
title: Definir ou alterar a ordenação de coluna | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- tempdb database [SQL Server], collations
- collations [SQL Server], column
ms.assetid: d7a9638b-717c-4680-9b98-8849081e08be
author: stevestein
ms.author: sstein
ms.openlocfilehash: 05b8211569b6ce83faaec043e5eb527a60f0ddab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583645"
---
# <a name="set-or-change-the-column-collation"></a><span data-ttu-id="26b44-102">Definir ou alterar a ordenação de coluna</span><span class="sxs-lookup"><span data-stu-id="26b44-102">Set or Change the Column Collation</span></span>
  <span data-ttu-id="26b44-103">É possível substituir a ordenação de banco de dados para dados `char`, `varchar`, `text`, `nchar`, `nvarchar` e `ntext` especificando uma ordenação diferente para uma coluna específica de uma tabela e usando uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="26b44-103">You can override the database collation for `char`, `varchar`, `text`, `nchar`, `nvarchar`, and `ntext` data by specifying a different collation for a specific column of a table and using one of the following:</span></span>  
  
-   <span data-ttu-id="26b44-104">A cláusula COLLATE de [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql) e [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="26b44-104">The COLLATE clause of [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql) and [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span></span> <span data-ttu-id="26b44-105">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="26b44-105">For example:</span></span>  
  
    ```  
    CREATE TABLE dbo.MyTable  
      (PrimaryKey   int PRIMARY KEY,  
       CharCol      varchar(10) COLLATE French_CI_AS NOT NULL  
      );  
    GO  
    ALTER TABLE dbo.MyTable ALTER COLUMN CharCol  
                varchar(10)COLLATE Latin1_General_CI_AS NOT NULL;  
    GO  
    ```  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="26b44-106">.</span><span class="sxs-lookup"><span data-stu-id="26b44-106">.</span></span> <span data-ttu-id="26b44-107">Para obter mais informações, [Suporte a ordenações e a Unicode](collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="26b44-107">For more information, [Collation and Unicode Support](collation-and-unicode-support.md).</span></span>  
  
-   <span data-ttu-id="26b44-108">Usando a `Column.Collation` propriedade no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (Smo).</span><span class="sxs-lookup"><span data-stu-id="26b44-108">Using the `Column.Collation` property in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO).</span></span>  
  
 <span data-ttu-id="26b44-109">Você não pode alterar a ordenação de uma coluna atualmente referenciada por qualquer um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="26b44-109">You cannot change the collation of a column that is currently referenced by any one of the following:</span></span>  
  
-   <span data-ttu-id="26b44-110">Uma coluna computada</span><span class="sxs-lookup"><span data-stu-id="26b44-110">A computed column</span></span>  
  
-   <span data-ttu-id="26b44-111">Um índice</span><span class="sxs-lookup"><span data-stu-id="26b44-111">An index</span></span>  
  
-   <span data-ttu-id="26b44-112">Estatísticas de distribuição geradas automaticamente ou pela instrução CREATE STATISTICS</span><span class="sxs-lookup"><span data-stu-id="26b44-112">Distribution statistics, either generated automatically or by the CREATE STATISTICS statement</span></span>  
  
-   <span data-ttu-id="26b44-113">Uma restrição CHECK</span><span class="sxs-lookup"><span data-stu-id="26b44-113">A CHECK constraint</span></span>  
  
-   <span data-ttu-id="26b44-114">Uma restrição FOREIGN KEY</span><span class="sxs-lookup"><span data-stu-id="26b44-114">A FOREIGN KEY constraint</span></span>  
  
 <span data-ttu-id="26b44-115">Ao trabalhar com **tempdb**, a cláusula [COLLATE](/sql/t-sql/statements/collations) inclui uma opção *database_default* para especificar que a coluna em uma tabela temporária usa a ordenação padrão do banco de dados de usuário atual para a conexão em vez da ordenação de **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="26b44-115">When you work with **tempdb**, the [COLLATE](/sql/t-sql/statements/collations) clause includes a *database_default* option to specify that a column in a temporary table uses the collation default of the current user database for the connection instead of the collation of **tempdb**.</span></span>  
  
## <a name="collations-and-text-columns"></a><span data-ttu-id="26b44-116">Ordenações e colunas de texto</span><span class="sxs-lookup"><span data-stu-id="26b44-116">Collations and text Columns</span></span>  
 <span data-ttu-id="26b44-117">Você pode inserir ou atualizar valores em uma coluna `text` cuja ordenação seja diferente da página de código da ordenação padrão do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="26b44-117">You can insert or update values in a `text` column whose collation is different from the code page of the default collation of the database.</span></span> <span data-ttu-id="26b44-118">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] converte implicitamente os valores para a ordenação da coluna.</span><span class="sxs-lookup"><span data-stu-id="26b44-118">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] implicitly converts the values to the collation of the column.</span></span>  
  
## <a name="collations-and-tempdb"></a><span data-ttu-id="26b44-119">Ordenações e tempdb</span><span class="sxs-lookup"><span data-stu-id="26b44-119">Collations and tempdb</span></span>  
 <span data-ttu-id="26b44-120">O banco de dados **tempdb** é criado toda vez que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é iniciado e tem a mesma ordenação padrão que o banco de dados **model**.</span><span class="sxs-lookup"><span data-stu-id="26b44-120">The **tempdb** database is built every time [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started and has the same default collation as the **model** database.</span></span> <span data-ttu-id="26b44-121">Normalmente isso é igual à ordenação padrão da instância.</span><span class="sxs-lookup"><span data-stu-id="26b44-121">This is typically the same as the default collation of the instance.</span></span> <span data-ttu-id="26b44-122">Se você criar um banco de dados de usuário e especificar uma ordenação padrão diferente do **modelo**, o banco de dados de usuário terá uma ordenação padrão diferente do **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="26b44-122">If you create a user database and specify a different default collation than **model**, the user database has a different default collation than **tempdb**.</span></span> <span data-ttu-id="26b44-123">Todos os procedimentos armazenados temporários ou tabelas temporárias são criados e armazenados em **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="26b44-123">All temporary stored procedures or temporary tables are created and stored in **tempdb**.</span></span> <span data-ttu-id="26b44-124">Isso significa que todas as colunas implícitas em tabelas temporárias e todas as constantes, variáveis e parâmetros coercíveis padrão em procedimentos armazenados temporários têm ordenações diferentes dos objetos comparáveis criados em tabelas e procedimentos armazenados permanentes.</span><span class="sxs-lookup"><span data-stu-id="26b44-124">This means that all implicit columns in temporary tables and all coercible-default constants, variables, and parameters in temporary stored procedures have collations that are different from comparable objects created in permanent tables and stored procedures.</span></span>  
  
 <span data-ttu-id="26b44-125">Isso pode levar a problemas com uma desigualdade em ordenações entre bancos de dados definidos pelo usuário e objetos de banco de dados do sistema.</span><span class="sxs-lookup"><span data-stu-id="26b44-125">This could lead to problems with a mismatch in collations between user-defined databases and system database objects.</span></span> <span data-ttu-id="26b44-126">Por exemplo, uma instância de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa a ordenação Latin1_General_CS_AS e você executa as seguintes instruções:</span><span class="sxs-lookup"><span data-stu-id="26b44-126">For example, an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses the Latin1_General_CS_AS collation and you execute the following statements:</span></span>  
  
```  
CREATE DATABASE TestDB COLLATE Estonian_CS_AS;  
USE TestDB;  
CREATE TABLE TestPermTab (PrimaryKey int PRIMARY KEY, Col1 nchar );  
```  
  
 <span data-ttu-id="26b44-127">Nesse sistema, o banco de dados **tempdb** usa a ordenação Latin1_General_CS_AS com a página de código 1252, e `TestDB` e `TestPermTab.Col1` usam a ordenação `Estonian_CS_AS` com a página de código 1257.</span><span class="sxs-lookup"><span data-stu-id="26b44-127">In this system, the **tempdb** database uses the Latin1_General_CS_AS collation with code page 1252, and `TestDB` and `TestPermTab.Col1` use the `Estonian_CS_AS` collation with code page 1257.</span></span> <span data-ttu-id="26b44-128">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="26b44-128">For example:</span></span>  
  
```  
USE TestDB;  
GO  
-- Create a temporary table with the same column declarations  
-- as TestPermTab  
CREATE TABLE #TestTempTab (PrimaryKey int PRIMARY KEY, Col1 nchar );  
INSERT INTO #TestTempTab  
         SELECT * FROM TestPermTab;  
GO  
```  
  
 <span data-ttu-id="26b44-129">Com o exemplo anterior, o banco de dados **tempdb** usa a ordenação Latin1_General_CS_AS, `TestDB` e `TestTab.Col1` usam a ordenação `Estonian_CS_AS`.</span><span class="sxs-lookup"><span data-stu-id="26b44-129">With the previous example, the **tempdb** database uses the Latin1_General_CS_AS collation, and `TestDB` and `TestTab.Col1` use the `Estonian_CS_AS` collation.</span></span> <span data-ttu-id="26b44-130">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="26b44-130">For example:</span></span>  
  
```  
SELECT * FROM TestPermTab AS a INNER JOIN #TestTempTab on a.Col1 = #TestTempTab.Col1;  
```  
  
 <span data-ttu-id="26b44-131">Como **tempdb** usa a ordenação do servidor padrão e `TestPermTab.Col1` usa uma ordenação diferente, o SQL Server retorna este erro: "Não é possível resolver o conflito de ordenação entre 'Latin1_General_CI_AS_KS_WS' e 'Estonian_CS_AS' igualmente na operação".</span><span class="sxs-lookup"><span data-stu-id="26b44-131">Because **tempdb** uses the default server collation and `TestPermTab.Col1` uses a different collation, SQL Server returns this error: "Cannot resolve collation conflict between 'Latin1_General_CI_AS_KS_WS' and 'Estonian_CS_AS' in equal to operation."</span></span>  
  
 <span data-ttu-id="26b44-132">Para evitar o erro, você pode usar uma das seguintes alternativas:</span><span class="sxs-lookup"><span data-stu-id="26b44-132">To prevent the error, you can use one of the following alternatives:</span></span>  
  
-   <span data-ttu-id="26b44-133">Especifique que a coluna da tabela temporária usa a ordenação padrão do banco de dados de usuário, não **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="26b44-133">Specify that the temporary table column use the default collation of the user database, not **tempdb**.</span></span> <span data-ttu-id="26b44-134">Isso permite que a tabela temporária trabalhe com tabelas formatadas de maneira semelhante em vários bancos de dados, se isso for exigido de seu sistema.</span><span class="sxs-lookup"><span data-stu-id="26b44-134">This enables the temporary table to work with similarly formatted tables in multiple databases, if that is required of your system.</span></span>  
  
    ```  
    CREATE TABLE #TestTempTab  
       (PrimaryKey int PRIMARY KEY,  
        Col1 nchar COLLATE database_default  
       );  
    ```  
  
-   <span data-ttu-id="26b44-135">Especifique a ordenação correta para a coluna `#TestTempTab`:</span><span class="sxs-lookup"><span data-stu-id="26b44-135">Specify the correct collation for the `#TestTempTab` column:</span></span>  
  
    ```  
    CREATE TABLE #TestTempTab  
       (PrimaryKey int PRIMARY KEY,  
        Col1 nchar COLLATE Estonian_CS_AS  
       );  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="26b44-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="26b44-136">See Also</span></span>  
 <span data-ttu-id="26b44-137">[Definir ou alterar o agrupamento do servidor](set-or-change-the-server-collation.md) </span><span class="sxs-lookup"><span data-stu-id="26b44-137">[Set or Change the Server Collation](set-or-change-the-server-collation.md) </span></span>  
 <span data-ttu-id="26b44-138">[Definir ou alterar a ordenação de banco de dados](set-or-change-the-database-collation.md) </span><span class="sxs-lookup"><span data-stu-id="26b44-138">[Set or Change the Database Collation](set-or-change-the-database-collation.md) </span></span>  
 [<span data-ttu-id="26b44-139">Suporte a ordenações e a Unicode</span><span class="sxs-lookup"><span data-stu-id="26b44-139">Collation and Unicode Support</span></span>](collation-and-unicode-support.md)  
  
  
