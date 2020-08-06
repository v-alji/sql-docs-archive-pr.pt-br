---
title: Fazer failover para um secundário do envio de logs (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- primary databases [SQL Server]
- secondary data files [SQL Server], manual fail over
- log shipping [SQL Server], failover
- failover [SQL Server], log shipping
ms.assetid: edfe5d59-4287-49c1-96c9-dd56212027bc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 164e2809e4eff5a14ef54124df7c7ca9077793ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681825"
---
# <a name="fail-over-to-a-log-shipping-secondary-sql-server"></a><span data-ttu-id="3b93b-102">Failover para um envio de logs secundário (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3b93b-102">Fail Over to a Log Shipping Secondary (SQL Server)</span></span>
  <span data-ttu-id="3b93b-103">O failover para um envio de logs secundário será útil se a instância do servidor primário falhar ou requerer manutenção.</span><span class="sxs-lookup"><span data-stu-id="3b93b-103">Failing over to a log shipping secondary is useful if the primary server instance fails or requires maintenance.</span></span>  
  
## <a name="preparing-for-a-controlled-failover"></a><span data-ttu-id="3b93b-104">Preparando para um failover controlado</span><span class="sxs-lookup"><span data-stu-id="3b93b-104">Preparing for a Controlled Failover</span></span>  
 <span data-ttu-id="3b93b-105">Geralmente, os bancos de dados primário e secundário não são sincronizados porque o banco de dados primário continua sendo atualizado após seu último trabalho de backup.</span><span class="sxs-lookup"><span data-stu-id="3b93b-105">Typically, the primary and secondary databases are unsynchronized, because the primary database continues to be updated after its latest backup job.</span></span> <span data-ttu-id="3b93b-106">Além disso, em alguns casos, os backups de log de transações recentes não foram copiados nas instâncias do servidor secundário ou alguns backups de log copiados talvez ainda não tenham sido aplicados ao banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="3b93b-106">Also, in some cases, recent transaction log backups have not been copied to the secondary server instances, or some copied log backups might still not have been applied to the secondary database.</span></span> <span data-ttu-id="3b93b-107">Recomendamos que você comece sincronizando todos os bancos de dados secundários com o banco de dados primário, se possível.</span><span class="sxs-lookup"><span data-stu-id="3b93b-107">We recommend that you begin by synchronizing all of the secondary databases with the primary database, if possible.</span></span>  
  
 <span data-ttu-id="3b93b-108">Para obter informações sobre trabalhos do envio de log, veja [Sobre o envio de logs &#40;SQL Server&#41;](about-log-shipping-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3b93b-108">For information about log shipping jobs, see [About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md).</span></span>  
  
## <a name="failing-over"></a><span data-ttu-id="3b93b-109">Fazendo failover</span><span class="sxs-lookup"><span data-stu-id="3b93b-109">Failing Over</span></span>  
 <span data-ttu-id="3b93b-110">Para fazer failover para um banco de dados secundário:</span><span class="sxs-lookup"><span data-stu-id="3b93b-110">To fail over to a secondary database:</span></span>  
  
1.  <span data-ttu-id="3b93b-111">Copie qualquer arquivo de backup não copiado do compartilhamento de backup na pasta de destino de cópia de cada servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="3b93b-111">Copy any uncopied backup files from the backup share to the copy destination folder of each secondary server.</span></span>  
  
2.  <span data-ttu-id="3b93b-112">Aplique qualquer backup de log de transações não aplicado em sequência em cada banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="3b93b-112">Apply any unapplied transaction log backups in sequence to each secondary database.</span></span> <span data-ttu-id="3b93b-113">Para obter mais informações, veja [Aplicar backups de log de transações &#40;SQL Server&#41;](../../relational-databases/backup-restore/apply-transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3b93b-113">For more information, see [Apply Transaction Log Backups &#40;SQL Server&#41;](../../relational-databases/backup-restore/apply-transaction-log-backups-sql-server.md).</span></span>  
  
3.  <span data-ttu-id="3b93b-114">Se o banco de dados primário estiver acessível, faça backup do log de transações ativas e aplique-o aos bancos de dados secundários.</span><span class="sxs-lookup"><span data-stu-id="3b93b-114">If the primary database is accessible, back up the active transaction log and apply the log backup to the secondary databases.</span></span>  
  
     <span data-ttu-id="3b93b-115">Se a instância de servidor primário original não estiver danificada, faça backup da parte final do log de transações do banco de dados primário usando WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="3b93b-115">If the original primary server instance is not damaged, back up the tail of the transaction log of the primary database using WITH NORECOVERY.</span></span> <span data-ttu-id="3b93b-116">Isso deixa o banco de dados no estado de restauração e, portanto, indisponível aos usuários.</span><span class="sxs-lookup"><span data-stu-id="3b93b-116">This leaves the database in the restoring state and therefore unavailable to users.</span></span> <span data-ttu-id="3b93b-117">Eventualmente você poderá avançar a rolagem desse banco de dados aplicando backups de log de transações do banco de dados primário substituído.</span><span class="sxs-lookup"><span data-stu-id="3b93b-117">Eventually you will be able to roll this database forward by applying transaction log backups from the replacement primary database.</span></span>  
  
     <span data-ttu-id="3b93b-118">Para obter mais informações, veja [Backups de log do transações &#40;SQL Server&#41;](../../relational-databases/backup-restore/transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3b93b-118">For more information, see [Transaction Log Backups &#40;SQL Server&#41;](../../relational-databases/backup-restore/transaction-log-backups-sql-server.md).</span></span>  
  
4.  <span data-ttu-id="3b93b-119">Depois que os servidores secundários forem sincronizados, você poderá fazer o failover para o banco de dados que preferir recuperando o banco de dados secundário e redirecionando os clientes para aquela instância de servidor.</span><span class="sxs-lookup"><span data-stu-id="3b93b-119">After the secondary servers are synchronized, you can fail over to whichever one you prefer by recovering its secondary database and redirecting clients to that server instance.</span></span> <span data-ttu-id="3b93b-120">A recuperação coloca o banco de dados em um estado consistente e online.</span><span class="sxs-lookup"><span data-stu-id="3b93b-120">Recovering puts the database into a consistent state and brings it online.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3b93b-121">Ao disponibilizar um banco de dados secundário, você deve assegurar que os metadados estejam consistentes com os metadados do banco de dados primário original.</span><span class="sxs-lookup"><span data-stu-id="3b93b-121">When you make a secondary database available, you should ensure that its metadata is consistent with the metadata of the original primary database.</span></span> <span data-ttu-id="3b93b-122">Para obter mais informações, consulte [Gerenciar metadados ao disponibilizar um banco de dados em outra instância do servidor &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span><span class="sxs-lookup"><span data-stu-id="3b93b-122">For more information, see [Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span></span>  
  
5.  <span data-ttu-id="3b93b-123">Depois de recuperar um banco de dados secundário, você poderá reconfigurá-lo para que atue como um banco de dados primário para outros bancos de dados secundários.</span><span class="sxs-lookup"><span data-stu-id="3b93b-123">After you have recovered a secondary database, you can reconfigure it to act as a primary database for other secondary databases.</span></span>  
  
     <span data-ttu-id="3b93b-124">Se nenhum outro banco de dados secundário estiver disponível, veja [Configurar o envio de logs &#40;SQL Server&#41;](configure-log-shipping-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3b93b-124">If no other secondary database is available, see [Configure Log Shipping &#40;SQL Server&#41;](configure-log-shipping-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="3b93b-125">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="3b93b-125">Related Tasks</span></span>  
  
-   [<span data-ttu-id="3b93b-126">Alterar funções entre servidores de envio de log primários e secundários &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3b93b-126">Change Roles Between Primary and Secondary Log Shipping Servers &#40;SQL Server&#41;</span></span>](change-roles-between-primary-and-secondary-log-shipping-servers-sql-server.md)  
  
-   [<span data-ttu-id="3b93b-127">Gerenciamento de logons e trabalhos após a troca de funções &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3b93b-127">Management of Logins and Jobs After Role Switching &#40;SQL Server&#41;</span></span>](../../sql-server/failover-clusters/management-of-logins-and-jobs-after-role-switching-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="3b93b-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3b93b-128">See Also</span></span>  
 <span data-ttu-id="3b93b-129">[Tabelas de envio de log e procedimentos armazenados](log-shipping-tables-and-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="3b93b-129">[Log Shipping Tables and Stored Procedures](log-shipping-tables-and-stored-procedures.md) </span></span>  
 <span data-ttu-id="3b93b-130">[Sobre o envio de logs &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3b93b-130">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="3b93b-131">Backups da parte final do log &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3b93b-131">Tail-Log Backups &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/tail-log-backups-sql-server.md)  
  
  
