---
title: Reconciliar alterações feitas por vários usuários (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- table modifications [SQL Server], multiple users
- reconciling changes made by multiple users
- modifications made by multiple users
ms.assetid: fc7ed4f2-ad3d-47fc-a3ef-51e5bb069ef0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 337d505fce474a33301c18313fe6137f6bc0ec1b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679602"
---
# <a name="reconcile-changes-made-by-multiple-users-visual-database-tools"></a><span data-ttu-id="2fddc-102">Reconciliar alterações feitas por vários usuários (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="2fddc-102">Reconcile Changes Made by Multiple Users (Visual Database Tools)</span></span>
  <span data-ttu-id="2fddc-103">Em um ambiente multiusuário, é possível ter vários usuários fazendo alterações no mesmo objeto simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="2fddc-103">In a multiuser environment, changes can be made on the same object by multiple users at once.</span></span> <span data-ttu-id="2fddc-104">Isso pode acontecer quando você estiver trabalhando na estrutura do objeto nos designers de diagrama de banco de dados ou tabela, ou pode ocorrer em valores nos resultados retornados no painel de resultados dos Designers de Consulta e Exibição.</span><span class="sxs-lookup"><span data-stu-id="2fddc-104">This can happen when you're working on the structure of the object in the Table or Database Diagram designers or it can happen to values in the results returned in the Query and View designer's Results pane.</span></span> <span data-ttu-id="2fddc-105">Isso pode causar conflitos que devem ser resolvidos.</span><span class="sxs-lookup"><span data-stu-id="2fddc-105">This can cause conflicts that you'll want to resolve.</span></span>  
  
## <a name="conflicts-in-the-table-or-database-diagram-designers"></a><span data-ttu-id="2fddc-106">Conflitos nos designers de diagramas de banco de dados ou tabelas</span><span class="sxs-lookup"><span data-stu-id="2fddc-106">Conflicts in the Table or Database Diagram Designers</span></span>  
 <span data-ttu-id="2fddc-107">Por exemplo, outro usuário pode excluir ou renomear uma tabela enquanto você estiver trabalhando na mesma ou em uma tabela relacionada no Designer de Tabela.</span><span class="sxs-lookup"><span data-stu-id="2fddc-107">For example, another user might delete or rename a table while you are working with the same or a related table in Table Designer.</span></span> <span data-ttu-id="2fddc-108">Quando você tentar salvar a tabela, a [Caixa de diálogo Alterações no Banco de Dados Detectadas &#40;Visual Database Tools&#41;](visual-database-tools.md) o notifica de que o banco de dados foi atualizado desde que você abriu a tabela.</span><span class="sxs-lookup"><span data-stu-id="2fddc-108">When you attempt to save your table, the [Database Changes Detected Dialog Box &#40;Visual Database Tools&#41;](visual-database-tools.md) notifies you that the database has been updated since you opened the table.</span></span>  
  
 <span data-ttu-id="2fddc-109">Essa caixa de diálogo também exibe uma lista de objetos de banco de dados que serão afetados como resultado de salvar sua tabela.</span><span class="sxs-lookup"><span data-stu-id="2fddc-109">This dialog box also displays a list of database objects that will be affected as a result of saving your table.</span></span> <span data-ttu-id="2fddc-110">Nesse momento, você pode adotar uma destas ações:</span><span class="sxs-lookup"><span data-stu-id="2fddc-110">At this point, you can take one of these actions:</span></span>  
  
-   <span data-ttu-id="2fddc-111">Escolha **Sim** para salvar sua tabela e atualizar o banco de dados com todas as alterações na lista.</span><span class="sxs-lookup"><span data-stu-id="2fddc-111">Choose **Yes** to save your table and update the database with all the changes in the list.</span></span>  
  
     <span data-ttu-id="2fddc-112">Essa ação pode afetar tabelas que compartilham os mesmos objetos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2fddc-112">This action could affect tables that share the same database objects.</span></span> <span data-ttu-id="2fddc-113">Por exemplo, suponha que você edite a coluna `au`_`id` na tabela `titleauthors` enquanto outro usuário esteja trabalhando na tabela `authors` , que é relacionada à tabela `titleauthors` pela coluna `au`\_`id` .</span><span class="sxs-lookup"><span data-stu-id="2fddc-113">For example, suppose you edit the `au`_`id` column in the `titleauthors` table while another user is working on the `authors` table which is related to the `titleauthors` table by the `au`\_`id` column.</span></span> <span data-ttu-id="2fddc-114">Se você salvar sua tabela, afetará a tabela do outro usuário.</span><span class="sxs-lookup"><span data-stu-id="2fddc-114">Saving your table will affect the other user's table.</span></span> <span data-ttu-id="2fddc-115">De forma semelhante, suponha que outro usuário tenha definido uma restrição de verificação para a coluna `qty` da tabela `sales` .</span><span class="sxs-lookup"><span data-stu-id="2fddc-115">Similarly, suppose that another user defined a check constraint for the `qty` column in the `sales` table.</span></span> <span data-ttu-id="2fddc-116">Se você excluir a coluna `qty` e salvar a tabela `sales` , a restrição de verificação do outro usuário será afetada.</span><span class="sxs-lookup"><span data-stu-id="2fddc-116">If you delete the `qty` column and save the `sales` table, the other user's check constraint will be affected.</span></span>  
  
-   <span data-ttu-id="2fddc-117">Selecione **Não** para cancelar a ação.</span><span class="sxs-lookup"><span data-stu-id="2fddc-117">Choose **No** to cancel the save action.</span></span>  
  
     <span data-ttu-id="2fddc-118">Você pode então fechar a tabela sem salvá-la.</span><span class="sxs-lookup"><span data-stu-id="2fddc-118">You can then close the table without saving it.</span></span> <span data-ttu-id="2fddc-119">Quando você reabrir a tabela, ela corresponderá ao que está no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2fddc-119">When you reopen the table it will match what is in the database.</span></span>  
  
-   <span data-ttu-id="2fddc-120">Escolha **Salvar Arquivo de Texto** para salvar uma lista das alterações.</span><span class="sxs-lookup"><span data-stu-id="2fddc-120">Choose **Save Text File** to save a list of the changes.</span></span>  
  
     <span data-ttu-id="2fddc-121">Você pode salvar a lista de alterações do banco de dados mostrada na caixa de diálogo **Alterações no Banco de Dados Detectadas** em um arquivo de texto, de forma que possa investigar a causa das alterações de outros usuários.</span><span class="sxs-lookup"><span data-stu-id="2fddc-121">You can save the list of database changes shown in the **Database Changes Detected** dialog box to a text file so that you can investigate the cause of other users' changes.</span></span> <span data-ttu-id="2fddc-122">Por exemplo, se outro usuário tiver editado uma tabela marcada para exclusão, você poderá pesquisar se a tabela deve ser excluída antes de atualizar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2fddc-122">For example, if another user edited a table that you marked for deletion, you may want to research whether the table should be deleted before updating the database.</span></span>  
  
## <a name="conflicts-in-the-query-and-view-designer"></a><span data-ttu-id="2fddc-123">Conflitos nos Designers de Consulta e Exibição</span><span class="sxs-lookup"><span data-stu-id="2fddc-123">Conflicts in the Query and View Designer</span></span>  
 <span data-ttu-id="2fddc-124">Se você executar uma consulta ou retornar os resultados de uma exibição, os dados serão mostrados no [Painel de Resultados](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2fddc-124">If you run a query or return the results of a view, the data is shown in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="2fddc-125">Vários usuários podem trabalhar no mesmo conjunto de dados ao mesmo tempo, o que pode causar conflitos.</span><span class="sxs-lookup"><span data-stu-id="2fddc-125">Multiple users can work on the same set of data at the same time, which can cause conflicts.</span></span>  
  
 <span data-ttu-id="2fddc-126">Por exemplo, digamos que você e um colega executem uma consulta para mostrar todos os dados da tabela `titleauthors` .</span><span class="sxs-lookup"><span data-stu-id="2fddc-126">For example, lets say you and a colleague each run a query to show all the data in the `titleauthors` table.</span></span> <span data-ttu-id="2fddc-127">Seu colega altera o primeiro nome no primeiro registro retornado de Barb para Bárbara.</span><span class="sxs-lookup"><span data-stu-id="2fddc-127">Your colleague changes the first name in the first record returned from Barb to Barbara.</span></span> <span data-ttu-id="2fddc-128">Nesse momento, o banco de dados tem Bárbara naquele campo, enquanto seu conjunto de resultados ainda mostra Barb.</span><span class="sxs-lookup"><span data-stu-id="2fddc-128">At this point the database has Barbara in that field, while your result set still shows Barb.</span></span> <span data-ttu-id="2fddc-129">Agora você digita Bárbara e clica fora da linha.</span><span class="sxs-lookup"><span data-stu-id="2fddc-129">Now you type in Barbara and click off of the row.</span></span> <span data-ttu-id="2fddc-130">Você receberá uma mensagem perguntando como deseja resolver o conflito.</span><span class="sxs-lookup"><span data-stu-id="2fddc-130">You will receive a message asking you how you want to resolve the conflict.</span></span>  
  
-   <span data-ttu-id="2fddc-131">Clique em **Sim** para atualizar o banco de dados com suas alterações.</span><span class="sxs-lookup"><span data-stu-id="2fddc-131">Click **Yes** to update the database with your changes.</span></span>  
  
     <span data-ttu-id="2fddc-132">Isso substituirá as mudanças de seu colega.</span><span class="sxs-lookup"><span data-stu-id="2fddc-132">This will override your colleague's changes.</span></span>  
  
-   <span data-ttu-id="2fddc-133">Clique em **Não** para ter seu conjunto de resultados atualizado ao que está atualmente no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2fddc-133">Click **No** to have your result set updated to what's currently in the database.</span></span>  
  
     <span data-ttu-id="2fddc-134">Isso substituirá suas alterações pelas de seu colega.</span><span class="sxs-lookup"><span data-stu-id="2fddc-134">This will override your changes with those of your colleague's.</span></span>  
  
-   <span data-ttu-id="2fddc-135">Clique em **Cancelar** para continuar editando sem resolver o conflito.</span><span class="sxs-lookup"><span data-stu-id="2fddc-135">Click **Cancel** to continue to edit without resolving the conflict.</span></span>  
  
     <span data-ttu-id="2fddc-136">Nesse caso, você não poderá confirmar suas alterações no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2fddc-136">In this case you will not be able to commit your changes to the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fddc-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2fddc-137">See Also</span></span>  
 [<span data-ttu-id="2fddc-138">Caixa de diálogo Alterações no Banco de Dados Detectadas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="2fddc-138">Database Changes Detected Dialog Box &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
