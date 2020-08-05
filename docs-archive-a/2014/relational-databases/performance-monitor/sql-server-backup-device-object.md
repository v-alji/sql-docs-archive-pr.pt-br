---
title: SQL Server, objeto Dispositivo de Backup | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLServer:Backup Device
- Backup Device object
ms.assetid: 52e7febf-d5e0-4674-945b-aacc40a9ad6e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e3126310ad31dcc153fc79508dbfaccf86f5da78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572506"
---
# <a name="sql-server-backup-device-object"></a><span data-ttu-id="4a638-102">SQL Server, objeto Backup Device</span><span class="sxs-lookup"><span data-stu-id="4a638-102">SQL Server, Backup Device Object</span></span>
  <span data-ttu-id="4a638-103">O objeto **Backup Device** oferece contadores para monitorar dispositivos de backup do Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizados para operações de backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="4a638-103">The **Backup Device** object provides counters to monitor Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup devices used for backup and restore operations.</span></span> <span data-ttu-id="4a638-104">Monitore os dispositivos de backup quando quiser determinar a taxa de transferência ou o andamento e o desempenho de operações de backup e restauração por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4a638-104">Monitor backup devices when you want to determine the throughput or the progress and performance of your backup and restore operations on a per device basis.</span></span> <span data-ttu-id="4a638-105">Para monitorar a taxa de transferência da operação de backup ou restauração inteira do banco de dados, use o contador **Taxa de Transferência de Backup/Restauração/s** do objeto [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Databases**.</span><span class="sxs-lookup"><span data-stu-id="4a638-105">To monitor the throughput of the entire database backup or restore operation, use the **Backup/Restore Throughput/sec** counter of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Databases** object.</span></span> <span data-ttu-id="4a638-106">Para obter mais informações, consulte [SQL Server, Databases Object](sql-server-databases-object.md).</span><span class="sxs-lookup"><span data-stu-id="4a638-106">For more information, see [SQL Server, Databases Object](sql-server-databases-object.md).</span></span>  
  
 <span data-ttu-id="4a638-107">Esta tabela descreve o contador **Backup Device** do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a638-107">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Backup Device** counter.</span></span>  
  
|<span data-ttu-id="4a638-108">Contadores do Dispositivo de Backup do SQL Server</span><span class="sxs-lookup"><span data-stu-id="4a638-108">SQL Server Backup Device counters</span></span>|<span data-ttu-id="4a638-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="4a638-109">Description</span></span>|  
|---------------------------------------|-----------------|  
|<span data-ttu-id="4a638-110">**Taxa de Transferência do Dispositivo em Bytes/s**</span><span class="sxs-lookup"><span data-stu-id="4a638-110">**Device Throughput Bytes/sec**</span></span>|<span data-ttu-id="4a638-111">Taxa de transferência de operações de leitura e gravação (em bytes por segundo) de um dispositivo de backup utilizado no backup ou restauração de bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="4a638-111">Throughput of read and write operations (in bytes per second) for a backup device used when backing up or restoring databases.</span></span> <span data-ttu-id="4a638-112">Este contador só existe enquanto a operação de backup ou restauração está em execução.</span><span class="sxs-lookup"><span data-stu-id="4a638-112">This counter exists only while the backup or restore operation is executing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4a638-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4a638-113">See Also</span></span>  
 <span data-ttu-id="4a638-114">[Dispositivos de backup &#40;SQL Server&#41;](../backup-restore/backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4a638-114">[Backup Devices &#40;SQL Server&#41;](../backup-restore/backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="4a638-115">Monitorar o uso de recursos &#40;Monitor do Sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="4a638-115">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
