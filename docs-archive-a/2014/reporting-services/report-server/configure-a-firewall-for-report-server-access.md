---
title: Configurar um firewall para acesso ao servidor de relatório | Microsoft Docs
ms.custom: ''
ms.date: 08/10/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- firewall systems [Reporting Services]
- configuring servers [Reporting Services]
ms.assetid: 04dae07a-a3a4-424c-9bcb-a8000e20dc93
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b578c980522d24f5a24a73fdfd080ec425335aac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575611"
---
# <a name="configure-a-firewall-for-report-server-access"></a><span data-ttu-id="fb8bc-102">Configure a Firewall for Report Server Access</span><span class="sxs-lookup"><span data-stu-id="fb8bc-102">Configure a Firewall for Report Server Access</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="fb8bc-103">Os aplicativos e os relatórios publicados do servidor de relatório são acessados por meio de URLs que especificam um endereço IP, uma porta e um diretório virtual.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-103">Report server applications and published reports are accessed through URLs that specify an IP address, port, and virtual directory.</span></span> <span data-ttu-id="fb8bc-104">Se o Firewall do Windows estiver ativado, a porta que o servidor de relatório está configurado para usar provavelmente estará fechada.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-104">If Windows Firewall is turned on, the port that the report server is configured to use is most likely closed.</span></span> <span data-ttu-id="fb8bc-105">As indicações de que uma porta pode estar fechada são o aparecimento de uma página da Web em branco depois de solicitar um relatório ou de uma página em branco quando você tentar abrir o Gerenciador de Relatórios a partir de um computador cliente remoto.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-105">Indications that a port might be closed are the appearance of a blank Web page after requesting a report, or a blank page when you attempt to open Report Manager from a remote client computer.</span></span>  
  
 <span data-ttu-id="fb8bc-106">Para abrir uma porta, você deve usar o utilitário Firewall do Windows no computador do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-106">To open a port, you must use the Windows Firewall utility on the report server computer.</span></span> <span data-ttu-id="fb8bc-107">O Reporting Services não abrirá portas para você; é necessário executar essa etapa manualmente.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-107">Reporting Services will not open ports for you; you must perform this step manually.</span></span>  
  
 <span data-ttu-id="fb8bc-108">Por padrão, o servidor de relatório escuta solicitações HTTP na porta 80.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-108">By default, the report server listens for HTTP requests on port 80.</span></span> <span data-ttu-id="fb8bc-109">Dessa forma, as instruções a seguir incluem etapas que especificam essa porta.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-109">As such, the following instructions include steps that specify that port.</span></span> <span data-ttu-id="fb8bc-110">Se você tiver configurado para que as URLs do servidor de relatório usem uma porta diferente, deverá especificar esse número de porta ao seguir as próximas instruções.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-110">If you configured the report server URLs to use a different port, you must specify that port number when following the instructions below.</span></span>  
  
 <span data-ttu-id="fb8bc-111">Se você estiver acessando bancos de dados relacionais do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em computadores externos ou se o banco de dados do servidor de relatório estiver em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] externa , você deve abrir as portas 1433 e 1434 no computador externo.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-111">If you are accessing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] relational databases on external computers, or if the report server database is on an external [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance, you must open port 1433 and 1434 on the external computer.</span></span> <span data-ttu-id="fb8bc-112">Para obter mais informações, veja [Configurar um Firewall do Windows para acesso ao Mecanismo de Banco de Dados](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb8bc-112">For more information, see [Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="fb8bc-113">Para obter mais informações sobre as configurações de firewall do Windows padrão e obter uma descrição das portas TCP que afetam o [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]e [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], consulte [Configurar o Firewall do Windows para permitir acesso ao SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md) em Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb8bc-113">For more information about the default Windows firewall settings, and a description of the TCP ports that affect the [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], see [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fb8bc-114">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="fb8bc-114">Prerequisites</span></span>  
 <span data-ttu-id="fb8bc-115">Essas instruções supõem que você já configurou a conta de serviço, criou o banco de dados do servidor de relatório e configurou URLs para o serviço Web Servidor de Relatórios e o Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-115">These instructions assume that you already configured the service account, created the report server database, and configured URLs for the Report Server Web service and Report Manager.</span></span> <span data-ttu-id="fb8bc-116">Para obter mais informações, consulte [Gerenciar um servidor de relatório de modo nativo do Reporting Services](manage-a-reporting-services-native-mode-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="fb8bc-116">For more information, see [Manage a Reporting Services Native Mode Report Server](manage-a-reporting-services-native-mode-report-server.md).</span></span>  
  
 <span data-ttu-id="fb8bc-117">Você também deve ter verificado se o servidor de relatório pode ser acessado por uma conexão local de navegador Web com a instância local do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-117">You should also have verified that the report server is accessible over a local Web browser connection to the local report server instance.</span></span> <span data-ttu-id="fb8bc-118">Essa etapa confirma que você tem uma instalação em funcionamento.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-118">This step establishes that you have a working installation.</span></span> <span data-ttu-id="fb8bc-119">Você deve verificar se a instalação está configurada corretamente antes de começar a abrir portas.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-119">You should verify that the installation is configured correctly before you begin opening ports.</span></span> <span data-ttu-id="fb8bc-120">Para concluir essa etapa no Windows Server, você também deve ter adicionado o site do servidor de relatório aos Sites Confiáveis.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-120">To complete this step on  Windows Server, you must have also added the report server site to Trusted Sites.</span></span> <span data-ttu-id="fb8bc-121">Para obter mais informações, consulte [Configurar um servidor de relatório no modo nativo para a Administração Local &#40;SSRS&#41;](configure-a-native-mode-report-server-for-local-administration-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="fb8bc-121">For more information, see [Configure a Native Mode Report Server for Local Administration &#40;SSRS&#41;](configure-a-native-mode-report-server-for-local-administration-ssrs.md).</span></span>  
  
## <a name="opening-ports-in-windows-firewall"></a><span data-ttu-id="fb8bc-122">Abrindo portas no Firewall do Windows</span><span class="sxs-lookup"><span data-stu-id="fb8bc-122">Opening Ports in Windows Firewall</span></span>  
 <span data-ttu-id="fb8bc-123">Há instruções separadas para versões diferentes do Firewall do Windows.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-123">There are separate instructions for different versions of Windows Firewall.</span></span>  
  
#### <a name="to-open-port-80-on-windows-7-windows-server-2008-r2-windows-server-2012-and-2012-r2"></a><span data-ttu-id="fb8bc-124">Para abrir a porta 80 no Windows 7, no Windows Server 2008 R2, no Windows Server 2012 e no 2012 R2</span><span class="sxs-lookup"><span data-stu-id="fb8bc-124">To open port 80 on Windows 7, Windows Server 2008 R2, Windows Server 2012 and 2012 R2</span></span>  
  
1.  <span data-ttu-id="fb8bc-125">No menu **Iniciar** , clique em **Painel de Controle**, em **Sistema e Segurança**e, em seguida, em **Firewall do Windows**.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-125">From the **Start** menu, click **Control Panel**, click **System and Security**, and then click **Windows Firewall**.</span></span> <span data-ttu-id="fb8bc-126">O Painel de controle não está configurado para a exibição 'Categoria', você precisa selecionar apenas a opção **Firewall do Windows.**</span><span class="sxs-lookup"><span data-stu-id="fb8bc-126">Control Panel is not configured for 'Category' view, you only need to select **Windows Firewall.**</span></span>  
  
2.  <span data-ttu-id="fb8bc-127">Clique em **Configurações Avançadas**.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-127">Click **Advanced Settings**.</span></span>  
  
3.  <span data-ttu-id="fb8bc-128">Clique em **Regras de entrada**.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-128">Click **Inbound Rules.**</span></span>  
  
4.  <span data-ttu-id="fb8bc-129">Clique em **Nova Regra** na janela **Ações\*\*\*\*.**</span><span class="sxs-lookup"><span data-stu-id="fb8bc-129">Click **New Rule** in the **Actions** window **.**</span></span>  
  
5.  <span data-ttu-id="fb8bc-130">Clique em **Tipo de Regra** de **porta.**</span><span class="sxs-lookup"><span data-stu-id="fb8bc-130">Click **Rule Type** of **Port.**</span></span>  
  
6.  <span data-ttu-id="fb8bc-131">Clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-131">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="fb8bc-132">Na página **Protocolos e Portas** , clique em **TCP**.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-132">On the **Protocol and Ports** page click **TCP**.</span></span>  
  
8.  <span data-ttu-id="fb8bc-133">Selecione **Portas Locais Específicas** e digite um valor de **80**.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-133">Select **Specific Local Ports** and type a value of **80**.</span></span>  
  
9. <span data-ttu-id="fb8bc-134">Clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-134">Click **Next**.</span></span>  
  
10. <span data-ttu-id="fb8bc-135">Na página **Ação** , clique em **Permitir a conexão**.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-135">On the **Action** page click **Allow the connection**.</span></span>  
  
11. <span data-ttu-id="fb8bc-136">Clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-136">Click **Next**.</span></span>  
  
12. <span data-ttu-id="fb8bc-137">Na página **Perfil** , clique nas opções adequadas para seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-137">On the **Profile** page click the appropriate options for your environment.</span></span>  
  
13. <span data-ttu-id="fb8bc-138">Clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-138">Click **Next**.</span></span>  
  
14. <span data-ttu-id="fb8bc-139">Na página **Nome** , digite o nome do**ReportServer (TCP na porta 80)**</span><span class="sxs-lookup"><span data-stu-id="fb8bc-139">On the **Name** page enter a name of**ReportServer (TCP on port 80)**</span></span>  
  
15. <span data-ttu-id="fb8bc-140">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-140">Click **Finish**.</span></span>  
  
16. <span data-ttu-id="fb8bc-141">Reinicie o computador.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-141">Restart the computer.</span></span>  
  
#### <a name="to-open-port-80-on-windows-vista-or-windows-server-2008"></a><span data-ttu-id="fb8bc-142">Para abrir a porta 80 no Windows Vista ou no Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="fb8bc-142">To open port 80 on Windows Vista or Windows Server 2008</span></span>  
  
1.  <span data-ttu-id="fb8bc-143">No menu **Iniciar** , clique em **painel de controle**, clique em **segurança**e, em seguida, clique em **Firewall do Windows**.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-143">From the **Start** menu, click **Control Panel**, click **Security**, and then click **Windows Firewall**.</span></span>  
  
2.  <span data-ttu-id="fb8bc-144">Clique em **Permitir um programa pelo Firewall do Windows**.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-144">Click **Allow a program through Windows Firewall**.</span></span>  
  
3.  <span data-ttu-id="fb8bc-145">Clique em **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-145">Click **Continue**.</span></span>  
  
4.  <span data-ttu-id="fb8bc-146">Na guia exceções, clique em **Adicionar porta**.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-146">On the Exceptions tab, click **Add Port**.</span></span>  
  
5.  <span data-ttu-id="fb8bc-147">Em nome, digite **ReportServer (TCP na porta 80)**.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-147">In Name, type **ReportServer (TCP on port 80)**.</span></span>  
  
6.  <span data-ttu-id="fb8bc-148">Em número da porta, digite **80**.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-148">In Port number, type **80**.</span></span>  
  
7.  <span data-ttu-id="fb8bc-149">Verifique se **TCP** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-149">Verify that **TCP** is selected.</span></span>  
  
8.  <span data-ttu-id="fb8bc-150">Clique em **alterar escopo**.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-150">Click **Change Scope**.</span></span>  
  
9. <span data-ttu-id="fb8bc-151">Clique em **minha rede (sub-rede) somente**e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-151">Click **My network (subnet) only**, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="fb8bc-152">Clique em **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-152">Click **OK** to close the dialog box.</span></span>  
  
11. <span data-ttu-id="fb8bc-153">Reinicie o computador.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-153">Restart the computer.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="fb8bc-154">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="fb8bc-154">Next Steps</span></span>  
 <span data-ttu-id="fb8bc-155">Depois de abrir a porta e antes de confirmar se usuários remotos podem acessar o servidor de relatório na porta que abriu, você deverá conceder acesso de usuário ao servidor de relatório por meio de atribuições de função em Base e no nível do site.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-155">After you open the port and before you confirm whether remote users can access the report server on the port that you open, you must grant user access to the report server through role assignments on Home and at the site level.</span></span> <span data-ttu-id="fb8bc-156">Você pode abrir uma porta corretamente e ainda ter falha de conexões do servidor de relatório se os usuários não tiverem permissões adequadas.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-156">You can open a port correctly and still have report server connections fail if users do not have sufficient permissions.</span></span> <span data-ttu-id="fb8bc-157">Para obter mais informações, consulte [Conceder acesso ao usuário a um servidor de relatório &#40;Gerenciador de Relatórios&#41;](../security/grant-user-access-to-a-report-server.md) nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb8bc-157">For more information, see [Grant User Access to a Report Server &#40;Report Manager&#41;](../security/grant-user-access-to-a-report-server.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="fb8bc-158">Você também pode verificar se a porta está aberta corretamente iniciando o Gerenciador de Relatórios em um computador diferente.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-158">You can also verify that the port is opened correctly by starting Report Manager on a different computer.</span></span> <span data-ttu-id="fb8bc-159">Para obter mais informações, consulte [Gerenciador de Relatórios &#40;modo nativo do SSRS&#41;](../report-manager-ssrs-native-mode.md) nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb8bc-159">For more information, see [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb8bc-160">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fb8bc-160">See Also</span></span>  
 <span data-ttu-id="fb8bc-161">[Configurar a conta de serviço do servidor de relatório &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="fb8bc-161">[Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="fb8bc-162">[Configurar as URLs do servidor de relatório &#40;SSRS Configuration Manager&#41;](../install-windows/configure-report-server-urls-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="fb8bc-162">[Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;](../install-windows/configure-report-server-urls-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="fb8bc-163">[Criar um banco de dados do servidor de relatório &#40;Configuration Manager SSRS&#41;](../../sql-server/install/create-a-report-server-database-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="fb8bc-163">[Create a Report Server Database  &#40;SSRS Configuration Manager&#41;](../../sql-server/install/create-a-report-server-database-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="fb8bc-164">[Configurar a conta de serviço do servidor de relatório &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="fb8bc-164">[Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span></span>  
 [<span data-ttu-id="fb8bc-165">Gerenciar um servidor de relatórios de Modo Nativo do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="fb8bc-165">Manage a Reporting Services Native Mode Report Server</span></span>](manage-a-reporting-services-native-mode-report-server.md)  
  
  
