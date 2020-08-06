---
title: Exibir comandos replicados e outras informações no banco de dados de distribuição (Programação Transact-SQL de replicação) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- sp_browsereplcmds
- transactional replication, monitoring
- distribution databases [SQL Server replication], viewing replicated commands
- viewing replicated commands
ms.assetid: 9c20acec-8fab-4483-b9c1-dfe3768f85dd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fb5850277d685f2ecf6471fa4bf9814579b2843e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685549"
---
# <a name="view-replicated-commands-and-other-information-in-the-distribution-database-replication-transact-sql-programming"></a><span data-ttu-id="68d5a-102">Exibir comandos replicados e outras informações no banco de dados de distribuição (Programação Transact-SQL de replicação)</span><span class="sxs-lookup"><span data-stu-id="68d5a-102">View Replicated Commands and Other Information in the Distribution Database (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="68d5a-103">Ao usar replicação transacional, os comandos de transação são armazenados no banco de dados de distribuição ou até que o Agente de Distribuição os propague a todos os Assinantes ou até um Agente de Distribuição enviar as alterações ao Assinante.</span><span class="sxs-lookup"><span data-stu-id="68d5a-103">When using transactional replication, transaction commands are stored in the distribution database until the Distribution Agent propagates them to all Subscribers or a Distribution Agent at the Subscriber pulls the changes.</span></span> <span data-ttu-id="68d5a-104">Esses comandos pendentes no banco de dados de distribuição podem ser exibidos programaticamente por meio de procedimentos armazenados de replicação.</span><span class="sxs-lookup"><span data-stu-id="68d5a-104">These pending commands in the distribution database can be viewed programmatically using replication stored procedures.</span></span> <span data-ttu-id="68d5a-105">Para obter mais informações, consulte [procedimentos armazenados de replicação &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="68d5a-105">For more information, see [Replication Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql).</span></span>  
  
### <a name="to-view-replicated-commands-from-all-transactional-publications-in-the-distribution-database"></a><span data-ttu-id="68d5a-106">Para exibir os comandos replicados de todas as publicações transacionais no banco de dados de distribuição</span><span class="sxs-lookup"><span data-stu-id="68d5a-106">To view replicated commands from all transactional publications in the distribution database</span></span>  
  
1.  <span data-ttu-id="68d5a-107">No Distribuidor, no banco de dados de distribuição, execute [sp_browsereplcmds](/sql/relational-databases/system-stored-procedures/sp-browsemergesnapshotfolder-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="68d5a-107">At the Distributor on the distribution database, execute [sp_browsereplcmds](/sql/relational-databases/system-stored-procedures/sp-browsemergesnapshotfolder-transact-sql).</span></span>  
  
### <a name="to-view-replicated-commands-in-the-distribution-database-from-a-specific-article-or-from-a-specific-database-published-using-transactional-replication"></a><span data-ttu-id="68d5a-108">Para exibir comandos replicados no banco de dados de distribuição de um artigo específico ou de um banco de dados publicado específico por meio de replicação transacional</span><span class="sxs-lookup"><span data-stu-id="68d5a-108">To view replicated commands in the distribution database from a specific article or from a specific database published using transactional replication</span></span>  
  
1.  <span data-ttu-id="68d5a-109">(Opcional) No Publicador, no banco de dados de publicação, execute [sp_helparticle](/sql/relational-databases/system-stored-procedures/sp-helparticle-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="68d5a-109">(Optional) At the Publisher on the publication database, execute [sp_helparticle](/sql/relational-databases/system-stored-procedures/sp-helparticle-transact-sql).</span></span> <span data-ttu-id="68d5a-110">Especifique a \*\* \@ publicação\*\* e o \*\* \@ artigo\*\*.</span><span class="sxs-lookup"><span data-stu-id="68d5a-110">Specify **\@publication** and **\@article**.</span></span> <span data-ttu-id="68d5a-111">Observe o valor de **id de artigo** no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="68d5a-111">Note the value of **article id** in the result set.</span></span>  
  
2.  <span data-ttu-id="68d5a-112">No Distribuidor, no banco de dados de distribuição, execute [sp_browsereplcmds](/sql/relational-databases/system-stored-procedures/sp-browsemergesnapshotfolder-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="68d5a-112">At the Distributor on the distribution database, execute [sp_browsereplcmds](/sql/relational-databases/system-stored-procedures/sp-browsemergesnapshotfolder-transact-sql).</span></span> <span data-ttu-id="68d5a-113">Adicional Especifique a ID do artigo da etapa 2 para \*\* \@ article_id\*\*.</span><span class="sxs-lookup"><span data-stu-id="68d5a-113">(Optional) Specify the article ID from step 2 for **\@article_id**.</span></span> <span data-ttu-id="68d5a-114">Adicional Especifique a ID do banco de dados de publicação para \*\* \@ publisher_database_id\*\*, que pode ser obtida na coluna **database_id** na exibição do catálogo [Sys. databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="68d5a-114">(Optional) Specify the ID of the publication database for **\@publisher_database_id**, which can be obtained from the **database_id** column in the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68d5a-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="68d5a-115">See Also</span></span>  
 [<span data-ttu-id="68d5a-116">Monitorar programaticamente a replicação</span><span class="sxs-lookup"><span data-stu-id="68d5a-116">Programmatically Monitor Replication</span></span>](../monitoring-replication.md)  
  
  
