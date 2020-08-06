---
title: Propriedades do log | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- QueryLogFileSize property
- QueryLogTableName property
- TraceBackgroundDistributionPeriod property
- TraceMaxRowsetSize property
- NullKeyConvertedToUnknown property
- CrashReportsFolder property
- TraceDefinitionFile property
- SQLDumperFlagsOn property
- KeyErrorLimit property
- SnapshotDefinitionFile property
- MinidumpErrorList property
- ErrorLogFileName property
- KeyDuplicate property
- IgnoreDataTruncation property
- logs [Analysis Services]
- Enabled property
- FileSizeMB property
- TraceFileWriteTrailerPeriod property
- TraceQueryResponseTextChunkSize property
- File property
- FileBufferSize property
- TraceRowsetBackgroundFlushPeriod property
- ErrorLogFileSize property
- TraceRequestParameters property
- KeyErrorLimitAction property
- CreateQueryLogTable property
- LogDir property
- TraceBackgroundFlushPeriod property
- TraceFileBufferSize property
- SQLDumperFlagsOff property
- QueryLogConnectionString property
- KeyNotFound property
- KeyErrorLogFile property
- TraceReportFQDN property
- KeyErrorAction property
- QueryLogFileName property
- MessageLogs property
- MiniDumpFlagsOn property
- SnapshotFrequencySec property
- QueryLogSampling property
- CreateAndSendCrashReports property
- LogDurationSec property
ms.assetid: 33fd90ee-cead-48f0-8ff9-9b458994c766
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3761ce3dca232db8968a2a7cba083dcc5554d792
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686389"
---
# <a name="log-properties"></a><span data-ttu-id="1d788-102">Propriedades do log</span><span class="sxs-lookup"><span data-stu-id="1d788-102">Log Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="1d788-103">oferece suporte às propriedades do servidor de log listadas nas tabelas a seguir.</span><span class="sxs-lookup"><span data-stu-id="1d788-103">supports the log server properties listed in the following tables.</span></span> <span data-ttu-id="1d788-104">Para obter mais informações sobre as propriedades de servidor adicionais e como defini-las, consulte [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="1d788-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
## <a name="general"></a><span data-ttu-id="1d788-105">Geral</span><span class="sxs-lookup"><span data-stu-id="1d788-105">General</span></span>  
 `File`  
 <span data-ttu-id="1d788-106">Uma propriedade de cadeia de caracteres que identifica o nome do arquivo de log do servidor.</span><span class="sxs-lookup"><span data-stu-id="1d788-106">A string property that identifies the name of the server log file.</span></span> <span data-ttu-id="1d788-107">Esta propriedade só se aplicará quando um arquivo de disco for usado para log, em vez de uma tabela de banco de dados (o comportamento padrão).</span><span class="sxs-lookup"><span data-stu-id="1d788-107">This property only applies when a disk file is used for logging, as opposed to a database table (the default behavior).</span></span>  
  
 <span data-ttu-id="1d788-108">O valor padrão desta propriedade é msmdsrv.log.</span><span class="sxs-lookup"><span data-stu-id="1d788-108">The default value for this property is msmdsrv.log.</span></span>  
  
 `FileBufferSize`  
 <span data-ttu-id="1d788-109">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d788-109">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MessageLogs`  
 <span data-ttu-id="1d788-110">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d788-110">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="error-log"></a><span data-ttu-id="1d788-111">Log de erros</span><span class="sxs-lookup"><span data-stu-id="1d788-111">Error Log</span></span>  
 <span data-ttu-id="1d788-112">Você pode definir essas propriedades no nível da instância de servidor para modificar os valores padrão para a Configuração de Erros que aparece em outras ferramentas e designers.</span><span class="sxs-lookup"><span data-stu-id="1d788-112">You can set these properties at the server instance level to modify the default values for Error Configuration that appear in other tools and designers.</span></span> <span data-ttu-id="1d788-113">Consulte [configuração de erro para o processamento de cubo, partição e dimensão &#40;SSAS-multidimensional&#41;](../multidimensional-models/error-configuration-for-cube-partition-and-dimension-processing.md) e <xref:Microsoft.AnalysisServices.MiningStructure.ErrorConfiguration%2A> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="1d788-113">See [Error Configuration for Cube, Partition, and Dimension Processing &#40;SSAS - Multidimensional&#41;](../multidimensional-models/error-configuration-for-cube-partition-and-dimension-processing.md) and <xref:Microsoft.AnalysisServices.MiningStructure.ErrorConfiguration%2A> for more information.</span></span>  
  
 <span data-ttu-id="1d788-114">**ErrorLog\ErrorLogFileName**</span><span class="sxs-lookup"><span data-stu-id="1d788-114">**ErrorLog\ErrorLogFileName**</span></span>  
 <span data-ttu-id="1d788-115">Uma propriedade usada como padrão durante a operação de processamento executada pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="1d788-115">A property used as a default during processing operation performed by the server.</span></span>  
  
 <span data-ttu-id="1d788-116">**ErrorLog\ErrorLogFileSize**</span><span class="sxs-lookup"><span data-stu-id="1d788-116">**ErrorLog\ErrorLogFileSize**</span></span>  
 <span data-ttu-id="1d788-117">Uma propriedade usada como padrão durante a operação de processamento executada pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="1d788-117">A property used as a default during processing operation performed by the server.</span></span>  
  
 <span data-ttu-id="1d788-118">**ErrorLog\KeyErrorAction**</span><span class="sxs-lookup"><span data-stu-id="1d788-118">**ErrorLog\KeyErrorAction**</span></span>  
 <span data-ttu-id="1d788-119">Especifica a ação executada pelo servidor quando um erro `KeyNotFound` ocorre.</span><span class="sxs-lookup"><span data-stu-id="1d788-119">Specifies the action taken by the server when a `KeyNotFound` error occurs.</span></span> <span data-ttu-id="1d788-120">As respostas válidas para esse erro incluem:</span><span class="sxs-lookup"><span data-stu-id="1d788-120">Valid responses to this error include:</span></span>  
  
-   <span data-ttu-id="1d788-121">`ConvertToUnknown` informa ao servidor para alocar o valor de chave de erro para o membro desconhecido.</span><span class="sxs-lookup"><span data-stu-id="1d788-121">`ConvertToUnknown` tells the server to allocate the error key value to the unknown member.</span></span>  
  
-   <span data-ttu-id="1d788-122">`DiscardRecord` informa ao servidor para excluir o registro.</span><span class="sxs-lookup"><span data-stu-id="1d788-122">`DiscardRecord` tells the server to exclude the record.</span></span>  
  
 <span data-ttu-id="1d788-123">**ErrorLog\KeyErrorLogFile**</span><span class="sxs-lookup"><span data-stu-id="1d788-123">**ErrorLog\KeyErrorLogFile**</span></span>  
 <span data-ttu-id="1d788-124">Esse é um nome de arquivo definido pelo usuário que deve ter uma extensão de arquivo .log, localizado em uma pasta na qual a conta de serviço tem permissões de leitura/gravação.</span><span class="sxs-lookup"><span data-stu-id="1d788-124">This is a user-defined filename that must have a .log file extension, located in a folder on which the service account has read-write permissions.</span></span> <span data-ttu-id="1d788-125">Este arquivo de log conterá somente os erros gerados durante o processamento.</span><span class="sxs-lookup"><span data-stu-id="1d788-125">This log file will only contain errors generated during processing.</span></span> <span data-ttu-id="1d788-126">Use o Flight Recorder se precisar de informações mais detalhadas.</span><span class="sxs-lookup"><span data-stu-id="1d788-126">Use the Flight Recorder if you require more detailed information.</span></span>  
  
 <span data-ttu-id="1d788-127">**ErrorLog\KeyErrorLimit**</span><span class="sxs-lookup"><span data-stu-id="1d788-127">**ErrorLog\KeyErrorLimit**</span></span>  
 <span data-ttu-id="1d788-128">Esse é o número máximo de erros de integridade de dados que o servidor permitirá antes da falha do processamento.</span><span class="sxs-lookup"><span data-stu-id="1d788-128">This is the maximum number of data integrity errors that the server will allow before failing the processing.</span></span> <span data-ttu-id="1d788-129">Um valor -1 indica que não há limite.</span><span class="sxs-lookup"><span data-stu-id="1d788-129">A value of -1 indicates that there is no limit.</span></span> <span data-ttu-id="1d788-130">O padrão é 0, o que significa parar o processamento depois do primeiro erro.</span><span class="sxs-lookup"><span data-stu-id="1d788-130">The default is 0, which means processing stops after the first error occurs.</span></span> <span data-ttu-id="1d788-131">Você também pode defini-lo como um número inteiro.</span><span class="sxs-lookup"><span data-stu-id="1d788-131">You can also set it to a whole number.</span></span>  
  
 <span data-ttu-id="1d788-132">**ErrorLog\KeyErrorLimitAction**</span><span class="sxs-lookup"><span data-stu-id="1d788-132">**ErrorLog\KeyErrorLimitAction**</span></span>  
 <span data-ttu-id="1d788-133">Especifica a ação executada pelo servidor quando o número de erros de chave atingiu o limite superior.</span><span class="sxs-lookup"><span data-stu-id="1d788-133">Specifies the action taken by the server when the number of key errors has reached the upper limit.</span></span> <span data-ttu-id="1d788-134">As respostas válidas para essa ação incluem:</span><span class="sxs-lookup"><span data-stu-id="1d788-134">Valid responses to this action include:</span></span>  
  
-   <span data-ttu-id="1d788-135">`StopProcessing` informa ao servidor para parar o processamento quando o limite de erros for atingido.</span><span class="sxs-lookup"><span data-stu-id="1d788-135">`StopProcessing` tells the server to stop processing when the error limit is reached.</span></span>  
  
-   <span data-ttu-id="1d788-136">`StopLogging` informa ao servidor para parar o log de erros quando o limite de erros for atingido, mas permitir que o processamento continue.</span><span class="sxs-lookup"><span data-stu-id="1d788-136">`StopLogging` tells the server to stop logging errors when the error limit is reached, but allow processing to continue.</span></span>  
  
 <span data-ttu-id="1d788-137">**ErrorLog\ LogErrorTypes\KeyNotFound**</span><span class="sxs-lookup"><span data-stu-id="1d788-137">**ErrorLog\ LogErrorTypes\KeyNotFound**</span></span>  
 <span data-ttu-id="1d788-138">Especifica a ação executada pelo servidor quando um erro `KeyNotFound` ocorre.</span><span class="sxs-lookup"><span data-stu-id="1d788-138">Specifies the action taken by the server when a `KeyNotFound` error occurs.</span></span> <span data-ttu-id="1d788-139">As respostas válidas para esse erro incluem:</span><span class="sxs-lookup"><span data-stu-id="1d788-139">Valid responses to this error include:</span></span>  
  
-   <span data-ttu-id="1d788-140">`IgnoreError` informa ao servidor para continuar o processamento sem registrar em log o erros ou contá-lo até o limite de erros de chave.</span><span class="sxs-lookup"><span data-stu-id="1d788-140">`IgnoreError` tells the server to continue processing without logging the error or counting it towards the key error limit.</span></span> <span data-ttu-id="1d788-141">Ao ignorar o erro, você simplesmente permite que o processamento continue sem adicioná-lo à contagem de erros ou registrá-lo em log na tela ou no arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="1d788-141">By ignoring the error, you simply allow processing to continue without adding to the error count or logging it to the screen or log file.</span></span> <span data-ttu-id="1d788-142">O registro em questão tem um problema de integridade de dados e não pode ser adicionado ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1d788-142">The record in question has a data integrity problem and cannot be added to the database.</span></span> <span data-ttu-id="1d788-143">O registro será descartado ou agregado ao Membro desconhecido, conforme determinado pela propriedade `KeyErrorAction`.</span><span class="sxs-lookup"><span data-stu-id="1d788-143">The record will either be discarded or aggregated to Unknown Member, as determined by the `KeyErrorAction` property.</span></span>  
  
-   <span data-ttu-id="1d788-144">`ReportAndContinue` informa ao servidor para registrar em log o erro, contá-lo até o limite de erros de chave e continuar o processamento.</span><span class="sxs-lookup"><span data-stu-id="1d788-144">`ReportAndContinue` tells the server to log the error, count it towards the key error limit, and continue processing.</span></span> <span data-ttu-id="1d788-145">O registro que aciona o erro é descartado ou convertido no Membro Desconhecido.</span><span class="sxs-lookup"><span data-stu-id="1d788-145">The record triggering the error is discarded or converted to Unknown Member.</span></span>  
  
-   <span data-ttu-id="1d788-146">`ReportAndStop` informa ao servidor para registrar em log o erro e parar o processamento imediatamente, independentemente do limite de erros de chave.</span><span class="sxs-lookup"><span data-stu-id="1d788-146">`ReportAndStop` tells the server to log the error and stop processing immediately, regardless of the key error limit.</span></span> <span data-ttu-id="1d788-147">O registro que aciona o erro é descartado ou convertido no Membro Desconhecido.</span><span class="sxs-lookup"><span data-stu-id="1d788-147">The record triggering the error is discarded or converted to Unknown Member.</span></span>  
  
 <span data-ttu-id="1d788-148">**ErrorLog\ LogErrorTypes\KeyDuplicate**</span><span class="sxs-lookup"><span data-stu-id="1d788-148">**ErrorLog\ LogErrorTypes\KeyDuplicate**</span></span>  
 <span data-ttu-id="1d788-149">Especifica a ação executada pelo servidor quando uma chave duplicada é encontrada.</span><span class="sxs-lookup"><span data-stu-id="1d788-149">Specifies the action taken by the server when a duplicate key is found.</span></span> <span data-ttu-id="1d788-150">Os valores válidos incluem `IgnoreError` para continuar o processamento como se o erro não tivesse ocorrido, `ReportAndContinue` para registrar em log o erro e continuar o processamento, e `ReportAndStop` para registrar em log o erro e parar o processamento imediatamente, mesmo se a contagem de erro estiver abaixo do limite de erros.</span><span class="sxs-lookup"><span data-stu-id="1d788-150">Valid values include `IgnoreError` to continue processing as if the error did not occur, `ReportAndContinue` to log the error and continue processing, and `ReportAndStop` to log the error and stop processing immediately, even if the error count is below the error limit.</span></span>  
  
 <span data-ttu-id="1d788-151">**ErrorLog\ LogErrorTypes\NullKeyConvertedToUnknown**</span><span class="sxs-lookup"><span data-stu-id="1d788-151">**ErrorLog\ LogErrorTypes\NullKeyConvertedToUnknown**</span></span>  
 <span data-ttu-id="1d788-152">Especifica a ação executada pelo servidor quando uma chave nula tiver sido convertida em Membro Desconhecido.</span><span class="sxs-lookup"><span data-stu-id="1d788-152">Specifies the action taken by the server when a null key has been converted to Unknown Member.</span></span> <span data-ttu-id="1d788-153">Os valores válidos incluem `IgnoreError` para continuar o processamento como se o erro não tivesse ocorrido, `ReportAndContinue` para registrar em log o erro e continuar o processamento, e `ReportAndStop` para registrar em log o erro e parar o processamento imediatamente, mesmo se a contagem de erro estiver abaixo do limite de erros.</span><span class="sxs-lookup"><span data-stu-id="1d788-153">Valid values include `IgnoreError` to continue processing as if the error did not occur, `ReportAndContinue` to log the error and continue processing, and `ReportAndStop` to log the error and stop processing immediately, even if the error count is below the error limit.</span></span>  
  
 <span data-ttu-id="1d788-154">**ErrorLog\ LogErrorTypes\NullKeyNotAllowed**</span><span class="sxs-lookup"><span data-stu-id="1d788-154">**ErrorLog\ LogErrorTypes\NullKeyNotAllowed**</span></span>  
 <span data-ttu-id="1d788-155">Especifica a ação executada pelo servidor quando `NullProcessing` estiver definido como `Error` para um atributo de dimensão.</span><span class="sxs-lookup"><span data-stu-id="1d788-155">Specifies the action taken by the server when `NullProcessing` is set to `Error` for a dimension attribute.</span></span> <span data-ttu-id="1d788-156">Um erro é gerado quando um valor nulo não é permitido em um determinado atributo.</span><span class="sxs-lookup"><span data-stu-id="1d788-156">An error is generated when a null value is not allowed in a given attribute.</span></span> <span data-ttu-id="1d788-157">Esta propriedade de configuração de erro informa a próxima etapa, que é relatar o erro e continuar o processamento até que o limite de erros seja atingido.</span><span class="sxs-lookup"><span data-stu-id="1d788-157">This error configuration property informs the next step, which is to report the error and continue processing until the error limit is reached.</span></span> <span data-ttu-id="1d788-158">Os valores válidos incluem `IgnoreError` para continuar o processamento como se o erro não tivesse ocorrido, `ReportAndContinue` para registrar em log o erro e continuar o processamento, e `ReportAndStop` para registrar em log o erro e parar o processamento imediatamente, mesmo se a contagem de erro estiver abaixo do limite de erros.</span><span class="sxs-lookup"><span data-stu-id="1d788-158">Valid values include `IgnoreError` to continue processing as if the error did not occur, `ReportAndContinue` to log the error and continue processing, and `ReportAndStop` to log the error and stop processing immediately, even if the error count is below the error limit.</span></span>  
  
 <span data-ttu-id="1d788-159">**ErrorLog\ LogErrorTypes\CalculationError**</span><span class="sxs-lookup"><span data-stu-id="1d788-159">**ErrorLog\ LogErrorTypes\CalculationError**</span></span>  
 <span data-ttu-id="1d788-160">Uma propriedade usada como padrão durante a operação de processamento executada pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="1d788-160">A property used as a default during processing operation performed by the server.</span></span>  
  
 <span data-ttu-id="1d788-161">**ErrorLog\IgnoreDataTruncation**</span><span class="sxs-lookup"><span data-stu-id="1d788-161">**ErrorLog\IgnoreDataTruncation**</span></span>  
 <span data-ttu-id="1d788-162">Uma propriedade usada como padrão durante a operação de processamento executada pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="1d788-162">A property used as a default during processing operation performed by the server.</span></span>  
  
## <a name="exception"></a><span data-ttu-id="1d788-163">Exceção</span><span class="sxs-lookup"><span data-stu-id="1d788-163">Exception</span></span>  
 <span data-ttu-id="1d788-164">**Exception\CreateAndSendCrashReports**</span><span class="sxs-lookup"><span data-stu-id="1d788-164">**Exception\CreateAndSendCrashReports**</span></span>  
 <span data-ttu-id="1d788-165">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d788-165">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1d788-166">**Exception\CrashReportsFolder**</span><span class="sxs-lookup"><span data-stu-id="1d788-166">**Exception\CrashReportsFolder**</span></span>  
 <span data-ttu-id="1d788-167">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d788-167">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1d788-168">**Exception\SQLDumperFlagsOn**</span><span class="sxs-lookup"><span data-stu-id="1d788-168">**Exception\SQLDumperFlagsOn**</span></span>  
 <span data-ttu-id="1d788-169">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d788-169">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1d788-170">**Exception\SQLDumperFlagsOff**</span><span class="sxs-lookup"><span data-stu-id="1d788-170">**Exception\SQLDumperFlagsOff**</span></span>  
 <span data-ttu-id="1d788-171">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d788-171">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1d788-172">**Exception\MiniDumpFlagsOn**</span><span class="sxs-lookup"><span data-stu-id="1d788-172">**Exception\MiniDumpFlagsOn**</span></span>  
 <span data-ttu-id="1d788-173">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d788-173">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1d788-174">**Exception\MinidumpErrorList**</span><span class="sxs-lookup"><span data-stu-id="1d788-174">**Exception\MinidumpErrorList**</span></span>  
 <span data-ttu-id="1d788-175">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d788-175">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="flight-recorder"></a><span data-ttu-id="1d788-176">Flight Recorder</span><span class="sxs-lookup"><span data-stu-id="1d788-176">Flight Recorder</span></span>  
 <span data-ttu-id="1d788-177">**FlightRecorder\Enabled**</span><span class="sxs-lookup"><span data-stu-id="1d788-177">**FlightRecorder\Enabled**</span></span>  
 <span data-ttu-id="1d788-178">Uma propriedade booliana que indica se o recurso de flight recorder está habilitado.</span><span class="sxs-lookup"><span data-stu-id="1d788-178">A Boolean property that indicates whether the flight recorder feature is enabled.</span></span>  
  
 <span data-ttu-id="1d788-179">**FlightRecorder\FileSizeMB**</span><span class="sxs-lookup"><span data-stu-id="1d788-179">**FlightRecorder\FileSizeMB**</span></span>  
 <span data-ttu-id="1d788-180">Uma propriedade de inteiro de 32 bits assinada que define o tamanho do arquivo de disco do flight recorder, em megabytes.</span><span class="sxs-lookup"><span data-stu-id="1d788-180">A signed 32-bit integer property that defines the size of the flight recorder disk file, in megabytes.</span></span>  
  
 <span data-ttu-id="1d788-181">**FlightRecorder\LogDurationSec**</span><span class="sxs-lookup"><span data-stu-id="1d788-181">**FlightRecorder\LogDurationSec**</span></span>  
 <span data-ttu-id="1d788-182">Uma propriedade de inteiro de 32 bits assinada que define a frequência com que o flight recorder é rodado, em segundos.</span><span class="sxs-lookup"><span data-stu-id="1d788-182">A signed 32-bit integer property that defines the frequency that the flight recorder is rolled over, in seconds.</span></span>  
  
 <span data-ttu-id="1d788-183">**FlightRecorder\SnapshotDefinitionFile**</span><span class="sxs-lookup"><span data-stu-id="1d788-183">**FlightRecorder\SnapshotDefinitionFile**</span></span>  
 <span data-ttu-id="1d788-184">Uma propriedade de cadeia de caracteres que define o nome do arquivo de definição de instantâneo, que contém comandos de identificação emitidos ao servidor quando um instantâneo é tirado.</span><span class="sxs-lookup"><span data-stu-id="1d788-184">A string property that defines the name of the snapshot definition file, containing discover commands that are issued to the server when a snapshot is taken.</span></span>  
  
 <span data-ttu-id="1d788-185">O valor padrão desta propriedade é em branco, que por sua vez, assume o nome de arquivo FlightRecorderSnapshotDef.xml como padrão.</span><span class="sxs-lookup"><span data-stu-id="1d788-185">The default value for this property is blank, which in turn defaults to file name FlightRecorderSnapshotDef.xml.</span></span>  
  
 <span data-ttu-id="1d788-186">**FlightRecorder\SnapshotFrequencySec**</span><span class="sxs-lookup"><span data-stu-id="1d788-186">**FlightRecorder\SnapshotFrequencySec**</span></span>  
 <span data-ttu-id="1d788-187">Uma propriedade de inteiro de 32 bits assinada que define a frequência de instantâneo, em segundos.</span><span class="sxs-lookup"><span data-stu-id="1d788-187">A signed 32-bit integer property that defines the snapshot frequency, in seconds.</span></span>  
  
 <span data-ttu-id="1d788-188">**FlightRecorder\TraceDefinitionFile**</span><span class="sxs-lookup"><span data-stu-id="1d788-188">**FlightRecorder\TraceDefinitionFile**</span></span>  
 <span data-ttu-id="1d788-189">Uma propriedade de cadeia de caracteres que especifica o nome do arquivo de definição de rastreamento do flight recorder.</span><span class="sxs-lookup"><span data-stu-id="1d788-189">A string property that specifies the name of the flight recorder trace definition file.</span></span>  
  
 <span data-ttu-id="1d788-190">O valor padrão desta propriedade é em branco, que por sua vez, assume FlightRecorderTraceDef.xml como padrão.</span><span class="sxs-lookup"><span data-stu-id="1d788-190">The default value for this property is blank, which in turn defaults to FlightRecorderTraceDef.xml.</span></span>  
  
## <a name="query-log"></a><span data-ttu-id="1d788-191">Log de consultas</span><span class="sxs-lookup"><span data-stu-id="1d788-191">Query Log</span></span>  
 <span data-ttu-id="1d788-192">**Aplica-se a:** Somente modo de servidor multidimensional</span><span class="sxs-lookup"><span data-stu-id="1d788-192">**Applies to:** Multidimensional server mode only</span></span>  
  
 <span data-ttu-id="1d788-193">**QueryLog\QueryLogFileName**</span><span class="sxs-lookup"><span data-stu-id="1d788-193">**QueryLog\QueryLogFileName**</span></span>  
 <span data-ttu-id="1d788-194">Uma propriedade de cadeia de caracteres que especifica o nome do arquivo de log de consultas.</span><span class="sxs-lookup"><span data-stu-id="1d788-194">A string property that specifies the name of the query log file.</span></span> <span data-ttu-id="1d788-195">Esta propriedade só se aplicará quando um arquivo de disco for usado para log, em vez de uma tabela de banco de dados (o comportamento padrão).</span><span class="sxs-lookup"><span data-stu-id="1d788-195">This property only applies when a disk file is used for logging, as opposed to a database table (the default behavior).</span></span>  
  
 <span data-ttu-id="1d788-196">**QueryLog\QueryLogSampling**</span><span class="sxs-lookup"><span data-stu-id="1d788-196">**QueryLog\QueryLogSampling**</span></span>  
 <span data-ttu-id="1d788-197">Uma propriedade de inteiro de 32 bits assinada que especifica a taxa de amostragem do log de consultas.</span><span class="sxs-lookup"><span data-stu-id="1d788-197">A signed 32-bit integer property that specifies the query log sampling rate.</span></span>  
  
 <span data-ttu-id="1d788-198">O valor padrão desta propriedade é 10, o que significa que 1 entre cada 10 consultas de servidor é registrada.</span><span class="sxs-lookup"><span data-stu-id="1d788-198">The default value for this property is 10, meaning that 1 out of every 10 server queries is logged.</span></span>  
  
 <span data-ttu-id="1d788-199">**QueryLog\QueryLogFileSize**</span><span class="sxs-lookup"><span data-stu-id="1d788-199">**QueryLog\QueryLogFileSize**</span></span>  
 <span data-ttu-id="1d788-200">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d788-200">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1d788-201">**QueryLog\QueryLogConnectionString**</span><span class="sxs-lookup"><span data-stu-id="1d788-201">**QueryLog\QueryLogConnectionString**</span></span>  
 <span data-ttu-id="1d788-202">Uma propriedade de cadeia de caracteres que especifica a conexão com o banco de dados de log de consultas.</span><span class="sxs-lookup"><span data-stu-id="1d788-202">A string property that specifies the connection to the query log database.</span></span>  
  
 <span data-ttu-id="1d788-203">**QueryLog\QueryLogTableName**</span><span class="sxs-lookup"><span data-stu-id="1d788-203">**QueryLog\QueryLogTableName**</span></span>  
 <span data-ttu-id="1d788-204">Uma propriedade de cadeia de caracteres que especifica o nome da tabela de log de consultas.</span><span class="sxs-lookup"><span data-stu-id="1d788-204">A string property that specifies the name of the query log table.</span></span>  
  
 <span data-ttu-id="1d788-205">O valor padrão desta propriedade é OlapQueryLog.</span><span class="sxs-lookup"><span data-stu-id="1d788-205">The default value for this property is OlapQueryLog.</span></span>  
  
 <span data-ttu-id="1d788-206">**QueryLog\CreateQueryLogTable**</span><span class="sxs-lookup"><span data-stu-id="1d788-206">**QueryLog\CreateQueryLogTable**</span></span>  
 <span data-ttu-id="1d788-207">Uma propriedade booliana que especifica se deve ser criada a tabela de log de consultas.</span><span class="sxs-lookup"><span data-stu-id="1d788-207">A Boolean property that specifies whether to create the query log table.</span></span>  
  
 <span data-ttu-id="1d788-208">O valor padrão desta propriedade é falso, o que indica que o servidor não criará a tabela de log automaticamente e não registrará os eventos de consulta.</span><span class="sxs-lookup"><span data-stu-id="1d788-208">The default value for this property is false, which indicates the server will not automatically create the log table and will not log query events.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1d788-209">Para obter mais informações sobre como configurar o log de consultas, consulte [operações de log no Analysis Services](../instances/log-operations-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="1d788-209">For more information about configuring the query log, see [Log operations in Analysis Services](../instances/log-operations-in-analysis-services.md).</span></span>  
  
## <a name="trace"></a><span data-ttu-id="1d788-210">Trace</span><span class="sxs-lookup"><span data-stu-id="1d788-210">Trace</span></span>  
 <span data-ttu-id="1d788-211">**Trace\TraceBackgroundDistributionPeriod**</span><span class="sxs-lookup"><span data-stu-id="1d788-211">**Trace\TraceBackgroundDistributionPeriod**</span></span>  
 <span data-ttu-id="1d788-212">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d788-212">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1d788-213">**Trace\TraceBackgroundFlushPeriod**</span><span class="sxs-lookup"><span data-stu-id="1d788-213">**Trace\TraceBackgroundFlushPeriod**</span></span>  
 <span data-ttu-id="1d788-214">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d788-214">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1d788-215">**Trace\TraceFileBufferSize**</span><span class="sxs-lookup"><span data-stu-id="1d788-215">**Trace\TraceFileBufferSize**</span></span>  
 <span data-ttu-id="1d788-216">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d788-216">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1d788-217">**Trace\TraceFileWriteTrailerPeriod**</span><span class="sxs-lookup"><span data-stu-id="1d788-217">**Trace\TraceFileWriteTrailerPeriod**</span></span>  
 <span data-ttu-id="1d788-218">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d788-218">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1d788-219">**Trace\TraceMaxRowsetSize**</span><span class="sxs-lookup"><span data-stu-id="1d788-219">**Trace\TraceMaxRowsetSize**</span></span>  
 <span data-ttu-id="1d788-220">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d788-220">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1d788-221">**Trace\TraceProtocolTraffic**</span><span class="sxs-lookup"><span data-stu-id="1d788-221">**Trace\TraceProtocolTraffic**</span></span>  
 <span data-ttu-id="1d788-222">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d788-222">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1d788-223">**Trace\TraceQueryResponseTextChunkSize**</span><span class="sxs-lookup"><span data-stu-id="1d788-223">**Trace\TraceQueryResponseTextChunkSize**</span></span>  
 <span data-ttu-id="1d788-224">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d788-224">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1d788-225">**Trace\TraceReportFQDN**</span><span class="sxs-lookup"><span data-stu-id="1d788-225">**Trace\TraceReportFQDN**</span></span>  
 <span data-ttu-id="1d788-226">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d788-226">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1d788-227">**Trace\TraceRequestParameters**</span><span class="sxs-lookup"><span data-stu-id="1d788-227">**Trace\TraceRequestParameters**</span></span>  
 <span data-ttu-id="1d788-228">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d788-228">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="1d788-229">**Trace\TraceRowsetBackgroundFlushPeriod**</span><span class="sxs-lookup"><span data-stu-id="1d788-229">**Trace\TraceRowsetBackgroundFlushPeriod**</span></span>  
 <span data-ttu-id="1d788-230">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d788-230">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d788-231">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1d788-231">See Also</span></span>  
 <span data-ttu-id="1d788-232">[Configurar propriedades do servidor no Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="1d788-232">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="1d788-233">Determina o Modo de Servidor de uma instância do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="1d788-233">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
