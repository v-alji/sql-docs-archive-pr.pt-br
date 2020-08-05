---
title: Tarefa Reorganizar Índice (plano de manutenção) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.defrag.f1
helpviewer_keywords:
- Reorganize Index Task dialog box
ms.assetid: e9cbebbd-f36f-4176-9832-382a46ac946c
author: rothja
ms.author: jroth
ms.openlocfilehash: 0bbb154045b781f8a92dfce9c9d2f6ee2d819c17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572520"
---
# <a name="reorganize-index-task-maintenance-plan"></a><span data-ttu-id="aaf02-102">Tarefa de Reorganização de Índice (Plano de Manutenção)</span><span class="sxs-lookup"><span data-stu-id="aaf02-102">Reorganize Index Task (Maintenance Plan)</span></span>
  <span data-ttu-id="aaf02-103">Use a caixa de diálogo **Tarefa de Reorganização de Índice** para mover as páginas de índice em uma ordem de pesquisa mais eficiente.</span><span class="sxs-lookup"><span data-stu-id="aaf02-103">Use the **ReorganizeIndex Task** dialog to move index pages into a more efficient search order.</span></span> <span data-ttu-id="aaf02-104">Esta tarefa usa a instrução `ALTER INDEX REORGANIZE` com bancos de dados do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aaf02-104">This task uses the `ALTER INDEX REORGANIZE` statement with [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] databases.</span></span>  
  
## <a name="options"></a><span data-ttu-id="aaf02-105">Opções</span><span class="sxs-lookup"><span data-stu-id="aaf02-105">Options</span></span>  
 <span data-ttu-id="aaf02-106">**Conexão**</span><span class="sxs-lookup"><span data-stu-id="aaf02-106">**Connection**</span></span>  
 <span data-ttu-id="aaf02-107">Selecione a conexão de servidor a ser usada na execução desta tarefa.</span><span class="sxs-lookup"><span data-stu-id="aaf02-107">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="aaf02-108">**Novo**</span><span class="sxs-lookup"><span data-stu-id="aaf02-108">**New**</span></span>  
 <span data-ttu-id="aaf02-109">Crie uma nova conexão com o servidor para usar ao executar esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="aaf02-109">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="aaf02-110">A caixa de diálogo **Nova Conexão** é descrita abaixo.</span><span class="sxs-lookup"><span data-stu-id="aaf02-110">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="aaf02-111">**Bancos de dados**</span><span class="sxs-lookup"><span data-stu-id="aaf02-111">**Databases**</span></span>  
 <span data-ttu-id="aaf02-112">Especifique os bancos de dados afetados por essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="aaf02-112">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="aaf02-113">**Todos os bancos de dados**</span><span class="sxs-lookup"><span data-stu-id="aaf02-113">**All databases**</span></span>  
  
     <span data-ttu-id="aaf02-114">Gere um plano de manutenção que executa tarefas de manutenção em todos os bancos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , exceto o tempdb.</span><span class="sxs-lookup"><span data-stu-id="aaf02-114">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases except tempdb.</span></span>  
  
-   <span data-ttu-id="aaf02-115">**Todos os bancos de dados do sistema**</span><span class="sxs-lookup"><span data-stu-id="aaf02-115">**All system databases**</span></span>  
  
     <span data-ttu-id="aaf02-116">Gere um plano de manutenção que executa tarefas de manutenção em cada banco de dados do sistema do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , exceto o **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="aaf02-116">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except **tempdb**.</span></span> <span data-ttu-id="aaf02-117">Nenhuma tarefa de manutenção é executada nos bancos de dados criados pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="aaf02-117">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="aaf02-118">**Todos os bancos de dados de usuários**</span><span class="sxs-lookup"><span data-stu-id="aaf02-118">**All user databases**</span></span>  
  
     <span data-ttu-id="aaf02-119">Gere um plano de manutenção que execute tarefas de manutenção em todos os bancos de dados criados por usuários.</span><span class="sxs-lookup"><span data-stu-id="aaf02-119">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="aaf02-120">Nenhuma tarefa de manutenção é executada com os bancos de dados do sistema do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aaf02-120">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="aaf02-121">**Estes bancos de dados específicos**</span><span class="sxs-lookup"><span data-stu-id="aaf02-121">**These specific databases**</span></span>  
  
     <span data-ttu-id="aaf02-122">Gere um plano de manutenção que execute tarefas de manutenção somente nos bancos de dados selecionados.</span><span class="sxs-lookup"><span data-stu-id="aaf02-122">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="aaf02-123">Pelo menos um banco de dados da lista deverá ser selecionado se esta opção for escolhida.</span><span class="sxs-lookup"><span data-stu-id="aaf02-123">At least one database in the list must be selected if this option is chosen.</span></span>  
  
 <span data-ttu-id="aaf02-124">**Objeto**</span><span class="sxs-lookup"><span data-stu-id="aaf02-124">**Object**</span></span>  
 <span data-ttu-id="aaf02-125">Limita a grade **Seleção** para exibir tabelas, exibições ou ambas.</span><span class="sxs-lookup"><span data-stu-id="aaf02-125">Limit the **Selection** grid to display tables, views, or both.</span></span>  
  
 <span data-ttu-id="aaf02-126">**Seleção**</span><span class="sxs-lookup"><span data-stu-id="aaf02-126">**Selection**</span></span>  
 <span data-ttu-id="aaf02-127">Especifique as tabelas ou índices afetados por esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="aaf02-127">Specify the tables or indexes affected by this task.</span></span> <span data-ttu-id="aaf02-128">Não disponível quando a opção **Tabelas e Exibições** é selecionada na caixa **Objeto** .</span><span class="sxs-lookup"><span data-stu-id="aaf02-128">Not available when **Tables and Views** is selected in the **Object** box.</span></span>  
  
 <span data-ttu-id="aaf02-129">**Compactar objetos grandes**</span><span class="sxs-lookup"><span data-stu-id="aaf02-129">**Compact large objects**</span></span>  
 <span data-ttu-id="aaf02-130">Desaloque espaço em tabelas e exibições quando possível.</span><span class="sxs-lookup"><span data-stu-id="aaf02-130">Deallocate space for tables and views when possible.</span></span> <span data-ttu-id="aaf02-131">Esta opção usa `ALTER INDEX LOB_COMPACTION = ON`.</span><span class="sxs-lookup"><span data-stu-id="aaf02-131">This option uses `ALTER INDEX LOB_COMPACTION = ON`.</span></span>  
  
 <span data-ttu-id="aaf02-132">**Exibir T-SQL**</span><span class="sxs-lookup"><span data-stu-id="aaf02-132">**View T-SQL**</span></span>  
 <span data-ttu-id="aaf02-133">Exiba as instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] executadas no servidor para esta tarefa, com base nas opções selecionadas.</span><span class="sxs-lookup"><span data-stu-id="aaf02-133">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aaf02-134">Quando o número de objetos afetados é grande, essa exibição pode ser demorada.</span><span class="sxs-lookup"><span data-stu-id="aaf02-134">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="aaf02-135">Caixa de diálogo Nova Conexão</span><span class="sxs-lookup"><span data-stu-id="aaf02-135">New Connection Dialog Box</span></span>  
 <span data-ttu-id="aaf02-136">**Nome da conexão**</span><span class="sxs-lookup"><span data-stu-id="aaf02-136">**Connection name**</span></span>  
 <span data-ttu-id="aaf02-137">Digite um nome para a nova conexão.</span><span class="sxs-lookup"><span data-stu-id="aaf02-137">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="aaf02-138">**Selecione ou digite um nome de servidor**</span><span class="sxs-lookup"><span data-stu-id="aaf02-138">**Select or enter a server name**</span></span>  
 <span data-ttu-id="aaf02-139">Selecione um servidor com o qual se conectar ao executar esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="aaf02-139">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="aaf02-140">**Atualizar**</span><span class="sxs-lookup"><span data-stu-id="aaf02-140">**Refresh**</span></span>  
 <span data-ttu-id="aaf02-141">Atualize a lista de servidores disponíveis.</span><span class="sxs-lookup"><span data-stu-id="aaf02-141">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="aaf02-142">**Digite as informações para fazer logon no servidor**</span><span class="sxs-lookup"><span data-stu-id="aaf02-142">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="aaf02-143">Especifica como autenticar no servidor.</span><span class="sxs-lookup"><span data-stu-id="aaf02-143">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="aaf02-144">**Use a segurança integrada do Windows**</span><span class="sxs-lookup"><span data-stu-id="aaf02-144">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="aaf02-145">Conecte-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] com a Autenticação do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="aaf02-145">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="aaf02-146">**Usar nome de usuário e senha específicos**</span><span class="sxs-lookup"><span data-stu-id="aaf02-146">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="aaf02-147">Conecte-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aaf02-147">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="aaf02-148">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="aaf02-148">This option is not available.</span></span>  
  
 <span data-ttu-id="aaf02-149">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="aaf02-149">**User name**</span></span>  
 <span data-ttu-id="aaf02-150">Forneça um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a ser usado na autenticação.</span><span class="sxs-lookup"><span data-stu-id="aaf02-150">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="aaf02-151">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="aaf02-151">This option is not available.</span></span>  
  
 <span data-ttu-id="aaf02-152">**Senha**</span><span class="sxs-lookup"><span data-stu-id="aaf02-152">**Password**</span></span>  
 <span data-ttu-id="aaf02-153">Forneça uma senha a ser usada na autenticação.</span><span class="sxs-lookup"><span data-stu-id="aaf02-153">Provide a password to use when authenticating.</span></span> <span data-ttu-id="aaf02-154">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="aaf02-154">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaf02-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aaf02-155">See Also</span></span>  
 <span data-ttu-id="aaf02-156">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aaf02-156">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 [<span data-ttu-id="aaf02-157">DBCC INDEXDEFRAG &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="aaf02-157">DBCC INDEXDEFRAG &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-indexdefrag-transact-sql)  
  
  
