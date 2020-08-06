---
title: Criando conjuntos nomeados em MDX (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Multidimensional Expressions [Analysis Services], named sets
- named sets [MDX]
- sets [MDX]
- MDX [Analysis Services], named sets
- queries [MDX], named sets
- set expressions [MDX]
ms.assetid: 213b0035-e96d-4ba0-83f2-ded206905603
author: minewiskan
ms.author: owend
ms.openlocfilehash: 91296f8c5d47afb15c67f0b60435c7f961734573
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680102"
---
# <a name="building-named-sets-in-mdx-mdx"></a><span data-ttu-id="b9888-102">Criando conjuntos nomeados em MDX (MDX)</span><span class="sxs-lookup"><span data-stu-id="b9888-102">Building Named Sets in MDX (MDX)</span></span>
  <span data-ttu-id="b9888-103">Uma expressão de conjunto pode ser uma declaração longa e complexa e, portanto, difícil de seguir ou entender.</span><span class="sxs-lookup"><span data-stu-id="b9888-103">A set expression can be a lengthy and complex declaration, and therefore be difficult to follow or understand.</span></span> <span data-ttu-id="b9888-104">Ou ainda, a expressão de conjunto pode ser usada com tanta frequência que sua definição repetidamente passa a ser penosa.</span><span class="sxs-lookup"><span data-stu-id="b9888-104">Or, a set expression may be used so frequently that repeatedly defining the set becomes burdensome.</span></span> <span data-ttu-id="b9888-105">Para ajudar a facilitar o trabalho com expressões longas, complexas e geralmente usadas, as expressões MDX permitem que você trabalhe nelas como um *conjunto nomeado*.</span><span class="sxs-lookup"><span data-stu-id="b9888-105">To help make working with a lengthy, complex or commonly used expression easier, Multidimensional Expressions (MDX) lets you such an expression as a *named set*.</span></span>  
  
 <span data-ttu-id="b9888-106">Basicamente, um conjunto nomeado é uma expressão de conjunto para a qual um alias foi atribuído.</span><span class="sxs-lookup"><span data-stu-id="b9888-106">Basically, a named set is a set expression to which an alias has been assigned.</span></span> <span data-ttu-id="b9888-107">Um conjunto nomeado pode incorporar todos os membros ou funções que normalmente podem ser incorporados a um conjunto.</span><span class="sxs-lookup"><span data-stu-id="b9888-107">A named set can incorporate any members or functions that can ordinarily be incorporated into a set.</span></span> <span data-ttu-id="b9888-108">Como a linguagem MDX trata o conjunto nomeado como uma expressão de conjunto, é possível usar esse alias em qualquer lugar que aceite uma expressão de conjunto.</span><span class="sxs-lookup"><span data-stu-id="b9888-108">Because MDX treats the named set alias as a set expression, you can use that alias anywhere a set expression is accepted.</span></span>  
  
 <span data-ttu-id="b9888-109">Você pode definir um conjunto nomeado para ter um destes contextos:</span><span class="sxs-lookup"><span data-stu-id="b9888-109">You can define a named set to have one of the following contexts:</span></span>  
  
-   <span data-ttu-id="b9888-110">**No escopo da consulta** Para criar um conjunto nomeado que seja definido como parte de uma consulta MDX e, portanto, cujo escopo esteja limitado à consulta, use a palavra-chave WITH.</span><span class="sxs-lookup"><span data-stu-id="b9888-110">**Query-scoped** To create a named set that is defined as part of an MDX query, and therefore whose scope is limited to the query, you use the WITH keyword.</span></span> <span data-ttu-id="b9888-111">Em seguida, você pode usar o conjunto nomeado em uma instrução MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="b9888-111">You can then use the named set within an MDX SELECT statement.</span></span> <span data-ttu-id="b9888-112">Usando essa abordagem, o conjunto nomeado criado pelo uso da palavra-chave pode ser alterado sem afetar a instrução SELECT.</span><span class="sxs-lookup"><span data-stu-id="b9888-112">Using this approach, the named set created by using the WITH keyword can be changed without disturbing the SELECT statement.</span></span>  
  
     <span data-ttu-id="b9888-113">Para obter mais informações sobre como usar a palavra-chave WITH para criar conjuntos nomeados, consulte [Criando conjuntos nomeados no escopo da consulta &#40;MDX&#41;](mdx-named-sets-creating-query-scoped-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="b9888-113">For more information about how to use the WITH keyword to create named sets, see [Creating Query-Scoped Named Sets &#40;MDX&#41;](mdx-named-sets-creating-query-scoped-named-sets.md).</span></span>  
  
-   <span data-ttu-id="b9888-114">**No escopo da sessão** Para criar um conjunto nomeado cujo escopo seja mais amplo que o contexto da consulta, ou seja, cujo escopo seja o tempo de vida da sessão de MDX, use a instrução CREATE SET.</span><span class="sxs-lookup"><span data-stu-id="b9888-114">**Session-scoped** To create a named set whose scope is wider than the context of the query, that is, whose scope is the lifetime of the MDX session, you use the CREATE SET statement.</span></span> <span data-ttu-id="b9888-115">Um conjunto nomeado definido pela instrução CREATE SET estará disponível para todas as consultas MDX dessa sessão.</span><span class="sxs-lookup"><span data-stu-id="b9888-115">A named set defined by using the CREATE SET statement is available to all MDX queries in that session.</span></span> <span data-ttu-id="b9888-116">A instrução CREATE SET faz sentido, por exemplo, em um aplicativo cliente que reutiliza consistentemente um conjunto em diversas consultas.</span><span class="sxs-lookup"><span data-stu-id="b9888-116">The CREATE SET statement makes sense, for example, in a client application that consistently reuses a set in a variety of queries.</span></span>  
  
     <span data-ttu-id="b9888-117">Para obter mais informações sobre como usar a instrução CREATE SET para criar conjuntos nomeados em uma sessão, consulte [Criando conjuntos nomeados no escopo da sessão &#40;MDX&#41;](mdx-named-sets-creating-session-scoped-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="b9888-117">For more information about how to use the CREATE SET statement to create named sets in a session, see [Creating Session-Scoped Named Sets &#40;MDX&#41;](mdx-named-sets-creating-session-scoped-named-sets.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9888-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b9888-118">See Also</span></span>  
 <span data-ttu-id="b9888-119">[Instrução SELECT &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select) </span><span class="sxs-lookup"><span data-stu-id="b9888-119">[SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select) </span></span>  
 <span data-ttu-id="b9888-120">[Instrução CREATE SET &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-set) </span><span class="sxs-lookup"><span data-stu-id="b9888-120">[CREATE SET Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-set) </span></span>  
 [<span data-ttu-id="b9888-121">Conceitos básicos de consulta MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b9888-121">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
