---
title: Sincronizar dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- synchronization [SQL Server replication], about synchronization
- merge replication synchronization [SQL Server replication]
- scripts [SQL Server replication], synchronization and
- synchronization [SQL Server replication]
- snapshot replication [SQL Server], synchronization
- transactional replication, synchronization
- subscriptions [SQL Server replication], synchronizing
- on demand script execution
- replication [SQL Server], synchronization
- scripts [SQL Server replication]
ms.assetid: 724802f7-7d69-46d3-a330-bd8aa7f53114
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c92cc4d1ae8e836f169a731ecf3c37c81f3dbf10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680891"
---
# <a name="synchronize-data"></a><span data-ttu-id="8b5be-102">Sincronizar dados</span><span class="sxs-lookup"><span data-stu-id="8b5be-102">Synchronize Data</span></span>
  <span data-ttu-id="8b5be-103">Sincronizando dados se refere ao processo de alterações de dados e esquemas sendo propagadas entre o Publicador e os Assinantes após o instantâneo inicial ter sido aplicado ao Assinante.</span><span class="sxs-lookup"><span data-stu-id="8b5be-103">Synchronizing data refers to the process of data and schema changes being propagated between the Publisher and Subscribers after the initial snapshot has been applied at the Subscriber.</span></span> <span data-ttu-id="8b5be-104">A sincronização pode acontecer:</span><span class="sxs-lookup"><span data-stu-id="8b5be-104">Synchronization can occur:</span></span>  
  
-   <span data-ttu-id="8b5be-105">Continuamente, o que é típico para replicação transacional.</span><span class="sxs-lookup"><span data-stu-id="8b5be-105">Continuously, which is typical for transactional replication.</span></span>  
  
-   <span data-ttu-id="8b5be-106">Sob demanda, o que é típico para replicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="8b5be-106">On demand, which is typical for merge replication.</span></span>  
  
-   <span data-ttu-id="8b5be-107">Em um agendamento, o que é típico para replicação de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="8b5be-107">On a schedule, which is typical for snapshot replication.</span></span>  
  
 <span data-ttu-id="8b5be-108">Quando uma assinatura é sincronizada, diferentes processos acontecem baseados no tipo de replicação que você está usando:</span><span class="sxs-lookup"><span data-stu-id="8b5be-108">When a subscription is synchronized, different processes occur based on the type of replication you are using:</span></span>  
  
-   <span data-ttu-id="8b5be-109">Replicação de instantâneo</span><span class="sxs-lookup"><span data-stu-id="8b5be-109">Snapshot replication.</span></span> <span data-ttu-id="8b5be-110">A sincronização significa que o Agente de Distribuição reaplicou o instantâneo ao Assinante para que o esquema e os dados no banco de dados da assinatura sejam consistentes com o bando de dados da publicação.</span><span class="sxs-lookup"><span data-stu-id="8b5be-110">Synchronization means that the Distribution Agent reapplies the snapshot at the Subscriber so that schema and data at the subscription database is consistent with the publication database.</span></span>  
  
     <span data-ttu-id="8b5be-111">Se alterações nos dados ou no esquema tiverem sido feitas no Publicador, um novo instantâneo deve ser gerado para propagar as modificações ao Assinante.</span><span class="sxs-lookup"><span data-stu-id="8b5be-111">If modifications to data or schema have been made at the Publisher, a new snapshot must be generated in order to propagate modifications to the Subscriber.</span></span>  
  
-   <span data-ttu-id="8b5be-112">Replicação transacional.</span><span class="sxs-lookup"><span data-stu-id="8b5be-112">Transactional replication.</span></span> <span data-ttu-id="8b5be-113">A sincronização significa que o Agente de Distribuição transfere atualizações, inserções, exclusões e quaisquer outras modificações do banco de dados de distribuição ao Assinante.</span><span class="sxs-lookup"><span data-stu-id="8b5be-113">Synchronization means that the Distribution Agent transfers updates, inserts, deletes, and any other changes from the distribution database to the Subscriber.</span></span>  
  
-   <span data-ttu-id="8b5be-114">Replicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="8b5be-114">Merge replication.</span></span> <span data-ttu-id="8b5be-115">A sincronização significa que o Agente de Mesclagem carrega alterações do Assinante ao Publicador e depois baixa as alterações do Publicador ao Assinante.</span><span class="sxs-lookup"><span data-stu-id="8b5be-115">Synchronization means that the Merge Agent uploads changes from the Subscriber to the Publisher and then downloads changes from the Publisher to the Subscriber.</span></span> <span data-ttu-id="8b5be-116">Conflitos, se houver, são detectados e resolvidos.</span><span class="sxs-lookup"><span data-stu-id="8b5be-116">Conflicts, if any, are detected and resolved.</span></span> <span data-ttu-id="8b5be-117">Os dados são convergidos e o Publicador e todos os Assinantes eventualmente acabam com os mesmos valores de dados.</span><span class="sxs-lookup"><span data-stu-id="8b5be-117">Data is converged, and the Publisher and all Subscribers eventually end up with the same data values.</span></span> <span data-ttu-id="8b5be-118">Se os conflitos forem detectados e resolvidos, o trabalho que foi confirmado por alguns usuários é alterado para resolver o conflito de acordo com a política que você definir.</span><span class="sxs-lookup"><span data-stu-id="8b5be-118">If conflicts were detected and resolved, work that was committed by some of the users is changed to resolve the conflict according to policies you define.</span></span>  
  
 <span data-ttu-id="8b5be-119">Publicações de instantâneo atualizam completamente o esquema no Assinante cada vez que ocorrer uma sincronização, assim todas as alterações de esquema são aplicadas ao Assinante.</span><span class="sxs-lookup"><span data-stu-id="8b5be-119">Snapshot publications completely refresh the schema at the Subscriber every time synchronization occurs, so all schema changes are applied to the Subscriber.</span></span> <span data-ttu-id="8b5be-120">Replicação transacional e replicação de mesclagem também oferecem suporte às alterações de esquema mais comuns.</span><span class="sxs-lookup"><span data-stu-id="8b5be-120">Transactional replication and merge replication also support the most common schema changes.</span></span> <span data-ttu-id="8b5be-121">Para obter mais informações, consulte [Make Schema Changes on Publication Databases](publish/make-schema-changes-on-publication-databases.md) (Fazer alterações de esquema em bancos de dados de publicação).</span><span class="sxs-lookup"><span data-stu-id="8b5be-121">For more information, see [Make Schema Changes on Publication Databases](publish/make-schema-changes-on-publication-databases.md).</span></span>  
  
 <span data-ttu-id="8b5be-122">Para sincronizar uma assinatura push, consulte [Synchronize a Push Subscription](synchronize-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="8b5be-122">To synchronize a push subscription, see [Synchronize a Push Subscription](synchronize-a-push-subscription.md).</span></span>  
  
 <span data-ttu-id="8b5be-123">Para sincronizar uma assinatura pull, consulte [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="8b5be-123">To synchronize a pull subscription, see [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md).</span></span>  
  
 <span data-ttu-id="8b5be-124">Para definir agendas de sincronização, consulte [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="8b5be-124">To set synchronization schedules, see [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span></span>  
  
 <span data-ttu-id="8b5be-125">**Para exibir e resolver conflitos de sincronização**</span><span class="sxs-lookup"><span data-stu-id="8b5be-125">**To view and resolve synchronization conflicts**</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="8b5be-126">: [Exibir e resolver conflitos de dados em publicações de mesclagem &#40;SQL Server Management Studio&#41;](view-and-resolve-data-conflicts-for-merge-publications.md)</span><span class="sxs-lookup"><span data-stu-id="8b5be-126">: [View and Resolve Data Conflicts for Merge Publications &#40;SQL Server Management Studio&#41;](view-and-resolve-data-conflicts-for-merge-publications.md)</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="8b5be-127">: [Exibir conflitos de dados em publicações transacionais &#40;SQL Server Management Studio&#41;](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md)</span><span class="sxs-lookup"><span data-stu-id="8b5be-127">: [View Data Conflicts for Transactional Publications &#40;SQL Server Management Studio&#41;](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md)</span></span>  
  
## <a name="executing-code-during-synchronization"></a><span data-ttu-id="8b5be-128">Executando código durante sincronização</span><span class="sxs-lookup"><span data-stu-id="8b5be-128">Executing Code During Synchronization</span></span>  
 <span data-ttu-id="8b5be-129">A replicação suporta dois métodos de execução de código durante a sincronização</span><span class="sxs-lookup"><span data-stu-id="8b5be-129">Replication supports two methods of executing code during synchronization</span></span>  
  
-   <span data-ttu-id="8b5be-130">A execução de script sob demanda tem suporte para replicação transacional e replicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="8b5be-130">On demand script execution is supported for transactional replication and merge replication.</span></span> <span data-ttu-id="8b5be-131">Usando em execução de script sob demanda, você pode especificar um script SQL para ser executado durante a sincronização.</span><span class="sxs-lookup"><span data-stu-id="8b5be-131">Using on demand script execution you can specify a SQL script to run during synchronization.</span></span> <span data-ttu-id="8b5be-132">O script é copiado ao Assinante e executado usando **sqlcmd** no começo do processo de sincronização.</span><span class="sxs-lookup"><span data-stu-id="8b5be-132">The script is copied to the Subscriber and executed using **sqlcmd** at the beginning of the synchronization process.</span></span> <span data-ttu-id="8b5be-133">O script não tem acesso às alterações replicadas enquanto elas são aplicadas ao Assinante.</span><span class="sxs-lookup"><span data-stu-id="8b5be-133">The script does not have access to the replicated changes as they are applied to the Subscriber.</span></span> <span data-ttu-id="8b5be-134">Para obter mais informações, consulte [Executar scripts durante a sincronização &#40;Programação do Transact-SQL de Replicação&#41;](execute-scripts-during-synchronization-replication-transact-sql-programming.md).</span><span class="sxs-lookup"><span data-stu-id="8b5be-134">For more information, see [Execute Scripts During Synchronization &#40;Replication Transact-SQL Programming&#41;](execute-scripts-during-synchronization-replication-transact-sql-programming.md).</span></span>  
  
-   <span data-ttu-id="8b5be-135">Manipuladores de lógica de negócios possuem suporte para replicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="8b5be-135">Business logic handlers are supported for merge replication.</span></span> <span data-ttu-id="8b5be-136">Usando a estrutura dos manipuladores de lógica de negócios, você pode escrever um assembly de código gerenciado durante o processo de sincronização de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="8b5be-136">Using the business logic handler framework you can write a managed code assembly that is called during the merge synchronization process.</span></span> <span data-ttu-id="8b5be-137">O assembly inclui lógica comercial que pode responder a uma série de condições durante a sincronização: alterações de dados, conflitos e erros.</span><span class="sxs-lookup"><span data-stu-id="8b5be-137">The assembly includes business logic that can respond to a number of conditions during synchronization: data changes, conflicts, and errors.</span></span> <span data-ttu-id="8b5be-138">Para obter mais informações, consulte [Executar lógica de negócios durante a sincronizações de mesclagem](merge/execute-business-logic-during-merge-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="8b5be-138">For more information, see [Execute Business Logic During Merge Synchronization](merge/execute-business-logic-during-merge-synchronization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b5be-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8b5be-139">See Also</span></span>  
 [<span data-ttu-id="8b5be-140">Detectar e resolver conflitos de replicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="8b5be-140">Detect and Resolve Merge Replication Conflicts</span></span>](merge/advanced-merge-replication-conflict-detection-and-resolution.md)  
  
  
