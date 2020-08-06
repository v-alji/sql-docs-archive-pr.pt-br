---
title: Propriedades do grupo de disponibilidade e novo grupo de disponibilidade (página Geral) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroupproperties.general.f1
ms.assetid: 9af5379f-91b8-4729-9f75-4a80242a30e9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 876b9d0948b7cd0d01c21b0ec1d64c51a55fa157
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569663"
---
# <a name="availability-group-properties-and-new-availability-group-general-page"></a><span data-ttu-id="153fe-102">Propriedades do Grupo de Disponibilidade e Novo Grupo de Disponibilidade (página geral)</span><span class="sxs-lookup"><span data-stu-id="153fe-102">Availability Group Properties and New Availability Group (General Page)</span></span>
  <span data-ttu-id="153fe-103">Este tópico se aplica à guia **Geral** da caixa de diálogo **Novo Grupo de Disponibilidade** e da caixa de diálogo **Propriedades do Grupo de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="153fe-103">This topic applies to the **General** tab of both the **New Availability Group** dialog box and the **Availability Group Properties** dialog box.</span></span>  <span data-ttu-id="153fe-104">A caixa de diálogo **Novo Grupo de Disponibilidade** permite criar um novo grupo de disponibilidade sem usar o [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)].</span><span class="sxs-lookup"><span data-stu-id="153fe-104">The **New Availability Group** dialog box enables you to create a new availability group without using the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)].</span></span> <span data-ttu-id="153fe-105">A caixa de diálogo **Propriedades do Grupo de Disponibilidade** permite exibir e alterar a configuração de um grupo de disponibilidade existente.</span><span class="sxs-lookup"><span data-stu-id="153fe-105">The **Availability Group Properties** dialog box enables you to view and alter the configuration of an existing availability group.</span></span>  
  
 <span data-ttu-id="153fe-106">**Para exibir as propriedades do grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="153fe-106">**To view availability group properties**</span></span>  
  
-   [<span data-ttu-id="153fe-107">Exibir as propriedades do grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="153fe-107">View Availability Group Properties &#40;SQL Server&#41;</span></span>](view-availability-group-properties-sql-server.md)  
  
-   [<span data-ttu-id="153fe-108">Usar o Painel AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="153fe-108">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
## <a name="ui-element-list"></a><span data-ttu-id="153fe-109">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="153fe-109">UI element list</span></span>  
 <span data-ttu-id="153fe-110">**Nome do grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="153fe-110">**Availability group name**</span></span>  
 <span data-ttu-id="153fe-111">O nome do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="153fe-111">Name of the availability group.</span></span> <span data-ttu-id="153fe-112">Esse é um nome especificado pelo usuário que deve ser exclusivo no WSFC (Windows Server Failover Cluster).</span><span class="sxs-lookup"><span data-stu-id="153fe-112">This is a user-specified name that must be unique within the Windows Server Failover Cluster (WSFC).</span></span>  
  
## <a name="availability-databases"></a><span data-ttu-id="153fe-113">Bancos de dados de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="153fe-113">Availability Databases</span></span>  
 <span data-ttu-id="153fe-114">**Database Name**</span><span class="sxs-lookup"><span data-stu-id="153fe-114">**Database Name**</span></span>  
 <span data-ttu-id="153fe-115">O nome de um banco de dados que foi adicionado ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="153fe-115">Name of a database that has been added to the availability group.</span></span>  
  
 <span data-ttu-id="153fe-116">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="153fe-116">**Add**</span></span>  
 <span data-ttu-id="153fe-117">Clique para adicionar um banco de dados ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="153fe-117">Click to add a database to the availability group.</span></span>  
  
 <span data-ttu-id="153fe-118">**Remover**</span><span class="sxs-lookup"><span data-stu-id="153fe-118">**Remove**</span></span>  
 <span data-ttu-id="153fe-119">Clique para remover um banco de dados selecionado do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="153fe-119">Click to remove a selected database from the availability group.</span></span>  
  
## <a name="availability-replicas"></a><span data-ttu-id="153fe-120">Réplicas de Disponibilidade</span><span class="sxs-lookup"><span data-stu-id="153fe-120">Availability Replicas</span></span>  
 <span data-ttu-id="153fe-121">**Instância de servidor**</span><span class="sxs-lookup"><span data-stu-id="153fe-121">**Server instance**</span></span>  
 <span data-ttu-id="153fe-122">O nome de servidor da instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que hospeda essa réplica e, para uma instância não padrão, seu nome de instância.</span><span class="sxs-lookup"><span data-stu-id="153fe-122">Server name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that is hosting this replica and, for a non-default instance, its instance name.</span></span>  
  
 <span data-ttu-id="153fe-123">**Função**</span><span class="sxs-lookup"><span data-stu-id="153fe-123">**Role**</span></span>  
 <span data-ttu-id="153fe-124">**Primário**</span><span class="sxs-lookup"><span data-stu-id="153fe-124">**Primary**</span></span>  
 <span data-ttu-id="153fe-125">Atualmente a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="153fe-125">Currently the primary replica.</span></span>  
  
 <span data-ttu-id="153fe-126">**Secundário**</span><span class="sxs-lookup"><span data-stu-id="153fe-126">**Secondary**</span></span>  
 <span data-ttu-id="153fe-127">Atualmente uma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="153fe-127">Currently a secondary replica.</span></span>  
  
 <span data-ttu-id="153fe-128">**Resolvendo**</span><span class="sxs-lookup"><span data-stu-id="153fe-128">**Resolving**</span></span>  
 <span data-ttu-id="153fe-129">Atualmente, a função de réplica está no processo de ser resolvida para a função primária ou secundária.</span><span class="sxs-lookup"><span data-stu-id="153fe-129">Currently the replica role is in the process of being resolved to either the primary or secondary role.</span></span>  
  
 <span data-ttu-id="153fe-130">**Modo de Disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="153fe-130">**Availability Mode**</span></span>  
 <span data-ttu-id="153fe-131">O modo de disponibilidade da réplica. Pode ser:</span><span class="sxs-lookup"><span data-stu-id="153fe-131">The availability mode of the replica, one of:</span></span>  
  
 <span data-ttu-id="153fe-132">**Confirmação assíncrona**</span><span class="sxs-lookup"><span data-stu-id="153fe-132">**Asynchronous commit**</span></span>  
 <span data-ttu-id="153fe-133">A réplica primária pode confirmar transações sem esperar que a réplica secundária grave o log no disco.</span><span class="sxs-lookup"><span data-stu-id="153fe-133">The primary replica can commit transactions without waiting for the secondary to write the log to disk.</span></span>  
  
 <span data-ttu-id="153fe-134">**Confirmação síncrona**</span><span class="sxs-lookup"><span data-stu-id="153fe-134">**Synchronous commit**</span></span>  
 <span data-ttu-id="153fe-135">A réplica primária espera para confirmar uma determinada transação até que a réplica secundária tenha gravado a transação em disco.</span><span class="sxs-lookup"><span data-stu-id="153fe-135">The primary replica waits to commit a given transaction until the secondary replica has written the transaction to disk.</span></span>  
  
 <span data-ttu-id="153fe-136">Para obter mais informações, consulte [modos de disponibilidade (grupos de disponibilidade AlwaysOn)](availability-modes-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="153fe-136">For more information, see [Availability Modes (AlwaysOn Availability Groups)](availability-modes-always-on-availability-groups.md).</span></span>  
  
 <span data-ttu-id="153fe-137">**Modo de Failover**</span><span class="sxs-lookup"><span data-stu-id="153fe-137">**Failover Mode**</span></span>  
 <span data-ttu-id="153fe-138">O modo de failover da réplica, um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="153fe-138">The failover mode of the replica, one of:</span></span>  
  
 <span data-ttu-id="153fe-139">**Automático**</span><span class="sxs-lookup"><span data-stu-id="153fe-139">**Automatic**</span></span>  
 <span data-ttu-id="153fe-140">Failover automático.</span><span class="sxs-lookup"><span data-stu-id="153fe-140">Automatic failover.</span></span> <span data-ttu-id="153fe-141">A réplica é um destino para failovers automáticos.</span><span class="sxs-lookup"><span data-stu-id="153fe-141">The replica is a target for automatic failovers.</span></span> <span data-ttu-id="153fe-142">Essa opção terá suporte apenas se o modo de disponibilidade estiver definido como confirmação síncrona.</span><span class="sxs-lookup"><span data-stu-id="153fe-142">This is supported only if the availability mode is set to synchronous commit.</span></span>  
  
 <span data-ttu-id="153fe-143">**Manual**</span><span class="sxs-lookup"><span data-stu-id="153fe-143">**Manual**</span></span>  
 <span data-ttu-id="153fe-144">Failover manual.</span><span class="sxs-lookup"><span data-stu-id="153fe-144">Manual failover.</span></span> <span data-ttu-id="153fe-145">O failover da réplica pode ser feito apenas manualmente pelo administrador do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="153fe-145">The replica can only be failed over to manually by the database administrator.</span></span>  
  
 <span data-ttu-id="153fe-146">**Conexões na Função Primária**</span><span class="sxs-lookup"><span data-stu-id="153fe-146">**Connections in Primary Role**</span></span>  
 <span data-ttu-id="153fe-147">O tipo de conexões de cliente com suporte quando a réplica possui a função primária.</span><span class="sxs-lookup"><span data-stu-id="153fe-147">The type of client connections supported when the replica owns the primary role.</span></span>  
  
 <span data-ttu-id="153fe-148">**Permitir todas as conexões**</span><span class="sxs-lookup"><span data-stu-id="153fe-148">**Allow all connections**</span></span>  
 <span data-ttu-id="153fe-149">Todas as conexões são permitidas com os bancos de dados na réplica primária.</span><span class="sxs-lookup"><span data-stu-id="153fe-149">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="153fe-150">Essa é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="153fe-150">This is the default setting.</span></span>  
  
 <span data-ttu-id="153fe-151">**Permitir conexões de leitura/gravação**</span><span class="sxs-lookup"><span data-stu-id="153fe-151">**Allow read/write connections**</span></span>  
 <span data-ttu-id="153fe-152">Conexões em que a propriedade de conexão Application Intent é definida como **ReadOnly** não são permitidas.</span><span class="sxs-lookup"><span data-stu-id="153fe-152">Connections where the Application Intent connection property is set to **ReadOnly** are disallowed.</span></span> <span data-ttu-id="153fe-153">Quando a propriedade Application Intent está definida como **ReadWrite** ou não está definida, a conexão é permitida.</span><span class="sxs-lookup"><span data-stu-id="153fe-153">When the Application Intent property is set to **ReadWrite** or the Application Intent connection property is not set, the connection is allowed.</span></span> <span data-ttu-id="153fe-154">Para obter mais informações sobre a propriedade de conexão Tentativa de Aplicativo, consulte [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="153fe-154">For more information about Application Intent connection property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
 <span data-ttu-id="153fe-155">**Secundária Legível**</span><span class="sxs-lookup"><span data-stu-id="153fe-155">**Readable Secondary**</span></span>  
 <span data-ttu-id="153fe-156">Se uma réplica de disponibilidade que está executando a função primária (isto é, está atuando como uma réplica secundária) pode aceitar conexões de clientes, um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="153fe-156">Whether an availability replica that is performing the secondary role (that is, a secondary replica) can accept connections from clients, one of:</span></span>  
  
 <span data-ttu-id="153fe-157">**Não**</span><span class="sxs-lookup"><span data-stu-id="153fe-157">**No**</span></span>  
 <span data-ttu-id="153fe-158">Nenhuma conexão direta é permitida para bancos de dados secundários desta réplica.</span><span class="sxs-lookup"><span data-stu-id="153fe-158">No direct connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="153fe-159">Eles não estão disponíveis para acesso de leitura.</span><span class="sxs-lookup"><span data-stu-id="153fe-159">They are not available for read access.</span></span> <span data-ttu-id="153fe-160">Essa é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="153fe-160">This is the default setting.</span></span>  
  
 <span data-ttu-id="153fe-161">**Tentativa de leitura somente**</span><span class="sxs-lookup"><span data-stu-id="153fe-161">**Read-intent only**</span></span>  
 <span data-ttu-id="153fe-162">Somente conexões diretas somente leitura são permitidas para bancos de dados secundários desta réplica.</span><span class="sxs-lookup"><span data-stu-id="153fe-162">Only direct read-only connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="153fe-163">Os bancos de dados secundários estão disponíveis para acesso de leitura.</span><span class="sxs-lookup"><span data-stu-id="153fe-163">The secondary database(s) are all available for read access.</span></span>  
  
 <span data-ttu-id="153fe-164">**Sim**</span><span class="sxs-lookup"><span data-stu-id="153fe-164">**Yes**</span></span>  
 <span data-ttu-id="153fe-165">Todas as conexões são permitidas para os bancos de dados secundários desta réplica, mas somente para acesso de leitura.</span><span class="sxs-lookup"><span data-stu-id="153fe-165">All connections are allowed to secondary databases of this replica, but only for read access.</span></span> <span data-ttu-id="153fe-166">Os bancos de dados secundários estão disponíveis para acesso de leitura.</span><span class="sxs-lookup"><span data-stu-id="153fe-166">The secondary database(s) are all available for read access.</span></span>  
  
 <span data-ttu-id="153fe-167">**Tempo Limite da Sessão (segundos)**</span><span class="sxs-lookup"><span data-stu-id="153fe-167">**Session Timeout (seconds)**</span></span>  
 <span data-ttu-id="153fe-168">O número de segundos do período de tempo limite de sessão nesta réplica.</span><span class="sxs-lookup"><span data-stu-id="153fe-168">The number of seconds for the session-timeout period on this replica.</span></span>  
  
 <span data-ttu-id="153fe-169">**URL do Ponto de Extremidade**</span><span class="sxs-lookup"><span data-stu-id="153fe-169">**Endpoint URL**</span></span>  
 <span data-ttu-id="153fe-170">A URL do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="153fe-170">The URL of the endpoint.</span></span> <span data-ttu-id="153fe-171">Para obter informações sobre o formato dessas URLs, veja [Especificar a URL do ponto de extremidade ao adicionar ou modificar uma réplica de disponibilidade &#40;SQL Server&#41;](specify-endpoint-url-adding-or-modifying-availability-replica.md).</span><span class="sxs-lookup"><span data-stu-id="153fe-171">For information the format of these URLs, see [Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;](specify-endpoint-url-adding-or-modifying-availability-replica.md).</span></span>  
  
 <span data-ttu-id="153fe-172">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="153fe-172">**Add**</span></span>  
 <span data-ttu-id="153fe-173">Clique para adicionar uma réplica secundária ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="153fe-173">Click to add a secondary replica to the availability group.</span></span>  
  
 <span data-ttu-id="153fe-174">**Remover**</span><span class="sxs-lookup"><span data-stu-id="153fe-174">**Remove**</span></span>  
 <span data-ttu-id="153fe-175">Clique para remover uma réplica secundária especificada do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="153fe-175">Click to remove a secondary replica from the availability group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="153fe-176">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="153fe-176">See Also</span></span>  
 [<span data-ttu-id="153fe-177">Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="153fe-177">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
