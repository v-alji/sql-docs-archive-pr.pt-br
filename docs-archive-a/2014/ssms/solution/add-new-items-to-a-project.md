---
title: Adicionar novos itens a um projeto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], item additions
- adding project items
ms.assetid: 76af8692-324f-4f5e-b1a0-d72ca8a107e3
author: stevestein
ms.author: sstein
ms.openlocfilehash: c73c58952c7801b3a0e2c86652feb461292cf37c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583275"
---
# <a name="add-new-items-to-a-project"></a><span data-ttu-id="5b213-102">Adicionar novos itens a um projeto</span><span class="sxs-lookup"><span data-stu-id="5b213-102">Add New Items to a Project</span></span>
  <span data-ttu-id="5b213-103">Adicione novos itens a um projeto para estender a funcionalidade do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="5b213-103">Add new items to a project to extend application functionality.</span></span> <span data-ttu-id="5b213-104">Um novo item pode ser uma consulta ou uma conexão.</span><span class="sxs-lookup"><span data-stu-id="5b213-104">A new item can be a query or a connection.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="5b213-105">tem dois tipos de projeto: Projeto de Script do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e Projeto de Script do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="5b213-105">has two project types: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Script Project, and Analysis Services Script Project.</span></span> <span data-ttu-id="5b213-106">O tipo de projeto determina os itens que você pode adicionar ao projeto.</span><span class="sxs-lookup"><span data-stu-id="5b213-106">The project type determines the items that you can add to the project.</span></span> <span data-ttu-id="5b213-107">Por exemplo, você pode adicionar uma consulta [!INCLUDE[tsql](../../includes/tsql-md.md)] (um arquivo com uma extensão .sql) a um projeto de script do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , mas não pode adicioná-lo a um Projeto de Script do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="5b213-107">For example, you can add a [!INCLUDE[tsql](../../includes/tsql-md.md)] query (a file with a .sql extension) to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Script project, but you cannot add it to an Analysis Services Script Project.</span></span>  
  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="5b213-108">não permite a criação de pastas dentro de projetos.</span><span class="sxs-lookup"><span data-stu-id="5b213-108">does not allow you to create folders within projects.</span></span> <span data-ttu-id="5b213-109">Para organizar seu trabalho, crie vários projetos dentro da solução.</span><span class="sxs-lookup"><span data-stu-id="5b213-109">To organize your work, create multiple projects within the solution.</span></span>  
  
### <a name="to-add-a-new-query-to-an-existing-project"></a><span data-ttu-id="5b213-110">Para adicionar uma nova consulta a um projeto existente</span><span class="sxs-lookup"><span data-stu-id="5b213-110">To add a new query to an existing project</span></span>  
  
1.  <span data-ttu-id="5b213-111">No Gerenciador de Soluções, selecione um projeto de destino.</span><span class="sxs-lookup"><span data-stu-id="5b213-111">In Solution Explorer, select a target project.</span></span>  
  
2.  <span data-ttu-id="5b213-112">No menu **Projeto** , clique em **Adicionar Novo Item**.</span><span class="sxs-lookup"><span data-stu-id="5b213-112">On the **Project** menu, click **Add New Item**.</span></span>  
  
3.  <span data-ttu-id="5b213-113">Na caixa de diálogo **Adicionar Novo Item** , selecione uma categoria no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="5b213-113">In the **Add New Item** dialog box, select a category in the left pane.</span></span>  
  
4.  <span data-ttu-id="5b213-114">Selecione um modelo de consulta no painel direito e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="5b213-114">Select a query template in the right pane, and then click **Add**.</span></span> <span data-ttu-id="5b213-115">A nova consulta é adicionada à pasta **Consultas** do projeto.</span><span class="sxs-lookup"><span data-stu-id="5b213-115">The new query is added in the **Queries** folder of the project.</span></span>  
  
5.  <span data-ttu-id="5b213-116">Na caixa de diálogo **Conectar ao Mecanismo de Banco de Dados** , especifique uma conexão para a nova consulta e clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="5b213-116">In the **Connect to Database Engine** dialog box, specify a connection for the new query, and then click **Connect**.</span></span> <span data-ttu-id="5b213-117">Você poderá clicar em **Cancelar** na caixa de diálogo da conexão se não quiser associar uma conexão com a consulta nova.</span><span class="sxs-lookup"><span data-stu-id="5b213-117">You can click **Cancel** on the connection dialog if you do not want to associate a connection to the new query.</span></span>  
  
6.  <span data-ttu-id="5b213-118">Caso deseje, renomeie a consulta no Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="5b213-118">Rename the query in Solution Explorer if you wish.</span></span>  
  
### <a name="to-add-a-new-connection-to-an-existing-project"></a><span data-ttu-id="5b213-119">Para adicionar uma nova conexão a um projeto existente</span><span class="sxs-lookup"><span data-stu-id="5b213-119">To add a new connection to an existing project</span></span>  
  
1.  <span data-ttu-id="5b213-120">No Gerenciador de Soluções, selecione um projeto de destino.</span><span class="sxs-lookup"><span data-stu-id="5b213-120">In Solution Explorer, select a target project.</span></span>  
  
2.  <span data-ttu-id="5b213-121">No menu **Projeto** , clique em **Adicionar Novo Item**.</span><span class="sxs-lookup"><span data-stu-id="5b213-121">On the **Project** menu, click **Add New Item**.</span></span>  
  
3.  <span data-ttu-id="5b213-122">Selecione **Conexão** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="5b213-122">Select **Connection** in the left pane.</span></span>  
  
4.  <span data-ttu-id="5b213-123">Selecione **Nova Conexão** no painel direito e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="5b213-123">Select **New Connection** in the right pane, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="5b213-124">Na caixa de diálogo **Conectar ao Mecanismo de Banco de Dados** , especifique uma conexão para a nova consulta e clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="5b213-124">In the **Connect to Database Engine** dialog box, specify a connection for the new query, and then click **Connect**.</span></span> <span data-ttu-id="5b213-125">A nova conexão é adicionada à pasta **Conexões** do projeto.</span><span class="sxs-lookup"><span data-stu-id="5b213-125">The new connection gets added in the **Connections** folder of the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b213-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5b213-126">See Also</span></span>  
 <span data-ttu-id="5b213-127">[Gerenciador de Soluções](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="5b213-127">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="5b213-128">[Associar extensões de arquivo a um editor de códigos](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md) </span><span class="sxs-lookup"><span data-stu-id="5b213-128">[Associate File Extensions to a Code Editor](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md) </span></span>  
 <span data-ttu-id="5b213-129">[Adicionar itens existentes a um projeto](add-existing-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="5b213-129">[Add Existing Items to a Project](add-existing-items-to-a-project.md) </span></span>  
 [<span data-ttu-id="5b213-130">Remover ou excluir um item ou projeto</span><span class="sxs-lookup"><span data-stu-id="5b213-130">Remove or Delete an Item or Project</span></span>](remove-or-delete-an-item-or-project.md)  
  
  
