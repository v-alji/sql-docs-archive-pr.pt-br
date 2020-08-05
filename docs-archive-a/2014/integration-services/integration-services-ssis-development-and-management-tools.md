---
title: Ambientes Integration Services (SSIS) e Studio | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- studio environments [Integration Services]
- tools [Integration Services], Business Intelligence Development Studio
- Business Intelligence Development Studio, Integration Services in
- SQL Server Management Studio [Integration Services]
- SSIS, studio environments
- SQL Server Integration Services, studio environments
- tools [Integration Services], SQL Server Management Studio
ms.assetid: 4eb73e65-d9f3-4ac6-a408-abfa85afc537
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bfe0cf7ef482dce3870db8c730c597daf1d539e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574175"
---
# <a name="integration-services-ssis-and-studio-environments"></a><span data-ttu-id="1eaea-102">SSIS (Integration Services) e Studio Environments</span><span class="sxs-lookup"><span data-stu-id="1eaea-102">Integration Services (SSIS) and Studio Environments</span></span>
  [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="1eaea-103">inclui dois estúdios para o trabalho com [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="1eaea-103">includes two studios for working with [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="1eaea-104">O[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para desenvolver os pacotes do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] exigidos por uma solução comercial.</span><span class="sxs-lookup"><span data-stu-id="1eaea-104">[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] for developing the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages that a business solution requires.</span></span> <span data-ttu-id="1eaea-105">O[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] fornece o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no qual você cria pacotes.</span><span class="sxs-lookup"><span data-stu-id="1eaea-105">[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] provides the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in which you create packages.</span></span>  
  
-   <span data-ttu-id="1eaea-106">O[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para gerenciar pacotes em um ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="1eaea-106">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] for managing packages in a production environment.</span></span>  
  
## <a name="sql-server-data-tools"></a><span data-ttu-id="1eaea-107">SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="1eaea-107">SQL Server Data Tools</span></span>  
 <span data-ttu-id="1eaea-108">Trabalhando no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], você pode executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="1eaea-108">Working in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], you can perform the following tasks:</span></span>  
  
-   <span data-ttu-id="1eaea-109">Execute o Assistente de Importação e Exportação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para criar pacotes básicos que copiam dados de uma origem para um destino.</span><span class="sxs-lookup"><span data-stu-id="1eaea-109">Run the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Import and Export Wizard to create basic packages that copy data from a source to a destination.</span></span>  
  
-   <span data-ttu-id="1eaea-110">Criar pacotes que incluem fluxo de controle complexo, fluxo de dados, lógica baseada em eventos e registros.</span><span class="sxs-lookup"><span data-stu-id="1eaea-110">Create packages that include complex control flow, data flow, event-driven logic, and logging.</span></span>  
  
-   <span data-ttu-id="1eaea-111">Testar e depurar pacotes usando os recursos de solução de problemas e monitoramento no Designer [!INCLUDE[ssIS](../includes/ssis-md.md)] e os recursos de depuração do [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1eaea-111">Test and debug packages by using the troubleshooting and monitoring features in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, and the debugging features in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="1eaea-112">Criar configurações que atualizam as propriedades de pacotes e objetos de pacote em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="1eaea-112">Create configurations that update the properties of packages and package objects at run time.</span></span>  
  
-   <span data-ttu-id="1eaea-113">Criar um utilitário de implantação que pode instalar pacotes e suas dependências em outros computadores.</span><span class="sxs-lookup"><span data-stu-id="1eaea-113">Create a deployment utility that can install packages and their dependencies on other computers.</span></span>  
  
-   <span data-ttu-id="1eaea-114">Salvar cópias de pacotes no banco de dados msdb do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], no Repositório de Pacotes do [!INCLUDE[ssIS](../includes/ssis-md.md)] e no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="1eaea-114">Save copies of packages to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] msdb database, the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Store, and the file system.</span></span>  
  
 <span data-ttu-id="1eaea-115">Para obter mais informações sobre o [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], consulte [SQL Server Data Tools](https://msdn.microsoft.com/library/hh272686.aspx).</span><span class="sxs-lookup"><span data-stu-id="1eaea-115">For more information about [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], see [SQL Server Data Tools](https://msdn.microsoft.com/library/hh272686.aspx).</span></span>  
  
## <a name="sql-server-management-studio"></a><span data-ttu-id="1eaea-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1eaea-116">SQL Server Management Studio</span></span>  
 <span data-ttu-id="1eaea-117">O[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] fornece o serviço [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que você usa para gerenciar pacotes, monitorar pacotes em execução e determinar o impacto e a linhagem de dados para objetos [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] e [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1eaea-117">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] provides the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service that you use to manage packages, monitor running packages, and determine impact and data lineage for [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects.</span></span>  
  
 <span data-ttu-id="1eaea-118">Trabalhando no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], você pode executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="1eaea-118">Working in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], you can perform the following tasks:</span></span>  
  
-   <span data-ttu-id="1eaea-119">Criar pastas para organizar pacotes de modo que faça sentido para sua organização.</span><span class="sxs-lookup"><span data-stu-id="1eaea-119">Create folders to organize packages in a way that is meaningful to your organization.</span></span>  
  
-   <span data-ttu-id="1eaea-120">Executar pacotes que são armazenados no computador local usando o utilitário Executar Pacote.</span><span class="sxs-lookup"><span data-stu-id="1eaea-120">Run packages that are stored on the local computer by using the Execute Package utility.</span></span>  
  
-   <span data-ttu-id="1eaea-121">Executar o Utilitário de Execução de Pacotes para gerar uma linha de comando a ser usada quando o utilitário de prompt de comando **dtexec** for executado (dtexec.exe).</span><span class="sxs-lookup"><span data-stu-id="1eaea-121">Run the Execute Package utility to generate a command line to use when you run the **dtexec** command prompt utility (dtexec.exe).</span></span>  
  
-   <span data-ttu-id="1eaea-122">Importar e exportar pacotes do banco de dados msdb do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], do Repositório de Pacotes [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1eaea-122">Import and export packages to and from the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] msdb database, the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Store, and the file system.</span></span>  
  
