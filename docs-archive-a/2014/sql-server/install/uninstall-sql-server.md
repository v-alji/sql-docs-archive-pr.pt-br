---
title: Desinstalar o SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: e6255f8e-a25e-4b3d-9310-c5da2f9c9333
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e72f153c28a1ccd827150eb3dddc0b52321518a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573434"
---
# <a name="uninstall-sql-server-2014"></a><span data-ttu-id="6dbf1-102">Desinstalar o SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="6dbf1-102">Uninstall SQL Server 2014</span></span>
  <span data-ttu-id="6dbf1-103">Siga os tópicos abaixo para desinstalar totalmente uma instância existente do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] e preparar o sistema de forma que possa reinstalar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6dbf1-103">Follow the topics below to uninstall an existing instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] completely, and prepare the system so that you can reinstall [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6dbf1-104">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="6dbf1-104">In This Section</span></span>  
 [<span data-ttu-id="6dbf1-105">Desinstalar uma instância existente do SQL Server &#40;instalação&#41;</span><span class="sxs-lookup"><span data-stu-id="6dbf1-105">Uninstall an Existing Instance of SQL Server &#40;Setup&#41;</span></span>](uninstall-an-existing-instance-of-sql-server-setup.md)  
 <span data-ttu-id="6dbf1-106">Este tópico descreve como desinstalar manualmente uma instância autônoma do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6dbf1-106">This topic describes how to manually uninstall a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="6dbf1-107">Desinstalar o PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="6dbf1-107">Uninstall PowerPivot for SharePoint</span></span>](uninstall-power-pivot-for-sharepoint.md)  
 <span data-ttu-id="6dbf1-108">Este tópico descreve como desinstalar manualmente o PowerPivot para SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6dbf1-108">This topic describes how to manually uninstall PowerPivot for SharePoint.</span></span>  
  
 [<span data-ttu-id="6dbf1-109">Desinstalar o Reporting Services</span><span class="sxs-lookup"><span data-stu-id="6dbf1-109">Uninstall Reporting Services</span></span>](uninstall-reporting-services.md)  
 <span data-ttu-id="6dbf1-110">Este tópico descreve como desinstalar servidores [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] para o modo do SharePoint e servidores de modo nativo.</span><span class="sxs-lookup"><span data-stu-id="6dbf1-110">This topic describes how to uninstall [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] servers for both SharePoint mode and Native mode servers.</span></span>  
  
 [<span data-ttu-id="6dbf1-111">Desinstalar e remover o Master Data Services</span><span class="sxs-lookup"><span data-stu-id="6dbf1-111">Uninstall and Remove Master Data Services</span></span>](uninstall-and-remove-master-data-services.md)  
 <span data-ttu-id="6dbf1-112">Este tópico descreve o processo de desinstalar e remover o [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] do computador local.</span><span class="sxs-lookup"><span data-stu-id="6dbf1-112">This topic describes the process of uninstalling and removing [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] from the local computer.</span></span>  
  
 [<span data-ttu-id="6dbf1-113">Remover objetos do Servidor de Qualidade de Dados</span><span class="sxs-lookup"><span data-stu-id="6dbf1-113">Remove Data Quality Server Objects</span></span>](remove-data-quality-server-objects.md)  
 <span data-ttu-id="6dbf1-114">Este tópico descreve como remover manualmente os objetos [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] após desinstalar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou apenas o componente [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] no [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="6dbf1-114">This topic describes how to manually remove the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] objects after uninstalling either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or just the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] component in [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6dbf1-115">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="6dbf1-115">Related Sections</span></span>  
  
-   [<span data-ttu-id="6dbf1-116">Remover uma Instância de Cluster de Failover do SQL Server &#40;Instalação&#41;</span><span class="sxs-lookup"><span data-stu-id="6dbf1-116">Remove a SQL Server Failover Cluster Instance &#40;Setup&#41;</span></span>](../failover-clusters/install/remove-a-sql-server-failover-cluster-instance-setup.md)  
  
-   [<span data-ttu-id="6dbf1-117">Adicionar ou remover nós em um cluster de failover do SQL Server &#40;Instalação&#41;</span><span class="sxs-lookup"><span data-stu-id="6dbf1-117">Add or Remove Nodes in a SQL Server Failover Cluster &#40;Setup&#41;</span></span>](../failover-clusters/install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md)  
  
-   [<span data-ttu-id="6dbf1-118">Remover uma instalação do SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="6dbf1-118">Drop a SQL Server 2014 Installation</span></span>](../../database-engine/install-windows/repair-a-failed-sql-server-installation.md)  
  
## <a name="see-also"></a><span data-ttu-id="6dbf1-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6dbf1-119">See Also</span></span>  
 <span data-ttu-id="6dbf1-120">[Planejando uma instalação do SQL Server](planning-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="6dbf1-120">[Planning a SQL Server Installation](planning-a-sql-server-installation.md) </span></span>  
 <span data-ttu-id="6dbf1-121">[Instalar o SQL Server 2014](../../database-engine/install-windows/install-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6dbf1-121">[Install SQL Server 2014](../../database-engine/install-windows/install-sql-server.md) </span></span>  
 [<span data-ttu-id="6dbf1-122">Atualizar para o SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="6dbf1-122">Upgrade to SQL Server 2014</span></span>](../../database-engine/install-windows/upgrade-sql-server.md)  
  
  
