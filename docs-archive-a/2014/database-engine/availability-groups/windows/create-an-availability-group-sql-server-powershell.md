---
title: Criar um grupo de disponibilidade (SQL Server PowerShell) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], creating
ms.assetid: bc69a7df-20fa-41e1-9301-11317c5270d2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3af9bf896b954e6849c0d491f9ed267655369ccb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686375"
---
# <a name="create-an-availability-group-sql-server-powershell"></a><span data-ttu-id="b9f71-102">Criar um Grupo de disponibilidade (SQL Server PowerShell)</span><span class="sxs-lookup"><span data-stu-id="b9f71-102">Create an Availability Group (SQL Server PowerShell)</span></span>
  <span data-ttu-id="b9f71-103">Esse tópico descreve como usar os cmdlets do PowerShell para criar e configurar um grupo de disponibilidade AlwaysOn usando o PowerShell no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9f71-103">This topic describes how to use PowerShell cmdlets to create and configure an AlwaysOn availability group by using PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="b9f71-104">Um *grupo de disponibilidade* define um conjunto de bancos de dados de usuários que realizará o failover como uma única unidade e um conjunto de parceiros de failover, conhecido como *réplicas de disponibilidade*, que oferece suporte a failover.</span><span class="sxs-lookup"><span data-stu-id="b9f71-104">An *availability group* defines a set of user databases that will fail over as a single unit and a set of failover partners, known as *availability replicas*, which support failover.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b9f71-105">Para obter uma introdução aos grupos de disponibilidade, consulte [Visão geral dos grupos de disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b9f71-105">For an introduction to availability groups, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span>  

> [!NOTE]  
>  <span data-ttu-id="b9f71-106">Como alternativa para o uso dos cmdlets do PowerShell, você pode usar o assistente para Criar Grupo de Disponibilidade ou o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9f71-106">As an alternative to using PowerShell cmdlets, you can use the Create Availability Group wizard or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b9f71-107">Para obter mais informações, veja [Usar a caixa de diálogo Novo Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;](use-the-new-availability-group-dialog-box-sql-server-management-studio.md) ou [Criar um grupo de disponibilidade &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="b9f71-107">For more information, see [Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;](use-the-new-availability-group-dialog-box-sql-server-management-studio.md) or [Create an Availability Group &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b9f71-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="b9f71-108">Before You Begin</span></span>  
 <span data-ttu-id="b9f71-109">É recomendável que você leia esta seção antes de tentar criar seu primeiro grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="b9f71-109">We strongly recommend that you read this section before attempting to create your first availability group.</span></span>  
  
###  <a name="prerequisites-restrictions-and-recommendations"></a><a name="PrerequisitesRestrictions"></a> <span data-ttu-id="b9f71-110">Pré-requisitos, restrições e recomendações</span><span class="sxs-lookup"><span data-stu-id="b9f71-110">Prerequisites, Restrictions, and Recommendations</span></span>  
  
-   <span data-ttu-id="b9f71-111">Antes de criar um grupo de disponibilidade, verifique se cada instância de host do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] reside em um nó diferente do WSFC (Windows Server Failover Clustering) de um único cluster de failover do WSFC.</span><span class="sxs-lookup"><span data-stu-id="b9f71-111">Before creating an availability group, verify that the host instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] each resides on a different Windows Server Failover Clustering (WSFC) node of a single WSFC failover cluster.</span></span> <span data-ttu-id="b9f71-112">Verifique também se suas instâncias de servidor atendem aos outros pré-requisitos de instância de servidor, se todos os outros requisitos do [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] são atendidos e se você está ciente das recomendações.</span><span class="sxs-lookup"><span data-stu-id="b9f71-112">Also, verify that your server instances met the other server-instance prerequisites and that all of the other [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] requirements are meet and that you are aware of the recommendations.</span></span> <span data-ttu-id="b9f71-113">Para obter mais informações, é altamente recomendável que você leia [Pré-requisitos, restrições e recomendações para grupos de disponibilidade AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="b9f71-113">For more information, we strongly recommend that you read [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b9f71-114">Segurança</span><span class="sxs-lookup"><span data-stu-id="b9f71-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b9f71-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="b9f71-115">Permissions</span></span>  
 <span data-ttu-id="b9f71-116">Requer a associação na função de servidor fixa **sysadmin** e a permissão de servidor CREATE AVAILABILITY GROUP, a permissão ALTER ANY AVAILABILITY GROUP ou a permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="b9f71-116">Requires membership in the **sysadmin** fixed server role and either CREATE AVAILABILITY GROUP server permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
###  <a name="summary-of-tasks-and-corresponding-powershell-cmdlets"></a><a name="SummaryPSStatements"></a><span data-ttu-id="b9f71-117">Resumo de tarefas e cmdlets do PowerShell correspondentes</span><span class="sxs-lookup"><span data-stu-id="b9f71-117">Summary of Tasks and Corresponding PowerShell Cmdlets</span></span>  
 <span data-ttu-id="b9f71-118">A tabela a seguir lista as tarefas básicas envolvidas na configuração de um grupo de disponibilidade e indica as tarefas com suporte nos cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9f71-118">The following table lists the basic tasks involved in configuring an availability group and indicates those that are supported by PowerShell cmdlets.</span></span> <span data-ttu-id="b9f71-119">As tarefas [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] devem ser executadas na sequência em que são apresentadas na tabela.</span><span class="sxs-lookup"><span data-stu-id="b9f71-119">The [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] tasks must be performed in the sequence in which they are presented in the table.</span></span>  
  
|<span data-ttu-id="b9f71-120">Tarefa</span><span class="sxs-lookup"><span data-stu-id="b9f71-120">Task</span></span>|<span data-ttu-id="b9f71-121">Cmdlets do PowerShell (se disponíveis) ou instrução Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b9f71-121">PowerShell Cmdlets (if Available) or Transact-SQL Statement</span></span>|<span data-ttu-id="b9f71-122">Onde executar a tarefa**<sup>\*</sup>**</span><span class="sxs-lookup"><span data-stu-id="b9f71-122">Where to Perform Task**<sup>\*</sup>**</span></span>|  
|----------|--------------------------------------------------------------------|-------------------------------------------|  
|<span data-ttu-id="b9f71-123">Criar ponto de extremidade de espelhamento de banco de dados (uma vez por instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="b9f71-123">Create database mirroring endpoint (once per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance)</span></span>|`New-SqlHadrEndPoint`|<span data-ttu-id="b9f71-124">Executar em cada instância de servidor que não tem ponto de extremidade de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b9f71-124">Execute on each server instance that lacks database mirroring endpoint.</span></span><br /><br /> <span data-ttu-id="b9f71-125">Observação: para alterar um ponto de extremidade de espelhamento de banco de dados existente, use `Set-SqlHadrEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="b9f71-125">Note: To alter an existing database mirroring endpoint, use `Set-SqlHadrEndpoint`.</span></span>|  
|<span data-ttu-id="b9f71-126">Criar grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="b9f71-126">Create availability group</span></span>|<span data-ttu-id="b9f71-127">Primeiro, use o cmdlet `New-SqlAvailabilityReplica` com o parâmetro `-AsTemplate` para criar um objeto da réplica de disponibilidade na memória para cada uma das duas réplicas de disponibilidade que você pretende incluir no grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="b9f71-127">First, use the `New-SqlAvailabilityReplica` cmdlet with the `-AsTemplate` parameter to create an in-memory availability-replica object for each of the two availability replicas that you plan to include in the availability group.</span></span><br /><br /> <span data-ttu-id="b9f71-128">Em seguida, crie o grupo de disponibilidade usando o cmdlet `New-SqlAvailabilityGroup` e referenciando os objetos da réplica de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="b9f71-128">Then, create the availability group by using the `New-SqlAvailabilityGroup` cmdlet and referencing your availability-replica objects.</span></span>|<span data-ttu-id="b9f71-129">Execute na instância de servidor que deve hospedar a réplica primária inicial.</span><span class="sxs-lookup"><span data-stu-id="b9f71-129">Execute on the server instance that is to host the initial primary replica.</span></span>|  
|<span data-ttu-id="b9f71-130">Unir a réplica secundária ao grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="b9f71-130">Join secondary replica to availability group</span></span>|`Join-SqlAvailabilityGroup`|<span data-ttu-id="b9f71-131">Execute em cada instância de servidor que hospeda uma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="b9f71-131">Execute on each server instance that is hosts a secondary replica.</span></span>|  
|<span data-ttu-id="b9f71-132">Preparar os banco de dados secundários</span><span class="sxs-lookup"><span data-stu-id="b9f71-132">Prepare the secondary database</span></span>|<span data-ttu-id="b9f71-133">`Backup-SqlDatabase` e `Restore-SqlDatabase`</span><span class="sxs-lookup"><span data-stu-id="b9f71-133">`Backup-SqlDatabase` and `Restore-SqlDatabase`</span></span>|<span data-ttu-id="b9f71-134">Crie backups na instância de servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="b9f71-134">Create backups on the server instance that hosts the primary replica.</span></span><br /><br /> <span data-ttu-id="b9f71-135">Restaure backups em cada instância de servidor que hospeda uma réplica secundária, usando o parâmetro de restauração `NoRecovery`.</span><span class="sxs-lookup"><span data-stu-id="b9f71-135">Restore backups on each server instance that hosts a secondary replica, using the `NoRecovery` restore parameter.</span></span> <span data-ttu-id="b9f71-136">Se os caminhos dos arquivos forem diferentes nos computadores que hospedam a réplica primária e a réplica secundária de destino, use também o parâmetro de restauração `RelocateFile`.</span><span class="sxs-lookup"><span data-stu-id="b9f71-136">If the file paths differ between the computers that host the primary replica and the target secondary replica, also use the `RelocateFile` restore parameter.</span></span>|  
|<span data-ttu-id="b9f71-137">Iniciar a sincronização de dados unindo cada banco de dados secundário ao grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="b9f71-137">Start data synchronization by joining each secondary database to availability group</span></span>|`Add-SqlAvailabilityDatabase`|<span data-ttu-id="b9f71-138">Execute em cada instância de servidor que hospeda uma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="b9f71-138">Execute on each server instance that hosts a secondary replica.</span></span>|  
  
 <span data-ttu-id="b9f71-139">**<sup>\*</sup>** Para executar uma determinada tarefa, altere o diretório ( `cd` ) para a instância ou instâncias de servidor indicadas.</span><span class="sxs-lookup"><span data-stu-id="b9f71-139">**<sup>\*</sup>**  To perform a given task, change directory (`cd`) to the indicated server instance or instances.</span></span>  
  
###  <a name="to-set-up-and-use-the-sql-server-powershell-provider"></a><a name="PsProviderLinks"></a><span data-ttu-id="b9f71-140">Para configurar e usar o provedor de SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9f71-140">To Set Up and Use the SQL Server PowerShell Provider</span></span>  
  
-   [<span data-ttu-id="b9f71-141">Provedor do SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9f71-141">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
-   [<span data-ttu-id="b9f71-142">Get Help SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9f71-142">Get Help SQL Server PowerShell</span></span>](../../../powershell/sql-server-powershell.md)  
  
##  <a name="using-powershell-to-create-and-configure-an-availability-group"></a><a name="PowerShellProcedure"></a><span data-ttu-id="b9f71-143">Usando o PowerShell para criar e configurar um grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="b9f71-143">Using PowerShell to Create and Configure an Availability Group</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b9f71-144">Para exibir a sintaxe e um exemplo de um cmdlet, use o cmdlet `Get-Help` no ambiente do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9f71-144">To view the syntax and an example of a given cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="b9f71-145">Para obter mais informações, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="b9f71-145">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
1.  <span data-ttu-id="b9f71-146">Altere o diretório (`cd`) para a instância do servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="b9f71-146">Change directory (`cd`) to the server instance that is to host the primary replica.</span></span>  
  
2.  <span data-ttu-id="b9f71-147">Crie um objeto da réplica de disponibilidade na memória para a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="b9f71-147">Create an in-memory availability-replica object for the primary replica.</span></span>  
  
3.  <span data-ttu-id="b9f71-148">Crie um objeto da réplica de disponibilidade na memória para cada réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="b9f71-148">Create an in-memory availability-replica object for each of the secondary replicas.</span></span>  
  
4.  <span data-ttu-id="b9f71-149">Crie o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="b9f71-149">Create the availability group.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b9f71-150">O tamanho máximo de um nome de grupo de disponibilidade é 128 caracteres.</span><span class="sxs-lookup"><span data-stu-id="b9f71-150">The maximum length for an availability group name is 128 characters.</span></span>  
  
5.  <span data-ttu-id="b9f71-151">Una a nova réplica secundária ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="b9f71-151">Join the new secondary replica to the availability group.</span></span> <span data-ttu-id="b9f71-152">Para obter mais informações, veja [Unir uma réplica secundária a um grupo de disponibilidade &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b9f71-152">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
6.  <span data-ttu-id="b9f71-153">Para cada banco de dados do grupo de disponibilidade, crie um banco de dados secundário restaurando backups recentes do banco de dados primário, usando RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="b9f71-153">For each database in the availability group, create a secondary database by restoring recent backups of the primary database, using RESTORE WITH NORECOVERY.</span></span>  
  
7.  <span data-ttu-id="b9f71-154">Una cada novo banco de dados secundário ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="b9f71-154">Join every new secondary database to the availability group.</span></span> <span data-ttu-id="b9f71-155">Para obter mais informações, veja [Unir uma réplica secundária a um grupo de disponibilidade &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b9f71-155">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
8.  <span data-ttu-id="b9f71-156">Se desejar, use o comando `dir` do Windows para verificar o conteúdo do novo grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="b9f71-156">Optionally, use the Windows `dir` command to verify the contents of the new availability group.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b9f71-157">Se as contas de serviço [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] das instâncias do servidor forem executadas em diferentes contas de usuário de domínio, em cada instância do servidor, crie um logon para a outra instância do servidor e conceda a permissão CONNECT a esse logon para o ponto de extremidade de espelhamento do banco de dados local.</span><span class="sxs-lookup"><span data-stu-id="b9f71-157">If the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service accounts of the server instances run under different domain user accounts, on each server instance, create a login for the other server instance and grant this login CONNECT permission to the local database mirroring endpoint.</span></span>  
  
##  <a name="example-using-powershell-to-create-an-availability-group"></a><a name="ExampleConfigureGroup"></a><span data-ttu-id="b9f71-158">Exemplo: usando o PowerShell para criar um grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="b9f71-158">Example: Using PowerShell to Create an Availability Group</span></span>  
 <span data-ttu-id="b9f71-159">O exemplo doe PowerShell a seguir cria e configura um grupo de disponibilidade simples denominado `MyAG` com duas réplicas de disponibilidade e um banco de dados de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="b9f71-159">The following PowerShell example creates and configures a simple availability group named `MyAG` with two availability replicas and one availability database.</span></span> <span data-ttu-id="b9f71-160">O exemplo:</span><span class="sxs-lookup"><span data-stu-id="b9f71-160">The example:</span></span>  
  
1.  <span data-ttu-id="b9f71-161">Faz backup do `MyDatabase` e de seu log de transações.</span><span class="sxs-lookup"><span data-stu-id="b9f71-161">Backs up `MyDatabase` and its transaction log.</span></span>  
  
2.  <span data-ttu-id="b9f71-162">Restaura o `MyDatabase` e seu log de transação, usando a opção `-NoRecovery`.</span><span class="sxs-lookup"><span data-stu-id="b9f71-162">Restores `MyDatabase` and its transaction log, using the `-NoRecovery` option.</span></span>  
  
3.  <span data-ttu-id="b9f71-163">Cria uma representação na memória da réplica primária, que será hospedada pela instância local do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (denominada `PrimaryComputer\Instance`).</span><span class="sxs-lookup"><span data-stu-id="b9f71-163">Creates an in-memory representation of the primary replica, which will be hosted by the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (named `PrimaryComputer\Instance`).</span></span>  
  
4.  <span data-ttu-id="b9f71-164">Cria uma representação na memória da réplica secundária, que será hospedada por uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (denominada `SecondaryComputer\Instance`).</span><span class="sxs-lookup"><span data-stu-id="b9f71-164">Creates an in-memory representation of the secondary replica, which will be hosted by an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (named `SecondaryComputer\Instance`).</span></span>  
  
5.  <span data-ttu-id="b9f71-165">Cria um grupo de disponibilidade denominado `MyAG`.</span><span class="sxs-lookup"><span data-stu-id="b9f71-165">Creates an availability group named `MyAG`.</span></span>  
  
6.  <span data-ttu-id="b9f71-166">Une a réplica secundária ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="b9f71-166">Joins the secondary replica to the availability group.</span></span>  
  
7.  <span data-ttu-id="b9f71-167">Une o banco de dados secundário ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="b9f71-167">Joins the secondary database to the availability group.</span></span>  
  
```powershell
# Backup my database and its log on the primary  
Backup-SqlDatabase `  
    -Database "MyDatabase" `  
    -BackupFile "\\share\backups\MyDatabase.bak" `  
    -ServerInstance "PrimaryComputer\Instance"  
  
Backup-SqlDatabase `  
    -Database "MyDatabase" `  
    -BackupFile "\\share\backups\MyDatabase.log" `  
    -ServerInstance "PrimaryComputer\Instance" `  
    -BackupAction Log   
  
# Restore the database and log on the secondary (using NO RECOVERY)  
Restore-SqlDatabase `  
    -Database "MyDatabase" `  
    -BackupFile "\\share\backups\MyDatabase.bak" `  
    -ServerInstance "SecondaryComputer\Instance" `  
    -NoRecovery  
  
Restore-SqlDatabase `  
    -Database "MyDatabase" `  
    -BackupFile "\\share\backups\MyDatabase.log" `  
    -ServerInstance "SecondaryComputer\Instance" `  
    -RestoreAction Log `  
    -NoRecovery  
  
# Create an in-memory representation of the primary replica.  
$primaryReplica = New-SqlAvailabilityReplica `  
    -Name "PrimaryComputer\Instance" `  
    -EndpointURL "TCP://PrimaryComputer.domain.com:5022" `  
    -AvailabilityMode "SynchronousCommit" `  
    -FailoverMode "Automatic" `  
    -Version 12 `  
    -AsTemplate  
  
# Create an in-memory representation of the secondary replica.  
$secondaryReplica = New-SqlAvailabilityReplica `  
    -Name "SecondaryComputer\Instance" `  
    -EndpointURL "TCP://SecondaryComputer.domain.com:5022" `  
    -AvailabilityMode "SynchronousCommit" `  
    -FailoverMode "Automatic" `  
    -Version 12 `  
    -AsTemplate  
  
# Create the availability group  
New-SqlAvailabilityGroup `  
    -Name "MyAG" `  
    -Path "SQLSERVER:\SQL\PrimaryComputer\Instance" `  
    -AvailabilityReplica @($primaryReplica,$secondaryReplica) `  
    -Database "MyDatabase"  
  
# Join the secondary replica to the availability group.  
Join-SqlAvailabilityGroup -Path "SQLSERVER:\SQL\SecondaryComputer\Instance" -Name "MyAG"  
  
# Join the secondary database to the availability group.  
Add-SqlAvailabilityDatabase -Path "SQLSERVER:\SQL\SecondaryComputer\Instance\AvailabilityGroups\MyAG" -Database "MyDatabase"  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="b9f71-168">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="b9f71-168">Related Tasks</span></span>  
 <span data-ttu-id="b9f71-169">**Para configurar uma instância de servidor para grupos de disponibilidade AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="b9f71-169">**To configure a server instance for AlwaysOn Availability Groups**</span></span>  
  
-   [<span data-ttu-id="b9f71-170">Habilitar e desabilitar grupos de disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b9f71-170">Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](enable-and-disable-always-on-availability-groups-sql-server.md)  
  
-   [<span data-ttu-id="b9f71-171">Criar um ponto de extremidade de espelhamento de banco de dados para Grupos de Disponibilidade AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="b9f71-171">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
 <span data-ttu-id="b9f71-172">**Para configurar um grupo de disponibilidade e propriedades de réplica**</span><span class="sxs-lookup"><span data-stu-id="b9f71-172">**To configure availability group and replica properties**</span></span>  
  
-   [<span data-ttu-id="b9f71-173">Alterar o modo de disponibilidade de uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b9f71-173">Change the Availability Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-availability-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="b9f71-174">Alterar o modo de failover de uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b9f71-174">Change the Failover Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-failover-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="b9f71-175">Criar ou configurar um ouvinte do grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b9f71-175">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="b9f71-176">Configurar a política de failover flexível para controlar condições de failover automático (grupos de disponibilidade AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="b9f71-176">Configure the Flexible Failover Policy to Control Conditions for Automatic Failover (AlwaysOn Availability Groups)</span></span>](configure-flexible-automatic-failover-policy.md)  
  
-   [<span data-ttu-id="b9f71-177">Especificar a URL do ponto de extremidade ao adicionar ou modificar uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b9f71-177">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
-   [<span data-ttu-id="b9f71-178">Configurar backup em réplicas de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b9f71-178">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
-   [<span data-ttu-id="b9f71-179">Configurar o acesso somente leitura em uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b9f71-179">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="b9f71-180">Configurar o roteamento somente leitura para um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b9f71-180">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="b9f71-181">Alterar o período de tempo limite da sessão de uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b9f71-181">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
 <span data-ttu-id="b9f71-182">**Para concluir a configuração do grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="b9f71-182">**To complete availability group configuration**</span></span>  
  
-   [<span data-ttu-id="b9f71-183">Unir uma réplica secundária a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b9f71-183">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="b9f71-184">Preparar um banco de dados secundário manualmente para um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b9f71-184">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="b9f71-185">Unir um banco de dados secundário a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b9f71-185">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="b9f71-186">Criar ou configurar um ouvinte do grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b9f71-186">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
 <span data-ttu-id="b9f71-187">**Maneiras alternativas de criar um grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="b9f71-187">**Alternative ways to create an availability group**</span></span>  
  
-   [<span data-ttu-id="b9f71-188">Usar o Assistente de Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="b9f71-188">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="b9f71-189">Usar a caixa de diálogo Novo Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="b9f71-189">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="b9f71-190">Criar um grupo de disponibilidade &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b9f71-190">Create an Availability Group &#40;Transact-SQL&#41;</span></span>](create-an-availability-group-transact-sql.md)  
  
 <span data-ttu-id="b9f71-191">**Para solucionar problemas de configuração de grupos de disponibilidade AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="b9f71-191">**To troubleshoot AlwaysOn Availability Groups configuration**</span></span>  
  
-   [<span data-ttu-id="b9f71-192">Solução de problemas de configuração de Grupos de Disponibilidade AlwaysOn (SQL Server) excluída</span><span class="sxs-lookup"><span data-stu-id="b9f71-192">Troubleshoot AlwaysOn Availability Groups Configuration (SQL Server)deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
  
-   [<span data-ttu-id="b9f71-193">Solucionar problemas de uma operação de adição de arquivo com falha &#40;Grupos de Disponibilidade AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="b9f71-193">Troubleshoot a Failed Add-File Operation &#40;AlwaysOn Availability Groups&#41;</span></span>](troubleshoot-a-failed-add-file-operation-always-on-availability-groups.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="b9f71-194">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="b9f71-194">Related Content</span></span>  
  
-   <span data-ttu-id="b9f71-195">**Blogs:**</span><span class="sxs-lookup"><span data-stu-id="b9f71-195">**Blogs:**</span></span>  
  
     [<span data-ttu-id="b9f71-196">Série de aprendizado do AlwaysON - HADRON: uso de trabalho do pool para bancos de dados habilitados do HADRON</span><span class="sxs-lookup"><span data-stu-id="b9f71-196">AlwaysON - HADRON Learning Series: Worker Pool Usage for HADRON Enabled Databases</span></span>](https://blogs.msdn.com/b/psssql/archive/2012/05/17/alwayson-hadron-learning-series-worker-pool-usage-for-hadron-enabled-databases.aspx)  
  
     [<span data-ttu-id="b9f71-197">Configurando o AlwaysOn com o SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9f71-197">Configuring AlwaysOn with SQL Server PowerShell</span></span>](https://blogs.msdn.com/b/sqlalwayson/archive/2012/02/03/configuring-alwayson-with-sql-server-powershell.aspx)  
  
     [<span data-ttu-id="b9f71-198">Blogs da equipe do SQL Server AlwaysOn: o blog oficial da equipe do SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="b9f71-198">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="b9f71-199">Blogs dos engenheiros do CSS SQL Server</span><span class="sxs-lookup"><span data-stu-id="b9f71-199">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="b9f71-200">**Vídeos:**</span><span class="sxs-lookup"><span data-stu-id="b9f71-200">**Videos:**</span></span>  
  
     [<span data-ttu-id="b9f71-201">Microsoft SQL Server codinome "Denali" Série AlwaysOn, Parte 1: Introduzindo a próxima geração de solução de alta disponibilidade</span><span class="sxs-lookup"><span data-stu-id="b9f71-201">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 1: Introducing the Next Generation High Availability Solution</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI302)  
  
     [<span data-ttu-id="b9f71-202">Microsoft SQL Server codinome "Denali" Série AlwaysOn, Parte 2: Criando uma solução de disponibilidade de missão crítica usando AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="b9f71-202">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 2: Building a Mission-Critical High Availability Solution Using AlwaysOn</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI404)  
  
-   <span data-ttu-id="b9f71-203">**Whitepapers:**</span><span class="sxs-lookup"><span data-stu-id="b9f71-203">**Whitepapers:**</span></span>  
  
     [<span data-ttu-id="b9f71-204">Guia de soluções AlwaysOn do Microsoft SQL Server para alta disponibilidade e recuperação de desastre</span><span class="sxs-lookup"><span data-stu-id="b9f71-204">Microsoft SQL Server AlwaysOn Solutions Guide for High Availability and Disaster Recovery</span></span>](https://go.microsoft.com/fwlink/?LinkId=227600)  
  
     [<span data-ttu-id="b9f71-205">White papers da Microsoft para SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="b9f71-205">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="b9f71-206">White papers da equipe de consultoria do cliente do SQL Server</span><span class="sxs-lookup"><span data-stu-id="b9f71-206">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="b9f71-207">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b9f71-207">See Also</span></span>  
 [<span data-ttu-id="b9f71-208">O ponto de extremidade de espelhamento de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b9f71-208">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md)   
