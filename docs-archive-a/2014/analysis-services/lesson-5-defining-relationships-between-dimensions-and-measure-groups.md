---
title: 'Lição 5: Definindo relações entre dimensões e grupos de medidas | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 31aeb271-47a1-433b-a8a5-120bcb4584d7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6dbdf20e64e3cd8adc751b69122a380d7b3b3648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572796"
---
# <a name="lesson-5-defining-relationships-between-dimensions-and-measure-groups"></a><span data-ttu-id="4bf76-102">Lição 5: Como definir relações entre grupos de medidas e dimensões</span><span class="sxs-lookup"><span data-stu-id="4bf76-102">Lesson 5: Defining Relationships Between Dimensions and Measure Groups</span></span>
  <span data-ttu-id="4bf76-103">Nas lições anteriores neste tutorial, você aprendeu que as dimensões de banco de dados adicionadas a um cubo podem ser usadas como base para uma ou mais dimensões de cubo.</span><span class="sxs-lookup"><span data-stu-id="4bf76-103">In the previous lessons in this tutorial, you learned that database dimensions added to a cube can be used as the basis for one or more cube dimensions.</span></span> <span data-ttu-id="4bf76-104">Nesta lição, você aprenderá a definir diferentes tipos de relações entre dimensões de cubo e grupos de medidas, além de especificar as propriedades dessas relações.</span><span class="sxs-lookup"><span data-stu-id="4bf76-104">In this lesson, you learn to define different types of relationships between cube dimensions and measure groups, and to specify the properties of these relationships.</span></span>  
  
 <span data-ttu-id="4bf76-105">Para obter mais informações, consulte [Relações de dimensão](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="4bf76-105">For more information, see [Dimension Relationships](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4bf76-106">Projetos concluídos de todas as lições deste tutorial estão disponíveis online.</span><span class="sxs-lookup"><span data-stu-id="4bf76-106">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="4bf76-107">Você pode avançar para qualquer lição com o uso do projeto concluído na lição anterior como um ponto de partida.</span><span class="sxs-lookup"><span data-stu-id="4bf76-107">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="4bf76-108">[Clique aqui](https://go.microsoft.com/fwlink/?LinkID=221866) para baixar os projetos de exemplo fornecidos com este tutorial.</span><span class="sxs-lookup"><span data-stu-id="4bf76-108">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 <span data-ttu-id="4bf76-109">Esta lição contém as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="4bf76-109">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="4bf76-110">Definindo uma relação referenciada</span><span class="sxs-lookup"><span data-stu-id="4bf76-110">Defining a Referenced Relationship</span></span>](lesson-5-1-defining-a-referenced-relationship.md)  
 <span data-ttu-id="4bf76-111">Nesta tarefa, você aprende a vincular uma dimensão a uma tabela de fatos indiretamente por meio de uma dimensão vinculada diretamente por meio de uma relação chave primária-chave estrangeira.</span><span class="sxs-lookup"><span data-stu-id="4bf76-111">In this task, you learn to link a dimension to a fact table indirectly through a dimension that is linked directly through a primary key-foreign key relationship.</span></span>  
  
 [<span data-ttu-id="4bf76-112">Definindo uma relação de fatos</span><span class="sxs-lookup"><span data-stu-id="4bf76-112">Defining a Fact Relationship</span></span>](lesson-5-2-defining-a-fact-relationship.md)  
 <span data-ttu-id="4bf76-113">Nesta tarefa, você aprenderá a definir uma dimensão com base nos dados da tabela de fatos e a definir a relação de dimensão como uma relação de fatos.</span><span class="sxs-lookup"><span data-stu-id="4bf76-113">In this task, you learn to define a dimension based on data in the fact table, and to define the dimension relationship as a fact relationship.</span></span>  
  
 [<span data-ttu-id="4bf76-114">Definindo uma relação muitos para muitos</span><span class="sxs-lookup"><span data-stu-id="4bf76-114">Defining a Many-to-Many Relationship</span></span>](lesson-5-3-defining-a-many-to-many-relationship.md)  
 <span data-ttu-id="4bf76-115">Nesta tarefa, você aprenderá a relacionar um fato a vários membros de dimensão através da definição de uma relação muitos-para-muitos entre as tabelas de dimensões e de fatos.</span><span class="sxs-lookup"><span data-stu-id="4bf76-115">In this task, you learn to relate a fact to multiple dimension members through the definition of a many-to-many relationship between dimension tables and fact tables.</span></span>  
  
 [<span data-ttu-id="4bf76-116">Definindo a granularidade da dimensão dentro de um grupo de medidas</span><span class="sxs-lookup"><span data-stu-id="4bf76-116">Defining Dimension Granularity within a Measure Group</span></span>](lesson-5-4-defining-dimension-granularity-within-a-measure-group.md)  
 <span data-ttu-id="4bf76-117">Nesta tarefa, você aprenderá a modificar a granularidade de uma dimensão para um grupo de medidas específico.</span><span class="sxs-lookup"><span data-stu-id="4bf76-117">In this task, you learn to modify the granularity of a dimension for a specific measure group.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="4bf76-118">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="4bf76-118">Next Lesson</span></span>  
 [<span data-ttu-id="4bf76-119">Lição 6: Como definir cálculos</span><span class="sxs-lookup"><span data-stu-id="4bf76-119">Lesson 6: Defining Calculations</span></span>](lesson-6-defining-calculations.md)  
  
## <a name="see-also"></a><span data-ttu-id="4bf76-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4bf76-120">See Also</span></span>  
 <span data-ttu-id="4bf76-121">[Cenário do tutorial de Analysis Services](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="4bf76-121">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="4bf76-122">[Modelagem multidimensional &#40;tutorial do Adventure Works&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="4bf76-122">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 [<span data-ttu-id="4bf76-123">Relações de dimensão</span><span class="sxs-lookup"><span data-stu-id="4bf76-123">Dimension Relationships</span></span>](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md)  
  
  
