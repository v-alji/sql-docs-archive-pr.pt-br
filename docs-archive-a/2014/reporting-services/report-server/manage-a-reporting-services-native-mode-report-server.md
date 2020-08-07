---
title: Gerenciar um servidor de relatório no modo nativo do Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services Configuration tool
- configuration options [Reporting Services]
- report servers [Reporting Services], configuring
ms.assetid: 6ca03a09-d6a8-4c93-ba12-1c99dcbfb618
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0d44a9329074a20c04f878c055674ea563b297f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575581"
---
# <a name="manage-a-reporting-services-native-mode-report-server"></a><span data-ttu-id="97fed-102">Gerenciar um servidor de relatório de modo nativo do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="97fed-102">Manage a Reporting Services Native Mode Report Server</span></span>
  <span data-ttu-id="97fed-103">Esta seção contém procedimentos para a configuração de uma instância do servidor de relatório de modo nativo usando o Gerenciador de Configurações do Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="97fed-103">This section contains procedures for configuring a native mode report server instance using the Reporting Services Configuration Manager.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="97fed-104">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="97fed-104">In This Section</span></span>  
 <span data-ttu-id="97fed-105">Os tópicos desta seção estão organizados em categorias para que seja possível localizar mais facilmente as instruções desejadas.</span><span class="sxs-lookup"><span data-stu-id="97fed-105">The topics in this section are organized into categories so that you can more easily find the instructions you want.</span></span> <span data-ttu-id="97fed-106">A primeira seção contém tópicos para tarefas de configuração básica para um servidor de relatório no modo nativo.</span><span class="sxs-lookup"><span data-stu-id="97fed-106">The first section contains topics for basic configuration tasks for a native mode report server.</span></span> <span data-ttu-id="97fed-107">A segunda seção contém tópicos de configuração avançada.</span><span class="sxs-lookup"><span data-stu-id="97fed-107">The second section contains advanced configuration topics.</span></span> <span data-ttu-id="97fed-108">A terceira seção contém tópicos para configuração de um servidor de relatório para execução no modo integrado do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="97fed-108">The third section contains topics for configuring a report server to run in SharePoint integrated mode.</span></span>  
  
### <a name="basic-configuration"></a><span data-ttu-id="97fed-109">Configuração básica</span><span class="sxs-lookup"><span data-stu-id="97fed-109">Basic Configuration</span></span>  
 [<span data-ttu-id="97fed-110">Reporting Services Configuration Manager &#40;Modo Nativo&#41;</span><span class="sxs-lookup"><span data-stu-id="97fed-110">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../sql-server/install/reporting-services-configuration-manager-native-mode.md)  
 <span data-ttu-id="97fed-111">Fornece etapas para iniciar a ferramenta Configuração do Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="97fed-111">Provides steps for starting the Reporting Services Configuration tool.</span></span>  
  
 [<span data-ttu-id="97fed-112">Configurar uma conta de serviço &#40;SSRS Configuration Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="97fed-112">Configure a Service Account &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/configure-a-service-account-ssrs-configuration-manager.md)  
 <span data-ttu-id="97fed-113">Explica como especificar informações de conta e senha para o serviço Servidor de Relatório.</span><span class="sxs-lookup"><span data-stu-id="97fed-113">Explains how to specify account and password information for the Report Server service.</span></span>  
  
 [<span data-ttu-id="97fed-114">Registrar um SPN &#40;Nome da Entidade de Serviço&#41; para um servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="97fed-114">Register a Service Principal Name &#40;SPN&#41; for a Report Server</span></span>](register-a-service-principal-name-spn-for-a-report-server.md)  
 <span data-ttu-id="97fed-115">Explica como registrar manualmente um SPN para um servidor de relatório executado em uma conta de usuário de domínio em uma rede que use autenticação Kerberos.</span><span class="sxs-lookup"><span data-stu-id="97fed-115">Explains how to manually register an SPN for a report server that runs under a domain user account on a network that uses Kerberos authentication.</span></span>  
  
 [<span data-ttu-id="97fed-116">Configurar uma URL &#40;SSRS Configuration Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="97fed-116">Configure a URL  &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-a-url-ssrs-configuration-manager.md)  
 <span data-ttu-id="97fed-117">Explica como estabelecer uma ou mais URLs usadas para acessar o serviço Web Servidor de Relatórios e o Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="97fed-117">Explains how to establish one or more URLs used to access the Report Server Web service and Report Manager.</span></span>  
  
 [<span data-ttu-id="97fed-118">Criar um banco de dados de servidor de relatório do modo nativo &#40;SSRS Configuration Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="97fed-118">Create a Native Mode Report Server Database  &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/ssrs-report-server-create-a-native-mode-report-server-database.md)  
 <span data-ttu-id="97fed-119">Fornece etapas para a criação de um banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="97fed-119">Provides steps for creating a report server database.</span></span> <span data-ttu-id="97fed-120">Essa etapa é necessária para a implantação de uma instalação do Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="97fed-120">This step is required for deploying a Reporting Services installation.</span></span>  
  
### <a name="advanced-or-optional-configuration"></a><span data-ttu-id="97fed-121">Configuração avançada ou opcional</span><span class="sxs-lookup"><span data-stu-id="97fed-121">Advanced or Optional Configuration</span></span>  
 [<span data-ttu-id="97fed-122">Configurar uma implantação de expansão do servidor de relatório no modo nativo &#40;Gerenciador de configurações do SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="97fed-122">Configure a Native Mode Report Server Scale-Out Deployment &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-a-native-mode-report-server-scale-out-deployment.md)  
 <span data-ttu-id="97fed-123">Fornece etapas para a configuração de vários servidores de relatório para compartilhar um banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="97fed-123">Provides steps for configuring multiple report servers to share a report server database.</span></span>  
  
 [<span data-ttu-id="97fed-124">Configurar um servidor de relatório para entrega de email &#40;Configuration Manager SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="97fed-124">Configure a Report Server for E-Mail Delivery &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md)  
 <span data-ttu-id="97fed-125">Fornece etapas para a configuração de um servidor de relatório para distribuição de email.</span><span class="sxs-lookup"><span data-stu-id="97fed-125">Provides steps for configuring a report server for e-mail distribution.</span></span>  
  
 [<span data-ttu-id="97fed-126">Configurar um firewall para acesso ao servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="97fed-126">Configure a Firewall for Report Server Access</span></span>](configure-a-firewall-for-report-server-access.md)  
 <span data-ttu-id="97fed-127">Explica como abrir as portas usadas para solicitações de entrada e respostas de saída de um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="97fed-127">Explains how to open ports used for inbound requests and outbound responses from a report server.</span></span>  
  
 [<span data-ttu-id="97fed-128">Configurar um servidor de relatório no modo nativo para a Administração Local &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="97fed-128">Configure a Native Mode Report Server for Local Administration &#40;SSRS&#41;</span></span>](configure-a-native-mode-report-server-for-local-administration-ssrs.md)  
 <span data-ttu-id="97fed-129">Descreve as etapas adicionais necessárias para conexão com o Gerenciador de Relatórios ou com um servidor de relatório usando http://localhost.</span><span class="sxs-lookup"><span data-stu-id="97fed-129">Describes additional steps required to connect to Report Manager or a report server using http://localhost.</span></span>  
  
 [<span data-ttu-id="97fed-130">Configurar um servidor de relatório para administração remota</span><span class="sxs-lookup"><span data-stu-id="97fed-130">Configure a Report Server for Remote Administration</span></span>](configure-a-report-server-for-remote-administration.md)  
 <span data-ttu-id="97fed-131">Explica como configurar uma instância do servidor de relatório remoto para que seja possível conectar e configurá-la a partir de um computador diferente.</span><span class="sxs-lookup"><span data-stu-id="97fed-131">Explains how to configure a remote report server instance so that you can connect to and configure it from a different computer.</span></span>  
  
 [<span data-ttu-id="97fed-132">Ativar ou desativar recursos do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="97fed-132">Turn Reporting Services Features On or Off</span></span>](turn-reporting-services-features-on-or-off.md)  
 <span data-ttu-id="97fed-133">Explica como remover recursos não usados em uma instalação do Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="97fed-133">Explains how to remove unused features in a Reporting Services installation.</span></span>  
  
 [<span data-ttu-id="97fed-134">Habilitar erros remotos &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="97fed-134">Enable Remote Errors &#40;Reporting Services&#41;</span></span>](enable-remote-errors-reporting-services.md)  
 <span data-ttu-id="97fed-135">Explica como definir as propriedades do servidor em um servidor de relatório para retornar informações adicionais sobre condições de erros que ocorrem em servidores remotos.</span><span class="sxs-lookup"><span data-stu-id="97fed-135">Explains how to set server properties on a report server to return additional information about error conditions that occur on remote servers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97fed-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="97fed-136">See Also</span></span>  
 <span data-ttu-id="97fed-137">[Configurar e administrar um servidor de relatório &#40;modo nativo do SSRS&#41;](configure-and-administer-a-report-server-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="97fed-137">[Configure and Administer a Report Server &#40;SSRS Native Mode&#41;](configure-and-administer-a-report-server-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="97fed-138">Configuração e administração de um servidor de relatório &#40;modo do SharePoint do Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="97fed-138">Configuration and Administration of a Report Server &#40;Reporting Services SharePoint Mode&#41;</span></span>](../configure-administer-report-server-reporting-services-sharepoint-mode.md)  
  
  
