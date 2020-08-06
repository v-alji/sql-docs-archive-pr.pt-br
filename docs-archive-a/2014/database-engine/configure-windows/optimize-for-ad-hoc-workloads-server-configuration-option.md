---
title: Opção de configuração de servidor optimize for ad hoc workloads | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- optimize for ad hoc workloads option
ms.assetid: 0972e028-3a8e-454b-a186-e814a1d431f2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b217e48d6e4b0ffa0f687ff170f16d4d77ad17d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679517"
---
# <a name="optimize-for-ad-hoc-workloads-server-configuration-option"></a><span data-ttu-id="e3ac3-102">Opção de configuração de servidor optimize for ad hoc workloads</span><span class="sxs-lookup"><span data-stu-id="e3ac3-102">optimize for ad hoc workloads Server Configuration Option</span></span>
  <span data-ttu-id="e3ac3-103">A opção **otimizar para cargas de trabalho ad hoc** é usada para aperfeiçoar a eficiência do cache de planos para cargas de trabalho que contêm muitos lotes ad hoc de uso exclusivo.</span><span class="sxs-lookup"><span data-stu-id="e3ac3-103">The **optimize for ad hoc workloads** option is used to improve the efficiency of the plan cache for workloads that contain many single use ad hoc batches.</span></span> <span data-ttu-id="e3ac3-104">Quando essa opção está definida como 1, o [!INCLUDE[ssDE](../../includes/ssde-md.md)] armazena um pequeno stub de plano compilado no cache de planos quando um lote é compilado pela primeira vez, em vez do plano compilado completo.</span><span class="sxs-lookup"><span data-stu-id="e3ac3-104">When this option is set to 1, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] stores a small compiled plan stub in the plan cache when a batch is compiled for the first time, instead of the full compiled plan.</span></span> <span data-ttu-id="e3ac3-105">Isso ajuda a aliviar a pressão sobre a memória não permitindo que o cache de planos fique cheio de planos compilados que não serão reutilizados.</span><span class="sxs-lookup"><span data-stu-id="e3ac3-105">This helps to relieve memory pressure by not allowing the plan cache to become filled with compiled plans that are not reused.</span></span>  
  
 <span data-ttu-id="e3ac3-106">O stub de plano compilado permite que o [!INCLUDE[ssDE](../../includes/ssde-md.md)] reconheça que esse lote ad hoc foi compilado antes, mas somente armazenou um stub de plano compilado, portanto, quando esse lote é invocado (compilado ou executado) novamente, o [!INCLUDE[ssDE](../../includes/ssde-md.md)] compila o lote, remove o stub de plano compilado do cache de planos e adiciona o plano compilado completo ao cache de planos.</span><span class="sxs-lookup"><span data-stu-id="e3ac3-106">The compiled plan stub allows the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to recognize that this ad hoc batch has been compiled before but has only stored a compiled plan stub, so when this batch is invoked (compiled or executed) again, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] compiles the batch, removes the compiled plan stub from the plan cache, and adds the full compiled plan to the plan cache.</span></span>  
  
 <span data-ttu-id="e3ac3-107">Configurar a opção **otimizar para cargas de trabalho ad hoc** como 1 afeta apenas os planos novos; os planos que já estão no cache de planos não são afetados.</span><span class="sxs-lookup"><span data-stu-id="e3ac3-107">Setting the **optimize for ad hoc workloads** to 1 affects only new plans; plans that are already in the plan cache are unaffected.</span></span>  
  
 <span data-ttu-id="e3ac3-108">O stub de plano compilado é um dos cacheobjtypes exibidos pela exibição de catálogo sys.dm_exec_cached_plans.</span><span class="sxs-lookup"><span data-stu-id="e3ac3-108">The compiled plan stub is one of the cacheobjtypes displayed by the sys.dm_exec_cached_plans catalog view.</span></span> <span data-ttu-id="e3ac3-109">Ele tem identificadores sql e de plano exclusivos.</span><span class="sxs-lookup"><span data-stu-id="e3ac3-109">It has a unique sql handle and plan handle.</span></span> <span data-ttu-id="e3ac3-110">O stub de plano compilado não tem um plano de execução associado a ele e a consulta do identificador do plano não retornará um Showplan XML.</span><span class="sxs-lookup"><span data-stu-id="e3ac3-110">The compiled plan stub does not have an execution plan associated with it and querying for the plan handle will not return an XML Showplan.</span></span>  
  
 <span data-ttu-id="e3ac3-111">O sinalizador de rastreamento 8032 reverte os parâmetros de limite de cache para a configuração do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] RTM, que, em geral, permite que os caches sejam maiores.</span><span class="sxs-lookup"><span data-stu-id="e3ac3-111">Trace flag 8032 reverts the cache limit parameters to the [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] RTM setting which in general allows caches to be larger.</span></span> <span data-ttu-id="e3ac3-112">Use esta configuração quando entradas de cache reutilizadas com frequência não se ajustarem no cache e quando a *opção de configuração do servidor de otimizar para cargas de trabalho ad hoc* não tiver resolvido o problema com o cache do plano.</span><span class="sxs-lookup"><span data-stu-id="e3ac3-112">Use this setting when frequently reused cache entries do not fit into the cache and when the *optimize for ad hoc workloads Server Configuration Option* has failed to resolve the problem with plan cache.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="e3ac3-113">O sinalizador de rastreamento 8032 pode causar baixo desempenho se os caches grandes deixarem menos memória disponível para outros consumidores de memória, como o pool de buffers.</span><span class="sxs-lookup"><span data-stu-id="e3ac3-113">Trace flag 8032 can cause poor performance if large caches make less memory available for other memory consumers, such as the buffer pool.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3ac3-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e3ac3-114">See Also</span></span>  
 <span data-ttu-id="e3ac3-115">[sys.dm_exec_cached_plans &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-cached-plans-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e3ac3-115">[sys.dm_exec_cached_plans &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-cached-plans-transact-sql) </span></span>  
 [<span data-ttu-id="e3ac3-116">Opções de configuração do servidor &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e3ac3-116">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
