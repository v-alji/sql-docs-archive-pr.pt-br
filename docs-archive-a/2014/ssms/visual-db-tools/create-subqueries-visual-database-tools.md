---
title: Criar subconsultas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], subqueries
- nested queries
- subqueries [SQL Server], SQL pane
ms.assetid: 34f6b9b4-ca3a-4a4f-9594-36e513f1c547
author: stevestein
ms.author: sstein
ms.openlocfilehash: 540228839b9734992be008b5d4fb7d717176832e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574996"
---
# <a name="create-subqueries-visual-database-tools"></a><span data-ttu-id="022ea-102">Criar subconsultas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="022ea-102">Create Subqueries (Visual Database Tools)</span></span>
  <span data-ttu-id="022ea-103">Você pode usar os resultados de uma consulta como entrada para outra.</span><span class="sxs-lookup"><span data-stu-id="022ea-103">You can use the results of one query as the input for another.</span></span> <span data-ttu-id="022ea-104">Pode usar os resultados de uma subconsulta como uma instrução que usa a função IN( ), o operador EXISTS ou a cláusula FROM.</span><span class="sxs-lookup"><span data-stu-id="022ea-104">You can use the results of a subquery as a statement that uses the IN( ) function, the EXISTS operator, or the FROM clause.</span></span>  
  
 <span data-ttu-id="022ea-105">Você pode criar uma subconsulta inserindo-a diretamente no painel de SQL ou copiando uma consulta e colando-a em outra.</span><span class="sxs-lookup"><span data-stu-id="022ea-105">You can create a subquery by entering it directly into the SQL pane or by copying a query and pasting it into another.</span></span>  
  
### <a name="to-define-a-subquery-in-the-sql-pane"></a><span data-ttu-id="022ea-106">Para definir uma subconsulta no painel SQL</span><span class="sxs-lookup"><span data-stu-id="022ea-106">To define a subquery in the SQL pane</span></span>  
  
1.  <span data-ttu-id="022ea-107">Crie a consulta primária.</span><span class="sxs-lookup"><span data-stu-id="022ea-107">Create the primary query.</span></span>  
  
2.  <span data-ttu-id="022ea-108">No painel SQL, selecione a instrução SQL e use **Copiar** para mover a consulta para a Área de Transferência.</span><span class="sxs-lookup"><span data-stu-id="022ea-108">In the SQL pane, select the SQL statement, and then use **Copy** to move the query to the Clipboard.</span></span>  
  
3.  <span data-ttu-id="022ea-109">Inicie a consulta nova e use **Colar** para mover a primeira consulta à nova consulta da cláusula WHERE ou FROM.</span><span class="sxs-lookup"><span data-stu-id="022ea-109">Start the new query, and then use **Paste** to move the first query into the new query's WHERE or FROM clause.</span></span>  
  
     <span data-ttu-id="022ea-110">Por exemplo, imagine que você tem duas tabelas, `products` e `suppliers`, e deseja criar uma consulta que mostre todos os produtos de fornecedores da Suécia.</span><span class="sxs-lookup"><span data-stu-id="022ea-110">For example, imagine you have two tables, `products` and `suppliers`, and you want to create a query showing all products for suppliers in Sweden.</span></span> <span data-ttu-id="022ea-111">Crie a primeira consulta na tabela `suppliers` para achar todos os fornecedores suecos:</span><span class="sxs-lookup"><span data-stu-id="022ea-111">Create the first query on the `suppliers` table to find all Swedish suppliers:</span></span>  
  
    ```  
    SELECT supplier_id  
    FROM supplier  
    WHERE (country = 'Sweden')  
    ```  
  
     <span data-ttu-id="022ea-112">Use o comando Copiar para mover essa consulta à Área de Transferência.</span><span class="sxs-lookup"><span data-stu-id="022ea-112">Use the Copy command to move this query to the Clipboard.</span></span> <span data-ttu-id="022ea-113">Crie a segunda consulta usando a tabela `products` , relacionando as informações que você precisa sobre os produtos:</span><span class="sxs-lookup"><span data-stu-id="022ea-113">Create the second query using the `products` table, listing the information you need about products:</span></span>  
  
    ```  
    SELECT product_id, supplier_id, product_name  
    FROM products  
    ```  
  
     <span data-ttu-id="022ea-114">No painel SQL, adicione uma cláusula WHERE à segunda consulta e cole a primeira consulta da Área de Transferência.</span><span class="sxs-lookup"><span data-stu-id="022ea-114">In the SQL pane, add a WHERE clause to the second query, then paste the first query from the Clipboard.</span></span> <span data-ttu-id="022ea-115">Delimite com parênteses a primeira consulta, de forma que o resultado final tenha esta aparência:</span><span class="sxs-lookup"><span data-stu-id="022ea-115">Place parentheses around the first query, so that the end result looks like this:</span></span>  
  
    ```  
    SELECT product_id, supplier_id, product_name  
    FROM products  
    WHERE supplier_id IN  
       (SELECT supplier_id  
      FROM supplier  
      WHERE (country = 'Sweden'))  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="022ea-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="022ea-116">See Also</span></span>  
 <span data-ttu-id="022ea-117">[Tipos de consulta com suporte &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="022ea-117">[Supported Query Types &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="022ea-118">Especificar critérios de pesquisa &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="022ea-118">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
