---
title: Criar consultas de exclusão (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- row removal [SQL Server], Delete query
- Delete query
- queries [SQL Server], types
- removing rows
- removing data
- data deletions [SQL Server]
- deleting rows
- deleting data
ms.assetid: 0db3af43-1ec4-48c8-b769-2bb9c76d3434
author: stevestein
ms.author: sstein
ms.openlocfilehash: a76c3aaef623365e419f40f3058308f6217d75d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583274"
---
# <a name="create-delete-queries-visual-database-tools"></a><span data-ttu-id="b39fa-102">Criar consultas de exclusão (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="b39fa-102">Create Delete Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="b39fa-103">Você pode excluir todas as linhas em uma tabela usando uma consulta Exclusão.</span><span class="sxs-lookup"><span data-stu-id="b39fa-103">You can delete all rows in a table by using a Delete query.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b39fa-104">A exclusão de todas as linhas da tabela limpa os dados na tabela, mas não exclui a tabela em si.</span><span class="sxs-lookup"><span data-stu-id="b39fa-104">Deleting all rows from a table clears the data in the table but does not delete the table itself.</span></span> <span data-ttu-id="b39fa-105">Para excluir uma tabela de um banco de dados, clique com o botão direito do mouse na tabela no Pesquisador de Objetos e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="b39fa-105">To delete a table from a database, right-click the table in Object Explorer and click **Delete**.</span></span>  
  
 <span data-ttu-id="b39fa-106">Quando você cria uma consulta Exclusão, o painel Critérios é alterado para refletir as opções disponíveis para exclusão de linhas.</span><span class="sxs-lookup"><span data-stu-id="b39fa-106">When you create a Delete query, the Criteria pane changes to reflect the options available for deleting rows.</span></span> <span data-ttu-id="b39fa-107">Como não são exibidos dados na consulta Exclusão, as colunas Saída, Classificar por e Ordem de Classificação são removidas.</span><span class="sxs-lookup"><span data-stu-id="b39fa-107">Because you do not display data in a Delete query, the Output, Sort By, and Sort Order columns are removed.</span></span> <span data-ttu-id="b39fa-108">Além disso, as caixas de seleção próximas aos nomes de coluna no retângulo que representa a tabela ou o objeto com valor de tabela são removidas, pois você não pode especificar colunas individuais para exclusão.</span><span class="sxs-lookup"><span data-stu-id="b39fa-108">In addition, the check boxes next to the column names in the rectangle representing the table or table-valued object are removed because you cannot specify individual columns to delete.</span></span>  
  
 <span data-ttu-id="b39fa-109">Se o Designer de Consulta e Exibição não puder excluir uma ou mais linhas, nenhuma delas será excluída e você receberá uma mensagem informando quais linhas contêm informações que não podem ser excluídas do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b39fa-109">If the Query and View Designer can't delete one or more of the rows none of them will be deleted and you will receive a message telling you which row(s) contain information that can't be deleted from the database.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="b39fa-110">Você não pode desfazer a ação de execução da consulta Exclusão.</span><span class="sxs-lookup"><span data-stu-id="b39fa-110">You cannot undo the action of executing a Delete query.</span></span> <span data-ttu-id="b39fa-111">Como precaução, faça backup de seus dados antes de executar uma consulta Exclusão.</span><span class="sxs-lookup"><span data-stu-id="b39fa-111">As a precaution, back up your data before executing a Delete query.</span></span>  
  
### <a name="to-create-a-delete-query"></a><span data-ttu-id="b39fa-112">Para criar uma consulta Exclusão</span><span class="sxs-lookup"><span data-stu-id="b39fa-112">To create a Delete query</span></span>  
  
1.  <span data-ttu-id="b39fa-113">Adicione a tabela para excluir linhas no painel Diagrama.</span><span class="sxs-lookup"><span data-stu-id="b39fa-113">Add the table to delete rows from to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="b39fa-114">No menu **Designer de Consultas** , aponte para **Alterar Tipo**e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="b39fa-114">From the **Query Designer** menu, point to **Change Type**, and then click **Delete**.</span></span> <span data-ttu-id="b39fa-115">**Observação** Se mais de uma tabela for exibida no painel Diagrama quando você iniciar a consulta de Exclusão, o Designer de Consulta e Exibição exibirá a caixa de diálogo [Excluir Tabela](visual-database-tools.md) , que solicitará o nome da tabela cujas linhas serão excluídas.</span><span class="sxs-lookup"><span data-stu-id="b39fa-115">**Note** If more than one table is displayed in the Diagram pane when you start the Delete query, the Query and View Designer displays the [Delete Table Dialog Box](visual-database-tools.md) to prompt you for the name of the table to delete rows from.</span></span>  
  
 <span data-ttu-id="b39fa-116">Quando você executa a consulta de Exclusão, nenhum resultado é relatado no [Painel de Resultados](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b39fa-116">When you execute the Delete query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="b39fa-117">Em vez disso, é exibida uma mensagem indicando quantas linhas foram excluídas.</span><span class="sxs-lookup"><span data-stu-id="b39fa-117">Instead, a message appears indicating how many rows were deleted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b39fa-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b39fa-118">See Also</span></span>  
 <span data-ttu-id="b39fa-119">[Tipos de consulta com suporte &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b39fa-119">[Supported Query Types &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="b39fa-120">Tópicos de instruções de como criar consultas e exibições &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="b39fa-120">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
