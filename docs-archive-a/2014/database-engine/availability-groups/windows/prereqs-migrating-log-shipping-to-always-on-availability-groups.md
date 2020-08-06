---
title: Pré-requisitos para migrar do envio de logs para Grupos de Disponibilidade AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: 2738ce65-205e-4682-92d8-dc7e37c58b2b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 76b50d5af8eb520b3764ff56397c040f2d0d0141
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681846"
---
# <a name="prerequisites-for-migrating-from-log-shipping-to-alwayson-availability-groups-sql-server"></a><span data-ttu-id="6af7b-102">Pré-requisitos para migrar de envio de logs para grupos de disponibilidade AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6af7b-102">Prerequisites for Migrating from Log Shipping to AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="6af7b-103">Esse tópico descreve os pré-requisitos para converter um banco de dados primário para envio de logs junto com um ou mais de seus bancos de dados secundários para um banco de dados primário AlwaysOn e bancos de dados secundários.</span><span class="sxs-lookup"><span data-stu-id="6af7b-103">This topic describes the prerequisites for converting a log shipping primary database along with one or more of its secondary databases to an AlwaysOn primary database and secondary database(s).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6af7b-104">Você pode configurar qualquer banco de dados primário ou secundário (possivelmente legível) em um grupo de disponibilidade como um banco de dados primário de envio de logs.</span><span class="sxs-lookup"><span data-stu-id="6af7b-104">You can configure any primary or secondary database (possibly readable) in an availability group as a log shipping primary database.</span></span>  
  
 <span data-ttu-id="6af7b-105">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="6af7b-105">**In This Topic:**</span></span>  
  
-   [<span data-ttu-id="6af7b-106">Pré-requisitos do grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="6af7b-106">Availability Group Prerequisites</span></span>](#AGPrereqsRealAddress)  
  
-   [<span data-ttu-id="6af7b-107">Pré-requisitos para envio de logs</span><span class="sxs-lookup"><span data-stu-id="6af7b-107">Log Shipping Prerequisites</span></span>](#LogShipPrereqs)  
  
-   [<span data-ttu-id="6af7b-108">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="6af7b-108">Related Tasks</span></span>](#RelatedTasks)  
  
-   [<span data-ttu-id="6af7b-109">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="6af7b-109">Related Content</span></span>](#RelatedContent)  
  
##  <a name="availability-group-prerequisites"></a><a name="AGPrereqsRealAddress"></a><span data-ttu-id="6af7b-110">Pré-requisitos do grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="6af7b-110">Availability Group Prerequisites</span></span>  
 <span data-ttu-id="6af7b-111">Para permitir que trabalhos de backup sejam executados na réplica primária do grupo de disponibilidade, use as seguintes configurações de backup dos Grupos de Disponibilidade AlwaysOn:</span><span class="sxs-lookup"><span data-stu-id="6af7b-111">To allow backup jobs to run on the primary replica of the availability group, use the following AlwaysOn Availability Groups backup settings:</span></span>  
  
|<span data-ttu-id="6af7b-112">Propriedade</span><span class="sxs-lookup"><span data-stu-id="6af7b-112">Property</span></span>|<span data-ttu-id="6af7b-113">Configuração</span><span class="sxs-lookup"><span data-stu-id="6af7b-113">Setting</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="6af7b-114">A preferência de backup automatizada do grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="6af7b-114">Automated backup preference of availability group</span></span>|<span data-ttu-id="6af7b-115">Apenas na réplica primária</span><span class="sxs-lookup"><span data-stu-id="6af7b-115">Only on the primary replica</span></span>|  
|<span data-ttu-id="6af7b-116">Prioridade de backup da réplica primária.</span><span class="sxs-lookup"><span data-stu-id="6af7b-116">Backup priority of the primary replica.</span></span>|<span data-ttu-id="6af7b-117">>0</span><span class="sxs-lookup"><span data-stu-id="6af7b-117">>0</span></span>|  
  
 <span data-ttu-id="6af7b-118">**Para obter mais informações:**</span><span class="sxs-lookup"><span data-stu-id="6af7b-118">**For more information:**</span></span>  
  
 [<span data-ttu-id="6af7b-119">Exibir as propriedades do grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6af7b-119">View Availability Group Properties &#40;SQL Server&#41;</span></span>](view-availability-group-properties-sql-server.md)  
  
 [<span data-ttu-id="6af7b-120">Configurar backup em réplicas de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6af7b-120">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
##  <a name="log-shipping-prerequisites"></a><a name="LogShipPrereqs"></a><span data-ttu-id="6af7b-121">Pré-requisitos de envio de logs</span><span class="sxs-lookup"><span data-stu-id="6af7b-121">Log Shipping Prerequisites</span></span>  
  
-   <span data-ttu-id="6af7b-122">O banco de dados primário para envio de logs deve residir na instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que hospeda a réplica primária inicial/atual do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="6af7b-122">The log shipping primary database must reside on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the initial/current primary replica of the availability group.</span></span>  
  
-   <span data-ttu-id="6af7b-123">Para um determinado banco de dados secundário para envio de log ser convertido em um banco de dados secundário AlwaysOn, ele deverá:</span><span class="sxs-lookup"><span data-stu-id="6af7b-123">For a given log shipping secondary database to be converted to an AlwaysOn secondary database, it must:</span></span>  
  
    -   <span data-ttu-id="6af7b-124">Usar o mesmo nome que o banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="6af7b-124">Use the same name as the primary database.</span></span>  
  
    -   <span data-ttu-id="6af7b-125">Residir em uma instância de servidor que hospeda uma réplica secundária para o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="6af7b-125">Reside on a server instance that hosts a secondary replica for the availability group.</span></span>  
  
 <span data-ttu-id="6af7b-126">Quando o trabalho de backup estiver sendo executado no banco de dados primário, desabilite o trabalho de backup e, assim que o trabalho de restauração tiver sido executado em um determinado banco de dados secundário, desabilite o trabalho de restauração.</span><span class="sxs-lookup"><span data-stu-id="6af7b-126">Once the backup job has run on the primary database, disable the backup job, and once the restore job has run on a given secondary database, disable the restore job.</span></span>  
  
 <span data-ttu-id="6af7b-127">Depois que você criar todos os bancos de dados secundários para o grupo de disponibilidade, se você desejar executar backups em réplicas secundárias, precisará reconfigurar a preferência de backup automatizada do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="6af7b-127">After you have created all the secondary databases for the availability group, if you want to perform backups on secondary replicas, you need to re-configure the automated backup preference of the availability group.</span></span>  
  
 <span data-ttu-id="6af7b-128">**Para obter mais informações:**</span><span class="sxs-lookup"><span data-stu-id="6af7b-128">**For more information:**</span></span>  
  
 <span data-ttu-id="6af7b-129">[Convertendo uma configuração para envio de logs para Grupo de Disponibilidade](https://blogs.msdn.com/b/sqlalwayson/archive/2012/01/09/converting-a-logshipping-configuration-to-availability-group.aspx) (um blog do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6af7b-129">[Converting a logshipping configuration to Availability Group](https://blogs.msdn.com/b/sqlalwayson/archive/2012/01/09/converting-a-logshipping-configuration-to-availability-group.aspx) (a SQL Server blog)</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="6af7b-130">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="6af7b-130">Related Tasks</span></span>  
 <span data-ttu-id="6af7b-131">**Envio de logs**</span><span class="sxs-lookup"><span data-stu-id="6af7b-131">**Log shipping**</span></span>  
  
-   [<span data-ttu-id="6af7b-132">Atualizar o envio de logs para SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6af7b-132">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](../../log-shipping/upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="6af7b-133">Remover envio de log &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6af7b-133">Remove Log Shipping &#40;SQL Server&#41;</span></span>](../../log-shipping/remove-log-shipping-sql-server.md)  
  
 <span data-ttu-id="6af7b-134">**Grupos de disponibilidade AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="6af7b-134">**AlwaysOn Availability Groups**</span></span>  
  
-   [<span data-ttu-id="6af7b-135">Usar o Assistente de Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6af7b-135">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="6af7b-136">Usar a caixa de diálogo Novo Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6af7b-136">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="6af7b-137">Criar um grupo de disponibilidade &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6af7b-137">Create an Availability Group &#40;Transact-SQL&#41;</span></span>](create-an-availability-group-transact-sql.md)  
  
-   [<span data-ttu-id="6af7b-138">Criar um grupo de disponibilidade &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="6af7b-138">Create an Availability Group &#40;SQL Server PowerShell&#41;</span></span>](../../../powershell/sql-server-powershell.md)  
  
-   [<span data-ttu-id="6af7b-139">Unir um banco de dados secundário a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6af7b-139">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="6af7b-140">Configurar backup em réplicas de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6af7b-140">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="6af7b-141">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="6af7b-141">Related Content</span></span>  
  
-   <span data-ttu-id="6af7b-142">**Blogs:**</span><span class="sxs-lookup"><span data-stu-id="6af7b-142">**Blogs:**</span></span>  
  
     [<span data-ttu-id="6af7b-143">Convertendo uma configuração para envio de logs para Grupo de Disponibilidade</span><span class="sxs-lookup"><span data-stu-id="6af7b-143">Converting a logshipping configuration to Availability Group</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/converting-a-logshipping-configuration-to-availability-group)  
  
     [<span data-ttu-id="6af7b-144">Adicione um banco de dados primário de envio de logs e bancos de dados secundários a um grupo de disponibilidade existente</span><span class="sxs-lookup"><span data-stu-id="6af7b-144">Add a Log Shipping Primary Database and Secondary Database(s) to an Existing Availability Group</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/add-a-log-shipping-primary-database-and-secondary-databases-to-an-existing-availability-group)  
  
     [<span data-ttu-id="6af7b-145">Blogs da equipe do SQL Server AlwaysOn: o blog oficial da equipe do SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="6af7b-145">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/)  
  
     [<span data-ttu-id="6af7b-146">Blogs dos engenheiros do CSS SQL Server</span><span class="sxs-lookup"><span data-stu-id="6af7b-146">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="6af7b-147">**Whitepapers:**</span><span class="sxs-lookup"><span data-stu-id="6af7b-147">**Whitepapers:**</span></span>  
  
     [<span data-ttu-id="6af7b-148">Guia de migração: Migrando para grupos de disponibilidade AlwaysOn de implantações anteriores que combinam espelhamento de banco de dados e envio de logs</span><span class="sxs-lookup"><span data-stu-id="6af7b-148">Migration Guide: Migrating to AlwaysOn Availability Groups from Prior Deployments Combining Database Mirroring and Log Shipping</span></span>](https://msdn.microsoft.com/library/jj635217)  
  
     [<span data-ttu-id="6af7b-149">White papers da Microsoft para SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="6af7b-149">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="6af7b-150">White papers da equipe de consultoria do cliente do SQL Server</span><span class="sxs-lookup"><span data-stu-id="6af7b-150">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="6af7b-151">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6af7b-151">See Also</span></span>  
 <span data-ttu-id="6af7b-152">[Sobre o envio de logs &#40;SQL Server&#41;](../../log-shipping/about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6af7b-152">[About Log Shipping &#40;SQL Server&#41;](../../log-shipping/about-log-shipping-sql-server.md) </span></span>  
 <span data-ttu-id="6af7b-153">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6af7b-153">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="6af7b-154">Monitoramento de grupos de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6af7b-154">Monitoring of Availability Groups &#40;SQL Server&#41;</span></span>](monitoring-of-availability-groups-sql-server.md)  
  
  
