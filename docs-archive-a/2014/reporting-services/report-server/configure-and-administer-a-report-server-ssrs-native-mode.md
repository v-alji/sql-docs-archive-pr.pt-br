---
title: Configurar e administrar um servidor de relatório (modo nativo do SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 08/10/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services, components
- deploying [Reporting Services], component options
- report servers [Reporting Services], component options
- configuration options [Reporting Services]
- administering Reporting Services
- components [Reporting Services], configuring
- configuring servers [Reporting Services]
ms.assetid: cfec012b-56f1-4346-9814-247acf22351c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5164fd2f9170cb092a45394f64f06d7622253f2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575601"
---
# <a name="configure-and-administer-a-report-server-ssrs-native-mode"></a><span data-ttu-id="d1050-102">Configurar e administrar um servidor de relatório (modo nativo do SSRS)</span><span class="sxs-lookup"><span data-stu-id="d1050-102">Configure and Administer a Report Server (SSRS Native Mode)</span></span>
  <span data-ttu-id="d1050-103">Este tópico resume as abordagens que podem ser usadas para configurar o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1050-103">This topic summarizes the approaches that you can use to configure [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="d1050-104">Também inclui uma lista de tópicos que explicam como configurar componentes, recursos ou recursos específicos de servidor.</span><span class="sxs-lookup"><span data-stu-id="d1050-104">It also includes a list of topics that explain how to configure specific components, features, or server capabilities.</span></span> <span data-ttu-id="d1050-105">Para configurar o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], você pode:</span><span class="sxs-lookup"><span data-stu-id="d1050-105">To configure [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can:</span></span>  
  
-   <span data-ttu-id="d1050-106">Usar o Gerenciador de Configuração do Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="d1050-106">Use the Reporting Services Configuration Manager.</span></span> <span data-ttu-id="d1050-107">Muitos dos tópicos nesta seção contêm informações sobre como configurar recursos específicos com essa ferramenta.</span><span class="sxs-lookup"><span data-stu-id="d1050-107">Many of the topics in this section contain information about how to configure specific features through this tool.</span></span>  
  
-   <span data-ttu-id="d1050-108">Usar o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] para personalizar propriedades de servidor, habilitar Meus Relatórios, habilitar logs de rastreamento e definir padrões em todo o site.</span><span class="sxs-lookup"><span data-stu-id="d1050-108">Use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to customize server properties, enable My Reports, enable trace logs, and set site-wide defaults.</span></span> <span data-ttu-id="d1050-109">Para obter mais informações sobre configurações de site, consulte [Servidor de relatório do Reporting Services &#40;Modo Nativo&#41;](reporting-services-report-server-native-mode.md) para o Management Studio.</span><span class="sxs-lookup"><span data-stu-id="d1050-109">For more information about site settings, see [Reporting Services Report Server &#40;Native Mode&#41;](reporting-services-report-server-native-mode.md) for Management Studio.</span></span> <span data-ttu-id="d1050-110">Observe que é possível criar e executar um script que defina propriedades de servidor programaticamente.</span><span class="sxs-lookup"><span data-stu-id="d1050-110">Note that you can create and run script that sets server properties programmatically.</span></span> <span data-ttu-id="d1050-111">Para obter mais informações, consulte [Implantação de script e tarefas administrativas](../tools/script-deployment-and-administrative-tasks.md) e [Propriedades de sistema do Servidor de Relatório](../report-server-web-service/net-framework/reporting-services-properties-report-server-system-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d1050-111">For more information, see [Script Deployment and Administrative Tasks](../tools/script-deployment-and-administrative-tasks.md) and [Report Server System Properties](../report-server-web-service/net-framework/reporting-services-properties-report-server-system-properties.md).</span></span>  
  
-   <span data-ttu-id="d1050-112">Use o Gerenciador de Relatórios para conceder permissões de acesso ao servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="d1050-112">Use Report Manager to grant permissions to access the report server.</span></span> <span data-ttu-id="d1050-113">Permissões são concedidas por atribuições de função definidas para cada usuário ou conta de grupo.</span><span class="sxs-lookup"><span data-stu-id="d1050-113">Permissions are conveyed through role assignments that you define for each user or group account.</span></span> <span data-ttu-id="d1050-114">Para obter mais informações, consulte [Funções e permissões &#40;Reporting Services&#41;](../security/roles-and-permissions-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="d1050-114">For more information, see [Roles and Permissions &#40;Reporting Services&#41;](../security/roles-and-permissions-reporting-services.md).</span></span>  
  
-   <span data-ttu-id="d1050-115">Como alternativa, modifique arquivos de configuração para alterar configurações do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d1050-115">Optionally, modify configuration files to change application settings.</span></span> <span data-ttu-id="d1050-116">Para obter mais informações sobre cada arquivo e diretrizes para modificá-los, consulte [Arquivos de configuração do Reporting Services](reporting-services-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="d1050-116">For more information about each file and guidelines for modifying them, see [Reporting Services Configuration Files](reporting-services-configuration-files.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d1050-117">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="d1050-117">In This Section</span></span>  
 [<span data-ttu-id="d1050-118">Configurar as URLs do servidor de relatório &#40;SSRS Configuration Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="d1050-118">Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-report-server-urls-ssrs-configuration-manager.md)  
 <span data-ttu-id="d1050-119">Descreve como definir as URLs usadas para acessar o servidor de relatório e o Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="d1050-119">Describes how to define the URLs used to access the report server and Report Manager.</span></span>  
  
 [<span data-ttu-id="d1050-120">Configurar a conta de serviço do servidor de relatório &#40;SSRS Configuration Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="d1050-120">Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md)  
 <span data-ttu-id="d1050-121">Fornece recomendações e etapas sobre como modificar a conta de serviço e a senha.</span><span class="sxs-lookup"><span data-stu-id="d1050-121">Provides recommendations and steps on how to modify service account and password.</span></span>  
  
 [<span data-ttu-id="d1050-122">Criar um banco de dados do servidor de relatório &#40;SSRS Configuration Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="d1050-122">Create a Report Server Database  &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/create-a-report-server-database-ssrs-configuration-manager.md)  
 <span data-ttu-id="d1050-123">Descreve como criar um banco de dados de servidor de relatório, exigido por armazenar metadados e objetos de servidor.</span><span class="sxs-lookup"><span data-stu-id="d1050-123">Describes how to create a report server database, required for storing server metadata and objects.</span></span>  
  
 [<span data-ttu-id="d1050-124">Configurar uma conexão de banco de dados do servidor de relatório &#40;SSRS Configuration Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="d1050-124">Configure a Report Server Database Connection  &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md)  
 <span data-ttu-id="d1050-125">Descreve como modificar a cadeia de conexão usada pelo servidor de relatório para conexão com o banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="d1050-125">Describes how to modify the connection string used by the report server to connect to the report server database.</span></span>  
  
 [<span data-ttu-id="d1050-126">Configurar um servidor de relatório para entrega de email &#40;Configuration Manager SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d1050-126">Configure a Report Server for E-Mail Delivery &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md)  
 <span data-ttu-id="d1050-127">Descreve como configurar um servidor de relatório para dar suporte à distribuição de relatório por email.</span><span class="sxs-lookup"><span data-stu-id="d1050-127">Describes how to configure a report server to support e-mail report distribution.</span></span>  
  
 [<span data-ttu-id="d1050-128">Configurar a conta de execução autônoma &#40;Gerenciador de configurações do SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d1050-128">Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md)  
 <span data-ttu-id="d1050-129">Descreve como configurar uma conta do usuário para processar relatórios no modo autônomo.</span><span class="sxs-lookup"><span data-stu-id="d1050-129">Describes how to configure a user account to process reports in unattended mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1050-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d1050-130">See Also</span></span>  
 <span data-ttu-id="d1050-131">[Configurar o acesso ao Construtor de Relatórios](configure-report-builder-access.md) </span><span class="sxs-lookup"><span data-stu-id="d1050-131">[Configure Report Builder Access](configure-report-builder-access.md) </span></span>  
 <span data-ttu-id="d1050-132">[Arquivos de configuração do Reporting Services](reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="d1050-132">[Reporting Services Configuration Files](reporting-services-configuration-files.md) </span></span>  
 <span data-ttu-id="d1050-133">[Reporting Services Configuration Manager &#40;Modo Nativo&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="d1050-133">[Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span></span>  
 <span data-ttu-id="d1050-134">[Segurança e proteção do Reporting Services](../security/reporting-services-security-and-protection.md) </span><span class="sxs-lookup"><span data-stu-id="d1050-134">[Reporting Services Security and Protection](../security/reporting-services-security-and-protection.md) </span></span>  
 [<span data-ttu-id="d1050-135">Servidor de relatório do Reporting Services &#40;Modo Nativo&#41;</span><span class="sxs-lookup"><span data-stu-id="d1050-135">Reporting Services Report Server &#40;Native Mode&#41;</span></span>](reporting-services-report-server-native-mode.md)  
  
  
