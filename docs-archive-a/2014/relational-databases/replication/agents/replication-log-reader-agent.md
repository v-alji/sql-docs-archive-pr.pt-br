---
title: Agente de Leitor de Log de replicação | Microsoft Docs
ms.custom: ''
ms.date: 10/29/2018
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Log Reader Agent, executables
- Log Reader Agent, parameter reference
- agents [SQL Server replication], Log Reader Agent
- command prompt [SQL Server replication]
ms.assetid: 5487b645-d99b-454c-8bd2-aff470709a0e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 120c7418d8b16fe6d083961affcf0b8a9c9f6c65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573924"
---
# <a name="replication-log-reader-agent"></a><span data-ttu-id="32562-102">Replication Agente de Leitor de Log</span><span class="sxs-lookup"><span data-stu-id="32562-102">Replication Log Reader Agent</span></span>
  <span data-ttu-id="32562-103">O Replication Agente de Leitor de Log é um executável que monitora o log de transações de cada banco de dados configurado para replicação transacional e copia as transações marcadas para replicação do log de transações no banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="32562-103">The Replication Log Reader Agent is an executable that monitors the transaction log of each database configured for transactional replication and copies the transactions marked for replication from the transaction log into the distribution database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="32562-104">Os parâmetros podem ser especificados em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="32562-104">Parameters can be specified in any order.</span></span> <span data-ttu-id="32562-105">Quando não são especificados parâmetros opcionais, são usados valores predefinidos com base no perfil de agente padrão.</span><span class="sxs-lookup"><span data-stu-id="32562-105">When optional parameters are not specified, predefined values based on the default agent profile are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32562-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="32562-106">Syntax</span></span>  
  
```  
  
      logread [-?]   
-Publisherserver_name[\instance_name]   
-PublisherDBpublisher_database   
[-Continuous]  
[-DefinitionFiledef_path_and_file_name]  
[-Distributorserver_name[\instance_name]]  
[-DistributorLogindistributor_login]  
[-DistributorPassworddistributor_password]  
[-DistributorSecurityMode [0|1]]  
[-EncryptionLevel [0|1|2]]  
[-ExtendedEventConfigFileconfiguration_path_and_file_name]  
[-HistoryVerboseLevel [0|1|2]]  
[-KeepAliveMessageIntervalkeep_alive_message_interval_seconds]  
[-LoginTimeOutlogin_time_out_seconds]  
[-LogScanThresholdscan_threshold]  
[-MaxCmdsInTrannumber_of_commands]  
[-MessageIntervalmessage_interval]  
[-Outputoutput_path_and_file_name]  
[-OutputVerboseLevel [0|1|2|3|4]]  
[-PacketSizepacket_size]  
[-PollingIntervalpolling_interval]  
[-ProfileNameprofile_name]   
[-PublisherFailoverPartnerserver_name[\instance_name] ]  
[-PublisherSecurityMode [0|1]]  
[-PublisherLoginpublisher_login]  
[-PublisherPasswordpublisher_password]   
[-QueryTimeOutquery_time_out_seconds]  
[-ReadBatchSizenumber_of_transactions]   
[-ReadBatchThresholdread_batch_threshold]  
[-RecoverFromDataErrors]  
```  
  
## <a name="arguments"></a><span data-ttu-id="32562-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="32562-107">Arguments</span></span>  
 <span data-ttu-id="32562-108">**-?**</span><span class="sxs-lookup"><span data-stu-id="32562-108">**-?**</span></span>  
 <span data-ttu-id="32562-109">Exibe informações de uso.</span><span class="sxs-lookup"><span data-stu-id="32562-109">Displays usage information.</span></span>  
  
 <span data-ttu-id="32562-110">**-Publisher** _server_name_[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="32562-110">**-Publisher** _server_name_[**\\**_instance_name_]</span></span>  
 <span data-ttu-id="32562-111">É o nome do Publicador.</span><span class="sxs-lookup"><span data-stu-id="32562-111">Is the name of the Publisher.</span></span> <span data-ttu-id="32562-112">Especifica *server_name* para a instância padrão do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nesse servidor.</span><span class="sxs-lookup"><span data-stu-id="32562-112">Specify *server_name* for the default instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on that server.</span></span> <span data-ttu-id="32562-113">Especifique _server_name_ **\\** _instance_name_ para uma instância nomeada do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] naquele servidor.</span><span class="sxs-lookup"><span data-stu-id="32562-113">Specify _server_name_**\\**_instance_name_ for a named instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on that server.</span></span>  
  
 <span data-ttu-id="32562-114">**-PublisherDB** _publisher_database_</span><span class="sxs-lookup"><span data-stu-id="32562-114">**-PublisherDB** _publisher_database_</span></span>  
 <span data-ttu-id="32562-115">É o nome do banco de dados Publicador.</span><span class="sxs-lookup"><span data-stu-id="32562-115">Is the name of the Publisher database.</span></span>  
  
 <span data-ttu-id="32562-116">**-Continuous**</span><span class="sxs-lookup"><span data-stu-id="32562-116">**-Continuous**</span></span>  
 <span data-ttu-id="32562-117">Especifica se o agente tenta ou não sondar transações replicadas continuamente.</span><span class="sxs-lookup"><span data-stu-id="32562-117">Specifies whether the agent tries to poll replicated transactions continually.</span></span> <span data-ttu-id="32562-118">Se especificado, o agente sondará as transações replicadas da origem em intervalos de sondagem, mesmo que não haja transações pendentes.</span><span class="sxs-lookup"><span data-stu-id="32562-118">If specified, the agent polls replicated transactions from the source at polling intervals even if there are no transactions pending.</span></span>  
  
 <span data-ttu-id="32562-119">**-DefinitionFile** _def_path_and_file_name_</span><span class="sxs-lookup"><span data-stu-id="32562-119">**-DefinitionFile** _def_path_and_file_name_</span></span>  
 <span data-ttu-id="32562-120">É o caminho do arquivo de definição de agente.</span><span class="sxs-lookup"><span data-stu-id="32562-120">Is the path of the agent definition file.</span></span> <span data-ttu-id="32562-121">Um arquivo de definição de agente contém argumentos de linha de comando para o agente.</span><span class="sxs-lookup"><span data-stu-id="32562-121">An agent definition file contains command-line arguments for the agent.</span></span> <span data-ttu-id="32562-122">O conteúdo do arquivo é analisado como um arquivo executável.</span><span class="sxs-lookup"><span data-stu-id="32562-122">The content of the file is parsed as an executable file.</span></span> <span data-ttu-id="32562-123">Use aspas duplas (") para especificar os valores de argumentos que contêm caracteres arbitrários.</span><span class="sxs-lookup"><span data-stu-id="32562-123">Use double quotation marks (") to specify argument values that contain arbitrary characters.</span></span>  
  
 <span data-ttu-id="32562-124">**-Distributor** _server_name_[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="32562-124">**-Distributor** _server_name_[**\\**_instance_name_]</span></span>  
 <span data-ttu-id="32562-125">É o nome do Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="32562-125">Is the Distributor name.</span></span> <span data-ttu-id="32562-126">Especifica *server_name* para a instância padrão do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] naquele servidor.</span><span class="sxs-lookup"><span data-stu-id="32562-126">Specify *server_name* for the default instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on that server.</span></span> <span data-ttu-id="32562-127">Especifique _server_name_ **\\** _instance_name_ para uma instância nomeada do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] naquele servidor.</span><span class="sxs-lookup"><span data-stu-id="32562-127">Specify _server_name_**\\**_instance_name_ for a named instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on that server.</span></span>  
  
 <span data-ttu-id="32562-128">**-DistributorLogin** _distributor_login_</span><span class="sxs-lookup"><span data-stu-id="32562-128">**-DistributorLogin** _distributor_login_</span></span>  
 <span data-ttu-id="32562-129">É o nome de logon do Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="32562-129">Is the Distributor login name.</span></span>  
  
 <span data-ttu-id="32562-130">**-DistributorPassword** _distributor_password_</span><span class="sxs-lookup"><span data-stu-id="32562-130">**-DistributorPassword** _distributor_password_</span></span>  
 <span data-ttu-id="32562-131">É a senha do Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="32562-131">Is the Distributor password.</span></span>  
  
 <span data-ttu-id="32562-132">**-DistributorSecurityMode** [ **0**| **1**]</span><span class="sxs-lookup"><span data-stu-id="32562-132">**-DistributorSecurityMode** [ **0**| **1**]</span></span>  
 <span data-ttu-id="32562-133">Especifica o modo de segurança do Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="32562-133">Specifies the security mode of the Distributor.</span></span> <span data-ttu-id="32562-134">Um valor **0** indica Modo de Autenticação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (padrão) e um valor **1** indica [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Modo de Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="32562-134">A value of **0** indicates [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication Mode (default), and a value of **1** indicates [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows Authentication Mode.</span></span>  
  
 <span data-ttu-id="32562-135">**-EncryptionLevel** [ **0** | **1** | **2** ]</span><span class="sxs-lookup"><span data-stu-id="32562-135">**-EncryptionLevel** [ **0** | **1** | **2** ]</span></span>  
 <span data-ttu-id="32562-136">É o nível da criptografia SSL (Secure Sockets Layer) usada pelo Agente de Leitor de Log ao fazer conexões.</span><span class="sxs-lookup"><span data-stu-id="32562-136">Is the level of Secure Sockets Layer (SSL) encryption that is used by the Log Reader Agent when making connections.</span></span>  
  
|<span data-ttu-id="32562-137">Valor EncryptionLevel</span><span class="sxs-lookup"><span data-stu-id="32562-137">EncryptionLevel value</span></span>|<span data-ttu-id="32562-138">Descrição</span><span class="sxs-lookup"><span data-stu-id="32562-138">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="32562-139">**0**</span><span class="sxs-lookup"><span data-stu-id="32562-139">**0**</span></span>|<span data-ttu-id="32562-140">Especifica que o SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="32562-140">Specifies that SSL is not used.</span></span>|  
|<span data-ttu-id="32562-141">**1**</span><span class="sxs-lookup"><span data-stu-id="32562-141">**1**</span></span>|<span data-ttu-id="32562-142">Especifica que o SSL é usado, mas que +o agente não verifica se o certificado de servidor SSL é assinado por um emissor confiável.</span><span class="sxs-lookup"><span data-stu-id="32562-142">Specifies that SSL is used, but the agent does not verify that the SSL server certificate is signed by a trusted issuer.</span></span>|  
|<span data-ttu-id="32562-143">**2**</span><span class="sxs-lookup"><span data-stu-id="32562-143">**2**</span></span>|<span data-ttu-id="32562-144">Especifica que o SSL é usado, e que o certificado é verificado.</span><span class="sxs-lookup"><span data-stu-id="32562-144">Specifies that SSL is used, and that the certificate is verified.</span></span>|  

 > [!NOTE]  
 >  <span data-ttu-id="32562-145">É definido um certificado SSL válido com um nome de domínio totalmente qualificado do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="32562-145">A valid SSL certificate is defined with a fully qualified domain name of the SQL Server.</span></span> <span data-ttu-id="32562-146">Para que o agente seja conectado com êxito ao definir -EncryptionLevel como 2, crie um alias no SQL Server local.</span><span class="sxs-lookup"><span data-stu-id="32562-146">In order for the agent to connect successfully when setting -EncryptionLevel to 2, create an alias on the local SQL Server.</span></span> <span data-ttu-id="32562-147">O parâmetro 'Alias Name' deve ser o nome do servidor e o parâmetro 'Server' deve ser definido como o nome totalmente qualificado do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="32562-147">The 'Alias Name' parameter should be the server name and the 'Server' parameter should be set to the fully qualified name of the SQL Server.</span></span>
 
 <span data-ttu-id="32562-148">Para obter mais informações, consulte [replicação do SQL Server Security](../security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="32562-148">For more information, see [SQL Server Replication Security](../security/view-and-modify-replication-security-settings.md).</span></span>  
  
 <span data-ttu-id="32562-149">**-ExtendedEventConfigFile** _configuration_path_and_file_name_</span><span class="sxs-lookup"><span data-stu-id="32562-149">**-ExtendedEventConfigFile** _configuration_path_and_file_name_</span></span>  
 <span data-ttu-id="32562-150">Especifica o caminho e o nome do arquivo de configuração XML de eventos estendidos.</span><span class="sxs-lookup"><span data-stu-id="32562-150">Specifies the path and file name for the extended events XML configuration file.</span></span> <span data-ttu-id="32562-151">O arquivo de configuração de eventos estendidos permite configurar sessões e habilitar eventos para acompanhamento.</span><span class="sxs-lookup"><span data-stu-id="32562-151">The extended events configuration file allows you to configure sessions and enable events for tracking.</span></span>  
  
 <span data-ttu-id="32562-152">**-HistoryVerboseLevel** [ **0**| **1**| **2**]</span><span class="sxs-lookup"><span data-stu-id="32562-152">**-HistoryVerboseLevel** [ **0**| **1**| **2**]</span></span>  
 <span data-ttu-id="32562-153">Especifica a quantidade de histórico registrada durante uma operação de leitura de log.</span><span class="sxs-lookup"><span data-stu-id="32562-153">Specifies the amount of history logged during a log reader operation.</span></span> <span data-ttu-id="32562-154">Você pode minimizar o efeito de desempenho do registro de histórico selecionando **1**.</span><span class="sxs-lookup"><span data-stu-id="32562-154">You can minimize the performance effect of history logging by selecting **1**.</span></span>  
  
|<span data-ttu-id="32562-155">Valor HistoryVerboseLevel</span><span class="sxs-lookup"><span data-stu-id="32562-155">HistoryVerboseLevel value</span></span>|<span data-ttu-id="32562-156">Descrição</span><span class="sxs-lookup"><span data-stu-id="32562-156">Description</span></span>|  
|-------------------------------|-----------------|  
|<span data-ttu-id="32562-157">**0**</span><span class="sxs-lookup"><span data-stu-id="32562-157">**0**</span></span>||  
|<span data-ttu-id="32562-158">**1**</span><span class="sxs-lookup"><span data-stu-id="32562-158">**1**</span></span>|<span data-ttu-id="32562-159">Padrão.</span><span class="sxs-lookup"><span data-stu-id="32562-159">Default.</span></span> <span data-ttu-id="32562-160">Sempre atualiza uma mensagem de histórico anterior do mesmo status (inicialização, andamento, êxito, etc.).</span><span class="sxs-lookup"><span data-stu-id="32562-160">Always update a previous history message of the same status (startup, progress, success, and so on).</span></span> <span data-ttu-id="32562-161">Se nenhum registro anterior com o mesmo status existir, insira um registro novo.</span><span class="sxs-lookup"><span data-stu-id="32562-161">If no previous record with the same status exists, insert a new record.</span></span>|  
|<span data-ttu-id="32562-162">**2**</span><span class="sxs-lookup"><span data-stu-id="32562-162">**2**</span></span>|<span data-ttu-id="32562-163">Insira novos registros de histórico, a menos que o registro seja para coisas como mensagens ociosas ou mensagens de trabalho de execução longa; em tal caso, atualize os registros anteriores.</span><span class="sxs-lookup"><span data-stu-id="32562-163">Insert new history records unless the record is for such things as idle messages or long-running job messages, in which case update the previous records.</span></span>|  
  
 <span data-ttu-id="32562-164">**-KeepAliveMessageInterval** _keep_alive_message_interval_seconds_</span><span class="sxs-lookup"><span data-stu-id="32562-164">**-KeepAliveMessageInterval** _keep_alive_message_interval_seconds_</span></span>  
 <span data-ttu-id="32562-165">É o número de segundos antes que o thread de histórico verifique se alguma das conexões existentes está esperando por uma resposta do servidor.</span><span class="sxs-lookup"><span data-stu-id="32562-165">Is the number of seconds before the history thread checks if any of the existing connections is waiting for a response from the server.</span></span> <span data-ttu-id="32562-166">Esse valor pode ser diminuído para evitar que o agente de verificação marque o Agente de Leitor de Log como suspeito ao executar um lote de execução longa.</span><span class="sxs-lookup"><span data-stu-id="32562-166">This value can be decreased to avoid having the checkup agent mark the Log Reader Agent as suspect when executing a long-running batch.</span></span> <span data-ttu-id="32562-167">O padrão é 300 segundos.</span><span class="sxs-lookup"><span data-stu-id="32562-167">The default is 300 seconds.</span></span>  
  
 <span data-ttu-id="32562-168">**-LoginTimeOut** _login_time_out_seconds_</span><span class="sxs-lookup"><span data-stu-id="32562-168">**-LoginTimeOut** _login_time_out_seconds_</span></span>  
 <span data-ttu-id="32562-169">É o número de segundos antes que o logon expire. O padrão é 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="32562-169">Is the number of seconds before the login times out. The default is 15 seconds.</span></span>  
  
 <span data-ttu-id="32562-170">**-LogScanThreshold** _scan_threshold_</span><span class="sxs-lookup"><span data-stu-id="32562-170">**-LogScanThreshold** _scan_threshold_</span></span>  
 <span data-ttu-id="32562-171">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="32562-171">Internal use only.</span></span>  
  
 <span data-ttu-id="32562-172">**-MaxCmdsInTran** _number_of_commands_</span><span class="sxs-lookup"><span data-stu-id="32562-172">**-MaxCmdsInTran** _number_of_commands_</span></span>  
 <span data-ttu-id="32562-173">Especifica o número máximo de instruções agrupadas em uma transação à medida que o Log Reader grava comandos no banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="32562-173">Specifies the maximum number of statements grouped into a transaction as the Log Reader writes commands to the distribution database.</span></span> <span data-ttu-id="32562-174">O uso desse parâmetro permite que o Agente de Leitor de Log e o Agente de Distribuição divida grandes transações (consistindo em muitos comandos) no Publicador em várias transações menores quando aplicadas no Assinante.</span><span class="sxs-lookup"><span data-stu-id="32562-174">Using this parameter allows the Log Reader Agent and Distribution Agent to divide large transactions (consisting of many commands) at the Publisher into several smaller transactions when applied at the Subscriber.</span></span> <span data-ttu-id="32562-175">A especificação desse parâmetro pode reduzir a contenção no Distribuidor e pode reduzir a latência entre o Publicador e o Assinante.</span><span class="sxs-lookup"><span data-stu-id="32562-175">Specifying this parameter can reduce contention at the Distributor and reduce latency between the Publisher and Subscriber.</span></span> <span data-ttu-id="32562-176">Como a transação original é aplicada em unidades menores, o Assinante pode acessar linhas de uma transação lógica de Publicador antes do fim da transação original,</span><span class="sxs-lookup"><span data-stu-id="32562-176">Because the original transaction is applied in smaller units, the Subscriber can access rows of a large logical Publisher transaction prior to the end of the original transaction, breaking strict transactional atomicity.</span></span> <span data-ttu-id="32562-177">O padrão é **0**, que preserva os limites de transação do Publicador.</span><span class="sxs-lookup"><span data-stu-id="32562-177">The default is **0**, which preserves the transaction boundaries of the Publisher.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="32562-178">Esse parâmetro é ignorado para publicações que não são do[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="32562-178">This parameter is ignored for non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] publications.</span></span> <span data-ttu-id="32562-179">Para obter mais informações, consulte a seção que "Configurando o trabalho de conjunto das transações" em [Performance Tuning for Oracle Publishers](../non-sql/performance-tuning-for-oracle-publishers.md).</span><span class="sxs-lookup"><span data-stu-id="32562-179">For more information, see the section "Configuring the Transaction Set Job" in [Performance Tuning for Oracle Publishers](../non-sql/performance-tuning-for-oracle-publishers.md).</span></span>  
  
 <span data-ttu-id="32562-180">**-MessageInterval** _message_interval_</span><span class="sxs-lookup"><span data-stu-id="32562-180">**-MessageInterval** _message_interval_</span></span>  
 <span data-ttu-id="32562-181">É o intervalo de tempo usado para registro de histórico.</span><span class="sxs-lookup"><span data-stu-id="32562-181">Is the time interval used for history logging.</span></span> <span data-ttu-id="32562-182">Um evento de histórico é registrado quando o valor **MessageInterval** é alcançado depois que o ultimo evento de histórico é registrado.</span><span class="sxs-lookup"><span data-stu-id="32562-182">A history event is logged when the **MessageInterval** value is reached after the last history event is logged.</span></span>  
  
 <span data-ttu-id="32562-183">Se não houver nenhuma transação replicada disponível na origem, o agente informará uma mensagem de não transação ao Distributor.</span><span class="sxs-lookup"><span data-stu-id="32562-183">If there is no replicated transaction available at the source, the agent reports a no-transaction message to the Distributor.</span></span> <span data-ttu-id="32562-184">Essa opção especifica quanto tempo o agente espera antes de informar outro mensagem de não transação.</span><span class="sxs-lookup"><span data-stu-id="32562-184">This option specifies how long the agent waits before reporting another no-transaction message.</span></span> <span data-ttu-id="32562-185">O agente sempre informa uma mensagem de não transação quando detecta que não há transações disponíveis na origem após transações replicadas de processamento anterior.</span><span class="sxs-lookup"><span data-stu-id="32562-185">Agents always report a no-transaction message when they detect that there are no transactions available at the source after previously processing replicated transactions.</span></span> <span data-ttu-id="32562-186">O padrão é 60 segundos.</span><span class="sxs-lookup"><span data-stu-id="32562-186">The default is 60 seconds.</span></span>  
  
 <span data-ttu-id="32562-187">**-Output** _output_path_and_file_name_</span><span class="sxs-lookup"><span data-stu-id="32562-187">**-Output** _output_path_and_file_name_</span></span>  
 <span data-ttu-id="32562-188">É o caminho do arquivo de saída do agente.</span><span class="sxs-lookup"><span data-stu-id="32562-188">Is the path of the agent output file.</span></span> <span data-ttu-id="32562-189">Se o nome de arquivo não for fornecido, a saída será enviada ao console.</span><span class="sxs-lookup"><span data-stu-id="32562-189">If the file name is not provided, the output is sent to the console.</span></span> <span data-ttu-id="32562-190">Se o nome do arquivo especificado existir, a saída será anexada ao arquivo.</span><span class="sxs-lookup"><span data-stu-id="32562-190">If the specified file name exists, the output is appended to the file.</span></span>  
  
 <span data-ttu-id="32562-191">**-OutputVerboseLevel** [ **0**| **1**| **2** | **3** | **4** ]</span><span class="sxs-lookup"><span data-stu-id="32562-191">**-OutputVerboseLevel** [ **0**| **1**| **2** | **3** | **4** ]</span></span>  
 <span data-ttu-id="32562-192">Especifica se a saída deve ser detalhada.</span><span class="sxs-lookup"><span data-stu-id="32562-192">Specifies whether the output should be verbose.</span></span>  
  
|<span data-ttu-id="32562-193">Valor</span><span class="sxs-lookup"><span data-stu-id="32562-193">Value</span></span>|<span data-ttu-id="32562-194">Descrição</span><span class="sxs-lookup"><span data-stu-id="32562-194">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="32562-195">**0**</span><span class="sxs-lookup"><span data-stu-id="32562-195">**0**</span></span>|<span data-ttu-id="32562-196">Somente mensagens de erro são impressas.</span><span class="sxs-lookup"><span data-stu-id="32562-196">Only error messages are printed.</span></span>|  
|<span data-ttu-id="32562-197">**1**</span><span class="sxs-lookup"><span data-stu-id="32562-197">**1**</span></span>|<span data-ttu-id="32562-198">Todas as mensagens de relatório de progresso do agente são impressas.</span><span class="sxs-lookup"><span data-stu-id="32562-198">All agent progress report messages are printed.</span></span>|  
|<span data-ttu-id="32562-199">**2** (padrão)</span><span class="sxs-lookup"><span data-stu-id="32562-199">**2** (default)</span></span>|<span data-ttu-id="32562-200">Todas as mensagens de relatório de progresso do agente e de erro são impressas.</span><span class="sxs-lookup"><span data-stu-id="32562-200">All error messages and agent progress report messages are printed.</span></span>|  
|<span data-ttu-id="32562-201">**3**</span><span class="sxs-lookup"><span data-stu-id="32562-201">**3**</span></span>|<span data-ttu-id="32562-202">Os primeiros 100 bytes de cada comando replicado são impressos.</span><span class="sxs-lookup"><span data-stu-id="32562-202">The first 100 bytes of each replicated command are printed.</span></span>|  
|<span data-ttu-id="32562-203">**4**</span><span class="sxs-lookup"><span data-stu-id="32562-203">**4**</span></span>|<span data-ttu-id="32562-204">Todos os comandos replicados são impressos.</span><span class="sxs-lookup"><span data-stu-id="32562-204">All replicated commands are printed.</span></span>|  
  
 <span data-ttu-id="32562-205">Os valores 2-4 são úteis na depuração.</span><span class="sxs-lookup"><span data-stu-id="32562-205">Values 2-4 are useful when debugging.</span></span>  
  
 <span data-ttu-id="32562-206">**-PacketSize** _packet_size_</span><span class="sxs-lookup"><span data-stu-id="32562-206">**-PacketSize** _packet_size_</span></span>  
 <span data-ttu-id="32562-207">É o tamanho do pacote, em bytes.</span><span class="sxs-lookup"><span data-stu-id="32562-207">Is the packet size, in bytes.</span></span> <span data-ttu-id="32562-208">O padrão é 4096 (bytes).</span><span class="sxs-lookup"><span data-stu-id="32562-208">The default is 4096 (bytes).</span></span>  
  
 <span data-ttu-id="32562-209">**-PollingInterval** _polling_interval_</span><span class="sxs-lookup"><span data-stu-id="32562-209">**-PollingInterval** _polling_interval_</span></span>  
 <span data-ttu-id="32562-210">É a frequência, em segundos, que o log é consultado para transações replicadas.</span><span class="sxs-lookup"><span data-stu-id="32562-210">Is how often, in seconds, the log is queried for replicated transactions.</span></span> <span data-ttu-id="32562-211">O padrão é 5 segundos.</span><span class="sxs-lookup"><span data-stu-id="32562-211">The default is 5 seconds.</span></span>  
  
 <span data-ttu-id="32562-212">**-ProfileName** _profile_name_</span><span class="sxs-lookup"><span data-stu-id="32562-212">**-ProfileName** _profile_name_</span></span>  
 <span data-ttu-id="32562-213">Especifica um perfil de agente a ser usado para parâmetros de agente.</span><span class="sxs-lookup"><span data-stu-id="32562-213">Specifies an agent profile to use for agent parameters.</span></span> <span data-ttu-id="32562-214">Se **ProfileName** for NULL, o perfil de agente será desabilitado.</span><span class="sxs-lookup"><span data-stu-id="32562-214">If **ProfileName** is NULL, the agent profile is disabled.</span></span> <span data-ttu-id="32562-215">Se **ProfileName** não for especificado, o perfil padrão de tipo de agente será usado.</span><span class="sxs-lookup"><span data-stu-id="32562-215">If **ProfileName** is not specified, the default profile for the agent type is used.</span></span> <span data-ttu-id="32562-216">Para obter mais informações, consulte [Perfis do agente de replicação](replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="32562-216">For information, see [Replication Agent Profiles](replication-agent-profiles.md).</span></span>  
  
 <span data-ttu-id="32562-217">**-PublisherFailoverPartner** _server_name_[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="32562-217">**-PublisherFailoverPartner** _server_name_[**\\**_instance_name_]</span></span>  
 <span data-ttu-id="32562-218">Especifica a instância de parceiro de failover do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que participa de uma sessão de espelhamento de banco de dados com o banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="32562-218">Specifies the failover partner instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] participating in a database mirroring session with the publication database.</span></span> <span data-ttu-id="32562-219">Para obter mais informações, consulte [Espelhamento e replicação de banco de dados &#40;SQL Server&#41;](../../../database-engine/database-mirroring/database-mirroring-and-replication-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="32562-219">For more information, see [Database Mirroring and Replication &#40;SQL Server&#41;](../../../database-engine/database-mirroring/database-mirroring-and-replication-sql-server.md).</span></span>  
  
 <span data-ttu-id="32562-220">**-PublisherSecurityMode** [ **0**| **1**]</span><span class="sxs-lookup"><span data-stu-id="32562-220">**-PublisherSecurityMode** [ **0**| **1**]</span></span>  
 <span data-ttu-id="32562-221">Especifica o modo de segurança do Publicador.</span><span class="sxs-lookup"><span data-stu-id="32562-221">Specifies the security mode of the Publisher.</span></span> <span data-ttu-id="32562-222">Um valor de **0** indica Autenticação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (padrão), e um valor de **1** indica Modo de Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="32562-222">A value of **0** indicates [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication (default), and a value of **1** indicates Windows Authentication Mode.</span></span>  
  
 <span data-ttu-id="32562-223">**-PublisherLogin** _publisher_login_</span><span class="sxs-lookup"><span data-stu-id="32562-223">**-PublisherLogin** _publisher_login_</span></span>  
 <span data-ttu-id="32562-224">É o nome de logon do Publicador.</span><span class="sxs-lookup"><span data-stu-id="32562-224">Is the Publisher login name.</span></span>  
  
 <span data-ttu-id="32562-225">**-PublisherPassword** _publisher_password_</span><span class="sxs-lookup"><span data-stu-id="32562-225">**-PublisherPassword** _publisher_password_</span></span>  
 <span data-ttu-id="32562-226">É a senha do Publicador.</span><span class="sxs-lookup"><span data-stu-id="32562-226">Is the Publisher password.</span></span>  
  
 <span data-ttu-id="32562-227">**-QueryTimeOut** _query_time_out_seconds_</span><span class="sxs-lookup"><span data-stu-id="32562-227">**-QueryTimeOut** _query_time_out_seconds_</span></span>  
 <span data-ttu-id="32562-228">É o número de segundos antes que a consulta expire. O padrão é 1800 segundos.</span><span class="sxs-lookup"><span data-stu-id="32562-228">Is the number of seconds before the query times out. The default is 1800 seconds.</span></span>  
  
 <span data-ttu-id="32562-229">**-ReadBatchSize** _number_of_transactions_</span><span class="sxs-lookup"><span data-stu-id="32562-229">**-ReadBatchSize** _number_of_transactions_</span></span>  
 <span data-ttu-id="32562-230">É o número máximo de transações lidas de um log de transações do banco de dados de publicação por ciclo de processamento, com um padrão de 500.</span><span class="sxs-lookup"><span data-stu-id="32562-230">Is the maximum number of transactions read out of the transaction log of the publishing database per processing cycle, with a default of 500.</span></span> <span data-ttu-id="32562-231">O agente continuará lendo transações em lotes até que todas as transações tenham sido lidas do log.</span><span class="sxs-lookup"><span data-stu-id="32562-231">The agent will continue to read transactions in batches until all transactions are read from the log.</span></span> <span data-ttu-id="32562-232">Esse parâmetro não tem suporte para Publicadores Oracle.</span><span class="sxs-lookup"><span data-stu-id="32562-232">This parameter is not supported for Oracle Publishers.</span></span>  
  
 <span data-ttu-id="32562-233">**-ReadBatchThreshold** _number_of_commands_</span><span class="sxs-lookup"><span data-stu-id="32562-233">**-ReadBatchThreshold** _number_of_commands_</span></span>  
 <span data-ttu-id="32562-234">É o número de comandos de replicação a serem lidos no log de transações, antes de ser emitido para o Assinante pelo Agente de Distribuição.</span><span class="sxs-lookup"><span data-stu-id="32562-234">Is the number of replication commands to be read from the transaction log before being issued to the Subscriber by the Distribution Agent.</span></span> <span data-ttu-id="32562-235">O padrão é 0.</span><span class="sxs-lookup"><span data-stu-id="32562-235">The default is 0.</span></span> <span data-ttu-id="32562-236">Se o parâmetro não for especificado, o Agente de Leitor de Log lerá até a parte final do log ou até o número especificado em **-ReadBatchSize** (número de transações).</span><span class="sxs-lookup"><span data-stu-id="32562-236">If this parameter is not specified, the Log Reader Agent will read to the end of the log or to the number specified in **-ReadBatchSize** (number of transactions).</span></span>  
  
 <span data-ttu-id="32562-237">**-RecoverFromDataErrors**</span><span class="sxs-lookup"><span data-stu-id="32562-237">**-RecoverFromDataErrors**</span></span>  
 <span data-ttu-id="32562-238">Especifica que o Agente de Leitor de Log continuará a executar, quando encontrar erros em dados de colunas publicados de um Publicador não SQL Server.</span><span class="sxs-lookup"><span data-stu-id="32562-238">Specifies that the Log Reader Agent continue to run when it encounters errors in column data published from a non-SQL Server Publisher.</span></span> <span data-ttu-id="32562-239">Por padrão, tais erros fazem o Agente de Leitor de Log falhar.</span><span class="sxs-lookup"><span data-stu-id="32562-239">By default, such errors cause the Log Reader Agent to fail.</span></span> <span data-ttu-id="32562-240">Quando você usa **-RecoverFromDataErrors**, dados de coluna são replicados erroneamente como NULL ou como um valor não nulo apropriado e as mensagens de aviso são registradas na tabela [MSlogreader_history](/sql/relational-databases/system-tables/mslogreader-history-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="32562-240">When you use **-RecoverFromDataErrors**, erroneous column data is replicated either as NULL or an appropriate nonnull value, and warning messages are logged to the [MSlogreader_history](/sql/relational-databases/system-tables/mslogreader-history-transact-sql) table.</span></span> <span data-ttu-id="32562-241">Esse parâmetro só tem suporte para Editores Oracle.</span><span class="sxs-lookup"><span data-stu-id="32562-241">This parameter is only supported for Oracle Publishers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32562-242">Comentários</span><span class="sxs-lookup"><span data-stu-id="32562-242">Remarks</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="32562-243">Se você instalou o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent para executar com uma conta Sistema Local em vez de uma conta de usuário de domínio (o padrão), o serviço só poderá acessar o computador local.</span><span class="sxs-lookup"><span data-stu-id="32562-243">If you installed [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent to run under a local system account instead of under a domain user account (the default), the service can access only the local computer.</span></span> <span data-ttu-id="32562-244">Se o Agente de Leitor de Log executado no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent for configurado para usar o Modo de Autenticação do Windows ao fazer logon no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], o Agente de Leitor de Log falhará.</span><span class="sxs-lookup"><span data-stu-id="32562-244">If the Log Reader Agent that runs under [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent is configured to use Windows Authentication Mode when it logs in to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the Log Reader Agent fails.</span></span> <span data-ttu-id="32562-245">A configuração padrão é Autenticação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="32562-245">The default setting is [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="32562-246">Para obter informações em como alterar contas de segurança, consulte [View and Modify Replication Security Settings](../security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="32562-246">For information about changing security accounts, see [View and Modify Replication Security Settings](../security/view-and-modify-replication-security-settings.md).</span></span>  
  
 <span data-ttu-id="32562-247">Para iniciar o Agente de Leitor de Log, execute **logread.exe** no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="32562-247">To start the Log Reader Agent, execute **logread.exe** from the command prompt.</span></span> <span data-ttu-id="32562-248">Para obter informações, consulte [Conceitos dos executáveis do agente de replicação](../concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="32562-248">For information, see [Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md).</span></span>  
  
## <a name="change-history"></a><span data-ttu-id="32562-249">Histórico de alterações</span><span class="sxs-lookup"><span data-stu-id="32562-249">Change History</span></span>  
  
|<span data-ttu-id="32562-250">Conteúdo atualizado</span><span class="sxs-lookup"><span data-stu-id="32562-250">Updated content</span></span>|  
|---------------------|  
|<span data-ttu-id="32562-251">Adicionado o parâmetro **-ExtendedEventConfigFile** .</span><span class="sxs-lookup"><span data-stu-id="32562-251">Added the **-ExtendedEventConfigFile** parameter.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="32562-252">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="32562-252">See Also</span></span>  
 [<span data-ttu-id="32562-253">Administração do agente de replicação</span><span class="sxs-lookup"><span data-stu-id="32562-253">Replication Agent Administration</span></span>](replication-agent-administration.md)  
  
  
