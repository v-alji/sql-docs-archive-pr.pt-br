---
title: Fazer upgrade do Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- upgrading databases
- databases [Analysis Services], upgrading
- installing Analysis Services, side-by-side installations
- Analysis Services upgrades
- Analysis Services upgrades, about upgrading Analysis Services
- SSAS, database migration
- upgrading Analysis Services
- installing Analysis Services, upgrading
- SSAS, upgrading
ms.assetid: a131d329-386e-4470-aaa9-ffcde4e5ec0c
author: Minewiskan
ms.author: owend
ms.openlocfilehash: 78bf7f27233bcfd46bc1f189324eddc72adcc961
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572168"
---
# <a name="upgrade-analysis-services"></a><span data-ttu-id="e3015-102">Atualizar o Analysis Services</span><span class="sxs-lookup"><span data-stu-id="e3015-102">Upgrade Analysis Services</span></span>
  <span data-ttu-id="e3015-103">Use a configuração do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para atualizar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3015-103">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup to upgrade [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e3015-104">Para obter informações detalhadas sobre como atualizar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no modo do SharePoint, consulte [Atualizar PowerPivot para SharePoint](upgrade-power-pivot-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="e3015-104">For detailed information on upgrading [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in SharePoint mode, see [Upgrade PowerPivot for SharePoint](upgrade-power-pivot-for-sharepoint.md).</span></span> <span data-ttu-id="e3015-105">Para obter mais informações sobre como atualizar uma instância existente do SQL Server, consulte [atualizar para o SQL Server 2014 usando o assistente de instalação &#40;&#41;de instalação ](upgrade-sql-server-using-the-installation-wizard-setup.md).</span><span class="sxs-lookup"><span data-stu-id="e3015-105">For more information about upgrading an existing SQL Server instance, see [Upgrade to SQL Server 2014 Using the Installation Wizard &#40;Setup&#41;](upgrade-sql-server-using-the-installation-wizard-setup.md).</span></span>  
  
## <a name="known-upgrade-issues"></a><span data-ttu-id="e3015-106">Problemas de atualização conhecidos</span><span class="sxs-lookup"><span data-stu-id="e3015-106">Known Upgrade Issues</span></span>  
 <span data-ttu-id="e3015-107">Antes de atualizar para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], revise o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e3015-107">Before upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], review the following:</span></span>  
  
-   <span data-ttu-id="e3015-108">[Notas de versão do SQL Server 2014](https://go.microsoft.com/fwlink/?LinkID=296445).</span><span class="sxs-lookup"><span data-stu-id="e3015-108">[SQL Server 2014 Release Notes](https://go.microsoft.com/fwlink/?LinkID=296445).</span></span>  
  
-   <span data-ttu-id="e3015-109">Para saber quais [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] recursos e funcionalidades foram descontinuados, preteridos ou alterados, consulte [Analysis Services compatibilidade com versões anteriores](https://docs.microsoft.com/analysis-services/analysis-services-backward-compatibility).</span><span class="sxs-lookup"><span data-stu-id="e3015-109">To learn which [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] features and functionality have been discontinued, deprecated, or changed see [Analysis Services Backward Compatibility](https://docs.microsoft.com/analysis-services/analysis-services-backward-compatibility).</span></span>  
  
## <a name="pre-upgrade-checklist"></a><span data-ttu-id="e3015-110">Lista de verificação anterior à atualização</span><span class="sxs-lookup"><span data-stu-id="e3015-110">Pre-Upgrade Checklist</span></span>  
 <span data-ttu-id="e3015-111">Antes de atualizar, revise as informações a seguir:</span><span class="sxs-lookup"><span data-stu-id="e3015-111">Before upgrading, review the following information:</span></span>  
  
-   [<span data-ttu-id="e3015-112">Atualizações de versão e edição com suporte</span><span class="sxs-lookup"><span data-stu-id="e3015-112">Supported Version and Edition Upgrades</span></span>](supported-version-and-edition-upgrades.md)  
  
-   [<span data-ttu-id="e3015-113">Requisitos de hardware e software para instalação do SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="e3015-113">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md)  
  
-   [<span data-ttu-id="e3015-114">Verificar parâmetros do Verificador de Configuração do Sistema</span><span class="sxs-lookup"><span data-stu-id="e3015-114">Check Parameters for the System Configuration Checker</span></span>](check-parameters-for-the-system-configuration-checker.md)  
  
-   [<span data-ttu-id="e3015-115">Considerações sobre segurança para uma instalação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="e3015-115">Security Considerations for a SQL Server Installation</span></span>](../../sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
-   [<span data-ttu-id="e3015-116">Backup e restauração de bancos de dados do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="e3015-116">Backup and Restore of Analysis Services Databases</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/backup-and-restore-of-analysis-services-databases)  
  
-   [<span data-ttu-id="e3015-117">Usar o Supervisor de Atualização para preparar para atualizações</span><span class="sxs-lookup"><span data-stu-id="e3015-117">Use Upgrade Advisor to Prepare for Upgrades</span></span>](../../sql-server/install/use-upgrade-advisor-to-prepare-for-upgrades.md)  
  
## <a name="upgrading-analysis-services"></a><span data-ttu-id="e3015-118">Atualizando o Analysis Services</span><span class="sxs-lookup"><span data-stu-id="e3015-118">Upgrading Analysis Services</span></span>  
 <span data-ttu-id="e3015-119">Você pode escolher entre várias abordagens para atualizar o servidor e os dados:</span><span class="sxs-lookup"><span data-stu-id="e3015-119">You can choose from several approaches to upgrade server and data:</span></span>  
  
-   <span data-ttu-id="e3015-120">Uma **atualização** in-loco substitui os arquivos de programas existentes por [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] arquivos de programas.</span><span class="sxs-lookup"><span data-stu-id="e3015-120">An **in-place upgrade** replaces the existing program files with [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] program files.</span></span> <span data-ttu-id="e3015-121">Os bancos de dados permanecem no mesmo local.</span><span class="sxs-lookup"><span data-stu-id="e3015-121">Databases remain in the same location.</span></span> <span data-ttu-id="e3015-122">As pastas de programa são atualizadas para refletir o novo nome.</span><span class="sxs-lookup"><span data-stu-id="e3015-122">Program folders are updated to reflect the new name.</span></span>  
  
-   <span data-ttu-id="e3015-123">Uma **atualização lado a lado** é uma nova instalação do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] no mesmo computador que tem uma instância existente do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="e3015-123">A **side-by-side upgrade** is a new installation of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on the same computer that has an existing Analysis Services instance.</span></span> <span data-ttu-id="e3015-124">Você pode mover bancos de dados para a nova instância no mesmo computador e, em seguida, desinstalar a versão antiga se você não for mais usá-la.</span><span class="sxs-lookup"><span data-stu-id="e3015-124">You can move databases over to the new instance on the same computer, and then uninstall the old version if you no longer use it.</span></span>  
  
-   <span data-ttu-id="e3015-125">Você também pode instalar o Analysis Services em novo hardware e, em seguida, migrar os bancos de dados existentes para aquele servidor.</span><span class="sxs-lookup"><span data-stu-id="e3015-125">You can also install Analysis Services on new hardware and then migrate existing databases to that server.</span></span>  
  
## <a name="in-place-upgrade"></a><span data-ttu-id="e3015-126">Atualização in-loco</span><span class="sxs-lookup"><span data-stu-id="e3015-126">In-place Upgrade</span></span>  
 <span data-ttu-id="e3015-127">Você pode atualizar uma instância existente do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e, como parte do processo de atualização, migrar automaticamente os bancos de dados existentes da instância antiga para a nova instância do.</span><span class="sxs-lookup"><span data-stu-id="e3015-127">You can upgrade an existing instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and, as part of the upgrade process, automatically migrate existing databases from the old instance to the new instance.</span></span> <span data-ttu-id="e3015-128">Como os metadados e os dados binários são incompatíveis entre as duas versões, você reterá os dados depois de atualizar e não precisará migrar os dados manualmente.</span><span class="sxs-lookup"><span data-stu-id="e3015-128">Because the metadata and binary data is compatible between the two versions, you will retain the data after you upgrade and you do not have to manually migrate the data.</span></span>  
  
 <span data-ttu-id="e3015-129">Para atualizar uma instância existente, execute a Instalação e especifique o nome da instância existente como o nome da nova instância.</span><span class="sxs-lookup"><span data-stu-id="e3015-129">To upgrade an existing instance, run Setup and specify the name of the existing instance as the name of the new instance.</span></span>  
  
## <a name="upgrading-databases"></a><span data-ttu-id="e3015-130">Atualizando bancos de dados</span><span class="sxs-lookup"><span data-stu-id="e3015-130">Upgrading Databases</span></span>  
 <span data-ttu-id="e3015-131">Bancos de dados que foram criados em versões anteriores do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] são executados no servidor atualizado sob uma configuração em nível de compatibilidade do banco de dados mais antigo.</span><span class="sxs-lookup"><span data-stu-id="e3015-131">Databases that were created in previous versions of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] run on the upgraded server under an older database compatibility level setting.</span></span> <span data-ttu-id="e3015-132">Os bancos de dados criados nas seguintes versões têm um nível de compatibilidade de banco de dados igual a 105.</span><span class="sxs-lookup"><span data-stu-id="e3015-132">Databases created in the following versions, have a database compatibility level of 105.</span></span> <span data-ttu-id="e3015-133">Você pode alterar o nível de compatibilidade se desejar usar recursos que exijam um nível de compatibilidade de banco de dados mais novo.</span><span class="sxs-lookup"><span data-stu-id="e3015-133">You can change the compatibility level if you want to use features that require a newer database compatibility level.</span></span> <span data-ttu-id="e3015-134">Caso contrário, você poderá executar os bancos de dados no servidor atualizado com o uso das configurações originais.</span><span class="sxs-lookup"><span data-stu-id="e3015-134">Otherwise, you can run the databases on the upgraded server using the original settings.</span></span> <span data-ttu-id="e3015-135">Para obter mais informações, consulte [definir o nível de compatibilidade de um banco de dados multidimensional &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/compatibility-level-of-a-multidimensional-database-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="e3015-135">For more information, see [Set the Compatibility Level of a Multidimensional Database &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/compatibility-level-of-a-multidimensional-database-analysis-services).</span></span>  
  
-   [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]  
  
-   [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]  
  
-   [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]  
  
-   [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e3015-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e3015-136">See Also</span></span>  
 <span data-ttu-id="e3015-137">[Recursos com suporte nas edições do SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span><span class="sxs-lookup"><span data-stu-id="e3015-137">[Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span></span>  
 <span data-ttu-id="e3015-138">[Planejando uma instalação do SQL Server](../../sql-server/install/planning-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="e3015-138">[Planning a SQL Server Installation](../../sql-server/install/planning-a-sql-server-installation.md) </span></span>  
 <span data-ttu-id="e3015-139">[Noções básicas sobre a arquitetura Microsoft OLAP](https://docs.microsoft.com/analysis-services/multidimensional-models/olap-physical/understanding-microsoft-olap-architecture) </span><span class="sxs-lookup"><span data-stu-id="e3015-139">[Understanding Microsoft OLAP Architecture](https://docs.microsoft.com/analysis-services/multidimensional-models/olap-physical/understanding-microsoft-olap-architecture) </span></span>  
 <span data-ttu-id="e3015-140">[Atualizar PowerPivot para SharePoint](upgrade-power-pivot-for-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="e3015-140">[Upgrade PowerPivot for SharePoint](upgrade-power-pivot-for-sharepoint.md) </span></span>  
 <span data-ttu-id="e3015-141">[Instalar Analysis Services no modo multidimensional e de mineração de dados](../../sql-server/install/install-analysis-services-in-multidimensional-and-data-mining-mode.md) </span><span class="sxs-lookup"><span data-stu-id="e3015-141">[Install Analysis Services in Multidimensional and Data Mining Mode](../../sql-server/install/install-analysis-services-in-multidimensional-and-data-mining-mode.md) </span></span>  
 [<span data-ttu-id="e3015-142">Instalação do PowerPivot para SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="e3015-142">PowerPivot for SharePoint 2010 Installation</span></span>](../../sql-server/install/powerpivot-for-sharepoint-2010-installation.md)  
  
  
