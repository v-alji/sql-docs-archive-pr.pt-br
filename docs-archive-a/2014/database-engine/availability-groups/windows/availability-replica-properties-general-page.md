---
title: Propriedades da réplica de disponibilidade (página Geral) | Microsoft Docs
ms.custom: ''
ms.date: 10/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilityreplicaproperties.general.f1
ms.assetid: 8318fefb-e045-4fab-8507-e1951fc7cec6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 313314baf009cdfb6109e63e9b65e369ac314f60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685309"
---
# <a name="availability-replica-properties-general-page"></a><span data-ttu-id="db028-102">Propriedades de réplica de disponibilidade (página Geral)</span><span class="sxs-lookup"><span data-stu-id="db028-102">Availability Replica Properties (General Page)</span></span>
  <span data-ttu-id="db028-103">Use esta caixa de diálogo para exibir as propriedades de uma réplica de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="db028-103">Use this dialog box to viewthe properties of an availability replica.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="db028-104">Lista de Tarefas</span><span class="sxs-lookup"><span data-stu-id="db028-104">Task List</span></span>  
 <span data-ttu-id="db028-105">**Para exibir as propriedades da réplica de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="db028-105">**To view availability replica properties**</span></span>  
  
-   [<span data-ttu-id="db028-106">Exibir as propriedades da réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="db028-106">View Availability Replica Properties &#40;SQL Server&#41;</span></span>](view-availability-replica-properties-sql-server.md)  
  
-   [<span data-ttu-id="db028-107">Usar o Painel AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="db028-107">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
## <a name="ui-element-list"></a><span data-ttu-id="db028-108">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="db028-108">UI element list</span></span>  
 <span data-ttu-id="db028-109">**Nome do grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="db028-109">**Availability group name**</span></span>  
 <span data-ttu-id="db028-110">O nome do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="db028-110">Name of the availability group.</span></span> <span data-ttu-id="db028-111">Esse é um nome especificado pelo usuário que deve ser exclusivo no WSFC (Windows Server Failover Cluster).</span><span class="sxs-lookup"><span data-stu-id="db028-111">This is a user-specified name that must be unique within the Windows Server Failover Cluster (WSFC).</span></span>  
  
 <span data-ttu-id="db028-112">**Instância de servidor**</span><span class="sxs-lookup"><span data-stu-id="db028-112">**Server instance**</span></span>  
 <span data-ttu-id="db028-113">O nome de servidor da instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que hospeda essa réplica e, para uma instância não padrão, seu nome de instância.</span><span class="sxs-lookup"><span data-stu-id="db028-113">Server name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that is hosting this replica and, for a non-default instance, its instance name.</span></span>  
  
 <span data-ttu-id="db028-114">**Função**</span><span class="sxs-lookup"><span data-stu-id="db028-114">**Role**</span></span>  
 <span data-ttu-id="db028-115">**Primário**</span><span class="sxs-lookup"><span data-stu-id="db028-115">**Primary**</span></span>  
 <span data-ttu-id="db028-116">Atualmente a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="db028-116">Currently the primary replica.</span></span>  
  
 <span data-ttu-id="db028-117">**Secundário**</span><span class="sxs-lookup"><span data-stu-id="db028-117">**Secondary**</span></span>  
 <span data-ttu-id="db028-118">Atualmente uma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="db028-118">Currently a secondary replica.</span></span>  
  
 <span data-ttu-id="db028-119">**Resolvendo**</span><span class="sxs-lookup"><span data-stu-id="db028-119">**Resolving**</span></span>  
 <span data-ttu-id="db028-120">Atualmente, a função de réplica está no processo de ser resolvida para a função primária ou secundária.</span><span class="sxs-lookup"><span data-stu-id="db028-120">Currently the replica role is in the process of being resolved to either the primary or secondary role.</span></span>  
  
 <span data-ttu-id="db028-121">**Modo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="db028-121">**Availability mode**</span></span>  
 <span data-ttu-id="db028-122">O modo de disponibilidade da réplica. Pode ser:</span><span class="sxs-lookup"><span data-stu-id="db028-122">The availability mode of the replica, one of:</span></span>  
  
 <span data-ttu-id="db028-123">**Confirmação assíncrona**</span><span class="sxs-lookup"><span data-stu-id="db028-123">**Asynchronous commit**</span></span>  
 <span data-ttu-id="db028-124">A réplica primária pode confirmar transações sem esperar que a réplica secundária grave o log no disco.</span><span class="sxs-lookup"><span data-stu-id="db028-124">The primary replica can commit transactions without waiting for the secondary to write the log to disk.</span></span>  
  
 <span data-ttu-id="db028-125">**Confirmação síncrona**</span><span class="sxs-lookup"><span data-stu-id="db028-125">**Synchronous commit**</span></span>  
 <span data-ttu-id="db028-126">A réplica primária espera para confirmar uma determinada transação até que a réplica secundária tenha gravado a transação em disco.</span><span class="sxs-lookup"><span data-stu-id="db028-126">The primary replica waits to commit a given transaction until the secondary replica has written the transaction to disk.</span></span>  
  
 <span data-ttu-id="db028-127">Para obter mais informações, consulte [modos de disponibilidade (grupos de disponibilidade AlwaysOn)](availability-modes-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="db028-127">For more information, see [Availability Modes (AlwaysOn Availability Groups)](availability-modes-always-on-availability-groups.md).</span></span>  
  
 <span data-ttu-id="db028-128">**Failover mode**</span><span class="sxs-lookup"><span data-stu-id="db028-128">**Failover mode**</span></span>  
 <span data-ttu-id="db028-129">O modo de failover da réplica, um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="db028-129">The failover mode of the replica, one of:</span></span>  
  
 <span data-ttu-id="db028-130">**Automático**</span><span class="sxs-lookup"><span data-stu-id="db028-130">**Automatic**</span></span>  
 <span data-ttu-id="db028-131">Failover automático.</span><span class="sxs-lookup"><span data-stu-id="db028-131">Automatic failover.</span></span> <span data-ttu-id="db028-132">A réplica é um destino para failovers automáticos.</span><span class="sxs-lookup"><span data-stu-id="db028-132">The replica is a target for automatic failovers.</span></span> <span data-ttu-id="db028-133">Essa opção terá suporte apenas se o modo de disponibilidade estiver definido como confirmação síncrona.</span><span class="sxs-lookup"><span data-stu-id="db028-133">This is supported only if the availability mode is set to synchronous commit.</span></span>  
  
 <span data-ttu-id="db028-134">**Manual**</span><span class="sxs-lookup"><span data-stu-id="db028-134">**Manual**</span></span>  
 <span data-ttu-id="db028-135">Failover manual.</span><span class="sxs-lookup"><span data-stu-id="db028-135">Manual failover.</span></span> <span data-ttu-id="db028-136">O failover da réplica pode ser feito apenas manualmente pelo administrador do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="db028-136">The replica can only be failed over to manually by the database administrator.</span></span>  
  
 <span data-ttu-id="db028-137">**Conexões na função primária**</span><span class="sxs-lookup"><span data-stu-id="db028-137">**Connections in primary role**</span></span>  
 <span data-ttu-id="db028-138">O tipo de conexões de cliente com suporte quando a réplica possui a função primária.</span><span class="sxs-lookup"><span data-stu-id="db028-138">The type of client connections supported when the replica owns the primary role.</span></span>  
  
 <span data-ttu-id="db028-139">**Permitir todas as conexões**</span><span class="sxs-lookup"><span data-stu-id="db028-139">**Allow all connections**</span></span>  
 <span data-ttu-id="db028-140">Todas as conexões são permitidas com os bancos de dados na réplica primária.</span><span class="sxs-lookup"><span data-stu-id="db028-140">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="db028-141">Essa é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="db028-141">This is the default setting.</span></span>  
  
 <span data-ttu-id="db028-142">**Permitir conexões de leitura/gravação**</span><span class="sxs-lookup"><span data-stu-id="db028-142">**Allow read/write connections**</span></span>  
 <span data-ttu-id="db028-143">Conexões em que a propriedade de conexão Application Intent é definida como **ReadOnly** não são permitidas.</span><span class="sxs-lookup"><span data-stu-id="db028-143">Connections where the Application Intent connection property is set to **ReadOnly** are disallowed.</span></span> <span data-ttu-id="db028-144">Quando a propriedade Application Intent está definida como **ReadWrite** ou a propriedade de conexão de intenção de aplicativo não está definida, a conexão é permitida.</span><span class="sxs-lookup"><span data-stu-id="db028-144">When the Application Intent property is set to **ReadWrite** or the application intent connection property is not set, the connection is allowed.</span></span>  
  
 <span data-ttu-id="db028-145">**Secundária Legível**</span><span class="sxs-lookup"><span data-stu-id="db028-145">**Readable Secondary**</span></span>  
 <span data-ttu-id="db028-146">Se uma réplica de disponibilidade que está executando a função primária (isto é, está atuando como uma réplica secundária) pode aceitar conexões de clientes, um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="db028-146">Whether an availability replica that is performing the secondary role (that is, a secondary replica) can accept connections from clients, one of:</span></span>  
  
 <span data-ttu-id="db028-147">**Não**</span><span class="sxs-lookup"><span data-stu-id="db028-147">**No**</span></span>  
 <span data-ttu-id="db028-148">Nenhuma conexão direta é permitida para bancos de dados secundários desta réplica.</span><span class="sxs-lookup"><span data-stu-id="db028-148">No direct connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="db028-149">Eles não estão disponíveis para acesso de leitura.</span><span class="sxs-lookup"><span data-stu-id="db028-149">They are not available for read access.</span></span> <span data-ttu-id="db028-150">Essa é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="db028-150">This is the default setting.</span></span>  
  
 <span data-ttu-id="db028-151">**Tentativa de leitura somente**</span><span class="sxs-lookup"><span data-stu-id="db028-151">**Read-intent only**</span></span>  
 <span data-ttu-id="db028-152">Somente conexões diretas somente leitura são permitidas para bancos de dados secundários desta réplica.</span><span class="sxs-lookup"><span data-stu-id="db028-152">Only direct read-only connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="db028-153">Os bancos de dados secundários estão disponíveis para acesso de leitura.</span><span class="sxs-lookup"><span data-stu-id="db028-153">The secondary database(s) are all available for read access.</span></span>  
  
 <span data-ttu-id="db028-154">**Sim**</span><span class="sxs-lookup"><span data-stu-id="db028-154">**Yes**</span></span>  
 <span data-ttu-id="db028-155">Todas as conexões são permitidas para os bancos de dados secundários desta réplica, mas somente para acesso de leitura.</span><span class="sxs-lookup"><span data-stu-id="db028-155">All connections are allowed to secondary databases of this replica, but only for read access.</span></span> <span data-ttu-id="db028-156">Os bancos de dados secundários estão disponíveis para acesso de leitura.</span><span class="sxs-lookup"><span data-stu-id="db028-156">The secondary database(s) are all available for read access.</span></span>  
  
 <span data-ttu-id="db028-157">Para obter mais informações, consulte secundários [ativos: réplicas secundárias legíveis (grupos de disponibilidade AlwaysOn)](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="db028-157">For more information, see [Active Secondaries: Readable Secondary Replicas (AlwaysOn Availability Groups)](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span></span>  
  
 <span data-ttu-id="db028-158">**Tempo limite da sessão (segundos)**</span><span class="sxs-lookup"><span data-stu-id="db028-158">**Session timeout (seconds)**</span></span>  
 <span data-ttu-id="db028-159">O período de tempo limite, em segundos.</span><span class="sxs-lookup"><span data-stu-id="db028-159">The time-out period, in seconds.</span></span> <span data-ttu-id="db028-160">O período de tempo limite é o tempo máximo que a réplica espera para receber uma mensagem de outra réplica antes de considerar que a conexão entre a réplica primária e secundária falhou.</span><span class="sxs-lookup"><span data-stu-id="db028-160">The time-out period is the maximum time that the replica waits to receive a message from another replica before considering connection between the primary and secondary replica have failed.</span></span> <span data-ttu-id="db028-161">O tempo limite da sessão detecta se réplicas secundárias estão conectadas à réplica primária.</span><span class="sxs-lookup"><span data-stu-id="db028-161">Session timeout detects whether secondaries are connected the primary replica.</span></span> <span data-ttu-id="db028-162">Ao detectar uma falha de conexão com uma réplica secundária, a réplica primária considera a réplica secundária como NOT_SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="db028-162">On detecting a failed connection with a secondary replica, the primary replica considers the secondary replica to be NOT_SYNCHRONIZED.</span></span> <span data-ttu-id="db028-163">Ao detectar uma falha de conexão com a réplica primária, uma réplica secundária simplesmente tenta se conectar outra vez.</span><span class="sxs-lookup"><span data-stu-id="db028-163">On detecting a failed connection with the primary replica, a secondary replica simply attempts to reconnect.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="db028-164">Os tempos limites de sessão não causam failovers automáticos.</span><span class="sxs-lookup"><span data-stu-id="db028-164">Session timeouts do not cause automatic failovers.</span></span>  
  
 <span data-ttu-id="db028-165">**URL do Ponto de Extremidade**</span><span class="sxs-lookup"><span data-stu-id="db028-165">**Endpoint URL**</span></span>  
 <span data-ttu-id="db028-166">Representação de cadeia de caracteres do ponto de extremidade de espelhamento de banco de dados especificado pelo usuário usado pelas conexões entre réplicas primária e secundária para sincronização de dados.</span><span class="sxs-lookup"><span data-stu-id="db028-166">String representation of the user-specified database mirroring endpoint that is used by connections between primary and secondary replicas for data synchronization.</span></span> <span data-ttu-id="db028-167">Para obter informações sobre a sintaxe das URLs de ponto de extremidade, veja [Especificar a URL do ponto de extremidade ao adicionar ou modificar uma réplica de disponibilidade &#40;SQL Server&#41;](specify-endpoint-url-adding-or-modifying-availability-replica.md).</span><span class="sxs-lookup"><span data-stu-id="db028-167">For information about the syntax of endpoint URLs, see [Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;](specify-endpoint-url-adding-or-modifying-availability-replica.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db028-168">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="db028-168">See Also</span></span>  
 [<span data-ttu-id="db028-169">Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="db028-169">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
