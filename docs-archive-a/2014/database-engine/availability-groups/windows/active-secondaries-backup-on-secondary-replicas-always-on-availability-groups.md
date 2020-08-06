---
title: 'Secundárias ativas: backup em réplicas secundárias (Always On grupos de disponibilidade) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- backup priority
- backup on secondary replicas
- Availability Groups [SQL Server], availability replicas
- Availability Groups [SQL Server], backup on secondary replicas
- active secondary replicas [SQL Server], backup on
- automated backup preference
- Availability Groups [SQL Server], active secondary replicas
ms.assetid: 82afe51b-71d1-4d5b-b20a-b57afc002405
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0cf899cdbeb1ae4ede6c9196b8eb93a9d9e54f05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681200"
---
# <a name="active-secondaries-backup-on-secondary-replicas-always-on-availability-groups"></a><span data-ttu-id="5adb7-102">Secundárias ativas: backup em réplicas secundárias (Grupos de Disponibilidade AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="5adb7-102">Active Secondaries: Backup on Secondary Replicas (Always On Availability Groups)</span></span>
  <span data-ttu-id="5adb7-103">Os recursos secundários ativos do [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] incluem suporte para execução de operações de backup em réplicas secundárias.</span><span class="sxs-lookup"><span data-stu-id="5adb7-103">The [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] active secondary capabilities include support for performing backup operations on secondary replicas.</span></span> <span data-ttu-id="5adb7-104">As operações de backup podem colocar tensão significativa na E/S e na CPU (com compactação de backup).</span><span class="sxs-lookup"><span data-stu-id="5adb7-104">Backup operations can put significant strain on I/O and CPU (with backup compression).</span></span> <span data-ttu-id="5adb7-105">O descarregamento de backups em uma réplica secundária sincronizada ou em sincronização permite usar os recursos na instância do servidor que hospeda a réplica primária para suas cargas de trabalho de camada-1.</span><span class="sxs-lookup"><span data-stu-id="5adb7-105">Offloading backups to a synchronized or synchronizing secondary replica allows you to use the resources on server instance that hosts the primary replica for your tier-1 workloads.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5adb7-106">As instruções RESTORE não são permitidas em nenhum dos bancos de dados primários ou secundários de um grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="5adb7-106">RESTORE statements are not allowed on either the primary or secondary databases of an availability group.</span></span>  
  
  
  
##  <a name="backup-types-supported-on-secondary-replicas"></a><a name="SupportedBuTypes"></a><span data-ttu-id="5adb7-107">Tipos de backup com suporte em réplicas secundárias</span><span class="sxs-lookup"><span data-stu-id="5adb7-107">Backup Types Supported on Secondary Replicas</span></span>  
  
-   <span data-ttu-id="5adb7-108">`BACKUP DATABASE` só oferece suporte a backups completos somente cópia de bancos de dados, de arquivos ou de grupos de arquivos quando executado em réplicas secundárias.</span><span class="sxs-lookup"><span data-stu-id="5adb7-108">`BACKUP DATABASE` supports only copy-only full backups of databases, files, or filegroups when it is executed on secondary replicas.</span></span> <span data-ttu-id="5adb7-109">Observe que os backups somente cópia não afetam a cadeia de logs nem limpam o bitmap diferencial.</span><span class="sxs-lookup"><span data-stu-id="5adb7-109">Note that copy-only backups do not impact the log chain or clear the differential bitmap.</span></span>  
  
-   <span data-ttu-id="5adb7-110">Não há suporte para backups diferenciais em réplicas secundárias.</span><span class="sxs-lookup"><span data-stu-id="5adb7-110">Differential backups are not supported on secondary replicas.</span></span>  
  
-   <span data-ttu-id="5adb7-111">**BACKUP LOG** dá suporte apenas a backups de log regulares (não há suporte para a opção COPY_ONLY em backups de log nas réplicas secundárias).</span><span class="sxs-lookup"><span data-stu-id="5adb7-111">**BACKUP LOG** supports only regular log backups (the COPY_ONLY option is not supported for log backups on secondary replicas).</span></span>  
  
     <span data-ttu-id="5adb7-112">Uma cadeia de logs consistente é garantida em backups de log feitos em qualquer uma das réplicas (primária ou secundária), independentemente de seu modo de disponibilidade (confirmação síncrona ou de confirmação assíncrona).</span><span class="sxs-lookup"><span data-stu-id="5adb7-112">A consistent log chain is ensured across log backups taken on any of the replicas (primary or secondary), irrespective of their availability mode (synchronous-commit or asynchronous-commit).</span></span>  
  
-   <span data-ttu-id="5adb7-113">Para fazer backup de um banco de dados secundário, uma réplica secundária deve ser capaz de se comunicar com a réplica primária e ser `SYNCHRONIZED` ou `SYNCHRONIZING`.</span><span class="sxs-lookup"><span data-stu-id="5adb7-113">To back up a secondary database, a secondary replica must be able to communicate with the primary replica and must be `SYNCHRONIZED` or `SYNCHRONIZING`.</span></span>  
  
##  <a name="configuring-where-backup-jobs-run"></a><a name="WhereBuJobsRun"></a><span data-ttu-id="5adb7-114">Configurando onde os trabalhos de backup são executados</span><span class="sxs-lookup"><span data-stu-id="5adb7-114">Configuring Where Backup Jobs Run</span></span>  
 <span data-ttu-id="5adb7-115">A execução de backups em uma réplica secundária para descarregar a carga de trabalho do backup do servidor de produção primário é um grande benefício.</span><span class="sxs-lookup"><span data-stu-id="5adb7-115">Performing backups on a secondary replica to offload the backup workload from the primary production server is a great benefit.</span></span> <span data-ttu-id="5adb7-116">No entanto, a execução de backups em réplicas secundárias introduz uma complexidade significativa no processo de determinação de onde os trabalhos de backup devem ser executados.</span><span class="sxs-lookup"><span data-stu-id="5adb7-116">However, performing backups on secondary replicas introduce significant complexity to the process of determining where backup jobs should run.</span></span> <span data-ttu-id="5adb7-117">Para resolver isto, configure onde os trabalhos de backup são executados, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="5adb7-117">To address this, configure where backup jobs run as follows:</span></span>  
  
1.  <span data-ttu-id="5adb7-118">Configure o grupo de disponibilidade para especificar em quais réplicas de disponibilidade você prefere que os backups sejam executados.</span><span class="sxs-lookup"><span data-stu-id="5adb7-118">Configure the availability group to specify which availability replicas where you would prefer backups to be performed.</span></span> <span data-ttu-id="5adb7-119">Para obter mais informações, confira os parâmetros *AUTOMATED_BACKUP_PREFERENCE* e *BACKUP_PRIORITY* em [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql) ou [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5adb7-119">For more information, see *AUTOMATED_BACKUP_PREFERENCE* and *BACKUP_PRIORITY* parameters in [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql) or [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql).</span></span>  
  
2.  <span data-ttu-id="5adb7-120">Crie trabalhos de backup com script para cada banco de dados de disponibilidade em cada instância de servidor que hospeda uma réplica de disponibilidade que é candidata a executar backups.</span><span class="sxs-lookup"><span data-stu-id="5adb7-120">Create scripted backup jobs for every availability database on every server instance that hosts an availability replica that is a candidate for performing backups.</span></span> <span data-ttu-id="5adb7-121">Para obter mais informações, confira a seção “Acompanhamento: Depois de configurar o backup em réplicas secundárias” de [Configurar backup em réplicas de disponibilidade &#40;SQL Server&#41;](configure-backup-on-availability-replicas-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5adb7-121">For more information, see the "Follow Up: After Configuring Backup on Secondary Replicas" section of [Configure Backup on Availability Replicas &#40;SQL Server&#41;](configure-backup-on-availability-replicas-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="5adb7-122">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="5adb7-122">Related Tasks</span></span>  
 <span data-ttu-id="5adb7-123">**Para configurar o backup em réplicas secundárias**</span><span class="sxs-lookup"><span data-stu-id="5adb7-123">**To configure backup on secondary replicas**</span></span>  
  
-   [<span data-ttu-id="5adb7-124">Configurar backup em réplicas de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5adb7-124">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
 <span data-ttu-id="5adb7-125">**Para determinar se a réplica atual é a réplica de backup preferencial**</span><span class="sxs-lookup"><span data-stu-id="5adb7-125">**To determine whether the current replica is the preferred backup replica**</span></span>  
  
-   [<span data-ttu-id="5adb7-126">sys.fn_hadr_backup_is_preferred_replica</span><span class="sxs-lookup"><span data-stu-id="5adb7-126">sys.fn_hadr_backup_is_preferred_replica</span></span>](/sql/relational-databases/system-functions/sys-fn-hadr-backup-is-preferred-replica-transact-sql)  
  
 <span data-ttu-id="5adb7-127">**Para criar um trabalho de backup**</span><span class="sxs-lookup"><span data-stu-id="5adb7-127">**To create a backup job**</span></span>  
  
-   [<span data-ttu-id="5adb7-128">Usar o Assistente de Plano de Manutenção</span><span class="sxs-lookup"><span data-stu-id="5adb7-128">Use the Maintenance Plan Wizard</span></span>](../../../relational-databases/maintenance-plans/use-the-maintenance-plan-wizard.md)  
  
-   [<span data-ttu-id="5adb7-129">Implementar trabalhos</span><span class="sxs-lookup"><span data-stu-id="5adb7-129">Implement Jobs</span></span>](../../../ssms/agent/implement-jobs.md)  
  
  
## <a name="see-also"></a><span data-ttu-id="5adb7-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5adb7-130">See Also</span></span>  
 <span data-ttu-id="5adb7-131">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5adb7-131">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="5adb7-132">[Backups somente cópia &#40;SQL Server&#41;](../../../relational-databases/backup-restore/copy-only-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5adb7-132">[Copy-Only Backups &#40;SQL Server&#41;](../../../relational-databases/backup-restore/copy-only-backups-sql-server.md) </span></span>  
 <span data-ttu-id="5adb7-133">[CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5adb7-133">[CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql) </span></span>  
 [<span data-ttu-id="5adb7-134">ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5adb7-134">ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-availability-group-transact-sql)  
  
  
