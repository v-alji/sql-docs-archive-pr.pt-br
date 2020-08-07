---
title: Criando uma tabela (tutorial) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- creating tables
ms.assetid: 653f2dd3-36a2-4bd5-8703-71a57d244661
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: c772f2527bd5ddb8a6759cbaa72d8aed9277f5cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575485"
---
# <a name="creating-a-table-tutorial"></a><span data-ttu-id="2822d-102">criando uma tabela (tutorial)</span><span class="sxs-lookup"><span data-stu-id="2822d-102">Creating a Table (Tutorial)</span></span>
  <span data-ttu-id="2822d-103">Para criar uma tabela, você deve fornecer um nome para a tabela e os nomes e tipos de dados de cada coluna na tabela.</span><span class="sxs-lookup"><span data-stu-id="2822d-103">To create a table, you must provide a name for the table, and the names and data types of each column in the table.</span></span> <span data-ttu-id="2822d-104">Também é uma prática recomendada indicar se são permitidos valores nulos em cada coluna.</span><span class="sxs-lookup"><span data-stu-id="2822d-104">It is also a good practice to indicate whether null values are allowed in each column.</span></span>  
  
 <span data-ttu-id="2822d-105">A maioria das tabelas tem uma chave primária, composta de uma ou mais colunas da tabela.</span><span class="sxs-lookup"><span data-stu-id="2822d-105">Most tables have a primary key, made up of one or more columns of the table.</span></span> <span data-ttu-id="2822d-106">Uma chave primária sempre é exclusiva.</span><span class="sxs-lookup"><span data-stu-id="2822d-106">A primary key is always unique.</span></span> <span data-ttu-id="2822d-107">O [!INCLUDE[ssDE](../includes/ssde-md.md)] aplicará a restrição que nenhum valor de chave primária pode ser repetido na tabela.</span><span class="sxs-lookup"><span data-stu-id="2822d-107">The [!INCLUDE[ssDE](../includes/ssde-md.md)] will enforce the restriction that any primary key value cannot be repeated in the table.</span></span>  
  
 <span data-ttu-id="2822d-108">Para obter uma lista de tipos de dados e links para uma descrição de cada um, consulte [Tipos de dados &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2822d-108">For a list of data types and links for a description of each, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2822d-109">O [!INCLUDE[ssDE](../includes/ssde-md.md)] pode ser instalado diferenciando ou não maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="2822d-109">The [!INCLUDE[ssDE](../includes/ssde-md.md)] can be installed as case sensitive or non-case sensitive.</span></span> <span data-ttu-id="2822d-110">Se o [!INCLUDE[ssDE](../includes/ssde-md.md)] for instalado diferenciando maiúsculas e minúsculas, os nomes de objeto sempre terão o mesmo tipo (em maiúsculas ou em minúsculas).</span><span class="sxs-lookup"><span data-stu-id="2822d-110">If the [!INCLUDE[ssDE](../includes/ssde-md.md)] is installed as case sensitive, object names must always have the same case.</span></span> <span data-ttu-id="2822d-111">Por exemplo, uma tabela denominada OrderData é diferente de uma tabela denominada ORDERDATA.</span><span class="sxs-lookup"><span data-stu-id="2822d-111">For example, a table named OrderData is a different table from a table named ORDERDATA.</span></span> <span data-ttu-id="2822d-112">Se o [!INCLUDE[ssDE](../includes/ssde-md.md)] estiver instalado como sem distinção entre maiúsculas e minúsculas, esses dois nomes de tabela serão considerados como sendo a mesma tabela, e esse nome poderá ser usado somente uma vez.</span><span class="sxs-lookup"><span data-stu-id="2822d-112">If the [!INCLUDE[ssDE](../includes/ssde-md.md)] is installed as non-case sensitive, those two table names are considered to be the same table, and that name can only be used one time.</span></span>  
  
### <a name="to-create-a-database-to-contain-the-new-table"></a><span data-ttu-id="2822d-113">Para criar um banco de dados para conter a tabela nova</span><span class="sxs-lookup"><span data-stu-id="2822d-113">To create a database to contain the new table</span></span>  
  
-   <span data-ttu-id="2822d-114">Copie o código a seguir em uma janela Editor de Consulta.</span><span class="sxs-lookup"><span data-stu-id="2822d-114">Enter the following code into a Query Editor window.</span></span>  
  
    ```  
    USE master;  
    GO  
  
    --Delete the TestData database if it exists.  
    IF EXISTS(SELECT * from sys.databases WHERE name='TestData')  
    BEGIN  
        DROP DATABASE TestData;  
    END  
  
    --Create a new database called TestData.  
    CREATE DATABASE TestData;  
    Press the F5 key to execute the code and create the database.  
    ```  
  
### <a name="switch-the-query-editor-connection-to-the-testdata-database"></a><span data-ttu-id="2822d-115">Alternar a conexão do Editor de Consulta com o banco de dados TestData</span><span class="sxs-lookup"><span data-stu-id="2822d-115">Switch the Query Editor connection to the TestData database</span></span>  
  
-   <span data-ttu-id="2822d-116">Em uma janela do Editor de Consultas, digite e execute o código a seguir para alterar sua conexão com o banco de dados `TestData` .</span><span class="sxs-lookup"><span data-stu-id="2822d-116">In a Query Editor window, type and execute the following code to change your connection to the `TestData` database.</span></span>  
  
    ```  
    USE TestData  
    GO  
    ```  
  
### <a name="to-create-a-table"></a><span data-ttu-id="2822d-117">Para criar uma tabela</span><span class="sxs-lookup"><span data-stu-id="2822d-117">To create a table</span></span>  
  
-   <span data-ttu-id="2822d-118">Em uma janela do Editor de Consultas, digite e execute o seguinte código para criar uma tabela simples chamada `Products`.</span><span class="sxs-lookup"><span data-stu-id="2822d-118">In a Query Editor window, type and execute the following code to create a simple table named `Products`.</span></span> <span data-ttu-id="2822d-119">As colunas na tabela são nomeadas `ProductID`, `ProductName`, `Price`e `ProductDescription`.</span><span class="sxs-lookup"><span data-stu-id="2822d-119">The columns in the table are named `ProductID`, `ProductName`, `Price`, and `ProductDescription`.</span></span> <span data-ttu-id="2822d-120">A coluna `ProductID` é a chave primária da tabela.</span><span class="sxs-lookup"><span data-stu-id="2822d-120">The `ProductID` column is the primary key of the table.</span></span> <span data-ttu-id="2822d-121">`int`, `varchar(25)`, `money`e `text` são todos tipos de dados.</span><span class="sxs-lookup"><span data-stu-id="2822d-121">`int`, `varchar(25)`, `money`, and `text` are all data types.</span></span> <span data-ttu-id="2822d-122">Somente as colunas `Price` e `ProductionDescription` podem não ter dados quando uma linha for inserida ou alterada.</span><span class="sxs-lookup"><span data-stu-id="2822d-122">Only the `Price` and `ProductionDescription` columns can have no data when a row is inserted or changed.</span></span> <span data-ttu-id="2822d-123">Essa instrução contém um elemento opcional (`dbo.`) chamado de um esquema.</span><span class="sxs-lookup"><span data-stu-id="2822d-123">This statement contains an optional element (`dbo.`) called a schema.</span></span> <span data-ttu-id="2822d-124">O esquema é o objeto do banco de dados que possui a tabela.</span><span class="sxs-lookup"><span data-stu-id="2822d-124">The schema is the database object that owns the table.</span></span> <span data-ttu-id="2822d-125">Se você for um administrador, `dbo` será o esquema padrão.</span><span class="sxs-lookup"><span data-stu-id="2822d-125">If you are an administrator, `dbo` is the default schema.</span></span> <span data-ttu-id="2822d-126">`dbo` representa o proprietário do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2822d-126">`dbo` stands for database owner.</span></span>  
  
    ```  
    CREATE TABLE dbo.Products  
       (ProductID int PRIMARY KEY NOT NULL,  
        ProductName varchar(25) NOT NULL,  
        Price money NULL,  
        ProductDescription text NULL)  
    GO  
    ```  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="2822d-127">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="2822d-127">Next Task in Lesson</span></span>  
 [<span data-ttu-id="2822d-128">Inserindo e atualizando dados em uma tabela &#40;tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="2822d-128">Inserting and Updating Data in a Table &#40;Tutorial&#41;</span></span>](../t-sql/lesson-1-3-inserting-and-updating-data-in-a-table.md)  
  
## <a name="see-also"></a><span data-ttu-id="2822d-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2822d-129">See Also</span></span>  
 [<span data-ttu-id="2822d-130">CREATE TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2822d-130">CREATE TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-table-transact-sql)  
  
  
