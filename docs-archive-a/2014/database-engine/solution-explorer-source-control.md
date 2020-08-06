---
title: Controle do código-fonte Gerenciador de Soluções | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Visual SourceSafe
- SQL Server Management Studio [SQL Server], source control services
- source-controlled files [SQL Server]
- source controls [SQL Server Management Studio], services
- version control services [SQL Server]
- file source control services [SQL Server]
- VSS [Visual SourceSafe]
ms.assetid: 6373adb8-3d81-4945-a9fc-1d0d5799d29a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 46471ba8149c26f80e78006bc3a8befc2e81b416
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575989"
---
# <a name="solution-explorer-source-control"></a><span data-ttu-id="dfd42-102">Controle do código-fonte do Gerenciador de Soluções</span><span class="sxs-lookup"><span data-stu-id="dfd42-102">Solution Explorer Source Control</span></span>
  [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="dfd42-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]Gerenciador de soluções pode ser integrado a um sistema de controle do código-fonte separado.</span><span class="sxs-lookup"><span data-stu-id="dfd42-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] Solution Explorer can be integrated into a separate source control system.</span></span> <span data-ttu-id="dfd42-104">Quando uma solução ou projeto é integrado em um sistema de controle do código-fonte, você pode controlar o acesso ao arquivo e a versão para os scripts e consultas em seus projetos.</span><span class="sxs-lookup"><span data-stu-id="dfd42-104">Once a solution or project is integrated into a source control system, you can control file access and versioning for the scripts and queries in your projects.</span></span>  
  
## <a name="solution-and-project-source-control"></a><span data-ttu-id="dfd42-105">Solução e projeto no controle do código-fonte</span><span class="sxs-lookup"><span data-stu-id="dfd42-105">Solution and Project Source Control</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../includes/ssnotedepfutureavoid-md.md)]  
  
 <span data-ttu-id="dfd42-106">O controle do código-fonte recorre a um sistema em que uma parte central do software de servidor armazena e rastreia versões de arquivos e também controla o acesso a eles.</span><span class="sxs-lookup"><span data-stu-id="dfd42-106">Source control refers to a system in which a central piece of server software stores and tracks file versions, and also controls access to files.</span></span> <span data-ttu-id="dfd42-107">Um sistema de controle do código-fonte típico inclui um provedor de controle do código-fonte, e dois ou mais clientes de controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="dfd42-107">A typical source control system includes a source control provider and two or more source control clients.</span></span> <span data-ttu-id="dfd42-108">O [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] pode ser integrado a um serviço de controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="dfd42-108">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] can be integrated with a source control service.</span></span> <span data-ttu-id="dfd42-109">Isso significa que você pode usar a ferramenta como um cliente de seu provedor de controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="dfd42-109">This means you can use the tool as a client for your source control provider.</span></span> <span data-ttu-id="dfd42-110">Sem deixar o ambiente, você pode administrar seus projetos individuais e em equipe facilmente.</span><span class="sxs-lookup"><span data-stu-id="dfd42-110">Without leaving the environment, you can manage your individual and team projects easily.</span></span> <span data-ttu-id="dfd42-111">O provedor de controle do código-fonte não é incluído com o [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dfd42-111">The source control provider is not included with [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
#### <a name="to-select-a-source-control-provider"></a><span data-ttu-id="dfd42-112">Para selecionar um provedor de controle do código-fonte</span><span class="sxs-lookup"><span data-stu-id="dfd42-112">To select a source control provider</span></span>  
  
1.  <span data-ttu-id="dfd42-113">Instale a parte cliente de seu provedor de controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="dfd42-113">Install the client portion of your source control provider.</span></span>  
  
2.  <span data-ttu-id="dfd42-114">No [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], no menu **Ferramentas** , clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="dfd42-114">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], on the **Tools** menu, click **Options**.</span></span>  
  
3.  <span data-ttu-id="dfd42-115">Na caixa de diálogo **Opções** , expanda **controle do código-fonte**e clique na página **seleção de plug-in** .</span><span class="sxs-lookup"><span data-stu-id="dfd42-115">In the **Options** dialog box, expand **Source Control**, and then click the **Plug-in Selection** page.</span></span>  
  
4.  <span data-ttu-id="dfd42-116">Na caixa de **plug-in do controle do código-fonte atual** , selecione o plug-in de controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="dfd42-116">In the **Current source control plug-in** box, select the source control plug-in.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dfd42-117">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="dfd42-117">In This Section</span></span>  
  
|<span data-ttu-id="dfd42-118">Tópico</span><span class="sxs-lookup"><span data-stu-id="dfd42-118">Topic</span></span>|<span data-ttu-id="dfd42-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="dfd42-119">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="dfd42-120">Noções básicas de controle do código-fonte</span><span class="sxs-lookup"><span data-stu-id="dfd42-120">Source Control Basics</span></span>](../../2014/database-engine/source-control-basics.md)|<span data-ttu-id="dfd42-121">Define a terminologia básica de controle do código-fonte e explica como seu projeto pode se beneficiar do uso de controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="dfd42-121">Defines basic source control terminology, and explains how your project can benefit from using source control services.</span></span>|  
|[<span data-ttu-id="dfd42-122">Adicionar soluções e projetos ao controle do código-fonte</span><span class="sxs-lookup"><span data-stu-id="dfd42-122">Add Solutions and Projects to Source Control</span></span>](../../2014/database-engine/add-solutions-and-projects-to-source-control.md)|<span data-ttu-id="dfd42-123">Explica como usar o ambiente do [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] para adicionar soluções e projetos ao controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="dfd42-123">Explains how to use the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment to add solutions and projects to source control.</span></span>|  
|[<span data-ttu-id="dfd42-124">Abrir soluções e projetos no controle do código-fonte</span><span class="sxs-lookup"><span data-stu-id="dfd42-124">Open Solutions and Projects from Source Control</span></span>](../../2014/database-engine/open-solutions-and-projects-from-source-control.md)|<span data-ttu-id="dfd42-125">Explica como usar o ambiente do [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] para abrir soluções e projetos com controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="dfd42-125">Explains how to use the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment to open source-controlled solutions and projects.</span></span>|  
|[<span data-ttu-id="dfd42-126">Gerenciar check-outs</span><span class="sxs-lookup"><span data-stu-id="dfd42-126">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)|<span data-ttu-id="dfd42-127">Explica como fazer check-out em soluções e arquivos de controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="dfd42-127">Explains how to check out solutions and files from source control.</span></span>|  
|[<span data-ttu-id="dfd42-128">Gerenciar check-ins</span><span class="sxs-lookup"><span data-stu-id="dfd42-128">Manage Checkins</span></span>](../../2014/database-engine/manage-checkins.md)|<span data-ttu-id="dfd42-129">Explica como fazer check-in de soluções e arquivos em controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="dfd42-129">Explains how to check solutions and files into source control.</span></span>|  
|[<span data-ttu-id="dfd42-130">Definir e recuperar informações de versão</span><span class="sxs-lookup"><span data-stu-id="dfd42-130">Set and Retrieve Version Information</span></span>](../../2014/database-engine/set-and-retrieve-version-information.md)|<span data-ttu-id="dfd42-131">Explica como recuperar o histórico de um projeto ou item, recuperar uma cópia local de um item ou comparar duas versões de item.</span><span class="sxs-lookup"><span data-stu-id="dfd42-131">Explains how to retrieve the history of a project or item, retrieve a local copy of an item, or compare two item versions.</span></span>|  
|||  
  
## <a name="see-also"></a><span data-ttu-id="dfd42-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dfd42-132">See Also</span></span>  
 <span data-ttu-id="dfd42-133">[Gerenciador de Soluções](../ssms/solution/solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="dfd42-133">[Solution Explorer](../ssms/solution/solution-explorer.md) </span></span>  
 <span data-ttu-id="dfd42-134">[Soluções &#40;SQL Server Management Studio&#41;](../ssms/sql-server-management-studio-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="dfd42-134">[Solutions &#40;SQL Server Management Studio&#41;](../ssms/sql-server-management-studio-ssms.md) </span></span>  
 <span data-ttu-id="dfd42-135">[Projetos &#40;SQL Server Management Studio&#41;](../ssms/solution/projects-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="dfd42-135">[Projects &#40;SQL Server Management Studio&#41;](../ssms/solution/projects-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="dfd42-136">Arquivos que gerenciam soluções e projetos</span><span class="sxs-lookup"><span data-stu-id="dfd42-136">Files That Manage Solutions and Projects</span></span>](../ssms/solution/files-that-manage-solutions-and-projects.md)  
  
  
