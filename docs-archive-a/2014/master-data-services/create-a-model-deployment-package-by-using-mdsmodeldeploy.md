---
title: Criar um pacote de implantação de modelo usando o MDSModelDeploy | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: c2687e39-dc20-494f-a707-2aa29f4c329e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c546d6398234dd43103d0e6c75822377e11de61a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583698"
---
# <a name="create-a-model-deployment-package-by-using-mdsmodeldeploy"></a><span data-ttu-id="8cd02-102">Criar um pacote de implantação de modelo usando o MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="8cd02-102">Create a Model Deployment Package by Using MDSModelDeploy</span></span>
  <span data-ttu-id="8cd02-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], use a ferramenta MDSModelDeploy para criar um pacote.</span><span class="sxs-lookup"><span data-stu-id="8cd02-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], use the MDSModelDeploy tool to create a package.</span></span> <span data-ttu-id="8cd02-104">Dependendo dos comandos especificados, o pacote poderá conter:</span><span class="sxs-lookup"><span data-stu-id="8cd02-104">Depending on the commands you specify, the package can contain either:</span></span>  
  
-   <span data-ttu-id="8cd02-105">Somente objetos de modelo.</span><span class="sxs-lookup"><span data-stu-id="8cd02-105">Model objects only.</span></span>  
  
-   <span data-ttu-id="8cd02-106">Objetos de modelo e dados.</span><span class="sxs-lookup"><span data-stu-id="8cd02-106">Model objects and data.</span></span>  
  
 <span data-ttu-id="8cd02-107">Se desejar implantar um pacote que contém apenas objetos de modelo, você poderá usar o assistente de implantação de modelo no aplicativo Web [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8cd02-107">If you want to deploy a package that contains model objects only, you can use the model deployment wizard in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application instead.</span></span> <span data-ttu-id="8cd02-108">Para obter mais informações, consulte [Criar um pacote de implantação de modelo usando o assistente](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="8cd02-108">For more information, see [Create a Model Deployment Package by Using the Wizard](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md).</span></span>  
> [!NOTE]  
> <span data-ttu-id="8cd02-109">Esta versão da ferramenta MDSModelDeploy não pode usar mais de gigabytes (GB) de memória.</span><span class="sxs-lookup"><span data-stu-id="8cd02-109">This version of the MDSModelDeploy tool cannot use more than gigabytes (GB) of memory.</span></span> <span data-ttu-id="8cd02-110">Quando você cria ou implanta modelos grandes usando **objetos de modelo e** a opção de dados, você pode ter erros de "memória insuficiente" ou "o fluxo era muito longo".</span><span class="sxs-lookup"><span data-stu-id="8cd02-110">When you create or deploy large models by using **Model objects and data** option, you may experience "Out of Memory" or "Stream was too long" errors.</span></span> <span data-ttu-id="8cd02-111">Para resolver esse problema, use o preparo do MDS para implantar os dados; ou atualize para o MDS 2016 ou uma versão posterior, que inclui a versão atualizada da ferramenta MDSModelDeploy.</span><span class="sxs-lookup"><span data-stu-id="8cd02-111">To resolve this issue, use MDS staging to deploy the data; or upgrade to MDS 2016 or a later version, which includes the updated version of the MDSModelDeploy tool.</span></span>
## <a name="prerequisites"></a><span data-ttu-id="8cd02-112">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="8cd02-112">Prerequisites</span></span>  
 <span data-ttu-id="8cd02-113">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="8cd02-113">To perform this procedure:</span></span>  
  
1.  <span data-ttu-id="8cd02-114">As permissões básicas exigidas para executar a ferramenta MDSModelDeploy são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="8cd02-114">The basic permissions required to run the MDSModelDeploy tool are the following:</span></span>  
  
    -   <span data-ttu-id="8cd02-115">A mesma permissão do Windows como o MDS Configuration Manager (administrador do Windows)</span><span class="sxs-lookup"><span data-stu-id="8cd02-115">The same Windows permission as the MDS Configuration Manager (administrator of Windows)</span></span>  
  
    -   <span data-ttu-id="8cd02-116">Permissão DBA no banco de dados do MDS.</span><span class="sxs-lookup"><span data-stu-id="8cd02-116">DBA permission on the MDS database.</span></span>  
  
2.  <span data-ttu-id="8cd02-117">As permissões necessárias para criar o pacote usando a ferramenta MDSModelDeploy são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="8cd02-117">The permissions required to create the package using the MDSModelDeploy tool are the following:</span></span>  
  
    -   <span data-ttu-id="8cd02-118">Permissão de administrador de modelo do MDS no modelo de dados.</span><span class="sxs-lookup"><span data-stu-id="8cd02-118">MDS model administrator permission on the data model.</span></span>  
  
    -   <span data-ttu-id="8cd02-119">Permissão de função do Gerenciamento de Integração do MDS.</span><span class="sxs-lookup"><span data-stu-id="8cd02-119">MDS Integration Management function permission.</span></span>  
  
3.  <span data-ttu-id="8cd02-120">As permissões necessárias para implantar um modelo usando a ferramenta MDSModelDeploy são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="8cd02-120">The permissions required to deploy a model using the MDSModelDeploy tool are the following:</span></span>  
  
    -   <span data-ttu-id="8cd02-121">Permissão de função do MDS Explorer</span><span class="sxs-lookup"><span data-stu-id="8cd02-121">MDS Explorer function permission</span></span>  
  
    -   <span data-ttu-id="8cd02-122">Permissão de função do Gerenciamento de Integração do MDS</span><span class="sxs-lookup"><span data-stu-id="8cd02-122">MDS Integration Management function permission</span></span>  
  
    -   <span data-ttu-id="8cd02-123">Permissão de função da Administração do Sistema do MDS.</span><span class="sxs-lookup"><span data-stu-id="8cd02-123">MDS System Administration function permission.</span></span>  
  
4.  <span data-ttu-id="8cd02-124">As permissões necessárias para listar modelos usando a ferramenta MDSModelDeploy são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="8cd02-124">The permissions required to list models using the MDSModelDeploy tool are the following:</span></span>  
  
    -   <span data-ttu-id="8cd02-125">Permissão de função do MDS Explorer</span><span class="sxs-lookup"><span data-stu-id="8cd02-125">MDS Explorer function permission</span></span>  
  
    -   <span data-ttu-id="8cd02-126">A permissão de administrador de modelo do MDS no modelo de dados para ver o modelo na lista.</span><span class="sxs-lookup"><span data-stu-id="8cd02-126">MDS model administrator permission on the data model on order to see the model in the list.</span></span>  
  
 <span data-ttu-id="8cd02-127">Deve existir um modelo como base para o pacote que será criado.</span><span class="sxs-lookup"><span data-stu-id="8cd02-127">A model must exist for you to create a package of.</span></span> <span data-ttu-id="8cd02-128">Para obter mais informações, consulte [Criar um modelo &#40;Master Data Services&#41;](create-a-model-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8cd02-128">For more information, see [Create a Model &#40;Master Data Services&#41;](create-a-model-master-data-services.md).</span></span>  
  
 <span data-ttu-id="8cd02-129">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8cd02-129">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-model-deployment-package-by-using-mdsmodeldeploy"></a><span data-ttu-id="8cd02-130">Para criar um pacote de implantação de modelo usando o MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="8cd02-130">To create a model deployment package by using MDSModelDeploy</span></span>  
  
1.  <span data-ttu-id="8cd02-131">Abra um prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="8cd02-131">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="8cd02-132">Navegue até o local de MDSModelDeploy.exe.</span><span class="sxs-lookup"><span data-stu-id="8cd02-132">Navigate to the location of MDSModelDeploy.exe.</span></span>  
  
    -   <span data-ttu-id="8cd02-133">Se o MDS estiver instalado na local padrão, o arquivo estará em *drive*: \Arquivos de Programas\Microsoft SQL Server\120\Master Data Services\Configuration.</span><span class="sxs-lookup"><span data-stu-id="8cd02-133">If MDS was installed in the default location, the file is in *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span></span>  
  
    -   <span data-ttu-id="8cd02-134">Se o MDS não estiver instalado no local padrão, pesquise MDSModelDeploy.exe no comutador local.</span><span class="sxs-lookup"><span data-stu-id="8cd02-134">If MDS was not installed in the default location, search the local computer for MDSModelDeploy.exe.</span></span>  
  
3.  <span data-ttu-id="8cd02-135">Opcional.</span><span class="sxs-lookup"><span data-stu-id="8cd02-135">Optional.</span></span> <span data-ttu-id="8cd02-136">Exiba as opções e a ajuda.</span><span class="sxs-lookup"><span data-stu-id="8cd02-136">View options and help.</span></span>  
  
    -   <span data-ttu-id="8cd02-137">Para exibir todas as opções disponíveis, digite `MDSModelDeploy` e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="8cd02-137">To display all available options, type `MDSModelDeploy` and press Enter.</span></span>  
  
    -   <span data-ttu-id="8cd02-138">Para exibir a ajuda para uma opção, digite o seguinte, em que *OptionName* é o nome da opção: `MDSModelDeploy help OptionName`.</span><span class="sxs-lookup"><span data-stu-id="8cd02-138">To display help for an option, type the following, where *OptionName* is the name of the option: `MDSModelDeploy help OptionName`.</span></span>  
  
4.  <span data-ttu-id="8cd02-139">Opcional.</span><span class="sxs-lookup"><span data-stu-id="8cd02-139">Optional.</span></span> <span data-ttu-id="8cd02-140">Se houver vários aplicativos Web, determine o nome do serviço no qual você implantará digitando este comando e pressionando Enter:</span><span class="sxs-lookup"><span data-stu-id="8cd02-140">If you have multiple web applications, determine the name of the service you will deploy to by typing this command and pressing Enter:</span></span>  
  
    ```  
    MDSModelDeploy listservices  
    ```  
  
     <span data-ttu-id="8cd02-141">Uma lista de valores é retornada, por exemplo, `MDS1, Default Web Site, MDS`.</span><span class="sxs-lookup"><span data-stu-id="8cd02-141">A list of values is returned, for example `MDS1, Default Web Site, MDS`.</span></span> <span data-ttu-id="8cd02-142">O primeiro valor nesta lista (neste caso, `MDS1`) é necessário para implantar o modelo.</span><span class="sxs-lookup"><span data-stu-id="8cd02-142">The first value in this list (in this case, `MDS1`) is needed to deploy the model.</span></span>  
  
5.  <span data-ttu-id="8cd02-143">Para criar um pacote que contém objetos de modelo e dados, digite o seguinte, onde *ModelName*, *VersionName*, *ServiceName*e *PackageName* são os nomes do modelo, da versão, do serviço e do arquivo de saída .pkg respectivamente:</span><span class="sxs-lookup"><span data-stu-id="8cd02-143">To create a package that contains model objects and data, type the following, where *ModelName*, *VersionName*, *ServiceName*,  and *PackageName* are the names of the model, version, service, and of the .pkg output file respectively:</span></span>  
  
    ```  
    MDSModelDeploy createpackage -model ModelName -version VersionName -service ServiceName -package PackageName -includedata  
    ```  
  
     <span data-ttu-id="8cd02-144">Para incluir dados, não use as opções `-version` e `-includedata` .</span><span class="sxs-lookup"><span data-stu-id="8cd02-144">If you do not want to include data, do not use the `-version` and `-includedata` switches.</span></span>  
  
6.  <span data-ttu-id="8cd02-145">Pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="8cd02-145">Press Enter.</span></span> <span data-ttu-id="8cd02-146">Quando o pacote é criado com êxito, uma mensagem é exibida informando que "A operação MDSModelDeploy foi concluída com êxito".</span><span class="sxs-lookup"><span data-stu-id="8cd02-146">When the package is successfully created, a message stating "MDSModelDeploy operation completed successfully" is displayed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8cd02-147">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="8cd02-147">Next Steps</span></span>  
  
-   [<span data-ttu-id="8cd02-148">Implantar um pacote de implantação de modelo usando MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="8cd02-148">Deploy a Model Deployment Package by Using MDSModelDeploy</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md)  
  
## <a name="see-also"></a><span data-ttu-id="8cd02-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8cd02-149">See Also</span></span>  
 <span data-ttu-id="8cd02-150">[Opções de implantação de modelo &#40;Master Data Services&#41;](../../2014/master-data-services/model-deployment-options-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="8cd02-150">[Model Deployment Options &#40;Master Data Services&#41;](../../2014/master-data-services/model-deployment-options-master-data-services.md) </span></span>  
 [<span data-ttu-id="8cd02-151">Implantando modelos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8cd02-151">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
  
