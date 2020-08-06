---
title: Exibir e ler arquivos de log da Instalação do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- viewing logs
- displaying log files
- Setup [SQL Server], logs
- installation log files [SQL Server]
- installing SQL Server, logs
- errors [SQL Server], Setup
- logs [SQL Server], Setup
ms.assetid: 9d77af64-9084-4375-908a-d90f99535062
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 70f9bbb9a8ed72503dc6fe90077232748b2c4ac2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680058"
---
# <a name="view-and-read-sql-server-setup-log-files"></a><span data-ttu-id="6a6c0-102">Exibir e ler arquivos de log da Instalação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="6a6c0-102">View and Read SQL Server Setup Log Files</span></span>
  <span data-ttu-id="6a6c0-103">Cada execução da instalação cria arquivos de log com uma nova pasta de log com carimbo de data/hora em% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\ .</span><span class="sxs-lookup"><span data-stu-id="6a6c0-103">Each execution of Setup creates log files are created with a new timestamped log folder at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\.</span></span> <span data-ttu-id="6a6c0-104">O formato de nome da pasta com carimbo de data/hora é AAAAMMDD_hhmmss.</span><span class="sxs-lookup"><span data-stu-id="6a6c0-104">The time-stamped log folder name format is YYYYMMDD_hhmmss.</span></span> <span data-ttu-id="6a6c0-105">Quando a Instalação é executada em um modo autônomo, os logs são criados em % temp%\sqlsetup\*.log.</span><span class="sxs-lookup"><span data-stu-id="6a6c0-105">When Setup is run in an unattended mode, the logs are created at % temp%\sqlsetup\*.log.</span></span> <span data-ttu-id="6a6c0-106">Todos os arquivos da pasta de logs são arquivados no arquivo Log\*.cab em sua respectiva pasta de log.</span><span class="sxs-lookup"><span data-stu-id="6a6c0-106">All files in the logs folder are archived into the Log\*.cab file in their respective log folder.</span></span>  
  
 <span data-ttu-id="6a6c0-107">Uma solicitação de Instalação típica passa por três fases de execução:</span><span class="sxs-lookup"><span data-stu-id="6a6c0-107">A typical Setup request goes through three execution phases:</span></span>  
  
1.  <span data-ttu-id="6a6c0-108">Texto de regras globais</span><span class="sxs-lookup"><span data-stu-id="6a6c0-108">Global rules text</span></span>  
  
2.  <span data-ttu-id="6a6c0-109">Atualização de componente</span><span class="sxs-lookup"><span data-stu-id="6a6c0-109">Component update</span></span>  
  
3.  <span data-ttu-id="6a6c0-110">Ação solicitada pelo usuário</span><span class="sxs-lookup"><span data-stu-id="6a6c0-110">User-requested action</span></span>  
  
 <span data-ttu-id="6a6c0-111">Em cada fase, a Instalação gera logs de detalhes e de resumo com logs adicionais criados conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="6a6c0-111">In each phase, Setup generates detail and summary logs with additional logs created as appropriate.</span></span> <span data-ttu-id="6a6c0-112">A Instalação é chamada ao menos três vezes para cada ação de instalação solicitada pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="6a6c0-112">Setup is called at least three times per user-requested Setup action.</span></span>  
  
 <span data-ttu-id="6a6c0-113">Os arquivos de armazenamento de dados contêm um instantâneo do estado de todos os objetos de configuração que estão sendo rastreados pelo processo de instalação e são úteis para solucionar erros de configuração.</span><span class="sxs-lookup"><span data-stu-id="6a6c0-113">Datastore files contain a snapshot of the state of all configuration objects being tracked by the Setup process, and are useful for troubleshooting configuration errors.</span></span> <span data-ttu-id="6a6c0-114">Despejos de arquivo XML são criados para objetos de armazenamento de dados em cada fase de execução.</span><span class="sxs-lookup"><span data-stu-id="6a6c0-114">XML file dumps are created for datastore objects for each execution phase.</span></span> <span data-ttu-id="6a6c0-115">Eles são salvos em sua própria subpasta de log na pasta de log com carimbo de data/hora, como a seguir:</span><span class="sxs-lookup"><span data-stu-id="6a6c0-115">They are saved in their own log subfolder under the time-stamped log folder, as follows:</span></span>  
  
-   <span data-ttu-id="6a6c0-116">Datastore_GlobalRules</span><span class="sxs-lookup"><span data-stu-id="6a6c0-116">Datastore_GlobalRules</span></span>  
  
-   <span data-ttu-id="6a6c0-117">Datastore_ComponentUpdated</span><span class="sxs-lookup"><span data-stu-id="6a6c0-117">Datastore_ComponentUpdated</span></span>  
  
-   <span data-ttu-id="6a6c0-118">Repositório de dados</span><span class="sxs-lookup"><span data-stu-id="6a6c0-118">Datastore</span></span>  
  
 <span data-ttu-id="6a6c0-119">As seções a seguir descrevem arquivos de log da Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6a6c0-119">The following sections describe [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup log files.</span></span>  
  
## <a name="summary-text"></a><span data-ttu-id="6a6c0-120">Texto resumido</span><span class="sxs-lookup"><span data-stu-id="6a6c0-120">Summary Text</span></span>  
  
### <a name="overview"></a><span data-ttu-id="6a6c0-121">Visão geral</span><span class="sxs-lookup"><span data-stu-id="6a6c0-121">Overview</span></span>  
 <span data-ttu-id="6a6c0-122">Esse arquivo mostra os componentes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] detectados durante Instalação, o ambiente de sistema operacional, valores de parâmetros de linha de comando, caso sejam especificados, e o status global de cada MSI/MSP que foi executado.</span><span class="sxs-lookup"><span data-stu-id="6a6c0-122">This file shows the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components that were detected during Setup, the operating system environment, command-line parameter values if they are specified, and the overall status of each MSI/MSP that was executed.</span></span>  
  
 <span data-ttu-id="6a6c0-123">O log é organizado nas seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="6a6c0-123">The log is organized into the following sections:</span></span>  
  
-   <span data-ttu-id="6a6c0-124">Um resumo global da execução</span><span class="sxs-lookup"><span data-stu-id="6a6c0-124">An overall summary of the execution</span></span>  
  
-   <span data-ttu-id="6a6c0-125">As propriedades e a configuração do computador em que a Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] foi executada</span><span class="sxs-lookup"><span data-stu-id="6a6c0-125">Properties and the configuration of the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup was run</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6a6c0-126">Recursos do produto instalados anteriormente no computador</span><span class="sxs-lookup"><span data-stu-id="6a6c0-126">product features previously installed on the computer</span></span>  
  
-   <span data-ttu-id="6a6c0-127">Descrição da versão de instalação e propriedades do pacote de instalação</span><span class="sxs-lookup"><span data-stu-id="6a6c0-127">Description of the installation version and installation package properties</span></span>  
  
-   <span data-ttu-id="6a6c0-128">Configurações de entrada em runtime que são fornecidas durante instalação</span><span class="sxs-lookup"><span data-stu-id="6a6c0-128">Runtime input settings that are provided during install</span></span>  
  
-   <span data-ttu-id="6a6c0-129">Local do arquivo de configuração</span><span class="sxs-lookup"><span data-stu-id="6a6c0-129">Location of the configuration file</span></span>  
  
-   <span data-ttu-id="6a6c0-130">Detalhes dos resultados de execução</span><span class="sxs-lookup"><span data-stu-id="6a6c0-130">Details of the execution results</span></span>  
  
-   <span data-ttu-id="6a6c0-131">Regras globais</span><span class="sxs-lookup"><span data-stu-id="6a6c0-131">Global rules</span></span>  
  
-   <span data-ttu-id="6a6c0-132">Regras específicas ao cenário de instalação</span><span class="sxs-lookup"><span data-stu-id="6a6c0-132">Rules specific to the installation scenario</span></span>  
  
-   <span data-ttu-id="6a6c0-133">Regras com falha</span><span class="sxs-lookup"><span data-stu-id="6a6c0-133">Failed rules</span></span>  
  
-   <span data-ttu-id="6a6c0-134">Local do arquivo de relatório de regras</span><span class="sxs-lookup"><span data-stu-id="6a6c0-134">Location of the rules report file</span></span>  
  
### <a name="location"></a><span data-ttu-id="6a6c0-135">Location</span><span class="sxs-lookup"><span data-stu-id="6a6c0-135">Location</span></span>  
 <span data-ttu-id="6a6c0-136">Ele está localizado em% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\ .</span><span class="sxs-lookup"><span data-stu-id="6a6c0-136">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\.</span></span>  
  
 <span data-ttu-id="6a6c0-137">Para localizar erros no arquivo de texto resumido, pesquise o arquivo usando as palavras-chave "error" ou "failed".</span><span class="sxs-lookup"><span data-stu-id="6a6c0-137">To find errors in the summary text file, search the file by using the "error" or "failed" keywords.</span></span>  
  
## <a name="summary_engine-base_yyyymmdd_hhmmsstxt"></a><span data-ttu-id="6a6c0-138">Summary_engine-base_YYYYMMDD_HHMMss.txt</span><span class="sxs-lookup"><span data-stu-id="6a6c0-138">Summary_engine-base_YYYYMMDD_HHMMss.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="6a6c0-139">Visão geral</span><span class="sxs-lookup"><span data-stu-id="6a6c0-139">Overview</span></span>  
 <span data-ttu-id="6a6c0-140">O arquivo de base summary_engine é semelhante ao arquivo de resumo e é gerado durante o fluxo de trabalho principal.</span><span class="sxs-lookup"><span data-stu-id="6a6c0-140">The summary_engine base file is similar to the summary file and is generated during the main workflow.</span></span>  
  
### <a name="location"></a><span data-ttu-id="6a6c0-141">Location</span><span class="sxs-lookup"><span data-stu-id="6a6c0-141">Location</span></span>  
 <span data-ttu-id="6a6c0-142">Ele está localizado em% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="6a6c0-142">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="summary_engine-base_yyyymmdd_hhmmss_componentupdatetxt"></a><span data-ttu-id="6a6c0-143">Summary_engine-base_YYYYMMDD_HHMMss_ComponentUpdate.txt</span><span class="sxs-lookup"><span data-stu-id="6a6c0-143">Summary_engine-base_YYYYMMDD_HHMMss_ComponentUpdate.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="6a6c0-144">Visão geral</span><span class="sxs-lookup"><span data-stu-id="6a6c0-144">Overview</span></span>  
 <span data-ttu-id="6a6c0-145">O arquivo de log resumido de atualização do componente é semelhante ao arquivo de resumo e é gerado durante o fluxo de trabalho de atualização de componente.</span><span class="sxs-lookup"><span data-stu-id="6a6c0-145">The component update summary log file is similar to the summary file and is generated during the component update workflow.</span></span>  
  
### <a name="location"></a><span data-ttu-id="6a6c0-146">Location</span><span class="sxs-lookup"><span data-stu-id="6a6c0-146">Location</span></span>  
 <span data-ttu-id="6a6c0-147">Ele está localizado em% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="6a6c0-147">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="summary_engine-base_versionnumbermmdd_hhmmss_globalrulestxt"></a><span data-ttu-id="6a6c0-148">Base_ de Summary_engine \<VersionNumber>MMDD_HHMMss_GlobalRules.txt</span><span class="sxs-lookup"><span data-stu-id="6a6c0-148">Summary_engine-base_\<VersionNumber>MMDD_HHMMss_GlobalRules.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="6a6c0-149">Visão geral</span><span class="sxs-lookup"><span data-stu-id="6a6c0-149">Overview</span></span>  
 <span data-ttu-id="6a6c0-150">O arquivo de log resumido de regras globais é semelhante ao arquivo de resumo gerado durante o fluxo de trabalho de regras globais.</span><span class="sxs-lookup"><span data-stu-id="6a6c0-150">The global rules summary log file is similar to the summary file generated during the global rules workflow.</span></span>  
  
### <a name="location"></a><span data-ttu-id="6a6c0-151">Location</span><span class="sxs-lookup"><span data-stu-id="6a6c0-151">Location</span></span>  
 <span data-ttu-id="6a6c0-152">Ele está localizado em% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="6a6c0-152">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="detailtxt"></a><span data-ttu-id="6a6c0-153">Detail.txt</span><span class="sxs-lookup"><span data-stu-id="6a6c0-153">Detail.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="6a6c0-154">Visão geral</span><span class="sxs-lookup"><span data-stu-id="6a6c0-154">Overview</span></span>  
 <span data-ttu-id="6a6c0-155">O arquivo Detail.txt é gerado para o fluxo de trabalho principal, como instalação ou atualização, e fornece os detalhes da execução.</span><span class="sxs-lookup"><span data-stu-id="6a6c0-155">Detail.txt is generated for the main workflow such as install or upgrade, and provides the details of the execution.</span></span> <span data-ttu-id="6a6c0-156">Os logs do arquivo são gerados com base na hora em que cada ação para a instalação foi invocada, e mostram a ordem na qual as ações foram executadas e suas dependências.</span><span class="sxs-lookup"><span data-stu-id="6a6c0-156">The logs in the file are generated based on the time when each action for the installation was invoked, and show the order in which the actions were executed, and their dependencies.</span></span>  
  
### <a name="location"></a><span data-ttu-id="6a6c0-157">Location</span><span class="sxs-lookup"><span data-stu-id="6a6c0-157">Location</span></span>  
 <span data-ttu-id="6a6c0-158">Ele está localizado em% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup</span><span class="sxs-lookup"><span data-stu-id="6a6c0-158">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup</span></span>  
  
 <span data-ttu-id="6a6c0-159">Bootstrap\Log\\<YYYYMMDD_HHMM>\Detail.txt.</span><span class="sxs-lookup"><span data-stu-id="6a6c0-159">Bootstrap\Log\\<YYYYMMDD_HHMM>\Detail.txt.</span></span>  
  
 <span data-ttu-id="6a6c0-160">Se ocorrer um erro durante o processo de Instalação, a exceção ou o erro será registrado no final desse arquivo.</span><span class="sxs-lookup"><span data-stu-id="6a6c0-160">If an error occurs during the Setup process, the exception or error are logged at the end of this file.</span></span> <span data-ttu-id="6a6c0-161">Para localizar os erros nesse arquivo, primeiro examine o final do arquivo e depois efetue uma pesquisa do arquivo pelas palavras-chave "error" ou "exception".</span><span class="sxs-lookup"><span data-stu-id="6a6c0-161">To find the errors in this file, first examine the end of the file followed by a search of the file for the "error" or "exception" keywords.</span></span>  
  
## <a name="detail_componentupdatetxt"></a><span data-ttu-id="6a6c0-162">Detail_ComponentUpdate.txt</span><span class="sxs-lookup"><span data-stu-id="6a6c0-162">Detail_ComponentUpdate.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="6a6c0-163">Visão geral</span><span class="sxs-lookup"><span data-stu-id="6a6c0-163">Overview</span></span>  
 <span data-ttu-id="6a6c0-164">O arquivo Detail_ComponentUpdate.txt é gerado para o fluxo de trabalho de atualização de componente e é semelhante ao Detail.txt.</span><span class="sxs-lookup"><span data-stu-id="6a6c0-164">The Detail_ComponentUpdate.txt file is generated for the component update workflow and is similar to Detail.txt.</span></span>  
  
### <a name="location"></a><span data-ttu-id="6a6c0-165">Location</span><span class="sxs-lookup"><span data-stu-id="6a6c0-165">Location</span></span>  
 <span data-ttu-id="6a6c0-166">Ele está localizado em% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="6a6c0-166">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="detail_globalrulestxt"></a><span data-ttu-id="6a6c0-167">Detail_GlobalRules.txt</span><span class="sxs-lookup"><span data-stu-id="6a6c0-167">Detail_GlobalRules.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="6a6c0-168">Visão geral</span><span class="sxs-lookup"><span data-stu-id="6a6c0-168">Overview</span></span>  
 <span data-ttu-id="6a6c0-169">O arquivo Detail_GlobalRules.txt é gerado para a execução de regras globais e é semelhante ao Detail.txt.</span><span class="sxs-lookup"><span data-stu-id="6a6c0-169">Detail_GlobalRules.txt is generated for the global rules execution and is similar to Detail.txt.</span></span>  
  
### <a name="location"></a><span data-ttu-id="6a6c0-170">Location</span><span class="sxs-lookup"><span data-stu-id="6a6c0-170">Location</span></span>  
 <span data-ttu-id="6a6c0-171">Ele está localizado em% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="6a6c0-171">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="msi-log-files"></a><span data-ttu-id="6a6c0-172">Arquivos de log MSI</span><span class="sxs-lookup"><span data-stu-id="6a6c0-172">MSI log files</span></span>  
  
### <a name="overview"></a><span data-ttu-id="6a6c0-173">Visão geral</span><span class="sxs-lookup"><span data-stu-id="6a6c0-173">Overview</span></span>  
 <span data-ttu-id="6a6c0-174">Os arquivos de log MSI fornecem detalhes do processo de pacote de instalação.</span><span class="sxs-lookup"><span data-stu-id="6a6c0-174">The MSI log files provide details of the installation package process.</span></span> <span data-ttu-id="6a6c0-175">Eles são gerados pelo MSIEXEC durante a instalação do pacote especificado.</span><span class="sxs-lookup"><span data-stu-id="6a6c0-175">They are generated by the MSIEXEC during the installation of the specified package.</span></span>  
  
 <span data-ttu-id="6a6c0-176">Tipos de arquivos de log MSI:</span><span class="sxs-lookup"><span data-stu-id="6a6c0-176">Types of MSI log files:</span></span>  
  
-   <span data-ttu-id="6a6c0-177">\<Feature>_\<Architecture>\_\<Interaction>.log</span><span class="sxs-lookup"><span data-stu-id="6a6c0-177">\<Feature>_\<Architecture>\_\<Interaction>.log</span></span>  
  
-   <span data-ttu-id="6a6c0-178">\<Feature>_\<Architecture>\_\<Language>\_\<Interaction>.log</span><span class="sxs-lookup"><span data-stu-id="6a6c0-178">\<Feature>_\<Architecture>\_\<Language>\_\<Interaction>.log</span></span>  
  
-   <span data-ttu-id="6a6c0-179">\<Feature>_\<Architecture>\_\<Interaction>\_\<workflow>.log</span><span class="sxs-lookup"><span data-stu-id="6a6c0-179">\<Feature>_\<Architecture>\_\<Interaction>\_\<workflow>.log</span></span>  
  
### <a name="location"></a><span data-ttu-id="6a6c0-180">Location</span><span class="sxs-lookup"><span data-stu-id="6a6c0-180">Location</span></span>  
 <span data-ttu-id="6a6c0-181">Os arquivos de log do MSI estão localizados em% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\<name \> . log.</span><span class="sxs-lookup"><span data-stu-id="6a6c0-181">The MSI log files are located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\<Name\>.log.</span></span>  
  
 <span data-ttu-id="6a6c0-182">No final do arquivo, há um resumo da execução, que inclui o status de êxito ou falha e propriedades.</span><span class="sxs-lookup"><span data-stu-id="6a6c0-182">At the end of the file is a summary of the execution which includes the success or failure status and properties.</span></span> <span data-ttu-id="6a6c0-183">Para localizar o erro no arquivo MSI, pesquise "value 3"; os erros geralmente são encontrados próximos à cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="6a6c0-183">To find the error in the MSI file, search for "value 3" and usually the errors can be found close to the string.</span></span>  
  
## <a name="configurationfileini"></a><span data-ttu-id="6a6c0-184">ConfigurationFile.ini</span><span class="sxs-lookup"><span data-stu-id="6a6c0-184">ConfigurationFile.ini</span></span>  
  
### <a name="overview"></a><span data-ttu-id="6a6c0-185">Visão geral</span><span class="sxs-lookup"><span data-stu-id="6a6c0-185">Overview</span></span>  
 <span data-ttu-id="6a6c0-186">O arquivo de configuração contém as configurações de entrada que são fornecidas durante instalação.</span><span class="sxs-lookup"><span data-stu-id="6a6c0-186">The configuration file contains the input settings that are provided during installation.</span></span> <span data-ttu-id="6a6c0-187">Pode ser usado para reiniciar a instalação sem ser necessário inserir as configurações manualmente.</span><span class="sxs-lookup"><span data-stu-id="6a6c0-187">It can be used to restart the installation without having to enter the settings manually.</span></span> <span data-ttu-id="6a6c0-188">Entretanto, as senhas das contas, o PID e alguns parâmetros não são salvos no arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="6a6c0-188">However, passwords for the accounts, PID, and some parameters are not saved in the configuration file.</span></span> <span data-ttu-id="6a6c0-189">As configurações podem ser adicionadas ao arquivo ou fornecidas por meio da linha de comando ou da interface do usuário de Instalação.</span><span class="sxs-lookup"><span data-stu-id="6a6c0-189">The settings can be either added to the file or provided by using the command line or the Setup user interface.</span></span> <span data-ttu-id="6a6c0-190">Para obter mais informações, consulte [instalar SQL Server 2014 usando um arquivo de configuração](install-sql-server-using-a-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="6a6c0-190">For more information, see [Install SQL Server 2014 Using a Configuration File](install-sql-server-using-a-configuration-file.md).</span></span>  
  
### <a name="location"></a><span data-ttu-id="6a6c0-191">Location</span><span class="sxs-lookup"><span data-stu-id="6a6c0-191">Location</span></span>  
 <span data-ttu-id="6a6c0-192">Ele está localizado em% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="6a6c0-192">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="systemconfigurationcheck_reporthtm"></a><span data-ttu-id="6a6c0-193">SystemConfigurationCheck_Report.htm</span><span class="sxs-lookup"><span data-stu-id="6a6c0-193">SystemConfigurationCheck_Report.htm</span></span>  
  
### <a name="overview"></a><span data-ttu-id="6a6c0-194">Visão geral</span><span class="sxs-lookup"><span data-stu-id="6a6c0-194">Overview</span></span>  
 <span data-ttu-id="6a6c0-195">O relatório de verificação da configuração do sistema contém uma breve descrição de cada regra executada, bem como o status de execução.</span><span class="sxs-lookup"><span data-stu-id="6a6c0-195">The system configuration check report contains a short description for each executed rule, and the execution status.</span></span>  
  
### <a name="location"></a><span data-ttu-id="6a6c0-196">Location</span><span class="sxs-lookup"><span data-stu-id="6a6c0-196">Location</span></span>  
 <span data-ttu-id="6a6c0-197">Ele está localizado em% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="6a6c0-197">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a6c0-198">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6a6c0-198">See Also</span></span>  
 <span data-ttu-id="6a6c0-199">[Tópicos de instruções sobre a instalação](../../sql-server/install/installation-how-to-topics.md) </span><span class="sxs-lookup"><span data-stu-id="6a6c0-199">[Installation How-to Topics](../../sql-server/install/installation-how-to-topics.md) </span></span>  
 [<span data-ttu-id="6a6c0-200">Instalar o SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="6a6c0-200">Install SQL Server 2014</span></span>](install-sql-server.md)  
  
  
