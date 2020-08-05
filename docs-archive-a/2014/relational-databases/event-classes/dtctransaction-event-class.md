---
title: Classe de evento DTCTransaction| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- DTCTransaction event class
ms.assetid: 9a2d358e-5b8f-4d0b-8b93-6705c009ad57
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1c72b8c718237582f5a40c56e40e2a51e79e177e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573017"
---
# <a name="dtctransaction-event-class"></a><span data-ttu-id="0a767-102">classe de evento DTCTransaction</span><span class="sxs-lookup"><span data-stu-id="0a767-102">DTCTransaction Event Class</span></span>
  <span data-ttu-id="0a767-103">Use a classe de evento **DTCTransaction** para monitorar o estado de transações do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] coordenado pelo MS DTC (Coordenador de Transações Distribuídas da [!INCLUDE[msCoName](../../includes/msconame-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="0a767-103">Use the **DTCTransaction** event class to monitor the state of [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] transactions coordinated through [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (DTC).</span></span> <span data-ttu-id="0a767-104">Isso inclui transações que envolvem dois ou mais bancos de dados na mesma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)]ou transações distribuídas que envolvem duas ou mais instâncias do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a767-104">This includes transactions involving two or more databases in the same instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], or distributed transactions involving two or more instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
## <a name="dtctransaction-event-class-data-columns"></a><span data-ttu-id="0a767-105">Colunas de dados da classe de evento DTCTransaction</span><span class="sxs-lookup"><span data-stu-id="0a767-105">DTCTransaction Event Class Data Columns</span></span>  
  
|<span data-ttu-id="0a767-106">Nome da coluna de dados</span><span class="sxs-lookup"><span data-stu-id="0a767-106">Data column name</span></span>|<span data-ttu-id="0a767-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="0a767-107">Data type</span></span>|<span data-ttu-id="0a767-108">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="0a767-108">Description</span></span>|<span data-ttu-id="0a767-109">ID da coluna</span><span class="sxs-lookup"><span data-stu-id="0a767-109">Column ID</span></span>|<span data-ttu-id="0a767-110">Filtrável</span><span class="sxs-lookup"><span data-stu-id="0a767-110">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="0a767-111">**ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="0a767-111">**ApplicationName**</span></span>|`nvarchar`|<span data-ttu-id="0a767-112">Nome do aplicativo cliente que criou a conexão com uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a767-112">Name of the client application that created the connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0a767-113">Essa coluna é populada com os valores passados pelo aplicativo e não com o nome exibido do programa.</span><span class="sxs-lookup"><span data-stu-id="0a767-113">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="0a767-114">10</span><span class="sxs-lookup"><span data-stu-id="0a767-114">10</span></span>|<span data-ttu-id="0a767-115">Sim</span><span class="sxs-lookup"><span data-stu-id="0a767-115">Yes</span></span>|  
|<span data-ttu-id="0a767-116">**BinaryData**</span><span class="sxs-lookup"><span data-stu-id="0a767-116">**BinaryData**</span></span>|`image`|<span data-ttu-id="0a767-117">Representação binária da ID da UOW (Unidade de Trabalho) que identifica exclusivamente essa transação dentro do DTC.</span><span class="sxs-lookup"><span data-stu-id="0a767-117">Binary representation of the Unit of Work ID (UOW) that uniquely identifies this transaction within DTC.</span></span>|<span data-ttu-id="0a767-118">2</span><span class="sxs-lookup"><span data-stu-id="0a767-118">2</span></span>|<span data-ttu-id="0a767-119">Sim</span><span class="sxs-lookup"><span data-stu-id="0a767-119">Yes</span></span>|  
|<span data-ttu-id="0a767-120">**ClientProcessID**</span><span class="sxs-lookup"><span data-stu-id="0a767-120">**ClientProcessID**</span></span>|`int`|<span data-ttu-id="0a767-121">ID atribuída pelo computador host ao processo em que o aplicativo cliente está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="0a767-121">ID assigned by the host computer to the process where the client application is running.</span></span> <span data-ttu-id="0a767-122">Essa coluna de dados será populada se o cliente fornecer a ID de processo do cliente.</span><span class="sxs-lookup"><span data-stu-id="0a767-122">This data column is populated if the client provides the client process ID.</span></span>|<span data-ttu-id="0a767-123">9</span><span class="sxs-lookup"><span data-stu-id="0a767-123">9</span></span>|<span data-ttu-id="0a767-124">Sim</span><span class="sxs-lookup"><span data-stu-id="0a767-124">Yes</span></span>|  
|<span data-ttu-id="0a767-125">**DatabaseID**</span><span class="sxs-lookup"><span data-stu-id="0a767-125">**DatabaseID**</span></span>|`int`|<span data-ttu-id="0a767-126">ID do banco de dados especificado pela instrução USE de *database* ou o banco de dados padrão se nenhuma instrução USE de *database* tiver sido emitida para uma determinada instância.</span><span class="sxs-lookup"><span data-stu-id="0a767-126">ID of the database specified by the USE *database* statement or the default database if no USE *database* statement has been issued for a given instance.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="0a767-127">exibirá o nome do banco de dados se a coluna de dados **ServerName** for capturada no rastreamento e o servidor estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="0a767-127">displays the name of the database if the **ServerName** data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="0a767-128">Determine o valor para um banco de dados usando a função DB_ID.</span><span class="sxs-lookup"><span data-stu-id="0a767-128">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="0a767-129">3</span><span class="sxs-lookup"><span data-stu-id="0a767-129">3</span></span>|<span data-ttu-id="0a767-130">Sim</span><span class="sxs-lookup"><span data-stu-id="0a767-130">Yes</span></span>|  
|<span data-ttu-id="0a767-131">**DatabaseName**</span><span class="sxs-lookup"><span data-stu-id="0a767-131">**DatabaseName**</span></span>|`nvarchar`|<span data-ttu-id="0a767-132">Nome do banco de dados no qual a instrução do usuário está sendo executada.</span><span class="sxs-lookup"><span data-stu-id="0a767-132">Name of the database in which the user statement is running.</span></span>|<span data-ttu-id="0a767-133">35</span><span class="sxs-lookup"><span data-stu-id="0a767-133">35</span></span>|<span data-ttu-id="0a767-134">Sim</span><span class="sxs-lookup"><span data-stu-id="0a767-134">Yes</span></span>|  
|<span data-ttu-id="0a767-135">**EventClass**</span><span class="sxs-lookup"><span data-stu-id="0a767-135">**EventClass**</span></span>|`int`|<span data-ttu-id="0a767-136">Tipo de evento = 19.</span><span class="sxs-lookup"><span data-stu-id="0a767-136">Type of event = 19.</span></span>|<span data-ttu-id="0a767-137">27</span><span class="sxs-lookup"><span data-stu-id="0a767-137">27</span></span>|<span data-ttu-id="0a767-138">Não</span><span class="sxs-lookup"><span data-stu-id="0a767-138">No</span></span>|  
|<span data-ttu-id="0a767-139">**EventSequence**</span><span class="sxs-lookup"><span data-stu-id="0a767-139">**EventSequence**</span></span>|`int`|<span data-ttu-id="0a767-140">Sequência de um determinado evento na solicitação.</span><span class="sxs-lookup"><span data-stu-id="0a767-140">Sequence of a given event within the request.</span></span>|<span data-ttu-id="0a767-141">51</span><span class="sxs-lookup"><span data-stu-id="0a767-141">51</span></span>|<span data-ttu-id="0a767-142">Não</span><span class="sxs-lookup"><span data-stu-id="0a767-142">No</span></span>|  
|<span data-ttu-id="0a767-143">**EventSubClass**</span><span class="sxs-lookup"><span data-stu-id="0a767-143">**EventSubClass**</span></span>|`int`|<span data-ttu-id="0a767-144">Tipo de subclasse de evento.</span><span class="sxs-lookup"><span data-stu-id="0a767-144">Type of event subclass.</span></span><br /><br /> <span data-ttu-id="0a767-145">0=Obter endereço</span><span class="sxs-lookup"><span data-stu-id="0a767-145">0=Get address</span></span><br /><br /> <span data-ttu-id="0a767-146">1=Propagar transação</span><span class="sxs-lookup"><span data-stu-id="0a767-146">1=Propagate Transaction</span></span><br /><br /> <span data-ttu-id="0a767-147">3=Fechar conexão</span><span class="sxs-lookup"><span data-stu-id="0a767-147">3=Close connection</span></span><br /><br /> <span data-ttu-id="0a767-148">6=Criar uma nova transação DTC</span><span class="sxs-lookup"><span data-stu-id="0a767-148">6=Creating a new DTC transaction</span></span><br /><br /> <span data-ttu-id="0a767-149">7=Inscrição em uma transação DTC</span><span class="sxs-lookup"><span data-stu-id="0a767-149">7=Enlisting in a DTC transaction</span></span><br /><br /> <span data-ttu-id="0a767-150">9=Confirmação interna</span><span class="sxs-lookup"><span data-stu-id="0a767-150">9=Internal commit</span></span><br /><br /> <span data-ttu-id="0a767-151">10=Anulação interna</span><span class="sxs-lookup"><span data-stu-id="0a767-151">10=Internal abort</span></span><br /><br /> <span data-ttu-id="0a767-152">14= Transação sendo preparada</span><span class="sxs-lookup"><span data-stu-id="0a767-152">14=Preparing Transaction</span></span><br /><br /> <span data-ttu-id="0a767-153">15=Transação preparada</span><span class="sxs-lookup"><span data-stu-id="0a767-153">15=Transaction is prepared</span></span><br /><br /> <span data-ttu-id="0a767-154">16=Transação sendo anulada</span><span class="sxs-lookup"><span data-stu-id="0a767-154">16=Transaction is aborting</span></span><br /><br /> <span data-ttu-id="0a767-155">17=Transação sendo confirmada</span><span class="sxs-lookup"><span data-stu-id="0a767-155">17=Transaction is committing</span></span><br /><br /> <span data-ttu-id="0a767-156">22=Falha da TM no estado preparado</span><span class="sxs-lookup"><span data-stu-id="0a767-156">22=TM failed while in prepared state</span></span><br /><br /> <span data-ttu-id="0a767-157">23=Desconhecido</span><span class="sxs-lookup"><span data-stu-id="0a767-157">23=Unknown</span></span>|<span data-ttu-id="0a767-158">21</span><span class="sxs-lookup"><span data-stu-id="0a767-158">21</span></span>|<span data-ttu-id="0a767-159">Sim</span><span class="sxs-lookup"><span data-stu-id="0a767-159">Yes</span></span>|  
|<span data-ttu-id="0a767-160">**GroupID**</span><span class="sxs-lookup"><span data-stu-id="0a767-160">**GroupID**</span></span>|`int`|<span data-ttu-id="0a767-161">ID do grupo de carga de trabalho no qual o evento de Rastreamento do SQL dispara.</span><span class="sxs-lookup"><span data-stu-id="0a767-161">ID of the workload group where the SQL Trace event fires.</span></span>|<span data-ttu-id="0a767-162">66</span><span class="sxs-lookup"><span data-stu-id="0a767-162">66</span></span>|<span data-ttu-id="0a767-163">Sim</span><span class="sxs-lookup"><span data-stu-id="0a767-163">Yes</span></span>|  
|<span data-ttu-id="0a767-164">**HostName**</span><span class="sxs-lookup"><span data-stu-id="0a767-164">**HostName**</span></span>|`nvarchar`|<span data-ttu-id="0a767-165">Nome do computador no qual o cliente está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="0a767-165">Name of the computer on which the client is running.</span></span> <span data-ttu-id="0a767-166">Essa coluna de dados será populada se o cliente fornecer o nome do host.</span><span class="sxs-lookup"><span data-stu-id="0a767-166">This data column is populated if the client provides the host name.</span></span> <span data-ttu-id="0a767-167">Para determinar o nome do host, use a função HOST_NAME.</span><span class="sxs-lookup"><span data-stu-id="0a767-167">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="0a767-168">8</span><span class="sxs-lookup"><span data-stu-id="0a767-168">8</span></span>|<span data-ttu-id="0a767-169">Sim</span><span class="sxs-lookup"><span data-stu-id="0a767-169">Yes</span></span>|  
|<span data-ttu-id="0a767-170">**IntegerData**</span><span class="sxs-lookup"><span data-stu-id="0a767-170">**IntegerData**</span></span>|`int`|<span data-ttu-id="0a767-171">Nível de isolamento da transação:</span><span class="sxs-lookup"><span data-stu-id="0a767-171">Isolation level of the transaction.</span></span>|<span data-ttu-id="0a767-172">25</span><span class="sxs-lookup"><span data-stu-id="0a767-172">25</span></span>|<span data-ttu-id="0a767-173">Sim</span><span class="sxs-lookup"><span data-stu-id="0a767-173">Yes</span></span>|  
|<span data-ttu-id="0a767-174">**IsSystem**</span><span class="sxs-lookup"><span data-stu-id="0a767-174">**IsSystem**</span></span>|`int`|<span data-ttu-id="0a767-175">Indica se o evento ocorreu em um processo do sistema ou do usuário.</span><span class="sxs-lookup"><span data-stu-id="0a767-175">Indicates whether the event occurred on a system process or a user process.</span></span> <span data-ttu-id="0a767-176">1 = sistema, 0 = usuário.</span><span class="sxs-lookup"><span data-stu-id="0a767-176">1 = system, 0 = user.</span></span>|<span data-ttu-id="0a767-177">60</span><span class="sxs-lookup"><span data-stu-id="0a767-177">60</span></span>|<span data-ttu-id="0a767-178">Sim</span><span class="sxs-lookup"><span data-stu-id="0a767-178">Yes</span></span>|  
|<span data-ttu-id="0a767-179">**LoginName**</span><span class="sxs-lookup"><span data-stu-id="0a767-179">**LoginName**</span></span>|`nvarchar`|<span data-ttu-id="0a767-180">Nome do logon do usuário (logon de segurança do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou as credenciais de logon do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows no formato DOMÍNIO\nomedeusuário).</span><span class="sxs-lookup"><span data-stu-id="0a767-180">Name of the login of the user (either the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security login or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows login credentials in the form of DOMAIN\username).</span></span>|<span data-ttu-id="0a767-181">11</span><span class="sxs-lookup"><span data-stu-id="0a767-181">11</span></span>|<span data-ttu-id="0a767-182">Sim</span><span class="sxs-lookup"><span data-stu-id="0a767-182">Yes</span></span>|  
|<span data-ttu-id="0a767-183">**LoginSid**</span><span class="sxs-lookup"><span data-stu-id="0a767-183">**LoginSid**</span></span>|`image`|<span data-ttu-id="0a767-184">Número SID (identificação de segurança) do usuário que fez logon.</span><span class="sxs-lookup"><span data-stu-id="0a767-184">Security identification number (SID) of the logged-in user.</span></span> <span data-ttu-id="0a767-185">Você pode encontrar essas informações na exibição de catálogo **sys.server_principals** .</span><span class="sxs-lookup"><span data-stu-id="0a767-185">You can find this information in the **sys.server_principals** catalog view.</span></span> <span data-ttu-id="0a767-186">Cada SID é exclusivo para cada logon no servidor.</span><span class="sxs-lookup"><span data-stu-id="0a767-186">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="0a767-187">41</span><span class="sxs-lookup"><span data-stu-id="0a767-187">41</span></span>|<span data-ttu-id="0a767-188">Sim</span><span class="sxs-lookup"><span data-stu-id="0a767-188">Yes</span></span>|  
|<span data-ttu-id="0a767-189">**NTDomainName**</span><span class="sxs-lookup"><span data-stu-id="0a767-189">**NTDomainName**</span></span>|`nvarchar`|<span data-ttu-id="0a767-190">O domínio do Windows ao qual o usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="0a767-190">Windows domain to which the user belongs.</span></span>|<span data-ttu-id="0a767-191">7</span><span class="sxs-lookup"><span data-stu-id="0a767-191">7</span></span>|<span data-ttu-id="0a767-192">Sim</span><span class="sxs-lookup"><span data-stu-id="0a767-192">Yes</span></span>|  
|<span data-ttu-id="0a767-193">**NTUserName**</span><span class="sxs-lookup"><span data-stu-id="0a767-193">**NTUserName**</span></span>|`nvarchar`|<span data-ttu-id="0a767-194">Nome do usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="0a767-194">Windows user name.</span></span>|<span data-ttu-id="0a767-195">6</span><span class="sxs-lookup"><span data-stu-id="0a767-195">6</span></span>|<span data-ttu-id="0a767-196">Sim</span><span class="sxs-lookup"><span data-stu-id="0a767-196">Yes</span></span>|  
|<span data-ttu-id="0a767-197">**RequestID**</span><span class="sxs-lookup"><span data-stu-id="0a767-197">**RequestID**</span></span>|`int`|<span data-ttu-id="0a767-198">ID da solicitação que contém a instrução.</span><span class="sxs-lookup"><span data-stu-id="0a767-198">ID of the request containing the statement.</span></span>|<span data-ttu-id="0a767-199">49</span><span class="sxs-lookup"><span data-stu-id="0a767-199">49</span></span>|<span data-ttu-id="0a767-200">Sim</span><span class="sxs-lookup"><span data-stu-id="0a767-200">Yes</span></span>|  
|<span data-ttu-id="0a767-201">**ServerName**</span><span class="sxs-lookup"><span data-stu-id="0a767-201">**ServerName**</span></span>|`nvarchar`|<span data-ttu-id="0a767-202">Nome da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que está sendo rastreada.</span><span class="sxs-lookup"><span data-stu-id="0a767-202">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="0a767-203">26</span><span class="sxs-lookup"><span data-stu-id="0a767-203">26</span></span>|<span data-ttu-id="0a767-204">Não</span><span class="sxs-lookup"><span data-stu-id="0a767-204">No</span></span>|  
|<span data-ttu-id="0a767-205">**SessionLoginName**</span><span class="sxs-lookup"><span data-stu-id="0a767-205">**SessionLoginName**</span></span>|`nvarchar`|<span data-ttu-id="0a767-206">Nome de logon do usuário que originou a sessão.</span><span class="sxs-lookup"><span data-stu-id="0a767-206">Login name of the user who originated the session.</span></span> <span data-ttu-id="0a767-207">Por exemplo, para se conectar ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando o Logon1 e executar uma instrução como Logon2, o **SessionLoginName** mostrará o Logon1 e o **LoginName** mostrará o Logon2.</span><span class="sxs-lookup"><span data-stu-id="0a767-207">For example, if you connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and execute a statement as Login2, **SessionLoginName** shows Login1 and **LoginName** shows Login2.</span></span> <span data-ttu-id="0a767-208">Essa coluna exibe logons do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e do Windows.</span><span class="sxs-lookup"><span data-stu-id="0a767-208">This column displays both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="0a767-209">64</span><span class="sxs-lookup"><span data-stu-id="0a767-209">64</span></span>|<span data-ttu-id="0a767-210">Sim</span><span class="sxs-lookup"><span data-stu-id="0a767-210">Yes</span></span>|  
|<span data-ttu-id="0a767-211">**SPID**</span><span class="sxs-lookup"><span data-stu-id="0a767-211">**SPID**</span></span>|`int`|<span data-ttu-id="0a767-212">Identificação da sessão em que ocorreu o evento.</span><span class="sxs-lookup"><span data-stu-id="0a767-212">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="0a767-213">12</span><span class="sxs-lookup"><span data-stu-id="0a767-213">12</span></span>|<span data-ttu-id="0a767-214">Sim</span><span class="sxs-lookup"><span data-stu-id="0a767-214">Yes</span></span>|  
|<span data-ttu-id="0a767-215">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="0a767-215">**StartTime**</span></span>|`datetime`|<span data-ttu-id="0a767-216">Horário de início do evento, quando disponível.</span><span class="sxs-lookup"><span data-stu-id="0a767-216">Time at which the event started, when available.</span></span>|<span data-ttu-id="0a767-217">14</span><span class="sxs-lookup"><span data-stu-id="0a767-217">14</span></span>|<span data-ttu-id="0a767-218">Sim</span><span class="sxs-lookup"><span data-stu-id="0a767-218">Yes</span></span>|  
|<span data-ttu-id="0a767-219">**TextData**</span><span class="sxs-lookup"><span data-stu-id="0a767-219">**TextData**</span></span>|`ntext`|<span data-ttu-id="0a767-220">Representação textual da UOW (Unidade de Trabalho) que identifica exclusivamente essa transação dentro do DTC.</span><span class="sxs-lookup"><span data-stu-id="0a767-220">Textual representation of the UOW that uniquely identifies this transaction within DTC.</span></span>|<span data-ttu-id="0a767-221">1</span><span class="sxs-lookup"><span data-stu-id="0a767-221">1</span></span>|<span data-ttu-id="0a767-222">Sim</span><span class="sxs-lookup"><span data-stu-id="0a767-222">Yes</span></span>|  
|<span data-ttu-id="0a767-223">**TransactionID**</span><span class="sxs-lookup"><span data-stu-id="0a767-223">**TransactionID**</span></span>|`bigint`|<span data-ttu-id="0a767-224">ID da transação atribuída pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="0a767-224">System-assigned ID of the transaction.</span></span>|<span data-ttu-id="0a767-225">4</span><span class="sxs-lookup"><span data-stu-id="0a767-225">4</span></span>|<span data-ttu-id="0a767-226">Sim</span><span class="sxs-lookup"><span data-stu-id="0a767-226">Yes</span></span>|  
|<span data-ttu-id="0a767-227">**XactSequence**</span><span class="sxs-lookup"><span data-stu-id="0a767-227">**XactSequence**</span></span>|`bigint`|<span data-ttu-id="0a767-228">Token usado para descrever a transação atual.</span><span class="sxs-lookup"><span data-stu-id="0a767-228">Token used to describe the current transaction.</span></span>|<span data-ttu-id="0a767-229">50</span><span class="sxs-lookup"><span data-stu-id="0a767-229">50</span></span>|<span data-ttu-id="0a767-230">Sim</span><span class="sxs-lookup"><span data-stu-id="0a767-230">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0a767-231">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0a767-231">See Also</span></span>  
 <span data-ttu-id="0a767-232">[Eventos estendidos](../extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="0a767-232">[Extended Events](../extended-events/extended-events.md) </span></span>  
 [<span data-ttu-id="0a767-233">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0a767-233">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  