---
title: Reimplantação de pacotes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- redeploying packages [Integration Services]
- deploying packages [Integration Services], redeploying
ms.assetid: 86806efb-8cf4-4f9d-9824-1152cb4c495c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4c5286d406d96f62fc74eb619f7e7a6064fde2a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679411"
---
# <a name="redeployment-of-packages"></a><span data-ttu-id="67957-102">Reimplantação de pacotes</span><span class="sxs-lookup"><span data-stu-id="67957-102">Redeployment of Packages</span></span>
  <span data-ttu-id="67957-103">Após a implantação de um projeto, talvez seja necessário atualizar ou estender a funcionalidade de pacotes e reimplantar o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém os pacotes atualizados.</span><span class="sxs-lookup"><span data-stu-id="67957-103">After a project is deployed, you may need to update or extend package functionality and then redeploy the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the updated packages.</span></span> <span data-ttu-id="67957-104">Como parte do processo de reimplantação dos pacotes, você deve revisar as propriedades de configuração incluídas no utilitário de implantação.</span><span class="sxs-lookup"><span data-stu-id="67957-104">As part of the process of redeploying packages, you should review the configuration properties that are included in the deployment utility.</span></span> <span data-ttu-id="67957-105">Por exemplo, você pode desejar não permitir mudanças de configuração depois que o pacote for reimplantado.</span><span class="sxs-lookup"><span data-stu-id="67957-105">For example, you may not want to allow configuration changes after the package is redeployed.</span></span>  
  
## <a name="process-for-redeployment"></a><span data-ttu-id="67957-106">Processo de reimplantação</span><span class="sxs-lookup"><span data-stu-id="67957-106">Process for Redeployment</span></span>  
 <span data-ttu-id="67957-107">Após a conclusão da atualização dos pacotes, você deve recriar o projeto, copiar a pasta de implantação para o computador de destino e executar novamente o Assistente de Instalação de Pacotes.</span><span class="sxs-lookup"><span data-stu-id="67957-107">After you finish updating the packages, you rebuild the project, copy the deployment folder to the target computer, and then rerun the Package Installation Wizard.</span></span>  
  
 <span data-ttu-id="67957-108">Se você atualizar apenas alguns pacotes do projeto, talvez não queira reimplantar o projeto todo.</span><span class="sxs-lookup"><span data-stu-id="67957-108">If you update only a few packages in the project, you may not want to redeploy the entire project.</span></span> <span data-ttu-id="67957-109">Para implantar apenas alguns pacotes, você pode criar um novo projeto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , adicionar os pacotes atualizados ao novo projeto e compilar e implantar o projeto.</span><span class="sxs-lookup"><span data-stu-id="67957-109">To deploy only a few packages, you can create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, add the updated packages to the new project, and then build and deploy the project.</span></span> <span data-ttu-id="67957-110">As configurações de pacotes são copiadas automaticamente com o pacote quando você adiciona o pacote a um projeto diferente.</span><span class="sxs-lookup"><span data-stu-id="67957-110">Package configurations are automatically copied with the package when you add the package to a different project.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="67957-111">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="67957-111">Related Tasks</span></span>  
 [<span data-ttu-id="67957-112">Implantar pacotes usando o utilitário de implantação</span><span class="sxs-lookup"><span data-stu-id="67957-112">Deploy Packages by Using the Deployment Utility</span></span>](../../2014/integration-services/deploy-packages-by-using-the-deployment-utility.md)  
  
  
