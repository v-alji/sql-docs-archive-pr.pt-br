---
title: MSSQLSERVER_14421 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 14421 (Database Engine error)
ms.assetid: 03e76d4a-d463-4673-8843-08e4ecaefe27
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d6bc793911797c334d87238ec46531f7afbf63ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581902"
---
# <a name="mssqlserver_14421"></a><span data-ttu-id="34368-102">MSSQLSERVER_14421</span><span class="sxs-lookup"><span data-stu-id="34368-102">MSSQLSERVER_14421</span></span>
    
## <a name="details"></a><span data-ttu-id="34368-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="34368-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="34368-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="34368-104">Product Name</span></span>|<span data-ttu-id="34368-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="34368-105">SQL Server</span></span>|  
|<span data-ttu-id="34368-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="34368-106">Event ID</span></span>|<span data-ttu-id="34368-107">14421</span><span class="sxs-lookup"><span data-stu-id="34368-107">14421</span></span>|  
|<span data-ttu-id="34368-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="34368-108">Event Source</span></span>|<span data-ttu-id="34368-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="34368-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="34368-110">Componente</span><span class="sxs-lookup"><span data-stu-id="34368-110">Component</span></span>|<span data-ttu-id="34368-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="34368-111">SQLEngine</span></span>|  
|<span data-ttu-id="34368-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="34368-112">Symbolic Name</span></span>|<span data-ttu-id="34368-113">SQLErrorNum14421</span><span class="sxs-lookup"><span data-stu-id="34368-113">SQLErrorNum14421</span></span>|  
|<span data-ttu-id="34368-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="34368-114">Message Text</span></span>|<span data-ttu-id="34368-115">O banco de dados secundário de envio de logs %s.%s tem um limite de restauração de %d minutos e está fora de sincronização. Nenhuma restauração foi executada há %d minutos.</span><span class="sxs-lookup"><span data-stu-id="34368-115">The log shipping secondary database %s.%s has restore threshold of %d minutes and is out of sync. No restore was performed for %d minutes.</span></span> <span data-ttu-id="34368-116">A latência restaurada é de %d minutos.</span><span class="sxs-lookup"><span data-stu-id="34368-116">Restored latency is %d minutes.</span></span> <span data-ttu-id="34368-117">Verifique as informações de monitoração de log do agente e de envio de logs.</span><span class="sxs-lookup"><span data-stu-id="34368-117">Check agent log and logshipping monitor information.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="34368-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="34368-118">Explanation</span></span>  
 <span data-ttu-id="34368-119">Essa mensagem indica que o envio de logs está fora de sincronia além do limite de restauração.</span><span class="sxs-lookup"><span data-stu-id="34368-119">This message indicates that log shipping is out of synchronization beyond the restore threshold.</span></span> <span data-ttu-id="34368-120">O limite de restauração é o número de minutos entre as operações de restauração antes de uma mensagem ser gerada.</span><span class="sxs-lookup"><span data-stu-id="34368-120">The restore threshold is the number of minutes that can elapse between restore operations before a message is generated.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="34368-121">Possíveis causas</span><span class="sxs-lookup"><span data-stu-id="34368-121">Possible Causes</span></span>  
 <span data-ttu-id="34368-122">Essa mensagem não indica necessariamente um problema com o envio de logs.</span><span class="sxs-lookup"><span data-stu-id="34368-122">This message does not necessarily indicate a problem with log shipping.</span></span> <span data-ttu-id="34368-123">Em vez disso, ela pode indicar um dos seguintes problemas:</span><span class="sxs-lookup"><span data-stu-id="34368-123">Instead, this message might indicate one of the following problems:</span></span>  
  
-   <span data-ttu-id="34368-124">O trabalho de restauração não está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="34368-124">The restore job is not running.</span></span>  
  
     <span data-ttu-id="34368-125">É possível que o trabalho não esteja sendo executando pelas seguintes causas: o serviço SQL Server Agent na instância do servidor secundário não está sendo executado, o trabalho está desabilitado ou a agenda do trabalho foi alterada.</span><span class="sxs-lookup"><span data-stu-id="34368-125">Possible causes of the job not running include the following: the SQL Server Agent service on the secondary server instance is not running, the job is disabled, or the schedule of the job has been changed.</span></span>  
  
-   <span data-ttu-id="34368-126">O trabalho de restauração está apresentando falhas.</span><span class="sxs-lookup"><span data-stu-id="34368-126">The restore job is failing.</span></span>  
  
     <span data-ttu-id="34368-127">É possível que o trabalho esteja apresentando falhas pelas seguintes causas: o caminho da pasta de restauração não é válido, o disco está cheio ou qualquer outro motivo pelo qual a instrução RESTORE possa apresentar falha.</span><span class="sxs-lookup"><span data-stu-id="34368-127">Possible causes of the job failing include the following: the restore folder path is not valid, the disk is full, or any other reason that the RESTORE statement could fail.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="34368-128">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="34368-128">User Action</span></span>  
 <span data-ttu-id="34368-129">Para solucionar o problema dessa mensagem:</span><span class="sxs-lookup"><span data-stu-id="34368-129">To troubleshoot this message:</span></span>  
  
-   <span data-ttu-id="34368-130">Verifique se o serviço SQL Server Agent está sendo executado para a instância do servidor secundário e se o trabalho de restauração para esse banco de dados secundário está habilitado e agendado para ser executado na frequência apropriada.</span><span class="sxs-lookup"><span data-stu-id="34368-130">Make sure that the SQL Server Agent service is running for the secondary server instance and that the restore job for this secondary database is enabled and is scheduled to run at the appropriate frequency.</span></span>  
  
-   <span data-ttu-id="34368-131">O trabalho de restauração no servidor secundário pode estar apresentando falha.</span><span class="sxs-lookup"><span data-stu-id="34368-131">The restore job on the secondary server might be failing.</span></span> <span data-ttu-id="34368-132">Nesse caso, verifique o histórico de trabalhos do trabalho de restauração para procurar a causa.</span><span class="sxs-lookup"><span data-stu-id="34368-132">In this case, check the job history for the restore job to look for the cause.</span></span>  
  
-   <span data-ttu-id="34368-133">É possível que o trabalho de restauração de envio de logs, executado na instância do servidor secundário, não consiga se conectar à instância do servidor monitor para atualizar a tabela **log_shipping_monitor_secondary**.</span><span class="sxs-lookup"><span data-stu-id="34368-133">The log shipping restore job, which runs on the secondary server instance, might not be able to connect to the monitor server instance to update the **log_shipping_monitor_secondary** table.</span></span> <span data-ttu-id="34368-134">Isso pode ser causado por um problema de autenticação entre a instância do servidor monitor e a instância do servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="34368-134">This might be caused by an authentication problem between the monitor server instance and the secondary server instance.</span></span>  
  
-   <span data-ttu-id="34368-135">O limite de alerta de backup pode ter um valor incorreto.</span><span class="sxs-lookup"><span data-stu-id="34368-135">The backup alert threshold might have an incorrect value.</span></span> <span data-ttu-id="34368-136">De modo ideal, esse valor é definido para pelo menos três vezes a frequência do trabalho de restauração.</span><span class="sxs-lookup"><span data-stu-id="34368-136">Ideally, this value is set to at least three times the frequency of the restore job.</span></span> <span data-ttu-id="34368-137">Se você alterar a frequência do trabalho de restauração depois que o envio de logs estiver configurado e funcionando, também deverá atualizar o valor do limite de alerta de backup.</span><span class="sxs-lookup"><span data-stu-id="34368-137">If you change the frequency of the restore job after log shipping is configured and functional, you must update the value of the backup alert threshold accordingly.</span></span>  
  
-   <span data-ttu-id="34368-138">Quando a instância do servidor monitor fica offline e, depois, volta a ficar online, a tabela **log_shipping_monitor_secondary** não é atualizada com os valores atuais antes da execução do trabalho de mensagem de alerta.</span><span class="sxs-lookup"><span data-stu-id="34368-138">When the monitor server instance goes offline and then comes back online, the **log_shipping_monitor_secondary** table is not updated with the current values before the alert message job runs.</span></span> <span data-ttu-id="34368-139">O erro 14421 pode surgir quando um trabalho de restauração resulta em "Não foi possível localizar um arquivo de backup de log que pudesse ser aplicado ao banco de dados secundário".</span><span class="sxs-lookup"><span data-stu-id="34368-139">Error 14421 can be raised when a restore job succeeds with, "Could not find a log backup file that could be applied to secondary database."</span></span> <span data-ttu-id="34368-140">Quando isso acontece, a hora da restauração não é atualizada.</span><span class="sxs-lookup"><span data-stu-id="34368-140">When this occurs, the restore time is not updated.</span></span> <span data-ttu-id="34368-141">Nesse caso, a causa do erro pode ser um problema com o trabalho de cópia.</span><span class="sxs-lookup"><span data-stu-id="34368-141">The cause of the error in this case might be an issue with the copy job.</span></span>  
  
     <span data-ttu-id="34368-142">Para atualizar as tabelas do monitor com os últimos dados do banco de dados secundário, execute **sp_refresh_log_shipping_monitor** na instância do servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="34368-142">To update the monitor tables with the latest data for the secondary database, run **sp_refresh_log_shipping_monitor** on the secondary server instance.</span></span>  
  
-   <span data-ttu-id="34368-143">Na instância do servidor monitor ou secundário, a data ou a hora está incorreta.</span><span class="sxs-lookup"><span data-stu-id="34368-143">On the secondary or monitor server instance, the date or time is incorrect.</span></span> <span data-ttu-id="34368-144">Isso também pode gerar mensagens de alerta.</span><span class="sxs-lookup"><span data-stu-id="34368-144">This may also generate alert messages.</span></span> <span data-ttu-id="34368-145">É possível que a data ou a hora do sistema tenha sido modificada em um deles.</span><span class="sxs-lookup"><span data-stu-id="34368-145">Possibly the system date or time was modified on the one of them.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="34368-146">Fusos horários diferentes para as duas instâncias de servidor não deveriam causar um problema.</span><span class="sxs-lookup"><span data-stu-id="34368-146">Different time zones for the two server instances should not cause a problem.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34368-147">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="34368-147">See Also</span></span>  
 <span data-ttu-id="34368-148">[&#41;&#40;Transact-SQL de log_shipping_monitor_secondary](/sql/relational-databases/system-tables/log-shipping-monitor-secondary-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="34368-148">[log_shipping_monitor_secondary &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/log-shipping-monitor-secondary-transact-sql) </span></span>  
 <span data-ttu-id="34368-149">[Sobre o envio de logs &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="34368-149">[About Log Shipping &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md) </span></span>  
 <span data-ttu-id="34368-150">[&#41;&#40;Transact-SQL de sp_help_log_shipping_monitor_secondary](/sql/relational-databases/system-stored-procedures/sp-help-log-shipping-monitor-secondary-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="34368-150">[sp_help_log_shipping_monitor_secondary &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-log-shipping-monitor-secondary-transact-sql) </span></span>  
 <span data-ttu-id="34368-151">[&#41;&#40;Transact-SQL de sp_refresh_log_shipping_monitor](/sql/relational-databases/system-stored-procedures/sp-refresh-log-shipping-monitor-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="34368-151">[sp_refresh_log_shipping_monitor &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-refresh-log-shipping-monitor-transact-sql) </span></span>  
 [<span data-ttu-id="34368-152">Sobre o envio de logs &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34368-152">About Log Shipping &#40;SQL Server&#41;</span></span>](../../database-engine/log-shipping/about-log-shipping-sql-server.md)  
  
  
