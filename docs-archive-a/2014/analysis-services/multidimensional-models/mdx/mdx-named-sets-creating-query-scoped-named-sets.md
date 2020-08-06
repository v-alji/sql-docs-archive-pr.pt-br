---
title: Criando conjuntos nomeados no escopo da consulta (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- query-scoped named sets [MDX]
- WITH keyword
ms.assetid: 78bc1e9a-1bc4-4a5a-ab0b-cf430c8fbfe1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6eccb4e20fca03079a04a0219b07f6411b80a433
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680095"
---
# <a name="creating-query-scoped-named-sets-mdx"></a><span data-ttu-id="51dc6-102">Criando conjuntos nomeados no escopo da consulta (MDX)</span><span class="sxs-lookup"><span data-stu-id="51dc6-102">Creating Query-Scoped Named Sets (MDX)</span></span>
  <span data-ttu-id="51dc6-103">Se um conjunto nomeado for necessário para uma única consulta MDX, é possível defini-lo usando a palavra-chave WITH.</span><span class="sxs-lookup"><span data-stu-id="51dc6-103">If a named set is only required for a single Multidimensional Expressions (MDX) query, you can define that named set by using the WITH keyword.</span></span> <span data-ttu-id="51dc6-104">O conjunto nomeado criado com a palavra-chave WITH deixará de existir ao fim da execução da consulta.</span><span class="sxs-lookup"><span data-stu-id="51dc6-104">A named set that is created by using the WITH keyword no longer exists after the query has finished running.</span></span>  
  
 <span data-ttu-id="51dc6-105">Como discutido neste tópico, a sintaxe da palavra-chave WITH é bem flexível, comportando até o uso de funções para definir o conjunto nomeado.</span><span class="sxs-lookup"><span data-stu-id="51dc6-105">As discussed in this topic, the syntax of the WITH keyword is quite flexible, even accommodating the use of functions to define the named set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="51dc6-106">Para obter mais informações sobre conjuntos nomeados, consulte [Criando conjuntos nomeados em MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="51dc6-106">For more information about named sets, see [Building Named Sets in MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span></span>  
  
## <a name="with-keyword-syntax"></a><span data-ttu-id="51dc6-107">Sintaxe da palavra-chave WITH</span><span class="sxs-lookup"><span data-stu-id="51dc6-107">WITH Keyword Syntax</span></span>  
 <span data-ttu-id="51dc6-108">Use a sintaxe a seguir para adicionar a palavra-chave WITH a uma instrução MDX SELECT:</span><span class="sxs-lookup"><span data-stu-id="51dc6-108">Use the following syntax to add the WITH keyword to a MDX SELECT statement:</span></span>  
  
```  
[ WITH <SELECT WITH clause> [ , <SELECT WITH clause> ... ] ]   
SELECT [ * | ( <SELECT query axis clause> [ , <SELECT query axis clause> ... ] ) ]  
FROM <SELECT subcube clause>   
[ <SELECT slicer axis clause> ]  
[ <SELECT cell property list clause> ]  
  
<SELECT WITH clause> ::=  
   ( SET Set_Identifier AS 'Set_Expression')  
  
```  
  
 <span data-ttu-id="51dc6-109">Na sintaxe para a palavra-chave WITH, o parâmetro `Set_Identifier` contém o alias do conjunto nomeado.</span><span class="sxs-lookup"><span data-stu-id="51dc6-109">In the syntax for the WITH keyword, the `Set_Identifier` parameter contains the alias for the named set.</span></span> <span data-ttu-id="51dc6-110">O parâmetro `Set_Expression` contém a expressão de conjunto à qual se refere o alias do conjunto nomeado.</span><span class="sxs-lookup"><span data-stu-id="51dc6-110">The `Set_Expression` parameter contains the set expression to which the named set alias refers.</span></span>  
  
## <a name="with-keyword-example"></a><span data-ttu-id="51dc6-111">Exemplo da palavra-chave WITH</span><span class="sxs-lookup"><span data-stu-id="51dc6-111">WITH Keyword Example</span></span>  
 <span data-ttu-id="51dc6-112">A consulta MDX a seguir examina a venda unitária dos diversos vinhos Chardonnay e Chablis em `FoodMart 2000`, o banco de dados de exemplo do Microsoft SQL Server 2000 Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="51dc6-112">The following MDX query examines the unit sales of the various Chardonnay and Chablis wines in `FoodMart 2000`, the sample database for Microsoft SQL Server 2000 Analysis Services.</span></span> <span data-ttu-id="51dc6-113">Essa consulta, embora bem simples em termos de conjunto de resultados, é longa e complicada quando requer manutenção.</span><span class="sxs-lookup"><span data-stu-id="51dc6-113">This query, although fairly simple in terms of the result set, is lengthy and unwieldy when you have to maintenance such a query.</span></span>  
  
```  
SELECT  
   {[Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Good].[Good Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Pearl].[Pearl Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Portsmouth].[Portsmouth Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Top Measure].[Top Measure Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Walrus].[Walrus Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Good].[Good Chablis Wine],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Pearl].[Pearl Chablis Wine],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Portsmouth].[Portsmouth Chablis Wine],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Top Measure].[Top Measure Chablis Wine],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Walrus].[Walrus Chablis Wine]} ON COLUMNS,  
   {Measures.[Unit Sales]} ON ROWS  
FROM Sales  
```  
  
 <span data-ttu-id="51dc6-114">Para facilitar a manutenção da consulta MDX anterior, você pode criar um conjunto nomeado para ela usando a palavra-chave WITH.</span><span class="sxs-lookup"><span data-stu-id="51dc6-114">To make the previous MDX query easier to maintain, you can create a named set for the query by using the WITH keyword.</span></span> <span data-ttu-id="51dc6-115">O código a seguir mostra como usar a palavra-chave WITH para criar um conjunto nomeado, `[ChardonnayChablis]`, e como o conjunto nomeado torna a manutenção da instrução SELECT mais rápida e fácil.</span><span class="sxs-lookup"><span data-stu-id="51dc6-115">The following code shows how to use the WITH keyword to create a named set, `[ChardonnayChablis]`, and how the named set makes the SELECT statement shorter and easier to maintain.</span></span>  
  
```  
WITH SET [ChardonnayChablis] AS  
   {[Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Good].[Good Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Pearl].[Pearl Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Portsmouth].[Portsmouth Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Top Measure].[Top Measure Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Walrus].[Walrus Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Good].[Good Chablis Wine],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Pearl].[Pearl Chablis Wine],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Portsmouth].[Portsmouth Chablis Wine],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Top Measure].[Top Measure Chablis Wine],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Walrus].[Walrus Chablis Wine]}  
  
SELECT  
   [ChardonnayChablis] ON COLUMNS,  
   {Measures.[Unit Sales]} ON ROWS  
FROM Sales  
```  
  
### <a name="using-functions-together-with-the-with-keyword"></a><span data-ttu-id="51dc6-116">Usando funções com a palavra-chave WITH</span><span class="sxs-lookup"><span data-stu-id="51dc6-116">Using Functions Together with the WITH Keyword</span></span>  
 <span data-ttu-id="51dc6-117">Embora seja possível definir explicitamente cada membro de um conjunto nomeado, essa abordagem pode produzir uma instrução extensa.</span><span class="sxs-lookup"><span data-stu-id="51dc6-117">Although you can explicitly define each member of a named set, this approach can produce a lengthy statement.</span></span> <span data-ttu-id="51dc6-118">Para facilitar a criação e a manutenção de um conjunto nomeado, use as funções MDX para definir os membros.</span><span class="sxs-lookup"><span data-stu-id="51dc6-118">To make the creation and maintenance of a named set easier, you can use MDX functions to define the members.</span></span>  
  
 <span data-ttu-id="51dc6-119">Por exemplo, o exemplo de consulta MDX a seguir usa as funções MDX [Filter](/sql/mdx/filter-mdx), [CurrentMember](/sql/mdx/current-mdx)e [Name](/sql/mdx/members-string-mdx) e a função VBA InStr para criar o conjunto nomeado `[ChardonnayChablis]` .</span><span class="sxs-lookup"><span data-stu-id="51dc6-119">For example, the following MDX query example uses the [Filter](/sql/mdx/filter-mdx), [CurrentMember](/sql/mdx/current-mdx), and [Name](/sql/mdx/members-string-mdx) MDX functions and the InStr VBA function to create the `[ChardonnayChablis]` named set.</span></span> <span data-ttu-id="51dc6-120">Essa versão do conjunto nomeado `[ChardonnayChablis]` é igual àquela definida explicitamente e mostrada anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="51dc6-120">This version of the `[ChardonnayChablis]` named set is the same as the explicitly defined version shown previously in this topic.</span></span>  
  
```  
WITH SET [ChardonnayChablis] AS  
   'Filter([Product].Members, (InStr(1, [Product].CurrentMember.Name, "chardonnay") <> 0) OR (InStr(1, [Product].CurrentMember.Name, "chablis") <> 0))'  
  
SELECT  
   [ChardonnayChablis] ON COLUMNS,  
   {Measures.[Unit Sales]} ON ROWS  
FROM Sales  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="51dc6-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="51dc6-121">See Also</span></span>  
 <span data-ttu-id="51dc6-122">[Instrução SELECT &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select) </span><span class="sxs-lookup"><span data-stu-id="51dc6-122">[SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select) </span></span>  
 [<span data-ttu-id="51dc6-123">Criando conjuntos nomeados no escopo da sessão &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="51dc6-123">Creating Session-Scoped Named Sets &#40;MDX&#41;</span></span>](mdx-named-sets-creating-session-scoped-named-sets.md)  
  
  
