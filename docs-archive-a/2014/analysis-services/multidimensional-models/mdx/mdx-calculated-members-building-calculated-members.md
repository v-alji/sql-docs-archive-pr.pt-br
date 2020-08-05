---
title: Criando membros calculados em MDX (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- MDX [Analysis Services], calculated members
- calculated members [MDX]
- Multidimensional Expressions [Analysis Services], calculated members
- queries [MDX], calculated members
ms.assetid: 9322e8b8-43e1-4e02-a7d1-e41a586a5bb8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 30dc6562ec394065cf2f177608d4e5679cbd7df3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572738"
---
# <a name="building-calculated-members-in-mdx-mdx"></a><span data-ttu-id="ddad5-102">Criando membros calculados em MDX (MDX)</span><span class="sxs-lookup"><span data-stu-id="ddad5-102">Building Calculated Members in MDX (MDX)</span></span>
  <span data-ttu-id="ddad5-103">Na linguagem MDX, um membro calculado é aquele resolvido pelo cálculo de uma expressão MDX para retornar um valor.</span><span class="sxs-lookup"><span data-stu-id="ddad5-103">In Multidimensional Expressions (MDX), a calculated member is a member that is resolved by calculating an MDX expression to return a value.</span></span> <span data-ttu-id="ddad5-104">Essa simples definição abrange uma quantidade enorme implicações.</span><span class="sxs-lookup"><span data-stu-id="ddad5-104">This innocuous definition covers an incredible amount of ground.</span></span> <span data-ttu-id="ddad5-105">A capacidade de construir e usar membros calculados em uma consulta MDX proporciona uma grande capacidade de manipulação de dados multidimensionais.</span><span class="sxs-lookup"><span data-stu-id="ddad5-105">The ability to construct and use calculated members in an MDX query provides a great deal of manipulation capability for multidimensional data.</span></span>  
  
 <span data-ttu-id="ddad5-106">Você pode criar membros calculados em qualquer ponto de uma hierarquia.</span><span class="sxs-lookup"><span data-stu-id="ddad5-106">You can create calculated members at any point within a hierarchy.</span></span> <span data-ttu-id="ddad5-107">Pode também criar membros calculados que dependem não só dos membros existentes em um cubo, mas também de outros membros calculados definidos na mesma expressão MDX.</span><span class="sxs-lookup"><span data-stu-id="ddad5-107">You can also create calculated members that depend not only on existing members in a cube, but also on other calculated members defined in the same MDX expression.</span></span>  
  
 <span data-ttu-id="ddad5-108">É possível definir um membro calculado para ter um destes contextos:</span><span class="sxs-lookup"><span data-stu-id="ddad5-108">You can define a calculated member to have one of the following contexts:</span></span>  
  
-   <span data-ttu-id="ddad5-109">**Com escopo da consulta** Para criar um membro calculado que seja definido como parte de uma consulta MDX e, portanto, cujo escopo esteja limitado à consulta, use a palavra-chave WITH.</span><span class="sxs-lookup"><span data-stu-id="ddad5-109">**Query-scoped** To create a calculated member that is defined as part of an MDX query, and therefore whose scope is limited to the query, you use the WITH keyword.</span></span> <span data-ttu-id="ddad5-110">Você pode usar o membro calculado em uma instrução MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="ddad5-110">You can then use the calculated member within an MDX SELECT statement.</span></span> <span data-ttu-id="ddad5-111">Usando essa abordagem, o membro calculado criado pelo uso da palavra-chave pode ser alterado sem afetar a instrução SELECT.</span><span class="sxs-lookup"><span data-stu-id="ddad5-111">Using this approach, the calculated member created by using the WITH keyword can be changed without disturbing the SELECT statement.</span></span>  
  
     <span data-ttu-id="ddad5-112">Para obter mais informações sobre como usar a palavra-chave WITH para criar membros calculados, consulte [Criando membros calculados no escopo da consulta &#40;MDX&#41;](mdx-calculated-members-query-scoped-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="ddad5-112">For more information about how to use the WITH keyword to create calculated members, see [Creating Query-Scoped Calculated Members &#40;MDX&#41;](mdx-calculated-members-query-scoped-calculated-members.md).</span></span>  
  
-   <span data-ttu-id="ddad5-113">**Com escopo da sessão** Para criar um membro calculado cujo escopo seja mais amplo que o contexto da consulta, ou seja, cujo escopo seja o tempo de vida da sessão MDX, use a instrução CREATE MEMBER.</span><span class="sxs-lookup"><span data-stu-id="ddad5-113">**Session-scoped** To create a calculated member whose scope is wider than the context of the query, that is, whose scope is the lifetime of the MDX session, you use the CREATE MEMBER statement.</span></span> <span data-ttu-id="ddad5-114">Um membro calculado definido usando-se a instrução CREATE MEMBER fica disponível para todas as consultas MDX dessa sessão.</span><span class="sxs-lookup"><span data-stu-id="ddad5-114">A calculated member defined by using the CREATE MEMBER statement is available to all MDX queries in that session.</span></span> <span data-ttu-id="ddad5-115">A instrução CREATE MEMBER faz sentido, por exemplo, em um aplicativo cliente que reutiliza consistentemente o mesmo conjunto em diversas consultas.</span><span class="sxs-lookup"><span data-stu-id="ddad5-115">The CREATE MEMBER statement makes sense, for example, in a client application that consistently reuses the same set in a variety of queries.</span></span>  
  
     <span data-ttu-id="ddad5-116">Para obter mais informações sobre como usar a instrução CREATE MEMBER para criar membros calculados em uma sessão, consulte [Criando membros calculados no escopo da sessão &#40;MDX&#41;](mdx-calculated-members-session-scoped-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="ddad5-116">For more information about how to use the CREATE MEMBER statement to create calculated members in a session, see [Creating Session-Scoped Calculated Members &#40;MDX&#41;](mdx-calculated-members-session-scoped-calculated-members.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddad5-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ddad5-117">See Also</span></span>  
 <span data-ttu-id="ddad5-118">[Instrução CREATE MEMBER &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) </span><span class="sxs-lookup"><span data-stu-id="ddad5-118">[CREATE MEMBER Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) </span></span>  
 <span data-ttu-id="ddad5-119">[Referência de função MDX &#40;&#41;MDX](/sql/mdx/mdx-function-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="ddad5-119">[MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx) </span></span>  
 [<span data-ttu-id="ddad5-120">Instrução SELECT &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="ddad5-120">SELECT Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-manipulation-select)  
  
  
