---
title: Exibir ou configurar a opção de configuração de servidor backup compression default | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], backup compression default option
- backup compression [SQL Server], backup compression default Option
ms.assetid: 23029395-3e93-4c29-b7d6-e5a47a3526ff
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f02458c069d7c155b199e24feb7ef028ae0f258a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583821"
---
# <a name="view-or-configure-the-backup-compression-default-server-configuration-option"></a><span data-ttu-id="7fbbf-102">Exibir ou configurar a opção de configuração de servidor backup compression default</span><span class="sxs-lookup"><span data-stu-id="7fbbf-102">View or Configure the backup compression default Server Configuration Option</span></span>
  <span data-ttu-id="7fbbf-103">Este tópico descreve como exibir ou configurar a opção de configuração de servidor **padrão de compactação de backup** em [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7fbbf-103">This topic describes how to view or configure the **backup compression default** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="7fbbf-104">A opção de **padrão de compactação de backup** determina se a instância de servidor cria backups compactados por padrão.</span><span class="sxs-lookup"><span data-stu-id="7fbbf-104">The **backup compression default** option determines whether the server instance creates compressed backups by default.</span></span> <span data-ttu-id="7fbbf-105">Quando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está instalado, a opção de **padrão de compactação de backup** está desativada.</span><span class="sxs-lookup"><span data-stu-id="7fbbf-105">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed, the **backup compression default** option is off.</span></span>  
  
 <span data-ttu-id="7fbbf-106">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="7fbbf-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7fbbf-107">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="7fbbf-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7fbbf-108">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="7fbbf-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="7fbbf-109">Recomendações</span><span class="sxs-lookup"><span data-stu-id="7fbbf-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="7fbbf-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="7fbbf-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7fbbf-111">**Para exibir ou configurar a opção padrão de compactação de backup usando:**</span><span class="sxs-lookup"><span data-stu-id="7fbbf-111">**To view or configure the backup compression default option, using:**</span></span>  
  
     [<span data-ttu-id="7fbbf-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7fbbf-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7fbbf-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7fbbf-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="7fbbf-114">**Acompanhamento:**  [Depois de configurar a opção backup compression default](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="7fbbf-114">**Follow Up:**  [After you configure the backup compression default option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7fbbf-115">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="7fbbf-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="7fbbf-116">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="7fbbf-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="7fbbf-117">A compactação de backup não está disponível em todas as edições do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7fbbf-117">Backup compression is not available in all editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7fbbf-118">Para obter mais informações, consulte [recursos com suporte nas edições do SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="7fbbf-118">For more information, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
-   <span data-ttu-id="7fbbf-119">Por padrão, a compactação aumenta consideravelmente o uso da CPU, e o consumo adicional da CPU por parte do processo de compactação pode afetar negativamente as operações simultâneas.</span><span class="sxs-lookup"><span data-stu-id="7fbbf-119">By default, compression significantly increases CPU usage, and the additional CPU consumed by the compression process might adversely impact concurrent operations.</span></span> <span data-ttu-id="7fbbf-120">Portanto, é recomendável criar backups compactados de baixa prioridade em uma sessão cujo uso da CPU é limitado pelo [Administrador de Recursos](../../relational-databases/resource-governor/resource-governor.md).</span><span class="sxs-lookup"><span data-stu-id="7fbbf-120">Therefore, you might want to create low-priority compressed backups in a session whose CPU usage is limited by [Resource Governor](../../relational-databases/resource-governor/resource-governor.md).</span></span> <span data-ttu-id="7fbbf-121">Para obter mais informações, consulte [Usar o Resource Governor para limitar o uso de CPU por meio de compactação de backup &#40;Transact-SQL&#41;](../../relational-databases/backup-restore/use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="7fbbf-121">For more information, see [Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;](../../relational-databases/backup-restore/use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="7fbbf-122">Recomendações</span><span class="sxs-lookup"><span data-stu-id="7fbbf-122">Recommendations</span></span>  
  
-   <span data-ttu-id="7fbbf-123">Ao criar um backup individual, definir uma configuração de envio de logs ou criar um plano de manutenção, é possível substituir o padrão do nível de servidor.</span><span class="sxs-lookup"><span data-stu-id="7fbbf-123">When you are creating an individual backup, configuring a log shipping configuration, or creating a maintenance plan, you can override the server-level default.</span></span>  
  
-   <span data-ttu-id="7fbbf-124">Compactação de backup tem suporte tanto para dispositivos de backup de disco como para dispositivos de backup de fita.</span><span class="sxs-lookup"><span data-stu-id="7fbbf-124">Backup compression is supported for both disk backup devices and tape backup devices.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7fbbf-125">Segurança</span><span class="sxs-lookup"><span data-stu-id="7fbbf-125">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7fbbf-126">Permissões</span><span class="sxs-lookup"><span data-stu-id="7fbbf-126">Permissions</span></span>  
 <span data-ttu-id="7fbbf-127">Permissões de execução sem parâmetros ou com apenas o primeiro parâmetro em **sp_configure** são concedidas a todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="7fbbf-127">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="7fbbf-128">Para executar **sp_configure** com ambos os parâmetros para alterar uma opção de configuração ou executar a instrução RECONFIGURE, o usuário deve ter a permissão ALTER SETTINGS no nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="7fbbf-128">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="7fbbf-129">A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="7fbbf-129">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7fbbf-130">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7fbbf-130">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-configure-the-backup-compression-default-option"></a><span data-ttu-id="7fbbf-131">Para exibir ou configurar a opção padrão de compactação de backup</span><span class="sxs-lookup"><span data-stu-id="7fbbf-131">To view or configure the backup compression default option</span></span>  
  
1.  <span data-ttu-id="7fbbf-132">No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="7fbbf-132">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="7fbbf-133">Clique no nó **Configurações de Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="7fbbf-133">Click the **Database settings** node.</span></span>  
  
3.  <span data-ttu-id="7fbbf-134">Em **Backup e restauração**, **Compactar backup** mostra a configuração atual da opção de **padrão de compactação de backup** .</span><span class="sxs-lookup"><span data-stu-id="7fbbf-134">Under **Backup and restore**, **Compress backup** shows the current setting of the **backup compression default** option.</span></span> <span data-ttu-id="7fbbf-135">Essa configuração determina o padrão do nível de servidor para backups compactados, como segue:</span><span class="sxs-lookup"><span data-stu-id="7fbbf-135">This setting determines the server-level default for compressing backups, as follows:</span></span>  
  
    -   <span data-ttu-id="7fbbf-136">Se a caixa **Compactar backup** estiver em branco, novos backups são descompactados por padrão.</span><span class="sxs-lookup"><span data-stu-id="7fbbf-136">If the **Compress backup** box is blank, new backups are uncompressed by default.</span></span>  
  
    -   <span data-ttu-id="7fbbf-137">Se a caixa **Compactar backup** estiver marcada, novos backups serão compactados por padrão.</span><span class="sxs-lookup"><span data-stu-id="7fbbf-137">If the **Compress backup** box is checked, new backups are compressed by default.</span></span>  
  
     <span data-ttu-id="7fbbf-138">Se você for membro da função de servidor fixa **sysadmin** ou **serveradmin** , também será possível alterar a configuração padrão clicando na caixa **Compactar backup** .</span><span class="sxs-lookup"><span data-stu-id="7fbbf-138">If you are a member of the **sysadmin** or **serveradmin** fixed server role, you can also change the default setting by clicking the **Compress backup** box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7fbbf-139">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7fbbf-139">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-backup-compression-default-option"></a><span data-ttu-id="7fbbf-140">Para exibir a opção padrão de compactação de backup</span><span class="sxs-lookup"><span data-stu-id="7fbbf-140">To view the backup compression default option</span></span>  
  
1.  <span data-ttu-id="7fbbf-141">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7fbbf-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7fbbf-142">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="7fbbf-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7fbbf-143">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="7fbbf-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="7fbbf-144">Este exemplo consulta a exibição de catálogo [sys.configurations](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) para determinar o valor de `backup compression default`.</span><span class="sxs-lookup"><span data-stu-id="7fbbf-144">This example queries the [sys.configurations](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) catalog view to determine the value for `backup compression default`.</span></span> <span data-ttu-id="7fbbf-145">O valor 0 significa que a compactação de backup está desativada e o valor 1 significa que a compactação de backup está habilitada.</span><span class="sxs-lookup"><span data-stu-id="7fbbf-145">A value of 0 means that backup compression is off, and a value of 1 means that backup compression is enabled.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
SELECT value   
FROM sys.configurations   
WHERE name = 'backup compression default' ;  
GO  
  
```  
  
#### <a name="to-configure-the-backup-compression-default-option"></a><span data-ttu-id="7fbbf-146">Para configurar a opção padrão de compactação de backup</span><span class="sxs-lookup"><span data-stu-id="7fbbf-146">To configure the backup compression default option</span></span>  
  
1.  <span data-ttu-id="7fbbf-147">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7fbbf-147">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7fbbf-148">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="7fbbf-148">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7fbbf-149">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="7fbbf-149">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="7fbbf-150">Este exemplo mostra como usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para configurar a instância de servidor para criar backups compactados por padrão.</span><span class="sxs-lookup"><span data-stu-id="7fbbf-150">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the server instance to create compressed backups by default.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_configure 'backup compression default', 1 ;  
RECONFIGURE WITH OVERRIDE ;  
GO  
  
```  
  
 <span data-ttu-id="7fbbf-151">Para obter mais informações, veja [Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7fbbf-151">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-backup-compression-default-option"></a><a name="FollowUp"></a> <span data-ttu-id="7fbbf-152">Acompanhamento: Depois de configurar a opção backup compression default</span><span class="sxs-lookup"><span data-stu-id="7fbbf-152">Follow Up: After you configure the backup compression default option</span></span>  
 <span data-ttu-id="7fbbf-153">A configuração entra em vigor imediatamente sem reiniciar o servidor.</span><span class="sxs-lookup"><span data-stu-id="7fbbf-153">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fbbf-154">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7fbbf-154">See Also</span></span>  
 <span data-ttu-id="7fbbf-155">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7fbbf-155">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="7fbbf-156">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7fbbf-156">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="7fbbf-157">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7fbbf-157">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="7fbbf-158">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7fbbf-158">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="7fbbf-159">Visão geral do backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7fbbf-159">Backup Overview &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/backup-overview-sql-server.md)  
  
  
