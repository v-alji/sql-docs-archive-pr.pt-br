---
title: Funcionalidade de Analysis Services descontinuada no SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Analysis Services, backward compatibility
- SSAS, backward compatibility
- SQL Server Analysis Services, backward compatibility
- discontinued functionality [Analysis Services]
- unsupported features [Analysis Services]
ms.assetid: 39406be1-9819-4629-9c29-b32fb20bab2e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5414344eb65c907593c9077ee2ba5610b8b397c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583229"
---
# <a name="discontinued-analysis-services-functionality-in-sql-server-2014"></a><span data-ttu-id="0d550-102">Funcionalidade descontinuada do Analysis Services no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="0d550-102">Discontinued Analysis Services Functionality in SQL Server 2014</span></span>
  <span data-ttu-id="0d550-103">Este tópico descreve os recursos do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que não estão mais disponíveis no [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d550-103">This topic describes [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] features that are no longer available in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
## <a name="discontinued-features-in-sssql14"></a><span data-ttu-id="0d550-104">Recursos descontinuados no [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d550-104">Discontinued Features in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]</span></span>  
  
|<span data-ttu-id="0d550-105">Categoria</span><span class="sxs-lookup"><span data-stu-id="0d550-105">Category</span></span>|<span data-ttu-id="0d550-106">Recurso substituído</span><span class="sxs-lookup"><span data-stu-id="0d550-106">Deprecated feature</span></span>|<span data-ttu-id="0d550-107">Substituição</span><span class="sxs-lookup"><span data-stu-id="0d550-107">Replacement</span></span>|  
|--------------|------------------------|-----------------|  
|<span data-ttu-id="0d550-108">Cubos locais</span><span class="sxs-lookup"><span data-stu-id="0d550-108">Local cubes</span></span>|<span data-ttu-id="0d550-109">Propriedade da cadeia de conexão InsertInto</span><span class="sxs-lookup"><span data-stu-id="0d550-109">InsertInto connection string property</span></span>|<span data-ttu-id="0d550-110">A sintaxe da cadeia de conexão original para popular cubos locais foi substituída pela instrução Criar Cubo Global.</span><span class="sxs-lookup"><span data-stu-id="0d550-110">Original connection string syntax for populating local cubes is replaced by the Create Global Cube statement.</span></span> <span data-ttu-id="0d550-111">Para obter mais informações, consulte [criar instrução de cubo GLOBAL &#40;&#41;MDX ](/sql/mdx/mdx-data-definition-create-global-cube).</span><span class="sxs-lookup"><span data-stu-id="0d550-111">For more information, see [CREATE GLOBAL CUBE Statement  &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-global-cube).</span></span>|  
|<span data-ttu-id="0d550-112">Cubos locais</span><span class="sxs-lookup"><span data-stu-id="0d550-112">Local cubes</span></span>|<span data-ttu-id="0d550-113">Propriedade da cadeia de conexão CreateCube</span><span class="sxs-lookup"><span data-stu-id="0d550-113">CreateCube connection string property</span></span>|<span data-ttu-id="0d550-114">A sintaxe da cadeia de conexão original para popular cubos locais foi substituída pela instrução Criar Cubo Global.</span><span class="sxs-lookup"><span data-stu-id="0d550-114">Original connection string syntax for populating local cubes is replaced by the Create Global Cube statement.</span></span> <span data-ttu-id="0d550-115">Para obter mais informações, consulte [criar instrução de cubo GLOBAL &#40;&#41;MDX ](/sql/mdx/mdx-data-definition-create-global-cube).</span><span class="sxs-lookup"><span data-stu-id="0d550-115">For more information, see [CREATE GLOBAL CUBE Statement  &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-global-cube).</span></span>|  
|<span data-ttu-id="0d550-116">Mineração de dados</span><span class="sxs-lookup"><span data-stu-id="0d550-116">Data Mining</span></span>|<span data-ttu-id="0d550-117">SQL Server 2000 PMML</span><span class="sxs-lookup"><span data-stu-id="0d550-117">SQL Server 2000 PMML</span></span>|<span data-ttu-id="0d550-118">O recurso SQL Server 2000 PMML gerou um formulário de PMML que teve extensões proprietárias para dar suporte a recursos exclusivos fornecidos por algoritmos de Mineração de Dados que não estavam disponíveis na especificação PMML.</span><span class="sxs-lookup"><span data-stu-id="0d550-118">The SQL Server 2000 PMML feature produced a form of PMML that had proprietary extensions to support unique features provided by Data Mining algorithms that were not available in the PMML specification.</span></span> <span data-ttu-id="0d550-119">No SQL Server 2005, o Analysis Services atualizou o recurso PMML para o padrão mais recente PMML 2.1.</span><span class="sxs-lookup"><span data-stu-id="0d550-119">In SQL Server 2005, Analysis Services updated the PMML feature to the newer PMML 2.1 standard.</span></span> <span data-ttu-id="0d550-120">Como resultado, as extensões proprietárias adicionadas ao SQL Server 2000 não são mais necessárias, embora ainda tenham suporte nessa versão.</span><span class="sxs-lookup"><span data-stu-id="0d550-120">As a result, the proprietary extensions added in SQL Server 2000 are no longer needed, although they are still supported in this release.</span></span>|  
|<span data-ttu-id="0d550-121">Instrução MDX</span><span class="sxs-lookup"><span data-stu-id="0d550-121">MDX Statement</span></span>|<span data-ttu-id="0d550-122">Instrução Criar Ação</span><span class="sxs-lookup"><span data-stu-id="0d550-122">Create Action statement</span></span>|<span data-ttu-id="0d550-123">Esta instrução é incluída para compatibilidade com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="0d550-123">This statement is included for backwards compatibility.</span></span> <span data-ttu-id="0d550-124">Ela foi substituída pelo objeto Ação.</span><span class="sxs-lookup"><span data-stu-id="0d550-124">It is replaced by the Action object.</span></span> <span data-ttu-id="0d550-125">Para obter mais informações sobre como criar ações em versões recentes do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , consulte [ações &#40;Analysis Services de dados multidimensionais&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="0d550-125">For more information about how to create actions in recent versions of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], see [Actions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md).</span></span>|  
  
## <a name="discontinued-features-in-previous-releases"></a><span data-ttu-id="0d550-126">Recursos descontinuados em versões anteriores</span><span class="sxs-lookup"><span data-stu-id="0d550-126">Discontinued Features in Previous Releases</span></span>  
 <span data-ttu-id="0d550-127">O Assistente de Migração, usado para migrar os bancos de dados do SQL Server 2000 Analysis Services para versões mais recentes, será descontinuado porque o SQL Server 2000 não conta mais com suporte.</span><span class="sxs-lookup"><span data-stu-id="0d550-127">Migration Wizard, used to migrate SQL Server 2000 Analysis Services databases to newer versions, is discontinued because SQL Server 2000 is no longer supported.</span></span>  
  
 <span data-ttu-id="0d550-128">A biblioteca DSO (Decision Support Objects) que fornecia compatibilidade com os bancos de dados do SQL Server 2000 Analysis Services também será descontinuada e não faz mais parte do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0d550-128">Decision Support Objects (DSO) library that provided compatibility with SQL Server 2000 Analysis Services databases is also discontinued and no longer part of SQL Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d550-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0d550-129">See Also</span></span>  
 [<span data-ttu-id="0d550-130">Analysis Services Backward Compatibility</span><span class="sxs-lookup"><span data-stu-id="0d550-130">Analysis Services Backward Compatibility</span></span>](analysis-services-backward-compatibility.md)  
  
  
