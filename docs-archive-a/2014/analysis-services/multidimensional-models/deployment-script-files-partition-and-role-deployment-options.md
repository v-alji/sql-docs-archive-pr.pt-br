---
title: Especificando opções de implantação de partição e função | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- input files [Analysis Services]
- partitions [Analysis Services], deployment options
- Analysis Services deployments, roles
- Analysis Services deployments, partitions
- Analysis Services Deployment Wizard, roles
- Analysis Services Deployment Wizard, partitions
- deploying [Analysis Services], roles
- roles [Analysis Services], deployment options
- deploying [Analysis Services], partitions
- modifying role deployments
- modifying partition deployments
ms.assetid: e9b9ca57-a5cc-4fc0-87b5-305257038d56
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8c8dd7bcb482c2d28a18e3039f5acb777b121202
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582642"
---
# <a name="specifying-partition-and-role-deployment-options"></a><span data-ttu-id="7e6e0-102">Especificando opções de implantação de função e de partição</span><span class="sxs-lookup"><span data-stu-id="7e6e0-102">Specifying Partition and Role Deployment Options</span></span>
  <span data-ttu-id="7e6e0-103">O [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Assistente de implantação lê as opções de implantação de partição e função do \<*project name*> arquivo. deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="7e6e0-103">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard reads the partition and role deployment options from the \<*project name*>.deploymentoptions file.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="7e6e0-104">cria esse arquivo quando você compila o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projeto.</span><span class="sxs-lookup"><span data-stu-id="7e6e0-104">creates this file when you build the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="7e6e0-105">usa as opções de implantação de partição e função do projeto atual quando o \<*project name*> arquivo. deploymentoptions é criado.</span><span class="sxs-lookup"><span data-stu-id="7e6e0-105">uses the partition and role deployment options of the current project when the \<*project name*>.deploymentoptions file is created.</span></span> <span data-ttu-id="7e6e0-106">Para obter mais informações sobre parâmetros de configuração, consulte [Understanding the Input Files Used to Create the Deployment Script](deployment-script-files-input-used-to-create-deployment-script.md).</span><span class="sxs-lookup"><span data-stu-id="7e6e0-106">For more information about configuration settings, see [Understanding the Input Files Used to Create the Deployment Script](deployment-script-files-input-used-to-create-deployment-script.md).</span></span>  
  
## <a name="reviewing-the-partition-and-role-deployment-options"></a><span data-ttu-id="7e6e0-107">Revisando as opções de implantação de partição e de função</span><span class="sxs-lookup"><span data-stu-id="7e6e0-107">Reviewing the Partition and Role Deployment Options</span></span>  
 <span data-ttu-id="7e6e0-108">As opções de implantação no \<*project name*> arquivo. deploymentoptions incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7e6e0-108">The deployment options in the \<*project name*>.deploymentoptions file include the following:</span></span>  
  
 <span data-ttu-id="7e6e0-109">**Opções de implantação de partição**</span><span class="sxs-lookup"><span data-stu-id="7e6e0-109">**Partition deployment options**</span></span>  
 <span data-ttu-id="7e6e0-110">O \<*project name*> arquivo. deploymentoptions especifica se as partições existentes no banco de dados de destino são retidas ou substituídas (padrão).</span><span class="sxs-lookup"><span data-stu-id="7e6e0-110">The \<*project name*>.deploymentoptions file specifies whether existing partitions in the destination database are retained or overwritten (default).</span></span> <span data-ttu-id="7e6e0-111">Se as partições existentes forem retidas, só serão implantadas partições novas e os projetos de partições e agregação em todos os grupos de medidas existentes ficarão inalterados.</span><span class="sxs-lookup"><span data-stu-id="7e6e0-111">If existing partitions are retained, only new partitions will be deployed, and the partitions and aggregation designs on all existing measure groups are left unchanged.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7e6e0-112">Se o grupo de medidas no qual a partição existe for excluído, a partição será excluída automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7e6e0-112">If the measure group in which the partition exists is deleted, the partition is automatically deleted.</span></span>  
  
 <span data-ttu-id="7e6e0-113">**Opções de implantação de função**</span><span class="sxs-lookup"><span data-stu-id="7e6e0-113">**Role deployment options**</span></span>  
 <span data-ttu-id="7e6e0-114">O \<*project name*> arquivo. deploymentoptions especifica uma das seguintes opções de implantação de função:</span><span class="sxs-lookup"><span data-stu-id="7e6e0-114">The \<*project name*>.deploymentoptions file specifies one of the following role deployment options:</span></span>  
  
-   <span data-ttu-id="7e6e0-115">As funções e os membros de função existentes no banco de dados de destino são retidos e apenas novas funções e membros de função são implantados.</span><span class="sxs-lookup"><span data-stu-id="7e6e0-115">Existing roles and role members in the destination database are retained, and only new roles and role members are deployed.</span></span>  
  
-   <span data-ttu-id="7e6e0-116">Todas as funções e os membros de função existentes no banco de dados de destino são substituídos pelas funções e pelos membros sendo implantados.</span><span class="sxs-lookup"><span data-stu-id="7e6e0-116">All existing roles and members in the destination database are replaced by the roles and members being deployed.</span></span>  
  
-   <span data-ttu-id="7e6e0-117">As funções e os membros de função existentes no banco de dados de destino são retidos e nenhuma nova função será implantada.</span><span class="sxs-lookup"><span data-stu-id="7e6e0-117">Existing roles and role members in the destination database are retained, and no new roles are deployed.</span></span>  
  
-   <span data-ttu-id="7e6e0-118">**Nota** Quando funções e membros existentes são retidos, as permissões associadas a essas funções são redefinidas como nenhuma.</span><span class="sxs-lookup"><span data-stu-id="7e6e0-118">**Note** When existing roles and members are retained, the permissions associated with those roles are reset to none.</span></span> <span data-ttu-id="7e6e0-119">As permissões de segurança são contidas pelos objetos que protegem, não pelas funções de segurança com que estão associadas.</span><span class="sxs-lookup"><span data-stu-id="7e6e0-119">Security permissions are contained by the objects they secure, not by the security roles with which they are associated.</span></span> <span data-ttu-id="7e6e0-120">Para obter mais informações sobre como trabalhar com esse comportamento usando o assistente de implantação do Analysis Service, consulte "reter funções e membros" na base de dados de conhecimento Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7e6e0-120">For more information about how to work with this behavior by using the Analysis Service Deployment Wizard, see 'Retain Roles and Members' in the Microsoft Knowledge Base.</span></span>  
  
## <a name="modifying-the-partition-and-role-deployment-options"></a><span data-ttu-id="7e6e0-121">Modificando as opções de implantação de partição e de função</span><span class="sxs-lookup"><span data-stu-id="7e6e0-121">Modifying the Partition and Role Deployment Options</span></span>  
 <span data-ttu-id="7e6e0-122">Talvez seja necessário implantar o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projeto usando opções de partição e função diferentes das armazenadas no \<*project name*> arquivo. deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="7e6e0-122">You may have to deploy the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project using different partition and role options than those stored in the \<*project name*>.deploymentoptions file.</span></span> <span data-ttu-id="7e6e0-123">Por exemplo, talvez você queira reter partições, funções e membros de função existentes, em vez de substituir todas as partições, funções e membros existentes, conforme indicado no \<*project name*> arquivo. deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="7e6e0-123">For example, you may want to retain existing partitions, roles, and role members, instead of replacing all existing partitions, roles, and members as indicated in the \<*project name*>.deploymentoptions file.</span></span>  
  
 <span data-ttu-id="7e6e0-124">Para modificar a implantação de partições e funções em um [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projeto do, você não pode alterar as configurações de partição e de funções no projeto, pois a *\<project name>* caixa de diálogo **páginas de propriedades** no não [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] exibe essas opções.</span><span class="sxs-lookup"><span data-stu-id="7e6e0-124">To modify the deployment of partitions and roles in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, you cannot change the partition and roles settings within the project because the *\<project name>* **Properties Pages** dialog box in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] does not display these options.</span></span> <span data-ttu-id="7e6e0-125">Se você quiser alterar as opções de implantação para funções e partições, deverá alterar essas informações no \<*project name*> próprio arquivo. deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="7e6e0-125">If you want to change the deployment options for roles and partitions, you must change this information within the \<*project name*>.deploymentoptions file itself.</span></span> <span data-ttu-id="7e6e0-126">O procedimento a seguir descreve como alterar as opções de implantação de partição e função no \<*project name*> arquivo. deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="7e6e0-126">The following procedure describes how to change the partition and role deployment options within the \<*project name*>.deploymentoptions file.</span></span>  
  
#### <a name="to-change-the-deployment-of-partitions-or-roles-after-the-input-files-have-been-generated"></a><span data-ttu-id="7e6e0-127">Para alterar a implantação de partições ou de funções depois que os arquivos de entrada tiverem sido gerados</span><span class="sxs-lookup"><span data-stu-id="7e6e0-127">To change the deployment of partitions or roles after the input files have been generated</span></span>  
  
-   <span data-ttu-id="7e6e0-128">Execute o Assistente para Implantação do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] interativamente, e na página **Opções de implantação de partição e de função** , especifique as novas opções de implantação para as partições e funções.</span><span class="sxs-lookup"><span data-stu-id="7e6e0-128">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard interactively, and on the **Partition and Role Deployment Options** page, specify new deployment options for the partitions and roles.</span></span>  
  
     <span data-ttu-id="7e6e0-129">- ou -</span><span class="sxs-lookup"><span data-stu-id="7e6e0-129">-or-</span></span>  
  
-   <span data-ttu-id="7e6e0-130">Execute o Assistente para Implantação do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] no prompt de comando e defina o assistente para ser executado em modo de arquivo de resposta.</span><span class="sxs-lookup"><span data-stu-id="7e6e0-130">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard at the command prompt, and set the wizard to run in answer file mode.</span></span> <span data-ttu-id="7e6e0-131">(Para obter mais informações sobre o modo de arquivo de resposta, consulte [executando o assistente de implantação de Analysis Services](running-the-analysis-services-deployment-wizard.md).)</span><span class="sxs-lookup"><span data-stu-id="7e6e0-131">(For more information about answer file mode, see [Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md).)</span></span>  
  
     <span data-ttu-id="7e6e0-132">- ou -</span><span class="sxs-lookup"><span data-stu-id="7e6e0-132">-or-</span></span>  
  
-   <span data-ttu-id="7e6e0-133">Abra o \<*project name*> . deploymentoptions em qualquer editor de texto e altere manualmente as opções.</span><span class="sxs-lookup"><span data-stu-id="7e6e0-133">Open the \<*project name*>.deploymentoptions in any text editor and manually change the options.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e6e0-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7e6e0-134">See Also</span></span>  
 <span data-ttu-id="7e6e0-135">[Especificando o destino de instalação](deployment-script-files-specifying-the-installation-target.md) </span><span class="sxs-lookup"><span data-stu-id="7e6e0-135">[Specifying the Installation Target](deployment-script-files-specifying-the-installation-target.md) </span></span>  
 <span data-ttu-id="7e6e0-136">[Especificando definições de configuração para implantação de solução](deployment-script-files-solution-deployment-config-settings.md) </span><span class="sxs-lookup"><span data-stu-id="7e6e0-136">[Specifying Configuration Settings for Solution Deployment](deployment-script-files-solution-deployment-config-settings.md) </span></span>  
 [<span data-ttu-id="7e6e0-137">Especificando opções de processamento</span><span class="sxs-lookup"><span data-stu-id="7e6e0-137">Specifying Processing Options</span></span>](deployment-script-files-specifying-processing-options.md)  
  
  
