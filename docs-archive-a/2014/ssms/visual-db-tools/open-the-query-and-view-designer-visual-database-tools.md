---
title: Abrir no Designer de Consulta e Exibição (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- opening View Designer
- View Designer, opening
- Query Designer [SQL Server], opening
- opening Query Designer
ms.assetid: b473f258-d53c-41c0-9ad9-528a2ff141f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3a36a0a9f014759269517a5774167f84c19b0b18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574424"
---
# <a name="open-the-query-and-view-designer-visual-database-tools"></a><span data-ttu-id="68883-102">Abrir o Designer de Consulta e Exibição (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="68883-102">Open the Query and View Designer (Visual Database Tools)</span></span>
  <span data-ttu-id="68883-103">O Designer de Consulta e Exibição é aberto quando a definição de uma exibição é aberta; mostra os resultados de uma consulta ou exibição, ou cria ou abre uma consulta.</span><span class="sxs-lookup"><span data-stu-id="68883-103">The Query and View Designer opens when you open the definition of a view, show the results for a query or view, or create or open a query.</span></span> <span data-ttu-id="68883-104">Consiste em quatro painéis separados:</span><span class="sxs-lookup"><span data-stu-id="68883-104">It consists of four separate panes:</span></span>  
  
-   <span data-ttu-id="68883-105">O painel Diagrama apresenta uma exibição gráfica das tabelas ou objetos com valor de tabela selecionados na conexão de dados.</span><span class="sxs-lookup"><span data-stu-id="68883-105">The Diagram pane presents a graphic display of the tables or table-valued objects you have selected from the data connection.</span></span> <span data-ttu-id="68883-106">Mostra também todas as relações de junção entre eles.</span><span class="sxs-lookup"><span data-stu-id="68883-106">It also shows any join relationships among them.</span></span>  
  
-   <span data-ttu-id="68883-107">O painel Critérios permite que sejam especificadas as opções de consulta – como colunas de dados a serem exibidas, como ordenar os resultados e quais linhas selecionar – inserindo as seleções em uma grade tipo planilha.</span><span class="sxs-lookup"><span data-stu-id="68883-107">The Criteria pane allows you to specify query options - such as which data columns to display, how to order the results, and what rows to select - by entering your choices into a spreadsheet-like grid.</span></span>  
  
-   <span data-ttu-id="68883-108">Você pode usar o painel SQL para criar sua própria instrução SQL, ou pode usar os painéis de Critérios e Diagrama para criar a instrução, caso em que as instruções SQL serão criadas no painel SQL.</span><span class="sxs-lookup"><span data-stu-id="68883-108">You can use the SQL pane to create your own SQL statement, or you can use the Criteria pane and Diagram pane to create the statement, in which case the SQL statements will be created in the SQL pane.</span></span> <span data-ttu-id="68883-109">À medida que você cria a consulta, o painel SQL é atualizado e reformatado automaticamente para ser lido com facilidade.</span><span class="sxs-lookup"><span data-stu-id="68883-109">As you build your query, the SQL pane automatically updates and reformats to be easily read.</span></span>  
  
-   <span data-ttu-id="68883-110">O painel Resultados mostra os resultados da consulta Selecionar executada mais recentemente.</span><span class="sxs-lookup"><span data-stu-id="68883-110">The Results pane shows the results of the most recently executed Select query.</span></span> <span data-ttu-id="68883-111">(Os resultados de outros tipos de consultas são exibidos em caixas de mensagens.)</span><span class="sxs-lookup"><span data-stu-id="68883-111">(The results of other query types are displayed in message boxes.)</span></span>  
  
-   <span data-ttu-id="68883-112">Esses painéis são úteis por trabalharem tanto com consultas quanto com exibições.</span><span class="sxs-lookup"><span data-stu-id="68883-112">These panes are useful for working with both queries and views.</span></span>  
  
-   <span data-ttu-id="68883-113">Quando uma exibição ou consulta é aberta, alguns dos painéis são também abertos.</span><span class="sxs-lookup"><span data-stu-id="68883-113">When you open a view or query some or all of the panes open with it.</span></span> <span data-ttu-id="68883-114">Quais são esses painéis dependerá das configurações da caixa de diálogo **Opções** e do sistema de gerenciamento de banco de dados ao qual você está conectado.</span><span class="sxs-lookup"><span data-stu-id="68883-114">Which ones open depend on the settings in the **Options** dialog box and what database management system you're connected to.</span></span> <span data-ttu-id="68883-115">O padrão é que todos os quatro sejam abertos.</span><span class="sxs-lookup"><span data-stu-id="68883-115">The default is that all four open.</span></span>  
  
### <a name="to-open-the-query-and-view-designer-for-a-view"></a><span data-ttu-id="68883-116">Para brir o Designer de Consulta e Exibição para uma exibição</span><span class="sxs-lookup"><span data-stu-id="68883-116">To open the Query and View Designer for a view</span></span>  
  
1.  <span data-ttu-id="68883-117">No Pesquisador de Objetos, clique com o botão direito do mouse na exibição que você deseja abrir e depois clique em **Design** ou **Abrir Exibição**.</span><span class="sxs-lookup"><span data-stu-id="68883-117">In Object Explorer, right-click the view you want to open and click **Design** or **Open View**.</span></span>  
  
     <span data-ttu-id="68883-118">Se você escolher **Design**, o Designer de Consulta e Exibição será aberto na forma determinada pelas opções selecionadas na caixa de diálogo **Opções** .</span><span class="sxs-lookup"><span data-stu-id="68883-118">If you chose **Design**, the Query and View Designer panes open as dictated by the options selected in the **Options** dialog box.</span></span> <span data-ttu-id="68883-119">Se você escolher **Abrir Exibição**, apenas o painel de Resultados será aberto por padrão.</span><span class="sxs-lookup"><span data-stu-id="68883-119">If you chose **Open View**, only the Results pane opens by default.</span></span>  
  
### <a name="to-open-the-query-and-view-designer-for-an-existing-query"></a><span data-ttu-id="68883-120">Para abrir o Designer de Consulta e Exibição para uma consulta existente</span><span class="sxs-lookup"><span data-stu-id="68883-120">To open the Query and View Designer for an existing query</span></span>  
  
1.  <span data-ttu-id="68883-121">No Gerenciador de Soluções, expanda a pasta **Consultas** .</span><span class="sxs-lookup"><span data-stu-id="68883-121">In Solution Explorer, expand the **Queries** folder.</span></span>  
  
2.  <span data-ttu-id="68883-122">Clique duas vezes na consulta a ser aberta.</span><span class="sxs-lookup"><span data-stu-id="68883-122">Double-click the query you want to open.</span></span>  
  
3.  <span data-ttu-id="68883-123">Realce as instruções de consulta, clique com o botão direito do mouse na área realçada e depois clique em **Projetar Consulta no Editor**.</span><span class="sxs-lookup"><span data-stu-id="68883-123">Highlight the query statement(s), right-click the highlighted area and click **Design Query in Editor**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68883-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="68883-124">See Also</span></span>  
 <span data-ttu-id="68883-125">[Tópicos de instruções sobre como criar consultas e exibições &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="68883-125">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="68883-126">Ferramentas do Designer de Consulta e Exibição &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="68883-126">Query and View Designer Tools &#40;Visual Database Tools&#41;</span></span>](query-and-view-designer-tools-visual-database-tools.md)  
  
  
