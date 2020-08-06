---
title: Sobre o envio de logs (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- secondary servers [SQL Server]
- log shipping [SQL Server], jobs
- copy jobs [SQL Server]
- primary databases [SQL Server]
- log shipping [SQL Server], monitoring
- log shipping [SQL Server], about log shipping
- alert jobs [SQL Server]
- availability [SQL Server]
- jobs [SQL Server], log shipping
- monitor servers [SQL Server]
- restore jobs [SQL Server]
- log shipping [SQL Server]
- backup jobs [SQL Server]
- primary servers [SQL Server]
ms.assetid: 55da6b94-3a4b-4bae-850f-4bf7f6e918ca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cbf36e0ddd94ec0ab0a40a448e50602decfc0645
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680051"
---
# <a name="about-log-shipping-sql-server"></a><span data-ttu-id="ca2f9-102">Sobre o envio de logs (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ca2f9-102">About Log Shipping (SQL Server)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ca2f9-103">permite o envio automático de backups do log de transações de um *banco de dados primário* em uma instância do *servidor primário* para um ou mais *banco de dados secundário* em outras instâncias de *servidor secundário* .</span><span class="sxs-lookup"><span data-stu-id="ca2f9-103">Log shipping allows you to automatically send transaction log backups from a *primary database* on a *primary server* instance to one or more *secondary databases* on separate *secondary server* instances.</span></span> <span data-ttu-id="ca2f9-104">Os backups de logs de transação são aplicados individualmente aos bancos de dados secundários.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-104">The transaction log backups are applied to each of the secondary databases individually.</span></span> <span data-ttu-id="ca2f9-105">Uma terceira instância de servidor opcional, conhecida como *servidor monitor*, registra o histórico e o status das operações de backup e restauração e, opcionalmente, emite alertas se essas operações não forem executadas como foram agendadas.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-105">An optional third server instance, known as the *monitor server*, records the history and status of backup and restore operations and, optionally, raises alerts if these operations fail to occur as scheduled.</span></span>  
  
 <span data-ttu-id="ca2f9-106">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="ca2f9-106">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="ca2f9-107">Benefícios</span><span class="sxs-lookup"><span data-stu-id="ca2f9-107">Benefits</span></span>](#Benefits)  
  
-   [<span data-ttu-id="ca2f9-108">Termos e definições</span><span class="sxs-lookup"><span data-stu-id="ca2f9-108">Terms and Definitions</span></span>](#TermsAndDefinitions)  
  
-   [<span data-ttu-id="ca2f9-109">Visão geral do envio de log</span><span class="sxs-lookup"><span data-stu-id="ca2f9-109">Log Shipping Overview</span></span>](#ComponentsAndConcepts)  
  
-   [<span data-ttu-id="ca2f9-110">Interoperabilidade</span><span class="sxs-lookup"><span data-stu-id="ca2f9-110">Interoperability</span></span>](#Interoperability)  
  
-   [<span data-ttu-id="ca2f9-111">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="ca2f9-111">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="benefits"></a><a name="Benefits"></a> <span data-ttu-id="ca2f9-112">Benefícios</span><span class="sxs-lookup"><span data-stu-id="ca2f9-112">Benefits</span></span>  
  
-   <span data-ttu-id="ca2f9-113">Fornece uma solução de recuperação de desastres para um único banco de dados primário e um ou mais bancos de dados secundários, cada um em uma instância separada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca2f9-113">Provides a disaster-recovery solution for a single primary database and one or more secondary databases, each on a separate instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="ca2f9-114">Dá suporte a acesso somente leitura limitado a bancos de dados secundários (durante o intervalo entre trabalhos de restauração).</span><span class="sxs-lookup"><span data-stu-id="ca2f9-114">Supports limited read-only access to secondary databases (during the interval between restore jobs).</span></span>  
  
-   <span data-ttu-id="ca2f9-115">Permite um atraso especificado pelo usuário entre o momento em que o servidor primário faz backup do log do banco de dados primário e quando os servidores secundários devem restaurar (aplicar) o backup do log.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-115">Allows a user-specified delay between when the primary server backs up the log of the primary database and when the secondary servers must restore (apply) the log backup.</span></span> <span data-ttu-id="ca2f9-116">Um atraso mais longo pode ser útil, por exemplo, se dados forem alterados acidentalmente no banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-116">A longer delay can be useful, for example, if data is accidentally changed on the primary database.</span></span> <span data-ttu-id="ca2f9-117">Se a alteração acidental for notada rapidamente, um atraso pode permitir que você recupere dados ainda inalterados de um banco de dados secundário, antes que a alteração seja refletida lá.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-117">If the accidental change is noticed quickly, a delay can let you retrieve still unchanged data from a secondary database before the change is reflected there.</span></span>  
  
##  <a name="terms-and-definitions"></a><a name="TermsAndDefinitions"></a> <span data-ttu-id="ca2f9-118">Termos e definições</span><span class="sxs-lookup"><span data-stu-id="ca2f9-118">Terms and Definitions</span></span>  
 <span data-ttu-id="ca2f9-119">servidor primário</span><span class="sxs-lookup"><span data-stu-id="ca2f9-119">primary server</span></span>  
 <span data-ttu-id="ca2f9-120">A instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que é seu servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-120">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is your production server.</span></span>  
  
 <span data-ttu-id="ca2f9-121">banco de dados primário</span><span class="sxs-lookup"><span data-stu-id="ca2f9-121">primary database</span></span>  
 <span data-ttu-id="ca2f9-122">O banco de dados no servidor primário cujo backup você quer fazer e enviar para outro servidor.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-122">The database on the primary server that you want to back up to another server.</span></span> <span data-ttu-id="ca2f9-123">Toda a administração da configuração de envio de logs pelo [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] é realizada a partir do banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-123">All administration of the log shipping configuration through [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is performed from the primary database.</span></span>  
  
 <span data-ttu-id="ca2f9-124">servidor secundário</span><span class="sxs-lookup"><span data-stu-id="ca2f9-124">secondary server</span></span>  
 <span data-ttu-id="ca2f9-125">A instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] onde você deseja manter uma cópia de espera passiva de seu banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-125">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where you want to keep a warm standby copy of your primary database.</span></span>  
  
 <span data-ttu-id="ca2f9-126">banco de dados secundário</span><span class="sxs-lookup"><span data-stu-id="ca2f9-126">secondary database</span></span>  
 <span data-ttu-id="ca2f9-127">A cópia de espera passiva do banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-127">The warm standby copy of the primary database.</span></span> <span data-ttu-id="ca2f9-128">O banco de dados secundário pode estar no estado RECOVERING ou no estado STANDBY, o que deixa o banco de dados disponível para acesso limitado de somente leitura.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-128">The secondary database may be in either the RECOVERING state or the STANDBY state, which leaves the database available for limited read-only access.</span></span>  
  
 <span data-ttu-id="ca2f9-129">servidor monitor</span><span class="sxs-lookup"><span data-stu-id="ca2f9-129">monitor server</span></span>  
 <span data-ttu-id="ca2f9-130">Uma instância opcional do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que rastreia todos os detalhes do envio de log, incluindo:</span><span class="sxs-lookup"><span data-stu-id="ca2f9-130">An optional instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that tracks all of the details of log shipping, including:</span></span>  
  
-   <span data-ttu-id="ca2f9-131">A data do último backup do log de transações do banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-131">When the transaction log on the primary database was last backed up.</span></span>  
  
-   <span data-ttu-id="ca2f9-132">A data da última vez em que os arquivos de backup foram copiados e restaurados nos servidores secundários.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-132">When the secondary servers last copied and restored the backup files.</span></span>  
  
-   <span data-ttu-id="ca2f9-133">Informações sobre qualquer alerta de falha de backup.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-133">Information about any backup failure alerts.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ca2f9-134">Uma vez configurado o servidor monitor, ele não pode ser alterado sem antes remover o envio de log.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-134">Once the monitor server has been configured, it cannot be changed without removing log shipping first.</span></span>  
  
 <span data-ttu-id="ca2f9-135">trabalho de backup</span><span class="sxs-lookup"><span data-stu-id="ca2f9-135">backup job</span></span>  
 <span data-ttu-id="ca2f9-136">Um trabalho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent que executa a operação de backup, registra o histórico no servidor local e no servidor monitor e exclui os arquivos de backup antigos e as informações do histórico.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-136">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that  performs the backup operation, logs history to the local server and the monitor server, and deletes old backup files and history information.</span></span> <span data-ttu-id="ca2f9-137">Quando o envio de logs está habilitado, a categoria de trabalho "Backup de Envio de Logs" é criada na instância do servidor primário.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-137">When log shipping is enabled, the job category "Log Shipping Backup" is created on the primary server instance.</span></span>  
  
 <span data-ttu-id="ca2f9-138">trabalho de cópia</span><span class="sxs-lookup"><span data-stu-id="ca2f9-138">copy job</span></span>  
 <span data-ttu-id="ca2f9-139">Um trabalho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent que copia os arquivos de backup do servidor primário para um destino configurável no servidor secundário e registra o histórico no servidor secundário e no servidor monitor.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-139">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that copies the backup files from the primary server to a configurable destination on the secondary server and logs history on the secondary server and the monitor server.</span></span> <span data-ttu-id="ca2f9-140">Quando o envio de logs estiver habilitado em um banco de dados, a categoria de trabalho “Cópia de Envio de Log" será criada em cada servidor secundário em uma configuração de envio de logs.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-140">When log shipping is enabled on a database, the job category "Log Shipping Copy" is created on each secondary server in a log shipping configuration.</span></span>  
  
 <span data-ttu-id="ca2f9-141">trabalho de restauração</span><span class="sxs-lookup"><span data-stu-id="ca2f9-141">restore job</span></span>  
 <span data-ttu-id="ca2f9-142">Um trabalho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent que restaura os arquivos de backup copiados nos bancos de dados secundários.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-142">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that restores the copied backup files to the secondary databases.</span></span> <span data-ttu-id="ca2f9-143">Ele registra o histórico no servidor local e no servidor monitor e exclui arquivos e informações de histórico antigos.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-143">It logs history on the local server and the monitor server, and deletes old files and old history information.</span></span> <span data-ttu-id="ca2f9-144">Quando o envio de logs estiver habilitado em um banco de dados, a categoria de trabalho “Restauração de Envio de Log" será criada na instância do servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-144">When log shipping is enabled on a database, the job category "Log Shipping Restore" is created on the secondary server instance.</span></span>  
  
 <span data-ttu-id="ca2f9-145">trabalho de alerta</span><span class="sxs-lookup"><span data-stu-id="ca2f9-145">alert job</span></span>  
 <span data-ttu-id="ca2f9-146">Um trabalho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent que emite alertas para os bancos de dados primário e secundário quando uma operação de backup e restauração não é concluída com êxito dentro de um limite especificado.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-146">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that raises alerts for primary and secondary databases when a backup or restore operation does not complete successfully within a specified threshold.</span></span> <span data-ttu-id="ca2f9-147">Quando o envio de logs estiver habilitado em um banco de dados, a categoria de trabalho “Alerta de Envio de Log" será criada na instância do servidor monitor.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-147">When log shipping is enabled on a database, job category "Log Shipping Alert" is created on the monitor server instance.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="ca2f9-148">Para cada alerta, você precisa especificar um número de alerta.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-148">For each alert, you need to specify an alert number.</span></span> <span data-ttu-id="ca2f9-149">Além disso, configure o alerta para notificar um operador quando um alerta for gerado.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-149">Also, be sure to configure the alert to notify an operator when an alert is raised.</span></span>  
  
##  <a name="log-shipping-overview"></a><a name="ComponentsAndConcepts"></a> <span data-ttu-id="ca2f9-150">Visão geral do envio de log</span><span class="sxs-lookup"><span data-stu-id="ca2f9-150">Log Shipping Overview</span></span>  
 <span data-ttu-id="ca2f9-151">O envio de logs engloba três operações:</span><span class="sxs-lookup"><span data-stu-id="ca2f9-151">Log shipping consists of three operations:</span></span>  
  
1.  <span data-ttu-id="ca2f9-152">Backup do log de transações da instância do servidor primário.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-152">Back up the transaction log at the primary server instance.</span></span>  
  
2.  <span data-ttu-id="ca2f9-153">Cópia do arquivo do log de transações para a instância do servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-153">Copy the transaction log file to the secondary server instance.</span></span>  
  
3.  <span data-ttu-id="ca2f9-154">Restauração do backup de log na instância do servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-154">Restore the log backup on the secondary server instance.</span></span>  
  
 <span data-ttu-id="ca2f9-155">O log pode ser enviado a várias instâncias de servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-155">The log can be shipped to multiple secondary server instances.</span></span> <span data-ttu-id="ca2f9-156">Nesses casos, as operações 2 e 3 são repetidas em cada instância de servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-156">In such cases, operations 2 and 3 are duplicated for each secondary server instance.</span></span>  
  
 <span data-ttu-id="ca2f9-157">Uma configuração de envio de logs não realiza automaticamente failover do servidor primário ao secundário.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-157">A log shipping configuration does not automatically fail over from the primary server to the secondary server.</span></span> <span data-ttu-id="ca2f9-158">Se o banco de dados primário ficar indisponível, os bancos de dados secundários poderão ser colocados online manualmente.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-158">If the primary database becomes unavailable, any of the secondary databases can be brought online manually.</span></span>  
  
 <span data-ttu-id="ca2f9-159">Você pode usar um banco de dados secundário para gerar relatórios.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-159">You can use a secondary database for reporting purposes.</span></span>  
  
 <span data-ttu-id="ca2f9-160">Além disso, é possível configurar alertas para a configuração de envio de log.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-160">In addition, you can configure alerts for your log shipping configuration.</span></span>  
  
### <a name="a-typical-log-shipping-configuration"></a><span data-ttu-id="ca2f9-161">Uma configuração de envio de logs comum</span><span class="sxs-lookup"><span data-stu-id="ca2f9-161">A Typical Log Shipping Configuration</span></span>  
 <span data-ttu-id="ca2f9-162">A figura a seguir mostra a configuração do envio de logs com a instância do servidor primário, três instâncias de servidor secundário e uma instância de servidor monitor.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-162">The following figure shows a log shipping configuration with the primary server instance, three secondary server instances, and a monitor server instance.</span></span> <span data-ttu-id="ca2f9-163">A figura ilustra as etapas executadas pelos trabalhos de backup, cópia e restauração, como segue:</span><span class="sxs-lookup"><span data-stu-id="ca2f9-163">The figure illustrates the steps performed by backup, copy, and restorejobs, as follows:</span></span>  
  
1.  <span data-ttu-id="ca2f9-164">A instância do servidor primário executa o trabalho de backup do log de transações do banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-164">The primary server instance runs the backup job to back up the transaction log on the primary database.</span></span> <span data-ttu-id="ca2f9-165">Essa instância do servidor coloca o backup do log em um arquivo de backup de log primário, enviado para a pasta de backup.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-165">This server instance then places the log backup into a primary log-backup file, which it sends to the backup folder.</span></span>  <span data-ttu-id="ca2f9-166">Nesta figura, a pasta de backup está em um diretório compartilhado, o *compartilhamento de backup*.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-166">In this figure, the backup folder is on a shared directory-the *backup share*.</span></span>  
  
2.  <span data-ttu-id="ca2f9-167">Cada uma das três instâncias de servidor secundário executa seu próprio trabalho de cópia do arquivo de backup de log primário para a sua própria pasta de destino local.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-167">Each of the three secondary server instances runs its own copy job to copy the primary log-backup file to its own local destination folder.</span></span>  
  
3.  <span data-ttu-id="ca2f9-168">Cada instância de servidor secundário executa seu próprio trabalho de restauração do arquivo de backup de log a partir da pasta de destino local no banco de dados secundário local.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-168">Each secondary server instance runs its own restore job to restore the log backup from the local destination folder onto the local secondary database.</span></span>  
  
 <span data-ttu-id="ca2f9-169">As instâncias de servidor primário e secundário enviam seus próprios históricos e status para a instância do servidor monitor.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-169">The primary and secondary server instances send their own history and status to the monitor server instance.</span></span>  
  
 <span data-ttu-id="ca2f9-170">![Configuração mostrando trabalhos de backup, cópia e restauração](../media/ls-typical-configuration.gif "Configuração mostrando trabalhos de backup, cópia e restauração")</span><span class="sxs-lookup"><span data-stu-id="ca2f9-170">![Configuration showing backup, copy, & restore jobs](../media/ls-typical-configuration.gif "Configuration showing backup, copy, & restore jobs")</span></span>  
  
##  <a name="interoperability"></a><a name="Interoperability"></a> <span data-ttu-id="ca2f9-171">Interoperabilidade</span><span class="sxs-lookup"><span data-stu-id="ca2f9-171">Interoperability</span></span>  
 <span data-ttu-id="ca2f9-172">O envio de logs pode ser usado com os seguintes recursos ou componentes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ca2f9-172">Log shipping can be used with the following features or components of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   [<span data-ttu-id="ca2f9-173">Pré-requisitos para migrar do envio de logs para Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ca2f9-173">Prerequisites for Migrating from Log Shipping to AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](../availability-groups/windows/prereqs-migrating-log-shipping-to-always-on-availability-groups.md)  
  
-   [<span data-ttu-id="ca2f9-174">Espelhamento de banco de dados e envio de logs &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ca2f9-174">Database Mirroring and Log Shipping &#40;SQL Server&#41;</span></span>](../database-mirroring/database-mirroring-and-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="ca2f9-175">Replicação e envio de logs &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ca2f9-175">Log Shipping and Replication &#40;SQL Server&#41;</span></span>](log-shipping-and-replication-sql-server.md)  
  
> [!NOTE]  
>  [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] <span data-ttu-id="ca2f9-176">e o espelhamento de banco de dados são mutuamente exclusivos.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-176">and database mirroring are mutually exclusive.</span></span> <span data-ttu-id="ca2f9-177">Um banco de dados que é configurado para um desses recursos não pode ser configurado para o outro.</span><span class="sxs-lookup"><span data-stu-id="ca2f9-177">A database that is configured for one of these features cannot be configured for the other.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="ca2f9-178">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="ca2f9-178">Related Tasks</span></span>  
  
-   [<span data-ttu-id="ca2f9-179">Atualizar o envio de logs para SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ca2f9-179">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="ca2f9-180">Configurar o envio de logs &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ca2f9-180">Configure Log Shipping &#40;SQL Server&#41;</span></span>](configure-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="ca2f9-181">Adicionar um banco de dados secundário a uma configuração de envio de logs &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ca2f9-181">Add a Secondary Database to a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](add-a-secondary-database-to-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="ca2f9-182">Remover um banco de dados secundário de uma configuração de envio de logs &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ca2f9-182">Remove a Secondary Database from a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="ca2f9-183">Remover envio de log &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ca2f9-183">Remove Log Shipping &#40;SQL Server&#41;</span></span>](remove-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="ca2f9-184">Exibir o relatório de envio de logs &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="ca2f9-184">View the Log Shipping Report &#40;SQL Server Management Studio&#41;</span></span>](view-the-log-shipping-report-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="ca2f9-185">Monitorar o envio de logs &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ca2f9-185">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="ca2f9-186">Executar failover para um secundário de envio de logs &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ca2f9-186">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
-   [<span data-ttu-id="ca2f9-187">Executar failover para um secundário de envio de logs &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ca2f9-187">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
-   [<span data-ttu-id="ca2f9-188">Gerenciamento de logons e trabalhos após a troca de funções &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ca2f9-188">Management of Logins and Jobs After Role Switching &#40;SQL Server&#41;</span></span>](../../sql-server/failover-clusters/management-of-logins-and-jobs-after-role-switching-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="ca2f9-189">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ca2f9-189">See Also</span></span>  
 [<span data-ttu-id="ca2f9-190">Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ca2f9-190">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](../availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md)  
  
  
