---
title: Especificando o destino de instalação | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- input files [Analysis Services]
- installation targets [Analysis Services]
- Analysis Services deployments, installation targets
- Analysis Services Deployment Wizard, installation targets
- deploying [Analysis Services], installation targets
- modifying installation targets
ms.assetid: cb706817-6f63-4771-92c3-b70030bbce3d
author: minewiskan
ms.author: owend
ms.openlocfilehash: e830fc353898e3ec835b338e84765a0cad0de43f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574941"
---
# <a name="specifying-the-installation-target"></a><span data-ttu-id="483ab-102">Especificando o destino de instalação</span><span class="sxs-lookup"><span data-stu-id="483ab-102">Specifying the Installation Target</span></span>
  <span data-ttu-id="483ab-103">O [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Assistente de implantação lê as informações de destino da instalação do \<*project name*> arquivo. deploymenttargets.</span><span class="sxs-lookup"><span data-stu-id="483ab-103">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard reads the installation target information from the \<*project name*>.deploymenttargets file.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="483ab-104">cria esse arquivo quando você compila o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projeto.</span><span class="sxs-lookup"><span data-stu-id="483ab-104">creates this file when you build the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="483ab-105">usa o banco de dados e o servidor especificados na página **implantação** da *\<project name>* caixa de diálogo páginas de **Propriedades** para criar o \<*project name*> arquivo. targets.</span><span class="sxs-lookup"><span data-stu-id="483ab-105">uses the database and server specified on the **Deployment** page of the *\<project name>* **Properties Pages** dialog box to create the \<*project name*>.targets file.</span></span>  
  
## <a name="modifying-the-installation-target-for-deployment"></a><span data-ttu-id="483ab-106">Modificando o destino de instalação para a implantação</span><span class="sxs-lookup"><span data-stu-id="483ab-106">Modifying the Installation Target for Deployment</span></span>  
 <span data-ttu-id="483ab-107">Em alguns casos, talvez seja necessário implantar um projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] em um banco de dados ou instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] diferente do especificado na página **Implantação** .</span><span class="sxs-lookup"><span data-stu-id="483ab-107">In some situations, you may need to deploy an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project to a database or [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance that is different than the one specified on the **Deployment** page.</span></span> <span data-ttu-id="483ab-108">Por exemplo, você talvez queira implantar o projeto em um servidor para teste antes da implantação e, em seguida, implantá-lo em um servidor de produção após a conclusão do teste.</span><span class="sxs-lookup"><span data-stu-id="483ab-108">For example, you may want to deploy the project to a server for testing before deployment, and then deploy it to a production server after testing is finished.</span></span> <span data-ttu-id="483ab-109">Também é possível implantar um projeto concluído e testado em vários servidores de produção em um cluster de Balanceamento de Carga de Rede ou em um servidor de preparação e em um de produção.</span><span class="sxs-lookup"><span data-stu-id="483ab-109">You may also want to deploy a completed and tested project to multiple production servers in a Network Load Balancing cluster, or to a staging server and a production server.</span></span>  
  
 <span data-ttu-id="483ab-110">Para implantar um projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] em um banco de dados ou instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] diferente, altere o destino de instalação no arquivo de entrada usando um dos métodos descritos no procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="483ab-110">To deploy an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project to a different database or [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, you can change the installation target in the input file by using one of the methods described in the following procedure.</span></span>  
  
#### <a name="to-change-the-installation-target-after-the-input-files-have-been-generated"></a><span data-ttu-id="483ab-111">Para alterar o destino de instalação depois que os arquivos de entrada tiverem sido gerados</span><span class="sxs-lookup"><span data-stu-id="483ab-111">To change the installation target after the input files have been generated</span></span>  
  
-   <span data-ttu-id="483ab-112">Execute o Assistente para Implantação do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] de modo interativo.</span><span class="sxs-lookup"><span data-stu-id="483ab-112">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard interactively.</span></span> <span data-ttu-id="483ab-113">Na página **Destino da Instalação** , especifique um novo destino para a instância e o banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="483ab-113">On the **Installation Target** page, specify a new destination for the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and database.</span></span>  
  
     <span data-ttu-id="483ab-114">- ou -</span><span class="sxs-lookup"><span data-stu-id="483ab-114">-or-</span></span>  
  
-   <span data-ttu-id="483ab-115">Execute o Assistente para Implantação do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] no prompt de comando e defina o assistente para executar em modo de arquivo de resposta.</span><span class="sxs-lookup"><span data-stu-id="483ab-115">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard at the command prompt and set the wizard to run in answer file mode.</span></span> <span data-ttu-id="483ab-116">Para obter mais informações sobre o modo de arquivo de resposta, consulte [Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="483ab-116">For more information about answer file mode, see [Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md).</span></span>  
  
     <span data-ttu-id="483ab-117">- ou -</span><span class="sxs-lookup"><span data-stu-id="483ab-117">-or-</span></span>  
  
-   <span data-ttu-id="483ab-118">Modifique o \<*project name*> arquivo. deploymenttargets usando qualquer editor de texto.</span><span class="sxs-lookup"><span data-stu-id="483ab-118">Modify the \<*project name*>.deploymenttargets file by using any text editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="483ab-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="483ab-119">See Also</span></span>  
 <span data-ttu-id="483ab-120">[Especificando opções de implantação de partição e função](deployment-script-files-partition-and-role-deployment-options.md) </span><span class="sxs-lookup"><span data-stu-id="483ab-120">[Specifying Partition and Role Deployment Options](deployment-script-files-partition-and-role-deployment-options.md) </span></span>  
 <span data-ttu-id="483ab-121">[Especificando definições de configuração para implantação de solução](deployment-script-files-solution-deployment-config-settings.md) </span><span class="sxs-lookup"><span data-stu-id="483ab-121">[Specifying Configuration Settings for Solution Deployment](deployment-script-files-solution-deployment-config-settings.md) </span></span>  
 [<span data-ttu-id="483ab-122">Especificando opções de processamento</span><span class="sxs-lookup"><span data-stu-id="483ab-122">Specifying Processing Options</span></span>](deployment-script-files-specifying-processing-options.md)  
  
  
