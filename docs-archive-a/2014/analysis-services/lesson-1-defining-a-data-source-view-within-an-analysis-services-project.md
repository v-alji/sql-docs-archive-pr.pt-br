---
title: 'Lição 1: definindo uma exibição da fonte de dados em um projeto Analysis Services | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7d3ffabd-78ae-4204-8323-29949d030c16
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8a3d69225217154e5072d0cd34349a247730ddaf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684949"
---
# <a name="lesson-1-defining-a-data-source-view-within-an-analysis-services-project"></a><span data-ttu-id="c7260-102">Lição 1: Definir uma exibição da fonte de dados em um projeto do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="c7260-102">Lesson 1: Defining a Data Source View within an Analysis Services Project</span></span>
  <span data-ttu-id="c7260-103">O projeto de um aplicativo de inteligência empresarial no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] inicia com a criação de um projeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7260-103">Designing a business intelligence application in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] starts with creating an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="c7260-104">Dentro desse projeto, você define todos os elementos da sua solução, começando com uma exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c7260-104">Within this project, you define all the elements of your solution, starting with a data source view.</span></span>  
  
 <span data-ttu-id="c7260-105">Esta lição contém as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="c7260-105">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="c7260-106">Criando um projeto do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="c7260-106">Creating an Analysis Services Project</span></span>](lesson-1-1-creating-an-analysis-services-project.md)  
 <span data-ttu-id="c7260-107">Nesta tarefa, você criará o projeto do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] com base em um modelo multidimensional do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c7260-107">In this task, you create the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, based on an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] multidimensional model template.</span></span>  
  
 [<span data-ttu-id="c7260-108">Definindo uma fonte de dados</span><span class="sxs-lookup"><span data-stu-id="c7260-108">Defining a Data Source</span></span>](lesson-1-2-defining-a-data-source.md)  
 <span data-ttu-id="c7260-109">Nesta tarefa, você especifica o banco de dados **AdventureWorksDW2012** como a fonte de dados das dimensões e dos cubos do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que serão definidos nas próximas lições.</span><span class="sxs-lookup"><span data-stu-id="c7260-109">In this task, you specify the **AdventureWorksDW2012** database as the data source for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] dimensions and cubes that you will define in subsequent lessons.</span></span>  
  
 [<span data-ttu-id="c7260-110">Definindo uma exibição da fonte de dados</span><span class="sxs-lookup"><span data-stu-id="c7260-110">Defining a Data Source View</span></span>](lesson-1-3-defining-a-data-source-view.md)  
 <span data-ttu-id="c7260-111">Nesta lição, você define uma exibição unificada exclusiva para os metadados das tabelas selecionadas no banco de dados **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="c7260-111">In this task, you define a single unified view of the metadata from selected tables in the **AdventureWorksDW2012** database.</span></span>  
  
 [<span data-ttu-id="c7260-112">Modificando nomes de tabela padrão</span><span class="sxs-lookup"><span data-stu-id="c7260-112">Modifying Default Table Names</span></span>](lesson-1-4-modifying-default-table-names.md)  
 <span data-ttu-id="c7260-113">Nesta tarefa, você modificará os nomes das tabelas na exibição da fonte de dados de forma que os nomes dos objetos subsequentes do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que serão definidos sejam mais fáceis de serem utilizados.</span><span class="sxs-lookup"><span data-stu-id="c7260-113">In this task, you modify table names in the data source view, so that the names of subsequent [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objects that you define will be more user-friendly.</span></span>  
  
 <span data-ttu-id="c7260-114">Compare os resultados com um arquivo de projeto de exemplo que foi criado para esta lição.</span><span class="sxs-lookup"><span data-stu-id="c7260-114">Compare your results against a sample project file that was built for this lesson.</span></span> <span data-ttu-id="c7260-115">Para obter mais informações sobre como baixar os projetos de exemplo que acompanham este tutorial, consulte [Projetos de modelo multidimensional SSAS para SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=221866) na página de amostras do produto no CodePlex.</span><span class="sxs-lookup"><span data-stu-id="c7260-115">For more information about downloading the sample projects that go with this tutorial, see [SSAS Multidimensional Model Projects for SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=221866) on the product samples page on codeplex.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="c7260-116">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="c7260-116">Next Lesson</span></span>  
 [<span data-ttu-id="c7260-117">Lição 2: Definir e implantar um cubo</span><span class="sxs-lookup"><span data-stu-id="c7260-117">Lesson 2: Defining and Deploying a Cube</span></span>](lesson-2-defining-and-deploying-a-cube.md)  
  
## <a name="see-also"></a><span data-ttu-id="c7260-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c7260-118">See Also</span></span>  
 <span data-ttu-id="c7260-119">[Criar um projeto de Analysis Services &#40;SSDT&#41;](multidimensional-models/create-an-analysis-services-project-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="c7260-119">[Create an Analysis Services Project &#40;SSDT&#41;](multidimensional-models/create-an-analysis-services-project-ssdt.md) </span></span>  
 <span data-ttu-id="c7260-120">[Fontes de dados com suporte &#40;SSAS multidimensional&#41;](multidimensional-models/supported-data-sources-ssas-multidimensional.md) </span><span class="sxs-lookup"><span data-stu-id="c7260-120">[Data Sources Supported &#40;SSAS Multidimensional&#41;](multidimensional-models/supported-data-sources-ssas-multidimensional.md) </span></span>  
 <span data-ttu-id="c7260-121">[Exibições da fonte de dados em modelos multidimensionais](multidimensional-models/data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="c7260-121">[Data Source Views in Multidimensional Models](multidimensional-models/data-source-views-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="c7260-122">[Cenário do tutorial de Analysis Services](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="c7260-122">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 [<span data-ttu-id="c7260-123">Modelagem multidimensional &#40;Tutorial do Adventure Works&#41;</span><span class="sxs-lookup"><span data-stu-id="c7260-123">Multidimensional Modeling &#40;Adventure Works Tutorial&#41;</span></span>](multidimensional-modeling-adventure-works-tutorial.md)  
  
  
