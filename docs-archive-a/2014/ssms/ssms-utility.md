---
title: Utilitário de SSMS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], opening
- command prompt utilities [SQL Server], sqlwb
- sqlwb utility
- Management Studio command line
- opening SQL Server Management Studio
ms.assetid: aafda520-9e2a-4e1e-b936-1b165f1684e8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0cfc9469e49e6ce3839d02a61477b8957fbc13e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582759"
---
# <a name="ssms-utility"></a><span data-ttu-id="5dabe-102">Utilitário de Ssms</span><span class="sxs-lookup"><span data-stu-id="5dabe-102">Ssms Utility</span></span>
  <span data-ttu-id="5dabe-103">O utilitário **Ssms**abre o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5dabe-103">The **Ssms**utility opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="5dabe-104">Se especificado, o **Ssms** também estabelece uma conexão com um servidor e abre consultas, scripts, arquivos, projetos e soluções.</span><span class="sxs-lookup"><span data-stu-id="5dabe-104">If specified, **Ssms** also establishes a connection to a server, and opens queries, scripts, files, projects, and solutions.</span></span>  
  
 <span data-ttu-id="5dabe-105">Você pode especificar arquivos que contenham consultas, projetos ou soluções.</span><span class="sxs-lookup"><span data-stu-id="5dabe-105">You can specify files that contain queries, projects, or solutions.</span></span> <span data-ttu-id="5dabe-106">Arquivos que contêm consultas serão conectados automaticamente a um servidor se a informação de conexão for fornecida e o tipo de arquivo for associado com aquele tipo de servidor.</span><span class="sxs-lookup"><span data-stu-id="5dabe-106">Files that contain queries are automatically connected to a server if connection information is provided and the file type is associated with that type of server.</span></span> <span data-ttu-id="5dabe-107">Por exemplo, arquivos .sql abrirão uma janela Editor de Consultas SQL em [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]e arquivos .mdx abrirão uma janela Editor de Consultas MDX em [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5dabe-107">For instance, .sql files will open a SQL Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], and .mdx files will open an MDX Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="5dabe-108">**Soluções e Projetos do SQL Server** serão abertos no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5dabe-108">**SQL Server Solutions and Projects** will open in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5dabe-109">O utilitário **Ssms** não executa consultas.</span><span class="sxs-lookup"><span data-stu-id="5dabe-109">The **Ssms** utility does not run queries.</span></span> <span data-ttu-id="5dabe-110">Para executar consultas da linha de comando, use o utilitário **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="5dabe-110">To run queries from the command line, use the **sqlcmd** utility.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dabe-111">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5dabe-111">Syntax</span></span>  
  
```  
  
      Ssms  
    [scriptfile] [projectfile] [solutionfile]  
    [-Sservername] [-ddatabasename] [-Uusername] [-Ppassword]   
    [-E] [-nosplash] [-log[filename]?] [-?]  
```  
  
## <a name="arguments"></a><span data-ttu-id="5dabe-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5dabe-112">Arguments</span></span>  
 <span data-ttu-id="5dabe-113">*scriptfile*</span><span class="sxs-lookup"><span data-stu-id="5dabe-113">*scriptfile*</span></span>  
 <span data-ttu-id="5dabe-114">Especifica um ou mais arquivos de script para serem abertos.</span><span class="sxs-lookup"><span data-stu-id="5dabe-114">Specifies one or more script files to open.</span></span> <span data-ttu-id="5dabe-115">O parâmetro deve conter o caminho completo para os arquivos.</span><span class="sxs-lookup"><span data-stu-id="5dabe-115">The parameter must contain the full path to the files.</span></span>  
  
 <span data-ttu-id="5dabe-116">*projectfile*</span><span class="sxs-lookup"><span data-stu-id="5dabe-116">*projectfile*</span></span>  
 <span data-ttu-id="5dabe-117">Especifica um projeto de script para ser aberto.</span><span class="sxs-lookup"><span data-stu-id="5dabe-117">Specifies a script project to open.</span></span> <span data-ttu-id="5dabe-118">O parâmetro deve conter o caminho completo para o arquivo de projeto de script.</span><span class="sxs-lookup"><span data-stu-id="5dabe-118">The parameter must contain the full path to the script project file.</span></span>  
  
 <span data-ttu-id="5dabe-119">*solutionfile*</span><span class="sxs-lookup"><span data-stu-id="5dabe-119">*solutionfile*</span></span>  
 <span data-ttu-id="5dabe-120">Especifica uma solução para ser aberta.</span><span class="sxs-lookup"><span data-stu-id="5dabe-120">Specifies a solution to open.</span></span> <span data-ttu-id="5dabe-121">O parâmetro deve conter o caminho completo para o arquivo de solução.</span><span class="sxs-lookup"><span data-stu-id="5dabe-121">The parameter must contain the full path to the solution file.</span></span>  
  
 <span data-ttu-id="5dabe-122">[**-S** _ServerName_]</span><span class="sxs-lookup"><span data-stu-id="5dabe-122">[**-S** _servername_]</span></span>  
 <span data-ttu-id="5dabe-123">Nome do servidor</span><span class="sxs-lookup"><span data-stu-id="5dabe-123">Server name</span></span>  
  
 <span data-ttu-id="5dabe-124">[**-d** _DatabaseName_]</span><span class="sxs-lookup"><span data-stu-id="5dabe-124">[**-d** _databasename_]</span></span>  
 <span data-ttu-id="5dabe-125">Nome do banco de dados</span><span class="sxs-lookup"><span data-stu-id="5dabe-125">Database name</span></span>  
  
 <span data-ttu-id="5dabe-126">[**-U** _username_]</span><span class="sxs-lookup"><span data-stu-id="5dabe-126">[**-U** _username_]</span></span>  
 <span data-ttu-id="5dabe-127">Nome de usuário ao conectar com a autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5dabe-127">User name when connecting with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication</span></span>  
  
 <span data-ttu-id="5dabe-128">[**-P** _senha_]</span><span class="sxs-lookup"><span data-stu-id="5dabe-128">[**-P** _password_]</span></span>  
 <span data-ttu-id="5dabe-129">Senha ao conectar-se com a autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5dabe-129">Password when connecting with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication</span></span>  
  
 <span data-ttu-id="5dabe-130">[**-E**]</span><span class="sxs-lookup"><span data-stu-id="5dabe-130">[**-E**]</span></span>  
 <span data-ttu-id="5dabe-131">Conectar usando a Autenticação do Windows</span><span class="sxs-lookup"><span data-stu-id="5dabe-131">Connect using Windows Authentication</span></span>  
  
 <span data-ttu-id="5dabe-132">[**-nosplash**]</span><span class="sxs-lookup"><span data-stu-id="5dabe-132">[**-nosplash**]</span></span>  
 <span data-ttu-id="5dabe-133">Impede o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] de exibir o gráfico da tela inicial ao abrir.</span><span class="sxs-lookup"><span data-stu-id="5dabe-133">Prevents [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from displaying the splash screen graphic while opening.</span></span> <span data-ttu-id="5dabe-134">Use essa opção ao conectar-se a um computador que executa o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] por meio de Serviços de Terminal em uma conexão com uma largura da banda limitada.</span><span class="sxs-lookup"><span data-stu-id="5dabe-134">Use this option when connecting to the computer running [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] by means of Terminal Services over a connection with a limited bandwidth.</span></span> <span data-ttu-id="5dabe-135">Este argumento não diferencia maiúsculas e minúsculas e pode ser exibido antes ou depois de outros argumentos</span><span class="sxs-lookup"><span data-stu-id="5dabe-135">This argument is not case-sensitive and may appear before or after other arguments</span></span>  
  
 <span data-ttu-id="5dabe-136">[**-log**_[filename]?_]</span><span class="sxs-lookup"><span data-stu-id="5dabe-136">[**-log**_[filename]?_]</span></span>  
 <span data-ttu-id="5dabe-137">Registra a atividade do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] no arquivo especificado para solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="5dabe-137">Logs [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] activity to the specified file for troubleshooting</span></span>  
  
 <span data-ttu-id="5dabe-138">[**-?**]</span><span class="sxs-lookup"><span data-stu-id="5dabe-138">[**-?**]</span></span>  
 <span data-ttu-id="5dabe-139">Exibe a ajuda de linha de comando</span><span class="sxs-lookup"><span data-stu-id="5dabe-139">Displays command line help</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5dabe-140">Comentários</span><span class="sxs-lookup"><span data-stu-id="5dabe-140">Remarks</span></span>  
 <span data-ttu-id="5dabe-141">Todas as alternâncias são opcionais e separadas por um espaço, exceto os arquivos que são separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="5dabe-141">All of the switches are optional and separated by a space except files which are separated by commas.</span></span> <span data-ttu-id="5dabe-142">Se você não especificar nenhuma alternância, o **Ssms** abrirá o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] como especificado nas configurações de **Opções** no menu **Ferramentas** .</span><span class="sxs-lookup"><span data-stu-id="5dabe-142">If you do not specify any switches, **Ssms** opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] as specified in the **Options** settings on the **Tools** menu.</span></span> <span data-ttu-id="5dabe-143">Por exemplo, se a página **Ambiente/Geral** na opção **Na inicialização** especificar **Abrir nova janela de consulta**, o **SSMS** será aberto com um Editor de Consultas em branco.</span><span class="sxs-lookup"><span data-stu-id="5dabe-143">For example, if the **Environment/General** page **At startup** option specifies **Open new query window**, **Ssms** will open with a blank Query Editor.</span></span>  
  
 <span data-ttu-id="5dabe-144">A opção **-log** deve aparecer no final da linha de comando, após todas as outras opções.</span><span class="sxs-lookup"><span data-stu-id="5dabe-144">The **-log** switch must appear at the end of the command line, after all other switches.</span></span> <span data-ttu-id="5dabe-145">O argumento de nome de arquivo é opcional.</span><span class="sxs-lookup"><span data-stu-id="5dabe-145">The filename argument is optional.</span></span> <span data-ttu-id="5dabe-146">Se um nome de arquivo for especificado, e o arquivo não existir, o arquivo será criado.</span><span class="sxs-lookup"><span data-stu-id="5dabe-146">If a filename is specified, and the file does not exist, the file is created.</span></span> <span data-ttu-id="5dabe-147">Se o arquivo não puder ser criado, por exemplo, devido à falta de acesso de gravação, o log será gravado na localização APPDATA não localizada (veja abaixo).</span><span class="sxs-lookup"><span data-stu-id="5dabe-147">If the file cannot be created - for example, due to insufficient write access, the log is written to the nonlocalized APPDATA location instead (See below).</span></span> <span data-ttu-id="5dabe-148">Se o argumento de nome de arquivo não for especificado, dois arquivos serão gravados na pasta de dados de aplicativo não localizada do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="5dabe-148">If the filename argument is not specified, two files are written to the current user's nonlocalized application data folder.</span></span> <span data-ttu-id="5dabe-149">A pasta de dados de aplicativo não localizada para o SQL Server pode ser encontrada na variável de ambiente de APPDATA.</span><span class="sxs-lookup"><span data-stu-id="5dabe-149">The nonlocalized application data folder for SQL Server can be found from the APPDATA environment variable.</span></span> <span data-ttu-id="5dabe-150">Por exemplo, para SQL Server 2012, a pasta é \<system drive> : \users \\<username \> \AppData\Roaming\Microsoft\AppEnv\10.0 \\ .</span><span class="sxs-lookup"><span data-stu-id="5dabe-150">For example, for SQL Server 2012, the folder is \<system drive>:\Users\\<username\>\AppData\Roaming\Microsoft\AppEnv\10.0\\.</span></span> <span data-ttu-id="5dabe-151">Os dois arquivos são, por padrão, chamados de ActivityLog.xml e ActivityLog.xsl.</span><span class="sxs-lookup"><span data-stu-id="5dabe-151">The two files are, by default, named ActivityLog.xml and ActivityLog.xsl.</span></span> <span data-ttu-id="5dabe-152">O primeiro contém os dados de log de atividade e o segundo é uma folha de estilo XML que fornece uma maneira mais conveniente de exibir o arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="5dabe-152">The former contains the activity log data and the latter is an XML style sheet which provides a more convenient way to view the XML file.</span></span> <span data-ttu-id="5dabe-153">Use as etapas a seguir para exibir o arquivo de log no Visualizador de XML padrão, como o Internet Explorer: clique em Iniciar, clique em executar... ", digite" \<system drive> : \users \\<nome de usuário \>\AppData\Roaming\Microsoft\AppEnv\10.0\ActivityLog.xml "no campo fornecido e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="5dabe-153">Use the following steps to view the log file in your default XML viewer, like Internet Explorer:  Click Start, then click Run...", then type "\<system drive>:\Users\\<username\>\AppData\Roaming\Microsoft\AppEnv\10.0\ActivityLog.xml" into the field provided, and then press Enter.</span></span>  
  
 <span data-ttu-id="5dabe-154">Arquivos que contenham consultas solicitarão para serem conectados a um servidor se a informação de conexão for fornecida e o tipo de arquivo for associado com o tipo de servidor.</span><span class="sxs-lookup"><span data-stu-id="5dabe-154">Files that contain queries will prompt to be connected to a server if connection information is provided and the file type is associated with that type of server.</span></span> <span data-ttu-id="5dabe-155">Por exemplo, arquivos .sql abrirão uma janela Editor de Consultas SQL em [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]e arquivos .mdx abrirão uma janela Editor de Consultas MDX em [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5dabe-155">For instance, .sql files will open a SQL Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], and .mdx files will open an MDX Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="5dabe-156">**Soluções e Projetos do SQL Server** serão abertos no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5dabe-156">**SQL Server Solutions and Projects** will open in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="5dabe-157">A tabela a seguir mapeia os tipos de servidor para extensões de arquivo.</span><span class="sxs-lookup"><span data-stu-id="5dabe-157">The following table maps server types to file extensions.</span></span>  
  
|<span data-ttu-id="5dabe-158">Tipo de servidor</span><span class="sxs-lookup"><span data-stu-id="5dabe-158">Server type</span></span>|<span data-ttu-id="5dabe-159">Extensão</span><span class="sxs-lookup"><span data-stu-id="5dabe-159">Extension</span></span>|  
|-----------------|---------------|  
|[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]|<span data-ttu-id="5dabe-160">.sql</span><span class="sxs-lookup"><span data-stu-id="5dabe-160">.sql</span></span>|  
|<span data-ttu-id="5dabe-161">SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="5dabe-161">SQL Server Analysis Services</span></span>|<span data-ttu-id="5dabe-162">.mdx</span><span class="sxs-lookup"><span data-stu-id="5dabe-162">.mdx</span></span><br /><br /> <span data-ttu-id="5dabe-163">.xmla</span><span class="sxs-lookup"><span data-stu-id="5dabe-163">.xmla</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="5dabe-164">Exemplos</span><span class="sxs-lookup"><span data-stu-id="5dabe-164">Examples</span></span>  
 <span data-ttu-id="5dabe-165">O script seguinte abre o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] em um prompt de comando com as configurações padrão:</span><span class="sxs-lookup"><span data-stu-id="5dabe-165">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt with the default settings:</span></span>  
  
```  
Ssms  
  
```  
  
 <span data-ttu-id="5dabe-166">O script seguinte abre o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] em um prompt de comando, com Autenticação do Windows, com o Editor de Código definido para o servidor `ACCTG and the database AdventureWorks2012,` sem mostrar a tela inicial:</span><span class="sxs-lookup"><span data-stu-id="5dabe-166">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt, with Windows Authentication, with the Code Editor set to the server `ACCTG and the database AdventureWorks2012,` without showing the splash screen:</span></span>  
  
```  
Ssms -E -S ACCTG -d AdventureWorks2012 -nosplash  
  
```  
  
 <span data-ttu-id="5dabe-167">O script seguinte abre o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] em um prompt de comando, e abre o script MonthEndQuery.</span><span class="sxs-lookup"><span data-stu-id="5dabe-167">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt, and opens the MonthEndQuery script.</span></span>  
  
```  
Ssms "C:\Documents and Settings\username\My Documents\SQL Server Management Studio Projects\FinanceScripts\FinanceScripts\MonthEndQuery.sql"  
  
```  
  
 <span data-ttu-id="5dabe-168">O script seguinte abre o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] em um prompt de comando e abre o projeto NewReportsProject no computador nomeado de `developer`:</span><span class="sxs-lookup"><span data-stu-id="5dabe-168">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt, and opens the NewReportsProject project on the computer named `developer`:</span></span>  
  
```  
Ssms "\\developer\fin\ReportProj\ReportProj\NewReportProj.ssmssqlproj"  
  
```  
  
 <span data-ttu-id="5dabe-169">O script seguinte abre o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] em um prompt de comando e abre a solução MonthlyReports:</span><span class="sxs-lookup"><span data-stu-id="5dabe-169">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt, and opens the MonthlyReports solution:</span></span>  
  
```  
Ssms "C:\solutionsfolder\ReportProj\MonthlyReports.ssmssln"  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="5dabe-170">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5dabe-170">See Also</span></span>  
 [<span data-ttu-id="5dabe-171">Usar o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5dabe-171">Use SQL Server Management Studio</span></span>](../database-engine/use-sql-server-management-studio.md)  
  
  
