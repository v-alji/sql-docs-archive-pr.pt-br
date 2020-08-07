---
title: Ativar o servidor de relatório e os recursos de integração do Power View no SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c7f64a54-c555-4d31-bf99-3abe57dc8626
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: af5f544e959c039b0bdb85d63d0b94917254d78a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582330"
---
# <a name="activate-the-report-server-and-power-view-integration-features-in-sharepoint"></a><span data-ttu-id="d4a41-102">Ativar o servidor de relatório e os recursos de integração do Power View no SharePoint</span><span class="sxs-lookup"><span data-stu-id="d4a41-102">Activate the Report Server and Power View Integration Features in SharePoint</span></span>
  <span data-ttu-id="d4a41-103">Os [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] recursos do conjunto de sites geralmente são ativados por padrão depois que você instala o [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)] suplemento para produtos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d4a41-103">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] site collection features are usually activated by default after you install the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)] Add-in for SharePoint products.</span></span> <span data-ttu-id="d4a41-104">Em algumas situações, você precisará ativar manualmente os recursos.</span><span class="sxs-lookup"><span data-stu-id="d4a41-104">In some situations you will need to manually activate the features.</span></span>  
  
 <span data-ttu-id="d4a41-105">Se você instalar o suplemento do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] para Produtos SharePoint 2010 depois da instalação do produto SharePoint, o recurso de integração de Servidor de relatório e o recurso de integração do Power View só será ativado para coleções de sites de raiz.</span><span class="sxs-lookup"><span data-stu-id="d4a41-105">If you install the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] add-in for SharePoint 2010 Products after the installation of the SharePoint product, then the Report Server integration feature and the Power View integration feature will only be activated for root site collections.</span></span> <span data-ttu-id="d4a41-106">Para outras coleções de sites, você precisará ativar manualmente os recursos.</span><span class="sxs-lookup"><span data-stu-id="d4a41-106">For other site collections, you will need to manually activate the features.</span></span> <span data-ttu-id="d4a41-107">Por exemplo se você tiver uma coleção de sites de **http://[nome do meu servidor]/sites/[nome da coleção de sites]** , será necessário ativar manualmente os recursos da coleção de sites do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d4a41-107">For example if you have a site collection of **http://[my server name]/sites/[site collection name]** you will need to manually activate the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] site collection features.</span></span>  
  
 <span data-ttu-id="d4a41-108">Quando não houver nenhuma coleção de sites raiz, o suplemento [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] registrará em log uma mensagem semelhante à seguinte.</span><span class="sxs-lookup"><span data-stu-id="d4a41-108">When there is no root site collection, the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] add-in will log a message similar to the following.</span></span>  
  
 <span data-ttu-id="d4a41-109">"O aplicativo Web SharePoint 80 não tem a coleção de sites raiz"</span><span class="sxs-lookup"><span data-stu-id="d4a41-109">"SharePoint web app 80 does not have root site collection"</span></span>  
  
 <span data-ttu-id="d4a41-110">A mensagem será encontrada no log de instalação do suplemento, chamado "RS_SP_ #. log", em que # é um número de incremento.</span><span class="sxs-lookup"><span data-stu-id="d4a41-110">The message will be found in the add-in installation log, named "RS_SP_#.log" where # is an incrementing number.</span></span> <span data-ttu-id="d4a41-111">O arquivo de log será encontrado na pasta Temp Users atual, por exemplo, C:\Users \\ [nome de usuário] \AppData\Local\Temp. Para obter mais informações sobre opções de log com o suplemento, consulte [instalar ou desinstalar o suplemento Reporting Services para sharepoint &#40;sharepoint 2010 e sharepoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="d4a41-111">The log file will be found in the current users Temp folder, for example C:\Users\\[user name]\AppData\Local\Temp. For more information on logging options with the add-in, see [Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md).</span></span>  
  
 <span data-ttu-id="d4a41-112">Neste tópico:</span><span class="sxs-lookup"><span data-stu-id="d4a41-112">In this topic:</span></span>  
  
-   [<span data-ttu-id="d4a41-113">Para ativar o Servidor de Relatório e os recursos de coleção de sites do Power View:</span><span class="sxs-lookup"><span data-stu-id="d4a41-113">To Activate the Report Server and Power View Integration Site Collection Features:</span></span>](#bkmk_features)  
  
-   [<span data-ttu-id="d4a41-114">Para ativar ou desativar o recurso de coleção de sites da Administração Central do Reporting Services:</span><span class="sxs-lookup"><span data-stu-id="d4a41-114">To Activate or Deactivate Reporting Services Central Administration Site Collection Feature:</span></span>](#bkmk_centraladmin)  
  
##  <a name="to-activate-the-report-server-and-power-view-integration-site-collection-features"></a><a name="bkmk_features"></a><span data-ttu-id="d4a41-115">Para ativar o servidor de relatório e Power View os recursos do conjunto de sites de integração:</span><span class="sxs-lookup"><span data-stu-id="d4a41-115">To Activate the Report Server and Power View Integration Site Collection Features:</span></span>  
  
1.  <span data-ttu-id="d4a41-116">Abra seu navegador no site em que você deseja que os recursos do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] estejam ativos.</span><span class="sxs-lookup"><span data-stu-id="d4a41-116">Open your browser to the site where you want the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features active.</span></span>  
  
2.  <span data-ttu-id="d4a41-117">Clique em **Ações do Site**.</span><span class="sxs-lookup"><span data-stu-id="d4a41-117">Click **Site Actions**.</span></span>  
  
3.  <span data-ttu-id="d4a41-118">Clique em **Configurações de Site**.</span><span class="sxs-lookup"><span data-stu-id="d4a41-118">Click **Site Settings**.</span></span>  
  
4.  <span data-ttu-id="d4a41-119">Clique em **Recursos do Conjunto de Sites** no Grupo Administração do Conjunto de Sites.</span><span class="sxs-lookup"><span data-stu-id="d4a41-119">Click **Site Collection Features** in the Site Collection Administration Group.</span></span>  
  
5.  <span data-ttu-id="d4a41-120">Localize **Recurso de Integração do Servidor de Relatório** ou **Recurso de Integração do Power View** na lista.</span><span class="sxs-lookup"><span data-stu-id="d4a41-120">Find **Report Server Integration Feature** or **Power View Integration Feature** in the list.</span></span>  
  
6.  <span data-ttu-id="d4a41-121">Clique em **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="d4a41-121">Click **Activate**.</span></span>  
  
 <span data-ttu-id="d4a41-122">Para desativar os recursos, é possível usar o mesmo procedimento, mas clique em **Desativar** em vez de **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="d4a41-122">To deactivate the features, you can use the same procedure, but click **Deactivate** rather than **Activate.**</span></span>  
  
##  <a name="to-activate-or-deactivate-reporting-services-central-administration-site-collection-feature"></a><a name="bkmk_centraladmin"></a><span data-ttu-id="d4a41-123">Para ativar ou desativar Reporting Services recurso de conjunto de sites de administração central:</span><span class="sxs-lookup"><span data-stu-id="d4a41-123">To Activate or Deactivate Reporting Services Central Administration Site Collection Feature:</span></span>  
  
1.  <span data-ttu-id="d4a41-124">Abra seu navegador na Administração Central do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d4a41-124">Open your browser to SharePoint Central Administration.</span></span>  
  
2.  <span data-ttu-id="d4a41-125">Clique em **Ações do Site**.</span><span class="sxs-lookup"><span data-stu-id="d4a41-125">Click **Site Actions**.</span></span>  
  
3.  <span data-ttu-id="d4a41-126">Clique em **Configurações de Site**.</span><span class="sxs-lookup"><span data-stu-id="d4a41-126">Click **Site Settings**.</span></span>  
  
4.  <span data-ttu-id="d4a41-127">Clique em **Recursos do Conjunto de Sites** no Grupo Administração do Conjunto de Sites.</span><span class="sxs-lookup"><span data-stu-id="d4a41-127">Click **Site Collection Features** in the Site Collection Administration Group.</span></span>  
  
5.  <span data-ttu-id="d4a41-128">Localize **Recurso da Administração Central do Servidor de Relatório** na lista.</span><span class="sxs-lookup"><span data-stu-id="d4a41-128">Find **Report Server Central Administration Feature** in the list.</span></span>  
  
6.  <span data-ttu-id="d4a41-129">Clique em **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="d4a41-129">Click **Activate**.</span></span>  
  
 <span data-ttu-id="d4a41-130">Para desativar o recurso, é possível usar o mesmo procedimento, mas clique em **Desativar** em vez de **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="d4a41-130">To deactivate the feature, you can use the same procedure, but click **Deactivate** rather than **Activate.**</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d4a41-131">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="d4a41-131">Next Steps</span></span>  
 <span data-ttu-id="d4a41-132">Depois que o recurso for ativado, será possível continuar com a integração do servidor.</span><span class="sxs-lookup"><span data-stu-id="d4a41-132">After the feature is activated, you can continue with server integration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4a41-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d4a41-133">See Also</span></span>  
 [<span data-ttu-id="d4a41-134">Instalar ou desinstalar o suplemento Reporting Services para SharePoint &#40;SharePoint 2010 e SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="d4a41-134">Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)  
  
  
