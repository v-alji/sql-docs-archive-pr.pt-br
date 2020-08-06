---
title: Usar o Administrador de Recursos para limitar o uso de CPU por meio de compactação de backup (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup compression [SQL Server], Resource Governor
- backup compression [SQL Server], CPU usage
- compression [SQL Server], backup compression
- backups [SQL Server], compression
- Resource Governor, backup compression
ms.assetid: 01796551-578d-4425-9b9e-d87210f7ba72
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 19a95cfa5c6780fbdf71ae58bd141aa9aa351efa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685802"
---
# <a name="use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql"></a><span data-ttu-id="77f06-102">Usar o Administrador de Recursos para limitar o uso de CPU por meio de compactação de backup (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="77f06-102">Use Resource Governor to Limit CPU Usage by Backup Compression (Transact-SQL)</span></span>
  <span data-ttu-id="77f06-103">Por padrão, a compactação de backup aumenta consideravelmente o uso de CPU, e o consumo adicional da CPU por parte do processo de compactação pode afetar negativamente as operações simultâneas.</span><span class="sxs-lookup"><span data-stu-id="77f06-103">By default, backing up using compression significantly increases CPU usage, and the additional CPU consumed by the compression process can adversely impact concurrent operations.</span></span> <span data-ttu-id="77f06-104">Portanto, convém criar um backup compactado de baixa prioridade em uma sessão cujo uso de CPU seja limitado pelo[Administrador de Recursos](../resource-governor/resource-governor.md) quando houver contenção de CPU.</span><span class="sxs-lookup"><span data-stu-id="77f06-104">Therefore, you might want to create a low-priority compressed backup in a session whose CPU usage is limited by[Resource Governor](../resource-governor/resource-governor.md) when CPU contention occurs.</span></span> <span data-ttu-id="77f06-105">Este tópico apresenta um cenário que classifica as sessões de um usuário específico do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mapeando-as para um grupo de carga de trabalho do Administrador de Recursos que limita o uso de CPU em casos como esse.</span><span class="sxs-lookup"><span data-stu-id="77f06-105">This topic presents a scenario that classifies the sessions of a particular [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user by mapping them to a Resource Governor workload group that limits CPU usage in such cases.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="77f06-106">Em um determinado cenário do Administrador de Recursos, a classificação de sessão pode ser baseada em um nome de usuário, em um nome de aplicativo ou em qualquer outro item que possa diferenciar uma conexão.</span><span class="sxs-lookup"><span data-stu-id="77f06-106">In a given Resource Governor scenario, session classification might be based on a user name, an application name, or anything else that can differentiate a connection.</span></span> <span data-ttu-id="77f06-107">Para obter mais informações, consulte [Resource Governor Classifier Function](../resource-governor/resource-governor-classifier-function.md) e [Resource Governor Workload Group](../resource-governor/resource-governor-workload-group.md).</span><span class="sxs-lookup"><span data-stu-id="77f06-107">For more information, see [Resource Governor Classifier Function](../resource-governor/resource-governor-classifier-function.md) and [Resource Governor Workload Group](../resource-governor/resource-governor-workload-group.md).</span></span>  
  
##  <a name="this-topic-contains-the-following-set-of-scenarios-which-are-presented-in-sequence"></a><a name="Top"></a> <span data-ttu-id="77f06-108">Este tópico contém o seguinte conjunto de cenários que são apresentados em sequência:</span><span class="sxs-lookup"><span data-stu-id="77f06-108">This topic contains the following set of scenarios, which are presented in sequence:</span></span>  
  
1.  [<span data-ttu-id="77f06-109">Configurando um logon e um usuário para operações de baixa prioridade</span><span class="sxs-lookup"><span data-stu-id="77f06-109">Setting Up a Login and User for Low-Priority Operations</span></span>](#setup_login_and_user)  
  
2.  [<span data-ttu-id="77f06-110">Configurando o Administrador de Recursos para limitar o uso de CPU</span><span class="sxs-lookup"><span data-stu-id="77f06-110">Configuring Resource Governor to Limit CPU Usage</span></span>](#configure_RG)  
  
3.  [<span data-ttu-id="77f06-111">Verificando a classificação da sessão atual (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="77f06-111">Verifying the Classification of the Current Session (Transact-SQL)</span></span>](#verifying)  
  
4.  [<span data-ttu-id="77f06-112">Compactando backups usando uma sessão com CPU limitada</span><span class="sxs-lookup"><span data-stu-id="77f06-112">Compressing Backups Using a Session with Limited CPU</span></span>](#creating_compressed_backup)  
  
##  <a name="setting-up-a-login-and-user-for-low-priority-operations"></a><a name="setup_login_and_user"></a> <span data-ttu-id="77f06-113">Configurando um logon e um usuário para operações de baixa prioridade</span><span class="sxs-lookup"><span data-stu-id="77f06-113">Setting Up a Login and User for Low-Priority Operations</span></span>  
 <span data-ttu-id="77f06-114">O cenário deste tópico requer um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e um usuário de baixa prioridade.</span><span class="sxs-lookup"><span data-stu-id="77f06-114">The scenario in this topic requires a low-priority [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and user.</span></span> <span data-ttu-id="77f06-115">O nome do usuário será usado para classificar sessões que executam no logon e roteá-las as para um grupo de carga de trabalho do Administrador de Recursos que limita o uso de CPU.</span><span class="sxs-lookup"><span data-stu-id="77f06-115">The user name will be used to classify sessions running in the login and route them to a Resource Governor workload group that limits CPU usage.</span></span>  
  
 <span data-ttu-id="77f06-116">O seguinte procedimento descreve as etapas para configuração de um logon e um usuário para essa finalidade, seguido por um exemplo do [!INCLUDE[tsql](../../includes/tsql-md.md)], "Exemplo A: Configurando um logon e um usuário (Transact-SQL)".</span><span class="sxs-lookup"><span data-stu-id="77f06-116">The following procedure describes the steps for setting up a login and user for this purpose, followed by a [!INCLUDE[tsql](../../includes/tsql-md.md)] example, "Example A: Setting Up a Login and User (Transact-SQL)."</span></span>  
  
### <a name="to-set-up-a-login-and-database-user-for-classifying-sessions"></a><span data-ttu-id="77f06-117">Para configurar um logon e um usuário de banco de dados para classificar sessões</span><span class="sxs-lookup"><span data-stu-id="77f06-117">To set up a login and database user for classifying sessions</span></span>  
  
1.  <span data-ttu-id="77f06-118">Crie um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para criar backups compactados de baixa prioridade.</span><span class="sxs-lookup"><span data-stu-id="77f06-118">Create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login for creating low-priority compressed backups.</span></span>  
  
     <span data-ttu-id="77f06-119">**Para criar um logon**</span><span class="sxs-lookup"><span data-stu-id="77f06-119">**To create a login**</span></span>  
  
    -   [<span data-ttu-id="77f06-120">Criar um logon</span><span class="sxs-lookup"><span data-stu-id="77f06-120">Create a Login</span></span>](../security/authentication-access/create-a-login.md)  
  
    -   [<span data-ttu-id="77f06-121">CREATE LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="77f06-121">CREATE LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-login-transact-sql)  
  
2.  <span data-ttu-id="77f06-122">Opcionalmente, conceda VIEW SERVER STATE a esse logon.</span><span class="sxs-lookup"><span data-stu-id="77f06-122">Optionally, grant VIEW SERVER STATE to this login.</span></span>  
  
    -   [<span data-ttu-id="77f06-123">Permissões de objeto do sistema GRANT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="77f06-123">GRANT System Object Permissions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/grant-system-object-permissions-transact-sql)  
  
     <span data-ttu-id="77f06-124">Para obter mais informações, consulte [Permissões de principal do banco de dados GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-principal-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="77f06-124">For more information, see [GRANT Database Principal Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-principal-permissions-transact-sql).</span></span>  
  
3.  <span data-ttu-id="77f06-125">Crie um usuário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para esse logon.</span><span class="sxs-lookup"><span data-stu-id="77f06-125">Create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user for this login.</span></span>  
  
     <span data-ttu-id="77f06-126">**Para criar um usuário**</span><span class="sxs-lookup"><span data-stu-id="77f06-126">**To create a user**</span></span>  
  
    -   [<span data-ttu-id="77f06-127">Criar um usuário de banco de dados</span><span class="sxs-lookup"><span data-stu-id="77f06-127">Create a Database User</span></span>](../security/authentication-access/create-a-database-user.md)  
  
    -   [<span data-ttu-id="77f06-128">CREATE USER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="77f06-128">CREATE USER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-user-transact-sql)  
  
4.  <span data-ttu-id="77f06-129">Para habilitar sessões desse logon e usuário para fazer backup de um determinado banco de dados, adicione o usuário à função de banco de dados db_backupoperator desse banco de dados.</span><span class="sxs-lookup"><span data-stu-id="77f06-129">To enable sessions of this login and user to back up a given database, add the user to the db_backupoperator database role of that database.</span></span> <span data-ttu-id="77f06-130">Faça isso para cada banco de dados do qual o usuário fará backup.</span><span class="sxs-lookup"><span data-stu-id="77f06-130">Do this for each database that this user will back up.</span></span> <span data-ttu-id="77f06-131">Opcionalmente, adicione o usuário a outras funções fixas do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="77f06-131">Optionally, add the user to other fixed database roles.</span></span>  
  
     <span data-ttu-id="77f06-132">**Para adicionar um usuário a uma função de banco de dados fixa**</span><span class="sxs-lookup"><span data-stu-id="77f06-132">**To add a user to a fixed database role**</span></span>  
  
    -   [<span data-ttu-id="77f06-133">sp_addrolemember &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="77f06-133">sp_addrolemember &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql)  
  
     <span data-ttu-id="77f06-134">Para obter mais informações, consulte [Permissões de principal do banco de dados GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-principal-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="77f06-134">For more information, see [GRANT Database Principal Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-principal-permissions-transact-sql).</span></span>  
  
### <a name="example-a-setting-up-a-login-and-user-transact-sql"></a><span data-ttu-id="77f06-135">Exemplo A: Configurando um logon e um usuário (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="77f06-135">Example A: Setting Up a Login and User (Transact-SQL)</span></span>  
 <span data-ttu-id="77f06-136">O exemplo a seguir é relevante apenas se você optar por criar um novo logon e usuário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para backups de baixa prioridade.</span><span class="sxs-lookup"><span data-stu-id="77f06-136">The following example is relevant only if you choose to create a new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and user for low-priority backups.</span></span> <span data-ttu-id="77f06-137">Alternativamente, você pode usar um logon e um usuário existentes, se forem apropriados.</span><span class="sxs-lookup"><span data-stu-id="77f06-137">Alternatively, you can use an existing login and user, if an appropriate one exists.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="77f06-138">O exemplo a seguir usa um logon e um nome de usuário de exemplo, *domain_name*`\MAX_CPU`.</span><span class="sxs-lookup"><span data-stu-id="77f06-138">The following example uses a sample login and user name, *domain_name*`\MAX_CPU`.</span></span> <span data-ttu-id="77f06-139">Substitua-os pelos nomes de logon e de usuário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que serão usados ao criar backups compactados de baixa prioridade.</span><span class="sxs-lookup"><span data-stu-id="77f06-139">Replace these with the names of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and user that you plan to use when creating your low-priority compressed backups.</span></span>  
  
 <span data-ttu-id="77f06-140">Esse exemplo cria um logon para a conta do Windows *domain_name*`\MAX_CPU` e, em seguida, concede a permissão VIEW SERVER STATE ao logon.</span><span class="sxs-lookup"><span data-stu-id="77f06-140">This example creates a login for the *domain_name*`\MAX_CPU` Windows account and then grants VIEW SERVER STATE permission to the login.</span></span> <span data-ttu-id="77f06-141">Essa permissão permite verificar a classificação do Administrador de Recursos de sessões do logon.</span><span class="sxs-lookup"><span data-stu-id="77f06-141">This permission enables you to verify the Resource Governor classification of sessions of the login.</span></span> <span data-ttu-id="77f06-142">Em seguida, o exemplo cria um usuário para *domain_name*`\MAX_CPU` e o adiciona à função de banco de dados fixa db_backupoperator do banco de dados de exemplo do [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="77f06-142">The example then creates a user for *domain_name*`\MAX_CPU` and adds it to the db_backupoperator fixed database role for the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="77f06-143">Esse nome de usuário será usado pela função de classificação do Administrador de Recursos.</span><span class="sxs-lookup"><span data-stu-id="77f06-143">This user name will be used by the Resource Governor classifier function.</span></span>  
  
```sql  
-- Create a SQL Server login for low-priority operations  
USE master;  
CREATE LOGIN [domain_name\MAX_CPU] FROM WINDOWS;  
GRANT VIEW SERVER STATE TO [domain_name\MAX_CPU];  
GO  
-- Create a SQL Server user in AdventureWorks2012 for this login  
USE AdventureWorks2012;  
CREATE USER [domain_name\MAX_CPU] FOR LOGIN [domain_name\MAX_CPU];  
EXEC sp_addrolemember 'db_backupoperator', 'domain_name\MAX_CPU';  
GO  
  
```  
  
 [<span data-ttu-id="77f06-144">&#91;Início&#93;</span><span class="sxs-lookup"><span data-stu-id="77f06-144">&#91;Top&#93;</span></span>](#Top)  
  
##  <a name="configuring-resource-governor-to-limit-cpu-usage"></a><a name="configure_RG"></a> <span data-ttu-id="77f06-145">Configurando o Administrador de Recursos para limitar o uso de CPU</span><span class="sxs-lookup"><span data-stu-id="77f06-145">Configuring Resource Governor to Limit CPU Usage</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="77f06-146">Verifique se o Administrador de Recursos está habilitado.</span><span class="sxs-lookup"><span data-stu-id="77f06-146">Ensure that Resource Governor is enabled.</span></span> <span data-ttu-id="77f06-147">Para obter mais informações, consulte [Habilitar Administrador de Recursos](../resource-governor/enable-resource-governor.md).</span><span class="sxs-lookup"><span data-stu-id="77f06-147">For more information, see [Enable Resource Governor](../resource-governor/enable-resource-governor.md).</span></span>  
  
 <span data-ttu-id="77f06-148">Neste cenário do Administrador de Recursos, a configuração inclui as seguintes etapas básicas:</span><span class="sxs-lookup"><span data-stu-id="77f06-148">In this Resource Governor scenario, configuration comprises the following basic steps:</span></span>  
  
1.  <span data-ttu-id="77f06-149">Criar e configurar um pool de recursos do Administrador de Recursos que limite a largura de banda média máxima da CPU que será fornecida a solicitações no pool de recursos quando houver contenção de CPU.</span><span class="sxs-lookup"><span data-stu-id="77f06-149">Create and configure a Resource Governor resource pool that limits the maximum average CPU bandwidth that will be given to requests in the resource pool when CPU contention occurs.</span></span>  
  
2.  <span data-ttu-id="77f06-150">Criar e configurar um grupo de carga de trabalho do Administrador de Recursos que use esse pool.</span><span class="sxs-lookup"><span data-stu-id="77f06-150">Create and configure a Resource Governor workload group that uses this pool.</span></span>  
  
3.  <span data-ttu-id="77f06-151">Criar uma *função de classificação*, que seja uma UDF (função definida pelo usuário) cujos valores de retorno sejam usados pelo Administrador de Recursos para classificar sessões para que sejam roteadas para o grupo de carga de trabalho adequado.</span><span class="sxs-lookup"><span data-stu-id="77f06-151">Create a *classifier function*, which is a user-defined function (UDF) whose return values are used by Resource Governor for classifying sessions so that they are routed to the appropriate workload group.</span></span>  
  
4.  <span data-ttu-id="77f06-152">Registrar a função de classificação com o Administrador de Recursos.</span><span class="sxs-lookup"><span data-stu-id="77f06-152">Register the classifier function with Resource Governor.</span></span>  
  
5.  <span data-ttu-id="77f06-153">Aplicar as alterações à configuração na memória do Administrador de Recursos.</span><span class="sxs-lookup"><span data-stu-id="77f06-153">Apply the changes to the Resource Governor in-memory configuration.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="77f06-154">Para obter informações sobre pools de recursos do Administrador de Recursos, grupos de carga de trabalho e classificação, consulte [Administrador de Recursos](../resource-governor/resource-governor.md).</span><span class="sxs-lookup"><span data-stu-id="77f06-154">For information about Resource Governor resource pools, workload groups, and classification, see [Resource Governor](../resource-governor/resource-governor.md).</span></span>  
  
 <span data-ttu-id="77f06-155">As instruções do [!INCLUDE[tsql](../../includes/tsql-md.md)] para essas etapas são descritas no procedimento, "Para configurar o Administrador de Recursos para limitar o uso de CPU", que é seguido por um exemplo do procedimento do [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="77f06-155">The [!INCLUDE[tsql](../../includes/tsql-md.md)] statements for these steps are described in the procedure, "To configure Resource Governor for limiting CPU usage," which is followed by a [!INCLUDE[tsql](../../includes/tsql-md.md)] example of the procedure.</span></span>  
  
 <span data-ttu-id="77f06-156">**Para configurar o Administrador de Recursos (SQL Server Management Studio)**</span><span class="sxs-lookup"><span data-stu-id="77f06-156">**To configure Resource Governor (SQL Server Management Studio)**</span></span>  
  
-   [<span data-ttu-id="77f06-157">Configurar o Resource Governor usando um modelo</span><span class="sxs-lookup"><span data-stu-id="77f06-157">Configure Resource Governor Using a Template</span></span>](../resource-governor/configure-resource-governor-using-a-template.md)  
  
-   [<span data-ttu-id="77f06-158">Criar um pool de recursos</span><span class="sxs-lookup"><span data-stu-id="77f06-158">Create a Resource Pool</span></span>](../resource-governor/create-a-resource-pool.md)  
  
-   [<span data-ttu-id="77f06-159">Criar um grupo de carga de trabalho</span><span class="sxs-lookup"><span data-stu-id="77f06-159">Create a Workload Group</span></span>](../resource-governor/create-a-workload-group.md)  
  
### <a name="to-configure-resource-governor-for-limiting-cpu-usage-transact-sql"></a><span data-ttu-id="77f06-160">Para configurar o Administrador de Recursos para limitar o uso de CPU (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="77f06-160">To configure Resource Governor for limiting CPU usage (Transact-SQL)</span></span>  
  
1.  <span data-ttu-id="77f06-161">Emita uma instrução [CREATE RESOURCE POOL](/sql/t-sql/statements/create-resource-pool-transact-sql) para criar um pool de recursos.</span><span class="sxs-lookup"><span data-stu-id="77f06-161">Issue a [CREATE RESOURCE POOL](/sql/t-sql/statements/create-resource-pool-transact-sql) statement to create a resource pool.</span></span> <span data-ttu-id="77f06-162">O exemplo deste procedimento usa a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="77f06-162">The example for this procedure uses the following syntax:</span></span>  
  
     <span data-ttu-id="77f06-163">*CREATE RESOURCE POOL pool_name* WITH ( MAX_CPU_PERCENT = *value* );</span><span class="sxs-lookup"><span data-stu-id="77f06-163">*CREATE RESOURCE POOL pool_name* WITH ( MAX_CPU_PERCENT = *value* );</span></span>  
  
     <span data-ttu-id="77f06-164">*Value* é um inteiro de 1 a 100 que indica a porcentagem da largura de banda média máxima da CPU.</span><span class="sxs-lookup"><span data-stu-id="77f06-164">*Value* is an integer from 1 to 100 that indicates the percentage of maximum average CPU bandwidth.</span></span> <span data-ttu-id="77f06-165">O valor adequado depende do ambiente.</span><span class="sxs-lookup"><span data-stu-id="77f06-165">The appropriate value depends on your environment.</span></span> <span data-ttu-id="77f06-166">Para fins de ilustração, o exemplo deste tópico usa 20 por cento (MAX_CPU_PERCENT = 20).</span><span class="sxs-lookup"><span data-stu-id="77f06-166">For the purpose of illustration, the example in this topic uses 20%  percent (MAX_CPU_PERCENT = 20.)</span></span>  
  
2.  <span data-ttu-id="77f06-167">Emita uma instrução [CREATE WORKLOAD GROUP](/sql/t-sql/statements/create-workload-group-transact-sql) para criar um grupo de carga de trabalho para operações de baixa prioridade cujo uso de CPU deve ser administrado.</span><span class="sxs-lookup"><span data-stu-id="77f06-167">Issue a [CREATE WORKLOAD GROUP](/sql/t-sql/statements/create-workload-group-transact-sql) statement to create a workload group for low-priority operations whose CPU usage you want to govern.</span></span> <span data-ttu-id="77f06-168">O exemplo deste procedimento usa a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="77f06-168">The example for this procedure uses the following syntax:</span></span>  
  
     <span data-ttu-id="77f06-169">CREATE WORKLOAD GROUP *group_name* USING *pool_name*;</span><span class="sxs-lookup"><span data-stu-id="77f06-169">CREATE WORKLOAD GROUP *group_name* USING *pool_name*;</span></span>  
  
3.  <span data-ttu-id="77f06-170">Emita uma instrução [CREATE FUNCTION](/sql/t-sql/statements/create-function-transact-sql) para criar uma função de classificação que mapeie o grupo de carga de trabalho criado na etapa anterior para o usuário do logon de baixa prioridade.</span><span class="sxs-lookup"><span data-stu-id="77f06-170">Issue a [CREATE FUNCTION](/sql/t-sql/statements/create-function-transact-sql) statement to create a classifier function that maps the workload group created in the preceding step to the user of the low-priority login.</span></span> <span data-ttu-id="77f06-171">O exemplo deste procedimento usa a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="77f06-171">The example for this procedure uses the following syntax:</span></span>  
  
     <span data-ttu-id="77f06-172">CREATE FUNCTION [*schema_name*.]*function_name*() RETURNS sysname</span><span class="sxs-lookup"><span data-stu-id="77f06-172">CREATE FUNCTION [*schema_name*.]*function_name*() RETURNS sysname</span></span>  
  
     <span data-ttu-id="77f06-173">WITH SCHEMABINDING</span><span class="sxs-lookup"><span data-stu-id="77f06-173">WITH SCHEMABINDING</span></span>  
  
     <span data-ttu-id="77f06-174">AS</span><span class="sxs-lookup"><span data-stu-id="77f06-174">AS</span></span>  
  
     <span data-ttu-id="77f06-175">BEGIN</span><span class="sxs-lookup"><span data-stu-id="77f06-175">BEGIN</span></span>  
  
     <span data-ttu-id="77f06-176">DECLARE @workload_group_name AS *sysname*</span><span class="sxs-lookup"><span data-stu-id="77f06-176">DECLARE @workload_group_name AS *sysname*</span></span>  
  
     <span data-ttu-id="77f06-177">IF (SUSER_NAME() = '*user_of_low_priority_login*')</span><span class="sxs-lookup"><span data-stu-id="77f06-177">IF (SUSER_NAME() = '*user_of_low_priority_login*')</span></span>  
  
     <span data-ttu-id="77f06-178">SET @workload_group_name = '*workload_group_name*'</span><span class="sxs-lookup"><span data-stu-id="77f06-178">SET @workload_group_name = '*workload_group_name*'</span></span>  
  
     <span data-ttu-id="77f06-179">RETURN @workload_group_name</span><span class="sxs-lookup"><span data-stu-id="77f06-179">RETURN @workload_group_name</span></span>  
  
     <span data-ttu-id="77f06-180">END</span><span class="sxs-lookup"><span data-stu-id="77f06-180">END</span></span>  
  
     <span data-ttu-id="77f06-181">Para obter informações sobre os componentes dessa instrução CREATE FUNCTION, consulte:</span><span class="sxs-lookup"><span data-stu-id="77f06-181">For information about the components of this CREATE FUNCTION statement, see:</span></span>  
  
    -   [<span data-ttu-id="77f06-182">DECLARE @local_variable &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="77f06-182">DECLARE @local_variable &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/declare-local-variable-transact-sql)  
  
    -   [<span data-ttu-id="77f06-183">SUSER_SNAME &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="77f06-183">SUSER_SNAME &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/suser-sname-transact-sql)  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="77f06-184">SUSER_NAME é apenas uma das várias funções do sistema que podem ser usadas em uma função de classificação.</span><span class="sxs-lookup"><span data-stu-id="77f06-184">SUSER_NAME is just one of several system functions that can be used in a classifier function.</span></span> <span data-ttu-id="77f06-185">Para obter mais informações, consulte [Criar e testar uma função de classificação definida pelo usuário](../resource-governor/create-and-test-a-classifier-user-defined-function.md).</span><span class="sxs-lookup"><span data-stu-id="77f06-185">For more information, see [Create and Test a Classifier User-Defined Function](../resource-governor/create-and-test-a-classifier-user-defined-function.md).</span></span>  
  
    -   <span data-ttu-id="77f06-186">[SET @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/set-local-variable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="77f06-186">[SET @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/set-local-variable-transact-sql).</span></span>  
  
4.  <span data-ttu-id="77f06-187">Emita uma instrução [ALTER RESOURCE GOVERNOR](/sql/t-sql/statements/alter-resource-governor-transact-sql) para registrar a função de classificação com o Administrador de Recursos.</span><span class="sxs-lookup"><span data-stu-id="77f06-187">Issue an [ALTER RESOURCE GOVERNOR](/sql/t-sql/statements/alter-resource-governor-transact-sql) statement to register the classifier function with Resource Governor.</span></span> <span data-ttu-id="77f06-188">O exemplo deste procedimento usa a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="77f06-188">The example for this procedure uses the following syntax:</span></span>  
  
     <span data-ttu-id="77f06-189">ALTER RESOURCE GOVERNOR WITH (CLASSIFIER_FUNCTION = *schema_name*.*function_name*);</span><span class="sxs-lookup"><span data-stu-id="77f06-189">ALTER RESOURCE GOVERNOR WITH (CLASSIFIER_FUNCTION = *schema_name*.*function_name*);</span></span>  
  
5.  <span data-ttu-id="77f06-190">Emita uma segunda instrução ALTER RESOURCE GOVERNADOR para aplicar as alterações à configuração na memória do Administrador de Recursos, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="77f06-190">Issue a second ALTER RESOURCE GOVERNOR statement to apply the changes to the Resource Governor in-memory configuration, as follows:</span></span>  
  
    ```  
    ALTER RESOURCE GOVERNOR RECONFIGURE;  
    ```  
  
### <a name="example-b-configuring-resource-governor-transact-sql"></a><span data-ttu-id="77f06-191">Exemplo B: Configurando o Resource Governor (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="77f06-191">Example B: Configuring Resource Governor (Transact-SQL)</span></span>  
 <span data-ttu-id="77f06-192">O exemplo a seguir executa as seguintes etapas em uma única transação:</span><span class="sxs-lookup"><span data-stu-id="77f06-192">The following example performs the following steps within a single transaction:</span></span>  
  
1.  <span data-ttu-id="77f06-193">Cria o pool de recursos `pMAX_CPU_PERCENT_20` .</span><span class="sxs-lookup"><span data-stu-id="77f06-193">Creates the `pMAX_CPU_PERCENT_20` resource pool.</span></span>  
  
2.  <span data-ttu-id="77f06-194">Cria o grupo de carga de trabalho `gMAX_CPU_PERCENT_20` .</span><span class="sxs-lookup"><span data-stu-id="77f06-194">Creates the `gMAX_CPU_PERCENT_20` workload group.</span></span>  
  
3.  <span data-ttu-id="77f06-195">Cria a função de classificação `rgclassifier_MAX_CPU()` que usa o nome de usuário criado no exemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="77f06-195">Creates the `rgclassifier_MAX_CPU()` classifier function, which uses the user name created in the preceding example.</span></span>  
  
4.  <span data-ttu-id="77f06-196">Registra a função de classificação no Administrador de Recursos.</span><span class="sxs-lookup"><span data-stu-id="77f06-196">Registers the classifier function with Resource Governor.</span></span>  
  
 <span data-ttu-id="77f06-197">Após confirmar a transação, o exemplo aplica as alterações da configuração nas instruções ALTER WORKLOAD GROUP ou ATER RESOURCE POOL.</span><span class="sxs-lookup"><span data-stu-id="77f06-197">After committing the transaction, the example applies the configuration changes requested in the ALTER WORKLOAD GROUP or ALTER RESOURCE POOL statements.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="77f06-198">O seguinte exemplo usa o nome de usuário de exemplo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] criado no "Exemplo A: Configurando um logon e um usuário (Transact-SQL)", *domain_name*`\MAX_CPU`.</span><span class="sxs-lookup"><span data-stu-id="77f06-198">The following example uses the user name of the sample [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user created in "Example A: Setting Up a Login and User (Transact-SQL)," *domain_name*`\MAX_CPU`.</span></span> <span data-ttu-id="77f06-199">Substitua-os pelo nome do usuário do logon que será usado para criar backups compactados de baixa prioridade.</span><span class="sxs-lookup"><span data-stu-id="77f06-199">Replace this with the name of the user of the login that you plan to use for creating low-priority compressed backups.</span></span>  
  
```sql  
-- Configure Resource Governor.  
BEGIN TRAN  
USE master;  
-- Create a resource pool that sets the MAX_CPU_PERCENT to 20%.   
CREATE RESOURCE POOL pMAX_CPU_PERCENT_20  
   WITH  
      (MAX_CPU_PERCENT = 20);  
GO  
-- Create a workload group to use this pool.   
CREATE WORKLOAD GROUP gMAX_CPU_PERCENT_20  
USING pMAX_CPU_PERCENT_20;  
GO  
-- Create a classification function.  
-- Note that any request that does not get classified goes into   
-- the 'Default' group.  
CREATE FUNCTION dbo.rgclassifier_MAX_CPU() RETURNS sysname   
WITH SCHEMABINDING  
AS  
BEGIN  
    DECLARE @workload_group_name AS sysname  
      IF (SUSER_NAME() = 'domain_name\MAX_CPU')  
          SET @workload_group_name = 'gMAX_CPU_PERCENT_20'  
    RETURN @workload_group_name  
END;  
GO  
  
-- Register the classifier function with Resource Governor.  
ALTER RESOURCE GOVERNOR WITH (CLASSIFIER_FUNCTION= dbo.rgclassifier_MAX_CPU);  
COMMIT TRAN;  
GO  
-- Start Resource Governor  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
  
```  
  
 [<span data-ttu-id="77f06-200">&#91;Início&#93;</span><span class="sxs-lookup"><span data-stu-id="77f06-200">&#91;Top&#93;</span></span>](#Top)  
  
##  <a name="verifying-the-classification-of-the-current-session-transact-sql"></a><a name="verifying"></a> <span data-ttu-id="77f06-201">Verificando a classificação da sessão atual (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="77f06-201">Verifying the Classification of the Current Session (Transact-SQL)</span></span>  
 <span data-ttu-id="77f06-202">Opcionalmente, faça logon como o usuário especificado na função de classificação e verifique a classificação da sessão emitindo a seguinte instrução [SELECT](/sql/t-sql/queries/select-transact-sql) no Pesquisador de Objetos:</span><span class="sxs-lookup"><span data-stu-id="77f06-202">Optionally, log in as the user that you specified in your classifier function, and verify the session classification by issuing the following [SELECT](/sql/t-sql/queries/select-transact-sql) statement in Object Explorer:</span></span>  
  
```sql  
USE master;  
SELECT sess.session_id, sess.login_name, sess.group_id, grps.name   
FROM sys.dm_exec_sessions AS sess   
JOIN sys.dm_resource_governor_workload_groups AS grps   
    ON sess.group_id = grps.group_id  
WHERE session_id > 50;  
GO  
```  
  
 <span data-ttu-id="77f06-203">No painel de resultados, a coluna **name** deve listar uma ou mais sessões para o nome do grupo de cargas de trabalho especificado na função de classificação.</span><span class="sxs-lookup"><span data-stu-id="77f06-203">In the results pane, the **name** column should list one or more sessions for the workload-group name that you specified in your classifier function.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="77f06-204">Para obter informações sobre as exibições de gerenciamento dinâmico chamado por essa instrução SELECT, consulte [sys.dm_exec_sessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) e [sys.dm_resource_governor_workload_groups &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-workload-groups-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="77f06-204">For information about the dynamic management views called by this SELECT statement, see [sys.dm_exec_sessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) and [sys.dm_resource_governor_workload_groups &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-workload-groups-transact-sql).</span></span>  
  
 [<span data-ttu-id="77f06-205">&#91;Início&#93;</span><span class="sxs-lookup"><span data-stu-id="77f06-205">&#91;Top&#93;</span></span>](#Top)  
  
##  <a name="compressing-backups-using-a-session-with-limited-cpu"></a><a name="creating_compressed_backup"></a> <span data-ttu-id="77f06-206">Compactando backups usando uma sessão com CPU limitada</span><span class="sxs-lookup"><span data-stu-id="77f06-206">Compressing Backups Using a Session with Limited CPU</span></span>  
 <span data-ttu-id="77f06-207">Para criar um backup compactado em uma sessão com uma CPU máxima limitada, faça logon como o usuário especificado na função de classificação.</span><span class="sxs-lookup"><span data-stu-id="77f06-207">To create a compressed backup in a session with a limited maximum CPU, log in as the user specified in your classifier function.</span></span> <span data-ttu-id="77f06-208">No comando backup, especifique com COMPACTação ( [!INCLUDE[tsql](../../includes/tsql-md.md)] ) ou selecione **Compactar backup** ( [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="77f06-208">In your backup command, either specify WITH COMPRESSION ([!INCLUDE[tsql](../../includes/tsql-md.md)]) or select **Compress backup** ([!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]).</span></span> <span data-ttu-id="77f06-209">Para criar um backup de banco de dados compactado, consulte [Criar um backup completo de banco de dados &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="77f06-209">To create a compressed database backup, see [Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span></span>  
  
### <a name="example-c-creating-a-compressed-backup-transact-sql"></a><span data-ttu-id="77f06-210">Exemplo C: Criando um backup compactado (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="77f06-210">Example C: Creating a Compressed Backup (Transact-SQL)</span></span>  
 <span data-ttu-id="77f06-211">O exemplo de [BACKUP](/sql/t-sql/statements/backup-transact-sql) a seguir cria um backup completo compactado do banco de dados [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] em um arquivo de backup recém-formatado, `Z:\SQLServerBackups\AdvWorksData.bak`.</span><span class="sxs-lookup"><span data-stu-id="77f06-211">The following [BACKUP](/sql/t-sql/statements/backup-transact-sql) example creates a compressed full backup of the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database in a newly formatted backup file, `Z:\SQLServerBackups\AdvWorksData.bak`.</span></span>  
  
```sql  
--Run backup statement in the gBackup session.  
BACKUP DATABASE AdventureWorks2012 TO DISK='Z:\SQLServerBackups\AdvWorksData.bak'   
WITH   
   FORMAT,   
   MEDIADESCRIPTION='AdventureWorks2012 Compressed Data Backups'  
   DESCRIPTION='First database backup on AdventureWorks2012 Compressed Data Backups media set'  
   COMPRESSION;  
GO  
```  
  
 [<span data-ttu-id="77f06-212">&#91;Início&#93;</span><span class="sxs-lookup"><span data-stu-id="77f06-212">&#91;Top&#93;</span></span>](#Top)  
  
## <a name="see-also"></a><span data-ttu-id="77f06-213">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="77f06-213">See Also</span></span>  
 <span data-ttu-id="77f06-214">[Criar e testar uma função de classificação definida pelo usuário](../resource-governor/create-and-test-a-classifier-user-defined-function.md) </span><span class="sxs-lookup"><span data-stu-id="77f06-214">[Create and Test a Classifier User-Defined Function](../resource-governor/create-and-test-a-classifier-user-defined-function.md) </span></span>  
 [<span data-ttu-id="77f06-215">Resource Governor</span><span class="sxs-lookup"><span data-stu-id="77f06-215">Resource Governor</span></span>](../resource-governor/resource-governor.md)  
  
  
