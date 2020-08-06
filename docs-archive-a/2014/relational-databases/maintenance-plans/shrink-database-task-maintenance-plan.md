---
title: Reduzir a tarefa do banco de dados (plano de manutenção) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.shrink.f1
- Shrink Database Task
- Shrink Database(s) Task
helpviewer_keywords:
- Shrink Database Task dialog box
ms.assetid: a9874cac-cded-4145-9c38-8aafd267dbee
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b8ee6060a4ee6ca3272434cf3d9115638a675e62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680398"
---
# <a name="shrink-database-task-maintenance-plan"></a><span data-ttu-id="68aac-102">Tarefa reduzir banco de dados (Plano de Manutenção)</span><span class="sxs-lookup"><span data-stu-id="68aac-102">Shrink Database Task (Maintenance Plan)</span></span>
  <span data-ttu-id="68aac-103">Use a caixa de diálogo da **Tarefa Reduzir Banco de Dados** para criar uma tarefa que tenta reduzir o tamanho dos bancos de dados selecionados.</span><span class="sxs-lookup"><span data-stu-id="68aac-103">Use the **Shrink Database Task** dialog to create a task that attempts to reduce the size of the selected databases.</span></span> <span data-ttu-id="68aac-104">Use as opções abaixo para determinar a quantidade de espaço não usado que permanecerá no banco de dados depois de ele ser reduzido (quanto maior a porcentagem, menos o banco de dados poderá ser reduzido).</span><span class="sxs-lookup"><span data-stu-id="68aac-104">Use the options below to determine the amount of unused space to remain in the database after the database is shrunk (the larger the percentage, the less the database can shrink).</span></span> <span data-ttu-id="68aac-105">O valor é baseado na porcentagem dos dados reais no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="68aac-105">The value is based on the percentage of the actual data in the database.</span></span> <span data-ttu-id="68aac-106">Por exemplo, se você reduzir um banco de dados de 100 MB contendo 60 MB de dados e 40 MB de espaço livre, com uma porcentagem de espaço livre de 50%, você ficará com 60 MB de dados e 30 MB de espaço livre (pois 50% de 60 MB são 30 MB).</span><span class="sxs-lookup"><span data-stu-id="68aac-106">For example, a 100-MB database containing 60 MB of data and 40 MB of free space, with a free space percentage of 50 percent, would result in 60 MB of data and 30 MB of free space (because 50 percent of 60 MB is 30 MB).</span></span> <span data-ttu-id="68aac-107">Somente o espaço em excesso no banco de dados é eliminado.</span><span class="sxs-lookup"><span data-stu-id="68aac-107">Only excess space in the database is eliminated.</span></span> <span data-ttu-id="68aac-108">Os valores válidos são de 0 a 100.</span><span class="sxs-lookup"><span data-stu-id="68aac-108">Valid values are from 0 through 100.</span></span>  
  
 <span data-ttu-id="68aac-109">A redução de arquivos de dados recupera espaço com a movimentação de páginas de dados do final do arquivo para o espaço desocupado mais próximo à frente do arquivo.</span><span class="sxs-lookup"><span data-stu-id="68aac-109">Shrinking data files recovers space by moving pages of data from the end of the file to unoccupied space closer to the front of the file.</span></span> <span data-ttu-id="68aac-110">Quando espaço livre suficiente é criado no final do arquivo, as páginas de dados no final do arquivo podem ser desalocadas e retornadas para o sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="68aac-110">When enough free space is created at the end of the file, data pages at end of the file can deallocated and returned to the file system.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="68aac-111">Os dados movidos para reduzir um arquivo podem ser espalhados para qualquer local disponível no arquivo.</span><span class="sxs-lookup"><span data-stu-id="68aac-111">Data that is moved to shrink a file can be scattered to any available location in the file.</span></span> <span data-ttu-id="68aac-112">Isso provoca uma fragmentação do índice e pode reduzir a velocidade do desempenho de consultas que pesquisam um intervalo do índice.</span><span class="sxs-lookup"><span data-stu-id="68aac-112">This causes index fragmentation and can slow the performance of queries that search a range of the index.</span></span> <span data-ttu-id="68aac-113">Para eliminar a fragmentação, considere a recompilação dos índices no arquivo após a redução.</span><span class="sxs-lookup"><span data-stu-id="68aac-113">To eliminate the fragmentation, consider rebuilding the indexes on the file after shrinking.</span></span>  
  
 <span data-ttu-id="68aac-114">Essa tarefa executa a instrução DBCC SHRINKDATABASE.</span><span class="sxs-lookup"><span data-stu-id="68aac-114">This task executes the DBCC SHRINKDATABASE statement.</span></span>  
  
## <a name="options"></a><span data-ttu-id="68aac-115">Opções</span><span class="sxs-lookup"><span data-stu-id="68aac-115">Options</span></span>  
 <span data-ttu-id="68aac-116">**Conexão**</span><span class="sxs-lookup"><span data-stu-id="68aac-116">**Connection**</span></span>  
 <span data-ttu-id="68aac-117">Selecione a conexão de servidor a ser usada na execução desta tarefa.</span><span class="sxs-lookup"><span data-stu-id="68aac-117">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="68aac-118">**Novo**</span><span class="sxs-lookup"><span data-stu-id="68aac-118">**New**</span></span>  
 <span data-ttu-id="68aac-119">Crie uma nova conexão com o servidor para usar ao executar esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="68aac-119">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="68aac-120">A caixa de diálogo **Nova Conexão** é descrita abaixo.</span><span class="sxs-lookup"><span data-stu-id="68aac-120">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="68aac-121">**Bancos de dados**</span><span class="sxs-lookup"><span data-stu-id="68aac-121">**Databases**</span></span>  
 <span data-ttu-id="68aac-122">Especifique os bancos de dados afetados por essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="68aac-122">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="68aac-123">**Todos os bancos de dados**</span><span class="sxs-lookup"><span data-stu-id="68aac-123">**All databases**</span></span>  
  
     <span data-ttu-id="68aac-124">Gere um plano de manutenção que executa tarefas de manutenção em todos os bancos de dados do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], exceto tempdb.</span><span class="sxs-lookup"><span data-stu-id="68aac-124">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases except tempdb.</span></span>  
  
-   <span data-ttu-id="68aac-125">**Todos os bancos de dados do sistema**</span><span class="sxs-lookup"><span data-stu-id="68aac-125">**All system databases**</span></span>  
  
     <span data-ttu-id="68aac-126">Gera um plano de manutenção que execute tarefas de manutenção em cada banco de dados do sistema do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , exceto o tempdb.</span><span class="sxs-lookup"><span data-stu-id="68aac-126">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except tempdb.</span></span> <span data-ttu-id="68aac-127">Nenhuma tarefa de manutenção é executada nos bancos de dados criados pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="68aac-127">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="68aac-128">**Todos os bancos de dados de usuários**</span><span class="sxs-lookup"><span data-stu-id="68aac-128">**All user databases**</span></span>  
  
     <span data-ttu-id="68aac-129">Gere um plano de manutenção que execute tarefas de manutenção em todos os bancos de dados criados por usuários.</span><span class="sxs-lookup"><span data-stu-id="68aac-129">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="68aac-130">Nenhuma tarefa de manutenção é executada com os bancos de dados do sistema do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="68aac-130">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="68aac-131">**Estes bancos de dados**</span><span class="sxs-lookup"><span data-stu-id="68aac-131">**These databases**</span></span>  
  
     <span data-ttu-id="68aac-132">Gere um plano de manutenção que execute tarefas de manutenção somente nos bancos de dados selecionados.</span><span class="sxs-lookup"><span data-stu-id="68aac-132">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="68aac-133">Pelo menos um banco de dados da lista deverá ser selecionado se esta opção for escolhida.</span><span class="sxs-lookup"><span data-stu-id="68aac-133">At least one database in the list must be selected if this option is chosen.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="68aac-134">Os planos de manutenção são executados somente em bancos de dados definidos com nível de compatibilidade 80 ou superior.</span><span class="sxs-lookup"><span data-stu-id="68aac-134">Maintenance plans only run against databases set to compatibility level 80 or higher.</span></span> <span data-ttu-id="68aac-135">Os bancos de dados definidos para o nível de compatibilidade 70 ou inferior não são exibidos.</span><span class="sxs-lookup"><span data-stu-id="68aac-135">Databases set to compatibility level 70 or lower are not displayed.</span></span>  
  
 <span data-ttu-id="68aac-136">**Reduzir o banco de dados quando ele ultrapassar**</span><span class="sxs-lookup"><span data-stu-id="68aac-136">**Shrink database when it grows beyond**</span></span>  
 <span data-ttu-id="68aac-137">Especifique o tamanho em megabytes que faz a tarefa ser executada.</span><span class="sxs-lookup"><span data-stu-id="68aac-137">Specify the size in megabytes that causes the task to execute.</span></span>  
  
 <span data-ttu-id="68aac-138">**Espaço livre após a redução**</span><span class="sxs-lookup"><span data-stu-id="68aac-138">**Amount of free space to remain after shrink**</span></span>  
 <span data-ttu-id="68aac-139">Deixe de reduzir quando o espaço livre nos arquivos de banco de dados alcançar esse tamanho.</span><span class="sxs-lookup"><span data-stu-id="68aac-139">Stop shrinking when free space in database files reaches this size.</span></span>  
  
 <span data-ttu-id="68aac-140">**Exibir T-SQL**</span><span class="sxs-lookup"><span data-stu-id="68aac-140">**View T-SQL**</span></span>  
 <span data-ttu-id="68aac-141">Exiba as instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] executadas no servidor para esta tarefa, com base nas opções selecionadas.</span><span class="sxs-lookup"><span data-stu-id="68aac-141">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="68aac-142">Quando o número de objetos afetados é grande, essa exibição pode ser demorada.</span><span class="sxs-lookup"><span data-stu-id="68aac-142">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="68aac-143">Caixa de diálogo Nova Conexão</span><span class="sxs-lookup"><span data-stu-id="68aac-143">New Connection Dialog Box</span></span>  
 <span data-ttu-id="68aac-144">**Nome da conexão**</span><span class="sxs-lookup"><span data-stu-id="68aac-144">**Connection name**</span></span>  
 <span data-ttu-id="68aac-145">Digite um nome para a nova conexão.</span><span class="sxs-lookup"><span data-stu-id="68aac-145">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="68aac-146">**Selecione ou digite um nome de servidor**</span><span class="sxs-lookup"><span data-stu-id="68aac-146">**Select or enter a server name**</span></span>  
 <span data-ttu-id="68aac-147">Selecione um servidor com o qual se conectar ao executar esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="68aac-147">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="68aac-148">**Atualizar**</span><span class="sxs-lookup"><span data-stu-id="68aac-148">**Refresh**</span></span>  
 <span data-ttu-id="68aac-149">Atualize a lista de servidores disponíveis.</span><span class="sxs-lookup"><span data-stu-id="68aac-149">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="68aac-150">**Digite as informações para fazer logon no servidor**</span><span class="sxs-lookup"><span data-stu-id="68aac-150">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="68aac-151">Especifica como autenticar no servidor.</span><span class="sxs-lookup"><span data-stu-id="68aac-151">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="68aac-152">**Usar segurança Integrada do Windows NT**</span><span class="sxs-lookup"><span data-stu-id="68aac-152">**Use Windows NT Integrated security**</span></span>  
 <span data-ttu-id="68aac-153">Conecte-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] com a Autenticação do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="68aac-153">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="68aac-154">**Usar nome de usuário e senha específicos**</span><span class="sxs-lookup"><span data-stu-id="68aac-154">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="68aac-155">Conecte-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="68aac-155">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="68aac-156">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="68aac-156">This option is not available.</span></span>  
  
 <span data-ttu-id="68aac-157">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="68aac-157">**User name**</span></span>  
 <span data-ttu-id="68aac-158">Forneça um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a ser usado na autenticação.</span><span class="sxs-lookup"><span data-stu-id="68aac-158">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="68aac-159">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="68aac-159">This option is not available.</span></span>  
  
 <span data-ttu-id="68aac-160">**Senha**</span><span class="sxs-lookup"><span data-stu-id="68aac-160">**Password**</span></span>  
 <span data-ttu-id="68aac-161">Forneça uma senha a ser usada na autenticação.</span><span class="sxs-lookup"><span data-stu-id="68aac-161">Provide a password to use when authenticating.</span></span> <span data-ttu-id="68aac-162">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="68aac-162">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68aac-163">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="68aac-163">See Also</span></span>  
 [<span data-ttu-id="68aac-164">DBCC SHRINKDATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="68aac-164">DBCC SHRINKDATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql)  
  
  
