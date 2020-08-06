---
title: Criar um alerta de banco de dados do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- database performance [SQL Server], alerts
- alerts [SQL Server], creating
- thresholds [SQL Server]
- database alerts [SQL Server]
- tuning databases [SQL Server], alerts
- monitoring performance [SQL Server], alerts
- monitoring server performance [SQL Server], alerts
- database monitoring [SQL Server], alerts
- server performance [SQL Server], alerts
ms.assetid: 0511136a-1b6b-4095-aa45-39e77b67aba2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fd0cc926412d64f7686744ee60840a32473d2386
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684672"
---
# <a name="create-a-sql-server-database-alert"></a><span data-ttu-id="772b9-102">Criar um alerta de banco de dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="772b9-102">Create a SQL Server Database Alert</span></span>
  <span data-ttu-id="772b9-103">É possível usar o Monitor do Sistema para criar um alerta a ser emitido quando um valor limite de um contador do Monitor do Sistema for atingido.</span><span class="sxs-lookup"><span data-stu-id="772b9-103">You can use System Monitor to create an alert that is raised when a threshold value for a System Monitor counter has been reached.</span></span> <span data-ttu-id="772b9-104">Em resposta ao alerta, o Monitor do Sistema inicia um aplicativo, tal como um aplicativo cliente escrito para manipular a condição de alerta.</span><span class="sxs-lookup"><span data-stu-id="772b9-104">In response to the alert, System Monitor launches an application, such as a custom application written to handle the alert condition.</span></span> <span data-ttu-id="772b9-105">Por exemplo, você pode criar um alerta a ser emitido quando o número de deadlocks exceder um valor específico.</span><span class="sxs-lookup"><span data-stu-id="772b9-105">For example, you could create an alert that is raised when the number of deadlocks exceeds a specific value.</span></span>  
  
 <span data-ttu-id="772b9-106">Também podem ser definidos alertas por meio do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="772b9-106">Alerts also can be defined by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="772b9-107">Para obter mais informações, consulte [Alertas](../../ssms/agent/alerts.md).</span><span class="sxs-lookup"><span data-stu-id="772b9-107">For more information, see [Alerts](../../ssms/agent/alerts.md).</span></span>  
  
 <span data-ttu-id="772b9-108">Para obter mais informações sobre como usar o Monitor do Sistema para configurar um alerta de banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consulte [Configurar um alerta de banco de dados do SQL Server &#40;Windows&#41;](../performance/set-up-a-sql-server-database-alert-windows.md).</span><span class="sxs-lookup"><span data-stu-id="772b9-108">For more information about using System Monitor to set up a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database alert, see [Set Up a SQL Server Database Alert &#40;Windows&#41;](../performance/set-up-a-sql-server-database-alert-windows.md) .</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="772b9-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="772b9-109">See Also</span></span>  
 <span data-ttu-id="772b9-110">[sp_add_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="772b9-110">[sp_add_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql) </span></span>  
 [<span data-ttu-id="772b9-111">sys.sysperfinfo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="772b9-111">sys.sysperfinfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-compatibility-views/sys-sysperfinfo-transact-sql)  
  
  
