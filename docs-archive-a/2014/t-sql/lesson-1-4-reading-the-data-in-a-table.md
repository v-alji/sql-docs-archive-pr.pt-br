---
title: Lendo os dados em uma tabela (tutorial) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- reading data in a table
ms.assetid: 532232c9-3d41-45cd-9150-de67a1cbfcf5
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 4bdaaeeddf8f35792c536624abfe6ff11b2dbd2e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575482"
---
# <a name="reading-the-data-in-a-table-tutorial"></a><span data-ttu-id="b9688-102">Lendo os dados em uma tabela (tutorial)</span><span class="sxs-lookup"><span data-stu-id="b9688-102">Reading the Data in a Table (Tutorial)</span></span>
  <span data-ttu-id="b9688-103">Use a instrução SELECT para ler os dados em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="b9688-103">Use the SELECT statement to read the data in a table.</span></span> <span data-ttu-id="b9688-104">A instrução SELECT é um das instruções [!INCLUDE[tsql](../includes/tsql-md.md)] mais importantes e há muitas variações na sintaxe.</span><span class="sxs-lookup"><span data-stu-id="b9688-104">The SELECT statement is one of the most important [!INCLUDE[tsql](../includes/tsql-md.md)] statements, and there are many variations in the syntax.</span></span> <span data-ttu-id="b9688-105">Para este tutorial, você trabalhará com cinco versões simples.</span><span class="sxs-lookup"><span data-stu-id="b9688-105">For this tutorial, you will work with five simple versions.</span></span>  
  
### <a name="to-read-the-data-in-a-table"></a><span data-ttu-id="b9688-106">Ler os dados em uma tabela</span><span class="sxs-lookup"><span data-stu-id="b9688-106">To read the data in a table</span></span>  
  
1.  <span data-ttu-id="b9688-107">Digite e execute as instruções seguintes para ler os dados na tabela `Products` .</span><span class="sxs-lookup"><span data-stu-id="b9688-107">Type and execute the following statements to read the data in the `Products` table.</span></span>  
  
    ```  
    -- The basic syntax for reading data from a single table  
    SELECT ProductID, ProductName, Price, ProductDescription  
        FROM dbo.Products  
    GO  
  
    ```  
  
2.  <span data-ttu-id="b9688-108">Você pode usar um asterisco para selecionar todas as colunas na tabela.</span><span class="sxs-lookup"><span data-stu-id="b9688-108">You can use an asterisk to select all the columns in the table.</span></span> <span data-ttu-id="b9688-109">Isso é frequentemente usado em consultas ad hoc.</span><span class="sxs-lookup"><span data-stu-id="b9688-109">This is often used in ad hoc queries.</span></span> <span data-ttu-id="b9688-110">Você deve fornecer a lista de colunas em seu código permanente para que a instrução retorne as colunas previstas, mesmo se uma coluna nova for adicionada posteriormente à tabela.</span><span class="sxs-lookup"><span data-stu-id="b9688-110">You should provide the column list in you permanent code so that the statement will return the predicted columns, even if a new column is added to the table later.</span></span>  
  
    ```  
    -- Returns all columns in the table  
    -- Does not use the optional schema, dbo  
    SELECT * FROM Products  
    GO  
  
    ```  
  
3.  <span data-ttu-id="b9688-111">Você pode omitir colunas que não deseja retornar.</span><span class="sxs-lookup"><span data-stu-id="b9688-111">You can omit columns that you do not want to return.</span></span> <span data-ttu-id="b9688-112">As colunas serão retornadas na ordem em que são listadas.</span><span class="sxs-lookup"><span data-stu-id="b9688-112">The columns will be returned in the order that they are listed.</span></span>  
  
    ```  
    -- Returns only two of the columns from the table  
    SELECT ProductName, Price  
        FROM dbo.Products  
    GO  
  
    ```  
  
4.  <span data-ttu-id="b9688-113">Use uma cláusula `WHERE` para limitar as linhas que serão retornadas ao usuário.</span><span class="sxs-lookup"><span data-stu-id="b9688-113">Use a `WHERE` clause to limit the rows that are returned to the user.</span></span>  
  
    ```  
    -- Returns only two of the records in the table  
    SELECT ProductID, ProductName, Price, ProductDescription  
        FROM dbo.Products  
        WHERE ProductID < 60  
    GO  
  
    ```  
  
5.  <span data-ttu-id="b9688-114">Você pode trabalhar com os valores nas colunas à medida que elas forem retornadas.</span><span class="sxs-lookup"><span data-stu-id="b9688-114">You can work with the values in the columns as they are returned.</span></span> <span data-ttu-id="b9688-115">O exemplo seguinte executa uma operação matemática na coluna `Price` .</span><span class="sxs-lookup"><span data-stu-id="b9688-115">The following example performs a mathematical operation on the `Price` column.</span></span> <span data-ttu-id="b9688-116">Colunas que foram alteradas dessa maneira não terão um nome, a menos que você forneça um, usando a palavra-chave `AS` .</span><span class="sxs-lookup"><span data-stu-id="b9688-116">Columns that have been changed in this way will not have a name unless you provide one by using the `AS` keyword.</span></span>  
  
    ```  
    -- Returns ProductName and the Price including a 7% tax  
    -- Provides the name CustomerPays for the calculated column  
    SELECT ProductName, Price * 1.07 AS CustomerPays  
        FROM dbo.Products  
    GO  
    ```  
  
## <a name="functions-that-are-useful-in-a-select-statement"></a><span data-ttu-id="b9688-117">Funções úteis em uma instrução SELECT</span><span class="sxs-lookup"><span data-stu-id="b9688-117">Functions That Are Useful in a SELECT Statement</span></span>  
 <span data-ttu-id="b9688-118">Para obter informações sobre algumas funções que você pode usar para trabalhar com instruções SELECT, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="b9688-118">For information about some functions that you can use to work with data in SELECT statements, see the following topics:</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="b9688-119">Funções de cadeia de caracteres &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b9688-119">String Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/string-functions-transact-sql)|[<span data-ttu-id="b9688-120">Tipos de dados e funções de data e hora &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b9688-120">Date and Time Data Types and Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql)|  
|[<span data-ttu-id="b9688-121">Funções matemáticas &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b9688-121">Mathematical Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/mathematical-functions-transact-sql)|[<span data-ttu-id="b9688-122">Funções de texto e imagem &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b9688-122">Text and Image Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/text-and-image-functions-textptr-transact-sql)|  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="b9688-123">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="b9688-123">Next Task in Lesson</span></span>  
 [<span data-ttu-id="b9688-124">Resumo: Criando objetos de banco de dados</span><span class="sxs-lookup"><span data-stu-id="b9688-124">Summary: Creating Database Objects</span></span>](lesson-1-5-summary-creating-database-objects.md)  
  
## <a name="see-also"></a><span data-ttu-id="b9688-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b9688-125">See Also</span></span>  
 [<span data-ttu-id="b9688-126">SELECT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b9688-126">SELECT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/select-transact-sql)  
  
  
