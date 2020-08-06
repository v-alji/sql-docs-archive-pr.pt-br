---
title: Monitorar o uso de disco | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- database monitoring [SQL Server], disk usage
- disks [SQL Server]
- monitoring performance [SQL Server], disk usage
- server performance [SQL Server], disk usage
- monitoring [SQL Server], disk activity
- excess paging [SQL Server]
- tuning databases [SQL Server], disk usage
- I/O [SQL Server], monitoring
- disks [SQL Server], monitoring activity
- isolating disk activity [SQL Server]
- database performance [SQL Server], disk usage
- monitoring server performance [SQL Server], disk usage
ms.assetid: 1525449c-ea7d-4222-b294-1ba1fe99c9ac
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 51479b024864322d34dc3b0208e29e93d7454184
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684668"
---
# <a name="monitor-disk-usage"></a><span data-ttu-id="af633-102">Monitorar o uso do disco</span><span class="sxs-lookup"><span data-stu-id="af633-102">Monitor Disk Usage</span></span>
  <span data-ttu-id="af633-103">O Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa chamadas de E/S (entrada/saída) do sistema operacional Microsoft Windows para executar operações de leitura e gravação no seu disco.</span><span class="sxs-lookup"><span data-stu-id="af633-103">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses Microsoft Windows operating system input/output (I/O) calls to perform read and write operations on your disk.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="af633-104">gerencia quando e como a E/S de disco é executada, mas o sistema operacional Windows executa as operações de E/S subjacentes.</span><span class="sxs-lookup"><span data-stu-id="af633-104">manages when and how disk I/O is performed, but the Windows operating system performs the underlying I/O operations.</span></span> <span data-ttu-id="af633-105">O subsistema de E/S compreende o barramento do sistema, as placas do controlador de disco, os discos, as unidades de fita, a unidade de CD-ROM e vários outros dispositivos de E/S.</span><span class="sxs-lookup"><span data-stu-id="af633-105">The I/O subsystem includes the system bus, disk controller cards, disks, tape drives, CD-ROM drive, and many other I/O devices.</span></span> <span data-ttu-id="af633-106">E/S no disco é, muitas vezes, a causa de gargalos em um sistema.</span><span class="sxs-lookup"><span data-stu-id="af633-106">Disk I/O is frequently the cause of bottlenecks in a system.</span></span>  
  
 <span data-ttu-id="af633-107">Monitorar a atividade de disco envolve duas áreas de foco:</span><span class="sxs-lookup"><span data-stu-id="af633-107">Monitoring disk activity involves two areas of focus:</span></span>  
  
-   <span data-ttu-id="af633-108">Monitorar E/S no disco e detectar paginação excessiva</span><span class="sxs-lookup"><span data-stu-id="af633-108">Monitoring Disk I/O and Detecting Excess Paging</span></span>  
  
-   <span data-ttu-id="af633-109">Isolar a atividade de disco criada pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af633-109">Isolating Disk Activity That [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Creates</span></span>  
  
 <span data-ttu-id="af633-110">Para obter mais informações, consulte [monitorando o uso do disco](https://social.technet.microsoft.com/wiki/contents/articles/monitoring-disk-usage.aspx)</span><span class="sxs-lookup"><span data-stu-id="af633-110">For more information see, [Monitoring Disk Usage](https://social.technet.microsoft.com/wiki/contents/articles/monitoring-disk-usage.aspx)</span></span>  
  
  
