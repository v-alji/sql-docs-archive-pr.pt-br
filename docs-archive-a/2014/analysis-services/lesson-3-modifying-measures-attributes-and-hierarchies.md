---
title: 'Lição 3: modificando medidas, atributos e hierarquias | Microsoft Docs'
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 17d243cb-9bfb-43d7-8e6f-4d601fd62150
author: minewiskan
ms.author: owend
ms.openlocfilehash: c410136540a0ba85d50fbabc8b2d3c52be1823f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575431"
---
# <a name="lesson-3-modifying-measures-attributes-and-hierarchies"></a><span data-ttu-id="cdcbe-102">Lição 3: Como modificar medidas, atributos e hierarquias</span><span class="sxs-lookup"><span data-stu-id="cdcbe-102">Lesson 3: Modifying Measures, Attributes and Hierarchies</span></span>
  <span data-ttu-id="cdcbe-103">Depois de definir o cubo inicial, você poderá melhorar a utilidade e a facilidade de uso do cubo.</span><span class="sxs-lookup"><span data-stu-id="cdcbe-103">After defining your initial cube, you are ready to improve the usefulness and friendliness of the cube.</span></span> <span data-ttu-id="cdcbe-104">Você pode fazer isto adicionando hierarquias que dão suporte à navegação e agregação em vários níveis, aplicando formatos a medidas específicas, e definindo cálculos e relações.</span><span class="sxs-lookup"><span data-stu-id="cdcbe-104">You can do this by adding hierarchies that support navigation and aggregation at various levels, by applying formats to specific measure, and by defining calculations and relationships.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cdcbe-105">Projetos concluídos de todas as lições deste tutorial estão disponíveis online.</span><span class="sxs-lookup"><span data-stu-id="cdcbe-105">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="cdcbe-106">Você pode avançar para qualquer lição com o uso do projeto concluído na lição anterior como um ponto de partida.</span><span class="sxs-lookup"><span data-stu-id="cdcbe-106">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="cdcbe-107">[Clique aqui](https://go.microsoft.com/fwlink/?LinkID=221866) para baixar os projetos de exemplo fornecidos com este tutorial.</span><span class="sxs-lookup"><span data-stu-id="cdcbe-107">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 <span data-ttu-id="cdcbe-108">Esta lição contém as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="cdcbe-108">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="cdcbe-109">Modificando medidas</span><span class="sxs-lookup"><span data-stu-id="cdcbe-109">Modifying Measures</span></span>](lesson-3-1-modifying-measures.md)  
 <span data-ttu-id="cdcbe-110">Nesta tarefa, você especificará propriedades de formatação para as medidas moeda e porcentagem do cubo do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cdcbe-110">In this task, you specify formatting properties for the currency and percentage measures in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>  
  
 [<span data-ttu-id="cdcbe-111">Modificando a dimensão Cliente</span><span class="sxs-lookup"><span data-stu-id="cdcbe-111">Modifying the Customer Dimension</span></span>](lesson-3-2-modifying-the-customer-dimension.md)  
 <span data-ttu-id="cdcbe-112">Nesta tarefa, você definirá uma hierarquia de usuário, criará cálculos nomeados, modificará atributos que serão usados em cálculos nomeados e agrupará atributos e hierarquias de usuário em pastas de exibição.</span><span class="sxs-lookup"><span data-stu-id="cdcbe-112">In this task, you define a user hierarchy, create named calculations, modify attributes to use named calculations, and group attributes and user hierarchies into display folders.</span></span>  
  
 [<span data-ttu-id="cdcbe-113">Modificando a dimensão Produto</span><span class="sxs-lookup"><span data-stu-id="cdcbe-113">Modifying the Product Dimension</span></span>](lesson-3-3-modifying-the-product-dimension.md)  
 <span data-ttu-id="cdcbe-114">Nesta tarefa, você definirá uma hierarquia do usuário, criará cálculos nomeados, definirá o nome do membro Todos e definirá as pastas de exibição.</span><span class="sxs-lookup"><span data-stu-id="cdcbe-114">In this task, you define a user hierarchy, create named calculations, define the All member name, and define display folders.</span></span>  
  
 [<span data-ttu-id="cdcbe-115">Modificando a dimensão de data</span><span class="sxs-lookup"><span data-stu-id="cdcbe-115">Modifying the Date Dimension</span></span>](lesson-3-4-modifying-the-date-dimension.md)  
 <span data-ttu-id="cdcbe-116">Nesta tarefa, você definirá uma hierarquia de usuário, modificará nomes de membros do atributo e usará chaves compostas para especificar membros de atributos exclusivos.</span><span class="sxs-lookup"><span data-stu-id="cdcbe-116">In this task, you define a user hierarchy, modify attribute member names, and use composite keys to specify unique attribute members.</span></span>  
  
 [<span data-ttu-id="cdcbe-117">Navegando no cubo implantado</span><span class="sxs-lookup"><span data-stu-id="cdcbe-117">Browsing the Deployed Cube</span></span>](lesson-3-5-browsing-the-deployed-cube.md)  
 <span data-ttu-id="cdcbe-118">Nesta tarefa, você navegará pelos dados do cubo usando o navegador no Designer de Cubo.</span><span class="sxs-lookup"><span data-stu-id="cdcbe-118">In this task, you browse cube data by using the browser in Cube Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdcbe-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cdcbe-119">See Also</span></span>  
 <span data-ttu-id="cdcbe-120">[Cenário do tutorial de Analysis Services](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="cdcbe-120">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 [<span data-ttu-id="cdcbe-121">Modelagem multidimensional &#40;Tutorial do Adventure Works&#41;</span><span class="sxs-lookup"><span data-stu-id="cdcbe-121">Multidimensional Modeling &#40;Adventure Works Tutorial&#41;</span></span>](multidimensional-modeling-adventure-works-tutorial.md)  
  
  
