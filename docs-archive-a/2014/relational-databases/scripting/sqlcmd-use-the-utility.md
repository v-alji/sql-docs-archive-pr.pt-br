---
title: Usar o utilitário sqlcmd
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- Transact-SQL statements, executing
- command prompt utilities [SQL Server], sqlcmd
- statements [SQL Server], executing
- sqlcmd utility, about sqlcmd utility
ms.assetid: 3ec89119-7314-43ef-9e91-12e72bb63d62
author: rothja
ms.author: jroth
ms.openlocfilehash: 922f9915272fb2d7fc63487ec135ce44ee91e88b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576265"
---
# <a name="use-the-sqlcmd-utility"></a><span data-ttu-id="4d9c2-102">Usar o utilitário sqlcmd</span><span class="sxs-lookup"><span data-stu-id="4d9c2-102">Use the sqlcmd Utility</span></span>
  <span data-ttu-id="4d9c2-103">O utilitário `sqlcmd` é um utilitário de linha de comando para execução interativa ad hoc dos scripts e instruções [!INCLUDE[tsql](../../includes/tsql-md.md)], e para automatização das tarefas de script do [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d9c2-103">The `sqlcmd` utility is a command-line utility for ad hoc, interactive execution of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and scripts and for automating [!INCLUDE[tsql](../../includes/tsql-md.md)] scripting tasks.</span></span> <span data-ttu-id="4d9c2-104">Para usar o `sqlcmd` de forma interativa ou para criar arquivos de script para serem executados com o `sqlcmd`, os usuários devem entender o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d9c2-104">To use `sqlcmd` interactively, or to build script files to be run using `sqlcmd`, users must understand [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="4d9c2-105">O utilitário `sqlcmd` é normalmente usado das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-105">The `sqlcmd` utility is typically used in the following ways:</span></span>  
  
-   <span data-ttu-id="4d9c2-106">Os usuários inserem interativamente instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] de forma semelhante ao trabalho no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-106">Users interactively enter [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in a manner similar to working at the command prompt.</span></span> <span data-ttu-id="4d9c2-107">Os resultados são exibidos no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-107">The results are displayed at the command prompt.</span></span> <span data-ttu-id="4d9c2-108">Para abrir uma janela de prompt de comando, clique em **Iniciar**, clique em **Todos os Programas**, aponte para **Acessórios**e, em seguida, clique em **Prompt de Comando**.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-108">To open a Command Prompt window, click **Start**, click **All Programs**, point to **Accessories**, and then click **Command Prompt**.</span></span> <span data-ttu-id="4d9c2-109">No prompt de comando, digite `sqlcmd` seguido por uma lista de opções que você deseja.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-109">At the command prompt, type `sqlcmd` followed by a list of options that you want.</span></span> <span data-ttu-id="4d9c2-110">Para obter uma lista completa das opções com suporte no `sqlcmd` , consulte [utilitário sqlcmd](../../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="4d9c2-110">For a complete list of the options that are supported by `sqlcmd`, see [sqlcmd Utility](../../tools/sqlcmd-utility.md).</span></span>  
  
-   <span data-ttu-id="4d9c2-111">Os usuários enviam um trabalho `sqlcmd` especificando uma única instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] a ser executada ou apontando o utilitário para um arquivo de texto que contenha instruções[!INCLUDE[tsql](../../includes/tsql-md.md)] a serem executadas.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-111">Users submit a `sqlcmd` job either by specifying a single [!INCLUDE[tsql](../../includes/tsql-md.md)] statement to execute, or by pointing the utility to a text file that contains [!INCLUDE[tsql](../../includes/tsql-md.md)] statements to execute.</span></span> <span data-ttu-id="4d9c2-112">O resultado geralmente é dirigido a um arquivo de texto, mas também pode ser exibido no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-112">The output is usually directed to a text file, but it can also be displayed at the command prompt.</span></span>  
  
-   <span data-ttu-id="4d9c2-113">[modo SQLCMD](edit-sqlcmd-scripts-with-query-editor.md) no Editor de Consultas [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4d9c2-113">[SQLCMD mode](edit-sqlcmd-scripts-with-query-editor.md) in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor.</span></span>  
  
-   <span data-ttu-id="4d9c2-114">SQL Server Management Objects (SMO)</span><span class="sxs-lookup"><span data-stu-id="4d9c2-114">SQL Server Management Objects (SMO)</span></span>  
  
-   <span data-ttu-id="4d9c2-115">Trabalhos do CmdExec do SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-115">SQL Server Agent CmdExec jobs.</span></span>  
  
## <a name="typically-used-sqlcmd-options"></a><span data-ttu-id="4d9c2-116">Opções sqlcmd normalmente usadas</span><span class="sxs-lookup"><span data-stu-id="4d9c2-116">Typically Used sqlcmd Options</span></span>  
 <span data-ttu-id="4d9c2-117">As opções a seguir são usadas com mais frequência:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-117">The following options are used most frequently:</span></span>  
  
-   <span data-ttu-id="4d9c2-118">A opção de servidor (**-S**) que identifica a instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à qual o `sqlcmd` se conecta.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-118">The server option (**-S**) that identifies the instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to which `sqlcmd` connects.</span></span>  
  
-   <span data-ttu-id="4d9c2-119">Opções de autenticação (**-E**, **-U**e **-P**) que especificam as credenciais que o `sqlcmd` usa para se conectar à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4d9c2-119">Authentication options (**-E**, **-U**, and **-P**) that specify the credentials that `sqlcmd` uses to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4d9c2-120">A opção **-E** é o padrão e não precisa ser especificada.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-120">The **-E** option is the default and does not have to be specified.</span></span>  
  
-   <span data-ttu-id="4d9c2-121">As opções de entrada (**-q**, **-Q**e **-i**) que identificam o local da entrada para `sqlcmd` .</span><span class="sxs-lookup"><span data-stu-id="4d9c2-121">Input options (**-Q**, **-q**, and **-i**) that identify the location of the input to `sqlcmd`.</span></span>  
  
-   <span data-ttu-id="4d9c2-122">A opção de saída (**-o**) que especifica o arquivo em que o deve `sqlcmd` colocar sua saída.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-122">The output option (**-o**) that specifies the file in which `sqlcmd` is to put its output.</span></span>  
  
## <a name="connecting-to-the-sqlcmd-utility"></a><span data-ttu-id="4d9c2-123">Conectando-se ao utilitário sqlcmd</span><span class="sxs-lookup"><span data-stu-id="4d9c2-123">Connecting to the sqlcmd Utility</span></span>  
 <span data-ttu-id="4d9c2-124">Estes são os usos comuns do utilitário `sqlcmd`:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-124">The following are common uses of the `sqlcmd` utility:</span></span>  
  
-   <span data-ttu-id="4d9c2-125">Conectando-se a uma instância padrão usando a Autenticação do Windows para executar instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] de forma interativa:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-125">Connecting to a default instance by using Windows Authentication to interactively run [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    sqlcmd -S <ComputerName>  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="4d9c2-126">No exemplo anterior, **-E** não é especificado porque é o padrão e `sqlcmd` se conecta à instância padrão usando a autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-126">In the previous example, **-E** is not specified because it is the default and `sqlcmd` connects to the default instance by using Windows Authentication.</span></span>  
  
-   <span data-ttu-id="4d9c2-127">Conexão com uma instância nomeada usando a Autenticação do Windows para executar instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] interativamente:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-127">Connecting to a named instance by using Windows Authentication to interactively run [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    sqlcmd -S <ComputerName>\<InstanceName>  
    ```  
  
     <span data-ttu-id="4d9c2-128">ou o</span><span class="sxs-lookup"><span data-stu-id="4d9c2-128">or</span></span>  
  
    ```  
    sqlcmd -S .\<InstanceName>  
    ```  
  
-   <span data-ttu-id="4d9c2-129">Conectando-se com uma instância nomeada, usando a Autenticação do Windows e especificando arquivos de entrada e saída:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-129">Connecting to a named instance by using Windows Authentication and specifying input and output files:</span></span>  
  
    ```  
    sqlcmd -S <ComputerName>\<InstanceName> -i <MyScript.sql> -o <MyOutput.rpt>  
    ```  
  
-   <span data-ttu-id="4d9c2-130">Conectando-se a uma instância padrão no computador local usando a Autenticação do Windows, executando uma consulta e executando o `sqlcmd` até mesmo após a consulta ter sido concluída:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-130">Connecting to the default instance on the local computer by using Windows Authentication, executing a query, and having `sqlcmd` remain running after the query has finished running:</span></span>  
  
    ```  
    sqlcmd -q "SELECT * FROM AdventureWorks2012.Person.Person"  
    ```  
  
-   <span data-ttu-id="4d9c2-131">Conectando-se a uma instância padrão no computador local usando a Autenticação do Windows, executando uma consulta, direcionando a saída para um arquivo e fazendo com que o `sqlcmd` feche após a conclusão da consulta:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-131">Connecting to the default instance on the local computer by using Windows Authentication, executing a query, directing the output to a file, and having `sqlcmd` exit after the query has finished running:</span></span>  
  
    ```  
    sqlcmd -Q "SELECT * FROM AdventureWorks2012.Person.Person" -o MyOutput.txt  
    ```  
  
-   <span data-ttu-id="4d9c2-132">Conectando-se a uma instância nomeada que usa a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para executar de forma interativa as instruções [!INCLUDE[tsql](../../includes/tsql-md.md)], com o `sqlcmd` solicitando uma senha:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-132">Connecting to a named instance using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication to interactively run [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, with `sqlcmd` prompting for a password:</span></span>  
  
    ```  
    sqlcmd -U MyLogin -S <ComputerName>\<InstanceName>  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="4d9c2-133">Para consultar uma lista das opções que têm suporte no utilitário `sqlcmd`, execute `sqlcmd -?`.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-133">To see a list of the options that are supported by the `sqlcmd` utility run: `sqlcmd -?`.</span></span>  
  
## <a name="running-transact-sql-statements-interactively-by-using-sqlcmd"></a><span data-ttu-id="4d9c2-134">Executando instruções Transact-SQL interativamente usando o sqlcmd</span><span class="sxs-lookup"><span data-stu-id="4d9c2-134">Running Transact-SQL Statements Interactively by Using sqlcmd</span></span>  
 <span data-ttu-id="4d9c2-135">Você pode usar o utilitário `sqlcmd` interativamente para executar instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] em uma janela de prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-135">You can use the `sqlcmd` utility interactively to execute [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in a Command Prompt window.</span></span> <span data-ttu-id="4d9c2-136">Para executar interativamente [!INCLUDE[tsql](../../includes/tsql-md.md)] instruções usando `sqlcmd` o, execute o utilitário sem usar as opções **-q**, **-Q**, **-Z**ou **-i** para especificar quaisquer arquivos de entrada ou consultas.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-136">To interactively execute [!INCLUDE[tsql](../../includes/tsql-md.md)] statements by using `sqlcmd`, run the utility without using the **-Q**, **-q**, **-Z**, or **-i** options to specify any input files or queries.</span></span> <span data-ttu-id="4d9c2-137">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-137">For example:</span></span>  
  
 `sqlcmd -S <ComputerName>\<InstanceName>`  
  
 <span data-ttu-id="4d9c2-138">Quando o comando é executado sem arquivos ou consultas de entrada, o `sqlcmd` se conecta à instância especificada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e, em seguida, exibe uma nova linha com um `1>` seguido de um sublinhado intermitente, que é conhecido como o prompt do `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-138">When the command is executed without input files or queries, `sqlcmd` connects to the specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and then displays a new line with a `1>` followed by a blinking underscore that is named the `sqlcmd` prompt.</span></span> <span data-ttu-id="4d9c2-139">O `1` significa que esta é a primeira linha de uma instrução [!INCLUDE[tsql](../../includes/tsql-md.md)], e o prompt do `sqlcmd` é o ponto no qual a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] iniciará quando ela for digitada nele.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-139">The `1` signifies that this is the first line of a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, and the `sqlcmd` prompt is the point at which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement will start when you type it in.</span></span>  
  
 <span data-ttu-id="4d9c2-140">No prompt `sqlcmd`, você pode digitar instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] e comandos `sqlcmd`, como `GO` e `EXIT`.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-140">At the `sqlcmd` prompt, you can type both [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and `sqlcmd` commands, such as `GO` and `EXIT`.</span></span> <span data-ttu-id="4d9c2-141">Cada instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] é colocada em um buffer denominado cache de instrução.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-141">Each [!INCLUDE[tsql](../../includes/tsql-md.md)] statement is put in a buffer called the statement cache.</span></span> <span data-ttu-id="4d9c2-142">Essas instruções são enviadas ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] depois que você digita o comando `GO` e pressiona ENTER.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-142">These statements are sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] after you type the `GO` command and press ENTER.</span></span> <span data-ttu-id="4d9c2-143">Para sair `sqlcmd` , digite `EXIT` ou `QUIT` no início de uma nova linha.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-143">To exit `sqlcmd`, type `EXIT` or `QUIT` at the start of a new line.</span></span>  
  
 <span data-ttu-id="4d9c2-144">Para limpar o cache de instruções, digite `:RESET`.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-144">To clear the statement cache, type `:RESET`.</span></span> <span data-ttu-id="4d9c2-145">A digitação `^C` faz com que o `sqlcmd` saia.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-145">Typing `^C` causes `sqlcmd` to exit.</span></span> <span data-ttu-id="4d9c2-146">O `^C` também pode ser usado para interromper a execução do cache de instrução depois que um comando `GO` é emitido.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-146">`^C` can also be used to stop the execution of the statement cache after a `GO` command has been issued.</span></span>  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)]<span data-ttu-id="4d9c2-147">as instruções que são inseridas em uma sessão interativa podem ser editadas inserindo o comando **: Ed** e o `sqlcmd` prompt.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-147">statements that are entered in an interactive session can edited by entering the **:ED** command and the `sqlcmd` prompt.</span></span> <span data-ttu-id="4d9c2-148">O editor será aberto e, após a edição da instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] e de fechamento do editor, a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] revisada aparecerá na janela de comando.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-148">The editor will open and, after editing the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement and closing the editor, the revised [!INCLUDE[tsql](../../includes/tsql-md.md)] statement will appear in the command window.</span></span> <span data-ttu-id="4d9c2-149">Insira `GO` para executar a instrução revisada [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4d9c2-149">Enter `GO` to run therevised [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
## <a name="quoted-strings"></a><span data-ttu-id="4d9c2-150">Cadeia de caracteres entre aspas</span><span class="sxs-lookup"><span data-stu-id="4d9c2-150">Quoted Strings</span></span>  
 <span data-ttu-id="4d9c2-151">Os caracteres entre aspas são usados sem nenhum pré-processamento adicional, a não ser quando as aspas podem ser inseridas em uma cadeia de caracteres através de duas aspas consecutivas.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-151">Characters that are enclosed in quotation marks are used without any additional preprocessing, except that quotations marks can be inserted into a string by entering two consecutive quotation marks.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4d9c2-152">trata esta sequência de caracteres como uma aspa.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-152">treats this character sequence as one quotation mark.</span></span> <span data-ttu-id="4d9c2-153">(Porém, a tradução acontece no servidor.) Não serão expandidas variáveis de script quando elas aparecerem dentro de uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-153">(However, the translation occurs in the server.) Scripting variables will not be expanded when they appear within a string.</span></span>  
  
 <span data-ttu-id="4d9c2-154">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-154">For example:</span></span>  
  
 `sqlcmd`  
  
 `PRINT "Length: 5"" 7'";`  
  
 `GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `Length: 5" 7'`  
  
## <a name="strings-that-span-multiple-lines"></a><span data-ttu-id="4d9c2-155">Cadeias de caracteres que abrangem várias linhas</span><span class="sxs-lookup"><span data-stu-id="4d9c2-155">Strings That Span Multiple Lines</span></span>  
 <span data-ttu-id="4d9c2-156">O `sqlcmd` oferece suporte a scripts com cadeias de caracteres que abrangem várias linhas.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-156">`sqlcmd` supports scripts that have strings that span multiple lines.</span></span> <span data-ttu-id="4d9c2-157">Por exemplo, a seguinte instrução `SELECT` estende diversas linhas, mas é uma única cadeia de caracteres executada ao pressionar a tecla ENTER, depois de digitar `GO`.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-157">For example, the following `SELECT` statement spans multiple lines but is a single string executed when you press the ENTER key after typing `GO`.</span></span>  
  
 `SELECT First line`  
  
 `FROM Second line`  
  
 `WHERE Third line;`  
  
 `GO`  
  
## <a name="interactive-sqlcmd-example"></a><span data-ttu-id="4d9c2-158">Exemplo interativo do sqlcmd</span><span class="sxs-lookup"><span data-stu-id="4d9c2-158">Interactive sqlcmd Example</span></span>  
 <span data-ttu-id="4d9c2-159">Este é um exemplo do que você verá ao executar o `sqlcmd` interativamente.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-159">This is an example of what you see when you run `sqlcmd` interactively.</span></span>  
  
 <span data-ttu-id="4d9c2-160">Ao abrir uma janela de prompt de comando, você verá uma linha semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-160">When you open a Command Prompt window, there is one line similar to:</span></span>  
  
 `C:\> _`  
  
 <span data-ttu-id="4d9c2-161">Isso significa que a pasta `C:\` é a pasta atual, e se você especificar um nome de arquivo, o Windows vai procurar o arquivo nessa pasta.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-161">This means the folder `C:\` is the current folder, and if you specify a file name, Windows will look for the file in that folder.</span></span>  
  
 <span data-ttu-id="4d9c2-162">Digite `sqlcmd` para se conectar à instância padrão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no computador local, e o conteúdo da janela Prompt de Comando será:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-162">Type `sqlcmd` to connect to the default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on the local computer, and the contents of the Command Prompt window will be:</span></span>  
  
 `C:\>sqlcmd`  
  
 `1> _`  
  
 <span data-ttu-id="4d9c2-163">Isso significa que você se conectou com a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e o `sqlcmd` agora está pronto para aceitar as instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] e os comandos `sqlcmd` .</span><span class="sxs-lookup"><span data-stu-id="4d9c2-163">This means you have connected to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and `sqlcmd` is now ready to accept [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and `sqlcmd` commands.</span></span> <span data-ttu-id="4d9c2-164">O sublinhado intermitente que precede o `1>` é o prompt `sqlcmd` que marca o local no qual as instruções e os comandos que você digita serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-164">The flashing underscore after the `1>` is the `sqlcmd` prompt that marks the location at which the statements and commands you type will be displayed.</span></span> <span data-ttu-id="4d9c2-165">Agora, digite `USE AdventureWorks2012` e pressione Enter e, em seguida, digite `GO` e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-165">Now, type `USE AdventureWorks2012` and press ENTER, and then type `GO` and press ENTER.</span></span> <span data-ttu-id="4d9c2-166">O conteúdo da janela de prompt de comando será:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-166">The contents of the Command Prompt window will be:</span></span>  
  
 `sqlcmd`  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `Changed database context to 'AdventureWorks2012'.`  
  
 `1> _`  
  
 <span data-ttu-id="4d9c2-167">Pressionar ENTER depois de inserir `USE AdventureWorks2012` sinaliza ao `sqlcmd` para iniciar uma linha nova.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-167">Pressing ENTER after entering `USE AdventureWorks2012` signaled `sqlcmd` to start a new line.</span></span> <span data-ttu-id="4d9c2-168">Ao pressionar ENTER após digitar `GO,` , você sinalizou o `sqlcmd` para enviar a instrução `USE AdventureWorks2012` à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d9c2-168">Pressing ENTER, after you type `GO,` signaled `sqlcmd` to send the `USE AdventureWorks2012` statement to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4d9c2-169">`sqlcmd` retornou uma mensagem para indicar que a instrução `USE` foi concluída com êxito e exibiu um novo prompt `1>` como sinal para inserir uma nova instrução ou comando.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-169">`sqlcmd` then returned a message to indicate that the `USE` statement completed successfully and displayed a new `1>` prompt as a signal to enter a new statement or command.</span></span>  
  
 <span data-ttu-id="4d9c2-170">O exemplo a seguir mostra o conteúdo da janela de prompt de comando ao você digitar uma instrução `SELECT` , uma `GO` para executar o comando `SELECT`, e uma `EXIT` para fechar o `sqlcmd`:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-170">The following example shows what the Command Prompt window contains if you type a `SELECT` statement, a `GO` to execute the `SELECT`, and an `EXIT` to exit `sqlcmd`:</span></span>  
  
 `sqlcmd`  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 `SELECT TOP (3) BusinessEntityID, FirstName, LastName`  
  
 `FROM Person.Person;`  
  
 `GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `BusinessEntityID   FirstName                 LastName`  
  
 `----------- -------------------------------- -----------`  
  
 `1           Syed                             Abbas`  
  
 `2           Catherine                        Abel`  
  
 `3           Kim                              Abercrombie`  
  
 `(3 rows affected)`  
  
 `1> EXIT`  
  
 `C:\>`  
  
 <span data-ttu-id="4d9c2-171">As linhas depois da linha `3> GO` são a saída de uma instrução `SELECT` .</span><span class="sxs-lookup"><span data-stu-id="4d9c2-171">The lines after line `3> GO` are the output of a `SELECT` statement.</span></span> <span data-ttu-id="4d9c2-172">Depois que você gerar a saída, o `sqlcmd` redefine o prompt `sqlcmd` e exibe `1>`.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-172">After you generate output, `sqlcmd` resets the `sqlcmd` prompt and displays `1>`.</span></span> <span data-ttu-id="4d9c2-173">Após digitar `EXIT` na linha `1>`, a janela de prompt de comando exibe a mesma linha, como fez quando você a abriu primeiramente.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-173">After entering `EXIT` at line `1>`, the Command Prompt window displays the same line it did when you first opened it.</span></span> <span data-ttu-id="4d9c2-174">Isto indica que o `sqlcmd` encerrou sua sessão.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-174">This indicates that `sqlcmd` has exited its session.</span></span> <span data-ttu-id="4d9c2-175">Agora você pode fechar a janela de prompt de comando digitando outro comando `EXIT` .</span><span class="sxs-lookup"><span data-stu-id="4d9c2-175">You can now close the Command Prompt window by typing another `EXIT` command.</span></span>  
  
## <a name="running-transact-sql-script-files-by-using-sqlcmd"></a><span data-ttu-id="4d9c2-176">Executando arquivos de script Transact-SQL usando o sqlcmd</span><span class="sxs-lookup"><span data-stu-id="4d9c2-176">Running Transact-SQL Script Files by Using sqlcmd</span></span>  
 <span data-ttu-id="4d9c2-177">Você pode usar o`sqlcmd` para executar arquivos de script de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-177">You can use `sqlcmd` to execute database script files.</span></span> <span data-ttu-id="4d9c2-178">Os arquivos de script são arquivos de texto que contêm uma mistura de instruções [!INCLUDE[tsql](../../includes/tsql-md.md)], comandos `sqlcmd` e variáveis de script.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-178">Script files are text files that contain a mix of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, `sqlcmd` commands, and scripting variables.</span></span> <span data-ttu-id="4d9c2-179">Para obter mais informações sobre como usar variáveis de script, veja [Usar sqlcmd com variáveis de script](sqlcmd-use-with-scripting-variables.md).</span><span class="sxs-lookup"><span data-stu-id="4d9c2-179">For more information about how to script variables, see [Use sqlcmd with Scripting Variables](sqlcmd-use-with-scripting-variables.md).</span></span> <span data-ttu-id="4d9c2-180">O `sqlcmd` funciona com instruções, comandos e variáveis de script em um arquivo de script de modo semelhante ao modo como funciona com instruções e comandos inseridos interativamente.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-180">`sqlcmd` works with the statements, commands, and scripting variables in a script file in a manner similar to how it works with statements and commands that are entered interactively.</span></span> <span data-ttu-id="4d9c2-181">A principal diferença é que o `sqlcmd` faz a leitura por meio do arquivo de entrada sem pausa, em vez de esperar que um usuário insira as instruções, os comandos e as variáveis de script.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-181">The main difference is that `sqlcmd` reads through the input file without pause instead of waiting for a user to enter the statements, commands, and scripting variables.</span></span>  
  
 <span data-ttu-id="4d9c2-182">Existem maneiras diferentes de criar arquivos de script de banco de dados:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-182">There are different ways to create database script files:</span></span>  
  
-   <span data-ttu-id="4d9c2-183">Você pode criar e depurar interativamente uma série de instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], e em seguida salvar o conteúdo da janela de consulta como arquivo script.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-183">You can interactively build and debug a set of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then save the contents of the Query window as a script file.</span></span>  
  
-   <span data-ttu-id="4d9c2-184">Você pode criar um arquivo de texto que contém instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] usando um editor de textos, como o Bloco de Notas.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-184">You can create a text file that contains [!INCLUDE[tsql](../../includes/tsql-md.md)] statements by using a text editor, such as Notepad.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="4d9c2-185">Exemplos</span><span class="sxs-lookup"><span data-stu-id="4d9c2-185">Examples</span></span>  
  
### <a name="a-running-a-script-by-using-sqlcmd"></a><span data-ttu-id="4d9c2-186">a.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-186">A.</span></span> <span data-ttu-id="4d9c2-187">Executando um script usando o sqlcmd</span><span class="sxs-lookup"><span data-stu-id="4d9c2-187">Running a script by using sqlcmd</span></span>  
 <span data-ttu-id="4d9c2-188">Iniciar o Bloco de Notas e digitar as seguintes instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="4d9c2-188">Start Notepad, and type the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 `SELECT TOP (3) BusinessEntityID, FirstName, LastName`  
  
 `FROM Person.Person;`  
  
 `GO`  
  
 <span data-ttu-id="4d9c2-189">Criar uma pasta nomeada `MyFolder` e, em seguida, salvar o script como o arquivo `MyScript.sql` na pasta `C:\MyFolder`.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-189">Create a folder named `MyFolder` and then save the script as the file `MyScript.sql` in the folder `C:\MyFolder`.</span></span> <span data-ttu-id="4d9c2-190">Digite a sequência abaixo no prompt de comando para executar o script e colocar a saída em `MyOutput.txt` , em `MyFolder`:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-190">Enter the following at the command prompt to run the script and put the output in `MyOutput.txt` in `MyFolder`:</span></span>  
  
 `sqlcmd -i C:\MyFolder\MyScript.sql -o C:\MyFolder\MyOutput.txt`  
  
 <span data-ttu-id="4d9c2-191">Ao exibir os conteúdos de `MyOutput.txt` no Bloco de Notas, você verá o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-191">When you view the contents of `MyOutput.txt` in Notepad, you will see the following:</span></span>  
  
 `Changed database context to 'AdventureWorks2012'.`  
  
 `BusinessEntityID FirstName   LastName`  
  
 `---------------- ----------- -----------`  
  
 `1                Syed        Abbas`  
  
 `2                Catherine   Abel`  
  
 `3                Kim         Abercrombie`  
  
 `(3 rows affected)`  
  
### <a name="b-using-sqlcmd-with-a-dedicated-administrative-connection"></a><span data-ttu-id="4d9c2-192">B.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-192">B.</span></span> <span data-ttu-id="4d9c2-193">Usando o sqlcmd com uma conexão administrativa dedicada</span><span class="sxs-lookup"><span data-stu-id="4d9c2-193">Using sqlcmd with a dedicated administrative connection</span></span>  
 <span data-ttu-id="4d9c2-194">No exemplo a seguir, `sqlcmd` é usado para se conectar a um servidor que tem um problema de bloqueio utilizando a conexão de administrador dedicada (DAC).</span><span class="sxs-lookup"><span data-stu-id="4d9c2-194">In the following example, `sqlcmd` is used to connect to a server that has a blocking problem by using the dedicated administrator connection (DAC).</span></span>  
  
 `C:\>sqlcmd -S ServerName -A`  
  
 `1> SELECT blocked FROM sys.dm_exec_requests WHERE blocked <> 0;`  
  
 `2> GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `spid   blocked`  
  
 `------ -------`  
  
 `62       64`  
  
 `(1 rows affected)`  
  
 <span data-ttu-id="4d9c2-195">Use o `sqlcmd` para finalizar o processo de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-195">Use `sqlcmd` to end the blocking process.</span></span>  
  
 `1> KILL 64;`  
  
 `2> GO`  
  
### <a name="c-using-sqlcmd-to-execute-a-stored-procedure"></a><span data-ttu-id="4d9c2-196">C.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-196">C.</span></span> <span data-ttu-id="4d9c2-197">Usando o sqlcmd para executar um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="4d9c2-197">Using sqlcmd to execute a stored procedure</span></span>  
 <span data-ttu-id="4d9c2-198">O exemplo a seguir mostra como executar um procedimento armazenado usando o `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-198">The following example shows how to execute a stored procedure by using `sqlcmd`.</span></span> <span data-ttu-id="4d9c2-199">Criar o seguinte procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-199">Create the following stored procedure.</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `IF OBJECT_ID ( ' dbo.ContactEmailAddress, 'P' ) IS NOT NULL`  
  
 `DROP PROCEDURE dbo.ContactEmailAddress;`  
  
 `GO`  
  
 `CREATE PROCEDURE dbo.ContactEmailAddress`  
  
 `(`  
  
 `@FirstName nvarchar(50)`  
  
 `,@LastName nvarchar(50)`  
  
 `)`  
  
 `AS`  
  
 `SET NOCOUNT ON`  
  
 `SELECT EmailAddress`  
  
 `FROM Person.Person`  
  
 `WHERE FirstName = @FirstName`  
  
 `AND LastName = @LastName;`  
  
 `SET NOCOUNT OFF`  
  
 <span data-ttu-id="4d9c2-200">No prompt `sqlcmd` , insira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-200">At the `sqlcmd` prompt, enter the following:</span></span>  
  
 `C:\sqlcmd`  
  
 `1> :Setvar FirstName Gustavo`  
  
 `1> :Setvar LastName Achong`  
  
 `1> EXEC dbo.ContactEmailAddress $(Gustavo),$(Achong)`  
  
 `2> GO`  
  
 `EmailAddress`  
  
 `-----------------------------`  
  
 `gustavo0@adventure-works.com`  
  
### <a name="d-using-sqlcmd-for-database-maintenance"></a><span data-ttu-id="4d9c2-201">D.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-201">D.</span></span> <span data-ttu-id="4d9c2-202">Usando o sqlcmd para manutenção do banco de dados</span><span class="sxs-lookup"><span data-stu-id="4d9c2-202">Using sqlcmd for database maintenance</span></span>  
 <span data-ttu-id="4d9c2-203">O exemplo a seguir mostra como usar o `sqlcmd` para uma tarefa de manutenção de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-203">The following example shows how to use `sqlcmd` for a database maintenance task.</span></span> <span data-ttu-id="4d9c2-204">Crie `C:\BackupTemplate.sql` com o seguinte código.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-204">Create `C:\BackupTemplate.sql` with the following code.</span></span>  
  
 `USE master;`  
  
 `BACKUP DATABASE [$(db)] TO DISK='$(bakfile)';`  
  
 <span data-ttu-id="4d9c2-205">No prompt `sqlcmd` , insira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-205">At the `sqlcmd` prompt, enter the following:</span></span>  
  
 `C:\ >sqlcmd`  
  
 `1> :connect <server>`  
  
 `Sqlcmd: Successfully connected to server <server>.`  
  
 `1> :setvar db msdb`  
  
 `1> :setvar bakfile c:\msdb.bak`  
  
 `1> :r c:\BackupTemplate.sql`  
  
 `2> GO`  
  
 `Changed database context to 'master'.`  
  
 `Processed 688 pages for database 'msdb', file 'MSDBData' on file 2.`  
  
 `Processed 5 pages for database 'msdb', file 'MSDBLog' on file 2.`  
  
 `BACKUP DATABASE successfully processed 693 pages in 0.725 seconds (7.830 MB/sec)`  
  
### <a name="e-using-sqlcmd-to-execute-code-on-multiple-instances"></a><span data-ttu-id="4d9c2-206">E.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-206">E.</span></span> <span data-ttu-id="4d9c2-207">Usando o sqlcmd para executar o código em diversas instâncias</span><span class="sxs-lookup"><span data-stu-id="4d9c2-207">Using sqlcmd to execute code on multiple instances</span></span>  
 <span data-ttu-id="4d9c2-208">O código a seguir em um arquivo exibe um script que conecta a duas instâncias.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-208">The following code in a file shows a script that connects to two instances.</span></span> <span data-ttu-id="4d9c2-209">Note o `GO` antes da conexão com a segunda instância.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-209">Notice the `GO` before the connection to the second instance.</span></span>  
  
 `:CONNECT <server>\,<instance1>`  
  
 `EXEC dbo.SomeProcedure`  
  
 `GO`  
  
 `:CONNECT <server>\,<instance2>`  
  
 `EXEC dbo.SomeProcedure`  
  
 `GO`  
  
### <a name="e-returning-xml-output"></a><span data-ttu-id="4d9c2-210">E.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-210">E.</span></span> <span data-ttu-id="4d9c2-211">Retornando a saída XML</span><span class="sxs-lookup"><span data-stu-id="4d9c2-211">Returning XML output</span></span>  
 <span data-ttu-id="4d9c2-212">O exemplo a seguir mostra como a saída XML é retornada sem formatação, em um fluxo contínuo.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-212">The following example shows how XML output is returned unformatted, in a continuous stream.</span></span>  
  
 `C:\>sqlcmd -d AdventureWorks2012`  
  
 `1> :XML ON`  
  
 `1> SELECT TOP 3 FirstName + ' ' + LastName + ', '`  
  
 `2> FROM Person.Person`  
  
 `3> GO`  
  
 `Syed Abbas, Catherine Abel, Kim Abercrombie,`  
  
### <a name="f-using-sqlcmd-in-a-windows-script-file"></a><span data-ttu-id="4d9c2-213">F.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-213">F.</span></span> <span data-ttu-id="4d9c2-214">Usando o sqlcmd em um arquivo de script do Windows</span><span class="sxs-lookup"><span data-stu-id="4d9c2-214">Using sqlcmd in a Windows script file</span></span>  
 <span data-ttu-id="4d9c2-215">Um `sqlcmd` comando como o `sqlcmd -i C:\InputFile.txt -o C:\OutputFile.txt,` pode ser executado em um arquivo. bat junto com o VBScript.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-215">A `sqlcmd`command such as `sqlcmd -i C:\InputFile.txt -o C:\OutputFile.txt,` can be executed in a .bat file together with VBScript.</span></span> <span data-ttu-id="4d9c2-216">Nesse caso, não use opções interativas.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-216">In this case, do not use interactive options.</span></span> <span data-ttu-id="4d9c2-217">O `sqlcmd` deve ser instalado no computador que está executando o arquivo .bat.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-217">`sqlcmd` must be installed on the computer that is executing the .bat file.</span></span>  
  
 <span data-ttu-id="4d9c2-218">Primeiro, crie os quatro arquivos a seguir:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-218">First, create the following four files:</span></span>  
  
-   <span data-ttu-id="4d9c2-219">C:\badscript.sql</span><span class="sxs-lookup"><span data-stu-id="4d9c2-219">C:\badscript.sql</span></span>  
  
    ```  
    SELECT batch_1_this_is_an_error  
    GO  
    SELECT 'batch #2'  
    GO  
    ```  
  
-   <span data-ttu-id="4d9c2-220">C:\goodscript.sql</span><span class="sxs-lookup"><span data-stu-id="4d9c2-220">C:\goodscript.sql</span></span>  
  
    ```  
    SELECT 'batch #1'  
    GO  
    SELECT 'batch #2'  
    GO  
    ```  
  
-   <span data-ttu-id="4d9c2-221">C:\returnvalue.sql</span><span class="sxs-lookup"><span data-stu-id="4d9c2-221">C:\returnvalue.sql</span></span>  
  
    ```  
    :exit(select 100)  
    @echo off  
    C:\windowsscript.bat  
    @echo off  
  
    echo Running badscript.sql  
    sqlcmd -i badscript.sql -b -o out.log  
    if not errorlevel 1 goto next1  
    echo == An error occurred   
  
    :next1  
  
    echo Running goodscript.sql  
    sqlcmd -i goodscript.sql -b -o out.log  
    if not errorlevel 1 goto next2  
    echo == An error occurred   
  
    :next2  
    echo Running returnvalue.sql  
    sqlcmd -i returnvalue.sql -o out.log  
    echo SQLCMD returned %errorlevel% to the command shell  
  
    :exit  
    ```  
  
-   <span data-ttu-id="4d9c2-222">C:\windowsscript.bat</span><span class="sxs-lookup"><span data-stu-id="4d9c2-222">C:\windowsscript.bat</span></span>  
  
    ```  
    @echo off  
  
    echo Running badscript.sql  
    sqlcmd -i badscript.sql -b -o out.log  
    if not errorlevel 1 goto next1  
    echo == An error occurred   
  
    :next1  
  
    echo Running goodscript.sql  
    sqlcmd -i goodscript.sql -b -o out.log  
    if not errorlevel 1 goto next2  
    echo == An error occurred   
  
    :next2  
    echo Running returnvalue.sql  
    sqlcmd -i returnvalue.sql -o out.log  
    echo SQLCMD returned %errorlevel% to the command shell  
  
    :exit  
    ```  
  
 <span data-ttu-id="4d9c2-223">Em seguida, no prompt de comando, execute `C:\windowsscript.bat`:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-223">Then, at the command prompt, run `C:\windowsscript.bat`:</span></span>  
  
 `C:\>windowsscript.bat`  
  
 `Running badscript.sql`  
  
 `== An error occurred`  
  
 `Running goodscript.sql`  
  
 `Running returnvalue.sql`  
  
 `SQLCMD returned 100 to the command shell`  
  
### <a name="g-using-sqlcmd-to-set-encryption-on-azure-sql-database"></a><span data-ttu-id="4d9c2-224">G.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-224">G.</span></span> <span data-ttu-id="4d9c2-225">Usar sqlcmd para definir a criptografia no Bancos de Dados SQL do Azure</span><span class="sxs-lookup"><span data-stu-id="4d9c2-225">Using sqlcmd to set encryption on Azure SQL Database</span></span>  
 <span data-ttu-id="4d9c2-226">Um `sqlcmd` pode ser executado em uma conexão com [!INCLUDE[ssSDS](../../includes/sssds-md.md)] dados no para especificar criptografia e confiança de certificado.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-226">A `sqlcmd`can be executed on a connection to [!INCLUDE[ssSDS](../../includes/sssds-md.md)] data on to specify encryption and certificate trust.</span></span> <span data-ttu-id="4d9c2-227">Duas opções ' sqlcmd ' ' ' estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-227">Two \`sqlcmd\`\`\`options are available:</span></span>  
  
-   <span data-ttu-id="4d9c2-228">A opção -N é usada pelo cliente para solicitar uma conexão criptografada.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-228">The -N switch is used by the client to request an encrypted connection.</span></span> <span data-ttu-id="4d9c2-229">Essa opção é equivalente à opção `ENCRYPT = true`do ADO.net.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-229">This option is equivalent to the ADO.net option `ENCRYPT = true`.</span></span>  
  
-   <span data-ttu-id="4d9c2-230">A opção -C é usada pelo cliente para configurá-lo para confiar implicitamente no certificado do servidor e não validá-lo.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-230">The -C switch is used by the client to configure it to implicitly the trust server certificate and not validate it.</span></span> <span data-ttu-id="4d9c2-231">Essa opção é equivalente à opção `TRUSTSERVERCERTIFICATE = true`do ADO.net.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-231">This option is equivalent to the ADO.net option `TRUSTSERVERCERTIFICATE = true`.</span></span>  
  
 <span data-ttu-id="4d9c2-232">O serviço [!INCLUDE[ssSDS](../../includes/sssds-md.md)] não dá suporte a todas as opções de `SET` disponíveis em uma instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-232">The [!INCLUDE[ssSDS](../../includes/sssds-md.md)] service does not support all the `SET` options available on a SQL Server instance.</span></span> <span data-ttu-id="4d9c2-233">As opções a seguir emitem um erro quando a opção de `SET` correspondente é definida como `ON` ou `OFF`:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-233">The following options throw an error when the corresponding `SET` option is set to `ON` or `OFF`:</span></span>  
  
-   <span data-ttu-id="4d9c2-234">SET ANSI_DEFAULTS</span><span class="sxs-lookup"><span data-stu-id="4d9c2-234">SET ANSI_DEFAULTS</span></span>  
  
-   <span data-ttu-id="4d9c2-235">SET ANSI_NULLS</span><span class="sxs-lookup"><span data-stu-id="4d9c2-235">SET ANSI_NULLS</span></span>  
  
-   <span data-ttu-id="4d9c2-236">SET REMOTE_PROC_TRANSACTIONS</span><span class="sxs-lookup"><span data-stu-id="4d9c2-236">SET REMOTE_PROC_TRANSACTIONS</span></span>  
  
-   <span data-ttu-id="4d9c2-237">SET ANSI_NULL_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="4d9c2-237">SET ANSI_NULL_DEFAULT</span></span>  
  
 <span data-ttu-id="4d9c2-238">As opções de SET a seguir não emitem exceções, mas não podem ser usadas.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-238">The following SET options do not throw exceptions but cannot be used.</span></span> <span data-ttu-id="4d9c2-239">Elas são substituídas:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-239">They are deprecated:</span></span>  
  
-   <span data-ttu-id="4d9c2-240">SET CONCAT_NULL_YIELDS_NULL</span><span class="sxs-lookup"><span data-stu-id="4d9c2-240">SET CONCAT_NULL_YIELDS_NULL</span></span>  
  
-   <span data-ttu-id="4d9c2-241">SET ANSI_PADDING</span><span class="sxs-lookup"><span data-stu-id="4d9c2-241">SET ANSI_PADDING</span></span>  
  
-   <span data-ttu-id="4d9c2-242">SET QUERY_GOVERNOR_COST_LIMIT</span><span class="sxs-lookup"><span data-stu-id="4d9c2-242">SET QUERY_GOVERNOR_COST_LIMIT</span></span>  
  
#### <a name="syntax"></a><span data-ttu-id="4d9c2-243">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4d9c2-243">Syntax</span></span>  
 <span data-ttu-id="4d9c2-244">Os exemplos a seguir fazem referência a casos em que as configurações do provedor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client incluem: `ForceProtocolEncryption = False`, `Trust Server Certificate = No`</span><span class="sxs-lookup"><span data-stu-id="4d9c2-244">The following examples refer to cases where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client Provider settings include: `ForceProtocolEncryption = False`, `Trust Server Certificate = No`</span></span>  
  
 <span data-ttu-id="4d9c2-245">Conectar usando credenciais do Windows e comunicação criptografada:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-245">Connect using Windows credentials and encrypt communication:</span></span>  
  
```  
SQLCMD -E -N  
  
```  
  
 <span data-ttu-id="4d9c2-246">Conectar usando credenciais do Windows e certificado do servidor confiável:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-246">Connect using Windows credentials and trust server certificate:</span></span>  
  
```  
SQLCMD -E -C  
  
```  
  
 <span data-ttu-id="4d9c2-247">Conectar usando credenciais do Windows, comunicação criptografada e certificado do servidor confiável:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-247">Connect using Windows credentials, encrypt communication and trust server certificate:</span></span>  
  
```  
SQLCMD -E -N -C  
  
```  
  
 <span data-ttu-id="4d9c2-248">Os exemplos a seguir fazem referência a casos em que as configurações do provedor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client incluem: `ForceProtocolEncryption = True`, `TrustServerCertificate = Yes`.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-248">The following examples refer to cases where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client Provider settings include: `ForceProtocolEncryption = True`, `TrustServerCertificate = Yes`.</span></span>  
  
 <span data-ttu-id="4d9c2-249">Conectar usando credenciais do Windows, comunicação criptografada e certificado do servidor confiável:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-249">Connect using Windows credentials, encrypt communication and trust server certificate:</span></span>  
  
```  
SQLCMD -E  
  
```  
  
 <span data-ttu-id="4d9c2-250">Conectar usando credenciais do Windows, comunicação criptografada e certificado do servidor confiável:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-250">Connect using Windows credentials, encrypt communication and trust server certificate:</span></span>  
  
```  
SQLCMD -E -N  
  
```  
  
 <span data-ttu-id="4d9c2-251">Conectar usando credenciais do Windows, comunicação criptografada e certificado do servidor confiável:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-251">Connect using Windows credentials, encrypt communication and trust server certificate:</span></span>  
  
```  
SQLCMD -E -T  
  
```  
  
 <span data-ttu-id="4d9c2-252">Conectar usando credenciais do Windows, comunicação criptografada e certificado do servidor confiável:</span><span class="sxs-lookup"><span data-stu-id="4d9c2-252">Connect using Windows credentials, encrypt communication and trust server certificate:</span></span>  
  
```  
SQLCMD -E -N -C  
  
```  
  
 <span data-ttu-id="4d9c2-253">Se o provedor especificar `ForceProtocolEncryption = True` a criptografia será habilitada mesmo que `Encrypt=No` esteja na cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="4d9c2-253">If the provider specifies `ForceProtocolEncryption = True` then encryption is enabled even if `Encrypt=No` in the connection string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d9c2-254">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4d9c2-254">See Also</span></span>  
 <span data-ttu-id="4d9c2-255">[Utilitário sqlcmd](../../tools/sqlcmd-utility.md) </span><span class="sxs-lookup"><span data-stu-id="4d9c2-255">[sqlcmd Utility](../../tools/sqlcmd-utility.md) </span></span>  
 <span data-ttu-id="4d9c2-256">[Usar sqlcmd com variáveis de script](sqlcmd-use-with-scripting-variables.md) </span><span class="sxs-lookup"><span data-stu-id="4d9c2-256">[Use sqlcmd with Scripting Variables](sqlcmd-use-with-scripting-variables.md) </span></span>  
 <span data-ttu-id="4d9c2-257">[Editar scripts SQLCMD com o Editor de Consultas](edit-sqlcmd-scripts-with-query-editor.md) </span><span class="sxs-lookup"><span data-stu-id="4d9c2-257">[Edit SQLCMD Scripts with Query Editor](edit-sqlcmd-scripts-with-query-editor.md) </span></span>  
 <span data-ttu-id="4d9c2-258">[Gerenciar etapas de trabalho](../../ssms/agent/manage-job-steps.md) </span><span class="sxs-lookup"><span data-stu-id="4d9c2-258">[Manage Job Steps](../../ssms/agent/manage-job-steps.md) </span></span>  
 [<span data-ttu-id="4d9c2-259">Criar uma etapa de trabalho CmdExec</span><span class="sxs-lookup"><span data-stu-id="4d9c2-259">Create a CmdExec Job Step</span></span>](../../ssms/agent/create-a-cmdexec-job-step.md)  
  
  
