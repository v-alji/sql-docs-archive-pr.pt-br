---
title: SQL Server Agent, objeto Alertas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Alerts object
- SQLAgent:Alerts
ms.assetid: e5e37f74-ee88-46d0-ad8f-71fd1b1fa64a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9aa6fa871730af8cf129b3ea6b0aa4f1853d7e4d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571354"
---
# <a name="sql-server-agent-alerts-object"></a><span data-ttu-id="436c2-102">SQL Server Agent, objeto Alerts</span><span class="sxs-lookup"><span data-stu-id="436c2-102">SQL Server Agent, Alerts Object</span></span>
  <span data-ttu-id="436c2-103">O objeto de desempenho **Alerts** do SQL Server Agent contém contadores de desempenho que relatam informações sobre alertas do SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="436c2-103">The SQL Server Agent **Alerts** performance object contains performance counters that report information about SQL Server Agent alerts.</span></span> <span data-ttu-id="436c2-104">A tabela a seguir lista os contadores contidos nesse objeto.</span><span class="sxs-lookup"><span data-stu-id="436c2-104">The table below lists the counters that this object contains.</span></span>  
  
 <span data-ttu-id="436c2-105">A tabela abaixo contém os contadores de **SQLAgent:Alerts** .</span><span class="sxs-lookup"><span data-stu-id="436c2-105">The table below contains the **SQLAgent:Alerts** counters.</span></span>  
  
|<span data-ttu-id="436c2-106">Nome</span><span class="sxs-lookup"><span data-stu-id="436c2-106">Name</span></span>|<span data-ttu-id="436c2-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="436c2-107">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="436c2-108">**Alertas ativados**</span><span class="sxs-lookup"><span data-stu-id="436c2-108">**Activated alerts**</span></span>|<span data-ttu-id="436c2-109">Este contador informa o total de alertas que o Microsoft SQL Agent ativou desde que foi reiniciado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="436c2-109">This counter reports the total number of alerts that SQL Server Agent has activated since the last time that SQL Server Agent restarted.</span></span>|  
|<span data-ttu-id="436c2-110">**Alertas ativados/minuto**</span><span class="sxs-lookup"><span data-stu-id="436c2-110">**Alerts activated/minute**</span></span>|<span data-ttu-id="436c2-111">Este contador informa o número de alertas que o SQL Server Agent ativou no último minuto.</span><span class="sxs-lookup"><span data-stu-id="436c2-111">This counter reports the number of alerts that SQL Server Agent activated within the last minute.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="436c2-112">Para usar este objeto do SQL Server Agent, os usuários devem ser membros da função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="436c2-112">To use this SQL Server Agent object, users must be a member of the **sysadmin** fixed server role.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="436c2-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="436c2-113">See Also</span></span>  
 <span data-ttu-id="436c2-114">[Alerts](../../ssms/agent/alerts.md) </span><span class="sxs-lookup"><span data-stu-id="436c2-114">[Alerts](../../ssms/agent/alerts.md) </span></span>  
 <span data-ttu-id="436c2-115">[Usar objetos de desempenho](../../ssms/agent/use-performance-objects.md) </span><span class="sxs-lookup"><span data-stu-id="436c2-115">[Use Performance Objects](../../ssms/agent/use-performance-objects.md) </span></span>  
 [<span data-ttu-id="436c2-116">Monitorar o uso de recursos &#40;Monitor do Sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="436c2-116">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
