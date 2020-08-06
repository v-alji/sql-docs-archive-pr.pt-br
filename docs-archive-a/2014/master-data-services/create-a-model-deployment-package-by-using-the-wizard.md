---
title: Criar um pacote de implantação de modelo usando o Assistente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deployment packages [Master Data Services], creating
- models [Master Data Services], creating a deployment package
- creating packages [Master Data Services]
ms.assetid: b24ec4c2-1378-4c72-ac69-4ec2647030f0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: abb30f9d8e08d8eec8e04960b61575da3a1dbcc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583136"
---
# <a name="create-a-model-deployment-package-by-using-the-wizard"></a><span data-ttu-id="24adc-102">Criar um pacote de implantação de modelo usando o Assistente</span><span class="sxs-lookup"><span data-stu-id="24adc-102">Create a Model Deployment Package by Using the Wizard</span></span>
  <span data-ttu-id="24adc-103">Use o assistente de implantação de modelo do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] somente para criar um pacote dos objetos de modelo.</span><span class="sxs-lookup"><span data-stu-id="24adc-103">Use the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] model deployment wizard to create a package of the model objects only.</span></span> <span data-ttu-id="24adc-104">Se você precisar incluir dados no pacote, consulte [Criar um pacote de implantação de modelo usando o MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span><span class="sxs-lookup"><span data-stu-id="24adc-104">If you need to include data in the package, see [Create a Model Deployment Package by Using MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="24adc-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="24adc-105">Prerequisites</span></span>  
 <span data-ttu-id="24adc-106">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="24adc-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="24adc-107">No aplicativo Web do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , é preciso ter permissão para acessar a área funcional de **Administração do Sistema** .</span><span class="sxs-lookup"><span data-stu-id="24adc-107">In the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application, you must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="24adc-108">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="24adc-108">You must be a model administrator.</span></span> <span data-ttu-id="24adc-109">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="24adc-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="24adc-110">Deve existir um modelo como base para o pacote que será criado.</span><span class="sxs-lookup"><span data-stu-id="24adc-110">A model must exist for you to create a package of.</span></span> <span data-ttu-id="24adc-111">Para obter mais informações, consulte [Criar um modelo &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-model-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="24adc-111">For more information, see [Create a Model &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-model-master-data-services.md).</span></span>  
  
### <a name="to-create-a-model-deployment-package"></a><span data-ttu-id="24adc-112">Para criar um pacote de implantação de modelo</span><span class="sxs-lookup"><span data-stu-id="24adc-112">To create a model deployment package</span></span>  
  
1.  <span data-ttu-id="24adc-113">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="24adc-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="24adc-114">Na barra de menus da página **Exibição de Modelo** , aponte para **Sistema** e clique em **Implantação**.</span><span class="sxs-lookup"><span data-stu-id="24adc-114">On the **Model View** page, from the menu bar, point to **System** and click **Deployment**.</span></span>  
  
3.  <span data-ttu-id="24adc-115">No **Assistente de Implantação de Modelo**, clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="24adc-115">On the **Model Deployment Wizard**, click **Create**.</span></span>  
  
4.  <span data-ttu-id="24adc-116">Na página **Criar Pacote** , selecione um modelo da lista **Modelo** .</span><span class="sxs-lookup"><span data-stu-id="24adc-116">On the **Create Package** page, select a model from the **Model** list.</span></span>  
  
5.  <span data-ttu-id="24adc-117">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="24adc-117">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="24adc-118">Clique em **Download**.</span><span class="sxs-lookup"><span data-stu-id="24adc-118">Click **Download**.</span></span>  
  
7.  <span data-ttu-id="24adc-119">Salve o arquivo.</span><span class="sxs-lookup"><span data-stu-id="24adc-119">Save the file.</span></span>  
  
8.  <span data-ttu-id="24adc-120">Clique em **Fechar** para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="24adc-120">Click **Close** to close the wizard.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="24adc-121">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="24adc-121">Next Steps</span></span>  
  
-   [<span data-ttu-id="24adc-122">Implantar um pacote de implantação de modelo usando o Assistente</span><span class="sxs-lookup"><span data-stu-id="24adc-122">Deploy a Model Deployment Package by Using the Wizard</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="24adc-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="24adc-123">See Also</span></span>  
 [<span data-ttu-id="24adc-124">Implantando modelos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="24adc-124">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
  
