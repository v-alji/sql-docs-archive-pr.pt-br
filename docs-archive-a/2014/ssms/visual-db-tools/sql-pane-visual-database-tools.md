---
title: Painel SQL (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Query Designer [SQL Server], SQL pane
- View Designer, SQL pane
- SQL pane [Visual Database Tools]
ms.assetid: dbabab18-0614-415b-a2ef-9bcd0d320d5c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3a87ec1d5517852fefb152e0ec7b3165fa32988b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678475"
---
# <a name="sql-pane-visual-database-tools"></a><span data-ttu-id="21456-102">Painel SQL (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="21456-102">SQL Pane (Visual Database Tools)</span></span>
  <span data-ttu-id="21456-103">Você pode usar o painel SQL para criar sua própria instrução SQL, ou pode usar os painéis de Critérios e Diagrama para criar a instrução, caso em que as instruções SQL serão criadas no painel SQL.</span><span class="sxs-lookup"><span data-stu-id="21456-103">You can use the SQL pane to create your own SQL statement, or you can use the Criteria pane and Diagram pane to create the statement, in which case the SQL statements will be created in the SQL pane.</span></span> <span data-ttu-id="21456-104">À medida que você cria a consulta, o painel SQL é atualizado e reformatado automaticamente para ser lido com facilidade.</span><span class="sxs-lookup"><span data-stu-id="21456-104">As you build your query, the SQL pane automatically updates and reformats for easy readability.</span></span>  
  
 <span data-ttu-id="21456-105">Para abrir o painel SQL, primeiro abra o Designer de Consulta e Exibição (com um objeto de banco de dados selecionado no Gerenciador de Servidores, no menu **Banco de Dados** , clique em **Nova Consulta**).</span><span class="sxs-lookup"><span data-stu-id="21456-105">To open the SQL pane, first open Query and View Designer (with a database object selected in Server Explorer, from the **Database** menu, click **New Query**).</span></span> <span data-ttu-id="21456-106">Em seguida, no menu **Designer de Consultas** , aponte para o **Painel** e clique em **SQL**.</span><span class="sxs-lookup"><span data-stu-id="21456-106">Then from the **Query Designer** menu point to **Pane** and click **SQL**.</span></span>  
  
 <span data-ttu-id="21456-107">No painel SQL você pode:</span><span class="sxs-lookup"><span data-stu-id="21456-107">In the SQL pane you can:</span></span>  
  
-   <span data-ttu-id="21456-108">Criar novas consultas entrando as instruções SQL.</span><span class="sxs-lookup"><span data-stu-id="21456-108">Create new queries by entering SQL statements.</span></span>  
  
-   <span data-ttu-id="21456-109">Modificar a instrução SQL criada pelo Designer de Consulta e Exibição baseado nas configurações que você faz nos painéis de Diagrama e Critérios.</span><span class="sxs-lookup"><span data-stu-id="21456-109">Modify the SQL statement created by the Query and View Designer based on settings you make in the Diagram and Criteria panes.</span></span>  
  
-   <span data-ttu-id="21456-110">Digitar as instruções que tiram proveito de recursos específicos para o banco de dados você está usando.</span><span class="sxs-lookup"><span data-stu-id="21456-110">Enter statements that take advantage of features specific to the database you are using.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="21456-111">Certifique-se de que você saiba as regras para identificar os objetos de banco de dados no banco de dados que você está usando.</span><span class="sxs-lookup"><span data-stu-id="21456-111">Be sure you know the rules for identifying database objects in the database you are using.</span></span> <span data-ttu-id="21456-112">Para obter detalhes, veja a documentação para seu sistema de administração de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="21456-112">For details, see the documentation for your database management system.</span></span>  
  
## <a name="statements-in-the-sql-pane"></a><span data-ttu-id="21456-113">Instruções no painel SQL</span><span class="sxs-lookup"><span data-stu-id="21456-113">Statements in the SQL Pane</span></span>  
 <span data-ttu-id="21456-114">Você pode editar a consulta atual diretamente no painel SQL.</span><span class="sxs-lookup"><span data-stu-id="21456-114">You can edit the current query directly in the SQL pane.</span></span> <span data-ttu-id="21456-115">Quando você vai para outro painel, o Designer de Consulta e Exibição automaticamente formata sua instrução, e então altera os painéis Diagrama e Critérios para corresponder a sua instrução.</span><span class="sxs-lookup"><span data-stu-id="21456-115">When you move to another pane, the Query and View Designer automatically formats your statement, and then changes the Diagram and Criteria panes to match your statement.</span></span>  
  
 <span data-ttu-id="21456-116">Se sua instrução não puder ser representada nos painéis Diagrama e Critérios, e se esses painéis estiverem visíveis, o Designer de Consulta e Exibição exibirá um erro e então lhe oferecerá duas opções:</span><span class="sxs-lookup"><span data-stu-id="21456-116">If your statement cannot be represented in the Diagram and Criteria panes, and if those panes are visible, Query and View Designer displays an error and then offers you two choices:</span></span>  
  
-   <span data-ttu-id="21456-117">Ignorar que a instrução não pode ser representada nos painéis Diagrama e Critérios.</span><span class="sxs-lookup"><span data-stu-id="21456-117">Ignore that the statement can not be represented in the Diagram and Criteria panes.</span></span>  
  
-   <span data-ttu-id="21456-118">Desfazer a mudança que não pode ser representada e reverter à versão mais recente versão da instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="21456-118">Undo the change that can not be represented and revert to the most recent version of the SQL statement.</span></span>  
  
 <span data-ttu-id="21456-119">Se você escolher ignorar que a instrução não pode ser representada nos painéis Diagrama e Critérios, o Designer de Consulta e Exibição escurecerá os outros painéis para indicar que eles já não refletem o conteúdo do painel SQL.</span><span class="sxs-lookup"><span data-stu-id="21456-119">If you choose to ignore that the statement can not be represented in the Diagram and Criteria panes, the Query and View Designer dims the other panes to indicate that they no longer reflect the contents of the SQL pane.</span></span>  
  
 <span data-ttu-id="21456-120">Você pode continuar editando a instrução e executá-la como você faria com qualquer instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="21456-120">You can continue to edit the statement and execute it as you would any SQL statement.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="21456-121">Se você inserir uma instrução SQL, mas depois fizer mais alterações na consulta alterando os painéis Diagrama e Critérios, o Designer de Consulta e Exibição recria e exibe novamente a instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="21456-121">If you enter an SQL statement, but then make further changes to the query by changing the Diagram and Criteria panes, the Query and View Designer rebuilds and redisplays the SQL statement.</span></span> <span data-ttu-id="21456-122">Em alguns casos, esta ação resulta em uma instrução SQL que é construída de forma diferente daquela que você inseriu originalmente (embora vá sempre render os mesmos resultados).</span><span class="sxs-lookup"><span data-stu-id="21456-122">In some cases, this action results in an SQL statement that is constructed differently from the one you originally entered (though it will always yield the same results).</span></span> <span data-ttu-id="21456-123">Esta diferença é particularmente possível quando você estiver trabalhando com critérios de pesquisa que envolvam várias cláusulas associadas a AND e OR.</span><span class="sxs-lookup"><span data-stu-id="21456-123">This difference is particularly likely when you are working with search conditions that involve several clauses linked with AND and OR.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21456-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="21456-124">See Also</span></span>  
 <span data-ttu-id="21456-125">[Criar consultas &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="21456-125">[Create Queries &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="21456-126">[Executar consultas &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="21456-126">[Run Queries &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="21456-127">[Tópicos de instruções sobre como criar consultas e exibições &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="21456-127">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="21456-128">[Painel Diagrama &#40;Visual Database Tools&#41;](diagram-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="21456-128">[Diagram Pane &#40;Visual Database Tools&#41;](diagram-pane-visual-database-tools.md) </span></span>  
 <span data-ttu-id="21456-129">[Painel de critérios &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="21456-129">[Criteria Pane &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="21456-130">Painel de Resultados &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="21456-130">Results Pane &#40;Visual Database Tools&#41;</span></span>](results-pane-visual-database-tools.md)  
  
  
