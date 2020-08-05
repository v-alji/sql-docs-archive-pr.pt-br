---
title: Especificar condições de pesquisa (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- choosing search criteria
- search conditions [SQL Server], specifying
- search criteria [SQL Server], specifying conditions
ms.assetid: 18e2c759-68ec-4efe-b208-2f73418cd9bd
author: stevestein
ms.author: sstein
ms.openlocfilehash: aa5dab8326de079c385a3a508bc1b01b1ee1247d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573355"
---
# <a name="specify-search-conditions-visual-database-tools"></a><span data-ttu-id="c4efb-102">Especificar condições de pesquisa (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="c4efb-102">Specify Search Conditions (Visual Database Tools)</span></span>
  <span data-ttu-id="c4efb-103">Você pode especificar as linhas de dados que aparecem em sua consulta especificando critérios de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c4efb-103">You can specify the data rows that appear in your query by specifying search conditions.</span></span> <span data-ttu-id="c4efb-104">Por exemplo, se você estiver consultando uma tabela `employee` , será possível especificar que você quer localizar apenas os funcionários que trabalham em uma determinada região.</span><span class="sxs-lookup"><span data-stu-id="c4efb-104">For example, if you are querying an `employee` table, you can specify that you want to find only the employees who work in a particular region.</span></span>  
  
 <span data-ttu-id="c4efb-105">Você especifica critérios de pesquisa usando uma expressão.</span><span class="sxs-lookup"><span data-stu-id="c4efb-105">You specify search conditions using an expression.</span></span> <span data-ttu-id="c4efb-106">Geralmente, a expressão consiste em um operador e um valor de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c4efb-106">Most commonly the expression consists of an operator and a search value.</span></span> <span data-ttu-id="c4efb-107">Por exemplo, para localizar os funcionários em uma região de vendas em particular, você poderia especificar o seguinte critério de pesquisa para a coluna `region` :</span><span class="sxs-lookup"><span data-stu-id="c4efb-107">For example, to find employees in a particular sales region, you might specify the following search criterion for the `region` column:</span></span>  
  
```  
='UK'  
```  
  
> [!NOTE]  
>  <span data-ttu-id="c4efb-108">Se você estiver trabalhando com várias tabelas, o Designer de Consulta e Exibição examinará cada critério de pesquisa para determinar se a comparação que você está fazendo resulta em uma junção.</span><span class="sxs-lookup"><span data-stu-id="c4efb-108">If you are working with multiple tables, the Query and View Designer examines each search condition to determine whether the comparison you are making results in a join.</span></span> <span data-ttu-id="c4efb-109">Nesse caso, o Designer de Consulta e Exibição converte automaticamente o critério de pesquisa em uma junção.</span><span class="sxs-lookup"><span data-stu-id="c4efb-109">If so, the Query and View Designer automatically converts the search condition into a join.</span></span> <span data-ttu-id="c4efb-110">Para obter mais informações, consulte [Unir tabelas automaticamente &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c4efb-110">For more information, see [Join Tables Automatically &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
### <a name="to-specify-search-conditions"></a><span data-ttu-id="c4efb-111">Para especificar os critérios de pesquisa</span><span class="sxs-lookup"><span data-stu-id="c4efb-111">To specify search conditions</span></span>  
  
1.  <span data-ttu-id="c4efb-112">Se você ainda não o fez, adicione as colunas ou expressões que você quer usar no seu critério de pesquisa ao painel Critérios.</span><span class="sxs-lookup"><span data-stu-id="c4efb-112">If you have not done so already, add the columns or expressions that you want to use within your search condition to the Criteria pane.</span></span>  
  
     <span data-ttu-id="c4efb-113">Se você estiver criando uma consulta selecionada e não quiser que as colunas ou as expressões pesquisadas apareçam na saída da consulta, limpe a coluna **Saída** de cada coluna ou expressão e as remova como colunas de saída.</span><span class="sxs-lookup"><span data-stu-id="c4efb-113">If you are creating a Select query and do not want the search columns or expressions to appear in the query output, clear the **Output** column for each search column or expression to remove them as output columns.</span></span>  
  
2.  <span data-ttu-id="c4efb-114">Localize a linha que contém a coluna ou expressão de dados a ser pesquisada e, depois, na coluna **Filtro** insira um critério de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c4efb-114">Locate the row containing the data column or expression to search, and then in the **Filter** column, enter a search condition.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c4efb-115">Se você não inserir um operador, o Designer de Consulta e Exibição inserirá automaticamente o operador de igualdade "=".</span><span class="sxs-lookup"><span data-stu-id="c4efb-115">If you do not enter an operator, the Query and View Designer automatically inserts the equality operator "=".</span></span>  
  
 <span data-ttu-id="c4efb-116">O Designer de Consulta e Exibição atualiza a instrução SQL no [painel SQL](sql-pane-visual-database-tools.md) adicionado ou modificando a cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="c4efb-116">The Query and View Designer updates the SQL statement in the [SQL Pane](sql-pane-visual-database-tools.md) by adding or modifying the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4efb-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c4efb-117">See Also</span></span>  
 <span data-ttu-id="c4efb-118">[Regras para inserir valores de pesquisa &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="c4efb-118">[Rules for Entering Search Values &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="c4efb-119">Especificar critérios de pesquisa &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="c4efb-119">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
