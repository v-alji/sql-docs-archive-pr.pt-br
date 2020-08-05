---
title: Ativar ou desativar recursos do Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services, configuration
- security [Reporting Services], strategies
ms.assetid: b69db02a-43a7-4fdc-ad9b-438d817a7f83
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f56f9984b5b02431db23b782652e5575af557bdb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573624"
---
# <a name="turn-reporting-services-features-on-or-off"></a><span data-ttu-id="92af5-102">Ativar e desativar recursos do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="92af5-102">Turn Reporting Services Features On or Off</span></span>
  <span data-ttu-id="92af5-103">Você pode desativar os recursos do servidor de relatório que não são usados como parte de uma estratégia de bloqueio para reduzir a superfície de ataque de um servidor de relatório de produção.</span><span class="sxs-lookup"><span data-stu-id="92af5-103">You can turn off report server features that you do not use as part of a lockdown strategy for reducing the attack surface of a production report server.</span></span> <span data-ttu-id="92af5-104">Na maioria dos casos, você deve executar os recursos do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] simultaneamente para usar toda a funcionalidade disponível no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92af5-104">In most cases, you will want to run [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] features concurrently to use all of the functionality provided in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="92af5-105">No entanto, dependendo de seu modelo de implantação, você pode desabilitar os recursos dos quais não precisa.</span><span class="sxs-lookup"><span data-stu-id="92af5-105">However, depending on your deployment model, you can disable the features that you do not require.</span></span> <span data-ttu-id="92af5-106">Por exemplo, você pode habilitar apenas o processamento em segundo plano se todo o processamento de relatórios for configurado como operações agendadas.</span><span class="sxs-lookup"><span data-stu-id="92af5-106">For example, you can enable only the background processing if all report processing is configured as scheduled operations.</span></span> <span data-ttu-id="92af5-107">Da mesma maneira, você pode executar somente o serviço Web Servidor de Relatório se quiser apenas relatórios interativos sob demanda.</span><span class="sxs-lookup"><span data-stu-id="92af5-107">Similarly, you can run just the Report Server Web service if you only want interactive, on-demand reporting.</span></span>  
  
 <span data-ttu-id="92af5-108">Os procedimentos descritos neste tópico mostram como desativar recursos do modo nativo do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="92af5-108">The procedures in this topic show you how to turn off native mode [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] features.</span></span> <span data-ttu-id="92af5-109">É possível configurar recursos de maneiras diferentes; por exemplo, editando o arquivo `RsReportServer.config` diretamente ou usando a faceta **Configuração da Área de Superfície do Reporting Services** do Gerenciamento Baseado em Políticas no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92af5-109">Features can be configured in different ways, such as by editing the `RsReportServer.config` file directly or by using the **Surface Area Configuration for Reporting Services** facet of Policy-Based Management in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="92af5-110">Use os links para localizar o(s) procedimento(s) que explica(m) como ativar ou desativar um recurso:</span><span class="sxs-lookup"><span data-stu-id="92af5-110">Use the links to locate the procedure or procedures that explain how to turn a feature on or off:</span></span>  
  
-   [<span data-ttu-id="92af5-111">Serviço Web servidor de relatórios</span><span class="sxs-lookup"><span data-stu-id="92af5-111">Report Server Web service</span></span>](#RSWebSvc)  
  
-   [<span data-ttu-id="92af5-112">Eventos e processamento agendados</span><span class="sxs-lookup"><span data-stu-id="92af5-112">Scheduled events and processing</span></span>](#Sched)  
  
-   [<span data-ttu-id="92af5-113">Gerenciador de Relatórios</span><span class="sxs-lookup"><span data-stu-id="92af5-113">Report Manager</span></span>](#ReportManager)  
  
-   [<span data-ttu-id="92af5-114">Construtor de Relatórios</span><span class="sxs-lookup"><span data-stu-id="92af5-114">Report Builder</span></span>](#ReportBuilder)  
  
-   [<span data-ttu-id="92af5-115">Segurança Integrada do Windows para fontes de dados de relatório</span><span class="sxs-lookup"><span data-stu-id="92af5-115">Windows Integrated security for report data sources</span></span>](#WinIntSec)  
  
##  <a name="report-server-web-service"></a><a name="RSWebSvc"></a><span data-ttu-id="92af5-116">Serviço Web servidor de relatórios</span><span class="sxs-lookup"><span data-stu-id="92af5-116">Report Server Web Service</span></span>  
  
#### <a name="to-turn-on-or-off-the-report-server-web-service-by-editing-configuration"></a><span data-ttu-id="92af5-117">Para ativar ou desativar o serviço Web Servidor de Relatórios editando a configuração</span><span class="sxs-lookup"><span data-stu-id="92af5-117">To turn on or off the Report Server Web service by editing configuration</span></span>  
  
1.  <span data-ttu-id="92af5-118">Abra o arquivo `RsReportServer.config` em um editor de texto.</span><span class="sxs-lookup"><span data-stu-id="92af5-118">Open the `RsReportServer.config` file in a text editor.</span></span> <span data-ttu-id="92af5-119">Para obter mais informações, consulte [Modificar um arquivo de configuração do Reporting Services &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92af5-119">For more information, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="92af5-120">Para ativar o serviço Web Servidor de Relatórios, defina `IsWebServiceEnabled` como `true`:</span><span class="sxs-lookup"><span data-stu-id="92af5-120">To turn on the Report Server Web service, set `IsWebServiceEnabled` to `true`:</span></span>  
  
    ```  
    <IsWebServiceEnabled>true</IsWebServiceEnabled>  
    ```  
  
3.  <span data-ttu-id="92af5-121">Para desativar o serviço Web Servidor de Relatórios, defina `IsWebServiceEnabled` como `false`:</span><span class="sxs-lookup"><span data-stu-id="92af5-121">To turn off the Report Server Web service, set `IsWebServiceEnabled` to `false`:</span></span>  
  
    ```  
    <IsWebServiceEnabled>false</IsWebServiceEnabled>  
    ```  
  
4.  <span data-ttu-id="92af5-122">Salve as alterações e feche o arquivo.</span><span class="sxs-lookup"><span data-stu-id="92af5-122">Save your changes and then close the file.</span></span>  
  
#### <a name="to-turn-on-or-off-the-report-server-web-service-by-using-sql-server-management-studio"></a><span data-ttu-id="92af5-123">Para ativar ou desativar o serviço Web Servidor de Relatórios usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="92af5-123">To turn on or off the Report Server Web service by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="92af5-124">Abra o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e se conecte à instância do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="92af5-124">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="92af5-125">No Pesquisador de objetos, clique com o botão direito do mouse no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] nó, aponte para **políticas**e clique em **facetas**.</span><span class="sxs-lookup"><span data-stu-id="92af5-125">In Object Explorer, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, point to **Policies**, and click **Facets**.</span></span>  
  
3.  <span data-ttu-id="92af5-126">Na lista **Faceta** , selecione **Configuração da Área de Superfície do Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="92af5-126">In the **Facet** list, select **Surface Area Configuration for Reporting Services**.</span></span>  
  
4.  <span data-ttu-id="92af5-127">Em **Propriedades da Faceta**:</span><span class="sxs-lookup"><span data-stu-id="92af5-127">Under **Facet Properties**:</span></span>  
  
    -   <span data-ttu-id="92af5-128">Para ativar o serviço Web servidor de relatórios, defina **WebServiceAndHTTPAccessEnabled** como `True` .</span><span class="sxs-lookup"><span data-stu-id="92af5-128">To turn on the Report Server Web service, set **WebServiceAndHTTPAccessEnabled** to `True`.</span></span>  
  
    -   <span data-ttu-id="92af5-129">Para desativar o serviço Web servidor de relatórios, defina **WebServiceAndHTTPAccessEnabled** como `False` .</span><span class="sxs-lookup"><span data-stu-id="92af5-129">To turn off the Report Server Web service, set **WebServiceAndHTTPAccessEnabled** to `False`.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="scheduled-events-and-delivery"></a><a name="Sched"></a> <span data-ttu-id="92af5-130">Eventos e entrega agendados</span><span class="sxs-lookup"><span data-stu-id="92af5-130">Scheduled Events and Delivery</span></span>  
  
#### <a name="to-turn-on-or-off-scheduled-events-and-delivery-by-editing-configuration"></a><span data-ttu-id="92af5-131">Para ativar ou desativar eventos e entrega agendados editando a configuração</span><span class="sxs-lookup"><span data-stu-id="92af5-131">To turn on or off scheduled events and delivery by editing configuration</span></span>  
  
1.  <span data-ttu-id="92af5-132">Abra o arquivo RsReportServer.config em um editor de texto.</span><span class="sxs-lookup"><span data-stu-id="92af5-132">Open the RsReportServer.config file in a text editor.</span></span> <span data-ttu-id="92af5-133">Para obter mais informações, consulte [Modificar um arquivo de configuração do Reporting Services &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92af5-133">For more information, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="92af5-134">Para ativar o processamento e a entrega agendados de relatórios, defina `IsSchedulingService`, `IsNotificationService` e `IsEventService` como `true`:</span><span class="sxs-lookup"><span data-stu-id="92af5-134">To turn on scheduled report processing and delivery, set `IsSchedulingService`, `IsNotificationService`, and `IsEventService` to `true`:</span></span>  
  
    ```  
    <IsSchedulingService>true</IsSchedulingService>  
    <IsNotificationService>true</IsNotificationService>  
    <IsEventService>true</IsEventService>  
    ```  
  
3.  <span data-ttu-id="92af5-135">Para desativar o processamento e a entrega agendados de relatórios, defina `IsSchedulingService`, `IsNotificationService` e `IsEventService` como `false`:</span><span class="sxs-lookup"><span data-stu-id="92af5-135">To turn off scheduled report processing and delivery, set `IsSchedulingService`, `IsNotificationService`, and `IsEventService` to `false`:</span></span>  
  
    ```  
    <IsSchedulingService>false</IsSchedulingService>  
    <IsNotificationService>false</IsNotificationService>  
    <IsEventService>false</IsEventService>  
    ```  
  
4.  <span data-ttu-id="92af5-136">Salve as alterações e feche o arquivo.</span><span class="sxs-lookup"><span data-stu-id="92af5-136">Save your changes and then close the file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="92af5-137">Não é possível desativar completamente o processamento em segundo plano porque ele fornece a funcionalidade de manutenção de banco de dados que é necessária para operações de servidor.</span><span class="sxs-lookup"><span data-stu-id="92af5-137">You cannot turn off background processing completely because it provides database maintenance functionality that is required for server operations.</span></span>  
  
#### <a name="to-turn-on-or-off-scheduled-events-and-delivery-by-using-sql-server-management-studio"></a><span data-ttu-id="92af5-138">Para ativar ou desativar eventos e entrega agendados usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="92af5-138">To turn on or off scheduled events and delivery by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="92af5-139">Abra o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e se conecte à instância do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="92af5-139">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="92af5-140">No Pesquisador de objetos, clique com o botão direito do mouse no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] nó, aponte para **políticas**e clique em **facetas**.</span><span class="sxs-lookup"><span data-stu-id="92af5-140">In Object Explorer, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, point to **Policies**, and click **Facets**.</span></span>  
  
3.  <span data-ttu-id="92af5-141">Na lista **Faceta** , selecione **Configuração da Área de Superfície do Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="92af5-141">In the **Facet** list, select **Surface Area Configuration for Reporting Services**.</span></span>  
  
4.  <span data-ttu-id="92af5-142">Em **Propriedades da Faceta**:</span><span class="sxs-lookup"><span data-stu-id="92af5-142">Under **Facet Properties**:</span></span>  
  
    -   <span data-ttu-id="92af5-143">Para ativar os eventos e a entrega agendados, defina **ScheduleEventsAndReportDeliveryEnabled** como `True` .</span><span class="sxs-lookup"><span data-stu-id="92af5-143">To turn on scheduled events and delivery, set **ScheduleEventsAndReportDeliveryEnabled** to `True`.</span></span>  
  
    -   <span data-ttu-id="92af5-144">Para desativar os eventos e a entrega agendados, defina **ScheduleEventsAndReportDeliveryEnabled** como `False` .</span><span class="sxs-lookup"><span data-stu-id="92af5-144">To turn off scheduled events and delivery, set **ScheduleEventsAndReportDeliveryEnabled** to `False`.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
> [!NOTE]  
>  <span data-ttu-id="92af5-145">Não é possível desativar completamente o processamento em segundo plano porque ele fornece a funcionalidade de manutenção de banco de dados que é necessária para operações de servidor.</span><span class="sxs-lookup"><span data-stu-id="92af5-145">You cannot turn off background processing completely because it provides database maintenance functionality that is required for server operations.</span></span>  
  
##  <a name="report-manager"></a><a name="ReportManager"></a><span data-ttu-id="92af5-146">Report Manager</span><span class="sxs-lookup"><span data-stu-id="92af5-146">Report Manager</span></span>  
  
#### <a name="to-turn-on-or-off-report-manager-by-editing-configuration"></a><span data-ttu-id="92af5-147">Para ativar ou desativar o Gerenciador de Relatórios editando a configuração</span><span class="sxs-lookup"><span data-stu-id="92af5-147">To turn on or off Report Manager by editing configuration</span></span>  
  
1.  <span data-ttu-id="92af5-148">Abra o arquivo RsReportServer.config em um editor de texto.</span><span class="sxs-lookup"><span data-stu-id="92af5-148">Open the RsReportServer.config file in a text editor.</span></span> <span data-ttu-id="92af5-149">Para obter instruções, veja [Modificar um arquivo de configuração do Reporting Services &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92af5-149">For instructions, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="92af5-150">Para ativar o Gerenciador de Relatórios, defina `IsReportManagerEnabled` como `true`:</span><span class="sxs-lookup"><span data-stu-id="92af5-150">To turn on Report Manager, set `IsReportManagerEnabled` to `true`:</span></span>  
  
    ```  
    <IsReportManagerEnabled>true</IsReportManagerEnabled>  
    ```  
  
3.  <span data-ttu-id="92af5-151">Para desativar o Gerenciador de Relatórios, defina `IsReportManagerEnabled` como `false`:</span><span class="sxs-lookup"><span data-stu-id="92af5-151">To turn off Report Manager, set `IsReportManagerEnabled` to `false`:</span></span>  
  
    ```  
    <IsReportManagerEnabled>false</IsReportManagerEnabled>  
    ```  
  
4.  <span data-ttu-id="92af5-152">Salve as alterações e feche o arquivo.</span><span class="sxs-lookup"><span data-stu-id="92af5-152">Save your changes and then close the file.</span></span>  
  
#### <a name="to-turn-on-or-off-report-manager-by-using-sql-server-management-studio"></a><span data-ttu-id="92af5-153">Para ativar ou desativar o Gerenciador de Relatórios usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="92af5-153">To turn on or off Report Manager by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="92af5-154">Abra o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e se conecte à instância do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="92af5-154">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="92af5-155">No **Pesquisador de Objetos**, clique com o botão direito do mouse no nó [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , aponte para **Políticas**e clique em **Facetas**.</span><span class="sxs-lookup"><span data-stu-id="92af5-155">In **Object Explorer**, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, point to **Policies**, and click **Facets**.</span></span>  
  
3.  <span data-ttu-id="92af5-156">Na lista **Faceta** , selecione **Configuração da Área de Superfície do Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="92af5-156">In the **Facet** list, select **Surface Area Configuration for Reporting Services**.</span></span>  
  
4.  <span data-ttu-id="92af5-157">Em **Propriedades da Faceta**:</span><span class="sxs-lookup"><span data-stu-id="92af5-157">Under **Facet Properties**:</span></span>  
  
    -   <span data-ttu-id="92af5-158">Para ativar Report Manager, defina **ReportManagerEnabled** como `True` .</span><span class="sxs-lookup"><span data-stu-id="92af5-158">To turn on Report Manager, set **ReportManagerEnabled** to `True`.</span></span>  
  
    -   <span data-ttu-id="92af5-159">Para desativar Report Manager, defina **ReportManagerEnabled** como `False` .</span><span class="sxs-lookup"><span data-stu-id="92af5-159">To turn off Report Manager, set **ReportManagerEnabled** to `False`.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="report-builder"></a><a name="ReportBuilder"></a> <span data-ttu-id="92af5-160">Construtor de Relatórios</span><span class="sxs-lookup"><span data-stu-id="92af5-160">Report Builder</span></span>  
  
#### <a name="to-turn-on-or-off-report-builder-by-using-sql-server-management-studio"></a><span data-ttu-id="92af5-161">Para ativar ou desativar o Construtor de Relatórios usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="92af5-161">To turn on or off Report Builder by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="92af5-162">Abra o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e se conecte à instância do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="92af5-162">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="92af5-163">No Pesquisador de Objetos, clique com o botão direito do mouse no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="92af5-163">In Object Explorer, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="92af5-164">Na caixa de diálogo **Propriedades do Servidor** , em **Selecionar uma página**, clique em **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="92af5-164">In the **Server Properties** dialog box, under **Select a page**, click **Security**.</span></span>  
  
    -   <span data-ttu-id="92af5-165">Para ativar o Construtor de Relatórios, selecione a opção **Habilitar execuções de relatórios ad hoc** .</span><span class="sxs-lookup"><span data-stu-id="92af5-165">To turn on Report Builder, select the **Enable ad hoc report executions** option.</span></span>  
  
    -   <span data-ttu-id="92af5-166">Para desativar o Construtor de Relatórios, desmarque a opção **Habilitar execuções de relatórios ad hoc** .</span><span class="sxs-lookup"><span data-stu-id="92af5-166">To turn off Report Builder, unselect the **Enable ad hoc report executions** option.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="windows-integrated-security"></a><a name="WinIntSec"></a> <span data-ttu-id="92af5-167">Segurança integrada do Windows</span><span class="sxs-lookup"><span data-stu-id="92af5-167">Windows Integrated Security</span></span>  
  
#### <a name="to-turn-on-or-off-windows-integrated-security-by-using-sql-server-management-studio"></a><span data-ttu-id="92af5-168">Para ativar ou desativar a segurança Integrada do Windows usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="92af5-168">To turn on or off Windows Integrated security by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="92af5-169">Abra o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e se conecte à instância do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="92af5-169">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="92af5-170">No Pesquisador de Objetos, clique com o botão direito do mouse no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="92af5-170">In Object Explorer, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="92af5-171">Na caixa de diálogo **Propriedades do Servidor** , em **Selecionar uma página**, clique em **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="92af5-171">In the **Server Properties** dialog box, under **Select a page**, click **Security**.</span></span>  
  
    -   <span data-ttu-id="92af5-172">Para ativar a segurança Integrada do Windows, selecione a opção **Habilitar a segurança Integrada do Windows para as fontes de dados do relatório** .</span><span class="sxs-lookup"><span data-stu-id="92af5-172">To turn on Windows Integrated security, select the **Enable Windows Integrated security for report data sources** option.</span></span>  
  
    -   <span data-ttu-id="92af5-173">Para desativar a segurança Integrada do Windows, desmarque a opção **Habilitar a segurança Integrada do Windows para as fontes de dados do relatório** .</span><span class="sxs-lookup"><span data-stu-id="92af5-173">To turn off Windows integrated security, unselect the **Enable Windows Integrated security for report data sources** option.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="92af5-174">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="92af5-174">See Also</span></span>  
 [<span data-ttu-id="92af5-175">Reporting Services Configuration Manager &#40;Modo Nativo&#41;</span><span class="sxs-lookup"><span data-stu-id="92af5-175">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../sql-server/install/reporting-services-configuration-manager-native-mode.md)  
  
  
