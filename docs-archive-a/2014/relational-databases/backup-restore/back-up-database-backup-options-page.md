---
title: Fazer backup de banco de dados (página Opções de Backup) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.backupdatabase.options.f1
- swb.backupdatabase.options.f1
ms.assetid: df0ddcdb-c94e-472b-b786-469ae8117b93
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ffd527ba4334244c7fd4c5d4a73099093cb8520b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583680"
---
# <a name="back-up-database-backup-options-page"></a><span data-ttu-id="dae77-102">Backup de Banco de Dados (página Opções de Backup)</span><span class="sxs-lookup"><span data-stu-id="dae77-102">Back Up Database (Backup Options Page)</span></span>
  <span data-ttu-id="dae77-103">Use a página  **Opções de Backup** da caixa de diálogo **Backup de Banco de Dados** para exibir ou modificar opções de backup de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="dae77-103">Use the  **Backup Options** page of the **Back Up Database** dialog box to view or modify database backup options.</span></span>  
  
 <span data-ttu-id="dae77-104">**Para criar um backup usando o SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="dae77-104">**To create a backup by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="dae77-105">Criar um backup completo de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dae77-105">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="dae77-106">Criar um backup diferencial de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dae77-106">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
> [!IMPORTANT]  
>  <span data-ttu-id="dae77-107">Você pode definir um plano de manutenção de banco de dados para criar backups de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="dae77-107">You can define a database maintenance plan to create database backups.</span></span> <span data-ttu-id="dae77-108">Para obter mais informações, consulte [Planos de Manutenção](../maintenance-plans/maintenance-plans.md) e [Usar o Assistente de Plano de Manutenção](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="dae77-108">For more information, see [Maintenance Plans](../maintenance-plans/maintenance-plans.md) and [Use the Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dae77-109">Ao especificar uma tarefa de backup usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], é possível gerar o script [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) correspondente clicando no botão **Script** e selecionando um destino para o script.</span><span class="sxs-lookup"><span data-stu-id="dae77-109">When you specify a backup task by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you can generate the corresponding [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) script by clicking the **Script** button and then selecting a destination for the script.</span></span>  
  
## <a name="options"></a><span data-ttu-id="dae77-110">Opções</span><span class="sxs-lookup"><span data-stu-id="dae77-110">Options</span></span>  
  
### <a name="backup-set"></a><span data-ttu-id="dae77-111">Conjunto de backup</span><span class="sxs-lookup"><span data-stu-id="dae77-111">Backup set</span></span>  
 <span data-ttu-id="dae77-112">As opções do painel **Conjunto de backup** permitem especificar informações opcionais sobre o conjunto de backup criado pela operação de backup.</span><span class="sxs-lookup"><span data-stu-id="dae77-112">The options of the **Backup set** panel allow for you to specify optional information about the backup set created by the back up operation.</span></span>  
  
 <span data-ttu-id="dae77-113">**Nome**</span><span class="sxs-lookup"><span data-stu-id="dae77-113">**Name**</span></span>  
 <span data-ttu-id="dae77-114">Especifique o nome do conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="dae77-114">Specify the backup set name.</span></span> <span data-ttu-id="dae77-115">O sistema sugere automaticamente um nome padrão com base no nome do banco de dados e no tipo de backup.</span><span class="sxs-lookup"><span data-stu-id="dae77-115">The system automatically suggests a default name based on the database name and the backup type.</span></span>  
  
 <span data-ttu-id="dae77-116">Para obter informações sobre conjuntos de backup, consulte [Conjuntos de mídias, famílias de mídia e conjuntos de backup &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="dae77-116">For information about backup sets, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
 <span data-ttu-id="dae77-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="dae77-117">**Description**</span></span>  
 <span data-ttu-id="dae77-118">Insira uma descrição do conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="dae77-118">Enter a description of the backup set.</span></span>  
  
 <span data-ttu-id="dae77-119">**O conjunto de backup vai expirar**</span><span class="sxs-lookup"><span data-stu-id="dae77-119">**Backup set will expire**</span></span>  
 <span data-ttu-id="dae77-120">Escolha uma das opções de validade a seguir.</span><span class="sxs-lookup"><span data-stu-id="dae77-120">Choose one of the following expiration options.</span></span> <span data-ttu-id="dae77-121">Essa opção será desabilitada se a opção **URL** for escolhida como destino do backup.</span><span class="sxs-lookup"><span data-stu-id="dae77-121">This option is disabled if **URL** is chosen as the backup destination.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dae77-122">**Depois**</span><span class="sxs-lookup"><span data-stu-id="dae77-122">**After**</span></span>|<span data-ttu-id="dae77-123">Especifique o número de dias que devem decorrer antes de o conjunto de backup expirar e poder ser substituído.</span><span class="sxs-lookup"><span data-stu-id="dae77-123">Specify the number of days that must elapse before this backup set expires and can be overwritten.</span></span> <span data-ttu-id="dae77-124">Esse valor pode ser de 0 a 99999 dias; 0 dia significa que o conjunto de backup nunca vai expirar.</span><span class="sxs-lookup"><span data-stu-id="dae77-124">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span><br /><br /> <span data-ttu-id="dae77-125">O valor padrão de validade do backup é o valor definido na opção **Retenção de mídia de backup padrão (em dias)** .</span><span class="sxs-lookup"><span data-stu-id="dae77-125">The default value for backup expiration is the value set in the **Default backup media retention (in days)** option.</span></span> <span data-ttu-id="dae77-126">Para acessá-la, clique com o botão direito do mouse no nome do servidor no Pesquisador de Objetos e selecione **Propriedades**; em seguida, clique na página **Definições de banco de dados** da caixa de diálogo **Propriedades do servidor** .</span><span class="sxs-lookup"><span data-stu-id="dae77-126">To access this, right-click the server name in Object Explorer and select **Properties**; then click the **Database Settings** page of the **Server Properties** dialog box.</span></span>|  
|<span data-ttu-id="dae77-127">**Em**</span><span class="sxs-lookup"><span data-stu-id="dae77-127">**On**</span></span>|<span data-ttu-id="dae77-128">Defina uma data específica em que o conjunto de backup deverá expirar e poderá ser substituído.</span><span class="sxs-lookup"><span data-stu-id="dae77-128">Specify a specific date when the backup set expires and can be overwritten.</span></span>|  
  
### <a name="compression"></a><span data-ttu-id="dae77-129">Compactação</span><span class="sxs-lookup"><span data-stu-id="dae77-129">Compression</span></span>  
 [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="dae77-130">(ou uma versão posterior) dá suporte à [compactação de backup](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="dae77-130">(or a later version) supports [backup compression](backup-compression-sql-server.md).</span></span>  
  
 <span data-ttu-id="dae77-131">**Defina compactação de backup**</span><span class="sxs-lookup"><span data-stu-id="dae77-131">**Set backup compression**</span></span>  
 <span data-ttu-id="dae77-132">No [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] (ou em uma versão posterior), selecione um dos seguintes valores de compactação de backup:</span><span class="sxs-lookup"><span data-stu-id="dae77-132">In [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] (or a later version), select one of the following backup compression values:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dae77-133">**Usar a configuração padrão do servidor**</span><span class="sxs-lookup"><span data-stu-id="dae77-133">**Use the default server setting**</span></span>|<span data-ttu-id="dae77-134">Clique para usar o padrão do nível de servidor.</span><span class="sxs-lookup"><span data-stu-id="dae77-134">Click to use the server-level default.</span></span><br /><br /> <span data-ttu-id="dae77-135">Esse padrão é definido pela opção de configuração do servidor **padrão de compactação de backup** .</span><span class="sxs-lookup"><span data-stu-id="dae77-135">This default is set by the **backup compression default** server-configuration option.</span></span> <span data-ttu-id="dae77-136">Para obter informações sobre como exibir a configuração atual dessa opção, consulte [Exibir ou configurar a opção de configuração de servidor backup compression default](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="dae77-136">For information about how to view the current setting of this option, see [View or Configure the backup compression default Server Configuration Option](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span></span>|  
|<span data-ttu-id="dae77-137">**Compactar backup**</span><span class="sxs-lookup"><span data-stu-id="dae77-137">**Compress backup**</span></span>|<span data-ttu-id="dae77-138">Clique em compactar backup, independentemente do padrão do nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="dae77-138">Click to compress the backup, regardless of the server-level default.</span></span><br /><br /> <span data-ttu-id="dae77-139">**\*\* Importante \*\*** Por padrão, a compactação aumenta consideravelmente o uso da CPU, e o consumo adicional da CPU por parte do processo de compactação poderá afetar negativamente as operações simultâneas.</span><span class="sxs-lookup"><span data-stu-id="dae77-139">**\*\* Important \*\*** By default, compression significantly increases CPU usage, and the additional CPU consumed by the compression process might adversely impact concurrent operations.</span></span> <span data-ttu-id="dae77-140">Portanto, é recomendável criar backups compactados de baixa prioridade em uma sessão cujo uso da CPU é limitado pelo [Administrador de Recursos](../resource-governor/resource-governor.md).</span><span class="sxs-lookup"><span data-stu-id="dae77-140">Therefore, you might want to create low-priority compressed backups in a session whose CPU usage is limited by [Resource Governor](../resource-governor/resource-governor.md).</span></span> <span data-ttu-id="dae77-141">Para obter mais informações, consulte [Usar o Resource Governor para limitar o uso de CPU por meio de compactação de backup &#40;Transact-SQL&#41;](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="dae77-141">For more information, see [Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span></span>|  
|<span data-ttu-id="dae77-142">**Não compactar o backup**</span><span class="sxs-lookup"><span data-stu-id="dae77-142">**Do not compress backup**</span></span>|<span data-ttu-id="dae77-143">Clique em criar um backup não compactado, independentemente do padrão do nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="dae77-143">Click to create an uncompressed backup, regardless of the server-level default.</span></span>|  
  
### <a name="encryption"></a><span data-ttu-id="dae77-144">Criptografia</span><span class="sxs-lookup"><span data-stu-id="dae77-144">Encryption</span></span>  
 <span data-ttu-id="dae77-145">Para criar um backup criptografado, marque a caixa de seleção **Criptografar backup** .</span><span class="sxs-lookup"><span data-stu-id="dae77-145">To create an encrypted backup, check the **Encrypt backup** check box.</span></span> <span data-ttu-id="dae77-146">Selecione um algoritmo de criptografia a ser usado na etapa de criptografia e forneça um Certificado ou uma Chave assimétrica de uma lista de certificados ou chaves assimétricas existentes.</span><span class="sxs-lookup"><span data-stu-id="dae77-146">Select an encryption algorithm to use for the encryption step, and provide a Certificate or Asymmetric key from a list of existing certificates or asymmetric keys.</span></span> <span data-ttu-id="dae77-147">Os algoritmos de criptografia disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="dae77-147">The available algorithms for encryption are:</span></span>  
  
-   <span data-ttu-id="dae77-148">AES 128</span><span class="sxs-lookup"><span data-stu-id="dae77-148">AES 128</span></span>  
  
-   <span data-ttu-id="dae77-149">AES 192</span><span class="sxs-lookup"><span data-stu-id="dae77-149">AES 192</span></span>  
  
-   <span data-ttu-id="dae77-150">AES 256</span><span class="sxs-lookup"><span data-stu-id="dae77-150">AES 256</span></span>  
  
-   <span data-ttu-id="dae77-151">DES triplo</span><span class="sxs-lookup"><span data-stu-id="dae77-151">Triple DES</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="dae77-152">A opção de criptografia estará desabilitada se você optou por anexar ao conjunto de backup existente.</span><span class="sxs-lookup"><span data-stu-id="dae77-152">The encryption option is disabled if you selected to append to existing backup set.</span></span>  
>   
>  <span data-ttu-id="dae77-153">É prática recomendada fazer backup do certificado ou das chaves e armazená-los em um local diferente do backup que você criptografou.</span><span class="sxs-lookup"><span data-stu-id="dae77-153">It is recommended practice to back up your certificate or keys and store them in a different location than the backup you encrypted.</span></span>  
>   
>  <span data-ttu-id="dae77-154">Há suporte somente para as chaves que residem no EKM (Gerenciamento Extensível Chaves).</span><span class="sxs-lookup"><span data-stu-id="dae77-154">Only keys residing in the Extensible Key Management (EKM) are supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dae77-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dae77-155">See Also</span></span>  
 <span data-ttu-id="dae77-156">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dae77-156">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="dae77-157">[Fazer backup de um log de transações &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dae77-157">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="dae77-158">[Fazer backup de arquivos e de grupos de arquivos &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dae77-158">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 [<span data-ttu-id="dae77-159">Fazer backup do log de transações quando o banco de dados está danificado &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dae77-159">Back Up the Transaction Log When the Database Is Damaged &#40;SQL Server&#41;</span></span>](back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md)  
  
  
