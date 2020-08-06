---
title: Classe de evento Data File Auto Grow | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Data File Auto Grow event class
ms.assetid: 63701c20-7886-454a-936f-7aea9d042cf7
author: stevestein
ms.author: sstein
ms.openlocfilehash: a144918bc1d146857fb25bf44892239157270ed4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570054"
---
# <a name="data-file-auto-grow-event-class"></a><span data-ttu-id="64a85-102">classe de evento Data File Auto Grow</span><span class="sxs-lookup"><span data-stu-id="64a85-102">Data File Auto Grow Event Class</span></span>
  <span data-ttu-id="64a85-103">A classe de evento **Data File Auto Grow** indica que o arquivo de dados pode se expandir automaticamente.</span><span class="sxs-lookup"><span data-stu-id="64a85-103">The **Data File Auto Grow** event class indicates that the data file grew automatically.</span></span> <span data-ttu-id="64a85-104">Esse evento não será acionado se o arquivo de dados crescer explicitamente devido a uma instrução ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="64a85-104">This event is not triggered if the data file is grown explicitly by using the ALTER DATABASE statement.</span></span>  
  
 <span data-ttu-id="64a85-105">Inclua a classe de evento **Data File Auto Grow** nos rastreamentos que monitoram o crescimento do arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="64a85-105">Include the **Data File Auto Grow** event class in traces that are monitoring growth of the data file.</span></span>  
  
 <span data-ttu-id="64a85-106">Quando a classe de evento **Data File Auto Grow** é incluída no rastreamento, a quantidade de sobrecarga incorrida é baixa, a menos que o arquivo de dados tenha crescimento automático frequentemente.</span><span class="sxs-lookup"><span data-stu-id="64a85-106">When the **Data File Auto Grow** event class is included in a trace, the amount of overhead incurred is low unless the data file is growing automatically frequently.</span></span>  
  
## <a name="data-file-auto-grow-event-class-data-columns"></a><span data-ttu-id="64a85-107">Colunas de dados da classe de evento Data File Auto Grow</span><span class="sxs-lookup"><span data-stu-id="64a85-107">Data File Auto Grow Event Class Data Columns</span></span>  
  
|<span data-ttu-id="64a85-108">Nome da coluna de dados</span><span class="sxs-lookup"><span data-stu-id="64a85-108">Data column name</span></span>|<span data-ttu-id="64a85-109">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="64a85-109">Data type</span></span>|<span data-ttu-id="64a85-110">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="64a85-110">Description</span></span>|<span data-ttu-id="64a85-111">ID da coluna</span><span class="sxs-lookup"><span data-stu-id="64a85-111">Column ID</span></span>|<span data-ttu-id="64a85-112">Filtrável</span><span class="sxs-lookup"><span data-stu-id="64a85-112">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="64a85-113">**ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="64a85-113">**ApplicationName**</span></span>|<span data-ttu-id="64a85-114">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="64a85-114">**nvarchar**</span></span>|<span data-ttu-id="64a85-115">Nome do aplicativo cliente que criou a conexão com uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64a85-115">Name of the client application that created the connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="64a85-116">Essa coluna é populada com os valores passados pelo aplicativo e não com o nome exibido do programa.</span><span class="sxs-lookup"><span data-stu-id="64a85-116">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="64a85-117">10</span><span class="sxs-lookup"><span data-stu-id="64a85-117">10</span></span>|<span data-ttu-id="64a85-118">Sim</span><span class="sxs-lookup"><span data-stu-id="64a85-118">Yes</span></span>|  
|<span data-ttu-id="64a85-119">**ClientProcessID**</span><span class="sxs-lookup"><span data-stu-id="64a85-119">**ClientProcessID**</span></span>|<span data-ttu-id="64a85-120">**int**</span><span class="sxs-lookup"><span data-stu-id="64a85-120">**int**</span></span>|<span data-ttu-id="64a85-121">ID atribuída pelo computador host ao processo em que o aplicativo cliente está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="64a85-121">ID assigned by the host computer to the process where the client application is running.</span></span> <span data-ttu-id="64a85-122">Essa coluna de dados será populada se o cliente fornecer a ID de processo do cliente.</span><span class="sxs-lookup"><span data-stu-id="64a85-122">This data column is populated if the client provides the client process ID.</span></span>|<span data-ttu-id="64a85-123">9</span><span class="sxs-lookup"><span data-stu-id="64a85-123">9</span></span>|<span data-ttu-id="64a85-124">Sim</span><span class="sxs-lookup"><span data-stu-id="64a85-124">Yes</span></span>|  
|<span data-ttu-id="64a85-125">**DatabaseID**</span><span class="sxs-lookup"><span data-stu-id="64a85-125">**DatabaseID**</span></span>|<span data-ttu-id="64a85-126">**int**</span><span class="sxs-lookup"><span data-stu-id="64a85-126">**int**</span></span>|<span data-ttu-id="64a85-127">ID do banco de dados especificado pela instrução USE de *database* ou o banco de dados padrão se nenhuma instrução USE de *database* tiver sido emitida para uma determinada instância.</span><span class="sxs-lookup"><span data-stu-id="64a85-127">ID of the database specified by the USE *database* statement or the default database if no USE *database* statement has been issued for a given instance.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="64a85-128">exibirá o nome do banco de dados se a coluna de dados **ServerName** for capturada no rastreamento e o servidor estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="64a85-128">displays the name of the database if the **ServerName** data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="64a85-129">Determine o valor para um banco de dados usando a função DB_ID.</span><span class="sxs-lookup"><span data-stu-id="64a85-129">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="64a85-130">3</span><span class="sxs-lookup"><span data-stu-id="64a85-130">3</span></span>|<span data-ttu-id="64a85-131">Sim</span><span class="sxs-lookup"><span data-stu-id="64a85-131">Yes</span></span>|  
|<span data-ttu-id="64a85-132">**DatabaseName**</span><span class="sxs-lookup"><span data-stu-id="64a85-132">**DatabaseName**</span></span>|<span data-ttu-id="64a85-133">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="64a85-133">**nvarchar**</span></span>|<span data-ttu-id="64a85-134">Nome do banco de dados no qual a instrução do usuário está sendo executada.</span><span class="sxs-lookup"><span data-stu-id="64a85-134">Name of the database in which the user statement is running.</span></span>|<span data-ttu-id="64a85-135">35</span><span class="sxs-lookup"><span data-stu-id="64a85-135">35</span></span>|<span data-ttu-id="64a85-136">Sim</span><span class="sxs-lookup"><span data-stu-id="64a85-136">Yes</span></span>|  
|<span data-ttu-id="64a85-137">**Duration**</span><span class="sxs-lookup"><span data-stu-id="64a85-137">**Duration**</span></span>|<span data-ttu-id="64a85-138">**bigint**</span><span class="sxs-lookup"><span data-stu-id="64a85-138">**bigint**</span></span>|<span data-ttu-id="64a85-139">Tempo (em milissegundos) necessário para estender o arquivo.</span><span class="sxs-lookup"><span data-stu-id="64a85-139">Length of time (in milliseconds) necessary to extend the file.</span></span>|<span data-ttu-id="64a85-140">13</span><span class="sxs-lookup"><span data-stu-id="64a85-140">13</span></span>|<span data-ttu-id="64a85-141">Sim</span><span class="sxs-lookup"><span data-stu-id="64a85-141">Yes</span></span>|  
|<span data-ttu-id="64a85-142">**EndTime**</span><span class="sxs-lookup"><span data-stu-id="64a85-142">**EndTime**</span></span>|<span data-ttu-id="64a85-143">**datetime**</span><span class="sxs-lookup"><span data-stu-id="64a85-143">**datetime**</span></span>|<span data-ttu-id="64a85-144">Hora de término do crescimento automático do arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="64a85-144">Time that the data file auto grow ended.</span></span>|<span data-ttu-id="64a85-145">18</span><span class="sxs-lookup"><span data-stu-id="64a85-145">18</span></span>|<span data-ttu-id="64a85-146">Sim</span><span class="sxs-lookup"><span data-stu-id="64a85-146">Yes</span></span>|  
|<span data-ttu-id="64a85-147">**EventClass**</span><span class="sxs-lookup"><span data-stu-id="64a85-147">**EventClass**</span></span>|<span data-ttu-id="64a85-148">**int**</span><span class="sxs-lookup"><span data-stu-id="64a85-148">**int**</span></span>|<span data-ttu-id="64a85-149">Tipo de evento = 92.</span><span class="sxs-lookup"><span data-stu-id="64a85-149">Type of event = 92.</span></span>|<span data-ttu-id="64a85-150">27</span><span class="sxs-lookup"><span data-stu-id="64a85-150">27</span></span>|<span data-ttu-id="64a85-151">Não</span><span class="sxs-lookup"><span data-stu-id="64a85-151">No</span></span>|  
|<span data-ttu-id="64a85-152">**EventSequence**</span><span class="sxs-lookup"><span data-stu-id="64a85-152">**EventSequence**</span></span>|<span data-ttu-id="64a85-153">**int**</span><span class="sxs-lookup"><span data-stu-id="64a85-153">**int**</span></span>|<span data-ttu-id="64a85-154">Sequência da classe de evento **CursorClose** no lote.</span><span class="sxs-lookup"><span data-stu-id="64a85-154">Sequence of the **CursorClose** event class in the batch.</span></span>|<span data-ttu-id="64a85-155">51</span><span class="sxs-lookup"><span data-stu-id="64a85-155">51</span></span>|<span data-ttu-id="64a85-156">Não</span><span class="sxs-lookup"><span data-stu-id="64a85-156">No</span></span>|  
|<span data-ttu-id="64a85-157">**Filename**</span><span class="sxs-lookup"><span data-stu-id="64a85-157">**Filename**</span></span>|<span data-ttu-id="64a85-158">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="64a85-158">**nvarchar**</span></span>|<span data-ttu-id="64a85-159">Nome lógico do arquivo que está sendo estendido.</span><span class="sxs-lookup"><span data-stu-id="64a85-159">Logical name of the file being extended.</span></span>|<span data-ttu-id="64a85-160">36</span><span class="sxs-lookup"><span data-stu-id="64a85-160">36</span></span>|<span data-ttu-id="64a85-161">Sim</span><span class="sxs-lookup"><span data-stu-id="64a85-161">Yes</span></span>|  
|<span data-ttu-id="64a85-162">**HostName**</span><span class="sxs-lookup"><span data-stu-id="64a85-162">**HostName**</span></span>|<span data-ttu-id="64a85-163">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="64a85-163">**nvarchar**</span></span>|<span data-ttu-id="64a85-164">Nome do computador no qual o cliente está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="64a85-164">Name of the computer on which the client is running.</span></span> <span data-ttu-id="64a85-165">Essa coluna de dados será populada se o cliente fornecer o nome do host.</span><span class="sxs-lookup"><span data-stu-id="64a85-165">This data column is populated if the client provides the host name.</span></span> <span data-ttu-id="64a85-166">Para determinar o nome do host, use a função HOST_NAME.</span><span class="sxs-lookup"><span data-stu-id="64a85-166">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="64a85-167">8</span><span class="sxs-lookup"><span data-stu-id="64a85-167">8</span></span>|<span data-ttu-id="64a85-168">Sim</span><span class="sxs-lookup"><span data-stu-id="64a85-168">Yes</span></span>|  
|<span data-ttu-id="64a85-169">**IntegerData**</span><span class="sxs-lookup"><span data-stu-id="64a85-169">**IntegerData**</span></span>|<span data-ttu-id="64a85-170">**int**</span><span class="sxs-lookup"><span data-stu-id="64a85-170">**int**</span></span>|<span data-ttu-id="64a85-171">Número de páginas de 8 quilobytes (KB) em que o arquivo aumentou.</span><span class="sxs-lookup"><span data-stu-id="64a85-171">Number of 8-kilobyte (KB) pages by which the file increased.</span></span>|<span data-ttu-id="64a85-172">25</span><span class="sxs-lookup"><span data-stu-id="64a85-172">25</span></span>|<span data-ttu-id="64a85-173">Sim</span><span class="sxs-lookup"><span data-stu-id="64a85-173">Yes</span></span>|  
|<span data-ttu-id="64a85-174">**IsSystem**</span><span class="sxs-lookup"><span data-stu-id="64a85-174">**IsSystem**</span></span>|<span data-ttu-id="64a85-175">**int**</span><span class="sxs-lookup"><span data-stu-id="64a85-175">**int**</span></span>|<span data-ttu-id="64a85-176">Indica se o evento ocorreu em um processo do sistema ou do usuário.</span><span class="sxs-lookup"><span data-stu-id="64a85-176">Indicates whether the event occurred on a system process or a user process.</span></span> <span data-ttu-id="64a85-177">1 = sistema, 0 = usuário.</span><span class="sxs-lookup"><span data-stu-id="64a85-177">1 = system, 0 = user.</span></span>|<span data-ttu-id="64a85-178">60</span><span class="sxs-lookup"><span data-stu-id="64a85-178">60</span></span>|<span data-ttu-id="64a85-179">Sim</span><span class="sxs-lookup"><span data-stu-id="64a85-179">Yes</span></span>|  
|<span data-ttu-id="64a85-180">**LoginName**</span><span class="sxs-lookup"><span data-stu-id="64a85-180">**LoginName**</span></span>|<span data-ttu-id="64a85-181">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="64a85-181">**nvarchar**</span></span>|<span data-ttu-id="64a85-182">Nome de logon do usuário (logon de segurança do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou as credenciais de logon do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows no formato DOMÍNIO\Nomedeusuário).</span><span class="sxs-lookup"><span data-stu-id="64a85-182">Name of the login of the user (either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security login or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows login credentials in the form of DOMAIN\Username).</span></span>|<span data-ttu-id="64a85-183">11</span><span class="sxs-lookup"><span data-stu-id="64a85-183">11</span></span>|<span data-ttu-id="64a85-184">Sim</span><span class="sxs-lookup"><span data-stu-id="64a85-184">Yes</span></span>|  
|<span data-ttu-id="64a85-185">**LoginSid**</span><span class="sxs-lookup"><span data-stu-id="64a85-185">**LoginSid**</span></span>|<span data-ttu-id="64a85-186">**imagem**</span><span class="sxs-lookup"><span data-stu-id="64a85-186">**image**</span></span>|<span data-ttu-id="64a85-187">SID (identificador de segurança) do usuário que fez logon.</span><span class="sxs-lookup"><span data-stu-id="64a85-187">Security identifier (SID) of the logged-in user.</span></span> <span data-ttu-id="64a85-188">Você pode encontrar essas informações na exibição de catálogo **sys.server_principals** .</span><span class="sxs-lookup"><span data-stu-id="64a85-188">You can find this information in the **sys.server_principals** catalog view.</span></span> <span data-ttu-id="64a85-189">Cada SID é exclusivo para cada logon no servidor.</span><span class="sxs-lookup"><span data-stu-id="64a85-189">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="64a85-190">41</span><span class="sxs-lookup"><span data-stu-id="64a85-190">41</span></span>|<span data-ttu-id="64a85-191">Sim</span><span class="sxs-lookup"><span data-stu-id="64a85-191">Yes</span></span>|  
|<span data-ttu-id="64a85-192">**NTDomainName**</span><span class="sxs-lookup"><span data-stu-id="64a85-192">**NTDomainName**</span></span>|<span data-ttu-id="64a85-193">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="64a85-193">**nvarchar**</span></span>|[!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="64a85-194">O domínio do Windows ao qual o usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="64a85-194">Windows domain to which the user belongs.</span></span>|<span data-ttu-id="64a85-195">7</span><span class="sxs-lookup"><span data-stu-id="64a85-195">7</span></span>|<span data-ttu-id="64a85-196">Sim</span><span class="sxs-lookup"><span data-stu-id="64a85-196">Yes</span></span>|  
|<span data-ttu-id="64a85-197">**ServerName**</span><span class="sxs-lookup"><span data-stu-id="64a85-197">**ServerName**</span></span>|<span data-ttu-id="64a85-198">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="64a85-198">**nvarchar**</span></span>|<span data-ttu-id="64a85-199">Nome da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que está sendo rastreada.</span><span class="sxs-lookup"><span data-stu-id="64a85-199">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="64a85-200">26</span><span class="sxs-lookup"><span data-stu-id="64a85-200">26</span></span>|<span data-ttu-id="64a85-201">Não</span><span class="sxs-lookup"><span data-stu-id="64a85-201">No</span></span>|  
|<span data-ttu-id="64a85-202">**SessionLoginName**</span><span class="sxs-lookup"><span data-stu-id="64a85-202">**SessionLoginName**</span></span>|<span data-ttu-id="64a85-203">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="64a85-203">**nvarchar**</span></span>|<span data-ttu-id="64a85-204">Nome de logon do usuário que originou a sessão.</span><span class="sxs-lookup"><span data-stu-id="64a85-204">Login name of the user that originated the session.</span></span> <span data-ttu-id="64a85-205">Por exemplo, para se conectar ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando o Logon1 e executar uma instrução como Logon2, o **SessionLoginName** mostrará o Logon1 e o **LoginName** mostrará o Logon2.</span><span class="sxs-lookup"><span data-stu-id="64a85-205">For example, if you connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and execute a statement as Login2, **SessionLoginName** shows Login1 and **LoginName** shows Login2.</span></span> <span data-ttu-id="64a85-206">Essa coluna exibe logons do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e do Windows.</span><span class="sxs-lookup"><span data-stu-id="64a85-206">This column displays both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="64a85-207">64</span><span class="sxs-lookup"><span data-stu-id="64a85-207">64</span></span>|<span data-ttu-id="64a85-208">Sim</span><span class="sxs-lookup"><span data-stu-id="64a85-208">Yes</span></span>|  
|<span data-ttu-id="64a85-209">**SPID**</span><span class="sxs-lookup"><span data-stu-id="64a85-209">**SPID**</span></span>|<span data-ttu-id="64a85-210">**Int**</span><span class="sxs-lookup"><span data-stu-id="64a85-210">**Int**</span></span>|<span data-ttu-id="64a85-211">Identificação da sessão em que ocorreu o evento.</span><span class="sxs-lookup"><span data-stu-id="64a85-211">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="64a85-212">12</span><span class="sxs-lookup"><span data-stu-id="64a85-212">12</span></span>|<span data-ttu-id="64a85-213">Sim</span><span class="sxs-lookup"><span data-stu-id="64a85-213">Yes</span></span>|  
|<span data-ttu-id="64a85-214">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="64a85-214">**StartTime**</span></span>|<span data-ttu-id="64a85-215">**datetime**</span><span class="sxs-lookup"><span data-stu-id="64a85-215">**datetime**</span></span>|<span data-ttu-id="64a85-216">Hora de início do evento, se disponível.</span><span class="sxs-lookup"><span data-stu-id="64a85-216">Time at which the event started, if available.</span></span>|<span data-ttu-id="64a85-217">14</span><span class="sxs-lookup"><span data-stu-id="64a85-217">14</span></span>|<span data-ttu-id="64a85-218">Sim</span><span class="sxs-lookup"><span data-stu-id="64a85-218">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="64a85-219">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="64a85-219">See Also</span></span>  
 [<span data-ttu-id="64a85-220">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="64a85-220">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  