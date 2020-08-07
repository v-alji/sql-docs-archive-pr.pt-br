---
title: Compatibilidade com versões anteriores | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Surface Area Configuration Tool
- command prompt [SQL Server], discontinued parameters
- discontinued functionality [SQL Server]
- compatibility [SQL Server], discontinued features
- SAC tool
- compatibility [Analysis Services]
- compatibility [Integration Services]
- SQL Server, discontinued features
- compatibility [Replication]
- compatibility [SQL Server]
- previous versions [SQL Server], (See also backward compatibility)
- backward compatibility [SQL Server]
- compatibility [Reporting Services]
- earlier versions [SQL Server], (See also backward compatibility)
ms.assetid: 15d9117e-e2fa-4985-99ea-66a117c1e9fd
author: rothja
ms.author: jroth
ms.openlocfilehash: fd8be66efd648f5b6703a76855a549a9bd30f1e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583758"
---
# <a name="backward-compatibility"></a><span data-ttu-id="af582-102">Backward Compatibility</span><span class="sxs-lookup"><span data-stu-id="af582-102">Backward Compatibility</span></span>
  <span data-ttu-id="af582-103">As seções a seguir contêm informações sobre compatibilidade com versões anteriores para componentes do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af582-103">The following sections contain backward compatibility information for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] components.</span></span> <span data-ttu-id="af582-104">Este conteúdo inclui informações sobre recursos descontinuados (substituídos), recursos suspensos, alterações que causam interrupções e alterações de comportamento.</span><span class="sxs-lookup"><span data-stu-id="af582-104">This content includes information about deprecated features, discontinued features, breaking changes, and behavior changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="af582-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="af582-105">In This Section</span></span>  
  
|<span data-ttu-id="af582-106">Tópico</span><span class="sxs-lookup"><span data-stu-id="af582-106">Topic</span></span>|<span data-ttu-id="af582-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="af582-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="af582-108">Compatibilidade com versões anteriores do SQL Server</span><span class="sxs-lookup"><span data-stu-id="af582-108">SQL Server Backward Compatibility</span></span>](../../2014/getting-started/sql-server-backward-compatibility.md)|<span data-ttu-id="af582-109">Contém tópicos que descrevem alterações no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que podem exigir que você efetue alterações em seus aplicativos.</span><span class="sxs-lookup"><span data-stu-id="af582-109">Contains topics that describe changes in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that might require you to make changes to your applications.</span></span> <span data-ttu-id="af582-110">Recursos que são incluídos nesta área de tópico incluem programabilidade de dados, ferramentas de configuração de área da superfície, Instalação, serviços [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e outras alterações amplas de funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="af582-110">Features that are included in this topic area include data programmability, surface area configuration tools, Setup, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] services, and other broad functionality changes.</span></span>|  
|[<span data-ttu-id="af582-111">Compatibilidade com versões anteriores do Mecanismo de Banco de Dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="af582-111">SQL Server Database Engine Backward Compatibility</span></span>](../database-engine/sql-server-database-engine-backward-compatibility.md)|<span data-ttu-id="af582-112">Contém tópicos que descrevem alterações do [!INCLUDE[ssDE](../includes/ssde-md.md)] no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que podem exigir que você faça alterações em seus aplicativos.</span><span class="sxs-lookup"><span data-stu-id="af582-112">Contains topics that describe [!INCLUDE[ssDE](../includes/ssde-md.md)] changes in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that might require you to make changes to your applications.</span></span>|  
|[<span data-ttu-id="af582-113">Analysis Services Backward Compatibility</span><span class="sxs-lookup"><span data-stu-id="af582-113">Analysis Services Backward Compatibility</span></span>](../../2014/analysis-services/analysis-services-backward-compatibility.md)|<span data-ttu-id="af582-114">Contém tópicos que descrevem alterações do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que podem exigir que você faça alterações em seus aplicativos.</span><span class="sxs-lookup"><span data-stu-id="af582-114">Contains topics that describe [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] changes in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that might require you to make changes to your applications.</span></span>|  
|[<span data-ttu-id="af582-115">Compatibilidade com versões anteriores do Integration Services</span><span class="sxs-lookup"><span data-stu-id="af582-115">Integration Services Backward Compatibility</span></span>](../integration-services/integration-services-backward-compatibility.md)|<span data-ttu-id="af582-116">Descreve alterações do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que podem exigir que você faça alterações em seus aplicativos DTS (Data Transformation Services) existentes.</span><span class="sxs-lookup"><span data-stu-id="af582-116">Describes [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] changes in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that might require you to make changes to your existing Data Transformation Services applications.</span></span>|  
|[<span data-ttu-id="af582-117">Compatibilidade com versões anteriores do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="af582-117">Reporting Services Backward Compatibility</span></span>](../reporting-services/reporting-services-backward-compatibility.md)|<span data-ttu-id="af582-118">Contém tópicos que descrevem alterações do [!INCLUDE[ssRS](../includes/ssrs.md)] no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que podem exigir que você faça alterações em suas soluções do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] existentes.</span><span class="sxs-lookup"><span data-stu-id="af582-118">Contains topics that describe [!INCLUDE[ssRS](../includes/ssrs.md)] changes in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that might require you to make changes to your existing [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] solutions.</span></span>|  
|[<span data-ttu-id="af582-119">&#40;de compatibilidade com versões anteriores Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="af582-119">Backward Compatibility &#40;Master Data Services&#41;</span></span>](../master-data-services/backward-compatibility-master-data-services.md)|<span data-ttu-id="af582-120">Contém tópicos que descrevem alterações do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que podem exigir que você faça alterações em suas soluções do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] existentes.</span><span class="sxs-lookup"><span data-stu-id="af582-120">Contains topics that describe [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] changes in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that might require you to make changes to your existing [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] solutions.</span></span>|  
|[<span data-ttu-id="af582-121">Compatibilidade com versões anteriores de replicação</span><span class="sxs-lookup"><span data-stu-id="af582-121">Replication Backward Compatibility</span></span>](../../2014/relational-databases/replication/replication-backward-compatibility.md)|<span data-ttu-id="af582-122">Contém tópicos que descrevem alterações do [!INCLUDE[ssDE](../includes/ssde-md.md)] no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que podem exigir que você faça alterações em suas soluções de replicação existentes.</span><span class="sxs-lookup"><span data-stu-id="af582-122">Contains topics that describe [!INCLUDE[ssDE](../includes/ssde-md.md)] changes in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that might require you to make changes to existing Replication solutions.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="af582-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="af582-123">See Also</span></span>  
 <span data-ttu-id="af582-124">[Instalar o SQL Server 2014](../database-engine/install-windows/install-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="af582-124">[Install SQL Server 2014](../database-engine/install-windows/install-sql-server.md) </span></span>  
 [<span data-ttu-id="af582-125">Atualizar para o SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="af582-125">Upgrade to SQL Server 2014</span></span>](../database-engine/install-windows/upgrade-sql-server.md)  
  
  
