---
title: Assinantes e Grupos de Disponibilidade AlwaysOn de replicação (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 01/16/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- failover subscribers with AlwaysOn
- Availability Groups [SQL Server], interoperability
- replication [SQL Server], AlwaysOn Availability Groups
ms.assetid: 0995f269-0580-43ed-b8bf-02b9ad2d7ee6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 449b5ac416f2ae86395c40a984678ed4258b3b85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574910"
---
# <a name="replication-subscribers-and-alwayson-availability-groups-sql-server"></a><span data-ttu-id="5747b-102">Assinantes de replicação e grupos de disponibilidade AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5747b-102">Replication Subscribers and AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="5747b-103">Quando um grupo de disponibilidade AlwaysOn contendo um banco de dados que é um assinante de replicação executar failover, a assinatura de replicação poderá falhar.</span><span class="sxs-lookup"><span data-stu-id="5747b-103">When an AlwaysOn availability group containing a database that is a replication subscriber fails over, the replication subscription might fail.</span></span> <span data-ttu-id="5747b-104">Para assinantes por push de replicação transacional, o agente de distribuição continuará a replicar automaticamente após um failover se a assinatura tiver sido criada usando o nome do ouvinte do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="5747b-104">For transactional replication push subscribers, the distribution agent will continue to replicate automatically after a failover if the subscription was created using the AG listener name.</span></span> <span data-ttu-id="5747b-105">Para assinantes por pull de replicação transacional, o agente de distribuição continuará a replicar automaticamente após um failover se a assinatura tiver sido criada usando o nome do ouvinte do grupo de disponibilidade e o servidor original do assinante estiver em execução.</span><span class="sxs-lookup"><span data-stu-id="5747b-105">For transactional replication pull subscribers, the distribution agent will continue to replicate automatically after a failover, if the subscription was created using the AG listener name and the original subscriber server is up and running.</span></span> <span data-ttu-id="5747b-106">Isso ocorre porque os trabalhos de agente de distribuição são criados somente no assinante original (réplica primária do grupo de disponibilidade).</span><span class="sxs-lookup"><span data-stu-id="5747b-106">This is because the distribution agent jobs only get created on the original subscriber (primary replica of the AG).</span></span> <span data-ttu-id="5747b-107">Para mesclar assinantes, um administrador de replicação deve reconfigurar o assinante manualmente, recriando a assinatura.</span><span class="sxs-lookup"><span data-stu-id="5747b-107">For merge subscribers, a replication administrator must manually reconfigure the subscriber, by recreating the subscription.</span></span>  
  
## <a name="what-is-supported"></a><span data-ttu-id="5747b-108">O que tem suporte</span><span class="sxs-lookup"><span data-stu-id="5747b-108">What is Supported</span></span>  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="5747b-109">oferece suporte ao failover automático do publicador, ao failover automático dos assinantes transacionais e ao failover manual dos assinantes de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="5747b-109">replication supports the automatic failover of the publisher, the automatic failover of transactional subscribers, and the manual failover of merge subscribers.</span></span> <span data-ttu-id="5747b-110">Não há suporte para o failover de um distribuidor em um banco de dados de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="5747b-110">The failover of a distributor on an availability database is not supported.</span></span> <span data-ttu-id="5747b-111">AlwaysOn não pode ser combinado com cenários Websync e [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="5747b-111">AlwaysOn cannot be combined with Websync and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Compact scenarios.</span></span>  
  
 <span data-ttu-id="5747b-112">**Failover de uma assinatura pull de mesclagem**</span><span class="sxs-lookup"><span data-stu-id="5747b-112">**Failover of a Merge Pull Subscription**</span></span>  
  
 <span data-ttu-id="5747b-113">Uma assinatura pull apresenta falha após o failover do grupo de disponibilidade porque o agente de pull não pode localizar os trabalhos armazenados no banco de dados **msdb** da instância de servidor que hospeda a réplica primária, que não está disponível porque a instância do servidor apresentou falha.</span><span class="sxs-lookup"><span data-stu-id="5747b-113">A pull subscription fails upon availability group failover, because pull agent cannot find the jobs stored in the **msdb** database of the server instance that hosts the primary replica; which is not available because the server instance has failed.</span></span>  
  
 <span data-ttu-id="5747b-114">**Failover de uma assinatura push de mesclagem**</span><span class="sxs-lookup"><span data-stu-id="5747b-114">**Failover of a Merge Push Subscription**</span></span>  
  
 <span data-ttu-id="5747b-115">Uma assinatura push apresenta falha após o failover do grupo de disponibilidade porque o agente de push não pode mais se conectar ao banco de dados de assinatura original no assinante original.</span><span class="sxs-lookup"><span data-stu-id="5747b-115">A push subscription fails upon availability group failover, because the push agent can no longer connect to original subscription database on original subscriber.</span></span>  
  
## <a name="how-to-create-transactional-subscription-in-an-alwayson-environment"></a><span data-ttu-id="5747b-116">Como criar uma assinatura transacional em um ambiente AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="5747b-116">How to Create Transactional Subscription in an AlwaysOn Environment</span></span>  
 <span data-ttu-id="5747b-117">Para a replicação transacional, use as seguintes etapas para configurar e fazer o failover de um grupo de disponibilidade do assinante:</span><span class="sxs-lookup"><span data-stu-id="5747b-117">For transactional replication, use the following steps to configure and failover a subscriber availability group:</span></span>  
  
1.  <span data-ttu-id="5747b-118">Antes de criar a assinatura, adicione o banco de dados do assinante ao grupo de disponibilidade AlwaysOn apropriado.</span><span class="sxs-lookup"><span data-stu-id="5747b-118">Before creating the subscription, add the subscriber database to the appropriate AlwaysOn availability group.</span></span>  
  
2.  <span data-ttu-id="5747b-119">Adicione o ouvinte do grupo de disponibilidade do assinante como um servidor vinculado para todos os nós do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="5747b-119">Add the subscriber's availability group Listener as a linked server to all nodes of the availability group.</span></span> <span data-ttu-id="5747b-120">Essa etapa garante que todos os parceiros de failover potenciais estejam cientes de e possam se conectar ao ouvinte.</span><span class="sxs-lookup"><span data-stu-id="5747b-120">This step ensures that all potential failover partners are aware of and can connect to the listener.</span></span>  
  
3.  <span data-ttu-id="5747b-121">Usando o script da seção abaixo **Criando uma assinatura push de replicação transacional** , crie a assinatura usando o nome do ouvinte de grupo de disponibilidade do assinante.</span><span class="sxs-lookup"><span data-stu-id="5747b-121">Using the script in the **Creating a Transactional Replication Push Subscription** section below, create the subscription using the name of the availability group listener of the subscriber.</span></span> <span data-ttu-id="5747b-122">Depois de um failover, o nome do ouvinte sempre permanecerá válido, enquanto que o nome de servidor real do assinante dependerá do nó real que se tornou o novo primário.</span><span class="sxs-lookup"><span data-stu-id="5747b-122">After a failover, the listener name will always remain valid, whereas the actual server name of the subscriber will depend on the actual node that became the new primary.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5747b-123">A assinatura deve ser criada usando um script [!INCLUDE[tsql](../../../includes/tsql-md.md)] e não pode ser criada usando o [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5747b-123">The subscription must be created by using a [!INCLUDE[tsql](../../../includes/tsql-md.md)] script and cannot be created using [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].</span></span>  
  
4.  <span data-ttu-id="5747b-124">Se estiver criando uma assinatura pull:</span><span class="sxs-lookup"><span data-stu-id="5747b-124">If creating a pull subscription:</span></span>  
  
    1.  <span data-ttu-id="5747b-125">No [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], no nó primário do assinante, abra a árvore do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="5747b-125">In [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], on the primary subscriber node, open the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent tree.</span></span>  
  
    2.  <span data-ttu-id="5747b-126">Identifique o trabalho do **Agente de Distribuição de Pull** e edite o trabalho.</span><span class="sxs-lookup"><span data-stu-id="5747b-126">Identify the **Pull Distribution Agent** job and edit the job.</span></span>  
  
    3.  <span data-ttu-id="5747b-127">Na etapa de trabalho **Executar Agente** , verifique os parâmetros `-Publisher` e `-Distributor` .</span><span class="sxs-lookup"><span data-stu-id="5747b-127">On the **Run Agent** job step, check the `-Publisher` and `-Distributor` parameters.</span></span> <span data-ttu-id="5747b-128">Verifique se esses parâmetros contêm os nomes diretos do servidor e a instância corretos do servidor do publicador e do distribuidor.</span><span class="sxs-lookup"><span data-stu-id="5747b-128">Make sure that these parameters contain the correct direct server and instance names of the publisher and distributor server.</span></span>  
  
    4.  <span data-ttu-id="5747b-129">Altere o parâmetro `-Subscriber` para o nome do ouvinte do grupo de disponibilidade do assinante.</span><span class="sxs-lookup"><span data-stu-id="5747b-129">Change the `-Subscriber` parameter to the subscriber's availability group listener name.</span></span>  
  
 <span data-ttu-id="5747b-130">Quando você cria sua assinatura seguindo essas etapas, não precisa fazer nada após um failover.</span><span class="sxs-lookup"><span data-stu-id="5747b-130">When you create your subscription following these steps, then you won't have to do anything after a failover.</span></span>  
  
## <a name="creating-a-transactional-replication-push-subscription"></a><span data-ttu-id="5747b-131">Criando uma assinatura push de replicação transacional</span><span class="sxs-lookup"><span data-stu-id="5747b-131">Creating a Transactional Replication Push Subscription</span></span>  
  
```  
-- commands to execute at the publisher, in the publisher database:  
use [<publisher database name>]  
EXEC sp_addsubscription @publication = N'<publication name>',   
       @subscriber = N'<availability group listener name>',   
       @destination_db = N'<subscriber database name>',   
       @subscription_type = N'Push',   
       @sync_type = N'automatic', @article = N'all', @update_mode = N'read only', @subscriber_type = 0;  
GO  
  
EXEC sp_addpushsubscription_agent @publication = N'<publication name>',   
       @subscriber = N'<availability group listener name>',   
       @subscriber_db = N'<subscriber database name>',   
       @job_login = null, @job_password = null, @subscriber_security_mode = 1;  
GO  
```  
  
## <a name="to-resume-the-merge-agents-after-the-availability-group-of-the-subscriber-fails-over"></a><span data-ttu-id="5747b-132">Para retomar os Agentes de Mesclagem após o failover do grupo de disponibilidade do assinante</span><span class="sxs-lookup"><span data-stu-id="5747b-132">To Resume the Merge Agents After the Availability Group of the Subscriber Fails Over</span></span>  
 <span data-ttu-id="5747b-133">Para a replicação de mesclagem, um administrador de replicação deve reconfigurar o assinante manualmente com as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="5747b-133">For merge replication, a replication administrator must manually reconfigure the subscriber with the following steps:</span></span>  
  
1.  <span data-ttu-id="5747b-134">Execute `sp_subscription_cleanup` para remover a assinatura antiga para o assinante.</span><span class="sxs-lookup"><span data-stu-id="5747b-134">Execute `sp_subscription_cleanup` to remove the old subscription for the subscriber.</span></span> <span data-ttu-id="5747b-135">Execute esta ação na nova réplica primária (a antiga réplica secundária).</span><span class="sxs-lookup"><span data-stu-id="5747b-135">Perform this action on the new primary replica (which was formerly the secondary replica).</span></span>  
  
2.  <span data-ttu-id="5747b-136">Recrie a assinatura criando uma nova assinatura, começando por um novo instantâneo.</span><span class="sxs-lookup"><span data-stu-id="5747b-136">Recreate the subscription by creating a new subscription, beginning with a new snapshot.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5747b-137">O processo atual é inconveniente para assinantes de replicação de mesclagem; entretanto, o cenário principal para a replicação de mesclagem é de usuários desconectados (áreas de trabalho, laptops, dispositivos de fone) que não usarão grupos de disponibilidade AlwaysOn no assinante.</span><span class="sxs-lookup"><span data-stu-id="5747b-137">The current process is inconvenient for merge replication subscribers, however the main scenario for merge replication is disconnected users (desktops, laptops, handset devices) which will not use AlwaysOn availability groups on the subscriber.</span></span>  
  
  
