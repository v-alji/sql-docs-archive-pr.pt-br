---
title: Tarefa Recompilar Índice (plano de manutenção) | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.reindex.f1
- reindex
helpviewer_keywords:
- Rebuild Index Task dialog box
ms.assetid: 33e2940b-139f-4563-b0cb-5683f08bd879
author: rothja
ms.author: jroth
ms.openlocfilehash: bc9d7c85a72c34cee1ef7af8cb4b4f25f918a3fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572522"
---
# <a name="rebuild-index-task-maintenance-plan"></a><span data-ttu-id="e9fbb-102">Tarefa Recriar Índice (Plano de Manutenção)</span><span class="sxs-lookup"><span data-stu-id="e9fbb-102">Rebuild Index Task (Maintenance Plan)</span></span>
  <span data-ttu-id="e9fbb-103">Use a caixa de diálogo **Tarefa Recompilar Índice** para recriar os índices nas tabelas do banco de dados com um novo fator de preenchimento.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-103">Use the **Rebuild Index Task** dialog to re-create the indexes on the tables in the database with a new fill factor.</span></span> <span data-ttu-id="e9fbb-104">O fator de preenchimento determina a quantidade de espaço vazio em cada página no índice, para acomodar futuras expansões.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-104">The fill factor determines the amount of empty space on each page in the index, to accommodate future expansion.</span></span> <span data-ttu-id="e9fbb-105">À medida que os dados são adicionados à tabela, o espaço livre é todo preenchido porque o fator de preenchimento não é mantido.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-105">As data is added to the table, the free space fills because the fill factor is not maintained.</span></span> <span data-ttu-id="e9fbb-106">Reorganizando dados e páginas de índice, é possível restabelecer o espaço livre.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-106">Reorganizing data and index pages can re-establish the free space.</span></span>  
  
 <span data-ttu-id="e9fbb-107">A **Tarefa Recompilar Índice** usa a instrução ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-107">The **Rebuild Index Task** uses the ALTER INDEX statement.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e9fbb-108">Opções</span><span class="sxs-lookup"><span data-stu-id="e9fbb-108">Options</span></span>  
 <span data-ttu-id="e9fbb-109">**Conexão**</span><span class="sxs-lookup"><span data-stu-id="e9fbb-109">**Connection**</span></span>  
 <span data-ttu-id="e9fbb-110">Selecione a conexão de servidor a ser usada na execução desta tarefa.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-110">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="e9fbb-111">**Novo**</span><span class="sxs-lookup"><span data-stu-id="e9fbb-111">**New**</span></span>  
 <span data-ttu-id="e9fbb-112">Crie uma nova conexão com o servidor para usar ao executar esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-112">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="e9fbb-113">A caixa de diálogo **Nova Conexão** é descrita abaixo.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-113">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="e9fbb-114">**Bancos de dados**</span><span class="sxs-lookup"><span data-stu-id="e9fbb-114">**Databases**</span></span>  
 <span data-ttu-id="e9fbb-115">Especifique os bancos de dados afetados por essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-115">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="e9fbb-116">**Todos os bancos de dados**</span><span class="sxs-lookup"><span data-stu-id="e9fbb-116">**All databases**</span></span>  
  
     <span data-ttu-id="e9fbb-117">Gere um plano de manutenção que executa tarefas de manutenção em todos os bancos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , exceto o tempdb.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-117">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases except tempdb.</span></span>  
  
-   <span data-ttu-id="e9fbb-118">**Todos os bancos de dados do sistema**</span><span class="sxs-lookup"><span data-stu-id="e9fbb-118">**All system databases**</span></span>  
  
     <span data-ttu-id="e9fbb-119">Gera um plano de manutenção que execute tarefas de manutenção em cada banco de dados do sistema do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , exceto o tempdb.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-119">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except tempdb.</span></span> <span data-ttu-id="e9fbb-120">Nenhuma tarefa de manutenção é executada nos bancos de dados criados pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-120">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="e9fbb-121">**Todos os bancos de dados de usuários**</span><span class="sxs-lookup"><span data-stu-id="e9fbb-121">**All user databases**</span></span>  
  
     <span data-ttu-id="e9fbb-122">Gere um plano de manutenção que execute tarefas de manutenção em todos os bancos de dados criados por usuários.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-122">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="e9fbb-123">Nenhuma tarefa de manutenção é executada com os bancos de dados do sistema do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9fbb-123">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="e9fbb-124">**Estes bancos de dados específicos**</span><span class="sxs-lookup"><span data-stu-id="e9fbb-124">**These specific databases**</span></span>  
  
     <span data-ttu-id="e9fbb-125">Gere um plano de manutenção que execute tarefas de manutenção somente nos bancos de dados selecionados.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-125">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="e9fbb-126">Pelo menos um banco de dados da lista deverá ser selecionado se esta opção for escolhida.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-126">At least one database in the list must be selected if this option is chosen.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e9fbb-127">Os planos de manutenção são executados somente em bancos de dados definidos com nível de compatibilidade 80 ou superior.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-127">Maintenance plans only run against databases set to compatibility level 80 or higher.</span></span> <span data-ttu-id="e9fbb-128">Os bancos de dados definidos para o nível de compatibilidade 70 ou inferior não são exibidos.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-128">Databases set to compatibility level 70 or lower are not displayed.</span></span>  
  
 <span data-ttu-id="e9fbb-129">**Objeto**</span><span class="sxs-lookup"><span data-stu-id="e9fbb-129">**Object**</span></span>  
 <span data-ttu-id="e9fbb-130">Limita a grade **Seleção** para exibir tabelas, exibições ou ambas.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-130">Limit the **Selection** grid to display tables, views, or both.</span></span>  
  
 <span data-ttu-id="e9fbb-131">**Seleção**</span><span class="sxs-lookup"><span data-stu-id="e9fbb-131">**Selection**</span></span>  
 <span data-ttu-id="e9fbb-132">Especifique as tabelas ou índices afetados por esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-132">Specify the tables or indexes affected by this task.</span></span> <span data-ttu-id="e9fbb-133">Não disponível quando **Tabelas e Exibições** estiver selecionado na caixa Objeto.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-133">Not available when **Tables and Views** is selected in the Object box.</span></span>  
  
 <span data-ttu-id="e9fbb-134">**Reorganiza páginas com a quantidade padrão de espaço livre**</span><span class="sxs-lookup"><span data-stu-id="e9fbb-134">**Reorganize pages with the default amount of free space**</span></span>  
 <span data-ttu-id="e9fbb-135">Descarta os índices nas tabelas no banco de dados e recria-os com o fator de preenchimento especificado quando os índices foram criados.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-135">Drop the indexes on the tables in the database and re-create them with the fill factor that was specified when the indexes were created.</span></span>  
  
 <span data-ttu-id="e9fbb-136">**Alterar o espaço livre por porcentagem de página para**</span><span class="sxs-lookup"><span data-stu-id="e9fbb-136">**Change free space per page percentage to**</span></span>  
 <span data-ttu-id="e9fbb-137">Descarta os índices nas tabelas no banco de dados e recria-os com um fator de preenchimento novo, calculado automaticamente, reservando a quantidade especificada de espaço livre nas páginas de índice.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-137">Drop the indexes on the tables in the database and re-create them with a new, automatically calculated fill factor, thereby reserving the specified amount of free space on the index pages.</span></span> <span data-ttu-id="e9fbb-138">Quanto maior a porcentagem, mais espaço livre será reservado nas páginas de índice e maior ficará o índice.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-138">The higher the percentage, the more free space is reserved on the index pages, and the larger the index grows.</span></span> <span data-ttu-id="e9fbb-139">Os valores válidos são de 0 a 100.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-139">Valid values are from 0 through 100.</span></span>  
  
 <span data-ttu-id="e9fbb-140">**Classificar resultados no tempdb**</span><span class="sxs-lookup"><span data-stu-id="e9fbb-140">**Sort results in tempdb**</span></span>  
 <span data-ttu-id="e9fbb-141">Use a `SORT_IN_TEMPDB` opção, que determina onde os resultados intermediários de classificação, gerados durante a criação do índice, são armazenados temporariamente.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-141">Use the `SORT_IN_TEMPDB`option, which determines where the intermediate sort results, generated during index creation, are temporarily stored.</span></span> <span data-ttu-id="e9fbb-142">Se uma operação de classificação não for necessária ou se a classificação puder ser executada na memória, a opção `SORT_IN_TEMPDB`será ignorada.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-142">If a sort operation is not required, or if the sort can be performed in memory, the `SORT_IN_TEMPDB`option is ignored.</span></span>  
  
 <span data-ttu-id="e9fbb-143">**Mantenha o índice online enquanto reindexa**</span><span class="sxs-lookup"><span data-stu-id="e9fbb-143">**Keep index online while reindexing**</span></span>  
 <span data-ttu-id="e9fbb-144">Use a opção `ONLINE` , que permite o acesso de usuários aos dados da tabela subjacente ou de índice clusterizado e qualquer índice não clusterizado associado durante as operações de índice.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-144">Use the `ONLINE` option which allows users to access the underlying table or clustered index data and any associated nonclustered indexes during index operations.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e9fbb-145">As operações de índice online não estão disponíveis em todas as edições de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9fbb-145">Online index operations are not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e9fbb-146">Para obter uma lista de recursos com suporte nas edições do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consulte [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="e9fbb-146">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="e9fbb-147">**Exibir T-SQL**</span><span class="sxs-lookup"><span data-stu-id="e9fbb-147">**View T-SQL**</span></span>  
 <span data-ttu-id="e9fbb-148">Exiba as instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] executadas no servidor para esta tarefa, com base nas opções selecionadas.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-148">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e9fbb-149">Quando o número de objetos afetados é grande, essa exibição pode ser demorada.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-149">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="e9fbb-150">Caixa de diálogo Nova Conexão</span><span class="sxs-lookup"><span data-stu-id="e9fbb-150">New Connection Dialog Box</span></span>  
 <span data-ttu-id="e9fbb-151">**Nome da conexão**</span><span class="sxs-lookup"><span data-stu-id="e9fbb-151">**Connection name**</span></span>  
 <span data-ttu-id="e9fbb-152">Digite um nome para a nova conexão.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-152">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="e9fbb-153">**Selecione ou digite um nome de servidor**</span><span class="sxs-lookup"><span data-stu-id="e9fbb-153">**Select or enter a server name**</span></span>  
 <span data-ttu-id="e9fbb-154">Selecione um servidor com o qual se conectar ao executar esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-154">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="e9fbb-155">**Atualizar**</span><span class="sxs-lookup"><span data-stu-id="e9fbb-155">**Refresh**</span></span>  
 <span data-ttu-id="e9fbb-156">Atualize a lista de servidores disponíveis.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-156">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="e9fbb-157">**Digite as informações para fazer logon no servidor**</span><span class="sxs-lookup"><span data-stu-id="e9fbb-157">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="e9fbb-158">Especifica como autenticar no servidor.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-158">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="e9fbb-159">**Use a segurança integrada do Windows**</span><span class="sxs-lookup"><span data-stu-id="e9fbb-159">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="e9fbb-160">Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] com a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-160">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with Windows Authentication.</span></span>  
  
 <span data-ttu-id="e9fbb-161">**Usar nome de usuário e senha específicos**</span><span class="sxs-lookup"><span data-stu-id="e9fbb-161">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="e9fbb-162">Conecte-se com uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9fbb-162">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="e9fbb-163">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-163">This option is not available.</span></span>  
  
 <span data-ttu-id="e9fbb-164">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="e9fbb-164">**User name**</span></span>  
 <span data-ttu-id="e9fbb-165">Forneça um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a ser usado na autenticação.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-165">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="e9fbb-166">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-166">This option is not available.</span></span>  
  
 <span data-ttu-id="e9fbb-167">**Senha**</span><span class="sxs-lookup"><span data-stu-id="e9fbb-167">**Password**</span></span>  
 <span data-ttu-id="e9fbb-168">Forneça uma senha a ser usada na autenticação.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-168">Provide a password to use when authenticating.</span></span> <span data-ttu-id="e9fbb-169">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="e9fbb-169">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9fbb-170">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e9fbb-170">See Also</span></span>  
 <span data-ttu-id="e9fbb-171">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e9fbb-171">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="e9fbb-172">[DBCC DBREINDEX &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e9fbb-172">[DBCC DBREINDEX &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql) </span></span>  
 <span data-ttu-id="e9fbb-173">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e9fbb-173">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 <span data-ttu-id="e9fbb-174">[Opção SORT_IN_TEMPDB para índices](../indexes/indexes.md) </span><span class="sxs-lookup"><span data-stu-id="e9fbb-174">[SORT_IN_TEMPDB Option For Indexes](../indexes/indexes.md) </span></span>  
 <span data-ttu-id="e9fbb-175">[Diretrizes para operações de índice online](../indexes/guidelines-for-online-index-operations.md) </span><span class="sxs-lookup"><span data-stu-id="e9fbb-175">[Guidelines for Online Index Operations](../indexes/guidelines-for-online-index-operations.md) </span></span>  
 <span data-ttu-id="e9fbb-176">[Como funcionam as operações de índice online](../indexes/how-online-index-operations-work.md) </span><span class="sxs-lookup"><span data-stu-id="e9fbb-176">[How Online Index Operations Work](../indexes/how-online-index-operations-work.md) </span></span>  
 [<span data-ttu-id="e9fbb-177">Executar operações de índice online</span><span class="sxs-lookup"><span data-stu-id="e9fbb-177">Perform Index Operations Online</span></span>](../indexes/perform-index-operations-online.md)  
  
  
