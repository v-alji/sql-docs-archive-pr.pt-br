---
title: Criar consultas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], creating
ms.assetid: 696a080d-848f-44d3-a918-e29bafaab85a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 52392adff03b27e1c4c19f354bc62c350cccf17a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569003"
---
# <a name="create-queries-visual-database-tools"></a><span data-ttu-id="46b83-102">Criar consultas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="46b83-102">Create Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="46b83-103">As consultas permitem que você recupere dados das tabelas e exibições em seu banco de dados.</span><span class="sxs-lookup"><span data-stu-id="46b83-103">Queries allow you to retrieve data from the tables and views in your database.</span></span> <span data-ttu-id="46b83-104">Você cria e trabalha com consultas no **Designer de Consulta e Exibição**, que é composto por quatro painéis: o [Painel de Diagrama](visual-database-tools.md), o [Painel SQL](sql-pane-visual-database-tools.md), o [Painel de Critérios](criteria-pane-visual-database-tools.md)e o [Painel de Resultados](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="46b83-104">You create and work with queries in **Query and View Designer**, which is composed of four panes: the [Diagram Pane](visual-database-tools.md), the [SQL Pane](sql-pane-visual-database-tools.md), the [Criteria Pane](criteria-pane-visual-database-tools.md), and the [Results Pane](results-pane-visual-database-tools.md).</span></span>  
  
### <a name="to-create-a-new-query"></a><span data-ttu-id="46b83-105">Para criar uma consulta</span><span class="sxs-lookup"><span data-stu-id="46b83-105">To create a new query</span></span>  
  
1.  <span data-ttu-id="46b83-106">No **Pesquisador de Objetos**, expanda o nó **Tabelas** do banco de dados que você deseja consultar.</span><span class="sxs-lookup"><span data-stu-id="46b83-106">In **Object Explorer**, expand the **Tables** node for the database you want to query.</span></span> <span data-ttu-id="46b83-107">Clique com o botão direito do mouse na tabela que deseja consultar e clique em **Abrir Tabela**.</span><span class="sxs-lookup"><span data-stu-id="46b83-107">Right-click the table you want to query and click **Open Table**.</span></span>  
  
2.  <span data-ttu-id="46b83-108">Para adicionar mais tabelas à consulta, no menu Designer de Consultas, selecione **Adicionar Tabela**.</span><span class="sxs-lookup"><span data-stu-id="46b83-108">To add more tables to the query, on the Query Designer menu, select **Add Table**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="46b83-109">Se você não conseguir ver os painéis **Diagrama**, **SQL**, **Critérios**ou **Resultados** , no menu Designer de Consultas, aponte para **Painel** e clique no painel que deseja abrir.</span><span class="sxs-lookup"><span data-stu-id="46b83-109">If you do not see the **Diagram**, **SQL**, **Criteria**, or **Results** panes, from the Query Designer menu, point to **Pane** and click the pane you want to open.</span></span>  
  
3.  <span data-ttu-id="46b83-110">Na caixa de diálogo **Adicionar Tabela** , selecione as tabelas que você deseja consultar e clique em **Adicionar** para cada uma.</span><span class="sxs-lookup"><span data-stu-id="46b83-110">In the **Add Table** dialog box, select the tables you want to query and click **Add** for each one.</span></span>  
  
4.  <span data-ttu-id="46b83-111">Após adicionar todas as tabelas que deseja consultar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="46b83-111">Once you have added all the tables you want to query, click **Close**.</span></span>  
  
     <span data-ttu-id="46b83-112">Para adicionar mais tabelas posteriormente, clique com o botão direito do mouse no espaço aberto do painel **Diagrama** e, no menu de atalho, clique em **Adicionar Tabela**.</span><span class="sxs-lookup"><span data-stu-id="46b83-112">To add more tables later, right-click the open space in the **Diagram** pane and from the shortcut menu click **Add Table**.</span></span>  
  
5.  <span data-ttu-id="46b83-113">No **Painel de Diagrama**, marque as caixas nos objetos com valor de tabela para cada coluna que você deseja consultar.</span><span class="sxs-lookup"><span data-stu-id="46b83-113">In the **Diagram Pane**, check the boxes in the table-valued objects for each column you want to query.</span></span>  
  
6.  <span data-ttu-id="46b83-114">No menu Designer de Consultas, escolha **Executar SQL** para executar sua consulta.</span><span class="sxs-lookup"><span data-stu-id="46b83-114">From the Query Designer menu, choose **Execute SQL** to run your query.</span></span>  
  
 <span data-ttu-id="46b83-115">Para refinar ainda mais a sua consulta, você pode alterar o código SQL no **Painel SQL** ou escolher opções como ordem de classificação e aliases de coluna no **Painel de Critérios.**</span><span class="sxs-lookup"><span data-stu-id="46b83-115">To further refine your query, you can change the SQL code in the **SQL Pane** or choose options such as sort order and column aliases in the **Criteria Pane.**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46b83-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="46b83-116">See Also</span></span>  
 <span data-ttu-id="46b83-117">[Salvar consultas &#40;Visual Database Tools&#41;](save-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="46b83-117">[Save Queries &#40;Visual Database Tools&#41;](save-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="46b83-118">[Tipos de consultas &#40;Visual Database Tools&#41;](types-of-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="46b83-118">[Types of Queries &#40;Visual Database Tools&#41;](types-of-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="46b83-119">[Especificar critérios de pesquisa &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="46b83-119">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 <span data-ttu-id="46b83-120">[Resumir os resultados da consulta &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="46b83-120">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="46b83-121">Executar operações básicas com consultas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="46b83-121">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
