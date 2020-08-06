---
title: Instalar a versão autônoma do Construtor de Relatórios (Construtor de Relatórios) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6b2291bb-1d20-4d08-81cb-a16dd8e01faf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2ba8c132125f56ad833a71a1c82221e2bf28d13e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575634"
---
# <a name="install-the-stand-alone-version-of-report-builder-report-builder"></a><span data-ttu-id="9cecf-102">Instalar a versão autônoma do Construtor de Relatórios (Construtor de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="9cecf-102">Install the Stand-Alone Version of Report Builder (Report Builder)</span></span>
  <span data-ttu-id="9cecf-103">Você pode instalar o Construtor de Relatórios do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Feature Pack no [centro de download da Microsoft](https://www.microsoft.com/download/details.aspx?id=53613) ou em um local como a pasta pública na qual o ReportBuilder3_x86.msi, o pacote de Windows Installer para Construtor de relatórios, foi baixado.</span><span class="sxs-lookup"><span data-stu-id="9cecf-103">You can install Report Builder from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] feature pack on the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53613) or a location such as public folder to which the ReportBuilder3_x86.msi, the Windows Installer Package for Report Builder, has been downloaded.</span></span>  
  
 <span data-ttu-id="9cecf-104">Também é possível executar uma instalação de linha de comando do Construtor de Relatórios e fornecer argumentos para personalizar a instalação.</span><span class="sxs-lookup"><span data-stu-id="9cecf-104">You can also perform a command line installation of Report Builder and provide arguments to customize the installation.</span></span> <span data-ttu-id="9cecf-105">Além dos parâmetros intrínsecos ao MSI padrão, você pode usar os parâmetros personalizados fornecidos pelo Construtor de Relatórios: RBINSTALLDIR e REPORTSERVERURL.</span><span class="sxs-lookup"><span data-stu-id="9cecf-105">In addition to the standard MSI intrinsic parameters, you can use the custom parameters that Report Builder provides: RBINSTALLDIR and REPORTSERVERURL.</span></span> <span data-ttu-id="9cecf-106">RBINSTALLDIR especifica a pasta de instalação raiz para o Construtor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="9cecf-106">RBINSTALLDIR specifies the root installation folder for Report Builder.</span></span> <span data-ttu-id="9cecf-107">REPORTSERVERURL especifica o servidor de relatório padrão que o Construtor de Relatórios usa para salvar relatórios no servidor.</span><span class="sxs-lookup"><span data-stu-id="9cecf-107">REPORTSERVERURL specifies the default report server that Report Builder uses to save reports on the server.</span></span>  
  
 <span data-ttu-id="9cecf-108">Se você quiser uma instalação completamente silenciosa, sem nenhuma interação com a interface do usuário, especifique a opção **/quiet** .</span><span class="sxs-lookup"><span data-stu-id="9cecf-108">If you want a completely silent installation, with no user interface interaction at all, specify the **/quiet** option.</span></span> <span data-ttu-id="9cecf-109">Por padrão, o sinalizador de opção silenciosa suprime erros de instalação.</span><span class="sxs-lookup"><span data-stu-id="9cecf-109">By design, the quiet option flag suppresses installation errors.</span></span> <span data-ttu-id="9cecf-110">Portanto, é recomendável incluir a opção **/l** que especifica o registro, quando você usar a opção silenciosa.</span><span class="sxs-lookup"><span data-stu-id="9cecf-110">It is therefore recommended that you include the **/l** option, which specifies logging, when you use the quiet option.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9cecf-111">Os recursos de segurança do Windows Vista e do Windows 7 exigem permissões elevadas para executar operações de linha de comando e solicitarão permissão para executar a linha de comando.</span><span class="sxs-lookup"><span data-stu-id="9cecf-111">Windows Vista and Windows 7 security features require elevated permissions to run command line operations and will prompt for permission to run the command line.</span></span> <span data-ttu-id="9cecf-112">A instalação não é silenciosa.</span><span class="sxs-lookup"><span data-stu-id="9cecf-112">The installation is not silent.</span></span> <span data-ttu-id="9cecf-113">Para fazer a instalação silenciosa, é necessário executar a linha de comando como um administrador.</span><span class="sxs-lookup"><span data-stu-id="9cecf-113">To make the installation silent, you need to run the command line as an administrator.</span></span>  
  
### <a name="to-install-report-builder-from-the-download-site"></a><span data-ttu-id="9cecf-114">Para instalar o Construtor de Relatórios no site de download</span><span class="sxs-lookup"><span data-stu-id="9cecf-114">To install Report Builder from the download site</span></span>  
  
1.  <span data-ttu-id="9cecf-115">Vá para [Microsoft SQL Server 2012 Construtor de relatórios](https://go.microsoft.com/fwlink/?LinkID=219138) e localize a seção Construtor de relatórios da página da Web.</span><span class="sxs-lookup"><span data-stu-id="9cecf-115">Go to [Microsoft SQL Server 2012 Report Builder](https://go.microsoft.com/fwlink/?LinkID=219138) and locate the Report Builder section of the Web page.</span></span>  
  
2.  <span data-ttu-id="9cecf-116">Clique em **pacote x86**.</span><span class="sxs-lookup"><span data-stu-id="9cecf-116">Click **X86 Package**.</span></span>  
  
3.  <span data-ttu-id="9cecf-117">Na caixa de diálogo **download de arquivo** , clique em **executar**.</span><span class="sxs-lookup"><span data-stu-id="9cecf-117">In the **File Download** dialog box, click **Run**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="9cecf-118">Baixe apenas arquivos de origens confiáveis.</span><span class="sxs-lookup"><span data-stu-id="9cecf-118">Download only files from trusted sources.</span></span>  
  
4.  <span data-ttu-id="9cecf-119">Na caixa de diálogo Internet Explorer, clique em **executar**.</span><span class="sxs-lookup"><span data-stu-id="9cecf-119">In the Internet Explorer dialog box, click **Run**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="9cecf-120">Execute apenas arquivos de origens confiáveis.</span><span class="sxs-lookup"><span data-stu-id="9cecf-120">Run only files from trusted sources.</span></span>  
  
5.  <span data-ttu-id="9cecf-121">O Assistente do Construtor de Relatórios do Microsoft SQL Server é iniciado.</span><span class="sxs-lookup"><span data-stu-id="9cecf-121">The Microsoft SQL Server Report Builder Wizard is launched.</span></span>  
  
6.  <span data-ttu-id="9cecf-122">Na página **Bem-vindo ao assistente de instalação** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9cecf-122">On the **Welcome to the Installation Wizard** page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="9cecf-123">Na página **contrato de licença** , leia o contrato e, em seguida, selecione a opção **eu aceito os termos do contrato de licença** .</span><span class="sxs-lookup"><span data-stu-id="9cecf-123">On the **License Agreement** page, read the agreement and then select the **I accept the terms in the license agreement** option.</span></span> <span data-ttu-id="9cecf-124">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9cecf-124">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="9cecf-125">Forneça seu nome e o nome da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="9cecf-125">Provide your personal name and company name.</span></span> <span data-ttu-id="9cecf-126">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9cecf-126">Click **Next**.</span></span>  
  
9. <span data-ttu-id="9cecf-127">Na página **seleção de recursos** , opcionalmente, clique em **procurar** ou em **custo de disco**.</span><span class="sxs-lookup"><span data-stu-id="9cecf-127">On the **Feature Selection** page, optionally click **Browse** or **Disk Cost**.</span></span> <span data-ttu-id="9cecf-128">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9cecf-128">Click **Next**.</span></span>  
  
    -   <span data-ttu-id="9cecf-129">Clique em **procurar** para ver o local padrão de construtor de relatórios e atualizá-lo.</span><span class="sxs-lookup"><span data-stu-id="9cecf-129">Click **Browse** to see the default location of Report Builder and update it.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="9cecf-130">A pasta de instalação padrão para Construtor de Relatórios é a \<drive> programas\microsoft SQL Server do programa.</span><span class="sxs-lookup"><span data-stu-id="9cecf-130">The default installation folder for Report Builder is \<drive>Program Files\Microsoft SQL Server.</span></span>  
  
    -   <span data-ttu-id="9cecf-131">Clique em **custo do disco** para saber a quantidade de espaço em disco que o construtor de relatórios consome.</span><span class="sxs-lookup"><span data-stu-id="9cecf-131">Click **Disk Cost** to learn how much disk space Report Builder consumes.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="9cecf-132">Se um volume não tiver a quantidade suficiente de espaço livre em disco, esse volume será realçado.</span><span class="sxs-lookup"><span data-stu-id="9cecf-132">If a volume does not have sufficient amount of free disk space, the volume is highlighted.</span></span>  
  
10. <span data-ttu-id="9cecf-133">Na página **Servidor de Destino Padrão** , se desejar, forneça a URL ao servidor de relatório de destino se for diferente do padrão.</span><span class="sxs-lookup"><span data-stu-id="9cecf-133">On the **Default Target Server** page, optionally provide the URL to the target report server if it is different from the default.</span></span> <span data-ttu-id="9cecf-134">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9cecf-134">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9cecf-135">Se você planejar trabalhar com o Construtor de Relatórios quando estiver conectado a um servidor de relatório, será conveniente fornecer a URL ao servidor nesse momento.</span><span class="sxs-lookup"><span data-stu-id="9cecf-135">If you plan to work with Report Builder when it is connected to a report server, it is convenient to provide the URL to the server at this time.</span></span> <span data-ttu-id="9cecf-136">No entanto, você também pode fazer isso na caixa de diálogo **Opções** quando estiver trabalhando no construtor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="9cecf-136">However, you can also do this from the **Options** dialog box when you are working in Report Builder.</span></span>  
  
11. <span data-ttu-id="9cecf-137">Clique em **instalar** para concluir a instalação do construtor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="9cecf-137">Click **Install** to complete the installation of Report Builder.</span></span>  
  
### <a name="to-install-report-builder-from-a-share"></a><span data-ttu-id="9cecf-138">Para instalar o Construtor de Relatórios de um compartilhamento</span><span class="sxs-lookup"><span data-stu-id="9cecf-138">To install Report Builder from a share</span></span>  
  
1.  <span data-ttu-id="9cecf-139">Contate o administrador para saber a localização do arquivo ReportBuilder3_x86.msi que é executado para instalar o Construtor de Relatórios no computador local.</span><span class="sxs-lookup"><span data-stu-id="9cecf-139">Contact your administrator for the location of ReportBuilder3_x86.msi.msi that you run to install Report Builder on your local computer.</span></span>  
  
2.  <span data-ttu-id="9cecf-140">Localize o arquivo ReportBuilder3_x86.msi, o MSI (Windows Installer Package) do Construtor de Relatórios, e clique nele.</span><span class="sxs-lookup"><span data-stu-id="9cecf-140">Browse to locate the ReportBuilder3_x86.msi.msi, the Windows Installer Package (MSI) for Report Builder, and click it.</span></span>  
  
     <span data-ttu-id="9cecf-141">O Assistente do Construtor de Relatórios do Microsoft SQL Server é iniciado.</span><span class="sxs-lookup"><span data-stu-id="9cecf-141">The Microsoft SQL Server Report Builder Wizard is launched.</span></span>  
  
3.  <span data-ttu-id="9cecf-142">Na página **Bem-vindo ao assistente de instalação** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9cecf-142">On the **Welcome to the Installation Wizard** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="9cecf-143">Na página **contrato de licença** , leia o contrato e, em seguida, selecione a opção **eu aceito os termos do contrato de licença** .</span><span class="sxs-lookup"><span data-stu-id="9cecf-143">On the **License Agreement** page, read the agreement and then select the **I accept the terms in the license agreement** option.</span></span> <span data-ttu-id="9cecf-144">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9cecf-144">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="9cecf-145">Forneça seu nome e o nome da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="9cecf-145">Provide your personal name and company name.</span></span> <span data-ttu-id="9cecf-146">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9cecf-146">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="9cecf-147">Na página **seleção de recursos** , opcionalmente, clique em **procurar** ou em **custo de disco**.</span><span class="sxs-lookup"><span data-stu-id="9cecf-147">On the **Feature Selection** page, optionally click **Browse** or **Disk Cost**.</span></span> <span data-ttu-id="9cecf-148">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9cecf-148">Click **Next**.</span></span>  
  
    -   <span data-ttu-id="9cecf-149">Clique em **procurar** para ver o local padrão de construtor de relatórios e atualizá-lo.</span><span class="sxs-lookup"><span data-stu-id="9cecf-149">Click **Browse** to see the default location of Report Builder and update it.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="9cecf-150">A pasta de instalação padrão para Construtor de Relatórios é a \<drive> programas\microsoft SQL Server do programa.</span><span class="sxs-lookup"><span data-stu-id="9cecf-150">The default installation folder for Report Builder is \<drive>Program Files\Microsoft SQL Server.</span></span>  
  
    -   <span data-ttu-id="9cecf-151">Clique em **custo do disco** para saber a quantidade de espaço em disco que o construtor de relatórios consome.</span><span class="sxs-lookup"><span data-stu-id="9cecf-151">Click **Disk Cost** to learn how much disk space Report Builder consumes.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="9cecf-152">Se um volume não tiver a quantidade suficiente de espaço livre em disco, esse volume será realçado.</span><span class="sxs-lookup"><span data-stu-id="9cecf-152">If a volume does not have sufficient amount of free disk space, the volume is highlighted.</span></span>  
  
7.  <span data-ttu-id="9cecf-153">Na página **Servidor de Destino Padrão** , se desejar, forneça a URL ao servidor de relatório de destino se for diferente do padrão.</span><span class="sxs-lookup"><span data-stu-id="9cecf-153">On the **Default Target Server** page, optionally provide the URL to the target report server if it is different from the default.</span></span> <span data-ttu-id="9cecf-154">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9cecf-154">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9cecf-155">Se você planejar trabalhar com o Construtor de Relatórios quando estiver conectado a um servidor de relatório, será conveniente fornecer a URL ao servidor nesse momento.</span><span class="sxs-lookup"><span data-stu-id="9cecf-155">If you plan to work with Report Builder when it is connected to a report server, it is convenient to provide the URL to the server at this time.</span></span> <span data-ttu-id="9cecf-156">No entanto, você também pode fazer isso na caixa de diálogo **Opções** quando estiver trabalhando no construtor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="9cecf-156">However, you can also do this from the **Options** dialog box when you are working in Report Builder.</span></span>  
  
8.  <span data-ttu-id="9cecf-157">Clique em **instalar** para concluir a instalação do construtor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="9cecf-157">Click **Install** to complete the installation of Report Builder.</span></span>  
  
### <a name="to-install-report-builder-from-the-command-line"></a><span data-ttu-id="9cecf-158">Para instalar o Construtor de Relatórios na linha de comando</span><span class="sxs-lookup"><span data-stu-id="9cecf-158">To install Report Builder from the command line</span></span>  
  
1.  <span data-ttu-id="9cecf-159">Vá para [Microsoft SQL Server 2012 Construtor de relatórios](https://go.microsoft.com/fwlink/?LinkID=219138) e localize a seção Construtor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="9cecf-159">Go to [Microsoft SQL Server 2012 Report Builder](https://go.microsoft.com/fwlink/?LinkID=219138) and locate the Report Builder section.</span></span>  
  
2.  <span data-ttu-id="9cecf-160">Clique em **pacote x86**.</span><span class="sxs-lookup"><span data-stu-id="9cecf-160">Click **X86 Package**.</span></span>  
  
3.  <span data-ttu-id="9cecf-161">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="9cecf-161">Click Save.</span></span>  
  
4.  <span data-ttu-id="9cecf-162">Opcionalmente, navegue até o local para salvar, verifique se a opção **salvar como** está **Windows Installer pacote**e, em seguida, clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="9cecf-162">Optionally, browse to the location to save to, verify the **Save as** option is **Windows Installer Package**, and then click **Save**.</span></span>  
  
5.  <span data-ttu-id="9cecf-163">No menu **Iniciar** , clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="9cecf-163">On the **Start** menu, click **Run**.</span></span>  
  
6.  <span data-ttu-id="9cecf-164">Na caixa de texto Abrir, digite `cmd.`</span><span class="sxs-lookup"><span data-stu-id="9cecf-164">In the Open text box, type `cmd.`</span></span>  
  
7.  <span data-ttu-id="9cecf-165">Na janela do prompt de comando, navegue até pasta em que você salvou o ReportBuilder3_x86.msi.</span><span class="sxs-lookup"><span data-stu-id="9cecf-165">In the Command Prompt window, navigate to the folder where you saved ReportBuilder3_x86.msi.</span></span>  
  
8.  <span data-ttu-id="9cecf-166">Digite um comando com o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="9cecf-166">Type a command with the following format:</span></span>  
  
     `msiexec/i ReportBuilder3_.msi /option [value] [/option [value]]`  
  
     <span data-ttu-id="9cecf-167">As duas opções específicas para instalar o Construtor de Relatórios são: RBINSTALLDIR e REPORTSERVERURL.</span><span class="sxs-lookup"><span data-stu-id="9cecf-167">The two options specific to installing Report Builder are: RBINSTALLDIR and REPORTSERVERURL.</span></span> <span data-ttu-id="9cecf-168">Não é necessário incluir esses argumentos na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="9cecf-168">It not required that you include these arguments in the command line.</span></span> <span data-ttu-id="9cecf-169">O comando de linha de base é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9cecf-169">The following is the baseline command:</span></span>  
  
     `msiexec /i ReportBuilder3_x86.msi /quiet`  
  
9. <span data-ttu-id="9cecf-170">Para executar o comando, pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="9cecf-170">To run the command, press Enter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cecf-171">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9cecf-171">See Also</span></span>  
 <span data-ttu-id="9cecf-172">[Instalar, desinstalar e Construtor de Relatórios suporte](../install-uninstall-and-report-builder-support.md) </span><span class="sxs-lookup"><span data-stu-id="9cecf-172">[Install, Uninstall, and Report Builder Support](../install-uninstall-and-report-builder-support.md) </span></span>  
 [<span data-ttu-id="9cecf-173">Desinstale a versão autônoma do Construtor de Relatórios &#40;Construtor de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="9cecf-173">Uninstall the Stand-Alone Version of Report Builder &#40;Report Builder&#41;</span></span>](install-report-builder.md)  
  
  
