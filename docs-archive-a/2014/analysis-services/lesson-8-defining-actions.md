---
title: 'Lição 8: definindo ações | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 15459396-83c9-48a0-b10a-99ae38768c79
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4d4daaed3f1992478b309529fc15e2e903a27920
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683809"
---
# <a name="lesson-8-defining-actions"></a><span data-ttu-id="45c6e-102">Lição 8: Como definir ações</span><span class="sxs-lookup"><span data-stu-id="45c6e-102">Lesson 8: Defining Actions</span></span>
  <span data-ttu-id="45c6e-103">Nesta lição, você aprenderá a definir ações em seu projeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="45c6e-103">In this lesson, you will learn to define actions in your [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="45c6e-104">Uma ação é como uma instrução MDX que é armazenada no [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e que pode ser incorporada em aplicativos cliente e iniciada por um usuário.</span><span class="sxs-lookup"><span data-stu-id="45c6e-104">An action is just a Multidimensional Expressions (MDX) statement that is stored in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and which can be incorporated into client applications and started by a user.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="45c6e-105">Projetos concluídos de todas as lições deste tutorial estão disponíveis online.</span><span class="sxs-lookup"><span data-stu-id="45c6e-105">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="45c6e-106">Você pode avançar para qualquer lição com o uso do projeto concluído na lição anterior como um ponto de partida.</span><span class="sxs-lookup"><span data-stu-id="45c6e-106">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="45c6e-107">[Clique aqui](https://go.microsoft.com/fwlink/?LinkID=221866) para baixar os projetos de exemplo fornecidos com este tutorial.</span><span class="sxs-lookup"><span data-stu-id="45c6e-107">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="45c6e-108">dá suporte aos tipos de ações descritos na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="45c6e-108">supports the types of actions that are described in the following table.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="45c6e-109">CommandLine</span><span class="sxs-lookup"><span data-stu-id="45c6e-109">CommandLine</span></span>|<span data-ttu-id="45c6e-110">Executa um comando no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="45c6e-110">Executes a command at the command prompt</span></span>|  
|<span data-ttu-id="45c6e-111">Conjunto de dados</span><span class="sxs-lookup"><span data-stu-id="45c6e-111">Dataset</span></span>|<span data-ttu-id="45c6e-112">Retorna um conjunto de dados a um aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="45c6e-112">Returns a dataset to a client application.</span></span>|  
|<span data-ttu-id="45c6e-113">Detalhamento</span><span class="sxs-lookup"><span data-stu-id="45c6e-113">Drillthrough</span></span>|<span data-ttu-id="45c6e-114">Retorna uma instrução de detalhamento como uma expressão e que o cliente executa para retornar um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="45c6e-114">Returns a drillthrough statement as an expression, which the client executes to return a rowset</span></span>|  
|<span data-ttu-id="45c6e-115">Html</span><span class="sxs-lookup"><span data-stu-id="45c6e-115">Html</span></span>|<span data-ttu-id="45c6e-116">Executa um script HTML em um navegador de Internet.</span><span class="sxs-lookup"><span data-stu-id="45c6e-116">Executes an HTML script in an Internet browser</span></span>|  
|<span data-ttu-id="45c6e-117">Proprietário</span><span class="sxs-lookup"><span data-stu-id="45c6e-117">Proprietary</span></span>|<span data-ttu-id="45c6e-118">Executa uma operação usando uma interface diferente das listadas nesta tabela.</span><span class="sxs-lookup"><span data-stu-id="45c6e-118">Performs an operation by using an interface other than those listed in this table.</span></span>|  
|<span data-ttu-id="45c6e-119">Relatório</span><span class="sxs-lookup"><span data-stu-id="45c6e-119">Report</span></span>|<span data-ttu-id="45c6e-120">Envia uma solicitação com base em URL parametrizada para um servidor de relatórios e retorna um relatório a um aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="45c6e-120">Submits a parameterized URL-based request to a report server and returns a report to a client application.</span></span>|  
|<span data-ttu-id="45c6e-121">Conjunto de linhas</span><span class="sxs-lookup"><span data-stu-id="45c6e-121">Rowset</span></span>|<span data-ttu-id="45c6e-122">Retorna um conjunto de linhas a um aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="45c6e-122">Returns a rowset to a client application.</span></span>|  
|<span data-ttu-id="45c6e-123">Instrução</span><span class="sxs-lookup"><span data-stu-id="45c6e-123">Statement</span></span>|<span data-ttu-id="45c6e-124">Executa um comando OLE DB.</span><span class="sxs-lookup"><span data-stu-id="45c6e-124">Runs an OLE DB command.</span></span>|  
|<span data-ttu-id="45c6e-125">URL</span><span class="sxs-lookup"><span data-stu-id="45c6e-125">URL</span></span>|<span data-ttu-id="45c6e-126">Exibe uma página da Web dinâmica em um navegador de Internet.</span><span class="sxs-lookup"><span data-stu-id="45c6e-126">Displays a dynamic Web page in an Internet browser.</span></span>|  
  
 <span data-ttu-id="45c6e-127">As ações permitem que os usuários iniciem um aplicativo ou executem outras etapas dentro do contexto de um item selecionado.</span><span class="sxs-lookup"><span data-stu-id="45c6e-127">Actions let users start an application or perform other steps within the context of a selected item.</span></span> <span data-ttu-id="45c6e-128">Para obter mais informações, consulte [Ações &#40;Analysis Services – Dados Multidimensionais&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md), [Ações em modelos multidimensionais](multidimensional-models/actions-in-multidimensional-models.md)</span><span class="sxs-lookup"><span data-stu-id="45c6e-128">For more information, see [Actions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md), [Actions in Multidimensional Models](multidimensional-models/actions-in-multidimensional-models.md)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="45c6e-129">Para obter mais exemplos de ações, consulte os exemplos de ação na guia Modelo do painel Ferramentas de Cálculo ou nos exemplos do data warehouse de exemplo do DW da [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="45c6e-129">For examples of actions, see the action examples on the Templates tab in the Calculation Tools pane or in the examples in the [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW sample data warehouse.</span></span> <span data-ttu-id="45c6e-130">Para obter mais informações sobre como instalar esse banco de dados, consulte [Instalar dados de exemplo e projetos para o tutorial de modelagem multidimensional do Analysis Services](install-sample-data-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="45c6e-130">For more information about installing this database, see [Install Sample Data and Projects for the Analysis Services Multidimensional Modeling Tutorial](install-sample-data-and-projects.md).</span></span>  
  
 <span data-ttu-id="45c6e-131">Esta lição inclui a seguinte tarefa:</span><span class="sxs-lookup"><span data-stu-id="45c6e-131">This lesson includes the following task:</span></span>  
  
 [<span data-ttu-id="45c6e-132">Definindo e usando uma ação de detalhamento</span><span class="sxs-lookup"><span data-stu-id="45c6e-132">Defining and Using a Drillthrough Action</span></span>](lesson-8-1-defining-and-using-a-drillthrough-action.md)  
 <span data-ttu-id="45c6e-133">Nesta tarefa, você definirá, usará e modificará uma ação de detalhamento através da relação de dimensão de fatos definida anteriormente neste tutorial.</span><span class="sxs-lookup"><span data-stu-id="45c6e-133">In this task, you define, use, and then modify a drillthrough action through the fact dimension relationship that you defined earlier in this tutorial.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="45c6e-134">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="45c6e-134">Next Lesson</span></span>  
 [<span data-ttu-id="45c6e-135">Lição 9: Como definir perspectivas e traduções</span><span class="sxs-lookup"><span data-stu-id="45c6e-135">Lesson 9: Defining Perspectives and Translations</span></span>](lesson-9-defining-perspectives-and-translations.md)  
  
## <a name="see-also"></a><span data-ttu-id="45c6e-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="45c6e-136">See Also</span></span>  
 <span data-ttu-id="45c6e-137">[Cenário do tutorial de Analysis Services](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="45c6e-137">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="45c6e-138">[Modelagem multidimensional &#40;tutorial do Adventure Works&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="45c6e-138">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 <span data-ttu-id="45c6e-139">[Ações &#40;Analysis Services de dados multidimensionais&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="45c6e-139">[Actions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="45c6e-140">Ações em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="45c6e-140">Actions in Multidimensional Models</span></span>](multidimensional-models/actions-in-multidimensional-models.md)  
  
  
