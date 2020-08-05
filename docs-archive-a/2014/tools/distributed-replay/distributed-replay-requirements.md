---
title: Requisitos de Distributed Replay | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 6fffee7d-891f-4d9d-b2c3-dd19855a1c2c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 66be93534756360e722fcccaf405815e14ffa7ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573328"
---
# <a name="distributed-replay-requirements"></a><span data-ttu-id="19edf-102">Distributed Replay Requirements</span><span class="sxs-lookup"><span data-stu-id="19edf-102">Distributed Replay Requirements</span></span>
  <span data-ttu-id="19edf-103">Antes de usar o recurso Distributed Replay do [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , considere os requisitos de produto destacados neste tópico.</span><span class="sxs-lookup"><span data-stu-id="19edf-103">Before using the [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay feature, consider the product requirements that are outlined in this topic.</span></span>  
  
## <a name="input-trace-requirements"></a><span data-ttu-id="19edf-104">Requisitos de rastreamento de entrada</span><span class="sxs-lookup"><span data-stu-id="19edf-104">Input Trace Requirements</span></span>  
 <span data-ttu-id="19edf-105">Para repetir dados de rastreamento com êxito, ele deve atender os requisitos de versão e formato e conter os eventos e as colunas necessárias.</span><span class="sxs-lookup"><span data-stu-id="19edf-105">To successfully replay trace data, it must meet the requirements for version and format, and contain the required events and columns.</span></span>  
  
### <a name="input-trace-versions"></a><span data-ttu-id="19edf-106">Versões de rastreamento de entrada</span><span class="sxs-lookup"><span data-stu-id="19edf-106">Input Trace Versions</span></span>  
 <span data-ttu-id="19edf-107">O Distributed Replay oferece suporte a dados de rastreamento de entrada que são coletados nas seguintes versões do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="19edf-107">Distributed Replay supports input trace data that is collected on the following versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]  
  
-   [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]  
  
-   [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]  
  
-   [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]  
  
-   [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]  
  
### <a name="input-trace-formats"></a><span data-ttu-id="19edf-108">Formatos de rastreamento de entrada</span><span class="sxs-lookup"><span data-stu-id="19edf-108">Input Trace Formats</span></span>  
 <span data-ttu-id="19edf-109">Os dados de rastreamento de entrada podem estar em qualquer um dos seguintes formatos:</span><span class="sxs-lookup"><span data-stu-id="19edf-109">The input trace data can be in any of the following formats:</span></span>  
  
-   <span data-ttu-id="19edf-110">Um único arquivo de rastreamento que tem a extensão `.trc` .</span><span class="sxs-lookup"><span data-stu-id="19edf-110">A single trace file that has the `.trc` extension.</span></span>  
  
-   <span data-ttu-id="19edf-111">Um conjunto de arquivos de rastreamento de substituição que siga a convenção de nomenclatura de substituição de arquivo, por exemplo: `<TraceFile>.trc`, `<TraceFile>_1.trc`, `<TraceFile>_2.trc`, `<TraceFile>_3.trc`, ... `<TraceFile>_n.trc`.</span><span class="sxs-lookup"><span data-stu-id="19edf-111">A set of rollover trace files that follow the file rollover naming convention, for example: `<TraceFile>.trc`, `<TraceFile>_1.trc`, `<TraceFile>_2.trc`, `<TraceFile>_3.trc`, ... `<TraceFile>_n.trc`.</span></span>  
  
### <a name="input-trace-events-and-columns"></a><span data-ttu-id="19edf-112">Eventos e colunas de rastreamento de entrada</span><span class="sxs-lookup"><span data-stu-id="19edf-112">Input Trace Events and Columns</span></span>  
 <span data-ttu-id="19edf-113">Os dados de rastreamento de entrada devem conter eventos e colunas específicos a serem reproduzidos pelo Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="19edf-113">The input trace data must contain specific events and columns to be replayed by Distributed Replay.</span></span> <span data-ttu-id="19edf-114">O modelo **TSQL_Replay** no [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] contém todas as colunas e eventos necessários, além de informações extras.</span><span class="sxs-lookup"><span data-stu-id="19edf-114">The **TSQL_Replay** template in [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] contains all of the required events and columns, in addition to extra information.</span></span> <span data-ttu-id="19edf-115">Para obter mais informações sobre esse modelo, consulte [Replay Requirements](../sql-server-profiler/replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19edf-115">For more information about that template, see [Replay Requirements](../sql-server-profiler/replay-requirements.md).</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="19edf-116">Se você não usar o modelo **TSQL_Replay** para capturar os dados de rastreamento de entrada, ou se os requisitos de rastreamento de entrada não forem atendidos, talvez você receba resultados de reprodução inesperados.</span><span class="sxs-lookup"><span data-stu-id="19edf-116">If you do not use the **TSQL_Replay** template to capture the input trace data, or if the input trace requirements are not satisfied, you may receive unexpected replay results.</span></span>  
  
 <span data-ttu-id="19edf-117">Também é possível criar um modelo de rastreamento personalizado e usá-lo para reproduzir eventos com o Distributed Replay, desde que ele contenha os seguintes eventos:</span><span class="sxs-lookup"><span data-stu-id="19edf-117">You can also create a custom trace template and use it to replay events with Distributed Replay, as long as it contains the following events:</span></span>  
  
-   <span data-ttu-id="19edf-118">Auditar logon</span><span class="sxs-lookup"><span data-stu-id="19edf-118">Audit Login</span></span>  
  
-   <span data-ttu-id="19edf-119">Auditar logoff</span><span class="sxs-lookup"><span data-stu-id="19edf-119">Audit Logout</span></span>  
  
-   <span data-ttu-id="19edf-120">ExistingConnection</span><span class="sxs-lookup"><span data-stu-id="19edf-120">ExistingConnection</span></span>  
  
-   <span data-ttu-id="19edf-121">RPC Output Parameter</span><span class="sxs-lookup"><span data-stu-id="19edf-121">RPC Output Parameter</span></span>  
  
-   <span data-ttu-id="19edf-122">RPC:Completed</span><span class="sxs-lookup"><span data-stu-id="19edf-122">RPC:Completed</span></span>  
  
-   <span data-ttu-id="19edf-123">RPC:Starting</span><span class="sxs-lookup"><span data-stu-id="19edf-123">RPC:Starting</span></span>  
  
-   <span data-ttu-id="19edf-124">SQL:BatchCompleted</span><span class="sxs-lookup"><span data-stu-id="19edf-124">SQL:BatchCompleted</span></span>  
  
-   <span data-ttu-id="19edf-125">SQL:BatchStarting</span><span class="sxs-lookup"><span data-stu-id="19edf-125">SQL:BatchStarting</span></span>  
  
 <span data-ttu-id="19edf-126">Se você estiver repetindo cursores de servidor, os seguintes eventos também são necessários:</span><span class="sxs-lookup"><span data-stu-id="19edf-126">If you are replaying server-side cursors, the following events are also required:</span></span>  
  
-   <span data-ttu-id="19edf-127">CursorClose</span><span class="sxs-lookup"><span data-stu-id="19edf-127">CursorClose</span></span>  
  
-   <span data-ttu-id="19edf-128">CursorExecute</span><span class="sxs-lookup"><span data-stu-id="19edf-128">CursorExecute</span></span>  
  
-   <span data-ttu-id="19edf-129">CursorOpen</span><span class="sxs-lookup"><span data-stu-id="19edf-129">CursorOpen</span></span>  
  
-   <span data-ttu-id="19edf-130">CursorPrepare</span><span class="sxs-lookup"><span data-stu-id="19edf-130">CursorPrepare</span></span>  
  
-   <span data-ttu-id="19edf-131">CursorUnprepare</span><span class="sxs-lookup"><span data-stu-id="19edf-131">CursorUnprepare</span></span>  
  
 <span data-ttu-id="19edf-132">Se você estiver repetindo instruções SQL preparadas de servidor, os seguintes eventos também são necessários:</span><span class="sxs-lookup"><span data-stu-id="19edf-132">If you are replaying server-side prepared SQL statements, the following events are also required:</span></span>  
  
-   <span data-ttu-id="19edf-133">Exec Prepared SQL</span><span class="sxs-lookup"><span data-stu-id="19edf-133">Exec Prepared SQL</span></span>  
  
-   <span data-ttu-id="19edf-134">Prepare SQL</span><span class="sxs-lookup"><span data-stu-id="19edf-134">Prepare SQL</span></span>  
  
 <span data-ttu-id="19edf-135">Todos os dados de rastreamento de entrada devem conter as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="19edf-135">All input trace data must contain the following columns:</span></span>  
  
-   <span data-ttu-id="19edf-136">Event Class</span><span class="sxs-lookup"><span data-stu-id="19edf-136">Event Class</span></span>  
  
-   <span data-ttu-id="19edf-137">EventSequence</span><span class="sxs-lookup"><span data-stu-id="19edf-137">EventSequence</span></span>  
  
-   <span data-ttu-id="19edf-138">TextData</span><span class="sxs-lookup"><span data-stu-id="19edf-138">TextData</span></span>  
  
-   <span data-ttu-id="19edf-139">Nome do Aplicativo</span><span class="sxs-lookup"><span data-stu-id="19edf-139">Application Name</span></span>  
  
-   <span data-ttu-id="19edf-140">LoginName</span><span class="sxs-lookup"><span data-stu-id="19edf-140">LoginName</span></span>  
  
-   <span data-ttu-id="19edf-141">DatabaseName</span><span class="sxs-lookup"><span data-stu-id="19edf-141">DatabaseName</span></span>  
  
-   <span data-ttu-id="19edf-142">ID do banco de dados</span><span class="sxs-lookup"><span data-stu-id="19edf-142">Database ID</span></span>  
  
-   <span data-ttu-id="19edf-143">HostName</span><span class="sxs-lookup"><span data-stu-id="19edf-143">HostName</span></span>  
  
-   <span data-ttu-id="19edf-144">Binary Data</span><span class="sxs-lookup"><span data-stu-id="19edf-144">Binary Data</span></span>  
  
-   <span data-ttu-id="19edf-145">SPID</span><span class="sxs-lookup"><span data-stu-id="19edf-145">SPID</span></span>  
  
-   <span data-ttu-id="19edf-146">Hora de início</span><span class="sxs-lookup"><span data-stu-id="19edf-146">Start Time</span></span>  
  
-   <span data-ttu-id="19edf-147">EndTime</span><span class="sxs-lookup"><span data-stu-id="19edf-147">EndTime</span></span>  
  
-   <span data-ttu-id="19edf-148">IsSystem</span><span class="sxs-lookup"><span data-stu-id="19edf-148">IsSystem</span></span>  
  
## <a name="supported-input-trace-and-target-server-combinations"></a><span data-ttu-id="19edf-149">Rastreamento de entrada e combinações de servidor de destino com suporte</span><span class="sxs-lookup"><span data-stu-id="19edf-149">Supported Input Trace and Target Server Combinations</span></span>  
 <span data-ttu-id="19edf-150">A tabela a seguir lista as versões com suporte dos dados de rastreamento e, para cada uma, as versões com suporte do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em que os dados podem ser repetidos.</span><span class="sxs-lookup"><span data-stu-id="19edf-150">The following table lists the supported versions of trace data, and for each, the supported versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that data can be replayed against.</span></span>  
  
|<span data-ttu-id="19edf-151">Versão de dados de rastreamento de entrada</span><span class="sxs-lookup"><span data-stu-id="19edf-151">Version of Input Trace Data</span></span>|<span data-ttu-id="19edf-152">Versões com suporte do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para a instância do servidor de destino</span><span class="sxs-lookup"><span data-stu-id="19edf-152">Supported Versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the Target Server Instance</span></span>|  
|---------------------------------|------------------------------------------------------------------------------------|  
|[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]<span data-ttu-id="19edf-153">, [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19edf-153">, [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]<span data-ttu-id="19edf-154">, [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19edf-154">, [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="19edf-155">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19edf-155">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]<span data-ttu-id="19edf-156">, [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19edf-156">, [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|[!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]|[!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]|  
  
## <a name="operating-system-requirements"></a><span data-ttu-id="19edf-157">Requisitos do Sistema Operacional</span><span class="sxs-lookup"><span data-stu-id="19edf-157">Operating System Requirements</span></span>  
 <span data-ttu-id="19edf-158">Os sistemas operacionais com suporte para a execução da ferramenta de administração e o controlador e os serviços cliente são os mesmos que sua instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="19edf-158">Supported operating systems for running the administration tool and the controller and client services is the same as your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="19edf-159">Para obter mais informações sobre quais sistemas operacionais têm suporte para sua [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instância do, consulte [requisitos de hardware e software para a instalação do SQL Server 2014](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="19edf-159">For more information about which operating systems are supported for your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance, see [Hardware and Software Requirements for Installing SQL Server 2014](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md).</span></span>  
  
 <span data-ttu-id="19edf-160">Os recursos do Distributed Replay têm suporte em sistemas operacionais x86 e x64.</span><span class="sxs-lookup"><span data-stu-id="19edf-160">Distributed Replay features are supported on both x86-based and x64-based operating systems.</span></span> <span data-ttu-id="19edf-161">Para sistemas operacionais x64, somente há suporte para Windows no modo Windows (WOW).</span><span class="sxs-lookup"><span data-stu-id="19edf-161">For x64-based operating systems, only Windows on Windows (WOW) mode is supported.</span></span>  
  
## <a name="installation-limitations"></a><span data-ttu-id="19edf-162">Limitações de instalação</span><span class="sxs-lookup"><span data-stu-id="19edf-162">Installation Limitations</span></span>  
 <span data-ttu-id="19edf-163">Qualquer computador pode ter apenas uma única instância de cada recurso do Distributed Replay instalado.</span><span class="sxs-lookup"><span data-stu-id="19edf-163">Any one computer can only have a single instance of each Distributed Replay feature installed.</span></span> <span data-ttu-id="19edf-164">A tabela a seguir lista a quantidade de instalações de cada recurso permitida em um único ambiente do Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="19edf-164">The following table lists how many installations of each feature are allowed in a single Distributed Replay environment.</span></span>  
  
|<span data-ttu-id="19edf-165">Recurso Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="19edf-165">Distributed Replay Feature</span></span>|<span data-ttu-id="19edf-166">Máximo de instalações por ambiente de repetição</span><span class="sxs-lookup"><span data-stu-id="19edf-166">Maximum Installations Per Replay Environment</span></span>|  
|--------------------------------|--------------------------------------------------|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="19edf-167">Distributed Replay Controller</span><span class="sxs-lookup"><span data-stu-id="19edf-167">Distributed Replay controller service</span></span>|<span data-ttu-id="19edf-168">1</span><span class="sxs-lookup"><span data-stu-id="19edf-168">1</span></span>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="19edf-169">Distributed Replay Client</span><span class="sxs-lookup"><span data-stu-id="19edf-169">Distributed Replay client service</span></span>|<span data-ttu-id="19edf-170">16 (computadores físicos ou virtuais)</span><span class="sxs-lookup"><span data-stu-id="19edf-170">16 (physical or virtual computers)</span></span>|  
|<span data-ttu-id="19edf-171">Ferramenta de administração</span><span class="sxs-lookup"><span data-stu-id="19edf-171">Administration tool</span></span>|<span data-ttu-id="19edf-172">Ilimitado</span><span class="sxs-lookup"><span data-stu-id="19edf-172">Unlimited</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="19edf-173">Embora só uma instância da ferramenta de administração possa ser instalada em um único computador, você pode iniciar várias instâncias dessa ferramenta.</span><span class="sxs-lookup"><span data-stu-id="19edf-173">Although only one instance of the administration tool can be installed on a single computer, you can start multiple instances of the administration tool.</span></span> <span data-ttu-id="19edf-174">Os comandos emitidos de várias ferramentas de administração são resolvidos na ordem em que são recebidos.</span><span class="sxs-lookup"><span data-stu-id="19edf-174">Commands issued from multiple administration tools are resolved in the order in which they are received.</span></span>  
  
## <a name="data-access-provider"></a><span data-ttu-id="19edf-175">Provedor de dados do sistema</span><span class="sxs-lookup"><span data-stu-id="19edf-175">Data Access Provider</span></span>  
 <span data-ttu-id="19edf-176">O Distributed Replay tem suporte apenas para o provedor de acesso a dados ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="19edf-176">Distributed Replay only supports the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC data access provider.</span></span>  
  
## <a name="target-server-preparation-requirements"></a><span data-ttu-id="19edf-177">Requisitos de preparação do servidor de destino</span><span class="sxs-lookup"><span data-stu-id="19edf-177">Target Server Preparation Requirements</span></span>  
 <span data-ttu-id="19edf-178">Nós recomendamos que o servidor de destino seja localizado em um ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="19edf-178">We recommend that the target server be located in a test environment.</span></span> <span data-ttu-id="19edf-179">Para repetir dados de rastreamento em uma instância diferente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da que foi originalmente registrada, verifique se as seguintes ações foram executadas no servidor de destino:</span><span class="sxs-lookup"><span data-stu-id="19edf-179">To replay trace data against a different instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] than it was originally recorded, make sure that the following has been done to the target server:</span></span>  
  
-   <span data-ttu-id="19edf-180">Todos os logons e usuários contidos nos dados de rastreamento devem estar presentes no mesmo banco de dados no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="19edf-180">All logins and users that are contained in the trace data must be present in the same database on the target server.</span></span>  
  
-   <span data-ttu-id="19edf-181">Todos os logos e usuários no servidor de destino devem ter as mesmas permissões que tinham no servidor original.</span><span class="sxs-lookup"><span data-stu-id="19edf-181">All logins and users on the target server must have the same permissions they had on the original server.</span></span>  
  
-   <span data-ttu-id="19edf-182">As IDs do banco de dados no destino devem, idealmente, ser idênticas àquela na origem.</span><span class="sxs-lookup"><span data-stu-id="19edf-182">The database IDs on the target ideally should be the same as those on the source.</span></span> <span data-ttu-id="19edf-183">No entanto, se essas permissões não forem iguais, a correspondência poderá ser executada com base no **DatabaseName** se estiver presente no rastreamento.</span><span class="sxs-lookup"><span data-stu-id="19edf-183">However, if they are not the same, matching can be performed based on **DatabaseName** if it is present in the trace.</span></span>  
  
-   <span data-ttu-id="19edf-184">O banco de dados padrão de cada logon contido nos dados de rastreamento deve estar configurado (no servidor de destino) para o respectivo banco de dados de destino do logon.</span><span class="sxs-lookup"><span data-stu-id="19edf-184">The default database for each login that is contained in the trace data must be set (on the target server) to the respective target database of the login.</span></span> <span data-ttu-id="19edf-185">Por exemplo, os dados de rastreamento a serem repetidos contêm atividade para o logon, **Pedro**, no banco de dados **Pedro_Db** na instância original do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19edf-185">For example, the trace data to be replayed contains activity for the login, **Fred**, in the database **Fred_Db** on the original instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="19edf-186">Portanto, no servidor de destino, o banco de dados padrão do logon **Pedro**deve estar configurado para o banco de dados que corresponde a **Pedro_Db** (mesmo que o nome do banco de dados seja diferente).</span><span class="sxs-lookup"><span data-stu-id="19edf-186">Therefore, on the target server, the default database for the login, **Fred**, must be set to the database that matches **Fred_Db** (even if the database name is different).</span></span> <span data-ttu-id="19edf-187">Para configurar o banco de dados padrão do logon, use o procedimento armazenado de sistema `sp_defaultdb` .</span><span class="sxs-lookup"><span data-stu-id="19edf-187">To set the default database of the login, use the `sp_defaultdb` system stored procedure.</span></span>  
  
 <span data-ttu-id="19edf-188">A repetição de eventos associados com logons faltantes ou incorretos resulta em erros de repetição, mas a operação de repetição continua.</span><span class="sxs-lookup"><span data-stu-id="19edf-188">Replaying events associated with missing or incorrect logins results in replay errors, but the replay operation continues.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19edf-189">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="19edf-189">See Also</span></span>  
 <span data-ttu-id="19edf-190">[SQL Server Distributed Replay](sql-server-distributed-replay.md) </span><span class="sxs-lookup"><span data-stu-id="19edf-190">[SQL Server Distributed Replay](sql-server-distributed-replay.md) </span></span>  
 <span data-ttu-id="19edf-191">[Segurança de Distributed Replay](distributed-replay-security.md) </span><span class="sxs-lookup"><span data-stu-id="19edf-191">[Distributed Replay Security](distributed-replay-security.md) </span></span>  
 [<span data-ttu-id="19edf-192">Instalar o Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="19edf-192">Install Distributed Replay</span></span>](install-distributed-replay-overview.md)  
  
  
