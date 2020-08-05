---
title: Gerenciador de Soluções | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], solutions
- projects [SQL Server Management Studio], about projects
- SQL Server Management Studio [SQL Server], projects
- solutions [SQL Server Management Studio], about solutions
- SQL Server Management Studio [SQL Server], items
- items [SQL Server]
ms.assetid: 0df09843-0d4f-4925-bc6c-99265035a0c1
author: stevestein
ms.author: sstein
ms.openlocfilehash: fa312f5e097fa1c59b9ba545709dc964a184c3f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572312"
---
# <a name="solution-explorer"></a><span data-ttu-id="1d7cf-102">Gerenciador de Soluções</span><span class="sxs-lookup"><span data-stu-id="1d7cf-102">Solution Explorer</span></span>
  <span data-ttu-id="1d7cf-103">O painel Gerenciador de Soluções no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] fornece contêineres chamados projetos para gerenciar itens, como scripts de banco de dados, consultas, conexões de dados e arquivos.</span><span class="sxs-lookup"><span data-stu-id="1d7cf-103">The Solution Explorer pane in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] provides containers called projects for managing items such as database scripts, queries, data connections, and files.</span></span> <span data-ttu-id="1d7cf-104">Um ou mais projetos relacionados um ao outro podem ser combinados em um contêiner chamado solução.</span><span class="sxs-lookup"><span data-stu-id="1d7cf-104">One or more projects that are related to each other can be combined in a container called a solution.</span></span>  
  
 <span data-ttu-id="1d7cf-105">Uma solução inclui um ou mais projetos, mais arquivos e metadados que ajudam a definir a solução como um todo.</span><span class="sxs-lookup"><span data-stu-id="1d7cf-105">A solution includes one or more projects, plus files and metadata that help define the solution as a whole.</span></span> <span data-ttu-id="1d7cf-106">Um projeto é um conjunto de arquivos mais metadados relacionados, como informações de conexão.</span><span class="sxs-lookup"><span data-stu-id="1d7cf-106">A project is a set of files, plus related metadata such as connection information.</span></span> <span data-ttu-id="1d7cf-107">Soluções e projetos contêm itens que representam scripts, consultas, informações de conexão e arquivos necessários para criar sua solução de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1d7cf-107">Solutions and projects contain items that represent the scripts, queries, connection information and files that you need to create your database solution.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
## <a name="benefits-of-using-solutions"></a><span data-ttu-id="1d7cf-108">Benefícios do uso de soluções</span><span class="sxs-lookup"><span data-stu-id="1d7cf-108">Benefits of Using Solutions</span></span>  
 <span data-ttu-id="1d7cf-109">Use esses contêineres para:</span><span class="sxs-lookup"><span data-stu-id="1d7cf-109">Use these containers to:</span></span>  
  
-   <span data-ttu-id="1d7cf-110">Implementar controle do código-fonte em consultas e scripts.</span><span class="sxs-lookup"><span data-stu-id="1d7cf-110">Implement source control on queries and scripts.</span></span>  
  
-   <span data-ttu-id="1d7cf-111">Gerenciar configurações da solução como um todo ou de projetos individuais.</span><span class="sxs-lookup"><span data-stu-id="1d7cf-111">Manage settings for your solution as a whole or for individual projects.</span></span>  
  
-   <span data-ttu-id="1d7cf-112">Tratar os detalhes do gerenciamento de arquivos enquanto você enfoca itens que compõem sua solução de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1d7cf-112">Handle the details of file management while you focus on items that make up your database solution.</span></span>  
  
-   <span data-ttu-id="1d7cf-113">Adicionar itens úteis a vários projetos na solução ou à solução sem consultar o item em cada projeto.</span><span class="sxs-lookup"><span data-stu-id="1d7cf-113">Add items that are useful to multiple projects in the solution or to the solution without referencing the item in each project.</span></span>  
  
-   <span data-ttu-id="1d7cf-114">Trabalhar em diversos arquivos independentes de soluções ou projetos.</span><span class="sxs-lookup"><span data-stu-id="1d7cf-114">Work on miscellaneous files that are independent from solutions or projects.</span></span>  
  
 <span data-ttu-id="1d7cf-115">Os itens contidos em projetos dependem do tipo de projeto e se você está usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d7cf-115">The items contained in projects depend on the project type and whether you are using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="1d7cf-116">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="1d7cf-116">Related Tasks</span></span>  
 <span data-ttu-id="1d7cf-117">Use os tópicos a seguir para começar a usar as Soluções do SQL Server:</span><span class="sxs-lookup"><span data-stu-id="1d7cf-117">Use the following topics to get started with SQL Server Solutions:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1d7cf-118">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="1d7cf-118">**Description**</span></span>|<span data-ttu-id="1d7cf-119">**Tópico**</span><span class="sxs-lookup"><span data-stu-id="1d7cf-119">**Topic**</span></span>|  
|<span data-ttu-id="1d7cf-120">Descreve como coletar um ou mais projetos em uma solução.</span><span class="sxs-lookup"><span data-stu-id="1d7cf-120">Describes how to collect one or more projects in a solution.</span></span>|[<span data-ttu-id="1d7cf-121">Soluções &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1d7cf-121">Solutions &#40;SQL Server Management Studio&#41;</span></span>](solutions-sql-server-management-studio.md)|  
|<span data-ttu-id="1d7cf-122">Descreve como criar um projeto e adicionar itens como scripts e conexões.</span><span class="sxs-lookup"><span data-stu-id="1d7cf-122">Describes how to create a project and add items like scripts and connections.</span></span>|[<span data-ttu-id="1d7cf-123">Projetos &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1d7cf-123">Projects &#40;SQL Server Management Studio&#41;</span></span>](projects-sql-server-management-studio.md)|  
|<span data-ttu-id="1d7cf-124">Descreve como integrar soluções ou projetos de indivíduo em um sistema de controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="1d7cf-124">Describes how to integrate solutions or individual projects into a source code control system.</span></span>|[<span data-ttu-id="1d7cf-125">Controle do código-fonte do Gerenciador de Soluções</span><span class="sxs-lookup"><span data-stu-id="1d7cf-125">Solution Explorer Source Control</span></span>](../../database-engine/solution-explorer-source-control.md)|  
|<span data-ttu-id="1d7cf-126">Fornece informações sobre os arquivos usados pelo [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para gerenciar soluções e arquivos.</span><span class="sxs-lookup"><span data-stu-id="1d7cf-126">Provides information about the files used by [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to manage solutions and files.</span></span>|[<span data-ttu-id="1d7cf-127">Arquivos que gerenciam soluções e projetos</span><span class="sxs-lookup"><span data-stu-id="1d7cf-127">Files That Manage Solutions and Projects</span></span>](files-that-manage-solutions-and-projects.md)|  
  
  
