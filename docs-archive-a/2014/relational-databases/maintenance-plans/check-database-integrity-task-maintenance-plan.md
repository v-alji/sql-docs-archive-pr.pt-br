---
title: Tarefa verificar integridade do banco de dados (Plano de Manutenção) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.maintplanproperties.integrity.f1
- sql12.swb.maint.integrity.f1
helpviewer_keywords:
- Check Database Integrity Task dialog box
ms.assetid: 3534494a-5dfe-4738-b49a-e7fabd731c47
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f786755a3b7ed5d991b4cf0e32c067e355c111ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576365"
---
# <a name="check-database-integrity-task-maintenance-plan"></a><span data-ttu-id="7b2fe-102">Tarefa Verificar Integridade do Banco de Dados (Plano de Manutenção)</span><span class="sxs-lookup"><span data-stu-id="7b2fe-102">Check Database Integrity Task (Maintenance Plan)</span></span>
  <span data-ttu-id="7b2fe-103">Use a caixa de diálogo **Tarefa Verificar Integridade do Banco de Dados** para verificar a alocação e integridade estrutural de tabelas do usuário e do sistema, além de índices no banco de dados, executando a instância `DBCC CHECKDB`[!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7b2fe-103">Use the **Check Database Integrity Task** dialog to check the allocation and structural integrity of user and system tables, and indexes in the database, by running the `DBCC CHECKDB`[!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="7b2fe-104">A execução de `DBCC` garante que quaisquer problemas de integridade com o banco de dados sejam reportados, permitindo assim serem endereçados posteriormente por um administrador do sistema ou proprietário de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7b2fe-104">Running `DBCC` ensures that any integrity problems with the database are reported, thereby allowing them to be addressed later by a system administrator or database owner.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7b2fe-105">Opções</span><span class="sxs-lookup"><span data-stu-id="7b2fe-105">Options</span></span>  
 <span data-ttu-id="7b2fe-106">**Conexão**</span><span class="sxs-lookup"><span data-stu-id="7b2fe-106">**Connection**</span></span>  
 <span data-ttu-id="7b2fe-107">Selecione a conexão de servidor a ser usada na execução desta tarefa.</span><span class="sxs-lookup"><span data-stu-id="7b2fe-107">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="7b2fe-108">**Novo**</span><span class="sxs-lookup"><span data-stu-id="7b2fe-108">**New**</span></span>  
 <span data-ttu-id="7b2fe-109">Crie uma nova conexão com o servidor para usar ao executar esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="7b2fe-109">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="7b2fe-110">A caixa de diálogo **Nova Conexão** é descrita abaixo.</span><span class="sxs-lookup"><span data-stu-id="7b2fe-110">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="7b2fe-111">**Bancos de dados**</span><span class="sxs-lookup"><span data-stu-id="7b2fe-111">**Databases**</span></span>  
 <span data-ttu-id="7b2fe-112">Especifique os bancos de dados afetados por essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="7b2fe-112">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="7b2fe-113">**Todos os bancos de dados**</span><span class="sxs-lookup"><span data-stu-id="7b2fe-113">**All databases**</span></span>  
  
     <span data-ttu-id="7b2fe-114">Gere um plano de manutenção que executa tarefas de manutenção em todos os bancos de dados do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], exceto **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="7b2fe-114">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases except **tempdb**.</span></span>  
  
-   <span data-ttu-id="7b2fe-115">**Todos os bancos de dados do sistema**</span><span class="sxs-lookup"><span data-stu-id="7b2fe-115">**All system databases**</span></span>  
  
     <span data-ttu-id="7b2fe-116">Gere um plano de manutenção que executa tarefas de manutenção em cada banco de dados do sistema do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , exceto o **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="7b2fe-116">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except **tempdb**.</span></span> <span data-ttu-id="7b2fe-117">Nenhuma tarefa de manutenção é executada nos bancos de dados criados pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="7b2fe-117">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="7b2fe-118">**Todos os bancos de dados de usuários**</span><span class="sxs-lookup"><span data-stu-id="7b2fe-118">**All user databases**</span></span>  
  
     <span data-ttu-id="7b2fe-119">Gere um plano de manutenção que execute tarefas de manutenção em todos os bancos de dados criados por usuários.</span><span class="sxs-lookup"><span data-stu-id="7b2fe-119">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="7b2fe-120">Nenhuma tarefa de manutenção é executada com os bancos de dados do sistema do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7b2fe-120">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="7b2fe-121">**Estes bancos de dados específicos**</span><span class="sxs-lookup"><span data-stu-id="7b2fe-121">**These specific databases**</span></span>  
  
     <span data-ttu-id="7b2fe-122">Gere um plano de manutenção que execute tarefas de manutenção somente nos bancos de dados selecionados.</span><span class="sxs-lookup"><span data-stu-id="7b2fe-122">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="7b2fe-123">Pelo menos um banco de dados da lista deverá ser selecionado se esta opção for escolhida.</span><span class="sxs-lookup"><span data-stu-id="7b2fe-123">At least one database in the list must be selected if this option is chosen.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7b2fe-124">Os planos de manutenção são executados somente em bancos de dados definidos com nível de compatibilidade 80 ou superior.</span><span class="sxs-lookup"><span data-stu-id="7b2fe-124">Maintenance plans only run against databases set to compatibility level 80 or higher.</span></span> <span data-ttu-id="7b2fe-125">Os bancos de dados definidos para o nível de compatibilidade 70 ou inferior não são exibidos.</span><span class="sxs-lookup"><span data-stu-id="7b2fe-125">Databases set to compatibility level 70 or lower are not displayed.</span></span>  
  
 <span data-ttu-id="7b2fe-126">**Incluir índices**</span><span class="sxs-lookup"><span data-stu-id="7b2fe-126">**Include indexes**</span></span>  
 <span data-ttu-id="7b2fe-127">Verifique a integridade de todas as páginas de índice, assim como das páginas de dados de tabela.</span><span class="sxs-lookup"><span data-stu-id="7b2fe-127">Check the integrity of all the index pages as well as the table data pages.</span></span>  
  
 <span data-ttu-id="7b2fe-128">**Exibir T-SQL**</span><span class="sxs-lookup"><span data-stu-id="7b2fe-128">**View T-SQL**</span></span>  
 <span data-ttu-id="7b2fe-129">Exiba as instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] executadas no servidor para esta tarefa, com base nas opções selecionadas.</span><span class="sxs-lookup"><span data-stu-id="7b2fe-129">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7b2fe-130">Quando o número de objetos afetados é grande, essa exibição pode ser demorada.</span><span class="sxs-lookup"><span data-stu-id="7b2fe-130">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="7b2fe-131">Caixa de diálogo Nova Conexão</span><span class="sxs-lookup"><span data-stu-id="7b2fe-131">New Connection Dialog Box</span></span>  
 <span data-ttu-id="7b2fe-132">**Nome da conexão**</span><span class="sxs-lookup"><span data-stu-id="7b2fe-132">**Connection name**</span></span>  
 <span data-ttu-id="7b2fe-133">Digite um nome para a nova conexão.</span><span class="sxs-lookup"><span data-stu-id="7b2fe-133">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="7b2fe-134">**Selecione ou digite um nome de servidor**</span><span class="sxs-lookup"><span data-stu-id="7b2fe-134">**Select or enter a server name**</span></span>  
 <span data-ttu-id="7b2fe-135">Selecione um servidor com o qual se conectar ao executar esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="7b2fe-135">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="7b2fe-136">**Atualizar**</span><span class="sxs-lookup"><span data-stu-id="7b2fe-136">**Refresh**</span></span>  
 <span data-ttu-id="7b2fe-137">Atualize a lista de servidores disponíveis.</span><span class="sxs-lookup"><span data-stu-id="7b2fe-137">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="7b2fe-138">**Digite as informações para fazer logon no servidor**</span><span class="sxs-lookup"><span data-stu-id="7b2fe-138">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="7b2fe-139">Especifica como autenticar no servidor.</span><span class="sxs-lookup"><span data-stu-id="7b2fe-139">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="7b2fe-140">**Use a segurança integrada do Windows**</span><span class="sxs-lookup"><span data-stu-id="7b2fe-140">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="7b2fe-141">Conecte-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] com a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="7b2fe-141">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with Windows Authentication.</span></span>  
  
 <span data-ttu-id="7b2fe-142">**Usar nome de usuário e senha específicos**</span><span class="sxs-lookup"><span data-stu-id="7b2fe-142">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="7b2fe-143">Conecte-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b2fe-143">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="7b2fe-144">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="7b2fe-144">This option is not available.</span></span>  
  
 <span data-ttu-id="7b2fe-145">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="7b2fe-145">**User name**</span></span>  
 <span data-ttu-id="7b2fe-146">Forneça um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a ser usado na autenticação.</span><span class="sxs-lookup"><span data-stu-id="7b2fe-146">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="7b2fe-147">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="7b2fe-147">This option is not available.</span></span>  
  
 <span data-ttu-id="7b2fe-148">**Senha**</span><span class="sxs-lookup"><span data-stu-id="7b2fe-148">**Password**</span></span>  
 <span data-ttu-id="7b2fe-149">Forneça uma senha a ser usada na autenticação.</span><span class="sxs-lookup"><span data-stu-id="7b2fe-149">Provide a password to use when authenticating.</span></span> <span data-ttu-id="7b2fe-150">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="7b2fe-150">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b2fe-151">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7b2fe-151">See Also</span></span>  
 [<span data-ttu-id="7b2fe-152">DBCC CHECKDB &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7b2fe-152">DBCC CHECKDB &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)  
  
  
