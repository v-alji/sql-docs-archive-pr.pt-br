---
title: MSSQLSERVER_18456 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 18456 (Database Engine error)
ms.assetid: c417631d-be1f-42e0-8844-9f92c77e11f7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f5addb6bfb9d056d9f1796749ae629d4150102a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680451"
---
# <a name="mssqlserver_18456"></a><span data-ttu-id="6a823-102">MSSQLSERVER_18456</span><span class="sxs-lookup"><span data-stu-id="6a823-102">MSSQLSERVER_18456</span></span>
    
## <a name="details"></a><span data-ttu-id="6a823-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="6a823-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6a823-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="6a823-104">Product Name</span></span>|<span data-ttu-id="6a823-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6a823-105">SQL Server</span></span>|  
|<span data-ttu-id="6a823-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="6a823-106">Event ID</span></span>|<span data-ttu-id="6a823-107">18456</span><span class="sxs-lookup"><span data-stu-id="6a823-107">18456</span></span>|  
|<span data-ttu-id="6a823-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="6a823-108">Event Source</span></span>|<span data-ttu-id="6a823-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6a823-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6a823-110">Componente</span><span class="sxs-lookup"><span data-stu-id="6a823-110">Component</span></span>|<span data-ttu-id="6a823-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6a823-111">SQLEngine</span></span>|  
|<span data-ttu-id="6a823-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="6a823-112">Symbolic Name</span></span>|<span data-ttu-id="6a823-113">LOGON_FAILED</span><span class="sxs-lookup"><span data-stu-id="6a823-113">LOGON_FAILED</span></span>|  
|<span data-ttu-id="6a823-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="6a823-114">Message Text</span></span>|<span data-ttu-id="6a823-115">Falha no logon do usuário '%.\*ls'.%.\*ls</span><span class="sxs-lookup"><span data-stu-id="6a823-115">Login failed for user '%.\*ls'.%.\*ls</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6a823-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="6a823-116">Explanation</span></span>  
 <span data-ttu-id="6a823-117">Quando uma tentativa de conexão é rejeitada por causa de uma falha na autenticação que envolva uma senha ou um nome de usuário incorreto, uma mensagem semelhante à seguinte é retornada ao cliente:  “Falha no logon do usuário '<nome_do_usuário>'.</span><span class="sxs-lookup"><span data-stu-id="6a823-117">When a connection attempt is rejected because of an authentication failure that involves a bad password or user name, a message similar to the following is returned to the client:  "Login failed for user '<user_name>'.</span></span> <span data-ttu-id="6a823-118">(Microsoft SQL Server, Erro: 18456)".</span><span class="sxs-lookup"><span data-stu-id="6a823-118">(Microsoft SQL Server, Error: 18456)".</span></span>  
  
 <span data-ttu-id="6a823-119">Informações adicionais voltadas ao cliente incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6a823-119">Additional information returned to the client includes the following:</span></span>  
  
 <span data-ttu-id="6a823-120">“Falha no logon do usuário '<nome_do_usuário>'.</span><span class="sxs-lookup"><span data-stu-id="6a823-120">"Login failed for user '<user_name>'.</span></span> <span data-ttu-id="6a823-121">(Provedor da Dados .Net SqlClient)"</span><span class="sxs-lookup"><span data-stu-id="6a823-121">(.Net SqlClient Data Provider)"</span></span>  
  
 -----------------------------\-  
  
 <span data-ttu-id="6a823-122">"Nome do servidor: <nome_do_computador>"</span><span class="sxs-lookup"><span data-stu-id="6a823-122">"Server Name: <computer_name>"</span></span>  
  
 <span data-ttu-id="6a823-123">"Número do erro: 18456"</span><span class="sxs-lookup"><span data-stu-id="6a823-123">"Error Number: 18456"</span></span>  
  
 <span data-ttu-id="6a823-124">"Severidade: 14"</span><span class="sxs-lookup"><span data-stu-id="6a823-124">"Severity: 14"</span></span>  
  
 <span data-ttu-id="6a823-125">"Estado: 1"</span><span class="sxs-lookup"><span data-stu-id="6a823-125">"State: 1"</span></span>  
  
 <span data-ttu-id="6a823-126">"Número de Linha: 65536"</span><span class="sxs-lookup"><span data-stu-id="6a823-126">"Line Number: 65536"</span></span>  
  
 <span data-ttu-id="6a823-127">A mensagem seguinte também poderá ser retornada:</span><span class="sxs-lookup"><span data-stu-id="6a823-127">The following message might also be returned:</span></span>  
  
 <span data-ttu-id="6a823-128">"Msg 18456, nível 14, estado 1, servidor <nome_do_computador>, linha 1"</span><span class="sxs-lookup"><span data-stu-id="6a823-128">"Msg 18456, Level 14, State 1, Server <computer_name>, Line 1"</span></span>  
  
 <span data-ttu-id="6a823-129">Falha no logon do usuário '<nome_do_usuário>'."</span><span class="sxs-lookup"><span data-stu-id="6a823-129">"Login failed for user '<user_name>'."</span></span>  
  
## <a name="additional-error-information"></a><span data-ttu-id="6a823-130">Informações adicionais de erro</span><span class="sxs-lookup"><span data-stu-id="6a823-130">Additional Error Information</span></span>  
 <span data-ttu-id="6a823-131">Para aumentar a segurança, a mensagem de erro que é retornada ao cliente oculta deliberadamente a natureza do erro de autenticação.</span><span class="sxs-lookup"><span data-stu-id="6a823-131">To increase security, the error message that is returned to the client deliberately hides the nature of the authentication error.</span></span> <span data-ttu-id="6a823-132">No entanto, no log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], um erro correspondente contém um estado de erro que mapeia até uma condição de falha na autenticação.</span><span class="sxs-lookup"><span data-stu-id="6a823-132">However, in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log, a corresponding error contains an error state that maps to an authentication failure condition.</span></span> <span data-ttu-id="6a823-133">Compare o estado de erro com a lista a seguir para determinar a razão da falha no logon.</span><span class="sxs-lookup"><span data-stu-id="6a823-133">Compare the error state to the following list to determine the reason for the login failure.</span></span>  
  
|<span data-ttu-id="6a823-134">Estado</span><span class="sxs-lookup"><span data-stu-id="6a823-134">State</span></span>|<span data-ttu-id="6a823-135">Descrição</span><span class="sxs-lookup"><span data-stu-id="6a823-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6a823-136">1</span><span class="sxs-lookup"><span data-stu-id="6a823-136">1</span></span>|<span data-ttu-id="6a823-137">Informações de erro não disponíveis.</span><span class="sxs-lookup"><span data-stu-id="6a823-137">Error information is not available.</span></span> <span data-ttu-id="6a823-138">Esse estado geralmente significa que você não tem permissão para receber os detalhes do erro.</span><span class="sxs-lookup"><span data-stu-id="6a823-138">This state usually means you do not have permission to receive the error details.</span></span> <span data-ttu-id="6a823-139">Contate o administrador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="6a823-139">Contact your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administrator for more information.</span></span>|  
|<span data-ttu-id="6a823-140">2</span><span class="sxs-lookup"><span data-stu-id="6a823-140">2</span></span>|<span data-ttu-id="6a823-141">A ID do usuário não é válida.</span><span class="sxs-lookup"><span data-stu-id="6a823-141">User ID is not valid.</span></span>|  
|<span data-ttu-id="6a823-142">5</span><span class="sxs-lookup"><span data-stu-id="6a823-142">5</span></span>|<span data-ttu-id="6a823-143">A ID do usuário não é válida.</span><span class="sxs-lookup"><span data-stu-id="6a823-143">User ID is not valid.</span></span>|  
|<span data-ttu-id="6a823-144">6</span><span class="sxs-lookup"><span data-stu-id="6a823-144">6</span></span>|<span data-ttu-id="6a823-145">Uma tentativa foi feita para usar um logon do Windows com Autenticação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6a823-145">An attempt was made to use a Windows login name with SQL Server Authentication.</span></span>|  
|<span data-ttu-id="6a823-146">7</span><span class="sxs-lookup"><span data-stu-id="6a823-146">7</span></span>|<span data-ttu-id="6a823-147">O logon está desabilitado e a senha está incorreta.</span><span class="sxs-lookup"><span data-stu-id="6a823-147">Login is disabled, and the password is incorrect.</span></span>|  
|<span data-ttu-id="6a823-148">8</span><span class="sxs-lookup"><span data-stu-id="6a823-148">8</span></span>|<span data-ttu-id="6a823-149">A senha está incorreta.</span><span class="sxs-lookup"><span data-stu-id="6a823-149">The password is incorrect.</span></span>|  
|<span data-ttu-id="6a823-150">9</span><span class="sxs-lookup"><span data-stu-id="6a823-150">9</span></span>|<span data-ttu-id="6a823-151">A senha não é válida.</span><span class="sxs-lookup"><span data-stu-id="6a823-151">Password is not valid.</span></span>|  
|<span data-ttu-id="6a823-152">11</span><span class="sxs-lookup"><span data-stu-id="6a823-152">11</span></span>|<span data-ttu-id="6a823-153">O logon é válido, mas houve falha no acesso ao servidor.</span><span class="sxs-lookup"><span data-stu-id="6a823-153">Login is valid, but server access failed.</span></span> <span data-ttu-id="6a823-154">Uma causa possível deste erro é quando o usuário do Windows tem acesso ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] como membro do grupo de administradores locais, mas o Windows não está fornecendo credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="6a823-154">One possible cause of this error is when the Windows user has access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as a member of the local administrators group, but Windows is not providing administrator credentials.</span></span> <span data-ttu-id="6a823-155">Para se conectar, inicie o programa de conexão usando a opção **Executar como administrador** e, depois, adicione o usuário do Windows ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] como um logon específico.</span><span class="sxs-lookup"><span data-stu-id="6a823-155">To connect, start the connecting program using the **Run as administrator** option, and then add the Windows user to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as a specific login.</span></span>|  
|<span data-ttu-id="6a823-156">12</span><span class="sxs-lookup"><span data-stu-id="6a823-156">12</span></span>|<span data-ttu-id="6a823-157">O logon é válido, mas houve falha no acesso ao servidor.</span><span class="sxs-lookup"><span data-stu-id="6a823-157">Login is valid login, but server access failed.</span></span>|  
|<span data-ttu-id="6a823-158">18</span><span class="sxs-lookup"><span data-stu-id="6a823-158">18</span></span>|<span data-ttu-id="6a823-159">A senha deve ser alterada.</span><span class="sxs-lookup"><span data-stu-id="6a823-159">Password must be changed.</span></span>|  
  
 <span data-ttu-id="6a823-160">Outros estados de erro existem e significam um erro de processamento interno inesperado.</span><span class="sxs-lookup"><span data-stu-id="6a823-160">Other error states exist and signify an unexpected internal processing error.</span></span>  
  
 <span data-ttu-id="6a823-161">**Outra possível causa incomum**</span><span class="sxs-lookup"><span data-stu-id="6a823-161">**An additional unusual possible cause**</span></span>  
  
 <span data-ttu-id="6a823-162">A razão de erro **Falha em uma tentativa de logon com a Autenticação do SQL Server. O servidor está configurado apenas para a autenticação do Windows.**</span><span class="sxs-lookup"><span data-stu-id="6a823-162">The error reason **An attempt to login using SQL authentication failed. Server is configured for Windows authentication only.**</span></span> <span data-ttu-id="6a823-163">pode ser retornado nas situações a seguir.</span><span class="sxs-lookup"><span data-stu-id="6a823-163">can be returned in the following situations.</span></span>  
  
-   <span data-ttu-id="6a823-164">Quando o servidor é configurado para a autenticação de modo misto e uma conexão ODBC usa o protocolo TCP, e a conexão não especificar explicitamente que a conexão deve usar uma conexão confiável.</span><span class="sxs-lookup"><span data-stu-id="6a823-164">When the server is configured for mixed mode authentication, and an ODBC connection uses the TCP protocol, and the connection does not explicitly specify that the connection should use a trusted connection.</span></span>  
  
-   <span data-ttu-id="6a823-165">Quando o servidor é configurado para a autenticação de modo misto, e uma conexão ODBC usa pipes nomeados, e as credenciais que o cliente usou para abrir o pipe nomeado são usadas para representar automaticamente o usuário, e a conexão não especificar explicitamente que ela deve usar uma conexão confiável.</span><span class="sxs-lookup"><span data-stu-id="6a823-165">When the server is configured for mixed mode authentication, and an ODBC connection uses named pipes, and the credentials the client used to open the named pipe are used to automatically impersonate the user, and the connection does not explicitly specify that the connection should use a trusted connection.</span></span>  
  
 <span data-ttu-id="6a823-166">Para resolver esse problema, inclua `TRUSTED_CONNECTION = TRUE` na cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="6a823-166">To resolve this issue, include `TRUSTED_CONNECTION = TRUE` in the connection string.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="6a823-167">Exemplos</span><span class="sxs-lookup"><span data-stu-id="6a823-167">Examples</span></span>  
 <span data-ttu-id="6a823-168">Neste exemplo, o estado do erro de autenticação é 8.</span><span class="sxs-lookup"><span data-stu-id="6a823-168">In this example, the authentication error state is 8.</span></span> <span data-ttu-id="6a823-169">Isso indica que a senha está incorreta.</span><span class="sxs-lookup"><span data-stu-id="6a823-169">This indicates that the password is incorrect.</span></span>  
  
|<span data-ttu-id="6a823-170">Data</span><span class="sxs-lookup"><span data-stu-id="6a823-170">Date</span></span>|<span data-ttu-id="6a823-171">Fonte</span><span class="sxs-lookup"><span data-stu-id="6a823-171">Source</span></span>|<span data-ttu-id="6a823-172">Mensagem</span><span class="sxs-lookup"><span data-stu-id="6a823-172">Message</span></span>|  
|----------|------------|-------------|  
|<span data-ttu-id="6a823-173">2007-12-05 20:12:56.34</span><span class="sxs-lookup"><span data-stu-id="6a823-173">2007-12-05 20:12:56.34</span></span>|<span data-ttu-id="6a823-174">Logon</span><span class="sxs-lookup"><span data-stu-id="6a823-174">Logon</span></span>|<span data-ttu-id="6a823-175">Erro: 18456, Severidade: 14, Estado: 8.</span><span class="sxs-lookup"><span data-stu-id="6a823-175">Error: 18456, Severity: 14, State: 8.</span></span>|  
|<span data-ttu-id="6a823-176">2007-12-05 20:12:56.34</span><span class="sxs-lookup"><span data-stu-id="6a823-176">2007-12-05 20:12:56.34</span></span>|<span data-ttu-id="6a823-177">Logon</span><span class="sxs-lookup"><span data-stu-id="6a823-177">Logon</span></span>|<span data-ttu-id="6a823-178">Falha no logon do usuário '<nome_do_usuário>'.</span><span class="sxs-lookup"><span data-stu-id="6a823-178">Login failed for user '<user_name>'.</span></span> <span data-ttu-id="6a823-179">[CLIENTE: \<ip address>]</span><span class="sxs-lookup"><span data-stu-id="6a823-179">[CLIENT: \<ip address>]</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="6a823-180">Quando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é instalado usando o modo de Autenticação do Windows e depois alterado para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e o modo de Autenticação do Windows, o logon **sa** é inicialmente desabilitado.</span><span class="sxs-lookup"><span data-stu-id="6a823-180">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed using Windows Authentication mode and is later changed to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows Authentication mode, the **sa** login is initially disabled.</span></span> <span data-ttu-id="6a823-181">Isso causa o erro de estado 7: "Falha no logon do usuário 'sa'." Para habilitar o logon **sa**, consulte [Alterar modo de autenticação do servidor](../../database-engine/configure-windows/change-server-authentication-mode.md).</span><span class="sxs-lookup"><span data-stu-id="6a823-181">This causes the state 7 error: "Login failed for user 'sa'." To enable the **sa** login, see [Change Server Authentication Mode](../../database-engine/configure-windows/change-server-authentication-mode.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6a823-182">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="6a823-182">User Action</span></span>  
 <span data-ttu-id="6a823-183">Se você estiver tentando se conectar usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], verifique se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está configurado no Modo de Autenticação Mista.</span><span class="sxs-lookup"><span data-stu-id="6a823-183">If you are trying to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, verify that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured in Mixed Authentication Mode.</span></span>  
  
 <span data-ttu-id="6a823-184">Se você estiver tentando se conectar usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], verifique se o logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] existe e se você o escreveu corretamente.</span><span class="sxs-lookup"><span data-stu-id="6a823-184">If you are trying to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, verify that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login exists and that you have spelled it properly.</span></span>  
  
 <span data-ttu-id="6a823-185">Se você estiver tentando se conectar usando a Autenticação do Windows, verifique se está devidamente conectado no domínio correto.</span><span class="sxs-lookup"><span data-stu-id="6a823-185">If you are trying to connect using Windows Authentication, verify that you are properly logged into the correct domain.</span></span>  
  
 <span data-ttu-id="6a823-186">Se o erro indicar estado 1, contate o administrador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6a823-186">If your error indicates state 1, contact your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administrator.</span></span>  
  
 <span data-ttu-id="6a823-187">Se você estiver tentando se conectar usando suas credenciais de administrador, inicie o aplicativo usando a opção **Executar como Administrador**.</span><span class="sxs-lookup"><span data-stu-id="6a823-187">If you are trying to connect using your administrator credentials, start you application by using the **Run as Administrator** option.</span></span> <span data-ttu-id="6a823-188">Quando conectado, adicione seu usuário do Windows como um logon individual.</span><span class="sxs-lookup"><span data-stu-id="6a823-188">When connected, add your Windows user as an individual login.</span></span>  
  
 <span data-ttu-id="6a823-189">Se o [!INCLUDE[ssDE](../../includes/ssde-md.md)] oferecer suporte a bancos de dados independentes, confirme que o logon não foi excluído após a migração para um usuário de banco de dados independente.</span><span class="sxs-lookup"><span data-stu-id="6a823-189">If the [!INCLUDE[ssDE](../../includes/ssde-md.md)] supports contained databases, confirm that the login was not deleted after migration to a contained database user.</span></span>  
  
 <span data-ttu-id="6a823-190">Durante a conexão local a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], as conexões de serviços executados em **NT AUTHORITY\NETWORK SERVICE** deverão ser autenticadas com o uso do nome de domínio totalmente qualificado dos computadores.</span><span class="sxs-lookup"><span data-stu-id="6a823-190">When connecting locally to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], connections from services running under **NT AUTHORITY\NETWORK SERVICE** must authenticate using the computers fully qualified domain name.</span></span> <span data-ttu-id="6a823-191">Para saber mais, confira [Como usar a conta de serviço de rede para acessar recursos no ASP.NET](https://msdn.microsoft.com/library/ff647402.aspx)</span><span class="sxs-lookup"><span data-stu-id="6a823-191">For more information, see [How To: Use the Network Service Account to Access Resources in ASP.NET](https://msdn.microsoft.com/library/ff647402.aspx)</span></span>  
  
  
