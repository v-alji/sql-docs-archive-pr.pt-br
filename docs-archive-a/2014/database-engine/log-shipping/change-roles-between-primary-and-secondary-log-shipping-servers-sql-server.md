---
title: Trocar funções entre servidores de envio de logs primários e secundários (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], role changes
- secondary data files [SQL Server], roles changed between
- primary databases [SQL Server]
- initial role changes [SQL Server]
- log shipping [SQL Server], failover
- failover [SQL Server], log shipping
ms.assetid: 2d7cc40a-47e8-4419-9b2b-7c69f700e806
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 52ddb89bfd18eef4cd2140bc67cf93d1800138f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681827"
---
# <a name="change-roles-between-primary-and-secondary-log-shipping-servers-sql-server"></a><span data-ttu-id="d7d92-102">Alterar funções entre servidores de envio de log primários e secundários (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d7d92-102">Change Roles Between Primary and Secondary Log Shipping Servers (SQL Server)</span></span>
  <span data-ttu-id="d7d92-103">Depois de fazer failover em uma configuração de log de envio do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para um servidor secundário, você pode configurar seu banco de dados secundário para agir como um banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="d7d92-103">After you have failed over a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log shipping configuration to a secondary server, you can configure your secondary database to act as the primary database.</span></span> <span data-ttu-id="d7d92-104">Então, você poderá trocar os bancos de dados primários e secundários como necessário.</span><span class="sxs-lookup"><span data-stu-id="d7d92-104">Then, you will be able to swap primary and secondary databases as needed.</span></span>  
  
## <a name="performing-the-initial-role-change"></a><span data-ttu-id="d7d92-105">Executando a alteração inicial de função</span><span class="sxs-lookup"><span data-stu-id="d7d92-105">Performing the Initial Role Change</span></span>  
 <span data-ttu-id="d7d92-106">Na primeira vez que você fizer failover no banco de dados secundário e torná-lo seu novo banco de dados primário, há uma série de etapas que deverão ser seguidas.</span><span class="sxs-lookup"><span data-stu-id="d7d92-106">The first time you want to fail over to the secondary database and make it your new primary database, there is a series of steps you must take.</span></span> <span data-ttu-id="d7d92-107">Depois de seguir essas etapas iniciais, você poderá alterar as funções facilmente entre o banco de dados primário e o banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="d7d92-107">After you have followed these initial steps, you will be able to swap roles between the primary database and the secondary database easily.</span></span>  
  
1.  <span data-ttu-id="d7d92-108">Faça failover manualmente do banco de dados primário para um banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="d7d92-108">Manually fail over from the primary database to a secondary database.</span></span> <span data-ttu-id="d7d92-109">Certifique-se de ter feito backup do log de transações ativas em seu servidor primário com NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="d7d92-109">Be sure to back up the active transaction log on your primary server with NORECOVERY.</span></span> <span data-ttu-id="d7d92-110">Para obter mais informações, consulte [Executar failover para um secundário de envio de logs &#40;SQL Server&#41;](fail-over-to-a-log-shipping-secondary-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d7d92-110">For more information, see [Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;](fail-over-to-a-log-shipping-secondary-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="d7d92-111">Desabilite o trabalho de backup de envio de logs no servidor primário original e os trabalhos de cópia e restauração no servidor secundário original.</span><span class="sxs-lookup"><span data-stu-id="d7d92-111">Disable the log shipping backup job on the original primary server, and the copy and restore jobs on the original secondary server.</span></span>  
  
3.  <span data-ttu-id="d7d92-112">Em seu banco de dados secundário (o banco de dados que você quer que seja o novo primário), configure o envio do log usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7d92-112">On your secondary database (the database you want to be the new primary), configure log shipping using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="d7d92-113">Para obter mais informações, consulte [Configurar o envio de logs &#40;SQL Server&#41;](configure-log-shipping-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d7d92-113">For more information, see [Configure Log Shipping &#40;SQL Server&#41;](configure-log-shipping-sql-server.md).</span></span> <span data-ttu-id="d7d92-114">Inclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="d7d92-114">Include the following steps:</span></span>  
  
    1.  <span data-ttu-id="d7d92-115">Use o mesmo compartilhamento usado para criar o servidor primário original para criar os backups.</span><span class="sxs-lookup"><span data-stu-id="d7d92-115">Use the same share for creating backups that you created for the original primary server.</span></span>  
  
    2.  <span data-ttu-id="d7d92-116">Quando adicionar o banco de dados secundário, na caixa de diálogo **Configurações do Banco de Dados Secundário** , digite o nome do banco de dados primário original na caixa **Banco de dados secundário** .</span><span class="sxs-lookup"><span data-stu-id="d7d92-116">When adding the secondary database, in the **Secondary Database Settings** dialog box, enter the name of the original primary database in the **Secondary database** box.</span></span>  
  
    3.  <span data-ttu-id="d7d92-117">Na caixa de diálogo **Configurações do Banco de Dados Secundário** , selecione **Não, o banco de dados secundário é inicializado**.</span><span class="sxs-lookup"><span data-stu-id="d7d92-117">In the **Secondary Database Settings** dialog box, select **No, the secondary database is initialized**.</span></span>  
  
4.  <span data-ttu-id="d7d92-118">Se o monitoramento de envio de logs tiver sido habilitado em sua configuração de envio de logs antiga, reconfigure o monitoramento de envio de logs para monitorar a nova configuração de envio de logs.</span><span class="sxs-lookup"><span data-stu-id="d7d92-118">If log shipping monitoring was enabled on your former log shipping configuration, reconfigure log shipping monitoring to monitor the new log shipping configuration.</span></span>  <span data-ttu-id="d7d92-119">Execute os seguintes comandos, substituindo *database_name* pelo nome de seu banco de dados:</span><span class="sxs-lookup"><span data-stu-id="d7d92-119">Execute the following commands, replacing *database_name* with the name of your database:</span></span>  
  
    1.  <span data-ttu-id="d7d92-120">**No novo servidor primário**</span><span class="sxs-lookup"><span data-stu-id="d7d92-120">**On the new primary server**</span></span>  
  
         <span data-ttu-id="d7d92-121">Execute as seguintes instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="d7d92-121">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
        ```  
        -- Statement to execute on the new primary server  
        USE msdb  
        GO  
        EXEC master.dbo.sp_change_log_shipping_secondary_database @secondary_database = N'database_name', @threshold_alert_enabled = 0;  
        GO  
        ```  
  
    2.  <span data-ttu-id="d7d92-122">**No novo servidor secundário:**</span><span class="sxs-lookup"><span data-stu-id="d7d92-122">**On the new secondary server**</span></span>  
  
         <span data-ttu-id="d7d92-123">Execute as seguintes instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="d7d92-123">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
        ```  
        -- Statement to execute on the new secondary server  
        USE msdb  
        GO  
        EXEC master.dbo.sp_change_log_shipping_primary_database @database=N'database_name', @threshold_alert_enabled = 0;  
        GO  
        ```  
  
## <a name="swapping-roles"></a><span data-ttu-id="d7d92-124">Alterando as funções</span><span class="sxs-lookup"><span data-stu-id="d7d92-124">Swapping Roles</span></span>  
 <span data-ttu-id="d7d92-125">Depois de ter concluído as etapas acima para a mudança inicial de funções, você poderá alterar as funções entre o banco de dados primário e o banco de dados secundário seguindo as etapas nesta seção.</span><span class="sxs-lookup"><span data-stu-id="d7d92-125">After you have completed the steps above for the initial role change, you can change roles between the primary database and the secondary database by following the steps in this section.</span></span> <span data-ttu-id="d7d92-126">Para executar uma mudança de função, siga estas etapas gerais:</span><span class="sxs-lookup"><span data-stu-id="d7d92-126">To perform a role change, follow these general steps:</span></span>  
  
1.  <span data-ttu-id="d7d92-127">Coloque o banco de dados secundário online, fazendo backup do log de transações no servidor primário com NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="d7d92-127">Bring the secondary database online, backing up the transaction log on the primary server with NORECOVERY.</span></span>  
  
2.  <span data-ttu-id="d7d92-128">Desabilite o trabalho de backup de envio de logs no servidor primário original e os trabalhos de cópia e restauração no servidor secundário original.</span><span class="sxs-lookup"><span data-stu-id="d7d92-128">Disable the log shipping backup job on the original primary server, and the copy and restore jobs on the original secondary server.</span></span>  
  
3.  <span data-ttu-id="d7d92-129">Habilite o trabalho de backup de envio de logs no servidor secundário (o novo servidor primário) e os trabalhos de cópia e restauração no servidor primário (o novo servidor secundário).</span><span class="sxs-lookup"><span data-stu-id="d7d92-129">Enable the log shipping backup job on the secondary server (the new primary server), and the copy and restore jobs on the primary server (the new secondary server).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d7d92-130">Ao alterar um banco de dados secundário para um banco de dados primário, para oferecer uma experiência consistente aos usuários e aplicativos, você poderá ter de recriar alguns ou todos os metadados do banco de dados, como logons e trabalhos, na nova instância de servidor primário.</span><span class="sxs-lookup"><span data-stu-id="d7d92-130">When you change a secondary database to the primary database, to provide a consistent experience to users and applications, you might have to re-create some or all of the metadata for the database, such as logins and jobs, on the new primary server instance.</span></span> <span data-ttu-id="d7d92-131">Para obter mais informações, consulte [Gerenciar metadados ao disponibilizar um banco de dados em outra instância do servidor &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span><span class="sxs-lookup"><span data-stu-id="d7d92-131">For more information, see [Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="d7d92-132">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="d7d92-132">Related Tasks</span></span>  
  
-   [<span data-ttu-id="d7d92-133">Executar failover para um secundário de envio de logs &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d7d92-133">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
-   [<span data-ttu-id="d7d92-134">Gerenciamento de logons e trabalhos após a troca de funções &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d7d92-134">Management of Logins and Jobs After Role Switching &#40;SQL Server&#41;</span></span>](../../sql-server/failover-clusters/management-of-logins-and-jobs-after-role-switching-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="d7d92-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d7d92-135">See Also</span></span>  
 [<span data-ttu-id="d7d92-136">Tabelas de envio de log e procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="d7d92-136">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
