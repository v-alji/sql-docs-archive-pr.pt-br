---
title: Adicionar tipos de conteúdo do servidor de relatório a uma biblioteca (Reporting Services no modo integrado do SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ac9136c8-9ef4-484c-8e9d-05008a186db5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9e0ee56c235a54920fba5389a61f300eeaa65329
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684622"
---
# <a name="add-report-server-content-types-to-a-library-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="13cd1-102">Adicionar tipos de conteúdo do servidor de relatório a uma biblioteca (Reporting Services no modo integrado do SharePoint)</span><span class="sxs-lookup"><span data-stu-id="13cd1-102">Add Report Server Content Types to a Library (Reporting Services in SharePoint Integrated Mode)</span></span>
  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="13cd1-103">fornece tipos de conteúdo predefinidos do SharePoint usados para gerenciar arquivos de fonte de dados compartilhada (.rsds), modelos de relatórios (.smdl) e arquivos de definição de relatório (.rdl) do Construtor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="13cd1-103">provides predefined SharePoint content types that are used to manage shared data source (.rsds) files, report models (.smdl), and Report Builder report definition (.rdl) files.</span></span> <span data-ttu-id="13cd1-104">A adição de um tipo de conteúdo do **Construtor de Relatórios**, do **Modelo de Relatório**ou da **Fonte de Dados de Relatório** a uma biblioteca ativa o comando **Novo** para que você possa criar novos documentos desse tipo.</span><span class="sxs-lookup"><span data-stu-id="13cd1-104">Adding a **Report Builder Report**, **Report Model**, and **Report Data Source** content type to a library enables the **New** command so that you can create new documents of that type.</span></span>  
  
 <span data-ttu-id="13cd1-105">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]Modo do SharePoint</span><span class="sxs-lookup"><span data-stu-id="13cd1-105">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>  
  
 <span data-ttu-id="13cd1-106">Para adicionar tipos de conteúdo a uma biblioteca, é necessário que você seja administrador de site ou ter o nível de permissão Controle Total.</span><span class="sxs-lookup"><span data-stu-id="13cd1-106">To add content types to a library, you must be a site administrator or have Full Control level of permission.</span></span>  
  
 <span data-ttu-id="13cd1-107">Os tipos de conteúdo do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] e o gerenciamento de tipo de conteúdo serão automaticamente habilitados em todas as bibliotecas de documentos para conjuntos de sites existentes criados no modelo de site da **Central de Business Intelligence** .</span><span class="sxs-lookup"><span data-stu-id="13cd1-107">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types and content type management will automatically be enabled in all document libraries for existing site collections created from the following **Business Intelligence Center** site template.</span></span>  
  
 <span data-ttu-id="13cd1-108">Sites criados depois da integração do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] não terão os tipos de conteúdo do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] habilitados.</span><span class="sxs-lookup"><span data-stu-id="13cd1-108">Sites created after the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] integration will not have the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types enabled.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="13cd1-109">Se você **não** tiver configurado anteriormente tipos de conteúdo para uma biblioteca, primeiro habilite o gerenciamento de tipos de conteúdo e, depois, habilite os tipos de conteúdo do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="13cd1-109">If you have **not** previously configured content types for a library, first enable management of content types, then enable the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types.</span></span> <span data-ttu-id="13cd1-110">Consulte os procedimentos para habilitar o gerenciamento de tipo de conteúdo em uma única biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="13cd1-110">See the procedures on enabling content type management in a single document library.</span></span>  
  
 <span data-ttu-id="13cd1-111">**Vídeo rápido:** [(SSRS) Habilitando tipos de conteúdo no SharePoint2010.wmv](http://www.youtube.com/watch?v=yqhm3DrtT1w) (http://www.youtube.com/watch?v=yqhm3DrtT1w).</span><span class="sxs-lookup"><span data-stu-id="13cd1-111">**Short video:** [(SSRS) Enabling Content Types in SharePoint2010.wmv](http://www.youtube.com/watch?v=yqhm3DrtT1w) (http://www.youtube.com/watch?v=yqhm3DrtT1w).</span></span>  
  
 <span data-ttu-id="13cd1-112">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="13cd1-112">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="13cd1-113">Habilitar tipos de conteúdo em todas as bibliotecas de documentos em um centro de BI existente</span><span class="sxs-lookup"><span data-stu-id="13cd1-113">Enable content types in all document libraries in an existing BI center</span></span>](#bkmk_enable_all)  
  
-   [<span data-ttu-id="13cd1-114">Para habilitar o gerenciamento de tipo de conteúdo para uma única biblioteca de documentos (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="13cd1-114">To enable content type management for a single document library (SharePoint 2013)</span></span>](#bkmk_enable_content_management)  
  
-   [<span data-ttu-id="13cd1-115">Para adicionar tipos de conteúdo de Reporting Services (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="13cd1-115">To add Reporting Services content types (SharePoint 2013)</span></span>](#bkmk_add_single)  
  
-   [<span data-ttu-id="13cd1-116">Para habilitar o gerenciamento de tipo de conteúdo para uma única biblioteca de documentos (SharePoint 2010)</span><span class="sxs-lookup"><span data-stu-id="13cd1-116">To enable content type management for a single document library (SharePoint 2010)</span></span>](#bkmk_enable_content_management_2010)  
  
-   [<span data-ttu-id="13cd1-117">Para adicionar tipos de conteúdo de servidor de relatório (SharePoint 2010)</span><span class="sxs-lookup"><span data-stu-id="13cd1-117">To add report server content types (SharePoint 2010)</span></span>](#bkmk_add_single_2010)  
  
-   [<span data-ttu-id="13cd1-118">Para habilitar tipos de conteúdo e gerenciamento de conteúdo para vários sites de BI</span><span class="sxs-lookup"><span data-stu-id="13cd1-118">To enable Content types and content management for multiple BI sites</span></span>](#bkmk_enable_multiple_sites)  
  
##  <a name="enable-content-types-in-all-document-libraries-in-an-existing-bi-center"></a><a name="bkmk_enable_all"></a><span data-ttu-id="13cd1-119">Habilitar tipos de conteúdo em todas as bibliotecas de documentos em um centro de BI existente</span><span class="sxs-lookup"><span data-stu-id="13cd1-119">Enable content types in all document libraries in an existing BI center</span></span>  
  
1.  <span data-ttu-id="13cd1-120">Para habilitar os tipos de conteúdo e o gerenciamento de conteúdo em todas as bibliotecas de documentos em um site existente da **Central de Business Intelligence** , você pode alternar o recurso de integração do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="13cd1-120">To enable the content types and content management in all document libraries in an existing **Business Intelligence Center** site, you can toggle the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] integration feature.</span></span>  
  
2.  <span data-ttu-id="13cd1-121">Vá para **Configurações de site**.</span><span class="sxs-lookup"><span data-stu-id="13cd1-121">Go to **Site settings**.</span></span>  
  
    -   <span data-ttu-id="13cd1-122">No SharePoint 2013, clique no ícone **Configurações** .</span><span class="sxs-lookup"><span data-stu-id="13cd1-122">In SharePoint 2013, click the **Settings** icon.</span></span> <span data-ttu-id="13cd1-123">![Configurações do SharePoint](https://docs.microsoft.com/analysis-services/analysis-services/media/as-sharepoint2013-settings-gear.gif "Configurações do SharePoint")</span><span class="sxs-lookup"><span data-stu-id="13cd1-123">![SharePoint Settings](https://docs.microsoft.com/analysis-services/analysis-services/media/as-sharepoint2013-settings-gear.gif "SharePoint Settings")</span></span>  
  
    -   <span data-ttu-id="13cd1-124">No SharePoint 2010, clique em **Ações do Site**e, depois, em **Configurações de Site**.</span><span class="sxs-lookup"><span data-stu-id="13cd1-124">In SharePoint 2010, click **Site Actions**, then click **Site Settings**.</span></span>  
  
3.  <span data-ttu-id="13cd1-125">Clique em **recursos do conjunto de sites**.</span><span class="sxs-lookup"><span data-stu-id="13cd1-125">Click **Site collection features**.</span></span>  
  
4.  <span data-ttu-id="13cd1-126">Localize o **Recurso de Integração do Servidor de Relatório** e clique em **Desativar**.</span><span class="sxs-lookup"><span data-stu-id="13cd1-126">Find the **Report Server Integration Feature** and click **Deactivate**.</span></span>  
  
     <span data-ttu-id="13cd1-127">![rs_reportserver_integration_active](media/rs-reportserver-integration-active.gif "rs_reportserver_integration_active")</span><span class="sxs-lookup"><span data-stu-id="13cd1-127">![rs_reportserver_integration_active](media/rs-reportserver-integration-active.gif "rs_reportserver_integration_active")</span></span>  
  
5.  <span data-ttu-id="13cd1-128">Atualize o navegador e clique em **Ativar** para o **Recurso de Integração do Servidor de Relatório**.</span><span class="sxs-lookup"><span data-stu-id="13cd1-128">Refresh the browser then click **Activate** for the **Report Server Integration Feature**.</span></span>  
  
    <span data-ttu-id="13cd1-129">![Ativar](media/rs-reportserver-integration-deactivate.gif "rs_reportserver_integration_deactive")</span><span class="sxs-lookup"><span data-stu-id="13cd1-129">![Deactivate](media/rs-reportserver-integration-deactivate.gif "rs_reportserver_integration_deactive")</span></span>  
  
##  <a name="to-enable-content-type-management-for-a-single-document-library-sharepoint-2013"></a><a name="bkmk_enable_content_management"></a><span data-ttu-id="13cd1-130">Para habilitar o gerenciamento de tipo de conteúdo para uma única biblioteca de documentos (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="13cd1-130">To enable content type management for a single document library (SharePoint 2013)</span></span>  
  
1.  <span data-ttu-id="13cd1-131">Abra a biblioteca para a qual você deseja habilitar vários tipos de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="13cd1-131">Open the library for which you want to enable multiple content types.</span></span>  
  
2.  <span data-ttu-id="13cd1-132">Clique em **Biblioteca** na faixa de opções.</span><span class="sxs-lookup"><span data-stu-id="13cd1-132">Click **Library** in the ribbon.</span></span>  
  
     <span data-ttu-id="13cd1-133">![rs_SharePoint2013_LibraryRibbon](media/rs-sharepoint2013-libraryribbon.gif "rs_SharePoint2013_LibraryRibbon")</span><span class="sxs-lookup"><span data-stu-id="13cd1-133">![rs_SharePoint2013_LibraryRibbon](media/rs-sharepoint2013-libraryribbon.gif "rs_SharePoint2013_LibraryRibbon")</span></span>  
  
3.  <span data-ttu-id="13cd1-134">Na faixa de opções **Biblioteca** , clique em **Configurações da Biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="13cd1-134">On the **Library** ribbon, click **Library Settings**.</span></span> <span data-ttu-id="13cd1-135">Se não aparecer **Configurações da Biblioteca** ou se o botão estiver desabilitado, você não terá permissão para definir configurações da biblioteca, inclusive tipos de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="13cd1-135">If you do not see **Library Settings** or the button is disabled, you do not have permission to configure library settings, including content types.</span></span>  
  
     <span data-ttu-id="13cd1-136">![rs_SharePoint2013_LibrarySettings](media/rs-sharepoint2013-librarysettings.gif "rs_SharePoint2013_LibrarySettings")</span><span class="sxs-lookup"><span data-stu-id="13cd1-136">![rs_SharePoint2013_LibrarySettings](media/rs-sharepoint2013-librarysettings.gif "rs_SharePoint2013_LibrarySettings")</span></span>  
  
4.  <span data-ttu-id="13cd1-137">Na seção **Configurações Gerais** , clique em **Configurações avançadas**.</span><span class="sxs-lookup"><span data-stu-id="13cd1-137">In the **General Settings** section, click **Advanced settings**.</span></span>  
  
     <span data-ttu-id="13cd1-138">![rs_SharePoint2013_LibrarySettings_AdvancedSettings](media/rs-sharepoint2013-librarysettings-advancedsettings.gif "rs_SharePoint2013_LibrarySettings_AdvancedSettings")</span><span class="sxs-lookup"><span data-stu-id="13cd1-138">![rs_SharePoint2013_LibrarySettings_AdvancedSettings](media/rs-sharepoint2013-librarysettings-advancedsettings.gif "rs_SharePoint2013_LibrarySettings_AdvancedSettings")</span></span>  
  
5.  <span data-ttu-id="13cd1-139">Na seção **Tipos de Conteúdo** , selecione **Sim** para permitir o gerenciamento de tipos de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="13cd1-139">In the **Content Types** section, select **Yes** to allow management of content types.</span></span>  
  
6.  <span data-ttu-id="13cd1-140">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="13cd1-140">Click **OK**.</span></span>  
  
##  <a name="to-add-reporting-services-content-types-sharepoint-2013"></a><a name="bkmk_add_single"></a> <span data-ttu-id="13cd1-141">Para adicionar tipos de conteúdo do Reporting Services (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="13cd1-141">To add Reporting Services content types (SharePoint 2013)</span></span>  
  
1.  <span data-ttu-id="13cd1-142">Abra a biblioteca para a qual você deseja adicionar tipos de conteúdo do Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="13cd1-142">Open the library for which you want to add Reporting Services content types.</span></span>  
  
2.  <span data-ttu-id="13cd1-143">Na faixa de opções, clique em **Biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="13cd1-143">On the ribbon, click **Library**.</span></span>  
  
3.  <span data-ttu-id="13cd1-144">Clique em **Configurações da Biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="13cd1-144">Click **Library Settings**.</span></span>  
  
4.  <span data-ttu-id="13cd1-145">Em **Tipos de Conteúdo**, clique em **Adicionar a partir de tipos de conteúdo de site existentes**.</span><span class="sxs-lookup"><span data-stu-id="13cd1-145">Under **Content Types**, click **Add from existing site content types**.</span></span>  
  
5.  <span data-ttu-id="13cd1-146">Em **Selecionar tipos de conteúdo de site de**, selecione **Tipos de Conteúdo do SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="13cd1-146">In **Select site content types from**, select **SQL Server Reporting Services Content Types**.</span></span>  
  
6.  <span data-ttu-id="13cd1-147">Na lista **Tipos Disponíveis de Conteúdo do Site** , clique em **Construtor de Relatórios**e em **Adicionar** para mover o tipo de conteúdo selecionado para a lista **Tipos de conteúdo a serem adicionados** .</span><span class="sxs-lookup"><span data-stu-id="13cd1-147">In the **Available Site Content Types** list, click **Report Builder**, and then click **Add** to move the selected content type to the **Content types to add** list.</span></span>  
  
7.  <span data-ttu-id="13cd1-148">Para adicionar os tipos de conteúdo **Modelo de Relatório** e **Fonte de Dados do Relatório** , repita a etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="13cd1-148">To add **Report Model** and **Report Data Source** content types, repeat the previous step.</span></span>  
  
8.  <span data-ttu-id="13cd1-149">Quando terminar de adicionar tipos de conteúdo, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="13cd1-149">When you finish adding content types, click **OK**.</span></span>  
  
9. > [!NOTE]  
    >  <span data-ttu-id="13cd1-150">Se o grupo de tipos de conteúdo [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]**Tipos de Conteúdo do SQL Server Reporting Services** não estiver visível na página **Adicionar Tipos de Conteúdo** , uma das seguintes condições será verdadeira:</span><span class="sxs-lookup"><span data-stu-id="13cd1-150">If the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content type group **SQL Server Reporting Services Content Types** is not visible on the **Add Content Types** page, one of the following conditions is true:</span></span>  
  
    -   <span data-ttu-id="13cd1-151">O suplemento [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] para produtos do SharePoint não foi instalado.</span><span class="sxs-lookup"><span data-stu-id="13cd1-151">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] add-in for SharePoint products has not been installed.</span></span> <span data-ttu-id="13cd1-152">Para obter mais informações, consulte [instalar ou desinstalar o suplemento Reporting Services para sharepoint &#40;sharepoint 2010 e sharepoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="13cd1-152">For more information, see [Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md).</span></span> <span data-ttu-id="13cd1-153">O tópico inclui informações sobre a instalação do suplemento e apresenta as etapa de instalação somente de arquivos do suplemento para oferecer soluções alternativas.</span><span class="sxs-lookup"><span data-stu-id="13cd1-153">The topic includes information on installing the add-in and stepping through a files only installation of the add-in to work around issues.</span></span>  
  
    -   <span data-ttu-id="13cd1-154">O suplemento está instalado, mas o recurso de coleta de site **Recurso de Integração do Servidor de Relatório** não está ativo.</span><span class="sxs-lookup"><span data-stu-id="13cd1-154">The add-in is installed but the site collection feature **Report Server Integration Feature** is not active.</span></span> <span data-ttu-id="13cd1-155">Confirme o recurso de coleta de site em **Configurações do Site**.</span><span class="sxs-lookup"><span data-stu-id="13cd1-155">Verify the site collection feature in **Site Settings**.</span></span>  
  
    -   <span data-ttu-id="13cd1-156">Todos os tipos de conteúdo do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] já foram adicionados à biblioteca.</span><span class="sxs-lookup"><span data-stu-id="13cd1-156">All of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types have already been added to the library.</span></span> <span data-ttu-id="13cd1-157">Se todos os tipos de conteúdo são parte de uma biblioteca, o grupo é removido da página **Adicionar Tipos de Conteúdo** .</span><span class="sxs-lookup"><span data-stu-id="13cd1-157">If all the content types are part of a library, then the group is removed from the **Add Content Types** page.</span></span> <span data-ttu-id="13cd1-158">Se você excluir um ou mais dos tipos de conteúdo do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , o grupo **Tipos de Conteúdo do SQL Server Reporting Services** ficará visível na página **Adicionar Tipos de Conteúdo** .</span><span class="sxs-lookup"><span data-stu-id="13cd1-158">If you delete one or more of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types, then the group **SQL Server Reporting Services Content Types** will be visible on the **Add Content Types** page.</span></span>  
  
##  <a name="to-enable-content-type-management-for-a-single-document-library-sharepoint-2010"></a><a name="bkmk_enable_content_management_2010"></a><span data-ttu-id="13cd1-159">Para habilitar o gerenciamento de tipo de conteúdo para uma única biblioteca de documentos (SharePoint 2010)</span><span class="sxs-lookup"><span data-stu-id="13cd1-159">To enable content type management for a single document library (SharePoint 2010)</span></span>  
  
1.  <span data-ttu-id="13cd1-160">Abra a biblioteca para a qual você deseja habilitar vários tipos de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="13cd1-160">Open the library for which you want to enable multiple content types.</span></span> <span data-ttu-id="13cd1-161">Na barra de menus da biblioteca, os seguintes menus serão exibidos: **Novo**, **Carregar**, **Ações**e **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="13cd1-161">On the library menu bar, you should see the following menus: **New**, **Upload**, **Actions**, and **Settings**.</span></span> <span data-ttu-id="13cd1-162">Se **Configurações**não aparecer, você não terá permissão para adicionar um tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="13cd1-162">If you do not see **Settings**, you do not have permission to add a content type.</span></span>  
  
2.  <span data-ttu-id="13cd1-163">Na faixa de opções **Ferramentas de Biblioteca** , clique em **Biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="13cd1-163">On the **Library Tools** ribbon, click **Library**.</span></span>  
  
     <span data-ttu-id="13cd1-164">![rs_SharePoint2010_LibraryRibbon](media/rs-sharepoint2010-libraryribbon.gif "rs_SharePoint2010_LibraryRibbon")</span><span class="sxs-lookup"><span data-stu-id="13cd1-164">![rs_SharePoint2010_LibraryRibbon](media/rs-sharepoint2010-libraryribbon.gif "rs_SharePoint2010_LibraryRibbon")</span></span>  
  
3.  <span data-ttu-id="13cd1-165">No grupo da faixa de opções **Configurações** , clique em **Configurações da Biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="13cd1-165">On the **Settings** ribbon group, click **Library Settings**.</span></span>  
  
4.  <span data-ttu-id="13cd1-166">Em **Configurações Gerais**, clique em **Configurações avançadas**.</span><span class="sxs-lookup"><span data-stu-id="13cd1-166">Under **General Settings**, click **Advanced settings**.</span></span>  
  
5.  <span data-ttu-id="13cd1-167">Na seção **Tipos de Conteúdo** , selecione **Sim** para permitir o gerenciamento de tipos de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="13cd1-167">In the **Content Types** section, select **Yes** to allow management of content types.</span></span>  
  
6.  <span data-ttu-id="13cd1-168">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="13cd1-168">Click **OK**.</span></span>  
  
##  <a name="to-add-report-server-content-types-sharepoint-2010"></a><a name="bkmk_add_single_2010"></a><span data-ttu-id="13cd1-169">Para adicionar tipos de conteúdo do servidor de relatório (SharePoint 2010)</span><span class="sxs-lookup"><span data-stu-id="13cd1-169">To add report server content types (SharePoint 2010)</span></span>  
  
1.  <span data-ttu-id="13cd1-170">Abra a biblioteca para a qual você deseja adicionar tipos de conteúdo do Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="13cd1-170">Open the library for which you want to add Reporting Services content types.</span></span>  
  
2.  <span data-ttu-id="13cd1-171">Nas guias de faixa de opções **Ferramentas de Biblioteca** , clique na **guia de Biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="13cd1-171">On the **Library Tools** ribbon tabs, click the **Library tab**.</span></span>  
  
3.  <span data-ttu-id="13cd1-172">No grupo da faixa de opções **Configurações** , clique em **Configurações da Biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="13cd1-172">On the **Settings** ribbon group, click **Library Settings**.</span></span>  
  
4.  <span data-ttu-id="13cd1-173">Em **Tipos de Conteúdo**, clique em **Adicionar a partir de tipos de conteúdo de site existentes**.</span><span class="sxs-lookup"><span data-stu-id="13cd1-173">Under **Content Types**, click **Add from existing site content types**.</span></span>  
  
5.  <span data-ttu-id="13cd1-174">Na seção **Selecionar Tipos de Conteúdo** , em **Selecionar tipos de conteúdo de site de**, clique na seta para selecionar **Tipos de Conteúdo do SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="13cd1-174">In the **Select Content Types** section, in **Select site content types from**, click the arrow to select **SQL Server Reporting Services Content Types**.</span></span>  
  
6.  <span data-ttu-id="13cd1-175">Na lista **Tipos Disponíveis de Conteúdo do Site** , clique em **Construtor de Relatórios**e em **Adicionar** para mover o tipo de conteúdo selecionado para a lista **Tipos de conteúdo a serem adicionados** .</span><span class="sxs-lookup"><span data-stu-id="13cd1-175">In the **Available Site Content Types** list, click **Report Builder**, and then click **Add** to move the selected content type to the **Content types to add** list.</span></span>  
  
7.  <span data-ttu-id="13cd1-176">Para adicionar os tipos de conteúdo **Modelo de Relatório** e **Fonte de Dados do Relatório** , repita a etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="13cd1-176">To add **Report Model** and **Report Data Source** content types, repeat the previous step.</span></span>  
  
8.  <span data-ttu-id="13cd1-177">Quando terminar de adicionar tipos de conteúdo, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="13cd1-177">When you finish adding content types, click **OK**.</span></span>  
  
##  <a name="to-enable-content-types-and-content-management-for-multiple-bi-sites"></a><a name="bkmk_enable_multiple_sites"></a><span data-ttu-id="13cd1-178">Para habilitar tipos de conteúdo e gerenciamento de conteúdo para vários sites de BI</span><span class="sxs-lookup"><span data-stu-id="13cd1-178">To enable Content types and content management for multiple BI sites</span></span>  
  
1.  <span data-ttu-id="13cd1-179">Para servidores de relatório do SQL Server Reporting Services 2008 e 2008 R2, você pode habilitar tipos de conteúdo e gerenciamento de conteúdo para vários sites do Business Intelligence Center:</span><span class="sxs-lookup"><span data-stu-id="13cd1-179">For SQL Server Reporting Services 2008 and 2008 R2 report servers, you can enable content types and content management for multiple Business Intelligence Center sites:</span></span>  
  
2.  <span data-ttu-id="13cd1-180">Em Administração Central do SharePoint, clique em **Configurações de Aplicativos Gerais**.</span><span class="sxs-lookup"><span data-stu-id="13cd1-180">In SharePoint Central Administration, click **General Applications settings**.</span></span> <span data-ttu-id="13cd1-181">Na seção **SQL Server Reporting Services (2008 e 2008 R2)** , clique em **Integração do Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="13cd1-181">In the **SQL Server Reporting Services (2008 and 2008 R2)** section, click **Reporting Services Integration**.</span></span>  
  
     <span data-ttu-id="13cd1-182">![rs_general_app_settings](media/rs-general-app-settings.gif "rs_general_app_settings")</span><span class="sxs-lookup"><span data-stu-id="13cd1-182">![rs_general_app_settings](media/rs-general-app-settings.gif "rs_general_app_settings")</span></span>  
  
3.  <span data-ttu-id="13cd1-183">Clique em **Recurso ativo em todos os conjuntos de sites existentes**.</span><span class="sxs-lookup"><span data-stu-id="13cd1-183">Click **Activate feature in all exciting site collections**.</span></span>  
  
     <span data-ttu-id="13cd1-184">![rs_general_app_settings_old_integrations](media/rs-general-app-settings-old-integrations.gif "rs_general_app_settings_old_integrations")</span><span class="sxs-lookup"><span data-stu-id="13cd1-184">![rs_general_app_settings_old_integrations](media/rs-general-app-settings-old-integrations.gif "rs_general_app_settings_old_integrations")</span></span>  
  
4.  <span data-ttu-id="13cd1-185">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="13cd1-185">Click **Ok**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13cd1-186">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="13cd1-186">See Also</span></span>  
 <span data-ttu-id="13cd1-187">[Referência de permissão de lista e site do SharePoint para itens do servidor de relatório](security/sharepoint-site-and-list-permission-reference-for-report-server-items.md) </span><span class="sxs-lookup"><span data-stu-id="13cd1-187">[SharePoint Site and List Permission Reference for Report Server Items](security/sharepoint-site-and-list-permission-reference-for-report-server-items.md) </span></span>  
 [<span data-ttu-id="13cd1-188">Iniciar Construtor de Relatórios &#40;Construtor de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="13cd1-188">Start Report Builder &#40;Report Builder&#41;</span></span>](report-builder/start-report-builder.md)  
  
  
