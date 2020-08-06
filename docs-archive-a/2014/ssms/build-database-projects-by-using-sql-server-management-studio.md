---
title: Construir projetos de banco de dados usando o SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- scripts [SQL Server], database projects
- database projects [SQL Server]
- projects [SQL Server Management Studio], about projects
- projects [SQL Server Management Studio]
ms.assetid: c2e80045-894d-44cf-b65c-e547ed738947
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3ddf3f61e69623716b2987c5c4d849398e822d18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568336"
---
# <a name="build-database-projects-by-using-sql-server-management-studio"></a><span data-ttu-id="620d0-102">Construir projetos de banco de dados usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="620d0-102">Build Database Projects by Using SQL Server Management Studio</span></span>
  <span data-ttu-id="620d0-103">Um projeto de script de banco de dados é um conjunto organizado de scripts, informações de conexão e modelos que são todos associados a um banco de dados ou a uma parte de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="620d0-103">A database script project is an organized set of scripts, connection information, and templates that are all associated with a database or one part of a database.</span></span> <span data-ttu-id="620d0-104">O [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] fornece o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para administrar e criar bancos de dados do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] no contexto de um projeto de script.</span><span class="sxs-lookup"><span data-stu-id="620d0-104">[!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provides the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] for administering and designing [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] databases within the context of a script project.</span></span> [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="620d0-105">inclui os designers, editores, guias e assistentes para ajudar os usuários a desenvolver, implantar e manter bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="620d0-105">includes designers, editors, guides and wizards to assist users in developing, deploying and maintaining databases.</span></span>  
  
## <a name="sql-server-management-studio"></a><span data-ttu-id="620d0-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="620d0-106">SQL Server Management Studio</span></span>  
 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="620d0-107">é um pacote de ferramentas administrativas para gerenciar os componentes que pertencem ao [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="620d0-107">is a suite of administrative tools for managing the components belonging to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="620d0-108">Esse ambiente integrado permite aos usuários executar uma variedade de tarefas, como backup de dados, edição de consultas e automação de funções comuns dentro de uma única interface.</span><span class="sxs-lookup"><span data-stu-id="620d0-108">This integrated environment allows users to perform a variety of tasks, such as backing up data, editing queries, and automating common functions within a single interface.</span></span>  
  
 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="620d0-109">inclui as seguintes ferramentas:</span><span class="sxs-lookup"><span data-stu-id="620d0-109">includes the following tools:</span></span>  
  
-   <span data-ttu-id="620d0-110">O Editor de Códigos é um editor de script avançado para escrever e editar scripts.</span><span class="sxs-lookup"><span data-stu-id="620d0-110">Code Editor is a rich script editor for writing and editing scripts.</span></span> [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="620d0-111">fornece quatro versões do Editor de Códigos: o Editor de Consultas [!INCLUDE[ssDE](../includes/ssde-md.md)] para scripts [!INCLUDE[tsql](../includes/tsql-md.md)] , o Editor de Consultas DMX, o Editor de Consultas MDX e o Editor de Consultas XML/A.</span><span class="sxs-lookup"><span data-stu-id="620d0-111">provides four versions of the Code Editor; the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor for [!INCLUDE[tsql](../includes/tsql-md.md)] scripts, the DMX Query Editor, the MDX Query Editor, and the XML/A Query Editor.</span></span>  
  
-   <span data-ttu-id="620d0-112">O Pesquisador de Objetos para localizar, modificar, criar scripts ou executar objetos que pertençam a instâncias do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="620d0-112">Object Explorer for locating, modifying, scripting or running objects belonging to instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="620d0-113">Explorador de Modelos, para localizar e gerar scripts de modelos.</span><span class="sxs-lookup"><span data-stu-id="620d0-113">Template Explorer for locating and scripting templates.</span></span>  
  
-   <span data-ttu-id="620d0-114">Gerenciador de Soluções, para organizar e armazenar scripts relacionados como partes de um projeto.</span><span class="sxs-lookup"><span data-stu-id="620d0-114">Solution Explorer for organizing and storing related scripts as parts of a project.</span></span>  
  
-   <span data-ttu-id="620d0-115">Janela Propriedades, para exibir as propriedades atuais de objetos selecionados.</span><span class="sxs-lookup"><span data-stu-id="620d0-115">Properties Window for displaying the current properties of selected objects.</span></span>  
  
 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="620d0-116">dá suporte a processos de trabalho eficientes, fornecendo:</span><span class="sxs-lookup"><span data-stu-id="620d0-116">supports efficient work processes by providing:</span></span>  
  
-   <span data-ttu-id="620d0-117">Acesso desconectado.</span><span class="sxs-lookup"><span data-stu-id="620d0-117">Disconnected access.</span></span> <span data-ttu-id="620d0-118">Você pode escrever e editar scripts sem conectar-se a uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="620d0-118">You can write and edit scripts without connecting to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="620d0-119">Scripts em qualquer caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="620d0-119">Scripting from any dialog box.</span></span> <span data-ttu-id="620d0-120">Você pode criar um script em qualquer caixa de diálogo, o que lhe permite ler, modificar, armazenar e reutilizar os scripts depois de criá-los.</span><span class="sxs-lookup"><span data-stu-id="620d0-120">You can create a script from any dialog box so that you can read, modify, store and reuse the scripts after you create them.</span></span>  
  
-   <span data-ttu-id="620d0-121">Caixas de diálogo não restritas.</span><span class="sxs-lookup"><span data-stu-id="620d0-121">Nonmodal dialog boxes.</span></span> <span data-ttu-id="620d0-122">Ao acessar uma caixa de diálogo de UI, você pode consultar outros recursos do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] sem fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="620d0-122">When you access a UI dialog box you can browse other resources in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] without closing the dialog box.</span></span>  
  
## <a name="solutions-and-script-projects"></a><span data-ttu-id="620d0-123">Soluções e Projetos de Script</span><span class="sxs-lookup"><span data-stu-id="620d0-123">Solutions and Script Projects</span></span>  
 <span data-ttu-id="620d0-124">O Gerenciador de Soluções é um utilitário para armazenar e reabrir soluções de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="620d0-124">Solution Explorer is a utility to store and reopen database solutions.</span></span> <span data-ttu-id="620d0-125">As soluções permitem organizar projetos e arquivos de script relacionados.</span><span class="sxs-lookup"><span data-stu-id="620d0-125">Solutions organize related script projects and files.</span></span> <span data-ttu-id="620d0-126">Os projetos de script armazenam arquivos de script, modelos SQL, informações de conexão e vários outros arquivos de informações do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="620d0-126">Script projects store [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] script files, SQL templates, connection information and other miscellaneous files.</span></span> <span data-ttu-id="620d0-127">Quando um script é salvo em um projeto de script, os usuários podem:</span><span class="sxs-lookup"><span data-stu-id="620d0-127">When a script is saved in a script project, users are able to:</span></span>  
  
-   <span data-ttu-id="620d0-128">Manter controle de versão em scripts.</span><span class="sxs-lookup"><span data-stu-id="620d0-128">Maintain version control on scripts.</span></span>  
  
-   <span data-ttu-id="620d0-129">Armazenar opções de resultados com um script.</span><span class="sxs-lookup"><span data-stu-id="620d0-129">Store results options with a script.</span></span>  
  
-   <span data-ttu-id="620d0-130">Organizar scripts relacionados em um único projeto de script.</span><span class="sxs-lookup"><span data-stu-id="620d0-130">Organize related scripts in a single script project.</span></span>  
  
-   <span data-ttu-id="620d0-131">Salvar informações de conexão com scripts.</span><span class="sxs-lookup"><span data-stu-id="620d0-131">Save connection information with scripts.</span></span>  
  
 <span data-ttu-id="620d0-132">O Gerenciador de Soluções é uma ferramenta para desenvolvedores que criam e reutilizam scripts relacionados ao mesmo projeto.</span><span class="sxs-lookup"><span data-stu-id="620d0-132">Solution Explorer is a tool for developers who are creating and reusing scripts that are related to the same project.</span></span> <span data-ttu-id="620d0-133">Se uma tarefa semelhante for necessária posteriormente, você poderá usar um grupo de scripts que foram armazenados em um projeto.</span><span class="sxs-lookup"><span data-stu-id="620d0-133">If a similar task is required later, you can use group of scripts that were stored in a project.</span></span> <span data-ttu-id="620d0-134">Caso já tenha criado aplicativos usando o [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], verá que o Gerenciador de Soluções é bem familiar.</span><span class="sxs-lookup"><span data-stu-id="620d0-134">If you have created applications by using [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], you will find Solution Explorer very familiar.</span></span>  
  
 <span data-ttu-id="620d0-135">Uma solução consiste em um ou mais projetos de script.</span><span class="sxs-lookup"><span data-stu-id="620d0-135">A solution consists of one or more script projects.</span></span> <span data-ttu-id="620d0-136">Um projeto consiste em um ou mais scripts ou conexões.</span><span class="sxs-lookup"><span data-stu-id="620d0-136">A project consists of one or more scripts or connections.</span></span> <span data-ttu-id="620d0-137">Um projeto também pode incluir arquivos não script.</span><span class="sxs-lookup"><span data-stu-id="620d0-137">A project may also include nonscript files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="620d0-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="620d0-138">See Also</span></span>  
 <span data-ttu-id="620d0-139">[Usar SQL Server Management Studio](../database-engine/use-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="620d0-139">[Use SQL Server Management Studio](../database-engine/use-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="620d0-140">[Editores de consulta e de texto &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/query-and-text-editors-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="620d0-140">[Query and Text Editors &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/query-and-text-editors-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="620d0-141">Soluções &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="620d0-141">Solutions &#40;SQL Server Management Studio&#41;</span></span>](solution/solutions-sql-server-management-studio.md)  
  
  
