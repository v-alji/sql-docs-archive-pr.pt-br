---
title: Consultando dados multidimensionais com MDX | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- multidimensional data [Analysis Services], querying
ms.assetid: e0a5dd60-35a3-4a4f-b36f-52ecea814886
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7b7589a98636e56e8c592cef213785544e18f4ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581555"
---
# <a name="querying-multidimensional-data-with-mdx"></a><span data-ttu-id="d424d-102">Consultando dados multidimensionais com MDX</span><span class="sxs-lookup"><span data-stu-id="d424d-102">Querying Multidimensional Data with MDX</span></span>
  <span data-ttu-id="d424d-103">Expressões multidimensionais (MDX) é a linguagem de consulta que você usa para trabalhar com e recuperar dados multidimensionais no [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d424d-103">Multidimensional Expressions (MDX) is the query language that you use to work with and retrieve multidimensional data in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="d424d-104">O MDX é baseado na especificação de XML for Analysis (XMLA), com extensões específicas para o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d424d-104">MDX is based on the XML for Analysis (XMLA) specification, with specific extensions for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="d424d-105">O MDX utiliza expressões compostas de identificadores, valores, instruções, funções e operadores que o [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] pode avaliar para recuperar um objeto (por exemplo, um conjunto ou um membro) ou um valor escalar (por exemplo, uma cadeia de caracteres ou um número).</span><span class="sxs-lookup"><span data-stu-id="d424d-105">MDX utilizes expressions composed of identifiers, values, statements, functions, and operators that [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] can evaluate to retrieve an object (for example a set or a member), or a scalar value (for example, a string or a number).</span></span>  
  
 <span data-ttu-id="d424d-106">Consultas e expressões MDX no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] são usadas para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d424d-106">MDX queries and expressions in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] are used to do the following:</span></span>  
  
-   <span data-ttu-id="d424d-107">Retornar dados a um aplicativo cliente de um [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] cubo.</span><span class="sxs-lookup"><span data-stu-id="d424d-107">Return data to a client application from a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] cube.</span></span>  
  
-   <span data-ttu-id="d424d-108">Formatar resultados de consulta.</span><span class="sxs-lookup"><span data-stu-id="d424d-108">Format query results.</span></span>  
  
-   <span data-ttu-id="d424d-109">Executar tarefas de design de cubo, incluindo a definição de membros calculados, conjuntos nomeados, tarefas de escopo e KPIs (indicadores chave de desempenho).</span><span class="sxs-lookup"><span data-stu-id="d424d-109">Perform cube design tasks, including the definition of calculated members, named sets, scoped assignments, and key performance indicators (KPIs).</span></span>  
  
-   <span data-ttu-id="d424d-110">Executar tarefas administrativas, incluindo dimensão e segurança da célula.</span><span class="sxs-lookup"><span data-stu-id="d424d-110">Perform administrative tasks, including dimension and cell security.</span></span>  
  
 <span data-ttu-id="d424d-111">O MDX é superficialmente semelhante em muitas formas à sintaxe de SQL que normalmente é usada em bancos de dados relacionais.</span><span class="sxs-lookup"><span data-stu-id="d424d-111">MDX is superficially similar in many ways to the SQL syntax that is typically used with relational databases.</span></span> <span data-ttu-id="d424d-112">Porém, o MDX não é uma extensão da linguagem SQL e é diferente do SQL em muitas formas.</span><span class="sxs-lookup"><span data-stu-id="d424d-112">However, MDX is not an extension of the SQL language and is different from SQL in many ways.</span></span> <span data-ttu-id="d424d-113">Para criar expressões MDX usadas para desenhar ou proteger cubos, ou para criar consultas de MDX para retornar e formatar dados multidimensionais, você precisa entender os conceitos básicos de modelagem MDX e dimensional, elementos de sintaxe MDX, operadores MDX, instruções MDX e funções MDX.</span><span class="sxs-lookup"><span data-stu-id="d424d-113">In order to create MDX expressions used to design or secure cubes, or to create MDX queries to return and format multidimensional data, you need to understand basic concepts in MDX and dimensional modeling, MDX syntax elements, MDX operators, MDX statements, and MDX functions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d424d-114">Para obter mais informações, consulte a seção recursos adicionais na página [SQL Server 2005-Analysis Services](https://go.microsoft.com/fwlink/?LinkId=80853) no site do Microsoft TechNet.</span><span class="sxs-lookup"><span data-stu-id="d424d-114">For more information, see the Additional Resources section on the [SQL Server 2005 - Analysis Services](https://go.microsoft.com/fwlink/?LinkId=80853) page on the Microsoft TechNet Web site.</span></span> <span data-ttu-id="d424d-115">Para obter mais informações sobre problemas de desempenho relacionados a cálculos e consultas MDX, consulte a seção "escrevendo MDX eficiente" no [Guia de desempenho do SQL Server 2005 Analysis Services](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span><span class="sxs-lookup"><span data-stu-id="d424d-115">For more information about performance issues related to MDX queries and calculations, see the section "Writing Efficient MDX" in the [SQL Server 2005 Analysis Services Performance Guide](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d424d-116">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="d424d-116">In This Section</span></span>  
  
|<span data-ttu-id="d424d-117">Tópico</span><span class="sxs-lookup"><span data-stu-id="d424d-117">Topic</span></span>|<span data-ttu-id="d424d-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="d424d-118">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="d424d-119">Principais conceitos em MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d424d-119">Key Concepts in MDX &#40;Analysis Services&#41;</span></span>](../key-concepts-in-mdx-analysis-services.md)|<span data-ttu-id="d424d-120">Você pode usar MDX (Multidimensional Expressions) para consultar dados multidimensionais ou para criar expressões MDX para uso em um cubo, mas primeiro você deve entender os [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] conceitos e a terminologia da dimensão.</span><span class="sxs-lookup"><span data-stu-id="d424d-120">You can use Multidimensional Expressions (MDX) to query multidimensional data or to create MDX expressions for use within a cube, but first you should understand [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] dimension concepts and terminology.</span></span>|  
|[<span data-ttu-id="d424d-121">Conceitos básicos de consulta MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d424d-121">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)|<span data-ttu-id="d424d-122">A linguagem MDX permite que você consulte objetos multidimensionais, como cubos, e retorna conjuntos de células multidimensionais que contêm dados do cubo.</span><span class="sxs-lookup"><span data-stu-id="d424d-122">Multidimensional Expressions (MDX) enables you to query multidimensional objects, such as cubes, and return multidimensional cellsets that contain the cube's data.</span></span> <span data-ttu-id="d424d-123">Este tópico e respectivos subtópicos fornecem uma visão geral das consultas MDX.</span><span class="sxs-lookup"><span data-stu-id="d424d-123">This topic and its subtopics provide an overview of MDX queries.</span></span>|  
|[<span data-ttu-id="d424d-124">Conceitos básicos do script MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d424d-124">MDX Scripting Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-scripting-fundamentals-analysis-services.md)|<span data-ttu-id="d424d-125">No [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] , um script MDX é composto de uma ou mais expressões MDX ou instruções que preenchem um cubo com cálculos.</span><span class="sxs-lookup"><span data-stu-id="d424d-125">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], a Multidimensional Expressions (MDX) script is made up of one or more MDX expressions or statements that populate a cube with calculations.</span></span><br /><br /> <span data-ttu-id="d424d-126">Um script MDX define o processo de cálculo de um cubo.</span><span class="sxs-lookup"><span data-stu-id="d424d-126">An MDX script defines the calculation process for a cube.</span></span> <span data-ttu-id="d424d-127">Um script MDX também é considerado parte do próprio cubo.</span><span class="sxs-lookup"><span data-stu-id="d424d-127">An MDX script is also considered part of the cube itself.</span></span> <span data-ttu-id="d424d-128">Portanto, alterar um script MDX associado a um cubo altera imediatamente o processo de cálculo do cubo.</span><span class="sxs-lookup"><span data-stu-id="d424d-128">Therefore, changing an MDX script associated with a cube immediately changes the calculation process for the cube.</span></span><br /><br /> <span data-ttu-id="d424d-129">Para criar scripts MDX, você pode usar o Designer de Cubo no [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d424d-129">To create MDX scripts, you can use Cube Designer in the [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d424d-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d424d-130">See Also</span></span>  
 <span data-ttu-id="d424d-131">[Elementos de sintaxe MDX &#40;&#41;MDX](/sql/mdx/mdx-syntax-elements-mdx) </span><span class="sxs-lookup"><span data-stu-id="d424d-131">[MDX Syntax Elements &#40;MDX&#41;](/sql/mdx/mdx-syntax-elements-mdx) </span></span>  
 [<span data-ttu-id="d424d-132">Referência da linguagem MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="d424d-132">MDX Language Reference &#40;MDX&#41;</span></span>](/sql/mdx/mdx-language-reference-mdx)  
  
  