---
title: Criando exibições e procedimentos armazenados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- creating views and stored procedures
ms.assetid: 53a0426d-07d8-4b7c-aa21-22632753bad8
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 76f6ecec446536191e8be4b05547ba5fd44c9d8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678481"
---
# <a name="creating-views-and-stored-procedures"></a><span data-ttu-id="548d0-102">criando exibições e procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="548d0-102">Creating Views and Stored Procedures</span></span>
  <span data-ttu-id="548d0-103"> Agora que a Marina pode acessar o banco de dados **TestData**, talvez convenha criar alguns objetos de banco de dados, como uma exibição e um procedimento armazenado, e conceder a Mary acesso a eles.</span><span class="sxs-lookup"><span data-stu-id="548d0-103">Now that Mary can access the **TestData** database, you may want to create some database objects, such as a view and a stored procedure, and then grant Mary access to them.</span></span> <span data-ttu-id="548d0-104">Uma exibição é uma instrução SELECT armazenada e um procedimento armazenado é uma ou mais instruções [!INCLUDE[tsql](../includes/tsql-md.md)] executadas como um lote.</span><span class="sxs-lookup"><span data-stu-id="548d0-104">A view is a stored SELECT statement, and a stored procedure is one or more [!INCLUDE[tsql](../includes/tsql-md.md)] statements that execute as a batch.</span></span>  
  
 <span data-ttu-id="548d0-105">Exibições são tabelas do tipo para consultas e não aceitam parâmetros.</span><span class="sxs-lookup"><span data-stu-id="548d0-105">Views are queried like tables and do not accept parameters.</span></span> <span data-ttu-id="548d0-106">Procedimentos armazenados são mais complexos que exibições.</span><span class="sxs-lookup"><span data-stu-id="548d0-106">Stored procedures are more complex than views.</span></span> <span data-ttu-id="548d0-107">Procedimentos armazenados podem ter parâmetros de entrada e saída e conter instruções para controlar o fluxo do código, como instruções IF e WHILE.</span><span class="sxs-lookup"><span data-stu-id="548d0-107">Stored procedures can have both input and output parameters and can contain statements to control the flow of the code, such as IF and WHILE statements.</span></span> <span data-ttu-id="548d0-108">É uma boa prática de programação usar procedimentos armazenados para todas as ações repetitivas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="548d0-108">It is good programming practice to use stored procedures for all repetitive actions in the database.</span></span>  
  
 <span data-ttu-id="548d0-109">Neste exemplo, você usará CREATE VIEW para criar uma exibição que seleciona apenas duas das colunas na tabela **Products** .</span><span class="sxs-lookup"><span data-stu-id="548d0-109">For this example, you will use CREATE VIEW to create a view that selects only two of the columns in the **Products** table.</span></span> <span data-ttu-id="548d0-110">Em seguida, você usará CREATE PROCEDURE para criar um procedimento armazenado que aceita um parâmetro de preço e retorna apenas produtos que custam menos do que o valor do parâmetro especificado.</span><span class="sxs-lookup"><span data-stu-id="548d0-110">Then, you will use CREATE PROCEDURE to create a stored procedure that accepts a price parameter and returns only those products that cost less than the specified parameter value.</span></span>  
  
### <a name="to-create-a-view"></a><span data-ttu-id="548d0-111">Para criar uma exibição</span><span class="sxs-lookup"><span data-stu-id="548d0-111">To create a view</span></span>  
  
1.  <span data-ttu-id="548d0-112">Execute a instrução a seguir para criar uma exibição muito simples que executa uma instrução SELECT e retorna os nomes e preços de nossos produtos para o usuário.</span><span class="sxs-lookup"><span data-stu-id="548d0-112">Execute the following statement to create a very simple view that executes a select statement, and returns the names and prices of our products to the user.</span></span>  
  
    ```  
    CREATE VIEW vw_Names  
       AS  
       SELECT ProductName, Price FROM Products;  
    GO  
  
    ```  
  
### <a name="test-the-view"></a><span data-ttu-id="548d0-113">Teste a exibição</span><span class="sxs-lookup"><span data-stu-id="548d0-113">Test the view</span></span>  
  
1.  <span data-ttu-id="548d0-114">Exibições são tratadas como tabelas.</span><span class="sxs-lookup"><span data-stu-id="548d0-114">Views are treated just like tables.</span></span> <span data-ttu-id="548d0-115">Use uma instrução `SELECT` para acessar uma exibição.</span><span class="sxs-lookup"><span data-stu-id="548d0-115">Use a `SELECT` statement to access a view.</span></span>  
  
    ```  
    SELECT * FROM vw_Names;  
    GO  
  
    ```  
  
### <a name="to-create-a-stored-procedure"></a><span data-ttu-id="548d0-116">Para criar um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="548d0-116">To create a stored procedure</span></span>  
  
1.  <span data-ttu-id="548d0-117">A instrução a seguir cria um `pr_Names`de nome de procedimento armazenado, aceita um parâmetro de entrada denominado `@VarPrice` do tipo de dados `money`.</span><span class="sxs-lookup"><span data-stu-id="548d0-117">The following statement creates a stored procedure name `pr_Names`, accepts an input parameter named `@VarPrice` of data type `money`.</span></span> <span data-ttu-id="548d0-118">O procedimento armazenado imprime a instrução `Products less than` concatenada com o parâmetro de entrada que é alterado do tipo de dados `money` para o tipo de dados de caractere `varchar(10)` .</span><span class="sxs-lookup"><span data-stu-id="548d0-118">The stored procedure prints the statement `Products less than` concatenated with the input parameter that is changed from the `money` data type into a `varchar(10)` character data type.</span></span> <span data-ttu-id="548d0-119">Depois, o procedimento executa uma instrução `SELECT` na exibição, passando o parâmetro de entrada como parte da cláusula `WHERE` .</span><span class="sxs-lookup"><span data-stu-id="548d0-119">Then, the procedure executes a `SELECT` statement on the view, passing the input parameter as part of the `WHERE` clause.</span></span> <span data-ttu-id="548d0-120">Isso retorna todos os produtos que custam menos do que o valor do parâmetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="548d0-120">This returns all products that cost less than the input parameter value.</span></span>  
  
    ```  
    CREATE PROCEDURE pr_Names @VarPrice money  
       AS  
       BEGIN  
          -- The print statement returns text to the user  
          PRINT 'Products less than ' + CAST(@VarPrice AS varchar(10));  
          -- A second statement starts here  
          SELECT ProductName, Price FROM vw_Names  
                WHERE Price < @varPrice;  
       END  
    GO  
  
    ```  
  
### <a name="test-the-stored-procedure"></a><span data-ttu-id="548d0-121">Testar o procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="548d0-121">Test the stored procedure</span></span>  
  
1.  <span data-ttu-id="548d0-122">Para testar o procedimento armazenado, digite e execute a instrução a seguir.</span><span class="sxs-lookup"><span data-stu-id="548d0-122">To test the stored procedure, type and execute the following statement.</span></span> <span data-ttu-id="548d0-123">O procedimento deve retornar os nomes dos dois produtos inseridos na tabela `Products` , na Lição 1, com um preço menor que `10.00`.</span><span class="sxs-lookup"><span data-stu-id="548d0-123">The procedure should return the names of the two products entered into the `Products` table in Lesson 1 with a price that is less than `10.00`.</span></span>  
  
    ```  
    EXECUTE pr_Names 10.00;  
    GO  
  
    ```  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="548d0-124">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="548d0-124">Next Task in Lesson</span></span>  
 [<span data-ttu-id="548d0-125">concedendo acesso a um objeto de banco de dados</span><span class="sxs-lookup"><span data-stu-id="548d0-125">Granting Access to a Database Object</span></span>](lesson-2-4-granting-access-to-a-database-object.md)  
  
## <a name="see-also"></a><span data-ttu-id="548d0-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="548d0-126">See Also</span></span>  
 <span data-ttu-id="548d0-127">[CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="548d0-127">[CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) </span></span>  
 [<span data-ttu-id="548d0-128">CREATE PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="548d0-128">CREATE PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-procedure-transact-sql)  
  
  
