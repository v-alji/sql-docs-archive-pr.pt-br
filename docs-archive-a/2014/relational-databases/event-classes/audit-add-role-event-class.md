---
title: Classe de evento Audit Add Role | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Audit Add Role event class
ms.assetid: 4ea55922-608c-4db2-8b3f-873862755bba
author: stevestein
ms.author: sstein
ms.openlocfilehash: d570dda8bb6e7a839ae901b7d9f8709895c2e88a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682251"
---
# <a name="audit-add-role-event-class"></a><span data-ttu-id="efc74-102">Classe de evento Audit Add Role</span><span class="sxs-lookup"><span data-stu-id="efc74-102">Audit Add Role Event Class</span></span>
  <span data-ttu-id="efc74-103">A classe de evento **Função de Adição de Auditoria** ocorre quando uma função de banco de dados é adicionada ou removida de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="efc74-103">The **Audit Add Role** event class occurs when a database role is added to or removed from a database.</span></span> <span data-ttu-id="efc74-104">Esta classe de evento é usada pelos procedimentos armazenados **sp_addrole** e **sp_droprole** .</span><span class="sxs-lookup"><span data-stu-id="efc74-104">This event class is used by the **sp_addrole** and **sp_droprole** stored procedures.</span></span>  
  
 <span data-ttu-id="efc74-105">Essa classe de evento poderá ser removida de uma versão futura do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="efc74-105">This event class may be removed from a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="efc74-106">É recomendável que, em vez disso, você use a classe de evento **Audit Database Principal Management** .</span><span class="sxs-lookup"><span data-stu-id="efc74-106">It is recommended that you use the **Audit Database Principal Management** event class instead.</span></span>  
  
## <a name="audit-add-role-event-class-data-columns"></a><span data-ttu-id="efc74-107">Colunas de Dados da Classe de Evento Audit Add Role</span><span class="sxs-lookup"><span data-stu-id="efc74-107">Audit Add Role Event Class Data Columns</span></span>  
  
|<span data-ttu-id="efc74-108">Nome da coluna de dados</span><span class="sxs-lookup"><span data-stu-id="efc74-108">Data column name</span></span>|<span data-ttu-id="efc74-109">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="efc74-109">Data type</span></span>|<span data-ttu-id="efc74-110">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="efc74-110">Description</span></span>|<span data-ttu-id="efc74-111">ID da coluna</span><span class="sxs-lookup"><span data-stu-id="efc74-111">Column ID</span></span>|<span data-ttu-id="efc74-112">Filtrável</span><span class="sxs-lookup"><span data-stu-id="efc74-112">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="efc74-113">**ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="efc74-113">**ApplicationName**</span></span>|<span data-ttu-id="efc74-114">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="efc74-114">**nvarchar**</span></span>|<span data-ttu-id="efc74-115">Nome do aplicativo cliente que criou a conexão com uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="efc74-115">Name of the client application that created the connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="efc74-116">Essa coluna é populada com os valores passados pelo aplicativo e não com o nome exibido do programa.</span><span class="sxs-lookup"><span data-stu-id="efc74-116">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="efc74-117">10</span><span class="sxs-lookup"><span data-stu-id="efc74-117">10</span></span>|<span data-ttu-id="efc74-118">Sim</span><span class="sxs-lookup"><span data-stu-id="efc74-118">Yes</span></span>|  
|<span data-ttu-id="efc74-119">**ClientProcessID**</span><span class="sxs-lookup"><span data-stu-id="efc74-119">**ClientProcessID**</span></span>|<span data-ttu-id="efc74-120">**int**</span><span class="sxs-lookup"><span data-stu-id="efc74-120">**int**</span></span>|<span data-ttu-id="efc74-121">ID atribuída pelo computador host ao processo em que o aplicativo cliente está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="efc74-121">ID assigned by the host computer to the process where the client application is running.</span></span> <span data-ttu-id="efc74-122">Essa coluna de dados será populada se a ID do processo do cliente for fornecida pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="efc74-122">This data column is populated if the client process ID is provided by the client.</span></span>|<span data-ttu-id="efc74-123">9</span><span class="sxs-lookup"><span data-stu-id="efc74-123">9</span></span>|<span data-ttu-id="efc74-124">Sim</span><span class="sxs-lookup"><span data-stu-id="efc74-124">Yes</span></span>|  
|<span data-ttu-id="efc74-125">**DatabaseID**</span><span class="sxs-lookup"><span data-stu-id="efc74-125">**DatabaseID**</span></span>|<span data-ttu-id="efc74-126">**int**</span><span class="sxs-lookup"><span data-stu-id="efc74-126">**int**</span></span>|<span data-ttu-id="efc74-127">ID do banco de dados especificado pela instrução USE de *database* ou o banco de dados padrão se nenhuma instrução USE de *database* tiver sido emitida para uma determinada instância.</span><span class="sxs-lookup"><span data-stu-id="efc74-127">ID of the database specified by the USE *database* statement or the default database if no USE *database* statement has been issued for a given instance.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="efc74-128">exibirá o nome do banco de dados se a coluna de dados **ServerName** for capturada no rastreamento e o servidor estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="efc74-128">displays the name of the database if the **ServerName** data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="efc74-129">Determine o valor para um banco de dados usando a função DB_ID.</span><span class="sxs-lookup"><span data-stu-id="efc74-129">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="efc74-130">3</span><span class="sxs-lookup"><span data-stu-id="efc74-130">3</span></span>|<span data-ttu-id="efc74-131">Sim</span><span class="sxs-lookup"><span data-stu-id="efc74-131">Yes</span></span>|  
|<span data-ttu-id="efc74-132">**DatabaseName**</span><span class="sxs-lookup"><span data-stu-id="efc74-132">**DatabaseName**</span></span>|<span data-ttu-id="efc74-133">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="efc74-133">**nvarchar**</span></span>|<span data-ttu-id="efc74-134">Nome do banco de dados no qual a instrução do usuário está sendo executada.</span><span class="sxs-lookup"><span data-stu-id="efc74-134">Name of the database in which the user statement is running.</span></span>|<span data-ttu-id="efc74-135">35</span><span class="sxs-lookup"><span data-stu-id="efc74-135">35</span></span>|<span data-ttu-id="efc74-136">Sim</span><span class="sxs-lookup"><span data-stu-id="efc74-136">Yes</span></span>|  
|<span data-ttu-id="efc74-137">**DBUserName**</span><span class="sxs-lookup"><span data-stu-id="efc74-137">**DBUserName**</span></span>|<span data-ttu-id="efc74-138">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="efc74-138">**nvarchar**</span></span>|<span data-ttu-id="efc74-139">Nome de usuário do emissor no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="efc74-139">Issuer's username in the database.</span></span>|<span data-ttu-id="efc74-140">40</span><span class="sxs-lookup"><span data-stu-id="efc74-140">40</span></span>|<span data-ttu-id="efc74-141">Sim</span><span class="sxs-lookup"><span data-stu-id="efc74-141">Yes</span></span>|  
|<span data-ttu-id="efc74-142">**EventClass**</span><span class="sxs-lookup"><span data-stu-id="efc74-142">**EventClass**</span></span>|<span data-ttu-id="efc74-143">**int**</span><span class="sxs-lookup"><span data-stu-id="efc74-143">**int**</span></span>|<span data-ttu-id="efc74-144">Tipo de evento = 111.</span><span class="sxs-lookup"><span data-stu-id="efc74-144">Type of event = 111.</span></span>|<span data-ttu-id="efc74-145">27</span><span class="sxs-lookup"><span data-stu-id="efc74-145">27</span></span>|<span data-ttu-id="efc74-146">Não</span><span class="sxs-lookup"><span data-stu-id="efc74-146">No</span></span>|  
|<span data-ttu-id="efc74-147">**EventSequence**</span><span class="sxs-lookup"><span data-stu-id="efc74-147">**EventSequence**</span></span>|<span data-ttu-id="efc74-148">**int**</span><span class="sxs-lookup"><span data-stu-id="efc74-148">**int**</span></span>|<span data-ttu-id="efc74-149">Sequência de um determinado evento na solicitação.</span><span class="sxs-lookup"><span data-stu-id="efc74-149">Sequence of a given event within the request.</span></span>|<span data-ttu-id="efc74-150">51</span><span class="sxs-lookup"><span data-stu-id="efc74-150">51</span></span>|<span data-ttu-id="efc74-151">Não</span><span class="sxs-lookup"><span data-stu-id="efc74-151">No</span></span>|  
|<span data-ttu-id="efc74-152">**EventSubClass**</span><span class="sxs-lookup"><span data-stu-id="efc74-152">**EventSubClass**</span></span>|<span data-ttu-id="efc74-153">**int**</span><span class="sxs-lookup"><span data-stu-id="efc74-153">**int**</span></span>|<span data-ttu-id="efc74-154">Tipo de subclasse de evento.</span><span class="sxs-lookup"><span data-stu-id="efc74-154">Type of event subclass.</span></span><br /><br /> <span data-ttu-id="efc74-155">1=Add</span><span class="sxs-lookup"><span data-stu-id="efc74-155">1=Add</span></span><br /><br /> <span data-ttu-id="efc74-156">2=Drop</span><span class="sxs-lookup"><span data-stu-id="efc74-156">2=Drop</span></span>|<span data-ttu-id="efc74-157">21</span><span class="sxs-lookup"><span data-stu-id="efc74-157">21</span></span>|<span data-ttu-id="efc74-158">Sim</span><span class="sxs-lookup"><span data-stu-id="efc74-158">Yes</span></span>|  
|<span data-ttu-id="efc74-159">**HostName**</span><span class="sxs-lookup"><span data-stu-id="efc74-159">**HostName**</span></span>|<span data-ttu-id="efc74-160">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="efc74-160">**nvarchar**</span></span>|<span data-ttu-id="efc74-161">Nome do computador no qual o cliente está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="efc74-161">Name of the computer on which the client is running.</span></span> <span data-ttu-id="efc74-162">Essa coluna de dados será populada se o cliente fornecer o nome do host.</span><span class="sxs-lookup"><span data-stu-id="efc74-162">This data column is populated if the client provides the host name.</span></span> <span data-ttu-id="efc74-163">Para determinar o nome do host, use a função HOST_NAME.</span><span class="sxs-lookup"><span data-stu-id="efc74-163">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="efc74-164">8</span><span class="sxs-lookup"><span data-stu-id="efc74-164">8</span></span>|<span data-ttu-id="efc74-165">Sim</span><span class="sxs-lookup"><span data-stu-id="efc74-165">Yes</span></span>|  
|<span data-ttu-id="efc74-166">**IsSystem**</span><span class="sxs-lookup"><span data-stu-id="efc74-166">**IsSystem**</span></span>|<span data-ttu-id="efc74-167">**int**</span><span class="sxs-lookup"><span data-stu-id="efc74-167">**int**</span></span>|<span data-ttu-id="efc74-168">Indica se o evento ocorreu em um processo do sistema ou do usuário.</span><span class="sxs-lookup"><span data-stu-id="efc74-168">Indicates whether the event occurred on a system process or a user process.</span></span> <span data-ttu-id="efc74-169">1 = sistema, 0 = usuário.</span><span class="sxs-lookup"><span data-stu-id="efc74-169">1 = system, 0 = user.</span></span>|<span data-ttu-id="efc74-170">60</span><span class="sxs-lookup"><span data-stu-id="efc74-170">60</span></span>|<span data-ttu-id="efc74-171">Sim</span><span class="sxs-lookup"><span data-stu-id="efc74-171">Yes</span></span>|  
|<span data-ttu-id="efc74-172">**LoginName**</span><span class="sxs-lookup"><span data-stu-id="efc74-172">**LoginName**</span></span>|<span data-ttu-id="efc74-173">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="efc74-173">**nvarchar**</span></span>|<span data-ttu-id="efc74-174">Nome do logon do usuário (logon de segurança do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou as credenciais de logon do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows no formato DOMÍNIO\nomedeusuário).</span><span class="sxs-lookup"><span data-stu-id="efc74-174">Name of the login of the user (either the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security login or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows login credentials in the form of DOMAIN\username).</span></span>|<span data-ttu-id="efc74-175">11</span><span class="sxs-lookup"><span data-stu-id="efc74-175">11</span></span>|<span data-ttu-id="efc74-176">Sim</span><span class="sxs-lookup"><span data-stu-id="efc74-176">Yes</span></span>|  
|<span data-ttu-id="efc74-177">**LoginSid**</span><span class="sxs-lookup"><span data-stu-id="efc74-177">**LoginSid**</span></span>|<span data-ttu-id="efc74-178">**imagem**</span><span class="sxs-lookup"><span data-stu-id="efc74-178">**image**</span></span>|<span data-ttu-id="efc74-179">Número SID (identificação de segurança) do usuário que fez logon.</span><span class="sxs-lookup"><span data-stu-id="efc74-179">Security identification number (SID) of the logged-in user.</span></span> <span data-ttu-id="efc74-180">Você pode encontrar essas informações na exibição de catálogo **sys.server_principals** .</span><span class="sxs-lookup"><span data-stu-id="efc74-180">You can find this information in the **sys.server_principals** catalog view.</span></span> <span data-ttu-id="efc74-181">Cada SID é exclusivo para cada logon no servidor.</span><span class="sxs-lookup"><span data-stu-id="efc74-181">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="efc74-182">41</span><span class="sxs-lookup"><span data-stu-id="efc74-182">41</span></span>|<span data-ttu-id="efc74-183">Sim</span><span class="sxs-lookup"><span data-stu-id="efc74-183">Yes</span></span>|  
|<span data-ttu-id="efc74-184">**NTDomainName**</span><span class="sxs-lookup"><span data-stu-id="efc74-184">**NTDomainName**</span></span>|<span data-ttu-id="efc74-185">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="efc74-185">**nvarchar**</span></span>|<span data-ttu-id="efc74-186">O domínio do Windows ao qual o usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="efc74-186">Windows domain to which the user belongs.</span></span>|<span data-ttu-id="efc74-187">7</span><span class="sxs-lookup"><span data-stu-id="efc74-187">7</span></span>|<span data-ttu-id="efc74-188">Sim</span><span class="sxs-lookup"><span data-stu-id="efc74-188">Yes</span></span>|  
|<span data-ttu-id="efc74-189">**NTUserName**</span><span class="sxs-lookup"><span data-stu-id="efc74-189">**NTUserName**</span></span>|<span data-ttu-id="efc74-190">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="efc74-190">**nvarchar**</span></span>|<span data-ttu-id="efc74-191">Nome do usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="efc74-191">Windows user name.</span></span>|<span data-ttu-id="efc74-192">6</span><span class="sxs-lookup"><span data-stu-id="efc74-192">6</span></span>|<span data-ttu-id="efc74-193">Sim</span><span class="sxs-lookup"><span data-stu-id="efc74-193">Yes</span></span>|  
|<span data-ttu-id="efc74-194">**RequestID**</span><span class="sxs-lookup"><span data-stu-id="efc74-194">**RequestID**</span></span>|<span data-ttu-id="efc74-195">**int**</span><span class="sxs-lookup"><span data-stu-id="efc74-195">**int**</span></span>|<span data-ttu-id="efc74-196">ID da solicitação que contém a instrução.</span><span class="sxs-lookup"><span data-stu-id="efc74-196">ID of the request containing the statement.</span></span>|<span data-ttu-id="efc74-197">49</span><span class="sxs-lookup"><span data-stu-id="efc74-197">49</span></span>|<span data-ttu-id="efc74-198">Sim</span><span class="sxs-lookup"><span data-stu-id="efc74-198">Yes</span></span>|  
|<span data-ttu-id="efc74-199">**RoleName**</span><span class="sxs-lookup"><span data-stu-id="efc74-199">**RoleName**</span></span>|<span data-ttu-id="efc74-200">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="efc74-200">**nvarchar**</span></span>|<span data-ttu-id="efc74-201">Nome da função de banco de dados que está sendo adicionada ou removida.</span><span class="sxs-lookup"><span data-stu-id="efc74-201">Name of the database role that is being added or removed.</span></span>|<span data-ttu-id="efc74-202">38</span><span class="sxs-lookup"><span data-stu-id="efc74-202">38</span></span>|<span data-ttu-id="efc74-203">Sim</span><span class="sxs-lookup"><span data-stu-id="efc74-203">Yes</span></span>|  
|<span data-ttu-id="efc74-204">**ServerName**</span><span class="sxs-lookup"><span data-stu-id="efc74-204">**ServerName**</span></span>|<span data-ttu-id="efc74-205">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="efc74-205">**nvarchar**</span></span>|<span data-ttu-id="efc74-206">Nome da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que está sendo rastreada.</span><span class="sxs-lookup"><span data-stu-id="efc74-206">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="efc74-207">26</span><span class="sxs-lookup"><span data-stu-id="efc74-207">26</span></span>|<span data-ttu-id="efc74-208">Não</span><span class="sxs-lookup"><span data-stu-id="efc74-208">No</span></span>|  
|<span data-ttu-id="efc74-209">**SessionLoginName**</span><span class="sxs-lookup"><span data-stu-id="efc74-209">**SessionLoginName**</span></span>|<span data-ttu-id="efc74-210">**Nvarchar**</span><span class="sxs-lookup"><span data-stu-id="efc74-210">**Nvarchar**</span></span>|<span data-ttu-id="efc74-211">Nome de logon do usuário que originou a sessão.</span><span class="sxs-lookup"><span data-stu-id="efc74-211">Login name of the user who originated the session.</span></span> <span data-ttu-id="efc74-212">Por exemplo, para se conectar ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando o Logon1 e executar uma instrução como Logon2, o **SessionLoginName** mostrará o Logon1 e o **LoginName** mostrará o Logon2.</span><span class="sxs-lookup"><span data-stu-id="efc74-212">For example, if you connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and execute a statement as Login2, **SessionLoginName** shows Login1 and **LoginName** shows Login2.</span></span> <span data-ttu-id="efc74-213">Essa coluna exibe logons do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e do Windows.</span><span class="sxs-lookup"><span data-stu-id="efc74-213">This column displays both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="efc74-214">64</span><span class="sxs-lookup"><span data-stu-id="efc74-214">64</span></span>|<span data-ttu-id="efc74-215">Sim</span><span class="sxs-lookup"><span data-stu-id="efc74-215">Yes</span></span>|  
|<span data-ttu-id="efc74-216">**SPID**</span><span class="sxs-lookup"><span data-stu-id="efc74-216">**SPID**</span></span>|<span data-ttu-id="efc74-217">**int**</span><span class="sxs-lookup"><span data-stu-id="efc74-217">**int**</span></span>|<span data-ttu-id="efc74-218">Identificação da sessão em que ocorreu o evento.</span><span class="sxs-lookup"><span data-stu-id="efc74-218">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="efc74-219">12</span><span class="sxs-lookup"><span data-stu-id="efc74-219">12</span></span>|<span data-ttu-id="efc74-220">Sim</span><span class="sxs-lookup"><span data-stu-id="efc74-220">Yes</span></span>|  
|<span data-ttu-id="efc74-221">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="efc74-221">**StartTime**</span></span>|<span data-ttu-id="efc74-222">**datetime**</span><span class="sxs-lookup"><span data-stu-id="efc74-222">**datetime**</span></span>|<span data-ttu-id="efc74-223">Hora de início do evento, se disponível.</span><span class="sxs-lookup"><span data-stu-id="efc74-223">Time at which the event started, if available.</span></span>|<span data-ttu-id="efc74-224">14</span><span class="sxs-lookup"><span data-stu-id="efc74-224">14</span></span>|<span data-ttu-id="efc74-225">Sim</span><span class="sxs-lookup"><span data-stu-id="efc74-225">Yes</span></span>|  
|<span data-ttu-id="efc74-226">**Êxito**</span><span class="sxs-lookup"><span data-stu-id="efc74-226">**Success**</span></span>|<span data-ttu-id="efc74-227">**int**</span><span class="sxs-lookup"><span data-stu-id="efc74-227">**int**</span></span>|<span data-ttu-id="efc74-228">1 = êxito.</span><span class="sxs-lookup"><span data-stu-id="efc74-228">1 = success.</span></span> <span data-ttu-id="efc74-229">0 = falha.</span><span class="sxs-lookup"><span data-stu-id="efc74-229">0 = failure.</span></span> <span data-ttu-id="efc74-230">Por exemplo, o valor 1 indica êxito em uma verificação de permissões e o valor 0 indica falha nessa verificação.</span><span class="sxs-lookup"><span data-stu-id="efc74-230">For example, a value of 1 indicates success of a permissions check and a value of 0 indicates a failure of that check.</span></span>|<span data-ttu-id="efc74-231">23</span><span class="sxs-lookup"><span data-stu-id="efc74-231">23</span></span>|<span data-ttu-id="efc74-232">Sim</span><span class="sxs-lookup"><span data-stu-id="efc74-232">Yes</span></span>|  
|<span data-ttu-id="efc74-233">**TransactionID**</span><span class="sxs-lookup"><span data-stu-id="efc74-233">**TransactionID**</span></span>|<span data-ttu-id="efc74-234">**bigint**</span><span class="sxs-lookup"><span data-stu-id="efc74-234">**bigint**</span></span>|<span data-ttu-id="efc74-235">ID da transação atribuída pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="efc74-235">System-assigned ID of the transaction.</span></span>|<span data-ttu-id="efc74-236">4</span><span class="sxs-lookup"><span data-stu-id="efc74-236">4</span></span>|<span data-ttu-id="efc74-237">Sim</span><span class="sxs-lookup"><span data-stu-id="efc74-237">Yes</span></span>|  
|<span data-ttu-id="efc74-238">**XactSequence**</span><span class="sxs-lookup"><span data-stu-id="efc74-238">**XactSequence**</span></span>|<span data-ttu-id="efc74-239">**bigint**</span><span class="sxs-lookup"><span data-stu-id="efc74-239">**bigint**</span></span>|<span data-ttu-id="efc74-240">Token usado para descrever a transação atual.</span><span class="sxs-lookup"><span data-stu-id="efc74-240">Token used to describe the current transaction.</span></span>|<span data-ttu-id="efc74-241">50</span><span class="sxs-lookup"><span data-stu-id="efc74-241">50</span></span>|<span data-ttu-id="efc74-242">Sim</span><span class="sxs-lookup"><span data-stu-id="efc74-242">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="efc74-243">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="efc74-243">See Also</span></span>  
 <span data-ttu-id="efc74-244">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="efc74-244">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 <span data-ttu-id="efc74-245">[sp_addrole &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrole-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="efc74-245">[sp_addrole &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrole-transact-sql) </span></span>  
 <span data-ttu-id="efc74-246">[sp_droprole &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droprole-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="efc74-246">[sp_droprole &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droprole-transact-sql) </span></span>  
 [<span data-ttu-id="efc74-247">Classe de evento Audit Database Principal Management</span><span class="sxs-lookup"><span data-stu-id="efc74-247">Audit Database Principal Management Event Class</span></span>](audit-database-principal-management-event-class.md)  
  
  