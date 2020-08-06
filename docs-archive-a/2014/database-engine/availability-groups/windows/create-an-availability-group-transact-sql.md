---
title: Criar um grupo de disponibilidade (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], creating
ms.assetid: 8b0a6301-8b79-4415-b608-b40876f30066
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 57a494af168a8f5572bafe93f8fb47b22a954a19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686372"
---
# <a name="create-an-availability-group-transact-sql"></a><span data-ttu-id="28caf-102">Criar um grupo de disponibilidade (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="28caf-102">Create an Availability Group (Transact-SQL)</span></span>
  <span data-ttu-id="28caf-103">Este tópico descreve como usar [!INCLUDE[tsql](../../../includes/tsql-md.md)] para criar e configurar um grupo de disponibilidade em instâncias de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] no qual o recurso [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] é habilitado.</span><span class="sxs-lookup"><span data-stu-id="28caf-103">This topic describes how to use [!INCLUDE[tsql](../../../includes/tsql-md.md)] to create and configure an availability group on instances of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] on which the [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] feature is enabled.</span></span> <span data-ttu-id="28caf-104">Um *grupo de disponibilidade* define um conjunto de bancos de dados de usuários que realizará o failover como uma única unidade e um conjunto de parceiros de failover, conhecido como *réplicas de disponibilidade*, que oferece suporte a failover.</span><span class="sxs-lookup"><span data-stu-id="28caf-104">An *availability group* defines a set of user databases that will fail over as a single unit and a set of failover partners, known as *availability replicas*, that support failover.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="28caf-105">Para obter uma introdução aos grupos de disponibilidade, consulte [Visão geral dos grupos de disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="28caf-105">For an introduction to availability groups, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span>  

> [!NOTE]  
>  <span data-ttu-id="28caf-106">Como alternativa ao uso do [!INCLUDE[tsql](../../../includes/tsql-md.md)], você pode usar o assistente para Criar Grupo de Disponibilidade ou os cmdlets do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28caf-106">As an alternative to using [!INCLUDE[tsql](../../../includes/tsql-md.md)], you can use the Create Availability Group wizard or [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell cmdlets.</span></span> <span data-ttu-id="28caf-107">Para obter mais informações, veja [Usar o Assistente de Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;](use-the-availability-group-wizard-sql-server-management-studio.md), [Usar a caixa de diálogo Novo Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)ou [Criar um grupo de disponibilidade &#40;SQL Server PowerShell&#41;](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="28caf-107">For more information, see [Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;](use-the-availability-group-wizard-sql-server-management-studio.md), [Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;](use-the-new-availability-group-dialog-box-sql-server-management-studio.md), or [Create an Availability Group &#40;SQL Server PowerShell&#41;](../../../powershell/sql-server-powershell.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="28caf-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="28caf-108">Before You Begin</span></span>  
 <span data-ttu-id="28caf-109">É recomendável que você leia esta seção antes de tentar criar seu primeiro grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="28caf-109">We strongly recommend that you read this section before attempting to create your first availability group.</span></span>  
  
###  <a name="prerequisites-restrictions-and-recommendations"></a><a name="PrerequisitesRestrictions"></a><span data-ttu-id="28caf-110">Pré-requisitos, restrições e recomendações</span><span class="sxs-lookup"><span data-stu-id="28caf-110">Prerequisites, Restrictions, and Recommendations</span></span>  
  
-   <span data-ttu-id="28caf-111">Antes de criar um grupo de disponibilidade, verifique se as instâncias do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que hospedam réplicas de disponibilidade residem em um nó diferente do WSFC (Windows Server Failover Clustering), dentro do mesmo cluster de failover do WSFC.</span><span class="sxs-lookup"><span data-stu-id="28caf-111">Before creating an availability group, verify that the instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that host availability replicas reside on different Windows Server Failover Clustering (WSFC) node within the same WSFC failover cluster.</span></span> <span data-ttu-id="28caf-112">Também verifique se cada instância de servidor atende todos os outros pré-requisitos de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="28caf-112">Also, verify that each of the server instance meets all other [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] prerequisites.</span></span> <span data-ttu-id="28caf-113">Para obter mais informações, é altamente recomendável que você leia [Pré-requisitos, restrições e recomendações para grupos de disponibilidade AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="28caf-113">For more information, we strongly recommend that you read [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="28caf-114">Segurança</span><span class="sxs-lookup"><span data-stu-id="28caf-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="28caf-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="28caf-115">Permissions</span></span>  
 <span data-ttu-id="28caf-116">Requer a associação na função de servidor fixa **sysadmin** e a permissão de servidor CREATE AVAILABILITY GROUP, a permissão ALTER ANY AVAILABILITY GROUP ou a permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="28caf-116">Requires membership in the **sysadmin** fixed server role and either CREATE AVAILABILITY GROUP server permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
###  <a name="summary-of-tasks-and-corresponding-transact-sql-statements"></a><a name="SummaryTsqlStatements"></a> <span data-ttu-id="28caf-117">Resumo de tarefas e instruções Transact-SQL correspondentes</span><span class="sxs-lookup"><span data-stu-id="28caf-117">Summary of Tasks and Corresponding Transact-SQL Statements</span></span>  
 <span data-ttu-id="28caf-118">A tabela a seguir lista as tarefas básicas envolvidas na criação e configuração de um grupo de disponibilidade e indica quais instruções do [!INCLUDE[tsql](../../../includes/tsql-md.md)] serão usadas nessas tarefas.</span><span class="sxs-lookup"><span data-stu-id="28caf-118">The following table lists the basic tasks involved in creating and configuring an availability group and indicates which [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements to use for these tasks.</span></span> <span data-ttu-id="28caf-119">As tarefas [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] devem ser executadas na sequência em que são apresentadas na tabela.</span><span class="sxs-lookup"><span data-stu-id="28caf-119">The [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] tasks must be performed in the sequence in which they are presented in the table.</span></span>  
  
|<span data-ttu-id="28caf-120">Tarefa</span><span class="sxs-lookup"><span data-stu-id="28caf-120">Task</span></span>|<span data-ttu-id="28caf-121">Instrução(ões) Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="28caf-121">Transact-SQL Statement(s)</span></span>|<span data-ttu-id="28caf-122">Onde executar a tarefa**<sup>\*</sup>**</span><span class="sxs-lookup"><span data-stu-id="28caf-122">Where to Perform Task**<sup>\*</sup>**</span></span>|  
|----------|----------------------------------|-------------------------------------------|  
|<span data-ttu-id="28caf-123">Criar ponto de extremidade de espelhamento de banco de dados (uma vez por instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="28caf-123">Create database mirroring endpoint (once per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance)</span></span>|<span data-ttu-id="28caf-124">Criar *ponto* de [extremidade EndpointName](/sql/t-sql/statements/create-endpoint-transact-sql) ... PARA DATABASE_MIRRORING</span><span class="sxs-lookup"><span data-stu-id="28caf-124">[CREATE ENDPOINT](/sql/t-sql/statements/create-endpoint-transact-sql) *endpointName* ... FOR DATABASE_MIRRORING</span></span>|<span data-ttu-id="28caf-125">Executar em cada instância de servidor que não tem ponto de extremidade de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="28caf-125">Execute on each server instance that lacks database mirroring endpoint.</span></span>|  
|<span data-ttu-id="28caf-126">Criar grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="28caf-126">Create availability group</span></span>|[<span data-ttu-id="28caf-127">CRIAR GRUPO DE DISPONIBILIDADE</span><span class="sxs-lookup"><span data-stu-id="28caf-127">CREATE AVAILABILITY GROUP</span></span>](/sql/t-sql/statements/create-availability-group-transact-sql)|<span data-ttu-id="28caf-128">Execute na instância de servidor que deve hospedar a réplica primária inicial.</span><span class="sxs-lookup"><span data-stu-id="28caf-128">Execute on the server instance that is to host the initial primary replica.</span></span>|  
|<span data-ttu-id="28caf-129">Unir a réplica secundária ao grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="28caf-129">Join secondary replica to availability group</span></span>|<span data-ttu-id="28caf-130">[ALTER AVAILABILITY GROUP](join-a-secondary-replica-to-an-availability-group-sql-server.md) *group_name* JOIN</span><span class="sxs-lookup"><span data-stu-id="28caf-130">[ALTER AVAILABILITY GROUP](join-a-secondary-replica-to-an-availability-group-sql-server.md) *group_name* JOIN</span></span>|<span data-ttu-id="28caf-131">Execute em cada instância de servidor que hospeda uma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="28caf-131">Execute on each server instance that hosts a secondary replica.</span></span>|  
|<span data-ttu-id="28caf-132">Preparar os banco de dados secundários</span><span class="sxs-lookup"><span data-stu-id="28caf-132">Prepare the secondary database</span></span>|<span data-ttu-id="28caf-133">[Backup](/sql/t-sql/statements/backup-transact-sql) e [restauração](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="28caf-133">[BACKUP](/sql/t-sql/statements/backup-transact-sql) and [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>|<span data-ttu-id="28caf-134">Crie backups na instância de servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="28caf-134">Create backups on the server instance that hosts the primary replica.</span></span><br /><br /> <span data-ttu-id="28caf-135">Restaure backups em cada instância de servidor que hospeda uma réplica secundária, usando RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="28caf-135">Restore backups on each server instance that hosts a secondary replica, using RESTORE WITH NORECOVERY.</span></span>|  
|<span data-ttu-id="28caf-136">Iniciar a sincronização de dados unindo cada banco de dados secundário ao grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="28caf-136">Start data synchronization by joining each secondary database to availability group</span></span>|<span data-ttu-id="28caf-137">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) *database_name* SET HADR AVAILABILITY GROUP = *group_name*</span><span class="sxs-lookup"><span data-stu-id="28caf-137">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) *database_name* SET HADR AVAILABILITY GROUP = *group_name*</span></span>|<span data-ttu-id="28caf-138">Execute em cada instância de servidor que hospeda uma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="28caf-138">Execute on each server instance that hosts a secondary replica.</span></span>|  
  
 <span data-ttu-id="28caf-139">**<sup>\*</sup>** Para executar uma determinada tarefa, conecte-se à instância ou instâncias de servidor indicadas.</span><span class="sxs-lookup"><span data-stu-id="28caf-139">**<sup>\*</sup>**  To perform a given task, connect to the indicated server instance or instances.</span></span>  
  
##  <a name="using-transact-sql-to-create-and-configure-an-availability-group"></a><a name="TsqlProcedure"></a> <span data-ttu-id="28caf-140">Usando Transact-SQL para criar e configurar um grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="28caf-140">Using Transact-SQL to Create and Configure an Availability Group</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="28caf-141"> Para obter um procedimento de configuração de exemplo que contém exemplos de código de cada uma dessas instruções do [!INCLUDE[tsql](../../../includes/tsql-md.md)] , consulte [Exemplo: configurando um grupo de disponibilidade que usa a Autenticação do Windows](#ExampleConfigAGWinAuth).</span><span class="sxs-lookup"><span data-stu-id="28caf-141">For a sample configuration procedure containing code examples of each these [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements, see [Example: Configuring an Availability Group that Uses Windows Authentication](#ExampleConfigAGWinAuth).</span></span>  
  
1.  <span data-ttu-id="28caf-142">Conecte-se à instância de servidor que deve hospedar a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="28caf-142">Connect to the server instance that is to host the primary replica.</span></span>  
  
2.  <span data-ttu-id="28caf-143">Crie o grupo de disponibilidade usando a instrução [Create Availability Group](/sql/t-sql/statements/create-availability-group-transact-sql) [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="28caf-143">Create the availability group by using the [CREATE AVAILABILITY GROUP](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span>  
  
3.  <span data-ttu-id="28caf-144">Una a nova réplica secundária ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="28caf-144">Join the new secondary replica to the availability group.</span></span> <span data-ttu-id="28caf-145">Para obter mais informações, veja [Unir uma réplica secundária a um grupo de disponibilidade &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="28caf-145">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
4.  <span data-ttu-id="28caf-146">Para cada banco de dados do grupo de disponibilidade, crie um banco de dados secundário restaurando backups recentes do banco de dados primário, usando RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="28caf-146">For each database in the availability group, create a secondary database by restoring recent backups of the primary database, using RESTORE WITH NORECOVERY.</span></span> <span data-ttu-id="28caf-147">Para obter mais informações, veja [Exemplo: configurando um grupo de disponibilidade usando a Autenticação do Windows (Transact-SQL)](create-an-availability-group-transact-sql.md), começando pela etapa que restaura o backup do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="28caf-147">For more information, see [Example: Setting Up an Availability Group Using Windows Authentication (Transact-SQL)](create-an-availability-group-transact-sql.md), starting with the step that restores the database backup.</span></span>  
  
5.  <span data-ttu-id="28caf-148">Una cada novo banco de dados secundário ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="28caf-148">Join every new secondary database to the availability group.</span></span> <span data-ttu-id="28caf-149">Para obter mais informações, veja [Unir uma réplica secundária a um grupo de disponibilidade &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="28caf-149">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
##  <a name="example-configuring-an-availability-group-that-uses-windows-authentication"></a><a name="ExampleConfigAGWinAuth"></a> <span data-ttu-id="28caf-150">Exemplo: configurando um grupo de disponibilidade que usa a Autenticação do Windows</span><span class="sxs-lookup"><span data-stu-id="28caf-150">Example: Configuring an Availability Group that Uses Windows Authentication</span></span>  
 <span data-ttu-id="28caf-151">Esse exemplo cria um procedimento de configuração [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] de exemplo que usa o [!INCLUDE[tsql](../../../includes/tsql-md.md)] para configurar pontos de extremidade de espelhamento de banco de dados que usam a Autenticação do Windows e para criar e configurar um grupo de disponibilidade e seus bancos de dados secundários.</span><span class="sxs-lookup"><span data-stu-id="28caf-151">This example creates a sample [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] configuration procedure that uses [!INCLUDE[tsql](../../../includes/tsql-md.md)] to set up database mirroring endpoints that use Windows Authentication and to create and configure an availability group and its secondary databases.</span></span>  
  
 <span data-ttu-id="28caf-152">Esse exemplo contém as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="28caf-152">This example contains the following sections:</span></span>  
  
-   [<span data-ttu-id="28caf-153">Pré-requisitos para usar o procedimento de configuração de exemplo</span><span class="sxs-lookup"><span data-stu-id="28caf-153">Prerequisites for Using the Sample Configuration Procedure</span></span>](#PrerequisitesForExample)  
  
-   [<span data-ttu-id="28caf-154">Procedimento de configuração de exemplo</span><span class="sxs-lookup"><span data-stu-id="28caf-154">Sample Configuration Procedure</span></span>](#SampleProcedure)  
  
-   [<span data-ttu-id="28caf-155">Concluir o exemplo de código para procedimento de configuração de exemplo</span><span class="sxs-lookup"><span data-stu-id="28caf-155">Complete Code Example for Sample Configuration Procedure</span></span>](#CompleteCodeExample)  
  
###  <a name="prerequisites-for-using-the-sample-configuration-procedure"></a><a name="PrerequisitesForExample"></a> <span data-ttu-id="28caf-156">Pré-requisitos para usar o procedimento de configuração de exemplo</span><span class="sxs-lookup"><span data-stu-id="28caf-156">Prerequisites for Using the Sample Configuration Procedure</span></span>  
 <span data-ttu-id="28caf-157">Este procedimento de exemplo tem os seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="28caf-157">This sample procedure has the following requirements:</span></span>  
  
-   <span data-ttu-id="28caf-158">As instâncias de servidor devem oferecer suporte ao [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28caf-158">The server instances must support [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span> <span data-ttu-id="28caf-159">Para obter mais informações, consulte [Pré-requisitos, restrições e recomendações para grupos de disponibilidade AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="28caf-159">For more information, see [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
-   <span data-ttu-id="28caf-160">Dois bancos de dados de exemplo, *MyDb1* e *MyDb2*, devem existir na instância de servidor que hospedará a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="28caf-160">Two sample databases, *MyDb1* and *MyDb2*, must exist on the server instance that will host the primary replica.</span></span> <span data-ttu-id="28caf-161">Os exemplos de código a seguir criam e configuram esses dois bancos de dados, e criam um backup completo de cada um deles.</span><span class="sxs-lookup"><span data-stu-id="28caf-161">The following code examples create and configure these two databases and create a full backup of each.</span></span> <span data-ttu-id="28caf-162">Execute esses exemplos de código na instância de servidor na qual você pretende criar o grupo de disponibilidade de exemplo.</span><span class="sxs-lookup"><span data-stu-id="28caf-162">Execute these code examples on the server instance on which you intend to create the sample availability group.</span></span> <span data-ttu-id="28caf-163">Essa instância de servidor hospedará a réplica primária inicial do grupo de disponibilidade de exemplo.</span><span class="sxs-lookup"><span data-stu-id="28caf-163">This server instance will host the initial primary replica of the sample availability group.</span></span>  
  
    1.  <span data-ttu-id="28caf-164">Este exemplo do [!INCLUDE[tsql](../../../includes/tsql-md.md)] cria esses bancos de dados e os alteram para usar o modelo de recuperação completo:</span><span class="sxs-lookup"><span data-stu-id="28caf-164">The following [!INCLUDE[tsql](../../../includes/tsql-md.md)] example creates these databases and alters them to use the full recovery model:</span></span>  
  
        ```sql
        -- Create sample databases:  
        CREATE DATABASE MyDb1;  
        GO  
        ALTER DATABASE MyDb1 SET RECOVERY FULL;  
        GO  
  
        CREATE DATABASE MyDb2;  
        GO  
        ALTER DATABASE MyDb2 SET RECOVERY FULL;  
        GO  
        ```  
  
    2.  <span data-ttu-id="28caf-165">O exemplo de código a seguir cria um backup completo de banco de dados de *MyDb1* e *MyDb2*.</span><span class="sxs-lookup"><span data-stu-id="28caf-165">The following code example creates a full database backup of *MyDb1* and *MyDb2*.</span></span> <span data-ttu-id="28caf-166">Este exemplo de código usa um compartilhamento de backup fictício, o arquivos de arquivos de arquivos de backup \\ \\ *FILESERVER* \\ *SQLbackups*.</span><span class="sxs-lookup"><span data-stu-id="28caf-166">This code example uses a fictional backup share, \\\\*FILESERVER*\\*SQLbackups*.</span></span>  
  
        ```sql
        -- Backup sample databases:  
        BACKUP DATABASE MyDb1   
        TO DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
            WITH FORMAT  
        GO  
  
        BACKUP DATABASE MyDb2   
        TO DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
            WITH FORMAT  
        GO
        ```  
  
###  <a name="sample-configuration-procedure"></a><a name="SampleProcedure"></a> <span data-ttu-id="28caf-167">Procedimento de configuração de exemplo</span><span class="sxs-lookup"><span data-stu-id="28caf-167">Sample Configuration Procedure</span></span>  
 <span data-ttu-id="28caf-168">Nesta configuração de exemplo, a réplica de disponibilidade será criada em duas instâncias de servidor autônomas cujas contas de serviço são executadas em domínios diferentes, porém confiáveis (`DOMAIN1` e `DOMAIN2`).</span><span class="sxs-lookup"><span data-stu-id="28caf-168">In this sample configuration, the availability replica will be created on two stand-alone server instances whose service accounts run under different, but trusted, domains (`DOMAIN1` and `DOMAIN2`).</span></span>  
  
 <span data-ttu-id="28caf-169">A tabela a seguir resume os valores usados nesta configuração de exemplo.</span><span class="sxs-lookup"><span data-stu-id="28caf-169">The following table summarizes the values used in this sample configuration.</span></span>  
  
|<span data-ttu-id="28caf-170">Função inicial</span><span class="sxs-lookup"><span data-stu-id="28caf-170">Initial role</span></span>|<span data-ttu-id="28caf-171">Sistema</span><span class="sxs-lookup"><span data-stu-id="28caf-171">System</span></span>|<span data-ttu-id="28caf-172">Instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] host</span><span class="sxs-lookup"><span data-stu-id="28caf-172">Host [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Instance</span></span>|  
|------------------|------------|---------------------------------------------|  
|<span data-ttu-id="28caf-173">Primária</span><span class="sxs-lookup"><span data-stu-id="28caf-173">Primary</span></span>|`COMPUTER01`|`AgHostInstance`|  
|<span data-ttu-id="28caf-174">Secundário</span><span class="sxs-lookup"><span data-stu-id="28caf-174">Secondary</span></span>|`COMPUTER02`|<span data-ttu-id="28caf-175">Instância padrão.</span><span class="sxs-lookup"><span data-stu-id="28caf-175">Default instance.</span></span>|  
  
1.  <span data-ttu-id="28caf-176">Crie um ponto de extremidade de espelhamento de banco de dados chamado *dbm_endpoint* na instância de servidor em que você pretende criar o grupo de disponibilidade (uma instância denominada `AgHostInstance` em `COMPUTER01`).</span><span class="sxs-lookup"><span data-stu-id="28caf-176">Create a database mirroring endpoint named *dbm_endpoint* on the server instance on which you plan to create the availability group (this is an instance named `AgHostInstance` on `COMPUTER01`).</span></span> <span data-ttu-id="28caf-177">Esse ponto de extremidade usa a porta 7022.</span><span class="sxs-lookup"><span data-stu-id="28caf-177">This endpoint uses port 7022.</span></span> <span data-ttu-id="28caf-178">Observe que a instância de servidor na qual você cria o grupo de disponibilidade hospedará a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="28caf-178">Note that the server instance on which you create the availability group will host the primary replica.</span></span>  
  
    ```sql
    -- Create endpoint on server instance that hosts the primary replica:  
    CREATE ENDPOINT dbm_endpoint  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO
    ```  
  
2.  <span data-ttu-id="28caf-179">Crie um ponto de extremidade *dbm_endpoint* na instância de servidor que hospedará a réplica secundária (a instância de servidor padrão em `COMPUTER02`).</span><span class="sxs-lookup"><span data-stu-id="28caf-179">Create an endpoint *dbm_endpoint* on the server instance that will host the secondary replica (this is the default server instance on `COMPUTER02`).</span></span> <span data-ttu-id="28caf-180">Esse ponto de extremidade usa a porta 5022.</span><span class="sxs-lookup"><span data-stu-id="28caf-180">This endpoint uses port 5022.</span></span>  
  
    ```sql
    -- Create endpoint on server instance that hosts the secondary replica:   
    CREATE ENDPOINT dbm_endpoint  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=5022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO
    ```  
  
3.  > [!NOTE]  
    >  <span data-ttu-id="28caf-181">Se as contas de serviço das instâncias de servidor que devem hospedar suas réplicas de disponibilidade forem executadas na mesma conta de domínio, esta etapa é desnecessária.</span><span class="sxs-lookup"><span data-stu-id="28caf-181">If the service accounts of the server instances that are to host your availability replicas run under the same domain account this step is unnecessary.</span></span> <span data-ttu-id="28caf-182">Ignore-a e vá diretamente para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="28caf-182">Skip it and go directly to the next step.</span></span>  
  
     <span data-ttu-id="28caf-183">Se as contas de serviço das instâncias de servidor forem executadas em usuários de domínio diferentes, em cada instância de servidor, crie um logon para a outra instância de servidor e conceda essa permissão de logon para acessar o ponto de extremidade de espelhamento de banco de dados local.</span><span class="sxs-lookup"><span data-stu-id="28caf-183">If the service accounts of the server instances run under different domain users, on each server instance, create a login for the other server instance and grant this login permission to access the local database mirroring endpoint.</span></span>  
  
     <span data-ttu-id="28caf-184">O exemplo de código a seguir mostra as instruções do [!INCLUDE[tsql](../../../includes/tsql-md.md)] para criar um logon e conceder a ele a permissão em um ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="28caf-184">The following code example shows the [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements for creating a login and granting it permission on an endpoint.</span></span> <span data-ttu-id="28caf-185">A conta de domínio da instância de servidor remoto é representada aqui como *domain_name*\\*user_name*.</span><span class="sxs-lookup"><span data-stu-id="28caf-185">The domain account of the remote server instance is represented here as *domain_name*\\*user_name*.</span></span>  
  
    ```sql
    -- If necessary, create a login for the service account, domain_name\user_name  
    -- of the server instance that will host the other replica:  
    USE master;  
    GO  
    CREATE LOGIN [domain_name\user_name] FROM WINDOWS;  
    GO  
    -- And Grant this login connect permissions on the endpoint:  
    GRANT CONNECT ON ENDPOINT::dbm_endpoint   
       TO [domain_name\user_name];  
    GO  
    ```  
  
4.  <span data-ttu-id="28caf-186">Na instância de servidor onde os bancos de dados de usuário residem, crie o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="28caf-186">On the server instance where the user databases reside, create the availability group.</span></span>  
  
     <span data-ttu-id="28caf-187">O exemplo de código a seguir cria um grupo de disponibilidade chamado *MyAG* na instância de servidor em que os bancos de dados de exemplo, *MyDb1* e *MyDb2*, foram criados.</span><span class="sxs-lookup"><span data-stu-id="28caf-187">The following code example creates an availability group named *MyAG* on the server instance on which the sample databases, *MyDb1* and *MyDb2*, were created.</span></span> <span data-ttu-id="28caf-188">Na `AgHostInstance`COMPUTER01 *, a instância de servidor local* é especificada primeiro.</span><span class="sxs-lookup"><span data-stu-id="28caf-188">The local server instance, `AgHostInstance`, on *COMPUTER01* is specified first.</span></span> <span data-ttu-id="28caf-189">Essa instância hospedará a réplica primária inicial.</span><span class="sxs-lookup"><span data-stu-id="28caf-189">This instance will host the initial primary replica.</span></span> <span data-ttu-id="28caf-190">Uma instância de servidor remota, a instância de servidor padrão em *COMPUTER02*, é especificada para hospedar uma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="28caf-190">A remote server instance, the default server instance on *COMPUTER02*, is specified to host a secondary replica.</span></span> <span data-ttu-id="28caf-191">Ambas as réplicas de disponibilidade são configuradas para usar o modo de confirmação assíncrona com failover manual (para réplicas de confirmação assíncrona, failover manual significa failover forçado com possível perda de dados).</span><span class="sxs-lookup"><span data-stu-id="28caf-191">Both availability replica are configured to use asynchronous-commit mode with manual failover (for asynchronous-commit replicas manual failover means  forced failover with possible data loss).</span></span>  
  
    ```sql
    -- Create the availability group, MyAG:   
    CREATE AVAILABILITY GROUP MyAG   
       FOR   
          DATABASE MyDB1, MyDB2   
       REPLICA ON   
          'COMPUTER01\AgHostInstance' WITH   
             (  
             ENDPOINT_URL = 'TCP://COMPUTER01.Adventure-Works.com:7022',   
             AVAILABILITY_MODE = ASYNCHRONOUS_COMMIT,  
             FAILOVER_MODE = MANUAL  
             ),  
          'COMPUTER02' WITH   
             (  
             ENDPOINT_URL = 'TCP://COMPUTER02.Adventure-Works.com:5022',  
             AVAILABILITY_MODE = ASYNCHRONOUS_COMMIT,  
             FAILOVER_MODE = MANUAL  
             );   
    GO  
    ```  
  
     <span data-ttu-id="28caf-192">Para obter mais códigos de exemplo [!INCLUDE[tsql](../../../includes/tsql-md.md)] de criação de um grupo de disponibilidade, veja [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="28caf-192">For additional [!INCLUDE[tsql](../../../includes/tsql-md.md)] code examples of creating an availability group, see [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql).</span></span>  
  
5.  <span data-ttu-id="28caf-193">Na instância de servidor que hospeda a réplica secundária, una a réplica secundária ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="28caf-193">On the server instance that hosts the secondary replica, join the secondary replica to the availability group.</span></span>  
  
     <span data-ttu-id="28caf-194">O exemplo de código a seguir une a réplica secundária de `COMPUTER02` ao grupo de disponibilidade `MyAG` .</span><span class="sxs-lookup"><span data-stu-id="28caf-194">The following code example joins the secondary replica on `COMPUTER02` to the `MyAG` availability group.</span></span>  
  
    ```sql
    -- On the server instance that hosts the secondary replica,   
    -- join the secondary replica to the availability group:  
    ALTER AVAILABILITY GROUP MyAG JOIN;  
    GO  
    ```  
  
6.  <span data-ttu-id="28caf-195">Na instância de servidor que hospeda a réplica secundária, crie os bancos de dados secundários.</span><span class="sxs-lookup"><span data-stu-id="28caf-195">On the server instance that hosts the secondary replica, create the secondary databases.</span></span>  
  
     <span data-ttu-id="28caf-196">O exemplo de código a seguir cria os bancos de dados secundários *MyDb1* e *MyDb2* restaurando backups de banco de dados que usam RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="28caf-196">The following code example creates the *MyDb1* and *MyDb2* secondary databases by restoring database backups using RESTORE WITH NORECOVERY.</span></span>  
  
    ```sql
    -- On the server instance that hosts the secondary replica,   
    -- Restore database backups using the WITH NORECOVERY option:  
    RESTORE DATABASE MyDb1   
        FROM DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
        WITH NORECOVERY  
    GO  
  
    RESTORE DATABASE MyDb2   
        FROM DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
        WITH NORECOVERY  
    GO
    ```  
  
7.  <span data-ttu-id="28caf-197">Na instância de servidor que hospeda a réplica primária, faça backup do log de transações em cada banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="28caf-197">On the server instance that hosts the primary replica, back up the transaction log on each of the primary databases.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="28caf-198">Quando você estiver configurando um grupo de disponibilidade real, é recomendável que, antes de fazer esse backup de log, você suspenda as tarefas de backup de log em seus bancos de dados primários até que tenha unido os bancos de dados secundários correspondentes ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="28caf-198">When you are configuring a real availability group, we recommend that, before taking this log backup, you suspend log backup tasks for your primary databases until you have joined the corresponding secondary databases to the availability group.</span></span>  
  
     <span data-ttu-id="28caf-199">O exemplo de código a seguir cria um backup de log de transações em MyDb1 e MyDb2.</span><span class="sxs-lookup"><span data-stu-id="28caf-199">The following code example creates a transaction log backup on MyDb1 and on MyDb2.</span></span>  
  
    ```sql
    -- On the server instance that hosts the primary replica,   
    -- Backup the transaction log on each primary database:  
    BACKUP LOG MyDb1   
    TO DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
        WITH NOFORMAT  
    GO  
  
    BACKUP LOG MyDb2   
    TO DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
        WITHNOFORMAT  
    GO
    ```  
  
    > [!TIP]  
    >  <span data-ttu-id="28caf-200">Normalmente, um backup de log deve ser feito em cada banco de dados primário e restaurado no banco de dados secundário correspondente (usando WITH NORECOVERY).</span><span class="sxs-lookup"><span data-stu-id="28caf-200">Typically, a log backup must be taken on each primary database and then restored on the corresponding secondary database (using WITH NORECOVERY).</span></span> <span data-ttu-id="28caf-201">Porém, esse backup de log pode ser desnecessário caso o banco de dados tenha acabado de ser criado e nenhum backup tenha sido feito ou caso o modelo de recuperação tenha sido alterado de SIMPLE para FULL.</span><span class="sxs-lookup"><span data-stu-id="28caf-201">However, this log backup might be unnecessary if the database has just been created and no log backup has been taken yet or the recovery model has just been changed from SIMPLE to FULL.</span></span>  
  
8.  <span data-ttu-id="28caf-202">Na instância de servidor que hospeda a réplica secundária, aplique backups de log aos bancos de dados secundários.</span><span class="sxs-lookup"><span data-stu-id="28caf-202">On the server instance that hosts the secondary replica, apply log backups to the secondary databases.</span></span>  
  
     <span data-ttu-id="28caf-203">O exemplo de código a seguir aplica backups aos bancos de dados secundários *MyDb1* e *MyDb2* restaurando backups de banco de dados que usam RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="28caf-203">The following code example applies backups to *MyDb1* and *MyDb2* secondary databases by restoring database backups using RESTORE WITH NORECOVERY.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="28caf-204">Quando você estiver preparando um banco de dados secundário real, precisará aplicar cada backup de log feito desde o backup de banco de dados do qual criou o banco de dados secundário, começando pelo mais antigo e sempre usando RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="28caf-204">When you are preparing a real secondary database, you need to apply every log backup taken since the database backup from which you created the secondary database, starting with the earliest and always using RESTORE WITH NORECOVERY.</span></span> <span data-ttu-id="28caf-205">É claro que, se você restaurar os backups de banco de dados completo e diferencial, precisará apenas aplicar os backups de log feitos após o backup diferencial.</span><span class="sxs-lookup"><span data-stu-id="28caf-205">Of course, if you restore both full and differential database backups, you would only need to apply the log backups taken after the differential backup.</span></span>  
  
    ```sql
    -- Restore the transaction log on each secondary database,  
    -- using the WITH NORECOVERY option:  
    RESTORE LOG MyDb1   
        FROM DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    RESTORE LOG MyDb2   
        FROM DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    ```  
  
9. <span data-ttu-id="28caf-206">Na instância de servidor que hospeda a réplica secundária, una os novos bancos de dados secundários ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="28caf-206">On the server instance that hosts the secondary replica, join the new secondary databases to the availability group.</span></span>  
  
     <span data-ttu-id="28caf-207">O exemplo de código a seguir une o banco de dados secundário *MyDb1* e, em seguida, os bancos de dados secundários *MyDb2* ao grupo de disponibilidade *MyAG* .</span><span class="sxs-lookup"><span data-stu-id="28caf-207">The following code example, joins the *MyDb1* secondary database and then the *MyDb2* secondary databases to the *MyAG* availability group.</span></span>  
  
    ```sql
    -- On the server instance that hosts the secondary replica,   
    -- join each secondary database to the availability group:  
    ALTER DATABASE MyDb1 SET HADR AVAILABILITY GROUP = MyAG;  
    GO  
  
    ALTER DATABASE MyDb2 SET HADR AVAILABILITY GROUP = MyAG;  
    GO
    ```  
  
###  <a name="complete-code-example-for-sample-configuration-procedure"></a><a name="CompleteCodeExample"></a> <span data-ttu-id="28caf-208">Concluir o exemplo de código para procedimento de configuração de exemplo</span><span class="sxs-lookup"><span data-stu-id="28caf-208">Complete Code Example for Sample Configuration Procedure</span></span>  
 <span data-ttu-id="28caf-209">O exemplo a seguir mescla os exemplos de código de todas as etapas do procedimento de configuração de exemplo.</span><span class="sxs-lookup"><span data-stu-id="28caf-209">The following example merges the code examples from all the steps of the sample configuration procedure.</span></span> <span data-ttu-id="28caf-210">A tabela a seguir resumiu os valores de espaço reservado usados neste exemplo de código.</span><span class="sxs-lookup"><span data-stu-id="28caf-210">The following table summarized the placeholder values used in this code example.</span></span> <span data-ttu-id="28caf-211">Para obter mais informações sobre as etapas deste exemplo de código, consulte [Pré-requisitos para usar o procedimento de configuração de exemplo](#PrerequisitesForExample) e [Procedimento de configuração de exemplo](#SampleProcedure), anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="28caf-211">For more information about the steps in this code example, see [Prerequisites for Using the Sample Configuration Procedure](#PrerequisitesForExample) and [Sample Configuration Procedure](#SampleProcedure), earlier in this topic.</span></span>  
  
|<span data-ttu-id="28caf-212">Espaço reservado</span><span class="sxs-lookup"><span data-stu-id="28caf-212">Placeholder</span></span>|<span data-ttu-id="28caf-213">Descrição</span><span class="sxs-lookup"><span data-stu-id="28caf-213">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="28caf-214">\\\\*FILESERVER*\\*SQLbackups*</span><span class="sxs-lookup"><span data-stu-id="28caf-214">\\\\*FILESERVER*\\*SQLbackups*</span></span>|<span data-ttu-id="28caf-215">Compartilhamento de backup ficcional.</span><span class="sxs-lookup"><span data-stu-id="28caf-215">Fictional backup share.</span></span>|  
|<span data-ttu-id="28caf-216">\\\\*FILESERVER*\\*SQLbackups\MyDb1.bak*</span><span class="sxs-lookup"><span data-stu-id="28caf-216">\\\\*FILESERVER*\\*SQLbackups\MyDb1.bak*</span></span>|<span data-ttu-id="28caf-217">Arquivo de backup de MyDb1.</span><span class="sxs-lookup"><span data-stu-id="28caf-217">Backup file for MyDb1.</span></span>|  
|<span data-ttu-id="28caf-218">\\\\*FILESERVER*\\*SQLbackups\MyDb2.bak*</span><span class="sxs-lookup"><span data-stu-id="28caf-218">\\\\*FILESERVER*\\*SQLbackups\MyDb2.bak*</span></span>|<span data-ttu-id="28caf-219">Arquivo de backup de MyDb2.</span><span class="sxs-lookup"><span data-stu-id="28caf-219">Backup file for MyDb2.</span></span>|  
|<span data-ttu-id="28caf-220">*7022*</span><span class="sxs-lookup"><span data-stu-id="28caf-220">*7022*</span></span>|<span data-ttu-id="28caf-221">Número de porta atribuído a cada ponto de extremidade de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="28caf-221">Port number assigned to each database mirroring endpoint.</span></span>|  
|<span data-ttu-id="28caf-222">*COMPUTER01\AgHostInstance*</span><span class="sxs-lookup"><span data-stu-id="28caf-222">*COMPUTER01\AgHostInstance*</span></span>|<span data-ttu-id="28caf-223">Instância de servidor que hospeda a réplica primária inicial.</span><span class="sxs-lookup"><span data-stu-id="28caf-223">Server instance that hosts the initial primary replica.</span></span>|  
|<span data-ttu-id="28caf-224">*COMPUTER02*</span><span class="sxs-lookup"><span data-stu-id="28caf-224">*COMPUTER02*</span></span>|<span data-ttu-id="28caf-225">Instância de servidor que hospeda a réplica secundária inicial.</span><span class="sxs-lookup"><span data-stu-id="28caf-225">Server instance that hosts the initial secondary replica.</span></span> <span data-ttu-id="28caf-226">Essa é a instância de servidor padrão em `COMPUTER02`.</span><span class="sxs-lookup"><span data-stu-id="28caf-226">This is the default server instance on `COMPUTER02`.</span></span>|  
|<span data-ttu-id="28caf-227">*dbm_endpoint*</span><span class="sxs-lookup"><span data-stu-id="28caf-227">*dbm_endpoint*</span></span>|<span data-ttu-id="28caf-228">Nome especificado para cada ponto de extremidade de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="28caf-228">Name specified for each database mirroring endpoint.</span></span>|  
|<span data-ttu-id="28caf-229">*MyAG*</span><span class="sxs-lookup"><span data-stu-id="28caf-229">*MyAG*</span></span>|<span data-ttu-id="28caf-230">Nome do grupo de disponibilidade de exemplo.</span><span class="sxs-lookup"><span data-stu-id="28caf-230">Name of sample availability group.</span></span>|  
|<span data-ttu-id="28caf-231">*MyDb1*</span><span class="sxs-lookup"><span data-stu-id="28caf-231">*MyDb1*</span></span>|<span data-ttu-id="28caf-232">Nome do primeiro banco de dados de exemplo.</span><span class="sxs-lookup"><span data-stu-id="28caf-232">Name of first sample database.</span></span>|  
|<span data-ttu-id="28caf-233">*MyDb2*</span><span class="sxs-lookup"><span data-stu-id="28caf-233">*MyDb2*</span></span>|<span data-ttu-id="28caf-234">Nome do segundo banco de dados de exemplo.</span><span class="sxs-lookup"><span data-stu-id="28caf-234">Name of second sample database.</span></span>|  
|<span data-ttu-id="28caf-235">*DOMAIN1\user1*</span><span class="sxs-lookup"><span data-stu-id="28caf-235">*DOMAIN1\user1*</span></span>|<span data-ttu-id="28caf-236">Conta de serviço da instância de servidor que deve hospedar a réplica primária inicial.</span><span class="sxs-lookup"><span data-stu-id="28caf-236">Service account of the server instance that is to host the initial primary replica.</span></span>|  
|<span data-ttu-id="28caf-237">*DOMAIN2\user2*</span><span class="sxs-lookup"><span data-stu-id="28caf-237">*DOMAIN2\user2*</span></span>|<span data-ttu-id="28caf-238">Conta de serviço da instância de servidor que deve hospedar a réplica secundária inicial.</span><span class="sxs-lookup"><span data-stu-id="28caf-238">Service account of the server instance that is to host the initial secondary replica.</span></span>|  
|<span data-ttu-id="28caf-239">TCP://*COMPUTER01.Adventure-Works.com*:*7022*</span><span class="sxs-lookup"><span data-stu-id="28caf-239">TCP://*COMPUTER01.Adventure-Works.com*:*7022*</span></span>|<span data-ttu-id="28caf-240">URL de ponto de extremidade da instância AgHostInstance do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] em COMPUTER01.</span><span class="sxs-lookup"><span data-stu-id="28caf-240">Endpoint URL of the AgHostInstance instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on COMPUTER01.</span></span>|  
|<span data-ttu-id="28caf-241">TCP://*COMPUTER02.Adventure-Works.com*:*5022*</span><span class="sxs-lookup"><span data-stu-id="28caf-241">TCP://*COMPUTER02.Adventure-Works.com*:*5022*</span></span>|<span data-ttu-id="28caf-242">URL de ponto de extremidade da instância padrão do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] em COMPUTER02.</span><span class="sxs-lookup"><span data-stu-id="28caf-242">Endpoint URL of the default instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on COMPUTER02.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="28caf-243">Para obter mais códigos de exemplo [!INCLUDE[tsql](../../../includes/tsql-md.md)] de criação de um grupo de disponibilidade, veja [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="28caf-243">For additional [!INCLUDE[tsql](../../../includes/tsql-md.md)] code examples of creating an availability group, see [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql).</span></span>  
  
```sql
-- on the server instance that will host the primary replica,   
-- create sample databases:  
CREATE DATABASE MyDb1;  
GO  
ALTER DATABASE MyDb1 SET RECOVERY FULL;  
GO  
  
CREATE DATABASE MyDb2;  
GO  
ALTER DATABASE MyDb2 SET RECOVERY FULL;  
GO  
  
-- Backup sample databases:  
BACKUP DATABASE MyDb1   
TO DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
    WITH FORMAT  
GO  
  
BACKUP DATABASE MyDb2   
TO DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
    WITH FORMAT  
GO  
  
-- Create the endpoint on the server instance that will host the primary replica:  
CREATE ENDPOINT dbm_endpoint  
    STATE=STARTED   
    AS TCP (LISTENER_PORT=7022)   
    FOR DATABASE_MIRRORING (ROLE=ALL)  
GO  
  
-- Create the endpoint on the server instance that will host the secondary replica:   
CREATE ENDPOINT dbm_endpoint  
    STATE=STARTED   
    AS TCP (LISTENER_PORT=7022)   
    FOR DATABASE_MIRRORING (ROLE=ALL)  
GO  
  
-- If both service accounts run under the same domain account, skip this step. Otherwise,   
-- On the server instance that will host the primary replica,   
-- create a login for the service account   
-- of the server instance that will host the secondary replica, DOMAIN2\user2,   
-- and grant this login connect permissions on the endpoint:  
USE master;  
GO  
CREATE LOGIN [DOMAIN2\user2] FROM WINDOWS;  
GO  
GRANT CONNECT ON ENDPOINT::dbm_endpoint   
   TO [DOMAIN2\user2];  
GO  
  
-- If both service accounts run under the same domain account, skip this step. Otherwise,   
-- On the server instance that will host the secondary replica,  
-- create a login for the service account   
-- of the server instance that will host the primary replica, DOMAIN1\user1,   
-- and grant this login connect permissions on the endpoint:  
USE master;  
GO  
  
CREATE LOGIN [DOMAIN1\user1] FROM WINDOWS;  
GO  
GRANT CONNECT ON ENDPOINT::dbm_endpoint   
   TO [DOMAIN1\user1];  
GO  
  
-- On the server instance that will host the primary replica,   
-- create the availability group, MyAG:  
CREATE AVAILABILITY GROUP MyAG   
   FOR   
      DATABASE MyDB1, MyDB2   
   REPLICA ON   
      'COMPUTER01\AgHostInstance' WITH   
         (  
         ENDPOINT_URL = 'TCP://COMPUTER01.Adventure-Works.com:7022',  
         AVAILABILITY_MODE = SYNCHRONOUS_COMMIT,  
         FAILOVER_MODE = AUTOMATIC  
         ),  
      'COMPUTER02' WITH   
         (  
         ENDPOINT_URL = 'TCP://COMPUTER02.Adventure-Works.com:7022',  
         AVAILABILITY_MODE = SYNCHRONOUS_COMMIT,  
         FAILOVER_MODE = AUTOMATIC  
         );   
GO  
  
-- On the server instance that hosts the secondary replica,   
-- join the secondary replica to the availability group:  
ALTER AVAILABILITY GROUP MyAG JOIN;  
GO  
  
-- Restore database backups onto this server instance, using RESTORE WITH NORECOVERY:  
RESTORE DATABASE MyDb1   
    FROM DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
    WITH NORECOVERY  
GO  
  
RESTORE DATABASE MyDb2   
    FROM DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
    WITH NORECOVERY  
GO  
  
-- Back up the transaction log on each primary database:  
BACKUP LOG MyDb1   
TO DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
    WITH NOFORMAT  
GO  
  
BACKUP LOG MyDb2   
TO DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
    WITHNOFORMAT  
GO  
  
-- Restore the transaction log on each secondary database,  
-- using the WITH NORECOVERY option:  
RESTORE LOG MyDb1   
    FROM DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
    WITH FILE=1, NORECOVERY  
GO  
RESTORE LOG MyDb2   
    FROM DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
    WITH FILE=1, NORECOVERY  
GO  
  
-- On the server instance that hosts the secondary replica,   
-- join each secondary database to the availability group:  
ALTER DATABASE MyDb1 SET HADR AVAILABILITY GROUP = MyAG;  
GO  
  
ALTER DATABASE MyDb2 SET HADR AVAILABILITY GROUP = MyAG;  
GO
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="28caf-244">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="28caf-244">Related Tasks</span></span>  
 <span data-ttu-id="28caf-245">**Para configurar um grupo de disponibilidade e propriedades de réplica**</span><span class="sxs-lookup"><span data-stu-id="28caf-245">**To configure availability group and replica properties**</span></span>  
  
-   [<span data-ttu-id="28caf-246">Alterar o modo de disponibilidade de uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="28caf-246">Change the Availability Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-availability-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="28caf-247">Alterar o modo de failover de uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="28caf-247">Change the Failover Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-failover-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="28caf-248">Criar ou configurar um ouvinte do grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="28caf-248">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="28caf-249">Configurar a política de failover flexível para controlar condições de failover automático (grupos de disponibilidade AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="28caf-249">Configure the Flexible Failover Policy to Control Conditions for Automatic Failover (AlwaysOn Availability Groups)</span></span>](configure-flexible-automatic-failover-policy.md)  
  
-   [<span data-ttu-id="28caf-250">Especificar a URL do ponto de extremidade ao adicionar ou modificar uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="28caf-250">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
-   [<span data-ttu-id="28caf-251">Configurar backup em réplicas de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="28caf-251">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
-   [<span data-ttu-id="28caf-252">Configurar o acesso somente leitura em uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="28caf-252">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="28caf-253">Configurar o roteamento somente leitura para um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="28caf-253">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="28caf-254">Alterar o período de tempo limite da sessão de uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="28caf-254">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
 <span data-ttu-id="28caf-255">**Para concluir a configuração do grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="28caf-255">**To complete availability group configuration**</span></span>  
  
-   [<span data-ttu-id="28caf-256">Unir uma réplica secundária a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="28caf-256">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="28caf-257">Preparar um banco de dados secundário manualmente para um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="28caf-257">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="28caf-258">Unir um banco de dados secundário a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="28caf-258">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="28caf-259">Criar ou configurar um ouvinte do grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="28caf-259">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
 <span data-ttu-id="28caf-260">**Maneiras alternativas de criar um grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="28caf-260">**Alternative ways to create an availability group**</span></span>  
  
-   [<span data-ttu-id="28caf-261">Usar o Assistente de Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="28caf-261">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="28caf-262">Usar a caixa de diálogo Novo Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="28caf-262">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="28caf-263">Criar um grupo de disponibilidade &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="28caf-263">Create an Availability Group &#40;SQL Server PowerShell&#41;</span></span>](../../../powershell/sql-server-powershell.md)  
  
 <span data-ttu-id="28caf-264">**Para habilitar Grupos de Disponibilidade AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="28caf-264">**To enable AlwaysOn Availability Groups**</span></span>  
  
-   [<span data-ttu-id="28caf-265">Habilitar e desabilitar grupos de disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="28caf-265">Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](enable-and-disable-always-on-availability-groups-sql-server.md)  
  
 <span data-ttu-id="28caf-266">**Para configurar um ponto de extremidade de espelhamento de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="28caf-266">**To configure a database mirroring endpoint**</span></span>  
  
-   [<span data-ttu-id="28caf-267">Criar um ponto de extremidade de espelhamento de banco de dados para Grupos de Disponibilidade AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="28caf-267">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="28caf-268">Criar um ponto de extremidade de espelhamento de banco de dados para a Autenticação do Windows &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="28caf-268">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="28caf-269">Usar certificados para um ponto de extremidade de espelhamento de banco de dados &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="28caf-269">Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/use-certificates-for-a-database-mirroring-endpoint-transact-sql.md)  
  
-   [<span data-ttu-id="28caf-270">Especificar a URL do ponto de extremidade ao adicionar ou modificar uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="28caf-270">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
 <span data-ttu-id="28caf-271">**Para solucionar problemas de configuração de grupos de disponibilidade AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="28caf-271">**To troubleshoot AlwaysOn Availability Groups configuration**</span></span>  
  
-   [<span data-ttu-id="28caf-272">Solução de problemas de configuração de Grupos de Disponibilidade AlwaysOn (SQL Server) excluída</span><span class="sxs-lookup"><span data-stu-id="28caf-272">Troubleshoot AlwaysOn Availability Groups Configuration (SQL Server)deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
  
-   [<span data-ttu-id="28caf-273">Solucionar problemas de uma operação de adição de arquivo com falha &#40;Grupos de Disponibilidade AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="28caf-273">Troubleshoot a Failed Add-File Operation &#40;AlwaysOn Availability Groups&#41;</span></span>](troubleshoot-a-failed-add-file-operation-always-on-availability-groups.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="28caf-274">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="28caf-274">Related Content</span></span>  
  
-   <span data-ttu-id="28caf-275">**Blogs:**</span><span class="sxs-lookup"><span data-stu-id="28caf-275">**Blogs:**</span></span>  
  
     [<span data-ttu-id="28caf-276">Série de aprendizado do AlwaysON - HADRON: uso de trabalho do pool para bancos de dados habilitados do HADRON</span><span class="sxs-lookup"><span data-stu-id="28caf-276">AlwaysON - HADRON Learning Series: Worker Pool Usage for HADRON Enabled Databases</span></span>](https://blogs.msdn.com/b/psssql/archive/2012/05/17/alwayson-hadron-learning-series-worker-pool-usage-for-hadron-enabled-databases.aspx)  
  
     [<span data-ttu-id="28caf-277">Blogs da equipe do SQL Server AlwaysOn: o blog oficial da equipe do SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="28caf-277">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="28caf-278">Blogs dos engenheiros do CSS SQL Server</span><span class="sxs-lookup"><span data-stu-id="28caf-278">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="28caf-279">**Vídeos:**</span><span class="sxs-lookup"><span data-stu-id="28caf-279">**Videos:**</span></span>  
  
     [<span data-ttu-id="28caf-280">Microsoft SQL Server codinome "Denali" Série AlwaysOn, Parte 1: Introduzindo a próxima geração de solução de alta disponibilidade</span><span class="sxs-lookup"><span data-stu-id="28caf-280">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 1: Introducing the Next Generation High Availability Solution</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI302)  
  
     [<span data-ttu-id="28caf-281">Microsoft SQL Server codinome "Denali" Série AlwaysOn, Parte 2: Criando uma solução de disponibilidade de missão crítica usando AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="28caf-281">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 2: Building a Mission-Critical High Availability Solution Using AlwaysOn</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI404)  
  
-   <span data-ttu-id="28caf-282">**Whitepapers:**</span><span class="sxs-lookup"><span data-stu-id="28caf-282">**Whitepapers:**</span></span>  
  
     [<span data-ttu-id="28caf-283">Guia de soluções AlwaysOn do Microsoft SQL Server para alta disponibilidade e recuperação de desastre</span><span class="sxs-lookup"><span data-stu-id="28caf-283">Microsoft SQL Server AlwaysOn Solutions Guide for High Availability and Disaster Recovery</span></span>](https://go.microsoft.com/fwlink/?LinkId=227600)  
  
     [<span data-ttu-id="28caf-284">White papers da Microsoft para SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="28caf-284">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="28caf-285">White papers da equipe de consultoria do cliente do SQL Server</span><span class="sxs-lookup"><span data-stu-id="28caf-285">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="28caf-286">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="28caf-286">See Also</span></span>  
 <span data-ttu-id="28caf-287">[O ponto de extremidade de espelhamento de banco de dados &#40;SQL Server&#41;](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="28caf-287">[The Database Mirroring Endpoint &#40;SQL Server&#41;](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="28caf-288">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="28caf-288">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="28caf-289">Ouvintes do grupo de disponibilidade, conectividade de cliente e failover de aplicativo &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="28caf-289">Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;</span></span>](../../listeners-client-connectivity-application-failover.md)   
