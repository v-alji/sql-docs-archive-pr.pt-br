---
title: Alterar o período de tempo limite da sessão de uma réplica de disponibilidade (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], session timeout
- session timeout [SQL Server]
ms.assetid: e23c6e06-1cd1-4d4a-9bc2-e3e06ab2933d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 302ba4a2b0b72a70b05e563eb4085913074469eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685302"
---
# <a name="change-the-session-timeout-period-for-an-availability-replica-sql-server"></a><span data-ttu-id="a9495-102">Alterar o período de tempo limite da sessão de uma réplica de disponibilidade (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a9495-102">Change the Session-Timeout Period for an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="a9495-103">Este tópico descreve como configurar o período de tempo limite da sessão de uma réplica de disponibilidade AlwaysOn usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], o [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou o PowerShell no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9495-103">This topic describes how to configure the session-timeout period of an AlwaysOn availability replica by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="a9495-104">O período de tempo limite da sessão é uma propriedade de réplica que controla quantos segundos uma réplica de disponibilidade espera por uma resposta de ping de uma réplica conectada antes de considerar que ocorreu uma falha na conexão.</span><span class="sxs-lookup"><span data-stu-id="a9495-104">The session-timeout period is a replica property that controls how many seconds (in seconds) that an availability replica waits for a ping response from a connected replica before considering the connection to have failed.</span></span> <span data-ttu-id="a9495-105">Por padrão, uma réplica espera 10 segundos por uma resposta de ping.</span><span class="sxs-lookup"><span data-stu-id="a9495-105">By default, a replica waits 10 seconds for a ping response.</span></span> <span data-ttu-id="a9495-106">Esta propriedade de réplica aplica-se apenas à conexão entre uma determinada réplica secundária e a réplica primária do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="a9495-106">This replica property applies only the connection between a given secondary replica and the primary replica of the availability group.</span></span> <span data-ttu-id="a9495-107">Para obter mais informações o período de tempo limite da sessão, confira [Visão geral dos grupos de disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a9495-107">For more information about the session-timeout period, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span>  
  
-   <span data-ttu-id="a9495-108">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="a9495-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a9495-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="a9495-109">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="a9495-110">Recomendações</span><span class="sxs-lookup"><span data-stu-id="a9495-110">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="a9495-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="a9495-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a9495-112">**Para alterar o período do tempo limite de sessão usando:**</span><span class="sxs-lookup"><span data-stu-id="a9495-112">**To change the session-timeout period, using:**</span></span>  
  
     [<span data-ttu-id="a9495-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a9495-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a9495-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a9495-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="a9495-115">PowerShell</span><span class="sxs-lookup"><span data-stu-id="a9495-115">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a9495-116">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="a9495-116">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="a9495-117">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="a9495-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="a9495-118">Você deve estar conectado à instância do servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="a9495-118">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="a9495-119">Recomendações</span><span class="sxs-lookup"><span data-stu-id="a9495-119">Recommendations</span></span>  
 <span data-ttu-id="a9495-120">Recomendamos que você mantenha o tempo limite em 10 segundos ou mais.</span><span class="sxs-lookup"><span data-stu-id="a9495-120">We recommend that you keep the time-out period at 10 seconds or greater.</span></span> <span data-ttu-id="a9495-121">Definir o valor como menos de 10 segundos cria a possibilidade de um sistema extremamente carregado perdendo PINGs e declarando uma falsa falha.</span><span class="sxs-lookup"><span data-stu-id="a9495-121">Setting the value to less than 10 seconds creates the possibility of a heavily loaded system missing PINGs and declaring a false failure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a9495-122">Segurança</span><span class="sxs-lookup"><span data-stu-id="a9495-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a9495-123">Permissões</span><span class="sxs-lookup"><span data-stu-id="a9495-123">Permissions</span></span>  
 <span data-ttu-id="a9495-124">Requer a permissão ALTER AVAILABILITY GROUP no grupo de disponibilidade, a permissão CONTROL AVAILABILITY GROUP, a permissão ALTER ANY AVAILABILITY GROUP ou a permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="a9495-124">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a9495-125">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a9495-125">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="a9495-126">**Para alterar o período do tempo limite de sessão de uma réplica de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="a9495-126">**To change the session-timeout period for an availability replica**</span></span>  
  
1.  <span data-ttu-id="a9495-127">No Pesquisador de Objetos, conecte-se à instância de servidor que hospeda a réplica primária e expanda a árvore de servidores.</span><span class="sxs-lookup"><span data-stu-id="a9495-127">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="a9495-128">Expanda os nós **Alta Disponibilidade AlwaysOn** e **Grupos de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="a9495-128">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="a9495-129">Clique no grupo de disponibilidade cuja réplica de disponibilidade você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="a9495-129">Click the availability group whose availability replica you want to configure.</span></span>  
  
4.  <span data-ttu-id="a9495-130">Clique com o botão direito do mouse na réplica a ser configurada e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="a9495-130">Right-click the replica to be configured, and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="a9495-131">Na caixa de diálogo **Propriedades da Réplica de Disponibilidade** , use o campo **Tempo limite da sessão (segundos)** para alterar o número de segundos do período do tempo limite da sessão nesta réplica.</span><span class="sxs-lookup"><span data-stu-id="a9495-131">In the **Availability Replica Properties** dialog box, use the **Session timeout (seconds)** field to change the number of seconds for the session-timeout period on this replica.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a9495-132">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a9495-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="a9495-133">**Para alterar o período do tempo limite de sessão de uma réplica de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="a9495-133">**To change the session-timeout period for an availability replica**</span></span>  
  
1.  <span data-ttu-id="a9495-134">Conecte-se à instância de servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="a9495-134">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="a9495-135">Use a instrução [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="a9495-135">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="a9495-136">ALTER AVAILABILITY GROUP *group_name*</span><span class="sxs-lookup"><span data-stu-id="a9495-136">ALTER AVAILABILITY GROUP *group_name*</span></span>  
  
     <span data-ttu-id="a9495-137">MODIFY REPLICA ON '*instance_name*' WITH ( SESSION_TIMEOUT =*seconds* )</span><span class="sxs-lookup"><span data-stu-id="a9495-137">MODIFY REPLICA ON '*instance_name*' WITH ( SESSION_TIMEOUT =*seconds* )</span></span>  
  
     <span data-ttu-id="a9495-138">em que *group_name* é o nome do grupo de disponibilidade, *instance_name* é o nome da instância de servidor que hospeda a réplica de disponibilidade a ser modificada e *seconds* especifica o número mínimo de segundos que a réplica deve esperar antes de aplicar o log aos bancos de dados ao funcionar como uma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="a9495-138">where *group_name* is the name of the availability group, *instance_name* is the name of the server instance that hosts the availability replica to be modified, and *seconds* specifies the minimum number of seconds that the replica must wait before applying log to databases when acting as a secondary replica.</span></span> <span data-ttu-id="a9495-139">O valor padrão é 0 segundos, o que indica que não há nenhum atraso de aplicação.</span><span class="sxs-lookup"><span data-stu-id="a9495-139">The default is 0 seconds, which indicates that there is no apply delay.</span></span>  
  
     <span data-ttu-id="a9495-140">O exemplo a seguir, inserido na réplica primária do grupo de disponibilidade `AccountsAG` , altera o valor do tempo limite da sessão para `15` segundos para a réplica localizada na instância de servidor `INSTANCE09` .</span><span class="sxs-lookup"><span data-stu-id="a9495-140">The following example, entered on the primary replica of the `AccountsAG` availability group, changes the session-timeout value to `15` seconds for the replica located on the `INSTANCE09` server instance.</span></span>  
  
    ```  
    ALTER AVAILABILITY GROUP AccountsAG   
       MODIFY REPLICA ON 'INSTANCE09' WITH (SESSION_TIMEOUT = 15);  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="a9495-141">Uso do PowerShell</span><span class="sxs-lookup"><span data-stu-id="a9495-141">Using PowerShell</span></span>  

### <a name="to-change-the-session-timeout-period-for-an-availability-replica"></a><span data-ttu-id="a9495-142">Para alterar o período do tempo limite de sessão de uma réplica de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="a9495-142">To change the session-timeout period for an availability replica</span></span>
  
1.  <span data-ttu-id="a9495-143">Altere o diretório (`cd`) para a instância do servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="a9495-143">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="a9495-144">Use o cmdlet `Set-SqlAvailabilityReplica` com o parâmetro `SessionTimeout` para alterar o número de segundos do período de tempo limite da sessão em uma réplica de disponibilidade especificada.</span><span class="sxs-lookup"><span data-stu-id="a9495-144">Use the `Set-SqlAvailabilityReplica` cmdlet with the `SessionTimeout` parameter to change the number of seconds for the session-timeout period on a specified availability replica.</span></span>  
  
     <span data-ttu-id="a9495-145">Por exemplo, o seguinte comando define o período de tempo limite de sessão para 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="a9495-145">For example, the following command sets the session-timeout period to 15 seconds.</span></span>  
  
    ```powershell
    Set-SqlAvailabilityReplica -SessionTimeout 15 -Path SQLSERVER:\Sql\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\AvailabilityReplicas\MyReplica  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="a9495-146">Para exibir a sintaxe de um cmdlet, use o cmdlet `Get-Help` no ambiente do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a9495-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="a9495-147">Para obter mais informações, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="a9495-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="a9495-148">Para configurar e usar o provedor de SQL Server PowerShell, consulte [provedor de SQL Server PowerShell](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="a9495-148">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a9495-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a9495-149">See Also</span></span>  
 [<span data-ttu-id="a9495-150">Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a9495-150">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
