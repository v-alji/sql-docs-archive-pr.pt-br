---
title: SQL Server Profiler-ferramentas-opções (página Opções Gerais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.replay.tools.generaloptions.f1
helpviewer_keywords:
- General Options dialog box
ms.assetid: a888246d-ccfe-415f-bbdc-d6adafac250a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: fad4d3529482835367898276a973bd7c8827b553
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575988"
---
# <a name="sql-server-profiler---tools-options-general-options-page"></a><span data-ttu-id="59eea-102">SQL Server Profiler-ferramentas-opções (página Opções Gerais)</span><span class="sxs-lookup"><span data-stu-id="59eea-102">SQL Server Profiler - Tools-Options (General Options Page)</span></span>
  <span data-ttu-id="59eea-103">Use a caixa de diálogo **Opções Gerais** para exibir ou especificar as opções a seguir.</span><span class="sxs-lookup"><span data-stu-id="59eea-103">Use the **General Options** dialog box to view or specify the following options.</span></span>  
  
## <a name="options"></a><span data-ttu-id="59eea-104">Opções</span><span class="sxs-lookup"><span data-stu-id="59eea-104">Options</span></span>  
  
### <a name="display-options"></a><span data-ttu-id="59eea-105">Opções de Exibição</span><span class="sxs-lookup"><span data-stu-id="59eea-105">Display Options</span></span>  
 <span data-ttu-id="59eea-106">**Nome da fonte**</span><span class="sxs-lookup"><span data-stu-id="59eea-106">**Font name**</span></span>  
 <span data-ttu-id="59eea-107">Exibe o nome da fonte usada na grade de resultados de rastreamento durante rastreamentos.</span><span class="sxs-lookup"><span data-stu-id="59eea-107">Displays the name of the font used in the trace results grid during traces.</span></span>  
  
 <span data-ttu-id="59eea-108">**Tamanho da fonte**</span><span class="sxs-lookup"><span data-stu-id="59eea-108">**Font size**</span></span>  
 <span data-ttu-id="59eea-109">Exibe o tamanho da fonte usada na grade de resultados de rastreamento durante rastreamentos.</span><span class="sxs-lookup"><span data-stu-id="59eea-109">Displays the size of the font used in the trace results grid during traces.</span></span>  
  
 <span data-ttu-id="59eea-110">**Escolher Fonte**</span><span class="sxs-lookup"><span data-stu-id="59eea-110">**Choose Font**</span></span>  
 <span data-ttu-id="59eea-111">Abre uma caixa de diálogo para alterar as configurações de fonte.</span><span class="sxs-lookup"><span data-stu-id="59eea-111">Opens a dialog to change the font settings.</span></span>  
  
 <span data-ttu-id="59eea-112">**Usar configurações regionais para exibir valores de data e hora**</span><span class="sxs-lookup"><span data-stu-id="59eea-112">**Use regional settings to display date and time values**</span></span>  
 <span data-ttu-id="59eea-113">Exibe os valores de data e hora com os parâmetros regionais configurados para seu computador.</span><span class="sxs-lookup"><span data-stu-id="59eea-113">Displays date and time values in regional settings configured for your computer.</span></span> <span data-ttu-id="59eea-114">Se você não selecionar essa opção, os valores de data e hora serão exibidos no formato fixo usado pelo Microsoft [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]que inclui milissegundos.</span><span class="sxs-lookup"><span data-stu-id="59eea-114">If you do not select this option, the date and time values are displayed in the fixed format used by Microsoft [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], which includes milliseconds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59eea-115">Ativar/desativar esta caixa de seleção altera o formato de exibição de colunas de hora como **StartTime** e **EndTime**.</span><span class="sxs-lookup"><span data-stu-id="59eea-115">Toggling this checkbox changes the time columns display format such as **StartTime** and **EndTime**.</span></span> <span data-ttu-id="59eea-116">Porém, não altera os parâmetros de valores **DateTime** dentro dos eventos de idioma ou RPCs (chamadas de procedimento remoto).</span><span class="sxs-lookup"><span data-stu-id="59eea-116">However, it does not change the **DateTime** value parameters inside the language events or remote procedure calls (RPCs).</span></span>  
  
 <span data-ttu-id="59eea-117">**Mostrar valores na coluna Duration em microssegundos**</span><span class="sxs-lookup"><span data-stu-id="59eea-117">**Show values in Duration column in microseconds**</span></span>  
 <span data-ttu-id="59eea-118">Exibe os valores em microssegundos na coluna de dados **Duration** de rastreamentos.</span><span class="sxs-lookup"><span data-stu-id="59eea-118">Displays the values in microseconds in the **Duration** data column of traces.</span></span> <span data-ttu-id="59eea-119">Por padrão, a coluna **Duration** exibe valores em milissegundos.</span><span class="sxs-lookup"><span data-stu-id="59eea-119">By default, the **Duration** column displays values in milliseconds.</span></span>  
  
### <a name="tracing-options"></a><span data-ttu-id="59eea-120">Opções de Rastreamento</span><span class="sxs-lookup"><span data-stu-id="59eea-120">Tracing Options</span></span>  
 <span data-ttu-id="59eea-121">**Iniciar rastreamento imediatamente após estabelecer a conexão.**</span><span class="sxs-lookup"><span data-stu-id="59eea-121">**Start tracing immediately after making connection**</span></span>  
 <span data-ttu-id="59eea-122">Começa a rastrear usando o modelo padrão assim que uma conexão é estabelecida.</span><span class="sxs-lookup"><span data-stu-id="59eea-122">Begin a trace using the default template as soon as a connection is made.</span></span>  
  
 <span data-ttu-id="59eea-123">**Atualizar a definição de rastreamento quando a versão do provedor for alterada**</span><span class="sxs-lookup"><span data-stu-id="59eea-123">**Update trace definition when provider version changes**</span></span>  
 <span data-ttu-id="59eea-124">Aplica a definição de rastreamento mais recente ao [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] quando o provedor for atualizado.</span><span class="sxs-lookup"><span data-stu-id="59eea-124">Apply the most current trace definition to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] when the provider is updated.</span></span> <span data-ttu-id="59eea-125">Este item não é verificado por padrão.</span><span class="sxs-lookup"><span data-stu-id="59eea-125">This item is not checked by default.</span></span> <span data-ttu-id="59eea-126">Isso força o [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] a consultar o servidor quanto à definição de rastreamento e a recriar o arquivo em disco, se houver um.</span><span class="sxs-lookup"><span data-stu-id="59eea-126">This forces [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] to query the server for the trace definition and re-create, if one exists, the file on disk.</span></span>  
  
### <a name="file-rollover-options"></a><span data-ttu-id="59eea-127">Opções de substituição de arquivos</span><span class="sxs-lookup"><span data-stu-id="59eea-127">File Rollover Options</span></span>  
 <span data-ttu-id="59eea-128">**Carregar todos os arquivos de substituição em sequência, sem avisar**</span><span class="sxs-lookup"><span data-stu-id="59eea-128">**Load all rollover files in sequence without prompting**</span></span>  
 <span data-ttu-id="59eea-129">Carrega automaticamente os arquivos de substituição quando um arquivo de rastreamento é aberto.</span><span class="sxs-lookup"><span data-stu-id="59eea-129">Load rollover files automatically when a trace file is opened.</span></span> <span data-ttu-id="59eea-130">Se mais de um arquivo foi criado durante o rastreamento, selecionar esta opção carregará automaticamente todos os arquivos de substituição.</span><span class="sxs-lookup"><span data-stu-id="59eea-130">If more than one file was created while tracing, selecting this option automatically loads all rollover files.</span></span>  
  
 <span data-ttu-id="59eea-131">**Perguntar antes de carregar arquivos de substituição**</span><span class="sxs-lookup"><span data-stu-id="59eea-131">**Prompt before loading rollover files**</span></span>  
 <span data-ttu-id="59eea-132">O [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] pergunta antes de adicionar um arquivo de substituição quando um arquivo de rastreamento é aberto.</span><span class="sxs-lookup"><span data-stu-id="59eea-132">Have [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] prompt you before adding a rollover file when a trace file is opened.</span></span>  
  
 <span data-ttu-id="59eea-133">**Nunca carregar arquivos de substituição subsequentes**</span><span class="sxs-lookup"><span data-stu-id="59eea-133">**Never load subsequent rollover files**</span></span>  
 [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] <span data-ttu-id="59eea-134">nunca carrega arquivos de substituição posteriores quando um arquivo de rastreamento é aberto.</span><span class="sxs-lookup"><span data-stu-id="59eea-134">never loads subsequent rollover files when a trace file is opened.</span></span>  
  
### <a name="replay-options"></a><span data-ttu-id="59eea-135">Opções de Repetição</span><span class="sxs-lookup"><span data-stu-id="59eea-135">Replay Options</span></span>  
 <span data-ttu-id="59eea-136">**Número padrão de threads de repetição**</span><span class="sxs-lookup"><span data-stu-id="59eea-136">**Default number of replay threads**</span></span>  
 <span data-ttu-id="59eea-137">Especifica o número de threads de repetição a usar simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="59eea-137">Specify the number of replay threads to use concurrently.</span></span> <span data-ttu-id="59eea-138">Um número mais alto consome mais recursos durante a repetição, porém aumenta a simultaneidade da repetição.</span><span class="sxs-lookup"><span data-stu-id="59eea-138">A higher number consumes more resources during replay, but increases replay concurrency.</span></span>  
  
 <span data-ttu-id="59eea-139">**Intervalo de espera padrão do monitor de integridade (s)**</span><span class="sxs-lookup"><span data-stu-id="59eea-139">**Default health monitor wait interval (sec)**</span></span>  
 <span data-ttu-id="59eea-140">Especifica o intervalo de espera de repetição, em segundos.</span><span class="sxs-lookup"><span data-stu-id="59eea-140">Specify the wait interval to replay in seconds.</span></span> <span data-ttu-id="59eea-141">O padrão é 3600 segundos (1 hora).</span><span class="sxs-lookup"><span data-stu-id="59eea-141">Default is 3600 seconds (1 hour).</span></span> <span data-ttu-id="59eea-142">Esta configuração afeta o tempo durante o qual um thread pode ser executado antes de ser concluído pelo monitor de integridade.</span><span class="sxs-lookup"><span data-stu-id="59eea-142">This setting affects the amount of time a thread is allowed to run before being terminated by the health monitor.</span></span>  
  
 <span data-ttu-id="59eea-143">**Intervalo de sondagem padrão do monitor de integridade (s)**</span><span class="sxs-lookup"><span data-stu-id="59eea-143">**Default health monitor poll interval (sec)**</span></span>  
 <span data-ttu-id="59eea-144">Especifica o intervalo de sondagem do monitor de integridade durante a repetição, em segundos.</span><span class="sxs-lookup"><span data-stu-id="59eea-144">Specify the health monitor poll interval during replay in seconds.</span></span> <span data-ttu-id="59eea-145">O padrão é 60 segundos.</span><span class="sxs-lookup"><span data-stu-id="59eea-145">Default is 60 seconds.</span></span> <span data-ttu-id="59eea-146">Este valor permite que o usuário configure com que frequência o monitor de integridade sonda candidatos a conclusão.</span><span class="sxs-lookup"><span data-stu-id="59eea-146">This value allows the user to configure how often the health monitor polls for candidates for termination.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59eea-147">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="59eea-147">See Also</span></span>  
 <span data-ttu-id="59eea-148">[Iniciar um rastreamento automaticamente após a conexão com um servidor &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="59eea-148">[Start a Trace Automatically after Connecting to a Server &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="59eea-149">[Definir padrões de exibição de rastreamento &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/set-trace-display-defaults-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="59eea-149">[Set Trace Display Defaults &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/set-trace-display-defaults-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="59eea-150">[Reproduzir uma tabela de rastreamento &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="59eea-150">[Replay a Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="59eea-151">[Reproduzir um arquivo de rastreamento &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="59eea-151">[Replay a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="59eea-152">[Reproduzir rastreamentos](../tools/sql-server-profiler/replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="59eea-152">[Replay Traces](../tools/sql-server-profiler/replay-traces.md) </span></span>  
 <span data-ttu-id="59eea-153">[Definir opções de rastreamento global &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/set-global-trace-options-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="59eea-153">[Set Global Trace Options &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/set-global-trace-options-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="59eea-154">[Modelos e permissões do SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="59eea-154">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="59eea-155">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="59eea-155">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
