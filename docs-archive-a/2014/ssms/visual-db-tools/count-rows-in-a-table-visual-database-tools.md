---
title: Contar linhas em uma tabela (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- totals [SQL Server], row counts
- row counts [SQL Server]
- column values [SQL Server]
- number of rows
- number of values
- counting rows
ms.assetid: dda4296a-1d16-4e77-8d6f-e295f6dd4e87
author: stevestein
ms.author: sstein
ms.openlocfilehash: f6dca92fb955b776f56d9b51f28b1a486b89f18f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680724"
---
# <a name="count-rows-in-a-table-visual-database-tools"></a><span data-ttu-id="60273-102">Contar linhas em uma tabela (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="60273-102">Count Rows in a Table (Visual Database Tools)</span></span>
  <span data-ttu-id="60273-103">Você pode contar linhas em uma tabela para determinar:</span><span class="sxs-lookup"><span data-stu-id="60273-103">You can count rows in a table to determine:</span></span>  
  
-   <span data-ttu-id="60273-104">O número total de linhas em uma tabela, por exemplo, uma conta de todos os livros em uma tabela `titles` .</span><span class="sxs-lookup"><span data-stu-id="60273-104">The total number of rows in a table, for example, a count of all the books in a `titles` table.</span></span>  
  
-   <span data-ttu-id="60273-105">O número de linhas em uma tabela que atenda uma condição específica, por exemplo, o número de livros publicados por um publicador em uma tabela `titles` .</span><span class="sxs-lookup"><span data-stu-id="60273-105">The number of rows in a table that meet a specific condition, for example, the number of books by one publisher in a `titles` table.</span></span>  
  
-   <span data-ttu-id="60273-106">O número de valores em uma coluna particular.</span><span class="sxs-lookup"><span data-stu-id="60273-106">The number of values in a particular column.</span></span>  
  
 <span data-ttu-id="60273-107">Quando você conta valores em uma coluna, nulos não são incluídos na conta.</span><span class="sxs-lookup"><span data-stu-id="60273-107">When you count values in a column, nulls are not included in the count.</span></span> <span data-ttu-id="60273-108">Por exemplo, você pode contar o número de livros em uma tabela `titles` que tenha valores na coluna `advance` .</span><span class="sxs-lookup"><span data-stu-id="60273-108">For example, you might count the number of books in a `titles` table that have values in the `advance` column.</span></span> <span data-ttu-id="60273-109">Por padrão, a conta inclui todos os valores, não apenas valores exclusivos.</span><span class="sxs-lookup"><span data-stu-id="60273-109">By default, the count includes all values, not just unique values.</span></span>  
  
 <span data-ttu-id="60273-110">Os procedimentos para todos os três tipos de contas são semelhantes.</span><span class="sxs-lookup"><span data-stu-id="60273-110">The procedures for all three types of counts are similar.</span></span>  
  
### <a name="to-count-all-the-rows-in-a-table"></a><span data-ttu-id="60273-111">Para contar todas as linhas em uma tabela</span><span class="sxs-lookup"><span data-stu-id="60273-111">To count all the rows in a table</span></span>  
  
1.  <span data-ttu-id="60273-112">Certifique-se de que a tabela que você quer resumir já está presente no painel Diagrama.</span><span class="sxs-lookup"><span data-stu-id="60273-112">Be sure the table you want to summarize is already present in the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="60273-113">Clique com o botão direito do mouse na tela de fundo do painel Diagrama e escolha **Adicionar Grupo por** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="60273-113">Right-click the background of the Diagram pane, then choose **Add Group By** from the shortcut menu.</span></span> <span data-ttu-id="60273-114">O [Designer de Consulta e Exibição](visual-database-tools.md) adicionará a coluna **Agrupar por** à grade do painel Critérios.</span><span class="sxs-lookup"><span data-stu-id="60273-114">The [Query and View Designer](visual-database-tools.md) adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="60273-115">Selecione \*\* \* (todas as colunas)\*\* no retângulo que representa a tabela ou o objeto com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="60273-115">Select **\* (All Columns)** in the rectangle representing the table or table-valued object.</span></span>  
  
     <span data-ttu-id="60273-116">O Designer de Consulta e Exibição preenche automaticamente o termo **Contagem** na coluna **Agrupar por** no painel de critérios e atribui um alias de coluna à coluna que você está resumindo.</span><span class="sxs-lookup"><span data-stu-id="60273-116">The Query and View Designer automatically fills the term **Count** into the **Group By** column in the Criteria pane and assigns a column alias to the column you are summarizing.</span></span> <span data-ttu-id="60273-117">Você pode substituir esse alias gerado automaticamente por outro que tenha mais significado.</span><span class="sxs-lookup"><span data-stu-id="60273-117">You can replace this automatically generated alias with a more meaningful one.</span></span> <span data-ttu-id="60273-118">Para obter mais detalhes, veja [Criar aliases de coluna &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="60273-118">For more details, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
4.  <span data-ttu-id="60273-119">Executa a consulta.</span><span class="sxs-lookup"><span data-stu-id="60273-119">Run the query.</span></span>  
  
### <a name="to-count-all-the-rows-that-meet-a-condition"></a><span data-ttu-id="60273-120">Para contar todas as linhas que atendam uma condição</span><span class="sxs-lookup"><span data-stu-id="60273-120">To count all the rows that meet a condition</span></span>  
  
1.  <span data-ttu-id="60273-121">Certifique-se de que a tabela que você quer resumir já está presente no painel Diagrama.</span><span class="sxs-lookup"><span data-stu-id="60273-121">Be sure the table you want to summarize is already present in the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="60273-122">Clique com o botão direito do mouse na tela de fundo do painel Diagrama e escolha **Adicionar Grupo por** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="60273-122">Right-click the background of the Diagram pane, then choose **Add Group By** from the shortcut menu.</span></span> <span data-ttu-id="60273-123">O Designer de Consulta e Exibição adicionará a coluna **Agrupar por** à grade do Painel de Critérios.</span><span class="sxs-lookup"><span data-stu-id="60273-123">The Query and View Designer adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="60273-124">Selecione \*\* \* (todas as colunas)\*\* no retângulo que representa a tabela ou o objeto estruturado por tabela.</span><span class="sxs-lookup"><span data-stu-id="60273-124">Select **\*(All Columns)** in the rectangle representing the table or table-structured object.</span></span>  
  
     <span data-ttu-id="60273-125">O Designer de Consulta e Exibição preenche automaticamente o termo **Contagem** na coluna **Agrupar por** no painel de critérios e atribui um alias de coluna à coluna que você está resumindo.</span><span class="sxs-lookup"><span data-stu-id="60273-125">The Query and View Designer automatically fills the term **Count** into the **Group By** column in the Criteria pane and assigns a column alias to the column you are summarizing.</span></span> <span data-ttu-id="60273-126">Para criar um título de coluna mais útil na saída da consulta, consulte [Criar aliases de coluna &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="60273-126">To create a more useful column heading in query output, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
4.  <span data-ttu-id="60273-127">Adicione a coluna de dados que você quer pesquisar e desmarque a caixa de seleção na coluna **Saída**.</span><span class="sxs-lookup"><span data-stu-id="60273-127">Add the data column that you want to search, and then clear the check box in the **Output** column.</span></span>  
  
     <span data-ttu-id="60273-128">O Designer de Consulta e Exibição preenche automaticamente o termo **Agrupar por** na coluna **Agrupar por** da grade.</span><span class="sxs-lookup"><span data-stu-id="60273-128">The Query and View Designer automatically fills the term **Group By** into the **Group By** column of the grid.</span></span>  
  
5.  <span data-ttu-id="60273-129">Altere **Agrupar por** na coluna **Agrupar por** para **Onde**.</span><span class="sxs-lookup"><span data-stu-id="60273-129">Change **Group By** in the **Group By** column to **Where**.</span></span>  
  
6.  <span data-ttu-id="60273-130">Na coluna **Filtro** para a coluna de dados a ser pesquisada, insira o critério da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="60273-130">In the **Filter** column for the data column to search, enter the search condition.</span></span>  
  
7.  <span data-ttu-id="60273-131">Executa a consulta.</span><span class="sxs-lookup"><span data-stu-id="60273-131">Run the query.</span></span>  
  
### <a name="to-count-the-values-in-a-column"></a><span data-ttu-id="60273-132">Para contar os valores em uma coluna.</span><span class="sxs-lookup"><span data-stu-id="60273-132">To count the values in a column</span></span>  
  
1.  <span data-ttu-id="60273-133">Certifique-se de que a tabela que você quer resumir já está presente no painel Diagrama.</span><span class="sxs-lookup"><span data-stu-id="60273-133">Be sure the table you want to summarize is already present in the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="60273-134">Clique com o botão direito do mouse na tela de fundo do painel Diagrama e escolha **Adicionar Grupo por** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="60273-134">Right-click the background of the Diagram pane, then choose **Add Group By** from the shortcut menu.</span></span> <span data-ttu-id="60273-135">O Designer de Consulta e Exibição adicionará a coluna **Agrupar por** à grade do Painel de Critérios.</span><span class="sxs-lookup"><span data-stu-id="60273-135">The Query and View Designer adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="60273-136">Acrescente a coluna que você quer contar ao painel Critérios.</span><span class="sxs-lookup"><span data-stu-id="60273-136">Add the column that you want to count to the Criteria pane.</span></span>  
  
     <span data-ttu-id="60273-137">O Designer de Consulta e Exibição preenche automaticamente o termo **Agrupar por** na coluna **Agrupar por** da grade.</span><span class="sxs-lookup"><span data-stu-id="60273-137">The Query and View Designer automatically fills the term **Group By** into the **Group By** column of the grid.</span></span>  
  
4.  <span data-ttu-id="60273-138">Altere **Agrupar por** na coluna **Agrupar por** para **Contagem**.</span><span class="sxs-lookup"><span data-stu-id="60273-138">Change **Group By** in the **Group By** column to **Count**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="60273-139">Para contar apenas valores exclusivos, escolha **Distinção de Contagem**.</span><span class="sxs-lookup"><span data-stu-id="60273-139">To count only unique values, choose **Count Distinct**.</span></span>  
  
5.  <span data-ttu-id="60273-140">Executa a consulta.</span><span class="sxs-lookup"><span data-stu-id="60273-140">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60273-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="60273-141">See Also</span></span>  
 <span data-ttu-id="60273-142">[Classificar e agrupar resultados de consulta &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="60273-142">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="60273-143">Resumir resultados da consulta &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="60273-143">Summarize Query Results &#40;Visual Database Tools&#41;</span></span>](summarize-query-results-visual-database-tools.md)  
  
  
