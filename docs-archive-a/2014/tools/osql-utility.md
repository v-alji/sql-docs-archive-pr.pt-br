---
title: Utilitário osql | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- statements [SQL Server], command prompt
- QUIT command
- Transact-SQL statements, command prompt
- EXIT command
- operating systems [SQL Server], commands
- osql utility [SQL Server]
- stored procedures [SQL Server], command prompt
- scripts [SQL Server], command prompt
- RESET command
- GO command
- command prompt utilities [SQL Server], osql
- CTRL+C command
ms.assetid: cf530d9e-0609-4528-8975-ab8e08e40b9a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 95782afe0de8567781316e3478d04a090f968ed5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678424"
---
# <a name="osql-utility"></a><span data-ttu-id="89f46-102">Utilitário osql</span><span class="sxs-lookup"><span data-stu-id="89f46-102">osql Utility</span></span>
  <span data-ttu-id="89f46-103">O utilitário **osql** permite inserir instruções [!INCLUDE[tsql](../includes/tsql-md.md)] , procedimentos de sistema e arquivos de script.</span><span class="sxs-lookup"><span data-stu-id="89f46-103">The **osql** utility allows you to enter [!INCLUDE[tsql](../includes/tsql-md.md)] statements, system procedures, and script files.</span></span> <span data-ttu-id="89f46-104">Esse utilitário usa o ODBC para comunicar-se com o servidor.</span><span class="sxs-lookup"><span data-stu-id="89f46-104">This utility uses ODBC to communicate with the server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="89f46-105">Esse recurso será removido em uma versão futura do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89f46-105">This feature will be removed in a future version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="89f46-106">Evite usar esse recurso em novo trabalho de desenvolvimento e planeje modificar os aplicativos que utilizam o recurso atualmente.</span><span class="sxs-lookup"><span data-stu-id="89f46-106">Avoid using this feature in new development work, and plan to modify applications that currently use the feature.</span></span> <span data-ttu-id="89f46-107">Use **sqlcmd** em vez disso.</span><span class="sxs-lookup"><span data-stu-id="89f46-107">Use **sqlcmd** instead.</span></span> <span data-ttu-id="89f46-108">Para saber mais, confira [sqlcmd Utility](sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="89f46-108">For more information, see [sqlcmd Utility](sqlcmd-utility.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89f46-109">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="89f46-109">Syntax</span></span>  
  
```  
  
      osql  
[-?] |  
[-L] |  
[  
  {  
     {-Ulogin_id [-Ppassword]} | -E }  
     [-Sserver_name[\instance_name]] [-Hwksta_name] [-ddb_name]  
     [-ltime_out] [-ttime_out] [-hheaders]  
     [-scol_separator] [-wcolumn_width] [-apacket_size]  
     [-e] [-I] [-D data_source_name]  
     [-ccmd_end] [-q "query"] [-Q"query"]  
     [-n] [-merror_level] [-r {0 | 1}]  
     [-iinput_file] [-ooutput_file] [-p]  
     [-b] [-u] [-R] [-O]  
]  
```  
  
## <a name="arguments"></a><span data-ttu-id="89f46-110">Argumentos</span><span class="sxs-lookup"><span data-stu-id="89f46-110">Arguments</span></span>  
 <span data-ttu-id="89f46-111">**-?**</span><span class="sxs-lookup"><span data-stu-id="89f46-111">**-?**</span></span>  
 <span data-ttu-id="89f46-112">Exibe o resumo da sintaxe de opções **osql** .</span><span class="sxs-lookup"><span data-stu-id="89f46-112">Displays the syntax summary of **osql** switches.</span></span>  
  
 <span data-ttu-id="89f46-113">**-L**</span><span class="sxs-lookup"><span data-stu-id="89f46-113">**-L**</span></span>  
 <span data-ttu-id="89f46-114">Lista os servidores configurados localmente e os nomes dos servidores que estão transmitindo na rede.</span><span class="sxs-lookup"><span data-stu-id="89f46-114">Lists the locally configured servers and the names of the servers broadcasting on the network.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89f46-115">Devido à natureza da transmissão em redes, o **osql** pode não receber a tempo uma resposta de todos os servidores.</span><span class="sxs-lookup"><span data-stu-id="89f46-115">Due to the nature of broadcasting on networks, **osql** may not receive a timely response from all servers.</span></span> <span data-ttu-id="89f46-116">Assim, a lista de servidores retornada pode variar para cada invocação dessa opção.</span><span class="sxs-lookup"><span data-stu-id="89f46-116">Therefore the list of servers returned may vary for each invocation of this option.</span></span>  
  
 <span data-ttu-id="89f46-117">**-U** _login_id_</span><span class="sxs-lookup"><span data-stu-id="89f46-117">**-U** _login_id_</span></span>  
 <span data-ttu-id="89f46-118">É a identificação de logon do usuário.</span><span class="sxs-lookup"><span data-stu-id="89f46-118">Is the user login ID.</span></span> <span data-ttu-id="89f46-119">IDs de logon diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="89f46-119">Login IDs are case-sensitive.</span></span>  
  
 <span data-ttu-id="89f46-120">**-P** _password_</span><span class="sxs-lookup"><span data-stu-id="89f46-120">**-P** _password_</span></span>  
 <span data-ttu-id="89f46-121">É uma senha especificada pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="89f46-121">Is a user-specified password.</span></span> <span data-ttu-id="89f46-122">Se a opção **-P** não for usada, o **osql** solicitará a senha.</span><span class="sxs-lookup"><span data-stu-id="89f46-122">If the **-P** option is not used, **osql** prompts for a password.</span></span> <span data-ttu-id="89f46-123">Se a opção **-P** for usada ao término do prompt de comando sem uma senha, **osql** usará a senha padrão (NULL).</span><span class="sxs-lookup"><span data-stu-id="89f46-123">If the **-P** option is used at the end of the command prompt without any password, **osql** uses the default password (NULL).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="89f46-124">Não use uma senha em branco.</span><span class="sxs-lookup"><span data-stu-id="89f46-124">Do not use a blank password.</span></span> <span data-ttu-id="89f46-125">Use uma senha forte.</span><span class="sxs-lookup"><span data-stu-id="89f46-125">Use a strong password.</span></span> <span data-ttu-id="89f46-126">Para saber mais, confira [Strong Passwords](../relational-databases/security/strong-passwords.md).</span><span class="sxs-lookup"><span data-stu-id="89f46-126">For more information, see [Strong Passwords](../relational-databases/security/strong-passwords.md).</span></span>  
  
 <span data-ttu-id="89f46-127">As senhas diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="89f46-127">Passwords are case-sensitive.</span></span>  
  
 <span data-ttu-id="89f46-128">A variável de ambiente OSQLPASSWORD permite definir uma senha padrão para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="89f46-128">The OSQLPASSWORD environment variable allows you to set a default password for the current session.</span></span> <span data-ttu-id="89f46-129">Assim, senhas não têm de ser codificadas em arquivos em lote.</span><span class="sxs-lookup"><span data-stu-id="89f46-129">Therefore, you do not have to hard code a password into batch files.</span></span>  
  
 <span data-ttu-id="89f46-130">Se você não especificar uma senha com a opção **-P** , **osql** verificará primeiro a variável OSQLPASSWORD.</span><span class="sxs-lookup"><span data-stu-id="89f46-130">If you do not specify a password with the **-P** option, **osql** first checks for the OSQLPASSWORD variable.</span></span> <span data-ttu-id="89f46-131">Se nenhum valor for definido, o **osql** usará a senha padrão, NULL.</span><span class="sxs-lookup"><span data-stu-id="89f46-131">If no value is set, **osql** uses the default password, NULL.</span></span> <span data-ttu-id="89f46-132">O exemplo seguinte define a variável OSQLPASSWORD em um prompt de comando e então acessa o utilitário **osql** :</span><span class="sxs-lookup"><span data-stu-id="89f46-132">The following example sets the OSQLPASSWORD variable at a command prompt and then accesses the **osql** utility:</span></span>  
  
```  
C:\>SET OSQLPASSWORD=abracadabra  
C:\>osql   
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="89f46-133">Para mascarar a senha, não especifique a opção **-P** juntamente com a opção **-U** .</span><span class="sxs-lookup"><span data-stu-id="89f46-133">To mask your password, do not specify the **-P** option along with the **-U** option.</span></span> <span data-ttu-id="89f46-134">Em vez disso, depois de especificar o **osql** juntamente com a opção **-U** e outras opções (não especificar **-P**), pressione ENTER e o **osql** solicitará uma senha.</span><span class="sxs-lookup"><span data-stu-id="89f46-134">Instead, after specifying **osql** along with the **-U** option and other switches (do not specify **-P**), press ENTER, and **osql** will prompt you for a password.</span></span> <span data-ttu-id="89f46-135">Esse método garante que sua senha será mascarada quando for inserida.</span><span class="sxs-lookup"><span data-stu-id="89f46-135">This method ensures that your password will be masked when it is entered.</span></span>  
  
 <span data-ttu-id="89f46-136">**-E**</span><span class="sxs-lookup"><span data-stu-id="89f46-136">**-E**</span></span>  
 <span data-ttu-id="89f46-137">Usa uma conexão confiável em vez de pedir uma senha.</span><span class="sxs-lookup"><span data-stu-id="89f46-137">Uses a trusted connection instead of requesting a password.</span></span>  
  
 <span data-ttu-id="89f46-138">**-S** _server_name_[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="89f46-138">**-S** _server_name_[ **\\**_instance_name_]</span></span>  
 <span data-ttu-id="89f46-139">Especifica uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] a qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="89f46-139">Specifies the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to connect to.</span></span> <span data-ttu-id="89f46-140">Especifica *server_name* para a conexão com a instância padrão do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] nesse servidor.</span><span class="sxs-lookup"><span data-stu-id="89f46-140">Specify *server_name* to connect to the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on that server.</span></span> <span data-ttu-id="89f46-141">Especifique _server_name_ **\\** _instance_name_ para se conectar a uma instância nomeada do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] nesse servidor.</span><span class="sxs-lookup"><span data-stu-id="89f46-141">Specify _server_name_**\\**_instance_name_ to connect to a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on that server.</span></span> <span data-ttu-id="89f46-142">Se nenhum servidor for especificado, o **osql** se conectará à instância padrão do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] no computador local.</span><span class="sxs-lookup"><span data-stu-id="89f46-142">If no server is specified, **osql** connects to the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on the local computer.</span></span> <span data-ttu-id="89f46-143">Essa opção é obrigatória quando o **osql** é executado de um computador remoto na rede.</span><span class="sxs-lookup"><span data-stu-id="89f46-143">This option is required when executing **osql** from a remote computer on the network.</span></span>  
  
 <span data-ttu-id="89f46-144">**-H** _wksta_name_</span><span class="sxs-lookup"><span data-stu-id="89f46-144">**-H** _wksta_name_</span></span>  
 <span data-ttu-id="89f46-145">É um nome de estação de trabalho.</span><span class="sxs-lookup"><span data-stu-id="89f46-145">Is a workstation name.</span></span> <span data-ttu-id="89f46-146">O nome de estação de trabalho é armazenado em **sysprocesses.hostname** e exibido por **sp_who**.</span><span class="sxs-lookup"><span data-stu-id="89f46-146">The workstation name is stored in **sysprocesses.hostname** and is displayed by **sp_who**.</span></span> <span data-ttu-id="89f46-147">Se essa opção não for especificada, o nome do computador atual será presumido.</span><span class="sxs-lookup"><span data-stu-id="89f46-147">If this option is not specified, the current computer name is assumed.</span></span>  
  
 <span data-ttu-id="89f46-148">**-d** _db_name_</span><span class="sxs-lookup"><span data-stu-id="89f46-148">**-d** _db_name_</span></span>  
 <span data-ttu-id="89f46-149">Emite uma instrução USE *db_name* quando **osql**é iniciado.</span><span class="sxs-lookup"><span data-stu-id="89f46-149">Issues a USE *db_name* statement when **osql**is started.</span></span>  
  
 <span data-ttu-id="89f46-150">**-l** _time_out_</span><span class="sxs-lookup"><span data-stu-id="89f46-150">**-l** _time_out_</span></span>  
 <span data-ttu-id="89f46-151">Especifica o número de segundos antes de um logon do **osql** expirar. O tempo limite padrão de logon do **osql** é de oito segundos.</span><span class="sxs-lookup"><span data-stu-id="89f46-151">Specifies the number of seconds before an **osql** login times out. The default time-out for login to **osql** is eight seconds.</span></span>  
  
 <span data-ttu-id="89f46-152">**-t** _time_out_</span><span class="sxs-lookup"><span data-stu-id="89f46-152">**-t** _time_out_</span></span>  
 <span data-ttu-id="89f46-153">Especifica o número de segundos antes de um comando expirar. Se não for especificado um valor de *time_out* , os comandos não vão atingir o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="89f46-153">Specifies the number of seconds before a command times out. If a *time_out* value is not specified, commands do not time out.</span></span>  
  
 <span data-ttu-id="89f46-154">**-h** _headers_</span><span class="sxs-lookup"><span data-stu-id="89f46-154">**-h** _headers_</span></span>  
 <span data-ttu-id="89f46-155">Especifica o número de linhas a imprimir entre cabeçalhos de coluna.</span><span class="sxs-lookup"><span data-stu-id="89f46-155">Specifies the number of rows to print between column headings.</span></span> <span data-ttu-id="89f46-156">O padrão é imprimir títulos uma vez para cada conjunto de resultados de consulta.</span><span class="sxs-lookup"><span data-stu-id="89f46-156">The default is to print headings one time for each set of query results.</span></span> <span data-ttu-id="89f46-157">Use -1 para especificar que nenhum cabeçalho será impresso.</span><span class="sxs-lookup"><span data-stu-id="89f46-157">Use -1 to specify that no headers will be printed.</span></span> <span data-ttu-id="89f46-158">Se -1 for usado, não deverá haver nenhum espaço entre o parâmetro e a configuração ( **-h-1**, não **-h -1**).</span><span class="sxs-lookup"><span data-stu-id="89f46-158">If -1 is used, there must be no space between the parameter and the setting (**-h-1**, not **-h -1**).</span></span>  
  
 <span data-ttu-id="89f46-159">**-s** _col_separator_</span><span class="sxs-lookup"><span data-stu-id="89f46-159">**-s** _col_separator_</span></span>  
 <span data-ttu-id="89f46-160">Especifica o caractere do separador de colunas que, por padrão, é um espaço em branco.</span><span class="sxs-lookup"><span data-stu-id="89f46-160">Specifies the column-separator character, which is a blank space by default.</span></span> <span data-ttu-id="89f46-161">Para usar caracteres que têm significado especial para o sistema operacional (por exemplo, |; & \< > ), coloque o caractere entre aspas duplas (").</span><span class="sxs-lookup"><span data-stu-id="89f46-161">To use characters that have special meaning to the operating system (for example, | ; & \< >), enclose the character in double quotation marks (").</span></span>  
  
 <span data-ttu-id="89f46-162">**-w** _column_width_</span><span class="sxs-lookup"><span data-stu-id="89f46-162">**-w** _column_width_</span></span>  
 <span data-ttu-id="89f46-163">Permite ao usuário definir a largura da tela de saída.</span><span class="sxs-lookup"><span data-stu-id="89f46-163">Allows the user to set the screen width for output.</span></span> <span data-ttu-id="89f46-164">O padrão é 80 caracteres.</span><span class="sxs-lookup"><span data-stu-id="89f46-164">The default is 80 characters.</span></span> <span data-ttu-id="89f46-165">Quando uma linha de saída alcança sua largura de tela máxima, ela é quebrada em várias linhas.</span><span class="sxs-lookup"><span data-stu-id="89f46-165">When an output line has reached its maximum screen width, it is broken into multiple lines.</span></span>  
  
 <span data-ttu-id="89f46-166">**-a** _packet_size_</span><span class="sxs-lookup"><span data-stu-id="89f46-166">**-a** _packet_size_</span></span>  
 <span data-ttu-id="89f46-167">Permite solicitar um pacote de tamanho diferente.</span><span class="sxs-lookup"><span data-stu-id="89f46-167">Allows you to request a different-sized packet.</span></span> <span data-ttu-id="89f46-168">Os valores válidos para *packet_size* são 512 a 65.535.</span><span class="sxs-lookup"><span data-stu-id="89f46-168">The valid values for *packet_size* are 512 through 65535.</span></span> <span data-ttu-id="89f46-169">O valor padrão **osql** é o padrão do servidor.</span><span class="sxs-lookup"><span data-stu-id="89f46-169">The default value **osql** is the server default.</span></span> <span data-ttu-id="89f46-170">Um tamanho de pacote maior pode aumentar o desempenho na execução de scripts maiores, em que a quantidade de instruções SQL entre comandos GO é substancial.</span><span class="sxs-lookup"><span data-stu-id="89f46-170">Increased packet size can enhance performance on larger script execution where the amount of SQL statements between GO commands is substantial.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="89f46-171">indicam que 8192 geralmente é a configuração mais rápida para operações de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="89f46-171">testing indicates that 8192 is typically the fastest setting for bulk copy operations.</span></span> <span data-ttu-id="89f46-172">Um tamanho de pacote maior pode ser solicitado, mas o **osql** assumirá como padrão o padrão do servidor se a solicitação não puder ser atendida.</span><span class="sxs-lookup"><span data-stu-id="89f46-172">A larger packet size can be requested, but **osql** defaults to the server default if the request cannot be granted.</span></span>  
  
 <span data-ttu-id="89f46-173">**-e**</span><span class="sxs-lookup"><span data-stu-id="89f46-173">**-e**</span></span>  
 <span data-ttu-id="89f46-174">Duplica a entrada.</span><span class="sxs-lookup"><span data-stu-id="89f46-174">Echoes input.</span></span>  
  
 <span data-ttu-id="89f46-175">**-I**</span><span class="sxs-lookup"><span data-stu-id="89f46-175">**-I**</span></span>  
 <span data-ttu-id="89f46-176">Ativa a opção de conexão QUOTED_IDENTIFIER.</span><span class="sxs-lookup"><span data-stu-id="89f46-176">Sets the QUOTED_IDENTIFIER connection option on.</span></span>  
  
 <span data-ttu-id="89f46-177">**-D** _data_source_name_</span><span class="sxs-lookup"><span data-stu-id="89f46-177">**-D** _data_source_name_</span></span>  
 <span data-ttu-id="89f46-178">Conecta-se a uma fonte de dados ODBC que é definida usando o driver ODBC do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89f46-178">Connects to an ODBC data source that is defined using the ODBC driver for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="89f46-179">A conexão **osql** usa as opções especificadas na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="89f46-179">The **osql** connection uses the options specified in the data source.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89f46-180">Essa opção não trabalha com fontes de dados definidas para outros drivers.</span><span class="sxs-lookup"><span data-stu-id="89f46-180">This option does not work with data sources defined for other drivers.</span></span>  
  
 <span data-ttu-id="89f46-181">**-c** _cmd_end_</span><span class="sxs-lookup"><span data-stu-id="89f46-181">**-c** _cmd_end_</span></span>  
 <span data-ttu-id="89f46-182">Especifica o terminador de comando.</span><span class="sxs-lookup"><span data-stu-id="89f46-182">Specifies the command terminator.</span></span> <span data-ttu-id="89f46-183">Por padrão, comandos são encerrados e enviados ao [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] se GO for inserido sozinho em uma linha.</span><span class="sxs-lookup"><span data-stu-id="89f46-183">By default, commands are terminated and sent to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] by entering GO on a line by itself.</span></span> <span data-ttu-id="89f46-184">Quando você redefinir o terminador de comando, não use palavras reservadas do [!INCLUDE[tsql](../includes/tsql-md.md)] nem caracteres que tenham significado especial para o sistema operacional, sejam ou não precedidos por uma barra invertida.</span><span class="sxs-lookup"><span data-stu-id="89f46-184">When you reset the command terminator, do not use [!INCLUDE[tsql](../includes/tsql-md.md)] reserved words or characters that have special meaning to the operating system, whether preceded by a backslash or not.</span></span>  
  
 <span data-ttu-id="89f46-185">**-q "** _query_ **"**</span><span class="sxs-lookup"><span data-stu-id="89f46-185">**-q "** _query_ **"**</span></span>  
 <span data-ttu-id="89f46-186">Executa uma consulta quando o **osql** é iniciado, mas não encerra o **osql** quando a consulta é concluída.</span><span class="sxs-lookup"><span data-stu-id="89f46-186">Executes a query when **osql** starts, but does not exit **osql** when the query completes.</span></span> <span data-ttu-id="89f46-187">(Observe que a instrução de consulta não deve incluir a instrução GO).</span><span class="sxs-lookup"><span data-stu-id="89f46-187">(Note that the query statement should not include GO).</span></span> <span data-ttu-id="89f46-188">Se você emitir uma consulta de um arquivo em lote, use %variáveis ou %variáveis% de ambiente.</span><span class="sxs-lookup"><span data-stu-id="89f46-188">If you issue a query from a batch file, use %variables, or environment %variables%.</span></span> <span data-ttu-id="89f46-189">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="89f46-189">For example:</span></span>  
  
```  
SET table=sys.objects  
osql -E -q "select name, object_id from %table%"  
```  
  
 <span data-ttu-id="89f46-190">Coloque a consulta entre aspas duplas e qualquer coisa incorporada na consulta entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="89f46-190">Use double quotation marks around the query and single quotation marks around anything embedded in the query.</span></span>  
  
 <span data-ttu-id="89f46-191">**-Q"** _query_ **"**</span><span class="sxs-lookup"><span data-stu-id="89f46-191">**-Q"** _query_ **"**</span></span>  
 <span data-ttu-id="89f46-192">Executa uma consulta e imediatamente encerra o **osql**.</span><span class="sxs-lookup"><span data-stu-id="89f46-192">Executes a query and immediately exits **osql**.</span></span> <span data-ttu-id="89f46-193">Coloque a consulta entre aspas duplas e qualquer coisa incorporada na consulta entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="89f46-193">Use double quotation marks around the query and single quotation marks around anything embedded in the query.</span></span>  
  
 <span data-ttu-id="89f46-194">**-n**</span><span class="sxs-lookup"><span data-stu-id="89f46-194">**-n**</span></span>  
 <span data-ttu-id="89f46-195">Remove a numeração e o símbolo de prompt (>) das linhas de entrada.</span><span class="sxs-lookup"><span data-stu-id="89f46-195">Removes numbering and the prompt symbol (>) from input lines.</span></span>  
  
 <span data-ttu-id="89f46-196">**-m** _error_level_</span><span class="sxs-lookup"><span data-stu-id="89f46-196">**-m** _error_level_</span></span>  
 <span data-ttu-id="89f46-197">Personaliza a exibição de mensagens de erro.</span><span class="sxs-lookup"><span data-stu-id="89f46-197">Customizes the display of error messages.</span></span> <span data-ttu-id="89f46-198">São exibidos o número da mensagem, o estado e o nível de erros com o nível de severidade especificado ou superior.</span><span class="sxs-lookup"><span data-stu-id="89f46-198">The message number, state, and error level are displayed for errors of the specified severity level or higher.</span></span> <span data-ttu-id="89f46-199">Nada é exibido para erros de níveis abaixo do nível especificado.</span><span class="sxs-lookup"><span data-stu-id="89f46-199">Nothing is displayed for errors of levels lower than the specified level.</span></span> <span data-ttu-id="89f46-200">Use **-1** para especificar que todos os cabeçalhos retornem com mensagens, até mesmo mensagens informativas.</span><span class="sxs-lookup"><span data-stu-id="89f46-200">Use **-1** to specify that all headers are returned with messages, even informational messages.</span></span> <span data-ttu-id="89f46-201">Se **-1**for usado, não deverá haver espaço entre o parâmetro e a configuração ( **-m-1**, não **-m -1**).</span><span class="sxs-lookup"><span data-stu-id="89f46-201">If using **-1**, there must be no space between the parameter and the setting (**-m-1**, not **-m -1**).</span></span>  
  
 <span data-ttu-id="89f46-202">**-r** { **0**| **1**}</span><span class="sxs-lookup"><span data-stu-id="89f46-202">**-r** { **0**| **1**}</span></span>  
 <span data-ttu-id="89f46-203">Redireciona a saída da mensagem para a tela (**stderr**).</span><span class="sxs-lookup"><span data-stu-id="89f46-203">Redirects message output to the screen (**stderr**).</span></span> <span data-ttu-id="89f46-204">Se você não especificar um parâmetro ou especificar **0**, serão redirecionadas somente mensagens de erro com nível de severidade 11 ou superior.</span><span class="sxs-lookup"><span data-stu-id="89f46-204">If you do not specify a parameter, or if you specify **0**, only error messages with a severity level 11 or higher are redirected.</span></span> <span data-ttu-id="89f46-205">Se você especificar **1**, serão redirecionadas todas as saídas da mensagem, incluindo “print”.</span><span class="sxs-lookup"><span data-stu-id="89f46-205">If you specify **1**, all message output (including "print") is redirected.</span></span>  
  
 <span data-ttu-id="89f46-206">**-i** _input_file_</span><span class="sxs-lookup"><span data-stu-id="89f46-206">**-i** _input_file_</span></span>  
 <span data-ttu-id="89f46-207">Identifica o arquivo que contém um lote de instruções SQL ou procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="89f46-207">Identifies the file that contains a batch of SQL statements or stored procedures.</span></span> <span data-ttu-id="89f46-208">O operador de comparação menor que ( **\<** ) pode ser usado no lugar de **-i**.</span><span class="sxs-lookup"><span data-stu-id="89f46-208">The less than (**\<**) comparison operator can be used in place of **-i**.</span></span>  
  
 <span data-ttu-id="89f46-209">**-o** _output_file_</span><span class="sxs-lookup"><span data-stu-id="89f46-209">**-o** _output_file_</span></span>  
 <span data-ttu-id="89f46-210">Identifica o arquivo que recebe a saída do **osql**.</span><span class="sxs-lookup"><span data-stu-id="89f46-210">Identifies the file that receives output from **osql**.</span></span> <span data-ttu-id="89f46-211">O operador de comparação maior que ( **>** ) pode ser usado no lugar de **-o**.</span><span class="sxs-lookup"><span data-stu-id="89f46-211">The greater than (**>**) comparison operator can be used in place of **-o**.</span></span>  
  
 <span data-ttu-id="89f46-212">Se *input_file* não for Unicode e **-u** não for especificado, *output_file* será armazenado no formato OEM.</span><span class="sxs-lookup"><span data-stu-id="89f46-212">If *input_file* is not Unicode and **-u** is not specified, *output_file* is stored in OEM format.</span></span> <span data-ttu-id="89f46-213">Se *input_file* for Unicode ou **-u** for especificado, *output_file* será armazenado em formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="89f46-213">If *input_file* is Unicode or **-u** is specified, *output_file* is stored in Unicode format.</span></span>  
  
 <span data-ttu-id="89f46-214">**-p**</span><span class="sxs-lookup"><span data-stu-id="89f46-214">**-p**</span></span>  
 <span data-ttu-id="89f46-215">Imprime estatísticas de desempenho.</span><span class="sxs-lookup"><span data-stu-id="89f46-215">Prints performance statistics.</span></span>  
  
 <span data-ttu-id="89f46-216">**-b**</span><span class="sxs-lookup"><span data-stu-id="89f46-216">**-b**</span></span>  
 <span data-ttu-id="89f46-217">Especifica que o **osql** é encerrado e retorna um valor DOS ERRORLEVEL em caso de erro.</span><span class="sxs-lookup"><span data-stu-id="89f46-217">Specifies that **osql** exits and returns a DOS ERRORLEVEL value when an error occurs.</span></span> <span data-ttu-id="89f46-218">O valor retornado à variável DOS ERRORLEVEL será 1 quando a mensagem de erro do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tiver um nível de severidade de 11 ou superior, caso contrário, o valor retornado será 0.</span><span class="sxs-lookup"><span data-stu-id="89f46-218">The value returned to the DOS ERRORLEVEL variable is 1 when the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] error message has a severity of 11 or greater; otherwise, the value returned is 0.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="89f46-219">Arquivos em lote do MS-DOS podem testar o valor de DOS ERRORLEVEL e tratar o erro adequadamente.</span><span class="sxs-lookup"><span data-stu-id="89f46-219">MS-DOS batch files can test the value of DOS ERRORLEVEL and handle the error appropriately.</span></span>  
  
 <span data-ttu-id="89f46-220">**-u**</span><span class="sxs-lookup"><span data-stu-id="89f46-220">**-u**</span></span>  
 <span data-ttu-id="89f46-221">Especificar que *output_file* será armazenado em formato Unicode, independentemente do formato de *input_file*.</span><span class="sxs-lookup"><span data-stu-id="89f46-221">Specifies that *output_file* is stored in Unicode format, regardless of the format of the *input_file*.</span></span>  
  
 <span data-ttu-id="89f46-222">**-R**</span><span class="sxs-lookup"><span data-stu-id="89f46-222">**-R**</span></span>  
 <span data-ttu-id="89f46-223">Especifica que o driver ODBC do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] usa configurações de cliente ao converter dados de moeda, data e hora em dados de caractere.</span><span class="sxs-lookup"><span data-stu-id="89f46-223">Specifies that the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ODBC driver use client settings when converting currency, date, and time data to character data.</span></span>  
  
 <span data-ttu-id="89f46-224">**-O**</span><span class="sxs-lookup"><span data-stu-id="89f46-224">**-O**</span></span>  
 <span data-ttu-id="89f46-225">Especifica que certos recursos do **osql** sejam desativados para corresponder ao comportamento de versões anteriores do **isql**.</span><span class="sxs-lookup"><span data-stu-id="89f46-225">Specifies that certain **osql** features be deactivated to match the behavior of earlier versions of **isql**.</span></span> <span data-ttu-id="89f46-226">Estes recursos são desativados:</span><span class="sxs-lookup"><span data-stu-id="89f46-226">These features are deactivated:</span></span>  
  
-   <span data-ttu-id="89f46-227">Processamento em lote de EOF</span><span class="sxs-lookup"><span data-stu-id="89f46-227">EOF batch processing</span></span>  
  
-   <span data-ttu-id="89f46-228">Escalonamento automático da largura do console</span><span class="sxs-lookup"><span data-stu-id="89f46-228">Automatic console width scaling</span></span>  
  
-   <span data-ttu-id="89f46-229">Mensagens largas</span><span class="sxs-lookup"><span data-stu-id="89f46-229">Wide messages</span></span>  
  
 <span data-ttu-id="89f46-230">Também define o valor DOS ERRORLEVEL padrão como -1.</span><span class="sxs-lookup"><span data-stu-id="89f46-230">It also sets the default DOS ERRORLEVEL value to -1.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89f46-231">As opções **-n**, **-O** e **-D** já não têm suporte do **osql**.</span><span class="sxs-lookup"><span data-stu-id="89f46-231">The **-n**, **-O** and **-D** options are no longer supported by **osql**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89f46-232">Comentários</span><span class="sxs-lookup"><span data-stu-id="89f46-232">Remarks</span></span>  
 <span data-ttu-id="89f46-233">O utilitário **osql** é iniciado diretamente do sistema operacional com as opções que diferenciam maiúsculas de minúsculas listadas aqui.</span><span class="sxs-lookup"><span data-stu-id="89f46-233">The **osql** utility is started directly from the operating system with the case-sensitive options listed here.</span></span> <span data-ttu-id="89f46-234">Depois que o **osql**é iniciado, ele aceita instruções SQL e as envia interativamente ao [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="89f46-234">After **osql**starts, it accepts SQL statements and sends them to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] interactively.</span></span> <span data-ttu-id="89f46-235">Os resultados são formatados e exibidos na tela (**stdout**).</span><span class="sxs-lookup"><span data-stu-id="89f46-235">The results are formatted and displayed on the screen (**stdout**).</span></span> <span data-ttu-id="89f46-236">Use QUIT ou EXIT para sair do **osql**.</span><span class="sxs-lookup"><span data-stu-id="89f46-236">Use QUIT or EXIT to exit from **osql**.</span></span>  
  
 <span data-ttu-id="89f46-237">Se você não especificar um nome de usuário ao iniciar o **osql**, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o verificará as variáveis de ambiente e as usará, por exemplo, **OSQLUSER = ( *`user`* )** ou **OSQLSERVER = ( *`server`* )**.</span><span class="sxs-lookup"><span data-stu-id="89f46-237">If you do not specify a user name when you start **osql**, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] checks for the environment variables and uses those, for example, **osqluser=(*`user`*)** or **osqlserver=(*`server`*)**.</span></span> <span data-ttu-id="89f46-238">Se nenhuma variável de ambiente for definida, o nome de usuário da estação de trabalho será usado.</span><span class="sxs-lookup"><span data-stu-id="89f46-238">If no environment variables are set, the workstation user name is used.</span></span> <span data-ttu-id="89f46-239">Se você não especificar um servidor, o nome da estação de trabalho será usado.</span><span class="sxs-lookup"><span data-stu-id="89f46-239">If you do not specify a server, the name of the workstation is used.</span></span>  
  
 <span data-ttu-id="89f46-240">Se as opções **-U** ou **-P** não forem usadas, o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tentará conectar usando o Modo de Autenticação do [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="89f46-240">If neither the **-U** or **-P** options are used, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] attempts to connect using [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication Mode.</span></span> <span data-ttu-id="89f46-241">A autenticação baseia-se na conta do [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows do usuário que está executando o **osql**.</span><span class="sxs-lookup"><span data-stu-id="89f46-241">Authentication is based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows account of the user running **osql**.</span></span>  
  
 <span data-ttu-id="89f46-242">O utilitário **osql** usa a API ODBC.</span><span class="sxs-lookup"><span data-stu-id="89f46-242">The **osql** utility uses the ODBC API.</span></span> <span data-ttu-id="89f46-243">O utilitário usa as configurações padrão do driver ODBC do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para as opções de conexão ISO do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="89f46-243">The utility uses the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ODBC driver default settings for the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ISO connection options.</span></span> <span data-ttu-id="89f46-244">Para obter mais informações, consulte Efeitos de Opções ANSI.</span><span class="sxs-lookup"><span data-stu-id="89f46-244">For more information, see Effects of ANSI Options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89f46-245">O utilitário **osql** não dá suporte a tipos de dados CLR definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="89f46-245">The **osql** utility does not support CLR user-defined data types.</span></span> <span data-ttu-id="89f46-246">Para processar esses tipos de dados, você deve usar o utilitário **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="89f46-246">To process these data types, you must use the **sqlcmd** utility.</span></span> <span data-ttu-id="89f46-247">Para saber mais, confira [sqlcmd Utility](sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="89f46-247">For more information, see [sqlcmd Utility](sqlcmd-utility.md).</span></span>  
  
## <a name="osql-commands"></a><span data-ttu-id="89f46-248">Comandos OSQL</span><span class="sxs-lookup"><span data-stu-id="89f46-248">OSQL Commands</span></span>  
 <span data-ttu-id="89f46-249">Além das instruções [!INCLUDE[tsql](../includes/tsql-md.md)] dentro do **osql**, os comandos a seguir também estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="89f46-249">In addition to [!INCLUDE[tsql](../includes/tsql-md.md)] statements within **osql**, these commands are also available.</span></span>  
  
|<span data-ttu-id="89f46-250">Comando</span><span class="sxs-lookup"><span data-stu-id="89f46-250">Command</span></span>|<span data-ttu-id="89f46-251">Descrição</span><span class="sxs-lookup"><span data-stu-id="89f46-251">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="89f46-252">GO</span><span class="sxs-lookup"><span data-stu-id="89f46-252">GO</span></span>|<span data-ttu-id="89f46-253">Executa todas as instruções inseridas depois do último GO.</span><span class="sxs-lookup"><span data-stu-id="89f46-253">Executes all statements entered after the last GO.</span></span>|  
|<span data-ttu-id="89f46-254">RESET</span><span class="sxs-lookup"><span data-stu-id="89f46-254">RESET</span></span>|<span data-ttu-id="89f46-255">Apaga as instruções inseridas.</span><span class="sxs-lookup"><span data-stu-id="89f46-255">Clears any statements you have entered.</span></span>|  
|<span data-ttu-id="89f46-256">QUIT ou EXIT( )</span><span class="sxs-lookup"><span data-stu-id="89f46-256">QUIT or EXIT( )</span></span>|<span data-ttu-id="89f46-257">Sai do **osql**.</span><span class="sxs-lookup"><span data-stu-id="89f46-257">Exits from **osql**.</span></span>|  
|<span data-ttu-id="89f46-258">CTRL+C</span><span class="sxs-lookup"><span data-stu-id="89f46-258">CTRL+C</span></span>|<span data-ttu-id="89f46-259">Finaliza uma consulta sem sair do **osql**.</span><span class="sxs-lookup"><span data-stu-id="89f46-259">Ends a query without exiting from **osql**.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="89f46-260">Os comandos !!</span><span class="sxs-lookup"><span data-stu-id="89f46-260">The !!</span></span> <span data-ttu-id="89f46-261">e ED não têm mais suporte no **osql**.</span><span class="sxs-lookup"><span data-stu-id="89f46-261">and ED commands are no longer supported by **osql**.</span></span>  
  
 <span data-ttu-id="89f46-262">Os terminadores de comando GO (por padrão), RESET EXIT, QUIT e CTRL+C só serão reconhecidos se forem exibidos no início de uma linha, imediatamente após o prompt do **osql** .</span><span class="sxs-lookup"><span data-stu-id="89f46-262">The command terminators GO (by default), RESET EXIT, QUIT, and CTRL+C, are recognized only if they appear at the beginning of a line, immediately following the **osql** prompt.</span></span>  
  
 <span data-ttu-id="89f46-263">GO sinaliza tanto o término de um lote quanto a execução de qualquer instrução de cachê do [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="89f46-263">GO signals both the end of a batch and the execution of any cached [!INCLUDE[tsql](../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="89f46-264">Quando você pressiona ENTER ao término de cada linha de entrada, o **osql** armazena as instruções nessa linha em cache.</span><span class="sxs-lookup"><span data-stu-id="89f46-264">When you press ENTER at the end of each input line, **osql** caches the statements on that line.</span></span> <span data-ttu-id="89f46-265">Quando você pressiona ENTER depois de digitar GO, todas as instruções atualmente em cache são enviadas como um lote ao [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89f46-265">When you press ENTER after typing GO, all of the currently cached statements are sent as a batch to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="89f46-266">O utilitário **osql** atual funciona como se houvesse um comando GO implícito ao final de qualquer script executado, portanto todas as instruções no script são executadas.</span><span class="sxs-lookup"><span data-stu-id="89f46-266">The current **osql** utility works as if there is an implied GO at the end of any script executed, therefore all statements in the script execute.</span></span>  
  
 <span data-ttu-id="89f46-267">Termine um comando digitando um começo de linha com um terminador de comando.</span><span class="sxs-lookup"><span data-stu-id="89f46-267">End a command by typing a line beginning with a command terminator.</span></span> <span data-ttu-id="89f46-268">Você pode seguir o terminador de comando com um inteiro para especificar quantas vezes o comando deve ser executado.</span><span class="sxs-lookup"><span data-stu-id="89f46-268">You can follow the command terminator with an integer to specify how many times the command should be run.</span></span> <span data-ttu-id="89f46-269">Por exemplo, para executar esse comando 100 vezes, digite:</span><span class="sxs-lookup"><span data-stu-id="89f46-269">For example, to execute this command 100 times, type:</span></span>  
  
```  
SELECT x = 1  
GO 100  
```  
  
 <span data-ttu-id="89f46-270">Os resultados são impressos após o término de execução.</span><span class="sxs-lookup"><span data-stu-id="89f46-270">The results are printed once at the end of execution.</span></span> <span data-ttu-id="89f46-271">O**osql** não aceita mais de 1.000 caracteres por linha.</span><span class="sxs-lookup"><span data-stu-id="89f46-271">**osql** does not accept more than 1,000 characters per line.</span></span> <span data-ttu-id="89f46-272">Instruções grandes devem ser divididas em várias linhas.</span><span class="sxs-lookup"><span data-stu-id="89f46-272">Large statements should be spread across multiple lines.</span></span>  
  
 <span data-ttu-id="89f46-273">Os recursos de recall de comando do Windows podem ser usados para chamar novamente e modificar instruções **osql** .</span><span class="sxs-lookup"><span data-stu-id="89f46-273">The command recall facilities of Windows can be used to recall and modify **osql** statements.</span></span> <span data-ttu-id="89f46-274">O buffer de consulta existente pode ser desmarcado digitando RESET.</span><span class="sxs-lookup"><span data-stu-id="89f46-274">The existing query buffer can be cleared by typing RESET.</span></span>  
  
 <span data-ttu-id="89f46-275">Ao executar procedimentos armazenados, o **osql** imprime uma linha em branco entre cada conjunto de resultados em um lote.</span><span class="sxs-lookup"><span data-stu-id="89f46-275">When running stored procedures, **osql** prints a blank line between each set of results in a batch.</span></span> <span data-ttu-id="89f46-276">Além disso, a mensagem "0 linhas afetadas" não aparece quando não se aplica à instrução executada.</span><span class="sxs-lookup"><span data-stu-id="89f46-276">In addition, the "0 rows affected" message does not appear when it does not apply to the statement executed.</span></span>  
  
## <a name="using-osql-interactively"></a><span data-ttu-id="89f46-277">Usando o osql interativamente</span><span class="sxs-lookup"><span data-stu-id="89f46-277">Using osql Interactively</span></span>  
 <span data-ttu-id="89f46-278">Para usar o **osql** interativamente, digite o comando **osql** (e qualquer uma das opções) em um prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="89f46-278">To use **osql** interactively, type the **osql** command (and any of the options) at a command prompt.</span></span>  
  
 <span data-ttu-id="89f46-279">Você pode ler em um arquivo contendo uma consulta (como Stores.qry) para execução pelo **osql** digitando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="89f46-279">You can read in a file containing a query (such as Stores.qry) for execution by **osql** by typing a command similar to this:</span></span>  
  
```  
osql -E -i stores.qry  
```  
  
 <span data-ttu-id="89f46-280">Você pode ler em um arquivo contendo uma consulta (como Titles.qry) e direcionar os resultados a outro arquivo digitando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="89f46-280">You can read in a file containing a query (such as Titles.qry) and direct the results to another file by typing a command similar to this:</span></span>  
  
```  
osql -E -i titles.qry -o titles.res  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="89f46-281">Quando possível, use a opção **-E**(conexão de confiança).</span><span class="sxs-lookup"><span data-stu-id="89f46-281">When possible, use the **-E**option (trusted connection).</span></span>  
  
 <span data-ttu-id="89f46-282">Ao usar o **osql** interativamente, você pode ler um arquivo do sistema operacional no buffer de comando com **: r**_file_name_.</span><span class="sxs-lookup"><span data-stu-id="89f46-282">When using **osql** interactively, you can read an operating-system file into the command buffer with **:r**_file_name_.</span></span> <span data-ttu-id="89f46-283">Isso envia o script SQL no *file_name* diretamente para o servidor como um único lote.</span><span class="sxs-lookup"><span data-stu-id="89f46-283">This sends the SQL script in *file_name* directly to the server as a single batch.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89f46-284">Ao usar o **osql**, o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] trata o separador em lote GO, se ele for exibido em um arquivo de script SQL, como um erro de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="89f46-284">When using **osql**, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] treats the batch separator GO, if it appears in a SQL script file, as a syntax error.</span></span>  
  
## <a name="inserting-comments"></a><span data-ttu-id="89f46-285">Inserindo comentários</span><span class="sxs-lookup"><span data-stu-id="89f46-285">Inserting Comments</span></span>  
 <span data-ttu-id="89f46-286">Você pode incluir comentários em uma instrução Transact-SQL enviada ao [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pelo **osql**.</span><span class="sxs-lookup"><span data-stu-id="89f46-286">You can include comments in a Transact-SQL statement submitted to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] by **osql**.</span></span> <span data-ttu-id="89f46-287">São permitidos dois tipos de estilos de comentário: -- e /\*...\*/.</span><span class="sxs-lookup"><span data-stu-id="89f46-287">Two types of commenting styles are allowed: -- and /\*...\*/.</span></span>  
  
## <a name="using-exit-to-return-results-in-osql"></a><span data-ttu-id="89f46-288">Usando EXIT para retornar resultados no osql</span><span class="sxs-lookup"><span data-stu-id="89f46-288">Using EXIT to Return Results in osql</span></span>  
 <span data-ttu-id="89f46-289">Você pode usar o resultado de uma instrução SELECT como o valor de retorno do **osql**.</span><span class="sxs-lookup"><span data-stu-id="89f46-289">You can use the result of a SELECT statement as the return value from **osql**.</span></span> <span data-ttu-id="89f46-290">Se ele for numérico, a última coluna da última linha do resultado será convertida em um inteiro de 4 bytes (longo).</span><span class="sxs-lookup"><span data-stu-id="89f46-290">If it is numeric, the last column of the last result row is converted to a 4-byte integer (long).</span></span> <span data-ttu-id="89f46-291">O MS-DOS transmite o byte baixo para o processo pai ou nível de erro do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="89f46-291">MS-DOS passes the low byte to the parent process or operating system error level.</span></span> <span data-ttu-id="89f46-292">O Windows passa o número inteiro de 4 bytes.</span><span class="sxs-lookup"><span data-stu-id="89f46-292">Windows passes the entire 4-byte integer.</span></span> <span data-ttu-id="89f46-293">A sintaxe do é:</span><span class="sxs-lookup"><span data-stu-id="89f46-293">The syntax is:</span></span>  
  
```  
EXIT ( < query > )  
```  
  
 <span data-ttu-id="89f46-294">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="89f46-294">For example:</span></span>  
  
```  
EXIT(SELECT @@ROWCOUNT)  
```  
  
 <span data-ttu-id="89f46-295">É possível incluir também o parâmetro EXIT como parte de um arquivo em lote.</span><span class="sxs-lookup"><span data-stu-id="89f46-295">You can also include the EXIT parameter as part of a batch file.</span></span> <span data-ttu-id="89f46-296">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="89f46-296">For example:</span></span>  
  
```  
osql -E -Q "EXIT(SELECT COUNT(*) FROM '%1')"  
```  
  
 <span data-ttu-id="89f46-297">O utilitário **osql** passa tudo entre os parênteses **()** para o servidor exatamente como digitado.</span><span class="sxs-lookup"><span data-stu-id="89f46-297">The **osql** utility passes everything between the parentheses **()** to the server exactly as entered.</span></span> <span data-ttu-id="89f46-298">Se um procedimento de sistema armazenado selecionar um conjunto e retornar um valor, somente a seleção será retornada.</span><span class="sxs-lookup"><span data-stu-id="89f46-298">If a stored system procedure selects a set and returns a value, only the selection is returned.</span></span> <span data-ttu-id="89f46-299">A instrução EXIT **()** sem nada entre os parênteses executa tudo que a precede no lote e é encerrada sem valor retornado.</span><span class="sxs-lookup"><span data-stu-id="89f46-299">The EXIT **()** statement with nothing between the parentheses executes everything preceding it in the batch and then exits with no return value.</span></span>  
  
 <span data-ttu-id="89f46-300">Há quatro formatos EXIT:</span><span class="sxs-lookup"><span data-stu-id="89f46-300">There are four EXIT formats:</span></span>  
  
-   <span data-ttu-id="89f46-301">EXIT</span><span class="sxs-lookup"><span data-stu-id="89f46-301">EXIT</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89f46-302">Não executa o lote; sai imediatamente e não retorna valor algum.</span><span class="sxs-lookup"><span data-stu-id="89f46-302">Does not execute the batch; quits immediately and returns no value.</span></span>  
  
-   <span data-ttu-id="89f46-303">EXIT **()**</span><span class="sxs-lookup"><span data-stu-id="89f46-303">EXIT **()**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89f46-304">Executa o lote e então sai imediatamente e não retorna valor algum.</span><span class="sxs-lookup"><span data-stu-id="89f46-304">Executes the batch, and then quits and returns no value.</span></span>  
  
-   <span data-ttu-id="89f46-305">SAIR **( *`query`* )**</span><span class="sxs-lookup"><span data-stu-id="89f46-305">EXIT **(*`query`*)**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89f46-306">Executa o lote, incluindo a consulta, e sai depois de retornar os resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="89f46-306">Executes the batch, including the query, and then quits after returning the results of the query.</span></span>  
  
-   <span data-ttu-id="89f46-307">RAISERROR com estado de 127</span><span class="sxs-lookup"><span data-stu-id="89f46-307">RAISERROR with a state of 127</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89f46-308">Se for usado RAISERROR em um script **osql** e ocorrer um estado 127, o **osql** sairá e retornará a ID da mensagem para o cliente.</span><span class="sxs-lookup"><span data-stu-id="89f46-308">If RAISERROR is used within an **osql** script and a state of 127 is raised, **osql** will quit and return the message ID back to the client.</span></span> <span data-ttu-id="89f46-309">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="89f46-309">For example:</span></span>  
  
```  
RAISERROR(50001, 10, 127)  
```  
  
 <span data-ttu-id="89f46-310">Esse erro fará com que o script **osql** seja encerrado e retorne a ID da mensagem 50001 ao cliente.</span><span class="sxs-lookup"><span data-stu-id="89f46-310">This error will cause the **osql** script to end and the message ID 50001 will be returned to the client.</span></span>  
  
 <span data-ttu-id="89f46-311">Os valores de retorno de -1 a -99 são reservados pelo [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]; o **osql** define estes valores:</span><span class="sxs-lookup"><span data-stu-id="89f46-311">The return values -1 to -99 are reserved by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]; **osql** defines these values:</span></span>  
  
-   <span data-ttu-id="89f46-312">-100</span><span class="sxs-lookup"><span data-stu-id="89f46-312">-100</span></span>  
  
     <span data-ttu-id="89f46-313">Erro encontrado antes da seleção do valor de retorno.</span><span class="sxs-lookup"><span data-stu-id="89f46-313">Error encountered prior to selecting return value.</span></span>  
  
-   <span data-ttu-id="89f46-314">-101</span><span class="sxs-lookup"><span data-stu-id="89f46-314">-101</span></span>  
  
     <span data-ttu-id="89f46-315">Nenhuma linha encontrada ao se selecionar o valor de retorno.</span><span class="sxs-lookup"><span data-stu-id="89f46-315">No rows found when selecting return value.</span></span>  
  
-   <span data-ttu-id="89f46-316">-102</span><span class="sxs-lookup"><span data-stu-id="89f46-316">-102</span></span>  
  
     <span data-ttu-id="89f46-317">Erro de conversão ao selecionar valor de retorno.</span><span class="sxs-lookup"><span data-stu-id="89f46-317">Conversion error occurred when selecting return value.</span></span>  
  
## <a name="displaying-money-and-smallmoney-data-types"></a><span data-ttu-id="89f46-318">Exibindo Tipos de Dados money e smallmoney</span><span class="sxs-lookup"><span data-stu-id="89f46-318">Displaying money and smallmoney Data Types</span></span>  
 <span data-ttu-id="89f46-319">o **osql** exibe os `money` tipos de dados e `smallmoney` com duas casas decimais, embora [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] armazene o valor internamente com quatro casas decimais.</span><span class="sxs-lookup"><span data-stu-id="89f46-319">**osql** displays the `money` and `smallmoney` data types with two decimal places although [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] stores the value internally with four decimal places.</span></span> <span data-ttu-id="89f46-320">Considere o exemplo:</span><span class="sxs-lookup"><span data-stu-id="89f46-320">Consider the example:</span></span>  
  
```  
SELECT CAST(CAST(10.3496 AS money) AS decimal(6, 4))  
GO  
```  
  
 <span data-ttu-id="89f46-321">Essa instrução produz um resultado de `10.3496`, que indica que o valor é armazenado com todas as casas decimais intactas.</span><span class="sxs-lookup"><span data-stu-id="89f46-321">This statement produces a result of `10.3496`, which indicates that the value is stored with all decimal places intact.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89f46-322">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="89f46-322">See Also</span></span>  
 <span data-ttu-id="89f46-323">[Comentário &#40;MDX&#41;](/sql/mdx/comment-mdx) </span><span class="sxs-lookup"><span data-stu-id="89f46-323">[Comment &#40;MDX&#41;](/sql/mdx/comment-mdx) </span></span>  
 <span data-ttu-id="89f46-324">[-- &#40;Comment&#41; &#40;MDX&#41;](/sql/mdx/comment-mdx) </span><span class="sxs-lookup"><span data-stu-id="89f46-324">[-- &#40;Comment&#41; &#40;MDX&#41;](/sql/mdx/comment-mdx) </span></span>  
 <span data-ttu-id="89f46-325">[CAST e CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="89f46-325">[CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql) </span></span>  
 [<span data-ttu-id="89f46-326">RAISERROR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="89f46-326">RAISERROR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/raiserror-transact-sql)  
  
  
