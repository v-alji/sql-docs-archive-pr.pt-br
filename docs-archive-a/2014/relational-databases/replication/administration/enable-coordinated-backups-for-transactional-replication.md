---
title: Habilitar backups coordenados para replicação transacional (Programação Transact-SQL de replicação) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- transactional replication, backup and restore
- sp_replicationdboption
- sync with backup [SQL Server replication]
- coordinated backups [SQL Server replication]
- backups [SQL Server replication], transactional replication
ms.assetid: 73a914ba-8b2d-4f4d-ac1b-db9bac676a30
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 77405cd968fa917c3ccc799eb7d168782443eee9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685588"
---
# <a name="enable-coordinated-backups-for-transactional-replication-replication-transact-sql-programming"></a><span data-ttu-id="329e9-102">Habilitar backups coordenados para a replicação transacional (Programação Transact-SQL de replicação)</span><span class="sxs-lookup"><span data-stu-id="329e9-102">Enable Coordinated Backups for Transactional Replication (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="329e9-103">Quando habilitar um banco de dados para a replicação transacional, é possível especificar que seja efetuado um backup de todas as transações antes que elas sejam entregues ao banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="329e9-103">When enabling a database for transactional replication, you can specify that all transactions must be backed up before being delivered to the distribution database.</span></span> <span data-ttu-id="329e9-104">Você pode habilitar também um backup coordenado no banco de dados de distribuição de modo que o log de transações, para o banco de dados de publicação, não fique truncado até que seja efetuado o backup das transações que foram propagadas ao Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="329e9-104">You can also enable coordinated backup on the distribution database so that the transaction log for the publication database is not truncated until transactions that have been propagated to the Distributor have been backed up.</span></span> <span data-ttu-id="329e9-105">Para obter mais informações, consulte [Estratégias para fazer backup e restaurar o instantâneo e a replicação transacional](strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="329e9-105">For more information, see [Strategies for Backing Up and Restoring Snapshot and Transactional Replication](strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md).</span></span>  
  
### <a name="to-enable-coordinated-backups-for-a-database-published-with-transactional-replication"></a><span data-ttu-id="329e9-106">Para habilitar backups coordenados para um banco de dados publicado com replicação transacional</span><span class="sxs-lookup"><span data-stu-id="329e9-106">To enable coordinated backups for a database published with transactional replication</span></span>  
  
1.  <span data-ttu-id="329e9-107">No Publicador, use a função [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql) para retornar a propriedade **IsSyncWithBackup** do banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="329e9-107">At the Publisher, use the [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql) function to return the **IsSyncWithBackup** property of the publication database.</span></span> <span data-ttu-id="329e9-108">Se a função retornar **1**, os backups coordenados já estarão habilitados para o banco de dados publicado.</span><span class="sxs-lookup"><span data-stu-id="329e9-108">If the function returns **1**, coordinated backups are already enabled for the published database.</span></span>  
  
2.  <span data-ttu-id="329e9-109">Se a função na etapa 1 retornar **0**, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) no Publicador do banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="329e9-109">If the function in step 1 returns **0**, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) at the Publisher on the publication database.</span></span> <span data-ttu-id="329e9-110">Especifique um valor de **sync with backup** para **\@optname** e **true** para **\@value**.</span><span class="sxs-lookup"><span data-stu-id="329e9-110">Specify a value of **sync with backup** for **\@optname**, and **true** for **\@value**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="329e9-111">Se alterar a opção **sync with backup** para **falso**, o ponto de truncamento do banco de dados de publicação será atualizado após a execução do Agente de Leitor de Log ou após um intervalo, caso o Agente de Leitor de Log esteja executando continuamente.</span><span class="sxs-lookup"><span data-stu-id="329e9-111">If you change the **sync with backup** option to **false**, the truncation point of the publication database will be updated after the Log Reader Agent runs, or after an interval if the Log Reader Agent is running continuously.</span></span> <span data-ttu-id="329e9-112">O intervalo máximo é controlado pelo parâmetro do agente **-MessageInterval** (que tem um padrão de 30 segundos).</span><span class="sxs-lookup"><span data-stu-id="329e9-112">The maximum interval is controlled by the **-MessageInterval** agent parameter (which has a default of 30 seconds).</span></span>  
  
### <a name="to-enable-coordinated-backups-for-a-distribution-database"></a><span data-ttu-id="329e9-113">Para habilitar backups coordenados para um banco de dados de distribuição</span><span class="sxs-lookup"><span data-stu-id="329e9-113">To enable coordinated backups for a distribution database</span></span>  
  
1.  <span data-ttu-id="329e9-114">No Editor, use a função [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql) para retornar a propriedade **IsSyncWithBackup** do banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="329e9-114">At the Distributor, use the [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql) function to return the **IsSyncWithBackup** property of the distribution database.</span></span> <span data-ttu-id="329e9-115">Se a função retornar **1**, os backups coordenados já estarão habilitados para o banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="329e9-115">If the function returns **1**, coordinated backups are already enabled for the distribution database.</span></span>  
  
2.  <span data-ttu-id="329e9-116">Se a função na etapa 1 retornar **0**, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) no Distribuidor do banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="329e9-116">If the function in step 1 returns **0**, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) at the Distributor on the distribution database.</span></span> <span data-ttu-id="329e9-117">Especifique um valor de **sincronização com backup** para \*\* \@ OptName\*\* e **true** para \*\* \@ valor\*\*.</span><span class="sxs-lookup"><span data-stu-id="329e9-117">Specify a value of **sync with backup** for **\@optname** and **true** for **\@value**.</span></span>  
  
### <a name="to-disable-coordinated-backups"></a><span data-ttu-id="329e9-118">Para desabilitar backups coordenados</span><span class="sxs-lookup"><span data-stu-id="329e9-118">To disable coordinated backups</span></span>  
  
1.  <span data-ttu-id="329e9-119">No Publicador do banco de dados de publicação ou no Distribuidor no banco de dados de distribuição, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="329e9-119">At either the Publisher on the publication database or at the Distributor on the distribution database, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql).</span></span> <span data-ttu-id="329e9-120">Especifique um valor **sync with backup** para **\@optname** e **false** para **\@value**.</span><span class="sxs-lookup"><span data-stu-id="329e9-120">Specify a value of **sync with backup** for **\@optname** and **false** for **\@value**.</span></span>  
  
  
