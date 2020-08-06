---
title: Criar aliases de coluna (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], aliases
- aliases [SQL Server], columns
ms.assetid: e2e1c166-8ea7-47a2-b6a7-e419bf0fa3bb
author: stevestein
ms.author: sstein
ms.openlocfilehash: febe7ed27ed10a283cab549bc65299577d69761c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571754"
---
# <a name="create-column-aliases-visual-database-tools"></a><span data-ttu-id="7ad83-102">Criar aliases de coluna (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="7ad83-102">Create Column Aliases (Visual Database Tools)</span></span>
  <span data-ttu-id="7ad83-103">Você pode criar aliases para nomes de coluna para tornar mais fácil o trabalho com nomes de colunas, cálculos e valores de resumo.</span><span class="sxs-lookup"><span data-stu-id="7ad83-103">You can create aliases for column names to make it easier to work with column names, calculations, and summary values.</span></span> <span data-ttu-id="7ad83-104">Por exemplo, você pode criar um alias de coluna para:</span><span class="sxs-lookup"><span data-stu-id="7ad83-104">For example, you can create a column alias to:</span></span>  
  
-   <span data-ttu-id="7ad83-105">Criar um nome de coluna, tal como "Total Amount", para uma expressão como `(quantity * unit_price)` ou para uma função de agregação.</span><span class="sxs-lookup"><span data-stu-id="7ad83-105">Create a column name, such as "Total Amount," for an expression such as `(quantity * unit_price)` or for an aggregate function.</span></span>  
  
-   <span data-ttu-id="7ad83-106">Criar um formulário resumido de um nome de coluna, como `"d_id"` para `"discounts.stor_id."`</span><span class="sxs-lookup"><span data-stu-id="7ad83-106">Create a shortened form of a column name, such as `"d_id"` for `"discounts.stor_id."`</span></span>  
  
 <span data-ttu-id="7ad83-107">Após ter definido um alias de coluna, você pode usar o alias em uma consulta Select para especificar a saída de consulta.</span><span class="sxs-lookup"><span data-stu-id="7ad83-107">After you have defined a column alias, you can use the alias in a Select query to specify query output.</span></span>  
  
### <a name="to-create-a-column-alias"></a><span data-ttu-id="7ad83-108">Para criar um alias de coluna</span><span class="sxs-lookup"><span data-stu-id="7ad83-108">To create a column alias</span></span>  
  
1.  <span data-ttu-id="7ad83-109">No **Painel de Critérios**, localize a linha contendo a coluna de dados para a qual você quer criar um alias e, caso necessário, marque-a para saída.</span><span class="sxs-lookup"><span data-stu-id="7ad83-109">In the **Criteria Pane**, locate the row containing the data column for which you want to create an alias, and if necessary, mark it for output.</span></span> <span data-ttu-id="7ad83-110">Se a coluna de dados já não estiver na grade, acrescente-a.</span><span class="sxs-lookup"><span data-stu-id="7ad83-110">If the data column is not already in the grid, add it.</span></span>  
  
2.  <span data-ttu-id="7ad83-111">Na coluna **Alias** para aquela linha, insira o alias.</span><span class="sxs-lookup"><span data-stu-id="7ad83-111">In the **Alias** column for that row, enter the alias.</span></span> <span data-ttu-id="7ad83-112">O alias deve seguir todas as convenções de nomenclatura SQL.</span><span class="sxs-lookup"><span data-stu-id="7ad83-112">The alias must follow all naming conventions for SQL.</span></span> <span data-ttu-id="7ad83-113">Se o nome de alias que você entrar contiver espaços, o Designer de Consulta e Visualização coloca delimitadores automaticamente ao redor dele.</span><span class="sxs-lookup"><span data-stu-id="7ad83-113">If the alias name you enter contains spaces, the Query and View Designer automatically puts delimiters around it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ad83-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7ad83-114">See Also</span></span>  
 <span data-ttu-id="7ad83-115">[Adicionar colunas a consultas &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="7ad83-115">[Add Columns to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="7ad83-116">[Classificar e agrupar resultados de consulta &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="7ad83-116">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 <span data-ttu-id="7ad83-117">[Resumir os resultados da consulta &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="7ad83-117">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="7ad83-118">Executar operações básicas com consultas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="7ad83-118">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
