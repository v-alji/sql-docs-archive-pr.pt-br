---
title: 'Lição 1: preparando o banco de dados de Analysis Services (tutorial básico de Data Mining) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2a796977-6568-4705-9d27-86a9b36658c2
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 07647a940851fbdbdc65357e168747662dc88380
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686004"
---
# <a name="lesson-1-preparing-the-analysis-services-database-basic-data-mining-tutorial"></a><span data-ttu-id="e7997-102">Lição 1: Preparando o banco de dados do Analysis Services (Tutorial de mineração de dados básico)</span><span class="sxs-lookup"><span data-stu-id="e7997-102">Lesson 1: Preparing the Analysis Services Database (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="e7997-103">Você é um novo funcionário de [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] quem recebeu uma tarefa com a criação de um aplicativo de Business Intelligence no [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e7997-103">You are a new employee of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] who has been tasked with designing a business intelligence application in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span> [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)]<span data-ttu-id="e7997-104">expectativa de aproveitar sua [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] experiência de Data Mining para descobrir informações interessantes e acionáveis sobre as pessoas que compraram bicicletas.</span><span class="sxs-lookup"><span data-stu-id="e7997-104">hopes to leverage your [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data mining experience to discover interesting and actionable information about people who have purchased bicycles.</span></span> <span data-ttu-id="e7997-105">Eles desejam que você preveja quais clientes potenciais têm mais probabilidade de comprar uma bicicleta no futuro.</span><span class="sxs-lookup"><span data-stu-id="e7997-105">They then want you to predict which prospective customers are most likely to purchase a bicycle in the future.</span></span>  
  
 <span data-ttu-id="e7997-106">A criação desse aplicativo no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] começa com a criação de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] um [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] projeto com base no [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] modelo de projeto para modelagem multidimensional e Data Mining.</span><span class="sxs-lookup"><span data-stu-id="e7997-106">Designing this application in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] starts with the creation in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] of a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project based on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project template for multidimensional modeling and data mining.</span></span> <span data-ttu-id="e7997-107">Depois de criar um projeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], defina uma ou mais fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="e7997-107">After you create an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, you define one or more data sources.</span></span> <span data-ttu-id="e7997-108">Em seguida, você define uma exibição dos metadados, chamada de *exibição da fonte de dados*, de tabelas e exibições selecionadas das fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="e7997-108">Then, you define a view of the metadata, called a *data source view*, from selected tables and views from the data sources.</span></span>  
  
 <span data-ttu-id="e7997-109">Nesta lição, você criará um projeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], definirá uma única fonte de dados e adicionará um subconjunto de tabelas a uma exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="e7997-109">In this lesson, you will create an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, define a single data source, and add a subset of tables to a data source view.</span></span> <span data-ttu-id="e7997-110">Esta lição inclui as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="e7997-110">This lesson includes the following tasks:</span></span>  
  
 [<span data-ttu-id="e7997-111">Criando um projeto de Analysis Services &#40;o tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="e7997-111">Creating an Analysis Services Project &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="e7997-112">Criando uma fonte de dados &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="e7997-112">Creating a Data Source &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="e7997-113">Criando uma exibição da fonte de dados &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="e7997-113">Creating a Data Source View &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-view-basic-data-mining-tutorial.md)  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="e7997-114">Primeira tarefa na lição</span><span class="sxs-lookup"><span data-stu-id="e7997-114">First Task in Lesson</span></span>  
 [<span data-ttu-id="e7997-115">Criando um projeto de Analysis Services &#40;o tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="e7997-115">Creating an Analysis Services Project &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="e7997-116">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="e7997-116">Next Lesson</span></span>  
 [<span data-ttu-id="e7997-117">Lição 2: criando uma estrutura de endereçamento direcionada &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="e7997-117">Lesson 2: Building a Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="e7997-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e7997-118">See Also</span></span>  
 <span data-ttu-id="e7997-119">[Exibições da fonte de dados em modelos multidimensionais](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models) </span><span class="sxs-lookup"><span data-stu-id="e7997-119">[Data Source Views in Multidimensional Models](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models) </span></span>  
 <span data-ttu-id="e7997-120">[Fontes de dados com suporte &#40;SSAS multidimensional&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/supported-data-sources-ssas-multidimensional) </span><span class="sxs-lookup"><span data-stu-id="e7997-120">[Data Sources Supported &#40;SSAS Multidimensional&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/supported-data-sources-ssas-multidimensional) </span></span>  
 <span data-ttu-id="e7997-121">[Compilar projetos de Analysis Services &#40;SSDT&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/build-analysis-services-projects-ssdt) </span><span class="sxs-lookup"><span data-stu-id="e7997-121">[Build Analysis Services Projects &#40;SSDT&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/build-analysis-services-projects-ssdt) </span></span>  
 [<span data-ttu-id="e7997-122">Criando um projeto do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="e7997-122">Creating an Analysis Services Project</span></span>](../analysis-services/lesson-1-1-creating-an-analysis-services-project.md)  
  
  
