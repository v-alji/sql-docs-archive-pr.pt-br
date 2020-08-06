---
title: Desabilitar publicação e distribuição | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- disabling publishing
- publishing [SQL Server replication], disabling
- distribution disabling [SQL Server replication]
- removing replication
- replication [SQL Server], removing
- disabling replication
- disabling distribution
ms.assetid: 6d4a1474-4d13-4826-8be2-80050fafa8a5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8843dac310d1e023fe7ce63eded02c9e1bed3731
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569930"
---
# <a name="disable-publishing-and-distribution"></a><span data-ttu-id="71f93-102">Desabilitar publicação e distribuição</span><span class="sxs-lookup"><span data-stu-id="71f93-102">Disable Publishing and Distribution</span></span>
  <span data-ttu-id="71f93-103">Este tópico descreve como desabilitar a publicação e a distribuição no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], o [!INCLUDE[tsql](../../includes/tsql-md.md)]ou o RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="71f93-103">This topic describes how to disable publishing and distribution in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="71f93-104">É possível fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="71f93-104">You can do the following:</span></span>  
  
-   <span data-ttu-id="71f93-105">Excluir todos os bancos de dados de distribuição no Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="71f93-105">Delete all distribution databases on the Distributor.</span></span>  
  
-   <span data-ttu-id="71f93-106">Desabilitar todos os Publicadores que usam o Distribuidor e excluir todas as publicações nesses Publicadores.</span><span class="sxs-lookup"><span data-stu-id="71f93-106">Disable all Publishers that use the Distributor and delete all publications on those Publishers.</span></span>  
  
-   <span data-ttu-id="71f93-107">Excluir todas as assinaturas para as publicações.</span><span class="sxs-lookup"><span data-stu-id="71f93-107">Delete all subscriptions to the publications.</span></span> <span data-ttu-id="71f93-108">Os dados nos bancos de dados de publicação e de assinatura não serão excluídos, porém, eles perdem a sua relação de sincronização com qualquer banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="71f93-108">Data in the publication and subscription databases will not be deleted; however, it loses its synchronization relationship to any publication databases.</span></span> <span data-ttu-id="71f93-109">Se quiser que os dados no Assinante sejam excluídos, eles deverão ser excluídos manualmente.</span><span class="sxs-lookup"><span data-stu-id="71f93-109">If you want the data at the Subscriber to be deleted, you must delete it manually.</span></span>  
  
 <span data-ttu-id="71f93-110">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="71f93-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="71f93-111">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="71f93-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="71f93-112">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="71f93-112">Prerequisites</span></span>](#Prerequisites)  
  
-   <span data-ttu-id="71f93-113">**Para desabilitar a publicação e a distribuição, usando:**</span><span class="sxs-lookup"><span data-stu-id="71f93-113">**To disable publishing and distribution, using:**</span></span>  
  
     [<span data-ttu-id="71f93-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="71f93-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="71f93-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="71f93-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="71f93-116">RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="71f93-116">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="71f93-117">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="71f93-117">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="71f93-118">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="71f93-118">Prerequisites</span></span>  
  
-   <span data-ttu-id="71f93-119">Para desabilitar a publicação e a distribuição, todos os bancos de dados de distribuição e publicação devem estar online.</span><span class="sxs-lookup"><span data-stu-id="71f93-119">To disable publishing and distribution, all distribution and publication databases must be online.</span></span> <span data-ttu-id="71f93-120">Se quaisquer *instantâneos de banco de dados* existirem para os bancos de dados de distribuição ou de publicação, eles devem ser descartados antes de desabilitar a publicação e a distribuição.</span><span class="sxs-lookup"><span data-stu-id="71f93-120">If any *database snapshots* exist for distribution or publication databases, they must be dropped before disabling publishing and distribution.</span></span> <span data-ttu-id="71f93-121">O instantâneo do banco de dados é uma cópia offline somente leitura de um banco de dados e não está relacionado a nenhum instantâneo de replicação.</span><span class="sxs-lookup"><span data-stu-id="71f93-121">A database snapshot is a read-only offline copy of a database and is not related to a replication snapshot.</span></span> <span data-ttu-id="71f93-122">Para obter mais informações, consulte [Instantâneos de banco de dados &#40;SQL Server&#41;](../databases/database-snapshots-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="71f93-122">For more information, see [Database Snapshots &#40;SQL Server&#41;](../databases/database-snapshots-sql-server.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="71f93-123">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="71f93-123">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="71f93-124">Desabilite a publicação e a distribuição usando o Assistente para Desabilitar Publicação e Distribuição.</span><span class="sxs-lookup"><span data-stu-id="71f93-124">Disable publishing and distribution by using the Disable Publishing and Distribution Wizard.</span></span>  
  
#### <a name="to-disable-publishing-and-distribution"></a><span data-ttu-id="71f93-125">Para desabilitar a publicação e a distribuição</span><span class="sxs-lookup"><span data-stu-id="71f93-125">To disable publishing and distribution</span></span>  
  
1.  <span data-ttu-id="71f93-126">Conecte-se ao Publicador ou Distribuidor que você quer desabilitar no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e então expanda o nó de servidor.</span><span class="sxs-lookup"><span data-stu-id="71f93-126">Connect to the Publisher or Distributor you want to disable in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="71f93-127">Clique com o botão direito do mouse na pasta **Replicação** e, então, clique em **Desabilitar Publicação e Distribuição**.</span><span class="sxs-lookup"><span data-stu-id="71f93-127">Right-click the **Replication** folder, and then click **Disable Publishing and Distribution**.</span></span>  
  
3.  <span data-ttu-id="71f93-128">Complete as etapas no Assistente para Desabilitar Publicação e Distribuição.</span><span class="sxs-lookup"><span data-stu-id="71f93-128">Complete the steps in the Disable Publishing and Distribution Wizard.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="71f93-129">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="71f93-129">Using Transact-SQL</span></span>  
 <span data-ttu-id="71f93-130">A publicação e a distribuição podem ser desabilitadas programaticamente usando procedimentos armazenados de replicação.</span><span class="sxs-lookup"><span data-stu-id="71f93-130">Publishing and distributing can be disabled programmatically using replication stored procedures.</span></span>  
  
#### <a name="to-disable-publishing-and-distribution"></a><span data-ttu-id="71f93-131">Para desabilitar a publicação e a distribuição</span><span class="sxs-lookup"><span data-stu-id="71f93-131">To disable publishing and distribution</span></span>  
  
1.  <span data-ttu-id="71f93-132">Pare todos os trabalhos relacionados a replicação.</span><span class="sxs-lookup"><span data-stu-id="71f93-132">Stop all replication-related jobs.</span></span> <span data-ttu-id="71f93-133">Para uma relação de nomes de trabalho, consulte a seção "Segurança do Agente sob o SQL Server Agent" do [Modelo de Segurança do Agente de Replicação](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="71f93-133">For a list of job names, see the "Agent Security Under SQL Server Agent" section of [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
2.  <span data-ttu-id="71f93-134">Em cada Assinante do banco de dados de assinatura, execute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) para remover objetos de replicação do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="71f93-134">At each Subscriber on the subscription database, execute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) to remove replication objects from the database.</span></span> <span data-ttu-id="71f93-135">Esse procedimento armazenado não removerá trabalhos de replicação no Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="71f93-135">This stored procedure will not remove replication jobs at the Distributor.</span></span>  
  
3.  <span data-ttu-id="71f93-136">No Publicador do banco de dados de publicação, execute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) para remover objetos de replicação do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="71f93-136">At the Publisher on the publication database, execute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) to remove replication objects from the database.</span></span>  
  
4.  <span data-ttu-id="71f93-137">Se o Publicador usar um Distribuidor remoto, execute [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="71f93-137">If the Publisher uses a remote Distributor, execute [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql).</span></span>  
  
5.  <span data-ttu-id="71f93-138">No Distribuidor, execute [sp_dropdistpublisher](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="71f93-138">At the Distributor, execute [sp_dropdistpublisher](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql).</span></span> <span data-ttu-id="71f93-139">Esse procedimento armazenado deverá ser executado uma vez para cada Publicador registrado no Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="71f93-139">This stored procedure should be run once for each Publisher registered at the Distributor.</span></span>  
  
6.  <span data-ttu-id="71f93-140">No Distribuidor, execute [sp_dropdistributiondb](/sql/relational-databases/system-stored-procedures/sp-dropdistributiondb-transact-sql) para excluir o banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="71f93-140">At the Distributor, execute [sp_dropdistributiondb](/sql/relational-databases/system-stored-procedures/sp-dropdistributiondb-transact-sql) to delete the distribution database.</span></span> <span data-ttu-id="71f93-141">Esse procedimento armazenado deverá ser executado uma vez para cada banco de dados de distribuição no Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="71f93-141">This stored procedure should be run once for each distribution database at the Distributor.</span></span> <span data-ttu-id="71f93-142">Isto também removerá qualquer trabalho do Queue Reader Agent associado com o banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="71f93-142">This also removes any Queue Reader Agent jobs associated with the distribution database.</span></span>  
  
7.  <span data-ttu-id="71f93-143">No Distribuidor, execute [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql) para remover a designação Distribuidor do servidor.</span><span class="sxs-lookup"><span data-stu-id="71f93-143">At the Distributor, execute [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql) to remove the Distributor designation from the server.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="71f93-144">Se todos os objetos de publicação e distribuição não forem descartados antes que você execute [sp_dropdistpublisher](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql) e [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql), estes procedimentos retornarão com um erro.</span><span class="sxs-lookup"><span data-stu-id="71f93-144">If all replication publishing and distribution objects are not dropped before you execute [sp_dropdistpublisher](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql) and [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql), these procedures will return an error.</span></span> <span data-ttu-id="71f93-145">Para descartar todos os objetos relacionados à replicação quando um Publicador ou distribuidor é Descartado, o parâmetro \*\* \@ no_checks\*\* deve ser definido como **1**.</span><span class="sxs-lookup"><span data-stu-id="71f93-145">To drop all replication-related objects when a Publisher or Distributor is dropped, the **\@no_checks** parameter must be set to **1**.</span></span> <span data-ttu-id="71f93-146">Se um Publicador ou distribuidor estiver offline ou inacessível, o parâmetro \*\* \@ ignore_distributor\*\* poderá ser definido como **1** para que eles possam ser descartados; no entanto, qualquer objeto de publicação e de distribuição deixado para trás deve ser removido manualmente.</span><span class="sxs-lookup"><span data-stu-id="71f93-146">If a Publisher or Distributor is offline or unreachable, the **\@ignore_distributor** parameter can be set to **1** so that they can be dropped; however, any publishing and distributing objects left behind must be removed manually.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="71f93-147">Exemplos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="71f93-147">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="71f93-148">Este script de exemplo remove objetos de replicação do banco de dados de assinatura.</span><span class="sxs-lookup"><span data-stu-id="71f93-148">This example script removes replication objects from the subscription database.</span></span>  
  
 [!code-sql[HowTo#sp_removedbreplication](../../snippets/tsql/SQL15/replication/howto/tsql/dropdistpub.sql#sp_removedbreplication)]  
  
 <span data-ttu-id="71f93-149">Esse script de exemplo desabilita a publicação e a distribuição em um servidor que é um Publicador e Distribuidor e descarta o banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="71f93-149">This example script disables publishing and distribution on a server that is a Publisher and Distributor and drops the distribution database.</span></span>  
  
 [!code-sql[HowTo#sp_DropDistPub](../../snippets/tsql/SQL15/replication/howto/tsql/dropdistpub.sql#sp_dropdistpub)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="71f93-150">Usando o RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="71f93-150">Using Replication Management Objects (RMO)</span></span>  
  
#### <a name="to-disable-publishing-and-distribution"></a><span data-ttu-id="71f93-151">Para desabilitar a publicação e a distribuição</span><span class="sxs-lookup"><span data-stu-id="71f93-151">To disable publishing and distribution</span></span>  
  
1.  <span data-ttu-id="71f93-152">Remova todas as assinaturas das publicações que usam o Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="71f93-152">Remove all subscriptions to publications that use the Distributor.</span></span> <span data-ttu-id="71f93-153">Para obter mais informações, consulte [Delete a Pull Subscription](delete-a-pull-subscription.md) e [Delete a Push Subscription](delete-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="71f93-153">For more information, see [Delete a Pull Subscription](delete-a-pull-subscription.md) and [Delete a Push Subscription](delete-a-push-subscription.md).</span></span>  
  
2.  <span data-ttu-id="71f93-154">Se o Publicador e o Distribuidor estiverem no mesmo servidor, remova todas as publicações que usam o Distribuidor e desabilite a publicação em todos os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="71f93-154">Remove all publications that use the Distributor, and disable publishing for all databases if the Publisher and Distributor are on the same server.</span></span> <span data-ttu-id="71f93-155">Para obter mais informações, consulte [Delete a Publication](publish/delete-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="71f93-155">For more information, see [Delete a Publication](publish/delete-a-publication.md).</span></span>  
  
3.  <span data-ttu-id="71f93-156">Crie uma conexão com o Distribuidor usando a classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="71f93-156">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
4.  <span data-ttu-id="71f93-157">Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.DistributionPublisher>.</span><span class="sxs-lookup"><span data-stu-id="71f93-157">Create an instance of the <xref:Microsoft.SqlServer.Replication.DistributionPublisher> class.</span></span> <span data-ttu-id="71f93-158">Especifique a propriedade <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Name%2A> e passe o objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> da etapa 3.</span><span class="sxs-lookup"><span data-stu-id="71f93-158">Specify the <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Name%2A> property, and pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 3.</span></span>  
  
5.  <span data-ttu-id="71f93-159">(Opcional) Chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> para obter as propriedades do objeto e para verificar se o Publicador existe.</span><span class="sxs-lookup"><span data-stu-id="71f93-159">(Optional) Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object and verify that the Publisher exists.</span></span> <span data-ttu-id="71f93-160">Se esse método retornar `false`, o nome do Publicador definido na etapa 4 estava incorreto ou o Publicador não está sendo usado pelo Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="71f93-160">If this method returns `false`, the Publisher name set in step 4 was incorrect or the Publisher is not used by this Distributor.</span></span>  
  
6.  <span data-ttu-id="71f93-161">Chame o método <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="71f93-161">Call the <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Remove%2A> method.</span></span> <span data-ttu-id="71f93-162">Passe um valor de `true` for *Force* se o Publicador e o distribuidor estiverem em servidores diferentes e quando o Publicador for desinstalado no distribuidor sem primeiro verificar se as publicações não existem mais no Publicador.</span><span class="sxs-lookup"><span data-stu-id="71f93-162">Pass a value of `true` for *force* if the Publisher and Distributor are on different servers, and when the Publisher should be uninstalled at the Distributor without first verifying that publications no longer exist at the Publisher.</span></span>  
  
7.  <span data-ttu-id="71f93-163">Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.ReplicationServer>.</span><span class="sxs-lookup"><span data-stu-id="71f93-163">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span> <span data-ttu-id="71f93-164">Passe o objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> da etapa 3.</span><span class="sxs-lookup"><span data-stu-id="71f93-164">Pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 3.</span></span>  
  
8.  <span data-ttu-id="71f93-165">Chame o método <xref:Microsoft.SqlServer.Replication.ReplicationServer.UninstallDistributor%2A> .</span><span class="sxs-lookup"><span data-stu-id="71f93-165">Call the <xref:Microsoft.SqlServer.Replication.ReplicationServer.UninstallDistributor%2A> method.</span></span> <span data-ttu-id="71f93-166">Passe um valor de `true` for *Force* para remover todos os objetos de replicação no distribuidor, sem primeiro verificar se todos os bancos de dados de publicação local foram desabilitados e se os bancos de dados de distribuição foram desinstalados.</span><span class="sxs-lookup"><span data-stu-id="71f93-166">Pass a value of `true` for *force* to remove all replication objects at the Distributor without first verifying that all local publication databases have been disabled, and distribution databases have been uninstalled.</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="71f93-167">Exemplos (RMO)</span><span class="sxs-lookup"><span data-stu-id="71f93-167">Examples (RMO)</span></span>  
 <span data-ttu-id="71f93-168">Esse exemplo remove o registro do Publicador no Distribuidor, descarta o banco de dados de distribuição e desinstala o Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="71f93-168">This example removes the Publisher registration at the Distributor, drops the distribution database, and uninstalls the Distributor.</span></span>  
  
 [!code-csharp[HowTo#rmo_DropDistPub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_dropdistpub)]  
  
 [!code-vb[HowTo#rmo_vb_DropDistPub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_dropdistpub)]  
  
 <span data-ttu-id="71f93-169">Esse exemplo desinstala o Distribuidor sem desabilitar primeiro os bancos de dados de publicação locais ou descartar o banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="71f93-169">This example uninstalls the Distributor without first disabling local publication databases or dropping the distribution database.</span></span>  
  
 [!code-csharp[HowTo#rmo_DropDistPubForce](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_dropdistpubforce)]  
  
 [!code-vb[HowTo#rmo_vb_DropDistPubForce](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_dropdistpubforce)]  
  
## <a name="see-also"></a><span data-ttu-id="71f93-170">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="71f93-170">See Also</span></span>  
 <span data-ttu-id="71f93-171">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="71f93-171">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span></span>  
 [<span data-ttu-id="71f93-172">Replication System Stored Procedures Concepts</span><span class="sxs-lookup"><span data-stu-id="71f93-172">Replication System Stored Procedures Concepts</span></span>](concepts/replication-system-stored-procedures-concepts.md)  
  
  
