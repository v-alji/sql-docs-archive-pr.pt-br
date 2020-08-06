---
title: Definir limites de aviso | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dbmmonitor.setwarningthreshold.f1
ms.assetid: 17f93147-e7d9-4092-b4c2-c11b38051171
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2d5fd9c0213d74f3a6b5d0d4cb2f11d3531d336d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681134"
---
# <a name="set-warning-thresholds"></a><span data-ttu-id="acbcb-102">Configurar limites de aviso</span><span class="sxs-lookup"><span data-stu-id="acbcb-102">Set Warning Thresholds</span></span>
  <span data-ttu-id="acbcb-103">Use essa caixa de diálogo para habilitar e configurar um ou mais limites de aviso para o banco de dados selecionado na árvore de navegação da caixa de diálogo **Monitor de Espelhamento de Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="acbcb-103">Use this dialog box to enable and configure one or more warning thresholds for the database selected in the navigation tree of the **Database Mirroring Monitor** dialog box.</span></span>  
  
 <span data-ttu-id="acbcb-104">A caixa de diálogo tenta se conectar a ambas as instâncias do servidor.</span><span class="sxs-lookup"><span data-stu-id="acbcb-104">The dialog box tries to connect to both server instances.</span></span> <span data-ttu-id="acbcb-105">Essas conexões são assincronamente estabelecidas.</span><span class="sxs-lookup"><span data-stu-id="acbcb-105">These connections are established asynchronously.</span></span> <span data-ttu-id="acbcb-106">A caixa de diálogo mostra o status da conexão de cada parceiro.</span><span class="sxs-lookup"><span data-stu-id="acbcb-106">The dialog shows the connection status of each partner.</span></span> <span data-ttu-id="acbcb-107">Se o parceiro não estiver conectado, você poderá clicar em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="acbcb-107">If the partner is not connected, you can click **Connect**.</span></span>  
  
 <span data-ttu-id="acbcb-108">**Para usar o SQL Server Management Studio para monitorar o espelhamento de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="acbcb-108">**To use SQL Server Management Studio to monitor database mirroring**</span></span>  
  
-   [<span data-ttu-id="acbcb-109">Iniciar o Monitor de Espelhamento de Banco de Dados &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="acbcb-109">Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;</span></span>](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md)  
  
## <a name="options"></a><span data-ttu-id="acbcb-110">Opções</span><span class="sxs-lookup"><span data-stu-id="acbcb-110">Options</span></span>  
 <span data-ttu-id="acbcb-111">*A instância de servidor e seu status de conexão*</span><span class="sxs-lookup"><span data-stu-id="acbcb-111">*Server instance and its connection status*</span></span>  
 <span data-ttu-id="acbcb-112">Nome de uma instância de servidor parceiro no formato _SYSTEM_ **\\** _INSTANCE_NAME_do sistema.</span><span class="sxs-lookup"><span data-stu-id="acbcb-112">Name of a partner server instance in the form _SYSTEM_**\\**_INSTANCE_NAME_.</span></span> <span data-ttu-id="acbcb-113">Com relação a uma instância de servidor padrão, o nome do sistema é exibido.</span><span class="sxs-lookup"><span data-stu-id="acbcb-113">For a default server instance, only the system name is displayed.</span></span>  
  
 <span data-ttu-id="acbcb-114">Esse campo indica também se o monitor está conectado atualmente à instância de servidor.</span><span class="sxs-lookup"><span data-stu-id="acbcb-114">This field also indicates whether the monitor is currently connected to this server instance.</span></span> <span data-ttu-id="acbcb-115">Os status de conexão possíveis são:</span><span class="sxs-lookup"><span data-stu-id="acbcb-115">The possible connection statuses are:</span></span>  
  
-   <span data-ttu-id="acbcb-116">**Não conectado a** *nome_da_instância_do_servidor*</span><span class="sxs-lookup"><span data-stu-id="acbcb-116">**Not connected to**  *server_instance_name*</span></span>  
  
-   <span data-ttu-id="acbcb-117">**Tentando se conectar a** *nome_da_instância_do_servidor*</span><span class="sxs-lookup"><span data-stu-id="acbcb-117">**Trying to connect to**  *server_instance_name*</span></span>  
  
-   <span data-ttu-id="acbcb-118">**Conectado a** *nome_da_instância_do_servidor*</span><span class="sxs-lookup"><span data-stu-id="acbcb-118">**Connected to**  *server_instance_name*</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="acbcb-119">Se você não for um membro da função de servidor fixa **sysadmin**, esse status será **Conectado a** *nome_da_instância_do_servidor* **(Permissões limitadas)** .</span><span class="sxs-lookup"><span data-stu-id="acbcb-119">If you do are not a member of the **sysadmin** fixed server role, this status is **Connected to** *server_instance_name* **(Limited permissions)**.</span></span>  
  
 <span data-ttu-id="acbcb-120">O nome de cada uma das instâncias de servidor de parceiro é exibido em um campo separado de *Instância de servidor e status de conexão* .</span><span class="sxs-lookup"><span data-stu-id="acbcb-120">The name of each of the partner server instances is displayed in a separate *Server instance and its connection status* field.</span></span> <span data-ttu-id="acbcb-121">O campo superior relacionará o servidor principal quando o monitor começar a ser executado.</span><span class="sxs-lookup"><span data-stu-id="acbcb-121">The top field lists the principal server when the monitor started running.</span></span>  
  
 <span data-ttu-id="acbcb-122">**Conectar**/**Cancelar**</span><span class="sxs-lookup"><span data-stu-id="acbcb-122">**Connect**/**Cancel**</span></span>  
 <span data-ttu-id="acbcb-123">O botão **Conectar**/**Cancelar** é associado a cada um dos campos *Instância de servidor e seu status de conexão* .</span><span class="sxs-lookup"><span data-stu-id="acbcb-123">A **Connect**/**Cancel** button is associated with each *Server instance and its connection status* fields.</span></span> <span data-ttu-id="acbcb-124">O status do botão depende do status da conexão:</span><span class="sxs-lookup"><span data-stu-id="acbcb-124">The state of the button depends on the connection status:</span></span>  
  
-   <span data-ttu-id="acbcb-125">Se não houver nenhuma conexão com a instância de servidor, o texto do botão será **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="acbcb-125">If there is no connection to the server instance, the button text is **Connect**.</span></span> <span data-ttu-id="acbcb-126">Clique para estabelecer conexão com a instância de servidor.</span><span class="sxs-lookup"><span data-stu-id="acbcb-126">Click to connect to the server instance.</span></span>  
  
-   <span data-ttu-id="acbcb-127">Quando uma tentativa de conexão estiver em andamento, o texto do botão será **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="acbcb-127">When a connection attempt is in progress, the button text is **Cancel**.</span></span> <span data-ttu-id="acbcb-128">Clique para cancelar a tentativa de conexão.</span><span class="sxs-lookup"><span data-stu-id="acbcb-128">Click to cancel the connection attempt.</span></span>  
  
-   <span data-ttu-id="acbcb-129">Se o servidor estiver conectado, o texto do botão será **Conectado**, e o botão ficará esmaecido.</span><span class="sxs-lookup"><span data-stu-id="acbcb-129">If the server is connected, the button text is **Connected**, and the button is dimmed.</span></span>  
  
 <span data-ttu-id="acbcb-130">**Limites**</span><span class="sxs-lookup"><span data-stu-id="acbcb-130">**Thresholds**</span></span>  
 <span data-ttu-id="acbcb-131">A grade **Limites** exibe as configurações de avisos de duas instâncias de servidor.</span><span class="sxs-lookup"><span data-stu-id="acbcb-131">The **Thresholds** grid displays the warnings settings for the two server instances.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="acbcb-132">Se uma instância de servidor não estiver conectada, suas colunas serão exibidas com células vazias e um plano de fundo cinza.</span><span class="sxs-lookup"><span data-stu-id="acbcb-132">If a server instance is not connected, its columns are displayed with empty cells and a gray background.</span></span> <span data-ttu-id="acbcb-133">Quando a conexão for aberta, a grade exibirá automaticamente o conteúdo da instância.</span><span class="sxs-lookup"><span data-stu-id="acbcb-133">When the connection opens, the grid automatically displays the content from the instance.</span></span>  
  
 <span data-ttu-id="acbcb-134">A grade contém as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="acbcb-134">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="acbcb-135">**Warnings**</span><span class="sxs-lookup"><span data-stu-id="acbcb-135">**Warnings**</span></span>  
 <span data-ttu-id="acbcb-136">Relaciona os avisos que têm suporte:</span><span class="sxs-lookup"><span data-stu-id="acbcb-136">Lists the supported warnings:</span></span>  
  
|<span data-ttu-id="acbcb-137">Aviso</span><span class="sxs-lookup"><span data-stu-id="acbcb-137">Warning</span></span>|<span data-ttu-id="acbcb-138">Descrição</span><span class="sxs-lookup"><span data-stu-id="acbcb-138">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="acbcb-139">**Avisar se o log não enviado exceder o limite**</span><span class="sxs-lookup"><span data-stu-id="acbcb-139">**Warn if the unsent log exceeds the threshold**</span></span>|<span data-ttu-id="acbcb-140">O limite indica o número de quilobytes (KB) do log não enviado na fila principal de envios de log.</span><span class="sxs-lookup"><span data-stu-id="acbcb-140">The threshold indicates the number of kilobytes (KB) of the unsent log in the send queue on the principal.</span></span>|  
|<span data-ttu-id="acbcb-141">**Avisar se o log não restaurado exceder o limite**</span><span class="sxs-lookup"><span data-stu-id="acbcb-141">**Warn if the unrestored log exceeds the threshold**</span></span>|<span data-ttu-id="acbcb-142">O limite indica o número de KBs da fila de restauração na instância de servidor espelho.</span><span class="sxs-lookup"><span data-stu-id="acbcb-142">The threshold indicates the number of KB of the redo queue on the mirror server instance.</span></span>|  
|<span data-ttu-id="acbcb-143">**Avisar se a idade da transação não enviada mais antiga exceder o limite**</span><span class="sxs-lookup"><span data-stu-id="acbcb-143">**Warn if the age of the oldest unsent transaction exceeds the threshold**</span></span>|<span data-ttu-id="acbcb-144">O limite indica o número de minutos de transações que ainda não foram enviadas da fila de envio para a instância de servidor de espelho.</span><span class="sxs-lookup"><span data-stu-id="acbcb-144">The threshold indicates the number of minutes of transactions that have not yet been sent from the send queue to the mirror server instance.</span></span> <span data-ttu-id="acbcb-145">Esse valor ajuda a medir o potencial de perda de dados em termos de tempo.</span><span class="sxs-lookup"><span data-stu-id="acbcb-145">This value helps measure the potential for data loss in terms of time.</span></span>|  
|<span data-ttu-id="acbcb-146">**Avisar se a sobrecarga espelhada confirmada exceder o limite**</span><span class="sxs-lookup"><span data-stu-id="acbcb-146">**Warn if the mirror commit overhead exceeds the threshold**</span></span>|<span data-ttu-id="acbcb-147">O limite indica o número de milissegundos de retardo por transação (pertinente só em modo de alta segurança).</span><span class="sxs-lookup"><span data-stu-id="acbcb-147">The threshold indicates the number of milliseconds of delay per transaction (relevant only in high-safety mode).</span></span> <span data-ttu-id="acbcb-148">Esse atraso consiste na quantidade de sobrecarga incidente enquanto a instância do servidor principal aguarda que a instância do servidor espelho grave o registro do log da transação na fila de restauração.</span><span class="sxs-lookup"><span data-stu-id="acbcb-148">This delay is the amount of overhead incurred while the principal server instance waits for the mirror server instance to write the transaction's log record into the redo queue.</span></span>|  
  
 <span data-ttu-id="acbcb-149">**Habilitado em '** *\<server instance>* **'**</span><span class="sxs-lookup"><span data-stu-id="acbcb-149">**Enabled at '** *\<server instance>* **'**</span></span>  
 <span data-ttu-id="acbcb-150">Uma caixa de seleção em branco indica que o aviso está desabilitado presentemente na instância de servidor.</span><span class="sxs-lookup"><span data-stu-id="acbcb-150">A blank check box indicates that the warning is currently disabled on the server instance.</span></span> <span data-ttu-id="acbcb-151">Para habilitar um aviso, clique em sua caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="acbcb-151">To enable a warning, click its check box.</span></span>  
  
 <span data-ttu-id="acbcb-152">**Limite em '** *\<server instance>* **'**</span><span class="sxs-lookup"><span data-stu-id="acbcb-152">**Threshold at '** *\<server instance>* **'**</span></span>  
 <span data-ttu-id="acbcb-153">Quando um aviso for habilitado, defina o limite no lado esquerdo dessa coluna.</span><span class="sxs-lookup"><span data-stu-id="acbcb-153">When a warning is enabled, set the threshold on the left side of this column.</span></span> <span data-ttu-id="acbcb-154">Um evento ocorrerá se o limite especificado tiver sido atingido quando a tabela de status for atualizada.</span><span class="sxs-lookup"><span data-stu-id="acbcb-154">An event occurs if the specified threshold has been reached when the status table is updated.</span></span> <span data-ttu-id="acbcb-155">Se você desabilitar um limite depois de configurar um valor, o valor permanecerá no campo e será usado quando você reabilitar o aviso.</span><span class="sxs-lookup"><span data-stu-id="acbcb-155">If you disable a threshold after configuring a value, your value remains in this field and will be used if you re-enable the warning.</span></span>  
  
 <span data-ttu-id="acbcb-156">Quando um aviso não for habilitado, o campo permanecerá inativo.</span><span class="sxs-lookup"><span data-stu-id="acbcb-156">When a warning is not enabled, this field is inactive.</span></span>  
  
 <span data-ttu-id="acbcb-157">**OK**</span><span class="sxs-lookup"><span data-stu-id="acbcb-157">**OK**</span></span>  
 <span data-ttu-id="acbcb-158">Clicar em **OK** fecha essa caixa de diálogo e exibe os valores dos limites de aviso especificados atualmente na grade **Limites** na página com guias **Avisos**.</span><span class="sxs-lookup"><span data-stu-id="acbcb-158">Clicking **OK** closes this dialog box and displays the currently specified values of warning thresholds in the **Thresholds** grid on the **Warnings**tabbed page.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="acbcb-159">Comentários</span><span class="sxs-lookup"><span data-stu-id="acbcb-159">Remarks</span></span>  
 <span data-ttu-id="acbcb-160">Um limite só se aplica a um parceiro por vez, mas é recomendado definir um limite para um determinado evento em ambos os parceiros, para assegurar que o aviso persista caso o banco de dados apresente failover.</span><span class="sxs-lookup"><span data-stu-id="acbcb-160">A threshold is only applicable at one partner at a time, but we recommend that you set a threshold for a given event on both partners to ensure that the warning persists if the database fails over.</span></span> <span data-ttu-id="acbcb-161">O limite adequado para cada parceiro depende das capacidades de desempenho o sistema daquele parceiro.</span><span class="sxs-lookup"><span data-stu-id="acbcb-161">The appropriate threshold for each partner depends on the performance capabilities of that partner's system.</span></span>  
  
 <span data-ttu-id="acbcb-162">Um evento de desempenho é gravado no log de eventos somente se o seu valor estiver no seu limite ou acima dele quando a tabela de status for atualizada.</span><span class="sxs-lookup"><span data-stu-id="acbcb-162">An event is written to the event log for a performance only if its value is at or above its threshold when the status table is being updated.</span></span> <span data-ttu-id="acbcb-163">Se um valor máximo alcançar temporariamente o limite entre as atualizações de status, este valor máximo é ignorado</span><span class="sxs-lookup"><span data-stu-id="acbcb-163">If a peak value reaches the threshold momentarily between status updates that peak is missed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acbcb-164">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="acbcb-164">See Also</span></span>  
 <span data-ttu-id="acbcb-165">[Iniciar o Monitor de Espelhamento de Banco de Dados &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="acbcb-165">[Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="acbcb-166">[Monitorando o espelhamento de banco de dados &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="acbcb-166">[Monitoring Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="acbcb-167">Iniciar o Assistente para Configurar Segurança de Espelhamento de Banco de Dados &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="acbcb-167">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
  
