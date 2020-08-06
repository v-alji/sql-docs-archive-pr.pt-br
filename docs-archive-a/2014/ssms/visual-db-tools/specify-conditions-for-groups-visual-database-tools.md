---
title: Especificar condições para grupos (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- HAVING clause, query groups
- group query conditions [SQL Server]
ms.assetid: 269ad9c5-3261-4526-badf-7be3c869f229
author: stevestein
ms.author: sstein
ms.openlocfilehash: da9bc1b70fbfae8bf2a68a3a3ba332020020f310
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568278"
---
# <a name="specify-conditions-for-groups-visual-database-tools"></a><span data-ttu-id="6b38f-102">Especificar condições para grupos (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="6b38f-102">Specify Conditions for Groups (Visual Database Tools)</span></span>
  <span data-ttu-id="6b38f-103">Você pode limitar os grupos exibidos em uma consulta especificando uma condição aplicável aos grupos como um todo, ou seja, uma cláusula HAVING.</span><span class="sxs-lookup"><span data-stu-id="6b38f-103">You can limit the groups that appear in a query by specifying a condition that applies to groups as a whole - a HAVING clause.</span></span> <span data-ttu-id="6b38f-104">Depois que os dados são agrupados e agregados, as condições na cláusula HAVING são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="6b38f-104">After the data has been grouped and aggregated, the conditions in the HAVING clause are applied.</span></span> <span data-ttu-id="6b38f-105">Somente os grupos que atendem as condições são exibidos na consulta.</span><span class="sxs-lookup"><span data-stu-id="6b38f-105">Only the groups that meet the conditions appear in the query.</span></span>  
  
 <span data-ttu-id="6b38f-106">Por exemplo, você pode desejar ver o preço médio de todos os livros de cada editor em uma tabela `titles` , mas somente se o preço médio exceder R$ 10,00.</span><span class="sxs-lookup"><span data-stu-id="6b38f-106">For example, you might want to see the average price of all books for each publisher in a `titles` table, but only if the average price exceeds $10.00.</span></span> <span data-ttu-id="6b38f-107">Nesse caso, você pode especificar uma cláusula HAVING com uma condição, como `AVG(price) > 10`.</span><span class="sxs-lookup"><span data-stu-id="6b38f-107">In that case, you could specify a HAVING clause with a condition such as `AVG(price) > 10`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6b38f-108">Em algumas instâncias, você pode desejar excluir linhas individuais de grupos antes de aplicar uma condição a grupos como um todo.</span><span class="sxs-lookup"><span data-stu-id="6b38f-108">In some instances, you might want to exclude individual rows from groups before applying a condition to groups as a whole.</span></span> <span data-ttu-id="6b38f-109">Para obter detalhes, veja [Usar cláusulas HAVING e WHERE na mesma consulta &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6b38f-109">For details, see [Use HAVING and WHERE Clauses in the Same Query &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="6b38f-110">Você pode criar condições complexas para uma cláusula HAVING usando AND e OR para vincular condições.</span><span class="sxs-lookup"><span data-stu-id="6b38f-110">You can create complex conditions for a HAVING clause by using AND and OR to link conditions.</span></span> <span data-ttu-id="6b38f-111">Para obter detalhes sobre como usar AND e OR em critérios de pesquisa, consulte [Especificar vários critérios de pesquisa para uma coluna &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-one-column-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6b38f-111">For details about using AND and OR in search conditions, see [Specify Multiple Search Conditions for One Column &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-one-column-visual-database-tools.md).</span></span>  
  
### <a name="to-specify-a-condition-for-a-group"></a><span data-ttu-id="6b38f-112">Para especificar uma condição para um grupo</span><span class="sxs-lookup"><span data-stu-id="6b38f-112">To specify a condition for a group</span></span>  
  
1.  <span data-ttu-id="6b38f-113">Especifique os grupos para a sua consulta.</span><span class="sxs-lookup"><span data-stu-id="6b38f-113">Specify the groups for your query.</span></span> <span data-ttu-id="6b38f-114">Para obter detalhes, veja [Agrupar linhas em resultados da consulta &#40;Visual Database Tools&#41;](group-rows-in-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6b38f-114">For details, see [Group Rows in Query Results &#40;Visual Database Tools&#41;](group-rows-in-query-results-visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="6b38f-115">Se ainda não estiver no [Painel Critérios](criteria-pane-visual-database-tools.md), adicione a coluna em que você deseja basear a condição.</span><span class="sxs-lookup"><span data-stu-id="6b38f-115">If it is not already in the [Criteria pane](criteria-pane-visual-database-tools.md), add the column on which you want to base the condition.</span></span> <span data-ttu-id="6b38f-116">(Na maioria das vezes, a condição envolve uma coluna que já é um grupo ou uma coluna de resumo.) Você não pode usar uma coluna que não faça parte de uma função de agregação ou da cláusula GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="6b38f-116">(Most often the condition involves a column that is already a group or summary column.) You cannot use a column that is not part of an aggregate function or of the GROUP BY clause.</span></span>  
  
3.  <span data-ttu-id="6b38f-117">Na coluna **Filtro**, especifique a condição que será aplicada ao grupo.</span><span class="sxs-lookup"><span data-stu-id="6b38f-117">In the **Filter** column, specify the condition to apply to the group.</span></span>  
  
     <span data-ttu-id="6b38f-118">O [Designer de Consulta e Exibição](query-and-view-designer-tools-visual-database-tools.md) cria automaticamente uma cláusula HAVING na instrução no [Painel SQL](sql-pane-visual-database-tools.md), como no seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="6b38f-118">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) automatically creates a HAVING clause in the statement in the [SQL pane](sql-pane-visual-database-tools.md), such as in the following example:</span></span>  
  
    ```  
    SELECT pub_id, AVG(price)  
    FROM titles  
    GROUP BY pub_id  
    HAVING (AVG(price) > 10)  
  
    ```  
  
4.  <span data-ttu-id="6b38f-119">Repita as etapas 2 e 3 para cada condição adicional que você deseja especificar.</span><span class="sxs-lookup"><span data-stu-id="6b38f-119">Repeat steps 2 and 3 for each additional condition you want to specify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b38f-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6b38f-120">See Also</span></span>  
 [<span data-ttu-id="6b38f-121">Classificar e agrupar resultados da consulta &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="6b38f-121">Sort and Group Query Results &#40;Visual Database Tools&#41;</span></span>](sort-and-group-query-results-visual-database-tools.md)  
  
  
