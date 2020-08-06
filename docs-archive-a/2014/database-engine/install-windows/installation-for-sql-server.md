---
title: Instalação do SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 09/09/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
f1_keywords:
- sql12.portal.Installation.f1
helpviewer_keywords:
- installing SQL Server, initial installation
- installation [SQL Server]
- initial installation [SQL Server]
ms.assetid: edd75f68-dc62-4479-a596-57ce8ad632e5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 62630400f276b00de8acfa875244558cdb39e47b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679490"
---
# <a name="installation-for-sql-server-2014"></a><span data-ttu-id="67ef4-102">Instalação para SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="67ef4-102">Installation for SQL Server 2014</span></span>
 ## <a name="download-sql-server-2014-express"></a>[<span data-ttu-id="67ef4-103">Baixar o SQL Server 2014 Express</span><span class="sxs-lookup"><span data-stu-id="67ef4-103">Download SQL Server 2014 Express</span></span>](http://www.hanselman.com/blog/DownloadSQLServerExpress.aspx)
  <span data-ttu-id="67ef4-104">**Obrigado a [Scott Hanselman](http://www.hanselman.com/) para coletar todos os links do pacote do instalador em um só lugar!**</span><span class="sxs-lookup"><span data-stu-id="67ef4-104">**Thank you to [Scott Hanselman](http://www.hanselman.com/) for collecting all of the installer package links in one place!**</span></span>
  
  <span data-ttu-id="67ef4-105">O Assistente de Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fornece uma única árvore de recurso para instalar todos os componentes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="67ef4-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard provides a single feature tree to install all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components:</span></span>  
  
-   [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
-   [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
-   [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]  
  
-   [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)]  
  
-   [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)]  
  
-   <span data-ttu-id="67ef4-106">Ferramentas de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="67ef4-106">Management tools</span></span>  
  
-   <span data-ttu-id="67ef4-107">Componentes de conectividade</span><span class="sxs-lookup"><span data-stu-id="67ef4-107">Connectivity components</span></span>  
  
 <span data-ttu-id="67ef4-108">Você pode instalar cada componente individualmente ou selecionar uma combinação dos componentes listados acima.</span><span class="sxs-lookup"><span data-stu-id="67ef4-108">You can install each component individually or select a combination of the components listed above.</span></span> <span data-ttu-id="67ef4-109">Para fazer a melhor escolha entre as edições e os componentes disponíveis no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consulte [edições e componentes do SQL Server 2014](../../sql-server/editions-and-components-of-sql-server-2016.md) e [recursos com suporte nas edições do SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="67ef4-109">To make the best choice among the editions and components available in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Editions and Components of SQL Server 2014](../../sql-server/editions-and-components-of-sql-server-2016.md) and [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="67ef4-110">O [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] está disponível em edições de 32 e 64 bits.</span><span class="sxs-lookup"><span data-stu-id="67ef4-110">[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] is available in 32-bit and 64-bit editions.</span></span>
 
 <span data-ttu-id="67ef4-111">**Experimente:**</span><span class="sxs-lookup"><span data-stu-id="67ef4-111">**Try it out:**</span></span>  
  
-   <span data-ttu-id="67ef4-112">Tem uma conta do Azure?</span><span class="sxs-lookup"><span data-stu-id="67ef4-112">Have an Azure account?</span></span>  <span data-ttu-id="67ef4-113">Em seguida, acesse **[aqui](https://ms.portal.azure.com/?flight=1#create/Microsoft.SQLServer2016RTMEnterpriseWindowsServer2012R2)** para criar uma máquina virtual com o SQL Server 2014 Service Pack 1 (SP1) já instalado.</span><span class="sxs-lookup"><span data-stu-id="67ef4-113">Then go **[Here](https://ms.portal.azure.com/?flight=1#create/Microsoft.SQLServer2016RTMEnterpriseWindowsServer2012R2)** to spin up a Virtual Machine with SQL Server 2014 Service Pack 1 (SP1) already installed.</span></span> <span data-ttu-id="67ef4-114">Para obter mais informações sobre o SQL Server 2014 (SP1), consulte [informações de versão do SQL Server 2014 Service Pack 1](https://support.microsoft.com/kb/3058865).</span><span class="sxs-lookup"><span data-stu-id="67ef4-114">For more information on SQL Server 2014 (SP1), see [SQL Server 2014 Service Pack 1 release information](https://support.microsoft.com/kb/3058865).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="67ef4-115">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="67ef4-115">In This Section</span></span>  
 <span data-ttu-id="67ef4-116">Independentemente de você usar o Assistente de Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou o prompt de comando para instalar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a Instalação envolve as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="67ef4-116">Regardless of whether you use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard or the command prompt to install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Setup involves the following steps:</span></span>  
  
 [<span data-ttu-id="67ef4-117">Planejando uma instalação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="67ef4-117">Planning a SQL Server Installation</span></span>](../../sql-server/install/planning-a-sql-server-installation.md)  
 <span data-ttu-id="67ef4-118">Descreve como preparar seu computador para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="67ef4-118">Describes how to prepare your computer for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="67ef4-119">Requisitos de hardware e software.</span><span class="sxs-lookup"><span data-stu-id="67ef4-119">Hardware and software requirements.</span></span>  
  
-   <span data-ttu-id="67ef4-120">Requisitos do Verificador de Configuração do Sistema e questões de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="67ef4-120">System Configuration Checker requirements and blocking issues.</span></span>  
  
-   <span data-ttu-id="67ef4-121">Considerações sobre segurança.</span><span class="sxs-lookup"><span data-stu-id="67ef4-121">Security considerations.</span></span>  
  
 [<span data-ttu-id="67ef4-122">Instalar o SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="67ef4-122">Install SQL Server 2014</span></span>](install-sql-server.md)  
 <span data-ttu-id="67ef4-123">Descreve as opções de instalação para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67ef4-123">Describes installation options for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="67ef4-124">Atualizar para o SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="67ef4-124">Upgrade to SQL Server 2014</span></span>](upgrade-sql-server.md)  
 <span data-ttu-id="67ef4-125">Descreve as opções de atualização para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67ef4-125">Describes options for upgrading to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="67ef4-126">Desinstalar o SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="67ef4-126">Uninstall SQL Server 2014</span></span>](../../sql-server/install/uninstall-sql-server.md)  
 <span data-ttu-id="67ef4-127">Descreve procedimentos para desinstalar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e o [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67ef4-127">Describes procedures to uninstall [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)].</span></span>  
  
 [<span data-ttu-id="67ef4-128">Instalação do cluster de failover do SQL Server</span><span class="sxs-lookup"><span data-stu-id="67ef4-128">SQL Server Failover Cluster Installation</span></span>](../../sql-server/failover-clusters/install/sql-server-failover-cluster-installation.md)  
 <span data-ttu-id="67ef4-129">Esta seção da documentação da Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] explica como instalar e configurar o cluster de failover do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="67ef4-129">This section of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup documentation explains how to install, and configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster.</span></span>  
  
 [<span data-ttu-id="67ef4-130">Install SQL Server 2014 BI Features</span><span class="sxs-lookup"><span data-stu-id="67ef4-130">Install SQL Server 2014 BI Features</span></span>](../../sql-server/install/install-sql-server-business-intelligence-features.md)  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="67ef4-131">recursos que são parte da plataforma Microsoft BI e que incluem [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]e vários aplicativos cliente usados para criação ou funcionamento com dados analíticos.</span><span class="sxs-lookup"><span data-stu-id="67ef4-131">features that are part of the Microsoft BI platform include [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], and several client applications used for creating or working with analytical data.</span></span> <span data-ttu-id="67ef4-132">Esta seção da documentação da Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] explica como instalar o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67ef4-132">This section of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup documentation explains how to install [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="67ef4-133">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="67ef4-133">Related Sections</span></span>  
 [<span data-ttu-id="67ef4-134">Tópicos de instruções sobre a instalação</span><span class="sxs-lookup"><span data-stu-id="67ef4-134">Installation How-to Topics</span></span>](../../sql-server/install/installation-how-to-topics.md)  
 <span data-ttu-id="67ef4-135">Fornece links para tópicos de procedimentos para instalar [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] do assistente de instalação, no prompt de comando, usando arquivos de configuração e o SysPrep.</span><span class="sxs-lookup"><span data-stu-id="67ef4-135">Provides links to procedural topics for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] from the installation wizard, from the command prompt, by using configuration files, and by using SysPrep.</span></span>  
  
 [<span data-ttu-id="67ef4-136">Instalar SQL Server recursos do BI com o SharePoint &#40;PowerPivot e Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="67ef4-136">Install SQL Server BI Features with SharePoint &#40;PowerPivot and Reporting Services&#41;</span></span>](../../sql-server/install/install-sql-server-bi-features-sharepoint-powerpivot-reporting-services.md)  
 <span data-ttu-id="67ef4-137">Esta seção explica como instalar recursos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em um ambiente do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="67ef4-137">This section explains how to install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] features in a SharePoint environment.</span></span> <span data-ttu-id="67ef4-138">Ela identifica quais recursos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estão disponíveis para uma versão e uma edição específicas do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="67ef4-138">It identifies which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] features are available given a specific version and edition of SharePoint.</span></span> <span data-ttu-id="67ef4-139">Ela também inclui procedimentos de instalação de PowerPivot para SharePoint e de Reporting Services no modo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="67ef4-139">It also includes installation procedures for PowerPivot for SharePoint and Reporting Services in SharePoint mode.</span></span>  
  
 [<span data-ttu-id="67ef4-140">Instalando exemplos e bancos de dados de exemplo do SQL Server</span><span class="sxs-lookup"><span data-stu-id="67ef4-140">Installing SQL Server Samples and Sample Databases</span></span>](https://sqlserversamples.codeplex.com/)  
 <span data-ttu-id="67ef4-141">Descreve como instalar e configurar os exemplos e bancos de dados de exemplo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="67ef4-141">Describes how to install and configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] samples and sample databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67ef4-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="67ef4-142">See Also</span></span>  
 <span data-ttu-id="67ef4-143">[O que há de novo na instalação do SQL Server](../../sql-server/install/what-s-new-in-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="67ef4-143">[What's New in SQL Server Installation](../../sql-server/install/what-s-new-in-sql-server-installation.md) </span></span>  
 [<span data-ttu-id="67ef4-144">Requisitos de hardware e software para instalação do SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="67ef4-144">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md)  
  
