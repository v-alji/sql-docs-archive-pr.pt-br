---
title: Resumir os resultados da consulta (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- summarizing query results
- queries [SQL Server], results
- aggregate queries [SQL Server]
ms.assetid: c9e15350-ed57-4d95-814d-815fbebfd86b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 08713be2d4439e520df07ec5efd6cb761a78a994
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683276"
---
# <a name="summarize-query-results-visual-database-tools"></a><span data-ttu-id="4512e-102">Resumir resultados da consulta (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="4512e-102">Summarize Query Results (Visual Database Tools)</span></span>
  <span data-ttu-id="4512e-103">Quando você cria consultas de agregação, certos princípios lógicos se aplicam.</span><span class="sxs-lookup"><span data-stu-id="4512e-103">When you create aggregate queries, certain logical principles apply.</span></span> <span data-ttu-id="4512e-104">Por exemplo, você não pode exibir o conteúdo de linhas individuais em uma consulta resumida.</span><span class="sxs-lookup"><span data-stu-id="4512e-104">For example, you cannot display the contents of individual rows in a summary query.</span></span> <span data-ttu-id="4512e-105">O Designer de Consulta e Exibição o ajuda a seguir esses princípios segundo a maneira como o [painel de Diagrama](visual-database-tools.md) e o [painel Critérios](criteria-pane-visual-database-tools.md) se comportam.</span><span class="sxs-lookup"><span data-stu-id="4512e-105">The Query and View Designer helps you comply with these principles in the way the [Diagram pane](visual-database-tools.md) and [Criteria pane](criteria-pane-visual-database-tools.md) behave.</span></span>  
  
 <span data-ttu-id="4512e-106">Compreendendo os princípios de consultas de agregação e o comportamento do Designer de Consulta e Exibição, você pode criar consultas de agregação logicamente corretas.</span><span class="sxs-lookup"><span data-stu-id="4512e-106">By understanding the principles of aggregate queries and the Query and View Designer's behavior, you can create logically correct aggregate queries.</span></span> <span data-ttu-id="4512e-107">O princípio prioritário é que consultas de agregação podem resultar apenas em informações resumidas.</span><span class="sxs-lookup"><span data-stu-id="4512e-107">The overriding principle is that aggregate queries can result only in summary information.</span></span> <span data-ttu-id="4512e-108">Assim, a maioria dos princípios que se seguem descreve as maneiras como você pode referenciar colunas de dados individuais dentro de uma consulta de agregação.</span><span class="sxs-lookup"><span data-stu-id="4512e-108">Thus, most of the principles that follow describe the ways that you can reference individual data columns within an aggregate query.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4512e-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="4512e-109">In This Section</span></span>  
 [<span data-ttu-id="4512e-110">Trabalhar com colunas em consultas de agregação &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="4512e-110">Work with Columns in Aggregate Queries &#40;Visual Database Tools&#41;</span></span>](work-with-columns-in-aggregate-queries-visual-database-tools.md)  
 <span data-ttu-id="4512e-111">Descreve conceitos sobre como agrupar e resumir colunas com as cláusulas GROUP BY, WHERE e HAVING.</span><span class="sxs-lookup"><span data-stu-id="4512e-111">Describes concepts about grouping and summarizing columns with the GROUP BY, WHERE, and HAVING clauses.</span></span>  
  
 [<span data-ttu-id="4512e-112">Contar linhas em uma tabela &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="4512e-112">Count Rows in a Table &#40;Visual Database Tools&#41;</span></span>](count-rows-in-a-table-visual-database-tools.md)  
 <span data-ttu-id="4512e-113">Fornece etapas para contar o número de linhas em uma tabela ou o número das linhas de uma tabela que atendem a um conjunto de critérios.</span><span class="sxs-lookup"><span data-stu-id="4512e-113">Provides steps for counting the number of rows in a table or the number of rows in a table that meet a set of criteria.</span></span>  
  
 [<span data-ttu-id="4512e-114">Resumir ou agregar valores para todas as linhas em uma tabela &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="4512e-114">Summarize or Aggregate Values for All Rows in a Table &#40;Visual Database Tools&#41;</span></span>](summarize-or-aggregate-values-for-all-rows-in-a-table-visual-database-tools.md)  
 <span data-ttu-id="4512e-115">Oferece etapas para resumir todas as linhas, em vez de um conjunto de linhas agrupadas.</span><span class="sxs-lookup"><span data-stu-id="4512e-115">Provides steps for summarizing all rows rather than for a set of grouped rows.</span></span>  
  
 [<span data-ttu-id="4512e-116">Resumir ou agregar valores usando expressões personalizadas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="4512e-116">Summarize or Aggregate Values Using Custom Expressions &#40;Visual Database Tools&#41;</span></span>](summarize-or-aggregate-values-using-custom-expressions-visual-database-tools.md)  
 <span data-ttu-id="4512e-117">Oferece etapas para usar expressões para resumir ou agregar, em vez de usar as cláusulas predefinidas.</span><span class="sxs-lookup"><span data-stu-id="4512e-117">Provides steps for using expressions to summarize or aggregate rather than using the predefined clauses.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4512e-118">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="4512e-118">Related Sections</span></span>  
 [<span data-ttu-id="4512e-119">Tópicos de instruções de como criar consultas e exibições &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="4512e-119">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
 <span data-ttu-id="4512e-120">Oferece links para tópicos que cobrem o modo de usar o Designer de Consulta e Exibição.</span><span class="sxs-lookup"><span data-stu-id="4512e-120">Provides links to topics covering how to use the Query and View Designer.</span></span>  
  
  
