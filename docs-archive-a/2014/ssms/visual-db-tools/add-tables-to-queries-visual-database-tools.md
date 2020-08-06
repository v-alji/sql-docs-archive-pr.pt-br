---
title: Adicionar tabelas a consultas (Ferramentas de Banco de Dados Visual) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- inserting tables
- adding tables
- queries [SQL Server], tables
ms.assetid: 6551aa7e-31a1-4636-852a-819bc53d658b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 572002bc913cc9916a75ce2b16c12064452d250f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574437"
---
# <a name="add-tables-to-queries-visual-database-tools"></a><span data-ttu-id="b4cf9-102">Adicionar tabelas a consultas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="b4cf9-102">Add Tables to Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="b4cf9-103">Quando você cria uma consulta, está recuperando dados de uma tabela ou outros objetos estruturados como tabelas – exibições e determinadas funções definidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="b4cf9-103">When you create a query, you are retrieving data from a table or other objects structured like tables - views and certain user-defined functions.</span></span> <span data-ttu-id="b4cf9-104">Para trabalhar com qualquer um desses objetos em sua consulta, adicione-os ao **Painel Diagrama**.</span><span class="sxs-lookup"><span data-stu-id="b4cf9-104">To work with any of these objects in your query, you add them to the **Diagram Pane**.</span></span>  
  
### <a name="to-add-a-table-or-table-valued-object-to-a-query"></a><span data-ttu-id="b4cf9-105">Para adicionar uma tabela ou objeto com valor de tabela a uma consulta</span><span class="sxs-lookup"><span data-stu-id="b4cf9-105">To add a table or table-valued object to a query</span></span>  
  
1.  <span data-ttu-id="b4cf9-106">No **painel Diagrama** do Designer de Consulta e Exibição, clique com o botão direito do mouse na tela de fundo e escolha **Adicionar Tabela** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="b4cf9-106">In the **Diagram pane** of the Query and View Designer, right-click the background and choose **Add Table** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="b4cf9-107">Na caixa de diálogo **Adicionar Tabela** , selecione a guia do tipo de objeto que deseja adicionar à consulta.</span><span class="sxs-lookup"><span data-stu-id="b4cf9-107">In the **Add Table** dialog box, select the tab for the type of object you want to add to the query.</span></span>  
  
3.  <span data-ttu-id="b4cf9-108">Na lista de itens, clique duas vezes em cada item que deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="b4cf9-108">In the list of items, double-click each item you want to add.</span></span>  
  
4.  <span data-ttu-id="b4cf9-109">Quando terminar de adicionar os itens, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b4cf9-109">When you finish adding items, click **Close**.</span></span>  
  
     <span data-ttu-id="b4cf9-110">O Designer de Consulta e Exibição atualiza adequadamente o **Painel Diagrama**, o **Painel Critérios**e o **Painel SQL** .</span><span class="sxs-lookup"><span data-stu-id="b4cf9-110">The Query and View Designer updates the **Diagram Pane**, **Criteria Pane**, and **SQL Pane** accordingly.</span></span>  
  
 <span data-ttu-id="b4cf9-111">As tabelas e as exibições são adicionadas automaticamente à consulta quando você as referencia na instrução do painel SQL.</span><span class="sxs-lookup"><span data-stu-id="b4cf9-111">Tables and views are automatically added to the query when you reference them in the statement in the SQL pane.</span></span>  
  
 <span data-ttu-id="b4cf9-112">O Designer de Consulta e Exibição não exibirá as colunas de dados de uma tabela ou objeto com estrutura de tabela se você não tiver direitos de acesso suficientes ou se o provedor não puder retornar informações sobre as mesmas.</span><span class="sxs-lookup"><span data-stu-id="b4cf9-112">The Query and View Designer will not display data columns for a table or table-structured object if you do not have sufficient access rights to it or if the provider cannot return information about it.</span></span> <span data-ttu-id="b4cf9-113">Nesses casos, serão exibidas apenas a barra de título e a caixa de seleção \* (Todas as Colunas) para a tabela ou objeto com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="b4cf9-113">In such cases, only a title bar and the \* (All Columns) check box are displayed for the table or table-valued object.</span></span>  
  
### <a name="to-add-an-existing-query-to-a-new-query"></a><span data-ttu-id="b4cf9-114">Para adicionar uma consulta existente a uma nova consulta</span><span class="sxs-lookup"><span data-stu-id="b4cf9-114">To add an existing query to a new query</span></span>  
  
1.  <span data-ttu-id="b4cf9-115">Verifique se o **Painel SQL** é exibido na nova consulta que está sendo criada.</span><span class="sxs-lookup"><span data-stu-id="b4cf9-115">Make sure the **SQL Pane** is displayed in the new query you are creating.</span></span>  
  
2.  <span data-ttu-id="b4cf9-116">No **Painel SQL**, digite um parêntese direito e esquerdo () depois da palavra FROM.</span><span class="sxs-lookup"><span data-stu-id="b4cf9-116">In the **SQL Pane**, type a right and left parentheses () after the word FROM.</span></span>  
  
3.  <span data-ttu-id="b4cf9-117">Abra o Designer de Consulta para a consulta existente.</span><span class="sxs-lookup"><span data-stu-id="b4cf9-117">Open the Query Designer for the existing query.</span></span> <span data-ttu-id="b4cf9-118">(Agora você tem dois Designers de Consulta abertos.)</span><span class="sxs-lookup"><span data-stu-id="b4cf9-118">(You now have two Query Designers open.)</span></span>  
  
4.  <span data-ttu-id="b4cf9-119">Exiba o **Painel SQL** para a consulta interna – a consulta existente que você está incluindo na nova consulta externa.</span><span class="sxs-lookup"><span data-stu-id="b4cf9-119">Display the **SQL Pane** for the inner query - the existing query you are including in the new, outer query.</span></span>  
  
5.  <span data-ttu-id="b4cf9-120">Selecione todo o texto no **Painel SQL**e copie para a Área de Transferência.</span><span class="sxs-lookup"><span data-stu-id="b4cf9-120">Select all the text in the **SQL Pane**, and copy it to the Clipboard.</span></span>  
  
6.  <span data-ttu-id="b4cf9-121">Clique no **Painel SQL** da consulta nova, posicione o cursor entre os parênteses que você adicionou e cole o conteúdo da Área de Transferência.</span><span class="sxs-lookup"><span data-stu-id="b4cf9-121">Click in the **SQL Pane** of the new query, situate the cursor between the parentheses you added, and paste the contents of the Clipboard.</span></span>  
  
7.  <span data-ttu-id="b4cf9-122">Ainda no **Painel SQL**, adicione um alias depois do parêntese direito.</span><span class="sxs-lookup"><span data-stu-id="b4cf9-122">Still in the **SQL Pane**, add an alias after the right parenthesis.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4cf9-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b4cf9-123">See Also</span></span>  
 <span data-ttu-id="b4cf9-124">[Criar aliases de tabela &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b4cf9-124">[Create Table Aliases &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="b4cf9-125">[Remover tabelas de consultas &#40;Visual Database Tools&#41;](remove-tables-from-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b4cf9-125">[Remove Tables from Queries &#40;Visual Database Tools&#41;](remove-tables-from-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="b4cf9-126">[Especificar critérios de pesquisa &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b4cf9-126">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 <span data-ttu-id="b4cf9-127">[Resumir os resultados da consulta &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b4cf9-127">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="b4cf9-128">Executar operações básicas com consultas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="b4cf9-128">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
