---
title: Palavra-chave EXISTing (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- EXISTING
helpviewer_keywords:
- Existing keyword
ms.assetid: 651ee9ac-04ef-4316-87c9-a3df5ac27d22
author: minewiskan
ms.author: owend
ms.openlocfilehash: 115444c832fe8fe9b258a0c23b97b97553f32e8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569689"
---
# <a name="existing-keyword-mdx"></a><span data-ttu-id="c217f-102">Palavra-chave EXISTING (MDX)</span><span class="sxs-lookup"><span data-stu-id="c217f-102">EXISTING Keyword (MDX)</span></span>
  <span data-ttu-id="c217f-103">Força a avaliação de um conjunto especificado no contexto atual.</span><span class="sxs-lookup"><span data-stu-id="c217f-103">Forces a specified set to be evaluated within the current context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c217f-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c217f-104">Syntax</span></span>  
  
```  
  
Existing Set_Expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="c217f-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c217f-105">Arguments</span></span>  
 <span data-ttu-id="c217f-106">*Set_Expression*</span><span class="sxs-lookup"><span data-stu-id="c217f-106">*Set_Expression*</span></span>  
 <span data-ttu-id="c217f-107">Uma expressão de conjunto de expressões multidimensionais (MDX) válida.</span><span class="sxs-lookup"><span data-stu-id="c217f-107">A valid Multidimensional Expressions (MDX) set expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c217f-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="c217f-108">Remarks</span></span>  
 <span data-ttu-id="c217f-109">Por padrão, são avaliados conjuntos no contexto do cubo que contém os membros do conjunto.</span><span class="sxs-lookup"><span data-stu-id="c217f-109">By default, sets are evaluated within the context of the cube that contains the members of the set.</span></span> <span data-ttu-id="c217f-110">A palavra-chave `Existing` força a avaliação de um conjunto especificado no contexto atual.</span><span class="sxs-lookup"><span data-stu-id="c217f-110">The `Existing` keyword forces a specified set to be evaluated within the current context instead.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c217f-111">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c217f-111">Example</span></span>  
 <span data-ttu-id="c217f-112">O exemplo a seguir retorna a contagem dos revendedores cujas vendas caíram ao longo do período anterior, com base em valores de Estado do membro, selecionados pelo usuário, avaliados usando a função `Aggregate`.</span><span class="sxs-lookup"><span data-stu-id="c217f-112">The following example returns the count of the resellers whose sales have declined over the previous time period, based on user-selected State-Province member values evaluated using the `Aggregate` function.</span></span> <span data-ttu-id="c217f-113">A palavra-chave [Hierarchize &#40;MDX&#41;](/sql/mdx/hierarchize-mdx) e [DrilldownLevel (MDX)](/sql/mdx/drilldownlevel-mdx) são usadas para retornar valores por queda de vendas por categorias de produto na dimensão Produto.</span><span class="sxs-lookup"><span data-stu-id="c217f-113">The [Hierarchize &#40;MDX&#41;](/sql/mdx/hierarchize-mdx) and [DrilldownLevel (MDX)](/sql/mdx/drilldownlevel-mdx) functions are used to return values for declining sales for product categories in the Product dimension.</span></span> <span data-ttu-id="c217f-114">A `Existing` palavra-chave força o conjunto na `Filter` função a ser avaliada no contexto atual, ou seja, para os membros Washington e Oregon da hierarquia de atributo State-província.</span><span class="sxs-lookup"><span data-stu-id="c217f-114">The `Existing` keyword forces the set in the `Filter` function to be evaluated in the current context - that is, for the Washington and Oregon members of the State-Province attribute hierarchy.</span></span>  
  
```  
WITH MEMBER Measures.[Declining Reseller Sales] AS  
   Count  
      (Filter  
         (Existing  
            (Reseller.Reseller.Reseller)  
         , [Measures].[Reseller Sales Amount] <   
            ([Measures].[Reseller Sales Amount]  
               ,[Date].Calendar.PrevMember  
            )  
        )  
      )  
MEMBER [Geography].[State-Province].x AS   
   Aggregate   
      ( {[Geography].[State-Province].&[WA]&[US]  
         , [Geography].[State-Province].&[OR]&[US] }   
      )  
SELECT NON EMPTY HIERARCHIZE   
      (AddCalculatedMembers   
         (   
            {DrillDownLevel  
               ({[Product].[All Products]}  
               )  
            }   
         )   
      ) DIMENSION PROPERTIES PARENT_UNIQUE_NAME ON COLUMNS   
FROM [Adventure Works]  
WHERE   
      ( [Geography].[State-Province].x  
        , [Date].[Calendar].[Calendar Quarter].&[2003]&[4]  
        ,[Measures].[Declining Reseller Sales]  
      )  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="c217f-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c217f-115">See Also</span></span>  
 <span data-ttu-id="c217f-116">[Contagem &#40;definida&#41; &#40;MDX&#41;](/sql/mdx/count-set-mdx) </span><span class="sxs-lookup"><span data-stu-id="c217f-116">[Count &#40;Set&#41; &#40;MDX&#41;](/sql/mdx/count-set-mdx) </span></span>  
 <span data-ttu-id="c217f-117">[AddCalculatedMembers&#41;MDX &#40;](/sql/mdx/addcalculatedmembers-mdx) </span><span class="sxs-lookup"><span data-stu-id="c217f-117">[AddCalculatedMembers &#40;MDX&#41;](/sql/mdx/addcalculatedmembers-mdx) </span></span>  
 <span data-ttu-id="c217f-118">[&#41;&#40;MDX de agregação](/sql/mdx/aggregate-mdx) </span><span class="sxs-lookup"><span data-stu-id="c217f-118">[Aggregate &#40;MDX&#41;](/sql/mdx/aggregate-mdx) </span></span>  
 <span data-ttu-id="c217f-119">[Filtrar &#40;&#41;MDX](/sql/mdx/filter-mdx) </span><span class="sxs-lookup"><span data-stu-id="c217f-119">[Filter &#40;MDX&#41;](/sql/mdx/filter-mdx) </span></span>  
 <span data-ttu-id="c217f-120">[Propriedades &#40;MDX&#41;](/sql/mdx/properties-mdx) </span><span class="sxs-lookup"><span data-stu-id="c217f-120">[Properties &#40;MDX&#41;](/sql/mdx/properties-mdx) </span></span>  
 <span data-ttu-id="c217f-121">[DrilldownLevel&#41;MDX &#40;](/sql/mdx/drilldownlevel-mdx) </span><span class="sxs-lookup"><span data-stu-id="c217f-121">[DrilldownLevel &#40;MDX&#41;](/sql/mdx/drilldownlevel-mdx) </span></span>  
 <span data-ttu-id="c217f-122">[Hierarquiar &#40;&#41;MDX](/sql/mdx/hierarchize-mdx) </span><span class="sxs-lookup"><span data-stu-id="c217f-122">[Hierarchize &#40;MDX&#41;](/sql/mdx/hierarchize-mdx) </span></span>  
 [<span data-ttu-id="c217f-123">Referência da Função MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="c217f-123">MDX Function Reference &#40;MDX&#41;</span></span>](/sql/mdx/mdx-function-reference-mdx)  
  
  
