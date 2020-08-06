---
title: Unir tabelas automaticamente (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- automatic joins
- joins [SQL Server], creating
- joins [SQL Server], automatic
ms.assetid: f152af82-bcb6-49ca-af19-48cdb7fc9ac6
author: stevestein
ms.author: sstein
ms.openlocfilehash: d05100f801d972759c1b5c105814f5cdbdccf84f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678496"
---
# <a name="join-tables-automatically-visual-database-tools"></a><span data-ttu-id="02e51-102">Unir tabelas automaticamente (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="02e51-102">Join Tables Automatically (Visual Database Tools)</span></span>
  <span data-ttu-id="02e51-103">Quando você adiciona duas ou mais tabelas a uma consulta, o [Designer de Consulta e Exibição](visual-database-tools.md) tenta determinar se elas estão relacionadas.</span><span class="sxs-lookup"><span data-stu-id="02e51-103">When you add two or more tables to a query, the [Query and View Designer](visual-database-tools.md) attempts to determine if they are related.</span></span> <span data-ttu-id="02e51-104">Se estiverem, o Designer de Consulta e Exibição unirá automaticamente linhas de junção entre os retângulos que representam as tabelas ou objetos estruturados por tabela.</span><span class="sxs-lookup"><span data-stu-id="02e51-104">If they are, the Query and View Designer automatically puts join lines between the rectangles representing the tables or table-structured objects.</span></span>  
  
 <span data-ttu-id="02e51-105">O Designer de Consulta e Exibição reconhecerá tabelas como unidas se:</span><span class="sxs-lookup"><span data-stu-id="02e51-105">The Query and View Designer will recognize tables as joined if:</span></span>  
  
-   <span data-ttu-id="02e51-106">O banco de dados contiver informações que especifica que as tabelas estão relacionadas.</span><span class="sxs-lookup"><span data-stu-id="02e51-106">The database contains information that specifies that the tables are related.</span></span>  
  
-   <span data-ttu-id="02e51-107">Se duas colunas, uma em cada tabela, tiverem o mesmo nome e tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="02e51-107">If two columns, one in each table, have the same name and data type.</span></span> <span data-ttu-id="02e51-108">A coluna deve ser uma chave primária em pelo menos uma das tabelas.</span><span class="sxs-lookup"><span data-stu-id="02e51-108">The column must be a primary key in at least one of the tables.</span></span> <span data-ttu-id="02e51-109">Por exemplo, se você adicionar as tabelas `employee` e `jobs` , se a coluna `job_id` for a chave primária na tabela `jobs` , e se cada tabela tiver uma coluna chamada `job_id` com o mesmo tipo de dados, o Designer de Consulta e Exibição unirá as tabelas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="02e51-109">For example, if you add `employee` and `jobs` tables, if the `job_id` column is the primary key in the `jobs` table, and if each table has a column called `job_id` with the same data type, the Query and View Designer will automatically join the tables.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="02e51-110">O Designer de Consulta e Exibição criará somente uma junção com base nas colunas com o mesmo nome e tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="02e51-110">The Query and View Designer will create only one join based on columns with the same name and data type.</span></span> <span data-ttu-id="02e51-111">Se for possível mais de uma união, o Designer de Consulta e Exibição será interrompido depois de criar uma união com base no primeiro conjunto de colunas coincidentes que encontrar.</span><span class="sxs-lookup"><span data-stu-id="02e51-111">If more than one join is possible, the Query and View Designer stops after creating a join based on the first set of matching columns that it finds.</span></span>  
  
-   <span data-ttu-id="02e51-112">O Designer de Consulta e Exibição detecta que um critério de pesquisa (uma cláusula WHERE) é, de fato, uma condição de junção.</span><span class="sxs-lookup"><span data-stu-id="02e51-112">The Query and View Designer detects that a search condition (a WHERE clause) is actually a join condition.</span></span> <span data-ttu-id="02e51-113">Por exemplo, você pode adicionar as tabelas `employee` e `jobs`e, depois criar um critério de pesquisa que procure o mesmo valor na coluna `job_id` das duas tabelas.</span><span class="sxs-lookup"><span data-stu-id="02e51-113">For example, you might add the tables `employee` and `jobs`, then create a search condition that searches for the same value in the `job_id` column of both tables.</span></span> <span data-ttu-id="02e51-114">Quando você fizer isso, o Designer de Consulta e Exibição detecta que o critério de pesquisa resulta em uma junção e, depois, cria uma condição de junção baseado no critério de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="02e51-114">When you do, the Query and View Designer detects that the search condition results in a join, and then creates a join condition based on the search condition.</span></span>  
  
 <span data-ttu-id="02e51-115">Se o Designer de Consulta e Exibição criou uma junção não adequada à sua consulta, você poderá modificar a junção ou removê-la.</span><span class="sxs-lookup"><span data-stu-id="02e51-115">If the Query and View Designer has created a join that is not suitable to your query, you can modify the join or remove it.</span></span> <span data-ttu-id="02e51-116">Para obter detalhes, consulte [Modificar operadores de junção &#40;Visual Database Tools&#41;](modify-join-operators-visual-database-tools.md) e [Remover junções &#40;Visual Database Tools&#41;](remove-joins-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="02e51-116">For details, see [Modify Join Operators &#40;Visual Database Tools&#41;](modify-join-operators-visual-database-tools.md) and [Remove Joins &#40;Visual Database Tools&#41;](remove-joins-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="02e51-117">Se o Designer de Consulta e Exibição não unir automaticamente as tabelas em sua consulta, você poderá criar uma junção.</span><span class="sxs-lookup"><span data-stu-id="02e51-117">If the Query and View Designer does not automatically join the tables in your query, you can create a join yourself.</span></span> <span data-ttu-id="02e51-118">Para obter detalhes, consulte [Unir tabelas manualmente &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="02e51-118">For details, see [Join Tables Manually &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02e51-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="02e51-119">See Also</span></span>  
 <span data-ttu-id="02e51-120">[Como o designer de consulta e exibição representa junções &#40;Visual Database Tools&#41;](how-the-query-and-view-designer-represents-joins-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="02e51-120">[How the Query and View Designer Represents Joins &#40;Visual Database Tools&#41;](how-the-query-and-view-designer-represents-joins-visual-database-tools.md) </span></span>  
 <span data-ttu-id="02e51-121">[Tópicos de instruções sobre como criar consultas e exibições &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="02e51-121">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="02e51-122">Consultar com junções &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="02e51-122">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
