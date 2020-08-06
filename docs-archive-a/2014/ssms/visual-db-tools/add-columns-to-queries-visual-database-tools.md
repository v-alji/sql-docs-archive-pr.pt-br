---
title: Adicionar colunas a consultas (Ferramentas de Banco de Dados Visual) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- inserting columns
- columns [SQL Server], adding
- queries [SQL Server], columns
- adding columns
ms.assetid: 82f3ba72-3d72-4fb1-8179-2a953a782787
author: stevestein
ms.author: sstein
ms.openlocfilehash: 49c6e575eea2d4437be1f16b400ca22120471fcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571770"
---
# <a name="add-columns-to-queries-visual-database-tools"></a><span data-ttu-id="393a1-102">Adicionar colunas a consultas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="393a1-102">Add Columns to Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="393a1-103">Para usar uma coluna em uma consulta, você deve adicioná-la à consulta.</span><span class="sxs-lookup"><span data-stu-id="393a1-103">To use a column in a query, you must add it to the query.</span></span> <span data-ttu-id="393a1-104">Você pode adicionar uma coluna para exibi-la na saída da consulta, usá-la para ordenar, pesquisar os conteúdos da coluna, ou para resumir seus conteúdos.</span><span class="sxs-lookup"><span data-stu-id="393a1-104">You might add a column to display it in query output, to use it for sorting, to search the contents of the column, or to summarize its contents.</span></span> <span data-ttu-id="393a1-105">Você pode decidir qual das colunas usadas na consulta será incluída no painel de resultados quando a consulta for executada.</span><span class="sxs-lookup"><span data-stu-id="393a1-105">You can decide which of the columns you use in the query are included in the results pane when the query is run.</span></span> <span data-ttu-id="393a1-106">Para obter mais informações, veja [Remover colunas de resultados da consulta &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="393a1-106">For more information see [Remove Columns from Query Results &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="393a1-107">Para exibir o tipo de dados de uma coluna no Designer de Consulta e Exibição, selecione a tabela ou objeto avaliado pela tabela no **Painel de Diagrama** e na janela de propriedades clique em Lista de Colunas.</span><span class="sxs-lookup"><span data-stu-id="393a1-107">To view the data type of a column in Query and View Designer; select the table or table-valued object in the **Diagram Pane** and in the properties window click Column List.</span></span> <span data-ttu-id="393a1-108">Em seguida, clique nas **reticências (...)** para abrir a caixa de diálogo **Lista de Colunas**.</span><span class="sxs-lookup"><span data-stu-id="393a1-108">Then click the **ellipses (...)** to open the **Column List** dialog box.</span></span>  
  
 <span data-ttu-id="393a1-109">Sempre que você usar uma coluna em uma consulta, você pode também usar uma expressão que consiste em qualquer combinação de colunas, literais, operadores e funções.</span><span class="sxs-lookup"><span data-stu-id="393a1-109">Wherever you use a column in a query, you can also use an expression that can consist of any combination of columns, literals, operators, and functions.</span></span>  
  
### <a name="to-add-an-individual-column"></a><span data-ttu-id="393a1-110">Para adicionar uma coluna individual</span><span class="sxs-lookup"><span data-stu-id="393a1-110">To add an individual column</span></span>  
  
-   <span data-ttu-id="393a1-111">No **Painel de Diagrama**, marque a caixa de seleção próxima à coluna que você quer incluir.</span><span class="sxs-lookup"><span data-stu-id="393a1-111">In the **Diagram Pane**, select the check box next to the column that you want to include.</span></span>  
  
     <span data-ttu-id="393a1-112">-ou-</span><span class="sxs-lookup"><span data-stu-id="393a1-112">-or-</span></span>  
  
-   <span data-ttu-id="393a1-113">No **Painel Critérios**, mova para a primeira linha de grade em branco, clique no campo da coluna **Coluna** e selecione um nome de coluna na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="393a1-113">In the **Criteria Pane**, move to the first blank grid row, click the field in the **Column** column, and select a column name from the drop-down list.</span></span>  
  
### <a name="to-add-all-columns-for-one-table-or-table-valued-object"></a><span data-ttu-id="393a1-114">Para adicionar todas as colunas de uma tabela ou objeto avaliado por tabela</span><span class="sxs-lookup"><span data-stu-id="393a1-114">To add all columns for one table or table-valued object</span></span>  
  
-   <span data-ttu-id="393a1-115">No **painel Diagrama**, marque a caixa de seleção ao lado de \*\* \* (todas as colunas)\*\*.</span><span class="sxs-lookup"><span data-stu-id="393a1-115">In the **Diagram Pane**, select the check box next to **\*(All Columns)**.</span></span>  
  
### <a name="to-add-all-columns-for-all-tables-and-table-structured-objects"></a><span data-ttu-id="393a1-116">Para adicionar todas as colunas para todas as tabelas e objetos estruturados por tabela</span><span class="sxs-lookup"><span data-stu-id="393a1-116">To add all columns for all tables and table-structured objects</span></span>  
  
1.  <span data-ttu-id="393a1-117">Verifique se nenhuma linha de junção está selecionada no **Painel de Operações de Tabela** .</span><span class="sxs-lookup"><span data-stu-id="393a1-117">Make sure no join lines in the **Table Operations Pane** are selected.</span></span>  
  
2.  <span data-ttu-id="393a1-118">Clique com o botão direito do mouse no espaço em branco da janela Design e escolha **Propriedades** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="393a1-118">Right-click in the empty space of the Design window and choose **Properties** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="393a1-119">Na janela Propriedades, clique em **Todas as colunas de saída** e escolha **Sim** ou **Não** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="393a1-119">In the Properties window click **Output all columns** and choose **Yes** or **No** from the dropdown list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="393a1-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="393a1-120">See Also</span></span>  
 <span data-ttu-id="393a1-121">[Remover colunas dos resultados da consulta &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="393a1-121">[Remove Columns from Query Results &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="393a1-122">[Remover colunas de consultas &#40;Visual Database Tools&#41;](remove-columns-from-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="393a1-122">[Remove Columns from Queries &#40;Visual Database Tools&#41;](remove-columns-from-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="393a1-123">[Especificar critérios de pesquisa &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="393a1-123">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 <span data-ttu-id="393a1-124">[Resumir os resultados da consulta &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="393a1-124">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="393a1-125">Executar operações básicas com consultas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="393a1-125">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
