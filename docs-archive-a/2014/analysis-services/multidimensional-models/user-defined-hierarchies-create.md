---
title: Criar hierarquias definidas pelo usuário | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- user-defined hierarchies [Analysis Services]
ms.assetid: 16715b85-0630-4a8e-99b0-c0d213cade26
author: minewiskan
ms.author: owend
ms.openlocfilehash: 17e870a2b20125132342db1845689b7c2481d623
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680661"
---
# <a name="create-user-defined-hierarchies"></a><span data-ttu-id="8c75f-102">Criar hierarquias definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="8c75f-102">Create User-Defined Hierarchies</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="8c75f-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]permite que você crie hierarquias definidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="8c75f-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] lets you create user-defined hierarchies.</span></span> <span data-ttu-id="8c75f-104">Uma hierarquia é uma coleção de níveis com base em atributos.</span><span class="sxs-lookup"><span data-stu-id="8c75f-104">A hierarchy is a collection of levels based on attributes.</span></span> <span data-ttu-id="8c75f-105">Por exemplo, uma hierarquia de tempo pode conter níveis de Ano, Trimestre, Mês, Semana e Dia.</span><span class="sxs-lookup"><span data-stu-id="8c75f-105">For example, a time hierarchy might contain the Year, Quarter, Month, Week, and Day levels.</span></span> <span data-ttu-id="8c75f-106">Em algumas hierarquias, cada atributo de membro implica exclusivamente o atributo do membro acima dele.</span><span class="sxs-lookup"><span data-stu-id="8c75f-106">In some hierarchies, each member attribute uniquely implies the member attribute above it.</span></span> <span data-ttu-id="8c75f-107">Algumas vezes, isso é chamado de hierarquia natural.</span><span class="sxs-lookup"><span data-stu-id="8c75f-107">This is sometimes referred to as a natural hierarchy.</span></span> <span data-ttu-id="8c75f-108">Uma hierarquia pode ser usada por usuários finais para procurar dados do cubo.</span><span class="sxs-lookup"><span data-stu-id="8c75f-108">A hierarchy can be used by end users to browse cube data.</span></span> <span data-ttu-id="8c75f-109">Defina hierarquias usando o painel Hierarquias do Designer de Dimensão em [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c75f-109">Define hierarchies by using the Hierarchies pane of Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="8c75f-110">Quando você cria uma hierarquia definida pelo usuário, a hierarquia pode ficar *desbalanceada*.</span><span class="sxs-lookup"><span data-stu-id="8c75f-110">When you create a user-defined hierarchy, the hierarchy might become *ragged*.</span></span> <span data-ttu-id="8c75f-111">Uma hierarquia desbalanceada é local em que o membro pai lógico de pelo menos um membro não está no nível imediatamente acima do membro.</span><span class="sxs-lookup"><span data-stu-id="8c75f-111">A ragged hierarchy is where the logical parent member of at least one member is not in the level immediately above the member.</span></span> <span data-ttu-id="8c75f-112">Se você tiver uma hierarquia desbalanceada, existem configurações que controlam se os membros ausentes estão visíveis e como exibi-los.</span><span class="sxs-lookup"><span data-stu-id="8c75f-112">If you have a ragged hierarchy, there are settings that control whether the missing members are visible and how to display the missing members.</span></span> <span data-ttu-id="8c75f-113">Para obter mais informações, consulte [Hierarquias desbalanceadas](user-defined-hierarchies-ragged-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="8c75f-113">For more information, see [Ragged Hierarchies](user-defined-hierarchies-ragged-hierarchies.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8c75f-114">Para obter mais informações sobre problemas de desempenho relacionadas ao design e à configuração de hierarquias definidas pelo usuário, consulte o [Guia de desempenho do Analysis Services do SQL Server 2005 Analysis Services](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span><span class="sxs-lookup"><span data-stu-id="8c75f-114">For more information about performance issues related to the design and configuration of user-defined hierarchies, see the [SQL Server 2005 Analysis Services Performance Guide](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c75f-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8c75f-115">See Also</span></span>  
 <span data-ttu-id="8c75f-116">[Propriedades da hierarquia de usuário](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md) </span><span class="sxs-lookup"><span data-stu-id="8c75f-116">[User Hierarchy Properties](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md) </span></span>  
 <span data-ttu-id="8c75f-117">[Propriedades de nível &#91;paved sobre&#93;](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-level-properties.md) </span><span class="sxs-lookup"><span data-stu-id="8c75f-117">[Level Properties &#91;Paved Over&#93;](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-level-properties.md) </span></span>  
 [<span data-ttu-id="8c75f-118">Hierarquia pai-filho</span><span class="sxs-lookup"><span data-stu-id="8c75f-118">Parent-Child Hierarchy</span></span>](parent-child-dimension.md)  
  
  
