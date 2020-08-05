---
title: Soluções de mineração de dados | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], about data mining
- data mining [Analysis Services], development
ms.assetid: 84f6548d-ebb0-4e10-9b29-66253fa0a04a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0ab4b5ddcc9958fa36d6c8ecae0e7fd79585b4fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572847"
---
# <a name="data-mining-solutions"></a><span data-ttu-id="48cbc-102">Soluções de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="48cbc-102">Data Mining Solutions</span></span>
  <span data-ttu-id="48cbc-103">Uma solução de mineração de dados é uma solução do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que contém um ou mais projetos de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="48cbc-103">A data mining solution is an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] solution that contains one or more data mining projects.</span></span>  
  
 <span data-ttu-id="48cbc-104">Os tópicos nesta seção fornecem informações sobre como projetar e implementar uma solução de Data Mining integrada usando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="48cbc-104">The topics in this section provide information about how to design and implement an integrated data mining solution by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="48cbc-105">Para obter uma visão geral do processo de design de mineração de dados e as ferramentas relacionadas, consulte [Data Mining Concepts](data-mining-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="48cbc-105">For an overview of the data mining design process and related tools, see [Data Mining Concepts](data-mining-concepts.md).</span></span>  
  
 <span data-ttu-id="48cbc-106">Para obter mais informações sobre os tipos de projetos que são úteis para mineração de dados, consulte [Projetos relacionados a soluções de mineração de dados](data-mining-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="48cbc-106">For more information about additional projects types that are useful for data mining, see [Related Projects for Data Mining Solutions](data-mining-solutions.md).</span></span>  
  
 [<span data-ttu-id="48cbc-107">Relacional versus soluções multidimensionais</span><span class="sxs-lookup"><span data-stu-id="48cbc-107">Relational vs. Multidimensional Solutions</span></span>](#bkmk_RelMD)  
  
 [<span data-ttu-id="48cbc-108">Implantando soluções de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="48cbc-108">Deploying Data Mining Solutions</span></span>](#bkmk_Deploy)  
  
 [<span data-ttu-id="48cbc-109">Passo a passo de solução</span><span class="sxs-lookup"><span data-stu-id="48cbc-109">Solution Walkthroughs</span></span>](#bkmk_Walkthru)  
  
##  <a name="relational-vs-multidimensional-solutions"></a><a name="bkmk_RelMD"></a> <span data-ttu-id="48cbc-110">Relacional versus Soluções multidimensionais</span><span class="sxs-lookup"><span data-stu-id="48cbc-110">Relational vs. Multidimensional Solutions</span></span>  
 <span data-ttu-id="48cbc-111">Uma solução de Data Mining pode ser baseada em dados multidimensionais, ou seja, um cubo existente ou dados puramente relacionais, como as tabelas e exibições em uma data warehouse, ou em arquivos de texto, pastas de trabalho do Excel ou outras fontes de dados externas.</span><span class="sxs-lookup"><span data-stu-id="48cbc-111">A data mining solution can be based either on multidimensional data-that is, an existing cube-or on purely relational data, such as the tables and views in a data warehouse, or on text files, Excel workbooks, or other external data sources.</span></span>  
  
-   <span data-ttu-id="48cbc-112">Você pode criar objetos de mineração de dados dentro de uma solução de banco de dados multidimensional existente.</span><span class="sxs-lookup"><span data-stu-id="48cbc-112">You can create data mining objects within an existing multidimensional database solution.</span></span>  
  
     <span data-ttu-id="48cbc-113">Normalmente você criaria uma solução como essa se já tivesse criado um cubo e quisesse executar mineração de dados usando o cubo como uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="48cbc-113">Typically you would create a solution like this if you have already created a cube and want to perform data mining by using the cube as a data source.</span></span> <span data-ttu-id="48cbc-114">Quando você move e faz backup de modelos com base em um cubo, o cubo também deve ser movido ou copiado.</span><span class="sxs-lookup"><span data-stu-id="48cbc-114">When you move and backup models based on a cube, the cube must also be moved or copied.</span></span>  
  
-   <span data-ttu-id="48cbc-115">Você pode criar uma solução de mineração de dados que contém apenas objetos de mineração de dados, inclusive as fontes de dados de apoio e as exibições da fonte de dados, e que usa somente fonte de dados relacional.</span><span class="sxs-lookup"><span data-stu-id="48cbc-115">You can create a data mining solution that contains only data mining objects, including the supporting data sources and data source views, and that uses relational data source only.</span></span>  
  
     <span data-ttu-id="48cbc-116">Este é o método preferido para criar modelos de mineração de dados, já que processar e consultar é geralmente mais rápido em fontes de dados relacionais.</span><span class="sxs-lookup"><span data-stu-id="48cbc-116">This is the preferred method for creating data mining models, as processing and querying is generally fastest against relational data sources.</span></span> <span data-ttu-id="48cbc-117">Você também pode facilmente mover e fazer backup de modelos entre servidores usando os comandos EXPORT e IMPORT.</span><span class="sxs-lookup"><span data-stu-id="48cbc-117">You can also easily move and backup models between servers by using the EXPORT and IMPORT commands.</span></span>  
  
##  <a name="deploying-data-mining-solutions"></a><a name="bkmk_Deploy"></a><span data-ttu-id="48cbc-118">Implantando soluções de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="48cbc-118">Deploying Data Mining Solutions</span></span>  
 <span data-ttu-id="48cbc-119">A instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para o qual você implanta a solução deve estar sendo executada em um modo que dá suporte a objetos multidimensionais e objetos de mineração de dados; ou seja, você não pode implantar objetos de mineração de dados em uma instância que hospeda modelos de tabela ou dados PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="48cbc-119">The instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to which you deploy the solution must be running in a mode that supports multidimensional objects and data mining objects; that is, you cannot deploy data mining objects to an instance that hosts tabular models or PowerPivot data.</span></span>  
  
 <span data-ttu-id="48cbc-120">Portanto, quando você cria uma solução de mineração de dados no Visual Studio, use o modelo **Projeto Multidimensional e de Mineração de Dados do Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="48cbc-120">Therefore, when you create a data mining solution in Visual Studio, be sure to use the template, **Analysis Services Multidimensional and Data Mining Project**.</span></span>  
  
 <span data-ttu-id="48cbc-121">Quando você implanta a solução, os objetos usados para mineração de dados são criados na instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] especificada, em um banco de dados com o mesmo nome do arquivo de solução.</span><span class="sxs-lookup"><span data-stu-id="48cbc-121">When you deploy the solution, the objects used for data mining are created in the specified [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, in a database with the same name as the solution file.</span></span>  
  
 <span data-ttu-id="48cbc-122">Para obter mais informações sobre como implantar soluções relacionais e multidimensionais, consulte [Implantação de soluções de mineração de dados](deployment-of-data-mining-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="48cbc-122">For more information about how to deploy both relational and multidimensional solutions, see [Deployment of Data Mining Solutions](deployment-of-data-mining-solutions.md).</span></span>  
  
##  <a name="solution-walkthrough"></a><a name="bkmk_Walkthru"></a> <span data-ttu-id="48cbc-123">Passo a passo de solução</span><span class="sxs-lookup"><span data-stu-id="48cbc-123">Solution Walkthrough</span></span>  
 <span data-ttu-id="48cbc-124">Fornece uma visão geral de como criar soluções de mineração de dados usando o Assistente de Mineração de Dados.</span><span class="sxs-lookup"><span data-stu-id="48cbc-124">Provides an overview of how to create data mining solutions by using the Data Mining Wizard.</span></span>  
  
 [<span data-ttu-id="48cbc-125">Criar uma estrutura de mineração relacional</span><span class="sxs-lookup"><span data-stu-id="48cbc-125">Create a Relational Mining Structure</span></span>](create-a-relational-mining-structure.md)  
 <span data-ttu-id="48cbc-126">Crie uma estrutura de mineração de dados relacionais, arquivos de texto e outras origens que podem ser combinadas em uma exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="48cbc-126">Create a mining structure from relational data, text files, and other sources that can be combined in a data source view.</span></span>  
  
 [<span data-ttu-id="48cbc-127">Criar uma estrutura de mineração OLAP</span><span class="sxs-lookup"><span data-stu-id="48cbc-127">Create an OLAP Mining Structure</span></span>](create-an-olap-mining-structure.md)  
 <span data-ttu-id="48cbc-128">Criar a estrutura de mineração baseada em dados em um cubo OLAP.</span><span class="sxs-lookup"><span data-stu-id="48cbc-128">Create a mining structure based on data in an OLAP cube.</span></span> <span data-ttu-id="48cbc-129">Os modelos que você cria dos dados OLAP podem ser salvos como uma dimensão de mineração de dados ou você pode salvar o conjunto de dados e seus modelos como um novo cubo.</span><span class="sxs-lookup"><span data-stu-id="48cbc-129">Models that you create from OLAP data can be saved as a data mining dimension, or you can save the set of data and your models as a new cube.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="48cbc-130">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="48cbc-130">In This Section</span></span>  
 [<span data-ttu-id="48cbc-131">Projetos de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="48cbc-131">Data Mining Projects</span></span>](data-mining-projects.md)  
  
 [<span data-ttu-id="48cbc-132">Processando objetos de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="48cbc-132">Processing Data Mining Objects</span></span>](processing-data-mining-objects.md)  
  
 [<span data-ttu-id="48cbc-133">Projetos relacionados a soluções de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="48cbc-133">Related Projects for Data Mining Solutions</span></span>](data-mining-solutions.md)  
  
 [<span data-ttu-id="48cbc-134">Implantação de soluções de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="48cbc-134">Deployment of Data Mining Solutions</span></span>](deployment-of-data-mining-solutions.md)  
  
## <a name="related-tasks-and-topics"></a><span data-ttu-id="48cbc-135">Tarefas e tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="48cbc-135">Related Tasks and Topics</span></span>  
 <span data-ttu-id="48cbc-136">Depois de você ter criado uma solução de mineração de dados básica, incluindo fontes de dados e uma estrutura de mineração, pode criar a solução adicionando novos modelos, testando e comparando modelos, criando previsões e experimentando com subconjuntos de dados.</span><span class="sxs-lookup"><span data-stu-id="48cbc-136">After you have created a basic data mining solution, including data sources and a mining structure, you can build on the solution by adding new models, testing and comparing models, creating predictions, and experimenting with subsets of data.</span></span>  
  
 <span data-ttu-id="48cbc-137">Para obter mais informações, consulte os seguintes links:</span><span class="sxs-lookup"><span data-stu-id="48cbc-137">For more information, see the following links:</span></span>  
  
|<span data-ttu-id="48cbc-138">Tarefas</span><span class="sxs-lookup"><span data-stu-id="48cbc-138">Tasks</span></span>|<span data-ttu-id="48cbc-139">Tópicos</span><span class="sxs-lookup"><span data-stu-id="48cbc-139">Topics</span></span>|  
|-----------|------------|  
|<span data-ttu-id="48cbc-140">Teste os modelos que você criou, valide a qualidade de seus dados de treinamento e crie gráficos que representam a precisão de modelos de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="48cbc-140">Test the models you create, validate the quality of your training data, and create charts that represent the accuracy of data mining models.</span></span>|[<span data-ttu-id="48cbc-141">Teste e validação &#40;Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="48cbc-141">Testing and Validation &#40;Data Mining&#41;</span></span>](testing-and-validation-data-mining.md)|  
|<span data-ttu-id="48cbc-142">Treine o modelo populando a estrutura e os modelos relacionados com os dados.</span><span class="sxs-lookup"><span data-stu-id="48cbc-142">Train the model by populating the structure and related models with data.</span></span> <span data-ttu-id="48cbc-143">Atualize e estenda modelos com novos dados.</span><span class="sxs-lookup"><span data-stu-id="48cbc-143">Update and extend models with new data.</span></span>|[<span data-ttu-id="48cbc-144">Processando objetos de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="48cbc-144">Processing Data Mining Objects</span></span>](processing-data-mining-objects.md)|  
|<span data-ttu-id="48cbc-145">Personalize um modelo de mineração aplicando filtros aos dados de treinamento, escolhendo um algoritmo diferente ou definindo parâmetros de algoritmo avançados.</span><span class="sxs-lookup"><span data-stu-id="48cbc-145">Customize a mining model by applying filters to the training data, choosing a different algorithm, or setting advanced algorithm parameters.</span></span>|[<span data-ttu-id="48cbc-146">Personalizar os modelos de mineração e a estrutura</span><span class="sxs-lookup"><span data-stu-id="48cbc-146">Customize Mining Models and Structure</span></span>](customize-mining-models-and-structure.md)|  
|<span data-ttu-id="48cbc-147">Personalize um modelo de mineração aplicando filtros aos dados usados no treinamento do modo.</span><span class="sxs-lookup"><span data-stu-id="48cbc-147">Customize a mining model by applying filters to the data used in training the mode.</span></span>|[<span data-ttu-id="48cbc-148">Adicionar Modelos de Mineração a uma estrutura &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="48cbc-148">Add Mining Models to a Structure &#40;Analysis Services - Data Mining&#41;</span></span>](add-mining-models-to-a-structure-analysis-services-data-mining.md)|  
|<span data-ttu-id="48cbc-149">Atualize e gerencie as soluções de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="48cbc-149">Update and manage data mining solutions.</span></span>|<span data-ttu-id="48cbc-150">Link TBD</span><span class="sxs-lookup"><span data-stu-id="48cbc-150">Link TBD</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="48cbc-151">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="48cbc-151">See Also</span></span>  
 [<span data-ttu-id="48cbc-152">Tutoriais de Data Mining &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="48cbc-152">Data Mining Tutorials &#40;Analysis Services&#41;</span></span>](../data-mining-tutorials-analysis-services.md)  
  
  
