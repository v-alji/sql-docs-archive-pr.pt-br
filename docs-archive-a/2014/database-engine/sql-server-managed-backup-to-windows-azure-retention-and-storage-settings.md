---
title: SQL Server Backup gerenciado para o Azure – configurações de armazenamento e retenção | Microsoft Docs
description: Este tópico descreve como configurar SQL Server Backup gerenciado para Microsoft Azure para um banco de dados e para definir as configurações padrão para a instância do.
ms.custom: ''
ms.date: 08/23/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: c4aa26ea-5465-40cc-8b83-f50603cb9db1
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 8ebdb81f8aa9edb9cd9326bcb1d286d5d3fe632c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683668"
---
# <a name="sql-server-managed-backup-to-azure---retention-and-storage-settings"></a><span data-ttu-id="b07c2-103">Backup gerenciado do SQL Server para Azure – Configurações de retenção e armazenamento</span><span class="sxs-lookup"><span data-stu-id="b07c2-103">SQL Server Managed Backup to Azure - Retention and Storage Settings</span></span>
  <span data-ttu-id="b07c2-104">Este tópico descreve as etapas básicas para configurar o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] de um banco de dados e para definir as configurações padrão da instância.</span><span class="sxs-lookup"><span data-stu-id="b07c2-104">This topic describes the basic steps to configure [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a database and to configure default settings for the instance.</span></span> <span data-ttu-id="b07c2-105">O tópico também descreve as etapas necessárias para pausar e retomar os serviços de [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para a instância.</span><span class="sxs-lookup"><span data-stu-id="b07c2-105">The topic also describes the steps necessary to pause and resume [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] services for the instance.</span></span>  
  
 <span data-ttu-id="b07c2-106">Para obter uma explicação completa da configuração [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] , consulte configurando [SQL Server Backup gerenciado no Azure](../relational-databases/backup-restore/enable-sql-server-managed-backup-to-microsoft-azure.md) e [Configurando SQL Server Backup gerenciado para o Azure para grupos de disponibilidade](../../2014/database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="b07c2-106">For a complete walkthrough of setting up [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] see [Setting up SQL Server Managed Backup to Azure](../relational-databases/backup-restore/enable-sql-server-managed-backup-to-microsoft-azure.md) and [Setting up SQL Server Managed Backup to Azure for Availability Groups](../../2014/database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b07c2-107">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="b07c2-107">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b07c2-108">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="b07c2-108">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b07c2-109">Não habilite o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] em bancos de dados que estejam usando planos de manutenção ou envio de logs.</span><span class="sxs-lookup"><span data-stu-id="b07c2-109">Do not enable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] on databases that are currently using maintenance plans or log shipping.</span></span> <span data-ttu-id="b07c2-110">Para obter mais informações sobre interoperabilidade e coexistência com outros recursos de SQL Server, consulte [SQL Server Backup gerenciado para o Azure: interoperabilidade e coexistência](../../2014/database-engine/sql-server-managed-backup-to-windows-azure-interoperability-and-coexistence.md)</span><span class="sxs-lookup"><span data-stu-id="b07c2-110">For more information on interoperability and coexistence with other SQL Server features, see [SQL Server Managed Backup to Azure: Interoperability and Coexistence](../../2014/database-engine/sql-server-managed-backup-to-windows-azure-interoperability-and-coexistence.md)</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="b07c2-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="b07c2-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="b07c2-112">O SQL Server Agent deve estar em execução.</span><span class="sxs-lookup"><span data-stu-id="b07c2-112">SQL Server Agent should be running.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="b07c2-113">Se o SQL Server Agent estiver parado por um período de tempo e, em seguida, reinicializado, você poderá ver uma atividade de backup maior dependendo do período de tempo decorrido entre a parada e o início do SQL Agent, e poderá haver uma lista de pendências de backups de log aguardando para serem executados.</span><span class="sxs-lookup"><span data-stu-id="b07c2-113">If SQL Server Agent is stopped for a period of time and then restarted, you may see an increased backup activity depending on the length of time elapsed between the stop and start of SQL Agent, and there might be a backlog of log backups waiting to run.</span></span> <span data-ttu-id="b07c2-114">Configure o SQL Server Agent para iniciar automaticamente na inicialização.</span><span class="sxs-lookup"><span data-stu-id="b07c2-114">Consider configuring SQL Server Agent to start automatically on start up.</span></span>  
  
-   <span data-ttu-id="b07c2-115">Uma conta de armazenamento do Azure e uma credencial do SQL que armazenam as informações de autenticação para a conta de armazenamento devem ser criadas antes da configuração [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b07c2-115">A Azure storage account and a SQL Credential that stores the authentication information to the storage account should both be created before configuring [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="b07c2-116">Para obter mais informações, consulte a seção [Introduction to Key Components and Concepts](../relational-databases/backup-restore/sql-server-backup-to-url.md#intorkeyconcepts) no tópico **Backup do SQL Server para URL** e [Lesson 2: Create a SQL Server Credential](../../2014/tutorials/lesson-2-create-a-sql-server-credential.md).</span><span class="sxs-lookup"><span data-stu-id="b07c2-116">For more information see [Introduction to Key Components and Concepts](../relational-databases/backup-restore/sql-server-backup-to-url.md#intorkeyconcepts) section of the **SQL Server Backup to URL** topic, and [Lesson 2: Create a SQL Server Credential](../../2014/tutorials/lesson-2-create-a-sql-server-credential.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b07c2-117">O [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] cria os contêineres necessários para armazenar os backups.</span><span class="sxs-lookup"><span data-stu-id="b07c2-117">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] creates the necessary containers to store the backups.</span></span> <span data-ttu-id="b07c2-118">O nome do contêiner é criado usando o formato ' nome da máquina-nome da instância '.</span><span class="sxs-lookup"><span data-stu-id="b07c2-118">The container name is created using 'machine name-instance name' format.</span></span> <span data-ttu-id="b07c2-119">Para Grupos de Disponibilidade AlwaysOn, o contêiner é nomeado por meio do GUID do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="b07c2-119">For AlwaysOn Availability Groups the container is named using the GUID of the availability group.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b07c2-120">Segurança</span><span class="sxs-lookup"><span data-stu-id="b07c2-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b07c2-121">Permissões</span><span class="sxs-lookup"><span data-stu-id="b07c2-121">Permissions</span></span>  
 <span data-ttu-id="b07c2-122">Para executar os procedimentos armazenados que habilitam o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] , você deve ser um `System Administrator` membro ou na função de banco de dados **db_backupoperator** com as permissões **ALTER ANY Credential** e `EXECUTE` permissões no **sp_delete_backuphistory**e `smart_admin.sp_backup_master_switch` procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="b07c2-122">To run the stored procedures that enable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)], you must be a  either a `System Administrator` or  member  in the **db_backupoperator** database role with **ALTER ANY CREDENTIAL** permissions, and `EXECUTE` permissions on the **sp_delete_backuphistory**, and `smart_admin.sp_backup_master_switch` stored procedures.</span></span>  <span data-ttu-id="b07c2-123">Os procedimentos armazenados e as funções usados para analisar as configurações existentes geralmente requerem permissões `Execute` no procedimento armazenado e `Select` na função, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="b07c2-123">Stored procedures and functions used to review the existing settings typically require `Execute` permissions on the stored procedure and `Select` on the function respectively.</span></span>  
  

  
###  <a name="considerations-for-enabling-ss_smartbackup-for-databases-and-instances"></a><a name="Considerations"></a><span data-ttu-id="b07c2-124">Considerações sobre a habilitação [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] de bancos de dados e instâncias</span><span class="sxs-lookup"><span data-stu-id="b07c2-124">Considerations for enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for Databases and Instances</span></span>  
 <span data-ttu-id="b07c2-125">O [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] pode ser habilitado para bancos de dados individuais separadamente ou para a instância inteira.</span><span class="sxs-lookup"><span data-stu-id="b07c2-125">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] can be enabled for individual databases separately or for the entire instance.</span></span> <span data-ttu-id="b07c2-126">As opções dependem dos requisitos de capacidade de recuperação para os bancos de dados na instância do, requisitos para gerenciar vários bancos de dados e instâncias e usar o armazenamento do Azure estrategicamente.</span><span class="sxs-lookup"><span data-stu-id="b07c2-126">The choices depend on the recoverability requirements for the databases on the instance, requirements for managing multiple databases and instances, and using Azure storage strategically.</span></span>  
  
#### <a name="enabling-ss_smartbackup-at-the-database-level"></a><span data-ttu-id="b07c2-127">Habilitando o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] no nível do banco de dados</span><span class="sxs-lookup"><span data-stu-id="b07c2-127">Enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the Database Level</span></span>  
 <span data-ttu-id="b07c2-128">Se um banco de dados tiver requisitos específicos para backup e período de retenção (SLA de recuperação) que sejam diferentes dos requisitos de outros bancos de dados na instância, configure o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] no nível do banco de dados para esse banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b07c2-128">If a database has specific requirements for backup and retention period (recoverability SLA) that is different from other databases on the instance, configure [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the database level for this database.</span></span> <span data-ttu-id="b07c2-129">As configurações no nível do banco de dados substituem os parâmetros de configuração no nível da instância.</span><span class="sxs-lookup"><span data-stu-id="b07c2-129">Database level settings override instance level configuration settings.</span></span> <span data-ttu-id="b07c2-130">No entanto, ambas as opções podem ser usadas juntas na mesma instância.</span><span class="sxs-lookup"><span data-stu-id="b07c2-130">However both these options can be used together on the same instance.</span></span> <span data-ttu-id="b07c2-131">A seguir, é apresentada uma lista das vantagens e considerações ao habilitar o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] no nível do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b07c2-131">Following is a list of advantages and considerations when enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the database level.</span></span>  
  
-   <span data-ttu-id="b07c2-132">Mais granular: parâmetros de configuração separados para cada banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b07c2-132">More granular: Separate configuration settings for each database.</span></span> <span data-ttu-id="b07c2-133">Pode oferecer suporte a diferentes períodos de retenção para bancos de dados individuais.</span><span class="sxs-lookup"><span data-stu-id="b07c2-133">Can support different retention periods for individual databases.</span></span>  
  
-   <span data-ttu-id="b07c2-134">Substitui as configurações no nível da instância para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b07c2-134">Overrides instance level settings for the database.</span></span>  
  
-   <span data-ttu-id="b07c2-135">Pode ser usado para reduzir os custos de armazenamento selecionando os bancos de dados individuais para fazer backup.</span><span class="sxs-lookup"><span data-stu-id="b07c2-135">Can be used to reduce storage costs by selecting individual databases to be backed up.</span></span>  
  
-   <span data-ttu-id="b07c2-136">Requer o gerenciamento de cada banco de dados</span><span class="sxs-lookup"><span data-stu-id="b07c2-136">Requires managing each database</span></span>  
  
#### <a name="enabling-ss_smartbackup-at-the-instance-level-with-default-settings"></a><span data-ttu-id="b07c2-137">Habilitando o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] no nível da instância com configurações padrão</span><span class="sxs-lookup"><span data-stu-id="b07c2-137">Enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the Instance Level with Default Settings</span></span>  
 <span data-ttu-id="b07c2-138">Use essa configuração se a maioria dos bancos de dados da instância tiver os mesmos requisitos para políticas de backup e de retenção ou se você quiser que novas instâncias do banco de dados sejam incluídas automaticamente no backup durante a criação.</span><span class="sxs-lookup"><span data-stu-id="b07c2-138">Use this setting if most of the databases in the instance have the same requirements for backup and retention policies, or if you want new database instances to automatically be backed up on creation.</span></span> <span data-ttu-id="b07c2-139">Alguns bancos de dados que são exceção à política ainda podem ser configurados individualmente.</span><span class="sxs-lookup"><span data-stu-id="b07c2-139">A few databases that are exception to the policy can still be configured individually.</span></span> <span data-ttu-id="b07c2-140">A seguir é apresentada uma lista de vantagens e de considerações ao habilitar o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] no nível da instância.</span><span class="sxs-lookup"><span data-stu-id="b07c2-140">Following is a list of advantages and considerations when enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the instance level.</span></span>  
  
-   <span data-ttu-id="b07c2-141">Automação no nível da instância: configurações comuns a aplicadas automaticamente para os novos bancos de dados adicionados depois.</span><span class="sxs-lookup"><span data-stu-id="b07c2-141">Automation at the instance level: Common settings applied to automatically for new databases added thereafter.</span></span>  
  
-   <span data-ttu-id="b07c2-142">Os novos bancos de dados terão seu backup feito automaticamente logo depois de criados nas instâncias</span><span class="sxs-lookup"><span data-stu-id="b07c2-142">New databases will be automatically backed up soon after they are created on the instances</span></span>  
  
-   <span data-ttu-id="b07c2-143">Pode ser se aplicado a bancos de dados que têm os mesmos requisitos de período de retenção.</span><span class="sxs-lookup"><span data-stu-id="b07c2-143">Can be applied to databases that have the same retention period requirements.</span></span>  
  
-   <span data-ttu-id="b07c2-144">Você ainda pode configurar os bancos de dados individuais que requerem uma período de retenção, mesmo com o backup do [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] habilitado no nível da instância com as configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="b07c2-144">You can still configure individual databases that require a different retention period even with [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] backup enabled at in instance level with default settings.</span></span> <span data-ttu-id="b07c2-145">Você também pode desabilitar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] o para bancos de dados se não pretender usar o armazenamento do Azure para os backups.</span><span class="sxs-lookup"><span data-stu-id="b07c2-145">You can also disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for databases if you do not intend to use Azure storage for the backups.</span></span>  
  
##  <a name="enable-and-configure-ss_smartbackup-for-a-database"></a><a name="DatabaseConfigure"></a><span data-ttu-id="b07c2-146">Habilitar e configurar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] o para um banco de dados</span><span class="sxs-lookup"><span data-stu-id="b07c2-146">Enable and Configure [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a Database</span></span>  
 <span data-ttu-id="b07c2-147">O procedimento armazenado `smart_admin.sp_set_db_backup` do sistema é usado para habilitar o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para um banco de dados específico.</span><span class="sxs-lookup"><span data-stu-id="b07c2-147">The system stored procedure `smart_admin.sp_set_db_backup` is used to enable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a specific database.</span></span> <span data-ttu-id="b07c2-148">Quando o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for habilitado pela primeira vez no banco de dados, as informações a seguir deverão ser especificadas, além da habilitação de [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="b07c2-148">When [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for the first time on the database, the following information must be specified in addition to enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]:</span></span>  
  
-   <span data-ttu-id="b07c2-149">O nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b07c2-149">The name of the database.</span></span>  
  
-   <span data-ttu-id="b07c2-150">O período de retenção.</span><span class="sxs-lookup"><span data-stu-id="b07c2-150">The retention period.</span></span>  
  
-   <span data-ttu-id="b07c2-151">Credencial SQL usada para autenticar para a conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="b07c2-151">SQL Credential used to authenticate to the Azure storage account.</span></span>  
  
-   <span data-ttu-id="b07c2-152">Especifique não criptografar usando \* \@ encryption_algorithm\*  =  **NO_ENCRYPTION** ou especifique um algoritmo de criptografia com suporte.</span><span class="sxs-lookup"><span data-stu-id="b07c2-152">Either specify not to encrypt using *\@encryption_algorithm* = **NO_ENCRYPTION** or specify a supported encryption algorithm.</span></span> <span data-ttu-id="b07c2-153">Para obter mais informações sobre criptografia, consulte [Backup Encryption](../relational-databases/backup-restore/backup-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="b07c2-153">For more information on encryption, see [Backup Encryption](../relational-databases/backup-restore/backup-encryption.md).</span></span>  
  
 <span data-ttu-id="b07c2-154">O [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para a configuração do nível de banco de dados só tem suporte com o Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="b07c2-154">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for database level configuration is only supported through Transact-SQL.</span></span>  
  
 <span data-ttu-id="b07c2-155">Após a habilitação do [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para um banco de dados, essas informações serão mantidas.</span><span class="sxs-lookup"><span data-stu-id="b07c2-155">Once [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for a database this information is persisted.</span></span> <span data-ttu-id="b07c2-156">Se você estiver alterando a configuração, somente o nome do banco de dados e a configuração que você deseja alterar serão necessários; o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] retém os valores existentes para outros parâmetros quando não especificado.</span><span class="sxs-lookup"><span data-stu-id="b07c2-156">If you are changing the configuration, only the database name and the setting you want to change is required, [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] retains the existing values for other parameters when not specified.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b07c2-157">Antes de configurar o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] em um banco de dados, talvez ele seja útil para a configuração existente, se houver.</span><span class="sxs-lookup"><span data-stu-id="b07c2-157">Before configuring [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] on a database it might be useful to existing configuration if any.</span></span> <span data-ttu-id="b07c2-158">A etapa de revisão de parâmetros de configuração de um banco de dados será explicada posteriormente nesta seção.</span><span class="sxs-lookup"><span data-stu-id="b07c2-158">The step to reviewing configuration settings for a database is explained later in this section.</span></span>  
  
-   <span data-ttu-id="b07c2-159">**Usando o Transact-SQL:**</span><span class="sxs-lookup"><span data-stu-id="b07c2-159">**Using Transact-SQL:**</span></span>  
  
     <span data-ttu-id="b07c2-160">Se você estiver habilitando pela [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] primeira vez, os parâmetros necessários serão: \* \@ database_name*, \* \@ credential_name*, \* \@ encryption_algorithm*, \* \@ enable_backup* o parâmetro \* \@ storage_url\* é opcional.</span><span class="sxs-lookup"><span data-stu-id="b07c2-160">If you are enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for the first time, the required parameters are: *\@database_name*, *\@credential_name*, *\@encryption_algorithm*,  *\@enable_backup* The *\@storage_url* parameter is optional.</span></span> <span data-ttu-id="b07c2-161">Se você não fornecer um valor para o @storage_url parâmetro, o valor será derivado usando as informações da conta de armazenamento da credencial do SQL.</span><span class="sxs-lookup"><span data-stu-id="b07c2-161">If you do not provide a value for  the @storage_url parameter, the value is derived using the storage account information from the SQL Credential.</span></span> <span data-ttu-id="b07c2-162">Se você fornecer a URL de armazenamento, só deverá fornecer a URL da raiz da conta de armazenamento e fazer a correspondência das informações na Credencial SQL que você especificou.</span><span class="sxs-lookup"><span data-stu-id="b07c2-162">If you provide the storage URL you should only provide the URL for the root of the storage account, and must match the information in the SQL Credential you specified.</span></span>  
  
    1.  <span data-ttu-id="b07c2-163">Conecte-se ao [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b07c2-163">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
    2.  <span data-ttu-id="b07c2-164">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="b07c2-164">From the Standard bar, click **New Query**.</span></span>  
  
    3.  <span data-ttu-id="b07c2-165">Copie e cole o exemplo a seguir na janela de consulta e clique em `Execute` .</span><span class="sxs-lookup"><span data-stu-id="b07c2-165">Copy and paste the following example into the query window and click `Execute`.</span></span> <span data-ttu-id="b07c2-166">Este exemplo habilita [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] o banco de dados ' TestDB '.</span><span class="sxs-lookup"><span data-stu-id="b07c2-166">This example enables [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for the database 'TestDB'.</span></span> <span data-ttu-id="b07c2-167">O período de retenção é definido como 30 dias.</span><span class="sxs-lookup"><span data-stu-id="b07c2-167">The retention period is set to 30 days.</span></span> <span data-ttu-id="b07c2-168">Este exemplo usa a opção de criptografia especificando o algoritmo de criptografia e as informações do criptografador.</span><span class="sxs-lookup"><span data-stu-id="b07c2-168">This sample uses the encryption option by specifying the encryption algorithm and the encryptor information.</span></span>  
  
    ```sql
    Use msdb;  
    GO  
    EXEC smart_admin.sp_set_db_backup   
                    @database_name='TestDB'   
                    ,@enable_backup=1  
                    ,@retention_days =30   
                    ,@credential_name ='MyCredential'  
                    ,@encryption_algorithm ='AES_256'  
                    ,@encryptor_type= 'Certificate'  
                    ,@encryptor_name='MyBackupCert'  
    GO
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b07c2-169">O período de retenção pode ser definido para qualquer valor de 1 a 30 dias.</span><span class="sxs-lookup"><span data-stu-id="b07c2-169">The retention period can be set to any value from 1 to 30 days.</span></span>  
    >   
    >  <span data-ttu-id="b07c2-170">Para obter mais informações sobre como criar um certificado para criptografia, consulte a etapa Criar um certificado de backup em [Create an Encrypted Backup](../relational-databases/backup-restore/create-an-encrypted-backup.md).</span><span class="sxs-lookup"><span data-stu-id="b07c2-170">For more information on creating a certificate for encryption, see the Create a Backup Certificate step in [Create an Encrypted Backup](../relational-databases/backup-restore/create-an-encrypted-backup.md).</span></span>  
  
     <span data-ttu-id="b07c2-171">Para obter mais informações sobre esse procedimento armazenado, consulte [smart_admin. set_db_backup &#40;Transact-SQL&#41;](https://msdn.microsoft.com/library/dn451013(v=sql.120).aspx)</span><span class="sxs-lookup"><span data-stu-id="b07c2-171">For more information on this stored procedure, see [smart_admin.set_db_backup &#40;Transact-SQL&#41;](https://msdn.microsoft.com/library/dn451013(v=sql.120).aspx)</span></span>  
  
     <span data-ttu-id="b07c2-172">Para examinar os parâmetros de configuração de um banco de dados, use a seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="b07c2-172">To review the configuration settings for a database use the following query:</span></span>  
  
    ```sql
    Use msdb  
    GO  
    SELECT * FROM smart_admin.fn_backup_db_config('TestDB')  
    ```  
  
##  <a name="enable-and-configure-default-ss_smartbackup-settings-for-the-instance"></a><a name="InstanceConfigure"></a><span data-ttu-id="b07c2-173">Habilitar e definir [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] configurações padrão para a instância</span><span class="sxs-lookup"><span data-stu-id="b07c2-173">Enable and Configure Default [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] settings for the Instance</span></span>  
 <span data-ttu-id="b07c2-174">Você pode habilitar e definir [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] as configurações padrão no nível da instância de duas maneiras: usando o procedimento armazenado do sistema `smart_admin.set_instance_backup` ou **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="b07c2-174">You can enable and configure default [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] settings at the instance level in two ways:  By using the system stored procedure `smart_admin.set_instance_backup` or **SQL Server Management Studio**.</span></span> <span data-ttu-id="b07c2-175">Os dois métodos são explicados abaixo:</span><span class="sxs-lookup"><span data-stu-id="b07c2-175">The two methods are explained below:</span></span>  
  
 <span data-ttu-id="b07c2-176">**smart_admin. set_instance_backup:**.</span><span class="sxs-lookup"><span data-stu-id="b07c2-176">**smart_admin.set_instance_backup:**.</span></span> <span data-ttu-id="b07c2-177">Ao especificar o valor **1** para \* \@ enable_backup\* parâmetro, você pode habilitar o backup e definir as configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="b07c2-177">By specifying the value **1** for *\@enable_backup* parameter, you can enable backup and set the default configurations.</span></span> <span data-ttu-id="b07c2-178">Após a aplicação no nível de instância, essas configurações padrão serão aplicadas a qualquer novo banco de dados adicionado a essa instância.</span><span class="sxs-lookup"><span data-stu-id="b07c2-178">Once applied at the instance level, these default settings are applied to any new database that is added to this instance.</span></span>  <span data-ttu-id="b07c2-179">Quando o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for habilitado pela primeira vez, as informações a seguir deverão ser fornecidas, além da habilitação de [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] na instância:</span><span class="sxs-lookup"><span data-stu-id="b07c2-179">When [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for the first time, the following information must be provided in addition to enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] on the instance:</span></span>  
  
-   <span data-ttu-id="b07c2-180">O período de retenção.</span><span class="sxs-lookup"><span data-stu-id="b07c2-180">The retention period.</span></span>  
  
-   <span data-ttu-id="b07c2-181">Credencial SQL usada para autenticar para a conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="b07c2-181">SQL Credential used to authenticate to the Azure storage account.</span></span>  
  
-   <span data-ttu-id="b07c2-182">A opção de criptografia.</span><span class="sxs-lookup"><span data-stu-id="b07c2-182">The encryption option.</span></span> <span data-ttu-id="b07c2-183">Especifique não criptografar usando \* \@ encryption_algorithm\*  =  **NO_ENCRYPTION** ou especifique um algoritmo de criptografia com suporte.</span><span class="sxs-lookup"><span data-stu-id="b07c2-183">Either specify not to encrypt using *\@encryption_algorithm* = **NO_ENCRYPTION** or specify a supported encryption algorithm.</span></span> <span data-ttu-id="b07c2-184">Para obter mais informações sobre criptografia, consulte [Backup Encryption](../relational-databases/backup-restore/backup-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="b07c2-184">For more information on encryption, see [Backup Encryption](../relational-databases/backup-restore/backup-encryption.md).</span></span>  
  
 <span data-ttu-id="b07c2-185">Depois de habilitadas, essas configurações serão mantidas.</span><span class="sxs-lookup"><span data-stu-id="b07c2-185">Once enabled these settings are persisted.</span></span> <span data-ttu-id="b07c2-186">Se você estiver alterando a configuração, somente o nome do banco de dados e a configuração que você deseja alterar serão necessários.</span><span class="sxs-lookup"><span data-stu-id="b07c2-186">If you are changing the configuration, only the database name and the setting you want to change is required.</span></span> <span data-ttu-id="b07c2-187">O [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] retém os valores existentes quando não especificado.</span><span class="sxs-lookup"><span data-stu-id="b07c2-187">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] retains the existing values when not specified.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b07c2-188">Antes de configurar o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] em uma instância, talvez seja útil verificar a configuração existente, se houver.</span><span class="sxs-lookup"><span data-stu-id="b07c2-188">Before configuring [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] on an instance, it might be useful to check for existing configuration, if any.</span></span> <span data-ttu-id="b07c2-189">A etapa de revisão de parâmetros de configuração de um banco de dados será explicada posteriormente nesta seção.</span><span class="sxs-lookup"><span data-stu-id="b07c2-189">The step to reviewing configuration settings for a database is explained later in this section.</span></span>  
  
 <span data-ttu-id="b07c2-190">**SQL Server Management Studio:** para executar esta tarefa no SQL Server Management Studio, vá até o pesquisador de objetos, expanda o nó **Gerenciamento** e clique com o botão direito do mouse em **Backup Gerenciado**.</span><span class="sxs-lookup"><span data-stu-id="b07c2-190">**SQL Server Management Studio:** To do this task in SQL Server Management Studio, go the object explorer, expand the **Management** node, and right click on **Managed Backup**.</span></span> <span data-ttu-id="b07c2-191">Selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="b07c2-191">Select **Configure**.</span></span> <span data-ttu-id="b07c2-192">Essa ação abre a caixa de diálogo **Backup Gerenciado** .</span><span class="sxs-lookup"><span data-stu-id="b07c2-192">This opens the **Managed Backup** dialog.</span></span> <span data-ttu-id="b07c2-193">Use essa caixa de diálogo para especificar o período de retenção, a Credencial do SQL, a URL de Armazenamento e as configurações de criptografia.</span><span class="sxs-lookup"><span data-stu-id="b07c2-193">Use this dialog to specify the retention period, SQL Credential, Storage URL, and the encryption settings.</span></span> <span data-ttu-id="b07c2-194">Para obter ajuda específica com esta caixa de diálogo, consulte [Configurar o backup gerenciado &#40;SQL Server Management Studio&#41;](configure-managed-backup-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="b07c2-194">For specific help with this dialog, see [Configure Managed Backup &#40;SQL Server Management Studio&#41;](configure-managed-backup-sql-server-management-studio.md).</span></span>  
  
#### <a name="using-transact-sql"></a><span data-ttu-id="b07c2-195">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b07c2-195">Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="b07c2-196">Conecte-se ao [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b07c2-196">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b07c2-197">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="b07c2-197">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b07c2-198">Copie e cole o exemplo a seguir na janela de consulta e clique em `Execute` .</span><span class="sxs-lookup"><span data-stu-id="b07c2-198">Copy and paste the following example into the query window and click `Execute`.</span></span>  
  
```sql
Use msdb;  
Go  
   EXEC smart_admin.sp_set_instance_backup  
                @retention_days=30   
                ,@credential_name='sqlbackuptoURL'  
                ,@encryption_algorithm ='AES_128'  
                ,@encryptor_type= 'Certificate'  
                ,@encryptor_name='MyBackupCert'  
                ,@enable_backup=1;  
GO  
  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b07c2-199">O período de retenção pode ser definido para qualquer valor de 1 a 30 dias.</span><span class="sxs-lookup"><span data-stu-id="b07c2-199">The retention period can be set to any value from 1 to 30 days.</span></span>  
>   
>  <span data-ttu-id="b07c2-200">Para obter mais informações sobre como criar um certificado para criptografia, consulte a etapa Criar um certificado de backup em [Create an Encrypted Backup](../relational-databases/backup-restore/create-an-encrypted-backup.md).</span><span class="sxs-lookup"><span data-stu-id="b07c2-200">For more information on creating a certificate for encryption, see the Create a Backup Certificate step in [Create an Encrypted Backup](../relational-databases/backup-restore/create-an-encrypted-backup.md).</span></span>  
  
 <span data-ttu-id="b07c2-201">Para exibir os parâmetros de configuração padrão para a instância, use a seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="b07c2-201">To view the default configuration settings for the instance, use the following query:</span></span>  
  
```sql
Use msdb;  
GO  
SELECT * FROM smart_admin.fn_backup_instance_config ();
```  
  
#### <a name="using-powershell"></a><span data-ttu-id="b07c2-202">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="b07c2-202">Using PowerShell</span></span>  
  
1.  <span data-ttu-id="b07c2-203">Iniciar uma instância do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b07c2-203">Start a PowerShell Instance</span></span>  
  
2.  <span data-ttu-id="b07c2-204">Executar o script a seguir depois de modificá-lo de acordo com suas configurações</span><span class="sxs-lookup"><span data-stu-id="b07c2-204">Run the following script after modifying it to suit your settings</span></span>  
  
    ```powershell
    cd SQLSERVER:\SQL\Computer\MyInstance
    $encryptionOption = New-SqlBackupEncryptionOption -EncryptionAlgorithm Aes128 -EncryptorType ServerCertificate -EncryptorName "MyBackupCert"  
    Get-SqlSmartAdmin | Set-SqlSmartAdmin -BackupEnabled $True -BackupRetentionPeriodInDays 10 -EncryptionOption $encryptionOption  
    ```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b07c2-205">Quando você cria um novo banco de dados depois de definir as configurações padrão, podem demorar até 15 minutos para que o banco de dados seja definido com as configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="b07c2-205">When you create a new database after configuring the default settings, it may take up to 15 minutes for the database to be configured with the default settings.</span></span> <span data-ttu-id="b07c2-206">Isso também se aplica a bancos de dados que são alterados de **Simple** para **Full** ou o modelo de recuperação **Bulk-Logged** .</span><span class="sxs-lookup"><span data-stu-id="b07c2-206">This also applies to databases that are changed from **Simple** to **Full** or **Bulk-Logged** recovery model.</span></span>  
  
##  <a name="disable-ss_smartbackup-for-a-database"></a><a name="DatabaseDisable"></a> <span data-ttu-id="b07c2-207">Desabilitar o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para um banco de dados</span><span class="sxs-lookup"><span data-stu-id="b07c2-207">Disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a database</span></span>  
 <span data-ttu-id="b07c2-208">Você pode desabilitar as configurações do [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] usando o procedimento armazenado `sp_set_db_backup` do sistema.</span><span class="sxs-lookup"><span data-stu-id="b07c2-208">You can disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] settings by using the `sp_set_db_backup` system stored procedure.</span></span> <span data-ttu-id="b07c2-209">O \* \@ enableparameter\* é usado para habilitar e desabilitar as [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] configurações de um banco de dados específico, em que 1 habilita e 0 desabilita as definições de configuração.</span><span class="sxs-lookup"><span data-stu-id="b07c2-209">The *\@enableparameter* is used to enable and disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] configurations for a specific database, where 1 enables and 0 disables the configuration settings.</span></span>  
  
#### <a name="to-disable-ss_smartbackup-for-a-specific-database"></a><span data-ttu-id="b07c2-210">Para desabilitar o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para um banco de dados específico:</span><span class="sxs-lookup"><span data-stu-id="b07c2-210">To Disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a specific database:</span></span>  
  
1.  <span data-ttu-id="b07c2-211">Conecte-se ao [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b07c2-211">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b07c2-212">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="b07c2-212">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b07c2-213">Copie e cole o exemplo a seguir na janela de consulta e clique em `Execute` .</span><span class="sxs-lookup"><span data-stu-id="b07c2-213">Copy and paste the following example into the query window and click `Execute`.</span></span>  
  
```sql
Use msdb;  
Go  
EXEC smart_admin.sp_set_db_backup   
                @database_name='TestDB'   
                ,@enable_backup=0;  
GO
```  
  
##  <a name="disable-ss_smartbackup-for-all-the-databases-on-the-instance"></a><a name="DatabaseAllDisable"></a> <span data-ttu-id="b07c2-214">Desabilitar o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para todos os bancos de dados na instância</span><span class="sxs-lookup"><span data-stu-id="b07c2-214">Disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for all the databases on the Instance</span></span>  
 <span data-ttu-id="b07c2-215">O procedimento a seguir deverá ser usado quando você quiser desabilitar parâmetros de configuração do [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] de todos os bancos de dados que atualmente têm o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] habilitado na instância.</span><span class="sxs-lookup"><span data-stu-id="b07c2-215">The following procedure is for when you want to disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] configuration settings from all the databases that currently have [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] enabled on the instance.</span></span>  <span data-ttu-id="b07c2-216">Os parâmetros de configuração, como a URL de armazenamento, retenção e a Credencial do SQL permanecerão nos metadados e poderão ser usados se o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for habilitado para o banco de dados posteriormente.</span><span class="sxs-lookup"><span data-stu-id="b07c2-216">The configuration settings like the storage URL, retention, and the SQL Credential will remain in the metadata and can be used  if [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for the database at a later time.</span></span> <span data-ttu-id="b07c2-217">Se você quiser apenas pausar os serviços do [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] temporariamente, poderá usar a opção mestra explicada nas seções a seguir mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="b07c2-217">If you want to just pause [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] services temporarily, you can use the master switch explained in the following sections later in this topic.</span></span>  
  
#### <a name="to-disable-ss_smartbackupfor-all-the-databases"></a><span data-ttu-id="b07c2-218">Para desabilitar o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]para todos os bancos de dados:</span><span class="sxs-lookup"><span data-stu-id="b07c2-218">To disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]for all the databases:</span></span>  
  
1.  <span data-ttu-id="b07c2-219">Conecte-se ao [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b07c2-219">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b07c2-220">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="b07c2-220">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b07c2-221">Copie e cole o exemplo a seguir na janela de consulta e clique em `Execute` .</span><span class="sxs-lookup"><span data-stu-id="b07c2-221">Copy and paste the following example into the query window and click `Execute`.</span></span> <span data-ttu-id="b07c2-222">O exemplo a seguir identifica se o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] está configurado no nível da instância e em todos os bancos de dados habilitados do [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] na instância, e executa o procedimento armazenado `sp_set_db_backup` do sistema para desabilitar o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b07c2-222">The following example identifies if [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is configured at the instance level and all the [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] enabled databases on the instance, and executes the system stored procedure `sp_set_db_backup` to disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span></span>  
  
```sql
-- Create a working table to store the database names  
Declare @DBNames TABLE  
  
       (  
             RowID int IDENTITY PRIMARY KEY  
             ,DBName varchar(500)  
  
       )  
-- Define the variables  
DECLARE @rowid int  
DECLARE @dbname varchar(500)  
DECLARE @SQL varchar(2000)  
-- Get the database names from the system function  
  
INSERT INTO @DBNames (DBName)  
  
SELECT db_name  
       FROM
  
       smart_admin.fn_backup_db_config (NULL)  
       WHERE is_smart_backup_enabled = 1  
  
       --Select DBName from @DBNames 
       select @rowid = min(RowID) FROM @DBNames  
  
       WHILE @rowID IS NOT NULL  
       Begin
             Set @dbname = (Select DBName From @DBNames Where RowID = @rowid)  
             Begin  
             Set @SQL = 'EXEC smart_admin.sp_set_db_backup    
                @database_name= '''+'' + @dbname+ ''+''',   
                @enable_backup=0'  
  
            EXECUTE (@SQL)  
  
             END  
             Select @rowid = min(RowID)  
             From @DBNames Where RowID > @rowid  
  
       END
```  
  
 <span data-ttu-id="b07c2-223">Para examinar os parâmetros de configuração de todos os bancos de dados da instância, use a seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="b07c2-223">To review the configuration settings for all the databases on the instance, use the following query:</span></span>  
  
```sql
Use msdb;  
GO  
SELECT * FROM smart_admin.fn_backup_db_config (NULL);  
GO
```  
  
##  <a name="disable-default-ss_smartbackup-settings-for-the-instance"></a><a name="InstanceDisable"></a> <span data-ttu-id="b07c2-224">Habilitar as configurações padrão do [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para a instância</span><span class="sxs-lookup"><span data-stu-id="b07c2-224">Disable Default [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] settings for the Instance</span></span>  
 <span data-ttu-id="b07c2-225">As configurações padrão no nível da instância se aplicam a todos os novos bancos de dados criados nessa instância.</span><span class="sxs-lookup"><span data-stu-id="b07c2-225">Default settings at the instance level apply to all new databases created on that instance.</span></span>  <span data-ttu-id="b07c2-226">Se não precisar mais das configurações padrão ou estas não forem mais exigidas, você poderá desabilitar essa configuração usando o procedimento armazenado **smart_admin.sp_set_instance_backup** do sistema.</span><span class="sxs-lookup"><span data-stu-id="b07c2-226">If you no longer need or require default settings, you can disable this configuration by using the **smart_admin.sp_set_instance_backup** System stored procedure.</span></span> <span data-ttu-id="b07c2-227">A desabilitação não remove os outros parâmetros de configuração como a URL de armazenamento, a configuração de retenção ou o nome da Credencial do SQL.</span><span class="sxs-lookup"><span data-stu-id="b07c2-227">Disabling does not remove the other configuration settings like the storage URL, retention setting, or the SQL Credential name.</span></span> <span data-ttu-id="b07c2-228">Essas configurações serão usadas se o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] estiver habilitado para a instância mais tarde.</span><span class="sxs-lookup"><span data-stu-id="b07c2-228">These settings will be used if [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for the instance at a later time.</span></span>  
  
#### <a name="to-disable-ss_smartbackup-default-configuration-settings"></a><span data-ttu-id="b07c2-229">Para desabilitar os parâmetros de configuração padrão do [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="b07c2-229">To disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] default configuration settings:</span></span>  
  
1.  <span data-ttu-id="b07c2-230">Conecte-se ao [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b07c2-230">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b07c2-231">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="b07c2-231">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b07c2-232">Copie e cole o exemplo a seguir na janela de consulta e clique em `Execute` .</span><span class="sxs-lookup"><span data-stu-id="b07c2-232">Copy and paste the following example into the query window and click `Execute`.</span></span>  
  
    ```sql
    Use msdb;  
    Go  
    EXEC smart_admin.sp_set_instance_backup  
                    @enable_backup=0;  
    GO
    ```  
  
#### <a name="using-powershell"></a><span data-ttu-id="b07c2-233">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="b07c2-233">Using PowerShell</span></span>  
  
1.  <span data-ttu-id="b07c2-234">Iniciar uma instância do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b07c2-234">Start a PowerShell Instance</span></span>  
  
2.  <span data-ttu-id="b07c2-235">Execute o seguinte script:</span><span class="sxs-lookup"><span data-stu-id="b07c2-235">Run the following script:</span></span>  
  
    ```powershell
    cd SQLSERVER:\SQL\Computer\MyInstance
    Set-SqlSmartAdmin -BackupEnabled $False  
    ```  
  
##  <a name="pause-ss_smartbackup-at-the-instance-level"></a><a name="InstancePause"></a> <span data-ttu-id="b07c2-236">Pause o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] no nível da instância</span><span class="sxs-lookup"><span data-stu-id="b07c2-236">Pause [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the Instance Level</span></span>  
 <span data-ttu-id="b07c2-237">Pode haver momentos em que você precise pausar temporariamente os serviços do [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] por um curto período de tempo.</span><span class="sxs-lookup"><span data-stu-id="b07c2-237">There might be times when you need to temporarily pause the [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] services for a short period time.</span></span>  <span data-ttu-id="b07c2-238">O procedimento armazenado `smart_admin.sp_backup_master_switch` do sistema permite que você desabilite o serviço do [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] no nível da instância.</span><span class="sxs-lookup"><span data-stu-id="b07c2-238">The `smart_admin.sp_backup_master_switch` system stored procedure allows you to disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] service at the instance level.</span></span>  <span data-ttu-id="b07c2-239">O mesmo procedimento armazenado é usado para retomar o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b07c2-239">The same stored procedure is used to resume [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="b07c2-240">O parâmetro @state é usado para definir se o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] deve ser desativado ou ativado.</span><span class="sxs-lookup"><span data-stu-id="b07c2-240">The @state parameter is used to define whether [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] should be turned off or on.</span></span>  
  
#### <a name="to-pause-ss_smartbackup-services-using-transact-sql"></a><span data-ttu-id="b07c2-241">Para pausar os serviços do [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] usando o Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="b07c2-241">To Pause [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Services Using Transact-SQL:</span></span>  
  
1.  <span data-ttu-id="b07c2-242">Conecte-se ao [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b07c2-242">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b07c2-243">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="b07c2-243">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b07c2-244">Copie e cole o exemplo a seguir na janela de consulta e, em seguida, clique em`Execute`</span><span class="sxs-lookup"><span data-stu-id="b07c2-244">Copy and paste the following example into the query window and then click `Execute`</span></span>  
  
```sql
Use msdb;  
GO  
EXEC smart_admin.sp_backup_master_switch @new_state=0;  
Go  
  
```  
  
#### <a name="to-pause-ss_smartbackup-using-powershell"></a><span data-ttu-id="b07c2-245">Para pausar o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] usando PowerShell</span><span class="sxs-lookup"><span data-stu-id="b07c2-245">To pause [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Using PowerShell</span></span>  
  
1.  <span data-ttu-id="b07c2-246">Iniciar uma instância do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b07c2-246">Start a PowerShell Instance</span></span>  
  
2.  <span data-ttu-id="b07c2-247">Executar o script a seguir depois de modificá-lo de acordo com suas configurações</span><span class="sxs-lookup"><span data-stu-id="b07c2-247">Run the following script after you modify it to suit your settings</span></span>  
  
    ```powershell
    cd SQLSERVER:\SQL\Computer\MyInstance
    Get-SqlSmartAdmin | Set-SqlSmartAdmin -MasterSwitch $False  
    ```  
  
#### <a name="to-resume-ss_smartbackup-using-transact-sql"></a><span data-ttu-id="b07c2-248">Para retomar o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] usando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b07c2-248">To resume [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="b07c2-249">Conecte-se ao [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b07c2-249">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b07c2-250">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="b07c2-250">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b07c2-251">Copie e cole o exemplo a seguir na janela de consulta e, em seguida, clique em `Execute` .</span><span class="sxs-lookup"><span data-stu-id="b07c2-251">Copy and paste the following example into the query window and then click `Execute`.</span></span>  
  
```sql
Use msdb;  
Go  
EXEC smart_admin. sp_backup_master_switch @new_state=1;  
GO
```  
  
#### <a name="to-resume-ss_smartbackup-using-powershell"></a><span data-ttu-id="b07c2-252">Para retomar o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] usando PowerShell</span><span class="sxs-lookup"><span data-stu-id="b07c2-252">To resume [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Using PowerShell</span></span>  
  
1.  <span data-ttu-id="b07c2-253">Iniciar uma instância do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b07c2-253">Start a PowerShell Instance</span></span>  
  
2.  <span data-ttu-id="b07c2-254">Executar o script a seguir depois de modificá-lo de acordo com suas configurações</span><span class="sxs-lookup"><span data-stu-id="b07c2-254">Run the following script after you modify it to suit your settings</span></span>  
  
    ```powershell
    cd SQLSERVER:\SQL\Computer\MyInstance
    Get-SqlSmartAdmin | Set-SqlSmartAdmin -MasterSwitch $True  
    ```  
