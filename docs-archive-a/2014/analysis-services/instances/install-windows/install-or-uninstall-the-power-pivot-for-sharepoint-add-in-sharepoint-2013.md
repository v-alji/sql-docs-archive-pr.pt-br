---
title: Instalar ou desinstalar o suplemento de PowerPivot para SharePoint (SharePoint 2013) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: fe13ce8b-9369-4126-928a-9426f9119424
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7df54d11021163167149e5b0c1edd960fee1a2ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679576"
---
# <a name="install-or-uninstall-the-powerpivot-for-sharepoint-add-in-sharepoint-2013"></a><span data-ttu-id="223ab-102">Instalar ou desinstalar o suplemento do PowerPivot para SharePoint (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="223ab-102">Install or Uninstall the PowerPivot for SharePoint Add-in (SharePoint 2013)</span></span>
  [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] <span data-ttu-id="223ab-103">é uma coleção de componentes de servidor de aplicativos e serviços back-end que fornece acesso a dados do [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] em um farm do [!INCLUDE[SPS2013](../../../includes/sps2013-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="223ab-103">is a collection of application server components and back-end services that provide [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] data access in a [!INCLUDE[SPS2013](../../../includes/sps2013-md.md)] farm.</span></span> <span data-ttu-id="223ab-104">O suplemento [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] para SharePoint (**spPowerpivot.msi**) é um pacote do instalador usado para instalar os componentes de servidor de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="223ab-104">The [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] for SharePoint add-in (**spPowerpivot.msi**) is an installer package used to install the application server components.</span></span>

-   <span data-ttu-id="223ab-105">O suplemento não é necessário para implantações do SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="223ab-105">The add-in is not required for SharePoint 2010 deployments.</span></span>

-   <span data-ttu-id="223ab-106">O suplemento não é necessário em uma implantação de servidor único que inclui o SharePoint 2013 e o [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] no modo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="223ab-106">The add-in is not required on a single server deployment that includes SharePoint 2013 and [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in SharePoint mode.</span></span> <span data-ttu-id="223ab-107">Os componentes instalados pelo suplemento são incluídos quando você instala um servidor do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] no modo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="223ab-107">The components installed by the add-in are included when you install an [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] server in SharePoint mode.</span></span> <span data-ttu-id="223ab-108">Para diagramas de implantações de exemplo com o suplemento, consulte [topologias de implantação para recursos de SQL Server bi no SharePoint](../../../sql-server/install/deployment-topologies-for-sql-server-bi-features-in-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="223ab-108">For diagrams of example deployments with the add-in, see [Deployment Topologies for SQL Server BI Features in SharePoint](../../../sql-server/install/deployment-topologies-for-sql-server-bi-features-in-sharepoint.md).</span></span>

 <span data-ttu-id="223ab-109">**Observação:** este tópico descreve a instalação de arquivos de solução do [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] e a ferramenta de configuração do [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] para SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="223ab-109">**Note:** This topic describes installing the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] solution files and [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] for SharePoint 2013 Configuration tool.</span></span> <span data-ttu-id="223ab-110">Após a instalação, consulte o tópico a seguir para obter informações sobre a ferramenta de configuração e recursos adicionais, [Configurar o PowerPivot e implantar soluções &#40;o SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/configure-power-pivot-and-deploy-solutions-sharepoint-2013).</span><span class="sxs-lookup"><span data-stu-id="223ab-110">After the installation, see the following topic for information on the configuration tool and additional features, [Configure PowerPivot and Deploy Solutions &#40;SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/configure-power-pivot-and-deploy-solutions-sharepoint-2013).</span></span>

 <span data-ttu-id="223ab-111">Para obter informações sobre como baixar o **spPowerPivot.msi**, consulte [Microsoft® SQL Server® 2014 PowerPivot® para Microsoft SharePoint®](https://go.microsoft.com/fwlink/?LinkID=324854).</span><span class="sxs-lookup"><span data-stu-id="223ab-111">For information on how to download **spPowerPivot.msi**, see [Microsoft® SQL Server® 2014 PowerPivot® for Microsoft SharePoint®](https://go.microsoft.com/fwlink/?LinkID=324854).</span></span>

 <span data-ttu-id="223ab-112">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="223ab-112">**In this topic:**</span></span>

-   [<span data-ttu-id="223ab-113">Tela de fundo</span><span class="sxs-lookup"><span data-stu-id="223ab-113">Background</span></span>](#bkmk_background)

-   [<span data-ttu-id="223ab-114">Onde instalar o spPowerPivot.msi?</span><span class="sxs-lookup"><span data-stu-id="223ab-114">Where to Install spPowerPivot.msi?</span></span>](#bkmk_where_to_install)

-   [<span data-ttu-id="223ab-115">Requisitos e pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="223ab-115">Requirements and Prerequisites</span></span>](#bkmk_prereq)

-   [<span data-ttu-id="223ab-116">Para instalar o PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="223ab-116">To Install PowerPivot for SharePoint</span></span>](#bkmk_install)

-   [<span data-ttu-id="223ab-117">Implantar os arquivos de solução do SharePoint com a Ferramenta de Configuração do PowerPivot para SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="223ab-117">Deploy the SharePoint Solution Files with the PowerPivot for SharePoint 2013 Configuration Tool</span></span>](#bkmk_deploy_solution)

-   [<span data-ttu-id="223ab-118">Desinstalar ou reparar o suplemento</span><span class="sxs-lookup"><span data-stu-id="223ab-118">Uninstall or repair the add-in</span></span>](#bkmk_remove_addin)

##  <a name="background"></a><a name="bkmk_background"></a> <span data-ttu-id="223ab-119">Plano de fundo</span><span class="sxs-lookup"><span data-stu-id="223ab-119">Background</span></span>

-   <span data-ttu-id="223ab-120">**Servidor de Aplicativos:** [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] no SharePoint 2013 inclui o uso de pastas de trabalho como uma fonte de dados, a atualização de dados agendada e o Painel de Gerenciamento do [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="223ab-120">**Application Server:** [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] functionality in SharePoint 2013 includes using workbooks as a data source, scheduled data refresh, and the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] Management Dashboard.</span></span>

     [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)]<span data-ttu-id="223ab-121">o é um [!INCLUDE[msCoName](../../../includes/msconame-md.md)] pacote de Windows Installer (**spPowerpivot.msi**) que implanta bibliotecas de cliente Analysis Services e copia os [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] arquivos de instalação no computador.</span><span class="sxs-lookup"><span data-stu-id="223ab-121">is a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows Installer package (**spPowerpivot.msi**) that deploys Analysis Services client libraries and copies [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] installation files to the computer.</span></span> <span data-ttu-id="223ab-122">O instalador não implanta nem configura recursos do [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="223ab-122">The installer does not deploy or configure [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] features in SharePoint.</span></span> <span data-ttu-id="223ab-123">Os seguintes componentes são instalados por padrão:</span><span class="sxs-lookup"><span data-stu-id="223ab-123">The following components install by default:</span></span>

    -   [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] <span data-ttu-id="223ab-124">2013. Esse componente inclui os scripts do PowerShell (arquivos .ps1), os pacotes de solução do SharePoint (.wsp) e a ferramenta de configuração do [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] 2013 para implantar o [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] em um farm do SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="223ab-124">2013. This component includes PowerShell scripts (.ps1 files), SharePoint solution packages (.wsp), and the [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] 2013 configuration tool to deploy [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] in a SharePoint 2013 farm.</span></span>

    -   [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="223ab-125">Provedor OLE DB para Analysis Services (MSOLAP).</span><span class="sxs-lookup"><span data-stu-id="223ab-125">OLE DB Provider for Analysis Services (MSOLAP).</span></span>

    -   <span data-ttu-id="223ab-126">Provedor de dados ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="223ab-126">ADOMD.NET data provider.</span></span>

    -   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="223ab-127">.</span><span class="sxs-lookup"><span data-stu-id="223ab-127">Analysis Management Objects.</span></span>

-   <span data-ttu-id="223ab-128">**Serviços de back-end:** se você usar o [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] para Excel para criar pastas de trabalho que contêm dados analíticos, será necessário ter Serviços do Excel configurados com um servidor BI que executa o [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] no modo SharePoint para acessar esses dados em um ambiente de servidor.</span><span class="sxs-lookup"><span data-stu-id="223ab-128">**Backend services:** If you use [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] for Excel to create workbooks that contain analytical data, you must have Excel Services configured with a BI server running [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in SharePoint mode to access that data in a server environment.</span></span> <span data-ttu-id="223ab-129">Você pode executar a Instalação do SQL Server em um computador que tenha o SharePoint Server 2013 instalado, ou em um computador diferente que não tenha o SharePoint.</span><span class="sxs-lookup"><span data-stu-id="223ab-129">You can run SQL Server Setup on a computer that has SharePoint Server 2013 installed, or on a different computer that has no SharePoint software.</span></span> <span data-ttu-id="223ab-130">O Analysis Services não tem nenhuma dependência no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="223ab-130">Analysis Services does not have any dependencies on SharePoint.</span></span>

     <span data-ttu-id="223ab-131">Para obter mais informações sobre como instalar, desinstalar e configurar serviços de back-end, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="223ab-131">For more information on installing, uninstalling, and configuring the backend services, see the following:</span></span>

    -   [<span data-ttu-id="223ab-132">Instalação do PowerPivot para SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="223ab-132">PowerPivot for SharePoint 2013 Installation</span></span>](https://docs.microsoft.com/analysis-services/instances/install-windows/install-analysis-services-in-power-pivot-mode)

    -   [<span data-ttu-id="223ab-133">Desinstalar o PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="223ab-133">Uninstall PowerPivot for SharePoint</span></span>](../../../sql-server/install/uninstall-power-pivot-for-sharepoint.md)

##  <a name="where-to-install-sppowerpivotmsi"></a><a name="bkmk_where_to_install"></a><span data-ttu-id="223ab-134">Onde instalar spPowerPivot.msi?</span><span class="sxs-lookup"><span data-stu-id="223ab-134">Where to Install spPowerPivot.msi?</span></span>
 <span data-ttu-id="223ab-135">Uma prática recomendada é instalar o **spPowerPivot.msi** em todos os servidores do farm do SharePoint para verificar a consistência da configuração, inclusive servidores de aplicativo e servidores Web front-end.</span><span class="sxs-lookup"><span data-stu-id="223ab-135">A recommended best practice is to install **spPowerPivot.msi** on all servers in the SharePoint farm for configuration consistency, including application servers and web-front end servers.</span></span> <span data-ttu-id="223ab-136">O pacote de instalador inclui os provedores de dados do Analysis Services, bem como a ferramenta configuração do [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="223ab-136">The installer package includes the Analysis Services data providers as well as the [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] configuration tool.</span></span> <span data-ttu-id="223ab-137">Ao instalar o **spPowerPivot.msi** , você pode personalizar a instalação excluindo componentes individuais.</span><span class="sxs-lookup"><span data-stu-id="223ab-137">When you install **spPowerPivot.msi** you can customize the installation by excluding individual components.</span></span>

 <span data-ttu-id="223ab-138">**Provedores de dados:** várias tecnologias do SharePoint e do SQL Server usam os provedores de dados do Analysis Services que incluem Serviços do Excel, PerformancePoint Services e Power View.</span><span class="sxs-lookup"><span data-stu-id="223ab-138">**Data providers:** Several SharePoint and SQL Server technologies use the Analysis Services data providers including Excel Services, PerformancePoint Services, and Power View.</span></span> <span data-ttu-id="223ab-139">A instalação do **spPowerPivot.msi** em todos os servidores do SharePoint assegura que o conjunto completo de provedores de dados do Analysis Services e a conectividade do PowerPivot estejam consistentemente disponíveis no farm.</span><span class="sxs-lookup"><span data-stu-id="223ab-139">Installing **spPowerPivot.msi** on all SharePoint servers ensures the full set of Analysis Services data providers and PowerPivot connectivity is consistently available across the farm.</span></span>

> [!NOTE]
>  <span data-ttu-id="223ab-140">Você deve instalar os provedores de dados do Analysis Services em um servidor do SharePoint 2013 que esteja usando o **spPowerPivot.msi**.</span><span class="sxs-lookup"><span data-stu-id="223ab-140">You must install the Analysis Services data providers on a SharePoint 2013 server using **spPowerPivot.msi**.</span></span> <span data-ttu-id="223ab-141">Outros pacotes de instalador disponíveis no Feature Pack do [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)] não têm suporte porque esses pacotes não incluem o arquivos de suporte do SharePoint 2013 exigidos pelos provedores de dados nesse ambiente.</span><span class="sxs-lookup"><span data-stu-id="223ab-141">Other installer packages available in the [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)] Feature Pack are not supported because these packages do not include the SharePoint 2013 support files that the data providers require in this environment.</span></span>

 <span data-ttu-id="223ab-142">**Ferramenta de Configuração:** a ferramenta de configuração do PowerPivot para SharePoint 2013 é necessária somente em um dos servidores do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="223ab-142">**Configuration Tool:** The PowerPivot for SharePoint 2013 configuration tool is required on only one of the SharePoint servers.</span></span> <span data-ttu-id="223ab-143">No entanto, uma prática recomendada em farms de vários servidores é instalar a ferramenta de configuração em pelo menos dois servidores, para que você tem acesso à ferramenta de configuração caso um dos dois servidores esteja offline.</span><span class="sxs-lookup"><span data-stu-id="223ab-143">However a recommended best practice in multi-server farms is to install the configuration tool on at least two servers so you have access to the configuration tool if one of the two servers is offline.</span></span>

##  <a name="requirements-and-prerequisites"></a><a name="bkmk_prereq"></a><span data-ttu-id="223ab-144">Requisitos e pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="223ab-144">Requirements and Prerequisites</span></span>

-   [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="223ab-145">SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="223ab-145">SharePoint Server 2013.</span></span>

-   <span data-ttu-id="223ab-146">O**spPowerPivot.msi** é de 64 bits somente, de acordo com os requisitos dos produtos e das tecnologias do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="223ab-146">**spPowerPivot.msi** is 64-bit only, in accordance with the requirements of SharePoint products and technologies.</span></span>

-   <span data-ttu-id="223ab-147">Um servidor do [!INCLUDE[ssASCurrent](../../../includes/ssascurrent-md.md)] no modo do PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="223ab-147">A [!INCLUDE[ssASCurrent](../../../includes/ssascurrent-md.md)] server in PowerPivot mode.</span></span> <span data-ttu-id="223ab-148">Os Serviços do Excel usarão a instância do SQL Server Analysis Services como um servidor do PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="223ab-148">Excel Services will use the SQL Server Analysis Services instance as a PowerPivot server.</span></span> <span data-ttu-id="223ab-149">O Analysis Services pode ser executado em um computador local ou remoto.</span><span class="sxs-lookup"><span data-stu-id="223ab-149">Analysis Services can run on the local or a remote computer.</span></span>

-   <span data-ttu-id="223ab-150">**Permissões:** para instalar o [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)], o usuário atual precisará ser um administrador no computador e um grupo Administradores de Farm do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="223ab-150">**Permissions:** To install [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)], the current user is required to be an administrator on the computer and a SharePoint Farm Administrators group.</span></span>

-   <span data-ttu-id="223ab-151">Para obter mais informações sobre [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] requisitos e pré-requisitos, acesse [requisitos de hardware e Software para Analysis Services Server no modo do SharePoint &#40;SQL Server 2014&#41;](../../../sql-server/install/hardware-software-requirements-analysis-services-server-sharepoint-mode.md).</span><span class="sxs-lookup"><span data-stu-id="223ab-151">For more information on [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] requirements and pre-requisites, go to [Hardware and Software Requirements for Analysis Services Server in SharePoint Mode &#40;SQL Server 2014&#41;](../../../sql-server/install/hardware-software-requirements-analysis-services-server-sharepoint-mode.md).</span></span>

##  <a name="to-install-powerpivot-for-sharepoint"></a><a name="bkmk_install"></a><span data-ttu-id="223ab-152">Para instalar o PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="223ab-152">To Install PowerPivot for SharePoint</span></span>
 <span data-ttu-id="223ab-153">O pacote de instalador do **spPowerpivot.msi** dá suporte a uma interface gráfica do usuário e a um modo de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="223ab-153">The **spPowerpivot.msi** installer package supports both a graphical user interface and a command-line mode.</span></span> <span data-ttu-id="223ab-154">Ambos os métodos de instalação requerem a execução do .msi com privilégios de administrador.</span><span class="sxs-lookup"><span data-stu-id="223ab-154">Both methods of installation require that you run the .msi with administrator privileges.</span></span> <span data-ttu-id="223ab-155">Após a instalação, consulte o tópico a seguir para obter informações sobre a ferramenta de configuração e recursos adicionais, [Configurar o PowerPivot e implantar soluções &#40;o SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/configure-power-pivot-and-deploy-solutions-sharepoint-2013).</span><span class="sxs-lookup"><span data-stu-id="223ab-155">After the installation, see the following topic for information on the configuration tool and additional features, [Configure PowerPivot and Deploy Solutions &#40;SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/configure-power-pivot-and-deploy-solutions-sharepoint-2013).</span></span>

### <a name="user-interface-installation"></a><span data-ttu-id="223ab-156">Instalação da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="223ab-156">User interface installation</span></span>
 <span data-ttu-id="223ab-157">Para instalar o [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] com a interface gráfica do usuário, conclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="223ab-157">To install [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] with the graphical user interface, complete the following steps:</span></span>

1.  <span data-ttu-id="223ab-158">Execute o **SpPowerPivot.msi**.</span><span class="sxs-lookup"><span data-stu-id="223ab-158">Run **SpPowerPivot.msi**.</span></span>

2.  <span data-ttu-id="223ab-159">Clique em **Avançar** na página Bem-vindo.</span><span class="sxs-lookup"><span data-stu-id="223ab-159">Click **Next** on the Welcome page.</span></span>

3.  <span data-ttu-id="223ab-160">Revise e aceite o contrato de licença, e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="223ab-160">Review and accept the license agreement, then click **Next**.</span></span>

4.  <span data-ttu-id="223ab-161">Na página **Seleção de Recursos** , todos os recursos são selecionados por padrão.</span><span class="sxs-lookup"><span data-stu-id="223ab-161">On the **Feature Selection** page, all of the features are selected by default.</span></span>

5.  <span data-ttu-id="223ab-162">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="223ab-162">Click **Next**.</span></span>

6.  <span data-ttu-id="223ab-163">Clique em **Instalar** para concluir a instalação.</span><span class="sxs-lookup"><span data-stu-id="223ab-163">Click **Install** to install to finish the installation.</span></span>

### <a name="command-line-installation"></a><span data-ttu-id="223ab-164">Instalação na linha de comando</span><span class="sxs-lookup"><span data-stu-id="223ab-164">Command Line Installation</span></span>
 <span data-ttu-id="223ab-165">Para uma instalação em linha de comando, abra um prompt de comando com permissões administrativas e execute o **spPowerPivot.msi**.</span><span class="sxs-lookup"><span data-stu-id="223ab-165">For a command-line installation, open a command prompt with administrative permissions, and then run the **spPowerPivot.msi**.</span></span> <span data-ttu-id="223ab-166">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="223ab-166">For example:</span></span>

 <span data-ttu-id="223ab-167">`Msiexec.exe /i SpPowerPivot.msi`.</span><span class="sxs-lookup"><span data-stu-id="223ab-167">`Msiexec.exe /i SpPowerPivot.msi`.</span></span>

 <span data-ttu-id="223ab-168">Para criar um log de instalação, use as opções de log MsiExec padrão.</span><span class="sxs-lookup"><span data-stu-id="223ab-168">To create an installation log, use the standard MsiExec logging switches.</span></span> <span data-ttu-id="223ab-169">O exemplo a seguir cria o arquivo de log "Install_Log.txt" usando a opção de log detalhado "v".</span><span class="sxs-lookup"><span data-stu-id="223ab-169">The following example creates the log file "Install_Log.txt" using the "v" verbose logging switch.</span></span>

```cmd
Msiexec.exe /i SpPowerPivot.msi /L v c:\test\Install_Log.txt
```

### <a name="quiet-command-line-installation-for-scripting"></a><span data-ttu-id="223ab-170">Instalação silenciosa na linha de comando para scripts</span><span class="sxs-lookup"><span data-stu-id="223ab-170">Quiet Command Line Installation for scripting</span></span>
 <span data-ttu-id="223ab-171">Você pode usar as opções **/q** ou **/Quiet** para uma instalação "silenciosa" que não exibirá caixas de diálogo ou avisos.</span><span class="sxs-lookup"><span data-stu-id="223ab-171">You can use the **/q** or **/quiet** switches for a "quiet" installation that will not display any dialogs or warnings.</span></span> <span data-ttu-id="223ab-172">A instalação silenciosa é útil quando você deseja gerar scripts da instalação do suplemento.</span><span class="sxs-lookup"><span data-stu-id="223ab-172">The quiet installation is useful if you want to script the installation of the add-in.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="223ab-173">Se você usar a opção **/q** para uma instalação de linha de comando silenciosa, o contrato de licença de usuário final não será exibido.</span><span class="sxs-lookup"><span data-stu-id="223ab-173">If you use the **/q** switch for a silent command line installation, the end-user license agreement will not be displayed.</span></span> <span data-ttu-id="223ab-174">Independentemente do método de instalação, o uso deste software é controlado por um contrato de licença e você é responsável por respeitar o contrato de licença.</span><span class="sxs-lookup"><span data-stu-id="223ab-174">Regardless of the installation method, the use of this software is governed by a license agreement and you are responsible for complying with the license agreement.</span></span>

#### <a name="to-perform-a-quiet-installation"></a><span data-ttu-id="223ab-175">Para executar uma instalação silenciosa</span><span class="sxs-lookup"><span data-stu-id="223ab-175">To perform a quiet installation</span></span>

1.  <span data-ttu-id="223ab-176">Abra um prompt **de comando com permissões de administrador**.</span><span class="sxs-lookup"><span data-stu-id="223ab-176">Open a command prompt **with administrator permissions**.</span></span>

2.  <span data-ttu-id="223ab-177">Execute o comando a seguir:</span><span class="sxs-lookup"><span data-stu-id="223ab-177">Run the following command:</span></span>

    ```cmd
    Msiexec.exe /i spPowerPivot.msi /q
    ```

### <a name="command-line-installation-to-include-specific-components"></a><span data-ttu-id="223ab-178">Instalação na linha de comando para incluir componentes específicos</span><span class="sxs-lookup"><span data-stu-id="223ab-178">Command Line Installation to include specific components</span></span>
 <span data-ttu-id="223ab-179">A ferramenta de configuração do [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] não é necessária em todos os servidores do SharePoint. No entanto, é recomendável instalá-la pelo menos em dois servidores para que a ferramenta de configuração esteja disponível quando você precisar.</span><span class="sxs-lookup"><span data-stu-id="223ab-179">The [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] Configuration tool is not required on every SharePoint server, however it is recommended to install it on at least two servers so the configuration tool is available when you need it.</span></span>

 <span data-ttu-id="223ab-180">Quando você instala o spPowerPivot.msi, pode usar as opções de linha de comando para instalar itens específicos, como os provedores de dados, e não a ferramenta de configuração do [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="223ab-180">When you install the spPowerPivot.msi, you can use the command line options to install specific items, such as the data providers and not the [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] Configuration tool.</span></span> <span data-ttu-id="223ab-181">A linha de comando a seguir é um exemplo de como instalar todos os componentes exceto a ferramenta de configuração:</span><span class="sxs-lookup"><span data-stu-id="223ab-181">The following command line is an example of installing all components except the configuration tool:</span></span>

```
Msiexec /i spPowerPivot.msi AGREETOLICENSE="yes" ADDLOCAL=" SQL_OLAPDM,SQL_ADOMD,SQL_AMO,SQLAS_SP_Common"
```

|<span data-ttu-id="223ab-182">Opção</span><span class="sxs-lookup"><span data-stu-id="223ab-182">Option</span></span>|<span data-ttu-id="223ab-183">Descrição</span><span class="sxs-lookup"><span data-stu-id="223ab-183">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="223ab-184">Analysis_Server_SP_addin</span><span class="sxs-lookup"><span data-stu-id="223ab-184">Analysis_Server_SP_addin</span></span>|<span data-ttu-id="223ab-185">Configuração do PowerPivot</span><span class="sxs-lookup"><span data-stu-id="223ab-185">PowerPivot Configuration</span></span>|
|<span data-ttu-id="223ab-186">SQL_OLAPDM</span><span class="sxs-lookup"><span data-stu-id="223ab-186">SQL_OLAPDM</span></span>|<span data-ttu-id="223ab-187">MSOLAP</span><span class="sxs-lookup"><span data-stu-id="223ab-187">MSOLAP</span></span>|
|<span data-ttu-id="223ab-188">SQL_ADOMD</span><span class="sxs-lookup"><span data-stu-id="223ab-188">SQL_ADOMD</span></span>|<span data-ttu-id="223ab-189">Provedor ADOMD.net</span><span class="sxs-lookup"><span data-stu-id="223ab-189">ADOMD.net provider</span></span>|
|<span data-ttu-id="223ab-190">SQL_AMO</span><span class="sxs-lookup"><span data-stu-id="223ab-190">SQL_AMO</span></span>|<span data-ttu-id="223ab-191">Provedor AMO</span><span class="sxs-lookup"><span data-stu-id="223ab-191">AMO provider</span></span>|
|<span data-ttu-id="223ab-192">SQLAS_SP_Common</span><span class="sxs-lookup"><span data-stu-id="223ab-192">SQLAS_SP_Common</span></span>|<span data-ttu-id="223ab-193">Componentes comuns do Analysis Services para SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="223ab-193">Analysis Services common components for SharePoint 2013</span></span>|

##  <a name="deploy-the-sharepoint-solution-files-with-the-powerpivot-for-sharepoint-2013-configuration-tool"></a><a name="bkmk_deploy_solution"></a><span data-ttu-id="223ab-194">Implantar os arquivos de solução do SharePoint com a ferramenta de configuração PowerPivot para SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="223ab-194">Deploy the SharePoint Solution Files with the PowerPivot for SharePoint 2013 Configuration Tool</span></span>
 <span data-ttu-id="223ab-195">Três dos arquivos copiados no disco rígido pelo spPowerPivot.msi são arquivos de solução do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="223ab-195">Three of the files copied to the hard drive by spPowerPivot.msi are SharePoint solution files.</span></span> <span data-ttu-id="223ab-196">O escopo de um arquivo de solução é o nível do aplicativo Web, enquanto o escopo do outros arquivos é o nível do farm.</span><span class="sxs-lookup"><span data-stu-id="223ab-196">The scope of one solution file is the Web application level while the scope of the other files is the farm level.</span></span> <span data-ttu-id="223ab-197">Os arquivos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="223ab-197">The files are the following:</span></span>

-   `PowerPivotFarmSolution.wsp`

-   `PowerPivotFarm14Solution.wsp`

-   `PowerPivotWebApplicationSolution.wsp`

 <span data-ttu-id="223ab-198">Os arquivos de solução do são copiados para a seguinte pasta:</span><span class="sxs-lookup"><span data-stu-id="223ab-198">The solution files are copied to the following folder:</span></span>

 `C:\Program Files\Microsoft SQL Server\120\Tools\PowerPivotTools\SPAddinConfiguration\Resources`

 <span data-ttu-id="223ab-199">Após a instalação do .msi, execute a Ferramenta de Configuração do [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] para configurar e implantar as soluções no farm do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="223ab-199">Following the .msi installation, run the [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] Configuration Tool to configure and deploy the solutions in the SharePoint farm.</span></span>

### <a name="to-start-the-configuration-tool"></a><span data-ttu-id="223ab-200">Para iniciar a ferramenta de configuração</span><span class="sxs-lookup"><span data-stu-id="223ab-200">To start the configuration tool</span></span> 

 <span data-ttu-id="223ab-201">Na tela inicial do Windows, digite "Power" e, nos resultados da pesquisa de aplicativos, clique em **configuração de PowerPivot para SharePoint 2013**.</span><span class="sxs-lookup"><span data-stu-id="223ab-201">From the Windows Start screen type "power" and in the Apps search results, click **PowerPivot for SharePoint 2013 Configuration**.</span></span> <span data-ttu-id="223ab-202">Observe que os resultados da pesquisa podem incluir dois links pois a instalação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instala ferramentas de configuração do [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] separadas para o SharePoint 2010 e o SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="223ab-202">Note that the search results may include two links because [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] setup installs separate [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] configuration tools for SharePoint 2010 and SharePoint 2013.</span></span> <span data-ttu-id="223ab-203">Verifique se você iniciou a ferramenta de Configuração do [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] para SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="223ab-203">Make sure you start the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] for SharePoint 2013 Configuration tool.</span></span>

 <span data-ttu-id="223ab-204">![duas ferramentas de configuração do PowerPivot](../../media/as-powerpivot-configtools-bothicons.gif "duas ferramentas de configuração do PowerPivot")</span><span class="sxs-lookup"><span data-stu-id="223ab-204">![two powerpivot configuration tools](../../media/as-powerpivot-configtools-bothicons.gif "two powerpivot configuration tools")</span></span>

 <span data-ttu-id="223ab-205">**Or**</span><span class="sxs-lookup"><span data-stu-id="223ab-205">**Or**</span></span>

1.  <span data-ttu-id="223ab-206">Vá para **Iniciar**, **Todos os Programas**.</span><span class="sxs-lookup"><span data-stu-id="223ab-206">Go to **Start**, **All Programs**.</span></span>

2.  <span data-ttu-id="223ab-207">Clique em **Microsoft SQL Server 2014**.</span><span class="sxs-lookup"><span data-stu-id="223ab-207">Click **Microsoft SQL Server 2014**.</span></span>

3.  <span data-ttu-id="223ab-208">Clique em **Ferramentas de Configuração**.</span><span class="sxs-lookup"><span data-stu-id="223ab-208">Click **Configuration Tools**.</span></span>

4.  <span data-ttu-id="223ab-209">Clique em **Configuração do PowerPivot para SharePoint 2013**.</span><span class="sxs-lookup"><span data-stu-id="223ab-209">Click **PowerPivot for SharePoint 2013 Configuration**.</span></span>

 <span data-ttu-id="223ab-210">Para obter mais informações sobre a ferramenta de configuração, consulte [PowerPivot Configuration Tools](../../power-pivot-sharepoint/power-pivot-configuration-tools.md).</span><span class="sxs-lookup"><span data-stu-id="223ab-210">For more information on the configuration tool, see [PowerPivot Configuration Tools](../../power-pivot-sharepoint/power-pivot-configuration-tools.md).</span></span>

##  <a name="uninstall-or-repair-the-add-in"></a><a name="bkmk_remove_addin"></a><span data-ttu-id="223ab-211">Desinstalar ou reparar o suplemento</span><span class="sxs-lookup"><span data-stu-id="223ab-211">Uninstall or repair the add-in</span></span>

> [!CAUTION]
>  <span data-ttu-id="223ab-212">Se você desinstalar o **spPowerPivot.msi** , os provedores de dados e a ferramenta de configuração serão desinstalados.</span><span class="sxs-lookup"><span data-stu-id="223ab-212">If you uninstall **spPowerPivot.msi** the data providers and the configuration tool are uninstalled.</span></span> <span data-ttu-id="223ab-213">A desinstalação dos provedores de dados fará com que o servidor não consiga se conectar ao PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="223ab-213">Uninstalling the data providers will cause the server to be unable to connect to PowerPivot.</span></span>

 <span data-ttu-id="223ab-214">Você pode desinstalar ou reparar o [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] usando um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="223ab-214">You can uninstall or repair [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] using one of the following methods:</span></span>

1.  <span data-ttu-id="223ab-215">**Painel de controle do Windows:** selecione **Microsoft SQL Server 2012 PowerPivot para SharePoint 2013**.</span><span class="sxs-lookup"><span data-stu-id="223ab-215">**Windows control panel:** Select **Microsoft SQL Server 2012 PowerPivot for SharePoint 2013**.</span></span> <span data-ttu-id="223ab-216">Clique em **Desinstalar** ou **Reparar**.</span><span class="sxs-lookup"><span data-stu-id="223ab-216">Click either **Uninstall** or **Repair**.</span></span>

2.  <span data-ttu-id="223ab-217">Execute o spPowerPivot.msi e selecione a opção **Remover** ou **Reparar** .</span><span class="sxs-lookup"><span data-stu-id="223ab-217">Run the spPowerPivot.msi and select the **Remove** option or the **Repair** option.</span></span>

 <span data-ttu-id="223ab-218">**Linha de comando:** para reparar ou desinstalar o PowerPivot para SharePoint 2013 usando a linha de comando, abra um prompt de comando **com permissões de administrador** e execute um dos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="223ab-218">**Command Line:** To repair or uninstall PowerPivot for SharePoint 2013 using the command line, open a command prompt **with administrator permissions** and run one of the following commands:</span></span>

-   <span data-ttu-id="223ab-219">Para reparar, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="223ab-219">To Repair, run the following command:</span></span>

    ```cmd
    msiexec.exe /f spPowerPivot.msi
    ```

 <span data-ttu-id="223ab-220">OU</span><span class="sxs-lookup"><span data-stu-id="223ab-220">OR</span></span>

-   <span data-ttu-id="223ab-221">Para desinstalar, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="223ab-221">To uninstall, run the following command:</span></span>

    ```cmd
    msiexec.exe /uninstall spPowerPivot.msi
    ```
