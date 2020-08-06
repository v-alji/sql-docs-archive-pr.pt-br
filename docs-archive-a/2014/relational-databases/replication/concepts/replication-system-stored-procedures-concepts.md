---
title: Conceitos de procedimentos armazenados do sistema de replicação | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- stored procedures [SQL Server replication], programming
- programming [SQL Server replication], system stored procedures
- programming interfaces [SQL Server replication]
- system stored procedures [SQL Server replication]
- replication [SQL Server], how-to topics
ms.assetid: 816d2bda-ed72-43ec-aa4d-7ee3dc25fd8a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 50536e5b6816c84dff26c9c9f99c46d02272b7de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685572"
---
# <a name="replication-system-stored-procedures-concepts"></a><span data-ttu-id="c68ab-102">Replication System Stored Procedures Concepts</span><span class="sxs-lookup"><span data-stu-id="c68ab-102">Replication System Stored Procedures Concepts</span></span>
  <span data-ttu-id="c68ab-103">Em [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], o acesso programático a toda a funcionalidade configurável pelo usuário em uma topologia de replicação é fornecido por procedimentos armazenados do sistema.</span><span class="sxs-lookup"><span data-stu-id="c68ab-103">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], programmatic access to all of the user-configurable functionality in a replication topology is provided by system stored procedures.</span></span> <span data-ttu-id="c68ab-104">Embora os procedimentos armazenados possam ser executados individualmente por meio do [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou do utilitário de linha de comando sqlcmd, pode ser útil gravar arquivos de script [!INCLUDE[tsql](../../../includes/tsql-md.md)] que possam ser executados para a criação de uma sequência lógica de tarefas de replicação.</span><span class="sxs-lookup"><span data-stu-id="c68ab-104">While stored procedures may be executed individually using the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or the sqlcmd command-line utility, it may be beneficial to write [!INCLUDE[tsql](../../../includes/tsql-md.md)] script files that can be executed to perform a logical sequence of replication tasks.</span></span>  
  
 <span data-ttu-id="c68ab-105">A criação de scripts para as tarefas de replicação oferece os seguintes benefícios:</span><span class="sxs-lookup"><span data-stu-id="c68ab-105">Scripting replication tasks provides the following benefits:</span></span>  
  
-   <span data-ttu-id="c68ab-106">Mantém uma cópia permanente das etapas usadas na implantação da sua topologia de replicação.</span><span class="sxs-lookup"><span data-stu-id="c68ab-106">Keeps a permanent copy of the steps used to deploy your replication topology.</span></span>  
  
-   <span data-ttu-id="c68ab-107">Usa um único script para configurar vários Assinantes.</span><span class="sxs-lookup"><span data-stu-id="c68ab-107">Uses a single script to configure multiple Subscribers.</span></span>  
  
-   <span data-ttu-id="c68ab-108">Educa rapidamente os administradores de banco de dados novos, permitindo que eles avaliem, compreendam, alterem o código ou solucionem seus problemas.</span><span class="sxs-lookup"><span data-stu-id="c68ab-108">Quickly educates new database administrators by enabling them to evaluate, understand, change, or troubleshoot the code.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="c68ab-109">Os scripts podem ser a fonte de vulnerabilidades de segurança; podem invocar funções de sistema sem o conhecimento ou a intervenção do usuário e conter credenciais de segurança em texto sem-formatação.</span><span class="sxs-lookup"><span data-stu-id="c68ab-109">Scripts can be the source of security vulnerabilities; they can invoke system functions without user knowledge or intervention and may contain security credentials in plain text.</span></span> <span data-ttu-id="c68ab-110">Analise os scripts para procurar problemas de segurança antes de usá-los.</span><span class="sxs-lookup"><span data-stu-id="c68ab-110">Review scripts for security issues before you use them.</span></span>  
  
## <a name="creating-replication-scripts"></a><span data-ttu-id="c68ab-111">Criando scripts de replicação</span><span class="sxs-lookup"><span data-stu-id="c68ab-111">Creating Replication Scripts</span></span>  
 <span data-ttu-id="c68ab-112">Do ponto de vista de replicação, um script é uma série de uma ou mais instruções [!INCLUDE[tsql](../../../includes/tsql-md.md)], onde cada instrução executa um procedimento armazenado de replicação.</span><span class="sxs-lookup"><span data-stu-id="c68ab-112">From the standpoint of replication, a script is a series of one or more [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements where each statement executes a replication stored procedure.</span></span> <span data-ttu-id="c68ab-113">Os scripts são arquivos de texto, geralmente com uma extensão de arquivo .sql, que podem ser executados com o utilitário sqlcmd.</span><span class="sxs-lookup"><span data-stu-id="c68ab-113">Scripts are text files, often with a .sql file extension, that can be run using the sqlcmd utility.</span></span> <span data-ttu-id="c68ab-114">Quando um arquivo de script é executado, o utilitário executa as instruções SQL armazenadas nele.</span><span class="sxs-lookup"><span data-stu-id="c68ab-114">When a script file is run, the utility executes the SQL statements stored in the file.</span></span> <span data-ttu-id="c68ab-115">De forma similar, um script pode ser armazenado como um objeto de consulta em um projeto do [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c68ab-115">Similarly, a script can be stored as a query object in a [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] project.</span></span>  
  
 <span data-ttu-id="c68ab-116">os scripts de replicação podem ser criados das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="c68ab-116">Replication scripts can be created in the following ways:</span></span>  
  
-   <span data-ttu-id="c68ab-117">Crie o script manualmente.</span><span class="sxs-lookup"><span data-stu-id="c68ab-117">Manually create the script.</span></span>  
  
-   <span data-ttu-id="c68ab-118">Use os recursos de geração de script fornecidos nos assistentes de replicação ou</span><span class="sxs-lookup"><span data-stu-id="c68ab-118">Use the script generation features that are provided in the replication wizards or</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="c68ab-119">.</span><span class="sxs-lookup"><span data-stu-id="c68ab-119">.</span></span> <span data-ttu-id="c68ab-120">Para obter mais informações, consulte [Scripting Replication](../scripting-replication.md).</span><span class="sxs-lookup"><span data-stu-id="c68ab-120">For more information, see [Scripting Replication](../scripting-replication.md).</span></span>  
  
-   <span data-ttu-id="c68ab-121">Use os RMOs (Replication Management Objects) para gerar o script programaticamente e criar um objeto de RMO.</span><span class="sxs-lookup"><span data-stu-id="c68ab-121">Use Replication Management Objects (RMOs) to programmatically generate the script to create an RMO object.</span></span>  
  
 <span data-ttu-id="c68ab-122">Quando você cria scripts de replicação manualmente, tenha em mente as seguintes considerações:</span><span class="sxs-lookup"><span data-stu-id="c68ab-122">When you manually create replication scripts, keep the following considerations in mind:</span></span>  
  
-   <span data-ttu-id="c68ab-123">Os scripts [!INCLUDE[tsql](../../../includes/tsql-md.md)] têm um ou mais lotes.</span><span class="sxs-lookup"><span data-stu-id="c68ab-123">[!INCLUDE[tsql](../../../includes/tsql-md.md)] scripts have one or more batches.</span></span> <span data-ttu-id="c68ab-124">O comando GO sinaliza o término de um lote.</span><span class="sxs-lookup"><span data-stu-id="c68ab-124">The GO command signals the end of a batch.</span></span> <span data-ttu-id="c68ab-125">Se um script [!INCLUDE[tsql](../../../includes/tsql-md.md)] não tiver nenhum comando GO, ele será executado como um único lote.</span><span class="sxs-lookup"><span data-stu-id="c68ab-125">If a [!INCLUDE[tsql](../../../includes/tsql-md.md)] script does not have any GO commands, it is executed as a single batch.</span></span>  
  
-   <span data-ttu-id="c68ab-126">Na execução de vários procedimentos armazenados de replicação em um único lote, após o primeiro procedimento, todos os procedimentos subsequentes do lote terão de ser precedidos pela palavra-chave EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="c68ab-126">When executing multiple replication stored procedures in a single batch, after the first procedure, all subsequent procedures in the batch must be preceded by the EXECUTE keyword.</span></span>  
  
-   <span data-ttu-id="c68ab-127">Todos os procedimentos armazenados de um lote devem ser compilados antes da execução do lote.</span><span class="sxs-lookup"><span data-stu-id="c68ab-127">All stored procedures in a batch must compile before a batch will execute.</span></span> <span data-ttu-id="c68ab-128">No entanto, após a compilação do lote, e após a criação do plano de execução, poderá ou não ocorrer um erro em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="c68ab-128">However, once the batch has been compiled, and an execution plan has been created, a run-time error may or may not occur.</span></span>  
  
-   <span data-ttu-id="c68ab-129">Ao criar scripts para configurar a replicação, use a Autenticação do Windows para evitar o armazenamento de credenciais de segurança no arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="c68ab-129">When creating scripts to configure replication, you should use Windows Authentication to avoid storing security credentials in the script file.</span></span> <span data-ttu-id="c68ab-130">Se for necessário armazenar credenciais em um arquivo de script, você deverá proteger o arquivo para impedir acesso não autorizado.</span><span class="sxs-lookup"><span data-stu-id="c68ab-130">If you must store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
## <a name="sample-replication-script"></a><span data-ttu-id="c68ab-131">Script de replicação de exemplo</span><span class="sxs-lookup"><span data-stu-id="c68ab-131">Sample Replication Script</span></span>  
 <span data-ttu-id="c68ab-132">O script a seguir pode ser executado para configurar a publicação e a distribuição em um servidor.</span><span class="sxs-lookup"><span data-stu-id="c68ab-132">The following script can be executed to setup publishing and distribution on a server.</span></span>  
  
```  
-- This script uses sqlcmd scripting variables. They are in the form  
-- $(MyVariable). For information about how to use scripting variables    
-- on the command line and in SQL Server Management Studio, see the   
-- "Executing Replication Scripts" section in the topic  
-- "Programming Replication Using System Stored Procedures".  
  
-- Install the Distributor and the distribution database.  
DECLARE @distributor AS sysname;  
DECLARE @distributionDB AS sysname;  
DECLARE @publisher AS sysname;  
DECLARE @directory AS nvarchar(500);  
DECLARE @publicationDB AS sysname;  
-- Specify the Distributor name.  
SET @distributor = $(DistPubServer);  
-- Specify the distribution database.  
SET @distributionDB = N'distribution';  
-- Specify the Publisher name.  
SET @publisher = $(DistPubServer);  
-- Specify the replication working directory.  
SET @directory = N'\\' + $(DistPubServer) + '\repldata';  
-- Specify the publication database.  
SET @publicationDB = N'AdventureWorks2012';   
  
-- Install the server MYDISTPUB as a Distributor using the defaults,  
-- including autogenerating the distributor password.  
USE master  
EXEC sp_adddistributor @distributor = @distributor;  
  
-- Create a new distribution database using the defaults, including  
-- using Windows Authentication.  
USE master  
EXEC sp_adddistributiondb @database = @distributionDB,   
    @security_mode = 1;  
GO  
  
-- Create a Publisher and enable AdventureWorks2012 for replication.  
-- Add MYDISTPUB as a publisher with MYDISTPUB as a local distributor  
-- and use Windows Authentication.  
DECLARE @distributionDB AS sysname;  
DECLARE @publisher AS sysname;  
-- Specify the distribution database.  
SET @distributionDB = N'distribution';  
-- Specify the Publisher name.  
SET @publisher = $(DistPubServer);  
  
USE [distribution]  
EXEC sp_adddistpublisher @publisher=@publisher,   
    @distribution_db=@distributionDB,   
    @security_mode = 1;  
GO  
  
```  
  
 <span data-ttu-id="c68ab-133">Dessa forma, esse script poderá ser salvo localmente como `instdistpub.sql`, para que possa ser executado ou executado novamente quando necessário.</span><span class="sxs-lookup"><span data-stu-id="c68ab-133">This script can then be saved locally as `instdistpub.sql` so that it can be run or rerun when needed.</span></span>  
  
 <span data-ttu-id="c68ab-134">O script anterior inclui variáveis de script **sqlcmd**, usadas em muitos dos códigos de replicação de exemplo dos Manuais Online do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c68ab-134">The previous script includes **sqlcmd** scripting variables, which are used in many of the replication code samples in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="c68ab-135">As variáveis de script são definidas por meio da sintaxe `$(MyVariable)`.</span><span class="sxs-lookup"><span data-stu-id="c68ab-135">Scripting variables are defined by using `$(MyVariable)` syntax.</span></span> <span data-ttu-id="c68ab-136">Os valores das variáveis podem ser transmitidos para um script na linha de comando ou no [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c68ab-136">Values for variables can be passed to a script at the command line or in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="c68ab-137">Para obter mais informações, consulte a próxima seção deste tópico, "Executando scripts de replicação".</span><span class="sxs-lookup"><span data-stu-id="c68ab-137">For more information, see the next section in this topic, "Executing Replication Scripts."</span></span>  
  
## <a name="executing-replication-scripts"></a><span data-ttu-id="c68ab-138">Executando scripts de replicação</span><span class="sxs-lookup"><span data-stu-id="c68ab-138">Executing Replication Scripts</span></span>  
 <span data-ttu-id="c68ab-139">Uma vez criado, um script de replicação pode ser executado de uma das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="c68ab-139">Once created, a replication script can be executed in one of the following ways:</span></span>  
  
### <a name="creating-a-sql-query-file-in-sql-server-management-studio"></a><span data-ttu-id="c68ab-140">Criando um arquivo de consulta SQL no SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c68ab-140">Creating a SQL Query File in SQL Server Management Studio</span></span>  
 <span data-ttu-id="c68ab-141">Um arquivo de script de replicação [!INCLUDE[tsql](../../../includes/tsql-md.md)] pode ser criado como um arquivo SQL Query em um projeto do [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c68ab-141">A replication [!INCLUDE[tsql](../../../includes/tsql-md.md)] script file can be created as a SQL Query file in a [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] project.</span></span> <span data-ttu-id="c68ab-142">Após a gravação do script, pode ser feita uma conexão ao banco de dados para que esse arquivo de consulta e o script possam ser executados.</span><span class="sxs-lookup"><span data-stu-id="c68ab-142">After the script is written, a connection can be made to the database for this query file and the script can be executed.</span></span> <span data-ttu-id="c68ab-143">Para obter mais informações sobre como criar [!INCLUDE[tsql](../../../includes/tsql-md.md)] scripts usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , consulte [editores de consulta e de texto &#40;SQL Server Management Studio&#41;](../../scripting/query-and-text-editors-sql-server-management-studio.md)).</span><span class="sxs-lookup"><span data-stu-id="c68ab-143">For more information about how to create [!INCLUDE[tsql](../../../includes/tsql-md.md)] scripts by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], see [Query and Text Editors &#40;SQL Server Management Studio&#41;](../../scripting/query-and-text-editors-sql-server-management-studio.md)).</span></span>  
  
 <span data-ttu-id="c68ab-144">Para usar um script que inclua variáveis de script, o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] deve ser executado em modo **sqlcmd**.</span><span class="sxs-lookup"><span data-stu-id="c68ab-144">To use a script that includes scripting variables, [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] must be running in **sqlcmd** mode.</span></span> <span data-ttu-id="c68ab-145">Em modo **sqlcmd**, o Editor de Consultas aceita sintaxe adicional específica do **sqlcmd**, como `:setvar`, usado para um valor de uma variável.</span><span class="sxs-lookup"><span data-stu-id="c68ab-145">In **sqlcmd** mode, the Query Editor accepts additional syntax specific to **sqlcmd**, such as `:setvar`, which is used to a value for a variable.</span></span> <span data-ttu-id="c68ab-146">Para obter mais informações sobre o modo **sqlcmd**, consulte [Editar scripts SQLCMD com o Editor de Consultas](../../scripting/edit-sqlcmd-scripts-with-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="c68ab-146">For more information about **sqlcmd** mode, see [Edit SQLCMD Scripts with Query Editor](../../scripting/edit-sqlcmd-scripts-with-query-editor.md).</span></span> <span data-ttu-id="c68ab-147">No script a seguir, `:setvar` é usado para fornecer um valor para a variável `$(DistPubServer)`.</span><span class="sxs-lookup"><span data-stu-id="c68ab-147">In the following script, `:setvar` is used to provide a value for the `$(DistPubServer)` variable.</span></span>  
  
```  
:setvar DistPubServer N'MyPublisherAndDistributor';  
  
-- Install the Distributor and the distribution database.  
DECLARE @distributor AS sysname;  
DECLARE @distributionDB AS sysname;  
DECLARE @publisher AS sysname;  
DECLARE @directory AS nvarchar(500);  
DECLARE @publicationDB AS sysname;  
-- Specify the Distributor name.  
SET @distributor = $(DistPubServer);  
-- Specify the distribution database.  
SET @distributionDB = N'distribution';  
-- Specify the Publisher name.  
SET @publisher = $(DistPubServer);  
  
--  
-- Additional code goes here  
--  
```  
  
### <a name="using-the-sqlcmd-utility-from-the-command-line"></a><span data-ttu-id="c68ab-148">Usando o utilitário sqlcmd na linha de comando</span><span class="sxs-lookup"><span data-stu-id="c68ab-148">Using the sqlcmd Utility from the Command Line</span></span>  
 <span data-ttu-id="c68ab-149">O exemplo a seguir mostra como a linha de comando é usada para executar o arquivo de script `instdistpub.sql` por meio do [utilitário sqlcmd](../../../tools/sqlcmd-utility.md):</span><span class="sxs-lookup"><span data-stu-id="c68ab-149">The following example shows how the command line is used to execute the `instdistpub.sql` script file using the [sqlcmd utility](../../../tools/sqlcmd-utility.md):</span></span>  
  
```  
sqlcmd.exe -E -S sqlserverinstance -i C:\instdistpub.sql -o C:\output.log -v DistPubServer="N'MyDistributorAndPublisher'"  
```  
  
 <span data-ttu-id="c68ab-150">Neste exemplo, a opção `-E` indica que a Autenticação do Windows será usada na conexão ao [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c68ab-150">In this example, the `-E` switch indicates that Windows Authentication is used when connecting to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c68ab-151">Quando a Autenticação do Windows for usada, não haverá necessidade de armazenar um nome de usuário e uma senha no arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="c68ab-151">When using Windows Authentication, there is no need to store a username and password in the script file.</span></span> <span data-ttu-id="c68ab-152">O nome e o caminho do arquivo de script são especificados pela opção `-i` e o nome do arquivo de saída é especificado pela opção `-o` (a saída do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] será gravada nesse arquivo em vez de no console quando essa opção for usada).</span><span class="sxs-lookup"><span data-stu-id="c68ab-152">The name and path of the script file is specified by the `-i` switch and the name of the output file is specified by the `-o` switch (output from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is written to this file instead of the console when this switch is used).</span></span> <span data-ttu-id="c68ab-153">O utilitário `sqlcmd` permite que você transmita variáveis de script para um script [!INCLUDE[tsql](../../../includes/tsql-md.md)] em runtime por meio da opção `-v`.</span><span class="sxs-lookup"><span data-stu-id="c68ab-153">The `sqlcmd` utility enables you to pass scripting variables to a [!INCLUDE[tsql](../../../includes/tsql-md.md)] script at runtime using the `-v` switch.</span></span> <span data-ttu-id="c68ab-154">Neste exemplo, `sqlcmd` substitui todas as instâncias de `$(DistPubServer)` do script pela valor `N'MyDistributorAndPublisher'` antes da execução.</span><span class="sxs-lookup"><span data-stu-id="c68ab-154">In this example, `sqlcmd` replaces every instance of `$(DistPubServer)` in the script with the value `N'MyDistributorAndPublisher'` before execution.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c68ab-155">A opção `-X` desabilita variáveis de script.</span><span class="sxs-lookup"><span data-stu-id="c68ab-155">The `-X` switch disables scripting variables.</span></span>  
  
### <a name="automating-tasks-in-a-batch-file"></a><span data-ttu-id="c68ab-156">Automatizando tarefas em um arquivo em lotes</span><span class="sxs-lookup"><span data-stu-id="c68ab-156">Automating Tasks in a Batch File</span></span>  
 <span data-ttu-id="c68ab-157">Com a utilização de um arquivo em lotes, as tarefas de administração de replicação, as tarefas de sincronização de replicação e outras tarefas podem ser automatizadas no mesmo arquivo em lotes.</span><span class="sxs-lookup"><span data-stu-id="c68ab-157">By using a batch file, replication administration tasks, replication synchronization tasks, and other tasks can be automated in the same batch file.</span></span> <span data-ttu-id="c68ab-158">O arquivo em lotes a seguir usa o utilitário **sqlcmd** para remover e recriar o banco de dados de assinatura e para adicionar uma assinatura pull de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="c68ab-158">The following batch file uses the **sqlcmd** utility to drop and recreate the subscription database and add a merge pull subscription.</span></span> <span data-ttu-id="c68ab-159">Em seguida, o arquivo invocará o agente de mesclagem para sincronizar a assinatura nova:</span><span class="sxs-lookup"><span data-stu-id="c68ab-159">Then the file invokes the merge agent to synchronize the new subscription:</span></span>  
  
```  
REM ----------------------Script to synchronize merge subscription ----------------------  
REM -- Creates subscription database and   
REM -- synchronizes the subscription to MergeSalesPerson.  
REM -- Current computer acts as both Publisher and Subscriber.  
REM -------------------------------------------------------------------------------------  
  
SET Publisher=%computername%  
SET Subscriber=%computername%  
SET PubDb=AdventureWorks  
SET SubDb=AdventureWorksReplica  
SET PubName=AdvWorksSalesOrdersMerge  
  
REM -- Drop and recreate the subscription database at the Subscriber  
sqlcmd /S%Subscriber% /E /Q"USE master IF EXISTS (SELECT * FROM sysdatabases WHERE name='%SubDb%' ) DROP DATABASE %SubDb%"  
sqlcmd /S%Subscriber% /E /Q"USE master CREATE DATABASE %SubDb%"  
  
REM -- Add a pull subscription at the Subscriber  
sqlcmd /S%Subscriber% /E /Q"USE %SubDb% EXEC sp_addmergepullsubscription @publisher = %Publisher%, @publication = %PubName%, @publisher_db = %PubDb%"  
sqlcmd /S%Subscriber% /E /Q"USE %SubDb%  EXEC sp_addmergepullsubscription_agent @publisher = %Publisher%, @publisher_db = %PubDb%, @publication = %PubName%, @subscriber = %Subscriber%, @subscriber_db = %SubDb%, @distributor = %Publisher%"  
  
REM -- This batch file starts the merge agent at the Subscriber to   
REM -- synchronize a pull subscription to a merge publication.  
REM -- The following must be supplied on one line.  
"\Program Files\Microsoft SQL Server\120\COM\REPLMERG.EXE"  -Publisher  %Publisher% -Subscriber  %Subscriber%  -Distributor %Publisher%  -PublisherDB  %PubDb% -SubscriberDB %SubDb% -Publication %PubName% -PublisherSecurityMode 1 -OutputVerboseLevel 1  -Output  -SubscriberSecurityMode 1  -SubscriptionType 1 -DistributorSecurityMode 1 -Validate 3  
  
```  
  
## <a name="scripting-common-replication-tasks"></a><span data-ttu-id="c68ab-160">Gerando scripts de tarefas comuns de replicação</span><span class="sxs-lookup"><span data-stu-id="c68ab-160">Scripting Common Replication Tasks</span></span>  
 <span data-ttu-id="c68ab-161">A seguir, algumas das tarefas de replicação mais comuns que podem ser incluídas em um script por meio de procedimentos armazenados do sistema:</span><span class="sxs-lookup"><span data-stu-id="c68ab-161">The following are some of the most common replication tasks can be scripted using system stored procedures:</span></span>  
  
-   <span data-ttu-id="c68ab-162">Configurando a publicação e a distribuição</span><span class="sxs-lookup"><span data-stu-id="c68ab-162">Configuring publishing and distribution</span></span>  
  
-   <span data-ttu-id="c68ab-163">Modificando as propriedades do Publicador e do Distribuidor</span><span class="sxs-lookup"><span data-stu-id="c68ab-163">Modifying Publisher and Distributor properties</span></span>  
  
-   <span data-ttu-id="c68ab-164">Desabilitando a publicação e a distribuição</span><span class="sxs-lookup"><span data-stu-id="c68ab-164">Disabling publishing and distribution</span></span>  
  
-   <span data-ttu-id="c68ab-165">Criando publicações e definindo artigos</span><span class="sxs-lookup"><span data-stu-id="c68ab-165">Creating publications and defining articles</span></span>  
  
-   <span data-ttu-id="c68ab-166">Excluindo publicações e artigos</span><span class="sxs-lookup"><span data-stu-id="c68ab-166">Deleting publications and articles</span></span>  
  
-   <span data-ttu-id="c68ab-167">Criando uma assinatura pull</span><span class="sxs-lookup"><span data-stu-id="c68ab-167">Creating a pull subscription</span></span>  
  
-   <span data-ttu-id="c68ab-168">Modificando uma assinatura pull</span><span class="sxs-lookup"><span data-stu-id="c68ab-168">Modifying a pull subscription</span></span>  
  
-   <span data-ttu-id="c68ab-169">Excluindo uma assinatura pull</span><span class="sxs-lookup"><span data-stu-id="c68ab-169">Deleting a pull subscription</span></span>  
  
-   <span data-ttu-id="c68ab-170">Criando uma assinatura push</span><span class="sxs-lookup"><span data-stu-id="c68ab-170">Creating a push subscription</span></span>  
  
-   <span data-ttu-id="c68ab-171">Modificando uma assinatura push</span><span class="sxs-lookup"><span data-stu-id="c68ab-171">Modifying a push subscription</span></span>  
  
-   <span data-ttu-id="c68ab-172">Excluindo uma assinatura push</span><span class="sxs-lookup"><span data-stu-id="c68ab-172">Deleting a push subscription</span></span>  
  
-   <span data-ttu-id="c68ab-173">Sincronizando uma assinatura pull</span><span class="sxs-lookup"><span data-stu-id="c68ab-173">Synchronizing a pull subscription</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c68ab-174">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c68ab-174">See Also</span></span>  
 <span data-ttu-id="c68ab-175">[Conceitos de programação da replicação](replication-programming-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="c68ab-175">[Replication Programming Concepts](replication-programming-concepts.md) </span></span>  
 <span data-ttu-id="c68ab-176">[Procedimentos armazenados de replicação &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c68ab-176">[Replication Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="c68ab-177">Replicação de script</span><span class="sxs-lookup"><span data-stu-id="c68ab-177">Scripting Replication</span></span>](../scripting-replication.md)  
  
  
