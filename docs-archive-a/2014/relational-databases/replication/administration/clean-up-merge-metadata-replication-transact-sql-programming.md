---
title: Limpar metadados de mesclagem (programação de Transact-SQL de replicação) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- metadata [SQL Server replication]
- sp_mergemetadataretentioncleanup
ms.assetid: 9b88baea-b7c6-4e5d-88f9-93d6a0ff0368
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5a2306db72fd3f0098e18ff058796a5498eafcac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683507"
---
# <a name="clean-up-merge-metadata-replication-transact-sql-programming"></a><span data-ttu-id="46d50-102">Limpar metadados de mesclagem (Programação Transact-SQL de replicação)</span><span class="sxs-lookup"><span data-stu-id="46d50-102">Clean Up Merge Metadata (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="46d50-103">Os metadados de replicação de mesclagem são limpados periodicamente pelo Agente de Mesclagem com base na configuração de retenção para a publicação.</span><span class="sxs-lookup"><span data-stu-id="46d50-103">Merge replication metadata is cleaned up periodically by the Merge Agent based on the retention setting for the publication.</span></span> <span data-ttu-id="46d50-104">Isso acontece no Publicador e Assinante no [MSmerge_genhistory](/sql/relational-databases/system-tables/msmerge-genhistory-transact-sql), [MSmerge_contents](/sql/relational-databases/system-tables/msmerge-contents-transact-sql), [MSmerge_tombstone](/sql/relational-databases/system-tables/msmerge-tombstone-transact-sql), [MSmerge_past_partition_mappings](/sql/relational-databases/system-tables/msmerge-past-partition-mappings-transact-sql)e nas tabelas do sistema [de MSmerge_current_partition_mappings](/sql/relational-databases/system-tables/msmerge-current-partition-mappings) .</span><span class="sxs-lookup"><span data-stu-id="46d50-104">This occurs at the Publisher and Subscriber in the [MSmerge_genhistory](/sql/relational-databases/system-tables/msmerge-genhistory-transact-sql), [MSmerge_contents](/sql/relational-databases/system-tables/msmerge-contents-transact-sql), [MSmerge_tombstone](/sql/relational-databases/system-tables/msmerge-tombstone-transact-sql), [MSmerge_past_partition_mappings](/sql/relational-databases/system-tables/msmerge-past-partition-mappings-transact-sql), and [MSmerge_current_partition_mappings](/sql/relational-databases/system-tables/msmerge-current-partition-mappings) system tables.</span></span> <span data-ttu-id="46d50-105">Também é possível limpar programaticamente os dados nessas tabelas usando procedimentos armazenados de replicação.</span><span class="sxs-lookup"><span data-stu-id="46d50-105">You can also programmatically clean up the data in these tables using replication stored procedures.</span></span>  
  
### <a name="to-manually-clean-up-merge-metadata"></a><span data-ttu-id="46d50-106">Para limpar os metadados de mesclagem manualmente</span><span class="sxs-lookup"><span data-stu-id="46d50-106">To manually clean up merge metadata</span></span>  
  
1.  <span data-ttu-id="46d50-107">No Publicador do banco de dados de publicação, execute [sp_mergemetadataretentioncleanup](/sql/relational-databases/system-stored-procedures/sp-mergemetadataretentioncleanup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="46d50-107">At the Publisher on the publication database, execute [sp_mergemetadataretentioncleanup](/sql/relational-databases/system-stored-procedures/sp-mergemetadataretentioncleanup-transact-sql).</span></span>  
  
2.  <span data-ttu-id="46d50-108">Adicional Observe o número de linhas removidas na etapa 1 da [MSmerge_genhistory](/sql/relational-databases/system-tables/msmerge-genhistory-transact-sql), [MSmerge_contents](/sql/relational-databases/system-tables/msmerge-contents-transact-sql)e [MSmerge_tombstone](/sql/relational-databases/system-tables/msmerge-tombstone-transact-sql) tabelas do sistema, retornadas respectivamente nos **@num_genhistory_rows** parâmetros de saída, **@num_contents_rows** e **@num_tombstone_rows** .</span><span class="sxs-lookup"><span data-stu-id="46d50-108">(Optional) Note the number of rows removed in step 1 from the [MSmerge_genhistory](/sql/relational-databases/system-tables/msmerge-genhistory-transact-sql), [MSmerge_contents](/sql/relational-databases/system-tables/msmerge-contents-transact-sql), and [MSmerge_tombstone](/sql/relational-databases/system-tables/msmerge-tombstone-transact-sql) system tables, returned respectively in the **@num_genhistory_rows**, **@num_contents_rows**, and **@num_tombstone_rows** output parameters.</span></span>  
  
3.  <span data-ttu-id="46d50-109">Repita as etapas 1 e 2 no Assinante para limpar os metadados no banco de dados de assinatura.</span><span class="sxs-lookup"><span data-stu-id="46d50-109">Repeat steps 1 and 2 at the Subscriber to clean up metadata on the subscription database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46d50-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="46d50-110">See Also</span></span>  
 [<span data-ttu-id="46d50-111">Desativação e expiração de assinatura</span><span class="sxs-lookup"><span data-stu-id="46d50-111">Subscription Expiration and Deactivation</span></span>](../subscription-expiration-and-deactivation.md)  
  
  
