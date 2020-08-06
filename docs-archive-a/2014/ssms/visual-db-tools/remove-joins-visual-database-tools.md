---
title: Remover junções (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- removing joins
- joins [SQL Server], removing
- deleting joins
ms.assetid: ccc212a1-fd13-48d6-85e5-5ff310c34bbd
author: stevestein
ms.author: sstein
ms.openlocfilehash: b037e317b629671f6ec5ea1fa90edfca6fafa627
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568279"
---
# <a name="remove-joins-visual-database-tools"></a><span data-ttu-id="57d2e-102">Remover Junções (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="57d2e-102">Remove Joins (Visual Database Tools)</span></span>
  <span data-ttu-id="57d2e-103">Se você não quer unir tabelas por uma junção interna ou uma junção externa, você pode remover a junção entre elas.</span><span class="sxs-lookup"><span data-stu-id="57d2e-103">If you do not want tables to be joined via an inner join or an outer join, you can remove the join between them.</span></span> <span data-ttu-id="57d2e-104">Por exemplo, você pode remover uma junção que o [Designer de Consulta e Exibição](visual-database-tools.md) criou automaticamente entre duas tabelas.</span><span class="sxs-lookup"><span data-stu-id="57d2e-104">For example, you might remove a join that the [Query and View Designer](visual-database-tools.md) has been created automatically between two tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="57d2e-105">Remover uma junção de uma consulta não altera a relação subjacente no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="57d2e-105">Removing a join from a query does not alter the underlying relationship in the database.</span></span>  
  
 <span data-ttu-id="57d2e-106">Se duas tabelas unidas fazem parte de sua consulta e você remove todas as condições de junção entre elas, a consulta resultante se torna o produto das duas tabelas – ou seja, se torna uma CROSS JOIN.</span><span class="sxs-lookup"><span data-stu-id="57d2e-106">If two joined tables are part of your query and you remove all join conditions between them, the resulting query becomes the product of both tables - that is, it becomes a CROSS JOIN.</span></span>  
  
### <a name="to-remove-a-join"></a><span data-ttu-id="57d2e-107">Para remover uma junção</span><span class="sxs-lookup"><span data-stu-id="57d2e-107">To remove a join</span></span>  
  
-   <span data-ttu-id="57d2e-108">No [painel Diagrama](diagram-pane-visual-database-tools.md), selecione a linha de junção para a junção a ser removida e pressione a tecla DELETE.</span><span class="sxs-lookup"><span data-stu-id="57d2e-108">In the [Diagram pane](diagram-pane-visual-database-tools.md), select the join line for the join to remove, and then press the DELETE key.</span></span> <span data-ttu-id="57d2e-109">Você pode selecionar e excluir várias linhas de junção de uma vez.</span><span class="sxs-lookup"><span data-stu-id="57d2e-109">You can select and delete multiple join lines at one time.</span></span>  
  
 <span data-ttu-id="57d2e-110">O Designer de Consulta e Exibição remove a linha de junção e altera a instrução no [painel SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="57d2e-110">The Query and View Designer removes the join line and alters the statement in the [SQL pane](sql-pane-visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57d2e-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="57d2e-111">See Also</span></span>  
 <span data-ttu-id="57d2e-112">[Unir tabelas automaticamente &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="57d2e-112">[Join Tables Automatically &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md) </span></span>  
 <span data-ttu-id="57d2e-113">[Unir tabelas manualmente &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="57d2e-113">[Join Tables Manually &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="57d2e-114">Consultar com junções &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="57d2e-114">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
