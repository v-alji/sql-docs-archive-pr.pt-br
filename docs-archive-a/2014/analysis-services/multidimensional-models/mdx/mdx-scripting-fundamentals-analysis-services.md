---
title: Conceitos básicos de script MDX (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- cubes [Analysis Services], scripts
- calculations [Analysis Services], scripts
- MDX [Analysis Services], scripts
- scripts [MDX]
- cubes [Analysis Services], calculations
- Multidimensional Expressions [Analysis Services], scripts
ms.assetid: fdecb3ce-7c87-4bab-8000-532ba7a29f96
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2f7638339d8fc366ee384d453f6df683f3bd41f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581558"
---
# <a name="mdx-scripting-fundamentals-analysis-services"></a><span data-ttu-id="85260-102">Conceitos básicos de geração de scripts MDX (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="85260-102">MDX Scripting Fundamentals (Analysis Services)</span></span>
  <span data-ttu-id="85260-103">No [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], um script MDX é composto de uma ou mais linguagens ou instruções MDX que populam um cubo com cálculos.</span><span class="sxs-lookup"><span data-stu-id="85260-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], a Multidimensional Expressions (MDX) script is made up of one or more MDX expressions or statements that populate a cube with calculations.</span></span>  
  
 <span data-ttu-id="85260-104">Um script MDX define o processo de cálculo de um cubo.</span><span class="sxs-lookup"><span data-stu-id="85260-104">An MDX script defines the calculation process for a cube.</span></span> <span data-ttu-id="85260-105">Um script MDX também é considerado parte do próprio cubo.</span><span class="sxs-lookup"><span data-stu-id="85260-105">An MDX script is also considered part of the cube itself.</span></span> <span data-ttu-id="85260-106">Portanto, alterar um script MDX associado a um cubo altera imediatamente o processo de cálculo do cubo.</span><span class="sxs-lookup"><span data-stu-id="85260-106">Therefore, changing an MDX script associated with a cube immediately changes the calculation process for the cube.</span></span>  
  
 <span data-ttu-id="85260-107">Para criar scripts MDX, você pode usar o Designer de Cubo no [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85260-107">To create MDX scripts, you can use Cube Designer in the [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="85260-108">Para obter mais informações, consulte [Definir atribuições e outros comandos de script](../define-assignments-and-other-script-commands.md) e [Introdução ao script MDX no Microsoft SQL Server 2005](https://go.microsoft.com/fwlink/?LinkId=81892).</span><span class="sxs-lookup"><span data-stu-id="85260-108">For more information, see [Define Assignments and Other Script Commands](../define-assignments-and-other-script-commands.md) and [Introduction to MDX Scripting in Microsoft SQL Server 2005](https://go.microsoft.com/fwlink/?LinkId=81892).</span></span>  
  
 <span data-ttu-id="85260-109">Para questões de desempenho relacionadas a cálculos e consultas MDX, consulte a seção de otimização de MDX no [Guia de Desempenho do SQL Server Analysis Services](https://go.microsoft.com/fwlink/p/?LinkId=399050).</span><span class="sxs-lookup"><span data-stu-id="85260-109">For performance issues related to MDX queries and calculations, see the MDX optimization section in the [SQL Server Analysis Services Performance Guide](https://go.microsoft.com/fwlink/p/?LinkId=399050).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="85260-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="85260-110">In This Section</span></span>  
  
|<span data-ttu-id="85260-111">Tópico</span><span class="sxs-lookup"><span data-stu-id="85260-111">Topic</span></span>|<span data-ttu-id="85260-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="85260-112">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="85260-113">O script básico de MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="85260-113">The Basic MDX Script &#40;MDX&#41;</span></span>](the-basic-mdx-script-mdx.md)|<span data-ttu-id="85260-114">Detalhes sobre o script MDX básico, inclusive o script MDX padrão fornecido em cada cubo, e como os scripts MDX geralmente funcionam dentro de um cubo no [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85260-114">Details the basic MDX script, including the default MDX script provided in each cube, and how MDX scripts generally function within a cube in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="85260-115">Gerenciando escopo e contexto &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="85260-115">Managing Scope and Context &#40;MDX&#41;</span></span>](managing-scope-and-context-mdx.md)|<span data-ttu-id="85260-116">Descreve como usar a instrução [CALCULATE](/sql/mdx/mdx-scripting-calculate) , a instrução [SCOPE](/sql/mdx/mdx-scripting-scope) e a função [This](/sql/mdx/this-mdx) para gerenciar contexto e escopo dentro de um script MDX.</span><span class="sxs-lookup"><span data-stu-id="85260-116">Describes how to use the [CALCULATE](/sql/mdx/mdx-scripting-calculate) statement, the [SCOPE](/sql/mdx/mdx-scripting-scope) statement, and the [This](/sql/mdx/this-mdx) function to manage context and scope within an MDX script.</span></span>|  
|[<span data-ttu-id="85260-117">Usando variáveis e parâmetros &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="85260-117">Using Variables and Parameters &#40;MDX&#41;</span></span>](using-variables-and-parameters-mdx.md)|<span data-ttu-id="85260-118">Descreve como utilizar variáveis e parâmetros em um script MDX.</span><span class="sxs-lookup"><span data-stu-id="85260-118">Describes how to use variables and parameters in an MDX script.</span></span>|  
|[<span data-ttu-id="85260-119">Tratamento de erro &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="85260-119">Error Handling &#40;MDX&#41;</span></span>](error-handling-mdx.md)|<span data-ttu-id="85260-120">Explica a manipulação de erros dentro de um script MDX.</span><span class="sxs-lookup"><span data-stu-id="85260-120">Explains error handling within an MDX script.</span></span>|  
|[<span data-ttu-id="85260-121">MDX com suporte &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="85260-121">Supported MDX &#40;MDX&#41;</span></span>](supported-mdx-mdx.md)|<span data-ttu-id="85260-122">Fornece uma lista de operadores, instruções e funções MDX suportadas em um script MDX.</span><span class="sxs-lookup"><span data-stu-id="85260-122">Provides a list of supported MDX operators, statements, and functions within an MDX script.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="85260-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="85260-123">See Also</span></span>  
 [<span data-ttu-id="85260-124">Referência da linguagem MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="85260-124">MDX Language Reference &#40;MDX&#41;</span></span>](/sql/mdx/mdx-language-reference-mdx)  
  
  
