---
title: Implantar um pacote de implantação de modelo usando o MDSModelDeploy | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: fb2a4df4-5e0d-4b34-818f-383dbde1b15c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c23dcc592c2de34fa87703c8ba58d949dfec455c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575885"
---
# <a name="deploy-a-model-deployment-package-by-using-mdsmodeldeploy"></a><span data-ttu-id="465f8-102">Implantar um pacote de implantação de modelo usando MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="465f8-102">Deploy a Model Deployment Package by Using MDSModelDeploy</span></span>
  <span data-ttu-id="465f8-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], use a ferramenta MDSModelDeploy para implantar um pacote que contém:</span><span class="sxs-lookup"><span data-stu-id="465f8-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], use the MDSModelDeploy tool to deploy a package that contains either:</span></span>  
  
-   <span data-ttu-id="465f8-104">Somente objetos de modelo.</span><span class="sxs-lookup"><span data-stu-id="465f8-104">Model objects only.</span></span>  
  
-   <span data-ttu-id="465f8-105">Objetos de modelo e dados.</span><span class="sxs-lookup"><span data-stu-id="465f8-105">Model objects and data.</span></span>  
  
 <span data-ttu-id="465f8-106">Se desejar implantar um pacote que contém apenas objetos de modelo, você poderá usar o assistente de implantação de modelo no aplicativo Web [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="465f8-106">If you want to deploy a package that contains model objects only, you can use the model deployment wizard in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application instead.</span></span> <span data-ttu-id="465f8-107">Para obter mais informações, consulte [Implantar um pacote de implantação de modelo usando o Assistente](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="465f8-107">For more information, see [Deploy a Model Deployment Package by Using the Wizard](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="465f8-108">Os pacotes podem ser implantados somente na edição do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] na qual eles foram criados.</span><span class="sxs-lookup"><span data-stu-id="465f8-108">Packages can be deployed to the edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] they were created in only.</span></span> <span data-ttu-id="465f8-109">Isso significa que os pacotes criados no [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] não podem ser implantados no [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] ou superior.</span><span class="sxs-lookup"><span data-stu-id="465f8-109">This means that packages created in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] cannot be deployed to [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] or higher.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="465f8-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="465f8-110">Prerequisites</span></span>  
 <span data-ttu-id="465f8-111">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="465f8-111">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="465f8-112">Você deverá ter permissão para acessar a área funcional **Administração do Sistema** no ambiente [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] de destino.</span><span class="sxs-lookup"><span data-stu-id="465f8-112">You must have permission to access the **System Administration** functional area in the target [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] environment.</span></span>  
  
-   <span data-ttu-id="465f8-113">Um pacote de implantação de modelo deverá existir.</span><span class="sxs-lookup"><span data-stu-id="465f8-113">A model deployment package must exist.</span></span> <span data-ttu-id="465f8-114">Para obter mais informações, consulte  [Criar um pacote de implantação de modelo usando MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span><span class="sxs-lookup"><span data-stu-id="465f8-114">For more information, see  [Create a Model Deployment Package by Using MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span></span>  
  
-   <span data-ttu-id="465f8-115">Você deve ser um administrador no ambiente onde está implantando o modelo.</span><span class="sxs-lookup"><span data-stu-id="465f8-115">You must be an administrator in the environment where you are deploying the model.</span></span> <span data-ttu-id="465f8-116">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="465f8-116">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="465f8-117">Se estiver atualizando um modelo com os dados, a versão que está sendo implantada não poderá ser **Bloqueada** nem **Confirmada**.</span><span class="sxs-lookup"><span data-stu-id="465f8-117">If you are updating a model with data, the version you're deploying to cannot be **Locked** or **Committed**.</span></span>  
  
### <a name="to-deploy-a-model-deployment-package"></a><span data-ttu-id="465f8-118">Para implantar um pacote de implantação de modelo</span><span class="sxs-lookup"><span data-stu-id="465f8-118">To deploy a model deployment package</span></span>  
  
1.  <span data-ttu-id="465f8-119">Determine se você está implantando um novo modelo, um clone de um modelo ou atualizando um modelo clonado previamente.</span><span class="sxs-lookup"><span data-stu-id="465f8-119">Determine whether you are deploying a new model, a clone of a model, or updating a previously-cloned model.</span></span> <span data-ttu-id="465f8-120">Para obter mais informações, consulte [Opções de implantação de modelo &#40;Master Data Services&#41;](../../2014/master-data-services/model-deployment-options-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="465f8-120">For more information, see [Model Deployment Options &#40;Master Data Services&#41;](../../2014/master-data-services/model-deployment-options-master-data-services.md).</span></span>  
  
2.  <span data-ttu-id="465f8-121">Abra um prompt de comando e navegue para MDSModelDeploy.exe.</span><span class="sxs-lookup"><span data-stu-id="465f8-121">Open a command prompt and navigate to MDSModelDeploy.exe.</span></span>  
  
    -   <span data-ttu-id="465f8-122">Se o MDS estiver instalado no local padrão, a ferramenta estará disponível em *unidade*: \Program Files\Microsoft SQL Server\120\Master data Services\Configuration\MDSModelDeploy.exe</span><span class="sxs-lookup"><span data-stu-id="465f8-122">If MDS is installed at the default location, the tool is available at *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration\MDSModelDeploy.exe</span></span>  
  
    -   <span data-ttu-id="465f8-123">Se o MDS não estiver instalado no local padrão, pesquise MDSModelDeploy.exe no comutador local.</span><span class="sxs-lookup"><span data-stu-id="465f8-123">If MDS is not installed at the default location, search the local computer for MDSModelDeploy.exe.</span></span>  
  
3.  <span data-ttu-id="465f8-124">Opcional.</span><span class="sxs-lookup"><span data-stu-id="465f8-124">Optional.</span></span> <span data-ttu-id="465f8-125">Exiba as opções e a ajuda.</span><span class="sxs-lookup"><span data-stu-id="465f8-125">View options and help.</span></span>  
  
    -   <span data-ttu-id="465f8-126">Para exibir todas as opções disponíveis, digite `MDSModelDeploy` e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="465f8-126">To display all available options, type `MDSModelDeploy` and press Enter.</span></span>  
  
    -   <span data-ttu-id="465f8-127">Para exibir a ajuda para uma opção, digite o seguinte, em que *OptionName* é o nome da opção: `MDSModelDeploy help OptionName`.</span><span class="sxs-lookup"><span data-stu-id="465f8-127">To display help for an option, type the following, where *OptionName* is the name of the option: `MDSModelDeploy help OptionName`.</span></span>  
  
4.  <span data-ttu-id="465f8-128">Opcional.</span><span class="sxs-lookup"><span data-stu-id="465f8-128">Optional.</span></span> <span data-ttu-id="465f8-129">Se houver vários aplicativos Web, determine o nome do serviço no qual você implantará digitando este comando e pressionando Enter:</span><span class="sxs-lookup"><span data-stu-id="465f8-129">If you have multiple web applications, determine the name of the service you will deploy to by typing this command and pressing Enter:</span></span>  
  
    ```  
    MDSModelDeploy listservices  
    ```  
  
     <span data-ttu-id="465f8-130">Uma lista de valores é retornada, por exemplo, `MDS1, Default Web Site, MDS`.</span><span class="sxs-lookup"><span data-stu-id="465f8-130">A list of values is returned, for example `MDS1, Default Web Site, MDS`.</span></span> <span data-ttu-id="465f8-131">O primeiro valor nesta lista (neste caso, `MDS1`) é necessário para implantar o modelo.</span><span class="sxs-lookup"><span data-stu-id="465f8-131">The first value in this list (in this case, `MDS1`) is needed to deploy the model.</span></span>  
  
5.  <span data-ttu-id="465f8-132">Dependendo de se você está criando um modelo, clonando um modelo ou atualizando um modelo, no prompt de comando, digite o seguinte e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="465f8-132">Depending on whether you are creating a model, cloning a model, or updating a model, at the command prompt, type the following and press Enter.</span></span>  
  
    -   <span data-ttu-id="465f8-133">Para criar um novo modelo:</span><span class="sxs-lookup"><span data-stu-id="465f8-133">To create a new model:</span></span>  
  
        ```  
        MDSModelDeploy deploynew -package PackageName -model ModelName -service ServiceName  
        ```  
  
    -   <span data-ttu-id="465f8-134">Para criar um clone de um modelo:</span><span class="sxs-lookup"><span data-stu-id="465f8-134">To create a clone of a model:</span></span>  
  
        ```  
        MDSModelDeploy deployclone -package PackageName  
        ```  
  
    -   <span data-ttu-id="465f8-135">Para atualizar um modelo existente e seus dados:</span><span class="sxs-lookup"><span data-stu-id="465f8-135">To update an existing model and its data:</span></span>  
  
        ```  
        MDSModelDeploy deployupdate -package PackageName -version VersionName  
        ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="465f8-136">Se você usar a ferramenta MDSModelDeploy para atualizar um modelo existente e seus dados, e o pacote não contiver uma entidade, um atributo ou um membro que exista no modelo de destino, MDSModelDeploy não excluirá a entidade, o atributo ou o membro do modelo.</span><span class="sxs-lookup"><span data-stu-id="465f8-136">If you use the MDSModelDeploy tool to update an existing model and its data, and the package does not contain an entity, attribute, or member that exists in the destination model, MDSModelDeploy will not delete that entity, attribute, or member from the model.</span></span>  
  
     <span data-ttu-id="465f8-137">Em que *PackageName* é o nome do arquivo do pacote (.pkg), *ModelName* é o nome do novo modelo, *VersionName* é o nome da versão e *ServiceName* é o nome do serviço retornado na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="465f8-137">Where *PackageName* is the name of the package (.pkg) file, *ModelName* is the name of the new model, *VersionName* is the name of the version, and *ServiceName* is the name of the service that you returned in the previous step.</span></span> <span data-ttu-id="465f8-138">Verifique se os nomes do modelo e da versão correspondem aos nomes exatos com diferenciação de maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="465f8-138">Ensure that the model and version names match the exact case-sensitive names.</span></span>  
  
6.  <span data-ttu-id="465f8-139">Quando o pacote é implantado com êxito, uma mensagem é exibida informando que "A operação MDSModelDeploy foi concluída com êxito".</span><span class="sxs-lookup"><span data-stu-id="465f8-139">When the package is successfully deployed, a message stating "MDSModelDeploy operation completed successfully" is displayed.</span></span>  
  
 <span data-ttu-id="465f8-140">**Observações:**</span><span class="sxs-lookup"><span data-stu-id="465f8-140">**Notes:**</span></span>  
  
-   <span data-ttu-id="465f8-141">Se uma exibição de assinatura no pacote tiver o mesmo nome que uma exibição de assinatura em um modelo existente, a exibição será criada como *ModelName. subscriptionviewname*.</span><span class="sxs-lookup"><span data-stu-id="465f8-141">If a subscription view in the package has the same name as a subscription view in an existing model, the view is created as *modelname.subscriptionviewname*.</span></span> <span data-ttu-id="465f8-142">Se esse nome já estiver em uso, a exibição de assinatura não será criada.</span><span class="sxs-lookup"><span data-stu-id="465f8-142">If this name is already in use, the subscription view is not created.</span></span>  
  
-   <span data-ttu-id="465f8-143">O processo de implantação tem quatro etapas:</span><span class="sxs-lookup"><span data-stu-id="465f8-143">The deployment process has four steps:</span></span>  
  
    1.  <span data-ttu-id="465f8-144">Os objetos de modelo são criados.</span><span class="sxs-lookup"><span data-stu-id="465f8-144">The model objects are created.</span></span>  
  
    2.  <span data-ttu-id="465f8-145">As regras de negócio são criadas.</span><span class="sxs-lookup"><span data-stu-id="465f8-145">Business rules are created.</span></span>  
  
    3.  <span data-ttu-id="465f8-146">As exibições de assinatura são criadas.</span><span class="sxs-lookup"><span data-stu-id="465f8-146">Subscription views are created.</span></span>  
  
    4.  <span data-ttu-id="465f8-147">Os dados mestre são preenchidos.</span><span class="sxs-lookup"><span data-stu-id="465f8-147">Master data is populated.</span></span>  
  
-   <span data-ttu-id="465f8-148">Ao criar um modelo novo ou clonado, se o processo falhar durante alguma etapa, o modelo será excluído.</span><span class="sxs-lookup"><span data-stu-id="465f8-148">When creating a new or cloned model, if the process fails during any step, the model is deleted.</span></span>  
  
     <span data-ttu-id="465f8-149">Na atualização de um modelo, se o processo falhar durante as três primeiras etapas, ele não continuará; no entanto, as alterações já feitas não serão revertidas.</span><span class="sxs-lookup"><span data-stu-id="465f8-149">When updating a model, if the process fails during the first three steps, it does not proceed; however, changes that are already made are not rolled back.</span></span> <span data-ttu-id="465f8-150">Se o processo falhar na etapa 4, os membros que podem ser atualizados serão atualizados.</span><span class="sxs-lookup"><span data-stu-id="465f8-150">If the process fails in step 4, members that can be updated are updated.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="465f8-151">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="465f8-151">Next Steps</span></span>  
 <span data-ttu-id="465f8-152">Metadados definidos pelo usuário, atributos de arquivo e permissões de usuário e de grupo não estão incluídos em pacotes de implantação de modelo.</span><span class="sxs-lookup"><span data-stu-id="465f8-152">User-defined metadata, file attributes, and user and group permissions are not included in model deployment packages.</span></span> <span data-ttu-id="465f8-153">Depois de implantar um modelo, você deve atualizar esses objetos manualmente.</span><span class="sxs-lookup"><span data-stu-id="465f8-153">After you deploy a model, you must update these manually.</span></span> <span data-ttu-id="465f8-154">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="465f8-154">For more information, see:</span></span>  
  
-   [<span data-ttu-id="465f8-155">Adicionar metadados &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="465f8-155">Add Metadata &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-metadata-master-data-services.md)  
  
-   [<span data-ttu-id="465f8-156">Atribuir permissões de objeto de modelo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="465f8-156">Assign Model Object Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="465f8-157">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="465f8-157">See Also</span></span>  
 [<span data-ttu-id="465f8-158">Implantando modelos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="465f8-158">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
  
