---
title: Utilitário ssbdiagnose (Service Broker) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- Service Broker, runtime reports
- Service Broker, command prompt utilities
- troubleshooting [Service Broker], conversations
- troubleshooting [Service Broker], configurations
- command prompt utilities [Service Broker]
- Service Broker, troubleshooting
- Service Broker, configuration reports
- Service Broker, tools
- troubleshooting [Service Broker], runtime
- conversations [Service Broker], troubleshooting
- troubleshooting [Service Broker], ssbdiagnose utility
- tools [Service Broker], ssbdiagnose
- Service Broker, ssbdiagnose utility
- ssbdiagnose
ms.assetid: 0c1636e8-a3db-438e-be4c-1ea40d1f4877
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8efc581eebd7d8fa7fa265abb54168af78b57ca2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683239"
---
# <a name="ssbdiagnose-utility-service-broker"></a><span data-ttu-id="3c1b4-102">Utilitário ssbdiagnose (Service Broker)</span><span class="sxs-lookup"><span data-stu-id="3c1b4-102">ssbdiagnose Utility (Service Broker)</span></span>
  <span data-ttu-id="3c1b4-103">O utilitário **ssbdiagnose** relata problemas em conversas do [!INCLUDE[ssSB](../../includes/sssb-md.md)] ou na configuração de serviços do [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3c1b4-103">The **ssbdiagnose** utility reports issues in [!INCLUDE[ssSB](../../includes/sssb-md.md)] conversations or the configuration of [!INCLUDE[ssSB](../../includes/sssb-md.md)] services.</span></span> <span data-ttu-id="3c1b4-104">É possível fazer verificações de configuração para dois serviços ou um único serviço.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-104">Configuration checks can be made for either two services or a single service.</span></span> <span data-ttu-id="3c1b4-105">Os problemas são reportados na janela de prompt de comando como texto legível ou XML formatado que pode ser redirecionado para um arquivo ou outro programa.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-105">Issues are reported either in the command prompt window as human-readable text, or as formatted XML that can be redirected to a file or another program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c1b4-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3c1b4-106">Syntax</span></span>  
  
```  
  
      ssbdiagnose   
[ [ -XML ]  
    [ -LEVEL { ERROR | WARNING | INFO } ]  
  [-IGNOREerror_id ] [ ...n]  
    [ <baseconnectionoptions> ]  
  { <configurationreport> | <runtimereport> }  
]  
| -?  
  
<configurationreport> ::=  
    CONFIGURATION  
  { [ FROM SERVICEservice_name  
      [ <fromconnectionoptions> ]  
      [ MIRROR <mirrorconnectionoptions> ]  
    ]  
    [ TO SERVICEservice_name[, broker_id ]  
      [ <toconnectionoptions> ]  
      [ MIRROR <mirrorconnectionoptions> ]  
    ]  
  }  
    ON CONTRACTcontract_name  
  [ ENCRYPTION { ON | OFF | ANONYMOUS } ]  
  
<runtime_report> ::=  
    RUNTIME  
    [-SHOWEVENTS ]  
        [ -NEW  
         [ -ID { conversation_handle  
                | conversation_group_id  
                 | conversation_id  
                  }  
        ] [ ...n]  
        ]  
    [ -TIMEOUTtimeout_interval ]  
    [ <runtimeconnectionoptions> ]  
  
<baseconnectionoptions> ::=  
  <connectionoptions>  
  
<fromconnectionoptions> ::=  
  <connectionoptions>  
  
<toconnectionoptions> ::=  
  <connectionoptions>  
  
<mirrorconnectionoptions> ::=  
  <connectionoptions>  
  
<runtimeconnectionoptions> ::=  
  [ CONNECT TO <connectionoptions> ] [ ...n]  
  
<connectionoptions> ::=  
    [ -E | { -Ulogin_id [ -Ppassword ] } ]  
  [ -Sserver_name[\instance_name] ]  
  [ -ddatabase_name ]  
  [ -llogin_timeout ]  
  
```  
  
## <a name="command-line-options"></a><span data-ttu-id="3c1b4-107">Opções de linha de comando</span><span class="sxs-lookup"><span data-stu-id="3c1b4-107">Command Line Options</span></span>  
 <span data-ttu-id="3c1b4-108">**-XML**</span><span class="sxs-lookup"><span data-stu-id="3c1b4-108">**-XML**</span></span>  
 <span data-ttu-id="3c1b4-109">Especifica que a saída de **ssbdiagnose** será gerada como XML formatado.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-109">Specifies that the **ssbdiagnose** output be generated as formatted XML.</span></span> <span data-ttu-id="3c1b4-110">Essa saída pode ser redirecionado para um arquivo ou outro aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-110">This can be redirected to a file or to another application.</span></span> <span data-ttu-id="3c1b4-111">Se **-XML** não for especificado, a saída de **ssbdiagnose** será formatada como texto legível.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-111">If **-XML** is not specified, the **ssbdiagnose** output is formatted as human-readable text.</span></span>  
  
 <span data-ttu-id="3c1b4-112">**-LEVEL** { **ERROR** | **WARNING** | **INFO**}</span><span class="sxs-lookup"><span data-stu-id="3c1b4-112">**-LEVEL** { **ERROR** | **WARNING** | **INFO**}</span></span>  
 <span data-ttu-id="3c1b4-113">Especifica o nível das mensagens a serem reportadas.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-113">Specifies the level of messages to report.</span></span>  
  
 <span data-ttu-id="3c1b4-114">**ERRO**: relata apenas mensagens de erro.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-114">**ERROR**: report only error messages.</span></span>  
  
 <span data-ttu-id="3c1b4-115">**AVISO**: relata mensagens de erro e de aviso.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-115">**WARNING**: report error and warning messages.</span></span>  
  
 <span data-ttu-id="3c1b4-116">**INFORMAÇÃO**: relata mensagens de erro, aviso e informações.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-116">**INFO**: report error, warning, and informational messages.</span></span>  
  
 <span data-ttu-id="3c1b4-117">A configuração padrão é **AVISO**.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-117">The default setting is **WARNING**.</span></span>  
  
 <span data-ttu-id="3c1b4-118">**-IGNORE** *error_id*</span><span class="sxs-lookup"><span data-stu-id="3c1b4-118">**-IGNORE** *error_id*</span></span>  
 <span data-ttu-id="3c1b4-119">Especifica que os erros ou as mensagens com a *error_id* especificada não serão incluídos em relatórios.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-119">Specifies that errors or messages that have the specified *error_id* not be included in reports.</span></span> <span data-ttu-id="3c1b4-120">Você pode especificar **-IGNORE** várias vezes para suprimir IDs de mensagens múltiplas.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-120">You can specify **-IGNORE** multiple times to suppress multiple message IDs.</span></span>  
  
 **\<baseconnectionoptions>**  
 <span data-ttu-id="3c1b4-121">Especifica as informações de conexão base usadas por **ssbdiagnose** quando opções de conexão não estão incluídas em uma cláusula específica.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-121">Specifies the base connection information that is used by **ssbdiagnose** when connection options are not included in a specific clause.</span></span> <span data-ttu-id="3c1b4-122">A informações de conexão atribuídas em uma cláusula específica substituem as informações de **baseconnectionoption** .</span><span class="sxs-lookup"><span data-stu-id="3c1b4-122">The connection information that is given in a specific clause overrides the **baseconnectionoption** information.</span></span> <span data-ttu-id="3c1b4-123">Essa operação é executada separadamente para cada parâmetro.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-123">This is performed separately for each parameter.</span></span> <span data-ttu-id="3c1b4-124">Por exemplo, se **-S** e **-d** estiverem especificados no **baseconnetionoptions**, e somente **-d** estiver especificado no **toconnetionoptions**, o **ssbdiagnose** usará -S do **baseconnetionoptions** e -d do **toconnetionoptions**.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-124">For example, if both **-S** and **-d** are specified in **baseconnetionoptions**, and only **-d** is specified in **toconnetionoptions**, **ssbdiagnose** uses -S from **baseconnetionoptions** and -d from **toconnetionoptions**.</span></span>  
  
 <span data-ttu-id="3c1b4-125">**CONFIGURATION**</span><span class="sxs-lookup"><span data-stu-id="3c1b4-125">**CONFIGURATION**</span></span>  
 <span data-ttu-id="3c1b4-126">Solicita um relatório de erros de configuração entre um par de serviços [!INCLUDE[ssSB](../../includes/sssb-md.md)] ou para um único serviço.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-126">Requests a report of configuration errors between a pair of [!INCLUDE[ssSB](../../includes/sssb-md.md)] services, or for a single service.</span></span>  
  
 <span data-ttu-id="3c1b4-127">**FROM SERVICE** *service_name*</span><span class="sxs-lookup"><span data-stu-id="3c1b4-127">**FROM SERVICE** *service_name*</span></span>  
 <span data-ttu-id="3c1b4-128">Especifica o serviço que inicia as conversas.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-128">Specifies the service that initiates conversations.</span></span>  
  
 **\<fromconnectionoptions>**  
 <span data-ttu-id="3c1b4-129">Especifica as informações necessárias para se conectar ao banco de dados que contém o serviço iniciador.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-129">Specifies the information that is required to connect to the database that holds the initiator service.</span></span> <span data-ttu-id="3c1b4-130">Se **fromconnectionoptions** não for especificado, o **ssbdiagnose** usará as informações de conexão de **baseconnectionoptions** para se conectar ao banco de dados do iniciador.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-130">If **fromconnectionoptions** is not specified, **ssbdiagnose** uses the connection information from **baseconnectionoptions** to connect to the initiator database.</span></span> <span data-ttu-id="3c1b4-131">Se **fromconnectionoptions** for especificado, essa opção deverá incluir o banco de dados que contém o serviço iniciador.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-131">If **fromconnectionoptions** is specified it must include the database that contains the initiator service.</span></span> <span data-ttu-id="3c1b4-132">Se **fromconnectionoptions** não for especificado, o **baseconnectionoptions** deverá especificar o banco de dados do iniciador.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-132">If **fromconnectionoptions** is not specified, the **baseconnectionoptions** must specify the initiator database.</span></span>  
  
 <span data-ttu-id="3c1b4-133">**TO SERVICE** *service_name*[, *broker_id* ]</span><span class="sxs-lookup"><span data-stu-id="3c1b4-133">**TO SERVICE** *service_name*[, *broker_id* ]</span></span>  
 <span data-ttu-id="3c1b4-134">Especifica o serviço que é o destino das conversas.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-134">Specifies the service that is the target for the conversations.</span></span>  
  
 <span data-ttu-id="3c1b4-135">*service_name*: especifica o nome do serviço de destino.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-135">*service_name*: specifies the name of the target service.</span></span>  
  
 <span data-ttu-id="3c1b4-136">*broker_id*: especifica a ID do [!INCLUDE[ssSB](../../includes/sssb-md.md)] que identifica o banco de dados de destino.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-136">*broker_id*: specifies the [!INCLUDE[ssSB](../../includes/sssb-md.md)] ID that identifies the target database.</span></span> <span data-ttu-id="3c1b4-137">*broker_id* é um GUID.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-137">*broker_id* is a GUID.</span></span> <span data-ttu-id="3c1b4-138">Você pode executar a seguinte consulta no banco de dados destino para encontrar esse item:</span><span class="sxs-lookup"><span data-stu-id="3c1b4-138">You can run the following query in the target database to find it:</span></span>  
  
```  
SELECT service_broker_guid  
FROM sys.databases  
WHERE database_id = DB_ID();  
```  
  
 **\<toconnectionoptions>**  
 <span data-ttu-id="3c1b4-139">Especifica as informações necessárias para se conectar ao banco de dados que contém o serviço de destino.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-139">Specifies the information that is required to connect the database that holds the target service.</span></span> <span data-ttu-id="3c1b4-140">Se **toconnectionoptions** não for especificado, o **ssbdiagnose** usará as informações de conexão de **baseconnectionoptions** para se conectar ao banco de dados de destino.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-140">If **toconnectionoptions** is not specified, **ssbdiagnose** uses the connection information from **baseconnectionoptions** to connect to the target database.</span></span>  
  
 <span data-ttu-id="3c1b4-141">**MIRROR**</span><span class="sxs-lookup"><span data-stu-id="3c1b4-141">**MIRROR**</span></span>  
 <span data-ttu-id="3c1b4-142">Especifica que o serviço [!INCLUDE[ssSB](../../includes/sssb-md.md)] associado é hospedado em um banco de dados espelhado.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-142">Specifies that the associated [!INCLUDE[ssSB](../../includes/sssb-md.md)] service is hosted in a mirrored database.</span></span> <span data-ttu-id="3c1b4-143">**ssbdiagnose** verifica se a rota para o serviço é uma rota espelhada, em que MIRROR_ADDRESS foi especificado em CREATE ROUTE.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-143">**ssbdiagnose** verifies that the route to the service is a mirrored route, where MIRROR_ADDRESS was specified on CREATE ROUTE.</span></span>  
  
 **\<mirrorconnectionoptions>**  
 <span data-ttu-id="3c1b4-144">Especifica as informações necessárias para se conectar ao banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-144">Specifies the information that is required to connect to the mirror database.</span></span> <span data-ttu-id="3c1b4-145">Se **mirrorconnectionoptions** não for especificado, o **ssbdiagnose** usará as informações de conexão de **baseconnectionoptions** para se conectar ao banco de dados de espelho.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-145">If **mirrorconnectionoptions** is not specified, **ssbdiagnose** uses the connection information from **baseconnectionoptions** to connect to the mirror database.</span></span>  
  
 <span data-ttu-id="3c1b4-146">**ON CONTRACT** *contract_name*</span><span class="sxs-lookup"><span data-stu-id="3c1b4-146">**ON CONTRACT** *contract_name*</span></span>  
 <span data-ttu-id="3c1b4-147">Solicita que **ssbdiagnose** verifique apenas as configurações que usam o contrato especificado.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-147">Requests that **ssbdiagnose** only check configurations that use the specified contract.</span></span> <span data-ttu-id="3c1b4-148">Se ON CONTRACT não for especificado, **ssbdiagnose** relatará o contrato denominado DEFAULT.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-148">If ON CONTRACT is not specified, **ssbdiagnose** reports on the contract named DEFAULT.</span></span>  
  
 <span data-ttu-id="3c1b4-149">**ENCRYPTION** { **ON** | **OFF** | **ANONYMOUS** }</span><span class="sxs-lookup"><span data-stu-id="3c1b4-149">**ENCRYPTION** { **ON** | **OFF** | **ANONYMOUS** }</span></span>  
 <span data-ttu-id="3c1b4-150">Solicita verificação se o diálogo está configurado corretamente para o nível especificado de criptografia:</span><span class="sxs-lookup"><span data-stu-id="3c1b4-150">Requests verification that the dialog is correctly configured for the specified level of encryption:</span></span>  
  
 <span data-ttu-id="3c1b4-151">**LIGADO**: configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-151">**ON**: Default setting.</span></span> <span data-ttu-id="3c1b4-152">A segurança de diálogo total está configurada.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-152">Full dialog security is configured.</span></span> <span data-ttu-id="3c1b4-153">Certificados foram implantados nos dois lados do diálogo, uma associação de serviço remoto está presente e a instrução GRANT SEND do serviço de destino especificou o usuário iniciador.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-153">Certificates have been deployed on both sides of the dialog, a remote service binding is present, and the GRANT SEND statement for the target service specified the initiator user.</span></span>  
  
 <span data-ttu-id="3c1b4-154">**DESLIGADO**: nenhuma segurança de diálogo está configurada.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-154">**OFF**: No dialog security is configured.</span></span> <span data-ttu-id="3c1b4-155">Nenhum certificado foi implantado, nenhuma associação de serviço remoto foi criada e a instrução GRANT SEND do serviço iniciador especificou a função **public** .</span><span class="sxs-lookup"><span data-stu-id="3c1b4-155">No certificates have been deployed, no remote service binding was created, and the GRANT SEND for the initiator service specified the **public** role.</span></span>  
  
 <span data-ttu-id="3c1b4-156">**ANÔNIMO**: a segurança de diálogo anônima está configurada.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-156">**ANONYMOUS**: Anonymous dialog security is configured.</span></span> <span data-ttu-id="3c1b4-157">Um certificado foi implantado, a associação de serviço remoto especificou a cláusula anônima e a instrução GRANT SEND do serviço de destino especificou a função **public** .</span><span class="sxs-lookup"><span data-stu-id="3c1b4-157">One certificate has been deployed, the remote service binding specified the anonymous clause, and the GRANT SEND for the target service specified the **public** role.</span></span>  
  
 <span data-ttu-id="3c1b4-158">**RUNTIME**</span><span class="sxs-lookup"><span data-stu-id="3c1b4-158">**RUNTIME**</span></span>  
 <span data-ttu-id="3c1b4-159">Solicita um relatório de problemas que causam erros de runtime para uma conversa do [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3c1b4-159">Requests a report of issues that cause runtime errors for a [!INCLUDE[ssSB](../../includes/sssb-md.md)] conversation.</span></span> <span data-ttu-id="3c1b4-160">Se nem **-NEW** ou **-ID** forem especificadas, o **ssbdiagnose** monitorará todas as conversas em todos os bancos de dados especificados nas opções de conexão.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-160">If neither **-NEW** or **-ID** are specified, **ssbdiagnose** monitors all conversations in all databases specified in the connection options.</span></span> <span data-ttu-id="3c1b4-161">Se **-NEW** ou **-ID** forem especificadas, o **ssbdiagnose** criará uma lista de IDs especificadas nos parâmetros.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-161">If **-NEW** or **-ID** are specified, **ssbdiagnose** builds a list of the IDs specified in the parameters.</span></span>  
  
 <span data-ttu-id="3c1b4-162">Durante a execução de **ssbdiagnose** , todos os eventos do [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] que indicam erros em runtime são registrados.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-162">While **ssbdiagnose** is running, it records all [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] events that indicate runtime errors.</span></span> <span data-ttu-id="3c1b4-163">Registra os eventos que ocorrem para as ID especificadas, além de eventos de nível de sistema.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-163">It records the events that occur for the specified IDs, plus system-level events.</span></span> <span data-ttu-id="3c1b4-164">Se forem encontrados erros em runtime, **ssbdiagnose** executará um relatório de configuração sobre a configuração associada.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-164">If runtime errors are encountered, **ssbdiagnose** runs a configuration report on the associated configuration.</span></span>  
  
 <span data-ttu-id="3c1b4-165">Por padrão, os erros em runtime não são incluídos no relatório de saída, somente os resultados da análise de configuração.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-165">By default, runtime errors are not included in the output report, only the results of the configuration analysis.</span></span> <span data-ttu-id="3c1b4-166">Use **-SHOWEVENTS** para que os erros em runtime sejam incluídos no relatório.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-166">Use **-SHOWEVENTS** to have the runtime errors included in the report.</span></span>  
  
 <span data-ttu-id="3c1b4-167">**-SHOWEVENTS**</span><span class="sxs-lookup"><span data-stu-id="3c1b4-167">**-SHOWEVENTS**</span></span>  
 <span data-ttu-id="3c1b4-168">Especifica que **ssbdiagnose** relata eventos do [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] durante um relatório RUNTIME.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-168">Specifies that **ssbdiagnose** report [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] events during a RUNTIME report.</span></span> <span data-ttu-id="3c1b4-169">Somente eventos considerados condições de erro são reportados.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-169">Only events that are considered error conditions are reported.</span></span> <span data-ttu-id="3c1b4-170">Por padrão, **ssbdiagnose** monitora apenas eventos de erro; não os relata na saída.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-170">By default, **ssbdiagnose** only monitors error events; it does not report them in the output.</span></span>  
  
 <span data-ttu-id="3c1b4-171">**-NEW**</span><span class="sxs-lookup"><span data-stu-id="3c1b4-171">**-NEW**</span></span>  
 <span data-ttu-id="3c1b4-172">Solicita o monitoramento no runtime da primeira conversa iniciada após o começo da execução de **ssbdiagnose**.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-172">Requests runtime monitoring of the first conversation that begins after **ssbdiagnose** starts running.</span></span>  
  
 <span data-ttu-id="3c1b4-173">**-ID**</span><span class="sxs-lookup"><span data-stu-id="3c1b4-173">**-ID**</span></span>  
 <span data-ttu-id="3c1b4-174">Solicita o monitoramento de runtime dos elementos de conversa especificados.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-174">Requests runtime monitoring of the specified conversation elements.</span></span> <span data-ttu-id="3c1b4-175">Você pode especificar **-ID** várias vezes.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-175">You can specify **-ID** multiple times.</span></span>  
  
 <span data-ttu-id="3c1b4-176">Se você especificar um identificador de conversa, somente os eventos associados ao ponto de extremidade da conversa associada serão reportados.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-176">If you specify a conversation handle, only events associated with the associated conversation endpoint are reported.</span></span> <span data-ttu-id="3c1b4-177">Se você especificar uma ID de conversa, todos os eventos dessa conversa e seus pontos de extremidade iniciador e de destino serão reportados.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-177">If you specify a conversation ID, all events for that conversation and its initiator and target endpoints are reported.</span></span> <span data-ttu-id="3c1b4-178">Se uma ID de grupo de conversa for especificada, todos os eventos de todas as conversas e pontos de extremidade no grupo de conversa serão reportados.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-178">If a conversation group ID is specified, all events for all conversations and endpoints in the conversation group are reported.</span></span>  
  
 <span data-ttu-id="3c1b4-179">*conversation_handle*</span><span class="sxs-lookup"><span data-stu-id="3c1b4-179">*conversation_handle*</span></span>  
 <span data-ttu-id="3c1b4-180">Um identificador exclusivo que identifica um ponto de extremidade de conversa em um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-180">A unique identifier that identifies a conversation endpoint in an application.</span></span> <span data-ttu-id="3c1b4-181">Os identificadores de conversa são exclusivos para um ponto de extremidade de uma conversa; os pontos de extremidade iniciador e de destino têm identificadores de conversa separados.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-181">Conversation handles are unique to one endpoint of a conversation, the initiator and target endpoints have separate conversation handles.</span></span>  
  
 <span data-ttu-id="3c1b4-182">Os identificadores de conversa são retornados aos aplicativos pelo *@dialog_handle* parâmetro da instrução **BEGIN DIALOG** e a `conversation_handle` coluna no conjunto de resultados de uma instrução **Receive** .</span><span class="sxs-lookup"><span data-stu-id="3c1b4-182">Conversation handles are returned to applications by the *@dialog_handle* parameter of the **BEGIN DIALOG** statement, and the `conversation_handle` column in the result set of a **RECEIVE** statement.</span></span>  
  
 <span data-ttu-id="3c1b4-183">Os identificadores de conversa são relatados na `conversation_handle` coluna das exibições de catálogo **sys. transmission_queue** e **Sys. conversation_endpoints** .</span><span class="sxs-lookup"><span data-stu-id="3c1b4-183">Conversation handles are reported in the `conversation_handle` column of the **sys.transmission_queue** and **sys.conversation_endpoints** catalog views.</span></span>  
  
 <span data-ttu-id="3c1b4-184">*conversation_group_id*</span><span class="sxs-lookup"><span data-stu-id="3c1b4-184">*conversation_group_id*</span></span>  
 <span data-ttu-id="3c1b4-185">O identificador exclusivo que identifica um grupo de conversa.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-185">The unique identifier that identifies a conversation group.</span></span>  
  
 <span data-ttu-id="3c1b4-186">As IDs do grupo de conversa são retornadas aos aplicativos pelo *@conversation_group_id* parâmetro da instrução **Get Conversation Group** e da `conversation_group_id` coluna no conjunto de resultados de uma instrução **Receive** .</span><span class="sxs-lookup"><span data-stu-id="3c1b4-186">Conversation group IDs are returned to applications by the *@conversation_group_id* parameter of the **GET CONVERSATION GROUP** statement and the `conversation_group_id` column in the result set of a **RECEIVE** statement.</span></span>  
  
 <span data-ttu-id="3c1b4-187">As IDs do grupo de conversa são relatadas nas `conversation_group_id` colunas das exibições de catálogo **sys. conversation_groups** e **Sys. conversation_endpoints** .</span><span class="sxs-lookup"><span data-stu-id="3c1b4-187">Conversation group IDs are reported in the `conversation_group_id` columns of the **sys.conversation_groups** and **sys.conversation_endpoints** catalog views.</span></span>  
  
 <span data-ttu-id="3c1b4-188">*conversation_id*</span><span class="sxs-lookup"><span data-stu-id="3c1b4-188">*conversation_id*</span></span>  
 <span data-ttu-id="3c1b4-189">O identificador exclusivo que identifica uma conversa.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-189">The unique identifier that identifies a conversation.</span></span> <span data-ttu-id="3c1b4-190">As IDs de conversa são iguais para os pontos de extremidade iniciador e de destino de uma conversa.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-190">Conversation IDs are the same for both the initiator and target endpoints of a conversation.</span></span>  
  
 <span data-ttu-id="3c1b4-191">As IDs de conversa são relatadas na `conversation_id` coluna da exibição de catálogo **sys. conversation_endpoints** .</span><span class="sxs-lookup"><span data-stu-id="3c1b4-191">Conversation IDs are reported in the `conversation_id` column of the **sys.conversation_endpoints** catalog view.</span></span>  
  
 <span data-ttu-id="3c1b4-192">**-TIMEOUT** *timeout_interval*</span><span class="sxs-lookup"><span data-stu-id="3c1b4-192">**-TIMEOUT** *timeout_interval*</span></span>  
 <span data-ttu-id="3c1b4-193">Especifica o número de segundos para a execução de um relatório **RUNTIME** .</span><span class="sxs-lookup"><span data-stu-id="3c1b4-193">Specifies the number of seconds for a **RUNTIME** report to run.</span></span> <span data-ttu-id="3c1b4-194">Se **-TIMEOUT** não for especificado, o relatório de runtime será executado indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-194">If **-TIMEOUT** is not specified the runtime report runs indefinitely.</span></span> <span data-ttu-id="3c1b4-195">**-TIMEOUT** é usado somente em relatórios de **RUNTIME** , não relatórios de **CONFIGURATION** .</span><span class="sxs-lookup"><span data-stu-id="3c1b4-195">**-TIMEOUT** is used only on **RUNTIME** reports, not **CONFIGURATION** reports.</span></span> <span data-ttu-id="3c1b4-196">Use ctrl + C para sair de **ssbdiagnose** if **-TIMEOUT** não foi especificado ou para encerrar um relatório de runtime antes de o intervalo **-** limite expirar.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-196">Use ctrl + C to quit **ssbdiagnose** if **-TIMEOUT** was not specified or to end a runtime report before the time**-** out interval expires.</span></span> <span data-ttu-id="3c1b4-197">*timeout_interval* deve ser um número entre 1 e 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-197">*timeout_interval* must be a number between 1 and 2,147,483,647.</span></span>  
  
 **\<runtimeconnectionoptions>**  
 <span data-ttu-id="3c1b4-198">Especifica as informações de conexão para os bancos de dados que contêm os serviços associados aos elementos de conversa sendo monitorados.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-198">Specifies the connection information for the databases that contain the services associated with conversation elements being monitored.</span></span> <span data-ttu-id="3c1b4-199">Se todos os serviços estiverem no mesmo banco de dados, você terá de especificar apenas uma cláusula **CONNECT TO** .</span><span class="sxs-lookup"><span data-stu-id="3c1b4-199">If all the services are in the same database, you only have to specify one **CONNECT TO** clause.</span></span> <span data-ttu-id="3c1b4-200">Se os serviços estiverem em bancos de dados separados, você deverá fornecer uma cláusula **CONNECT TO** para cada banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-200">If the services are in separate databases you must supply a **CONNECT TO** clause for each database.</span></span> <span data-ttu-id="3c1b4-201">Se **runtimeconnectionoptions** não for especificado, **ssbdiagnose** usará as informações de conexão de **baseconnectionoptions**.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-201">If **runtimeconnectionoptions** is not specified, **ssbdiagnose** uses the connection information from **baseconnectionoptions**.</span></span>  
  
 <span data-ttu-id="3c1b4-202">**-E**</span><span class="sxs-lookup"><span data-stu-id="3c1b4-202">**-E**</span></span>  
 <span data-ttu-id="3c1b4-203">Abra uma conexão de Autenticação do Windows com uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] usando sua conta atual do Windows como ID de logon.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-203">Open a Windows Authentication connection to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by using your current Windows account as the login ID.</span></span> <span data-ttu-id="3c1b4-204">O logon deve ser membro da função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="3c1b4-204">The login must be a member of the **sysadmin** fixed-server role.</span></span>  
  
 <span data-ttu-id="3c1b4-205">A opção -E ignora as configurações de usuário e senha das variáveis de ambiente SQLCMDUSER e SQLCMDPASSWORD.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-205">The -E option ignores the user and password settings of the SQLCMDUSER and SQLCMDPASSWORD environment variables.</span></span>  
  
 <span data-ttu-id="3c1b4-206">Se **-E** ou **-U** não for especificado, **ssbdiagnose** usará o valor da variável de ambiente SQLCMDUSER.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-206">If neither **-E** nor **-U** is specified, **ssbdiagnose** uses the value from the SQLCMDUSER environment variable.</span></span> <span data-ttu-id="3c1b4-207">Se SQLCMDUSER também não for definido, **ssbdiagnose** usará a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-207">If SQLCMDUSER is not set either, **ssbdiagnose** uses Windows Authentication.</span></span>  
  
 <span data-ttu-id="3c1b4-208">Se a opção **-E** for usada com as opções **-U** ou **-P** , uma mensagem de erro será gerada.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-208">If the **-E** option is used together with the **-U** option or the **-P** option, an error message is generated.</span></span>  
  
 <span data-ttu-id="3c1b4-209">**-U** *login_id*</span><span class="sxs-lookup"><span data-stu-id="3c1b4-209">**-U** *login_id*</span></span>  
 <span data-ttu-id="3c1b4-210">Abra uma conexão de Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando a ID de logon especificada.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-210">Open a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication connection by using the specified login ID.</span></span> <span data-ttu-id="3c1b4-211">O logon deve ser membro da função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="3c1b4-211">The login must be a member of the **sysadmin** fixed-server role.</span></span>  
  
 <span data-ttu-id="3c1b4-212">Se **-E** ou **-U** não for especificado, **ssbdiagnose** usará o valor da variável de ambiente SQLCMDUSER.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-212">If neither **-E** nor **-U** is specified, **ssbdiagnose** uses the value from the SQLCMDUSER environment variable.</span></span> <span data-ttu-id="3c1b4-213">Se SQLCMDUSER também não for definido, **ssbdiagnose** tentará se conectar usando o modo de Autenticação do Windows com base na conta do Windows do usuário que está executando **ssbdiagnose**.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-213">If SQLCMDUSER is not set either, **ssbdiagnose** tries to connect by using Windows Authentication mode based on the Windows account of the user who is running **ssbdiagnose**.</span></span>  
  
 <span data-ttu-id="3c1b4-214">Se a opção **-U** for usada junto com **-E** , uma mensagem de erro será gerada.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-214">If the **-U** option is used together with the **-E** option, an error message is generated.</span></span> <span data-ttu-id="3c1b4-215">Se a opção **-U** for seguida de mais de um argumento, uma mensagem de erro será gerada e o programa será encerrado.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-215">If the **-U** option is followed by more than one argument, an error message is generated and the program exits.</span></span>  
  
 <span data-ttu-id="3c1b4-216">**-P** *password*</span><span class="sxs-lookup"><span data-stu-id="3c1b4-216">**-P** *password*</span></span>  
 <span data-ttu-id="3c1b4-217">Especifica a senha para a ID de logon **-U** .</span><span class="sxs-lookup"><span data-stu-id="3c1b4-217">Specifies the password for the **-U** login ID.</span></span> <span data-ttu-id="3c1b4-218">Senhas diferenciam maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-218">Passwords are case sensitive.</span></span> <span data-ttu-id="3c1b4-219">Se a opção **-U** for usada e **-P** não, **ssbdiagnose** usará o valor da variável de ambiente SQLCMDPASSWORD.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-219">If the **-U** option is used and the **-P** option is not used, **ssbdiagnose** uses the value from the SQLCMDPASSWORD environment variable.</span></span> <span data-ttu-id="3c1b4-220">Se SQLCMDPASSWORD também não for definido, **ssbdiagnose** solicitará uma senha ao usuário.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-220">If SQLCMDPASSWORD is not set either, **ssbdiagnose** prompts the user for a password.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3c1b4-221">Quando você digitar um comando SET SQLCMDPASSWORD, sua senha ficará visível para qualquer pessoa que possa ver seu monitor.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-221">When you type a SET SQLCMDPASSWORD command, your password will be visible to anyone who can see your monitor.</span></span>  
  
 <span data-ttu-id="3c1b4-222">Se a opção **-P** for especificada sem uma senha, **ssbdiagnose** usará o valor padrão (NULL).</span><span class="sxs-lookup"><span data-stu-id="3c1b4-222">If the **-P** option is specified without a password **ssbdiagnose** uses the default password (NULL).</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteStrongPass](../../includes/ssnotestrongpass-md.md)] <span data-ttu-id="3c1b4-223">Para obter mais informações, confira [Senhas fortes](../../relational-databases/security/strong-passwords.md).</span><span class="sxs-lookup"><span data-stu-id="3c1b4-223">For more information, see [Strong Passwords](../../relational-databases/security/strong-passwords.md).</span></span>  
  
 <span data-ttu-id="3c1b4-224">A solicitação de senha é exibida no console, como a seguir: `Password:`</span><span class="sxs-lookup"><span data-stu-id="3c1b4-224">The password prompt is displayed by printing the password prompt to the console, as follows: `Password:`</span></span>  
  
 <span data-ttu-id="3c1b4-225">A entrada do usuário está oculta.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-225">User input is hidden.</span></span> <span data-ttu-id="3c1b4-226">Isso significa que nada é exibido e o cursor fica em posição.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-226">This means that nothing is displayed and the cursor stays in position.</span></span>  
  
 <span data-ttu-id="3c1b4-227">Será gerada uma mensagem de erro se a opção **-P** for usada com a opção **-E** .</span><span class="sxs-lookup"><span data-stu-id="3c1b4-227">If the **-P** option is used with the **-E** option, an error message is generated.</span></span>  
  
 <span data-ttu-id="3c1b4-228">Se a opção **-P** for seguida por mais de um argumento, uma mensagem de erro será gerada.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-228">If the **-P** option is followed by more than one argument, an error message is generated.</span></span>  
  
 <span data-ttu-id="3c1b4-229">**-S** *server_name*[\\*instance_name*]</span><span class="sxs-lookup"><span data-stu-id="3c1b4-229">**-S** *server_name*[\\*instance_name*]</span></span>  
 <span data-ttu-id="3c1b4-230">Especifica a instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] que contém os serviços do [!INCLUDE[ssSB](../../includes/sssb-md.md)] a serem analisados.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-230">Specifies the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that holds the [!INCLUDE[ssSB](../../includes/sssb-md.md)] services to be analyzed.</span></span>  
  
 <span data-ttu-id="3c1b4-231">Especifica *server_name* para conexão com a instância padrão do [!INCLUDE[ssDE](../../includes/ssde-md.md)] naquele servidor.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-231">Specify *server_name* to connect to the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on that server.</span></span> <span data-ttu-id="3c1b4-232">Especifique *server_name ***\\*** instance_name* para se conectar a uma instância nomeada do [!INCLUDE[ssDE](../../includes/ssde-md.md)] nesse servidor.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-232">Specify *server_name***\\***instance_name* to connect to a named instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on that server.</span></span> <span data-ttu-id="3c1b4-233">Se **-S** não for especificado, **ssbdiagnose** usará o valor da variável de ambiente SQLCMDSERVER.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-233">If **-S** is not specified, **ssbdiagnose** uses the value of the SQLCMDSERVER environment variable.</span></span> <span data-ttu-id="3c1b4-234">Se SQLCMDSERVER também não for definido, **ssbdiagnose** se conectará à instância padrão do [!INCLUDE[ssDE](../../includes/ssde-md.md)] no computador local.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-234">If SQLCMDSERVER is not set either, **ssbdiagnose** connects to the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on the local computer.</span></span>  
  
 <span data-ttu-id="3c1b4-235">**-d** *database_name*</span><span class="sxs-lookup"><span data-stu-id="3c1b4-235">**-d** *database_name*</span></span>  
 <span data-ttu-id="3c1b4-236">Especifica o banco de dados que contém os serviços do [!INCLUDE[ssSB](../../includes/sssb-md.md)] a serem analisados.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-236">Specifies the database that holds the [!INCLUDE[ssSB](../../includes/sssb-md.md)] services to be analyzed.</span></span> <span data-ttu-id="3c1b4-237">Se o banco de dados não existir, uma mensagem de erro será gerada.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-237">If the database does not exist, an error message is generated.</span></span> <span data-ttu-id="3c1b4-238">Se **-d** não for especificado, o padrão será o banco de dados especificado na propriedade default-database para o seu logon.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-238">If **-d** is not specified, the default is the database specified in the default-database property for your login.</span></span>  
  
 <span data-ttu-id="3c1b4-239">**-l** *login_timeout*</span><span class="sxs-lookup"><span data-stu-id="3c1b4-239">**-l** *login_timeout*</span></span>  
 <span data-ttu-id="3c1b4-240">Especifica o número de segundos que devem decorrer antes que o tempo limite de uma tentativa de conexão com um servidor seja alcançada. Se **-l** não for especificado, **ssbdiagnose** usará o valor definido para a variável de ambiente SQLCMDLOGINTIMEOUT.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-240">Specifies the number of seconds before an attempt to connect to a server times out. If **-l** is not specified, **ssbdiagnose** uses the value set for the SQLCMDLOGINTIMEOUT environment variable.</span></span> <span data-ttu-id="3c1b4-241">Se SQLCMDLOGINTIMEOUT também não for definida, o tempo limite padrão será de trinta segundos.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-241">If SQLCMDLOGINTIMEOUT is not set either, the default time-out is thirty seconds.</span></span> <span data-ttu-id="3c1b4-242">O tempo limite do logon deve ser um número entre 0 e 65534.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-242">The login time-out must be a number between 0 and 65534.</span></span> <span data-ttu-id="3c1b4-243">Se o valor fornecido não for numérico ou não estiver nesse intervalo, **ssbdiagnose** vai gerar uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-243">If the value that is supplied is not numeric or does not fall into that range, **ssbdiagnose** generates an error message.</span></span> <span data-ttu-id="3c1b4-244">Um valor de 0 especifica o tempo limite como infinito.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-244">A value of 0 specifies time-out to be infinite.</span></span>  
  
 <span data-ttu-id="3c1b4-245">**-?**</span><span class="sxs-lookup"><span data-stu-id="3c1b4-245">**-?**</span></span>  
 <span data-ttu-id="3c1b4-246">Exibe a ajuda de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-246">Displays command line help.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c1b4-247">Comentários</span><span class="sxs-lookup"><span data-stu-id="3c1b4-247">Remarks</span></span>  
 <span data-ttu-id="3c1b4-248">Use **ssbdiagnose** para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3c1b4-248">Use **ssbdiagnose** to do the following:</span></span>  
  
-   <span data-ttu-id="3c1b4-249">Confirmar que não há erros de configuração em um aplicativo [!INCLUDE[ssSB](../../includes/sssb-md.md)] recém-configurado.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-249">Confirm that there are no configuration errors in a newly configured [!INCLUDE[ssSB](../../includes/sssb-md.md)] application.</span></span>  
  
-   <span data-ttu-id="3c1b4-250">Confirmar que não há erros de configuração depois que você alterar a configuração de um aplicativo [!INCLUDE[ssSB](../../includes/sssb-md.md)] existente.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-250">Confirm that there are no configuration errors after changing the configuration of an existing [!INCLUDE[ssSB](../../includes/sssb-md.md)] application.</span></span>  
  
-   <span data-ttu-id="3c1b4-251">Confirmar que não há erros de configuração após a desanexação de um banco de dados [!INCLUDE[ssSB](../../includes/sssb-md.md)] nova anexação a uma nova instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c1b4-251">Confirm that there are no configuration errors after a [!INCLUDE[ssSB](../../includes/sssb-md.md)] database is detached and then reattached to a new instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="3c1b4-252">Pesquise se há erros de configuração quando mensagens de erro não são transmitidas com êxito entre serviços.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-252">Research whether there are configuration errors when messages are not successfully transmitted between services.</span></span>  
  
-   <span data-ttu-id="3c1b4-253">Obtenha um relatório de quaisquer erros que ocorram em um conjunto de elementos de conversa de [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3c1b4-253">Get a report of any errors that occur in a set of [!INCLUDE[ssSB](../../includes/sssb-md.md)] conversation elements.</span></span>  
  
## <a name="configuration-reporting"></a><span data-ttu-id="3c1b4-254">Relatório de configuração</span><span class="sxs-lookup"><span data-stu-id="3c1b4-254">Configuration Reporting</span></span>  
 <span data-ttu-id="3c1b4-255">Para analisar corretamente a configuração usada por uma conversa, execute um relatório de configuração **ssbdiagnose** que use as mesmas opções utilizadas pela conversa.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-255">To correctly analyze the configuration used by a conversation, run a **ssbdiagnose** configuration report that uses the same options that are used by the conversation.</span></span> <span data-ttu-id="3c1b4-256">Se você especificar um nível mais baixo de opções para **ssbdiagnose** do que o utilizado pela conversa, **ssbdiagnose** talvez não reporte as condições necessárias para a conversa.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-256">If you specify a lower level of options for **ssbdiagnose** than are used by the conversation, **ssbdiagnose** might not report conditions that are required by the conversation.</span></span> <span data-ttu-id="3c1b4-257">Se você especificar um nível mais alto de opções para **ssbdiagnose**, talvez o utilitário reporte itens desnecessários para a conversa.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-257">If you specify a higher level of options for **ssbdiagnose**, it might report items that are not required by the conversation.</span></span> <span data-ttu-id="3c1b4-258">Por exemplo, uma conversa entre dois serviços no mesmo banco de dados pode ser executada com ENCPRYPTION OFF.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-258">For example, a conversation between two services in the same database can be run with ENCPRYPTION OFF.</span></span> <span data-ttu-id="3c1b4-259">Se você executar **ssbdiagnose** para validar a configuração entre os dois serviços, mas utilizar a configuração ENCRYPTION ON padrão, **ssbdiagnose** relatará que uma chave mestra está faltando no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-259">If you run **ssbdiagnose** to validate the configuration between the two services, but use the default ENCRYPTION ON setting, **ssbdiagnose** reports that the database is missing a master key.</span></span> <span data-ttu-id="3c1b4-260">Uma chave mestra não é necessária para a conversa.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-260">A master key is not required for the conversation.</span></span>  
  
 <span data-ttu-id="3c1b4-261">O relatório de configuração **ssbdiagnose** analisa apenas um serviço do [!INCLUDE[ssSB](../../includes/sssb-md.md)] ou um único par de serviços cada vez que é executado.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-261">The **ssbdiagnose** configuration report analyzes only one [!INCLUDE[ssSB](../../includes/sssb-md.md)] service or a single pair of services every time it is run.</span></span> <span data-ttu-id="3c1b4-262">Para obter relatórios sobre vários pares de serviços do [!INCLUDE[ssSB](../../includes/sssb-md.md)] , crie um arquivo de comando .cmd que chame **ssbdiagnose** várias vezes.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-262">To report on multiple pairs of [!INCLUDE[ssSB](../../includes/sssb-md.md)] services, build a .cmd command file that calls **ssbdiagnose** multiple times.</span></span>  
  
## <a name="runtime-reporting"></a><span data-ttu-id="3c1b4-263">Relatório de runtime</span><span class="sxs-lookup"><span data-stu-id="3c1b4-263">Runtime Reporting</span></span>  
 <span data-ttu-id="3c1b4-264">Quando -RUNTIME é especificado, o **ssbdiagnose** procura todos os bancos de dados especificados no **runtimeconnectionoptions** e no **baseconnectionoptions** para criar uma lista de IDs do [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3c1b4-264">When -RUNTIME is specified, **ssbdiagnose** searches all databases specified in **runtimeconnectionoptions** and **baseconnectionoptions** to build a list of [!INCLUDE[ssSB](../../includes/sssb-md.md)] IDs.</span></span> <span data-ttu-id="3c1b4-265">A lista completa de IDs criada depende dos itens especificados para - NEW e - ID:</span><span class="sxs-lookup"><span data-stu-id="3c1b4-265">The full list of IDs built depends on what is specified for -NEW and -ID:</span></span>  
  
-   <span data-ttu-id="3c1b4-266">Se **-NEW** ou **-ID** não for especificado, a lista conterá todas as conversas de todos os bancos de dados especificados nas opções de conexão.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-266">If neither **-NEW** or **-ID** are specified, the list includes all conversations for all databases specified in the connection options.</span></span>  
  
-   <span data-ttu-id="3c1b4-267">Se **-NEW** for especificado, **ssbdiagnose** incluirá os elementos da primeira conversa iniciada após a execução de **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="3c1b4-267">If **-NEW** is specified, **ssbdiagnose** includes the elements for the first conversation that starts after **ssbdiagnose** is run.</span></span> <span data-ttu-id="3c1b4-268">Isso inclui a ID e os identificadores de conversa dos pontos de extremidade de destino e iniciador da conversa.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-268">This includes the conversation ID and the conversation handles for both the target and initiator conversation endpoints.</span></span>  
  
-   <span data-ttu-id="3c1b4-269">Se **-ID** for especificado com um identificador de conversa, somente esse identificador será incluído na lista.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-269">If **-ID** is specified with a conversation handle, only that handle is included in the list.</span></span>  
  
-   <span data-ttu-id="3c1b4-270">Se **-ID** for especificado com uma ID de conversa, essa ID e os identificadores dos dois pontos de extremidade da conversa serão adicionados à lista.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-270">If **-ID** is specified with a conversation ID, the conversation ID and the handles for both of its conversation endpoints are added to the list.</span></span>  
  
-   <span data-ttu-id="3c1b4-271">Se **-ID** for especificado com uma ID de grupo de conversa, todas as IDs e identificadores de conversa nesse grupo serão adicionados à lista.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-271">If **-ID** is specified with a conversation group ID, all the conversation IDs and conversation handles in that group are added to the list.</span></span>  
  
 <span data-ttu-id="3c1b4-272">A lista não inclui elementos de bancos de dados que não são cobertos pelas opções de conexão.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-272">The list does not include elements from databases that are not covered by the connection options.</span></span> <span data-ttu-id="3c1b4-273">Por exemplo, suponhamos que você use **-ID** para especificar uma ID de conversa, mas forneça somente uma cláusula **runtimeconnectionoptions** para o banco de dados iniciador e não para o banco de dados de destino.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-273">For example, assume that you use **-ID** to specify a conversation ID, but only provide a **runtimeconnectionoptions** clause for the initiator database and not the target database.</span></span> <span data-ttu-id="3c1b4-274">**ssbdiagnose** não incluirá o identificador de conversa de destino em sua lista de IDs, somente a ID da conversa e o identificador da conversa do iniciador.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-274">**ssbdiagnose** will not include the target conversation handle in its list of IDs, only the conversation ID and the initiator conversation handle.</span></span>  
  
 <span data-ttu-id="3c1b4-275">O**ssbdiagnose** monitora os eventos de [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] dos bancos de dados cobertos por **runtimeconnectionoptions** e **baseconnectionoptions**.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-275">**ssbdiagnose** monitors the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] events from the databases covered by **runtimeconnectionoptions** and **baseconnectionoptions**.</span></span> <span data-ttu-id="3c1b4-276">Ele procura eventos do [!INCLUDE[ssSB](../../includes/sssb-md.md)] que indicam que um erro foi encontrado por um ou mais IDs do [!INCLUDE[ssSB](../../includes/sssb-md.md)] na lista de runtime.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-276">It searches for [!INCLUDE[ssSB](../../includes/sssb-md.md)] events that indicate an error was encountered by one or more of the [!INCLUDE[ssSB](../../includes/sssb-md.md)] IDs in the runtime list.</span></span> <span data-ttu-id="3c1b4-277">O**ssbdiagnose** também procura eventos de erro do [!INCLUDE[ssSB](../../includes/sssb-md.md)] no nível do sistema não especificamente associados a nenhum grupo de conversa.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-277">**ssbdiagnose** also searches for system-level [!INCLUDE[ssSB](../../includes/sssb-md.md)] error events not specifically associated with any conversation group.</span></span>  
  
 <span data-ttu-id="3c1b4-278">Se **ssbdiagnose** localizar erros na conversa, o utilitário relatar a causa raiz dos eventos executando também um relatório de configuração.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-278">If **ssbdiagnose** finds conversation errors, the utility will attempt to report on the root cause of the events by also running a configuration report.</span></span> <span data-ttu-id="3c1b4-279">**ssbdiagnose** usa os metadados dos bancos de dados para tentar determinar as instâncias, as IDs do [!INCLUDE[ssSB](../../includes/sssb-md.md)] , os bancos de dados, os serviços e os contratos usados pela conversa.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-279">**ssbdiagnose** uses the metadata in the databases to try to determine the instances, [!INCLUDE[ssSB](../../includes/sssb-md.md)] IDs, databases, services, and contracts used by the conversation.</span></span> <span data-ttu-id="3c1b4-280">Em seguida, executa um relatório de configuração que usa todas as informações disponíveis.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-280">It then runs a configuration report using all available information.</span></span>  
  
 <span data-ttu-id="3c1b4-281">Por padrão, **ssbdiagnose** não relata eventos de erro.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-281">By default, **ssbdiagnose** does not report error events.</span></span> <span data-ttu-id="3c1b4-282">O utilitário só reporta os problemas subjacentes encontrados durante a verificação de configuração.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-282">It only reports the underlying issues found during the configuration check.</span></span> <span data-ttu-id="3c1b4-283">Isso minimiza a quantidade de informações reportadas e lhe ajuda a enfatizar os problemas de configuração subjacentes.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-283">This minimizes the amount of information reported and helps you focus on the underlying configuration issues.</span></span> <span data-ttu-id="3c1b4-284">Você pode especificar **-SHOWEVENTS** para ver os eventos de erro encontrados por **ssbdiagnose**.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-284">You can specify **-SHOWEVENTS** to see the error events encountered by **ssbdiagnose**.</span></span>  
  
## <a name="issues-reported-by-ssbdiagnose"></a><span data-ttu-id="3c1b4-285">Problemas reportados por ssbdiagnose</span><span class="sxs-lookup"><span data-stu-id="3c1b4-285">Issues Reported by ssbdiagnose</span></span>  
 <span data-ttu-id="3c1b4-286">**ssbdiagnose** relata três classes de problemas.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-286">**ssbdiagnose** reports three classes of issues.</span></span> <span data-ttu-id="3c1b4-287">No arquivo de saída XML, cada classe de problema é reportada como um tipo separado de elemento Issue.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-287">In the XML output file, each class of issue is reported as a separate type of the Issue element.</span></span> <span data-ttu-id="3c1b4-288">Os três tipos de problemas relatados por **ssbdiagnose** são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="3c1b4-288">The three types of issues reported by **ssbdiagnose** are as follows:</span></span>  
  
 <span data-ttu-id="3c1b4-289">**Diagnóstico**</span><span class="sxs-lookup"><span data-stu-id="3c1b4-289">**Diagnosis**</span></span>  
 <span data-ttu-id="3c1b4-290">Reporta um problema de configuração.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-290">Reports a configuration issue.</span></span> <span data-ttu-id="3c1b4-291">Isso inclui os problemas encontrados durante a execução de relatório **CONFIGURATION** ou na fase de configuração de um relatório **RUNTIME** .</span><span class="sxs-lookup"><span data-stu-id="3c1b4-291">This includes issues found either a **CONFIGURATION** report is running, or during the configuration phase of a **RUNTIME** report.</span></span> <span data-ttu-id="3c1b4-292">**ssbdiagnose** relata cada problema de configuração uma vez.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-292">**ssbdiagnose** reports each configuration issue one time.</span></span>  
  
 <span data-ttu-id="3c1b4-293">**Evento**</span><span class="sxs-lookup"><span data-stu-id="3c1b4-293">**Event**</span></span>  
 <span data-ttu-id="3c1b4-294">Relata um evento [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] que indica que um problema foi encontrado por uma conversa monitorada durante um relatório **RUNTIME** .</span><span class="sxs-lookup"><span data-stu-id="3c1b4-294">Reports a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] event that indicates a problem was encountered by a conversation being monitored during a **RUNTIME** report.</span></span> <span data-ttu-id="3c1b4-295">**ssbdiagnose** relata eventos toda vez que eles são gerados.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-295">**ssbdiagnose** reports events every time they are generated.</span></span> <span data-ttu-id="3c1b4-296">Os eventos poderão ser reportados várias vezes se várias conversas encontrarem o problema.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-296">Events can be reported multiple times if several conversations encounter the problem.</span></span>  
  
 <span data-ttu-id="3c1b4-297">**Problema**</span><span class="sxs-lookup"><span data-stu-id="3c1b4-297">**Problem**</span></span>  
 <span data-ttu-id="3c1b4-298">Relata um problema que está impedindo o **ssbdiagnose** de concluir uma análise de configuração ou de monitorar conversas.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-298">Reports an issue that is preventing **ssbdiagnose** from completing a configuration analysis or from monitoring conversations.</span></span>  
  
## <a name="sqlcmd-environment-variables"></a><span data-ttu-id="3c1b4-299">Variáveis de ambiente sqlcmd</span><span class="sxs-lookup"><span data-stu-id="3c1b4-299">sqlcmd Environment Variables</span></span>  
 <span data-ttu-id="3c1b4-300">O utilitário **ssbdiagnose** dá suporte às variáveis de ambiente SQLCMDSERVER, SQLCMDUSER, SQLCMDPASSWORD e SQLCMDLOGINTIMOUT que também são usadas pelo utilitário **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="3c1b4-300">The **ssbdiagnose** utility supports the SQLCMDSERVER, SQLCMDUSER, SQLCMDPASSWORD, and SQLCMDLOGINTIMOUT environment variables that are also used by the **sqlcmd** utility.</span></span> <span data-ttu-id="3c1b4-301">Você pode definir as variáveis de ambiente usando o comando SET de prompt de comando ou o comando **setvar** em scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] que executa com o uso de **sqlcmd**.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-301">You can set the environment variables either by using the command prompt SET command, or by using the **setvar** command in [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts that you run by using **sqlcmd**.</span></span> <span data-ttu-id="3c1b4-302">Para obter mais informações sobre como usar **setvar** no **sqlcmd**, veja [Usar sqlcmd com variáveis de script](../../relational-databases/scripting/sqlcmd-use-with-scripting-variables.md).</span><span class="sxs-lookup"><span data-stu-id="3c1b4-302">For more information about how to use **setvar** in **sqlcmd**, see [Use sqlcmd with Scripting Variables](../../relational-databases/scripting/sqlcmd-use-with-scripting-variables.md).</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="3c1b4-303">Permissões</span><span class="sxs-lookup"><span data-stu-id="3c1b4-303">Permissions</span></span>  
 <span data-ttu-id="3c1b4-304">Em cada cláusula **connectionoptions** , o logon especificado com **-E** ou **-U** deve ser membro da função de servidor fixa **sysadmin** na instância especificada em **-S**.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-304">In each **connectionoptions** clause, the login specified with either **-E** or **-U** must be a member of the **sysadmin** fixed-server role in the instance specified in **-S**.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="3c1b4-305">Exemplos</span><span class="sxs-lookup"><span data-stu-id="3c1b4-305">Examples</span></span>  
 <span data-ttu-id="3c1b4-306">Esta seção contém exemplos do uso de **ssbdiagnose** em um prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-306">This section contains examples of using **ssbdiagnose** at a command prompt.</span></span>  
  
### <a name="a-checking-the-configuration-of-two-services-in-the-same-database"></a><span data-ttu-id="3c1b4-307">a.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-307">A.</span></span> <span data-ttu-id="3c1b4-308">Verificando a configuração de dois serviços no mesmo banco de dados</span><span class="sxs-lookup"><span data-stu-id="3c1b4-308">Checking the Configuration of Two Services in the Same Database</span></span>  
 <span data-ttu-id="3c1b4-309">O exemplo a seguir mostra como solicitar um relatório de configuração quando estas condições são verdadeiras:</span><span class="sxs-lookup"><span data-stu-id="3c1b4-309">The following example shows how to request a configuration report when the following are true;</span></span>  
  
-   <span data-ttu-id="3c1b4-310">Os serviços iniciador e de destino estão no mesmo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-310">The initiator and target service are in the same database.</span></span>  
  
-   <span data-ttu-id="3c1b4-311">O banco de dados está na instância padrão do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c1b4-311">The database is in the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="3c1b4-312">As instâncias estão no mesmo computador em que **ssbdiagnose** é executado.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-312">The instances is on the same computer on which **ssbdiagnose** is run.</span></span>  
  
 <span data-ttu-id="3c1b4-313">O utilitário **ssbdiagnose** relata a configuração que usa o contrato DEFAULT porque ON CONTRACT não foi especificado.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-313">The **ssbdiagnose** utility reports the configuration that uses the DEFAULT contract because ON CONTRACT is not specified.</span></span>  
  
```  
ssbdiagnose -E -d MyDatabase CONFIGURATION FROM SERVICE /test/initiator TO SERVICE /test/target  
```  
  
### <a name="b-checking-the-configuration-of-two-services-on-separate-computers-that-use-one-login"></a><span data-ttu-id="3c1b4-314">B.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-314">B.</span></span> <span data-ttu-id="3c1b4-315">Verificando a configuração de dois serviços em computadores separados que não usam logon</span><span class="sxs-lookup"><span data-stu-id="3c1b4-315">Checking the Configuration of Two Services on Separate Computers That Use One Login</span></span>  
 <span data-ttu-id="3c1b4-316">O exemplo a seguir mostra como solicitar um relatório de configuração quando os serviços iniciador e de destino estão em computadores separados, mas podem ser acessados com o uso do mesmo logon de Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-316">The following example shows how to request a configuration report when the initiator and target service are on separate computers, but can be accessed by using the same Windows Authentication login.</span></span>  
  
```  
ssbdiagnose -E CONFIGURATION FROM SERVICE /text/initiator -S InitiatorComputer -d InitiatorDatabase TO SERVICE /test/target -S TargetComputer -d TargetDatabase ON CONTRACT TestContract  
```  
  
### <a name="c-checking-the-configuration-of-two-services-on-separate-computers-that-use-separate-logins"></a><span data-ttu-id="3c1b4-317">C.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-317">C.</span></span> <span data-ttu-id="3c1b4-318">Verificando a configuração de dois serviços em computadores separados que usam logons diferentes</span><span class="sxs-lookup"><span data-stu-id="3c1b4-318">Checking the Configuration of Two Services on Separate Computers That Use Separate Logins</span></span>  
 <span data-ttu-id="3c1b4-319">O exemplo a seguir mostra como solicitar um relatório de configuração quando os serviços iniciador e de destino estão em computadores separados, e logons de Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] diferentes são necessários para cada instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c1b4-319">The following example shows how to request a configuration report when the initiator and target service are on separate computers, and separate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication logins are required for each instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
```  
ssbdiagnose CONFIGURATION FROM SERVICE /text/initiator   
-S InitiatorComputer -U InitiatorLogin -p !wEx23Dvb   
-d InitiatorDatabase TO SERVICE /test/target -S TargetComputer   
-U TargetLogin -p ER!49jiy -d TargetDatabase ON CONTRACT TestContract  
```  
  
### <a name="d-checking-mirrored-service-configurations-on-separate-computers-with-anonymous-encryption"></a><span data-ttu-id="3c1b4-320">D.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-320">D.</span></span> <span data-ttu-id="3c1b4-321">Verificando configurações de serviços espelhados em computadores separados com criptografia anônima</span><span class="sxs-lookup"><span data-stu-id="3c1b4-321">Checking Mirrored Service Configurations on Separate Computers With Anonymous Encryption</span></span>  
 <span data-ttu-id="3c1b4-322">O exemplo a seguir mostra como solicitar um relatório de configuração quando os serviços iniciador e de destino estão em computadores separados e o iniciador é espelhado para uma instância nomeada.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-322">The following example shows how to request a configuration report when the initiator and target service are on separate computers and the initiator is mirrored to a named instance.</span></span> <span data-ttu-id="3c1b4-323">O relatório também verifica se os serviços estão configurados para usar criptografia anônima.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-323">The report also verifies that the services are configured to use anonymous encryption.</span></span>  
  
```  
ssbdiagnose -E CONFIGURATION FROM SERVICE /text/initiator   
-S InitiatorComputer -d InitiatorDatabase MIRROR   
-S MirrorComputer/MirrorInstance TO SERVICE /test/target   
-S TargetComputer -d TargetDatabase ON CONTRACT TestContract ENCRYPTION ANONYMOUS  
```  
  
### <a name="e-checking-the-configuration-of-two-contracts"></a><span data-ttu-id="3c1b4-324">E.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-324">E.</span></span> <span data-ttu-id="3c1b4-325">Verificando a configuração de dois contratos</span><span class="sxs-lookup"><span data-stu-id="3c1b4-325">Checking the Configuration of Two Contracts</span></span>  
 <span data-ttu-id="3c1b4-326">O exemplo a seguir mostra como criar um arquivo de comando que solicite relatórios de configuração quando estas condições forem verdadeiras:</span><span class="sxs-lookup"><span data-stu-id="3c1b4-326">The following example shows how to build a command file that requests configuration reports when the following are true:</span></span>  
  
-   <span data-ttu-id="3c1b4-327">Os serviços iniciador e de destino estão no mesmo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-327">The initiator and target service are in the same database.</span></span>  
  
-   <span data-ttu-id="3c1b4-328">O banco de dados está na instância padrão do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c1b4-328">The database is in the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="3c1b4-329">A instância está no mesmo computador em que **ssbdiagnose** é executado.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-329">The instance is on the same computer on which **ssbdiagnose** is run.</span></span>  
  
 <span data-ttu-id="3c1b4-330">Cada vez que **ssbdiagnose** é executado, o utilitário relata a configuração de um contrato diferente entre os mesmos serviços.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-330">Each time **ssbdiagnose** is run it reports the configuration for a different contract between the same services.</span></span>  
  
```  
ssbdiagnose -E -d MyDatabase CONFIGURATION FROM SERVICE   
/test/initiator TO SERVICE /test/target ON CONTRACT PayRaiseContract  
ssbdiagnose -E -d MyDatabase CONFIGURATION FROM SERVICE /test/initiator   
TO SERVICE /test/target ON CONTRACT PromotionContract  
```  
  
### <a name="f-monitor-the-status-of-a-specific-conversation-on-the-local-computer-with-a-time-out"></a><span data-ttu-id="3c1b4-331">F.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-331">F.</span></span> <span data-ttu-id="3c1b4-332">Monitorar o status de uma conversa específica no computador local com um tempo limite</span><span class="sxs-lookup"><span data-stu-id="3c1b4-332">Monitor the status of a specific conversation on the local computer with a time out</span></span>  
 <span data-ttu-id="3c1b4-333">O exemplo a seguir mostra como monitorar uma conversa específica em que os serviços iniciador e de destino estão no mesmo banco de dados na instância padrão do mesmo computador que está executando **ssbdiagnose**.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-333">The following example shows how to monitor a specific conversation where the initiator and target services are in the same database in the default instance of the same computer that is running **ssbdiagnose**.</span></span> <span data-ttu-id="3c1b4-334">O intervalo de tempo limite é definido como 20 segundos.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-334">The time-out interval is set to 20 seconds.</span></span>  
  
```  
ssbdiagnose -E -d TestDatabase RUNTIME -ID D68D77A9-B1CF-41BF-A5CE-279ABCAB140D -TIMEOUT 20  
```  
  
### <a name="g-monitor-the-status-of-a-conversation-that-spans-two-computers"></a><span data-ttu-id="3c1b4-335">G.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-335">G.</span></span> <span data-ttu-id="3c1b4-336">Monitorar o status de uma conversa que abrange dois computadores</span><span class="sxs-lookup"><span data-stu-id="3c1b4-336">Monitor the status of a conversation that spans two computers</span></span>  
 <span data-ttu-id="3c1b4-337">O exemplo a seguir mostra como monitorar uma conversa específica na qual os serviços iniciador e de destino estão em computadores separados.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-337">The following example shows how to monitor a specific conversation where the initiator and target services are on separate computers.</span></span>  
  
```  
ssbdiagnose RUNTIME -ID D68D77A9-B1CF-41BF-A5CE-279ABCAB140D   
-TIMEOUT 10 CONNECT TO -E -S InitiatorComputer/InitiatorInstance   
-d InitiatorDatabase CONNECT TO -E -S TargetComputer/TargetInstance   
-d TargetDatabase  
```  
  
### <a name="h-monitor-the-status-of-a-conversation-in-two-databases-in-the-same-instance"></a><span data-ttu-id="3c1b4-338">H.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-338">H.</span></span> <span data-ttu-id="3c1b4-339">Monitorar o status de uma conversa em dois bancos de dados na mesma instância</span><span class="sxs-lookup"><span data-stu-id="3c1b4-339">Monitor the status of a conversation in two databases in the same instance</span></span>  
 <span data-ttu-id="3c1b4-340">O exemplo a seguir mostra como monitorar uma conversa específica na qual os serviços iniciador e de destino estão em bancos de dados separados na mesma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c1b4-340">The following example shows how to monitor a specific conversation where the initiator and target services are in separate databases in the same instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="3c1b4-341">O exemplo usa **baseconnectionoptions** para especificar as informações de instância e logon e duas cláusulas CONNECT TO para especificar os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-341">The example uses the **baseconnectionoptions** to specify the instance and login information, and two CONNECT TO clauses to specify the databases.</span></span> <span data-ttu-id="3c1b4-342">-SHOWEVENTS é especificada para que todos os eventos de runtime sejam incluídos na saída do relatório.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-342">-SHOWEVENTS is specified so that all runtime events are included in the report output.</span></span>  
  
```  
ssbdiagnose -E -S TestComputer/DevTestInstance RUNTIME -SHOWEVENTS   
-ID 5094d4a7-e38c-4c37-da37-1d58b1cb8455 -TIMEOUT 10 CONNECT TO   
-d InitiatorDatabase CONNECT TO -d TargetDatabase  
```  
  
### <a name="i-monitor-the-status-of-two-conversations-between-two-databases"></a><span data-ttu-id="3c1b4-343">I.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-343">I.</span></span> <span data-ttu-id="3c1b4-344">Monitorar o status de duas conversas entre dois bancos de dados</span><span class="sxs-lookup"><span data-stu-id="3c1b4-344">Monitor the status of two conversations between two databases</span></span>  
 <span data-ttu-id="3c1b4-345">O exemplo a seguir mostra como monitorar duas conversas nas quais os serviços iniciador e de destino estão em bancos de dados separados na mesma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c1b4-345">The following example shows how to monitor two conversations where the initiator and target services are in separate databases in the same instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="3c1b4-346">O exemplo usa **baseconnectionoptions** para especificar as informações de instância e logon e duas cláusulas CONNECT TO para especificar os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-346">The example uses the **baseconnectionoptions** to specify the instance and login information, and two CONNECT TO clauses to specify the databases.</span></span>  
  
```  
ssbdiagnose -E -S TestComputer/DevTestInstance RUNTIME   
-ID 5094d4a7-e38c-4c37-da37-1d58b1cb8455   
-ID 9b293be9-226b-4e22-e169-1d2c2c15be86 -TIMEOUT 10 CONNECT TO   
-d InitiatorDatabase CONNECT TO -d TargetDatabase  
```  
  
### <a name="j-monitor-the-status-of-all-conversations-between-two-databases"></a><span data-ttu-id="3c1b4-347">J.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-347">J.</span></span> <span data-ttu-id="3c1b4-348">Monitorar o status de todas as conversas entre dois bancos de dados</span><span class="sxs-lookup"><span data-stu-id="3c1b4-348">Monitor the status of all conversations between two databases</span></span>  
 <span data-ttu-id="3c1b4-349">O exemplo a seguir mostra como monitorar todas as conversas entre dois bancos de dados na mesma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c1b4-349">The following example shows how to monitor all the conversation between two databases in the same instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="3c1b4-350">O exemplo usa **baseconnectionoptions** para especificar as informações de instância e logon e duas cláusulas CONNECT TO para especificar os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-350">The example uses the **baseconnectionoptions** to specify the instance and login information, and two CONNECT TO clauses to specify the databases.</span></span>  
  
```  
ssbdiagnose -E -S TestComputer/DevTestInstance RUNTIME   
-TIMEOUT 10 CONNECT TO -d InitiatorDatabase CONNECT TO   
-d TargetDatabase  
```  
  
### <a name="k-ignore-specific-errors"></a><span data-ttu-id="3c1b4-351">K.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-351">K.</span></span> <span data-ttu-id="3c1b4-352">Ignorar erros específicos</span><span class="sxs-lookup"><span data-stu-id="3c1b4-352">Ignore Specific Errors</span></span>  
 <span data-ttu-id="3c1b4-353">O exemplo a seguir mostra como ignorar erros conhecidos (303 e 304) no modo com a ativação está configurada atualmente em um sistema de teste.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-353">The following example shows how to ignore known errors (303 and 304) in how activation is currently configured in a test system.</span></span>  
  
```  
ssbdiagnose -IGNORE 303 -IGNORE 304 -E -d TestDatabase   
CONFIGURATION FROM SERVICE /test/initiator TO SERVICE /test/target   
ON CONTRACT TextContract  
```  
  
### <a name="l-redirecting-ssbdiagnose-xml-output"></a><span data-ttu-id="3c1b4-354">L.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-354">L.</span></span> <span data-ttu-id="3c1b4-355">Redirecionando a saída XML de ssbdiagnose</span><span class="sxs-lookup"><span data-stu-id="3c1b4-355">Redirecting ssbdiagnose XML Output</span></span>  
 <span data-ttu-id="3c1b4-356">O exemplo a seguir mostra como solicitar que o **ssbdiagnose** gere sua saída como um arquivo XML redirecionado para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-356">The following example shows how to request that **ssbdiagnose** generate its output as an XML file that is redirected to a file.</span></span> <span data-ttu-id="3c1b4-357">O arquivo TestDiag.xml pode ser aberto por um aplicativo para analisar ou relatar arquivos XML do **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="3c1b4-357">The TestDiag.xml file can then be opened by an application to analyze or report **ssbdiagnose** XML files.</span></span> <span data-ttu-id="3c1b4-358">Se preferir, você pode exibi-lo de um editor de XML geral como o Bloco de Notas XML.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-358">Or, you can view it from a general XML editor such as XML Notepad.</span></span>  
  
```  
ssbdiagnose -XML -E -d MyDatabase CONFIGURATION FROM SERVICE   
/test/initiator TO SERVICE /test/target > c:\MyDiagnostics\TestDiag.xml  
```  
  
### <a name="m-using-an-environment-variable"></a><span data-ttu-id="3c1b4-359">M.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-359">M.</span></span> <span data-ttu-id="3c1b4-360">Usando uma variável de ambiente</span><span class="sxs-lookup"><span data-stu-id="3c1b4-360">Using an Environment Variable</span></span>  
 <span data-ttu-id="3c1b4-361">O exemplo a seguir define primeiramente a variável de ambiente SQLCMDSERVER para conter o nome do servidor e executa **ssbdiagnose** sem especificar **-S**.</span><span class="sxs-lookup"><span data-stu-id="3c1b4-361">The following example first sets the SQLCMDSERVER environment variable to hold the server name, and then runs **ssbdiagnose** without specifying **-S**.</span></span>  
  
```  
SET SQLCMDSERVER=MyComputer  
ssbdiagnose -XML -E -d MyDatabase CONFIGURATION FROM SERVICE   
/test/initiator TO SERVICE /test/target  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c1b4-362">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3c1b4-362">See Also</span></span>  
 <span data-ttu-id="3c1b4-363">[SQL Server Service Broker](../../database-engine/configure-windows/sql-server-service-broker.md) </span><span class="sxs-lookup"><span data-stu-id="3c1b4-363">[SQL Server Service Broker](../../database-engine/configure-windows/sql-server-service-broker.md) </span></span>  
 <span data-ttu-id="3c1b4-364">[BEGIN DIALOG CONVERSATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/begin-dialog-conversation-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3c1b4-364">[BEGIN DIALOG CONVERSATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/begin-dialog-conversation-transact-sql) </span></span>  
 <span data-ttu-id="3c1b4-365">[CREATE BROKER PRIORITY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-broker-priority-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3c1b4-365">[CREATE BROKER PRIORITY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-broker-priority-transact-sql) </span></span>  
 <span data-ttu-id="3c1b4-366">[CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3c1b4-366">[CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql) </span></span>  
 <span data-ttu-id="3c1b4-367">[CREATE CONTRACT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-contract-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3c1b4-367">[CREATE CONTRACT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-contract-transact-sql) </span></span>  
 <span data-ttu-id="3c1b4-368">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3c1b4-368">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="3c1b4-369">[CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3c1b4-369">[CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) </span></span>  
 <span data-ttu-id="3c1b4-370">[CREATE MESSAGE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-message-type-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3c1b4-370">[CREATE MESSAGE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-message-type-transact-sql) </span></span>  
 <span data-ttu-id="3c1b4-371">[CREATE QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-queue-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3c1b4-371">[CREATE QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-queue-transact-sql) </span></span>  
 <span data-ttu-id="3c1b4-372">[CREATE REMOTE SERVICE BINDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-remote-service-binding-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3c1b4-372">[CREATE REMOTE SERVICE BINDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-remote-service-binding-transact-sql) </span></span>  
 <span data-ttu-id="3c1b4-373">[CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3c1b4-373">[CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql) </span></span>  
 <span data-ttu-id="3c1b4-374">[CREATE SERVICE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-service-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3c1b4-374">[CREATE SERVICE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-service-transact-sql) </span></span>  
 <span data-ttu-id="3c1b4-375">[RECEIVE &#40;Transact-SQL&#41;](/sql/t-sql/statements/receive-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3c1b4-375">[RECEIVE &#40;Transact-SQL&#41;](/sql/t-sql/statements/receive-transact-sql) </span></span>  
 <span data-ttu-id="3c1b4-376">[sys.transmission_queue &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-transmission-queue-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3c1b4-376">[sys.transmission_queue &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-transmission-queue-transact-sql) </span></span>  
 <span data-ttu-id="3c1b4-377">[sys.conversation_endpoints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-conversation-endpoints-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3c1b4-377">[sys.conversation_endpoints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-conversation-endpoints-transact-sql) </span></span>  
 [<span data-ttu-id="3c1b4-378">sys.conversation_groups &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3c1b4-378">sys.conversation_groups &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-conversation-groups-transact-sql)  
  
  
