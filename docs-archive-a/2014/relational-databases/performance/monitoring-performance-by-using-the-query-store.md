---
title: Monitorando o desempenho usando o Repositório de Consultas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: e06344a4-22a5-4c67-b6c6-a7060deb5de6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e5d74b9c4def9c0314569a8d0bd87939cdcb11b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582986"
---
# <a name="monitoring-performance-by-using-the-query-store"></a><span data-ttu-id="9a8bb-102">Monitoring Performance By Using the Query Store</span><span class="sxs-lookup"><span data-stu-id="9a8bb-102">Monitoring Performance By Using the Query Store</span></span>
  <span data-ttu-id="9a8bb-103">O recurso repositório de consultas fornece aos DBAs insights sobre escolha e desempenho do plano de consulta.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-103">The query store feature provides DBAs with insight on query plan choice and performance.</span></span> <span data-ttu-id="9a8bb-104">Ele simplifica a solução de problemas, permitindo que você localize rapidamente diferenças de desempenho causadas por alterações nos planos de consulta.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-104">It simplifies performance troubleshooting by enabling you to quickly find performance differences caused by changes in query plans.</span></span> <span data-ttu-id="9a8bb-105">O recurso captura automaticamente um histórico de consultas, planos e estatísticas de runtime e os mantém para sua análise.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-105">The feature automatically captures a history of queries, plans, and runtime statistics, and retains these for your review.</span></span> <span data-ttu-id="9a8bb-106">Ele separa os dados por janelas de tempo, permitindo que você veja os padrões de uso do banco de dados e entenda quando as alterações aos planos de consulta ocorreram no servidor.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-106">It separates data by time windows, allowing you to see database usage patterns and understand when query plan changes happened on the server.</span></span> <span data-ttu-id="9a8bb-107">O repositório de consultas pode ser configurado usando a opção [ALTER DATABASE SET](/sql/t-sql/statements/alter-database-transact-sql-set-options) .</span><span class="sxs-lookup"><span data-stu-id="9a8bb-107">The query store can be configured by using the [ALTER DATABASE SET](/sql/t-sql/statements/alter-database-transact-sql-set-options) option.</span></span>

||
|-|
|<span data-ttu-id="9a8bb-108">**Aplica-se a**: [!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)] ([obtenha](http://azure.micosoft.com/documentation/articles/sql-database-preview-whats-new/?WT.mc_id=TSQL_GetItTag)).</span><span class="sxs-lookup"><span data-stu-id="9a8bb-108">**Applies to**: [!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)] ([Get it](http://azure.micosoft.com/documentation/articles/sql-database-preview-whats-new/?WT.mc_id=TSQL_GetItTag)).</span></span>|

> [!IMPORTANT]
>  <span data-ttu-id="9a8bb-109">Este é um recurso de visualização.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-109">This is currently a preview feature.</span></span> <span data-ttu-id="9a8bb-110">Para usar o repositório de consultas, você deve reconhecer e concordar que a implementação do repositório está sujeita aos termos de visualização anteriores do contrato de licença (por exemplo, Contrato Enterprise, Contrato do Microsoft Azure ou Contrato de Assinatura do Microsoft Online), bem como quaisquer [Termos suplementares de uso da Visualização do Microsoft Azure](https://azure.microsoft.com/support/legal/preview-supplemental-terms/)aplicáveis.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-110">To use the Query Store you must acknowledge and agree that implementation of Query Store is subject to the preview terms in your license agreement (e.g. the Enterprise Agreement, Microsoft Azure Agreement, or Microsoft Online Subscription Agreement), as well as any applicable [Supplemental Terms of Use for Microsoft Azure Preview](https://azure.microsoft.com/support/legal/preview-supplemental-terms/).</span></span>

##  <a name="enabling-the-query-store"></a><a name="Enabling"></a> <span data-ttu-id="9a8bb-111">Habilitando o Repositório de Consultas</span><span class="sxs-lookup"><span data-stu-id="9a8bb-111">Enabling the Query Store</span></span>
 <span data-ttu-id="9a8bb-112">O repositório de consultas não está ativo para novos bancos de dados por padrão.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-112">Query Store is not active for new databases by default.</span></span>

#### <a name="by-using-the-query-store-page-in-management-studio"></a><span data-ttu-id="9a8bb-113">Usando a página Repositório de Consultas no Management Studio</span><span class="sxs-lookup"><span data-stu-id="9a8bb-113">By Using the Query Store Page in Management Studio</span></span>

1.  <span data-ttu-id="9a8bb-114">No Pesquisador de Objetos, clique com o botão direito do mouse em um banco de dados e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-114">In Object Explorer, right-click a database, and then click **Properties**.</span></span> <span data-ttu-id="9a8bb-115">(Requer [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 2016 versão [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="9a8bb-115">(Requires [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 2016 version of [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].)</span></span>

2.  <span data-ttu-id="9a8bb-116">Na caixa de diálogo **Propriedades do Banco de Dados** , selecione a página **Repositório de Consultas** .</span><span class="sxs-lookup"><span data-stu-id="9a8bb-116">In the **Database Properties** dialog box, select the **Query Store** page.</span></span>

3.  <span data-ttu-id="9a8bb-117">Na caixa **Habilitar** selecione **Verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-117">In the **Enable** box, select **True**.</span></span>

#### <a name="by-using-transact-sql-statements"></a><span data-ttu-id="9a8bb-118">Usando as instruções Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9a8bb-118">By Using Transact-SQL Statements</span></span>

1.  <span data-ttu-id="9a8bb-119">Use a instrução `ALTER DATABASE` para habilitar o repositório de consultas.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-119">Use the `ALTER DATABASE` statement to enable the query store.</span></span> <span data-ttu-id="9a8bb-120">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9a8bb-120">For example:</span></span>

    ```
    ALTER DATABASE AdventureWorks2012 SET QUERY_STORE = ON;
    ```

     <span data-ttu-id="9a8bb-121">Para obter mais opções de sintaxe relacionadas ao repositório de consultas, consulte [Opções ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="9a8bb-121">For more syntax options related to the query store, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>

> [!NOTE]
>  <span data-ttu-id="9a8bb-122">Não é possível habilitar o repositório de consultas no banco de dados mestre.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-122">You cannot enable the query store for the master database.</span></span>



##  <a name="information-in-the-query-store"></a><a name="About"></a> <span data-ttu-id="9a8bb-123">Informações no Repositório de Consultas</span><span class="sxs-lookup"><span data-stu-id="9a8bb-123">Information in the Query Store</span></span>
 <span data-ttu-id="9a8bb-124">Planos de execução para qualquer consulta específica no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] normalmente envolvem horas extras por vários motivos diferentes, como alterações de estatísticas, alterações de esquema, criação/exclusão de índices, etc. O cache de procedimento (no qual os planos de consulta em cache são armazenados) armazena apenas o plano de execução mais recente.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-124">Execution plans for any specific query in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] typically evolve over time due to a number of different reasons such as statistics changes, schema changes, creation/deletion of indexes, etc. The procedure cache (where cached query plans are stored) only stores the latest execution plan.</span></span> <span data-ttu-id="9a8bb-125">Os planos também são removidos do cache do plano devido à pressão da memória.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-125">Plans also get evicted from the plan cache due to memory pressure.</span></span> <span data-ttu-id="9a8bb-126">Como resultado, as regressões do desempenho de consulta causadas por alterações no plano de execução podem não ser triviais e podem ter resolução lenta.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-126">As a result, query performance regressions caused by execution plan changes can be non-trivial and time consuming to resolve.</span></span>

 <span data-ttu-id="9a8bb-127">Como o repositório de consultas mantém vários planos de execução por consulta, ele pode impor políticas para direcionar o processador de consultas para usar um plano de execução específico para uma consulta.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-127">Since the query store retains multiple execution plans per query, it can enforce policies to direct the query processor to use a specific execution plan for a query.</span></span> <span data-ttu-id="9a8bb-128">Isso é conhecido como imposição de plano.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-128">This is referred to as plan forcing.</span></span> <span data-ttu-id="9a8bb-129">A imposição de plano no repositório de consultas é fornecida usando um mecanismo semelhante à dica de consulta [USE PLAN](/sql/t-sql/queries/hints-transact-sql-query) , mas não requer nenhuma alteração nos aplicativos do usuário.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-129">Plan forcing in Query Store is provided by using a mechanism similar to the [USE PLAN](/sql/t-sql/queries/hints-transact-sql-query) query hint, but it does not require any change in user applications.</span></span> <span data-ttu-id="9a8bb-130">A imposição de plano pode resolver uma regressão de desempenho de consulta causada por uma alteração do plano em um período muito curto.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-130">Plan forcing can resolve a query performance regression caused by a plan change in a very short period of time.</span></span>

 <span data-ttu-id="9a8bb-131">Cenários comuns para o uso do recurso Repositório de Consultas são:</span><span class="sxs-lookup"><span data-stu-id="9a8bb-131">Common scenarios for using the Query Store feature are:</span></span>

-   <span data-ttu-id="9a8bb-132">Localizar e corrigir rapidamente uma regressão de desempenho do plano, forçando o plano de consulta anterior.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-132">Quickly find and fix a plan performance regression by forcing the previous query plan.</span></span> <span data-ttu-id="9a8bb-133">Corrigir consultas com regressão recente no desempenho devido a alterações no plano de execução.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-133">Fix queries that have recently regressed in performance due to execution plan changes.</span></span>

-   <span data-ttu-id="9a8bb-134">Determinar o número de vezes que uma consulta foi executada em determinada janela de tempo, auxiliando um DBA na solução de problemas de recurso de desempenho.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-134">Determine the number of times a query was executed in a given time window, assisting a DBA in troubleshooting performance resource problems.</span></span>

-   <span data-ttu-id="9a8bb-135">Identificar as principais consultas *n* (por tempo de execução, consumo de memória, etc.) nas últimas *x* horas.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-135">Identify top *n* queries (by execution time, memory consumption, etc.) in the past *x* hours.</span></span>

-   <span data-ttu-id="9a8bb-136">Fazer auditoria de histórico dos planos de consulta para determinada consulta.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-136">Audit the history of query plans for a given query.</span></span>

-   <span data-ttu-id="9a8bb-137">Analisar os padrões de uso dos recursos (CPU, E/S e memória) para determinado banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-137">Analyze the resource (CPU, I/O, and Memory) usage patterns for a particular database.</span></span>

 <span data-ttu-id="9a8bb-138">O armazenamento de consultas contém dois repositórios; um **repositório de planos** para manter as informações do plano de execução e um **repositório de estatísticas de runtime** para manter as informações de estatísticas de execução.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-138">The query store contains two stores; a **plan store** for persisting the execution plan information, and a **runtime stats store** for persisting the execution statistics information.</span></span> <span data-ttu-id="9a8bb-139">O número de planos exclusivos que pode ser armazenado para uma consulta no repositório de planos é limitado pela opção de configuração `max_plans_per_query`.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-139">The number of unique plans that can be stored for a query in the plan store is limited by the `max_plans_per_query` configuration option.</span></span> <span data-ttu-id="9a8bb-140">Para melhorar o desempenho, as informações são gravadas nos dois repositórios de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-140">To enhance performance, the information is written to the two stores asynchronously.</span></span> <span data-ttu-id="9a8bb-141">Para otimizar o uso do espaço, as estatísticas de runtime no repositório de estatísticas de runtime são agregadas em uma janela de tempo fixa.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-141">To minimize space usage, the runtime execution statistics in the runtime stats store are aggregated over a fixed time window.</span></span> <span data-ttu-id="9a8bb-142">As informações nesses repositórios são visíveis consultando as exibições de catálogo do repositório de consultas.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-142">The information in these stores is visible by querying the query store catalog views.</span></span>

 <span data-ttu-id="9a8bb-143">A consulta a seguir retorna informações sobre consultas e planos no repositório de consultas.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-143">The following query returns information about queries and plans in the query store.</span></span>

```
SELECT Txt.query_text_id, Txt.query_sql_text, Pl.plan_id, Qry.*
FROM sys.query_store_plan AS Pl
JOIN sys.query_store_query AS Qry
    ON Pl.query_id = Qry.query_id
JOIN sys.query_store_query_text AS Txt
    ON Qry.query_text_id = Txt.query_text_id ;
```



## <a name="using-the-regressed-queries-feature"></a><span data-ttu-id="9a8bb-144">Usando o recurso de consultas regredidas</span><span class="sxs-lookup"><span data-stu-id="9a8bb-144">Using the Regressed Queries Feature</span></span>
 <span data-ttu-id="9a8bb-145">Depois de habilitar o repositório de consultas, atualize a parte do banco de dados do painel Pesquisador de objetos para adicionar a seção **repositório de consultas** .</span><span class="sxs-lookup"><span data-stu-id="9a8bb-145">After enabling the query store, refresh the database portion of the Object Explorer pane to add the **Query Store** section.</span></span>

 <span data-ttu-id="9a8bb-146">![QueryStore](../../database-engine/media/querystore.PNG "QueryStore")</span><span class="sxs-lookup"><span data-stu-id="9a8bb-146">![QueryStore](../../database-engine/media/querystore.PNG "QueryStore")</span></span>

 <span data-ttu-id="9a8bb-147">A seleção de **Consultas Regredidas**abre o painel **Consultas Regredidas** no [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a8bb-147">Selecting **Regressed Queries**, opens the **Regressed Queries** pane in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="9a8bb-148">O painel Consultas Regredidas mostra consultas e planos no repositório de consultas.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-148">The Regressed Queries pane shows you the queries, and plans in the query store.</span></span> <span data-ttu-id="9a8bb-149">Caixas de listas suspensas na parte superior permitem que você selecione consultas com base em vários critérios.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-149">Drop down boxes at the top allow you to select queries based on various criteria.</span></span> <span data-ttu-id="9a8bb-150">Selecione um plano para ver o plano de consulta gráfico.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-150">Select a plan to see the graphical query plan.</span></span> <span data-ttu-id="9a8bb-151">Botões estão disponíveis para exibir a consulta de origem, impor e cancelar a imposição de um plano de consulta e atualizar a exibição.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-151">Buttons are available to view the source query, force, and unforce a query plan, and refresh the display.</span></span>

 <span data-ttu-id="9a8bb-152">![RegressedQueries](../../database-engine/media/regressedqueries.PNG "RegressedQueries")</span><span class="sxs-lookup"><span data-stu-id="9a8bb-152">![RegressedQueries](../../database-engine/media/regressedqueries.PNG "RegressedQueries")</span></span>

 <span data-ttu-id="9a8bb-153">Para forçar um plano, selecione uma consulta e um plano e, em seguida, clique em **forçar plano.**</span><span class="sxs-lookup"><span data-stu-id="9a8bb-153">To force a plan, select a query and plan, and then click **Force Plan.**</span></span> <span data-ttu-id="9a8bb-154">Você pode impor apenas planos que foram salvos pelo recurso de plano de consulta e ainda são mantidos no cache do plano de consulta.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-154">You can only force plans that were saved by the query plan feature and are still retained in the query plan cache.</span></span>



##  <a name="configuration-options"></a><a name="Options"></a> <span data-ttu-id="9a8bb-155">Opções de configuração</span><span class="sxs-lookup"><span data-stu-id="9a8bb-155">Configuration Options</span></span>
 <span data-ttu-id="9a8bb-156">OPERATION_MODE pode ser READ_WRITE ou READ_ONLY.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-156">OPERATION_MODE Can be READ_WRITE or READ_ONLY.</span></span>

 <span data-ttu-id="9a8bb-157">CLEANUP_POLICY configurar o argumento STALE_QUERY_THRESHOLD_DAYS para especificar o número de dias para reter dados no repositório de consultas.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-157">CLEANUP_POLICY Configure the STALE_QUERY_THRESHOLD_DAYS argument to specify the number of days to retain data in the query store.</span></span>

 <span data-ttu-id="9a8bb-158">DATA_FLUSH_INTERVAL_SECONDS Determina a frequência na qual os dados gravados no repositório de consultas são persistidos no disco.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-158">DATA_FLUSH_INTERVAL_SECONDS Determines the frequency at which data written to the query store is persisted to disk.</span></span> <span data-ttu-id="9a8bb-159">Para otimizar o desempenho, os dados coletados pelo repositório de consultas são gravados de maneira assíncrona no disco.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-159">To optimize for performance, data collected by the query store is asynchronously written to the disk.</span></span> <span data-ttu-id="9a8bb-160">A frequência em que essa transferência assíncrona ocorre é configurada via DATA_FLUSH_INTERVAL_SECONDS.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-160">The frequency at which this asynchronous transfer occurs is configured via DATA_FLUSH_INTERVAL_SECONDS.</span></span>

 <span data-ttu-id="9a8bb-161">MAX_SIZE_MB configura o tamanho máximo do repositório de consultas.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-161">MAX_SIZE_MB Configures the maximum size of the query store.</span></span> <span data-ttu-id="9a8bb-162">Se os dados no repositório de consultas atingir o limite MAX_SIZE_MB, o repositório de consultas alterará automaticamente o status de somente gravação para somente leitura e interromperá a coleta de novos dados.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-162">If the data in the query store hits the MAX_SIZE_MB limit, the query store automatically changes the state from read-write to read-only and stops collecting new data.</span></span>

 <span data-ttu-id="9a8bb-163">INTERVAL_LENGTH_MINUTES Determina o intervalo de tempo em que os dados de estatísticas de execução do runtime são agregados no repositório de consultas.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-163">INTERVAL_LENGTH_MINUTES Determines the time interval at which runtime execution statistics data is aggregated into the query store.</span></span> <span data-ttu-id="9a8bb-164">Para otimizar o uso de espaço, as estatísticas de execução de runtime no repositório de estatísticas de runtime são agregadas em uma janela de tempo fixa.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-164">To optimize for space usage, the runtime execution statistics in the Runtime Stats Store are aggregated over a fixed time window.</span></span> <span data-ttu-id="9a8bb-165">Essa janela de tempo fixa é configurada usando INTERVAL_LENGTH_MINUTES.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-165">This fixed time window is configured via INTERVAL_LENGTH_MINUTES.</span></span>

 <span data-ttu-id="9a8bb-166">Consulte a exibição `sys.database_query_store_options` para determinar as opções atuais do repositório de consultas.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-166">Query the `sys.database_query_store_options` view to determine the current options of the query store.</span></span>

 <span data-ttu-id="9a8bb-167">Para obter mais informações sobre como definir opções usando instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] , consulte [Gerenciamento de opção](#OptionMgmt).</span><span class="sxs-lookup"><span data-stu-id="9a8bb-167">For more information about setting options by using [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, see [Option Management](#OptionMgmt).</span></span>

 

##  <a name="related-views-functions-and-procedures"></a><a name="Related"></a> <span data-ttu-id="9a8bb-168">Exibições, Funções e Procedimentos Relacionados</span><span class="sxs-lookup"><span data-stu-id="9a8bb-168">Related Views, Functions, and Procedures</span></span>
 <span data-ttu-id="9a8bb-169">O repositório de consultas pode ser exibido e gerenciado por meio do [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] ou usando as exibições e os procedimentos a seguir.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-169">The Query Store can be viewed and managed through [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] or by using the following views and procedures.</span></span>

-   [<span data-ttu-id="9a8bb-170">sys.fn_stmt_sql_handle_from_sql_stmt &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a8bb-170">sys.fn_stmt_sql_handle_from_sql_stmt &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/sys-fn-stmt-sql-handle-from-sql-stmt-transact-sql)

### <a name="query-store-catalog-views"></a><span data-ttu-id="9a8bb-171">Exibições do catálogo de repositório de consulta</span><span class="sxs-lookup"><span data-stu-id="9a8bb-171">Query Store Catalog Views</span></span>
 <span data-ttu-id="9a8bb-172">Sete exibições do catálogo apresentam informações sobre o repositório de consultas.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-172">Seven catalog views present information about the Query Store.</span></span>

-   [<span data-ttu-id="9a8bb-173">sys.database_query_store_options &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a8bb-173">sys.database_query_store_options &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-query-store-options-transact-sql)

-   [<span data-ttu-id="9a8bb-174">sys.query_context_settings &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a8bb-174">sys.query_context_settings &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-context-settings-transact-sql)

-   [<span data-ttu-id="9a8bb-175">sys.query_store_plan &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a8bb-175">sys.query_store_plan &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-plan-transact-sql)

-   [<span data-ttu-id="9a8bb-176">sys.query_store_query &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a8bb-176">sys.query_store_query &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-query-transact-sql)

-   [<span data-ttu-id="9a8bb-177">sys.query_store_query_text &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a8bb-177">sys.query_store_query_text &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-query-text-transact-sql)

-   [<span data-ttu-id="9a8bb-178">sys.query_store_runtime_stats &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a8bb-178">sys.query_store_runtime_stats &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-runtime-stats-transact-sql)

-   [<span data-ttu-id="9a8bb-179">sys.query_store_runtime_stats_interval &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a8bb-179">sys.query_store_runtime_stats_interval &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-runtime-stats-interval-transact-sql)

### <a name="query-store-stored-procedures"></a><span data-ttu-id="9a8bb-180">Procedimentos armazenados do repositório de consulta</span><span class="sxs-lookup"><span data-stu-id="9a8bb-180">Query Store Stored Procedures</span></span>
 <span data-ttu-id="9a8bb-181">Seis procedimentos armazenados configuram o repositório de consultas.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-181">Six stored procedures configure the Query Store.</span></span>

-   [<span data-ttu-id="9a8bb-182">sp_query_store_flush_db &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a8bb-182">sp_query_store_flush_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-flush-db-transact-sql)

-   [<span data-ttu-id="9a8bb-183">sp_query_store_reset_exec_stats &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a8bb-183">sp_query_store_reset_exec_stats &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-reset-exec-stats-transact-sql)

-   [<span data-ttu-id="9a8bb-184">sp_query_store_force_plan &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a8bb-184">sp_query_store_force_plan &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-force-plan-transact-sql)

-   [<span data-ttu-id="9a8bb-185">sp_query_store_unforce_plan &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a8bb-185">sp_query_store_unforce_plan &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-unforce-plan-transact-sql)

-   [<span data-ttu-id="9a8bb-186">sp_query_store_remove_plan &#40;Transct-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a8bb-186">sp_query_store_remove_plan &#40;Transct-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-remove-plan-transct-sql)

-   [<span data-ttu-id="9a8bb-187">sp_query_store_remove_query &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a8bb-187">sp_query_store_remove_query &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-remove-query-transact-sql)



##  <a name="key-usage-scenarios"></a><a name="Scenarios"></a> <span data-ttu-id="9a8bb-188">Principais cenários de uso</span><span class="sxs-lookup"><span data-stu-id="9a8bb-188">Key Usage Scenarios</span></span>

###  <a name="option-management"></a><a name="OptionMgmt"></a> <span data-ttu-id="9a8bb-189">Gerenciamento de opção</span><span class="sxs-lookup"><span data-stu-id="9a8bb-189">Option Management</span></span>
 <span data-ttu-id="9a8bb-190">Esta seção fornece algumas diretrizes sobre como gerenciar recursos do próprio repositório de consultas.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-190">This section provides some guidelines on managing Query Store feature itself.</span></span>

 <span data-ttu-id="9a8bb-191">**O Repositório de Consultas está ativo no momento?**</span><span class="sxs-lookup"><span data-stu-id="9a8bb-191">**Is Query Store currently active?**</span></span>

 <span data-ttu-id="9a8bb-192">O Repositório de Consultas armazena seus dados dentro do banco de dados do usuário e é por isso que ele tem limite de tamanho (configurado com `MAX_STORAGE_SIZE_MB`).</span><span class="sxs-lookup"><span data-stu-id="9a8bb-192">Query Store stores its data inside the user database and that is why it has size limit (configured  with `MAX_STORAGE_SIZE_MB`).</span></span> <span data-ttu-id="9a8bb-193">Se os dados no repositório de consultas atingirem esse limite, o repositório de consultas alterará automaticamente o status de somente gravação para somente leitura e interromperá a coleta de novos dados.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-193">If data in Query Store hits that limit Query Store will automatically change state from read-write to read-only and stop collecting new data.</span></span>

 <span data-ttu-id="9a8bb-194">Execute o script a seguir para determinar se o repositório de consultas está ativo no momento e se está coletando estatísticas de runtime ou não.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-194">Execute the following script to determine if Query Store is currently active, and whether it is currently collects runtime stats or not.</span></span>

```
DECLARE @x nvarchar(100) = CAST(newid() AS nvarchar(100));
DECLARE @query nvarchar(max) = 
N'IF EXISTS
(
    SELECT * 
    FROM sys.query_store_query_text 
    WHERE query_sql_text LIKE ''%' + @x + N'%''
)
SELECT ''Query Store is active'' ;
ELSE SELECT ''Query Store is NOT active''' ;
EXEC sp_executesql @query;
```

 <span data-ttu-id="9a8bb-195">**Opções Obter Repositório de Consultas**</span><span class="sxs-lookup"><span data-stu-id="9a8bb-195">**Get Query Store options**</span></span>

 <span data-ttu-id="9a8bb-196">Para obter informações detalhadas sobre o status do repositório de consultas, execute o seguinte em um banco de dados do usuário.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-196">To find out detailed information about Query Store status, execute following in a user database.</span></span>

```
SELECT * FROM sys.database_query_store_options;
```

 <span data-ttu-id="9a8bb-197">**Configurar o intervalo do Repositório de Consultas**</span><span class="sxs-lookup"><span data-stu-id="9a8bb-197">**Setting Query Store interval**</span></span>

 <span data-ttu-id="9a8bb-198">Você pode substituir o intervalo para agregar estatísticas de runtime de consulta (o padrão é 60 minutos).</span><span class="sxs-lookup"><span data-stu-id="9a8bb-198">You can override interval for aggregating query runtime statistics (default is 60 minutes).</span></span>

```

      USE master;
GO

ALTER DATABASE <database_name> 
SET QUERY_STORE (INTERVAL_LENGTH_MINUTES = 15);
```

 <span data-ttu-id="9a8bb-199">Observe que não são permitidos valores arbitrários – você deve usar um dos seguintes: 1, 5, 10, 15, 30 e 60.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-199">Note that arbitrary values are not allowed - you should use one of the following: 1, 5, 10, 15, 30 and 60.</span></span>

 <span data-ttu-id="9a8bb-200">O novo valor do intervalo é exposto na exibição `sys.database_query_store_options`.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-200">New value for interval is exposed through `sys.database_query_store_options` view.</span></span>

 <span data-ttu-id="9a8bb-201">Se o armazenamento do repositório de consultas estiver completo, use a seguinte instrução para ampliar o armazenamento.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-201">If the Query Store storage is full use the following statement to extend the storage.</span></span>

```
ALTER DATABASE <database_name> 
SET QUERY_STORE (MAX_STORAGE_SIZE_MB = <new_size>);
```

 <span data-ttu-id="9a8bb-202">**Opções Obter Todos os Repositórios de Consultas**</span><span class="sxs-lookup"><span data-stu-id="9a8bb-202">**Set all Query Store options**</span></span>

 <span data-ttu-id="9a8bb-203">Você pode definir várias opções de repositório de consultas de uma só vez com uma única instrução ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-203">You can set multiple Query Store options at once with a single ALTER DATABASE statement.</span></span>

```
ALTER DATABASE <database name> 
SET QUERY_STORE (
    OPERATION_MODE = READ_WRITE,
    CLEANUP_POLICY = 
    (STALE_QUERY_THRESHOLD_DAYS = 30),
    DATA_FLUSH_INTERVAL_SECONDS = 3000,
    MAX_STORAGE_SIZE_MB = 500,
    INTERVAL_LENGTH_MINUTES = 15
);
```

 <span data-ttu-id="9a8bb-204">**Limpar o espaço**</span><span class="sxs-lookup"><span data-stu-id="9a8bb-204">**Cleaning up the space**</span></span>

 <span data-ttu-id="9a8bb-205">Tabelas internas do repositório de consultas são criadas no grupo de arquivos PRIMARY durante a criação do banco de dados e essa configuração não pode ser alterada posteriormente.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-205">Query Store internal tables are created in the PRIMARY filegroup during database creation and that configuration cannot be changed later.</span></span> <span data-ttu-id="9a8bb-206">Se você estiver executando sem espaço, limpe os dados antigos do repositório de consultas usando a instrução a seguir.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-206">If you are running out of space you might want to clear older Query Store data by using the following statement.</span></span>

```
ALTER DATABASE <db_name> SET QUERY_STORE CLEAR;
```

 <span data-ttu-id="9a8bb-207">Você pode também limpar apenas dados de consulta ad hoc, pois são menos relevantes para otimizações de consulta e análise do plano, mas eles ocupam a mesma quantidade de espaço.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-207">Alternatively, you might want to clear up only ad-hoc query data, since it is less relevant for query optimizations and plan analysis but takes up just as much space.</span></span>

 <span data-ttu-id="9a8bb-208">**Excluir consultas ad hoc** Isso exclui as consultas que só foram executadas uma vez e que têm mais de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-208">**Delete ad-hoc queries** This deletes the queries that were only executed only once and that are more than 24 hours old.</span></span>

```
DECLARE @id int
DECLARE adhoc_queries_cursor CURSOR 
FOR 
SELECT q.query_id
FROM sys.query_store_query_text AS qt
JOIN sys.query_store_query AS q 
    ON q.query_text_id = qt.query_text_id
JOIN sys.query_store_plan AS p 
    ON p.query_id = q.query_id
JOIN sys.query_store_runtime_stats AS rs 
    ON rs.plan_id = p.plan_id
GROUP BY q.query_id
HAVING SUM(rs.count_executions) < 2 
AND MAX(rs.last_execution_time) < DATEADD (hour, -24, GETUTCDATE())
ORDER BY q.query_id ;

OPEN adhoc_queries_cursor ;
FETCH NEXT FROM adhoc_queries_cursor INTO @id;
WHILE @@fetch_status = 0
    BEGIN 
        PRINT @id
        EXEC sp_query_store_remove_query @id
        FETCH NEXT FROM adhoc_queries_cursor INTO @id
    END 
CLOSE adhoc_queries_cursor ;
DEALLOCATE adhoc_queries_cursor;
```

 <span data-ttu-id="9a8bb-209">Você pode definir seu próprio procedimento com uma lógica diferente, para limpar os dados que não são mais importantes para você.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-209">You can define your own procedure with different logic for clearing up the data that is no longer important for you.</span></span>

 <span data-ttu-id="9a8bb-210">O exemplo acima usa o procedimento armazenado estendido `sp_query_store_remove_query` para remover dados desnecessários.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-210">The example above uses the `sp_query_store_remove_query` extended stored procedure for removing unnecessary data.</span></span> <span data-ttu-id="9a8bb-211">Você também pode usar dois outros procedimentos.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-211">You can also use two other procedures.</span></span>

-   <span data-ttu-id="9a8bb-212">`sp_query_store_reset_exec_stats`-Limpar estatísticas de tempo de execução para um determinado plano.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-212">`sp_query_store_reset_exec_stats` - clear runtime statistics for a given plan.</span></span>

-   <span data-ttu-id="9a8bb-213">`sp_query_store_remove_plan`-Remove um único plano.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-213">`sp_query_store_remove_plan` - removes a single plan.</span></span>



###  <a name="performance-auditing-and-troubleshooting"></a><a name="Peformance"></a> <span data-ttu-id="9a8bb-214">Auditoria e solução de problemas de desempenho</span><span class="sxs-lookup"><span data-stu-id="9a8bb-214">Performance Auditing and Troubleshooting</span></span>
 <span data-ttu-id="9a8bb-215">Como o repositório de consultas mantém o histórico de compilação e métricas do runtime durante as execuções da consulta, há muitas questões diferentes que podem ser respondidas facilmente com relação à carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-215">Because Query Store keeps history of compilation and runtime metrics throughout query executions there are many different questions you can easily answer with regards to your workload.</span></span>

 <span data-ttu-id="9a8bb-216">**Últimas *n* consultas executadas no banco de dados.**</span><span class="sxs-lookup"><span data-stu-id="9a8bb-216">**Last *n* queries executed on the database.**</span></span>

```
SELECT TOP 10 qt.query_sql_text, q.query_id, 
    qt.query_text_id, p.plan_id, rs.last_execution_time
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p 
    ON q.query_id = p.query_id 
JOIN sys.query_store_runtime_stats AS rs 
    ON p.plan_id = rs.plan_id
ORDER BY rs.last_execution_time DESC;
```

 <span data-ttu-id="9a8bb-217">**Número de execuções para cada consulta.**</span><span class="sxs-lookup"><span data-stu-id="9a8bb-217">**Number of executions for each query.**</span></span>

```
SELECT q.query_id, qt.query_text_id, qt.query_sql_text, 
    SUM(rs.count_executions) AS total_execution_count
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p 
    ON q.query_id = p.query_id 
JOIN sys.query_store_runtime_stats AS rs 
    ON p.plan_id = rs.plan_id
GROUP BY q.query_id, qt.query_text_id, qt.query_sql_text
ORDER BY total_execution_count DESC;
```

 <span data-ttu-id="9a8bb-218">**O número de consultas com o tempo médio de execução mais longo na última hora.**</span><span class="sxs-lookup"><span data-stu-id="9a8bb-218">**The number of queries with the longest average execution time within last hour.**</span></span>

```
SELECT TOP 10 rs.avg_duration, qt.query_sql_text, q.query_id,
    qt.query_text_id, p.plan_id, GETUTCDATE() AS CurrentUTCTime, 
    rs.last_execution_time 
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p 
    ON q.query_id = p.query_id 
JOIN sys.query_store_runtime_stats AS rs 
    ON p.plan_id = rs.plan_id
WHERE rs.last_execution_time > DATEADD(hour, -1, GETUTCDATE())
ORDER BY rs.avg_duration DESC;
```

 <span data-ttu-id="9a8bb-219">**O número de consultas que tiveram a maior média de leituras físicas de e/s nas últimas 24 horas, com contagem média de linhas e execuções correspondentes.**</span><span class="sxs-lookup"><span data-stu-id="9a8bb-219">**The number of queries that had the biggest average physical IO reads in last 24 hours, with corresponding average row count and execution count.**</span></span>

```
SELECT TOP 10 rs.avg_physical_io_reads, qt.query_sql_text, 
    q.query_id, qt.query_text_id, p.plan_id, rs.runtime_stats_id, 
    rsi.start_time, rsi.end_time, rs.avg_rowcount, rs.count_executions
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p 
    ON q.query_id = p.query_id 
JOIN sys.query_store_runtime_stats AS rs 
    ON p.plan_id = rs.plan_id 
JOIN sys.query_store_runtime_stats_interval AS rsi 
    ON rsi.runtime_stats_interval_id = rs.runtime_stats_interval_id
WHERE rsi.start_time >= DATEADD(hour, -24, GETUTCDATE()) 
ORDER BY rs.avg_physical_io_reads DESC;
```

 <span data-ttu-id="9a8bb-220">**Consultas com vários planos.**</span><span class="sxs-lookup"><span data-stu-id="9a8bb-220">**Queries with multiple plans.**</span></span> <span data-ttu-id="9a8bb-221">Essas consultas são especialmente interessantes porque são candidatas a regressões em razão de alteração na escolha do plano.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-221">These queries are especially interesting because they are candidates for regressions due to plan choice change.</span></span> <span data-ttu-id="9a8bb-222">A consulta a seguir identifica essas consultas junto com todos os planos:</span><span class="sxs-lookup"><span data-stu-id="9a8bb-222">The following query identifies these queries along with all plans:</span></span>

```
WITH Query_MultPlans
AS
(
    SELECT COUNT(*) AS cnt, q.query_id 
    FROM sys.query_store_query_text AS qt
    JOIN sys.query_store_query AS q
        ON qt.query_text_id = q.query_text_id
    JOIN sys.query_store_plan AS p
        ON p.query_id = q.query_id
    GROUP BY q.query_id
    HAVING COUNT(distinct plan_id) > 1
)

SELECT q.query_id, object_name(object_id) AS ContainingObject, query_sql_text,
plan_id, p.query_plan AS plan_xml,
p.last_compile_start_time, p.last_execution_time
FROM Query_MultPlans AS qm
JOIN sys.query_store_query AS q
    ON qm.query_id = q.query_id
JOIN sys.query_store_plan AS p
    ON q.query_id = p.query_id
JOIN sys.query_store_query_text qt 
    ON qt.query_text_id = q.query_text_id
ORDER BY query_id, plan_id;
```

 <span data-ttu-id="9a8bb-223">**Consultas que regressivou recentemente o desempenho (comparando diferentes pontos no tempo).**</span><span class="sxs-lookup"><span data-stu-id="9a8bb-223">**Queries that recently regressed in performance (comparing different point in time).**</span></span> <span data-ttu-id="9a8bb-224">O exemplo de consulta a seguir retorna todas as consultas para as quais o tempo de execução dobrou nas últimas 48 horas em razão de alteração na escolha do plano.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-224">The following query example returns all queries for which execution time doubled in last 48 hours due to a plan choice change.</span></span> <span data-ttu-id="9a8bb-225">A consulta compara todos os intervalos de estatísticas de runtime lado a lado.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-225">Query compares all runtime stat intervals side by side.</span></span>

```
SELECT 
    qt.query_sql_text, 
    q.query_id, 
    qt.query_text_id, 
    rs1.runtime_stats_id AS runtime_stats_id_1,
    rsi1.start_time AS interval_1, 
    p1.plan_id AS plan_1, 
    rs1.avg_duration AS avg_duration_1, 
    rs2.avg_duration AS avg_duration_2,
    p2.plan_id AS plan_2, 
    rsi2.start_time AS interval_2, 
    rs2.runtime_stats_id AS runtime_stats_id_2
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p1 
    ON q.query_id = p1.query_id 
JOIN sys.query_store_runtime_stats AS rs1 
    ON p1.plan_id = rs1.plan_id 
JOIN sys.query_store_runtime_stats_interval AS rsi1 
    ON rsi1.runtime_stats_interval_id = rs1.runtime_stats_interval_id 
JOIN sys.query_store_plan AS p2 
    ON q.query_id = p2.query_id 
JOIN sys.query_store_runtime_stats AS rs2 
    ON p2.plan_id = rs2.plan_id 
JOIN sys.query_store_runtime_stats_interval AS rsi2 
    ON rsi2.runtime_stats_interval_id = rs2.runtime_stats_interval_id
WHERE rsi1.start_time > DATEADD(hour, -48, GETUTCDATE()) 
    AND rsi2.start_time > rsi1.start_time 
    AND p1.plan_id <> p2.plan_id
    AND rs2.avg_duration > 2*rs1.avg_duration
ORDER BY q.query_id, rsi1.start_time, rsi2.start_time;
```

 <span data-ttu-id="9a8bb-226">Para ver todas as regressões de desempenho (não apenas as relacionadas a alteração na escolha do plano), basta remover a condição `AND p1.plan_id <> p2.plan_id` da consulta anterior.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-226">If you want to see performance all regressions (not only those related to plan choice change) than just remove condition `AND p1.plan_id <> p2.plan_id` from the previous query.</span></span>

 <span data-ttu-id="9a8bb-227">**Consultas que resumiram recentemente no desempenho (comparando a execução recente versus histórico).**</span><span class="sxs-lookup"><span data-stu-id="9a8bb-227">**Queries that recently regressed in performance (comparing recent vs. history execution).**</span></span> <span data-ttu-id="9a8bb-228">A próxima consulta compara os períodos de execução baseados na execução da consulta.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-228">The next query compares query execution based periods of execution.</span></span> <span data-ttu-id="9a8bb-229">Nesse exemplo específico, a consulta compara a execução no período recente (1 hora) versus o período do histórico (último dia) e identifica as que introduziram additional_duration_workload.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-229">In this particular example the query compares execution in recent period (1 hour) vs. history period (last day) and identifies those that introduced additional_duration_workload.</span></span> <span data-ttu-id="9a8bb-230">Essa métrica é calculada como uma diferença entre a média de execução recente e a média de execução do histórico, multiplicado pelo número de execuções recentes.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-230">This metrics is calculated as a difference between recent average execution and history average execution multiplied by the number of recent executions.</span></span> <span data-ttu-id="9a8bb-231">Representa, na verdade, quanto de duração adicional as execuções recentes introduziram em comparação com histórico:</span><span class="sxs-lookup"><span data-stu-id="9a8bb-231">It actually represents how much of additional duration recent executions introduced compared to history:</span></span>

```
--- "Recent" workload - last 1 hour
DECLARE @recent_start_time datetimeoffset;
DECLARE @recent_end_time datetimeoffset;
SET @recent_start_time = DATEADD(hour, -1, SYSUTCDATETIME());
SET @recent_end_time = SYSUTCDATETIME();

--- "History" workload
DECLARE @history_start_time datetimeoffset;
DECLARE @history_end_time datetimeoffset;
SET @history_start_time = DATEADD(hour, -24, SYSUTCDATETIME());
SET @history_end_time = SYSUTCDATETIME();

WITH
hist AS
(
    SELECT 
        p.query_id query_id, 
        CONVERT(float, SUM(rs.avg_duration*rs.count_executions)) total_duration, 
        SUM(rs.count_executions) count_executions,
        COUNT(distinct p.plan_id) num_plans 
     FROM sys.query_store_runtime_stats AS rs
        JOIN sys.query_store_plan p ON p.plan_id = rs.plan_id
    WHERE  (rs.first_execution_time >= @history_start_time AND rs.last_execution_time < @history_end_time)
        OR (rs.first_execution_time <= @history_start_time AND rs.last_execution_time > @history_start_time)
        OR (rs.first_execution_time <= @history_end_time AND rs.last_execution_time > @history_end_time)
    GROUP BY p.query_id
),
recent AS
(
    SELECT 
        p.query_id query_id, 
        CONVERT(float, SUM(rs.avg_duration*rs.count_executions)) total_duration, 
        SUM(rs.count_executions) count_executions,
        COUNT(distinct p.plan_id) num_plans 
    FROM sys.query_store_runtime_stats AS rs
        JOIN sys.query_store_plan p ON p.plan_id = rs.plan_id
    WHERE  (rs.first_execution_time >= @recent_start_time AND rs.last_execution_time < @recent_end_time)
        OR (rs.first_execution_time <= @recent_start_time AND rs.last_execution_time > @recent_start_time)
        OR (rs.first_execution_time <= @recent_end_time AND rs.last_execution_time > @recent_end_time)
    GROUP BY p.query_id
)
SELECT 
    results.query_id query_id,
    results.query_text query_text,
    results.additional_duration_workload additional_duration_workload,
    results.total_duration_recent total_duration_recent,
    results.total_duration_hist total_duration_hist,
    ISNULL(results.count_executions_recent, 0) count_executions_recent,
    ISNULL(results.count_executions_hist, 0) count_executions_hist 
FROM
(
    SELECT
        hist.query_id query_id,
        qt.query_sql_text query_text,
        ROUND(CONVERT(float, recent.total_duration/recent.count_executions-hist.total_duration/hist.count_executions)*(recent.count_executions), 2) AS additional_duration_workload,
        ROUND(recent.total_duration, 2) total_duration_recent, 
        ROUND(hist.total_duration, 2) total_duration_hist,
        recent.count_executions count_executions_recent,
        hist.count_executions count_executions_hist   
    FROM hist 
        JOIN recent 
            ON hist.query_id = recent.query_id 
        JOIN sys.query_store_query AS q 
            ON q.query_id = hist.query_id
        JOIN sys.query_store_query_text AS qt 
            ON q.query_text_id = qt.query_text_id    
) AS results
WHERE additional_duration_workload > 0
ORDER BY additional_duration_workload DESC
OPTION (MERGE JOIN);
```



###  <a name="maintaining-query-performance-stability"></a><a name="Stability"></a><span data-ttu-id="9a8bb-232">Mantendo a estabilidade do desempenho da consulta</span><span class="sxs-lookup"><span data-stu-id="9a8bb-232">Maintaining Query Performance Stability</span></span>
 <span data-ttu-id="9a8bb-233">Para consultas executadas várias vezes você pode perceber que o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usou diferentes planos que resultaram em diferentes utilizações de recurso e duração.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-233">For queries that are executed multiple times you may notice that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] used different plans which resulted in different resource utilization and duration.</span></span> <span data-ttu-id="9a8bb-234">Com o repositório de consultas, você pode facilmente detectar quando o desempenho da consulta regrediu e determinar o plano ideal dentro de um período de interesse.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-234">With Query Store you can easily detect when the query performance regressed and determine the optimal plan within a period of interest.</span></span> <span data-ttu-id="9a8bb-235">Em seguida, você pode forçar o plano ideal para execução futura da consulta.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-235">Then you can force that optimal plan for future query execution.</span></span>

 <span data-ttu-id="9a8bb-236">Você também pode identificar desempenho inconsistente de consulta para uma consulta com parâmetros ( autoparametrizada ou parametrizada manualmente).</span><span class="sxs-lookup"><span data-stu-id="9a8bb-236">You can also identify inconsistent query performance for a query with parameters (either auto- parameterized or manually parameterized).</span></span> <span data-ttu-id="9a8bb-237">Entre diferentes planos, você pode identificar o plano que é rápido e ideal o suficiente para todos ou a maioria dos valores de parâmetro e forçar esse plano, mantendo desempenho previsível para o conjunto mais amplo de cenários de usuário.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-237">Among different plans you can identify plan which is fast and optimal enough for all or most of the parameter values and force that plan; keeping predictable performance for the wider set of user scenarios.</span></span>

 <span data-ttu-id="9a8bb-238">**Impor um plano para uma consulta (aplicar política de imposição).**</span><span class="sxs-lookup"><span data-stu-id="9a8bb-238">**Force or a plan for a query (apply forcing policy).**</span></span> <span data-ttu-id="9a8bb-239">Quando um plano é forçado para determinada consulta, sempre que uma consulta é executada com o plano imposto.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-239">When a plan is forced for a certain query, every time a query comes to execution it will be executed with the plan that is forced.</span></span>

```
EXEC sp_query_store_force_plan @query_id = 48, @plan_id = 49;
```

 <span data-ttu-id="9a8bb-240">Ao usar `sp_query_store_force_plan` você só pode impor planos registrados pelo repositório de consultas como um plano para essa consulta.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-240">When using `sp_query_store_force_plan` you can only force plans that were recorded by Query Store as a plan for that query.</span></span> <span data-ttu-id="9a8bb-241">Em outras palavras, os únicos planos disponíveis para uma consulta são aqueles que já foram usados para executar Q1 enquanto o repositório de consultas estava ativo.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-241">In other words, the only plans available for a query are those that were already used to execute Q1 while Query Store was active.</span></span>

 <span data-ttu-id="9a8bb-242">**Remover a imposição de plano para uma consulta.**</span><span class="sxs-lookup"><span data-stu-id="9a8bb-242">**Remove plan forcing for a query.**</span></span> <span data-ttu-id="9a8bb-243">Para confiar novamente no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] otimizador de consulta para calcular o plano de consulta ideal, use `sp_query_store_unforce_plan` para não forçar o plano selecionado para a consulta.</span><span class="sxs-lookup"><span data-stu-id="9a8bb-243">To rely again on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] query optimizer to calculate the optimal query plan, use `sp_query_store_unforce_plan` to unforce the plan that was selected for the query.</span></span>

```
EXEC sp_query_store_unforce_plan @query_id = 48, @plan_id = 49;
```



## <a name="see-also"></a><span data-ttu-id="9a8bb-244">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9a8bb-244">See Also</span></span>
 <span data-ttu-id="9a8bb-245">[Monitore e ajuste para ferramentas de](../performance/monitor-and-tune-for-performance.md) [ajuste e monitoramento de desempenho](../performance/performance-monitoring-and-tuning-tools.md) de desempenho [abra o monitor de atividade &#40;SQL Server Management Studio](../performance-monitor/open-activity-monitor-sql-server-management-studio.md) [Monitor de atividade](../performance-monitor/activity-monitor.md) de&#41;</span><span class="sxs-lookup"><span data-stu-id="9a8bb-245">[Monitor and Tune for Performance](../performance/monitor-and-tune-for-performance.md) [Performance Monitoring and Tuning Tools](../performance/performance-monitoring-and-tuning-tools.md) [Open Activity Monitor &#40;SQL Server Management Studio&#41;](../performance-monitor/open-activity-monitor-sql-server-management-studio.md) [Activity Monitor](../performance-monitor/activity-monitor.md)</span></span>


