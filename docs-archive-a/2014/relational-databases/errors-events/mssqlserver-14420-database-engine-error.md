---
title: MSSQLSERVER_14420 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 14420 (Database Engine error)
ms.assetid: 4a1d72b1-ab1b-4119-a11b-a8a05c6fdb45
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7a17ab1e2281530b06c9ad27ac2a31672de0681e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572100"
---
# <a name="mssqlserver_14420"></a><span data-ttu-id="d86f5-102">MSSQLSERVER_14420</span><span class="sxs-lookup"><span data-stu-id="d86f5-102">MSSQLSERVER_14420</span></span>
    
## <a name="details"></a><span data-ttu-id="d86f5-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="d86f5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d86f5-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="d86f5-104">Product Name</span></span>|<span data-ttu-id="d86f5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d86f5-105">SQL Server</span></span>|  
|<span data-ttu-id="d86f5-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="d86f5-106">Event ID</span></span>|<span data-ttu-id="d86f5-107">14420</span><span class="sxs-lookup"><span data-stu-id="d86f5-107">14420</span></span>|  
|<span data-ttu-id="d86f5-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="d86f5-108">Event Source</span></span>|<span data-ttu-id="d86f5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d86f5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d86f5-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d86f5-110">Component</span></span>|<span data-ttu-id="d86f5-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d86f5-111">SQLEngine</span></span>|  
|<span data-ttu-id="d86f5-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="d86f5-112">Symbolic Name</span></span>|<span data-ttu-id="d86f5-113">SQLErrorNum14420</span><span class="sxs-lookup"><span data-stu-id="d86f5-113">SQLErrorNum14420</span></span>|  
|<span data-ttu-id="d86f5-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="d86f5-114">Message Text</span></span>|<span data-ttu-id="d86f5-115">O banco de dados primário de envio de logs %s.%s tem um limite de backup de %d minutos e não executou uma operação de log de backup há %d minutos.</span><span class="sxs-lookup"><span data-stu-id="d86f5-115">The log shipping primary database %s.%s has backup threshold of %d minutes and has not performed a backup log operation for %d minutes.</span></span> <span data-ttu-id="d86f5-116">Verifique as informações de monitoração de log do agente e de envio de logs.</span><span class="sxs-lookup"><span data-stu-id="d86f5-116">Check agent log and logshipping monitor information.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d86f5-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="d86f5-117">Explanation</span></span>  
 <span data-ttu-id="d86f5-118">O envio de logs está fora de sincronia além do limite de backup.</span><span class="sxs-lookup"><span data-stu-id="d86f5-118">Log shipping is out of synchronization beyond the backup threshold.</span></span> <span data-ttu-id="d86f5-119">O limite de backup é o número de minutos entre os trabalhos de backup de envio de logs antes de um alerta ser gerado.</span><span class="sxs-lookup"><span data-stu-id="d86f5-119">The backup threshold is the number of minutes that are allowed to elapse between log-shipping backup jobs before an alert is generated.</span></span> <span data-ttu-id="d86f5-120">Essa mensagem não indica necessariamente um problema com o envio de logs.</span><span class="sxs-lookup"><span data-stu-id="d86f5-120">This message does not necessarily indicate a problem with log shipping.</span></span> <span data-ttu-id="d86f5-121">Em vez disso, ela pode indicar um dos seguintes problemas:</span><span class="sxs-lookup"><span data-stu-id="d86f5-121">Instead, this message might indicate one of the following problems:</span></span>  
  
-   <span data-ttu-id="d86f5-122">O trabalho de backup não está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="d86f5-122">The backup job is not running.</span></span> <span data-ttu-id="d86f5-123">Causas possíveis: o serviço SQL Server Agent na instância do servidor primário não está sendo executado, o trabalho está desabilitado ou a agenda do trabalho foi alterada.</span><span class="sxs-lookup"><span data-stu-id="d86f5-123">Possible causes for this include the following: the SQL Server Agent service on the primary server instance is not running, the job is disabled, or the job's schedule has been changed.</span></span>  
  
-   <span data-ttu-id="d86f5-124">O trabalho de backup está apresentando falhas.</span><span class="sxs-lookup"><span data-stu-id="d86f5-124">The backup job is failing.</span></span> <span data-ttu-id="d86f5-125">Causas possíveis: o caminho de pasta de backup não é válido, o disco está cheio ou qualquer outro motivo pelo qual a instrução BACKUP possa apresentar falha.</span><span class="sxs-lookup"><span data-stu-id="d86f5-125">Possible causes for this include the following: the backup folder path is not valid, the disk is full, or any other reason that the BACKUP statement could fail.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d86f5-126">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="d86f5-126">User Action</span></span>  
 <span data-ttu-id="d86f5-127">Para solucionar o problema dessa mensagem:</span><span class="sxs-lookup"><span data-stu-id="d86f5-127">To troubleshoot this message:</span></span>  
  
-   <span data-ttu-id="d86f5-128">Verifique se o serviço SQL Server Agent está sendo executado para a instância do servidor primário e se o trabalho de backup para esse banco de dados primário está habilitado e agendado para ser executado na frequência apropriada.</span><span class="sxs-lookup"><span data-stu-id="d86f5-128">Make sure that the SQL Server Agent service is running for the primary server instance and that the backup job for this primary database is enabled and is scheduled to run at the appropriate frequency.</span></span>  
  
-   <span data-ttu-id="d86f5-129">O trabalho de backup no servidor primário pode estar apresentando falhas.</span><span class="sxs-lookup"><span data-stu-id="d86f5-129">The backup job on the primary server might be failing.</span></span> <span data-ttu-id="d86f5-130">Nesse caso, examine o histórico de trabalhos do trabalho de backup para procurar a causa.</span><span class="sxs-lookup"><span data-stu-id="d86f5-130">In this case, examine the job history for the backup job to look for the cause.</span></span>  
  
-   <span data-ttu-id="d86f5-131">É possível que o trabalho de backup de envio de logs, executado na instância do servidor primário, não consiga se conectar à instância do servidor monitor para atualizar a tabela **log_shipping_monitor_primary**.</span><span class="sxs-lookup"><span data-stu-id="d86f5-131">The log shipping backup job, which runs on the primary server instance, might not be able to connect to the monitor server instance to update the **log_shipping_monitor_primary** table.</span></span> <span data-ttu-id="d86f5-132">Isso pode ser causado por um problema de autenticação entre a instância do servidor monitor e a instância do servidor primário.</span><span class="sxs-lookup"><span data-stu-id="d86f5-132">This could be caused by an authentication problem between the monitor server instance and the primary server instance.</span></span>  
  
-   <span data-ttu-id="d86f5-133">O limite de alerta de backup pode ter um valor incorreto.</span><span class="sxs-lookup"><span data-stu-id="d86f5-133">The backup alert threshold might have an incorrect value.</span></span> <span data-ttu-id="d86f5-134">De modo ideal, esse valor é definido para pelo menos três vezes a frequência do trabalho de backup.</span><span class="sxs-lookup"><span data-stu-id="d86f5-134">Ideally, this value is set to at least three times the frequency of the backup job.</span></span> <span data-ttu-id="d86f5-135">Se você alterar a frequência do trabalho de backup depois que o envio de logs estiver configurado e funcionando, também deverá atualizar o valor do limite de alerta de backup.</span><span class="sxs-lookup"><span data-stu-id="d86f5-135">If you change the frequency of the backup job after log shipping is configured and functional, you must update the value of the backup alert threshold accordingly.</span></span>  
  
-   <span data-ttu-id="d86f5-136">Quando a instância do servidor monitor fica offline e, depois, volta a ficar online, a tabela **log_shipping_monitor_primary** não é atualizada com os valores atuais antes da execução do trabalho de mensagem de alerta.</span><span class="sxs-lookup"><span data-stu-id="d86f5-136">When the monitor server instance goes offline and then comes back online, the **log_shipping_monitor_primary** table is not updated with the current values before the alert message job runs.</span></span> <span data-ttu-id="d86f5-137">Para atualizar as tabelas do monitor com os últimos dados do banco de dados primário, execute **sp_refresh_log_shipping_monitor** na instância do servidor primário.</span><span class="sxs-lookup"><span data-stu-id="d86f5-137">To update the monitor tables with the latest data for the primary database, run **sp_refresh_log_shipping_monitor** on the primary server instance.</span></span>  
  
-   <span data-ttu-id="d86f5-138">Na instância do servidor monitor ou primário, a data ou a hora está incorreta.</span><span class="sxs-lookup"><span data-stu-id="d86f5-138">On the primary or monitor server instance, the date or time is incorrect.</span></span> <span data-ttu-id="d86f5-139">Isso também pode gerar mensagens de alerta.</span><span class="sxs-lookup"><span data-stu-id="d86f5-139">This may also generate alert messages.</span></span> <span data-ttu-id="d86f5-140">É possível que a data ou a hora do sistema tenha sido modificada em um deles.</span><span class="sxs-lookup"><span data-stu-id="d86f5-140">Possibly the system date or time was modified on the one of them.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d86f5-141">Fusos horários diferentes para as duas instâncias de servidor não deveriam causar um problema.</span><span class="sxs-lookup"><span data-stu-id="d86f5-141">Different time zones for the two server instances should not cause a problem.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d86f5-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d86f5-142">See Also</span></span>  
 <span data-ttu-id="d86f5-143">[&#41;&#40;Transact-SQL de log_shipping_monitor_primary](/sql/relational-databases/system-tables/log-shipping-monitor-primary-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d86f5-143">[log_shipping_monitor_primary &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/log-shipping-monitor-primary-transact-sql) </span></span>  
 <span data-ttu-id="d86f5-144">[Sobre o envio de logs &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d86f5-144">[About Log Shipping &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md) </span></span>  
 <span data-ttu-id="d86f5-145">[&#41;&#40;Transact-SQL de sp_help_log_shipping_monitor_primary](/sql/relational-databases/system-stored-procedures/sp-help-log-shipping-monitor-primary-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d86f5-145">[sp_help_log_shipping_monitor_primary &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-log-shipping-monitor-primary-transact-sql) </span></span>  
 <span data-ttu-id="d86f5-146">[&#41;&#40;Transact-SQL de sp_refresh_log_shipping_monitor](/sql/relational-databases/system-stored-procedures/sp-refresh-log-shipping-monitor-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d86f5-146">[sp_refresh_log_shipping_monitor &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-refresh-log-shipping-monitor-transact-sql) </span></span>  
 [<span data-ttu-id="d86f5-147">Sobre o envio de logs &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d86f5-147">About Log Shipping &#40;SQL Server&#41;</span></span>](../../database-engine/log-shipping/about-log-shipping-sql-server.md)  
  
  
