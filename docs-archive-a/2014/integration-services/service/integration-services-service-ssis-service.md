---
title: Serviço SSIS (Serviço Integration Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services service, about Integration Services service
- SQL Server Integration Services service
- service [Integration Services],about Integration Services service
- service [Integration Services]
- SQL Server Integration Services, service
ms.assetid: 2c785b3b-4a0c-4df7-b5cd-23756dc87842
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 04b24f0f0d54009c50654904d606a208504f229c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685841"
---
# <a name="integration-services-service-ssis-service"></a><span data-ttu-id="81c51-102">Serviço do Integration Services (Serviço SSIS)</span><span class="sxs-lookup"><span data-stu-id="81c51-102">Integration Services Service (SSIS Service)</span></span>
  <span data-ttu-id="81c51-103">Os tópicos desta seção discutem o serviço [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , um serviço do Windows para gerenciamento de pacotes [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81c51-103">The topics in this section discuss the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="81c51-104">Este serviço não é exigido para criar, salvar e executar pacotes do Integration Services.</span><span class="sxs-lookup"><span data-stu-id="81c51-104">This service is not required to create, save, and run Integration Services packages.</span></span> [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] <span data-ttu-id="81c51-105">dá suporte ao serviço [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] para compatibilidade com versões anteriores do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81c51-105">supports the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="81c51-106">A partir do [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] armazena objetos, configurações e dados operacionais no `SSISDB` Database para projetos que você implantou no [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] servidor usando o modelo de implantação de projeto.</span><span class="sxs-lookup"><span data-stu-id="81c51-106">Starting in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] stores objects, settings, and operational data in the `SSISDB` database for projects that you've deployed to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server using the project deployment model.</span></span> <span data-ttu-id="81c51-107">O servidor do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , que é uma instância do Mecanismo de Banco de Dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , hospeda o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="81c51-107">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server, which is an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Database Engine, hosts the database.</span></span> <span data-ttu-id="81c51-108">Para obter mais informações sobre o banco de dados, consulte [Catálogo do SSIS](../catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="81c51-108">For more information about the database, see [SSIS Catalog](../catalog/ssis-catalog.md).</span></span> <span data-ttu-id="81c51-109">Para obter mais informações sobre implantação de projetos no servidor do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , consulte [Implantar projetos no servidor do Integration Services](../deploy-projects-to-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="81c51-109">For more information about deploying projects to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server, see [Deploy Projects to Integration Services Server](../deploy-projects-to-integration-services-server.md).</span></span>  
  
## <a name="management-capabilities"></a><span data-ttu-id="81c51-110">Recursos de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="81c51-110">Management Capabilities</span></span>  
 <span data-ttu-id="81c51-111">O serviço [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] é um serviço Windows para gerenciamento de pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81c51-111">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is a Windows service for managing [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="81c51-112">O serviço [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] está disponível apenas no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81c51-112">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is available only in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="81c51-113">A execução do serviço [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] fornece os seguintes recursos de gerenciamento:</span><span class="sxs-lookup"><span data-stu-id="81c51-113">Running the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service provides the following management capabilities:</span></span>  
  
-   <span data-ttu-id="81c51-114">Início dos pacotes armazenados local e remoto</span><span class="sxs-lookup"><span data-stu-id="81c51-114">Starting remote and locally stored packages</span></span>  
  
-   <span data-ttu-id="81c51-115">Interrupção dos pacotes em execução local e remoto</span><span class="sxs-lookup"><span data-stu-id="81c51-115">Stopping remote and locally running packages</span></span>  
  
-   <span data-ttu-id="81c51-116">Monitoramento dos pacotes em execução local e remoto.</span><span class="sxs-lookup"><span data-stu-id="81c51-116">Monitoring remote and locally running packages</span></span>  
  
-   <span data-ttu-id="81c51-117">Importação e exportação de pacotes</span><span class="sxs-lookup"><span data-stu-id="81c51-117">Importing and exporting packages</span></span>  
  
-   <span data-ttu-id="81c51-118">Gerenciamento do armazenamento de pacotes</span><span class="sxs-lookup"><span data-stu-id="81c51-118">Managing package storage</span></span>  
  
-   <span data-ttu-id="81c51-119">Personalização das pastas de armazenamento</span><span class="sxs-lookup"><span data-stu-id="81c51-119">Customizing storage folders</span></span>  
  
-   <span data-ttu-id="81c51-120">Interrupção de pacotes em execução quando o serviço é interrompido</span><span class="sxs-lookup"><span data-stu-id="81c51-120">Stopping running packages when the service is stopped</span></span>  
  
-   <span data-ttu-id="81c51-121">Exibição do log de Eventos do Windows</span><span class="sxs-lookup"><span data-stu-id="81c51-121">Viewing the Windows Event log</span></span>  
  
-   <span data-ttu-id="81c51-122">Conectar-se a vários servidores [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81c51-122">Connecting to multiple [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] servers</span></span>  
  
## <a name="startup-type-for-integration-services-service"></a><span data-ttu-id="81c51-123">Tipo de inicialização do serviço Integration Services</span><span class="sxs-lookup"><span data-stu-id="81c51-123">Startup Type for Integration Services Service</span></span>  
 <span data-ttu-id="81c51-124">O serviço [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] é instalado quando você instala o componente do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81c51-124">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is installed when you install the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] component of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="81c51-125">Por padrão, o serviço [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] é iniciado e o tipo de inicialização do serviço é definido como automático.</span><span class="sxs-lookup"><span data-stu-id="81c51-125">By default, the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is started and the startup type of the service is set to automatic.</span></span> <span data-ttu-id="81c51-126">O serviço deve estar em execução para monitorar os pacotes armazenados no Repositório de Pacotes do [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81c51-126">The service must be running to monitor the packages that are stored in the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Store.</span></span> <span data-ttu-id="81c51-127">O Repositório de Pacotes [!INCLUDE[ssIS](../../includes/ssis-md.md)] pode estar no banco de dados msdb em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou nas pastas designadas no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="81c51-127">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Store can be either the msdb database in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or the designated folders in the file system.</span></span>  
  
 <span data-ttu-id="81c51-128">O serviço [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] não será necessário se você só quiser projetar e executar pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81c51-128">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is not required if you only want to design and execute [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="81c51-129">Porém, o serviço é necessário para listar e monitorar pacotes usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81c51-129">However, the service is required to list and monitor packages using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="81c51-130">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="81c51-130">Related Tasks</span></span>  
  
-   [<span data-ttu-id="81c51-131">Definir as propriedades do serviço do Integration Services</span><span class="sxs-lookup"><span data-stu-id="81c51-131">Set the Properties of the Integration Services Service</span></span>](../set-the-properties-of-the-integration-services-service.md)  
  
-   [<span data-ttu-id="81c51-132">Exibir eventos para o serviço do Integration Services</span><span class="sxs-lookup"><span data-stu-id="81c51-132">View Events for the Integration Services Service</span></span>](../view-events-for-the-integration-services-service.md)  
  
  
