---
title: Planejando uma instalação do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- installing SQL Server, planning
ms.assetid: b1d56f2f-603f-48f2-b902-c715f14a6db9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e5b1dae9d2ef32298a9ddf2eeed1530e5ae97683
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581667"
---
# <a name="planning-a-sql-server-installation"></a><span data-ttu-id="48f4d-102">Planejando uma instalação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="48f4d-102">Planning a SQL Server Installation</span></span>
  <span data-ttu-id="48f4d-103">Para instalar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="48f4d-103">To install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], follow these steps:</span></span>  
  
-   <span data-ttu-id="48f4d-104">Examine os requisitos de instalação, as verificações de configuração do sistema e as considerações sobre segurança da instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="48f4d-104">Review installation requirements, system configuration checks, and security considerations for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span>  
  
-   <span data-ttu-id="48f4d-105">Execute a Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para instalar ou atualizar para uma versão posterior.</span><span class="sxs-lookup"><span data-stu-id="48f4d-105">Run [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup to install or upgrade to a later version.</span></span>  
  
-   <span data-ttu-id="48f4d-106">Use os utilitários do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para configurar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48f4d-106">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilities to configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="48f4d-107">Independentemente do método de instalação, é necessário confirmar a aceitação dos termos da licença de software como indivíduo ou em nome de uma entidade, a menos que o uso do software seja governado por um contrato separado, como um contrato de licenciamento por volume da [!INCLUDE[msCoName](../../includes/msconame-md.md)] ou um contrato de terceiros com um ISV ou OEM.</span><span class="sxs-lookup"><span data-stu-id="48f4d-107">Regardless of the installation method, you are required to confirm acceptance of the software license terms as an individual or on behalf of an entity, unless your use of the software is governed by a separate agreement such as a [!INCLUDE[msCoName](../../includes/msconame-md.md)] volume licensing agreement or a third-party agreement with an ISV or OEM.</span></span>  
  
 <span data-ttu-id="48f4d-108">Os termos da licença são exibidos para exame e aceitação na interface do usuário da Instalação.</span><span class="sxs-lookup"><span data-stu-id="48f4d-108">The license terms are displayed for review and acceptance in the Setup user interface.</span></span> <span data-ttu-id="48f4d-109">As instalações autônomas (usando o parâmetro /Q ou /QS) devem incluir o parâmetro /IAcceptSQLServerLicenseTerms.</span><span class="sxs-lookup"><span data-stu-id="48f4d-109">Unattended installations (using the /Q or /QS parameters) must include the /IAcceptSQLServerLicenseTerms parameter.</span></span> <span data-ttu-id="48f4d-110">Você pode analisar as condições de licença separadamente em [Microsoft Software License Terms](https://go.microsoft.com/fwlink/?LinkID=148209)(em inglês).</span><span class="sxs-lookup"><span data-stu-id="48f4d-110">You can review the license terms separately at [Microsoft Software License Terms](https://go.microsoft.com/fwlink/?LinkID=148209).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="48f4d-111">Dependendo de como você recebeu o software (por exemplo, por meio de licenciamento por volume da [!INCLUDE[msCoName](../../includes/msconame-md.md)] ), o uso do software pode estar sujeito a termos e condições adicionais.</span><span class="sxs-lookup"><span data-stu-id="48f4d-111">Depending on how you received the software (for example, through [!INCLUDE[msCoName](../../includes/msconame-md.md)] volume licensing), your use of the software may be subject to additional terms and conditions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="48f4d-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="48f4d-112">In This Section</span></span>  
 [<span data-ttu-id="48f4d-113">Novidades na instalação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="48f4d-113">What's New in SQL Server Installation</span></span>](../../../2014/sql-server/install/what-s-new-in-sql-server-installation.md)  
 <span data-ttu-id="48f4d-114">Este tópico descreve os detalhes sobre os recursos novos ou aprimorados de instalação nesta versão do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48f4d-114">This topic describes the details about the new or improved features of installation in this version of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 [<span data-ttu-id="48f4d-115">Requisitos de hardware e software para instalação do SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="48f4d-115">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](hardware-and-software-requirements-for-installing-sql-server.md)  
 <span data-ttu-id="48f4d-116">Este tópico lista os requisitos mínimos de hardware e software para a instalação e execução de uma instância do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48f4d-116">This topic lists the minimum hardware and software requirements to install and run an instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 [<span data-ttu-id="48f4d-117">Considerações sobre segurança para uma instalação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="48f4d-117">Security Considerations for a SQL Server Installation</span></span>](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
 <span data-ttu-id="48f4d-118">Este tópico descreve algumas práticas recomendadas de segurança que você deve considerar antes de instalar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e depois de instalar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48f4d-118">This topic describes some security best practices that you should consider before you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and after you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="48f4d-119">Configurar contas de serviço e permissões do Windows</span><span class="sxs-lookup"><span data-stu-id="48f4d-119">Configure Windows Service Accounts and Permissions</span></span>](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md)  
 <span data-ttu-id="48f4d-120">Este tópico descreve a configuração padrão de serviços nesta versão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]e as opções de configuração de serviços [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que você pode definir durante e após a instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="48f4d-120">This topic describes the default configuration of services in this release of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and configuration options for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services that you can set during and after [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span>  
  
 [<span data-ttu-id="48f4d-121">Protocolos de rede e bibliotecas de rede</span><span class="sxs-lookup"><span data-stu-id="48f4d-121">Network Protocols and Network Libraries</span></span>](../../../2014/sql-server/install/network-protocols-and-network-libraries.md)  
 <span data-ttu-id="48f4d-122">Este tópico descreve a configuração padrão de protocolos de rede nesta versão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]e as opções de configuração disponíveis.</span><span class="sxs-lookup"><span data-stu-id="48f4d-122">This topic describes the default configuration of network protocols in this release of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and the configuration options available.</span></span>  
  
 [<span data-ttu-id="48f4d-123">Trabalhar com várias versões e instâncias do SQL Server</span><span class="sxs-lookup"><span data-stu-id="48f4d-123">Work with Multiple Versions and Instances of SQL Server</span></span>](../../../2014/sql-server/install/work-with-multiple-versions-and-instances-of-sql-server.md)  
 <span data-ttu-id="48f4d-124">Este tópico descreve as considerações para a instalação de várias versões e instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48f4d-124">This topic describes the considerations for installing multiple versions and instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="48f4d-125">Versões de idiomas locais no SQL Server</span><span class="sxs-lookup"><span data-stu-id="48f4d-125">Local Language Versions in SQL Server</span></span>](../../../2014/sql-server/install/local-language-versions-in-sql-server.md)  
 <span data-ttu-id="48f4d-126">Este tópico descreve sobre as versões localizadas do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48f4d-126">This topic describes about the localized versions of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="48f4d-127">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="48f4d-127">Related Sections</span></span>  
 [<span data-ttu-id="48f4d-128">Instalar o SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="48f4d-128">Install SQL Server 2014</span></span>](../../database-engine/install-windows/install-sql-server.md)  
 <span data-ttu-id="48f4d-129">Esta seção fornece uma visão geral de opções de instalação diferentes disponíveis para instalar o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48f4d-129">This section provides an overview of different installation options we have for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 [<span data-ttu-id="48f4d-130">Install SQL Server 2014 BI Features</span><span class="sxs-lookup"><span data-stu-id="48f4d-130">Install SQL Server 2014 BI Features</span></span>](install-sql-server-business-intelligence-features.md)  
 <span data-ttu-id="48f4d-131">Esta seção da documentação de Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] explica como instalar recursos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que fazem parte da plataforma Microsoft BI.</span><span class="sxs-lookup"><span data-stu-id="48f4d-131">This section of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup documentation explains how to install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] features that are part of the Microsoft BI platform.</span></span>  
  
 [<span data-ttu-id="48f4d-132">Atualizar para o SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="48f4d-132">Upgrade to SQL Server 2014</span></span>](../../database-engine/install-windows/upgrade-sql-server.md)  
 <span data-ttu-id="48f4d-133">A seção fornece uma visão geral da atualização de instâncias de versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48f4d-133">The section provides an overview of upgrading instances of previous [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] versions to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 [<span data-ttu-id="48f4d-134">Desinstalar o SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="48f4d-134">Uninstall SQL Server 2014</span></span>](uninstall-sql-server.md)  
 <span data-ttu-id="48f4d-135">Consulte esta seção para desinstalar totalmente uma instância existente do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] e preparar o sistema para reinstalar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48f4d-135">Refer this section to uninstall an existing instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] completely, and prepare the system so that you can reinstall [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="48f4d-136">Instalação do cluster de failover do SQL Server</span><span class="sxs-lookup"><span data-stu-id="48f4d-136">SQL Server Failover Cluster Installation</span></span>](../failover-clusters/install/sql-server-failover-cluster-installation.md)  
 <span data-ttu-id="48f4d-137">Esta seção da documentação da Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] explica como instalar e configurar o cluster de failover do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="48f4d-137">This section of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup documentation explains how to install, and configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48f4d-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="48f4d-138">See Also</span></span>  
 <span data-ttu-id="48f4d-139">[Instalação de início rápido do SQL Server 2014](../../../2014/getting-started/quick-start-installation-of-sql-server-2014.md) </span><span class="sxs-lookup"><span data-stu-id="48f4d-139">[Quick-Start Installation of SQL Server 2014](../../../2014/getting-started/quick-start-installation-of-sql-server-2014.md) </span></span>  
 <span data-ttu-id="48f4d-140">[Instalar o SQL Server 2014 no prompt de comando](../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md) </span><span class="sxs-lookup"><span data-stu-id="48f4d-140">[Install SQL Server 2014 from the Command Prompt](../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md) </span></span>  
 <span data-ttu-id="48f4d-141">[Soluções de alta disponibilidade &#40;SQL Server&#41;](../failover-clusters/high-availability-solutions-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="48f4d-141">[High Availability Solutions &#40;SQL Server&#41;](../failover-clusters/high-availability-solutions-sql-server.md) </span></span>  
 <span data-ttu-id="48f4d-142">[Antes de instalar o cluster de failover](../failover-clusters/install/before-installing-failover-clustering.md) </span><span class="sxs-lookup"><span data-stu-id="48f4d-142">[Before Installing Failover Clustering](../failover-clusters/install/before-installing-failover-clustering.md) </span></span>  
 [<span data-ttu-id="48f4d-143">Atualize para o SQL Server 2014 usando o assistente de instalação &#40;a instalação&#41;</span><span class="sxs-lookup"><span data-stu-id="48f4d-143">Upgrade to SQL Server 2014 Using the Installation Wizard &#40;Setup&#41;</span></span>](../../database-engine/install-windows/upgrade-sql-server-using-the-installation-wizard-setup.md)  
  
  
