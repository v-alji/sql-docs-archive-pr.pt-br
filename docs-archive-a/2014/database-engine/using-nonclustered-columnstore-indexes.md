---
title: Usando índices Columnstore não clusterizados | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
ms.assetid: 4c341fb8-7cb1-4cab-921b-e80b751d6c19
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: c876eb6fdd466349ac369dcff8e292bc0839c669
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680617"
---
# <a name="using-nonclustered-columnstore-indexes"></a><span data-ttu-id="48a9c-102">Usando índices columnstore não clusterizados</span><span class="sxs-lookup"><span data-stu-id="48a9c-102">Using Nonclustered Columnstore Indexes</span></span>
  <span data-ttu-id="48a9c-103">Descreve as tarefas principais para usar um índice columnstore não clusterizado em uma tabela do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="48a9c-103">Describes key tasks for using a nonclustered columnstore index on a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table.</span></span>

 <span data-ttu-id="48a9c-104">Para obter uma visão geral de índices columnstore, consulte [Columnstore Indexes Described](../relational-databases/indexes/columnstore-indexes-described.md).</span><span class="sxs-lookup"><span data-stu-id="48a9c-104">For an overview of columnstore indexes, see [Columnstore Indexes Described](../relational-databases/indexes/columnstore-indexes-described.md).</span></span>

 <span data-ttu-id="48a9c-105">Para obter informações sobre índices columnstore clusterizados, consulte [Using Clustered Columnstore Indexes](../relational-databases/indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="48a9c-105">For information about clustered columnstore indexes, see [Using Clustered Columnstore Indexes](../relational-databases/indexes/indexes.md).</span></span>

## <a name="contents"></a><span data-ttu-id="48a9c-106">Sumário</span><span class="sxs-lookup"><span data-stu-id="48a9c-106">Contents</span></span>

-   [<span data-ttu-id="48a9c-107">Criar um índice columnstore não clusterizado</span><span class="sxs-lookup"><span data-stu-id="48a9c-107">Create a Nonclustered Columnstore Index</span></span>](../../2014/database-engine/using-nonclustered-columnstore-indexes.md#load)

-   [<span data-ttu-id="48a9c-108">Alterar os dados em um índice Columnstore não clusterizado</span><span class="sxs-lookup"><span data-stu-id="48a9c-108">Change the Data in a Nonclustered Columnstore Index</span></span>](../../2014/database-engine/using-nonclustered-columnstore-indexes.md#change)

##  <a name="create-a-nonclustered-columnstore-index"></a><a name="load"></a><span data-ttu-id="48a9c-109">Criar um índice Columnstore não clusterizado</span><span class="sxs-lookup"><span data-stu-id="48a9c-109">Create a Nonclustered Columnstore Index</span></span>
 <span data-ttu-id="48a9c-110">Para carregar dados em um índice columnstore não clusterizado, primeiro carregue os dados em uma tabela de armazenamento tradicional armazenada como um índice de heap ou cluster e, em seguida, use [Create COLUMNSTORE index &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-columnstore-index-transact-sql) para criar um índice columnstore.</span><span class="sxs-lookup"><span data-stu-id="48a9c-110">To load data into a nonclustered columnstore index, first load data into a traditional rowstore table stored as a heap or clustered index, and then use [CREATE COLUMNSTORE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-columnstore-index-transact-sql) to create a columnstore index.</span></span>

 <span data-ttu-id="48a9c-111">![Carregando dados em um índice columnstore](../../2014/database-engine/media/sql-server-pdw-columnstore-loadprocess-nonclustered.gif "Carregando dados em um índice columnstore")</span><span class="sxs-lookup"><span data-stu-id="48a9c-111">![Loading data into a columnstore index](../../2014/database-engine/media/sql-server-pdw-columnstore-loadprocess-nonclustered.gif "Loading data into a columnstore index")</span></span>

##  <a name="change-the-data-in-a-nonclustered-columnstore-index"></a><a name="change"></a><span data-ttu-id="48a9c-112">Alterar os dados em um índice Columnstore não clusterizado</span><span class="sxs-lookup"><span data-stu-id="48a9c-112">Change the Data in a Nonclustered Columnstore Index</span></span>
 <span data-ttu-id="48a9c-113">Quando você cria um índice columnstore não clusterizado em uma tabela, não pode modificar diretamente os dados nessa tabela.</span><span class="sxs-lookup"><span data-stu-id="48a9c-113">Once you create a nonclustered columnstore index on a table, you cannot directly modify the data in that table.</span></span> <span data-ttu-id="48a9c-114">Uma consulta com INSERT, UPDATE, DELETE ou MERGE falhará e retornará uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="48a9c-114">A query with INSERT, UPDATE, DELETE, or MERGE will fail and return an error message.</span></span> <span data-ttu-id="48a9c-115">Para adicionar ou modificar os dados na tabela, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="48a9c-115">To add or modify the data in the table, you can do one of the following:</span></span>

-   <span data-ttu-id="48a9c-116">Desabilite o índice columnstore.</span><span class="sxs-lookup"><span data-stu-id="48a9c-116">Disable the columnstore index.</span></span> <span data-ttu-id="48a9c-117">Depois, você pode atualizar os dados na tabela.</span><span class="sxs-lookup"><span data-stu-id="48a9c-117">You can then update the data in the table.</span></span> <span data-ttu-id="48a9c-118">Se você desabilitar o índice columnstore, poderá recriar o índice columnstore quando concluir a atualização dos dados.</span><span class="sxs-lookup"><span data-stu-id="48a9c-118">If you disable the columnstore index, you can rebuild the columnstore index when you finish updating the data.</span></span> <span data-ttu-id="48a9c-119">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="48a9c-119">For example:</span></span>

    ```
    ALTER INDEX mycolumnstoreindex ON mytable DISABLE;
    -- update mytable --
    ALTER INDEX mycolumnstoreindex on mytable REBUILD
    ```

-   <span data-ttu-id="48a9c-120">Descarte o índice columnstore, atualize a tabela e crie novamente o índice columnstore com CREATE COLUMNSTORE INDEX.</span><span class="sxs-lookup"><span data-stu-id="48a9c-120">Drop the columnstore index, update the table, and then re-create the columnstore index with CREATE COLUMNSTORE INDEX.</span></span> <span data-ttu-id="48a9c-121">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="48a9c-121">For example:</span></span>

    ```
    DROP INDEX mycolumnstoreindex ON mytable
    -- update mytable --
    CREATE NONCLUSTERED COLUMNSTORE INDEX mycolumnstoreindex ON mytable;

    ```

-   <span data-ttu-id="48a9c-122">Carregar dados em uma tabela de preparação sem um índice columnstore.</span><span class="sxs-lookup"><span data-stu-id="48a9c-122">Load data into a staging table that does not have a columnstore index.</span></span> <span data-ttu-id="48a9c-123">Criar um índice columnstore na tabela de preparo.</span><span class="sxs-lookup"><span data-stu-id="48a9c-123">Build a columnstore index on the staging table.</span></span> <span data-ttu-id="48a9c-124">Alternar a tabela de preparo para uma partição vazia da tabela principal.</span><span class="sxs-lookup"><span data-stu-id="48a9c-124">Switch the staging table into an empty partition of the main table.</span></span>

-   <span data-ttu-id="48a9c-125">Alternar uma partição da tabela com o índice columnstore para uma tabela de preparo vazia.</span><span class="sxs-lookup"><span data-stu-id="48a9c-125">Switch a partition from the table with the columnstore index into an empty staging table.</span></span> <span data-ttu-id="48a9c-126">Se houver um índice columnstore na tabela de preparo, desabilite o índice columnstore.</span><span class="sxs-lookup"><span data-stu-id="48a9c-126">If there is a columnstore index on the staging table, disable the columnstore index.</span></span> <span data-ttu-id="48a9c-127">Executar quaisquer atualizações.</span><span class="sxs-lookup"><span data-stu-id="48a9c-127">Perform any updates.</span></span> <span data-ttu-id="48a9c-128">Criar (ou recriar) o índice columnstore.</span><span class="sxs-lookup"><span data-stu-id="48a9c-128">Build (or rebuild) the columnstore index.</span></span> <span data-ttu-id="48a9c-129">Alternar a tabela de preparo para a partição anterior (não vazia) da tabela principal.</span><span class="sxs-lookup"><span data-stu-id="48a9c-129">Switch the staging table back into the (now empty) partition of the main table.</span></span>




