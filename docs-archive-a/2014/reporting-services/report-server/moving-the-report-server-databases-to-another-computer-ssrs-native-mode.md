---
title: Movendo os bancos de dados do servidor de relatório para outro computador (modo nativo do SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 44a9854d-e333-44f6-bdc7-8837b9f34416
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 49fd35f57cf783b262b3c690e3047e5f479ab193
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678573"
---
# <a name="moving-the-report-server-databases-to-another-computer-ssrs-native-mode"></a><span data-ttu-id="ba517-102">Movendo os bancos de dados do servidor de relatório para outro computador (modo nativo do SSRS)</span><span class="sxs-lookup"><span data-stu-id="ba517-102">Moving the Report Server Databases to Another Computer (SSRS Native Mode)</span></span>
  <span data-ttu-id="ba517-103">Você pode mover os bancos de dados do servidor de relatório que são usados em uma instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] para uma instância do que está em um computador diferente.</span><span class="sxs-lookup"><span data-stu-id="ba517-103">You can move the report server databases that are used in an installation [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] to an instance that is on a different computer.</span></span> <span data-ttu-id="ba517-104">Os bancos de dados reportserver e reportservertempdb devem ser movidos ou copiados juntos.</span><span class="sxs-lookup"><span data-stu-id="ba517-104">Both the reportserver and reportservertempdb databases must be moved or copied together.</span></span> <span data-ttu-id="ba517-105">Uma instalação do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] requer os dois bancos de dados; o banco de dados reportservertempdb deve ser relacionado por nome ao banco de dados reportserver primário que está sendo movido.</span><span class="sxs-lookup"><span data-stu-id="ba517-105">A [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation requires both databases; the reportservertempdb database must be related by name to the primary reportserver database you are moving.</span></span>  
  
 <span data-ttu-id="ba517-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modo nativo.</span><span class="sxs-lookup"><span data-stu-id="ba517-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>  
  
 <span data-ttu-id="ba517-107">A movimentação de um banco de dados não afeta as operações agendadas que estão definidas atualmente para itens de servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="ba517-107">Moving a database does not effect scheduled operations that are currently defined for report server items.</span></span>  
  
-   <span data-ttu-id="ba517-108">As agendas serão recriadas na primeira vez em que o serviço do servidor de relatório for reiniciado.</span><span class="sxs-lookup"><span data-stu-id="ba517-108">Schedules will be recreated the first time that you restart the Report Server service.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ba517-109">Agent que são usados para acionar uma agenda serão recriados na nova instância do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ba517-109">Agent jobs that are used to trigger a schedule will be recreated on the new database instance.</span></span> <span data-ttu-id="ba517-110">Não é necessário mover os trabalhos para o novo computador, mas você pode excluir os trabalhos que não serão mais usados.</span><span class="sxs-lookup"><span data-stu-id="ba517-110">You do not have to move the jobs to the new computer, but you might want to delete jobs on the computer that will no longer be used.</span></span>  
  
-   <span data-ttu-id="ba517-111">Assinaturas, relatórios em cache e instantâneos são preservados no banco de dados movido.</span><span class="sxs-lookup"><span data-stu-id="ba517-111">Subscriptions, cached reports, and snapshots are preserved in the moved database.</span></span> <span data-ttu-id="ba517-112">Se um instantâneo não estiver capturando dados atualizados depois que o banco de dados for movido, desmarque as opções de instantâneo no Gerenciador de Relatórios, clique em **Aplicar** para salvar as alterações, recrie o agendamento e clique em **Aplicar** novamente para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="ba517-112">If a snapshot is not picking up refreshed data after the database is moved, clear the snapshot options in Report Manager, click **Apply** to save your changes, re-create the schedule, and click **Apply** again to save your changes.</span></span>  
  
-   <span data-ttu-id="ba517-113">Os dados do relatório temporário e da sessão de usuário que são armazenados em reportservertempdb são mantidos quando o banco de dados é movido.</span><span class="sxs-lookup"><span data-stu-id="ba517-113">Temporary report and user session data that is stored in reportservertempdb are persisted when you move that database.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ba517-114">fornece várias abordagens para mover bancos de dados, inclusive backup e restauração, anexação e desanexação e cópia.</span><span class="sxs-lookup"><span data-stu-id="ba517-114">provides several approaches for moving databases, including backup and restore, attach and detach, and copy.</span></span> <span data-ttu-id="ba517-115">Nem todas as abordagens são apropriadas para realocar um banco de dados existente em uma nova instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="ba517-115">Not all approaches are appropriate for relocating an existing database to a new server instance.</span></span> <span data-ttu-id="ba517-116">A abordagem que deve ser usada para mover o banco de dados do servidor de relatório varia dependendo dos requisitos de disponibilidade do sistema.</span><span class="sxs-lookup"><span data-stu-id="ba517-116">The approach that you should use to move the report server database will vary depending on your system availability requirements.</span></span> <span data-ttu-id="ba517-117">O modo mais fácil para mover os bancos de dados do servidor de relatório é anexá-los e desanexá-los.</span><span class="sxs-lookup"><span data-stu-id="ba517-117">The easiest way to move the report server databases is to attach and detach them.</span></span> <span data-ttu-id="ba517-118">No entanto, esta abordagem requer que o servidor de relatório fique offline enquanto o banco de dados é desanexado.</span><span class="sxs-lookup"><span data-stu-id="ba517-118">However, this approach requires that you take the report server offline while you detach the database.</span></span> <span data-ttu-id="ba517-119">O backup e a restauração são a melhor opção se você desejar minimizar as interrupções de serviço, mas é necessário executar os comandos [!INCLUDE[tsql](../../includes/tsql-md.md)] para efetuar as operações.</span><span class="sxs-lookup"><span data-stu-id="ba517-119">Backup and restore is a better choice if you want to minimize service disruptions, but you must run [!INCLUDE[tsql](../../includes/tsql-md.md)] commands to perform the operations.</span></span> <span data-ttu-id="ba517-120">A cópia do banco de dados não é recomendada (principalmente se o Assistente para Copiar Banco de Dados for utilizado); as configurações de permissão não são preservadas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ba517-120">Copying the database is not recommended (specifically, by using the Copy Database Wizard); it does not preserve permission settings in the database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ba517-121">As etapas descritas neste tópico são recomendadas quando a realocação do banco de dados do servidor de relatório for a única alteração feita na instalação existente.</span><span class="sxs-lookup"><span data-stu-id="ba517-121">The steps provided in this topic are recommended when relocating the report server database is the only change you are making to the existing installation.</span></span> <span data-ttu-id="ba517-122">A migração de uma instalação inteira do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] (ou seja, a movimentação do banco de dados e a alteração da identidade do serviço Windows do Servidor de Relatório que usa o banco de dados) exige a reconfiguração da conexão e a redefinição de uma chave de criptografia.</span><span class="sxs-lookup"><span data-stu-id="ba517-122">Migrating an entire [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation (that is, moving the database and changing the identity of the Report Server Windows service that uses the database) requires connection reconfiguration and an encryption key reset.</span></span>  
  
## <a name="detaching-and-attaching-the-report-server-databases"></a><span data-ttu-id="ba517-123">Desanexando e anexando os bancos de dados do servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="ba517-123">Detaching and Attaching the Report Server Databases</span></span>  
 <span data-ttu-id="ba517-124">Se conseguir colocar o servidor de relatório offline, você poderá desanexar os bancos de dados para movê-los para a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a ser usada.</span><span class="sxs-lookup"><span data-stu-id="ba517-124">If you can take the report server offline, you can detach the databases to move them to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you want to use.</span></span> <span data-ttu-id="ba517-125">Esta abordagem preserva as permissões nos bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="ba517-125">This approach preserves permissions in the databases.</span></span> <span data-ttu-id="ba517-126">Se você estiver usando um banco de dados do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , mova-o para outra instância do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ba517-126">If you are using a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] database, you must move it to another [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] instance.</span></span> <span data-ttu-id="ba517-127">Depois de mover os bancos de dados, reconfigure a conexão do servidor de relatório com o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ba517-127">After you move the databases, you must reconfigure the report server connection to the report server database.</span></span> <span data-ttu-id="ba517-128">Se você estiver executando uma implantação de expansão, deverá reconfigurar a conexão do banco de dados do servidor de relatório para cada servidor de relatório da implantação.</span><span class="sxs-lookup"><span data-stu-id="ba517-128">If you are running a scale-out deployment, you must reconfigure the report server database connection for each report server in the deployment.</span></span>  
  
 <span data-ttu-id="ba517-129">Realize as etapas a seguir para mover os bancos de dados:</span><span class="sxs-lookup"><span data-stu-id="ba517-129">Use the following steps to move the databases:</span></span>  
  
1.  <span data-ttu-id="ba517-130">Faça backup das chaves de criptografia para o banco de dados do servidor de relatório que deseja mover.</span><span class="sxs-lookup"><span data-stu-id="ba517-130">Backup the encryption keys for the report server database you want to move.</span></span> <span data-ttu-id="ba517-131">Você pode usar a ferramenta Configuração do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] para fazer backup das chaves.</span><span class="sxs-lookup"><span data-stu-id="ba517-131">You can use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool backup the keys.</span></span>  
  
2.  <span data-ttu-id="ba517-132">Pare o serviço do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="ba517-132">Stop the Report Server service.</span></span> <span data-ttu-id="ba517-133">Você pode usar a ferramenta Configuração do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] para parar o serviço.</span><span class="sxs-lookup"><span data-stu-id="ba517-133">You can use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool to stop the service.</span></span>  
  
3.  <span data-ttu-id="ba517-134">Inicie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] e abra uma conexão com a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instância que hospeda os bancos de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="ba517-134">Start [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and open a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that hosts the report server databases.</span></span>  
  
4.  <span data-ttu-id="ba517-135">Clique com o botão direito do mouse no banco de dados do servidor de relatório, aponte para Tarefas e clique em **Desanexar**.</span><span class="sxs-lookup"><span data-stu-id="ba517-135">Right-click the report server database, point to Tasks, and click **Detach**.</span></span> <span data-ttu-id="ba517-136">Repita esta etapa para o banco de dados temporário do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="ba517-136">Repeat this step for the report server temporary database.</span></span>  
  
5.  <span data-ttu-id="ba517-137">Copie ou mova os arquivos .mdf e .ldf para a pasta Dados da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="ba517-137">Copy or move the .mdf and .ldf files to the Data folder of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you want to use.</span></span> <span data-ttu-id="ba517-138">Como dois bancos de dados estão sendo movidos, certifique-se de mover ou copiar os quatro arquivos.</span><span class="sxs-lookup"><span data-stu-id="ba517-138">Because you are moving two databases, make sure that you move or copy all four files.</span></span>  
  
6.  <span data-ttu-id="ba517-139">No [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], abra uma conexão com a nova instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que hospedará os bancos de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="ba517-139">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], open a connection to the new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that will host the report server databases.</span></span>  
  
7.  <span data-ttu-id="ba517-140">Clique com o botão direito do mouse no nó Bancos de dados e clique em **Anexar**.</span><span class="sxs-lookup"><span data-stu-id="ba517-140">Right-click the Databases node, and then click **Attach**.</span></span>  
  
8.  <span data-ttu-id="ba517-141">Clique em **Adicionar** para selecionar os arquivos .mdf e .ldf do banco de dados do servidor de relatórios que deseja anexar.</span><span class="sxs-lookup"><span data-stu-id="ba517-141">Click **Add** to select the report server database .mdf and .ldf files that you want to attach.</span></span> <span data-ttu-id="ba517-142">Repita esta etapa para o banco de dados temporário do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="ba517-142">Repeat this step for the report server temporary database.</span></span>  
  
9. <span data-ttu-id="ba517-143">Depois que os bancos de dados forem anexados, verifique se o `RSExecRole` é uma função de banco de dados no banco de dados do servidor de relatório e no banco de dados temporário.</span><span class="sxs-lookup"><span data-stu-id="ba517-143">After the databases are attached, verify that the `RSExecRole` is a database role in the report server database and temporary database.</span></span> <span data-ttu-id="ba517-144">`RSExecRole`é necessário ter permissões de selecionar, inserir, atualizar, excluir e referenciar nas tabelas de banco de dados do servidor de relatório e permissões de execução nos procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="ba517-144">`RSExecRole` must have select, insert, update, delete, and reference permissions on the report server database tables, and execute permissions on the stored procedures.</span></span> <span data-ttu-id="ba517-145">Para mais informações, veja [Criar o RSExecRole](../security/create-the-rsexecrole.md).</span><span class="sxs-lookup"><span data-stu-id="ba517-145">For more information, see [Create the RSExecRole](../security/create-the-rsexecrole.md).</span></span>  
  
10. <span data-ttu-id="ba517-146">Inicie a ferramenta Configuração do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e abra uma conexão com o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="ba517-146">Start the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool and open a connection to the report server.</span></span>  
  
11. <span data-ttu-id="ba517-147">Na página Banco de dados, selecione a nova instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="ba517-147">On the Database page, select the new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance, and then click **Connect**.</span></span>  
  
12. <span data-ttu-id="ba517-148">Selecione o banco de dados do servidor de relatório que acaba de ser movido e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="ba517-148">Select the report server database that you just moved, and then click **Apply**.</span></span>  
  
13. <span data-ttu-id="ba517-149">Na página Chaves de Criptografia, clique em Restaurar.</span><span class="sxs-lookup"><span data-stu-id="ba517-149">On the Encryption Keys page, click Restore.</span></span> <span data-ttu-id="ba517-150">Especifique o arquivo que contém a cópia de backup das chaves e a senha para desbloquear o arquivo.</span><span class="sxs-lookup"><span data-stu-id="ba517-150">Specify the file that contains the backup copy of the keys and the password to unlock the file.</span></span>  
  
14. <span data-ttu-id="ba517-151">Reinicie o serviço Servidor de Relatório.</span><span class="sxs-lookup"><span data-stu-id="ba517-151">Restart the Report Server service.</span></span>  
  
## <a name="backing-up-and-restoring-the-report-server-databases"></a><span data-ttu-id="ba517-152">Fazendo backup e restaurando os bancos de dados do servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="ba517-152">Backing Up and Restoring the Report Server Databases</span></span>  
 <span data-ttu-id="ba517-153">Se não for possível colocar o servidor de relatório offline, use o recurso de backup e restauração para realocar os bancos de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="ba517-153">If you cannot take the report server offline, you can use backup and restore to relocate the report server databases.</span></span> <span data-ttu-id="ba517-154">Você deve usar instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] para fazer o backup e a restauração.</span><span class="sxs-lookup"><span data-stu-id="ba517-154">You must use [!INCLUDE[tsql](../../includes/tsql-md.md)] statements to do the backup and restore.</span></span> <span data-ttu-id="ba517-155">Depois de restaurar os bancos de dados, configure o servidor de relatório para usar o banco de dados na nova instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="ba517-155">After you restore the databases, you must configure the report server to use the database on the new server instance.</span></span> <span data-ttu-id="ba517-156">Para obter mais informações, consulte as instruções no final deste tópico.</span><span class="sxs-lookup"><span data-stu-id="ba517-156">For more information, see the instructions at the end of this topic.</span></span>  
  
### <a name="using-backup-and-copy_only-to-backup-the-report-server-databases"></a><span data-ttu-id="ba517-157">Usando BACKUP e COPY_ONLY para fazer backup dos bancos de dados do servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="ba517-157">Using BACKUP and COPY_ONLY to Backup the Report Server Databases</span></span>  
 <span data-ttu-id="ba517-158">Ao fazer backup dos bancos de dados, defina o argumento COPY_ONLY.</span><span class="sxs-lookup"><span data-stu-id="ba517-158">When backing up the databases, set the COPY_ONLY argument.</span></span> <span data-ttu-id="ba517-159">Faça backup dos bancos de dados e dos arquivos de log.</span><span class="sxs-lookup"><span data-stu-id="ba517-159">Be sure to back up both of the databases and log files.</span></span>  
  
```  
-- To permit log backups, before the full database backup, alter the database   
-- to use the full recovery model.  
USE master;  
GO  
ALTER DATABASE ReportServer  
   SET RECOVERY FULL  
  
-- If the ReportServerData device does not exist yet, create it.   
USE master  
GO  
EXEC sp_addumpdevice 'disk', 'ReportServerData',   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\BACKUP\ReportServerData.bak'  
  
-- Create a logical backup device, ReportServerLog.  
USE master  
GO  
EXEC sp_addumpdevice 'disk', 'ReportServerLog',   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\BACKUP\ReportServerLog.bak'  
  
-- Back up the full ReportServer database.  
BACKUP DATABASE ReportServer  
   TO ReportServerData  
   WITH COPY_ONLY  
  
-- Back up the ReportServer log.  
BACKUP LOG ReportServer  
   TO ReportServerLog  
   WITH COPY_ONLY  
  
-- To permit log backups, before the full database backup, alter the database   
-- to use the full recovery model.  
USE master;  
GO  
ALTER DATABASE ReportServerTempdb  
   SET RECOVERY FULL  
  
-- If the ReportServerTempDBData device does not exist yet, create it.   
USE master  
GO  
EXEC sp_addumpdevice 'disk', 'ReportServerTempDBData',   
'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\BACKUP\ReportServerTempDBData.bak'  
  
-- Create a logical backup device, ReportServerTempDBLog.  
USE master  
GO  
EXEC sp_addumpdevice 'disk', 'ReportServerTempDBLog',   
'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\BACKUP\ReportServerTempDBLog.bak'  
  
-- Back up the full ReportServerTempDB database.  
BACKUP DATABASE ReportServerTempDB  
   TO ReportServerTempDBData  
   WITH COPY_ONLY  
  
-- Back up the ReportServerTempDB log.  
BACKUP LOG ReportServerTempDB  
   TO ReportServerTempDBLog  
   WITH COPY_ONLY  
```  
  
### <a name="using-restore-and-move-to-relocate-the-report-server-databases"></a><span data-ttu-id="ba517-160">Usando RESTORE e MOVE para realocar os bancos de dados do servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="ba517-160">Using RESTORE and MOVE to Relocate the Report Server Databases</span></span>  
 <span data-ttu-id="ba517-161">Ao restaurar os bancos de dados, inclua o argumento MOVE para especificar um caminho.</span><span class="sxs-lookup"><span data-stu-id="ba517-161">When restoring the databases, be sure to include the MOVE argument so that you can specify a path.</span></span> <span data-ttu-id="ba517-162">Use o argumento NORECOVERY para executar a restauração inicial; isso mantém o banco de dados no estado RESTORING, permitindo que você tenha tempo de revisar os backups de log para determinar qual deve ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="ba517-162">Use the NORECOVERY argument to perform the initial restore; this keeps the database in a RESTORING state, giving you time to review log backups to determine which one to restore.</span></span> <span data-ttu-id="ba517-163">A etapa final repete a operação RESTORE com o argumento RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="ba517-163">The final step repeats the RESTORE operation with the RECOVERY argument.</span></span>  
  
 <span data-ttu-id="ba517-164">O argumento MOVE usa o nome lógico do arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="ba517-164">The MOVE argument uses the logical name of the data file.</span></span> <span data-ttu-id="ba517-165">Para localizar o nome lógico, execute a seguinte instrução: `RESTORE FILELISTONLY FROM DISK='C:\ReportServerData.bak';`</span><span class="sxs-lookup"><span data-stu-id="ba517-165">To find the logical name, execute the following statement: `RESTORE FILELISTONLY FROM DISK='C:\ReportServerData.bak';`</span></span>  
  
 <span data-ttu-id="ba517-166">O exemplo a seguir inclui o argumento FILE para especificar a posição do arquivo de log a ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="ba517-166">The following examples include the FILE argument so that you can specify the file position of the log file to restore.</span></span> <span data-ttu-id="ba517-167">Para localizar a posição do arquivo, execute a seguinte instrução: `RESTORE HEADERONLY FROM DISK='C:\ReportServerData.bak';`</span><span class="sxs-lookup"><span data-stu-id="ba517-167">To find the file position, execute the following statement: `RESTORE HEADERONLY FROM DISK='C:\ReportServerData.bak';`</span></span>  
  
 <span data-ttu-id="ba517-168">Ao restaurar o banco de dados e os arquivos de log, execute cada operação RESTORE separadamente.</span><span class="sxs-lookup"><span data-stu-id="ba517-168">When restoring the database and log files, you should run each RESTORE operation separately.</span></span>  
  
```  
-- Restore the report server database and move to new instance folder   
RESTORE DATABASE ReportServer  
   FROM DISK='C:\ReportServerData.bak'  
   WITH NORECOVERY,   
      MOVE 'ReportServer' TO   
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServer.mdf',   
      MOVE 'ReportServer_log' TO  
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServer_Log.ldf';  
GO  
  
-- Restore the report server log file to new instance folder   
RESTORE LOG ReportServer  
   FROM DISK='C:\ReportServerData.bak'  
   WITH NORECOVERY, FILE=2  
      MOVE 'ReportServer' TO   
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServer.mdf',   
      MOVE 'ReportServer_log' TO  
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServer_Log.ldf';  
GO  
  
-- Restore and move the report server temporary database  
RESTORE DATABASE ReportServerTempdb  
   FROM DISK='C:\ReportServerTempDBData.bak'  
   WITH NORECOVERY,   
      MOVE 'ReportServerTempDB' TO   
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServerTempDB.mdf',   
      MOVE 'ReportServerTempDB_log' TO  
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\REportServerTempDB_Log.ldf';  
GO  
  
-- Restore the temporary database log file to new instance folder   
RESTORE LOG ReportServerTempdb  
   FROM DISK='C:\ReportServerTempDBData.bak'  
   WITH NORECOVERY, FILE=2  
      MOVE 'ReportServerTempDB' TO   
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServerTempDB.mdf',   
      MOVE 'ReportServerTempDB_log' TO  
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\REportServerTempDB_Log.ldf';  
GO  
  
-- Perform final restore  
RESTORE DATABASE ReportServer  
   WITH RECOVERY  
GO  
  
-- Perform final restore  
RESTORE DATABASE ReportServerTempDB  
   WITH RECOVERY  
GO  
```  
  
### <a name="how-to-configure-the-report-server-database-connection"></a><span data-ttu-id="ba517-169">Como configurar a conexão do banco de dados do servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="ba517-169">How to Configure the Report Server Database Connection</span></span>  
  
1.  <span data-ttu-id="ba517-170">Inicie o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager e abra uma conexão com o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="ba517-170">Start the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager and open a connection to the report server.</span></span>  
  
2.  <span data-ttu-id="ba517-171">Na página Banco de Dados, clique em **Alterar Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="ba517-171">On the Database page, click **Change Database**.</span></span> <span data-ttu-id="ba517-172">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ba517-172">Click **Next**.</span></span>  
  
3.  <span data-ttu-id="ba517-173">Clique em **Escolher um banco de dados existente do servidor de relatório**.</span><span class="sxs-lookup"><span data-stu-id="ba517-173">Click **Choose an existing report server database**.</span></span> <span data-ttu-id="ba517-174">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ba517-174">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="ba517-175">Selecione o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que agora hospeda o banco de dados do servidor de relatório e clique em **Testar Conexão**.</span><span class="sxs-lookup"><span data-stu-id="ba517-175">Select the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that now hosts the report server database and click **Test Connection**.</span></span> <span data-ttu-id="ba517-176">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ba517-176">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="ba517-177">Em Nome do Banco de Dados, selecione o banco de dados do servidor de relatório que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="ba517-177">In Database Name, select the report server database that you want to use.</span></span> <span data-ttu-id="ba517-178">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ba517-178">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="ba517-179">Em Credenciais, especifique as credenciais que o servidor de relatório usará para conectar-se ao banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="ba517-179">In Credentials, specify the credentials that the report server will use to connect to the report server database.</span></span> <span data-ttu-id="ba517-180">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ba517-180">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="ba517-181">Clique em **Avançar** e em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="ba517-181">Click **Next** and then **Finish**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ba517-182">Uma instalação do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] requer que a instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] inclua a função `RSExecRole`.</span><span class="sxs-lookup"><span data-stu-id="ba517-182">A [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation requires that the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] instance include the `RSExecRole` role.</span></span> <span data-ttu-id="ba517-183">A criação de funções, o registro de logon e as atribuições de função ocorrem quando a conexão do banco de dados do servidor de relatório é definida por meio da ferramenta Configuração do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ba517-183">Role creation, login registration, and role assignments occur when you set the report server database connection through the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool.</span></span> <span data-ttu-id="ba517-184">Se você usar abordagens alternativas (especificamente, se usar o utilitário de prompt de comando rsconfig.exe) para configurar a conexão, o servidor de relatório não estará em um estado de funcionamento.</span><span class="sxs-lookup"><span data-stu-id="ba517-184">If you use alternate approaches (specifically, if you use the rsconfig.exe command prompt utility) to configure the connection, the report server will not be in a working state.</span></span> <span data-ttu-id="ba517-185">Talvez seja necessário gravar o código WMI para disponibilizar o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="ba517-185">You might have to write WMI code to make the report server available.</span></span> <span data-ttu-id="ba517-186">Para obter mais informações, consulte [Acessar o provedor WMI do Reporting Services](../tools/access-the-reporting-services-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="ba517-186">For more information, see [Access the Reporting Services WMI Provider](../tools/access-the-reporting-services-wmi-provider.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba517-187">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ba517-187">See Also</span></span>  
 <span data-ttu-id="ba517-188">[Criar o RSExecRole](../security/create-the-rsexecrole.md) </span><span class="sxs-lookup"><span data-stu-id="ba517-188">[Create the RSExecRole](../security/create-the-rsexecrole.md) </span></span>  
 <span data-ttu-id="ba517-189">[Iniciar e parar o serviço Servidor de Relatório](start-and-stop-the-report-server-service.md) </span><span class="sxs-lookup"><span data-stu-id="ba517-189">[Start and Stop the Report Server Service](start-and-stop-the-report-server-service.md) </span></span>  
 <span data-ttu-id="ba517-190">[Configurar uma conexão de banco de dados do servidor de relatório &#40;Configuration Manager SSRS&#41;](../../sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="ba517-190">[Configure a Report Server Database Connection  &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="ba517-191">[Configurar a conta de execução autônoma &#40;Configuration Manager do SSRS&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="ba517-191">[Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="ba517-192">[Reporting Services Configuration Manager &#40;Modo Nativo&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="ba517-192">[Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span></span>  
 <span data-ttu-id="ba517-193">[Utilitário rsconfig &#40;SSRS&#41;](../tools/rsconfig-utility-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ba517-193">[rsconfig Utility &#40;SSRS&#41;](../tools/rsconfig-utility-ssrs.md) </span></span>  
 <span data-ttu-id="ba517-194">[Configurar e gerenciar chaves de criptografia &#40;Configuration Manager SSRS&#41;](../install-windows/ssrs-encryption-keys-manage-encryption-keys.md) </span><span class="sxs-lookup"><span data-stu-id="ba517-194">[Configure and Manage Encryption Keys &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-encryption-keys-manage-encryption-keys.md) </span></span>  
 [<span data-ttu-id="ba517-195">Banco de dados do servidor de relatório &#40;modo nativo do SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ba517-195">Report Server Database &#40;SSRS Native Mode&#41;</span></span>](report-server-database-ssrs-native-mode.md)  
  
  
