---
title: FILESTREAM e Filetable com Grupos de Disponibilidade AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], Availability Groups
- FILESTREAM [SQL Server], Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: fdceda9a-a9db-4d1d-8745-345992164a98
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e7de7b4d66890bb5f1fe49799844f666de81f4db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573280"
---
# <a name="filestream-and-filetable-with-alwayson-availability-groups-sql-server"></a><span data-ttu-id="b401a-102">FILESTREAM e FileTable com grupos de disponibilidade AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b401a-102">FILESTREAM and FileTable with AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="b401a-103">Este tópico contém informações sobre como o usar os recursos FILESTREAM e FileTable com o [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b401a-103">This topic contains information about the using the FILESTREAM and FileTable features with [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="b401a-104">Todas as funcionalidades FILESTREAM têm suporte.</span><span class="sxs-lookup"><span data-stu-id="b401a-104">All FILESTREAM functionality is supported.</span></span> <span data-ttu-id="b401a-105">Depois de um failover, os dados de FILESTREAM podem ser acessados em ambas as réplicas secundárias legíveis e no novo primário.</span><span class="sxs-lookup"><span data-stu-id="b401a-105">After a failover, FILESTREAM data is accessible on both readable secondary replicas and on the new primary.</span></span>  
  
 <span data-ttu-id="b401a-106">A funcionalidade FileTable tem suporte parcial.</span><span class="sxs-lookup"><span data-stu-id="b401a-106">FileTable functionality is partially supported.</span></span> <span data-ttu-id="b401a-107">Depois de um failover, os dados de FileTable estarão acessíveis na réplica primária, mas os dados de FileTable não estarão acessíveis em réplicas secundárias legíveis.</span><span class="sxs-lookup"><span data-stu-id="b401a-107">After a failover, FileTable data is accessible on the primary replica, but FileTable data is not accessible on readable secondary replicas.</span></span>  
  
 <span data-ttu-id="b401a-108">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="b401a-108">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="b401a-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="b401a-109">Prerequisites</span></span>](#Prerequisites)  
  
-   [<span data-ttu-id="b401a-110">Usando VNNs (nomes de rede virtual) para acesso FILESTREAM e FileTable</span><span class="sxs-lookup"><span data-stu-id="b401a-110">Using Virtual Network Names (VNNs) for FILESTREAM and FileTable Access</span></span>](#vnn)  
  
-   [<span data-ttu-id="b401a-111">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="b401a-111">Related Tasks</span></span>](#RelatedTasks)  
  
-   [<span data-ttu-id="b401a-112">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="b401a-112">Related Content</span></span>](#RelatedContent)  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="b401a-113">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="b401a-113">Prerequisites</span></span>  
  
-   <span data-ttu-id="b401a-114">Antes de adicionar um banco de dados que usa FILESTREAM, com ou sem FileTable, a um grupo de disponibilidade, verifique se o FILESTREAM está habilitado em toda instância de servidor que hospeda uma réplica de disponibilidade do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="b401a-114">Before adding a database that uses FILESTREAM, with or without FileTable, to an availability group, ensure that FILESTREAM is enabled on every server instance that hosts an availability replica for the availability group.</span></span> <span data-ttu-id="b401a-115">Para obter mais informações, consulte [Enable and Configure FILESTREAM](../../../relational-databases/blob/enable-and-configure-filestream.md).</span><span class="sxs-lookup"><span data-stu-id="b401a-115">For more information, see [Enable and Configure FILESTREAM](../../../relational-databases/blob/enable-and-configure-filestream.md).</span></span>  
  
##  <a name="using-virtual-network-names-vnns-for-filestream-and-filetable-access"></a><a name="vnn"></a><span data-ttu-id="b401a-116">Usando VNNs (nomes de rede virtual) para acesso de FILESTREAM e Filetable</span><span class="sxs-lookup"><span data-stu-id="b401a-116">Using Virtual Network Names (VNNs) for FILESTREAM and FileTable Access</span></span>  
 <span data-ttu-id="b401a-117">Ao habilitar o FILESTREAM em uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], um compartilhamento de nível de instância é criado para fornecer acesso aos dados FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="b401a-117">When you enable FILESTREAM on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], an instance-level share is created to provide access to the FILESTREAM data.</span></span> <span data-ttu-id="b401a-118">Você acessa esse compartilhamento usando o nome do computador no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="b401a-118">You access this share by using the computer name in the following format:</span></span>  
  
 `\\<computer_name>\<filestream_share_name>`  
  
 <span data-ttu-id="b401a-119">Em um grupo de disponibilidade AlwaysOn, porém, o nome do computador é virtualizado usando um nome de rede virtual ou VNN.</span><span class="sxs-lookup"><span data-stu-id="b401a-119">In an AlwaysOn availability group, however, the name of the computer is virtualized by using a Virtual Network Name, or VNN.</span></span> <span data-ttu-id="b401a-120">Quando o computador for a réplica primária em um grupo de disponibilidade, e os bancos de dados do grupo de disponibilidade contiverem dados FILESTREAM, um compartilhamento de escopo definido por VNN também será criado para fornecer acesso aos dados FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="b401a-120">When the computer is the primary replica in an availability group, and databases in the availability group contain FILESTREAM data, then a VNN-scoped share is also created to provide access to the FILESTREAM data.</span></span> <span data-ttu-id="b401a-121">Isso não afeta o acesso do Transact-SQL aos dados FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="b401a-121">This does not affect Transact-SQL access to FILESTREAM data.</span></span> <span data-ttu-id="b401a-122">No entanto, os aplicativos que usam as APIs do sistema de arquivos têm de usar o compartilhamento de escopo definido por VNN, que tem um caminho no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="b401a-122">However applications that use file system APIs have to use the VNN-scoped share, which has a path in the following format:</span></span>  
  
 `\\<VNN>\<filestream_share_name>`  
  
 <span data-ttu-id="b401a-123">Esse compartilhamento de escopo definido por VNN é criado quando ocorre um dos eventos a seguir.</span><span class="sxs-lookup"><span data-stu-id="b401a-123">This VNN-scoped share is created when one of the following events occurs.</span></span>  
  
-   <span data-ttu-id="b401a-124">Você adiciona um banco de dados que contém dados FILESTREAM a um grupo de disponibilidade AlwaysOn na réplica primária:</span><span class="sxs-lookup"><span data-stu-id="b401a-124">You add a database that contains FILESTREAM data to an AlwaysOn availability group on the primary replica.</span></span> <span data-ttu-id="b401a-125">Nesse caso, o compartilhamento `\\<computer_name>\<filestream_share_name>` já existe.</span><span class="sxs-lookup"><span data-stu-id="b401a-125">In this case, the share `\\<computer_name>\<filestream_share_name>` already exists.</span></span> <span data-ttu-id="b401a-126">O compartilhamento `\\<VNN>\<filestream_share_name>` será criado.</span><span class="sxs-lookup"><span data-stu-id="b401a-126">The share `\\<VNN>\<filestream_share_name>` is created.</span></span>  
  
-   <span data-ttu-id="b401a-127">Você habilita o FILESTREAM para acesso de transmissão de E/S de arquivos em uma réplica primária com grupos de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="b401a-127">You enable FILESTREAM for file i/o streaming access on a primary replica that has availability groups.</span></span> <span data-ttu-id="b401a-128">Os seguintes compartilhamentos serão criados:</span><span class="sxs-lookup"><span data-stu-id="b401a-128">The following shares are created:</span></span>  
  
    1.  `\\<computer_name>\<filestream_share_name>`  
  
    2.  <span data-ttu-id="b401a-129">`\\<VNN1>\<filestream_share_name>` para o grupo de disponibilidade 1.</span><span class="sxs-lookup"><span data-stu-id="b401a-129">`\\<VNN1>\<filestream_share_name>` for availability group 1.</span></span>  
  
    3.  <span data-ttu-id="b401a-130">`\\<VNN2>\<filestream_share_name>` para o grupo de disponibilidade 2.</span><span class="sxs-lookup"><span data-stu-id="b401a-130">`\\<VNN2>\<filestream_share_name>` for availability group 2.</span></span>  
  
 <span data-ttu-id="b401a-131">Esses compartilhamentos de escopo definido por VNN também serão propagados para todas as réplicas secundárias.</span><span class="sxs-lookup"><span data-stu-id="b401a-131">These VNN-scoped shares are also propagated to all secondary replicas.</span></span>  
  
 <span data-ttu-id="b401a-132">Quando o banco de dados que contém dados FILESTREAM ou FileTable pertence a um grupo de disponibilidade AlwaysOn:</span><span class="sxs-lookup"><span data-stu-id="b401a-132">When the database that contains FILESTREAM or FileTable data belongs to an AlwaysOn availability group:</span></span>  
  
-   <span data-ttu-id="b401a-133">As funções FILESTREAM e FileTable aceitam ou retornam VNNs (nomes de rede virtual) em vez de nomes de computadores.</span><span class="sxs-lookup"><span data-stu-id="b401a-133">The FILESTREAM and FileTable functions accept or return virtual network names (VNNs) instead of computer names.</span></span> <span data-ttu-id="b401a-134">Para obter mais informações sobre essas funções, veja [Funções Filestream e FileTable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/filestream-and-filetable-functions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b401a-134">For more information about these functions, see [Filestream and FileTable Functions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/filestream-and-filetable-functions-transact-sql).</span></span>  
  
-   <span data-ttu-id="b401a-135">Todo o acesso aos dados FILESTREAM ou FileTable pelas APIs do sistema de arquivos deve usar VNNs em vez de nomes de computadores.</span><span class="sxs-lookup"><span data-stu-id="b401a-135">All access to FILESTREAM or FileTable data through the file system APIs should use VNNs instead of computer names.</span></span>  
  
 <span data-ttu-id="b401a-136">Se seu aplicativo tentar acessar o compartilhamento usando o nome do computador no formato `\\<computer_name>\<filestream_share_name>` quando o banco de dados fizer parte de um grupo de disponibilidade, ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="b401a-136">If your application tries to access the share by using the computer name in the format `\\<computer_name>\<filestream_share_name>` when the database is part of an availability group, then an error is raised.</span></span>  
  
 <span data-ttu-id="b401a-137">Se seu aplicativo tentar acessar o compartilhamento usando o caminho de escopo definido por VNN quando o banco de dados não fizer parte de um grupo de disponibilidade, a solicitação poderá ser bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="b401a-137">If your application tries to access the share by using a VNN-scoped path when the database is not part of an availability group, then the request may succeed.</span></span> <span data-ttu-id="b401a-138">Nesse caso, o nome de rede virtual será resolvido como nome do computador.</span><span class="sxs-lookup"><span data-stu-id="b401a-138">In this case, the virtual network name is resolved to the computer name.</span></span> <span data-ttu-id="b401a-139">No entanto, esse uso não é recomendado, pois o caminho de escopo definido por VNN deixará de funcionar se o grupo de disponibilidade for descartado.</span><span class="sxs-lookup"><span data-stu-id="b401a-139">However this usage is strongly discouraged, since the VNN-scoped path will stop working if the availability group is dropped.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="b401a-140">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="b401a-140">Related Tasks</span></span>  
  
-   [<span data-ttu-id="b401a-141">Habilitar e configurar o FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="b401a-141">Enable and Configure FILESTREAM</span></span>](../../../relational-databases/blob/enable-and-configure-filestream.md)  
  
-   [<span data-ttu-id="b401a-142">Habilitar os pré-requisitos para o FileTable</span><span class="sxs-lookup"><span data-stu-id="b401a-142">Enable the Prerequisites for FileTable</span></span>](../../../relational-databases/blob/enable-the-prerequisites-for-filetable.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="b401a-143">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="b401a-143">Related Content</span></span>  
 <span data-ttu-id="b401a-144">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="b401a-144">None.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b401a-145">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b401a-145">See Also</span></span>  
 [<span data-ttu-id="b401a-146">Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b401a-146">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
