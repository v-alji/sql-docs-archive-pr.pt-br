---
title: Propriedades do banco de dados (página Repositório de Consultas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql13.swb.databaseproperties.querystore.f1
ms.assetid: da47d75e-291a-4305-acef-4b0aaf5215da
author: stevestein
ms.author: sstein
ms.openlocfilehash: bab0d9b697e9ad9ec4b27f320d26b9b9edb5944e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681678"
---
# <a name="database-properties-query-store-page"></a><span data-ttu-id="7eca5-102">Propriedades do banco de dados (página Repositório de Consultas)</span><span class="sxs-lookup"><span data-stu-id="7eca5-102">Database Properties (Query Store Page)</span></span>
  <span data-ttu-id="7eca5-103">Acesse esta página do banco de dados principal e use-a para configurar e modificar as propriedades do repositório de consultas do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7eca5-103">Access this page from the principal database, and use it to configure and to modify the properties of the database query store.</span></span> <span data-ttu-id="7eca5-104">Essas opções também podem ser configuradas usando as opções [ALTER DATABASE SET](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="7eca5-104">These options can also be configure by using the [ALTER DATABASE SET options](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span> <span data-ttu-id="7eca5-105">Para obter informações sobre repositório de consultas, veja [Monitoring Performance By Using the Query Store](../performance/monitoring-performance-by-using-the-query-store.md).</span><span class="sxs-lookup"><span data-stu-id="7eca5-105">For information about the query store, see [Monitoring Performance By Using the Query Store](../performance/monitoring-performance-by-using-the-query-store.md).</span></span>  
  
||  
|-|  
|<span data-ttu-id="7eca5-106">**Aplica-se a**: [!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7eca5-106">**Applies to**: [!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)].</span></span>|  
  
## <a name="options"></a><span data-ttu-id="7eca5-107">Opções</span><span class="sxs-lookup"><span data-stu-id="7eca5-107">Options</span></span>  
 <span data-ttu-id="7eca5-108">Habilitar</span><span class="sxs-lookup"><span data-stu-id="7eca5-108">Enable</span></span>  
 <span data-ttu-id="7eca5-109">Habilita e desabilita o repositório de consultas.</span><span class="sxs-lookup"><span data-stu-id="7eca5-109">Enables and disables the query store.</span></span>  
  
 <span data-ttu-id="7eca5-110">Modo de Operação</span><span class="sxs-lookup"><span data-stu-id="7eca5-110">Operation Mode</span></span>  
 <span data-ttu-id="7eca5-111">Os valores válidos são READ_ONLY e READ_WRITE.</span><span class="sxs-lookup"><span data-stu-id="7eca5-111">Valid values are READ_ONLY and READ_WRITE.</span></span> <span data-ttu-id="7eca5-112">No modo READ_WRITE, o repositório de consultas coleta e persiste as informações das estatísticas de execução do plano de consulta e do runtime.</span><span class="sxs-lookup"><span data-stu-id="7eca5-112">In READ_WRITE mode, the query store collects and persists query plan and runtime execution statistics information.</span></span> <span data-ttu-id="7eca5-113">No modo READ_ONLY, as informações podem ser lidas do repositório de consultas, mas novas informações não são adicionadas.</span><span class="sxs-lookup"><span data-stu-id="7eca5-113">In READ_ONLY mode, information can be read from the query store, but new information is not added.</span></span> <span data-ttu-id="7eca5-114">Se o espaço máximo alocado do repositório de consultas tiver se esgotado, o repositório de consultas alterará o modo de operação para READ_ONLY.</span><span class="sxs-lookup"><span data-stu-id="7eca5-114">If the maximum allocated space of the query store has been exhausted, the query store will change its operation mode to READ_ONLY.</span></span>  
  
 <span data-ttu-id="7eca5-115">Modo de Operação (Real)</span><span class="sxs-lookup"><span data-stu-id="7eca5-115">Operation Mode (Actual)</span></span>  
 <span data-ttu-id="7eca5-116">Descreve o modo de operação do repositório de consultas.</span><span class="sxs-lookup"><span data-stu-id="7eca5-116">Gets the actual operation mode of the query store.</span></span>  
  
 <span data-ttu-id="7eca5-117">Modo de Operação (Solicitado)</span><span class="sxs-lookup"><span data-stu-id="7eca5-117">Operation Mode (Requested)</span></span>  
 <span data-ttu-id="7eca5-118">Obtém e define o modo de operação desejado do repositório de consultas.</span><span class="sxs-lookup"><span data-stu-id="7eca5-118">Gets and sets the desired operation mode of the query store.</span></span>  
  
 <span data-ttu-id="7eca5-119">Intervalo de Limpeza de Dados (Minutos)</span><span class="sxs-lookup"><span data-stu-id="7eca5-119">Data Flush Interval (Minutes)</span></span>  
 <span data-ttu-id="7eca5-120">Determina a frequência na qual os dados gravados no repositório de consultas é persistida no disco.</span><span class="sxs-lookup"><span data-stu-id="7eca5-120">Determines the frequency at which data written to the query store is persisted to disk.</span></span> <span data-ttu-id="7eca5-121">Para otimizar o desempenho, os dados coletados pelo repositório de consultas são gravados de maneira assíncrona no disco.</span><span class="sxs-lookup"><span data-stu-id="7eca5-121">To optimize for performance, data collected by the query store is asynchronously written to the disk.</span></span> <span data-ttu-id="7eca5-122">A frequência em que essa transferência assíncrona ocorre é configurada.</span><span class="sxs-lookup"><span data-stu-id="7eca5-122">The frequency at which this asynchronous transfer occurs is configured.</span></span>  
  
 <span data-ttu-id="7eca5-123">Intervalo de Coleta de Estatísticas</span><span class="sxs-lookup"><span data-stu-id="7eca5-123">Statistics Collection Interval</span></span>  
 <span data-ttu-id="7eca5-124">Obtém e define o valor do intervalo da coleta de estatísticas.</span><span class="sxs-lookup"><span data-stu-id="7eca5-124">Gets and sets the statistics collection interval value.</span></span>  
  
 <span data-ttu-id="7eca5-125">Tamanho Máximo (MB)</span><span class="sxs-lookup"><span data-stu-id="7eca5-125">Max Size (MB)</span></span>  
 <span data-ttu-id="7eca5-126">Obtém e define o espaço total alocado para o repositório de consultas.</span><span class="sxs-lookup"><span data-stu-id="7eca5-126">Gets and sets the total space allocated to the query store.</span></span>  
  
 <span data-ttu-id="7eca5-127">Limite de Consulta Obsoleto (Dias)</span><span class="sxs-lookup"><span data-stu-id="7eca5-127">Stale Query Threshold (Days)</span></span>  
 <span data-ttu-id="7eca5-128">Obtém e define o limite de consulta obsoleto.</span><span class="sxs-lookup"><span data-stu-id="7eca5-128">Gets and sets the stale query threshold.</span></span> <span data-ttu-id="7eca5-129">Configure o argumento STALE_QUERY_THRESHOLD_DAYS para especificar o número de dias que os dados devem ser mantidos no repositório de consultas.</span><span class="sxs-lookup"><span data-stu-id="7eca5-129">Configure the STALE_QUERY_THRESHOLD_DAYS argument to specify the number of days to retain data in the query store.</span></span>  
  
 <span data-ttu-id="7eca5-130">Limpar Dados da Consulta</span><span class="sxs-lookup"><span data-stu-id="7eca5-130">Purge Query Data</span></span>  
 <span data-ttu-id="7eca5-131">Remove o conteúdo do repositório de consultas.</span><span class="sxs-lookup"><span data-stu-id="7eca5-131">Removes the contents of the query store.</span></span>  
  
 <span data-ttu-id="7eca5-132">Gráficos de pizza</span><span class="sxs-lookup"><span data-stu-id="7eca5-132">Pie Charts</span></span>  
 <span data-ttu-id="7eca5-133">O gráfico da esquerda mostra o consumo total do arquivo de banco de dados no disco e a parte do arquivo que é preenchida com os dados do repositório de consultas.</span><span class="sxs-lookup"><span data-stu-id="7eca5-133">The left chart shows the total database file consumption on the disk, and the portion of the file which is filled with the query store data.</span></span>  
  
 <span data-ttu-id="7eca5-134">O gráfico à direita mostra a parte da cota do repositório de consultas usada no momento.</span><span class="sxs-lookup"><span data-stu-id="7eca5-134">The right chart shows the portion of the query store quota which is currently used up.</span></span> <span data-ttu-id="7eca5-135">Observe que a cota não é mostrada no gráfico à esquerda.</span><span class="sxs-lookup"><span data-stu-id="7eca5-135">Note that the quota is not shown in the left chart.</span></span> <span data-ttu-id="7eca5-136">A cota pode exceder o tamanho atual do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7eca5-136">The quota may exceed the current size of the database.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7eca5-137">Comentários</span><span class="sxs-lookup"><span data-stu-id="7eca5-137">Remarks</span></span>  
 <span data-ttu-id="7eca5-138">O recurso repositório de consultas fornece aos DBAs insights sobre escolha e desempenho do plano de consulta.</span><span class="sxs-lookup"><span data-stu-id="7eca5-138">The query store feature provides DBAs with insight on query plan choice and performance.</span></span> <span data-ttu-id="7eca5-139">Ele simplifica a solução de problemas, permitindo que você localize rapidamente diferenças de desempenho causadas por alterações nos planos de consulta.</span><span class="sxs-lookup"><span data-stu-id="7eca5-139">It simplifies performance troubleshooting by enabling you to quickly find performance differences caused by changes in query plans.</span></span> <span data-ttu-id="7eca5-140">O recurso captura automaticamente um histórico de consultas, planos e estatísticas de runtime e os mantém para sua análise.</span><span class="sxs-lookup"><span data-stu-id="7eca5-140">The feature automatically captures a history of queries, plans, and runtime statistics, and retains these for your review.</span></span> <span data-ttu-id="7eca5-141">Ele separa os dados por janelas de tempo, permitindo que você veja os padrões de uso do banco de dados e entenda quando as alterações aos planos de consulta ocorreram no servidor.</span><span class="sxs-lookup"><span data-stu-id="7eca5-141">It separates data by time windows, allowing you to see database usage patterns and understand when query plan changes happened on the server.</span></span> <span data-ttu-id="7eca5-142">O repositório de consultas pode ser configurado usando essa página de propriedades do banco de dados do repositório de consultas, ou usando a opção [ALTER DATABASE SET](/sql/t-sql/statements/alter-database-transact-sql-set-options) .</span><span class="sxs-lookup"><span data-stu-id="7eca5-142">The query store can be configured by using this query store database property page, or by using the [ALTER DATABASE SET](/sql/t-sql/statements/alter-database-transact-sql-set-options) option.</span></span> <span data-ttu-id="7eca5-143">O repositório de consultas apresenta informações usando uma caixa de diálogo do [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7eca5-143">The query store presents information by using a [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] dialog box.</span></span> <span data-ttu-id="7eca5-144">Para obter mais informações sobre o repositório de consultas, veja [Monitoring Performance By Using the Query Store](../performance/monitoring-performance-by-using-the-query-store.md).</span><span class="sxs-lookup"><span data-stu-id="7eca5-144">For more information about query store, see [Monitoring Performance By Using the Query Store](../performance/monitoring-performance-by-using-the-query-store.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eca5-145">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7eca5-145">See Also</span></span>  
 <span data-ttu-id="7eca5-146">[Procedimentos armazenados do Repositório de Consultas &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/query-store-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7eca5-146">[Query Store Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/query-store-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="7eca5-147">Exibições de catálogo do repositório de consultas &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7eca5-147">Query Store Catalog Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/query-store-catalog-views-transact-sql)  
  
  
