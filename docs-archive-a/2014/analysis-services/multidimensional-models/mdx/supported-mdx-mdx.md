---
title: MDX (MDX) com suporte | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- MDX [Analysis Services], statements
- MDX [Analysis Services], functions
ms.assetid: 308bc0b3-4fd6-4435-972b-5e40d9e3c99b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 17e8df6a2aa6da6b88a07a2abdef99d6ea03d8eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683763"
---
# <a name="supported-mdx-mdx"></a><span data-ttu-id="05947-102">Suporte para MDX (MDX)</span><span class="sxs-lookup"><span data-stu-id="05947-102">Supported MDX (MDX)</span></span>
  <span data-ttu-id="05947-103">As instruções e funções a seguir são suportadas em scripts MDX:</span><span class="sxs-lookup"><span data-stu-id="05947-103">The following statements and functions are supported within Multidimensional Expressions (MDX) Script:</span></span>  
  
 [<span data-ttu-id="05947-104">&#40;Comentário&#41; &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="05947-104">&#40;Comment&#41; &#40;MDX&#41;</span></span>](/sql/mdx/comment-mdx)  
  
 [<span data-ttu-id="05947-105">-- &#40;Comment&#41; &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="05947-105">-- &#40;Comment&#41; &#40;MDX&#41;</span></span>](/sql/mdx/comment-mdx)  
  
 [<span data-ttu-id="05947-106">Comentário &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="05947-106">Comment &#40;MDX&#41;</span></span>](/sql/mdx/comment-mdx)  
  
 [<span data-ttu-id="05947-107">Instrução ALTER CUBE &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="05947-107">ALTER CUBE Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-definition-alter-cube)  
  
> [!NOTE]  
>  <span data-ttu-id="05947-108">Apenas a alteração do membro padrão é suportada pelo script MDX.</span><span class="sxs-lookup"><span data-stu-id="05947-108">Only altering the default member is supported in MDX Scripting.</span></span>  
  
 [<span data-ttu-id="05947-109">Instrução CALCULATE &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="05947-109">CALCULATE Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-scripting-calculate)  
  
 [<span data-ttu-id="05947-110">Instrução CASE &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="05947-110">CASE Statement &#40;MDX&#41;</span></span>](/sql/mdx/case-statement-mdx)  
  
 [<span data-ttu-id="05947-111">Instrução CREATE CELL CALCULATION &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="05947-111">CREATE CELL CALCULATION Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-definition-create-cell-calculation)  
  
 [<span data-ttu-id="05947-112">Instrução CREATE MEMBER &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="05947-112">CREATE MEMBER Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-definition-create-member)  
  
 [<span data-ttu-id="05947-113">Instrução CREATE SET &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="05947-113">CREATE SET Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-definition-create-set)  
  
 [<span data-ttu-id="05947-114">Palavra-chave EXISTING &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="05947-114">EXISTING Keyword &#40;MDX&#41;</span></span>](mdx-query-existing-keyword.md)  
  
 [<span data-ttu-id="05947-115">Instrução FREEZE &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="05947-115">FREEZE Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-scripting-freeze)  
  
 [<span data-ttu-id="05947-116">Instrução IF &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="05947-116">IF Statement  &#40;MDX&#41;</span></span>](/sql/mdx/mdx-scripting-if)  
  
 [<span data-ttu-id="05947-117">Este &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="05947-117">This &#40;MDX&#41;</span></span>](/sql/mdx/this-mdx)  
  
> [!NOTE]  
>  <span data-ttu-id="05947-118">A linguagem MDX oferece suporte a atribuição das seguintes propriedades de célula: `BACK_COLOR`, `FORE_COLOR`, `FORMAT_STRING`, `FONT_FLAGS`, `FONT_NAME` e `FONT_SIZE`.</span><span class="sxs-lookup"><span data-stu-id="05947-118">MDX supports assignment to the following cell properties: `BACK_COLOR`, `FORE_COLOR`, `FORMAT_STRING`, `FONT_FLAGS`, `FONT_NAME`, and `FONT_SIZE`.</span></span> <span data-ttu-id="05947-119">Para obter mais informações, consulte [Como usar propriedades da célula &#40;MDX&#41;](mdx-cell-properties-using-cell-properties.md).</span><span class="sxs-lookup"><span data-stu-id="05947-119">For more information, see [Using Cell Properties &#40;MDX&#41;](mdx-cell-properties-using-cell-properties.md).</span></span> <span data-ttu-id="05947-120">O MDX também dá suporte à atribuição à `NON_EMPTY_BEHAVIOR` propriedade da instrução [Create member](/sql/mdx/mdx-data-definition-create-member) .</span><span class="sxs-lookup"><span data-stu-id="05947-120">MDX also supports assignment to the `NON_EMPTY_BEHAVIOR` property of the [CREATE MEMBER](/sql/mdx/mdx-data-definition-create-member) statement.</span></span>  
  
 [<span data-ttu-id="05947-121">Instrução SCOPE &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="05947-121">SCOPE Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-scripting-scope)  
  
## <a name="see-also"></a><span data-ttu-id="05947-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="05947-122">See Also</span></span>  
 [<span data-ttu-id="05947-123">O script básico de MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="05947-123">The Basic MDX Script &#40;MDX&#41;</span></span>](the-basic-mdx-script-mdx.md)  
  
  
