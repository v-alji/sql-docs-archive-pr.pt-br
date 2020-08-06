---
title: Problemas de atualização de Reporting Services (Supervisor de atualização) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Report Manager [Reporting Services], upgrade issues
- Reporting Services, upgrades
- upgrading Reporting Services
- report servers [Reporting Services], upgrade issues
ms.assetid: d9663f25-98d7-4508-ae3c-55a7277211bd
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 569afe735d68a724c0b4cc61ad2b7767088c2b30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583339"
---
# <a name="reporting-services-upgrade-issues-upgrade-advisor"></a><span data-ttu-id="3235d-102">Problemas de atualização do Reporting Services (supervisor de atualização)</span><span class="sxs-lookup"><span data-stu-id="3235d-102">Reporting Services Upgrade Issues (Upgrade Advisor)</span></span>
  <span data-ttu-id="3235d-103">Os tópicos a seguir descrevem os [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] problemas que podem afetar a atualização para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3235d-103">The following topics describe the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] issues that might affect your upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="3235d-104">Eles descrevem ações que podem ser tomadas para diminuir o efeito dessas alterações em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="3235d-104">The topics describe actions that you can take to mitigate the effect of these changes on your environment.</span></span>  
  
 <span data-ttu-id="3235d-105">O Supervisor de Atualização analisa uma instalação do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="3235d-105">Upgrade Advisor analyzes a report server installation.</span></span> <span data-ttu-id="3235d-106">Se apenas componentes cliente estiverem instalados (por exemplo, se o Designer de Relatórios for o único componente do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instalado no computador), nenhum problema será reportado.</span><span class="sxs-lookup"><span data-stu-id="3235d-106">If only client components are installed (for example, if Report Designer is the only [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] component installed on the computer), no issues will be reported.</span></span>  
  
 <span data-ttu-id="3235d-107">Dependendo de como sua instalação foi configurada, você poderá encontrar outros problemas que não foram reportados pelo Supervisor de Atualização.</span><span class="sxs-lookup"><span data-stu-id="3235d-107">Depending on how you configured your installation, you may encounter additional issues that are not reported by Upgrade Advisor.</span></span> <span data-ttu-id="3235d-108">Esses problemas não impedem que a atualização do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] tenha êxito, mas podem afetar a maneira como os relatórios e os aplicativos são executados depois que a atualização é concluída.</span><span class="sxs-lookup"><span data-stu-id="3235d-108">These issues do not prevent a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] upgrade from succeeding, but they may affect how reports and applications run after an upgrade is finished.</span></span> <span data-ttu-id="3235d-109">Para obter mais informações sobre esses problemas, consulte "Compatibilidade com versões anteriores do Reporting Services" nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3235d-109">To learn about these issues, see "Reporting Services Backward Compatibility" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="3235d-110">Se não for possível usar a Instalação para atualizar uma instalação do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], você poderá instalar uma nova instância do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e migrar a instalação existente para essa nova instância.</span><span class="sxs-lookup"><span data-stu-id="3235d-110">If you cannot use Setup to upgrade a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation, you can install a new [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance and migrate your existing installation to the new instance.</span></span> <span data-ttu-id="3235d-111">Para obter mais informações, consulte "atualizar e migrar Reporting Services" nos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] manuais online, [atualizar e migrar Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="3235d-111">For more information, see "Upgrade and Migrate Reporting Services" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online, [Upgrade and Migrate Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md).</span></span>  
  
 <span data-ttu-id="3235d-112">Os tópicos a seguir descrevem problemas conhecidos reportados pelo Supervisor de Atualização e explicam como modificar a instalação existente para permitir que a atualização ocorra.</span><span class="sxs-lookup"><span data-stu-id="3235d-112">The following topics describe known issues that are reported by Upgrade Advisor, and explain how you can modify your existing installation to allow an upgrade to occur.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3235d-113">O Supervisor de Atualização deve estar instalado no servidor de relatório para analisar a instância do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3235d-113">Upgrade Advisor must be installed on the report server to analyze an instance of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="3235d-114">O [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] não dá suporte à análise remota.</span><span class="sxs-lookup"><span data-stu-id="3235d-114">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] does not support remote analysis.</span></span>  
>   
>  <span data-ttu-id="3235d-115">Para obter mais informações, consulte [instalando o supervisor de atualização](../../../2014/sql-server/install/installing-upgrade-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="3235d-115">For more information, see [Installing Upgrade Advisor](../../../2014/sql-server/install/installing-upgrade-advisor.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3235d-116">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="3235d-116">In This Section</span></span>  
  
-   [<span data-ttu-id="3235d-117">Certificados de cliente no site do servidor de relatório &#40;supervisor de atualização&#41;</span><span class="sxs-lookup"><span data-stu-id="3235d-117">Client certificates on the report server web site &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/client-certificates-on-the-report-server-web-site-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3235d-118">Extensões personalizadas foram detectadas no servidor de relatório &#40;supervisor de atualização&#41;</span><span class="sxs-lookup"><span data-stu-id="3235d-118">Custom extensions were detected on the report server &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/custom-extensions-were-detected-on-the-report-server-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3235d-119">Foram detectados itens de relatório personalizados no servidor de relatório &#40;supervisor de atualização&#41;</span><span class="sxs-lookup"><span data-stu-id="3235d-119">Custom report items were detected on the report server &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/custom-report-items-were-detected-on-the-report-server-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3235d-120">Os componentes de compatibilidade com versões anteriores do IIS não foram detectados &#40;supervisor de atualização&#41;</span><span class="sxs-lookup"><span data-stu-id="3235d-120">IIS backward compatibility components were not detected &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/iis-backward-compatibility-components-were-not-detected-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3235d-121">Restrição de endereço IP detectada &#40;supervisor de atualização&#41;</span><span class="sxs-lookup"><span data-stu-id="3235d-121">IP address restriction detected &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/ip-address-restriction-detected-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3235d-122">Filtros ISAPI detectados no site do servidor de relatório &#40;supervisor de atualização&#41;</span><span class="sxs-lookup"><span data-stu-id="3235d-122">ISAPI filters detected on the report server site &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/isapi-filters-detected-on-the-report-server-site-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3235d-123">Foram detectadas extensões obsoletas no computador do servidor de relatório &#40;o supervisor de atualização&#41;</span><span class="sxs-lookup"><span data-stu-id="3235d-123">Obsolete extensions were detected on the report server computer &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/obsolete-extensions-were-detected-on-the-report-server-computer-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3235d-124">O banco de dados do servidor de relatório não está configurado &#40;supervisor de atualização&#41;</span><span class="sxs-lookup"><span data-stu-id="3235d-124">Report server database is not configured &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/report-server-database-is-not-configured-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3235d-125">SQL Server grupo de serviço Web do servidor de relatório 2005 detectado &#40;supervisor de atualização&#41;</span><span class="sxs-lookup"><span data-stu-id="3235d-125">SQL Server 2005 Report Server Web Service group detected &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/sql-server-2005-report-server-web-service-group-detected-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3235d-126">Os diretórios virtuais não são especificados &#40;supervisor de atualização&#41;</span><span class="sxs-lookup"><span data-stu-id="3235d-126">Virtual directories are unspecified &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/virtual-directories-are-unspecified-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3235d-127">O diretório virtual tem um método de autenticação sem suporte &#40;supervisor de atualização&#41;</span><span class="sxs-lookup"><span data-stu-id="3235d-127">Virtual directory has unsupported authentication method &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/virtual-directory-has-unsupported-authentication-method-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3235d-128">Alterações nos limites de CPU e memória para SQL Server Standard e Enterprise &#40;Upgrade Advisor&#41;</span><span class="sxs-lookup"><span data-stu-id="3235d-128">Changes to CPU and memory limits for SQL Server Standard and Enterprise &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/cpu-memory-limits-changes-sql-server-standard-enterprise-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3235d-129">Contas de domínio necessárias para o farm do SharePoint &#40;supervisor de atualização&#41;</span><span class="sxs-lookup"><span data-stu-id="3235d-129">Domain accounts required for SharePoint farm &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/domain-accounts-required-for-sharepoint-farm-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3235d-130">Navegação direta para o servidor de relatório &#40;supervisor de atualização&#41;</span><span class="sxs-lookup"><span data-stu-id="3235d-130">Direct Browsing to Report Server &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/direct-browsing-to-report-server-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3235d-131">O Microsoft SharePoint 2007 está instalado &#40;supervisor de atualização&#41;</span><span class="sxs-lookup"><span data-stu-id="3235d-131">Microsoft SharePoint 2007 is Installed &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/microsoft-sharepoint-2007-is-installed-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3235d-132">Microsoft SQL Server Reporting Services serviço compartilhado do SharePoint está instalado lado a lado &#40;o supervisor de atualização&#41;</span><span class="sxs-lookup"><span data-stu-id="3235d-132">Microsoft SQL Server Reporting Services SharePoint Shared Service is Installed Side by Side &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/sql-server-reporting-services-sharepoint-shared-service-side-by-side-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3235d-133">&#40;do supervisor de atualização do Mecanismo de Banco de Dados incompatível&#41;</span><span class="sxs-lookup"><span data-stu-id="3235d-133">Incompatible Database Engine Server Collation &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/incompatible-database-engine-server-collation-upgrade-advisor.md)  
  
-   [<span data-ttu-id="3235d-134">Outros problemas de atualização do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="3235d-134">Other Reporting Services Upgrade Issues</span></span>](../../../2014/sql-server/install/other-reporting-services-upgrade-issues.md)  
  
  
