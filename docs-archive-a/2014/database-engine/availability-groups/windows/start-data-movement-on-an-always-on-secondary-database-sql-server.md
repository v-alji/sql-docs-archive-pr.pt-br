---
title: Iniciar a movimentação de dados em um banco de dados secundário AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], databases
ms.assetid: 498eb3fb-6a43-434d-ad95-68a754232c45
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3ce4f80b456244cd6e024377383abe75e002057a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685291"
---
# <a name="start-data-movement-on-an-alwayson-secondary-database-sql-server"></a><span data-ttu-id="8d78a-102">Iniciar movimentação de dados em um banco de dados secundário AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="8d78a-102">Start Data Movement on an AlwaysOn Secondary Database (SQL Server)</span></span>
  <span data-ttu-id="8d78a-103">Este tópico contém informações sobre como iniciar a sincronização de dados depois que você adiciona um banco de dados a um grupo de disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="8d78a-103">This topic contains information about how to start data synchronization after you add a database to an AlwaysOn availability group.</span></span> <span data-ttu-id="8d78a-104">Para cada nova réplica primária, bancos de dados secundários devem ser preparados nas instâncias do servidor que hospedam as réplicas secundárias.</span><span class="sxs-lookup"><span data-stu-id="8d78a-104">For each new primary replica, secondary databases must be prepared on the server instances that host the secondary replicas.</span></span> <span data-ttu-id="8d78a-105">Em seguida, cada um destes bancos de dados secundários deve ser unido manualmente ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="8d78a-105">Then each of these secondary databases must be manually joined to the availability group.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8d78a-106">Se os caminhos de arquivos forem idênticos em cada instância do servidor que hospeda uma réplica de disponibilidade para um grupo de disponibilidade, o [Assistente de Novo Grupo de Disponibilidade](use-the-availability-group-wizard-sql-server-management-studio.md), [Assistente para Adicionar Réplica ao Grupo de Disponibilidade](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)ou [Assistente para Adicionar Banco de dados ao Grupo de Disponibilidade](availability-group-add-database-to-group-wizard.md) poderá iniciar a sincronização de dados automaticamente para você.</span><span class="sxs-lookup"><span data-stu-id="8d78a-106">If the file paths are identical on every server instance that hosts an availability replica for an availability group, the [New Availability Group Wizard](use-the-availability-group-wizard-sql-server-management-studio.md), [Add Replica to Availability Group Wizard](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md), or [Add Database to Availability Group Wizard](availability-group-add-database-to-group-wizard.md) might be able to automatically start data synchronization for you.</span></span>  
  
 <span data-ttu-id="8d78a-107">Para iniciar a sincronização de dados manualmente, você precisa conectar-se a cada instância de servidor, uma por vez, que está hospedando uma réplica secundária para o grupo de disponibilidade e concluir as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="8d78a-107">To start data synchronization manually, you need to connect, in turn, to each server instance that is hosting a secondary replica for the availability group and complete the following steps:</span></span>  
  
1.  <span data-ttu-id="8d78a-108">Restaure os backups atuais de cada banco de dados primário e seu log de transações (usando RESTORE WITH NORECOVERY).</span><span class="sxs-lookup"><span data-stu-id="8d78a-108">Restore current backups of each primary database and its transaction log (using RESTORE WITH NORECOVERY).</span></span> <span data-ttu-id="8d78a-109">Você pode usar qualquer uma das seguintes abordagens alternativas:</span><span class="sxs-lookup"><span data-stu-id="8d78a-109">You can use either of the following alternative approaches:</span></span>  
  
    -   <span data-ttu-id="8d78a-110">Restaurar manualmente um backup recente do banco de dados primário usando RESTORE WITH NORECOVERY e, em seguida, restaurar cada backup de log subsequente usando RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="8d78a-110">Manually restore a recent database backup of the primary database using RESTORE WITH NORECOVERY, and then restore each subsequent log backup using RESTORE WITH NORECOVERY.</span></span> <span data-ttu-id="8d78a-111">Executar essa sequência de restauração em cada instância do servidor que hospeda uma réplica secundária para o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="8d78a-111">Perform this restore sequence on every server instance that hosts a secondary replica for the availability group.</span></span>  
  
         <span data-ttu-id="8d78a-112">**Para obter mais informações:**</span><span class="sxs-lookup"><span data-stu-id="8d78a-112">**For more information:**</span></span>  
  
         [<span data-ttu-id="8d78a-113">Preparar um banco de dados secundário manualmente para um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8d78a-113">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
    -   <span data-ttu-id="8d78a-114">Se você estiver adicionando um ou mais bancos de dados primários de envio de logs a um grupo de disponibilidade, poderá ser capaz de migrar um ou mais dos bancos de dados secundários correspondentes de envio de logs para Grupos de Disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="8d78a-114">If you are adding one or more log shipping primary databases to an availability group, you might be able to migrate one or more of the corresponding secondary databases from log shipping to AlwaysOn Availability Groups.</span></span> <span data-ttu-id="8d78a-115">Migrar um banco de dados secundário de envio de logs exige que se use o mesmo nome de banco de dados que o banco de dados primário e que ele resida em uma instância de servidor que esteja hospedando uma réplica secundária para o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="8d78a-115">Migrating a log shipping secondary database requires that it use the same database name as the primary database and that it reside on a server instance that is hosting a secondary replica for the availability group.</span></span> <span data-ttu-id="8d78a-116">Além disso, o grupo de disponibilidade deve ser configurado de forma que a réplica primária seja preferida para backups e seja um candidato para realizar backups (quer dizer, ele tem uma prioridade de backup que é >0).</span><span class="sxs-lookup"><span data-stu-id="8d78a-116">Furthermore, the availability group must be configured so that the primary replica is preferred for backups and is a candidate for performing backups (that is, that has a backup priority that is >0).</span></span> <span data-ttu-id="8d78a-117">Quando o trabalho de backup estiver sendo executado no banco de dados primário, você precisará desabilitar o trabalho de backup e, assim que o trabalho de restauração tiver sido executado em um determinado banco de dados secundário, você precisará desabilitar o trabalho de restauração.</span><span class="sxs-lookup"><span data-stu-id="8d78a-117">Once the backup job has run on the primary database, you will need to disable the backup job, and once the restore job has run on a given secondary database, you will need to disable the restore job.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="8d78a-118">Depois que você criar todos os bancos de dados secundários para o grupo de disponibilidade, se você desejar executar backups em réplicas secundárias, precisará reconfigurar a preferência de backup automatizada do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="8d78a-118">After you have created all the secondary databases for the availability group, if you want to perform backups on secondary replicas, you will need to re-configure the automated backup preference of the availability group.</span></span>  
  
         <span data-ttu-id="8d78a-119">**Para obter mais informações:**</span><span class="sxs-lookup"><span data-stu-id="8d78a-119">**For more information:**</span></span>  
  
         [<span data-ttu-id="8d78a-120">Pré-requisitos para migrar do envio de logs para Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8d78a-120">Prerequisites for Migrating from Log Shipping to AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](prereqs-migrating-log-shipping-to-always-on-availability-groups.md)  
  
         [<span data-ttu-id="8d78a-121">Configurar backup em réplicas de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8d78a-121">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
2.  <span data-ttu-id="8d78a-122">O mais rápido possível, una cada banco de dados secundário recém-preparado ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="8d78a-122">As soon as possible, join each newly prepared secondary database to the availability group.</span></span>  
  
     <span data-ttu-id="8d78a-123">**Para obter mais informações:**</span><span class="sxs-lookup"><span data-stu-id="8d78a-123">**For more information:**</span></span>  
  
     [<span data-ttu-id="8d78a-124">Unir um banco de dados secundário a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8d78a-124">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
##  <a name="related-tasks"></a><a name="LaunchWiz"></a> <span data-ttu-id="8d78a-125">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="8d78a-125">Related Tasks</span></span>  
  
-   [<span data-ttu-id="8d78a-126">Usar a caixa de diálogo Novo Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="8d78a-126">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="8d78a-127">Usar o Assistente para Adicionar Réplica ao Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="8d78a-127">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="8d78a-128">Usar o Assistente para Adicionar Banco de Dados ao Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="8d78a-128">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="8d78a-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8d78a-129">See Also</span></span>  
 [<span data-ttu-id="8d78a-130">Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8d78a-130">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
