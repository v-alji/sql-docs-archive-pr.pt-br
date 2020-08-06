---
title: Mover bancos de dados do sistema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- moving system databases
- disaster recovery [SQL Server], moving database files
- database files [SQL Server], moving
- data files [SQL Server], moving
- tempdb database [SQL Server], moving
- system databases [SQL Server], moving
- scheduled disk maintenace [SQL Server]
- moving databases
- msdb database [SQL Server], moving
- moving database files
- relocating database files
- planned database relocations [SQL Server]
- master database [SQL Server], moving
- model database [SQL Server], moving
- Resource database [SQL Server]
- databases [SQL Server], moving
ms.assetid: 72bb62ee-9602-4f71-be51-c466c1670878
author: stevestein
ms.author: sstein
ms.openlocfilehash: 748d781d6bbefb0dc710427a34ebd71ec7037fdb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686310"
---
# <a name="move-system-databases"></a><span data-ttu-id="af3a7-102">Mover bancos de dados do sistema</span><span class="sxs-lookup"><span data-stu-id="af3a7-102">Move System Databases</span></span>
  <span data-ttu-id="af3a7-103">Este tópico descreve como mover bancos de dados do sistema no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af3a7-103">This topic describes how to move system databases in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="af3a7-104">Mover bancos de dados do sistema pode ser útil nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="af3a7-104">Moving system databases may be useful in the following situations:</span></span>  
  
-   <span data-ttu-id="af3a7-105">Recuperação de falha.</span><span class="sxs-lookup"><span data-stu-id="af3a7-105">Failure recovery.</span></span> <span data-ttu-id="af3a7-106">Por exemplo, o banco de dados está em modo de suspeição ou foi desligado devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="af3a7-106">For example, the database is in suspect mode or has shut down because of a hardware failure.</span></span>  
  
-   <span data-ttu-id="af3a7-107">Realocação planejada.</span><span class="sxs-lookup"><span data-stu-id="af3a7-107">Planned relocation.</span></span>  
  
-   <span data-ttu-id="af3a7-108">Realocação para manutenção de disco programada.</span><span class="sxs-lookup"><span data-stu-id="af3a7-108">Relocation for scheduled disk maintenance.</span></span>  
  
 <span data-ttu-id="af3a7-109">Os procedimentos a seguir se aplicam para mover arquivos de banco de dados dentro da mesma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af3a7-109">The following procedures apply to moving database files within the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="af3a7-110">Para mover um banco de dados para uma outra instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou para um outro servidor, use as operações de [backup e restauração](../backup-restore/back-up-and-restore-of-sql-server-databases.md) ou [de anexação e desanexação](move-a-database-using-detach-and-attach-transact-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="af3a7-110">To move a database to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or to another server, use the [backup and restore](../backup-restore/back-up-and-restore-of-sql-server-databases.md) or [detach and attach](move-a-database-using-detach-and-attach-transact-sql.md) operations.</span></span>  
  
 <span data-ttu-id="af3a7-111">Os procedimentos neste tópico exigem o nome lógico dos arquivos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="af3a7-111">The procedures in this topic require the logical name of the database files.</span></span> <span data-ttu-id="af3a7-112">Para obter o nome, consulte a coluna de nome na exibição de catálogo [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="af3a7-112">To obtain the name, query the name column in the [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) catalog view.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="af3a7-113">Se você mover um banco de dados do sistema e, posteriormente, recriar o banco de dados mestre, será necessário mover o banco de dados do sistema novamente porque a operação de recriação instala todos os bancos de dados do sistema em seus locais padrão.</span><span class="sxs-lookup"><span data-stu-id="af3a7-113">If you move a system database and later rebuild the master database, you must move the system database again because the rebuild operation installs all system databases to their default location.</span></span>  
  
##  <a name="in-this-topic"></a><a name="Intro"></a> <span data-ttu-id="af3a7-114">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="af3a7-114">**In This Topic**</span></span>  
  
-   [<span data-ttu-id="af3a7-115">Procedimento de manutenção de disco agendado e realocação planejada</span><span class="sxs-lookup"><span data-stu-id="af3a7-115">Planned Relocation and Scheduled Disk Maintenance Procedure</span></span>](#Planned)  
  
-   [<span data-ttu-id="af3a7-116">Procedimento de recuperação de falha</span><span class="sxs-lookup"><span data-stu-id="af3a7-116">Failure Recovery Procedure</span></span>](#Failure)  
  
-   [<span data-ttu-id="af3a7-117">Movendo o banco de dados mestre</span><span class="sxs-lookup"><span data-stu-id="af3a7-117">Moving the master Database</span></span>](#master)  
  
-   [<span data-ttu-id="af3a7-118">Movendo o banco de dados de recursos</span><span class="sxs-lookup"><span data-stu-id="af3a7-118">Moving the Resource Database</span></span>](#Resource)  
  
-   [<span data-ttu-id="af3a7-119">Acompanhamento: depois de mover todos os bancos de dados do sistema</span><span class="sxs-lookup"><span data-stu-id="af3a7-119">Follow-up: After Moving All System Databases</span></span>](#Follow)  
  
-   [<span data-ttu-id="af3a7-120">Exemplos</span><span class="sxs-lookup"><span data-stu-id="af3a7-120">Examples</span></span>](#Examples)  
  
##  <a name="planned-relocation-and-scheduled-disk-maintenance-procedure"></a><a name="Planned"></a> <span data-ttu-id="af3a7-121">Realocação planejada e procedimento de manutenção de disco agendado</span><span class="sxs-lookup"><span data-stu-id="af3a7-121">Planned Relocation and Scheduled Disk Maintenance Procedure</span></span>  
 <span data-ttu-id="af3a7-122">Para mover um arquivo de dados de um banco de dados do sistema ou arquivo de log como parte de uma realocação planejada ou operação de manutenção, execute as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="af3a7-122">To move a system database data or log file as part of a planned relocation or scheduled maintenance operation, follow these steps.</span></span> <span data-ttu-id="af3a7-123">Este procedimento se aplica a todos os bancos de dados do sistema exceto os bancos de dados mestre e Recurso.</span><span class="sxs-lookup"><span data-stu-id="af3a7-123">This procedure applies to all system databases except the master and Resource databases.</span></span>  
  
1.  <span data-ttu-id="af3a7-124">Para cada arquivo a ser movido, execute a seguinte instrução.</span><span class="sxs-lookup"><span data-stu-id="af3a7-124">For each file to be moved, run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE ( NAME = logical_name , FILENAME = 'new_path\os_file_name' )  
    ```  
  
2.  <span data-ttu-id="af3a7-125">Pare a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou desligue o sistema para realizar a manutenção.</span><span class="sxs-lookup"><span data-stu-id="af3a7-125">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or shut down the system to perform maintenance.</span></span> <span data-ttu-id="af3a7-126">Para obter mais informações, consulte [Iniciar, parar, pausar, retomar e reiniciar os serviços SQL Server](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="af3a7-126">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
3.  <span data-ttu-id="af3a7-127">Mova o arquivo ou os arquivos para o novo local.</span><span class="sxs-lookup"><span data-stu-id="af3a7-127">Move the file or files to the new location.</span></span>  
  
4.  <span data-ttu-id="af3a7-128">Reinicialize a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou o servidor.</span><span class="sxs-lookup"><span data-stu-id="af3a7-128">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or the server.</span></span> <span data-ttu-id="af3a7-129">Para obter mais informações, consulte [Iniciar, parar, pausar, retomar e reiniciar os serviços SQL Server](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="af3a7-129">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
5.  <span data-ttu-id="af3a7-130">Execute a consulta a seguir para verificar se houve alteração no arquivo.</span><span class="sxs-lookup"><span data-stu-id="af3a7-130">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
 <span data-ttu-id="af3a7-131">Se o banco de dados msdb for movido e a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estiver configurada para [Database Mail](../database-mail/database-mail.md), execute estas etapas adicionais.</span><span class="sxs-lookup"><span data-stu-id="af3a7-131">If the msdb database is moved and the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured for [Database Mail](../database-mail/database-mail.md), complete these additional steps.</span></span>  
  
1.  <span data-ttu-id="af3a7-132">Verifique se o [!INCLUDE[ssSB](../../../includes/sssb-md.md)] está habilitado para o banco de dados msdb executando a consulta a seguir.</span><span class="sxs-lookup"><span data-stu-id="af3a7-132">Verify that [!INCLUDE[ssSB](../../../includes/sssb-md.md)] is enabled for the msdb database by running the following query.</span></span>  
  
    ```  
    SELECT is_broker_enabled   
    FROM sys.databases  
    WHERE name = N'msdb';  
    ```  
  
     <span data-ttu-id="af3a7-133">Para obter mais informações sobre como habilitar o [!INCLUDE[ssSB](../../../includes/sssb-md.md)], veja [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="af3a7-133">For more information about enabling [!INCLUDE[ssSB](../../../includes/sssb-md.md)], see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
2.  <span data-ttu-id="af3a7-134">Verifique se o Database Mail está funcionando, enviando um email de teste.</span><span class="sxs-lookup"><span data-stu-id="af3a7-134">Verify that Database Mail is working by sending a test mail.</span></span>  
  
##  <a name="failure-recovery-procedure"></a><a name="Failure"></a> <span data-ttu-id="af3a7-135">Falha no procedimento de recuperação</span><span class="sxs-lookup"><span data-stu-id="af3a7-135">Failure Recovery Procedure</span></span>  
 <span data-ttu-id="af3a7-136">Se um arquivo tiver de ser movido devido à falha de um hardware, siga estas etapas para realocar o arquivo para o novo local.</span><span class="sxs-lookup"><span data-stu-id="af3a7-136">If a file must be moved because of a hardware failure, follow these steps to relocate the file to a new location.</span></span> <span data-ttu-id="af3a7-137">Este procedimento se aplica a todos os bancos de dados do sistema exceto os bancos de dados mestre e Recurso.</span><span class="sxs-lookup"><span data-stu-id="af3a7-137">This procedure applies to all system databases except the master and Resource databases.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="af3a7-138">Se o banco de dados não puder ser inicializado, significa que ele está em modo de suspeição ou em estado não recuperado, e apenas os membros de função fixa sysadmin podem mover o arquivo.</span><span class="sxs-lookup"><span data-stu-id="af3a7-138">If the database cannot be started, that is it is in suspect mode or in an unrecovered state, only members of the sysadmin fixed role can move the file.</span></span>  
  
1.  <span data-ttu-id="af3a7-139">Interrompa a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , se tiver sido iniciado.</span><span class="sxs-lookup"><span data-stu-id="af3a7-139">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if it is started.</span></span>  
  
2.  <span data-ttu-id="af3a7-140">Inicie a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no modo somente recuperação mestre, inserindo um dos seguintes comandos no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="af3a7-140">Start the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in master-only recovery mode by entering one of the following commands at the command prompt.</span></span> <span data-ttu-id="af3a7-141">Os parâmetros especificados nestes comandos diferenciam maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="af3a7-141">The parameters specified in these commands are case sensitive.</span></span> <span data-ttu-id="af3a7-142">Os comandos falham quando os parâmetros não são especificados como demonstrado.</span><span class="sxs-lookup"><span data-stu-id="af3a7-142">The commands fail when the parameters are not specified as shown.</span></span>  
  
    -   <span data-ttu-id="af3a7-143">Para a instância padrão (MSSQLSERVER), execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="af3a7-143">For the default (MSSQLSERVER) instance, run the following command:</span></span>  
  
        ```  
        NET START MSSQLSERVER /f /T3608  
        ```  
  
    -   <span data-ttu-id="af3a7-144">Para uma instância nomeada, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="af3a7-144">For a named instance, run the following command:</span></span>  
  
        ```  
        NET START MSSQL$instancename /f /T3608  
        ```  
  
     <span data-ttu-id="af3a7-145">Para obter mais informações, consulte [Iniciar, parar, pausar, retomar e reiniciar os serviços SQL Server](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="af3a7-145">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
3.  <span data-ttu-id="af3a7-146">Para cada arquivo a ser movido, use comandos **sqlcmd** ou [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] para executar a instrução a seguir.</span><span class="sxs-lookup"><span data-stu-id="af3a7-146">For each file to be moved, use **sqlcmd** commands or [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] to run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE( NAME = logical_name , FILENAME = 'new_path\os_file_name' )  
    ```  
  
     <span data-ttu-id="af3a7-147">Para obter mais informações sobre como usar o utilitário **sqlcmd** , veja [Usar o Utilitário sqlcmd](../scripting/sqlcmd-use-the-utility.md).</span><span class="sxs-lookup"><span data-stu-id="af3a7-147">For more information about using the **sqlcmd** utility, see [Use the sqlcmd Utility](../scripting/sqlcmd-use-the-utility.md).</span></span>  
  
4.  <span data-ttu-id="af3a7-148">Saia do utilitário **sqlcmd** ou [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af3a7-148">Exit the **sqlcmd** utility or [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
5.  <span data-ttu-id="af3a7-149">Pare a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af3a7-149">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="af3a7-150">Por exemplo, execute `NET STOP MSSQLSERVER`.</span><span class="sxs-lookup"><span data-stu-id="af3a7-150">For example, run `NET STOP MSSQLSERVER`.</span></span>  
  
6.  <span data-ttu-id="af3a7-151">Mova o arquivo ou os arquivos para o novo local.</span><span class="sxs-lookup"><span data-stu-id="af3a7-151">Move the file or files to the new location.</span></span>  
  
7.  <span data-ttu-id="af3a7-152">Reinicie a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af3a7-152">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="af3a7-153">Por exemplo, execute `NET START MSSQLSERVER`.</span><span class="sxs-lookup"><span data-stu-id="af3a7-153">For example, run `NET START MSSQLSERVER`.</span></span>  
  
8.  <span data-ttu-id="af3a7-154">Execute a consulta a seguir para verificar se houve alteração no arquivo.</span><span class="sxs-lookup"><span data-stu-id="af3a7-154">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
##  <a name="moving-the-master-database"></a><a name="master"></a> <span data-ttu-id="af3a7-155">Movendo o banco de dados mestre</span><span class="sxs-lookup"><span data-stu-id="af3a7-155">Moving the master Database</span></span>  
 <span data-ttu-id="af3a7-156">Para mover o banco de dados mestre, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="af3a7-156">To move the master database, follow these steps.</span></span>  
  
1.  <span data-ttu-id="af3a7-157">Pelo menu **Iniciar** , aponte para **Todos os Programas**, aponte para **Microsoft SQL Server**, aponte para **Ferramentas de Configuração**e clique em **SQL Server Configuration Manager**.</span><span class="sxs-lookup"><span data-stu-id="af3a7-157">From the **Start** menu, point to **All Programs**, point to **Microsoft SQL Server**, point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="af3a7-158">No nó **Serviços do SQL Server** , clique com o botão direito do mouse na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (por exemplo, **SQL Server [MSSQLSERVER]** ) e escolha **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="af3a7-158">In the **SQL Server Services** node, right-click the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (for example, **SQL Server (MSSQLSERVER)**) and choose **Properties**.</span></span>  
  
3.  <span data-ttu-id="af3a7-159">Na caixa de diálogo \*\*Propriedades do SQL Server ( \*\*\*nome_instância \***)** , clique na guia **Parâmetros de Inicialização** .</span><span class="sxs-lookup"><span data-stu-id="af3a7-159">In the **SQL Server (***instance_name***) Properties** dialog box, click the **Startup Parameters** tab.</span></span>  
  
4.  <span data-ttu-id="af3a7-160">Na caixa **Parâmetros existentes**, selecione o parâmetro -d para mover o arquivo de dados mestre.</span><span class="sxs-lookup"><span data-stu-id="af3a7-160">In the **Existing parameters** box, select the -d parameter to move the master data file.</span></span> <span data-ttu-id="af3a7-161">Clique em **Atualizar** para salvar a alteração.</span><span class="sxs-lookup"><span data-stu-id="af3a7-161">Click **Update** to save the change.</span></span>  
  
     <span data-ttu-id="af3a7-162">Na caixa **Especificar um parâmetro de inicialização** , altere o parâmetro para o novo caminho do banco de dados mestre.</span><span class="sxs-lookup"><span data-stu-id="af3a7-162">In the **Specify a startup parameter** box, change the parameter to the new path of the master database.</span></span>  
  
5.  <span data-ttu-id="af3a7-163">Na caixa **Parâmetros existentes**, selecione o parâmetro -l para mover o arquivo de log mestre.</span><span class="sxs-lookup"><span data-stu-id="af3a7-163">In the **Existing parameters** box, select the -l parameter to move the master log file.</span></span> <span data-ttu-id="af3a7-164">Clique em **Atualizar** para salvar a alteração.</span><span class="sxs-lookup"><span data-stu-id="af3a7-164">Click **Update** to save the change.</span></span>  
  
     <span data-ttu-id="af3a7-165">Na caixa **Especificar um parâmetro de inicialização** , altere o parâmetro para o novo caminho do banco de dados mestre.</span><span class="sxs-lookup"><span data-stu-id="af3a7-165">In the **Specify a startup parameter** box, change the parameter to the new path of the master database.</span></span>  
  
     <span data-ttu-id="af3a7-166">O valor do parâmetro para o arquivo de dados deve seguir o parâmetro `-d` e o valor para o arquivo de log deve seguir o parâmetro `-l` .</span><span class="sxs-lookup"><span data-stu-id="af3a7-166">The parameter value for the data file must follow the `-d` parameter and the value for the log file must follow the `-l` parameter.</span></span> <span data-ttu-id="af3a7-167">O exemplo a seguir mostra os valores de parâmetro da localização padrão do arquivo de dados mestre.</span><span class="sxs-lookup"><span data-stu-id="af3a7-167">The following example shows the parameter values for the default location of the master data file.</span></span>  
  
     `-dC:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\master.mdf`  
  
     `-lC:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\mastlog.ldf`  
  
     <span data-ttu-id="af3a7-168">Se a realocação planejada para o arquivo de dados mestre for `E:\SQLData`, os valores de parâmetros serão alterados da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="af3a7-168">If the planned relocation for the master data file is `E:\SQLData`, the parameter values would be changed as follows:</span></span>  
  
     `-dE:\SQLData\master.mdf`  
  
     `-lE:\SQLData\mastlog.ldf`  
  
6.  <span data-ttu-id="af3a7-169">Interrompa a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clicando com o botão direito do mouse no nome da instância e escolhendo **Interromper**.</span><span class="sxs-lookup"><span data-stu-id="af3a7-169">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by right-clicking the instance name and choosing **Stop**.</span></span>  
  
7.  <span data-ttu-id="af3a7-170">Mova os arquivos do master.mdf e mastlog.ldf para o local novo.</span><span class="sxs-lookup"><span data-stu-id="af3a7-170">Move the master.mdf and mastlog.ldf files to the new location.</span></span>  
  
8.  <span data-ttu-id="af3a7-171">Reinicie a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af3a7-171">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
9. <span data-ttu-id="af3a7-172">Verifique a alteração do arquivo para o banco de dados mestre executando a consulta a seguir.</span><span class="sxs-lookup"><span data-stu-id="af3a7-172">Verify the file change for the master database by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID('master');  
    GO  
    ```  
  
##  <a name="moving-the-resource-database"></a><a name="Resource"></a> <span data-ttu-id="af3a7-173">Movendo o banco de dados de recursos</span><span class="sxs-lookup"><span data-stu-id="af3a7-173">Moving the Resource Database</span></span>  
 <span data-ttu-id="af3a7-174">A localização do banco de dados de recursos é \<*drive*>:\Program Files\Microsoft SQL Server\MSSQL\<version>.\<*instance_name*>\MSSQL\Binn\\.</span><span class="sxs-lookup"><span data-stu-id="af3a7-174">The location of the Resource database is \<*drive*>:\Program Files\Microsoft SQL Server\MSSQL\<version>.\<*instance_name*>\MSSQL\Binn\\.</span></span> <span data-ttu-id="af3a7-175">O banco de dados não pode ser movido.</span><span class="sxs-lookup"><span data-stu-id="af3a7-175">The database cannot be moved.</span></span>  
  
##  <a name="follow-up-after-moving-all-system-databases"></a><a name="Follow"></a> <span data-ttu-id="af3a7-176">Acompanhamento: depois de mover todos os bancos de dados do sistema</span><span class="sxs-lookup"><span data-stu-id="af3a7-176">Follow-up: After Moving All System Databases</span></span>  
 <span data-ttu-id="af3a7-177">Se você moveu todos os bancos de dados do sistema para uma nova unidade ou volume ou para outro servidor com uma letra de unidade diferente, faça as atualizações a seguir.</span><span class="sxs-lookup"><span data-stu-id="af3a7-177">If you have moved all of the system databases to a new drive or volume or to another server with a different drive letter, make the following updates.</span></span>  
  
-   <span data-ttu-id="af3a7-178">Altere o caminho do log do SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="af3a7-178">Change the SQL Server Agent log path.</span></span> <span data-ttu-id="af3a7-179">Se você não atualizar este caminho, o SQL Server Agent não iniciará.</span><span class="sxs-lookup"><span data-stu-id="af3a7-179">If you do not update this path, SQL Server Agent will fail to start.</span></span>  
  
-   <span data-ttu-id="af3a7-180">Altere o local padrão do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="af3a7-180">Change the database default location.</span></span> <span data-ttu-id="af3a7-181">Criar um novo banco de dados pode falhar se a letra da unidade e do caminho especificados como a localização padrão não existir.</span><span class="sxs-lookup"><span data-stu-id="af3a7-181">Creating a new database may fail if the drive letter and path specified as the default location do not exist.</span></span>  
  
#### <a name="change-the-sql-server-agent-log-path"></a><span data-ttu-id="af3a7-182">Altere o caminho do log do SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="af3a7-182">Change the SQL Server Agent Log Path</span></span>  
  
1.  <span data-ttu-id="af3a7-183">No SQL Server Management Studio, em Pesquisador de Objetos, expanda **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="af3a7-183">From SQL Server Management Studio, in Object Explorer, expand **SQL Server Agent**.</span></span>  
  
2.  <span data-ttu-id="af3a7-184">Clique com o botão direito do mouse em **Logs de Erros** e clique em **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="af3a7-184">Right-click **Error Logs** and click **Configure**.</span></span>  
  
3.  <span data-ttu-id="af3a7-185">Na caixa de diálogo **Configurar Logs de Erros do SQL Server Agent** , especifique o novo local do arquivo SQLAGENT.OUT.</span><span class="sxs-lookup"><span data-stu-id="af3a7-185">In the **Configure SQL Server Agent Error Logs** dialog box, specify the new location of the SQLAGENT.OUT file.</span></span> <span data-ttu-id="af3a7-186">O local padrão é C:\Program Files\Microsoft SQL Server\MSSQL12. <instance_name> \MSSQL\Log \\ .</span><span class="sxs-lookup"><span data-stu-id="af3a7-186">The default location is C:\Program Files\Microsoft SQL Server\MSSQL12.<instance_name>\MSSQL\Log\\.</span></span>  
  
#### <a name="change-the-database-default-location"></a><span data-ttu-id="af3a7-187">Altere o local padrão do banco de dados</span><span class="sxs-lookup"><span data-stu-id="af3a7-187">Change the database default location</span></span>  
  
1.  <span data-ttu-id="af3a7-188">No SQL Server Management Studio, em Pesquisador de Objetos, clique com o botão direito do mouse no servidor do SQL Server e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="af3a7-188">From SQL Server Management Studio, in Object Explorer, right-click the SQL Server server and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="af3a7-189">Na caixa de diálogo **Propriedades do Servidor** da caixa de diálogo, selecione **Configurações de Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="af3a7-189">In the **Server Properties** dialog box, select **Database Settings**.</span></span>  
  
3.  <span data-ttu-id="af3a7-190">Em **Locais padrão de banco de dados**, navegue até o novo local para os arquivos de dados e log.</span><span class="sxs-lookup"><span data-stu-id="af3a7-190">Under **Database Default Locations**, browse to the new location for both the data and log files.</span></span>  
  
4.  <span data-ttu-id="af3a7-191">Pare e inicie o serviço do SQL Server para concluir a alteração.</span><span class="sxs-lookup"><span data-stu-id="af3a7-191">Stop and start the SQL Server service to complete the change.</span></span>  
  
##  <a name="examples"></a><a name="Examples"></a> <span data-ttu-id="af3a7-192">Exemplos</span><span class="sxs-lookup"><span data-stu-id="af3a7-192">Examples</span></span>  
  
### <a name="a-moving-the-tempdb-database"></a><span data-ttu-id="af3a7-193">a.</span><span class="sxs-lookup"><span data-stu-id="af3a7-193">A.</span></span> <span data-ttu-id="af3a7-194">Movendo o banco de dados tempdb</span><span class="sxs-lookup"><span data-stu-id="af3a7-194">Moving the tempdb database</span></span>  
 <span data-ttu-id="af3a7-195">O seguinte exemplo move os arquivos de log e de dados `tempdb` para um novo local como parte de uma realocação planejada.</span><span class="sxs-lookup"><span data-stu-id="af3a7-195">The following example moves the `tempdb` data and log files to a new location as part of a planned relocation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="af3a7-196">Como o tempdb é recriado a cada vez que a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é iniciada, você não precisa mover fisicamente os arquivos de log e de dados.</span><span class="sxs-lookup"><span data-stu-id="af3a7-196">Because tempdb is re-created each time the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started, you do not have to physically move the data and log files.</span></span> <span data-ttu-id="af3a7-197">Os arquivos são criados no local novo quando o serviço é reiniciado na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="af3a7-197">The files are created in the new location when the service is restarted in step 3.</span></span> <span data-ttu-id="af3a7-198">Até que o serviço seja reiniciado, o tempdb continua usando os arquivos de dados e de log no local existente.</span><span class="sxs-lookup"><span data-stu-id="af3a7-198">Until the service is restarted, tempdb continues to use the data and log files in existing location.</span></span>  
  
1.  <span data-ttu-id="af3a7-199">Determine os nomes de arquivo lógicos do banco de dados `tempdb` e o seu local atual no disco.</span><span class="sxs-lookup"><span data-stu-id="af3a7-199">Determine the logical file names of the `tempdb` database and their current location on the disk.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'tempdb');  
    GO  
    ```  
  
2.  <span data-ttu-id="af3a7-200">Altere o local de cada arquivo usando `ALTER DATABASE`.</span><span class="sxs-lookup"><span data-stu-id="af3a7-200">Change the location of each file by using `ALTER DATABASE`.</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE tempdb   
    MODIFY FILE (NAME = tempdev, FILENAME = 'E:\SQLData\tempdb.mdf');  
    GO  
    ALTER DATABASE tempdb   
    MODIFY FILE (NAME = templog, FILENAME = 'F:\SQLLog\templog.ldf');  
    GO  
    ```  
  
3.  <span data-ttu-id="af3a7-201">Pare e reinicie a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af3a7-201">Stop and restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
4.  <span data-ttu-id="af3a7-202">Verifique a alteração do arquivo.</span><span class="sxs-lookup"><span data-stu-id="af3a7-202">Verify the file change.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'tempdb');  
    ```  
  
5.  <span data-ttu-id="af3a7-203">Exclua os arquivos `tempdb.mdf` e `templog.ldf` do local original.</span><span class="sxs-lookup"><span data-stu-id="af3a7-203">Delete the `tempdb.mdf` and `templog.ldf` files from the original location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af3a7-204">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="af3a7-204">See Also</span></span>  
 <span data-ttu-id="af3a7-205">[Banco de dados de recursos](resource-database.md) </span><span class="sxs-lookup"><span data-stu-id="af3a7-205">[Resource Database](resource-database.md) </span></span>  
 <span data-ttu-id="af3a7-206">[Banco de dados tempdb](tempdb-database.md) </span><span class="sxs-lookup"><span data-stu-id="af3a7-206">[tempdb Database](tempdb-database.md) </span></span>  
 <span data-ttu-id="af3a7-207">[Banco de dados mestre](master-database.md) </span><span class="sxs-lookup"><span data-stu-id="af3a7-207">[master Database](master-database.md) </span></span>  
 <span data-ttu-id="af3a7-208">[Banco de dados msdb](msdb-database.md) </span><span class="sxs-lookup"><span data-stu-id="af3a7-208">[msdb Database](msdb-database.md) </span></span>  
 <span data-ttu-id="af3a7-209">[Banco de dados modelo](model-database.md) </span><span class="sxs-lookup"><span data-stu-id="af3a7-209">[model Database](model-database.md) </span></span>  
 <span data-ttu-id="af3a7-210">[Mover bancos de dados de usuário](move-user-databases.md) </span><span class="sxs-lookup"><span data-stu-id="af3a7-210">[Move User Databases](move-user-databases.md) </span></span>  
 <span data-ttu-id="af3a7-211">[Mover arquivos de banco de dados](move-database-files.md) </span><span class="sxs-lookup"><span data-stu-id="af3a7-211">[Move Database Files](move-database-files.md) </span></span>  
 <span data-ttu-id="af3a7-212">[Iniciar, parar, pausar, retomar, reiniciar o mecanismo de banco de dados, o SQL Server Agent ou o serviço SQL Server Browser](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md) </span><span class="sxs-lookup"><span data-stu-id="af3a7-212">[Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md) </span></span>  
 <span data-ttu-id="af3a7-213">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="af3a7-213">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="af3a7-214">Recompilar bancos de dados do sistema</span><span class="sxs-lookup"><span data-stu-id="af3a7-214">Rebuild System Databases</span></span>](system-databases.md)  
  
  
