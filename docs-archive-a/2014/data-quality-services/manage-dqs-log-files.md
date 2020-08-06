---
title: Gerenciar arquivos de log do DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
helpviewer_keywords:
- logging
- log files
- dqs log files
ms.assetid: 4fccfd24-aede-4882-be69-ec1e82682e16
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ca85772b8cc8aca41b75ad05d028bc444f280378
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582629"
---
# <a name="manage-dqs-log-files"></a><span data-ttu-id="cbbd7-102">Gerenciar arquivos de log do DQS</span><span class="sxs-lookup"><span data-stu-id="cbbd7-102">Manage DQS Log Files</span></span>
  <span data-ttu-id="cbbd7-103">Arquivos de log do[!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) o ajudam a diagnosticar e solucionar problemas no [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]e no [!INCLUDE[ssDQSCleansingLong](../includes/ssdqscleansinglong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbbd7-103">[!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) log files help you in diagnosing and troubleshooting issue with [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], and the [!INCLUDE[ssDQSCleansingLong](../includes/ssdqscleansinglong-md.md)].</span></span> <span data-ttu-id="cbbd7-104">São gerados arquivos de log separados para o [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], o [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]e o [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbbd7-104">Separate log files are generated for [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], and the [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)].</span></span>  
  
 <span data-ttu-id="cbbd7-105">Você pode usar o [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] para definir a configuração de severidade de log para recursos e módulos do [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cbbd7-105">You can use [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] to configure the log severity setting for [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] features and modules.</span></span> <span data-ttu-id="cbbd7-106">Adicionalmente, você também pode definir outras configurações (avançadas) para os arquivos de log do DQS, alterando manualmente os parâmetros de configuração de log DQS no banco de dados DQS_MAIN e um arquivo XML no computador [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cbbd7-106">Additionally, you can also configure some other (advanced) settings for the DQS log files by manually changing the DQS log configuration settings in the DQS_MAIN database and an XML file on the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] computer.</span></span>  
  
##  <a name="data-quality-server-log-file"></a><a name="DQSServer"></a><span data-ttu-id="cbbd7-107">Arquivo de log do Data Quality Server</span><span class="sxs-lookup"><span data-stu-id="cbbd7-107">Data Quality Server Log File</span></span>  
 <span data-ttu-id="cbbd7-108">O arquivo de log [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] , DQServerLog.DQS_MAIN.log, inclui logs de atividades que são executadas no [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbbd7-108">The [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log file, DQServerLog.DQS_MAIN.log, includes logs of activities that are run on [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span> <span data-ttu-id="cbbd7-109">Se você tiver instalado a instância padrão do SQL Server, o arquivo DQServerLog.DQS_MAIN.log estará disponível em C:\Arquivos de Programas\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log.</span><span class="sxs-lookup"><span data-stu-id="cbbd7-109">If you installed the default instance of SQL Server, the DQServerLog.DQS_MAIN.log file is available at C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log.</span></span> <span data-ttu-id="cbbd7-110">O arquivo de log [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] contém as seguintes informações, delimitadas por uma barra (|):</span><span class="sxs-lookup"><span data-stu-id="cbbd7-110">The [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log file contains the following pieces of information, each delimited by a pipe (|):</span></span>  
  
-   <span data-ttu-id="cbbd7-111">Data e hora</span><span class="sxs-lookup"><span data-stu-id="cbbd7-111">Date and time</span></span>  
  
-   <span data-ttu-id="cbbd7-112">Nome do thread</span><span class="sxs-lookup"><span data-stu-id="cbbd7-112">Thread name</span></span>  
  
-   <span data-ttu-id="cbbd7-113">ID do thread</span><span class="sxs-lookup"><span data-stu-id="cbbd7-113">Thread ID</span></span>  
  
-   <span data-ttu-id="cbbd7-114">Severidade do log (FATAL, ERROR, WARN, INFO e DEBUG)</span><span class="sxs-lookup"><span data-stu-id="cbbd7-114">Log severity (FATAL, ERROR, WARN, INFO, and DEBUG)</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cbbd7-115">A severidade de log DEBUG equivale a Detalhado.</span><span class="sxs-lookup"><span data-stu-id="cbbd7-115">The DEBUG logging severity is same as Verbose.</span></span>  
  
-   <span data-ttu-id="cbbd7-116">UID (ID de infraestrutura de DQS interna)</span><span class="sxs-lookup"><span data-stu-id="cbbd7-116">UID (internal DQS infrastructure ID)</span></span>  
  
-   <span data-ttu-id="cbbd7-117">Namespace</span><span class="sxs-lookup"><span data-stu-id="cbbd7-117">Namespace</span></span>  
  
-   <span data-ttu-id="cbbd7-118">Classe e método</span><span class="sxs-lookup"><span data-stu-id="cbbd7-118">Class and method</span></span>  
  
-   <span data-ttu-id="cbbd7-119">Mensagem</span><span class="sxs-lookup"><span data-stu-id="cbbd7-119">Message</span></span>  
  
 <span data-ttu-id="cbbd7-120">Além disso, o arquivo de log exibe também informações sobre a versão do aplicativo, o nome de computador, o nome do usuário e o sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="cbbd7-120">Along with these, the log file also displays information about the application version, computer name, user name, and operating system.</span></span>  
  
 <span data-ttu-id="cbbd7-121">Uma entrada de exemplo no arquivo de log [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="cbbd7-121">A sample entry in the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log file looks like the following:</span></span>  
  
```  
23-08-2013 01:45:29|[]|4|INFO|PUID|InfInfoModuleStarting|Microsoft.Ssdqs.Core.Startup.ServerInit|Starting DQS ServerInit: version [12.0.0.0], machine name [DQS-TEST], user name [NT Service\MSSQLSERVER], operating system [Microsoft Windows NT 6.1.7600.0]...  
```  
  
 <span data-ttu-id="cbbd7-122">O arquivo DQServerLog.DQS_MAIN.log é um arquivo rolante; um novo arquivo de log é criado quando o arquivo de log existente excede o limite de tamanho do arquivo rolante especificado nos parâmetros de configuração de log do [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cbbd7-122">The DQServerLog.DQS_MAIN.log file is a rolling file, and a new log file is created once the existing log file exceeds the rolling file size limit specified in the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log configuration settings.</span></span> <span data-ttu-id="cbbd7-123">Para obter mais informações, consulte [Configure Advanced Settings for DQS Log Files](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="cbbd7-123">For more information, see [Configure Advanced Settings for DQS Log Files](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md).</span></span>  
  
##  <a name="data-quality-client-log-file"></a><a name="DQSClient"></a><span data-ttu-id="cbbd7-124">Data Quality Client arquivo de log</span><span class="sxs-lookup"><span data-stu-id="cbbd7-124">Data Quality Client Log File</span></span>  
 <span data-ttu-id="cbbd7-125">O arquivo de log [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , DQClientLog.log, inclui logs do lado do cliente.</span><span class="sxs-lookup"><span data-stu-id="cbbd7-125">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log file, DQClientLog.log, includes the client side logs.</span></span> <span data-ttu-id="cbbd7-126">O arquivo de log [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] está disponível em %APPDATA%\SSDQS\Log.</span><span class="sxs-lookup"><span data-stu-id="cbbd7-126">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log file is available at %APPDATA%\SSDQS\Log.</span></span> <span data-ttu-id="cbbd7-127">O arquivo de log [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] contém um conjunto de informações semelhante ao do arquivo de log de servidor, mas para o lado do cliente.</span><span class="sxs-lookup"><span data-stu-id="cbbd7-127">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log file contains similar set of information as in the server log file, but for the client side.</span></span>  
  
 <span data-ttu-id="cbbd7-128">Assim como no arquivo de log [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] , o arquivo de log [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] também é um arquivo rolante; um novo arquivo de log é criado quando o arquivo de log existente excede o limite de tamanho do arquivo rolante especificado nos parâmetros de configuração de log do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cbbd7-128">As with the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log file, the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log file is also a rolling file, and a new log file is created once the existing log file exceeds the rolling file size limit specified in the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log configuration settings.</span></span> <span data-ttu-id="cbbd7-129">Para obter mais informações, consulte [Configure Advanced Settings for DQS Log Files](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="cbbd7-129">For more information, see [Configure Advanced Settings for DQS Log Files](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md).</span></span>  
  
##  <a name="dqs-cleansing-component-log-file"></a><a name="DQSCleansing"></a><span data-ttu-id="cbbd7-130">Arquivo de log do componente de limpeza DQS</span><span class="sxs-lookup"><span data-stu-id="cbbd7-130">DQS Cleansing Component Log File</span></span>  
 <span data-ttu-id="cbbd7-131">O arquivo de log [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] , DQSSSISLog.log, inclui logs de atividades executados usando o [!INCLUDE[ssDQSCleansingLong](../includes/ssdqscleansinglong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbbd7-131">The [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] log file, DQSSSISLog.log, includes logs of activities performed using the [!INCLUDE[ssDQSCleansingLong](../includes/ssdqscleansinglong-md.md)].</span></span> <span data-ttu-id="cbbd7-132">O arquivo de log de componente [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] está disponível em %APPDATA%\SSDQS\Log.</span><span class="sxs-lookup"><span data-stu-id="cbbd7-132">The [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] component log file is available at %APPDATA%\SSDQS\Log.</span></span> <span data-ttu-id="cbbd7-133">O arquivo de log [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] contém um conjunto de informações semelhante ao do arquivo de log de servidor, mas para o [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbbd7-133">The [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] log file contains similar set of information as in the server log file, but for the [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)].</span></span>  
  
##  <a name="related-tasks"></a><a name="RT"></a> <span data-ttu-id="cbbd7-134">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="cbbd7-134">Related Tasks</span></span>  
  
|<span data-ttu-id="cbbd7-135">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="cbbd7-135">Task Description</span></span>|<span data-ttu-id="cbbd7-136">Tópico</span><span class="sxs-lookup"><span data-stu-id="cbbd7-136">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="cbbd7-137">Descreve como definir configurações de severidade de log para arquivos de log DQS usando o [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbbd7-137">Describes how to configure log severity settings for DQS log files using [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span></span>|[<span data-ttu-id="cbbd7-138">Configurar níveis de severidade para arquivos de log do DQS</span><span class="sxs-lookup"><span data-stu-id="cbbd7-138">Configure Severity Levels for DQS Log Files</span></span>](../../2014/data-quality-services/configure-severity-levels-for-dqs-log-files.md)|  
|<span data-ttu-id="cbbd7-139">Descreve como definir manualmente configurações avançadas para arquivos de log DQS.</span><span class="sxs-lookup"><span data-stu-id="cbbd7-139">Describes how to manually configure advanced settings for DQS log files.</span></span>|[<span data-ttu-id="cbbd7-140">Definir configurações avançadas para arquivos de log do DQS</span><span class="sxs-lookup"><span data-stu-id="cbbd7-140">Configure Advanced Settings for DQS Log Files</span></span>](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md)|  
  
## <a name="see-also"></a><span data-ttu-id="cbbd7-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cbbd7-141">See Also</span></span>  
 [<span data-ttu-id="cbbd7-142">administração do dqs</span><span class="sxs-lookup"><span data-stu-id="cbbd7-142">DQS Administration</span></span>](../../2014/data-quality-services/dqs-administration.md)  
  
  
