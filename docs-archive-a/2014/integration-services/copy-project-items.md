---
title: Copiar itens de projeto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data sources [Integration Services], copying
- packages [Integration Services], copying
- copying data source views
- copying data sources
- copying packages
- data source views [Integration Services], copying
ms.assetid: 1606c54d-20f9-49f3-a4ef-caad83a772aa
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3456209c467c3b8474e130181d02304911098d2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574839"
---
# <a name="copy-project-items"></a><span data-ttu-id="42dcf-102">Copiar itens do projeto</span><span class="sxs-lookup"><span data-stu-id="42dcf-102">Copy Project Items</span></span>
  <span data-ttu-id="42dcf-103">Este tópico descreve como copiar objetos em um projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ou entre projetos do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="42dcf-103">This topic describes how to copy objects within an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project or between [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects.</span></span> <span data-ttu-id="42dcf-104">Você também pode copiar objetos entre os outros tipos de projetos do [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] e [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42dcf-104">You can also copy objects between the other types of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] projects, [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] and [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="42dcf-105">Para copiar entre projetos, o projeto deve fazer parte da mesma solução [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="42dcf-105">To copy between projects, the project must be part of the same [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] solution.</span></span> <span data-ttu-id="42dcf-106">Para obter mais informações, consulte [Projetos do Integration Services &#40;SSIS&#41;](integration-services-ssis-projects-and-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="42dcf-106">For more information, see [Integration Services &#40;SSIS&#41; Projects](integration-services-ssis-projects-and-solutions.md).</span></span>  
  
### <a name="to-copy-project-level-items"></a><span data-ttu-id="42dcf-107">Para copiar itens de nível de projeto</span><span class="sxs-lookup"><span data-stu-id="42dcf-107">To copy project level items</span></span>  
  
1.  <span data-ttu-id="42dcf-108">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto ou solução [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] com que deseja trabalhar.</span><span class="sxs-lookup"><span data-stu-id="42dcf-108">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project or solution that you want to work with.</span></span>  
  
2.  <span data-ttu-id="42dcf-109">Expanda o projeto e pasta de item do qual deseja copiar.</span><span class="sxs-lookup"><span data-stu-id="42dcf-109">Expand the project and item folder to copy from.</span></span>  
  
3.  <span data-ttu-id="42dcf-110">Clique com o botão direito do mouse no item e clique em **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="42dcf-110">Right-click the item and click **Copy**.</span></span>  
  
4.  <span data-ttu-id="42dcf-111">Clique com o botão direito do mouse no projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] a ser copiado e clique em **Colar**.</span><span class="sxs-lookup"><span data-stu-id="42dcf-111">Right-click the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project to copy to and click **Paste**.</span></span>  
  
     <span data-ttu-id="42dcf-112">Os itens são copiados automaticamente na pasta correta.</span><span class="sxs-lookup"><span data-stu-id="42dcf-112">The items are automatically copied to the correct folder.</span></span> <span data-ttu-id="42dcf-113">Se você copiar itens que não são pacotes no projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , os itens serão copiados na pasta **Diversos** .</span><span class="sxs-lookup"><span data-stu-id="42dcf-113">If you copy items to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that are not packages, the items are copied to the **Miscellaneous** folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42dcf-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="42dcf-114">See Also</span></span>  
 <span data-ttu-id="42dcf-115">[Integration Services &#40;os pacotes&#41; SSIS](../../2014/integration-services/integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="42dcf-115">[Integration Services &#40;SSIS&#41; Packages](../../2014/integration-services/integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="42dcf-116">Copiar objetos de pacote</span><span class="sxs-lookup"><span data-stu-id="42dcf-116">Copy Package Objects</span></span>](../../2014/integration-services/copy-package-objects.md)  
  
  
