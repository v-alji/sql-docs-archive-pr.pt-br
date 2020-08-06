---
title: Alterar grupo de disponibilidade offline
description: Etapas para definir seu grupo de disponibilidade Always On offline
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], take offline
ms.assetid: 50f5aad8-0dff-45ef-8350-f9596d3db898
author: rothja
ms.author: jroth
ms.openlocfilehash: db2f56befe6905b9c3de6bd1ab6a2e5a4a00b1b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574881"
---
# <a name="take-an-availability-group-offline-sql-server"></a><span data-ttu-id="14ee6-103">Colocar um grupo de disponibilidade offline (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="14ee6-103">Take an Availability Group Offline (SQL Server)</span></span>
  <span data-ttu-id="14ee6-104">Este tópico descreve como passar um grupo de disponibilidade AlwaysOn do estado ONLINE para o estado OFFLINE usando o [!INCLUDE[tsql](../includes/tsql-md.md)] no [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)] e em versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="14ee6-104">This topic describes how to take an AlwaysOn availability group from the ONLINE state to the OFFLINE state by using [!INCLUDE[tsql](../includes/tsql-md.md)] in [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)] and later versions.</span></span> <span data-ttu-id="14ee6-105">Não há perda de dados para bancos de dados de confirmação síncrona, pois, se alguma réplica de confirmação síncrona não é sincronizada, a operação OFFLINE gera um erro e deixa o grupo de disponibilidade ONLINE.</span><span class="sxs-lookup"><span data-stu-id="14ee6-105">There is no data loss for synchronous-commit databases because if any synchronous-commit replica is not synchronized, the OFFLINE operation raises an error and leaves the availability group ONLINE.</span></span> <span data-ttu-id="14ee6-106">Quando o grupo de disponibilidade permanece online, isso protege bancos de dados de confirmação síncrona não sincronizados contra possível perda de dados.</span><span class="sxs-lookup"><span data-stu-id="14ee6-106">Keeping the availability group online protects unsynchronized synchronous-commit databases from possible data loss.</span></span> <span data-ttu-id="14ee6-107">Depois que um grupo de disponibilidade se torna offline, seus bancos de dados ficam indisponíveis para os clientes e você não pode recolocar o grupo de disponibilidade online.</span><span class="sxs-lookup"><span data-stu-id="14ee6-107">After an availability group goes offline, its databases become unavailable to clients and you cannot bring the availability group back online.</span></span> <span data-ttu-id="14ee6-108">Portanto, coloque um grupo de disponibilidade offline somente para migrar os recursos do grupo de disponibilidade de um cluster WSFC para outro.</span><span class="sxs-lookup"><span data-stu-id="14ee6-108">Therefore, take an availability group offline only to migrate the availability group resources from one WSFC cluster to another.</span></span>  
  
 <span data-ttu-id="14ee6-109">Durante uma migração entre clusters de [!INCLUDE[ssHADR](../includes/sshadr-md.md)], se algum aplicativo se conectar diretamente à réplica primária de um grupo de disponibilidade, o grupo de disponibilidade deverá ser colocado offline.</span><span class="sxs-lookup"><span data-stu-id="14ee6-109">During a cross-cluster migration of [!INCLUDE[ssHADR](../includes/sshadr-md.md)], if any applications connect directly to the primary replica of an availability group, the availability group must be taken offline.</span></span> <span data-ttu-id="14ee6-110">A migração entre clusters de [!INCLUDE[ssHADR](../includes/sshadr-md.md)] dá suporte à atualização do sistema operacional com tempo de inatividade mínimo de grupos de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="14ee6-110">Cross-cluster migration of [!INCLUDE[ssHADR](../includes/sshadr-md.md)] supports OS upgrade with minimal downtime of availability groups.</span></span> <span data-ttu-id="14ee6-111">O cenário típico é usar a migração entre clusters de [!INCLUDE[ssHADR](../includes/sshadr-md.md)] para a atualização do sistema operacional para [!INCLUDE[win8](../includes/win8-md.md)] ou para o [!INCLUDE[win8srv](../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14ee6-111">The typical scenario is to use cross-cluster migration of [!INCLUDE[ssHADR](../includes/sshadr-md.md)] for OS upgrade to [!INCLUDE[win8](../includes/win8-md.md)] or [!INCLUDE[win8srv](../includes/win8srv-md.md)].</span></span> <span data-ttu-id="14ee6-112">Para obter mais informações, consulte [Migração entre clusters de grupos de disponibilidade AlwaysOn para atualização do sistema operacional](https://msdn.microsoft.com/library/jj873730.aspx).</span><span class="sxs-lookup"><span data-stu-id="14ee6-112">For more information, see [Cross-Cluster Migration of AlwaysOn Availability Groups for OS Upgrade](https://msdn.microsoft.com/library/jj873730.aspx).</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="14ee6-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="14ee6-113">Before You Begin</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="14ee6-114">Use a opção OFFLINE apenas para uma migração entre clusters de recursos do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="14ee6-114">Use the OFFLINE option only for a cross-cluster migration of availability group resources.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="14ee6-115">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="14ee6-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="14ee6-116">A instância de servidor na qual você insere o comando OFFLINE deve executar o [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)] ou posterior (edição Enterprise ou superior).</span><span class="sxs-lookup"><span data-stu-id="14ee6-116">The server instance on which you enter the OFFLINE command must be running [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)] or above (Enterprise edition or above).</span></span>  
  
-   <span data-ttu-id="14ee6-117">O grupo de disponibilidade deve estar online no momento.</span><span class="sxs-lookup"><span data-stu-id="14ee6-117">The availability group must currently be online.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="14ee6-118">Recomendações</span><span class="sxs-lookup"><span data-stu-id="14ee6-118">Recommendations</span></span>  
 <span data-ttu-id="14ee6-119">Antes de você colocar o grupo de disponibilidade offline, exclua o ouvinte do grupo de disponibilidade ou os ouvintes.</span><span class="sxs-lookup"><span data-stu-id="14ee6-119">Before you take the availability group offline, delete the availability group listener or listeners.</span></span> <span data-ttu-id="14ee6-120">Para obter mais informações, veja [Remover um ouvinte do grupo de disponibilidade &#40;SQL Server&#41;](availability-groups/windows/remove-an-availability-group-listener-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="14ee6-120">For more information, see [Remove an Availability Group Listener &#40;SQL Server&#41;](availability-groups/windows/remove-an-availability-group-listener-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="14ee6-121">Segurança</span><span class="sxs-lookup"><span data-stu-id="14ee6-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="14ee6-122">Permissões</span><span class="sxs-lookup"><span data-stu-id="14ee6-122">Permissions</span></span>  
 <span data-ttu-id="14ee6-123">Requer a permissão ALTER AVAILABILITY GROUP no grupo de disponibilidade, a permissão CONTROL AVAILABILITY GROUP, a permissão ALTER ANY AVAILABILITY GROUP ou a permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="14ee6-123">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="14ee6-124">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="14ee6-124">Using Transact-SQL</span></span>  
 <span data-ttu-id="14ee6-125">**Para colocar um grupo de disponibilidade offline**</span><span class="sxs-lookup"><span data-stu-id="14ee6-125">**To take an availability group offline**</span></span>  
  
1.  <span data-ttu-id="14ee6-126">Conecte-se a uma instância de servidor que hospede uma réplica de disponibilidade do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="14ee6-126">Connect to a server instance that hosts an availability replica for the availability group.</span></span> <span data-ttu-id="14ee6-127">Essa réplica pode ser a réplica primária ou uma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="14ee6-127">This replica can be the primary replica or a secondary replica.</span></span>  
  
2.  <span data-ttu-id="14ee6-128">Use a instrução [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="14ee6-128">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="14ee6-129">ALTER AVAILABILITY GROUP *group_name* OFFLINE</span><span class="sxs-lookup"><span data-stu-id="14ee6-129">ALTER AVAILABILITY GROUP *group_name* OFFLINE</span></span>  
  
     <span data-ttu-id="14ee6-130">em que *group_name* é o nome do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="14ee6-130">where *group_name* is the name of the availability group.</span></span>  
  
### <a name="example"></a><span data-ttu-id="14ee6-131">Exemplo</span><span class="sxs-lookup"><span data-stu-id="14ee6-131">Example</span></span>  
 <span data-ttu-id="14ee6-132">O exemplo a seguir coloca o grupo de disponibilidade `AccountsAG` offline.</span><span class="sxs-lookup"><span data-stu-id="14ee6-132">The following example takes the `AccountsAG` availability group offline.</span></span>  
  
```sql
ALTER AVAILABILITY GROUP AccountsAG OFFLINE;  
```  
  
##  <a name="follow-up-after-the-availability-group-goes-offline"></a><a name="FollowUp"></a> <span data-ttu-id="14ee6-133">Acompanhamento: Depois que o grupo de disponibilidade estiver offline</span><span class="sxs-lookup"><span data-stu-id="14ee6-133">Follow Up: After the Availability Group Goes Offline</span></span>  
  
-   <span data-ttu-id="14ee6-134">**Registro em log da operação OFFLINE:**  a identidade do nó WSFC em que a operação OFFLINE foi iniciada é armazenada no log do cluster WSFC e no SQL ERRORLOG.</span><span class="sxs-lookup"><span data-stu-id="14ee6-134">**Logging of OFFLINE operation:**  The identity of the WSFC node where the OFFLINE operation was initiated is stored in both the WSFC cluster log and the SQL ERRORLOG.</span></span>  
  
-   <span data-ttu-id="14ee6-135">**Se você não tiver excluído o ouvinte do grupo de disponibilidade antes de colocar o grupo offline:**  Se você estiver migrando o grupo de disponibilidade para outro cluster WSFC, exclua o VNN e o VIP do ouvinte.</span><span class="sxs-lookup"><span data-stu-id="14ee6-135">**If you did not delete the availability group listener before taking the group offline:**  If you are migrating the availability group to another WSFC cluster, delete the VNN and VIP of the listener.</span></span> <span data-ttu-id="14ee6-136">É possível excluí-los usando o console do Gerenciamento de Cluster de Failover, o cmdlet [Remove-ClusterResource](https://technet.microsoft.com/library/ee461015\(WS.10\).aspx) do PowerShell ou [cluster.exe](https://technet.microsoft.com/library/ee461015\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="14ee6-136">You can delete them by using either the Failover Cluster Management console, the [Remove-ClusterResource](https://technet.microsoft.com/library/ee461015\(WS.10\).aspx) PowerShell cmdlet, or [cluster.exe](https://technet.microsoft.com/library/ee461015\(WS.10\).aspx).</span></span> <span data-ttu-id="14ee6-137">Observe que cluster.exe foi preterido no Windows 8.</span><span class="sxs-lookup"><span data-stu-id="14ee6-137">Note that cluster.exe is deprecated on Windows 8.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="14ee6-138">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="14ee6-138">Related Tasks</span></span>  
  
-   [<span data-ttu-id="14ee6-139">Remover um ouvinte do grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="14ee6-139">Remove an Availability Group Listener &#40;SQL Server&#41;</span></span>](availability-groups/windows/remove-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="14ee6-140">Alterar o contexto do cluster HADR da instância de servidor &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="14ee6-140">Change the HADR Cluster Context of Server Instance &#40;SQL Server&#41;</span></span>](availability-groups/windows/change-the-hadr-cluster-context-of-server-instance-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="14ee6-141">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="14ee6-141">Related Content</span></span>  
  
-   <span data-ttu-id="14ee6-142">[Artigos técnicos do SQL Server 2012](https://msdn.microsoft.com/library/bb418445\(SQL.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="14ee6-142">[SQL Server 2012 Technical Articles](https://msdn.microsoft.com/library/bb418445\(SQL.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="14ee6-143">Blog da equipe do AlwaysOn do SQL Server: blog oficial da equipe do SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="14ee6-143">SQL Server AlwaysOn Team Blog: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
## <a name="see-also"></a><span data-ttu-id="14ee6-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="14ee6-144">See Also</span></span>  
 [<span data-ttu-id="14ee6-145">Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="14ee6-145">AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](availability-groups/windows/always-on-availability-groups-sql-server.md)  
