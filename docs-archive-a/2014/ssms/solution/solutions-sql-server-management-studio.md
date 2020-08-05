---
title: Soluções (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- solutions [SQL Server Management Studio]
- SQL Server Management Studio [SQL Server], solutions
- projects [SQL Server Management Studio], about projects
- SQL Server Management Studio [SQL Server], projects
- scripts [SQL Server], SQL Server Management Studio
ms.assetid: d06a8a05-7201-4055-8cf3-21bcb4e82c25
author: stevestein
ms.author: sstein
ms.openlocfilehash: 836d3b3002d72541ad88ae55eac6d951530e0ca2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572310"
---
# <a name="solutions-sql-server-management-studio"></a><span data-ttu-id="659b4-102">Soluções (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="659b4-102">Solutions (SQL Server Management Studio)</span></span>
  <span data-ttu-id="659b4-103">A solução [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] é uma coleção de um ou mais projetos relacionados.</span><span class="sxs-lookup"><span data-stu-id="659b4-103">A [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] solution is a collection of one or more related projects.</span></span> <span data-ttu-id="659b4-104">Projetos são contêineres que os desenvolvedores usam para organizar arquivos relacionados, como conjuntos de scripts de administração geralmente usados.</span><span class="sxs-lookup"><span data-stu-id="659b4-104">Projects are containers that developers use to organize related files, such as sets of commonly used administration scripts.</span></span>  
  
## <a name="solution-overview"></a><span data-ttu-id="659b4-105">Visão geral da solução</span><span class="sxs-lookup"><span data-stu-id="659b4-105">Solution Overview</span></span>  
 <span data-ttu-id="659b4-106">Você pode usar o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] como uma plataforma de desenvolvimento de scripts para o [!INCLUDE[ssDE](../../includes/ssde-md.md)] e o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="659b4-106">You can use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] as a script development platform for [!INCLUDE[ssDE](../../includes/ssde-md.md)] and [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="659b4-107">Use os editores de códigos do [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] para desenvolver scripts e consultas para bancos de dados relacionais e multidimensionais, e coletar scripts e consultas relacionados em projetos.</span><span class="sxs-lookup"><span data-stu-id="659b4-107">Use the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] code editors to develop scripts and queries for relational and multidimensional databases, and collect related scripts and queries together in projects.</span></span>  
  
 <span data-ttu-id="659b4-108">Os projetos podem conter:</span><span class="sxs-lookup"><span data-stu-id="659b4-108">Projects can contain:</span></span>  
  
-   <span data-ttu-id="659b4-109">Consultas e scripts que implementam processos de produção.</span><span class="sxs-lookup"><span data-stu-id="659b4-109">Queries and scripts that implement production processes.</span></span>  
  
-   <span data-ttu-id="659b4-110">Informações de conexão e arquivos usados pelas consultas e scripts.</span><span class="sxs-lookup"><span data-stu-id="659b4-110">Connection information and files used by the queries and scripts.</span></span>  
  
 <span data-ttu-id="659b4-111">Um ou mais projetos relacionados podem ser combinados em uma solução.</span><span class="sxs-lookup"><span data-stu-id="659b4-111">One or more related projects can be combined in a solution.</span></span> <span data-ttu-id="659b4-112">Soluções e projetos podem ser gerenciados usando o painel do Gerenciador de Soluções no [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="659b4-112">Solutions and projects can be managed by using the Solution Explorer pane in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="659b4-113">Soluções e projetos podem ser integrados em um banco de dados do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual SourceSafe (VSS) ou em outros provedores de controle do código-fonte de terceiros, para controle de alterações de desenvolvimento e gerenciamento do ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="659b4-113">Solutions and projects can be integrated into a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual SourceSafe (VSS) database or other third-party source control providers, for development change tracking and life-cycle management.</span></span>  
  
## <a name="solution-tasks"></a><span data-ttu-id="659b4-114">Tarefas de solução</span><span class="sxs-lookup"><span data-stu-id="659b4-114">Solution Tasks</span></span>  
  
|<span data-ttu-id="659b4-115">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="659b4-115">Task Description</span></span>|<span data-ttu-id="659b4-116">Tópico</span><span class="sxs-lookup"><span data-stu-id="659b4-116">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="659b4-117">Descreve como criar uma nova solução que pode ser usada para conter um ou mais projetos.</span><span class="sxs-lookup"><span data-stu-id="659b4-117">Describes how to create a new solution that can then be used to contain one or more projects.</span></span>|[<span data-ttu-id="659b4-118">Criar uma nova solução</span><span class="sxs-lookup"><span data-stu-id="659b4-118">Create a New Solution</span></span>](create-a-new-solution.md)|  
|<span data-ttu-id="659b4-119">Descreve como abrir uma solução existente no Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="659b4-119">Describes how to open an existing solution in Solution Explorer.</span></span>|[<span data-ttu-id="659b4-120">Abrir uma solução existente</span><span class="sxs-lookup"><span data-stu-id="659b4-120">Open an Existing Solution</span></span>](open-an-existing-solution.md)|  
|<span data-ttu-id="659b4-121">Descreve como fechar uma solução.</span><span class="sxs-lookup"><span data-stu-id="659b4-121">Describes how to close a solution.</span></span>|[<span data-ttu-id="659b4-122">Fechar uma solução</span><span class="sxs-lookup"><span data-stu-id="659b4-122">Close a Solution</span></span>](close-a-solution.md)|  
|<span data-ttu-id="659b4-123">Descreve como excluir uma solução.</span><span class="sxs-lookup"><span data-stu-id="659b4-123">Describes how to delete a solution.</span></span>|[<span data-ttu-id="659b4-124">Excluir uma solução</span><span class="sxs-lookup"><span data-stu-id="659b4-124">Delete a Solution</span></span>](delete-a-solution.md)|  
|<span data-ttu-id="659b4-125">Descreve como copiar itens entre projetos.</span><span class="sxs-lookup"><span data-stu-id="659b4-125">Describes how to copy items between projects.</span></span>|[<span data-ttu-id="659b4-126">Copiar itens em uma solução</span><span class="sxs-lookup"><span data-stu-id="659b4-126">Copy Items in a Solution</span></span>](copy-items-in-a-solution.md)|  
|<span data-ttu-id="659b4-127">Descreve como excluir itens em um projeto ou um projeto inteiro.</span><span class="sxs-lookup"><span data-stu-id="659b4-127">Describes how to delete items in a project, or an entire project.</span></span>|[<span data-ttu-id="659b4-128">Remover ou excluir um item ou projeto</span><span class="sxs-lookup"><span data-stu-id="659b4-128">Remove or Delete an Item or Project</span></span>](remove-or-delete-an-item-or-project.md)|  
|<span data-ttu-id="659b4-129">Descreve como mover itens entre projetos em uma solução.</span><span class="sxs-lookup"><span data-stu-id="659b4-129">Describes how to move items between projects in a solution.</span></span>|[<span data-ttu-id="659b4-130">Mover itens em uma solução</span><span class="sxs-lookup"><span data-stu-id="659b4-130">Move Items in a Solution</span></span>](move-items-in-a-solution.md)|  
|<span data-ttu-id="659b4-131">Descreve como renomear uma solução ou os itens na solução.</span><span class="sxs-lookup"><span data-stu-id="659b4-131">Describes how to rename a solution or the items in the solution.</span></span>|[<span data-ttu-id="659b4-132">Renomear soluções e itens de projeto</span><span class="sxs-lookup"><span data-stu-id="659b4-132">Rename Solutions and Project Items</span></span>](rename-solutions-and-project-items.md)|  
  
## <a name="see-also"></a><span data-ttu-id="659b4-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="659b4-133">See Also</span></span>  
 <span data-ttu-id="659b4-134">[Gerenciador de Soluções](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="659b4-134">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="659b4-135">[Projetos &#40;SQL Server Management Studio&#41;](projects-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="659b4-135">[Projects &#40;SQL Server Management Studio&#41;](projects-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="659b4-136">Controle do código-fonte do Gerenciador de Soluções</span><span class="sxs-lookup"><span data-stu-id="659b4-136">Solution Explorer Source Control</span></span>](../../database-engine/solution-explorer-source-control.md)  
  
  
