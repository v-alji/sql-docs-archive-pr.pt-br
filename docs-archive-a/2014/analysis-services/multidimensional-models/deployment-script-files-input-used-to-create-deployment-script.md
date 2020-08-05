---
title: Noções básicas sobre os arquivos de entrada usados para criar o script de implantação | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- input files [Analysis Services]
- Analysis Services Deployment Wizard, scripts
- deploying [Analysis Services], input files
- Analysis Services Deployment Wizard, input files
- scripts [Analysis Services], deployment
- Analysis Services deployments, input files
- modifying input files
ms.assetid: 20e080cd-6a0e-4591-b022-ea4cd3638e36
author: minewiskan
ms.author: owend
ms.openlocfilehash: 34695993d4f153c6c0b97fef744d92c682517c99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574382"
---
# <a name="understanding-the-input-files-used-to-create-the-deployment-script"></a><span data-ttu-id="d8050-102">Compreendendo os arquivos de entrada usados para criar o script de implantação</span><span class="sxs-lookup"><span data-stu-id="d8050-102">Understanding the Input Files Used to Create the Deployment Script</span></span>
  <span data-ttu-id="d8050-103">Quando você cria um [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projeto [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] do, o gera arquivos XML para o projeto.</span><span class="sxs-lookup"><span data-stu-id="d8050-103">When you build a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] generates XML files for the project.</span></span> <span data-ttu-id="d8050-104">O [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] coloca esses arquivos XML na pasta de saída do projeto [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8050-104">[!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] puts these XML files in the Output folder of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="d8050-105">Por padrão, a saída está fora na pasta \Lixeira.</span><span class="sxs-lookup"><span data-stu-id="d8050-105">By default output is out in the \Bin folder.</span></span> <span data-ttu-id="d8050-106">A tabela a seguir lista os arquivos XML criados pelo [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8050-106">The following table lists the XML files that [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] creates.</span></span>  
  
|<span data-ttu-id="d8050-107">Arquivo XMLA</span><span class="sxs-lookup"><span data-stu-id="d8050-107">XMLA file</span></span>|<span data-ttu-id="d8050-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="d8050-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d8050-109">\<*project name*>. asdatabase</span><span class="sxs-lookup"><span data-stu-id="d8050-109">\<*project name*>.asdatabase</span></span>|<span data-ttu-id="d8050-110">Contém as definições declarativas para todos os objetos do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] no projeto.</span><span class="sxs-lookup"><span data-stu-id="d8050-110">Contains the declarative definitions for all the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects in the project.</span></span>|  
|<span data-ttu-id="d8050-111">\<*project name*>. deploymenttargets</span><span class="sxs-lookup"><span data-stu-id="d8050-111">\<*project name*>.deploymenttargets</span></span>|<span data-ttu-id="d8050-112">Contém o nome da instância e do banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] em que os objetos do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] serão criados.</span><span class="sxs-lookup"><span data-stu-id="d8050-112">Contains the name of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and database in which the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects will be created.</span></span>|  
|<span data-ttu-id="d8050-113">\<*project name*>. configsettings</span><span class="sxs-lookup"><span data-stu-id="d8050-113">\<*project name*>.configsettings</span></span>|<span data-ttu-id="d8050-114">Contém configurações específicas do ambiente, como informações de conexão de fonte de dados e locais de armazenamento de objeto.</span><span class="sxs-lookup"><span data-stu-id="d8050-114">Contains environment specific settings, such as data source connection information and object storage locations.</span></span> <span data-ttu-id="d8050-115">As configurações nesse arquivo substituem as configurações no \<*project name*> arquivo. asdatabase.</span><span class="sxs-lookup"><span data-stu-id="d8050-115">Settings in this file override settings in the \<*project name*>.asdatabase file.</span></span>|  
|<span data-ttu-id="d8050-116">\<*project name*>. deploymentoptions</span><span class="sxs-lookup"><span data-stu-id="d8050-116">\<*project name*>.deploymentoptions</span></span>|<span data-ttu-id="d8050-117">Contém opções de implantação como se a implantação é transacional e se objetos implantados deveriam ser processados depois da implantação.</span><span class="sxs-lookup"><span data-stu-id="d8050-117">Contains deployment options, such as whether deployment is transactional and whether deployed objects should be processed after deployment.</span></span>|  
  
> [!NOTE]  
>  [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="d8050-118">nunca armazena senhas em seus arquivos de projeto.</span><span class="sxs-lookup"><span data-stu-id="d8050-118">never stores passwords in its project files.</span></span>  
  
## <a name="modifying-the-input-files"></a><span data-ttu-id="d8050-119">Modificando os arquivos de entrada</span><span class="sxs-lookup"><span data-stu-id="d8050-119">Modifying the Input Files</span></span>  
 <span data-ttu-id="d8050-120">Modificar os valores nos arquivos de entrada ou os valores recuperados dos arquivos de entrada torna possível alterar o destino da implantação, as definições de configuração e as opções de implantação sem editar todo o \<*project name*> arquivo. asdatabase (ou um arquivo de script XMLA inteiro se você gerar um script a partir de um [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] banco de dados existente).</span><span class="sxs-lookup"><span data-stu-id="d8050-120">Modifying the values in the input files, or the values retrieved from the input files, makes it possible to change the deployment destination, the configuration settings, and deployment options without editing the whole \<*project name*>.asdatabase file (or a whole XMLA script file if you generate a script from an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database).</span></span> <span data-ttu-id="d8050-121">A possibilidade de modificar arquivos individuais permite que você crie com facilidade scripts de implantação para diferentes finalidades.</span><span class="sxs-lookup"><span data-stu-id="d8050-121">Being able to modify individual files lets you easily create different deployment scripts for different purposes.</span></span>  
  
 <span data-ttu-id="d8050-122">Os tópicos seguintes explicam como modificar valores nos vários arquivos de entrada:</span><span class="sxs-lookup"><span data-stu-id="d8050-122">The following topics explain how to modify values in the various input files:</span></span>  
  
-   [<span data-ttu-id="d8050-123">Especificando o destino de instalação</span><span class="sxs-lookup"><span data-stu-id="d8050-123">Specifying the Installation Target</span></span>](deployment-script-files-specifying-the-installation-target.md)  
  
-   [<span data-ttu-id="d8050-124">Especificando opções de implantação de função e de partição</span><span class="sxs-lookup"><span data-stu-id="d8050-124">Specifying Partition and Role Deployment Options</span></span>](deployment-script-files-partition-and-role-deployment-options.md)  
  
-   [<span data-ttu-id="d8050-125">Especificando definições de configuração para implantação de solução</span><span class="sxs-lookup"><span data-stu-id="d8050-125">Specifying Configuration Settings for Solution Deployment</span></span>](deployment-script-files-solution-deployment-config-settings.md)  
  
-   [<span data-ttu-id="d8050-126">Especificando opções de processamento</span><span class="sxs-lookup"><span data-stu-id="d8050-126">Specifying Processing Options</span></span>](deployment-script-files-specifying-processing-options.md)  
  
## <a name="see-also"></a><span data-ttu-id="d8050-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d8050-127">See Also</span></span>  
 <span data-ttu-id="d8050-128">[Executando o assistente de implantação do Analysis Services](running-the-analysis-services-deployment-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="d8050-128">[Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md) </span></span>  
 [<span data-ttu-id="d8050-129">Compreendendo o script de implantação do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="d8050-129">Understanding the Analysis Services Deployment Script</span></span>](understanding-the-analysis-services-deployment-script.md)  
  
  
