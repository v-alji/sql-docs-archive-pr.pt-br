---
title: Criar um backup completo do banco de dados (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backing up databases [SQL Server], full backups
- backing up databases [SQL Server], SQL Server Management Studio
- backups [SQL Server], creating
- database backups [SQL Server], SQL Server Management Studio
ms.assetid: 586561fc-dfbb-4842-84f8-204a9100a534
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f406464680a1669133dc87bdfb231c644d33fbdb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685194"
---
# <a name="create-a-full-database-backup-sql-server"></a><span data-ttu-id="b49b2-102">Criar um backup completo de banco de dados (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b49b2-102">Create a Full Database Backup (SQL Server)</span></span>
  <span data-ttu-id="b49b2-103">Este tópico descreve como criar um backup de banco de dados completo no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], o [!INCLUDE[tsql](../../includes/tsql-md.md)]ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b49b2-103">This topic describes how to create a full database backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b49b2-104">Para obter informações sobre SQL Server Backup para o serviço de armazenamento de BLOBs do Azure, consulte [SQL Server Backup e restauração com o serviço de armazenamento de BLOBs do Azure](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="b49b2-104">For information on SQL Server backup to the Azure Blob storage service, see, [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span></span>  
  
 <span data-ttu-id="b49b2-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="b49b2-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b49b2-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="b49b2-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b49b2-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="b49b2-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b49b2-108">Recomendações</span><span class="sxs-lookup"><span data-stu-id="b49b2-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="b49b2-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="b49b2-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b49b2-110">**Para criar um backup de banco de dados completo usando:**</span><span class="sxs-lookup"><span data-stu-id="b49b2-110">**To create a full database backup, using:**</span></span>  
  
     [<span data-ttu-id="b49b2-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b49b2-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b49b2-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b49b2-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="b49b2-113">PowerShell</span><span class="sxs-lookup"><span data-stu-id="b49b2-113">PowerShell</span></span>](#PowerShellProcedure)  
  
-   [<span data-ttu-id="b49b2-114">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="b49b2-114">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b49b2-115">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="b49b2-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b49b2-116">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="b49b2-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b49b2-117">A instrução BACKUP não é permitida em uma transação explícita ou implícita.</span><span class="sxs-lookup"><span data-stu-id="b49b2-117">The BACKUP statement is not allowed in an explicit or implicit transaction.</span></span>  
  
-   <span data-ttu-id="b49b2-118">Os backups criados por uma versão mais recente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não podem ser restaurados em versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b49b2-118">Backups that are created by more recent version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot be restored in earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="b49b2-119">Para obter mais informações, veja [Visão geral do backup &#40;SQL Server&#41;](backup-overview-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b49b2-119">For more information, see [Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="b49b2-120">Recomendações</span><span class="sxs-lookup"><span data-stu-id="b49b2-120">Recommendations</span></span>  
  
-   <span data-ttu-id="b49b2-121">À medida que um banco de dados aumenta, os backups completos de banco de dados levam mais tempo para serem concluídos e exigem mais espaço de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="b49b2-121">As a database increases in size full database backups take more time to finish and require more storage space.</span></span> <span data-ttu-id="b49b2-122">Portanto, para um banco de dados grande, convém complementar um backup de banco de dados completo com uma série de *backups de bancos de dados diferenciais*.</span><span class="sxs-lookup"><span data-stu-id="b49b2-122">Therefore, for a large database, you might want to supplement a full database backup with a series of *differential database backups*.</span></span> <span data-ttu-id="b49b2-123">Para obter mais informações, veja [Backups diferenciais &#40;SQL Server&#41;](differential-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b49b2-123">For more information, see [Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md).</span></span>  
  
-   <span data-ttu-id="b49b2-124">Você pode estimar o tamanho de um backup de banco de dados completo usando o procedimento armazenado do sistema [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="b49b2-124">You can estimate the size of a full database backup by using the [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) system stored procedure.</span></span>  
  
-   <span data-ttu-id="b49b2-125">Por padrão, toda operação de backup bem-sucedida acrescenta uma entrada ao log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e ao log de eventos do sistema.</span><span class="sxs-lookup"><span data-stu-id="b49b2-125">By default, every successful backup operation adds an entry in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and in the system event log.</span></span> <span data-ttu-id="b49b2-126">Se você fizer backup do log com muita frequência, essas mensagens de êxito se acumularão muito rapidamente, resultando em logs de erros imensos que podem dificultar a localização de outras mensagens.</span><span class="sxs-lookup"><span data-stu-id="b49b2-126">If back up the log very frequently, these success messages accumulate quickly, resulting in huge error logs that can make finding other messages difficult.</span></span> <span data-ttu-id="b49b2-127">Em tais situações, você pode suprimir essas entradas de log usando o sinalizador de rastreamento 3226, caso nenhum dos seus scripts dependa dessas entradas.</span><span class="sxs-lookup"><span data-stu-id="b49b2-127">In such cases you can suppress these log entries by using trace flag 3226 if none of your scripts depend on those entries.</span></span> <span data-ttu-id="b49b2-128">Para obter mais informações, veja, [Sinalizadores de rastreamento &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b49b2-128">For more information, see [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b49b2-129">Segurança</span><span class="sxs-lookup"><span data-stu-id="b49b2-129">Security</span></span>  
 <span data-ttu-id="b49b2-130">TRUSTWORTHY é definido como OFF em um backup de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b49b2-130">TRUSTWORTHY is set to OFF on a database backup.</span></span> <span data-ttu-id="b49b2-131">Para obter informações sobre como definir TRUSTWORTHY como ON, veja [Opções do ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="b49b2-131">For information about how to set TRUSTWORTHY to ON, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
 <span data-ttu-id="b49b2-132">A partir do [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], as opções `PASSWORD` e `MEDIAPASSWORD` foram descontinuadas para a criação de backups.</span><span class="sxs-lookup"><span data-stu-id="b49b2-132">Beginning with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] the `PASSWORD` and `MEDIAPASSWORD` options are discontinued for creating backups.</span></span> <span data-ttu-id="b49b2-133">Você ainda poderá restaurar os backups criados com senhas.</span><span class="sxs-lookup"><span data-stu-id="b49b2-133">You can still restore backups created with passwords.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b49b2-134">Permissões</span><span class="sxs-lookup"><span data-stu-id="b49b2-134">Permissions</span></span>  
 <span data-ttu-id="b49b2-135">As permissões BACKUP DATABASE e BACKUP LOG usam como padrão os membros da função de servidor fixa **sysadmin** e as funções de banco de dados fixas **db_owner** e **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="b49b2-135">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="b49b2-136">Os problemas de propriedade e permissão no arquivo físico do dispositivo de backup podem interferir em uma operação de backup.</span><span class="sxs-lookup"><span data-stu-id="b49b2-136">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b49b2-137">deve ser capaz de ler e gravar no dispositivo; a conta sob a qual o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executa deve ter permissões de gravação.</span><span class="sxs-lookup"><span data-stu-id="b49b2-137">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="b49b2-138">No entanto, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), que adiciona uma entrada para um dispositivo de backup nas tabelas do sistema, não verifica permissões de acesso a arquivos.</span><span class="sxs-lookup"><span data-stu-id="b49b2-138">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="b49b2-139">Esses problemas no arquivo físico do dispositivo de backup podem não aparecer até que o recurso físico seja acessado quando o backup ou restauração é tentado.</span><span class="sxs-lookup"><span data-stu-id="b49b2-139">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b49b2-140">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b49b2-140">Using SQL Server Management Studio</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b49b2-141"> Ao especificar uma tarefa de backup usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], é possível gerar o script [!INCLUDE[tsql](../../includes/tsql-md.md)] [BACKUP](/sql/t-sql/statements/backup-transact-sql) correspondente, clicando no botão **Script** e selecionando um destino para o script.</span><span class="sxs-lookup"><span data-stu-id="b49b2-141">When you specify a back up task by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you can generate the corresponding [!INCLUDE[tsql](../../includes/tsql-md.md)] [BACKUP](/sql/t-sql/statements/backup-transact-sql) script by clicking the **Script** button and selecting a script destination.</span></span>  
  
#### <a name="to-back-up-a-database"></a><span data-ttu-id="b49b2-142">Para fazer o backup de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="b49b2-142">To back up a database</span></span>  
  
1.  <span data-ttu-id="b49b2-143">Depois de se conectar à instância apropriada do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], em Pesquisador de Objetos, clique no nome do servidor para expandir a árvore do servidor.</span><span class="sxs-lookup"><span data-stu-id="b49b2-143">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="b49b2-144">Expanda **Bancos de Dados**e, dependendo do banco de dados, selecione um banco de usuário ou expanda **Bancos de Dados do Sistema** e selecione um banco do sistema.</span><span class="sxs-lookup"><span data-stu-id="b49b2-144">Expand **Databases**, and depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="b49b2-145">Clique com o botão direito do mouse no banco de dados, aponte para **Tarefas**e clique em **Backup**.</span><span class="sxs-lookup"><span data-stu-id="b49b2-145">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="b49b2-146">Será exibida a caixa de diálogo **Backup de Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="b49b2-146">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="b49b2-147">Na `Database` caixa de listagem, verifique o nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b49b2-147">In the `Database` list box, verify the database name.</span></span> <span data-ttu-id="b49b2-148">Você pode, como opção, selecionar um banco de dados diferente da lista.</span><span class="sxs-lookup"><span data-stu-id="b49b2-148">You can optionally select a different database from the list.</span></span>  
  
5.  <span data-ttu-id="b49b2-149">Você pode executar um backup de banco de dados para qualquer modelo de recuperação (**FULL**, **BULK_LOGGED**ou **SIMPLE**).</span><span class="sxs-lookup"><span data-stu-id="b49b2-149">You can perform a database backup for any recovery model (**FULL**, **BULK_LOGGED**, or **SIMPLE**).</span></span>  
  
6.  <span data-ttu-id="b49b2-150">Na caixa de listagem **Tipo de backup** , selecione **Completo**.</span><span class="sxs-lookup"><span data-stu-id="b49b2-150">In the **Backup type** list box, select **Full**.</span></span>  
  
     <span data-ttu-id="b49b2-151">Observe que depois de criar um backup de banco de dados completo, é possível criar um backup de banco de dados diferencial. Para obter mais informações, consulte [Criar um backup diferencial de banco de dados &#40;SQL Server&#41;](create-a-differential-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b49b2-151">Note that after creating a full database backup, you can create a differential database backup; for more information, see [Create a Differential Database Backup &#40;SQL Server&#41;](create-a-differential-database-backup-sql-server.md).</span></span>  
  
7.  <span data-ttu-id="b49b2-152">Opcionalmente, você pode selecionar **Copiar Somente Backup** para criar um backup somente cópia.</span><span class="sxs-lookup"><span data-stu-id="b49b2-152">Optionally, you can select **Copy Only Backup** to create a copy-only backup.</span></span> <span data-ttu-id="b49b2-153">Um *backup somente cópia* é um backup do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que não depende da sequência de backups convencionais do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b49b2-153">A *copy-only backup* is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup that is independent of the sequence of conventional [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span> <span data-ttu-id="b49b2-154">Para obter mais informações, veja [Backups somente cópia &#40;SQL Server&#41;](copy-only-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b49b2-154">For more information, see [Copy-Only Backups &#40;SQL Server&#41;](copy-only-backups-sql-server.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b49b2-155">Quando a opção **Diferencial** está selecionada, você não pode criar um backup somente cópia.</span><span class="sxs-lookup"><span data-stu-id="b49b2-155">When the **Differential** option is selected, you cannot create a copy-only backup.</span></span>  
  
8.  <span data-ttu-id="b49b2-156">Para **componente de backup**, clique em `Database` .</span><span class="sxs-lookup"><span data-stu-id="b49b2-156">For **Backup component**, click `Database`.</span></span>  
  
9. <span data-ttu-id="b49b2-157">Aceite o nome do conjunto de backup padrão sugerido na caixa de texto **Nome** ou digite um nome diferente para o conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="b49b2-157">Either accept the default backup set name suggested in the **Name** text box, or enter a different name for the backup set.</span></span>  
  
10. <span data-ttu-id="b49b2-158">Opcionalmente, na caixa de texto **Descrição** , digite uma descrição do conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="b49b2-158">Optionally, in the **Description** text box, enter a description of the backup set.</span></span>  
  
11. <span data-ttu-id="b49b2-159">Escolha o tipo do destino do backup e clique em **Disco**, **Fita** ou **URL**.</span><span class="sxs-lookup"><span data-stu-id="b49b2-159">Choose the type of backup destination by clicking **Disk**, **Tape** or **URL**.</span></span> <span data-ttu-id="b49b2-160">Para selecionar os caminhos de até 64 unidades de disco ou fita que contêm um único conjunto de mídia, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b49b2-160">To select the paths of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span> <span data-ttu-id="b49b2-161">Os caminhos selecionados são exibidos na caixa de listagem **Backup** .</span><span class="sxs-lookup"><span data-stu-id="b49b2-161">The selected paths are displayed in the **Backup to** list box.</span></span>  
  
     <span data-ttu-id="b49b2-162">Para remover um destino de backup, selecione-o e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="b49b2-162">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="b49b2-163">Para exibir o conteúdo de um destino de backup, selecione-o e clique em **Conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="b49b2-163">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
12. <span data-ttu-id="b49b2-164">Para exibir ou selecionar as opções de mídia, clique em **Opções de Mídia** no painel **Selecionar uma página** .</span><span class="sxs-lookup"><span data-stu-id="b49b2-164">To view or select the media options, click **Media Options** in the **Select a page** pane.</span></span>  
  
13. <span data-ttu-id="b49b2-165">Selecione uma opção **Substituir Mídia** , com um clique em uma das opções a seguir:</span><span class="sxs-lookup"><span data-stu-id="b49b2-165">Select an **Overwrite Media** option, by clicking one of the following:</span></span>  
  
    -   <span data-ttu-id="b49b2-166">**Fazer backup no conjunto de mídias existente**</span><span class="sxs-lookup"><span data-stu-id="b49b2-166">**Back up to the existing media set**</span></span>  
  
         <span data-ttu-id="b49b2-167">Para essa opção, clique em **Anexar ao conjunto de backup existente** ou **Substituir todos os conjuntos de backup existentes**.</span><span class="sxs-lookup"><span data-stu-id="b49b2-167">For this option, click either **Append to the existing backup set** or **Overwrite all existing backup sets**.</span></span> <span data-ttu-id="b49b2-168">Para obter mais informações, veja [Conjuntos de mídias, famílias de mídia e conjuntos de backup &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b49b2-168">For more information, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
         <span data-ttu-id="b49b2-169">Opcionalmente, selecione **Verificar nome do conjunto de mídias e validade do conjunto de backup** para que a operação de backup verifique a data e a hora em que o conjunto de mídias e de backup expiram.</span><span class="sxs-lookup"><span data-stu-id="b49b2-169">Optionally, select **Check media set name and backup set expiration** to cause the backup operation to verify the date and time at which the media set and backup set expire.</span></span>  
  
         <span data-ttu-id="b49b2-170">Como opção, digite um nome na caixa de texto **Nome do conjunto de mídias** .</span><span class="sxs-lookup"><span data-stu-id="b49b2-170">Optionally, enter a name in the **Media set name** text box.</span></span> <span data-ttu-id="b49b2-171">Se nenhum nome for especificado, um conjunto de mídias com um nome em branco será criado.</span><span class="sxs-lookup"><span data-stu-id="b49b2-171">If no name is specified, a media set with a blank name is created.</span></span> <span data-ttu-id="b49b2-172">Se você especificar um nome de conjunto de mídias, a mídia (fita ou disco) é verificada para ver se o nome real corresponde ao nome digitado.</span><span class="sxs-lookup"><span data-stu-id="b49b2-172">If you specify a media set name, the media (tape or disk) is checked to see whether the actual name matches the name you enter here.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="b49b2-173">Essa opção será desabilitada se a opção **URL** for selecionada como o destino de backup na página **General** .</span><span class="sxs-lookup"><span data-stu-id="b49b2-173">This option is disabled if you selected **URL** as the backup destination in the **General** page.</span></span> <span data-ttu-id="b49b2-174">Para saber mais, confira [Fazer backup do banco de dados &#40;página Opções de Mídia&#41;](back-up-database-media-options-page.md)</span><span class="sxs-lookup"><span data-stu-id="b49b2-174">For more information, see [Back Up Database &#40;Media Options Page&#41;](back-up-database-media-options-page.md)</span></span>  
        >   
        >  <span data-ttu-id="b49b2-175">Se você planeja usar criptografia, não selecione essa opção.</span><span class="sxs-lookup"><span data-stu-id="b49b2-175">If you plan to use encryption, do not select this option.</span></span> <span data-ttu-id="b49b2-176">Se você selecionar esta opção, as opções de criptografia na página **Opções de Backup** serão desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="b49b2-176">If you select this option, the encryption options in the **Backup Options** page will be disabled.</span></span> <span data-ttu-id="b49b2-177">A criptografia não tem suporte ao anexar ao conjunto de backup existente.</span><span class="sxs-lookup"><span data-stu-id="b49b2-177">Encryption is not supported when appending to the existing backup set.</span></span>  
  
    -   <span data-ttu-id="b49b2-178">**Fazer backup em um novo conjunto de mídias e apagar todos os conjuntos de backup existentes**</span><span class="sxs-lookup"><span data-stu-id="b49b2-178">**Back up to a new media set, and erase all existing backup sets**</span></span>  
  
         <span data-ttu-id="b49b2-179">Para essa opção, digite um nome na caixa de texto **Nome do novo conjunto de mídias** e, opcionalmente, descreva o conjunto de mídias na caixa de texto **Descrição do novo conjunto de mídias** .</span><span class="sxs-lookup"><span data-stu-id="b49b2-179">For this option, enter a name in the **New media set name** text box, and, optionally, describe the media set in the **New media set description** text box.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="b49b2-180">Essa opção será desabilitada se a opção **URL** for selecionada na página **General** .</span><span class="sxs-lookup"><span data-stu-id="b49b2-180">This option is disabled if you selected **URL** in the **General** page.</span></span> <span data-ttu-id="b49b2-181">Não há suporte para essas ações durante o backup no armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="b49b2-181">These actions are not supported when backing up to Azure storage.</span></span>  
  
14. <span data-ttu-id="b49b2-182">Na seção **confiabilidade** , marque opcionalmente:</span><span class="sxs-lookup"><span data-stu-id="b49b2-182">In the **Reliability** section, optionally check:</span></span>  
  
    -   <span data-ttu-id="b49b2-183">**Verificar backup quando concluído**</span><span class="sxs-lookup"><span data-stu-id="b49b2-183">**Verify backup when finished**.</span></span>  
  
    -   <span data-ttu-id="b49b2-184">**Executar soma de verificação antes de gravar na mídia**e, como opção, **Continuar com erro da soma de verificação**.</span><span class="sxs-lookup"><span data-stu-id="b49b2-184">**Perform checksum before writing to media**, and, optionally, **Continue on checksum error**.</span></span> <span data-ttu-id="b49b2-185">Para obter informações sobre somas de verificação, veja [Erros de mídia possíveis durante backup e restauração &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b49b2-185">For information on checksums, see [Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span></span>  
  
15. <span data-ttu-id="b49b2-186">Se o backup estiver sendo feito em uma unidade de fita (conforme especificado na seção **Destino** da página **Geral** ), a opção **Descarregar a fita após o backup** estará ativa.</span><span class="sxs-lookup"><span data-stu-id="b49b2-186">If you are backing up to a tape drive (as specified in the **Destination** section of the **General** page), the **Unload the tape after backup** option is active.</span></span> <span data-ttu-id="b49b2-187">Clicar nessa opção ativa a opção **Rebobinar a fita antes de descarregar** .</span><span class="sxs-lookup"><span data-stu-id="b49b2-187">Clicking this option activates the **Rewind the tape before unloading** option.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b49b2-188">As opções na seção **Log de transações** estarão inativos exceto se o backup estiver sendo feito em um log de transações (como especificado na seção **Tipo de backup** da página **Geral** ).</span><span class="sxs-lookup"><span data-stu-id="b49b2-188">The options in the **Transaction log** section are inactive unless you are backing up a transaction log (as specified in the **Backup type** section of the **General** page).</span></span>  
  
16. <span data-ttu-id="b49b2-189">Para exibir ou selecionar as opções de backup, clique em **Opções de Backup** no painel **Selecionar uma página** .</span><span class="sxs-lookup"><span data-stu-id="b49b2-189">To view or select the backup options, click **Backup Options** in the **Select a page** pane.</span></span>  
  
17. <span data-ttu-id="b49b2-190">Especifique quando o conjunto de backup irá expirar e pode ser substituído sem ignorar explicitamente a verificação dos dados de expiração:</span><span class="sxs-lookup"><span data-stu-id="b49b2-190">Specify when the backup set will expire and can be overwritten without explicitly skipping verification of the expiration data:</span></span>  
  
    -   <span data-ttu-id="b49b2-191">Para que o conjunto de backup expire depois de um número específico de dias, clique em **Depois** (a opção padrão) e digite quantos dias depois da criação do conjunto ele deve expirar.</span><span class="sxs-lookup"><span data-stu-id="b49b2-191">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="b49b2-192">Esse valor pode ser de 0 a 99999 dias; 0 dia significa que o conjunto de backup nunca vai expirar.</span><span class="sxs-lookup"><span data-stu-id="b49b2-192">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="b49b2-193">O valor padrão é definido na opção **Retenção de mídia de backup padrão (em dias)** da caixa de diálogo **Propriedades do Servidor** (Página Configurações de Banco de Dados).</span><span class="sxs-lookup"><span data-stu-id="b49b2-193">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (Database Settings Page).</span></span> <span data-ttu-id="b49b2-194">Para acessar, clique com o botão direito do mouse no nome do servidor em Pesquisador de Objetos e selecione propriedades. Depois, selecione a página **Configurações de Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="b49b2-194">To access this, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="b49b2-195">Para que o conjunto de backup expire em uma data específica, clique no campo **Em**e digite a data de expiração do conjunto.</span><span class="sxs-lookup"><span data-stu-id="b49b2-195">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
         <span data-ttu-id="b49b2-196">Para obter mais informações sobre datas de validade de backup, consulte [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b49b2-196">For more information about backup expiration dates, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
18. [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="b49b2-197">e posteriores dão suporte para [compactação de backup](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b49b2-197">and later supports [backup compression](backup-compression-sql-server.md).</span></span> <span data-ttu-id="b49b2-198">Por padrão, a compactação de um backup depende do valor da opção de configuração de servidor **padrão de compactação de backup**.</span><span class="sxs-lookup"><span data-stu-id="b49b2-198">By default, whether a backup is compressed depends on the value of the **backup-compression default** server configuration option.</span></span> <span data-ttu-id="b49b2-199">Porém, independentemente do padrão atual do nível do servidor, é possível compactar um backup, marcando a opção **Compactar backup**e evitar a compactação marcando **Não compactar o backup**.</span><span class="sxs-lookup"><span data-stu-id="b49b2-199">However, regardless of the current server-level default, you can compress a backup by checking **Compress backup**, and you can prevent compression by checking **Do not compress backup**.</span></span>  
  
     <span data-ttu-id="b49b2-200">**Para exibir ou alterar o padrão de compactação de backup atual**</span><span class="sxs-lookup"><span data-stu-id="b49b2-200">**To view or change the current backup compression default**</span></span>  
  
    -   [<span data-ttu-id="b49b2-201">Exibir ou configurar a opção de configuração de servidor backup compression default</span><span class="sxs-lookup"><span data-stu-id="b49b2-201">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
19. <span data-ttu-id="b49b2-202">Especifique se a criptografia deve ser usada para o backup.</span><span class="sxs-lookup"><span data-stu-id="b49b2-202">Specify whether to use encryption for the backup.</span></span> <span data-ttu-id="b49b2-203">Selecione um algoritmo de criptografia a ser usado na etapa de criptografia e forneça um Certificado ou uma Chave assimétrica de uma lista de certificados ou chaves assimétricas existentes.</span><span class="sxs-lookup"><span data-stu-id="b49b2-203">Select an encryption algorithm to use for the encryption step, and provide a Certificate or Asymmetric key from a list of existing certificates or asymmetric keys.</span></span> <span data-ttu-id="b49b2-204">A criptografia tem suporte no SQL Server 2014 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="b49b2-204">Encryption is supported in SQL Server 2014 or later.</span></span> <span data-ttu-id="b49b2-205">Para obter mais detalhes sobre as opções de criptografia, consulte [Fazer backup do banco de dados &#40;página Opções de Backup&#41;](back-up-database-backup-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="b49b2-205">For more details on the Encryption options, see [Back Up Database &#40;Backup Options Page&#41;](back-up-database-backup-options-page.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b49b2-206">Alternativamente, é possível usar o Assistente de Plano de Manutenção para criar backups de bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="b49b2-206">Alternatively, you can use the Maintenance Plan Wizard to create database backups.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b49b2-207">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b49b2-207">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-full-database-backup"></a><span data-ttu-id="b49b2-208">Para criar um backup de banco de dados completo</span><span class="sxs-lookup"><span data-stu-id="b49b2-208">To create a full database backup</span></span>  
  
1.  <span data-ttu-id="b49b2-209">Execute a instrução BACKUP DATABASE para criar o backup do banco de dados completo, especificando:</span><span class="sxs-lookup"><span data-stu-id="b49b2-209">Execute the BACKUP DATABASE statement to create the full database backup, specifying:</span></span>  
  
    -   <span data-ttu-id="b49b2-210">O nome do banco de dados do qual fazer backup.</span><span class="sxs-lookup"><span data-stu-id="b49b2-210">The name of the database to back up.</span></span>  
  
    -   <span data-ttu-id="b49b2-211">O dispositivo de backup em que o backup completo do banco de dados será gravado.</span><span class="sxs-lookup"><span data-stu-id="b49b2-211">The backup device where the full database backup is written.</span></span>  
  
     <span data-ttu-id="b49b2-212">A sintaxe básica [!INCLUDE[tsql](../../includes/tsql-md.md)] para o backup de banco de dados completo é:</span><span class="sxs-lookup"><span data-stu-id="b49b2-212">The basic [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax for a full database backup is:</span></span>  
  
     <span data-ttu-id="b49b2-213">BACKUP DATABASE *database*</span><span class="sxs-lookup"><span data-stu-id="b49b2-213">BACKUP DATABASE *database*</span></span>  
  
     <span data-ttu-id="b49b2-214">TO *backup_device* [ **,** ...*n* ]</span><span class="sxs-lookup"><span data-stu-id="b49b2-214">TO *backup_device* [ **,**...*n* ]</span></span>  
  
     <span data-ttu-id="b49b2-215">[ WITH *com_opções* [ **,** ...*o* ] ] ;</span><span class="sxs-lookup"><span data-stu-id="b49b2-215">[ WITH *with_options* [ **,**...*o* ] ] ;</span></span>  
  
    |<span data-ttu-id="b49b2-216">Opção</span><span class="sxs-lookup"><span data-stu-id="b49b2-216">Option</span></span>|<span data-ttu-id="b49b2-217">Descrição</span><span class="sxs-lookup"><span data-stu-id="b49b2-217">Description</span></span>|  
    |------------|-----------------|  
    |<span data-ttu-id="b49b2-218">*database*</span><span class="sxs-lookup"><span data-stu-id="b49b2-218">*database*</span></span>|<span data-ttu-id="b49b2-219">É o banco de dados do qual fazer backup.</span><span class="sxs-lookup"><span data-stu-id="b49b2-219">Is the database that is to be backed up.</span></span>|  
    |<span data-ttu-id="b49b2-220">*backup_device* [ **,** ...*n* ]</span><span class="sxs-lookup"><span data-stu-id="b49b2-220">*backup_device* [ **,**...*n* ]</span></span>|<span data-ttu-id="b49b2-221">Especifica uma lista de 1 a 64 dispositivos de backup a serem usados para a operação de backup.</span><span class="sxs-lookup"><span data-stu-id="b49b2-221">Specifies a list of from 1 to 64 backup devices to use for the backup operation.</span></span> <span data-ttu-id="b49b2-222">Você pode especificar um dispositivo de backup físico ou pode especificar um dispositivo de backup lógico correspondente, se já definido.</span><span class="sxs-lookup"><span data-stu-id="b49b2-222">You can specify a physical backup device, or you can specify a corresponding logical backup device, if already defined.</span></span> <span data-ttu-id="b49b2-223">Para especificar um dispositivo de backup físico, use a opção DISK ou TAPE:</span><span class="sxs-lookup"><span data-stu-id="b49b2-223">To specify a physical backup device, use the DISK or TAPE option:</span></span><br /><br /> <span data-ttu-id="b49b2-224">{ DISK &#124; TAPE } **=** _physical_backup_device_name_</span><span class="sxs-lookup"><span data-stu-id="b49b2-224">{ DISK &#124; TAPE } **=**_physical_backup_device_name_</span></span><br /><br /> <span data-ttu-id="b49b2-225">Para obter mais informações, consulte [Dispositivos de backup &#40;SQL Server&#41;](backup-devices-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b49b2-225">For more information, see [Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md).</span></span>|  
    |<span data-ttu-id="b49b2-226">WITH *with_options* [ **,** ...*o* ]</span><span class="sxs-lookup"><span data-stu-id="b49b2-226">WITH *with_options* [ **,**...*o* ]</span></span>|<span data-ttu-id="b49b2-227">Opcionalmente, especifica uma ou mais opções adicionais, *o*.</span><span class="sxs-lookup"><span data-stu-id="b49b2-227">Optionally, specifies one or more additional options, *o*.</span></span> <span data-ttu-id="b49b2-228">Para obter informações sobre os fundamentos de opções, consulte a etapa 2.</span><span class="sxs-lookup"><span data-stu-id="b49b2-228">For information about some of the basic with options, see step 2.</span></span>|  
  
2.  <span data-ttu-id="b49b2-229">Opcionalmente, especifique uma ou mais opções WITH.</span><span class="sxs-lookup"><span data-stu-id="b49b2-229">Optionally, specify one or more WITH options.</span></span> <span data-ttu-id="b49b2-230">Algumas opções WITH básicas são descritas aqui.</span><span class="sxs-lookup"><span data-stu-id="b49b2-230">A few basic WITH options are described here.</span></span> <span data-ttu-id="b49b2-231">Para obter informações sobre todas as opções WITH, confira [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b49b2-231">For information about all the WITH options, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
    -   <span data-ttu-id="b49b2-232">Opções WITH do conjunto de backup básico:</span><span class="sxs-lookup"><span data-stu-id="b49b2-232">Basic backup set WITH options:</span></span>  
  
         <span data-ttu-id="b49b2-233">{ COMPRESSION | NO_COMPRESSION }</span><span class="sxs-lookup"><span data-stu-id="b49b2-233">{ COMPRESSION | NO_COMPRESSION }</span></span>  
         <span data-ttu-id="b49b2-234">No [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] e versões posteriores somente, especifica se [compressão de backup](backup-compression-sql-server.md) é executada neste backup, substituindo o padrão de nível de servidor.</span><span class="sxs-lookup"><span data-stu-id="b49b2-234">In [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] and later only, specifies whether [backup compression](backup-compression-sql-server.md) is performed on this backup, overriding the server-level default.</span></span>  
  
         <span data-ttu-id="b49b2-235">ENCRYPTION (ALGORITHM, SERVER CERTIFICATE |ASYMMETRIC KEY)</span><span class="sxs-lookup"><span data-stu-id="b49b2-235">ENCRYPTION (ALGORITHM,  SERVER CERTIFICATE |ASYMMETRIC KEY)</span></span>  
         <span data-ttu-id="b49b2-236">No SQL Server 2014 ou em versões posteriores somente, especifique o algoritmo de criptografia a ser usado, e o certificado ou chave assimétrica usada para proteger a criptografia.</span><span class="sxs-lookup"><span data-stu-id="b49b2-236">In SQL Server 2014 or later only, specify the encryption algorithm to use, and the Certificate or Asymmetric key to use to secure the encryption.</span></span>  
  
         <span data-ttu-id="b49b2-237">Descrição **=** { **' *`text`* '**  |  **@** _text_variable_ }</span><span class="sxs-lookup"><span data-stu-id="b49b2-237">DESCRIPTION **=** { **'*`text`*'** | **@**_text_variable_ }</span></span>  
         <span data-ttu-id="b49b2-238">Especifica o texto de forma livre que descreve o conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="b49b2-238">Specifies the free-form text that describes the backup set.</span></span> <span data-ttu-id="b49b2-239">A cadeia de caracteres pode conter um máximo de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="b49b2-239">The string can have a maximum of 255 characters.</span></span>  
  
         <span data-ttu-id="b49b2-240">Nome **=** { *backup_set_name*  |  **@** _backup_set_name_var_ }</span><span class="sxs-lookup"><span data-stu-id="b49b2-240">NAME **=** { *backup_set_name* | **@**_backup_set_name_var_ }</span></span>  
         <span data-ttu-id="b49b2-241">Especifica o nome do conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="b49b2-241">Specifies the name of the backup set.</span></span> <span data-ttu-id="b49b2-242">Os nomes podem ter no máximo de 128 caracteres.</span><span class="sxs-lookup"><span data-stu-id="b49b2-242">Names can have a maximum of 128 characters.</span></span> <span data-ttu-id="b49b2-243">Se NAME não estiver especificado, ele estará em branco.</span><span class="sxs-lookup"><span data-stu-id="b49b2-243">If NAME is not specified, it is blank.</span></span>  
  
    -   <span data-ttu-id="b49b2-244">Opções WITH do conjunto de backup básico:</span><span class="sxs-lookup"><span data-stu-id="b49b2-244">Basic backup set WITH options:</span></span>  
  
         <span data-ttu-id="b49b2-245">Por padrão, BACKUP anexa o backup a um conjunto de mídias existente, preservando conjuntos de backup existentes.</span><span class="sxs-lookup"><span data-stu-id="b49b2-245">By default, BACKUP appends the backup to an existing media set, preserving existing backup sets.</span></span> <span data-ttu-id="b49b2-246">Para especificar isso explicitamente, use a opção NOINIT.</span><span class="sxs-lookup"><span data-stu-id="b49b2-246">To explicitly specify this, use the NOINIT option.</span></span> <span data-ttu-id="b49b2-247">Para obter informações sobre o acréscimo a conjuntos de backup existentes, consulte [Conjuntos de mídias, famílias de mídia e conjuntos de backup &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b49b2-247">For information about appending to existing backup sets, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
         <span data-ttu-id="b49b2-248">Alternativamente, para formatar a mídia de backup, use a opção FORMAT:</span><span class="sxs-lookup"><span data-stu-id="b49b2-248">Alternatively, to format the backup media, use the FORMAT option:</span></span>  
  
         <span data-ttu-id="b49b2-249">Format [ **,** MediaName **=** { *media_name*  |  **@** _media_name_variable_ }] [ **,** MediaDescription **=** { *Text*  |  **@** _text_variable_ }]</span><span class="sxs-lookup"><span data-stu-id="b49b2-249">FORMAT [ **,** MEDIANAME**=** { *media_name* | **@**_media_name_variable_ } ] [ **,** MEDIADESCRIPTION **=** { *text* | **@**_text_variable_ } ]</span></span>  
         <span data-ttu-id="b49b2-250">Use a cláusula FORMAT quando estiver usando a mídia pela primeira vez ou quando quiser sobrescrever todos os dados existentes</span><span class="sxs-lookup"><span data-stu-id="b49b2-250">Use the FORMAT clause when you are using media for the first time or you want to overwrite all existing data.</span></span> <span data-ttu-id="b49b2-251">Opcionalmente, atribua à nova mídia um nome e uma descrição.</span><span class="sxs-lookup"><span data-stu-id="b49b2-251">Optionally, assign the new media a media name and description.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="b49b2-252">Tenha muito cuidado ao usar a cláusula FORMAT ou a instrução BACKUP, pois isso destrói qualquer backup previamente armazenado na mídia de backup.</span><span class="sxs-lookup"><span data-stu-id="b49b2-252">Use extreme caution when you are using the FORMAT clause of the BACKUP statement because this destroys any backups that were previously stored on the backup media.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="b49b2-253">Exemplos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b49b2-253">Examples (Transact-SQL)</span></span>  
  
#### <a name="a-backing-up-to-a-disk-device"></a><span data-ttu-id="b49b2-254">a.</span><span class="sxs-lookup"><span data-stu-id="b49b2-254">A.</span></span> <span data-ttu-id="b49b2-255">Fazendo backup para um dispositivo de disco.</span><span class="sxs-lookup"><span data-stu-id="b49b2-255">Backing up to a disk device</span></span>  
 <span data-ttu-id="b49b2-256">O exemplo a seguir faz backup de banco de dados completo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] em um disco, usando `FORMAT` para criar um novo conjunto de mídia.</span><span class="sxs-lookup"><span data-stu-id="b49b2-256">The following example backs up the complete [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database to disk, by using `FORMAT` to create a new media set.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.Bak'  
   WITH FORMAT,  
      MEDIANAME = 'Z_SQLServerBackups',  
      NAME = 'Full Backup of AdventureWorks2012';  
GO  
```  
  
#### <a name="b-backing-up-to-a-tape-device"></a><span data-ttu-id="b49b2-257">B.</span><span class="sxs-lookup"><span data-stu-id="b49b2-257">B.</span></span> <span data-ttu-id="b49b2-258">Fazendo backup para um dispositivo de fita</span><span class="sxs-lookup"><span data-stu-id="b49b2-258">Backing up to a tape device</span></span>  
 <span data-ttu-id="b49b2-259">O exemplo a seguir faz backup do banco de dados completo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]em fita, anexando o backup aos backups anteriores.</span><span class="sxs-lookup"><span data-stu-id="b49b2-259">The following example backs up the complete [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]database to tape, appending the backup to the previous backups.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
   TO TAPE = '\\.\Tape0'  
   WITH NOINIT,  
      NAME = 'Full Backup of AdventureWorks2012';  
GO  
```  
  
#### <a name="c-backing-up-to-a-logical-tape-device"></a><span data-ttu-id="b49b2-260">C.</span><span class="sxs-lookup"><span data-stu-id="b49b2-260">C.</span></span> <span data-ttu-id="b49b2-261">Fazendo backup em um dispositivo de fita lógico</span><span class="sxs-lookup"><span data-stu-id="b49b2-261">Backing up to a logical tape device</span></span>  
 <span data-ttu-id="b49b2-262">O exemplo a seguir cria um dispositivo de backup lógico para uma unidade de fita.</span><span class="sxs-lookup"><span data-stu-id="b49b2-262">The following example creates a logical backup device for a tape drive.</span></span> <span data-ttu-id="b49b2-263">O exemplo faz backup completo do banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] nesse dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b49b2-263">The example then backs up the complete [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database to that device.</span></span>  
  
```sql  
-- Create a logical backup device,   
-- AdventureWorks2012_Bak_Tape, for tape device \\.\tape0.  
USE master;  
GO  
EXEC sp_addumpdevice 'tape', 'AdventureWorks2012_Bak_Tape', '\\.\tape0'; USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
   TO AdventureWorks2012_Bak_Tape  
   WITH FORMAT,  
      MEDIANAME = 'AdventureWorks2012_Bak_Tape',  
      MEDIADESCRIPTION = '\\.\tape0',   
      NAME = 'Full Backup of AdventureWorks2012';  
GO  
```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="b49b2-264">Uso do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b49b2-264">Using PowerShell</span></span>  
  
1.  <span data-ttu-id="b49b2-265">Use o cmdlet `Backup-SqlDatabase`.</span><span class="sxs-lookup"><span data-stu-id="b49b2-265">Use the `Backup-SqlDatabase` cmdlet.</span></span> <span data-ttu-id="b49b2-266">Para indicar explicitamente que se trata de um backup de banco de dados completo, especifique o parâmetro **-BackupAction** com seu valor padrão, `Database` .</span><span class="sxs-lookup"><span data-stu-id="b49b2-266">To explicitly indicate that this is a full database backup, specify the **-BackupAction**  parameter with its default value, `Database`.</span></span> <span data-ttu-id="b49b2-267">Esse parâmetro é opcional para backups completos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b49b2-267">This parameter is optional for full database backups.</span></span>  
  
     <span data-ttu-id="b49b2-268">O exemplo a seguir cria um backup de banco de dados completo do banco de dados `MyDB` para o local de backup padrão da instância de servidor `Computer\Instance`.</span><span class="sxs-lookup"><span data-stu-id="b49b2-268">The following example creates a full database backup of the `MyDB` database to the default backup location of the server instance `Computer\Instance`.</span></span> <span data-ttu-id="b49b2-269">Como opção, esse exemplo especifica `-BackupAction Database`.</span><span class="sxs-lookup"><span data-stu-id="b49b2-269">Optionally, this example specifies `-BackupAction Database`.</span></span>  
  
    ```powershell
    Backup-SqlDatabase -ServerInstance Computer\Instance -Database MyDB -BackupAction Database  
    ```  
  
 <span data-ttu-id="b49b2-270">**Para configurar e usar o provedor do SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="b49b2-270">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="b49b2-271">Provedor do SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="b49b2-271">SQL Server PowerShell Provider</span></span>](../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="b49b2-272">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="b49b2-272">Related Tasks</span></span>  
  
-   [<span data-ttu-id="b49b2-273">Fazer backup de um banco de dados (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b49b2-273">Back Up a Database (SQL Server)</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="b49b2-274">Criar um backup diferencial de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b49b2-274">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="b49b2-275">Restaurar um backup de banco de dados &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="b49b2-275">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="b49b2-276">Restaurar um backup de banco de dados no modelo de recuperação simples &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b49b2-276">Restore a Database Backup Under the Simple Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md)  
  
-   [<span data-ttu-id="b49b2-277">Restaurar um banco de dados até o ponto de falha no modelo de recuperação completa &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b49b2-277">Restore a Database to the Point of Failure Under the Full Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-database-to-point-of-failure-full-recovery.md)  
  
-   [<span data-ttu-id="b49b2-278">Restaurar um banco de dados em um novo local &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b49b2-278">Restore a Database to a New Location &#40;SQL Server&#41;</span></span>](restore-a-database-to-a-new-location-sql-server.md)  
  
-   [<span data-ttu-id="b49b2-279">Usar o Assistente de Plano de Manutenção</span><span class="sxs-lookup"><span data-stu-id="b49b2-279">Use the Maintenance Plan Wizard</span></span>](../maintenance-plans/use-the-maintenance-plan-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="b49b2-280">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b49b2-280">See Also</span></span>  
 <span data-ttu-id="b49b2-281">[Visão geral do backup &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b49b2-281">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="b49b2-282">[Backups de log de transações &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b49b2-282">[Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="b49b2-283">[Conjuntos de mídias, famílias de mídia e conjuntos de backup &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b49b2-283">[Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md) </span></span>  
 <span data-ttu-id="b49b2-284">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b49b2-284">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="b49b2-285">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b49b2-285">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="b49b2-286">[Fazer backup do banco de dados &#40;página Geral&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="b49b2-286">[Back Up Database &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="b49b2-287">[Fazer backup do banco de dados &#40;página Opções de Backup&#41;](back-up-database-backup-options-page.md) </span><span class="sxs-lookup"><span data-stu-id="b49b2-287">[Back Up Database &#40;Backup Options Page&#41;](back-up-database-backup-options-page.md) </span></span>  
 <span data-ttu-id="b49b2-288">[Backups diferenciais &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b49b2-288">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="b49b2-289">Backups de bancos de dados completos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b49b2-289">Full Database Backups &#40;SQL Server&#41;</span></span>](full-database-backups-sql-server.md)  
