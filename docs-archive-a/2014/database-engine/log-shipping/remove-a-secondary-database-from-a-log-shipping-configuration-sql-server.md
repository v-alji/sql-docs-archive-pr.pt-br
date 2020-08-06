---
title: Remover um banco de dados secundário de uma configuração de envio de logs (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- deleting secondary databases
- secondary databases [SQL Server], in log shipping
- removing secondary databases
- secondary data files [SQL Server], removing
- log shipping [SQL Server], secondary databases
ms.assetid: ebe368a4-ca1c-45d0-9a71-3ddbd5b26a8e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 119f2762d41d0787b6b3279507e9671e89fddfca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575320"
---
# <a name="remove-a-secondary-database-from-a-log-shipping-configuration-sql-server"></a><span data-ttu-id="87ac8-102">Remova um banco de dados secundário de uma configuração de envio de logs (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="87ac8-102">Remove a Secondary Database from a Log Shipping Configuration (SQL Server)</span></span>
  <span data-ttu-id="87ac8-103">Este tópico descreve como remover um banco de dados secundário de envio de logs no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87ac8-103">This topic describes how to remove a log shipping secondary database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="87ac8-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="87ac8-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="87ac8-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="87ac8-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="87ac8-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="87ac8-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="87ac8-107">**Para remover um banco de dados secundário de envio de logs, usando:**</span><span class="sxs-lookup"><span data-stu-id="87ac8-107">**To remove a log shipping secondary database, using:**</span></span>  
  
     [<span data-ttu-id="87ac8-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="87ac8-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="87ac8-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="87ac8-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="87ac8-110">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="87ac8-110">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="87ac8-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="87ac8-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="87ac8-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="87ac8-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="87ac8-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="87ac8-113">Permissions</span></span>  
 <span data-ttu-id="87ac8-114">Os procedimentos armazenados de envio de logs exigem a associação à função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="87ac8-114">The log-shipping stored procedures require membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="87ac8-115">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="87ac8-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-a-log-shipping-secondary-database"></a><span data-ttu-id="87ac8-116">Para remover um banco de dados secundário de envio de logs</span><span class="sxs-lookup"><span data-stu-id="87ac8-116">To remove a log shipping secondary database</span></span>  
  
1.  <span data-ttu-id="87ac8-117">Conecte à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que é no momento o servidor primário para envio de logs e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="87ac8-117">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is currently the log shipping primary server and expand that instance.</span></span>  
  
2.  <span data-ttu-id="87ac8-118">Expanda **Bancos de Dados**, clique com o botão direito do mouse no banco de dados primário de envio de logs e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="87ac8-118">Expand **Databases**, right-click the log shipping primary database, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="87ac8-119">Em **Selecionar uma página**, clique em **Envio do Log de Transações**.</span><span class="sxs-lookup"><span data-stu-id="87ac8-119">Under **Select a page**, click **Transaction Log Shipping**.</span></span>  
  
4.  <span data-ttu-id="87ac8-120">Em **Instâncias e banco de dados do servidor secundário**, clique no banco de dados que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="87ac8-120">Under **Secondary server instances and databases**, click the database you want to remove.</span></span>  
  
5.  <span data-ttu-id="87ac8-121">Clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="87ac8-121">Click **Remove**.</span></span>  
  
6.  <span data-ttu-id="87ac8-122">Clique em **OK** para atualizar a configuração.</span><span class="sxs-lookup"><span data-stu-id="87ac8-122">Click **OK** to update the configuration.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="87ac8-123">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="87ac8-123">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-a-secondary-database"></a><span data-ttu-id="87ac8-124">Para remover um banco de dados secundário</span><span class="sxs-lookup"><span data-stu-id="87ac8-124">To Remove a Secondary Database</span></span>  
  
1.  <span data-ttu-id="87ac8-125">No servidor primário, execute [sp_delete_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-primary-secondary-transact-sql) para excluir as informações sobre o banco de dados secundário do servidor primário.</span><span class="sxs-lookup"><span data-stu-id="87ac8-125">On the primary server, execute [sp_delete_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-primary-secondary-transact-sql) to delete the information about the secondary database from the primary server.</span></span>  
  
2.  <span data-ttu-id="87ac8-126">No servidor secundário, execute [sp_delete_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-secondary-database-transact-sql) para excluir o banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="87ac8-126">On the secondary server, execute [sp_delete_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-secondary-database-transact-sql) to delete the secondary database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="87ac8-127">Se não houver outro banco de dados secundário com a mesma ID secundária, **sp_delete_log_shipping_secondary_primary** será invocado de **sp_delete_log_shipping_secondary_database** e excluirá a entrada da ID secundária e os trabalhos de cópia e restauração.</span><span class="sxs-lookup"><span data-stu-id="87ac8-127">If there are no other secondary databases with the same secondary ID, **sp_delete_log_shipping_secondary_primary** is invoked from **sp_delete_log_shipping_secondary_database** and deletes the entry for the secondary ID and the copy and restore jobs.</span></span>  
  
3.  <span data-ttu-id="87ac8-128">No servidor secundário, desabilite os trabalhos de cópia e restauração.</span><span class="sxs-lookup"><span data-stu-id="87ac8-128">On the secondary server, disable the copy and restore jobs.</span></span> <span data-ttu-id="87ac8-129">Para obter mais informações, consulte [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="87ac8-129">For more information, see [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="87ac8-130">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="87ac8-130">Related Tasks</span></span>  
  
-   [<span data-ttu-id="87ac8-131">Atualizar o envio de logs para SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="87ac8-131">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="87ac8-132">Configurar o envio de logs &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="87ac8-132">Configure Log Shipping &#40;SQL Server&#41;</span></span>](configure-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="87ac8-133">Adicionar um banco de dados secundário a uma configuração de envio de logs &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="87ac8-133">Add a Secondary Database to a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](add-a-secondary-database-to-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="87ac8-134">Remover envio de log &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="87ac8-134">Remove Log Shipping &#40;SQL Server&#41;</span></span>](remove-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="87ac8-135">Exibir o relatório de envio de logs &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="87ac8-135">View the Log Shipping Report &#40;SQL Server Management Studio&#41;</span></span>](view-the-log-shipping-report-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="87ac8-136">Monitorar o envio de logs &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="87ac8-136">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="87ac8-137">Executar failover para um secundário de envio de logs &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="87ac8-137">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="87ac8-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="87ac8-138">See Also</span></span>  
 <span data-ttu-id="87ac8-139">[Sobre o envio de logs &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="87ac8-139">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="87ac8-140">Tabelas de envio de log e procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="87ac8-140">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
