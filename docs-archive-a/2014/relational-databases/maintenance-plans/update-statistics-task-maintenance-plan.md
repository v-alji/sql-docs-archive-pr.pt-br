---
title: Tarefa Atualização de Estatísticas (Plano de manutenção) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.statistics.f1
helpviewer_keywords:
- Updates Statistics Task dialog box
ms.assetid: 22902fd0-eb39-4f18-af94-3fcb69d2a3a4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 486ef2da96785ed200900f497435117ef6437cb5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583581"
---
# <a name="update-statistics-task-maintenance-plan"></a><span data-ttu-id="9a695-102">Tarefa Atualização de Estatísticas (Plano de manutenção)</span><span class="sxs-lookup"><span data-stu-id="9a695-102">Update Statistics Task (Maintenance Plan)</span></span>
  <span data-ttu-id="9a695-103">Use a caixa de diálogo **Tarefa Atualizar Estatísticas** para atualizar informações do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sobre os dados nas tabelas e nos índices.</span><span class="sxs-lookup"><span data-stu-id="9a695-103">Use the **Update Statistics Task** dialog to update [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] information about the data in the tables and indexes.</span></span> <span data-ttu-id="9a695-104">Essa tarefa cria uma nova amostra das estatísticas de distribuição de cada índice criado em tabelas de usuário no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9a695-104">This task resamples the distribution statistics of each index created on user tables in the database.</span></span> <span data-ttu-id="9a695-105">As estatísticas de distribuição são usadas pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para otimizar a navegação em tabelas durante o processamento de instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a695-105">The distribution statistics are used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to optimize navigation through tables during the processing of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="9a695-106">Para construir as estatísticas de distribuição automaticamente, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] faz uma amostra periódica dos dados na tabela correspondente para cada índice.</span><span class="sxs-lookup"><span data-stu-id="9a695-106">To build the distribution statistics automatically, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] periodically samples the data in the corresponding table for each index.</span></span> <span data-ttu-id="9a695-107">O tamanho da amostra tem como base o número de linhas na tabela e a frequência de modificação dos dados.</span><span class="sxs-lookup"><span data-stu-id="9a695-107">This size of the sample is based on the number of rows in the table and the frequency of data modification.</span></span> <span data-ttu-id="9a695-108">Use essa opção para executar uma amostragem adicional usando a porcentagem de dados especificada nas tabelas.</span><span class="sxs-lookup"><span data-stu-id="9a695-108">Use this option to perform an additional sampling using the specified percentage of data in the tables.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9a695-109">usa estas informações para criar planos de consulta melhores.</span><span class="sxs-lookup"><span data-stu-id="9a695-109">uses this information to create better query plans.</span></span>  
  
 <span data-ttu-id="9a695-110">Essa tarefa executa a instrução UPDATE STATISTICS.</span><span class="sxs-lookup"><span data-stu-id="9a695-110">This task executes the UPDATE STATISTICS statement.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9a695-111">Opções</span><span class="sxs-lookup"><span data-stu-id="9a695-111">Options</span></span>  
 <span data-ttu-id="9a695-112">**Conexão**</span><span class="sxs-lookup"><span data-stu-id="9a695-112">**Connection**</span></span>  
 <span data-ttu-id="9a695-113">Selecione a conexão de servidor a ser usada na execução desta tarefa.</span><span class="sxs-lookup"><span data-stu-id="9a695-113">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="9a695-114">**Novo**</span><span class="sxs-lookup"><span data-stu-id="9a695-114">**New**</span></span>  
 <span data-ttu-id="9a695-115">Crie uma nova conexão com o servidor para usar ao executar esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="9a695-115">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="9a695-116">A caixa de diálogo **Nova Conexão** é descrita abaixo.</span><span class="sxs-lookup"><span data-stu-id="9a695-116">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="9a695-117">**Bancos de dados**</span><span class="sxs-lookup"><span data-stu-id="9a695-117">**Databases**</span></span>  
 <span data-ttu-id="9a695-118">Especifique os bancos de dados afetados por essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="9a695-118">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="9a695-119">**Todos os bancos de dados**</span><span class="sxs-lookup"><span data-stu-id="9a695-119">**All databases**</span></span>  
  
     <span data-ttu-id="9a695-120">Gere um plano de manutenção que execute tarefas de manutenção em todos os bancos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , exceto tempdb.</span><span class="sxs-lookup"><span data-stu-id="9a695-120">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases, except tempdb.</span></span>  
  
-   <span data-ttu-id="9a695-121">**Todos os bancos de dados do sistema**</span><span class="sxs-lookup"><span data-stu-id="9a695-121">**All system databases**</span></span>  
  
     <span data-ttu-id="9a695-122">Gera um plano de manutenção que execute tarefas de manutenção em cada banco de dados do sistema do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , exceto o tempdb.</span><span class="sxs-lookup"><span data-stu-id="9a695-122">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except tempdb.</span></span> <span data-ttu-id="9a695-123">Nenhuma tarefa de manutenção é executada nos bancos de dados criados pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="9a695-123">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="9a695-124">**Todos os bancos de dados de usuários**</span><span class="sxs-lookup"><span data-stu-id="9a695-124">**All user databases**</span></span>  
  
     <span data-ttu-id="9a695-125">Gere um plano de manutenção que execute tarefas de manutenção em todos os bancos de dados criados por usuários.</span><span class="sxs-lookup"><span data-stu-id="9a695-125">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="9a695-126">Nenhuma tarefa de manutenção é executada com os bancos de dados do sistema do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a695-126">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="9a695-127">**Estes bancos de dados específicos**</span><span class="sxs-lookup"><span data-stu-id="9a695-127">**These specific databases**</span></span>  
  
     <span data-ttu-id="9a695-128">Gere um plano de manutenção que execute tarefas de manutenção somente nos bancos de dados selecionados.</span><span class="sxs-lookup"><span data-stu-id="9a695-128">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="9a695-129">Pelo menos um banco de dados da lista deverá ser selecionado se esta opção for escolhida.</span><span class="sxs-lookup"><span data-stu-id="9a695-129">At least one database in the list must be selected if this option is chosen.</span></span>  
  
 <span data-ttu-id="9a695-130">**Observação** Planos de manutenção são executados somente em bancos de dados definidos com nível de compatibilidade 80 ou superior.</span><span class="sxs-lookup"><span data-stu-id="9a695-130">**Note** Maintenance plans only run against databases set to compatibility level 80 or higher.</span></span> <span data-ttu-id="9a695-131">Os bancos de dados definidos para o nível de compatibilidade 70 ou inferior não são exibidos.</span><span class="sxs-lookup"><span data-stu-id="9a695-131">Databases set to compatibility level 70 or lower are not displayed.</span></span>  
  
 <span data-ttu-id="9a695-132">**Objeto**</span><span class="sxs-lookup"><span data-stu-id="9a695-132">**Object**</span></span>  
 <span data-ttu-id="9a695-133">Limita a grade **Seleção** para exibir tabelas, exibições ou ambas.</span><span class="sxs-lookup"><span data-stu-id="9a695-133">Limit the **Selection** grid to display tables, views, or both.</span></span>  
  
 <span data-ttu-id="9a695-134">**Seleção**</span><span class="sxs-lookup"><span data-stu-id="9a695-134">**Selection**</span></span>  
 <span data-ttu-id="9a695-135">Especifique as tabelas ou índices afetados por esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="9a695-135">Specify the tables or indexes affected by this task.</span></span> <span data-ttu-id="9a695-136">Não disponível quando **Tabelas e Exibições** estiver selecionado na caixa Objeto.</span><span class="sxs-lookup"><span data-stu-id="9a695-136">Not available when **Tables and Views** is selected in the Object box.</span></span>  
  
 <span data-ttu-id="9a695-137">**Todas as estatísticas existentes**</span><span class="sxs-lookup"><span data-stu-id="9a695-137">**All existing statistics**</span></span>  
 <span data-ttu-id="9a695-138">Atualize as estatísticas de colunas e índices.</span><span class="sxs-lookup"><span data-stu-id="9a695-138">Update statistics for both columns and indexes.</span></span>  
  
 <span data-ttu-id="9a695-139">**Somente estatísticas de coluna**</span><span class="sxs-lookup"><span data-stu-id="9a695-139">**Column statistics only**</span></span>  
 <span data-ttu-id="9a695-140">Atualiza apenas as estatísticas de coluna.</span><span class="sxs-lookup"><span data-stu-id="9a695-140">Only update column statistics.</span></span>  
  
 <span data-ttu-id="9a695-141">**Somente estatísticas do índice**</span><span class="sxs-lookup"><span data-stu-id="9a695-141">**Index statistics only**</span></span>  
 <span data-ttu-id="9a695-142">Só atualiza estatísticas do índice.</span><span class="sxs-lookup"><span data-stu-id="9a695-142">Only update index statistics.</span></span>  
  
 <span data-ttu-id="9a695-143">**Tipo de exame**</span><span class="sxs-lookup"><span data-stu-id="9a695-143">**Scan type**</span></span>  
 <span data-ttu-id="9a695-144">Tipo de exame usado para coletar estatísticas atualizadas.</span><span class="sxs-lookup"><span data-stu-id="9a695-144">Type of scan used to gather updated statistics.</span></span>  
  
 <span data-ttu-id="9a695-145">**Exame completo**</span><span class="sxs-lookup"><span data-stu-id="9a695-145">**Full scan**</span></span>  
 <span data-ttu-id="9a695-146">Lê todas as linhas na tabela ou exibição para coletar as estatísticas.</span><span class="sxs-lookup"><span data-stu-id="9a695-146">Read all rows in the table or view to gather the statistics.</span></span>  
  
 <span data-ttu-id="9a695-147">**Amostra por**</span><span class="sxs-lookup"><span data-stu-id="9a695-147">**Sample by**</span></span>  
 <span data-ttu-id="9a695-148">Especifique a porcentagem da tabela ou exibição indexada ou o número de linhas de amostragem ao coletar estatísticas de tabelas ou exibições maiores.</span><span class="sxs-lookup"><span data-stu-id="9a695-148">Specify the percentage of the table or indexed view, or the number of rows to sample when collecting statistics for larger tables or views.</span></span>  
  
 <span data-ttu-id="9a695-149">**Exibir T-SQL**</span><span class="sxs-lookup"><span data-stu-id="9a695-149">**View T-SQL**</span></span>  
 <span data-ttu-id="9a695-150">Exiba as instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] executadas no servidor para esta tarefa, com base nas opções selecionadas.</span><span class="sxs-lookup"><span data-stu-id="9a695-150">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9a695-151">Quando o número de objetos afetados é grande, essa exibição pode ser demorada.</span><span class="sxs-lookup"><span data-stu-id="9a695-151">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="9a695-152">Caixa de diálogo Nova Conexão</span><span class="sxs-lookup"><span data-stu-id="9a695-152">New Connection Dialog Box</span></span>  
 <span data-ttu-id="9a695-153">**Nome da conexão**</span><span class="sxs-lookup"><span data-stu-id="9a695-153">**Connection name**</span></span>  
 <span data-ttu-id="9a695-154">Digite um nome para a nova conexão.</span><span class="sxs-lookup"><span data-stu-id="9a695-154">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="9a695-155">**Selecione ou digite um nome de servidor**</span><span class="sxs-lookup"><span data-stu-id="9a695-155">**Select or enter a server name**</span></span>  
 <span data-ttu-id="9a695-156">Selecione um servidor com o qual se conectar ao executar esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="9a695-156">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="9a695-157">**Atualizar**</span><span class="sxs-lookup"><span data-stu-id="9a695-157">**Refresh**</span></span>  
 <span data-ttu-id="9a695-158">Atualize a lista de servidores disponíveis.</span><span class="sxs-lookup"><span data-stu-id="9a695-158">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="9a695-159">**Digite as informações para fazer logon no servidor**</span><span class="sxs-lookup"><span data-stu-id="9a695-159">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="9a695-160">Especifica como autenticar no servidor.</span><span class="sxs-lookup"><span data-stu-id="9a695-160">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="9a695-161">**Use a segurança integrada do Windows**</span><span class="sxs-lookup"><span data-stu-id="9a695-161">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="9a695-162">Conecte-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] com a Autenticação do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="9a695-162">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="9a695-163">**Usar nome de usuário e senha específicos**</span><span class="sxs-lookup"><span data-stu-id="9a695-163">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="9a695-164">Conecte-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a695-164">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="9a695-165">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="9a695-165">This option is not available.</span></span>  
  
 <span data-ttu-id="9a695-166">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="9a695-166">**User name**</span></span>  
 <span data-ttu-id="9a695-167">Forneça um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a ser usado na autenticação.</span><span class="sxs-lookup"><span data-stu-id="9a695-167">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="9a695-168">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="9a695-168">This option is not available.</span></span>  
  
 <span data-ttu-id="9a695-169">**Senha**</span><span class="sxs-lookup"><span data-stu-id="9a695-169">**Password**</span></span>  
 <span data-ttu-id="9a695-170">Forneça uma senha a ser usada na autenticação.</span><span class="sxs-lookup"><span data-stu-id="9a695-170">Provide a password to use when authenticating.</span></span> <span data-ttu-id="9a695-171">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="9a695-171">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a695-172">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9a695-172">See Also</span></span>  
 [<span data-ttu-id="9a695-173">UPDATE STATISTICS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a695-173">UPDATE STATISTICS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/update-statistics-transact-sql)  
  
  
