---
title: Exibições da fonte de dados em modelos multidimensionais | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data source views [Analysis Services]
- data source views [Analysis Services], about data source views
- SQL Server Analysis Services, data source views
- data source views [Analysis Services], multiple
- Analysis Services, data source views
- multiple data source views
- SSAS, data source views
ms.assetid: 4c12376f-4fc2-492b-9a00-93eec34571ed
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1aef6b6d716ec71ac082ca8b7c042492c1712b1a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685351"
---
# <a name="data-source-views-in-multidimensional-models"></a><span data-ttu-id="dcf12-102">Exibições de fontes de dados em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="dcf12-102">Data Source Views in Multidimensional Models</span></span>
  <span data-ttu-id="dcf12-103">Uma DSV (exibição da fonte de dados) é uma abstração de uma fonte de dados relacional que se torna a base dos cubos e das dimensões que você cria em um projeto multidimensional.</span><span class="sxs-lookup"><span data-stu-id="dcf12-103">A data source view (DSV) is an abstraction of a relational data source that becomes the basis of the cubes and dimensions you create in a multidimensional project.</span></span> <span data-ttu-id="dcf12-104">A finalidade de uma DSV é conceder o controle sobre as estruturas de dados usadas em seu projeto e funcionar independentemente das fontes de dados subjacentes (por exemplo, a capacidade de renomear ou concatenar colunas sem modificar diretamente a fonte de dados original).</span><span class="sxs-lookup"><span data-stu-id="dcf12-104">The purpose of a DSV is to give you control over the data structures used in your project, and to work independently of the underlying data sources (for example, the ability to rename or concatenate columns without directly modifying the original data source).</span></span>  
  
 <span data-ttu-id="dcf12-105">Você pode compilar várias exibições de fontes de dados em um projeto ou banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] em uma ou mais fontes de dados e construir cada uma delas para atender aos requisitos de uma solução diferente.</span><span class="sxs-lookup"><span data-stu-id="dcf12-105">You can build multiple data source views in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or database on one or more data sources, and construct each one to satisfy the requirements for a different solution.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="dcf12-106">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="dcf12-106">Related Tasks</span></span>  
 [<span data-ttu-id="dcf12-107">Como definir uma exibição da fonte de dados &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dcf12-107">Defining a Data Source View &#40;Analysis Services&#41;</span></span>](defining-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="dcf12-108">Como adicionar ou remover tabelas ou exibições em uma exibição da fonte de dados &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dcf12-108">Adding or Removing Tables or Views in a Data Source View &#40;Analysis Services&#41;</span></span>](adding-or-removing-tables-or-views-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="dcf12-109">Alterar propriedades em uma exibição da fonte de dados &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dcf12-109">Change Properties in a Data Source View &#40;Analysis Services&#41;</span></span>](change-properties-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="dcf12-110">Definir relações lógicas em uma exibição da fonte de dados &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dcf12-110">Define Logical Relationships in a Data Source View &#40;Analysis Services&#41;</span></span>](define-logical-relationships-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="dcf12-111">Definir chaves primárias lógicas em uma exibição da fonte de dados &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dcf12-111">Define Logical Primary Keys in a Data Source View &#40;Analysis Services&#41;</span></span>](define-logical-primary-keys-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="dcf12-112">Definir cálculos nomeados em uma exibição da fonte de dados &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dcf12-112">Define Named Calculations in a Data Source View &#40;Analysis Services&#41;</span></span>](define-named-calculations-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="dcf12-113">Definir consultas nomeadas em uma exibição da fonte de dados &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dcf12-113">Define Named Queries in a Data Source View &#40;Analysis Services&#41;</span></span>](define-named-queries-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="dcf12-114">Substituir uma tabela ou uma consulta nomeada em uma exibição da fonte de dados &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dcf12-114">Replace a Table or a Named Query in a Data Source View &#40;Analysis Services&#41;</span></span>](replace-a-table-or-a-named-query-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="dcf12-115">Trabalhar com diagramas em um Designer de exibição da fonte de dados &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dcf12-115">Work with Diagrams in Data Source View Designer &#40;Analysis Services&#41;</span></span>](work-with-diagrams-in-data-source-view-designer-analysis-services.md)  
  
 [<span data-ttu-id="dcf12-116">Explorar dados em uma exibição da fonte de dados &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dcf12-116">Explore Data in a Data Source View &#40;Analysis Services&#41;</span></span>](explore-data-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="dcf12-117">Excluir uma exibição da fonte de dados &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dcf12-117">Delete a Data Source View &#40;Analysis Services&#41;</span></span>](delete-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="dcf12-118">Atualizar o esquema em uma exibição da fonte de dados &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dcf12-118">Refresh the Schema in a Data Source View &#40;Analysis Services&#41;</span></span>](refresh-the-schema-in-a-data-source-view-analysis-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="dcf12-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dcf12-119">See Also</span></span>  
 <span data-ttu-id="dcf12-120">[&#40;Analysis Services do assistente de geração de esquema&#41;](schema-generation-wizard-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="dcf12-120">[Schema Generation Wizard &#40;Analysis Services&#41;](schema-generation-wizard-analysis-services.md) </span></span>  
 [<span data-ttu-id="dcf12-121">Fontes de dados com suporte &#40;SSAS multidimensional&#41;</span><span class="sxs-lookup"><span data-stu-id="dcf12-121">Data Sources Supported &#40;SSAS Multidimensional&#41;</span></span>](supported-data-sources-ssas-multidimensional.md)  
  
  
