---
title: Opção de configuração de servidor affinity64 mask | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- processor affinity [SQL Server]
- affinity64 mask option
- binding processors [SQL Server]
ms.assetid: 75ed08c7-f85c-4e15-9ee1-e7bc545d3293
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d2ea6d2e364feaa67d91de0055617aac9dc285ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575353"
---
# <a name="affinity64-mask-server-configuration-option"></a><span data-ttu-id="7d450-102">Opção affinity64 mask de configuração de servidor</span><span class="sxs-lookup"><span data-stu-id="7d450-102">affinity64 mask Server Configuration Option</span></span>
  <span data-ttu-id="7d450-103">A opção affinity64 mask associa processadores a threads específicos, de modo semelhante à opção affinity mask.</span><span class="sxs-lookup"><span data-stu-id="7d450-103">The affinity64 mask binds processors to specific threads, similar to the affinity mask option.</span></span> <span data-ttu-id="7d450-104">Use a opção affinity mask para associar os primeiros 32 processadores e use affinity64 mask para associar os processadores restantes no computador.</span><span class="sxs-lookup"><span data-stu-id="7d450-104">Use affinity mask to bind the first 32 processors, and use affinity64 mask to bind the remaining processors on the computer.</span></span> <span data-ttu-id="7d450-105">Esta opção é visível somente na versão de 64 bits do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d450-105">This option is only visible on the 64-bit version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoteDepNextAvoid](../../includes/ssnotedepnextavoid-md.md)] <span data-ttu-id="7d450-106">Em vez disso, use [ALTER SERVER CONFIGURATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-server-configuration-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7d450-106">Use [ALTER SERVER CONFIGURATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-server-configuration-transact-sql) instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d450-107">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7d450-107">See Also</span></span>  
 <span data-ttu-id="7d450-108">[Opção affinity mask de configuração de servidor](affinity-mask-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="7d450-108">[affinity mask Server Configuration Option](affinity-mask-server-configuration-option.md) </span></span>  
 <span data-ttu-id="7d450-109">[Monitorar o uso de recursos &#40;Monitor do Sistema&#41;](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="7d450-109">[Monitor Resource Usage &#40;System Monitor&#41;](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md) </span></span>  
 <span data-ttu-id="7d450-110">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7d450-110">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="7d450-111">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7d450-111">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="7d450-112">RECONFIGURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7d450-112">RECONFIGURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reconfigure-transact-sql)  
  
  
