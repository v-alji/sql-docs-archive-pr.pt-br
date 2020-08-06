---
title: Geração de scripts do mecanismo de banco de dados
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- scripts [SQL Server], PowerShell
- scripts [SQL Server]
- scripting [SQL Server Database Engine]
- scripting [SQL Server Database Engine], PowerShell
ms.assetid: 9978a884-59a2-4e7f-a82a-335149f3a261
author: rothja
ms.author: jroth
ms.openlocfilehash: 79dca27e2aa5f2c0bc473534e0a8b204345b3993
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568428"
---
# <a name="database-engine-scripting"></a><span data-ttu-id="ad789-102">Geração de scripts do mecanismo de banco de dados</span><span class="sxs-lookup"><span data-stu-id="ad789-102">Database Engine Scripting</span></span>
  <span data-ttu-id="ad789-103">O [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] oferece suporte ao ambiente de script do [!INCLUDE[msCoName](../../includes/msconame-md.md)] PowerShell para gerenciar instâncias do [!INCLUDE[ssDE](../../includes/ssde-md.md)] e os objetos nas instâncias.</span><span class="sxs-lookup"><span data-stu-id="ad789-103">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] supports the [!INCLUDE[msCoName](../../includes/msconame-md.md)] PowerShell scripting environment to manage instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and the objects in the instances.</span></span> <span data-ttu-id="ad789-104">Também é possível criar e executar consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] que contêm [!INCLUDE[tsql](../../includes/tsql-md.md)] e XQuery em ambientes muito semelhantes aos ambientes de script.</span><span class="sxs-lookup"><span data-stu-id="ad789-104">You can also build and run [!INCLUDE[ssDE](../../includes/ssde-md.md)] queries that contain [!INCLUDE[tsql](../../includes/tsql-md.md)] and XQuery in environments very similar to scripting environments.</span></span>  
  
## <a name="sql-server-powershell"></a><span data-ttu-id="ad789-105">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad789-105">SQL Server PowerShell</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ad789-106">inclui dois snap-ins do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell que implementam:</span><span class="sxs-lookup"><span data-stu-id="ad789-106">includes two [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell snap-ins that implement:</span></span>  
  
-   <span data-ttu-id="ad789-107">Um provedor do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell que expõe as hierarquias de modelos de objeto de gerenciamento do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] como caminhos do PowerShell que são semelhantes aos caminhos do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="ad789-107">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell provider that exposes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] management object model hierarchies as PowerShell paths that are similar to file system paths.</span></span> <span data-ttu-id="ad789-108">É possível usar as classes de modelo de objeto de gerenciamento do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para gerenciar os objetos representados em cada nó do caminho.</span><span class="sxs-lookup"><span data-stu-id="ad789-108">You can use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] management object model classes to manage the objects represented at each node of the path.</span></span>  
  
-   <span data-ttu-id="ad789-109">Um conjunto de cmdlets do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que implementa comandos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ad789-109">A set of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cmdlets that implement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] commands.</span></span> <span data-ttu-id="ad789-110">Um dos cmdlets é **Invoke-Sqlcmd**.</span><span class="sxs-lookup"><span data-stu-id="ad789-110">One of the cmdlets is **Invoke-Sqlcmd**.</span></span> <span data-ttu-id="ad789-111">Isso é usado para executar [!INCLUDE[ssDE](../../includes/ssde-md.md)] scripts de consulta a serem executados com o `sqlcmd` utilitário.</span><span class="sxs-lookup"><span data-stu-id="ad789-111">This is used to run [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query scripts to be run with the `sqlcmd` utility.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ad789-112">fornece estes recursos para execução do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ad789-112">provides these features for running PowerShell:</span></span>  
  
-   <span data-ttu-id="ad789-113">O módulo **sqlps** do PowerShell que pode ser importado para uma sessão do PowerShell; em seguida, o módulo carrega os snap-ins do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . É possível executar interativamente comandos do PowerShell ad hoc.</span><span class="sxs-lookup"><span data-stu-id="ad789-113">The **sqlps** PowerShell module that can be imported to a PowerShell session, the module then loads the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] snap-ins. You can interactively run ad hoc PowerShell commands.</span></span> <span data-ttu-id="ad789-114">É possível executar arquivos de script usando um comando como .\MyFolder\MyScript.ps1.</span><span class="sxs-lookup"><span data-stu-id="ad789-114">You can run script files using a command such as .\MyFolder\MyScript.ps1.</span></span>  
  
-   <span data-ttu-id="ad789-115">Os arquivos de script do PowerShell podem ser usados como entrada para etapas de trabalho do PowerShell do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent que executam os scripts em intervalos agendados ou em resposta a eventos do sistema.</span><span class="sxs-lookup"><span data-stu-id="ad789-115">PowerShell script files can be used as input to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent PowerShell job steps that run the scripts either at scheduled intervals or in response to system events.</span></span>  
  
-   <span data-ttu-id="ad789-116">O utilitário **sqlps** que inicia o PowerShell e importa o módulo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ad789-116">The **sqlps** utility that starts PowerShell and imports the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] module.</span></span> <span data-ttu-id="ad789-117">Em seguida, você pode executar todas as ações com suporte no módulo.</span><span class="sxs-lookup"><span data-stu-id="ad789-117">You can then perform all actions supported by the module.</span></span> <span data-ttu-id="ad789-118">É possível iniciar o utilitário **sqlps** em um prompt de comando ou clicando com o botão direito do mouse nos nós da árvore do Pesquisador de Objetos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Studio e selecionando **Iniciar PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ad789-118">You can start the **sqlps** utility either in a command prompt or by right-clicking on the nodes in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Studio Object Explorer tree and selecting **Start PowerShell**.</span></span>  
  
## <a name="database-engine-queries"></a><span data-ttu-id="ad789-119">Consultas do mecanismo de banco de dados</span><span class="sxs-lookup"><span data-stu-id="ad789-119">Database Engine Queries</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)] <span data-ttu-id="ad789-120">contêm três tipos de elementos:</span><span class="sxs-lookup"><span data-stu-id="ad789-120">query scripts contain three types of elements:</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="ad789-121">.</span><span class="sxs-lookup"><span data-stu-id="ad789-121">language statements.</span></span>  
  
-   <span data-ttu-id="ad789-122">Instruções de linguagem XQuery</span><span class="sxs-lookup"><span data-stu-id="ad789-122">XQuery language statements</span></span>  
  
-   <span data-ttu-id="ad789-123">Comandos e variáveis do `sqlcmd` utilitário.</span><span class="sxs-lookup"><span data-stu-id="ad789-123">Commands and variables from the `sqlcmd` utility.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ad789-124">fornece três ambientes para criar e executar consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="ad789-124">provides three environments for building and running [!INCLUDE[ssDE](../../includes/ssde-md.md)] queries:</span></span>  
  
-   <span data-ttu-id="ad789-125">É possível executar e depurar consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] interativamente no Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad789-125">You can interactively run and debug [!INCLUDE[ssDE](../../includes/ssde-md.md)] queries in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="ad789-126">É possível codificar e depurar várias instruções em uma sessão e, em seguida, salvar todas as instruções em um único arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="ad789-126">You can code and debug several statements in one session, then save all of the statements in a single script file.</span></span>  
  
-   <span data-ttu-id="ad789-127">O `sqlcmd` Utilitário de prompt de comando permite executar consultas interativamente [!INCLUDE[ssDE](../../includes/ssde-md.md)] e também executar [!INCLUDE[ssDE](../../includes/ssde-md.md)] arquivos de script de consulta existentes.</span><span class="sxs-lookup"><span data-stu-id="ad789-127">The `sqlcmd` command prompt utility lets you interactively run [!INCLUDE[ssDE](../../includes/ssde-md.md)] queries, and also run existing [!INCLUDE[ssDE](../../includes/ssde-md.md)] query script files.</span></span>  
  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)] <span data-ttu-id="ad789-128">normalmente são codificados interativamente no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] usando o Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ad789-128">query script files are typically coded interactively in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] by using the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span> <span data-ttu-id="ad789-129">O arquivo pode ser aberto posteriormente em um destes ambientes:</span><span class="sxs-lookup"><span data-stu-id="ad789-129">The file can later be opened in one of these environments:</span></span>  
  
-   <span data-ttu-id="ad789-130">Use o menu [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] **Abrir**/**do** para abrir o arquivo em uma nova janela do Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad789-130">Use the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] **File**/**Open** menu to open the file in a new [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window.</span></span>  
  
-   <span data-ttu-id="ad789-131">Use o parâmetro **-i**_input_file_ para executar o arquivo com o `sqlcmd` utilitário.</span><span class="sxs-lookup"><span data-stu-id="ad789-131">Use the **-i**_input_file_ parameter to run the file with the `sqlcmd` utility.</span></span>  
  
-   <span data-ttu-id="ad789-132">Use o parâmetro **-QueryFromFile** para executar o arquivo com o cmdlet **Invoke-Sqlcmd** em scripts do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ad789-132">Use the **-QueryFromFile** parameter to run the file with the **Invoke-Sqlcmd** cmdlet in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell scripts.</span></span>  
  
-   <span data-ttu-id="ad789-133">Use etapas de trabalho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent [!INCLUDE[tsql](../../includes/tsql-md.md)] para executar os scripts em intervalos agendados ou em resposta a eventos do sistema.</span><span class="sxs-lookup"><span data-stu-id="ad789-133">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent [!INCLUDE[tsql](../../includes/tsql-md.md)] job steps to run the scripts either at scheduled intervals or in response to system events.</span></span>  
  
 <span data-ttu-id="ad789-134">Além disso, você pode usar o Assistente para Gerar Scripts do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para gerar scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ad789-134">In addition, you can use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Generate Script Wizard to generate [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts.</span></span> <span data-ttu-id="ad789-135">Você pode clicar com o botão direito do mouse no Pesquisador de Objetos do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e selecionar o item de menu **Gerar Script** .</span><span class="sxs-lookup"><span data-stu-id="ad789-135">You can right-click objects in the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer, then select the **Generate Script** menu item.</span></span> <span data-ttu-id="ad789-136">A opção**Gerar Script** inicia o assistente que fornece instruções para o processo de criação de um script.</span><span class="sxs-lookup"><span data-stu-id="ad789-136">**Generate Script** launches the wizard, which guides you through the process of creating a script.</span></span>  
  
## <a name="database-engine-scripting-tasks"></a><span data-ttu-id="ad789-137">Tarefas de scripts do mecanismo de banco de dados</span><span class="sxs-lookup"><span data-stu-id="ad789-137">Database Engine Scripting Tasks</span></span>  
  
|<span data-ttu-id="ad789-138">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="ad789-138">Task Description</span></span>|<span data-ttu-id="ad789-139">Tópico</span><span class="sxs-lookup"><span data-stu-id="ad789-139">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="ad789-140">Descreve como usar código e editores de texto no [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] para desenvolver, depurar e executar interativamente scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ad789-140">Describes how to use the code and text editors in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to interactively develop, debug, and run [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts</span></span>|[<span data-ttu-id="ad789-141">Editores de consultas e de texto &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="ad789-141">Query and Text Editors &#40;SQL Server Management Studio&#41;</span></span>](../scripting/query-and-text-editors-sql-server-management-studio.md)|  
|<span data-ttu-id="ad789-142">Descreve como usar o utilitário `sqlcmd` para executar scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] do prompt de comando, incluindo a capacidade de desenvolver scripts de maneira interativa.</span><span class="sxs-lookup"><span data-stu-id="ad789-142">Describes how to use the `sqlcmd` utility to run [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts from the command prompt, including the ability to interactively develop scripts.</span></span>|[<span data-ttu-id="ad789-143">Tópicos de informações práticas sobre sqlcmd</span><span class="sxs-lookup"><span data-stu-id="ad789-143">sqlcmd How-to Topics</span></span>](../../database-engine/sqlcmd-how-to-topics.md)|  
|<span data-ttu-id="ad789-144">Descreve como integrar os componentes do SQL Server em um ambiente do Windows PowerShell 2.0 e depois criar scripts do PowerShell para gerenciar instâncias e objetos do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ad789-144">Describes how to integrate the SQL Server components into a Windows PowerShell 2.0 environment and then build PowerShell scripts for managing SQL Server instances and objects.</span></span>|[<span data-ttu-id="ad789-145">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad789-145">SQL Server PowerShell</span></span>](../../powershell/sql-server-powershell.md)|  
|<span data-ttu-id="ad789-146">Descreve como usar o assistente para **Gerar e Publicar Scripts** para criar scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] que recriam um ou mais dos objetos de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ad789-146">Describes how to use the **Generate and Publish Scripts** wizard to create [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts that recreate one or more of the objects from a database.</span></span>|[<span data-ttu-id="ad789-147">Gerar scripts &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="ad789-147">Generate Scripts &#40;SQL Server Management Studio&#41;</span></span>](generate-scripts-sql-server-management-studio.md)|  
  
## <a name="see-also"></a><span data-ttu-id="ad789-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ad789-148">See Also</span></span>  
 <span data-ttu-id="ad789-149">[Utilitário sqlcmd](../../tools/sqlcmd-utility.md) </span><span class="sxs-lookup"><span data-stu-id="ad789-149">[sqlcmd Utility](../../tools/sqlcmd-utility.md) </span></span>  
 [<span data-ttu-id="ad789-150">Tutorial: Gravando instruções Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ad789-150">Tutorial: Writing Transact-SQL Statements</span></span>](../../t-sql/tutorial-writing-transact-sql-statements.md)  
  
  