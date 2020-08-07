---
title: Ativar o recurso de Sincronização de Arquivos do servidor de relatório na administração central do SharePoint | Microsoft Docs
ms.prod: sql-server-2014
ms.technology: reporting-services
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.date: 03/06/2017
ms.openlocfilehash: 55feac69da85c7287ea56f4b8245350dd7e69565
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575668"
---
# <a name="activate-the-report-server-file-sync-feature-in-sharepoint-central-administration"></a><span data-ttu-id="e1a7e-102">Ativar o recurso de sincronização de relatório do Servidor de Relatório na Administração Central do SharePoint</span><span class="sxs-lookup"><span data-stu-id="e1a7e-102">Activate the Report Server File Sync Feature in SharePoint Central Administration</span></span>

<span data-ttu-id="e1a7e-103">O recurso Sincronização de arquivos do Servidor de Relatório do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] utiliza manipuladores de eventos do SharePoint para sincronizar o catálogo do servidor de relatório com itens em bibliotecas de documentos.</span><span class="sxs-lookup"><span data-stu-id="e1a7e-103">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Report Server File Sync feature utilizes SharePoint event handlers to synchronize the report server catalog with items in document libraries.</span></span> <span data-ttu-id="e1a7e-104">Esse recurso é benéfico quando os usuários carregam com frequência itens de relatórios publicados diretamente nas bibliotecas de documentos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e1a7e-104">This feature is beneficial when users frequently upload published report items directly to SharePoint document libraries.</span></span> <span data-ttu-id="e1a7e-105">Se o recurso de sincronização de arquivo não estiver ativado, o conteúdo ainda será sincronizado, mas não com a frequência.</span><span class="sxs-lookup"><span data-stu-id="e1a7e-105">If the file Sync feature isn't activated, content will still be synchronized but not as frequently.</span></span>  
  
<span data-ttu-id="e1a7e-106">O recurso Sincronização de Arquivos pode ser ativado na Administração de Site do SharePoint depois que você instala o Suplemento [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)] para produtos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e1a7e-106">The File Sync feature can be activated in SharePoint Site Administration after you install the [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)] Add-in for SharePoint products.</span></span>  
  
<span data-ttu-id="e1a7e-107">Esse recurso pode ser ativado e desativado manualmente por site, mas não no nível de conjunto de sites.</span><span class="sxs-lookup"><span data-stu-id="e1a7e-107">This feature can be manually activated and deactivated per site but not at the site collection level.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e1a7e-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="e1a7e-108">Prerequisites</span></span>  
 <span data-ttu-id="e1a7e-109">O Suplemento [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] para o SharePoint deve ser instalado.</span><span class="sxs-lookup"><span data-stu-id="e1a7e-109">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Add-in for SharePoint must be installed.</span></span> <span data-ttu-id="e1a7e-110">Se o suplemento não estiver instalado, o recurso de sincronização de arquivo não estará visível na lista de recursos do site.</span><span class="sxs-lookup"><span data-stu-id="e1a7e-110">If the add-in isn't installed, the file sync feature won't be visible in the site feature list.</span></span>  
  
 <span data-ttu-id="e1a7e-111">Para verificar a instalação, exiba a lista de aplicativos instalados no [!INCLUDE[msCoName](../includes/msconame-md.md)] Painel de Controle **do**Windows.</span><span class="sxs-lookup"><span data-stu-id="e1a7e-111">To verify installation, view the list of installed applications in [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows **Control Panel**.</span></span> <span data-ttu-id="e1a7e-112">Se o Suplemento [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] estiver instalado, siga as instruções deste tópico para ativar o recurso Sincronização de arquivos do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="e1a7e-112">If the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Add-in is installed, follow the instructions in this topic to activate the report server file sync feature.</span></span>  
  
### <a name="to-activate-or-deactivate-the-reporting-services-file-sync-feature-on-a-site"></a><span data-ttu-id="e1a7e-113">Para ativar ou desativar o recurso Sincronização de arquivos do Reporting Services em um site</span><span class="sxs-lookup"><span data-stu-id="e1a7e-113">To activate or deactivate the Reporting Services File Sync feature on a Site</span></span>  
  
1.  <span data-ttu-id="e1a7e-114">Na página principal do seu site, clique no menu **ações do site** e clique em **configurações do site**.</span><span class="sxs-lookup"><span data-stu-id="e1a7e-114">From the main page of your site, click the **Site Actions** menu and click **Site Settings**.</span></span>  
  
2.  <span data-ttu-id="e1a7e-115">Nas **ações do site**, clique em **gerenciar recursos do site**.</span><span class="sxs-lookup"><span data-stu-id="e1a7e-115">In the **Site Actions**, click **Manage Site Features**.</span></span>  
  
3.  <span data-ttu-id="e1a7e-116">Localize **Sincronização de arquivos do Servidor de Relatório** na lista.</span><span class="sxs-lookup"><span data-stu-id="e1a7e-116">Find **Report Server File Sync** in the list.</span></span>  
  
4.  <span data-ttu-id="e1a7e-117">Clique em **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="e1a7e-117">Click **Activate**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e1a7e-118">Para desativar o recurso Sincronização de arquivos do Servidor de Relatório, é possível usar o mesmo procedimento, mas clique em **Desativar**.</span><span class="sxs-lookup"><span data-stu-id="e1a7e-118">To deactivate the Report Server file sync feature, you can use the same procedure but click **Deactivate**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1a7e-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e1a7e-119">See Also</span></span>  
 <span data-ttu-id="e1a7e-120">[Solucionar problemas de partes de relatório &#40;Construtor de Relatórios e SSRS&#41;](report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e1a7e-120">[Troubleshoot Report Parts &#40;Report Builder and SSRS&#41;](report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e1a7e-121">[Ativar o servidor de relatório e os recursos de integração do Power View no SharePoint](activate-the-report-server-and-power-view-integration-features-in-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="e1a7e-121">[Activate the Report Server and Power View Integration Features in SharePoint](activate-the-report-server-and-power-view-integration-features-in-sharepoint.md) </span></span>  
 <span data-ttu-id="e1a7e-122">[Instalar ou desinstalar o suplemento Reporting Services para SharePoint &#40;SharePoint 2010 e SharePoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="e1a7e-122">[Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md) </span></span>  
 [<span data-ttu-id="e1a7e-123">Instalar ou desinstalar o suplemento Reporting Services para SharePoint &#40;SharePoint 2010 e SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="e1a7e-123">Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)  
  
  
