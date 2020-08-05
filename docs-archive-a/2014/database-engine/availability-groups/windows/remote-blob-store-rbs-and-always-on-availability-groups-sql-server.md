---
title: RBS (Remote BLOB Store) e Grupos de Disponibilidade AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
ms.assetid: 01a70258-d4fd-40bc-bc44-c490b5d6c420
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f12a11162d286731b2b510a9051183e6c3025b2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571611"
---
# <a name="remote-blob-store-rbs-and-alwayson-availability-groups-sql-server"></a><span data-ttu-id="1919d-102">RBS (Remote Blob Store) e grupos de disponibilidade AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1919d-102">Remote Blob Store (RBS) and AlwaysOn Availability Groups (SQL Server)</span></span>
  [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]<span data-ttu-id="1919d-103">o pode fornecer uma solução de alta disponibilidade e recuperação de desastre para objetos de blob do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [RBS (Remote BLOB Store)](../../../relational-databases/blob/remote-blob-store-rbs-sql-server.md) .</span><span class="sxs-lookup"><span data-stu-id="1919d-103">can provide a high-availability and disaster recovery solution for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)][Remote Blob Store (RBS)](../../../relational-databases/blob/remote-blob-store-rbs-sql-server.md) BLOB objects (blobs).</span></span> [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] <span data-ttu-id="1919d-104">protege quaisquer esquemas e metadados RBS armazenados em um banco de dados de disponibilidade replicando-os para as réplicas secundárias.</span><span class="sxs-lookup"><span data-stu-id="1919d-104">protects any RBS metadata and schemas stored in an availability database by replicating them to the secondary replicas.</span></span> <span data-ttu-id="1919d-105">Esse é o banco de dados de conteúdo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1919d-105">This is the SharePoint Content Database.</span></span> <span data-ttu-id="1919d-106">Em linhas gerais, o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] armazena esses metadados RBS independentemente do blob.</span><span class="sxs-lookup"><span data-stu-id="1919d-106">Generally speaking, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] stores this RBS metadata independently from the blob.</span></span>  
  
 <span data-ttu-id="1919d-107">A proteção para dados BLOB RBD depende do local do repositório de BLOB:</span><span class="sxs-lookup"><span data-stu-id="1919d-107">The protection for RBD BLOB data depends on the BLOB Store Location, as follows:</span></span>  
  
|<span data-ttu-id="1919d-108">Local do repositório de BLOB</span><span class="sxs-lookup"><span data-stu-id="1919d-108">BLOB Store Location</span></span>|<span data-ttu-id="1919d-109">Os grupos de disponibilidade podem proteger esses dados BLOB?</span><span class="sxs-lookup"><span data-stu-id="1919d-109">Can Availability Groups Protect This BLOB Data?</span></span>|  
|-------------------------|-----------------------------------------------------|  
|<span data-ttu-id="1919d-110">O mesmo banco de dados que contém os metadados RBS (armazenados por meio de um provedor remoto FILESTREAM RBS)</span><span class="sxs-lookup"><span data-stu-id="1919d-110">The same database that contains the RBS metadata  (stored using a RBS remote FILESTREAM provider)</span></span>|<span data-ttu-id="1919d-111">Sim</span><span class="sxs-lookup"><span data-stu-id="1919d-111">Yes</span></span>|  
|<span data-ttu-id="1919d-112">Outro banco de dados na mesma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (armazenado por meio de um provedor remoto FILESTREAM RBS)</span><span class="sxs-lookup"><span data-stu-id="1919d-112">Another database in the same instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (stored using a RBS remote FILESTREAM provider)</span></span>|<span data-ttu-id="1919d-113">Sim</span><span class="sxs-lookup"><span data-stu-id="1919d-113">Yes</span></span><br /><br /> <span data-ttu-id="1919d-114">Recomendamos que você coloque esse banco de dados no mesmo grupo de disponibilidade que o banco de dados que contém os metadados RBS.</span><span class="sxs-lookup"><span data-stu-id="1919d-114">We recommend that you put this database in the same availability group as the database that contains the RBS metadata.</span></span>|  
|<span data-ttu-id="1919d-115">Outro banco de dados em uma instância diferente do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (armazenado por meio de um provedor remoto FILESTREAM RBS)</span><span class="sxs-lookup"><span data-stu-id="1919d-115">Another database in a different instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (stored using a RBS remote FILESTREAM provider)</span></span>|<span data-ttu-id="1919d-116">Sim</span><span class="sxs-lookup"><span data-stu-id="1919d-116">Yes</span></span><br /><br /> <span data-ttu-id="1919d-117">Esse banco de dados deve estar em um grupo de disponibilidade separado.</span><span class="sxs-lookup"><span data-stu-id="1919d-117">This database must be in a separate availability group.</span></span>|  
|<span data-ttu-id="1919d-118">Um repositório de BLOB de terceiros</span><span class="sxs-lookup"><span data-stu-id="1919d-118">A third-party BLOB store</span></span>|<span data-ttu-id="1919d-119">Não</span><span class="sxs-lookup"><span data-stu-id="1919d-119">No</span></span><br /><br /> <span data-ttu-id="1919d-120">Para proteger esses dados BLOB, use os mecanismos de alta disponibilidade do provedor de repositório de BLOB.</span><span class="sxs-lookup"><span data-stu-id="1919d-120">To protect this BLOB data, use the high-availability mechanisms of the BLOB store provider.</span></span>|  
  
##  <a name="limitations"></a><a name="Limitations"></a> <span data-ttu-id="1919d-121">Limitações</span><span class="sxs-lookup"><span data-stu-id="1919d-121">Limitations</span></span>  
  
-   <span data-ttu-id="1919d-122">Os mantenedores do RBS precisam ser direcionados para a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="1919d-122">RBS maintainers need to be targeted on the primary replica.</span></span>  
  
##  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="1919d-123">Recomendações</span><span class="sxs-lookup"><span data-stu-id="1919d-123">Recommendations</span></span>  
  
-   <span data-ttu-id="1919d-124">Use um ouvinte de grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="1919d-124">Use an availability group listener.</span></span> <span data-ttu-id="1919d-125">Para obter mais informações, consulte [Ouvintes do grupo de disponibilidade, conectividade de cliente e failover de aplicativo &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span><span class="sxs-lookup"><span data-stu-id="1919d-125">For more information, see [Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span></span>  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="1919d-126">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="1919d-126">Related Content</span></span>  
  
-   <span data-ttu-id="1919d-127">[Maintaining Remote BLOB Store](https://msdn.microsoft.com/library/gg316773\(SQL.105\).aspx) (Mantendo o Remote BLOB Store) (nos Manuais Online do [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="1919d-127">[Maintaining Remote BLOB Store](https://msdn.microsoft.com/library/gg316773\(SQL.105\).aspx) (in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] Books Online)</span></span>  
  
-   <span data-ttu-id="1919d-128">[Running RBS Maintainer](https://blogs.msdn.com/b/sqlrbs/archive/2010/03/19/running-rbs-maintainer.aspx) (Executando o Mantenedor do RBS) (blog)</span><span class="sxs-lookup"><span data-stu-id="1919d-128">[Running RBS Maintainer](https://blogs.msdn.com/b/sqlrbs/archive/2010/03/19/running-rbs-maintainer.aspx) (blog)</span></span>  
  
-   <span data-ttu-id="1919d-129">[Configure Remote BLOB Storage (RBS) with the FILESTREAM provider (SharePoint 2010)](https://blogs.msdn.com/b/mvpawardprogram/archive/2012/04/02/configure-remote-blob-storage-rbs-with-the-filestream-provider-sharepoint-2010.aspx) (Configurar o RBS (Remote BLOB Storage) com o provedor FILESTREAM (SharePoint 2010)) (blog)</span><span class="sxs-lookup"><span data-stu-id="1919d-129">[Configure Remote BLOB Storage (RBS) with the FILESTREAM provider (SharePoint 2010)](https://blogs.msdn.com/b/mvpawardprogram/archive/2012/04/02/configure-remote-blob-storage-rbs-with-the-filestream-provider-sharepoint-2010.aspx) (blog)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1919d-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1919d-130">See Also</span></span>  
 <span data-ttu-id="1919d-131">[Conectividade de cliente AlwaysOn &#40;SQL Server&#41;](always-on-client-connectivity-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1919d-131">[AlwaysOn Client Connectivity &#40;SQL Server&#41;](always-on-client-connectivity-sql-server.md) </span></span>  
 [<span data-ttu-id="1919d-132">Remote Blob Store &#40;RBS&#41; &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1919d-132">Remote Blob Store &#40;RBS&#41; &#40;SQL Server&#41;</span></span>](../../../relational-databases/blob/remote-blob-store-rbs-sql-server.md)  
  
  
