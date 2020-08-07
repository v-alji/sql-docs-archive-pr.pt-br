---
title: 'Lição 4: definindo propriedades avançadas de atributo e dimensão | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0e86b9be-e47d-4bb4-87eb-136ff3a61aef
author: minewiskan
ms.author: owend
ms.openlocfilehash: deb2d9c40ad5024f6cc4ba6e9148df41a168c6e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681893"
---
# <a name="lesson-4-defining-advanced-attribute-and-dimension-properties"></a><span data-ttu-id="1d4cc-102">Lição 4: Como definir propriedades avançadas de dimensão e de atributo</span><span class="sxs-lookup"><span data-stu-id="1d4cc-102">Lesson 4: Defining Advanced Attribute and Dimension Properties</span></span>
  <span data-ttu-id="1d4cc-103">Nesta lição, você aprenderá como usar algumas propriedades avançadas de atributos, hierarquias de atributo e propriedades de dimensão.</span><span class="sxs-lookup"><span data-stu-id="1d4cc-103">In this lesson, you will learn how to use some of the advanced properties of attributes, attribute hierarchies, and dimension properties.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1d4cc-104">Esta lição baseia-se na versão aprimorada do projeto do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que você concluiu nas três primeiras lições deste tutorial.</span><span class="sxs-lookup"><span data-stu-id="1d4cc-104">This lesson is based on an enhanced version of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project that you completed in the first three lessons of this tutorial.</span></span> <span data-ttu-id="1d4cc-105">A primeira tarefa nesta lição descreve como localizar o projeto de exemplo apropriado que deve ser usado na lição e a diferença entre este projeto e o projeto que você criou nas três primeiras lições.</span><span class="sxs-lookup"><span data-stu-id="1d4cc-105">The first task in this lesson describes where to locate the appropriate sample project to use for the lesson, and the difference between this project and the project that you created in the first three lessons.</span></span>  
  
 <span data-ttu-id="1d4cc-106">Esta lição contém as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="1d4cc-106">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="1d4cc-107">Usando uma versão modificada do projeto do Tutorial do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="1d4cc-107">Using a Modified Version of the Analysis Services Tutorial Project</span></span>](lesson-4-1-using-a-modified-version-of-the-analysis-services-tutorial-project.md)  
 <span data-ttu-id="1d4cc-108">Nesta tarefa, você abrirá, revisará e implantará uma versão modificada do projeto Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , que contém vários grupos de medidas e dimensões adicionais.</span><span class="sxs-lookup"><span data-stu-id="1d4cc-108">In this task, you open, review, and deploy a modified version of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, which has multiple measure groups and additional dimensions.</span></span>  
  
 [<span data-ttu-id="1d4cc-109">Definindo propriedades de atributo pai em uma hierarquia pai-filho</span><span class="sxs-lookup"><span data-stu-id="1d4cc-109">Defining Parent Attribute Properties in a Parent-Child Hierarchy</span></span>](lesson-4-2-defining-parent-attribute-properties-in-a-parent-child-hierarchy.md)  
 <span data-ttu-id="1d4cc-110">Nesta tarefa, você definirá nomes de nível em uma dimensão pai-filho e especificará se os dados relacionados aos membros pai serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="1d4cc-110">In this task, you define level names in a parent-child dimension and specify whether data related to parent members is displayed.</span></span> <span data-ttu-id="1d4cc-111">Para obter mais informações, consulte [hierarquia pai-filho](multidimensional-models/parent-child-dimension.md) e [atributos em hierarquias pai-filho](multidimensional-models/parent-child-dimension-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="1d4cc-111">For more information, see [Parent-Child Hierarchy](multidimensional-models/parent-child-dimension.md) and [Attributes in Parent-Child Hierarchies](multidimensional-models/parent-child-dimension-attributes.md).</span></span>  
  
 [<span data-ttu-id="1d4cc-112">Agrupando membros de atributo automaticamente</span><span class="sxs-lookup"><span data-stu-id="1d4cc-112">Automatically Grouping Attribute Members</span></span>](lesson-4-3-automatically-grouping-attribute-members.md)  
 <span data-ttu-id="1d4cc-113">Nesta tarefa, você criará automaticamente agrupamento de membros de atributos com base na distribuição de membros dentro da hierarquia de atributos.</span><span class="sxs-lookup"><span data-stu-id="1d4cc-113">In this task, you automatically create groupings of attribute members based on the distribution of the members within the attribute hierarchy.</span></span> <span data-ttu-id="1d4cc-114">Para obter mais informações, consulte [Agrupar membros de atributo &#40;Diferenciação&#41;](multidimensional-models/attribute-properties-group-attribute-members.md).</span><span class="sxs-lookup"><span data-stu-id="1d4cc-114">For more information, see [Group Attribute Members &#40;Discretization&#41;](multidimensional-models/attribute-properties-group-attribute-members.md).</span></span>  
  
 [<span data-ttu-id="1d4cc-115">Ocultando e desabilitando as hierarquias de atributo</span><span class="sxs-lookup"><span data-stu-id="1d4cc-115">Hiding and Disabling Attribute Hierarchies</span></span>](lesson-4-4-hiding-and-disabling-attribute-hierarchies.md)  
 <span data-ttu-id="1d4cc-116">Nesta tarefa, você aprenderá como e quando desativar ou ocultar as hierarquias de atributo.</span><span class="sxs-lookup"><span data-stu-id="1d4cc-116">In this task, you learn how and when to disable or hide attribute hierarchies.</span></span>  
  
 [<span data-ttu-id="1d4cc-117">Classificando membros de atributo com base em um atributo secundário</span><span class="sxs-lookup"><span data-stu-id="1d4cc-117">Sorting Attribute Members Based on a Secondary Attribute</span></span>](lesson-4-5-sorting-attribute-members-based-on-a-secondary-attribute.md)  
 <span data-ttu-id="1d4cc-118">Nesta tarefa, você aprenderá como classificar os membros de dimensão com base em um atributo secundário para atingir a ordem de classificação desejada.</span><span class="sxs-lookup"><span data-stu-id="1d4cc-118">In this task, you learn how to sort dimension members based on a secondary attribute, to achieve the sort order that you want.</span></span>  
  
 [<span data-ttu-id="1d4cc-119">Especificando relações de atributo entre atributos em uma hierarquia definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="1d4cc-119">Specifying Attribute Relationships Between Attributes in a User-Defined Hierarchy</span></span>](4-6-specifying-attribute-relationships-in-user-defined-hierarchy.md)  
 <span data-ttu-id="1d4cc-120">Nesta tarefa, você aprenderá a definir propriedades de membro para atributos e especificar relações de agregação entre eles.</span><span class="sxs-lookup"><span data-stu-id="1d4cc-120">In this task, you learn how to define member properties for attributes and to specify aggregation relationships between them.</span></span> <span data-ttu-id="1d4cc-121">Para obter mais informações, consulte [definir relações de atributo](multidimensional-models/attribute-relationships-define.md) e [Propriedades de hierarquia de usuário](multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md).</span><span class="sxs-lookup"><span data-stu-id="1d4cc-121">For more information, see [Define Attribute Relationships](multidimensional-models/attribute-relationships-define.md) and [User Hierarchy Properties](multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md).</span></span>  
  
 [<span data-ttu-id="1d4cc-122">Definindo o membro desconhecido e as propriedades de processamento nulo</span><span class="sxs-lookup"><span data-stu-id="1d4cc-122">Defining the Unknown Member and Null Processing Properties</span></span>](lesson-4-7-defining-the-unknown-member-and-null-processing-properties.md)  
 <span data-ttu-id="1d4cc-123">Nesta tarefa, você configura as propriedades UnknownMember e UnknownMemberName para tratar as condições de erro causadas por membros de dimensão nulos.</span><span class="sxs-lookup"><span data-stu-id="1d4cc-123">In this task, you configure the UnknownMember and UnknownMemberName properties to handle error conditions caused by null dimension members.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="1d4cc-124">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="1d4cc-124">Next Lesson</span></span>  
 [<span data-ttu-id="1d4cc-125">Lição 5: Como definir relações entre grupos de medidas e dimensões</span><span class="sxs-lookup"><span data-stu-id="1d4cc-125">Lesson 5: Defining Relationships Between Dimensions and Measure Groups</span></span>](lesson-5-defining-relationships-between-dimensions-and-measure-groups.md)  
  
## <a name="see-also"></a><span data-ttu-id="1d4cc-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1d4cc-126">See Also</span></span>  
 <span data-ttu-id="1d4cc-127">[Cenário do tutorial de Analysis Services](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="1d4cc-127">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="1d4cc-128">[Modelagem multidimensional &#40;tutorial do Adventure Works&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="1d4cc-128">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 [<span data-ttu-id="1d4cc-129">Dimensões em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="1d4cc-129">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
