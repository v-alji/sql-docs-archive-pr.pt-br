---
title: Fazer backup do log de transações quando o banco de dados estiver danificado (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server], damaged
- backing up [SQL Server]. damaged database
- transaction log backups [SQL Server], damaged databases
ms.assetid: 9b8873cc-df54-4336-ab9b-8f525132c2b0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea712e6bc4e73119a4f07a7775f9f25e212f8534
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568656"
---
# <a name="back-up-the-transaction-log-when-the-database-is-damaged-sql-server"></a><span data-ttu-id="44a4e-102">Fazer backup do log de transações quando o banco de dados está danificado (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="44a4e-102">Back Up the Transaction Log When the Database Is Damaged (SQL Server)</span></span>
  <span data-ttu-id="44a4e-103">Este tópico descreve como fazer backup de um log de transações quando o banco de dados está danificado no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44a4e-103">This topic describes how to back up a transaction log when the database is damaged in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="44a4e-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="44a4e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="44a4e-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="44a4e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="44a4e-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="44a4e-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="44a4e-107">Recomendações</span><span class="sxs-lookup"><span data-stu-id="44a4e-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="44a4e-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="44a4e-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="44a4e-109">**Para fazer backup do log de transações quando o banco de dados está danificado, usando:**</span><span class="sxs-lookup"><span data-stu-id="44a4e-109">**To back up the transaction log when the database is damaged, using:**</span></span>  
  
     [<span data-ttu-id="44a4e-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="44a4e-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="44a4e-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="44a4e-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="44a4e-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="44a4e-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="44a4e-113">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="44a4e-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="44a4e-114">A instrução BACKUP não é permitida em uma transação explícita ou implícita.</span><span class="sxs-lookup"><span data-stu-id="44a4e-114">The BACKUP statement is not allowed in an explicit or implicit transaction.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="44a4e-115">Recomendações</span><span class="sxs-lookup"><span data-stu-id="44a4e-115">Recommendations</span></span>  
  
-   <span data-ttu-id="44a4e-116">Para um banco de dados que usa o modelo de recuperação total ou bulk-logged, geralmente você precisa fazer backup do final do log antes de iniciar a restauração do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="44a4e-116">For a database that uses either the full or bulk-logged recovery model, you generally need to back up the tail of the log before beginning to restore the database.</span></span> <span data-ttu-id="44a4e-117">Você também deve fazer backup do final do log do banco de dados primário antes de efetuar o failover de uma configuração de envio de logs.</span><span class="sxs-lookup"><span data-stu-id="44a4e-117">You also should back up the tail of the log of the primary database before failing over a log shipping configuration.</span></span> <span data-ttu-id="44a4e-118">A restauração do backup do final do log como o backup do log final antes de recuperar o banco de dados evita perda de trabalho após uma falha.</span><span class="sxs-lookup"><span data-stu-id="44a4e-118">Restoring the tail-log backup as the final log backup before recovering the database avoids work loss after a failure.</span></span> <span data-ttu-id="44a4e-119">Para obter mais informações sobre backups da parte final do log, veja [Backups da parte final do log &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="44a4e-119">For more information about tail-log backups, see [Tail-Log Backups &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="44a4e-120">Segurança</span><span class="sxs-lookup"><span data-stu-id="44a4e-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="44a4e-121">Permissões</span><span class="sxs-lookup"><span data-stu-id="44a4e-121">Permissions</span></span>  
 <span data-ttu-id="44a4e-122">As permissões BACKUP DATABASE e BACKUP LOG usam como padrão os membros da função de servidor fixa **sysadmin** e as funções de banco de dados fixas **db_owner** e **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="44a4e-122">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="44a4e-123">Os problemas de propriedade e permissão no arquivo físico do dispositivo de backup podem interferir em uma operação de backup.</span><span class="sxs-lookup"><span data-stu-id="44a4e-123">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="44a4e-124">deve ser capaz de ler e gravar no dispositivo; a conta sob a qual o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executa deve ter permissões de gravação.</span><span class="sxs-lookup"><span data-stu-id="44a4e-124">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="44a4e-125">No entanto, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), que adiciona uma entrada para um dispositivo de backup nas tabelas do sistema, não verifica permissões de acesso a arquivos.</span><span class="sxs-lookup"><span data-stu-id="44a4e-125">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="44a4e-126">Esses problemas no arquivo físico do dispositivo de backup podem não aparecer até que o recurso físico seja acessado quando o backup ou restauração é tentado.</span><span class="sxs-lookup"><span data-stu-id="44a4e-126">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="44a4e-127">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="44a4e-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-back-up-the-tail-of-the-transaction-log"></a><span data-ttu-id="44a4e-128">Para fazer backup do final do log de transações</span><span class="sxs-lookup"><span data-stu-id="44a4e-128">To back up the tail of the transaction log</span></span>  
  
1.  <span data-ttu-id="44a4e-129">Depois de se conectar à instância apropriada do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], em Pesquisador de Objetos, clique no nome do servidor para expandir a árvore do servidor.</span><span class="sxs-lookup"><span data-stu-id="44a4e-129">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="44a4e-130">Expanda **Bancos de Dados**e, dependendo do banco de dados, selecione um banco de dados de usuário ou expanda **Bancos de Dados do Sistema** e selecione um banco de dados do sistema.</span><span class="sxs-lookup"><span data-stu-id="44a4e-130">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="44a4e-131">Clique com o botão direito do mouse no banco de dados, aponte para **Tarefas**e clique em **Backup**.</span><span class="sxs-lookup"><span data-stu-id="44a4e-131">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="44a4e-132">Será exibida a caixa de diálogo **Backup de Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="44a4e-132">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="44a4e-133">Na caixa de listagem **Banco de Dados** , verifique o nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="44a4e-133">In the **Database** list box, verify the database name.</span></span> <span data-ttu-id="44a4e-134">Você pode, como opção, selecionar um banco de dados diferente da lista.</span><span class="sxs-lookup"><span data-stu-id="44a4e-134">You can optionally select a different database from the list.</span></span>  
  
5.  <span data-ttu-id="44a4e-135">Verifique se o modelo de recuperação é **FULL** ou **BULK_LOGGED**.</span><span class="sxs-lookup"><span data-stu-id="44a4e-135">Verify that the recovery model is either **FULL** or **BULK_LOGGED**.</span></span>  
  
6.  <span data-ttu-id="44a4e-136">Na caixa de listagem **Tipo de Backup** , selecione **Log de Transações**.</span><span class="sxs-lookup"><span data-stu-id="44a4e-136">In the **Backup type** list box, select **Transaction Log**.</span></span>  
  
7.  <span data-ttu-id="44a4e-137">Deixe a opção **Copiar Somente Backup** desmarcada.</span><span class="sxs-lookup"><span data-stu-id="44a4e-137">Leave **Copy Only Backup** deselected.</span></span>  
  
8.  <span data-ttu-id="44a4e-138">Na área **Conjunto de backup** , aceite o nome do conjunto de backup padrão sugerido na caixa de texto **Nome** ou digite um nome diferente para o conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="44a4e-138">In the **Backup set** area, either accept the default backup set name suggested in the **Name** text box, or enter a different name for the backup set.</span></span>  
  
9. <span data-ttu-id="44a4e-139">Na caixa de texto **Descrição** , insira uma descrição para o backup da parte final do log.</span><span class="sxs-lookup"><span data-stu-id="44a4e-139">In the **Description** text box, enter a description for the tail-log backup.</span></span>  
  
10. <span data-ttu-id="44a4e-140">Especifique quando o conjunto de backup irá expirar:</span><span class="sxs-lookup"><span data-stu-id="44a4e-140">Specify when the backup set will expire:</span></span>  
  
    -   <span data-ttu-id="44a4e-141">Para que o conjunto de backup expire depois de um número específico de dias, clique em **Depois** (a opção padrão) e digite quantos dias depois da criação do conjunto ele deve expirar.</span><span class="sxs-lookup"><span data-stu-id="44a4e-141">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="44a4e-142">Esse valor pode ser de 0 a 99999 dias; 0 dia significa que o conjunto de backup nunca vai expirar.</span><span class="sxs-lookup"><span data-stu-id="44a4e-142">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="44a4e-143">O valor padrão é definido na opção **Retenção de mídia de backup padrão (em dias)** da caixa de diálogo **Propriedades do Servidor** (página**Configurações do Banco de Dados** ).</span><span class="sxs-lookup"><span data-stu-id="44a4e-143">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (**Database Settings** page).</span></span> <span data-ttu-id="44a4e-144">Para acessar essa caixa de diálogo, clique com o botão direito do mouse no nome do servidor no Pesquisador de Objetos, selecione propriedades e a página **Configurações do Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="44a4e-144">To access this dialog box, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="44a4e-145">Para que o conjunto de backup expire em uma data específica, clique no campo **Em**e digite a data de expiração do conjunto.</span><span class="sxs-lookup"><span data-stu-id="44a4e-145">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
11. <span data-ttu-id="44a4e-146">Escolha o tipo do destino de backup clicando em **Disco** ou **Fita**.</span><span class="sxs-lookup"><span data-stu-id="44a4e-146">Choose the type of backup destination by clicking **Disk** or **Tape**.</span></span> <span data-ttu-id="44a4e-147">Para selecionar os caminhos de até 64 unidades de disco ou fita que contêm um único conjunto de mídia, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="44a4e-147">To select the paths of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span> <span data-ttu-id="44a4e-148">Os caminhos selecionados são exibidos na caixa de listagem **Backup** .</span><span class="sxs-lookup"><span data-stu-id="44a4e-148">The selected paths are displayed in the **Backup to** list box.</span></span>  
  
     <span data-ttu-id="44a4e-149">Para remover um destino de backup, selecione-o e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="44a4e-149">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="44a4e-150">Para exibir o conteúdo de um destino de backup, selecione-o e clique em **Conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="44a4e-150">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
12. <span data-ttu-id="44a4e-151">Na página **Opções** , selecione uma opção **Substituir Mídia** , clicando em uma das opções a seguir:</span><span class="sxs-lookup"><span data-stu-id="44a4e-151">On the **Options** page, select an **Overwrite Media** option, by clicking one of the following:</span></span>  
  
    -   <span data-ttu-id="44a4e-152">**Fazer backup no conjunto de mídias existente**</span><span class="sxs-lookup"><span data-stu-id="44a4e-152">**Back up to the existing media set**</span></span>  
  
         <span data-ttu-id="44a4e-153">Para essa opção, clique em **Anexar ao conjunto de backup existente** ou **Substituir todos os conjuntos de backup existentes**.</span><span class="sxs-lookup"><span data-stu-id="44a4e-153">For this option, click either **Append to the existing backup set** or **Overwrite all existing backup sets**.</span></span>  
  
         <span data-ttu-id="44a4e-154">Opcionalmente, selecione **Verificar nome do conjunto de mídias e validade do conjunto de backup** para que a operação de backup verifique a data e a hora em que o conjunto de mídias e de backup expiram.</span><span class="sxs-lookup"><span data-stu-id="44a4e-154">Optionally, select **Check media set name and backup set expiration** to cause the backup operation to verify the date and time at which the media set and backup set expire.</span></span>  
  
         <span data-ttu-id="44a4e-155">Como opção, digite um nome na caixa de texto **Nome do conjunto de mídias** .</span><span class="sxs-lookup"><span data-stu-id="44a4e-155">Optionally, enter a name in the **Media set name** text box.</span></span> <span data-ttu-id="44a4e-156">Se nenhum nome for especificado, um conjunto de mídias com um nome em branco será criado.</span><span class="sxs-lookup"><span data-stu-id="44a4e-156">If no name is specified, a media set with a blank name is created.</span></span> <span data-ttu-id="44a4e-157">Se você especificar um nome de conjunto de mídias, a mídia (fita ou disco) é verificada para ver se o nome real corresponde ao nome digitado.</span><span class="sxs-lookup"><span data-stu-id="44a4e-157">If you specify a media set name, the media (tape or disk) is checked to see whether the actual name matches the name you enter here.</span></span>  
  
         <span data-ttu-id="44a4e-158">Se você deixar o nome da mídia em branco e marcar a caixa para verificar a mídia, a verificação terá sucesso se o nome da mídia também estiver em branco na mídia.</span><span class="sxs-lookup"><span data-stu-id="44a4e-158">If you leave the media name blank and check the box to check it against the media, success will equal the media name on the media also being blank.</span></span>  
  
    -   <span data-ttu-id="44a4e-159">**Fazer backup em um novo conjunto de mídias e apagar todos os conjuntos de backup existentes**</span><span class="sxs-lookup"><span data-stu-id="44a4e-159">**Back up to a new media set, and erase all existing backup sets**</span></span>  
  
         <span data-ttu-id="44a4e-160">Para essa opção, digite um nome na caixa de texto **Nome do novo conjunto de mídias** e, opcionalmente, descreva o conjunto de mídias na caixa de texto **Descrição do novo conjunto de mídias** .</span><span class="sxs-lookup"><span data-stu-id="44a4e-160">For this option, enter a name in the **New media set name** text box, and, optionally, describe the media set in the **New media set description** text box.</span></span>  
  
     <span data-ttu-id="44a4e-161">Para obter mais informações sobre as opções de conjuntos de mídias, veja [Conjuntos de mídias, famílias de mídia e conjuntos de backup &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="44a4e-161">For more information about media set options, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
13. <span data-ttu-id="44a4e-162">Na seção **Confiabilidade** , como opção, marque:</span><span class="sxs-lookup"><span data-stu-id="44a4e-162">In the **Reliability** section, optionally, check:</span></span>  
  
    -   <span data-ttu-id="44a4e-163">**Verificar backup quando concluído**</span><span class="sxs-lookup"><span data-stu-id="44a4e-163">**Verify backup when finished**.</span></span>  
  
    -   <span data-ttu-id="44a4e-164">**Executar soma de verificação antes de gravar na mídia**.</span><span class="sxs-lookup"><span data-stu-id="44a4e-164">**Perform checksum before writing to media**.</span></span>  
  
    -   <span data-ttu-id="44a4e-165">**Continuar em erro de soma de verificação**</span><span class="sxs-lookup"><span data-stu-id="44a4e-165">**Continue on checksum error**</span></span>  
  
     <span data-ttu-id="44a4e-166">Para obter informações sobre somas de verificação, veja [Erros de mídia possíveis durante backup e restauração &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="44a4e-166">For information on checksums, see [Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span></span>  
  
14. <span data-ttu-id="44a4e-167">Na seção **Log de transações** , marque **Fazer backup da parte final do log e deixar o banco de dados no estado de restauração**.</span><span class="sxs-lookup"><span data-stu-id="44a4e-167">In the **Transaction log** section, check **Back up the tail of the log, and leave database in the restoring state**.</span></span>  
  
     <span data-ttu-id="44a4e-168">Isso é equivalente a especificar a instrução [BACKUP](/sql/t-sql/statements/backup-transact-sql) a seguir:</span><span class="sxs-lookup"><span data-stu-id="44a4e-168">This is equivalent to specifying the following [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement:</span></span>  
  
     `BACKUP LOG <database_name> TO <backup_device> WITH NORECOVERY`  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="44a4e-169">Na hora da restauração, a caixa de diálogo Restaurar Banco de dados exibe o tipo de um backup da parte final do log como **Log de Transações (Copiar Somente)** .</span><span class="sxs-lookup"><span data-stu-id="44a4e-169">At restore time, the Restore Database dialog box displays the type of a tail-log backup as **Transaction Log (Copy Only)**.</span></span>  
  
15. <span data-ttu-id="44a4e-170">Se o backup estiver sendo feito em uma unidade de fita (conforme especificado na seção **Destino** da página **Geral** ), a opção **Descarregar a fita após o backup** estará ativa.</span><span class="sxs-lookup"><span data-stu-id="44a4e-170">If you are backing up to a tape drive (as specified in the **Destination** section of the **General** page), the **Unload the tape after backup** option is active.</span></span> <span data-ttu-id="44a4e-171">Clicar nessa opção ativa a opção **Rebobinar a fita antes de descarregar** .</span><span class="sxs-lookup"><span data-stu-id="44a4e-171">Clicking this option activates the **Rewind the tape before unloading** option.</span></span>  
  
16. [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="44a4e-172">e posteriores dão suporte para [compactação de backup](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="44a4e-172">and later supports [backup compression](backup-compression-sql-server.md).</span></span> <span data-ttu-id="44a4e-173">Por padrão, a compactação de um backup depende do valor da opção de configuração de servidor **padrão de compactação de backup**.</span><span class="sxs-lookup"><span data-stu-id="44a4e-173">By default, whether a backup is compressed depends on the value of the **backup-compression default** server configuration option.</span></span> <span data-ttu-id="44a4e-174">Porém, independentemente do padrão atual do nível do servidor, é possível compactar um backup, marcando a opção **Compactar backup**e evitar a compactação marcando **Não compactar o backup**.</span><span class="sxs-lookup"><span data-stu-id="44a4e-174">However, regardless of the current server-level default, you can compress a backup by checking **Compress backup**, and you can prevent compression by checking **Do not compress backup**.</span></span>  
  
     <span data-ttu-id="44a4e-175">**Para exibir o padrão de compactação de backup atual**</span><span class="sxs-lookup"><span data-stu-id="44a4e-175">**To view the current backup compression default**</span></span>  
  
    -   [<span data-ttu-id="44a4e-176">Exibir ou configurar a opção de configuração de servidor backup compression default</span><span class="sxs-lookup"><span data-stu-id="44a4e-176">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="44a4e-177">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="44a4e-177">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-backup-of-the-currently-active-transaction-log"></a><span data-ttu-id="44a4e-178">Para criar um backup do log de transações atualmente ativas</span><span class="sxs-lookup"><span data-stu-id="44a4e-178">To create a backup of the currently active transaction log</span></span>  
  
1.  <span data-ttu-id="44a4e-179">Execute a instrução BACKUP LOG para fazer backup do log de transações atualmente ativas, especificando:</span><span class="sxs-lookup"><span data-stu-id="44a4e-179">Execute the BACKUP LOG statement to back up the currently active transaction log, specifying:</span></span>  
  
    -   <span data-ttu-id="44a4e-180">O nome do banco de dados ao qual o log de transações cujo backup será feito pertence.</span><span class="sxs-lookup"><span data-stu-id="44a4e-180">The name of the database to which the transaction log to back up belongs.</span></span>  
  
    -   <span data-ttu-id="44a4e-181">O dispositivo de backup onde o backup de log de transações será gravado.</span><span class="sxs-lookup"><span data-stu-id="44a4e-181">The backup device where the transaction log backup will be written.</span></span>  
  
    -   <span data-ttu-id="44a4e-182">A cláusula NO_TRUNCATE.</span><span class="sxs-lookup"><span data-stu-id="44a4e-182">The NO_TRUNCATE clause.</span></span>  
  
         <span data-ttu-id="44a4e-183">Essa cláusula permite fazer backup da parte ativa do log de transações mesmo se o banco de dados estiver inacessível, contanto que o arquivo de log de transações esteja acessível e sem-danos.</span><span class="sxs-lookup"><span data-stu-id="44a4e-183">This clause allows the active part of the transaction log to be backed up even if the database is inaccessible, provided that the transaction log file is accessible and undamaged.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="44a4e-184">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="44a4e-184">Example (Transact-SQL)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="44a4e-185">Este exemplo usa o [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], que usa o modelo de recuperação simples.</span><span class="sxs-lookup"><span data-stu-id="44a4e-185">This example uses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], which uses the simple recovery model.</span></span> <span data-ttu-id="44a4e-186">Para permitir backups de log, antes de fazer um backup de banco de dados completo, o banco de dados foi definido para usar o modelo de recuperação completa.</span><span class="sxs-lookup"><span data-stu-id="44a4e-186">To permit log backups, before taking a full database backup, the database was set to use the full recovery model.</span></span> <span data-ttu-id="44a4e-187">Para obter mais informações, veja [Exibir ou alterar o modelo de recuperação de um banco de dados &#40;SQL Server&#41;](view-or-change-the-recovery-model-of-a-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="44a4e-187">For more information, see [View or Change the Recovery Model of a Database &#40;SQL Server&#41;](view-or-change-the-recovery-model-of-a-database-sql-server.md).</span></span>  
  
 <span data-ttu-id="44a4e-188">Este exemplo faz o backup do log da transação ativa no momento quando um banco de dados é danificado e está inacessível, se o log de transação não estiver danificado e estiver acessível.</span><span class="sxs-lookup"><span data-stu-id="44a4e-188">This example backs up the currently active transaction log when a database is damaged and inaccessible, if the transaction log is undamaged and accessible.</span></span>  
  
```scr  
BACKUP LOG AdventureWorks2012  
   TO MyAdvWorks_FullRM_log1  
   WITH NO_TRUNCATE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="44a4e-189">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="44a4e-189">See Also</span></span>  
 <span data-ttu-id="44a4e-190">[Restaurar um backup de log de transações &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="44a4e-190">[Restore a Transaction Log Backup &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span></span>  
 <span data-ttu-id="44a4e-191">[Restaurar um banco de dados do SQL Server em um ponto específico &#40;Modelo de recuperação completa&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="44a4e-191">[Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span></span>  
 <span data-ttu-id="44a4e-192">[Fazer backup do banco de dados &#40;página Opções de Backup&#41;](back-up-database-backup-options-page.md) </span><span class="sxs-lookup"><span data-stu-id="44a4e-192">[Back Up Database &#40;Backup Options Page&#41;](back-up-database-backup-options-page.md) </span></span>  
 <span data-ttu-id="44a4e-193">[Fazer backup do banco de dados &#40;página Geral&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="44a4e-193">[Back Up Database &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="44a4e-194">[Aplicar backups de log de transações &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="44a4e-194">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="44a4e-195">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="44a4e-195">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="44a4e-196">[Restaurações de arquivos &#40;Modelo de recuperação simples&#41;](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="44a4e-196">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 [<span data-ttu-id="44a4e-197">Restaurações de arquivo &#40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="44a4e-197">File Restores &#40;Full Recovery Model&#41;</span></span>](file-restores-full-recovery-model.md)  
  
  
