---
title: Remover o envio de logs (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], removing
- removing log shipping
- deleting log shipping
ms.assetid: 859373db-c744-4a4b-8479-45163f61e8cb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 14fdc36c66073e89dcc2014aed4319a2ce78a98f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574251"
---
# <a name="remove-log-shipping-sql-server"></a><span data-ttu-id="60d30-102">Remover envio de log (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="60d30-102">Remove Log Shipping (SQL Server)</span></span>
  <span data-ttu-id="60d30-103">Este tópico descreve como remover o envio de logs no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60d30-103">This topic describes how to remove log shipping in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="60d30-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="60d30-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="60d30-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="60d30-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="60d30-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="60d30-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="60d30-107">**Para remover envio de log, usando:**</span><span class="sxs-lookup"><span data-stu-id="60d30-107">**To remove log shipping, using:**</span></span>  
  
     [<span data-ttu-id="60d30-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="60d30-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="60d30-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="60d30-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="60d30-110">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="60d30-110">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="60d30-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="60d30-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="60d30-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="60d30-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="60d30-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="60d30-113">Permissions</span></span>  
 <span data-ttu-id="60d30-114">Os procedimentos armazenados de envio de logs exigem a associação à função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="60d30-114">The log-shipping stored procedures require membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="60d30-115">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="60d30-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-log-shipping"></a><span data-ttu-id="60d30-116">Para remover envio de logs</span><span class="sxs-lookup"><span data-stu-id="60d30-116">To remove log shipping</span></span>  
  
1.  <span data-ttu-id="60d30-117">Conecte à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que é no momento o servidor primário para envio de logs e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="60d30-117">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is currently the log shipping primary server and expand that instance.</span></span>  
  
2.  <span data-ttu-id="60d30-118">Expanda **Bancos de Dados**, clique com o botão direito do mouse no banco de dados primário de envio de logs e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="60d30-118">Expand **Databases**, right-click the log shipping primary database, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="60d30-119">Em **Selecionar uma página**, clique em **Envio do Log de Transações**.</span><span class="sxs-lookup"><span data-stu-id="60d30-119">Under **Select a page**, click **Transaction Log Shipping**.</span></span>  
  
4.  <span data-ttu-id="60d30-120">Desmarque a caixa de seleção **Habilite isto como banco de dados primário em uma configuração de envio de logs** .</span><span class="sxs-lookup"><span data-stu-id="60d30-120">Clear the **Enable this as a primary database in a log shipping configuration** check box.</span></span>  
  
5.  <span data-ttu-id="60d30-121">Clique em **OK** para remover o envio de logs deste banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="60d30-121">Click **OK** to remove log shipping from this primary database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="60d30-122">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="60d30-122">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-log-shipping"></a><span data-ttu-id="60d30-123">Para remover envio de logs</span><span class="sxs-lookup"><span data-stu-id="60d30-123">To Remove Log Shipping</span></span>  
  
1.  <span data-ttu-id="60d30-124">No servidor primário de envio de logs, execute [sp_delete_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-primary-secondary-transact-sql) para excluir as informações sobre o banco de dados secundário do servidor primário.</span><span class="sxs-lookup"><span data-stu-id="60d30-124">On the log shipping primary server, execute [sp_delete_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-primary-secondary-transact-sql) to delete the information about the secondary database from the primary server.</span></span>  
  
2.  <span data-ttu-id="60d30-125">No servidor secundário de envio de logs, execute [sp_delete_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-secondary-database-transact-sql) para excluir o banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="60d30-125">On the log shipping secondary server, execute [sp_delete_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-secondary-database-transact-sql) to delete the secondary database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="60d30-126">Se não houver outro banco de dados secundário com a mesma ID secundária, **sp_delete_log_shipping_secondary_primary** será invocado de **sp_delete_log_shipping_secondary_database** e excluirá a entrada da ID secundária e os trabalhos de cópia e restauração.</span><span class="sxs-lookup"><span data-stu-id="60d30-126">If there are no other secondary databases with the same secondary ID, **sp_delete_log_shipping_secondary_primary** is invoked from **sp_delete_log_shipping_secondary_database** and deletes the entry for the secondary ID and the copy and restore jobs.</span></span>  
  
3.  <span data-ttu-id="60d30-127">No servidor primário de envio de logs, execute **sp_delete_log_shipping_primary_database** para excluir informações sobre a configuração de envio do log no servidor primário.</span><span class="sxs-lookup"><span data-stu-id="60d30-127">On the log shipping primary server, execute **sp_delete_log_shipping_primary_database** to delete information about the log shipping configuration from the primary server.</span></span> <span data-ttu-id="60d30-128">Isso também exclui a tarefa de backup.</span><span class="sxs-lookup"><span data-stu-id="60d30-128">This also deletes the backup job.</span></span>  
  
4.  <span data-ttu-id="60d30-129">No servidor primário para envio de logs, desabilite o trabalho de backup.</span><span class="sxs-lookup"><span data-stu-id="60d30-129">On the log shipping primary server, disable the backup job.</span></span> <span data-ttu-id="60d30-130">Para obter mais informações, consulte [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="60d30-130">For more information, see [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span></span>  
  
5.  <span data-ttu-id="60d30-131">No servidor secundário para envio de logs, desabilite os trabalhos de cópia e restauração.</span><span class="sxs-lookup"><span data-stu-id="60d30-131">On the log shipping secondary server, disable the copy and restore jobs.</span></span>  
  
6.  <span data-ttu-id="60d30-132">Como opção, se você já não estiver usando o banco de dados secundário para envio de logs, poderá excluí-lo do servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="60d30-132">Optionally, if you are no longer using the log shipping secondary database, you can delete it from the secondary server.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="60d30-133">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="60d30-133">Related Tasks</span></span>  
  
-   [<span data-ttu-id="60d30-134">Atualizar o envio de logs para SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="60d30-134">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="60d30-135">Configurar o envio de logs &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="60d30-135">Configure Log Shipping &#40;SQL Server&#41;</span></span>](configure-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="60d30-136">Adicionar um banco de dados secundário a uma configuração de envio de logs &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="60d30-136">Add a Secondary Database to a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](add-a-secondary-database-to-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="60d30-137">Remover um banco de dados secundário de uma configuração de envio de logs &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="60d30-137">Remove a Secondary Database from a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="60d30-138">Monitorar o envio de logs &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="60d30-138">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="60d30-139">Executar failover para um secundário de envio de logs &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="60d30-139">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
-   [<span data-ttu-id="60d30-140">Disable or Enable a Job</span><span class="sxs-lookup"><span data-stu-id="60d30-140">Disable or Enable a Job</span></span>](../../ssms/agent/disable-or-enable-a-job.md)  
  
## <a name="see-also"></a><span data-ttu-id="60d30-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="60d30-141">See Also</span></span>  
 <span data-ttu-id="60d30-142">[Sobre o envio de logs &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="60d30-142">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="60d30-143">Tabelas de envio de log e procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="60d30-143">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
