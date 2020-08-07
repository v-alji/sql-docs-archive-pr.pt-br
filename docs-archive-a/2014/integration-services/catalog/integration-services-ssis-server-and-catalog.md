---
title: Servidor Integration Services (SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], managing
- managing packages [Integration Services]
ms.assetid: 6d667bba-7c25-492a-8f4d-70ebaca28f40
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a0da83cdac269499dfbde7a6387a4af4690c83ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575288"
---
# <a name="integration-services-ssis-server"></a><span data-ttu-id="3f6e5-102">Servidor do Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="3f6e5-102">Integration Services (SSIS) Server</span></span>
  <span data-ttu-id="3f6e5-103">Depois de criar e testar pacotes no [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], você pode implantar os projetos que contêm os pacotes no servidor do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3f6e5-103">After you design and test packages in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], you can deploy the projects that contain the packages to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
 <span data-ttu-id="3f6e5-104">O servidor do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] é uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que hospeda o banco de dados do `SSISDB`.</span><span class="sxs-lookup"><span data-stu-id="3f6e5-104">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server is an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the `SSISDB` database.</span></span> <span data-ttu-id="3f6e5-105">O banco de dados armazena os seguintes objetos: pacotes, projetos, parâmetros, permissões, propriedades de servidor e histórico operacional.</span><span class="sxs-lookup"><span data-stu-id="3f6e5-105">The database stores the following objects: packages, projects, parameters, permissions, server properties, and operational history.</span></span>  
  
 <span data-ttu-id="3f6e5-106">O banco de dados do `SSISDB` expõe as informações de objeto em exibições públicas que você pode consultar.</span><span class="sxs-lookup"><span data-stu-id="3f6e5-106">The `SSISDB` database exposes the object information in public views that you can query.</span></span> <span data-ttu-id="3f6e5-107">O banco de dados também fornece procedimentos armazenados que você pode chamar para gerenciar os objetos.</span><span class="sxs-lookup"><span data-stu-id="3f6e5-107">The database also provides stored procedures that you can call to manage the objects.</span></span>  
  
 <span data-ttu-id="3f6e5-108">Para poder implantar os projetos no servidor do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], você precisa criar o catálogo do `SSISDB`.</span><span class="sxs-lookup"><span data-stu-id="3f6e5-108">Before you can deploy the projects to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server, you need to create the `SSISDB` catalog.</span></span>  
  
 <span data-ttu-id="3f6e5-109">Para obter uma visão geral da funcionalidade de catálogo do SSISDB, confira [Catálogo do SSIS](ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="3f6e5-109">For an overview of the SSISDB catalog functionality, see [SSIS Catalog](ssis-catalog.md).</span></span>  
  
## <a name="high-availability"></a><span data-ttu-id="3f6e5-110">Alta disponibilidade</span><span class="sxs-lookup"><span data-stu-id="3f6e5-110">High Availability</span></span>  
 <span data-ttu-id="3f6e5-111">Como outros bancos de dados de usuários, o banco de dados `SSISDB` dá suporte a espelhamento de banco de dados e replicação.</span><span class="sxs-lookup"><span data-stu-id="3f6e5-111">Like other user databases, the `SSISDB` database does support database mirroring and replication.</span></span> <span data-ttu-id="3f6e5-112">Para obter mais informações sobre espelhamento e replicação, veja [Espelhamento de banco de dados &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3f6e5-112">For more information about mirroring and replication, see [Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md).</span></span>  
  
 <span data-ttu-id="3f6e5-113">Você também pode fornecer alta disponibilidade do SSISDB e de seu conteúdo utilizando o SSIS e grupos de disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="3f6e5-113">You can also provide high-availability of SSISDB and its contents by making use of SSIS and AlwaysOn Availability Groups.</span></span> <span data-ttu-id="3f6e5-114">Para obter mais informações, consulte a publicação deste blog de Matt Masson, [SSIS com AlwaysOn](https://go.microsoft.com/fwlink/?LinkId=255873)em blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="3f6e5-114">For more information, see this blog post by Matt Masson, [SSIS with AlwaysOn](https://go.microsoft.com/fwlink/?LinkId=255873), at blogs.msdn.com.</span></span>  
  
##  <a name="integration-services-server-in-sql-server-management-studio"></a><a name="ssms"></a><span data-ttu-id="3f6e5-115">Integration Services servidor no SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3f6e5-115">Integration Services Server in SQL Server Management Studio</span></span>  
 <span data-ttu-id="3f6e5-116">Quando você conecta a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que hospeda o banco de dados do `SSISDB`, vê os seguintes objetos no Pesquisador de Objetos:</span><span class="sxs-lookup"><span data-stu-id="3f6e5-116">When you connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the `SSISDB` database, you see the following objects in Object Explorer:</span></span>  
  
-   <span data-ttu-id="3f6e5-117">**Banco de dados SSISDB**</span><span class="sxs-lookup"><span data-stu-id="3f6e5-117">**SSISDB Database**</span></span>  
  
     <span data-ttu-id="3f6e5-118">O `SSISDB` banco de dados é exibido sob o nó **databases** no objeto Explore.</span><span class="sxs-lookup"><span data-stu-id="3f6e5-118">The `SSISDB` database appears under the **Databases** node in Object Explore.</span></span> <span data-ttu-id="3f6e5-119">Você pode consultar as exibições e chamar os procedimentos armazenados que gerenciam o servidor do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] e os objetos que estão armazenados no servidor.</span><span class="sxs-lookup"><span data-stu-id="3f6e5-119">You can query the views and call the stored procedures that manage the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server and the objects that are stored on the server.</span></span>  
  
-   <span data-ttu-id="3f6e5-120">**Catálogos do Integration Services**</span><span class="sxs-lookup"><span data-stu-id="3f6e5-120">**Integration Services Catalogs**</span></span>  
  
     <span data-ttu-id="3f6e5-121">No nó **Catálogos do Integration Services** , há pastas para projetos e ambientes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3f6e5-121">Under the **Integration Services Catalogs** node there are folders for [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] projects and environments.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="3f6e5-122">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="3f6e5-122">Related Tasks</span></span>  
  
-   [<span data-ttu-id="3f6e5-123">Criar o catálogo do SSIS</span><span class="sxs-lookup"><span data-stu-id="3f6e5-123">Create the SSIS Catalog</span></span>](../create-the-ssis-catalog.md)  
  
-   [<span data-ttu-id="3f6e5-124">Exibir a lista de pacotes no servidor do Integration Services</span><span class="sxs-lookup"><span data-stu-id="3f6e5-124">View the List of Packages on the Integration Services Server</span></span>](view-the-list-of-packages-on-the-integration-services-server.md)  
  
-   [<span data-ttu-id="3f6e5-125">Implantar projetos no servidor do Integration Services</span><span class="sxs-lookup"><span data-stu-id="3f6e5-125">Deploy Projects to Integration Services Server</span></span>](../deploy-projects-to-integration-services-server.md)  
  
-   [<span data-ttu-id="3f6e5-126">Executar um pacote no servidor SSIS usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3f6e5-126">Run a Package on the SSIS Server Using SQL Server Management Studio</span></span>](../run-a-package-on-the-ssis-server-using-sql-server-management-studio.md)  
  
## <a name="related-content"></a><span data-ttu-id="3f6e5-127">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="3f6e5-127">Related Content</span></span>  
 <span data-ttu-id="3f6e5-128">Entrada de blog [SSIS com AlwaysOn](https://go.microsoft.com/fwlink/?LinkId=255873)em blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="3f6e5-128">Blog entry, [SSIS with AlwaysOn](https://go.microsoft.com/fwlink/?LinkId=255873), at blogs.msdn.com.</span></span>  
  
  
