---
title: Configurar o acesso somente leitura em uma réplica de disponibilidade (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 10/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- connection access to availability replicas
- Availability Groups [SQL Server], readable secondary replicas
- active secondary replicas [SQL Server], read-only access to
- Availability Groups [SQL Server], read-only routing
- Availability Groups [SQL Server], client connectivity
ms.assetid: 22387419-22c4-43fa-851c-5fecec4b049b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ab13081396aff46d193c1b0449d6b93042ee60d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679532"
---
# <a name="configure-read-only-access-on-an-availability-replica-sql-server"></a><span data-ttu-id="d2d69-102">Configurar o acesso somente leitura em uma réplica de disponibilidade (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d2d69-102">Configure Read-Only Access on an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="d2d69-103">Por padrão, tanto o acesso de leitura-gravação quanto o acesso de tentativa de leitura são permitidos para a réplica primária e nenhuma conexão direta é permitida com as réplicas secundárias de um grupo de disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="d2d69-103">By default both read-write and read-intent access are allowed to the primary replica and no connections are allowed to secondary replicas of an AlwaysOn availability group.</span></span> <span data-ttu-id="d2d69-104">Este tópico descreve como configurar o acesso de conexão em uma réplica de disponibilidade de um grupo de disponibilidade AlwaysOn no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d2d69-104">This topic describes how to configure connection access on an availability replica of an AlwaysOn availability group in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
 <span data-ttu-id="d2d69-105">Para obter informações sobre as implicações de permitir o acesso somente leitura para uma réplica secundária e para uma introdução ao acesso de conexão, consulte [Sobre Acesso de conexão de cliente a réplicas de disponibilidade &#40;SQL Server&#41;](about-client-connection-access-to-availability-replicas-sql-server.md) e [Secundárias ativas: réplicas secundárias legíveis &#40;Grupos de Disponibilidade AlwaysOn&#41;](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="d2d69-105">For information about the implications of enabling read-only access for a secondary replica and for an introduction to connection access, see [About Client Connection Access to Availability Replicas &#40;SQL Server&#41;](about-client-connection-access-to-availability-replicas-sql-server.md) and [Active Secondaries: Readable Secondary Replicas &#40;AlwaysOn Availability Groups&#41;](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span></span>  
  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d2d69-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="d2d69-106">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="d2d69-107">Pré-requisitos e restrições</span><span class="sxs-lookup"><span data-stu-id="d2d69-107">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="d2d69-108">Para configurar um acesso de conexão diferente, deverá estar conectado à instância de servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="d2d69-108">To configure different connection access, you must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d2d69-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="d2d69-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d2d69-110">Permissões</span><span class="sxs-lookup"><span data-stu-id="d2d69-110">Permissions</span></span>  
  
|<span data-ttu-id="d2d69-111">Tarefa</span><span class="sxs-lookup"><span data-stu-id="d2d69-111">Task</span></span>|<span data-ttu-id="d2d69-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="d2d69-112">Permissions</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="d2d69-113">Para configurar réplicas ao criar um grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="d2d69-113">To configure replicas when creating an availability group</span></span>|<span data-ttu-id="d2d69-114">Requer a associação na função de servidor fixa **sysadmin** e a permissão de servidor CREATE AVAILABILITY GROUP, a permissão ALTER ANY AVAILABILITY GROUP ou a permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="d2d69-114">Requires membership in the **sysadmin** fixed server role and either CREATE AVAILABILITY GROUP server permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>|  
|<span data-ttu-id="d2d69-115">Para modificar uma réplica de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="d2d69-115">To modify an availability replica</span></span>|<span data-ttu-id="d2d69-116">Requer a permissão ALTER AVAILABILITY GROUP no grupo de disponibilidade, a permissão CONTROL AVAILABILITY GROUP, a permissão ALTER ANY AVAILABILITY GROUP ou a permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="d2d69-116">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>|  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d2d69-117">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d2d69-117">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="d2d69-118">**Para configurar o acesso em uma réplica de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="d2d69-118">**To configure access on an availability replica**</span></span>  
  
1.  <span data-ttu-id="d2d69-119">No Pesquisador de Objetos, conecte-se à instância de servidor que hospeda a réplica primária e expanda a árvore de servidores.</span><span class="sxs-lookup"><span data-stu-id="d2d69-119">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="d2d69-120">Expanda os nós **Alta Disponibilidade AlwaysOn** e **Grupos de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="d2d69-120">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="d2d69-121">Clique no grupo de disponibilidade cuja réplica você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="d2d69-121">Click the availability group whose replica you want to change.</span></span>  
  
4.  <span data-ttu-id="d2d69-122">Clique com o botão direito do mouse na réplica de disponibilidade e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="d2d69-122">Right-click the availability replica, and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="d2d69-123">Na caixa de diálogo **Propriedades de Réplica de disponibilidade** , você pode alterar o acesso de conexão para as funções primária e secundária, da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="d2d69-123">In the **Availability Replica Properties** dialog box, you can change the connection access for the primary role and for the secondary role, as follows:</span></span>  
  
    -   <span data-ttu-id="d2d69-124">Para a função secundária, selecione um novo valor na lista suspensa **Secundária de Leitura** , da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="d2d69-124">For the secondary role, select a new value from the **Readable secondary** drop list, as follows:</span></span>  
  
         <span data-ttu-id="d2d69-125">**Não**</span><span class="sxs-lookup"><span data-stu-id="d2d69-125">**No**</span></span>  
         <span data-ttu-id="d2d69-126">Nenhuma conexão de usuário é permitida para bancos de dados secundários desta réplica.</span><span class="sxs-lookup"><span data-stu-id="d2d69-126">No user connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="d2d69-127">Eles não estão disponíveis para acesso de leitura.</span><span class="sxs-lookup"><span data-stu-id="d2d69-127">They are not available for read access.</span></span> <span data-ttu-id="d2d69-128">Essa é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="d2d69-128">This is the default setting.</span></span>  
  
         <span data-ttu-id="d2d69-129">**Tentativa de leitura somente**</span><span class="sxs-lookup"><span data-stu-id="d2d69-129">**Read-intent only**</span></span>  
         <span data-ttu-id="d2d69-130">Somente conexões somente leitura são permitidas para bancos de dados secundários desta réplica.</span><span class="sxs-lookup"><span data-stu-id="d2d69-130">Only read-only connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="d2d69-131">Os bancos de dados secundários estão disponíveis para acesso de leitura.</span><span class="sxs-lookup"><span data-stu-id="d2d69-131">The secondary database(s) are all available for read access.</span></span>  
  
         <span data-ttu-id="d2d69-132">**Sim**</span><span class="sxs-lookup"><span data-stu-id="d2d69-132">**Yes**</span></span>  
         <span data-ttu-id="d2d69-133">Todas as conexões são permitidas para os bancos de dados secundários desta réplica, mas somente para acesso de leitura.</span><span class="sxs-lookup"><span data-stu-id="d2d69-133">All connections are allowed to secondary databases of this replica, but only for read access.</span></span> <span data-ttu-id="d2d69-134">Os bancos de dados secundários estão disponíveis para acesso de leitura.</span><span class="sxs-lookup"><span data-stu-id="d2d69-134">The secondary database(s) are all available for read access.</span></span>  
  
    -   <span data-ttu-id="d2d69-135">Para a função primária, selecione um novo valor na lista suspensa **Conexões na função primária** , da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="d2d69-135">For the primary role, select a new value from the **Connections in primary role** drop list, as follows:</span></span>  
  
         <span data-ttu-id="d2d69-136">**Permitir todas as conexões**</span><span class="sxs-lookup"><span data-stu-id="d2d69-136">**Allow all connections**</span></span>  
         <span data-ttu-id="d2d69-137">Todas as conexões são permitidas com os bancos de dados na réplica primária.</span><span class="sxs-lookup"><span data-stu-id="d2d69-137">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="d2d69-138">Essa é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="d2d69-138">This is the default setting.</span></span>  
  
         <span data-ttu-id="d2d69-139">**Permitir conexões de leitura/gravação**</span><span class="sxs-lookup"><span data-stu-id="d2d69-139">**Allow read/write connections**</span></span>  
         <span data-ttu-id="d2d69-140">Quando a propriedade Application Intent está definida como **ReadWrite** ou não está definida, a conexão é permitida.</span><span class="sxs-lookup"><span data-stu-id="d2d69-140">When the Application Intent property is set to **ReadWrite** or the Application Intent connection property is not set, the connection is allowed.</span></span> <span data-ttu-id="d2d69-141">Conexões em que a propriedade de conexão Application Intent é definida como **ReadOnly** não são permitidas.</span><span class="sxs-lookup"><span data-stu-id="d2d69-141">Connections where the Application Intent connection property is set to **ReadOnly** are not allowed.</span></span> <span data-ttu-id="d2d69-142">Isto pode ajudar a impedir os clientes de conectarem uma carga de trabalho com intenção de leitura à réplica primária por engano.</span><span class="sxs-lookup"><span data-stu-id="d2d69-142">This can help prevent customers from connecting a read-intent work load to the primary replica by mistake.</span></span> <span data-ttu-id="d2d69-143">Para obter mais informações sobre a propriedade de conexão Tentativa de Aplicativo, consulte [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="d2d69-143">For more information about Application Intent connection property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d2d69-144">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d2d69-144">Using Transact-SQL</span></span>  
 <span data-ttu-id="d2d69-145">**Para configurar o acesso em uma réplica de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="d2d69-145">**To configure access on an availability replica**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d2d69-146">Para obter um exemplo desse procedimento, veja [Exemplo (Transact-SQL)](#TsqlExample), mais adiante nesta seção.</span><span class="sxs-lookup"><span data-stu-id="d2d69-146">For an example of this procedure, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="d2d69-147">Conecte-se à instância de servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="d2d69-147">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="d2d69-148">Se você estiver especificando uma réplica para um novo grupo de disponibilidade, use a instrução [CREATE AVAILABILITY GROUP](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d2d69-148">If you are specifying a replica for a new availability group, use the [CREATE AVAILABILITY GROUP](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="d2d69-149">Se você estiver adicionando ou modificando uma réplica de um grupo de disponibilidade existente, use a instrução [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d2d69-149">If you are adding or modifying a replica of an existing availability group, use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span>  
  
    -   <span data-ttu-id="d2d69-150">Para configurar o acesso de conexão para a função secundária, na cláusula ADD REPLICA ou MODIFY REPLICA WITH, especifique a opção SECONDARY_ROLE, da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="d2d69-150">To configure connection access for the secondary role, in the ADD REPLICA or MODIFY REPLICA WITH clause, specify the SECONDARY_ROLE option, as follows:</span></span>  
  
         <span data-ttu-id="d2d69-151">SECONDARY_ROLE **(** ALLOW_CONNECTIONS **=** { NO | READ_ONLY | ALL } **)**</span><span class="sxs-lookup"><span data-stu-id="d2d69-151">SECONDARY_ROLE **(** ALLOW_CONNECTIONS **=** { NO | READ_ONLY | ALL } **)**</span></span>  
  
         <span data-ttu-id="d2d69-152">onde:</span><span class="sxs-lookup"><span data-stu-id="d2d69-152">where,</span></span>  
  
         <span data-ttu-id="d2d69-153">Não</span><span class="sxs-lookup"><span data-stu-id="d2d69-153">NO</span></span>  
         <span data-ttu-id="d2d69-154">Nenhuma conexão direta é permitida para bancos de dados secundários desta réplica.</span><span class="sxs-lookup"><span data-stu-id="d2d69-154">No direct connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="d2d69-155">Eles não estão disponíveis para acesso de leitura.</span><span class="sxs-lookup"><span data-stu-id="d2d69-155">They are not available for read access.</span></span> <span data-ttu-id="d2d69-156">Essa é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="d2d69-156">This is the default setting.</span></span>  
  
         <span data-ttu-id="d2d69-157">READ_ONLY</span><span class="sxs-lookup"><span data-stu-id="d2d69-157">READ_ONLY</span></span>  
         <span data-ttu-id="d2d69-158">Somente conexões somente leitura são permitidas para bancos de dados secundários desta réplica.</span><span class="sxs-lookup"><span data-stu-id="d2d69-158">Only read-only connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="d2d69-159">Os bancos de dados secundários estão disponíveis para acesso de leitura.</span><span class="sxs-lookup"><span data-stu-id="d2d69-159">The secondary database(s) are all available for read access.</span></span>  
  
         <span data-ttu-id="d2d69-160">ALL</span><span class="sxs-lookup"><span data-stu-id="d2d69-160">ALL</span></span>  
         <span data-ttu-id="d2d69-161">Todas as conexões são permitidas para os bancos de dados secundários desta réplica, mas somente para acesso de leitura.</span><span class="sxs-lookup"><span data-stu-id="d2d69-161">All connections are allowed to secondary databases of this replica, but only for read access.</span></span> <span data-ttu-id="d2d69-162">Os bancos de dados secundários estão disponíveis para acesso de leitura.</span><span class="sxs-lookup"><span data-stu-id="d2d69-162">The secondary database(s) are all available for read access.</span></span>  
  
3.  <span data-ttu-id="d2d69-163">Para configurar o acesso de conexão para a função primária, na cláusula ADD REPLICA ou MODIFY REPLICA WITH, especifique a opção PRIMARY_ROLE, da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="d2d69-163">To configure connection access for the primary role, in the ADD REPLICA or MODIFY REPLICA WITH clause, specify the PRIMARY_ROLE option, as follows:</span></span>  
  
     <span data-ttu-id="d2d69-164">PRIMARY_ROLE **(** ALLOW_CONNECTIONS **=** { READ_WRITE | ALL } **)**</span><span class="sxs-lookup"><span data-stu-id="d2d69-164">PRIMARY_ROLE **(** ALLOW_CONNECTIONS **=** { READ_WRITE | ALL } **)**</span></span>  
  
     <span data-ttu-id="d2d69-165">onde:</span><span class="sxs-lookup"><span data-stu-id="d2d69-165">where,</span></span>  
  
     <span data-ttu-id="d2d69-166">READ_WRITE</span><span class="sxs-lookup"><span data-stu-id="d2d69-166">READ_WRITE</span></span>  
     <span data-ttu-id="d2d69-167">Conexões em que a propriedade de conexão Application Intent é definida como **ReadOnly** não são permitidas.</span><span class="sxs-lookup"><span data-stu-id="d2d69-167">Connections where the Application Intent connection property is set to **ReadOnly** are disallowed.</span></span>  <span data-ttu-id="d2d69-168">Quando a propriedade Application Intent está definida como **ReadWrite** ou não está definida, a conexão é permitida.</span><span class="sxs-lookup"><span data-stu-id="d2d69-168">When the Application Intent property is set to **ReadWrite** or the Application Intent connection property is not set, the connection is allowed.</span></span> <span data-ttu-id="d2d69-169">Para obter mais informações sobre a propriedade de conexão Tentativa de Aplicativo, consulte [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="d2d69-169">For more information about Application Intent connection property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
     <span data-ttu-id="d2d69-170">ALL</span><span class="sxs-lookup"><span data-stu-id="d2d69-170">ALL</span></span>  
     <span data-ttu-id="d2d69-171">Todas as conexões são permitidas com os bancos de dados na réplica primária.</span><span class="sxs-lookup"><span data-stu-id="d2d69-171">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="d2d69-172">Essa é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="d2d69-172">This is the default setting.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="d2d69-173">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d2d69-173">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="d2d69-174">O exemplo a seguir adiciona uma réplica secundária a um grupo de disponibilidade denominado *AG2*.</span><span class="sxs-lookup"><span data-stu-id="d2d69-174">The following example adds a secondary replica to an availability group named *AG2*.</span></span> <span data-ttu-id="d2d69-175">Uma instância de servidor autônoma *COMPUTER03\HADR_INSTANCE*, é especificada para hospedar a nova réplica de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="d2d69-175">A stand-alone server instance, *COMPUTER03\HADR_INSTANCE*, is specified to host the new availability replica.</span></span> <span data-ttu-id="d2d69-176">Essa réplica foi configurada para permitir apenas conexões de leitura-gravação para a função primária e para permitir apenas conexões de tentativa de leitura para uma função secundária.</span><span class="sxs-lookup"><span data-stu-id="d2d69-176">This replica configured to allow only read-write connections for the primary role and to allow only read-intent connections for secondary role.</span></span>  
  
```sql
ALTER AVAILABILITY GROUP AG2   
   ADD REPLICA ON   
      'COMPUTER03\HADR_INSTANCE' WITH   
         (  
         ENDPOINT_URL = 'TCP://COMPUTER03:7022',  
         PRIMARY_ROLE ( ALLOW_CONNECTIONS = READ_WRITE ),  
         SECONDARY_ROLE (ALLOW_CONNECTIONS = READ_ONLY )  
         );   
GO  
```  
  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="d2d69-177">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="d2d69-177">Using PowerShell</span></span>  

### <a name="to-configure-access-on-an-availability-replica"></a><span data-ttu-id="d2d69-178">Para configurar o acesso em uma réplica de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="d2d69-178">To configure access on an availability replica</span></span>
  
> [!NOTE]  
>  <span data-ttu-id="d2d69-179">Para obter um exemplo de código, consulte os exemplos do PowerShell mais adiante nesta seção.</span><span class="sxs-lookup"><span data-stu-id="d2d69-179">For a code example, see the PowerShell examples later in this section.</span></span>  
  
1.  <span data-ttu-id="d2d69-180">Altere o diretório (`cd`) para a instância do servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="d2d69-180">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="d2d69-181">Ao adicionar uma réplica de disponibilidade a um grupo de disponibilidade, use o cmdlet `New-SqlAvailabilityReplica`.</span><span class="sxs-lookup"><span data-stu-id="d2d69-181">When adding an availability replica to an availability group, use the `New-SqlAvailabilityReplica` cmdlet.</span></span> <span data-ttu-id="d2d69-182">Ao modificar uma réplica de disponibilidade existente, use o cmdlet `Set-SqlAvailabilityReplica`.</span><span class="sxs-lookup"><span data-stu-id="d2d69-182">When modifying an existing availability replica, use the `Set-SqlAvailabilityReplica` cmdlet.</span></span> <span data-ttu-id="d2d69-183">Os parâmetros relevantes são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="d2d69-183">The relevant parameters are as follows:</span></span>  
  
    -   <span data-ttu-id="d2d69-184">Para configurar o acesso de conexão para a função secundária, especifique o `ConnectionModeInSecondaryRole` parâmetro *secondary_role_keyword* , em que *secondary_role_keyword* é igual a um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="d2d69-184">To configure connection access for the secondary role, specify the `ConnectionModeInSecondaryRole`*secondary_role_keyword* parameter, where *secondary_role_keyword* equals one of the following values:</span></span>  
  
         `AllowNoConnections`  
         <span data-ttu-id="d2d69-185">Nenhuma conexão direta é permitida com os bancos de dados na réplica secundária e os bancos de dados não estão disponíveis para acesso de leitura.</span><span class="sxs-lookup"><span data-stu-id="d2d69-185">No direct connections are allowed to the databases in the secondary replica and the databases are not available for read access.</span></span> <span data-ttu-id="d2d69-186">Essa é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="d2d69-186">This is the default setting.</span></span>  
  
         `AllowReadIntentConnectionsOnly`  
         <span data-ttu-id="d2d69-187">Conexões são permitidas somente com os bancos de dados na réplica secundária em que a propriedade Application Intent está definida como **ReadOnly**.</span><span class="sxs-lookup"><span data-stu-id="d2d69-187">Connections are allowed only to the databases in the secondary replica where the Application Intent property is set to **ReadOnly**.</span></span> <span data-ttu-id="d2d69-188">Para obter mais informações sobre essa propriedade, consulte [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="d2d69-188">For more information about this property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
         `AllowAllConnections`  
         <span data-ttu-id="d2d69-189">Todas as conexões são permitidas com os bancos de dados na réplica secundária para acesso somente leitura.</span><span class="sxs-lookup"><span data-stu-id="d2d69-189">All connections are allowed to the databases in the secondary replica for read-only access.</span></span>  
  
    -   <span data-ttu-id="d2d69-190">Para configurar o acesso de conexão para a função primária, especifique `ConnectionModeInPrimaryRole` *primary_role_keyword*, em que *primary_role_keyword* é igual a um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="d2d69-190">To configure connection access for the primary role, specify `ConnectionModeInPrimaryRole`*primary_role_keyword*, where *primary_role_keyword* equals one of the following values:</span></span>  
  
         `AllowReadWriteConnections`  
         <span data-ttu-id="d2d69-191">Conexões em que a propriedade de conexão Application Intent é definida como ReadOnly não são permitidas.</span><span class="sxs-lookup"><span data-stu-id="d2d69-191">Connections where the Application Intent connection property is set to ReadOnly are disallowed.</span></span> <span data-ttu-id="d2d69-192">Quando a propriedade Application Intent está definida como ReadWrite ou não está definida, a conexão é permitida.</span><span class="sxs-lookup"><span data-stu-id="d2d69-192">When the Application Intent property is set to ReadWrite or the Application Intent connection property is not set, the connection is allowed.</span></span> <span data-ttu-id="d2d69-193">Para obter mais informações sobre a propriedade de conexão Tentativa de Aplicativo, consulte [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="d2d69-193">For more information about Application Intent connection property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
         `AllowAllConnections`  
         <span data-ttu-id="d2d69-194">Todas as conexões são permitidas com os bancos de dados na réplica primária.</span><span class="sxs-lookup"><span data-stu-id="d2d69-194">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="d2d69-195">Essa é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="d2d69-195">This is the default setting.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d2d69-196">Para exibir a sintaxe de um cmdlet, use o cmdlet `Get-Help` no ambiente do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d2d69-196">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell environment.</span></span> <span data-ttu-id="d2d69-197">Para obter mais informações, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="d2d69-197">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="d2d69-198">Para configurar e usar o provedor de SQL Server PowerShell, consulte [provedor de SQL Server PowerShell](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="d2d69-198">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>
  
<span data-ttu-id="d2d69-199">O exemplo a seguir define os parâmetros `ConnectionModeInSecondaryRole` e `ConnectionModeInPrimaryRole` para `AllowAllConnections`.</span><span class="sxs-lookup"><span data-stu-id="d2d69-199">The following example, sets the both the `ConnectionModeInSecondaryRole` and `ConnectionModeInPrimaryRole` parameters to `AllowAllConnections`.</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\PrimaryServer\default\AvailabilityGroups\MyAg  
$primaryReplica = Get-Item "AvailabilityReplicas\PrimaryServer"  

Set-SqlAvailabilityReplica -ConnectionModeInSecondaryRole "AllowAllConnections" `
 -InputObject $primaryReplica  
Set-SqlAvailabilityReplica -ConnectionModeInPrimaryRole "AllowAllConnections" `
-InputObject $primaryReplica
```  

##  <a name="follow-up-after-configuring-read-only-access-for-an-availability-replica"></a><a name="FollowUp"></a> <span data-ttu-id="d2d69-200">Acompanhamento: depois de configurar o acesso somente leitura para uma réplica de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="d2d69-200">Follow Up: After Configuring Read-Only Access for an Availability Replica</span></span>  
 <span data-ttu-id="d2d69-201">**Acesso somente leitura para uma réplica secundária legível**</span><span class="sxs-lookup"><span data-stu-id="d2d69-201">**Read-only access to a readable secondary replica**</span></span>  
  
-   <span data-ttu-id="d2d69-202">Ao usar o [utilitário bcp](../../../tools/bcp-utility.md) ou o [utilitário sqlcmd](../../../tools/sqlcmd-utility.md), você pode especificar o acesso somente leitura a qualquer réplica secundária que esteja habilitada para acesso somente leitura, especificando a `-K ReadOnly` opção.</span><span class="sxs-lookup"><span data-stu-id="d2d69-202">When using the [bcp Utility](../../../tools/bcp-utility.md) or [sqlcmd Utility](../../../tools/sqlcmd-utility.md), you can specify read-only access to any secondary replica that is enabled for read-only access by specifying the `-K ReadOnly` switch.</span></span>  
  
-   <span data-ttu-id="d2d69-203">Para permitir que aplicativos clientes conectem-se a réplicas secundárias legíveis:</span><span class="sxs-lookup"><span data-stu-id="d2d69-203">To enable client applications to connect to readable secondary replicas:</span></span>  
  
    ||<span data-ttu-id="d2d69-204">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="d2d69-204">Prerequisite</span></span>|<span data-ttu-id="d2d69-205">Link</span><span class="sxs-lookup"><span data-stu-id="d2d69-205">Link</span></span>|  
    |-|------------------|----------|  
    |<span data-ttu-id="d2d69-206">![Caixa de seleção](../../media/checkboxemptycenterxtraspacetopandright.gif "Caixa de seleção")</span><span class="sxs-lookup"><span data-stu-id="d2d69-206">![Checkbox](../../media/checkboxemptycenterxtraspacetopandright.gif "Checkbox")</span></span>|<span data-ttu-id="d2d69-207">Verifique se o grupo de disponibilidade tem um ouvinte.</span><span class="sxs-lookup"><span data-stu-id="d2d69-207">Ensure that the availability group has a listener.</span></span>|[<span data-ttu-id="d2d69-208">Criar ou configurar um ouvinte do grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d2d69-208">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)|  
    |<span data-ttu-id="d2d69-209">![Caixa de seleção](../../media/checkboxemptycenterxtraspacetopandright.gif "Caixa de seleção")</span><span class="sxs-lookup"><span data-stu-id="d2d69-209">![Checkbox](../../media/checkboxemptycenterxtraspacetopandright.gif "Checkbox")</span></span>|<span data-ttu-id="d2d69-210">Configurar o roteamento somente leitura para o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="d2d69-210">Configure read-only routing for the availability group.</span></span>|[<span data-ttu-id="d2d69-211">Configurar o roteamento somente leitura para um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d2d69-211">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)|  
  
 <span data-ttu-id="d2d69-212">**Fatores que podem afetar gatilhos e trabalhos depois de um failover**</span><span class="sxs-lookup"><span data-stu-id="d2d69-212">**Factors that might affect triggers and jobs after a failover**</span></span>  
  
 <span data-ttu-id="d2d69-213">Se você tem gatilhos e trabalhos que podem falhar ao executar um banco de dados secundário não legível ou em um banco de dados secundário legível, você precisa executar o script dos gatilhos e dos trabalhos para verificar em uma réplica determinada se o banco de dados é primário ou secundário legível.</span><span class="sxs-lookup"><span data-stu-id="d2d69-213">If you have triggers and jobs that will fail when running on a non-readable secondary database or on a readable secondary database, you need to script the triggers and jobs to check on a given replica to determine whether the database is a primary database or is a readable secondary database.</span></span> <span data-ttu-id="d2d69-214">Para obter estas informações, use a função [DATABASEPROPERTYEX](/sql/t-sql/functions/databasepropertyex-transact-sql) para retornar a propriedade **Updatability** do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d2d69-214">To obtain this information, use the [DATABASEPROPERTYEX](/sql/t-sql/functions/databasepropertyex-transact-sql) function to return the **Updatability** property of the database.</span></span> <span data-ttu-id="d2d69-215">Para identificar um banco de dados somente leitura, especifique READ_ONLY como o valor, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="d2d69-215">To identify a read-only database, specify READ_ONLY as the value, as follows:</span></span>  
  
```  
DATABASEPROPERTYEX([db name],'Updatability') = N'READ_ONLY'  
```  
  
 <span data-ttu-id="d2d69-216">Para identificar um banco de dados leitura/gravação, especifique READ_WRITE como o valor.</span><span class="sxs-lookup"><span data-stu-id="d2d69-216">To identify a read-write database, specify READ_WRITE as the value.</span></span>  
  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="d2d69-217">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="d2d69-217">Related Tasks</span></span>  
  
-   [<span data-ttu-id="d2d69-218">Configurar o roteamento somente leitura para um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d2d69-218">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="d2d69-219">Criar ou configurar um ouvinte do grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d2d69-219">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="d2d69-220">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="d2d69-220">Related Content</span></span>  
  
-   [<span data-ttu-id="d2d69-221">Always On: proposta de valor da secundária legível</span><span class="sxs-lookup"><span data-stu-id="d2d69-221">Always On: Value Proposition of Readable Secondary</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-value-proposition-of-readable-secondary)  
  
-   [<span data-ttu-id="d2d69-222">Always On: por que há duas opções para habilitar uma réplica secundária para a carga de trabalho de leitura?</span><span class="sxs-lookup"><span data-stu-id="d2d69-222">Always On: Why there are two options to enable a secondary replica for read workload?</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-why-there-are-two-options-to-enable-a-secondary-replica-for-read-workload)  
  
-   [<span data-ttu-id="d2d69-223">Always On: configurar uma réplica secundária legível</span><span class="sxs-lookup"><span data-stu-id="d2d69-223">Always On: Setting up Readable Secondary Replica</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-setting-up-readable-seconary-replica)  
  
-   [<span data-ttu-id="d2d69-224">Always On: acabei de habilitar a réplica secundária legível, mas minha consulta está bloqueada?</span><span class="sxs-lookup"><span data-stu-id="d2d69-224">Always On: I just enabled Readable Secondary but my query is blocked?</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-i-just-enabled-readable-secondary-but-my-query-is-blocked)  
  
-   [<span data-ttu-id="d2d69-225">Always On: disponibilizando as estatísticas mais recentes na réplica secundária legível, no banco de dados somente leitura e no instantâneo do banco de dados</span><span class="sxs-lookup"><span data-stu-id="d2d69-225">Always On: Making latest statistics available on Readable Secondary, Read-Only database and Database Snapshot</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-making-latest-statistics-available-on-readable-secondary-read-only-database-and-database-snapshot)  
  
-   [<span data-ttu-id="d2d69-226">Always On: desafios das estatísticas no banco de dados somente leitura, no instantâneo do banco de dados e na réplica secundária</span><span class="sxs-lookup"><span data-stu-id="d2d69-226">Always On: Challenges with statistics on ReadOnly database, Database Snapshot and Secondary Replica</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-challenges-with-statistics-on-readonly-database-database-snapshot-and-secondary-replica)  
  
-   [<span data-ttu-id="d2d69-227">Always On: impacto na carga de trabalho primária ao executar a carga de trabalho de relatório na réplica secundária</span><span class="sxs-lookup"><span data-stu-id="d2d69-227">Always On: Impact on the primary workload when you run reporting workload on the secondary replica</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-impact-on-the-primary-workload-when-you-run-reporting-workload-on-the-secondary-replica)  
  
-   [<span data-ttu-id="d2d69-228">Always On: impacto do mapeamento da carga de trabalho de relatório na réplica secundária legível para o isolamento do instantâneo</span><span class="sxs-lookup"><span data-stu-id="d2d69-228">Always On: Impact of mapping reporting workload on Readable Secondary to Snapshot Isolation</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-impact-of-mapping-reporting-workload-on-readable-secondary-to-snapshot-isolation)  
  
-   [<span data-ttu-id="d2d69-229">Always On: minimizando o bloqueio do thread REDO ao executar a carga de trabalho de relatório na réplica secundária</span><span class="sxs-lookup"><span data-stu-id="d2d69-229">Always On: Minimizing blocking of REDO thread when running reporting workload on Secondary Replica</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-minimizing-blocking-of-redo-thread-when-running-reporting-workload-on-secondary-replica)  
  
-   [<span data-ttu-id="d2d69-230">Always On: réplica secundária legível e latência de dados</span><span class="sxs-lookup"><span data-stu-id="d2d69-230">Always On: Readable Secondary and data latency</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-readable-secondary-and-data-latency)  
  
## <a name="see-also"></a><span data-ttu-id="d2d69-231">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d2d69-231">See Also</span></span>  
 <span data-ttu-id="d2d69-232">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d2d69-232">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="d2d69-233">Secundárias ativas: réplicas secundárias legíveis &#40;Grupos de Disponibilidade AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="d2d69-233">Active Secondaries: Readable Secondary Replicas &#40;AlwaysOn Availability Groups&#41;</span></span>](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md)  
 [<span data-ttu-id="d2d69-234">Sobre o acesso de conexão de cliente a réplicas de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d2d69-234">About Client Connection Access to Availability Replicas &#40;SQL Server&#41;</span></span>](about-client-connection-access-to-availability-replicas-sql-server.md)  
