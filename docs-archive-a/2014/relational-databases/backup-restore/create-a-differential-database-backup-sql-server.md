---
title: Criar um backup diferencial do banco de dados (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full differential backups [SQL Server]
- database backups [SQL Server], full differential backups
- backing up databases [SQL Server], full differential backups
- backups [SQL Server], creating
ms.assetid: 70f49794-b217-4519-9f2a-76ed61fa9f99
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2c3fb53d90ce633498bc518282d1ff03ce0b926e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583657"
---
# <a name="create-a-differential-database-backup-sql-server"></a><span data-ttu-id="960e7-102">Criar um backup diferencial de banco de dados (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="960e7-102">Create a Differential Database Backup (SQL Server)</span></span>
  <span data-ttu-id="960e7-103">Este tópico descreve como criar um backup de banco de dados diferencial no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="960e7-103">This topic describes how to create a differential database backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="960e7-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="960e7-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="960e7-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="960e7-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="960e7-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="960e7-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="960e7-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="960e7-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="960e7-108">Recomendações</span><span class="sxs-lookup"><span data-stu-id="960e7-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="960e7-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="960e7-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="960e7-110">**Para criar um backup de banco de dados diferencial usando:**</span><span class="sxs-lookup"><span data-stu-id="960e7-110">**To create a differential database backup, using:**</span></span>  
  
     [<span data-ttu-id="960e7-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="960e7-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="960e7-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="960e7-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="960e7-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="960e7-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="960e7-114">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="960e7-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="960e7-115">A instrução BACKUP não é permitida em uma transação explícita ou implícita.</span><span class="sxs-lookup"><span data-stu-id="960e7-115">The BACKUP statement is not allowed in an explicit or implicit transaction.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="960e7-116">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="960e7-116">Prerequisites</span></span>  
  
-   <span data-ttu-id="960e7-117">Para criar um backup diferencial de banco de dados é necessário um backup completo de banco de dados anterior.</span><span class="sxs-lookup"><span data-stu-id="960e7-117">Creating a differential database backup requires that a previous full database backup exist.</span></span> <span data-ttu-id="960e7-118">Se o banco de dados selecionado nunca foi salvo, faça um backup completo antes de criar qualquer backup diferencial.</span><span class="sxs-lookup"><span data-stu-id="960e7-118">If the selected database has never been backed up, run a full database backup before creating any differential backups.</span></span> <span data-ttu-id="960e7-119">Para obter mais informações, veja [Criar um backup completo de banco de dados &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="960e7-119">For more information, see [Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="960e7-120">Recomendações</span><span class="sxs-lookup"><span data-stu-id="960e7-120">Recommendations</span></span>  
  
-   <span data-ttu-id="960e7-121">Como os backups diferenciais aumentam em tamanho, a restauração de um backup diferencial pode aumentar de forma significativa o tempo necessário para restaurar um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="960e7-121">As the differential backups increase in size, restoring a differential backup can significantly increase the time that is required to restore a database.</span></span> <span data-ttu-id="960e7-122">Por isso, recomendamos que você use um backup completo novo em intervalos definidos para estabelecer uma nova base diferencial para os dados.</span><span class="sxs-lookup"><span data-stu-id="960e7-122">Therefore, we recommend that you take a new full backup at set intervals to establish a new differential base for the data.</span></span> <span data-ttu-id="960e7-123">Por exemplo, você poderia usar um backup completo semanal de todo o banco de dados (isto é, um backup completo do banco de dados) seguido de uma série regular de backups diferenciais do banco de dados durante a semana.</span><span class="sxs-lookup"><span data-stu-id="960e7-123">For example, you might take a weekly full backup of the whole database (that is, a full database backup) followed by a regular series of differential database backups during the week.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="960e7-124">Segurança</span><span class="sxs-lookup"><span data-stu-id="960e7-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="960e7-125">Permissões</span><span class="sxs-lookup"><span data-stu-id="960e7-125">Permissions</span></span>  
 <span data-ttu-id="960e7-126">As permissões BACKUP DATABASE e BACKUP LOG usam como padrão os membros da função de servidor fixa **sysadmin** e as funções de banco de dados fixas **db_owner** e **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="960e7-126">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="960e7-127">Os problemas de propriedade e permissão no arquivo físico do dispositivo de backup podem interferir em uma operação de backup.</span><span class="sxs-lookup"><span data-stu-id="960e7-127">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="960e7-128">deve ser capaz de ler e gravar no dispositivo; a conta sob a qual o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executa deve ter permissões de gravação.</span><span class="sxs-lookup"><span data-stu-id="960e7-128">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="960e7-129">No entanto, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), que adiciona uma entrada para um dispositivo de backup nas tabelas do sistema, não verifica permissões de acesso a arquivos.</span><span class="sxs-lookup"><span data-stu-id="960e7-129">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="960e7-130">Esses problemas no arquivo físico do dispositivo de backup podem não aparecer até que o recurso físico seja acessado quando o backup ou restauração é tentado.</span><span class="sxs-lookup"><span data-stu-id="960e7-130">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="960e7-131">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="960e7-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-differential-database-backup"></a><span data-ttu-id="960e7-132">Para criar um backup de banco de dados diferencial</span><span class="sxs-lookup"><span data-stu-id="960e7-132">To create a differential database backup</span></span>  
  
1.  <span data-ttu-id="960e7-133">Depois de se conectar à instância apropriada do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], em Pesquisador de Objetos, clique no nome do servidor para expandir a árvore do servidor.</span><span class="sxs-lookup"><span data-stu-id="960e7-133">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="960e7-134">Expanda **Bancos de Dados**e, dependendo do banco de dados, selecione um banco de usuário ou expanda **Bancos de Dados do Sistema** e selecione um banco do sistema.</span><span class="sxs-lookup"><span data-stu-id="960e7-134">Expand **Databases**, and depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="960e7-135">Clique com o botão direito do mouse no banco de dados, aponte para **Tarefas**e clique em **Backup**.</span><span class="sxs-lookup"><span data-stu-id="960e7-135">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="960e7-136">Será exibida a caixa de diálogo **Backup de Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="960e7-136">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="960e7-137">Na caixa de listagem **Banco de Dados** , verifique o nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="960e7-137">In the **Database** list box, verify the database name.</span></span> <span data-ttu-id="960e7-138">Você pode, como opção, selecionar um banco de dados diferente da lista.</span><span class="sxs-lookup"><span data-stu-id="960e7-138">You can optionally select a different database from the list.</span></span>  
  
     <span data-ttu-id="960e7-139">É possível executar um backup diferencial para qualquer modelo de recuperação (completo, bulk-logged ou simples).</span><span class="sxs-lookup"><span data-stu-id="960e7-139">You can perform a differential backup for any recovery model (full, bulk-logged, or simple).</span></span>  
  
5.  <span data-ttu-id="960e7-140">Na caixa de listagem **Tipo de backup** , selecione **Diferencial**.</span><span class="sxs-lookup"><span data-stu-id="960e7-140">In the **Backup type** list box, select **Differential**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="960e7-141"> Quando **Diferencial** está selecionado, verifique se a caixa de seleção **Copiar Somente Backup** está desmarcada.</span><span class="sxs-lookup"><span data-stu-id="960e7-141">When **Differential** is selected, verify that the **Copy Only Backup** check box is cleared.</span></span>  
  
6.  <span data-ttu-id="960e7-142">Para **Componente de backup**, clique em **Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="960e7-142">For **Backup component**, click **Database**.</span></span>  
  
7.  <span data-ttu-id="960e7-143">Aceite o nome do conjunto de backup padrão sugerido na caixa de texto **Nome** ou digite um nome diferente para o conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="960e7-143">Either accept the default backup set name suggested in the **Name** text box, or enter a different name for the backup set.</span></span>  
  
8.  <span data-ttu-id="960e7-144">Opcionalmente, na caixa de texto **Descrição** , digite uma descrição do conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="960e7-144">Optionally, in the **Description** text box, enter a description of the backup set.</span></span>  
  
9. <span data-ttu-id="960e7-145">Especifique quando o conjunto de backup irá expirar:</span><span class="sxs-lookup"><span data-stu-id="960e7-145">Specify when the backup set will expire:</span></span>  
  
    -   <span data-ttu-id="960e7-146">Para que o conjunto de backup expire depois de um número específico de dias, clique em **Depois** (a opção padrão) e digite quantos dias depois da criação do conjunto ele deve expirar.</span><span class="sxs-lookup"><span data-stu-id="960e7-146">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="960e7-147">Esse valor pode ser de 0 a 99999 dias; 0 dia significa que o conjunto de backup nunca vai expirar.</span><span class="sxs-lookup"><span data-stu-id="960e7-147">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="960e7-148">O valor padrão é definido na opção **Retenção de mídia de backup padrão (em dias)** da caixa de diálogo **Propriedades do Servidor** (página**Configurações do Banco de Dados** ).</span><span class="sxs-lookup"><span data-stu-id="960e7-148">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (**Database Settings** page).</span></span> <span data-ttu-id="960e7-149">Para acessar, clique com o botão direito do mouse no nome do servidor em Pesquisador de Objetos e selecione propriedades. Depois, selecione a página **Configurações de Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="960e7-149">To access this, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="960e7-150">Para que o conjunto de backup expire em uma data específica, clique no campo **Em**e digite a data de expiração do conjunto.</span><span class="sxs-lookup"><span data-stu-id="960e7-150">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
10. <span data-ttu-id="960e7-151">Escolha o tipo do destino de backup clicando em **Disco** ou **Fita**.</span><span class="sxs-lookup"><span data-stu-id="960e7-151">Choose the type of backup destination by clicking **Disk** or **Tape**.</span></span> <span data-ttu-id="960e7-152">Para selecionar o caminho de até 64 unidades de disco ou de fita que contém um único conjunto de mídias, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="960e7-152">To select the path of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span> <span data-ttu-id="960e7-153">Os caminhos selecionados são exibidos na caixa de listagem **Backup** .</span><span class="sxs-lookup"><span data-stu-id="960e7-153">The selected paths are displayed in the **Backup to** list box.</span></span>  
  
     <span data-ttu-id="960e7-154">Para remover um destino de backup, selecione-o e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="960e7-154">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="960e7-155">Para exibir o conteúdo de um destino de backup, selecione-o e clique em **Conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="960e7-155">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
11. <span data-ttu-id="960e7-156">Para exibir ou selecionar as opções avançadas, clique em **Opções** no painel **Selecionar uma página** .</span><span class="sxs-lookup"><span data-stu-id="960e7-156">To view or select the advanced options, click **Options** in the **Select a page** pane.</span></span>  
  
12. <span data-ttu-id="960e7-157">Selecione uma opção **Substituir Mídia** , com um clique em uma das opções a seguir:</span><span class="sxs-lookup"><span data-stu-id="960e7-157">Select an **Overwrite Media** option, by clicking one of the following:</span></span>  
  
    -   <span data-ttu-id="960e7-158">**Fazer backup no conjunto de mídias existente**</span><span class="sxs-lookup"><span data-stu-id="960e7-158">**Back up to the existing media set**</span></span>  
  
         <span data-ttu-id="960e7-159">Para essa opção, clique em **Anexar ao conjunto de backup existente** ou **Substituir todos os conjuntos de backup existentes**.</span><span class="sxs-lookup"><span data-stu-id="960e7-159">For this option, click either **Append to the existing backup set** or **Overwrite all existing backup sets**.</span></span> <span data-ttu-id="960e7-160">Como opção, marque a caixa de verificação **Verificar nome do conjunto de mídias e validade do conjunto de backup** e especifique a caixa de texto do **Nome do conjunto de mídias** .</span><span class="sxs-lookup"><span data-stu-id="960e7-160">Optionally, check the **Check media set name and backup set expiration** check box and, optionally, enter a name in the **Media set name** text box.</span></span> <span data-ttu-id="960e7-161">Se nenhum nome for especificado, um conjunto de mídias com um nome em branco será criado.</span><span class="sxs-lookup"><span data-stu-id="960e7-161">If no name is specified, a media set with a blank name is created.</span></span> <span data-ttu-id="960e7-162">Se você especificar um nome de conjunto de mídias, a mídia (fita ou disco) será verificada para conferir se o nome real corresponde ao nome inserido aqui.</span><span class="sxs-lookup"><span data-stu-id="960e7-162">If you specify a media set name, the media (tape or disk) is checked to see if the actual name matches the name you enter here.</span></span>  
  
         <span data-ttu-id="960e7-163">Se você deixar o nome da mídia em branco e marcar a caixa para verificar a mídia, a verificação terá sucesso se o nome da mídia também estiver em branco na mídia.</span><span class="sxs-lookup"><span data-stu-id="960e7-163">If you leave the media name blank and check the box to check it against the media, success will equal the media name on the media also being blank.</span></span>  
  
    -   <span data-ttu-id="960e7-164">**Fazer backup em um novo conjunto de mídias e apagar todos os conjuntos de backup existentes**</span><span class="sxs-lookup"><span data-stu-id="960e7-164">**Back up to a new media set, and erase all existing backup sets**</span></span>  
  
         <span data-ttu-id="960e7-165">Para essa opção, digite um nome na caixa de texto **Nome do novo conjunto de mídias** e, opcionalmente, descreva o conjunto de mídias na caixa de texto **Descrição do novo conjunto de mídias** .</span><span class="sxs-lookup"><span data-stu-id="960e7-165">For this option, enter a name in the **New media set name** text box, and, optionally, describe the media set in the **New media set description** text box.</span></span>  
  
13. <span data-ttu-id="960e7-166">Na seção **Confiabilidade** , como opção, marque:</span><span class="sxs-lookup"><span data-stu-id="960e7-166">In the **Reliability** section, optionally, check:</span></span>  
  
    -   <span data-ttu-id="960e7-167">**Verificar backup quando concluído**</span><span class="sxs-lookup"><span data-stu-id="960e7-167">**Verify backup when finished**.</span></span>  
  
    -   <span data-ttu-id="960e7-168">**Executar soma de verificação antes de gravar na mídia**e, como opção, **Continuar com erro da soma de verificação**.</span><span class="sxs-lookup"><span data-stu-id="960e7-168">**Perform checksum before writing to media**, and, optionally, **Continue on checksum error**.</span></span> <span data-ttu-id="960e7-169">Para obter informações sobre somas de verificação, consulte [Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md) [Possíveis erros de mídia durante backup e restauração (SQL Server)].</span><span class="sxs-lookup"><span data-stu-id="960e7-169">For information about checksums, see [Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span></span>  
  
14. <span data-ttu-id="960e7-170">Se o backup estiver sendo feito em uma unidade de fita (conforme especificado na seção **Destino** da página **Geral** ), a opção **Descarregar a fita após o backup** estará ativa.</span><span class="sxs-lookup"><span data-stu-id="960e7-170">If you are backing up to a tape drive (as specified in the **Destination** section of the **General** page), the **Unload the tape after backup** option is active.</span></span> <span data-ttu-id="960e7-171">Clicar nessa opção ativa a opção **Rebobinar a fita antes de descarregar** .</span><span class="sxs-lookup"><span data-stu-id="960e7-171">Clicking this option activates the **Rewind the tape before unloading** option.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="960e7-172">As opções na seção **Log de transações** estarão inativos exceto se o backup estiver sendo feito em um log de transações (como especificado na seção **Tipo de backup** da página **Geral** ).</span><span class="sxs-lookup"><span data-stu-id="960e7-172">The options in the **Transaction log** section are inactive unless you are backing up a transaction log (as specified in the **Backup type** section of the **General** page).</span></span>  
  
15. [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="960e7-173">e posteriores dão suporte para [compactação de backup](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="960e7-173">and later supports [backup compression](backup-compression-sql-server.md).</span></span> <span data-ttu-id="960e7-174">Por padrão, a compactação de um backup depende do valor da opção de configuração de servidor **padrão de compactação de backup**.</span><span class="sxs-lookup"><span data-stu-id="960e7-174">By default, whether a backup is compressed depends on the value of the **backup-compression default** server configuration option.</span></span> <span data-ttu-id="960e7-175">Porém, independentemente do padrão atual do nível do servidor, é possível compactar um backup, marcando a opção **Compactar backup**e evitar a compactação marcando **Não compactar o backup**.</span><span class="sxs-lookup"><span data-stu-id="960e7-175">However, regardless of the current server-level default, you can compress a backup by checking **Compress backup**, and you can prevent compression by checking **Do not compress backup**.</span></span>  
  
     <span data-ttu-id="960e7-176">**Para exibir o padrão de compactação de backup atual**</span><span class="sxs-lookup"><span data-stu-id="960e7-176">**To view the current backup compression default**</span></span>  
  
    -   [<span data-ttu-id="960e7-177">Exibir ou configurar a opção de configuração de servidor backup compression default</span><span class="sxs-lookup"><span data-stu-id="960e7-177">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
    > [!NOTE]  
    >  <span data-ttu-id="960e7-178">Como alternativa, é possível usar o Assistente para Plano de Manutenção para criar backups de banco de dados diferenciais.</span><span class="sxs-lookup"><span data-stu-id="960e7-178">Alternatively, you can use the Maintenance Plan Wizard to create differential database backups.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="960e7-179">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="960e7-179">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-differential-database-backup"></a><span data-ttu-id="960e7-180">Para criar um backup de banco de dados diferencial</span><span class="sxs-lookup"><span data-stu-id="960e7-180">To create a differential database backup</span></span>  
  
1.  <span data-ttu-id="960e7-181">Execute a instrução BACKUP DATABASE para criar o backup de banco de dados diferencial, especificando:</span><span class="sxs-lookup"><span data-stu-id="960e7-181">Execute the BACKUP DATABASE statement to create the differential database backup, specifying:</span></span>  
  
    -   <span data-ttu-id="960e7-182">O nome do banco de dados do qual fazer backup.</span><span class="sxs-lookup"><span data-stu-id="960e7-182">The name of the database to back up.</span></span>  
  
    -   <span data-ttu-id="960e7-183">O dispositivo de backup em que o backup completo do banco de dados será gravado.</span><span class="sxs-lookup"><span data-stu-id="960e7-183">The backup device where the full database backup is written.</span></span>  
  
    -   <span data-ttu-id="960e7-184">A cláusula DIFFERENTIAL, para especificar que o backup só será feito nas partes do banco de dados que foram alteradas depois da criação do último backup completo.</span><span class="sxs-lookup"><span data-stu-id="960e7-184">The DIFFERENTIAL clause, to specify that only the parts of the database that have changed after the last full database backup was created are backed up.</span></span>  
  
     <span data-ttu-id="960e7-185">A sintaxe necessária é:</span><span class="sxs-lookup"><span data-stu-id="960e7-185">The required syntax is:</span></span>  
  
     <span data-ttu-id="960e7-186">BACKUP DATABASE *database_name* TO <backup_device> WITH DIFFERENTIAL</span><span class="sxs-lookup"><span data-stu-id="960e7-186">BACKUP DATABASE *database_name* TO <backup_device> WITH DIFFERENTIAL</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="960e7-187">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="960e7-187">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="960e7-188">Este exemplo cria um backup completo e diferencial de banco de dados para o banco de dados `MyAdvWorks` .</span><span class="sxs-lookup"><span data-stu-id="960e7-188">This example creates a full and a differential database backup for the `MyAdvWorks` database.</span></span>  
  
```sql  
-- Create a full database backup first.  
BACKUP DATABASE MyAdvWorks   
   TO MyAdvWorks_1   
   WITH INIT;  
GO  
-- Time elapses.  
-- Create a differential database backup, appending the backup  
-- to the backup device containing the full database backup.  
BACKUP DATABASE MyAdvWorks  
   TO MyAdvWorks_1  
   WITH DIFFERENTIAL;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="960e7-189">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="960e7-189">See Also</span></span>  
 <span data-ttu-id="960e7-190">[Backups diferenciais &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="960e7-190">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="960e7-191">[Criar um backup completo de banco de dados &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="960e7-191">[Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="960e7-192">[Fazer backup de arquivos e de grupos de arquivos &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="960e7-192">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="960e7-193">[Restaurar um backup de banco de dados diferencial &#40;SQL Server&#41;](restore-a-differential-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="960e7-193">[Restore a Differential Database Backup &#40;SQL Server&#41;](restore-a-differential-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="960e7-194">[Restaurar um backup de log de transações &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="960e7-194">[Restore a Transaction Log Backup &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span></span>  
 <span data-ttu-id="960e7-195">[Planos de manutenção](../maintenance-plans/maintenance-plans.md) </span><span class="sxs-lookup"><span data-stu-id="960e7-195">[Maintenance Plans](../maintenance-plans/maintenance-plans.md) </span></span>  
 [<span data-ttu-id="960e7-196">Backups completos de arquivos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="960e7-196">Full File Backups &#40;SQL Server&#41;</span></span>](full-file-backups-sql-server.md)  
  
  
