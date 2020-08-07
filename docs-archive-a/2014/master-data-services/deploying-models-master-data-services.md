---
title: Implantando modelos (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deployment packages [Master Data Services], about deployment packages
- deployment packages [Master Data Services]
ms.assetid: 30085c08-034f-4efe-80fe-408f9091ff5c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a9cc99112ec874e89ae07faa575235d9a041a972
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584178"
---
# <a name="deploying-models-master-data-services"></a><span data-ttu-id="619d8-102">Implantando modelos (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="619d8-102">Deploying Models (Master Data Services)</span></span>
  <span data-ttu-id="619d8-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], um pacote é um arquivo XML que contém uma estrutura de modelo implantável, e opcionalmente, dados do modelo.</span><span class="sxs-lookup"><span data-stu-id="619d8-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a package is an XML file that contains a deployable model structure, and optionally, data from the model.</span></span> <span data-ttu-id="619d8-104">Use pacotes modelo para mover cópias de modelos de um ambiente MDS para outro, ou crie novos modelos em seu ambiente MDS existente.</span><span class="sxs-lookup"><span data-stu-id="619d8-104">Use model packages to move copies of models from one MDS environment to another, or to create new models in your existing MDS environment.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="619d8-105">Os pacotes podem ser implantados somente na edição do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] na qual eles foram criados.</span><span class="sxs-lookup"><span data-stu-id="619d8-105">Packages can be deployed to the edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] they were created in only.</span></span> <span data-ttu-id="619d8-106">Isso significa que os pacotes criados no [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] não podem ser implantados no [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] ou superior.</span><span class="sxs-lookup"><span data-stu-id="619d8-106">This means that packages created in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] cannot be deployed to [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] or higher.</span></span>  
  
## <a name="tools-for-deploying-models"></a><span data-ttu-id="619d8-107">Ferramentas para implantar modelos</span><span class="sxs-lookup"><span data-stu-id="619d8-107">Tools for Deploying Models</span></span>  
 <span data-ttu-id="619d8-108">Para trabalhar com pacotes de modelo, você pode usar uma das três ferramentas, dependendo de suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="619d8-108">To work with model packages, you can use one of three tools, depending on your needs.</span></span>  
  
-   <span data-ttu-id="619d8-109">**Ferramenta MDSModelDeploy**: para criar e implantar objetos de modelo e dados, use a ferramenta MDSModelDeploy.exe.</span><span class="sxs-lookup"><span data-stu-id="619d8-109">**MDSModelDeploy tool**: To create and deploy model objects and data, use the MDSModelDeploy.exe tool.</span></span> <span data-ttu-id="619d8-110">Se você tiver selecionado o caminho padrão ao instalar o MDS, essa ferramenta estará localizada em *unidade*: \Program Files\Microsoft SQL Server\120\Master data Services\Configuration.</span><span class="sxs-lookup"><span data-stu-id="619d8-110">If you selected the default path when installing MDS, this tool is located on *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span></span>  
  
-   <span data-ttu-id="619d8-111">**Assistente para Implantação de Modelo**: para criar e implantar pacotes somente da estrutura de modelo, use o assistente no aplicativo Web do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="619d8-111">**Model Deployment wizard**: To create and deploy packages of the model structure only, use the wizard in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application.</span></span> <span data-ttu-id="619d8-112">Você não pode usar esse assistente para implantar dados.</span><span class="sxs-lookup"><span data-stu-id="619d8-112">You cannot use this wizard to deploy data.</span></span>  
  
-   <span data-ttu-id="619d8-113">**Editor de Pacote de Modelo**: para editar um pacote de modelo, use o ModelPackageEditor.exe, que inicia o assistente do Editor de Pacote de Modelo.</span><span class="sxs-lookup"><span data-stu-id="619d8-113">**Model Package Editor**: To edit a model package, use the ModelPackageEditor.exe that launches the Model Package Editor wizard.</span></span> <span data-ttu-id="619d8-114">Use esse assistente para editar um pacote criado pela ferramenta MDSModelDeploy ou pelo assistente de Implantação de Modelo.</span><span class="sxs-lookup"><span data-stu-id="619d8-114">You use this wizard to edit a package that was created by the MDSModelDeploy tool or the Model Deployment wizard.</span></span> <span data-ttu-id="619d8-115">Se você tiver selecionado o caminho padrão ao instalar o MDS, essa ferramenta estará localizada em *unidade*: \Program Files\Microsoft SQL Server\120\Master data Services\Configuration.</span><span class="sxs-lookup"><span data-stu-id="619d8-115">If you selected the default path when installing MDS, this tool is located on *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="619d8-116">Você pode usar o MDSDeployModel para criar um novo modelo, criar um clone de um modelo ou atualizar um modelo existente e seus dados.</span><span class="sxs-lookup"><span data-stu-id="619d8-116">You can use the MDSDeployModel to create a new model, create a clone of a model, or update an existing model and its data.</span></span> <span data-ttu-id="619d8-117">Se você usar a ferramenta MDSModelDeploy para atualizar um modelo existente e seus dados, e o pacote não contiver uma entidade, um atributo ou um membro que exista no modelo de destino, MDSModelDeploy não excluirá a entidade, o atributo ou o membro do modelo.</span><span class="sxs-lookup"><span data-stu-id="619d8-117">If you use the MDSModelDeploy tool to update an existing model and its data, and the package does not contain an entity, attribute, or member that exists in the destination model, MDSModelDeploy will not delete that entity, attribute, or member from the model.</span></span>  
  
## <a name="what-packages-contain"></a><span data-ttu-id="619d8-118">O que os pacotes contêm</span><span class="sxs-lookup"><span data-stu-id="619d8-118">What Packages Contain</span></span>  
 <span data-ttu-id="619d8-119">Um pacote de modelo é um arquivo XML salvo com a extensão .pkg.</span><span class="sxs-lookup"><span data-stu-id="619d8-119">A model package is an XML file that is saved with the .pkg extension.</span></span> <span data-ttu-id="619d8-120">Ao criar um pacote de implantação, é possível optar por incluir dados ou não.</span><span class="sxs-lookup"><span data-stu-id="619d8-120">When you create a deployment package, you can decide whether or not to include data.</span></span> <span data-ttu-id="619d8-121">Se decidir incluir dados, você deverá selecionar uma versão dos dados a ser incluída.</span><span class="sxs-lookup"><span data-stu-id="619d8-121">If you decide to include data, you must select a version of the data to include.</span></span>  
  
 <span data-ttu-id="619d8-122">Todos os objetos de modelo são incluídos em um pacote.</span><span class="sxs-lookup"><span data-stu-id="619d8-122">All model objects are included in a package.</span></span> <span data-ttu-id="619d8-123">Esses objetos são:</span><span class="sxs-lookup"><span data-stu-id="619d8-123">These objects are:</span></span>  
  
-   <span data-ttu-id="619d8-124">Entidades</span><span class="sxs-lookup"><span data-stu-id="619d8-124">Entities</span></span>  
  
-   <span data-ttu-id="619d8-125">Atributos</span><span class="sxs-lookup"><span data-stu-id="619d8-125">Attributes</span></span>  
  
-   <span data-ttu-id="619d8-126">Grupos de atributos</span><span class="sxs-lookup"><span data-stu-id="619d8-126">Attribute groups</span></span>  
  
-   <span data-ttu-id="619d8-127">Hierarquias</span><span class="sxs-lookup"><span data-stu-id="619d8-127">Hierarchies</span></span>  
  
-   <span data-ttu-id="619d8-128">Coleções</span><span class="sxs-lookup"><span data-stu-id="619d8-128">Collections</span></span>  
  
-   <span data-ttu-id="619d8-129">Regras de negócio</span><span class="sxs-lookup"><span data-stu-id="619d8-129">Business rules</span></span>  
  
-   <span data-ttu-id="619d8-130">Sinalizadores de versão</span><span class="sxs-lookup"><span data-stu-id="619d8-130">Version flags</span></span>  
  
-   <span data-ttu-id="619d8-131">Exibições de assinatura</span><span class="sxs-lookup"><span data-stu-id="619d8-131">Subscription views</span></span>  
  
 <span data-ttu-id="619d8-132">Metadados definidos pelo usuário, atributos de arquivo e permissões de grupo não estão incluídos.</span><span class="sxs-lookup"><span data-stu-id="619d8-132">User-defined metadata, file attributes, and user and group permissions are not included.</span></span> <span data-ttu-id="619d8-133">Depois de implantar um modelo, você deve atualizar esses objetos manualmente.</span><span class="sxs-lookup"><span data-stu-id="619d8-133">After you deploy a model, you must update these manually.</span></span>  
  
## <a name="sample-packages"></a><span data-ttu-id="619d8-134">Pacotes de exemplo</span><span class="sxs-lookup"><span data-stu-id="619d8-134">Sample Packages</span></span>  
 <span data-ttu-id="619d8-135">Arquivos de pacotes de exemplo são incluídos quando você instala o [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="619d8-135">Sample package files are included when you install [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span></span> <span data-ttu-id="619d8-136">Estes arquivos de pacotes estão no diretório Master Data Services\Samples\Packages onde o [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]foi instalado.</span><span class="sxs-lookup"><span data-stu-id="619d8-136">These package files are in the Master Data Services\Samples\Packages directory where you installed [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span></span> <span data-ttu-id="619d8-137">Quando você implanta esses pacotes de exemplo usando a ferramenta MDSModelDeploy, modelos de exemplo são criados e populados com dados.</span><span class="sxs-lookup"><span data-stu-id="619d8-137">When you deploy these sample packages by using the MDSModelDeploy tool, sample models are created and populated with data.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="619d8-138">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="619d8-138">Related Tasks</span></span>  
  
|<span data-ttu-id="619d8-139">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="619d8-139">Task Description</span></span>|<span data-ttu-id="619d8-140">Tópico</span><span class="sxs-lookup"><span data-stu-id="619d8-140">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="619d8-141">Crie um novo pacote de implantação de objetos de modelo e/ou dados usando a ferramenta MDSModelDeploy.</span><span class="sxs-lookup"><span data-stu-id="619d8-141">Create a new deployment package of model objects and/or data by using the MDSModelDeploy tool.</span></span>|[<span data-ttu-id="619d8-142">Criar um pacote de implantação de modelo usando o MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="619d8-142">Create a Model Deployment Package by Using MDSModelDeploy</span></span>](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md)|  
|<span data-ttu-id="619d8-143">Crie um novo pacote de implantação somente de objetos de modelo usando o assistente.</span><span class="sxs-lookup"><span data-stu-id="619d8-143">Create a new deployment package of model objects only by using the wizard.</span></span>|[<span data-ttu-id="619d8-144">Criar um pacote de implantação de modelo usando o Assistente</span><span class="sxs-lookup"><span data-stu-id="619d8-144">Create a Model Deployment Package by Using the Wizard</span></span>](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md)|  
|<span data-ttu-id="619d8-145">Implante um pacote de objetos de modelo e dados usando a ferramenta MDSModelDeploy.</span><span class="sxs-lookup"><span data-stu-id="619d8-145">Deploy a package of model objects and data by using the MDSModelDeploy tool.</span></span>|[<span data-ttu-id="619d8-146">Implantar um pacote de implantação de modelo usando MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="619d8-146">Deploy a Model Deployment Package by Using MDSModelDeploy</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md)|  
|<span data-ttu-id="619d8-147">Implante um pacote somente de objetos de modelo usando o assistente.</span><span class="sxs-lookup"><span data-stu-id="619d8-147">Deploy a package of model objects only by using the wizard.</span></span>|[<span data-ttu-id="619d8-148">Implantar um pacote de implantação de modelo usando o Assistente</span><span class="sxs-lookup"><span data-stu-id="619d8-148">Deploy a Model Deployment Package by Using the Wizard</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md)|  
|<span data-ttu-id="619d8-149">Edite um pacote de implantação de modelo para implantar partes selecionadas de um modelo, em vez do modelo inteiro.</span><span class="sxs-lookup"><span data-stu-id="619d8-149">Edit a model deployment package to deploy selected parts of a model, rather than the entire model.</span></span>|[<span data-ttu-id="619d8-150">Editar um pacote de implantação de modelo</span><span class="sxs-lookup"><span data-stu-id="619d8-150">Edit a Model Deployment Package</span></span>](../../2014/master-data-services/edit-a-model-deployment-package.md)|  
  
## <a name="related-content"></a><span data-ttu-id="619d8-151">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="619d8-151">Related Content</span></span>  
  
-   [<span data-ttu-id="619d8-152">Opções de implantação de modelo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="619d8-152">Model Deployment Options &#40;Master Data Services&#41;</span></span>](model-deployment-options-master-data-services.md)  
  
  
