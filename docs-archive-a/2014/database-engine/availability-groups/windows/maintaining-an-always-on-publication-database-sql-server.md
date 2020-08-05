---
title: Mantendo um banco de dados de publicação AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], interoperability
- replication [SQL Server], AlwaysOn Availability Groups
ms.assetid: 55b345fe-2eb9-4b04-a900-63d858eec360
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e8f36d29049140b6e5bbdfc1a4e716d41a766a06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573268"
---
# <a name="maintaining-an-alwayson-publication-database-sql-server"></a><span data-ttu-id="40c20-102">Mantendo um banco de dados de publicação AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="40c20-102">Maintaining an AlwaysOn Publication Database (SQL Server)</span></span>
  <span data-ttu-id="40c20-103">Este tópico discute considerações especiais para manter um banco de dados de publicação quando você usa grupos de disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="40c20-103">This topic discusses special considerations for maintaining a publication database when you use AlwaysOn availability groups.</span></span>  
  
 
  
##  <a name="maintaining-a-published-database-in-an-availability-group"></a><a name="MaintainPublDb"></a><span data-ttu-id="40c20-104">Mantendo um banco de dados publicado em um grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="40c20-104">Maintaining a Published Database in an Availability Group</span></span>  
 <span data-ttu-id="40c20-105">Manter um banco de dados de publicação AlwaysOn é basicamente o mesmo que manter um banco de dados de publicação padrão, com as seguintes considerações:</span><span class="sxs-lookup"><span data-stu-id="40c20-105">Maintaining an AlwaysOn publication database is basically the same as maintaining a standard publication database, with the following considerations:</span></span>  
  
-   <span data-ttu-id="40c20-106">A administração deve ocorrer no host de réplica primária.</span><span class="sxs-lookup"><span data-stu-id="40c20-106">Administration must occur at the primary replica host.</span></span> <span data-ttu-id="40c20-107">No [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], as publicações aparecem sob a pasta **Publicações Locais** para o host de réplica primária e também para réplicas secundárias legíveis.</span><span class="sxs-lookup"><span data-stu-id="40c20-107">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], publications appear under the **Local Publications** folder for the primary replica host and also for readable secondary replicas.</span></span> <span data-ttu-id="40c20-108">Depois do failover, talvez você precise atualizar manualmente o [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] para que a alteração seja refletida se a réplica secundária elevada a primária não estiver legível.</span><span class="sxs-lookup"><span data-stu-id="40c20-108">After failover, you might have to manually refresh [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] for the change to be reflected if the secondary that was promoted to primary was not readable.</span></span>  
  
-   <span data-ttu-id="40c20-109">O monitor de replicação sempre exibe informações de publicação sob o publicador original.</span><span class="sxs-lookup"><span data-stu-id="40c20-109">Replication Monitor always displays publication information under the original publisher.</span></span> <span data-ttu-id="40c20-110">Entretanto, estas informações podem ser exibidas no Monitor de Replicação de qualquer réplica, adicionando o publicador original como um servidor.</span><span class="sxs-lookup"><span data-stu-id="40c20-110">However, this information can be viewed in Replication Monitor from any replica by adding the original publisher as a server.</span></span>  
  
-   <span data-ttu-id="40c20-111">Ao usar os procedimentos armazenados ou RMO (Replication Management Objects) para gerenciar na réplica primária atual, nos casos em que você especifica o nome do Publicador, especifique o nome da instância na qual o banco de dados foi habilitado para a replicação (o publicador original).</span><span class="sxs-lookup"><span data-stu-id="40c20-111">When using stored procedures or Replication Management Objects (RMO) to administer replication at the current primary, for cases in which you specify the Publisher name, you must specify the name of the instance on which the database was enabled for replication (the original publisher).</span></span> <span data-ttu-id="40c20-112">Para determinar o nome apropriado, use a função `PUBLISHINGSERVERNAME`.</span><span class="sxs-lookup"><span data-stu-id="40c20-112">To determine the appropriate name, use the `PUBLISHINGSERVERNAME` function.</span></span> <span data-ttu-id="40c20-113">Quando um banco de dados de publicação ingressa em um grupo de disponibilidade, os metadados de replicação armazenados nas réplicas de banco de dados secundárias são idênticos aos da réplica primária.</span><span class="sxs-lookup"><span data-stu-id="40c20-113">When a publishing database joins an availability group, the replication metadata stored in the secondary database replicas is identical to that at the primary.</span></span> <span data-ttu-id="40c20-114">Portanto, para os bancos de dados de publicação habilitados para replicação na réplica primária, o nome da instância do publicador armazenado em tabelas do sistema na réplica secundária é o nome da réplica primária, e não da secundária.</span><span class="sxs-lookup"><span data-stu-id="40c20-114">Consequently, for publication databases enabled for replication at the primary, the publisher instance name stored in system tables at the secondary is the name of the primary, not the secondary.</span></span> <span data-ttu-id="40c20-115">Isso afeta a configuração e a manutenção da replicação, em caso de falha do banco de dados de publicação para uma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="40c20-115">This affects replication configuration and maintenance if the publication database fails over to a secondary.</span></span> <span data-ttu-id="40c20-116">Por exemplo, se você estiver configurando a replicação com procedimentos armazenados em um secundário após o failover e quiser uma assinatura pull para um banco de dados de publicação que foi habilitado em uma réplica diferente, deverá especificar o nome do Publicador original em vez do Publicador atual como o *@publisher* parâmetro de `sp_addpullsubscription` ou `sp_addmergepulllsubscription` .</span><span class="sxs-lookup"><span data-stu-id="40c20-116">For example, if you are configuring replication with stored procedures at a secondary after failover, and you want a pull subscription to a publication database that was enabled at a different replica, you must specify the name of the original publisher instead of the current publisher as the *@publisher* parameter of `sp_addpullsubscription` or `sp_addmergepulllsubscription`.</span></span> <span data-ttu-id="40c20-117">Entretanto, se você habilitar um banco de dados de publicação depois do failover, o nome de instância de publicador armazenado nas tabelas do sistema será o nome do host primário atual.</span><span class="sxs-lookup"><span data-stu-id="40c20-117">However, if you enable a publication database after failover, the publisher instance name stored in the system tables is the name of the current primary host.</span></span> <span data-ttu-id="40c20-118">Nesse caso, você usaria o nome do host da réplica primária atual para o *@publisher* parâmetro.</span><span class="sxs-lookup"><span data-stu-id="40c20-118">In this case, you would use the host name of the current primary replica for the *@publisher* parameter.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="40c20-119">Para alguns procedimentos, como `sp_addpublication` , o *@publisher* parâmetro tem suporte apenas para Publicadores que não são instâncias do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ; nesses casos, ele não é relevante para o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="40c20-119">For some procedures, such as `sp_addpublication`, the *@publisher* parameter is supported only for publishers that are not instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]; in these cases, it is not relevant for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] AlwaysOn.</span></span>  
  
-   <span data-ttu-id="40c20-120">Para sincronizar uma assinatura no [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] após o failover, sincronize as assinaturas pull do assinante e sincronize as assinaturas push do publicador ativo.</span><span class="sxs-lookup"><span data-stu-id="40c20-120">To synchronize a subscription in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] after a failover, synchronize pull subscriptions from the subscriber and synchronize push subscriptions from the active publisher.</span></span>  
  
##  <a name="removing-a-published-database-from-an-availability-group"></a><a name="RemovePublDb"></a> <span data-ttu-id="40c20-121">Removendo um banco de dados publicado de um grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="40c20-121">Removing a Published Database from an Availability Group</span></span>  
 <span data-ttu-id="40c20-122">Considere os problemas a seguir se um banco de dados publicado for removido de um grupo de disponibilidade, ou se um grupo de disponibilidade que tem um banco de dados de membro publicado for removido.</span><span class="sxs-lookup"><span data-stu-id="40c20-122">Consider the following issues if a published database is removed from an availability group, or if an availability group that has a published member database is dropped.</span></span>  
  
-   <span data-ttu-id="40c20-123">Se o banco de dados de publicação no Publicador original for removido de uma réplica primária do grupo de disponibilidade, você deverá executar `sp_redirect_publisher` sem especificar um valor para o *@redirected_publisher* parâmetro a fim de remover o redirecionamento do par Publicador/banco de dados.</span><span class="sxs-lookup"><span data-stu-id="40c20-123">If the publication database at the original publisher is removed from an availability group primary replica, you must run `sp_redirect_publisher` without specifying a value for the *@redirected_publisher* parameter in order to remove the redirection for the publisher/database pair.</span></span>  
  
    ```  
    EXEC sys.sp_redirect_publisher   
        @original_publisher = 'MyPublisher',  
        @published_database = 'MyPublishedDB';  
    ```  
  
     <span data-ttu-id="40c20-124">O banco de dados será deixado no estado de recuperação na réplica primária e deve ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="40c20-124">The database will be left in the recovering state at the primary and must be restored.</span></span> <span data-ttu-id="40c20-125">Quando você faz isso, a replicação deve funcionar inalterada no Publicador original.</span><span class="sxs-lookup"><span data-stu-id="40c20-125">Once you do this, replication should work unchanged against the original Publisher.</span></span>  
  
-   <span data-ttu-id="40c20-126">Se o banco de dados de publicação falhar no publicador original para uma réplica e o banco de dados for removido da réplica primária de grupo de disponibilidade, use o procedimento armazenado `sp_redirect_publisher` para redirecionar explicitamente o publicador original para o novo publicador.</span><span class="sxs-lookup"><span data-stu-id="40c20-126">If the publication database fails over from the original publisher to a replica and the database is removed from the availability group primary replica, use the stored procedure `sp_redirect_publisher` to explicitly redirect the original publisher to the new publisher.</span></span> <span data-ttu-id="40c20-127">O banco de dados será deixado no estado de recuperação e deverá ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="40c20-127">The database will be left in the recovering state and must be restored.</span></span> <span data-ttu-id="40c20-128">Quando você faz isso, a replicação deve continuar a funcionar como ocorria no grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="40c20-128">Once you do this, replication should continue to work as it did under the availability group.</span></span>  
  
    ```  
    EXEC sys.sp_redirect_publisher   
        @original_publisher = 'MyPublisher',  
        @published_database = 'MyPublishedDB',  
        @redirected_publisher = 'MyNewPublisher';  
    ```  
  
     <span data-ttu-id="40c20-129">Não remova o servidor remoto para o publicador original do distribuidor, mesmo que o servidor não possa mais ser acessado.</span><span class="sxs-lookup"><span data-stu-id="40c20-129">Do not remove the remote server for the original publisher from the distributor, even if the server can no longer be accessed.</span></span> <span data-ttu-id="40c20-130">Os metadados de servidor para o publicador original são necessários no distribuidor para atender consultas de metadados de publicação.</span><span class="sxs-lookup"><span data-stu-id="40c20-130">The server metadata for the original publisher is needed at the distributor to satisfy publication metadata queries.</span></span>  
  
-   <span data-ttu-id="40c20-131">Se um grupo de disponibilidade completo for removido, o comportamento em relação a um banco de dados replicado de membro será igual ao de um banco de dados publicado que é removido de um grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="40c20-131">If a complete availability group is removed, the behavior with regard to a member replicated database is the same as when a published database is removed from an availability group.</span></span> <span data-ttu-id="40c20-132">A replicação poderá ser retomada da réplica primária mais recente assim que o banco de dados for restaurado e o redirecionamento for modificado.</span><span class="sxs-lookup"><span data-stu-id="40c20-132">Replication can be resumed from the last primary as soon as the database has been restored and the redirection has been modified.</span></span> <span data-ttu-id="40c20-133">Se o banco de dados for restaurado em seu publicador original, o redirecionamento deverá ser removido.</span><span class="sxs-lookup"><span data-stu-id="40c20-133">If the database is restored at its original publisher, redirection should be removed.</span></span> <span data-ttu-id="40c20-134">Se o banco de dados for restaurado em um host diferente, o redirecionamento deverá ser direcionado explicitamente ao novo host.</span><span class="sxs-lookup"><span data-stu-id="40c20-134">If the database is restored at a different host, redirection should be explicitly directed to the new host.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="40c20-135">Quando um grupo de disponibilidade que publicou bancos de dados de membro é removido, ou um banco de dados publicado é removido de um grupo de disponibilidade, todas as cópias dos bancos de dados publicados permanecem no estado de recuperação.</span><span class="sxs-lookup"><span data-stu-id="40c20-135">When an availability group is removed that has published member databases, or a published database is removed from an availability group, all copies of the published databases will be left in the recovering state.</span></span> <span data-ttu-id="40c20-136">Se restaurado, cada um aparecerá como um banco de dados publicado.</span><span class="sxs-lookup"><span data-stu-id="40c20-136">If restored, each will appear as a published database.</span></span> <span data-ttu-id="40c20-137">Apenas uma cópia deve ser retida com metadados de publicação.</span><span class="sxs-lookup"><span data-stu-id="40c20-137">Only one copy should be retained with publication metadata.</span></span> <span data-ttu-id="40c20-138">Para desabilitar a replicação para uma cópia de banco de dados publicada, primeiro remova todas as assinaturas e publicações do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="40c20-138">To disable replication for a published database copy, first remove all subscriptions and publications from the database.</span></span>  
  
     <span data-ttu-id="40c20-139">Execute `sp_dropsubscription` para remover assinaturas da publicação.</span><span class="sxs-lookup"><span data-stu-id="40c20-139">Run `sp_dropsubscription` to remove publication subscriptions.</span></span> <span data-ttu-id="40c20-140">Certifique-se de definir o parâmetro *@ignore_distributributor* como 1 para preservar os metadados do banco de dados de publicação ativa no distribuidor.</span><span class="sxs-lookup"><span data-stu-id="40c20-140">Make sure to set the parameter *@ignore_distributributor* to 1 to preserve the metadata for the active publishing database at the distributor.</span></span>  
  
    ```  
    USE MyDBName;  
    GO  
  
    EXEC sys.sp_dropsubscription   
        @subscriber = 'MySubscriber',  
        @publication = 'MyPublication',  
        @article = 'all',  
        @ignore_distributor = 1;  
    ```  
  
     <span data-ttu-id="40c20-141">Execute `sp_droppublication` para remover todas as publicações.</span><span class="sxs-lookup"><span data-stu-id="40c20-141">Run `sp_droppublication` to remove all publications.</span></span> <span data-ttu-id="40c20-142">Novamente, defina o parâmetro *@ignore_distributor* como 1 para preservar os metadados do banco de dados de publicação ativa no distribuidor.</span><span class="sxs-lookup"><span data-stu-id="40c20-142">Again, set the parameter *@ignore_distributor* to 1 to preserve the metadata for the active publishing database at the distributor.</span></span>  
  
    ```  
    EXEC sys.sp_droppublication   
        @publication = 'MyPublication',  
        @ignore_distributor = 1;  
    ```  
  
     <span data-ttu-id="40c20-143">Execute `sp_replicationdboption` para desabilitar a replicação para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="40c20-143">Run `sp_replicationdboption` to disable replication for the database.</span></span>  
  
    ```  
    EXEC sys.sp_replicationdboption  
        @dbname = 'MyDBName',  
        @optname = 'publish',  
        @value = 'false';  
    ```  
  
     <span data-ttu-id="40c20-144">Neste momento, a cópia do banco de dados publicado pode ser retida ou removida.</span><span class="sxs-lookup"><span data-stu-id="40c20-144">At this point, the copy of the published database can be retained or dropped.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="40c20-145">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="40c20-145">Related Tasks</span></span>  
  
-   [<span data-ttu-id="40c20-146">Configurar a replicação para grupos de disponibilidade AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="40c20-146">Configure Replication for AlwaysOn Availability Groups (SQL Server)</span></span>](always-on-availability-groups-sql-server.md)  
  
-   [<span data-ttu-id="40c20-147">Replicação, Controle de Alterações, captura de dados de alteração e Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="40c20-147">Replication, Change Tracking, Change Data Capture, and AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](replicate-track-change-data-capture-always-on-availability.md)  
  
-   [<span data-ttu-id="40c20-148">Perguntas Frequentes sobre Administração de Replicação</span><span class="sxs-lookup"><span data-stu-id="40c20-148">Replication Administration FAQ</span></span>](../../../relational-databases/replication/administration/frequently-asked-questions-for-replication-administrators.md)  
  
-   [<span data-ttu-id="40c20-149">Assinantes de replicação e Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="40c20-149">Replication Subscribers and AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](replication-subscribers-and-always-on-availability-groups-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="40c20-150">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="40c20-150">See Also</span></span>  
 <span data-ttu-id="40c20-151">[Pré-requisitos, restrições e recomendações para Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="40c20-151">[Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span></span>  
 <span data-ttu-id="40c20-152">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="40c20-152">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="40c20-153">[Grupos de Disponibilidade AlwaysOn: interoperabilidade (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="40c20-153">[AlwaysOn Availability Groups: Interoperability (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span></span>  
 [<span data-ttu-id="40c20-154">Replicação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="40c20-154">SQL Server Replication</span></span>](../../../relational-databases/replication/sql-server-replication.md)  
  
  
