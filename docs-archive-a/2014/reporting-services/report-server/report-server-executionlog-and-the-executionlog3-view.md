---
title: Log de execução do servidor de relatório e a exibição ExecutionLog3 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- logs [Reporting Services], execution
- execution logs [Reporting Services]
ms.assetid: a7ead67d-1404-4e67-97e7-4c7b0d942070
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 868f8497e61c17662cb621850cdb8aee74c82706
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571306"
---
# <a name="report-server-execution-log-and-the-executionlog3-view"></a><span data-ttu-id="a080f-102">Log de execução do servidor de relatório e a exibição ExecutionLog3</span><span class="sxs-lookup"><span data-stu-id="a080f-102">Report Server Execution Log and the ExecutionLog3 View</span></span>
  <span data-ttu-id="a080f-103">O log de execução do servidor de relatório contém informações sobre os relatórios executados no servidor ou em vários servidores em uma implantação em expansão no modo nativo ou no farm do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a080f-103">The report server execution log contains information about the reports that execute on the server or on multiple servers in a native mode scale-out deployment or a SharePoint farm.</span></span> <span data-ttu-id="a080f-104">É possível usar o log de execução de relatório para descobrir a frequência na qual um relatório é solicitado, quais são os formatos de saída mais usados e qual é o tempo de processamento em milissegundos em cada fase do processamento.</span><span class="sxs-lookup"><span data-stu-id="a080f-104">You can use the report execution log to find out how often a report is requested, what output formats are used the most, and how many milliseconds of processing time is spent on each processing phase.</span></span> <span data-ttu-id="a080f-105">O log contém informações sobre o período de tempo gasto na execução da consulta do conjunto de dados de um relatório e a hora gasta no processamento dos dados.</span><span class="sxs-lookup"><span data-stu-id="a080f-105">The log contains information on the length of time spent executing a report's dataset query and the time spent processing the data.</span></span> <span data-ttu-id="a080f-106">Se você for um administrador de servidor de relatório, poderá revisar as informações de log, identificar tarefas demoradas e dar sugestões aos autores de relatório sobre as áreas do relatório (conjunto de dados ou processamento) que eles podem melhorar.</span><span class="sxs-lookup"><span data-stu-id="a080f-106">If you are a report server administrator, you can review the log information and identify long running tasks and make suggestions to the report authors on the areas of the report (dataset or processing) they may be able to improve.</span></span>  
  
 <span data-ttu-id="a080f-107">Os servidores de relatório configurados no modo do SharePoint também podem utilizar os logs ULS do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a080f-107">Report servers configured for SharePoint mode, can also utilize the SharePoint ULS logs.</span></span> <span data-ttu-id="a080f-108">Para obter mais informações, consulte [Ativar eventos do Reporting Services para o log de rastreamento do SharePoint &#40;ULS&#41;](turn-on-reporting-services-events-for-the-sharepoint-trace-log-uls.md)</span><span class="sxs-lookup"><span data-stu-id="a080f-108">For more information, see [Turn on Reporting Services events for the SharePoint trace log &#40;ULS&#41;](turn-on-reporting-services-events-for-the-sharepoint-trace-log-uls.md)</span></span>  
  
##  <a name="viewing-log-information"></a><a name="bkmk_top"></a> <span data-ttu-id="a080f-109">Exibindo as informações do log</span><span class="sxs-lookup"><span data-stu-id="a080f-109">Viewing Log Information</span></span>  
 <span data-ttu-id="a080f-110">A execução do servidor de relatório registra dados sobre execução de relatório em uma tabela de banco de dados interna.</span><span class="sxs-lookup"><span data-stu-id="a080f-110">The report server execution logs data about report execution into an internal database table.</span></span> <span data-ttu-id="a080f-111">As informações da tabela estão disponíveis nas exibições do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a080f-111">The information from the table is available from SQL Server views.</span></span>  
  
 <span data-ttu-id="a080f-112">O log de execução de relatório é armazenado no banco de dados do servidor de relatório que, por padrão, é denominado **ReportServer**.</span><span class="sxs-lookup"><span data-stu-id="a080f-112">The report execution log is stored in the report server database that by default is named **ReportServer**.</span></span> <span data-ttu-id="a080f-113">As exibições SQL fornecem as informações do log de execução.</span><span class="sxs-lookup"><span data-stu-id="a080f-113">The SQL views provide the execution log information.</span></span> <span data-ttu-id="a080f-114">As exibições "2" e "3" foram adicionadas às versões mais recentes e contêm novos campos ou contêm campos com nomes mais amigáveis que as versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="a080f-114">The "2" and "3" views were added in more recent releases and contain new fields or they contain fields with friendlier names than the previous releases.</span></span> <span data-ttu-id="a080f-115">As exibições mais antigas permanecem no produto; portanto, os aplicativos que dependem delas não são impactados.</span><span class="sxs-lookup"><span data-stu-id="a080f-115">The older views remain in the product so custom applications that depend on them are not impacted.</span></span> <span data-ttu-id="a080f-116">Se você não tem uma dependência em uma exibição mais antiga, por exemplo, ExecutionLog, é recomendável que use a exibição mais recente, ExecutionLog**3**.</span><span class="sxs-lookup"><span data-stu-id="a080f-116">If you do not have a dependence on an older view, for example ExecutionLog, it is recommended you use the most recent view, ExecutionLog**3**.</span></span>  
  
 <span data-ttu-id="a080f-117">Neste tópico:</span><span class="sxs-lookup"><span data-stu-id="a080f-117">In this topic:</span></span>  
  
-   [<span data-ttu-id="a080f-118">Configurações de um servidor de relatório no modo SharePoint</span><span class="sxs-lookup"><span data-stu-id="a080f-118">Configuration Settings for a SharePoint mode Report Server</span></span>](#bkmk_sharepoint)  
  
-   [<span data-ttu-id="a080f-119">Configurações de um servidor de relatório no modo nativo</span><span class="sxs-lookup"><span data-stu-id="a080f-119">Configuration Settings for a Native Mode Report Server</span></span>](#bkmk_native)  
  
-   [<span data-ttu-id="a080f-120">Campos de log (ExecutionLog3)</span><span class="sxs-lookup"><span data-stu-id="a080f-120">Log Fields (ExecutionLog3)</span></span>](#bkmk_executionlog3)  
  
-   [<span data-ttu-id="a080f-121">O campo AdditionalInfo</span><span class="sxs-lookup"><span data-stu-id="a080f-121">The AdditionalInfo Field</span></span>](#bkmk_additionalinfo)  
  
-   [<span data-ttu-id="a080f-122">Campos de log (ExecutionLog2)</span><span class="sxs-lookup"><span data-stu-id="a080f-122">Log Fields (ExecutionLog2)</span></span>](#bkmk_executionlog2)  
  
-   [<span data-ttu-id="a080f-123">Campos de log (ExecutionLog)</span><span class="sxs-lookup"><span data-stu-id="a080f-123">Log Fields (ExecutionLog)</span></span>](#bkmk_executionlog)  
  
##  <a name="configuration-settings-for-a-sharepoint-mode-report-server"></a><a name="bkmk_sharepoint"></a> <span data-ttu-id="a080f-124">Configurações de um servidor de relatório no modo SharePoint</span><span class="sxs-lookup"><span data-stu-id="a080f-124">Configuration Settings for a SharePoint mode Report Server</span></span>  
 <span data-ttu-id="a080f-125">Você pode ativar ou desativar a execução de relatório nas configurações de sistema de um aplicativo de serviço [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a080f-125">You can turn report execution logging on or off from the system settings of a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span>  
  
 <span data-ttu-id="a080f-126">Por padrão, as entradas de log são mantidas por 60 dias.</span><span class="sxs-lookup"><span data-stu-id="a080f-126">By default, log entries are kept 60 days.</span></span> <span data-ttu-id="a080f-127">Entradas que excedem essa data são removidas às 2h00</span><span class="sxs-lookup"><span data-stu-id="a080f-127">Entries that exceed this date are removed at 2:00 A.M.</span></span> <span data-ttu-id="a080f-128">diariamente.</span><span class="sxs-lookup"><span data-stu-id="a080f-128">every day.</span></span> <span data-ttu-id="a080f-129">Em uma instalação madura, somente 60 dias de informações estarão disponíveis em um dado momento.</span><span class="sxs-lookup"><span data-stu-id="a080f-129">On a mature installation, only 60 days of information will be available at any given time.</span></span>  
  
 <span data-ttu-id="a080f-130">Não é possível definir limites para o número de linhas ou o tipo de entradas registradas.</span><span class="sxs-lookup"><span data-stu-id="a080f-130">You cannot set limits on the number of rows or on the type of entries that are logged.</span></span>  
  
 <span data-ttu-id="a080f-131">**Para habilitar o log de execução:**</span><span class="sxs-lookup"><span data-stu-id="a080f-131">**To enable execution logging:**</span></span>  
  
1.  <span data-ttu-id="a080f-132">Na Administração Central do SharePoint, clique em **Gerenciar aplicativos de serviço** no grupo **Gerenciamento de Aplicativos** .</span><span class="sxs-lookup"><span data-stu-id="a080f-132">From SharePoint Central Administration, click **Manage service applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="a080f-133">Clique no nome do aplicativo de serviço [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] a ser configurado.</span><span class="sxs-lookup"><span data-stu-id="a080f-133">Click the name of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application you want to configure.</span></span>  
  
3.  <span data-ttu-id="a080f-134">Clique em **Configurações do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="a080f-134">Click **System Settings**.</span></span>  
  
4.  <span data-ttu-id="a080f-135">Selecione **Habilitar Log de Execução** na seção **Log** .</span><span class="sxs-lookup"><span data-stu-id="a080f-135">Select **Enable Execution Logging** in the **Logging** section.</span></span>  
  
5.  <span data-ttu-id="a080f-136">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a080f-136">Click **OK**.</span></span>  
  
 <span data-ttu-id="a080f-137">**Para habilitar o log detalhado:**</span><span class="sxs-lookup"><span data-stu-id="a080f-137">**To enable verbose logging:**</span></span>  
  
 <span data-ttu-id="a080f-138">Você precisa habilitar o log conforme descrito nas etapas anteriores e concluir as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="a080f-138">You need to enable logging as described in the previous steps and then complete the following:</span></span>  
  
1.  <span data-ttu-id="a080f-139">Na página **Configurações do Sistema** do aplicativo de serviços [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , localize a seção **Definido pelo usuário** .</span><span class="sxs-lookup"><span data-stu-id="a080f-139">From the **System Settings** page of your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] services application, find the **User-defined** section.</span></span>  
  
2.  <span data-ttu-id="a080f-140">Altere o **ExecutionLogLevel** para **detalhado**.</span><span class="sxs-lookup"><span data-stu-id="a080f-140">Change the **ExecutionLogLevel** to **verbose**.</span></span> <span data-ttu-id="a080f-141">Esse é um campo de entrada de texto, e os dois valores possíveis são **detalhado** e **normal**.</span><span class="sxs-lookup"><span data-stu-id="a080f-141">This field is a text entry field and the two possible values are **verbose** and **normal**.</span></span>  
  
##  <a name="configuration-settings-for-a-native-mode-report-server"></a><a name="bkmk_native"></a> <span data-ttu-id="a080f-142">Configurações de um servidor de relatório no modo nativo</span><span class="sxs-lookup"><span data-stu-id="a080f-142">Configuration Settings for a Native Mode Report Server</span></span>  
 <span data-ttu-id="a080f-143">Você pode ativar ou desativar o log de execução de relatório na página de Propriedades do Servidor do SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="a080f-143">You can turn report execution logging on or off from the Server Properties page in SQL Server Management Studio.</span></span> <span data-ttu-id="a080f-144">O **EnableExecutionLogging** é uma propriedade avançada.</span><span class="sxs-lookup"><span data-stu-id="a080f-144">The **EnableExecutionLogging** is and Advanced property.</span></span>  
  
 <span data-ttu-id="a080f-145">Por padrão, as entradas de log são mantidas por 60 dias.</span><span class="sxs-lookup"><span data-stu-id="a080f-145">By default, log entries are kept 60 days.</span></span> <span data-ttu-id="a080f-146">Entradas que excedem essa data são removidas às 2h00</span><span class="sxs-lookup"><span data-stu-id="a080f-146">Entries that exceed this date are removed at 2:00 A.M.</span></span> <span data-ttu-id="a080f-147">diariamente.</span><span class="sxs-lookup"><span data-stu-id="a080f-147">every day.</span></span> <span data-ttu-id="a080f-148">Em uma instalação madura, somente 60 dias de informações estarão disponíveis em um dado momento.</span><span class="sxs-lookup"><span data-stu-id="a080f-148">On a mature installation, only 60 days of information will be available at any given time.</span></span>  
  
 <span data-ttu-id="a080f-149">Não é possível definir limites para o número de linhas ou o tipo de entradas registradas.</span><span class="sxs-lookup"><span data-stu-id="a080f-149">You cannot set limits on the number of rows or on the type of entries that are logged.</span></span>  
  
 <span data-ttu-id="a080f-150">**Para habilitar o log de execução:**</span><span class="sxs-lookup"><span data-stu-id="a080f-150">**To enable execution logging:**</span></span>  
  
1.  <span data-ttu-id="a080f-151">Inicie o SQL Server Management Studio com privilégios administrativos.</span><span class="sxs-lookup"><span data-stu-id="a080f-151">Start SQL Server Management Studio with administrative privileges.</span></span> <span data-ttu-id="a080f-152">Por exemplo, clique com o botão direito do mouse no ícone do Management Studio e clique em 'Executar como administrador'.</span><span class="sxs-lookup"><span data-stu-id="a080f-152">For example right-click the Management Studio icon and click 'Run as administrator'.</span></span>  
  
2.  <span data-ttu-id="a080f-153">Conecte-se ao servidor de relatório desejado.</span><span class="sxs-lookup"><span data-stu-id="a080f-153">Connect to the desired report server.</span></span>  
  
3.  <span data-ttu-id="a080f-154">Clique com o botão direito do mouse no nome do servidor e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="a080f-154">Right-click the server name and click **Properties**.</span></span> <span data-ttu-id="a080f-155">Se a opção Propriedades for desabilitada, verifique se você executou o SQL Server Management Studio com privilégios administrativos.</span><span class="sxs-lookup"><span data-stu-id="a080f-155">If the Properties option is disabled, verify you ran SQL Server Management Studio with administrative privileges.</span></span>  
  
4.  <span data-ttu-id="a080f-156">Clique na página **Log** .</span><span class="sxs-lookup"><span data-stu-id="a080f-156">Click the **Logging** page.</span></span>  
  
5.  <span data-ttu-id="a080f-157">Selecione **Habilitar log de execução de relatório**.</span><span class="sxs-lookup"><span data-stu-id="a080f-157">Select **Enable report execution Logging**.</span></span>  
  
 <span data-ttu-id="a080f-158">**Para habilitar o log detalhado:**</span><span class="sxs-lookup"><span data-stu-id="a080f-158">**To enable verbose logging:**</span></span>  
  
 <span data-ttu-id="a080f-159">Você precisa habilitar o log conforme descrito nas etapas anteriores e concluir as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="a080f-159">You need to enable logging as described in the previous steps and then complete the following:</span></span>  
  
1.  <span data-ttu-id="a080f-160">Na caixa de diálogo **Propriedades do Servidor** , clique na página **Avançado** .</span><span class="sxs-lookup"><span data-stu-id="a080f-160">From the **Server Properties** dialog, click the **Advanced** page.</span></span>  
  
2.  <span data-ttu-id="a080f-161">Na seção **Definido pelo usuário** , altere o **ExecutionLogLevel** para **detalhado**.</span><span class="sxs-lookup"><span data-stu-id="a080f-161">In the **User-defined** section, change the **ExecutionLogLevel** to **verbose**.</span></span> <span data-ttu-id="a080f-162">Esse é um campo de entrada de texto, e os dois valores possíveis são **detalhado** e **normal**.</span><span class="sxs-lookup"><span data-stu-id="a080f-162">This field is a text entry field and the two possible values are **verbose** and **normal**.</span></span>  
  
##  <a name="log-fields-executionlog3"></a><a name="bkmk_executionlog3"></a> <span data-ttu-id="a080f-163">Campos de log (ExecutionLog3)</span><span class="sxs-lookup"><span data-stu-id="a080f-163">Log Fields (ExecutionLog3)</span></span>  
 <span data-ttu-id="a080f-164">Esta exibição adicionou o nó de diagnóstico de desempenho adicional à coluna **AdditionalInfo** baseada em XML.</span><span class="sxs-lookup"><span data-stu-id="a080f-164">This view added additional performance diagnostics node inside the XML based **AdditionalInfo** column.</span></span> <span data-ttu-id="a080f-165">A coluna AdditionalInfo contém uma estrutura XML de 1 para muitos campos adicionais de informação.</span><span class="sxs-lookup"><span data-stu-id="a080f-165">The AdditionalInfo column contains an XML structure of 1 to many additional fields of information.</span></span> <span data-ttu-id="a080f-166">Este é um exemplo de instrução Transact-SQL para recuperar linhas da exibição ExecutionLog3.</span><span class="sxs-lookup"><span data-stu-id="a080f-166">The following is a sample Transact SQL statement to retrieve rows from the view ExecutionLog3.</span></span> <span data-ttu-id="a080f-167">O exemplo presume que o nome do banco de dados do servidor de relatório seja **ReportServer**:</span><span class="sxs-lookup"><span data-stu-id="a080f-167">The sample assumes the report server database is named **ReportServer**:</span></span>  
  
```  
Use ReportServer  
select * from ExecutionLog3 order by TimeStart DESC  
```  
  
 <span data-ttu-id="a080f-168">A tabela a seguir descreve os dados capturados no log de execução de relatório</span><span class="sxs-lookup"><span data-stu-id="a080f-168">The following table describes the data that is captured in the report execution log</span></span>  
  
|<span data-ttu-id="a080f-169">Coluna</span><span class="sxs-lookup"><span data-stu-id="a080f-169">Column</span></span>|<span data-ttu-id="a080f-170">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="a080f-170">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a080f-171">InstanceName</span><span class="sxs-lookup"><span data-stu-id="a080f-171">InstanceName</span></span>|<span data-ttu-id="a080f-172">Nome da instância de servidor de relatório que manipulou a solicitação.</span><span class="sxs-lookup"><span data-stu-id="a080f-172">Name of the report server instance that handled the request.</span></span> <span data-ttu-id="a080f-173">Se seu ambiente tiver mais de um servidor de relatório, você poderá analisar a distribuição de InstanceName para monitorar e determinar se o balanceador da carga de rede distribui solicitações pelos servidores de relatório conforme esperado.</span><span class="sxs-lookup"><span data-stu-id="a080f-173">If your environment has more than one report server, you can analyze the InstanceName distribution to monitor and determine if your network-load balancer distributes requests across report servers as expected.</span></span>|  
|<span data-ttu-id="a080f-174">ItemPath</span><span class="sxs-lookup"><span data-stu-id="a080f-174">ItemPath</span></span>|<span data-ttu-id="a080f-175">Caminho onde um relatório ou item de relatório é armazenado.</span><span class="sxs-lookup"><span data-stu-id="a080f-175">Path of where a report or report item is stored.</span></span>|  
|<span data-ttu-id="a080f-176">UserName</span><span class="sxs-lookup"><span data-stu-id="a080f-176">UserName</span></span>|<span data-ttu-id="a080f-177">Identificador do usuário.</span><span class="sxs-lookup"><span data-stu-id="a080f-177">User identifier.</span></span>|  
|<span data-ttu-id="a080f-178">ExecutionID</span><span class="sxs-lookup"><span data-stu-id="a080f-178">ExecutionID</span></span>|<span data-ttu-id="a080f-179">O identificador interno associado a uma solicitação.</span><span class="sxs-lookup"><span data-stu-id="a080f-179">The internal identifier associated with a request.</span></span> <span data-ttu-id="a080f-180">Solicitações nas mesmas sessões de usuário compartilham a mesma id de execução.</span><span class="sxs-lookup"><span data-stu-id="a080f-180">Requests on the same user sessions share the same execution id.</span></span>|  
|<span data-ttu-id="a080f-181">RequestType</span><span class="sxs-lookup"><span data-stu-id="a080f-181">RequestType</span></span>|<span data-ttu-id="a080f-182">Valores possíveis:</span><span class="sxs-lookup"><span data-stu-id="a080f-182">Possible Values:</span></span><br /><span data-ttu-id="a080f-183">**Interativo**</span><span class="sxs-lookup"><span data-stu-id="a080f-183">**Interactive**</span></span><br /><span data-ttu-id="a080f-184">**Assinatura**</span><span class="sxs-lookup"><span data-stu-id="a080f-184">**Subscription**</span></span><br /><br /> <br /><br /> <span data-ttu-id="a080f-185">A análise dos dados de log filtrados por RequestType=Subscription e classificados por TimeStart pode revelar períodos de uso de assinatura pesados e talvez você queira modificar algumas assinaturas de relatório para um horário diferente.</span><span class="sxs-lookup"><span data-stu-id="a080f-185">Analyzing log data filtered by RequestType=Subscription and sorted by TimeStart may reveal periods of heavy subscription usage and you may want to modify some of the report subscriptions to a different time.</span></span>|  
|<span data-ttu-id="a080f-186">Formatar</span><span class="sxs-lookup"><span data-stu-id="a080f-186">Format</span></span>|<span data-ttu-id="a080f-187">Formato de renderização.</span><span class="sxs-lookup"><span data-stu-id="a080f-187">Rendering format.</span></span>|  
|<span data-ttu-id="a080f-188">parâmetros</span><span class="sxs-lookup"><span data-stu-id="a080f-188">Parameters</span></span>|<span data-ttu-id="a080f-189">Valores de parâmetro usados em uma execução de relatório.</span><span class="sxs-lookup"><span data-stu-id="a080f-189">Parameter values used for a report execution.</span></span>|  
|<span data-ttu-id="a080f-190">ItemAction</span><span class="sxs-lookup"><span data-stu-id="a080f-190">ItemAction</span></span>|<span data-ttu-id="a080f-191">Valores possíveis:</span><span class="sxs-lookup"><span data-stu-id="a080f-191">Possible values:</span></span><br /><br /> <span data-ttu-id="a080f-192">**Render**</span><span class="sxs-lookup"><span data-stu-id="a080f-192">**Render**</span></span><br /><br /> <span data-ttu-id="a080f-193">**Sort**</span><span class="sxs-lookup"><span data-stu-id="a080f-193">**Sort**</span></span><br /><br /> <span data-ttu-id="a080f-194">**BookMarkNavigation**</span><span class="sxs-lookup"><span data-stu-id="a080f-194">**BookMarkNavigation**</span></span><br /><br /> <span data-ttu-id="a080f-195">**DocumentNavigation**</span><span class="sxs-lookup"><span data-stu-id="a080f-195">**DocumentNavigation**</span></span><br /><br /> <span data-ttu-id="a080f-196">**GetDocumentMap**</span><span class="sxs-lookup"><span data-stu-id="a080f-196">**GetDocumentMap**</span></span><br /><br /> <span data-ttu-id="a080f-197">**FindString**</span><span class="sxs-lookup"><span data-stu-id="a080f-197">**Findstring**</span></span><br /><br /> <span data-ttu-id="a080f-198">**Executados**</span><span class="sxs-lookup"><span data-stu-id="a080f-198">**Execute**</span></span><br /><br /> <span data-ttu-id="a080f-199">**RenderEdit**</span><span class="sxs-lookup"><span data-stu-id="a080f-199">**RenderEdit**</span></span>|  
|<span data-ttu-id="a080f-200">TimeStart</span><span class="sxs-lookup"><span data-stu-id="a080f-200">TimeStart</span></span>|<span data-ttu-id="a080f-201">Horas de início e parada que indicam a duração de um processo de relatório.</span><span class="sxs-lookup"><span data-stu-id="a080f-201">Start and stop times that indicate the duration of a report process.</span></span>|  
|<span data-ttu-id="a080f-202">TimeEnd</span><span class="sxs-lookup"><span data-stu-id="a080f-202">TimeEnd</span></span>||  
|<span data-ttu-id="a080f-203">TimeDataRetrieval</span><span class="sxs-lookup"><span data-stu-id="a080f-203">TimeDataRetrieval</span></span>|<span data-ttu-id="a080f-204">Número de milissegundos gastos na recuperação dos dados.</span><span class="sxs-lookup"><span data-stu-id="a080f-204">Number of milliseconds spent retrieving the data.</span></span>|  
|<span data-ttu-id="a080f-205">TimeProcessing</span><span class="sxs-lookup"><span data-stu-id="a080f-205">TimeProcessing</span></span>|<span data-ttu-id="a080f-206">Número de milissegundos gastos no processamento do relatório.</span><span class="sxs-lookup"><span data-stu-id="a080f-206">Number of milliseconds spent processing the report.</span></span>|  
|<span data-ttu-id="a080f-207">TimeRendering</span><span class="sxs-lookup"><span data-stu-id="a080f-207">TimeRendering</span></span>|<span data-ttu-id="a080f-208">Número de milissegundos gastos na renderização do relatório.</span><span class="sxs-lookup"><span data-stu-id="a080f-208">Number of milliseconds spent rendering the report.</span></span>|  
|<span data-ttu-id="a080f-209">Fonte</span><span class="sxs-lookup"><span data-stu-id="a080f-209">Source</span></span>|<span data-ttu-id="a080f-210">Fonte da execução de relatório.</span><span class="sxs-lookup"><span data-stu-id="a080f-210">Source of the report execution.</span></span> <span data-ttu-id="a080f-211">Valores possíveis:</span><span class="sxs-lookup"><span data-stu-id="a080f-211">Possible values:</span></span><br /><br /> <span data-ttu-id="a080f-212">**Ao vivo**</span><span class="sxs-lookup"><span data-stu-id="a080f-212">**Live**</span></span><br /><br /> <span data-ttu-id="a080f-213">**Cache**: indica uma execução em cache, por exemplo, as consultas de conjunto de consulta não são executadas ao vivo.</span><span class="sxs-lookup"><span data-stu-id="a080f-213">**Cache**: Indicates a cached execution, for example, dataset queries are not executed live.</span></span><br /><br /> <span data-ttu-id="a080f-214">**Instantâneo**</span><span class="sxs-lookup"><span data-stu-id="a080f-214">**Snapshot**</span></span><br /><br /> <span data-ttu-id="a080f-215">**Histórico**</span><span class="sxs-lookup"><span data-stu-id="a080f-215">**History**</span></span><br /><br /> <span data-ttu-id="a080f-216">**Adhoc** : indica um relatório de detalhamento baseado em modelo de relatório gerado dinamicamente ou um relatório Construtor de relatórios que é visualizado em um cliente que utiliza o servidor de relatório para processamento e renderização.</span><span class="sxs-lookup"><span data-stu-id="a080f-216">**AdHoc** : Indicates either a dynamically generated report model based drill through report, or a Report Builder report that is previewed on a client utilizing the report server for processing and rendering.</span></span><br /><br /> <span data-ttu-id="a080f-217">**Sessão**: indica uma solicitação de acompanhamento dentro de uma sessão já estabelecida.</span><span class="sxs-lookup"><span data-stu-id="a080f-217">**Session**: Indicates a follow up request within an already established session.</span></span>  <span data-ttu-id="a080f-218">Por exemplo, a solicitação inicial é exibir página 1 e a solicitação de acompanhamento é exportar para o Excel com o estado de sessão atual.</span><span class="sxs-lookup"><span data-stu-id="a080f-218">For example the initial request is to view page 1, and the follow up request is to export to Excel with the current session state.</span></span><br /><br /> <span data-ttu-id="a080f-219">**RDCE**: indica uma extensão de personalização de definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="a080f-219">**Rdce**:  Indicates a Report Definition Customization Extension.</span></span> <span data-ttu-id="a080f-220">Uma extensão personalizada RDCE pode personalizar uma definição de relatório dinamicamente antes de ela ser passada ao mecanismo de processamento mediante a execução do relatório.</span><span class="sxs-lookup"><span data-stu-id="a080f-220">An RDCE custom extension can dynamically customize a report definition before it is passed to the processing engine upon report execution.</span></span>|  
|<span data-ttu-id="a080f-221">Status</span><span class="sxs-lookup"><span data-stu-id="a080f-221">Status</span></span>|<span data-ttu-id="a080f-222">Status (rsSuccess ou um código de erro; se vários erros ocorrerem, só o primeiro erro será registrado).</span><span class="sxs-lookup"><span data-stu-id="a080f-222">Status (either rsSuccess or an error code; if multiple errors occur, only the first error is recorded).</span></span>|  
|<span data-ttu-id="a080f-223">ByteCount</span><span class="sxs-lookup"><span data-stu-id="a080f-223">ByteCount</span></span>|<span data-ttu-id="a080f-224">Tamanho de relatórios renderizados em bytes.</span><span class="sxs-lookup"><span data-stu-id="a080f-224">Size of rendered reports in bytes.</span></span>|  
|<span data-ttu-id="a080f-225">RowCount</span><span class="sxs-lookup"><span data-stu-id="a080f-225">RowCount</span></span>|<span data-ttu-id="a080f-226">Número de linhas retornadas pelas consultas.</span><span class="sxs-lookup"><span data-stu-id="a080f-226">Number of rows returned from queries.</span></span>|  
|<span data-ttu-id="a080f-227">AdditionalInfo</span><span class="sxs-lookup"><span data-stu-id="a080f-227">AdditionalInfo</span></span>|<span data-ttu-id="a080f-228">Um conjunto de propriedades XML contendo informações adicionais sobre a execução.</span><span class="sxs-lookup"><span data-stu-id="a080f-228">An XML property bag containing additional information about the execution.</span></span> <span data-ttu-id="a080f-229">O conteúdo pode ser diferente para cada linha.</span><span class="sxs-lookup"><span data-stu-id="a080f-229">The contents can be different for each row.</span></span>|  
  
##  <a name="the-additionalinfo-field"></a><a name="bkmk_additionalinfo"></a> <span data-ttu-id="a080f-230">O campo AdditionalInfo</span><span class="sxs-lookup"><span data-stu-id="a080f-230">The AdditionalInfo Field</span></span>  
 <span data-ttu-id="a080f-231">O campo AdditionalInfo é uma estrutura ou um conjunto de propriedades XML contendo informações adicionais sobre a execução.</span><span class="sxs-lookup"><span data-stu-id="a080f-231">The AdditionalInfo field is an XML property bag or structure containing additional information about the execution.</span></span> <span data-ttu-id="a080f-232">O conteúdo pode ser diferente para cada linha do log.</span><span class="sxs-lookup"><span data-stu-id="a080f-232">The contents can be different for each row in the log.</span></span>  
  
 <span data-ttu-id="a080f-233">As tabelas a seguir são exemplos de conteúdo do campo AddtionalInfo para registro em log padrão e detalhado:</span><span class="sxs-lookup"><span data-stu-id="a080f-233">The following tables are examples  of the contents of the AddtionalInfo field for both standard and verbose logging:</span></span>  
  
 <span data-ttu-id="a080f-234">**Exemplo de registro em log padrão de AddtionalInfo**</span><span class="sxs-lookup"><span data-stu-id="a080f-234">**Standard logging example of AddtionalInfo**</span></span>  
  
```  
<AdditionalInfo>  
  <ProcessingEngine>2</ProcessingEngine>  
  <ScalabilityTime>  
    <Pagination>0</Pagination>  
    <Processing>0</Processing>  
  </ScalabilityTime>  
  <EstimatedMemoryUsageKB>  
    <Pagination>0</Pagination>  
    <Processing>6</Processing>  
  </EstimatedMemoryUsageKB>  
  <DataExtension>  
    <SQL>1</SQL>  
  </DataExtension>  
  <Connections>  
    <Connection>  
      <ConnectionOpenTime>147</ConnectionOpenTime>  
      <DataSets>  
        <DataSet>  
          <Name>DataSet1</Name>  
          <RowsRead>16</RowsRead>  
          <TotalTimeDataRetrieval>642</TotalTimeDataRetrieval>  
          <ExecuteReaderTime>63</ExecuteReaderTime>  
        </DataSet>  
        <DataSet>  
          <Name>DataSet2</Name>  
          <RowsRead>3</RowsRead>  
          <TotalTimeDataRetrieval>157</TotalTimeDataRetrieval>  
          <ExecuteReaderTime>60</ExecuteReaderTime>  
        </DataSet>  
      </DataSets>  
    </Connection>  
  </Connections>  
</AdditionalInfo>  
  
```  
  
 <span data-ttu-id="a080f-235">**Exemplo de registro em log detalhado de AdditionalInfo**</span><span class="sxs-lookup"><span data-stu-id="a080f-235">**Verbose logging example of AdditionalInfo**</span></span>  
  
```  
<AdditionalInfo>  
  <ProcessingEngine>2</ProcessingEngine>  
  <ScalabilityTime>  
    <Pagination>0</Pagination>  
    <Processing>0</Processing>  
  </ScalabilityTime>  
  <EstimatedMemoryUsageKB>  
    <Pagination>0</Pagination>  
    <Processing>6</Processing>  
  </EstimatedMemoryUsageKB>  
  <DataExtension>  
    <SQL>1</SQL>  
  </DataExtension>  
  <Connections>  
    <Connection>  
      <ConnectionOpenTime>127</ConnectionOpenTime>  
      <DataSource>  
        <Name>DataSource1</Name>  
        <DataExtension>SQL</DataExtension>  
      </DataSource>  
      <DataSets>  
        <DataSet>  
          <Name>DataSet1</Name>  
          <RowsRead>16</RowsRead>  
          <TotalTimeDataRetrieval>655</TotalTimeDataRetrieval>  
          <QueryPrepareAndExecutionTime>94</QueryPrepareAndExecutionTime>  
          <ExecuteReaderTime>33</ExecuteReaderTime>  
          <DataReaderMappingTime>30</DataReaderMappingTime>  
          <DisposeDataReaderTime>1</DisposeDataReaderTime>  
        </DataSet>  
        <DataSet>  
          <Name>DataSet2</Name>  
          <RowsRead>3</RowsRead>  
          <TotalTimeDataRetrieval>16</TotalTimeDataRetrieval>  
          <QueryPrepareAndExecutionTime>2</QueryPrepareAndExecutionTime>  
          <ExecuteReaderTime>1</ExecuteReaderTime>  
          <DataReaderMappingTime>0</DataReaderMappingTime>  
          <DisposeDataReaderTime>0</DisposeDataReaderTime>  
        </DataSet>  
      </DataSets>  
    </Connection>  
  </Connections>  
</AdditionalInfo>  
  
```  
  
 <span data-ttu-id="a080f-236">Veja a seguir uma descrição de algumas das propriedades que você verá no campo AdditionalInfo:</span><span class="sxs-lookup"><span data-stu-id="a080f-236">The following describes some of the properties you will see in the AdditionalInfo field:</span></span>  
  
-   <span data-ttu-id="a080f-237">**ProcessingEngine**: 1 = SQL Server 2005, 2 = o novo mecanismo de processamento sob demanda.</span><span class="sxs-lookup"><span data-stu-id="a080f-237">**ProcessingEngine**: 1=SQL Server 2005, 2=The new On-demand Processing Engine.</span></span> <span data-ttu-id="a080f-238">Se a maioria de seus relatórios ainda estiver mostrando o valor 1, você poderá investigar como reprojetá-los para que utilizem o mecanismo de processamento sob demanda mais novo e eficiente.</span><span class="sxs-lookup"><span data-stu-id="a080f-238">If a majority of your reports are still showing the value of 1, you may investigate how to redesign them so they utilize the newer and more efficient on-demand processing engine.</span></span>  
  
     `<ProcessingEngine>2</ProcessingEngine>`  
  
-   <span data-ttu-id="a080f-239">**Redimensiontime**: o número de milissegundos gasto na execução de operações relacionadas à escala no mecanismo de processamento.</span><span class="sxs-lookup"><span data-stu-id="a080f-239">**ScalabilityTime**: The number of milliseconds spent performing scale related operations in the processing engine.</span></span> <span data-ttu-id="a080f-240">O valor 0 indica que nenhuma hora adicional foi gasta em operações de escala; indica também que a solicitação não estava sob pressão de memória.</span><span class="sxs-lookup"><span data-stu-id="a080f-240">A value of 0 indicates that no additional time was spent on scale operations and a 0 also indicates the request was not under memory pressure.</span></span>  
  
    ```  
    <ScalabilityTime>  
        <Processing>0</Processing>  
    </ScalabilityTime>  
    ```  
  
-   <span data-ttu-id="a080f-241">**EstimatedMemoryUsageKB**: uma estimativa da quantidade de pico de memória, em quilobytes, consumida por cada componente durante uma solicitação específica.</span><span class="sxs-lookup"><span data-stu-id="a080f-241">**EstimatedMemoryUsageKB**: An estimate of the peak amount of memory, in kilobytes, consumed by each component during a particular request.</span></span>  
  
    ```  
    <EstimatedMemoryUsageKB>  
        <Processing>38</Processing>  
    </EstimatedMemoryUsageKB>  
    ```  
  
-   <span data-ttu-id="a080f-242">**Dataextension**: os tipos de extensões de dados ou fontes de dados usados no relatório.</span><span class="sxs-lookup"><span data-stu-id="a080f-242">**DataExtension**: The types of data extensions or data sources used in the report.</span></span> <span data-ttu-id="a080f-243">O número é uma contagem do número de ocorrências da fonte de dados específica.</span><span class="sxs-lookup"><span data-stu-id="a080f-243">The number is a count of the number of occurrences of the particular data source.</span></span>  
  
    ```  
    <DataExtension>  
       <DAX>2</DAX>  
    </DataExtension>  
    ```  
  
-   <span data-ttu-id="a080f-244">**ExternalImages** O valor está em milissegundos.</span><span class="sxs-lookup"><span data-stu-id="a080f-244">**ExternalImages**The value is in miliseconds.</span></span> <span data-ttu-id="a080f-245">Esses dados podem ser usados para diagnosticar problemas de desempenho.</span><span class="sxs-lookup"><span data-stu-id="a080f-245">This data can be used to diagnose performance issues.</span></span> <span data-ttu-id="a080f-246">A hora necessária para recuperar imagens de um servidor Web externo pode tornar lenta a execução de relatório geral.</span><span class="sxs-lookup"><span data-stu-id="a080f-246">The time needed to retrieve images from an external webserver may slow the overall report execution.</span></span> <span data-ttu-id="a080f-247">Adicionado no [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a080f-247">Added in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span></span>  
  
    ```  
    <ExternalImages>  
        <Count>3</Count>  
        <ByteCount>9268</ByteCount>  
        <ResourceFetchTime>9</ResourceFetchTime>  
    </ExternalImages>  
    ```  
  
-   <span data-ttu-id="a080f-248">**Conexões**: uma estrutura de vários níveis.</span><span class="sxs-lookup"><span data-stu-id="a080f-248">**Connections**: A multi-leveled structure.</span></span> <span data-ttu-id="a080f-249">Adicionado no [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a080f-249">Added in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span></span>  
  
    ```  
    <Connections>  
        <Connection>  
          <ConnectionOpenTime>127</ConnectionOpenTime>  
          <DataSource>  
            <Name>DataSource1</Name>  
            <DataExtension>SQL</DataExtension>  
          </DataSource>  
          <DataSets>  
            <DataSet>  
              <Name>DataSet1</Name>  
              <RowsRead>16</RowsRead>  
              <TotalTimeDataRetrieval>655</TotalTimeDataRetrieval>  
              <QueryPrepareAndExecutionTime>94</QueryPrepareAndExecutionTime>  
              <ExecuteReaderTime>33</ExecuteReaderTime>  
              <DataReaderMappingTime>30</DataReaderMappingTime>  
              <DisposeDataReaderTime>1</DisposeDataReaderTime>  
            </DataSet>  
            <DataSet>  
              <Name>DataSet2</Name>  
              <RowsRead>3</RowsRead>  
              <TotalTimeDataRetrieval>16</TotalTimeDataRetrieval>  
              <QueryPrepareAndExecutionTime>2</QueryPrepareAndExecutionTime>  
              <ExecuteReaderTime>1</ExecuteReaderTime>  
              <DataReaderMappingTime>0</DataReaderMappingTime>  
              <DisposeDataReaderTime>0</DisposeDataReaderTime>  
            </DataSet>  
          </DataSets>  
        </Connection>  
    </Connections>  
  
    ```  
  
##  <a name="log-fields-executionlog2"></a><a name="bkmk_executionlog2"></a> <span data-ttu-id="a080f-250">Campos de log (ExecutionLog2)</span><span class="sxs-lookup"><span data-stu-id="a080f-250">Log Fields (ExecutionLog2)</span></span>  
 <span data-ttu-id="a080f-251">Esta exibição adicionou alguns campos novos e renomeou outros.</span><span class="sxs-lookup"><span data-stu-id="a080f-251">This view added a few new fields and renamed a few others.</span></span> <span data-ttu-id="a080f-252">Este é um exemplo de instrução Transact-SQL para recuperar linhas da exibição ExecutionLog2.</span><span class="sxs-lookup"><span data-stu-id="a080f-252">The following is a sample Transact SQL statement to retrieve rows from the view ExecutionLog2.</span></span> <span data-ttu-id="a080f-253">O exemplo presume que o nome do banco de dados do servidor de relatório seja **ReportServer**:</span><span class="sxs-lookup"><span data-stu-id="a080f-253">The sample assumes the report server database is named **ReportServer**:</span></span>  
  
```  
Use ReportServer  
select * from ExecutionLog2 order by TimeStart DESC  
```  
  
 <span data-ttu-id="a080f-254">A tabela a seguir descreve os dados capturados no log de execução de relatório</span><span class="sxs-lookup"><span data-stu-id="a080f-254">The following table describes the data that is captured in the report execution log</span></span>  
  
|<span data-ttu-id="a080f-255">Column</span><span class="sxs-lookup"><span data-stu-id="a080f-255">Column</span></span>|<span data-ttu-id="a080f-256">Descrição</span><span class="sxs-lookup"><span data-stu-id="a080f-256">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a080f-257">InstanceName</span><span class="sxs-lookup"><span data-stu-id="a080f-257">InstanceName</span></span>|<span data-ttu-id="a080f-258">Nome da instância de servidor de relatório que manipulou a solicitação.</span><span class="sxs-lookup"><span data-stu-id="a080f-258">Name of the report server instance that handled the request.</span></span>|  
|<span data-ttu-id="a080f-259">ReportPath</span><span class="sxs-lookup"><span data-stu-id="a080f-259">ReportPath</span></span>|<span data-ttu-id="a080f-260">A estrutura de caminho para o relatório.</span><span class="sxs-lookup"><span data-stu-id="a080f-260">The path structure to the report.</span></span>  <span data-ttu-id="a080f-261">Por exemplo, um relatório chamado "test", que está na pasta raiz do Gerenciador de Relatórios, teria um ReportPath "/test".</span><span class="sxs-lookup"><span data-stu-id="a080f-261">For example a report named "test" which is the in root folder in Report Manager, would have a ReportPath of "/test".</span></span><br /><br /> <span data-ttu-id="a080f-262">Um relatório chamado "test", salvo na pasta "samples" do Gerenciador de Relatórios, terá o ReportPath "/Samples/test/"</span><span class="sxs-lookup"><span data-stu-id="a080f-262">A report named "test" that is saved in the folder "samples" on Report Manager , will have a ReportPath of "/Samples/test/"</span></span>|  
|<span data-ttu-id="a080f-263">UserName</span><span class="sxs-lookup"><span data-stu-id="a080f-263">UserName</span></span>|<span data-ttu-id="a080f-264">Identificador do usuário.</span><span class="sxs-lookup"><span data-stu-id="a080f-264">User identifier.</span></span>|  
|<span data-ttu-id="a080f-265">ExecutionID</span><span class="sxs-lookup"><span data-stu-id="a080f-265">ExecutionID</span></span>||  
|<span data-ttu-id="a080f-266">RequestType</span><span class="sxs-lookup"><span data-stu-id="a080f-266">RequestType</span></span>|<span data-ttu-id="a080f-267">Tipo de solicitação (usuário ou sistema).</span><span class="sxs-lookup"><span data-stu-id="a080f-267">Request type (either user or system).</span></span>|  
|<span data-ttu-id="a080f-268">Formatar</span><span class="sxs-lookup"><span data-stu-id="a080f-268">Format</span></span>|<span data-ttu-id="a080f-269">Formato de renderização.</span><span class="sxs-lookup"><span data-stu-id="a080f-269">Rendering format.</span></span>|  
|<span data-ttu-id="a080f-270">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a080f-270">Parameters</span></span>|<span data-ttu-id="a080f-271">Valores de parâmetro usados em uma execução de relatório.</span><span class="sxs-lookup"><span data-stu-id="a080f-271">Parameter values used for a report execution.</span></span>|  
|<span data-ttu-id="a080f-272">ReportAction</span><span class="sxs-lookup"><span data-stu-id="a080f-272">ReportAction</span></span>|<span data-ttu-id="a080f-273">Valores possíveis: Render, Sort, BookMarkNavigation, DocumentNavigation, GetDocumentMap, Findstring</span><span class="sxs-lookup"><span data-stu-id="a080f-273">Possible values: Render, Sort, BookMarkNavigation, DocumentNavigation, GetDocumentMap, Findstring</span></span>|  
|<span data-ttu-id="a080f-274">TimeStart</span><span class="sxs-lookup"><span data-stu-id="a080f-274">TimeStart</span></span>|<span data-ttu-id="a080f-275">Horas de início e parada que indicam a duração de um processo de relatório.</span><span class="sxs-lookup"><span data-stu-id="a080f-275">Start and stop times that indicate the duration of a report process.</span></span>|  
|<span data-ttu-id="a080f-276">TimeEnd</span><span class="sxs-lookup"><span data-stu-id="a080f-276">TimeEnd</span></span>||  
|<span data-ttu-id="a080f-277">TimeDataRetrieval</span><span class="sxs-lookup"><span data-stu-id="a080f-277">TimeDataRetrieval</span></span>|<span data-ttu-id="a080f-278">Número de milissegundos gastos na recuperação dos dados, no processamento do relatório e na renderização do relatório.</span><span class="sxs-lookup"><span data-stu-id="a080f-278">Number of milliseconds spent retrieving the data, processing the report, and rendering the report.</span></span>|  
|<span data-ttu-id="a080f-279">TimeProcessing</span><span class="sxs-lookup"><span data-stu-id="a080f-279">TimeProcessing</span></span>||  
|<span data-ttu-id="a080f-280">TimeRendering</span><span class="sxs-lookup"><span data-stu-id="a080f-280">TimeRendering</span></span>||  
|<span data-ttu-id="a080f-281">Fonte</span><span class="sxs-lookup"><span data-stu-id="a080f-281">Source</span></span>|<span data-ttu-id="a080f-282">Fonte da execução de relatório (1=Ativo, 2=Cache, 3=Instantâneo, 4=Histórico).</span><span class="sxs-lookup"><span data-stu-id="a080f-282">Source of the report execution (1=Live, 2=Cache, 3=Snapshot, 4=History).</span></span>|  
|<span data-ttu-id="a080f-283">Status</span><span class="sxs-lookup"><span data-stu-id="a080f-283">Status</span></span>|<span data-ttu-id="a080f-284">Status (rsSuccess ou um código de erro; se vários erros ocorrerem, só o primeiro erro será registrado).</span><span class="sxs-lookup"><span data-stu-id="a080f-284">Status (either rsSuccess or an error code; if multiple errors occur, only the first error is recorded).</span></span>|  
|<span data-ttu-id="a080f-285">ByteCount</span><span class="sxs-lookup"><span data-stu-id="a080f-285">ByteCount</span></span>|<span data-ttu-id="a080f-286">Tamanho de relatórios renderizados em bytes.</span><span class="sxs-lookup"><span data-stu-id="a080f-286">Size of rendered reports in bytes.</span></span>|  
|<span data-ttu-id="a080f-287">RowCount</span><span class="sxs-lookup"><span data-stu-id="a080f-287">RowCount</span></span>|<span data-ttu-id="a080f-288">Número de linhas retornadas pelas consultas.</span><span class="sxs-lookup"><span data-stu-id="a080f-288">Number of rows returned from queries.</span></span>|  
|<span data-ttu-id="a080f-289">AdditionalInfo</span><span class="sxs-lookup"><span data-stu-id="a080f-289">AdditionalInfo</span></span>|<span data-ttu-id="a080f-290">Um conjunto de propriedades XML contendo informações adicionais sobre a execução.</span><span class="sxs-lookup"><span data-stu-id="a080f-290">An XML property bag containing additional information about the execution.</span></span>|  
  
##  <a name="log-fields-executionlog"></a><a name="bkmk_executionlog"></a> <span data-ttu-id="a080f-291">Campos de log (ExecutionLog)</span><span class="sxs-lookup"><span data-stu-id="a080f-291">Log Fields (ExecutionLog)</span></span>  
 <span data-ttu-id="a080f-292">Este é um exemplo de instrução Transact-SQL para recuperar linhas da exibição ExecutionLog.</span><span class="sxs-lookup"><span data-stu-id="a080f-292">The following is a sample Transact SQL statement to retrieve rows from the view ExecutionLog.</span></span> <span data-ttu-id="a080f-293">O exemplo presume que o nome do banco de dados do servidor de relatório seja **ReportServer**:</span><span class="sxs-lookup"><span data-stu-id="a080f-293">The sample assumes the report server database is named **ReportServer**:</span></span>  
  
```  
Use ReportServer  
select * from ExecutionLog order by TimeStart DESC  
  
```  
  
 <span data-ttu-id="a080f-294">A tabela a seguir descreve os dados capturados no log de execução de relatório</span><span class="sxs-lookup"><span data-stu-id="a080f-294">The following table describes the data that is captured in the report execution log</span></span>  
  
|<span data-ttu-id="a080f-295">Column</span><span class="sxs-lookup"><span data-stu-id="a080f-295">Column</span></span>|<span data-ttu-id="a080f-296">Descrição</span><span class="sxs-lookup"><span data-stu-id="a080f-296">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a080f-297">InstanceName</span><span class="sxs-lookup"><span data-stu-id="a080f-297">InstanceName</span></span>|<span data-ttu-id="a080f-298">Nome da instância de servidor de relatório que manipulou a solicitação.</span><span class="sxs-lookup"><span data-stu-id="a080f-298">Name of the report server instance that handled the request.</span></span>|  
|<span data-ttu-id="a080f-299">ReportID</span><span class="sxs-lookup"><span data-stu-id="a080f-299">ReportID</span></span>|<span data-ttu-id="a080f-300">Identificador do relatório.</span><span class="sxs-lookup"><span data-stu-id="a080f-300">Report identifier.</span></span>|  
|<span data-ttu-id="a080f-301">UserName</span><span class="sxs-lookup"><span data-stu-id="a080f-301">UserName</span></span>|<span data-ttu-id="a080f-302">Identificador do usuário.</span><span class="sxs-lookup"><span data-stu-id="a080f-302">User identifier.</span></span>|  
|<span data-ttu-id="a080f-303">RequestType</span><span class="sxs-lookup"><span data-stu-id="a080f-303">RequestType</span></span>|<span data-ttu-id="a080f-304">Valores possíveis:</span><span class="sxs-lookup"><span data-stu-id="a080f-304">Possible values:</span></span><br /><br /> <span data-ttu-id="a080f-305">True = Uma solicitação de assinatura</span><span class="sxs-lookup"><span data-stu-id="a080f-305">True = A Subscription request</span></span><br /><br /> <span data-ttu-id="a080f-306">False = Uma solicitação interativa</span><span class="sxs-lookup"><span data-stu-id="a080f-306">False= An Interactive request</span></span>|  
|<span data-ttu-id="a080f-307">Formatar</span><span class="sxs-lookup"><span data-stu-id="a080f-307">Format</span></span>|<span data-ttu-id="a080f-308">Formato de renderização.</span><span class="sxs-lookup"><span data-stu-id="a080f-308">Rendering format.</span></span>|  
|<span data-ttu-id="a080f-309">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a080f-309">Parameters</span></span>|<span data-ttu-id="a080f-310">Valores de parâmetro usados em uma execução de relatório.</span><span class="sxs-lookup"><span data-stu-id="a080f-310">Parameter values used for a report execution.</span></span>|  
|<span data-ttu-id="a080f-311">TimeStart</span><span class="sxs-lookup"><span data-stu-id="a080f-311">TimeStart</span></span>|<span data-ttu-id="a080f-312">Horas de início e parada que indicam a duração de um processo de relatório.</span><span class="sxs-lookup"><span data-stu-id="a080f-312">Start and stop times that indicate the duration of a report process.</span></span>|  
|<span data-ttu-id="a080f-313">TimeEnd</span><span class="sxs-lookup"><span data-stu-id="a080f-313">TimeEnd</span></span>||  
|<span data-ttu-id="a080f-314">TimeDataRetrieval</span><span class="sxs-lookup"><span data-stu-id="a080f-314">TimeDataRetrieval</span></span>|<span data-ttu-id="a080f-315">Número de milissegundos gastos na recuperação dos dados, no processamento do relatório e na renderização do relatório.</span><span class="sxs-lookup"><span data-stu-id="a080f-315">Number of milliseconds spent retrieving the data, processing the report, and rendering the report.</span></span>|  
|<span data-ttu-id="a080f-316">TimeProcessing</span><span class="sxs-lookup"><span data-stu-id="a080f-316">TimeProcessing</span></span>||  
|<span data-ttu-id="a080f-317">TimeRendering</span><span class="sxs-lookup"><span data-stu-id="a080f-317">TimeRendering</span></span>||  
|<span data-ttu-id="a080f-318">Fonte</span><span class="sxs-lookup"><span data-stu-id="a080f-318">Source</span></span>|<span data-ttu-id="a080f-319">Fonte da execução de relatório.</span><span class="sxs-lookup"><span data-stu-id="a080f-319">Source of the report execution.</span></span> <span data-ttu-id="a080f-320">Valores possíveis: (1=Ativo, 2=Cache, 3=Instantâneo, 4=Histórico, 5=Adhoc, 6=Sessão, 7=RDCE).</span><span class="sxs-lookup"><span data-stu-id="a080f-320">Possible values: (1=Live, 2=Cache, 3=Snapshot, 4=History, 5=Adhoc, 6=Session, 7=RDCE).</span></span>|  
|<span data-ttu-id="a080f-321">Status</span><span class="sxs-lookup"><span data-stu-id="a080f-321">Status</span></span>|<span data-ttu-id="a080f-322">Valores possíveis: rsSuccess, rsProcessingAborted ou um código de erro.</span><span class="sxs-lookup"><span data-stu-id="a080f-322">Possible values: rsSuccess, rsProcessingAborted, or an error code.</span></span> <span data-ttu-id="a080f-323">Se vários erros ocorrerem, só o primeiro erro será registrado.</span><span class="sxs-lookup"><span data-stu-id="a080f-323">If multiple errors occur, only the first error is recorded.</span></span>|  
|<span data-ttu-id="a080f-324">ByteCount</span><span class="sxs-lookup"><span data-stu-id="a080f-324">ByteCount</span></span>|<span data-ttu-id="a080f-325">Tamanho de relatórios renderizados em bytes.</span><span class="sxs-lookup"><span data-stu-id="a080f-325">Size of rendered reports in bytes.</span></span>|  
|<span data-ttu-id="a080f-326">RowCount</span><span class="sxs-lookup"><span data-stu-id="a080f-326">RowCount</span></span>|<span data-ttu-id="a080f-327">Número de linhas retornadas pelas consultas.</span><span class="sxs-lookup"><span data-stu-id="a080f-327">Number of rows returned from queries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a080f-328">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a080f-328">See Also</span></span>  
 <span data-ttu-id="a080f-329">[Ativar Reporting Services eventos para o log de rastreamento do SharePoint &#40;ULS&#41;](turn-on-reporting-services-events-for-the-sharepoint-trace-log-uls.md) </span><span class="sxs-lookup"><span data-stu-id="a080f-329">[Turn on Reporting Services events for the SharePoint trace log &#40;ULS&#41;](turn-on-reporting-services-events-for-the-sharepoint-trace-log-uls.md) </span></span>  
 <span data-ttu-id="a080f-330">[Fontes e arquivos de log do Reporting Services](../report-server/reporting-services-log-files-and-sources.md) </span><span class="sxs-lookup"><span data-stu-id="a080f-330">[Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md) </span></span>  
 [<span data-ttu-id="a080f-331">Referência de erros e eventos &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a080f-331">Errors and Events Reference &#40;Reporting Services&#41;</span></span>](../troubleshooting/errors-and-events-reference-reporting-services.md)  
  
  
