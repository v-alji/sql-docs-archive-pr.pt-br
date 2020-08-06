---
title: Estabelecer uma linha de base de desempenho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- database performance [SQL Server], baselines
- monitoring performance [SQL Server], baselines
- tuning databases [SQL Server], baselines
- server performance [SQL Server], baselines
- performance [SQL Server], baselines
- baseline performance [SQL Server]
- measurements for baseline statistics [SQL Server]
- monitoring server performance [SQL Server], establishing baseline
- database monitoring [SQL Server], baselines
ms.assetid: dc5aa8d6-2507-448f-ad86-4196443915fc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0cb85ae8ad370b816c6240b58aabd247c7593c16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679306"
---
# <a name="establish-a-performance-baseline"></a><span data-ttu-id="723a8-102">Estabelecer uma linha de base de desempenho</span><span class="sxs-lookup"><span data-stu-id="723a8-102">Establish a Performance Baseline</span></span>
  <span data-ttu-id="723a8-103">Para determinar se o sistema do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está com desempenho ótimo, meça o desempenho a intervalos regulares, mesmo quando não houver problemas, para estabelecer uma linha de base para o desempenho do servidor.</span><span class="sxs-lookup"><span data-stu-id="723a8-103">To determine whether your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system is performing optimally, take performance measurements at regular intervals over time, even when no problems occur, to establish a server performance baseline.</span></span> <span data-ttu-id="723a8-104">Compare cada novo de conjuntos de medidas com os anteriores.</span><span class="sxs-lookup"><span data-stu-id="723a8-104">Compare each new set of measurements with those taken earlier.</span></span>  
  
 <span data-ttu-id="723a8-105">As seguintes áreas afetam o desempenho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="723a8-105">The following areas affect the performance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="723a8-106">Recursos do sistema (hardware)</span><span class="sxs-lookup"><span data-stu-id="723a8-106">System resources (hardware)</span></span>  
  
-   <span data-ttu-id="723a8-107">Arquitetura de rede</span><span class="sxs-lookup"><span data-stu-id="723a8-107">Network architecture</span></span>  
  
-   <span data-ttu-id="723a8-108">O sistema operacional</span><span class="sxs-lookup"><span data-stu-id="723a8-108">The operating system</span></span>  
  
-   <span data-ttu-id="723a8-109">Aplicativos de banco de dados</span><span class="sxs-lookup"><span data-stu-id="723a8-109">Database applications</span></span>  
  
-   <span data-ttu-id="723a8-110">Aplicativos cliente</span><span class="sxs-lookup"><span data-stu-id="723a8-110">Client applications</span></span>  
  
 <span data-ttu-id="723a8-111">No mínimo, use medidas de linha de base para determinar:</span><span class="sxs-lookup"><span data-stu-id="723a8-111">At a minimum, use baseline measurements to determine:</span></span>  
  
-   <span data-ttu-id="723a8-112">Horas de pico e fora de pico da operação.</span><span class="sxs-lookup"><span data-stu-id="723a8-112">Peak and off-peak hours of operation.</span></span>  
  
-   <span data-ttu-id="723a8-113">Tempos de resposta a consultas de produção ou comandos de lote.</span><span class="sxs-lookup"><span data-stu-id="723a8-113">Production-query or batch-command response times.</span></span>  
  
-   <span data-ttu-id="723a8-114">Tempos de conclusão de backup e restauração de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="723a8-114">Database backup and restore completion times.</span></span>  
  
 <span data-ttu-id="723a8-115">Tendo estabelecido uma linha de base para o desempenho do servidor, compare as estatísticas da linha de base com o desempenho atual do servidor.</span><span class="sxs-lookup"><span data-stu-id="723a8-115">After you establish a server performance baseline, compare the baseline statistics to current server performance.</span></span> <span data-ttu-id="723a8-116">Números muito acima ou muito abaixo da linha de base são candidatos a investigação extra.</span><span class="sxs-lookup"><span data-stu-id="723a8-116">Numbers far above or far below your baseline are candidates for further investigation.</span></span> <span data-ttu-id="723a8-117">Eles podem indicar áreas que necessitam de ajuste ou reconfiguração.</span><span class="sxs-lookup"><span data-stu-id="723a8-117">They may indicate areas in need of tuning or reconfiguration.</span></span> <span data-ttu-id="723a8-118">Por exemplo, se o tempo necessário para executar um conjunto de consultas aumentar, examine as consultas para determinar se podem ser reescritas ou se devem ser adicionadas estatísticas de colunas ou novos índices.</span><span class="sxs-lookup"><span data-stu-id="723a8-118">For example, if the amount of time to execute a set of queries increases, examine the queries to determine if they can be rewritten, or if column statistics or new indexes must be added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="723a8-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="723a8-119">See Also</span></span>  
 [<span data-ttu-id="723a8-120">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="723a8-120">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
