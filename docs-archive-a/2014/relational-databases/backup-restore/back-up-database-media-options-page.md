---
title: Fazer backup de banco de dados (página Opções de Mídia) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- swb.backupdatabase.mediaoptions.f1
- sql12.swb.backupdatabase.mediaoptions.f1
ms.assetid: eff36228-710c-4ed5-9af5-95859575dc0f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cd09eb091a7f488f891bc2e69d19ad039b65e065
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682306"
---
# <a name="back-up-database-media-options-page"></a><span data-ttu-id="6802d-102">Backup de Banco de Dados (página Opções de Mídia)</span><span class="sxs-lookup"><span data-stu-id="6802d-102">Back Up Database (Media Options Page)</span></span>
  <span data-ttu-id="6802d-103">Use a página  **Opções de Mídia** da caixa de diálogo **Fazer Backup de Banco de Dados** para exibir ou modificar opções de mídia de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6802d-103">Use the  **Media Options** page of the **Back Up Database** dialog box to view or modify database media options.</span></span>  
  
 <span data-ttu-id="6802d-104">**Para criar um backup usando o SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="6802d-104">**To create a backup by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="6802d-105">Criar um backup completo de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6802d-105">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="6802d-106">Criar um backup diferencial de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6802d-106">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6802d-107">Você pode definir um plano de manutenção de banco de dados para criar backups de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6802d-107">You can define a database maintenance plan to create database backups.</span></span> <span data-ttu-id="6802d-108">Para obter mais informações, consulte [Planos de Manutenção](../maintenance-plans/maintenance-plans.md) e [Usar o Assistente de Plano de Manutenção](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="6802d-108">For more information, see [Maintenance Plans](../maintenance-plans/maintenance-plans.md) and [Use the Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6802d-109">Ao especificar uma tarefa de backup usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], é possível gerar o script [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) correspondente clicando no botão **Script** e selecionando um destino para o script.</span><span class="sxs-lookup"><span data-stu-id="6802d-109">When you specify a backup task by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you can generate the corresponding [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) script by clicking the **Script** button and then selecting a destination for the script.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6802d-110">Opções</span><span class="sxs-lookup"><span data-stu-id="6802d-110">Options</span></span>  
  
### <a name="overwrite-media"></a><span data-ttu-id="6802d-111">Substituir mídia</span><span class="sxs-lookup"><span data-stu-id="6802d-111">Overwrite media</span></span>  
 <span data-ttu-id="6802d-112">As opções do painel **Substituir mídia** controlam como o backup é gravado na mídia.</span><span class="sxs-lookup"><span data-stu-id="6802d-112">The options of the **Overwrite media** panel control how the backup is written to the media.</span></span> <span data-ttu-id="6802d-113">SE você selecionou a URL (Armazenamento do Microsoft Azure) como destino de backup na página Geral da caixa de diálogo Backup de Banco de Dados, as opções na seção Substituir mídia serão desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="6802d-113">IF you selected URL (Azure Storage) as the backup destination on the General page of the Back Up Database dialog box, the options under the Overwrite media section are disabled.</span></span> <span data-ttu-id="6802d-114">Você pode substituir um backup usando a instrução Transact-SQL `BACKUP TO URL.. WITH FORMAT`.</span><span class="sxs-lookup"><span data-stu-id="6802d-114">You can overwrite a backup using the `BACKUP TO URL.. WITH FORMAT` Transact-SQL statement.</span></span> <span data-ttu-id="6802d-115">Para saber mais, confira [SQL Server Backup to URL](sql-server-backup-to-url.md).</span><span class="sxs-lookup"><span data-stu-id="6802d-115">For more information, see [SQL Server Backup to URL](sql-server-backup-to-url.md).</span></span>  
  
 <span data-ttu-id="6802d-116">Há suporte somente para a opção **Fazer backup em um novo conjunto de mídias e apagar todos os conjuntos de backup existentes** nas opções de criptografia.</span><span class="sxs-lookup"><span data-stu-id="6802d-116">Only the option, **Backup to a new media, and erase all existing backup sets** is supported with encryption options.</span></span> <span data-ttu-id="6802d-117">Se você selecionar as opções na seção **Fazer backup na mídia existente**, as opções de criptografias na página **Opções de Backup** serão desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="6802d-117">If you select the options under the **Back up to existing media** section, the encryptions options on the **Backup Options** page will be disabled.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6802d-118">Para obter informações sobre conjuntos de mídias, consulte [Conjuntos de mídias, famílias de mídia e conjuntos de backup &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6802d-118">For information about media sets, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
 <span data-ttu-id="6802d-119">**Fazer backup no conjunto de mídias existente**</span><span class="sxs-lookup"><span data-stu-id="6802d-119">**Back up to the existing media set**</span></span>  
 <span data-ttu-id="6802d-120">Faz o backup de um banco de dados em um conjunto de mídias existente.</span><span class="sxs-lookup"><span data-stu-id="6802d-120">Back up a database to an existing media set.</span></span> <span data-ttu-id="6802d-121">A seleção desse botão de opção habilita três opções.</span><span class="sxs-lookup"><span data-stu-id="6802d-121">Selecting this option button activates three options.</span></span>  
  
 <span data-ttu-id="6802d-122">Escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="6802d-122">Choose one of the following options:</span></span>  
  
 <span data-ttu-id="6802d-123">**Anexar ao conjunto de backup existente**</span><span class="sxs-lookup"><span data-stu-id="6802d-123">**Append to the existing backup set**</span></span>  
 <span data-ttu-id="6802d-124">Anexe o conjunto de backup ao conjunto de mídias existente, preservando qualquer backup anterior.</span><span class="sxs-lookup"><span data-stu-id="6802d-124">Append the backup set to the existing media set, preserving any prior backups.</span></span>  
  
 <span data-ttu-id="6802d-125">**Substituir todos os conjuntos de backup existentes**</span><span class="sxs-lookup"><span data-stu-id="6802d-125">**Overwrite all existing backup sets**</span></span>  
 <span data-ttu-id="6802d-126">Substitua pelo backup atual quaisquer backups anteriores no conjunto de mídias existente.</span><span class="sxs-lookup"><span data-stu-id="6802d-126">Replace any prior backups on the existing media set with the current backup.</span></span>  
  
 <span data-ttu-id="6802d-127">**Verificar nome do conjunto de mídias e validade do conjunto de backup**</span><span class="sxs-lookup"><span data-stu-id="6802d-127">**Check media set name and backup set expiration**</span></span>  
 <span data-ttu-id="6802d-128">Opcionalmente, ao efetuar o backup para um conjunto de mídias existente, solicite que a operação de backup verifique o nome e a data de validade dos conjuntos de backup.</span><span class="sxs-lookup"><span data-stu-id="6802d-128">Optionally, if backing up to an existing media set, require the backup operation to verify the name and the expiration date of the backup sets.</span></span>  
  
 <span data-ttu-id="6802d-129">**Nome do conjunto de mídias**</span><span class="sxs-lookup"><span data-stu-id="6802d-129">**Media set name**</span></span>  
 <span data-ttu-id="6802d-130">Se a opção **Verificar nome do conjunto de mídias e validade do conjunto de backup** for marcada, opcionalmente, especifique o nome do conjunto de mídias a ser usado para essa operação de backup.</span><span class="sxs-lookup"><span data-stu-id="6802d-130">If **Check media set name and backup set expiration** is selected, optionally, specify the name of the media set to be used for this backup operation.</span></span>  
  
 <span data-ttu-id="6802d-131">**Fazer backup em um novo conjunto de mídias e apagar todos os conjuntos de backup existentes**</span><span class="sxs-lookup"><span data-stu-id="6802d-131">**Back up to a new media set, and erase all existing backup sets**</span></span>  
 <span data-ttu-id="6802d-132">Use um conjunto de mídias novo, apagando os conjuntos de backup anteriores.</span><span class="sxs-lookup"><span data-stu-id="6802d-132">Use a new media set, erasing the previous backup sets.</span></span>  
  
 <span data-ttu-id="6802d-133">Clicando-se nessa opção as seguintes opções são habilitadas:</span><span class="sxs-lookup"><span data-stu-id="6802d-133">Clicking this option activates the following options:</span></span>  
  
 <span data-ttu-id="6802d-134">**Novo nome do conjunto de mídias**</span><span class="sxs-lookup"><span data-stu-id="6802d-134">**New media set name**</span></span>  
 <span data-ttu-id="6802d-135">Opcionalmente, digite um nome novo para os conjuntos de mídias.</span><span class="sxs-lookup"><span data-stu-id="6802d-135">Optionally, enter a new name for the media set.</span></span>  
  
 <span data-ttu-id="6802d-136">**Descrição do novo conjunto de mídias**</span><span class="sxs-lookup"><span data-stu-id="6802d-136">**New media set description**</span></span>  
 <span data-ttu-id="6802d-137">Opcionalmente, digite uma descrição significativa do novo conjunto de mídias.</span><span class="sxs-lookup"><span data-stu-id="6802d-137">Optionally, enter a meaningful description of the new media set.</span></span> <span data-ttu-id="6802d-138">Essa descrição deve ser específica o suficiente para comunicar o conteúdo com precisão.</span><span class="sxs-lookup"><span data-stu-id="6802d-138">This description should be specific enough to communicate the contents accurately.</span></span>  
  
### <a name="reliability"></a><span data-ttu-id="6802d-139">Confiabilidade</span><span class="sxs-lookup"><span data-stu-id="6802d-139">Reliability</span></span>  
 <span data-ttu-id="6802d-140">As opções do painel **Log de transações** controlam o gerenciamento de erro pela operação de backup.</span><span class="sxs-lookup"><span data-stu-id="6802d-140">The options of the **Transaction log** panel control error management by the backup operation.</span></span>  
  
 <span data-ttu-id="6802d-141">**Verificar backup quando concluído**</span><span class="sxs-lookup"><span data-stu-id="6802d-141">**Verify backup when finished**</span></span>  
 <span data-ttu-id="6802d-142">Verifique se o conjunto de backup está completo e se todos os volumes estão legíveis.</span><span class="sxs-lookup"><span data-stu-id="6802d-142">Verify that the backup set is complete and that all volumes are readable.</span></span>  
  
 <span data-ttu-id="6802d-143">**Executar soma de verificação antes de gravar na mídia**</span><span class="sxs-lookup"><span data-stu-id="6802d-143">**Perform checksum before writing to media**</span></span>  
 <span data-ttu-id="6802d-144">Verifique as somas de verificação antes de gravar na mídia de backup.</span><span class="sxs-lookup"><span data-stu-id="6802d-144">Verify the checksums before writing to the backup media.</span></span> <span data-ttu-id="6802d-145">A seleção dessa opção é o equivalente a especificar a opção CHECKSUM na instrução BACKUP de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6802d-145">Selecting this option is equivalent to specifying the CHECKSUM option in the BACKUP statement of [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="6802d-146">A seleção dessa opção pode aumentar a carga de trabalho e diminuir a taxa de transferência da operação de backup.</span><span class="sxs-lookup"><span data-stu-id="6802d-146">Selecting this option may increase the workload, and decrease the backup throughput of the backup operation.</span></span> <span data-ttu-id="6802d-147">Para obter informações sobre somas de verificação de backup, veja [Erros de mídia possíveis durante backup e restauração &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6802d-147">For information about backup checksums, see [Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span></span>  
  
 <span data-ttu-id="6802d-148">**Continuar se houver erro**</span><span class="sxs-lookup"><span data-stu-id="6802d-148">**Continue on error**</span></span>  
 <span data-ttu-id="6802d-149">A operação de backup deve continuar mesmo tendo-se encontrado um ou mais erros.</span><span class="sxs-lookup"><span data-stu-id="6802d-149">The backup operation is to continue even after encountering one or more errors.</span></span>  
  
### <a name="transaction-log"></a><span data-ttu-id="6802d-150">Log de transações</span><span class="sxs-lookup"><span data-stu-id="6802d-150">Transaction log</span></span>  
 <span data-ttu-id="6802d-151">As opções do painel **Log de transações** controlam o comportamento de um backup de log de transações.</span><span class="sxs-lookup"><span data-stu-id="6802d-151">The options of the **Transaction log** panel control the behavior of a transaction log backup.</span></span> <span data-ttu-id="6802d-152">Essas opções são relevantes apenas no modelo de recuperação completa ou modelo de recuperação bulk-logged.</span><span class="sxs-lookup"><span data-stu-id="6802d-152">These options are relevant only under the full recovery model or bulk-logged recovery model.</span></span> <span data-ttu-id="6802d-153">Elas são habilitadas apenas se o **Log de transações** tiver sido selecionado no campo **Tipo de backup** na página [Geral](../../integration-services/general-page-of-integration-services-designers-options.md) da caixa de diálogo **Fazer Backup de Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="6802d-153">They are activated only if **Transaction log** has been selected in the **Backup type** field on the [General](../../integration-services/general-page-of-integration-services-designers-options.md) page of the **Back Up Database** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6802d-154">Para obter informações sobre backups do log de transações, veja [Backups do log de transações &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6802d-154">For information about transaction log backups, see [Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
 <span data-ttu-id="6802d-155">**Truncar o log de transações**</span><span class="sxs-lookup"><span data-stu-id="6802d-155">**Truncate the transaction log**</span></span>  
 <span data-ttu-id="6802d-156">Faça backup do log de transações e trunque-o para liberar espaço de log.</span><span class="sxs-lookup"><span data-stu-id="6802d-156">Back up the transaction log and truncate it to free log space.</span></span> <span data-ttu-id="6802d-157">O banco de dados permanece online.</span><span class="sxs-lookup"><span data-stu-id="6802d-157">The database remains online.</span></span> <span data-ttu-id="6802d-158">Essa é a opção padrão.</span><span class="sxs-lookup"><span data-stu-id="6802d-158">This is the default option.</span></span>  
  
 <span data-ttu-id="6802d-159">**Fazer backup da parte final do log e deixar o banco de dados no estado de restauração**</span><span class="sxs-lookup"><span data-stu-id="6802d-159">**Back up the tail of the log, and leave the database in the restoring state**</span></span>  
 <span data-ttu-id="6802d-160">Faça o backup da parte final do log e deixe o banco de dados em um estado de restauração.</span><span class="sxs-lookup"><span data-stu-id="6802d-160">Back up the tail of the log and leave the database in a restoring state.</span></span> <span data-ttu-id="6802d-161">Essa opção cria um *backup da parte final do log*, que faz o backup de logs que ainda não tiveram seus backups executados (o log ativo), normalmente, em preparação para a restauração de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6802d-161">This option creates a *tail-log backup*, which backs up logs that have not yet been backed up (the active log), typically, in preparation for restoring a database.</span></span> <span data-ttu-id="6802d-162">O banco de dados ficará indisponível para usuários até que seja completamente restaurado.</span><span class="sxs-lookup"><span data-stu-id="6802d-162">The database will be unavailable to users until it is completely restored.</span></span>  
  
 <span data-ttu-id="6802d-163">A seleção dessa opção equivale à especificação de WITH NO_TRUNCATE, NORECOVERY em uma instrução [BACKUP](/sql/t-sql/statements/backup-transact-sql) ([!INCLUDE[tsql](../../includes/tsql-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="6802d-163">Selecting this option is equivalent to specifying WITH NO_TRUNCATE, NORECOVERY in a [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement ([!INCLUDE[tsql](../../includes/tsql-md.md)]).</span></span> <span data-ttu-id="6802d-164">Para obter mais informações, veja [Backups da parte final do log &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6802d-164">For more information, see [Tail-Log Backups &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span></span>  
  
### <a name="tape-drive"></a><span data-ttu-id="6802d-165">Unidade de fita</span><span class="sxs-lookup"><span data-stu-id="6802d-165">Tape drive</span></span>  
 <span data-ttu-id="6802d-166">As opções do painel **Unidade de fita** controlam o gerenciamento de fita durante a operação de backup.</span><span class="sxs-lookup"><span data-stu-id="6802d-166">The options of the **Tape drive** panel control tape management during the backup operation.</span></span> <span data-ttu-id="6802d-167">Essas opções serão habilitadas apenas se **Fita** tiver sido selecionada no painel **Destino** da página [Geral](../../integration-services/general-page-of-integration-services-designers-options.md) da caixa de diálogo **Fazer Backup de Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="6802d-167">These options are activated only if **Tape** has been selected in the **Destination** panel on the [General](../../integration-services/general-page-of-integration-services-designers-options.md) page of the **Back Up Database** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6802d-168">Para obter informações sobre como usar dispositivos de fita, veja [Dispositivos de backup &#40;SQL Server&#41;](backup-devices-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6802d-168">For information about how to use tape devices, see [Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md).</span></span>  
  
 <span data-ttu-id="6802d-169">**Descarregar a fita após o backup**</span><span class="sxs-lookup"><span data-stu-id="6802d-169">**Unload the tape after backup**</span></span>  
 <span data-ttu-id="6802d-170">Depois que o backup for concluído, descarregue a fita.</span><span class="sxs-lookup"><span data-stu-id="6802d-170">After the backup is complete, unload the tape.</span></span>  
  
 <span data-ttu-id="6802d-171">**Rebobinar a fita antes de descarregar**</span><span class="sxs-lookup"><span data-stu-id="6802d-171">**Rewind the tape before unloading**</span></span>  
 <span data-ttu-id="6802d-172">Antes de descarregar, libere e rebobine a fita.</span><span class="sxs-lookup"><span data-stu-id="6802d-172">Before unloading the tape, release and rewind it.</span></span> <span data-ttu-id="6802d-173">Isso só será habilitado se **Descarregar a fita após o backup** for selecionado.</span><span class="sxs-lookup"><span data-stu-id="6802d-173">This is enabled only if **Unload the tape after backup** is selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6802d-174">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6802d-174">See Also</span></span>  
 <span data-ttu-id="6802d-175">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6802d-175">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="6802d-176">[Fazer backup de um log de transações &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6802d-176">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="6802d-177">[Fazer backup de arquivos e de grupos de arquivos &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6802d-177">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 [<span data-ttu-id="6802d-178">Fazer backup do log de transações quando o banco de dados está danificado &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6802d-178">Back Up the Transaction Log When the Database Is Damaged &#40;SQL Server&#41;</span></span>](back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md)  
  
  
