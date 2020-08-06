---
title: MSSQL_REPL027183 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_REPL027183 error
ms.assetid: 52c271ac-1a0e-43d5-85d4-35886d1efd32
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4484318cd6ec6ff4f0b201be69dc9b7544dd2c2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685543"
---
# <a name="mssql_repl027183"></a><span data-ttu-id="cd88e-102">MSSQL_REPL027183</span><span class="sxs-lookup"><span data-stu-id="cd88e-102">MSSQL_REPL027183</span></span>
    
## <a name="message-details"></a><span data-ttu-id="cd88e-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="cd88e-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cd88e-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="cd88e-104">Product Name</span></span>|<span data-ttu-id="cd88e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="cd88e-105">SQL Server</span></span>|  
|<span data-ttu-id="cd88e-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="cd88e-106">Event ID</span></span>|<span data-ttu-id="cd88e-107">27183</span><span class="sxs-lookup"><span data-stu-id="cd88e-107">27183</span></span>|  
|<span data-ttu-id="cd88e-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="cd88e-108">Event Source</span></span>|<span data-ttu-id="cd88e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cd88e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cd88e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="cd88e-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="cd88e-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="cd88e-111">Symbolic Name</span></span>||  
|<span data-ttu-id="cd88e-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="cd88e-112">Message Text</span></span>|<span data-ttu-id="cd88e-113">O processo de mesclagem não pôde enumerar as alterações nos artigos que apresentaram filtros de linha com parâmetros.</span><span class="sxs-lookup"><span data-stu-id="cd88e-113">The merge process failed to enumerate changes in articles with parameterized row filters.</span></span> <span data-ttu-id="cd88e-114">Se a falha persistir, aumente o tempo limite da consulta nesse processo, reduza o período de retenção da publicação e aprimore os índices nas tabelas publicadas.</span><span class="sxs-lookup"><span data-stu-id="cd88e-114">If this failure continues, increase the query timeout for this process, reduce the retention period for the publication, and improve indexes on published tables.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cd88e-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="cd88e-115">Explanation</span></span>  
 <span data-ttu-id="cd88e-116">Esse erro surge quando o tempo limite do Merge Agent ocorre durante o processamento de alterações em uma publicação filtrada.</span><span class="sxs-lookup"><span data-stu-id="cd88e-116">This error is raised if a Merge Agent timeout occurs while processing changes in a filtered publication.</span></span> <span data-ttu-id="cd88e-117">O tempo limite pode ser causado por um dos seguintes problemas:</span><span class="sxs-lookup"><span data-stu-id="cd88e-117">The timeout might be caused by one of the following issues:</span></span>  
  
-   <span data-ttu-id="cd88e-118">A otimização das partições pré-computadas não está sendo usada.</span><span class="sxs-lookup"><span data-stu-id="cd88e-118">Not using the precomputed partitions optimization.</span></span>  
  
-   <span data-ttu-id="cd88e-119">Fragmentação de índice em colunas usadas para filtragem.</span><span class="sxs-lookup"><span data-stu-id="cd88e-119">Index fragmentation on columns used for filtering.</span></span>  
  
-   <span data-ttu-id="cd88e-120">Tabelas de metadados de mesclagens grandes, como **MSmerge_tombstone**, **MSmerge_contents**e **MSmerge_genhistory**.</span><span class="sxs-lookup"><span data-stu-id="cd88e-120">Large merge metadata tables, such as **MSmerge_tombstone**, **MSmerge_contents**, and **MSmerge_genhistory**.</span></span>  
  
-   <span data-ttu-id="cd88e-121">Tabelas filtradas não associadas em uma chave exclusiva e associação de filtros que envolvem um grande número de tabelas.</span><span class="sxs-lookup"><span data-stu-id="cd88e-121">Filtered tables that are not joined on a unique key and join filters that involve a large number of tables.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cd88e-122">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="cd88e-122">User Action</span></span>  
 <span data-ttu-id="cd88e-123">Como resolver o problema:</span><span class="sxs-lookup"><span data-stu-id="cd88e-123">To resolve the issue:</span></span>  
  
-   <span data-ttu-id="cd88e-124">Aumente o valor do parâmetro **-QueryTimeOut** do Agente de Mesclagem para permitir que o processamento continue enquanto você aborda os problemas subjacentes que estão provocando o erro.</span><span class="sxs-lookup"><span data-stu-id="cd88e-124">Increase the value of the **-QueryTimeOut** parameter for the Merge Agent to allow processing to continue while you address the underlying issues causing the error.</span></span> <span data-ttu-id="cd88e-125">Os parâmetros de agente podem ser especificados em perfis de agente e na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="cd88e-125">Agent parameters can be specified in agent profiles and on the command line.</span></span> <span data-ttu-id="cd88e-126">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="cd88e-126">For more information, see:</span></span>  
  
    -   [<span data-ttu-id="cd88e-127">Trabalhar com perfis do Agente de Replicação</span><span class="sxs-lookup"><span data-stu-id="cd88e-127">Work with Replication Agent Profiles</span></span>](agents/replication-agent-profiles.md)  
  
    -   [<span data-ttu-id="cd88e-128">Exibir e modificar parâmetros do prompt de comando de agentes de replicação &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="cd88e-128">View and Modify Replication Agent Command Prompt Parameters &#40;SQL Server Management Studio&#41;</span></span>](agents/view-and-modify-replication-agent-command-prompt-parameters.md)  
  
    -   <span data-ttu-id="cd88e-129">[Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="cd88e-129">[Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
-   <span data-ttu-id="cd88e-130">Use a otimização de partições pré-computadas, se possível.</span><span class="sxs-lookup"><span data-stu-id="cd88e-130">Use the precomputed partitions optimization if possible.</span></span> <span data-ttu-id="cd88e-131">Por padrão, essa otimização será usada se um número de requisitos de publicação forem atendidos.</span><span class="sxs-lookup"><span data-stu-id="cd88e-131">This optimization is used by default if a number of publication requirements are met.</span></span> <span data-ttu-id="cd88e-132">Para obter mais informações sobre esses requisitos, consulte [Otimizar o desempenho de filtro com parâmetros com partições pré-computadas](merge/parameterized-filters-optimize-for-precomputed-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="cd88e-132">For more information about these requirements, see [Optimize Parameterized Filter Performance with Precomputed Partitions](merge/parameterized-filters-optimize-for-precomputed-partitions.md).</span></span> <span data-ttu-id="cd88e-133">Se a publicação não satisfizer esses requisitos, considere reprojetar a publicação.</span><span class="sxs-lookup"><span data-stu-id="cd88e-133">If the publication does not meet these requirements, consider redesigning the publication.</span></span>  
  
-   <span data-ttu-id="cd88e-134">Especifique a menor definição possível para o período de retenção da publicação, porque a replicação não poderá limpar os metadados nos bancos de dados de assinatura e publicação antes do período de retenção ser atingido.</span><span class="sxs-lookup"><span data-stu-id="cd88e-134">Specify the lowest setting possible for the publication retention period, because replication cannot clean up metadata in the publication and subscription databases until the retention period is reached.</span></span> <span data-ttu-id="cd88e-135">Para obter mais informações, consulte [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="cd88e-135">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
-   <span data-ttu-id="cd88e-136">Como parte da manutenção da replicação de mesclagem, verifique esporadicamente o crescimento das tabelas do sistema associadas à replicação de mesclagem: **MSmerge_contents**, **MSmerge_genhistory**, **MSmerge_tombstone**, **MSmerge_current_partition_mappings**e **MSmerge_past_partition_mappings**.</span><span class="sxs-lookup"><span data-stu-id="cd88e-136">As part of maintenance for merge replication, occasionally check the growth of the system tables associated with merge replication: **MSmerge_contents**, **MSmerge_genhistory**, and **MSmerge_tombstone**, **MSmerge_current_partition_mappings**, and **MSmerge_past_partition_mappings**.</span></span> <span data-ttu-id="cd88e-137">Periodicamente, indexe novamente essas tabelas.</span><span class="sxs-lookup"><span data-stu-id="cd88e-137">Periodically re-index these tables.</span></span> <span data-ttu-id="cd88e-138">Para obter mais informações, veja [Reorganizar e recriar índices](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="cd88e-138">For more information, see [Reorganize and Rebuild Indexes](../indexes/indexes.md).</span></span>  
  
-   <span data-ttu-id="cd88e-139">Certifique-se de que as colunas usadas para filtragem estejam indexadas corretamente e reconstrua tais índices, se necessário.</span><span class="sxs-lookup"><span data-stu-id="cd88e-139">Ensure that columns used for filtering are properly indexed and rebuild such indexes if necessary.</span></span> <span data-ttu-id="cd88e-140">Para obter mais informações, veja [Reorganizar e recriar índices](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="cd88e-140">For more information, see [Reorganize and Rebuild Indexes](../indexes/indexes.md).</span></span>  
  
-   <span data-ttu-id="cd88e-141">Defina a propriedade **join_unique_key** para filtros de junção com base em colunas exclusivas.</span><span class="sxs-lookup"><span data-stu-id="cd88e-141">Set the **join_unique_key** property for join filters that are based on unique columns.</span></span> <span data-ttu-id="cd88e-142">Para obter mais informações, consulte [Join Filters](merge/join-filters.md).</span><span class="sxs-lookup"><span data-stu-id="cd88e-142">For more information, see [Join Filters](merge/join-filters.md).</span></span>  
  
-   <span data-ttu-id="cd88e-143">Limite o número de tabelas na hierarquia de filtro de junção.</span><span class="sxs-lookup"><span data-stu-id="cd88e-143">Limit the number of tables in the join filter hierarchy.</span></span> <span data-ttu-id="cd88e-144">Se você estiver gerando filtros de junção de cinco ou mais tabelas, considere outras soluções: não filtre tabelas pequenas, que não estão sujeitas a alterações ou que sejam basicamente tabelas de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="cd88e-144">If you are generating join filters of five or more tables, consider other solutions: do not filter tables that are small, not subject to change, or are primarily lookup tables.</span></span> <span data-ttu-id="cd88e-145">Use filtros de junção somente entre tabelas que devem ser particionadas entre assinaturas.</span><span class="sxs-lookup"><span data-stu-id="cd88e-145">Use join filters only between tables that must be partitioned among subscriptions.</span></span>  
  
-   <span data-ttu-id="cd88e-146">Faça um número menor de alterações em tabelas filtradas entre as sincronizações ou execute o Merge Agent mais frequentemente.</span><span class="sxs-lookup"><span data-stu-id="cd88e-146">Make a smaller number of changes on filtered tables between synchronizations, or run the Merge Agent more frequently.</span></span> <span data-ttu-id="cd88e-147">Para obter mais informações sobre como definir agendas de sincronização, consulte [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="cd88e-147">For more information about setting synchronization schedules, see [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd88e-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cd88e-148">See Also</span></span>  
 [<span data-ttu-id="cd88e-149">Referência de erros e eventos &#40;Replicação&#41;</span><span class="sxs-lookup"><span data-stu-id="cd88e-149">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
