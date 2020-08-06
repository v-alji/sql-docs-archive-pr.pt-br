---
title: 'Propriedades do grupo de disponibilidade: novo grupo de disponibilidade (página preferências de backup) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroupproperties.backuppreferences.f1
helpviewer_keywords:
- read-only routing
ms.assetid: 65fff22d-5963-4a8c-8b31-fe9ab247a03e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7914d4b1d7af06bcaf4f3fd05a260138e3edf5fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569668"
---
# <a name="availability-group-properties-new-availability-group-backup-preferences-page"></a><span data-ttu-id="3aa9c-102">Propriedades do grupo de disponibilidade: Novo Grupo de Disponibilidade (página Preferências de Backup)</span><span class="sxs-lookup"><span data-stu-id="3aa9c-102">Availability Group Properties: New Availability Group (Backup Preferences Page)</span></span>
  <span data-ttu-id="3aa9c-103">Use esta caixa de diálogo para exibir e alterar as preferências de backup do grupo de disponibilidade selecionado.</span><span class="sxs-lookup"><span data-stu-id="3aa9c-103">Use this dialog box to view and change the backup preferences of the selected availability group.</span></span>  
  
 <span data-ttu-id="3aa9c-104">**Para exibir as propriedades do grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="3aa9c-104">**To view availability group properties**</span></span>  
  
-   [<span data-ttu-id="3aa9c-105">Exibir as propriedades do grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3aa9c-105">View Availability Group Properties &#40;SQL Server&#41;</span></span>](view-availability-group-properties-sql-server.md)  
  
-   [<span data-ttu-id="3aa9c-106">Usar o Painel AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3aa9c-106">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
## <a name="where-should-backups-occur"></a><span data-ttu-id="3aa9c-107">Onde devem ocorrer os backups?</span><span class="sxs-lookup"><span data-stu-id="3aa9c-107">Where should backups occur?</span></span>  
 <span data-ttu-id="3aa9c-108">**Preferir Secundário**</span><span class="sxs-lookup"><span data-stu-id="3aa9c-108">**Prefer Secondary**</span></span>  
 <span data-ttu-id="3aa9c-109">Especifica que os backups devem ocorrer em uma réplica secundária, exceto quando a réplica primária for a única réplica online.</span><span class="sxs-lookup"><span data-stu-id="3aa9c-109">Specifies that backups should occur on a secondary replica except when the primary replica is the only replica online.</span></span> <span data-ttu-id="3aa9c-110">Nesse caso, o backup deve ocorrer na réplica primária.</span><span class="sxs-lookup"><span data-stu-id="3aa9c-110">In that case, the backup should occur on the primary replica.</span></span> <span data-ttu-id="3aa9c-111">Essa é a opção padrão.</span><span class="sxs-lookup"><span data-stu-id="3aa9c-111">This is the default option.</span></span>  
  
 <span data-ttu-id="3aa9c-112">**Somente Secundário**</span><span class="sxs-lookup"><span data-stu-id="3aa9c-112">**Secondary only**</span></span>  
 <span data-ttu-id="3aa9c-113">Especifica que os backups nunca devem ser executados na réplica primária.</span><span class="sxs-lookup"><span data-stu-id="3aa9c-113">Specifies that backups should never be performed on the primary replica.</span></span> <span data-ttu-id="3aa9c-114">Se a réplica primária for a única réplica online, o backup não deveria ocorrer.</span><span class="sxs-lookup"><span data-stu-id="3aa9c-114">If the primary replica is the only replica online, the backup should not occur.</span></span>  
  
 <span data-ttu-id="3aa9c-115">**Primário**</span><span class="sxs-lookup"><span data-stu-id="3aa9c-115">**Primary**</span></span>  
 <span data-ttu-id="3aa9c-116">Especifica que os backups sempre devem ocorrer na réplica primária.</span><span class="sxs-lookup"><span data-stu-id="3aa9c-116">Specifies that the backups should always occur on the primary replica.</span></span> <span data-ttu-id="3aa9c-117">Essa opção será útil se você precisar de recursos de backup, como a criação de backups diferenciais, que não têm suporte quando o backup é executado em uma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="3aa9c-117">This option is useful if you need backup features, such as creating differential backups, that are not supported when backup is run on a secondary replica.</span></span>  
  
 <span data-ttu-id="3aa9c-118">**Qualquer Réplica**</span><span class="sxs-lookup"><span data-stu-id="3aa9c-118">**Any Replica**</span></span>  
 <span data-ttu-id="3aa9c-119">Especifica que você prefere que trabalhos de backup ignorem a função das réplicas de disponibilidade ao escolher a réplica para executar backups.</span><span class="sxs-lookup"><span data-stu-id="3aa9c-119">Specifies that you prefer that backup jobs ignore the role of the availability replicas when choosing the replica to perform backups.</span></span> <span data-ttu-id="3aa9c-120">Observe que os trabalhos de backup podem avaliar outros fatores, como prioridade de backup de cada réplica de disponibilidade em combinação com seu estado operacional e estado conectado.</span><span class="sxs-lookup"><span data-stu-id="3aa9c-120">Note backup jobs might evaluate other factors such as backup priority of each availability replica in combination with its operational state and connected state.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3aa9c-121">Não há nenhuma imposição da configuração de preferência de backup.</span><span class="sxs-lookup"><span data-stu-id="3aa9c-121">There is no enforcement of the backup-preference setting.</span></span> <span data-ttu-id="3aa9c-122">A interpretação dessa preferência depende da lógica, se houver, que você usa para o script em trabalhos de backup para os bancos de dados em um determinado grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="3aa9c-122">The interpretation of this preference depends on the logic, if any, that you script into back jobs for the databases in a given availability group.</span></span> <span data-ttu-id="3aa9c-123">Para obter mais informações, consulte secundários [ativos: backup em réplicas secundárias (grupos de disponibilidade AlwaysOn)](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="3aa9c-123">For more information, see [Active Secondaries: Backup on Secondary Replicas (AlwaysOn Availability Groups)](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md).</span></span>  
  
## <a name="replica-backup-priorities"></a><span data-ttu-id="3aa9c-124">Prioridades de backup de réplica</span><span class="sxs-lookup"><span data-stu-id="3aa9c-124">Replica backup priorities</span></span>  
 <span data-ttu-id="3aa9c-125">Esta grade exibe a prioridade de backup atual de cada instância de servidor que hospeda uma réplica para o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="3aa9c-125">This grid displays the current backup priority of each server instance that hosts a replica for the availability group.</span></span> <span data-ttu-id="3aa9c-126">Use essa grade para alterar a prioridade de backup de uma ou mais réplicas de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="3aa9c-126">Use this grid to change the backup priority of one or more availability replicas.</span></span>  
  
 <span data-ttu-id="3aa9c-127">**Instância do Servidor**</span><span class="sxs-lookup"><span data-stu-id="3aa9c-127">**Server Instance**</span></span>  
 <span data-ttu-id="3aa9c-128">O nome da instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que hospeda a réplica de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="3aa9c-128">The name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the availability replica.</span></span>  
  
 <span data-ttu-id="3aa9c-129">**Prioridade de Backup (Mais Baixa = 1, Mais Alta = 100)**</span><span class="sxs-lookup"><span data-stu-id="3aa9c-129">**Backup Priority (Lowest=1, Highest=100)**</span></span>  
 <span data-ttu-id="3aa9c-130">Especifica sua prioridade para executar backups nesta réplica em relação às outras réplicas no mesmo grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="3aa9c-130">Specifies your priority for performing backups on this replica relative to the other replicas in the same availability group.</span></span> <span data-ttu-id="3aa9c-131">O valor é um número inteiro no intervalo de 0..100.</span><span class="sxs-lookup"><span data-stu-id="3aa9c-131">The value is an integer in the range of 0..100.</span></span> <span data-ttu-id="3aa9c-132">1 indica a prioridade mais baixa, e 100 indica a prioridade mais alta.</span><span class="sxs-lookup"><span data-stu-id="3aa9c-132">1 indicates the lowest priority, and 100 indicates the highest priority.</span></span> <span data-ttu-id="3aa9c-133">Se **Prioridade de Backup** = 1, a réplica de disponibilidade será escolhida para execução de backups apenas se nenhuma réplica de disponibilidade de prioridade mais alta estiver disponível atualmente.</span><span class="sxs-lookup"><span data-stu-id="3aa9c-133">If **Backup Priority** = 1, the availability replica would be chosen for performing backups only if no higher priority availability replicas are currently available.</span></span>  
  
 <span data-ttu-id="3aa9c-134">**Excluir Réplica**</span><span class="sxs-lookup"><span data-stu-id="3aa9c-134">**Exclude Replica**</span></span>  
 <span data-ttu-id="3aa9c-135">Selecione se desejar que esta réplica de disponibilidade nunca seja escolhida para executar backups.</span><span class="sxs-lookup"><span data-stu-id="3aa9c-135">Select if you never want this availability replica to be chosen for performing backups.</span></span> <span data-ttu-id="3aa9c-136">Isso é útil, por exemplo, para uma réplica de disponibilidade remota para a qual você nunca deseja que ocorra o failover de backups.</span><span class="sxs-lookup"><span data-stu-id="3aa9c-136">This is useful, for example, for a remote availability replica to which you never want backups to fail over.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aa9c-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3aa9c-137">See Also</span></span>  
 <span data-ttu-id="3aa9c-138">[Secundárias ativas: backup em réplicas secundárias (Grupos de Disponibilidade AlwaysOn)](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="3aa9c-138">[Active Secondaries: Backup on Secondary Replicas (AlwaysOn Availability Groups)](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="3aa9c-139">ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3aa9c-139">ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-availability-group-transact-sql)  
  
  
