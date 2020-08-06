---
title: Agente de Leitor de Fila de Replicação | Microsoft Docs
ms.custom: ''
ms.date: 10/29/2018
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- agents [SQL Server replication], Queue Reader Agent
- command prompt [SQL Server replication]
- Queue Reader Agent, parameter reference
- Queue Reader Agent, executables
ms.assetid: 8e227793-11f6-47c6-99dc-ffc282f5d4bf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 854c425db3fbaa346dab5eb2c41bd58cf03f65c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569958"
---
# <a name="replication-queue-reader-agent"></a><span data-ttu-id="e08eb-102">Agente de Leitor de Fila de Replicação</span><span class="sxs-lookup"><span data-stu-id="e08eb-102">Replication Queue Reader Agent</span></span>
  <span data-ttu-id="e08eb-103">O Queue Reader Agent de Replicação é um executável que lê mensagens armazenadas em uma fila do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ou uma Fila de Mensagens da [!INCLUDE[msCoName](../../../includes/msconame-md.md)] e, em seguida, aplica essas mensagens ao Publicador.</span><span class="sxs-lookup"><span data-stu-id="e08eb-103">The Replication Queue Reader Agent is an executable that reads messages stored in a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] queue or a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Message Queue and then applies those messages to the Publisher.</span></span> <span data-ttu-id="e08eb-104">O Queue Reader Agent é usado com publicações de instantâneo e transacionais que permitem atualização em fila.</span><span class="sxs-lookup"><span data-stu-id="e08eb-104">Queue Reader Agent is used with snapshot and transactional publications that allow queued updating.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e08eb-105">Os parâmetros podem ser especificados em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="e08eb-105">Parameters can be specified in any order.</span></span> <span data-ttu-id="e08eb-106">Quando não são especificados parâmetros opcionais, são usados valores predefinidos com base no perfil de agente padrão.</span><span class="sxs-lookup"><span data-stu-id="e08eb-106">When optional parameters are not specified, predefined values based on the default agent profile are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e08eb-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e08eb-107">Syntax</span></span>  
  
```  
  
      qrdrsvc [-?]  
[-Continuous]  
[-DefinitionFiledefinition_file]  
[-Distributorserver_name[\instance_name]]  
[-DistributionDBdistribution_database]  
[-DistributorLogindistributor_login]  
[-DistributorPassworddistributor_password]  
[-DistributorSecurityMode [0|1]]  
[-EncryptionLevel [0|1|2]]  
[-HistoryVerboseLevel [0|1|2|3]]  
[-LoginTimeOutlogin_time_out_seconds]  
[-Outputoutput_path_and_file_name]  
[-OutputVerboseLevel [0|1|2]]  
[-PollingIntervalpolling_interval]  
[-PublisherFailoverPartnerserver_name[\instance_name] ]  
[-ProfileNameagent_profile_name]  
[-QueryTimeOutquery_time_out_seconds]  
[-ResolverState [1|2|3]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="e08eb-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e08eb-108">Arguments</span></span>  
 <span data-ttu-id="e08eb-109">**-?**</span><span class="sxs-lookup"><span data-stu-id="e08eb-109">**-?**</span></span>  
 <span data-ttu-id="e08eb-110">Exibe informações de uso.</span><span class="sxs-lookup"><span data-stu-id="e08eb-110">Displays usage information.</span></span>  
  
 <span data-ttu-id="e08eb-111">**-Continuous**</span><span class="sxs-lookup"><span data-stu-id="e08eb-111">**-Continuous**</span></span>  
 <span data-ttu-id="e08eb-112">Especifica se o agente tenta processar transações em fila continuamente.</span><span class="sxs-lookup"><span data-stu-id="e08eb-112">Specifies whether the agent attempts to process queued transactions continuously.</span></span> <span data-ttu-id="e08eb-113">Se especificado, o agente continua a execução, mesmo que não haja transações na fila pendentes de nenhum dos assinantes.</span><span class="sxs-lookup"><span data-stu-id="e08eb-113">If specified, the agent continues execution even if there are no queued transactions pending from any of the subscribers.</span></span>  
  
 <span data-ttu-id="e08eb-114">**-DefinitionFile** _def_path_and_file_name_</span><span class="sxs-lookup"><span data-stu-id="e08eb-114">**-DefinitionFile** _def_path_and_file_name_</span></span>  
 <span data-ttu-id="e08eb-115">É o caminho do arquivo de definição de agente.</span><span class="sxs-lookup"><span data-stu-id="e08eb-115">Is the path of the agent definition file.</span></span> <span data-ttu-id="e08eb-116">Um arquivo de definição de agente contém argumentos de linha de comando para o agente.</span><span class="sxs-lookup"><span data-stu-id="e08eb-116">An agent definition file contains command-line arguments for the agent.</span></span> <span data-ttu-id="e08eb-117">O conteúdo do arquivo é analisado como um arquivo executável.</span><span class="sxs-lookup"><span data-stu-id="e08eb-117">The content of the file is parsed as an executable file.</span></span> <span data-ttu-id="e08eb-118">Use aspas duplas (") para especificar valores de argumentos que contêm caracteres arbitrários.</span><span class="sxs-lookup"><span data-stu-id="e08eb-118">Use double quotation marks (") to specify argument values containing arbitrary characters.</span></span>  
  
 <span data-ttu-id="e08eb-119">**-Distributor** _server_name_[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="e08eb-119">**-Distributor** _server_name_[**\\**_instance_name_]</span></span>  
 <span data-ttu-id="e08eb-120">É o nome do Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="e08eb-120">Is the Distributor name.</span></span> <span data-ttu-id="e08eb-121">Especifica *server_name* para a instância padrão do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] naquele servidor.</span><span class="sxs-lookup"><span data-stu-id="e08eb-121">Specify *server_name* for the default instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on that server.</span></span> <span data-ttu-id="e08eb-122">Especifique *server_name*\\*instance_name* para uma instância nomeada do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] naquele servidor.</span><span class="sxs-lookup"><span data-stu-id="e08eb-122">Specify *server_name*\\*instance_name* for a named instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on that server.</span></span> <span data-ttu-id="e08eb-123">Se não for especificado, o nome assumirá o padrão do nome da instância padrão do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] no computador local.</span><span class="sxs-lookup"><span data-stu-id="e08eb-123">If not specified, the name defaults to the name of the default instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on the local computer.</span></span>  
  
 <span data-ttu-id="e08eb-124">**-DistributionDB** _distribution_database_</span><span class="sxs-lookup"><span data-stu-id="e08eb-124">**-DistributionDB** _distribution_database_</span></span>  
 <span data-ttu-id="e08eb-125">É o banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="e08eb-125">Is the distribution database.</span></span>  
  
 <span data-ttu-id="e08eb-126">**-DistributorLogin** _distributor_login_</span><span class="sxs-lookup"><span data-stu-id="e08eb-126">**-DistributorLogin** _distributor_login_</span></span>  
 <span data-ttu-id="e08eb-127">É o nome de logon do Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="e08eb-127">Is the Distributor login name.</span></span>  
  
 <span data-ttu-id="e08eb-128">**-DistributorPassword** _distributor_password_</span><span class="sxs-lookup"><span data-stu-id="e08eb-128">**-DistributorPassword** _distributor_password_</span></span>  
 <span data-ttu-id="e08eb-129">É a senha do Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="e08eb-129">Is the Distributor password.</span></span>  
  
 <span data-ttu-id="e08eb-130">**-DistributorSecurityMode** [ **0**| **1**]</span><span class="sxs-lookup"><span data-stu-id="e08eb-130">**-DistributorSecurityMode** [ **0**| **1**]</span></span>  
 <span data-ttu-id="e08eb-131">Especifica o modo de segurança do Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="e08eb-131">Specifies the security mode of the Distributor.</span></span> <span data-ttu-id="e08eb-132">Um valor de **0** indica Modo (padrão) de Autenticação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e um valor de **1** indica Modo de Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="e08eb-132">A value of **0** indicates [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication Mode (default), and a value of **1** indicates Windows Authentication Mode.</span></span>  
  
 <span data-ttu-id="e08eb-133">**-EncryptionLevel** [ **0** | **1** | **2** ]</span><span class="sxs-lookup"><span data-stu-id="e08eb-133">**-EncryptionLevel** [ **0** | **1** | **2** ]</span></span>  
 <span data-ttu-id="e08eb-134">É o nível da criptografia SSL (Secure Sockets Layer) usada pelo Queue Reader Agent ao fazer conexões.</span><span class="sxs-lookup"><span data-stu-id="e08eb-134">Is the level of Secure Sockets Layer (SSL) encryption used by the Queue Reader Agent when making connections.</span></span>  
  
|<span data-ttu-id="e08eb-135">Valor EncryptionLevel</span><span class="sxs-lookup"><span data-stu-id="e08eb-135">EncryptionLevel value</span></span>|<span data-ttu-id="e08eb-136">Descrição</span><span class="sxs-lookup"><span data-stu-id="e08eb-136">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="e08eb-137">**0**</span><span class="sxs-lookup"><span data-stu-id="e08eb-137">**0**</span></span>|<span data-ttu-id="e08eb-138">Especifica que o SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="e08eb-138">Specifies that SSL is not used.</span></span>|  
|<span data-ttu-id="e08eb-139">**1**</span><span class="sxs-lookup"><span data-stu-id="e08eb-139">**1**</span></span>|<span data-ttu-id="e08eb-140">Especifica que o SSL é usado, mas que +o agente não verifica se o certificado de servidor SSL é assinado por um emissor confiável.</span><span class="sxs-lookup"><span data-stu-id="e08eb-140">Specifies that SSL is used, but the agent does not verify that the SSL server certificate is signed by a trusted issuer.</span></span>|  
|<span data-ttu-id="e08eb-141">**2**</span><span class="sxs-lookup"><span data-stu-id="e08eb-141">**2**</span></span>|<span data-ttu-id="e08eb-142">Especifica que o SSL é usado, e que o certificado é verificado.</span><span class="sxs-lookup"><span data-stu-id="e08eb-142">Specifies that SSL is used, and that the certificate is verified.</span></span>|  

 > [!NOTE]  
 >  <span data-ttu-id="e08eb-143">É definido um certificado SSL válido com um nome de domínio totalmente qualificado do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e08eb-143">A valid SSL certificate is defined with a fully qualified domain name of the SQL Server.</span></span> <span data-ttu-id="e08eb-144">Para que o agente seja conectado com êxito ao definir -EncryptionLevel como 2, crie um alias no SQL Server local.</span><span class="sxs-lookup"><span data-stu-id="e08eb-144">In order for the agent to connect successfully when setting -EncryptionLevel to 2, create an alias on the local SQL Server.</span></span> <span data-ttu-id="e08eb-145">O parâmetro 'Alias Name' deve ser o nome do servidor e o parâmetro 'Server' deve ser definido como o nome totalmente qualificado do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e08eb-145">The 'Alias Name' parameter should be the server name and the 'Server' parameter should be set to the fully qualified name of the SQL Server.</span></span>
  
 <span data-ttu-id="e08eb-146">Para obter mais informações, consulte [replicação do SQL Server Security](../security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="e08eb-146">For more information, see [SQL Server Replication Security](../security/view-and-modify-replication-security-settings.md).</span></span>  
  
 <span data-ttu-id="e08eb-147">**-HistoryVerboseLevel** [ **0**| **1**| **2**| **3**]</span><span class="sxs-lookup"><span data-stu-id="e08eb-147">**-HistoryVerboseLevel** [ **0**| **1**| **2**| **3**]</span></span>  
 <span data-ttu-id="e08eb-148">Especifica a quantidade de histórico registrada durante uma operação de leitura de fila.</span><span class="sxs-lookup"><span data-stu-id="e08eb-148">Specifies the amount of history logged during a queue reader operation.</span></span> <span data-ttu-id="e08eb-149">Você pode minimizar o efeito de registro de histórico no desempenho selecionando **1**.</span><span class="sxs-lookup"><span data-stu-id="e08eb-149">You can minimize the effect of history logging on performance by selecting **1**.</span></span>  
  
|<span data-ttu-id="e08eb-150">Valor HistoryVerboseLevel</span><span class="sxs-lookup"><span data-stu-id="e08eb-150">HistoryVerboseLevel value</span></span>|<span data-ttu-id="e08eb-151">Descrição</span><span class="sxs-lookup"><span data-stu-id="e08eb-151">Description</span></span>|  
|-------------------------------|-----------------|  
|<span data-ttu-id="e08eb-152">**0**</span><span class="sxs-lookup"><span data-stu-id="e08eb-152">**0**</span></span>|<span data-ttu-id="e08eb-153">Nenhum log de histórico (não recomendado).</span><span class="sxs-lookup"><span data-stu-id="e08eb-153">No history logging (not recommended).</span></span>|  
|<span data-ttu-id="e08eb-154">**1**</span><span class="sxs-lookup"><span data-stu-id="e08eb-154">**1**</span></span>|<span data-ttu-id="e08eb-155">Padrão.</span><span class="sxs-lookup"><span data-stu-id="e08eb-155">Default.</span></span> <span data-ttu-id="e08eb-156">Sempre atualiza uma mensagem de histórico anterior do mesmo status (inicialização, andamento, êxito, etc.).</span><span class="sxs-lookup"><span data-stu-id="e08eb-156">Always update a previous history message of the same status (startup, progress, success, and so on).</span></span> <span data-ttu-id="e08eb-157">Se nenhum registro anterior com o mesmo status existir, insira um registro novo.</span><span class="sxs-lookup"><span data-stu-id="e08eb-157">If no previous record with the same status exists, insert a new record.</span></span>|  
|<span data-ttu-id="e08eb-158">**2**</span><span class="sxs-lookup"><span data-stu-id="e08eb-158">**2**</span></span>|<span data-ttu-id="e08eb-159">Insira novos registros de histórico, incluindo mensagens ociosas ou mensagens de trabalho de execução longa.</span><span class="sxs-lookup"><span data-stu-id="e08eb-159">Insert new history records, including idle messages or long-running job messages.</span></span>|  
|<span data-ttu-id="e08eb-160">**3**</span><span class="sxs-lookup"><span data-stu-id="e08eb-160">**3**</span></span>|<span data-ttu-id="e08eb-161">Insira novos registros de histórico que incluam detalhes adicionais que podem ser úteis na solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="e08eb-161">Insert new history records that include additional details that may be useful for troubleshooting.</span></span>|  
  
 <span data-ttu-id="e08eb-162">**-LoginTimeOut** _login_time_out_seconds_</span><span class="sxs-lookup"><span data-stu-id="e08eb-162">**-LoginTimeOut** _login_time_out_seconds_</span></span>  
 <span data-ttu-id="e08eb-163">É o número de segundos antes que o logon expire. O padrão é 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="e08eb-163">Is the number of seconds before the login times out. The default is 15 seconds.</span></span>  
  
 <span data-ttu-id="e08eb-164">**-Output** _output_path_and_file_name_</span><span class="sxs-lookup"><span data-stu-id="e08eb-164">**-Output** _output_path_and_file_name_</span></span>  
 <span data-ttu-id="e08eb-165">É o caminho do arquivo de saída do agente.</span><span class="sxs-lookup"><span data-stu-id="e08eb-165">Is the path of the agent output file.</span></span> <span data-ttu-id="e08eb-166">Se o nome de arquivo não for fornecido, a saída será enviada ao console.</span><span class="sxs-lookup"><span data-stu-id="e08eb-166">If the file name is not provided, the output is sent to the console.</span></span> <span data-ttu-id="e08eb-167">Se o nome do arquivo especificado existir, a saída será anexada ao arquivo.</span><span class="sxs-lookup"><span data-stu-id="e08eb-167">If the specified file name exists, the output is appended to the file.</span></span>  
  
 <span data-ttu-id="e08eb-168">**-OutputVerboseLevel** [ **0**| **1**| **2**]</span><span class="sxs-lookup"><span data-stu-id="e08eb-168">**-OutputVerboseLevel** [ **0**| **1**| **2**]</span></span>  
 <span data-ttu-id="e08eb-169">Especifica se a saída deve ser detalhada.</span><span class="sxs-lookup"><span data-stu-id="e08eb-169">Specifies whether the output should be verbose.</span></span> <span data-ttu-id="e08eb-170">Se o nível detalhado for **0**, só mensagens de erro serão impressas.</span><span class="sxs-lookup"><span data-stu-id="e08eb-170">If the verbose level is **0**, only error messages are printed.</span></span> <span data-ttu-id="e08eb-171">Se o nível detalhado for **1**, todas as mensagens de relatório de progresso serão impressas.</span><span class="sxs-lookup"><span data-stu-id="e08eb-171">If the verbose level is **1**, all the progress report messages are printed.</span></span> <span data-ttu-id="e08eb-172">Se o nível detalhado for **2** (padrão), todas as mensagens de erro e de relatório de progresso serão impressas, o que é útil na depuração.</span><span class="sxs-lookup"><span data-stu-id="e08eb-172">If the verbose level is **2** (default), all error messages and progress report messages are printed, which is useful for debugging.</span></span>  
  
 <span data-ttu-id="e08eb-173">**-PollingInterval** _polling_interval_</span><span class="sxs-lookup"><span data-stu-id="e08eb-173">**-PollingInterval** _polling_interval_</span></span>  
 <span data-ttu-id="e08eb-174">É relevante apenas para assinaturas de atualização que usam filas com base no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e08eb-174">Is relevant only for updating subscriptions that use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] based queues.</span></span> <span data-ttu-id="e08eb-175">Especifica com que frequência, em segundos, a fila do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] é sondada para transações em fila pendentes.</span><span class="sxs-lookup"><span data-stu-id="e08eb-175">Specifies how often, in seconds, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] queue is polled for pending queued transactions.</span></span> <span data-ttu-id="e08eb-176">O valor pode ser entre 0 e 240 segundos.</span><span class="sxs-lookup"><span data-stu-id="e08eb-176">The value can be between 0 and 240 seconds.</span></span> <span data-ttu-id="e08eb-177">O padrão é 5 segundos.</span><span class="sxs-lookup"><span data-stu-id="e08eb-177">The default is 5 seconds.</span></span>  
  
 <span data-ttu-id="e08eb-178">**-PublisherFailoverPartner** _server_name_[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="e08eb-178">**-PublisherFailoverPartner** _server_name_[**\\**_instance_name_]</span></span>  
 <span data-ttu-id="e08eb-179">Especifica a instância de parceiro de failover do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que participa de uma sessão de espelhamento de banco de dados com o banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="e08eb-179">Specifies the failover partner instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] participating in a database mirroring session with the publication database.</span></span> <span data-ttu-id="e08eb-180">Para obter mais informações, consulte [Espelhamento e replicação de banco de dados &#40;SQL Server&#41;](../../../database-engine/database-mirroring/database-mirroring-and-replication-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e08eb-180">For more information, see [Database Mirroring and Replication &#40;SQL Server&#41;](../../../database-engine/database-mirroring/database-mirroring-and-replication-sql-server.md).</span></span>  
  
 <span data-ttu-id="e08eb-181">**-ProfileName** _agent_profile_name_</span><span class="sxs-lookup"><span data-stu-id="e08eb-181">**-ProfileName** _agent_profile_name_</span></span>  
 <span data-ttu-id="e08eb-182">É o nome de um perfil de agente usado para fornecer um conjunto de valores padrão ao agente.</span><span class="sxs-lookup"><span data-stu-id="e08eb-182">Is the name of an agent profile used to supply a set of default values to the agent.</span></span> <span data-ttu-id="e08eb-183">Para obter mais informações, consulte [Perfis do agente de replicação](replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="e08eb-183">For information, see [Replication Agent Profiles](replication-agent-profiles.md).</span></span>  
  
 <span data-ttu-id="e08eb-184">**-QueryTimeOut** _query_time_out_seconds_</span><span class="sxs-lookup"><span data-stu-id="e08eb-184">**-QueryTimeOut** _query_time_out_seconds_</span></span>  
 <span data-ttu-id="e08eb-185">É o número de segundos antes que a consulta expire. O padrão é 1800 segundos.</span><span class="sxs-lookup"><span data-stu-id="e08eb-185">Is the number of seconds before the query times out. The default is 1800 seconds.</span></span>  
  
 <span data-ttu-id="e08eb-186">**-ResolverState** [ **1**| **2**| **3**]</span><span class="sxs-lookup"><span data-stu-id="e08eb-186">**-ResolverState** [ **1**| **2**| **3**]</span></span>  
 <span data-ttu-id="e08eb-187">Especifica como conflitos de atualização na fila são resolvidos.</span><span class="sxs-lookup"><span data-stu-id="e08eb-187">Specifies how queued updating conflicts are resolved.</span></span> <span data-ttu-id="e08eb-188">Um valor **1** indica que o Publicador ganha o conflito, a transação na fila conflitante será revertida no Publicador e no Assinante de atualização de origem e o processo de transações subsequentes em fila continuará.</span><span class="sxs-lookup"><span data-stu-id="e08eb-188">A value of **1** indicates the Publisher wins the conflict, and the current conflicting queued transaction will be rolled back on the Publisher and the originating updating Subscriber; the processing of subsequent queued transactions will continue.</span></span> <span data-ttu-id="e08eb-189">Um valor **2** indica que o Assinante ganha o conflito e a transação na fila substituirá os valores no Publicador.</span><span class="sxs-lookup"><span data-stu-id="e08eb-189">A value of **2** indicates the Subscriber wins the conflict, and the queued transaction will override the values on the Publisher.</span></span> <span data-ttu-id="e08eb-190">Um valor **3** indica que qualquer conflito resultará na reinicialização do Assinante; o Publicador ganha o conflito, o processamento de transações subsequentes na fila será interrompido e a assinatura será reiniciada.</span><span class="sxs-lookup"><span data-stu-id="e08eb-190">A value of **3** indicates that any conflict will result in Subscriber re-initialization; the Publisher wins the conflict, processing of subsequent queued transactions will be terminated, and the subscription will be reinitialized.</span></span> <span data-ttu-id="e08eb-191">A configuração padrão é **1** para publicações transacionais e **3** para publicações de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="e08eb-191">The default setting is **1** for transactional publications and **3** for snapshot publications.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e08eb-192">Comentários</span><span class="sxs-lookup"><span data-stu-id="e08eb-192">Remarks</span></span>  
 <span data-ttu-id="e08eb-193">Para iniciar o Queue Reader Agent, execute **qrdrsvc.exe** no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="e08eb-193">To start the Queue Reader Agent, execute **qrdrsvc.exe** from the command prompt.</span></span> <span data-ttu-id="e08eb-194">Para obter informações, consulte [Executáveis do agente de replicação](../concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="e08eb-194">For information, see [Replication Agent Executables](../concepts/replication-agent-executables-concepts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e08eb-195">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e08eb-195">See Also</span></span>  
 [<span data-ttu-id="e08eb-196">Administração do agente de replicação</span><span class="sxs-lookup"><span data-stu-id="e08eb-196">Replication Agent Administration</span></span>](replication-agent-administration.md)  
  
  
