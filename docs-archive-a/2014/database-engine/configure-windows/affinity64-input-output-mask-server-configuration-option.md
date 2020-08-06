---
title: Opção de configuração de servidor affinity64 Input-Output mask | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- processor affinity [SQL Server]
- binding processors [SQL Server]
- affinity64 I/O mask option
ms.assetid: d304eae7-5116-40ee-a0fa-0a3c0bc20c01
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 19616f5718254bde5601ea1beeec21412ad867de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575355"
---
# <a name="affinity64-input-output-mask-server-configuration-option"></a><span data-ttu-id="5b095-102">Opção de configuração do servidor affinity64 I/O mask</span><span class="sxs-lookup"><span data-stu-id="5b095-102">affinity64 Input-Output mask Server Configuration Option</span></span>
  <span data-ttu-id="5b095-103">A **affinity64 I/O mask** associa a E/S de disco do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a um subconjunto especificado de CPUs, de forma semelhante à opção **affinity I/O mask** .</span><span class="sxs-lookup"><span data-stu-id="5b095-103">The **affinity64 I/O mask** binds [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disk I/O to a specified subset of CPUs, similar to the **affinity I/O mask** option.</span></span> <span data-ttu-id="5b095-104">Use **affinity I/O mask** para associar os primeiros 32 processadores e use **affinity64 I/O mask** para associar os processadores restantes no computador.</span><span class="sxs-lookup"><span data-stu-id="5b095-104">Use **affinity I/O mask** to bind the first 32 processors, and use **affinity64 I/O mask** to bind the remaining processors on the computer.</span></span> <span data-ttu-id="5b095-105">Se você reconfigurar a **affinity64 I/O mask**, será necessário reinicializar a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b095-105">If you reconfigure the **affinity64 I/O mask**, you must restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5b095-106">Esta opção é visível somente na versão de 64 bits do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b095-106">This option is only visible on the 64-bit version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b095-107">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5b095-107">See Also</span></span>  
 <span data-ttu-id="5b095-108">[Opção de configuração do servidor de máscara de Entrada-Saída de afinidade](affinity-input-output-mask-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="5b095-108">[affinity Input-Output mask Server Configuration Option](affinity-input-output-mask-server-configuration-option.md) </span></span>  
 <span data-ttu-id="5b095-109">[Monitorar o uso de recursos &#40;Monitor do Sistema&#41;](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="5b095-109">[Monitor Resource Usage &#40;System Monitor&#41;](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md) </span></span>  
 <span data-ttu-id="5b095-110">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5b095-110">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="5b095-111">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5b095-111">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="5b095-112">RECONFIGURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5b095-112">RECONFIGURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reconfigure-transact-sql)  
  
  
