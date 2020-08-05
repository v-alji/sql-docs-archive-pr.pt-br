---
title: Data warehouse de gerenciamento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- data collector [SQL Server], management data warehouse
- data warehouse
- management data warehouse
ms.assetid: 9874a8b2-7ccd-494a-944c-ad33b30b5499
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 96eb26c3e273832aead4aa0421304df17dc5b8ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572106"
---
# <a name="management-data-warehouse"></a><span data-ttu-id="49acd-102">data warehouse de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="49acd-102">Management Data Warehouse</span></span>
  <span data-ttu-id="49acd-103">O data warehouse de gerenciamento é um banco de dados relacional que contém os dados coletados de um servidor representa o destino da coleta de dados.</span><span class="sxs-lookup"><span data-stu-id="49acd-103">The management data warehouse is a relational database that contains the data that is collected from a server that is a data collection target.</span></span> <span data-ttu-id="49acd-104">Esses dados são usados para gerar os relatórios dos conjuntos de coleta de Dados do Sistema e também podem ser usados para criar relatórios personalizados.</span><span class="sxs-lookup"><span data-stu-id="49acd-104">This data is used to generate the reports for the System Data collection sets, and can also be used to create custom reports.</span></span>  
  
 <span data-ttu-id="49acd-105">A infraestrutura do coletor de dados define os trabalhos e os planos de manutenção necessários para implementar as políticas de retenção definidas pelo administrador do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="49acd-105">The data collector infrastructure defines the jobs and maintenance plans that are needed to implement the retention policies defined by the database administrator.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="49acd-106">Para esta versão do coletor de dados, o data warehouse de gerenciamento é criado com o modelo de recuperação simples para minimizar o registro.</span><span class="sxs-lookup"><span data-stu-id="49acd-106">For this release of the data collector, the management data warehouse is created using the Simple recovery model, to minimize logging.</span></span> <span data-ttu-id="49acd-107">Você deve implementar o modelo de recuperação adequado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="49acd-107">You should implement the appropriate recovery model for your organization.</span></span>  
  
## <a name="deploying-and-using-the-data-warehouse"></a><span data-ttu-id="49acd-108">Implantando e usando o data warehouse</span><span class="sxs-lookup"><span data-stu-id="49acd-108">Deploying and Using the Data Warehouse</span></span>  
 <span data-ttu-id="49acd-109">Você pode instalar o data warehouse de gerenciamento na mesma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que executa o coletor de dados.</span><span class="sxs-lookup"><span data-stu-id="49acd-109">You can install the management data warehouse on the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that runs the data collector.</span></span> <span data-ttu-id="49acd-110">No entanto, se o desempenho ou os recursos do servidor forem um problema no servidor que está sendo monitorado, você poderá instalar o data warehouse de gerenciamento em outro computador.</span><span class="sxs-lookup"><span data-stu-id="49acd-110">However, if server resources or performance is an issue on the server being monitored, you can install the management data warehouse on a different computer.</span></span>  
  
 <span data-ttu-id="49acd-111">Os esquemas necessários e seus objetos para os conjuntos de coleta do sistema predefinidos são criados quando você gera o data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="49acd-111">The required schemas and their objects for the predefined system collection sets are created when you create the management data warehouse.</span></span> <span data-ttu-id="49acd-112">Os esquemas que são criados são principal e instantâneos. Um terceiro esquema, custom_snapshots, é criado quando os conjuntos de coleta definidos pelo usuário são criados, o que inclui itens de coleta que usam o tipo de coletor de Consultas T-SQL Genérico.</span><span class="sxs-lookup"><span data-stu-id="49acd-112">The schemas that are created are core and snapshots.A third schema, custom_snapshots, is created when user-defined collection sets are created that include collection items that use the Generic T-SQL Query collector type.</span></span>  
  
###### <a name="core-schema"></a><span data-ttu-id="49acd-113">Esquema principal</span><span class="sxs-lookup"><span data-stu-id="49acd-113">Core schema</span></span>  
 <span data-ttu-id="49acd-114">O esquema principal descreve as tabelas, os procedimentos armazenados e as exibições usados para organizar e identificar os dados coletados.</span><span class="sxs-lookup"><span data-stu-id="49acd-114">The core schema describes the tables, stored procedures, and views that are used to organize and to identify collected data.</span></span> <span data-ttu-id="49acd-115">Essas tabelas são compartilhadas entre todas as tabelas de dados criadas para tipos de coletores individuais.</span><span class="sxs-lookup"><span data-stu-id="49acd-115">These tables are shared among all the data tables created for individual collector types.</span></span> <span data-ttu-id="49acd-116">Esse esquema está bloqueado e só pode ser modificado pelo proprietário do banco de dados do data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="49acd-116">This schema is locked and can only be modified by the owner of the management data warehouse database.</span></span> <span data-ttu-id="49acd-117">Os nomes das tabelas nesse esquema são prefixados por "core".</span><span class="sxs-lookup"><span data-stu-id="49acd-117">The names of the tables in this schema are prefixed by "core".</span></span>  
  
 <span data-ttu-id="49acd-118">A tabela a seguir descreve as tabelas de banco de dados no esquema principal.</span><span class="sxs-lookup"><span data-stu-id="49acd-118">The following table describes the database tables in the core schema.</span></span> <span data-ttu-id="49acd-119">Essas tabelas de banco de dados permitem que o coletor de dados rastreie o local de origem dos dados, quem os inseriu e quando foram carregados no data warehouse.</span><span class="sxs-lookup"><span data-stu-id="49acd-119">These database tables enable the data collector to track where the data came from, who inserted it, and when it was uploaded to the data warehouse.</span></span>  
  
|<span data-ttu-id="49acd-120">Nome da tabela</span><span class="sxs-lookup"><span data-stu-id="49acd-120">Table name</span></span>|<span data-ttu-id="49acd-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="49acd-121">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="49acd-122">core.performance_counter_report_group_items</span><span class="sxs-lookup"><span data-stu-id="49acd-122">core.performance_counter_report_group_items</span></span>|<span data-ttu-id="49acd-123">Armazena informações sobre como os relatórios do data warehouse de gerenciamento devem agrupar e agregar contadores de desempenho.</span><span class="sxs-lookup"><span data-stu-id="49acd-123">Stores information about how the management data warehouse reports should group and aggregate performance counters.</span></span>|  
|<span data-ttu-id="49acd-124">core.snapshots_internal</span><span class="sxs-lookup"><span data-stu-id="49acd-124">core.snapshots_internal</span></span>|<span data-ttu-id="49acd-125">Identifica cada novo instantâneo.</span><span class="sxs-lookup"><span data-stu-id="49acd-125">Identifies each new snapshot.</span></span> <span data-ttu-id="49acd-126">Uma nova linha é inserida nessa tabela sempre que um pacote de carregamento inicia o carregamento de um novo lote de dados.</span><span class="sxs-lookup"><span data-stu-id="49acd-126">A new row is inserted into this table whenever an upload package starts uploading a new batch of data.</span></span>|  
|<span data-ttu-id="49acd-127">core.snapshot_timetable_internal</span><span class="sxs-lookup"><span data-stu-id="49acd-127">core.snapshot_timetable_internal</span></span>|<span data-ttu-id="49acd-128">Armazena informações sobre as horas do instantâneo.</span><span class="sxs-lookup"><span data-stu-id="49acd-128">Stores information about the snapshot times.</span></span> <span data-ttu-id="49acd-129">A hora do instantâneo é armazenada em uma tabela separada porque muitos instantâneos podem ocorrer praticamente ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="49acd-129">The snapshot time is stored in a separate table because many snapshots can happen at nearly the same time.</span></span>|  
|<span data-ttu-id="49acd-130">core.source.info_internal</span><span class="sxs-lookup"><span data-stu-id="49acd-130">core.source.info_internal</span></span>|<span data-ttu-id="49acd-131">Esta tabela armazena informações sobre a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="49acd-131">This table stores information about the data source.</span></span> <span data-ttu-id="49acd-132">Esta tabela é atualizada sempre que um novo conjunto de coleta inicia o carregamento de dados no data warehouse.</span><span class="sxs-lookup"><span data-stu-id="49acd-132">This table is updated whenever a new collection set starts uploading data to the data warehouse.</span></span>|  
|<span data-ttu-id="49acd-133">core.supported_collector_types_internal</span><span class="sxs-lookup"><span data-stu-id="49acd-133">core.supported_collector_types_internal</span></span>|<span data-ttu-id="49acd-134">Contém as IDs dos tipos de coletor registrados que podem carregar dados no data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="49acd-134">Contains the IDs of registered collector types that can upload data to the management data warehouse.</span></span> <span data-ttu-id="49acd-135">Essa tabela só é atualizada quando o esquema do warehouse é atualizado para suportar um novo tipo de coletor.</span><span class="sxs-lookup"><span data-stu-id="49acd-135">This table is only updated when the schema of the warehouse is updated to support a new collector type.</span></span> <span data-ttu-id="49acd-136">Quando o data warehouse de gerenciamento é criado, essa tabela é populada com as IDs dos tipos de coletor fornecidos pelo coletor de dados.</span><span class="sxs-lookup"><span data-stu-id="49acd-136">When the management data warehouse is created, this table is populated with the IDs of the collector types provided by the data collector.</span></span>|  
|<span data-ttu-id="49acd-137">core.wait_categories</span><span class="sxs-lookup"><span data-stu-id="49acd-137">core.wait_categories</span></span>|<span data-ttu-id="49acd-138">Contém as categorias usadas para agrupar tipos de espera de acordo com a característica wait_type.</span><span class="sxs-lookup"><span data-stu-id="49acd-138">Contains the categories used to group wait types according to wait_type characteristic.</span></span>|  
|<span data-ttu-id="49acd-139">core.wait_types</span><span class="sxs-lookup"><span data-stu-id="49acd-139">core.wait_types</span></span>|<span data-ttu-id="49acd-140">Contém os tipos de espera reconhecidos pelo coletor de dados.</span><span class="sxs-lookup"><span data-stu-id="49acd-140">Contains the wait types recognized by the data collector.</span></span>|  
|<span data-ttu-id="49acd-141">core.purge_info_internal</span><span class="sxs-lookup"><span data-stu-id="49acd-141">core.purge_info_internal</span></span>|<span data-ttu-id="49acd-142">Indica que foi feita uma solicitação para parar a remoção de dados do data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="49acd-142">Indicates that a request has been made to stop the removal of data from the management data warehouse.</span></span>|  
  
 <span data-ttu-id="49acd-143">As tabelas precedentes são usadas com tabelas de tipos de coletor para armazenar informações.</span><span class="sxs-lookup"><span data-stu-id="49acd-143">The preceding tables are used with collector type tables to store information.</span></span> <span data-ttu-id="49acd-144">Por exemplo, o tipo de coletor de Rastreamento do SQL Genérico usa as tabelas a seguir para armazenar dados de rastreamento:</span><span class="sxs-lookup"><span data-stu-id="49acd-144">For example, the Generic SQL Trace collector type uses the following tables to store trace data:</span></span>  
  
-   <span data-ttu-id="49acd-145">core.source_info_internal</span><span class="sxs-lookup"><span data-stu-id="49acd-145">core.source_info_internal</span></span>  
  
-   <span data-ttu-id="49acd-146">core.snapshots_internal</span><span class="sxs-lookup"><span data-stu-id="49acd-146">core.snapshots_internal</span></span>  
  
-   <span data-ttu-id="49acd-147">snapshots.trace_info</span><span class="sxs-lookup"><span data-stu-id="49acd-147">snapshots.trace_info</span></span>  
  
-   <span data-ttu-id="49acd-148">snapshots.trace_data</span><span class="sxs-lookup"><span data-stu-id="49acd-148">snapshots.trace_data</span></span>  
  
###### <a name="snapshots-schema"></a><span data-ttu-id="49acd-149">Esquema de instantâneos</span><span class="sxs-lookup"><span data-stu-id="49acd-149">Snapshots schema</span></span>  
 <span data-ttu-id="49acd-150">O esquema de instantâneos descreve os objetos que precisam armazenar e atualizar dados coletados pelos tipos de coletores fornecidos.</span><span class="sxs-lookup"><span data-stu-id="49acd-150">The snapshots schema describes the objects needed to store and maintain the data collected by the collector types that are provided.</span></span> <span data-ttu-id="49acd-151">As tabelas neste esquema são fixas e não precisam ser alteradas durante o tempo de vida do tipo de coletor.</span><span class="sxs-lookup"><span data-stu-id="49acd-151">The tables in this schema are fixed and do not need to be changed during the lifetime of the collector type.</span></span> <span data-ttu-id="49acd-152">Se houver necessidade de alterações, o esquema só poderá ser alterado por membros com função mdw_admin.</span><span class="sxs-lookup"><span data-stu-id="49acd-152">If changes are needed, the schema can only be changed by members of the mdw_admin role.</span></span> <span data-ttu-id="49acd-153">Essas tabelas são criadas para armazenar os dados coletados pelos conjuntos de coleta de dados do sistema.</span><span class="sxs-lookup"><span data-stu-id="49acd-153">These tables are created to store the data collected by the System Data collection sets.</span></span>  
  
 <span data-ttu-id="49acd-154">As tabelas a seguir ilustram uma parte do esquema do data warehouse de gerenciamento necessária para os conjuntos de coleta de atividades do servidor e estatísticas de consulta.</span><span class="sxs-lookup"><span data-stu-id="49acd-154">The following tables illustrate a portion of the management data warehouse schema that is required for the Server Activity and Query Statistics collection sets.</span></span>  
  
-   <span data-ttu-id="49acd-155">Tabelas de recurso de nível de sistema</span><span class="sxs-lookup"><span data-stu-id="49acd-155">System-level resource tables</span></span>  
  
    -   <span data-ttu-id="49acd-156">**snapshots.os_wait_stats**</span><span class="sxs-lookup"><span data-stu-id="49acd-156">**snapshots.os_wait_stats**</span></span>  
  
    -   <span data-ttu-id="49acd-157">**snapshots.os_latch_stats**</span><span class="sxs-lookup"><span data-stu-id="49acd-157">**snapshots.os_latch_stats**</span></span>  
  
    -   <span data-ttu-id="49acd-158">**snapshots.os_schedulers**</span><span class="sxs-lookup"><span data-stu-id="49acd-158">**snapshots.os_schedulers**</span></span>  
  
    -   `snapshots.os_memory_clerks`  
  
    -   <span data-ttu-id="49acd-159">**snapshots.os_memory_nodes**</span><span class="sxs-lookup"><span data-stu-id="49acd-159">**snapshots.os_memory_nodes**</span></span>  
  
    -   <span data-ttu-id="49acd-160">snapshots.sql_process_and_system_memory</span><span class="sxs-lookup"><span data-stu-id="49acd-160">snapshots.sql_process_and_system_memory</span></span>  
  
-   <span data-ttu-id="49acd-161">Atividade do sistema</span><span class="sxs-lookup"><span data-stu-id="49acd-161">System activity</span></span>  
  
    -   <span data-ttu-id="49acd-162">snapshots.active_sessions_and_requests</span><span class="sxs-lookup"><span data-stu-id="49acd-162">snapshots.active_sessions_and_requests</span></span>  
  
-   <span data-ttu-id="49acd-163">Estatísticas de consulta</span><span class="sxs-lookup"><span data-stu-id="49acd-163">Query statistics</span></span>  
  
    -   <span data-ttu-id="49acd-164">snapshots.query_stats</span><span class="sxs-lookup"><span data-stu-id="49acd-164">snapshots.query_stats</span></span>  
  
-   <span data-ttu-id="49acd-165">Estatísticas de E/S</span><span class="sxs-lookup"><span data-stu-id="49acd-165">I/O statistics</span></span>  
  
    -   `snapshots.io_virtual_file_stats`  
  
-   <span data-ttu-id="49acd-166">Texto e plano de consulta</span><span class="sxs-lookup"><span data-stu-id="49acd-166">Query text and plan</span></span>  
  
    -   <span data-ttu-id="49acd-167">snapshots.notable_query_text</span><span class="sxs-lookup"><span data-stu-id="49acd-167">snapshots.notable_query_text</span></span>  
  
    -   <span data-ttu-id="49acd-168">snapshots.notable_query_plan</span><span class="sxs-lookup"><span data-stu-id="49acd-168">snapshots.notable_query_plan</span></span>  
  
-   <span data-ttu-id="49acd-169">Estatísticas de consultas normalizadas</span><span class="sxs-lookup"><span data-stu-id="49acd-169">Normalized query statistics</span></span>  
  
    -   <span data-ttu-id="49acd-170">snapshots.distinct_queries</span><span class="sxs-lookup"><span data-stu-id="49acd-170">snapshots.distinct_queries</span></span>  
  
    -   <span data-ttu-id="49acd-171">snapshots.distinct_query_to_handle</span><span class="sxs-lookup"><span data-stu-id="49acd-171">snapshots.distinct_query_to_handle</span></span>  
  
 <span data-ttu-id="49acd-172">**Esquema custom_snapshots**</span><span class="sxs-lookup"><span data-stu-id="49acd-172">**Custom_snapshots schema**</span></span>  
  
 <span data-ttu-id="49acd-173">Um esquema custom_snapshots descreve novas tabelas e exibições criadas quando os tipos de coletor padrão ou de terceiros são usados para criar conjuntos de coleta definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="49acd-173">The custom_snapshots schema describes new tables and views that are created when standard or third-party collector types are used to create user-defined collection sets.</span></span> <span data-ttu-id="49acd-174">Qualquer tipo de coletor que exija uma nova tabela de dados para um item de coleta pode criar essa tabela neste esquema.</span><span class="sxs-lookup"><span data-stu-id="49acd-174">Any collector type that requires a new data table for a collection item can create that table in this schema.</span></span> <span data-ttu-id="49acd-175">Novas tabelas podem ser adicionadas a esse esquema por membros da função mdw_writer.</span><span class="sxs-lookup"><span data-stu-id="49acd-175">New tables can be added in this schema by members of the mdw_writer role.</span></span> <span data-ttu-id="49acd-176">Todas as outras alterações no esquema só poderão ser feitas por membros da função mdw_admin.</span><span class="sxs-lookup"><span data-stu-id="49acd-176">Any other changes to the schema can only be made by members of the mdw_admin role.</span></span>  
  
 <span data-ttu-id="49acd-177">Você pode obter informações detalhadas sobre o tipo de dados e o conteúdo de colunas de tabelas do banco de dados lendo a documentação do procedimento armazenado do coletor de dados adequado para cada uma das tabelas.</span><span class="sxs-lookup"><span data-stu-id="49acd-177">You can get detailed data type and content information for the database table columns by reading the documentation for the appropriate data collector stored procedure for each of the tables.</span></span>  
  
### <a name="best-practices"></a><span data-ttu-id="49acd-178">Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="49acd-178">Best Practices</span></span>  
 <span data-ttu-id="49acd-179">Ao trabalhar com o data warehouse de gerenciamento, recomendamos que você siga estas práticas recomendadas:</span><span class="sxs-lookup"><span data-stu-id="49acd-179">When working with the management data warehouse, we recommend following these best practices:</span></span>  
  
-   <span data-ttu-id="49acd-180">Não modifique o metadados de tabelas de data warehouse de gerenciamento a menos que você esteja adicionando um tipo de coletor novo.</span><span class="sxs-lookup"><span data-stu-id="49acd-180">Do not modify the metadata of management data warehouse tables unless you are adding a new collector type.</span></span>  
  
-   <span data-ttu-id="49acd-181">Não modifique os dados diretamente no data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="49acd-181">Do not directly modify the data in the management data warehouse.</span></span> <span data-ttu-id="49acd-182">Alterar os dados que coletados invalida a legitimidade dos dados coletados.</span><span class="sxs-lookup"><span data-stu-id="49acd-182">Changing the data that you have collected invalidates the legitimacy of the collected data.</span></span>  
  
-   <span data-ttu-id="49acd-183">Em vez de usar as tabelas diretamente, use os procedimentos armazenados documentados e as funções fornecidas pelo coletor de dados para acessar instância e dados de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="49acd-183">Instead of directly using the tables, use the documented stored procedures and functions that are provided with the data collector to access instance and application data.</span></span> <span data-ttu-id="49acd-184">Os nomes e as definições de tabelas podem ser alterados. Elas são alteradas quando você atualiza o aplicativo e talvez sejam alteradas em futuras versões.</span><span class="sxs-lookup"><span data-stu-id="49acd-184">The table names and definitions can change, do change when you update the application, and might change in future releases.</span></span>  
  
## <a name="change-history"></a><span data-ttu-id="49acd-185">Histórico de alterações</span><span class="sxs-lookup"><span data-stu-id="49acd-185">Change History</span></span>  
  
|<span data-ttu-id="49acd-186">Conteúdo atualizado</span><span class="sxs-lookup"><span data-stu-id="49acd-186">Updated content</span></span>|  
|---------------------|  
|<span data-ttu-id="49acd-187">Adicionada a tabela core.performance_counter_report_group_items à seção "Esquema principal".</span><span class="sxs-lookup"><span data-stu-id="49acd-187">Added the core.performance_counter_report_group_items table to the "Core schema" section.</span></span>|  
|<span data-ttu-id="49acd-188">Atualizada a lista de tabelas na seção "Esquema de instantâneos".</span><span class="sxs-lookup"><span data-stu-id="49acd-188">Updated the list of tables in the "Snapshots schema" section.</span></span> <span data-ttu-id="49acd-189">Adicionados snapshots.os_memory_clerks,snapshots.sql_process_and_system_memory e snapshots.io_virtual_file_stats.</span><span class="sxs-lookup"><span data-stu-id="49acd-189">Added snapshots.os_memory_clerks,snapshots.sql_process_and_system_memory, and snapshots.io_virtual_file_stats.</span></span> <span data-ttu-id="49acd-190">snapshots.os_process_memory e snapshots.distinct_query_stats foram removidos.</span><span class="sxs-lookup"><span data-stu-id="49acd-190">Removedsnapshots.os_process_memory and snapshots.distinct_query_stats.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="49acd-191">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="49acd-191">See Also</span></span>  
 <span data-ttu-id="49acd-192">[Procedimentos armazenados do data warehouse de gerenciamento &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/management-data-warehouse-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="49acd-192">[Management Data Warehouse Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/management-data-warehouse-stored-procedures-transact-sql) </span></span>  
 <span data-ttu-id="49acd-193">[Procedimentos armazenados de coletor de dados &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="49acd-193">[Data Collector Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql) </span></span>  
 <span data-ttu-id="49acd-194">[Coleta de Dados](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="49acd-194">[Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="49acd-195">Exibir um relatório de conjuntos de coleta &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="49acd-195">View a Collection Set Report &#40;SQL Server Management Studio&#41;</span></span>](view-a-collection-set-report-sql-server-management-studio.md)  
  
  
