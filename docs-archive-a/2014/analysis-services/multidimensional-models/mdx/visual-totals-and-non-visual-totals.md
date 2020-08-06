---
title: Totais visuais e totais não visuais | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ea9d02f2-a668-4547-ade5-e3d077a2e1bd
author: minewiskan
ms.author: owend
ms.openlocfilehash: ddff047be6a819d05276848cbeb430fb8e4c9c2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683748"
---
# <a name="visual-totals-and-non-visual-totals"></a><span data-ttu-id="bfdda-102">Totais visuais e totais não visuais</span><span class="sxs-lookup"><span data-stu-id="bfdda-102">Visual Totals and Non Visual Totals</span></span>
  <span data-ttu-id="bfdda-103">Totais visuais são totais no final de uma coluna ou linha que somam todos os itens visíveis na coluna ou linha.</span><span class="sxs-lookup"><span data-stu-id="bfdda-103">Visual Totals are totals at the end of a column or row that add up all of the items visible in the column or row.</span></span> <span data-ttu-id="bfdda-104">Esse é o comportamento padrão da maioria das tabelas ao serem exibidas.</span><span class="sxs-lookup"><span data-stu-id="bfdda-104">This is the default behavior for most tables when displayed.</span></span> <span data-ttu-id="bfdda-105">Porém, ocasionalmente o usuário desejará exibir somente certas colunas em uma tabela, mas manter os totais da linha inteira, inclusive das colunas que não são exibidas.</span><span class="sxs-lookup"><span data-stu-id="bfdda-105">However, there are times when the user wants to display only certain columns in a table but keep the totals for the entire row, including those that are not displayed.</span></span> <span data-ttu-id="bfdda-106">Esses são chamados de `Non Visual Totals`, porque o total provém de valores tanto visíveis como não visíveis.</span><span class="sxs-lookup"><span data-stu-id="bfdda-106">These are called `Non Visual Totals`, because the total comes from both the visible and non-visible values.</span></span>  
  
 <span data-ttu-id="bfdda-107">O cenário a seguir demonstra o comportamento dos totais Não Visuais.</span><span class="sxs-lookup"><span data-stu-id="bfdda-107">The following scenario demonstrates the behavior of Non Visual totals.</span></span> <span data-ttu-id="bfdda-108">A primeira etapa mostra o comportamento padrão dos Totais Visuais.</span><span class="sxs-lookup"><span data-stu-id="bfdda-108">The first step shows the default behavior of Visual Totals.</span></span>  
  
 <span data-ttu-id="bfdda-109">O exemplo a seguir é uma consulta da [Adventure Works] para obter números de [Valor das Vendas do Revendedor] em uma tabela em que as categorias de produto são as colunas e os tipos de negócios dos revendedores são as linhas.</span><span class="sxs-lookup"><span data-stu-id="bfdda-109">The following example is a query of [Adventure Works] to obtain [Reseller Sales Amount] figures in a table where the product categories are the columns and the reseller business types are the rows.</span></span> <span data-ttu-id="bfdda-110">Observe que são fornecidos totais para produtos e revendedores quando a seguinte instrução SELECT é emitida:</span><span class="sxs-lookup"><span data-stu-id="bfdda-110">Note that totals are given for both products and resellers when the following SELECT statement is issued:</span></span>  
  
 `select [Category].members on 0,`  
  
 `[Business Type].members on 1`  
  
 `from [Adventure Works]`  
  
 `where [Measures].[Reseller Sales Amount]`  
  
 <span data-ttu-id="bfdda-111">Gera os seguintes resultados:</span><span class="sxs-lookup"><span data-stu-id="bfdda-111">Produces the following results:</span></span>  
  
|||||||  
|-|-|-|-|-|-|  
||<span data-ttu-id="bfdda-112">**Todos os produtos**</span><span class="sxs-lookup"><span data-stu-id="bfdda-112">**All Products**</span></span>|<span data-ttu-id="bfdda-113">**Acessórios**</span><span class="sxs-lookup"><span data-stu-id="bfdda-113">**Accessories**</span></span>|<span data-ttu-id="bfdda-114">**Bikes**</span><span class="sxs-lookup"><span data-stu-id="bfdda-114">**Bikes**</span></span>|<span data-ttu-id="bfdda-115">**Roupas**</span><span class="sxs-lookup"><span data-stu-id="bfdda-115">**Clothing**</span></span>|<span data-ttu-id="bfdda-116">**Componentes**</span><span class="sxs-lookup"><span data-stu-id="bfdda-116">**Components**</span></span>|  
|<span data-ttu-id="bfdda-117">**Todos os Revendedores**</span><span class="sxs-lookup"><span data-stu-id="bfdda-117">**All Resellers**</span></span>|<span data-ttu-id="bfdda-118">**$80,450,596.98**</span><span class="sxs-lookup"><span data-stu-id="bfdda-118">**$80,450,596.98**</span></span>|<span data-ttu-id="bfdda-119">**$571,297.93**</span><span class="sxs-lookup"><span data-stu-id="bfdda-119">**$571,297.93**</span></span>|<span data-ttu-id="bfdda-120">**$66,302,381.56**</span><span class="sxs-lookup"><span data-stu-id="bfdda-120">**$66,302,381.56**</span></span>|<span data-ttu-id="bfdda-121">**$1,777,840.84**</span><span class="sxs-lookup"><span data-stu-id="bfdda-121">**$1,777,840.84**</span></span>|<span data-ttu-id="bfdda-122">**$11,799,076.66**</span><span class="sxs-lookup"><span data-stu-id="bfdda-122">**$11,799,076.66**</span></span>|  
|<span data-ttu-id="bfdda-123">**Specialty Bike Shop**</span><span class="sxs-lookup"><span data-stu-id="bfdda-123">**Specialty Bike Shop**</span></span>|<span data-ttu-id="bfdda-124">**$6,756,166.18**</span><span class="sxs-lookup"><span data-stu-id="bfdda-124">**$6,756,166.18**</span></span>|<span data-ttu-id="bfdda-125">**$65,125.48**</span><span class="sxs-lookup"><span data-stu-id="bfdda-125">**$65,125.48**</span></span>|<span data-ttu-id="bfdda-126">**$6,080,117.73**</span><span class="sxs-lookup"><span data-stu-id="bfdda-126">**$6,080,117.73**</span></span>|<span data-ttu-id="bfdda-127">**$252,933.91**</span><span class="sxs-lookup"><span data-stu-id="bfdda-127">**$252,933.91**</span></span>|<span data-ttu-id="bfdda-128">**$357,989.07**</span><span class="sxs-lookup"><span data-stu-id="bfdda-128">**$357,989.07**</span></span>|  
|<span data-ttu-id="bfdda-129">**Revendedor de Valor Agregado**</span><span class="sxs-lookup"><span data-stu-id="bfdda-129">**Value Added Reseller**</span></span>|<span data-ttu-id="bfdda-130">**$34,967,517.33**</span><span class="sxs-lookup"><span data-stu-id="bfdda-130">**$34,967,517.33**</span></span>|<span data-ttu-id="bfdda-131">**$175,002.81**</span><span class="sxs-lookup"><span data-stu-id="bfdda-131">**$175,002.81**</span></span>|<span data-ttu-id="bfdda-132">**$30,892,354.33**</span><span class="sxs-lookup"><span data-stu-id="bfdda-132">**$30,892,354.33**</span></span>|<span data-ttu-id="bfdda-133">**$592,385.71**</span><span class="sxs-lookup"><span data-stu-id="bfdda-133">**$592,385.71**</span></span>|<span data-ttu-id="bfdda-134">**$3,307,774.48**</span><span class="sxs-lookup"><span data-stu-id="bfdda-134">**$3,307,774.48**</span></span>|  
|<span data-ttu-id="bfdda-135">**Warehouse**</span><span class="sxs-lookup"><span data-stu-id="bfdda-135">**Warehouse**</span></span>|<span data-ttu-id="bfdda-136">**$38,726,913.48**</span><span class="sxs-lookup"><span data-stu-id="bfdda-136">**$38,726,913.48**</span></span>|<span data-ttu-id="bfdda-137">**$331,169.64**</span><span class="sxs-lookup"><span data-stu-id="bfdda-137">**$331,169.64**</span></span>|<span data-ttu-id="bfdda-138">**$29,329,909.50**</span><span class="sxs-lookup"><span data-stu-id="bfdda-138">**$29,329,909.50**</span></span>|<span data-ttu-id="bfdda-139">**$932,521.23**</span><span class="sxs-lookup"><span data-stu-id="bfdda-139">**$932,521.23**</span></span>|<span data-ttu-id="bfdda-140">**$8,133,313.11**</span><span class="sxs-lookup"><span data-stu-id="bfdda-140">**$8,133,313.11**</span></span>|  
  
## <a name="non-visual-on-rows-and-columns"></a><span data-ttu-id="bfdda-141">Não visual em linhas e colunas</span><span class="sxs-lookup"><span data-stu-id="bfdda-141">Non-Visual on rows and columns</span></span>  
 <span data-ttu-id="bfdda-142">Para produzir uma tabela somente com dados dos produtos Accessories e Clothing, revendedores Value Added Reseller e Warehouse, mas mantendo os totais gerais, o seguinte poderia ser escrito usando NON VISUAL:</span><span class="sxs-lookup"><span data-stu-id="bfdda-142">To produce a table with data only for the Accessories and Clothing products, the Value Added Reseller and Warehouse resellers, yet keeping the overall totals could be written as follows using NON VISUAL:</span></span>  
  
 `select [Category].members on 0,`  
  
 `[Business Type].members on 1`  
  
 `from NON VISUAL (Select {[Category].Accessories, [Category].Clothing} on 0,`  
  
 `{[Business Type].[Value Added Reseller], [Business Type].[Warehouse]} on 1`  
  
 `from [Adventure Works])`  
  
 `where [Measures].[Reseller Sales Amount]`  
  
 <span data-ttu-id="bfdda-143">Gera os seguintes resultados:</span><span class="sxs-lookup"><span data-stu-id="bfdda-143">Produces the following results:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="bfdda-144">**Todos os produtos**</span><span class="sxs-lookup"><span data-stu-id="bfdda-144">**All Products**</span></span>|<span data-ttu-id="bfdda-145">**Acessórios**</span><span class="sxs-lookup"><span data-stu-id="bfdda-145">**Accessories**</span></span>|<span data-ttu-id="bfdda-146">**Roupas**</span><span class="sxs-lookup"><span data-stu-id="bfdda-146">**Clothing**</span></span>|  
|<span data-ttu-id="bfdda-147">**Todos os Revendedores**</span><span class="sxs-lookup"><span data-stu-id="bfdda-147">**All Resellers**</span></span>|<span data-ttu-id="bfdda-148">**$80,450,596.98**</span><span class="sxs-lookup"><span data-stu-id="bfdda-148">**$80,450,596.98**</span></span>|<span data-ttu-id="bfdda-149">**$571,297.93**</span><span class="sxs-lookup"><span data-stu-id="bfdda-149">**$571,297.93**</span></span>|<span data-ttu-id="bfdda-150">**$1,777,840.84**</span><span class="sxs-lookup"><span data-stu-id="bfdda-150">**$1,777,840.84**</span></span>|  
|<span data-ttu-id="bfdda-151">**Revendedor de Valor Agregado**</span><span class="sxs-lookup"><span data-stu-id="bfdda-151">**Value Added Reseller**</span></span>|<span data-ttu-id="bfdda-152">**$34,967,517.33**</span><span class="sxs-lookup"><span data-stu-id="bfdda-152">**$34,967,517.33**</span></span>|<span data-ttu-id="bfdda-153">**$175,002.81**</span><span class="sxs-lookup"><span data-stu-id="bfdda-153">**$175,002.81**</span></span>|<span data-ttu-id="bfdda-154">**$592,385.71**</span><span class="sxs-lookup"><span data-stu-id="bfdda-154">**$592,385.71**</span></span>|  
|<span data-ttu-id="bfdda-155">**Warehouse**</span><span class="sxs-lookup"><span data-stu-id="bfdda-155">**Warehouse**</span></span>|<span data-ttu-id="bfdda-156">**$38,726,913.48**</span><span class="sxs-lookup"><span data-stu-id="bfdda-156">**$38,726,913.48**</span></span>|<span data-ttu-id="bfdda-157">**$331,169.64**</span><span class="sxs-lookup"><span data-stu-id="bfdda-157">**$331,169.64**</span></span>|<span data-ttu-id="bfdda-158">**$932,521.23**</span><span class="sxs-lookup"><span data-stu-id="bfdda-158">**$932,521.23**</span></span>|  
  
## <a name="non-visual-on-rows"></a><span data-ttu-id="bfdda-159">Não visual em linhas</span><span class="sxs-lookup"><span data-stu-id="bfdda-159">Non-Visual on rows</span></span>  
 <span data-ttu-id="bfdda-160">Para criar uma tabela que totalize visualmente as colunas, mas nos totais de linhas exiba o total verdadeiro de todos os itens em [Category], a seguinte consulta deve ser emitida:</span><span class="sxs-lookup"><span data-stu-id="bfdda-160">To produce a table that visually totals the columns but for row totals brings the true total of all [Category], the following query should be issued:</span></span>  
  
 `select [Category].members on 0,`  
  
 `[Business Type].members on 1`  
  
 `from NON VISUAL (Select {[Category].Accessories, [Category].Clothing} on 0`  
  
 `from ( Select {[Business Type].[Value Added Reseller], [Business Type].[Warehouse]} on 0`  
  
 `from [Adventure Works])`  
  
 `)`  
  
 `where [Measures].[Reseller Sales Amount]`  
  
 <span data-ttu-id="bfdda-161">Observe como NON VISUAL é aplicado somente a [Category].</span><span class="sxs-lookup"><span data-stu-id="bfdda-161">Note how NON VISUAL is only applied to [Category].</span></span>  
  
 <span data-ttu-id="bfdda-162">A consulta anterior gera os seguintes resultados:</span><span class="sxs-lookup"><span data-stu-id="bfdda-162">The above query produces the following results:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="bfdda-163">Todos os Produtos</span><span class="sxs-lookup"><span data-stu-id="bfdda-163">All Products</span></span>|<span data-ttu-id="bfdda-164">Acessórios</span><span class="sxs-lookup"><span data-stu-id="bfdda-164">Accessories</span></span>|<span data-ttu-id="bfdda-165">Roupas</span><span class="sxs-lookup"><span data-stu-id="bfdda-165">Clothing</span></span>|  
|<span data-ttu-id="bfdda-166">Todos os Revendedores</span><span class="sxs-lookup"><span data-stu-id="bfdda-166">All Resellers</span></span>|<span data-ttu-id="bfdda-167">$73,694,430.80</span><span class="sxs-lookup"><span data-stu-id="bfdda-167">$73,694,430.80</span></span>|<span data-ttu-id="bfdda-168">$506,172.45</span><span class="sxs-lookup"><span data-stu-id="bfdda-168">$506,172.45</span></span>|<span data-ttu-id="bfdda-169">$1,524,906.93</span><span class="sxs-lookup"><span data-stu-id="bfdda-169">$1,524,906.93</span></span>|  
|<span data-ttu-id="bfdda-170">Revendedor de Valor Agregado</span><span class="sxs-lookup"><span data-stu-id="bfdda-170">Value Added Reseller</span></span>|<span data-ttu-id="bfdda-171">$34,967,517.33</span><span class="sxs-lookup"><span data-stu-id="bfdda-171">$34,967,517.33</span></span>|<span data-ttu-id="bfdda-172">$175,002.81</span><span class="sxs-lookup"><span data-stu-id="bfdda-172">$175,002.81</span></span>|<span data-ttu-id="bfdda-173">$592,385.71</span><span class="sxs-lookup"><span data-stu-id="bfdda-173">$592,385.71</span></span>|  
|<span data-ttu-id="bfdda-174">Warehouse</span><span class="sxs-lookup"><span data-stu-id="bfdda-174">Warehouse</span></span>|<span data-ttu-id="bfdda-175">$38,726,913.48</span><span class="sxs-lookup"><span data-stu-id="bfdda-175">$38,726,913.48</span></span>|<span data-ttu-id="bfdda-176">$331,169.64</span><span class="sxs-lookup"><span data-stu-id="bfdda-176">$331,169.64</span></span>|<span data-ttu-id="bfdda-177">$932,521.23</span><span class="sxs-lookup"><span data-stu-id="bfdda-177">$932,521.23</span></span>|  
  
 <span data-ttu-id="bfdda-178">Quando comparados aos resultados anteriores, você poderá observar que a linha [Todos os Revendedores] agora soma os valores exibidos para [Revendedor de Valor Agregado] e [Warehouse], mas a coluna [Todos os Produtos] mostra o valor total para todos os produtos, inclusive aqueles não exibidos.</span><span class="sxs-lookup"><span data-stu-id="bfdda-178">When compared with the previous results, you can observe that the [All Resellers] row now adds up to the displayed values for [Value Added Reseller] and [Warehouse] but that the [All Products] column shows the total value for all products, including those not displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfdda-179">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bfdda-179">See Also</span></span>  
 <span data-ttu-id="bfdda-180">[Conceitos principais em MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="bfdda-180">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="bfdda-181">[Autoexists](autoexists.md) </span><span class="sxs-lookup"><span data-stu-id="bfdda-181">[Autoexists](autoexists.md) </span></span>  
 <span data-ttu-id="bfdda-182">[Trabalhando com membros, tuplas e conjuntos &#40;&#41;MDX](working-with-members-tuples-and-sets-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="bfdda-182">[Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md) </span></span>  
 <span data-ttu-id="bfdda-183">[Conceitos básicos de consulta MDX &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="bfdda-183">[MDX Query Fundamentals &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span></span>  
 <span data-ttu-id="bfdda-184">[A consulta MDX básica &#40;&#41;MDX](mdx-query-the-basic-query.md) </span><span class="sxs-lookup"><span data-stu-id="bfdda-184">[The Basic MDX Query &#40;MDX&#41;](mdx-query-the-basic-query.md) </span></span>  
 <span data-ttu-id="bfdda-185">[Restringindo a consulta com eixos de consulta e de segmentação &#40;MDX&#41;](mdx-query-and-slicer-axes-restricting-the-query.md) </span><span class="sxs-lookup"><span data-stu-id="bfdda-185">[Restricting the Query with Query and Slicer Axes &#40;MDX&#41;](mdx-query-and-slicer-axes-restricting-the-query.md) </span></span>  
 [<span data-ttu-id="bfdda-186">Estabelecendo o contexto de cubo em uma consulta &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="bfdda-186">Establishing Cube Context in a Query &#40;MDX&#41;</span></span>](establishing-cube-context-in-a-query-mdx.md)  
  
  
