---
title: Inserindo e atualizando dados em uma tabela (tutorial) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- inserting and updating data
ms.assetid: 514dc87a-b829-43b5-8fc8-1a400a260284
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 0646019f166e1c2cc126a4cc7d2ed8f27a7bd2f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575481"
---
# <a name="inserting-and-updating-data-in-a-table-tutorial"></a><span data-ttu-id="a4937-102">Inserindo e atualizando dados em uma tabela (tutorial)</span><span class="sxs-lookup"><span data-stu-id="a4937-102">Inserting and Updating Data in a Table (Tutorial)</span></span>
  <span data-ttu-id="a4937-103">Agora que você criou a tabela **Products**, está pronto para inserir dados na tabela usando a instrução INSERT.</span><span class="sxs-lookup"><span data-stu-id="a4937-103">Now that you have created the **Products** table, you are ready to insert data into the table by using the INSERT statement.</span></span> <span data-ttu-id="a4937-104">Depois que os dados forem inseridos, você alterará o conteúdo de uma linha usando uma instrução UPDATE.</span><span class="sxs-lookup"><span data-stu-id="a4937-104">After the data is inserted, you will change the content of a row by using an UPDATE statement.</span></span> <span data-ttu-id="a4937-105">Você usará a cláusula WHERE da instrução UPDATE para restringir a atualização a uma única linha.</span><span class="sxs-lookup"><span data-stu-id="a4937-105">You will use the WHERE clause of the UPDATE statement to restrict the update to a single row.</span></span> <span data-ttu-id="a4937-106">As quatro instruções inserem os dados a seguir.</span><span class="sxs-lookup"><span data-stu-id="a4937-106">The four statements will enter the following data.</span></span>  
  
|<span data-ttu-id="a4937-107">ProductID</span><span class="sxs-lookup"><span data-stu-id="a4937-107">ProductID</span></span>|<span data-ttu-id="a4937-108">ProductName</span><span class="sxs-lookup"><span data-stu-id="a4937-108">ProductName</span></span>|<span data-ttu-id="a4937-109">Preço</span><span class="sxs-lookup"><span data-stu-id="a4937-109">Price</span></span>|<span data-ttu-id="a4937-110">ProductDescription</span><span class="sxs-lookup"><span data-stu-id="a4937-110">ProductDescription</span></span>|  
|---------------|-----------------|-----------|------------------------|  
|<span data-ttu-id="a4937-111">1</span><span class="sxs-lookup"><span data-stu-id="a4937-111">1</span></span>|<span data-ttu-id="a4937-112">Clamp</span><span class="sxs-lookup"><span data-stu-id="a4937-112">Clamp</span></span>|<span data-ttu-id="a4937-113">12.48</span><span class="sxs-lookup"><span data-stu-id="a4937-113">12.48</span></span>|<span data-ttu-id="a4937-114">Workbench clamp</span><span class="sxs-lookup"><span data-stu-id="a4937-114">Workbench clamp</span></span>|  
|<span data-ttu-id="a4937-115">50</span><span class="sxs-lookup"><span data-stu-id="a4937-115">50</span></span>|<span data-ttu-id="a4937-116">Screwdriver</span><span class="sxs-lookup"><span data-stu-id="a4937-116">Screwdriver</span></span>|<span data-ttu-id="a4937-117">3,17</span><span class="sxs-lookup"><span data-stu-id="a4937-117">3.17</span></span>|<span data-ttu-id="a4937-118">Flat head</span><span class="sxs-lookup"><span data-stu-id="a4937-118">Flat head</span></span>|  
|<span data-ttu-id="a4937-119">75</span><span class="sxs-lookup"><span data-stu-id="a4937-119">75</span></span>|<span data-ttu-id="a4937-120">Tire Bar</span><span class="sxs-lookup"><span data-stu-id="a4937-120">Tire Bar</span></span>||<span data-ttu-id="a4937-121">Tool for changing tires.</span><span class="sxs-lookup"><span data-stu-id="a4937-121">Tool for changing tires.</span></span>|  
|<span data-ttu-id="a4937-122">3000</span><span class="sxs-lookup"><span data-stu-id="a4937-122">3000</span></span>|<span data-ttu-id="a4937-123">3mm Bracket</span><span class="sxs-lookup"><span data-stu-id="a4937-123">3mm Bracket</span></span>|<span data-ttu-id="a4937-124">.52</span><span class="sxs-lookup"><span data-stu-id="a4937-124">.52</span></span>||  
  
 <span data-ttu-id="a4937-125">A sintaxe básica é: INSERT, nome da tabela, lista de colunas, VALUES e uma lista de valores a serem inseridos.</span><span class="sxs-lookup"><span data-stu-id="a4937-125">The basic syntax is: INSERT, table name, column list, VALUES, and then a list of the values to be inserted.</span></span> <span data-ttu-id="a4937-126">Os dois hifens antes de uma linha indicam que a linha é um comentário e o texto será ignorado pelo compilador.</span><span class="sxs-lookup"><span data-stu-id="a4937-126">The two hyphens in front of a line indicate that the line is a comment and the text will be ignored by the compiler.</span></span> <span data-ttu-id="a4937-127">Neste caso, o comentário descreve uma variação admissível da sintaxe.</span><span class="sxs-lookup"><span data-stu-id="a4937-127">In this case, the comment describes a permissible variation of the syntax.</span></span>  
  
### <a name="to-insert-data-into-a-table"></a><span data-ttu-id="a4937-128">Para inserir dados em uma tabela</span><span class="sxs-lookup"><span data-stu-id="a4937-128">To insert data into a table</span></span>  
  
1.  <span data-ttu-id="a4937-129">Execute a instrução a seguir para inserir uma linha na tabela `Products` que foi criada na tarefa anterior.</span><span class="sxs-lookup"><span data-stu-id="a4937-129">Execute the following statement to insert a row into the `Products` table that was created in the previous task.</span></span> <span data-ttu-id="a4937-130">Esta é a sintaxe básica.</span><span class="sxs-lookup"><span data-stu-id="a4937-130">This is the basic syntax.</span></span>  
  
    ```  
    -- Standard syntax  
    INSERT dbo.Products (ProductID, ProductName, Price, ProductDescription)  
        VALUES (1, 'Clamp', 12.48, 'Workbench clamp')  
    GO  
  
    ```  
  
2.  <span data-ttu-id="a4937-131">A instrução a seguir mostra como você pode alterar a ordem na qual os parâmetros são fornecidos alternando o posicionamento de `ProductID` e `ProductName` na lista de campos (entre parênteses) e na lista de valores.</span><span class="sxs-lookup"><span data-stu-id="a4937-131">The following statement shows how you can change the order in which the parameters are provided by switching the placement of the `ProductID` and `ProductName` in both the field list (in parentheses) and in the values list.</span></span>  
  
    ```  
    -- Changing the order of the columns  
    INSERT dbo.Products (ProductName, ProductID, Price, ProductDescription)  
        VALUES ('Screwdriver', 50, 3.17, 'Flat head')  
    GO  
  
    ```  
  
3.  <span data-ttu-id="a4937-132">A instrução a seguir demonstra que os nomes das colunas são opcionais, desde que os valores estejam listados na ordem correta.</span><span class="sxs-lookup"><span data-stu-id="a4937-132">The following statement demonstrates that the names of the columns are optional, as long as the values are listed in the correct order.</span></span> <span data-ttu-id="a4937-133">Esta sintaxe é comum, mas não é recomendada, pois possivelmente outras usuários terão dificuldade para compreender o código.</span><span class="sxs-lookup"><span data-stu-id="a4937-133">This syntax is common but is not recommended because it might be harder for others to understand your code.</span></span> <span data-ttu-id="a4937-134">`NULL` é especificado para a coluna `Price` porque o preço desse produto ainda não é conhecido.</span><span class="sxs-lookup"><span data-stu-id="a4937-134">`NULL` is specified for the `Price` column because the price for this product is not yet known.</span></span>  
  
    ```  
    -- Skipping the column list, but keeping the values in order  
    INSERT dbo.Products  
        VALUES (75, 'Tire Bar', NULL, 'Tool for changing tires.')  
    GO  
  
    ```  
  
4.  <span data-ttu-id="a4937-135">O nome de esquema é opcional, desde que você esteja acessando e alterando uma tabela em seu esquema padrão.</span><span class="sxs-lookup"><span data-stu-id="a4937-135">The schema name is optional as long as you are accessing and changing a table in your default schema.</span></span> <span data-ttu-id="a4937-136">Como a coluna `ProductDescription` permite valores nulos e nenhum valor está sendo fornecido, o nome de coluna `ProductDescription` e o valor podem ser descartados completamente da instrução.</span><span class="sxs-lookup"><span data-stu-id="a4937-136">Because the `ProductDescription` column allows null values and no value is being provided, the `ProductDescription` column name and value can be dropped from the statement completely.</span></span>  
  
    ```  
    -- Dropping the optional dbo and dropping the ProductDescription column  
    INSERT Products (ProductID, ProductName, Price)  
        VALUES (3000, '3mm Bracket', .52)  
    GO  
    ```  
  
### <a name="to-update-the-products-table"></a><span data-ttu-id="a4937-137">Para atualizar a tabela de produtos</span><span class="sxs-lookup"><span data-stu-id="a4937-137">To update the products table</span></span>  
  
1.  <span data-ttu-id="a4937-138">Digite e execute a instrução `UPDATE` a seguir para alterar o `ProductName` do segundo produto de `Screwdriver`para `Flat Head Screwdriver`.</span><span class="sxs-lookup"><span data-stu-id="a4937-138">Type and execute the following `UPDATE` statement to change the `ProductName` of the second product from `Screwdriver`, to `Flat Head Screwdriver`.</span></span>  
  
    ```  
    UPDATE dbo.Products  
        SET ProductName = 'Flat Head Screwdriver'  
        WHERE ProductID = 50  
    GO  
    ```  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="a4937-139">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="a4937-139">Next Task in Lesson</span></span>  
 [<span data-ttu-id="a4937-140">Lendo os dados em uma tabela &#40;Tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="a4937-140">Reading the Data in a Table &#40;Tutorial&#41;</span></span>](lesson-1-4-reading-the-data-in-a-table.md)  
  
## <a name="see-also"></a><span data-ttu-id="a4937-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a4937-141">See Also</span></span>  
 <span data-ttu-id="a4937-142">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a4937-142">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span></span>  
 [<span data-ttu-id="a4937-143">UPDATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a4937-143">UPDATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/update-transact-sql)  
  
  
