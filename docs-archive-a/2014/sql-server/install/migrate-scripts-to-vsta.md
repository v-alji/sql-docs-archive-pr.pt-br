---
title: Migrar scripts para o VSTA | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- SSIS Script task, converting scripts
- Script component [Integration Services], converting scripts
- Script task [Integration Services], converting scripts
- SSIS Script component, converting scripts
ms.assetid: d685098b-86a1-46bf-939a-63d56951e009
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: afbc19c35f99a5abc5a6ebd92024e42baa6a9237
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684996"
---
# <a name="migrate-scripts-to-vsta"></a><span data-ttu-id="9877b-102">Migrar scripts para o VSTA</span><span class="sxs-lookup"><span data-stu-id="9877b-102">Migrate Scripts to VSTA</span></span>
  <span data-ttu-id="9877b-103">Quando você atualiza [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] pacotes para [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] o, o migra os scripts em quaisquer tarefas de script ou componentes de script para o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] VSTA (Tools for Applications).</span><span class="sxs-lookup"><span data-stu-id="9877b-103">When you upgrade [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] packages to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] migrates the scripts in any Script tasks or Script components to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span> <span data-ttu-id="9877b-104">O VSTA é o ambiente de script usado pelo [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9877b-104">VSTA is the scripting environment that [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] uses.</span></span> <span data-ttu-id="9877b-105">No [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , o ambiente de script do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] é [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] para aplicativos (Vsa).</span><span class="sxs-lookup"><span data-stu-id="9877b-105">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], the scripting environment for [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] is [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] for Applications (VSA).</span></span>  
  
 <span data-ttu-id="9877b-106">Se os scripts em qualquer uma das tarefas ou componentes de Script fizerem referência a interfaces, talvez você precise modificar essas referências antes de atualizar o pacote.</span><span class="sxs-lookup"><span data-stu-id="9877b-106">If the scripts in either the Script tasks or Script components reference interfaces, you might have to modify those references before you upgrade the package.</span></span> <span data-ttu-id="9877b-107">Caso contrário, o pacote não será atualizado ou os scripts não serão validados, dependendo do método de atualização utilizado.</span><span class="sxs-lookup"><span data-stu-id="9877b-107">Otherwise, the package will not be upgraded or the scripts will not be validated, depending on the upgrade method that you use.</span></span> <span data-ttu-id="9877b-108">Para modificar essas referências, substitua referências a interfaces IDTS*xxx*90 com referências às interfaces IDTS*xxx*100 correspondentes.</span><span class="sxs-lookup"><span data-stu-id="9877b-108">To modify these references, replace references to IDTS*xxx*90 interfaces with references to the corresponding IDTS*xxx*100 interfaces.</span></span>  
  
 <span data-ttu-id="9877b-109">Para obter mais informações sobre como migrar scripts e atualizar pacotes, consulte [atualizar pacotes de Integration Services](../../integration-services/install-windows/upgrade-integration-services-packages.md).</span><span class="sxs-lookup"><span data-stu-id="9877b-109">For more information about how to migrate scripts and upgrade packages, see [Upgrade Integration Services Packages](../../integration-services/install-windows/upgrade-integration-services-packages.md).</span></span>  
  
## <a name="understanding-migration-failures"></a><span data-ttu-id="9877b-110">Noções básicas sobre falhas de migração</span><span class="sxs-lookup"><span data-stu-id="9877b-110">Understanding Migration Failures</span></span>  
 <span data-ttu-id="9877b-111">Quando você migra os scripts, a migração pode falhar por um dos seguintes motivos:</span><span class="sxs-lookup"><span data-stu-id="9877b-111">When you migrate the scripts, the migration can fail because of one of the following reasons:</span></span>  
  
-   <span data-ttu-id="9877b-112">O ponto de entrada do script VSA foi renomeado.</span><span class="sxs-lookup"><span data-stu-id="9877b-112">The entry point for the VSA script was renamed.</span></span>  
  
     <span data-ttu-id="9877b-113">O ponto de entrada especifica o método na classe `ScriptMain` do projeto VSTA que o runtime do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] chama como ponto de entrada para o código da tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="9877b-113">The entry point specifies the method in the `ScriptMain` class in the VSTA project that the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] runtime calls as the entry point into the Script task code.</span></span> <span data-ttu-id="9877b-114">A classe `ScriptMain` é a classe padrão gerada pelos modelos de script.</span><span class="sxs-lookup"><span data-stu-id="9877b-114">The `ScriptMain` class is the default class that the script templates generate.</span></span>  
  
-   <span data-ttu-id="9877b-115">Não há nenhum ponto de entrada ou existem vários pontos de entrada no script VSA.</span><span class="sxs-lookup"><span data-stu-id="9877b-115">There is no entry point or there are multiple entry points in the VSA script.</span></span>  
  
-   <span data-ttu-id="9877b-116">Não foi possível adicionar referências de assembly.</span><span class="sxs-lookup"><span data-stu-id="9877b-116">Assembly references could not be added.</span></span>  
  
-   <span data-ttu-id="9877b-117">A classe `ScriptMain` foi modificada para herdar de outras classes além da classe `ScriptObjectModelSSIS`.</span><span class="sxs-lookup"><span data-stu-id="9877b-117">The `ScriptMain` class was modified to inherit from other classes in addition to the `ScriptObjectModelSSIS` class.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="9877b-118">[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]o não oferece suporte a várias heranças.</span><span class="sxs-lookup"><span data-stu-id="9877b-118">[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] does not support multiple inheritance.</span></span>  
  
 <span data-ttu-id="9877b-119">Você não pode converter um script VSA que usa [!INCLUDE[vbprvblong](../../includes/vbprvblong-md.md)] o para um script do VSTA que usa o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csharp_orcas_long](../../includes/csharp-orcas-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9877b-119">You cannot convert a VSA script that uses [!INCLUDE[vbprvblong](../../includes/vbprvblong-md.md)] to a VSTA script that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csharp_orcas_long](../../includes/csharp-orcas-long-md.md)].</span></span> <span data-ttu-id="9877b-120">No entanto, você pode criar um novo script do VSTA que usa o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csharp_orcas_long](../../includes/csharp-orcas-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9877b-120">However, you can create a new VSTA script that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csharp_orcas_long](../../includes/csharp-orcas-long-md.md)].</span></span> <span data-ttu-id="9877b-121">Para obter mais informações, consulte [Codificando e depurando a tarefa Script](../../integration-services/control-flow/script-task.md) e [Codificando e depurando o componente Script](../../integration-services/data-flow/transformations/script-component.md).</span><span class="sxs-lookup"><span data-stu-id="9877b-121">For more information, see [Coding and Debugging the Script Task](../../integration-services/control-flow/script-task.md) and [Coding and Debugging the Script Component](../../integration-services/data-flow/transformations/script-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9877b-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9877b-122">See Also</span></span>  
 [<span data-ttu-id="9877b-123">Estendendo pacotes com scripts</span><span class="sxs-lookup"><span data-stu-id="9877b-123">Extending Packages with Scripting</span></span>](../../relational-databases/server-management-objects-smo/tasks/scripting.md)  
  
  
