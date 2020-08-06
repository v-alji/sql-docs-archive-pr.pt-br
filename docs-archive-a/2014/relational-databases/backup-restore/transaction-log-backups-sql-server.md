---
title: Backups do log de transações (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backing up [SQL Server], transaction logs
- transaction log backups [SQL Server], creating
- log backups [SQL Server[
- transaction log backups [SQL Server], sequencing
ms.assetid: f4a44a35-0f44-4a42-91d5-d73ac658a3b0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 752447d6c38a2df0fcbdce72fbba12edd7a9eeb3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681709"
---
# <a name="transaction-log-backups-sql-server"></a><span data-ttu-id="9ca72-102">Backups de log de transações (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9ca72-102">Transaction Log Backups (SQL Server)</span></span>
  <span data-ttu-id="9ca72-103">Este tópico é relevante apenas para bancos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que estejam usando modelos de recuperação completa ou bulk-logged.</span><span class="sxs-lookup"><span data-stu-id="9ca72-103">This topic is relevant only for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases that are using the full or bulk-logged recovery models.</span></span> <span data-ttu-id="9ca72-104">Este tópico descreve o backup do log de transações de um banco de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9ca72-104">This topic discusses backing up the transaction log of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="9ca72-105">Você deve ter pelo menos criado um backup completo antes de criar qualquer backup de log.</span><span class="sxs-lookup"><span data-stu-id="9ca72-105">Minimally, you must have created at least one full backup before you can create any log backups.</span></span> <span data-ttu-id="9ca72-106">Depois disso, o backup do log de transações pode ser feito a qualquer momento, exceto durante outro backup de log.</span><span class="sxs-lookup"><span data-stu-id="9ca72-106">After that, the transaction log can be backed up at any time unless the log is already being backed up.</span></span> <span data-ttu-id="9ca72-107">Recomendamos que você faça backups de log com frequência para minimizar exposição à perda de trabalho e truncar o log de transações.</span><span class="sxs-lookup"><span data-stu-id="9ca72-107">We recommend that you take log backups frequently, both to minimize work loss exposure and to truncate the transaction log.</span></span> <span data-ttu-id="9ca72-108">Normalmente, um administrador de banco de dados cria um backup completo de banco de dados ocasionalmente, como semanalmente, e, opcionalmente, cria uma série de backups de banco de dados diferentes a um intervalo mais curto, como diariamente.</span><span class="sxs-lookup"><span data-stu-id="9ca72-108">Typically, a database administrator creates a full database backup occasionally, such as weekly, and, optionally, creates a series of differential database backup at a shorter interval, such as daily.</span></span> <span data-ttu-id="9ca72-109">Independentemente dos backups de banco de dados, o administrador de banco de dados faz backup do log de transações a intervalos frequentes, como a cada 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="9ca72-109">Independently of the database backups, the database administrator backs up the transaction log at frequent intervals, such as every 10 minutes.</span></span> <span data-ttu-id="9ca72-110">Para determinado tipo de backup, o intervalo ideal entre backups depende de fatores como importância dos dados, tamanho do banco de dados e carga de trabalho do servidor.</span><span class="sxs-lookup"><span data-stu-id="9ca72-110">For a given type of backup, the optimal interval depends on factors such as the importance of the data, the size of the database, and the workload of the server.</span></span>  
  
 <span data-ttu-id="9ca72-111">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="9ca72-111">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="9ca72-112">Como funciona uma sequência de backups de log</span><span class="sxs-lookup"><span data-stu-id="9ca72-112">How a Sequence of Log Backups Works</span></span>](#LogBackupSequence)  
  
-   [<span data-ttu-id="9ca72-113">Recomendações</span><span class="sxs-lookup"><span data-stu-id="9ca72-113">Recommendations</span></span>](#Recommendations)  
  
-   [<span data-ttu-id="9ca72-114">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="9ca72-114">Related Tasks</span></span>](#RelatedTasks)  
  
-   [<span data-ttu-id="9ca72-115">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="9ca72-115">Related Content</span></span>](#RelatedContent)  
  
##  <a name="how-a-sequence-of-log-backups-works"></a><a name="LogBackupSequence"></a><span data-ttu-id="9ca72-116">Como funciona uma sequência de backups de log</span><span class="sxs-lookup"><span data-stu-id="9ca72-116">How a Sequence of Log Backups Works</span></span>  
 <span data-ttu-id="9ca72-117">A sequência de backups de log de transações *log chain* é independente dos backups de dados.</span><span class="sxs-lookup"><span data-stu-id="9ca72-117">The sequence of transaction log backups *log chain* is independent of data backups.</span></span> <span data-ttu-id="9ca72-118">Por exemplo, suponha a sequência de eventos a seguir.</span><span class="sxs-lookup"><span data-stu-id="9ca72-118">For example, assume the following sequence of events.</span></span>  
  
|<span data-ttu-id="9ca72-119">Hora</span><span class="sxs-lookup"><span data-stu-id="9ca72-119">Time</span></span>|<span data-ttu-id="9ca72-120">Evento</span><span class="sxs-lookup"><span data-stu-id="9ca72-120">Event</span></span>|  
|----------|-----------|  
|<span data-ttu-id="9ca72-121">8:00h</span><span class="sxs-lookup"><span data-stu-id="9ca72-121">8:00 A.M.</span></span>|<span data-ttu-id="9ca72-122">Backup do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9ca72-122">Back up database.</span></span>|  
|<span data-ttu-id="9ca72-123">Meio-dia</span><span class="sxs-lookup"><span data-stu-id="9ca72-123">Noon</span></span>|<span data-ttu-id="9ca72-124">Backup de log de transações.</span><span class="sxs-lookup"><span data-stu-id="9ca72-124">Back up transaction log.</span></span>|  
|<span data-ttu-id="9ca72-125">16:00h</span><span class="sxs-lookup"><span data-stu-id="9ca72-125">4:00 P.M.</span></span>|<span data-ttu-id="9ca72-126">Backup de log de transações.</span><span class="sxs-lookup"><span data-stu-id="9ca72-126">Back up transaction log.</span></span>|  
|<span data-ttu-id="9ca72-127">18:00h</span><span class="sxs-lookup"><span data-stu-id="9ca72-127">6:00 P.M.</span></span>|<span data-ttu-id="9ca72-128">Backup do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9ca72-128">Back up database.</span></span>|  
|<span data-ttu-id="9ca72-129">20:00h</span><span class="sxs-lookup"><span data-stu-id="9ca72-129">8:00 P.M.</span></span>|<span data-ttu-id="9ca72-130">Backup de log de transações.</span><span class="sxs-lookup"><span data-stu-id="9ca72-130">Back up transaction log.</span></span>|  
  
 <span data-ttu-id="9ca72-131">O backup do log de transações criado às 20h</span><span class="sxs-lookup"><span data-stu-id="9ca72-131">The transaction log backup created at 8:00 P.M.</span></span> <span data-ttu-id="9ca72-132">contém registros de logs de transações de 16h</span><span class="sxs-lookup"><span data-stu-id="9ca72-132">contains transaction log records from 4:00 P.M.</span></span> <span data-ttu-id="9ca72-133">até 20h, abrangendo a hora de conclusão do backup completo do banco de dados criado às 18h.</span><span class="sxs-lookup"><span data-stu-id="9ca72-133">through 8:00 P.M., spanning the time when the full database backup was created at 6:00 P.M.</span></span> <span data-ttu-id="9ca72-134">A sequência de backups de logs de transações é a continuação do backup completo de banco de dados inicial criado às 8h</span><span class="sxs-lookup"><span data-stu-id="9ca72-134">The sequence of transaction log backups is continuous from the initial full database backup created at 8:00 A.M.</span></span> <span data-ttu-id="9ca72-135">até o último backup do log de transações criado às 20h.</span><span class="sxs-lookup"><span data-stu-id="9ca72-135">to the last transaction log backup created at 8:00 P.M.</span></span> <span data-ttu-id="9ca72-136">Para obter informações sobre como aplicar esses backups de log, veja o exemplo [Aplicar backups de log de transações &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9ca72-136">For information about how to apply these log backups, see the example in [Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
##  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="9ca72-137">Recomendações</span><span class="sxs-lookup"><span data-stu-id="9ca72-137">Recommendations</span></span>  
  
-   <span data-ttu-id="9ca72-138">Se um log de transações estiver danificado, o trabalho executado desde o backup válido mais recente será perdido.</span><span class="sxs-lookup"><span data-stu-id="9ca72-138">If a transaction log is damaged, work that is performed since the most recent valid backup is lost.</span></span> <span data-ttu-id="9ca72-139">Portanto, recomendamos enfaticamente que você coloque seus arquivos de log em um armazenamento tolerante a falhas.</span><span class="sxs-lookup"><span data-stu-id="9ca72-139">Therefore we strongly recommend that you put your log files on fault-tolerant storage.</span></span>  
  
-   <span data-ttu-id="9ca72-140">Se um banco de dados for danificado ou se você estiver a ponto de restaurar o banco de dados, recomendamos que você crie um [backup da parte final do log](tail-log-backups-sql-server.md) para permitir a restauração do banco de dados até o momento atual.</span><span class="sxs-lookup"><span data-stu-id="9ca72-140">If a database is damaged or you are about to restore the database, we recommend that you create a [tail-log backup](tail-log-backups-sql-server.md) to enable you to restore the database to the current point in time.</span></span>  
  
-   <span data-ttu-id="9ca72-141">Por padrão, toda operação de backup bem-sucedida acrescenta uma entrada ao log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e ao log de eventos do sistema.</span><span class="sxs-lookup"><span data-stu-id="9ca72-141">By default, every successful backup operation adds an entry in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and in the system event log.</span></span> <span data-ttu-id="9ca72-142">Se você fizer backup do log com muita frequência, essas mensagens de êxito se acumularão muito rapidamente, resultando em logs de erros imensos que podem dificultar a localização de outras mensagens.</span><span class="sxs-lookup"><span data-stu-id="9ca72-142">If back up the log very frequently, these success messages accumulate quickly, resulting in huge error logs that can make finding other messages difficult.</span></span> <span data-ttu-id="9ca72-143">Em tais situações, você pode suprimir essas entradas de log usando o sinalizador de rastreamento 3226, caso nenhum dos seus scripts dependa dessas entradas.</span><span class="sxs-lookup"><span data-stu-id="9ca72-143">In such cases you can suppress these log entries by using trace flag 3226 if none of your scripts depend on those entries.</span></span> <span data-ttu-id="9ca72-144">Para obter mais informações, veja, [Sinalizadores de rastreamento &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9ca72-144">For more information, see [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="9ca72-145">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="9ca72-145">Related Tasks</span></span>  
 <span data-ttu-id="9ca72-146">**Para criar um backup de log de transações**</span><span class="sxs-lookup"><span data-stu-id="9ca72-146">**To create a transaction log backup**</span></span>  
  
-   [<span data-ttu-id="9ca72-147">Fazer backup de um log de transações &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9ca72-147">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
-   <span data-ttu-id="9ca72-148"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="9ca72-148"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span></span>  
  
 <span data-ttu-id="9ca72-149">Para agendar trabalhos de backup, consulte [Use the Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="9ca72-149">To schedule backup jobs, see [Use the Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span></span>  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="9ca72-150">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="9ca72-150">Related Content</span></span>  
 <span data-ttu-id="9ca72-151">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="9ca72-151">None.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ca72-152">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9ca72-152">See Also</span></span>  
 <span data-ttu-id="9ca72-153">[O log de transações &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9ca72-153">[The Transaction Log &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="9ca72-154">[Fazer backup e restaurar bancos de dados do SQL Server](back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="9ca72-154">[Back Up and Restore of SQL Server Databases](back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="9ca72-155">[Backups da parte final do log &#40;SQL Server&#41;](tail-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9ca72-155">[Tail-Log Backups &#40;SQL Server&#41;](tail-log-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="9ca72-156">Aplicar backups de log de transações &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9ca72-156">Apply Transaction Log Backups &#40;SQL Server&#41;</span></span>](transaction-log-backups-sql-server.md)  
  
  
