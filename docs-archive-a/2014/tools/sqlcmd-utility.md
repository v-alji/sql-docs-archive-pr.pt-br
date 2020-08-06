---
title: Utilitário sqlcmd | Microsoft Docs
ms.custom: ''
ms.date: 11/29/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- statements [SQL Server], command prompt
- QUIT command
- Transact-SQL statements, command prompt
- EXIT command
- sqlcmd commands
- ED command
- sqlcmd utility
- command prompt utilities [SQL Server], sqlcmd
- '!! command'
- stored procedures [SQL Server], command prompt
- system stored procedures [SQL Server], command prompt
- sqlcmd utility, about sqlcmd utility
- scripts [SQL Server], command prompt
- RESET command
- GO command
ms.assetid: e1728707-5215-4c04-8320-e36f161b834a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9fbe5a3dcefb2218543e015dad71acfe79aea8e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684426"
---
# <a name="sqlcmd-utility"></a><span data-ttu-id="e029d-102">Utilitário sqlcmd</span><span class="sxs-lookup"><span data-stu-id="e029d-102">sqlcmd Utility</span></span>
  <span data-ttu-id="e029d-103">O `sqlcmd` utilitário permite que você insira [!INCLUDE[tsql](../includes/tsql-md.md)] instruções, procedimentos do sistema e arquivos de script no prompt de comando, no **Editor de consultas** no modo sqlcmd, em um arquivo de script do Windows ou em uma etapa de trabalho do sistema operacional (Cmd.exe) de um trabalho do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="e029d-103">The `sqlcmd` utility lets you enter [!INCLUDE[tsql](../includes/tsql-md.md)] statements, system procedures, and script files at the command prompt, in **Query Editor** in SQLCMD mode, in a Windows script file or in an operating system (Cmd.exe) job step of a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent job.</span></span> <span data-ttu-id="e029d-104">Esse utilitário usa ODBC para executar lotes [!INCLUDE[tsql](../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e029d-104">This utility uses ODBC to execute [!INCLUDE[tsql](../includes/tsql-md.md)] batches.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]<span data-ttu-id="e029d-105">usa o [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] SqlClient para execução no modo normal e sqlcmd no **Editor de consultas**.</span><span class="sxs-lookup"><span data-stu-id="e029d-105">uses the [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]SqlClient for execution in regular and SQLCMD mode in **Query Editor**.</span></span> <span data-ttu-id="e029d-106">Quando `sqlcmd` é executado na linha de comando, `sqlcmd` usa o driver ODBC.</span><span class="sxs-lookup"><span data-stu-id="e029d-106">When `sqlcmd` is run from the command line, `sqlcmd` uses the ODBC driver.</span></span> <span data-ttu-id="e029d-107">Devido às diversas opções padrão que podem ser aplicadas, é possível observar um comportamento diferente ao executar a mesma consulta no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] no Modo SQLCMD e no utilitário `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="e029d-107">Because different default options may apply, you might see different behavior when you execute the same query in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] in SQLCMD Mode and in the `sqlcmd` utility.</span></span>  
  
 <span data-ttu-id="e029d-108">Atualmente, `sqlcmd` não requer um espaço entre a opção de linha de comando e o valor.</span><span class="sxs-lookup"><span data-stu-id="e029d-108">Currently, `sqlcmd` does not require a space between the command line option and the value.</span></span> <span data-ttu-id="e029d-109">Porém, em uma versão futura, um espaço pode ser necessário entre a opção de linha de comando e o valor.</span><span class="sxs-lookup"><span data-stu-id="e029d-109">However, in a future release, a space may be required between the command line option and the value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e029d-110">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e029d-110">Syntax</span></span>  
  
```  
  
   sqlcmd  
   -a  
   packet_size  
   -A (dedicated administrator connection)  
-b (terminate batch job if there is an error)  
-cbatch_terminator-C (trust the server certificate)  
-ddb_name-e (echo input)  
-E (use trusted connection)  
-fcodepage | i:codepage[,o:codepage] | o:codepage[,i:codepage]  
-hrows_per_header-Hworkstation_name-iinput_file-I (enable quoted identifiers)  
-k[1 | 2] (remove or replace control characters)  
-Kapplication_intent-llogin_timeout-L[c] (list servers, optional clean output)  
-merror_level-Mmultisubnet_failover-N (encrypt connection)  
-ooutput_file-p[1] (print statistics, optional colon format)  
-Ppassword-q "cmdline query"-Q "cmdline query" (and exit)  
-r[0 | 1] (msgs to stderr)  
-R (use client regional settings)  
-scol_separator-S [protocol:]server[\instance_name][,port]  
-tquery_timeout-u (unicode output file)  
-Ulogin_id-vvar = "value"-Verror_severity_level-wcolumn_width-W (remove trailing spaces)  
-x (disable variable substitution)  
-X[1] (disable commands, startup script, environment variables and optional exit)  
-yvariable_length_type_display_width-Yfixed_length_type_display_width-znew_password -Znew_password (and exit)  
  
-? (usage)  
```  
  
## <a name="command-line-options"></a><span data-ttu-id="e029d-111">Opções de linha de comando</span><span class="sxs-lookup"><span data-stu-id="e029d-111">Command-line Options</span></span>  
 <span data-ttu-id="e029d-112">**Opções relacionadas a logon**</span><span class="sxs-lookup"><span data-stu-id="e029d-112">**Login-Related Options**</span></span>  
  <span data-ttu-id="e029d-113">**-A**</span><span class="sxs-lookup"><span data-stu-id="e029d-113">**-A**</span></span>  
 <span data-ttu-id="e029d-114">Fazer logon no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] com uma DAC (conexão de administrador dedicada).</span><span class="sxs-lookup"><span data-stu-id="e029d-114">Logs in to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] with a Dedicated Administrator Connection (DAC).</span></span> <span data-ttu-id="e029d-115">Esse tipo de conexão é usado para solucionar um problema no servidor.</span><span class="sxs-lookup"><span data-stu-id="e029d-115">This kind of connection is used to troubleshoot a server.</span></span> <span data-ttu-id="e029d-116">Isso funcionará apenas com computadores servidor que oferecem suporte para DAC.</span><span class="sxs-lookup"><span data-stu-id="e029d-116">This will only work with server computers that support DAC.</span></span> <span data-ttu-id="e029d-117">Se a DAC não estiver disponível, o `sqlcmd` gerará uma mensagem de erro e será encerrado.</span><span class="sxs-lookup"><span data-stu-id="e029d-117">If DAC is not available, `sqlcmd` generates an error message and then exits.</span></span> <span data-ttu-id="e029d-118">Para obter mais informações sobre a DAC, consulte [Conexão de diagnóstico para administradores de banco de dados](../database-engine/configure-windows/diagnostic-connection-for-database-administrators.md).</span><span class="sxs-lookup"><span data-stu-id="e029d-118">For more information about DAC, see [Diagnostic Connection for Database Administrators](../database-engine/configure-windows/diagnostic-connection-for-database-administrators.md).</span></span>  
  
 <span data-ttu-id="e029d-119">**-C**</span><span class="sxs-lookup"><span data-stu-id="e029d-119">**-C**</span></span>  
 <span data-ttu-id="e029d-120">Essa opção é usada pelo cliente para configurá-lo para confiar implicitamente no certificado do servidor sem validação.</span><span class="sxs-lookup"><span data-stu-id="e029d-120">This switch is used by the client to configure it to implicitly trust the server certificate without validation.</span></span> <span data-ttu-id="e029d-121">Essa opção é equivalente à opção `TRUSTSERVERCERTIFICATE = true`do ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="e029d-121">This option is equivalent to the ADO.NET option `TRUSTSERVERCERTIFICATE = true`.</span></span>  
  
 <span data-ttu-id="e029d-122">**-d** _db_name_</span><span class="sxs-lookup"><span data-stu-id="e029d-122">**-d** _db_name_</span></span>  
 <span data-ttu-id="e029d-123">Emite uma `USE` instrução *db_name* quando você inicia `sqlcmd` .</span><span class="sxs-lookup"><span data-stu-id="e029d-123">Issues a `USE` *db_name* statement when you start `sqlcmd`.</span></span> <span data-ttu-id="e029d-124">Essa opção define a variável de script SQLCMDDBNAME do `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="e029d-124">This option sets the `sqlcmd` scripting variable SQLCMDDBNAME.</span></span> <span data-ttu-id="e029d-125">Isso especifica o banco de dados inicial.</span><span class="sxs-lookup"><span data-stu-id="e029d-125">This specifies the initial database.</span></span> <span data-ttu-id="e029d-126">O padrão é a propriedade do banco de dados padrão de seu logon.</span><span class="sxs-lookup"><span data-stu-id="e029d-126">The default is your login's default-database property.</span></span> <span data-ttu-id="e029d-127">Se o banco de dados não existir, será gerada uma mensagem de erro e o `sqlcmd` é encerrado.</span><span class="sxs-lookup"><span data-stu-id="e029d-127">If the database does not exist, an error message is generated and `sqlcmd` exits.</span></span>  
  
 <span data-ttu-id="e029d-128">**-l** _login_timeout_</span><span class="sxs-lookup"><span data-stu-id="e029d-128">**-l** _login_timeout_</span></span>  
 <span data-ttu-id="e029d-129">Especifica o número de segundos antes que um logon do `sqlcmd` para o driver ODBC expire, ao tentar conectar a um servidor.</span><span class="sxs-lookup"><span data-stu-id="e029d-129">Specifies the number of seconds before a `sqlcmd` login to the ODBC driver times out when you try to connect to a server.</span></span> <span data-ttu-id="e029d-130">Essa opção define a variável de script SQLCMDLOGINTIMEOUT do `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="e029d-130">This option sets the `sqlcmd` scripting variable SQLCMDLOGINTIMEOUT.</span></span> <span data-ttu-id="e029d-131">O tempo limite padrão de logon do `sqlcmd` é de oito segundos.</span><span class="sxs-lookup"><span data-stu-id="e029d-131">The default time-out for login to `sqlcmd` is eight seconds.</span></span> <span data-ttu-id="e029d-132">O tempo limite do logon deve ser um número entre 0 e 65534.</span><span class="sxs-lookup"><span data-stu-id="e029d-132">The login time-out must be a number between 0 and 65534.</span></span> <span data-ttu-id="e029d-133">O `sqlcmd` irá gerar uma mensagem de erro se o valor fornecido não for numérico ou não estiver nesse intervalo.</span><span class="sxs-lookup"><span data-stu-id="e029d-133">If the value supplied is not numeric or does not fall into that range, `sqlcmd` generates an error message.</span></span> <span data-ttu-id="e029d-134">Um valor de 0 especifica o tempo limite como infinito.</span><span class="sxs-lookup"><span data-stu-id="e029d-134">A value of 0 specifies time-out to be infinite.</span></span>  
  
 <span data-ttu-id="e029d-135">**-E**</span><span class="sxs-lookup"><span data-stu-id="e029d-135">**-E**</span></span>  
 <span data-ttu-id="e029d-136">Usa uma conexão confiável em vez de um nome de usuário e senha para fazer logon no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e029d-136">Uses a trusted connection instead of using a user name and password to log on to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e029d-137">Por padrão, sem a especificação de -E, `sqlcmd` usa a opção de conexão confiável.</span><span class="sxs-lookup"><span data-stu-id="e029d-137">By default, without -E specified, `sqlcmd` uses the trusted connection option.</span></span>  
  
 <span data-ttu-id="e029d-138">A opção **-E** ignora possíveis definições de variável de ambiente de nome de usuário e senha como SQLCMDPASSWORD.</span><span class="sxs-lookup"><span data-stu-id="e029d-138">The **-E** option ignores possible user name and password environment variable settings such as SQLCMDPASSWORD.</span></span> <span data-ttu-id="e029d-139">Se a opção **-E** for usada com as opções **-U** ou **-P** , uma mensagem de erro será gerada.</span><span class="sxs-lookup"><span data-stu-id="e029d-139">If the **-E** option is used together with the **-U** option or the **-P** option, an error message is generated.</span></span>  
  
 <span data-ttu-id="e029d-140">**-H** _workstation_name_</span><span class="sxs-lookup"><span data-stu-id="e029d-140">**-H** _workstation_name_</span></span>  
 <span data-ttu-id="e029d-141">Um nome de estação de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e029d-141">A workstation name.</span></span> <span data-ttu-id="e029d-142">Essa opção define a variável de script SQLCMDWORKSTATION do `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="e029d-142">This option sets the `sqlcmd` scripting variable SQLCMDWORKSTATION.</span></span> <span data-ttu-id="e029d-143">O nome da estação de trabalho é listado na coluna **hostname** da exibição de catálogo **sys.processes** e pode ser retornado usando o procedimento armazenado **sp_who**.</span><span class="sxs-lookup"><span data-stu-id="e029d-143">The workstation name is listed in the **hostname** column of the **sys.processes** catalog view and can be returned using the stored procedure **sp_who**.</span></span> <span data-ttu-id="e029d-144">Se essa opção não for especificada, o padrão será o nome do computador atual.</span><span class="sxs-lookup"><span data-stu-id="e029d-144">If this option is not specified, the default is the current computer name.</span></span> <span data-ttu-id="e029d-145">Esse nome pode ser usado para identificar sessões `sqlcmd` diferentes.</span><span class="sxs-lookup"><span data-stu-id="e029d-145">This name can be used to identify different `sqlcmd` sessions.</span></span>  
  
 <span data-ttu-id="e029d-146">**-K** _application_intent_</span><span class="sxs-lookup"><span data-stu-id="e029d-146">**-K** _application_intent_</span></span>  
 <span data-ttu-id="e029d-147">Declara o tipo de carga de trabalho de aplicativo ao conectar-se a um servidor.</span><span class="sxs-lookup"><span data-stu-id="e029d-147">Declares the application workload type when connecting to a server.</span></span> <span data-ttu-id="e029d-148">O único valor com suporte no momento é **ReadOnly**.</span><span class="sxs-lookup"><span data-stu-id="e029d-148">The only currently supported value is **ReadOnly**.</span></span> <span data-ttu-id="e029d-149">Se **-K** não estiver especificado, o utilitário sqlcmd não terá suporte à conectividade com uma réplica secundária em um grupo de disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="e029d-149">If **-K** is not specified, the sqlcmd utility will not support connectivity to a secondary replica in an AlwaysOn availability group.</span></span> <span data-ttu-id="e029d-150">Para obter mais informações, consulte secundários [ativos: réplicas secundárias legíveis](../database-engine/availability-groups/windows/active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="e029d-150">For more information, see [Active Secondaries: Readable Secondary Replicas](../database-engine/availability-groups/windows/active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span></span>  
  
 <span data-ttu-id="e029d-151">`-M`*multisubnet_failover*</span><span class="sxs-lookup"><span data-stu-id="e029d-151">`-M` *multisubnet_failover*</span></span>  
 <span data-ttu-id="e029d-152">Sempre especifique `-M` ao conectar-se ao ouvinte de um grupo de disponibilidade do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ou de uma instância de cluster de failover do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e029d-152">Always specify `-M` when connecting to the availability group listener of a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] availability group or a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Failover Cluster Instance.</span></span> <span data-ttu-id="e029d-153">`-M` proporciona a detecção mais rápida e a conexão com o servidor (atualmente) ativo.</span><span class="sxs-lookup"><span data-stu-id="e029d-153">`-M` provides for faster detection of and connection to the (currently) active server.</span></span> <span data-ttu-id="e029d-154">Se `-M` não for especificada, `-M` ficará desativada.</span><span class="sxs-lookup"><span data-stu-id="e029d-154">If `-M` is not specified, `-M` is off.</span></span> <span data-ttu-id="e029d-155">Para obter mais informações sobre o [!INCLUDE[ssHADR](../includes/sshadr-md.md)] , consulte [ouvintes de grupo de disponibilidade, conectividade de cliente e failover de aplicativo &#40;SQL Server&#41;](../database-engine/listeners-client-connectivity-application-failover.md), [criação e configuração de grupos de disponibilidade &#40;SQL Server ](../database-engine/availability-groups/windows/creation-and-configuration-of-availability-groups-sql-server.md)&#41;, [clustering de failover e grupos de disponibilidade AlwaysOn ](../database-engine/availability-groups/windows/failover-clustering-and-always-on-availability-groups-sql-server.md)&#40;SQL Server&#41;e secundários [ativos: réplicas secundárias legíveis](../database-engine/availability-groups/windows/active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) .</span><span class="sxs-lookup"><span data-stu-id="e029d-155">For more information about [!INCLUDE[ssHADR](../includes/sshadr-md.md)], see [Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../database-engine/listeners-client-connectivity-application-failover.md), [Creation and Configuration of Availability Groups &#40;SQL Server&#41;](../database-engine/availability-groups/windows/creation-and-configuration-of-availability-groups-sql-server.md), [Failover Clustering and AlwaysOn Availability Groups &#40;SQL Server&#41;](../database-engine/availability-groups/windows/failover-clustering-and-always-on-availability-groups-sql-server.md), and [Active Secondaries: Readable Secondary Replicas](../database-engine/availability-groups/windows/active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) .</span></span>  
  
 <span data-ttu-id="e029d-156">**-N**</span><span class="sxs-lookup"><span data-stu-id="e029d-156">**-N**</span></span>  
 <span data-ttu-id="e029d-157">Essa opção é usada pelo cliente para solicitar uma conexão criptografada.</span><span class="sxs-lookup"><span data-stu-id="e029d-157">This switch is used by the client to request an encrypted connection.</span></span>  
  
 <span data-ttu-id="e029d-158">**-P** _password_</span><span class="sxs-lookup"><span data-stu-id="e029d-158">**-P** _password_</span></span>  
 <span data-ttu-id="e029d-159">É uma senha especificada pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="e029d-159">Is a user-specified password.</span></span> <span data-ttu-id="e029d-160">Senhas diferenciam maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e029d-160">Passwords are case sensitive.</span></span> <span data-ttu-id="e029d-161">Se a opção-U for usada e a opção **-P** não for usada e a variável de ambiente SQLCMDPASSWORD não tiver sido definida, o `sqlcmd` solicitará ao usuário uma senha.</span><span class="sxs-lookup"><span data-stu-id="e029d-161">If the -U option is used and the **-P** option is not used, and the SQLCMDPASSWORD environment variable has not been set, `sqlcmd` prompts the user for a password.</span></span> <span data-ttu-id="e029d-162">Se a opção **-P** for usada no final do prompt de comando sem uma senha, `sqlcmd` o usará a senha padrão (NULL).</span><span class="sxs-lookup"><span data-stu-id="e029d-162">If the **-P** option is used at the end of the command prompt without a password `sqlcmd` uses the default password (NULL).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e029d-163">Não use uma senha em branco.</span><span class="sxs-lookup"><span data-stu-id="e029d-163">Do not use a blank password.</span></span> <span data-ttu-id="e029d-164">Use uma senha forte.</span><span class="sxs-lookup"><span data-stu-id="e029d-164">Use a strong password.</span></span> <span data-ttu-id="e029d-165">Para saber mais, confira [Strong Passwords](../relational-databases/security/strong-passwords.md).</span><span class="sxs-lookup"><span data-stu-id="e029d-165">For more information, see [Strong Passwords](../relational-databases/security/strong-passwords.md).</span></span>  
  
 <span data-ttu-id="e029d-166">A solicitação de senha é exibida no console, como a seguir: `Password:`</span><span class="sxs-lookup"><span data-stu-id="e029d-166">The password prompt is displayed by printing the password prompt to the console, as follows: `Password:`</span></span>  
  
 <span data-ttu-id="e029d-167">A entrada do usuário está oculta.</span><span class="sxs-lookup"><span data-stu-id="e029d-167">User input is hidden.</span></span> <span data-ttu-id="e029d-168">Isso significa que nada é exibido e o cursor fica em posição.</span><span class="sxs-lookup"><span data-stu-id="e029d-168">This means that nothing is displayed and the cursor stays in position.</span></span>  
  
 <span data-ttu-id="e029d-169">A variável de ambiente SQLCMDPASSWORD lhe permite definir uma senha padrão para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="e029d-169">The SQLCMDPASSWORD environment variable lets you set a default password for the current session.</span></span> <span data-ttu-id="e029d-170">Assim, senhas não têm de ser hard-coded em arquivos em lote.</span><span class="sxs-lookup"><span data-stu-id="e029d-170">Therefore, passwords do not have to be hard-coded into batch files.</span></span>  
  
 <span data-ttu-id="e029d-171">O exemplo a seguir define, em primeiro lugar, a variável SQLCMDPASSWORD no prompt de comando e acessa o utilitário `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="e029d-171">The following example first sets the SQLCMDPASSWORD variable at the command prompt and then accesses the `sqlcmd` utility.</span></span> <span data-ttu-id="e029d-172">No prompt de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="e029d-172">At the command prompt, type:</span></span>  
  
 `SET SQLCMDPASSWORD= p@a$$w0rd`  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e029d-173">A senha estará visível para qualquer um que tiver acesso ao monitor do seu computador.</span><span class="sxs-lookup"><span data-stu-id="e029d-173">The password will be visible to anyone who can see your computer monitor.</span></span>  
  
 <span data-ttu-id="e029d-174">No prompt de comando a seguir, digite:</span><span class="sxs-lookup"><span data-stu-id="e029d-174">At the following command prompt, type:</span></span>  
  
 `sqlcmd`  
  
 <span data-ttu-id="e029d-175">Se a combinação de nome de usuário e senha estiver incorreta, uma mensagem de erro será gerada.</span><span class="sxs-lookup"><span data-stu-id="e029d-175">If the user name and password combination is incorrect, an error message is generated.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e029d-176">A variável de ambiente OSQLPASSWORD foi mantida para compatibilidade com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="e029d-176">The OSQLPASSWORD environment variable has been kept for backward compatibility.</span></span> <span data-ttu-id="e029d-177">A variável de ambiente SQLCMDPASSWORD tem precedência sobre a variável de ambiente OSQLPASSWORD; Isso significa que o `sqlcmd` e o **osql** podem ser usados ao lado um do outro sem interferência e que os scripts antigos continuarão a funcionar.</span><span class="sxs-lookup"><span data-stu-id="e029d-177">The SQLCMDPASSWORD environment variable takes precedence over the OSQLPASSWORD environment variable; this means that `sqlcmd` and **osql** can be used next to each other without interference and that old scripts will continue to work.</span></span>  
  
 <span data-ttu-id="e029d-178">Será gerada uma mensagem de erro se a opção **-P** for usada com a opção **-E** .</span><span class="sxs-lookup"><span data-stu-id="e029d-178">If the **-P** option is used with the **-E** option, an error message is generated.</span></span>  
  
 <span data-ttu-id="e029d-179">Se a opção **-P** for seguida de mais de um argumento, uma mensagem de erro será gerada e o programa será fechado.</span><span class="sxs-lookup"><span data-stu-id="e029d-179">If the **-P** option is followed by more than one argument, an error message is generated and the program exits.</span></span>  
  
 <span data-ttu-id="e029d-180">**-S** [*protocolo*:]*servidor*[ **\\** _instance_name_] [**,**_porta_]</span><span class="sxs-lookup"><span data-stu-id="e029d-180">**-S** [*protocol*:]*server*[**\\**_instance_name_][**,**_port_]</span></span>  
 <span data-ttu-id="e029d-181">Especifica uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] à qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="e029d-181">Specifies the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to which to connect.</span></span> <span data-ttu-id="e029d-182">Define a variável de script SQLCMDSERVER do `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="e029d-182">It sets the `sqlcmd` scripting variable SQLCMDSERVER.</span></span>  
  
 <span data-ttu-id="e029d-183">Especifique *server_name* para se conectar à instância padrão do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] nesse computador servidor.</span><span class="sxs-lookup"><span data-stu-id="e029d-183">Specify *server_name* to connect to the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on that server computer.</span></span> <span data-ttu-id="e029d-184">Especifique *server_name* [ **\\** _instance_name_ ] para se conectar a uma instância nomeada do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] no computador do servidor.</span><span class="sxs-lookup"><span data-stu-id="e029d-184">Specify *server_name* [ **\\**_instance_name_ ] to connect to a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on that server computer.</span></span> <span data-ttu-id="e029d-185">Se nenhum servidor for especificado, o `sqlcmd` irá se conectar à instância padrão do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] no computador local.</span><span class="sxs-lookup"><span data-stu-id="e029d-185">If no server computer is specified, `sqlcmd` connects to the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on the local computer.</span></span> <span data-ttu-id="e029d-186">Essa opção é necessária quando se executa o `sqlcmd` de um computador remoto na rede.</span><span class="sxs-lookup"><span data-stu-id="e029d-186">This option is required when you execute `sqlcmd` from a remote computer on the network.</span></span>  
  
 <span data-ttu-id="e029d-187">o *protocolo* pode ser `tcp` (TCP/IP), `lpc` (memória compartilhada) ou `np` (pipes nomeados).</span><span class="sxs-lookup"><span data-stu-id="e029d-187">*protocol* can be `tcp` (TCP/IP), `lpc` (shared memory), or `np` (named pipes).</span></span>  
  
 <span data-ttu-id="e029d-188">Se você não especificar um *server_name* [ **\\** _instance_name_ ] ao iniciar `sqlcmd` , [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o verificará e usará a variável de ambiente SQLCMDSERVER.</span><span class="sxs-lookup"><span data-stu-id="e029d-188">If you do not specify a *server_name* [ **\\**_instance_name_ ] when you start `sqlcmd`, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] checks for and uses the SQLCMDSERVER environment variable.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e029d-189">A variável de ambiente OSQLSERVER foi mantida para compatibilidade com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="e029d-189">The OSQLSERVER environment variable has been kept for backward compatibility.</span></span> <span data-ttu-id="e029d-190">A variável de ambiente SQLCMDSERVER tem precedência sobre a variável de ambiente OSQLSERVER; Isso significa que o `sqlcmd` e o **osql** podem ser usados ao lado um do outro sem interferência e que os scripts antigos continuarão a funcionar.</span><span class="sxs-lookup"><span data-stu-id="e029d-190">The SQLCMDSERVER environment variable takes precedence over the OSQLSERVER environment variable; this means that `sqlcmd` and **osql** can be used next to each other without interference and that old scripts will continue to work.</span></span>  
  
 <span data-ttu-id="e029d-191">**-U** _login_id_</span><span class="sxs-lookup"><span data-stu-id="e029d-191">**-U** _login_id_</span></span>  
 <span data-ttu-id="e029d-192">É a identificação de logon do usuário.</span><span class="sxs-lookup"><span data-stu-id="e029d-192">Is the user login ID.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e029d-193">A variável de ambiente OSQLUSER está disponível para compatibilidade com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="e029d-193">The OSQLUSER environment variable is available for backward compatibility.</span></span> <span data-ttu-id="e029d-194">A variável de ambiente SQLCMDUSER tem precedência em relação à variável de ambiente OSQLUSER.</span><span class="sxs-lookup"><span data-stu-id="e029d-194">The SQLCMDUSER environment variable takes precedence over the OSQLUSER environment variable.</span></span> <span data-ttu-id="e029d-195">Isso significa que o `sqlcmd` e o **osql** podem ser usados ao lado um do outro sem interferência.</span><span class="sxs-lookup"><span data-stu-id="e029d-195">This means that `sqlcmd` and **osql** can be used next to each other without interference.</span></span> <span data-ttu-id="e029d-196">Significa também que scripts **osql** existentes continuarão funcionando.</span><span class="sxs-lookup"><span data-stu-id="e029d-196">It also means that existing **osql** scripts will continue to work.</span></span>  
  
 <span data-ttu-id="e029d-197">Se nem a opção **-U** nem a opção **-P** for especificada, o `sqlcmd` tentará se conectar usando o modo de autenticação do [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="e029d-197">If neither the **-U** option nor the **-P** option is specified, `sqlcmd` tries to connect by using [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication mode.</span></span> <span data-ttu-id="e029d-198">A autenticação baseia-se na conta do Windows do usuário que está executando o `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="e029d-198">Authentication is based on the Windows account of the user who is running `sqlcmd`.</span></span>  
  
 <span data-ttu-id="e029d-199">Se a opção **-U** for usada com a opção **-E** (descrita adiante neste tópico), uma mensagem de erro será gerada.</span><span class="sxs-lookup"><span data-stu-id="e029d-199">If the **-U** option is used with the **-E** option (described later in this topic), an error message is generated.</span></span> <span data-ttu-id="e029d-200">Se a opção **-U** for seguida de mais de um argumento, uma mensagem de erro será gerada e o programa será encerrado.</span><span class="sxs-lookup"><span data-stu-id="e029d-200">If the **-U** option is followed by more than one argument, an error message is generated and the program exits.</span></span>  
  
 <span data-ttu-id="e029d-201">**-z** _new_password_</span><span class="sxs-lookup"><span data-stu-id="e029d-201">**-z** _new_password_</span></span>  
 <span data-ttu-id="e029d-202">Alterar senha:</span><span class="sxs-lookup"><span data-stu-id="e029d-202">Change password:</span></span>  
  
 `sqlcmd -U someuser -P s0mep@ssword -z a_new_p@a$$w0rd`  
  
 <span data-ttu-id="e029d-203">**-Z** _new_password_</span><span class="sxs-lookup"><span data-stu-id="e029d-203">**-Z** _new_password_</span></span>  
 <span data-ttu-id="e029d-204">Alterar senha e sair:</span><span class="sxs-lookup"><span data-stu-id="e029d-204">Change password and exit:</span></span>  
  
 `sqlcmd -U someuser -P s0mep@ssword -Z a_new_p@a$$w0rd`  
  
 <span data-ttu-id="e029d-205">**Opções de entrada/saída**</span><span class="sxs-lookup"><span data-stu-id="e029d-205">**Input/Output Options**</span></span>  
  <span data-ttu-id="e029d-206">**-f** _codepage_ | **i:** _codepage_[ **,o:** _codepage_] | **o:** _codepage_[ **,i:** _codepage_]</span><span class="sxs-lookup"><span data-stu-id="e029d-206">**-f** _codepage_ | **i:**_codepage_[**,o:**_codepage_] | **o:**_codepage_[**,i:**_codepage_]</span></span>  
 <span data-ttu-id="e029d-207">Especifica as páginas de código de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="e029d-207">Specifies the input and output code pages.</span></span> <span data-ttu-id="e029d-208">O número da página de código é um valor numérico que especifica um código de página instalada do Windows.</span><span class="sxs-lookup"><span data-stu-id="e029d-208">The codepage number is a numeric value that specifies an installed Windows code page.</span></span>  
  
 <span data-ttu-id="e029d-209">Regras de conversão de página de código:</span><span class="sxs-lookup"><span data-stu-id="e029d-209">Code-page conversion rules:</span></span>  
  
-   <span data-ttu-id="e029d-210">Se não for especificada nenhuma página de código, o `sqlcmd` usará a página de código atual para arquivos de entrada e de saída, a menos que o arquivo de entrada seja um arquivo Unicode, para o qual não é necessária nenhuma conversão.</span><span class="sxs-lookup"><span data-stu-id="e029d-210">If no code pages are specified, `sqlcmd` will use the current code page for both input and output files, unless the input file is a Unicode file, in which case no conversion is required.</span></span>  
  
-   <span data-ttu-id="e029d-211">O `sqlcmd` reconhece automaticamente arquivos de entrada Unicode big-endian e little-endian.</span><span class="sxs-lookup"><span data-stu-id="e029d-211">`sqlcmd` automatically recognizes both big-endian and little-endian Unicode input files.</span></span> <span data-ttu-id="e029d-212">Se a opção **-u** tiver sido especificada, a saída sempre será Unicode little endian.</span><span class="sxs-lookup"><span data-stu-id="e029d-212">If the **-u** option has been specified, the output will always be little-endian Unicode.</span></span>  
  
-   <span data-ttu-id="e029d-213">Se não for especificado nenhum arquivo de saída, a página de código de saída será a página de código de console.</span><span class="sxs-lookup"><span data-stu-id="e029d-213">If no output file is specified, the output code page will be the console code page.</span></span> <span data-ttu-id="e029d-214">Isso habilita a saída a ser exibida corretamente no console.</span><span class="sxs-lookup"><span data-stu-id="e029d-214">This enables the output to be displayed correctly on the console.</span></span>  
  
-   <span data-ttu-id="e029d-215">Assume-se que arquivos de entrada múltiplos tenham a mesma página de código.</span><span class="sxs-lookup"><span data-stu-id="e029d-215">Multiple input files are assumed to be of the same code page.</span></span> <span data-ttu-id="e029d-216">Arquivos de entrada Unicode e não Unicode podem ser misturados.</span><span class="sxs-lookup"><span data-stu-id="e029d-216">Unicode and non-Unicode input files can be mixed.</span></span>  
  
 <span data-ttu-id="e029d-217">Digite `chcp` no prompt de comando para verificar a página de código de Cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="e029d-217">Enter `chcp` at the command prompt to verify the code page of Cmd.exe.</span></span>  
  
 <span data-ttu-id="e029d-218">**-i** _input_file_[**,**_input_file2_...]</span><span class="sxs-lookup"><span data-stu-id="e029d-218">**-i** _input_file_[**,**_input_file2_...]</span></span>  
 <span data-ttu-id="e029d-219">Identifica o arquivo que contém um lote de instruções SQL ou procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="e029d-219">Identifies the file that contains a batch of SQL statements or stored procedures.</span></span> <span data-ttu-id="e029d-220">Poderão ser especificados vários arquivos para serem lidos e processados em ordem.</span><span class="sxs-lookup"><span data-stu-id="e029d-220">Multiple files may be specified that will be read and processed in order.</span></span> <span data-ttu-id="e029d-221">Não use espaço entre nomes de arquivos.</span><span class="sxs-lookup"><span data-stu-id="e029d-221">Do not use any spaces between file names.</span></span> <span data-ttu-id="e029d-222">`sqlcmd` verificará primeiramente se todos os arquivos especificados existem.</span><span class="sxs-lookup"><span data-stu-id="e029d-222">`sqlcmd` will first check to see whether all the specified files exist.</span></span> <span data-ttu-id="e029d-223">Se um ou mais arquivos não existirem, o `sqlcmd` será encerrado.</span><span class="sxs-lookup"><span data-stu-id="e029d-223">If one or more files do not exist, `sqlcmd` will exit.</span></span> <span data-ttu-id="e029d-224">As opções -i e Q/-q são mutuamente exclusivas.</span><span class="sxs-lookup"><span data-stu-id="e029d-224">The -i and the -Q/-q options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="e029d-225">Exemplos de caminho:</span><span class="sxs-lookup"><span data-stu-id="e029d-225">Path examples:</span></span>  
  
 <span data-ttu-id="e029d-226">**-i** C: \\<nome do arquivo\></span><span class="sxs-lookup"><span data-stu-id="e029d-226">**-i** C:\\<filename\></span></span>  
  
 <span data-ttu-id="e029d-227">**-i** \\ \\<Server \> \\<compartilhamento $>\\<nome do arquivo\></span><span class="sxs-lookup"><span data-stu-id="e029d-227">**-i** \\\\<Server\>\\<Share$>\\<filename\></span></span>  
  
 <span data-ttu-id="e029d-228">**-i** "Pasta C:\Alguma \\<nome do arquivo \> "</span><span class="sxs-lookup"><span data-stu-id="e029d-228">**-i** "C:\Some Folder\\<file name\>"</span></span>  
  
 <span data-ttu-id="e029d-229">Os nomes de caminhos que contêm espaços deverão ficar entre aspas.</span><span class="sxs-lookup"><span data-stu-id="e029d-229">File paths that contain spaces must be enclosed in quotation marks.</span></span>  
  
 <span data-ttu-id="e029d-230">Essa opção pode ser usada mais de uma vez: **-i**_input_file_ **-i**_input_file._</span><span class="sxs-lookup"><span data-stu-id="e029d-230">This option may be used more than once: **-i**_input_file_ **-I**_I input_file._</span></span>  
  
 <span data-ttu-id="e029d-231">**-o** _output_file_</span><span class="sxs-lookup"><span data-stu-id="e029d-231">**-o** _output_file_</span></span>  
 <span data-ttu-id="e029d-232">Identifica o arquivo que recebe a saída do `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="e029d-232">Identifies the file that receives output from `sqlcmd`.</span></span>  
  
 <span data-ttu-id="e029d-233">Se **-u** for especificado, *output_file* será armazenado no formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="e029d-233">If **-u** is specified, the *output_file* is stored in Unicode format.</span></span> <span data-ttu-id="e029d-234">Se o nome do arquivo for inválido, uma mensagem de erro será gerada e o `sqlcmd` será encerrado.</span><span class="sxs-lookup"><span data-stu-id="e029d-234">If the file name is not valid, an error message is generated, and `sqlcmd` exits.</span></span> <span data-ttu-id="e029d-235">O `sqlcmd` não oferece suporte à gravação simultânea de vários processos `sqlcmd` no mesmo arquivo.</span><span class="sxs-lookup"><span data-stu-id="e029d-235">`sqlcmd` does not support concurrent writing of multiple `sqlcmd` processes to the same file.</span></span> <span data-ttu-id="e029d-236">A saída de arquivo será corrompida ou incorreta.</span><span class="sxs-lookup"><span data-stu-id="e029d-236">The file output will be corrupted or incorrect.</span></span> <span data-ttu-id="e029d-237">Consulte a opção **-f** para obter mais informações sobre formatos de arquivo.</span><span class="sxs-lookup"><span data-stu-id="e029d-237">See the **-f** switch for more information about file formats.</span></span> <span data-ttu-id="e029d-238">Esse arquivo será criado se não existir.</span><span class="sxs-lookup"><span data-stu-id="e029d-238">This file will be created if it does not exist.</span></span> <span data-ttu-id="e029d-239">Será substituído um arquivo com o mesmo nome de uma sessão `sqlcmd` anterior.</span><span class="sxs-lookup"><span data-stu-id="e029d-239">A file of the same name from a prior `sqlcmd` session will be overwritten.</span></span> <span data-ttu-id="e029d-240">O arquivo aqui especificado não é o arquivo **stdout** .</span><span class="sxs-lookup"><span data-stu-id="e029d-240">The file specified here is not the **stdout** file.</span></span> <span data-ttu-id="e029d-241">Se um arquivo **stdout** for especificado, esse arquivo não será usado.</span><span class="sxs-lookup"><span data-stu-id="e029d-241">If a **stdout** file is specified this file will not be used.</span></span>  
  
 <span data-ttu-id="e029d-242">Exemplos de caminho:</span><span class="sxs-lookup"><span data-stu-id="e029d-242">Path examples:</span></span>  
  
 <span data-ttu-id="e029d-243">**-o** C: \\< nome de arquivo></span><span class="sxs-lookup"><span data-stu-id="e029d-243">**-o** C:\\< filename></span></span>  
  
 <span data-ttu-id="e029d-244">**-o** \\ \\<Server \> \\<compartilhamento $>\\<nome do arquivo\></span><span class="sxs-lookup"><span data-stu-id="e029d-244">**-o** \\\\<Server\>\\<Share$>\\<filename\></span></span>  
  
 <span data-ttu-id="e029d-245">**-o "** Pasta C:\Alguma \\<nome do arquivo \> "</span><span class="sxs-lookup"><span data-stu-id="e029d-245">**-o "** C:\Some Folder\\<file name\>"</span></span>  
  
 <span data-ttu-id="e029d-246">Os nomes de caminhos que contêm espaços deverão ficar entre aspas.</span><span class="sxs-lookup"><span data-stu-id="e029d-246">File paths that contain spaces must be enclosed in quotation marks.</span></span>  
  
 <span data-ttu-id="e029d-247">**-r**[**0** | **1**]</span><span class="sxs-lookup"><span data-stu-id="e029d-247">**-r**[**0** | **1**]</span></span>  
 <span data-ttu-id="e029d-248">Redireciona a saída da mensagem de erro para a tela (**stderr**).</span><span class="sxs-lookup"><span data-stu-id="e029d-248">Redirects the error message output to the screen (**stderr**).</span></span> <span data-ttu-id="e029d-249">Se você não especificar um parâmetro ou se especificar **0**, serão redirecionadas somente mensagens de erro com nível de severidade 11 ou acima disso.</span><span class="sxs-lookup"><span data-stu-id="e029d-249">If you do not specify a parameter or if you specify **0**, only error messages that have a severity level of 11 or higher are redirected.</span></span> <span data-ttu-id="e029d-250">Se você especificar **1**, serão redirecionadas todas as saídas de mensagens de erro inclusive PRINT.</span><span class="sxs-lookup"><span data-stu-id="e029d-250">If you specify **1**, all error message output including PRINT is redirected.</span></span> <span data-ttu-id="e029d-251">Não tem nenhum efeito se você usar -o.</span><span class="sxs-lookup"><span data-stu-id="e029d-251">Has no effect if you use -o.</span></span> <span data-ttu-id="e029d-252">Por padrão, mensagens são envidadas para **stdout**.</span><span class="sxs-lookup"><span data-stu-id="e029d-252">By default, messages are sent to **stdout**.</span></span>  
  
 <span data-ttu-id="e029d-253">**-R**</span><span class="sxs-lookup"><span data-stu-id="e029d-253">**-R**</span></span>  
 <span data-ttu-id="e029d-254">Faz com que `sqlcmd` o localize colunas numéricas, de moeda, de data e de hora recuperadas [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] com base na localidade do cliente.</span><span class="sxs-lookup"><span data-stu-id="e029d-254">Causes `sqlcmd` to localize numeric, currency, date, and time columns retrieved from [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] based on the client's locale.</span></span> <span data-ttu-id="e029d-255">Por padrão, essas colunas são exibidas usando as configurações regionais do servidor.</span><span class="sxs-lookup"><span data-stu-id="e029d-255">By default, these columns are displayed using the server's regional settings.</span></span>  
  
 <span data-ttu-id="e029d-256">**-u**</span><span class="sxs-lookup"><span data-stu-id="e029d-256">**-u**</span></span>  
 <span data-ttu-id="e029d-257">Especifica se *output_file* é armazenado no formato Unicode, independentemente do formato de *input_file*.</span><span class="sxs-lookup"><span data-stu-id="e029d-257">Specifies that *output_file* is stored in Unicode format, regardless of the format of *input_file*.</span></span>  
  
 <span data-ttu-id="e029d-258">**Opções de execução de consultas**</span><span class="sxs-lookup"><span data-stu-id="e029d-258">**Query Execution Options**</span></span>  
  <span data-ttu-id="e029d-259">**-e**</span><span class="sxs-lookup"><span data-stu-id="e029d-259">**-e**</span></span>  
 <span data-ttu-id="e029d-260">Grava scripts de entrada no dispositivo de saída padrão (**stdout**).</span><span class="sxs-lookup"><span data-stu-id="e029d-260">Writes input scripts to the standard output device (**stdout**).</span></span>  
  
 <span data-ttu-id="e029d-261">**-I**</span><span class="sxs-lookup"><span data-stu-id="e029d-261">**-I**</span></span>  
 <span data-ttu-id="e029d-262">Define a opção de conexão SET QUOTED_IDENTIFIER como ON.</span><span class="sxs-lookup"><span data-stu-id="e029d-262">Sets the SET QUOTED_IDENTIFIER connection option to ON.</span></span> <span data-ttu-id="e029d-263">Por padrão, ela é definida como OFF.</span><span class="sxs-lookup"><span data-stu-id="e029d-263">By default, it is set to OFF.</span></span> <span data-ttu-id="e029d-264">Para obter mais informações, veja [SET QUOTED_IDENTIFIER &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-quoted-identifier-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e029d-264">For more information, see [SET QUOTED_IDENTIFIER &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-quoted-identifier-transact-sql).</span></span>  
  
 <span data-ttu-id="e029d-265">**-q"** _cmdline query_ **"**</span><span class="sxs-lookup"><span data-stu-id="e029d-265">**-q"** _cmdline query_ **"**</span></span>  
 <span data-ttu-id="e029d-266">Executa uma consulta quando `sqlcmd` é iniciado, mas não encerra `sqlcmd` quando a consulta for concluída.</span><span class="sxs-lookup"><span data-stu-id="e029d-266">Executes a query when `sqlcmd` starts, but does not exit `sqlcmd` when the query has finished running.</span></span> <span data-ttu-id="e029d-267">Podem ser executadas consultas delimitadas por vários ponto e vírgula.</span><span class="sxs-lookup"><span data-stu-id="e029d-267">Multiple-semicolon-delimited queries can be executed.</span></span> <span data-ttu-id="e029d-268">Use aspas na consulta, conforme o exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="e029d-268">Use quotation marks around the query, as shown in the following example.</span></span>  
  
 <span data-ttu-id="e029d-269">No prompt de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="e029d-269">At the command prompt, type:</span></span>  
  
 `sqlcmd -d AdventureWorks2012 -q "SELECT FirstName, LastName FROM Person.Person WHERE LastName LIKE 'Whi%';"`  
  
 `sqlcmd -d AdventureWorks2012 -q "SELECT TOP 5 FirstName FROM Person.Person;SELECT TOP 5 LastName FROM Person.Person;"`  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e029d-270">Não use o terminador GO na consulta.</span><span class="sxs-lookup"><span data-stu-id="e029d-270">Do not use the GO terminator in the query.</span></span>  
  
 <span data-ttu-id="e029d-271">Se for especificado `-b` juntamente com essa opção, `sqlcmd` será encerrado com erro.</span><span class="sxs-lookup"><span data-stu-id="e029d-271">If `-b` is specified together with this option, `sqlcmd` exits on error.</span></span> <span data-ttu-id="e029d-272">`-b` é descrita posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="e029d-272">`-b` is described later in this topic.</span></span>  
  
 <span data-ttu-id="e029d-273">**-Q "** _consulta cmdline_ **"**</span><span class="sxs-lookup"><span data-stu-id="e029d-273">**-Q"** _cmdline query_ **"**</span></span>  
 <span data-ttu-id="e029d-274">Executa uma consulta quando `sqlcmd` é iniciado e imediatamente encerra `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="e029d-274">Executes a query when `sqlcmd` starts and then immediately exits `sqlcmd`.</span></span> <span data-ttu-id="e029d-275">Podem ser executadas consultas delimitadas por vários ponto e vírgula.</span><span class="sxs-lookup"><span data-stu-id="e029d-275">Multiple-semicolon-delimited queries can be executed.</span></span>  
  
 <span data-ttu-id="e029d-276">Use aspas na consulta, conforme o exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="e029d-276">Use quotation marks around the query, as shown in the following example.</span></span>  
  
 <span data-ttu-id="e029d-277">No prompt de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="e029d-277">At the command prompt, type:</span></span>  
  
 `sqlcmd -d AdventureWorks2012 -Q "SELECT FirstName, LastName FROM Person.Person WHERE LastName LIKE 'Whi%';"`  
  
 `sqlcmd -d AdventureWorks2012 -Q "SELECT TOP 5 FirstName FROM Person.Person;SELECT TOP 5 LastName FROM Person.Person;"`  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e029d-278">Não use o terminador GO na consulta.</span><span class="sxs-lookup"><span data-stu-id="e029d-278">Do not use the GO terminator in the query.</span></span>  
  
 <span data-ttu-id="e029d-279">Se for especificado `-b` juntamente com essa opção, `sqlcmd` será encerrado com erro.</span><span class="sxs-lookup"><span data-stu-id="e029d-279">If `-b` is specified together with this option, `sqlcmd` exits on error.</span></span> <span data-ttu-id="e029d-280">`-b` é descrita posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="e029d-280">`-b` is described later in this topic.</span></span>  
  
 <span data-ttu-id="e029d-281">**-t** _query_timeout_</span><span class="sxs-lookup"><span data-stu-id="e029d-281">**-t** _query_timeout_</span></span>  
 <span data-ttu-id="e029d-282">Especifica o número de segundos antes que um comando (ou instrução SQL) expire. Essa opção define a `sqlcmd` variável de script SQLCMDSTATTIMEOUT.</span><span class="sxs-lookup"><span data-stu-id="e029d-282">Specifies the number of seconds before a command (or SQL statement) times out. This option sets the `sqlcmd` scripting variable SQLCMDSTATTIMEOUT.</span></span> <span data-ttu-id="e029d-283">Se um valor *time_out* não for especificado, o comando não atingirá o tempo limite. O *query\*\*time_out* precisa ser um número entre 1 e 65534.</span><span class="sxs-lookup"><span data-stu-id="e029d-283">If a *time_out* value is not specified, the command does not time out. The *query\*\*time_out* must be a number between 1 and 65534.</span></span> <span data-ttu-id="e029d-284">O `sqlcmd` irá gerar uma mensagem de erro se o valor fornecido não for numérico ou não estiver nesse intervalo.</span><span class="sxs-lookup"><span data-stu-id="e029d-284">If the value supplied is not numeric or does not fall into that range, `sqlcmd` generates an error message.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e029d-285">O valor do tempo limite real poderá variar em relação ao valor *time_out* especificado em vários segundos.</span><span class="sxs-lookup"><span data-stu-id="e029d-285">The actual time out value may vary from the specified *time_out* value by several seconds.</span></span>  
  
 <span data-ttu-id="e029d-286">**-vvar =** _valor_[ **var =** _valor_...]</span><span class="sxs-lookup"><span data-stu-id="e029d-286">**-vvar =** _value_[ **var =** _value_...]</span></span>  
 <span data-ttu-id="e029d-287">Cria uma `sqlcmd` variável de script que pode ser usada em um `sqlcmd` script.</span><span class="sxs-lookup"><span data-stu-id="e029d-287">Creates a `sqlcmd`scripting variable that can be used in a `sqlcmd` script.</span></span> <span data-ttu-id="e029d-288">Se o valor contiver espaços, mantenha-o entre aspas.</span><span class="sxs-lookup"><span data-stu-id="e029d-288">Enclose the value in quotation marks if the value contains spaces.</span></span> <span data-ttu-id="e029d-289">Você pode especificar vários valores de **_var_** = **" *`values`* "** .</span><span class="sxs-lookup"><span data-stu-id="e029d-289">You can specify multiple **_var_**=**"*`values`*"** values.</span></span> <span data-ttu-id="e029d-290">Se houver erros em quaisquer dos valores especificados, o `sqlcmd` irá gerar uma mensagem de erro e então será encerrado.</span><span class="sxs-lookup"><span data-stu-id="e029d-290">If there are errors in any of the values specified, `sqlcmd` generates an error message and then exits.</span></span>  
  
 `sqlcmd -v MyVar1=something MyVar2="some thing"`  
  
 `sqlcmd -v MyVar1=something -v MyVar2="some thing"`  
  
 <span data-ttu-id="e029d-291">**-x**</span><span class="sxs-lookup"><span data-stu-id="e029d-291">**-x**</span></span>  
 <span data-ttu-id="e029d-292">Faz com que o `sqlcmd` ignore variáveis de script.</span><span class="sxs-lookup"><span data-stu-id="e029d-292">Causes `sqlcmd` to ignore scripting variables.</span></span> <span data-ttu-id="e029d-293">Isso é útil quando um script contém muitas instruções INSERT que podem conter cadeias de caracteres que têm o mesmo formato de variáveis regulares, como $(*variable_name*).</span><span class="sxs-lookup"><span data-stu-id="e029d-293">This is useful when a script contains many INSERT statements that may contain strings that have the same format as regular variables, such as $(*variable_name*).</span></span>  
  
 <span data-ttu-id="e029d-294">**Opções de formatação**</span><span class="sxs-lookup"><span data-stu-id="e029d-294">**Formatting Options**</span></span>  
  <span data-ttu-id="e029d-295">**-h** _headers_</span><span class="sxs-lookup"><span data-stu-id="e029d-295">**-h** _headers_</span></span>  
 <span data-ttu-id="e029d-296">Especifica o número de linhas a imprimir entre os títulos da coluna.</span><span class="sxs-lookup"><span data-stu-id="e029d-296">Specifies the number of rows to print between the column headings.</span></span> <span data-ttu-id="e029d-297">O padrão é imprimir títulos uma vez para cada conjunto de resultados de consulta.</span><span class="sxs-lookup"><span data-stu-id="e029d-297">The default is to print headings one time for each set of query results.</span></span> <span data-ttu-id="e029d-298">Essa opção define a variável de script SQLCMDHEADERS do `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="e029d-298">This option sets the `sqlcmd` scripting variable SQLCMDHEADERS.</span></span> <span data-ttu-id="e029d-299">Use **-1** para especificar que os cabeçalhos não devem ser impressos.</span><span class="sxs-lookup"><span data-stu-id="e029d-299">Use **-1** to specify that headers must not be printed.</span></span> <span data-ttu-id="e029d-300">Qualquer valor inválido faz com que o `sqlcmd` gere uma mensagem de erro e então seja encerrado.</span><span class="sxs-lookup"><span data-stu-id="e029d-300">Any value that is not valid causes `sqlcmd` to generate an error message and then exit.</span></span>  
  
 <span data-ttu-id="e029d-301">**-k** [**1** | **2**]</span><span class="sxs-lookup"><span data-stu-id="e029d-301">**-k** [**1** | **2**]</span></span>  
 <span data-ttu-id="e029d-302">Remove todos os caracteres de controle, como tabulações e caracteres de nova linha, da saída.</span><span class="sxs-lookup"><span data-stu-id="e029d-302">Removes all control characters, such as tabs and new line characters from the output.</span></span> <span data-ttu-id="e029d-303">Isso preserva a formatação de coluna quando os dados são retornados.</span><span class="sxs-lookup"><span data-stu-id="e029d-303">This preserves column formatting when data is returned.</span></span> <span data-ttu-id="e029d-304">Se for especificado 1, os caracteres de controle serão substituídos por um único espaço.</span><span class="sxs-lookup"><span data-stu-id="e029d-304">If 1 is specified, the control characters are replaced by a single space.</span></span> <span data-ttu-id="e029d-305">Se for especificado 2, os caracteres de controle consecutivos serão substituídos por um único espaço.</span><span class="sxs-lookup"><span data-stu-id="e029d-305">If 2 is specified, consecutive control characters are replaced by a single space.</span></span> <span data-ttu-id="e029d-306">**-k** é igual a **-k1**.</span><span class="sxs-lookup"><span data-stu-id="e029d-306">**-k** is the same as **-k1**.</span></span>  
  
 <span data-ttu-id="e029d-307">**-s** _col_separator_</span><span class="sxs-lookup"><span data-stu-id="e029d-307">**-s** _col_separator_</span></span>  
 <span data-ttu-id="e029d-308">Especifica o caractere do separador de coluna.</span><span class="sxs-lookup"><span data-stu-id="e029d-308">Specifies the column-separator character.</span></span> <span data-ttu-id="e029d-309">O padrão é um espaço em branco.</span><span class="sxs-lookup"><span data-stu-id="e029d-309">The default is a blank space.</span></span> <span data-ttu-id="e029d-310">Essa opção define a variável de script SQLCMDCOLSEP do `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="e029d-310">This option sets the `sqlcmd` scripting variable SQLCMDCOLSEP.</span></span> <span data-ttu-id="e029d-311">Para usar caracteres com um significado especial para o sistema operacional como, por exemplo, E comercial (&) ou ponto e vírgula (;), use-os entre aspas (").</span><span class="sxs-lookup"><span data-stu-id="e029d-311">To use characters that have special meaning to the operating system such as the ampersand (&), or semicolon (;), enclose the character in quotation marks (").</span></span> <span data-ttu-id="e029d-312">O separador de coluna pode ser qualquer caractere de 8 bits.</span><span class="sxs-lookup"><span data-stu-id="e029d-312">The column separator can be any 8-bit character.</span></span>  
  
 <span data-ttu-id="e029d-313">**-w** _column_width_</span><span class="sxs-lookup"><span data-stu-id="e029d-313">**-w** _column_width_</span></span>  
 <span data-ttu-id="e029d-314">Especifica a largura de tela para saída.</span><span class="sxs-lookup"><span data-stu-id="e029d-314">Specifies the screen width for output.</span></span> <span data-ttu-id="e029d-315">Essa opção define a variável de script SQLCMDCOLWIDTH do `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="e029d-315">This option sets the `sqlcmd` scripting variable SQLCMDCOLWIDTH.</span></span> <span data-ttu-id="e029d-316">A largura da coluna deve ser um número maior que 8 e menor que 65536.</span><span class="sxs-lookup"><span data-stu-id="e029d-316">The column width must be a number greater than 8 and less than 65536.</span></span> <span data-ttu-id="e029d-317">Se a largura da coluna especificada não estiver nesse intervalo, o `sqlcmd` irá gerar uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="e029d-317">If the specified column width does not fall into that range, `sqlcmd` generates and error message.</span></span> <span data-ttu-id="e029d-318">A largura padrão é 80 caracteres.</span><span class="sxs-lookup"><span data-stu-id="e029d-318">The default width is 80 characters.</span></span> <span data-ttu-id="e029d-319">Quando uma linha de saída excede a largura de coluna especificada, ela inclui a próxima linha.</span><span class="sxs-lookup"><span data-stu-id="e029d-319">When an output line exceeds the specified column width, it wraps on to the next line.</span></span>  
  
 <span data-ttu-id="e029d-320">**-W**</span><span class="sxs-lookup"><span data-stu-id="e029d-320">**-W**</span></span>  
 <span data-ttu-id="e029d-321">Essa opção remove espaços à direita de uma coluna.</span><span class="sxs-lookup"><span data-stu-id="e029d-321">This option removes trailing spaces from a column.</span></span> <span data-ttu-id="e029d-322">Use esta opção com a opção **-s** ao preparar dados a serem exportados para outro aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e029d-322">Use this option together with the **-s** option when preparing data that is to be exported to another application.</span></span> <span data-ttu-id="e029d-323">Ela não pode ser usada com as opções **-y** ou **-Y** .</span><span class="sxs-lookup"><span data-stu-id="e029d-323">Cannot be used with the **-y** or **-Y** options.</span></span>  
  
 <span data-ttu-id="e029d-324">**-y** _variable_length_type_display_width_</span><span class="sxs-lookup"><span data-stu-id="e029d-324">**-y** _variable_length_type_display_width_</span></span>  
 <span data-ttu-id="e029d-325">Define a variável de script SQLCMDMAXVARTYPEWIDTH do `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="e029d-325">Sets the `sqlcmd` scripting variable SQLCMDMAXVARTYPEWIDTH.</span></span> <span data-ttu-id="e029d-326">O padrão é 256.</span><span class="sxs-lookup"><span data-stu-id="e029d-326">The default is 256.</span></span> <span data-ttu-id="e029d-327">Ele limita o número de caracteres retornados para os tipos de dados com comprimento variável grande:</span><span class="sxs-lookup"><span data-stu-id="e029d-327">It limits the number of characters that are returned for the large variable length data types:</span></span>  
  
-   `varchar(max)`  
  
-   `nvarchar(max)`  
  
-   `varbinary(max)`  
  
-   `xml`  
  
-   `UDT (user-defined data types)`  
  
-   `text`  
  
-   `ntext`  
  
-   `image`  
  
> [!NOTE]  
>  <span data-ttu-id="e029d-328">UDTs podem ter comprimento fixo dependendo da implementação.</span><span class="sxs-lookup"><span data-stu-id="e029d-328">UDTs can be of fixed length depending on the implementation.</span></span> <span data-ttu-id="e029d-329">Se esse tamanho de UDT de tamanho fixo for mais curto que *display_width*, o valor do UDT retornado não será afetado.</span><span class="sxs-lookup"><span data-stu-id="e029d-329">If this length of a fixed length UDT is shorter that *display_width*, the value of the UDT returned is not affected.</span></span> <span data-ttu-id="e029d-330">Porém, se o tamanho for mais longo que *display_width*, a saída será truncada.</span><span class="sxs-lookup"><span data-stu-id="e029d-330">However, if the length is longer than *display_width*, the output is truncated.</span></span>  
  
 
> [!IMPORTANT]  
>  <span data-ttu-id="e029d-331">Use a opção **-y 0** com muito cuidado, porque isso poderá causar graves problemas de desempenho tanto no servidor quanto na rede, dependendo do tamanho dos dados retornados.</span><span class="sxs-lookup"><span data-stu-id="e029d-331">Use the **-y 0** option with extreme caution because it may cause serious performance issues on both the server and the network, depending on the size of data returned.</span></span>  
  
 <span data-ttu-id="e029d-332">**-Y** _fixed_length_type_display_width_</span><span class="sxs-lookup"><span data-stu-id="e029d-332">**-Y** _fixed_length_type_display_width_</span></span>  
 <span data-ttu-id="e029d-333">Define a variável de script SQLCMDMAXFIXEDTYPEWIDTH do `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="e029d-333">Sets the `sqlcmd` scripting variable SQLCMDMAXFIXEDTYPEWIDTH.</span></span> <span data-ttu-id="e029d-334">O padrão é 0 (ilimitado).</span><span class="sxs-lookup"><span data-stu-id="e029d-334">The default is 0 (unlimited).</span></span> <span data-ttu-id="e029d-335">Limita o número de caracteres retornado para os tipos de dados a seguir:</span><span class="sxs-lookup"><span data-stu-id="e029d-335">Limits the number of characters that are returned for the following data types:</span></span>  
  
-   <span data-ttu-id="e029d-336">`char(`*n* `)` , em que 1<= n<= 8000</span><span class="sxs-lookup"><span data-stu-id="e029d-336">`char(` *n* `)`, where 1<=n<=8000</span></span>  
  
-   <span data-ttu-id="e029d-337">`nchar(n`*n* `)` , em que 1<= n<= 4000</span><span class="sxs-lookup"><span data-stu-id="e029d-337">`nchar(n` *n* `)`, where 1<=n<=4000</span></span>  
  
-   <span data-ttu-id="e029d-338">`varchar(n`*n* `)` , em que 1<= n<= 8000</span><span class="sxs-lookup"><span data-stu-id="e029d-338">`varchar(n` *n* `)`, where 1<=n<=8000</span></span>  
  
-   <span data-ttu-id="e029d-339">`nvarchar(n`*n* `)` , em que 1<= n<= 4000</span><span class="sxs-lookup"><span data-stu-id="e029d-339">`nvarchar(n` *n* `)`, where 1<=n<=4000</span></span>  
  
-   <span data-ttu-id="e029d-340">`varbinary(n`*n* `)` , em que 1<= n<= 4000</span><span class="sxs-lookup"><span data-stu-id="e029d-340">`varbinary(n` *n* `)`, where 1<=n<=4000</span></span>  
  
-   `variant`  
  
 <span data-ttu-id="e029d-341">**Opções de relatório de erros**</span><span class="sxs-lookup"><span data-stu-id="e029d-341">**Error Reporting Options**</span></span>  
  `-b`  
 <span data-ttu-id="e029d-342">Especifica que o `sqlcmd` é encerrado e retorna um valor DOS ERRORLEVEL em caso de erro.</span><span class="sxs-lookup"><span data-stu-id="e029d-342">Specifies that `sqlcmd` exits and returns a DOS ERRORLEVEL value when an error occurs.</span></span> <span data-ttu-id="e029d-343">O valor que é retornado à variável DOS ERRORLEVEL é **1** quando a mensagem de erro [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tiver um nível de severidade maior do que 10; caso contrário, o valor retornado é **0**.</span><span class="sxs-lookup"><span data-stu-id="e029d-343">The value that is returned to the DOS ERRORLEVEL variable is **1** when the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] error message has a severity level greater than 10; otherwise, the value returned is **0**.</span></span> <span data-ttu-id="e029d-344">Se a opção `-V` tiver sido definida além de `-b`, o `sqlcmd` não relatará um erro se o nível de severidade for inferior aos valores definidos usando `-V`.</span><span class="sxs-lookup"><span data-stu-id="e029d-344">If the `-V` option has been set in addition to `-b`, `sqlcmd` will not report an error if the severity level is lower than the values set using `-V`.</span></span> <span data-ttu-id="e029d-345">Arquivos em lote do prompt de comando podem testar o valor de ERRORLEVEL e tratar o erro adequadamente.</span><span class="sxs-lookup"><span data-stu-id="e029d-345">Command prompt batch files can test the value of ERRORLEVEL and handle the error appropriately.</span></span> <span data-ttu-id="e029d-346">`sqlcmd` não relata erros para nível de severidade 10 (mensagens informativas).</span><span class="sxs-lookup"><span data-stu-id="e029d-346">`sqlcmd` does not report errors for severity level 10 (informational messages).</span></span>  
  
 <span data-ttu-id="e029d-347">Se o script `sqlcmd` tiver um comentário incorreto, erro de sintaxe, ou se estiver faltando uma variável de script, ERRORLEVEL retorna 1.</span><span class="sxs-lookup"><span data-stu-id="e029d-347">If the `sqlcmd` script contains an incorrect comment, syntax error, or is missing a scripting variable, ERRORLEVEL returned is 1.</span></span>  
  
 <span data-ttu-id="e029d-348">**-m** _error_level_</span><span class="sxs-lookup"><span data-stu-id="e029d-348">**-m** _error_level_</span></span>  
 <span data-ttu-id="e029d-349">Controla quais mensagens de erro são enviadas para **stdout**.</span><span class="sxs-lookup"><span data-stu-id="e029d-349">Controls which error messages are sent to **stdout**.</span></span> <span data-ttu-id="e029d-350">Mensagens com um nível de severidade maior ou igual a esse nível são enviadas.</span><span class="sxs-lookup"><span data-stu-id="e029d-350">Messages that have a severity level greater than or equal to this level are sent.</span></span> <span data-ttu-id="e029d-351">Quando esse valor for definido como **-1**, todas as mensagens, incluindo mensagens informativas, serão enviadas.</span><span class="sxs-lookup"><span data-stu-id="e029d-351">When this value is set to **-1**, all messages including informational messages, are sent.</span></span> <span data-ttu-id="e029d-352">Não são permitidos espaços entre **-m** e **-1**.</span><span class="sxs-lookup"><span data-stu-id="e029d-352">Spaces are not allowed between the **-m** and **-1**.</span></span> <span data-ttu-id="e029d-353">Por exemplo, **-m-1** é válido, e **-m-1** não.</span><span class="sxs-lookup"><span data-stu-id="e029d-353">For example, **-m-1** is valid, and **-m-1** is not.</span></span>  
  
 <span data-ttu-id="e029d-354">Essa opção também define a variável de script SQLCMDERRORLEVEL do `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="e029d-354">This option also sets the `sqlcmd` scripting variable SQLCMDERRORLEVEL.</span></span> <span data-ttu-id="e029d-355">Essa variável tem um padrão de 0.</span><span class="sxs-lookup"><span data-stu-id="e029d-355">This variable has a default of 0.</span></span>  
  
 <span data-ttu-id="e029d-356">`-V`*error_severity_level*</span><span class="sxs-lookup"><span data-stu-id="e029d-356">`-V` *error_severity_level*</span></span>  
 <span data-ttu-id="e029d-357">Controla o nível de severidade usado para definir a variável ERRORLEVEL.</span><span class="sxs-lookup"><span data-stu-id="e029d-357">Controls the severity level that is used to set the ERRORLEVEL variable.</span></span> <span data-ttu-id="e029d-358">Mensagens de erro com níveis de severidade maiores ou iguais a esse valor definem ERRORLEVEL.</span><span class="sxs-lookup"><span data-stu-id="e029d-358">Error messages that have severity levels greater than or equal to this value set ERRORLEVEL.</span></span> <span data-ttu-id="e029d-359">Valores menores que 0 são reportados como 0.</span><span class="sxs-lookup"><span data-stu-id="e029d-359">Values that are less than 0 are reported as 0.</span></span> <span data-ttu-id="e029d-360">Podem ser usados arquivos de lote e CMD para testar o valor da variável ERRORLEVEL.</span><span class="sxs-lookup"><span data-stu-id="e029d-360">Batch and CMD files can be used to test the value of the ERRORLEVEL variable.</span></span>  
  
 <span data-ttu-id="e029d-361">**Opções diversas**</span><span class="sxs-lookup"><span data-stu-id="e029d-361">**Miscellaneous Options**</span></span>  
  <span data-ttu-id="e029d-362">**-a** _packet_size_</span><span class="sxs-lookup"><span data-stu-id="e029d-362">**-a** _packet_size_</span></span>  
 <span data-ttu-id="e029d-363">Exige um pacote de tamanho diferente.</span><span class="sxs-lookup"><span data-stu-id="e029d-363">Requests a packet of a different size.</span></span> <span data-ttu-id="e029d-364">Essa opção define a variável de script SQLCMDPACKETSIZE do `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="e029d-364">This option sets the `sqlcmd` scripting variable SQLCMDPACKETSIZE.</span></span> <span data-ttu-id="e029d-365">*packet_size* deve ser um valor entre 512 e 32767.</span><span class="sxs-lookup"><span data-stu-id="e029d-365">*packet_size* must be a value between 512 and 32767.</span></span> <span data-ttu-id="e029d-366">O padrão é igual a 4096.</span><span class="sxs-lookup"><span data-stu-id="e029d-366">The default = 4096.</span></span> <span data-ttu-id="e029d-367">Um tamanho de pacote maior pode melhorar o desempenho da execução de scripts que tenham muitas instruções SQL entre comandos GO.</span><span class="sxs-lookup"><span data-stu-id="e029d-367">A larger packet size can enhance performance for execution of scripts that have lots of SQL statements between GO commands.</span></span> <span data-ttu-id="e029d-368">Pode-se solicitar um tamanho de pacote maior.</span><span class="sxs-lookup"><span data-stu-id="e029d-368">You can request a larger packet size.</span></span> <span data-ttu-id="e029d-369">Porém, se a solicitação for negada, o `sqlcmd` usará o padrão de servidor para tamanho de pacote.</span><span class="sxs-lookup"><span data-stu-id="e029d-369">However, if the request is denied, `sqlcmd` uses the server default for packet size.</span></span>  
  
 <span data-ttu-id="e029d-370">**-c** _batch_terminator_</span><span class="sxs-lookup"><span data-stu-id="e029d-370">**-c** _batch_terminator_</span></span>  
 <span data-ttu-id="e029d-371">Especifica o terminador de lote.</span><span class="sxs-lookup"><span data-stu-id="e029d-371">Specifies the batch terminator.</span></span> <span data-ttu-id="e029d-372">Por padrão, comandos são finalizados e enviados para o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] digitando-se apenas a palavra "GO" em uma linha.</span><span class="sxs-lookup"><span data-stu-id="e029d-372">By default, commands are terminated and sent to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] by typing the word "GO" on a line by itself.</span></span> <span data-ttu-id="e029d-373">Ao redefinir o terminador de lote, não use palavras-chave reservadas do [!INCLUDE[tsql](../includes/tsql-md.md)] ou caracteres que tenham um significado especial para o sistema operacional, mesmo que sejam precedidas por uma barra invertida.</span><span class="sxs-lookup"><span data-stu-id="e029d-373">When you reset the batch terminator, do not use [!INCLUDE[tsql](../includes/tsql-md.md)] reserved keywords or characters that have special meaning to the operating system, even if they are preceded by a backslash.</span></span>  
  
 <span data-ttu-id="e029d-374">**-L**[**c**]</span><span class="sxs-lookup"><span data-stu-id="e029d-374">**-L**[**c**]</span></span>  
 <span data-ttu-id="e029d-375">Lista os computadores servidor localmente configurados e os nomes dos computadores servidor que estão transmitindo na rede.</span><span class="sxs-lookup"><span data-stu-id="e029d-375">Lists the locally configured server computers, and the names of the server computers that are broadcasting on the network.</span></span> <span data-ttu-id="e029d-376">Esse parâmetro não pode ser usado em combinação com outros parâmetros.</span><span class="sxs-lookup"><span data-stu-id="e029d-376">This parameter cannot be used in combination with other parameters.</span></span> <span data-ttu-id="e029d-377">O número máximo de computadores servidores que pode ser listado é 3000.</span><span class="sxs-lookup"><span data-stu-id="e029d-377">The maximum number of server computers that can be listed is 3000.</span></span> <span data-ttu-id="e029d-378">Se a lista de servidores ficar truncada devido ao tamanho do buffer, será exibida uma mensagem de aviso.</span><span class="sxs-lookup"><span data-stu-id="e029d-378">If the server list is truncated because of the size of the buffer a warning message is displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e029d-379">Devido à natureza da difusão em redes, `sqlcmd` o pode não receber uma resposta oportuna de todos os servidores.</span><span class="sxs-lookup"><span data-stu-id="e029d-379">Because of the nature of broadcasting on networks, `sqlcmd` may not receive a timely response from all servers.</span></span> <span data-ttu-id="e029d-380">Assim, a lista de servidores retornada pode variar para cada invocação dessa opção.</span><span class="sxs-lookup"><span data-stu-id="e029d-380">Therefore, the list of servers returned may vary for each invocation of this option.</span></span>  
  
 <span data-ttu-id="e029d-381">Se o parâmetro opcional **c** for especificado, a saída aparecerá sem os servidores: linha de cabeçalho e cada linha de servidor será listada sem espaços à esquerda.</span><span class="sxs-lookup"><span data-stu-id="e029d-381">If the optional parameter **c** is specified, the output appears without the Servers: header line and each server line is listed without leading spaces.</span></span> <span data-ttu-id="e029d-382">Isso é chamado de saída normal.</span><span class="sxs-lookup"><span data-stu-id="e029d-382">This is referred to as clean output.</span></span> <span data-ttu-id="e029d-383">A saída normal melhora o desempenho de processamento das linguagens dos scripts.</span><span class="sxs-lookup"><span data-stu-id="e029d-383">Clean output improves the processing performance of scripting languages.</span></span>  
  
 <span data-ttu-id="e029d-384">**-p**[**1**]</span><span class="sxs-lookup"><span data-stu-id="e029d-384">**-p**[**1**]</span></span>  
 <span data-ttu-id="e029d-385">Imprime estatísticas de desempenho para cada conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="e029d-385">Prints performance statistics for every result set.</span></span> <span data-ttu-id="e029d-386">O exemplo a seguir mostra o formato para estatísticas de desempenho:</span><span class="sxs-lookup"><span data-stu-id="e029d-386">The following is an example of the format for performance statistics:</span></span>  
  
 `Network packet size (bytes): n`  
  
 `x xact[s]:`  
  
 `Clock Time (ms.): total       t1  avg       t2 (t3 xacts per sec.)`  
  
 <span data-ttu-id="e029d-387">Em que:</span><span class="sxs-lookup"><span data-stu-id="e029d-387">Where:</span></span>  
  
 <span data-ttu-id="e029d-388">`x` = Número de transações processadas pelo [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e029d-388">`x` = Number of transactions that are processed by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="e029d-389">`t1` = Tempo total para todas as transações.</span><span class="sxs-lookup"><span data-stu-id="e029d-389">`t1` = Total time for all transactions.</span></span>  
  
 <span data-ttu-id="e029d-390">`t2` = Tempo médio de uma única transação.</span><span class="sxs-lookup"><span data-stu-id="e029d-390">`t2` = Average time for a single transaction.</span></span>  
  
 <span data-ttu-id="e029d-391">`t3` = Número médio de transações por segundo.</span><span class="sxs-lookup"><span data-stu-id="e029d-391">`t3` = Average number of transactions per second.</span></span>  
  
 <span data-ttu-id="e029d-392">Todos os tempos estão em milissegundos.</span><span class="sxs-lookup"><span data-stu-id="e029d-392">All times are in milliseconds.</span></span>  
  
 <span data-ttu-id="e029d-393">Se o parâmetro opcional **1** for especificado, o formato de saída das estatísticas estará em formato separado por dois pontos, que poderá ser facilmente importado para uma planilha ou processado por um script.</span><span class="sxs-lookup"><span data-stu-id="e029d-393">If the optional parameter **1** is specified, the output format of the statistics is in colon-separated format that can be imported easily into a spreadsheet or processed by a script.</span></span>  
  
 <span data-ttu-id="e029d-394">Se o parâmetro opcional for qualquer valor diferente de **1**, um erro será gerado e será `sqlcmd` encerrado.</span><span class="sxs-lookup"><span data-stu-id="e029d-394">If the optional parameter is any value other than **1**, an error is generated and `sqlcmd` exits.</span></span>  
  
 <span data-ttu-id="e029d-395">`-X`[**1**]</span><span class="sxs-lookup"><span data-stu-id="e029d-395">`-X`[**1**]</span></span>  
 <span data-ttu-id="e029d-396">Desabilita comandos que podem comprometer a segurança do sistema quando o `sqlcmd` é executado a partir de um arquivo em lote.</span><span class="sxs-lookup"><span data-stu-id="e029d-396">Disables commands that might compromise system security when `sqlcmd` is executed from a batch file.</span></span> <span data-ttu-id="e029d-397">Os comandos desabilitados ainda são reconhecidos; o `sqlcmd` emite uma mensagem de aviso e continua.</span><span class="sxs-lookup"><span data-stu-id="e029d-397">The disabled commands are still recognized; `sqlcmd` issues a warning message and continues.</span></span> <span data-ttu-id="e029d-398">Se o parâmetro opcional **1** for especificado, o `sqlcmd` gerará uma mensagem de erro e será encerrado.</span><span class="sxs-lookup"><span data-stu-id="e029d-398">If the optional parameter **1** is specified, `sqlcmd` generates an error message and then exits.</span></span> <span data-ttu-id="e029d-399">Os comandos a seguir são desabilitados quando for usada a opção `-X`:</span><span class="sxs-lookup"><span data-stu-id="e029d-399">The following commands are disabled when the `-X` option is used:</span></span>  
  
-   <span data-ttu-id="e029d-400">**ED**</span><span class="sxs-lookup"><span data-stu-id="e029d-400">**ED**</span></span>  
  
-   <span data-ttu-id="e029d-401">**!!**</span><span class="sxs-lookup"><span data-stu-id="e029d-401">**!!**</span></span> <span data-ttu-id="e029d-402">_command_</span><span class="sxs-lookup"><span data-stu-id="e029d-402">_command_</span></span>  
  
 <span data-ttu-id="e029d-403">Se for especificada a opção `-X`, isso evita que variáveis de ambiente sejam transmitidas para o `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="e029d-403">If the `-X` option is specified, it prevents environment variables from being passed on to `sqlcmd`.</span></span> <span data-ttu-id="e029d-404">Evita também que o script de inicialização especificado, usando a variável de script SQLCMDINI, seja executado.</span><span class="sxs-lookup"><span data-stu-id="e029d-404">It also prevents the startup script specified by using the SQLCMDINI scripting variable from being executed.</span></span> <span data-ttu-id="e029d-405">Para obter mais informações sobre `sqlcmd` variáveis de script, consulte [usar sqlcmd com variáveis de script](../relational-databases/scripting/sqlcmd-use-with-scripting-variables.md).</span><span class="sxs-lookup"><span data-stu-id="e029d-405">For more information about `sqlcmd` scripting variables, see [Use sqlcmd with Scripting Variables](../relational-databases/scripting/sqlcmd-use-with-scripting-variables.md).</span></span>  
  
 <span data-ttu-id="e029d-406">**-?**</span><span class="sxs-lookup"><span data-stu-id="e029d-406">**-?**</span></span>  
 <span data-ttu-id="e029d-407">Exibe o resumo de sintaxe de opções do `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="e029d-407">Displays the syntax summary of `sqlcmd` options.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e029d-408">Comentários</span><span class="sxs-lookup"><span data-stu-id="e029d-408">Remarks</span></span>  
 <span data-ttu-id="e029d-409">As opções não precisam ser usadas na ordem mostrada na seção de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="e029d-409">Options do not have to be used in the order shown in the syntax section.</span></span>  
  
 <span data-ttu-id="e029d-410">Quando são retornados vários resultados, o `sqlcmd` imprime uma linha em branco entre cada conjunto de resultados em um lote.</span><span class="sxs-lookup"><span data-stu-id="e029d-410">When multiple results are returned, `sqlcmd` prints a blank line between each result set in a batch.</span></span> <span data-ttu-id="e029d-411">Além disso, a \<x> mensagem "linhas afetadas" não aparece quando não se aplica à instrução executada.</span><span class="sxs-lookup"><span data-stu-id="e029d-411">In addition, the "\<x> rows affected" message does not appear when it does not apply to the statement executed.</span></span>  
  
 <span data-ttu-id="e029d-412">Para usar `sqlcmd` interativamente, digite `sqlcmd` no prompt de comando com uma ou mais das opções descritas anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="e029d-412">To use `sqlcmd` interactively, type `sqlcmd` at the command prompt with any one or more of the options described earlier in this topic.</span></span> <span data-ttu-id="e029d-413">Para obter mais informações, consulte [Usar o Utilitário sqlcmd](../relational-databases/scripting/sqlcmd-use-the-utility.md)</span><span class="sxs-lookup"><span data-stu-id="e029d-413">For more information, see [Use the sqlcmd Utility](../relational-databases/scripting/sqlcmd-use-the-utility.md)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e029d-414">As opções **-L**, **-Q**, **-Z** ou **-i** fazem `sqlcmd` a saída após a execução.</span><span class="sxs-lookup"><span data-stu-id="e029d-414">The options **-L**, **-Q**, **-Z** or **-i** cause `sqlcmd` to exit after execution.</span></span>  
  
 <span data-ttu-id="e029d-415">O comprimento total da linha de comando `sqlcmd` no ambiente de comando (Cmd.exe), incluindo todos os argumentos e variáveis expandidas, é aquele determinado pelo sistema operacional para Cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="e029d-415">The total length of the `sqlcmd` command line in the command environment (Cmd.exe), including all arguments and expanded variables, is that which is determined by the operating system for Cmd.exe.</span></span>  
  
## <a name="variable-precedence-low-to-high"></a><span data-ttu-id="e029d-416">Precedência de variável (baixa para alta)</span><span class="sxs-lookup"><span data-stu-id="e029d-416">Variable Precedence (Low to High)</span></span>  
  
1.  <span data-ttu-id="e029d-417">Variáveis ambientais do nível de sistema.</span><span class="sxs-lookup"><span data-stu-id="e029d-417">System-level environmental variables.</span></span>  
  
2.  <span data-ttu-id="e029d-418">Variáveis ambientais do nível de usuário.</span><span class="sxs-lookup"><span data-stu-id="e029d-418">User-level environmental variables</span></span>  
  
3.  <span data-ttu-id="e029d-419">Shell de comando (**set** X = Y) definido no prompt de comando antes da execução `sqlcmd` .</span><span class="sxs-lookup"><span data-stu-id="e029d-419">Command shell (**SET** X=Y) set at command prompt before running `sqlcmd`.</span></span>  
  
4.  <span data-ttu-id="e029d-420">**sqlcmd-v** X=Y</span><span class="sxs-lookup"><span data-stu-id="e029d-420">**sqlcmd-v** X=Y</span></span>  
  
5.  <span data-ttu-id="e029d-421">**:Setvar** X Y</span><span class="sxs-lookup"><span data-stu-id="e029d-421">**:Setvar** X Y</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e029d-422">Para exibir as variáveis ambientais, no **Painel de Controle**, abra **Sistema**e clique na guia **Avançado** .</span><span class="sxs-lookup"><span data-stu-id="e029d-422">To view the environmental variables, in **Control Panel**, open **System**, and then click the **Advanced** tab.</span></span>  
  
## <a name="sqlcmd-scripting-variables"></a><span data-ttu-id="e029d-423">Variáveis de script do sqlcmd</span><span class="sxs-lookup"><span data-stu-id="e029d-423">sqlcmd Scripting Variables</span></span>  
  
|<span data-ttu-id="e029d-424">Variável</span><span class="sxs-lookup"><span data-stu-id="e029d-424">Variable</span></span>|<span data-ttu-id="e029d-425">Opção relacionada</span><span class="sxs-lookup"><span data-stu-id="e029d-425">Related switch</span></span>|<span data-ttu-id="e029d-426">R/W</span><span class="sxs-lookup"><span data-stu-id="e029d-426">R/W</span></span>|<span data-ttu-id="e029d-427">Padrão</span><span class="sxs-lookup"><span data-stu-id="e029d-427">Default</span></span>|  
|--------------|--------------------|----------|-------------|  
|<span data-ttu-id="e029d-428">SQLCMDUSER</span><span class="sxs-lookup"><span data-stu-id="e029d-428">SQLCMDUSER</span></span>|<span data-ttu-id="e029d-429">-U</span><span class="sxs-lookup"><span data-stu-id="e029d-429">-U</span></span>|<span data-ttu-id="e029d-430">R</span><span class="sxs-lookup"><span data-stu-id="e029d-430">R</span></span>|<span data-ttu-id="e029d-431">""</span><span class="sxs-lookup"><span data-stu-id="e029d-431">""</span></span>|  
|<span data-ttu-id="e029d-432">SQLCMDPASSWORD</span><span class="sxs-lookup"><span data-stu-id="e029d-432">SQLCMDPASSWORD</span></span>|<span data-ttu-id="e029d-433">-P</span><span class="sxs-lookup"><span data-stu-id="e029d-433">-P</span></span>|--|<span data-ttu-id="e029d-434">""</span><span class="sxs-lookup"><span data-stu-id="e029d-434">""</span></span>|  
|<span data-ttu-id="e029d-435">SQLCMDSERVER</span><span class="sxs-lookup"><span data-stu-id="e029d-435">SQLCMDSERVER</span></span>|<span data-ttu-id="e029d-436">-S</span><span class="sxs-lookup"><span data-stu-id="e029d-436">-S</span></span>|<span data-ttu-id="e029d-437">R</span><span class="sxs-lookup"><span data-stu-id="e029d-437">R</span></span>|<span data-ttu-id="e029d-438">"DefaultLocalInstance"</span><span class="sxs-lookup"><span data-stu-id="e029d-438">"DefaultLocalInstance"</span></span>|  
|<span data-ttu-id="e029d-439">SQLCMDWORKSTATION</span><span class="sxs-lookup"><span data-stu-id="e029d-439">SQLCMDWORKSTATION</span></span>|<span data-ttu-id="e029d-440">-H</span><span class="sxs-lookup"><span data-stu-id="e029d-440">-H</span></span>|<span data-ttu-id="e029d-441">R</span><span class="sxs-lookup"><span data-stu-id="e029d-441">R</span></span>|<span data-ttu-id="e029d-442">"ComputerName"</span><span class="sxs-lookup"><span data-stu-id="e029d-442">"ComputerName"</span></span>|  
|<span data-ttu-id="e029d-443">SQLCMDDBNAME</span><span class="sxs-lookup"><span data-stu-id="e029d-443">SQLCMDDBNAME</span></span>|<span data-ttu-id="e029d-444">-d</span><span class="sxs-lookup"><span data-stu-id="e029d-444">-d</span></span>|<span data-ttu-id="e029d-445">R</span><span class="sxs-lookup"><span data-stu-id="e029d-445">R</span></span>|<span data-ttu-id="e029d-446">""</span><span class="sxs-lookup"><span data-stu-id="e029d-446">""</span></span>|  
|<span data-ttu-id="e029d-447">SQLCMDLOGINTIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e029d-447">SQLCMDLOGINTIMEOUT</span></span>|<span data-ttu-id="e029d-448">-l</span><span class="sxs-lookup"><span data-stu-id="e029d-448">-l</span></span>|<span data-ttu-id="e029d-449">R/W</span><span class="sxs-lookup"><span data-stu-id="e029d-449">R/W</span></span>|<span data-ttu-id="e029d-450">"8" (segundos)</span><span class="sxs-lookup"><span data-stu-id="e029d-450">"8" (seconds)</span></span>|  
|<span data-ttu-id="e029d-451">SQLCMDSTATTIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e029d-451">SQLCMDSTATTIMEOUT</span></span>|<span data-ttu-id="e029d-452">-T</span><span class="sxs-lookup"><span data-stu-id="e029d-452">-t</span></span>|<span data-ttu-id="e029d-453">R/W</span><span class="sxs-lookup"><span data-stu-id="e029d-453">R/W</span></span>|<span data-ttu-id="e029d-454">"0" = espere indefinidamente</span><span class="sxs-lookup"><span data-stu-id="e029d-454">"0" = wait indefinitely</span></span>|  
|<span data-ttu-id="e029d-455">SQLCMDHEADERS</span><span class="sxs-lookup"><span data-stu-id="e029d-455">SQLCMDHEADERS</span></span>|<span data-ttu-id="e029d-456">-H</span><span class="sxs-lookup"><span data-stu-id="e029d-456">-h</span></span>|<span data-ttu-id="e029d-457">R/W</span><span class="sxs-lookup"><span data-stu-id="e029d-457">R/W</span></span>|<span data-ttu-id="e029d-458">"0"</span><span class="sxs-lookup"><span data-stu-id="e029d-458">"0"</span></span>|  
|<span data-ttu-id="e029d-459">SQLCMDCOLSEP</span><span class="sxs-lookup"><span data-stu-id="e029d-459">SQLCMDCOLSEP</span></span>|<span data-ttu-id="e029d-460">-S</span><span class="sxs-lookup"><span data-stu-id="e029d-460">-s</span></span>|<span data-ttu-id="e029d-461">R/W</span><span class="sxs-lookup"><span data-stu-id="e029d-461">R/W</span></span>|<span data-ttu-id="e029d-462">" "</span><span class="sxs-lookup"><span data-stu-id="e029d-462">" "</span></span>|  
|<span data-ttu-id="e029d-463">SQLCMDCOLWIDTH</span><span class="sxs-lookup"><span data-stu-id="e029d-463">SQLCMDCOLWIDTH</span></span>|<span data-ttu-id="e029d-464">-w</span><span class="sxs-lookup"><span data-stu-id="e029d-464">-w</span></span>|<span data-ttu-id="e029d-465">R/W</span><span class="sxs-lookup"><span data-stu-id="e029d-465">R/W</span></span>|<span data-ttu-id="e029d-466">"0"</span><span class="sxs-lookup"><span data-stu-id="e029d-466">"0"</span></span>|  
|<span data-ttu-id="e029d-467">SQLCMDPACKETSIZE</span><span class="sxs-lookup"><span data-stu-id="e029d-467">SQLCMDPACKETSIZE</span></span>|<span data-ttu-id="e029d-468">-a</span><span class="sxs-lookup"><span data-stu-id="e029d-468">-a</span></span>|<span data-ttu-id="e029d-469">R</span><span class="sxs-lookup"><span data-stu-id="e029d-469">R</span></span>|<span data-ttu-id="e029d-470">"4096"</span><span class="sxs-lookup"><span data-stu-id="e029d-470">"4096"</span></span>|  
|<span data-ttu-id="e029d-471">SQLCMDERRORLEVEL</span><span class="sxs-lookup"><span data-stu-id="e029d-471">SQLCMDERRORLEVEL</span></span>|<span data-ttu-id="e029d-472">-M</span><span class="sxs-lookup"><span data-stu-id="e029d-472">-m</span></span>|<span data-ttu-id="e029d-473">R/W</span><span class="sxs-lookup"><span data-stu-id="e029d-473">R/W</span></span>|<span data-ttu-id="e029d-474">0</span><span class="sxs-lookup"><span data-stu-id="e029d-474">0</span></span>|  
|<span data-ttu-id="e029d-475">SQLCMDMAXVARTYPEWIDTH</span><span class="sxs-lookup"><span data-stu-id="e029d-475">SQLCMDMAXVARTYPEWIDTH</span></span>|<span data-ttu-id="e029d-476">-y</span><span class="sxs-lookup"><span data-stu-id="e029d-476">-y</span></span>|<span data-ttu-id="e029d-477">R/W</span><span class="sxs-lookup"><span data-stu-id="e029d-477">R/W</span></span>|<span data-ttu-id="e029d-478">"256"</span><span class="sxs-lookup"><span data-stu-id="e029d-478">"256"</span></span>|  
|<span data-ttu-id="e029d-479">SQLCMDMAXFIXEDTYPEWIDTH</span><span class="sxs-lookup"><span data-stu-id="e029d-479">SQLCMDMAXFIXEDTYPEWIDTH</span></span>|<span data-ttu-id="e029d-480">-y</span><span class="sxs-lookup"><span data-stu-id="e029d-480">-Y</span></span>|<span data-ttu-id="e029d-481">R/W</span><span class="sxs-lookup"><span data-stu-id="e029d-481">R/W</span></span>|<span data-ttu-id="e029d-482">"0" = ilimitado</span><span class="sxs-lookup"><span data-stu-id="e029d-482">"0" = unlimited</span></span>|  
|<span data-ttu-id="e029d-483">SQLCMDEDITOR</span><span class="sxs-lookup"><span data-stu-id="e029d-483">SQLCMDEDITOR</span></span>||<span data-ttu-id="e029d-484">R/W</span><span class="sxs-lookup"><span data-stu-id="e029d-484">R/W</span></span>|<span data-ttu-id="e029d-485">"edit.com"</span><span class="sxs-lookup"><span data-stu-id="e029d-485">"edit.com"</span></span>|  
|<span data-ttu-id="e029d-486">SQLCMDINI</span><span class="sxs-lookup"><span data-stu-id="e029d-486">SQLCMDINI</span></span>||<span data-ttu-id="e029d-487">R</span><span class="sxs-lookup"><span data-stu-id="e029d-487">R</span></span>|<span data-ttu-id="e029d-488">""</span><span class="sxs-lookup"><span data-stu-id="e029d-488">""</span></span>|  
  
 <span data-ttu-id="e029d-489">SQLCMDUSER, SQLCMDPASSWORD e SQLCMDSERVER são definidos quando **:Connect**</span><span class="sxs-lookup"><span data-stu-id="e029d-489">SQLCMDUSER, SQLCMDPASSWORD and SQLCMDSERVER are set when **:Connect**</span></span>  
  
 <span data-ttu-id="e029d-490">é usado.</span><span class="sxs-lookup"><span data-stu-id="e029d-490">is used.</span></span>  
  
 <span data-ttu-id="e029d-491">R indica que o valor pode ser definido apenas uma vez durante a inicialização do programa.</span><span class="sxs-lookup"><span data-stu-id="e029d-491">R indicates the value can only be set one time during program initialization.</span></span>  
  
 <span data-ttu-id="e029d-492">R/W indica que o valor pode ser modificado com o comando **setvar** e que os próximos comandos serão influenciados pelo novo valor.</span><span class="sxs-lookup"><span data-stu-id="e029d-492">R/W indicates that the value can be modified by using the **setvar** command and subsequent commands will be influenced by the new value.</span></span>  
  
## <a name="sqlcmd-commands"></a><span data-ttu-id="e029d-493">Comandos sqlcmd</span><span class="sxs-lookup"><span data-stu-id="e029d-493">sqlcmd Commands</span></span>  
 <span data-ttu-id="e029d-494">Além das instruções do [!INCLUDE[tsql](../includes/tsql-md.md)] no `sqlcmd`, também estão disponíveis os comandos a seguir:</span><span class="sxs-lookup"><span data-stu-id="e029d-494">In addition to [!INCLUDE[tsql](../includes/tsql-md.md)] statements within `sqlcmd`, the following commands are also available:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e029d-495">**GO** [*count*]</span><span class="sxs-lookup"><span data-stu-id="e029d-495">**GO** [*count*]</span></span>|<span data-ttu-id="e029d-496">**:List**</span><span class="sxs-lookup"><span data-stu-id="e029d-496">**:List**</span></span>|  
|<span data-ttu-id="e029d-497">[ **:** ] **RESET**</span><span class="sxs-lookup"><span data-stu-id="e029d-497">[**:**] **RESET**</span></span>|<span data-ttu-id="e029d-498">**:Error**</span><span class="sxs-lookup"><span data-stu-id="e029d-498">**:Error**</span></span>|  
|<span data-ttu-id="e029d-499">[ **:** ] **ED**</span><span class="sxs-lookup"><span data-stu-id="e029d-499">[**:**] **ED**</span></span>|<span data-ttu-id="e029d-500">**:Out**</span><span class="sxs-lookup"><span data-stu-id="e029d-500">**:Out**</span></span>|  
|<span data-ttu-id="e029d-501">[**:**] **!!**</span><span class="sxs-lookup"><span data-stu-id="e029d-501">[**:**] **!!**</span></span>|<span data-ttu-id="e029d-502">**:Perftrace**</span><span class="sxs-lookup"><span data-stu-id="e029d-502">**:Perftrace**</span></span>|  
|<span data-ttu-id="e029d-503">[ **:** ] **QUIT**</span><span class="sxs-lookup"><span data-stu-id="e029d-503">[**:**] **QUIT**</span></span>|<span data-ttu-id="e029d-504">**:Connect**</span><span class="sxs-lookup"><span data-stu-id="e029d-504">**:Connect**</span></span>|  
|<span data-ttu-id="e029d-505">[ **:** ] **EXIT**</span><span class="sxs-lookup"><span data-stu-id="e029d-505">[**:**] **EXIT**</span></span>|<span data-ttu-id="e029d-506">**:On Error**</span><span class="sxs-lookup"><span data-stu-id="e029d-506">**:On Error**</span></span>|  
|<span data-ttu-id="e029d-507">**:r**</span><span class="sxs-lookup"><span data-stu-id="e029d-507">**:r**</span></span>|<span data-ttu-id="e029d-508">**:Help**</span><span class="sxs-lookup"><span data-stu-id="e029d-508">**:Help**</span></span>|  
|<span data-ttu-id="e029d-509">**:ServerList**</span><span class="sxs-lookup"><span data-stu-id="e029d-509">**:ServerList**</span></span>|<span data-ttu-id="e029d-510">**:XML** [**ON** &#124; **OFF**]</span><span class="sxs-lookup"><span data-stu-id="e029d-510">**:XML** [**ON** &#124; **OFF**]</span></span>|  
|<span data-ttu-id="e029d-511">**:Setvar**</span><span class="sxs-lookup"><span data-stu-id="e029d-511">**:Setvar**</span></span>|<span data-ttu-id="e029d-512">**:Listvar**</span><span class="sxs-lookup"><span data-stu-id="e029d-512">**:Listvar**</span></span>|  
  
 <span data-ttu-id="e029d-513">Lembre-se do seguinte ao usar comandos do `sqlcmd`:</span><span class="sxs-lookup"><span data-stu-id="e029d-513">Be aware of the following when you use `sqlcmd` commands:</span></span>  
  
-   <span data-ttu-id="e029d-514">Todos os comandos do `sqlcmd`, exceto GO, devem ser antecedidos de dois pontos (:).</span><span class="sxs-lookup"><span data-stu-id="e029d-514">All `sqlcmd` commands, except GO, must be prefixed by a colon (:).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="e029d-515">Para manter a compatibilidade com versões anteriores de scripts **osql** existentes, alguns dos comandos serão reconhecidos sem os dois-pontos.</span><span class="sxs-lookup"><span data-stu-id="e029d-515">To maintain backward compatibility with existing **osql** scripts, some of the commands will be recognized without the colon.</span></span> <span data-ttu-id="e029d-516">Isso é indicado pelo [**:**].</span><span class="sxs-lookup"><span data-stu-id="e029d-516">This is indicated by the [**:**].</span></span>  
  
-   <span data-ttu-id="e029d-517">Os comandos do `sqlcmd` serão reconhecidos apenas se aparecerem no início de uma linha.</span><span class="sxs-lookup"><span data-stu-id="e029d-517">`sqlcmd` commands are recognized only if they appear at the start of a line.</span></span>  
  
-   <span data-ttu-id="e029d-518">Todos os comandos do `sqlcmd` não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e029d-518">All `sqlcmd` commands are case insensitive.</span></span>  
  
-   <span data-ttu-id="e029d-519">Cada comando deve estar em uma linha separada.</span><span class="sxs-lookup"><span data-stu-id="e029d-519">Each command must be on a separate line.</span></span> <span data-ttu-id="e029d-520">Um comando não pode ser seguido por uma instrução do [!INCLUDE[tsql](../includes/tsql-md.md)] ou por outro comando.</span><span class="sxs-lookup"><span data-stu-id="e029d-520">A command cannot be followed by a [!INCLUDE[tsql](../includes/tsql-md.md)] statement or another command.</span></span>  
  
-   <span data-ttu-id="e029d-521">Comandos são executados imediatamente.</span><span class="sxs-lookup"><span data-stu-id="e029d-521">Commands are executed immediately.</span></span> <span data-ttu-id="e029d-522">Eles não são colocados no buffer de execução como as instruções [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e029d-522">They are not put in the execution buffer as [!INCLUDE[tsql](../includes/tsql-md.md)] statements are.</span></span>  
  
 <span data-ttu-id="e029d-523">**Comandos de Edição**</span><span class="sxs-lookup"><span data-stu-id="e029d-523">**Editing Commands**</span></span>  
  <span data-ttu-id="e029d-524">[ **:** ] **ED**</span><span class="sxs-lookup"><span data-stu-id="e029d-524">[**:**] **ED**</span></span>  
 <span data-ttu-id="e029d-525">Inicie o editor de textos.</span><span class="sxs-lookup"><span data-stu-id="e029d-525">Starts the text editor.</span></span> <span data-ttu-id="e029d-526">Esse editor pode ser usado para editar o lote atual do [!INCLUDE[tsql](../includes/tsql-md.md)] ou o último lote executado.</span><span class="sxs-lookup"><span data-stu-id="e029d-526">This editor can be used to edit the current [!INCLUDE[tsql](../includes/tsql-md.md)] batch, or the last executed batch.</span></span> <span data-ttu-id="e029d-527">Para editar o último lote executado, o comando **ED** deve ser digitado imediatamente depois da execução do último lote.</span><span class="sxs-lookup"><span data-stu-id="e029d-527">To edit the last executed batch, the **ED** command must be typed immediately after the last batch has completed execution.</span></span>  
  
 <span data-ttu-id="e029d-528">O editor de textos é definido pela variável de ambiente SQLCMDEDITOR.</span><span class="sxs-lookup"><span data-stu-id="e029d-528">The text editor is defined by the SQLCMDEDITOR environment variable.</span></span> <span data-ttu-id="e029d-529">O editor padrão é 'Editar.'</span><span class="sxs-lookup"><span data-stu-id="e029d-529">The default editor is 'Edit'.</span></span> <span data-ttu-id="e029d-530">Para alterar o editor, defina a variável de ambiente SQLCMDEDITOR.</span><span class="sxs-lookup"><span data-stu-id="e029d-530">To change the editor, set the SQLCMDEDITOR environment variable.</span></span> <span data-ttu-id="e029d-531">Por exemplo, para definir o editor como [!INCLUDE[msCoName](../includes/msconame-md.md)] Notepad, no prompt de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="e029d-531">For example, to set the editor to [!INCLUDE[msCoName](../includes/msconame-md.md)] Notepad, at the command prompt, type:</span></span>  
  
 `SET SQLCMDEDITOR=notepad`  
  
 <span data-ttu-id="e029d-532">[ **:** ] **RESET**</span><span class="sxs-lookup"><span data-stu-id="e029d-532">[**:**] **RESET**</span></span>  
 <span data-ttu-id="e029d-533">Desmarca o cache de instruções.</span><span class="sxs-lookup"><span data-stu-id="e029d-533">Clears the statement cache.</span></span>  
  
 <span data-ttu-id="e029d-534">**:List**</span><span class="sxs-lookup"><span data-stu-id="e029d-534">**:List**</span></span>  
 <span data-ttu-id="e029d-535">Imprime o conteúdo do cache de instrução.</span><span class="sxs-lookup"><span data-stu-id="e029d-535">Prints the content of the statement cache.</span></span>  
  
 <span data-ttu-id="e029d-536">**Variáveis**</span><span class="sxs-lookup"><span data-stu-id="e029d-536">**Variables**</span></span>  
  <span data-ttu-id="e029d-537">**: Setvar** \<**var**> [ **"*`value`*"** ]</span><span class="sxs-lookup"><span data-stu-id="e029d-537">**:Setvar** \<**var**> [ **"*`value`*"** ]</span></span>  
 <span data-ttu-id="e029d-538">Define as variáveis de script do `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="e029d-538">Defines `sqlcmd` scripting variables.</span></span> <span data-ttu-id="e029d-539">Variáveis de script têm o seguinte formato: `$(VARNAME)`.</span><span class="sxs-lookup"><span data-stu-id="e029d-539">Scripting variables have the following format: `$(VARNAME)`.</span></span>  
  
 <span data-ttu-id="e029d-540">Nomes de variáveis não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e029d-540">Variable names are case insensitive.</span></span>  
  
 <span data-ttu-id="e029d-541">Variáveis de script podem ser definidas da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="e029d-541">Scripting variables can be set in the following ways:</span></span>  
  
-   <span data-ttu-id="e029d-542">Usando-se implicitamente uma opção de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="e029d-542">Implicitly using a command-line option.</span></span> <span data-ttu-id="e029d-543">Por exemplo, a opção **-l** define a `sqlcmd` variável SQLCMDLOGINTIMEOUT.</span><span class="sxs-lookup"><span data-stu-id="e029d-543">For example, the **-l** option sets the SQLCMDLOGINTIMEOUT `sqlcmd` variable.</span></span>  
  
-   <span data-ttu-id="e029d-544">Explicitamente, usando o comando **:Setvar** .</span><span class="sxs-lookup"><span data-stu-id="e029d-544">Explicitly by using the **:Setvar** command.</span></span>  
  
-   <span data-ttu-id="e029d-545">Definindo uma variável de ambiente antes de executar o `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="e029d-545">By defining an environment variable before you run `sqlcmd`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e029d-546">A opção `-X` evita que variáveis de ambiente sejam passadas para o `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="e029d-546">The `-X` option prevents environment variables from being passed on to `sqlcmd`.</span></span>  
  
 <span data-ttu-id="e029d-547">Se uma variável definida com **:Setvar** e uma variável de ambiente tiverem o mesmo nome, a variável definida com **:Setvar** terá precedência.</span><span class="sxs-lookup"><span data-stu-id="e029d-547">If a variable defined by using **:Setvar** and an environment variable have the same name, the variable defined by using **:Setvar** takes precedence.</span></span>  
  
 <span data-ttu-id="e029d-548">Nomes de variáveis não devem conter caracteres de espaço em branco.</span><span class="sxs-lookup"><span data-stu-id="e029d-548">Variable names must not contain blank space characters.</span></span>  
  
 <span data-ttu-id="e029d-549">Nomes de variáveis não podem ter a mesma forma que uma expressão variável, como $ (var).</span><span class="sxs-lookup"><span data-stu-id="e029d-549">Variable names cannot have the same form as a variable expression, such as $(var).</span></span>  
  
 <span data-ttu-id="e029d-550">Se o valor da cadeia de caracteres da variável de script tiver espaços em branco, use aspas.</span><span class="sxs-lookup"><span data-stu-id="e029d-550">If the string value of the scripting variable contains blank spaces, enclose the value in quotation marks.</span></span> <span data-ttu-id="e029d-551">Se não for especificado um valor para uma variável de script, a variável de script será descartada.</span><span class="sxs-lookup"><span data-stu-id="e029d-551">If a value for a scripting variable is not specified, the scripting variable is dropped.</span></span>  
  
 <span data-ttu-id="e029d-552">**:Listvar**</span><span class="sxs-lookup"><span data-stu-id="e029d-552">**:Listvar**</span></span>  
 <span data-ttu-id="e029d-553">Exibe uma lista das variáveis de script definidas atualmente.</span><span class="sxs-lookup"><span data-stu-id="e029d-553">Displays a list of the scripting variables that are currently set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e029d-554">Somente variáveis de script definidas por `sqlcmd` , e aquelas que são definidas usando o comando **: setvar** serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="e029d-554">Only scripting variables that are set by `sqlcmd`, and those that are set using the **:Setvar** command will be displayed.</span></span>  
  
 <span data-ttu-id="e029d-555">**Comandos de Saída**</span><span class="sxs-lookup"><span data-stu-id="e029d-555">**Output Commands**</span></span>  
  <span data-ttu-id="e029d-556">**:Error** </span><span class="sxs-lookup"><span data-stu-id="e029d-556">**:Error** </span></span>  
 <span data-ttu-id="e029d-557">**_\<_** _filename_  **_>|_ STDERR | STDOUT**</span><span class="sxs-lookup"><span data-stu-id="e029d-557">**_\<_** _filename_  **_>|_ STDERR|STDOUT**</span></span>  
 <span data-ttu-id="e029d-558">Redireciona toda a saída de erro para o arquivo especificado por *nome do arquivo*para **stderr** ou **stdout**.</span><span class="sxs-lookup"><span data-stu-id="e029d-558">Redirect all error output to the file specified by *file name*, to **stderr** or to **stdout**.</span></span> <span data-ttu-id="e029d-559">O comando **Error** pode aparecer várias vezes em um script.</span><span class="sxs-lookup"><span data-stu-id="e029d-559">The **Error** command can appear multiple times in a script.</span></span> <span data-ttu-id="e029d-560">Por padrão, saída de erro é enviada para **stderr**.</span><span class="sxs-lookup"><span data-stu-id="e029d-560">By default, error output is sent to **stderr**.</span></span>  
  
 <span data-ttu-id="e029d-561">*nome do arquivo*</span><span class="sxs-lookup"><span data-stu-id="e029d-561">*file name*</span></span>  
 <span data-ttu-id="e029d-562">Cria e abre um arquivo que receberá a saída.</span><span class="sxs-lookup"><span data-stu-id="e029d-562">Creates and opens a file that will receive the output.</span></span> <span data-ttu-id="e029d-563">Se o arquivo já existir, será truncado para zero bytes.</span><span class="sxs-lookup"><span data-stu-id="e029d-563">If the file already exists, it will be truncated to zero bytes.</span></span> <span data-ttu-id="e029d-564">Se o arquivo não estiver disponível devido a permissões ou outras razões, a saída não será alternada e será enviada ao último destino especificado ou ao destino padrão.</span><span class="sxs-lookup"><span data-stu-id="e029d-564">If the file is not available because of permissions or other reasons, the output will not be switched and will be sent to the last specified or default destination.</span></span>  
  
 <span data-ttu-id="e029d-565">**STDERR**</span><span class="sxs-lookup"><span data-stu-id="e029d-565">**STDERR**</span></span>  
 <span data-ttu-id="e029d-566">Muda a saída de erro para o fluxo **stderr** .</span><span class="sxs-lookup"><span data-stu-id="e029d-566">Switches error output to the **stderr** stream.</span></span> <span data-ttu-id="e029d-567">Se houver redirecionamento, o destino para o qual o fluxo foi redirecionado receberá a saída de erro.</span><span class="sxs-lookup"><span data-stu-id="e029d-567">If this has been redirected, the target to which the stream has been redirected will receive the error output.</span></span>  
  
 <span data-ttu-id="e029d-568">**STDOUT**</span><span class="sxs-lookup"><span data-stu-id="e029d-568">**STDOUT**</span></span>  
 <span data-ttu-id="e029d-569">Muda a saída de erro para o fluxo **stdout** .</span><span class="sxs-lookup"><span data-stu-id="e029d-569">Switches error output to the **stdout** stream.</span></span> <span data-ttu-id="e029d-570">Se houver redirecionamento, o destino para o qual o fluxo foi redirecionado receberá a saída de erro.</span><span class="sxs-lookup"><span data-stu-id="e029d-570">If this has been redirected, the target to which the stream has been redirected will receive the error output.</span></span>  
  
 <span data-ttu-id="e029d-571">\*\*: Out \<** _filename_ **> \*\* |  **Stderr** |  **Stdout**</span><span class="sxs-lookup"><span data-stu-id="e029d-571">**:Out \<** _filename_ **>**| **STDERR**| **STDOUT**</span></span>  
 <span data-ttu-id="e029d-572">Cria e redireciona todos os resultados da consulta para o arquivo especificado por *nome do arquivo*para **stderr** ou **stdout**.</span><span class="sxs-lookup"><span data-stu-id="e029d-572">Creates and redirects all query results to the file specified by *file name*, to **stderr** or to **stdout**.</span></span> <span data-ttu-id="e029d-573">Por padrão, a saída é enviada para **stdout**.</span><span class="sxs-lookup"><span data-stu-id="e029d-573">By default, output is sent to **stdout**.</span></span> <span data-ttu-id="e029d-574">Se o arquivo já existir, será truncado para zero bytes.</span><span class="sxs-lookup"><span data-stu-id="e029d-574">If the file already exists, it will be truncated to zero bytes.</span></span> <span data-ttu-id="e029d-575">O comando **Out** pode aparecer várias vezes em um script.</span><span class="sxs-lookup"><span data-stu-id="e029d-575">The **Out** command can appear multiple times in a script.</span></span>  
  
 <span data-ttu-id="e029d-576">\*\*:P erftrace \<** _filename_ **> \*\* |  **Stderr** |  **Stdout**</span><span class="sxs-lookup"><span data-stu-id="e029d-576">**:Perftrace \<** _filename_ **>**| **STDERR**| **STDOUT**</span></span>  
 <span data-ttu-id="e029d-577">Cria e redireciona todas as informações de rastreamento de desempenho para o arquivo especificado por *nome do arquivo*para **stderr** ou **stdout**.</span><span class="sxs-lookup"><span data-stu-id="e029d-577">Creates and redirects all performance trace information to the file specified by *file name*, to **stderr** or to **stdout**.</span></span> <span data-ttu-id="e029d-578">Por padrão a saída de rastreamento de desempenho é enviada para **stdout**.</span><span class="sxs-lookup"><span data-stu-id="e029d-578">By default performance trace output is sent to **stdout**.</span></span> <span data-ttu-id="e029d-579">Se o arquivo já existir, será truncado para zero bytes.</span><span class="sxs-lookup"><span data-stu-id="e029d-579">If the file already exists, it will be truncated to zero bytes.</span></span> <span data-ttu-id="e029d-580">O comando **Perftrace** pode aparecer várias vezes em um script.</span><span class="sxs-lookup"><span data-stu-id="e029d-580">The **Perftrace** command can appear multiple times in a script.</span></span>  
  
 <span data-ttu-id="e029d-581">**Comandos de controle de execução**</span><span class="sxs-lookup"><span data-stu-id="e029d-581">**Execution Control Commands**</span></span>  
  <span data-ttu-id="e029d-582">**:** Se houver erro [ `exit`  |  `ignore` ]</span><span class="sxs-lookup"><span data-stu-id="e029d-582">**:On Error**[ `exit` | `ignore`]</span></span>  
 <span data-ttu-id="e029d-583">Define a ação a ser executada no caso de um erro durante a execução de script ou em lote.</span><span class="sxs-lookup"><span data-stu-id="e029d-583">Sets the action to be performed when an error occurs during script or batch execution.</span></span>  
  
 <span data-ttu-id="e029d-584">Quando a opção `exit` é usada, o `sqlcmd` é fechado com o valor de erro adequado.</span><span class="sxs-lookup"><span data-stu-id="e029d-584">When the `exit` option is used, `sqlcmd` exits with the appropriate error value.</span></span>  
  
 <span data-ttu-id="e029d-585">Quando é usada a opção `ignore`, o `sqlcmd` ignora o erro e continua executando o lote ou script.</span><span class="sxs-lookup"><span data-stu-id="e029d-585">When the `ignore` option is used, `sqlcmd` ignores the error and continues executing the batch or script.</span></span> <span data-ttu-id="e029d-586">Por padrão, será impressa uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="e029d-586">By default, an error message will be printed.</span></span>  
  
 <span data-ttu-id="e029d-587">[ **:** ] **QUIT**</span><span class="sxs-lookup"><span data-stu-id="e029d-587">[**:**] **QUIT**</span></span>  
 <span data-ttu-id="e029d-588">Faz com que o `sqlcmd` seja encerrado.</span><span class="sxs-lookup"><span data-stu-id="e029d-588">Causes `sqlcmd` to exit.</span></span>  
  
 <span data-ttu-id="e029d-589">[**:**] **Sair**[ **( *`statement`* )** ]</span><span class="sxs-lookup"><span data-stu-id="e029d-589">[**:**] **EXIT**[ **(*`statement`*)** ]</span></span>  
 <span data-ttu-id="e029d-590">Permite usar o resultado de uma instrução SELECT como o valor de retorno do `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="e029d-590">Lets you use the result of a SELECT statement as the return value from `sqlcmd`.</span></span> <span data-ttu-id="e029d-591">Se numérico, a primeira coluna da última linha do resultado será convertida em um inteiro de 4 bytes (longo).</span><span class="sxs-lookup"><span data-stu-id="e029d-591">If numeric, the first column of the last result row is converted to a 4-byte integer (long).</span></span> <span data-ttu-id="e029d-592">O MS-DOS transmite o byte baixo para o processo pai ou nível de erro do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="e029d-592">MS-DOS passes the low byte to the parent process or operating system error level.</span></span> <span data-ttu-id="e029d-593">O Windows 200x passa todo o número inteiro de 4 bytes.</span><span class="sxs-lookup"><span data-stu-id="e029d-593">Windows 200x passes the whole 4-byte integer.</span></span> <span data-ttu-id="e029d-594">A sintaxe do é:</span><span class="sxs-lookup"><span data-stu-id="e029d-594">The syntax is:</span></span>  
  
 `:EXIT(query)`  
  
 <span data-ttu-id="e029d-595">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e029d-595">For example:</span></span>  
  
 `:EXIT(SELECT @@ROWCOUNT)`  
  
 <span data-ttu-id="e029d-596">É possível incluir também o parâmetro **EXIT** como parte de um arquivo em lote.</span><span class="sxs-lookup"><span data-stu-id="e029d-596">You can also include the **EXIT** parameter as part of a batch file.</span></span> <span data-ttu-id="e029d-597">Por exemplo, no prompt de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="e029d-597">For example, at the command prompt, type:</span></span>  
  
 `sqlcmd -Q "EXIT(SELECT COUNT(*) FROM '%1')"`  
  
 <span data-ttu-id="e029d-598">O `sqlcmd` utilitário envia tudo entre os parênteses **()** para o servidor.</span><span class="sxs-lookup"><span data-stu-id="e029d-598">The `sqlcmd` utility sends everything between the parentheses **()** to the server.</span></span> <span data-ttu-id="e029d-599">Se um procedimento armazenado de sistema selecionar um conjunto e retornar um valor, somente a seleção será retornada.</span><span class="sxs-lookup"><span data-stu-id="e029d-599">If a system stored procedure selects a set and returns a value, only the selection is returned.</span></span> <span data-ttu-id="e029d-600">A instrução EXIT **()** sem nada entre os parênteses executa tudo antes dela no lote e é fechada sem um valor de retorno.</span><span class="sxs-lookup"><span data-stu-id="e029d-600">The EXIT **()** statement with nothing between the parentheses executes everything before it in the batch and then exits without a return value.</span></span>  
  
 <span data-ttu-id="e029d-601">Quando é especificada uma consulta incorreta, o `sqlcmd` é encerrado sem um valor de retorno.</span><span class="sxs-lookup"><span data-stu-id="e029d-601">When an incorrect query is specified, `sqlcmd` will exit without a return value.</span></span>  
  
 <span data-ttu-id="e029d-602">Eis uma lista de formatos EXIT:</span><span class="sxs-lookup"><span data-stu-id="e029d-602">Here is a list of EXIT formats:</span></span>  
  
-   <span data-ttu-id="e029d-603">:EXIT</span><span class="sxs-lookup"><span data-stu-id="e029d-603">:EXIT</span></span>  
  
 <span data-ttu-id="e029d-604">Não executa o lote e então sai imediatamente e não retorna valor algum.</span><span class="sxs-lookup"><span data-stu-id="e029d-604">Does not execute the batch, and then quits immediately and returns no value.</span></span>  
  
-   <span data-ttu-id="e029d-605">:EXIT( )</span><span class="sxs-lookup"><span data-stu-id="e029d-605">:EXIT( )</span></span>  
  
 <span data-ttu-id="e029d-606">Executa o lote e então sai imediatamente e não retorna valor algum.</span><span class="sxs-lookup"><span data-stu-id="e029d-606">Executes the batch, and then quits and returns no value.</span></span>  
  
-   <span data-ttu-id="e029d-607">:EXIT(query)</span><span class="sxs-lookup"><span data-stu-id="e029d-607">:EXIT(query)</span></span>  
  
 <span data-ttu-id="e029d-608">Executa o lote que inclui a consulta, e então sai depois de retornar os resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="e029d-608">Executes the batch that includes the query, and then quits after it returns the results of the query.</span></span>  
  
 <span data-ttu-id="e029d-609">Se RAISERROR for usado em um `sqlcmd` script e um estado de 127 for gerado, sairá `sqlcmd` e retornará a ID da mensagem para o cliente.</span><span class="sxs-lookup"><span data-stu-id="e029d-609">If RAISERROR is used within a `sqlcmd` script and a state of 127 is raised, `sqlcmd` will quit and return the message ID back to the client.</span></span> <span data-ttu-id="e029d-610">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e029d-610">For example:</span></span>  
  
 `RAISERROR(50001, 10, 127)`  
  
 <span data-ttu-id="e029d-611">Esse erro fará com que o script do `sqlcmd` seja encerrado e retorne a ID de mensagem 50001 ao cliente.</span><span class="sxs-lookup"><span data-stu-id="e029d-611">This error will cause the `sqlcmd` script to end and return the message ID 50001 to the client.</span></span>  
  
 <span data-ttu-id="e029d-612">Os valores de retorno -1 a -99 são reservados pelo [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]; `sqlcmd` define os seguintes valores de retorno adicionais:</span><span class="sxs-lookup"><span data-stu-id="e029d-612">The return values -1 to -99 are reserved by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]; `sqlcmd` defines the following additional return values:</span></span>  
  
|<span data-ttu-id="e029d-613">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="e029d-613">Return Values</span></span>|<span data-ttu-id="e029d-614">Descrição</span><span class="sxs-lookup"><span data-stu-id="e029d-614">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="e029d-615">-100</span><span class="sxs-lookup"><span data-stu-id="e029d-615">-100</span></span>|<span data-ttu-id="e029d-616">Erro encontrado antes da seleção do valor de retorno.</span><span class="sxs-lookup"><span data-stu-id="e029d-616">Error encountered prior to selecting return value.</span></span>|  
|<span data-ttu-id="e029d-617">-101</span><span class="sxs-lookup"><span data-stu-id="e029d-617">-101</span></span>|<span data-ttu-id="e029d-618">Nenhuma linha encontrada ao se selecionar o valor de retorno.</span><span class="sxs-lookup"><span data-stu-id="e029d-618">No rows found when selecting return value.</span></span>|  
|<span data-ttu-id="e029d-619">-102</span><span class="sxs-lookup"><span data-stu-id="e029d-619">-102</span></span>|<span data-ttu-id="e029d-620">Erro de conversão ao selecionar valor de retorno.</span><span class="sxs-lookup"><span data-stu-id="e029d-620">Conversion error occurred when selecting return value.</span></span>|  
  
 <span data-ttu-id="e029d-621">**GO** [*count*]</span><span class="sxs-lookup"><span data-stu-id="e029d-621">**GO** [*count*]</span></span>  
 <span data-ttu-id="e029d-622">GO sinaliza tanto o término de um lote quanto a execução de qualquer instrução de cachê do [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e029d-622">GO signals both the end of a batch and the execution of any cached [!INCLUDE[tsql](../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="e029d-623">Ao especificar um valor para *count*, serão executadas as instruções de cache *count* vezes, como um único lote.</span><span class="sxs-lookup"><span data-stu-id="e029d-623">When specifying a value for *count*, the cached statements will be executed *count* times, as a single batch.</span></span>  
  
 <span data-ttu-id="e029d-624">**Comandos diversos**</span><span class="sxs-lookup"><span data-stu-id="e029d-624">**Miscellaneous Commands**</span></span>  
  <span data-ttu-id="e029d-625">**: r\<** _filename_ **>**</span><span class="sxs-lookup"><span data-stu-id="e029d-625">**:r \<** _filename_ **>**</span></span>  
 <span data-ttu-id="e029d-626">Analisa [!INCLUDE[tsql](../includes/tsql-md.md)] comandos e instruções adicionais `sqlcmd` do arquivo especificado por **<*`filename`*>** no cache de instruções.</span><span class="sxs-lookup"><span data-stu-id="e029d-626">Parses additional [!INCLUDE[tsql](../includes/tsql-md.md)] statements and `sqlcmd` commands from the file specified by **<*`filename`*>** into the statement cache.</span></span>  
  
 <span data-ttu-id="e029d-627">Se o arquivo contiver instruções [!INCLUDE[tsql](../includes/tsql-md.md)] que não são seguidas por **GO**, digite **GO** na linha que segue **:r**.</span><span class="sxs-lookup"><span data-stu-id="e029d-627">If the file contains [!INCLUDE[tsql](../includes/tsql-md.md)] statements that are not followed by **GO**, you must enter **GO** on the line that follows **:r**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e029d-628">**\<** _filename_ **>** é lido em relação ao diretório de inicialização no qual `sqlcmd` foi executado.</span><span class="sxs-lookup"><span data-stu-id="e029d-628">**\<** _filename_ **>** is read relative to the startup directory in which `sqlcmd` was run.</span></span>  
  
 <span data-ttu-id="e029d-629">O arquivo será lido e executado depois que for encontrado um terminador de lote.</span><span class="sxs-lookup"><span data-stu-id="e029d-629">The file will be read and executed after a batch terminator is encountered.</span></span> <span data-ttu-id="e029d-630">Podem ser emitidos vários comandos **:r** .</span><span class="sxs-lookup"><span data-stu-id="e029d-630">You can issue multiple **:r** commands.</span></span> <span data-ttu-id="e029d-631">O arquivo pode incluir qualquer comando `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="e029d-631">The file may include any `sqlcmd` command.</span></span> <span data-ttu-id="e029d-632">Isso inclui o terminador de lote **GO**.</span><span class="sxs-lookup"><span data-stu-id="e029d-632">This includes the batch terminator **GO**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e029d-633">A contagem de linha que é exibida em modo interativo será aumentada em um para cada comando **:r** encontrado.</span><span class="sxs-lookup"><span data-stu-id="e029d-633">The line count that is displayed in interactive mode will be increased by one for every **:r** command encountered.</span></span> <span data-ttu-id="e029d-634">O comando **:r** aparecerá na saída do comando de lista.</span><span class="sxs-lookup"><span data-stu-id="e029d-634">The **:r** command will appear in the output of the list command.</span></span>  
  
 <span data-ttu-id="e029d-635">**:Serverlist**</span><span class="sxs-lookup"><span data-stu-id="e029d-635">**:Serverlist**</span></span>  
 <span data-ttu-id="e029d-636">Lista os servidores configurados localmente e os nomes dos servidores que estão transmitindo na rede.</span><span class="sxs-lookup"><span data-stu-id="e029d-636">Lists the locally configured servers and the names of the servers broadcasting on the network.</span></span>  
  
 <span data-ttu-id="e029d-637">**: Conectar** _server_name_[ **\\** _instance_name_] [-l *tempo limite*] [-U *user_name* [-P *senha*]]</span><span class="sxs-lookup"><span data-stu-id="e029d-637">**:Connect** _server_name_[**\\**_instance_name_] [-l *timeout*] [-U *user_name* [-P *password*]]</span></span>  
 <span data-ttu-id="e029d-638">Conecta-se a uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e029d-638">Connects to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e029d-639">Além disso fecha a conexão atual.</span><span class="sxs-lookup"><span data-stu-id="e029d-639">Also closes the current connection.</span></span>  
  
 <span data-ttu-id="e029d-640">Opções de tempo limite:</span><span class="sxs-lookup"><span data-stu-id="e029d-640">Time-out options:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e029d-641">0</span><span class="sxs-lookup"><span data-stu-id="e029d-641">0</span></span>|<span data-ttu-id="e029d-642">esperar</span><span class="sxs-lookup"><span data-stu-id="e029d-642">wait forever</span></span>|  
|<span data-ttu-id="e029d-643">n>0</span><span class="sxs-lookup"><span data-stu-id="e029d-643">n>0</span></span>|<span data-ttu-id="e029d-644">esperar por n segundos</span><span class="sxs-lookup"><span data-stu-id="e029d-644">wait for n seconds</span></span>|  
  
 <span data-ttu-id="e029d-645">A variável de script SQLCMDSERVER refletirá a conexão ativa atual.</span><span class="sxs-lookup"><span data-stu-id="e029d-645">The SQLCMDSERVER scripting variable will reflect the current active connection.</span></span>  
  
 <span data-ttu-id="e029d-646">Se não for especificado *timeout* , o valor da variável SQLCMDLOGINTIMEOUT será o padrão.</span><span class="sxs-lookup"><span data-stu-id="e029d-646">If *timeout* is not specified, the value of the SQLCMDLOGINTIMEOUT variable is the default.</span></span>  
  
 <span data-ttu-id="e029d-647">Se apenas *user_name* for especificado (como uma opção ou variável de ambiente), será solicitado que o usuário insira uma senha.</span><span class="sxs-lookup"><span data-stu-id="e029d-647">If only *user_name* is specified (either as an option, or as an environment variable), the user will be prompted to enter a password.</span></span> <span data-ttu-id="e029d-648">Isso não ocorre se as variáveis de ambiente SQLCMDUSER ou SQLCMDPASSWORD tiverem sido definidas.</span><span class="sxs-lookup"><span data-stu-id="e029d-648">This is not true if the SQLCMDUSER or SQLCMDPASSWORD environment variables have been set.</span></span> <span data-ttu-id="e029d-649">Se as opções e as variáveis de ambiente não forem fornecidas, o modo de Autenticação do Windows será usado para fazer logon.</span><span class="sxs-lookup"><span data-stu-id="e029d-649">If neither options nor environment variables are provided, Windows Authentication mode is used to login.</span></span> <span data-ttu-id="e029d-650">Por exemplo, para conectar-se a uma instância, `instance1`, do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], `myserver`, usando segurança integrada você usaria o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e029d-650">For example to connect to an instance, `instance1`, of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], `myserver`, by using integrated security you would use the following:</span></span>  
  
 `:connect myserver\instance1`  
  
 <span data-ttu-id="e029d-651">Para conectar-se à instância padrão do `myserver` usando variáveis de script, você usaria o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e029d-651">To connect to the default instance of `myserver` using scripting variables, you would use the following:</span></span>  
  
 `:setvar myusername test`  
  
 `:setvar myservername myserver`  
  
 `:connect $(myservername) $(myusername)`  
  
 <span data-ttu-id="e029d-652">[**:**] **!!**\< *command*></span><span class="sxs-lookup"><span data-stu-id="e029d-652">[**:**] **!!**\< *command*></span></span>  
 <span data-ttu-id="e029d-653">Executa comandos de sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="e029d-653">Executes operating system commands.</span></span> <span data-ttu-id="e029d-654">Para executar um comando do sistema operacional, inicie uma linha com dois pontos de exclamação ( **!!** ) seguida do comando do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="e029d-654">To execute an operating system command, start a line with two exclamation marks (**!!**) followed by the operating system command.</span></span> <span data-ttu-id="e029d-655">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e029d-655">For example:</span></span>  
  
 `:!! Dir`  
  
> [!NOTE]  
>  <span data-ttu-id="e029d-656">O comando é executado no computador no qual o `sqlcmd` está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="e029d-656">The command is executed on the computer on which `sqlcmd` is running.</span></span>  
  
 <span data-ttu-id="e029d-657">**:XML** [**ON** | **OFF**]</span><span class="sxs-lookup"><span data-stu-id="e029d-657">**:XML** [**ON** | **OFF**]</span></span>  
 <span data-ttu-id="e029d-658">Para obter mais informações, consulte "XML Output Format", posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="e029d-658">For more information, see "XML Output Format," later in this topic</span></span>  
  
 <span data-ttu-id="e029d-659">**:Help**</span><span class="sxs-lookup"><span data-stu-id="e029d-659">**:Help**</span></span>  
 <span data-ttu-id="e029d-660">Lista comandos do `sqlcmd` juntamente com uma breve descrição de cada comando.</span><span class="sxs-lookup"><span data-stu-id="e029d-660">Lists `sqlcmd` commands together with a short description of each command.</span></span>  
  
### <a name="sqlcmd-file-names"></a><span data-ttu-id="e029d-661">Nomes de arquivos sqlcmd</span><span class="sxs-lookup"><span data-stu-id="e029d-661">sqlcmd File Names</span></span>  
 <span data-ttu-id="e029d-662">`sqlcmd`os arquivos de entrada podem ser especificados com a opção **-i** ou o comando **: r** .</span><span class="sxs-lookup"><span data-stu-id="e029d-662">`sqlcmd` input files can be specified with the **-i** option or the **:r** command.</span></span> <span data-ttu-id="e029d-663">Arquivos de saída podem ser especificados com a opção **-o** ou os comandos **:Error**, **:Out** e **:Perftrace** .</span><span class="sxs-lookup"><span data-stu-id="e029d-663">Output files can be specified with the **-o** option or the **:Error**, **:Out** and **:Perftrace** commands.</span></span> <span data-ttu-id="e029d-664">A seguir algumas diretrizes sobre como trabalhar com esses arquivos:</span><span class="sxs-lookup"><span data-stu-id="e029d-664">The following are some guidelines for working with these files:</span></span>  
  
-   <span data-ttu-id="e029d-665">**: Error**, **: out** e **:P erftrace** devem usar separados **<*`filename`*>** .</span><span class="sxs-lookup"><span data-stu-id="e029d-665">**:Error**, **:Out** and **:Perftrace** should use separate **<*`filename`*>**.</span></span> <span data-ttu-id="e029d-666">Se o mesmo **<*`filename`*>** for usado, as entradas dos comandos poderão ser misturadas.</span><span class="sxs-lookup"><span data-stu-id="e029d-666">If the same **<*`filename`*>** is used, inputs from the commands may be intermixed.</span></span>  
  
-   <span data-ttu-id="e029d-667">Se for chamado um arquivo de entrada em um servidor remoto do `sqlcmd` em um computador local e o arquivo tiver um caminho de arquivo de unidade como: c:\OutputFile.txt.</span><span class="sxs-lookup"><span data-stu-id="e029d-667">If an input file that is located on a remote server is called from `sqlcmd` on a local computer and the file contains a drive file path such as :out c:\OutputFile.txt.</span></span> <span data-ttu-id="e029d-668">O arquivo de saída será criado no computador local e não no servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="e029d-668">The output file will be created on the local computer and not on the remote server.</span></span>  
  
-   <span data-ttu-id="e029d-669">Os caminhos de arquivo válidos incluem: C: \\ **<*`filename`*>** , \\ \\<Server \> \\<compartilhamento $>\\ **<*`filename`*>** e "pasta c:\Alguma \\ **<*`file name`*>** ".</span><span class="sxs-lookup"><span data-stu-id="e029d-669">Valid file paths include: C:\\**<*`filename`*>**, \\\\<Server\>\\<Share$>\\**<*`filename`*>** and "C:\Some Folder\\**<*`file name`*>**".</span></span> <span data-ttu-id="e029d-670">Se houver um espaço no caminho, use aspas.</span><span class="sxs-lookup"><span data-stu-id="e029d-670">If there is a space in the path, use quotation marks.</span></span>  
  
-   <span data-ttu-id="e029d-671">Cada nova sessão do `sqlcmd` substituirá arquivos existentes que tenham os mesmos nomes.</span><span class="sxs-lookup"><span data-stu-id="e029d-671">Each new `sqlcmd` session will overwrite existing files that have the same names.</span></span>  
  
### <a name="informational-messages"></a><span data-ttu-id="e029d-672">Mensagens informativas</span><span class="sxs-lookup"><span data-stu-id="e029d-672">Informational Messages</span></span>  
 <span data-ttu-id="e029d-673">O `sqlcmd` imprime qualquer mensagem informativa enviada pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="e029d-673">`sqlcmd` prints any informational message that are sent by the server.</span></span> <span data-ttu-id="e029d-674">No exemplo a seguir, depois que as instruções do [!INCLUDE[tsql](../includes/tsql-md.md)] são executadas, é impressa uma mensagem informativa.</span><span class="sxs-lookup"><span data-stu-id="e029d-674">In the following example, after the [!INCLUDE[tsql](../includes/tsql-md.md)] statements are executed, an informational message is printed.</span></span>  
  
 <span data-ttu-id="e029d-675">No prompt de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e029d-675">At the command prompt, type the following:</span></span>  
  
 `sqlcmd`  
  
 `At the sqlcmd prompt type:`  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 <span data-ttu-id="e029d-676">Quando você pressiona ENTER, a seguinte mensagem informativa é impressa: "Contexto de banco de dados alterado para 'AdventureWorks2012'."</span><span class="sxs-lookup"><span data-stu-id="e029d-676">When you press ENTER, the following informational message is printed: "Changed database context to 'AdventureWorks2012'."</span></span>  
  
### <a name="output-format-from-transact-sql-queries"></a><span data-ttu-id="e029d-677">Formato de saída do Transact-SQL Queries</span><span class="sxs-lookup"><span data-stu-id="e029d-677">Output Format from Transact-SQL Queries</span></span>  
 <span data-ttu-id="e029d-678">O `sqlcmd` imprime, em primeiro lugar, um cabeçalho de coluna com os nomes de coluna especificados na lista de seleção.</span><span class="sxs-lookup"><span data-stu-id="e029d-678">`sqlcmd` first prints a column header that contains the column names specified in the select list.</span></span> <span data-ttu-id="e029d-679">Os nomes de coluna são separados usando-se o caractere SQLCMDCOLSEP.</span><span class="sxs-lookup"><span data-stu-id="e029d-679">The column names are separated by using the SQLCMDCOLSEP character.</span></span> <span data-ttu-id="e029d-680">Por padrão, esse é um espaço.</span><span class="sxs-lookup"><span data-stu-id="e029d-680">By default, this is a space.</span></span> <span data-ttu-id="e029d-681">Se o nome de coluna for mais curto do que a largura de coluna, a saída será preenchida com espaços até a coluna seguinte.</span><span class="sxs-lookup"><span data-stu-id="e029d-681">If the column name is shorter than the column width, the output is padded with spaces up to the next column.</span></span>  
  
 <span data-ttu-id="e029d-682">Essa linha será seguida por uma linha divisória formada por uma série de tracejados.</span><span class="sxs-lookup"><span data-stu-id="e029d-682">This line will be followed by a separator line that is a series of dash characters.</span></span> <span data-ttu-id="e029d-683">A saída a seguir mostra um exemplo.</span><span class="sxs-lookup"><span data-stu-id="e029d-683">The following output shows an example.</span></span>  
  
 <span data-ttu-id="e029d-684">Inicie o `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="e029d-684">Start `sqlcmd`.</span></span> <span data-ttu-id="e029d-685">No prompt de comando do `sqlcmd`, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e029d-685">At the `sqlcmd` command prompt, type the following:</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `SELECT TOP (2) BusinessEntityID, FirstName, LastName`  
  
 `FROM Person.Person;`  
  
 `GO`  
  
 <span data-ttu-id="e029d-686">Quando você pressiona Enter, o seguinte conjunto de resultados é retornado.</span><span class="sxs-lookup"><span data-stu-id="e029d-686">When you press ENTER, the following result set is returned.</span></span>  
  
 `BusinessEntityID FirstName    LastName`  
  
 `---------------- ------------ ----------`  
  
 `285              Syed         Abbas`  
  
 `293              Catherine    Abel`  
  
 `(2 row(s) affected)`  
  
 <span data-ttu-id="e029d-687">Embora a coluna `BusinessEntityID` tenha apenas 4 caracteres de largura, ela foi expandida para acomodar o nome de coluna mais longo.</span><span class="sxs-lookup"><span data-stu-id="e029d-687">Although the `BusinessEntityID` column is only 4 characters wide, it has been expanded to accommodate the longer column name.</span></span> <span data-ttu-id="e029d-688">Por padrão, a saída é finalizada com 80 caracteres.</span><span class="sxs-lookup"><span data-stu-id="e029d-688">By default, output is terminated at 80 characters.</span></span> <span data-ttu-id="e029d-689">Isso pode ser alterado com a opção **-w** ou com a definição da variável de script SQLCMDCOLWIDTH.</span><span class="sxs-lookup"><span data-stu-id="e029d-689">This can be changed by using the **-w** option, or by setting the SQLCMDCOLWIDTH scripting variable.</span></span>  
  
### <a name="xml-output-format"></a><span data-ttu-id="e029d-690">Formato de saída XML</span><span class="sxs-lookup"><span data-stu-id="e029d-690">XML Output Format</span></span>  
 <span data-ttu-id="e029d-691">Saída XML é o resultado de uma cláusula FOR XML, não formatada, em um fluxo contínuo.</span><span class="sxs-lookup"><span data-stu-id="e029d-691">XML output that is the result of a FOR XML clause is output, unformatted, in a continuous stream.</span></span>  
  
 <span data-ttu-id="e029d-692">Quando você esperar uma saída XML, use o seguinte comando: `:XML ON`.</span><span class="sxs-lookup"><span data-stu-id="e029d-692">When you expect XML output, use the following command: `:XML ON`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e029d-693">O `sqlcmd` retorna mensagens de erro no formato habitual.</span><span class="sxs-lookup"><span data-stu-id="e029d-693">`sqlcmd` returns error messages in the usual format.</span></span> <span data-ttu-id="e029d-694">Observe que as mensagens de erro também são produzidas no fluxo de texto XML em formato XML.</span><span class="sxs-lookup"><span data-stu-id="e029d-694">Notice that the error messages are also output in the XML text stream in XML format.</span></span> <span data-ttu-id="e029d-695">Usando `:XML ON`, o `sqlcmd` não exibe mensagens informativas.</span><span class="sxs-lookup"><span data-stu-id="e029d-695">By using `:XML ON`, `sqlcmd` does not display informational messages.</span></span>  
  
 <span data-ttu-id="e029d-696">Para definir XML em modo off, use o seguinte comando: `:XML OFF`.</span><span class="sxs-lookup"><span data-stu-id="e029d-696">To set the XML mode off, use the following command: `:XML OFF`.</span></span>  
  
 <span data-ttu-id="e029d-697">O comando GO não deve aparecer antes de o comando XML OFF ser emitido porque o comando XML OFF retorna o `sqlcmd` para a saída orientada por linhas.</span><span class="sxs-lookup"><span data-stu-id="e029d-697">The GO command should not appear before the XML OFF command is issued because the XML OFF command switches `sqlcmd` back to row-oriented output.</span></span>  
  
 <span data-ttu-id="e029d-698">Dados XML (em fluxo) e dados de conjunto de linhas não podem ser misturados.</span><span class="sxs-lookup"><span data-stu-id="e029d-698">XML (streamed) data and rowset data cannot be mixed.</span></span> <span data-ttu-id="e029d-699">Se o comando XML ON não tiver sido emitido antes da execução de uma instrução do [!INCLUDE[tsql](../includes/tsql-md.md)] que gera protocolos XML, a saída será adulterada.</span><span class="sxs-lookup"><span data-stu-id="e029d-699">If the XML ON command has not been issued before a [!INCLUDE[tsql](../includes/tsql-md.md)] statement that outputs XML streams is executed, the output will be garbled.</span></span> <span data-ttu-id="e029d-700">Se o comando XML ON tiver sido emitido, não será possível executar instruções do [!INCLUDE[tsql](../includes/tsql-md.md)] que gerem conjuntos de linhas normais.</span><span class="sxs-lookup"><span data-stu-id="e029d-700">If the XML ON command has been issued, you cannot execute [!INCLUDE[tsql](../includes/tsql-md.md)] statements that output regular row sets.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e029d-701">O comando **:XML** não oferece suporte para a instrução SET STATISTICS XML.</span><span class="sxs-lookup"><span data-stu-id="e029d-701">The **:XML** command does not support the SET STATISTICS XML statement.</span></span>  
  
## <a name="sqlcmd-best-practices"></a><span data-ttu-id="e029d-702">Práticas recomendadas sqlcmd</span><span class="sxs-lookup"><span data-stu-id="e029d-702">sqlcmd Best Practices</span></span>  
 <span data-ttu-id="e029d-703">Use as seguintes práticas para ajudar a maximizar a segurança e a eficiência.</span><span class="sxs-lookup"><span data-stu-id="e029d-703">Use the following practices to help maximize security and efficiency.</span></span>  
  
-   <span data-ttu-id="e029d-704">Use segurança integrada.</span><span class="sxs-lookup"><span data-stu-id="e029d-704">Use integrated security.</span></span>  
  
-   <span data-ttu-id="e029d-705">Use `-X` em ambientes automatizados.</span><span class="sxs-lookup"><span data-stu-id="e029d-705">Use `-X` in automated environments.</span></span>  
  
-   <span data-ttu-id="e029d-706">Proteja arquivos de entrada e de saída usando permissões adequadas de sistema de arquivos NTFS.</span><span class="sxs-lookup"><span data-stu-id="e029d-706">Secure input and output files by using appropriate NTFS file system permissions.</span></span>  
  
-   <span data-ttu-id="e029d-707">Para aumentar o desempenho, faça o máximo possível em uma sessão `sqlcmd`, em vez de usar uma série de sessões.</span><span class="sxs-lookup"><span data-stu-id="e029d-707">To increase performance, do as much in one `sqlcmd` session as you can, instead of in a series of sessions.</span></span>  
  
-   <span data-ttu-id="e029d-708">Defina valores mais altos de tempo limite para execução em lote ou de consulta do que você imagina que levará para a execução em lote ou de consulta.</span><span class="sxs-lookup"><span data-stu-id="e029d-708">Set time-out values for batch or query execution higher than you expect it will take to execute the batch or query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e029d-709">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e029d-709">See Also</span></span>  
 <span data-ttu-id="e029d-710">[Iniciar o utilitário sqlcmd](../relational-databases/scripting/sqlcmd-start-the-utility.md) </span><span class="sxs-lookup"><span data-stu-id="e029d-710">[Start the sqlcmd Utility](../relational-databases/scripting/sqlcmd-start-the-utility.md) </span></span>  
 <span data-ttu-id="e029d-711">[Executar arquivos de script Transact-SQL usando sqlcmd](../relational-databases/scripting/sqlcmd-run-transact-sql-script-files.md) </span><span class="sxs-lookup"><span data-stu-id="e029d-711">[Run Transact-SQL Script Files Using sqlcmd](../relational-databases/scripting/sqlcmd-run-transact-sql-script-files.md) </span></span>  
 <span data-ttu-id="e029d-712">[Usar o utilitário sqlcmd](../relational-databases/scripting/sqlcmd-use-the-utility.md) </span><span class="sxs-lookup"><span data-stu-id="e029d-712">[Use the sqlcmd Utility](../relational-databases/scripting/sqlcmd-use-the-utility.md) </span></span>  
 <span data-ttu-id="e029d-713">[Usar sqlcmd com variáveis de script](../relational-databases/scripting/sqlcmd-use-with-scripting-variables.md) </span><span class="sxs-lookup"><span data-stu-id="e029d-713">[Use sqlcmd with Scripting Variables](../relational-databases/scripting/sqlcmd-use-with-scripting-variables.md) </span></span>  
 <span data-ttu-id="e029d-714">[Conectar-se ao mecanismo de banco de dados com sqlcmd](../relational-databases/scripting/sqlcmd-connect-to-the-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="e029d-714">[Connect to the Database Engine With sqlcmd](../relational-databases/scripting/sqlcmd-connect-to-the-database-engine.md) </span></span>  
 <span data-ttu-id="e029d-715">[Editar scripts SQLCMD com o Editor de Consultas](../relational-databases/scripting/edit-sqlcmd-scripts-with-query-editor.md) </span><span class="sxs-lookup"><span data-stu-id="e029d-715">[Edit SQLCMD Scripts with Query Editor](../relational-databases/scripting/edit-sqlcmd-scripts-with-query-editor.md) </span></span>  
 <span data-ttu-id="e029d-716">[Gerenciar etapas de trabalho](../ssms/agent/manage-job-steps.md) </span><span class="sxs-lookup"><span data-stu-id="e029d-716">[Manage Job Steps](../ssms/agent/manage-job-steps.md) </span></span>  
 [<span data-ttu-id="e029d-717">Criar uma etapa de trabalho CmdExec</span><span class="sxs-lookup"><span data-stu-id="e029d-717">Create a CmdExec Job Step</span></span>](../ssms/agent/create-a-cmdexec-job-step.md)  
  
  
