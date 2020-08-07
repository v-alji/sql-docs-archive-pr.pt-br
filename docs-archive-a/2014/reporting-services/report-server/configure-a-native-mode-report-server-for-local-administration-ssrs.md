---
title: Configurar um servidor de relatório no modo nativo para a Administração Local (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- UAC
- installing Reporting Services
- Windows Vista
- Localhost
- windows server 2008
- Vista
ms.assetid: 312c6bb8-b3f7-4142-a55f-c69ee15bbf52
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ad53f293ef825a382d9e39b58527a36ef291687a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575610"
---
# <a name="configure-a-native-mode-report-server-for-local-administration-ssrs"></a><span data-ttu-id="a1d3e-102">Configurar um servidor de relatório no modo nativo para a Administração Local (SSRS)</span><span class="sxs-lookup"><span data-stu-id="a1d3e-102">Configure a Native Mode Report Server for Local Administration (SSRS)</span></span>
  <span data-ttu-id="a1d3e-103">A implantação de um servidor de relatório do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] em um dos seguintes sistemas operacionais exigirá mais etapas de configuração se você desejar administrar localmente a instância do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-103">Deploying a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report server on one of the following operating systems requires more configuration steps if you want to administer the report server instance locally.</span></span> <span data-ttu-id="a1d3e-104">Este tópico explica como configurar o servidor de relatório para administração local.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-104">This topic explains how to configure the report server for local administration.</span></span> <span data-ttu-id="a1d3e-105">Se você ainda não instalou ou configurou o servidor de relatório, consulte [instalar SQL Server 2014 no assistente de instalação &#40;a instalação&#41;](../../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md) e [gerenciar um servidor de relatório no modo nativo do Reporting Services](manage-a-reporting-services-native-mode-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="a1d3e-105">If you have not yet installed or configured the report server, see [Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](../../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md) and [Manage a Reporting Services Native Mode Report Server](manage-a-reporting-services-native-mode-report-server.md).</span></span>  
  
||  
|-|  
|<span data-ttu-id="a1d3e-106">**[!INCLUDE[applies](../../includes/applies-md.md)]** [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Modo nativo</span><span class="sxs-lookup"><span data-stu-id="a1d3e-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode</span></span>|  
  
-   [!INCLUDE[winblue_server_2](../../includes/winblue-server-2-md.md)]  
  
-   [!INCLUDE[winblue_client_2](../../includes/winblue-client-2-md.md)]  
  
-   [!INCLUDE[win8](../../includes/win8-md.md)]  
  
-   [!INCLUDE[win8srv](../../includes/win8srv-md.md)]  
  
-   [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)]  
  
-   [!INCLUDE[win7](../../includes/win7-md.md)]  
  
-   [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)]  
  
 <span data-ttu-id="a1d3e-107">Como o sistema operacional destacado limita as permissões, os membros do grupo Administradores local executam a maioria dos aplicativos como se estivessem usando a conta de Usuário Padrão.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-107">Because the noted operating systems limit permissions, members of the local Administrators group run most applications as if they are using the Standard User account.</span></span>  
  
 <span data-ttu-id="a1d3e-108">Embora essa prática melhore a segurança geral do sistema, ela impede que você use as atribuições de funções internas predefinidas que o Reporting Services cria para administradores locais.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-108">While this practice improves the overall security of your system, it prevents you from using the predefined, built-in role assignments that Reporting Services creates for local administrators.</span></span>  
  
-   [<span data-ttu-id="a1d3e-109">Visão geral de alterações de configuração</span><span class="sxs-lookup"><span data-stu-id="a1d3e-109">Overview of Configuration Changes</span></span>](#bkmk_configuraiton_overview)  
  
-   [<span data-ttu-id="a1d3e-110">Para configurar um Servidor de Relatório Local e uma Administração do Gerenciador de Relatórios</span><span class="sxs-lookup"><span data-stu-id="a1d3e-110">To Configure Local Report Server and Report Manager Administration</span></span>](#bkmk_configure_local_server)  
  
-   [<span data-ttu-id="a1d3e-111">Para configurar o SQL Server Management Studio (SSMS) para a administração de servidor de relatórios local</span><span class="sxs-lookup"><span data-stu-id="a1d3e-111">To Configure SQL Server Management Studio (SSMS) for local report server administration</span></span>](#bkmk_configure_ssms)  
  
-   [<span data-ttu-id="a1d3e-112">Para configurar o SQL Server Data Tools BI (SSDT) para publicar um Servidor de Relatórios Local</span><span class="sxs-lookup"><span data-stu-id="a1d3e-112">To Configure SQL Server Data Tools BI (SSDT) to Publish to a Local Report Server</span></span>](#bkmk_configure_ssdt)  
  
-   [<span data-ttu-id="a1d3e-113">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="a1d3e-113">Additional Information</span></span>](#bkmk_addiitonal_informaiton)  
  
##  <a name="overview-of-configuration-changes"></a><a name="bkmk_configuraiton_overview"></a><span data-ttu-id="a1d3e-114">Visão geral das alterações de configuração</span><span class="sxs-lookup"><span data-stu-id="a1d3e-114">Overview of Configuration Changes</span></span>  
 <span data-ttu-id="a1d3e-115">As seguintes alterações de configuração configuram o servidor para que você possa usar permissões de usuário padrão para gerenciar o conteúdo e as operações do servidor de relatório:</span><span class="sxs-lookup"><span data-stu-id="a1d3e-115">The following configuration changes configure the server so that you can use standard user permissions to manage report server content and operations:</span></span>  
  
-   <span data-ttu-id="a1d3e-116">Adicione URLs do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] a sites confiáveis.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-116">Add [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] URLs to trusted sites.</span></span> <span data-ttu-id="a1d3e-117">Por padrão, o Internet Explorer que é executado nos sistemas operacionais listados é executado no **Modo Protegido**, um recurso que impede que solicitações do navegador alcancem processos de nível superior executados no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-117">By default, Internet Explorer running on the listed operating systems runs in **Protected Mode**, a feature that blocks browser requests from reaching high-level processes that run on the same computer.</span></span> <span data-ttu-id="a1d3e-118">Você pode desabilitar o modo protegido para os aplicativos do servidor de relatório adicionando-os como Sites Confiáveis.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-118">You can disable protected mode for the report server applications by adding them as Trusted Sites.</span></span>  
  
-   <span data-ttu-id="a1d3e-119">Crie atribuições de função que concedam a você, o administrador do servidor de relatório, permissão para gerenciar o conteúdo e as operações, sem precisar usar o recurso **Executar como administrador** no Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-119">Create role assignments that grant you, the report server administrator, permission to manage content and operations without having to use the **Run as administrator** feature on Internet Explorer.</span></span> <span data-ttu-id="a1d3e-120">Ao criar atribuições de funções para sua conta de usuário do Windows, você obtém acesso a um servidor de relatório com permissões de Gerenciador de Conteúdo e Administrador do Sistema por meio de atribuições explícitas de funções que substituem as atribuições de funções internas predefinidas que o Reporting Services cria.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-120">By creating role assignments for your Windows user account, you gain access to a report server with Content Manager and System Administrator permissions through explicit role assignments that replace the predefined, built-in role assignments that Reporting Services creates.</span></span>  
  
##  <a name="to-configure-local-report-server-and-report-manager-administration"></a><a name="bkmk_configure_local_server"></a><span data-ttu-id="a1d3e-121">Para configurar o servidor de relatório local e a administração do Report Manager</span><span class="sxs-lookup"><span data-stu-id="a1d3e-121">To Configure Local Report Server and Report Manager Administration</span></span>  
 <span data-ttu-id="a1d3e-122">Conclua as etapas de configuração nessa seção se você estiver navegando para um servidor de relatórios local e vir erros semelhantes ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="a1d3e-122">Complete the configuration steps in this section if you are browsing to a local report server and you see errors similar to the following:</span></span>  
  
-   <span data-ttu-id="a1d3e-123">O usuário `'Domain\[user name]`' não tem as permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-123">User `'Domain\[user name]`' does not have required permissions.</span></span> <span data-ttu-id="a1d3e-124">Verifique se as permissões suficientes foram concedidas e as restrições do UAC (Controle da conta de usuário) do Windows foram resolvidas.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-124">Verify that sufficient permissions have been granted and Windows User Account Control (UAC) restrictions have been addressed.</span></span>  
  
###  <a name="trusted-site-settings-in-the-browser"></a><a name="bkmk_site_settings"></a><span data-ttu-id="a1d3e-125">Configurações de site confiáveis no navegador</span><span class="sxs-lookup"><span data-stu-id="a1d3e-125">Trusted Site Settings in the Browser</span></span>  
  
1.  <span data-ttu-id="a1d3e-126">Abra uma janela do navegador com permissões Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-126">Open a browser window with Run as administrator permissions.</span></span> <span data-ttu-id="a1d3e-127">No menu **Iniciar** , clique em **Todos os Programas**, clique com o botão direito do mouse em **Internet Explorer**e selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-127">From the **Start** menu, click **All Programs**, right-click **Internet Explorer**, and select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="a1d3e-128">Clique em **Permitir** para continuar.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-128">Click **Allow** to continue.</span></span>  
  
3.  <span data-ttu-id="a1d3e-129">No endereço da URL, insira a URL do Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-129">In the URL address, enter the Report Manager URL.</span></span> <span data-ttu-id="a1d3e-130">Para obter instruções, consulte [Gerenciador de Relatórios &#40;modo nativo do SSRS&#41;](../report-manager-ssrs-native-mode.md) em Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1d3e-130">For instructions, see [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
4.  <span data-ttu-id="a1d3e-131">Clique em **Ferramentas**.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-131">Click **Tools**.</span></span>  
  
5.  <span data-ttu-id="a1d3e-132">Clique em **Opções da Internet**.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-132">Click **Internet Options**.</span></span>  
  
6.  <span data-ttu-id="a1d3e-133">Clique em **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-133">Click **Security**.</span></span>  
  
7.  <span data-ttu-id="a1d3e-134">Clique em **Sites Confiáveis**.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-134">Click **Trusted Sites**.</span></span>  
  
8.  <span data-ttu-id="a1d3e-135">Clique em **Sites**.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-135">Click **Sites**.</span></span>  
  
9. <span data-ttu-id="a1d3e-136">Adicione `http://<your-server-name>`.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-136">Add `http://<your-server-name>`.</span></span>  
  
10. <span data-ttu-id="a1d3e-137">Desmarque a caixa de seleção **Exigir certificação do servidor (https:) para todos os sites desta zona** se não estiver usando HTTPS para o site padrão.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-137">Clear the check box **Require server certification (https:) for all sites in this zone** if you are not using HTTPS for the default site.</span></span>  
  
11. <span data-ttu-id="a1d3e-138">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-138">Click **Add**.</span></span>  
  
12. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
###  <a name="report-manager-folder-settings"></a><a name="bkmk_configure_folder_settings"></a> <span data-ttu-id="a1d3e-139">Configurações da pasta do Gerenciador de Relatórios</span><span class="sxs-lookup"><span data-stu-id="a1d3e-139">Report Manager Folder Settings</span></span>  
  
1.  <span data-ttu-id="a1d3e-140">No Gerenciador de Relatórios, na página inicial, clique em **Configurações de Pasta**.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-140">In Report Manager, on the Home page, click **Folder Settings**.</span></span>  
  
2.  <span data-ttu-id="a1d3e-141">Na página Configurações de Pasta, clique em **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-141">In the Folder Settings page, click **Security**.</span></span>  
  
3.  <span data-ttu-id="a1d3e-142">Clique em **Atribuição de Nova Função**.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-142">Click **New Role Assignment**.</span></span>  
  
4.  <span data-ttu-id="a1d3e-143">No campo **Nome do grupo ou do usuário** , conta de usuário do Windows neste formato: `<domain>\<user>`.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-143">In the **Group or user name** field, type your Windows user account in this format: `<domain>\<user>`.</span></span>  
  
5.  <span data-ttu-id="a1d3e-144">Selecione **Gerenciador de Conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-144">Select **Content Manager**.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
###  <a name="report-manager-site-settings"></a><a name="bkmk_configure_site_settings"></a> <span data-ttu-id="a1d3e-145">Configurações do Site do Gerenciador de Relatórios</span><span class="sxs-lookup"><span data-stu-id="a1d3e-145">Report Manager Site Settings</span></span>  
  
1.  <span data-ttu-id="a1d3e-146">Abra seu navegador com privilégios administrativos e navegue até o gerenciador de relatórios, `http://<server name>/reports`.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-146">Open your browser with administrative privileges and browse to report manager, `http://<server name>/reports`.</span></span>  
  
2.  <span data-ttu-id="a1d3e-147">Clique em **Configurações de Site** no canto superior da Página Inicial.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-147">Click **Site Settings** in the upper corner of the Home page.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="a1d3e-148">**Observação:** se a opção **Configurações de Site** não for exibida, feche e reabra o navegador, e navegue até o gerenciador de relatórios com privilégios administrativos.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-148">**Note:** If you do not see the **Site Settings** option, close and reopen your browser and browse to report manager with administrative privileges.</span></span>  
  
3.  <span data-ttu-id="a1d3e-149">Clique em **segurança**.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-149">Click **security**.</span></span>  
  
4.  <span data-ttu-id="a1d3e-150">Clique em **Atribuição de Nova Função**.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-150">Click **New Role Assignment**.</span></span>  
  
5.  <span data-ttu-id="a1d3e-151">No campo **Nome do grupo ou do usuário** , conta de usuário do Windows neste formato: `<domain>\<user>`.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-151">In the **Group or user name** field, type your Windows user account in this format: `<domain>\<user>`.</span></span>  
  
6.  <span data-ttu-id="a1d3e-152">Selecione **Administrador do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-152">Select **System Administrator**.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="a1d3e-153">Feche o Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-153">Close Report Manager.</span></span>  
  
9. <span data-ttu-id="a1d3e-154">Abra novamente o Gerenciador de Relatórios no Internet Explorer sem usar **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-154">Re-open Report Manager in Internet Explorer, without using **Run as administrator**.</span></span>  
  
##  <a name="to-configure-sql-server-management-studio-ssms-for-local-report-server-administration"></a><a name="bkmk_configure_ssms"></a><span data-ttu-id="a1d3e-155">Para configurar o SQL Server Management Studio (SSMS) para a administração do servidor de relatório local</span><span class="sxs-lookup"><span data-stu-id="a1d3e-155">To Configure SQL Server Management Studio (SSMS) for local report server administration</span></span>  
 <span data-ttu-id="a1d3e-156">Por padrão, você não pode acessar todas as propriedades do servidor de relatório disponíveis no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] a menos que inicie o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] com privilégios administrativos.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-156">By default, you cannot access all of the report server properties available in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] unless you start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] with administrative privileges.</span></span>  
  
 <span data-ttu-id="a1d3e-157">**Para configurar as atribuições de função do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]** , você não precisa iniciar o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] com permissões elevadas a cada vez:</span><span class="sxs-lookup"><span data-stu-id="a1d3e-157">**To configure [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]** role properties and role assignments so you do not need to start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] with elevated permissions each time:</span></span>  
  
-   <span data-ttu-id="a1d3e-158">No menu **Iniciar** , clique em **Todos os Programas**, clique em **SQL Server 2014**, clique com o botão direito do mouse em **[!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]** e clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-158">From the **Start** menu, click **All Programs**, click **SQL Server 2014**, right-click **[!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]**, and then click **Run as administrator**.</span></span>  
  
-   <span data-ttu-id="a1d3e-159">Conecte-se ao servidor do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] local.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-159">Connect to your local [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] server.</span></span>  
  
-   <span data-ttu-id="a1d3e-160">No nó **Segurança** , clique em **Funções do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-160">In the **Security** node, click **System Roles**.</span></span>  
  
-   <span data-ttu-id="a1d3e-161">Clique com o botão direito do mouse em **Administrador do Sistema** e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-161">Right-click **System Administrator** and then click **Properties**.</span></span>  
  
-   <span data-ttu-id="a1d3e-162">Na página **Propriedades de Função do Sistema** , selecione **Exibir propriedades do servidor de relatório**.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-162">In the **System Role Properties** page, select **View report server properties**.</span></span> <span data-ttu-id="a1d3e-163">Selecione as outras propriedades que você quer associar aos membros da função administradores do sistema.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-163">Select any other properties you want associated with members of the system administrators role.</span></span>  
  
-   <span data-ttu-id="a1d3e-164">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-164">Click **OK**.</span></span>  
  
-   <span data-ttu-id="a1d3e-165">Feche o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1d3e-165">Close [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]</span></span>  
  
-   <span data-ttu-id="a1d3e-166">Para adicionar um usuário à função do sistema "administrador do sistema", consulte a seção [Configurações do Site do Gerenciador de Relatórios](#bkmk_configure_site_settings) anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-166">To add a user to the system role "system administrator", see the [Report Manager Site Settings](#bkmk_configure_site_settings) section earlier in this topic.</span></span>  
  
 <span data-ttu-id="a1d3e-167">Agora, quando você abre o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] e não seleciona explicitamente **Executar como administrador** , tem acesso às propriedades do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-167">Now when you open [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and do not explicitly select **Run as administrator** you have access to the report server properties.</span></span>  
  
##  <a name="to-configure-sql-server-data-tools-bi-ssdt-to-publish-to-a-local-report-server"></a><a name="bkmk_configure_ssdt"></a><span data-ttu-id="a1d3e-168">Para configurar o BI de SQL Server Data Tools (SSDT) para publicar em um servidor de relatório local</span><span class="sxs-lookup"><span data-stu-id="a1d3e-168">To Configure SQL Server Data Tools BI (SSDT) to Publish to a Local Report Server</span></span>  
 <span data-ttu-id="a1d3e-169">Se você instalou o [!INCLUDE[SSDTDev11](../../includes/ssdtdev11-md.md)] em um dos sistemas operacionais listados na primeira seção desse tópico, e quiser que o SSDT interaja com um servidor de relatório de modo Nativo local, receberá erros de permissão a menos que abra o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] com permissões elevadas ou configure as funções de serviços de relatório.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-169">If you installed [!INCLUDE[SSDTDev11](../../includes/ssdtdev11-md.md)] on one of the operating systems listed in the first section of this topic, and you want SSDT to interact with a local Native mode report server, you will experiences permission errors unless you open [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] with elevated permissions or configure reporting services roles.</span></span> <span data-ttu-id="a1d3e-170">Por exemplo, se você não tiver permissões adequadas, terá problemas semelhantes aos seguintes:</span><span class="sxs-lookup"><span data-stu-id="a1d3e-170">For example, if you do not have sufficient permissions, you experience issues similar to the following:</span></span>  
  
-   <span data-ttu-id="a1d3e-171">Quando você tentar implantar itens de relatório no servidor de relatório local, verá uma mensagem de erro semelhante à seguinte na janela **Lista de Erros** :</span><span class="sxs-lookup"><span data-stu-id="a1d3e-171">When you attempt to deploy report items to the local report server, you see an error message similar to the following in the **Error List** window:</span></span>  
  
    -   <span data-ttu-id="a1d3e-172">As permissões concedidas ao usuário 'Domain\\<nome de usuário\>' são insuficientes para a execução dessa operação.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-172">The permissions granted to user 'Domain\\<user name\>' are insufficient for performing this operation.</span></span>  
  
 <span data-ttu-id="a1d3e-173">**Para executar com permissões elevadas a cada vez que você abrir o SSDT:**</span><span class="sxs-lookup"><span data-stu-id="a1d3e-173">**To run with elevated permissions each time you open SSDT:**</span></span>  
  
1.  <span data-ttu-id="a1d3e-174">Na tela iniciar, digite `sql server` e clique com o botão direito do mouse em **SQL Server Data Tools para Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-174">From the start screen, type `sql server` and then right-click **SQL Server Data Tools for Visual Studio**.</span></span> <span data-ttu-id="a1d3e-175">Clique em **Executar como administrador**</span><span class="sxs-lookup"><span data-stu-id="a1d3e-175">Click **Run as administrator**</span></span>  
  
     <span data-ttu-id="a1d3e-176">**Ou**em sistemas operacionais mais antigos:</span><span class="sxs-lookup"><span data-stu-id="a1d3e-176">**Or**, on older operating systems:</span></span>  
  
     <span data-ttu-id="a1d3e-177">No menu **Iniciar** , clique em **Todos os Programas**, clique em **SQL Server 2014**, clique com o botão direito do mouse em **Ferramentas de Dados do SQL Server**e clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-177">From the **Start** menu, click **All Programs**, click **SQL Server 2014**, right-click **SQL Server Data Tools**, and then click **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="a1d3e-178">Clique em **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-178">Click **Continue**.</span></span>  
  
3.  <span data-ttu-id="a1d3e-179">Clique em **Executar Programa**.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-179">Click **Run Program**.</span></span>  
  
 <span data-ttu-id="a1d3e-180">Agora você deve poder implantar relatórios e outros itens em um servidor de relatório local.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-180">You should now be able to deploy reports and other items to a local report server.</span></span>  
  
 <span data-ttu-id="a1d3e-181">**Para configurar as atribuições de função do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , você não precisa iniciar o SSDT com permissões elevadas a cada vez:**</span><span class="sxs-lookup"><span data-stu-id="a1d3e-181">**To configure [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] role assignments so you do not need to start SSDT with elevated permissions each time:**</span></span>  
  
-   <span data-ttu-id="a1d3e-182">Consulte as seções [Configurações da pasta do Gerenciador de Relatórios](#bkmk_configure_folder_settings) e [Configurações do Site do Gerenciador de Relatórios](#bkmk_configure_site_settings) anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-182">See the [Report Manager Folder Settings](#bkmk_configure_folder_settings) and [Report Manager Site Settings](#bkmk_configure_site_settings) sections earlier in this topic.</span></span>  
  
##  <a name="additional-information"></a><a name="bkmk_addiitonal_informaiton"></a><span data-ttu-id="a1d3e-183">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="a1d3e-183">Additional Information</span></span>  
 <span data-ttu-id="a1d3e-184">Uma etapa de configuração adicional e comum relacionada à administração do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] é abrir a porta 80 no Windows Firewall para permitir o acesso ao computador do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="a1d3e-184">An additional and common configuration step related to [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] administration is to open port 80 in Windows Firewall to allow access to the report server computer.</span></span> <span data-ttu-id="a1d3e-185">Para obter instruções, consulte [Configure a Firewall for Report Server Access](configure-a-firewall-for-report-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="a1d3e-185">For instructions, see [Configure a Firewall for Report Server Access](configure-a-firewall-for-report-server-access.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1d3e-186">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a1d3e-186">See Also</span></span>  
 [<span data-ttu-id="a1d3e-187">Gerenciar um servidor de relatórios de Modo Nativo do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a1d3e-187">Manage a Reporting Services Native Mode Report Server</span></span>](manage-a-reporting-services-native-mode-report-server.md)  
  
  
