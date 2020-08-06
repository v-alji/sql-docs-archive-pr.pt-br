---
title: Arquivo de configuração ReportingServicesService | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- traces [Reporting Services]
- Report Server Windows service, ReportingServicesService configuration file
- ReportingServicesService configuration file
ms.assetid: 40f4a401-cb61-4c42-b1ec-01acdacdacd1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5124631db9635211827dd3b1abbff7116101a61d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574491"
---
# <a name="reportingservicesservice-configuration-file"></a><span data-ttu-id="117ba-102">arquivo de configuração ReportingServicesService</span><span class="sxs-lookup"><span data-stu-id="117ba-102">ReportingServicesService Configuration File</span></span>
  <span data-ttu-id="117ba-103">O arquivo ReportingServicesService.exe.config inclui configurações de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="117ba-103">The ReportingServicesService.exe.config file includes settings that configure tracing.</span></span>  
  
## <a name="file-location"></a><span data-ttu-id="117ba-104">Localização do arquivo</span><span class="sxs-lookup"><span data-stu-id="117ba-104">File Location</span></span>  
 <span data-ttu-id="117ba-105">Este arquivo está localizado na pasta \Reporting Services\Report Server\Bin.</span><span class="sxs-lookup"><span data-stu-id="117ba-105">This file is located in the \Reporting Services\Report Server\Bin folder.</span></span>  
  
## <a name="editing-guidelines"></a><span data-ttu-id="117ba-106">Editando diretrizes</span><span class="sxs-lookup"><span data-stu-id="117ba-106">Editing Guidelines</span></span>  
 <span data-ttu-id="117ba-107">Você pode modificar este arquivo para renomear o arquivo de log ou aumentar ou diminuir níveis de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="117ba-107">You can modify this file to rename the log file or to increase or decrease trace levels.</span></span> <span data-ttu-id="117ba-108">Não modifique nenhuma outra configuração.</span><span class="sxs-lookup"><span data-stu-id="117ba-108">Do not modify any of the other settings.</span></span> <span data-ttu-id="117ba-109">Para obter instruções, consulte [Modificar um arquivo de configuração do Reporting Services &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span><span class="sxs-lookup"><span data-stu-id="117ba-109">For instructions, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span></span> <span data-ttu-id="117ba-110">Para obter mais informações sobre logs de rastreamento, consulte [Log de rastreamento do serviço Servidor de Relatório](report-server-service-trace-log.md).</span><span class="sxs-lookup"><span data-stu-id="117ba-110">For more information about trace logs, see [Report Server Service Trace Log](report-server-service-trace-log.md).</span></span>  
  
## <a name="example-configuration"></a><span data-ttu-id="117ba-111">Exemplo de Configuração</span><span class="sxs-lookup"><span data-stu-id="117ba-111">Example Configuration</span></span>  
 <span data-ttu-id="117ba-112">O exemplo a seguir mostra as configurações e os valores padrão localizados no arquivo ReportingServicesService.exe.config.</span><span class="sxs-lookup"><span data-stu-id="117ba-112">The following example shows the settings and default values found in the ReportingServicesService.exe.config file.</span></span>  
  
```  
<configSections>  
      <section name="RStrace" type="Microsoft.ReportingServices.Diagnostics.RSTraceSectionHandler,Microsoft.ReportingServices.Diagnostics" />  
</configSections>  
<system.diagnostics>  
      <switches>  
          <add name="DefaultTraceSwitch" value="3" />  
      </switches>  
</system.diagnostics>  
<RStrace>  
      <add name="FileName" value="ReportServerService_" />  
      <add name="FileSizeLimitMb" value="32" />  
      <add name="KeepFilesForDays" value="14" />  
      <add name="Prefix" value="tid, time" />  
      <add name="TraceListeners" value="debugwindow, file" />  
      <add name="TraceFileMode" value="unique" />  
      <add name="Components" value="all" />  
</RStrace>  
<runtime>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
             <dependentAssembly>  
                    <assemblyIdentity name="Microsoft.ReportingServices.Interfaces"  
                        publicKeyToken="89845dcd8080cc91"  
                        culture="neutral" />  
                    <bindingRedirect oldVersion="8.0.242.0"  
                                     newVersion="10.0.0.0"/>  
                    <bindingRedirect oldVersion="9.0.242.0"  
                                     newVersion="10.0.0.0"/>  
             </dependentAssembly>  
      </assemblyBinding>  
      <gcServer enabled="true" />  
</runtime>  
```  
  
## <a name="configuration-settings"></a><span data-ttu-id="117ba-113">Definições de configuração</span><span class="sxs-lookup"><span data-stu-id="117ba-113">Configuration Settings</span></span>  
 <span data-ttu-id="117ba-114">A tabela a seguir fornece informações sobre configurações específicas.</span><span class="sxs-lookup"><span data-stu-id="117ba-114">The following table provides information about specific settings.</span></span> <span data-ttu-id="117ba-115">As configurações são apresentadas na ordem em que aparecem no arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="117ba-115">Settings are presented in the order in which they appear in the configuration file.</span></span>  
  
|<span data-ttu-id="117ba-116">Configuração</span><span class="sxs-lookup"><span data-stu-id="117ba-116">Setting</span></span>|<span data-ttu-id="117ba-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="117ba-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="117ba-118">**RStrace**</span><span class="sxs-lookup"><span data-stu-id="117ba-118">**RStrace**</span></span>|<span data-ttu-id="117ba-119">Especifica os namespaces usados para erros e rastreamento.</span><span class="sxs-lookup"><span data-stu-id="117ba-119">Specifies namespaces used for errors and tracing.</span></span>|  
|<span data-ttu-id="117ba-120">**DefaultTraceSwitch**</span><span class="sxs-lookup"><span data-stu-id="117ba-120">**DefaultTraceSwitch**</span></span>|<span data-ttu-id="117ba-121">Especifica o nível de informações que é relatado no log de rastreamento ReportServerService.</span><span class="sxs-lookup"><span data-stu-id="117ba-121">Specifies the level of information that is reported to the ReportServerService trace log.</span></span> <span data-ttu-id="117ba-122">Cada nível inclui as informações relatadas por todos os níveis de baixa numeração.</span><span class="sxs-lookup"><span data-stu-id="117ba-122">Each level includes the information reported by all lower-numbered levels.</span></span> <span data-ttu-id="117ba-123">A desabilitação do rastreamento não é recomendada.</span><span class="sxs-lookup"><span data-stu-id="117ba-123">Disabling tracing is not recommended.</span></span> <span data-ttu-id="117ba-124">Os valores válidos incluem:</span><span class="sxs-lookup"><span data-stu-id="117ba-124">Valid values include:</span></span><br /><br /> <span data-ttu-id="117ba-125">0 = Desabilita o rastreamento</span><span class="sxs-lookup"><span data-stu-id="117ba-125">0= Disables tracing</span></span><br /><br /> <span data-ttu-id="117ba-126">1 = Exceções e reinicializações</span><span class="sxs-lookup"><span data-stu-id="117ba-126">1= Exceptions and restarts</span></span><br /><br /> <span data-ttu-id="117ba-127">2 = Exceções, reinicializações, avisos</span><span class="sxs-lookup"><span data-stu-id="117ba-127">2= Exceptions, restarts, warnings</span></span><br /><br /> <span data-ttu-id="117ba-128">3 = Exceções, reinicializações, avisos, mensagens de status (padrão)</span><span class="sxs-lookup"><span data-stu-id="117ba-128">3= Exceptions, restarts, warnings, status messages (default)</span></span><br /><br /> <span data-ttu-id="117ba-129">4 = Modo detalhado</span><span class="sxs-lookup"><span data-stu-id="117ba-129">4= Verbose mode</span></span>|  
|<span data-ttu-id="117ba-130">**FileName**</span><span class="sxs-lookup"><span data-stu-id="117ba-130">**FileName**</span></span>|<span data-ttu-id="117ba-131">Especifica a primeira parte do nome de arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="117ba-131">Specifies the first portion of the log file name.</span></span> <span data-ttu-id="117ba-132">O valor especificado por `Prefix` completa o resto do nome.</span><span class="sxs-lookup"><span data-stu-id="117ba-132">The value specified by `Prefix` completes the rest of the name.</span></span> <span data-ttu-id="117ba-133">Por padrão, o nome é ReportServerService_.</span><span class="sxs-lookup"><span data-stu-id="117ba-133">By default, the name is ReportServerService_.</span></span>|  
|<span data-ttu-id="117ba-134">**FileSizeLimitMb**</span><span class="sxs-lookup"><span data-stu-id="117ba-134">**FileSizeLimitMb**</span></span>|<span data-ttu-id="117ba-135">Especifica o limite superior do tamanho do log de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="117ba-135">Specifies an upper limit on trace log size.</span></span> <span data-ttu-id="117ba-136">O arquivo é medido em megabytes.</span><span class="sxs-lookup"><span data-stu-id="117ba-136">The file is measured in megabytes.</span></span> <span data-ttu-id="117ba-137">Os valores válidos são de 0 a um inteiro máximo.</span><span class="sxs-lookup"><span data-stu-id="117ba-137">Valid values are 0 to a maximum integer.</span></span> <span data-ttu-id="117ba-138">O valor padrão é 32.</span><span class="sxs-lookup"><span data-stu-id="117ba-138">The default value is 32.</span></span>|  
|<span data-ttu-id="117ba-139">**KeepFilesForDays**</span><span class="sxs-lookup"><span data-stu-id="117ba-139">**KeepFilesForDays**</span></span>|<span data-ttu-id="117ba-140">Especifica o número de dias depois dos quais um arquivo de log de rastreamento será excluído.</span><span class="sxs-lookup"><span data-stu-id="117ba-140">Specifies the number of days after which a trace log file will be deleted.</span></span> <span data-ttu-id="117ba-141">Os valores válidos são de 0 a um inteiro máximo.</span><span class="sxs-lookup"><span data-stu-id="117ba-141">Valid values are 0 to a maximum integer.</span></span> <span data-ttu-id="117ba-142">O valor padrão é 14.</span><span class="sxs-lookup"><span data-stu-id="117ba-142">The default value is 14.</span></span>|  
|`Prefix`|<span data-ttu-id="117ba-143">Especifica um valor gerado que diferencia uma instância de log de outra.</span><span class="sxs-lookup"><span data-stu-id="117ba-143">Specifies a generated value that distinguishes one log instance from another.</span></span> <span data-ttu-id="117ba-144">Por padrão, os valores do carimbo de data/hora são adicionados aos nomes de arquivo de log de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="117ba-144">By default, timestamp values are appended to trace log file names.</span></span> <span data-ttu-id="117ba-145">Esse valor é definido como " tid, time ".</span><span class="sxs-lookup"><span data-stu-id="117ba-145">This value is set to " tid, time ".</span></span> <span data-ttu-id="117ba-146">Não modifique esta configuração.</span><span class="sxs-lookup"><span data-stu-id="117ba-146">Do not modify this setting.</span></span>|  
|<span data-ttu-id="117ba-147">**TraceListeners**</span><span class="sxs-lookup"><span data-stu-id="117ba-147">**TraceListeners**</span></span>|<span data-ttu-id="117ba-148">Especifica um destino para a saída do conteúdo do log de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="117ba-148">Specifies a target for outputting trace log content.</span></span> <span data-ttu-id="117ba-149">Você pode especificar vários destinos usando uma vírgula para separar cada um.</span><span class="sxs-lookup"><span data-stu-id="117ba-149">You can specify multiple targets using a comma to separate each one.</span></span> <span data-ttu-id="117ba-150">Os valores válidos incluem:</span><span class="sxs-lookup"><span data-stu-id="117ba-150">Valid values include:</span></span><br /><br /> <span data-ttu-id="117ba-151">DebugWindow (padrão)</span><span class="sxs-lookup"><span data-stu-id="117ba-151">DebugWindow (default)</span></span><br /><br /> <span data-ttu-id="117ba-152">File (padrão)</span><span class="sxs-lookup"><span data-stu-id="117ba-152">File (default)</span></span><br /><br /> <span data-ttu-id="117ba-153">StdOut</span><span class="sxs-lookup"><span data-stu-id="117ba-153">StdOut</span></span>|  
|<span data-ttu-id="117ba-154">**TraceFileMode**</span><span class="sxs-lookup"><span data-stu-id="117ba-154">**TraceFileMode**</span></span>|<span data-ttu-id="117ba-155">Especifica se os logs de rastreamento contêm dados para um período de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="117ba-155">Specifies whether trace logs contain data for a 24-hour period.</span></span> <span data-ttu-id="117ba-156">Um log de rastreamento exclusivo deve existir para cada componente em cada dia.</span><span class="sxs-lookup"><span data-stu-id="117ba-156">You should have one unique trace log for each component on each day.</span></span> <span data-ttu-id="117ba-157">Esse valor é definido como "Unique (default)".</span><span class="sxs-lookup"><span data-stu-id="117ba-157">This value is set to "Unique (default)".</span></span> <span data-ttu-id="117ba-158">Não modifique esse valor.</span><span class="sxs-lookup"><span data-stu-id="117ba-158">Do not modify this value.</span></span>|  
|<span data-ttu-id="117ba-159">**Componentes**</span><span class="sxs-lookup"><span data-stu-id="117ba-159">**Components**</span></span>|<span data-ttu-id="117ba-160">Especifica os componentes para os quais são criados logs de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="117ba-160">Specifies the components for which trace logs are created.</span></span> <span data-ttu-id="117ba-161">O valor padrão é `all`.</span><span class="sxs-lookup"><span data-stu-id="117ba-161">The default value is `all`.</span></span> <span data-ttu-id="117ba-162">Outros valores válidos para esta configuração incluem os nomes de componentes internos.</span><span class="sxs-lookup"><span data-stu-id="117ba-162">Other valid values for this setting include the names of internal components.</span></span> <span data-ttu-id="117ba-163">Não modifique esse valor.</span><span class="sxs-lookup"><span data-stu-id="117ba-163">Do not modify this value.</span></span>|  
|<span data-ttu-id="117ba-164">**Appmodel**</span><span class="sxs-lookup"><span data-stu-id="117ba-164">**Runtime**</span></span>|<span data-ttu-id="117ba-165">Especifica configurações que oferecem suporte para a compatibilidade com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="117ba-165">Specifies configuration settings that support backward compatibility with the previous version.</span></span> <span data-ttu-id="117ba-166">As configurações de runtime são usadas para redirecionar solicitações relacionadas à versão anterior de Microsoft.ReportingServices.Interfaces para a nova versão.</span><span class="sxs-lookup"><span data-stu-id="117ba-166">Runtime settings are used to redirect requests that target the previous version of Microsoft.ReportingServices.Interfaces to the new version.</span></span><br /><br /> <span data-ttu-id="117ba-167">Todas as configurações desta seção são descritas na documentação do produto [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="117ba-167">All of the configuration settings in this section are described in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] product documentation.</span></span> <span data-ttu-id="117ba-168">Para obter mais informações, procure “Configurações de esquema de runtime” no site do MSDN ou na documentação do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="117ba-168">For more information, search for "Runtime Schema Settings" on the MSDN Web site or in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] documentation.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="117ba-169">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="117ba-169">See Also</span></span>  
 <span data-ttu-id="117ba-170">[Arquivos de configuração do Reporting Services](reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="117ba-170">[Reporting Services Configuration Files](reporting-services-configuration-files.md) </span></span>  
 [<span data-ttu-id="117ba-171">Log de rastreamento do serviço Servidor de Relatório</span><span class="sxs-lookup"><span data-stu-id="117ba-171">Report Server Service Trace Log</span></span>](report-server-service-trace-log.md)  
  
  
