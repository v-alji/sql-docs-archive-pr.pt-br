---
title: Mensagens personalizadas para registro em log | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logs [Integration Services], custom
- writing log entries
- SSIS packages, logs
- custom messages for logging [Integration Services]
ms.assetid: 3c74bba9-02b7-4bf5-bad5-19278b680730
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2b9f450c74ef6d46876adfde45729c71b3262449
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574214"
---
# <a name="custom-messages-for-logging"></a><span data-ttu-id="9137a-102">Mensagens personalizadas para log</span><span class="sxs-lookup"><span data-stu-id="9137a-102">Custom Messages for Logging</span></span>
  <span data-ttu-id="9137a-103">O [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] fornece um rico conjunto de eventos personalizados para gravação de entradas de log para pacotes e diversas tarefas.</span><span class="sxs-lookup"><span data-stu-id="9137a-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] provides a rich set of custom events for writing log entries for packages and many tasks.</span></span> <span data-ttu-id="9137a-104">Você pode usar essas entradas para salvar informações detalhadas sobre progresso de execução, resultados e problemas registrando eventos predefinidos ou mensagens definidas pelo usuário para análise posterior.</span><span class="sxs-lookup"><span data-stu-id="9137a-104">You can use these entries to save detailed information about execution progress, results, and problems by recording predefined events or user-defined messages for later analysis.</span></span> <span data-ttu-id="9137a-105">Por exemplo, você pode registrar quando uma inserção em massa é iniciada ou finalizada para identificar problemas de desempenho na execução do pacote.</span><span class="sxs-lookup"><span data-stu-id="9137a-105">For example, you can record when a bulk insert begins and ends to identify performance issues when the package runs.</span></span>  
  
 <span data-ttu-id="9137a-106">As entradas de log personalizadas são um conjunto de entradas diferente do conjunto de eventos de log padrão, disponível para pacotes e todos os contêineres e tarefas.</span><span class="sxs-lookup"><span data-stu-id="9137a-106">The custom log entries are a different set of entries than the set of standard logging events that are available for packages and all containers and tasks.</span></span> <span data-ttu-id="9137a-107">As entradas de log personalizadas são elaboradas para capturar informações úteis sobre uma tarefa específica em um pacote.</span><span class="sxs-lookup"><span data-stu-id="9137a-107">The custom log entries are tailored to capture useful information about a specific task in a package.</span></span> <span data-ttu-id="9137a-108">Por exemplo, uma das entradas de log personalizadas da tarefa Executar SQL registra a instrução SQL executada pela tarefa no log.</span><span class="sxs-lookup"><span data-stu-id="9137a-108">For example, one of the custom log entries for the Execute SQL task records the SQL statement that the task executes in the log.</span></span>  
  
 <span data-ttu-id="9137a-109">Todas as entradas de log incluem informações de data e hora, inclusive as entradas de log que são gravadas automaticamente quando um pacote é iniciado ou finalizado.</span><span class="sxs-lookup"><span data-stu-id="9137a-109">All log entries include date and time information, including the log entries that are automatically written when a package begins and finishes.</span></span> <span data-ttu-id="9137a-110">Diversos tipos de eventos de log gravam várias entradas no log.</span><span class="sxs-lookup"><span data-stu-id="9137a-110">Many of the log events write multiple entries to the log.</span></span> <span data-ttu-id="9137a-111">Isso acontece normalmente quando o evento tem fases diferentes.</span><span class="sxs-lookup"><span data-stu-id="9137a-111">This typically occurs when the event has different phases.</span></span> <span data-ttu-id="9137a-112">Por exemplo, o evento de log `ExecuteSQLExecutingQuery` grava três entradas: uma entrada depois que a tarefa adquire uma conexão com o banco de dados, outra depois que a tarefa começa a preparar a instrução SQL e uma depois que a execução da instrução SQL foi concluída.</span><span class="sxs-lookup"><span data-stu-id="9137a-112">For example, the `ExecuteSQLExecutingQuery` log event writes three entries: one entry after the task acquires a connection to the database, another after the task starts to prepare the SQL statement, and one more after the execution of the SQL statement is completed.</span></span>  
  
 <span data-ttu-id="9137a-113">Os objetos [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] a seguir têm entradas de log personalizadas:</span><span class="sxs-lookup"><span data-stu-id="9137a-113">The following [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] objects have custom log entries:</span></span>  
  
 [<span data-ttu-id="9137a-114">Pacote</span><span class="sxs-lookup"><span data-stu-id="9137a-114">Package</span></span>](#Package)  
  
 [<span data-ttu-id="9137a-115">Tarefa Inserção em Massa</span><span class="sxs-lookup"><span data-stu-id="9137a-115">Bulk Insert Task</span></span>](#BulkInsert)  
  
 [<span data-ttu-id="9137a-116">Tarefa de Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="9137a-116">Data Flow Task</span></span>](#DataFlow)  
  
 [<span data-ttu-id="9137a-117">Tarefa Executar DTS 2000</span><span class="sxs-lookup"><span data-stu-id="9137a-117">Execute DTS 2000 Task</span></span>](#ExecuteDTS200)  
  
 [<span data-ttu-id="9137a-118">Tarefa Executar Processo</span><span class="sxs-lookup"><span data-stu-id="9137a-118">Execute Process Task</span></span>](#ExecuteProcess)  
  
 [<span data-ttu-id="9137a-119">Tarefa Executar SQL</span><span class="sxs-lookup"><span data-stu-id="9137a-119">Execute SQL Task</span></span>](#ExecuteSQL)  
  
 [<span data-ttu-id="9137a-120">Tarefa Sistema de Arquivos</span><span class="sxs-lookup"><span data-stu-id="9137a-120">File System Task</span></span>](#FileSystem)  
  
 [<span data-ttu-id="9137a-121">Tarefa FTP</span><span class="sxs-lookup"><span data-stu-id="9137a-121">FTP Task</span></span>](#FTP)  
  
 [<span data-ttu-id="9137a-122">Tarefa Fila de Mensagens</span><span class="sxs-lookup"><span data-stu-id="9137a-122">Message Queue Task</span></span>](#MessageQueue)  
  
 [<span data-ttu-id="9137a-123">Tarefa Script</span><span class="sxs-lookup"><span data-stu-id="9137a-123">Script Task</span></span>](#Script)  
  
 [<span data-ttu-id="9137a-124">Tarefa Enviar Email</span><span class="sxs-lookup"><span data-stu-id="9137a-124">Send Mail Task</span></span>](#SendMail)  
  
 [<span data-ttu-id="9137a-125">Tarefa Transferir Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="9137a-125">Transfer Database Task</span></span>](#TransferDatabase)  
  
 [<span data-ttu-id="9137a-126">Tarefa Transferir Mensagens de Erro</span><span class="sxs-lookup"><span data-stu-id="9137a-126">Transfer Error Messages Task</span></span>](#TransferErrorMessages)  
  
 [<span data-ttu-id="9137a-127">Tarefa Transferir Trabalhos</span><span class="sxs-lookup"><span data-stu-id="9137a-127">Transfer Jobs Task</span></span>](#TransferJobs)  
  
 [<span data-ttu-id="9137a-128">Tarefa Transferir Logons</span><span class="sxs-lookup"><span data-stu-id="9137a-128">Transfer Logins Task</span></span>](#TransferLogins)  
  
 [<span data-ttu-id="9137a-129">Tarefa Transferir Procedimentos Armazenados Mestres</span><span class="sxs-lookup"><span data-stu-id="9137a-129">Transfer Master Stored Procedures Task</span></span>](#TransferMasterStoredProcedures)  
  
 [<span data-ttu-id="9137a-130">Tarefa Transferir Objetos do SQL Server</span><span class="sxs-lookup"><span data-stu-id="9137a-130">Transfer SQL Server Objects Task</span></span>](#TransferSQLServerObjects)  
  
 [<span data-ttu-id="9137a-131">Tarefa Serviços Web</span><span class="sxs-lookup"><span data-stu-id="9137a-131">Web Services Task</span></span>](#WebServices)  
  
 [<span data-ttu-id="9137a-132">Tarefa Leitor de Dados do WMI</span><span class="sxs-lookup"><span data-stu-id="9137a-132">WMI Data Reader Task</span></span>](#WMIDataReader)  
  
 [<span data-ttu-id="9137a-133">Tarefa Detector de Eventos do WMI</span><span class="sxs-lookup"><span data-stu-id="9137a-133">WMI Event Watcher Task</span></span>](#WMIEventWatcher)  
  
 [<span data-ttu-id="9137a-134">XML Task</span><span class="sxs-lookup"><span data-stu-id="9137a-134">XML Task</span></span>](#XML)  
  
## <a name="log-entries"></a><span data-ttu-id="9137a-135">Entradas de log</span><span class="sxs-lookup"><span data-stu-id="9137a-135">Log Entries</span></span>  
  
###  <a name="package"></a><a name="Package"></a> <span data-ttu-id="9137a-136">Pacote</span><span class="sxs-lookup"><span data-stu-id="9137a-136">Package</span></span>  
 <span data-ttu-id="9137a-137">A tabela a seguir relaciona as entradas de log personalizadas para pacotes.</span><span class="sxs-lookup"><span data-stu-id="9137a-137">The following table lists the custom log entries for packages.</span></span>  
  
|<span data-ttu-id="9137a-138">Entrada de log</span><span class="sxs-lookup"><span data-stu-id="9137a-138">Log entry</span></span>|<span data-ttu-id="9137a-139">Descrição</span><span class="sxs-lookup"><span data-stu-id="9137a-139">Description</span></span>|  
|---------------|-----------------|  
|`PackageStart`|<span data-ttu-id="9137a-140">Indica que o pacote começou a ser executado.</span><span class="sxs-lookup"><span data-stu-id="9137a-140">Indicates that the package began to run.</span></span><br /><br /> <span data-ttu-id="9137a-141">Observação: esta entrada de log é gravada no log automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9137a-141">Note: This log entry is automatically written to the log.</span></span> <span data-ttu-id="9137a-142">Não é possível excluí-la.</span><span class="sxs-lookup"><span data-stu-id="9137a-142">You cannot exclude it.</span></span>|  
|`PackageEnd`|<span data-ttu-id="9137a-143">Indica que o pacote foi concluído.</span><span class="sxs-lookup"><span data-stu-id="9137a-143">Indicates that the package completed.</span></span><br /><br /> <span data-ttu-id="9137a-144">Observação: esta entrada de log é gravada no log automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9137a-144">Note: This log entry is automatically written to the log.</span></span> <span data-ttu-id="9137a-145">Não é possível excluí-la.</span><span class="sxs-lookup"><span data-stu-id="9137a-145">You cannot exclude it.</span></span>|  
|`Diagnostic`|<span data-ttu-id="9137a-146">Fornece informações sobre a configuração do sistema que afeta a execução de pacotes como os executáveis numéricos que podem ser executados simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="9137a-146">Provides information about the system configuration that affects package execution such as the number executables that can be run concurrently.</span></span><br /><br /> <span data-ttu-id="9137a-147">A entrada de log `Diagnostic` também inclui entradas anteriores e posteriores a chamadas para provedores de dados externos.</span><span class="sxs-lookup"><span data-stu-id="9137a-147">The `Diagnostic` log entry also includes before and after entries for calls to external data providers.</span></span> <span data-ttu-id="9137a-148">Para obter mais informações, consulte [Solução de problemas de conectividade de pacotes de ferramentas](troubleshooting/troubleshooting-tools-for-package-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="9137a-148">For more information, see [Troubleshooting Tools Package Connectivity](troubleshooting/troubleshooting-tools-for-package-connectivity.md).</span></span>|  
  
###  <a name="bulk-insert-task"></a><a name="BulkInsert"></a> <span data-ttu-id="9137a-149">Tarefa Inserção em Massa</span><span class="sxs-lookup"><span data-stu-id="9137a-149">Bulk Insert Task</span></span>  
 <span data-ttu-id="9137a-150">A seguinte tabela relaciona as entradas de log personalizadas para a tarefa inserção em massa .</span><span class="sxs-lookup"><span data-stu-id="9137a-150">The following table lists the custom log entries for the Bulk Insert task.</span></span>  
  
|<span data-ttu-id="9137a-151">Entrada de log</span><span class="sxs-lookup"><span data-stu-id="9137a-151">Log entry</span></span>|<span data-ttu-id="9137a-152">Descrição</span><span class="sxs-lookup"><span data-stu-id="9137a-152">Description</span></span>|  
|---------------|-----------------|  
|`DTSBulkInsertTaskBegin`|<span data-ttu-id="9137a-153">Indica que a inserção em massa iniciou.</span><span class="sxs-lookup"><span data-stu-id="9137a-153">Indicates that the bulk insert began.</span></span>|  
|`DTSBulkInsertTaskEnd`|<span data-ttu-id="9137a-154">Indica que a inserção em massa foi concluída.</span><span class="sxs-lookup"><span data-stu-id="9137a-154">Indicates that the bulk insert finished.</span></span>|  
|`DTSBulkInsertTaskInfos`|<span data-ttu-id="9137a-155">Fornece informações descritivas sobre a tarefa.</span><span class="sxs-lookup"><span data-stu-id="9137a-155">Provides descriptive information about the task.</span></span>|  
  
###  <a name="data-flow-task"></a><a name="DataFlow"></a> <span data-ttu-id="9137a-156">Data Flow Task</span><span class="sxs-lookup"><span data-stu-id="9137a-156">Data Flow Task</span></span>  
 <span data-ttu-id="9137a-157">A tabela a seguir relaciona as entradas de log personalizadas para a tarefa de Fluxo de Dados.</span><span class="sxs-lookup"><span data-stu-id="9137a-157">The following table lists the custom log entries for the Data Flow task.</span></span>  
  
|<span data-ttu-id="9137a-158">Entrada de log</span><span class="sxs-lookup"><span data-stu-id="9137a-158">Log entry</span></span>|<span data-ttu-id="9137a-159">Descrição</span><span class="sxs-lookup"><span data-stu-id="9137a-159">Description</span></span>|  
|---------------|-----------------|  
|`BufferSizeTuning`|<span data-ttu-id="9137a-160">Indica que a tarefa de Fluxo de Dados alterou o tamanho do buffer.</span><span class="sxs-lookup"><span data-stu-id="9137a-160">Indicates that the Data Flow task changed the size of the buffer.</span></span> <span data-ttu-id="9137a-161">A entrada de log descreve os motivos da mudança de tamanho e relaciona o novo tamanho do buffer temporário.</span><span class="sxs-lookup"><span data-stu-id="9137a-161">The log entry describes the reasons for the size change and lists the temporary new buffer size.</span></span>|  
|`OnPipelinePostEndOfRowset`|<span data-ttu-id="9137a-162">Indica que um componente recebeu o sinal de final do conjunto de linhas, definido pela última chamada do método `ProcessInput`.</span><span class="sxs-lookup"><span data-stu-id="9137a-162">Denotes that a component has been given its end-of-rowset signal, which is set by the last call of the `ProcessInput` method.</span></span> <span data-ttu-id="9137a-163">Uma entrada é gravada para cada componente no fluxo de dados que processa a entrada.</span><span class="sxs-lookup"><span data-stu-id="9137a-163">An entry is written for each component in the data flow that processes input.</span></span> <span data-ttu-id="9137a-164">A entrada contém o nome do componente.</span><span class="sxs-lookup"><span data-stu-id="9137a-164">The entry includes the name of the component.</span></span>|  
|`OnPipelinePostPrimeOutput`|<span data-ttu-id="9137a-165">Indica que o componente completou sua última chamada para o método `PrimeOutput`.</span><span class="sxs-lookup"><span data-stu-id="9137a-165">Indicates that the component has completed its last call to the `PrimeOutput` method.</span></span> <span data-ttu-id="9137a-166">Dependendo do fluxo de dados, várias entradas de log podem ser gravadas.</span><span class="sxs-lookup"><span data-stu-id="9137a-166">Depending on the data flow, multiple log entries may be written.</span></span> <span data-ttu-id="9137a-167">Se o componente for uma fonte, isto significará que o componente tem linhas de processamento concluídas.</span><span class="sxs-lookup"><span data-stu-id="9137a-167">If the component is a source, this means that the component has finished processing rows.</span></span>|  
|`OnPipelinePreEndOfRowset`|<span data-ttu-id="9137a-168">Indica que um componente está prestes a receber o sinal de final do conjunto de linhas, definido pela última chamada do método `ProcessInput`.</span><span class="sxs-lookup"><span data-stu-id="9137a-168">Indicates that a component is about to receive its end-of-rowset signal, which is set by the last call of the `ProcessInput` method.</span></span> <span data-ttu-id="9137a-169">Uma entrada é gravada para cada componente no fluxo de dados que processa a entrada.</span><span class="sxs-lookup"><span data-stu-id="9137a-169">An entry is written for each component in the data flow that processes input.</span></span> <span data-ttu-id="9137a-170">A entrada contém o nome do componente.</span><span class="sxs-lookup"><span data-stu-id="9137a-170">The entry includes the name of the component.</span></span>|  
|`OnPipelinePrePrimeOutput`|<span data-ttu-id="9137a-171">Indica que o componente está prestes a receber sua chamada a partir do método `PrimeOutput`.</span><span class="sxs-lookup"><span data-stu-id="9137a-171">Indicates that the component is about to receive its call from the `PrimeOutput` method.</span></span> <span data-ttu-id="9137a-172">Dependendo do fluxo de dados, várias entradas de log podem ser gravadas.</span><span class="sxs-lookup"><span data-stu-id="9137a-172">Depending on the data flow, multiple log entries may be written.</span></span>|  
|`OnPipelineRowsSent`|<span data-ttu-id="9137a-173">Informa o número de linhas fornecido a uma entrada de componente por uma chamada para o método `ProcessInput`.</span><span class="sxs-lookup"><span data-stu-id="9137a-173">Reports the number of rows provided to a component input by a call to the `ProcessInput` method.</span></span> <span data-ttu-id="9137a-174">A entrada de log inclui o nome do componente.</span><span class="sxs-lookup"><span data-stu-id="9137a-174">The log entry includes the component name.</span></span>|  
|`PipelineBufferLeak`|<span data-ttu-id="9137a-175">Fornece informações sobre qualquer componente que manteve buffers ativos depois que o gerenciador de buffers for desativado.</span><span class="sxs-lookup"><span data-stu-id="9137a-175">Provides information about any component that kept buffers alive after the buffer manager goes away.</span></span> <span data-ttu-id="9137a-176">Isso significa que os recursos de buffers não foram liberados e pode haver vazamentos de memória.</span><span class="sxs-lookup"><span data-stu-id="9137a-176">This means that buffers resources were not released and may cause memory leaks.</span></span> <span data-ttu-id="9137a-177">A entrada de log fornece o nome do componente e a ID do buffer.</span><span class="sxs-lookup"><span data-stu-id="9137a-177">The log entry provides the name of the component and the ID of the buffer.</span></span>|  
|`PipelineExecutionPlan`|<span data-ttu-id="9137a-178">Informa o plano de execução do fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="9137a-178">Reports the execution plan of the data flow.</span></span> <span data-ttu-id="9137a-179">Fornece informações sobre como os buffers serão enviados a componentes.</span><span class="sxs-lookup"><span data-stu-id="9137a-179">It provides information about how buffers will be sent to components.</span></span> <span data-ttu-id="9137a-180">Essas informações, em combinação com a entrada de PipelineExecutionTrees, descrevem o que está acontecendo na tarefa.</span><span class="sxs-lookup"><span data-stu-id="9137a-180">This information, in combination with the PipelineExecutionTrees entry, describes what is occurring in the task.</span></span>|  
|`PipelineExecutionTrees`|<span data-ttu-id="9137a-181">Informa as árvores de execução sobre o layout do fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="9137a-181">Reports the execution trees of the layout in the data flow.</span></span> <span data-ttu-id="9137a-182">O agendador do mecanismo de fluxo de dados usa as árvores para compilar o plano de execução do fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="9137a-182">The scheduler of the data flow engine use the trees to build the execution plan of the data flow.</span></span>|  
|`PipelineInitialization`|<span data-ttu-id="9137a-183">Fornece informações de inicialização sobre a tarefa.</span><span class="sxs-lookup"><span data-stu-id="9137a-183">Provides initialization information about the task.</span></span> <span data-ttu-id="9137a-184">Essas informações incluem os diretórios para armazenamento temporário de dados de BLOB, o tamanho do buffer padrão e o número de linhas em um buffer.</span><span class="sxs-lookup"><span data-stu-id="9137a-184">This information includes the directories to use for temporary storage of BLOB data, the default buffer size, and the number of rows in a buffer.</span></span> <span data-ttu-id="9137a-185">Dependendo da configuração da tarefa de Fluxo de Dados, várias entradas de log podem ser gravadas.</span><span class="sxs-lookup"><span data-stu-id="9137a-185">Depending on the configuration of the Data Flow task, multiple log entries may be written.</span></span>|  
  
###  <a name="execute-dts-2000-task"></a><a name="ExecuteDTS200"></a> <span data-ttu-id="9137a-186">Tarefa Executar DTS 2000</span><span class="sxs-lookup"><span data-stu-id="9137a-186">Execute DTS 2000 Task</span></span>  
 <span data-ttu-id="9137a-187">A tabela a seguir relaciona as entradas de log personalizadas para a tarefa Executar DTS 2000.</span><span class="sxs-lookup"><span data-stu-id="9137a-187">The following table lists the custom log entries for the Execute DTS 2000 task.</span></span>  
  
|<span data-ttu-id="9137a-188">Entrada de log</span><span class="sxs-lookup"><span data-stu-id="9137a-188">Log entry</span></span>|<span data-ttu-id="9137a-189">Descrição</span><span class="sxs-lookup"><span data-stu-id="9137a-189">Description</span></span>|  
|---------------|-----------------|  
|`ExecuteDTS80PackageTaskBegin`|<span data-ttu-id="9137a-190">Indica que a tarefa começou a ser executada em um pacote DTS 2000.</span><span class="sxs-lookup"><span data-stu-id="9137a-190">Indicates that the task began to run a DTS 2000 package.</span></span>|  
|`ExecuteDTS80PackageTaskEnd`|<span data-ttu-id="9137a-191">Indica que a tarefa foi concluída.</span><span class="sxs-lookup"><span data-stu-id="9137a-191">Indicates that the task finished.</span></span><br /><br /> <span data-ttu-id="9137a-192">Observação: o pacote DTS 2000 pode continuar a ser executado após a conclusão da tarefa.</span><span class="sxs-lookup"><span data-stu-id="9137a-192">Note: The DTS 2000 package may continue to run after the task ends.</span></span>|  
|`ExecuteDTS80PackageTaskTaskInfo`|<span data-ttu-id="9137a-193">Fornece informações descritivas sobre a tarefa.</span><span class="sxs-lookup"><span data-stu-id="9137a-193">Provides descriptive information about the task.</span></span>|  
|`ExecuteDTS80PackageTaskTaskResult`|<span data-ttu-id="9137a-194">Informa o resultado de execução do pacote DTS 2000 executado pela tarefa.</span><span class="sxs-lookup"><span data-stu-id="9137a-194">Reports the execution result of the DTS 2000 package that the task ran.</span></span>|  
  
###  <a name="execute-process-task"></a><a name="ExecuteProcess"></a> <span data-ttu-id="9137a-195">Tarefa Executar Processo</span><span class="sxs-lookup"><span data-stu-id="9137a-195">Execute Process Task</span></span>  
 <span data-ttu-id="9137a-196">A tabela a seguir relaciona as entradas de log personalizadas para a tarefa Executar Processo.</span><span class="sxs-lookup"><span data-stu-id="9137a-196">The following table lists the custom log entries for the Execute Process task.</span></span>  
  
|<span data-ttu-id="9137a-197">Entrada de log</span><span class="sxs-lookup"><span data-stu-id="9137a-197">Log entry</span></span>|<span data-ttu-id="9137a-198">Descrição</span><span class="sxs-lookup"><span data-stu-id="9137a-198">Description</span></span>|  
|---------------|-----------------|  
|`ExecuteProcessExecutingProcess`|<span data-ttu-id="9137a-199">Fornece informações sobre o processo do executável que a tarefa está configurada para executar.</span><span class="sxs-lookup"><span data-stu-id="9137a-199">Provides information about the process of running the executable that the task is configured to run.</span></span><br /><br /> <span data-ttu-id="9137a-200">São gravadas duas entradas de log.</span><span class="sxs-lookup"><span data-stu-id="9137a-200">Two log entries are written.</span></span> <span data-ttu-id="9137a-201">Uma contém informações sobre o nome e o local do executável que a tarefa executa e o outro registra a saída do executável.</span><span class="sxs-lookup"><span data-stu-id="9137a-201">One contains information about the name and location of the executable that the task runs, and the other records the exit from the executable.</span></span>|  
|`ExecuteProcessVariableRouting`|<span data-ttu-id="9137a-202">Fornece informações sobre quais variáveis são encaminhadas para a entrada e as saídas do executável.</span><span class="sxs-lookup"><span data-stu-id="9137a-202">Provides information about which variables are routed to the input and outputs of the executable.</span></span> <span data-ttu-id="9137a-203">As entradas de log são gravadas em stdin (a entrada), stdout (a saída) e stderr (a saída do erro).</span><span class="sxs-lookup"><span data-stu-id="9137a-203">Log entries are written for stdin (the input), stdout (the output), and stderr (the error output).</span></span>|  
  
###  <a name="execute-sql-task"></a><a name="ExecuteSQL"></a> <span data-ttu-id="9137a-204">Tarefa Executar SQL</span><span class="sxs-lookup"><span data-stu-id="9137a-204">Execute SQL Task</span></span>  
 <span data-ttu-id="9137a-205">A tabela a seguir descreve a entrada de log personalizada da tarefa Executar SQL.</span><span class="sxs-lookup"><span data-stu-id="9137a-205">The following table describes the custom log entry for the Execute SQL task.</span></span>  
  
|<span data-ttu-id="9137a-206">Entrada de log</span><span class="sxs-lookup"><span data-stu-id="9137a-206">Log entry</span></span>|<span data-ttu-id="9137a-207">Descrição</span><span class="sxs-lookup"><span data-stu-id="9137a-207">Description</span></span>|  
|---------------|-----------------|  
|`ExecuteSQLExecutingQuery`|<span data-ttu-id="9137a-208">Fornece informações sobre as fases de execução da instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="9137a-208">Provides information about the execution phases of the SQL statement.</span></span> <span data-ttu-id="9137a-209">As entradas de log são gravadas quando a tarefa adquire conexão com o banco de dados, quando a tarefa começa a preparar a instrução SQL e depois que a execução da instrução SQL é concluída.</span><span class="sxs-lookup"><span data-stu-id="9137a-209">Log entries are written when the task acquires connection to the database, when the task starts to prepare the SQL statement, and after the execution of the SQL statement is completed.</span></span> <span data-ttu-id="9137a-210">A entrada de log da fase de preparação inclui a instrução SQL usada pela tarefa.</span><span class="sxs-lookup"><span data-stu-id="9137a-210">The log entry for the prepare phase includes the SQL statement that the task uses.</span></span>|  
  
###  <a name="file-system-task"></a><a name="FileSystem"></a> <span data-ttu-id="9137a-211">Tarefa Sistema de Arquivos</span><span class="sxs-lookup"><span data-stu-id="9137a-211">File System Task</span></span>  
 <span data-ttu-id="9137a-212">A tabela a seguir descreve a entrada de log personalizada da tarefa Sistema de Arquivos.</span><span class="sxs-lookup"><span data-stu-id="9137a-212">The following table describes the custom log entry for the File System task.</span></span>  
  
|<span data-ttu-id="9137a-213">Entrada de log</span><span class="sxs-lookup"><span data-stu-id="9137a-213">Log entry</span></span>|<span data-ttu-id="9137a-214">Descrição</span><span class="sxs-lookup"><span data-stu-id="9137a-214">Description</span></span>|  
|---------------|-----------------|  
|`FileSystemOperation`|<span data-ttu-id="9137a-215">Informa a operação executada pela tarefa.</span><span class="sxs-lookup"><span data-stu-id="9137a-215">Reports the operation that the task performs.</span></span> <span data-ttu-id="9137a-216">A entrada de log é gravada quando a operação de sistema de arquivos é iniciada e inclui informações sobre a origem e o destino.</span><span class="sxs-lookup"><span data-stu-id="9137a-216">The log entry is written when the file system operation starts and includes information about the source and destination.</span></span>|  
  
###  <a name="ftp-task"></a><a name="FTP"></a> <span data-ttu-id="9137a-217">Tarefa FTP</span><span class="sxs-lookup"><span data-stu-id="9137a-217">FTP Task</span></span>  
 <span data-ttu-id="9137a-218">A tabela a seguir relaciona as entradas de log personalizadas da tarefa FTP.</span><span class="sxs-lookup"><span data-stu-id="9137a-218">The following table lists the custom log entries for the FTP task.</span></span>  
  
|<span data-ttu-id="9137a-219">Entrada de log</span><span class="sxs-lookup"><span data-stu-id="9137a-219">Log entry</span></span>|<span data-ttu-id="9137a-220">Descrição</span><span class="sxs-lookup"><span data-stu-id="9137a-220">Description</span></span>|  
|---------------|-----------------|  
|`FTPConnectingToServer`|<span data-ttu-id="9137a-221">Indica que a tarefa iniciou uma conexão com o servidor FTP.</span><span class="sxs-lookup"><span data-stu-id="9137a-221">Indicates that the task initiated a connection to the FTP server.</span></span>|  
|`FTPOperation`|<span data-ttu-id="9137a-222">Informa o início e o tipo de operação de FTP que a tarefa executa.</span><span class="sxs-lookup"><span data-stu-id="9137a-222">Reports the beginning of and the type of FTP operation that the task performs.</span></span>|  
  
###  <a name="message-queue-task"></a><a name="MessageQueue"></a> <span data-ttu-id="9137a-223">Tarefa Fila de Mensagens</span><span class="sxs-lookup"><span data-stu-id="9137a-223">Message Queue Task</span></span>  
 <span data-ttu-id="9137a-224">A tabela a seguir relaciona as entradas de log personalizadas para a tarefa Fila de Mensagens.</span><span class="sxs-lookup"><span data-stu-id="9137a-224">The following table lists the custom log entries for the Message Queue task.</span></span>  
  
|<span data-ttu-id="9137a-225">Entrada de log</span><span class="sxs-lookup"><span data-stu-id="9137a-225">Log entry</span></span>|<span data-ttu-id="9137a-226">Descrição</span><span class="sxs-lookup"><span data-stu-id="9137a-226">Description</span></span>|  
|---------------|-----------------|  
|`MSMQAfterOpen`|<span data-ttu-id="9137a-227">Indica que a tarefa finalizou a abertura da fila de mensagens.</span><span class="sxs-lookup"><span data-stu-id="9137a-227">Indicates that the task finished opening the message queue.</span></span>|  
|`MSMQBeforeOpen`|<span data-ttu-id="9137a-228">Indica que a tarefa começou a abrir a fila de mensagens.</span><span class="sxs-lookup"><span data-stu-id="9137a-228">Indicates that the task began to open the message queue.</span></span>|  
|`MSMQBeginReceive`|<span data-ttu-id="9137a-229">Indica que a tarefa começou a receber uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="9137a-229">Indicates that the task began to receive a message.</span></span>|  
|`MSMQBeginSend`|<span data-ttu-id="9137a-230">Indica que a tarefa começou a enviar uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="9137a-230">Indicates that the task began to send a message.</span></span>|  
|`MSMQEndReceive`|<span data-ttu-id="9137a-231">Indica que a tarefa terminou de receber uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="9137a-231">Indicates that the task finished receiving a message.</span></span>|  
|`MSMQEndSend`|<span data-ttu-id="9137a-232">Indica que a tarefa terminou de enviar uma mensagem</span><span class="sxs-lookup"><span data-stu-id="9137a-232">Indicates that the task finished sending a message</span></span>|  
|`MSMQTaskInfo`|<span data-ttu-id="9137a-233">Fornece informações descritivas sobre a tarefa.</span><span class="sxs-lookup"><span data-stu-id="9137a-233">Provides descriptive information about the task.</span></span>|  
|`MSMQTaskTimeOut`|<span data-ttu-id="9137a-234">Indica que o tempo limite da tarefa foi esgotado.</span><span class="sxs-lookup"><span data-stu-id="9137a-234">Indicates that the task timed out.</span></span>|  
  
###  <a name="script-task"></a><a name="Script"></a> <span data-ttu-id="9137a-235">Tarefa Script</span><span class="sxs-lookup"><span data-stu-id="9137a-235">Script Task</span></span>  
 <span data-ttu-id="9137a-236">A tabela a seguir descreve a entrada de log personalizada da tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="9137a-236">The following table describes the custom log entry for the Script task.</span></span>  
  
|<span data-ttu-id="9137a-237">Entrada de log</span><span class="sxs-lookup"><span data-stu-id="9137a-237">Log entry</span></span>|<span data-ttu-id="9137a-238">Descrição</span><span class="sxs-lookup"><span data-stu-id="9137a-238">Description</span></span>|  
|---------------|-----------------|  
|`ScriptTaskLogEntry`|<span data-ttu-id="9137a-239">Informa os resultados da implementação do registro em log no script.</span><span class="sxs-lookup"><span data-stu-id="9137a-239">Reports the results of implementing logging in the script.</span></span> <span data-ttu-id="9137a-240">Uma entrada de log é gravada para cada chamada ao método `Log` do objeto `Dts`.</span><span class="sxs-lookup"><span data-stu-id="9137a-240">A log entry is written for each call to the `Log` method of the `Dts` object.</span></span> <span data-ttu-id="9137a-241">A entrada é gravada quando o código é executado.</span><span class="sxs-lookup"><span data-stu-id="9137a-241">The entry is written when the code is run.</span></span> <span data-ttu-id="9137a-242">Para obter mais informações, consulte [Registro em log na Tarefa Script](extending-packages-scripting/task/logging-in-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="9137a-242">For more information, see [Logging in the Script Task](extending-packages-scripting/task/logging-in-the-script-task.md).</span></span>|  
  
###  <a name="send-mail-task"></a><a name="SendMail"></a> <span data-ttu-id="9137a-243">Tarefa Enviar Email</span><span class="sxs-lookup"><span data-stu-id="9137a-243">Send Mail Task</span></span>  
 <span data-ttu-id="9137a-244">A tabela a seguir relaciona as entradas de log personalizadas para a tarefa Enviar Email.</span><span class="sxs-lookup"><span data-stu-id="9137a-244">The following table lists the custom log entries for the Send Mail task.</span></span>  
  
|<span data-ttu-id="9137a-245">Entrada de log</span><span class="sxs-lookup"><span data-stu-id="9137a-245">Log entry</span></span>|<span data-ttu-id="9137a-246">Descrição</span><span class="sxs-lookup"><span data-stu-id="9137a-246">Description</span></span>|  
|---------------|-----------------|  
|`SendMailTaskBegin`|<span data-ttu-id="9137a-247">Indica que a tarefa começou a enviar uma mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="9137a-247">Indicates that the task began to send an e-mail message.</span></span>|  
|`SendMailTaskEnd`|<span data-ttu-id="9137a-248">Indica que a tarefa terminou de enviar uma mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="9137a-248">Indicates that the task finished sending an e-mail message.</span></span>|  
|`SendMailTaskInfo`|<span data-ttu-id="9137a-249">Fornece informações descritivas sobre a tarefa.</span><span class="sxs-lookup"><span data-stu-id="9137a-249">Provides descriptive information about the task.</span></span>|  
  
###  <a name="transfer-database-task"></a><a name="TransferDatabase"></a> <span data-ttu-id="9137a-250">Tarefa Transferir Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="9137a-250">Transfer Database Task</span></span>  
 <span data-ttu-id="9137a-251">A tabela a seguir relaciona as entradas de log personalizadas para a tarefa Transferir Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="9137a-251">The following table lists the custom log entries for the Transfer Database task.</span></span>  
  
|<span data-ttu-id="9137a-252">Entrada de log</span><span class="sxs-lookup"><span data-stu-id="9137a-252">Log entry</span></span>|<span data-ttu-id="9137a-253">Descrição</span><span class="sxs-lookup"><span data-stu-id="9137a-253">Description</span></span>|  
|---------------|-----------------|  
|`SourceDB`|<span data-ttu-id="9137a-254">Especifica o banco de dados que a tarefa copiou.</span><span class="sxs-lookup"><span data-stu-id="9137a-254">Specifies the database that the task copied.</span></span>|  
|`SourceSQLServer`|<span data-ttu-id="9137a-255">Especifica o computador a partir do qual o banco de dados foi copiado.</span><span class="sxs-lookup"><span data-stu-id="9137a-255">Specifies the computer from which the database was copied.</span></span>|  
  
###  <a name="transfer-error-messages-task"></a><a name="TransferErrorMessages"></a> <span data-ttu-id="9137a-256">Tarefa Transferir Mensagens de Erro</span><span class="sxs-lookup"><span data-stu-id="9137a-256">Transfer Error Messages Task</span></span>  
 <span data-ttu-id="9137a-257">A tabela a seguir relaciona as entradas de log personalizadas para a tarefa Transferir Mensagens de Erro.</span><span class="sxs-lookup"><span data-stu-id="9137a-257">The following table lists the custom log entries for the Transfer Error Messages task.</span></span>  
  
|<span data-ttu-id="9137a-258">Entrada de log</span><span class="sxs-lookup"><span data-stu-id="9137a-258">Log entry</span></span>|<span data-ttu-id="9137a-259">Descrição</span><span class="sxs-lookup"><span data-stu-id="9137a-259">Description</span></span>|  
|---------------|-----------------|  
|`TransferErrorMessagesTaskFinishedTransferringObjects`|<span data-ttu-id="9137a-260">Indica que a tarefa terminou de transferir mensagens de erro.</span><span class="sxs-lookup"><span data-stu-id="9137a-260">Indicates that the task finished transferring error messages.</span></span>|  
|`TransferErrorMessagesTaskStartTransferringObjects`|<span data-ttu-id="9137a-261">Indica que a tarefa começou a transferir as mensagens de erro.</span><span class="sxs-lookup"><span data-stu-id="9137a-261">Indicates that the task started to transfer error messages.</span></span>|  
  
###  <a name="transfer-jobs-task"></a><a name="TransferJobs"></a> <span data-ttu-id="9137a-262">Tarefa Transferir Trabalhos</span><span class="sxs-lookup"><span data-stu-id="9137a-262">Transfer Jobs Task</span></span>  
 <span data-ttu-id="9137a-263">A tabela a seguir relaciona as entradas de log personalizadas para a tarefa Transferir Trabalhos.</span><span class="sxs-lookup"><span data-stu-id="9137a-263">The following table lists the custom log entries for the Transfer Jobs task.</span></span>  
  
|<span data-ttu-id="9137a-264">Entrada de log</span><span class="sxs-lookup"><span data-stu-id="9137a-264">Log entry</span></span>|<span data-ttu-id="9137a-265">Descrição</span><span class="sxs-lookup"><span data-stu-id="9137a-265">Description</span></span>|  
|---------------|-----------------|  
|`TransferJobsTaskFinishedTransferringObjects`|<span data-ttu-id="9137a-266">Indica que a tarefa terminou a transferência dos trabalhos do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="9137a-266">Indicates that the task finished transferring [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs.</span></span>|  
|`TransferJobsTaskStartTransferringObjects`|<span data-ttu-id="9137a-267">Indica que a tarefa começou a transferência dos trabalhos do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="9137a-267">Indicates that the task started to transfer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs.</span></span>|  
  
###  <a name="transfer-logins-task"></a><a name="TransferLogins"></a> <span data-ttu-id="9137a-268">Tarefa Transferir Logons</span><span class="sxs-lookup"><span data-stu-id="9137a-268">Transfer Logins Task</span></span>  
 <span data-ttu-id="9137a-269">A tabela a seguir relaciona as entradas de log personalizadas para a tarefa Transferir Logons.</span><span class="sxs-lookup"><span data-stu-id="9137a-269">The following table lists the custom log entries for the Transfer Logins task.</span></span>  
  
|<span data-ttu-id="9137a-270">Entrada de log</span><span class="sxs-lookup"><span data-stu-id="9137a-270">Log entry</span></span>|<span data-ttu-id="9137a-271">Descrição</span><span class="sxs-lookup"><span data-stu-id="9137a-271">Description</span></span>|  
|---------------|-----------------|  
|`TransferLoginsTaskFinishedTransferringObjects`|<span data-ttu-id="9137a-272">Indica que a tarefa terminou a transferência dos logons.</span><span class="sxs-lookup"><span data-stu-id="9137a-272">Indicates that the task finished transferring logins.</span></span>|  
|`TransferLoginsTaskStartTransferringObjects`|<span data-ttu-id="9137a-273">Indica que a tarefa começou a transferência dos logons.</span><span class="sxs-lookup"><span data-stu-id="9137a-273">Indicates that the task started to transfer logins.</span></span>|  
  
###  <a name="transfer-master-stored-procedures-task"></a><a name="TransferMasterStoredProcedures"></a> <span data-ttu-id="9137a-274">Tarefa Transferir Procedimentos Armazenados Mestres</span><span class="sxs-lookup"><span data-stu-id="9137a-274">Transfer Master Stored Procedures Task</span></span>  
 <span data-ttu-id="9137a-275">A tabela a seguir relaciona as entradas de log personalizadas para a tarefa Transferir Procedimentos Armazenados Mestres.</span><span class="sxs-lookup"><span data-stu-id="9137a-275">The following table lists the custom log entries for the Transfer Master Stored Procedures task.</span></span>  
  
|<span data-ttu-id="9137a-276">Entrada de log</span><span class="sxs-lookup"><span data-stu-id="9137a-276">Log entry</span></span>|<span data-ttu-id="9137a-277">Descrição</span><span class="sxs-lookup"><span data-stu-id="9137a-277">Description</span></span>|  
|---------------|-----------------|  
|`TransferStoredProceduresTaskFinishedTransferringObjects`|<span data-ttu-id="9137a-278">Indica que a tarefa terminou de transferir procedimentos armazenados definidos pelo usuário armazenados no banco de dados **mestre** .</span><span class="sxs-lookup"><span data-stu-id="9137a-278">Indicates that the task finished transferring user-defined stored procedures that are stored in the **master** database.</span></span>|  
|`TransferStoredProceduresTaskStartTransferringObjects`|<span data-ttu-id="9137a-279">Indica que a tarefa começou a transferir procedimentos armazenados definidos pelo usuário armazenados no banco de dados **mestre** .</span><span class="sxs-lookup"><span data-stu-id="9137a-279">Indicates that the task started to transfer user-defined stored procedures that are stored in the **master** database.</span></span>|  
  
###  <a name="transfer-sql-server-objects-task"></a><a name="TransferSQLServerObjects"></a> <span data-ttu-id="9137a-280">Tarefa Transferir Objetos do SQL Server</span><span class="sxs-lookup"><span data-stu-id="9137a-280">Transfer SQL Server Objects Task</span></span>  
 <span data-ttu-id="9137a-281">A tabela a seguir relaciona as entradas de log personalizadas da tarefa Transferir Objetos do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9137a-281">The following table lists the custom log entries for the Transfer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Objects task.</span></span>  
  
|<span data-ttu-id="9137a-282">Entrada de log</span><span class="sxs-lookup"><span data-stu-id="9137a-282">Log entry</span></span>|<span data-ttu-id="9137a-283">Descrição</span><span class="sxs-lookup"><span data-stu-id="9137a-283">Description</span></span>|  
|---------------|-----------------|  
|`TransferSqlServerObjectsTaskFinishedTransferringObjects`|<span data-ttu-id="9137a-284">Indica que a tarefa terminou a transferência dos objetos de banco de dados do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9137a-284">Indicates that the task finished transferring [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database objects.</span></span>|  
|`TransferSqlServerObjectsTaskStartTransferringObjects`|<span data-ttu-id="9137a-285">Indica que a tarefa começou a transferência dos objetos de banco de dados do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9137a-285">Indicates that the task started to transfer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database objects.</span></span>|  
  
###  <a name="web-services-task"></a><a name="WebServices"></a> <span data-ttu-id="9137a-286">Tarefa Serviços Web</span><span class="sxs-lookup"><span data-stu-id="9137a-286">Web Services Task</span></span>  
 <span data-ttu-id="9137a-287">A tabela a seguir relaciona as entradas de log personalizadas que podem ser habilitadas para a tarefa Serviços Web.</span><span class="sxs-lookup"><span data-stu-id="9137a-287">The following table lists the custom log entries that you can enable for the Web Services task.</span></span>  
  
|<span data-ttu-id="9137a-288">Entrada de log</span><span class="sxs-lookup"><span data-stu-id="9137a-288">Log entry</span></span>|<span data-ttu-id="9137a-289">Descrição</span><span class="sxs-lookup"><span data-stu-id="9137a-289">Description</span></span>|  
|---------------|-----------------|  
|`WSTaskBegin`|<span data-ttu-id="9137a-290">A tarefa começou a acessar um serviço Web.</span><span class="sxs-lookup"><span data-stu-id="9137a-290">The task began to access a Web service.</span></span>|  
|`WSTaskEnd`|<span data-ttu-id="9137a-291">A tarefa completou um método de serviço Web.</span><span class="sxs-lookup"><span data-stu-id="9137a-291">The task completed a Web service method.</span></span>|  
|`WSTaskInfo`|<span data-ttu-id="9137a-292">Informações descritivas sobre a tarefa.</span><span class="sxs-lookup"><span data-stu-id="9137a-292">Descriptive information about the task.</span></span>|  
  
###  <a name="wmi-data-reader-task"></a><a name="WMIDataReader"></a> <span data-ttu-id="9137a-293">Tarefa Leitor de Dados do WMI</span><span class="sxs-lookup"><span data-stu-id="9137a-293">WMI Data Reader Task</span></span>  
 <span data-ttu-id="9137a-294">A tabela a seguir relaciona as entradas de log personalizadas para a tarefa Leitor de Dados do WMI.</span><span class="sxs-lookup"><span data-stu-id="9137a-294">The following table lists the custom log entries for the WMI Data Reader task.</span></span>  
  
|<span data-ttu-id="9137a-295">Entrada de log</span><span class="sxs-lookup"><span data-stu-id="9137a-295">Log entry</span></span>|<span data-ttu-id="9137a-296">Descrição</span><span class="sxs-lookup"><span data-stu-id="9137a-296">Description</span></span>|  
|---------------|-----------------|  
|`WMIDataReaderGettingWMIData`|<span data-ttu-id="9137a-297">Indica que a tarefa começou a ser ler os dados do WMI.</span><span class="sxs-lookup"><span data-stu-id="9137a-297">Indicates that the task began to read WMI data.</span></span>|  
|`WMIDataReaderOperation`|<span data-ttu-id="9137a-298">Informa a consulta WQL executada pela tarefa.</span><span class="sxs-lookup"><span data-stu-id="9137a-298">Reports the WQL query that the task ran.</span></span>|  
  
###  <a name="wmi-event-watcher-task"></a><a name="WMIEventWatcher"></a> <span data-ttu-id="9137a-299">Tarefa Detector de Eventos do WMI</span><span class="sxs-lookup"><span data-stu-id="9137a-299">WMI Event Watcher Task</span></span>  
 <span data-ttu-id="9137a-300">A tabela a seguir relaciona as entradas de registro personalizadas da tarefa Detector de Eventos do WMI.</span><span class="sxs-lookup"><span data-stu-id="9137a-300">The following table lists the custom log entries for the WMI Event Watcher task.</span></span>  
  
|<span data-ttu-id="9137a-301">Entrada de log</span><span class="sxs-lookup"><span data-stu-id="9137a-301">Log entry</span></span>|<span data-ttu-id="9137a-302">Descrição</span><span class="sxs-lookup"><span data-stu-id="9137a-302">Description</span></span>|  
|---------------|-----------------|  
|`WMIEventWatcherEventOccurred`|<span data-ttu-id="9137a-303">Mostra que o evento ocorrido era o que a tarefa estava monitorando.</span><span class="sxs-lookup"><span data-stu-id="9137a-303">Denotes that the event occurred that the task was monitoring.</span></span>|  
|`WMIEventWatcherTimedout`|<span data-ttu-id="9137a-304">Indica que o tempo limite da tarefa foi esgotado.</span><span class="sxs-lookup"><span data-stu-id="9137a-304">Indicates that the task timed out.</span></span>|  
|`WMIEventWatcherWatchingForWMIEvents`|<span data-ttu-id="9137a-305">Indica que a tarefa começou a executar a consulta WQL.</span><span class="sxs-lookup"><span data-stu-id="9137a-305">Indicates that the task began to execute the WQL query.</span></span> <span data-ttu-id="9137a-306">A entrada inclui a consulta.</span><span class="sxs-lookup"><span data-stu-id="9137a-306">The entry includes the query.</span></span>|  
  
###  <a name="xml-task"></a><a name="XML"></a> <span data-ttu-id="9137a-307">XML Task</span><span class="sxs-lookup"><span data-stu-id="9137a-307">XML Task</span></span>  
 <span data-ttu-id="9137a-308">A tabela a seguir descreve a entrada de log personalizada da tarefa XML.</span><span class="sxs-lookup"><span data-stu-id="9137a-308">The following table describes the custom log entry for the XML task.</span></span>  
  
|<span data-ttu-id="9137a-309">Entrada de log</span><span class="sxs-lookup"><span data-stu-id="9137a-309">Log entry</span></span>|<span data-ttu-id="9137a-310">Descrição</span><span class="sxs-lookup"><span data-stu-id="9137a-310">Description</span></span>|  
|---------------|-----------------|  
|`XMLOperation`|<span data-ttu-id="9137a-311">Fornece informações sobre a operação executada pela tarefa</span><span class="sxs-lookup"><span data-stu-id="9137a-311">Provides information about the operation that the task performs</span></span>|   
  
## <a name="see-also"></a><span data-ttu-id="9137a-312">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9137a-312">See Also</span></span>  
 [<span data-ttu-id="9137a-313">Registro em Log do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9137a-313">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
