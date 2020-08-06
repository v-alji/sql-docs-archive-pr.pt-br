---
title: Alterar o contexto do cluster HADR da instância de servidor (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], WSFC clusters
- Availability replicas [SQL Server], change WSFC cluster context
ms.assetid: ecd99f91-b9a2-4737-994e-507065a12f80
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cbc29fa2ebaaf2bbc9e577b5bd303e8a0dd0ec4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685304"
---
# <a name="change-the-hadr-cluster-context-of-server-instance-sql-server"></a><span data-ttu-id="60b30-102">Alterar o contexto do cluster HADR da instância de servidor (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="60b30-102">Change the HADR Cluster Context of Server Instance (SQL Server)</span></span>
  <span data-ttu-id="60b30-103">Este tópico descreve como alternar o contexto do cluster HADR de uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usando [!INCLUDE[tsql](../../../includes/tsql-md.md)] no [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] e em versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="60b30-103">This topic describes how to switch the HADR cluster context of an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)] in [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] and later versions.</span></span> <span data-ttu-id="60b30-104">O *contexto do cluster HADR* determina qual cluster do WSFC (Clustering de Failover de Windows Server) gerencia os metadados das réplicas de disponibilidade hospedadas pela instância de servidor.</span><span class="sxs-lookup"><span data-stu-id="60b30-104">The *HADR cluster context* determines which Windows Server Failover Clustering (WSFC) cluster manages the metadata for availability replicas hosted by the server instance.</span></span>  
  
 <span data-ttu-id="60b30-105">Alterne o contexto do cluster HADR somente durante uma migração entre clusters de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] para uma instância do [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] em um novo cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="60b30-105">Switch the HADR cluster context only during a cross-cluster migration of [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] to an instance of [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] on a new WSFC cluster.</span></span> <span data-ttu-id="60b30-106">A migração entre clusters de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] oferece suporte à atualização do sistema operacional para o [!INCLUDE[win8](../../../includes/win8-md.md)] ou o [!INCLUDE[win8srv](../../../includes/win8srv-md.md)] com tempo de inatividade mínimo de grupos de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="60b30-106">Cross-cluster migration of [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] supports OS upgrade to [!INCLUDE[win8](../../../includes/win8-md.md)] or [!INCLUDE[win8srv](../../../includes/win8srv-md.md)] with minimal downtime of availability groups.</span></span> <span data-ttu-id="60b30-107">Para obter mais informações, consulte [Migração entre clusters de grupos de disponibilidade AlwaysOn para atualização do sistema operacional](https://msdn.microsoft.com/library/jj873730.aspx).</span><span class="sxs-lookup"><span data-stu-id="60b30-107">For more information, see [Cross-Cluster Migration of AlwaysOn Availability Groups for OS Upgrade](https://msdn.microsoft.com/library/jj873730.aspx).</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="60b30-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="60b30-108">Before You Begin</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="60b30-109">Alterne o contexto do cluster HADR somente durante a migração entre clusters das implantações de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="60b30-109">Switch the HADR cluster context only during cross-cluster migration of [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] deployments.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="60b30-110">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="60b30-110">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="60b30-111">Só é possível alternar o contexto do cluster HADR do cluster WSFC local para um cluster remoto e, depois, do cluster remoto para o cluster local.</span><span class="sxs-lookup"><span data-stu-id="60b30-111">You can switch the HADR cluster context only from the local WSFC cluster to a remote cluster and then back from the remote cluster to the local cluster.</span></span> <span data-ttu-id="60b30-112">Você não pode alternar o contexto do cluster HADR de um cluster remoto para outro cluster remoto.</span><span class="sxs-lookup"><span data-stu-id="60b30-112">You cannot switch the HADR cluster context from one remote cluster to another remote cluster.</span></span>  
  
-   <span data-ttu-id="60b30-113">O contexto do cluster HADR pode ser alternado para um cluster remoto somente quando a instância do SQL Server não está hospedando réplicas de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="60b30-113">The HADR cluster context can be switched to a remote cluster only when the instance of SQL Server is not hosting any availability replicas.</span></span>  
  
-   <span data-ttu-id="60b30-114">Um contexto do cluster HADR remoto pode ser alternado novamente para o cluster local a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="60b30-114">A remote HADR cluster context can be switched back to the local cluster at any time.</span></span> <span data-ttu-id="60b30-115">Entretanto, o contexto não poderá ser alternado novamente enquanto a instância de servidor estiver hospedando réplicas de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="60b30-115">However, the context cannot be switched again as long as the server instance is hosting any availability replicas.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="60b30-116">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="60b30-116">Prerequisites</span></span>  
  
-   <span data-ttu-id="60b30-117">A instância de servidor na qual você altera o contexto do cluster HADR deve executar o [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] ou posterior (edição Enterprise ou superior).</span><span class="sxs-lookup"><span data-stu-id="60b30-117">The server instance on which you change the HADR cluster context must be running [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] or above (Enterprise edition or above).</span></span>  
  
-   <span data-ttu-id="60b30-118">A instância de servidor deve estar habilitada para AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="60b30-118">The server instance must be enabled for AlwaysOn.</span></span> <span data-ttu-id="60b30-119">Para obter mais informações, veja [Habilitar e desabilitar Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](enable-and-disable-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="60b30-119">For more information, see [Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;](enable-and-disable-always-on-availability-groups-sql-server.md).</span></span>  
  
-   <span data-ttu-id="60b30-120">Para qualificar-se para ser alternada do contexto de cluster local para um cluster remoto, uma instância de servidor não pode hospedar réplicas de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="60b30-120">To be eligible to be switched from the local cluster context to a remote cluster cluster, a server instance cannot be hosting any availability replicas.</span></span> <span data-ttu-id="60b30-121">A exibição de catálogo [sys.availability_replicas](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql) não deve retornar linhas.</span><span class="sxs-lookup"><span data-stu-id="60b30-121">The [sys.availability_replicas](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql) catalog view should not return any rows.</span></span>  
  
     <span data-ttu-id="60b30-122">Se existirem réplicas de disponibilidade na instância do servidor, antes de alterar o contexto do cluster HADR, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="60b30-122">If any availability replicas exist on the server instance, before you can change the HADR cluster context, you must do one of the following:</span></span>  
  
    |<span data-ttu-id="60b30-123">Função da Réplica</span><span class="sxs-lookup"><span data-stu-id="60b30-123">Replica Role</span></span>|<span data-ttu-id="60b30-124">Ação</span><span class="sxs-lookup"><span data-stu-id="60b30-124">Action</span></span>|<span data-ttu-id="60b30-125">Link</span><span class="sxs-lookup"><span data-stu-id="60b30-125">Link</span></span>|  
    |------------------|------------|----------|  
    |<span data-ttu-id="60b30-126">Primária</span><span class="sxs-lookup"><span data-stu-id="60b30-126">Primary</span></span>|<span data-ttu-id="60b30-127">Colocar o grupo de disponibilidade offline.</span><span class="sxs-lookup"><span data-stu-id="60b30-127">Take the availability group offline.</span></span>|[<span data-ttu-id="60b30-128">Colocar um grupo de disponibilidade offline &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="60b30-128">Take an Availability Group Offline &#40;SQL Server&#41;</span></span>](../../take-an-availability-group-offline-sql-server.md)|  
    |<span data-ttu-id="60b30-129">Secundário</span><span class="sxs-lookup"><span data-stu-id="60b30-129">Secondary</span></span>|<span data-ttu-id="60b30-130">Remover a réplica de seu grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="60b30-130">Remove the replica from its availability group</span></span>|[<span data-ttu-id="60b30-131">Remover uma réplica secundária de um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="60b30-131">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)|  
  
-   <span data-ttu-id="60b30-132">Antes de alternar de um cluster remoto para o cluster local, verifique se todas as réplicas de confirmação síncrona foram sincronizadas (SYNCHRONIZED).</span><span class="sxs-lookup"><span data-stu-id="60b30-132">Before you can switch from a remote cluster to the local cluster, all synchronous-commit replicas must be SYNCHRONIZED.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="60b30-133">Recomendações</span><span class="sxs-lookup"><span data-stu-id="60b30-133">Recommendations</span></span>  
  
-   <span data-ttu-id="60b30-134">É recomendável especificar o nome de domínio completo.</span><span class="sxs-lookup"><span data-stu-id="60b30-134">We recommend that you specify the full domain name.</span></span> <span data-ttu-id="60b30-135">Isso é necessário porque, para localizar o endereço IP de destino de um nome curto, ALTER SERVER CONFIGURATION usa a resolução DNS.</span><span class="sxs-lookup"><span data-stu-id="60b30-135">This is because to find the target IP address of a short name, ALTER SERVER CONFIGURATION uses DNS resolution.</span></span> <span data-ttu-id="60b30-136">Em algumas situações, dependendo da ordem de pesquisa de DNS, o uso de um nome curto pode gerar confusão.</span><span class="sxs-lookup"><span data-stu-id="60b30-136">Under some situations, depending on the DNS searching order, using a short name could cause confusion.</span></span> <span data-ttu-id="60b30-137">Por exemplo, considere o comando a seguir, que é executado em um nó no domínio `abc` , (`node1.abc.com`).</span><span class="sxs-lookup"><span data-stu-id="60b30-137">For example, consider the following command, which is executed on a node in the `abc` domain, (`node1.abc.com`).</span></span> <span data-ttu-id="60b30-138">O cluster de destino pretendido é o cluster `CLUS01` no domínio `xyz` (`clus01.xyz.com`).</span><span class="sxs-lookup"><span data-stu-id="60b30-138">The intended destination cluster is the `CLUS01` cluster in the `xyz` domain (`clus01.xyz.com`).</span></span> <span data-ttu-id="60b30-139">No entanto, o domínio local também hospeda um cluster denominado `CLUS01` (`clus01.abc.com`).</span><span class="sxs-lookup"><span data-stu-id="60b30-139">However, the local  domain hosts also hosts a cluster named `CLUS01` (`clus01.abc.com`).</span></span>  
  
     <span data-ttu-id="60b30-140">Se o nome curto do cluster de destino, `CLUS01`, foi especificado, a resolução de nome DNS pode retornar o endereço IP do cluster incorreto, `clus01.abc.com`.</span><span class="sxs-lookup"><span data-stu-id="60b30-140">If the short name of the target cluster, `CLUS01`, were specified, DNS name resolution could return the IP address of the wrong cluster, `clus01.abc.com`.</span></span> <span data-ttu-id="60b30-141">Para evitar essa confusão, especifique o nome completo do cluster de destino, como no seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="60b30-141">To avoid such confusion, specify the full name of the target cluster, as in the following example:</span></span>  
  
    ```  
    ALTER SERVER CONFIGURATION SET HADR CLUSTER CONTEXT = 'clus01.xyz.com'  
    ```  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="60b30-142">Segurança</span><span class="sxs-lookup"><span data-stu-id="60b30-142">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="60b30-143">Permissões</span><span class="sxs-lookup"><span data-stu-id="60b30-143">Permissions</span></span>  
  
-   <span data-ttu-id="60b30-144">**logon do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="60b30-144">**SQL Server login**</span></span>  
  
     <span data-ttu-id="60b30-145">Requer a permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="60b30-145">Requires CONTROL SERVER permission.</span></span>  
  
-   <span data-ttu-id="60b30-146">**SQL Server conta de serviço**</span><span class="sxs-lookup"><span data-stu-id="60b30-146">**SQL Server service account**</span></span>  
  
     <span data-ttu-id="60b30-147">A conta do serviço [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] da instância de servidor deve ter:</span><span class="sxs-lookup"><span data-stu-id="60b30-147">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service account of the server instance must have:</span></span>  
  
    -   <span data-ttu-id="60b30-148">Permissão para abrir o cluster WSFC de destino.</span><span class="sxs-lookup"><span data-stu-id="60b30-148">Permission to open the destination WSFC cluster.</span></span>  
  
    -   <span data-ttu-id="60b30-149">Acesso de leitura/gravação no WSFC remoto.</span><span class="sxs-lookup"><span data-stu-id="60b30-149">Remote WSFC read-write access.</span></span>  
  
 
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="60b30-150">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="60b30-150">Using Transact-SQL</span></span>  
 <span data-ttu-id="60b30-151">**Para alterar o contexto do cluster WSFC de uma réplica de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="60b30-151">**To change the WSFC cluster context of an availability replica**</span></span>  
  
1.  <span data-ttu-id="60b30-152">Conecte-se à instância de servidor que hospeda a réplica primária ou uma réplica secundária do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="60b30-152">Connect to the server instance that hosts either the primary replica or a secondary replica of the availability group.</span></span>  
  
2.  <span data-ttu-id="60b30-153">Use a cláusula SET HADR CLUSTER CONTEXT da instrução [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql) , da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="60b30-153">Use the SET HADR CLUSTER CONTEXT clause of the [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="60b30-154">ALTERAR o contexto do CLUSTER HADR do conjunto de configurações do servidor **=** { **' *`windows_cluster`* '** | LOCAL</span><span class="sxs-lookup"><span data-stu-id="60b30-154">ALTER SERVER CONFIGURATION SET HADR CLUSTER CONTEXT **=** { **'*`windows_cluster`*'** | LOCAL }</span></span>  
  
     <span data-ttu-id="60b30-155">onde:</span><span class="sxs-lookup"><span data-stu-id="60b30-155">where,</span></span>  
  
     <span data-ttu-id="60b30-156">*cluster_windows*</span><span class="sxs-lookup"><span data-stu-id="60b30-156">*windows_cluster*</span></span>  
     <span data-ttu-id="60b30-157">O CON (nome do objeto de cluster) de um cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="60b30-157">The cluster object name (CON) of a WSFC cluster.</span></span> <span data-ttu-id="60b30-158">Você pode especificar o nome curto ou o nome de domínio completo.</span><span class="sxs-lookup"><span data-stu-id="60b30-158">You can specify either the short name or the full domain name.</span></span> <span data-ttu-id="60b30-159">É recomendável especificar o nome de domínio completo.</span><span class="sxs-lookup"><span data-stu-id="60b30-159">We recommend that you specify the full domain name.</span></span> <span data-ttu-id="60b30-160">Para obter mais informações, consulte [recomendações](#Recommendations), anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="60b30-160">For more information, see [Recommendations](#Recommendations), earlier in this topic.</span></span>  
  
     <span data-ttu-id="60b30-161">LOCAL</span><span class="sxs-lookup"><span data-stu-id="60b30-161">LOCAL</span></span>  
     <span data-ttu-id="60b30-162">O cluster WSFC local.</span><span class="sxs-lookup"><span data-stu-id="60b30-162">The local WSFC cluster.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="60b30-163">Exemplos</span><span class="sxs-lookup"><span data-stu-id="60b30-163">Examples</span></span>  
 <span data-ttu-id="60b30-164">O exemplo a seguir altera o contexto do cluster HADR para um cluster diferente.</span><span class="sxs-lookup"><span data-stu-id="60b30-164">The following example changes the HADR cluster context to a different cluster.</span></span> <span data-ttu-id="60b30-165">Para identificar o cluster WSFC de destino, `clus01`, o exemplo especifica o nome de objeto completo do cluster, `clus01.xyz.com`.</span><span class="sxs-lookup"><span data-stu-id="60b30-165">To identify the destination WSFC cluster, `clus01`, the example specifies the full cluster object name, `clus01.xyz.com`.</span></span>  
  
```  
ALTER SERVER CONFIGURATION SET HADR CLUSTER CONTEXT = 'clus01.xyz.com';  
```  
  
 <span data-ttu-id="60b30-166">O exemplo a seguir altera o contexto do cluster HADR para o cluster WSFC local.</span><span class="sxs-lookup"><span data-stu-id="60b30-166">The following example changes the HADR cluster context to the local WSFC cluster.</span></span>  
  
```  
ALTER SERVER CONFIGURATION SET HADR CLUSTER CONTEXT = LOCAL;  
```  
  

  
##  <a name="follow-up-after-switching-the-cluster-context-of-an-availability-replica"></a><a name="FollowUp"></a> <span data-ttu-id="60b30-167">Acompanhamento: depois de alternar o contexto do cluster de uma réplica de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="60b30-167">Follow Up: After Switching the Cluster Context of an Availability Replica</span></span>  
 <span data-ttu-id="60b30-168">O novo contexto do cluster HADR tem efeito imediatamente, sem a reinicialização da instância de servidor.</span><span class="sxs-lookup"><span data-stu-id="60b30-168">The new HADR cluster context takes effect immediately, without restarting the server instance.</span></span> <span data-ttu-id="60b30-169">A configuração de contexto do cluster HADR é uma configuração persistente em nível de instância que permanece inalterada se a instância de servidor é reiniciada.</span><span class="sxs-lookup"><span data-stu-id="60b30-169">The HADR cluster context setting is a persistent instance-level setting that remains unchanged if the server instance restarts.</span></span>  
  
 <span data-ttu-id="60b30-170">Confirme o novo contexto do cluster HADR consultando a exibição de gerenciamento dinâmico [sys.dm_hadr_cluster](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-transact-sql) , da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="60b30-170">Confirm the new HADR cluster context by querying the [sys.dm_hadr_cluster](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-transact-sql) dynamic management view, as follows:</span></span>  
  
```  
SELECT cluster_name FROM sys.dm_hadr_cluster  
```  
  
 <span data-ttu-id="60b30-171">Essa consulta deve retornar o nome do cluster para o qual você define o contexto do cluster HADR.</span><span class="sxs-lookup"><span data-stu-id="60b30-171">This query should return the name of the cluster to which you set the HADR cluster context.</span></span>  
  
 <span data-ttu-id="60b30-172">Quando o contexto do cluster HADR é alternado para um novo cluster:</span><span class="sxs-lookup"><span data-stu-id="60b30-172">When the HADR cluster context is switched to a new cluster:</span></span>  
  
-   <span data-ttu-id="60b30-173">Os metadados são limpos para todas as réplicas de disponibilidade hospedadas no momento pela instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60b30-173">The metadata is cleaned up for any availability replicas that are currently hosted by the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="60b30-174">Todos os bancos de dados que antes pertenciam a uma réplica de disponibilidade agora se encontram no estado RESTORING.</span><span class="sxs-lookup"><span data-stu-id="60b30-174">All the databases that previously belonged to an availability replica are now in the RESTORING state.</span></span>  
  
 
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="60b30-175">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="60b30-175">Related Tasks</span></span>  
  
-   [<span data-ttu-id="60b30-176">Remover um ouvinte do grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="60b30-176">Remove an Availability Group Listener &#40;SQL Server&#41;</span></span>](remove-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="60b30-177">Colocar um grupo de disponibilidade offline &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="60b30-177">Take an Availability Group Offline &#40;SQL Server&#41;</span></span>](../../take-an-availability-group-offline-sql-server.md)  
  
-   [<span data-ttu-id="60b30-178">Adicionar uma réplica secundária a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="60b30-178">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="60b30-179">Remover uma réplica secundária de um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="60b30-179">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="60b30-180">Criar ou configurar um ouvinte do grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="60b30-180">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="60b30-181">Unir um banco de dados secundário a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="60b30-181">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
 
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="60b30-182">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="60b30-182">Related Content</span></span>  
  
-   <span data-ttu-id="60b30-183">[Artigos técnicos do SQL Server 2012](https://msdn.microsoft.com/library/bb418445\(SQL.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="60b30-183">[SQL Server 2012 Technical Articles](https://msdn.microsoft.com/library/bb418445\(SQL.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="60b30-184">Blog da equipe do AlwaysOn do SQL Server: blog oficial da equipe do SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="60b30-184">SQL Server AlwaysOn Team Blog: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
  
  
## <a name="see-also"></a><span data-ttu-id="60b30-185">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="60b30-185">See Also</span></span>  
 <span data-ttu-id="60b30-186">[Grupos de disponibilidade AlwaysOn (SQL Server)](always-on-availability-groups-sql-server.md) [Windows Server Failover clustering &#40;&#41; WSFC com SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="60b30-186">[AlwaysOn Availability Groups (SQL Server)](always-on-availability-groups-sql-server.md) [Windows Server Failover Clustering &#40;WSFC&#41; with SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md) </span></span>  
 [<span data-ttu-id="60b30-187">ALTER SERVER CONFIGURATION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="60b30-187">ALTER SERVER CONFIGURATION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-server-configuration-transact-sql)  
  
  
