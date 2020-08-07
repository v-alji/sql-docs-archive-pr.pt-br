---
title: Criando membros calculados no escopo da sessão (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- CREATE MEMBER statement
- session-scoped calculated members [MDX]
ms.assetid: 2875ed89-2c26-4645-8ed9-8848479d110f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8fe7a9f137d8b74eaa5bad104dbfdb471dd14588
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581563"
---
# <a name="creating-session-scoped-calculated-members-mdx"></a><span data-ttu-id="5fb19-102">Criando membros calculados no escopo da sessão (MDX)</span><span class="sxs-lookup"><span data-stu-id="5fb19-102">Creating Session-Scoped Calculated Members (MDX)</span></span>
  <span data-ttu-id="5fb19-103">Para criar um membro calculado disponível por meio de uma sessão de expressões MDX, use a instrução [CREATE MEMBER](/sql/mdx/mdx-data-definition-create-member) .</span><span class="sxs-lookup"><span data-stu-id="5fb19-103">To create a calculated member that is available throughout a Multidimensional Expressions (MDX) session, you use the [CREATE MEMBER](/sql/mdx/mdx-data-definition-create-member) statement.</span></span> <span data-ttu-id="5fb19-104">Um membro calculado criado com a instrução CREATE MEMBER não será removido até que a sessão MDX seja encerrada.</span><span class="sxs-lookup"><span data-stu-id="5fb19-104">A calculated member that is created by using the CREATE MEMBER statement will not be removed until after the MDX session closes.</span></span>  
  
 <span data-ttu-id="5fb19-105">Como discutido neste tópico, a sintaxe da instrução CREATE MEMBER é direta e fácil usar.</span><span class="sxs-lookup"><span data-stu-id="5fb19-105">As discussed in this topic, the syntax of the CREATE MEMBER statement is straightforward and easy to use.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5fb19-106">Para obter mais informações sobre membros calculados, consulte [Criando membros calculados no MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="5fb19-106">For more information about calculated members, see [Building Calculated Members in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span></span>  
  
## <a name="create-member-syntax"></a><span data-ttu-id="5fb19-107">Sintaxe de CREATE MEMBER</span><span class="sxs-lookup"><span data-stu-id="5fb19-107">CREATE MEMBER Syntax</span></span>  
 <span data-ttu-id="5fb19-108">Use a sintaxe a seguir para adicionar a instrução CREATE MEMBER à instrução MDX:</span><span class="sxs-lookup"><span data-stu-id="5fb19-108">Use the following syntax to add the CREATE MEMBER statement to the MDX statement:</span></span>  
  
```  
CREATE [SESSION] MEMBER [<cube-name>.]<fully-qualified-member-name> AS <expression> [,<property-definition-list>]  
<cube name> ::= CURRENTCUBE | <Cube Name>  
<property-definition-list> ::= <property-definition>  
  | <property-definition>, <property-definition-list>  
<property-definition> ::= <property-identifier> = <property-value>  
<property-identifier> ::= VISIBLE | SOLVEORDER | SOLVE_ORDER | FORMAT_STRING | NON_EMPTY_BEHAVIOR <ole db member properties>  
```  
  
 <span data-ttu-id="5fb19-109">Na sintaxe da instrução CREATE MEMBER, o valor `fully-qualified-member-name` é o nome totalmente qualificado do membro calculado.</span><span class="sxs-lookup"><span data-stu-id="5fb19-109">In the syntax for the CREATE MEMBER statement, the `fully-qualified-member-name` value is the fully qualified name of the calculated member.</span></span> <span data-ttu-id="5fb19-110">O nome totalmente qualificado inclui a dimensão ou o nível a que o membro calculado está associado.</span><span class="sxs-lookup"><span data-stu-id="5fb19-110">The fully qualified name includes the dimension or level to which the calculated member is associated.</span></span> <span data-ttu-id="5fb19-111">O valor `expression` retorna o valor do membro calculado depois que o valor de expressão foi avaliado.</span><span class="sxs-lookup"><span data-stu-id="5fb19-111">The `expression` value returns the value of the calculated member after the expression value has been evaluated,.</span></span>  
  
## <a name="create-member-example"></a><span data-ttu-id="5fb19-112">Exemplo de CREATE MEMBER</span><span class="sxs-lookup"><span data-stu-id="5fb19-112">CREATE MEMBER Example</span></span>  
 <span data-ttu-id="5fb19-113">O exemplo a seguir usa a instrução CREATE MEMBER para criar o membro calculado `LastFourStores` .</span><span class="sxs-lookup"><span data-stu-id="5fb19-113">The following example uses the CREATE MEMBER statement to create the `LastFourStores` calculated member.</span></span> <span data-ttu-id="5fb19-114">Esse membro calculado retorna a soma de unidades vendidas nas últimas quatro lojas e estará disponível durante toda a sessão do cubo.</span><span class="sxs-lookup"><span data-stu-id="5fb19-114">This calculated member returns the sum of units sold for the last four stores, and will be available throughout the whole session of the cube.</span></span>  
  
```  
Create Session Member [Store].[Measures].LastFourStores as   
sum(([Stores].[ByLocation].Lag(3) :  
[Stores].[ByLocation].NextMember), [Measures].[Units Sold])  
```  
  
## <a name="see-also"></a><span data-ttu-id="5fb19-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5fb19-115">See Also</span></span>  
 [<span data-ttu-id="5fb19-116">Criando membros calculados no escopo da consulta &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="5fb19-116">Creating Query-Scoped Calculated Members &#40;MDX&#41;</span></span>](mdx-calculated-members-query-scoped-calculated-members.md)  
  
  
