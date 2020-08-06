---
title: Objetos Database (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- objects [Analysis Services], about objects
- SQL Server Analysis Services, objects
- Analysis Services objects, about Analysis Services objects
- SSAS, objects
- Analysis Services objects
- objects [Analysis Services]
ms.assetid: f76d869b-fc1d-4807-9f28-da09c7be382d
author: minewiskan
ms.author: owend
ms.openlocfilehash: d61e3213356146e1cf9e452e0b62e02c96bd4902
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686429"
---
# <a name="database-objects-analysis-services---multidimensional-data"></a><span data-ttu-id="bc214-102">Objetos de banco de dados (Analysis Services – Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="bc214-102">Database Objects (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="bc214-103">Uma [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instância contém objetos de banco de dados e assemblies para uso com OLAP (processamento analítico online) e Data Mining.</span><span class="sxs-lookup"><span data-stu-id="bc214-103">A [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance contains database objects and assemblies for use with online analytical processing (OLAP) and data mining.</span></span>  
  
-   <span data-ttu-id="bc214-104">Os bancos de dados contêm objetos OLAP e dados de mineração, como fontes de dados, exibições de fonte de dados, cubos, medidas, grupos de medidas, dimensões, atributos, hierarquias, estruturas de mineração de dados, modelos de mineração de dados e funções.</span><span class="sxs-lookup"><span data-stu-id="bc214-104">Databases contain OLAP and data mining objects, such as data sources, data source views, cubes, measures, measure groups, dimensions, attributes, hierarchies, mining structures, mining models and roles.</span></span>  
  
-   <span data-ttu-id="bc214-105">Os assemblies contêm funções definidas pelo usuário que ampliam a funcionalidade de funções intrínsecas, fornecidas com as linguagens MDX e extensões de mineração de dados (DMX).</span><span class="sxs-lookup"><span data-stu-id="bc214-105">Assemblies contain user-defined functions that extend the functionality of the intrinsic functions provided with the Multidimensional Expressions (MDX) and Data Mining Extensions (DMX) languages.</span></span>  
  
 <span data-ttu-id="bc214-106">O objeto <xref:Microsoft.AnalysisServices.Database> é o contêiner de todos os objetos de dados necessários para um projeto de business intelligence (como cubos OLAP, dimensões e estruturas de mineração de dados) e seus objetos de suporte (como <xref:Microsoft.AnalysisServices.DataSource>, <xref:Microsoft.AnalysisServices.Account> e <xref:Microsoft.AnalysisServices.Role>).</span><span class="sxs-lookup"><span data-stu-id="bc214-106">The <xref:Microsoft.AnalysisServices.Database> object is the container for all data objects that are needed for a business intelligence project (such as OLAP cubes, dimensions, and data mining structures), and their supporting objects (such as <xref:Microsoft.AnalysisServices.DataSource>, <xref:Microsoft.AnalysisServices.Account>, and <xref:Microsoft.AnalysisServices.Role>).</span></span>  
  
 <span data-ttu-id="bc214-107">Um objeto <xref:Microsoft.AnalysisServices.Database> fornece acesso a objetos e atributos incluindo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bc214-107">A <xref:Microsoft.AnalysisServices.Database> object provides access to objects and attributes that include the following:</span></span>  
  
-   <span data-ttu-id="bc214-108">Todos os cubos que você pode acessar, como uma coleção.</span><span class="sxs-lookup"><span data-stu-id="bc214-108">All cubes that you can access, as a collection.</span></span>  
  
-   <span data-ttu-id="bc214-109">Todas as dimensões que você pode acessar, como uma coleção.</span><span class="sxs-lookup"><span data-stu-id="bc214-109">All dimensions that you can access, as a collection.</span></span>  
  
-   <span data-ttu-id="bc214-110">Todas as estruturas de mineração que você pode acessar, como uma coleção.</span><span class="sxs-lookup"><span data-stu-id="bc214-110">All mining structures that you can access, as a collection.</span></span>  
  
-   <span data-ttu-id="bc214-111">Todas as fontes de dados e exibições de fonte de dados, como duas coleções.</span><span class="sxs-lookup"><span data-stu-id="bc214-111">All data sources and data source views, as two collections.</span></span>  
  
-   <span data-ttu-id="bc214-112">Todas as funções e permissões de banco de dados, como duas coleções.</span><span class="sxs-lookup"><span data-stu-id="bc214-112">All roles and database permissions, as two collections.</span></span>  
  
-   <span data-ttu-id="bc214-113">O valor da ordenação para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bc214-113">The collation value for the database.</span></span>  
  
-   <span data-ttu-id="bc214-114">O tamanho estimado do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bc214-114">The estimated size of the database.</span></span>  
  
-   <span data-ttu-id="bc214-115">O valor do idioma do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bc214-115">The language value of the database.</span></span>  
  
-   <span data-ttu-id="bc214-116">A configuração visível do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bc214-116">The visible setting for the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bc214-117">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="bc214-117">In This Section</span></span>  
 <span data-ttu-id="bc214-118">Os tópicos seguintes descrevem objetos compartilhados por recursos OLAP e mineração de dados no [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc214-118">The following topics describe objects shared by both OLAP and data mining features in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>  
  
|<span data-ttu-id="bc214-119">Tópico</span><span class="sxs-lookup"><span data-stu-id="bc214-119">Topic</span></span>|<span data-ttu-id="bc214-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="bc214-120">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="bc214-121">Fontes de dados em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="bc214-121">Data Sources in Multidimensional Models</span></span>](../data-sources-in-multidimensional-models.md)|<span data-ttu-id="bc214-122">Descreve uma fonte de dados no [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc214-122">Describes a data source in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="bc214-123">Exibições de fontes de dados em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="bc214-123">Data Source Views in Multidimensional Models</span></span>](../data-source-views-in-multidimensional-models.md)|<span data-ttu-id="bc214-124">Descreve um modelo de dados lógico baseado em uma ou mais fontes de dados, no [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc214-124">Describes a logical data model based on one or more data sources, in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="bc214-125">Cubos em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="bc214-125">Cubes in Multidimensional Models</span></span>](../cubes-in-multidimensional-models.md)|<span data-ttu-id="bc214-126">Descreve cubos e objetos de cubo, incluindo medidas, grupos de medidas, relações de uso de dimensão, cálculos indicadores de desempenho principais, ações, traduções, partições e perspectivas.</span><span class="sxs-lookup"><span data-stu-id="bc214-126">Describes cubes and cube objects, including measures, measure groups, dimension usage relationships, calculations, key performance indicators, actions, translations, partitions, and perspectives.</span></span>|  
|[<span data-ttu-id="bc214-127">Dimensões &#40;Analysis Services – Dados Multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="bc214-127">Dimensions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../../multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md)|<span data-ttu-id="bc214-128">Descreve dimensões e objetos de dimensão, inclusive atributos, relações de atributo, hierarquias, níveis e membros.</span><span class="sxs-lookup"><span data-stu-id="bc214-128">Describes dimensions and dimension objects, including attributes, attribute relationships, hierarchies, levels, and members.</span></span>|  
|[<span data-ttu-id="bc214-129">Estruturas de Mineração &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="bc214-129">Mining Structures &#40;Analysis Services - Data Mining&#41;</span></span>](../../data-mining/mining-structures-analysis-services-data-mining.md)|<span data-ttu-id="bc214-130">Descreve estruturas e objetos de mineração de dados, inclusive modelos de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="bc214-130">Describes mining structures and mining objects, including mining models.</span></span>|  
|[<span data-ttu-id="bc214-131">Funções de Segurança &#40;Analysis Services – Dados Multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="bc214-131">Security Roles  &#40;Analysis Services - Multidimensional Data&#41;</span></span>](security-roles-analysis-services-multidimensional-data.md)|<span data-ttu-id="bc214-132">Descreve uma função, o mecanismo de segurança usado para controlar o acesso a objetos no [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc214-132">Describes a role, the security mechanism used to control access to objects in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="bc214-133">Gerenciamento de assemblies de modelo multidimensional</span><span class="sxs-lookup"><span data-stu-id="bc214-133">Multidimensional Model Assemblies Management</span></span>](../multidimensional-model-assemblies-management.md)|<span data-ttu-id="bc214-134">Descreve um assembly, uma coleção de funções definidas pelo usuário e usada para ampliar as linguagens MDX e DMX, no [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc214-134">Describes an assembly, a collection of user-defined functions used to extend the MDX and DMX languages, in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bc214-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bc214-135">See Also</span></span>  
 <span data-ttu-id="bc214-136">[Fontes de dados com suporte &#40;SSAS multidimensional&#41;](../supported-data-sources-ssas-multidimensional.md) </span><span class="sxs-lookup"><span data-stu-id="bc214-136">[Data Sources Supported &#40;SSAS Multidimensional&#41;](../supported-data-sources-ssas-multidimensional.md) </span></span>  
 <span data-ttu-id="bc214-137">[Soluções de modelo multidimensional &#40;SSAS&#41;](../multidimensional-model-solutions-ssas.md) </span><span class="sxs-lookup"><span data-stu-id="bc214-137">[Multidimensional Model Solutions &#40;SSAS&#41;](../multidimensional-model-solutions-ssas.md) </span></span>  
 [<span data-ttu-id="bc214-138">Soluções de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="bc214-138">Data Mining Solutions</span></span>](../../data-mining/data-mining-solutions.md)  
  
  
