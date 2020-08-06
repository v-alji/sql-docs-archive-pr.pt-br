---
title: Solucionar problemas de uma operação de adição de arquivo com falha (Grupos de Disponibilidade AlwaysOn) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- secondary databases [SQL Server], Availability Groups
- Availability Groups [SQL Server], troubleshooting
ms.assetid: 31ceaebf-864b-4dd0-9112-0d047b0316ad
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2551080c214f18473caa71a3e17797c34fcc943a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685281"
---
# <a name="troubleshoot-a-failed-add-file-operation-alwayson-availability-groups"></a><span data-ttu-id="31185-102">Solução de problemas de uma operação de adicionar arquivos com falha (grupos de disponibilidade de AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="31185-102">Troubleshoot a Failed Add-File Operation (AlwaysOn Availability Groups)</span></span>
  <span data-ttu-id="31185-103">Em algumas implantações de grupos de disponibilidade AlwaysOn, os caminhos de arquivos diferem entre o sistema que hospeda a réplica primária e os sistemas que hospedam uma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="31185-103">In some AlwaysOn availability group deployments, file paths differ between the system that hosts the primary replica and systems that host a secondary replica.</span></span> <span data-ttu-id="31185-104">Se o caminho do arquivo de uma operação de adicionar arquivos não existir em uma réplica secundária, a operação de adicionar arquivos terá sucesso no banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="31185-104">If the file path of an add-file operation does not exist on a secondary replica, the add-file operation will succeed on the primary database.</span></span> <span data-ttu-id="31185-105">Mas a operação de adicionar arquivos fará o banco de dados secundário ser suspenso.</span><span class="sxs-lookup"><span data-stu-id="31185-105">But the add-file operation will cause the secondary database to be suspended.</span></span> <span data-ttu-id="31185-106">Isto, por sua vez, faz a réplica secundária entrar no estado NOT SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="31185-106">This, in turn, causes the secondary replica to enter the NOT SYNCHRONIZING state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="31185-107">É recomendável que, se possível, o caminho do arquivo (incluindo a letra da unidade) de um determinado banco de dados secundário seja idêntico ao caminho do banco de dados primário correspondente.</span><span class="sxs-lookup"><span data-stu-id="31185-107">We recommend that, if possible, the file path (including the drive letter) of a given secondary database be identical to the path of the corresponding primary database.</span></span>  
  
## <a name="problem-resolution"></a><span data-ttu-id="31185-108">Resolução de problemas</span><span class="sxs-lookup"><span data-stu-id="31185-108">Problem Resolution</span></span>  
 <span data-ttu-id="31185-109">Para resolver esse problema, o proprietário do banco de dados deve concluir as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="31185-109">To resolve this problem the database owner must complete the following steps:</span></span>  
  
1.  <span data-ttu-id="31185-110">Remover o banco de dados secundário do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="31185-110">Remove the secondary database from the availability group.</span></span> <span data-ttu-id="31185-111">Para obter mais informações, veja [Remover um banco de dados secundário de um grupo de disponibilidade &#40;SQL Server&#41;](remove-a-secondary-database-from-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="31185-111">For more information, see [Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;](remove-a-secondary-database-from-an-availability-group-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="31185-112">No banco de dados secundário existente, restaure um backup completo do grupo de arquivos que contém o arquivo adicionado no banco de dados secundário, usando WITH NORECOVERY e WITH MOVE (especificando o caminho de arquivo na instância de servidor que hospeda a réplica secundária).</span><span class="sxs-lookup"><span data-stu-id="31185-112">On the existing secondary database, restore a full backup of the filegroup that contains the added file to the secondary database, using WITH NORECOVERY and WITH MOVE (specifying the file path on the server instance that hosts the secondary replica).</span></span> <span data-ttu-id="31185-113">Para obter mais informações, consulte [Restaurar um banco de dados em um novo local &#40;SQL Server&#41;](../../../relational-databases/backup-restore/restore-a-database-to-a-new-location-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="31185-113">For more information, see [Restore a Database to a New Location &#40;SQL Server&#41;](../../../relational-databases/backup-restore/restore-a-database-to-a-new-location-sql-server.md).</span></span>  
  
3.  <span data-ttu-id="31185-114">Faça backup do log de transações que contém a operação adicionar arquivo no banco de dados primário e restaure manualmente o backup do log no banco de dados secundário usando WITH NORECOVERY e WITH MOVE.</span><span class="sxs-lookup"><span data-stu-id="31185-114">Back up the transaction log that contains the add-file operation on the primary database, and manually restore the log backup on the secondary database using WITH NORECOVERY and WITH MOVE.</span></span>  
  
4.  <span data-ttu-id="31185-115">Prepare o banco de dados secundário para reingressar no grupo de disponibilidade, restaurando, WITH NO RECOVERY, todos os backups de log pendentes a partir do banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="31185-115">Prepare the secondary database for re-joining the availability group, by restoring, WITH NO RECOVERY, any other outstanding log backups from the primary database.</span></span>  
  
5.  <span data-ttu-id="31185-116">Reunindo o banco de dados secundário ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="31185-116">Rejoin the secondary database to the availability group.</span></span> <span data-ttu-id="31185-117">Para obter mais informações, consulte [Unir um banco de dados secundário a um grupo de disponibilidade &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="31185-117">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31185-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="31185-118">See Also</span></span>  
 <span data-ttu-id="31185-119">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="31185-119">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="31185-120">[Preparar um banco de dados secundário manualmente para um grupo de disponibilidade &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="31185-120">[Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md) </span></span>  
 <span data-ttu-id="31185-121">[Solução de problemas de usuários órfãos &#40;SQL Server&#41;](../../../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="31185-121">[Troubleshoot Orphaned Users &#40;SQL Server&#41;](../../../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md) </span></span>  
 [<span data-ttu-id="31185-122">Solucionar problemas de &#40;de configuração de Grupos de Disponibilidade AlwaysOn SQL Server&#41;excluídos</span><span class="sxs-lookup"><span data-stu-id="31185-122">Troubleshoot AlwaysOn Availability Groups Configuration &#40;SQL Server&#41;deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
  
  
