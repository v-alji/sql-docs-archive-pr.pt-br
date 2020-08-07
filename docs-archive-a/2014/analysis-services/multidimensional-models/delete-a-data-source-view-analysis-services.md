---
title: Excluir uma exibição da fonte de dados (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- deleting data source views
- data source views [Analysis Services], deleting
- removing data source views
ms.assetid: ae3f5ca0-ecbf-4b52-8386-eb457719d854
author: minewiskan
ms.author: owend
ms.openlocfilehash: 24b587e8d8961161ea803915c31d117c11f7cf2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583197"
---
# <a name="delete-a-data-source-view-analysis-services"></a><span data-ttu-id="b3dac-102">Excluir uma exibição da fonte de dados (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="b3dac-102">Delete a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="b3dac-103">Se você não estiver mais usando uma DSV (exibição da fonte de dados) em um projeto OLAP, poderá excluí-la do projeto no [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b3dac-103">If you are no longer using a data source view (DSV) in an OLAP project, you can delete it from the project in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="b3dac-104">A exclusão de uma DSV é permanente.</span><span class="sxs-lookup"><span data-stu-id="b3dac-104">Deleting a DSV is permanent.</span></span> <span data-ttu-id="b3dac-105">Não é possível restaurar uma DSV excluída para um projeto ou banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b3dac-105">You cannot restore a deleted DSV to a [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or database.</span></span>  
  
 <span data-ttu-id="b3dac-106">As DSVs das quais outros objetos dependem não podem ser excluídas de um banco de dados aberto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] pelo [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] em modo online.</span><span class="sxs-lookup"><span data-stu-id="b3dac-106">DSVs that other objects depend on cannot be deleted from an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database opened by [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] in online mode.</span></span> <span data-ttu-id="b3dac-107">Para excluir uma DSV de um projeto que está conectado a um banco de dados executado em um servidor, você primeiro deve excluir todos os objetos no banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que dependem da DSV antes de excluir a própria DSV.</span><span class="sxs-lookup"><span data-stu-id="b3dac-107">To delete a DSV from a project that is connected o a database running on a server, you must first delete all objects in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database that depend on that DSV before deleting the DSV itself.</span></span>  
  
 <span data-ttu-id="b3dac-108">Excluir uma DSV invalidará outros objetos do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que dependem dela; portanto, antes de excluir a DSV, consulte a lista de objetos que ficarão inválidos quando a DSV for removida.</span><span class="sxs-lookup"><span data-stu-id="b3dac-108">Deleting a DSV will invalidate other [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects that depend on it, so before you delete the DSV, you will see the list of objects that will become invalid once the DSV is removed.</span></span> <span data-ttu-id="b3dac-109">Examine esta lista com cuidado para ter certeza de que ela não inclui objetos que você ainda espera usar.</span><span class="sxs-lookup"><span data-stu-id="b3dac-109">Review this list carefully to be sure that it does not include objects you still expect to use.</span></span>  
  
 <span data-ttu-id="b3dac-110">![Caixa de diálogo Excluir Objetos](../media/ssas-olapdsv-deleteobjects.gif "Caixa de diálogo Excluir Objetos")</span><span class="sxs-lookup"><span data-stu-id="b3dac-110">![Delete Objects dialog box](../media/ssas-olapdsv-deleteobjects.gif "Delete Objects dialog box")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3dac-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b3dac-111">See Also</span></span>  
 <span data-ttu-id="b3dac-112">[Exibições da fonte de dados em modelos multidimensionais](data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="b3dac-112">[Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="b3dac-113">Alterar propriedades em uma exibição da fonte de dados &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b3dac-113">Change Properties in a Data Source View &#40;Analysis Services&#41;</span></span>](change-properties-in-a-data-source-view-analysis-services.md)  
  
  
