---
title: Criar consultas Insert Values (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- inserting values
- queries [SQL Server], types
- adding values
- row additions [SQL Server], Insert Values query
- inserting rows
- Insert Values query
- adding rows
- table values [SQL Server]
ms.assetid: 2d4b2f6d-cc09-434b-8a0e-ccce40628064
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2fc71b0148ee8a7e92c517fe75b56c329b3c88f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680257"
---
# <a name="create-insert-values-queries-visual-database-tools"></a><span data-ttu-id="9fa35-102">Criar consultas Insert Values (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9fa35-102">Create Insert Values Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="9fa35-103">Você pode criar uma nova linha na tabela atual usando uma consulta Insert Values.</span><span class="sxs-lookup"><span data-stu-id="9fa35-103">You can create a new row in the current table using an Insert Values query.</span></span> <span data-ttu-id="9fa35-104">Ao criar uma consulta Insert Values, você especifica:</span><span class="sxs-lookup"><span data-stu-id="9fa35-104">When you create an Insert Values query, you specify:</span></span>  
  
-   <span data-ttu-id="9fa35-105">A tabela de banco de dados à qual a linha será adicionada.</span><span class="sxs-lookup"><span data-stu-id="9fa35-105">The database table to add the row to.</span></span>  
  
-   <span data-ttu-id="9fa35-106">As colunas cujo conteúdo você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="9fa35-106">The columns whose contents you want to add.</span></span>  
  
-   <span data-ttu-id="9fa35-107">O valor ou a expressão a ser inserida nas colunas individuais.</span><span class="sxs-lookup"><span data-stu-id="9fa35-107">The value or expression to insert into the individual columns.</span></span>  
  
 <span data-ttu-id="9fa35-108">Por exemplo, a seguinte consulta adiciona uma linha à tabela `titles` especificando valores para o título, tipo, editora e preço:</span><span class="sxs-lookup"><span data-stu-id="9fa35-108">For example, the following query adds a row to the `titles` table, specifying values for the title, type, publisher, and price:</span></span>  
  
```  
INSERT INTO titles  
         (title_id, title, type, pub_id, price)  
VALUES   ('BU9876', 'Creating Web Pages', 'business', '1389', '29.99')  
```  
  
 <span data-ttu-id="9fa35-109">Quando você cria uma consulta Insert Values, o painel Critérios muda para refletir somente as opções disponíveis para inserir uma nova linha: o nome da coluna e o valor a ser inserido.</span><span class="sxs-lookup"><span data-stu-id="9fa35-109">When you create an Insert Values query, the Criteria pane changes to reflect the only options available for inserting a new row: the column name and the value to insert.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="9fa35-110">Você não pode desfazer a ação de execução de uma consulta Insert Values.</span><span class="sxs-lookup"><span data-stu-id="9fa35-110">You cannot undo the action of executing an Insert Values query.</span></span> <span data-ttu-id="9fa35-111">Como precaução, faça backup de seus dados antes de executar a consulta.</span><span class="sxs-lookup"><span data-stu-id="9fa35-111">As a precaution, back up your data before executing the query.</span></span>  
  
### <a name="to-create-an-insert-values-query"></a><span data-ttu-id="9fa35-112">Para criar uma consulta Insert Values</span><span class="sxs-lookup"><span data-stu-id="9fa35-112">To create an Insert Values query</span></span>  
  
1.  <span data-ttu-id="9fa35-113">Adicione a tabela que deseja atualizar ao painel Diagrama.</span><span class="sxs-lookup"><span data-stu-id="9fa35-113">Add the table you want to update to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="9fa35-114">No menu **Designer de Consultas** , aponte para **Alterar Tipo**e clique em **Insert Values**.</span><span class="sxs-lookup"><span data-stu-id="9fa35-114">From the **Query Designer** menu point to **Change Type**, and then click **Insert Values**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9fa35-115">Se mais de uma tabela for exibida no painel Diagrama quando você iniciar a consulta Insert Values, o Designer de Consulta e Exibição exibirá a caixa de diálogo [Escolher Tabela de Destino para Inserir Valores](visual-database-tools.md) que solicitará o nome da tabela a ser atualizada.</span><span class="sxs-lookup"><span data-stu-id="9fa35-115">If more than one table is displayed in the Diagram pane when you start the Insert Values query, the Query and View Designer displays the [Choose Target Table for Insert Values Dialog Box](visual-database-tools.md) to prompt you for the name of the table to update.</span></span>  
  
3.  <span data-ttu-id="9fa35-116">No painel Diagrama, clique na caixa de seleção de cada coluna para a qual você deseja fornecer novos valores.</span><span class="sxs-lookup"><span data-stu-id="9fa35-116">In the Diagram pane, click the check box for each column for which you want to supply new values.</span></span> <span data-ttu-id="9fa35-117">Essas colunas serão exibidas no painel Critérios.</span><span class="sxs-lookup"><span data-stu-id="9fa35-117">Those columns will show in the Criteria pane.</span></span> <span data-ttu-id="9fa35-118">As colunas só serão atualizadas se você as adicionar à consulta.</span><span class="sxs-lookup"><span data-stu-id="9fa35-118">Columns will be updated only if you add them to the query.</span></span>  
  
4.  <span data-ttu-id="9fa35-119">Na coluna **Novo Valor** do painel Critérios, insira o novo valor para a coluna.</span><span class="sxs-lookup"><span data-stu-id="9fa35-119">In the **New Value** column of the Criteria pane, enter the new value for the column.</span></span> <span data-ttu-id="9fa35-120">Você pode inserir valores literais, nomes de coluna ou expressões.</span><span class="sxs-lookup"><span data-stu-id="9fa35-120">You can enter literal values, column names, or expressions.</span></span> <span data-ttu-id="9fa35-121">O valor deve corresponder (ou ser compatível com) ao tipo de dados da coluna que você está atualizando.</span><span class="sxs-lookup"><span data-stu-id="9fa35-121">The value must match (or be compatible with) the data type of the column you are updating.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="9fa35-122">O Designer de Consulta e Exibição não pode verificar se um valor é adequado ao comprimento da coluna que você está inserindo.</span><span class="sxs-lookup"><span data-stu-id="9fa35-122">The Query and View Designer cannot check that a value fits within the length of the column you are inserting.</span></span> <span data-ttu-id="9fa35-123">Se você fornecer um valor muito longo, ele poderá ser truncado sem aviso.</span><span class="sxs-lookup"><span data-stu-id="9fa35-123">If you provide a value that is too long, it might be truncated without warning.</span></span> <span data-ttu-id="9fa35-124">Por exemplo, se uma coluna `name` tiver 20 caracteres, mas você especificar um valor de inserção de 25 caracteres, os últimos 5 caracteres poderão ser truncados.</span><span class="sxs-lookup"><span data-stu-id="9fa35-124">For example, if a `name` column is 20 characters long but you specify an insert value of 25 characters, the last 5 characters might be truncated.</span></span>  
  
 <span data-ttu-id="9fa35-125">Se você executar uma consulta Insert Values, nenhum resultado será relatado no painel de [Resultados](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9fa35-125">When you execute an Insert Values query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="9fa35-126">Em vez disso, será exibida uma mensagem indicando quantas linhas foram alteradas.</span><span class="sxs-lookup"><span data-stu-id="9fa35-126">Instead, a message appears indicating how many rows were changed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fa35-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9fa35-127">See Also</span></span>  
 <span data-ttu-id="9fa35-128">[Tipos de consulta com suporte &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="9fa35-128">[Supported Query Types &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span></span>  
 <span data-ttu-id="9fa35-129">[Tópicos de instruções sobre como criar consultas e exibições &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="9fa35-129">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="9fa35-130">Executar operações básicas com consultas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="9fa35-130">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
