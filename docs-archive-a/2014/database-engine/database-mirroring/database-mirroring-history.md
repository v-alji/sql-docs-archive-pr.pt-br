---
title: Histórico de espelhamento de banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dbmmonitor.databasemirroringhistory.f1
ms.assetid: 1d6e4b10-4a23-47d7-9918-c417992f09d3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3e32ad9bfdce15413d89fbd5ba3d79a5ef14f7a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581457"
---
# <a name="database-mirroring-history"></a><span data-ttu-id="409b1-102">Histórico do espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="409b1-102">Database Mirroring History</span></span>
  <span data-ttu-id="409b1-103">Use essa caixa de diálogo para exibir o histórico de status de espelhamento de um banco de dados espelho em uma instância de servidor especificada.</span><span class="sxs-lookup"><span data-stu-id="409b1-103">Use this dialog box to view the history of mirroring status for a mirrored database on a specified server instance.</span></span>  
  
 <span data-ttu-id="409b1-104">**Para usar o SQL Server Management Studio para monitorar o espelhamento de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="409b1-104">**To use SQL Server Management Studio to monitor database mirroring**</span></span>  
  
-   [<span data-ttu-id="409b1-105">Iniciar o Monitor de Espelhamento de Banco de Dados &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="409b1-105">Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;</span></span>](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md)  
  
## <a name="options"></a><span data-ttu-id="409b1-106">Opções</span><span class="sxs-lookup"><span data-stu-id="409b1-106">Options</span></span>  
 <span data-ttu-id="409b1-107">**Instância de servidor**</span><span class="sxs-lookup"><span data-stu-id="409b1-107">**Server instance**</span></span>  
 <span data-ttu-id="409b1-108">Nome da instância de servidor a partir da qual o histórico está sendo informado.</span><span class="sxs-lookup"><span data-stu-id="409b1-108">Name of the server instance from which the history is being reported.</span></span>  
  
 <span data-ttu-id="409b1-109">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="409b1-109">**Database**</span></span>  
 <span data-ttu-id="409b1-110">Nome do banco de dados cujo histórico está sendo informado.</span><span class="sxs-lookup"><span data-stu-id="409b1-110">Name of the database whose history is being reported.</span></span>  
  
 <span data-ttu-id="409b1-111">**Filtrar lista por**</span><span class="sxs-lookup"><span data-stu-id="409b1-111">**Filter list by**</span></span>  
 <span data-ttu-id="409b1-112">Lista valores de filtro.</span><span class="sxs-lookup"><span data-stu-id="409b1-112">Lists filter values.</span></span> <span data-ttu-id="409b1-113">A escolha de um novo valor atualiza a grade automaticamente.</span><span class="sxs-lookup"><span data-stu-id="409b1-113">Choosing a new value refreshes the grid automatically.</span></span>  
  
 <span data-ttu-id="409b1-114">Os possíveis valores de filtro são:</span><span class="sxs-lookup"><span data-stu-id="409b1-114">The possible filter values are:</span></span>  
  
-   <span data-ttu-id="409b1-115">Últimas duas horas</span><span class="sxs-lookup"><span data-stu-id="409b1-115">Last two hours</span></span>  
  
-   <span data-ttu-id="409b1-116">Últimas quatro horas</span><span class="sxs-lookup"><span data-stu-id="409b1-116">Last four hours</span></span>  
  
-   <span data-ttu-id="409b1-117">Últimas oito horas</span><span class="sxs-lookup"><span data-stu-id="409b1-117">Last eight hours</span></span>  
  
-   <span data-ttu-id="409b1-118">Último dia</span><span class="sxs-lookup"><span data-stu-id="409b1-118">Last day</span></span>  
  
-   <span data-ttu-id="409b1-119">Últimos dois dias</span><span class="sxs-lookup"><span data-stu-id="409b1-119">Last two days</span></span>  
  
-   <span data-ttu-id="409b1-120">Últimos 100 registros</span><span class="sxs-lookup"><span data-stu-id="409b1-120">Last 100 records</span></span>  
  
-   <span data-ttu-id="409b1-121">Últimos 500 registros</span><span class="sxs-lookup"><span data-stu-id="409b1-121">Last 500 records</span></span>  
  
-   <span data-ttu-id="409b1-122">Últimos 1000 registros</span><span class="sxs-lookup"><span data-stu-id="409b1-122">Last 1000 records</span></span>  
  
-   <span data-ttu-id="409b1-123">Todos os registros</span><span class="sxs-lookup"><span data-stu-id="409b1-123">All records</span></span>  
  
 <span data-ttu-id="409b1-124">**Atualizar**</span><span class="sxs-lookup"><span data-stu-id="409b1-124">**Refresh**</span></span>  
 <span data-ttu-id="409b1-125">Clique para atualizar a lista de histórico.</span><span class="sxs-lookup"><span data-stu-id="409b1-125">Click to refresh the history list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="409b1-126">Esta caixa de diálogo não atualiza a lista de histórico automaticamente.</span><span class="sxs-lookup"><span data-stu-id="409b1-126">This dialog box does not automatically refresh the history list.</span></span> <span data-ttu-id="409b1-127">Para atualizar a lista, clique em **Atualizar** ou escolha outra opção de filtro.</span><span class="sxs-lookup"><span data-stu-id="409b1-127">To refresh the list, either click **Refresh** or choose another filter option.</span></span> <span data-ttu-id="409b1-128">Somente membros da função de servidor fixa **sysadmin** podem atualizar o histórico de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="409b1-128">Only members of the **sysadmin** fixed server role can update the mirroring history.</span></span>  
  
 <span data-ttu-id="409b1-129">**Histórico**</span><span class="sxs-lookup"><span data-stu-id="409b1-129">**History**</span></span>  
 <span data-ttu-id="409b1-130">Exibe a lista de histórico.</span><span class="sxs-lookup"><span data-stu-id="409b1-130">Displays the history list.</span></span> <span data-ttu-id="409b1-131">Clique em um cabeçalho de coluna para classificar a grade por essa coluna.</span><span class="sxs-lookup"><span data-stu-id="409b1-131">Clicking on a column header sorts the grid by that column.</span></span> <span data-ttu-id="409b1-132">A lista contém as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="409b1-132">The list contains the following columns:</span></span>  
  
|<span data-ttu-id="409b1-133">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="409b1-133">Column name</span></span>|<span data-ttu-id="409b1-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="409b1-134">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="409b1-135">**Hora registrada**</span><span class="sxs-lookup"><span data-stu-id="409b1-135">**Time Recorded**</span></span>|<span data-ttu-id="409b1-136">Carimbo de data/hora da linha do histórico.</span><span class="sxs-lookup"><span data-stu-id="409b1-136">Timestamp of the history row.</span></span>|  
|<span data-ttu-id="409b1-137">**Função**</span><span class="sxs-lookup"><span data-stu-id="409b1-137">**Role**</span></span>|<span data-ttu-id="409b1-138">Função de espelhamento atual da instância de servidor deste banco de dados, Principal ou Espelho.</span><span class="sxs-lookup"><span data-stu-id="409b1-138">Current mirroring role of the server instance for this database, either Principal or Mirror.</span></span>|  
|<span data-ttu-id="409b1-139">**Estado de Espelhamento**</span><span class="sxs-lookup"><span data-stu-id="409b1-139">**Mirroring State**</span></span>|<span data-ttu-id="409b1-140">Estado do banco de dados:</span><span class="sxs-lookup"><span data-stu-id="409b1-140">State of the database:</span></span><br /><br /> <span data-ttu-id="409b1-141">Desconectado</span><span class="sxs-lookup"><span data-stu-id="409b1-141">Disconnected</span></span><br /><br /> <span data-ttu-id="409b1-142">Failover pendente</span><span class="sxs-lookup"><span data-stu-id="409b1-142">Pending Failover</span></span><br /><br /> <span data-ttu-id="409b1-143">Suspenso</span><span class="sxs-lookup"><span data-stu-id="409b1-143">Suspended</span></span><br /><br /> <span data-ttu-id="409b1-144">Sincronizado</span><span class="sxs-lookup"><span data-stu-id="409b1-144">Synchronized</span></span><br /><br /> <span data-ttu-id="409b1-145">Sincronizando</span><span class="sxs-lookup"><span data-stu-id="409b1-145">Synchronizing</span></span><br /><br /> <span data-ttu-id="409b1-146">Unknown (desconhecido)</span><span class="sxs-lookup"><span data-stu-id="409b1-146">Unknown</span></span>|  
|<span data-ttu-id="409b1-147">**Conexão de Testemunha**</span><span class="sxs-lookup"><span data-stu-id="409b1-147">**Witness Connection**</span></span>|<span data-ttu-id="409b1-148">Estado da conexão de testemunha na sessão de espelhamento de banco de dados, Conectado ou Desconectado.</span><span class="sxs-lookup"><span data-stu-id="409b1-148">State of the witness connection in the mirroring session of the database, either Connected or Disconnected.</span></span> <span data-ttu-id="409b1-149">Se não houver nenhum servidor testemunha, o valor será NULL.</span><span class="sxs-lookup"><span data-stu-id="409b1-149">If there is no witness, the value is NULL.</span></span>|  
|<span data-ttu-id="409b1-150">**Log Não Enviado**</span><span class="sxs-lookup"><span data-stu-id="409b1-150">**Unsent Log**</span></span>|<span data-ttu-id="409b1-151">Tamanho, em quilobytes (KB), do log não enviado na fila de envio da instância de servidor principal.</span><span class="sxs-lookup"><span data-stu-id="409b1-151">Size, in kilobytes (KB), of the unsent log in the send queue on the principal server instance.</span></span>|  
|<span data-ttu-id="409b1-152">**Tempo para Envio**</span><span class="sxs-lookup"><span data-stu-id="409b1-152">**Time to Send**</span></span>|<span data-ttu-id="409b1-153">Tempo aproximado exigido pela instância de servidor principal para enviar o log atualmente na fila de envio para a instância de servidor espelho (a *taxa de envio*).</span><span class="sxs-lookup"><span data-stu-id="409b1-153">Approximate amount of time the principal server instance will require to send the log that is currently in the send queue to the mirror server instance (the *send rate*).</span></span> <span data-ttu-id="409b1-154">Como a taxa de transações de entrada pode variar significativamente, a hora para enviar o log é uma estimativa.</span><span class="sxs-lookup"><span data-stu-id="409b1-154">Because the rate of incoming transactions can vary significantly, the time to send log is an estimate.</span></span> <span data-ttu-id="409b1-155">A taxa de envio, porém, pode ser útil para estimar aproximadamente a hora exigida para um failover manual.</span><span class="sxs-lookup"><span data-stu-id="409b1-155">However, the send rate can be useful for roughly estimating the time required for a manual failover.</span></span>|  
|<span data-ttu-id="409b1-156">**Send Rate**</span><span class="sxs-lookup"><span data-stu-id="409b1-156">**Send Rate**</span></span>|<span data-ttu-id="409b1-157">Taxa em que as transações estão sendo enviadas à instância de servidor espelho, em KB por segundo.</span><span class="sxs-lookup"><span data-stu-id="409b1-157">Rate at which transactions are being sent to the mirror server instance, in KB per second.</span></span>|  
|<span data-ttu-id="409b1-158">**Nova Taxa de Transação**</span><span class="sxs-lookup"><span data-stu-id="409b1-158">**New Transaction Rate**</span></span>|<span data-ttu-id="409b1-159">Taxa em que as transações de entrada estão sendo inseridas no log do servidor principal, em KB por segundo.</span><span class="sxs-lookup"><span data-stu-id="409b1-159">Rate at which incoming transactions are being entered into the principal's log, in KB per second.</span></span> <span data-ttu-id="409b1-160">Para determinar se o espelhamento está atrasado, acompanhando ou atualizado, compare esse valor ao valor do **Tempo para Envio** .</span><span class="sxs-lookup"><span data-stu-id="409b1-160">To determine whether mirroring is falling behind, staying up, or catching up, compare this value to the **Time to Send** value.</span></span>|  
|<span data-ttu-id="409b1-161">**Transação Não Enviada Mais Antiga**</span><span class="sxs-lookup"><span data-stu-id="409b1-161">**Oldest Unsent Transaction**</span></span>|<span data-ttu-id="409b1-162">Idade da transação não enviada mais antiga na fila de envio.</span><span class="sxs-lookup"><span data-stu-id="409b1-162">Age of the oldest unsent transaction in the send queue.</span></span> <span data-ttu-id="409b1-163">A idade dessa transação indica quantos minutos de transações ainda não foram enviados à instância de servidor espelho.</span><span class="sxs-lookup"><span data-stu-id="409b1-163">The age of this transaction indicates how many minutes of transactions have not yet been sent to the mirror server instance.</span></span> <span data-ttu-id="409b1-164">Esse valor ajuda a medir o potencial de perda de dados em termos de tempo.</span><span class="sxs-lookup"><span data-stu-id="409b1-164">This value helps measure the potential for data loss in terms of time.</span></span>|  
|<span data-ttu-id="409b1-165">**Log Não Restaurado**</span><span class="sxs-lookup"><span data-stu-id="409b1-165">**Unrestored Log**</span></span>|<span data-ttu-id="409b1-166">A quantidade de log em espera na fila de restauração, em quilobytes (KB).</span><span class="sxs-lookup"><span data-stu-id="409b1-166">The amount of log waiting in the redo queue, in KB.</span></span>|  
|<span data-ttu-id="409b1-167">**Tempo para Recuperar**</span><span class="sxs-lookup"><span data-stu-id="409b1-167">**Time to Restore**</span></span>|<span data-ttu-id="409b1-168">Número aproximado de minutos exigido para que o log atualmente na fila de restauração seja aplicado ao banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="409b1-168">Approximate number of minutes required for the log currently in the redo queue to be applied to the mirror database.</span></span>|  
|<span data-ttu-id="409b1-169">**Taxa de Recuperação**</span><span class="sxs-lookup"><span data-stu-id="409b1-169">**Restore Rate**</span></span>|<span data-ttu-id="409b1-170">Taxa em que as transações estão sendo recuperadas no banco de dados espelho, em KB por segundo.</span><span class="sxs-lookup"><span data-stu-id="409b1-170">Rate at which transactions are being restored into the mirror database, in KB per second.</span></span>|  
|<span data-ttu-id="409b1-171">**Sobrecarga Espelhada Confirmada**</span><span class="sxs-lookup"><span data-stu-id="409b1-171">**Mirror Commit Overhead**</span></span>|<span data-ttu-id="409b1-172">Atraso médio por transação em milissegundos (somente em modos síncronos).</span><span class="sxs-lookup"><span data-stu-id="409b1-172">Average delay per transaction in milliseconds (only in synchronous modes).</span></span> <span data-ttu-id="409b1-173">Esse atraso consiste na quantidade de sobrecarga incidente enquanto a instância do servidor principal aguarda que a instância do servidor espelho grave o registro do log da transação na fila de restauração.</span><span class="sxs-lookup"><span data-stu-id="409b1-173">This delay is the amount of overhead incurred while the principal server instance waits for the mirror server instance to write the transaction's log record into the redo queue.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="409b1-174">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="409b1-174">See Also</span></span>  
 <span data-ttu-id="409b1-175">[Iniciar o Monitor de Espelhamento de Banco de Dados &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="409b1-175">[Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="409b1-176">[Monitorando o espelhamento de banco de dados &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="409b1-176">[Monitoring Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="409b1-177">Iniciar o Assistente para Configurar Segurança de Espelhamento de Banco de Dados &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="409b1-177">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
  
