---
title: Verificar uma instalação do Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- checking report server installations
- verifying report server installations
- Report Designer [Reporting Services], verifying installations
- installing Reporting Services, verifying installations
- Report Manager [Reporting Services], verifying installations
- report servers [Reporting Services], verifying installations
- Setup [Reporting Services], verifying installations
ms.assetid: 82a51a99-66f0-4b0c-b05b-07d22387adb0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5b90f997f99cfc9d3f8625eb4e08d193af52d7f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569188"
---
# <a name="verify-a-reporting-services-installation"></a><span data-ttu-id="c525d-102">Verificar uma instalação do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c525d-102">Verify a Reporting Services Installation</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="c525d-103">podem ser instalados em um de dois modos: Nativo ou SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c525d-103">report servers can be installed in one of two modes, Native or SharePoint.</span></span> <span data-ttu-id="c525d-104">As etapas que você deve seguir para verificar a instalação dependem do modo do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="c525d-104">The steps you should follow for verifying the installation depend on the report server mode.</span></span>  
  
 <span data-ttu-id="c525d-105">Este tópico inclui as informações a seguir:</span><span class="sxs-lookup"><span data-stu-id="c525d-105">This topic contains the following information:</span></span>  
  
-   [<span data-ttu-id="c525d-106">Verificar a instalação do modo do SharePoint</span><span class="sxs-lookup"><span data-stu-id="c525d-106">Verify SharePoint Mode Installation</span></span>](#bkmk_sharepointmode)  
  
-   [<span data-ttu-id="c525d-107">Verificar uma instalação no modo Nativo</span><span class="sxs-lookup"><span data-stu-id="c525d-107">Verify a Native Mode Installation</span></span>](#bkmk_nativemode)  
  
##  <a name="verify-sharepoint-mode-installation"></a><a name="bkmk_sharepointmode"></a> <span data-ttu-id="c525d-108">Verificar a instalação do modo do SharePoint</span><span class="sxs-lookup"><span data-stu-id="c525d-108">Verify SharePoint Mode Installation</span></span>  
  
#### <a name="to-verify-the-reporting-services-service"></a><span data-ttu-id="c525d-109">Para verificar o serviço Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c525d-109">To verify the Reporting Services Service</span></span>  
  
1.  <span data-ttu-id="c525d-110">Na Administração Central do SharePoint, clique em **Gerenciar serviços no servidor** no grupo **Configurações do Sistema** .</span><span class="sxs-lookup"><span data-stu-id="c525d-110">From SharePoint central administration, click **Manage services on server** in the **System Settings** group.</span></span>  
  
2.  <span data-ttu-id="c525d-111">Verifique se o **Serviço SQL Server Reporting Services** está instalado e no estado **Executando** .</span><span class="sxs-lookup"><span data-stu-id="c525d-111">Verify the **SQL Server Reporting Services Service** is installed and in the **Running** state.</span></span>  
  
     <span data-ttu-id="c525d-112">Se você não vir o serviço do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] na lista, verifique se o serviço está instalado.</span><span class="sxs-lookup"><span data-stu-id="c525d-112">If you do not see the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service in the list, verify the service is installed.</span></span> <span data-ttu-id="c525d-113">Para obter mais informações, consulte a seção "instalar e iniciar o Reporting Services o serviço do SharePoint" [em instalar Reporting Services modo do SharePoint para sharepoint 2010](../../sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2010.md).</span><span class="sxs-lookup"><span data-stu-id="c525d-113">For more information, see the "Install and start the Reporting Services SharePoint Service" section of [Install Reporting Services SharePoint Mode for SharePoint 2010](../../sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2010.md).</span></span>  
  
#### <a name="to-verify-the-service-application"></a><span data-ttu-id="c525d-114">Para verificar o aplicativo de serviço</span><span class="sxs-lookup"><span data-stu-id="c525d-114">To verify the Service Application</span></span>  
  
1.  <span data-ttu-id="c525d-115">Para verificar na Administração Central que você tem pelo menos um aplicativo de serviço do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , clique em **Gerenciar Aplicativos de Serviço** no grupo **Gerenciamento de Aplicativo** .</span><span class="sxs-lookup"><span data-stu-id="c525d-115">To verify from Central Administration you have at least one [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application, click **Manage Service Applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="c525d-116">Verifique se há um aplicativo de serviço do tipo **Aplicativo de Serviço SQL Server Reporting Services** e um proxy de aplicativo correspondente.</span><span class="sxs-lookup"><span data-stu-id="c525d-116">Verify there is a service application of type **SQL Server Reporting Services Service Application** and a corresponding application proxy.</span></span>  
  
3.  <span data-ttu-id="c525d-117">Clique **próximo** ao nome do aplicativo de serviço e clique em **Propriedades** na barra de ferramentas do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c525d-117">Click **near** the name of the service application and then click **Properties** in the SharePoint toolbar.</span></span>  <span data-ttu-id="c525d-118">Se você clicar no nome do aplicativo de serviço, serão abertas as páginas de Gerenciamento do aplicativo de serviço, não na página de propriedades.</span><span class="sxs-lookup"><span data-stu-id="c525d-118">If you click the name of the service application it will open the Management pages of the service application, not the properties page.</span></span>  
  
4.  <span data-ttu-id="c525d-119">Verifique se a **Associação de Aplicativo Web** está configurada para apontar para o aplicativo Web desejado.</span><span class="sxs-lookup"><span data-stu-id="c525d-119">Verify the **Web Application Association** is configured to point to the desired web application.</span></span>  
  
#### <a name="to-verify-the-site-collection-feature"></a><span data-ttu-id="c525d-120">Para verificar os Recursos da Coleção de Sites</span><span class="sxs-lookup"><span data-stu-id="c525d-120">To verify the Site collection Feature</span></span>  
  
1.  <span data-ttu-id="c525d-121">Nas configurações do site, clique em **Recursos da Coleção de Sites** no grupo **Administração da Coleção de Sites** .</span><span class="sxs-lookup"><span data-stu-id="c525d-121">In site settings, click **Site collection Features** in the **Site Collection Administration** group.</span></span>  
  
2.  <span data-ttu-id="c525d-122">Verifique se o **Recurso de Integração do Servidor de Relatório** está ativo.</span><span class="sxs-lookup"><span data-stu-id="c525d-122">Verify the **Report Server Integration Feature** is active.</span></span>  
  
#### <a name="to-verify-reporting-server-content-types"></a><span data-ttu-id="c525d-123">Para verificar tipos de conteúdo do servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="c525d-123">To Verify Reporting Server content types</span></span>  
  
1.  <span data-ttu-id="c525d-124">Para verificar ou adicionar [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] tipos de conteúdo do servidor de relatório, consulte [adicionar tipos de conteúdo do servidor de relatório a uma biblioteca &#40;Reporting Services no modo integrado do SharePoint&#41;](../add-reporting-services-content-types-to-a-sharepoint-library.md).</span><span class="sxs-lookup"><span data-stu-id="c525d-124">To verify or add [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report server content types, see [Add Report Server Content Types to a Library &#40;Reporting Services in SharePoint Integrated Mode&#41;](../add-reporting-services-content-types-to-a-sharepoint-library.md).</span></span>  
  
#### <a name="to-verify-you-can-launch-report-builder"></a><span data-ttu-id="c525d-125">Para verificar se você pode iniciar o Construtor de Relatórios</span><span class="sxs-lookup"><span data-stu-id="c525d-125">To verify you can launch Report Builder</span></span>  
  
1.  <span data-ttu-id="c525d-126">Na biblioteca de documentos, clique em **Documentos** na faixa de opções do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c525d-126">From a document library, click **Documents** in the SharePoint ribbon.</span></span>  
  
2.  <span data-ttu-id="c525d-127">Clique em **Novo Documento** e clique em **Relatório do Construtor de Relatórios**.</span><span class="sxs-lookup"><span data-stu-id="c525d-127">Click **New Document** and click **Report Builder Report**.</span></span> <span data-ttu-id="c525d-128">Se você não vir essa opção, examine o procedimento anterior sobre como adicionar os tipos de conteúdo do servidor de relatório a uma biblioteca.</span><span class="sxs-lookup"><span data-stu-id="c525d-128">If you do not see this option, review the previous procedure on adding the report server content types to a library.</span></span>  
  
#### <a name="create-a-basic-report"></a><span data-ttu-id="c525d-129">Criar um relatório básico</span><span class="sxs-lookup"><span data-stu-id="c525d-129">Create a basic report</span></span>  
  
1.  <span data-ttu-id="c525d-130">Em uma biblioteca de documentos do SharePoint, crie um relatório básico do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que contém somente uma caixa de texto, por exemplo, um título.</span><span class="sxs-lookup"><span data-stu-id="c525d-130">In a SharePoint document library, create a basic [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report that only contains a text box, for example a title.</span></span> <span data-ttu-id="c525d-131">O relatório não contém fonte de dados ou conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="c525d-131">The report does not contain any data sources or datasets.</span></span> <span data-ttu-id="c525d-132">A meta é verificar se você pode abrir o Construtor de Relatórios e um relatório básico será visualizado.</span><span class="sxs-lookup"><span data-stu-id="c525d-132">The goal is to verify you can open Report Builder and a basic report will preview.</span></span>  
  
2.  <span data-ttu-id="c525d-133">Salve o relatório em uma biblioteca de documentos e execute o relatório da biblioteca.</span><span class="sxs-lookup"><span data-stu-id="c525d-133">Save the report to the document library and the run the report from the library.</span></span> <span data-ttu-id="c525d-134">Para obter mais informações sobre como criar relatórios com o Construtor de Relatórios, veja [Iniciar o Construtor de Relatórios (Construtor de Relatórios)](https://technet.microsoft.com/library/ms159221.aspx).</span><span class="sxs-lookup"><span data-stu-id="c525d-134">For more information on creating reports with Report Builder, see [Start Report Builder (Report Builder)](https://technet.microsoft.com/library/ms159221.aspx).</span></span>  
  
#### <a name="reporting-services-samples"></a><span data-ttu-id="c525d-135">Exemplos do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c525d-135">Reporting Services samples</span></span>  
  
1.  <span data-ttu-id="c525d-136">Concluir um dos tutoriais do Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="c525d-136">Complete one of the Reporting Services tutorials.</span></span> <span data-ttu-id="c525d-137">Para obter mais informações, consulte [Tutoriais do Reporting Services &#40;SSRS&#41;](../reporting-services-tutorials-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c525d-137">For more information, see [Reporting Services Tutorials &#40;SSRS&#41;](../reporting-services-tutorials-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="c525d-138">Baixe o banco de dados de exemplo do Adventure Works e os relatórios de exemplo do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] do CodePlex.</span><span class="sxs-lookup"><span data-stu-id="c525d-138">Download the Adventure works sample database and the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] sample reports from CodePlex.</span></span> <span data-ttu-id="c525d-139">Para obter mais informações, consulte os [Exemplos de relatórios do AdventureWorks](https://msftrsprodsamples.codeplex.com/wikipage?title=SS2012!AdventureWorks2012%20Report%20Samples&referringTitle=Home).</span><span class="sxs-lookup"><span data-stu-id="c525d-139">For more information, see [AdventureWorks Report Samples](https://msftrsprodsamples.codeplex.com/wikipage?title=SS2012!AdventureWorks2012%20Report%20Samples&referringTitle=Home).</span></span>  
  
##  <a name="verify-a-native-mode-installation"></a><a name="bkmk_nativemode"></a><span data-ttu-id="c525d-140">Verificar uma instalação do modo nativo</span><span class="sxs-lookup"><span data-stu-id="c525d-140">Verify a Native Mode Installation</span></span>  
 <span data-ttu-id="c525d-141">Quando você instala um servidor de relatório do modo Nativo usando a configuração padrão, a Instalação instala e implanta o servidor.</span><span class="sxs-lookup"><span data-stu-id="c525d-141">When you install a Native mode report server using the default configuration, Setup installs and deploys the server.</span></span> <span data-ttu-id="c525d-142">Você pode verificar se a Instalação implantou o servidor de relatório executando alguns testes simples.</span><span class="sxs-lookup"><span data-stu-id="c525d-142">You can verify whether Setup deployed the report server by performing a few simple tests.</span></span> <span data-ttu-id="c525d-143">Você deve ser um administrador local para executar essas etapas.</span><span class="sxs-lookup"><span data-stu-id="c525d-143">You must be a local administrator to perform these steps.</span></span> <span data-ttu-id="c525d-144">Para permitir que outros usuários executem o teste, você deve configurar o acesso ao servidor de relatório para tais usuários.</span><span class="sxs-lookup"><span data-stu-id="c525d-144">To enable other users to perform testing, you must configure report server access for those users.</span></span>  
  
#### <a name="to-verify-that-the-report-server-is-installed-and-running"></a><span data-ttu-id="c525d-145">Para verificar se o servidor de relatório está instalado e em execução</span><span class="sxs-lookup"><span data-stu-id="c525d-145">To verify that the report server is installed and running</span></span>  
  
1.  <span data-ttu-id="c525d-146">Execute a ferramenta Configuração do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e se conecte à instância do servidor de relatório recém-instalada.</span><span class="sxs-lookup"><span data-stu-id="c525d-146">Run the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool and connect to the report server instance you just installed.</span></span> <span data-ttu-id="c525d-147">A página URL do Serviço Web inclui um link para o serviço Web Servidor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="c525d-147">The Web Service URL page includes a link to the Report Server Web service.</span></span> <span data-ttu-id="c525d-148">Clique no link para verificar se você pode acessar o servidor.</span><span class="sxs-lookup"><span data-stu-id="c525d-148">Click the link to verify you can access the server.</span></span> <span data-ttu-id="c525d-149">Se o banco de dados do servidor de relatório não estiver configurado, faça isso primeiro antes de clicar no link.</span><span class="sxs-lookup"><span data-stu-id="c525d-149">If the report server database is not configured, do that first before clicking the link.</span></span>  
  
2.  <span data-ttu-id="c525d-150">Abra os aplicativos do console Serviços e verifique se o serviço Servidor de Relatório está em execução.</span><span class="sxs-lookup"><span data-stu-id="c525d-150">Open the Services console applications and verify that the Report Server service is running.</span></span> <span data-ttu-id="c525d-151">Para exibir o status do serviço Servidor de Relatório, clique em **Iniciar**, aponte para **Painel de Controle**, clique duas vezes em **Ferramentas Administrativas**e clique duas vezes em **Serviços**.</span><span class="sxs-lookup"><span data-stu-id="c525d-151">To view the status of the Report Server service, click **Start**, point to **Control Panel**, double-click **Administrative Tools**, and then double-click **Services**.</span></span> <span data-ttu-id="c525d-152">Quando a lista de serviços for exibida, role até **Servidor de Relatório (MSSQLSERVER)**.</span><span class="sxs-lookup"><span data-stu-id="c525d-152">When the list of services appears, scroll to **Report Server (MSSQLSERVER)**.</span></span> <span data-ttu-id="c525d-153">O status deve ser **Iniciado**.</span><span class="sxs-lookup"><span data-stu-id="c525d-153">The status should be **Started**.</span></span>  
  
3.  <span data-ttu-id="c525d-154">Abra um navegador e digite a URL do servidor de relatório na barra de endereço.</span><span class="sxs-lookup"><span data-stu-id="c525d-154">Open a browser and type the report server URL in the address bar.</span></span> <span data-ttu-id="c525d-155">O endereço consiste no nome do servidor e no nome do diretório virtual especificados para o servidor de relatório durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="c525d-155">The address consists of the server name and the virtual directory name that you specified for the report server during setup.</span></span> <span data-ttu-id="c525d-156">Por padrão, o diretório virtual do servidor de relatório é denominado **ReportServer**.</span><span class="sxs-lookup"><span data-stu-id="c525d-156">By default, the report server virtual directory is named **ReportServer**.</span></span> <span data-ttu-id="c525d-157">Você pode usar a seguinte URL para verificar a instalação do servidor de relatório: http:// *\<computer name>* /reportserver *\<_instance name>* .</span><span class="sxs-lookup"><span data-stu-id="c525d-157">You can use the following URL to verify report server installation: http://*\<computer name>*/ReportServer*\<_instance name>*.</span></span> <span data-ttu-id="c525d-158">A URL será diferente se você tiver instalado o servidor de relatório como uma instância nomeada.</span><span class="sxs-lookup"><span data-stu-id="c525d-158">The URL will be different if you installed the report server as a named instance.</span></span> <span data-ttu-id="c525d-159">Para obter mais informações sobre o formato de URL, consulte [Configurar as URLs do servidor de relatório &#40;Gerenciador de Configurações do SSRS&#41;](configure-report-server-urls-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="c525d-159">For more information about the URL format, see [Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;](configure-report-server-urls-ssrs-configuration-manager.md).</span></span> <span data-ttu-id="c525d-160">Se você é um administrador local no Windows Vista ou no Windows Server 2008, consulte [Configurar um servidor de relatório no modo nativo para a Administração Local &#40;SSRS&#41;](../report-server/configure-a-native-mode-report-server-for-local-administration-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c525d-160">If you are a local administrator on Windows Vista or Windows Server 2008, see [Configure a Native Mode Report Server for Local Administration &#40;SSRS&#41;](../report-server/configure-a-native-mode-report-server-for-local-administration-ssrs.md).</span></span>  
  
4.  <span data-ttu-id="c525d-161">Execute relatórios para testar as operações do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="c525d-161">Run reports to test report server operations.</span></span> <span data-ttu-id="c525d-162">Para esta etapa, você pode criar um relatório de exemplo de um tutorial.</span><span class="sxs-lookup"><span data-stu-id="c525d-162">For this step, you can create a sample report from a tutorial.</span></span> <span data-ttu-id="c525d-163">Para obter mais informações, consulte [Criar um relatório de tabela básico &#40;Tutorial do SSRS&#41;](../create-a-basic-table-report-ssrs-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="c525d-163">For more information, see [Create a Basic Table Report &#40;SSRS Tutorial&#41;](../create-a-basic-table-report-ssrs-tutorial.md).</span></span>  
  
#### <a name="to-verify-that-report-manager-is-installed-and-running"></a><span data-ttu-id="c525d-164">Para verificar se o Gerenciador de Relatórios está instalado e em execução</span><span class="sxs-lookup"><span data-stu-id="c525d-164">To verify that Report Manager is installed and running</span></span>  
  
1.  <span data-ttu-id="c525d-165">Abra um navegador e digite a URL do Gerenciador de Relatórios na barra de endereço.</span><span class="sxs-lookup"><span data-stu-id="c525d-165">Open a browser and type the Report Manager URL in the address bar.</span></span> <span data-ttu-id="c525d-166">O endereço consiste no nome do servidor e no nome do diretório virtual especificados para o Gerenciador de Relatórios durante a instalação ou na página URL do Gerenciador de Relatórios da ferramenta Configuração do Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="c525d-166">The address consists of the server name and the virtual directory name that you specified for the Report Manager during setup or in the Report Manager URL page in the Reporting Services Configuration tool.</span></span> <span data-ttu-id="c525d-167">Por padrão, o diretório virtual do Gerenciador de Relatórios é **Reports**.</span><span class="sxs-lookup"><span data-stu-id="c525d-167">By default, the Report Manager virtual directory is **Reports**.</span></span> <span data-ttu-id="c525d-168">Você pode usar a seguinte URL para verificar a instalação do Gerenciador de Relatórios:</span><span class="sxs-lookup"><span data-stu-id="c525d-168">You can use the following URL to verify Report Manager installation:</span></span>  
  
     <span data-ttu-id="c525d-169">http:// *\<computer name>* /reports *\<_instance name>* .</span><span class="sxs-lookup"><span data-stu-id="c525d-169">http://*\<computer name>*/Reports*\<_instance name>*.</span></span>  
  
2.  <span data-ttu-id="c525d-170">Use o Gerenciador de Relatórios para criar uma nova pasta ou carregar um arquivo a fim de testar se as condições são devolvidas para o banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="c525d-170">Use Report Manager to create a new folder or upload a file to test whether definitions are passed back to the report server database.</span></span> <span data-ttu-id="c525d-171">Se essas operações obtiverem êxito, a conexão estará funcional.</span><span class="sxs-lookup"><span data-stu-id="c525d-171">If these operations are successful, the connection is functional.</span></span>  
  
     <span data-ttu-id="c525d-172">Para obter mais informações, consulte [Gerenciador de Relatórios &#40;modo nativo do SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="c525d-172">For more information, see [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
#### <a name="to-verify-that-report-designer-is-installed-and-running"></a><span data-ttu-id="c525d-173">Para verificar se o Designer de Relatórios está instalado e em execução</span><span class="sxs-lookup"><span data-stu-id="c525d-173">To verify that Report Designer is installed and running</span></span>  
  
1.  <span data-ttu-id="c525d-174">Abra o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]e crie um novo projeto com base em um tipo de projeto do Servidor de Relatório.</span><span class="sxs-lookup"><span data-stu-id="c525d-174">Open [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], and create a new project based on a Report Server project type.</span></span> <span data-ttu-id="c525d-175">Para obter mais informações sobre como usar o Assistente de Projeto do Servidor de Relatório, consulte [Reporting Services no SSDT &#40;SQL Server Data Tools&#41;](../tools/reporting-services-in-sql-server-data-tools-ssdt.md) nos Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c525d-175">For more information on using the Report Server Project Wizard, see [Reporting Services in SQL Server Data Tools &#40;SSDT&#41;](../tools/reporting-services-in-sql-server-data-tools-ssdt.md) in SQL Server Books Online.</span></span>  
  
2.  <span data-ttu-id="c525d-176">Se você tiver instalado exemplos de relatório, precisará abrir os arquivos de projeto do relatório de exemplo e publicar os relatórios em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="c525d-176">If you installed report samples, open the sample report project files and publish the reports to a report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c525d-177">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c525d-177">See Also</span></span>  
 <span data-ttu-id="c525d-178">[Solucionar problemas de instalação de Reporting Services](troubleshoot-a-reporting-services-installation.md) </span><span class="sxs-lookup"><span data-stu-id="c525d-178">[Troubleshoot a Reporting Services Installation](troubleshoot-a-reporting-services-installation.md) </span></span>  
 [<span data-ttu-id="c525d-179">Causa e resolução de erros do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c525d-179">Cause and Resolution of Reporting Services Errors</span></span>](../troubleshooting/cause-and-resolution-of-reporting-services-errors.md)  
  
  