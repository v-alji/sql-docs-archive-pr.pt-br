---
title: Fazer backup e restaurar bancos de dados replicados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- backups [SQL Server replication]
- administering replication, restoring
- backing up replicated databases
- backups [SQL Server replication], about backups
- restoring replicated databases [SQL Server replication]
- recovery [SQL Server replication], about recovery
- restoring databases [SQL Server], replicated databases
- backing up databases [SQL Server], replicated databases
- restoring [SQL Server replication], about restoring
- recovery [SQL Server replication]
- replication [SQL Server], administering
- distribution databases [SQL Server replication], backing up
- restoring [SQL Server replication]
- administering replication, backing up
ms.assetid: 04588807-21e7-4bbe-9727-b72f692cffa7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e91505bacf67f7f4628bd1b3f6b2cc78a6bc4c3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574664"
---
# <a name="back-up-and-restore-replicated-databases"></a><span data-ttu-id="ef66c-102">Fazer backup e restaurar bancos de dados replicados</span><span class="sxs-lookup"><span data-stu-id="ef66c-102">Back Up and Restore Replicated Databases</span></span>
  <span data-ttu-id="ef66c-103">Bancos de dados replicados requerem atenção especial em relação a backup e restauração de dados.</span><span class="sxs-lookup"><span data-stu-id="ef66c-103">Replicated databases require special attention with regards to backing up and restoring data.</span></span> <span data-ttu-id="ef66c-104">Este tópico fornece informações iniciais e links para obter mais informações sobre estratégias de backup e restauração para cada tipo de replicação.</span><span class="sxs-lookup"><span data-stu-id="ef66c-104">This topic provides introductory information and links to further information on backup and restore strategies for each type of replication.</span></span>  
  
 <span data-ttu-id="ef66c-105">A replicação oferece suporte à restauração de bancos de dados replicados para o mesmo servidor e banco de dados dos quais o backup foi criado.</span><span class="sxs-lookup"><span data-stu-id="ef66c-105">Replication supports restoring replicated databases to the same server and database from which the backup was created.</span></span> <span data-ttu-id="ef66c-106">Se você restaurar um backup de um banco de dados replicado para outro servidor ou banco de dados, as configurações de replicação não poderão ser preservadas.</span><span class="sxs-lookup"><span data-stu-id="ef66c-106">If you restore a backup of a replicated database to another server or database, replication settings cannot be preserved.</span></span> <span data-ttu-id="ef66c-107">Neste caso, você deve recriar todas as publicações e assinaturas depois que os backups forem restaurados.</span><span class="sxs-lookup"><span data-stu-id="ef66c-107">In this case, you must recreate all publications and subscriptions after backups are restored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ef66c-108">Será possível restaurar um banco de dados replicado para um servidor auxiliar se estiver sendo usada a remessa de log.</span><span class="sxs-lookup"><span data-stu-id="ef66c-108">It is possible to restore a replicated database to a standby server if log shipping is being used.</span></span> <span data-ttu-id="ef66c-109">Para obter mais informações, veja [Replicação e envio de logs &#40;SQL Server&#41;](../../../database-engine/log-shipping/log-shipping-and-replication-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ef66c-109">For more information, see [Log Shipping and Replication &#40;SQL Server&#41;](../../../database-engine/log-shipping/log-shipping-and-replication-sql-server.md).</span></span>  
  
 <span data-ttu-id="ef66c-110">Deve ser feito backup regularmente para bancos de dados replicados e bancos de dados do sistema associados.</span><span class="sxs-lookup"><span data-stu-id="ef66c-110">Replicated databases and their associated system databases should be backed up regularly.</span></span> <span data-ttu-id="ef66c-111">Faça backup dos seguintes bancos de dados:</span><span class="sxs-lookup"><span data-stu-id="ef66c-111">Back up the following databases:</span></span>  
  
-   <span data-ttu-id="ef66c-112">O banco de dados de publicação no Publicador.</span><span class="sxs-lookup"><span data-stu-id="ef66c-112">The publication database at the Publisher</span></span>  
  
-   <span data-ttu-id="ef66c-113">O banco de dados de distribuição no Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="ef66c-113">The distribution database at the Distributor</span></span>  
  
-   <span data-ttu-id="ef66c-114">O banco de dados de assinatura em cada Assinante.</span><span class="sxs-lookup"><span data-stu-id="ef66c-114">The subscription database at each Subscriber</span></span>  
  
-   <span data-ttu-id="ef66c-115">Os bancos de dados de sistema **mestre** e **msdb** no Publicador, Distribuidor e todos os Assinantes.</span><span class="sxs-lookup"><span data-stu-id="ef66c-115">The **master** and **msdb** system databases at the Publisher, Distributor and all Subscribers.</span></span> <span data-ttu-id="ef66c-116">Esses bancos de dados devem ter, cada um, seus backups realizados em simultâneo com o banco de dados de replicação relevante.</span><span class="sxs-lookup"><span data-stu-id="ef66c-116">These databases should be backed up at the same time as each other and the relevant replication database.</span></span> <span data-ttu-id="ef66c-117">Por exemplo, faça o backup dos bancos de dados **mestre** e **msdb** no Publicador ao mesmo tempo em que executa o backup do banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="ef66c-117">For example, back up the **master** and **msdb** databases at the Publisher at the same time you back up the publication database.</span></span> <span data-ttu-id="ef66c-118">Se o banco de dados de publicação for restaurado, assegure-se de que os bancos de dados **mestre** e **msdb** são consistentes com o banco de dados de publicação, em termos de configuração de replicação e ajustes.</span><span class="sxs-lookup"><span data-stu-id="ef66c-118">If the publication database is restored, ensure that the **master** and **msdb** database are consistent with the publication database in terms of replication configuration and settings.</span></span>  
  
 <span data-ttu-id="ef66c-119">Se você executar backups de log regulares, qualquer alteração relacionada à replicação deverá ser capturada nos backups de log.</span><span class="sxs-lookup"><span data-stu-id="ef66c-119">If you perform regular log backups, any replication-related changes should be captured in the log backups.</span></span> <span data-ttu-id="ef66c-120">Se não executar backups de log, um backup deve ser executado sempre que uma configuração pertinente à replicação for alterada.</span><span class="sxs-lookup"><span data-stu-id="ef66c-120">If you do not perform log backups, a backup should be performed whenever a setting relevant to replication is changed.</span></span> <span data-ttu-id="ef66c-121">Para obter mais informações, consulte [Common Actions Requiring an Updated Backup](common-actions-requiring-an-updated-backup.md).</span><span class="sxs-lookup"><span data-stu-id="ef66c-121">For more information, see [Common Actions Requiring an Updated Backup](common-actions-requiring-an-updated-backup.md).</span></span>  
  
## <a name="backup-and-restore-strategies"></a><span data-ttu-id="ef66c-122">Estratégias de backup e restauração</span><span class="sxs-lookup"><span data-stu-id="ef66c-122">Backup and Restore Strategies</span></span>  
 <span data-ttu-id="ef66c-123">As estratégias de backup e restauração de cada nó em uma topologia de replicação diferem de acordo com tipo de replicação usado.</span><span class="sxs-lookup"><span data-stu-id="ef66c-123">The strategies for backing up and restoring each node in a replication topology differ according to the type of replication used.</span></span> <span data-ttu-id="ef66c-124">Para obter informações sobre estratégias de backup e restauração para cada tipo de replicação, consulte os tópicos abaixo:</span><span class="sxs-lookup"><span data-stu-id="ef66c-124">For information on backup and restore strategies for each type of replication, see the following topics:</span></span>  
  
-   [<span data-ttu-id="ef66c-125">Estratégias para fazer backup e restaurar o instantâneo e a replicação transacional</span><span class="sxs-lookup"><span data-stu-id="ef66c-125">Strategies for Backing Up and Restoring Snapshot and Transactional Replication</span></span>](strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md)  
  
-   [<span data-ttu-id="ef66c-126">Estratégias para fazer backup e restaurar a replicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="ef66c-126">Strategies for Backing Up and Restoring Merge Replication</span></span>](strategies-for-backing-up-and-restoring-merge-replication.md)  
  
 <span data-ttu-id="ef66c-127">Como parte de qualquer estratégia de recuperação, mantenha sempre um script atual de suas configurações de replicação em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="ef66c-127">As part of any recovery strategy, always keep a current script of your replication settings in a safe location.</span></span> <span data-ttu-id="ef66c-128">No caso de uma falha do servidor ou da necessidade de configurar um ambiente de teste, você poderá modificar o script alterando as referências no nome do servidor e isso poderá ser usado para ajudar a recriar suas configurações de replicação.</span><span class="sxs-lookup"><span data-stu-id="ef66c-128">In the event of server failure or the need to set up a test environment, you can modify the script by changing server name references, and it can be used to help recreate your replication settings.</span></span> <span data-ttu-id="ef66c-129">Além de executar o script em suas configurações de replicação atuais, você deve executar o script de habilitação e desabilitação da replicação.</span><span class="sxs-lookup"><span data-stu-id="ef66c-129">In addition to scripting your current replication settings, you should script the enabling and disabling of replication.</span></span> <span data-ttu-id="ef66c-130">Para obter informações sobre a execução do script de objetos de replicação, consulte [Scripting Replication](../scripting-replication.md).</span><span class="sxs-lookup"><span data-stu-id="ef66c-130">For information about scripting replication objects, see [Scripting Replication](../scripting-replication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef66c-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ef66c-131">See Also</span></span>  
 <span data-ttu-id="ef66c-132">[Fazer backup e restaurar bancos de dados do SQL Server](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="ef66c-132">[Back Up and Restore of SQL Server Databases](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 [<span data-ttu-id="ef66c-133">Best Practices for Replication Administration</span><span class="sxs-lookup"><span data-stu-id="ef66c-133">Best Practices for Replication Administration</span></span>](best-practices-for-replication-administration.md)  
  
  
