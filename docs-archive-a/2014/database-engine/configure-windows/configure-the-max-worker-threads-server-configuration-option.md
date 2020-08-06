---
title: Configurar a opção de configuração de servidor max worker threads | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- worker threads [SQL Server]
- max worker threads option
ms.assetid: abeadfa4-a14d-469a-bacf-75812e48fac1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4881cefee350d34d93b539c56be6f43866d3ddfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575347"
---
# <a name="configure-the-max-worker-threads-server-configuration-option"></a><span data-ttu-id="83045-102">Configurar a opção max worker threads de configuração de servidor</span><span class="sxs-lookup"><span data-stu-id="83045-102">Configure the max worker threads Server Configuration Option</span></span>
  <span data-ttu-id="83045-103">Este tópico descreve como configurar a opção de configuração de servidor **max worker threads** no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83045-103">This topic describes how to configure the **max worker threads** server configuration option in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="83045-104">A opção **max worker threads** configura o número de threads de trabalho que estão disponíveis para os processos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="83045-104">The **max worker threads** option configures the number of worker threads that are available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="83045-105">usa os serviços de thread nativos dos sistemas operacionais de forma que um ou mais threads ofereçam suporte a cada rede à qual o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oferece suporte simultaneamente, outro thread controle pontos de verificação de banco de dados e um pool de threads controle todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="83045-105">uses the native thread services of the operating systems so that one or more threads support each network that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supports simultaneously, another thread handles database checkpoints, and a pool of threads handles all users.</span></span> <span data-ttu-id="83045-106">O valor padrão de **max worker threads** é 0.</span><span class="sxs-lookup"><span data-stu-id="83045-106">The default value for **max worker threads** is 0.</span></span> <span data-ttu-id="83045-107">Isso habilita o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a configurar automaticamente o número de threads de trabalho na inicialização.</span><span class="sxs-lookup"><span data-stu-id="83045-107">This enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to automatically configure the number of worker threads at startup.</span></span> <span data-ttu-id="83045-108">A configuração padrão é a melhor para a maioria dos sistemas.</span><span class="sxs-lookup"><span data-stu-id="83045-108">The default setting is best for most systems.</span></span> <span data-ttu-id="83045-109">No entanto, dependendo de sua configuração de sistema, a definição de **max worker threads** com um valor específico às vezes melhora o desempenho.</span><span class="sxs-lookup"><span data-stu-id="83045-109">However, depending on your system configuration, setting **max worker threads** to a specific value sometimes improves performance.</span></span>  
  
 <span data-ttu-id="83045-110">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="83045-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="83045-111">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="83045-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="83045-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="83045-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="83045-113">Recomendações</span><span class="sxs-lookup"><span data-stu-id="83045-113">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="83045-114">Segurança</span><span class="sxs-lookup"><span data-stu-id="83045-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="83045-115">**Para configurar a opção max worker threads, usando:**</span><span class="sxs-lookup"><span data-stu-id="83045-115">**To configure the max worker threads option, using:**</span></span>  
  
     [<span data-ttu-id="83045-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="83045-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="83045-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="83045-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="83045-118">**Acompanhamento:**  [após você configurar a opção max worker threads](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="83045-118">**Follow Up:**  [After you configure the max worker threads option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="83045-119">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="83045-119">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="83045-120">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="83045-120">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="83045-121">Quando o número real de solicitações de consulta é menor que a quantidade definida em **max worker threads**, um thread controla cada solicitação de consulta.</span><span class="sxs-lookup"><span data-stu-id="83045-121">When the actual number of query requests is less than the amount set in **max worker threads**, one thread handles each query request.</span></span> <span data-ttu-id="83045-122">No entanto, se o número real de solicitações de consulta exceder o valor definido em **Max Worker threads**, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agrupa os threads de trabalho para que o próximo thread de trabalho disponível possa lidar com a solicitação.</span><span class="sxs-lookup"><span data-stu-id="83045-122">However, if the actual number of query request exceeds the amount set in **max worker threads**, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pools the worker threads so that the next available worker thread can handle the request.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="83045-123">Recomendações</span><span class="sxs-lookup"><span data-stu-id="83045-123">Recommendations</span></span>  
  
-   <span data-ttu-id="83045-124">Esta é uma opção avançada e deve ser alterada somente por um administrador de banco de dados experiente ou técnico certificado do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="83045-124">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="83045-125">O thread pooling ajuda a otimizar o desempenho quando são conectados grandes números de clientes ao servidor.</span><span class="sxs-lookup"><span data-stu-id="83045-125">Thread pooling helps optimize performance when large numbers of clients are connected to the server.</span></span> <span data-ttu-id="83045-126">Normalmente, é criado um thread de sistema operacional separado para cada solicitação de consulta.</span><span class="sxs-lookup"><span data-stu-id="83045-126">Usually, a separate operating system thread is created for each query request.</span></span> <span data-ttu-id="83045-127">Porém, com centenas de conexões para o servidor, usam um thread por solicitação de consulta pode consumir quantias grandes de recursos do sistema.</span><span class="sxs-lookup"><span data-stu-id="83045-127">However, with hundreds of connections to the server, using one thread per query request can consume large amounts of system resources.</span></span> <span data-ttu-id="83045-128">A opção **max worker threads** habilita o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a criar um pool de threads de trabalho para atender a um número maior de solicitações de consulta, o que melhora o desempenho.</span><span class="sxs-lookup"><span data-stu-id="83045-128">The **max worker threads** option enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to create a pool of worker threads to service a larger number of query requests, which improves performance.</span></span>  
  
-   <span data-ttu-id="83045-129">A tabela a seguir mostra o número configurado automaticamente de máximo de threads de trabalho para várias combinações de CPUs e versões do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83045-129">The following table shows the automatically configured number of max worker threads for various combinations of CPUs and versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    |<span data-ttu-id="83045-130">Número de CPUs</span><span class="sxs-lookup"><span data-stu-id="83045-130">Number of CPUs</span></span>|<span data-ttu-id="83045-131">Computador de 32 bits</span><span class="sxs-lookup"><span data-stu-id="83045-131">32-bit computer</span></span>|<span data-ttu-id="83045-132">Computador de 64 bits</span><span class="sxs-lookup"><span data-stu-id="83045-132">64-bit computer</span></span>|  
    |--------------------|----------------------|----------------------|  
    |<span data-ttu-id="83045-133">\<= 4 processadores</span><span class="sxs-lookup"><span data-stu-id="83045-133">\<= 4 processors</span></span>|<span data-ttu-id="83045-134">256</span><span class="sxs-lookup"><span data-stu-id="83045-134">256</span></span>|<span data-ttu-id="83045-135">512</span><span class="sxs-lookup"><span data-stu-id="83045-135">512</span></span>|  
    |<span data-ttu-id="83045-136">8 processadores</span><span class="sxs-lookup"><span data-stu-id="83045-136">8 processors</span></span>|<span data-ttu-id="83045-137">288</span><span class="sxs-lookup"><span data-stu-id="83045-137">288</span></span>|<span data-ttu-id="83045-138">576</span><span class="sxs-lookup"><span data-stu-id="83045-138">576</span></span>|  
    |<span data-ttu-id="83045-139">16 processadores</span><span class="sxs-lookup"><span data-stu-id="83045-139">16 processors</span></span>|<span data-ttu-id="83045-140">352</span><span class="sxs-lookup"><span data-stu-id="83045-140">352</span></span>|<span data-ttu-id="83045-141">704</span><span class="sxs-lookup"><span data-stu-id="83045-141">704</span></span>|  
    |<span data-ttu-id="83045-142">32 processadores</span><span class="sxs-lookup"><span data-stu-id="83045-142">32 processors</span></span>|<span data-ttu-id="83045-143">480</span><span class="sxs-lookup"><span data-stu-id="83045-143">480</span></span>|<span data-ttu-id="83045-144">960</span><span class="sxs-lookup"><span data-stu-id="83045-144">960</span></span>|  
    |<span data-ttu-id="83045-145">64 processadores</span><span class="sxs-lookup"><span data-stu-id="83045-145">64 processors</span></span>|<span data-ttu-id="83045-146">736</span><span class="sxs-lookup"><span data-stu-id="83045-146">736</span></span>|<span data-ttu-id="83045-147">1.472</span><span class="sxs-lookup"><span data-stu-id="83045-147">1472</span></span>|  
    |<span data-ttu-id="83045-148">128 processadores</span><span class="sxs-lookup"><span data-stu-id="83045-148">128 processors</span></span>|<span data-ttu-id="83045-149">4.224</span><span class="sxs-lookup"><span data-stu-id="83045-149">4224</span></span>|<span data-ttu-id="83045-150">4480</span><span class="sxs-lookup"><span data-stu-id="83045-150">4480</span></span>|  
    |<span data-ttu-id="83045-151">256 processadores</span><span class="sxs-lookup"><span data-stu-id="83045-151">256 processors</span></span>|<span data-ttu-id="83045-152">8.320</span><span class="sxs-lookup"><span data-stu-id="83045-152">8320</span></span>|<span data-ttu-id="83045-153">8.576</span><span class="sxs-lookup"><span data-stu-id="83045-153">8576</span></span>|  
  
    > [!NOTE]  
    >  <span data-ttu-id="83045-154">Para obter recomendações sobre como usar mais de 64 CPUs, veja [Práticas recomendadas para executar o SQL Server em computadores que têm mais de 64 CPUs](https://technet.microsoft.com/library/ee210547\(SQL.105\).aspx).</span><span class="sxs-lookup"><span data-stu-id="83045-154">For recommendations on using more than 64 CPUs, refer to [Best Practices for Running SQL Server on Computers That Have More Than 64 CPUs](https://technet.microsoft.com/library/ee210547\(SQL.105\).aspx).</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="83045-155">É recomendável 1024 como o número máximo de threads de trabalho para uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executado em um computador de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="83045-155">We recommend 1024 as the maximum number of worker threads for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on a 32-bit computer.</span></span>  
  
-   <span data-ttu-id="83045-156">Quando todos os threads de trabalho estiverem ativos com a execução de consultas longas, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] poderá parecer não estar respondendo até que um thread de trabalho seja concluído e fique disponível.</span><span class="sxs-lookup"><span data-stu-id="83045-156">When all worker threads are active with long running queries, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] might appear unresponsive until a worker thread completes and becomes available.</span></span> <span data-ttu-id="83045-157">Embora não seja um defeito, isso às vezes pode ser indesejável.</span><span class="sxs-lookup"><span data-stu-id="83045-157">Although this is not a defect, it can sometimes be undesirable.</span></span> <span data-ttu-id="83045-158">Se um processo parecer ser não estar respondendo e nenhuma nova consulta possa ser processada, então conecte ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que usa a conexão de administrador dedicada (DAC) e elimine o processo.</span><span class="sxs-lookup"><span data-stu-id="83045-158">If a process appears to be unresponsive and no new queries can be processed, then connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the dedicated administrator connection (DAC), and kill the process.</span></span> <span data-ttu-id="83045-159">Para evitar isto, aumente o número de máximo threads de trabalho.</span><span class="sxs-lookup"><span data-stu-id="83045-159">To prevent this, increase the number of max worker threads.</span></span>  
  
 <span data-ttu-id="83045-160">A opção de configuração do servidor **max worker threads** não leva em consideração os threads necessários para todas as tarefas de sistema como grupos de disponibilidade, Service Broker, Gerenciador de Bloqueio dentre outros.</span><span class="sxs-lookup"><span data-stu-id="83045-160">The **max worker threads** server configuration option does not take into account threads that are required for all the system tasks such as Availibility Groups, Service Broker, Lock Manager, and others.</span></span>  <span data-ttu-id="83045-161">Se o número de threads configurados estiver sendo excedido, a seguinte consulta fornecerá informações sobre as tarefas do sistema que geraram os threads adicionais.</span><span class="sxs-lookup"><span data-stu-id="83045-161">If the number of threads configured are being exceeded, the following query will provide information about the system tasks that have spawned the additional threads.</span></span>  
  
```  
SELECT  
s.session_id,  
r.command,  
r.status,  
r.wait_type,  
r.scheduler_id,  
w.worker_address,  
w.is_preemptive,  
w.state,  
t.task_state,  
t.session_id,  
t.exec_context_id,  
t.request_id  
FROM sys.dm_exec_sessions AS s  
INNERJOIN sys.dm_exec_requests AS r  
    ON s.session_id = r.session_id  
INNER JOIN sys.dm_os_tasks AS t  
    ON r.task_address = t.task_address  
INNER JOIN sys.dm_os_workers AS w  
    ON t.worker_address = w.worker_address  
WHERE s.is_user_process = 0;  
  
```  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="83045-162">Segurança</span><span class="sxs-lookup"><span data-stu-id="83045-162">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="83045-163">Permissões</span><span class="sxs-lookup"><span data-stu-id="83045-163">Permissions</span></span>  
 <span data-ttu-id="83045-164">Permissões de execução sem parâmetros ou com apenas o primeiro parâmetro em **sp_configure** são concedidas a todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="83045-164">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="83045-165">Para executar **sp_configure** com ambos os parâmetros para alterar uma opção de configuração ou executar a instrução RECONFIGURE, o usuário deve ter a permissão ALTER SETTINGS no nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="83045-165">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="83045-166">A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="83045-166">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="83045-167">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="83045-167">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-max-worker-threads-option"></a><span data-ttu-id="83045-168">Para configurar a opção max worker threads</span><span class="sxs-lookup"><span data-stu-id="83045-168">To configure the max worker threads option</span></span>  
  
1.  <span data-ttu-id="83045-169">No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="83045-169">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="83045-170">Clique no nó **Processadores** .</span><span class="sxs-lookup"><span data-stu-id="83045-170">Click the **Processors** node.</span></span>  
  
3.  <span data-ttu-id="83045-171">Na caixa **máximo de threads de trabalho** , digite ou selecione um valor de 128 a 32767.</span><span class="sxs-lookup"><span data-stu-id="83045-171">In the **Max worker threads** box, type or select a value from 128 through 32767.</span></span>  
  
     <span data-ttu-id="83045-172">Use a opção **max worker threads** para configurar o número de threads de trabalho disponível para os processos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="83045-172">Use the **max worker threads** option to configure the number of worker threads available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processes.</span></span> <span data-ttu-id="83045-173">A configuração padrão para **max worker threads** é a melhor para a maioria dos sistemas.</span><span class="sxs-lookup"><span data-stu-id="83045-173">The default setting for **max worker threads** is best for most systems.</span></span> <span data-ttu-id="83045-174">No entanto, dependendo de sua configuração de sistema, definir **máximo de threads de trabalho** como um valor menor algumas vezes melhora o desempenho.</span><span class="sxs-lookup"><span data-stu-id="83045-174">However, depending on your system configuration, setting **max worker threads** to a smaller value sometimes improves performance.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="83045-175">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="83045-175">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-max-worker-threads-option"></a><span data-ttu-id="83045-176">Para configurar a opção max worker threads</span><span class="sxs-lookup"><span data-stu-id="83045-176">To configure the max worker threads option</span></span>  
  
1.  <span data-ttu-id="83045-177">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83045-177">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="83045-178">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="83045-178">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="83045-179">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="83045-179">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="83045-180">Este exemplo mostra como usar o [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para configurar a opção `max worker threads` como `900`.</span><span class="sxs-lookup"><span data-stu-id="83045-180">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the `max worker threads` option to `900`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'max worker threads', 900 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="83045-181">Para obter mais informações, veja [Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="83045-181">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-max-worker-threads-option"></a><a name="FollowUp"></a> <span data-ttu-id="83045-182">Acompanhamento: Após você configurar a opção max worker threads</span><span class="sxs-lookup"><span data-stu-id="83045-182">Follow Up: After you configure the max worker threads option</span></span>  
 <span data-ttu-id="83045-183">A alteração entrará em vigor imediatamente sem exigir que o [!INCLUDE[ssDE](../../includes/ssde-md.md)] reinicie.</span><span class="sxs-lookup"><span data-stu-id="83045-183">The change will take effect immediately without requiring the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to restart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83045-184">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="83045-184">See Also</span></span>  
 <span data-ttu-id="83045-185">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="83045-185">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="83045-186">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="83045-186">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="83045-187">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="83045-187">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="83045-188">Conexão de diagnóstico para administradores de banco de dados</span><span class="sxs-lookup"><span data-stu-id="83045-188">Diagnostic Connection for Database Administrators</span></span>](diagnostic-connection-for-database-administrators.md)  
  
  
