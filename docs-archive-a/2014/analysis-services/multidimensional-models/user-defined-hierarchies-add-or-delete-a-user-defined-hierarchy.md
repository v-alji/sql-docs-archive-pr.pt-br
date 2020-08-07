---
title: Adicionar ou excluir uma hierarquia definida pelo usuário | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Analysis Services], adding
- removing hierarchies
- adding hierarchies
- deleting hierarchies
- hierarchies [Analysis Services], removing
ms.assetid: 953818b4-9543-4c01-bb20-1d45ec6dfb91
author: minewiskan
ms.author: owend
ms.openlocfilehash: d20404a1d93d57221eb830366392eb90600f26c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575396"
---
# <a name="add-or-delete-a-user-defined-hierarchy"></a><span data-ttu-id="d10c3-102">Adicionar ou excluir uma hierarquia definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="d10c3-102">Add or Delete a User-Defined Hierarchy</span></span>
  <span data-ttu-id="d10c3-103">Você adiciona ou remove uma hierarquia definida pelo usuário de uma dimensão na guia **Estrutura da Dimensão** no Designer de Dimensão em [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d10c3-103">You add a user-defined hierarchy to or remove a user-defined hierarchy from a dimension on the **Dimension Structure** tab in Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="d10c3-104">Quando você adicionar uma hierarquia definida pelo usuário, ela não ficará disponível aos usuários até que seja instanciada em uma instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e a dimensão seja processada.</span><span class="sxs-lookup"><span data-stu-id="d10c3-104">When you add a user-defined hierarchy, it is not available to users until it is instantiated in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and the dimension is processed.</span></span> <span data-ttu-id="d10c3-105">Para obter mais informações, consulte [bancos de dados de modelo multidimensional &#40;SSAS&#41;](multidimensional-model-databases-ssas.md) e [processamento de objeto de modelo multidimensional](processing-a-multidimensional-model-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="d10c3-105">For more information, see [Multidimensional Model Databases &#40;SSAS&#41;](multidimensional-model-databases-ssas.md) and [Multidimensional Model Object Processing](processing-a-multidimensional-model-analysis-services.md).</span></span>  
  
### <a name="to-add-a-user-defined-hierarchy-to-a-dimension"></a><span data-ttu-id="d10c3-106">Para adicionar uma hierarquia definida pelo usuário em uma dimensão</span><span class="sxs-lookup"><span data-stu-id="d10c3-106">To add a user-defined hierarchy to a dimension</span></span>  
  
1.  <span data-ttu-id="d10c3-107">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o projeto apropriado do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e abra a dimensão com a qual você quer trabalhar.</span><span class="sxs-lookup"><span data-stu-id="d10c3-107">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the appropriate [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, and then open the dimension with which you want to work.</span></span>  
  
     <span data-ttu-id="d10c3-108">A dimensão será aberta no Designer de Dimensão na guia **Estrutura da Dimensão** .</span><span class="sxs-lookup"><span data-stu-id="d10c3-108">The dimension opens in Dimension Designer on the **Dimension Structure** tab.</span></span>  
  
2.  <span data-ttu-id="d10c3-109">No painel **Atributos** , arraste um atributo que você quer usar na hierarquia definida pelo usuário para o painel **Hierarquias** .</span><span class="sxs-lookup"><span data-stu-id="d10c3-109">From the **Attributes** pane, drag an attribute that you want to use in the user-defined hierarchy to the **Hierarchies** pane.</span></span>  
  
3.  <span data-ttu-id="d10c3-110">Arraste mais atributos para formar níveis na hierarquia definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="d10c3-110">Drag additional attributes to form levels in the user-defined hierarchy.</span></span>  
  
     <span data-ttu-id="d10c3-111">A ordem na qual os atributos são listados na hierarquia é importante.</span><span class="sxs-lookup"><span data-stu-id="d10c3-111">The order in which attributes are listed in the hierarchy is important.</span></span> <span data-ttu-id="d10c3-112">Por exemplo, em uma hierarquia de tempo, os anos devem parecer mais acima na lista de hierarquia do que os dias.</span><span class="sxs-lookup"><span data-stu-id="d10c3-112">For example, in a time hierarchy, years should appear higher in the hierarchy list than days.</span></span>  
  
4.  <span data-ttu-id="d10c3-113">Se desejar, reorganize os níveis na hierarquia definida pelo usuário arrastando-os para as posições corretas.</span><span class="sxs-lookup"><span data-stu-id="d10c3-113">Optionally, rearrange the levels in the user-defined hierarchy by dragging them to the correct positions.</span></span>  
  
5.  <span data-ttu-id="d10c3-114">Se desejar, modifique as propriedades da hierarquia definida pelo usuário ou seus níveis.</span><span class="sxs-lookup"><span data-stu-id="d10c3-114">Optionally, modify properties of the user-defined hierarchy or its levels.</span></span>  
  
     <span data-ttu-id="d10c3-115">Por exemplo, convém especificar um nome para a hierarquia definida pelo usuário, renomear um ou mais de seus níveis e definir um nome personalizado para o Todo o nível.</span><span class="sxs-lookup"><span data-stu-id="d10c3-115">For example, you might want to specify a name for the user-defined hierarchy, rename one or more of its levels, and define a custom name for the All level.</span></span> <span data-ttu-id="d10c3-116">Para obter mais informações, consulte [Propriedades de hierarquia de usuário](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md)e propriedades de [nível &#91;paved sobre&#93;](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-level-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d10c3-116">For more information, see [User Hierarchy Properties](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md), and [Level Properties &#91;Paved Over&#93;](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-level-properties.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d10c3-117">Por padrão, uma hierarquia definida pelo usuário é somente um caminho que permite que os usuários façam busca detalhada para obter informações.</span><span class="sxs-lookup"><span data-stu-id="d10c3-117">By default, a user-defined hierarchy is just a path that enables users to drill down for information.</span></span> <span data-ttu-id="d10c3-118">Porém, se houver relações entre níveis, você pode aumentar o desempenho da consulta configurando relações de atributo entre níveis.</span><span class="sxs-lookup"><span data-stu-id="d10c3-118">However, if relationships exist between levels, you can increase query performance by configuring attribute relationships between levels.</span></span> <span data-ttu-id="d10c3-119">Para obter mais informações, consulte [Relações de atributo](../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md) e [Definir relações de atributo](attribute-relationships-define.md).</span><span class="sxs-lookup"><span data-stu-id="d10c3-119">For more information, see [Attribute Relationships](../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md) and [Define Attribute Relationships](attribute-relationships-define.md).</span></span>  
  
### <a name="to-remove-a-user-defined-hierarchy-from-a-dimension"></a><span data-ttu-id="d10c3-120">Para remover uma hierarquia definida pelo usuário de uma dimensão</span><span class="sxs-lookup"><span data-stu-id="d10c3-120">To remove a user-defined hierarchy from a dimension</span></span>  
  
-   <span data-ttu-id="d10c3-121">Na guia **Estrutura da Dimensão** , clique na hierarquia definida pelo usuário que deseja remover do painel **Hierarquias** .</span><span class="sxs-lookup"><span data-stu-id="d10c3-121">On the **Dimension Structure** tab, click the user-defined hierarchy that you want to remove in the **Hierarchies** pane.</span></span> <span data-ttu-id="d10c3-122">Na barra de ferramentas, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="d10c3-122">On the toolbar, click **Delete**.</span></span>  
  
     - <span data-ttu-id="d10c3-123">ou –</span><span class="sxs-lookup"><span data-stu-id="d10c3-123">or -</span></span>  
  
-   <span data-ttu-id="d10c3-124">Clique com o botão direito do mouse na hierarquia definida pelo usuário que você quer remover do painel **Hierarquias** e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="d10c3-124">Right-click the user-defined hierarchy that you want to remove in the **Hierarchies** pane and then click **Delete**.</span></span>  
  
     - <span data-ttu-id="d10c3-125">ou –</span><span class="sxs-lookup"><span data-stu-id="d10c3-125">or -</span></span>  
  
-   <span data-ttu-id="d10c3-126">Arraste a hierarquia definida pelo usuário para fora da superfície de design.</span><span class="sxs-lookup"><span data-stu-id="d10c3-126">Drag the user-defined hierarchy off of the design surface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d10c3-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d10c3-127">See Also</span></span>  
 <span data-ttu-id="d10c3-128">[Hierarquias de usuário](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="d10c3-128">[User Hierarchies](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies.md) </span></span>  
 [<span data-ttu-id="d10c3-129">Criar hierarquias definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="d10c3-129">Create User-Defined Hierarchies</span></span>](user-defined-hierarchies-create.md)  
  
  
