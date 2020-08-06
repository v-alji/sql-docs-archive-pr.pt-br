---
title: Ferramentas do Designer de Consulta e Exibição (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.querydesigner
- vdt.pane.diagram
- vdt.pane.grid
- vdt.dlgbox.querybuilder
- vdt.pane.sql
- vdt.pane.results
helpviewer_keywords:
- Query Designer [SQL Server], panes
- View Designer, panes
- Query Designer [SQL Server], components
- View Designer, components
ms.assetid: 12e4b5a5-b793-4b6c-a0e5-c450c49bf26f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 29bd3fa9e171551197927aae0d1bc00446df6e7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683297"
---
# <a name="query-and-view-designer-tools-visual-database-tools"></a><span data-ttu-id="384e5-102">Ferramentas do Designer de Consulta e Exibição (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="384e5-102">Query and View Designer Tools (Visual Database Tools)</span></span>
  <span data-ttu-id="384e5-103">Quando você criar uma consulta, uma exibição, uma função embutida ou um único procedimento armazenado de instrução, o designer que você usa consiste em quatro painéis: painel diagrama , painel Critérios, painel SQL e painel Resultados.</span><span class="sxs-lookup"><span data-stu-id="384e5-103">When you design a query, view, in-line function, or single-statement stored procedure, the designer you use consists of four panes: the Diagram pane, the Criteria pane, the SQL pane, and the Results pane.</span></span>  
  
 <span data-ttu-id="384e5-104">![Designer de consultas](../../database-engine/media//vs-queryviewdsgpanes.gif "Designer de Consulta")</span><span class="sxs-lookup"><span data-stu-id="384e5-104">![Query Designer](../../database-engine/media//vs-queryviewdsgpanes.gif "Query Designer")</span></span>  
  
-   <span data-ttu-id="384e5-105">O painel Diagrama exibe as tabelas e outros objetos com valores de tabela que você está consultando.</span><span class="sxs-lookup"><span data-stu-id="384e5-105">The Diagram pane displays the tables and other table-valued objects that you are querying.</span></span> <span data-ttu-id="384e5-106">Cada retângulo representa uma tabela ou um objeto com valor de tabela e mostra as colunas de dados disponíveis.</span><span class="sxs-lookup"><span data-stu-id="384e5-106">Each rectangle represents a table or table-valued object and shows the available data columns.</span></span> <span data-ttu-id="384e5-107">Junções são indicadas por linhas entre os retângulos.</span><span class="sxs-lookup"><span data-stu-id="384e5-107">Joins are indicated by lines between the rectangles.</span></span> <span data-ttu-id="384e5-108">Para obter mais informações, consulte [Painel Diagrama &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="384e5-108">For more information, see [Diagram Pane &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
-   <span data-ttu-id="384e5-109">O painel Critérios contém uma grade do tipo planilha na qual você especifica opções, como colunas de dados para exibição, linhas a serem selecionadas, como agrupar linhas, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="384e5-109">The Criteria pane contains a spreadsheet-like grid in which you specify options, such as which data columns to display, what rows to select, how to group rows, and so on.</span></span> <span data-ttu-id="384e5-110">Para obter mais informações, consulte [Painel Critérios &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="384e5-110">For more information, see [Criteria Pane &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md).</span></span>  
  
-   <span data-ttu-id="384e5-111">O painel SQL exibe a instrução SQL para a consulta ou exibição.</span><span class="sxs-lookup"><span data-stu-id="384e5-111">The SQL pane displays the SQL statement for the query or view.</span></span> <span data-ttu-id="384e5-112">Você pode editar a instrução SQL criada pelo Designer ou pode inserir a sua própria instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="384e5-112">You can edit the SQL statement created by the Designer or you can enter your own SQL statement.</span></span> <span data-ttu-id="384e5-113">É particularmente útil inserir instruções SQL que não possam ser criadas pelos painéis Diagrama e Critério, como consultas de união.</span><span class="sxs-lookup"><span data-stu-id="384e5-113">It is particularly useful for entering SQL statements that cannot be created using the Diagram and Criteria panes, such as union queries.</span></span> <span data-ttu-id="384e5-114">Para obter mais informações, consulte [Painel SQL &#40;Visual Database Tools&#41;](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="384e5-114">For more information, see [SQL Pane &#40;Visual Database Tools&#41;](sql-pane-visual-database-tools.md).</span></span>  
  
-   <span data-ttu-id="384e5-115">O painel Resultados mostra uma grade com dados recuperados pela consulta ou exibição.</span><span class="sxs-lookup"><span data-stu-id="384e5-115">The Results pane shows a grid with data retrieved by the query or view.</span></span> <span data-ttu-id="384e5-116">No Designer de Consulta e Exibição, o painel mostra os resultados da consulta de SELECT executada mais recentemente.</span><span class="sxs-lookup"><span data-stu-id="384e5-116">In the Query and View Designer, the pane shows the results of the most recently executed SELECT query.</span></span> <span data-ttu-id="384e5-117">Você pode modificar o banco de dados editando valores nas células da grade e pode adicionar ou excluir linhas.</span><span class="sxs-lookup"><span data-stu-id="384e5-117">You can modify the database by editing values in the cells of the grid, and you can add or delete rows.</span></span> <span data-ttu-id="384e5-118">Para obter mais informações, consulte [Painel de Resultados &#40;Visual Database Tools&#41;](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="384e5-118">For more information, see [Results Pane &#40;Visual Database Tools&#41;](results-pane-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="384e5-119">Você pode criar uma consulta ou exibição trabalhando em qualquer painel: é possível especificar uma coluna a ser exibida, escolhendo-a no painel Diagrama, inserindo-a no painel Critérios ou tornando-a parte da instrução SQL no painel SQL.</span><span class="sxs-lookup"><span data-stu-id="384e5-119">You can create a query or view by working in any of the panes: you can specify a column to display by choosing it in the Diagram pane, entering it into the Criteria pane, or making it part of the SQL statement in the SQL pane.</span></span>  
  
## <a name="displaying-and-hiding-panes"></a><span data-ttu-id="384e5-120">Exibindo e ocultando painéis</span><span class="sxs-lookup"><span data-stu-id="384e5-120">Displaying and Hiding Panes</span></span>  
 <span data-ttu-id="384e5-121">Para ocultar ou exibir um painel que não esteja visível, clique com o botão direito do mouse na superfície de design, aponte para **Painel**e clique no nome do painel.</span><span class="sxs-lookup"><span data-stu-id="384e5-121">To hide a pane or display a pane that is not visible, right-click the design surface, point to **Pane**, and then click the name of the pane.</span></span> <span data-ttu-id="384e5-122">Se o Designer de Consulta e Exibição for aberto em modo Designer de Consultas, o painel de **Resultados** não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="384e5-122">If the Query and View Designer is opened in Query Designer mode, the **Results** pane is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="384e5-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="384e5-123">See Also</span></span>  
 <span data-ttu-id="384e5-124">[Tópicos de instruções sobre como criar consultas e exibições &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="384e5-124">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="384e5-125">[Abra o designer de consulta e exibição &#40;Visual Database Tools&#41;](open-the-query-and-view-designer-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="384e5-125">[Open the Query and View Designer &#40;Visual Database Tools&#41;](open-the-query-and-view-designer-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="384e5-126">Editor SQL &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="384e5-126">SQL Editor &#40;Visual Database Tools&#41;</span></span>](sql-editor-visual-database-tools.md)  
  
  
