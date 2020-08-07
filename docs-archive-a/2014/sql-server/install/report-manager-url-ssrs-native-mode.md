---
title: URL de Report Manager (modo nativo do SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.rsconfigtool.reportmanagervirtualdirectory.f1
ms.assetid: 45768952-23a6-45a5-b541-e7bf192b4a78
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: ec43c91bb2d24bb96cc6541d93311ce6dd234ed4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575562"
---
# <a name="report-manager-url-ssrs-native-mode"></a><span data-ttu-id="077f2-102">URL do Gerenciador de Relatórios (modo nativo do SSRS)</span><span class="sxs-lookup"><span data-stu-id="077f2-102">Report Manager URL (SSRS Native Mode)</span></span>
  <span data-ttu-id="077f2-103">Use a página URL do Gerenciador de Relatórios para configurar ou modificar a URL usada para acessar o Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="077f2-103">Use the Report Manager URL page to configure or modify the URL used to access Report Manager.</span></span> <span data-ttu-id="077f2-104">Por padrão, a URL do Gerenciador de Relatórios herda o prefixo, o endereço IP e a porta da URL do serviço Web Servidor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="077f2-104">By default, the Report Manager URL inherits the prefix, IP address, and port of the Report Server Web service URL.</span></span> <span data-ttu-id="077f2-105">Isso ocorre porque o Gerenciador de Relatórios fornece acesso front-end ao serviço Web que é executado no mesmo serviço do Servidor de Relatório.</span><span class="sxs-lookup"><span data-stu-id="077f2-105">This is because Report Manager provides front-end access to the Web service that runs within the same Report Server service.</span></span> <span data-ttu-id="077f2-106">Se você estiver isolando os aplicativos de serviço e usando o Gerenciador de Relatórios para acessar um serviço Web Servidor de Relatórios em um computador diferente, deverá editar o arquivo RSReportServer.config para apontar o Gerenciador de Relatórios para uma instância diferente.</span><span class="sxs-lookup"><span data-stu-id="077f2-106">If you are isolating the service applications and using Report Manager to access a Report Server Web service on a different computer, you must edit RSReportServer.config file to point Report Manager to a different instance.</span></span> <span data-ttu-id="077f2-107">Para obter mais informações sobre como configurar uma conexão de Report Manager com um servidor de relatório remoto, consulte [Gerenciador de Configurações do Reporting Services &#40;modo nativo&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="077f2-107">For more information about configuring a Report Manager connection to a remote report server, see [Reporting Services Configuration Manager &#40;Native Mode&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span></span>  
  
 [!INCLUDE[applies](../../includes/applies-md.md)]<span data-ttu-id="077f2-108">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modo nativo.</span><span class="sxs-lookup"><span data-stu-id="077f2-108">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>  
  
 <span data-ttu-id="077f2-109">Se estiver configurando o servidor de relatório para execução no modo integrado do SharePoint, não crie uma URL do Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="077f2-109">If you are configuring the report server to run in SharePoint integrated mode, do not create a Report Manager URL.</span></span> <span data-ttu-id="077f2-110">Não há suporte ao Gerenciador de Relatórios em um servidor de relatório que é executado no modo integrado do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="077f2-110">Report Manager is not supported on a report server that runs in SharePoint integrated mode.</span></span> <span data-ttu-id="077f2-111">Se já existir uma URL para o Gerenciador de Relatórios, ela ficará indisponível depois que você configurar o servidor de relatório para execução no modo integrado do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="077f2-111">If a URL already exists for Report Manager, it will become unavailable after you configure the report server to run in SharePoint integrated mode.</span></span>  
  
 <span data-ttu-id="077f2-112">Para abrir essa página, inicie o Gerenciador de Configurações do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e clique em **URL do Gerenciador de Relatórios** no painel de navegação.</span><span class="sxs-lookup"><span data-stu-id="077f2-112">To open this page, start the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager and click **Report Manager URL** in the navigation pane.</span></span> <span data-ttu-id="077f2-113">Para obter mais informações sobre como iniciar o Configuration Manager, consulte [Gerenciador de Configurações do Reporting Services &#40;modo nativo&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="077f2-113">For more information about how to start the Configuration Manager, see [Reporting Services Configuration Manager &#40;Native Mode&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="077f2-114">Se o Gerenciador de Relatórios não estiver habilitado, você não poderá definir opções nessa página.</span><span class="sxs-lookup"><span data-stu-id="077f2-114">If Report Manager is not enabled, you cannot set options on this page.</span></span> <span data-ttu-id="077f2-115">Para obter mais informações sobre como habilitar Report Manager, consulte [Gerenciador de Configurações do Reporting Services &#40;modo nativo&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="077f2-115">For more information about enabling Report Manager, see [Reporting Services Configuration Manager &#40;Native Mode&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="077f2-116">Opções</span><span class="sxs-lookup"><span data-stu-id="077f2-116">Options</span></span>  
 <span data-ttu-id="077f2-117">**Diretório virtual**</span><span class="sxs-lookup"><span data-stu-id="077f2-117">**Virtual Directory**</span></span>  
 <span data-ttu-id="077f2-118">Especifica o nome do diretório virtual do Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="077f2-118">Specifies the virtual directory name for Report Manager.</span></span> <span data-ttu-id="077f2-119">Você pode ter apenas um nome de diretório virtual para cada instância do Gerenciador de Relatórios no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="077f2-119">You can only have one virtual directory name for each Report Manager instance on the same computer.</span></span>  
  
 <span data-ttu-id="077f2-120">**URLs**</span><span class="sxs-lookup"><span data-stu-id="077f2-120">**URLs**</span></span>  
 <span data-ttu-id="077f2-121">Exibe a URL definida para a instância atual do Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="077f2-121">Displays the URL defined for the current Report Manager instance.</span></span>  
  
 <span data-ttu-id="077f2-122">**Avançado**</span><span class="sxs-lookup"><span data-stu-id="077f2-122">**Advanced**</span></span>  
 <span data-ttu-id="077f2-123">Adicione mais uma URL à instância atual do Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="077f2-123">Add an additional URL for the current Report Manager instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="077f2-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="077f2-124">See Also</span></span>  
 <span data-ttu-id="077f2-125">[Configurar uma URL &#40;Configuration Manager SSRS&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="077f2-125">[Configure a URL  &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="077f2-126">[URLs em arquivos de configuração &#40;Configuration Manager SSRS&#41;](../../reporting-services/install-windows/urls-in-configuration-files-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="077f2-126">[URLs in Configuration Files  &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/urls-in-configuration-files-ssrs-configuration-manager.md) </span></span>  
 [<span data-ttu-id="077f2-127">Configurar as URLs do servidor de relatório &#40;SSRS Configuration Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="077f2-127">Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;</span></span>](../../reporting-services/install-windows/configure-report-server-urls-ssrs-configuration-manager.md)  
  
  
