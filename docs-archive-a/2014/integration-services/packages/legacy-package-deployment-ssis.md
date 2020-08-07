---
title: Implantação de pacote (SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, deploying
- deploying packages [Integration Services]
- SQL Server Integration Services packages, deploying
- deploying packages [Integration Services], about deploying packages
- packages [Integration Services], deploying
- SSIS packages, deploying
ms.assetid: 0f5fc7be-e37e-4ecd-ba99-697c8ae3436f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 32627eddf5e7a696decd549e9b87ebb5c3b9d031
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575201"
---
# <a name="package-deployment-ssis"></a><span data-ttu-id="01323-102">Implantação de pacotes (SSIS)</span><span class="sxs-lookup"><span data-stu-id="01323-102">Package Deployment (SSIS)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="01323-103">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] inclui ferramentas e assistentes que simplificam a implantação de pacotes do computador de desenvolvimento para o servidor de produção ou para outros computadores.</span><span class="sxs-lookup"><span data-stu-id="01323-103">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes tools and wizards that make it simple to deploy packages from the development computer to the production server or to other computers.</span></span>  
  
 <span data-ttu-id="01323-104">Há quatro etapas no processo de implantação de pacotes:</span><span class="sxs-lookup"><span data-stu-id="01323-104">There are four steps in the package deployment process:</span></span>  
  
1.  <span data-ttu-id="01323-105">A primeira etapa é opcional e envolve a criação de configurações de pacotes que atualizam as propriedades dos elementos dos pacotes em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="01323-105">The first optional step is optional and involves creating package configurations that update properties of package elements at run time.</span></span> <span data-ttu-id="01323-106">As configurações são incluídas automaticamente quando se implantam os pacotes.</span><span class="sxs-lookup"><span data-stu-id="01323-106">The configurations are automatically included when you deploy the packages.</span></span>  
  
2.  <span data-ttu-id="01323-107">A segunda etapa é desenvolver o projeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] para criar um utilitário de implantação de pacote.</span><span class="sxs-lookup"><span data-stu-id="01323-107">The second step is to build the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project to create a package deployment utility.</span></span> <span data-ttu-id="01323-108">O utilitário de implantação para o projeto contém os pacotes que você quer implantar</span><span class="sxs-lookup"><span data-stu-id="01323-108">The deployment utility for the project contains the packages that you want to deploy</span></span>  
  
3.  <span data-ttu-id="01323-109">A terceira etapa é copiar a pasta de implantação que foi criada quando você desenvolveu o projeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] para o computador de destino.</span><span class="sxs-lookup"><span data-stu-id="01323-109">The third step is to copy the deployment folder that was created when you built the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project to the target computer.</span></span>  
  
4.  <span data-ttu-id="01323-110">A quarta etapa é executar no computador de destino o Assistente de Instalação de Pacotes para instalar os pacotes no sistema de arquivos ou em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="01323-110">The fourth step is to run, on the target computer, the Package Installation Wizard to install the packages to the file system or to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="01323-111">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="01323-111">Related Tasks</span></span>  
 <span data-ttu-id="01323-112">Para obter informações sobre como criar um utilitário de implantação, consulte [Criar um utilitário de implantação](../create-a-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="01323-112">For information about how to create a deployment utility, see [Create a Deployment Utility](../create-a-deployment-utility.md).</span></span>  
  
 <span data-ttu-id="01323-113">Para obter informações sobre como implantar pacotes usando o utilitário de implantação, consulte [Implantar pacotes usando o utilitário de implantação](../deploy-packages-by-using-the-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="01323-113">For information about how to deploy packages using the deployment utility, see [Deploy Packages by Using the Deployment Utility](../deploy-packages-by-using-the-deployment-utility.md).</span></span>  
  
 <span data-ttu-id="01323-114">Para obter informações sobre como criar configurações de pacote, consulte [Criar configurações de pacote](../create-package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="01323-114">For information about how to create package configurations, see [Create Package Configurations](../create-package-configurations.md).</span></span>  
  
  
