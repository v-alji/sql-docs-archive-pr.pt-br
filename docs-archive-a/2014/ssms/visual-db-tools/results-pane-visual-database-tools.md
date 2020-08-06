---
title: Painel de Resultados (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- View Designer, Results pane
- result sets [SQL Server], queries
- synchronization [SQL Server], query results with definition
- displaying query results in grid
- grid showing query results [SQL Server]
- showing query results in grid
- Query Designer [SQL Server], Results pane
- results [SQL Server], query
- viewing query results
- queries [SQL Server], results
- Results pane
ms.assetid: 6309a1bc-a628-4141-8bb5-b35924bd19f9
author: stevestein
ms.author: sstein
ms.openlocfilehash: f0db32336931f74777be56befcde9501dc484b69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568996"
---
# <a name="results-pane-visual-database-tools"></a><span data-ttu-id="583cd-102">Painel de Resultados (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="583cd-102">Results Pane (Visual Database Tools)</span></span>
  <span data-ttu-id="583cd-103">O painel Resultados mostra os resultados da consulta SELECT executada mais recentemente.</span><span class="sxs-lookup"><span data-stu-id="583cd-103">The Results pane shows the results of the most recently executed SELECT query.</span></span> <span data-ttu-id="583cd-104">(Os resultados de outros tipos de consultas são exibidos em caixas de mensagens.) Para abrir o painel Resultados, abra ou crie uma consulta ou exibição ou retorne os dados de uma tabela.</span><span class="sxs-lookup"><span data-stu-id="583cd-104">(The results of other query types are displayed in message boxes.) To open the results pane, open or create a query or view or return a table's data.</span></span> <span data-ttu-id="583cd-105">Se o painel Resultados não for exibido por padrão, no menu **Designer de Consulta** , aponte para **Painel**e clique em **Resultados**.</span><span class="sxs-lookup"><span data-stu-id="583cd-105">If the results pane doesn't show by default, from the **Query Designer** menu, point to **Pane**, and then click **Results**.</span></span>  
  
## <a name="what-you-can-do-in-the-results-pane"></a><span data-ttu-id="583cd-106">O que você pode fazer no painel Resultados</span><span class="sxs-lookup"><span data-stu-id="583cd-106">What You Can Do in the Results Pane</span></span>  
  
-   <span data-ttu-id="583cd-107">Exibir o conjunto de resultados para a consulta SELECT executada mais recentemente em uma grade tipo planilha.</span><span class="sxs-lookup"><span data-stu-id="583cd-107">View the result set for the most recently executed SELECT query in a spreadsheet-like grid.</span></span>  
  
-   <span data-ttu-id="583cd-108">Você pode editar os valores em colunas individuais no conjunto de resultados, adicionar linhas novas e excluir linhas existentes para consultas ou exibições que mostram dados de uma única tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="583cd-108">For queries or views that show data from a single table or view, you can edit the values in individual columns in the result set, add new rows, and delete existing rows.</span></span>  
  
## <a name="limitations-in-the-results-pane"></a><span data-ttu-id="583cd-109">Limitações do painel Resultados</span><span class="sxs-lookup"><span data-stu-id="583cd-109">Limitations in the Results Pane</span></span>  
  
-   <span data-ttu-id="583cd-110">Em alguns casos, somente os resultados retornados por funções com valor de tabela podem ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="583cd-110">Results returned by table-valued functions can only be updated in some cases.</span></span>  
  
-   <span data-ttu-id="583cd-111">As consultas ou as exibições que incluem colunas de mais de uma tabela ou exibição não podem ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="583cd-111">Queries or views that include columns from more than one table or view cannot be updated.</span></span>  
  
-   <span data-ttu-id="583cd-112">Os resultados retornados por um procedimento armazenado não podem ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="583cd-112">Results returned by a stored procedure cannot be updated.</span></span>  
  
-   <span data-ttu-id="583cd-113">As consultas ou as exibições que utilizam cláusulas GROUP BY ou DISTINCT não podem ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="583cd-113">Queries or views using the GROUP BY or DISTINCT clauses are not updatable.</span></span>  
  
## <a name="navigating-in-the-results-pane"></a><span data-ttu-id="583cd-114">Navegando no painel Resultados</span><span class="sxs-lookup"><span data-stu-id="583cd-114">Navigating in the Results Pane</span></span>  
 <span data-ttu-id="583cd-115">Você pode navegar rapidamente pelos registros, utilizando a barra de navegação da parte inferior do painel Resultados.</span><span class="sxs-lookup"><span data-stu-id="583cd-115">You can quickly navigate through the records using the navigation bar at the bottom of the Results pane.</span></span>  
  
 <span data-ttu-id="583cd-116">Há botões para seguir até o primeiro e o último registro, registros anteriores e posteriores, e para seguir até determinado registro.</span><span class="sxs-lookup"><span data-stu-id="583cd-116">There are buttons for going to the first and last records, the next and previous records, and for going to a particular record.</span></span>  
  
 <span data-ttu-id="583cd-117">Para ir até um registro específico, digite o número da linha na caixa de texto da barra de navegação e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="583cd-117">To go to a particular record, type the number of the row in the text box in the navigation bar and then press ENTER.</span></span>  
  
 <span data-ttu-id="583cd-118">Para obter informações sobre como usar atalhos de teclado no Designer de Consulta e Exibição, veja [Navegar no Designer de Consulta e Exibição &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="583cd-118">For information about using keyboard shortcuts in the Query and View Designer see [Navigate in the Query and View Designer &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="keeping-the-results-set-synchronized-with-the-query-definition"></a><span data-ttu-id="583cd-119">Mantendo o conjunto de resultados sincronizado com a definição de consulta</span><span class="sxs-lookup"><span data-stu-id="583cd-119">Keeping the Results Set Synchronized with the Query Definition</span></span>  
 <span data-ttu-id="583cd-120">Enquanto se está trabalhando nos resultados de uma consulta ou exibição, é possível que os registros do painel de resultados percam a sincronização com a definição da consulta.</span><span class="sxs-lookup"><span data-stu-id="583cd-120">While you are working on the results of a query or view it is possible for the records in the results pane to get out of synchronization with the query's definition.</span></span> <span data-ttu-id="583cd-121">Por exemplo, se você executar uma consulta para quatro entre cinco colunas de uma tabela e, depois, utilizar o painel Diagrama para adicionar a quinta coluna à definição da consulta, os dados da quinta coluna não serão adicionados automaticamente ao painel Resultados.</span><span class="sxs-lookup"><span data-stu-id="583cd-121">For example, if you run a query for four out of five columns in a table, and then use the Diagram pane to add the fifth column to the definition of the query, that fifth column's data will not automatically be added to the Results pane.</span></span> <span data-ttu-id="583cd-122">Para fazer com que o painel de resultados reflita a nova definição de consulta, execute novamente a consulta.</span><span class="sxs-lookup"><span data-stu-id="583cd-122">To make the results pane reflect the new query definition, run the query again.</span></span>  
  
 <span data-ttu-id="583cd-123">Se a consulta for alterada, será exibido um ícone de alerta e o texto “Consulta alterada” no canto inferior direito do painel Resultados.</span><span class="sxs-lookup"><span data-stu-id="583cd-123">If a query changes, an alert icon and the text "Query Changed" appears in the lower-right corner of the results pane.</span></span> <span data-ttu-id="583cd-124">O ícone será repetido no canto superior esquerdo do painel.</span><span class="sxs-lookup"><span data-stu-id="583cd-124">The icon is repeated in the upper-left corner of the pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="583cd-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="583cd-125">See Also</span></span>  
 <span data-ttu-id="583cd-126">[Criar consultas &#40;Visual Database Tools&#41;](create-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="583cd-126">[Create Queries &#40;Visual Database Tools&#41;](create-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="583cd-127">[Executar consultas &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="583cd-127">[Run Queries &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="583cd-128">[Tópicos de instruções sobre como criar consultas e exibições &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="583cd-128">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="583cd-129">[Painel Diagrama &#40;Visual Database Tools&#41;](diagram-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="583cd-129">[Diagram Pane &#40;Visual Database Tools&#41;](diagram-pane-visual-database-tools.md) </span></span>  
 <span data-ttu-id="583cd-130">[Painel de critérios &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="583cd-130">[Criteria Pane &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="583cd-131">Trabalhar com dados no painel de resultados &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="583cd-131">Work with Data in the Results Pane &#40;Visual Database Tools&#41;</span></span>](results-pane-visual-database-tools.md)  
  
  
