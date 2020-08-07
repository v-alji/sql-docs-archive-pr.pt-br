---
title: Adicionar um item da coleção a um conjunto de coleções (Transact-SQL)   Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- collection items [SQL Server]
- collection sets [SQL Server], adding items
ms.assetid: 9fe6454e-8c0e-4b50-937b-d9871b20fd13
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0b21508761bdfbaf8918242b074f78203c1bcaed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583632"
---
# <a name="add-a-collection-item-to-a-collection-set-transact-sql"></a><span data-ttu-id="f2686-102">Adicionar um item de coleta a um conjunto de coletas (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f2686-102">Add a Collection Item to a Collection Set (Transact-SQL)</span></span>
  <span data-ttu-id="f2686-103">Você pode adicionar um item de coleta a um conjunto de coleta existente usando os procedimentos armazenados fornecidos com o coletor de dados.</span><span class="sxs-lookup"><span data-stu-id="f2686-103">You can add a collection item to an existing collection set using the stored procedures that are provided with the data collector.</span></span>  
  
 <span data-ttu-id="f2686-104">Complete os seguintes passos usando o Editor de Consultas no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2686-104">Carry out the following steps using Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
### <a name="add-a-collection-item-to-a-collection-set"></a><span data-ttu-id="f2686-105">Adicione um item de coleta a um conjunto de coleta</span><span class="sxs-lookup"><span data-stu-id="f2686-105">Add a collection item to a collection set</span></span>  
  
1.  <span data-ttu-id="f2686-106">Interrompa o conjunto de coleta ao qual você deseja adicionar o item executando o procedimento armazenado **sp_syscollector_stop_collection_set** .</span><span class="sxs-lookup"><span data-stu-id="f2686-106">Stop the collection set that you want to add the item to by running the **sp_syscollector_stop_collection_set** stored procedure.</span></span> <span data-ttu-id="f2686-107">Por exemplo, para parar um conjunto de coleta denominado "Conjunto de Coleta de Teste", execute as seguintes instruções:</span><span class="sxs-lookup"><span data-stu-id="f2686-107">For example, to stop a collection set that is named "Test Collection Set", run the following statements:</span></span>  
  
    ```sql  
    USE msdb  
    DECLARE @csid int  
    SELECT @csid = collection_set_id  
    FROM syscollector_collection_sets  
    WHERE name = 'Test Collection Set'  
    SELECT @csid  
    EXEC dbo.sp_syscollector_stop_collection_set @collection_set_id = @csid  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="f2686-108">Você também pode parar o conjunto de coleta usando o Pesquisador de Objetos no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2686-108">You can also stop the collection set by using Object Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="f2686-109">Para obter mais informações, veja [Iniciar ou interromper um conjunto de coleta](start-or-stop-a-collection-set.md).</span><span class="sxs-lookup"><span data-stu-id="f2686-109">For more information, see [Start or Stop a Collection Set](start-or-stop-a-collection-set.md).</span></span>  
  
2.  <span data-ttu-id="f2686-110">Declare o conjunto de coleta ao qual você deseja adicionar o item de coleta.</span><span class="sxs-lookup"><span data-stu-id="f2686-110">Declare the collection set that you want to add the collection item to.</span></span> <span data-ttu-id="f2686-111">O código a seguir fornece um exemplo de como declarar a ID do conjunto de coleta.</span><span class="sxs-lookup"><span data-stu-id="f2686-111">The following code provides an example of how to declare the collection set ID.</span></span>  
  
    ```sql  
    DECLARE @collection_set_id_1 int  
    SELECT @collection_set_id_1 = collection_set_id FROM [msdb].[dbo].[syscollector_collection_sets]  
    WHERE name = N'Test Collection Set'; -- name of collection set  
    ```  
  
3.  <span data-ttu-id="f2686-112">Declare o tipo de coletor.</span><span class="sxs-lookup"><span data-stu-id="f2686-112">Declare the collector type.</span></span> <span data-ttu-id="f2686-113">O código a seguir fornece um exemplo de como declarar o tipo de coletor de Consultas T-SQL Genérico.</span><span class="sxs-lookup"><span data-stu-id="f2686-113">The following code provides an example of how to declare the Generic T-SQL Query collector type.</span></span>  
  
    ```sql  
    DECLARE @collector_type_uid_1 uniqueidentifier  
    SELECT @collector_type_uid_1 = collector_type_uid FROM [msdb].[dbo].[syscollector_collector_types]   
       WHERE name = N'Generic T-SQL Query Collector Type';  
    ```  
  
     <span data-ttu-id="f2686-114">Execute o código a seguir para obter uma lista dos tipos de coletores instalados:</span><span class="sxs-lookup"><span data-stu-id="f2686-114">You can run the following code to obtain a list of the installed collector types:</span></span>  
  
    ```sql  
    USE msdb  
    SELECT * from syscollector_collector_types  
    GO  
    ```  
  
4.  <span data-ttu-id="f2686-115">Execute o procedimento armazenado **sp_syscollector_create_collection_item** para criar o item de coleta.</span><span class="sxs-lookup"><span data-stu-id="f2686-115">Run the **sp_syscollector_create_collection_item** stored procedure to create the collection item.</span></span> <span data-ttu-id="f2686-116">Você deve declarar o esquema do item de coleta para que ele seja mapeado para o esquema necessário para o tipo de coletor desejado.</span><span class="sxs-lookup"><span data-stu-id="f2686-116">You must declare the schema for the collection item so that it maps to the required schema for the desired collector type.</span></span> <span data-ttu-id="f2686-117">O exemplo a seguir usa o esquema de entrada de Consultas T-SQL Genérico.</span><span class="sxs-lookup"><span data-stu-id="f2686-117">The following example uses the Generic T-SQL Query input schema.</span></span>  
  
    ```sql  
    DECLARE @collection_item_id int;  
    EXEC [msdb].[dbo].[sp_syscollector_create_collection_item]   
    @name=N'OS Wait Stats', --name of collection item  
    @parameters=N'  
    <ns:TSQLQueryCollector xmlns:ns="DataCollectorType">  
     <Query>  
      <Value>select * from sys.dm_os_wait_stats</Value>  
      <OutputTable>os_wait_stats</OutputTable>  
    </Query>  
    </ns:TSQLQueryCollector>',  
    @collection_item_id = @collection_item_id OUTPUT,  
    @frequency = 60,  
    @collection_set_id = @collection_set_id_1, --- Provides the collection set ID number  
    @collector_type_uid = @collector_type_uid_1 -- Provides the collector type UID  
    SELECT @collection_item_id     
    ```  
  
5.  <span data-ttu-id="f2686-118">Antes de iniciar o conjunto de coleta atualizado, execute a consulta a seguir para verificar se o novo item de coleta foi criado:</span><span class="sxs-lookup"><span data-stu-id="f2686-118">Before starting the updated collection set, run the following query to verify that the new collection item has been created:</span></span>  
  
    ```xaml  
    USE msdb  
    SELECT * from syscollector_collection_sets  
    SELECT * from syscollector_collection_items  
    GO  
    ```  
  
     <span data-ttu-id="f2686-119">Os conjuntos de coleta e seus itens de coleta são exibidos na guia **Resultados** .</span><span class="sxs-lookup"><span data-stu-id="f2686-119">The collection sets and their collection items are displayed in the **Results** tab.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2686-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f2686-120">See Also</span></span>  
 <span data-ttu-id="f2686-121">[Criar um conjunto de coleta personalizado que usa o tipo de coletor de Consultas T-SQL genérico &#40;Transact-SQL&#41;](create-custom-collection-set-generic-t-sql-query-collector-type.md) </span><span class="sxs-lookup"><span data-stu-id="f2686-121">[Create a Custom Collection Set That Uses the Generic T-SQL Query Collector Type &#40;Transact-SQL&#41;](create-custom-collection-set-generic-t-sql-query-collector-type.md) </span></span>  
 [<span data-ttu-id="f2686-122">Procedimentos armazenados de coletor de dados &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f2686-122">Data Collector Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql)  
  
  
