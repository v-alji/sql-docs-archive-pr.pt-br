---
title: Pré-requisitos para registro em log mínimo em importação em massa | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- minimal logging [SQL Server]
- logged bulk copy [SQL Server]
- logs [SQL Server], minimal logging
- minimally logged operations [SQL Server]
- bulk importing [SQL Server], minimal logging
ms.assetid: bd1dac6b-6ef8-4735-ad4e-67bb42dc4f66
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4711e25dcfcc99e14894e47166638673c61a6831
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685168"
---
# <a name="prerequisites-for-minimal-logging-in-bulk-import"></a><span data-ttu-id="f606b-102">Prerequisites for Minimal Logging in Bulk Import</span><span class="sxs-lookup"><span data-stu-id="f606b-102">Prerequisites for Minimal Logging in Bulk Import</span></span>
  <span data-ttu-id="f606b-103">Para um banco de dados no modelo de recuperação completa, todas as operações de inserção de linha executadas pela importação em massa são registradas completamente no log de transações.</span><span class="sxs-lookup"><span data-stu-id="f606b-103">For a database under the full recovery model, all row-insert operations that are performed by bulk import are fully logged in the transaction log.</span></span> <span data-ttu-id="f606b-104">Importações de grandes volumes de dados poderão fazer o log de transações ficar cheio rapidamente se o modelo de recuperação completa for usado.</span><span class="sxs-lookup"><span data-stu-id="f606b-104">Large data imports can cause the transaction log to fill rapidly if the full recovery model is used.</span></span> <span data-ttu-id="f606b-105">Por outro lado, no modelo de recuperação simples ou no modelo de recuperação bulk-logged, o log mínimo de operações de importação em massa reduz a possibilidade de uma operação de importação em massa preencher o espaço do log.</span><span class="sxs-lookup"><span data-stu-id="f606b-105">In contrast, under the simple recovery model or bulk-logged recovery model, minimal logging of bulk-import operations reduces the possibility that a bulk-import operation will fill the log space.</span></span> <span data-ttu-id="f606b-106">O log mínimo também é mais eficiente que o log completo.</span><span class="sxs-lookup"><span data-stu-id="f606b-106">Minimal logging is also more efficient than full logging.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f606b-107">O modelo de recuperação bulk-logged foi projetado para substituir temporariamente o modelo de recuperação completa durante operações em massa de grande porte.</span><span class="sxs-lookup"><span data-stu-id="f606b-107">The bulk-logged recovery model is designed to temporarily replace the full recovery model during large bulk operations.</span></span>  
  
## <a name="table-requirements-for-minimally-logging-bulk-import-operations"></a><span data-ttu-id="f606b-108">Requisitos de tabela para operações de importação em massa com log mínimo</span><span class="sxs-lookup"><span data-stu-id="f606b-108">Table Requirements for Minimally Logging Bulk-Import Operations</span></span>  
 <span data-ttu-id="f606b-109">O log mínimo requer que a tabela de destino atenda às seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="f606b-109">Minimal logging requires that the target table meets the following conditions:</span></span>  
  
-   <span data-ttu-id="f606b-110">A tabela não está sendo reproduzida.</span><span class="sxs-lookup"><span data-stu-id="f606b-110">The table is not being replicated.</span></span>  
  
-   <span data-ttu-id="f606b-111">O bloqueio da tabela é especificado (usando TABLOCK).</span><span class="sxs-lookup"><span data-stu-id="f606b-111">Table locking is specified (using TABLOCK).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f606b-112">Embora as inserções de dados não sejam registradas no log de transações durante uma operação da importação com log em massa, o [!INCLUDE[ssDE](../../includes/ssde-md.md)] ainda faz o log de alocações de extensão cada vez que uma nova extensão é alocada à tabela.</span><span class="sxs-lookup"><span data-stu-id="f606b-112">Although data insertions are not logged in the transaction log during a minimally logged bulk-import operation, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] still logs extent allocations each time a new extent is allocated to the table.</span></span>  
  
-   <span data-ttu-id="f606b-113">A tabela não é do tipo com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="f606b-113">Table is not a memory-optimized table.</span></span>  
  
 <span data-ttu-id="f606b-114">A possibilidade de ocorrência de log mínimo em uma tabela também poderá depender se a tabela estiver indexada e, nesse caso, se a tabela estiver vazia:</span><span class="sxs-lookup"><span data-stu-id="f606b-114">Whether minimal logging can occur for a table also depends on whether the table is indexed and, if so, whether the table is empty:</span></span>  
  
-   <span data-ttu-id="f606b-115">Se a tabela não tiver nenhum índice, as páginas de dados terão log mínimo.</span><span class="sxs-lookup"><span data-stu-id="f606b-115">If the table has no indexes, data pages are minimally logged.</span></span>  
  
-   <span data-ttu-id="f606b-116">Se a tabela não tiver nenhum índice clusterizado, mas tiver um ou mais índices não clusterizados, as páginas de dados sempre terão log mínimo.</span><span class="sxs-lookup"><span data-stu-id="f606b-116">If the table has no clustered index but has one or more nonclustered indexes, data pages are always minimally logged.</span></span> <span data-ttu-id="f606b-117">No entanto, a forma como as páginas de índice são registradas depende da tabela:</span><span class="sxs-lookup"><span data-stu-id="f606b-117">How index pages are logged, however, depends on whether the table is empty:</span></span>  
  
    -   <span data-ttu-id="f606b-118">Se a tabela estiver vazia, a páginas de índice terão log mínimo.</span><span class="sxs-lookup"><span data-stu-id="f606b-118">If the table is empty, index pages are minimally logged.</span></span>  
  
    -   <span data-ttu-id="f606b-119">Se a tabela não estiver vazia, as páginas de índice terão log completo.</span><span class="sxs-lookup"><span data-stu-id="f606b-119">If table is non-empty, index pages are fully logged.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="f606b-120">Se você iniciar com uma tabela vazia e importar os dados em massa em vários lotes, para o primeiro lote as páginas de índice e as páginas de dados terão log mínimo, mas começando com o segundo lote, só as páginas de dados terão log mínimo.</span><span class="sxs-lookup"><span data-stu-id="f606b-120">If you start with an empty table and bulk import the data in multiple batches, both index and data pages are minimally logged for the first batch, but beginning with the second batch, only data pages are minimally logged.</span></span>  
  
-   <span data-ttu-id="f606b-121">Se a tabela tiver um índice clusterizado e estiver vazia, ambas as páginas de dados e de índice terão log mínimo.</span><span class="sxs-lookup"><span data-stu-id="f606b-121">If the table has a clustered index and is empty, both data and index pages are minimally logged.</span></span> <span data-ttu-id="f606b-122">Por outro lado, se uma tabela tiver um índice clusterizado e não estiver vazia, as páginas de dados e as páginas de índice terão log completo seja qual for o modelo de recuperação.</span><span class="sxs-lookup"><span data-stu-id="f606b-122">In contrast, if a table has a clustered index and is non-empty, data pages and index pages are both fully logged regardless of the recovery model.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f606b-123">Se você iniciar com uma tabela vazia e importar os dados em massa em vários lotes, as páginas de índice e as páginas de dados terão log mínimo para o primeiro lote, mas a partir do segundo lote, apenas as páginas de dados terão bulk-logged.</span><span class="sxs-lookup"><span data-stu-id="f606b-123">If you start with an empty table and bulk import the data in batches, both index and data pages are minimally logged for the first batch, but from the second batch onwards, only data pages are bulk logged.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f606b-124">Quando a replicação transacional está habilitada, as operações BULK INSERT são completamente registradas mesmo no modelo de recuperação bulk-logged.</span><span class="sxs-lookup"><span data-stu-id="f606b-124">When transactional replication is enabled, BULK INSERT operations are fully logged even under the Bulk Logged recovery model.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="f606b-125">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="f606b-125">Related Tasks</span></span>  
  
-   [<span data-ttu-id="f606b-126">Exibir ou alterar o modelo de recuperação de um banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f606b-126">View or Change the Recovery Model of a Database &#40;SQL Server&#41;</span></span>](../backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="f606b-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f606b-127">See Also</span></span>  
 <span data-ttu-id="f606b-128">[Modelos de recuperação &#40;SQL Server&#41;](../backup-restore/recovery-models-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f606b-128">[Recovery Models &#40;SQL Server&#41;](../backup-restore/recovery-models-sql-server.md) </span></span>  
 <span data-ttu-id="f606b-129">[Utilitário bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="f606b-129">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="f606b-130">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f606b-130">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="f606b-131">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f606b-131">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="f606b-132">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f606b-132">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="f606b-133">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f606b-133">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="f606b-134">[Dicas de tabela &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table) </span><span class="sxs-lookup"><span data-stu-id="f606b-134">[Table Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table) </span></span>  
 [<span data-ttu-id="f606b-135">INSERT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f606b-135">INSERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/insert-transact-sql)  
  
  
