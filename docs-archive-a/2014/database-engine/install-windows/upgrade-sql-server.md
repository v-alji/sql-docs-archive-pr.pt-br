---
title: Atualizar para o SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- upgrading SQL Server
ms.assetid: 5064e35b-b70d-4a0b-a9e9-fff04162f9d2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 857bbd6d7269b7675653b11a9d7c0acd07927f62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680059"
---
# <a name="upgrade-to-sql-server-2014"></a><span data-ttu-id="32cb4-102">Atualizar para o SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="32cb4-102">Upgrade to SQL Server 2014</span></span>
  <span data-ttu-id="32cb4-103">Você pode atualizar instâncias do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]ou [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] para [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32cb4-103">You can upgrade instances of, [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="32cb4-104">Antes de executar a Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para atualizar para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], confira o [Guia Técnico de Atualização do SQL Server 2014](https://download.microsoft.com/download/7/1/5/715BDFA7-51B6-4D7B-AF17-61E78C7E538F/SQL_Server_2014_Upgrade_technical_guide.pdf) (download em PDF), consulte os tópicos sobre o processo de atualização nesta seção e leia as o [Notas de Versão do SQL Server 2014](https://go.microsoft.com/fwlink/?LinkID=296445).</span><span class="sxs-lookup"><span data-stu-id="32cb4-104">Before running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup to upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], check out the [SQL Server 2014 Upgrade Technical Guide](https://download.microsoft.com/download/7/1/5/715BDFA7-51B6-4D7B-AF17-61E78C7E538F/SQL_Server_2014_Upgrade_technical_guide.pdf) (PDF download), review the topics about the upgrade process in this section, and read the [SQL Server 2014 Release Notes](https://go.microsoft.com/fwlink/?LinkID=296445).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="32cb4-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="32cb4-105">In This Section</span></span>  
 <span data-ttu-id="32cb4-106">Esta seção contém os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="32cb4-106">This section contains the following topics:</span></span>  
  
-   [<span data-ttu-id="32cb4-107">Atualizações de versão e edição com suporte</span><span class="sxs-lookup"><span data-stu-id="32cb4-107">Supported Version and Edition Upgrades</span></span>](supported-version-and-edition-upgrades.md)  
  
-   [<span data-ttu-id="32cb4-108">Usar o Supervisor de Atualização para preparar para atualizações</span><span class="sxs-lookup"><span data-stu-id="32cb4-108">Use Upgrade Advisor to Prepare for Upgrades</span></span>](../../sql-server/install/use-upgrade-advisor-to-prepare-for-upgrades.md)  
  
-   [<span data-ttu-id="32cb4-109">Usar o Distributed Replay Utility para preparar para atualizações</span><span class="sxs-lookup"><span data-stu-id="32cb4-109">Use the Distributed Replay Utility to Prepare for Upgrades</span></span>](../../sql-server/install/use-the-distributed-replay-utility-to-prepare-for-upgrades.md)  
  
-   [<span data-ttu-id="32cb4-110">Atualizar o Analysis Services</span><span class="sxs-lookup"><span data-stu-id="32cb4-110">Upgrade Analysis Services</span></span>](upgrade-analysis-services.md)  
  
-   [<span data-ttu-id="32cb4-111">Atualizar o Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="32cb4-111">Upgrade Database Engine</span></span>](upgrade-database-engine.md)  
  
-   [<span data-ttu-id="32cb4-112">Atualizar o Data Quality Services</span><span class="sxs-lookup"><span data-stu-id="32cb4-112">Upgrade Data Quality Services</span></span>](upgrade-data-quality-services.md)  
  
-   [<span data-ttu-id="32cb4-113">Atualização do Integration Services</span><span class="sxs-lookup"><span data-stu-id="32cb4-113">Upgrade Integration Services</span></span>](../../integration-services/install-windows/upgrade-integration-services.md)  
  
-   [<span data-ttu-id="32cb4-114">Atualizar o Master Data Services</span><span class="sxs-lookup"><span data-stu-id="32cb4-114">Upgrade Master Data Services</span></span>](upgrade-master-data-services.md)  
  
-   [<span data-ttu-id="32cb4-115">Atualizar o PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="32cb4-115">Upgrade PowerPivot for SharePoint</span></span>](upgrade-power-pivot-for-sharepoint.md)  
  
-   [<span data-ttu-id="32cb4-116">Atualizar bancos de dados replicados</span><span class="sxs-lookup"><span data-stu-id="32cb4-116">Upgrade Replicated Databases</span></span>](../../database-engine/install-windows/upgrade-replicated-databases.md)  
  
-   [<span data-ttu-id="32cb4-117">Atualizar e migrar o Reporting Services</span><span class="sxs-lookup"><span data-stu-id="32cb4-117">Upgrade and Migrate Reporting Services</span></span>](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md)  
  
-   [<span data-ttu-id="32cb4-118">Atualizar Ferramentas de Gerenciamento do SQL Server</span><span class="sxs-lookup"><span data-stu-id="32cb4-118">Upgrade SQL Server Management Tools</span></span>](upgrade-sql-server-management-tools.md)  
  
-   [<span data-ttu-id="32cb4-119">Tópicos de informações práticas sobre atualização</span><span class="sxs-lookup"><span data-stu-id="32cb4-119">Upgrade How-to Topics</span></span>](../../../2014/sql-server/install/upgrade-how-to-topics.md)  
  
## <a name="see-also"></a><span data-ttu-id="32cb4-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="32cb4-120">See Also</span></span>  
 <span data-ttu-id="32cb4-121">[Atualizar o Mecanismo de Banco de Dados](upgrade-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="32cb4-121">[Upgrade Database Engine](upgrade-database-engine.md) </span></span>  
 <span data-ttu-id="32cb4-122">[Atualizar o Analysis Services](upgrade-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="32cb4-122">[Upgrade Analysis Services](upgrade-analysis-services.md) </span></span>  
 <span data-ttu-id="32cb4-123">[Atualizar e migrar o Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="32cb4-123">[Upgrade and Migrate Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md) </span></span>  
 <span data-ttu-id="32cb4-124">[Atualização do Integration Services](../../integration-services/install-windows/upgrade-integration-services.md) </span><span class="sxs-lookup"><span data-stu-id="32cb4-124">[Upgrade Integration Services](../../integration-services/install-windows/upgrade-integration-services.md) </span></span>  
 <span data-ttu-id="32cb4-125">[Atualizar bancos de dados replicados](../../database-engine/install-windows/upgrade-replicated-databases.md) </span><span class="sxs-lookup"><span data-stu-id="32cb4-125">[Upgrade Replicated Databases](../../database-engine/install-windows/upgrade-replicated-databases.md) </span></span>  
 <span data-ttu-id="32cb4-126">[Atualizar o Master Data Services](upgrade-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="32cb4-126">[Upgrade Master Data Services](upgrade-master-data-services.md) </span></span>  
 <span data-ttu-id="32cb4-127">[SQL Server 2012 Analisador de Práticas Recomendadas](https://www.microsoft.com/download/details.aspx?id=29302) </span><span class="sxs-lookup"><span data-stu-id="32cb4-127">[SQL Server 2012 Best Practices Analyzer](https://www.microsoft.com/download/details.aspx?id=29302) </span></span>  
 <span data-ttu-id="32cb4-128">[Analisador de Práticas Recomendadas do SQL Server 2008 R2](https://www.microsoft.com/download/details.aspx?id=436) </span><span class="sxs-lookup"><span data-stu-id="32cb4-128">[SQL Server 2008 R2 Best Practices Analyzer](https://www.microsoft.com/download/details.aspx?id=436) </span></span>  
 [<span data-ttu-id="32cb4-129">Compatibilidade com versões anteriores</span><span class="sxs-lookup"><span data-stu-id="32cb4-129">Backward Compatibility</span></span>](../../../2014/getting-started/backward-compatibility.md)  
  
  
