---
title: 'Lista de verificação: Use o PowerShell para verificar PowerPivot para SharePoint | Microsoft Docs'
ms.custom: ''
ms.date: 07/20/2020
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 73a13f05-3450-411f-95f9-4b6167cc7607
author: minewiskan
ms.author: owend
ms.openlocfilehash: 001b3fae82851b9ec08b0383bb3db9e6d011ae32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679595"
---
# <a name="checklist-use-powershell-to-verify-powerpivot-for-sharepoint"></a><span data-ttu-id="58336-102">Lista de verificação: use o PowerShell para verificar o PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="58336-102">CheckList: Use PowerShell to Verify PowerPivot for SharePoint</span></span>
  <span data-ttu-id="58336-103">Nenhuma instalação do [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] ou operação de recuperação será completa sem um teste de verificação rigoroso que confirme o funcionamento correto dos serviços e dos dados.</span><span class="sxs-lookup"><span data-stu-id="58336-103">No [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] installation or recovery operation is complete without a solid verification test pass that confirms your services and data are operational.</span></span> <span data-ttu-id="58336-104">Neste artigo, mostramos como executar essas etapas usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="58336-104">In this article, we show you how to perform these steps using Windows PowerShell.</span></span> <span data-ttu-id="58336-105">Colocamos cada etapa em sua própria seção para que você possa ir diretamente para as tarefas específicas.</span><span class="sxs-lookup"><span data-stu-id="58336-105">We put each step into its own section so that you can go straight to specific tasks.</span></span> <span data-ttu-id="58336-106">Por exemplo, execute o script na seção [Bancos de dados](#bkmk_databases) deste tópico para verificar o nome dos bancos de dados de conteúdo e aplicativo de serviço se quiser agendá-los para manutenção ou backup.</span><span class="sxs-lookup"><span data-stu-id="58336-106">For example, run the script in the [Databases](#bkmk_databases) section of this topic to verify the name of the service application and content databases if you want to schedule them for maintenance or backup.</span></span>

|||
|-|-|
|<span data-ttu-id="58336-107">![Conteúdo relacionado ao PowerShell](../../../reporting-services/media/rs-powershellicon.jpg "Conteúdo relacionado ao PowerShell")</span><span class="sxs-lookup"><span data-stu-id="58336-107">![PowerShell related content](../../../reporting-services/media/rs-powershellicon.jpg "PowerShell related content")</span></span>|<span data-ttu-id="58336-108">Um script completo do PowerShell é incluído na parte final do tópico.</span><span class="sxs-lookup"><span data-stu-id="58336-108">A full PowerShell script is included at the bottom of the topic.</span></span> <span data-ttu-id="58336-109">Use o script completo como ponto de partida para criar um script personalizado para fazer a auditoria da implantação completa do [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="58336-109">Use the full script as a starting point to build a custom script for auditing your full [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] deployment.</span></span>|

||
|-|
|<span data-ttu-id="58336-110">**[!INCLUDE[applies](../../../includes/applies-md.md)]** SharePoint 2013 &#124; SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="58336-110">**[!INCLUDE[applies](../../../includes/applies-md.md)]**  SharePoint 2013 &#124; SharePoint 2010</span></span>|

 <span data-ttu-id="58336-111">**Neste tópico**: os itens indicados após o sumário correspondem às áreas do diagrama.</span><span class="sxs-lookup"><span data-stu-id="58336-111">**In this topic**: The lettered items in the following the TOC correspond to areas of the diagram.</span></span> <span data-ttu-id="58336-112">O diagrama ilustra os</span><span class="sxs-lookup"><span data-stu-id="58336-112">The diagram illustrates the</span></span>

|||
|-|-|
|[<span data-ttu-id="58336-113">Preparar o ambiente do PowerShell</span><span class="sxs-lookup"><span data-stu-id="58336-113">Prepare your PowerShell environment</span></span>](#bkmk_prerequisites)<br /><br /> [<span data-ttu-id="58336-114">Sintomas e ações recomendadas</span><span class="sxs-lookup"><span data-stu-id="58336-114">Symptoms and Recommended Actions</span></span>](#bkmk_symptoms)<br /><br /> <span data-ttu-id="58336-115">**(A)** [Serviço Windows do Analysis Services](#bkmk_windows_service)</span><span class="sxs-lookup"><span data-stu-id="58336-115">**(A)** [Analysis Services Windows Service](#bkmk_windows_service)</span></span><br /><br /> <span data-ttu-id="58336-116">**(B)** [PowerPivotSystemService e PowerPivotEngineService](#bkmk_engine_and_system_service)</span><span class="sxs-lookup"><span data-stu-id="58336-116">**(B)** [PowerPivotSystemService and PowerPivotEngineService](#bkmk_engine_and_system_service)</span></span><br /><br /> <span data-ttu-id="58336-117">**(C)** [Aplicativos de serviço e proxies do PowerPivot](#bkmk_powerpivot_service_application)</span><span class="sxs-lookup"><span data-stu-id="58336-117">**(C)** [PowerPivot Service Application(s) and proxies](#bkmk_powerpivot_service_application)</span></span><br /><br /> <span data-ttu-id="58336-118">**(D)** [Bancos de dados](#bkmk_databases)</span><span class="sxs-lookup"><span data-stu-id="58336-118">**(D)** [Databases](#bkmk_databases)</span></span><br /><br /> [<span data-ttu-id="58336-119">Recursos do SharePoint</span><span class="sxs-lookup"><span data-stu-id="58336-119">SharePoint Features</span></span>](#bkmk_features)<br /><br /> [<span data-ttu-id="58336-120">Trabalhos de timer</span><span class="sxs-lookup"><span data-stu-id="58336-120">Timer Jobs</span></span>](#bkmk_timer_jobs)<br /><br /> [<span data-ttu-id="58336-121">Regras de integridade</span><span class="sxs-lookup"><span data-stu-id="58336-121">Health Rules</span></span>](#bkmk_health_rules)<br /><br /> <span data-ttu-id="58336-122">**(E)** [Logs do Windows e do ULS](#bkmk_logs)</span><span class="sxs-lookup"><span data-stu-id="58336-122">**(E)** [Windows and ULS Logs](#bkmk_logs)</span></span><br /><br /> [<span data-ttu-id="58336-123">Provedor MSOLAP</span><span class="sxs-lookup"><span data-stu-id="58336-123">MSOLAP Provider</span></span>](#bkmk_msolap)<br /><br /> [<span data-ttu-id="58336-124">Biblioteca de cliente ADOMD.Net</span><span class="sxs-lookup"><span data-stu-id="58336-124">ADOMD.Net client Library</span></span>](#bkmk_adomd)<br /><br /> [<span data-ttu-id="58336-125">Regras de coleta de dados de integridade</span><span class="sxs-lookup"><span data-stu-id="58336-125">Health Data Collection Rules</span></span>](#bkmk_health_collection)<br /><br /> [<span data-ttu-id="58336-126">Soluções</span><span class="sxs-lookup"><span data-stu-id="58336-126">Solutions</span></span>](#bkmk_solutions)<br /><br /> [<span data-ttu-id="58336-127">Etapas de verificação manual</span><span class="sxs-lookup"><span data-stu-id="58336-127">Manual Verification Steps</span></span>](#bkmk_manual)<br /><br /> [<span data-ttu-id="58336-128">Mais recursos</span><span class="sxs-lookup"><span data-stu-id="58336-128">More Resources</span></span>](#bkmk_more_resources)<br /><br /> [<span data-ttu-id="58336-129">Script completo do PowerShell</span><span class="sxs-lookup"><span data-stu-id="58336-129">Full PowerShell Script</span></span>](#bkmk_full_script)|<span data-ttu-id="58336-130">![verificação de powershell do powerpivot](../../../sql-server/install/media/ssas-powershell-component-verification.png "verificação de powershell do powerpivot")</span><span class="sxs-lookup"><span data-stu-id="58336-130">![powershell verification of powerpivot](../../../sql-server/install/media/ssas-powershell-component-verification.png "powershell verification of powerpivot")</span></span>|

##  <a name="prepare-your-powershell-environment"></a><a name="bkmk_prerequisites"></a> <span data-ttu-id="58336-131">Preparar o ambiente do PowerShell</span><span class="sxs-lookup"><span data-stu-id="58336-131">Prepare your PowerShell environment</span></span>
 <span data-ttu-id="58336-132">As etapas desta seção preparam o ambiente do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="58336-132">The steps in this section prepare your PowerShell environment.</span></span> <span data-ttu-id="58336-133">As etapas podem não ser necessárias, dependendo de como o ambiente de script está configurado no momento.</span><span class="sxs-lookup"><span data-stu-id="58336-133">The steps may not be required, depending on how your scripting environment is currently configured.</span></span>

 <span data-ttu-id="58336-134">**Permissões do PowerShell**</span><span class="sxs-lookup"><span data-stu-id="58336-134">**PowerShell Permissions**</span></span>

 <span data-ttu-id="58336-135">Abra uma janela do PowerShell ou o ISE (Ambiente de Script Integrado) do PowerShell com **privilégios administrativos**.</span><span class="sxs-lookup"><span data-stu-id="58336-135">Open a Powershell window or the PowerShell ISE (Integrated Scripting Environment) with **administrative privileges**.</span></span> <span data-ttu-id="58336-136">Se você não tiver privilégios administrativos ao executar comandos, receberá uma mensagem de erro semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="58336-136">If you do not have administrative privileges when you run commands, you will see an error message similar to the following:</span></span>

 <span data-ttu-id="58336-137">Get-SPLogEvent: você precisa ter **privilégios de administrador** no computador para executar este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="58336-137">Get-SPLogEvent : You need to have Machine **administrator privileges** to run this cmdlet.</span></span>

 <span data-ttu-id="58336-138">**Módulo do SharePoint e do [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="58336-138">**SharePoint and [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)]** Module</span></span>

 <span data-ttu-id="58336-139">Se uma mensagem de erro semelhante à seguinte for exibida quando você executar cmdlets relacionados ao SharePoint, execute o comando Add-PSSnapin:</span><span class="sxs-lookup"><span data-stu-id="58336-139">If you see an error message similar to the following when you run SharePoint related cmdlets, run the Add-PSSnapin command:</span></span>

 <span data-ttu-id="58336-140">O termo “Get-PowerPivotSystemService” **não é reconhecido como nome de um cmdlet**, uma função, um arquivo de script nem um programa operável.</span><span class="sxs-lookup"><span data-stu-id="58336-140">The term 'Get-PowerPivotSystemService' **is not recognized as the name of a cmdlet**, function, script file, or operable program.</span></span> <span data-ttu-id="58336-141">Verifique a ortografia do nome ou se um caminho foi incluído, verifique se ele está correto e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="58336-141">Check the spelling of the name, or if a path was included, verify that the path is correct and try again.</span></span>

```
Add-PSSnapin Microsoft.Sharepoint.Powershell -EA 0
```

 <span data-ttu-id="58336-142">**Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="58336-142">**Windows PowerShell**</span></span>

 <span data-ttu-id="58336-143">Para obter mais informações sobre o PowerShell ISE, consulte [Introdução ao Windows PowerShell ISE](https://technet.microsoft.com/library/dd315244.aspx) e [Usar o Windows PowerShell para administrar o SharePoint 2013](https://technet.microsoft.com/library/ee806878\(v=office.15\).aspx).</span><span class="sxs-lookup"><span data-stu-id="58336-143">For more information on the PowerShell ISE, see [Introducing the Windows PowerShell ISE](https://technet.microsoft.com/library/dd315244.aspx) and [Use Windows PowerShell to administer SharePoint 2013](https://technet.microsoft.com/library/ee806878\(v=office.15\).aspx).</span></span>

|||
|-|-|
|<span data-ttu-id="58336-144">![powerpivot no conjunto geral de aplicativos do sharepoint](../../../sql-server/install/media/ssas-powerpivot-logo.png "powerpivot no conjunto geral de aplicativos do sharepoint")</span><span class="sxs-lookup"><span data-stu-id="58336-144">![powerpivot in sharepoint general application set](../../../sql-server/install/media/ssas-powerpivot-logo.png "powerpivot in sharepoint general application set")</span></span>|<span data-ttu-id="58336-145">Se desejar, você pode verificar a maioria dos componentes na Administração Central, usando o painel de gerenciamento do [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="58336-145">You can optionally verify a majority of the components in Central Administration, using the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] management dashboard.</span></span> <span data-ttu-id="58336-146">Para abrir o painel na Administração Central, clique em **Configurações Gerais do Aplicativo**e clique em **Painel de Gerenciamento** no **PowerPivot**.</span><span class="sxs-lookup"><span data-stu-id="58336-146">To open the dashboard in Central Administration, click **General Application Settings**, and then click **Management Dashboard** in the **PowerPivot**.</span></span> <span data-ttu-id="58336-147">Para obter mais informações sobre o painel, consulte [PowerPivot Management Dashboard and Usage Data](../../power-pivot-sharepoint/power-pivot-management-dashboard-and-usage-data.md).</span><span class="sxs-lookup"><span data-stu-id="58336-147">For more information on the dashboard, see [PowerPivot Management Dashboard and Usage Data](../../power-pivot-sharepoint/power-pivot-management-dashboard-and-usage-data.md).</span></span>|

##  <a name="symptoms-and-recommended-actions"></a><a name="bkmk_symptoms"></a><span data-ttu-id="58336-148">Sintomas e ações recomendadas</span><span class="sxs-lookup"><span data-stu-id="58336-148">Symptoms and Recommended Actions</span></span>
 <span data-ttu-id="58336-149">A tabela a seguir é uma lista de sintomas ou problemas e a ação sugerida deste tópico para ajudar você a resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="58336-149">The following table is a list of symptoms or issues and the suggested section of this topic to consult to help you resolve the issue.</span></span>

|<span data-ttu-id="58336-150">Sintoma</span><span class="sxs-lookup"><span data-stu-id="58336-150">Symptom</span></span>|<span data-ttu-id="58336-151">Consulte a seção</span><span class="sxs-lookup"><span data-stu-id="58336-151">See section</span></span>|
|-------------|-----------------|
|<span data-ttu-id="58336-152">A atualização de dados não está em execução</span><span class="sxs-lookup"><span data-stu-id="58336-152">Data refresh is not running</span></span>|<span data-ttu-id="58336-153">Consulte a seção [Timer Jobs](#bkmk_timer_jobs) e verifique se o **Trabalho de timer online de atualização de dados PowerPivot** está online.</span><span class="sxs-lookup"><span data-stu-id="58336-153">See the section [Timer Jobs](#bkmk_timer_jobs) and verify the **Online PowerPivot Data Refresh Timer Job** is online.</span></span>|
|<span data-ttu-id="58336-154">Os dados do painel de gerenciamento são antigos</span><span class="sxs-lookup"><span data-stu-id="58336-154">Management dashboard data is old</span></span>|<span data-ttu-id="58336-155">Consulte a seção [Trabalhos de timer](#bkmk_timer_jobs) e verifique se o **Trabalho de timer de processamento do painel de gerenciamento** está online.</span><span class="sxs-lookup"><span data-stu-id="58336-155">See the section [Timer Jobs](#bkmk_timer_jobs) and verify the **Management Dashboard Processing Timer Job** is online.</span></span>|
|<span data-ttu-id="58336-156">Algumas partes do Painel de Gerenciamento</span><span class="sxs-lookup"><span data-stu-id="58336-156">Some portions of the Management Dashboard</span></span>|<span data-ttu-id="58336-157">Se você instalar o PowerPivot para SharePoint em um farm que tenha a topologia de Administração Central, sem Serviços do Excel ou PowerPivot para SharePoint, deverá baixar e instalar a biblioteca cliente do Microsoft ADOMD.NET se quiser acesso completo aos relatórios internos no painel de gerenciamento PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="58336-157">If you install PowerPivot for SharePoint into a farm that has the topology of Central Administration, without Excel Services or PowerPivot for SharePoint, you must download and install the Microsoft ADOMD.NET client library if you want full access to the built-in reports in the PowerPivot management dashboard.</span></span> <span data-ttu-id="58336-158">Alguns relatórios no painel usam ADOMD.NET para acessar dados internos que fornecem dados de relação sobre o processamento de consultas do PowerPivot e a integridade de servidor no farm.</span><span class="sxs-lookup"><span data-stu-id="58336-158">Some reports in the dashboard use ADOMD.NET to access internal data that provides reporting data on PowerPivot query processing and server health in the farm.</span></span> <span data-ttu-id="58336-159">Veja a seção [Biblioteca de cliente do ADOMD.Net](#bkmk_adomd) e o tópico [Instalar o ADOMD.NET em servidores Web front-end executando a Administração Central](../../../sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="58336-159">See the section [ADOMD.Net client Library](#bkmk_adomd) and the topic [Install ADOMD.NET on Web Front-End Servers Running Central Administration](../../../sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md).</span></span>|
|\<future content>||

##  <a name="analysis-services-windows-service"></a><a name="bkmk_windows_service"></a> <span data-ttu-id="58336-160">Serviço Windows do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="58336-160">Analysis Services Windows Service</span></span>
 <span data-ttu-id="58336-161">O script nesta seção verifica a instância do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] no modo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="58336-161">The script in this section verifies the instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in SharePoint mode.</span></span> <span data-ttu-id="58336-162">Verifique se o serviço está **em execução**.</span><span class="sxs-lookup"><span data-stu-id="58336-162">Verify the service is **running**.</span></span>

```powershell
Get-Service | Select name, displayname, status | Where {$_.Name -eq "msolap`$powerpivot"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name              DisplayName                                Status
----              -----------                                ------
MSOLAP$POWERPIVOT SQL Server Analysis Services (POWERPIVOT) Running
```

##  <a name="powerpivotsystemservice-and-powerpivotengineservice"></a><a name="bkmk_engine_and_system_service"></a><span data-ttu-id="58336-163">PowerPivotSystemService e PowerPivotEngineService</span><span class="sxs-lookup"><span data-stu-id="58336-163">PowerPivotSystemService and PowerPivotEngineService</span></span>
 <span data-ttu-id="58336-164">Os scripts desta seção verificam os serviços de sistema do [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="58336-164">The scripts in this section verify the [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] system services.</span></span> <span data-ttu-id="58336-165">Há um serviço de sistema para uma implantação do SharePoint 2013 e dois serviços para uma implantação do SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="58336-165">There is one system service for a SharePoint 2013 deployment and two services for a SharePoint 2010 deployment.</span></span>

 <span data-ttu-id="58336-166">**PowerPivotSystemService**</span><span class="sxs-lookup"><span data-stu-id="58336-166">**PowerPivotSystemService**</span></span>

 <span data-ttu-id="58336-167">Verifique se o status é **online**.</span><span class="sxs-lookup"><span data-stu-id="58336-167">Verify the Status is **Online**.</span></span>

```powershell
Get-PowerPivotSystemService | Select typename, status, applications, farm | Format-Table -Property * -AutoSize | Out-Default
```

```Output
TypeName                                  Status Applications                             Farm
--------                                  ------ ------------                             ----
SQL Server PowerPivot Service Application Online {Default PowerPivot Service Application} SPFarm Name=SharePoint_Config_77d8ab0744a34e8aa27c806a2b8c760c
```

 <span data-ttu-id="58336-168">**PowerPivotEngineService**</span><span class="sxs-lookup"><span data-stu-id="58336-168">**PowerPivotEngineService**</span></span>

> [!NOTE]
>  <span data-ttu-id="58336-169">**Ignore este script se** você estiver usando o SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="58336-169">**Skip this script if** you are using SharePoint 2013.</span></span> <span data-ttu-id="58336-170">O PowerPivotEngineService não faz parte de uma implantação do SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="58336-170">The PowerPivotEngineService is not part of a SharePoint 2013 deployment.</span></span> <span data-ttu-id="58336-171">Se você executar o cmdlet Get-PowerPivot**Engine**Service no SharePoint 2013, verá uma mensagem de erro semelhante à seguinte.</span><span class="sxs-lookup"><span data-stu-id="58336-171">If you run the Get-PowerPivot**Engine**Service cmdlet on SharePoint 2013, you will see an error message similar to the following.</span></span> <span data-ttu-id="58336-172">Essa mensagem de erro será retornada mesmo se você tiver executado o comando Add-PSSnapin descrito na seção de pré-requisitos deste tópico.</span><span class="sxs-lookup"><span data-stu-id="58336-172">This error message is returned even if you have run the Add-PSSnapin command described in the prerequisites section of this topic.</span></span>
> 
>  <span data-ttu-id="58336-173">O termo 'Get-PowerPivotEngineService' não é reconhecido como o nome de um cmdlet</span><span class="sxs-lookup"><span data-stu-id="58336-173">The term 'Get-PowerPivotEngineService' is not recognized as the name of a cmdlet</span></span>

 <span data-ttu-id="58336-174">Em uma implantação do SharePoint 2010, verifique se o status é **Online**.</span><span class="sxs-lookup"><span data-stu-id="58336-174">In a SharePoint 2010 deployment, verify the status is **Online**.</span></span>

```powershell
Get-PowerPivotEngineService | Select typename, status, name, instances, farm | Format-Table -Property * -AutoSize | Out-Default
```

```Output
TypeName  : SQL Server Analysis Services
Status    : Online
Name      : MSOLAP$POWERPIVOT
Instances : {POWERPIVOT}
Farm      : SPFarm Name=SharePoint_Config
```

##  <a name="powerpivot-service-applications-and-proxies"></a><a name="bkmk_powerpivot_service_application"></a><span data-ttu-id="58336-175">Aplicativos de serviço PowerPivot e proxies</span><span class="sxs-lookup"><span data-stu-id="58336-175">PowerPivot Service Application(s) and proxies</span></span>
 <span data-ttu-id="58336-176">Verifique se o status é **Online**.</span><span class="sxs-lookup"><span data-stu-id="58336-176">Verify the status is **Online**.</span></span> <span data-ttu-id="58336-177">O aplicativo de Serviços do Excel não usa uma banco de dados de aplicativo de serviço e, portanto, o cmdlet não retorna um nome de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="58336-177">The Excel Services Application does not use a service application database and therefore the cmdlet does not return a database name.</span></span> <span data-ttu-id="58336-178">Observe o banco de dados usado pelo aplicativo de serviço do [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] , para que você possa verificar se o banco de dados está online na seção de banco de dados mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="58336-178">Note the database used by the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] service application so you can verify the database is online in the database section later in this topic.</span></span>

 <span data-ttu-id="58336-179">**Aplicativos de serviço do Excel e do PowerPivot**</span><span class="sxs-lookup"><span data-stu-id="58336-179">**PowerPivot and Excel Service Application(s)**</span></span>

 <span data-ttu-id="58336-180">Em uma implantação do SharePoint 2010, verifique se o status é **Online**.</span><span class="sxs-lookup"><span data-stu-id="58336-180">For a SharePoint 2010 deployment, verify the status is **Online**.</span></span>

```powershell
Get-PowerPivotServiceApplication | Select typename,name, status, unattendedaccount, applicationpool, farm, database
Get-SPExcelServiceApplication | Select typename, DisplayName, status
```

```Output
TypeName          : PowerPivot Service Application
Name              : PowerPivotServiceApplication1
Status            : Online
UnattendedAccount : PowerPivotUnattendedAccount
ApplicationPool   : SPIisWebServiceApplicationPool Name=sqlbi_serviceapp
Farm              : SPFarm Name=SharePoint_Config
Database          : GeminiServiceDatabase Name=PowerPivotServiceApplication1_19648f3f2c944e27acdc6c20aab8487a

TypeName    : Excel Services Application Web Service Application
DisplayName : Excel Services Application
Status      : Online
```

 <span data-ttu-id="58336-181">**Pool de aplicativos de serviço**</span><span class="sxs-lookup"><span data-stu-id="58336-181">**Service Application Pool**</span></span>

> [!NOTE]
>  <span data-ttu-id="58336-182">O exemplo de código a seguir retorna primeiro a propriedade applicationpool do aplicativo de serviço padrão do [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="58336-182">The following code sample first returns the applicationpool property of the default [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] service application.</span></span> <span data-ttu-id="58336-183">O nome é analisado na cadeia de caracteres e usado para obter o status do objeto do pool de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="58336-183">The name is parsed from the string and used to get the status of the application pool object.</span></span>
> 
>  <span data-ttu-id="58336-184">Verifique se o status é **online**.</span><span class="sxs-lookup"><span data-stu-id="58336-184">Verify the Status is **Online**.</span></span> <span data-ttu-id="58336-185">Se o status não estiver online ou você vir "erro http" ao navegar no [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] site, verifique se as credenciais de identidade nos pools de aplicativos do IIS ainda estão corretas.</span><span class="sxs-lookup"><span data-stu-id="58336-185">If the status is not Online or you see "http error" when you browse the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] site, verify the identity credentials in the IIS application pools are still correct.</span></span> <span data-ttu-id="58336-186">O nome do pool do IIS é o valor da propriedade ID retornada pelo comando Get-SPServiceApplicationPool.</span><span class="sxs-lookup"><span data-stu-id="58336-186">The IIS pool name will is the value of the ID property returned by the Get-SPServiceApplicationPool command.</span></span>

```powershell
$poolname = [string](Get-PowerPivotServiceApplication | Select -Property applicationpool)
$position = $poolname.lastindexof("=")
$poolname = $poolname.substring($position+1)
$poolname = $poolname.substring(0,$poolname.length-1)

Get-SPServiceApplicationPool | Select name, status, processaccountname, id | Where {$_.Name -eq $poolname} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name                           Status ProcessAccountName Id
----                           ------ ------------------ ------- 
SharePoint Web Services System Online DOMAIN\account     89b50ec3-49e3-4de7-881a-2cec4b8b73ea
```

 ![Observação](../../../reporting-services/media/rs-fyinote.png "observação") O pool de aplicativos também pode ser verificado na página Administração Central **gerenciar aplicativos de serviço**. <span data-ttu-id="58336-188">Clique no nome do aplicativo de serviço e, em seguida, clique em **propriedades** na faixa de opções.</span><span class="sxs-lookup"><span data-stu-id="58336-188">Click the name of the service application and then click **properties** in the ribbon.</span></span>

 <span data-ttu-id="58336-189">**Proxies do aplicativo de serviço do Excel e do PowerPivot**</span><span class="sxs-lookup"><span data-stu-id="58336-189">**PowerPivot and Excel Service Application proxies**</span></span>

 <span data-ttu-id="58336-190">Verifique se o status é **online**.</span><span class="sxs-lookup"><span data-stu-id="58336-190">Verify the Status is **Online**.</span></span>

```powershell
Get-SPServiceApplicationProxy | Select typename, status, unattendedaccount, displayname | Where {$_.TypeName -Like "*powerpivot*" -Or $_.TypeName -Like "*excel services*"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
TypeName                                                 Status UnattendedAccount           DisplayName
--------                                                 ------ -----------------           -----------
PowerPivot Service Application Proxy                     Online PowerPivotUnattendedAccount PowerPivotServiceApplication1
Excel Services Application Web Service Application Proxy Online                             Excel Services Application
```

##  <a name="databases"></a><a name="bkmk_databases"></a> <span data-ttu-id="58336-191">Bancos de dados</span><span class="sxs-lookup"><span data-stu-id="58336-191">Databases</span></span>
 <span data-ttu-id="58336-192">O script a seguir retorna o status dos bancos de dados de aplicativo de serviço e de todos os bancos de dados de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="58336-192">The following script returns the status of the service application databases and all content databases.</span></span> <span data-ttu-id="58336-193">Verifique se o status é **Online**.</span><span class="sxs-lookup"><span data-stu-id="58336-193">Verify the status is **Online**.</span></span>

```powershell
Get-SPDatabase | Select name, status, server, typename | Where {$_.TypeName -eq "content database" -Or $_.TypeName -Like "*Gemini*"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name                                                                       Status Server                  TypeName 
----                                                                       ------ ------                  -------- 
DefaultPowerPivotServiceApplicationDB-38422181-2b68-4ab2-b2bb-9c00c39e5a5e Online SPServer Name=TESTSERVER Microsoft.AnalysisServices.SPAddin.GeminiServiceDatabase
DefaultWebApplicationDB-f0db1a8e-4c22-408c-b9b9-153bd74b0312               Online TESTSERVER\POWERPIVOT    Content Database 
SharePoint_Admin_3cadf0b098bf49e0bb15abd487f5c684                          Online TESTSERVER\POWERPIVOT    Content Database
```

##  <a name="sharepoint-features"></a><a name="bkmk_features"></a><span data-ttu-id="58336-194">Recursos do SharePoint</span><span class="sxs-lookup"><span data-stu-id="58336-194">SharePoint Features</span></span>
 <span data-ttu-id="58336-195">Verifique se o site e os recursos do farm estão online.</span><span class="sxs-lookup"><span data-stu-id="58336-195">Verify the site, web, and farm features are online.</span></span>

```powershell
Get-SPFeature | Select displayname, status, scope, farm | Where {$_.displayName -Like "*powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
DisplayName     Status Scope Farm                         
-----------     ------ ----- ----                         
PowerPivotSite  Online  Site SPFarm Name=SharePoint_Config
PowerPivotAdmin Online   Web SPFarm Name=SharePoint_Config
PowerPivot      Online  Farm SPFarm Name=SharePoint_Config
```

##  <a name="timer-jobs"></a><a name="bkmk_timer_jobs"></a><span data-ttu-id="58336-196">Trabalhos de timer</span><span class="sxs-lookup"><span data-stu-id="58336-196">Timer Jobs</span></span>
 <span data-ttu-id="58336-197">Verifique se os trabalhos de timer estão **Online**.</span><span class="sxs-lookup"><span data-stu-id="58336-197">Verify the Time Jobs are **Online**.</span></span> <span data-ttu-id="58336-198">O EngineService do [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] não está instalado no SharePoint 2013, portanto, o script não listará os trabalhos de timer do EngineService em uma implantação do SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="58336-198">The [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] EngineService is not installed on SharePoint 2013, therefore the script will not list EngineService timer jobs in a SharePoint 2013 deployment.</span></span>

```powershell
Get-SPTimerJob | Where {$_.service -Like "*power*" -Or $_.service -Like "*mid*"} | Select status, displayname, LastRunTime, service | Format-Table -Property * -AutoSize | Out-Default
```

```Output
      Status DisplayName                                                                          LastRunTime          Service                             
------ -----------                                                                          -----------          -------                             
Online Health Analysis Job (Daily, SQL Server Analysis Services, All Servers)               4/9/2014 12:00:01 AM EngineService Name=MSOLAP$POWERPIVOT
Online Health Analysis Job (Hourly, SQL Server Analysis Services, All Servers)              4/9/2014 1:00:01 PM  EngineService Name=MSOLAP$POWERPIVOT
Online Health Analysis Job (Weekly, SQL Server Analysis Services, All Servers)              4/6/2014 12:00:10 AM EngineService Name=MSOLAP$POWERPIVOT
Online PowerPivot Management Dashboard Processing Timer Job                                 4/8/2014 3:45:38 AM  MidTierService
Online PowerPivot Health Statistics Collector Timer Job                                     4/9/2014 1:00:12 PM  MidTierService
Online PowerPivot Data Refresh Timer Job                                                    4/9/2014 1:09:36 PM  MidTierService
Online Health Analysis Job (Daily, SQL Server PowerPivot Service Application, All Servers)  4/9/2014 12:00:00 AM MidTierService
Online Health Analysis Job (Daily, SQL Server PowerPivot Service Application, Any Server)   4/9/2014 12:00:00 AM MidTierService
Online Health Analysis Job (Weekly, SQL Server PowerPivot Service Application, All Servers) 4/6/2014 12:00:03 AM MidTierService
Online Health Analysis Job (Weekly, SQL Server PowerPivot Service Application, Any Server)  4/6/2014 12:00:03 AM MidTierService
Online PowerPivot Setup Extension Timer Job                                                 4/1/2014 1:40:31 AM  MidTierService
```

##  <a name="health-rules"></a><a name="bkmk_health_rules"></a><span data-ttu-id="58336-199">Regras de integridade</span><span class="sxs-lookup"><span data-stu-id="58336-199">Health Rules</span></span>
 <span data-ttu-id="58336-200">Há menos regras em uma implantação do SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="58336-200">There are fewer rules in a SharePoint 2013 deployment.</span></span> <span data-ttu-id="58336-201">Para obter uma lista completa de regras para cada ambiente do SharePoint e uma explicação de como usar as regras, consulte [regras de integridade do PowerPivot – configurar](../../power-pivot-sharepoint/configure-power-pivot-health-rules.md).</span><span class="sxs-lookup"><span data-stu-id="58336-201">For a full list of rules for each SharePoint environment and an explanation of how to use the rules, see [PowerPivot Health Rules - Configure](../../power-pivot-sharepoint/configure-power-pivot-health-rules.md).</span></span>

```powershell
Get-SPHealthAnalysisRule | Select name, enabled, summary | Where {$_.summary -Like "*power*"}  | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name                          Enabled Summary
----                          ------- -------         
SecondaryLogonHealthRule         True PowerPivot:  Secondary Logon service (seclogon) is disabled
DataRefreshTimerJobHealthRule    True PowerPivot: The PowerPivot Data Refresh timer job is disabled.
ASUsageLoadHealthRule            True PowerPivot: The ratio of load events to connections is too high.
ASMiniDumpHealthRule             True PowerPivot: One or more minidump files were found in the Logs directory, indicating a program crash
ASUsageCubeRule                  True PowerPivot: Usage data is not getting updated at the expected frequency.
ASADOMDNETHealthRule             True PowerPivot: ADOMD.NET is not installed on a standalone WFE that is configured for central admin
MidTierAcctReadPermissionRule    True PowerPivot: MidTier process account should have 'Full Read' permission on all associated SPWebApplications.
```

##  <a name="windows-and-uls-logs"></a><a name="bkmk_logs"></a><span data-ttu-id="58336-202">Logs do Windows e do ULS</span><span class="sxs-lookup"><span data-stu-id="58336-202">Windows and ULS Logs</span></span>
 <span data-ttu-id="58336-203">**Log de eventos do Windows**</span><span class="sxs-lookup"><span data-stu-id="58336-203">**Windows event log**</span></span>

 <span data-ttu-id="58336-204">O comando a seguir pesquisará o log de eventos do Windows em busca dos eventos relacionados à instância do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] no modo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="58336-204">The following command will search the windows event log for events related to the instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in SharePoint mode.</span></span> <span data-ttu-id="58336-205">Para obter informações sobre como desabilitar eventos ou alterar o nível de evento, consulte [configurar e exibir arquivos de log do SharePoint e log de diagnóstico &#40;PowerPivot para SharePoint&#41;](../../power-pivot-sharepoint/configure-and-view-sharepoint-and-diagnostic-logging.md).</span><span class="sxs-lookup"><span data-stu-id="58336-205">For information on disabling events or changing the event level, see [Configure and View SharePoint Log Files  and Diagnostic Logging &#40;PowerPivot for SharePoint&#41;](../../power-pivot-sharepoint/configure-and-view-sharepoint-and-diagnostic-logging.md).</span></span>

 <span data-ttu-id="58336-206">**Nome do serviço:** MSOLAP$POWERPIVOT</span><span class="sxs-lookup"><span data-stu-id="58336-206">**Service Name:** MSOLAP$POWERPIVOT</span></span>

 <span data-ttu-id="58336-207">**Nome de exibição nos Serviços Windows:** SQL Server Analysis Services (POWERPIVOT)</span><span class="sxs-lookup"><span data-stu-id="58336-207">**Display name in Windows Services:** SQL Server Analysis Services (POWERPIVOT)</span></span>

```powershell
Get-EventLog "application" | Where-Object {$_.source -Like "msolap`$powerpivot*"}  | Select timegenerated, entrytype , source, message | Format-Table -property * -AutoSize | Out-Default
```

```Output
TimeGenerated           EntryType Source            Message
-------------           --------- ------            -------
4/16/2014 1:45:19 PM  Information MSOLAP$POWERPIVOT Software usage metrics are disabled.
4/16/2014 1:45:19 PM  Information MSOLAP$POWERPIVOT Service started. Microsoft SQL Server Analysis Services 64 Bit Evaluation (x64) RTM 12.0.1997.5.
4/16/2014 1:45:18 PM  Information MSOLAP$POWERPIVOT The flight recorder was started.
4/14/2014 6:45:37 PM  Information MSOLAP$POWERPIVOT Software usage metrics are disabled.
```

 <span data-ttu-id="58336-208">**Log do ULS do SharePoint, últimas 48 horas**</span><span class="sxs-lookup"><span data-stu-id="58336-208">**SharePoint ULS Log, last 48 hours**</span></span>

 <span data-ttu-id="58336-209">O comando a seguir retornará as mensagens do [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] do log do ULS que foram criadas nas últimas 48 horas.</span><span class="sxs-lookup"><span data-stu-id="58336-209">The following command will return [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] messages from the ULS log that were created in the last 48 hours.</span></span> <span data-ttu-id="58336-210">Ajuste o parâmetro addhours de acordo com as suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="58336-210">Adjust the addhours parameter for your need.</span></span>

```powershell
Get-SPLogEvent -StartTime(Get-Date).AddHours(-48) | Where-Object {$_.Area -eq "powerpivot service" -and $_.level -eq "high"} | Select timestamp, area, category, eventid,level, message | Format-Table -Property * -AutoSize | Out-Default
```

 <span data-ttu-id="58336-211">A seguinte variação do comando retorna apenas eventos de log da categoria **atualização de dados** :</span><span class="sxs-lookup"><span data-stu-id="58336-211">The following variation of the command only returns log events for the **data refresh** category.</span></span>

```powershell
Get-SPLogEvent -starttime(Get-Date).addhours(-48) | Where-Object {$_.category -eq "data refresh" -and $_.level -eq "high"} | Select timestamp, area, category, eventid, level, correlation, message
```

```Output
Timestamp   : 4/14/2014 7:15:01 PM
Area        : PowerPivot Service
Category    : Data Refresh
EventID     : 43
Level       : High
Correlation : 5755879c-7cab-e097-8f80-f27895d44a77
Message     : The following error occurred when working with the service application, Default PowerPivot Service Application. Skipping the service application..

Timestamp   : 4/14/2014 7:15:02 PM
Area        : PowerPivot Service
Category    : Data Refresh
EventID     : 99
Level       : High
Correlation : 5755879c-7cab-e097-8f80-f27895d44a77
Message     : EXCEPTION: System.TimeoutException: The request channel timed out while waiting for a reply after 00:00:47.0625313. Increase the timeout value passed to 
              the call to Request or increase the SendTimeout value on the Binding. The time allotted to this operation may have been a portion of a longer timeout. 
              ---> System.TimeoutException: The HTTP request to 'http://localhost:32843/SecurityTokenServiceApplication/securitytoken.svc/actas' has exceeded the 
              allotted timeout of 00:00:54.5930000. The time allotted to this operation may have been a portion of a longer timeout. ---> System.Net.WebException: The 
              operation has timed out     at System.Net.HttpWebRequest.GetResponse()     at 
              System.ServiceModel.Channels.HttpChannelFactory`1.HttpRequestChannel.HttpChannelRequest.WaitForReply(TimeSpan timeout...
```

##  <a name="msolap-provider"></a><a name="bkmk_msolap"></a><span data-ttu-id="58336-212">Provedor MSOLAP</span><span class="sxs-lookup"><span data-stu-id="58336-212">MSOLAP Provider</span></span>
 <span data-ttu-id="58336-213">Verifique o provedor MSOLAP.</span><span class="sxs-lookup"><span data-stu-id="58336-213">Verify the provider MSOLAP provider.</span></span> [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]<span data-ttu-id="58336-214">e [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)] [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] exigem MSOLAP. 5.</span><span class="sxs-lookup"><span data-stu-id="58336-214">and [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)] [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] require MSOLAP.5.</span></span>

```powershell
$excelApp = Get-SPExcelServiceApplication
Get-SPExcelDataProvider -ExcelServiceApplication $excelApp | Select providerid, providertype, description | Where {$_.providerid -like "msolap*" } | Format-Table -Property * -AutoSize | Out-Default
```

```Output
ProviderId ProviderType Description
---------- ------------ -----------
MSOLAP     Oledb        Microsoft OLE DB Provider for OLAP Services     
MSOLAP.3   Oledb        Microsoft OLE DB Provider for OLAP Services 9.0 
MSOLAP.4   Oledb        Microsoft OLE DB Provider for OLAP Services 10.0
MSOLAP.5   Oledb        Microsoft OLE DB Provider for OLAP Services 11.0
```

 <span data-ttu-id="58336-215">Para saber mais, confira [Instalar o provedor OLE DB do Analysis Services nos servidores do SharePoint](../../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md) e [Adicionar MSOLAP.5 como um provedor de dados confiável aos Serviços do Excel](https://technet.microsoft.com/library/hh758436.aspx).</span><span class="sxs-lookup"><span data-stu-id="58336-215">For more information, see [Install the Analysis Services OLE DB Provider on SharePoint Servers](../../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md) and [Add MSOLAP.5 as a Trusted Data Provider in Excel Services](https://technet.microsoft.com/library/hh758436.aspx).</span></span>

##  <a name="adomdnet-client-library"></a><a name="bkmk_adomd"></a><span data-ttu-id="58336-216">Biblioteca de cliente do ADOMD.Net</span><span class="sxs-lookup"><span data-stu-id="58336-216">ADOMD.Net client Library</span></span>

```powershell
Get-WMIObject -Class win32_product | Where-Object {$_.name -Like "*ado*"} | Select name, version, vendor | Format-Table -Property * -AutoSize | out-default
```

```Output
name                                                  version      vendor
----                                                  -------      ------
Microsoft SQL Server 2008 Analysis Services ADOMD.NET 10.1.2531.0  Microsoft Corporation
Microsoft SQL Server 2005 Analysis Services ADOMD.NET 9.00.1399.06 Microsoft Corporation
```

 <span data-ttu-id="58336-217">Para obter mais informações, confira [Instalar o ADOMD.NET em servidores Web front-end executando a Administração Central](../../../sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="58336-217">For more information, see [Install ADOMD.NET on Web Front-End Servers Running Central Administration](../../../sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md).</span></span>

##  <a name="health-data-collection-rules"></a><a name="bkmk_health_collection"></a><span data-ttu-id="58336-218">Regras de coleta de dados de integridade</span><span class="sxs-lookup"><span data-stu-id="58336-218">Health Data Collection Rules</span></span>
 <span data-ttu-id="58336-219">Verifique se o **Status** é Online e se **Habilitado** está definido como True.</span><span class="sxs-lookup"><span data-stu-id="58336-219">Verify the **Status** is Online and **Enabled** is True.</span></span>

```powershell
Get-SPUsageDefinition | Select name, status, enabled, tablename, DaysToKeepDetailedData | Where {$_.name -Like "powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name                         Status Enabled TableName                   DaysToKeepDetailedData
----                         ------ ------- ---------                   ----------------------
PowerPivot Connections       OnlineTrue AnalysisServicesConnections  14
PowerPivot Load Data Usage   Online    True AnalysisServicesLoads                           14
PowerPivot Query Usage       Online    True AnalysisServicesRequests                        14
PowerPivot Unload Data Usage Online    True AnalysisServicesUnloads                         14
```

 <span data-ttu-id="58336-220">Para obter mais informações, consulte [PowerPivot Usage Data Collection](../../power-pivot-sharepoint/power-pivot-usage-data-collection.md).</span><span class="sxs-lookup"><span data-stu-id="58336-220">For more information, see [PowerPivot Usage Data Collection](../../power-pivot-sharepoint/power-pivot-usage-data-collection.md).</span></span>

##  <a name="solutions"></a><a name="bkmk_solutions"></a><span data-ttu-id="58336-221">Soluções</span><span class="sxs-lookup"><span data-stu-id="58336-221">Solutions</span></span>
 <span data-ttu-id="58336-222">Se os outros componentes estiverem online, você poderá ignorar a verificação das soluções.</span><span class="sxs-lookup"><span data-stu-id="58336-222">If the other components are online then you can skip verifying the solutions.</span></span> <span data-ttu-id="58336-223">Se, no entanto, as regras de integridade estiverem ausentes, verifique se as duas soluções existem e mostravam Verifique se as duas soluções do PowerPivot estão **Online** e **Implantadas**.</span><span class="sxs-lookup"><span data-stu-id="58336-223">If however the Health rules are missing, verify the two solutions exist and showed Verify the two PowerPivot solutions are **Online** and **Deployed**.</span></span>

```powershell
Get-SPSolution | Select name, status, deployed, DeploymentState, DeployedServers | Where {$_.Name -Like "*powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default
```

<span data-ttu-id="58336-224">SharePoint 2013:</span><span class="sxs-lookup"><span data-stu-id="58336-224">SharePoint 2013:</span></span>

```Output
Name                                 Status Deployed        DeploymentState DeployedServers
----                                 ------ --------        --------------- ---------------
powerpivotfarm14solution.wsp         Online     True         GlobalDeployed {UETESTA00}
powerpivotfarmsolution.wsp           Online     True         GlobalDeployed {UETESTA00}
powerpivotwebapplicationsolution.wsp Online     True WebApplicationDeployed {UETESTA00}
```

<span data-ttu-id="58336-225">SharePoint 2010:</span><span class="sxs-lookup"><span data-stu-id="58336-225">SharePoint 2010:</span></span>

```Output
Name                 Status Deployed        DeploymentState DeployedServers 
----                 ------ --------        --------------- --------------- 
powerpivotfarm.wsp   Online     True         GlobalDeployed {uesql11spoint2}
powerpivotwebapp.wsp Online     True WebApplicationDeployed {uesql11spoint2}
```

 <span data-ttu-id="58336-226">Para obter mais informações sobre como implantar soluções do SharePoint, veja [Implantar pacotes de solução (SharePoint Server 2010)](https://technet.microsoft.com/library/cc262995\(v=office.14\).aspx).</span><span class="sxs-lookup"><span data-stu-id="58336-226">For more information on how to deploy SharePoint solutions, see [Deploy solution packages (SharePoint Server 2010)](https://technet.microsoft.com/library/cc262995\(v=office.14\).aspx).</span></span>

##  <a name="manual-verification-steps"></a><a name="bkmk_manual"></a> <span data-ttu-id="58336-227">Etapas de verificação manual</span><span class="sxs-lookup"><span data-stu-id="58336-227">Manual Verification Steps</span></span>
 <span data-ttu-id="58336-228">Esta seção descreve as etapas de verificação que não podem ser concluídas com os cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="58336-228">This section describes verification steps that cannot be completed with PowerShell cmdlets.</span></span>

 <span data-ttu-id="58336-229">**Atualização de dados agendada:** configure a agenda de atualização para uma pasta de trabalho para **Também atualizar o mais rápido possível**.</span><span class="sxs-lookup"><span data-stu-id="58336-229">**Scheduled Data Refresh:** Configure the refresh schedule a workbook to **Also refresh as soon as possible**.</span></span>  <span data-ttu-id="58336-230">Para obter mais informações, consulte a seção "verificar atualização de dados" de [agendar dados de atualização e fontes de dados que não dão suporte à autenticação do Windows &#40;PowerPivot para SharePoint&#41;](../../power-pivot-sharepoint/schedule-data-refresh-and-data-sources-no-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="58336-230">For more information, see the "Verify Data Refresh" section of [Schedule Data Refresh and Data Sources That Do Not Support Windows Authentication &#40;PowerPivot for SharePoint&#41;](../../power-pivot-sharepoint/schedule-data-refresh-and-data-sources-no-windows-authentication.md).</span></span>

##  <a name="more-resources"></a><a name="bkmk_more_resources"></a><span data-ttu-id="58336-231">Mais recursos</span><span class="sxs-lookup"><span data-stu-id="58336-231">More Resources</span></span>
 <span data-ttu-id="58336-232">[Cmdlets de administração do servidor Web (IIS) no Windows PowerShell](https://technet.microsoft.com/library/ee790599.aspx).</span><span class="sxs-lookup"><span data-stu-id="58336-232">[Web Server (IIS) Administration Cmdlets in Windows PowerShell](https://technet.microsoft.com/library/ee790599.aspx).</span></span>

 <span data-ttu-id="58336-233">[PowerShell para verificar serviços, sites do IIS e o status do pool de aplicativos no SharePoint](https://gallery.technet.microsoft.com/office/PowerShell-to-check-a6ed72a0).</span><span class="sxs-lookup"><span data-stu-id="58336-233">[PowerShell to check services, IIS sites and Application Pool status in SharePoint](https://gallery.technet.microsoft.com/office/PowerShell-to-check-a6ed72a0).</span></span>

 <span data-ttu-id="58336-234">[Referência do Windows PowerShell para SharePoint 2013](https://technet.microsoft.com/library/ee890108\(v=office.15\).aspx)</span><span class="sxs-lookup"><span data-stu-id="58336-234">[Windows PowerShell for SharePoint 2013 reference](https://technet.microsoft.com/library/ee890108\(v=office.15\).aspx)</span></span>

 <span data-ttu-id="58336-235">[Referência do Windows PowerShell para SharePoint Foundation 2010](https://technet.microsoft.com/library/ee890105\(v=office.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="58336-235">[Windows PowerShell for SharePoint Foundation 2010 reference](https://technet.microsoft.com/library/ee890105\(v=office.14\).aspx)</span></span>

 <span data-ttu-id="58336-236">[Gerenciar Serviços do Excel com o Windows PowerShell (SharePoint Server 2010)](https://technet.microsoft.com/library/ff191201\(v=office.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="58336-236">[Manage Excel Services with Windows PowerShell (SharePoint Server 2010)](https://technet.microsoft.com/library/ff191201\(v=office.14\).aspx)</span></span>

 [<span data-ttu-id="58336-237">Exibir e ler arquivos de log da Instalação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="58336-237">View and Read SQL Server Setup Log Files</span></span>](../../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md)

 [<span data-ttu-id="58336-238">Usar o cmdlet Get-EvenLog</span><span class="sxs-lookup"><span data-stu-id="58336-238">Use the Get-EvenLog cmdlet</span></span>](https://technet.microsoft.com/library/ee176846.aspx)

##  <a name="full-powershell-script"></a><a name="bkmk_full_script"></a><span data-ttu-id="58336-239">Script completo do PowerShell</span><span class="sxs-lookup"><span data-stu-id="58336-239">Full PowerShell Script</span></span>
 <span data-ttu-id="58336-240">O script a seguir contém todos os comandos das seções anteriores.</span><span class="sxs-lookup"><span data-stu-id="58336-240">The Following script contains all of the commands from the previous sections.</span></span> <span data-ttu-id="58336-241">O script executa os comandos na mesma ordem em que são apresentados neste tópico.</span><span class="sxs-lookup"><span data-stu-id="58336-241">The script runs the commands in the same order as they are presented in this topic.</span></span> <span data-ttu-id="58336-242">O script contém algumas variações opcionais dos comandos observados neste tópico caso você precise de filtragem adicional.</span><span class="sxs-lookup"><span data-stu-id="58336-242">The script contains some optional variations of the commands noted in this topic in case you need additional filtering.</span></span> <span data-ttu-id="58336-243">As variações são desabilitadas com um caractere de comentário (#).</span><span class="sxs-lookup"><span data-stu-id="58336-243">The variations are disabled with a comment character (#).</span></span> <span data-ttu-id="58336-244">O script também inclui algumas instruções para verificar o modo [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] SharePoint.</span><span class="sxs-lookup"><span data-stu-id="58336-244">The script also includes some statements for verifying [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span> <span data-ttu-id="58336-245">As instruções [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] são desabilitadas com um caractere de comentário (#).</span><span class="sxs-lookup"><span data-stu-id="58336-245">The [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] statements are disabled with a comment character (#).</span></span>

```powershell
# This script audits services related to PowerPivot for SharePoint
$starttime = Get-Date
write-host -foregroundcolor DarkGray StartTime $starttime

Write-Host  "Import the SharePoint PowerShell snappin"
Add-PSSnapin Microsoft.Sharepoint.Powershell -EA 0

Write-Host -ForegroundColor Green "Analysis Services Windows Service"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-Service | Select name, displayname, status | Where {$_.Name -eq "msolap`$powerpivot"} | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "PowerPivotEngineService and PowerPivotSystemService"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"

Get-PowerPivotSystemService | Select typename, status, applications, farm | Format-Table -property * -AutoSize | Out-Default
# If needed, you can run the following to compare job definitions specific to the service against the results of the timer job definition section
#Get-PowerPivotSystemService | select -ExpandProperty jobdefinitions | select displayname, schedule, service | format-table -property * -autosize | out-default

Get-PowerPivotEngineService | Select typename, status, name, instances, farm | Format-Table -property * -AutoSize | Out-Default
# If needed, you can run the following to compare job definitions specific to the service against the results of the timer job definition section
#Get-PowerPivotEngineService | select -ExpandProperty jobdefinitions | select displayname, schedule, service | format-table -property * -autosize | out-default

#Write-Host -ForegroundColor Green "Service Instances - optional if you want to associate services with the server"
#Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
#Get-SPServiceInstance | select typename, status, server, service, instance | where {$_.TypeName -like "*powerpivot*" -or $_.TypeName -like "*excel*" -or $_.TypeName -like "*Analysis Services*"} | format-table -property * -autosize | out-default
#Get-PowerPivotEngineServiceInstance  | select typename, ASServername, status, server, service, instance
#Get-PowerPivotSystemServiceInstance  | select typename, ASSServerName, status, server, service, instance

Write-Host -ForegroundColor Green "PowerPivot And Excel Service Applications"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-PowerPivotServiceApplication | Select typename,name, status, unattendedaccount, applicationpool, farm, database
Get-SPExcelServiceApplication | Select typename,  DisplayName, status

#Write-Host ""
Write-Host -ForegroundColor Green "PowerPivot Service Application pool"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
# the following assumes there is only 1 PowerPivot Service Application, and returns that application's pool name.  if you have more than one, use the 2nd version
$poolname = [string](Get-PowerPivotServiceApplication | Select -Property applicationpool)
$position = $poolname.lastindexof("=")
$poolname = $poolname.substring($position+1)
$poolname = $poolname.substring(0,$poolname.length-1)
Get-SPServiceApplicationPool | Select name, status, processaccountname, id | Where {$_.Name -eq $poolname} | Format-Table -Property * -AutoSize | Out-Default

#Write-Host ""
Write-Host -ForegroundColor Green "PowerPivot and Excel Service Application Proxy"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPServiceApplicationProxy |  Select typename, status, unattendedaccount, displayname | Where {$_.TypeName -like "*powerpivot*" -or $_.TypeName -like "*excel services*"} | Format-Table -Property * -AutoSize | Out-Default
#Get-SPServiceApplicationProxy |  select typename, status, unattendedaccount, displayname | where {$_.TypeName -like "*powerpivot*" -or $_.TypeName -like "*Reporting Services*" -or $_.TypeName -like "*excel services*"} | format-table -property * -autosize | out-default

Write-Host -ForegroundColor Green "DATABASES"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPDatabase | Select name, status, server, typename | Where {$_.TypeName -eq "content database" -or $_.TypeName -like "*Gemini*"} | Format-Table -Property * -AutoSize | Out-Default
#Get-SPDatabase | select name, status, server, typename | where {$_.TypeName -eq "content database" -or $_.TypeName -like "*Gemini*" -or $_.TypeName -like "*ReportingServices*"}

Write-Host -ForegroundColor Green "features"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPFeature | Select displayname, status, scope, farm | Where {$_.displayName -like "*powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default
#Get-SPFeature | select displayname, status, scope, farm | where {$_.displayName -like "*powerpivot*" -or $_.displayName -like "*ReportServer*"}  | format-table -property * -autosize | out-default

Write-Host -ForegroundColor Green "Timer Jobs (Job Definitions) -- list is the same as seen in the 'Review timer job definitions' section of the management dashboard"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPTimerJob | Where {$_.service -like "*power*" -or $_.service -like "*mid*"} | Select status, displayname, LastRunTime, service | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "health rules"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPHealthAnalysisRule | Select name, enabled, summary | Where {$_.summary -Like "*power*"}  | Format-Table -Property * -AutoSize | Out-Default

$time = Get-Date
Write-Host -ForegroundColor DarkGray StartTime $starttime
Write-Host -ForegroundColor DarkGray EndTime $time

Write-Host -ForegroundColor Green "Windows Event Log data MSSQL$POWERPIVOT and "
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-EventLog "application" | Where-Object {$_.source -like "msolap`$powerpivot*"}  | Select timegenerated, entrytype , source, message | Format-Table -Property * -autosize | Out-Default
#The following is the same command but with the Inforamtion events filtered out.
#Get-EventLog "application" | Where-Object {$_.source -like "msolap`$powerpivot*" -and ($_.entrytype -match "error" -or $_.entrytype -match "critical" -or $_.entrytype -match "warning")}  |select timegenerated, entrytype , source, message | format-table -property * -autosize | out-default

#Write-Host ""
Write-Host -ForegroundColor Green "ULS Log data"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPLogEvent -StartTime(Get-Date).AddHours(-48) | Where-Object {$_.Area -eq "powerpivot service" -and $_.level -eq "high"} | Select timestamp, area, category, eventid, level, correlation, message | Format-Table -Property * -AutoSize | Out-Default
#the following example filters for the category 'data refresh'
#Get-SPLogEvent -starttime(get-date).addhours(-48) | Where-Object {$_.category -eq "data refresh" -and $_.level -eq "high"} | select timestamp, area, category, eventid, level, correlation, message

$time = Get-Date
Write-Host -ForegroundColor DarkGray StartTime $starttime
Write-Host -ForegroundColor DarkGray EndTime $time

Write-Host -ForegroundColor Green "MSOLAP data provider for Excel Servivces, service application"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
$excelApp = Get-SPExcelServiceApplication
Get-SPExcelDataProvider -ExcelServiceApplication $excelApp | Select providerid, providertype, description | Where {$_.providerid -like "msolap*" } | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "ADOMD.net client library"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-WMIObject -Class win32_product | Where-Object {$_.name -like "*ado*"} | Select name, version, vendor | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "Usage Data Rules"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPUsageDefinition | Select name, status, enabled, tablename, DaysToKeepDetailedData | Where {$_.name -like "powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "Solutions"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPSolution | Select name, status, deployed, DeploymentState, DeployedServers | Where {$_.Name -like "*powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default

$time = Get-Date
Write-Host -ForegroundColor DarkGray StartTime $starttime
Write-Host -ForegroundColor DarkGray EndTime $time
```
