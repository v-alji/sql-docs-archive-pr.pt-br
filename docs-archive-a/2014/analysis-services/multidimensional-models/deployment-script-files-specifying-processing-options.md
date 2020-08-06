---
title: Especificando opções de processamento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Analysis Services deployments, processing options
- input files [Analysis Services]
- deploying [Analysis Services], processing options
- modifying processing options
- Analysis Services Deployment Wizard, processing options
ms.assetid: e9e50817-908e-4210-bc3d-8e2957568241
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9690aaa7e1d3b3870eb6ab01630b98027263655f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679057"
---
# <a name="specifying-processing-options"></a><span data-ttu-id="67705-102">Especificando opções de processamento</span><span class="sxs-lookup"><span data-stu-id="67705-102">Specifying Processing Options</span></span>
  <span data-ttu-id="67705-103">O [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Assistente de implantação lê as opções de processamento do \<*project name*> arquivo. deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="67705-103">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard reads the processing options from the \<*project name*>.deploymentoptions file.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="67705-104">cria esse arquivo quando você compila o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projeto.</span><span class="sxs-lookup"><span data-stu-id="67705-104">creates this file when you build the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="67705-105">usa as opções de processamento especificadas na página **implantação** da *\<project name>* caixa de diálogo **páginas de propriedades** para criar o \<*project name*> arquivo. deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="67705-105">uses the processing options specified on the **Deployment** page of *\<project name>* **Properties Pages** dialog box to create the \<*project name*>.deploymentoptions file.</span></span>  
  
## <a name="reviewing-the-processing-options-for-deployment"></a><span data-ttu-id="67705-106">Revisando as opções de processamento para implantação</span><span class="sxs-lookup"><span data-stu-id="67705-106">Reviewing the Processing Options for Deployment</span></span>  
 <span data-ttu-id="67705-107">As definições de configuração armazenadas no \<*project name*> arquivo. deploymentoptions são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="67705-107">The configuration settings stored within the \<*project name*>.deploymentoptions file are as follows:</span></span>  
  
-   <span data-ttu-id="67705-108">**Método de Processamento** Essa configuração controla se os objetos implantados são processados após a implantação e o tipo de processamento executados.</span><span class="sxs-lookup"><span data-stu-id="67705-108">**Processing Method** This setting controls whether the deployed objects are processed after deployment and the type of processing that will be performed.</span></span> <span data-ttu-id="67705-109">Há três opções de processamento:</span><span class="sxs-lookup"><span data-stu-id="67705-109">There are three processing options:</span></span>  
  
    -   <span data-ttu-id="67705-110">Processamento padrão</span><span class="sxs-lookup"><span data-stu-id="67705-110">Default processing (default)</span></span>  
  
    -   <span data-ttu-id="67705-111">Processamento completo</span><span class="sxs-lookup"><span data-stu-id="67705-111">Full processing</span></span>  
  
    -   <span data-ttu-id="67705-112">Nenhum</span><span class="sxs-lookup"><span data-stu-id="67705-112">None</span></span>  
  
-   <span data-ttu-id="67705-113">**Opções de Tabelas de Write-back** Se o write-back estiver habilitado no projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , essa configuração definirá como o write-back será manipulado.</span><span class="sxs-lookup"><span data-stu-id="67705-113">**Writeback Table Options** If writeback is enabled in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, this setting defines how writeback is handled.</span></span> <span data-ttu-id="67705-114">Há três opções de tabela de write-back:</span><span class="sxs-lookup"><span data-stu-id="67705-114">There are three writeback table options:</span></span>  
  
    -   <span data-ttu-id="67705-115">Por padrão, a tabela de write-back existente será usada, se existir.</span><span class="sxs-lookup"><span data-stu-id="67705-115">By default, if a writeback table exists, it will be used.</span></span> <span data-ttu-id="67705-116">Se uma tabela de write-back não existir, uma nova tabela será criada.</span><span class="sxs-lookup"><span data-stu-id="67705-116">If a writeback table does not exist, a new writeback table will be created.</span></span>  
  
    -   <span data-ttu-id="67705-117">Se uma tabela de write-back já existir, a implantação falhará.</span><span class="sxs-lookup"><span data-stu-id="67705-117">If a writeback table already exists, the deployment fails.</span></span> <span data-ttu-id="67705-118">Se uma tabela de write-back não existir, uma nova tabela será criada.</span><span class="sxs-lookup"><span data-stu-id="67705-118">If a writeback table does not exist, a new writeback table will be created.</span></span>  
  
    -   <span data-ttu-id="67705-119">Independentemente da existência de uma tabela de write-back, uma nova tabela será criada.</span><span class="sxs-lookup"><span data-stu-id="67705-119">Regardless of whether a writeback table already exists, a new writeback table will be created.</span></span> <span data-ttu-id="67705-120">Nesse caso, o Assistente para Implantação do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] excluirá qualquer tabela existente e vai substituí-la por uma nova.</span><span class="sxs-lookup"><span data-stu-id="67705-120">In this case, the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard will delete any existing table and replace it with a new writeback table.</span></span>  
  
-   <span data-ttu-id="67705-121">**Implantação Transacional** Essa configuração controla se a implantação das alterações de metadados e dos comandos de processo ocorre em uma única transação ou em transações separadas.</span><span class="sxs-lookup"><span data-stu-id="67705-121">**Transactional Deployment** This setting controls whether the deployment of metadata changes and process commands occurs in a single transaction or in separate transactions.</span></span>  
  
    -   <span data-ttu-id="67705-122">Se essa opção for `True` (padrão), o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] implantará todas as alterações de metadados e todos os comandos de processo em uma única transação.</span><span class="sxs-lookup"><span data-stu-id="67705-122">If this option is `True` (default), [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] deploys all metadata changes and all process commands within a single transaction.</span></span>  
  
    -   <span data-ttu-id="67705-123">Se essa opção for `False`, o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] implantará as alterações de metadados em uma única transação e cada comando de processamento será implantado em sua própria transação.</span><span class="sxs-lookup"><span data-stu-id="67705-123">If this option is `False`, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] deploys the metadata changes in a single transaction, and deploys each processing command in its own transaction.</span></span>  
  
## <a name="modifying-the-processing-options-for-deployment"></a><span data-ttu-id="67705-124">Modificando as opções de processamento para implantação</span><span class="sxs-lookup"><span data-stu-id="67705-124">Modifying the Processing Options for Deployment</span></span>  
 <span data-ttu-id="67705-125">No entanto, talvez seja necessário implantar o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projeto usando opções de processamento diferentes das armazenadas no \<*project name*> arquivo. deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="67705-125">However, you may need to deploy the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project using different processing options than those stored in the \<*project name*>.deploymentoptions file.</span></span> <span data-ttu-id="67705-126">Por exemplo, você pode processar por completo todos os objetos, processar usando a opção padrão ou não processá-los.</span><span class="sxs-lookup"><span data-stu-id="67705-126">For example, you may want to have all objects fully processed, or processed using the default processing option, or have no processing occur.</span></span> <span data-ttu-id="67705-127">Se os cubos ou dimensões forem habilitados para gravação, é possível especificar se uma tabela de write-back nova ou existente será usada.</span><span class="sxs-lookup"><span data-stu-id="67705-127">If the cubes or dimensions are write-enabled, you can specify whether a new or existing writeback table be used.</span></span>  
  
 <span data-ttu-id="67705-128">Para modificar as opções de processamento usadas durante a implantação, edite e recrie o projeto ou altere as opções de processamento do arquivo de entrada usando um dos métodos conforme descrito no procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="67705-128">To modify the processing options used during deployment, you can either edit and rebuild the project, or change the processing options in the input file by using one of the methods as described in the following procedure.</span></span>  
  
#### <a name="to-change-processing-options-after-the-input-files-have-been-generated"></a><span data-ttu-id="67705-129">Para alterar as opções de processamento depois que os arquivos de entrada tiverem sido gerados</span><span class="sxs-lookup"><span data-stu-id="67705-129">To change processing options after the input files have been generated</span></span>  
  
-   <span data-ttu-id="67705-130">Execute o Assistente para Implantação do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] de modo interativo.</span><span class="sxs-lookup"><span data-stu-id="67705-130">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard interactively.</span></span> <span data-ttu-id="67705-131">Na página **Opções de Processamento** , especifique as opções de processamento para o projeto que está sendo implantado.</span><span class="sxs-lookup"><span data-stu-id="67705-131">On the **Processing Options** page, specify the processing options for the project being deployed.</span></span>  
  
     <span data-ttu-id="67705-132">- ou -</span><span class="sxs-lookup"><span data-stu-id="67705-132">-or-</span></span>  
  
-   <span data-ttu-id="67705-133">Execute o Assistente para Implantação do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] no prompt de comando e defina o assistente para executar em modo de arquivo de resposta.</span><span class="sxs-lookup"><span data-stu-id="67705-133">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard at the command prompt and set the wizard to run in answer file mode.</span></span> <span data-ttu-id="67705-134">Para obter mais informações sobre o modo de arquivo de resposta, consulte [Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="67705-134">For more information about answer file mode, see [Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md).</span></span>  
  
     <span data-ttu-id="67705-135">- ou -</span><span class="sxs-lookup"><span data-stu-id="67705-135">-or-</span></span>  
  
-   <span data-ttu-id="67705-136">Modifique o \<*project name*> arquivo. deploymentoptions usando qualquer editor de texto.</span><span class="sxs-lookup"><span data-stu-id="67705-136">Modify the \<*project name*>.deploymentoptions file by using any text editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67705-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="67705-137">See Also</span></span>  
 <span data-ttu-id="67705-138">[Especificando o destino de instalação](deployment-script-files-specifying-the-installation-target.md) </span><span class="sxs-lookup"><span data-stu-id="67705-138">[Specifying the Installation Target](deployment-script-files-specifying-the-installation-target.md) </span></span>  
 <span data-ttu-id="67705-139">[Especificando opções de implantação de partição e função](deployment-script-files-partition-and-role-deployment-options.md) </span><span class="sxs-lookup"><span data-stu-id="67705-139">[Specifying Partition and Role Deployment Options](deployment-script-files-partition-and-role-deployment-options.md) </span></span>  
 [<span data-ttu-id="67705-140">Especificando definições de configuração para implantação de solução</span><span class="sxs-lookup"><span data-stu-id="67705-140">Specifying Configuration Settings for Solution Deployment</span></span>](deployment-script-files-solution-deployment-config-settings.md)  
  
  
