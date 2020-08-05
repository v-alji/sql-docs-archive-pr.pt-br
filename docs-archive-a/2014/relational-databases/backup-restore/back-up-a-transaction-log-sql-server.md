---
title: Fazer backup de um log de transações (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- transaction log backups [SQL Server], SQL Server Management Studio
- backups [SQL Server], creating
- backing up transaction logs [SQL Server], SQL Server Management Studio
ms.assetid: 3426b5eb-6327-4c7f-88aa-37030be69fbf
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b57ca40b08718cda5095249991e0d424e6593a24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573147"
---
# <a name="back-up-a-transaction-log-sql-server"></a><span data-ttu-id="b04ca-102">Fazer backup de um log de transações (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b04ca-102">Back Up a Transaction Log (SQL Server)</span></span>
  <span data-ttu-id="b04ca-103">Este tópico descreve como fazer backup de um log de transações no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], o [!INCLUDE[tsql](../../includes/tsql-md.md)]ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b04ca-103">This topic describes how to back up a transaction log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
 <span data-ttu-id="b04ca-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="b04ca-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b04ca-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="b04ca-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b04ca-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="b04ca-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b04ca-107">Recomendações</span><span class="sxs-lookup"><span data-stu-id="b04ca-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="b04ca-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="b04ca-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b04ca-109">**Para fazer backup de um log de transações usando:**</span><span class="sxs-lookup"><span data-stu-id="b04ca-109">**To back up a transaction log, using:**</span></span>  
  
     [<span data-ttu-id="b04ca-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b04ca-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b04ca-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b04ca-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="b04ca-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="b04ca-112">PowerShell</span></span>](#PowerShellProcedure)  
  
    > [!NOTE]  
    >  <span data-ttu-id="b04ca-113"> Alternativamente, é possível usar o[Assistente de Plano de Manutenção](../maintenance-plans/use-the-maintenance-plan-wizard.md)para criar backups.</span><span class="sxs-lookup"><span data-stu-id="b04ca-113">Alternatively, you can use the[Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md)to create backups.</span></span>  
  
-   [<span data-ttu-id="b04ca-114">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="b04ca-114">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b04ca-115">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="b04ca-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b04ca-116">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="b04ca-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b04ca-117">A instrução BACKUP não é permitida em uma transação explícita ou implícita.</span><span class="sxs-lookup"><span data-stu-id="b04ca-117">The BACKUP statement is not allowed in an explicit or implicit transaction.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="b04ca-118">Recomendações</span><span class="sxs-lookup"><span data-stu-id="b04ca-118">Recommendations</span></span>  
  
-   <span data-ttu-id="b04ca-119">Se um banco de dados usar o modelo de recuperação total ou bulk-logged, você deverá fazer backup do log de transações com regularidade suficiente para proteger os dados e impedir que o log de transações fique cheio.</span><span class="sxs-lookup"><span data-stu-id="b04ca-119">If a database uses either the full or bulk-logged recovery model, you must back up the transaction log regularly enough to protect your data and to keep the transaction log from filling.</span></span> <span data-ttu-id="b04ca-120">Isso trunca o log e oferece suporte à restauração do banco de dados para um período específico.</span><span class="sxs-lookup"><span data-stu-id="b04ca-120">This truncates the log and supports restoring the database to a specific point in time.</span></span>  
  
-   <span data-ttu-id="b04ca-121">Por padrão, toda operação de backup bem-sucedida acrescenta uma entrada ao log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e ao log de eventos do sistema.</span><span class="sxs-lookup"><span data-stu-id="b04ca-121">By default, every successful backup operation adds an entry in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and in the system event log.</span></span> <span data-ttu-id="b04ca-122">Se você fizer backup do log com muita frequência, essas mensagens de êxito se acumularão muito rapidamente, resultando em logs de erros imensos que podem dificultar a localização de outras mensagens.</span><span class="sxs-lookup"><span data-stu-id="b04ca-122">If back up the log very frequently, these success messages accumulate quickly, resulting in huge error logs that can make finding other messages difficult.</span></span> <span data-ttu-id="b04ca-123">Em tais situações, você pode suprimir essas entradas de log usando o sinalizador de rastreamento 3226, caso nenhum dos seus scripts dependa dessas entradas.</span><span class="sxs-lookup"><span data-stu-id="b04ca-123">In such cases you can suppress these log entries by using trace flag 3226 if none of your scripts depend on those entries.</span></span> <span data-ttu-id="b04ca-124">Para obter mais informações, veja, [Sinalizadores de rastreamento &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b04ca-124">For more information, see [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b04ca-125">Segurança</span><span class="sxs-lookup"><span data-stu-id="b04ca-125">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b04ca-126">Permissões</span><span class="sxs-lookup"><span data-stu-id="b04ca-126">Permissions</span></span>  
 <span data-ttu-id="b04ca-127">As permissões BACKUP DATABASE e BACKUP LOG usam como padrão os membros da função de servidor fixa **sysadmin** e as funções de banco de dados fixas **db_owner** e **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="b04ca-127">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="b04ca-128">Os problemas de propriedade e permissão no arquivo físico do dispositivo de backup podem interferir em uma operação de backup.</span><span class="sxs-lookup"><span data-stu-id="b04ca-128">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b04ca-129">deve ser capaz de ler e gravar no dispositivo; a conta sob a qual o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executa deve ter permissões de gravação.</span><span class="sxs-lookup"><span data-stu-id="b04ca-129">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="b04ca-130">No entanto, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), que adiciona uma entrada para um dispositivo de backup nas tabelas do sistema, não verifica permissões de acesso a arquivos.</span><span class="sxs-lookup"><span data-stu-id="b04ca-130">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="b04ca-131">Esses problemas no arquivo físico do dispositivo de backup podem não aparecer até que o recurso físico seja acessado quando o backup ou restauração é tentado.</span><span class="sxs-lookup"><span data-stu-id="b04ca-131">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b04ca-132">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b04ca-132">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-back-up-a-transaction-log"></a><span data-ttu-id="b04ca-133">Para fazer backup de um log de transações</span><span class="sxs-lookup"><span data-stu-id="b04ca-133">To back up a transaction log</span></span>  
  
1.  <span data-ttu-id="b04ca-134">Depois de conectar-se à instância adequada do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], no Pesquisador de Objeto, clique no nome do servidor para expandir a árvore do servidor.</span><span class="sxs-lookup"><span data-stu-id="b04ca-134">After connecting to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="b04ca-135">Expanda **Bancos de Dados**e, dependendo do banco de dados, selecione um banco de dados de usuário ou expanda **Bancos de Dados do Sistema** e selecione um banco de dados do sistema.</span><span class="sxs-lookup"><span data-stu-id="b04ca-135">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="b04ca-136">Clique com o botão direito do mouse no banco de dados, aponte para **Tarefas**e clique em **Backup**.</span><span class="sxs-lookup"><span data-stu-id="b04ca-136">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="b04ca-137">Será exibida a caixa de diálogo **Backup de Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="b04ca-137">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="b04ca-138">Na caixa de listagem **Banco de Dados** , verifique o nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b04ca-138">In the **Database** list box, verify the database name.</span></span> <span data-ttu-id="b04ca-139">Você pode, como opção, selecionar um banco de dados diferente da lista.</span><span class="sxs-lookup"><span data-stu-id="b04ca-139">You can optionally select a different database from the list.</span></span>  
  
5.  <span data-ttu-id="b04ca-140">Verifique se o modelo de recuperação é **FULL** ou **BULK_LOGGED**.</span><span class="sxs-lookup"><span data-stu-id="b04ca-140">Verify that the recovery model is either **FULL** or **BULK_LOGGED**.</span></span>  
  
6.  <span data-ttu-id="b04ca-141">Na caixa de listagem **Tipo de Backup** , selecione **Log de Transações**.</span><span class="sxs-lookup"><span data-stu-id="b04ca-141">In the **Backup type** list box, select **Transaction Log**.</span></span>  
  
7.  <span data-ttu-id="b04ca-142">Opcionalmente, você pode selecionar **Copiar Somente Backup** para criar um backup somente cópia.</span><span class="sxs-lookup"><span data-stu-id="b04ca-142">Optionally, you can select **Copy Only Backup** to create a copy-only backup.</span></span> <span data-ttu-id="b04ca-143">Um *backup somente cópia* é um backup do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que não depende da sequência de backups convencionais do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b04ca-143">A *copy-only backup* is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup that is independent of the sequence of conventional [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span> <span data-ttu-id="b04ca-144">Para obter mais informações, veja [Backups somente cópia &#40;SQL Server&#41;](copy-only-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b04ca-144">For more information, see [Copy-Only Backups &#40;SQL Server&#41;](copy-only-backups-sql-server.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b04ca-145">Quando a opção **Diferencial** está selecionada, você não pode criar um backup somente cópia.</span><span class="sxs-lookup"><span data-stu-id="b04ca-145">When the **Differential** option is selected, you cannot create a copy-only backup.</span></span>  
  
8.  <span data-ttu-id="b04ca-146">Aceite o nome do conjunto de backup padrão sugerido na caixa de texto **Nome** ou digite um nome diferente para o conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="b04ca-146">Either accept the default backup set name suggested in the **Name** text box, or enter a different name for the backup set.</span></span>  
  
9. <span data-ttu-id="b04ca-147">Opcionalmente, na caixa de texto **Descrição** , digite uma descrição do conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="b04ca-147">Optionally, in the **Description** text box, enter a description of the backup set.</span></span>  
  
10. <span data-ttu-id="b04ca-148">Especifique quando o conjunto de backup irá expirar:</span><span class="sxs-lookup"><span data-stu-id="b04ca-148">Specify when the backup set will expire:</span></span>  
  
    -   <span data-ttu-id="b04ca-149">Para que o conjunto de backup expire depois de um número específico de dias, clique em **Depois** (a opção padrão) e digite quantos dias depois da criação do conjunto ele deve expirar.</span><span class="sxs-lookup"><span data-stu-id="b04ca-149">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="b04ca-150">Esse valor pode ser de 0 a 99999 dias; 0 dia significa que o conjunto de backup nunca vai expirar.</span><span class="sxs-lookup"><span data-stu-id="b04ca-150">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="b04ca-151">O valor padrão é definido na opção **Retenção de mídia de backup padrão (em dias)** da caixa de diálogo **Propriedades do Servidor** (página**Configurações do Banco de Dados** ).</span><span class="sxs-lookup"><span data-stu-id="b04ca-151">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (**Database Settings** page).</span></span> <span data-ttu-id="b04ca-152">Para acessar essa caixa de diálogo, clique com o botão direito do mouse no nome do servidor no Pesquisador de Objetos, selecione propriedades e a página **Configurações do Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="b04ca-152">To access this dialog box, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="b04ca-153">Para que o conjunto de backup expire em uma data específica, clique no campo **Em**e digite a data de expiração do conjunto.</span><span class="sxs-lookup"><span data-stu-id="b04ca-153">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
11. <span data-ttu-id="b04ca-154">Escolha o tipo do destino de backup clicando em **Disco**, **URL** ou **Fita**.</span><span class="sxs-lookup"><span data-stu-id="b04ca-154">Choose the type of backup destination by clicking **Disk**, **URL** or **Tape**.</span></span> <span data-ttu-id="b04ca-155">Para selecionar os caminhos de até 64 unidades de disco ou fita que contêm um único conjunto de mídia, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b04ca-155">To select the paths of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span> <span data-ttu-id="b04ca-156">Os caminhos selecionados são exibidos na caixa de listagem **Backup** .</span><span class="sxs-lookup"><span data-stu-id="b04ca-156">The selected paths are displayed in the **Backup to** list box.</span></span>  
  
     <span data-ttu-id="b04ca-157">Para remover um destino de backup, selecione-o e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="b04ca-157">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="b04ca-158">Para exibir o conteúdo de um destino de backup, selecione-o e clique em **Conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="b04ca-158">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
12. <span data-ttu-id="b04ca-159">Para exibir ou selecionar as opções avançadas, clique em **Opções** no painel **Selecionar uma página** .</span><span class="sxs-lookup"><span data-stu-id="b04ca-159">To view or select the advanced options, click **Options** in the **Select a page** pane.</span></span>  
  
13. <span data-ttu-id="b04ca-160">Selecione uma opção **Substituir Mídia** , com um clique em uma das opções a seguir:</span><span class="sxs-lookup"><span data-stu-id="b04ca-160">Select an **Overwrite Media** option, by clicking one of the following:</span></span>  
  
    -   <span data-ttu-id="b04ca-161">**Fazer backup no conjunto de mídias existente**</span><span class="sxs-lookup"><span data-stu-id="b04ca-161">**Back up to the existing media set**</span></span>  
  
         <span data-ttu-id="b04ca-162">Para essa opção, clique em **Anexar ao conjunto de backup existente** ou **Substituir todos os conjuntos de backup existentes**.</span><span class="sxs-lookup"><span data-stu-id="b04ca-162">For this option, click either **Append to the existing backup set** or **Overwrite all existing backup sets**.</span></span> <span data-ttu-id="b04ca-163">Para obter mais informações, veja [Conjuntos de mídias, famílias de mídia e conjuntos de backup &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b04ca-163">For more information, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
         <span data-ttu-id="b04ca-164">Opcionalmente, selecione **Verificar nome do conjunto de mídias e validade do conjunto de backup** para que a operação de backup verifique a data e a hora em que o conjunto de mídias e de backup expiram.</span><span class="sxs-lookup"><span data-stu-id="b04ca-164">Optionally, select **Check media set name and backup set expiration** to cause the backup operation to verify the date and time at which the media set and backup set expire.</span></span>  
  
         <span data-ttu-id="b04ca-165">Como opção, digite um nome na caixa de texto **Nome do conjunto de mídias** .</span><span class="sxs-lookup"><span data-stu-id="b04ca-165">Optionally, enter a name in the **Media set name** text box.</span></span> <span data-ttu-id="b04ca-166">Se nenhum nome for especificado, um conjunto de mídias com um nome em branco será criado.</span><span class="sxs-lookup"><span data-stu-id="b04ca-166">If no name is specified, a media set with a blank name is created.</span></span> <span data-ttu-id="b04ca-167">Se você especificar um nome de conjunto de mídias, a mídia (fita ou disco) é verificada para ver se o nome real corresponde ao nome digitado.</span><span class="sxs-lookup"><span data-stu-id="b04ca-167">If you specify a media set name, the media (tape or disk) is checked to see whether the actual name matches the name you enter here.</span></span>  
  
         <span data-ttu-id="b04ca-168">Se você deixar o nome da mídia em branco e marcar a caixa para verificar a mídia, a verificação terá sucesso se o nome da mídia também estiver em branco na mídia.</span><span class="sxs-lookup"><span data-stu-id="b04ca-168">If you leave the media name blank and check the box to check it against the media, success will equal the media name on the media also being blank.</span></span>  
  
    -   <span data-ttu-id="b04ca-169">**Fazer backup em um novo conjunto de mídias e apagar todos os conjuntos de backup existentes**</span><span class="sxs-lookup"><span data-stu-id="b04ca-169">**Back up to a new media set, and erase all existing backup sets**</span></span>  
  
         <span data-ttu-id="b04ca-170">Para essa opção, digite um nome na caixa de texto **Nome do novo conjunto de mídias** e, opcionalmente, descreva o conjunto de mídias na caixa de texto **Descrição do novo conjunto de mídias** .</span><span class="sxs-lookup"><span data-stu-id="b04ca-170">For this option, enter a name in the **New media set name** text box, and, optionally, describe the media set in the **New media set description** text box.</span></span> <span data-ttu-id="b04ca-171">Para obter mais informações, veja [Conjuntos de mídias, famílias de mídia e conjuntos de backup &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b04ca-171">For more information, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
14. <span data-ttu-id="b04ca-172">Na seção **Confiabilidade** , como opção, marque:</span><span class="sxs-lookup"><span data-stu-id="b04ca-172">In the **Reliability** section, optionally, check:</span></span>  
  
    -   <span data-ttu-id="b04ca-173">**Verificar backup quando concluído**</span><span class="sxs-lookup"><span data-stu-id="b04ca-173">**Verify backup when finished**.</span></span>  
  
    -   <span data-ttu-id="b04ca-174">**Executar soma de verificação antes de gravar na mídia**e, como opção, **Continuar com erro da soma de verificação**.</span><span class="sxs-lookup"><span data-stu-id="b04ca-174">**Perform checksum before writing to media**, and, optionally, **Continue on checksum error**.</span></span> <span data-ttu-id="b04ca-175">Para obter informações sobre somas de verificação, veja [Erros de mídia possíveis durante backup e restauração &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b04ca-175">For information on checksums, see [Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span></span>  
  
15. <span data-ttu-id="b04ca-176">Na seção **Log de transações** :</span><span class="sxs-lookup"><span data-stu-id="b04ca-176">In the **Transaction log** section:</span></span>  
  
    -   <span data-ttu-id="b04ca-177">Para fazer backups de log rotineiros, mantenha a seleção padrão **Truncar o log de transações removendo entradas inativas**.</span><span class="sxs-lookup"><span data-stu-id="b04ca-177">For routine log backups, keep the default selection, **Truncate the transaction log by removing inactive entries**.</span></span>  
  
    -   <span data-ttu-id="b04ca-178">Para fazer backup da parte final do log (ou seja, o log ativo), marque **Fazer backup da parte final do log e deixar o banco de dados no estado de restauração**.</span><span class="sxs-lookup"><span data-stu-id="b04ca-178">To back up the tail of the log (that is, the active log), check **Back up the tail of the log, and leave database in the restoring state**.</span></span>  
  
         <span data-ttu-id="b04ca-179">Um backup da parte final do log é realizado após a falha do backup final do log a fim de evitar perda de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b04ca-179">A tail-log backup is taken after a failure to back up the tail of the log in order to prevent work loss.</span></span> <span data-ttu-id="b04ca-180">Fazer backup de log ativo (backup da parte final do log) após uma falha, antes do início da restauração do banco de dados ou ao executar failover em um banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="b04ca-180">Back up the active log (a tail-log backup) both after a failure, before beginning to restore the database, or when failing over to a secondary database.</span></span> <span data-ttu-id="b04ca-181">Selecionar esta opção é equivalente a especificar a opção NORECOVERY na instrução BACKUP LOG do Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="b04ca-181">Selecting this option is equivalent to specifying the NORECOVERY option in the BACKUP LOG statement of Transact-SQL.</span></span> <span data-ttu-id="b04ca-182">Para obter mais informações sobre backups da parte final do log, veja [Backups da parte final do log &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b04ca-182">For more information about tail-log backups, see [Tail-Log Backups &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span></span>  
  
16. <span data-ttu-id="b04ca-183">Se o backup estiver sendo feito em uma unidade de fita (conforme especificado na seção **Destino** da página **Geral** ), a opção **Descarregar a fita após o backup** estará ativa.</span><span class="sxs-lookup"><span data-stu-id="b04ca-183">If you are backing up to a tape drive (as specified in the **Destination** section of the **General** page), the **Unload the tape after backup** option is active.</span></span> <span data-ttu-id="b04ca-184">Clicar nessa opção ativa a opção **Rebobinar a fita antes de descarregar** .</span><span class="sxs-lookup"><span data-stu-id="b04ca-184">Clicking this option activates the **Rewind the tape before unloading** option.</span></span>  
  
17. [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="b04ca-185">e posteriores dão suporte para [compactação de backup](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b04ca-185">and later supports [backup compression](backup-compression-sql-server.md).</span></span> <span data-ttu-id="b04ca-186">Por padrão, a compactação de um backup depende do valor da opção de configuração de servidor **padrão de compactação de backup**.</span><span class="sxs-lookup"><span data-stu-id="b04ca-186">By default, whether a backup is compressed depends on the value of the **backup-compression default** server configuration option.</span></span> <span data-ttu-id="b04ca-187">Porém, independentemente do padrão atual do nível do servidor, é possível compactar um backup, marcando a opção **Compactar backup**e evitar a compactação marcando **Não compactar o backup**.</span><span class="sxs-lookup"><span data-stu-id="b04ca-187">However, regardless of the current server-level default, you can compress a backup by checking **Compress backup**, and you can prevent compression by checking **Do not compress backup**.</span></span>  
  
     <span data-ttu-id="b04ca-188">**Para exibir o padrão de compactação de backup atual**</span><span class="sxs-lookup"><span data-stu-id="b04ca-188">**To view the current backup compression default**</span></span>  
  
    -   [<span data-ttu-id="b04ca-189">Exibir ou configurar a opção de configuração de servidor backup compression default</span><span class="sxs-lookup"><span data-stu-id="b04ca-189">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
 <span data-ttu-id="b04ca-190">**Criptografia**</span><span class="sxs-lookup"><span data-stu-id="b04ca-190">**Encryption**</span></span>  
  
 <span data-ttu-id="b04ca-191">Para criptografar o arquivo de backup, marque a caixa de seleção **Criptografar backup** .</span><span class="sxs-lookup"><span data-stu-id="b04ca-191">To encrypt the backup file check the **Encrypt backup** check box.</span></span> <span data-ttu-id="b04ca-192">Selecione um algoritmo de criptografia a ser usado para criptografar o arquivo de backup e forneça um Certificado ou uma Chave Assimétrica.</span><span class="sxs-lookup"><span data-stu-id="b04ca-192">Select an encryption algorithm to use for encrypting the backup file and provide a Certificate or Asymmetric key.</span></span> <span data-ttu-id="b04ca-193">Os algoritmos de criptografia disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="b04ca-193">The available algorithms for encryption are:</span></span>  
  
-   <span data-ttu-id="b04ca-194">AES 128</span><span class="sxs-lookup"><span data-stu-id="b04ca-194">AES 128</span></span>  
  
-   <span data-ttu-id="b04ca-195">AES 192</span><span class="sxs-lookup"><span data-stu-id="b04ca-195">AES 192</span></span>  
  
-   <span data-ttu-id="b04ca-196">AES 256</span><span class="sxs-lookup"><span data-stu-id="b04ca-196">AES 256</span></span>  
  
-   <span data-ttu-id="b04ca-197">DES triplo</span><span class="sxs-lookup"><span data-stu-id="b04ca-197">Triple DES</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b04ca-198">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b04ca-198">Using Transact-SQL</span></span>  
  
#### <a name="to-back-up-a-transaction-log"></a><span data-ttu-id="b04ca-199">Para fazer backup de um log de transações</span><span class="sxs-lookup"><span data-stu-id="b04ca-199">To back up a transaction log</span></span>  
  
1.  <span data-ttu-id="b04ca-200">Execute a instrução BACKUP LOG para fazer backup do log de transações, especificando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b04ca-200">Execute the BACKUP LOG statement to back up the transaction log, specifying the following:</span></span>  
  
    -   <span data-ttu-id="b04ca-201">O nome do banco de dados a que pertence o log de transações a ser feito backup.</span><span class="sxs-lookup"><span data-stu-id="b04ca-201">The name of the database to which the transaction log that you want to back up belongs.</span></span>  
  
    -   <span data-ttu-id="b04ca-202">O dispositivo de backup em que o backup de log de transações será gravado.</span><span class="sxs-lookup"><span data-stu-id="b04ca-202">The backup device where the transaction log backup is written.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="b04ca-203">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b04ca-203">Example (Transact-SQL)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b04ca-204">Este exemplo usa o banco de dados [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] , que usa o modelo de recuperação simples.</span><span class="sxs-lookup"><span data-stu-id="b04ca-204">This example uses the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database, which uses the simple recovery model.</span></span> <span data-ttu-id="b04ca-205">Para permitir backups de log, antes de fazer um backup de banco de dados completo, o banco de dados foi definido para usar o modelo de recuperação completa.</span><span class="sxs-lookup"><span data-stu-id="b04ca-205">To permit log backups, before taking a full database backup, the database was set to use the full recovery model.</span></span> <span data-ttu-id="b04ca-206">Para obter mais informações, veja [Exibir ou alterar o modelo de recuperação de um banco de dados &#40;SQL Server&#41;](view-or-change-the-recovery-model-of-a-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b04ca-206">For more information, see [View or Change the Recovery Model of a Database &#40;SQL Server&#41;](view-or-change-the-recovery-model-of-a-database-sql-server.md).</span></span>  
  
 <span data-ttu-id="b04ca-207">Este exemplo cria um backup de log de transações do banco de dados [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] para o dispositivo de backup criado anteriormente e denominado `MyAdvWorks_FullRM_log1`.</span><span class="sxs-lookup"><span data-stu-id="b04ca-207">This example creates a transaction log backup for the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database to the previously created named backup device, `MyAdvWorks_FullRM_log1`.</span></span>  
  
```sql  
BACKUP LOG AdventureWorks2012  
   TO MyAdvWorks_FullRM_log1;  
GO  
```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="b04ca-208">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="b04ca-208">Using PowerShell</span></span>  
  
<span data-ttu-id="b04ca-209">Use o cmdlet `Backup-SqlDatabase` e especifique `Log` para o valor do parâmetro `-BackupAction`.</span><span class="sxs-lookup"><span data-stu-id="b04ca-209">Use the `Backup-SqlDatabase` cmdlet and specify `Log` for the value of the `-BackupAction` parameter.</span></span>  
  
<span data-ttu-id="b04ca-210">O exemplo a seguir cria um backup do log do banco de dados `MyDB` para o local de backup padrão da instância de servidor `Computer\Instance`.</span><span class="sxs-lookup"><span data-stu-id="b04ca-210">The following example creates a log backup of the `MyDB` database to the default backup location of the server instance `Computer\Instance`.</span></span>  
  
    ```powershell
    Backup-SqlDatabase -ServerInstance Computer\Instance -Database MyDB -BackupAction Log  
    ```  
  
<span data-ttu-id="b04ca-211">Para configurar e usar o provedor de SQL Server PowerShell, consulte [provedor de SQL Server PowerShell](../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="b04ca-211">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../powershell/sql-server-powershell-provider.md).</span></span>
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="b04ca-212">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="b04ca-212">Related Tasks</span></span>  
  
-   [<span data-ttu-id="b04ca-213">Restaurar um backup de log de transações &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b04ca-213">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
-   [<span data-ttu-id="b04ca-214">Restaurar um banco de dados do SQL Server em um ponto específico &#40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="b04ca-214">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
-   [<span data-ttu-id="b04ca-215">Solução de problemas de um log de transação completa &#40;Erro do SQL Server 9002&#41;</span><span class="sxs-lookup"><span data-stu-id="b04ca-215">Troubleshoot a Full Transaction Log &#40;SQL Server Error 9002&#41;</span></span>](../logs/troubleshoot-a-full-transaction-log-sql-server-error-9002.md)  
  
## <a name="see-also"></a><span data-ttu-id="b04ca-216">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b04ca-216">See Also</span></span>  
 <span data-ttu-id="b04ca-217">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b04ca-217">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="b04ca-218">[Aplicar backups de log de transações &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b04ca-218">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="b04ca-219">[Planos de manutenção](../maintenance-plans/maintenance-plans.md) </span><span class="sxs-lookup"><span data-stu-id="b04ca-219">[Maintenance Plans](../maintenance-plans/maintenance-plans.md) </span></span>  
 [<span data-ttu-id="b04ca-220">Backups completos de arquivos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b04ca-220">Full File Backups &#40;SQL Server&#41;</span></span>](full-file-backups-sql-server.md)  
