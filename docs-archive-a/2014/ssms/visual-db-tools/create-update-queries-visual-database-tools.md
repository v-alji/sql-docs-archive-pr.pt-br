---
title: Criar consultas de atualização (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- tables [SQL Server], updating
- queries [SQL Server], types
- Update query
- updating tables
ms.assetid: 178b7b75-8078-4e61-b2a8-4719b9d8033d
author: stevestein
ms.author: sstein
ms.openlocfilehash: bbea575d544875dba73de923474cc11bbcb46a9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574993"
---
# <a name="create-update-queries-visual-database-tools"></a><span data-ttu-id="23e81-102">Criar consultas de atualização (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="23e81-102">Create Update Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="23e81-103">Você pode alterar o conteúdo de várias linhas em uma operação usando uma consulta Update.</span><span class="sxs-lookup"><span data-stu-id="23e81-103">You can change the contents of multiple rows in one operation by using an Update query.</span></span> <span data-ttu-id="23e81-104">Por exemplo, em uma tabela `titles` , você pode usar uma consulta Update para adicionar 10% ao preço de todos os livros de um publicador específico.</span><span class="sxs-lookup"><span data-stu-id="23e81-104">For example, in a `titles` table you can use an Update query to add 10% to the price of all books for a particular publisher.</span></span>  
  
 <span data-ttu-id="23e81-105">Ao criar uma consulta Update, você especifica:</span><span class="sxs-lookup"><span data-stu-id="23e81-105">When you create an Update query, you specify:</span></span>  
  
-   <span data-ttu-id="23e81-106">A tabela a ser atualizada.</span><span class="sxs-lookup"><span data-stu-id="23e81-106">The table to update.</span></span>  
  
-   <span data-ttu-id="23e81-107">As colunas cujo conteúdo você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="23e81-107">The columns whose contents you want to update.</span></span>  
  
-   <span data-ttu-id="23e81-108">O valor ou a expressão a ser atualizada nas colunas individuais.</span><span class="sxs-lookup"><span data-stu-id="23e81-108">The value or expression to use to update the individual columns.</span></span>  
  
-   <span data-ttu-id="23e81-109">Os critérios de pesquisa para definir as linhas que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="23e81-109">Search conditions to define the rows you want to update.</span></span>  
  
 <span data-ttu-id="23e81-110">Por exemplo, a consulta seguinte atualiza a tabela `titles` adicionando 10% ao preço de todos os títulos de um publicador:</span><span class="sxs-lookup"><span data-stu-id="23e81-110">For example, the following query updates the `titles` table by adding 10% to the price of all titles for one publisher:</span></span>  
  
```  
UPDATE titles  
SET price = price * 1.1  
WHERE (pub_id = '0766')  
```  
  
> [!CAUTION]  
>  <span data-ttu-id="23e81-111">Você não pode desfazer a ação de execução da consulta Update.</span><span class="sxs-lookup"><span data-stu-id="23e81-111">You cannot undo the action of executing an Update query.</span></span> <span data-ttu-id="23e81-112">Como precaução, faça backup de seus dados antes de executar a consulta.</span><span class="sxs-lookup"><span data-stu-id="23e81-112">As a precaution, back up your data before executing the query.</span></span>  
  
### <a name="to-create-an-update-query"></a><span data-ttu-id="23e81-113">Para criar uma consulta Update</span><span class="sxs-lookup"><span data-stu-id="23e81-113">To create an Update query</span></span>  
  
1.  <span data-ttu-id="23e81-114">Adicione a tabela que deseja atualizar ao painel Diagrama.</span><span class="sxs-lookup"><span data-stu-id="23e81-114">Add the table you want to update to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="23e81-115">No menu **Designer de Consultas** , aponte para **Alterar Tipo**e clique em **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="23e81-115">From the **Query Designer** menu point to **Change Type**, and then click **Update**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="23e81-116">Se mais de uma tabela for exibida no painel Diagrama quando você iniciar a consulta de Atualização, o Designer de Consulta e Exibição exibirá [Escolher Tabela de Destino da Caixa de Diálogo Inserir Valores](visual-database-tools.md) , que solicitará o nome da tabela a ser atualizada.</span><span class="sxs-lookup"><span data-stu-id="23e81-116">If more than one table is displayed in the Diagram pane when you start the Update query, the Query and View Designer displays the [Choose Target Table for Insert Values Dialog Box](visual-database-tools.md) to prompt you for the name of the table to update.</span></span>  
  
3.  <span data-ttu-id="23e81-117">No painel Diagrama, clique na caixa de seleção de cada coluna para a qual você deseja fornecer novos valores.</span><span class="sxs-lookup"><span data-stu-id="23e81-117">In the Diagram pane, click the check box for each column for which you want to supply new values.</span></span> <span data-ttu-id="23e81-118">Essas colunas serão exibidas no painel Critérios.</span><span class="sxs-lookup"><span data-stu-id="23e81-118">Those columns will show in the Criteria pane.</span></span> <span data-ttu-id="23e81-119">As colunas só serão atualizadas se você as adicionar à consulta.</span><span class="sxs-lookup"><span data-stu-id="23e81-119">Columns will be updated only if you add them to the query.</span></span>  
  
4.  <span data-ttu-id="23e81-120">Na coluna **Novo Valor** do painel Critérios, insira o valor de atualização para a coluna.</span><span class="sxs-lookup"><span data-stu-id="23e81-120">In the **New Value** column of the Criteria pane, enter the update value for the column.</span></span> <span data-ttu-id="23e81-121">Você pode inserir valores literais, nomes de coluna ou expressões.</span><span class="sxs-lookup"><span data-stu-id="23e81-121">You can enter literal values, column names, or expressions.</span></span> <span data-ttu-id="23e81-122">O valor deve corresponder (ou ser compatível com) ao tipo de dados da coluna que você está atualizando.</span><span class="sxs-lookup"><span data-stu-id="23e81-122">The value must match (or be compatible with) the data type of the column you are updating.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="23e81-123">O Designer de Consulta e Exibição não pode verificar se um valor é adequado ao comprimento da coluna que você está atualizando.</span><span class="sxs-lookup"><span data-stu-id="23e81-123">The Query and View Designer cannot check that a value fits within the length of the column you are updating.</span></span> <span data-ttu-id="23e81-124">Se você fornecer um valor muito longo, ele poderá ser truncado sem aviso.</span><span class="sxs-lookup"><span data-stu-id="23e81-124">If you provide a value that is too long, it might be truncated without warning.</span></span> <span data-ttu-id="23e81-125">Por exemplo, se uma coluna `name` tiver 20 caracteres, mas você especificar um valor de atualização de 25 caracteres, os últimos 5 caracteres poderão ser truncados.</span><span class="sxs-lookup"><span data-stu-id="23e81-125">For example, if a `name` column is 20 characters long but you specify an update value of 25 characters, the last 5 characters might be truncated.</span></span>  
  
5.  <span data-ttu-id="23e81-126">Defina as linhas a serem atualizadas inserindo critérios de pesquisa na coluna **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="23e81-126">Define the rows to update by entering search conditions in the **Filter** column.</span></span> <span data-ttu-id="23e81-127">Para obter detalhes, consulte [Especificar critérios de pesquisa &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="23e81-127">For details, see [Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="23e81-128">Se você não especificar um critério de pesquisa, todas as linhas na tabela especificada serão atualizadas.</span><span class="sxs-lookup"><span data-stu-id="23e81-128">If you do not specify a search condition, all rows in the specified table will be updated.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="23e81-129">Quando você adiciona uma coluna ao painel Critérios para uso em um critério de pesquisa, o Designer de Consulta e Exibição também a adiciona à lista de colunas a serem atualizadas.</span><span class="sxs-lookup"><span data-stu-id="23e81-129">When you add a column to the Criteria pane for use in a search condition, the Query and View Designer also adds it to the list of columns to be updated.</span></span> <span data-ttu-id="23e81-130">Se você quiser utilizar uma coluna para um critério de pesquisa, mas não quiser atualizá-la, desmarque a caixa de seleção próxima ao nome da coluna no retângulo que representa a tabela ou o objeto com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="23e81-130">If you want to use a column for a search condition but not update it, clear the check box next to the column name in the rectangle representing the table or table-valued object.</span></span>  
  
 <span data-ttu-id="23e81-131">Quando você executa uma consulta de Atualização, nenhum resultado será relatado no painel de [Resultados](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="23e81-131">When you execute an Update query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="23e81-132">Em vez disso, será exibida uma mensagem indicando quantas linhas foram alteradas.</span><span class="sxs-lookup"><span data-stu-id="23e81-132">Instead, a message appears indicating how many rows were changed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23e81-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="23e81-133">See Also</span></span>  
 <span data-ttu-id="23e81-134">[Tipos de consulta com suporte &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="23e81-134">[Supported Query Types &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span></span>  
 <span data-ttu-id="23e81-135">[Tópicos de instruções sobre como criar consultas e exibições &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="23e81-135">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="23e81-136">Executar operações básicas com consultas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="23e81-136">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
