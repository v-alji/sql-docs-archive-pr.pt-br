---
title: Armazenar conjuntos de dados compartilhados em cache (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4acb1bbe-1c04-4979-b893-dc1b1c5039b6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5b08149b075ae3fd267baf2dad0ca342457958c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575617"
---
# <a name="cache-shared-datasets-ssrs"></a><span data-ttu-id="4f7ff-102">Conjuntos de dados compartilhado em cache (SSRS)</span><span class="sxs-lookup"><span data-stu-id="4f7ff-102">Cache Shared Datasets (SSRS)</span></span>
  <span data-ttu-id="4f7ff-103">Os resultados de consultas de um conjunto de dados compartilhado podem ser copiados para um cache para fornecer dados consistentes para vários relatórios e melhorar o tempo de resposta da consulta do conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-103">Query results for a shared dataset can be copied to a cache to provide consistent data for multiple reports and to improve response time for the dataset query.</span></span> <span data-ttu-id="4f7ff-104">Como relatórios, você pode configurar um conjunto de dados compartilhado para ser armazenado em cache no primeiro uso ou especificando uma agenda.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-104">Like reports, you can configure a shared dataset to be cached on first use or by specifying a schedule.</span></span>  
  
 <span data-ttu-id="4f7ff-105">Um conjunto de dados compartilhado pode ser incluído em vários relatórios ou como parte de definições de componente.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-105">A shared dataset can be included in multiple reports or as part of component definitions.</span></span> <span data-ttu-id="4f7ff-106">Armazenando em cache o conjunto de dados compartilhado, você fornece um conjunto de dados consistente para todos os relatórios que o usam e também reduz o número de vezes que a consulta de conjunto de dados é executada em relação à fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-106">By caching the shared dataset, you provide a consistent set of data for all reports that use it, and also reduce the number of times that the dataset query runs against the external data source.</span></span>  
  
 <span data-ttu-id="4f7ff-107">A lista a seguir fornece exemplos de quando armazenar em cache um conjunto de dados compartilhado:</span><span class="sxs-lookup"><span data-stu-id="4f7ff-107">The following list provides examples of when to cache a shared dataset:</span></span>  
  
-   <span data-ttu-id="4f7ff-108">A consulta leva uma quantidade significativa de tempo para ser executada.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-108">The query takes a substantial amount of time to run.</span></span>  
  
-   <span data-ttu-id="4f7ff-109">A consulta usa parâmetros, mas na maior parte do tempo, o número de combinações de parâmetros é pequeno.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-109">The query takes parameters, but most of the time, the number of parameter combinations is small.</span></span> <span data-ttu-id="4f7ff-110">Cada combinação cria resultados da consulta armazenados em cache.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-110">Each combination creates cached query results.</span></span>  
  
-   <span data-ttu-id="4f7ff-111">A consulta é executada em horas previsíveis do dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-111">The query runs at predictable times of the day, week, or month.</span></span>  
  
-   <span data-ttu-id="4f7ff-112">A consulta é executada como o resultado de uma referência de conjunto de dados compartilhado em um relatório que é entregue por email, onde é provável que um grande número de pessoas clique no link em um curto período de tempo.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-112">The query runs as the result of a shared dataset reference in a report that is delivered via e-mail, where a large number of people are likely to click the link in a short span of time.</span></span>  
  
-   <span data-ttu-id="4f7ff-113">A lista a seguir fornece exemplos de quando não armazenar em cache um conjunto de dados compartilhado:</span><span class="sxs-lookup"><span data-stu-id="4f7ff-113">The following list provides examples of when not to cache a shared dataset:</span></span>  
  
-   <span data-ttu-id="4f7ff-114">Os resultados da consulta devem sempre incluir os dados mais recentes.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-114">The query results must always include the most recent data.</span></span>  
  
-   <span data-ttu-id="4f7ff-115">A consulta é executada rapidamente.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-115">The query runs quickly.</span></span>  
  
-   <span data-ttu-id="4f7ff-116">A consulta é executada com pouca frequência.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-116">The query runs infrequently.</span></span>  
  
-   <span data-ttu-id="4f7ff-117">A consulta usa parâmetros, o número de combinações de parâmetros é grande e nenhuma combinação é mais provável que a outra.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-117">The query takes parameters, the number of parameter combinations is large, and no combination is more likely than another.</span></span>  
  
-   <span data-ttu-id="4f7ff-118">A fonte de dados na qual o conjunto de dados compartilhado é baseado tem Prompt ou credenciais do Windows Integrado.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-118">The data source that the shared dataset is based on has Prompt or Windows Integrated credentials.</span></span>  
  
-   <span data-ttu-id="4f7ff-119">O filtro ou a consulta do conjunto de dados compartilhado contém uma expressão com uma referência à coleção global Usuário.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-119">The shared dataset filter or the query contains an expression with a reference to the global collection User.</span></span>  
  
 <span data-ttu-id="4f7ff-120">Se um usuário escolher valores de parâmetros de relatório diferentes dos valores padrão especificados para o conjunto de resultados armazenado em cache, a consulta do conjunto de dados será executada ativamente e os resultados armazenados em cache não serão usados para essa consulta.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-120">If a user chooses report parameter values that differ from the default values that are specified for the cached result set, the dataset query runs actively and the cached results are not used for that query.</span></span>  
  
## <a name="caching-shared-datasets"></a><span data-ttu-id="4f7ff-121">Armazenando em cache conjuntos de dados compartilhados</span><span class="sxs-lookup"><span data-stu-id="4f7ff-121">Caching Shared Datasets</span></span>  
 <span data-ttu-id="4f7ff-122">Para habilitar o armazenamento em cache de um conjunto de dados compartilhado, você deve selecionar a opção de cache no conjunto de dados compartilhado.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-122">To enable caching for a shared dataset, you must select the cache option on the shared dataset.</span></span> <span data-ttu-id="4f7ff-123">Depois que o armazenamento em cache é habilitado, os resultados da consulta de um conjunto de dados compartilhado são copiados no cache no primeiro uso.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-123">After caching is enabled, the query results for a shared dataset are copied to the cache on first use.</span></span> <span data-ttu-id="4f7ff-124">Se o conjunto de dados compartilhado tiver parâmetros, cada combinação de parâmetros criará uma nova entrada no cache.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-124">If the shared dataset has parameters, each combination of parameters creates a new entry in the cache.</span></span>  
  
 <span data-ttu-id="4f7ff-125">Enquanto os resultados da consulta para uma combinação de parâmetros específica estão no cache, cada relatório iniciado para processamento e que inclui uma referência ao conjunto de dados compartilhado com esses valores de parâmetros usará os dados armazenados em cache.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-125">While the query results for a specific parameter combination are in the cache, each report that is launched for processing and that includes a reference to the shared dataset with those parameter values will use the cached data.</span></span>  
  
 <span data-ttu-id="4f7ff-126">Você pode especificar por quanto tempo os dados devem ser mantidos no cache antes de expirarem.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-126">You can specify how long to keep data in the cache before it expires.</span></span> <span data-ttu-id="4f7ff-127">Para obter mais informações, consulte [Página cache, conjuntos de dados compartilhados &#40;Gerenciador de relatórios&#41;](../caching-page-shared-datasets-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="4f7ff-127">For more information, see [Caching Page, Shared Datasets &#40;Report Manager&#41;](../caching-page-shared-datasets-report-manager.md).</span></span>  
  
## <a name="preloading-the-cache"></a><span data-ttu-id="4f7ff-128">Pré-carregando o cache</span><span class="sxs-lookup"><span data-stu-id="4f7ff-128">Preloading the Cache</span></span>  
 <span data-ttu-id="4f7ff-129">Você pode pré-carregar o cache criando um plano de atualização de cache.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-129">You can preload the cache by creating a cache refresh plan.</span></span> <span data-ttu-id="4f7ff-130">Com um plano de atualização, você pode especificar com que frequência atualizar o cache usando uma agenda específica de item ou uma agenda compartilhada.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-130">With a refresh plan, you can specify how often to refresh the cache by using an item-specific schedule or a shared schedule.</span></span> <span data-ttu-id="4f7ff-131">Para evitar várias entradas no cache para o mesmo item, a agenda especificada deve permitir tempo de processamento suficiente para o processamento da consulta na fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-131">To avoid multiple cache entries for the same item, the schedule that you specify should allow enough time for query processing on the external data source.</span></span> <span data-ttu-id="4f7ff-132">Por exemplo, se a consulta levar 20 minutos para ser executada, a agenda de atualização deverá ser maior que 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-132">For example, if the query takes 20 minutes to run, the refresh schedule should be greater than 20 minutes.</span></span> <span data-ttu-id="4f7ff-133">Para obter mais informações, consulte [Schedules](../subscriptions/schedules.md).</span><span class="sxs-lookup"><span data-stu-id="4f7ff-133">For more information, see [Schedules](../subscriptions/schedules.md).</span></span>  
  
 <span data-ttu-id="4f7ff-134">Para criar um plano de atualização de cache para um conjunto de dados compartilhado, as seguintes condições são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-134">To create a cache refresh plan for a shared dataset, the following conditions apply.</span></span>  
  
-   <span data-ttu-id="4f7ff-135">O conjunto de dados compartilhado deve estar habilitado para armazenamento em cache.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-135">The shared dataset must be enabled for caching.</span></span>  
  
-   <span data-ttu-id="4f7ff-136">A fonte de dados compartilhada da qual o conjunto de dados compartilhado depende não pode usar Prompt ou credenciais do Windows Integrado.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-136">The shared data source that the shared dataset depends on cannot use Prompt or Windows Integrated credentials.</span></span>  
  
-   <span data-ttu-id="4f7ff-137">Se o conjunto de dados compartilhado tiver parâmetros, você deverá especificar valores padrão estáticos para cada parâmetro que não esteja marcado como somente leitura.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-137">If the shared dataset has parameters, you must specify static default values for each parameter that is not marked read-only.</span></span> <span data-ttu-id="4f7ff-138">Parâmetros somente leitura sempre usarão o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-138">Read-only parameters will always use the default value.</span></span> <span data-ttu-id="4f7ff-139">Para armazenar em cache um conjunto de dados compartilhado para várias combinações de parâmetros, você deve criar um plano de atualização de cache separado para cada combinação.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-139">To cache a shared dataset for multiple combinations of parameters, you must create a separate cache refresh plan for each combination of values.</span></span> <span data-ttu-id="4f7ff-140">Parâmetros não podem conter referências a outros conjuntos de dados.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-140">Parameters cannot contain references to other datasets.</span></span>  
  
-   <span data-ttu-id="4f7ff-141">Cada plano de atualização do cache está associado a apenas um conjunto de dados compartilhado ou relatório.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-141">Each cache refresh plan is associated with only one shared dataset or report.</span></span>  
  
-   <span data-ttu-id="4f7ff-142">Você deve ter as permissões ReadPolicy e UpdatePolicy no conjunto de dados compartilhado.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-142">You must have ReadPolicy and UpdatePolicy permissions on the shared dataset.</span></span>  
  
 <span data-ttu-id="4f7ff-143">Os planos de atualização do cache se aplicam a conjuntos de dados compartilhados e relatórios.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-143">Cache refresh plans apply to both shared datasets and reports.</span></span> <span data-ttu-id="4f7ff-144">Para obter mais informações, consulte [Opções de atualização do cache &#40;Gerenciador de Relatórios&#41;](../cache-refresh-options-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="4f7ff-144">For more information, see [Cache Refresh Options &#40;Report Manager&#41;](../cache-refresh-options-report-manager.md).</span></span>  
  
## <a name="conditions-that-cause-cache-expiration"></a><span data-ttu-id="4f7ff-145">Condições que provocam a expiração do cache</span><span class="sxs-lookup"><span data-stu-id="4f7ff-145">Conditions that Cause Cache Expiration</span></span>  
 <span data-ttu-id="4f7ff-146">As condições a seguir podem fazer com que um cache de conjunto de dados compartilhado se torne inválido.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-146">The following conditions can cause a shared dataset cache to become not valid.</span></span>  
  
-   <span data-ttu-id="4f7ff-147">Uma condição de agenda expira.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-147">A schedule condition expires.</span></span> <span data-ttu-id="4f7ff-148">O tempo limite do cache é esgotado ou o tempo de expiração ocorre.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-148">The cache times out or the expiration time occurs.</span></span>  
  
-   <span data-ttu-id="4f7ff-149">Uma agenda compartilhada é excluída.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-149">A shared schedule is deleted.</span></span>  
  
-   <span data-ttu-id="4f7ff-150">Alterações em uma agenda compartilhada.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-150">Changes to a shared schedule.</span></span> <span data-ttu-id="4f7ff-151">Agendas compartilhadas podem ser pausadas, o que também afeta quando um cache expira.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-151">Shared schedules can be paused, which also affects when a cache expires.</span></span>  
  
-   <span data-ttu-id="4f7ff-152">A definição de consulta do conjunto de dados compartilhado é alterada.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-152">The query definition for the shared dataset changes.</span></span>  
  
-   <span data-ttu-id="4f7ff-153">As credenciais da fonte de dados compartilhada da qual o conjunto de dados compartilhado depende são alteradas.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-153">The credentials for the shared data source that the shared dataset depends on change.</span></span>  
  
-   <span data-ttu-id="4f7ff-154">As opções de cache do conjunto de dados compartilhado são alteradas.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-154">The cache options for the shared dataset change.</span></span>  
  
-   <span data-ttu-id="4f7ff-155">Os valores padrão dos parâmetros somente leitura do conjunto de dados compartilhado são alterados.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-155">The default values for read-only parameters for the shared dataset change.</span></span>  
  
-   <span data-ttu-id="4f7ff-156">Os filtros que fazem parte da definição do conjunto de dados compartilhado são alterados.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-156">The filters that are part of the shared dataset definition change.</span></span>  
  
-   <span data-ttu-id="4f7ff-157">O conjunto de dados compartilhado é excluído do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-157">The shared dataset is deleted from the report server.</span></span> <span data-ttu-id="4f7ff-158">Quando um conjunto de dados compartilhado é excluído, as cópias armazenadas em cache associadas e os planos de atualização de cache também são excluídos.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-158">When a shared dataset is deleted, associated cached copies and cache refresh plans are also deleted.</span></span>  
  
 <span data-ttu-id="4f7ff-159">As atualizações nos planos de atualização do cache de conjuntos de dados compartilhados não afetam os relatórios que já estão sendo processados.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-159">Updates to cache refresh plans for shared datasets do not affect reports that are already being processed.</span></span> <span data-ttu-id="4f7ff-160">A atualização de um plano de atualização do cache afeta apenas inicializações futuras de relatórios que fazem referência ao conjunto de dados compartilhado.</span><span class="sxs-lookup"><span data-stu-id="4f7ff-160">Updating a cache refresh plan affects only future launches of reports that reference the shared dataset.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f7ff-161">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4f7ff-161">See Also</span></span>  
 [<span data-ttu-id="4f7ff-162">Gerenciar conjuntos de dados compartilhados</span><span class="sxs-lookup"><span data-stu-id="4f7ff-162">Manage Shared Datasets</span></span>](../report-data/manage-shared-datasets.md)  
  
  
