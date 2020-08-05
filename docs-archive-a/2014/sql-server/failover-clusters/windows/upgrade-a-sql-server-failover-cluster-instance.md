---
title: Atualizar um cluster de failover do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- upgrading failover clusters
- clusters [SQL Server], upgrading
- failover clustering [SQL Server], upgrading
ms.assetid: daac41fe-7d0b-4f14-84c2-62952ad8cbfa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ca08e83c362e714f234a60ee358df3bcb03ade93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573562"
---
# <a name="upgrade-a-sql-server-failover-cluster"></a><span data-ttu-id="6ac7d-102">Atualizar um cluster de failover do SQL Server</span><span class="sxs-lookup"><span data-stu-id="6ac7d-102">Upgrade a SQL Server Failover Cluster</span></span>
  <span data-ttu-id="6ac7d-103">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] oferece suporte à atualização do [!INCLUDE[ssDE](../../../includes/ssde-md.md)] e do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] a partir de clusters de failover do [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], do [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)], do [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] e do [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] separadamente em todos os nós de cluster de failover.</span><span class="sxs-lookup"><span data-stu-id="6ac7d-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] supports upgrade of the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] and [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] from [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)], and [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] failover clusters separately on all failover cluster nodes.</span></span>  
  
 <span data-ttu-id="6ac7d-104">Os detalhes do suporte são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="6ac7d-104">Support details are as follows:</span></span>  
  
-   <span data-ttu-id="6ac7d-105">A atualização tem suporte na interface do usuário e no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="6ac7d-105">Upgrade is supported both through the user interface and from the command prompt.</span></span> <span data-ttu-id="6ac7d-106">Para obter mais informações, consulte [Atualizar uma instância de cluster de failover do SQL Server &#40;Instalação&#41;](upgrade-a-sql-server-failover-cluster-instance-setup.md) e [Instalar o SQL Server 2014 do prompt de comando](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="6ac7d-106">For more information, see [Upgrade a SQL Server Failover Cluster Instance &#40;Setup&#41;](upgrade-a-sql-server-failover-cluster-instance-setup.md) and [Install SQL Server 2014 from the Command Prompt](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span></span>  
  
-   <span data-ttu-id="6ac7d-107">Atualizando de [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] – você pode executar a atualização do prompt de comando em cada nó de cluster de failover ou usando a interface do usuário de instalação para atualizar cada nó de cluster.</span><span class="sxs-lookup"><span data-stu-id="6ac7d-107">Upgrading from [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] - You can run upgrade from the command prompt on each failover cluster node, or by using the Setup UI to upgrade each cluster node.</span></span> <span data-ttu-id="6ac7d-108">Se os recursos de pesquisa de texto completo e de Replicação não existirem na instância que está sendo atualizada, eles serão instalados automaticamente sem a opção para omiti-los.</span><span class="sxs-lookup"><span data-stu-id="6ac7d-108">If Full-text search and Replication features do not exist on the instance being upgraded, they will be installed automatically with no option to omit them.</span></span>  
  
-   <span data-ttu-id="6ac7d-109">Instalação de service pack: você deve aplicar service packs e patches do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para os clusters de failover do [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] separadamente em todos os nós.</span><span class="sxs-lookup"><span data-stu-id="6ac7d-109">Service pack installation - you must apply [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service packs and patches to [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] failover clusters separately on all nodes.</span></span>  
  
-   <span data-ttu-id="6ac7d-110">Os cenários a seguir não têm suporte:</span><span class="sxs-lookup"><span data-stu-id="6ac7d-110">The following scenarios are not supported:</span></span>  
  
    -   <span data-ttu-id="6ac7d-111">Não é possível migrar de uma instância autônoma do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para um cluster de failover.</span><span class="sxs-lookup"><span data-stu-id="6ac7d-111">You cannot migrate from a stand-alone instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to a failover cluster.</span></span>  
  
    -   <span data-ttu-id="6ac7d-112">Adicionar recursos a um cluster de failover.</span><span class="sxs-lookup"><span data-stu-id="6ac7d-112">Add features to a failover cluster.</span></span> <span data-ttu-id="6ac7d-113">Por exemplo, você não pode adicionar o [!INCLUDE[ssDE](../../../includes/ssde-md.md)] a um cluster de failover somente do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6ac7d-113">For example, you cannot add the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] to an existing [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]-only failover cluster.</span></span>  
  
    -   <span data-ttu-id="6ac7d-114">Você não pode fazer downgrade do nó de cluster de failover para uma instância autônoma.</span><span class="sxs-lookup"><span data-stu-id="6ac7d-114">You cannot downgrade a failover cluster node to a stand-alone instance.</span></span>  
  
-   <span data-ttu-id="6ac7d-115">Para obter mais informações, consulte [Instâncias do Cluster de Failover do AlwaysOn (SQL Server)](always-on-failover-cluster-instances-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6ac7d-115">For more information, see [AlwaysOn Failover Cluster Instances (SQL Server)](always-on-failover-cluster-instances-sql-server.md).</span></span>  
  
## <a name="upgrading-a-ssnoversion-multi-subnet-failover-cluster"></a><span data-ttu-id="6ac7d-116">Atualizando um cluster de failover de várias sub-redes do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ac7d-116">Upgrading a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Multi-Subnet Failover Cluster</span></span>  
 <span data-ttu-id="6ac7d-117">Não é possível atualizar diretamente um cluster de failover que não seja de várias sub-redes [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para um [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] cluster de failover de várias sub-redes.</span><span class="sxs-lookup"><span data-stu-id="6ac7d-117">You cannot directly upgrade a non-multi-subnet [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover cluster to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] multi-subnet failover cluster.</span></span> <span data-ttu-id="6ac7d-118">Para obter mais informações, consulte [Atualizar uma instância de cluster de failover do SQL Server &#40;instalação&#41;](upgrade-a-sql-server-failover-cluster-instance-setup.md).</span><span class="sxs-lookup"><span data-stu-id="6ac7d-118">For more information, see [Upgrade a SQL Server Failover Cluster Instance &#40;Setup&#41;](upgrade-a-sql-server-failover-cluster-instance-setup.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ac7d-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6ac7d-119">See Also</span></span>  
 <span data-ttu-id="6ac7d-120">[Atualizações de versão e edição com suporte](../../../database-engine/install-windows/supported-version-and-edition-upgrades.md) </span><span class="sxs-lookup"><span data-stu-id="6ac7d-120">[Supported Version and Edition Upgrades](../../../database-engine/install-windows/supported-version-and-edition-upgrades.md) </span></span>  
 <span data-ttu-id="6ac7d-121">[Atualizar uma instância de cluster de failover SQL Server &#40;instalação&#41;](upgrade-a-sql-server-failover-cluster-instance-setup.md) </span><span class="sxs-lookup"><span data-stu-id="6ac7d-121">[Upgrade a SQL Server Failover Cluster Instance &#40;Setup&#41;](upgrade-a-sql-server-failover-cluster-instance-setup.md) </span></span>  
 [<span data-ttu-id="6ac7d-122">Install SQL Server 2014 from the Command Prompt</span><span class="sxs-lookup"><span data-stu-id="6ac7d-122">Install SQL Server 2014 from the Command Prompt</span></span>](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md)  
  
  
