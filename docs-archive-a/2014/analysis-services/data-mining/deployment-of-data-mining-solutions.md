---
title: Implantação de soluções de mineração de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], deploying
- deploying [Analysis Services], production environments
- deploying [Analysis Services - data mining]
- solutions [Analysis Services], deploying
- models [Analysis Services], data mining
ms.assetid: d83effc7-437d-42e9-8ac3-b65f79e27043
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5764be2f7530add2fa4cb028b288be69598bb95c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582211"
---
# <a name="deployment-of-data-mining-solutions"></a><span data-ttu-id="af68c-102">Implantação de soluções de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="af68c-102">Deployment of Data Mining Solutions</span></span>
  <span data-ttu-id="af68c-103">A última etapa no processo de mineração de dados é implantar os modelos para um ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="af68c-103">The last step in the data mining process is to deploy the models to a production environment.</span></span> <span data-ttu-id="af68c-104">A implantação é importante porque torna os modelos disponíveis para usuários, para que você possa executar qualquer uma das tarefas a seguir:</span><span class="sxs-lookup"><span data-stu-id="af68c-104">Deployment is important because it makes the models available to users so that you can perform any of the following tasks:</span></span>  
  
-   <span data-ttu-id="af68c-105">Use os modelos para criar previsões e tomar decisões comerciais.</span><span class="sxs-lookup"><span data-stu-id="af68c-105">Use the models to create predictions and make business decisions.</span></span> <span data-ttu-id="af68c-106">Para obter informações sobre as ferramentas que você pode usar para criar consultas, consulte [interfaces de consulta de mineração de dados](data-mining-query-tools.md).</span><span class="sxs-lookup"><span data-stu-id="af68c-106">For information about the tools you can use to create queries, see [Data Mining Query Interfaces](data-mining-query-tools.md).</span></span>  
  
-   <span data-ttu-id="af68c-107">Insira a funcionalidade de mineração de dados diretamente em um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="af68c-107">Embed data mining functionality directly into an application.</span></span> <span data-ttu-id="af68c-108">Você pode incluir AMO (Objetos de Gerenciamento de Análise) ou um assembly que contém um conjunto de objetos que seu aplicativo pode usar para criar, alterar, processar e excluir estruturas e modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="af68c-108">You can include Analysis Management Objects (AMO) or an assembly that contains a set of objects that your application can use to create, alter, process, and delete mining structures and mining models.</span></span>  
  
-   <span data-ttu-id="af68c-109">Crie relatórios que permitem que os usuários solicitem previsões, exibam tendências ou comparem modelos.</span><span class="sxs-lookup"><span data-stu-id="af68c-109">Create reports that let users request predictions, view trends, or compare models.</span></span>  
  
 <span data-ttu-id="af68c-110">Esta seção fornece informações detalhadas sobre as opções de implantação.</span><span class="sxs-lookup"><span data-stu-id="af68c-110">This section provides detailed information about deployment options.</span></span>  
  
 [<span data-ttu-id="af68c-111">Requisitos para a implantação de soluções de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="af68c-111">Requirements for Deployment of Data Mining Solutions</span></span>](#bkmk_Reqs)  
  
 [<span data-ttu-id="af68c-112">Implantando uma solução relacional</span><span class="sxs-lookup"><span data-stu-id="af68c-112">Deploying a Relational Solution</span></span>](#bkmk_RelationalSltn)  
  
 [<span data-ttu-id="af68c-113">Implantando uma solução multidimensional</span><span class="sxs-lookup"><span data-stu-id="af68c-113">Deploying a Multidimensional Solution</span></span>](#bkmk_MDSltn)  
  
 [<span data-ttu-id="af68c-114">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="af68c-114">Related Resources</span></span>](#bkmk_Resources)  
  
## <a name="in-this-section"></a><span data-ttu-id="af68c-115">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="af68c-115">In This Section</span></span>  
 [<span data-ttu-id="af68c-116">Implantar uma solução de mineração de dados em versões anteriores do SQL Server</span><span class="sxs-lookup"><span data-stu-id="af68c-116">Deploy a Data Mining Solution to Previous Versions of SQL Server</span></span>](deploy-a-data-mining-solution-to-previous-versions-of-sql-server.md)  
  
 [<span data-ttu-id="af68c-117">Exportar e importar objetos de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="af68c-117">Export and Import Data Mining Objects</span></span>](export-and-import-data-mining-objects.md)  
  
##  <a name="requirements-for-deployment-of-data-mining-solutions"></a><a name="bkmk_Reqs"></a> <span data-ttu-id="af68c-118">Requisitos para a implantação de soluções de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="af68c-118">Requirements for Deployment of Data Mining Solutions</span></span>  
 <span data-ttu-id="af68c-119">A instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para o qual você implanta a solução deve estar sendo executada em um modo que dá suporte a objetos multidimensionais e objetos de mineração de dados; ou seja, você não pode implantar objetos de mineração de dados em uma instância que hospeda modelos de tabela ou dados PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="af68c-119">The instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to which you deploy the solution must be running in a mode that supports multidimensional objects and data mining objects; that is, you cannot deploy data mining objects to an instance that hosts tabular models or PowerPivot data.</span></span>  
  
 <span data-ttu-id="af68c-120">Portanto, quando você cria uma solução de mineração de dados no Visual Studio, use o modelo **Projeto Multidimensional e de Mineração de Dados do Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="af68c-120">Therefore, when you create a data mining solution in Visual Studio, be sure to use the template, **Analysis Services Multidimensional and Data Mining Project**.</span></span>  
  
 <span data-ttu-id="af68c-121">Quando você implanta a solução, os objetos usados para mineração de dados são criados na instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] especificada, em um banco de dados com o mesmo nome do arquivo de solução.</span><span class="sxs-lookup"><span data-stu-id="af68c-121">When you deploy the solution, the objects used for data mining are created in the specified [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, in a database with the same name as the solution file.</span></span>  
  
###  <a name="deploying-a-relational-solution"></a><a name="bkmk_RelationalSltn"></a><span data-ttu-id="af68c-122">Implantando uma solução relacional</span><span class="sxs-lookup"><span data-stu-id="af68c-122">Deploying a Relational Solution</span></span>  
 <span data-ttu-id="af68c-123">Quando você implanta uma solução de mineração de dados relacional, os objetos de mineração de dados exigidos são criados dentro de um novo banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e os objetos são processados por padrão.</span><span class="sxs-lookup"><span data-stu-id="af68c-123">When you deploy a relational data mining solution, the required data mining objects are created within a new [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, and the objects are processed by default.</span></span> <span data-ttu-id="af68c-124">Você pode alterar as opções de processamento usando a propriedade de configuração, **Opção de Processamento**.</span><span class="sxs-lookup"><span data-stu-id="af68c-124">You can change processing options by using the configuration property, **Processing Option**.</span></span> <span data-ttu-id="af68c-125">Para obter mais informações, consulte [Configurar propriedades do projeto do Analysis Services &#40;SSDT&#41;](../multidimensional-models/configure-analysis-services-project-properties-ssdt.md).</span><span class="sxs-lookup"><span data-stu-id="af68c-125">For more information, see [Configure Analysis Services Project Properties &#40;SSDT&#41;](../multidimensional-models/configure-analysis-services-project-properties-ssdt.md).</span></span>  
  
 <span data-ttu-id="af68c-126">Por padrão, somente as alterações incrementais são implantadas de cada vez.</span><span class="sxs-lookup"><span data-stu-id="af68c-126">By default, only incremental changes are deployed each time.</span></span> <span data-ttu-id="af68c-127">Em outras palavras, você pode modificar um modelo de mineração e, quando reimplantar o projeto, somente o modelo de mineração será atualizado.</span><span class="sxs-lookup"><span data-stu-id="af68c-127">In other words, you can modify a mining model, and when you re-deploy the project, only that mining model would be updated.</span></span> <span data-ttu-id="af68c-128">Porém, se você tiver vários clientes que editam o banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , isto poderá levar a erros.</span><span class="sxs-lookup"><span data-stu-id="af68c-128">However, if you have multiple clients editing the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, this can lead to errors.</span></span> <span data-ttu-id="af68c-129">Para alterar o modo de implantação padrão para que o banco de dados inteiro seja atualizado quando você implantar a solução, altere a propriedade **Modo de Implantação**</span><span class="sxs-lookup"><span data-stu-id="af68c-129">To change the default deployment mode so that the entire database is refreshed when you deploy the solution, change the **Deployment Mode** property</span></span>  
  
 <span data-ttu-id="af68c-130">Em uma solução de mineração de dados relacional, os únicos objetos que devem ser implantados são a definição de fonte de dados, as exibições da fonte de dados que foram usadas, as estruturas de mineração e todos os modelos de mineração dependentes.</span><span class="sxs-lookup"><span data-stu-id="af68c-130">In a relational data mining solution, the only objects that must be deployed are the data source definition, any data source views that were used, the mining structures, and all dependent mining models.</span></span>  
  
###  <a name="deploying-a-multidimensional-solution"></a><a name="bkmk_MDSltn"></a><span data-ttu-id="af68c-131">Implantando uma solução multidimensional</span><span class="sxs-lookup"><span data-stu-id="af68c-131">Deploying a Multidimensional Solution</span></span>  
 <span data-ttu-id="af68c-132">Quando você implanta uma solução de mineração de dados multidimensional, esta solução cria seus objetos de mineração de dados dentro do mesmo banco de dados do cubo de origem.</span><span class="sxs-lookup"><span data-stu-id="af68c-132">When you deploy a multidimensional data mining solution, this solution creates your data mining objects within the same database as the source cube.</span></span>  
  
 <span data-ttu-id="af68c-133">Quando você processa a estrutura de mineração ou o modelo de mineração, você também deve processar o cubo de origem.</span><span class="sxs-lookup"><span data-stu-id="af68c-133">When you process the mining structure or mining model, you must process the source cube as well.</span></span> <span data-ttu-id="af68c-134">Por isto, implantar uma solução que usa modelos de mineração OLAP pode levar mais tempo que as soluções de mineração de dados relacionais.</span><span class="sxs-lookup"><span data-stu-id="af68c-134">For this reason, deploying a solution that uses OLAP mining models can take longer than relational data mining solutions.</span></span>  
  
 <span data-ttu-id="af68c-135">Normalmente os objetos de mineração de dados também usam as mesmas fontes de dados e exibições da fonte de dados que são usadas para o cubo.</span><span class="sxs-lookup"><span data-stu-id="af68c-135">Typically data mining objects also use the same data sources and data source views that are used for the cube.</span></span> <span data-ttu-id="af68c-136">No entanto, você pode adicionar fontes de dados e exibições da fonte de dados que são destinadas especificamente para mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="af68c-136">However, you can add data sources and data source views that are targeted specifically to data mining.</span></span> <span data-ttu-id="af68c-137">Por exemplo, normalmente um cubo não conteria dados sobre clientes em potencial ou dados externos que não são usados nos objetos multidimensionais.</span><span class="sxs-lookup"><span data-stu-id="af68c-137">For example, typically a cube would not contain data about prospective clients, or external data not used in the multidimensional objects.</span></span>  
  
##  <a name="related-resources"></a><a name="bkmk_Resources"></a><span data-ttu-id="af68c-138">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="af68c-138">Related Resources</span></span>  
 [<span data-ttu-id="af68c-139">Movendo objetos de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="af68c-139">Moving Data Mining Objects</span></span>](moving-data-mining-objects.md)  
  
 <span data-ttu-id="af68c-140">Se seu modelo for baseado somente em dados relacionais, exportar e importar objetos usando DMX é o modo mais fácil de mover modelos.</span><span class="sxs-lookup"><span data-stu-id="af68c-140">If your model is based on relational data only, exporting and importing objects using DMX is the easiest way to move models.</span></span>  
  
 [<span data-ttu-id="af68c-141">Mover um Banco de Dados do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="af68c-141">Move an Analysis Services Database</span></span>](../multidimensional-models/move-an-analysis-services-database.md)  
  
 <span data-ttu-id="af68c-142">Quando os modela usam um cubo como uma fonte de dados, consulte este tópico para obter mais informações sobre como mover modelos e os dados de cubo de suporte.</span><span class="sxs-lookup"><span data-stu-id="af68c-142">When models use a cube as a data source, refer to this topic for more information about how to move models and their supporting cube data.</span></span>  
  
 [<span data-ttu-id="af68c-143">Implantar projetos do Analysis Services &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="af68c-143">Deploy Analysis Services Projects &#40;SSDT&#41;</span></span>](../multidimensional-models/deploy-analysis-services-projects-ssdt.md)  
  
 <span data-ttu-id="af68c-144">Fornece informações gerais sobre a implantação de projetos do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e descreve as propriedades que você pode definir como parte da configuração de projeto.</span><span class="sxs-lookup"><span data-stu-id="af68c-144">Provides general information about deployment of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projects, and describes the properties that you can set as part of the project configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af68c-145">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="af68c-145">See Also</span></span>  
 <span data-ttu-id="af68c-146">[Processamento de objeto de modelo multidimensional](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="af68c-146">[Multidimensional Model Object Processing](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md) </span></span>  
 <span data-ttu-id="af68c-147">[Interfaces de consulta de mineração de dados](data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="af68c-147">[Data Mining Query Interfaces](data-mining-query-tools.md) </span></span>  
 [<span data-ttu-id="af68c-148">Requisitos e considerações de processamento &#40;Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="af68c-148">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](processing-requirements-and-considerations-data-mining.md)  
  
  
