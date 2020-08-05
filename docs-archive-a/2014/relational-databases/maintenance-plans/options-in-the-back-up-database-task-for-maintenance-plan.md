---
title: Tarefa Backup de Banco de Dados (plano de manutenção) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.backup.f1
- sql12.swb.maint.maintplanproperties.logbackup.f1
helpviewer_keywords:
- Back Up Database Task dialog box
ms.assetid: ed1ef012-fa14-4ba5-bafe-d1527ba065b3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 952730f09deeede360dff5e2bd83f8cdc8a20a67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572526"
---
# <a name="back-up-database-task-maintenance-plan"></a><span data-ttu-id="629be-102">Tarefa de Backup de Banco de Dados (Plano de Manutenção)</span><span class="sxs-lookup"><span data-stu-id="629be-102">Back Up Database Task (Maintenance Plan)</span></span>
  <span data-ttu-id="629be-103">Use a caixa de diálogo **Tarefa Fazer Backup de Banco de Dados** para adicionar uma tarefa de backup ao plano de manutenção.</span><span class="sxs-lookup"><span data-stu-id="629be-103">Use the **Back Up Database Task** dialog to add a backup task to the maintenance plan.</span></span> <span data-ttu-id="629be-104">O backup do banco de dados é importante no caso de falha do sistema ou hardware (ou erros do usuário) que levem o banco de dados a ser danificado de alguma forma, exigindo assim que uma cópia de backup seja restaurada.</span><span class="sxs-lookup"><span data-stu-id="629be-104">Backing up the database is important in case of system or hardware failure (or user errors) that cause the database to be damaged in some way, thus requiring a backed-up copy to be restored.</span></span> <span data-ttu-id="629be-105">Essa tarefa lhe permite executar arquivos completos, diferenciais, e grupos de arquivos e backups de log de transações.</span><span class="sxs-lookup"><span data-stu-id="629be-105">This task allows you to perform full, differential, files and filegroups, and transaction log backups.</span></span>  
  
 <span data-ttu-id="629be-106">**Para criar uma tarefa de banco de dados de backup**</span><span class="sxs-lookup"><span data-stu-id="629be-106">**To create a backup database task**</span></span>  
  
-   [<span data-ttu-id="629be-107">Criar um Plano de Manutenção</span><span class="sxs-lookup"><span data-stu-id="629be-107">Create a Maintenance Plan</span></span>](create-a-maintenance-plan.md)  
  
## <a name="options"></a><span data-ttu-id="629be-108">Opções</span><span class="sxs-lookup"><span data-stu-id="629be-108">Options</span></span>  
 <span data-ttu-id="629be-109">**Conexão**</span><span class="sxs-lookup"><span data-stu-id="629be-109">**Connection**</span></span>  
 <span data-ttu-id="629be-110">Selecione a conexão de servidor a ser usada na execução desta tarefa.</span><span class="sxs-lookup"><span data-stu-id="629be-110">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="629be-111">**Novo**</span><span class="sxs-lookup"><span data-stu-id="629be-111">**New**</span></span>  
 <span data-ttu-id="629be-112">Crie uma nova conexão com o servidor para usar ao executar esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="629be-112">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="629be-113">A caixa de diálogo **Nova Conexão** é descrita abaixo.</span><span class="sxs-lookup"><span data-stu-id="629be-113">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="629be-114">**Bancos de dados**</span><span class="sxs-lookup"><span data-stu-id="629be-114">**Databases**</span></span>  
 <span data-ttu-id="629be-115">Especifique os bancos de dados afetados por essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="629be-115">Specify the databases affected by this task.</span></span> <span data-ttu-id="629be-116">Quando selecionada, a lista suspensa fornece as seguintes opções: **Todos os bancos de dados**, **Todos os bancos de dados do sistema**, **Todos os bancos de dados de usuário**, **Esses bancos de dados específicos**.</span><span class="sxs-lookup"><span data-stu-id="629be-116">When selected, the drop down list provides the following options: **All databases**, **All system databases**, **All user databases**, **These specific databases**.</span></span>  
  
 <span data-ttu-id="629be-117">**Todos os bancos de dados**</span><span class="sxs-lookup"><span data-stu-id="629be-117">**All databases**</span></span>  
 <span data-ttu-id="629be-118">Gere um plano de manutenção que execute tarefas de manutenção em todos os bancos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="629be-118">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span>  
  
 <span data-ttu-id="629be-119">**Todos os bancos de dados do sistema (mestre, msdb, modelo)**</span><span class="sxs-lookup"><span data-stu-id="629be-119">**All system databases (master, msdb, model)**</span></span>  
 <span data-ttu-id="629be-120">Gere um plano de manutenção que execute tarefas de manutenção em relação a cada um dos bancos de dados do sistema [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="629be-120">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span> <span data-ttu-id="629be-121">Nenhuma tarefa de manutenção é executada nos bancos de dados criados pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="629be-121">No maintenance tasks are run against user-created databases.</span></span>  
  
 <span data-ttu-id="629be-122">**Todos os bancos de dados de usuários (exceto mestre, modelo, msdb, tempdb)**</span><span class="sxs-lookup"><span data-stu-id="629be-122">**All user databases (excluding master, model, msdb, tempdb)**</span></span>  
 <span data-ttu-id="629be-123">Gere um plano de manutenção que execute tarefas de manutenção em todos os bancos de dados criados por usuários.</span><span class="sxs-lookup"><span data-stu-id="629be-123">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="629be-124">Nenhuma tarefa de manutenção é executada com os bancos de dados do sistema do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="629be-124">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
 <span data-ttu-id="629be-125">**Estes bancos de dados**</span><span class="sxs-lookup"><span data-stu-id="629be-125">**These databases**</span></span>  
 <span data-ttu-id="629be-126">Gere um plano de manutenção que execute tarefas de manutenção somente nos bancos de dados selecionados.</span><span class="sxs-lookup"><span data-stu-id="629be-126">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="629be-127">Pelo menos um banco de dados da lista deverá ser selecionado se esta opção for escolhida.</span><span class="sxs-lookup"><span data-stu-id="629be-127">At least one database in the list must be selected if this option is chosen.</span></span>  
  
 <span data-ttu-id="629be-128">**Tipo de backup**</span><span class="sxs-lookup"><span data-stu-id="629be-128">**Backup type**</span></span>  
 <span data-ttu-id="629be-129">Exibe o tipo de backup a ser executado.</span><span class="sxs-lookup"><span data-stu-id="629be-129">Shows the type of backup to be performed.</span></span>  
  
 <span data-ttu-id="629be-130">**Componente de backup**</span><span class="sxs-lookup"><span data-stu-id="629be-130">**Backup component**</span></span>  
 <span data-ttu-id="629be-131">Selecione **Banco de dados** para fazer o backup de todo o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="629be-131">Select **Database** to back up the entire database.</span></span> <span data-ttu-id="629be-132">Selecione **Arquivo e grupos de arquivos** para fazer o backup de apenas uma parte do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="629be-132">Select **File and filegroups** to back up only a portion of the database.</span></span> <span data-ttu-id="629be-133">Se selecionado, forneça o nome do arquivo ou do grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="629be-133">If selected, provide the file or filegroup name.</span></span> <span data-ttu-id="629be-134">Quando vários bancos de dados são selecionados na caixa **Bancos de dados** , especifique apenas **Bancos de dados** para **Componentes de backup**.</span><span class="sxs-lookup"><span data-stu-id="629be-134">When multiple databases are selected in the **Databases** box, only specify **Databases** for the **Backup components**.</span></span> <span data-ttu-id="629be-135">Para executar backups de arquivo ou grupo de arquivos, crie uma tarefa para cada banco de dados.</span><span class="sxs-lookup"><span data-stu-id="629be-135">To perform file or filegroup backups, create a task for each database.</span></span>  
  
 <span data-ttu-id="629be-136">**O conjunto de backup vai expirar**</span><span class="sxs-lookup"><span data-stu-id="629be-136">**Backup set will expire**</span></span>  
 <span data-ttu-id="629be-137">Especifica quando o conjunto de backup pode ser substituído por outro conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="629be-137">Specify when the backup set can be overwritten by another backup set.</span></span>  
  
 <span data-ttu-id="629be-138">**Fazer backup em**</span><span class="sxs-lookup"><span data-stu-id="629be-138">**Back up to**</span></span>  
 <span data-ttu-id="629be-139">Execute o backup do banco de dados para um arquivo ou fita.</span><span class="sxs-lookup"><span data-stu-id="629be-139">Back up the database to a file or to tape.</span></span> <span data-ttu-id="629be-140">Somente dispositivos de fita anexados ao computador que contém o banco de dados estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="629be-140">Only tape devices attached to the computer containing the database are available.</span></span>  
  
 <span data-ttu-id="629be-141">**Execute o banco de dados por um ou mais arquivos**</span><span class="sxs-lookup"><span data-stu-id="629be-141">**Back up databases across one or more files**</span></span>  
 <span data-ttu-id="629be-142">Clique em **Adicionar** para abrir a caixa de diálogo **Selecionar Destino do Backup** e fornecer um ou mais locais de disco ou dispositivo de fita.</span><span class="sxs-lookup"><span data-stu-id="629be-142">Click **Add** to open the **Select Backup Destination** dialog box, and provide one or more a disk location, or tape device.</span></span>  
  
 <span data-ttu-id="629be-143">**Se existirem arquivos de backup**</span><span class="sxs-lookup"><span data-stu-id="629be-143">**If backup files exist**</span></span>  
 <span data-ttu-id="629be-144">Selecione **Anexar** para adicionar esse backup ao final do arquivo.</span><span class="sxs-lookup"><span data-stu-id="629be-144">Select **Append** to add this backup to the end of the file.</span></span> <span data-ttu-id="629be-145">Selecione **Substituir**, para remover qualquer backup antigo do arquivo e substituí-lo por pelo backup novo.</span><span class="sxs-lookup"><span data-stu-id="629be-145">Select **Overwrite**, to remove any old backup in the file and replace them with this new backup.</span></span>  
  
 <span data-ttu-id="629be-146">**Crie um arquivo de backup para cada banco de dados**</span><span class="sxs-lookup"><span data-stu-id="629be-146">**Create a backup file for every database**</span></span>  
 <span data-ttu-id="629be-147">Crie um arquivo de backup no local especificado na caixa de pasta.</span><span class="sxs-lookup"><span data-stu-id="629be-147">Create a backup file in the location specified in the folder box.</span></span> <span data-ttu-id="629be-148">Um arquivo será criado para cada banco de dados selecionado.</span><span class="sxs-lookup"><span data-stu-id="629be-148">One file will be created for each database selected.</span></span>  
  
 <span data-ttu-id="629be-149">**Crie um subdiretório para cada banco de dados**</span><span class="sxs-lookup"><span data-stu-id="629be-149">**Create a sub-directory for each database**</span></span>  
 <span data-ttu-id="629be-150">Selecione para colocar cada banco de dados em uma subpasta.</span><span class="sxs-lookup"><span data-stu-id="629be-150">Select to place each database in a subfolder.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="629be-151">Embora planos de manutenção possam criar subdiretórios, tarefas de manutenção não podem excluir subdiretórios.</span><span class="sxs-lookup"><span data-stu-id="629be-151">Although maintenance plans can create subdirectories, maintenance tasks cannot delete subdirectories.</span></span> <span data-ttu-id="629be-152">Esse recurso reduz a possibilidade de um ataque mal-intencionado que use a tarefa de Limpeza de Manutenção para excluir arquivos.</span><span class="sxs-lookup"><span data-stu-id="629be-152">This feature reduces the possibility of a malicious attack that uses the Maintenance Cleanup task to delete files.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="629be-153">O subdiretório herda permissões do diretório pai.</span><span class="sxs-lookup"><span data-stu-id="629be-153">The subdirectory inherits permissions from the parent directory.</span></span> <span data-ttu-id="629be-154">Restrinja permissões para evitar acesso não autorizado.</span><span class="sxs-lookup"><span data-stu-id="629be-154">Restrict permissions to avoid unauthorized access.</span></span>  
  
 <span data-ttu-id="629be-155">**Pasta**</span><span class="sxs-lookup"><span data-stu-id="629be-155">**Folder**</span></span>  
 <span data-ttu-id="629be-156">Especifique a pasta para os arquivos de banco de dados automaticamente criados.</span><span class="sxs-lookup"><span data-stu-id="629be-156">Specify the folder to contain the automatically created database files.</span></span>  
  
 <span data-ttu-id="629be-157">**Extensão de arquivo de backup**</span><span class="sxs-lookup"><span data-stu-id="629be-157">**Backup file extension**</span></span>  
 <span data-ttu-id="629be-158">Especifique a extensão a ser usada para os arquivos de backup.</span><span class="sxs-lookup"><span data-stu-id="629be-158">Specify the extension to use for the backup files.</span></span> <span data-ttu-id="629be-159">O valor padrão é **.bak**.</span><span class="sxs-lookup"><span data-stu-id="629be-159">The default is **.bak**.</span></span>  
  
 <span data-ttu-id="629be-160">**Verificar integridade do backup**</span><span class="sxs-lookup"><span data-stu-id="629be-160">**Verify backup integrity**</span></span>  
 <span data-ttu-id="629be-161">Verifique se o conjunto de backup está completo e se todos os volumes estão legíveis.</span><span class="sxs-lookup"><span data-stu-id="629be-161">Verify that the backup set is complete and that all volumes are readable.</span></span>  
  
 <span data-ttu-id="629be-162">**Fazer backup da parte final do log e deixar o banco de dados no estado de restauração**</span><span class="sxs-lookup"><span data-stu-id="629be-162">**Back up the tail of the log, and leave the database in the restoring state**</span></span>  
 <span data-ttu-id="629be-163">Execute um backup de log como a última etapa antes de restaurar um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="629be-163">Perform a log backup as the last step before restoring a database.</span></span> <span data-ttu-id="629be-164">Para obter mais informações, veja [Backups da parte final do log &#40;SQL Server&#41;](../backup-restore/tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="629be-164">For more information, see [Tail-Log Backups &#40;SQL Server&#41;](../backup-restore/tail-log-backups-sql-server.md).</span></span>  
  
 <span data-ttu-id="629be-165">**Defina compactação de backup**</span><span class="sxs-lookup"><span data-stu-id="629be-165">**Set backup compression**</span></span>  
 <span data-ttu-id="629be-166">Em [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] (ou em uma versão posterior), selecione um dos seguintes valores de [compactação de backup](../backup-restore/backup-compression-sql-server.md) :</span><span class="sxs-lookup"><span data-stu-id="629be-166">In [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] (or a later version), select one the following [backup compression](../backup-restore/backup-compression-sql-server.md) values:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="629be-167">**Usar a configuração padrão do servidor**</span><span class="sxs-lookup"><span data-stu-id="629be-167">**Use the default server setting**</span></span>|<span data-ttu-id="629be-168">Clique para usar o padrão do nível de servidor.</span><span class="sxs-lookup"><span data-stu-id="629be-168">Click to use the server-level default.</span></span><br /><br /> <span data-ttu-id="629be-169">Esse padrão é definido pela opção de configuração do servidor **padrão de compactação de backup** .</span><span class="sxs-lookup"><span data-stu-id="629be-169">This default is set by the **backup compression default** server-configuration option.</span></span> <span data-ttu-id="629be-170">Para obter informações sobre como exibir a configuração atual dessa opção, veja [Exibir ou configurar a opção backup compression default de configuração de servidor](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="629be-170">For information about how to view the current setting of this option,  see [View or Configure the backup compression default Server Configuration Option](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span></span>|  
|<span data-ttu-id="629be-171">**Compactar backup**</span><span class="sxs-lookup"><span data-stu-id="629be-171">**Compress backup**</span></span>|<span data-ttu-id="629be-172">Clique em compactar backup, independentemente do padrão do nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="629be-172">Click to compress the backup, regardless of the server-level default.</span></span><br /><br /> <span data-ttu-id="629be-173">**\*\* Importante \*\*** Por padrão, a compactação aumenta consideravelmente o uso da CPU, e o consumo adicional da CPU por parte do processo de compactação pode afetar negativamente as operações simultâneas.</span><span class="sxs-lookup"><span data-stu-id="629be-173">**\*\* Important \*\*** By default, compression significantly increases CPU usage, and the additional CPU consumed by the compression process might adversely affect concurrent operations.</span></span> <span data-ttu-id="629be-174">Portanto, é recomendável criar backups compactados de baixa prioridade em uma sessão cujo uso da CPU é limitado pelo [Administrador de Recursos](../resource-governor/resource-governor.md).</span><span class="sxs-lookup"><span data-stu-id="629be-174">Therefore, you might want to create low-priority compressed backups in a session whose CPU usage is limited by [Resource Governor](../resource-governor/resource-governor.md).</span></span> <span data-ttu-id="629be-175">Para obter mais informações, consulte [Usar o Resource Governor para limitar o uso de CPU por meio de compactação de backup &#40;Transact-SQL&#41;](../backup-restore/use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="629be-175">For more information, see [Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;](../backup-restore/use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span></span>|  
|<span data-ttu-id="629be-176">**Não compactar o backup**</span><span class="sxs-lookup"><span data-stu-id="629be-176">**Do not compress backup**</span></span>|<span data-ttu-id="629be-177">Clique em criar um backup não compactado, independentemente do padrão do nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="629be-177">Click to create an uncompressed backup, regardless of the server-level default.</span></span>|  
  
 <span data-ttu-id="629be-178">**Exibir T-SQL**</span><span class="sxs-lookup"><span data-stu-id="629be-178">**View T-SQL**</span></span>  
 <span data-ttu-id="629be-179">Exiba as instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] executadas no servidor para esta tarefa, com base nas opções selecionadas.</span><span class="sxs-lookup"><span data-stu-id="629be-179">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="629be-180">Quando o número de objetos afetados é grande, essa exibição pode ser demorada.</span><span class="sxs-lookup"><span data-stu-id="629be-180">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="629be-181">Caixa de diálogo Nova Conexão</span><span class="sxs-lookup"><span data-stu-id="629be-181">New Connection Dialog Box</span></span>  
 <span data-ttu-id="629be-182">**Nome da conexão**</span><span class="sxs-lookup"><span data-stu-id="629be-182">**Connection name**</span></span>  
 <span data-ttu-id="629be-183">Digite um nome para a nova conexão.</span><span class="sxs-lookup"><span data-stu-id="629be-183">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="629be-184">**Selecione ou digite um nome de servidor**</span><span class="sxs-lookup"><span data-stu-id="629be-184">**Select or enter a server name**</span></span>  
 <span data-ttu-id="629be-185">Selecione um servidor com o qual se conectar ao executar esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="629be-185">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="629be-186">**Atualizar**</span><span class="sxs-lookup"><span data-stu-id="629be-186">**Refresh**</span></span>  
 <span data-ttu-id="629be-187">Atualize a lista de servidores disponíveis.</span><span class="sxs-lookup"><span data-stu-id="629be-187">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="629be-188">**Digite as informações para fazer logon no servidor**</span><span class="sxs-lookup"><span data-stu-id="629be-188">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="629be-189">Especifica como autenticar no servidor.</span><span class="sxs-lookup"><span data-stu-id="629be-189">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="629be-190">**Use a segurança integrada do Windows**</span><span class="sxs-lookup"><span data-stu-id="629be-190">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="629be-191">Conecte-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] com a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="629be-191">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with Windows Authentication.</span></span>  
  
 <span data-ttu-id="629be-192">**Usar nome de usuário e senha específicos**</span><span class="sxs-lookup"><span data-stu-id="629be-192">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="629be-193">Conecte-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="629be-193">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="629be-194">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="629be-194">This option is not available.</span></span>  
  
 <span data-ttu-id="629be-195">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="629be-195">**User name**</span></span>  
 <span data-ttu-id="629be-196">Forneça um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a ser usado na autenticação.</span><span class="sxs-lookup"><span data-stu-id="629be-196">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="629be-197">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="629be-197">This option is not available.</span></span>  
  
 <span data-ttu-id="629be-198">**Senha**</span><span class="sxs-lookup"><span data-stu-id="629be-198">**Password**</span></span>  
 <span data-ttu-id="629be-199">Forneça uma senha a ser usada na autenticação.</span><span class="sxs-lookup"><span data-stu-id="629be-199">Provide a password to use when authenticating.</span></span> <span data-ttu-id="629be-200">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="629be-200">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="629be-201">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="629be-201">See Also</span></span>  
 [<span data-ttu-id="629be-202">BACKUP &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="629be-202">BACKUP &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/backup-transact-sql)  
  
  
