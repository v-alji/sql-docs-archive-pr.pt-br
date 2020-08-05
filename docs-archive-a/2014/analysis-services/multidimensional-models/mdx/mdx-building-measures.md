---
title: Criando medidas em MDX | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f0347835-4983-4d26-acbb-6c8fae7992bd
author: minewiskan
ms.author: owend
ms.openlocfilehash: ac49d37f11584bfbc5d372241056da39e7dd8c93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572744"
---
# <a name="building-measures-in-mdx"></a><span data-ttu-id="a80fa-102">Compilando medidas em MDX</span><span class="sxs-lookup"><span data-stu-id="a80fa-102">Building Measures in MDX</span></span>
  <span data-ttu-id="a80fa-103">Nas expressões MDX, uma medida é uma expressão DAX nomeada que é resolvida pelo cálculo da expressão para retornar um valor em um Modelo de Tabela.</span><span class="sxs-lookup"><span data-stu-id="a80fa-103">In Multidimensional Expressions (MDX), a measure is a named DAX expression that is resolved by calculating the expression to return a value in a Tabular Model.</span></span> <span data-ttu-id="a80fa-104">Essa simples definição abrange uma quantidade enorme implicações.</span><span class="sxs-lookup"><span data-stu-id="a80fa-104">This innocuous definition covers an incredible amount of ground.</span></span> <span data-ttu-id="a80fa-105">A capacidade de construir e usar medidas em uma consulta MDX proporciona uma grande capacidade de manipulação de dados de tabela.</span><span class="sxs-lookup"><span data-stu-id="a80fa-105">The ability to construct and use measures in an MDX query provides a great deal of manipulation capability for tabular data.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="a80fa-106">As medidas podem ser definidas apenas em modelos de tabela; se o seu banco de dados estiver definido no modo multidimensional, a criação de uma medida gerará um erro</span><span class="sxs-lookup"><span data-stu-id="a80fa-106">Measures can only be defined in tabular models; if your database is set in multidimensional mode, creating a measure will generate an error</span></span>  
  
 <span data-ttu-id="a80fa-107">Para criar uma medida que seja definida como parte de uma consulta MDX e, portanto, cujo escopo esteja limitado à consulta, use a palavra-chave WITH.</span><span class="sxs-lookup"><span data-stu-id="a80fa-107">To create a measure that is defined as part of an MDX query, and therefore whose scope is limited to the query, you use the WITH keyword.</span></span> <span data-ttu-id="a80fa-108">Em seguida, você pode usar a medida em uma instrução MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="a80fa-108">You can then use the measure within an MDX SELECT statement.</span></span> <span data-ttu-id="a80fa-109">Usando essa abordagem, o membro calculado criado pelo uso da palavra-chave pode ser alterado sem afetar a instrução SELECT.</span><span class="sxs-lookup"><span data-stu-id="a80fa-109">Using this approach, the calculated member created by using the WITH keyword can be changed without disturbing the SELECT statement.</span></span> <span data-ttu-id="a80fa-110">No entanto, em MDX você referencia a medida de uma forma diferente da adotada nas expressões DAX; para referenciar a medida você a denomina como membro da dimensão [Measures], consulte o seguinte exemplo de MDX:</span><span class="sxs-lookup"><span data-stu-id="a80fa-110">However, in MDX you reference the measure in a different way than when in DAX expressions; to reference the measure you name it as a member of the [Measures] dimension, see the following MDX example:</span></span>  
  
```  
with measure  'Sales Territory'[Total Sales Amount] = SUM('Internet Sales'[Sales Amount]) + SUM('Reseller Sales'[Sales Amount])  
select measures.[Total Sales Amount] on columns  
     ,NON EMPTY [Date].[Calendar Year].children on rows  
from [Model]  
  
```  
  
 <span data-ttu-id="a80fa-111">Isso retornará os dados seguintes quando executado:</span><span class="sxs-lookup"><span data-stu-id="a80fa-111">It will return the following data when executed:</span></span>  
  
||<span data-ttu-id="a80fa-112">Total Sales Amount</span><span class="sxs-lookup"><span data-stu-id="a80fa-112">Total Sales Amount</span></span>||  
|-|------------------------|-|  
|<span data-ttu-id="a80fa-113">2001</span><span class="sxs-lookup"><span data-stu-id="a80fa-113">2001</span></span>|<span data-ttu-id="a80fa-114">11331808.96</span><span class="sxs-lookup"><span data-stu-id="a80fa-114">11331808.96</span></span>||  
|<span data-ttu-id="a80fa-115">2002</span><span class="sxs-lookup"><span data-stu-id="a80fa-115">2002</span></span>|<span data-ttu-id="a80fa-116">30674773.18</span><span class="sxs-lookup"><span data-stu-id="a80fa-116">30674773.18</span></span>||  
|<span data-ttu-id="a80fa-117">2003</span><span class="sxs-lookup"><span data-stu-id="a80fa-117">2003</span></span>|<span data-ttu-id="a80fa-118">41993729.72</span><span class="sxs-lookup"><span data-stu-id="a80fa-118">41993729.72</span></span>||  
|<span data-ttu-id="a80fa-119">2004</span><span class="sxs-lookup"><span data-stu-id="a80fa-119">2004</span></span>|<span data-ttu-id="a80fa-120">25808962.34</span><span class="sxs-lookup"><span data-stu-id="a80fa-120">25808962.34</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="a80fa-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a80fa-121">See Also</span></span>  
 <span data-ttu-id="a80fa-122">[Instrução CREATE MEMBER &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) </span><span class="sxs-lookup"><span data-stu-id="a80fa-122">[CREATE MEMBER Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) </span></span>  
 <span data-ttu-id="a80fa-123">[Referência de função MDX &#40;&#41;MDX](/sql/mdx/mdx-function-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="a80fa-123">[MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx) </span></span>  
 [<span data-ttu-id="a80fa-124">Instrução SELECT &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="a80fa-124">SELECT Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-manipulation-select)  
  
  
