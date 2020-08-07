---
title: Criar um conjunto de coleta personalizado que usa o tipo de coletor de consultas T-SQL genérico (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- T-SQL Query collector type
- collection sets [SQL Server], creating custom
ms.assetid: 6b06db5b-cfdc-4ce0-addd-ec643460605b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ab21ad5fd65556dec639fd5ca6999d23e2de673b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575878"
---
# <a name="create-a-custom-collection-set-that-uses-the-generic-t-sql-query-collector-type-transact-sql"></a><span data-ttu-id="4450c-102">Criar um conjunto de coleta personalizado que usa o tipo de coletor de Consultas T-SQL genérico (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4450c-102">Create a Custom Collection Set That Uses the Generic T-SQL Query Collector Type (Transact-SQL)</span></span>
  <span data-ttu-id="4450c-103">É possível criar um conjunto de coleta personalizado com itens de coleta que usam o tipo de coletor de Consultas T-SQL Genérico, usando os procedimentos armazenados fornecidos com o coletor de dados.</span><span class="sxs-lookup"><span data-stu-id="4450c-103">You can create a custom collection set with collection items that use the Generic T-SQL Query collector type by using the stored procedures that are provided with the data collector.</span></span> <span data-ttu-id="4450c-104">A execução dessa tarefa envolve o uso do Editor de Consultas no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para aplicar os seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="4450c-104">Accomplishing this task involves using Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to carry out the following procedures:</span></span>  
  
-   <span data-ttu-id="4450c-105">Configurar as agendas de carregamento.</span><span class="sxs-lookup"><span data-stu-id="4450c-105">Configure upload schedules.</span></span>  
  
-   <span data-ttu-id="4450c-106">Definir e criar o conjunto de coleta.</span><span class="sxs-lookup"><span data-stu-id="4450c-106">Define and create the collection set.</span></span>  
  
-   <span data-ttu-id="4450c-107">Definir e criar um item de coleta.</span><span class="sxs-lookup"><span data-stu-id="4450c-107">Define and create a collection item.</span></span>  
  
-   <span data-ttu-id="4450c-108">Verificar se o conjunto de coleta e os itens de coleta existem.</span><span class="sxs-lookup"><span data-stu-id="4450c-108">Verify that the collection set and collection items exist.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4450c-109">Antes de criar um conjunto de coleta personalizado, configure os parâmetros da coleta de dados.</span><span class="sxs-lookup"><span data-stu-id="4450c-109">Before you create a custom collection set, you must configure data collection parameters.</span></span> <span data-ttu-id="4450c-110">Para obter mais informações, veja [Configurar parâmetros de coleta de dados &#40;Transact-SQL&#41;](configure-data-collection-parameters-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="4450c-110">For more information, see [Configure Data Collection Parameters &#40;Transact-SQL&#41;](configure-data-collection-parameters-transact-sql.md).</span></span>  
  
### <a name="define-and-create-the-collection-set"></a><span data-ttu-id="4450c-111">Definir e criar o conjunto de coleta</span><span class="sxs-lookup"><span data-stu-id="4450c-111">Define and create the collection set</span></span>  
  
1.  <span data-ttu-id="4450c-112">Defina um novo conjunto de coleta usando o procedimento armazenado sp_syscollector_create_collection_set.</span><span class="sxs-lookup"><span data-stu-id="4450c-112">Define a new collection set using the sp_syscollector_create_collection_set stored procedure.</span></span>  
  
    ```  
    USE msdb;  
    DECLARE @collection_set_id int;  
    DECLARE @collection_set_uid uniqueidentifier;  
    EXEC sp_syscollector_create_collection_set   
        @name=N'DMV Test 1',   
        @collection_mode=0,   
        @description=N'This is a test collection set',   
        @logging_level=1,   
        @days_until_expiration=14,   
        @schedule_name=N'CollectorSchedule_Every_15min',   
        @collection_set_id=@collection_set_id OUTPUT,   
        @collection_set_uid=@collection_set_uid OUTPUT;  
    SELECT @collection_set_id, @collection_set_uid;  
    ```  
  
     <span data-ttu-id="4450c-113">O modo de coleta pode ser definido como 0 (armazenado em cache) ou como 1 (não armazenado em cache).</span><span class="sxs-lookup"><span data-stu-id="4450c-113">The collection mode can be set to either 0 (cached) or to 1 (non-cached).</span></span>  
  
     <span data-ttu-id="4450c-114">O nível de log pode ser definido como 0, 1 ou 2.</span><span class="sxs-lookup"><span data-stu-id="4450c-114">The logging level can be set to 0, 1 or 2.</span></span>  
  
     <span data-ttu-id="4450c-115">As agendas pré-configuradas a seguir são fornecidas com o coletor de dados:</span><span class="sxs-lookup"><span data-stu-id="4450c-115">The following preconfigured schedules are provided with the data collector:</span></span>  
  
    -   <span data-ttu-id="4450c-116">CollectorSchedule_Every_5min</span><span class="sxs-lookup"><span data-stu-id="4450c-116">CollectorSchedule_Every_5min</span></span>  
  
    -   <span data-ttu-id="4450c-117">CollectorSchedule_Every_10min</span><span class="sxs-lookup"><span data-stu-id="4450c-117">CollectorSchedule_Every_10min</span></span>  
  
    -   <span data-ttu-id="4450c-118">CollectorSchedule_Every_15min</span><span class="sxs-lookup"><span data-stu-id="4450c-118">CollectorSchedule_Every_15min</span></span>  
  
    -   <span data-ttu-id="4450c-119">CollectorSchedule_Every_30min</span><span class="sxs-lookup"><span data-stu-id="4450c-119">CollectorSchedule_Every_30min</span></span>  
  
    -   <span data-ttu-id="4450c-120">CollectorSchedule_Every_60min</span><span class="sxs-lookup"><span data-stu-id="4450c-120">CollectorSchedule_Every_60min</span></span>  
  
    -   <span data-ttu-id="4450c-121">CollectorSchedule_Every_6h</span><span class="sxs-lookup"><span data-stu-id="4450c-121">CollectorSchedule_Every_6h</span></span>  
  
     <span data-ttu-id="4450c-122">Se você não desejar usar uma das agendas fornecidas, poderá criar uma nova agenda e usá-la no conjunto de coleta.</span><span class="sxs-lookup"><span data-stu-id="4450c-122">If you do not want to use one of the schedules that are provided, you can create a new schedule and use it for the collection set.</span></span> <span data-ttu-id="4450c-123">Para obter mais informações, veja [Criar e anexar agendamentos a trabalhos](../../ssms/agent/create-and-attach-schedules-to-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="4450c-123">For more information, see [Create and Attach Schedules to Jobs](../../ssms/agent/create-and-attach-schedules-to-jobs.md).</span></span>  
  
### <a name="define-and-create-a-collection-item"></a><span data-ttu-id="4450c-124">Definir e criar um item de coleta</span><span class="sxs-lookup"><span data-stu-id="4450c-124">Define and create a collection item</span></span>  
  
1.  <span data-ttu-id="4450c-125">Como o novo item de coleta é baseado em um tipo de coletor genérico já instalado, você pode executar o código a seguir para definir o GUID que corresponde ao tipo de coletor de Consultas T-SQL Genérico.</span><span class="sxs-lookup"><span data-stu-id="4450c-125">Because the new collection item is based on a generic collector type that is already installed, you can run the following code to set the GUID to correspond to the Generic T-SQL Query collector type.</span></span>  
  
    ```sql  
    DECLARE @collector_type_uid uniqueidentifier;  
    SELECT @collector_type_uid = collector_type_uid FROM [msdb].[dbo].[syscollector_collector_types]   
    WHERE name = N'Generic T-SQL Query Collector Type';  
    DECLARE @collection_item_id int;  
    ```  
  
2.  <span data-ttu-id="4450c-126">Use o procedimento armazenado sp_syscollector_create_collection_item para criar o item de coleta.</span><span class="sxs-lookup"><span data-stu-id="4450c-126">Use the sp_syscollector_create_collection_item stored procedure to create the collection item.</span></span> <span data-ttu-id="4450c-127">Declare o esquema do item de coleta para que ele seja mapeado para o esquema exigido para o tipo de coletor de Consultas T-SQL Genérico.</span><span class="sxs-lookup"><span data-stu-id="4450c-127">Declare the schema for the collection item so it maps to the schema that is required for the Generic T-SQL Query collector type.</span></span>  
  
    ```sql  
    EXEC sp_syscollector_create_collection_item   
        @name=N'Query Stats - Test 1',   
        @parameters=N'  
            <ns:TSQLQueryCollector xmlns:ns="DataCollectorType">  
            <Query>  
            <Value>SELECT * FROM sys.dm_exec_query_stats</Value>  
            <OutputTable>dm_exec_query_stats</OutputTable>  
            </Query>  
            </ns:TSQLQueryCollector>',   
        @collection_item_id=@collection_item_id OUTPUT,   
        @frequency=5,   
        @collection_set_id=@collection_set_id,   
        @collector_type_uid=@collector_type_uid;  
    SELECT @collection_item_id;  
    ```  
  
### <a name="verify-that-the-new-collection-set-and-collection-item-exist"></a><span data-ttu-id="4450c-128">Verificar se o novo conjunto de coleta e o item de coleta existem</span><span class="sxs-lookup"><span data-stu-id="4450c-128">Verify that the new collection set and collection item exist</span></span>  
  
1.  <span data-ttu-id="4450c-129">Antes de iniciar o novo conjunto de coleta, execute a consulta a seguir para verificar se o novo conjunto de coleta e seu item de coleta foram criados.</span><span class="sxs-lookup"><span data-stu-id="4450c-129">Before starting the new collection set, run the following query to verify that the new collection set and its collection item have been created.</span></span>  
  
    ```sql  
    USE msdb;  
    SELECT * FROM syscollector_collection_sets;  
    SELECT * FROM syscollector_collection_items;  
    GO  
    ```  
  
     <span data-ttu-id="4450c-130">Você também pode fazer uma verificação visual no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4450c-130">You can also do a visual check in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="4450c-131">No Pesquisador de Objetos, expanda o nó **Gerenciamento** e expanda **Coleta de Dados**.</span><span class="sxs-lookup"><span data-stu-id="4450c-131">In Object Explorer, expand the **Management** node, and then expand **Data Collection**.</span></span> <span data-ttu-id="4450c-132">O novo conjunto de coleta será exibido.</span><span class="sxs-lookup"><span data-stu-id="4450c-132">The new collection set will be displayed.</span></span> <span data-ttu-id="4450c-133">O ícone de círculo vermelho do conjunto de coleta indica que o conjunto de coleta está parado.</span><span class="sxs-lookup"><span data-stu-id="4450c-133">The red circle icon for the collection set indicates that the collection set is stopped.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4450c-134">Exemplo</span><span class="sxs-lookup"><span data-stu-id="4450c-134">Example</span></span>  
 <span data-ttu-id="4450c-135">O exemplo de código a seguir combina os exemplos documentados nas etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="4450c-135">The following code sample combines the examples that are documented in the previous steps.</span></span> <span data-ttu-id="4450c-136">Observe que a frequência da coleta definida para o item de coleta (5 segundos) é ignorada porque o modo de coleta do conjunto de coleta está definido como 0, que é um modo de armazenamento em cache.</span><span class="sxs-lookup"><span data-stu-id="4450c-136">Note that the collection frequency that is set for the collection item (5 seconds) is ignored because the collection set collection mode is set to 0, which is cached mode.</span></span> <span data-ttu-id="4450c-137">Para obter mais informações, consulte [Data Collection](data-collection.md).</span><span class="sxs-lookup"><span data-stu-id="4450c-137">For more information, see [Data Collection](data-collection.md).</span></span>  
  
```sql  
USE msdb;  
  
DECLARE @collection_set_id int;  
DECLARE @collection_set_uid uniqueidentifier  
  
EXEC dbo.sp_syscollector_create_collection_set  
    @name = N'DMV Stats Test 1',  
    @collection_mode = 0,  
    @description = N'This is a test collection set',  
    @logging_level=1,  
    @days_until_expiration = 14,  
    @schedule_name=N'CollectorSchedule_Every_15min',  
    @collection_set_id = @collection_set_id OUTPUT,  
    @collection_set_uid = @collection_set_uid OUTPUT;  
SELECT @collection_set_id,@collection_set_uid;  
  
DECLARE @collector_type_uid uniqueidentifier;  
SELECT @collector_type_uid = collector_type_uid FROM syscollector_collector_types   
WHERE name = N'Generic T-SQL Query Collector Type';  
  
DECLARE @collection_item_id int;  
EXEC sp_syscollector_create_collection_item  
@name= N'Query Stats - Test 1',  
@parameters=N'  
<ns:TSQLQueryCollector xmlns:ns="DataCollectorType">  
<Query>  
  <Value>select * from sys.dm_exec_query_stats</Value>  
  <OutputTable>dm_exec_query_stats</OutputTable>  
</Query>  
 </ns:TSQLQueryCollector>',  
    @collection_item_id = @collection_item_id OUTPUT,  
    @frequency = 5, -- This parameter is ignored in cached mode  
    @collection_set_id = @collection_set_id,  
    @collector_type_uid = @collector_type_uid;  
SELECT @collection_item_id;  
  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="4450c-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4450c-138">See Also</span></span>  
 <span data-ttu-id="4450c-139">[Procedimentos armazenados de coletor de dados &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4450c-139">[Data Collector Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql) </span></span>  
 <span data-ttu-id="4450c-140">[Gerenciar Agendas](../../ssms/agent/manage-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="4450c-140">[Manage Schedules](../../ssms/agent/manage-schedules.md) </span></span>  
 [<span data-ttu-id="4450c-141">Iniciar ou parar um conjunto de coleta</span><span class="sxs-lookup"><span data-stu-id="4450c-141">Start or Stop a Collection Set</span></span>](start-or-stop-a-collection-set.md)  
  
  
