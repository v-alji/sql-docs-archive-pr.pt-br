---
title: Operadores de rollup personalizado em dimensões pai-filho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- child rollup operations
- UnaryOperatorColumn property
- custom rollup operators [Analysis Services]
- unary operators
- parent-child dimensions [Analysis Services]
ms.assetid: a3ddd9fc-5fa3-4227-9322-8c45a5b5c2c3
author: minewiskan
ms.author: owend
ms.openlocfilehash: db12ccc6703ee4863dd3b6bd598d2317b54fce6a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575411"
---
# <a name="custom-rollup-operators-in-parent-child-dimensions"></a><span data-ttu-id="a9e90-102">Operadores de rollup personalizados em dimensões pai-filho</span><span class="sxs-lookup"><span data-stu-id="a9e90-102">Custom Rollup Operators in Parent-Child Dimensions</span></span>
  <span data-ttu-id="a9e90-103">Os operadores de acúmulo personalizado proporcionam uma maneira simples de controlar como os valores dos membros são acumulados nos valores pai em uma hierarquia pai-filho.</span><span class="sxs-lookup"><span data-stu-id="a9e90-103">Custom rollup operators provide a simple way to control how member values are rolled up into parent values in a parent-child hierarchy.</span></span> <span data-ttu-id="a9e90-104">Em uma dimensão que contém uma relação pai-filho, você especifica uma coluna que contém operadores unários que especificam o acúmulo para todos os membros não calculados do atributo pai.</span><span class="sxs-lookup"><span data-stu-id="a9e90-104">In a dimension containing a parent-child relationship, you specify a column that contains unary operators that specify rollup for all noncalculated members of the parent attribute.</span></span> <span data-ttu-id="a9e90-105">O operador unário é aplicado aos membros sempre que os valores dos membros pai são avaliados.</span><span class="sxs-lookup"><span data-stu-id="a9e90-105">The unary operator is applied to members whenever the values of the parent members are evaluated.</span></span>  
  
 <span data-ttu-id="a9e90-106">Os operadores unários são armazenados na coluna definida pela propriedade `UnaryOperatorColumn` do atributo pai e são aplicados a cada membro do atributo.</span><span class="sxs-lookup"><span data-stu-id="a9e90-106">The unary operators are stored in column defined by the `UnaryOperatorColumn` property of the parent attribute, and they are applied to each member of the attribute.</span></span> <span data-ttu-id="a9e90-107">A coluna especificada por essa propriedade pode residir na tabela de dimensões ou em uma tabela relacionada à tabela de dimensões por uma chave estrangeira desta.</span><span class="sxs-lookup"><span data-stu-id="a9e90-107">The column specified by this property can reside either in the dimension table or in a table related to the dimension table by a foreign key in the dimension table.</span></span>  
  
 <span data-ttu-id="a9e90-108">Operadores de acúmulo personalizado oferecem funcionalidades semelhantes às das fórmulas de membro personalizado, porém mais simplificadas.</span><span class="sxs-lookup"><span data-stu-id="a9e90-108">Custom rollup operators provide functionality similar to, but more simplified than, custom member formulas.</span></span> <span data-ttu-id="a9e90-109">Uma fórmula de membro personalizado utiliza expressões multidimensionais (MDX) para determinar como os membros são acumulados.</span><span class="sxs-lookup"><span data-stu-id="a9e90-109">A custom member formula uses Multidimensional Expressions (MDX) expressions to determine how the members are rolled up.</span></span> <span data-ttu-id="a9e90-110">Diferentemente, o operador de acúmulo personalizado emprega um operador unário simples para determinar como o valor de um membro afeta o pai.</span><span class="sxs-lookup"><span data-stu-id="a9e90-110">In contrast, a custom rollup operator uses a simple unary operator to determine how the value of a member affects the parent.</span></span> <span data-ttu-id="a9e90-111">Fórmulas de membro personalizado do nível precedente em uma dimensão prevalecem sobre o operador de acúmulo personalizado do nível.</span><span class="sxs-lookup"><span data-stu-id="a9e90-111">Custom member formulas of the preceding level in a dimension override a level's custom rollup operator.</span></span>  
  
## <a name="custom-rollup-precedence"></a><span data-ttu-id="a9e90-112">Precedência do acúmulo personalizado</span><span class="sxs-lookup"><span data-stu-id="a9e90-112">Custom Rollup Precedence</span></span>  
 <span data-ttu-id="a9e90-113">Em termos de precedência, os operadores de acúmulo personalizado do atributo de origem para um nível da hierarquia prevalecem sobre as fórmulas de membro personalizado do nível anterior.</span><span class="sxs-lookup"><span data-stu-id="a9e90-113">In terms of precedence, the custom rollup operators of the source attribute for a level in a hierarchy override the custom member formulas of the previous level.</span></span> <span data-ttu-id="a9e90-114">No entanto, as fórmulas de membro personalizado do nível precedente prevalecem sobre os operadores de acúmulo personalizado de um nível.</span><span class="sxs-lookup"><span data-stu-id="a9e90-114">However, the custom member formulas of the preceding level override the custom rollup operators of a level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9e90-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a9e90-115">See Also</span></span>  
 <span data-ttu-id="a9e90-116">[Definir fórmulas de membro personalizado](attribute-properties-define-custom-member-formulas.md) </span><span class="sxs-lookup"><span data-stu-id="a9e90-116">[Define Custom Member Formulas](attribute-properties-define-custom-member-formulas.md) </span></span>  
 [<span data-ttu-id="a9e90-117">Operadores unários em dimensões pai-filho</span><span class="sxs-lookup"><span data-stu-id="a9e90-117">Unary Operators in Parent-Child Dimensions</span></span>](parent-child-dimension-attributes-unary-operators.md)  
  
  
