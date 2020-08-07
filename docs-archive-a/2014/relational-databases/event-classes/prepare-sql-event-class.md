---
title: Preparar a classe de evento SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Prepare SQL event class
ms.assetid: 4ff3aa04-0f1a-49e2-a43d-7251bab4a458
author: stevestein
ms.author: sstein
ms.openlocfilehash: aaeaa6aee7fa61527180290ac22a584ed22f5178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575812"
---
# <a name="prepare-sql-event-class"></a><span data-ttu-id="f9710-102">classe de evento Prepare SQL</span><span class="sxs-lookup"><span data-stu-id="f9710-102">Prepare SQL Event Class</span></span>
  <span data-ttu-id="f9710-103">A classe de evento Prepare SQL indica que SqlClient, ODBC, OLE DB ou DB-Library preparou uma ou mais instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] a serem usadas.</span><span class="sxs-lookup"><span data-stu-id="f9710-103">The Prepare SQL event class indicates that SqlClient, ODBC, OLE DB, or DB-Library has prepared a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or statements for use.</span></span>  
  
## <a name="prepare-sql-event-class-data-columns"></a><span data-ttu-id="f9710-104">Colunas de dados da classe de evento Prepare SQL</span><span class="sxs-lookup"><span data-stu-id="f9710-104">Prepare SQL Event Class Data Columns</span></span>  
  
|<span data-ttu-id="f9710-105">Nome da coluna de dados</span><span class="sxs-lookup"><span data-stu-id="f9710-105">Data column name</span></span>|<span data-ttu-id="f9710-106">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="f9710-106">Data type</span></span>|<span data-ttu-id="f9710-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="f9710-107">Description</span></span>|<span data-ttu-id="f9710-108">ID da coluna</span><span class="sxs-lookup"><span data-stu-id="f9710-108">Column ID</span></span>|<span data-ttu-id="f9710-109">Filtrável</span><span class="sxs-lookup"><span data-stu-id="f9710-109">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="f9710-110">ApplicationName</span><span class="sxs-lookup"><span data-stu-id="f9710-110">ApplicationName</span></span>|`nvarchar`|<span data-ttu-id="f9710-111">Nome do aplicativo cliente que criou a conexão com uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9710-111">Name of the client application that created the connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f9710-112">Essa coluna é populada com os valores passados pelo aplicativo e não com o nome exibido do programa.</span><span class="sxs-lookup"><span data-stu-id="f9710-112">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="f9710-113">10</span><span class="sxs-lookup"><span data-stu-id="f9710-113">10</span></span>|<span data-ttu-id="f9710-114">Sim</span><span class="sxs-lookup"><span data-stu-id="f9710-114">Yes</span></span>|  
|<span data-ttu-id="f9710-115">ClientProcessID</span><span class="sxs-lookup"><span data-stu-id="f9710-115">ClientProcessID</span></span>|`int`|<span data-ttu-id="f9710-116">ID atribuída pelo computador host ao processo em que o aplicativo cliente está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="f9710-116">ID assigned by the host computer to the process where the client application is running.</span></span> <span data-ttu-id="f9710-117">Essa coluna de dados será populada se o cliente fornecer a ID de processo do cliente.</span><span class="sxs-lookup"><span data-stu-id="f9710-117">This data column is populated if the client provides the client process ID.</span></span>|<span data-ttu-id="f9710-118">9</span><span class="sxs-lookup"><span data-stu-id="f9710-118">9</span></span>|<span data-ttu-id="f9710-119">Sim</span><span class="sxs-lookup"><span data-stu-id="f9710-119">Yes</span></span>|  
|<span data-ttu-id="f9710-120">DatabaseID</span><span class="sxs-lookup"><span data-stu-id="f9710-120">DatabaseID</span></span>|`int`|<span data-ttu-id="f9710-121">ID do banco de dados especificado pela instrução USE de *database* ou o banco de dados padrão se nenhuma instrução USE de *database* tiver sido emitida para uma determinada instância.</span><span class="sxs-lookup"><span data-stu-id="f9710-121">ID of the database specified by the USE *database* statement or the default database if no USE *database* statement has been issued for a given instance.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="f9710-122">exibirá o nome do banco de dados se a coluna de dados ServerName for capturada no rastreamento e o servidor estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="f9710-122">displays the name of the database if the ServerName data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="f9710-123">Determine o valor para um banco de dados usando a função DB_ID.</span><span class="sxs-lookup"><span data-stu-id="f9710-123">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="f9710-124">3</span><span class="sxs-lookup"><span data-stu-id="f9710-124">3</span></span>|<span data-ttu-id="f9710-125">Sim</span><span class="sxs-lookup"><span data-stu-id="f9710-125">Yes</span></span>|  
|<span data-ttu-id="f9710-126">DatabaseName</span><span class="sxs-lookup"><span data-stu-id="f9710-126">DatabaseName</span></span>|`nvarchar`|<span data-ttu-id="f9710-127">Nome do banco de dados no qual a instrução do usuário está sendo executada.</span><span class="sxs-lookup"><span data-stu-id="f9710-127">Name of the database in which the user statement is running.</span></span>|<span data-ttu-id="f9710-128">35</span><span class="sxs-lookup"><span data-stu-id="f9710-128">35</span></span>|<span data-ttu-id="f9710-129">Sim</span><span class="sxs-lookup"><span data-stu-id="f9710-129">Yes</span></span>|  
|<span data-ttu-id="f9710-130">EventClass</span><span class="sxs-lookup"><span data-stu-id="f9710-130">EventClass</span></span>|`int`|<span data-ttu-id="f9710-131">Tipo de evento = 71.</span><span class="sxs-lookup"><span data-stu-id="f9710-131">Type of event = 71.</span></span>|<span data-ttu-id="f9710-132">27</span><span class="sxs-lookup"><span data-stu-id="f9710-132">27</span></span>|<span data-ttu-id="f9710-133">Não</span><span class="sxs-lookup"><span data-stu-id="f9710-133">No</span></span>|  
|<span data-ttu-id="f9710-134">EventSequence</span><span class="sxs-lookup"><span data-stu-id="f9710-134">EventSequence</span></span>|`int`|<span data-ttu-id="f9710-135">Sequência de um determinado evento na solicitação.</span><span class="sxs-lookup"><span data-stu-id="f9710-135">Sequence of a given event within the request.</span></span>|<span data-ttu-id="f9710-136">51</span><span class="sxs-lookup"><span data-stu-id="f9710-136">51</span></span>|<span data-ttu-id="f9710-137">Não</span><span class="sxs-lookup"><span data-stu-id="f9710-137">No</span></span>|  
|<span data-ttu-id="f9710-138">GroupID</span><span class="sxs-lookup"><span data-stu-id="f9710-138">GroupID</span></span>|`int`|<span data-ttu-id="f9710-139">ID do grupo de carga de trabalho no qual o evento de Rastreamento do SQL dispara.</span><span class="sxs-lookup"><span data-stu-id="f9710-139">ID of the workload group where the SQL Trace event fires.</span></span>|<span data-ttu-id="f9710-140">66</span><span class="sxs-lookup"><span data-stu-id="f9710-140">66</span></span>|<span data-ttu-id="f9710-141">Sim</span><span class="sxs-lookup"><span data-stu-id="f9710-141">Yes</span></span>|  
|<span data-ttu-id="f9710-142">Handle</span><span class="sxs-lookup"><span data-stu-id="f9710-142">Handle</span></span>|`int`|<span data-ttu-id="f9710-143">Identificador da instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] preparada.</span><span class="sxs-lookup"><span data-stu-id="f9710-143">Handle of the prepared [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>|<span data-ttu-id="f9710-144">33</span><span class="sxs-lookup"><span data-stu-id="f9710-144">33</span></span>|<span data-ttu-id="f9710-145">Sim</span><span class="sxs-lookup"><span data-stu-id="f9710-145">Yes</span></span>|  
|<span data-ttu-id="f9710-146">HostName</span><span class="sxs-lookup"><span data-stu-id="f9710-146">HostName</span></span>|`nvarchar`|<span data-ttu-id="f9710-147">Nome do computador no qual o cliente está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="f9710-147">Name of the computer on which the client is running.</span></span> <span data-ttu-id="f9710-148">Essa coluna de dados será populada se o nome do host for fornecido pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="f9710-148">This data column is populated if the host name is provided by the client.</span></span> <span data-ttu-id="f9710-149">Para determinar o nome do host, use a função HOST_NAME.</span><span class="sxs-lookup"><span data-stu-id="f9710-149">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="f9710-150">8</span><span class="sxs-lookup"><span data-stu-id="f9710-150">8</span></span>|<span data-ttu-id="f9710-151">Sim</span><span class="sxs-lookup"><span data-stu-id="f9710-151">Yes</span></span>|  
|<span data-ttu-id="f9710-152">IsSystem</span><span class="sxs-lookup"><span data-stu-id="f9710-152">IsSystem</span></span>|`int`|<span data-ttu-id="f9710-153">Indica se o evento ocorreu em um processo do sistema ou do usuário.</span><span class="sxs-lookup"><span data-stu-id="f9710-153">Indicates whether the event occurred on a system process or a user process.</span></span> <span data-ttu-id="f9710-154">1 = sistema, 0 = usuário.</span><span class="sxs-lookup"><span data-stu-id="f9710-154">1 = system, 0 = user.</span></span>|<span data-ttu-id="f9710-155">60</span><span class="sxs-lookup"><span data-stu-id="f9710-155">60</span></span>|<span data-ttu-id="f9710-156">Sim</span><span class="sxs-lookup"><span data-stu-id="f9710-156">Yes</span></span>|  
|<span data-ttu-id="f9710-157">LoginName</span><span class="sxs-lookup"><span data-stu-id="f9710-157">LoginName</span></span>|`nvarchar`|<span data-ttu-id="f9710-158">Nome de logon do usuário (logon de segurança do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou as credenciais de logon do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows no formato DOMÍNIO/nomedousuário).</span><span class="sxs-lookup"><span data-stu-id="f9710-158">Name of the login of the user (either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security login or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows login credentials in the form of DOMAIN\username).</span></span>|<span data-ttu-id="f9710-159">11</span><span class="sxs-lookup"><span data-stu-id="f9710-159">11</span></span>|<span data-ttu-id="f9710-160">Sim</span><span class="sxs-lookup"><span data-stu-id="f9710-160">Yes</span></span>|  
|<span data-ttu-id="f9710-161">LoginSid</span><span class="sxs-lookup"><span data-stu-id="f9710-161">LoginSid</span></span>|`image`|<span data-ttu-id="f9710-162">Número SID (identificação de segurança) do usuário que fez logon.</span><span class="sxs-lookup"><span data-stu-id="f9710-162">Security identification number (SID) of the logged-in user.</span></span> <span data-ttu-id="f9710-163">Você pode encontrar essas informações na exibição de catálogo sys.server_principals.</span><span class="sxs-lookup"><span data-stu-id="f9710-163">You can find this information in the sys.server_principals catalog view.</span></span> <span data-ttu-id="f9710-164">Cada SID é exclusivo para cada logon no servidor.</span><span class="sxs-lookup"><span data-stu-id="f9710-164">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="f9710-165">41</span><span class="sxs-lookup"><span data-stu-id="f9710-165">41</span></span>|<span data-ttu-id="f9710-166">Sim</span><span class="sxs-lookup"><span data-stu-id="f9710-166">Yes</span></span>|  
|<span data-ttu-id="f9710-167">NTDomainName</span><span class="sxs-lookup"><span data-stu-id="f9710-167">NTDomainName</span></span>|`nvarchar`|<span data-ttu-id="f9710-168">O domínio do Windows ao qual o usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="f9710-168">Windows domain to which the user belongs.</span></span>|<span data-ttu-id="f9710-169">7</span><span class="sxs-lookup"><span data-stu-id="f9710-169">7</span></span>|<span data-ttu-id="f9710-170">Sim</span><span class="sxs-lookup"><span data-stu-id="f9710-170">Yes</span></span>|  
|<span data-ttu-id="f9710-171">NTUserName</span><span class="sxs-lookup"><span data-stu-id="f9710-171">NTUserName</span></span>|`nvarchar`|<span data-ttu-id="f9710-172">Nome do usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="f9710-172">Windows user name.</span></span>|<span data-ttu-id="f9710-173">6</span><span class="sxs-lookup"><span data-stu-id="f9710-173">6</span></span>|<span data-ttu-id="f9710-174">Sim</span><span class="sxs-lookup"><span data-stu-id="f9710-174">Yes</span></span>|  
|<span data-ttu-id="f9710-175">RequestID</span><span class="sxs-lookup"><span data-stu-id="f9710-175">RequestID</span></span>|`int`|<span data-ttu-id="f9710-176">ID da solicitação que contém a instrução.</span><span class="sxs-lookup"><span data-stu-id="f9710-176">ID of the request containing the statement.</span></span>|<span data-ttu-id="f9710-177">49</span><span class="sxs-lookup"><span data-stu-id="f9710-177">49</span></span>|<span data-ttu-id="f9710-178">Sim</span><span class="sxs-lookup"><span data-stu-id="f9710-178">Yes</span></span>|  
|<span data-ttu-id="f9710-179">ServerName</span><span class="sxs-lookup"><span data-stu-id="f9710-179">ServerName</span></span>|`nvarchar`|<span data-ttu-id="f9710-180">Nome da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que está sendo rastreada.</span><span class="sxs-lookup"><span data-stu-id="f9710-180">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="f9710-181">26</span><span class="sxs-lookup"><span data-stu-id="f9710-181">26</span></span>|<span data-ttu-id="f9710-182">Não</span><span class="sxs-lookup"><span data-stu-id="f9710-182">No</span></span>|  
|<span data-ttu-id="f9710-183">SessionLoginName</span><span class="sxs-lookup"><span data-stu-id="f9710-183">SessionLoginName</span></span>|`nvarchar`|<span data-ttu-id="f9710-184">Nome de logon do usuário que originou a sessão.</span><span class="sxs-lookup"><span data-stu-id="f9710-184">Login name of the user who originated the session.</span></span> <span data-ttu-id="f9710-185">Por exemplo, ao se conectar ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando o Logon1 e executar uma instrução como Logon2, SessionLoginName mostrará o Logon1 e LoginName mostrará o Logon2.</span><span class="sxs-lookup"><span data-stu-id="f9710-185">For example, if you connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and execute a statement as Login2, SessionLoginName shows Login1 and LoginName shows Login2.</span></span> <span data-ttu-id="f9710-186">Essa coluna exibe logons do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e do Windows.</span><span class="sxs-lookup"><span data-stu-id="f9710-186">This column displays both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="f9710-187">64</span><span class="sxs-lookup"><span data-stu-id="f9710-187">64</span></span>|<span data-ttu-id="f9710-188">Sim</span><span class="sxs-lookup"><span data-stu-id="f9710-188">Yes</span></span>|  
|<span data-ttu-id="f9710-189">SPID</span><span class="sxs-lookup"><span data-stu-id="f9710-189">SPID</span></span>|`int`|<span data-ttu-id="f9710-190">Identificação da sessão em que ocorreu o evento.</span><span class="sxs-lookup"><span data-stu-id="f9710-190">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="f9710-191">12</span><span class="sxs-lookup"><span data-stu-id="f9710-191">12</span></span>|<span data-ttu-id="f9710-192">Sim</span><span class="sxs-lookup"><span data-stu-id="f9710-192">Yes</span></span>|  
|<span data-ttu-id="f9710-193">StartTime</span><span class="sxs-lookup"><span data-stu-id="f9710-193">StartTime</span></span>|`datetime`|<span data-ttu-id="f9710-194">Hora de início do evento, se disponível.</span><span class="sxs-lookup"><span data-stu-id="f9710-194">Time at which the event started, if available.</span></span>|<span data-ttu-id="f9710-195">14</span><span class="sxs-lookup"><span data-stu-id="f9710-195">14</span></span>|<span data-ttu-id="f9710-196">Sim</span><span class="sxs-lookup"><span data-stu-id="f9710-196">Yes</span></span>|  
|<span data-ttu-id="f9710-197">TransactionID</span><span class="sxs-lookup"><span data-stu-id="f9710-197">TransactionID</span></span>|`bigint`|<span data-ttu-id="f9710-198">ID da transação atribuída pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="f9710-198">System-assigned ID of the transaction.</span></span>|<span data-ttu-id="f9710-199">4</span><span class="sxs-lookup"><span data-stu-id="f9710-199">4</span></span>|<span data-ttu-id="f9710-200">Sim</span><span class="sxs-lookup"><span data-stu-id="f9710-200">Yes</span></span>|  
|<span data-ttu-id="f9710-201">XactSequence</span><span class="sxs-lookup"><span data-stu-id="f9710-201">XactSequence</span></span>|`bigint`|<span data-ttu-id="f9710-202">Token usado para descrever a transação atual.</span><span class="sxs-lookup"><span data-stu-id="f9710-202">Token used to describe the current transaction.</span></span>|<span data-ttu-id="f9710-203">50</span><span class="sxs-lookup"><span data-stu-id="f9710-203">50</span></span>|<span data-ttu-id="f9710-204">Sim</span><span class="sxs-lookup"><span data-stu-id="f9710-204">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f9710-205">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f9710-205">See Also</span></span>  
 [<span data-ttu-id="f9710-206">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f9710-206">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  