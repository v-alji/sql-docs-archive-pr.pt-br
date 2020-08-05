---
title: Criando membros calculados no escopo da consulta (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- WITH keyword
- query-scoped calculated members [MDX]
ms.assetid: c4507149-e67b-4e5d-9192-cc911acd9adc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9c0b3e7184f3cc6abd189344bbce1b6e1f948ebb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572742"
---
# <a name="creating-query-scoped-calculated-members-mdx"></a><span data-ttu-id="33c4a-102">Criando membros calculados no escopo da consulta (MDX)</span><span class="sxs-lookup"><span data-stu-id="33c4a-102">Creating Query-Scoped Calculated Members (MDX)</span></span>
  <span data-ttu-id="33c4a-103">Se um membro calculado for necessário para uma única consulta de expressões multidimensionais (MDX), é possível defini-lo usando a palavra-chave WITH.</span><span class="sxs-lookup"><span data-stu-id="33c4a-103">If a calculated member is only required for a single Multidimensional Expressions (MDX) query, you can define that calculated member by using the WITH keyword.</span></span> <span data-ttu-id="33c4a-104">O membro calculado criado com a palavra-chave WITH deixará de existir ao fim da execução da consulta.</span><span class="sxs-lookup"><span data-stu-id="33c4a-104">A calculated member that is created by using the WITH keyword no longer exists after the query has finished running.</span></span>  
  
 <span data-ttu-id="33c4a-105">Como discutido neste tópico, a sintaxe da palavra-chave WITH é bem flexível, permitindo até que um membro calculado baseie-se em outro membro calculado.</span><span class="sxs-lookup"><span data-stu-id="33c4a-105">As discussed in this topic, the syntax of the WITH keyword is quite flexible, even allowing a calculated member to be based on another calculated member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="33c4a-106">Para obter mais informações sobre membros calculados, consulte [Criando membros calculados no MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="33c4a-106">For more information about calculated members, see [Building Calculated Members in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span></span>  
  
## <a name="with-keyword-syntax"></a><span data-ttu-id="33c4a-107">Sintaxe da palavra-chave WITH</span><span class="sxs-lookup"><span data-stu-id="33c4a-107">WITH Keyword Syntax</span></span>  
 <span data-ttu-id="33c4a-108">Use a sintaxe a seguir para adicionar a palavra-chave WITH a uma instrução MDX SELECT:</span><span class="sxs-lookup"><span data-stu-id="33c4a-108">Use the following syntax to add the WITH keyword to an MDX SELECT statement:</span></span>  
  
```  
[ WITH <SELECT WITH clause> [ , <SELECT WITH clause> ... ] ] SELECT [ * | ( <SELECT query axis clause> [ , <SELECT query axis clause> ... ] ) ]FROM <SELECT subcube clause> [ <SELECT slicer axis clause> ][ <SELECT cell property list clause> ]  
<SELECT WITH clause> ::=  
   ( [ CALCULATED ] MEMBER <CREATE MEMBER body clause>) | <CREATE MEMBER body clause> ::= Member_Identifier AS 'MDX_Expression'  
   [ <CREATE MEMBER property clause> [ , <CREATE MEMBER property clause> ... ] ]  
<CREATE MEMBER property clause> ::=  
   ( MemberProperty_Identifier = Scalar_Expression )  
  
```  
  
 <span data-ttu-id="33c4a-109">Na sintaxe da palavra-chave WITH, o valor `Member_Identifier` é o nome totalmente qualificado do membro calculado.</span><span class="sxs-lookup"><span data-stu-id="33c4a-109">In the syntax for the WITH keyword, the `Member_Identifier` value is the fully qualified name of the calculated member.</span></span> <span data-ttu-id="33c4a-110">Esse nome totalmente qualificado inclui a dimensão ou o nível a que o membro calculado está associado.</span><span class="sxs-lookup"><span data-stu-id="33c4a-110">This fully qualified name includes the dimension or level to which the calculated member is associated.</span></span> <span data-ttu-id="33c4a-111">O valor `MDX_Expression` retorna o valor do membro calculado depois que o valor de expressão foi avaliado.</span><span class="sxs-lookup"><span data-stu-id="33c4a-111">The `MDX_Expression` value returns the value of the calculated member after the expression value has been evaluated.</span></span> <span data-ttu-id="33c4a-112">Opcionalmente, os valores de propriedades de células intrínsecas de um membro calculado podem ser especificados fornecendo-se o nome da propriedade de célula no valor `MemberProperty_Identifier` e o valor da propriedade de célula no valor `Scalar_Expression` .</span><span class="sxs-lookup"><span data-stu-id="33c4a-112">The values of intrinsic cell properties for a calculated member can be optionally specified by supplying the name of the cell property in the `MemberProperty_Identifier` value and the value of the cell property in the `Scalar_Expression` value.</span></span>  
  
## <a name="with-keyword-examples"></a><span data-ttu-id="33c4a-113">Exemplos da palavra-chave WITH</span><span class="sxs-lookup"><span data-stu-id="33c4a-113">WITH Keyword Examples</span></span>  
 <span data-ttu-id="33c4a-114">A consulta MDX a seguir define um membro calculado, `[Measures].[Special Discount]`, calculando um desconto especial com base no valor de desconto original.</span><span class="sxs-lookup"><span data-stu-id="33c4a-114">The following MDX query defines a calculated member, `[Measures].[Special Discount]`, calculating a special discount based on the original discount amount.</span></span>  
  
```  
WITH   
   MEMBER [Measures].[Special Discount] AS  
   [Measures].[Discount Amount] * 1.5  
SELECT   
   [Measures].[Special Discount] on COLUMNS,  
   NON EMPTY [Product].[Product].MEMBERS  ON Rows  
FROM [Adventure Works]  
WHERE [Product].[Category].[Bikes]  
```  
  
 <span data-ttu-id="33c4a-115">Também é possível criar membros calculados em qualquer ponto de uma hierarquia.</span><span class="sxs-lookup"><span data-stu-id="33c4a-115">You can also create calculated members at any point within a hierarchy.</span></span> <span data-ttu-id="33c4a-116">Por exemplo, a consulta MDX a seguir define o membro calculado `[BigSeller]` para um cubo Vendas hipotético.</span><span class="sxs-lookup"><span data-stu-id="33c4a-116">For example, the following MDX query defines the `[BigSeller]` calculated member for a hypothetical Sales cube.</span></span> <span data-ttu-id="33c4a-117">Esse membro calculado determina se uma loja especificada possui, no mínimo, 100,00 em vendas unitárias para cerveja e vinho.</span><span class="sxs-lookup"><span data-stu-id="33c4a-117">This calculated member determines whether a specified store has at least 100.00 in unit sales for beer and wine.</span></span> <span data-ttu-id="33c4a-118">No entanto, a consulta cria o membro calculado `[BigSeller]` não como um membro filho da dimensão `[Product]` , mas sim como um membro filho do membro `[Beer and Wine]` .</span><span class="sxs-lookup"><span data-stu-id="33c4a-118">However, the query creates the `[BigSeller]` calculated member not as a child member of the `[Product]` dimension, but instead as a child member of the `[Beer and Wine]` member.</span></span>  
  
```  
WITH   
   MEMBER [Product].[Beer and Wine].[BigSeller] AS  
  IIf([Product].[Beer and Wine] > 100, "Yes","No")  
SELECT  
   {[Product].[BigSeller]} ON COLUMNS,  
   Store.[Store Name].Members ON ROWS  
FROM Sales  
  
```  
  
 <span data-ttu-id="33c4a-119">Membros calculados não têm que depender exclusivamente dos membros existentes em um cubo.</span><span class="sxs-lookup"><span data-stu-id="33c4a-119">Calculated members do not have to depend only on existing members in a cube.</span></span> <span data-ttu-id="33c4a-120">O membro calculado também pode basear-se em outros membros calculados definidos na mesma expressão MDX.</span><span class="sxs-lookup"><span data-stu-id="33c4a-120">Calculated member can also be based on other calculated members defined in the same MDX expression.</span></span> <span data-ttu-id="33c4a-121">Por exemplo, a consulta MDX a seguir usa o valor criado pelo primeiro membro calculado, `[Measures].[Special Discount]`, para gerar o valor do segundo membro calculado, `[Measures].[Special Discounted Amount]`:</span><span class="sxs-lookup"><span data-stu-id="33c4a-121">For example, the following MDX query uses the value created in the first calculated member, `[Measures].[Special Discount]`, to generate the value of the second calculated member, `[Measures].[Special Discounted Amount]`.</span></span>  
  
```  
WITH   
   MEMBER [Measures].[Special Discount] AS  
   [Measures].[Discount Percentage] * 1.5,   
   FORMAT_STRING = 'Percent'  
  
   MEMBER [Measures].[Special Discounted Amount] AS  
   [Measures].[Reseller Average Unit Price] * [Measures].[Special Discount],   
   FORMAT_STRING = 'Currency'  
  
SELECT   
   {[Measures].[Special Discount], [Measures].[Special Discounted Amount]} on COLUMNS,  
   NON EMPTY [Product].[Product].MEMBERS  ON Rows  
FROM [Adventure Works]  
WHERE [Product].[Category].[Bikes]  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="33c4a-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="33c4a-122">See Also</span></span>  
 <span data-ttu-id="33c4a-123">[Referência de função MDX &#40;&#41;MDX](/sql/mdx/mdx-function-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="33c4a-123">[MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx) </span></span>  
 <span data-ttu-id="33c4a-124">[Instrução SELECT &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select) </span><span class="sxs-lookup"><span data-stu-id="33c4a-124">[SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select) </span></span>  
 [<span data-ttu-id="33c4a-125">Criando membros calculados no escopo da sessão &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="33c4a-125">Creating Session-Scoped Calculated Members &#40;MDX&#41;</span></span>](mdx-calculated-members-session-scoped-calculated-members.md)  
  
  
