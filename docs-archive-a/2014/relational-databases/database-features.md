---
title: Recursos de banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 04518abb-8581-47c8-a601-ee9136c3c0eb
author: rothja
ms.author: jroth
ms.openlocfilehash: 56b9f9ba9cc6e11ea82b822ae10b31710c8617b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575165"
---
# <a name="database-features"></a><span data-ttu-id="fdeba-102">Recursos de banco de dados</span><span class="sxs-lookup"><span data-stu-id="fdeba-102">Database Features</span></span>
  <span data-ttu-id="fdeba-103">Esta seção contém os recursos e as tarefas associadas a bancos de dados, objetos de banco de dados, tipos de dados e os mecanismos usados para trabalhar com dados ou gerenciá-los.</span><span class="sxs-lookup"><span data-stu-id="fdeba-103">This section contains the features and tasks associated with databases, database objects, data types, and the mechanisms used to work with or manage data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fdeba-104">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="fdeba-104">In This Section</span></span>  
  
|||
|--|--|
|[<span data-ttu-id="fdeba-105">Bancos de dados</span><span class="sxs-lookup"><span data-stu-id="fdeba-105">Databases</span></span>](databases/databases.md)|[<span data-ttu-id="fdeba-106">Fazer backup e restaurar bancos de dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="fdeba-106">Back Up and Restore of SQL Server Databases</span></span>](backup-restore/back-up-and-restore-of-sql-server-databases.md)|  
|[<span data-ttu-id="fdeba-107">Tabelas</span><span class="sxs-lookup"><span data-stu-id="fdeba-107">Tables</span></span>](tables/tables.md)|[<span data-ttu-id="fdeba-108">Números de sequência</span><span class="sxs-lookup"><span data-stu-id="fdeba-108">Sequence Numbers</span></span>](sequence-numbers/sequence-numbers.md)|[<span data-ttu-id="fdeba-109">Importação e exportação em massa de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fdeba-109">Bulk Import and Export of Data &#40;SQL Server&#41;</span></span>](import-export/bulk-import-and-export-of-data-sql-server.md)|  
|[<span data-ttu-id="fdeba-110">OLTP in-memory &#40;Otimização na memória&#41;</span><span class="sxs-lookup"><span data-stu-id="fdeba-110">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](in-memory-oltp/in-memory-oltp-in-memory-optimization.md)|[<span data-ttu-id="fdeba-111">Gatilhos DDL</span><span class="sxs-lookup"><span data-stu-id="fdeba-111">DDL Triggers</span></span>](triggers/ddl-triggers.md)|[<span data-ttu-id="fdeba-112">Data Compression</span><span class="sxs-lookup"><span data-stu-id="fdeba-112">Data Compression</span></span>](data-compression/data-compression.md)|  
|[<span data-ttu-id="fdeba-113">Índices</span><span class="sxs-lookup"><span data-stu-id="fdeba-113">Indexes</span></span>](indexes/indexes.md)|[<span data-ttu-id="fdeba-114">Gatilhos DML</span><span class="sxs-lookup"><span data-stu-id="fdeba-114">DML Triggers</span></span>](triggers/dml-triggers.md)|[<span data-ttu-id="fdeba-115">Objetos Automation no Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fdeba-115">OLE Automation Objects in Transact-SQL</span></span>](stored-procedures/ole-automation-objects-in-transact-sql.md)|  
|[<span data-ttu-id="fdeba-116">Tabelas e índices particionados</span><span class="sxs-lookup"><span data-stu-id="fdeba-116">Partitioned Tables and Indexes</span></span>](partitions/partitioned-tables-and-indexes.md)|[<span data-ttu-id="fdeba-117">Sinônimos &#40;Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="fdeba-117">Synonyms &#40;Database Engine&#41;</span></span>](synonyms/synonyms-database-engine.md)|[<span data-ttu-id="fdeba-118">Notificações de eventos</span><span class="sxs-lookup"><span data-stu-id="fdeba-118">Event Notifications</span></span>](service-broker/event-notifications.md)|  
|[<span data-ttu-id="fdeba-119">Exibições</span><span class="sxs-lookup"><span data-stu-id="fdeba-119">Views</span></span>](views/views.md)|[<span data-ttu-id="fdeba-120">Dados XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fdeba-120">XML Data &#40;SQL Server&#41;</span></span>](xml/xml-data-sql-server.md)|[<span data-ttu-id="fdeba-121">Monitorar e ajustar o desempenho</span><span class="sxs-lookup"><span data-stu-id="fdeba-121">Monitor and Tune for Performance</span></span>](performance/monitor-and-tune-for-performance.md)|  
|[<span data-ttu-id="fdeba-122">Procedimentos armazenados &#40;Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="fdeba-122">Stored Procedures &#40;Database Engine&#41;</span></span>](stored-procedures/stored-procedures-database-engine.md)|[<span data-ttu-id="fdeba-123">Dados espaciais &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fdeba-123">Spatial Data &#40;SQL Server&#41;</span></span>](spatial/spatial-data-sql-server.md)||  
|[<span data-ttu-id="fdeba-124">Pesquisar &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fdeba-124">Search &#40;SQL Server&#41;</span></span>](../database-engine/search-sql-server.md)|[<span data-ttu-id="fdeba-125">Objeto binário grande &#40;Blob&#41; Dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fdeba-125">Binary Large Object &#40;Blob&#41; Data &#40;SQL Server&#41;</span></span>](blob/binary-large-object-blob-data-sql-server.md)||  
|[<span data-ttu-id="fdeba-126">Funções definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="fdeba-126">User-Defined Functions</span></span>](user-defined-functions/user-defined-functions.md)|[<span data-ttu-id="fdeba-127">Aplicativos da camada de dados</span><span class="sxs-lookup"><span data-stu-id="fdeba-127">Data-tier Applications</span></span>](data-tier-applications/data-tier-applications.md)||  
|[<span data-ttu-id="fdeba-128">Estatísticas</span><span class="sxs-lookup"><span data-stu-id="fdeba-128">Statistics</span></span>](statistics/statistics.md)|[<span data-ttu-id="fdeba-129">O log de transações &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fdeba-129">The Transaction Log &#40;SQL Server&#41;</span></span>](logs/the-transaction-log-sql-server.md)||  
|[<span data-ttu-id="fdeba-130">Guias de plano</span><span class="sxs-lookup"><span data-stu-id="fdeba-130">Plan Guides</span></span>](performance/plan-guides.md)|[<span data-ttu-id="fdeba-131">Pontos de verificação de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fdeba-131">Database Checkpoints &#40;SQL Server&#41;</span></span>](logs/database-checkpoints-sql-server.md)||  
  
  
