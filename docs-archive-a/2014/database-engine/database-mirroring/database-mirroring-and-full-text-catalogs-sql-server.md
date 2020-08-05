---
title: Espelhamento de banco de dados e catálogos de texto completo (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], interoperability
- full-text catalogs [SQL Server], database mirroring
- catalogs [SQL Server], database mirroring
ms.assetid: e34072ae-fe8a-462d-bb03-02fa0987f793
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 39929f4bed6edbd1e8ec5c1b72dbe8f7aefeec68
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571575"
---
# <a name="database-mirroring-and-full-text-catalogs-sql-server"></a><span data-ttu-id="24251-102">Espelhamento de banco de dados e catálogos de texto completo (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="24251-102">Database Mirroring and Full-Text Catalogs (SQL Server)</span></span>
  <span data-ttu-id="24251-103">Para espelhar um banco de dados que possui um catálogo de texto completo, use o backup como sempre para criar um backup de banco de dados completo do banco de dados principal e então restaure o backup para copiar o banco de dados no servidor espelho.</span><span class="sxs-lookup"><span data-stu-id="24251-103">To mirror a database that has a full-text catalog, use backup as usual to create a full database backup of the principal database, and then restore the backup to copy the database to the mirror server.</span></span> <span data-ttu-id="24251-104">Para obter mais informações, veja [Preparar um banco de dados espelho para espelhamento &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="24251-104">For more information, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
## <a name="full-text-catalog-and-indexes-before-failover"></a><span data-ttu-id="24251-105">Catálogo de texto completo e índices antes do failover</span><span class="sxs-lookup"><span data-stu-id="24251-105">Full-Text Catalog and Indexes Before Failover</span></span>  
 <span data-ttu-id="24251-106">Em um banco de dados espelho criado recentemente, o catálogo de texto completo é o mesmo de quando foi feito o backup do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="24251-106">In a newly created mirror database, the full-text catalog is the same as when the database was backed up.</span></span> <span data-ttu-id="24251-107">Depois do início do espelhamento de banco de dados, qualquer alteração no nível de catálogo feira por instruções DDL (CREATE FULLTEXT CATALOG, ALTER FULLTEXT CATALOG, DROP FULLTEXT CATALOG) é registrada e enviada ao servidor espelho para ser reproduzida no banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="24251-107">After database mirroring starts, any catalog-level changes that were made by DDL statements (CREATE FULLTEXT CATALOG, ALTER FULLTEXT CATALOG, DROP FULLTEXT CATALOG) are logged and sent to the mirror server to be replayed on the mirror database.</span></span> <span data-ttu-id="24251-108">Porém, não são reproduzidas as alterações no nível de índice no banco de dados espelho, pois ele não está registrado no servidor principal.</span><span class="sxs-lookup"><span data-stu-id="24251-108">However, index-level changes are not reproduced on the mirror database because it is not logged on to the principal server.</span></span> <span data-ttu-id="24251-109">Portanto, à medida que o conteúdo do catálogo de texto completo muda no banco de dados principal, o conteúdo do catálogo de texto completo no banco de dados espelho não é sincronizado.</span><span class="sxs-lookup"><span data-stu-id="24251-109">Therefore, as the contents of the full-text catalog change on the principal database, the contents of the full-text catalog on the mirror database are unsynchronized.</span></span>  
  
## <a name="full-text-indexes-after-failover"></a><span data-ttu-id="24251-110">Índices de texto completo após o failover</span><span class="sxs-lookup"><span data-stu-id="24251-110">Full-Text Indexes After Failover</span></span>  
 <span data-ttu-id="24251-111">Após um failover, o rastreamento completo de um índice de texto completo no novo servidor principal pode ser necessário ou útil nas situações seguintes:</span><span class="sxs-lookup"><span data-stu-id="24251-111">After a failover, a full crawl of a full-text index on the new principal server might be required or useful in the following situations:</span></span>  
  
-   <span data-ttu-id="24251-112">Se o rastreamento de alterações estiver OFF em um índice de texto completo, você deve iniciar um rastreamento completo nesse índice usando a seguinte instrução:</span><span class="sxs-lookup"><span data-stu-id="24251-112">If change-tracking is turned OFF on a full text index, you must start a full crawl on that index by using the following statement:</span></span>  
  
     <span data-ttu-id="24251-113">ALTER FULLTEXT INDEX ON *table_name* START FULL POPULATION</span><span class="sxs-lookup"><span data-stu-id="24251-113">ALTER FULLTEXT INDEX ON *table_name* START FULL POPULATION</span></span>  
  
-   <span data-ttu-id="24251-114">Se estiver configurado para rastreamento de alterações automático, o índice de texto completo será sincronizado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="24251-114">If a full-text index is configured for automatic change tracking, the full-text index is automatically synchronized.</span></span> <span data-ttu-id="24251-115">Porém, a sincronização reduz um pouco o desempenho do texto completo.</span><span class="sxs-lookup"><span data-stu-id="24251-115">However, synchronization slows full-text performance somewhat.</span></span> <span data-ttu-id="24251-116">Se o desempenho estiver muito lento, você poderá fazer com que um rastreamento completo seja executado definindo o rastreamento de alterações como desligado e redefinindo-o como automático:</span><span class="sxs-lookup"><span data-stu-id="24251-116">If performance is too slow, you can cause a full crawl by setting change tracking off and then resetting it to automatic:</span></span>  
  
    -   <span data-ttu-id="24251-117">Para definir o rastreamento de alterações como desligado:</span><span class="sxs-lookup"><span data-stu-id="24251-117">To set change tracking off:</span></span>  
  
         <span data-ttu-id="24251-118">ALTER FULLTEXT INDEX ON *table_name* SET CHANGE_TRACKING OFF</span><span class="sxs-lookup"><span data-stu-id="24251-118">ALTER FULLTEXT INDEX ON *table_name* SET CHANGE_TRACKING OFF</span></span>  
  
    -   <span data-ttu-id="24251-119">Para definir o rastreamento de alterações automático como automático:</span><span class="sxs-lookup"><span data-stu-id="24251-119">To set on automatic change tracking to automatic:</span></span>  
  
         <span data-ttu-id="24251-120">ALTER FULLTEXT INDEX ON *table_name* SET CHANGE_TRACKING AUTO</span><span class="sxs-lookup"><span data-stu-id="24251-120">ALTER FULLTEXT INDEX ON *table_name* SET CHANGE_TRACKING AUTO</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="24251-121">Para verificar se o controle de alterações automático está ativado, você pode usar a função [OBJECTPROPERTYEX](/sql/t-sql/functions/objectproperty-transact-sql) para consultar a propriedade **TableFullTextBackgroundUpdateIndexOn** da tabela.</span><span class="sxs-lookup"><span data-stu-id="24251-121">To see whether auto change tracking is on, you can use the [OBJECTPROPERTYEX](/sql/t-sql/functions/objectproperty-transact-sql) function to query the **TableFullTextBackgroundUpdateIndexOn** property of the table.</span></span>  
  
 <span data-ttu-id="24251-122">Para obter mais informações, consulte [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="24251-122">For more information, see [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="24251-123">Iniciar um rastreamento após um failover funciona da mesma maneira que iniciar um rastreamento após uma restauração.</span><span class="sxs-lookup"><span data-stu-id="24251-123">Starting a crawl after failover works the same as starting a crawl after a restore.</span></span>  
  
## <a name="after-forcing-service"></a><span data-ttu-id="24251-124">Depois de forçar serviço</span><span class="sxs-lookup"><span data-stu-id="24251-124">After Forcing Service</span></span>  
 <span data-ttu-id="24251-125">Depois que o serviço é forçado para o servidor espelho (com possível perda de dados), inicie um rastreamento completo.</span><span class="sxs-lookup"><span data-stu-id="24251-125">After service is forced to the mirror server (with possible data loss), start a full crawl.</span></span> <span data-ttu-id="24251-126">O método a ser usado para iniciar um rastreamento completo depende se as alterações no índice de texto completo são rastreadas.</span><span class="sxs-lookup"><span data-stu-id="24251-126">The method to use for starting a full crawl depends on whether the full-text index is change tracked.</span></span> <span data-ttu-id="24251-127">Para obter mais informações, consulte "Índices de texto completo após o failover", anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="24251-127">For more information, see "Full-Text Indexes After Failover," earlier in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24251-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="24251-128">See Also</span></span>  
 <span data-ttu-id="24251-129">[ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="24251-129">[ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql) </span></span>  
 <span data-ttu-id="24251-130">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="24251-130">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span></span>  
 <span data-ttu-id="24251-131">[DROP FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="24251-131">[DROP FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-fulltext-index-transact-sql) </span></span>  
 <span data-ttu-id="24251-132">[Espelhamento de banco de dados &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="24251-132">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="24251-133">Fazer backup e restaurar índices e catálogos de texto completo</span><span class="sxs-lookup"><span data-stu-id="24251-133">Back Up and Restore Full-Text Catalogs and Indexes</span></span>](../../relational-databases/indexes/indexes.md)  
  
  
