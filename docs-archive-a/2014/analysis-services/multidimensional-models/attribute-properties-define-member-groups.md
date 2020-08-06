---
title: Definir grupos de membros | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- member groups [Analysis Services]
- grouping members
- DiscretizationMethod property
ms.assetid: 006cc915-c499-4781-b9a7-01ad31bebf6a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 95f9516c7a0077e97af348afa863fe15c8d4528b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685364"
---
# <a name="define-member-groups"></a><span data-ttu-id="23eda-102">Definir grupos de membros</span><span class="sxs-lookup"><span data-stu-id="23eda-102">Define Member Groups</span></span>
  <span data-ttu-id="23eda-103">Se um atributo possuir um grande número de membros, será possível agrupá-los em blocos, reduzindo o número de membros que os usuários veem ao navegar pelos dados da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="23eda-103">If an attribute has a large number of members, you can choose to group those members into buckets, reducing the number of members that users see when they browse the data in a hierarchy.</span></span> <span data-ttu-id="23eda-104">Você pode determinar o número de blocos em que os membros são agrupados e definir um esquema de nomeação para os blocos.</span><span class="sxs-lookup"><span data-stu-id="23eda-104">You can also determine the number of buckets in which the members are groups and set a naming scheme for the buckets.</span></span> <span data-ttu-id="23eda-105">Para obter mais informações, consulte [Agrupar membros de atributo &#40;Diferenciação&#41;](attribute-properties-group-attribute-members.md).</span><span class="sxs-lookup"><span data-stu-id="23eda-105">For more information, see [Group Attribute Members &#40;Discretization&#41;](attribute-properties-group-attribute-members.md).</span></span>  
  
 <span data-ttu-id="23eda-106">Para agrupar os membros, defina a propriedade **DiscretizationMethod** , acessada pela janela **Propriedades** do [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23eda-106">You group members by setting the **DiscretizationMethod** property, which is accessed through the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="23eda-107">Quando você cria grupos de membros, suas alterações ficam indisponíveis para os usuários até que a dimensão seja processada.</span><span class="sxs-lookup"><span data-stu-id="23eda-107">When you create member groups, your changes are not available to users until you process the dimension.</span></span> <span data-ttu-id="23eda-108">Para obter mais informações, consulte [processamento de objeto de modelo multidimensional](processing-a-multidimensional-model-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="23eda-108">For more information, see [Multidimensional Model Object Processing](processing-a-multidimensional-model-analysis-services.md).</span></span>  
  
### <a name="to-create-member-groups"></a><span data-ttu-id="23eda-109">Criar grupos de membros</span><span class="sxs-lookup"><span data-stu-id="23eda-109">To create member groups</span></span>  
  
1.  <span data-ttu-id="23eda-110">Abra a dimensão com a qual você deseja trabalhar.</span><span class="sxs-lookup"><span data-stu-id="23eda-110">Open the dimension that you want to work with.</span></span> <span data-ttu-id="23eda-111">A guia **Estrutura da Dimensão** é aberta por padrão.</span><span class="sxs-lookup"><span data-stu-id="23eda-111">The **Dimension Structure** tab opens by default.</span></span>  
  
2.  <span data-ttu-id="23eda-112">Em **Atributos**, clique com o botão direito do mouse no atributo cujos membros você quer agrupar e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="23eda-112">In **Attributes**, right-click the attribute whose members you want to group, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="23eda-113">Na lista suspensa ao lado de **DiscretizationMethod**, selecione um método para agrupar os membros.</span><span class="sxs-lookup"><span data-stu-id="23eda-113">From the drop-down list next to **DiscretizationMethod**, select a method by which to group the members.</span></span> <span data-ttu-id="23eda-114">Para obter mais informações sobre as configurações de **DiscretizationMethod**, consulte [Agrupar membros de atributo &#40;Discretização&#41;](attribute-properties-group-attribute-members.md).</span><span class="sxs-lookup"><span data-stu-id="23eda-114">For more information about **DiscretizationMethod** settings, see [Group Attribute Members &#40;Discretization&#41;](attribute-properties-group-attribute-members.md).</span></span>  
  
  
