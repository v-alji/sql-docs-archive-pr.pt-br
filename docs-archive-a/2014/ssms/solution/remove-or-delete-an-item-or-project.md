---
title: Remover ou excluir um item ou projeto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- deleting project items
- projects [SQL Server Management Studio], item removal
- removing project items
ms.assetid: 3fd92434-70f5-466e-bef0-7e0fd73ddb1c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 679911f15d6c47f4274180602a5376c4ec03c77b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572317"
---
# <a name="remove-or-delete-an-item-or-project"></a><span data-ttu-id="7aab4-102">Remover ou excluir um item ou projeto</span><span class="sxs-lookup"><span data-stu-id="7aab4-102">Remove or Delete an Item or Project</span></span>
  <span data-ttu-id="7aab4-103">Os itens de projeto do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] são consultas, conexões e arquivos diversos.</span><span class="sxs-lookup"><span data-stu-id="7aab4-103">Project items in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] projects are Queries, Connections, and Miscellaneous files.</span></span> <span data-ttu-id="7aab4-104">Você pode remover consultas de projeto e arquivos diversos de sua solução sem apagar os arquivos do armazenamento.</span><span class="sxs-lookup"><span data-stu-id="7aab4-104">You can remove project queries and miscellaneous files from your solution without erasing the files from storage.</span></span> <span data-ttu-id="7aab4-105">Remova um projeto ou item quando não for útil na solução atual, mas que você deseja incluí-lo em outra solução.</span><span class="sxs-lookup"><span data-stu-id="7aab4-105">Remove a project or item when it is not useful in the current solution but you want to include it in another solution.</span></span>  
  
### <a name="to-remove-a-project-item"></a><span data-ttu-id="7aab4-106">Para remover um item de projeto</span><span class="sxs-lookup"><span data-stu-id="7aab4-106">To remove a project item</span></span>  
  
1.  <span data-ttu-id="7aab4-107">No Gerenciador de Soluções, selecione o item de projeto que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="7aab4-107">In Solution Explorer, select the project item you want to remove.</span></span>  
  
2.  <span data-ttu-id="7aab4-108">No menu **Editar** , clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="7aab4-108">On the **Edit** menu, click **Remove**.</span></span>  
  
3.  <span data-ttu-id="7aab4-109">Na caixa de diálogo de confirmação, clique em **Remover** para remover o item do projeto.</span><span class="sxs-lookup"><span data-stu-id="7aab4-109">On the confirmation dialog, click **Remove** to remove the item from the project.</span></span>  
  
 <span data-ttu-id="7aab4-110">Um item removido continua existindo no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="7aab4-110">A removed item still exists on the file system.</span></span> <span data-ttu-id="7aab4-111">Desta forma, você pode adicionar um item removido à solução original ou a outra solução.</span><span class="sxs-lookup"><span data-stu-id="7aab4-111">Therefore, you can add a removed item to its original solution or to another solution.</span></span>  
  
#### <a name="to-remove-a-project"></a><span data-ttu-id="7aab4-112">Para remover um projeto</span><span class="sxs-lookup"><span data-stu-id="7aab4-112">To remove a project</span></span>  
  
1.  <span data-ttu-id="7aab4-113">No Gerenciador de Soluções, selecione o projeto que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="7aab4-113">In Solution Explorer, select the project you want to remove.</span></span>  
  
2.  <span data-ttu-id="7aab4-114">No menu **Editar** , clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="7aab4-114">On the **Edit** menu, click **Remove**.</span></span>  
  
3.  <span data-ttu-id="7aab4-115">Na caixa de diálogo de confirmação, clique em **OK**para remover o projeto da solução.</span><span class="sxs-lookup"><span data-stu-id="7aab4-115">On the confirmation dialog, click **OK**, to remove the project from the solution.</span></span>  
  
 <span data-ttu-id="7aab4-116">Você pode excluir um projeto permanentemente, mas primeiro é necessário remover qualquer referência ao projeto das soluções do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e depois usar o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Explorer para excluir os arquivos associados permanentemente do armazenamento.</span><span class="sxs-lookup"><span data-stu-id="7aab4-116">You can delete a project permanently, but you first need to remove any references to the project from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] solutions, and then use [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Explorer to permanently delete the associated files from storage.</span></span>  
  
#### <a name="to-delete-a-project"></a><span data-ttu-id="7aab4-117">Para excluir um projeto</span><span class="sxs-lookup"><span data-stu-id="7aab4-117">To delete a project</span></span>  
  
1.  <span data-ttu-id="7aab4-118">No Gerenciador de Soluções, remova o projeto que você deseja excluir da solução.</span><span class="sxs-lookup"><span data-stu-id="7aab4-118">In Solution Explorer, remove the project you want to delete from the solution.</span></span>  
  
2.  <span data-ttu-id="7aab4-119">No Windows Explorer, localize e selecione os arquivos associados ao projeto ou ao item que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="7aab4-119">In Windows Explorer, locate and select the files associated with the project or item you want to delete.</span></span>  
  
3.  <span data-ttu-id="7aab4-120">No menu **Arquivo** , clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="7aab4-120">On the **File** menu, click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aab4-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7aab4-121">See Also</span></span>  
 <span data-ttu-id="7aab4-122">[Gerenciador de Soluções](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="7aab4-122">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="7aab4-123">[Adicionar novos itens a um projeto](add-new-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="7aab4-123">[Add New Items to a Project](add-new-items-to-a-project.md) </span></span>  
 [<span data-ttu-id="7aab4-124">Adicionar itens existentes a um projeto</span><span class="sxs-lookup"><span data-stu-id="7aab4-124">Add Existing Items to a Project</span></span>](add-existing-items-to-a-project.md)  
  
  
