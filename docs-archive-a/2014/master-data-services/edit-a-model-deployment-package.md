---
title: Editar um pacote de implantação de modelo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 6b0fdb7d-83dd-4392-9011-4ae642c471f1
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b8bfd7083e2ba763d15a405266260b5a096c8378
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584161"
---
# <a name="edit-a-model-deployment-package"></a><span data-ttu-id="4e4eb-102">Editar um pacote de implantação de modelo</span><span class="sxs-lookup"><span data-stu-id="4e4eb-102">Edit a Model Deployment Package</span></span>
  <span data-ttu-id="4e4eb-103">Este tópico descreve como implantar partes selecionadas de um modelo em MDS, e não um modelo inteiro.</span><span class="sxs-lookup"><span data-stu-id="4e4eb-103">This topic describes how to deploy selected parts of a model in MDS, rather than an entire model.</span></span> <span data-ttu-id="4e4eb-104">Para fazer isso, edite um pacote de modelo MDS usando o Editor de Pacote de Modelo.</span><span class="sxs-lookup"><span data-stu-id="4e4eb-104">To do so, you edit an MDS model package using the Model Package Editor.</span></span>  
  
 <span data-ttu-id="4e4eb-105">O assistente de Editor de Pacote de Modelo permite que você selecione as entidades específicas, hierarquias derivadas, exibições de assinatura e regras de negócio em um modelo a ser incluído em um pacote MDS e, posteriormente, implante-as.</span><span class="sxs-lookup"><span data-stu-id="4e4eb-105">The Model Package Editor wizard enables you to select the specific entities, derived hierarchies, subscription views, and business rules in a model that you want to include in an MDS package, and then later deploy.</span></span> <span data-ttu-id="4e4eb-106">É possível omitir essas partes do modelo que você não deseja implantar.</span><span class="sxs-lookup"><span data-stu-id="4e4eb-106">You can leave out those parts of the model that you do not want to deploy.</span></span> <span data-ttu-id="4e4eb-107">Quando você seleciona uma entidade, todos os objetos dependentes dessa entidade também são selecionados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4e4eb-107">When you select an entity, all of the dependent objects in that entity are also automatically selected.</span></span>  
  
 <span data-ttu-id="4e4eb-108">Você usa o Editor de Pacote de Modelo para selecionar partes de um modelo em um arquivo de pacote que foi criado pela ferramenta MDSModelDeploy (que cria um arquivo de pacote que inclui objetos e dados) ou o assistente de implantação de modelo (que cria um arquivo que inclui apenas a estrutura do modelo).</span><span class="sxs-lookup"><span data-stu-id="4e4eb-108">You use the Model Package Editor to select parts of a model in a package file that was created by either the MDSModelDeploy tool (which creates a package file that includes objects and data) or the Model Deployment wizard (which creates a file that includes only the model structure).</span></span> <span data-ttu-id="4e4eb-109">Depois de editar o modelo no pacote, use a ferramenta MDSModelDeploy para implantar objetos e dados, ou o assistente de implantação de modelo, para implantar apenas a estrutura do modelo.</span><span class="sxs-lookup"><span data-stu-id="4e4eb-109">After editing the model in the package, you use the MDSModelDeploy tool to deploy objects and data, or the Model Deployment wizard to deploy just the model structure.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4e4eb-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="4e4eb-110">Prerequisites</span></span>  
 <span data-ttu-id="4e4eb-111">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="4e4eb-111">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="4e4eb-112">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="4e4eb-112">You must be a model administrator.</span></span> <span data-ttu-id="4e4eb-113">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4e4eb-113">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="4e4eb-114">Deve existir um pacote de modelo a ser editado.</span><span class="sxs-lookup"><span data-stu-id="4e4eb-114">A model package must exist for you to edit.</span></span> <span data-ttu-id="4e4eb-115">Para obter mais informações, consulte [Implantando modelos &#40;Master Data Services&#41;](../../2014/master-data-services/deploying-models-master-data-services.md) e [Criar um pacote de implantação de modelo usando o Assistente](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md) ou [Criar um pacote de implantação de modelo usando MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span><span class="sxs-lookup"><span data-stu-id="4e4eb-115">For more information, see [Deploying Models &#40;Master Data Services&#41;](../../2014/master-data-services/deploying-models-master-data-services.md) and [Create a Model Deployment Package by Using the Wizard](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md) or [Create a Model Deployment Package by Using MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span></span>  
  
### <a name="to-edit-a-model-deployment-package"></a><span data-ttu-id="4e4eb-116">Para editar um pacote de implantação de modelo</span><span class="sxs-lookup"><span data-stu-id="4e4eb-116">To edit a model deployment package</span></span>  
  
1.  <span data-ttu-id="4e4eb-117">No Windows Explorer, no servidor MDS, vá para *drive*:\Arquivos de Programas\Microsoft SQL Server\120\Master Data Services\Configuration.</span><span class="sxs-lookup"><span data-stu-id="4e4eb-117">In Windows Explorer on the MDS server, move to *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span></span>  
  
2.  <span data-ttu-id="4e4eb-118">Execute ModelPackageEditor.exe.</span><span class="sxs-lookup"><span data-stu-id="4e4eb-118">Execute ModelPackageEditor.exe.</span></span>  
  
3.  <span data-ttu-id="4e4eb-119">No assistente de Editor de Pacote de Modelo, clique em **Procurar**, vá até a pasta que contém seus pacotes, selecione um pacote e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="4e4eb-119">In the Model Package Editor wizard, click **Browse**, move to the folder containing your packages, select a package, and then click **Open**.</span></span> <span data-ttu-id="4e4eb-120">Clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="4e4eb-120">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="4e4eb-121">Selecione essas entidades, hierarquias derivadas, exibições de assinaturas ou regras de negócio a serem implantadas.</span><span class="sxs-lookup"><span data-stu-id="4e4eb-121">Select those entities, derived hierarchies, subscriptions views, or business rules that you want to deploy.</span></span> <span data-ttu-id="4e4eb-122">Cancele a seleção do que você não deseja implantar.</span><span class="sxs-lookup"><span data-stu-id="4e4eb-122">Deselect those that you do not want to deploy.</span></span> <span data-ttu-id="4e4eb-123">Clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="4e4eb-123">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="4e4eb-124">Verifique a lista de seleções a ser implantada.</span><span class="sxs-lookup"><span data-stu-id="4e4eb-124">Verify the list of selections to deploy.</span></span> <span data-ttu-id="4e4eb-125">Para alterar, clique em **Voltar** e repita a etapa 4.</span><span class="sxs-lookup"><span data-stu-id="4e4eb-125">To change, click **Back** and repeat step 4.</span></span>  
  
6.  <span data-ttu-id="4e4eb-126">Clique em **Procurar**, vá para a pasta na qual você deseja salvar o pacote parcial e insira o nome de arquivo do pacote parcial (com uma extensão .pkg).</span><span class="sxs-lookup"><span data-stu-id="4e4eb-126">Click **Browse**, move to the folder that you want to save the partial package in, and then enter the file name of the partial package (with a .pkg extension).</span></span> <span data-ttu-id="4e4eb-127">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4e4eb-127">Click **Save**.</span></span>  
  
7.  <span data-ttu-id="4e4eb-128">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="4e4eb-128">Click **Finish**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="4e4eb-129">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="4e4eb-129">Next Steps</span></span>  
  
-   [<span data-ttu-id="4e4eb-130">Implantar um pacote de implantação de modelo usando o Assistente</span><span class="sxs-lookup"><span data-stu-id="4e4eb-130">Deploy a Model Deployment Package by Using the Wizard</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md)  
  
-   [<span data-ttu-id="4e4eb-131">Implantar um pacote de implantação de modelo usando MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="4e4eb-131">Deploy a Model Deployment Package by Using MDSModelDeploy</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md)  
  
  
