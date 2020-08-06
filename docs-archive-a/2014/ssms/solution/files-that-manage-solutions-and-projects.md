---
title: Arquivos que gerenciam soluções e projetos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], files
- .ssmssln files
- .ssmsmobileproj files
- .ssmsasproj files
- .ssmssqlproj files
- .sqlsuo files
- files [SQL Server Management Studio], projects
ms.assetid: e19d2859-0b97-4727-ac27-c4c226d86b2f
author: stevestein
ms.author: sstein
ms.openlocfilehash: c94f1f853263c3969961de91ec95b921f5d78ead
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680740"
---
# <a name="files-that-manage-solutions-and-projects"></a><span data-ttu-id="1ad20-102">Arquivos que gerenciam soluções e projetos</span><span class="sxs-lookup"><span data-stu-id="1ad20-102">Files That Manage Solutions and Projects</span></span>
  <span data-ttu-id="1ad20-103">Este tópico descreve os tipos de arquivos específicos para o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ad20-103">This topic describes the file types that are specific to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="1ad20-104">Por padrão, todas as soluções e seus projetos são criados em \Meus Documentos\SQL Server Management Studio Projects.</span><span class="sxs-lookup"><span data-stu-id="1ad20-104">By default, all solutions and their projects are created in \My Documents\SQL Server Management Studio Projects.</span></span>  
  
## <a name="management-studio-solution-files"></a><span data-ttu-id="1ad20-105">Arquivos de solução do Management Studio</span><span class="sxs-lookup"><span data-stu-id="1ad20-105">Management Studio Solution Files</span></span>  
 <span data-ttu-id="1ad20-106">O [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] usa tipos de arquivo diferentes em comparação com o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] ou o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1ad20-106">[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] uses different file types than [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio.</span></span> <span data-ttu-id="1ad20-107">Isso significa que você não pode abrir uma solução [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] ou não Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1ad20-107">This means you cannot open a [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] solution in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or in Visual Studio.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="1ad20-108">Os arquivos da solução permitem que o Gerenciador de Soluções exiba uma interface gráfica para gerenciar seus arquivos.</span><span class="sxs-lookup"><span data-stu-id="1ad20-108">solution files allow Solution Explorer to display a graphical interface for managing your files.</span></span>  
  
|<span data-ttu-id="1ad20-109">Extensão</span><span class="sxs-lookup"><span data-stu-id="1ad20-109">Extension</span></span>|<span data-ttu-id="1ad20-110">Tipo de arquivo</span><span class="sxs-lookup"><span data-stu-id="1ad20-110">File type</span></span>|<span data-ttu-id="1ad20-111">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="1ad20-111">Description</span></span>|<span data-ttu-id="1ad20-112">Criado por</span><span class="sxs-lookup"><span data-stu-id="1ad20-112">Created by</span></span>|  
|---------------|---------------|-----------------|----------------|  
|<span data-ttu-id="1ad20-113">.ssmssln</span><span class="sxs-lookup"><span data-stu-id="1ad20-113">.ssmssln</span></span>|[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="1ad20-114">Objeto de solução</span><span class="sxs-lookup"><span data-stu-id="1ad20-114">Solution Object</span></span>|<span data-ttu-id="1ad20-115">Fornece o ambiente com referências ao local em disco de projetos, itens de projeto e soluções do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ad20-115">Provides the environment with references to the location on disk of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] projects, project items, and solution</span></span>|[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]|  
  
## <a name="management-studio-project-files"></a><span data-ttu-id="1ad20-116">Arquivos de projeto do Management Studio</span><span class="sxs-lookup"><span data-stu-id="1ad20-116">Management Studio Project Files</span></span>  
 <span data-ttu-id="1ad20-117">Da mesma forma que as soluções contêm arquivos que gerenciam os objetos da solução, os projetos contêm arquivos de projeto.</span><span class="sxs-lookup"><span data-stu-id="1ad20-117">In the same way that solutions contain solution files that manage objects in a solution, projects contain project files.</span></span> <span data-ttu-id="1ad20-118">O tipo de arquivo de projeto que o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] cria para um projeto depende do modelo usado para criar o projeto.</span><span class="sxs-lookup"><span data-stu-id="1ad20-118">The type of project file that [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] creates for a project depends on the template used to create the project.</span></span> <span data-ttu-id="1ad20-119">A tabela a seguir descreve o tipo de arquivo criado para cada projeto.</span><span class="sxs-lookup"><span data-stu-id="1ad20-119">The following table describes the type of file created for each project.</span></span>  
  
|<span data-ttu-id="1ad20-120">Extensão</span><span class="sxs-lookup"><span data-stu-id="1ad20-120">Extension</span></span>|<span data-ttu-id="1ad20-121">Modelo do projeto</span><span class="sxs-lookup"><span data-stu-id="1ad20-121">Project template</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="1ad20-122">.ssmssqlproj</span><span class="sxs-lookup"><span data-stu-id="1ad20-122">.ssmssqlproj</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1ad20-123">Projeto de scripts</span><span class="sxs-lookup"><span data-stu-id="1ad20-123">Scripts Project</span></span>|  
|<span data-ttu-id="1ad20-124">.ssmsasproj</span><span class="sxs-lookup"><span data-stu-id="1ad20-124">.ssmsasproj</span></span>|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="1ad20-125">Projeto de scripts</span><span class="sxs-lookup"><span data-stu-id="1ad20-125">Scripts Project</span></span>|  
  
## <a name="location-of-solution-level-files"></a><span data-ttu-id="1ad20-126">Local dos arquivos do nível da solução</span><span class="sxs-lookup"><span data-stu-id="1ad20-126">Location of Solution-Level Files</span></span>  
 <span data-ttu-id="1ad20-127">Por padrão, arquivos do nível da solução são criados no diretório físico do primeiro projeto criado com a solução.</span><span class="sxs-lookup"><span data-stu-id="1ad20-127">By default, solution-level files are created in the physical directory of the first project that is created with the solution.</span></span> <span data-ttu-id="1ad20-128">Você pode especificar um diretório para a solução criando uma solução, ou especificar o diretório ao criar um projeto novo.</span><span class="sxs-lookup"><span data-stu-id="1ad20-128">You can specify a directory for the solution by creating a solution, or you can specify the directory when you create a new project.</span></span>  
  
 <span data-ttu-id="1ad20-129">Se você tiver uma estrutura de diretórios semelhante à estrutura lógica mostrada no Gerenciador de Soluções, os arquivos de projeto e solução serão mais fáceis de localizar e compartilhar com outros desenvolvedores em uma equipe.</span><span class="sxs-lookup"><span data-stu-id="1ad20-129">If you have a directory structure similar to the logical structure shown in Solution Explorer, project and solution files are easier to locate and share with other developers on a team.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ad20-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1ad20-130">See Also</span></span>  
 <span data-ttu-id="1ad20-131">[Gerenciar arquivos com codificação](manage-files-with-encoding.md) </span><span class="sxs-lookup"><span data-stu-id="1ad20-131">[Manage Files with Encoding](manage-files-with-encoding.md) </span></span>  
 <span data-ttu-id="1ad20-132">[Arquivos diversos](miscellaneous-files.md) </span><span class="sxs-lookup"><span data-stu-id="1ad20-132">[Miscellaneous Files](miscellaneous-files.md) </span></span>  
 <span data-ttu-id="1ad20-133">[Gerenciador de Soluções](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="1ad20-133">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="1ad20-134">[Soluções &#40;SQL Server Management Studio&#41;](solutions-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="1ad20-134">[Solutions &#40;SQL Server Management Studio&#41;](solutions-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="1ad20-135">[Projetos &#40;SQL Server Management Studio&#41;](projects-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="1ad20-135">[Projects &#40;SQL Server Management Studio&#41;](projects-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="1ad20-136">Controle do código-fonte do Gerenciador de Soluções</span><span class="sxs-lookup"><span data-stu-id="1ad20-136">Solution Explorer Source Control</span></span>](../../database-engine/solution-explorer-source-control.md)  
  
  
