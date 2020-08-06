---
title: 'Lição 7: definindo KPIs (indicadores chave de desempenho) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 36d53770-294f-43ab-8850-15d5351ff60c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 87df6fd91a66505f124144cafd9a44c6e5e70e85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680129"
---
# <a name="lesson-7-defining-key-performance-indicators-kpis"></a><span data-ttu-id="995f4-102">Lição 7: Definir KPIs (indicadores chave de desempenho)</span><span class="sxs-lookup"><span data-stu-id="995f4-102">Lesson 7: Defining Key Performance Indicators (KPIs)</span></span>
  <span data-ttu-id="995f4-103">Nesta lição, você aprenderá a definir os KPIs (indicadores chave de desempenho) no projeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="995f4-103">In this lesson, you learn to define Key Performance Indicators (KPIs) in your [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="995f4-104">Os KPIs fornecem uma estrutura para a definição de cálculos no servidor que medem seus negócios e padronizam a forma como as informações resultantes são exibidas.</span><span class="sxs-lookup"><span data-stu-id="995f4-104">KPIs provide a framework for defining server-side calculations that measure your business, and they standardize how the resulting information is displayed.</span></span> <span data-ttu-id="995f4-105">Eles podem ser exibidos em relatórios, portais e painéis, através das APIs de acesso a dados e das ferramentas da [!INCLUDE[msCoName](../includes/msconame-md.md)] e de terceiros.</span><span class="sxs-lookup"><span data-stu-id="995f4-105">KPIs can be displayed in reports, portals, and dashboards, through data access APIs, and through [!INCLUDE[msCoName](../includes/msconame-md.md)] tools and third-party tools.</span></span> <span data-ttu-id="995f4-106">Os KPIs são wrappers de metadados em torno de medidas normais e outras expressões MDX (Multidimensional Expressions).</span><span class="sxs-lookup"><span data-stu-id="995f4-106">KPIs are metadata wrappers around regular measures and other Multidimensional Expressions (MDX) expressions.</span></span> <span data-ttu-id="995f4-107">Para obter mais informações, consulte [Indicadores Chave de Desempenho &#40;KPIs&#41; em Modelos Multidimensionais](multidimensional-models/key-performance-indicators-kpis-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="995f4-107">For more information, see [Key Performance Indicators &#40;KPIs&#41; in Multidimensional Models](multidimensional-models/key-performance-indicators-kpis-in-multidimensional-models.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="995f4-108">Projetos concluídos de todas as lições deste tutorial estão disponíveis online.</span><span class="sxs-lookup"><span data-stu-id="995f4-108">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="995f4-109">Você pode avançar para qualquer lição com o uso do projeto concluído na lição anterior como um ponto de partida.</span><span class="sxs-lookup"><span data-stu-id="995f4-109">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="995f4-110">[Clique aqui](https://go.microsoft.com/fwlink/?LinkID=221866) para baixar os projetos de exemplo fornecidos com este tutorial.</span><span class="sxs-lookup"><span data-stu-id="995f4-110">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 <span data-ttu-id="995f4-111">Esta lição contém a seguinte tarefa:</span><span class="sxs-lookup"><span data-stu-id="995f4-111">This lesson contains the following task:</span></span>  
  
 [<span data-ttu-id="995f4-112">Definindo e procurando KPIs</span><span class="sxs-lookup"><span data-stu-id="995f4-112">Defining and Browsing KPIs</span></span>](lesson-7-1-defining-and-browsing-kpis.md)  
 <span data-ttu-id="995f4-113">Nesta tarefa, você definirá os KPIs na exibição Formulário e, em seguida, alternará para a exibição Navegador para navegar pelos dados do cubo usando os KPIs.</span><span class="sxs-lookup"><span data-stu-id="995f4-113">In this task, you define KPIs in the Form view and then switch to the Browser view to browse the cube data by using the KPIs.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="995f4-114">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="995f4-114">Next Lesson</span></span>  
 [<span data-ttu-id="995f4-115">Lição 8: Como definir ações</span><span class="sxs-lookup"><span data-stu-id="995f4-115">Lesson 8: Defining Actions</span></span>](lesson-8-defining-actions.md)  
  
## <a name="see-also"></a><span data-ttu-id="995f4-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="995f4-116">See Also</span></span>  
 <span data-ttu-id="995f4-117">[Cenário do tutorial de Analysis Services](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="995f4-117">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="995f4-118">[Modelagem multidimensional &#40;tutorial do Adventure Works&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="995f4-118">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 [<span data-ttu-id="995f4-119">Indicadores Chave de Desempenho &#40;KPIs&#41; em Modelos Multidimensionais</span><span class="sxs-lookup"><span data-stu-id="995f4-119">Key Performance Indicators &#40;KPIs&#41; in Multidimensional Models</span></span>](multidimensional-models/key-performance-indicators-kpis-in-multidimensional-models.md)  
  
  
