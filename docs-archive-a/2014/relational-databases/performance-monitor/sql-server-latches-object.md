---
title: SQL Server, objeto Travas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Latches object
- SQLServer:Latches
ms.assetid: 2393ea1c-2bf3-41c3-9f37-b9761144eeca
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6f49ac00114065e971c0893f9217ab883eb2d7f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570636"
---
# <a name="sql-server-latches-object"></a><span data-ttu-id="f38bd-102">SQL Server, objeto Latches</span><span class="sxs-lookup"><span data-stu-id="f38bd-102">SQL Server, Latches Object</span></span>
  <span data-ttu-id="f38bd-103">O objeto **SQLServer:Latches** no Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oferece contadores para monitorar bloqueios de recursos internos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , chamados travas.</span><span class="sxs-lookup"><span data-stu-id="f38bd-103">The **SQLServer:Latches** object in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides counters to monitor internal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resource locks called latches.</span></span> <span data-ttu-id="f38bd-104">Monitorar as travas para determinar a atividade de usuário e o uso de recursos pode ajudar a identificar gargalos de desempenho.</span><span class="sxs-lookup"><span data-stu-id="f38bd-104">Monitoring the latches to determine user activity and resource usage can help you to identify performance bottlenecks.</span></span>  
  
 <span data-ttu-id="f38bd-105">Esta tabela descreve os contadores **Travas** do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f38bd-105">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Latches** counters.</span></span>  
  
|<span data-ttu-id="f38bd-106">Contadores de travas do SQL Server</span><span class="sxs-lookup"><span data-stu-id="f38bd-106">SQL Server Latches counters</span></span>|<span data-ttu-id="f38bd-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="f38bd-107">Description</span></span>|  
|---------------------------------|-----------------|  
|<span data-ttu-id="f38bd-108">**Tempo Médio de Espera de Trava (ms)**</span><span class="sxs-lookup"><span data-stu-id="f38bd-108">**Average Latch Wait Time (ms)**</span></span>|<span data-ttu-id="f38bd-109">Tempo médio de espera de trava (em milissegundos) para solicitações de trava que tiveram de esperar.</span><span class="sxs-lookup"><span data-stu-id="f38bd-109">Average latch wait time (in milliseconds) for latch requests that had to wait.</span></span>|  
|<span data-ttu-id="f38bd-110">**Esperas de Trava/s**</span><span class="sxs-lookup"><span data-stu-id="f38bd-110">**Latch Waits/sec**</span></span>|<span data-ttu-id="f38bd-111">Número de solicitações de trava que não puderam ser concedidas imediatamente.</span><span class="sxs-lookup"><span data-stu-id="f38bd-111">Number of latch requests that could not be granted immediately.</span></span>|  
|<span data-ttu-id="f38bd-112">**Número de SuperLatches**</span><span class="sxs-lookup"><span data-stu-id="f38bd-112">**Number of SuperLatches**</span></span>|<span data-ttu-id="f38bd-113">Número de travas que atualmente são SuperLatches.</span><span class="sxs-lookup"><span data-stu-id="f38bd-113">Number of latches that are currently SuperLatches.</span></span>|  
|<span data-ttu-id="f38bd-114">**Rebaixamentos de SuperLatches/s**</span><span class="sxs-lookup"><span data-stu-id="f38bd-114">**SuperLatch Demotions/sec**</span></span>|<span data-ttu-id="f38bd-115">Número de SuperLatches que foram rebaixados a travas regulares no último segundo.</span><span class="sxs-lookup"><span data-stu-id="f38bd-115">Number of SuperLatches that have been demoted to regular latches in the last second.</span></span>|  
|<span data-ttu-id="f38bd-116">**Promoções para SuperLatch/s**</span><span class="sxs-lookup"><span data-stu-id="f38bd-116">**SuperLatch Promotions/sec**</span></span>|<span data-ttu-id="f38bd-117">Número de travas que foram promovidas a SuperLatches no último segundo.</span><span class="sxs-lookup"><span data-stu-id="f38bd-117">Number of latches that have been promoted to SuperLatches in the last second.</span></span>|  
|<span data-ttu-id="f38bd-118">**Tempo de Espera Total de Trava (ms)**</span><span class="sxs-lookup"><span data-stu-id="f38bd-118">**Total Latch Wait Time (ms)**</span></span>|<span data-ttu-id="f38bd-119">Tempo de espera total de trava (em milissegundos) para solicitações de trava no último segundo.</span><span class="sxs-lookup"><span data-stu-id="f38bd-119">Total latch wait time (in milliseconds) for latch requests in the last second.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f38bd-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f38bd-120">See Also</span></span>  
 [<span data-ttu-id="f38bd-121">Monitorar o uso de recursos &#40;Monitor do Sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="f38bd-121">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
