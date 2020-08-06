---
title: Implantar um pacote de implantação de modelo usando o Assistente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deployment packages [Master Data Services], deploying
- models [Master Data Services], deploying a package
ms.assetid: 4f65dc60-0ff8-46e6-9988-5bc5b9603ad0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 75af9f7c12d866c6d9707f62c898aa7601f94800
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683572"
---
# <a name="deploy-a-model-deployment-package-by-using-the-wizard"></a><span data-ttu-id="aa4ee-102">Implantar um pacote de implantação de modelo usando o Assistente</span><span class="sxs-lookup"><span data-stu-id="aa4ee-102">Deploy a Model Deployment Package by Using the Wizard</span></span>
  <span data-ttu-id="aa4ee-103">Use o assistente de implantação de modelo do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] para implantar pacotes que contêm somente objetos de modelo.</span><span class="sxs-lookup"><span data-stu-id="aa4ee-103">Use the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] model deployment wizard to deploy packages that contain model objects only.</span></span> <span data-ttu-id="aa4ee-104">Se você precisar implantar um pacote com dados, consulte [Implantar um pacote de implantação de modelo usando MDSModelDeploy](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span><span class="sxs-lookup"><span data-stu-id="aa4ee-104">If you need to deploy a package with data, see [Deploy a Model Deployment Package by Using MDSModelDeploy](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="aa4ee-105">Os pacotes podem ser implantados somente na edição do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] na qual eles foram criados.</span><span class="sxs-lookup"><span data-stu-id="aa4ee-105">Packages can be deployed to the edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] they were created in only.</span></span> <span data-ttu-id="aa4ee-106">Isso significa que os pacotes criados no [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] não podem ser implantados no [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa4ee-106">This means that packages created in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] cannot be deployed to [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="aa4ee-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="aa4ee-107">Prerequisites</span></span>  
 <span data-ttu-id="aa4ee-108">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="aa4ee-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="aa4ee-109">Você deverá ter permissão para acessar a área funcional **Administração do Sistema** no ambiente [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] de destino.</span><span class="sxs-lookup"><span data-stu-id="aa4ee-109">You must have permission to access the **System Administration** functional area in the target [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] environment.</span></span>  
  
-   <span data-ttu-id="aa4ee-110">Um pacote de implantação de modelo deverá existir.</span><span class="sxs-lookup"><span data-stu-id="aa4ee-110">A model deployment package must exist.</span></span> <span data-ttu-id="aa4ee-111">Para obter mais informações, consulte [Criar um pacote de implantação de modelo usando o assistente](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="aa4ee-111">For more information, see [Create a Model Deployment Package by Using the Wizard](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md).</span></span>  
  
-   <span data-ttu-id="aa4ee-112">Você deve ser um administrador no ambiente onde está implantando o modelo.</span><span class="sxs-lookup"><span data-stu-id="aa4ee-112">You must be an administrator in the environment where you are deploying the model.</span></span> <span data-ttu-id="aa4ee-113">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="aa4ee-113">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-deploy-a-model-deployment-package-of-model-objects-only"></a><span data-ttu-id="aa4ee-114">Para implantar um pacote de implantação de modelo somente de objetos de modelo</span><span class="sxs-lookup"><span data-stu-id="aa4ee-114">To deploy a model deployment package of model objects only</span></span>  
  
1.  <span data-ttu-id="aa4ee-115">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="aa4ee-115">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="aa4ee-116">Na barra de menus da página **Exibição de Modelo** , aponte para **Sistema** e clique em **Implantação**.</span><span class="sxs-lookup"><span data-stu-id="aa4ee-116">On the **Model View** page, from the menu bar, point to **System** and click **Deployment**.</span></span>  
  
3.  <span data-ttu-id="aa4ee-117">No **Assistente de Implantação de Modelo**, clique em **Implantar**.</span><span class="sxs-lookup"><span data-stu-id="aa4ee-117">On the **Model Deployment Wizard**, click **Deploy**.</span></span>  
  
4.  <span data-ttu-id="aa4ee-118">Clique em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="aa4ee-118">Click **Browse**.</span></span>  
  
5.  <span data-ttu-id="aa4ee-119">Localize seu pacote de implantação (arquivo .pkg) e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="aa4ee-119">Find your deployment package (.pkg file) and click **Open**.</span></span>  
  
6.  <span data-ttu-id="aa4ee-120">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="aa4ee-120">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="aa4ee-121">Depois que o pacote for carregado, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="aa4ee-121">After the package is loaded, click **Next**.</span></span>  
  
8.  <span data-ttu-id="aa4ee-122">Se o modelo já existir, você poderá atualizá-lo selecionando **Atualizar o modelo existente**.</span><span class="sxs-lookup"><span data-stu-id="aa4ee-122">If the model already exists, you can update it by selecting **Update the existing model**.</span></span> <span data-ttu-id="aa4ee-123">Para criar um novo modelo, selecione **Criar novo modelo** e, depois de clicar em **Avançar** , digite o nome do novo modelo.</span><span class="sxs-lookup"><span data-stu-id="aa4ee-123">To create a new model, select **Create a new model** and after you click **Next** you can type a name for the new model.</span></span>  
  
9. <span data-ttu-id="aa4ee-124">Clique em **Concluir** para sair do assistente.</span><span class="sxs-lookup"><span data-stu-id="aa4ee-124">Click **Finish** to exit the wizard.</span></span>  
  
 <span data-ttu-id="aa4ee-125">**Observações:**</span><span class="sxs-lookup"><span data-stu-id="aa4ee-125">**Notes:**</span></span>  
  
-   <span data-ttu-id="aa4ee-126">Se uma exibição de assinatura no pacote tiver o mesmo nome que uma exibição de assinatura em um modelo existente, a exibição será criada como *ModelName. subscriptionviewname*.</span><span class="sxs-lookup"><span data-stu-id="aa4ee-126">If a subscription view in the package has the same name as a subscription view in an existing model, the view is created as *modelname.subscriptionviewname*.</span></span> <span data-ttu-id="aa4ee-127">Se esse nome já estiver em uso, a exibição de assinatura não será criada.</span><span class="sxs-lookup"><span data-stu-id="aa4ee-127">If this name is already in use, the subscription view is not created.</span></span>  
  
-   <span data-ttu-id="aa4ee-128">O processo de implantação tem quatro etapas:</span><span class="sxs-lookup"><span data-stu-id="aa4ee-128">The deployment process has four steps:</span></span>  
  
    1.  <span data-ttu-id="aa4ee-129">Os objetos de modelo são criados.</span><span class="sxs-lookup"><span data-stu-id="aa4ee-129">The model objects are created.</span></span>  
  
    2.  <span data-ttu-id="aa4ee-130">As exibições de assinatura são criadas.</span><span class="sxs-lookup"><span data-stu-id="aa4ee-130">Subscription views are created.</span></span>  
  
    3.  <span data-ttu-id="aa4ee-131">As regras de negócio são criadas.</span><span class="sxs-lookup"><span data-stu-id="aa4ee-131">Business rules are created.</span></span>  
  
    4.  <span data-ttu-id="aa4ee-132">Os dados mestre são preenchidos.</span><span class="sxs-lookup"><span data-stu-id="aa4ee-132">Master data is populated.</span></span>  
  
-   <span data-ttu-id="aa4ee-133">Ao criar um modelo novo ou clonado, se o processo falhar durante alguma etapa, o modelo será excluído.</span><span class="sxs-lookup"><span data-stu-id="aa4ee-133">When creating a new or cloned model, if the process fails during any step, the model is deleted.</span></span>  
  
     <span data-ttu-id="aa4ee-134">Na atualização de um modelo, se o processo falhar durante alguma das três primeiras etapas, ele não irá além dessa etapa; no entanto, as alterações já feitas não serão revertidas.</span><span class="sxs-lookup"><span data-stu-id="aa4ee-134">When updating a model, if the process fails during any of the first three steps, it does not proceed beyond that step; however, changes that are already made are not rolled back.</span></span> <span data-ttu-id="aa4ee-135">Se o processo falhar na etapa 4, os membros que podem ser atualizados serão atualizados.</span><span class="sxs-lookup"><span data-stu-id="aa4ee-135">If the process fails in step 4, members that can be updated are updated.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="aa4ee-136">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="aa4ee-136">Next Steps</span></span>  
 <span data-ttu-id="aa4ee-137">Metadados definidos pelo usuário, atributos de arquivo e permissões de usuário e de grupo não estão incluídos em pacotes de implantação de modelo.</span><span class="sxs-lookup"><span data-stu-id="aa4ee-137">User-defined metadata, file attributes, and user and group permissions are not included in model deployment packages.</span></span> <span data-ttu-id="aa4ee-138">Depois de implantar um modelo, você deve atualizar esses objetos manualmente.</span><span class="sxs-lookup"><span data-stu-id="aa4ee-138">After you deploy a model, you must update these manually.</span></span> <span data-ttu-id="aa4ee-139">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="aa4ee-139">For more information, see:</span></span>  
  
-   [<span data-ttu-id="aa4ee-140">Adicionar metadados &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="aa4ee-140">Add Metadata &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-metadata-master-data-services.md)  
  
-   [<span data-ttu-id="aa4ee-141">Atribuir permissões de objeto de modelo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="aa4ee-141">Assign Model Object Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="aa4ee-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aa4ee-142">See Also</span></span>  
 [<span data-ttu-id="aa4ee-143">Implantando modelos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="aa4ee-143">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
  
