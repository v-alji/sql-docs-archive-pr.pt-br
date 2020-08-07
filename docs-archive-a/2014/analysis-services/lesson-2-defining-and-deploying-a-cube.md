---
title: 'Lição 2: definindo e implantando um cubo | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: bb62e3c9-462f-4ad2-ac8e-92e2f9e9cc28
author: minewiskan
ms.author: owend
ms.openlocfilehash: a2c043920ac646ec4da9eaa2aace4bf6f48e694c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581587"
---
# <a name="lesson-2-defining-and-deploying-a-cube"></a><span data-ttu-id="34bf6-102">Lição 2: Definir e implantar um cubo</span><span class="sxs-lookup"><span data-stu-id="34bf6-102">Lesson 2: Defining and Deploying a Cube</span></span>
  <span data-ttu-id="34bf6-103">Depois de definir uma exibição da fonte de dados em seu [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] projeto, você estará pronto para definir um [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cubo inicial.</span><span class="sxs-lookup"><span data-stu-id="34bf6-103">After you define a data source view in your [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, you are ready to define an initial [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube.</span></span>  
  
 <span data-ttu-id="34bf6-104">Você pode definir um cubo e suas dimensões em uma etapa usando o Assistente para Cubos.</span><span class="sxs-lookup"><span data-stu-id="34bf6-104">You can define a cube and its dimensions in a single pass using the Cube Wizard.</span></span> <span data-ttu-id="34bf6-105">Como alternativa, você pode definir uma ou mais dimensões e depois usar o Assistente para Cubos para definir um cubo que use aquelas dimensões.</span><span class="sxs-lookup"><span data-stu-id="34bf6-105">Alternatively, you can define one or more dimensions and then use the Cube Wizard to define a cube that uses those dimensions.</span></span> <span data-ttu-id="34bf6-106">Se você estiver criando uma solução complexa, normalmente começará definindo as dimensões.</span><span class="sxs-lookup"><span data-stu-id="34bf6-106">If you are designing a complex solution, you generally start by defining the dimensions.</span></span> <span data-ttu-id="34bf6-107">Para obter mais informações, consulte [Dimensões em modelos multidimensionais](multidimensional-models/dimensions-in-multidimensional-models.md) ou [Cubos em modelos multidimensionais](multidimensional-models/cubes-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="34bf6-107">For more information, see [Dimensions in Multidimensional Models](multidimensional-models/dimensions-in-multidimensional-models.md) or [Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="34bf6-108">Projetos concluídos de todas as lições deste tutorial estão disponíveis online.</span><span class="sxs-lookup"><span data-stu-id="34bf6-108">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="34bf6-109">Você pode avançar para qualquer lição com o uso do projeto concluído na lição anterior como um ponto de partida.</span><span class="sxs-lookup"><span data-stu-id="34bf6-109">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="34bf6-110">[Clique aqui](https://go.microsoft.com/fwlink/?LinkID=221866) para baixar os projetos de exemplo fornecidos com este tutorial.</span><span class="sxs-lookup"><span data-stu-id="34bf6-110">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 <span data-ttu-id="34bf6-111">Esta lição contém as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="34bf6-111">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="34bf6-112">Definindo uma dimensão</span><span class="sxs-lookup"><span data-stu-id="34bf6-112">Defining a Dimension</span></span>](lesson-2-1-defining-a-dimension.md)  
 <span data-ttu-id="34bf6-113">Nesta tarefa, você usará o Assistente para Dimensões para definir uma dimensão.</span><span class="sxs-lookup"><span data-stu-id="34bf6-113">In this task, you use the Dimension Wizard to define a dimension.</span></span>  
  
 [<span data-ttu-id="34bf6-114">Definindo um cubo</span><span class="sxs-lookup"><span data-stu-id="34bf6-114">Defining a Cube</span></span>](lesson-2-2-defining-a-cube.md)  
 <span data-ttu-id="34bf6-115">Nesta tarefa, você usará o Assistente para Cubos para definir um cubo inicial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34bf6-115">In this task, you use the Cube Wizard to define an initial [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube.</span></span>  
  
 [<span data-ttu-id="34bf6-116">Adicionando atributos em dimensões</span><span class="sxs-lookup"><span data-stu-id="34bf6-116">Adding Attributes to Dimensions</span></span>](lesson-2-3-adding-attributes-to-dimensions.md)  
 <span data-ttu-id="34bf6-117">Nesta tarefa, você adicionará atributos às dimensões criadas.</span><span class="sxs-lookup"><span data-stu-id="34bf6-117">In this task, you add attributes to the dimensions that you created.</span></span>  
  
 [<span data-ttu-id="34bf6-118">Revisando as propriedades de dimensão e cubo</span><span class="sxs-lookup"><span data-stu-id="34bf6-118">Reviewing Cube and Dimension Properties</span></span>](lesson-2-4-reviewing-cube-and-dimension-properties.md)  
 <span data-ttu-id="34bf6-119">Nesta tarefa, você revisará a estrutura do cubo definido usando o Assistente para Cubos.</span><span class="sxs-lookup"><span data-stu-id="34bf6-119">In this task, you review the structure of the cube that you defined by using the Cube Wizard.</span></span>  
  
 [<span data-ttu-id="34bf6-120">Implantando um projeto do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="34bf6-120">Deploying an Analysis Services Project</span></span>](lesson-2-5-deploying-an-analysis-services-project.md)  
 <span data-ttu-id="34bf6-121">Nesta tarefa, você implantará o projeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] em sua instância local do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]e aprenderá sobre determinadas propriedades de implantação.</span><span class="sxs-lookup"><span data-stu-id="34bf6-121">In this task, you deploy the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project to your local instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], and learn about certain deployment properties.</span></span>  
  
 [<span data-ttu-id="34bf6-122">Navegando pelo cubo</span><span class="sxs-lookup"><span data-stu-id="34bf6-122">Browsing the Cube</span></span>](lesson-2-6-browsing-the-cube.md)  
 <span data-ttu-id="34bf6-123">Nesta tarefa, você navegará no cubo e dimensões de dados usando o Excel ou o designer de consulta MDX.</span><span class="sxs-lookup"><span data-stu-id="34bf6-123">In this task, you browse the cube and dimension data by using Excel or the MDX query designer.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="34bf6-124">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="34bf6-124">Next Lesson</span></span>  
 [<span data-ttu-id="34bf6-125">Lição 3: Como modificar medidas, atributos e hierarquias</span><span class="sxs-lookup"><span data-stu-id="34bf6-125">Lesson 3: Modifying Measures, Attributes and Hierarchies</span></span>](lesson-3-modifying-measures-attributes-and-hierarchies.md)  
  
## <a name="see-also"></a><span data-ttu-id="34bf6-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="34bf6-126">See Also</span></span>  
 <span data-ttu-id="34bf6-127">[Cenário do tutorial de Analysis Services](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="34bf6-127">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="34bf6-128">[Modelagem multidimensional &#40;tutorial do Adventure Works&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="34bf6-128">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 <span data-ttu-id="34bf6-129">[Dimensões em modelos multidimensionais](multidimensional-models/dimensions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="34bf6-129">[Dimensions in Multidimensional Models](multidimensional-models/dimensions-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="34bf6-130">[Cubos em modelos multidimensionais](multidimensional-models/cubes-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="34bf6-130">[Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="34bf6-131">[Configurar propriedades do projeto de Analysis Services &#40;SSDT&#41;](multidimensional-models/configure-analysis-services-project-properties-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="34bf6-131">[Configure Analysis Services Project Properties &#40;SSDT&#41;](multidimensional-models/configure-analysis-services-project-properties-ssdt.md) </span></span>  
 <span data-ttu-id="34bf6-132">[Compilar projetos de Analysis Services &#40;SSDT&#41;](multidimensional-models/build-analysis-services-projects-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="34bf6-132">[Build Analysis Services Projects &#40;SSDT&#41;](multidimensional-models/build-analysis-services-projects-ssdt.md) </span></span>  
 [<span data-ttu-id="34bf6-133">Implantar projetos do Analysis Services &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="34bf6-133">Deploy Analysis Services Projects &#40;SSDT&#41;</span></span>](multidimensional-models/deploy-analysis-services-projects-ssdt.md)  
  
  
