---
title: Autoexiste | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 56283497-624c-45b5-8a0d-036b0e331d22
author: minewiskan
ms.author: owend
ms.openlocfilehash: dd35958a364456c12d58392afe3754f6adcf97b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575423"
---
# <a name="autoexists"></a><span data-ttu-id="8e47b-102">autoexists</span><span class="sxs-lookup"><span data-stu-id="8e47b-102">Autoexists</span></span>
  <span data-ttu-id="8e47b-103">O conceito de *autoexists* limita o espaço de cubo a células que, de fato, existem no cubo em contraposição às que podem existir em decorrência da criação de todas as combinações possíveis de membros de hierarquia de atributos da mesma hierarquia.</span><span class="sxs-lookup"><span data-stu-id="8e47b-103">The concept of *autoexists* limits the cube space to those cells that actually exist in the cube in contraposition to those that might exist as a result of creating all possible combinations of attribute hierarchy members from the same hierarchy.</span></span> <span data-ttu-id="8e47b-104">Isso porque os membros de uma hierarquia de atributo não podem existir com membros de outra hierarquia de atributo na mesma dimensão.</span><span class="sxs-lookup"><span data-stu-id="8e47b-104">This is because members of one attribute hierarchy cannot exist with members of another attribute hierarchy in the same dimension.</span></span> <span data-ttu-id="8e47b-105">Quando duas ou mais hierarquias de atributo da mesma dimensão são usadas em uma instrução SELECT, o Analysis Services avalia as expressões dos atributos para verificar se os membros desses atributos sejam corretamente confinados para atender aos critérios de todos os outros atributos.</span><span class="sxs-lookup"><span data-stu-id="8e47b-105">When two or more attribute hierarchies of the same dimension are used in a SELECT statement, Analysis Services evaluates the attributes' expressions to make sure that the members of those attributes are properly confined to meet the criteria of all other attributes.</span></span>  
  
 <span data-ttu-id="8e47b-106">Por exemplo, vamos supor que você esteja trabalhando com atributos da dimensão Geografia.</span><span class="sxs-lookup"><span data-stu-id="8e47b-106">For example, suppose you are working with attributes from the Geography dimension.</span></span> <span data-ttu-id="8e47b-107">Se houver uma expressão que retorne todos os membros do atributo City e outra que confine os membros do atributo Country a todos os países da Europa, isso resultará no confinamento dos membros de City apenas às cidades que pertençam a países da Europa.</span><span class="sxs-lookup"><span data-stu-id="8e47b-107">If you have one expression that returns all members from the City attribute and another expression that confines members from the Country attribute to all countries in Europe, then this will result in the City members being confined to only those cities that belong to countries in Europe.</span></span> <span data-ttu-id="8e47b-108">Isso por conta da característica autoexists do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="8e47b-108">This is because of the autoexists characteristic of Analysis Services.</span></span> <span data-ttu-id="8e47b-109">Autoexists somente se aplica a atributos da mesma dimensão porque tenta impedir que os registros da dimensão excluídos em uma expressão do atributo sejam incluídos pelas outras expressões do atributo.</span><span class="sxs-lookup"><span data-stu-id="8e47b-109">Autoexists only applies to attributes from the same dimension because it tries to prevent the dimension records excluded in one attribute expression from being included by the other attribute expressions.</span></span> <span data-ttu-id="8e47b-110">Autoexists também pode ser considerado a interseção resultante das diferentes expressões de atributo em relação às linhas de dimensão.</span><span class="sxs-lookup"><span data-stu-id="8e47b-110">Autoexists can also be understood as the resulting intersection of the different attributes expressions over the dimension rows.</span></span>  
  
## <a name="cell-existence"></a><span data-ttu-id="8e47b-111">Existência da célula</span><span class="sxs-lookup"><span data-stu-id="8e47b-111">Cell Existence</span></span>  
 <span data-ttu-id="8e47b-112">As seguintes células sempre existem:</span><span class="sxs-lookup"><span data-stu-id="8e47b-112">The following cells always exist:</span></span>  
  
-   <span data-ttu-id="8e47b-113">O membro (All), de toda hierarquia, quando cruzado com membros de outras hierarquias na mesma dimensão.</span><span class="sxs-lookup"><span data-stu-id="8e47b-113">The (All) member, of every hierarchy, when crossed with members of other hierarchies in the same dimension.</span></span>  
  
-   <span data-ttu-id="8e47b-114">Os membros calculados quando cruzados com seus irmãos não calculados, ou com seus pais ou descendentes de seus irmãos não calculados.</span><span class="sxs-lookup"><span data-stu-id="8e47b-114">Calculated members when crossed with their non-calculated siblings, or with the parents or descendants of their non-calculated siblings.</span></span>  
  
## <a name="providing-non-existing-cells"></a><span data-ttu-id="8e47b-115">Fornecendo células não existentes</span><span class="sxs-lookup"><span data-stu-id="8e47b-115">Providing Non-existing cells</span></span>  
 <span data-ttu-id="8e47b-116">Uma célula não existente é uma célula fornecida pelo sistema como uma resposta para uma consulta ou um cálculo que solicita uma célula não existente no cubo.</span><span class="sxs-lookup"><span data-stu-id="8e47b-116">A non-existing cell is a cell provided by the system as a response to a query or calculation that requests a cell that does not exist in the cube.</span></span> <span data-ttu-id="8e47b-117">Por exemplo, se você tiver um cubo com uma hierarquia de atributo City e uma hierarquia de atributo Country pertencentes à dimensão Geography, além de uma medida Internet Sales Amount, o espaço desse cubo só incluirá os membros existentes entre si.</span><span class="sxs-lookup"><span data-stu-id="8e47b-117">For example, if you have a cube that has a City attribute hierarchy and a Country attribute hierarchy that belong to the Geography dimension, and an Internet Sales Amount measure, the space of this cube only includes those members that exist with each other.</span></span> <span data-ttu-id="8e47b-118">Por exemplo, se a hierarquia de atributo Cidade incluir as cidades de Nova Iorque, Londres, Paris, Tóquio e Melbourne; e a hierarquia de atributo País incluir os países Estados Unidos, Reino Unido, França, Japão e Austrália; o espaço do cubo não incluirá o espaço (célula) na interseção Paris e Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="8e47b-118">For example, if the City attribute hierarchy includes the cities New York, London, Paris, Tokyo, and Melbourne; and the Country attribute hierarchy includes the countries United States, United Kingdom, France, Japan, and Australia; then the space of the cube does not include the space (cell) at the intersection of Paris and United States.</span></span>  
  
 <span data-ttu-id="8e47b-119">Ao consultar células que não existem, as células inexistentes retornarão nulas; ou seja, elas não poderão conter cálculos e você não poderá definir um cálculo que seja gravado nesse espaço.</span><span class="sxs-lookup"><span data-stu-id="8e47b-119">When querying cells that do not exist, non-existing cells return nulls; that is, they cannot contain calculations and you cannot define a calculation that writes to this space.</span></span> <span data-ttu-id="8e47b-120">Por exemplo, a instrução a seguir inclui células que não existem.</span><span class="sxs-lookup"><span data-stu-id="8e47b-120">For example, the following statement includes cells that do not exist.</span></span>  
  
```  
SELECT [Customer].[Gender].[Gender].Members ON COLUMNS,  
{[Customer].[Customer].[Aaron A. Allen]  
   ,[Customer].[Customer].[Abigail Clark]} ON ROWS   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="8e47b-121">Essa consulta usa a função [Membros (Conjunto) (MDX)](/sql/mdx/members-set-mdx) para retornar o conjunto de membros da hierarquia de atributo Sexo no eixo da coluna, e cruza esse conjunto com o conjunto especificado de membros da hierarquia de atributo Cliente no eixo de linhas.</span><span class="sxs-lookup"><span data-stu-id="8e47b-121">This query uses the [Members (Set) (MDX)](/sql/mdx/members-set-mdx) function to return the set of members of the Gender attribute hierarchy on the column axis, and crosses this set with the specified set of members from the Customer attribute hierarchy on the row axis.</span></span>  
  
 <span data-ttu-id="8e47b-122">Quando você executa a consulta anterior, a célula na interseção Aaron A. Allen e Feminino exibe um valor nulo.</span><span class="sxs-lookup"><span data-stu-id="8e47b-122">When you execute the previous query, the cell at the intersection of Aaron A. Allen and Female displays a null.</span></span> <span data-ttu-id="8e47b-123">Similarmente, a célula na interseção Abigail Clark e Masculino exibe um valor nulo.</span><span class="sxs-lookup"><span data-stu-id="8e47b-123">Similarly, the cell at the intersection of Abigail Clark and Male displays a null.</span></span> <span data-ttu-id="8e47b-124">Essas células não existem e não podem conter um valor, mas as células que não existem podem aparecer no resultado retornado por uma consulta.</span><span class="sxs-lookup"><span data-stu-id="8e47b-124">These cells do not exist and cannot contain a value, but cells that do not exist can appear in the result returned by a query.</span></span>  
  
 <span data-ttu-id="8e47b-125">Quando você usa a função [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) para retornar o produto vetorial de membros de hierarquia de atributo de hierarquias de atributo na mesma dimensão, o Autoexists limita as tuplas que são retornadas ao conjunto de tuplas que realmente existem, em vez de retornar um produto Cartesiano completo.</span><span class="sxs-lookup"><span data-stu-id="8e47b-125">When you use the [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) function to return the cross-product of attribute hierarchy members from attribute hierarchies in the same dimension, auto-exists limits those tuples being returned to the set of tuples that actually exist, rather than returning a full Cartesian product.</span></span> <span data-ttu-id="8e47b-126">Por exemplo, execute e examine os resultados da execução da consulta a seguir.</span><span class="sxs-lookup"><span data-stu-id="8e47b-126">For example, run and then examine the results from the execution of the following query.</span></span>  
  
```  
SELECT CROSSJOIN  
   (  
      {[Customer].[Country].[United States]},  
         [Customer].[State-Province].Members  
  ) ON 0   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="8e47b-127">Note que 0 é usado para designar o eixo da coluna, que é a forma abreviada de eixo (0) – que é o eixo da coluna.</span><span class="sxs-lookup"><span data-stu-id="8e47b-127">Notice that 0 is used to designate the column axis, which is shorthand for axis(0) - which is the column axis.</span></span>  
  
 <span data-ttu-id="8e47b-128">A consulta anterior somente retorna células para membros de cada hierarquia de atributo na consulta que existe um com o outro.</span><span class="sxs-lookup"><span data-stu-id="8e47b-128">The previous query only returns cells for members from each attribute hierarchy in the query that exist with each other.</span></span> <span data-ttu-id="8e47b-129">A consulta anterior também pode ser escrita usando a nova \* variante da função [de interjunção (MDX)](/sql/mdx/crossjoin-mdx) .</span><span class="sxs-lookup"><span data-stu-id="8e47b-129">The previous query can also be written using the new \* variant of the [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) function.</span></span>  
  
```  
SELECT   
   [Customer].[Country].[United States] *   
      [Customer].[State-Province].Members  
ON 0   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
 <span data-ttu-id="8e47b-130">A consulta anterior também poderia ser escrita da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="8e47b-130">The previous query could also be written in the following manner:</span></span>  
  
```  
SELECT [Customer].[State-Province].Members  
ON 0   
FROM [Adventure Works]  
WHERE (Measures.[Internet Sales Amount],  
   [Customer].[Country].[United States])  
```  
  
 <span data-ttu-id="8e47b-131">Os valores das células retornadas serão idênticos, apesar de os metadados no conjunto de resultados serem diferentes.</span><span class="sxs-lookup"><span data-stu-id="8e47b-131">The cells values returned will be identical, although the metadata in the result set will be different.</span></span> <span data-ttu-id="8e47b-132">Por exemplo, com a consulta anterior, a hierarquia País foi movida para o eixo do slicer (na cláusula WHERE) e, portanto, não aparece explicitamente no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="8e47b-132">For example, with the previous query, the Country hierarchy was moved to the slicer axis (in the WHERE clause) and therefore does not appear explicitly in the result set.</span></span>  
  
 <span data-ttu-id="8e47b-133">Cada uma dessas três consultas anteriores demonstra o efeito do comportamento de existência automática no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8e47b-133">Each of these three previous queries demonstrates the effect of the auto-exists behavior in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="deep-and-shallow-autoexists"></a><span data-ttu-id="8e47b-134">Autoexists Deep e Shallow</span><span class="sxs-lookup"><span data-stu-id="8e47b-134">Deep and Shallow Autoexists</span></span>  
 <span data-ttu-id="8e47b-135">Autoexists pode ser aplicado às expressões como Deep ou Shallow.</span><span class="sxs-lookup"><span data-stu-id="8e47b-135">Autoexists can be applied to the expressions as Deep or Shallow.</span></span> <span data-ttu-id="8e47b-136">`Deep Autoexists` significa que todas as expressões serão avaliadas para atender o espaço mais profundo possível após a aplicação das expressões de segmentação de dados, das expressões de subseleção no eixo etc.</span><span class="sxs-lookup"><span data-stu-id="8e47b-136">`Deep Autoexists` means that all expressions will be evaluated to meet the deepest possible space after applying the slicer expressions, the sub select expressions in the axis, and so on.</span></span> <span data-ttu-id="8e47b-137">`Shallow Autoexists` quer dizer que as expressões externas são avaliadas antes da expressão atual e esses resultados são transmitidos à expressão atual.</span><span class="sxs-lookup"><span data-stu-id="8e47b-137">`Shallow Autoexists` means that external expressions are evaluated before the current expression and those results are passed to the current expression.</span></span> <span data-ttu-id="8e47b-138">A configuração padrão é deep autoexists.</span><span class="sxs-lookup"><span data-stu-id="8e47b-138">The default setting is deep autoexists.</span></span>  
  
 <span data-ttu-id="8e47b-139">O cenário e os exemplos a seguir ajudarão a ilustrar os tipos diferentes de Autoexistss.</span><span class="sxs-lookup"><span data-stu-id="8e47b-139">The following scenario and samples will help to illustrate the different types of Autoexistss.</span></span> <span data-ttu-id="8e47b-140">Nos exemplos a seguir, dois conjuntos serão criados: um como uma expressão calculada e o outro como uma expressão constante.</span><span class="sxs-lookup"><span data-stu-id="8e47b-140">In the following examples two sets will be created: one as a calculated expression and the other as a constant expression.</span></span>  
  
 `//Obtain the Top 10 best reseller selling products by Name`  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `set Preferred10Products as '`  
  
 `{[Product].[Model Name].&[Mountain-200],`  
  
 `[Product].[Model Name].&[Road-250],`  
  
 `[Product].[Model Name].&[Mountain-100],`  
  
 `[Product].[Model Name].&[Road-650],`  
  
 `[Product].[Model Name].&[Touring-1000],`  
  
 `[Product].[Model Name].&[Road-550-W],`  
  
 `[Product].[Model Name].&[Road-350-W],`  
  
 `[Product].[Model Name].&[HL Mountain Frame],`  
  
 `[Product].[Model Name].&[Road-150],`  
  
 `[Product].[Model Name].&[Touring-3000]`  
  
 `}'`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Top10SellingProducts on 1`  
  
 `from [Adventure Works]`  
  
 <span data-ttu-id="8e47b-141">O conjunto de resultados obtido é:</span><span class="sxs-lookup"><span data-stu-id="8e47b-141">The obtained result set is:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="8e47b-142">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="8e47b-142">**Reseller Sales Amount**</span></span>|<span data-ttu-id="8e47b-143">**Valor de desconto**</span><span class="sxs-lookup"><span data-stu-id="8e47b-143">**Discount Amount**</span></span>|<span data-ttu-id="8e47b-144">**Desconto PCT**</span><span class="sxs-lookup"><span data-stu-id="8e47b-144">**PCT Discount**</span></span>|  
|<span data-ttu-id="8e47b-145">**Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="8e47b-145">**Mountain-200**</span></span>|<span data-ttu-id="8e47b-146">**$14,356,699.36**</span><span class="sxs-lookup"><span data-stu-id="8e47b-146">**$14,356,699.36**</span></span>|<span data-ttu-id="8e47b-147">**$19,012.71**</span><span class="sxs-lookup"><span data-stu-id="8e47b-147">**$19,012.71**</span></span>|<span data-ttu-id="8e47b-148">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-148">**0.13%**</span></span>|  
|<span data-ttu-id="8e47b-149">**Road-250**</span><span class="sxs-lookup"><span data-stu-id="8e47b-149">**Road-250**</span></span>|<span data-ttu-id="8e47b-150">**$9,377,457.68**</span><span class="sxs-lookup"><span data-stu-id="8e47b-150">**$9,377,457.68**</span></span>|<span data-ttu-id="8e47b-151">**$4,032.47**</span><span class="sxs-lookup"><span data-stu-id="8e47b-151">**$4,032.47**</span></span>|<span data-ttu-id="8e47b-152">**0, 4%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-152">**0.04%**</span></span>|  
|<span data-ttu-id="8e47b-153">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="8e47b-153">**Mountain-100**</span></span>|<span data-ttu-id="8e47b-154">**$8,568,958.27**</span><span class="sxs-lookup"><span data-stu-id="8e47b-154">**$8,568,958.27**</span></span>|<span data-ttu-id="8e47b-155">**$139,393.27**</span><span class="sxs-lookup"><span data-stu-id="8e47b-155">**$139,393.27**</span></span>|<span data-ttu-id="8e47b-156">**1,63%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-156">**1.63%**</span></span>|  
|<span data-ttu-id="8e47b-157">**Road-650**</span><span class="sxs-lookup"><span data-stu-id="8e47b-157">**Road-650**</span></span>|<span data-ttu-id="8e47b-158">**$7,442,141.81**</span><span class="sxs-lookup"><span data-stu-id="8e47b-158">**$7,442,141.81**</span></span>|<span data-ttu-id="8e47b-159">**$39,698.30**</span><span class="sxs-lookup"><span data-stu-id="8e47b-159">**$39,698.30**</span></span>|<span data-ttu-id="8e47b-160">**0.53%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-160">**0.53%**</span></span>|  
|<span data-ttu-id="8e47b-161">**Touring-1000**</span><span class="sxs-lookup"><span data-stu-id="8e47b-161">**Touring-1000**</span></span>|<span data-ttu-id="8e47b-162">**$6,723,794.29**</span><span class="sxs-lookup"><span data-stu-id="8e47b-162">**$6,723,794.29**</span></span>|<span data-ttu-id="8e47b-163">**$166,144.17**</span><span class="sxs-lookup"><span data-stu-id="8e47b-163">**$166,144.17**</span></span>|<span data-ttu-id="8e47b-164">**2,47%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-164">**2.47%**</span></span>|  
|<span data-ttu-id="8e47b-165">**Road-550-W**</span><span class="sxs-lookup"><span data-stu-id="8e47b-165">**Road-550-W**</span></span>|<span data-ttu-id="8e47b-166">**$3,668,383.88**</span><span class="sxs-lookup"><span data-stu-id="8e47b-166">**$3,668,383.88**</span></span>|<span data-ttu-id="8e47b-167">**$1,901.97**</span><span class="sxs-lookup"><span data-stu-id="8e47b-167">**$1,901.97**</span></span>|<span data-ttu-id="8e47b-168">**0, 5%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-168">**0.05%**</span></span>|  
|<span data-ttu-id="8e47b-169">**Road-350-W**</span><span class="sxs-lookup"><span data-stu-id="8e47b-169">**Road-350-W**</span></span>|<span data-ttu-id="8e47b-170">**$3,665,932.31**</span><span class="sxs-lookup"><span data-stu-id="8e47b-170">**$3,665,932.31**</span></span>|<span data-ttu-id="8e47b-171">**$20,946.50**</span><span class="sxs-lookup"><span data-stu-id="8e47b-171">**$20,946.50**</span></span>|<span data-ttu-id="8e47b-172">**0,57%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-172">**0.57%**</span></span>|  
|<span data-ttu-id="8e47b-173">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="8e47b-173">**HL Mountain Frame**</span></span>|<span data-ttu-id="8e47b-174">**$3,365,069.27**</span><span class="sxs-lookup"><span data-stu-id="8e47b-174">**$3,365,069.27**</span></span>|<span data-ttu-id="8e47b-175">**$174.11**</span><span class="sxs-lookup"><span data-stu-id="8e47b-175">**$174.11**</span></span>|<span data-ttu-id="8e47b-176">**0, 1%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-176">**0.01%**</span></span>|  
|<span data-ttu-id="8e47b-177">**Road-150**</span><span class="sxs-lookup"><span data-stu-id="8e47b-177">**Road-150**</span></span>|<span data-ttu-id="8e47b-178">**$2,363,805.16**</span><span class="sxs-lookup"><span data-stu-id="8e47b-178">**$2,363,805.16**</span></span>|<span data-ttu-id="8e47b-179">**$0**</span><span class="sxs-lookup"><span data-stu-id="8e47b-179">**$0.00**</span></span>|<span data-ttu-id="8e47b-180">**0, 0%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-180">**0.00%**</span></span>|  
|<span data-ttu-id="8e47b-181">**Touring-3000**</span><span class="sxs-lookup"><span data-stu-id="8e47b-181">**Touring-3000**</span></span>|<span data-ttu-id="8e47b-182">**$2,046,508.26**</span><span class="sxs-lookup"><span data-stu-id="8e47b-182">**$2,046,508.26**</span></span>|<span data-ttu-id="8e47b-183">**$79,582.15**</span><span class="sxs-lookup"><span data-stu-id="8e47b-183">**$79,582.15**</span></span>|<span data-ttu-id="8e47b-184">**3,89%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-184">**3.89%**</span></span>|  
  
 <span data-ttu-id="8e47b-185">O conjunto obtido com base nos produtos parece ser igual a Preferred10Products; assim, verificando o conjunto Preferred10Products:</span><span class="sxs-lookup"><span data-stu-id="8e47b-185">The obtained set of products seems to be the same as Preferred10Products; so, verifying the Preferred10Products set:</span></span>  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `set Preferred10Products as '`  
  
 `{[Product].[Model Name].&[Mountain-200],`  
  
 `[Product].[Model Name].&[Road-250],`  
  
 `[Product].[Model Name].&[Mountain-100],`  
  
 `[Product].[Model Name].&[Road-650],`  
  
 `[Product].[Model Name].&[Touring-1000],`  
  
 `[Product].[Model Name].&[Road-550-W],`  
  
 `[Product].[Model Name].&[Road-350-W],`  
  
 `[Product].[Model Name].&[HL Mountain Frame],`  
  
 `[Product].[Model Name].&[Road-150],`  
  
 `[Product].[Model Name].&[Touring-3000]`  
  
 `}'`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Preferred10Products on 1`  
  
 `from [Adventure Works]`  
  
 <span data-ttu-id="8e47b-186">De acordo com os resultados a seguir, os dois conjuntos (Top10SellingProducts, Preferred10Products) são iguais</span><span class="sxs-lookup"><span data-stu-id="8e47b-186">As per the following results, both sets (Top10SellingProducts, Preferred10Products) are the same</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="8e47b-187">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="8e47b-187">**Reseller Sales Amount**</span></span>|<span data-ttu-id="8e47b-188">**Valor de desconto**</span><span class="sxs-lookup"><span data-stu-id="8e47b-188">**Discount Amount**</span></span>|<span data-ttu-id="8e47b-189">**Desconto PCT**</span><span class="sxs-lookup"><span data-stu-id="8e47b-189">**PCT Discount**</span></span>|  
|<span data-ttu-id="8e47b-190">**Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="8e47b-190">**Mountain-200**</span></span>|<span data-ttu-id="8e47b-191">**$14,356,699.36**</span><span class="sxs-lookup"><span data-stu-id="8e47b-191">**$14,356,699.36**</span></span>|<span data-ttu-id="8e47b-192">**$19,012.71**</span><span class="sxs-lookup"><span data-stu-id="8e47b-192">**$19,012.71**</span></span>|<span data-ttu-id="8e47b-193">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-193">**0.13%**</span></span>|  
|<span data-ttu-id="8e47b-194">**Road-250**</span><span class="sxs-lookup"><span data-stu-id="8e47b-194">**Road-250**</span></span>|<span data-ttu-id="8e47b-195">**$9,377,457.68**</span><span class="sxs-lookup"><span data-stu-id="8e47b-195">**$9,377,457.68**</span></span>|<span data-ttu-id="8e47b-196">**$4,032.47**</span><span class="sxs-lookup"><span data-stu-id="8e47b-196">**$4,032.47**</span></span>|<span data-ttu-id="8e47b-197">**0, 4%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-197">**0.04%**</span></span>|  
|<span data-ttu-id="8e47b-198">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="8e47b-198">**Mountain-100**</span></span>|<span data-ttu-id="8e47b-199">**$8,568,958.27**</span><span class="sxs-lookup"><span data-stu-id="8e47b-199">**$8,568,958.27**</span></span>|<span data-ttu-id="8e47b-200">**$139,393.27**</span><span class="sxs-lookup"><span data-stu-id="8e47b-200">**$139,393.27**</span></span>|<span data-ttu-id="8e47b-201">**1,63%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-201">**1.63%**</span></span>|  
|<span data-ttu-id="8e47b-202">**Road-650**</span><span class="sxs-lookup"><span data-stu-id="8e47b-202">**Road-650**</span></span>|<span data-ttu-id="8e47b-203">**$7,442,141.81**</span><span class="sxs-lookup"><span data-stu-id="8e47b-203">**$7,442,141.81**</span></span>|<span data-ttu-id="8e47b-204">**$39,698.30**</span><span class="sxs-lookup"><span data-stu-id="8e47b-204">**$39,698.30**</span></span>|<span data-ttu-id="8e47b-205">**0.53%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-205">**0.53%**</span></span>|  
|<span data-ttu-id="8e47b-206">**Touring-1000**</span><span class="sxs-lookup"><span data-stu-id="8e47b-206">**Touring-1000**</span></span>|<span data-ttu-id="8e47b-207">**$6,723,794.29**</span><span class="sxs-lookup"><span data-stu-id="8e47b-207">**$6,723,794.29**</span></span>|<span data-ttu-id="8e47b-208">**$166,144.17**</span><span class="sxs-lookup"><span data-stu-id="8e47b-208">**$166,144.17**</span></span>|<span data-ttu-id="8e47b-209">**2,47%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-209">**2.47%**</span></span>|  
|<span data-ttu-id="8e47b-210">**Road-550-W**</span><span class="sxs-lookup"><span data-stu-id="8e47b-210">**Road-550-W**</span></span>|<span data-ttu-id="8e47b-211">**$3,668,383.88**</span><span class="sxs-lookup"><span data-stu-id="8e47b-211">**$3,668,383.88**</span></span>|<span data-ttu-id="8e47b-212">**$1,901.97**</span><span class="sxs-lookup"><span data-stu-id="8e47b-212">**$1,901.97**</span></span>|<span data-ttu-id="8e47b-213">**0, 5%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-213">**0.05%**</span></span>|  
|<span data-ttu-id="8e47b-214">**Road-350-W**</span><span class="sxs-lookup"><span data-stu-id="8e47b-214">**Road-350-W**</span></span>|<span data-ttu-id="8e47b-215">**$3,665,932.31**</span><span class="sxs-lookup"><span data-stu-id="8e47b-215">**$3,665,932.31**</span></span>|<span data-ttu-id="8e47b-216">**$20,946.50**</span><span class="sxs-lookup"><span data-stu-id="8e47b-216">**$20,946.50**</span></span>|<span data-ttu-id="8e47b-217">**0,57%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-217">**0.57%**</span></span>|  
|<span data-ttu-id="8e47b-218">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="8e47b-218">**HL Mountain Frame**</span></span>|<span data-ttu-id="8e47b-219">**$3,365,069.27**</span><span class="sxs-lookup"><span data-stu-id="8e47b-219">**$3,365,069.27**</span></span>|<span data-ttu-id="8e47b-220">**$174.11**</span><span class="sxs-lookup"><span data-stu-id="8e47b-220">**$174.11**</span></span>|<span data-ttu-id="8e47b-221">**0, 1%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-221">**0.01%**</span></span>|  
|<span data-ttu-id="8e47b-222">**Road-150**</span><span class="sxs-lookup"><span data-stu-id="8e47b-222">**Road-150**</span></span>|<span data-ttu-id="8e47b-223">**$2,363,805.16**</span><span class="sxs-lookup"><span data-stu-id="8e47b-223">**$2,363,805.16**</span></span>|<span data-ttu-id="8e47b-224">**$0**</span><span class="sxs-lookup"><span data-stu-id="8e47b-224">**$0.00**</span></span>|<span data-ttu-id="8e47b-225">**0, 0%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-225">**0.00%**</span></span>|  
|<span data-ttu-id="8e47b-226">**Touring-3000**</span><span class="sxs-lookup"><span data-stu-id="8e47b-226">**Touring-3000**</span></span>|<span data-ttu-id="8e47b-227">**$2,046,508.26**</span><span class="sxs-lookup"><span data-stu-id="8e47b-227">**$2,046,508.26**</span></span>|<span data-ttu-id="8e47b-228">**$79,582.15**</span><span class="sxs-lookup"><span data-stu-id="8e47b-228">**$79,582.15**</span></span>|<span data-ttu-id="8e47b-229">**3,89%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-229">**3.89%**</span></span>|  
  
 <span data-ttu-id="8e47b-230">O exemplo a seguir ilustrará o conceito de Autoexists profundo.</span><span class="sxs-lookup"><span data-stu-id="8e47b-230">The following example will illustrate the concept of deep Autoexists.</span></span> <span data-ttu-id="8e47b-231">No exemplo, nós estamos filtrando Top10SellingProducts pelo atributo [Product].[Product Line] para os itens no grupo [Mountain].</span><span class="sxs-lookup"><span data-stu-id="8e47b-231">In the example we are filtering Top10SellingProducts by [Product].[Product Line] attribute for those in [Mountain] group.</span></span> <span data-ttu-id="8e47b-232">Observe que os dois atributos (slicer e axis) pertencem a mesma dimensão, [Product].</span><span class="sxs-lookup"><span data-stu-id="8e47b-232">Note that both attributes (slicer and axis) belong to the same dimension, [Product].</span></span>  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `// Preferred10Products set removed for clarity`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Top10SellingProducts on 1`  
  
 `from [Adventure Works]`  
  
 `where [Product].[Product Line].[Mountain]`  
  
 <span data-ttu-id="8e47b-233">Gera o seguinte conjunto de resultados:</span><span class="sxs-lookup"><span data-stu-id="8e47b-233">Produces the following result set:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="8e47b-234">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="8e47b-234">**Reseller Sales Amount**</span></span>|<span data-ttu-id="8e47b-235">**Valor de desconto**</span><span class="sxs-lookup"><span data-stu-id="8e47b-235">**Discount Amount**</span></span>|<span data-ttu-id="8e47b-236">**Desconto PCT**</span><span class="sxs-lookup"><span data-stu-id="8e47b-236">**PCT Discount**</span></span>|  
|<span data-ttu-id="8e47b-237">**Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="8e47b-237">**Mountain-200**</span></span>|<span data-ttu-id="8e47b-238">**$14,356,699.36**</span><span class="sxs-lookup"><span data-stu-id="8e47b-238">**$14,356,699.36**</span></span>|<span data-ttu-id="8e47b-239">**$19,012.71**</span><span class="sxs-lookup"><span data-stu-id="8e47b-239">**$19,012.71**</span></span>|<span data-ttu-id="8e47b-240">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-240">**0.13%**</span></span>|  
|<span data-ttu-id="8e47b-241">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="8e47b-241">**Mountain-100**</span></span>|<span data-ttu-id="8e47b-242">**$8,568,958.27**</span><span class="sxs-lookup"><span data-stu-id="8e47b-242">**$8,568,958.27**</span></span>|<span data-ttu-id="8e47b-243">**$139,393.27**</span><span class="sxs-lookup"><span data-stu-id="8e47b-243">**$139,393.27**</span></span>|<span data-ttu-id="8e47b-244">**1,63%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-244">**1.63%**</span></span>|  
|<span data-ttu-id="8e47b-245">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="8e47b-245">**HL Mountain Frame**</span></span>|<span data-ttu-id="8e47b-246">**$3,365,069.27**</span><span class="sxs-lookup"><span data-stu-id="8e47b-246">**$3,365,069.27**</span></span>|<span data-ttu-id="8e47b-247">**$174.11**</span><span class="sxs-lookup"><span data-stu-id="8e47b-247">**$174.11**</span></span>|<span data-ttu-id="8e47b-248">**0, 1%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-248">**0.01%**</span></span>|  
|<span data-ttu-id="8e47b-249">**Mountain-300**</span><span class="sxs-lookup"><span data-stu-id="8e47b-249">**Mountain-300**</span></span>|<span data-ttu-id="8e47b-250">**$1,907,249.38**</span><span class="sxs-lookup"><span data-stu-id="8e47b-250">**$1,907,249.38**</span></span>|<span data-ttu-id="8e47b-251">**$876.95**</span><span class="sxs-lookup"><span data-stu-id="8e47b-251">**$876.95**</span></span>|<span data-ttu-id="8e47b-252">**0, 5%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-252">**0.05%**</span></span>|  
|<span data-ttu-id="8e47b-253">**Mountain-500**</span><span class="sxs-lookup"><span data-stu-id="8e47b-253">**Mountain-500**</span></span>|<span data-ttu-id="8e47b-254">**$1,067,327.31**</span><span class="sxs-lookup"><span data-stu-id="8e47b-254">**$1,067,327.31**</span></span>|<span data-ttu-id="8e47b-255">**$17,266.09**</span><span class="sxs-lookup"><span data-stu-id="8e47b-255">**$17,266.09**</span></span>|<span data-ttu-id="8e47b-256">**1,62%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-256">**1.62%**</span></span>|  
|<span data-ttu-id="8e47b-257">**Mountain-400-W**</span><span class="sxs-lookup"><span data-stu-id="8e47b-257">**Mountain-400-W**</span></span>|<span data-ttu-id="8e47b-258">**$592,450.05**</span><span class="sxs-lookup"><span data-stu-id="8e47b-258">**$592,450.05**</span></span>|<span data-ttu-id="8e47b-259">**$303.49**</span><span class="sxs-lookup"><span data-stu-id="8e47b-259">**$303.49**</span></span>|<span data-ttu-id="8e47b-260">**0, 5%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-260">**0.05%**</span></span>|  
|<span data-ttu-id="8e47b-261">**LL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="8e47b-261">**LL Mountain Frame**</span></span>|<span data-ttu-id="8e47b-262">**$521,864.42**</span><span class="sxs-lookup"><span data-stu-id="8e47b-262">**$521,864.42**</span></span>|<span data-ttu-id="8e47b-263">**$252.41**</span><span class="sxs-lookup"><span data-stu-id="8e47b-263">**$252.41**</span></span>|<span data-ttu-id="8e47b-264">**0, 5%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-264">**0.05%**</span></span>|  
|<span data-ttu-id="8e47b-265">**ML Mountain Frame-W**</span><span class="sxs-lookup"><span data-stu-id="8e47b-265">**ML Mountain Frame-W**</span></span>|<span data-ttu-id="8e47b-266">**$482,953.16**</span><span class="sxs-lookup"><span data-stu-id="8e47b-266">**$482,953.16**</span></span>|<span data-ttu-id="8e47b-267">**$206.95**</span><span class="sxs-lookup"><span data-stu-id="8e47b-267">**$206.95**</span></span>|<span data-ttu-id="8e47b-268">**0, 4%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-268">**0.04%**</span></span>|  
|<span data-ttu-id="8e47b-269">**ML Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="8e47b-269">**ML Mountain Frame**</span></span>|<span data-ttu-id="8e47b-270">**$343,785.29**</span><span class="sxs-lookup"><span data-stu-id="8e47b-270">**$343,785.29**</span></span>|<span data-ttu-id="8e47b-271">**$161.82**</span><span class="sxs-lookup"><span data-stu-id="8e47b-271">**$161.82**</span></span>|<span data-ttu-id="8e47b-272">**0, 5%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-272">**0.05%**</span></span>|  
|<span data-ttu-id="8e47b-273">**Women's Mountain Shorts**</span><span class="sxs-lookup"><span data-stu-id="8e47b-273">**Women's Mountain Shorts**</span></span>|<span data-ttu-id="8e47b-274">**$260,304.09**</span><span class="sxs-lookup"><span data-stu-id="8e47b-274">**$260,304.09**</span></span>|<span data-ttu-id="8e47b-275">**$6,675.56**</span><span class="sxs-lookup"><span data-stu-id="8e47b-275">**$6,675.56**</span></span>|<span data-ttu-id="8e47b-276">**2,56%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-276">**2.56%**</span></span>|  
  
 <span data-ttu-id="8e47b-277">No conjunto de resultados acima, havia sete itens novos na lista Top10SellingProducts, e Mountain-200, Mountain-100 e HL Mountain Frame foram movidos para o início da lista.</span><span class="sxs-lookup"><span data-stu-id="8e47b-277">In the above result set we have seven newcomers to the list of Top10SellingProducts and Mountain-200, Mountain-100, and HL Mountain Frame have moved to the top of the list.</span></span> <span data-ttu-id="8e47b-278">No conjunto de resultados anterior, esses três valores foram intercalados.</span><span class="sxs-lookup"><span data-stu-id="8e47b-278">In the previous result set those three values were interspersed.</span></span>  
  
 <span data-ttu-id="8e47b-279">Isso se chama Deep Autoexists, porque o conjunto Top10SellingProducts é avaliado para atender às condições de divisão da consulta.</span><span class="sxs-lookup"><span data-stu-id="8e47b-279">This is called Deep Autoexists, because the Top10SellingProducts set is evaluated to meet the slicing conditions of the query.</span></span> <span data-ttu-id="8e47b-280">Deep Autoexists significa que todas as expressões serão avaliadas para atender o espaço mais profundo possível após a aplicação das expressões de segmentação de dados, das expressões de subseleção no eixo etc.</span><span class="sxs-lookup"><span data-stu-id="8e47b-280">Deep Autoexists means that all expressions will be evaluated to meet the deepest possible space after applying the slicer expressions, the sub select expressions in the axis, and so on.</span></span>  
  
 <span data-ttu-id="8e47b-281">No entanto, pode ser que alguém queira ser capaz de executar a análise sobre Top10SellingProducts como equivalente a Preferred10Products, como no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="8e47b-281">However, one might want to be able to do the analysis over the Top10SellingProducts as equivalent to Preferred10Products, as in the following example:</span></span>  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `set Preferred10Products as '`  
  
 `{[Product].[Model Name].&[Mountain-200],`  
  
 `[Product].[Model Name].&[Road-250],`  
  
 `[Product].[Model Name].&[Mountain-100],`  
  
 `[Product].[Model Name].&[Road-650],`  
  
 `[Product].[Model Name].&[Touring-1000],`  
  
 `[Product].[Model Name].&[Road-550-W],`  
  
 `[Product].[Model Name].&[Road-350-W],`  
  
 `[Product].[Model Name].&[HL Mountain Frame],`  
  
 `[Product].[Model Name].&[Road-150],`  
  
 `[Product].[Model Name].&[Touring-3000]`  
  
 `}'`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Preferred10Products on 1`  
  
 `from [Adventure Works]`  
  
 `where [Product].[Product Line].[Mountain]`  
  
 <span data-ttu-id="8e47b-282">Gera o seguinte conjunto de resultados:</span><span class="sxs-lookup"><span data-stu-id="8e47b-282">Produces the following result set:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="8e47b-283">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="8e47b-283">**Reseller Sales Amount**</span></span>|<span data-ttu-id="8e47b-284">**Valor de desconto**</span><span class="sxs-lookup"><span data-stu-id="8e47b-284">**Discount Amount**</span></span>|<span data-ttu-id="8e47b-285">**Desconto PCT**</span><span class="sxs-lookup"><span data-stu-id="8e47b-285">**PCT Discount**</span></span>|  
|<span data-ttu-id="8e47b-286">**Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="8e47b-286">**Mountain-200**</span></span>|<span data-ttu-id="8e47b-287">**$14,356,699.36**</span><span class="sxs-lookup"><span data-stu-id="8e47b-287">**$14,356,699.36**</span></span>|<span data-ttu-id="8e47b-288">**$19,012.71**</span><span class="sxs-lookup"><span data-stu-id="8e47b-288">**$19,012.71**</span></span>|<span data-ttu-id="8e47b-289">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-289">**0.13%**</span></span>|  
|<span data-ttu-id="8e47b-290">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="8e47b-290">**Mountain-100**</span></span>|<span data-ttu-id="8e47b-291">**$8,568,958.27**</span><span class="sxs-lookup"><span data-stu-id="8e47b-291">**$8,568,958.27**</span></span>|<span data-ttu-id="8e47b-292">**$139,393.27**</span><span class="sxs-lookup"><span data-stu-id="8e47b-292">**$139,393.27**</span></span>|<span data-ttu-id="8e47b-293">**1,63%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-293">**1.63%**</span></span>|  
|<span data-ttu-id="8e47b-294">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="8e47b-294">**HL Mountain Frame**</span></span>|<span data-ttu-id="8e47b-295">**$3,365,069.27**</span><span class="sxs-lookup"><span data-stu-id="8e47b-295">**$3,365,069.27**</span></span>|<span data-ttu-id="8e47b-296">**$174.11**</span><span class="sxs-lookup"><span data-stu-id="8e47b-296">**$174.11**</span></span>|<span data-ttu-id="8e47b-297">**0, 1%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-297">**0.01%**</span></span>|  
  
 <span data-ttu-id="8e47b-298">Nos resultados acima, a segmentação de dados dá um resultado que contém apenas os produtos de Preferred10Products que fazem parte do grupo [Mountain] em [Product].[Product Line]; conforme o esperado, porque Preferred10Products é uma expressão constante.</span><span class="sxs-lookup"><span data-stu-id="8e47b-298">In the above results, the slicing gives a result that contains only those products from Preferred10Products that are part of the [Mountain] group in [Product].[Product Line]; as expected, because Preferred10Products is a constant expression.</span></span>  
  
 <span data-ttu-id="8e47b-299">Esse conjunto de resultados também é considerado Shallow Autoexists.</span><span class="sxs-lookup"><span data-stu-id="8e47b-299">This result set is also understood as Shallow Autoexists.</span></span> <span data-ttu-id="8e47b-300">Isso ocorre porque a expressão é avaliada antes da cláusula de divisão.</span><span class="sxs-lookup"><span data-stu-id="8e47b-300">This is because the expression is evaluated before the slicing clause.</span></span> <span data-ttu-id="8e47b-301">No exemplo anterior, a expressão era uma expressão constante para fins de ilustração, para introduzir o conceito.</span><span class="sxs-lookup"><span data-stu-id="8e47b-301">In the previous example, the expression was a constant expression for illustration purposes in order to introduce the concept.</span></span>  
  
 <span data-ttu-id="8e47b-302">O comportamento de Autoexists pode ser modificado no nível da sessão com o uso da propriedade da cadeia de caracteres de conexão `Autoexists`.</span><span class="sxs-lookup"><span data-stu-id="8e47b-302">Autoexists behavior can be modified at the session level using the `Autoexists` connection string property.</span></span> <span data-ttu-id="8e47b-303">O exemplo a seguir começa abrindo uma nova sessão e adicionando a propriedade *Autoexists=3* à cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="8e47b-303">The following example begins by opening a new session and adding the *Autoexists=3* property to the connection string.</span></span> <span data-ttu-id="8e47b-304">Você deve abrir uma nova conexão para executar o exemplo.</span><span class="sxs-lookup"><span data-stu-id="8e47b-304">You must open a new connection in order to do the example.</span></span> <span data-ttu-id="8e47b-305">Após o estabelecimento da conexão com a configuração Autoexist, ela permanecerá em efeito até que a conexão seja encerrada.</span><span class="sxs-lookup"><span data-stu-id="8e47b-305">Once the connection is established with the Autoexist setting it will remain in effect until that connection is finished.</span></span>  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `//Preferred10Products set removed for clarity`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Top10SellingProducts on 1`  
  
 `from [Adventure Works]`  
  
 `where [Product].[Product Line].[Mountain]`  
  
 <span data-ttu-id="8e47b-306">O conjunto de resultados a seguir agora mostra o comportamento superficial de Autoexists.</span><span class="sxs-lookup"><span data-stu-id="8e47b-306">The following result set now shows the shallow behavior of Autoexists.</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="8e47b-307">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="8e47b-307">**Reseller Sales Amount**</span></span>|<span data-ttu-id="8e47b-308">**Valor de desconto**</span><span class="sxs-lookup"><span data-stu-id="8e47b-308">**Discount Amount**</span></span>|<span data-ttu-id="8e47b-309">**Desconto PCT**</span><span class="sxs-lookup"><span data-stu-id="8e47b-309">**PCT Discount**</span></span>|  
|<span data-ttu-id="8e47b-310">**Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="8e47b-310">**Mountain-200**</span></span>|<span data-ttu-id="8e47b-311">**$14,356,699.36**</span><span class="sxs-lookup"><span data-stu-id="8e47b-311">**$14,356,699.36**</span></span>|<span data-ttu-id="8e47b-312">**$19,012.71**</span><span class="sxs-lookup"><span data-stu-id="8e47b-312">**$19,012.71**</span></span>|<span data-ttu-id="8e47b-313">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-313">**0.13%**</span></span>|  
|<span data-ttu-id="8e47b-314">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="8e47b-314">**Mountain-100**</span></span>|<span data-ttu-id="8e47b-315">**$8,568,958.27**</span><span class="sxs-lookup"><span data-stu-id="8e47b-315">**$8,568,958.27**</span></span>|<span data-ttu-id="8e47b-316">**$139,393.27**</span><span class="sxs-lookup"><span data-stu-id="8e47b-316">**$139,393.27**</span></span>|<span data-ttu-id="8e47b-317">**1,63%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-317">**1.63%**</span></span>|  
|<span data-ttu-id="8e47b-318">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="8e47b-318">**HL Mountain Frame**</span></span>|<span data-ttu-id="8e47b-319">**$3,365,069.27**</span><span class="sxs-lookup"><span data-stu-id="8e47b-319">**$3,365,069.27**</span></span>|<span data-ttu-id="8e47b-320">**$174.11**</span><span class="sxs-lookup"><span data-stu-id="8e47b-320">**$174.11**</span></span>|<span data-ttu-id="8e47b-321">**0, 1%**</span><span class="sxs-lookup"><span data-stu-id="8e47b-321">**0.01%**</span></span>|  
  
 <span data-ttu-id="8e47b-322">O comportamento de autoexisteções pode ser modificado usando o parâmetro Autoexists = [1 | 2 | 3] na cadeia de conexão; consulte [Propriedades XMLA com suporte &#40;&#41;XMLA](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/propertylist-element-supported-xmla-properties) e <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.ConnectionString%2A> para uso de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8e47b-322">Autoexists behavior can be modified by using the AUTOEXISTS=[1|2|3] parameter in the connection string; see [Supported XMLA Properties &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/propertylist-element-supported-xmla-properties) and <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.ConnectionString%2A> for parameter usage.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e47b-323">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8e47b-323">See Also</span></span>  
 <span data-ttu-id="8e47b-324">[Conceitos principais em MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="8e47b-324">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="8e47b-325">[Espaço do cubo](cube-space.md) </span><span class="sxs-lookup"><span data-stu-id="8e47b-325">[Cube Space](cube-space.md) </span></span>  
 <span data-ttu-id="8e47b-326">[Tuplas](tuples.md) </span><span class="sxs-lookup"><span data-stu-id="8e47b-326">[Tuples](tuples.md) </span></span>  
 <span data-ttu-id="8e47b-327">[Trabalhando com membros, tuplas e conjuntos &#40;&#41;MDX](working-with-members-tuples-and-sets-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="8e47b-327">[Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md) </span></span>  
 <span data-ttu-id="8e47b-328">[Totais visuais e totais não visuais](visual-totals-and-non-visual-totals.md) </span><span class="sxs-lookup"><span data-stu-id="8e47b-328">[Visual Totals and Non Visual Totals](visual-totals-and-non-visual-totals.md) </span></span>  
 <span data-ttu-id="8e47b-329">[Referência de linguagem MDX &#40;&#41;MDX](/sql/mdx/mdx-language-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="8e47b-329">[MDX Language Reference &#40;MDX&#41;](/sql/mdx/mdx-language-reference-mdx) </span></span>  
 [<span data-ttu-id="8e47b-330">Referência de expressões multidimensionais &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="8e47b-330">Multidimensional Expressions &#40;MDX&#41; Reference</span></span>](/sql/mdx/multidimensional-expressions-mdx-reference)  
  
  
