---
title: Conexões do SSIS (Integration Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, connections
- SSIS packages, connections
- sources [Integration Services], connections
- packages [Integration Services], connections
- destinations [Integration Services], connections
- tasks [Integration Services], connections
- connections [Integration Services], about connections
- connections [Integration Services]
- SQL Server Integration Services packages, connections
ms.assetid: 72f5afa3-d636-410b-9e81-2ffa27772a8c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b00cc850b5bcf8276976dd2faa825fe80a3bd3bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571507"
---
# <a name="integration-services-ssis-connections"></a><span data-ttu-id="6f79b-102">Conexões do SSIS (Integration Services)</span><span class="sxs-lookup"><span data-stu-id="6f79b-102">Integration Services (SSIS) Connections</span></span>
  <span data-ttu-id="6f79b-103">Os pacotes [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] usam conexões para executar diferentes tarefas e implementar recursos do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="6f79b-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages use connections to perform different tasks and to implement [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] features:</span></span>  
  
-   <span data-ttu-id="6f79b-104">Conectar com armazenamentos de dados de origem e de destino, como texto, XML, pastas de trabalho do Excel e bancos de dados relacionais para extrair e carregar dados.</span><span class="sxs-lookup"><span data-stu-id="6f79b-104">Connecting to source and destination data stores such as text, XML, Excel workbooks, and relational databases to extract and load data.</span></span>  
  
-   <span data-ttu-id="6f79b-105">Conectar com bancos de dados relacionais que contêm dados de referência para executar pesquisas exatas ou difusas.</span><span class="sxs-lookup"><span data-stu-id="6f79b-105">Connecting to relational databases that contain reference data to perform exact or fuzzy lookups.</span></span>  
  
-   <span data-ttu-id="6f79b-106">Conectar com bancos de dados relacionais para executar instruções SQL, como os comandos SELECT, DELETE e INSERT e também procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="6f79b-106">Connecting to relational databases to run SQL statements such as SELECT, DELETE, and INSERT commands and also stored procedures.</span></span>  
  
-   <span data-ttu-id="6f79b-107">Conectar com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para executar tarefas de manutenção e transferência, como backup de bancos de dados e transferência de logons.</span><span class="sxs-lookup"><span data-stu-id="6f79b-107">Connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to perform maintenance and transfer tasks such as backing up databases and transferring logins.</span></span>  
  
-   <span data-ttu-id="6f79b-108">Gravar entradas de log em arquivos de texto e XML e tabelas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e configurações de pacote em tabelas [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6f79b-108">Writing log entries in text and XML files and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables and package configurations to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables.</span></span>  
  
-   <span data-ttu-id="6f79b-109">Conectar com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para criar tabelas de trabalho temporárias, exigidas por algumas transformações para fazer o seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="6f79b-109">Connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to create temporary work tables that some transformations require to do their work.</span></span>  
  
-   <span data-ttu-id="6f79b-110">Conectar com projetos e bancos de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para acessar modelos de mineração de dados, cubos e dimensões de processo e para executar códigos DDL.</span><span class="sxs-lookup"><span data-stu-id="6f79b-110">Connecting to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projects and databases to access data mining models, process cubes and dimensions, and run DDL code.</span></span>  
  
-   <span data-ttu-id="6f79b-111">Especificar arquivos e pastas existentes ou criar novos para usar com enumeradores e tarefas Loop Foreach.</span><span class="sxs-lookup"><span data-stu-id="6f79b-111">Specifying existing or creating new files and folders to use with Foreach Loop enumerators and tasks.</span></span>  
  
-   <span data-ttu-id="6f79b-112">Conectar com filas de mensagens e com a WMI (Instrumentação de Gerenciamento do Windows), o SMO ( [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects), a Web e servidores de email.</span><span class="sxs-lookup"><span data-stu-id="6f79b-112">Connecting to message queues and to Windows Management Instrumentation (WMI), [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO), Web, and mail servers.</span></span>  
  
 <span data-ttu-id="6f79b-113">Para estabelecer essas conexões, o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] usa gerenciadores de conexões, conforme descrito na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="6f79b-113">To make these connections, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] uses connection managers, as described in the next section.</span></span>  
  
## <a name="connection-managers"></a><span data-ttu-id="6f79b-114">Gerenciadores de conexões</span><span class="sxs-lookup"><span data-stu-id="6f79b-114">Connection Managers</span></span>  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="6f79b-115">usa o gerenciador de conexões como uma representação lógica de uma conexão.</span><span class="sxs-lookup"><span data-stu-id="6f79b-115">uses the connection manager as a logical representation of a connection.</span></span> <span data-ttu-id="6f79b-116">Em tempo de design, você define as propriedades de um gerenciador de conexões para descrever a conexão física que o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] cria quando o pacote é executado.</span><span class="sxs-lookup"><span data-stu-id="6f79b-116">At design time, you set the properties of a connection manager to describe the physical connection that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates when the package runs.</span></span> <span data-ttu-id="6f79b-117">Por exemplo, um gerenciador de conexões inclui a propriedade `ConnectionString` que você define em tempo de design; em tempo de execução, uma conexão física é criada usando o valor na propriedade da cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="6f79b-117">For example, a connection manager includes the `ConnectionString` property that you set at design time; at run time, a physical connection is created using the value in the connection string property.</span></span>  
  
 <span data-ttu-id="6f79b-118">Um pacote pode usar várias instâncias de um tipo de gerenciador de conexões e você pode definir as propriedades em cada instância.</span><span class="sxs-lookup"><span data-stu-id="6f79b-118">A package can use multiple instances of a connection manager type, and you can set the properties on each instance.</span></span> <span data-ttu-id="6f79b-119">Em tempo de execução, cada instância de um tipo de gerenciador de conexões cria uma conexão que tem atributos diferentes.</span><span class="sxs-lookup"><span data-stu-id="6f79b-119">At run time, each instance of a connection manager type creates a connection that has different attributes.</span></span>  
  
 <span data-ttu-id="6f79b-120">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] fornece diferentes tipos de gerenciadores de conexões que permitem a conexão de pacotes com várias fontes de dados e servidores:</span><span class="sxs-lookup"><span data-stu-id="6f79b-120">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides different types of connection managers that enable packages to connect to a variety of data sources and servers:</span></span>  
  
-   <span data-ttu-id="6f79b-121">Há gerenciadores de conexões internos que a Instalação instala durante a instalação do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f79b-121">There are built-in connection managers that Setup installs when you install [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="6f79b-122">Há gerenciadores de conexões disponíveis para download no site da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6f79b-122">There are connection managers that are available for download from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] website.</span></span>  
  
-   <span data-ttu-id="6f79b-123">Você poderá criar seu próprio gerenciador de conexões personalizado se os gerenciadores de conexões existentes não atenderem às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="6f79b-123">You can create your own custom connection manager if the existing connection managers do not meet your needs.</span></span>  
  
### <a name="built-in-connection-managers"></a><span data-ttu-id="6f79b-124">Gerenciadores de conexões internos</span><span class="sxs-lookup"><span data-stu-id="6f79b-124">Built-in Connection Managers</span></span>  
 <span data-ttu-id="6f79b-125">A tabela a seguir lista os tipos de gerenciadores de conexões fornecidos pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f79b-125">The following table lists the connection manager types that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides.</span></span>  
  
|<span data-ttu-id="6f79b-126">Type</span><span class="sxs-lookup"><span data-stu-id="6f79b-126">Type</span></span>|<span data-ttu-id="6f79b-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="6f79b-127">Description</span></span>|<span data-ttu-id="6f79b-128">Tópico</span><span class="sxs-lookup"><span data-stu-id="6f79b-128">Topic</span></span>|  
|----------|-----------------|-----------|  
|<span data-ttu-id="6f79b-129">ADO</span><span class="sxs-lookup"><span data-stu-id="6f79b-129">ADO</span></span>|<span data-ttu-id="6f79b-130">Conecta-se a objetos ActiveX Data Objects (ADO).</span><span class="sxs-lookup"><span data-stu-id="6f79b-130">Connects to ActiveX Data Objects (ADO) objects.</span></span>|[<span data-ttu-id="6f79b-131">Gerenciador de conexões ADO</span><span class="sxs-lookup"><span data-stu-id="6f79b-131">ADO Connection Manager</span></span>](ado-connection-manager.md)|  
|<span data-ttu-id="6f79b-132">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6f79b-132">ADO.NET</span></span>|<span data-ttu-id="6f79b-133">Conecta-se a uma fonte de dados usando um provedor .NET.</span><span class="sxs-lookup"><span data-stu-id="6f79b-133">Connects to a data source by using a .NET provider.</span></span>|[<span data-ttu-id="6f79b-134">Gerenciador de conexões ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6f79b-134">ADO.NET Connection Manager</span></span>](ado-net-connection-manager.md)|  
|<span data-ttu-id="6f79b-135">CACHE</span><span class="sxs-lookup"><span data-stu-id="6f79b-135">CACHE</span></span>|<span data-ttu-id="6f79b-136">Lê dados do fluxo de dados ou de um arquivo de cache (.caw) e pode salvar esses dados em um arquivo de cache.</span><span class="sxs-lookup"><span data-stu-id="6f79b-136">Reads data from the data flow or from a cache file (.caw), and can save data to the cache file.</span></span>|[<span data-ttu-id="6f79b-137">Gerenciador de Conexões de Cache</span><span class="sxs-lookup"><span data-stu-id="6f79b-137">Cache Connection Manager</span></span>](cache-connection-manager.md)|  
|<span data-ttu-id="6f79b-138">DQS</span><span class="sxs-lookup"><span data-stu-id="6f79b-138">DQS</span></span>|<span data-ttu-id="6f79b-139">Conecta-se a um servidor a um banco de dados do Data Quality Services no servidor.</span><span class="sxs-lookup"><span data-stu-id="6f79b-139">Connects to a Data Quality Services server and a Data Quality Services database on the server.</span></span>|[<span data-ttu-id="6f79b-140">Gerenciador de Conexões de Limpeza DQS</span><span class="sxs-lookup"><span data-stu-id="6f79b-140">DQS Cleansing Connection Manager</span></span>](dqs-cleansing-connection-manager.md)|  
|<span data-ttu-id="6f79b-141">EXCEL</span><span class="sxs-lookup"><span data-stu-id="6f79b-141">EXCEL</span></span>|<span data-ttu-id="6f79b-142">Conecta-se a um arquivo da pasta de trabalho do Excel.</span><span class="sxs-lookup"><span data-stu-id="6f79b-142">Connects to an Excel workbook file.</span></span>|[<span data-ttu-id="6f79b-143">Gerenciador de Conexões do Excel</span><span class="sxs-lookup"><span data-stu-id="6f79b-143">Excel Connection Manager</span></span>](excel-connection-manager.md)|  
|<span data-ttu-id="6f79b-144">FILE</span><span class="sxs-lookup"><span data-stu-id="6f79b-144">FILE</span></span>|<span data-ttu-id="6f79b-145">Conecta-se a um arquivo ou uma pasta.</span><span class="sxs-lookup"><span data-stu-id="6f79b-145">Connects to a file or a folder.</span></span>|[<span data-ttu-id="6f79b-146">Gerenciador de Conexões de Arquivos</span><span class="sxs-lookup"><span data-stu-id="6f79b-146">File Connection Manager</span></span>](file-connection-manager.md)|  
|<span data-ttu-id="6f79b-147">FLATFILE</span><span class="sxs-lookup"><span data-stu-id="6f79b-147">FLATFILE</span></span>|<span data-ttu-id="6f79b-148">Conecta-se a dados em um único arquivo simples.</span><span class="sxs-lookup"><span data-stu-id="6f79b-148">Connect to data in a single flat file.</span></span>|[<span data-ttu-id="6f79b-149">Gerenciador de Conexões de Arquivos Simples</span><span class="sxs-lookup"><span data-stu-id="6f79b-149">Flat File Connection Manager</span></span>](flat-file-connection-manager.md)|  
|<span data-ttu-id="6f79b-150">FTP</span><span class="sxs-lookup"><span data-stu-id="6f79b-150">FTP</span></span>|<span data-ttu-id="6f79b-151">Conecta-se a um servidor FTP.</span><span class="sxs-lookup"><span data-stu-id="6f79b-151">Connect to an FTP server.</span></span>|[<span data-ttu-id="6f79b-152">Gerenciador de Conexões de FTP</span><span class="sxs-lookup"><span data-stu-id="6f79b-152">FTP Connection Manager</span></span>](ftp-connection-manager.md)|  
|<span data-ttu-id="6f79b-153">HTTP</span><span class="sxs-lookup"><span data-stu-id="6f79b-153">HTTP</span></span>|<span data-ttu-id="6f79b-154">Conecta-se a um servidor Web.</span><span class="sxs-lookup"><span data-stu-id="6f79b-154">Connects to a webserver.</span></span>|[<span data-ttu-id="6f79b-155">Gerenciador de Conexões de HTTP</span><span class="sxs-lookup"><span data-stu-id="6f79b-155">HTTP Connection Manager</span></span>](http-connection-manager.md)|  
|<span data-ttu-id="6f79b-156">MSMQ</span><span class="sxs-lookup"><span data-stu-id="6f79b-156">MSMQ</span></span>|<span data-ttu-id="6f79b-157">Conecta-se a uma fila de mensagens.</span><span class="sxs-lookup"><span data-stu-id="6f79b-157">Connects to a message queue.</span></span>|[<span data-ttu-id="6f79b-158">Gerenciador de Conexões MSMQ</span><span class="sxs-lookup"><span data-stu-id="6f79b-158">MSMQ Connection Manager</span></span>](msmq-connection-manager.md)|  
|<span data-ttu-id="6f79b-159">MSOLAP100</span><span class="sxs-lookup"><span data-stu-id="6f79b-159">MSOLAP100</span></span>|<span data-ttu-id="6f79b-160">Conecta-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ou a um projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f79b-160">Connects to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] or an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span>|[<span data-ttu-id="6f79b-161">Gerenciador de Conexões do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="6f79b-161">Analysis Services Connection Manager</span></span>](analysis-services-connection-manager.md)|  
|<span data-ttu-id="6f79b-162">MULTIFILE</span><span class="sxs-lookup"><span data-stu-id="6f79b-162">MULTIFILE</span></span>|<span data-ttu-id="6f79b-163">Conecta-se a vários arquivos e pastas.</span><span class="sxs-lookup"><span data-stu-id="6f79b-163">Connects to multiple files and folders.</span></span>|[<span data-ttu-id="6f79b-164">Gerenciador de Conexões de Vários Arquivos</span><span class="sxs-lookup"><span data-stu-id="6f79b-164">Multiple Files Connection Manager</span></span>](multiple-files-connection-manager.md)|  
|<span data-ttu-id="6f79b-165">MULTIFLATFILE</span><span class="sxs-lookup"><span data-stu-id="6f79b-165">MULTIFLATFILE</span></span>|<span data-ttu-id="6f79b-166">Conecta-se a vários arquivos e pastas de dados.</span><span class="sxs-lookup"><span data-stu-id="6f79b-166">Connects to multiple data files and folders.</span></span>|[<span data-ttu-id="6f79b-167">Gerenciador de Conexões de Vários Arquivos Simples</span><span class="sxs-lookup"><span data-stu-id="6f79b-167">Multiple Flat Files Connection Manager</span></span>](multiple-flat-files-connection-manager.md)|  
|<span data-ttu-id="6f79b-168">OLEDB</span><span class="sxs-lookup"><span data-stu-id="6f79b-168">OLEDB</span></span>|<span data-ttu-id="6f79b-169">Conecta-se a uma fonte de dados usando um provedor OLE DB.</span><span class="sxs-lookup"><span data-stu-id="6f79b-169">Connects to a data source by using an OLE DB provider.</span></span>|[<span data-ttu-id="6f79b-170">Gerenciador de conexões OLE DB</span><span class="sxs-lookup"><span data-stu-id="6f79b-170">OLE DB Connection Manager</span></span>](ole-db-connection-manager.md)|  
|<span data-ttu-id="6f79b-171">ODBCODBC</span><span class="sxs-lookup"><span data-stu-id="6f79b-171">ODBC</span></span>|<span data-ttu-id="6f79b-172">Conecta-se a uma fonte de dados usando ODBC.</span><span class="sxs-lookup"><span data-stu-id="6f79b-172">Connects to a data source by using ODBC.</span></span>|[<span data-ttu-id="6f79b-173">Gerenciador de Conexões ODBC</span><span class="sxs-lookup"><span data-stu-id="6f79b-173">ODBC Connection Manager</span></span>](odbc-connection-manager.md)|  
|<span data-ttu-id="6f79b-174">SMOServer</span><span class="sxs-lookup"><span data-stu-id="6f79b-174">SMOServer</span></span>|<span data-ttu-id="6f79b-175">Conecta-se a um servidor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO).</span><span class="sxs-lookup"><span data-stu-id="6f79b-175">Connects to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO) server.</span></span>|[<span data-ttu-id="6f79b-176">Gerenciador de Conexões SMO</span><span class="sxs-lookup"><span data-stu-id="6f79b-176">SMO Connection Manager</span></span>](smo-connection-manager.md)|  
|<span data-ttu-id="6f79b-177">SMTP</span><span class="sxs-lookup"><span data-stu-id="6f79b-177">SMTP</span></span>|<span data-ttu-id="6f79b-178">Conecta-se a um servidor de email SMTP.</span><span class="sxs-lookup"><span data-stu-id="6f79b-178">Connects to an SMTP mail server.</span></span>|[<span data-ttu-id="6f79b-179">Gerenciador de Conexões SMTP</span><span class="sxs-lookup"><span data-stu-id="6f79b-179">SMTP Connection Manager</span></span>](smtp-connection-manager.md)|  
|<span data-ttu-id="6f79b-180">SQLMOBILE</span><span class="sxs-lookup"><span data-stu-id="6f79b-180">SQLMOBILE</span></span>|<span data-ttu-id="6f79b-181">Conecta-se a um banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="6f79b-181">Connects to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact database.</span></span>|[<span data-ttu-id="6f79b-182">Gerenciador de Conexões do SQL Server Compact Edition</span><span class="sxs-lookup"><span data-stu-id="6f79b-182">SQL Server Compact Edition Connection Manager</span></span>](sql-server-compact-edition-connection-manager.md)|  
|<span data-ttu-id="6f79b-183">WMI</span><span class="sxs-lookup"><span data-stu-id="6f79b-183">WMI</span></span>|<span data-ttu-id="6f79b-184">Conecta-se a um servidor e especifica o escopo de gerenciamento de Instrumentação de Gerenciamento do Windows (WMI) no servidor.</span><span class="sxs-lookup"><span data-stu-id="6f79b-184">Connects to a server and specifies the scope of Windows Management Instrumentation (WMI) management on the server.</span></span>|[<span data-ttu-id="6f79b-185">Gerenciador de Conexões WMI</span><span class="sxs-lookup"><span data-stu-id="6f79b-185">WMI Connection Manager</span></span>](wmi-connection-manager.md)|  
  
### <a name="connection-managers-available-for-download"></a><span data-ttu-id="6f79b-186">Gerenciadores de conexão disponíveis para download</span><span class="sxs-lookup"><span data-stu-id="6f79b-186">Connection Managers Available for Download</span></span>  
 <span data-ttu-id="6f79b-187">A tabela a seguir lista tipos adicionais de gerenciadores de conexões que podem ser baixados no site da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6f79b-187">The following table lists additional types of connection manager that you can download from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] website.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6f79b-188">Os gerenciadores de conexões listados na tabela a seguir funcionam apenas com o [!INCLUDE[ssEnterpriseEd11](../../includes/ssenterpriseed11-md.md)] e o [!INCLUDE[ssDeveloperEd11](../../includes/ssdevelopered11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f79b-188">The connection managers listed in the following table work only with [!INCLUDE[ssEnterpriseEd11](../../includes/ssenterpriseed11-md.md)] and [!INCLUDE[ssDeveloperEd11](../../includes/ssdevelopered11-md.md)].</span></span>  
  
|<span data-ttu-id="6f79b-189">Type</span><span class="sxs-lookup"><span data-stu-id="6f79b-189">Type</span></span>|<span data-ttu-id="6f79b-190">Descrição</span><span class="sxs-lookup"><span data-stu-id="6f79b-190">Description</span></span>|<span data-ttu-id="6f79b-191">Tópico</span><span class="sxs-lookup"><span data-stu-id="6f79b-191">Topic</span></span>|  
|----------|-----------------|-----------|  
|<span data-ttu-id="6f79b-192">ORACLE</span><span class="sxs-lookup"><span data-stu-id="6f79b-192">ORACLE</span></span>|<span data-ttu-id="6f79b-193">Conecta-se a um servidor \<version info> da Oracle.</span><span class="sxs-lookup"><span data-stu-id="6f79b-193">Connects to an Oracle \<version info> server.</span></span>|<span data-ttu-id="6f79b-194">O gerenciador de conexões Oracle é o componente de gerenciador de conexões do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector para Oracle da Attunity.</span><span class="sxs-lookup"><span data-stu-id="6f79b-194">The Oracle connection manager is the connection manager component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector for Oracle by Attunity.</span></span> <span data-ttu-id="6f79b-195">O [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector para Oracle da Attunity também inclui uma origem e um destino.</span><span class="sxs-lookup"><span data-stu-id="6f79b-195">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector for Oracle by Attunity also includes a source and a destination.</span></span> <span data-ttu-id="6f79b-196">Para obter mais informações, consulte a página de download de [Microsoft Connectors para Oracle e Teradata da Attunity](https://go.microsoft.com/fwlink/?LinkId=251526).</span><span class="sxs-lookup"><span data-stu-id="6f79b-196">For more information, see the download page, [Microsoft Connectors for Oracle and Teradata by Attunity](https://go.microsoft.com/fwlink/?LinkId=251526).</span></span>|  
|<span data-ttu-id="6f79b-197">SAPBI</span><span class="sxs-lookup"><span data-stu-id="6f79b-197">SAPBI</span></span>|<span data-ttu-id="6f79b-198">Conecta a um sistema SAP NetWeaver BI versão 7.</span><span class="sxs-lookup"><span data-stu-id="6f79b-198">Connects to an SAP NetWeaver BI version 7 system.</span></span>|<span data-ttu-id="6f79b-199">O gerenciador de conexões SAP BI é o componente de gerenciador de conexões do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector para SAP BI.</span><span class="sxs-lookup"><span data-stu-id="6f79b-199">The SAP BI connection manager is the connection manager component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector for SAP BI.</span></span> <span data-ttu-id="6f79b-200">O [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector para SAP BI também inclui uma origem e um destino.</span><span class="sxs-lookup"><span data-stu-id="6f79b-200">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector for SAP BI also includes a source and a destination.</span></span> <span data-ttu-id="6f79b-201">Para obter mais informações, consulte a página de download [Microsoft SQL Server 2008 Feature Pack](https://www.microsoft.com/download/details.aspx?id=30440).</span><span class="sxs-lookup"><span data-stu-id="6f79b-201">For more information, see the download page, [Microsoft SQL Server 2008 Feature Pack](https://www.microsoft.com/download/details.aspx?id=30440).</span></span>|  
|<span data-ttu-id="6f79b-202">TERADATA</span><span class="sxs-lookup"><span data-stu-id="6f79b-202">TERADATA</span></span>|<span data-ttu-id="6f79b-203">Conecta-se a um servidor \<version info> Teradata.</span><span class="sxs-lookup"><span data-stu-id="6f79b-203">Connects to a Teradata \<version info> server.</span></span>|<span data-ttu-id="6f79b-204">O gerenciador de conexões Teradata é o componente de gerenciador de conexões do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector para Teradata da Attunity.</span><span class="sxs-lookup"><span data-stu-id="6f79b-204">The Teradata connection manager is the connection manager component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector for Teradata by Attunity.</span></span> <span data-ttu-id="6f79b-205">O [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector para Teradata da Attunity também inclui uma origem e um destino.</span><span class="sxs-lookup"><span data-stu-id="6f79b-205">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector for Teradata by Attunity also includes a source and a destination.</span></span> <span data-ttu-id="6f79b-206">Para obter mais informações, consulte a página de download de [Microsoft Connectors para Oracle e Teradata da Attunity](https://go.microsoft.com/fwlink/?LinkId=251526).</span><span class="sxs-lookup"><span data-stu-id="6f79b-206">For more information, see the download page, [Microsoft Connectors for Oracle and Teradata by Attunity](https://go.microsoft.com/fwlink/?LinkId=251526).</span></span>|  
  
### <a name="custom-connection-managers"></a><span data-ttu-id="6f79b-207">Gerenciadores de conexões personalizados</span><span class="sxs-lookup"><span data-stu-id="6f79b-207">Custom Connection Managers</span></span>  
 <span data-ttu-id="6f79b-208">Também é possível escrever gerenciadores de conexões personalizados.</span><span class="sxs-lookup"><span data-stu-id="6f79b-208">You can also write custom connection managers.</span></span> <span data-ttu-id="6f79b-209">Para obter mais informações, consulte [Developing a Custom Connection Manager](../extending-packages-custom-objects/connection-manager/developing-a-custom-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="6f79b-209">For more information, see [Developing a Custom Connection Manager](../extending-packages-custom-objects/connection-manager/developing-a-custom-connection-manager.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="6f79b-210">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="6f79b-210">Related Tasks</span></span>  
 <span data-ttu-id="6f79b-211">Para obter detalhes sobre como adicionar ou excluir um gerenciador de conexões em um pacote, consulte [Adicionar, excluir ou compartilhar um Gerenciador de Conexões em um pacote](../add-delete-or-share-a-connection-manager-in-a-package.md).</span><span class="sxs-lookup"><span data-stu-id="6f79b-211">For details about how to add or delete a connection manager in a package, see [Add, Delete, or Share a Connection Manager in a Package](../add-delete-or-share-a-connection-manager-in-a-package.md).</span></span>  
  
 <span data-ttu-id="6f79b-212">Para obter detalhes sobre como definir as propriedades de um gerenciador de conexões em um pacote, consulte [Definir as propriedades de um Gerenciador de Conexões](../set-the-properties-of-a-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="6f79b-212">For details about how to set the properties of a connection manager in a package, see [Set the Properties of a Connection Manager](../set-the-properties-of-a-connection-manager.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="6f79b-213">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="6f79b-213">Related Content</span></span>  
  
-   <span data-ttu-id="6f79b-214">Vídeo, [Aproveite o Microsoft Connector para Oracle da Attunity para melhorar o desempenho do pacote](https://technet.microsoft.com/sqlserver/gg598963.aspx), em technet.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6f79b-214">Video, [Leverage Microsoft Attunity Connector for Oracle to enhance Package Performance](https://technet.microsoft.com/sqlserver/gg598963.aspx), on technet.microsoft.com</span></span>  
  
-   <span data-ttu-id="6f79b-215">Artigos do Wiki, [Conectividade de SSIS](https://social.technet.microsoft.com/wiki/contents/articles/sql-server-integration-services-ssis.aspx#Connectivity), em social.technet.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6f79b-215">Wiki articles, [SSIS Connectivity](https://social.technet.microsoft.com/wiki/contents/articles/sql-server-integration-services-ssis.aspx#Connectivity), on social.technet.microsoft.com</span></span>  
  
-   <span data-ttu-id="6f79b-216">Entrada de blog, [Conectando ao MySQL a partir do SSIS](https://go.microsoft.com/fwlink/?LinkId=217669), em blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="6f79b-216">Blog entry, [Connecting to MySQL from SSIS](https://go.microsoft.com/fwlink/?LinkId=217669), on blogs.msdn.com.</span></span>  
  
-   <span data-ttu-id="6f79b-217">Artigo técnico, [Extraindo e carregando dados do SharePoint nos SQL Server Integration Services](https://go.microsoft.com/fwlink/?LinkId=247826), em msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="6f79b-217">Technical article, [Extracting and Loading SharePoint Data in SQL Server Integration Services](https://go.microsoft.com/fwlink/?LinkId=247826), on msdn.microsoft.com.</span></span>  
  
-   <span data-ttu-id="6f79b-218">Artigo técnico, [Você obtém a mensagem de erro "DTS_E_CANNOTACQUIRECONNECTIONFROMCONNECTIONMANAGER" ao usar o gerenciador de conexões Oracle no SSIS](https://go.microsoft.com/fwlink/?LinkId=233696), em support.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="6f79b-218">Technical article, [You get "DTS_E_CANNOTACQUIRECONNECTIONFROMCONNECTIONMANAGER" error message when using Oracle connection manager in SSIS](https://go.microsoft.com/fwlink/?LinkId=233696), on support.microsoft.com.</span></span>  
  
  