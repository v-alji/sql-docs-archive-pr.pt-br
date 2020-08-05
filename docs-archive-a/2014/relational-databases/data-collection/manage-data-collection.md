---
title: Gerenciar a coleta de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- data collection [SQL Server]
- data collector [SQL Server], Transact-SQL
- data collector [SQL Server], SQL Server Management Studio
ms.assetid: bc137daa-9f37-4c01-9766-8b7350c75af8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0a7d88923bc41939541bedeed2d40908e454e9c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572108"
---
# <a name="manage-data-collection"></a><span data-ttu-id="ec574-102">Gerenciar coleta de dados</span><span class="sxs-lookup"><span data-stu-id="ec574-102">Manage Data Collection</span></span>
  <span data-ttu-id="ec574-103">Você pode usar [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)] procedimentos armazenados e funções para gerenciar diferentes aspectos da coleta de dados, como habilitar ou desabilitar a coleta de dados, alterar a configuração de um conjunto de coleta ou exibir dados no data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="ec574-103">You can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures and functions to manage different aspects of data collection, such as enabling or disabling data collection, changing a collection set configuration, or viewing data in the management data warehouse.</span></span>  
  
## <a name="manage-data-collection-by-using-sql-server-management-studio"></a><span data-ttu-id="ec574-104">Gerenciar a coleta de dados usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ec574-104">Manage Data Collection by Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="ec574-105">Você pode executar as seguintes tarefas relacionadas ao coletor de dados usando o Pesquisador de Objetos no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ec574-105">You can perform the following data collector-related tasks by using Object Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]:</span></span>  
  
-   [<span data-ttu-id="ec574-106">Configurar o Data Warehouse de Gerenciamento &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-106">Configure the Management Data Warehouse &#40;SQL Server Management Studio&#41;</span></span>](configure-the-management-data-warehouse-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="ec574-107">Configurar propriedades de um coletor de dados</span><span class="sxs-lookup"><span data-stu-id="ec574-107">Configure Properties of a Data Collector</span></span>](configure-properties-of-a-data-collector.md)  
  
-   [<span data-ttu-id="ec574-108">Habilitar ou desabilitar a coleta de dados</span><span class="sxs-lookup"><span data-stu-id="ec574-108">Enable or Disable Data Collection</span></span>](data-collection.md)  
  
-   [<span data-ttu-id="ec574-109">Iniciar ou interromper um conjunto de coleta</span><span class="sxs-lookup"><span data-stu-id="ec574-109">Start or Stop a Collection Set</span></span>](start-or-stop-a-collection-set.md)  
  
-   [<span data-ttu-id="ec574-110">Usar o SQL Server Profiler para criar um conjunto de coleta de Rastreamento do SQL &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-110">Use SQL Server Profiler to Create a SQL Trace Collection Set &#40;SQL Server Management Studio&#41;</span></span>](use-sql-server-profiler-to-create-a-sql-trace-collection-set.md)  
  
-   [<span data-ttu-id="ec574-111">Exibir logs de conjuntos de coleta &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-111">View Collection Set Logs &#40;SQL Server Management Studio&#41;</span></span>](view-collection-set-logs-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="ec574-112">Exibir ou alterar agendas de conjuntos de coleta &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-112">View or Change Collection Set Schedules &#40;SQL Server Management Studio&#41;</span></span>](view-or-change-collection-set-schedules-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="ec574-113">Exibir um relatório de conjuntos de coleta &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-113">View a Collection Set Report &#40;SQL Server Management Studio&#41;</span></span>](view-a-collection-set-report-sql-server-management-studio.md)  
  
## <a name="manage-data-collection-by-using-transact-sql"></a><span data-ttu-id="ec574-114">Gerenciar coleta de dados usando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ec574-114">Manage Data Collection by Using Transact-SQL</span></span>  
 <span data-ttu-id="ec574-115">O coletor de dados fornece uma extensa coleção de procedimentos armazenados que você pode usar para executar qualquer tarefa relacionada ao coletor de dados.</span><span class="sxs-lookup"><span data-stu-id="ec574-115">The data collector provides an extensive collection of stored procedures that you can use to perform any data-collector related task.</span></span> <span data-ttu-id="ec574-116">Por exemplo, usando o [!INCLUDE[tsql](../../includes/tsql-md.md)], é possível realizar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="ec574-116">For example, by using [!INCLUDE[tsql](../../includes/tsql-md.md)], you can perform the following tasks:</span></span>  
  
-   [<span data-ttu-id="ec574-117">Configurar parâmetros de coleta de dados &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-117">Configure Data Collection Parameters &#40;Transact-SQL&#41;</span></span>](configure-data-collection-parameters-transact-sql.md)  
  
-   [<span data-ttu-id="ec574-118">Habilitar ou desabilitar a coleta de dados</span><span class="sxs-lookup"><span data-stu-id="ec574-118">Enable or Disable Data Collection</span></span>](data-collection.md)  
  
-   [<span data-ttu-id="ec574-119">Iniciar ou interromper um conjunto de coleta</span><span class="sxs-lookup"><span data-stu-id="ec574-119">Start or Stop a Collection Set</span></span>](start-or-stop-a-collection-set.md)  
  
-   [<span data-ttu-id="ec574-120">Criar um conjunto de coleta personalizado que usa o tipo de coletor de Consultas T-SQL genérico &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-120">Create a Custom Collection Set That Uses the Generic T-SQL Query Collector Type &#40;Transact-SQL&#41;</span></span>](create-custom-collection-set-generic-t-sql-query-collector-type.md)  
  
-   [<span data-ttu-id="ec574-121">Adicionar um item de coleta a um conjunto de coletas &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-121">Add a Collection Item to a Collection Set &#40;Transact-SQL&#41;</span></span>](add-a-collection-item-to-a-collection-set-transact-sql.md)  
  
 <span data-ttu-id="ec574-122">Além disso, existem funções e exibições que podem ser utilizadas para obter dados de configuração dos bancos de dados msdb e do data warehouse de gerenciamento, dados do log de execução e dados armazenados no data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="ec574-122">In addition, there are functions and views that you can use to get configuration data for the msdb and management data warehouse databases, execution log data, and data that is stored in the management data warehouse.</span></span>  
  
 <span data-ttu-id="ec574-123">Você pode usar os procedimentos armazenados, funções e exibições fornecidos para criar seus próprios cenários de coleta de dados completos.</span><span class="sxs-lookup"><span data-stu-id="ec574-123">You can use the stored procedures, functions, and views that are provided to create your own end-to-end data collection scenarios.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ec574-124">Diferentemente de procedimentos armazenados regulares, os procedimentos armazenados do coletor de dados usam apenas parâmetros digitados e não oferecem suporte a conversão de tipo de dados automática.</span><span class="sxs-lookup"><span data-stu-id="ec574-124">Unlike regular stored procedures, the data collector stored procedures use strictly typed parameters and do not support automatic data type conversion.</span></span> <span data-ttu-id="ec574-125">Se esses parâmetros não forem chamados pelos tipos de dados com parâmetros de entrada corretos, como especificado na descrição do argumento, o procedimento armazenado retornará um erro.</span><span class="sxs-lookup"><span data-stu-id="ec574-125">If these parameters are not called with the correct input parameter data types, as specified in the argument description, the stored procedure returns an error.</span></span>  
  
 <span data-ttu-id="ec574-126">Você pode usar o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para criar e executar os códigos de amostra fornecidos.</span><span class="sxs-lookup"><span data-stu-id="ec574-126">You can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to create and execute the provided code samples.</span></span> <span data-ttu-id="ec574-127">Para obter mais informações, veja [Pesquisador de Objetos](../../ssms/object/object-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="ec574-127">For more information, see [Object Explorer](../../ssms/object/object-explorer.md).</span></span> <span data-ttu-id="ec574-128">Como alternativa, você pode criar a consulta em qualquer editor e salvá-la em um arquivo de texto com uma extensão de nome de arquivo .sql.</span><span class="sxs-lookup"><span data-stu-id="ec574-128">As an alternative you can create the query in any editor and save it in a text file that has a .sql file name extension.</span></span> <span data-ttu-id="ec574-129">Você pode executar a consulta no prompt de comando do Windows usando o utilitário `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="ec574-129">You can execute the query from the Windows command prompt using the `sqlcmd` utility.</span></span> <span data-ttu-id="ec574-130">Para obter mais informações, consulte [Usar o Utilitário sqlcmd](../scripting/sqlcmd-use-the-utility.md).</span><span class="sxs-lookup"><span data-stu-id="ec574-130">For more information, see [Use the sqlcmd Utility](../scripting/sqlcmd-use-the-utility.md).</span></span>  
  
### <a name="stored-procedures-and-views"></a><span data-ttu-id="ec574-131">Stored Procedures and Views</span><span class="sxs-lookup"><span data-stu-id="ec574-131">Stored Procedures and Views</span></span>  
 <span data-ttu-id="ec574-132">**Trabalhando com o coletor de dados**</span><span class="sxs-lookup"><span data-stu-id="ec574-132">**Working with the data collector**</span></span>  
  
 <span data-ttu-id="ec574-133">A tabela a seguir descreve os procedimentos armazenados que podem ser usados para funcionar com o coletor de dados.</span><span class="sxs-lookup"><span data-stu-id="ec574-133">The following table describes the stored procedures that you can use to work with the data collector.</span></span>  
  
|<span data-ttu-id="ec574-134">Nome do procedimento</span><span class="sxs-lookup"><span data-stu-id="ec574-134">Procedure name</span></span>|<span data-ttu-id="ec574-135">Descrição</span><span class="sxs-lookup"><span data-stu-id="ec574-135">Description</span></span>|  
|--------------------|-----------------|  
|[<span data-ttu-id="ec574-136">sp_syscollector_enable_collector</span><span class="sxs-lookup"><span data-stu-id="ec574-136">sp_syscollector_enable_collector</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-enable-collector-transact-sql)|<span data-ttu-id="ec574-137">Habilite o coletor de dados.</span><span class="sxs-lookup"><span data-stu-id="ec574-137">Enable the data collector.</span></span>|  
|[<span data-ttu-id="ec574-138">sp_syscollector_disable_collector</span><span class="sxs-lookup"><span data-stu-id="ec574-138">sp_syscollector_disable_collector</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-disable-collector-transact-sql)|<span data-ttu-id="ec574-139">Desabilita o coletor de dados.</span><span class="sxs-lookup"><span data-stu-id="ec574-139">Disable the data collector.</span></span>|  
  
 <span data-ttu-id="ec574-140">**Trabalhando com conjuntos de coleta**</span><span class="sxs-lookup"><span data-stu-id="ec574-140">**Working with collection sets**</span></span>  
  
 <span data-ttu-id="ec574-141">A tabela a seguir descreve os procedimentos armazenados que podem ser usados para funcionar com os conjuntos de coleta.</span><span class="sxs-lookup"><span data-stu-id="ec574-141">The following table describes the stored procedures that you can use to work with collection sets.</span></span>  
  
|<span data-ttu-id="ec574-142">Nome do procedimento</span><span class="sxs-lookup"><span data-stu-id="ec574-142">Procedure name</span></span>|<span data-ttu-id="ec574-143">Descrição</span><span class="sxs-lookup"><span data-stu-id="ec574-143">Description</span></span>|  
|--------------------|-----------------|  
|[<span data-ttu-id="ec574-144">sp_syscollector_run_collection_set &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-144">sp_syscollector_run_collection_set &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-run-collection-set-transact-sql)|<span data-ttu-id="ec574-145">Executar um conjunto de coleta sob demanda.</span><span class="sxs-lookup"><span data-stu-id="ec574-145">Run a collection set on demand.</span></span>|  
|[<span data-ttu-id="ec574-146">sp_syscollector_start_collection_set &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-146">sp_syscollector_start_collection_set &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-start-collection-set-transact-sql)|<span data-ttu-id="ec574-147">Iniciar um conjunto de coleta.</span><span class="sxs-lookup"><span data-stu-id="ec574-147">Start a collection set.</span></span>|  
|[<span data-ttu-id="ec574-148">sp_syscollector_stop_collection_set &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-148">sp_syscollector_stop_collection_set &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-stop-collection-set-transact-sql)|<span data-ttu-id="ec574-149">Parar um conjunto de coleta.</span><span class="sxs-lookup"><span data-stu-id="ec574-149">Stop a collection set.</span></span>|  
|[<span data-ttu-id="ec574-150">sp_syscollector_create_collection_set &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-150">sp_syscollector_create_collection_set &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-create-collection-set-transact-sql)|<span data-ttu-id="ec574-151">Criar um conjunto de coleta.</span><span class="sxs-lookup"><span data-stu-id="ec574-151">Create a collection set.</span></span>|  
|[<span data-ttu-id="ec574-152">sp_syscollector_delete_collection_set &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-152">sp_syscollector_delete_collection_set &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-delete-collection-set-transact-sql)|<span data-ttu-id="ec574-153">Excluir um conjunto de coleta.</span><span class="sxs-lookup"><span data-stu-id="ec574-153">Delete a collection set.</span></span>|  
|[<span data-ttu-id="ec574-154">sp_syscollector_update_collection_set &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-154">sp_syscollector_update_collection_set &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-update-collection-set-transact-sql)|<span data-ttu-id="ec574-155">Alterar a configuração de um conjunto de coleta.</span><span class="sxs-lookup"><span data-stu-id="ec574-155">Change a collection set configuration.</span></span>|  
|[<span data-ttu-id="ec574-156">sp_syscollector_upload_collection_set &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-156">sp_syscollector_upload_collection_set &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-upload-collection-set-transact-sql)|<span data-ttu-id="ec574-157">Carregar dados de um conjunto de coleta no data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="ec574-157">Upload collection set data to the management data warehouse.</span></span> <span data-ttu-id="ec574-158">Isso é efetivamente um carregamento sob demanda.</span><span class="sxs-lookup"><span data-stu-id="ec574-158">This is effectively an on-demand upload.</span></span>|  
  
 <span data-ttu-id="ec574-159">**Trabalhando com itens de coleta**</span><span class="sxs-lookup"><span data-stu-id="ec574-159">**Working with collection items**</span></span>  
  
 <span data-ttu-id="ec574-160">A tabela a seguir descreve os procedimentos armazenados que podem ser usados para funcionar com os itens de coleta.</span><span class="sxs-lookup"><span data-stu-id="ec574-160">The following table describes the stored procedures that you can use to work with collection items.</span></span>  
  
|<span data-ttu-id="ec574-161">Nome do procedimento</span><span class="sxs-lookup"><span data-stu-id="ec574-161">Procedure name</span></span>|<span data-ttu-id="ec574-162">Descrição</span><span class="sxs-lookup"><span data-stu-id="ec574-162">Description</span></span>|  
|--------------------|-----------------|  
|[<span data-ttu-id="ec574-163">sp_syscollector_create_collection_item &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-163">sp_syscollector_create_collection_item &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-create-collection-item-transact-sql)|<span data-ttu-id="ec574-164">Criar um item de coleta.</span><span class="sxs-lookup"><span data-stu-id="ec574-164">Create a collection item.</span></span>|  
|[<span data-ttu-id="ec574-165">sp_syscollector_delete_collection_item &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-165">sp_syscollector_delete_collection_item &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-delete-collection-item-transact-sql)|<span data-ttu-id="ec574-166">Excluir um item de coleta.</span><span class="sxs-lookup"><span data-stu-id="ec574-166">Delete a collection item.</span></span>|  
|[<span data-ttu-id="ec574-167">sp_syscollector_update_collection_item &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-167">sp_syscollector_update_collection_item &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-update-collection-item-transact-sql)|<span data-ttu-id="ec574-168">Atualizar um item de coleta.</span><span class="sxs-lookup"><span data-stu-id="ec574-168">Update a collection item.</span></span>|  
  
 <span data-ttu-id="ec574-169">**Trabalhando com tipos de coletor**</span><span class="sxs-lookup"><span data-stu-id="ec574-169">**Working with collector types**</span></span>  
  
 <span data-ttu-id="ec574-170">A tabela a seguir descreve os procedimentos armazenados que podem ser usados para funcionar com os tipos de coletor.</span><span class="sxs-lookup"><span data-stu-id="ec574-170">The following table describes the stored procedures that you can use to work with collector types.</span></span>  
  
|<span data-ttu-id="ec574-171">Nome do procedimento</span><span class="sxs-lookup"><span data-stu-id="ec574-171">Procedure name</span></span>|<span data-ttu-id="ec574-172">Descrição</span><span class="sxs-lookup"><span data-stu-id="ec574-172">Description</span></span>|  
|--------------------|-----------------|  
|[<span data-ttu-id="ec574-173">sp_syscollector_create_collector_type &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-173">sp_syscollector_create_collector_type &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-create-collector-type-transact-sql)|<span data-ttu-id="ec574-174">Criar um tipo de coletor.</span><span class="sxs-lookup"><span data-stu-id="ec574-174">Create a collector type.</span></span>|  
|[<span data-ttu-id="ec574-175">sp_syscollector_update_collector_type &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-175">sp_syscollector_update_collector_type &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-update-collector-type-transact-sql)|<span data-ttu-id="ec574-176">Atualizar um tipo de coletor.</span><span class="sxs-lookup"><span data-stu-id="ec574-176">Update a collector type.</span></span>|  
|[<span data-ttu-id="ec574-177">sp_syscollector_delete_collector_type &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-177">sp_syscollector_delete_collector_type &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-delete-collector-type-transact-sql)|<span data-ttu-id="ec574-178">Exclui um tipo de coletor.</span><span class="sxs-lookup"><span data-stu-id="ec574-178">Delete a collector type.</span></span>|  
  
 <span data-ttu-id="ec574-179">**Obtendo informações de configuração**</span><span class="sxs-lookup"><span data-stu-id="ec574-179">**Getting configuration information**</span></span>  
  
 <span data-ttu-id="ec574-180">A tabela a seguir descreve as exibições que podem ser usadas para se obter informações de configuração e dados do log de execução.</span><span class="sxs-lookup"><span data-stu-id="ec574-180">The following table describes the views that you can use for getting configuration information and execution log data.</span></span>  
  
|<span data-ttu-id="ec574-181">Nome da exibição</span><span class="sxs-lookup"><span data-stu-id="ec574-181">View name</span></span>|<span data-ttu-id="ec574-182">Descrição</span><span class="sxs-lookup"><span data-stu-id="ec574-182">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="ec574-183">syscollector_config_store &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-183">syscollector_config_store &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/syscollector-config-store-transact-sql)|<span data-ttu-id="ec574-184">Obter configuração do coletor de dados.</span><span class="sxs-lookup"><span data-stu-id="ec574-184">Get data collector configuration.</span></span>|  
|[<span data-ttu-id="ec574-185">syscollector_collection_items &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-185">syscollector_collection_items &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/syscollector-collection-items-transact-sql)|<span data-ttu-id="ec574-186">Obter informações sobre o item de coleta.</span><span class="sxs-lookup"><span data-stu-id="ec574-186">Get collection item information.</span></span>|  
|[<span data-ttu-id="ec574-187">syscollector_collection_sets &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-187">syscollector_collection_sets &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/syscollector-collection-sets-transact-sql)|<span data-ttu-id="ec574-188">Obter informações sobre o conjunto de coleta.</span><span class="sxs-lookup"><span data-stu-id="ec574-188">Get collection set information.</span></span>|  
|[<span data-ttu-id="ec574-189">syscollector_collector_types &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-189">syscollector_collector_types &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/syscollector-collector-types-transact-sql)|<span data-ttu-id="ec574-190">Obter informações sobre o tipo de coletor.</span><span class="sxs-lookup"><span data-stu-id="ec574-190">Get collector type information.</span></span>|  
|[<span data-ttu-id="ec574-191">syscollector_execution_log &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-191">syscollector_execution_log &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/syscollector-execution-log-transact-sql)|<span data-ttu-id="ec574-192">Obter informações sobre o conjunto de coleta e a execução do pacote.</span><span class="sxs-lookup"><span data-stu-id="ec574-192">Get information about collection set and package execution.</span></span>|  
|[<span data-ttu-id="ec574-193">syscollector_execution_stats &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-193">syscollector_execution_stats &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/syscollector-execution-stats-transact-sql)|<span data-ttu-id="ec574-194">Obter informações sobre a execução de tarefa.</span><span class="sxs-lookup"><span data-stu-id="ec574-194">Get information about task execution.</span></span>|  
|[<span data-ttu-id="ec574-195">syscollector_execution_log_full &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-195">syscollector_execution_log_full &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/syscollector-execution-log-full-transact-sql)|<span data-ttu-id="ec574-196">Obter informações quando o log de execução estiver completo.</span><span class="sxs-lookup"><span data-stu-id="ec574-196">Get information when the execution log is full.</span></span>|  
  
 <span data-ttu-id="ec574-197">**Configurando o acesso ao data warehouse de gerenciamento**</span><span class="sxs-lookup"><span data-stu-id="ec574-197">**Configuring access to the management data warehouse**</span></span>  
  
 <span data-ttu-id="ec574-198">A tabela a seguir descreve os procedimentos armazenados que podem ser usados para configurar o acesso ao data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="ec574-198">The following table describes the stored procedures that you can use to configure access to the management data warehouse.</span></span>  
  
|<span data-ttu-id="ec574-199">Nome do procedimento</span><span class="sxs-lookup"><span data-stu-id="ec574-199">Procedure name</span></span>|<span data-ttu-id="ec574-200">Descrição</span><span class="sxs-lookup"><span data-stu-id="ec574-200">Description</span></span>|  
|--------------------|-----------------|  
|[<span data-ttu-id="ec574-201">sp_syscollector_set_warehouse_database_name &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-201">sp_syscollector_set_warehouse_database_name &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-set-warehouse-database-name-transact-sql)|<span data-ttu-id="ec574-202">Especificar o nome de banco de dados definido na cadeia de caracteres de conexão para o data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="ec574-202">Specify the database name defined in the connection string for the management data warehouse.</span></span>|  
|[<span data-ttu-id="ec574-203">sp_syscollector_set_warehouse_instance_name &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-203">sp_syscollector_set_warehouse_instance_name &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-set-warehouse-instance-name-transact-sql)|<span data-ttu-id="ec574-204">Especificar a instância definida na cadeia de caracteres de conexão para o data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="ec574-204">Specify the instance defined in the connection string for the management data warehouse.</span></span>|  
  
 <span data-ttu-id="ec574-205">**Configurando o data warehouse de gerenciamento**</span><span class="sxs-lookup"><span data-stu-id="ec574-205">**Configuring the management data warehouse**</span></span>  
  
 <span data-ttu-id="ec574-206">A tabela a seguir descreve os procedimentos armazenados que podem ser usados para funcionar com a configuração do data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="ec574-206">The following table describes the stored procedures that you can use to work with the management data warehouse configuration.</span></span>  
  
|<span data-ttu-id="ec574-207">Nome do procedimento</span><span class="sxs-lookup"><span data-stu-id="ec574-207">Procedure name</span></span>|<span data-ttu-id="ec574-208">Descrição</span><span class="sxs-lookup"><span data-stu-id="ec574-208">Description</span></span>|  
|--------------------|-----------------|  
|[<span data-ttu-id="ec574-209">core.sp_create_snapshot &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-209">core.sp_create_snapshot &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/core-sp-create-snapshot-transact-sql)|<span data-ttu-id="ec574-210">Criar um instantâneo de coleta no data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="ec574-210">Create a collection snapshot in the management data warehouse.</span></span>|  
|[<span data-ttu-id="ec574-211">core.sp_update_data_source &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-211">core.sp_update_data_source &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/core-sp-update-data-source-transact-sql)|<span data-ttu-id="ec574-212">Atualizar a fonte de dados para coleta de dados.</span><span class="sxs-lookup"><span data-stu-id="ec574-212">Update the data source for data collection.</span></span>|  
|[<span data-ttu-id="ec574-213">core.sp_add_collector_type &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-213">core.sp_add_collector_type &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/core-sp-add-collector-type-transact-sql)|<span data-ttu-id="ec574-214">Adicionar um tipo de coletor ao data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="ec574-214">Add a collector type to the management data warehouse.</span></span>|  
|[<span data-ttu-id="ec574-215">core.sp_remove_collector_type &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-215">core.sp_remove_collector_type &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/core-sp-remove-collector-type-transact-sql)|<span data-ttu-id="ec574-216">Remover um tipo de coletor do data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="ec574-216">Remove a collector type from the management data warehouse.</span></span>|  
|[<span data-ttu-id="ec574-217">core.sp_purge_data &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-217">core.sp_purge_data &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/core-sp-purge-data-transact-sql)|<span data-ttu-id="ec574-218">Excluir dados do data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="ec574-218">Delete data from the management data warehouse.</span></span>|  
  
 <span data-ttu-id="ec574-219">**Trabalhando com pacotes de carregamento**</span><span class="sxs-lookup"><span data-stu-id="ec574-219">**Working with upload packages**</span></span>  
  
 <span data-ttu-id="ec574-220">A tabela a seguir descreve os procedimentos armazenados que podem ser usados para funcionar com pacotes de carregamento.</span><span class="sxs-lookup"><span data-stu-id="ec574-220">The following table describes the stored procedures that you can use to work with upload packages.</span></span>  
  
|<span data-ttu-id="ec574-221">Nome do procedimento</span><span class="sxs-lookup"><span data-stu-id="ec574-221">Procedure name</span></span>|<span data-ttu-id="ec574-222">Descrição</span><span class="sxs-lookup"><span data-stu-id="ec574-222">Description</span></span>|  
|--------------------|-----------------|  
|[<span data-ttu-id="ec574-223">sp_syscollector_set_cache_window &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-223">sp_syscollector_set_cache_window &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-set-cache-window-transact-sql)|<span data-ttu-id="ec574-224">Configurar o número de repetições do carregamento de dados.</span><span class="sxs-lookup"><span data-stu-id="ec574-224">Configure the number of data upload retries.</span></span>|  
|[<span data-ttu-id="ec574-225">sp_syscollector_set_cache_directory &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-225">sp_syscollector_set_cache_directory &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-set-cache-directory-transact-sql)|<span data-ttu-id="ec574-226">Especificar o armazenamento temporário entre as repetições de carregamento.</span><span class="sxs-lookup"><span data-stu-id="ec574-226">Specify temporary storage for data between upload retries.</span></span>|  
  
 <span data-ttu-id="ec574-227">**Trabalhando com o log de execução de coleta de dados**</span><span class="sxs-lookup"><span data-stu-id="ec574-227">**Working with the data collection execution log**</span></span>  
  
 <span data-ttu-id="ec574-228">A tabela a seguir descreve os procedimentos armazenados que podem ser usados para funcionar com o log de execução de coleta de dados.</span><span class="sxs-lookup"><span data-stu-id="ec574-228">The following table describes the stored procedures that you can use to work with the data collection execution log.</span></span>  
  
|<span data-ttu-id="ec574-229">Nome do procedimento</span><span class="sxs-lookup"><span data-stu-id="ec574-229">Procedure name</span></span>|<span data-ttu-id="ec574-230">Descrição</span><span class="sxs-lookup"><span data-stu-id="ec574-230">Description</span></span>|  
|--------------------|-----------------|  
|[<span data-ttu-id="ec574-231">sp_syscollector_delete_execution_log_tree &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-231">sp_syscollector_delete_execution_log_tree &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-syscollector-delete-execution-log-tree-transact-sql)|<span data-ttu-id="ec574-232">Excluir entradas do conjunto de coleta do log de execução.</span><span class="sxs-lookup"><span data-stu-id="ec574-232">Delete collection set entries from the execution log.</span></span>|  
  
### <a name="functions"></a><span data-ttu-id="ec574-233">Funções</span><span class="sxs-lookup"><span data-stu-id="ec574-233">Functions</span></span>  
 <span data-ttu-id="ec574-234">A tabela a seguir descreve as funções que podem ser usadas para obter informações de execução e rastreamento.</span><span class="sxs-lookup"><span data-stu-id="ec574-234">The following table describes the functions that you can use to obtain execution and trace information.</span></span>  
  
|<span data-ttu-id="ec574-235">Nome da função</span><span class="sxs-lookup"><span data-stu-id="ec574-235">Function name</span></span>|<span data-ttu-id="ec574-236">Descrição</span><span class="sxs-lookup"><span data-stu-id="ec574-236">Description</span></span>|  
|-------------------|-----------------|  
|[<span data-ttu-id="ec574-237">fn_syscollector_get_execution_details &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-237">fn_syscollector_get_execution_details &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/fn-syscollector-get-execution-details-transact-sql)|<span data-ttu-id="ec574-238">Obter os dados de log de execução do [!INCLUDE[ssIS](../../includes/ssis-md.md)] para um pacote específico.</span><span class="sxs-lookup"><span data-stu-id="ec574-238">Get [!INCLUDE[ssIS](../../includes/ssis-md.md)] execution log data for a specific package.</span></span>|  
|[<span data-ttu-id="ec574-239">fn_syscollector_get_execution_stats &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-239">fn_syscollector_get_execution_stats &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/fn-syscollector-get-execution-stats-transact-sql)|<span data-ttu-id="ec574-240">Obter estatísticas de execução para um pacote ou conjunto de coleta.</span><span class="sxs-lookup"><span data-stu-id="ec574-240">Get execution statistics for a collection set or package.</span></span> <span data-ttu-id="ec574-241">Estas informações incluem erros que estão registrados.</span><span class="sxs-lookup"><span data-stu-id="ec574-241">This information includes errors that are logged.</span></span>|  
|[<span data-ttu-id="ec574-242">snapshots.fn_trace_getdata &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec574-242">snapshots.fn_trace_getdata &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/snapshots-fn-trace-getdata-transact-sql)|<span data-ttu-id="ec574-243">Obter os eventos que são registrados quando o tipo de coletor de Rastreamento do SQL Genérico é usado para coletar dados.</span><span class="sxs-lookup"><span data-stu-id="ec574-243">Get the events that are logged when the Generic SQL Trace collector type is used to collect data.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ec574-244">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ec574-244">See Also</span></span>  
 <span data-ttu-id="ec574-245">[Executar um procedimento armazenado](../stored-procedures/execute-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="ec574-245">[Execute a Stored Procedure](../stored-procedures/execute-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="ec574-246">[Usar SQL Server Management Studio](../../database-engine/use-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="ec574-246">[Use SQL Server Management Studio](../../database-engine/use-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="ec574-247">Coleta de Dados</span><span class="sxs-lookup"><span data-stu-id="ec574-247">Data Collection</span></span>](data-collection.md)  
  
  